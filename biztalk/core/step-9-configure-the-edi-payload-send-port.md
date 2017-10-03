---
title: "手順 9: EDI ペイロードの送信ポートの構成 |Microsoft ドキュメント"
ms.custom: 
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: 
ms.suite: 
ms.tgt_pltfrm: 
ms.topic: article
ms.assetid: 71a8a4a7-7c3e-4e33-a9c0-a6445a3cc236
caps.latest.revision: "18"
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: 9de1dff24af11cd03cda2550dcab921aec25d585
ms.sourcegitcommit: cb908c540d8f1a692d01dc8f313e16cb4b4e696d
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 09/20/2017
---
# <a name="step-9-configure-the-edi-payload-send-port"></a>手順 9: EDI ペイロードの送信ポートを構成します。
![手順 11 の 9](../core/media/tut-step9-of-11.gif "Tut_Step9_of_11")  
  
 によって表されるバックエンド Contoso アプリケーションに、EDI ペイロードから生成された XML を送信する送信ポートを設定するこの手順で、 \\_EDIXMLToContoso フォルダーです。 この送信ポートは、PassThruTransmit 送信パイプラインを使用します。  
  
## <a name="prerequisites"></a>前提条件  
 [!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)] 管理者グループのメンバーとしてログオンしている必要があります。  
  
### <a name="to-create-the-sendpayloadedixml-send-port"></a>Send_Payload_EdiXml 送信ポートを作成するには  
  
1.  [!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)]管理コンソールを右クリックして**送信ポート**、 をポイント**新規**、クリックして**静的な一方向送信ポート**です。  
  
2.  **送信ポートのプロパティ** ダイアログ ボックスで、送信ポート名**Send_Payload_EdiXml**です。 選択**ファイル**の**型**、クリックして**構成**です。  
  
    > [!NOTE]
    >  送信パイプラインではペイロード ファイルの AS2 処理を行わないため、種類には [FILE] を指定します。 送信パイプラインでは、ペイロード ファイルをローカル フォルダにルーティングして、EDI トランザクション セットが表示されるようにするだけです。  
  
3.  **FILE トランスポートのプロパティ** ダイアログ ボックスの**コピー先フォルダー**を参照して選択[!INCLUDE[btsBiztalkServerPath](../includes/btsbiztalkserverpath-md.md)]sdk \as2 Tutorial\\_EDIXMLToContoso です。 ままにして**ファイル名**として**%MessageID%.xml**です。 **[OK]**をクリックします。  
  
4.  既定の**PassThruTransmit**の**送信パイプライン**です。  
  
    > [!NOTE]
    >  PassThruTransmit 送信パイプラインを使用するため、パイプラインではペイロード メッセージの EDI 処理は実行されませんが、ペイロード メッセージは AS2EdiReceive receive パイプラインで生成された XML の形式でローカル フォルダに送信されます。  
  
5.  をクリックして**フィルター**コンソール ツリーでします。 **プロパティ**、入力**BTS です。MessageType**です。 **演算子**、入力 **==**です。 **値**、入力`http://schemas.microsoft.com/BizTalk/Edi/X12/2006#X12_00401_864`です。  
  
    > [!NOTE]
    >  このフィルタにより、この送信ポートはメッセージ ボックスから X12 864 ペイロード メッセージのみを取得するようになります。  
  
6.  **[OK]**をクリックします。  
  
7.  **送信ポート**のペイン、[!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)]管理コンソールを右クリックし、 **Send_Payload_EdiXml**送信ポートをクリックして**開始**です。  
  
## <a name="next-steps"></a>次の手順  
 AS2 および X12 を作成する間、2 つの取引アグリーメントのパートナー、」の説明に従って[手順 10: X12 および AS2 取引先アグリーメントを構成します。](../core/step-10-configure-the-x12-and-as2-trading-partner-agreement.md)  
  
## <a name="see-also"></a>参照  
 [チュートリアル 3: AS2 チュートリアル](../core/tutorial-3-as2-tutorial.md)