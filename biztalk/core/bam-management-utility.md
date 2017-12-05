---
title: "BAM 管理ユーティリティ |Microsoft ドキュメント"
ms.custom: 
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: 
ms.suite: 
ms.tgt_pltfrm: 
ms.topic: article
ms.assetid: c55aabe2-f38b-4917-863c-b408a4eef98e
caps.latest.revision: "50"
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: 5374ba63ba8eb4193c3ef4990e8c169646a3528b
ms.sourcegitcommit: 5abd0ed3f9e4858ffaaec5481bfa8878595e95f7
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 11/28/2017
---
# <a name="bam-management-utility"></a><span data-ttu-id="e6986-102">BAM 管理ユーティリティ</span><span class="sxs-lookup"><span data-stu-id="e6986-102">BAM Management Utility</span></span>
<span data-ttu-id="e6986-103">BAM 管理ユーティリティは、BAM インフラストラクチャのあらゆる要素を管理、保守するために、ビジネス アクティビティ監視 (BAM) 定義の管理者によって使用されます。</span><span class="sxs-lookup"><span data-stu-id="e6986-103">Administrators of Business Activity Monitoring (BAM) definitions use the BAM Management utility to manage and maintain all aspects of the BAM infrastructure.</span></span>  
  
 <span data-ttu-id="e6986-104">BAM ユーティリティを使用すると、次のようなタスクを実行できます。</span><span class="sxs-lookup"><span data-stu-id="e6986-104">You can use the BAM utility to perform the following tasks:</span></span>  
  
-   <span data-ttu-id="e6986-105">BAM 定義/BAM 構成の XML を入力として使用する。</span><span class="sxs-lookup"><span data-stu-id="e6986-105">Consume BAM definition and BAM configuration XML as input.</span></span> <span data-ttu-id="e6986-106">BAM 定義ファイル (XML または XLS) は、追跡データや集計データ、さらには、追跡データに対するビジネス エンド ユーザー向けのビューを定義するファイルです。</span><span class="sxs-lookup"><span data-stu-id="e6986-106">The BAM definition XML or XLS files define the data to track and aggregate, as well as the business end user's view on the tracking data.</span></span> <span data-ttu-id="e6986-107">BAM 構成 XML は、サーバー名、データベース名、データベース設定など、インフラストラクチャの展開先となる環境を定義したものです。</span><span class="sxs-lookup"><span data-stu-id="e6986-107">The BAM configuration XML mandates where to deploy the infrastructure, such as the server name, database name, and other database settings.</span></span>  
  
-   <span data-ttu-id="e6986-108">サーバー上にランタイム インフラストラクチャを展開する。このインフラストラクチャには、BAM プライマリ インポート データベース、BAM スター スキーマ データベース、BAM 分析データベース、および対応するデータ変換サービス (DTS) パッケージが含まれます。</span><span class="sxs-lookup"><span data-stu-id="e6986-108">Deploy the run-time infrastructure on the server, which includes the BAM Primary Import database, BAM Star Schema database, BAM Analysis database, and corresponding Data Transformation Services (DTS) packages.</span></span> <span data-ttu-id="e6986-109">この作業では、次のアイテムが作成されます。</span><span class="sxs-lookup"><span data-stu-id="e6986-109">The following items are created during this step:</span></span>  
  
    -   <span data-ttu-id="e6986-110">BAM プライマリ インポート データベース</span><span class="sxs-lookup"><span data-stu-id="e6986-110">BAM Primary Import database</span></span>  
  
    -   <span data-ttu-id="e6986-111">BAM スター スキーマ データベース</span><span class="sxs-lookup"><span data-stu-id="e6986-111">BAM Star Schema database</span></span>  
  
    -   <span data-ttu-id="e6986-112">BAM アーカイブ データベース</span><span class="sxs-lookup"><span data-stu-id="e6986-112">BAM Archive database</span></span>  
  
    -   <span data-ttu-id="e6986-113">BAM 分析データベース</span><span class="sxs-lookup"><span data-stu-id="e6986-113">BAM Analysis database</span></span>  
  
> [!NOTE]
>  <span data-ttu-id="e6986-114">BAM コマンドを適切に動作させるためには、BAM 管理ユーティリティを実行するコンピューターのロケール設定が、展開されている BAM 定義の作成に使用したロケールと一致している必要があります。</span><span class="sxs-lookup"><span data-stu-id="e6986-114">The locale setting of the computer running the BAM Management utility must be the same as the locale used to create the BAM definition being deployed in order for the BAM commands to work properly.</span></span> <span data-ttu-id="e6986-115">たとえばを実行する場合、 **get ビュー**構成されているコンピューターのロケールが英語とフランス語ロケールのコンピューターで、データベースに対して設定することはできませんをリセットしない限り、返されたビュー名を使用する、コンピューターをフランス語ロケール。</span><span class="sxs-lookup"><span data-stu-id="e6986-115">For example, if you execute the **get-views** command on a computer configured with an English locale setting against a database on a computer with a French locale you will not be able to use the returned view name unless you reset your computer locale to French.</span></span>  
  
 <span data-ttu-id="e6986-116">BAM 管理ユーティリティを使用すると、サーバーに対して追跡構成を生成したり展開したりできます。</span><span class="sxs-lookup"><span data-stu-id="e6986-116">You can use the BAM Management utility to generate and deploy your tracking configuration on a server.</span></span> <span data-ttu-id="e6986-117">BAM 管理ユーティリティにあるコマンド ライン ツールは、 \<*インストール パス*\>\Program Files\Microsoft BizTalk Server\<バージョン\>\Tracking\BM.exe です。</span><span class="sxs-lookup"><span data-stu-id="e6986-117">The BAM Management utility is a command-line tool located at \<*installation path*\>\Program Files\Microsoft BizTalk Server \<version\>\Tracking\BM.exe.</span></span>  
  
> [!IMPORTANT]
>  <span data-ttu-id="e6986-118">BAM 管理ユーティリティを実行するには、メンバーである、 **db_owner**の BAM プライマリ インポート、BAM スター スキーマ、および BAM アーカイブ データベースの SQL Server データベース ロール。</span><span class="sxs-lookup"><span data-stu-id="e6986-118">To run the BAM management utility, you must be member of the **db_owner** SQL Server Database role in the BAM Primary Import, BAM Star Schema, and BAM Archive databases.</span></span> <span data-ttu-id="e6986-119">また、BAM 警告に関連する更新を行う場合には、BAM 警告データベースに対する sysadmin アクセス許可も必要です。</span><span class="sxs-lookup"><span data-stu-id="e6986-119">You must also have sysadmin permissions on the BAM Alerts databases if making any updates related to BAM Alerts.</span></span>  
  
> [!NOTE]
>  <span data-ttu-id="e6986-120">ユーザー アカウント制御 (UAC) をサポートするシステムでは、管理者特権を使用してこのツールを実行することが必要な場合があります。</span><span class="sxs-lookup"><span data-stu-id="e6986-120">On a system that supports User Account Control (UAC), you may need to run the tool with Administrative privileges.</span></span> <span data-ttu-id="e6986-121">これを行うには、アプリケーションを右クリックし、**管理者として実行**です。</span><span class="sxs-lookup"><span data-stu-id="e6986-121">To do this, right-click the application, and then select **Run as administrator**.</span></span>  
  
## <a name="bam-management-utility-commands"></a><span data-ttu-id="e6986-122">BAM 管理ユーティリティのコマンド</span><span class="sxs-lookup"><span data-stu-id="e6986-122">BAM Management Utility Commands</span></span>  
 <span data-ttu-id="e6986-123">コマンドの使用法を次の表記規則に従って説明します。</span><span class="sxs-lookup"><span data-stu-id="e6986-123">The command descriptions use these conventions:</span></span>  
  
-   <span data-ttu-id="e6986-124">角かっこ ([]) は省略可能なパラメーターであることを示します。</span><span class="sxs-lookup"><span data-stu-id="e6986-124">The square brackets ([]) indicate an optional parameter.</span></span>  
  
-   <span data-ttu-id="e6986-125">山かっこ (<>) は必須のパラメーターであることを示します。</span><span class="sxs-lookup"><span data-stu-id="e6986-125">The angled brackets (<>) indicate a required parameter.</span></span>  
  
-   <span data-ttu-id="e6986-126">中かっこ ({}) は、かっこ内に列挙されている項目から、いずれか 1 つを選択する必要があることを示します。</span><span class="sxs-lookup"><span data-stu-id="e6986-126">The braces ({}) indicate that one item should be selected from the enumerated list.</span></span>  
  
-   <span data-ttu-id="e6986-127">セキュリティ アカウントには、NT グループ アカウントを使用することも、個々の NT ユーザー アカウントを使用することもできます。</span><span class="sxs-lookup"><span data-stu-id="e6986-127">A security account can be either an NT group or an individual NT user account.</span></span>  
  
-   <span data-ttu-id="e6986-128">BAM 定義ファイルの形式には、XML ファイルまたは BAM Excel ブック ファイル (.xls) を使用できます。</span><span class="sxs-lookup"><span data-stu-id="e6986-128">A BAM definition file can be either an XML file or a BAM Excel workbook file (.xls).</span></span>  
  
-   <span data-ttu-id="e6986-129">BAM 構成ファイルが指定されなかった場合、現在のフォルダーの BamConfiguration.xml が既定で使用されます。</span><span class="sxs-lookup"><span data-stu-id="e6986-129">If the BAM configuration file is not supplied, it defaults to BamConfiguration.xml in the current folder.</span></span>  
  
 <span data-ttu-id="e6986-130">各コマンドについては、次のトピックで説明します。</span><span class="sxs-lookup"><span data-stu-id="e6986-130">The Individual command descriptions are contained in the following topics:</span></span>  
  
-   [<span data-ttu-id="e6986-131">データベース コマンド</span><span class="sxs-lookup"><span data-stu-id="e6986-131">Database Commands</span></span>](../core/database-commands.md)  
  
-   [<span data-ttu-id="e6986-132">BAM 定義 (監視モデル) の展開コマンド</span><span class="sxs-lookup"><span data-stu-id="e6986-132">Deployment of BAM Definition (Observation Model) Commands</span></span>](../core/deployment-of-bam-definition-observation-model-commands.md)  
  
-   [<span data-ttu-id="e6986-133">インフラストラクチャ管理コマンド</span><span class="sxs-lookup"><span data-stu-id="e6986-133">Infrastructure Management Commands</span></span>](../core/infrastructure-management-commands.md)  
  
-   [<span data-ttu-id="e6986-134">アクティビティ管理コマンド</span><span class="sxs-lookup"><span data-stu-id="e6986-134">Activity Management Commands</span></span>](../core/activity-management-commands.md)  
  
-   [<span data-ttu-id="e6986-135">ビュー管理コマンド</span><span class="sxs-lookup"><span data-stu-id="e6986-135">View Management Commands</span></span>](../core/view-management-commands.md)  
  
-   [<span data-ttu-id="e6986-136">Alert Management コマンド</span><span class="sxs-lookup"><span data-stu-id="e6986-136">Alert Management Commands</span></span>](../core/alert-management-commands.md)  
  
-   [<span data-ttu-id="e6986-137">ユーザー管理コマンド</span><span class="sxs-lookup"><span data-stu-id="e6986-137">User Management Commands</span></span>](../core/user-management-commands.md)  
  
-   [<span data-ttu-id="e6986-138">警告サブスクリプション管理コマンド</span><span class="sxs-lookup"><span data-stu-id="e6986-138">Alert Subscription Management Commands</span></span>](../core/alert-subscription-management-commands.md)  
  
-   [<span data-ttu-id="e6986-139">インターセプター管理コマンド</span><span class="sxs-lookup"><span data-stu-id="e6986-139">Interceptor Management Commands</span></span>](../core/interceptor-management-commands.md)  
  
## <a name="displaying-the-bam-management-utility-help"></a><span data-ttu-id="e6986-140">BAM 管理ユーティリティのヘルプの表示</span><span class="sxs-lookup"><span data-stu-id="e6986-140">Displaying the BAM Management Utility Help</span></span>  
 <span data-ttu-id="e6986-141">使用する、 **/しますか?**</span><span class="sxs-lookup"><span data-stu-id="e6986-141">You use the **/?**</span></span> <span data-ttu-id="e6986-142">または、 **BAM 管理ユーティリティのヘルプ**を BAM 管理ユーティリティのヘルプ ファイルを表示するコマンド。</span><span class="sxs-lookup"><span data-stu-id="e6986-142">or the **help BAM Management utility** command to display the Help file for the BAM Management utility.</span></span>  
  
#### <a name="to-display-the-help-file-for-the-bam-management-utility"></a><span data-ttu-id="e6986-143">BAM 管理ユーティリティのヘルプ ファイルを表示するには</span><span class="sxs-lookup"><span data-stu-id="e6986-143">To display the Help file for the BAM Management utility</span></span>  
  
1.  <span data-ttu-id="e6986-144">コマンド プロンプトから次のディレクトリを参照: C:\Program files \microsoft BizTalk Server\<バージョン\>\Tracking\\です。</span><span class="sxs-lookup"><span data-stu-id="e6986-144">From a command prompt, browse to the following directory: C:\Program Files\Microsoft BizTalk Server \<version\>\Tracking\\.</span></span>  
  
2.  <span data-ttu-id="e6986-145">型**bm**または**bm ヘルプ**です。</span><span class="sxs-lookup"><span data-stu-id="e6986-145">Type **bm** or **bm help**.</span></span>  
  
3.  <span data-ttu-id="e6986-146">Enter キーを押します。</span><span class="sxs-lookup"><span data-stu-id="e6986-146">Press ENTER.</span></span>