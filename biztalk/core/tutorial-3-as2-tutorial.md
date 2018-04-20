---
title: 'チュートリアル 3: AS2 チュートリアル |Microsoft ドキュメント'
ms.custom: ''
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: ''
ms.suite: ''
ms.tgt_pltfrm: ''
ms.topic: article
ms.assetid: 018829a9-e670-4b87-bac5-7f7b1332d90e
caps.latest.revision: 32
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: 03de45aa09b2704f205b81db4c513a0da5770ee3
ms.sourcegitcommit: 36350889f318e1f7e0ac9506dc8df794d475bda6
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 04/20/2018
---
# <a name="tutorial-3-as2-tutorial"></a>チュートリアル 3: AS2 チュートリアル
このチュートリアルでは、HTTP トランスポートを経由して EDIINT/AS2 でエンコードされたメッセージを受信および送信するソリューションを設定します。  
  
 **チュートリアルのソリューションのしくみ**  
  
 このソリューションは次の処理を実行します。  
  
-   パートナー (Fabrikam) から AS2 メッセージを受信する  
  
-   パートナーに MDN 応答を非同期に返す  
  
-   AS2 メッセージの EDI ペイロードを処理する  
  
-   AS2 を介してパートナー (Fabrikam) に 997 受信確認を返す  
  
-   EDI メッセージのペイロードを含む XML ファイルをホーム組織 (Contoso) のバックエンド アプリケーションにルーティングする  
  
    > [!NOTE]
    >  このソリューションは、AS2 メッセージのセキュリティを確保するために署名または暗号化を使用しません。  
  
 **チュートリアル コンポーネント**  
  
 このソリューションは次のものを使用します。  
  
-   BTS Http Receive ISAPI フィルタ、送信側から AS2 または EDI メッセージを受信する **(/Contoso/BTSHTTPReceive.dll**)。  
  
-   997 受信確認および MDN を返すことによって、パートナーをシミュレートするために ASPX Web ページ (**http://localhost/Fabrikam/Default.aspx**)。  
  
-   864 スキーマおよびその他のスキーマの展開に使用するプロジェクト ファイル (**Schemas.btproj**)。  
  
-   一方向の HTTP 受信 EDI ファイルを受信する場所 (**Receive_AS2**)。 この受信場所は、AS2 デコーダーおよび EDI 逆アセンブラーを含む既定の AS2EdiReceive パイプラインを使用します。  
  
-   動的な HTTP 送信ポート非同期 MDN の返信を (**Send_Async_MDN**)。 この送信ポートは、AS2 エンコーダーを含む AS2Send パイプラインを使用します。  
  
-   静的な一方向の FILE 送信 EDI ペイロードをバックエンド フォルダーに XML ファイルにルーティングするポート (**Send_Payload_EdiXml**)。 この送信ポートは、PassThruTransmit 送信パイプラインを使用します。  
  
-   静的な一方向 HTTP 送信ポートを AS2 経由でパートナーに 997 受信確認を返す (**Send_Async_997**)。 この送信ポートは、AS2 エンコーダーを含む AS2Send パイプラインを使用しますが、EDI アセンブラーは不要です。  
  
-   Fabrikam パートナーから EDI ファイルを BizTalk に送信するアプリケーションの構築に使用するプロジェクト ファイル (**Sender.csproj**)。  
  
 **メッセージ フロー**  
  
 完全なソリューションにおけるメッセージ フローを次の図に示します。  
  
 ![AS2 チュートリアル メッセージ フロー](../core/media/31710c1d-4070-433e-953d-dcbfd0bb07a0.gif "31710c1d-4070-433e-953d-dcbfd0bb07a0")  
  
 チュートリアル コンポーネントでは、次のようにメッセージが処理されます。  
  
1.  使用する、 **sender.exe アプリケーション** パートナー Fabrikam から BizTalk Server コンピューターに、元の EDI および AS2 メッセージを送信します。 sender.exe は、Contoso 仮想ディレクトリに EDI/AS2 メッセージを送信します。  
  
    > [!NOTE]
    >  この一覧のイベントは、示されている順序で発生するとは限りません。  
    >   
    >  テスト メッセージは X12_00401_864.edi で、場所は \Program Files\Microsoft BizTalk Server 20xx\SDK\AS2 Tutorial です。  
  
2.  **Receive_AS2** 一方向受信場所は、Contoso 仮想ディレクトリからファイルを選択する、BTSHTTPReceive.dll ISAPI 拡張機能を使用して、Fabrikam から EDI メッセージを受信します。 受信パイプラインは、AS2 メッセージをデコードし、EDI インターチェンジを逆アセンブルした後、メッセージ XML を MessageBox にドロップします。  
  
3.  受信パイプラインは AS2 メッセージの MDN を生成します。MDN は非同期になるように設定されているため、受信パイプラインは MDN を MessageBox にドロップします。  
  
4.  受信パイプラインは、EDI インターチェンジに応答して 997 受信確認を生成し、997 を MessageBox にドロップします。  
  
5.  **Send_Payload_EdiXml** 静的な一方向送信ポート EDI ペイロードを MessageBox から取得、BTS のフィルター処理します。MessageType のコンテキスト プロパティです。  
  
6.  ペイロードの送信ポートの送信で表されるバックエンド Contoso アプリケーションに、EDI ペイロードを含む XML ファイル、 \\_EDIXMLToContoso フォルダーです。 この送信ポートは、PassThruTransmit 送信パイプラインを使用します。  
  
7.  **Send_Async_MDN** 動的送信ポート、非同期 MDN を MessageBox から取得、EdiIntAS.IsAS2AsynchronousMdn コンテキスト プロパティに関してフィルター処理します。  
  
8.  MDN 送信ポートを返します。 MDN を、 \\_MDNToFabrikam フォルダーです。 これは、動的送信ポートであるため、アドレスを使用して、メッセージのヘッダーの Receipt-delivery-option 行 (**http://localhost/Fabrikam/Default.aspx?Destination=_MDNToFabrikam**) にメッセージをルーティングする、 \\_MDNToFabrikam フォルダーです。  
  
9. **Send_Async_997** ポート 997 を MessageBox から取得、フィルタ リング、BTS を送信します。MessageType のコンテキスト プロパティです。  
  
10. 997 送信ポートの使用を EdiReceive によって生成された 997 メッセージを受信するためのパイプラインを送信する HTTP トランスポート、 \\_ 997tofabrikam フォルダーです。 送信ポートは、URI を使用して、Fabrikam default.aspx ページにメッセージを送信 **http://localhost/Fabrikam/Default.aspx?Destination=_997ToFabrikam**です。 Default.aspx ページに 997 を送信し、 \\_ 997tofabrikam フォルダーです。  
  
 このチュートリアルを行うには、次の知識が必要です。  
  
-   BizTalk Server パイプラインとパイプライン コンポーネント  
  
-   HTTP アダプター  
  
-   ポートと受信場所が表示されます。  
  
-   [送信ポート]  
  
## <a name="in-this-section"></a>このセクションの内容  
  
-   [手順 1: AS2 チュートリアルの準備](../core/step-1-prepare-for-the-as2-tutorial.md)  
  
-   [手順 2: サンプル X12 スキーマの作成と展開](../core/step-2-create-and-deploy-the-sample-x12-schema.md)  
  
-   [手順 3: 組織のパーティとビジネス プロファイルを構成する](../core/step-3-configure-a-party-and-business-profile-for-your-organization2.md)  
  
-   [手順 4: パーティとビジネス プロファイルを取引先として構成する](../core/step-4-configure-a-party-and-business-profile-for-your-trading-partner2.md)  
  
-   [手順 5: 取引先の Web ページの構成](../core/step-5-configure-the-trading-partner-web-pages.md)  
  
-   [手順 6: EDI-AS2 の受信場所の構成](../core/step-6-configure-the-edi-as2-receive-location.md)  
  
-   [手順 7: MDN 送信ポートの構成](../core/step-7-configure-the-mdn-send-port.md)  
  
-   [手順 8: 997 送信ポートの構成](../core/step-8-configure-the-997-send-port.md)  
  
-   [手順 9: EDI ペイロード送信ポートの構成](../core/step-9-configure-the-edi-payload-send-port.md)  
  
-   [手順 10: X12 および AS2 取引先契約の構成](../core/step-10-configure-the-x12-and-as2-trading-partner-agreement.md)  
  
-   [手順 11: AS2 ソリューションのテスト](../core/step-11-test-the-as2-solution.md)  
  
## <a name="see-also"></a>参照  
 [BizTalk Server チュートリアル](../core/biztalk-server-tutorials.md)