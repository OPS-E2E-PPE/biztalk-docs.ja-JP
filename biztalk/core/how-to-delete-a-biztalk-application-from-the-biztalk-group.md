---
title: "BizTalk グループから BizTalk アプリケーションを削除する方法 |Microsoft ドキュメント"
ms.custom: 
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: 
ms.suite: 
ms.tgt_pltfrm: 
ms.topic: article
helpviewer_keywords:
- undeploying, applications
- applications, deleting
- applications, groups
- undeploying, deleting
- managing [applications], deleting
- deleting, applications
- applications, undeploying
- managing [applications], groups
- groups, applications
ms.assetid: 968a6436-ae1a-4f85-bb44-e704826a0197
caps.latest.revision: "28"
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: 269ef99a3244d0aba55d9dad856c0262d0d14ba0
ms.sourcegitcommit: cb908c540d8f1a692d01dc8f313e16cb4b4e696d
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 09/20/2017
---
# <a name="how-to-delete-a-biztalk-application-from-the-biztalk-group"></a><span data-ttu-id="3f11d-102">BizTalk グループから BizTalk アプリケーションを削除する方法</span><span class="sxs-lookup"><span data-stu-id="3f11d-102">How to Delete a BizTalk Application from the BizTalk Group</span></span>
<span data-ttu-id="3f11d-103">BizTalk グループからアプリケーションを削除できます。</span><span class="sxs-lookup"><span data-stu-id="3f11d-103">You can delete an application from the BizTalk group.</span></span> <span data-ttu-id="3f11d-104">アプリケーションを削除すると、グループの BizTalk データベースからアプリケーションのデータがすべて削除され、BizTalk Server 管理コンソールにアプリケーションが表示されなくなります。</span><span class="sxs-lookup"><span data-stu-id="3f11d-104">This removes all of its data from the BizTalk databases for the group, and the application no longer displays in the BizTalk Server Administration console.</span></span> <span data-ttu-id="3f11d-105">アプリケーションはアンインストールされません。</span><span class="sxs-lookup"><span data-stu-id="3f11d-105">It does not uninstall the application.</span></span>  
  
 <span data-ttu-id="3f11d-106">アプリケーションを削除する前に、次の点を考慮してください。</span><span class="sxs-lookup"><span data-stu-id="3f11d-106">Before you delete an application, bear in mind the following points:</span></span>  
  
-   <span data-ttu-id="3f11d-107">アプリケーションを削除する前に、アプリケーションを停止しておく必要があります。</span><span class="sxs-lookup"><span data-stu-id="3f11d-107">The application must be stopped before you can delete it.</span></span> <span data-ttu-id="3f11d-108">」の説明に従って、アプリケーションを停止する完全停止オプションを使用する必要があります[起動し、BizTalk アプリケーションを停止する方法](../core/how-to-start-and-stop-a-biztalk-application.md)です。</span><span class="sxs-lookup"><span data-stu-id="3f11d-108">You should use the Full Stop option for stopping the application, as described in [How to Start and Stop a BizTalk Application](../core/how-to-start-and-stop-a-biztalk-application.md).</span></span>  
  
-   <span data-ttu-id="3f11d-109">アプリケーションを削除できるのは、削除対象のアプリケーションを他のアプリケーションが参照していない場合だけです。</span><span class="sxs-lookup"><span data-stu-id="3f11d-109">You can delete an application only if no other applications contain references to it.</span></span> <span data-ttu-id="3f11d-110">削除するアプリケーションを他のアプリケーションが参照している場合、先に他のアプリケーションから参照を削除する必要があります。</span><span class="sxs-lookup"><span data-stu-id="3f11d-110">If other applications contain references to the application you want to remove, you must first remove the references from the other applications.</span></span> <span data-ttu-id="3f11d-111">手順については、次を参照してください。[を別のアプリケーションへの参照を削除する方法](../core/how-to-remove-a-reference-to-another-application.md)です。</span><span class="sxs-lookup"><span data-stu-id="3f11d-111">For instructions, see [How to Remove a Reference to Another Application](../core/how-to-remove-a-reference-to-another-application.md).</span></span>  
  
-   <span data-ttu-id="3f11d-112">削除対象のアプリケーションの送信ポート グループに、他のアプリケーションの送信ポートが属している場合、そのアプリケーションは削除できません。</span><span class="sxs-lookup"><span data-stu-id="3f11d-112">You cannot delete an application if it contains a send port group of which a send port in another application is a member.</span></span> <span data-ttu-id="3f11d-113">メンバーとなっている送信ポートを参加解除してから、アプリケーションを削除する必要があります。</span><span class="sxs-lookup"><span data-stu-id="3f11d-113">You must unenlist the member send port before you can delete the application.</span></span> <span data-ttu-id="3f11d-114">手順については、次を参照してください。[送信ポートまたは送信ポート グループを参加解除する方法](../core/how-to-unenlist-a-send-port-or-send-port-group.md)です。</span><span class="sxs-lookup"><span data-stu-id="3f11d-114">For instructions, see [How to Unenlist a Send Port or Send Port Group](../core/how-to-unenlist-a-send-port-or-send-port-group.md).</span></span>  
  
-   <span data-ttu-id="3f11d-115">削除対象のアプリケーションに、パーティによって参照されている送信ポートが含まれている場合、そのアプリケーションは削除できません。</span><span class="sxs-lookup"><span data-stu-id="3f11d-115">You cannot delete an application if it contains a send port that is referenced by a party.</span></span> <span data-ttu-id="3f11d-116">パーティから参照を削除するか、送信ポートを削除するか、または送信ポートを別のアプリケーションに移動します。</span><span class="sxs-lookup"><span data-stu-id="3f11d-116">You can delete the reference from the party, delete the send port, or move the send port to a different application.</span></span> <span data-ttu-id="3f11d-117">これらのタスクの実行方法の詳細については、次を参照してください。[方法を表示または編集するパーティ](http://msdn.microsoft.com/library/42e6f3a0-8f7d-4f6c-ab05-a1fab7bf46ca)、[送信ポートを削除する方法](../core/how-to-delete-a-send-port.md)、または[別のアプリケーションにアイテムを移動する方法](../core/how-to-move-an-artifact-to-a-different-application.md)です。</span><span class="sxs-lookup"><span data-stu-id="3f11d-117">For instructions on performing these tasks, see [How to View or Edit a Party](http://msdn.microsoft.com/library/42e6f3a0-8f7d-4f6c-ab05-a1fab7bf46ca), [How to Delete a Send Port](../core/how-to-delete-a-send-port.md), or [How to Move an Artifact to a Different Application](../core/how-to-move-an-artifact-to-a-different-application.md).</span></span>  
  
-   <span data-ttu-id="3f11d-118">既定のアプリケーションは削除できません。</span><span class="sxs-lookup"><span data-stu-id="3f11d-118">You cannot delete the default application.</span></span> <span data-ttu-id="3f11d-119">別のアプリケーションを既定にしてから削除する必要があります。</span><span class="sxs-lookup"><span data-stu-id="3f11d-119">If you want to delete it, you must first make another application the default.</span></span> <span data-ttu-id="3f11d-120">手順については、次を参照してください。[を既定のアプリケーションを変更する方法](../core/how-to-change-the-default-application.md)です。</span><span class="sxs-lookup"><span data-stu-id="3f11d-120">For instructions, see [How to Change the Default Application](../core/how-to-change-the-default-application.md).</span></span>  
  
-   <span data-ttu-id="3f11d-121">削除対象のアプリケーションのオーケストレーションに、中断したインスタンスが含まれている場合、そのアプリケーションは削除できません。</span><span class="sxs-lookup"><span data-stu-id="3f11d-121">You cannot delete an application if an orchestration in the application has a suspended instance.</span></span>  
  
-   <span data-ttu-id="3f11d-122">BizTalk アプリケーションを完全に展開解除、行う必要がありますもで説明した手順[を BizTalk アプリケーションをアンインストールする方法](../core/how-to-uninstall-a-biztalk-application.md)、」の説明に従って、他のファイルと設定を削除する必要がありますもと[を削除する方法その他のファイルと BizTalk アプリケーションの設定](../core/how-to-remove-other-files-and-settings-for-a-biztalk-application.md)です。</span><span class="sxs-lookup"><span data-stu-id="3f11d-122">To completely undeploy a BizTalk application, you must also take the steps described in [How to Uninstall a BizTalk Application](../core/how-to-uninstall-a-biztalk-application.md), and you may also need to remove other files and settings, as described in [How to Remove Other Files and Settings for a BizTalk Application](../core/how-to-remove-other-files-and-settings-for-a-biztalk-application.md).</span></span>  
  
## <a name="prerequisites"></a><span data-ttu-id="3f11d-123">前提条件</span><span class="sxs-lookup"><span data-stu-id="3f11d-123">Prerequisites</span></span>  
 <span data-ttu-id="3f11d-124">このトピックの手順を実行するには、BizTalk Server 管理者グループのメンバーであるアカウントを使用してログオンする必要があります。</span><span class="sxs-lookup"><span data-stu-id="3f11d-124">To perform the procedures in this topic, you must be logged on with an account that is a member of the BizTalk Server Administrators group.</span></span> <span data-ttu-id="3f11d-125">詳細なアクセス許可についてを参照してください。[を展開すると、BizTalk アプリケーションの管理に必要なアクセス許可](../core/permissions-required-for-deploying-and-managing-a-biztalk-application.md)です。</span><span class="sxs-lookup"><span data-stu-id="3f11d-125">For more detailed information on permissions, see [Permissions Required for Deploying and Managing a BizTalk Application](../core/permissions-required-for-deploying-and-managing-a-biztalk-application.md).</span></span>  
  
## <a name="to-delete-a-biztalk-application"></a><span data-ttu-id="3f11d-126">BizTalk アプリケーションを削除するには</span><span class="sxs-lookup"><span data-stu-id="3f11d-126">To delete a BizTalk application</span></span>  
  
#### <a name="using-the-biztalk-server-administration-console"></a><span data-ttu-id="3f11d-127">BizTalk Server 管理コンソールの使用</span><span class="sxs-lookup"><span data-stu-id="3f11d-127">Using the BizTalk Server Administration console</span></span>  
  
1.  <span data-ttu-id="3f11d-128">をクリックして**開始**、 をクリックして**すべてのプログラム**、 をクリックして[!INCLUDE[btsBizTalkServerStartMenuItemui](../includes/btsbiztalkserverstartmenuitemui-md.md)]、順にクリック**BizTalk Server 管理コンソール**です。</span><span class="sxs-lookup"><span data-stu-id="3f11d-128">Click **Start**, click **All Programs**, click [!INCLUDE[btsBizTalkServerStartMenuItemui](../includes/btsbiztalkserverstartmenuitemui-md.md)], and then click **BizTalk Server Administration**.</span></span>  
  
2.  <span data-ttu-id="3f11d-129">コンソール ツリーで  **BizTalk Server 管理コンソール**BizTalk グループを展開し、展開、**アプリケーション**です。</span><span class="sxs-lookup"><span data-stu-id="3f11d-129">In the console tree, expand  **BizTalk Server Administration**, expand the BizTalk group, and expand **Applications**.</span></span>  
  
3.  <span data-ttu-id="3f11d-130">アプリケーションのフォルダーを右クリックし、をクリックして**削除**です。</span><span class="sxs-lookup"><span data-stu-id="3f11d-130">Right-click the application folder, and then click **Delete**.</span></span>  
  
4.  <span data-ttu-id="3f11d-131">をクリックして**はい**削除を確認します。</span><span class="sxs-lookup"><span data-stu-id="3f11d-131">Click **Yes** to confirm the deletion.</span></span>  
  
     <span data-ttu-id="3f11d-132">BizTalk Server は、BizTalk データベースからアプリケーションのデータをすべて削除し、BizTalk Server 管理コンソールからアプリケーションを削除します。</span><span class="sxs-lookup"><span data-stu-id="3f11d-132">BizTalk Server deletes all of the application data from the BizTalk databases and removes the application from the administration console.</span></span>  
  
     <span data-ttu-id="3f11d-133">BizTalk Server がアプリケーション アイテムを削除できない場合、削除操作が失敗します。</span><span class="sxs-lookup"><span data-stu-id="3f11d-133">If BizTalk Server cannot delete any of the application artifacts, the delete operation fails.</span></span> <span data-ttu-id="3f11d-134">この場合、BizTalk Server は削除操作のロールバックを試行します。</span><span class="sxs-lookup"><span data-stu-id="3f11d-134">In this case, BizTalk Server attempts to roll back the delete operation.</span></span>  
  
#### <a name="using-the-command-line"></a><span data-ttu-id="3f11d-135">コマンドラインを使用</span><span class="sxs-lookup"><span data-stu-id="3f11d-135">Using the command line</span></span>  
  
1.  <span data-ttu-id="3f11d-136">次のように、コマンド プロンプトを開きます: をクリックして**開始**、 をクリックして**実行**、型`cmd`、順にクリック**ok**です。</span><span class="sxs-lookup"><span data-stu-id="3f11d-136">Open a command prompt as follows: Click **Start**, click **Run**, type `cmd`, and then click **OK**.</span></span>  
  
2.  <span data-ttu-id="3f11d-137">次の表に示すように、適切な値を置き換えて、次のコマンドを入力します。</span><span class="sxs-lookup"><span data-stu-id="3f11d-137">Type the following command, substituting the appropriate values, as described in the following table:</span></span>  
  
     <span data-ttu-id="3f11d-138">**BTSTask RemoveApp/applicationname は:** *値*[**/Server:***値*] [**/database:** *値*]</span><span class="sxs-lookup"><span data-stu-id="3f11d-138">**BTSTask RemoveApp /ApplicationName:** *value* [**/Server:***value*] [**/Database:***value*]</span></span>  
  
     <span data-ttu-id="3f11d-139">例:</span><span class="sxs-lookup"><span data-stu-id="3f11d-139">Example:</span></span>  
  
     <span data-ttu-id="3f11d-140">**BTSTask RemoveApp applicationname:**</span><span class="sxs-lookup"><span data-stu-id="3f11d-140">**BTSTask RemoveApp /ApplicationName:MyApplication**</span></span>  
  
    |<span data-ttu-id="3f11d-141">パラメーター</span><span class="sxs-lookup"><span data-stu-id="3f11d-141">Parameter</span></span>|<span data-ttu-id="3f11d-142">値</span><span class="sxs-lookup"><span data-stu-id="3f11d-142">Value</span></span>|  
    |---------------|-----------|  
    |<span data-ttu-id="3f11d-143">**/ApplicationName**</span><span class="sxs-lookup"><span data-stu-id="3f11d-143">**/ApplicationName**</span></span>|<span data-ttu-id="3f11d-144">削除する BizTalk アプリケーションの名前。</span><span class="sxs-lookup"><span data-stu-id="3f11d-144">Name of the BizTalk application to delete.</span></span> <span data-ttu-id="3f11d-145">名前には、スペースが含まれている場合は、二重引用符 (") で囲む必要があります。</span><span class="sxs-lookup"><span data-stu-id="3f11d-145">If the name includes spaces, you must enclose it in double quotation marks (").</span></span>|  
    |<span data-ttu-id="3f11d-146">**/サーバー**</span><span class="sxs-lookup"><span data-stu-id="3f11d-146">**/Server**</span></span>|<span data-ttu-id="3f11d-147">BizTalk 管理データベースをホストする SQL Server インスタンスの名前です。</span><span class="sxs-lookup"><span data-stu-id="3f11d-147">Name of the SQL Server instance hosting the BizTalk Management database.</span></span> <span data-ttu-id="3f11d-148">Database パラメーターを指定する場合は必須です。</span><span class="sxs-lookup"><span data-stu-id="3f11d-148">Required if you specify the Database parameter.</span></span> <span data-ttu-id="3f11d-149">Server パラメーターおよび Database パラメーターを指定しなかった場合、グループの既定の BizTalk 管理データベースが使用されます。</span><span class="sxs-lookup"><span data-stu-id="3f11d-149">If Server and Database parameters are not specified, the default BizTalk Management database for the group is used.</span></span>|  
    |<span data-ttu-id="3f11d-150">**/データベース**</span><span class="sxs-lookup"><span data-stu-id="3f11d-150">**/Database**</span></span>|<span data-ttu-id="3f11d-151">BizTalk 管理データベースの名前。</span><span class="sxs-lookup"><span data-stu-id="3f11d-151">Name of the BizTalk Management database.</span></span> <span data-ttu-id="3f11d-152">Server パラメーターを指定する場合は必須です。</span><span class="sxs-lookup"><span data-stu-id="3f11d-152">Required if you specify the Server parameter.</span></span> <span data-ttu-id="3f11d-153">Server パラメーターおよび Database パラメーターを指定しなかった場合、グループの既定の BizTalk 管理データベースが使用されます。</span><span class="sxs-lookup"><span data-stu-id="3f11d-153">If Server and Database parameters are not specified, the default BizTalk Management database for the group is used.</span></span>|  
  
## <a name="see-also"></a><span data-ttu-id="3f11d-154">参照</span><span class="sxs-lookup"><span data-stu-id="3f11d-154">See Also</span></span>  
 <span data-ttu-id="3f11d-155">[BizTalk アプリケーションを展開解除](../core/undeploying-biztalk-applications.md) </span><span class="sxs-lookup"><span data-stu-id="3f11d-155">[Undeploying BizTalk Applications](../core/undeploying-biztalk-applications.md) </span></span>  
 [<span data-ttu-id="3f11d-156">BizTalk アプリケーションの展開</span><span class="sxs-lookup"><span data-stu-id="3f11d-156">Deploying BizTalk Applications</span></span>](../core/deploying-biztalk-applications.md)