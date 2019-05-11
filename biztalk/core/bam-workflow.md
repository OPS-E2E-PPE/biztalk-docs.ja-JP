---
title: BAM のワークフロー |Microsoft Docs
ms.custom: ''
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: ''
ms.suite: ''
ms.tgt_pltfrm: ''
ms.topic: article
helpviewer_keywords:
- monitoring business activities [BAM], collecting business data
- XML files
- orchestrations, XML files
- business activities, business data
- infrastructure, managing [BAM]
- business activities, monitoring
- monitoring business activities [BAM], monitoring flow
- managing [BAM], infrastructure
- monitoring business activities [BAM], viewing business data
- managing [orchestrations], mapping XML to orchestrations
ms.assetid: 8b4ae145-3e16-4bb8-bfba-09b9f666218d
caps.latest.revision: 9
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: 82cfe7fe5f29994c72b9f9026c03321ba44e3575
ms.sourcegitcommit: d27732e569b0897361dfaebca8352aa97bb7efe1
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 05/10/2019
ms.locfileid: "65529163"
---
# <a name="bam-workflow"></a><span data-ttu-id="6431c-102">BAM のワークフロー</span><span class="sxs-lookup"><span data-stu-id="6431c-102">BAM Workflow</span></span>
<span data-ttu-id="6431c-103">次の図は、ビジネス アクティビティの監視、および使用するツールを使用する 4 つのユーザー ロールを示します。</span><span class="sxs-lookup"><span data-stu-id="6431c-103">The following figure shows the four user roles who work with Business Activity Monitoring, and the tools that they use.</span></span>  
  
 <span data-ttu-id="6431c-104">![](../core/media/ebiz-tut-bamworkflow.gif "ebiz_tut_bamworkflow")</span><span class="sxs-lookup"><span data-stu-id="6431c-104">![](../core/media/ebiz-tut-bamworkflow.gif "ebiz_tut_bamworkflow")</span></span>  
<span data-ttu-id="6431c-105">BAM ロール</span><span class="sxs-lookup"><span data-stu-id="6431c-105">BAM Roles</span></span>  
  
 <span data-ttu-id="6431c-106">次の手順では、ビジネス アクティビティの監視を使用するため、ワークフローの概要を提供します。</span><span class="sxs-lookup"><span data-stu-id="6431c-106">The following steps provide a high-level overview of the workflow for using Business Activity Monitoring.</span></span>  
  
## <a name="specifying-the-business-data-to-collect"></a><span data-ttu-id="6431c-107">ビジネス データの収集を指定します。</span><span class="sxs-lookup"><span data-stu-id="6431c-107">Specifying the business data to collect</span></span>  
 <span data-ttu-id="6431c-108">次のようにビジネス データが収集されます。</span><span class="sxs-lookup"><span data-stu-id="6431c-108">Business data is collected in the following manner:</span></span>  
  
-   <span data-ttu-id="6431c-109">ビジネス アナリストは BAM アクティビティ ウィザードを使用して、すべてのビジネス ユーザーを収集するデータを指定します。</span><span class="sxs-lookup"><span data-stu-id="6431c-109">The business analyst uses the BAM Activity Wizard to specify what data to collect for all business users.</span></span>  
  
-   <span data-ttu-id="6431c-110">ビジネス アナリストは BAM ビュー ウィザードを使用して、ビジネス ユーザーの各カテゴリのビューを定義します。</span><span class="sxs-lookup"><span data-stu-id="6431c-110">The business analyst uses the BAM View Wizard to define the view for each category of business user.</span></span>  
  
-   <span data-ttu-id="6431c-111">アクティビティが完了すると、保存し、Microsoft® Excel ブック内のビューには、BAM 定義ブックが呼び出されます。</span><span class="sxs-lookup"><span data-stu-id="6431c-111">When finished, he saves the activities and views in a Microsoft® Excel Workbook called the BAM Definition Workbook.</span></span>  
  
-   <span data-ttu-id="6431c-112">ビジネス アナリストは BAM 定義ブックを XML にエクスポートします。</span><span class="sxs-lookup"><span data-stu-id="6431c-112">The business analyst exports the BAM Definition Workbook to XML.</span></span>  
  
-   <span data-ttu-id="6431c-113">システム管理者および開発者は、その役割を実行するのに、XML を使用します。</span><span class="sxs-lookup"><span data-stu-id="6431c-113">The system administrator and developer use the XML to perform their roles.</span></span>  
  
-   <span data-ttu-id="6431c-114">手順については、BAM 定義ブックを使用するためにある[ビジネス アクティビティの定義および Excel でのビュー](../core/defining-business-activities-and-views-in-excel.md)します。</span><span class="sxs-lookup"><span data-stu-id="6431c-114">Instructions for using the BAM Definition Workbook are located in [Defining Business Activities and Views in Excel](../core/defining-business-activities-and-views-in-excel.md).</span></span>  
  
## <a name="managing-the-bam-infrastructure"></a><span data-ttu-id="6431c-115">BAM インフラストラクチャの管理</span><span class="sxs-lookup"><span data-stu-id="6431c-115">Managing the BAM Infrastructure</span></span>  
 <span data-ttu-id="6431c-116">システム管理者が、BAM 管理ユーティリティ (BM を使用して、ビジネス アナリストが希望している BAM ビューを定義した後。EXE) では、ブックからエクスポートされたコマンド ライン ツール、BAM 定義ブックまたは XML から BAM インフラストラクチャを展開します。</span><span class="sxs-lookup"><span data-stu-id="6431c-116">After the business analyst has defined the BAM view he wants, the system administrator uses the BAM management utility (BM.EXE), a command-line tool, to deploy the BAM infrastructure from the BAM Definition Workbook or the XML exported from the workbook.</span></span>  
  
 <span data-ttu-id="6431c-117">BAM 管理ユーティリティを動的に作成、テーブル、トリガー、DTS パッケージ、および OLAP キューブ、BAM ビューをサポートするために必要です。</span><span class="sxs-lookup"><span data-stu-id="6431c-117">The BAM management utility dynamically creates the tables, triggers, DTS packages, and OLAP cubes necessary to support the BAM view.</span></span>  
  
 <span data-ttu-id="6431c-118">たびに、ビジネス アナリストが別の BAM ビューを定義または既存の BAM ビューの変更、システム管理者は、BAM 定義ブックを再デプロイする必要があります。</span><span class="sxs-lookup"><span data-stu-id="6431c-118">Each time the business analyst defines a different BAM view, or changes an existing BAM view, the system administrator must redeploy the BAM Definition Workbook.</span></span>  
  
## <a name="mapping-the-xml-to-an-orchestration"></a><span data-ttu-id="6431c-119">オーケストレーションに XML のマッピング</span><span class="sxs-lookup"><span data-stu-id="6431c-119">Mapping the XML to an orchestration</span></span>  
 <span data-ttu-id="6431c-120">ビジネス アナリストが、BAM 定義ブックを XML にエクスポートした後、開発者は、追跡プロファイル エディターに XML ファイルをインポートします。</span><span class="sxs-lookup"><span data-stu-id="6431c-120">After the business analyst exports the BAM Definition Workbook to XML, the developer imports the XML file into the Tracking Profile Editor.</span></span> <span data-ttu-id="6431c-121">開発者は、オーケストレーションに XML のマッピング、ビジネス アナリストの情報の要件を実装します。</span><span class="sxs-lookup"><span data-stu-id="6431c-121">The developer implements the business analyst's information requirements, mapping the XML to an orchestration.</span></span>  
  
 <span data-ttu-id="6431c-122">追跡プロファイル エディターを使用して、開発者は、XML をオーケストレーションにマップする、次の手順を実行します。</span><span class="sxs-lookup"><span data-stu-id="6431c-122">Using the Tracking Profile Editor, the developer performs the following steps to map the XML to an orchestration:</span></span>  
  
- <span data-ttu-id="6431c-123">BizTalk 管理データベース (構成データベースとも呼ばれます) に格納されている展開済みのアセンブリを読み込みます。</span><span class="sxs-lookup"><span data-stu-id="6431c-123">Loads the deployed assembly that is stored in the BizTalk Management database (also known as the Configuration database).</span></span> <span data-ttu-id="6431c-124">展開済みのアセンブリには、ビジネス アナリストは、上記の手順 1. で指定されている要件に対応する 1 つまたは複数のオーケストレーションが含まれています。</span><span class="sxs-lookup"><span data-stu-id="6431c-124">The deployed assembly contains one or more orchestrations corresponding to the requirements that the business analyst specified in Step 1 above.</span></span>  
  
- <span data-ttu-id="6431c-125">オーケストレーションから抽出されるデータを定義します。</span><span class="sxs-lookup"><span data-stu-id="6431c-125">Defines the data to be extracted from an orchestration.</span></span> <span data-ttu-id="6431c-126">メッセージのスキーマから項目を削除することにより、これを行うし、オーケストレーション図形に、適切なビジネス マイルス トーン (イベント) とデータ項目フォルダー。</span><span class="sxs-lookup"><span data-stu-id="6431c-126">You do this by dropping items from the message schemas and orchestration shapes into the appropriate business milestone (event) and data item folders.</span></span>  
  
- <span data-ttu-id="6431c-127">彼が完了したら、彼プロファイルとして保存を BizTalk® Server 追跡 (.btt) ファイル、Visual SourceSafe などの格納データベースにします。</span><span class="sxs-lookup"><span data-stu-id="6431c-127">When he is finished, he saves the profile as a BizTalk® Server tracking (.btt) file, to a storage database such as Visual SourceSafe.</span></span>  
  
  <span data-ttu-id="6431c-128">開発者は、テスト データベースに .btt ファイルを展開し、統合テストを行って結果を確認します。</span><span class="sxs-lookup"><span data-stu-id="6431c-128">The developer deploys the .btt file to a testing database, and verifies the result through integration testing.</span></span>  
  
## <a name="deploying-the-tracking-profile"></a><span data-ttu-id="6431c-129">追跡プロファイルの展開</span><span class="sxs-lookup"><span data-stu-id="6431c-129">Deploying the Tracking Profile</span></span>  
 <span data-ttu-id="6431c-130">追跡プロファイル エディターを使用して、システム管理者は、1 つまたは複数の BizTalk 管理データベースにプロファイルを展開します。</span><span class="sxs-lookup"><span data-stu-id="6431c-130">Using the Tracking Profile Editor, the system administrator deploys the profile to one or more BizTalk Management databases.</span></span>  
  
 <span data-ttu-id="6431c-131">たびに、開発者は、オーケストレーション、またはビジネス ユーザーの変更の要件を変更しより多くのデータを追跡する、システム管理者は、bttdeploy.exe コマンド ライン ユーティリティを使用して追跡プロファイルを再展開する必要があります。</span><span class="sxs-lookup"><span data-stu-id="6431c-131">Each time the developer changes the orchestration, or the requirements of the business users change and they want to track more data, the system administrator needs to redeploy the tracking profile using the bttdeploy.exe command line utility.</span></span>  
  
## <a name="viewing-the-business-data"></a><span data-ttu-id="6431c-132">ビジネス データの表示</span><span class="sxs-lookup"><span data-stu-id="6431c-132">Viewing the business data</span></span>  
 <span data-ttu-id="6431c-133">ビジネス ユーザーは、BM.exe ユーティリティによって生成される _LiveData ブックを使用します。</span><span class="sxs-lookup"><span data-stu-id="6431c-133">The business user uses the _LiveData workbook, which is produced by the BM.exe utility.</span></span> <span data-ttu-id="6431c-134">ビジネス ユーザーが _LiveData ブックを開くたびに、ビジネス プロセスの特定の側面を監視するために収集されるデータの新しいライブ バージョンが表示されます。</span><span class="sxs-lookup"><span data-stu-id="6431c-134">Each time the business user opens the _LiveData workbook, he receives a new live version of the data that is collected to monitor a specific aspect of the business process.</span></span>  
  
-   <span data-ttu-id="6431c-135">リアルタイム集計として定義されているデータを表示するビジネス ユーザーだけが必要 をクリックする**更新**データを表示するブックでします。</span><span class="sxs-lookup"><span data-stu-id="6431c-135">To view data that is defined as real-time aggregation, the business user just needs to click **Refresh** in the workbook to view the data.</span></span>  
  
-   <span data-ttu-id="6431c-136">集計データがリアルタイムでない場合、ビジネス ユーザーは、スケジュールされた DTS パッケージの実行時に実行されるビジネス データのスナップショットを表示します。</span><span class="sxs-lookup"><span data-stu-id="6431c-136">If the aggregation data is not real-time, the business user views a snapshot of the business data that is taken at the time that the scheduled DTS package runs.</span></span>  
  
-   <span data-ttu-id="6431c-137">お客様の組織は、コラボレーションの要件がある、ビジネス ユーザーは BAS Web サイトからライブ データをアクセスできます。</span><span class="sxs-lookup"><span data-stu-id="6431c-137">If your organization has collaboration requirements, the business user can access the live data from the BAS Web site.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="6431c-138">参照</span><span class="sxs-lookup"><span data-stu-id="6431c-138">See Also</span></span>  
 <span data-ttu-id="6431c-139">[Excel でビジネス アクティビティとビューの定義](../core/defining-business-activities-and-views-in-excel.md) </span><span class="sxs-lookup"><span data-stu-id="6431c-139">[Defining Business Activities and Views in Excel](../core/defining-business-activities-and-views-in-excel.md) </span></span>  
 [<span data-ttu-id="6431c-140">BAM によるビジネス アクティビティの監視</span><span class="sxs-lookup"><span data-stu-id="6431c-140">Monitoring Business Activities with BAM</span></span>](../core/monitoring-business-activities-with-bam.md)