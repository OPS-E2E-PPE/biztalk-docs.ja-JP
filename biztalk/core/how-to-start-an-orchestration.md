---
title: "オーケストレーションを開始する方法 |Microsoft ドキュメント"
ms.custom: 
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: 
ms.suite: 
ms.tgt_pltfrm: 
ms.topic: article
helpviewer_keywords:
- managing [orchestrations], starting
- starting, orchestrations
- orchestrations, starting
ms.assetid: 83411279-ee6f-4d68-aa3b-b5cd5e106088
caps.latest.revision: "19"
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: e277c078a36129a125937114ee9287a1e97999b3
ms.sourcegitcommit: cb908c540d8f1a692d01dc8f313e16cb4b4e696d
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 09/20/2017
---
# <a name="how-to-start-an-orchestration"></a>オーケストレーションを開始する方法
このトピックでは、BizTalk Server 管理コンソールを使用して、オーケストレーションを開始する方法について説明します。 オーケストレーションを開始すると、受信メッセージの処理が開始されます。  
  
 オーケストレーションを開始する際には、次の重要事項を念頭に置いてください。  
  
-   オーケストレーションは、開始する前に、関連付けられたすべての送信ポートおよび送信ポート グループと共に参加させる必要があります。 手順については、次を参照してください。[にオーケストレーションを参加させる方法](../core/how-to-enlist-an-orchestration.md)と[に送信ポートまたは送信ポート グループを参加させる方法](../core/how-to-enlist-a-send-port-or-send-port-group.md)です。  
  
-   オーケストレーションを開始しても、関連付けられた送信ポートは自動的に開始されません。 説明したように、個別に開始する必要があります[送信ポートまたは送信ポート グループを開始する方法](../core/how-to-start-a-send-port-or-send-port-group.md)です。  
  
-   BizTalk Server について、この送信ポートに送信されたメッセージを配置または送信ポートが参加しているホストの保留キューにポート グループを送信または送信ポート グループで場合は、送信ポートの参加や送信ポート グループがこのオーケストレーションに関連付けられている開始しないでください、p です。  
  
> [!NOTE]
>  アプリケーション開発者は、このトピックの手順を使用して、開発プロセス中にその機能をテストするためのオーケストレーションを開始できます。  
  
## <a name="prerequisites"></a>前提条件  
 このトピックの手順を実行するには、BizTalk Server Operators グループまたは BizTalk Server 管理者グループのメンバーとしてログオンする必要があります。 詳細なアクセス許可についてを参照してください。[を展開すると、BizTalk アプリケーションの管理に必要なアクセス許可](../core/permissions-required-for-deploying-and-managing-a-biztalk-application.md)です。  
  
### <a name="to-start-an-orchestration"></a>オーケストレーションを開始するには  
  
1.  をクリックして**開始**、 をクリックして**すべてのプログラム**、 をクリックして[!INCLUDE[btsBizTalkServerStartMenuItemui](../includes/btsbiztalkserverstartmenuitemui-md.md)]、順にクリック**BizTalk Server 管理コンソール**です。  
  
2.  コンソール ツリーで  [!INCLUDE[btsBizTalkServerAdminConsoleui](../includes/btsbiztalkserveradminconsoleui-md.md)]、BizTalk グループを展開し、**アプリケーション**、し、オーケストレーションを開始するを含むアプリケーションを展開します。  
  
3.  をクリックして**オーケストレーション**、オーケストレーションを右クリックし、クリックして**開始**です。  
  
    > [!IMPORTANT]
    >  オーケストレーションを開始する前に、関連付けられた送信ポートおよび送信ポート グループ参加させなかった場合、エラー メッセージが表示されます。  
  
    > [!NOTE]
    >  一度に複数のオーケストレーションを開始するに、shift キーを押しながらと各オーケストレーションを選択、オーケストレーションを右クリックし、をクリックして**開始**です。  
  
## <a name="see-also"></a>参照  
 [オーケストレーションの管理](../core/managing-orchestrations.md)   
 [オーケストレーションを停止する方法](../core/how-to-stop-an-orchestration.md)   
 [BizTalk アプリケーション開始および停止する方法](../core/how-to-start-and-stop-a-biztalk-application.md)