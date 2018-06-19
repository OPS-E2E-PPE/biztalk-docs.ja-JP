---
title: '手順 8: 997 送信ポートの構成 |Microsoft ドキュメント'
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
ms.openlocfilehash: ec3c022ec1236d760c69250a2faecc7cacdb543c
ms.sourcegitcommit: cb908c540d8f1a692d01dc8f313e16cb4b4e696d
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 09/20/2017
ms.locfileid: "22277218"
---
# <a name="step-8-configure-the-997-send-port"></a>手順 8: 997 送信ポートを構成します。
![手順 11 の 8](../core/media/tut-step8-of-11.gif "Tut_Step8_of_11")  
  
 このステップでは、パートナーに 997 メッセージを送信するための送信ポートを設定します。 この送信ポートは、AS2EdiSend 送信パイプラインを使用して、EDIINT/AS2 でエンコードされた 997 受信確認を _997ToFabrikam フォルダに送信します。  
  
## <a name="prerequisites"></a>前提条件  
 [!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)] 管理者グループのメンバーとしてログオンしている必要があります。  
  
### <a name="to-create-the-sendasync997-send-port"></a>Send_Async_997 送信ポートを作成するには  
  
1.  [!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)]管理コンソールで、[BizTalk アプリケーション 1] ノードを右クリックして**送信ポート**、指す**新規**、順にクリック**静的な一方向送信ポート**.  
  
    > [!NOTE]
    >  AS2 メッセージ受信者としての Fabrikam パーティには MDN が設定されていないので、静的な一方向の送信ポートを使用します。  
  
2.  **送信ポートのプロパティ** ダイアログ ボックスに、名前、送信ポートに**Send_Async_997**です。 選択**HTTP**の**型**、クリックして**構成**です。  
  
3.  **HTTP トランスポートのプロパティ** ダイアログ ボックスの**送信先 URL**、入力`http://localhost/Fabrikam/Default.aspx?Destination=_997ToFabrikam`です。 クリア**有効チャンク エンコード** をクリックし、 **OK**です。  
  
    > [!NOTE]
    >  **送信先 URL**設定、送信ポートから Fabrikam 仮想ディレクトリに 997 メッセージを送信してされるようになります。 この仮想ディレクトリに関連付けられている Default.aspx.cs ファイルが、.msg 拡張子を使用して 997 を構築し、送信先のフォルダに送信します。  
  
4.  **送信ポートのプロパティ**ダイアログ ボックスで、 **AS2EdiSend**の**送信パイプライン**です。  
  
5.  をクリックして**フィルター**コンソール ツリーでします。 **プロパティ** **BTS です。MessageType**です。 **演算子**  **==** です。 **値**、入力`http://schemas.microsoft.com/Edi/X12#X12_997_Root`です。  
  
    > [!NOTE]
    >  このフィルタにより、送信ポートはメッセージ ボックスから 997 受信確認だけを取得するようになります。  
  
6.  **[OK]** をクリックします。  
  
7.  **送信ポート**のペイン、[!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)]管理コンソールを右クリックし、 **Send_Async_997**送信ポートをクリックして**開始**です。  
  
## <a name="next-steps"></a>次の手順  
 送信ポートを構成する (**Send_Payload_EdiXml**)」の説明に従って、EDI ペイロードを Contoso に送信する[手順 9: EDI ペイロードの送信ポートを構成する](../core/step-9-configure-the-edi-payload-send-port.md)です。  
  
## <a name="see-also"></a>参照  
 [BizTalk Server が AS2 メッセージを送信する方法](../core/how-biztalk-server-sends-as2-messages.md)   
 [AS2 経由でメッセージの静的送信ポートを構成します。](../core/configuring-a-static-send-port-for-messages-over-as2.md)