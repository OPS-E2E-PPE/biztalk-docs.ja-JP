---
title: アクティビティ Continuation |Microsoft Docs
ms.custom: ''
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: ''
ms.suite: ''
ms.tgt_pltfrm: ''
ms.topic: article
helpviewer_keywords:
- continuation tokens
- activities [BAM], code samples
- activities [BAM], continuation tokens
- continuations, activities [BAM]
- code samples, activities [BAM]
ms.assetid: 47d91ae6-77c1-4efb-940f-a7b3a325e5bd
caps.latest.revision: 14
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: 4a8615dc75802b643783e3c366159180b740521a
ms.sourcegitcommit: 381e83d43796a345488d54b3f7413e11d56ad7be
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 05/07/2019
ms.locfileid: "65361700"
---
# <a name="activity-continuation"></a><span data-ttu-id="ad38b-102">アクティビティ Continuation</span><span class="sxs-lookup"><span data-stu-id="ad38b-102">Activity Continuation</span></span>
<span data-ttu-id="ad38b-103">BAM アクティビティ (ビジネス アクティビティとも呼ばれます) は、複数の異種アプリケーション (たとえば、パイプライン、2 つのオーケストレーション、基幹業務アプリケーション、および後に別のパイプライン) にまたがることができます。</span><span class="sxs-lookup"><span data-stu-id="ad38b-103">The BAM activity (also called the business activity) can span multiple heterogeneous applications (for example, a pipeline, two orchestrations, a line-of-business application, and then another pipeline).</span></span> <span data-ttu-id="ad38b-104">BAM インフラストラクチャは、わずかな作業、開発者などと呼ばれる概念を持つ複数のアプリケーションからのイベントを関連付けることができます"*継続*、"次の図に表示されます。</span><span class="sxs-lookup"><span data-stu-id="ad38b-104">The BAM infrastructure can correlate the events from multiple applications with a little help from the developer – a concept called "*Continuation*," which is shown in the following figure.</span></span>  
  
 <span data-ttu-id="ad38b-105">![](../core/media/ebiz-prog-bam-fig4-app-scopes-cont-tokens.gif "ebiz_prog_bam_fig4_app_scopes_cont_tokens")</span><span class="sxs-lookup"><span data-stu-id="ad38b-105">![](../core/media/ebiz-prog-bam-fig4-app-scopes-cont-tokens.gif "ebiz_prog_bam_fig4_app_scopes_cont_tokens")</span></span>  

## <a name="applications"></a><span data-ttu-id="ad38b-106">[アプリケーション]</span><span class="sxs-lookup"><span data-stu-id="ad38b-106">Applications</span></span>  
 <span data-ttu-id="ad38b-107">アクティビティの最初の部分は、Sales アプリケーションで行われますでは、アクティビティの 2 番目の部分は梱包/組み立てアプリケーションで行われ、最後に、配送の進捗が、出荷アプリケーションで使用可能です。</span><span class="sxs-lookup"><span data-stu-id="ad38b-107">The first part of the activity happens in the Sales application, the second part of the activity happens in the Packaging & Assembly application, and finally, the delivery progress is available in the Shipping application.</span></span> <span data-ttu-id="ad38b-108">各アプリケーションは、現在の作業単位の異なる Id を使用して: 発注 (書 PO) 番号、販売注文番号 (SO)、および出荷指示番号 (UPS)。</span><span class="sxs-lookup"><span data-stu-id="ad38b-108">Each application uses different IDs for the current work unit: purchase order number (PO), sales order number (SO), and shipping order number (UPS).</span></span> <span data-ttu-id="ad38b-109">2 つのアプリケーションの間でイベントを関連付けるためには、次の必要があります。</span><span class="sxs-lookup"><span data-stu-id="ad38b-109">To correlate the events between two different applications, you must:</span></span>  
  
- <span data-ttu-id="ad38b-110">継続トークンという、一意の両方のアプリケーション (たとえば、交換されるメッセージの部分) に提供されるデータを特定します。</span><span class="sxs-lookup"><span data-stu-id="ad38b-110">Identify the continuation token – a unique piece of data that is available to both applications (for example, the part of the message being exchanged).</span></span>  
  
- <span data-ttu-id="ad38b-111">最初のアプリケーションで EnableContinuation を呼び出し、現在の ActivityID と共に継続トークンを渡します。</span><span class="sxs-lookup"><span data-stu-id="ad38b-111">Call EnableContinuation in the first application and pass the continuation token along with the current ActivityID.</span></span>  
  
- <span data-ttu-id="ad38b-112">2 番目のアプリケーションでは BeginActivity を呼び出さないでください。</span><span class="sxs-lookup"><span data-stu-id="ad38b-112">Do not call BeginActivity in the second application.</span></span>  
  
- <span data-ttu-id="ad38b-113">2 番目のアプリケーション内のすべての後続のイベントを ActivityID ではなく、継続トークンを使用して起動します。</span><span class="sxs-lookup"><span data-stu-id="ad38b-113">Fire all subsequent events in the second application by using the continuation token instead of ActivityID.</span></span>  
  
  <span data-ttu-id="ad38b-114">次のコード例では、3 つのアプリケーションでアクティビティ continuation の使用を示します。</span><span class="sxs-lookup"><span data-stu-id="ad38b-114">The following code example illustrates the use of activity continuation among three applications:</span></span>  
  
  <span data-ttu-id="ad38b-115">**注文書アプリケーション**</span><span class="sxs-lookup"><span data-stu-id="ad38b-115">**Purchase Order Application**</span></span>  
  
```  
string oID="PO#123";  
string soID="SO#265";  
es.BeginActivity("PurchaseOrder",poID);  
es.UpdateActivity("PurchaseOrder",poID,  
    "POReceived",DateTime.UtcNow,  
    "POAmount",100,  
"CustomerCity","Seattle");  
es.EnableContinuation(  
   "PurchaseOrder",poId,soID);  
es.EndActivity("PurchaseOrder",poID);  
```  
  
 <span data-ttu-id="ad38b-116">**調達アプリケーション**</span><span class="sxs-lookup"><span data-stu-id="ad38b-116">**Fulfillment Application**</span></span>  
  
```  
string soID="SO#265";  
string upsID="UPS#97892";  
es.UpdateActivity("PurchaseOrder",soID,  
    "POApproved",DateTime.UtcNow,  
    "ProductName","ProductA");  
es.EnableContinuation(  
   "PurchaseOrder",soID,upsID);  
es.EndActivity("PurchaseOrder",soID);  
```  
  
 <span data-ttu-id="ad38b-117">**出荷アプリケーション**</span><span class="sxs-lookup"><span data-stu-id="ad38b-117">**Shipping Application**</span></span>  
  
```  
string upsID="UPS#97892"  
es.UpdateActivity("PurchaseOrder", upsID,  
"POShipped",DateTime.UtcNow);  
es.EndActivity("PurchaseOrder",upsID)  
  
```  
  
 <span data-ttu-id="ad38b-118">アクティビティ continuation を使用して、コード内にこれらのガイドラインに従います。</span><span class="sxs-lookup"><span data-stu-id="ad38b-118">Follow these guidelines to use activity continuation in your code:</span></span>  
  
-   <span data-ttu-id="ad38b-119">エンド ユーザーは、同じアクティビティの一部としてさまざまなアプリケーションの作業を扱う必要がある場合にのみ継続を使用します。</span><span class="sxs-lookup"><span data-stu-id="ad38b-119">Only use continuation when the end user must treat the work of different applications as part of the same activity.</span></span> <span data-ttu-id="ad38b-120">アプリケーションごとに個別のアクティビティを使用し、エンド ユーザーとして意味のあるアクティビティには、各アプリケーションで作業を表示する場合に、アクティビティのリレーションシップを作成します。</span><span class="sxs-lookup"><span data-stu-id="ad38b-120">Use separate activities for each application and create an activity relationship if the end user views the work in each applications as meaningful activities.</span></span>  
  
-   <span data-ttu-id="ad38b-121">アプリケーションの作業単位には、一対一のリレーションシップがない場合、行えますアクティビティ リレーションシップがないの継続などの販売注文が存在する複数の出荷する場合。</span><span class="sxs-lookup"><span data-stu-id="ad38b-121">If the work units in the applications do not have a one-to-one relationship, you can use activity relationships but not continuation, for example, when multiple shipments exist for a sales order.</span></span>  
  
-   <span data-ttu-id="ad38b-122">同期的に BAM にデータを送信する場合 (DirectEventStream を使用) に関連するすべてのコンポーネント、ActivityID を伝達し、continuation を使用する必要はありません。</span><span class="sxs-lookup"><span data-stu-id="ad38b-122">If you send data to BAM synchronously (using DirectEventStream) and the ActivityID is propagated to all involved components, then you do not need to use continuation.</span></span>  
  
-   <span data-ttu-id="ad38b-123">非同期的に BAM にデータを送信する場合 (BufferedEventStream を使用してまたはオーケストレーションから)、すべてのコンポーネントに ActivityID を伝達される場合でも継続を使用してする必要があります。</span><span class="sxs-lookup"><span data-stu-id="ad38b-123">If you send data to BAM asynchronously (using BufferedEventStream or from orchestrations), then you must use continuation even if the ActivityID is propagated to all components.</span></span> <span data-ttu-id="ad38b-124">この場合は、一意の文字列 (たとえば、アプリケーション名) で、各アプリケーションで ActivityID を使い分けますを使用する必要があります。</span><span class="sxs-lookup"><span data-stu-id="ad38b-124">In this case, you need to use a different ActivityID in each application by prefixing it with a unique string (for example, Application Name).</span></span> <span data-ttu-id="ad38b-125">これは、ため、別のアプリケーションからデータが BAM にランダムな順序でくる可能性があります。 また、BAM は正しいクエリと集計の結果を確認する順序のイベントを非表示にする必要があります。</span><span class="sxs-lookup"><span data-stu-id="ad38b-125">This is necessary because the data from different applications may arrive to BAM in random order and BAM has to hide the out-of-order events to ensure correct query and aggregation results.</span></span>  
  
-   <span data-ttu-id="ad38b-126">継続より多くのデータを交換するようにアプリケーションの書き換えは必要ありません。</span><span class="sxs-lookup"><span data-stu-id="ad38b-126">Continuation does not require rewriting your applications to exchange more data.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="ad38b-127">参照</span><span class="sxs-lookup"><span data-stu-id="ad38b-127">See Also</span></span>  
  
 <span data-ttu-id="ad38b-128">[BAM 動的インフラストラクチャ](../core/bam-dynamic-infrastructure.md) </span><span class="sxs-lookup"><span data-stu-id="ad38b-128">[BAM Dynamic Infrastructure](../core/bam-dynamic-infrastructure.md) </span></span>  
 <span data-ttu-id="ad38b-129">[BAM API (BizTalk Server サンプル)](../core/bam-api-biztalk-server-sample.md) </span><span class="sxs-lookup"><span data-stu-id="ad38b-129">[BAM API (BizTalk Server Sample)](../core/bam-api-biztalk-server-sample.md) </span></span>  
 [<span data-ttu-id="ad38b-130">BAM End-to-End (BizTalk Server サンプル)</span><span class="sxs-lookup"><span data-stu-id="ad38b-130">BAM End-to-End (BizTalk Server Sample)</span></span>](../core/bam-end-to-end-biztalk-server-sample.md)