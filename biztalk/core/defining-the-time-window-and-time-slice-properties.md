---
title: Timewindow プロパティと Timeslice プロパティの定義 |Microsoft Docs
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
ms.openlocfilehash: 902d50596185de13792e5d03b0d7e0dbd4238f55
ms.sourcegitcommit: 381e83d43796a345488d54b3f7413e11d56ad7be
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 05/07/2019
ms.locfileid: "65352355"
---
# <a name="defining-the-time-window-and-time-slice-properties"></a><span data-ttu-id="7051e-102">TimeWindow プロパティと TimeSlice プロパティの定義</span><span class="sxs-lookup"><span data-stu-id="7051e-102">Defining the Time Window and Time Slice Properties</span></span>
<span data-ttu-id="7051e-103">管理者を使用して、timewindow プロパティと TimeSlice プロパティ BAMConfiguration.xml ファイルで、BAM プライマリ インポート データベースのリアルタイム集計のテーブルにデータの有効期間を定義します。</span><span class="sxs-lookup"><span data-stu-id="7051e-103">Administrators use the TimeWindow and the TimeSlice properties in the BAMConfiguration.xml file to define the life of the data in the real-time aggregation tables in the BAM primary import database.</span></span>  
  
> [!NOTE]
>  <span data-ttu-id="7051e-104">BAM 構成ファイルの変更を適用するには、は、管理者は現在 BAM 構成では、展開解除し、更新した BAMConfiguration.xml を展開する必要があります。</span><span class="sxs-lookup"><span data-stu-id="7051e-104">To enact the changes they make in the BAM configuration file, administrators must undeploy the current BAM configuration, and then deploy the updated BAMConfiguration.xml.</span></span>  
  
 <span data-ttu-id="7051e-105">BAM 定義を展開解除については、次を参照してください。 [BAM 定義を削除する方法](../core/how-to-remove-bam-definitions.md)します。</span><span class="sxs-lookup"><span data-stu-id="7051e-105">For information about undeploying a BAM definition, see [How to Remove BAM Definitions](../core/how-to-remove-bam-definitions.md).</span></span> <span data-ttu-id="7051e-106">BAM 定義の展開方法の詳細については、次を参照してください。 [BAM 定義を展開する方法](../core/how-to-deploy-bam-definitions.md)します。</span><span class="sxs-lookup"><span data-stu-id="7051e-106">For information about deploying a BAM definition, see [How to Deploy BAM Definitions](../core/how-to-deploy-bam-definitions.md).</span></span>  
  
 <span data-ttu-id="7051e-107">BAM インフラストラクチャの展開を解除せずに timewindow プロパティと timeslice プロパティの値を変更する場合は、BAM プライマリ インポート データベースの BAM_Metadata_Activities テーブルの列を変更することができます。</span><span class="sxs-lookup"><span data-stu-id="7051e-107">If you want to change the TimeWindow and TimeSlice values without undeploying the BAM infrastructure, you can modifying the columns in the BAM_Metadata_Activities table in the BAM primary import database.</span></span>  
  
## <a name="timeslice"></a><span data-ttu-id="7051e-108">タイム スライス</span><span class="sxs-lookup"><span data-stu-id="7051e-108">TimeSlice</span></span>  
 <span data-ttu-id="7051e-109">BAM インスタンス データのグループ化の完了します。 TimeSlice プロパティを使用するとします。</span><span class="sxs-lookup"><span data-stu-id="7051e-109">You use the TimeSlice property to group completed BAM instance data.</span></span> <span data-ttu-id="7051e-110">TimeSlice プロパティは、データが BAM インスタンス データのグループに BAM プライマリ インポート データベースに書き込まれた時刻を使用します。</span><span class="sxs-lookup"><span data-stu-id="7051e-110">The TimeSlice property uses time that the data is written to the BAM primary import database to group BAM instance data.</span></span>  
  
 <span data-ttu-id="7051e-111">インスタンス A が完了し、2000/1/1 に、BAM プライマリ インポート データベースに永続化など、午前 1時 02分</span><span class="sxs-lookup"><span data-stu-id="7051e-111">For example, instance A is completed and persisted in the BAM primary import database at 1/1/2000 1:02 a.m.</span></span> <span data-ttu-id="7051e-112">インスタンス B が完了し、2000/1/1 に、BAM プライマリ インポート データベースに永続化の午前 1時 04分</span><span class="sxs-lookup"><span data-stu-id="7051e-112">Instance B is completed and persisted in the BAM primary import database at 1/1/2000 1:04 a.m.</span></span> <span data-ttu-id="7051e-113">TimeSlice プロパティの値を 5 分に設定する場合は、インスタンス A と B のインスタンス化されます。</span><span class="sxs-lookup"><span data-stu-id="7051e-113">If you set the value of the TimeSlice property to five minutes, instance A and instance B are grouped together.</span></span>  
  
#### <a name="to-change-the-timeslice-value-in-the-bam-configuration-file"></a><span data-ttu-id="7051e-114">BAM 構成ファイルで timeslice プロパティの値を変更するには</span><span class="sxs-lookup"><span data-stu-id="7051e-114">To change the TimeSlice value in the BAM Configuration file</span></span>  
  
-   <span data-ttu-id="7051e-115">BAM 構成ファイルの行の値を変更します。</span><span class="sxs-lookup"><span data-stu-id="7051e-115">Change the value in this line of the BAM Configuration file:</span></span>  
  
    ```  
    <Property Name="RTATimeSlice">5</Property>  
    ```  
  
#### <a name="to-change-the-timeslice-value-in-the-bammetadataactivities-table"></a><span data-ttu-id="7051e-116">BAM_Metadata_Activities テーブルで timeslice プロパティの値を変更するには</span><span class="sxs-lookup"><span data-stu-id="7051e-116">To change the TimeSlice value in the BAM_Metadata_Activities table</span></span>  
  
-   <span data-ttu-id="7051e-117">BAMPrimaryImport データベースの bam_Metadata_Activities テーブルにある rtatimeslice プロパティの値を変更します。</span><span class="sxs-lookup"><span data-stu-id="7051e-117">Modify the RTATimeSlice values, located in the bam_Metadata_Activities table in the BAMPrimaryImport database.</span></span> <span data-ttu-id="7051e-118">1 つまたは複数のアクティビティに複数のリアルタイム集計 (RTA) をデプロイする場合は、rta ごとに、異なる時間枠を指定するオプションがあります。</span><span class="sxs-lookup"><span data-stu-id="7051e-118">If you deploy multiple real-time aggregations (RTA) for one or more activities, you have the option to specify a different time window for each RTA.</span></span>  
  
    > [!NOTE]
    >  <span data-ttu-id="7051e-119">Rtawindow プロパティの値は整数である必要があります、時間単位は分では常にします。</span><span class="sxs-lookup"><span data-stu-id="7051e-119">The value of RTAWindow must be an integer and the time unit is always minutes.</span></span>  
  
## <a name="timewindow"></a><span data-ttu-id="7051e-120">Timewindow プロパティ</span><span class="sxs-lookup"><span data-stu-id="7051e-120">TimeWindow</span></span>  
 <span data-ttu-id="7051e-121">CubeUpdate DTS パッケージを実行すると、パッケージでは、BAM プライマリ インポート データベースからデータを BAM キューブに移動します。</span><span class="sxs-lookup"><span data-stu-id="7051e-121">When you run the CubeUpdate DTS package, the package moves data from the BAM primary import database into the BAM cubes.</span></span> <span data-ttu-id="7051e-122">パッケージは、BAM データのグループ化されたインスタンスすべて、グループ内のデータが Rtawindow プロパティで指定された有効期間より古い、リアルタイム集計データを移動します。</span><span class="sxs-lookup"><span data-stu-id="7051e-122">The package moves real-time aggregation data as grouped BAM data instances after all of the data in the group is older than the age specified in the RTA window property.</span></span>  
  
#### <a name="to-change-the-timewindow-value-in-the-bam-configuration-file"></a><span data-ttu-id="7051e-123">BAM 構成ファイルで timewindow プロパティの値を変更するには</span><span class="sxs-lookup"><span data-stu-id="7051e-123">To change the TimeWindow value in the BAM Configuration file</span></span>  
  
-   <span data-ttu-id="7051e-124">BAM 構成ファイルの行の値を変更します。</span><span class="sxs-lookup"><span data-stu-id="7051e-124">Change the value in this line of the BAM Configuration file:</span></span>  
  
    ```  
    <Property Name="RTAWindow">60</Property>  
    ```  
  
#### <a name="to-change-the-timewindow-value-in-the-bammetadataactivities-table"></a><span data-ttu-id="7051e-125">BAM_Metadata_Activities テーブルで timewindow プロパティの値を変更するには</span><span class="sxs-lookup"><span data-stu-id="7051e-125">To change the TimeWindow value in the BAM_Metadata_Activities table</span></span>  
  
-   <span data-ttu-id="7051e-126">BAMPrimaryImport データベースの bam_Metadata_Activities テーブルにある rtawindow プロパティの値を変更します。</span><span class="sxs-lookup"><span data-stu-id="7051e-126">Modify the RTAWindow values, located in the bam_Metadata_Activities table in the BAMPrimaryImport database.</span></span> <span data-ttu-id="7051e-127">1 つまたは複数のアクティビティに複数のリアルタイム集計 (RTA) をデプロイする場合は、rta ごとに、異なる時間枠を指定するオプションがあります。</span><span class="sxs-lookup"><span data-stu-id="7051e-127">If you deploy multiple real-time aggregations (RTA) for one or more activities, you have the option to specify a different time window for each RTA.</span></span>  
  
    > [!NOTE]
    >  <span data-ttu-id="7051e-128">Rtawindow プロパティの値は整数である必要があります、時間単位は分では常にします。</span><span class="sxs-lookup"><span data-stu-id="7051e-128">The value of RTAWindow must be an integer and the time unit is always minutes.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="7051e-129">参照</span><span class="sxs-lookup"><span data-stu-id="7051e-129">See Also</span></span>  
 <span data-ttu-id="7051e-130">[BAM 構成スキーマ](../core/bam-configuration-schema.md) </span><span class="sxs-lookup"><span data-stu-id="7051e-130">[BAM Configuration Schema](../core/bam-configuration-schema.md) </span></span>  
 [<span data-ttu-id="7051e-131">BAM のセキュリティに関する推奨事項</span><span class="sxs-lookup"><span data-stu-id="7051e-131">BAM Security Recommendations</span></span>](../core/bam-security-recommendations.md)