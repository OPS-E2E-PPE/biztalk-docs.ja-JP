---
title: Services データベース、BAM 通知への参照を更新する方法 |Microsoft Docs
ms.custom: ''
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: ''
ms.suite: ''
ms.tgt_pltfrm: ''
ms.topic: article
helpviewer_keywords:
- Notification Services Application database [BAM], restoring
- Notification Services Application database [BAM], updating references
- restoring, BAM
- NS$instance_name service Notification Services Application database [BAM], NS$instance_name service
- restoring [BAM], updating references
- BAM, restoring
- restoring [BAM], Notification Services Application database
- restoring [BAM], NS$instance_name service
ms.assetid: b007fdc2-2e74-4eef-b4c3-43689e9f2180
caps.latest.revision: 16
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: 93a285b770ce7f2ab20cc8865e7804e31141336f
ms.sourcegitcommit: 381e83d43796a345488d54b3f7413e11d56ad7be
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 05/07/2019
ms.locfileid: "65383637"
---
# <a name="how-to-update-references-to-the-bam-notification-services-databases"></a><span data-ttu-id="7a9df-102">BAM Notification Services データベースの参照を更新する方法</span><span class="sxs-lookup"><span data-stu-id="7a9df-102">How to Update References to the BAM Notification Services Databases</span></span>
<span data-ttu-id="7a9df-103">送信先システムにビジネス アクティビティ監視 (BAM) Notification Services データベースを復元するための手順を実行した後は、すべてのコンピューター上の通知サービスを再登録する必要があります、[!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)]実行しているグループNotification Services (NSservice.exe)。</span><span class="sxs-lookup"><span data-stu-id="7a9df-103">After you perform the steps necessary to restore the Business Activity Monitoring (BAM) Notification Services databases to the destination system, you must re-register the Notification Service on all computers in the [!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)] group that are running Notification Services (NSservice.exe).</span></span> <span data-ttu-id="7a9df-104">これにより、Notification Services の新しい場所にデータベースに接続できます。</span><span class="sxs-lookup"><span data-stu-id="7a9df-104">This enables Notification Services to connect to the databases in their new location.</span></span>  
  
 <span data-ttu-id="7a9df-105">Notification Services のインスタンスを登録すると、NS $instance_name サービスを作成します、ローカルのサーバーでパフォーマンス カウンターを作成し、レジストリに情報を追加します。</span><span class="sxs-lookup"><span data-stu-id="7a9df-105">Registering an instance of Notification Services creates the NS$instance_name service, creates performance counters on the local server, and adds information to the registry.</span></span> <span data-ttu-id="7a9df-106">次のサーバー インスタンスを登録する必要があります。</span><span class="sxs-lookup"><span data-stu-id="7a9df-106">You must register the instance on the following servers:</span></span>  
  
- <span data-ttu-id="7a9df-107">NS $instance_name サービスを実行する各サーバー。</span><span class="sxs-lookup"><span data-stu-id="7a9df-107">Each server that runs the NS$instance_name service.</span></span> <span data-ttu-id="7a9df-108">サービスでは、ホスト、ジェネレーター、およびディストリビューター コンポーネント イベント プロバイダーを実行します。</span><span class="sxs-lookup"><span data-stu-id="7a9df-108">The service runs the event provider host, generator, and distributor components.</span></span> <span data-ttu-id="7a9df-109">スケール アウト構成では、サービスは、複数のサーバーで実行されます。</span><span class="sxs-lookup"><span data-stu-id="7a9df-109">For scaled-out configurations, the service runs on multiple servers.</span></span>  
  
- <span data-ttu-id="7a9df-110">サブスクリプションの管理アプリケーションを実行する各サーバー。</span><span class="sxs-lookup"><span data-stu-id="7a9df-110">Each server that runs a subscription management application.</span></span> <span data-ttu-id="7a9df-111">サブスクリプション管理アプリケーションは、独自のサーバーで実行する場合は作成できません、NS $instance_name サービス インスタンスを登録するときに。</span><span class="sxs-lookup"><span data-stu-id="7a9df-111">If the subscription management application runs on its own server, do not create the NS$instance_name service when registering the instance.</span></span>  
  
- <span data-ttu-id="7a9df-112">独立したイベント プロバイダーを実行する各サーバー。</span><span class="sxs-lookup"><span data-stu-id="7a9df-112">Each server that runs an independent event provider.</span></span> <span data-ttu-id="7a9df-113">独立したイベント プロバイダーは、独自のサーバーまたはデータベース サーバーで実行する場合は作成できません NS $instance_name サービス インスタンスを登録するときにします。</span><span class="sxs-lookup"><span data-stu-id="7a9df-113">If the independent event provider runs on its own server or the database server, do not create the NS$instance_name service when registering the instance.</span></span>  
  
  <span data-ttu-id="7a9df-114">データベース サーバーが実行されない場合も、Notification Services インスタンスまたはクライアント コンポーネントでは、このサーバーのインスタンスを登録できません。</span><span class="sxs-lookup"><span data-stu-id="7a9df-114">If the database server does not also run the Notification Services instance or the client components, do not register the instance on this server.</span></span>  
  
## <a name="prerequisites"></a><span data-ttu-id="7a9df-115">前提条件</span><span class="sxs-lookup"><span data-stu-id="7a9df-115">Prerequisites</span></span>  
  
-   <span data-ttu-id="7a9df-116">ここで示す手順を実行するには、管理者グループのメンバーとしてログオンする必要があります。</span><span class="sxs-lookup"><span data-stu-id="7a9df-116">You must be logged on as a member of the Administrators group to perform this procedure.</span></span>  
  
-   <span data-ttu-id="7a9df-117">SQL Notification Services 用ビジネス アクティビティ監視 (BAM) 警告プロバイダーは、BAM Notification Services データベースを復元するコンピューターにインストールする必要があります。</span><span class="sxs-lookup"><span data-stu-id="7a9df-117">The Business Activity Monitoring (BAM) Alert Provider for SQL Notification Services must be installed on the computer where you are restoring the BAM Notification Services databases.</span></span>  
  
### <a name="to-update-references-to-the-bam-notification-services-databases-sql-server-2008-r2sp1"></a><span data-ttu-id="7a9df-118">BAM Notification Services データベース (SQL Server 2008 R2 SP1) への参照を更新するには</span><span class="sxs-lookup"><span data-stu-id="7a9df-118">To update references to the BAM Notification Services databases (SQL Server 2008 R2/SP1)</span></span>  
  
1. <span data-ttu-id="7a9df-119">をクリックして**開始**、 をクリックして**実行**、型**cmd**、順にクリックします**OK**。</span><span class="sxs-lookup"><span data-stu-id="7a9df-119">Click **Start**, click **Run**, type **cmd**, and then click **OK**.</span></span>  
  
2. <span data-ttu-id="7a9df-120">コマンド プロンプトで、次のディレクトリに移動します[!INCLUDE[btsBiztalkServerPath](../includes/btsbiztalkserverpath-md.md)]追跡します。</span><span class="sxs-lookup"><span data-stu-id="7a9df-120">At the command prompt, navigate to the following directory: [!INCLUDE[btsBiztalkServerPath](../includes/btsbiztalkserverpath-md.md)]Tracking.</span></span>  
  
3. <span data-ttu-id="7a9df-121">Type: **bm.exe get-config –filename:config.xml**</span><span class="sxs-lookup"><span data-stu-id="7a9df-121">Type: **bm.exe get-config –filename:config.xml**</span></span>  
  
   > [!NOTE]
   >  <span data-ttu-id="7a9df-122">ユーザー アカウント制御 (UAC) をサポートするシステムでは、管理者特権を使用してこのツールを実行することが必要な場合があります。</span><span class="sxs-lookup"><span data-stu-id="7a9df-122">On a system that supports User Account Control (UAC), you may need to run the tool with Administrative privileges.</span></span>  
  
4. <span data-ttu-id="7a9df-123">これには、Notification Services 再登録する必要があります、コンピューターの一覧を取得する 2 の手順で作成した xml ファイルを開きます。</span><span class="sxs-lookup"><span data-stu-id="7a9df-123">Open the xml file created in step 2 to obtain the list of the computers on which you must re-register Notification Services.</span></span>  
  
    <span data-ttu-id="7a9df-124">コンピューター名が記載されて、 **\<プロパティ名\=\>** 内のパラメーター、 **\<DeploymentUnit 名前 ="Alert"\>** xml ファイルのセクション:</span><span class="sxs-lookup"><span data-stu-id="7a9df-124">The computer names are listed in the **\<Property Name\=\>** parameters in the **\<DeploymentUnit Name="Alert"\>** section of the xml file:</span></span>  
  
   ```  
   -<DeploymentUnit Name="Alert">  
   <Property Name="GeneratorServerName" />  
   <Property Name="ProviderServerName" />  
   <Property Name="DistributorServerName" />  
     </DeploymentUnit>  
   ```  
  
5. <span data-ttu-id="7a9df-125">Xml ファイルに記載の各コンピューターで NS サービスを停止し、Notification Services のインスタンスの登録を解除します。</span><span class="sxs-lookup"><span data-stu-id="7a9df-125">On each computer listed in the xml file, stop the NS service and then unregister an instance of Notification Services:</span></span>  
  
   1.  <span data-ttu-id="7a9df-126">をクリックして**開始**、 をクリックして**プログラム**、 をクリックして**Microsoft SQL Server 2008 R2**、 をクリックして**構成ツール**をクリックして**Notification Services コマンド プロンプト**します。</span><span class="sxs-lookup"><span data-stu-id="7a9df-126">Click **Start**, click **Programs**, click **Microsoft SQL Server 2008 R2**, click **Configuration Tools**, and then click **Notification Services Command Prompt**.</span></span>  
  
   2.  <span data-ttu-id="7a9df-127">コマンド プロンプトで「: **net NS$ BamAlerts を停止します。**</span><span class="sxs-lookup"><span data-stu-id="7a9df-127">At the command prompt, type: **net stop NS$BamAlerts**</span></span>  
  
   3.  <span data-ttu-id="7a9df-128">インスタンスの登録を解除するには、次のコマンドを入力します。</span><span class="sxs-lookup"><span data-stu-id="7a9df-128">Type the following command to unregister the instance:</span></span>  
  
        <span data-ttu-id="7a9df-129">**nscontrol unregister-name BamAlerts**</span><span class="sxs-lookup"><span data-stu-id="7a9df-129">**nscontrol unregister  -name BamAlerts**</span></span>  
  
        <span data-ttu-id="7a9df-130">インスタンスの登録を解除すると、レジストリのエントリが削除されるほか、NS$instance_name サービスも (存在する場合は) 削除されます。さらに、このサービスに対応するパフォーマンス カウンターも削除されます。</span><span class="sxs-lookup"><span data-stu-id="7a9df-130">Unregistering an instance removes the registry entries, removes the NS$instance_name service (if present), and deletes the performance counters for the service.</span></span>  
  
6. <span data-ttu-id="7a9df-131">通知サービスを再登録します。</span><span class="sxs-lookup"><span data-stu-id="7a9df-131">Re-register the Notification Service:</span></span>  
  
   1.  <span data-ttu-id="7a9df-132">をクリックして**開始**、 をクリックして**プログラム**、 をクリックして**Microsoft SQL Server 2008 R2**、 をクリックして**構成ツール**をクリックして**Notification Services コマンド プロンプト**します。</span><span class="sxs-lookup"><span data-stu-id="7a9df-132">Click **Start**, click **Programs**, click **Microsoft SQL Server 2008 R2**, click **Configuration Tools**, and then click **Notification Services Command Prompt**.</span></span>  
  
   2.  <span data-ttu-id="7a9df-133">コマンド プロンプトで「: **nscontrol register-name BamAlerts-サーバー**  *\<ServerName\>\*\*\*-service - serviceusername"*\*\* \<ServiceUserName\>***"-servicepassword"***\<ServicePassword\>\* \* *"*\*</span><span class="sxs-lookup"><span data-stu-id="7a9df-133">At the command prompt, type: **nscontrol register -name BamAlerts -server** *\<ServerName\>***-service -serviceusername "***\<ServiceUserName\>***" -servicepassword "***\<ServicePassword\>\*\*\*"*\*</span></span>  
  
        <span data-ttu-id="7a9df-134">これにより、Notification Services が適切なデータベース (この情報は、nscontrol により、サービス コンピューターのレジストリに保持) にログオンできます。</span><span class="sxs-lookup"><span data-stu-id="7a9df-134">This enables Notification Services to log on to the correct database (this information is maintained in the registry of the service machine by nscontrol).</span></span>  
  
       > [!IMPORTANT]
       >  <span data-ttu-id="7a9df-135">新しい Notification Services データベース サーバーを使用して、忘れず、 **-サーバー**サービスを再登録するときのオプションします。</span><span class="sxs-lookup"><span data-stu-id="7a9df-135">Remember to use the new Notification Services databases server in the **-server** option when re-registering the service.</span></span> <span data-ttu-id="7a9df-136">さらに、古いものと、新しい Notification Services サービスの同じユーザー名を使用する必要があります。</span><span class="sxs-lookup"><span data-stu-id="7a9df-136">In addition, you should use the same user name for the new Notification Services service as the old one.</span></span>  
  
7. <span data-ttu-id="7a9df-137">BAM ポータルをホストするコンピューターで次のようにクリックします**開始**、 をクリック**プログラム**、 をクリック**Microsoft SQL Server 2008 R2**、 をクリック**構成ツール。**、 をクリックし、 **Notification Services コマンド プロンプト**します。</span><span class="sxs-lookup"><span data-stu-id="7a9df-137">On the computer that hosts the BAM portal, click **Start**, click **Programs**, click **Microsoft SQL Server 2008 R2**, click **Configuration Tools**, and then click **Notification Services Command Prompt**.</span></span>  
  
8. <span data-ttu-id="7a9df-138">コマンド プロンプトで、次のように入力します。</span><span class="sxs-lookup"><span data-stu-id="7a9df-138">At the command prompt, type:</span></span>  
  
    <span data-ttu-id="7a9df-139">**net stop NS$BamAlerts**</span><span class="sxs-lookup"><span data-stu-id="7a9df-139">**net stop NS$BamAlerts**</span></span>  
  
9. <span data-ttu-id="7a9df-140">コマンド プロンプトで、次のように入力します。</span><span class="sxs-lookup"><span data-stu-id="7a9df-140">At the command prompt, type:</span></span>  
  
     <span data-ttu-id="7a9df-141">**nscontrol unregister-name BamAlerts**</span><span class="sxs-lookup"><span data-stu-id="7a9df-141">**nscontrol unregister  -name BamAlerts**</span></span>  
  
10. <span data-ttu-id="7a9df-142">コマンド プロンプトで、次のように入力します。</span><span class="sxs-lookup"><span data-stu-id="7a9df-142">At the command prompt, type:</span></span>  
  
     <span data-ttu-id="7a9df-143">**nscontrol register 名前***\<BamAlerts\>***-サーバー**  *\<NotificationServicesDatabaseServer\>*</span><span class="sxs-lookup"><span data-stu-id="7a9df-143">**nscontrol register  -name**  *\<BamAlerts\>*  **-server** *\<NotificationServicesDatabaseServer\>*</span></span>  
  
11. <span data-ttu-id="7a9df-144">コマンド プロンプトで「:**開始 NS$ BamAlerts を net**します。</span><span class="sxs-lookup"><span data-stu-id="7a9df-144">At the command prompt, type: **net start NS$BamAlerts**.</span></span>  
  
12. <span data-ttu-id="7a9df-145">をクリックして**開始**、 をクリックして**実行**、型**cmd**、順にクリックします**OK**。</span><span class="sxs-lookup"><span data-stu-id="7a9df-145">Click **Start**, click **Run**, type **cmd**, and then click **OK**.</span></span>  
  
13. <span data-ttu-id="7a9df-146">コマンド プロンプトで、次のディレクトリに移動します[!INCLUDE[btsBiztalkServerPath](../includes/btsbiztalkserverpath-md.md)]追跡します。</span><span class="sxs-lookup"><span data-stu-id="7a9df-146">At the command prompt, navigate to the following directory: [!INCLUDE[btsBiztalkServerPath](../includes/btsbiztalkserverpath-md.md)]Tracking.</span></span>  
  
14. <span data-ttu-id="7a9df-147">コマンド プロンプトで、次のように入力します。</span><span class="sxs-lookup"><span data-stu-id="7a9df-147">At the command prompt, type:</span></span>  
  
     <span data-ttu-id="7a9df-148">**bm.exe update-config –FileName:config.xml**</span><span class="sxs-lookup"><span data-stu-id="7a9df-148">**bm.exe update-config –FileName:config.xml**</span></span>  
  
    > [!NOTE]
    >  <span data-ttu-id="7a9df-149">ユーザー アカウント制御 (UAC) をサポートするシステムでは、管理者特権を使用してこのツールを実行することが必要な場合があります。</span><span class="sxs-lookup"><span data-stu-id="7a9df-149">On a system that supports User Account Control (UAC), you may need to run the tool with Administrative privileges.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="7a9df-150">参照</span><span class="sxs-lookup"><span data-stu-id="7a9df-150">See Also</span></span>  
 [<span data-ttu-id="7a9df-151">BAM のバックアップと復元</span><span class="sxs-lookup"><span data-stu-id="7a9df-151">Backing Up and Restoring BAM</span></span>](../core/backing-up-and-restoring-bam.md)