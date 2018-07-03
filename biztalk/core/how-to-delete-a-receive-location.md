---
title: 削除する方法、受信場所 |Microsoft Docs
ms.custom: ''
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: ''
ms.suite: ''
ms.tgt_pltfrm: ''
ms.topic: article
helpviewer_keywords:
- managing [receive locations], deleting
- receive locations, deleting
- deleting, receive locations
ms.assetid: aa859355-af4c-48d9-b224-78fd3ef618fc
caps.latest.revision: 14
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: c3acc788e1c0bfeb9e722aee0b55d66e6f09d096
ms.sourcegitcommit: 266308ec5c6a9d8d80ff298ee6051b4843c5d626
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 06/27/2018
ms.locfileid: "36991443"
---
# <a name="how-to-delete-a-receive-location"></a>受信場所を削除する方法
このトピックでは、BizTalk Server 管理コンソールを使用して、受信場所を削除する方法について説明します。 削除した受信場所は、BizTalk 管理データベースから削除され、BizTalk Server 管理コンソールに表示されなくなります。  
  
 受信場所を削除する際には、次の重要事項を念頭に置いてください。  
  
-   受信場所を削除する前にする必要があります最初に無効にすること、」の説明に従って[受信場所を無効にする方法](../core/how-to-disable-a-receive-location.md)します。  
  
-   受信ポートのプライマリ受信場所を削除することはできません。 プライマリ受信場所を削除しようとすると、エラー メッセージが表示されます。 受信場所を削除するには、受信ポートを削除してそれに含まれるすべての受信場所を削除するか、または別の受信場所をプライマリに設定してから元の受信場所を削除します。 プライマリ受信場所の受信場所を作成する手順については、次を参照してください。[受信場所のプロパティを編集する方法](../core/how-to-edit-the-properties-of-a-receive-location.md)します。  
  
-   受信場所を削除した後、削除した受信場所に対応する分離ホストのワーカー プロセスを再起動します。  
  
## <a name="prerequisites"></a>前提条件  
 このトピックの手順を実行するには、BizTalk Server 管理者グループのメンバーであるアカウントでログオンする必要があります。 詳細なアクセス許可についてを参照してください。[を展開すると、BizTalk アプリケーションの管理に必要なアクセス許可](../core/permissions-required-for-deploying-and-managing-a-biztalk-application.md)します。  
  
### <a name="to-delete-a-receive-location"></a>受信場所を削除するには  
  
1. クリックして**開始**、 をクリックして**すべてのプログラム**、 をクリックして[!INCLUDE[btsBizTalkServerStartMenuItemui](../includes/btsbiztalkserverstartmenuitemui-md.md)]、順にクリックします**BizTalk Server 管理**します。  
  
2. コンソール ツリーで、BizTalk グループを展開し、受信場所を削除する BizTalk アプリケーションを展開します。  
  
3. をクリックして**受信場所**、削除、およびをクリックし、受信場所を右クリックして**削除**します。  
  
## <a name="see-also"></a>参照  
 [受信場所の管理](../core/managing-receive-locations.md)