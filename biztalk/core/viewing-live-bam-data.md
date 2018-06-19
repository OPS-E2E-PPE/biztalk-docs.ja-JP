---
title: ライブ BAM データの表示 |Microsoft ドキュメント
ms.custom: ''
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: ''
ms.suite: ''
ms.tgt_pltfrm: ''
ms.topic: article
helpviewer_keywords:
- data, real-time data [BAM]
- BAM, real-time data
ms.assetid: 23e6561e-b570-49f4-bc4c-f4fbfde6fc81
caps.latest.revision: 11
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: 37610fee118d2bf6392189dddccdccd912c055b8
ms.sourcegitcommit: cb908c540d8f1a692d01dc8f313e16cb4b4e696d
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 09/20/2017
ms.locfileid: "22288370"
---
# <a name="viewing-live-bam-data"></a><span data-ttu-id="b2df2-102">ライブ BAM データの表示</span><span class="sxs-lookup"><span data-stu-id="b2df2-102">Viewing Live BAM Data</span></span>
<span data-ttu-id="b2df2-103">ライブ BAM データは次のようなさまざまな方法で表示できます。</span><span class="sxs-lookup"><span data-stu-id="b2df2-103">Following are the different ways you can view live BAM data.</span></span>  
  
-   <span data-ttu-id="b2df2-104">発注プロセスやローン処理など、1 つのアクティビティ インスタンスの過程をリアルタイムで、または履歴 (アーカイブ済み) レコードから表示します。</span><span class="sxs-lookup"><span data-stu-id="b2df2-104">View a single activity instance (for example, Purchase Order or Loan Process) as it evolves in real-time or from the historical (archived) records.</span></span> <span data-ttu-id="b2df2-105">このビューでは、ビジネス レベルに関連するデータのみが表示され、複雑な実装は非表示になっています。</span><span class="sxs-lookup"><span data-stu-id="b2df2-105">This view shows only the data relevant at the business level and hides complexity of the diverse implementation.</span></span> <span data-ttu-id="b2df2-106">1 つのアクティビティ インスタンスを表示する方法の詳細については、次を参照してください。[を個々 のアクティビティを表示する方法](../core/how-to-view-an-individual-activity.md)です。</span><span class="sxs-lookup"><span data-stu-id="b2df2-106">For more information about viewing a single activity instance, see [How to View an Individual Activity](../core/how-to-view-an-individual-activity.md).</span></span>  
  
-   <span data-ttu-id="b2df2-107">関連するアクティビティ インスタンス、たとえば、指定した注文書に関連付けられている出荷や、注文書が含まれている請求書に移動します。</span><span class="sxs-lookup"><span data-stu-id="b2df2-107">Navigate to the related activity instances, for example, Shipments associated with given Purchase Order, or the Invoice in which it is included.</span></span> <span data-ttu-id="b2df2-108">関連するアクティビティ インスタンスへの移動の詳細については、次を参照してください。[ハウツー関連アクティビティの表示および関連ドキュメント](../core/how-to-view-related-activities-and-related-documents.md)です。</span><span class="sxs-lookup"><span data-stu-id="b2df2-108">For more information about navigating to related activity instances, see [How to View Related Activities and Related Documents](../core/how-to-view-related-activities-and-related-documents.md).</span></span>  
  
-   <span data-ttu-id="b2df2-109">現在処理中、または既に発生しているすべてのビジネス アクティビティに関する集計 (主要業績評価指標) を参照します。</span><span class="sxs-lookup"><span data-stu-id="b2df2-109">Browse Aggregations (Key Performance Indicators) around all the Business Activities that are currently being processed or have already happened.</span></span> <span data-ttu-id="b2df2-110">集計は、リアルタイムで、または指定した期間のアクティビティのスナップショットに基づいて実行できます。</span><span class="sxs-lookup"><span data-stu-id="b2df2-110">The Aggregations can be done in Real-Time or can be based on a snapshot of the Activities taken at specific time.</span></span> <span data-ttu-id="b2df2-111">集計の参照の詳細については、次を参照してください。 [BAM 集計を表示する方法](../core/how-to-view-bam-aggregations.md)です。</span><span class="sxs-lookup"><span data-stu-id="b2df2-111">For more information about browsing aggregations, see [How to View BAM Aggregations](../core/how-to-view-bam-aggregations.md).</span></span>  
  
-   <span data-ttu-id="b2df2-112">BAM の新機能の 1 つである進捗ディメンションを使用します。</span><span class="sxs-lookup"><span data-stu-id="b2df2-112">Use Progress Dimensions, one of the new features in BAM.</span></span> <span data-ttu-id="b2df2-113">進捗ディメンションを使用すると、指定した完了段階にあるアクティビティをフィルター処理またはグループ化することができます。</span><span class="sxs-lookup"><span data-stu-id="b2df2-113">These dimensions allow filtering or grouping of the Activities at a given stage of completion.</span></span> <span data-ttu-id="b2df2-114">進捗ディメンションの詳細については、次を参照してください。[進捗ディメンション](../core/progress-dimension.md)です。</span><span class="sxs-lookup"><span data-stu-id="b2df2-114">For more information about Progress Dimensions, see [Progress Dimension](../core/progress-dimension.md).</span></span>  
  
-   <span data-ttu-id="b2df2-115">進捗データまたはビジネス データに基づいてアクティビティ インスタンスを検索します。</span><span class="sxs-lookup"><span data-stu-id="b2df2-115">Search for activity instances based on their progress or business data.</span></span> <span data-ttu-id="b2df2-116">たとえば、顧客の署名を待っている状態の、指定した値より金額が大きなローンを検索できます。</span><span class="sxs-lookup"><span data-stu-id="b2df2-116">For example, you can search for loans that are waiting for customer signature and the dollar amount is greater than a given value.</span></span> <span data-ttu-id="b2df2-117">Bam アクティビティを検索する方法に関する詳細については、次を参照してください。[アクティビティの検索方法](../core/how-to-search-for-activities.md)です。</span><span class="sxs-lookup"><span data-stu-id="b2df2-117">For more information about searching activities in BAM, see [How to Search for Activities](../core/how-to-search-for-activities.md).</span></span>  
  
## <a name="in-this-section"></a><span data-ttu-id="b2df2-118">このセクションの内容</span><span class="sxs-lookup"><span data-stu-id="b2df2-118">In This Section</span></span>  
  
-   [<span data-ttu-id="b2df2-119">BAM 集計を表示する方法</span><span class="sxs-lookup"><span data-stu-id="b2df2-119">How to View BAM Aggregations</span></span>](../core/how-to-view-bam-aggregations.md)  
  
-   [<span data-ttu-id="b2df2-120">アクティビティを検索する方法</span><span class="sxs-lookup"><span data-stu-id="b2df2-120">How to Search for Activities</span></span>](../core/how-to-search-for-activities.md)  
  
## <a name="see-also"></a><span data-ttu-id="b2df2-121">参照</span><span class="sxs-lookup"><span data-stu-id="b2df2-121">See Also</span></span>  
 [<span data-ttu-id="b2df2-122">BAM によるビジネス アクティビティの監視</span><span class="sxs-lookup"><span data-stu-id="b2df2-122">Monitoring Business Activities with BAM</span></span>](../core/monitoring-business-activities-with-bam.md)