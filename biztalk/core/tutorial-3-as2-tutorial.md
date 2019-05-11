---
title: チュートリアル 3:AS2 チュートリアル |Microsoft Docs
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
ms.openlocfilehash: a0fb5f48a8e85c318b85322557ac940e36ecd142
ms.sourcegitcommit: 381e83d43796a345488d54b3f7413e11d56ad7be
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 05/07/2019
ms.locfileid: "65401710"
---
# <a name="tutorial-3-as2-tutorial"></a>チュートリアル 3:AS2 チュートリアル
このチュートリアルでは、受信し、HTTP トランスポートを介して EDIINT/AS2 でエンコードされたメッセージを送信するソリューションを設定します。  
  
 **チュートリアル ソリューションのしくみ**  
  
 このソリューションは次の処理を実行します。  
  
- パートナー (Fabrikam) から AS2 メッセージを受信します。  
  
- パートナーに非同期的に MDN 応答を返す  
  
- AS2 メッセージの EDI ペイロードを処理します。  
  
- AS2 経由でパートナー (Fabrikam) に 997 受信確認を返す  
  
- ホーム組織 (Contoso) のバックエンド アプリケーションに EDI メッセージのペイロードを含む XML ファイルをルーティングします。  
  
  > [!NOTE]
  >  このソリューションは、AS2 メッセージのセキュリティを確保するのに署名または暗号化を使用できません。  
  
  **チュートリアル コンポーネント**  
  
  このソリューションは、次のものを使用します。  
  
- BTS Http Receive ISAPI フィルタ、送信側から AS2 または EDI メッセージを受信する **(/Contoso/BTSHTTPReceive.dll**)。  
  
- 997 受信確認および MDN を返すことによって、パートナーをシミュレートするために ASPX Web ページ (**http://localhost/Fabrikam/Default.aspx**)。  
  
- 使用する 864 スキーマおよびその他のスキーマをデプロイするプロジェクト ファイル (**Schemas.btproj**)。  
  
- 一方向の HTTP 受信場所で EDI ファイルを受信する (**Receive_AS2**)。 これは受信 AS2 デコーダーおよび EDI 逆アセンブラーを含む既定の AS2EdiReceive パイプラインで、場所が使用します。  
  
- 動的な HTTP 送信ポートを非同期 MDN を返す (**Send_Async_MDN**)。 この送信ポートは、AS2 エンコーダーを含む AS2Send パイプラインを使用します。  
  
- 静的な一方向の FILE 送信ポートをバックエンド フォルダーに XML ファイルに、EDI ペイロードをルーティングする (**Send_Payload_EdiXml**)。 この送信ポートは、PassThruTransmit 送信パイプラインを使用します。  
  
- 静的な一方向 HTTP 送信ポートを AS2 経由でパートナーに 997 受信確認を返す (**Send_Async_997**)。 この送信ポートは、AS2 エンコーダーが含まれている EDI アセンブラーの必要がない AS2Send パイプラインを使用します。  
  
- Fabrikam 取引先から EDI ファイルを BizTalk に送信するアプリケーションの構築に使用するプロジェクト ファイル (**Sender.csproj**)。  
  
  **メッセージ フロー**  
  
  完成したソリューションにおけるメッセージ フローは、次の図に示すようになります。  
  
  ![AS2 チュートリアル メッセージ フロー](../core/media/31710c1d-4070-433e-953d-dcbfd0bb07a0.gif "31710c1d-4070-433e-953d-dcbfd0bb07a0")  
  
  チュートリアル コンポーネントは、次のようなメッセージを処理します。  
  
1. 使用する、 **sender.exe アプリケーション**パートナー Fabrikam から BizTalk Server コンピューターに、元の EDI および AS2 メッセージを送信します。 Sender.exe は、Contoso 仮想ディレクトリに edi/as2 メッセージを送信します。  
  
   > [!NOTE]
   >  この一覧のイベントは、示されている順序で発生するとは限りません。  
   >   
   >  テスト メッセージは、\Program Files\Microsoft BizTalk Server 20xx \sdk\as2 Tutorial の X12_00401_864.edi です。  
  
2. **Receive_AS2**一方向受信場所が Contoso 仮想ディレクトリからファイルを取得する、BTSHTTPReceive.dll ISAPI 拡張機能を使用して、Fabrikam から EDI メッセージを受信します。 受信パイプラインは AS2 メッセージをデコード、EDI インターチェンジを逆アセンブル、および、メッセージ ボックスに XML メッセージを削除します。  
  
3. 受信パイプラインは、AS2 メッセージの MDN を生成し、受信パイプラインがメッセージ ボックスに MDN を削除するため、MDN は非同期に設定されて、します。  
  
4. 受信パイプラインでは、EDI インターチェンジへの応答で 997 受信確認を生成し、997 を MessageBox にドロップします。  
  
5. **Send_Payload_EdiXml**静的な一方向の送信ポートを取得、EDI ペイロードをメッセージ ボックスから、BTS のフィルター処理します。MessageType のコンテキスト プロパティです。  
  
6. ペイロード送信ポートで表されるバックエンド Contoso アプリケーションは、EDI ペイロードを含む XML ファイル、 \\_EDIXMLToContoso フォルダー。 この送信ポートは、PassThruTransmit 送信パイプラインを使用します。  
  
7. **Send_Async_MDN**動的送信ポート非同期 mdn はから取得し、メッセージ ボックス、EdiIntAS.IsAS2AsynchronousMdn コンテキスト プロパティに関してフィルタ処理します。  
  
8. MDN 送信ポートを返します。 MDN を、 \\_MDNToFabrikam フォルダー。 これは、動的送信ポートであるためには、メッセージのヘッダーの Receipt-delivery-option 行にアドレスが使用されます (**http://localhost/Fabrikam/Default.aspx?Destination=_MDNToFabrikam**) にメッセージをルーティングする、 \\_MDNToFabrikam フォルダー。  
  
9. **Send_Async_997**送信ポートから取得し、997、メッセージ ボックス、BTS のフィルター処理します。MessageType のコンテキスト プロパティです。  
  
10. 997 送信ポートの使用、EdiReceive によって生成された 997 メッセージ受信パイプラインに送信する HTTP トランスポート、 \\_ 997tofabrikam フォルダー。 送信ポートの URI を使用して、Fabrikam default.aspx ページにメッセージを送信する **http://localhost/Fabrikam/Default.aspx?Destination=_997ToFabrikam**します。 Default.aspx ページに 997 を送信し、 \\_ 997tofabrikam フォルダー。  
  
    このチュートリアルには、次の知識があります。  
  
-   BizTalk Server パイプラインおよびパイプライン コンポーネント  
  
-   HTTP アダプター  
  
-   受信ポートと受信場所  
  
-   送信ポート  
  
## <a name="in-this-section"></a>このセクションの内容  
  
-   [ステップ 1: AS2 チュートリアルを準備します。](../core/step-1-prepare-for-the-as2-tutorial.md)  
  
-   [手順 2:作成およびデプロイのサンプル X12 スキーマ](../core/step-2-create-and-deploy-the-sample-x12-schema.md)  
  
-   [ステップ 3:組織のパーティとビジネス プロファイルを構成します。](../core/step-3-configure-a-party-and-business-profile-for-your-organization2.md)  
  
-   [手順 4:取引先のパーティとビジネス プロファイルを構成します。](../core/step-4-configure-a-party-and-business-profile-for-your-trading-partner2.md)  
  
-   [手順 5:取引先パートナーの Web ページを構成します。](../core/step-5-configure-the-trading-partner-web-pages.md)  
  
-   [手順 6:EDI AS2 を構成する受信場所](../core/step-6-configure-the-edi-as2-receive-location.md)  
  
-   [手順 7:MDN の送信ポートを構成します。](../core/step-7-configure-the-mdn-send-port.md)  
  
-   [手順 8:997 送信ポートを構成します。](../core/step-8-configure-the-997-send-port.md)  
  
-   [手順 9:EDI ペイロード送信ポートを構成します。](../core/step-9-configure-the-edi-payload-send-port.md)  
  
-   [手順 10: X12 および AS2 取引先アグリーメントを構成します。](../core/step-10-configure-the-x12-and-as2-trading-partner-agreement.md)  
  
-   [手順 11: AS2 ソリューションをテストします。](../core/step-11-test-the-as2-solution.md)  
  
## <a name="see-also"></a>参照  
 [BizTalk Server チュートリアル](../core/biztalk-server-tutorials.md)