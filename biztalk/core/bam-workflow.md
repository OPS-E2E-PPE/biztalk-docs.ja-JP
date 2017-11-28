---
title: "BAM ワークフロー |Microsoft ドキュメント"
ms.custom: 
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: 
ms.suite: 
ms.tgt_pltfrm: 
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
caps.latest.revision: "9"
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: 19356d6191963ec441f0b85c0e987c8515dcf1f4
ms.sourcegitcommit: cb908c540d8f1a692d01dc8f313e16cb4b4e696d
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 09/20/2017
---
# <a name="bam-workflow"></a><span data-ttu-id="fe37c-102">BAM のワークフロー</span><span class="sxs-lookup"><span data-stu-id="fe37c-102">BAM Workflow</span></span>
<span data-ttu-id="fe37c-103">ビジネス アクティビティ監視と連携する 4 つのユーザー ロールと、ロールで使用されるツールを次に示します。</span><span class="sxs-lookup"><span data-stu-id="fe37c-103">The following figure shows the four user roles who work with Business Activity Monitoring, and the tools that they use.</span></span>  
  
 ![](../core/media/ebiz-tut-bamworkflow.gif "ebiz_tut_bamworkflow")  
<span data-ttu-id="fe37c-104">BAM ロール</span><span class="sxs-lookup"><span data-stu-id="fe37c-104">BAM Roles</span></span>  
  
 <span data-ttu-id="fe37c-105">次の手順では、ビジネス アクティビティ監視を使用するためのワークフローの概要について説明します。</span><span class="sxs-lookup"><span data-stu-id="fe37c-105">The following steps provide a high-level overview of the workflow for using Business Activity Monitoring.</span></span>  
  
## <a name="specifying-the-business-data-to-collect"></a><span data-ttu-id="fe37c-106">収集するビジネス データの指定</span><span class="sxs-lookup"><span data-stu-id="fe37c-106">Specifying the business data to collect</span></span>  
 <span data-ttu-id="fe37c-107">ビジネス データは次のように収集されます。</span><span class="sxs-lookup"><span data-stu-id="fe37c-107">Business data is collected in the following manner:</span></span>  
  
-   <span data-ttu-id="fe37c-108">ビジネス アナリストは、BAM アクティビティ ウィザードを使用して、すべてのビジネス ユーザー用に収集するデータを指定します。</span><span class="sxs-lookup"><span data-stu-id="fe37c-108">The business analyst uses the BAM Activity Wizard to specify what data to collect for all business users.</span></span>  
  
-   <span data-ttu-id="fe37c-109">また、BAM ビュー ウィザードを使用して、ビジネス ユーザーのカテゴリごとにビューを定義します。</span><span class="sxs-lookup"><span data-stu-id="fe37c-109">The business analyst uses the BAM View Wizard to define the view for each category of business user.</span></span>  
  
-   <span data-ttu-id="fe37c-110">定義が終了した後、BAM 定義ブックと呼ばれる Microsoft® Excel ブックに、アクティビティとビューを保存します。</span><span class="sxs-lookup"><span data-stu-id="fe37c-110">When finished, he saves the activities and views in a Microsoft® Excel Workbook called the BAM Definition Workbook.</span></span>  
  
-   <span data-ttu-id="fe37c-111">ビジネス アナリストは BAM 定義ブックを XML にエクスポートします。</span><span class="sxs-lookup"><span data-stu-id="fe37c-111">The business analyst exports the BAM Definition Workbook to XML.</span></span>  
  
-   <span data-ttu-id="fe37c-112">システム管理者と開発者は、この XML を使用してロールを実行します。</span><span class="sxs-lookup"><span data-stu-id="fe37c-112">The system administrator and developer use the XML to perform their roles.</span></span>  
  
-   <span data-ttu-id="fe37c-113">BAM 定義ブックを使用するための手順にある[ビジネス アクティビティの定義および Excel でビュー](../core/defining-business-activities-and-views-in-excel.md)です。</span><span class="sxs-lookup"><span data-stu-id="fe37c-113">Instructions for using the BAM Definition Workbook are located in [Defining Business Activities and Views in Excel](../core/defining-business-activities-and-views-in-excel.md).</span></span>  
  
## <a name="managing-the-bam-infrastructure"></a><span data-ttu-id="fe37c-114">BAM インフラストラクチャの管理</span><span class="sxs-lookup"><span data-stu-id="fe37c-114">Managing the BAM Infrastructure</span></span>  
 <span data-ttu-id="fe37c-115">ビジネス アナリストが必要な BAM ビューを定義した後、システム管理者は BAM 管理ユーティリティ (BM.EXE) というコマンド ライン ツールを使用して、BAM 定義ブック、またはブックからエクスポートした XML から BAM インフラストラクチャを展開します。</span><span class="sxs-lookup"><span data-stu-id="fe37c-115">After the business analyst has defined the BAM view he wants, the system administrator uses the BAM management utility (BM.EXE), a command-line tool, to deploy the BAM infrastructure from the BAM Definition Workbook or the XML exported from the workbook.</span></span>  
  
 <span data-ttu-id="fe37c-116">BAM 管理ユーティリティを使用すると、BAM ビューのサポートに必要なテーブル、トリガー、DTS パッケージ、および OLAP キューブが動的に作成されます。</span><span class="sxs-lookup"><span data-stu-id="fe37c-116">The BAM management utility dynamically creates the tables, triggers, DTS packages, and OLAP cubes necessary to support the BAM view.</span></span>  
  
 <span data-ttu-id="fe37c-117">ビジネス アナリストが別の BAM ビューを定義したり、既存の BAM ビューを変更するたびに、システム管理者は BAM 定義ブックを再展開する必要があります。</span><span class="sxs-lookup"><span data-stu-id="fe37c-117">Each time the business analyst defines a different BAM view, or changes an existing BAM view, the system administrator must redeploy the BAM Definition Workbook.</span></span>  
  
## <a name="mapping-the-xml-to-an-orchestration"></a><span data-ttu-id="fe37c-118">オーケストレーションへの XML のマッピング</span><span class="sxs-lookup"><span data-stu-id="fe37c-118">Mapping the XML to an orchestration</span></span>  
 <span data-ttu-id="fe37c-119">ビジネス アナリストが BAM 定義ブックを XML にエクスポートした後、開発者は XML ファイルを追跡プロファイル エディターにインポートします。</span><span class="sxs-lookup"><span data-stu-id="fe37c-119">After the business analyst exports the BAM Definition Workbook to XML, the developer imports the XML file into the Tracking Profile Editor.</span></span> <span data-ttu-id="fe37c-120">開発者は、XML をオーケストレーションにマップして、ビジネス アナリストに必要な情報を実装します。</span><span class="sxs-lookup"><span data-stu-id="fe37c-120">The developer implements the business analyst's information requirements, mapping the XML to an orchestration.</span></span>  
  
 <span data-ttu-id="fe37c-121">XML をオーケストレーションにマップするには、追跡プロファイル エディター (TPE) を使用して次の手順を実行します。</span><span class="sxs-lookup"><span data-stu-id="fe37c-121">Using the Tracking Profile Editor, the developer performs the following steps to map the XML to an orchestration:</span></span>  
  
-   <span data-ttu-id="fe37c-122">BizTalk 管理データベース (構成データベース) に格納されている展開済みのアセンブリを読み込みます。</span><span class="sxs-lookup"><span data-stu-id="fe37c-122">Loads the deployed assembly that is stored in the BizTalk Management database (also known as the Configuration database).</span></span> <span data-ttu-id="fe37c-123">展開済みのアセンブリには、上記の手順 1. でビジネス アナリストが指定した要件に対応する 1 つ以上のオーケストレーションが含まれています。</span><span class="sxs-lookup"><span data-stu-id="fe37c-123">The deployed assembly contains one or more orchestrations corresponding to the requirements that the business analyst specified in Step 1 above.</span></span>  
  
-   <span data-ttu-id="fe37c-124">オーケストレーションから抽出するデータを定義します。</span><span class="sxs-lookup"><span data-stu-id="fe37c-124">Defines the data to be extracted from an orchestration.</span></span> <span data-ttu-id="fe37c-125">これには、メッセージ スキーマやオーケストレーション図形から適切なビジネス マイルストーン (イベント) やデータ項目フォルダーに項目をドロップします。</span><span class="sxs-lookup"><span data-stu-id="fe37c-125">You do this by dropping items from the message schemas and orchestration shapes into the appropriate business milestone (event) and data item folders.</span></span>  
  
-   <span data-ttu-id="fe37c-126">作業が終了した後、ファイルを BizTalk® Server 追跡 (.btt) ファイルとして Visual SourceSafe などの格納データベースに保存します。</span><span class="sxs-lookup"><span data-stu-id="fe37c-126">When he is finished, he saves the profile as a BizTalk® Server tracking (.btt) file, to a storage database such as Visual SourceSafe.</span></span>  
  
 <span data-ttu-id="fe37c-127">開発者は .btt ファイルをテスト データベースに展開し、結合テストを行って結果を確認します。</span><span class="sxs-lookup"><span data-stu-id="fe37c-127">The developer deploys the .btt file to a testing database, and verifies the result through integration testing.</span></span>  
  
## <a name="deploying-the-tracking-profile"></a><span data-ttu-id="fe37c-128">追跡プロファイルの展開</span><span class="sxs-lookup"><span data-stu-id="fe37c-128">Deploying the Tracking Profile</span></span>  
 <span data-ttu-id="fe37c-129">システム管理者は、追跡プロファイル エディターを使用して、1 つ以上の BizTalk 管理データベースにプロファイルを展開します。</span><span class="sxs-lookup"><span data-stu-id="fe37c-129">Using the Tracking Profile Editor, the system administrator deploys the profile to one or more BizTalk Management databases.</span></span>  
  
 <span data-ttu-id="fe37c-130">開発者がオーケストレーションを変更したり、ビジネス ユーザーの要件が変わって追跡するデータが増えるたびに、システム管理者は、コマンド ライン ユーティリティの bttdeploy.exe を使用して追跡プロファイルを再展開する必要があります。</span><span class="sxs-lookup"><span data-stu-id="fe37c-130">Each time the developer changes the orchestration, or the requirements of the business users change and they want to track more data, the system administrator needs to redeploy the tracking profile using the bttdeploy.exe command line utility.</span></span>  
  
## <a name="viewing-the-business-data"></a><span data-ttu-id="fe37c-131">ビジネス データの表示</span><span class="sxs-lookup"><span data-stu-id="fe37c-131">Viewing the business data</span></span>  
 <span data-ttu-id="fe37c-132">ビジネス ユーザーは、BM.exe ユーティリティによって生成される _LiveData ブックを使用します。</span><span class="sxs-lookup"><span data-stu-id="fe37c-132">The business user uses the _LiveData workbook, which is produced by the BM.exe utility.</span></span> <span data-ttu-id="fe37c-133">_LiveData ブックを開くたびに新しいライブ データが受信されます。このデータはビジネス プロセスの特定の側面を監視するために収集されたものです。</span><span class="sxs-lookup"><span data-stu-id="fe37c-133">Each time the business user opens the _LiveData workbook, he receives a new live version of the data that is collected to monitor a specific aspect of the business process.</span></span>  
  
-   <span data-ttu-id="fe37c-134">リアルタイム集計として定義されているデータを表示するには、ビジネス ユーザーだけが必要 をクリックする**更新**データを表示するブックでします。</span><span class="sxs-lookup"><span data-stu-id="fe37c-134">To view data that is defined as real-time aggregation, the business user just needs to click **Refresh** in the workbook to view the data.</span></span>  
  
-   <span data-ttu-id="fe37c-135">集計データがリアルタイムでない場合は、スケジュール設定された DTS パッケージの実行時に取得されたビジネス データのスナップショットを参照できます。</span><span class="sxs-lookup"><span data-stu-id="fe37c-135">If the aggregation data is not real-time, the business user views a snapshot of the business data that is taken at the time that the scheduled DTS package runs.</span></span>  
  
-   <span data-ttu-id="fe37c-136">組織で共同作業が必要な場合、ビジネス ユーザーは BAS Web サイトからライブ データにアクセスできます。</span><span class="sxs-lookup"><span data-stu-id="fe37c-136">If your organization has collaboration requirements, the business user can access the live data from the BAS Web site.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="fe37c-137">参照</span><span class="sxs-lookup"><span data-stu-id="fe37c-137">See Also</span></span>  
 <span data-ttu-id="fe37c-138">[Excel でビジネス アクティビティとビューを定義します。](../core/defining-business-activities-and-views-in-excel.md) </span><span class="sxs-lookup"><span data-stu-id="fe37c-138">[Defining Business Activities and Views in Excel](../core/defining-business-activities-and-views-in-excel.md) </span></span>  
 [<span data-ttu-id="fe37c-139">BAM によるビジネス アクティビティの監視</span><span class="sxs-lookup"><span data-stu-id="fe37c-139">Monitoring Business Activities with BAM</span></span>](../core/monitoring-business-activities-with-bam.md)