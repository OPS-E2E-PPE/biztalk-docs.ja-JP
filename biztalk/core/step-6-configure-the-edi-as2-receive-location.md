---
title: '手順 6: EDI、AS2 を構成する受信場所 |Microsoft ドキュメント'
ms.custom: ''
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: ''
ms.suite: ''
ms.tgt_pltfrm: ''
ms.topic: article
ms.assetid: 167f8ba2-d38b-4088-863b-2bd90c2a12a2
caps.latest.revision: 27
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: 4bbf1fce88301960a28c19fa20c9996282ce4619
ms.sourcegitcommit: cb908c540d8f1a692d01dc8f313e16cb4b4e696d
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 09/20/2017
ms.locfileid: "22276258"
---
# <a name="step-6-configure-the-edi-as2-receive-location"></a>手順 6: EDI、AS2 を構成する受信場所
![手順 11 の 6](../core/media/tut-step6-of-11.gif "Tut_Step6_of_11")  
  
 このステップでは、Fabrikam パーティからの EDI メッセージを受信する一方向の受信場所を設定します。 この受信場所では、AS2EdiReceive 受信パイプラインを使用して、送信されてくる EDI および AS2 メッセージを処理します。 このメッセージは、sender.exe アプリケーションにより、Contoso 仮想ディレクトリを通じ、BTSHTTPReceive.dll ISAPI 拡張を使用して受信場所に送信されます。  
  
 このチュートリアルでは、MDN 応答を非同期で送信する動的送信ポートを設定します。 このシナリオで必要となるのは、一方向の受信ポートだけです。 しかし、同期 MDN を指定する AS2 メッセージを送信するよう Sender.exe を変更することもできます。 この場合、MDN を返信するため、双方向の要求応答受信ポートを作成する必要があります。 詳細についてを参照してください「ソリューションをテストする、」の[チュートリアル (AS2): 同期 MDN による AS2 経由での EDI の受信](../core/walkthrough-as2-receiving-edi-over-as2-with-a-synchronous-mdn.md)です。  
  
## <a name="prerequisites"></a>前提条件  
 [!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)] 管理者グループのメンバーとしてログオンしている必要があります。  
  
### <a name="to-create-the-biztalk-http-receive-location"></a>BizTalk HTTP 受信場所を作成するには  
  
1.  [!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)]管理コンソールで、[BizTalk アプリケーション 1] ノードを右クリックして**受信ポート**、指す**新規**、順にクリック**一方向の受信ポート**.  
  
2.  受信ポートに名前を付けます**Receive_AS2**です。  
  
3.  をクリックして**受信場所**をクリックしてコンソール ツリーで、**新規**です。  
  
4.  **受信場所のプロパティ**ダイアログ ボックスで、名前、受信場所**Receive_AS2** **HTTP**の**型**、し、をクリックして**構成**です。  
  
5.  **HTTP トランスポートのプロパティ** ダイアログ ボックスで、入力 **/Contoso/BTSHTTPReceive.dll**の**仮想ディレクトリと ISAPI 拡張**です。 クリア**成功した場合の戻り値の関連付けハンドル**選択**失敗した要求を中断**です。 **[OK]** をクリックします。  
  
6.  選択**AS2EdiReceive**の**受信パイプライン**です。 をクリックして **[ok]**、順にクリック**OK**もう一度です。  
  
    > [!NOTE]
    >  AS2EdiReceive 受信パイプラインは、AS2 のデコードと EDI の逆アセンブルを実行します。  
  
7.  [!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)]管理コンソールで、をクリックして**受信場所**[BizTalk アプリケーション 1] ノードを右クリックし**Receive_AS2**、クリックして**を有効にする**.  
  
## <a name="next-steps"></a>次の手順  
 送信ポートを構成する (**Send_Asynch_MDN**) 送信する送信ポート、非同期 MDN を Fabrikam に」の説明に従って[手順 7: MDN の送信ポート構成](../core/step-7-configure-the-mdn-send-port.md)です。  
  
## <a name="see-also"></a>参照  
 [BizTalk Server が AS2 メッセージを受信する方法](../core/how-biztalk-server-receives-as2-messages.md)   
 [構成、AS2 経由でメッセージの受信ポート](../core/configuring-a-receive-port-for-messages-over-as2.md)