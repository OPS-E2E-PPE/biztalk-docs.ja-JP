---
title: "Services データベース、BAM 通知への参照を更新する方法 |Microsoft ドキュメント"
ms.custom: 
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: 
ms.suite: 
ms.tgt_pltfrm: 
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
caps.latest.revision: "16"
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: 394a002fedaffbb9c67fa4b0ae0229215e6d8efa
ms.sourcegitcommit: cb908c540d8f1a692d01dc8f313e16cb4b4e696d
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 09/20/2017
---
# <a name="how-to-update-references-to-the-bam-notification-services-databases"></a><span data-ttu-id="a3ac8-102">BAM Notification Services データベースの参照を更新する方法</span><span class="sxs-lookup"><span data-stu-id="a3ac8-102">How to Update References to the BAM Notification Services Databases</span></span>
<span data-ttu-id="a3ac8-103">送信先システムへのビジネス アクティビティの監視 (BAM) 通知サービス データベースを復元するために必要な手順が完了したら、Notification Services (NSservice.exe) を実行する [!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)] グループのすべてのコンピューターに Notification Services を再登録する必要があります。</span><span class="sxs-lookup"><span data-stu-id="a3ac8-103">After you perform the steps necessary to restore the Business Activity Monitoring (BAM) Notification Services databases to the destination system, you must re-register the Notification Service on all computers in the [!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)] group that are running Notification Services (NSservice.exe).</span></span> <span data-ttu-id="a3ac8-104">こうして初めて、Notification Services から新しい場所のデータベースに接続できるようになります。</span><span class="sxs-lookup"><span data-stu-id="a3ac8-104">This enables Notification Services to connect to the databases in their new location.</span></span>  
  
 <span data-ttu-id="a3ac8-105">Notification Services のインスタンスを再登録すると、NS$instance_name サービスが作成されるほか、ローカル サーバーにパフォーマンス カウンターが作成され、レジストリに情報が追加されます。</span><span class="sxs-lookup"><span data-stu-id="a3ac8-105">Registering an instance of Notification Services creates the NS$instance_name service, creates performance counters on the local server, and adds information to the registry.</span></span> <span data-ttu-id="a3ac8-106">インスタンスの登録が必要となるサーバーは次のとおりです。</span><span class="sxs-lookup"><span data-stu-id="a3ac8-106">You must register the instance on the following servers:</span></span>  
  
-   <span data-ttu-id="a3ac8-107">NS$instance_name サービスを実行するすべてのサーバー:</span><span class="sxs-lookup"><span data-stu-id="a3ac8-107">Each server that runs the NS$instance_name service.</span></span> <span data-ttu-id="a3ac8-108">このサービスは、イベント プロバイダー ホスト、ジェネレーター、およびディストリビューター コンポーネントを実行します。</span><span class="sxs-lookup"><span data-stu-id="a3ac8-108">The service runs the event provider host, generator, and distributor components.</span></span> <span data-ttu-id="a3ac8-109">スケールアウト構成の場合、このサービスは複数のサーバー上で実行されます。</span><span class="sxs-lookup"><span data-stu-id="a3ac8-109">For scaled-out configurations, the service runs on multiple servers.</span></span>  
  
-   <span data-ttu-id="a3ac8-110">サブスクリプション管理アプリケーションを実行するすべてのサーバー:</span><span class="sxs-lookup"><span data-stu-id="a3ac8-110">Each server that runs a subscription management application.</span></span> <span data-ttu-id="a3ac8-111">サブスクリプション管理アプリケーションが専用のサーバーで実行されている場合、インスタンスの登録時に NS$instance_name サービスは作成しないでください。</span><span class="sxs-lookup"><span data-stu-id="a3ac8-111">If the subscription management application runs on its own server, do not create the NS$instance_name service when registering the instance.</span></span>  
  
-   <span data-ttu-id="a3ac8-112">独立したイベント プロバイダーを実行するすべてのサーバー :</span><span class="sxs-lookup"><span data-stu-id="a3ac8-112">Each server that runs an independent event provider.</span></span> <span data-ttu-id="a3ac8-113">独立したイベント プロバイダーが専用のサーバーまたはデータベース サーバーで実行されている場合、インスタンスの登録時に NS$instance_name サービスは作成しないでください。</span><span class="sxs-lookup"><span data-stu-id="a3ac8-113">If the independent event provider runs on its own server or the database server, do not create the NS$instance_name service when registering the instance.</span></span>  
  
 <span data-ttu-id="a3ac8-114">Notification Services のインスタンスもクライアント コンポーネントも実行されていないデータベース サーバーには、インスタンスを登録しないでください。</span><span class="sxs-lookup"><span data-stu-id="a3ac8-114">If the database server does not also run the Notification Services instance or the client components, do not register the instance on this server.</span></span>  
  
## <a name="prerequisites"></a><span data-ttu-id="a3ac8-115">前提条件</span><span class="sxs-lookup"><span data-stu-id="a3ac8-115">Prerequisites</span></span>  
  
-   <span data-ttu-id="a3ac8-116">ここで示す手順を実行するには、管理者グループのメンバーとしてログオンする必要があります。</span><span class="sxs-lookup"><span data-stu-id="a3ac8-116">You must be logged on as a member of the Administrators group to perform this procedure.</span></span>  
  
-   <span data-ttu-id="a3ac8-117">BAM Notification Services データベースを復元するコンピューターに SQL Notification Services のビジネス アクティビティ監視 (BAM) 警告プロバイダーがインストールされている必要があります。</span><span class="sxs-lookup"><span data-stu-id="a3ac8-117">The Business Activity Monitoring (BAM) Alert Provider for SQL Notification Services must be installed on the computer where you are restoring the BAM Notification Services databases.</span></span>  
  
### <a name="to-update-references-to-the-bam-notification-services-databases-sql-server-2008-r2sp1"></a><span data-ttu-id="a3ac8-118">BAM Notification Services データベースの参照を更新するには (SQL Server 2008 R2/SP1)</span><span class="sxs-lookup"><span data-stu-id="a3ac8-118">To update references to the BAM Notification Services databases (SQL Server 2008 R2/SP1)</span></span>  
  
1.  <span data-ttu-id="a3ac8-119">をクリックして**開始**、 をクリックして**実行**、型**cmd**、順にクリック**ok**です。</span><span class="sxs-lookup"><span data-stu-id="a3ac8-119">Click **Start**, click **Run**, type **cmd**, and then click **OK**.</span></span>  
  
2.  <span data-ttu-id="a3ac8-120">コマンド プロンプトで、[!INCLUDE[btsBiztalkServerPath](../includes/btsbiztalkserverpath-md.md)]Tracking ディレクトリに移動します。</span><span class="sxs-lookup"><span data-stu-id="a3ac8-120">At the command prompt, navigate to the following directory: [!INCLUDE[btsBiztalkServerPath](../includes/btsbiztalkserverpath-md.md)]Tracking.</span></span>  
  
3.  <span data-ttu-id="a3ac8-121">型: **bm.exe get – filename:config.xml**</span><span class="sxs-lookup"><span data-stu-id="a3ac8-121">Type: **bm.exe get-config –filename:config.xml**</span></span>  
  
    > [!NOTE]
    >  <span data-ttu-id="a3ac8-122">ユーザー アカウント制御 (UAC) をサポートするシステムでは、管理者特権を使用してこのツールを実行することが必要な場合があります。</span><span class="sxs-lookup"><span data-stu-id="a3ac8-122">On a system that supports User Account Control (UAC), you may need to run the tool with Administrative privileges.</span></span>  
  
4.  <span data-ttu-id="a3ac8-123">手順 2. で作成した xml ファイルを開き、Notification Services の再登録が必要なコンピューターを確認します。</span><span class="sxs-lookup"><span data-stu-id="a3ac8-123">Open the xml file created in step 2 to obtain the list of the computers on which you must re-register Notification Services.</span></span>  
  
     <span data-ttu-id="a3ac8-124">コンピューターの名前が表示されている、 **\<プロパティ名\=>** 内のパラメーター、  **\<DeploymentUnit 名前 ="Alert">** xml のセクションファイル:</span><span class="sxs-lookup"><span data-stu-id="a3ac8-124">The computer names are listed in the **\<Property Name\=>** parameters in the **\<DeploymentUnit Name="Alert">** section of the xml file:</span></span>  
  
    ```  
    -<DeploymentUnit Name="Alert">  
    <Property Name="GeneratorServerName" />  
    <Property Name="ProviderServerName" />  
    <Property Name="DistributorServerName" />  
      </DeploymentUnit>  
    ```  
  
5.  <span data-ttu-id="a3ac8-125">この xml ファイルで確認した各コンピューターで NS サービスを停止し、Notification Services のインスタンスの登録を解除します。</span><span class="sxs-lookup"><span data-stu-id="a3ac8-125">On each computer listed in the xml file, stop the NS service and then unregister an instance of Notification Services:</span></span>  
  
    1.  <span data-ttu-id="a3ac8-126">をクリックして**開始**、 をクリックして**プログラム**、 をクリックして**Microsoft SQL Server 2008 R2**、 をクリックして**構成ツール**をクリックして**Notification Services コマンド プロンプト**です。</span><span class="sxs-lookup"><span data-stu-id="a3ac8-126">Click **Start**, click **Programs**, click **Microsoft SQL Server 2008 R2**, click **Configuration Tools**, and then click **Notification Services Command Prompt**.</span></span>  
  
    2.  <span data-ttu-id="a3ac8-127">コマンド プロンプトで次のように入力します: **net NS$ BamAlerts を停止する。**</span><span class="sxs-lookup"><span data-stu-id="a3ac8-127">At the command prompt, type: **net stop NS$BamAlerts**</span></span>  
  
    3.  <span data-ttu-id="a3ac8-128">次のコマンドを入力して、インスタンスの登録を解除します。</span><span class="sxs-lookup"><span data-stu-id="a3ac8-128">Type the following command to unregister the instance:</span></span>  
  
         <span data-ttu-id="a3ac8-129">**nscontrol unregister-name BamAlerts**</span><span class="sxs-lookup"><span data-stu-id="a3ac8-129">**nscontrol unregister  -name BamAlerts**</span></span>  
  
         <span data-ttu-id="a3ac8-130">インスタンスの登録を解除すると、レジストリのエントリが削除されるほか、NS$instance_name サービスも (存在する場合は) 削除されます。さらに、このサービスに対応するパフォーマンス カウンターも削除されます。</span><span class="sxs-lookup"><span data-stu-id="a3ac8-130">Unregistering an instance removes the registry entries, removes the NS$instance_name service (if present), and deletes the performance counters for the service.</span></span>  
  
6.  <span data-ttu-id="a3ac8-131">次の手順で Notification Services を再登録します。</span><span class="sxs-lookup"><span data-stu-id="a3ac8-131">Re-register the Notification Service:</span></span>  
  
    1.  <span data-ttu-id="a3ac8-132">をクリックして**開始**、 をクリックして**プログラム**、 をクリックして**Microsoft SQL Server 2008 R2**、 をクリックして**構成ツール**をクリックして**Notification Services コマンド プロンプト**です。</span><span class="sxs-lookup"><span data-stu-id="a3ac8-132">Click **Start**, click **Programs**, click **Microsoft SQL Server 2008 R2**, click **Configuration Tools**, and then click **Notification Services Command Prompt**.</span></span>  
  
    2.  <span data-ttu-id="a3ac8-133">コマンド プロンプトで次のように入力します: **nscontrol register-name BamAlerts-サーバー**  *\<ServerName >***-サービス - serviceusername"**  *。\<ServiceUserName >***"-servicepassword"***\<ServicePassword >***"**</span><span class="sxs-lookup"><span data-stu-id="a3ac8-133">At the command prompt, type: **nscontrol register -name BamAlerts -server** *\<ServerName>***-service -serviceusername "***\<ServiceUserName>***" -servicepassword "***\<ServicePassword>***"**</span></span>  
  
         <span data-ttu-id="a3ac8-134">これにより、Notification Services が適切なデータベースに接続できるようになります。この情報は、nscontrol により、サービス コンピューターのレジストリに格納されます。</span><span class="sxs-lookup"><span data-stu-id="a3ac8-134">This enables Notification Services to log on to the correct database (this information is maintained in the registry of the service machine by nscontrol).</span></span>  
  
        > [!IMPORTANT]
        >  <span data-ttu-id="a3ac8-135">新しい Notification Services データベース サーバーを使用してください、 **-サーバー**サービスの再登録オプションを選択します。</span><span class="sxs-lookup"><span data-stu-id="a3ac8-135">Remember to use the new Notification Services databases server in the **-server** option when re-registering the service.</span></span> <span data-ttu-id="a3ac8-136">また、新しい Notification Services サービスには、以前と同じユーザー名を使用する必要があります。</span><span class="sxs-lookup"><span data-stu-id="a3ac8-136">In addition, you should use the same user name for the new Notification Services service as the old one.</span></span>  
  
7.  <span data-ttu-id="a3ac8-137">BAM ポータルをホストするコンピューターでをクリックして**開始**、 をクリックして**プログラム**、 をクリックして**Microsoft SQL Server 2008 R2**、 をクリックして**の構成ツール**、クリックして**Notification Services コマンド プロンプト**です。</span><span class="sxs-lookup"><span data-stu-id="a3ac8-137">On the computer that hosts the BAM portal, click **Start**, click **Programs**, click **Microsoft SQL Server 2008 R2**, click **Configuration Tools**, and then click **Notification Services Command Prompt**.</span></span>  
  
8.  <span data-ttu-id="a3ac8-138">コマンド プロンプトで、次のように入力します。</span><span class="sxs-lookup"><span data-stu-id="a3ac8-138">At the command prompt, type:</span></span>  
  
     <span data-ttu-id="a3ac8-139">**net stop NS$ BamAlerts**</span><span class="sxs-lookup"><span data-stu-id="a3ac8-139">**net stop NS$BamAlerts**</span></span>  
  
9. <span data-ttu-id="a3ac8-140">コマンド プロンプトで、次のように入力します。</span><span class="sxs-lookup"><span data-stu-id="a3ac8-140">At the command prompt, type:</span></span>  
  
     <span data-ttu-id="a3ac8-141">**nscontrol unregister-name BamAlerts**</span><span class="sxs-lookup"><span data-stu-id="a3ac8-141">**nscontrol unregister  -name BamAlerts**</span></span>  
  
10. <span data-ttu-id="a3ac8-142">コマンド プロンプトで、次のように入力します。</span><span class="sxs-lookup"><span data-stu-id="a3ac8-142">At the command prompt, type:</span></span>  
  
     <span data-ttu-id="a3ac8-143">**nscontrol register 名前***\<BamAlerts >***-サーバー**  *\<NotificationServicesDatabaseServer >* </span><span class="sxs-lookup"><span data-stu-id="a3ac8-143">**nscontrol register  -name**  *\<BamAlerts>*  **-server** *\<NotificationServicesDatabaseServer>*</span></span>  
  
11. <span data-ttu-id="a3ac8-144">コマンド プロンプトで次のように入力します。: **「net start NS$ BamAlerts**です。</span><span class="sxs-lookup"><span data-stu-id="a3ac8-144">At the command prompt, type: **net start NS$BamAlerts**.</span></span>  
  
12. <span data-ttu-id="a3ac8-145">をクリックして**開始**、 をクリックして**実行**、型**cmd**、順にクリック**ok**です。</span><span class="sxs-lookup"><span data-stu-id="a3ac8-145">Click **Start**, click **Run**, type **cmd**, and then click **OK**.</span></span>  
  
13. <span data-ttu-id="a3ac8-146">コマンド プロンプトで、[!INCLUDE[btsBiztalkServerPath](../includes/btsbiztalkserverpath-md.md)]Tracking ディレクトリに移動します。</span><span class="sxs-lookup"><span data-stu-id="a3ac8-146">At the command prompt, navigate to the following directory: [!INCLUDE[btsBiztalkServerPath](../includes/btsbiztalkserverpath-md.md)]Tracking.</span></span>  
  
14. <span data-ttu-id="a3ac8-147">コマンド プロンプトで、次のように入力します。</span><span class="sxs-lookup"><span data-stu-id="a3ac8-147">At the command prompt, type:</span></span>  
  
     <span data-ttu-id="a3ac8-148">**bm.exe の更新プログラム – filename:config.xml**</span><span class="sxs-lookup"><span data-stu-id="a3ac8-148">**bm.exe update-config –FileName:config.xml**</span></span>  
  
    > [!NOTE]
    >  <span data-ttu-id="a3ac8-149">ユーザー アカウント制御 (UAC) をサポートするシステムでは、管理者特権を使用してこのツールを実行することが必要な場合があります。</span><span class="sxs-lookup"><span data-stu-id="a3ac8-149">On a system that supports User Account Control (UAC), you may need to run the tool with Administrative privileges.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="a3ac8-150">参照</span><span class="sxs-lookup"><span data-stu-id="a3ac8-150">See Also</span></span>  
 [<span data-ttu-id="a3ac8-151">バックアップおよび BAM を復元します。</span><span class="sxs-lookup"><span data-stu-id="a3ac8-151">Backing Up and Restoring BAM</span></span>](../core/backing-up-and-restoring-bam.md)