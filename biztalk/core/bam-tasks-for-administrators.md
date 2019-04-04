---
title: 管理者の BAM タスク |Microsoft Docs
ms.custom: ''
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: ''
ms.suite: ''
ms.tgt_pltfrm: ''
ms.topic: article
ms.assetid: 2d9ae9a6-50fa-4f82-8e48-8dffa55c127f
caps.latest.revision: 33
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: 742eeffd496eaf43fbdd809f2610f2af64d04251
ms.sourcegitcommit: 266308ec5c6a9d8d80ff298ee6051b4843c5d626
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 06/27/2018
ms.locfileid: "36996363"
---
# <a name="bam-tasks-for-administrators"></a><span data-ttu-id="bd8f9-102">管理者の BAM タスク</span><span class="sxs-lookup"><span data-stu-id="bd8f9-102">BAM Tasks for Administrators</span></span>
<span data-ttu-id="bd8f9-103">このトピックでは、BAM インフラストラクチャを管理する際に BAM 管理者が実行する一般的なタスクについて説明します。</span><span class="sxs-lookup"><span data-stu-id="bd8f9-103">This topic describes typical tasks that BAM administrators undertake in managing the BAM infrastructure.</span></span>  
  
## <a name="configuring-bam"></a><span data-ttu-id="bd8f9-104">BAM の構成</span><span class="sxs-lookup"><span data-stu-id="bd8f9-104">Configuring BAM</span></span>  
 <span data-ttu-id="bd8f9-105">BAM の初期構成が完了したら、BizTalk Server 構成ウィザードを使用します。</span><span class="sxs-lookup"><span data-stu-id="bd8f9-105">The initial configuration of BAM is done using the BizTalk Server Configuration Wizard.</span></span> <span data-ttu-id="bd8f9-106">この構成ウィザードを使用すると、管理者は次の操作を実行できます。</span><span class="sxs-lookup"><span data-stu-id="bd8f9-106">Using the configuration wizard administrators can:</span></span>  
  
- <span data-ttu-id="bd8f9-107">ビジネス アクティビティの監視ツールを有効にする</span><span class="sxs-lookup"><span data-stu-id="bd8f9-107">Enable Business Activity Monitoring tools</span></span>  
  
- <span data-ttu-id="bd8f9-108">BAM 集計用に SQL Server Analysis Services を有効にする</span><span class="sxs-lookup"><span data-stu-id="bd8f9-108">Enable SQL Server Analysis Services for BAM aggregations</span></span>  
  
- <span data-ttu-id="bd8f9-109">BAM ツールに使用するサーバー名とデータベースを指定する</span><span class="sxs-lookup"><span data-stu-id="bd8f9-109">Specify the server name and databases used for BAM tools</span></span>  
  
- <span data-ttu-id="bd8f9-110">BAM 警告の SQL Server Notification Services を有効にする</span><span class="sxs-lookup"><span data-stu-id="bd8f9-110">Enable SQL Server Notification Services for BAM alerts</span></span>  
  
- <span data-ttu-id="bd8f9-111">BAM Notification Service の実行に使用するアカウントを指定する</span><span class="sxs-lookup"><span data-stu-id="bd8f9-111">Specify the account used to run the BAM Notification service</span></span>  
  
- <span data-ttu-id="bd8f9-112">BAM 警告の送信に使用する SMTP サーバーを指定する</span><span class="sxs-lookup"><span data-stu-id="bd8f9-112">Specify the SMTP server that is used to send BAM alerts</span></span>  
  
- <span data-ttu-id="bd8f9-113">BAM 警告の格納に使用するファイルの場所を指定する</span><span class="sxs-lookup"><span data-stu-id="bd8f9-113">Specify the file location used to store BAM alerts</span></span>  
  
- <span data-ttu-id="bd8f9-114">BAM 警告データベースが存在する SQL Server の名前を指定する</span><span class="sxs-lookup"><span data-stu-id="bd8f9-114">Specify the name of SQL server on which the BAM alerts databases resides</span></span>  
  
- <span data-ttu-id="bd8f9-115">警告データベース名のプレフィックスを指定する</span><span class="sxs-lookup"><span data-stu-id="bd8f9-115">Specify the prefix for alerts database names</span></span>  
  
- <span data-ttu-id="bd8f9-116">コンピューターで BAM ポータルを有効にする</span><span class="sxs-lookup"><span data-stu-id="bd8f9-116">Enable the BAM portal on a computer</span></span>  
  
- <span data-ttu-id="bd8f9-117">BAM ポータルの実行に使用する Web サービス アカウントを指定する</span><span class="sxs-lookup"><span data-stu-id="bd8f9-117">Specify the Web service accounts used to run the BAM portal</span></span>  
  
- <span data-ttu-id="bd8f9-118">BAM ポータルにアクセスできる Windows グループを指定する</span><span class="sxs-lookup"><span data-stu-id="bd8f9-118">Specify the Windows groups that can access the BAM portal</span></span>  
  
- <span data-ttu-id="bd8f9-119">BAM ポータル Web サイトの場所を指定する</span><span class="sxs-lookup"><span data-stu-id="bd8f9-119">Specify the location of the BAM portal Web site</span></span>  
  
  <span data-ttu-id="bd8f9-120">この構成ウィザードの使用に関する詳細については、次のトピックを参照してください。</span><span class="sxs-lookup"><span data-stu-id="bd8f9-120">For more information about using the configuration wizard see the following topics:</span></span>  
  
- [<span data-ttu-id="bd8f9-121">BAM 警告を構成します。</span><span class="sxs-lookup"><span data-stu-id="bd8f9-121">Configure BAM Alerts</span></span>](../install-and-config-guides/configure-biztalk-server.md)  
  
- [<span data-ttu-id="bd8f9-122">BAM ツールを構成します。</span><span class="sxs-lookup"><span data-stu-id="bd8f9-122">Configure BAM Tools</span></span>](../install-and-config-guides/configure-biztalk-server.md)  
  
- [<span data-ttu-id="bd8f9-123">BAM ポータルを構成します。</span><span class="sxs-lookup"><span data-stu-id="bd8f9-123">Configure the BAM Portal</span></span>](../install-and-config-guides/configure-biztalk-server.md)  
  
### <a name="distributed-notification-services---sql-server-2008-r2-only"></a><span data-ttu-id="bd8f9-124">分散された Notification Services の SQL Server 2008 R2 のみ</span><span class="sxs-lookup"><span data-stu-id="bd8f9-124">Distributed Notification Services - SQL Server 2008 R2 only</span></span>
<span data-ttu-id="bd8f9-125">BAM が分散環境で実行されるように構成すると、警告や通知を処理するときにパフォーマンスが向上します。</span><span class="sxs-lookup"><span data-stu-id="bd8f9-125">Configuring BAM to run in a distributed environment affords performance benefits when processing alerts and notifications.</span></span> <span data-ttu-id="bd8f9-126">このような BAM 構成では、Notification Services のプロバイダー、ジェネレーター、ディストリビューターの各ロールを異なるコンピューターに配置するため、Notification Services を複数のコンピューター環境にインストールする必要があります。</span><span class="sxs-lookup"><span data-stu-id="bd8f9-126">When you do this, the Provider, Generator, and Distributor roles of Notification Services are on different computers and you must install Notification Services in the multiple computer environment.</span></span>  

> [!NOTE]
> <span data-ttu-id="bd8f9-127">SQL Server 2012 以降では、BizTalk Server は、SQL Database Mail を使用します。</span><span class="sxs-lookup"><span data-stu-id="bd8f9-127">Starting with SQL Server 2012, BizTalk Server uses SQL Database Mail.</span></span> <span data-ttu-id="bd8f9-128">SQL Server 2012 を使用している場合、またはそれ以降にこれは適用されません。</span><span class="sxs-lookup"><span data-stu-id="bd8f9-128">So if you're using SQL Server 2012 or newer, this does not apply to you.</span></span> <span data-ttu-id="bd8f9-129">参照してください[BAM 警告](../install-and-config-guides/prepare-your-computer-for-installation.md#BKMK_BAMAlerts)のガイダンスについてはします。</span><span class="sxs-lookup"><span data-stu-id="bd8f9-129">See [BAM Alerts](../install-and-config-guides/prepare-your-computer-for-installation.md#BKMK_BAMAlerts) for guidance.</span></span>
  
##### <a name="to-configure-distributed-notification-services"></a><span data-ttu-id="bd8f9-130">分散された Notification Services を構成するには</span><span class="sxs-lookup"><span data-stu-id="bd8f9-130">To configure distributed Notification Services</span></span>  
  
1. <span data-ttu-id="bd8f9-131">SQL Server Notification Services をインストールします。</span><span class="sxs-lookup"><span data-stu-id="bd8f9-131">Install SQL Server Notification Services.</span></span> 
  
   > [!NOTE]
   >  <span data-ttu-id="bd8f9-132">SQL Server では、notification Services が含まれていません。</span><span class="sxs-lookup"><span data-stu-id="bd8f9-132">Notification Services is not included in SQL Server.</span></span> <span data-ttu-id="bd8f9-133">選択して BizTalk Server をインストールするときに、SQL Server Notification Services をインストール、 **SQL Notification Services 用 BAM 警告プロバイダー**オプションで **追加ソフトウェア**上、 **コンポーネントのインストール**インストール ウィザードのページ。</span><span class="sxs-lookup"><span data-stu-id="bd8f9-133">Install SQL Server Notification Services when you install BizTalk Server by selecting the **BAM Alert Provider for SQL Notification Services** option under **Additional Software** on the **Component Installation** page of the installation wizard.</span></span>  
  
2. <span data-ttu-id="bd8f9-134">BAM 通知を作成する C:\Program files \microsoft SQL Server\90\NotificationServices\9.0.242\bin\nscontrol を実行する分散環境では、各コンピューター上のサービス名を登録 - bamalerts-サーバー\<サーバー名\>-サービス - serviceusername\<警告ユーザー アカウント\>-servicepassword \<passwd\>コマンド プロンプトからです。</span><span class="sxs-lookup"><span data-stu-id="bd8f9-134">To create the BAM notification service on each computer in the distributed environment run C:\Program Files\Microsoft SQL Server\90\NotificationServices\9.0.242\bin\nscontrol register -name bamalerts -server \<server name\> -service -serviceusername \<alertsuseraccount\> -servicepassword \<passwd\> from a command prompt.</span></span>  
  
3. <span data-ttu-id="bd8f9-135">各コンピューターで、分散された Notifications Services 用に構成されている BAM インフラストラクチャ構成ファイルを編集します。</span><span class="sxs-lookup"><span data-stu-id="bd8f9-135">Edit the BAM infrastructure configuration file on each computer being configured for distributed Notifications Serviced.</span></span> <span data-ttu-id="bd8f9-136">構成ファイルを取得する、 **bm.exe config の取得のファイル名:\<出力ファイル\>** コマンド。</span><span class="sxs-lookup"><span data-stu-id="bd8f9-136">To get the configuration file, use the **bm.exe get-config -FileName:\<output file\>** command.</span></span>  
  
4. <span data-ttu-id="bd8f9-137">構成ファイルを編集し、分散された Notification Services 環境でサーバーを参照します。</span><span class="sxs-lookup"><span data-stu-id="bd8f9-137">Edit the configuration file to reference the servers in the distributed Notification services environment:</span></span>  
  
   ```  
   <Property Name="GeneratorServerName">PFIDWYUK</Property>  
   <Property Name="ProviderServerName">PFIDWYUK</Property>  
   <Property Name="DistributorServerName">PFIDWYUK</Property>  
   ```  
  
5. <span data-ttu-id="bd8f9-138">更新プログラムの config の bm.exe を使用してファイル名:\<config ファイル\>BAM 構成を更新します。</span><span class="sxs-lookup"><span data-stu-id="bd8f9-138">Use the bm.exe update-config -FileName:\<config file\> to update the BAM configuration.</span></span>  
  
6. <span data-ttu-id="bd8f9-139">分散環境のすべてのコンピューターで、Notification Services を再起動します。</span><span class="sxs-lookup"><span data-stu-id="bd8f9-139">Restart the Notification Services on all the computers in the distributed environment.</span></span>  
  
   <span data-ttu-id="bd8f9-140">複数コンピューター環境で BAM をインストールする方法の詳細については、[BAM インストールおよび構成 (ビジネス アクティビティ監視)、複数コンピューター環境で](http://go.microsoft.com/fwlink/p/?LinkID=208597)を参照してください。</span><span class="sxs-lookup"><span data-stu-id="bd8f9-140">For more information on installing BAM in a multicomputer environment, see [Install and Configure BAM (Business Activity Monitoring) in a Multi-Computer Environment](http://go.microsoft.com/fwlink/p/?LinkID=208597).</span></span>  
  
### <a name="moving-the-bam-primary-import-database"></a><span data-ttu-id="bd8f9-141">BAM プライマリ インポート データベースの移動</span><span class="sxs-lookup"><span data-stu-id="bd8f9-141">Moving the BAM Primary Import Database</span></span>  
 <span data-ttu-id="bd8f9-142">ハードウェアのアップグレードやスケールアップを行うときなど、ある時点で BAM プライマリ インポート データベースの移動が必要になる場合があります。</span><span class="sxs-lookup"><span data-stu-id="bd8f9-142">At some point it may become necessary to move the BAM Primary Import database, such as when you are upgrading hardware or scaling up operations.</span></span> <span data-ttu-id="bd8f9-143">データベースを移動するには、バックアップ操作と復元操作を実行します。</span><span class="sxs-lookup"><span data-stu-id="bd8f9-143">To move the database you perform a backup and restore operation.</span></span> <span data-ttu-id="bd8f9-144">このプロセスの詳細については、[をバックアップおよび復元する BAM](../core/backing-up-and-restoring-bam.md)を参照してください。</span><span class="sxs-lookup"><span data-stu-id="bd8f9-144">For more information about this process, see [Backing Up and Restoring BAM](../core/backing-up-and-restoring-bam.md).</span></span>  
  
### <a name="working-with-bam-definitions"></a><span data-ttu-id="bd8f9-145">BAM 定義の操作</span><span class="sxs-lookup"><span data-stu-id="bd8f9-145">Working with BAM Definitions</span></span>  
 <span data-ttu-id="bd8f9-146">管理者は BAM 定義と密接にかかわっています。</span><span class="sxs-lookup"><span data-stu-id="bd8f9-146">Administrators work closely with BAM definitions.</span></span> <span data-ttu-id="bd8f9-147">BAM 定義の操作に使用する主なツールは BAM 管理ユーティリティです。</span><span class="sxs-lookup"><span data-stu-id="bd8f9-147">The primary tool you use to work with BAM definitions is the BAM Management utility.</span></span> <span data-ttu-id="bd8f9-148">このユーティリティを使用すると、次のタスクを実行できます。</span><span class="sxs-lookup"><span data-stu-id="bd8f9-148">You can perform the following tasks by using this utility:</span></span>  
  
- <span data-ttu-id="bd8f9-149">アクティビティを変更する。</span><span class="sxs-lookup"><span data-stu-id="bd8f9-149">Changing activities.</span></span> <span data-ttu-id="bd8f9-150">使用することができます、**展開すべて**、**更新すべて**、**削除アクティビティ**、 **set-actvitywindow** BAM 管理ユーティリティのコマンド展開済みのアクティビティを変更します。</span><span class="sxs-lookup"><span data-stu-id="bd8f9-150">You can use the **deploy-all**, **update-all**, **remove-activity**, **and set-actvitywindow** commands of the BAM management utility to change your deployed activities.</span></span>  
  
- <span data-ttu-id="bd8f9-151">アクティビティ テーブルにインデックスを適用してパフォーマンスを向上する。</span><span class="sxs-lookup"><span data-stu-id="bd8f9-151">Applying indexes to activity tables to enhance performance.</span></span> <span data-ttu-id="bd8f9-152">使用する、**インデックスの作成**と**インデックスを削除**アクティビティのインデックスを変更するコマンド。</span><span class="sxs-lookup"><span data-stu-id="bd8f9-152">You use the **create-index** and **delete-index** commands to modify the indexes on activities.</span></span>  
  
- <span data-ttu-id="bd8f9-153">ビューにセキュリティを設定する。</span><span class="sxs-lookup"><span data-stu-id="bd8f9-153">Setting security on views.</span></span> <span data-ttu-id="bd8f9-154">使用することができます、**アカウントの追加**と**削除アカウント**コマンドをユーザーに付与するアクセス権をビュー。</span><span class="sxs-lookup"><span data-stu-id="bd8f9-154">You can use the **add-account** and **remove-account** commands to grant users access rights to views.</span></span>  
  
- <span data-ttu-id="bd8f9-155">アクティビティの分散ナビゲーションを構成する。</span><span class="sxs-lookup"><span data-stu-id="bd8f9-155">Configuring distributed navigation of activities.</span></span> <span data-ttu-id="bd8f9-156">使用する、**参照を有効にする**と**無効にする参照**アクティビティの分散ナビゲーションを構成するコマンド。</span><span class="sxs-lookup"><span data-stu-id="bd8f9-156">You use the **enable-reference** and **disable-reference** commands to configure distributed navigation of activities.</span></span> <span data-ttu-id="bd8f9-157">アクティビティの分散ナビゲーションの詳細については、[を管理する分散ナビゲーションのリモート アクティビティ](../core/managing-distributed-navigation-of-remote-activities.md)を参照してください。</span><span class="sxs-lookup"><span data-stu-id="bd8f9-157">For more information about the distributed navigation of activities, see [Managing Distributed Navigation of Remote Activities](../core/managing-distributed-navigation-of-remote-activities.md).</span></span>  
  
- <span data-ttu-id="bd8f9-158">変更を監査する。</span><span class="sxs-lookup"><span data-stu-id="bd8f9-158">Auditing changes.</span></span> <span data-ttu-id="bd8f9-159">BAM 動的インフラストラクチャを使用して変更を一覧表示、 **get 変更**コマンド。</span><span class="sxs-lookup"><span data-stu-id="bd8f9-159">You can list changes to the BAM dynamic infrastructure using the **get-changes** command.</span></span>  
  
  <span data-ttu-id="bd8f9-160">BAM 管理ユーティリティで使用できるすべてのコマンドについては、[BAM 管理ユーティリティ](../core/bam-management-utility.md)を参照してください。</span><span class="sxs-lookup"><span data-stu-id="bd8f9-160">For a description of all the commands available through the BAM Management utility, see [BAM Management Utility](../core/bam-management-utility.md).</span></span> <span data-ttu-id="bd8f9-161">BAM 管理ユーティリティを使用した BAM 定義の操作の例については、[BAM 動的インフラストラクチャの管理](../core/managing-the-bam-dynamic-infrastructure.md)を参照してください。</span><span class="sxs-lookup"><span data-stu-id="bd8f9-161">For examples of using the BAM Management utility to work with BAM definitions, see [Managing the BAM Dynamic Infrastructure](../core/managing-the-bam-dynamic-infrastructure.md).</span></span>  
  
## <a name="configuring-multiple-biztalk-groups-to-reference-a-single-bam-database"></a><span data-ttu-id="bd8f9-162">1 つの BAM データベースを参照する複数の BizTalk グループの構成</span><span class="sxs-lookup"><span data-stu-id="bd8f9-162">Configuring Multiple BizTalk Groups to Reference a Single BAM Database</span></span>  
 <span data-ttu-id="bd8f9-163">新しいまたは既存の BizTalk Server グループのいずれかを使用する BAM を構成する場合は、既に別の BizTalk Server グループで使用されている同じ BAM データベースを使用するグループを構成できます。</span><span class="sxs-lookup"><span data-stu-id="bd8f9-163">When configuring BAM to use either a new or an existing BizTalk Server group, you can configure the group to use the same BAM databases that are already in use by another BizTalk Server group.</span></span>  <span data-ttu-id="bd8f9-164">この方法で BAM を構成するには、次のタスクを実行する必要があります。</span><span class="sxs-lookup"><span data-stu-id="bd8f9-164">To configure BAM in this manner, you must perform the following tasks:</span></span>  
  
-   <span data-ttu-id="bd8f9-165">BizTalk Server の構成ウィザードを使用して既存の BAM プライマリ インポート データベースから構成情報を取得します。</span><span class="sxs-lookup"><span data-stu-id="bd8f9-165">Get the configuration information from the existing BAM Primary Import database using the BizTalk Server Configuration Wizard.</span></span> <span data-ttu-id="bd8f9-166">構成情報には、サーバー名とデータベース名が含まれます。</span><span class="sxs-lookup"><span data-stu-id="bd8f9-166">This includes the server and database names.</span></span> <span data-ttu-id="bd8f9-167">チェック ボックスの状態に注意してください。</span><span class="sxs-lookup"><span data-stu-id="bd8f9-167">Note the state of the check boxes.</span></span> <span data-ttu-id="bd8f9-168">[BAM ツール] ページと [BAM 警告] ページの両方の構成情報を取得するようにしてください。</span><span class="sxs-lookup"><span data-stu-id="bd8f9-168">Be sure to get the configuration information for both the BAM Tools and BAM Alerts pages.</span></span>  
  
-   <span data-ttu-id="bd8f9-169">新しいグループに BAM を構成し、対象のプライマリ インポート テーブル (PIT) 用に構成されている情報を正確に入力します。</span><span class="sxs-lookup"><span data-stu-id="bd8f9-169">Configure BAM for the new group, and enter the exact information as configured already for the target PIT.</span></span> <span data-ttu-id="bd8f9-170">新しいグループの構成情報を入力するときに、既存のグループから収集されたすべての情報を使用して、新しいグループを構成します。ただし、BAM 警告ユーザーについては空白のままにする必要があります。</span><span class="sxs-lookup"><span data-stu-id="bd8f9-170">When entering the configuration information for the new group you will use all the information collected from the existing group to configure the new group, except the BAM Alerts user, which you must leave blank.</span></span>  
  
## <a name="backing-up-and-restoring-bam"></a><span data-ttu-id="bd8f9-171">BAM のバックアップと復元</span><span class="sxs-lookup"><span data-stu-id="bd8f9-171">Backing Up and Restoring BAM</span></span>  
 <span data-ttu-id="bd8f9-172">管理者は、ディザスター リカバリーの状況に備えて計画を行う必要があります。</span><span class="sxs-lookup"><span data-stu-id="bd8f9-172">Administrators should plan for disaster recovery situations.</span></span> <span data-ttu-id="bd8f9-173">BAM 分析、追跡分析、BAM スター スキーマ、BAM アーカイブ、および BAM プライマリ インポート データベースをバックアップして、これらを復元する状況に備える必要があります。</span><span class="sxs-lookup"><span data-stu-id="bd8f9-173">You should back up the BAM Analysis, Tracking Analysis, BAM Star Schema, BAM Archive, and BAM Primary Import databases to provide for situations in which you must restore them.</span></span>  <span data-ttu-id="bd8f9-174">バックアップおよび BAM データベースを復元する方法については、[をバックアップおよび復元する BAM](../core/backing-up-and-restoring-bam.md)を参照してください。</span><span class="sxs-lookup"><span data-stu-id="bd8f9-174">For information about backing up and restoring the BAM databases, see [Backing Up and Restoring BAM](../core/backing-up-and-restoring-bam.md).</span></span>  
  
## <a name="working-with-renamed-servers"></a><span data-ttu-id="bd8f9-175">名前を変更したサーバーの操作</span><span class="sxs-lookup"><span data-stu-id="bd8f9-175">Working with Renamed Servers</span></span>  
 <span data-ttu-id="bd8f9-176">サーバーの名前を変更するか、BAM インフラストラクチャをサーバー間で移動するとき、Excel ブックで BAM 定義を更新して、Excel ブックを更新する必要があります。</span><span class="sxs-lookup"><span data-stu-id="bd8f9-176">When you rename a server or move the BAM infrastructure between servers, you must update the Excel workbook by updating the BAM definitions in that workbook.</span></span>  
  
 <span data-ttu-id="bd8f9-177">次のようなシナリオで、ブックの更新が必要になります。</span><span class="sxs-lookup"><span data-stu-id="bd8f9-177">The scenarios in which you would need to update the workbook include:</span></span>  
  
- <span data-ttu-id="bd8f9-178">BAM インフラストラクチャを新しいデータベースに移動するステージング シナリオ。</span><span class="sxs-lookup"><span data-stu-id="bd8f9-178">A staging scenario, in which you move the BAM infrastructure to a new database.</span></span> <span data-ttu-id="bd8f9-179">Excel ブックが機能していることを確認するには、ブックを再展開または移行してから再び更新する必要があります。</span><span class="sxs-lookup"><span data-stu-id="bd8f9-179">To ensure that the Excel workbooks are still functional, you must redeploy or migrate and then re-update the workbooks.</span></span>  
  
- <span data-ttu-id="bd8f9-180">BizTalk Server を実行しているコンピューターの名前を変更するシナリオ。</span><span class="sxs-lookup"><span data-stu-id="bd8f9-180">A scenario in which you rename the computer running BizTalk Server.</span></span> <span data-ttu-id="bd8f9-181">これは、DTS パッケージと、ブックの更新に加えて、OLAP データ ソースの更新が必要です。</span><span class="sxs-lookup"><span data-stu-id="bd8f9-181">This requires updating the DTS packages and OLAP data source in addition to updating the workbook.</span></span>  
  
  <span data-ttu-id="bd8f9-182">Excel ブックの更新には、次の 2 つの手法があります。</span><span class="sxs-lookup"><span data-stu-id="bd8f9-182">There are two approaches you can use to update the Excel workbook:</span></span>  
  
- <span data-ttu-id="bd8f9-183">新しいサーバーから、次の BAM マネージャー コマンドを実行します。</span><span class="sxs-lookup"><span data-stu-id="bd8f9-183">Run the following BAM Manager command from the new server:</span></span>  
  
   <span data-ttu-id="bd8f9-184">**bm.exe の update livedataworkbook-名前:\<update.xls livedata ブック\>**</span><span class="sxs-lookup"><span data-stu-id="bd8f9-184">**bm.exe update-livedataworkbook -Name:\<livedata workbook to update.xls\>**</span></span>  
  
  > [!NOTE]
  >  <span data-ttu-id="bd8f9-185">新しいサーバー名および BAM プライマリ インポート データベース名を指定することもできます: **bm.exe 更新-livedataworkbook-名前:\<update.xls livedata ブック\>[-サーバー:\<server\>] [-データベース:\<データベース\>]**</span><span class="sxs-lookup"><span data-stu-id="bd8f9-185">You can also specify the new server name and/or BAM Primary Import database name: **bm.exe update-livedataworkbook -Name:\<livedata workbook to update.xls\> [-Server:\<server\>] [-Database:\<database\>]**</span></span>  
  
- <span data-ttu-id="bd8f9-186">または、この Excel ブックを Excel 内で更新します。</span><span class="sxs-lookup"><span data-stu-id="bd8f9-186">Alternatively, you can update the Excel workbook from within Excel:</span></span>  
  
  1.  <span data-ttu-id="bd8f9-187">更新するブックを開きます。</span><span class="sxs-lookup"><span data-stu-id="bd8f9-187">Open the workbook you want to update.</span></span>  
  
  2.  <span data-ttu-id="bd8f9-188">BAM のメニューから**BAM データベースの接続**します。</span><span class="sxs-lookup"><span data-stu-id="bd8f9-188">From the BAM menu, click **BAM Db Connection**.</span></span>  
  
  3.  <span data-ttu-id="bd8f9-189">新しいサーバーおよび BAM プライマリ インポート データベースの名前を入力します。</span><span class="sxs-lookup"><span data-stu-id="bd8f9-189">Enter the new server name and BAM Primary Import database name.</span></span>  
  
## <a name="managing-alerts"></a><span data-ttu-id="bd8f9-190">警告の管理</span><span class="sxs-lookup"><span data-stu-id="bd8f9-190">Managing Alerts</span></span>  
 <span data-ttu-id="bd8f9-191">管理者は、いくつかの方法で警告を管理することができます。</span><span class="sxs-lookup"><span data-stu-id="bd8f9-191">Administrators can manage alerts in a several ways:</span></span>  
  
 <span data-ttu-id="bd8f9-192">BAM 管理ユーティリティを使用して、警告の展開と削除を実行できます。</span><span class="sxs-lookup"><span data-stu-id="bd8f9-192">You can use the BAM Management utility to deploy and remove alerts.</span></span> <span data-ttu-id="bd8f9-193">このユーティリティは、警告の有効化と無効化だけでなく、サブスクリプションの追加と削除にも使用できます。</span><span class="sxs-lookup"><span data-stu-id="bd8f9-193">You can also use the utility to add and remove subscriptions, as well as to enable and disable alerts.</span></span> <span data-ttu-id="bd8f9-194">詳細については、BAM 管理ユーティリティを使用して、[BAM 管理ユーティリティ](../core/bam-management-utility.md)、 [BAM セキュリティの管理](../core/managing-bam-security.md)、および[BAM 定義を管理する](../core/managing-bam-definitions.md)を参照してください。</span><span class="sxs-lookup"><span data-stu-id="bd8f9-194">For more information about using the BAM Management utility, see [BAM Management Utility](../core/bam-management-utility.md), [Managing BAM Security](../core/managing-bam-security.md), and [Managing BAM Definitions](../core/managing-bam-definitions.md).</span></span>  
  
 <span data-ttu-id="bd8f9-195">BAM ポータルを使用して、警告の作成や削除を行うこともできます。</span><span class="sxs-lookup"><span data-stu-id="bd8f9-195">You can also create and remove alerts through the BAM portal.</span></span>  <span data-ttu-id="bd8f9-196">BAM ポータルを使用してアラートを作成する方法の詳細については、[BAM ポータルでのアクティビティの検索](../core/activity-searches-in-the-bam-portal.md)を参照してください。</span><span class="sxs-lookup"><span data-stu-id="bd8f9-196">For information about creating alerts using the BAM portal, see [Activity Searches in the BAM Portal](../core/activity-searches-in-the-bam-portal.md).</span></span>  
  
### <a name="cleaning-up-the-alerts-chronicle-table"></a><span data-ttu-id="bd8f9-197">警告記録テーブルのクリーンアップ</span><span class="sxs-lookup"><span data-stu-id="bd8f9-197">Cleaning up the Alerts Chronicle table</span></span>  
 <span data-ttu-id="bd8f9-198">BAM 警告が構成されている場合、作成される各アクティビティ ビューに対して SQL ジョブが作成されます。</span><span class="sxs-lookup"><span data-stu-id="bd8f9-198">If BAM alerts are configured, a SQL job is created for each activity view that is created.</span></span> <span data-ttu-id="bd8f9-199">次のテンプレートを使用して、ジョブに名前が付けられます。</span><span class="sxs-lookup"><span data-stu-id="bd8f9-199">The job will be named using the following template:</span></span>  
  
 <span data-ttu-id="bd8f9-200">bam _\<ビュー名\>_\<アクティビティ ビュー\>_DelAlertHistJob</span><span class="sxs-lookup"><span data-stu-id="bd8f9-200">bam_\<View Name\>_\<Activity View\>_DelAlertHistJob</span></span>  
  
 <span data-ttu-id="bd8f9-201">このジョブを指定したインスタンス警告に対する監査データをクリーンアップ\<アクティビティ ビュー\>は Bam_Metadata_AlertChronicle テーブル内。</span><span class="sxs-lookup"><span data-stu-id="bd8f9-201">This job cleans up auditing data for the instance alerts for the specified \<Activity View\> in the Bam_Metadata_AlertChronicle table.</span></span> <span data-ttu-id="bd8f9-202">特定のアクティビティ ビューにインスタンス警告を定義した場合、警告が発生するたびに、このテーブルに新しい行が追加されます。</span><span class="sxs-lookup"><span data-stu-id="bd8f9-202">If you have defined instance alerts on the particular activity view, a new row will be added to this table every time the alert is fired.</span></span>  
  
 <span data-ttu-id="bd8f9-203">テーブルをクリーンアップするために、ジョブは手動で実行することも、アプリケーションや環境に応じて実行されるようにスケジュールすることもできます。</span><span class="sxs-lookup"><span data-stu-id="bd8f9-203">You can run this job manually to clean up the table or schedule it to run according to the need of your application or environment.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="bd8f9-204">参照</span><span class="sxs-lookup"><span data-stu-id="bd8f9-204">See Also</span></span>  
 [<span data-ttu-id="bd8f9-205">BAM の管理</span><span class="sxs-lookup"><span data-stu-id="bd8f9-205">Managing BAM</span></span>](../core/managing-bam.md)