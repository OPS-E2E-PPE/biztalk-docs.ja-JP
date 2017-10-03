---
title: "削除する方法、受信場所 |Microsoft ドキュメント"
ms.custom: 
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: 
ms.suite: 
ms.tgt_pltfrm: 
ms.topic: article
helpviewer_keywords:
- managing [receive locations], deleting
- receive locations, deleting
- deleting, receive locations
ms.assetid: aa859355-af4c-48d9-b224-78fd3ef618fc
caps.latest.revision: "14"
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: 19828b7b456e872af78c2bae3c89ed75828a32ba
ms.sourcegitcommit: cb908c540d8f1a692d01dc8f313e16cb4b4e696d
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 09/20/2017
---
# <a name="how-to-delete-a-receive-location"></a>受信場所を削除する方法
このトピックでは、BizTalk Server 管理コンソールを使用して、受信場所を削除する方法について説明します。 削除した受信場所は、BizTalk 管理データベースから削除され、BizTalk Server 管理コンソールに表示されなくなります。  
  
 受信場所を削除する際には、次の重要事項を念頭に置いてください。  
  
-   受信場所を削除することができます、前に、必要があります最初に無効にする」の説明に従って[受信場所を無効にする方法](../core/how-to-disable-a-receive-location.md)です。  
  
-   受信ポートのプライマリ受信場所を削除することはできません。 プライマリ受信場所を削除しようとすると、エラー メッセージが表示されます。 受信場所を削除するには、受信ポートを削除してそれに含まれるすべての受信場所を削除するか、または別の受信場所をプライマリに設定してから元の受信場所を削除します。 プライマリ受信場所の受信場所を作成する方法については、次を参照してください。[受信場所のプロパティを編集する方法](../core/how-to-edit-the-properties-of-a-receive-location.md)です。  
  
-   受信場所を削除した後、削除した受信場所に対応する分離ホストのワーカー プロセスを再起動します。  
  
## <a name="prerequisites"></a>前提条件  
 このトピックの手順を実行するには、BizTalk Server 管理者グループのメンバーであるアカウントを使用してログオンする必要があります。 詳細なアクセス許可についてを参照してください。[を展開すると、BizTalk アプリケーションの管理に必要なアクセス許可](../core/permissions-required-for-deploying-and-managing-a-biztalk-application.md)です。  
  
### <a name="to-delete-a-receive-location"></a>受信場所を削除するには  
  
1.  をクリックして**開始**、 をクリックして**すべてのプログラム**、 をクリックして[!INCLUDE[btsBizTalkServerStartMenuItemui](../includes/btsbiztalkserverstartmenuitemui-md.md)]、順にクリック**BizTalk Server 管理コンソール**です。  
  
2.  コンソール ツリーで、BizTalk グループを展開し、受信場所を削除する BizTalk アプリケーションを展開します。  
  
3.  をクリックして**受信場所**、削除、およびをクリックし、受信場所を右クリックして**削除**です。  
  
## <a name="see-also"></a>参照  
 [受信場所の管理](../core/managing-receive-locations.md)