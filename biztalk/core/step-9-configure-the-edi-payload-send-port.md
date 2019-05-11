---
title: 手順 9:EDI ペイロード送信ポートの構成 |Microsoft Docs
ms.custom: ''
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: ''
ms.suite: ''
ms.tgt_pltfrm: ''
ms.topic: article
ms.assetid: 71a8a4a7-7c3e-4e33-a9c0-a6445a3cc236
caps.latest.revision: 18
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: 77a43ec4402cf2abf86d77e1d6d10512ff9d3694
ms.sourcegitcommit: 381e83d43796a345488d54b3f7413e11d56ad7be
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 05/07/2019
ms.locfileid: "65244218"
---
# <a name="step-9-configure-the-edi-payload-send-port"></a>手順 9:EDI ペイロード送信ポートを構成します。
![手順 11 の 9](../core/media/tut-step9-of-11.gif "Tut_Step9_of_11")  
  
 によって表されるバックエンド Contoso アプリケーションに、EDI ペイロードから生成される XML を送信する送信ポートを設定するこの手順で、 \\_EDIXMLToContoso フォルダー。 この送信ポートは、PassThruTransmit 送信パイプラインを使用します。  
  
## <a name="prerequisites"></a>前提条件  
 [!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)] 管理者グループのメンバーとしてログオンしている必要があります。  
  
### <a name="to-create-the-sendpayloadedixml-send-port"></a>Send_Payload_EdiXml 送信ポートを作成するには  
  
1. [!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)]管理コンソールで、右クリックして**送信ポート**、 をポイント**新規**、順にクリックします**静的な一方向送信ポート**します。  
  
2. **送信ポートのプロパティ**ダイアログ ボックスで、送信ポートに名前**Send_Payload_EdiXml**します。 選択**ファイル**の**型**、 をクリックし、**構成**します。  
  
   > [!NOTE]
   >  ファイルの種類は、送信パイプラインがペイロード ファイルに AS2 処理が実行していないために指定されます。 EDI トランザクション セットを表示できるようにローカル フォルダーにペイロード ファイルのルーティングにはだけです。  
  
3. **FILE トランスポートのプロパティ** ダイアログ ボックスの**先フォルダー**を参照して選択[!INCLUDE[btsBiztalkServerPath](../includes/btsbiztalkserverpath-md.md)]sdk \as2 Tutorial\\_EDIXMLToContoso します。 まま**ファイル名**として **%MessageID%.xml**します。 **[OK]** をクリックします。  
  
4. 既定の**PassThruTransmit**の**送信パイプライン**します。  
  
   > [!NOTE]
   >  PassThruTransmit 送信パイプラインを使用しているため、パイプラインは EDI ペイロード メッセージの処理は実行されませんが、AS2EdiReceive によって生成された XML 形式でローカル フォルダーに送信されます受信パイプライン。  
  
5. クリックして**フィルター**コンソール ツリーでします。 **プロパティ**、入力**BTS します。MessageType**します。 **演算子**、入力 **==** します。 **値**、入力`http://schemas.microsoft.com/BizTalk/Edi/X12/2006#X12_00401_864`します。  
  
   > [!NOTE]
   >  このフィルターにより、この送信ポートはのみ X12 864 ペイロード メッセージ、メッセージ ボックスから。  
  
6. **[OK]** をクリックします。  
  
7. **送信ポート**のウィンドウ、[!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)]管理コンソールを右クリックし、 **Send_Payload_EdiXml**送信ポート、およびクリックして**開始**。  
  
## <a name="next-steps"></a>次の手順  
 AS2 と X12 を作成する」の説明に従って、2 つの取引先アグリーメントがパートナー[手順 10。X12 および AS2 取引先アグリーメントを構成します。](../core/step-10-configure-the-x12-and-as2-trading-partner-agreement.md)  
  
## <a name="see-also"></a>参照  
 [チュートリアル 3: AS2 チュートリアル](../core/tutorial-3-as2-tutorial.md)