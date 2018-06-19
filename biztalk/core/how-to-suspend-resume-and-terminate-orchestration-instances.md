---
title: 中断、再開、およびオーケストレーションのインスタンスを終了する方法 |Microsoft ドキュメント
ms.custom: ''
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: ''
ms.suite: ''
ms.tgt_pltfrm: ''
ms.topic: article
helpviewer_keywords:
- managing [orchestrations], resuming
- orchestrations, terminating
- managing [orchestrations], suspending
- orchestrations, resuming
- orchestrations, suspending
- managing [orchestrations], terminating
ms.assetid: 7b373dad-57d5-4696-9b29-a6c351d44fa8
caps.latest.revision: 17
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: 9528ac0e810a3d4e203733ab1cc5b041d3d61d31
ms.sourcegitcommit: cb908c540d8f1a692d01dc8f313e16cb4b4e696d
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 09/20/2017
ms.locfileid: "22256770"
---
# <a name="how-to-suspend-resume-and-terminate-orchestration-instances"></a><span data-ttu-id="54569-102">オーケストレーション インスタンスを中断、再開、および終了する方法</span><span class="sxs-lookup"><span data-stu-id="54569-102">How to Suspend, Resume, and Terminate Orchestration Instances</span></span>
<span data-ttu-id="54569-103">このトピックでは、BizTalk Server 管理コンソールを使用して、実行中の 1 つ以上のオーケストレーションのサービス インスタンスを中断、再開、および終了する方法について説明します。</span><span class="sxs-lookup"><span data-stu-id="54569-103">This topic describes how to suspend, resume, and terminate one or more running service instances of an orchestration by using the BizTalk Server Administration console.</span></span> <span data-ttu-id="54569-104">サービスのインスタンスとは、後続の処理や追跡を目的に BizTalk Server が処理しているオーケストレーションのインスタンス、または、メッセージ ボックスにシリアル化されたオーケストレーションのインスタンスを指します。</span><span class="sxs-lookup"><span data-stu-id="54569-104">A service instance is an instance of an orchestration that BizTalk Server is either processing or that has been serialized into the MessageBox for further processing or tracking.</span></span>  
  
 <span data-ttu-id="54569-105">以下に、これら 3 つの操作の効果について説明します。</span><span class="sxs-lookup"><span data-stu-id="54569-105">The following describes the effects of these three operations:</span></span>  
  
-   <span data-ttu-id="54569-106">**中断します。**</span><span class="sxs-lookup"><span data-stu-id="54569-106">**Suspend.**</span></span> <span data-ttu-id="54569-107">サービス インスタンスを一時停止します。</span><span class="sxs-lookup"><span data-stu-id="54569-107">This pauses the service instance.</span></span> <span data-ttu-id="54569-108">インプロセス メッセージは最後まで実行されます。</span><span class="sxs-lookup"><span data-stu-id="54569-108">In-process messages run to completion.</span></span> <span data-ttu-id="54569-109">メッセージは依然として回送されますが、処理されません。</span><span class="sxs-lookup"><span data-stu-id="54569-109">Messages are still routed to service instances, but are not processed.</span></span>  
  
-   <span data-ttu-id="54569-110">**再開します。**</span><span class="sxs-lookup"><span data-stu-id="54569-110">**Resume.**</span></span> <span data-ttu-id="54569-111">中断したインスタンスの処理を再開します。</span><span class="sxs-lookup"><span data-stu-id="54569-111">This resumes processing of suspended instances.</span></span>  
  
> [!NOTE]
>  <span data-ttu-id="54569-112">ブレークポイント状態のインスタンスは再開できません。</span><span class="sxs-lookup"><span data-stu-id="54569-112">You cannot resume an instance from a breakpoint state.</span></span> <span data-ttu-id="54569-113">このようなインスタンスを再開すると、"保留中" という状態が表示されることがあります。ただし、このインスタンスは最終的に失敗します。</span><span class="sxs-lookup"><span data-stu-id="54569-113">Resuming such an instance may show a status of "Pending," but the instance will eventually fail.</span></span>  
  
-   <span data-ttu-id="54569-114">**終了します。**</span><span class="sxs-lookup"><span data-stu-id="54569-114">**Terminate.**</span></span> <span data-ttu-id="54569-115">メッセージ処理をすべて終了します。</span><span class="sxs-lookup"><span data-stu-id="54569-115">This terminates all message processing.</span></span> <span data-ttu-id="54569-116">サービス インスタンスは、BizTalk Server データベースから削除されます。</span><span class="sxs-lookup"><span data-stu-id="54569-116">The service instance is deleted from the BizTalk Server databases.</span></span> <span data-ttu-id="54569-117">サービス インスタンスが処理しているメッセージも削除されます。ただし、終了しないサービス インスタンスによって参照されているメッセージは削除されません。</span><span class="sxs-lookup"><span data-stu-id="54569-117">Messages that the service instance is processing are also deleted, except for any messages that are also referenced by a service instance that is not being terminated.</span></span>  
  
## <a name="prerequisites"></a><span data-ttu-id="54569-118">前提条件</span><span class="sxs-lookup"><span data-stu-id="54569-118">Prerequisites</span></span>  
 <span data-ttu-id="54569-119">このトピックの手順を実行するには、BizTalk Server Operators グループまたは BizTalk Server 管理者グループのメンバーとしてログオンする必要があります。</span><span class="sxs-lookup"><span data-stu-id="54569-119">To perform the procedure in this topic, you must be logged on as a member of the BizTalk Server Operators group or the BizTalk Server Administrators group.</span></span> <span data-ttu-id="54569-120">詳細なアクセス許可についてを参照してください。[を展開すると、BizTalk アプリケーションの管理に必要なアクセス許可](../core/permissions-required-for-deploying-and-managing-a-biztalk-application.md)です。</span><span class="sxs-lookup"><span data-stu-id="54569-120">For more detailed information on permissions, see [Permissions Required for Deploying and Managing a BizTalk Application](../core/permissions-required-for-deploying-and-managing-a-biztalk-application.md).</span></span>  
  
### <a name="to-view-start-stop-or-terminate-an-instance-of-an-orchestration"></a><span data-ttu-id="54569-121">オーケストレーションのインスタンスを開始、停止、または終了するには</span><span class="sxs-lookup"><span data-stu-id="54569-121">To view start, stop, or terminate an instance of an orchestration</span></span>  
  
1.  <span data-ttu-id="54569-122">をクリックして**開始**、 をクリックして**すべてのプログラム**、 をクリックして[!INCLUDE[btsBizTalkServerStartMenuItemui](../includes/btsbiztalkserverstartmenuitemui-md.md)]、順にクリック**BizTalk Server 管理コンソール**です。</span><span class="sxs-lookup"><span data-stu-id="54569-122">Click **Start**, click **All Programs**, click [!INCLUDE[btsBizTalkServerStartMenuItemui](../includes/btsbiztalkserverstartmenuitemui-md.md)], and then click **BizTalk Server Administration**.</span></span>  
  
2.  <span data-ttu-id="54569-123">[グループ ハブ] ページを表示する BizTalk グループを選択します。</span><span class="sxs-lookup"><span data-stu-id="54569-123">Select the BizTalk Group to display the Group Hub page.</span></span>  
  
3.  <span data-ttu-id="54569-124">**進行中の作業**をクリックして**サービス インスタンスを実行している**です。</span><span class="sxs-lookup"><span data-stu-id="54569-124">Under **Work in Progress**, click **Running service instances**.</span></span>  
  
     <span data-ttu-id="54569-125">ページ下部のクエリ結果パネルに、オーケストレーションのすべてのインスタンスが表示されます。</span><span class="sxs-lookup"><span data-stu-id="54569-125">The query results panel in the lower section of the page displays all instances of the orchestration.</span></span>  
  
4.  <span data-ttu-id="54569-126">オーケストレーションの別のインスタンスを表示して、クエリを絞り込んでするには、下にあるボックスをクリックして**値**の**Search For**フィールドで、表示、およびをクリックするインスタンスの種類を選択**クエリの実行**.</span><span class="sxs-lookup"><span data-stu-id="54569-126">To refine the query and view different instances for the orchestration, click the box under **Value** for the **Search For** field, select the instance type to view, and then click **Run Query**.</span></span> <span data-ttu-id="54569-127">クエリの作成の詳細については、「関連項目」で検索に関するトピックを選んで参照してください。</span><span class="sxs-lookup"><span data-stu-id="54569-127">For more information about creating queries, see the topics on searching under See Also.</span></span>  
  
5.  <span data-ttu-id="54569-128">をクリックして、インスタンスを右クリックして**Suspend**、**再開**、または**Terminate**です。</span><span class="sxs-lookup"><span data-stu-id="54569-128">Right-click the instance you want and click **Suspend**, **Resume**, or **Terminate**.</span></span> <span data-ttu-id="54569-129">この機能を使用すると、再開するインスタンスを選択できます。</span><span class="sxs-lookup"><span data-stu-id="54569-129">This functionality allows you to select which instances to resume.</span></span>  
  
    > [!NOTE]
    >  <span data-ttu-id="54569-130">複数のインスタンスに対して操作を実行するには、CTRL キーを押しながら目的のインスタンスをクリックします。</span><span class="sxs-lookup"><span data-stu-id="54569-130">To perform the operation on multiple instances, hold down the CTRL key and click the instances you want.</span></span> <span data-ttu-id="54569-131">インスタンスを右クリックし、をクリックし、 **Suspend**、**再開**、または**Terminate**です。</span><span class="sxs-lookup"><span data-stu-id="54569-131">Then right-click an instance and click **Suspend**, **Resume**, or **Terminate**.</span></span>  
  
     <span data-ttu-id="54569-132">[サービス インスタンスの状態](../core/service-instance-states.md)中断状態について詳しく説明します。</span><span class="sxs-lookup"><span data-stu-id="54569-132">[Service Instance States](../core/service-instance-states.md) provides more information on the suspended state.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="54569-133">参照</span><span class="sxs-lookup"><span data-stu-id="54569-133">See Also</span></span>  
 <span data-ttu-id="54569-134">[オーケストレーションの管理](../core/managing-orchestrations.md) </span><span class="sxs-lookup"><span data-stu-id="54569-134">[Managing Orchestrations](../core/managing-orchestrations.md) </span></span>  
 <span data-ttu-id="54569-135">[実行中のサービス インスタンスを検索する方法](../core/how-to-search-for-running-service-instances.md) </span><span class="sxs-lookup"><span data-stu-id="54569-135">[How to Search for Running Service Instances](../core/how-to-search-for-running-service-instances.md) </span></span>  
 [<span data-ttu-id="54569-136">中断されたサービス インスタンスを検索する方法</span><span class="sxs-lookup"><span data-stu-id="54569-136">How to Search for Suspended Service Instances</span></span>](../core/how-to-search-for-suspended-service-instances.md)