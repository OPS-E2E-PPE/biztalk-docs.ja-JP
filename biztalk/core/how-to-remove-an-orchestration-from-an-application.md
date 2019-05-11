---
title: オーケストレーションをアプリケーションから削除する方法 |Microsoft Docs
ms.custom: ''
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: ''
ms.suite: ''
ms.tgt_pltfrm: ''
ms.topic: article
helpviewer_keywords:
- applications, orchestrations
- deleting, orchestrations
- managing [orchestrations], deleting
- orchestrations, applications
- orchestrations, deleting
ms.assetid: e6d635ea-3513-42de-a667-b56c536e5328
caps.latest.revision: 12
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: 0a3dbca1d838ca2691dcbfd1174debe49cbf0362
ms.sourcegitcommit: 381e83d43796a345488d54b3f7413e11d56ad7be
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 05/07/2019
ms.locfileid: "65335033"
---
# <a name="how-to-remove-an-orchestration-from-an-application"></a><span data-ttu-id="fc360-102">オーケストレーションをアプリケーションから削除する方法</span><span class="sxs-lookup"><span data-stu-id="fc360-102">How to Remove an Orchestration from an Application</span></span>
<span data-ttu-id="fc360-103">ここでは、BizTalk Server 管理コンソールまたはコマンド ラインを使用して、オーケストレーションを BizTalk アプリケーションから削除する方法について説明します。</span><span class="sxs-lookup"><span data-stu-id="fc360-103">This topic describes how to use the BizTalk Server Administration console or the command line to remove an orchestration from a BizTalk application.</span></span> <span data-ttu-id="fc360-104">オーケストレーションをアプリケーションから削除すると、BizTalk グループの BizTalk 管理データベースからも削除されます。</span><span class="sxs-lookup"><span data-stu-id="fc360-104">Removing an orchestration from an application also deletes it from the BizTalk Management database for the BizTalk group.</span></span>  
  
 <span data-ttu-id="fc360-105">オーケストレーションを削除すると、次の処理が行われます。</span><span class="sxs-lookup"><span data-stu-id="fc360-105">When you remove an orchestration, the following occurs:</span></span>  
  
- <span data-ttu-id="fc360-106">オーケストレーションが BizTalk 管理データベースから削除されます。</span><span class="sxs-lookup"><span data-stu-id="fc360-106">The orchestration is deleted from the BizTalk Management database.</span></span>  
  
- <span data-ttu-id="fc360-107">オーケストレーションを含む BizTalk アセンブリも BizTalk 管理データベースから削除されますが、ローカル ファイル システムまたはグローバル アセンブリ キャッシュ (GAC) 内に存在する場合、そのアセンブリは削除されません。</span><span class="sxs-lookup"><span data-stu-id="fc360-107">The BizTalk assembly that contains the orchestration is deleted from the BizTalk Management database, but is not removed from the local file system or the global assembly cache (GAC), if it exists in these locations.</span></span>  
  
- <span data-ttu-id="fc360-108">BizTalk アセンブリが削除されるため、アセンブリに含まれるすべての成果物は、BizTalk 管理データベースから削除されます。</span><span class="sxs-lookup"><span data-stu-id="fc360-108">As a consequence of the BizTalk assembly being deleted, all artifacts contained in the assembly are deleted from the BizTalk Management database as well.</span></span>  
  
  <span data-ttu-id="fc360-109">オーケストレーションをアプリケーションから削除する前に、次の重要事項を考慮します。</span><span class="sxs-lookup"><span data-stu-id="fc360-109">Before removing an orchestration from an application, bear in mind the following important points:</span></span>  
  
- <span data-ttu-id="fc360-110">他のアイテムがこのオーケストレーションに依存関係を持っている場合、または削除されるアセンブリに含まれるアイテムに依存関係を持っている場合は、オーケストレーションを削除するとアイテムが適切に動作しなくなります。</span><span class="sxs-lookup"><span data-stu-id="fc360-110">If other artifacts have dependencies on this orchestration or the artifacts contained in the assembly that will also be removed, they will no longer function correctly when you remove the orchestration.</span></span> <span data-ttu-id="fc360-111">依存関係に関する背景情報は、次を参照してください。[依存関係とアプリケーションの展開](../core/dependencies-and-application-deployment.md)します。</span><span class="sxs-lookup"><span data-stu-id="fc360-111">For background information about dependencies, see [Dependencies and Application Deployment](../core/dependencies-and-application-deployment.md).</span></span>  
  
- <span data-ttu-id="fc360-112">実行中のインスタンスを含むオーケストレーションは削除できません。</span><span class="sxs-lookup"><span data-stu-id="fc360-112">You cannot remove an orchestration that has running instances.</span></span> <span data-ttu-id="fc360-113">実行中のインスタンスはすべて終了する必要があります。</span><span class="sxs-lookup"><span data-stu-id="fc360-113">You must terminate any running instances.</span></span>  
  
## <a name="prerequisites"></a><span data-ttu-id="fc360-114">前提条件</span><span class="sxs-lookup"><span data-stu-id="fc360-114">Prerequisites</span></span>  
 <span data-ttu-id="fc360-115">このトピックの手順を実行するには、BizTalk Server 管理者グループのメンバーであるアカウントでログオンする必要があります。</span><span class="sxs-lookup"><span data-stu-id="fc360-115">To perform the procedures in this topic, you must be logged on with an account that is a member of the BizTalk Server Administrators group.</span></span> <span data-ttu-id="fc360-116">詳細なアクセス許可についてを参照してください。[を展開すると、BizTalk アプリケーションの管理に必要なアクセス許可](../core/permissions-required-for-deploying-and-managing-a-biztalk-application.md)します。</span><span class="sxs-lookup"><span data-stu-id="fc360-116">For more detailed information on permissions, see [Permissions Required for Deploying and Managing a BizTalk Application](../core/permissions-required-for-deploying-and-managing-a-biztalk-application.md).</span></span>  
  
## <a name="to-remove-an-orchestration-from-an-application"></a><span data-ttu-id="fc360-117">オーケストレーションをアプリケーションから削除するには</span><span class="sxs-lookup"><span data-stu-id="fc360-117">To remove an orchestration from an application</span></span>  
  
#### <a name="using-the-biztalk-server-administration-console"></a><span data-ttu-id="fc360-118">BizTalk Server 管理コンソールの使用</span><span class="sxs-lookup"><span data-stu-id="fc360-118">Using the BizTalk Server Administration console</span></span>  
  
1. <span data-ttu-id="fc360-119">クリックして**開始**、 をクリックして**すべてのプログラム**、 をクリックして[!INCLUDE[btsBizTalkServerStartMenuItemui](../includes/btsbiztalkserverstartmenuitemui-md.md)]、順にクリックします**BizTalk Server 管理**します。</span><span class="sxs-lookup"><span data-stu-id="fc360-119">Click **Start**, click **All Programs**, click [!INCLUDE[btsBizTalkServerStartMenuItemui](../includes/btsbiztalkserverstartmenuitemui-md.md)], and then click **BizTalk Server Administration**.</span></span>  
  
2. <span data-ttu-id="fc360-120">コンソール ツリーで、展開**BizTalk Server 管理**展開し、BizTalk グループを展開し、**アプリケーション**、し、削除するオーケストレーションを含むアプリケーションを展開します。</span><span class="sxs-lookup"><span data-stu-id="fc360-120">In the console tree, expand **BizTalk Server Administration**, expand the BizTalk group, expand **Applications**, and then expand the application containing the orchestration that you want to remove.</span></span>  
  
3. <span data-ttu-id="fc360-121">クリックして**オーケストレーション**、オーケストレーションを右クリックし、クリックして**参加解除**します。</span><span class="sxs-lookup"><span data-stu-id="fc360-121">Click **Orchestrations**, right-click the orchestration, and then click **Unenlist**.</span></span>  
  
4. <span data-ttu-id="fc360-122">オーケストレーションを選択し、[**ビュー**、] をクリックし、**インスタンス情報**します。</span><span class="sxs-lookup"><span data-stu-id="fc360-122">Select the orchestration, point to **View**, and then click **Instance Information**.</span></span>  
  
5. <span data-ttu-id="fc360-123">クエリの結果ウィンドウで、オーケストレーション インスタンスを右クリックし、 **Terminate**します。</span><span class="sxs-lookup"><span data-stu-id="fc360-123">In the query results pane, right-click the orchestration instances, and then click **Terminate**.</span></span>  
  
   > [!NOTE]
   >  <span data-ttu-id="fc360-124">参加解除、インスタンス、実行中の終了および停止できますすべてのアプリケーションのオーケストレーションは、一度に、アプリケーションの完全停止オプションを使用して」の説明に従って[BizTalk アプリケーション開始および停止方法](../core/how-to-start-and-stop-a-biztalk-application.md)します。</span><span class="sxs-lookup"><span data-stu-id="fc360-124">You can unenlist, terminate running instances, and stop all of the orchestrations in an application at once by using the Full Stop option for the application, as described in [How to Start and Stop a BizTalk Application](../core/how-to-start-and-stop-a-biztalk-application.md).</span></span>  
  
6. <span data-ttu-id="fc360-125">クリックして**オーケストレーション**、オーケストレーションを右クリックし、クリックして**削除**します。</span><span class="sxs-lookup"><span data-stu-id="fc360-125">Click **Orchestrations**, right-click the orchestration, and then click **Remove**.</span></span>  
  
#### <a name="using-the-command-line"></a><span data-ttu-id="fc360-126">コマンドラインを使用</span><span class="sxs-lookup"><span data-stu-id="fc360-126">Using the command line</span></span>  
  
1. <span data-ttu-id="fc360-127">次のように、コマンド プロンプトを開きます。をクリックして**開始**、 をクリックして**実行**、型`cmd`、順にクリックします**OK**。</span><span class="sxs-lookup"><span data-stu-id="fc360-127">Open a command prompt as follows: Click **Start**, click **Run**, type `cmd`, and then click **OK**.</span></span>  
  
2. <span data-ttu-id="fc360-128">次の表に示すように、適切な値を置き換えて、次のコマンドを入力します。</span><span class="sxs-lookup"><span data-stu-id="fc360-128">Type the following command, substituting the appropriate values, as described in the following table:</span></span>  
  
    <span data-ttu-id="fc360-129">**BTSTask RemoveResource** [**/ApplicationName:**<em>value</em>] **/Luid:**<em>value</em> [**/Server:**<em>value</em>] [**/Database:**<em>value</em>]</span><span class="sxs-lookup"><span data-stu-id="fc360-129">**BTSTask RemoveResource** [**/ApplicationName:**<em>value</em>] **/Luid:**<em>value</em> [**/Server:**<em>value</em>] [**/Database:**<em>value</em>]</span></span>  
  
    <span data-ttu-id="fc360-130">例:</span><span class="sxs-lookup"><span data-stu-id="fc360-130">Example:</span></span>  
  
    <span data-ttu-id="fc360-131">**BTSTask RemoveResource /ApplicationName:MyApplication /Luid:"MyApp.Orchestrations, Version=1.0.0.0, Culture=neutral, PublicKeyToken=0123456789ABCDEF"**</span><span class="sxs-lookup"><span data-stu-id="fc360-131">**BTSTask RemoveResource /ApplicationName:MyApplication /Luid:"MyApp.Orchestrations, Version=1.0.0.0, Culture=neutral, PublicKeyToken=0123456789ABCDEF"**</span></span>  
  
   |<span data-ttu-id="fc360-132">パラメーター</span><span class="sxs-lookup"><span data-stu-id="fc360-132">Parameter</span></span>|<span data-ttu-id="fc360-133">説明</span><span class="sxs-lookup"><span data-stu-id="fc360-133">Description</span></span>|  
   |---------------|-----------------|  
   |<span data-ttu-id="fc360-134">**/ApplicationName**</span><span class="sxs-lookup"><span data-stu-id="fc360-134">**/ApplicationName**</span></span>|<span data-ttu-id="fc360-135">削除するオーケストレーションが存在する BizTalk アプリケーションの名前。</span><span class="sxs-lookup"><span data-stu-id="fc360-135">Name of the BizTalk application containing the orchestration to delete.</span></span> <span data-ttu-id="fc360-136">名前にスペースが含まれている場合は、二重引用符 (") で囲む必要があります。</span><span class="sxs-lookup"><span data-stu-id="fc360-136">If the name includes spaces, you must enclose it in double quotation marks (").</span></span> <span data-ttu-id="fc360-137">このパラメーターを指定しなかった場合、既定のアプリケーションが使用されます。</span><span class="sxs-lookup"><span data-stu-id="fc360-137">If this parameter is not specified, the default application is used.</span></span>|  
   |<span data-ttu-id="fc360-138">**/Luid**</span><span class="sxs-lookup"><span data-stu-id="fc360-138">**/Luid**</span></span>|<span data-ttu-id="fc360-139">オーケストレーションのローカル一意識別子 (LUID)。</span><span class="sxs-lookup"><span data-stu-id="fc360-139">Locally unique identifier (LUID) of the orchestration.</span></span> <span data-ttu-id="fc360-140">LUID を取得するにを使用して、 [ListApp コマンド](../core/listapp-command.md)します。</span><span class="sxs-lookup"><span data-stu-id="fc360-140">You can obtain the LUID by using the [ListApp Command](../core/listapp-command.md).</span></span>|  
   |<span data-ttu-id="fc360-141">**/サーバー**</span><span class="sxs-lookup"><span data-stu-id="fc360-141">**/Server**</span></span>|<span data-ttu-id="fc360-142">BizTalk 管理データベースをホストする SQL Server インスタンスの名前です。</span><span class="sxs-lookup"><span data-stu-id="fc360-142">Name of the SQL Server instance hosting the BizTalk Management database.</span></span> <span data-ttu-id="fc360-143">Database パラメーターを指定する場合は必須です。</span><span class="sxs-lookup"><span data-stu-id="fc360-143">Required if you specify the Database parameter.</span></span> <span data-ttu-id="fc360-144">Server パラメーターおよび Database パラメーターを指定しなかった場合、グループの既定の BizTalk 管理データベースが使用されます。</span><span class="sxs-lookup"><span data-stu-id="fc360-144">If Server and Database parameters are not specified, the default BizTalk Management database for the group is used.</span></span>|  
   |<span data-ttu-id="fc360-145">**/Database**</span><span class="sxs-lookup"><span data-stu-id="fc360-145">**/Database**</span></span>|<span data-ttu-id="fc360-146">BizTalk 管理データベースの名前。</span><span class="sxs-lookup"><span data-stu-id="fc360-146">Name of the BizTalk Management database.</span></span> <span data-ttu-id="fc360-147">Server パラメーターを指定する場合は必須です。</span><span class="sxs-lookup"><span data-stu-id="fc360-147">Required if you specify the Server parameter.</span></span> <span data-ttu-id="fc360-148">Server パラメーターおよび Database パラメーターを指定しなかった場合、グループの既定の BizTalk 管理データベースが使用されます。</span><span class="sxs-lookup"><span data-stu-id="fc360-148">If Server and Database parameters are not specified, the default BizTalk Management database for the group is used.</span></span>|  
  
## <a name="see-also"></a><span data-ttu-id="fc360-149">参照</span><span class="sxs-lookup"><span data-stu-id="fc360-149">See Also</span></span>  
 <span data-ttu-id="fc360-150">[オーケストレーションの管理](../core/managing-orchestrations.md) </span><span class="sxs-lookup"><span data-stu-id="fc360-150">[Managing Orchestrations](../core/managing-orchestrations.md) </span></span>  
 [<span data-ttu-id="fc360-151">RemoveResource コマンド</span><span class="sxs-lookup"><span data-stu-id="fc360-151">RemoveResource Command</span></span>](../core/removeresource-command.md)