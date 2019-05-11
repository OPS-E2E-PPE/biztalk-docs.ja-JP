---
title: ライブ BAM データの表示 |Microsoft Docs
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
ms.openlocfilehash: 0993af1a64db2f80797b87d864e1dc561cbd1ef3
ms.sourcegitcommit: 381e83d43796a345488d54b3f7413e11d56ad7be
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 05/07/2019
ms.locfileid: "65243172"
---
# <a name="viewing-live-bam-data"></a><span data-ttu-id="57bd8-102">ライブ BAM データの表示</span><span class="sxs-lookup"><span data-stu-id="57bd8-102">Viewing Live BAM Data</span></span>
<span data-ttu-id="57bd8-103">ライブ BAM データを表示するさまざまな方法を次に示します。</span><span class="sxs-lookup"><span data-stu-id="57bd8-103">Following are the different ways you can view live BAM data.</span></span>  
  
-   <span data-ttu-id="57bd8-104">過程をリアルタイムまたは履歴 (アーカイブ済み) レコードから 1 つのアクティビティのインスタンス (たとえば、注文書やローン プロセス) を表示します。</span><span class="sxs-lookup"><span data-stu-id="57bd8-104">View a single activity instance (for example, Purchase Order or Loan Process) as it evolves in real-time or from the historical (archived) records.</span></span> <span data-ttu-id="57bd8-105">このビューは、ビジネス レベルで関連するデータのみが表示されます、多様な実装の複雑さを非表示になります。</span><span class="sxs-lookup"><span data-stu-id="57bd8-105">This view shows only the data relevant at the business level and hides complexity of the diverse implementation.</span></span> <span data-ttu-id="57bd8-106">1 つのアクティビティ インスタンスを表示する方法についての詳細については、次を参照してください。[個々 のアクティビティを表示する方法](../core/how-to-view-an-individual-activity.md)します。</span><span class="sxs-lookup"><span data-stu-id="57bd8-106">For more information about viewing a single activity instance, see [How to View an Individual Activity](../core/how-to-view-an-individual-activity.md).</span></span>  
  
-   <span data-ttu-id="57bd8-107">などの関連するアクティビティのインスタンスに移動し、メディアの送付に関連付けられている特定の発注書、または請求書が含まれる。</span><span class="sxs-lookup"><span data-stu-id="57bd8-107">Navigate to the related activity instances, for example, Shipments associated with given Purchase Order, or the Invoice in which it is included.</span></span> <span data-ttu-id="57bd8-108">関連するアクティビティ インスタンスへの移動に関する詳細については、次を参照してください。[ビューの関連アクティビティおよび関連ドキュメント方法](../core/how-to-view-related-activities-and-related-documents.md)します。</span><span class="sxs-lookup"><span data-stu-id="57bd8-108">For more information about navigating to related activity instances, see [How to View Related Activities and Related Documents](../core/how-to-view-related-activities-and-related-documents.md).</span></span>  
  
-   <span data-ttu-id="57bd8-109">現在処理されているか、既に発生しているすべてのビジネス アクティビティに関する集計 (主要業績評価指標) を参照します。</span><span class="sxs-lookup"><span data-stu-id="57bd8-109">Browse Aggregations (Key Performance Indicators) around all the Business Activities that are currently being processed or have already happened.</span></span> <span data-ttu-id="57bd8-110">集計を行うことができますをリアルタイムで特定の時点でのアクティビティのスナップショットに基づく場合もあります。</span><span class="sxs-lookup"><span data-stu-id="57bd8-110">The Aggregations can be done in Real-Time or can be based on a snapshot of the Activities taken at specific time.</span></span> <span data-ttu-id="57bd8-111">集計の参照の詳細については、次を参照してください。 [BAM 集計の表示方法](../core/how-to-view-bam-aggregations.md)します。</span><span class="sxs-lookup"><span data-stu-id="57bd8-111">For more information about browsing aggregations, see [How to View BAM Aggregations](../core/how-to-view-bam-aggregations.md).</span></span>  
  
-   <span data-ttu-id="57bd8-112">BAM の新機能のいずれかの進捗ディメンションを使用します。</span><span class="sxs-lookup"><span data-stu-id="57bd8-112">Use Progress Dimensions, one of the new features in BAM.</span></span> <span data-ttu-id="57bd8-113">これらのディメンションでは、フィルター処理または指定した完了段階にあるアクティビティのグループ化を許可します。</span><span class="sxs-lookup"><span data-stu-id="57bd8-113">These dimensions allow filtering or grouping of the Activities at a given stage of completion.</span></span> <span data-ttu-id="57bd8-114">進捗ディメンションの詳細については、次を参照してください。[進捗ディメンション](../core/progress-dimension.md)します。</span><span class="sxs-lookup"><span data-stu-id="57bd8-114">For more information about Progress Dimensions, see [Progress Dimension](../core/progress-dimension.md).</span></span>  
  
-   <span data-ttu-id="57bd8-115">その進行状況やビジネス データに基づくアクティビティ インスタンスを検索します。</span><span class="sxs-lookup"><span data-stu-id="57bd8-115">Search for activity instances based on their progress or business data.</span></span> <span data-ttu-id="57bd8-116">たとえば、顧客の署名を待機しているローンを検索することができ、金額が指定した値より大きい。</span><span class="sxs-lookup"><span data-stu-id="57bd8-116">For example, you can search for loans that are waiting for customer signature and the dollar amount is greater than a given value.</span></span> <span data-ttu-id="57bd8-117">Bam アクティビティの検索に関する詳細については、次を参照してください。[アクティビティの検索方法](../core/how-to-search-for-activities.md)します。</span><span class="sxs-lookup"><span data-stu-id="57bd8-117">For more information about searching activities in BAM, see [How to Search for Activities](../core/how-to-search-for-activities.md).</span></span>  
  
## <a name="in-this-section"></a><span data-ttu-id="57bd8-118">このセクションの内容</span><span class="sxs-lookup"><span data-stu-id="57bd8-118">In This Section</span></span>  
  
-   [<span data-ttu-id="57bd8-119">BAM 集計を表示する方法</span><span class="sxs-lookup"><span data-stu-id="57bd8-119">How to View BAM Aggregations</span></span>](../core/how-to-view-bam-aggregations.md)  
  
-   [<span data-ttu-id="57bd8-120">アクティビティを検索する方法</span><span class="sxs-lookup"><span data-stu-id="57bd8-120">How to Search for Activities</span></span>](../core/how-to-search-for-activities.md)  
  
## <a name="see-also"></a><span data-ttu-id="57bd8-121">参照</span><span class="sxs-lookup"><span data-stu-id="57bd8-121">See Also</span></span>  
 [<span data-ttu-id="57bd8-122">BAM によるビジネス アクティビティの監視</span><span class="sxs-lookup"><span data-stu-id="57bd8-122">Monitoring Business Activities with BAM</span></span>](../core/monitoring-business-activities-with-bam.md)