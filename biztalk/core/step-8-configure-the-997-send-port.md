---
title: '手順 8: 997 送信ポートの構成 |Microsoft Docs'
ms.custom: ''
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: ''
ms.suite: ''
ms.tgt_pltfrm: ''
ms.topic: article
ms.assetid: 4780c491-9f1a-4f13-b346-6a2e1801ec09
caps.latest.revision: 21
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: fd203912dbf77c3e677f8f1180ba312c02829699
ms.sourcegitcommit: 266308ec5c6a9d8d80ff298ee6051b4843c5d626
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 06/27/2018
ms.locfileid: "37022760"
---
# <a name="step-8-configure-the-997-send-port"></a>手順 8: 997 送信ポートを構成します。
![手順 8 11 の](../core/media/tut-step8-of-11.gif "Tut_Step8_of_11")  
  
 このステップでは、パートナーに 997 メッセージを送信するための送信ポートを設定します。 この送信ポートは、AS2EdiSend 送信パイプラインを使用して、EDIINT/AS2 でエンコードされた 997 受信確認を _997ToFabrikam フォルダに送信します。  
  
## <a name="prerequisites"></a>必須コンポーネント  
 [!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)] 管理者グループのメンバーとしてログオンしている必要があります。  
  
### <a name="to-create-the-sendasync997-send-port"></a>Send_Async_997 送信ポートを作成するには  
  
1. [!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)]管理コンソールで、[BizTalk アプリケーション 1] ノードを右クリックして**送信ポート**、] をポイント**新規**、] をクリックし、**静的な一方向送信ポート**.  
  
   > [!NOTE]
   >  AS2 メッセージ受信者としての Fabrikam パーティには MDN が設定されていないので、静的な一方向の送信ポートを使用します。  
  
2. **送信ポートのプロパティ** ダイアログ ボックスで、送信ポートの名前、 **Send_Async_997**します。 選択**HTTP**の**型**、 をクリックし、**構成**します。  
  
3. **HTTP トランスポートのプロパティ** ダイアログ ボックスの**送信先 URL**、入力`http://localhost/Fabrikam/Default.aspx?Destination=_997ToFabrikam`します。 クリア**チャンク エンコードを有効にする** をクリックし、 **OK**します。  
  
   > [!NOTE]
   >  **送信先 URL**設定により、送信ポートから Fabrikam 仮想ディレクトリに 997 メッセージを送信してされるようになります。 この仮想ディレクトリに関連付けられている Default.aspx.cs ファイルが、.msg 拡張子を使用して 997 を構築し、送信先のフォルダに送信します。  
  
4. **送信ポートのプロパティ**ダイアログ ボックスで、 **AS2EdiSend**の**送信パイプライン**します。  
  
5. クリックして**フィルター**コンソール ツリーでします。 **プロパティ**、 **BTS します。MessageType**します。 **演算子**、  **==** します。 **値**、入力`http://schemas.microsoft.com/Edi/X12#X12_997_Root`します。  
  
   > [!NOTE]
   >  このフィルタにより、送信ポートはメッセージ ボックスから 997 受信確認だけを取得するようになります。  
  
6. **[OK]** をクリックします。  
  
7. **送信ポート**のウィンドウ、[!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)]管理コンソールを右クリックし、 **Send_Async_997**送信ポート、およびクリックして**開始**。  
  
## <a name="next-steps"></a>次の手順  
 送信ポートを構成する (**Send_Payload_EdiXml**)」の説明に従って、EDI ペイロードを Contoso に送信する[手順 9: EDI ペイロード送信ポートの構成](../core/step-9-configure-the-edi-payload-send-port.md)します。  
  
## <a name="see-also"></a>参照  
 [BizTalk Server が AS2 メッセージを送信する方法](../core/how-biztalk-server-sends-as2-messages.md)   
 [AS2 経由でのメッセージの静的送信ポートの構成](../core/configuring-a-static-send-port-for-messages-over-as2.md)