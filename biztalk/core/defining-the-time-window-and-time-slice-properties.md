---
title: 時間枠とタイム スライスのプロパティを定義する |Microsoft ドキュメント
ms.custom: ''
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: ''
ms.suite: ''
ms.tgt_pltfrm: ''
ms.topic: article
helpviewer_keywords:
- managing [BAM], aggregations
- managing [BAM], real-time data
- Primary Import database [BAM], time properties
- aggregations [BAM], managing
- Primary Import database [BAM], real-time data
- BAMConfiguration.xml file
- aggregations [BAM], real-time data
ms.assetid: 7f07b179-da10-4702-baf7-69516c8f16a6
caps.latest.revision: 11
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: d846b03866196e0a31facbbff68db50ec6a00a5f
ms.sourcegitcommit: cb908c540d8f1a692d01dc8f313e16cb4b4e696d
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 09/20/2017
ms.locfileid: "22239058"
---
# <a name="defining-the-time-window-and-time-slice-properties"></a><span data-ttu-id="cf3fe-102">TimeWindow プロパティと TimeSlice プロパティの定義</span><span class="sxs-lookup"><span data-stu-id="cf3fe-102">Defining the Time Window and Time Slice Properties</span></span>
<span data-ttu-id="cf3fe-103">管理者は、BAMConfiguration.xml ファイルの TimeWindow プロパティと TimeSlice プロパティを使用して、BAM プライマリ インポート データベースのリアルタイム集計のテーブルに格納されるデータの有効期間を定義することができます。</span><span class="sxs-lookup"><span data-stu-id="cf3fe-103">Administrators use the TimeWindow and the TimeSlice properties in the BAMConfiguration.xml file to define the life of the data in the real-time aggregation tables in the BAM primary import database.</span></span>  
  
> [!NOTE]
>  <span data-ttu-id="cf3fe-104">BAM 構成ファイルに加えた変更を反映するには、管理者が、現在展開している BAM 構成の展開を解除し、更新した BAMConfiguration.xml を展開する必要があります。</span><span class="sxs-lookup"><span data-stu-id="cf3fe-104">To enact the changes they make in the BAM configuration file, administrators must undeploy the current BAM configuration, and then deploy the updated BAMConfiguration.xml.</span></span>  
  
 <span data-ttu-id="cf3fe-105">BAM 定義を展開解除については、次を参照してください。 [BAM 定義を削除する方法](../core/how-to-remove-bam-definitions.md)です。</span><span class="sxs-lookup"><span data-stu-id="cf3fe-105">For information about undeploying a BAM definition, see [How to Remove BAM Definitions](../core/how-to-remove-bam-definitions.md).</span></span> <span data-ttu-id="cf3fe-106">BAM 定義の展開方法の詳細については、次を参照してください。 [BAM 定義を展開する方法](../core/how-to-deploy-bam-definitions.md)です。</span><span class="sxs-lookup"><span data-stu-id="cf3fe-106">For information about deploying a BAM definition, see [How to Deploy BAM Definitions](../core/how-to-deploy-bam-definitions.md).</span></span>  
  
 <span data-ttu-id="cf3fe-107">BAM インフラストラクチャの展開を解除せずに TimeWindow プロパティと TimeSlice プロパティの値を変更する必要がある場合は、BAM プライマリ インポート データベースの BAM_Metadata_Activities テーブルの列を編集することができます。</span><span class="sxs-lookup"><span data-stu-id="cf3fe-107">If you want to change the TimeWindow and TimeSlice values without undeploying the BAM infrastructure, you can modifying the columns in the BAM_Metadata_Activities table in the BAM primary import database.</span></span>  
  
## <a name="timeslice"></a><span data-ttu-id="cf3fe-108">TimeSlice</span><span class="sxs-lookup"><span data-stu-id="cf3fe-108">TimeSlice</span></span>  
 <span data-ttu-id="cf3fe-109">TimeSlice プロパティは、完了した BAM インスタンス データのグループ化に使用します。</span><span class="sxs-lookup"><span data-stu-id="cf3fe-109">You use the TimeSlice property to group completed BAM instance data.</span></span> <span data-ttu-id="cf3fe-110">このプロパティでは、データが BAM プライマリ インポート データベースに書き込まれた時刻を BAM インスタンス データのグループ化に使用しています。</span><span class="sxs-lookup"><span data-stu-id="cf3fe-110">The TimeSlice property uses time that the data is written to the BAM primary import database to group BAM instance data.</span></span>  
  
 <span data-ttu-id="cf3fe-111">インスタンス A が完了し、1/1/2000 で BAM プライマリ インポート データベースに永続化など、午前 1時 02分</span><span class="sxs-lookup"><span data-stu-id="cf3fe-111">For example, instance A is completed and persisted in the BAM primary import database at 1/1/2000 1:02 a.m.</span></span> <span data-ttu-id="cf3fe-112">インスタンス B が完了し、1/1/2000 で BAM プライマリ インポート データベースに永続化午前 1時 04分</span><span class="sxs-lookup"><span data-stu-id="cf3fe-112">Instance B is completed and persisted in the BAM primary import database at 1/1/2000 1:04 a.m.</span></span> <span data-ttu-id="cf3fe-113">TimeSlice プロパティの値を 5 分に設定した場合、インスタンス A と B のインスタンスは一緒に分類されます。</span><span class="sxs-lookup"><span data-stu-id="cf3fe-113">If you set the value of the TimeSlice property to five minutes, instance A and instance B are grouped together.</span></span>  
  
#### <a name="to-change-the-timeslice-value-in-the-bam-configuration-file"></a><span data-ttu-id="cf3fe-114">BAM 構成ファイルで TimeSlice プロパティの値を変更するには</span><span class="sxs-lookup"><span data-stu-id="cf3fe-114">To change the TimeSlice value in the BAM Configuration file</span></span>  
  
-   <span data-ttu-id="cf3fe-115">BAM 構成ファイルで、次の行の値を変更します。</span><span class="sxs-lookup"><span data-stu-id="cf3fe-115">Change the value in this line of the BAM Configuration file:</span></span>  
  
    ```  
    <Property Name="RTATimeSlice">5</Property>  
    ```  
  
#### <a name="to-change-the-timeslice-value-in-the-bammetadataactivities-table"></a><span data-ttu-id="cf3fe-116">BAM_Metadata_Activities テーブルで timeslice プロパティの値を変更するには</span><span class="sxs-lookup"><span data-stu-id="cf3fe-116">To change the TimeSlice value in the BAM_Metadata_Activities table</span></span>  
  
-   <span data-ttu-id="cf3fe-117">BAMPrimaryImport データベースの bam_Metadata_Activities テーブルにある RTATimeSlice プロパティの値を変更します。</span><span class="sxs-lookup"><span data-stu-id="cf3fe-117">Modify the RTATimeSlice values, located in the bam_Metadata_Activities table in the BAMPrimaryImport database.</span></span> <span data-ttu-id="cf3fe-118">1 つ以上のアクティビティを対象としたリアルタイム集計 (TRA) を複数展開している場合は、RTA ごとに別の時間帯を指定できます。</span><span class="sxs-lookup"><span data-stu-id="cf3fe-118">If you deploy multiple real-time aggregations (RTA) for one or more activities, you have the option to specify a different time window for each RTA.</span></span>  
  
    > [!NOTE]
    >  <span data-ttu-id="cf3fe-119">RTAWindow の値は整数値で指定する必要があり、時間の単位は常に分になります。</span><span class="sxs-lookup"><span data-stu-id="cf3fe-119">The value of RTAWindow must be an integer and the time unit is always minutes.</span></span>  
  
## <a name="timewindow"></a><span data-ttu-id="cf3fe-120">TimeWindow</span><span class="sxs-lookup"><span data-stu-id="cf3fe-120">TimeWindow</span></span>  
 <span data-ttu-id="cf3fe-121">CubeUpdate DTS パッケージを実行すると、データが BAM プライマリ インポート データベースから BAM キューブに移動されます。</span><span class="sxs-lookup"><span data-stu-id="cf3fe-121">When you run the CubeUpdate DTS package, the package moves data from the BAM primary import database into the BAM cubes.</span></span> <span data-ttu-id="cf3fe-122">パッケージは、グループ内のすべてのデータが RTAWindow プロパティで指定した期間を経過したときに、リアルタイム集計のデータを、グループ化された BAM データ インスタンスとして移動します。</span><span class="sxs-lookup"><span data-stu-id="cf3fe-122">The package moves real-time aggregation data as grouped BAM data instances after all of the data in the group is older than the age specified in the RTA window property.</span></span>  
  
#### <a name="to-change-the-timewindow-value-in-the-bam-configuration-file"></a><span data-ttu-id="cf3fe-123">BAM 構成ファイルで TimeWindow プロパティの値を変更するには</span><span class="sxs-lookup"><span data-stu-id="cf3fe-123">To change the TimeWindow value in the BAM Configuration file</span></span>  
  
-   <span data-ttu-id="cf3fe-124">BAM 構成ファイルで、次の行の値を変更します。</span><span class="sxs-lookup"><span data-stu-id="cf3fe-124">Change the value in this line of the BAM Configuration file:</span></span>  
  
    ```  
    <Property Name="RTAWindow">60</Property>  
    ```  
  
#### <a name="to-change-the-timewindow-value-in-the-bammetadataactivities-table"></a><span data-ttu-id="cf3fe-125">BAM_Metadata_Activities テーブルで TimeWindow プロパティの値を変更するには</span><span class="sxs-lookup"><span data-stu-id="cf3fe-125">To change the TimeWindow value in the BAM_Metadata_Activities table</span></span>  
  
-   <span data-ttu-id="cf3fe-126">BAMPrimaryImport データベースの bam_Metadata_Activities テーブルにある RTAWindow プロパティの値を変更します。</span><span class="sxs-lookup"><span data-stu-id="cf3fe-126">Modify the RTAWindow values, located in the bam_Metadata_Activities table in the BAMPrimaryImport database.</span></span> <span data-ttu-id="cf3fe-127">1 つ以上のアクティビティを対象としたリアルタイム集計 (TRA) を複数展開している場合は、RTA ごとに別の時間帯を指定できます。</span><span class="sxs-lookup"><span data-stu-id="cf3fe-127">If you deploy multiple real-time aggregations (RTA) for one or more activities, you have the option to specify a different time window for each RTA.</span></span>  
  
    > [!NOTE]
    >  <span data-ttu-id="cf3fe-128">RTAWindow の値は整数値で指定する必要があり、時間の単位は常に分になります。</span><span class="sxs-lookup"><span data-stu-id="cf3fe-128">The value of RTAWindow must be an integer and the time unit is always minutes.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="cf3fe-129">参照</span><span class="sxs-lookup"><span data-stu-id="cf3fe-129">See Also</span></span>  
 <span data-ttu-id="cf3fe-130">[BAM 構成スキーマ](../core/bam-configuration-schema.md) </span><span class="sxs-lookup"><span data-stu-id="cf3fe-130">[BAM Configuration Schema](../core/bam-configuration-schema.md) </span></span>  
 [<span data-ttu-id="cf3fe-131">BAM のセキュリティに関する推奨事項</span><span class="sxs-lookup"><span data-stu-id="cf3fe-131">BAM Security Recommendations</span></span>](../core/bam-security-recommendations.md)