---
title: "証明書を削除する方法、受信場所 |Microsoft ドキュメント"
ms.custom: 
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: 
ms.suite: 
ms.tgt_pltfrm: 
ms.topic: article
helpviewer_keywords:
- certificates, receive locations
- receive locations, certificates
- managing [receive locations], certificates
ms.assetid: 717d41bf-4260-4df4-9d0a-07243bb9b12c
caps.latest.revision: "9"
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: e70cd846c364d52544bf8504d42132dd35fe65d7
ms.sourcegitcommit: cb908c540d8f1a692d01dc8f313e16cb4b4e696d
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 09/20/2017
---
# <a name="how-to-remove-a-certificate-from-a-receive-location"></a>受信場所から証明書を削除する方法
このトピックでは、BizTalk Server 管理コンソールを使用して、受信場所からセキュリティ証明書を削除する方法について説明します。 この操作を実行すると、受信場所ではメッセージが暗号化されなくなり、メッセージはクリア テキストで送信されるようになります。 証明書を受信場所から削除しても、証明書ストアからは削除されません。  
  
## <a name="prerequisites"></a>前提条件  
 このトピックの手順を実行するには、BizTalk Server 管理者グループのメンバーであるアカウントを使用してログオンする必要があります。 詳細なアクセス許可についてを参照してください。[を展開すると、BizTalk アプリケーションの管理に必要なアクセス許可](../core/permissions-required-for-deploying-and-managing-a-biztalk-application.md)です。  
  
### <a name="to-remove-a-certificate-from-a-receive-location"></a>受信場所から証明書を削除するには  
  
1.  をクリックして**開始**、 をクリックして**すべてのプログラム**、 をクリックして[!INCLUDE[btsBizTalkServerStartMenuItemui](../includes/btsbiztalkserverstartmenuitemui-md.md)]、順にクリック**BizTalk Server 管理コンソール**です。  
  
2.  コンソール ツリーで、BizTalk グループを展開し、受信場所から証明書を削除する BizTalk アプリケーションを展開します。  
  
3.  展開**受信場所**、受信場所を右クリックし、をクリックして**プロパティ**、クリックして**証明書**です。  
  
4.  をクリックして**削除証明書**、クリックして**[ok]**です。  
  
## <a name="see-also"></a>参照  
 [受信場所の管理](../core/managing-receive-locations.md)