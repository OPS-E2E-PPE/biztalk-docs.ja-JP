---
title: 'チュートリアル 3: AS2 チュートリアル |Microsoft Docs'
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
ms.openlocfilehash: b629d1390b6471fb85a0b9e6fb6b605bedb043a6
ms.sourcegitcommit: 266308ec5c6a9d8d80ff298ee6051b4843c5d626
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 06/27/2018
ms.locfileid: "37013467"
---
# <a name="tutorial-3-as2-tutorial"></a>チュートリアル 3: AS2 チュートリアル
このチュートリアルでは、HTTP トランスポートを経由して EDIINT/AS2 でエンコードされたメッセージを受信および送信するソリューションを設定します。  
  
 **チュートリアル ソリューションのしくみ**  
  
 このソリューションは次の処理を実行します。  
  
- パートナー (Fabrikam) から AS2 メッセージを受信する  
  
- パートナーに MDN 応答を非同期に返す  
  
- AS2 メッセージの EDI ペイロードを処理する  
  
- AS2 を介してパートナー (Fabrikam) に 997 受信確認を返す  
  
- EDI メッセージのペイロードを含む XML ファイルをホーム組織 (Contoso) のバックエンド アプリケーションにルーティングする  
  
  > [!NOTE]
  >  このソリューションは、AS2 メッセージのセキュリティを確保するために署名または暗号化を使用しません。  
  
  **チュートリアル コンポーネント**  
  
  このソリューションは次のものを使用します。  
  
- BTS Http Receive ISAPI フィルタ、送信側から AS2 または EDI メッセージを受信する **(/Contoso/BTSHTTPReceive.dll**)。  
  
- 997 受信確認および MDN を返すことによって、パートナーをシミュレートするために ASPX Web ページ (**http://localhost/Fabrikam/Default.aspx**)。  
  
- 使用する 864 スキーマおよびその他のスキーマをデプロイするプロジェクト ファイル (**Schemas.btproj**)。  
  
- 一方向の HTTP 受信場所で EDI ファイルを受信する (**Receive_AS2**)。 この受信場所は、AS2 デコーダーおよび EDI 逆アセンブラーを含む既定の AS2EdiReceive パイプラインを使用します。  
  
- 動的な HTTP 送信ポートを非同期 MDN を返す (**Send_Async_MDN**)。 この送信ポートは、AS2 エンコーダーを含む AS2Send パイプラインを使用します。  
  
- 静的な一方向の FILE 送信ポートをバックエンド フォルダーに XML ファイルに、EDI ペイロードをルーティングする (**Send_Payload_EdiXml**)。 この送信ポートは、PassThruTransmit 送信パイプラインを使用します。  
  
- 静的な一方向 HTTP 送信ポートを AS2 経由でパートナーに 997 受信確認を返す (**Send_Async_997**)。 この送信ポートは、AS2 エンコーダーを含む AS2Send パイプラインを使用しますが、EDI アセンブラーは不要です。  
  
- Fabrikam 取引先から EDI ファイルを BizTalk に送信するアプリケーションの構築に使用するプロジェクト ファイル (**Sender.csproj**)。  
  
  **メッセージ フロー**  
  
  完全なソリューションにおけるメッセージ フローを次の図に示します。  
  
  ![AS2 チュートリアル メッセージ フロー](../core/media/31710c1d-4070-433e-953d-dcbfd0bb07a0.gif "31710c1d-4070-433e-953d-dcbfd0bb07a0")  
  
  チュートリアル コンポーネントでは、次のようにメッセージが処理されます。  
  
1. 使用する、 **sender.exe アプリケーション**パートナー Fabrikam から BizTalk Server コンピューターに、元の EDI および AS2 メッセージを送信します。 sender.exe は、Contoso 仮想ディレクトリに EDI/AS2 メッセージを送信します。  
  
   > [!NOTE]
   >  この一覧のイベントは、示されている順序で発生するとは限りません。  
   >   
   >  テスト メッセージは X12_00401_864.edi で、場所は \Program Files\Microsoft BizTalk Server 20xx\SDK\AS2 Tutorial です。  
  
2. **Receive_AS2**一方向受信場所が Contoso 仮想ディレクトリからファイルを取得する、BTSHTTPReceive.dll ISAPI 拡張機能を使用して、Fabrikam から EDI メッセージを受信します。 受信パイプラインは、AS2 メッセージをデコードし、EDI インターチェンジを逆アセンブルした後、メッセージ XML を MessageBox にドロップします。  
  
3. 受信パイプラインは AS2 メッセージの MDN を生成します。MDN は非同期になるように設定されているため、受信パイプラインは MDN を MessageBox にドロップします。  
  
4. 受信パイプラインは、EDI インターチェンジに応答して 997 受信確認を生成し、997 を MessageBox にドロップします。  
  
5. **Send_Payload_EdiXml**静的な一方向の送信ポートを取得、EDI ペイロードをメッセージ ボックスから、BTS のフィルター処理します。MessageType のコンテキスト プロパティです。  
  
6. ペイロード送信ポートで表されるバックエンド Contoso アプリケーションは、EDI ペイロードを含む XML ファイル、 \\_EDIXMLToContoso フォルダー。 この送信ポートは、PassThruTransmit 送信パイプラインを使用します。  
  
7. **Send_Async_MDN**動的送信ポート非同期 mdn はから取得し、メッセージ ボックス、EdiIntAS.IsAS2AsynchronousMdn コンテキスト プロパティに関してフィルタ処理します。  
  
8. MDN 送信ポートを返します。 MDN を、 \\_MDNToFabrikam フォルダー。 これは、動的送信ポートであるためには、メッセージのヘッダーの Receipt-delivery-option 行にアドレスが使用されます (**http://localhost/Fabrikam/Default.aspx?Destination=_MDNToFabrikam**) にメッセージをルーティングする、 \\_MDNToFabrikam フォルダー。  
  
9. **Send_Async_997**送信ポートから取得し、997、メッセージ ボックス、BTS のフィルター処理します。MessageType のコンテキスト プロパティです。  
  
10. 997 送信ポートの使用、EdiReceive によって生成された 997 メッセージ受信パイプラインに送信する HTTP トランスポート、 \\_ 997tofabrikam フォルダー。 送信ポートの URI を使用して、Fabrikam default.aspx ページにメッセージを送信する **http://localhost/Fabrikam/Default.aspx?Destination=_997ToFabrikam**します。 Default.aspx ページに 997 を送信し、 \\_ 997tofabrikam フォルダー。  
  
    このチュートリアルを行うには、次の知識が必要です。  
  
-   BizTalk Server パイプラインとパイプライン コンポーネント  
  
-   HTTP アダプター  
  
-   受信ポートと受信場所  
  
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