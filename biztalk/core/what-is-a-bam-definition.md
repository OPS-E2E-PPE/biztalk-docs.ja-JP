---
title: "BAM 定義について | Microsoft Docs"
ms.custom: 
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: 
ms.suite: 
ms.tgt_pltfrm: 
ms.topic: article
helpviewer_keywords:
- definitions [BAM], observation models
- definitions [BAM], about BAM definitions
- definitions [BAM]
ms.assetid: 1ba1f45e-85fe-492f-8a2e-98bf3570c633
caps.latest.revision: "13"
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: 6cbc600f66be7167aabb4cf0273cb1c0bda78973
ms.sourcegitcommit: cb908c540d8f1a692d01dc8f313e16cb4b4e696d
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 09/20/2017
---
# <a name="what-is-a-bam-definition"></a><span data-ttu-id="b0dfe-103">BAM 定義について</span><span class="sxs-lookup"><span data-stu-id="b0dfe-103">What Is a BAM Definition?</span></span>
<span data-ttu-id="b0dfe-104">BAM 定義は、BAM 監視モデルの XML 表現で、監視するビジネス プロセスの概要を定義したものです。</span><span class="sxs-lookup"><span data-stu-id="b0dfe-104">A BAM definition is an XML representation of a BAM observation model, which is a high-level definition a business process that you want to monitor.</span></span> <span data-ttu-id="b0dfe-105">監視モデル (つまり BAM 定義) の主要部分は、マイルストーン、収集するデータ イベント (BAM アクティビティ)、データ収集の説明、および情報をユーザー (BAM ビュー) に表示する方法で構成されています。</span><span class="sxs-lookup"><span data-stu-id="b0dfe-105">The main parts of the observation model, and therefore the BAM definition, are the milestone and data events to collect (the BAM activity); a description of any data aggregations; and how to present the information to users (the BAM view).</span></span>  
  
> [!NOTE]
>  <span data-ttu-id="b0dfe-106">BAM スキーマに準拠した XML ファイルを手作業で作成することはできますが、定義が検証されないので BAM 定義を作成する方法としてはお勧めしません。</span><span class="sxs-lookup"><span data-stu-id="b0dfe-106">You can also manually create an XML file that follows the BAM schema, but this is not a recommended way to create the BAM definition as it does not provide a definition that has been validated.</span></span>  
  
 <span data-ttu-id="b0dfe-107">BAM 定義には、次の項目を含めることができます。</span><span class="sxs-lookup"><span data-stu-id="b0dfe-107">BAM definitions can contain the following items:</span></span>  
  
-   <span data-ttu-id="b0dfe-108">ビジネス アクティビティ : 有効な BAM 定義には、ビジネス アクティビティ (BAM アクティビティ) が含まれている必要があります。</span><span class="sxs-lookup"><span data-stu-id="b0dfe-108">Business activities - A valid BAM definition must contain a business activity (also referred to as a BAM activity).</span></span> <span data-ttu-id="b0dfe-109">その他の項目はすべて省略できます。</span><span class="sxs-lookup"><span data-stu-id="b0dfe-109">All other items in the definition are optional.</span></span> <span data-ttu-id="b0dfe-110">ビジネス アクティビティ定義を追加する方法の詳細については、次を参照してください。[ビジネス アクティビティの定義方法](../core/how-to-define-a-business-activity.md)です。</span><span class="sxs-lookup"><span data-stu-id="b0dfe-110">For information about adding a business activity to a definition, see [How to Define a Business Activity](../core/how-to-define-a-business-activity.md).</span></span>  
  
-   <span data-ttu-id="b0dfe-111">ビュー : ビジネス アクティビティで定義されたデータにアクセスできるユーザーを定義します。</span><span class="sxs-lookup"><span data-stu-id="b0dfe-111">Views – Views define the set of users that can access the data defined by the business activity.</span></span> <span data-ttu-id="b0dfe-112">ビューは、フィルター処理されたデータ、フィルター処理されたデータの集計、およびフィルター処理されたデータの表示方法 (ピボットグラフ レポートなど) で構成されます。</span><span class="sxs-lookup"><span data-stu-id="b0dfe-112">Views consist of filtered data, aggregations of the filtered data, and ways of presenting the filtered data, such as a PivotChart report.</span></span> <span data-ttu-id="b0dfe-113">BAM では、1 つのアクティビティに対して複数のビューを定義できます。</span><span class="sxs-lookup"><span data-stu-id="b0dfe-113">BAM supports the definition of one or more views per activity.</span></span>  
  
     <span data-ttu-id="b0dfe-114">ビューでは、次のビジネス プロセスを定義できます。</span><span class="sxs-lookup"><span data-stu-id="b0dfe-114">In a view you can define the following business processes:</span></span>  
  
    -   <span data-ttu-id="b0dfe-115">エイリアスに基づいたビジネス データ : エイリアスを使用することで、データ項目にフレンドリ名を適用することができます。</span><span class="sxs-lookup"><span data-stu-id="b0dfe-115">Aliased business data - Aliasing allows you to apply friendly names to data items.</span></span> <span data-ttu-id="b0dfe-116">たとえば、開発者は項目"LName"と呼ばれるデータを定義することがあります。</span><span class="sxs-lookup"><span data-stu-id="b0dfe-116">For example, a developer may define a data item called “LName.”</span></span> <span data-ttu-id="b0dfe-117">別名を作成するようにライブ データを"Last Name"bam の展開を表示するときに"LName"が表示されないようにします。</span><span class="sxs-lookup"><span data-stu-id="b0dfe-117">You can create an alias so that the “LName” is displayed as “Last Name” when viewing the BAM live data.</span></span>  <span data-ttu-id="b0dfe-118">エイリアスの詳細については、次を参照してください。[ビュー アイテムの名前を変更する方法](../core/how-to-rename-view-items.md)です。</span><span class="sxs-lookup"><span data-stu-id="b0dfe-118">For more information about aliasing, see [How to Rename View Items](../core/how-to-rename-view-items.md).</span></span>  
  
    -   <span data-ttu-id="b0dfe-119">期間 : アクティビティを監視する期間です。</span><span class="sxs-lookup"><span data-stu-id="b0dfe-119">Duration - The time period over which the activity is monitored.</span></span>  
  
    -   <span data-ttu-id="b0dfe-120">マイルストーン グループ : 一連のビジネス マイルストーンです。</span><span class="sxs-lookup"><span data-stu-id="b0dfe-120">Milestone groups - Sets of business milestones.</span></span> <span data-ttu-id="b0dfe-121">グループを使用して、ある期間のビジネス マイルストーンの開始または終了のいずれかを表すことができます。</span><span class="sxs-lookup"><span data-stu-id="b0dfe-121">You can use a group as either the starting or ending business milestone of a duration.</span></span>  
  
    -   <span data-ttu-id="b0dfe-122">集計 : これらは、リアルタイム集計 (RTA) またはスケジュール済みの集計 (オンライン分析処理 (OLAP)) のいずれかで、次の項目で構成されます。</span><span class="sxs-lookup"><span data-stu-id="b0dfe-122">Aggregations -  These can be either real-time aggregations (RTAs) or scheduled aggregations (also referred to as online analytical processing (OLAP)), and consist of the following items:</span></span>  
  
-   <span data-ttu-id="b0dfe-123">メジャー : Analysis Services (OLAP) キューブのファクト テーブルの列に基づいた OLAP キューブに格納されている数値のセットです。</span><span class="sxs-lookup"><span data-stu-id="b0dfe-123">Measures - A set of numeric values in an Analysis Services (OLAP) cube based on a column in the fact table of the cube.</span></span>  
  
-   <span data-ttu-id="b0dfe-124">進捗ディメンション : 処理中のアクティビティの進捗状況に関する集計を作成する場合に使用します。</span><span class="sxs-lookup"><span data-stu-id="b0dfe-124">Progress dimension - Represents the creation of aggregations with respect to the progress of activities that are still in process.</span></span>  
  
-   <span data-ttu-id="b0dfe-125">データ ディメンション : 集計を分類する場合に使用します。</span><span class="sxs-lookup"><span data-stu-id="b0dfe-125">Data dimension - Used to categorize an aggregation.</span></span> <span data-ttu-id="b0dfe-126">データ ディメンションは、BAM アクティビティに含まれている文字列型のデータ項目に基づいています。</span><span class="sxs-lookup"><span data-stu-id="b0dfe-126">Data dimensions are based on the value of string formatted data items in the BAM activity.</span></span>  
  
-   <span data-ttu-id="b0dfe-127">時間ディメンション : 定義済みの時間単位の集計を作成する場合に使用します。</span><span class="sxs-lookup"><span data-stu-id="b0dfe-127">Time dimension - Used to create aggregations across defined time segments.</span></span>  
  
-   <span data-ttu-id="b0dfe-128">数値範囲ディメンション : 特定の数値範囲のフレンドリ名に基づいた集計を分類する場合に使用します。</span><span class="sxs-lookup"><span data-stu-id="b0dfe-128">Numeric range dimension - Used to categorize aggregations based on friendly names of given numeric ranges.</span></span>  
  
 <span data-ttu-id="b0dfe-129">BAM 定義には、ビューで定義した警告の定義を含めることができます。</span><span class="sxs-lookup"><span data-stu-id="b0dfe-129">BAM definitions can contain alert definitions that are defined in the views.</span></span> <span data-ttu-id="b0dfe-130">また、ピボットテーブル レイアウトも含めることができます。</span><span class="sxs-lookup"><span data-stu-id="b0dfe-130">BAM definitions can also contain PivotTable layouts.</span></span> <span data-ttu-id="b0dfe-131">BAM 定義を展開すると、ライブ ビジネス データを含むピボットテーブル レポートは、Excel のライブ データ ブックまたは BAM ポータルを使用して表示することができます。</span><span class="sxs-lookup"><span data-stu-id="b0dfe-131">Once the BAM definition is deployed, the PivotTable reports containing the live business data that can be viewed using the Excel livedata workbook or through the BAM portal.</span></span>  
  
> [!NOTE]
>  <span data-ttu-id="b0dfe-132">Excel 用 BAM アドインを使用して作成された BAM 定義には、アラートを含めることはできません。</span><span class="sxs-lookup"><span data-stu-id="b0dfe-132">BAM definitions created using the BAM Add-in for Excel cannot contain alerts.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="b0dfe-133">参照</span><span class="sxs-lookup"><span data-stu-id="b0dfe-133">See Also</span></span>  
 <span data-ttu-id="b0dfe-134">[Excel でビジネス アクティビティとビューを定義します。](../core/defining-business-activities-and-views-in-excel.md) </span><span class="sxs-lookup"><span data-stu-id="b0dfe-134">[Defining Business Activities and Views in Excel](../core/defining-business-activities-and-views-in-excel.md) </span></span>  
 <span data-ttu-id="b0dfe-135">[BAM ポータル](../core/bam-portal.md) </span><span class="sxs-lookup"><span data-stu-id="b0dfe-135">[BAM Portal](../core/bam-portal.md) </span></span>  
 [<span data-ttu-id="b0dfe-136">BAM 動的インフラストラクチャ</span><span class="sxs-lookup"><span data-stu-id="b0dfe-136">BAM Dynamic Infrastructure</span></span>](../core/bam-dynamic-infrastructure.md)