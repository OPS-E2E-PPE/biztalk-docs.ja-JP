---
title: オーケストレーションを開始する方法 |Microsoft Docs
ms.custom: ''
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: ''
ms.suite: ''
ms.tgt_pltfrm: ''
ms.topic: article
helpviewer_keywords:
- managing [orchestrations], starting
- starting, orchestrations
- orchestrations, starting
ms.assetid: 83411279-ee6f-4d68-aa3b-b5cd5e106088
caps.latest.revision: 19
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: d2593c68d642debcfcd8b49fa0ee67f806adc7c1
ms.sourcegitcommit: 266308ec5c6a9d8d80ff298ee6051b4843c5d626
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 06/27/2018
ms.locfileid: "36993059"
---
# <a name="how-to-start-an-orchestration"></a>オーケストレーションを開始する方法
このトピックでは、BizTalk Server 管理コンソールを使用して、オーケストレーションを開始する方法について説明します。 オーケストレーションを開始すると、受信メッセージの処理が開始されます。  
  
 オーケストレーションを開始する際には、次の重要事項を念頭に置いてください。  
  
-   オーケストレーションは、開始する前に、関連付けられたすべての送信ポートおよび送信ポート グループと共に参加させる必要があります。 手順については、次を参照してください。[オーケストレーションを参加させる方法](../core/how-to-enlist-an-orchestration.md)と[に送信ポートまたは送信ポート グループを参加させる方法](../core/how-to-enlist-a-send-port-or-send-port-group.md)します。  
  
-   オーケストレーションを開始しても、関連付けられた送信ポートは自動的に開始されません。 説明されているように、個別に開始する必要があります[送信ポートまたは送信ポート グループを開始する方法](../core/how-to-start-a-send-port-or-send-port-group.md)します。  
  
-   BizTalk Server について、この送信ポートに送信されたメッセージを配置または送信ポートを参加するホストの保留キューにポート グループを送信または送信ポート グループで送信ポート グループが、このオーケストレーションに関連付けられているや起動しないが、送信ポートを参加させる、p。  
  
> [!NOTE]
>  アプリケーション開発者は、このトピックの手順を使用して、開発プロセス中にその機能をテストするためのオーケストレーションを開始できます。  
  
## <a name="prerequisites"></a>前提条件  
 このトピックの手順を実行するには、BizTalk Server Operators グループまたは BizTalk Server 管理者グループのメンバーとしてログオンする必要があります。 詳細なアクセス許可についてを参照してください。[を展開すると、BizTalk アプリケーションの管理に必要なアクセス許可](../core/permissions-required-for-deploying-and-managing-a-biztalk-application.md)します。  
  
### <a name="to-start-an-orchestration"></a>オーケストレーションを開始するには  
  
1. クリックして**開始**、 をクリックして**すべてのプログラム**、 をクリックして[!INCLUDE[btsBizTalkServerStartMenuItemui](../includes/btsbiztalkserverstartmenuitemui-md.md)]、順にクリックします**BizTalk Server 管理**します。  
  
2. コンソール ツリーで、展開[!INCLUDE[btsBizTalkServerAdminConsoleui](../includes/btsbiztalkserveradminconsoleui-md.md)]展開し、BizTalk グループを展開し、**アプリケーション**、し、開始するオーケストレーションを含むアプリケーションを展開します。  
  
3. クリックして**オーケストレーション**、オーケストレーションを右クリックし、クリックして**開始**します。  
  
   > [!IMPORTANT]
   >  オーケストレーションを開始する前に、関連付けられた送信ポートおよび送信ポート グループ参加させなかった場合、エラー メッセージが表示されます。  
  
   > [!NOTE]
   >  一度に複数のオーケストレーションを開始するに、shift キーを押しながらと各オーケストレーションを選択、オーケストレーションを右クリックし、順にクリックします**開始**します。  
  
## <a name="see-also"></a>参照  
 [オーケストレーションの管理](../core/managing-orchestrations.md)   
 [オーケストレーションを停止する方法](../core/how-to-stop-an-orchestration.md)   
 [BizTalk アプリケーション開始および停止する方法](../core/how-to-start-and-stop-a-biztalk-application.md)