---
title: オーケストレーションを開始する方法 |Microsoft ドキュメント
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
ms.openlocfilehash: e277c078a36129a125937114ee9287a1e97999b3
ms.sourcegitcommit: cb908c540d8f1a692d01dc8f313e16cb4b4e696d
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 09/20/2017
ms.locfileid: "22255426"
---
# <a name="how-to-start-an-orchestration"></a><span data-ttu-id="0a2eb-102">オーケストレーションを開始する方法</span><span class="sxs-lookup"><span data-stu-id="0a2eb-102">How to Start an Orchestration</span></span>
<span data-ttu-id="0a2eb-103">このトピックでは、BizTalk Server 管理コンソールを使用して、オーケストレーションを開始する方法について説明します。</span><span class="sxs-lookup"><span data-stu-id="0a2eb-103">This topic describes how to use the BizTalk Server Administration console to start an orchestration.</span></span> <span data-ttu-id="0a2eb-104">オーケストレーションを開始すると、受信メッセージの処理が開始されます。</span><span class="sxs-lookup"><span data-stu-id="0a2eb-104">When you start an orchestration, it begins processing incoming messages.</span></span>  
  
 <span data-ttu-id="0a2eb-105">オーケストレーションを開始する際には、次の重要事項を念頭に置いてください。</span><span class="sxs-lookup"><span data-stu-id="0a2eb-105">When starting and orchestration, bear in mind the following important points:</span></span>  
  
-   <span data-ttu-id="0a2eb-106">オーケストレーションは、開始する前に、関連付けられたすべての送信ポートおよび送信ポート グループと共に参加させる必要があります。</span><span class="sxs-lookup"><span data-stu-id="0a2eb-106">Before you can start the orchestration, it must be enlisted, along with all of the send ports and send port groups associated with it.</span></span> <span data-ttu-id="0a2eb-107">手順については、次を参照してください。[にオーケストレーションを参加させる方法](../core/how-to-enlist-an-orchestration.md)と[に送信ポートまたは送信ポート グループを参加させる方法](../core/how-to-enlist-a-send-port-or-send-port-group.md)です。</span><span class="sxs-lookup"><span data-stu-id="0a2eb-107">For instructions, see [How to Enlist an Orchestration](../core/how-to-enlist-an-orchestration.md) and [How to Enlist a Send Port or Send Port Group](../core/how-to-enlist-a-send-port-or-send-port-group.md).</span></span>  
  
-   <span data-ttu-id="0a2eb-108">オーケストレーションを開始しても、関連付けられた送信ポートは自動的に開始されません。</span><span class="sxs-lookup"><span data-stu-id="0a2eb-108">Starting an orchestration does not automatically start any associated send ports.</span></span> <span data-ttu-id="0a2eb-109">説明したように、個別に開始する必要があります[送信ポートまたは送信ポート グループを開始する方法](../core/how-to-start-a-send-port-or-send-port-group.md)です。</span><span class="sxs-lookup"><span data-stu-id="0a2eb-109">You must start them separately, as described in [How to Start a Send Port or Send Port Group](../core/how-to-start-a-send-port-or-send-port-group.md).</span></span>  
  
-   <span data-ttu-id="0a2eb-110">BizTalk Server について、この送信ポートに送信されたメッセージを配置または送信ポートが参加しているホストの保留キューにポート グループを送信または送信ポート グループで場合は、送信ポートの参加や送信ポート グループがこのオーケストレーションに関連付けられている開始しないでください、p です。</span><span class="sxs-lookup"><span data-stu-id="0a2eb-110">If you enlist the send ports and/or send port groups associated with this orchestration, but do not start them, BizTalk Server places any messages sent to this send port or send port group in the suspended queue of the host where you enlisted the send port or send port group.</span></span>  
  
> [!NOTE]
>  <span data-ttu-id="0a2eb-111">アプリケーション開発者は、このトピックの手順を使用して、開発プロセス中にその機能をテストするためのオーケストレーションを開始できます。</span><span class="sxs-lookup"><span data-stu-id="0a2eb-111">The application developer can start an orchestration to test its functionality during the development process by using the procedure in this topic.</span></span>  
  
## <a name="prerequisites"></a><span data-ttu-id="0a2eb-112">前提条件</span><span class="sxs-lookup"><span data-stu-id="0a2eb-112">Prerequisites</span></span>  
 <span data-ttu-id="0a2eb-113">このトピックの手順を実行するには、BizTalk Server Operators グループまたは BizTalk Server 管理者グループのメンバーとしてログオンする必要があります。</span><span class="sxs-lookup"><span data-stu-id="0a2eb-113">To perform the procedure in this topic, you must be logged on as a member of the BizTalk Server Operators group or the BizTalk Server Administrators group.</span></span> <span data-ttu-id="0a2eb-114">詳細なアクセス許可についてを参照してください。[を展開すると、BizTalk アプリケーションの管理に必要なアクセス許可](../core/permissions-required-for-deploying-and-managing-a-biztalk-application.md)です。</span><span class="sxs-lookup"><span data-stu-id="0a2eb-114">For more detailed information on permissions, see [Permissions Required for Deploying and Managing a BizTalk Application](../core/permissions-required-for-deploying-and-managing-a-biztalk-application.md).</span></span>  
  
### <a name="to-start-an-orchestration"></a><span data-ttu-id="0a2eb-115">オーケストレーションを開始するには</span><span class="sxs-lookup"><span data-stu-id="0a2eb-115">To start an orchestration</span></span>  
  
1.  <span data-ttu-id="0a2eb-116">をクリックして**開始**、 をクリックして**すべてのプログラム**、 をクリックして[!INCLUDE[btsBizTalkServerStartMenuItemui](../includes/btsbiztalkserverstartmenuitemui-md.md)]、順にクリック**BizTalk Server 管理コンソール**です。</span><span class="sxs-lookup"><span data-stu-id="0a2eb-116">Click **Start**, click **All Programs**, click [!INCLUDE[btsBizTalkServerStartMenuItemui](../includes/btsbiztalkserverstartmenuitemui-md.md)], and then click **BizTalk Server Administration**.</span></span>  
  
2.  <span data-ttu-id="0a2eb-117">コンソール ツリーで  [!INCLUDE[btsBizTalkServerAdminConsoleui](../includes/btsbiztalkserveradminconsoleui-md.md)]、BizTalk グループを展開し、**アプリケーション**、し、オーケストレーションを開始するを含むアプリケーションを展開します。</span><span class="sxs-lookup"><span data-stu-id="0a2eb-117">In the console tree, expand [!INCLUDE[btsBizTalkServerAdminConsoleui](../includes/btsbiztalkserveradminconsoleui-md.md)], expand the BizTalk group, expand **Applications**, and then expand the application containing the orchestration that you want to start.</span></span>  
  
3.  <span data-ttu-id="0a2eb-118">をクリックして**オーケストレーション**、オーケストレーションを右クリックし、クリックして**開始**です。</span><span class="sxs-lookup"><span data-stu-id="0a2eb-118">Click **Orchestrations**, right-click the orchestration, and then click **Start**.</span></span>  
  
    > [!IMPORTANT]
    >  <span data-ttu-id="0a2eb-119">オーケストレーションを開始する前に、関連付けられた送信ポートおよび送信ポート グループ参加させなかった場合、エラー メッセージが表示されます。</span><span class="sxs-lookup"><span data-stu-id="0a2eb-119">If you did not first enlist the associated send port and send port groups before starting the orchestration, you will see an error message.</span></span>  
  
    > [!NOTE]
    >  <span data-ttu-id="0a2eb-120">一度に複数のオーケストレーションを開始するに、shift キーを押しながらと各オーケストレーションを選択、オーケストレーションを右クリックし、をクリックして**開始**です。</span><span class="sxs-lookup"><span data-stu-id="0a2eb-120">To start multiple orchestrations at once, hold down the shift key and select each orchestration, right-click an orchestration, and then click **Start**.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="0a2eb-121">参照</span><span class="sxs-lookup"><span data-stu-id="0a2eb-121">See Also</span></span>  
 <span data-ttu-id="0a2eb-122">[オーケストレーションの管理](../core/managing-orchestrations.md) </span><span class="sxs-lookup"><span data-stu-id="0a2eb-122">[Managing Orchestrations](../core/managing-orchestrations.md) </span></span>  
 <span data-ttu-id="0a2eb-123">[オーケストレーションを停止する方法](../core/how-to-stop-an-orchestration.md) </span><span class="sxs-lookup"><span data-stu-id="0a2eb-123">[How to Stop an Orchestration](../core/how-to-stop-an-orchestration.md) </span></span>  
 [<span data-ttu-id="0a2eb-124">BizTalk アプリケーション開始および停止する方法</span><span class="sxs-lookup"><span data-stu-id="0a2eb-124">How to Start and Stop a BizTalk Application</span></span>](../core/how-to-start-and-stop-a-biztalk-application.md)