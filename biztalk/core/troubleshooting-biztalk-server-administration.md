---
title: "BizTalk Server 管理のトラブルシューティング |Microsoft ドキュメント"
ms.custom: 
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: 
ms.suite: 
ms.tgt_pltfrm: 
ms.topic: article
ms.assetid: 9dfb56b0-352f-4012-b030-087bbcfe09d4
caps.latest.revision: "27"
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: d89f81bbaf15dfb0c87de91659888d70a2345a6c
ms.sourcegitcommit: cb908c540d8f1a692d01dc8f313e16cb4b4e696d
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 09/20/2017
---
# <a name="troubleshooting-biztalk-server-administration"></a><span data-ttu-id="d0352-102">BizTalk Server 管理のトラブルシューティング</span><span class="sxs-lookup"><span data-stu-id="d0352-102">Troubleshooting BizTalk Server Administration</span></span>
<span data-ttu-id="d0352-103">このセクションでは、BizTalk Server 管理コンソールの使用時に発生する一般的な問題に関する情報をまとめて提供します。</span><span class="sxs-lookup"><span data-stu-id="d0352-103">This section provides a centralized location for information about common problems encountered while using the BizTalk Server Administration console.</span></span>  
  
 <span data-ttu-id="d0352-104">次の既知の問題、に加えて[一般的な問題と解決策を BizTalk Server 管理コンソール](http://social.technet.microsoft.com/wiki/contents/articles/common-issues-and-resolutions-with-the-biztalk-server-administration-console.aspx)追加情報を提供します。</span><span class="sxs-lookup"><span data-stu-id="d0352-104">In addition to the following Known Issues, [Common Issues and Resolutions With the BizTalk Server Administration Console](http://social.technet.microsoft.com/wiki/contents/articles/common-issues-and-resolutions-with-the-biztalk-server-administration-console.aspx) provides additional information.</span></span>  
  
## <a name="known-issues"></a><span data-ttu-id="d0352-105">既知の問題</span><span class="sxs-lookup"><span data-stu-id="d0352-105">Known Issues</span></span>  
  
#### <a name="delay-in-entsso-service-prevents-biztalk-server-service-from-starting"></a><span data-ttu-id="d0352-106">ENTSSO サービスの遅れのため、BizTalk Server サービスが開始されない</span><span class="sxs-lookup"><span data-stu-id="d0352-106">Delay in ENTSSO Service prevents BizTalk Server service from starting</span></span>  
  
##### <a name="problem"></a><span data-ttu-id="d0352-107">問題</span><span class="sxs-lookup"><span data-stu-id="d0352-107">Problem</span></span>  
 <span data-ttu-id="d0352-108">DTC を使用したコンピューターの再起動が自動起動に設定されていない場合、BizTalk Server サービスが開始されないことがあります。</span><span class="sxs-lookup"><span data-stu-id="d0352-108">Rebooting your computer with DTC not set to automatic start-up may prevent the BizTalk Server service from starting.</span></span>  
  
##### <a name="cause"></a><span data-ttu-id="d0352-109">原因</span><span class="sxs-lookup"><span data-stu-id="d0352-109">Cause</span></span>  
 <span data-ttu-id="d0352-110">これは、ENTSSO サービスの開始にかかる時間が、BizTalk Server サーバーに許可されたタイムアウト時間を超えることがあるためです。</span><span class="sxs-lookup"><span data-stu-id="d0352-110">This is because the ENTSSO service can take more time to start than is allowed by the BizTalk Server service timeout duration.</span></span>  
  
##### <a name="solution"></a><span data-ttu-id="d0352-111">解決方法</span><span class="sxs-lookup"><span data-stu-id="d0352-111">Solution</span></span>  
 <span data-ttu-id="d0352-112">この問題を解決するには、DTC を自動に設定します。</span><span class="sxs-lookup"><span data-stu-id="d0352-112">To resolve this issue, set DTC to automatic.</span></span>  
  
#### <a name="sql-resources-may-become-locked"></a><span data-ttu-id="d0352-113">SQL リソースがロックされることがある</span><span class="sxs-lookup"><span data-stu-id="d0352-113">SQL resources may become locked</span></span>  
  
##### <a name="problem"></a><span data-ttu-id="d0352-114">問題</span><span class="sxs-lookup"><span data-stu-id="d0352-114">Problem</span></span>  
 <span data-ttu-id="d0352-115">次のエラーが発生することがあります。</span><span class="sxs-lookup"><span data-stu-id="d0352-115">The following error may occur:</span></span>  
  
 <span data-ttu-id="d0352-116">**トランザクション (プロセス ID 95) が、ロックのリソースで他のプロセスとデッドロックして、このトランザクションがそのデッドロックの対象となりました。トランザクションを再実行します。**</span><span class="sxs-lookup"><span data-stu-id="d0352-116">**Transaction (Process ID 95) was deadlocked on lock resources with another process and has been chosen as the deadlock victim. Rerun the transaction.**</span></span>  
  
##### <a name="cause"></a><span data-ttu-id="d0352-117">原因</span><span class="sxs-lookup"><span data-stu-id="d0352-117">Cause</span></span>  
 <span data-ttu-id="d0352-118">これはまれに発生する状況であり、ユーザーが行った管理操作のために別のユーザーがデータベース管理からロックアウトされています。</span><span class="sxs-lookup"><span data-stu-id="d0352-118">This is a very rare situation in which administrative operations performed by one user result in another user being locked out of database administration.</span></span>  
  
##### <a name="solution"></a><span data-ttu-id="d0352-119">解決方法</span><span class="sxs-lookup"><span data-stu-id="d0352-119">Solution</span></span>  
 <span data-ttu-id="d0352-120">問題は短時間で自動的に解消されます。</span><span class="sxs-lookup"><span data-stu-id="d0352-120">The problem should remedy itself shortly.</span></span> <span data-ttu-id="d0352-121">数分後にもう一度実行してみてください。</span><span class="sxs-lookup"><span data-stu-id="d0352-121">Try the operation again in a few minutes.</span></span>  
  
#### <a name="sql-database-may-become-locked"></a><span data-ttu-id="d0352-122">SQL データベースがロックされることがある</span><span class="sxs-lookup"><span data-stu-id="d0352-122">SQL database may become locked</span></span>  
  
##### <a name="problem"></a><span data-ttu-id="d0352-123">問題</span><span class="sxs-lookup"><span data-stu-id="d0352-123">Problem</span></span>  
 <span data-ttu-id="d0352-124">ユーザーが SQL データベースからロックアウトされることがあります。</span><span class="sxs-lookup"><span data-stu-id="d0352-124">Users may be locked out of the SQL database.</span></span> <span data-ttu-id="d0352-125">さまざまなエラー メッセージが返される可能性があります。</span><span class="sxs-lookup"><span data-stu-id="d0352-125">A number of different error messages may be returned.</span></span>  
  
##### <a name="cause"></a><span data-ttu-id="d0352-126">原因</span><span class="sxs-lookup"><span data-stu-id="d0352-126">Cause</span></span>  
 <span data-ttu-id="d0352-127">1 人のユーザーがデータベースに書き込んでいるため、実質的に別のユーザーがデータベースからロックアウトされることがあります。</span><span class="sxs-lookup"><span data-stu-id="d0352-127">In some cases one user writing to the database will effectively lock another user out of the database.</span></span>  
  
##### <a name="solution"></a><span data-ttu-id="d0352-128">解決方法</span><span class="sxs-lookup"><span data-stu-id="d0352-128">Solution</span></span>  
 <span data-ttu-id="d0352-129">問題は短時間で自動的に解消されます。</span><span class="sxs-lookup"><span data-stu-id="d0352-129">The problem should remedy itself shortly.</span></span> <span data-ttu-id="d0352-130">数分後にもう一度実行してみてください。</span><span class="sxs-lookup"><span data-stu-id="d0352-130">Try the operation again in a few minutes.</span></span>  
  
#### <a name="termination-of-multiple-service-instances-in-a-multiple-messagebox-environment-fails-with-an-error"></a><span data-ttu-id="d0352-131">複数のメッセージ ボックス環境で複数のサービス インスタンスを終了するとエラーが発生する</span><span class="sxs-lookup"><span data-stu-id="d0352-131">Termination of multiple service instances in a multiple messagebox environment fails with an error</span></span>  
  
##### <a name="problem"></a><span data-ttu-id="d0352-132">問題</span><span class="sxs-lookup"><span data-stu-id="d0352-132">Problem</span></span>  
 <span data-ttu-id="d0352-133">BizTalk Server 管理コンソールから複数のサービス インスタンスを終了しようとすると失敗し、次のようなエラーが表示されます。</span><span class="sxs-lookup"><span data-stu-id="d0352-133">Attempts to terminate multiple service instances from the BizTalk Server Administration console fail and an error similar to the following is displayed:</span></span>  
  
 <span data-ttu-id="d0352-134">SQL Server によって、コンポーネント 'Agent XPs' のプロシージャ 'sys.xp_sqlagent_enum_jobs' に対するアクセスがブロックされました。サーバーのセキュリティ構成で、このモジュールが OFF に設定されているためです。</span><span class="sxs-lookup"><span data-stu-id="d0352-134">SQL Server blocked access to procedure 'sys.xp_sqlagent_enum_jobs' of component 'Agent XPs' because this component is turned off as part of the security configuration for this server.</span></span>  
  
> [!NOTE]
>  <span data-ttu-id="d0352-135">この問題は複数のメッセージ ボックス環境で発生します。</span><span class="sxs-lookup"><span data-stu-id="d0352-135">This problem occurs in a multiple messagebox environment.</span></span>  
  
##### <a name="cause"></a><span data-ttu-id="d0352-136">原因</span><span class="sxs-lookup"><span data-stu-id="d0352-136">Cause</span></span>  
 <span data-ttu-id="d0352-137">場合、複数のメッセージ ボックス環境でこの問題は発生 SQL エージェント ジョブ ' operations_operateoninstances_onmaster _\<*dbName*>' が、セカンダリ メッセージ ボックス データベースで実行されていません。</span><span class="sxs-lookup"><span data-stu-id="d0352-137">This problem can occur in a multiple messagebox environment if the SQL agent job 'Operations_OperateOnInstances_OnMaster_\<*dbName*>' is not running on the secondary messagebox databases.</span></span> <span data-ttu-id="d0352-138">セカンダリ メッセージ ボックス データベースからプライマリ メッセージ ボックス データベースに情報を伝達するためには、このジョブを実行している必要があります。</span><span class="sxs-lookup"><span data-stu-id="d0352-138">This job must be running in order to propagate information from the secondary messagebox databases to the primary messagebox database.</span></span> <span data-ttu-id="d0352-139">このジョブが有効になっていないか、ログオン エラーが発生した場合、このジョブは実行できません。</span><span class="sxs-lookup"><span data-stu-id="d0352-139">This job will fail to run if it is not enabled or if a logon failure occurs.</span></span>  
  
##### <a name="solution"></a><span data-ttu-id="d0352-140">解決方法</span><span class="sxs-lookup"><span data-stu-id="d0352-140">Solution</span></span>  
 <span data-ttu-id="d0352-141">操作を実行する複数のサービス インスタンスで同時に、BizTalk 管理コンソールを使用しているし、複数のメッセージ ボックス データベース、BizTalk Server 環境を構成する場合は、SQL Server エージェント ジョブがという名前のことを確認 ' Operations_OperateOnInstances_OnMaster_\<*dbName*>' は、すべてのセカンダリ (マスター以外の) メッセージ ボックス データベースで有効にします。</span><span class="sxs-lookup"><span data-stu-id="d0352-141">If you are using the BizTalk Administration console to perform operations on multiple service instances simultaneously and your BizTalk Server environment is configured with multiple messagebox databases, verify that the SQL Server Agent job named 'Operations_OperateOnInstances_OnMaster_\<*dbName*>' is enabled on all secondary (non-master) messagebox databases.</span></span> <span data-ttu-id="d0352-142">さらに、セカンダリ メッセージ ボックス データベースをホストする SQL Server コンピューターの SQL Server エージェント サービスは、セカンダリ メッセージ ボックス データベースの BTS_SQLAGENT_USER データベース ロールに含まれるアカウントとして実行する必要があります。</span><span class="sxs-lookup"><span data-stu-id="d0352-142">Additionally, the SQL Server Agent service on the SQL Server computer that hosts the secondary messagebox databases must run as an account that is included in the BTS_SQLAGENT_USER database role of the secondary messagebox database.</span></span>  
  
> [!NOTE]
>  <span data-ttu-id="d0352-143">\<*dbname*> は、BizTalk メッセージ ボックス データベースの実際の名前を表すプレース ホルダーです。</span><span class="sxs-lookup"><span data-stu-id="d0352-143">\<*dbname*> is a placeholder for the actual name of the BizTalk messagebox database.</span></span>  
  
 <span data-ttu-id="d0352-144">SQL Server エージェント サービス アカウントをセカンダリ メッセージ ボックス データベースの BTS_SQLAGENT_USER データベース ロールに追加するには、次の手順を実行します。</span><span class="sxs-lookup"><span data-stu-id="d0352-144">Follow these steps to add the SQL Server Agent service account to the BTS_SQLAGENT_USER database role of the secondary messagebox database</span></span>  
  
 <span data-ttu-id="d0352-145">**SQL Server 2008 で**</span><span class="sxs-lookup"><span data-stu-id="d0352-145">**On SQL Server 2008**</span></span>  
  
1.  <span data-ttu-id="d0352-146">をクリックして**開始**、 をポイント**すべてのプログラム**、 をポイント**Microsoft SQL Server 2008**、順にクリック**SQL Server Management Studio**です。</span><span class="sxs-lookup"><span data-stu-id="d0352-146">Click **Start**, point to **All Programs**, point to **Microsoft SQL Server 2008**, and then click **SQL Server Management Studio**.</span></span>  
  
2.  <span data-ttu-id="d0352-147">入力を求められたらを選択して、**サーバーの種類**の**データベース エンジン**を入力するかを選択、**サーバー名**セカンダリ メッセージ ボックス データベースをホストします。</span><span class="sxs-lookup"><span data-stu-id="d0352-147">When prompted choose the **Server type** of **Database Engine** and enter or select the **Server name** that hosts the secondary messagebox database.</span></span>  
  
3.  <span data-ttu-id="d0352-148">クリックして展開**データベース**セカンダリ メッセージ ボックス データベースを展開し、クリックして展開**セキュリティ**をクリックして展開**ロール**をクリックして展開**データベース ロール**、し、BTS_SQLAGENT_USER データベース ロールをダブルクリックします。</span><span class="sxs-lookup"><span data-stu-id="d0352-148">Click to expand **Databases**, click to expand the secondary messagebox database, click to expand **Security**, click to expand **Roles**, click to expand **Database Roles**, and then double-click the BTS_SQLAGENT_USER database role.</span></span>  
  
4.  <span data-ttu-id="d0352-149">**[追加]** をクリックします。</span><span class="sxs-lookup"><span data-stu-id="d0352-149">Click the **Add** button.</span></span>  
  
5.  <span data-ttu-id="d0352-150">をクリックして**参照**、SQL Server エージェント サービス アカウントのメンバーであるグループを選択し、をクリックして**OK**です。</span><span class="sxs-lookup"><span data-stu-id="d0352-150">Click **Browse**, select a group that the SQL Server Agent service account is a member of, and then click **OK**.</span></span>  
  
> [!NOTE]
>  <span data-ttu-id="d0352-151">SQL Server エージェント サービス アカウントが指定されたグループのメンバーではない場合、このアカウントをグループに追加する必要があります。</span><span class="sxs-lookup"><span data-stu-id="d0352-151">If the SQL Server Agent service account is not a member of the specified group then you will need to add it to the group.</span></span>  
  
#### <a name="changes-applied-in-one-instance-of-the-biztalk-administration-console-are-not-automatically-updated-in-other-instances-of-the-biztalk-administration-console"></a><span data-ttu-id="d0352-152">BizTalk 管理コンソールのあるインスタンスに適用した変更が、BizTalk 管理コンソールの他のインスタンスに自動的に反映されない</span><span class="sxs-lookup"><span data-stu-id="d0352-152">Changes applied in one instance of the BizTalk Administration console are not automatically updated in other instances of the BizTalk Administration console</span></span>  
  
##### <a name="problem"></a><span data-ttu-id="d0352-153">問題</span><span class="sxs-lookup"><span data-stu-id="d0352-153">Problem</span></span>  
 <span data-ttu-id="d0352-154">BizTalk 管理コンソールの複数のインスタンスが同時に同じ BizTalk Server グループに接続している場合に、あるインスタンスで行われた変更が他のインスタンスに自動的に反映されません。</span><span class="sxs-lookup"><span data-stu-id="d0352-154">If multiple instances of the BizTalk Administration console are simultaneously connected to the same BizTalk Server group, changes made in one instance of the BizTalk Administration console are not automatically reflected in the other instance(s) of the BizTalk Administration console.</span></span> <span data-ttu-id="d0352-155">このため、BizTalk 管理コンソールのインスタンスに表示されているアイテムの状態が BizTalk 管理データベースに格納されているアイテムの実際の状態と一致しない場合に、そのインスタンスでアイテムを変更しようとすると、同時実行違反エラーが発生する可能性があります。</span><span class="sxs-lookup"><span data-stu-id="d0352-155">This can cause concurrency violation errors when attempting to modify an artifact displayed in an instance of the BizTalk Administration console if the state of the artifact does not match the actual state of the artifact as stored in the BizTalk management database.</span></span>  
  
##### <a name="cause"></a><span data-ttu-id="d0352-156">原因</span><span class="sxs-lookup"><span data-stu-id="d0352-156">Cause</span></span>  
 <span data-ttu-id="d0352-157">BizTalk 管理コンソールの各インスタンスは、BizTalk グループ構成のキャッシュを独自に保持しており、そのキャッシュにのみ変更を反映します。</span><span class="sxs-lookup"><span data-stu-id="d0352-157">Each instance of the BizTalk Administration console maintains its own cache of the BizTalk group configuration and only reflects changes in the cache.</span></span> <span data-ttu-id="d0352-158">キャッシュが更新されるのは、BizTalk 管理コンソール ビューが更新されるときだけです。</span><span class="sxs-lookup"><span data-stu-id="d0352-158">The cache is only updated when the BizTalk Administration console view is refreshed.</span></span>  
  
##### <a name="resolution"></a><span data-ttu-id="d0352-159">解決策</span><span class="sxs-lookup"><span data-stu-id="d0352-159">Resolution</span></span>  
 <span data-ttu-id="d0352-160">BizTalk 管理コンソールで、同時実行違反エラーが発生した場合をクリックして、BizTalk 管理コンソールのインスタンスのキャッシュを更新、**更新**BizTalk 管理コンソール ボタンツールバーまたはキーを押して、 **f5 キーを押して**キー。</span><span class="sxs-lookup"><span data-stu-id="d0352-160">If you receive concurrency violation errors in the BizTalk Administration console, update the cache for the instance of the BizTalk Administration console by clicking the **Refresh** button on the BizTalk Administration console toolbar or by pressing the **F5** key.</span></span>  
  
#### <a name="failed-to-execute-action-stop-error-occurs-when-you-attempt-to-stop-an-orchestration-with-the-biztalk-administration-console"></a><span data-ttu-id="d0352-161">BizTalk 管理コンソールでオーケストレーションを停止しようとすると、"アクション '停止' の実行に失敗しました" というエラーが発生する</span><span class="sxs-lookup"><span data-stu-id="d0352-161">Failed to execute action 'Stop' error occurs when you attempt to stop an Orchestration with the BizTalk Administration console</span></span>  
  
##### <a name="problem"></a><span data-ttu-id="d0352-162">問題</span><span class="sxs-lookup"><span data-stu-id="d0352-162">Problem</span></span>  
 <span data-ttu-id="d0352-163">BizTalk 管理コンソールでオーケストレーションを停止しようとすると、次のようなエラー メッセージが表示されます。</span><span class="sxs-lookup"><span data-stu-id="d0352-163">When you attempt to stop an Orchestration in the BizTalk Administration console, an error message similar to the following is generated:</span></span>  
  
```  
Failed to execute action 'Stop'.  
------------------------------  
ADDITIONAL INFORMATION:  
A transport-level error has occurred when sending the request to the server. (provider: TCP Provider, error: 0 - An existing connection was forcibly closed by the remote host.) (Microsoft SQL Server, Error: 10054)  
```  
  
 <span data-ttu-id="d0352-164">この問題は、次の条件が当てはまるときに発生します。</span><span class="sxs-lookup"><span data-stu-id="d0352-164">This problem may occur if the following conditions are true:</span></span>  
  
-   <span data-ttu-id="d0352-165">BizTalk 管理コンソールが開いている。</span><span class="sxs-lookup"><span data-stu-id="d0352-165">The BizTalk Administration console is open.</span></span>  
  
-   <span data-ttu-id="d0352-166">BizTalk 管理データベースが SQL Server のクラスター化インスタンスにインストールされている。</span><span class="sxs-lookup"><span data-stu-id="d0352-166">The BizTalk management database is installed on a clustered instance of SQL Server.</span></span>  
  
-   <span data-ttu-id="d0352-167">SQL Server のクラスター化インスタンスがフェールオーバーされている。</span><span class="sxs-lookup"><span data-stu-id="d0352-167">The clustered instance of SQL Server is failed over.</span></span>  
  
-   <span data-ttu-id="d0352-168">フェールオーバー完了後に、BizTalk 管理コンソールを使用してオーケストレーションの実行中のインスタンスを停止しようとした。</span><span class="sxs-lookup"><span data-stu-id="d0352-168">After the failover is complete, you attempt to stop a running instance of an orchestration using the BizTalk Administration console.</span></span>  
  
##### <a name="cause"></a><span data-ttu-id="d0352-169">原因</span><span class="sxs-lookup"><span data-stu-id="d0352-169">Cause</span></span>  
 <span data-ttu-id="d0352-170">BizTalk 管理コンソールは、[!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)] の管理データベースへの接続を維持しています。</span><span class="sxs-lookup"><span data-stu-id="d0352-170">The BizTalk Administration console maintains a connection to the [!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)] management database.</span></span> <span data-ttu-id="d0352-171">フェールオーバー中に [!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)] の管理データベースとの接続が切断されると、BizTalk 管理コンソールをいったん閉じて再度開くまで、一部の管理タスクから "接続できませんでした" または "実行できませんでした" というエラーが返される場合があります。</span><span class="sxs-lookup"><span data-stu-id="d0352-171">When the connection to [!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)] management database has been broken during the failover, some management tasks may return a "Failed to connect" or "Failed to execute" error until the BizTalk Administration console has been closed and reopened.</span></span>  
  
##### <a name="resolution"></a><span data-ttu-id="d0352-172">解決策</span><span class="sxs-lookup"><span data-stu-id="d0352-172">Resolution</span></span>  
 <span data-ttu-id="d0352-173">BizTalk 管理コンソールを閉じて再度開きます。</span><span class="sxs-lookup"><span data-stu-id="d0352-173">Close and reopen the BizTalk Administration console.</span></span> <span data-ttu-id="d0352-174">BizTalk 管理コンソールが再び開くと、指定した [!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)] 管理データベースとの接続が新たに作成されます。</span><span class="sxs-lookup"><span data-stu-id="d0352-174">When the BizTalk Administration console is reopened it creates a new connection to the specified [!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)] management database.</span></span>  
  
#### <a name="windows-group-names-that-were-previously-deleted-do-not-have-access-to-the-biztalk-server-databases"></a><span data-ttu-id="d0352-175">以前に削除した Windows グループ名で BizTalk Server データベースにアクセスできない</span><span class="sxs-lookup"><span data-stu-id="d0352-175">Windows group names that were previously deleted do not have access to the BizTalk Server databases</span></span>  
  
##### <a name="problem"></a><span data-ttu-id="d0352-176">問題</span><span class="sxs-lookup"><span data-stu-id="d0352-176">Problem</span></span>  
 <span data-ttu-id="d0352-177">[!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)] を再インストールする際に、以前に削除した Windows グループ名を使用すると、その Windows グループは BizTalk Server データベースにアクセスできません。</span><span class="sxs-lookup"><span data-stu-id="d0352-177">If, when reinstalling [!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)], you use a Windows group name that was previously deleted, the Windows group will not have access to the BizTalk Server databases.</span></span>  
  
##### <a name="cause"></a><span data-ttu-id="d0352-178">原因</span><span class="sxs-lookup"><span data-stu-id="d0352-178">Cause</span></span>  
 <span data-ttu-id="d0352-179">Windows グループを削除し、同じ名前で Windows グループを作成すると、その Windows グループ用に新しいセキュリティ識別子 (SID) が生成されますが、</span><span class="sxs-lookup"><span data-stu-id="d0352-179">Deleting a Windows group and then creating a Windows group with the same name produces a new Security Identifier (SID) for the Windows group.</span></span> <span data-ttu-id="d0352-180">以前の SID が SQL Server にキャッシュされたままであるため、新しい Windows グループは SQL Server にログオンできません。</span><span class="sxs-lookup"><span data-stu-id="d0352-180">However the old SID is still cached in SQL Server, so the new Windows group cannot log on to SQL Server.</span></span>  
  
##### <a name="resolution"></a><span data-ttu-id="d0352-181">解決策</span><span class="sxs-lookup"><span data-stu-id="d0352-181">Resolution</span></span>  
 <span data-ttu-id="d0352-182">Windows グループを削除するときは、その Windows グループの SQL Server ログインも削除する必要があります。</span><span class="sxs-lookup"><span data-stu-id="d0352-182">When you delete the Windows group, you must also remove the SQL Server login for the Windows group.</span></span>  
  
#### <a name="biztalk-administrator-cannot-start-the-biztalk-server-administration-console"></a><span data-ttu-id="d0352-183">BizTalk 管理者が BizTalk Server 管理コンソールを起動できない</span><span class="sxs-lookup"><span data-stu-id="d0352-183">BizTalk Administrator cannot start the BizTalk Server Administration console</span></span>  
  
##### <a name="problem"></a><span data-ttu-id="d0352-184">問題</span><span class="sxs-lookup"><span data-stu-id="d0352-184">Problem</span></span>  
 <span data-ttu-id="d0352-185">BizTalk 管理者 (BizTalk Administrators Windows グループのメンバー) がローカル コンピューターの Windows Administrators グループのメンバーでない場合、BizTalk Server 管理コンソールを開けないことがあります。</span><span class="sxs-lookup"><span data-stu-id="d0352-185">A BizTalk Administrator (member of the BizTalk Administrators Windows group) may not be able to open the BizTalk Server Administration console if that user is not a member of the Windows Administrators group on the local computer.</span></span>  
  
##### <a name="cause"></a><span data-ttu-id="d0352-186">原因</span><span class="sxs-lookup"><span data-stu-id="d0352-186">Cause</span></span>  
 <span data-ttu-id="d0352-187">この問題は、BizTalk Server を再インストールまたは再構成した場合に発生します。</span><span class="sxs-lookup"><span data-stu-id="d0352-187">This problem can occur if you have reinstalled or reconfigured BizTalk Server.</span></span> <span data-ttu-id="d0352-188">SQL Server がキャッシュされたセキュリティ ID を使用したことが原因です。</span><span class="sxs-lookup"><span data-stu-id="d0352-188">This is because SQL Server used cached security IDs.</span></span>  
  
##### <a name="resolution"></a><span data-ttu-id="d0352-189">解決策</span><span class="sxs-lookup"><span data-stu-id="d0352-189">Resolution</span></span>  
 <span data-ttu-id="d0352-190">BizTalk 管理者を、ローカル コンピューター上のローカル Windows Administrators グループに一時的に追加します。</span><span class="sxs-lookup"><span data-stu-id="d0352-190">Temporarily add the BizTalk Administrator to the local Windows Administrators group on the local computer.</span></span> <span data-ttu-id="d0352-191">BizTalk Server 管理コンソールが正常に開いたら、ローカル コンピューター上のローカル Windows Administrators グループから BizTalk 管理者を削除します。</span><span class="sxs-lookup"><span data-stu-id="d0352-191">After successfully opening the BizTalk Server Administration console, remove the BizTalk Administrator from the local Windows Administrators group on the local computer.</span></span>  
  
#### <a name="cannot-start-a-host-instance-on-a-remote-computer"></a><span data-ttu-id="d0352-192">リモート コンピューターでホスト インスタンスを起動できない</span><span class="sxs-lookup"><span data-stu-id="d0352-192">Cannot start a host instance on a remote computer</span></span>  
  
##### <a name="problem"></a><span data-ttu-id="d0352-193">問題</span><span class="sxs-lookup"><span data-stu-id="d0352-193">Problem</span></span>  
 <span data-ttu-id="d0352-194">BizTalk ホスト インスタンスを起動するときに、次のエラーを表示する可能性があります、リモート コンピューター上の BizTalk ホスト インスタンスを作成するときに:「ログオンに失敗したため開始できませんでした」。</span><span class="sxs-lookup"><span data-stu-id="d0352-194">When you create a BizTalk Host instance on a remote computer, you may see the following error when you start the BizTalk Host instance: "Failed to start due to logon failure."</span></span>  
  
##### <a name="cause"></a><span data-ttu-id="d0352-195">原因</span><span class="sxs-lookup"><span data-stu-id="d0352-195">Cause</span></span>  
 <span data-ttu-id="d0352-196">このエラーは、BizTalk ホスト インスタンスを実行しているサービス アカウントに無効な資格情報を入力した場合、またはそのサービス アカウントにサービスとしてログオンする権限がない場合に発生します。</span><span class="sxs-lookup"><span data-stu-id="d0352-196">This error can occur if you entered invalid credentials for the service account under which the BizTalk Host instance is running, or the service account does not have logon as service rights.</span></span>  
  
##### <a name="resolution"></a><span data-ttu-id="d0352-197">解決策</span><span class="sxs-lookup"><span data-stu-id="d0352-197">Resolution</span></span>  
 <span data-ttu-id="d0352-198">BizTalk ホスト インスタンスを起動する前に、リモート コンピューター内のサービス アカウントにサービスとしてログオンする権限を割り当てます。</span><span class="sxs-lookup"><span data-stu-id="d0352-198">Assign logon as a service right to the service account in the remote computer before you start the BizTalk Host instance.</span></span> <span data-ttu-id="d0352-199">ローカル コンピューターではこの処理が自動的に行われますが、リモート コンピューターでは手動で実行する必要があります。</span><span class="sxs-lookup"><span data-stu-id="d0352-199">This is done automatically on a local computer, but must be done manually on a remote computer.</span></span>  
  
#### <a name="creating-or-configuring-a-host-instance-on-an-x64-computer-with-the-32-bit-only-option-selected-fails"></a><span data-ttu-id="d0352-200">X64 コンピューターで [32 ビットのみ] オプションが選択または構成されていると、ホスト インスタンスの作成または構成が失敗する</span><span class="sxs-lookup"><span data-stu-id="d0352-200">Creating or configuring a host instance on an X64 computer with the 32-bit only option selected fails</span></span>  
  
##### <a name="problem"></a><span data-ttu-id="d0352-201">問題</span><span class="sxs-lookup"><span data-stu-id="d0352-201">Problem</span></span>  
 <span data-ttu-id="d0352-202">[!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)] 管理コンソールで [32 ビットのみ] オプション (既定) が選択されていると、X64 コンピューター上の BizTalk ホスト インスタンスの作成が失敗します。</span><span class="sxs-lookup"><span data-stu-id="d0352-202">In the [!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)] Administration Console, creating a BizTalk Host instance on an X64 computer with the 32-bit only option selected (default) may fail.</span></span>  
  
 <span data-ttu-id="d0352-203">BizTalk Server 構成マネージャーで、[32 ビットのみ] オプションを選択して、X64 コンピューターの BizTalk Server ランタイムの構成や、インプロセス ホスト インスタンスまたは分離ホスト インスタンスの作成を行うと、サービスの開始が失敗する可能性があります。</span><span class="sxs-lookup"><span data-stu-id="d0352-203">In BizTalk Server Configuration Manager, when configuring the BizTalk Server Runtime on an X64 computer, creating an in-process or isolated host instance with the 32-bit only option selected can cause the service to fail to start.</span></span>  
  
##### <a name="cause"></a><span data-ttu-id="d0352-204">原因</span><span class="sxs-lookup"><span data-stu-id="d0352-204">Cause</span></span>  
 <span data-ttu-id="d0352-205">Unknown</span><span class="sxs-lookup"><span data-stu-id="d0352-205">Unknown</span></span>  
  
##### <a name="resolution"></a><span data-ttu-id="d0352-206">解決策</span><span class="sxs-lookup"><span data-stu-id="d0352-206">Resolution</span></span>  
 <span data-ttu-id="d0352-207">この問題は断続的に発生します。</span><span class="sxs-lookup"><span data-stu-id="d0352-207">This issue is intermittent.</span></span> <span data-ttu-id="d0352-208">ホストの作成または構成を再度試みるか、[32 ビットのみ] オプションをオフにします。</span><span class="sxs-lookup"><span data-stu-id="d0352-208">Attempt to create or configure the host again or deselect the 32-bit only option.</span></span>  
  
#### <a name="host-instance-deletion-does-not-clear-registry-information"></a><span data-ttu-id="d0352-209">ホスト インスタンスを削除してもレジストリ情報が消去されない</span><span class="sxs-lookup"><span data-stu-id="d0352-209">Host instance deletion does not clear registry information</span></span>  
  
##### <a name="problem"></a><span data-ttu-id="d0352-210">問題</span><span class="sxs-lookup"><span data-stu-id="d0352-210">Problem</span></span>  
 <span data-ttu-id="d0352-211">ローカル コンピューターの管理者でないユーザーがインプロセス ホストまたは分離ホストを削除すると、アクセスが拒否されたことを通知するエラー メッセージが表示されます。</span><span class="sxs-lookup"><span data-stu-id="d0352-211">If you are not an administrator on the local computer, when you delete an in-process or isolated host, an access denied error message appears.</span></span> <span data-ttu-id="d0352-212">ホストは強制的に削除できますが、</span><span class="sxs-lookup"><span data-stu-id="d0352-212">You can forcibly delete the host.</span></span> <span data-ttu-id="d0352-213">この方法でホストを削除すると、関連するすべてのレジストリ情報が消去されません。</span><span class="sxs-lookup"><span data-stu-id="d0352-213">However, deleting the host in this manner does not clear all of the related registry information.</span></span>  
  
##### <a name="cause"></a><span data-ttu-id="d0352-214">原因</span><span class="sxs-lookup"><span data-stu-id="d0352-214">Cause</span></span>  
 <span data-ttu-id="d0352-215">ホスト インスタンスに関連するレジストリ情報を削除するには、管理者特権が必要です。</span><span class="sxs-lookup"><span data-stu-id="d0352-215">Deletion of the registry information related to a host instance requires Administrator privileges.</span></span>  
  
##### <a name="resolution"></a><span data-ttu-id="d0352-216">解決策</span><span class="sxs-lookup"><span data-stu-id="d0352-216">Resolution</span></span>  
 <span data-ttu-id="d0352-217">ローカル管理者アカウントでログオンしてホストを削除すると、関連するレジストリ情報も削除されます。</span><span class="sxs-lookup"><span data-stu-id="d0352-217">Log on as a local Administrator account before deleting the host so that the related registry information is also removed.</span></span>  
  
#### <a name="cannot-delete-a-messagebox-database"></a><span data-ttu-id="d0352-218">メッセージ ボックス データベースを削除できない</span><span class="sxs-lookup"><span data-stu-id="d0352-218">Cannot delete a MessageBox database</span></span>  
  
##### <a name="problem"></a><span data-ttu-id="d0352-219">問題</span><span class="sxs-lookup"><span data-stu-id="d0352-219">Problem</span></span>  
 <span data-ttu-id="d0352-220">メッセージ ボックス データベースを削除できない場合があります。</span><span class="sxs-lookup"><span data-stu-id="d0352-220">You may not be able to delete a MessageBox database.</span></span> <span data-ttu-id="d0352-221">削除に失敗した場合は、次のいずれかの問題が原因と考えられます。</span><span class="sxs-lookup"><span data-stu-id="d0352-221">If the deletion fails, one of the following issues may be responsible:</span></span>  
  
-   <span data-ttu-id="d0352-222">キャッシュ更新間隔に指定した時間が経過していない。</span><span class="sxs-lookup"><span data-stu-id="d0352-222">The cache refresh interval has not expired.</span></span>  
  
-   <span data-ttu-id="d0352-223">メッセージ ボックス データベースに不完全なインスタンスが含まれている。</span><span class="sxs-lookup"><span data-stu-id="d0352-223">The MessageBox database contains incomplete instances.</span></span>  
  
 <span data-ttu-id="d0352-224">削除に失敗したときにキャッシュ更新間隔まだ切れていない場合、次のエラー メッセージが表示されます:"メッセージ ボックスにがある可能性がある残存作業、メッセージ ボックスのため削除できません。</span><span class="sxs-lookup"><span data-stu-id="d0352-224">If the cache refresh interval has not yet expired, the following error message appears when the deletion fails: "MessageBox cannot be deleted since there could be remaining work in the MessageBox.</span></span> <span data-ttu-id="d0352-225">確認して、MessageBox になくなる不完全なインスタンスがあること、もう一度やり直してください。"</span><span class="sxs-lookup"><span data-stu-id="d0352-225">Please ensure that there are no more incomplete instances in the MessageBox, and try again."</span></span>  
  
##### <a name="cause"></a><span data-ttu-id="d0352-226">原因</span><span class="sxs-lookup"><span data-stu-id="d0352-226">Cause</span></span>  
 <span data-ttu-id="d0352-227">メッセージ ボックス データベースで新しいメッセージの公開を無効にしてからデータベースを削除するまでの間に、キャッシュ更新間隔に指定した時間が経過する必要があります。</span><span class="sxs-lookup"><span data-stu-id="d0352-227">The cache refresh interval must expire between the time you disable new message publication in the MessageBox database and the time you delete the database.</span></span> <span data-ttu-id="d0352-228">既定では、キャッシュ更新間隔は、60 秒です。</span><span class="sxs-lookup"><span data-stu-id="d0352-228">By default, the cache refresh interval is 60 seconds.</span></span>  
  
##### <a name="resolution"></a><span data-ttu-id="d0352-229">解決策</span><span class="sxs-lookup"><span data-stu-id="d0352-229">Resolution</span></span>  
 <span data-ttu-id="d0352-230">メッセージ ボックス データベースを削除するには、事前にそのメッセージ ボックス データベースについて新しいメッセージの公開を無効にし、キャッシュ更新間隔に指定した時間が経過するまで待つ必要があります。</span><span class="sxs-lookup"><span data-stu-id="d0352-230">To delete a MessageBox database, you must first disable new message publication for that MessageBox database, and then wait until the cache refresh interval expires, before you delete the MessageBox database.</span></span>  
  
 <span data-ttu-id="d0352-231">メッセージ ボックス データベースに不完全なサービス インスタンスが含まれている場合、次のエラー メッセージが表示されます:"、メッセージ ボックスには不完全なインスタンスがまだ含まれているために削除できません。</span><span class="sxs-lookup"><span data-stu-id="d0352-231">If the MessageBox database contains incomplete service instances, the following error message appears: "The MessageBox cannot be deleted because it may still contain incomplete instances.</span></span> <span data-ttu-id="d0352-232">メッセージ ボックスに不完全なインスタンスが存在しないことを確認して、再試行してください。" というエラー メッセージが表示されます。</span><span class="sxs-lookup"><span data-stu-id="d0352-232">Ensure that there are no incomplete instances in the MessageBox, and try again".</span></span>  
  
 <span data-ttu-id="d0352-233">BizTalk Server 管理コンソールの [グループ ハブ] ページを使用して、メッセージ ボックス データベースの不完全なサービス インスタンスを表示できます。</span><span class="sxs-lookup"><span data-stu-id="d0352-233">You can view incomplete service instances in the MessageBox database using the Group Hub page in the BizTalk Server Administration Console.</span></span> <span data-ttu-id="d0352-234">グループ ハブ ページでサービス インスタンスの状態を表示する方法については、次を参照してください。[追跡サービス インスタンスの検索方法](../core/how-to-search-for-tracked-service-instances.md)です。</span><span class="sxs-lookup"><span data-stu-id="d0352-234">For information about viewing the status of service instances in the Group Hub page, see [How to Search for Tracked Service Instances](../core/how-to-search-for-tracked-service-instances.md).</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="d0352-235">参照</span><span class="sxs-lookup"><span data-stu-id="d0352-235">See Also</span></span>  
 [<span data-ttu-id="d0352-236">トラブルシューティング</span><span class="sxs-lookup"><span data-stu-id="d0352-236">Troubleshooting</span></span>](../core/troubleshooting.md)