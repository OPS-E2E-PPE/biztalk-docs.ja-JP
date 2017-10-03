---
title: "スケジュール済みの集計 |Microsoft ドキュメント"
ms.custom: 
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: 
ms.suite: 
ms.tgt_pltfrm: 
ms.topic: article
helpviewer_keywords:
- BAM, aggregations
- scheduling, aggregations [BAM]
- aggregations [BAM], scheduling
ms.assetid: 4e2da2eb-b1fc-4b27-98d6-564e6df719e1
caps.latest.revision: "7"
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: 0cf2558b046d53deb6036553c5206beebd4d80ab
ms.sourcegitcommit: cb908c540d8f1a692d01dc8f313e16cb4b4e696d
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 09/20/2017
---
# <a name="scheduled-aggregations"></a><span data-ttu-id="2e9d5-102">スケジュール済みの集計</span><span class="sxs-lookup"><span data-stu-id="2e9d5-102">Scheduled Aggregations</span></span>
<span data-ttu-id="2e9d5-103">BAM では、動的に生成された OLAP キューブとデータ変換サービス (DTS) パッケージに基づいてスケジュール済みの集計を行います。</span><span class="sxs-lookup"><span data-stu-id="2e9d5-103">BAM bases scheduled aggregations on dynamically generated OLAP cubes and Data Transformation Services (DTS) packages.</span></span> <span data-ttu-id="2e9d5-104">スケジュール済みの集計に含まれるデータは、DTS パッケージを実行したときのビジネス アクティビティのスナップショットを表します。</span><span class="sxs-lookup"><span data-stu-id="2e9d5-104">The data in scheduled aggregations represents a snapshot of your business activities when you start your DTS package.</span></span> <span data-ttu-id="2e9d5-105">これを実現する、分析のための DTS パッケージの最初の手順は、ストアド プロシージャへの呼び出し**bam_Metadata_BeginAnalysis**から成るスナップショットを取得します。</span><span class="sxs-lookup"><span data-stu-id="2e9d5-105">To achieve this, the first step of the DTS package for analysis is a call to the stored procedure **bam_Metadata_BeginAnalysis** that will retrieve a snapshot consisting of:</span></span>  
  
-   <span data-ttu-id="2e9d5-106">実行中のすべてのアクティビティ インスタンスのスナップショット コピー</span><span class="sxs-lookup"><span data-stu-id="2e9d5-106">A snapshot copy of all activity instances in progress</span></span>  
  
-   <span data-ttu-id="2e9d5-107">前回 DTS パッケージを実行してからスナップショットが生成されるまでの間に完了したアクティビティ インスタンスの増加時間帯を表すビュー</span><span class="sxs-lookup"><span data-stu-id="2e9d5-107">A view that represents an incremental window on the completed activity instances from the moment that you ran the DTS package for the last time to the moment of the snapshot</span></span>  
  
 <span data-ttu-id="2e9d5-108">BAM では、集計を行う際、非常に短い時間だけアクティビティ ストレージに排他ロックを保持して、同時にデータが書き込まれないようにしています。</span><span class="sxs-lookup"><span data-stu-id="2e9d5-108">BAM achieves this by taking an exclusive lock on the Activity Storage for a very short time, thus preventing any data writing at the same time.</span></span> <span data-ttu-id="2e9d5-109">BAM でスナップショットの生成が開始されると、DTS パッケージの実行に時間がかかることがありますが、BAM では処理中に受け取った新しいデータは無視されます。</span><span class="sxs-lookup"><span data-stu-id="2e9d5-109">Once BAM takes the snapshot, the DTS package might take a long time to run, but BAM will ignore any new data that arrives during the processing.</span></span> <span data-ttu-id="2e9d5-110">このアクティビティは、次の図のようになります。</span><span class="sxs-lookup"><span data-stu-id="2e9d5-110">The following figure illustrates this activity:</span></span>  
  
 ![](../core/media/ebiz-prog-bam-data-maint-fig9.gif "ebiz_prog_bam_data_maint_fig9")  
<span data-ttu-id="2e9d5-111">BAM のスケジュール済みの集計</span><span class="sxs-lookup"><span data-stu-id="2e9d5-111">BAM Scheduled Aggregations</span></span>  
  
 <span data-ttu-id="2e9d5-112">上の図では、BAM は完了したアクティビティ インスタンスに関するデータを完成したインスタンスの OLAP キューブに移動しています。</span><span class="sxs-lookup"><span data-stu-id="2e9d5-112">In the figure, BAM moves data about the completed activity instances to the Completed Instances OLAP cube.</span></span> <span data-ttu-id="2e9d5-113">BAM では、このキューブを増分処理します。</span><span class="sxs-lookup"><span data-stu-id="2e9d5-113">BAM incrementally processes this cube.</span></span>  
  
 <span data-ttu-id="2e9d5-114">同時に、実行中のアクティビティに関するデータは、DTS パッケージにより完全処理されるアクティブなインスタンスのキューブに移動します。</span><span class="sxs-lookup"><span data-stu-id="2e9d5-114">At the same time, BAM moves the data about the activities still in progress to the Active Instances cube, which the DTS package fully processes.</span></span> <span data-ttu-id="2e9d5-115">BAM では、どの時点においても、実行中のアクティビティの数は比較的少ないことが想定されているため、このようなデータの移動により問題が発生することはありません。</span><span class="sxs-lookup"><span data-stu-id="2e9d5-115">This is acceptable, because BAM assumes that only a relatively small number of activities are in progress at any given moment.</span></span>  
  
 <span data-ttu-id="2e9d5-116">スケジュール済みの集計データは、完了したアクティビティと実行中のアクティビティ間の差分を埋め合わせている仮想キューブから利用できます。</span><span class="sxs-lookup"><span data-stu-id="2e9d5-116">Data for the scheduled aggregations is available from a virtual cube that hides the difference between the completed and current activities.</span></span> <span data-ttu-id="2e9d5-117">詳細については、次を参照してください。[スケジュールされている集計のデータのクエリを実行する](../core/querying-scheduled-aggregated-data.md)です。</span><span class="sxs-lookup"><span data-stu-id="2e9d5-117">For more information, see [Querying Scheduled Aggregated Data](../core/querying-scheduled-aggregated-data.md).</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="2e9d5-118">参照</span><span class="sxs-lookup"><span data-stu-id="2e9d5-118">See Also</span></span>  
 [<span data-ttu-id="2e9d5-119">集計とは何ですか。</span><span class="sxs-lookup"><span data-stu-id="2e9d5-119">What Is an Aggregation?</span></span>](../core/what-is-an-aggregation.md)