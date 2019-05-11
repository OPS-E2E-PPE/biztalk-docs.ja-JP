---
title: プライマリ インポート データベースのアーカイブ |Microsoft Docs
ms.custom: ''
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: ''
ms.suite: ''
ms.tgt_pltfrm: ''
ms.topic: article
helpviewer_keywords:
- Primary Import database [BAM], archiving data
- archived data, BAM
- managing [BAM], archiving data
- data, archiving [BAM]
ms.assetid: 4a014a59-0578-41fa-9441-8b582f54bbe8
caps.latest.revision: 10
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: 0fff7fe5720df0b73ea84f9387d47a4d35b96051
ms.sourcegitcommit: d27732e569b0897361dfaebca8352aa97bb7efe1
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 05/10/2019
ms.locfileid: "65530623"
---
# <a name="archiving-primary-import-database-data"></a><span data-ttu-id="1ec5a-102">プライマリ インポート データベースのアーカイブ</span><span class="sxs-lookup"><span data-stu-id="1ec5a-102">Archiving Primary Import Database Data</span></span>
<span data-ttu-id="1ec5a-103">管理者は、プライマリ インポート データベースのアクティビティ インスタンス データをアーカイブする時間枠を指定できます。</span><span class="sxs-lookup"><span data-stu-id="1ec5a-103">An administrator can specify the time window for archiving activity instance data in the primary import database.</span></span> <span data-ttu-id="1ec5a-104">BAMPrimaryImport データベースの BAM_Metadata_Activities テーブルで、OnlineWindowTimeUnit プロパティと OnlineWindowTimeLength プロパティを使用するとします。</span><span class="sxs-lookup"><span data-stu-id="1ec5a-104">You use the OnlineWindowTimeUnit and OnlineWindowTimeLength properties in the BAM_Metadata_Activities table in the BAMPrimaryImport database.</span></span>  
  
 <span data-ttu-id="1ec5a-105">ビジネス ユーザーが複数のアクティビティを配置した場合は、アクティビティごとに、異なる時間枠を指定できます。</span><span class="sxs-lookup"><span data-stu-id="1ec5a-105">If business users have deployed multiple activities, you can specify a different time window for each activity.</span></span> <span data-ttu-id="1ec5a-106">アクティビティを展開する方法の詳細については、「ビジネス アクティビティを定義する」を参照してください*インフォメーション ワーカー ユーザー ガイド*します。</span><span class="sxs-lookup"><span data-stu-id="1ec5a-106">For information about deploying activities, see "Defining a Business Activity" in *Information Workers Users Guide*.</span></span>  
  
 <span data-ttu-id="1ec5a-107">次の表では、OnlineWindowTimeUnit と OnlineWindowTimeLength 使用できる値について説明します。</span><span class="sxs-lookup"><span data-stu-id="1ec5a-107">The following table describes the values you can use for OnlineWindowTimeUnit and OnlineWindowTimeLength.</span></span>  
  
|<span data-ttu-id="1ec5a-108">プロパティ</span><span class="sxs-lookup"><span data-stu-id="1ec5a-108">Property</span></span>|<span data-ttu-id="1ec5a-109">値</span><span class="sxs-lookup"><span data-stu-id="1ec5a-109">Value</span></span>|  
|--------------|-----------|  
|<span data-ttu-id="1ec5a-110">OnlineWindowTimeUnit</span><span class="sxs-lookup"><span data-stu-id="1ec5a-110">OnlineWindowTimeUnit</span></span>|<span data-ttu-id="1ec5a-111">このプロパティにすることができます。 1 か月、日、時間、または 1 分です。</span><span class="sxs-lookup"><span data-stu-id="1ec5a-111">This property can be: month, day, hour, or minute.</span></span> <span data-ttu-id="1ec5a-112">このプロパティの既定値は、月です。</span><span class="sxs-lookup"><span data-stu-id="1ec5a-112">The default value of this property is month.</span></span>|  
|<span data-ttu-id="1ec5a-113">OnlineWindowTimeLength</span><span class="sxs-lookup"><span data-stu-id="1ec5a-113">OnlineWindowTimeLength</span></span>|<span data-ttu-id="1ec5a-114">このプロパティは整数である必要があります。</span><span class="sxs-lookup"><span data-stu-id="1ec5a-114">This property must be an integer.</span></span> <span data-ttu-id="1ec5a-115">このプロパティの既定値は、6 です。</span><span class="sxs-lookup"><span data-stu-id="1ec5a-115">The default value of this property is 6.</span></span>|  
  
 <span data-ttu-id="1ec5a-116">BAM では、パーティションがオンライン ウィンドウ (現在の時刻 - OnlineWindowTimeLength の OnlineWindowTimeUnit) よりも古い場合に、パーティションで BAM プライマリ インポート データベースからデータが移動します。</span><span class="sxs-lookup"><span data-stu-id="1ec5a-116">BAM moves data out of the BAM primary import database by partition, when the partition is older than the online window (current time - OnlineWindowTimeLength of OnlineWindowTimeUnit).</span></span> <span data-ttu-id="1ec5a-117">たとえば、OnlineWindowTimeLength = 5 と OnlineWindowTimeUnit 5 日間が削除よりも 1 日、古いパーティションを = です。</span><span class="sxs-lookup"><span data-stu-id="1ec5a-117">For example, for OnlineWindowTimeLength = 5 and OnlineWindowTimeUnit = day, partitions older than 5 days are removed.</span></span>  
  
 <span data-ttu-id="1ec5a-118">BAM では、BAM アーカイブ データベースにアーカイブ済みアクティビティ インスタンス データを移動します。</span><span class="sxs-lookup"><span data-stu-id="1ec5a-118">BAM moves archived activity instance data into the BAM archiving database.</span></span> <span data-ttu-id="1ec5a-119">BizTalk BAM 構成中にデータベースをアーカイブ、BAM を指定します。</span><span class="sxs-lookup"><span data-stu-id="1ec5a-119">You specify the BAM archiving database during BizTalk BAM Configuration.</span></span> <span data-ttu-id="1ec5a-120">BizTalk BAM 構成の詳細については、次を参照してください。 [BAM 構成スキーマ](../core/bam-configuration-schema.md)します。</span><span class="sxs-lookup"><span data-stu-id="1ec5a-120">For information about BizTalk BAM configuration, see [BAM Configuration Schema](../core/bam-configuration-schema.md).</span></span>  
  
 <span data-ttu-id="1ec5a-121">BAM キューブ更新アクティビティ キューブにインスタンス データを処理するデータ変換サービス (DTS) パッケージを実行していない場合、BAM はアクティビティ インスタンス データをアーカイブできません。</span><span class="sxs-lookup"><span data-stu-id="1ec5a-121">BAM will not archive activity instance data if you have not run the BAM cube update Data Transformation Services (DTS) package, which processes the instance data into the activity cube.</span></span>  
  
 <span data-ttu-id="1ec5a-122">BAM データ保守 DTS パッケージの実行方法の詳細については、次を参照してください。[の BAM DTS パッケージ](../core/bam-dts-packages.md)します。</span><span class="sxs-lookup"><span data-stu-id="1ec5a-122">For information about running the BAM data maintenance DTS package, see [BAM DTS Packages](../core/bam-dts-packages.md).</span></span>  
  
 <span data-ttu-id="1ec5a-123">時間の経過と共にアクティビティ インスタンス データが追加されるにつれて、BAMArchive データベースはサイズの増加はします。</span><span class="sxs-lookup"><span data-stu-id="1ec5a-123">Over time the BAMArchive database will grow in size as activity instance data is added.</span></span> <span data-ttu-id="1ec5a-124">データベース全体を切り捨てる簡単な方法はありませんが、記憶域の要件を削減するデータベースのトランザクション ログを定期的に切り捨てることができ、定期的にバックアップおよび BAMArchive データベース全体をアーカイブすることができます。</span><span class="sxs-lookup"><span data-stu-id="1ec5a-124">Although there is no straightforward way to truncate an entire database, you can periodically truncate the database transaction log to reduce the storage requirements, and you can periodically back up and archive the entire BAMArchive database.</span></span> <span data-ttu-id="1ec5a-125">「トランザクション ログの切り捨て」でを参照してください。 SQL Server オンライン ブックの詳細についてはします。</span><span class="sxs-lookup"><span data-stu-id="1ec5a-125">See “Truncating the transaction log” in SQL Server Books Online for more information.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="1ec5a-126">参照</span><span class="sxs-lookup"><span data-stu-id="1ec5a-126">See Also</span></span>  
 <span data-ttu-id="1ec5a-127">[Timewindow プロパティと Timeslice プロパティを定義します。](../core/defining-the-time-window-and-time-slice-properties.md) </span><span class="sxs-lookup"><span data-stu-id="1ec5a-127">[Defining the Time Window and Time Slice Properties](../core/defining-the-time-window-and-time-slice-properties.md) </span></span>  
 [<span data-ttu-id="1ec5a-128">BAM 動的インフラストラクチャの管理</span><span class="sxs-lookup"><span data-stu-id="1ec5a-128">Managing the BAM Dynamic Infrastructure</span></span>](../core/managing-the-bam-dynamic-infrastructure.md)