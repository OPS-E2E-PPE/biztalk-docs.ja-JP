---
title: "プライマリ インポート データベースのデータをアーカイブ |Microsoft ドキュメント"
ms.custom: 
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: 
ms.suite: 
ms.tgt_pltfrm: 
ms.topic: article
helpviewer_keywords:
- Primary Import database [BAM], archiving data
- archived data, BAM
- managing [BAM], archiving data
- data, archiving [BAM]
ms.assetid: 4a014a59-0578-41fa-9441-8b582f54bbe8
caps.latest.revision: "10"
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: c0fdfd55681fabd1b6cfc72f68b7e33150a121f2
ms.sourcegitcommit: cb908c540d8f1a692d01dc8f313e16cb4b4e696d
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 09/20/2017
---
# <a name="archiving-primary-import-database-data"></a><span data-ttu-id="0e760-102">プライマリ インポート データベースのアーカイブ</span><span class="sxs-lookup"><span data-stu-id="0e760-102">Archiving Primary Import Database Data</span></span>
<span data-ttu-id="0e760-103">管理者は、プライマリ インポート データベースに格納されているアクティビティ インスタンス データをアーカイブする時間枠を指定できます。</span><span class="sxs-lookup"><span data-stu-id="0e760-103">An administrator can specify the time window for archiving activity instance data in the primary import database.</span></span> <span data-ttu-id="0e760-104">この操作には、BAMPrimaryImport データベースの BAM_Metadata_Activities テーブルの OnlineWindowTimeUnit プロパティと OnlineWindowTimeLength プロパティを使用します。</span><span class="sxs-lookup"><span data-stu-id="0e760-104">You use the OnlineWindowTimeUnit and OnlineWindowTimeLength properties in the BAM_Metadata_Activities table in the BAMPrimaryImport database.</span></span>  
  
 <span data-ttu-id="0e760-105">ビジネス ユーザーが複数のアクティビティを展開している場合、アクティビティごとに別の時間枠を指定することができます。</span><span class="sxs-lookup"><span data-stu-id="0e760-105">If business users have deployed multiple activities, you can specify a different time window for each activity.</span></span> <span data-ttu-id="0e760-106">アクティビティの展開方法の詳細についてを参照してください「ビジネス アクティビティを定義する」*情報ワーカー ユーザー ガイド*です。</span><span class="sxs-lookup"><span data-stu-id="0e760-106">For information about deploying activities, see "Defining a Business Activity" in *Information Workers Users Guide*.</span></span>  
  
 <span data-ttu-id="0e760-107">次の表は、OnlineWindowTimeUnit プロパティと OnlineWindowTimeLength プロパティに使用できる値を示しています。</span><span class="sxs-lookup"><span data-stu-id="0e760-107">The following table describes the values you can use for OnlineWindowTimeUnit and OnlineWindowTimeLength.</span></span>  
  
|<span data-ttu-id="0e760-108">プロパティ</span><span class="sxs-lookup"><span data-stu-id="0e760-108">Property</span></span>|<span data-ttu-id="0e760-109">値</span><span class="sxs-lookup"><span data-stu-id="0e760-109">Value</span></span>|  
|--------------|-----------|  
|<span data-ttu-id="0e760-110">OnlineWindowTimeUnit</span><span class="sxs-lookup"><span data-stu-id="0e760-110">OnlineWindowTimeUnit</span></span>|<span data-ttu-id="0e760-111">このプロパティには、month、day、hour、または minute を設定できます。</span><span class="sxs-lookup"><span data-stu-id="0e760-111">This property can be: month, day, hour, or minute.</span></span> <span data-ttu-id="0e760-112">このプロパティの既定値は month です。</span><span class="sxs-lookup"><span data-stu-id="0e760-112">The default value of this property is month.</span></span>|  
|<span data-ttu-id="0e760-113">OnlineWindowTimeLength</span><span class="sxs-lookup"><span data-stu-id="0e760-113">OnlineWindowTimeLength</span></span>|<span data-ttu-id="0e760-114">このプロパティには、整数値を指定する必要があります。</span><span class="sxs-lookup"><span data-stu-id="0e760-114">This property must be an integer.</span></span> <span data-ttu-id="0e760-115">このプロパティの既定値は 6 です。</span><span class="sxs-lookup"><span data-stu-id="0e760-115">The default value of this property is 6.</span></span>|  
  
 <span data-ttu-id="0e760-116">BAM では、パーティションがオンライン時間帯 (OnlineWindowTimeLength と OnlineWindowTimeUnit で示される) よりも古くなったときに、パーティション単位で BAM プライマリ インポート データベースからデータを移動します。</span><span class="sxs-lookup"><span data-stu-id="0e760-116">BAM moves data out of the BAM primary import database by partition, when the partition is older than the online window (current time - OnlineWindowTimeLength of OnlineWindowTimeUnit).</span></span> <span data-ttu-id="0e760-117">たとえば、OnlineWindowTimeLength = 5 と OnlineWindowTimeUnit = day の場合、5 日以上経過しているパーティションが削除されます。</span><span class="sxs-lookup"><span data-stu-id="0e760-117">For example, for OnlineWindowTimeLength = 5 and OnlineWindowTimeUnit = day, partitions older than 5 days are removed.</span></span>  
  
 <span data-ttu-id="0e760-118">BAM では、BAM アーカイブ データベースにアーカイブしたアクティビティ インスタンス データを移動します。</span><span class="sxs-lookup"><span data-stu-id="0e760-118">BAM moves archived activity instance data into the BAM archiving database.</span></span> <span data-ttu-id="0e760-119">BAM アーカイブ データベースは、BizTalk で BAM を構成するときに指定します。</span><span class="sxs-lookup"><span data-stu-id="0e760-119">You specify the BAM archiving database during BizTalk BAM Configuration.</span></span> <span data-ttu-id="0e760-120">BizTalk BAM 構成については、次を参照してください。 [BAM 構成スキーマ](../core/bam-configuration-schema.md)です。</span><span class="sxs-lookup"><span data-stu-id="0e760-120">For information about BizTalk BAM configuration, see [BAM Configuration Schema](../core/bam-configuration-schema.md).</span></span>  
  
 <span data-ttu-id="0e760-121">BAM では、インスタンス データを処理してアクティビティ キューブを生成する、BAM キューブ更新のデータ変換サービス (DTS) パッケージを実行していない場合、アクティビティ インスタンスのデータをアーカイブしません。</span><span class="sxs-lookup"><span data-stu-id="0e760-121">BAM will not archive activity instance data if you have not run the BAM cube update Data Transformation Services (DTS) package, which processes the instance data into the activity cube.</span></span>  
  
 <span data-ttu-id="0e760-122">BAM データ保守 DTS パッケージの実行方法の詳細については、次を参照してください。[の BAM DTS パッケージ](../core/bam-dts-packages.md)です。</span><span class="sxs-lookup"><span data-stu-id="0e760-122">For information about running the BAM data maintenance DTS package, see [BAM DTS Packages](../core/bam-dts-packages.md).</span></span>  
  
 <span data-ttu-id="0e760-123">時間と共に、アクティビティ インスタンスのデータが追加されるにつれて、BAMArchive データベースのサイズが大きくなります。</span><span class="sxs-lookup"><span data-stu-id="0e760-123">Over time the BAMArchive database will grow in size as activity instance data is added.</span></span> <span data-ttu-id="0e760-124">データベース全体を切り詰める簡単な方法はありませんが、データベース トランザクション ログを定期的に切り詰めて必要なストレージを削減したり、BAMArchive データベース全体のバックアップとアーカイブを定期的に行ったりすることができます。</span><span class="sxs-lookup"><span data-stu-id="0e760-124">Although there is no straightforward way to truncate an entire database, you can periodically truncate the database transaction log to reduce the storage requirements, and you can periodically back up and archive the entire BAMArchive database.</span></span> <span data-ttu-id="0e760-125">詳細については、SQL Server Books Online の「トランザクション ログの切り詰め」を参照してください。</span><span class="sxs-lookup"><span data-stu-id="0e760-125">See “Truncating the transaction log” in SQL Server Books Online for more information.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="0e760-126">参照</span><span class="sxs-lookup"><span data-stu-id="0e760-126">See Also</span></span>  
 <span data-ttu-id="0e760-127">[時間枠とタイム スライスのプロパティを定義します。](../core/defining-the-time-window-and-time-slice-properties.md) </span><span class="sxs-lookup"><span data-stu-id="0e760-127">[Defining the Time Window and Time Slice Properties](../core/defining-the-time-window-and-time-slice-properties.md) </span></span>  
 [<span data-ttu-id="0e760-128">BAM 動的インフラストラクチャの管理</span><span class="sxs-lookup"><span data-stu-id="0e760-128">Managing the BAM Dynamic Infrastructure</span></span>](../core/managing-the-bam-dynamic-infrastructure.md)