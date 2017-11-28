---
title: "管理者用の BAM タスク |Microsoft ドキュメント"
ms.custom: 
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: 
ms.suite: 
ms.tgt_pltfrm: 
ms.topic: article
ms.assetid: 2d9ae9a6-50fa-4f82-8e48-8dffa55c127f
caps.latest.revision: "33"
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: 4b529a0510ee56a92d3957a84a91d635666016f1
ms.sourcegitcommit: cb908c540d8f1a692d01dc8f313e16cb4b4e696d
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 09/20/2017
---
# <a name="bam-tasks-for-administrators"></a><span data-ttu-id="6b450-102">管理者の BAM タスク</span><span class="sxs-lookup"><span data-stu-id="6b450-102">BAM Tasks for Administrators</span></span>
<span data-ttu-id="6b450-103">このトピックでは、BAM インフラストラクチャを管理する際に BAM 管理者が実行する一般的なタスクについて説明します。</span><span class="sxs-lookup"><span data-stu-id="6b450-103">This topic describes typical tasks that BAM administrators undertake in managing the BAM infrastructure.</span></span>  
  
## <a name="configuring-bam"></a><span data-ttu-id="6b450-104">BAM の構成</span><span class="sxs-lookup"><span data-stu-id="6b450-104">Configuring BAM</span></span>  
 <span data-ttu-id="6b450-105">BAM の初期構成は、[!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)] 構成ウィザードを使用して行います。</span><span class="sxs-lookup"><span data-stu-id="6b450-105">The initial configuration of BAM is done using the [!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)] Configuration Wizard.</span></span> <span data-ttu-id="6b450-106">この構成ウィザードを使用すると、管理者は次の操作を実行できます。</span><span class="sxs-lookup"><span data-stu-id="6b450-106">Using the configuration wizard administrators can:</span></span>  
  
-   <span data-ttu-id="6b450-107">ビジネス アクティビティの監視ツールを有効にする</span><span class="sxs-lookup"><span data-stu-id="6b450-107">Enable Business Activity Monitoring tools</span></span>  
  
-   <span data-ttu-id="6b450-108">BAM 集計用に SQL Server Analysis Services を有効にする</span><span class="sxs-lookup"><span data-stu-id="6b450-108">Enable SQL Server Analysis Services for BAM aggregations</span></span>  
  
-   <span data-ttu-id="6b450-109">BAM ツールに使用するサーバー名とデータベースを指定する</span><span class="sxs-lookup"><span data-stu-id="6b450-109">Specify the server name and databases used for BAM tools</span></span>  
  
-   <span data-ttu-id="6b450-110">BAM 警告の SQL Server Notification Services を有効にする</span><span class="sxs-lookup"><span data-stu-id="6b450-110">Enable SQL Server Notification Services for BAM alerts</span></span>  
  
-   <span data-ttu-id="6b450-111">BAM Notification Service の実行に使用するアカウントを指定する</span><span class="sxs-lookup"><span data-stu-id="6b450-111">Specify the account used to run the BAM Notification service</span></span>  
  
-   <span data-ttu-id="6b450-112">BAM 警告の送信に使用する SMTP サーバーを指定する</span><span class="sxs-lookup"><span data-stu-id="6b450-112">Specify the SMTP server that is used to send BAM alerts</span></span>  
  
-   <span data-ttu-id="6b450-113">BAM 警告の格納に使用するファイルの場所を指定する</span><span class="sxs-lookup"><span data-stu-id="6b450-113">Specify the file location used to store BAM alerts</span></span>  
  
-   <span data-ttu-id="6b450-114">BAM 警告データベースが存在する SQL Server の名前を指定する</span><span class="sxs-lookup"><span data-stu-id="6b450-114">Specify the name of SQL server on which the BAM alerts databases resides</span></span>  
  
-   <span data-ttu-id="6b450-115">警告データベース名のプレフィックスを指定する</span><span class="sxs-lookup"><span data-stu-id="6b450-115">Specify the prefix for alerts database names</span></span>  
  
-   <span data-ttu-id="6b450-116">コンピューターで BAM ポータルを有効にする</span><span class="sxs-lookup"><span data-stu-id="6b450-116">Enable the BAM portal on a computer</span></span>  
  
-   <span data-ttu-id="6b450-117">BAM ポータルの実行に使用する Web サービス アカウントを指定する</span><span class="sxs-lookup"><span data-stu-id="6b450-117">Specify the Web service accounts used to run the BAM portal</span></span>  
  
-   <span data-ttu-id="6b450-118">BAM ポータルにアクセスできる Windows グループを指定する</span><span class="sxs-lookup"><span data-stu-id="6b450-118">Specify the Windows groups that can access the BAM portal</span></span>  
  
-   <span data-ttu-id="6b450-119">BAM ポータル Web サイトの場所を指定する</span><span class="sxs-lookup"><span data-stu-id="6b450-119">Specify the location of the BAM portal Web site</span></span>  
  
 <span data-ttu-id="6b450-120">この構成ウィザードの使用に関する詳細については、次のトピックを参照してください。</span><span class="sxs-lookup"><span data-stu-id="6b450-120">For more information about using the configuration wizard see the following topics:</span></span>  
  
-   [<span data-ttu-id="6b450-121">BizTalk Server 構成を使用して BAM 警告の構成</span><span class="sxs-lookup"><span data-stu-id="6b450-121">Configuring BAM Alerts Using the BizTalk Server Configuration</span></span>](http://msdn.microsoft.com/library/04d79f8c-9e7f-4ba8-83ce-f79c33fb8e60)  
  
-   [<span data-ttu-id="6b450-122">BizTalk Server 構成を使用して BAM ツールを構成します。</span><span class="sxs-lookup"><span data-stu-id="6b450-122">Configuring BAM Tools Using the BizTalk Server Configuration</span></span>](http://msdn.microsoft.com/library/075a1627-5bc2-488c-a88c-42c86cc8c3bb)  
  
-   [<span data-ttu-id="6b450-123">BizTalk Server 構成を使用して BAM ポータルを構成します。</span><span class="sxs-lookup"><span data-stu-id="6b450-123">Configuring the BAM Portal Using the BizTalk Server Configuration</span></span>](http://msdn.microsoft.com/library/8af7cccb-823e-48bd-9743-dfbba4bafa11)  
  
### <a name="distributed-notification-services"></a><span data-ttu-id="6b450-124">分散された Notification Services</span><span class="sxs-lookup"><span data-stu-id="6b450-124">Distributed Notification Services</span></span>  
 <span data-ttu-id="6b450-125">BAM が分散環境で実行されるように構成すると、警告や通知を処理するときにパフォーマンスが向上します。</span><span class="sxs-lookup"><span data-stu-id="6b450-125">Configuring BAM to run in a distributed environment affords performance benefits when processing alerts and notifications.</span></span> <span data-ttu-id="6b450-126">このような BAM 構成では、Notification Services のプロバイダー、ジェネレーター、ディストリビューターの各ロールを異なるコンピューターに配置するため、Notification Services を複数のコンピューター環境にインストールする必要があります。</span><span class="sxs-lookup"><span data-stu-id="6b450-126">When you do this, the Provider, Generator, and Distributor roles of Notification Services are on different computers and you must install Notification Services in the multiple computer environment.</span></span>  
  
##### <a name="to-configure-distributed-notification-services"></a><span data-ttu-id="6b450-127">分散された Notification Services を構成するには</span><span class="sxs-lookup"><span data-stu-id="6b450-127">To configure distributed Notification Services</span></span>  
  
1.  <span data-ttu-id="6b450-128">[!INCLUDE[btsSQLServer2005](../includes/btssqlserver2005-md.md)] Notification Services をインストールします。</span><span class="sxs-lookup"><span data-stu-id="6b450-128">Install the [!INCLUDE[btsSQLServer2005](../includes/btssqlserver2005-md.md)] Notification Services.</span></span> <span data-ttu-id="6b450-129">分散された Notification Services の詳細については、次を参照してください。、 [!INCLUDE[btsSQLServer2005](../includes/btssqlserver2005-md.md)] Notification Services のマニュアル[http://go.microsoft.com/fwlink/?LinkId=68095](http://go.microsoft.com/fwlink/?LinkId=68095)です。</span><span class="sxs-lookup"><span data-stu-id="6b450-129">For more information about Distributed Notification Services, see the [!INCLUDE[btsSQLServer2005](../includes/btssqlserver2005-md.md)] Notification Services documentation at [http://go.microsoft.com/fwlink/?LinkId=68095](http://go.microsoft.com/fwlink/?LinkId=68095).</span></span>  
  
    > [!NOTE]
    >  <span data-ttu-id="6b450-130">Notification Services は含まれていない[!INCLUDE[btsSQLServer2008](../includes/btssqlserver2008-md.md)]です。</span><span class="sxs-lookup"><span data-stu-id="6b450-130">Notification Services is not included in [!INCLUDE[btsSQLServer2008](../includes/btssqlserver2008-md.md)].</span></span> <span data-ttu-id="6b450-131">使用している場合[!INCLUDE[btsSQLServer2008](../includes/btssqlserver2008-md.md)]、インストール[!INCLUDE[btsSQLServerNoVersion](../includes/btssqlservernoversion-md.md)]Notification Services をインストールするときに[!INCLUDE[btsBizTalkServer2006r3](../includes/btsbiztalkserver2006r3-md.md)]を選択して、 **SQL Notification Services 用 BAM 警告プロバイダー**オプションで **追加ソフトウェア**上、**コンポーネントのインストール**インストール ウィザードのページです。</span><span class="sxs-lookup"><span data-stu-id="6b450-131">If you are using [!INCLUDE[btsSQLServer2008](../includes/btssqlserver2008-md.md)], install [!INCLUDE[btsSQLServerNoVersion](../includes/btssqlservernoversion-md.md)] Notification Services when you install [!INCLUDE[btsBizTalkServer2006r3](../includes/btsbiztalkserver2006r3-md.md)] by selecting the **BAM Alert Provider for SQL Notification Services** option under **Additional Software** on the **Component Installation** page of the installation wizard.</span></span>  
  
2.  <span data-ttu-id="6b450-132">BAM 通知を作成する、C:\Program files \microsoft SQL Server\90\NotificationServices\9.0.242\bin\nscontrol の実行の分散環境では、各コンピューター上のサービス名の登録 - bamalerts-サーバー\<サーバー名 > - サービス -serviceusername\<警告ユーザー アカウント >-servicepassword \<passwd > コマンド プロンプトからです。</span><span class="sxs-lookup"><span data-stu-id="6b450-132">To create the BAM notification service on each computer in the distributed environment run C:\Program Files\Microsoft SQL Server\90\NotificationServices\9.0.242\bin\nscontrol register -name bamalerts -server \<server name> -service -serviceusername \<alertsuseraccount> -servicepassword \<passwd> from a command prompt.</span></span>  
  
3.  <span data-ttu-id="6b450-133">各コンピューターで、分散された Notifications Services 用に構成されている BAM インフラストラクチャ構成ファイルを編集します。</span><span class="sxs-lookup"><span data-stu-id="6b450-133">Edit the BAM infrastructure configuration file on each computer being configured for distributed Notifications Serviced.</span></span> <span data-ttu-id="6b450-134">構成ファイルを取得するを使用して、 **bm.exe get config ファイル名:\<出力ファイル >**コマンド。</span><span class="sxs-lookup"><span data-stu-id="6b450-134">To get the configuration file, use the **bm.exe get-config -FileName:\<output file>** command.</span></span>  
  
4.  <span data-ttu-id="6b450-135">構成ファイルを編集し、分散された Notification Services 環境でサーバーを参照します。</span><span class="sxs-lookup"><span data-stu-id="6b450-135">Edit the configuration file to reference the servers in the distributed Notification services environment:</span></span>  
  
    ```  
    <Property Name="GeneratorServerName">PFIDWYUK</Property>  
    <Property Name="ProviderServerName">PFIDWYUK</Property>  
    <Property Name="DistributorServerName">PFIDWYUK</Property>  
    ```  
  
5.  <span data-ttu-id="6b450-136">Bm.exe の更新プログラムの構成を使用するファイル名:\<構成ファイル > BAM 構成を更新します。</span><span class="sxs-lookup"><span data-stu-id="6b450-136">Use the bm.exe update-config -FileName:\<config file> to update the BAM configuration.</span></span>  
  
6.  <span data-ttu-id="6b450-137">分散環境のすべてのコンピューターで、Notification Services を再起動します。</span><span class="sxs-lookup"><span data-stu-id="6b450-137">Restart the Notification Services on all the computers in the distributed environment.</span></span>  
  
 <span data-ttu-id="6b450-138">複数コンピューター環境で BAM をインストールする方法の詳細については、次を参照してください[関連するインストール ガイドを BizTalk Server 2013](http://go.microsoft.com/fwlink/p/?LinkID=269582)と[のインストールと構成での BAM (ビジネス アクティビティ監視) 複数のコンピューター。環境](http://go.microsoft.com/fwlink/p/?LinkID=208597)です。</span><span class="sxs-lookup"><span data-stu-id="6b450-138">For more information on installing BAM in a multicomputer environment, see [Installation Guides Related to BizTalk Server 2013](http://go.microsoft.com/fwlink/p/?LinkID=269582) and [Install and Configure BAM (Business Activity Monitoring) in a Multi-Computer Environment](http://go.microsoft.com/fwlink/p/?LinkID=208597).</span></span>  
  
### <a name="moving-the-bam-primary-import-database"></a><span data-ttu-id="6b450-139">BAM プライマリ インポート データベースの移動</span><span class="sxs-lookup"><span data-stu-id="6b450-139">Moving the BAM Primary Import Database</span></span>  
 <span data-ttu-id="6b450-140">ハードウェアのアップグレードやスケールアップを行うときなど、ある時点で BAM プライマリ インポート データベースの移動が必要になる場合があります。</span><span class="sxs-lookup"><span data-stu-id="6b450-140">At some point it may become necessary to move the BAM Primary Import database, such as when you are upgrading hardware or scaling up operations.</span></span> <span data-ttu-id="6b450-141">データベースを移動するには、バックアップ操作と復元操作を実行します。</span><span class="sxs-lookup"><span data-stu-id="6b450-141">To move the database you perform a backup and restore operation.</span></span> <span data-ttu-id="6b450-142">このプロセスの詳細については、次を参照してください。[をバックアップおよび復元する BAM](../core/backing-up-and-restoring-bam.md)です。</span><span class="sxs-lookup"><span data-stu-id="6b450-142">For more information about this process, see [Backing Up and Restoring BAM](../core/backing-up-and-restoring-bam.md).</span></span>  
  
### <a name="working-with-bam-definitions"></a><span data-ttu-id="6b450-143">BAM 定義の操作</span><span class="sxs-lookup"><span data-stu-id="6b450-143">Working with BAM Definitions</span></span>  
 <span data-ttu-id="6b450-144">管理者は BAM 定義と密接にかかわっています。</span><span class="sxs-lookup"><span data-stu-id="6b450-144">Administrators work closely with BAM definitions.</span></span> <span data-ttu-id="6b450-145">BAM 定義の操作に使用する主なツールは BAM 管理ユーティリティです。</span><span class="sxs-lookup"><span data-stu-id="6b450-145">The primary tool you use to work with BAM definitions is the BAM Management utility.</span></span> <span data-ttu-id="6b450-146">このユーティリティを使用すると、次のタスクを実行できます。</span><span class="sxs-lookup"><span data-stu-id="6b450-146">You can perform the following tasks by using this utility:</span></span>  
  
-   <span data-ttu-id="6b450-147">アクティビティを変更する。</span><span class="sxs-lookup"><span data-stu-id="6b450-147">Changing activities.</span></span> <span data-ttu-id="6b450-148">使用することができます、**展開すべて**、**更新すべて**、**削除アクティビティ**、 **set-actvitywindow** BAM 管理ユーティリティのコマンド展開済みのアクティビティを変更します。</span><span class="sxs-lookup"><span data-stu-id="6b450-148">You can use the **deploy-all**, **update-all**, **remove-activity**, **and set-actvitywindow** commands of the BAM management utility to change your deployed activities.</span></span>  
  
-   <span data-ttu-id="6b450-149">アクティビティ テーブルにインデックスを適用してパフォーマンスを向上する。</span><span class="sxs-lookup"><span data-stu-id="6b450-149">Applying indexes to activity tables to enhance performance.</span></span> <span data-ttu-id="6b450-150">使用する、**インデックスの作成**と**delete インデックス**アクティビティのインデックスを変更するコマンド。</span><span class="sxs-lookup"><span data-stu-id="6b450-150">You use the **create-index** and **delete-index** commands to modify the indexes on activities.</span></span>  
  
-   <span data-ttu-id="6b450-151">ビューにセキュリティを設定する。</span><span class="sxs-lookup"><span data-stu-id="6b450-151">Setting security on views.</span></span> <span data-ttu-id="6b450-152">使用することができます、**アカウントの追加**と**削除アカウント**ユーザーに付与するためのコマンドにアクセス権をビュー。</span><span class="sxs-lookup"><span data-stu-id="6b450-152">You can use the **add-account** and **remove-account** commands to grant users access rights to views.</span></span>  
  
-   <span data-ttu-id="6b450-153">アクティビティの分散ナビゲーションを構成する。</span><span class="sxs-lookup"><span data-stu-id="6b450-153">Configuring distributed navigation of activities.</span></span> <span data-ttu-id="6b450-154">使用する、**参照を有効にする**と**無効参照**アクティビティの分散ナビゲーションを設定するコマンド。</span><span class="sxs-lookup"><span data-stu-id="6b450-154">You use the **enable-reference** and **disable-reference** commands to configure distributed navigation of activities.</span></span> <span data-ttu-id="6b450-155">アクティビティの分散ナビゲーションの詳細については、次を参照してください。[管理分散ナビゲーションのリモート アクティビティ](../core/managing-distributed-navigation-of-remote-activities.md)です。</span><span class="sxs-lookup"><span data-stu-id="6b450-155">For more information about the distributed navigation of activities, see [Managing Distributed Navigation of Remote Activities](../core/managing-distributed-navigation-of-remote-activities.md).</span></span>  
  
-   <span data-ttu-id="6b450-156">変更を監査する。</span><span class="sxs-lookup"><span data-stu-id="6b450-156">Auditing changes.</span></span> <span data-ttu-id="6b450-157">BAM 動的インフラストラクチャを使用して、変更の一覧を表示することができます、 **get 変更**コマンド。</span><span class="sxs-lookup"><span data-stu-id="6b450-157">You can list changes to the BAM dynamic infrastructure using the **get-changes** command.</span></span>  
  
 <span data-ttu-id="6b450-158">BAM 管理ユーティリティで使用可能なすべてのコマンドの説明は、次を参照してください。 [BAM 管理ユーティリティ](../core/bam-management-utility.md)です。</span><span class="sxs-lookup"><span data-stu-id="6b450-158">For a description of all the commands available through the BAM Management utility, see [BAM Management Utility](../core/bam-management-utility.md).</span></span> <span data-ttu-id="6b450-159">BAM 管理ユーティリティを使用した BAM 定義の操作の例については、次を参照してください。 [BAM 動的インフラストラクチャを管理する](../core/managing-the-bam-dynamic-infrastructure.md)です。</span><span class="sxs-lookup"><span data-stu-id="6b450-159">For examples of using the BAM Management utility to work with BAM definitions, see [Managing the BAM Dynamic Infrastructure](../core/managing-the-bam-dynamic-infrastructure.md).</span></span>  
  
## <a name="configuring-multiple-biztalk-groups-to-reference-a-single-bam-database"></a><span data-ttu-id="6b450-160">1 つの BAM データベースを参照する複数の BizTalk グループの構成</span><span class="sxs-lookup"><span data-stu-id="6b450-160">Configuring Multiple BizTalk Groups to Reference a Single BAM Database</span></span>  
 <span data-ttu-id="6b450-161">新しいまたは既存のいずれかを使用する BAM を構成するときに[!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)]グループ、既に別の使用されている同じ BAM データベースを使用するグループを構成することができます[!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)]グループ。</span><span class="sxs-lookup"><span data-stu-id="6b450-161">When configuring BAM to use either a new or an existing [!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)] group, you can configure the group to use the same BAM databases that are already in use by another [!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)] group.</span></span>  <span data-ttu-id="6b450-162">この方法で BAM を構成するには、次のタスクを行う必要があります。</span><span class="sxs-lookup"><span data-stu-id="6b450-162">To configure BAM in this manner, you must perform the following tasks:</span></span>  
  
-   <span data-ttu-id="6b450-163">[!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)] 構成ウィザードを使用して、既存の BAM プライマリ インポート データベースから構成情報を取得します。</span><span class="sxs-lookup"><span data-stu-id="6b450-163">Get the configuration information from the existing BAM Primary Import database using the [!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)] Configuration Wizard.</span></span> <span data-ttu-id="6b450-164">構成情報には、サーバー名とデータベース名が含まれます。</span><span class="sxs-lookup"><span data-stu-id="6b450-164">This includes the server and database names.</span></span> <span data-ttu-id="6b450-165">チェック ボックスの状態に注意してください。</span><span class="sxs-lookup"><span data-stu-id="6b450-165">Note the state of the check boxes.</span></span> <span data-ttu-id="6b450-166">[BAM ツール] ページと [BAM 警告] ページの両方の構成情報を取得するようにしてください。</span><span class="sxs-lookup"><span data-stu-id="6b450-166">Be sure to get the configuration information for both the BAM Tools and BAM Alerts pages.</span></span>  
  
-   <span data-ttu-id="6b450-167">新しいグループに BAM を構成し、対象のプライマリ インポート テーブル (PIT) 用に構成されている情報を正確に入力します。</span><span class="sxs-lookup"><span data-stu-id="6b450-167">Configure BAM for the new group, and enter the exact information as configured already for the target PIT.</span></span> <span data-ttu-id="6b450-168">新しいグループの構成情報を入力するときに、既存のグループから収集されたすべての情報を使用して、新しいグループを構成します。ただし、BAM 警告ユーザーについては空白のままにする必要があります。</span><span class="sxs-lookup"><span data-stu-id="6b450-168">When entering the configuration information for the new group you will use all the information collected from the existing group to configure the new group, except the BAM Alerts user, which you must leave blank.</span></span>  
  
## <a name="backing-up-and-restoring-bam"></a><span data-ttu-id="6b450-169">BAM のバックアップと復元</span><span class="sxs-lookup"><span data-stu-id="6b450-169">Backing Up and Restoring BAM</span></span>  
 <span data-ttu-id="6b450-170">管理者は、ディザスター リカバリーの状況に備えて計画を行う必要があります。</span><span class="sxs-lookup"><span data-stu-id="6b450-170">Administrators should plan for disaster recovery situations.</span></span> <span data-ttu-id="6b450-171">BAM 分析、追跡分析、BAM スター スキーマ、BAM アーカイブ、および BAM プライマリ インポート データベースをバックアップして、これらを復元する状況に備える必要があります。</span><span class="sxs-lookup"><span data-stu-id="6b450-171">You should back up the BAM Analysis, Tracking Analysis, BAM Star Schema, BAM Archive, and BAM Primary Import databases to provide for situations in which you must restore them.</span></span>  <span data-ttu-id="6b450-172">バックアップして、BAM データベースの復元については、次を参照してください。[をバックアップおよび復元する BAM](../core/backing-up-and-restoring-bam.md)です。</span><span class="sxs-lookup"><span data-stu-id="6b450-172">For information about backing up and restoring the BAM databases, see [Backing Up and Restoring BAM](../core/backing-up-and-restoring-bam.md).</span></span>  
  
## <a name="working-with-renamed-servers"></a><span data-ttu-id="6b450-173">名前を変更したサーバーの操作</span><span class="sxs-lookup"><span data-stu-id="6b450-173">Working with Renamed Servers</span></span>  
 <span data-ttu-id="6b450-174">サーバーの名前を変更するか、BAM インフラストラクチャをサーバー間で移動するとき、Excel ブックで BAM 定義を更新して、Excel ブックを更新する必要があります。</span><span class="sxs-lookup"><span data-stu-id="6b450-174">When you rename a server or move the BAM infrastructure between servers, you must update the Excel workbook by updating the BAM definitions in that workbook.</span></span>  
  
 <span data-ttu-id="6b450-175">次のようなシナリオで、ブックの更新が必要になります。</span><span class="sxs-lookup"><span data-stu-id="6b450-175">The scenarios in which you would need to update the workbook include:</span></span>  
  
-   <span data-ttu-id="6b450-176">BAM インフラストラクチャを新しいデータベースに移動するステージング シナリオ。</span><span class="sxs-lookup"><span data-stu-id="6b450-176">A staging scenario, in which you move the BAM infrastructure to a new database.</span></span> <span data-ttu-id="6b450-177">Excel ブックが機能していることを確認するには、ブックを再展開または移行してから再び更新する必要があります。</span><span class="sxs-lookup"><span data-stu-id="6b450-177">To ensure that the Excel workbooks are still functional, you must redeploy or migrate and then re-update the workbooks.</span></span>  
  
-   <span data-ttu-id="6b450-178">BizTalk Server を実行しているコンピューターの名前を変更するシナリオ。</span><span class="sxs-lookup"><span data-stu-id="6b450-178">A scenario in which you rename the computer running BizTalk Server.</span></span> <span data-ttu-id="6b450-179">これは、DTS パッケージおよびブックの更新だけでなく OLAP データ ソースの更新が必要です。</span><span class="sxs-lookup"><span data-stu-id="6b450-179">This requires updating the DTS packages and OLAP data source in addition to updating the workbook.</span></span>  
  
 <span data-ttu-id="6b450-180">Excel ブックの更新には、次の 2 つの手法があります。</span><span class="sxs-lookup"><span data-stu-id="6b450-180">There are two approaches you can use to update the Excel workbook:</span></span>  
  
-   <span data-ttu-id="6b450-181">新しいサーバーから、次の BAM マネージャー コマンドを実行します。</span><span class="sxs-lookup"><span data-stu-id="6b450-181">Run the following BAM Manager command from the new server:</span></span>  
  
     <span data-ttu-id="6b450-182">**bm.exe 更新 livedataworkbook-名前:\<update.xls をライブ データ ブック >**</span><span class="sxs-lookup"><span data-stu-id="6b450-182">**bm.exe update-livedataworkbook -Name:\<livedata workbook to update.xls>**</span></span>  
  
    > [!NOTE]
    >  <span data-ttu-id="6b450-183">新しいサーバー名および BAM プライマリ インポート データベース名を指定することもできます: **bm.exe 更新 livedataworkbook-名前:\<update.xls をライブ データ ブック > [-サーバー:\<サーバー >] [-データベース:\<データベース >]**</span><span class="sxs-lookup"><span data-stu-id="6b450-183">You can also specify the new server name and/or BAM Primary Import database name: **bm.exe update-livedataworkbook -Name:\<livedata workbook to update.xls> [-Server:\<server>] [-Database:\<database>]**</span></span>  
  
-   <span data-ttu-id="6b450-184">または、この Excel ブックを Excel 内で更新します。</span><span class="sxs-lookup"><span data-stu-id="6b450-184">Alternatively, you can update the Excel workbook from within Excel:</span></span>  
  
    1.  <span data-ttu-id="6b450-185">更新するブックを開きます。</span><span class="sxs-lookup"><span data-stu-id="6b450-185">Open the workbook you want to update.</span></span>  
  
    2.  <span data-ttu-id="6b450-186">BAM メニューから  **BAM データベースの接続**です。</span><span class="sxs-lookup"><span data-stu-id="6b450-186">From the BAM menu, click **BAM Db Connection**.</span></span>  
  
    3.  <span data-ttu-id="6b450-187">新しいサーバーおよび BAM プライマリ インポート データベースの名前を入力します。</span><span class="sxs-lookup"><span data-stu-id="6b450-187">Enter the new server name and BAM Primary Import database name.</span></span>  
  
## <a name="managing-alerts"></a><span data-ttu-id="6b450-188">警告の管理</span><span class="sxs-lookup"><span data-stu-id="6b450-188">Managing Alerts</span></span>  
 <span data-ttu-id="6b450-189">管理者は、いくつかの方法で警告を管理することができます。</span><span class="sxs-lookup"><span data-stu-id="6b450-189">Administrators can manage alerts in a several ways:</span></span>  
  
 <span data-ttu-id="6b450-190">BAM 管理ユーティリティを使用して、警告の展開と削除を実行できます。</span><span class="sxs-lookup"><span data-stu-id="6b450-190">You can use the BAM Management utility to deploy and remove alerts.</span></span> <span data-ttu-id="6b450-191">このユーティリティは、警告の有効化と無効化だけでなく、サブスクリプションの追加と削除にも使用できます。</span><span class="sxs-lookup"><span data-stu-id="6b450-191">You can also use the utility to add and remove subscriptions, as well as to enable and disable alerts.</span></span> <span data-ttu-id="6b450-192">詳細については、BAM 管理ユーティリティを使用して、次を参照してください。 [BAM 管理ユーティリティ](../core/bam-management-utility.md)、 [BAM セキュリティを管理する](../core/managing-bam-security.md)、および[BAM 定義を管理する](../core/managing-bam-definitions.md)です。</span><span class="sxs-lookup"><span data-stu-id="6b450-192">For more information about using the BAM Management utility, see [BAM Management Utility](../core/bam-management-utility.md), [Managing BAM Security](../core/managing-bam-security.md), and [Managing BAM Definitions](../core/managing-bam-definitions.md).</span></span>  
  
 <span data-ttu-id="6b450-193">BAM ポータルを使用して、警告の作成や削除を行うこともできます。</span><span class="sxs-lookup"><span data-stu-id="6b450-193">You can also create and remove alerts through the BAM portal.</span></span>  <span data-ttu-id="6b450-194">BAM ポータルを使用して警告を作成する方法の詳細については、次を参照してください。 [BAM ポータルでのアクティビティの検索](../core/activity-searches-in-the-bam-portal.md)です。</span><span class="sxs-lookup"><span data-stu-id="6b450-194">For information about creating alerts using the BAM portal, see [Activity Searches in the BAM Portal](../core/activity-searches-in-the-bam-portal.md).</span></span>  
  
### <a name="cleaning-up-the-alerts-chronicle-table"></a><span data-ttu-id="6b450-195">警告記録テーブルのクリーンアップ</span><span class="sxs-lookup"><span data-stu-id="6b450-195">Cleaning up the Alerts Chronicle table</span></span>  
 <span data-ttu-id="6b450-196">BAM 警告が構成されている場合、作成される各アクティビティ ビューに対して SQL ジョブが作成されます。</span><span class="sxs-lookup"><span data-stu-id="6b450-196">If BAM alerts are configured, a SQL job is created for each activity view that is created.</span></span> <span data-ttu-id="6b450-197">次のテンプレートを使用して、ジョブに名前が付けられます。</span><span class="sxs-lookup"><span data-stu-id="6b450-197">The job will be named using the following template:</span></span>  
  
 <span data-ttu-id="6b450-198">bam _\<ビュー名 > _\<アクティビティ ビュー > _DelAlertHistJob</span><span class="sxs-lookup"><span data-stu-id="6b450-198">bam_\<View Name>_\<Activity View>_DelAlertHistJob</span></span>  
  
 <span data-ttu-id="6b450-199">このジョブに指定されたインスタンス警告に対する監査データをクリーンアップ\<アクティビティ ビュー > は Bam_Metadata_AlertChronicle テーブルにします。</span><span class="sxs-lookup"><span data-stu-id="6b450-199">This job cleans up auditing data for the instance alerts for the specified \<Activity View> in the Bam_Metadata_AlertChronicle table.</span></span> <span data-ttu-id="6b450-200">特定のアクティビティ ビューにインスタンス警告を定義した場合、警告が発生するたびに、このテーブルに新しい行が追加されます。</span><span class="sxs-lookup"><span data-stu-id="6b450-200">If you have defined instance alerts on the particular activity view, a new row will be added to this table every time the alert is fired.</span></span>  
  
 <span data-ttu-id="6b450-201">テーブルをクリーンアップするために、ジョブは手動で実行することも、アプリケーションや環境に応じて実行されるようにスケジュールすることもできます。</span><span class="sxs-lookup"><span data-stu-id="6b450-201">You can run this job manually to clean up the table or schedule it to run according to the need of your application or environment.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="6b450-202">参照</span><span class="sxs-lookup"><span data-stu-id="6b450-202">See Also</span></span>  
 [<span data-ttu-id="6b450-203">BAM の管理</span><span class="sxs-lookup"><span data-stu-id="6b450-203">Managing BAM</span></span>](../core/managing-bam.md)