---
title: BAM 管理ユーティリティ |Microsoft Docs
ms.custom: ''
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: ''
ms.suite: ''
ms.tgt_pltfrm: ''
ms.topic: article
ms.assetid: c55aabe2-f38b-4917-863c-b408a4eef98e
caps.latest.revision: 50
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: cd7569bb1f257c3b8686902ea5776e5bf8e1b467
ms.sourcegitcommit: d27732e569b0897361dfaebca8352aa97bb7efe1
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 05/10/2019
ms.locfileid: "65530582"
---
# <a name="bam-management-utility"></a><span data-ttu-id="ea8d3-102">BAM 管理ユーティリティ</span><span class="sxs-lookup"><span data-stu-id="ea8d3-102">BAM Management Utility</span></span>
<span data-ttu-id="ea8d3-103">ビジネス アクティビティ監視 (BAM) 定義の管理者では、BAM 管理ユーティリティを使用して、管理し、BAM インフラストラクチャのあらゆる側面を管理します。</span><span class="sxs-lookup"><span data-stu-id="ea8d3-103">Administrators of Business Activity Monitoring (BAM) definitions use the BAM Management utility to manage and maintain all aspects of the BAM infrastructure.</span></span>  
  
 <span data-ttu-id="ea8d3-104">BAM ユーティリティを使用するには、次のタスクを実行します。</span><span class="sxs-lookup"><span data-stu-id="ea8d3-104">You can use the BAM utility to perform the following tasks:</span></span>  
  
-   <span data-ttu-id="ea8d3-105">BAM 定義と BAM 構成 XML を入力として使用します。</span><span class="sxs-lookup"><span data-stu-id="ea8d3-105">Consume BAM definition and BAM configuration XML as input.</span></span> <span data-ttu-id="ea8d3-106">BAM 定義 XML または XLS ファイルは、追跡し、集計、追跡データに関するビジネス エンドユーザーのビューにデータを定義します。</span><span class="sxs-lookup"><span data-stu-id="ea8d3-106">The BAM definition XML or XLS files define the data to track and aggregate, as well as the business end user's view on the tracking data.</span></span> <span data-ttu-id="ea8d3-107">BAM 構成 XML には、サーバー名、データベース名、およびその他のデータベースの設定など、インフラストラクチャをデプロイする場所が定められています。</span><span class="sxs-lookup"><span data-stu-id="ea8d3-107">The BAM configuration XML mandates where to deploy the infrastructure, such as the server name, database name, and other database settings.</span></span>  
  
-   <span data-ttu-id="ea8d3-108">BAM プライマリ インポート データベース、BAM スター スキーマ データベース、BAM 分析データベースが含まれているサーバー上のランタイム インフラストラクチャをデプロイし、対応するデータ変換サービス (DTS) パッケージ。</span><span class="sxs-lookup"><span data-stu-id="ea8d3-108">Deploy the run-time infrastructure on the server, which includes the BAM Primary Import database, BAM Star Schema database, BAM Analysis database, and corresponding Data Transformation Services (DTS) packages.</span></span> <span data-ttu-id="ea8d3-109">この手順では、次の項目が作成されます。</span><span class="sxs-lookup"><span data-stu-id="ea8d3-109">The following items are created during this step:</span></span>  
  
    -   <span data-ttu-id="ea8d3-110">BAM プライマリ インポート データベース</span><span class="sxs-lookup"><span data-stu-id="ea8d3-110">BAM Primary Import database</span></span>  
  
    -   <span data-ttu-id="ea8d3-111">BAM スター スキーマ データベース</span><span class="sxs-lookup"><span data-stu-id="ea8d3-111">BAM Star Schema database</span></span>  
  
    -   <span data-ttu-id="ea8d3-112">BAM アーカイブ データベース</span><span class="sxs-lookup"><span data-stu-id="ea8d3-112">BAM Archive database</span></span>  
  
    -   <span data-ttu-id="ea8d3-113">BAM 分析データベース</span><span class="sxs-lookup"><span data-stu-id="ea8d3-113">BAM Analysis database</span></span>  
  
> [!NOTE]
>  <span data-ttu-id="ea8d3-114">BAM 管理ユーティリティを実行しているコンピューターのロケール設定は、適切に機能する BAM コマンドの順序でデプロイされている BAM 定義を作成するために使用するロケールと同じである必要があります。</span><span class="sxs-lookup"><span data-stu-id="ea8d3-114">The locale setting of the computer running the BAM Management utility must be the same as the locale used to create the BAM definition being deployed in order for the BAM commands to work properly.</span></span> <span data-ttu-id="ea8d3-115">実行する場合など、 **get ビュー**構成されたコンピューターのロケールが英語とフランス語のロケールを使用しているコンピューターで、データベースに対して設定することはできませんをリセットしない限り、返されたビュー名を使用する、コンピューターをフランス語のロケール。</span><span class="sxs-lookup"><span data-stu-id="ea8d3-115">For example, if you execute the **get-views** command on a computer configured with an English locale setting against a database on a computer with a French locale you will not be able to use the returned view name unless you reset your computer locale to French.</span></span>  
  
 <span data-ttu-id="ea8d3-116">BAM 管理ユーティリティを使用して、生成して、サーバーに対して追跡構成をデプロイすることができます。</span><span class="sxs-lookup"><span data-stu-id="ea8d3-116">You can use the BAM Management utility to generate and deploy your tracking configuration on a server.</span></span> <span data-ttu-id="ea8d3-117">BAM 管理ユーティリティにあるコマンド ライン ツールは、 \<*インストール パス*\>\Program Files\Microsoft BizTalk Server\<バージョン\>\Tracking\BM.exe します。</span><span class="sxs-lookup"><span data-stu-id="ea8d3-117">The BAM Management utility is a command-line tool located at \<*installation path*\>\Program Files\Microsoft BizTalk Server \<version\>\Tracking\BM.exe.</span></span>  
  
> [!IMPORTANT]
>  <span data-ttu-id="ea8d3-118">BAM 管理ユーティリティを実行するには、メンバーである、 **db_owner**の BAM プライマリ インポート、BAM スター スキーマ、および BAM アーカイブ データベースの SQL Server データベース ロール。</span><span class="sxs-lookup"><span data-stu-id="ea8d3-118">To run the BAM management utility, you must be member of the **db_owner** SQL Server Database role in the BAM Primary Import, BAM Star Schema, and BAM Archive databases.</span></span> <span data-ttu-id="ea8d3-119">BAM 警告に関連する更新を行う場合、BAM 警告データベースの sysadmin アクセス許可が必要です。</span><span class="sxs-lookup"><span data-stu-id="ea8d3-119">You must also have sysadmin permissions on the BAM Alerts databases if making any updates related to BAM Alerts.</span></span>  
  
> [!NOTE]
>  <span data-ttu-id="ea8d3-120">ユーザー アカウント制御 (UAC) をサポートするシステムでは、管理者特権を使用してこのツールを実行することが必要な場合があります。</span><span class="sxs-lookup"><span data-stu-id="ea8d3-120">On a system that supports User Account Control (UAC), you may need to run the tool with Administrative privileges.</span></span> <span data-ttu-id="ea8d3-121">これを行うには、アプリケーションを右クリックし、**管理者として実行**します。</span><span class="sxs-lookup"><span data-stu-id="ea8d3-121">To do this, right-click the application, and then select **Run as administrator**.</span></span>  
  
## <a name="bam-management-utility-commands"></a><span data-ttu-id="ea8d3-122">BAM 管理ユーティリティのコマンド</span><span class="sxs-lookup"><span data-stu-id="ea8d3-122">BAM Management Utility Commands</span></span>  
 <span data-ttu-id="ea8d3-123">コマンドの説明では、これらの規則を使用します。</span><span class="sxs-lookup"><span data-stu-id="ea8d3-123">The command descriptions use these conventions:</span></span>  
  
- <span data-ttu-id="ea8d3-124">角かっこ () は、オプションのパラメーターを示します。</span><span class="sxs-lookup"><span data-stu-id="ea8d3-124">The square brackets ([]) indicate an optional parameter.</span></span>  
  
- <span data-ttu-id="ea8d3-125">山かっこ (<) は、必要なパラメーターを示します。</span><span class="sxs-lookup"><span data-stu-id="ea8d3-125">The angled brackets (<>) indicate a required parameter.</span></span>  
  
- <span data-ttu-id="ea8d3-126">中かっこ ({}) 1 つのアイテムが列挙された一覧から選択する必要がありますを指定します。</span><span class="sxs-lookup"><span data-stu-id="ea8d3-126">The braces ({}) indicate that one item should be selected from the enumerated list.</span></span>  
  
- <span data-ttu-id="ea8d3-127">セキュリティ アカウントは NT グループまたは個々 の NT ユーザー アカウントのいずれかにできます。</span><span class="sxs-lookup"><span data-stu-id="ea8d3-127">A security account can be either an NT group or an individual NT user account.</span></span>  
  
- <span data-ttu-id="ea8d3-128">BAM 定義ファイルを XML ファイルまたは BAM Excel ブック ファイル (.xls) のいずれかを使用できます。</span><span class="sxs-lookup"><span data-stu-id="ea8d3-128">A BAM definition file can be either an XML file or a BAM Excel workbook file (.xls).</span></span>  
  
- <span data-ttu-id="ea8d3-129">BAM 構成ファイルが指定されていない場合の既定値は、現在のフォルダーの BamConfiguration.xml です。</span><span class="sxs-lookup"><span data-stu-id="ea8d3-129">If the BAM configuration file is not supplied, it defaults to BamConfiguration.xml in the current folder.</span></span>  
  
  <span data-ttu-id="ea8d3-130">次のトピックでは、個々 のコマンドの説明が含まれています。</span><span class="sxs-lookup"><span data-stu-id="ea8d3-130">The Individual command descriptions are contained in the following topics:</span></span>  
  
- [<span data-ttu-id="ea8d3-131">データベース コマンド</span><span class="sxs-lookup"><span data-stu-id="ea8d3-131">Database Commands</span></span>](../core/database-commands.md)  
  
- [<span data-ttu-id="ea8d3-132">BAM 定義 (監視モデル) の展開コマンド</span><span class="sxs-lookup"><span data-stu-id="ea8d3-132">Deployment of BAM Definition (Observation Model) Commands</span></span>](../core/deployment-of-bam-definition-observation-model-commands.md)  
  
- [<span data-ttu-id="ea8d3-133">インフラストラクチャ管理コマンド</span><span class="sxs-lookup"><span data-stu-id="ea8d3-133">Infrastructure Management Commands</span></span>](../core/infrastructure-management-commands.md)  
  
- [<span data-ttu-id="ea8d3-134">アクティビティ管理コマンド</span><span class="sxs-lookup"><span data-stu-id="ea8d3-134">Activity Management Commands</span></span>](../core/activity-management-commands.md)  
  
- [<span data-ttu-id="ea8d3-135">ビュー管理コマンド</span><span class="sxs-lookup"><span data-stu-id="ea8d3-135">View Management Commands</span></span>](../core/view-management-commands.md)  
  
- [<span data-ttu-id="ea8d3-136">Alert Management コマンド</span><span class="sxs-lookup"><span data-stu-id="ea8d3-136">Alert Management Commands</span></span>](../core/alert-management-commands.md)  
  
- [<span data-ttu-id="ea8d3-137">ユーザー管理コマンド</span><span class="sxs-lookup"><span data-stu-id="ea8d3-137">User Management Commands</span></span>](../core/user-management-commands.md)  
  
- [<span data-ttu-id="ea8d3-138">警告サブスクリプション管理コマンド</span><span class="sxs-lookup"><span data-stu-id="ea8d3-138">Alert Subscription Management Commands</span></span>](../core/alert-subscription-management-commands.md)  
  
- [<span data-ttu-id="ea8d3-139">インターセプター管理コマンド</span><span class="sxs-lookup"><span data-stu-id="ea8d3-139">Interceptor Management Commands</span></span>](../core/interceptor-management-commands.md)  
  
## <a name="displaying-the-bam-management-utility-help"></a><span data-ttu-id="ea8d3-140">BAM 管理ユーティリティのヘルプを表示します。</span><span class="sxs-lookup"><span data-stu-id="ea8d3-140">Displaying the BAM Management Utility Help</span></span>  
 <span data-ttu-id="ea8d3-141">使用する、 **/でしょうか。**</span><span class="sxs-lookup"><span data-stu-id="ea8d3-141">You use the **/?**</span></span> <span data-ttu-id="ea8d3-142">または、 **BAM 管理ユーティリティのヘルプ**BAM 管理ユーティリティのヘルプ ファイルを表示するコマンド。</span><span class="sxs-lookup"><span data-stu-id="ea8d3-142">or the **help BAM Management utility** command to display the Help file for the BAM Management utility.</span></span>  
  
#### <a name="to-display-the-help-file-for-the-bam-management-utility"></a><span data-ttu-id="ea8d3-143">BAM 管理ユーティリティのヘルプ ファイルを表示するには</span><span class="sxs-lookup"><span data-stu-id="ea8d3-143">To display the Help file for the BAM Management utility</span></span>  
  
1.  <span data-ttu-id="ea8d3-144">コマンド プロンプトから次のディレクトリを参照してください。C:\Program files \microsoft BizTalk Server\<バージョン\>\Tracking\\します。</span><span class="sxs-lookup"><span data-stu-id="ea8d3-144">From a command prompt, browse to the following directory: C:\Program Files\Microsoft BizTalk Server \<version\>\Tracking\\.</span></span>  
  
2.  <span data-ttu-id="ea8d3-145">型**bm**または**bm ヘルプ**します。</span><span class="sxs-lookup"><span data-stu-id="ea8d3-145">Type **bm** or **bm help**.</span></span>  
  
3.  <span data-ttu-id="ea8d3-146">Enter キーを押します。</span><span class="sxs-lookup"><span data-stu-id="ea8d3-146">Press ENTER.</span></span>