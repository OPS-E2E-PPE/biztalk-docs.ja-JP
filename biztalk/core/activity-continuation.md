---
title: "アクティビティ Continuation |Microsoft ドキュメント"
ms.custom: 
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: 
ms.suite: 
ms.tgt_pltfrm: 
ms.topic: article
helpviewer_keywords:
- continuation tokens
- activities [BAM], code samples
- activities [BAM], continuation tokens
- continuations, activities [BAM]
- code samples, activities [BAM]
ms.assetid: 47d91ae6-77c1-4efb-940f-a7b3a325e5bd
caps.latest.revision: "14"
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: c7568da0647ae9847c3de2d060d75a53466b9709
ms.sourcegitcommit: cb908c540d8f1a692d01dc8f313e16cb4b4e696d
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 09/20/2017
---
# <a name="activity-continuation"></a><span data-ttu-id="9361b-102">アクティビティ Continuation</span><span class="sxs-lookup"><span data-stu-id="9361b-102">Activity Continuation</span></span>
<span data-ttu-id="9361b-103">BAM アクティビティ (ビジネス アクティビティとも呼ばれます) は複数の異種アプリケーションにまたがることができます (たとえば、1 つのパイプラインから 2 つのオーケストレーション、1 つの基幹業務アプリケーションを経て別のパイプラインに至るなど)。</span><span class="sxs-lookup"><span data-stu-id="9361b-103">The BAM activity (also called the business activity) can span multiple heterogeneous applications (for example, a pipeline, two orchestrations, a line-of-business application, and then another pipeline).</span></span> <span data-ttu-id="9361b-104">BAM インフラストラクチャは、開発者と呼ばれる概念の手助けを持つ複数のアプリケーションからのイベントを関連付けることができます"*継続*、"次の図に示したです。</span><span class="sxs-lookup"><span data-stu-id="9361b-104">The BAM infrastructure can correlate the events from multiple applications with a little help from the developer – a concept called "*Continuation*," which is shown in the following figure.</span></span>  
  
 ![](../core/media/ebiz-prog-bam-fig4-app-scopes-cont-tokens.gif "ebiz_prog_bam_fig4_app_scopes_cont_tokens")  

## <a name="applications"></a><span data-ttu-id="9361b-105">[アプリケーション]</span><span class="sxs-lookup"><span data-stu-id="9361b-105">Applications</span></span>  
 <span data-ttu-id="9361b-106">アクティビティの最初の部分は販売アプリケーションで行われ、2 番目の部分は梱包/組み立てアプリケーションで行われます。最後に、配送の進捗が、出荷アプリケーションで利用可能になります。</span><span class="sxs-lookup"><span data-stu-id="9361b-106">The first part of the activity happens in the Sales application, the second part of the activity happens in the Packaging & Assembly application, and finally, the delivery progress is available in the Shipping application.</span></span> <span data-ttu-id="9361b-107">各アプリケーションでは、そのときの作業単位によって、注文書番号 (PO)、販売注文番号 (SO)、出荷指示番号 (UPS) というように ID を使い分けます。</span><span class="sxs-lookup"><span data-stu-id="9361b-107">Each application uses different IDs for the current work unit: purchase order number (PO), sales order number (SO), and shipping order number (UPS).</span></span> <span data-ttu-id="9361b-108">2 つの異なるアプリケーションの間でイベントを関連付けるには、以下の指示に従う必要があります。</span><span class="sxs-lookup"><span data-stu-id="9361b-108">To correlate the events between two different applications, you must:</span></span>  
  
-   <span data-ttu-id="9361b-109">継続トークンという、両方のアプリケーションで使用できる一意のデータ (たとえば、交換するメッセージの一部分) を指定します。</span><span class="sxs-lookup"><span data-stu-id="9361b-109">Identify the continuation token – a unique piece of data that is available to both applications (for example, the part of the message being exchanged).</span></span>  
  
-   <span data-ttu-id="9361b-110">最初のアプリケーションで EnableContinuation を呼び出し、現在の ActivityID と共に継続トークンを渡します。</span><span class="sxs-lookup"><span data-stu-id="9361b-110">Call EnableContinuation in the first application and pass the continuation token along with the current ActivityID.</span></span>  
  
-   <span data-ttu-id="9361b-111">2 つ目のアプリケーションでは BeginActivity を呼び出さないでください。</span><span class="sxs-lookup"><span data-stu-id="9361b-111">Do not call BeginActivity in the second application.</span></span>  
  
-   <span data-ttu-id="9361b-112">2 つ目のアプリケーションでは、以後すべてのイベントを ActivityID ではなく継続トークンを使用して発生させます。</span><span class="sxs-lookup"><span data-stu-id="9361b-112">Fire all subsequent events in the second application by using the continuation token instead of ActivityID.</span></span>  
  
 <span data-ttu-id="9361b-113">次のコード例で、3 つのアプリケーションでアクティビティ Continuation を使用する方法を示します。</span><span class="sxs-lookup"><span data-stu-id="9361b-113">The following code example illustrates the use of activity continuation among three applications:</span></span>  
  
 <span data-ttu-id="9361b-114">**注文書アプリケーション**</span><span class="sxs-lookup"><span data-stu-id="9361b-114">**Purchase Order Application**</span></span>  
  
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
  
 <span data-ttu-id="9361b-115">**調達アプリケーション**</span><span class="sxs-lookup"><span data-stu-id="9361b-115">**Fulfillment Application**</span></span>  
  
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
  
 <span data-ttu-id="9361b-116">**出荷アプリケーション**</span><span class="sxs-lookup"><span data-stu-id="9361b-116">**Shipping Application**</span></span>  
  
```  
string upsID="UPS#97892"  
es.UpdateActivity("PurchaseOrder", upsID,  
"POShipped",DateTime.UtcNow);  
es.EndActivity("PurchaseOrder",upsID)  
  
```  
  
 <span data-ttu-id="9361b-117">アクティビティ Continuation をコード内で使用するときは、次のガイドラインに従ってください。</span><span class="sxs-lookup"><span data-stu-id="9361b-117">Follow these guidelines to use activity continuation in your code:</span></span>  
  
-   <span data-ttu-id="9361b-118">エンド ユーザーが、異なるアプリケーションの作業を同一のアクティビティの一部として処理する必要がある場合に限り、Continuation を使用します。</span><span class="sxs-lookup"><span data-stu-id="9361b-118">Only use continuation when the end user must treat the work of different applications as part of the same activity.</span></span> <span data-ttu-id="9361b-119">エンド ユーザーが各アプリケーションの中でその作業を意味のあるアクティビティとして見る場合、アプリケーションごとに個別のアクティビティを使用し、アクティビティのリレーションシップを作成します。</span><span class="sxs-lookup"><span data-stu-id="9361b-119">Use separate activities for each application and create an activity relationship if the end user views the work in each applications as meaningful activities.</span></span>  
  
-   <span data-ttu-id="9361b-120">1 つの販売注文に複数の出荷があるときなど、複数のアプリケーションの作業単位間に一対一のリレーションシップがない場合、アクティビティのリレーションシップは使用できますが、Continuation は使用できません。</span><span class="sxs-lookup"><span data-stu-id="9361b-120">If the work units in the applications do not have a one-to-one relationship, you can use activity relationships but not continuation, for example, when multiple shipments exist for a sales order.</span></span>  
  
-   <span data-ttu-id="9361b-121">(DirectEventStream を使用して) BAM に同期的にデータを送信し、関連するすべてのコンポーネントに ActivityID を伝達する場合、Continuation を使用する必要はありません。</span><span class="sxs-lookup"><span data-stu-id="9361b-121">If you send data to BAM synchronously (using DirectEventStream) and the ActivityID is propagated to all involved components, then you do not need to use continuation.</span></span>  
  
-   <span data-ttu-id="9361b-122">(BufferedEventStream を使用するか、またはオーケストレーションから) BAM に非同期にデータを送信するときは、すべてのコンポーネントに ActivityID を伝達する場合でも Continuation を使用する必要があります。</span><span class="sxs-lookup"><span data-stu-id="9361b-122">If you send data to BAM asynchronously (using BufferedEventStream or from orchestrations), then you must use continuation even if the ActivityID is propagated to all components.</span></span> <span data-ttu-id="9361b-123">この場合、アプリケーションごとに一意の文字列 (アプリケーション名など) をプレフィックスとして付けることで、ActivityID を使い分ける必要があります。</span><span class="sxs-lookup"><span data-stu-id="9361b-123">In this case, you need to use a different ActivityID in each application by prefixing it with a unique string (for example, Application Name).</span></span> <span data-ttu-id="9361b-124">複数のアプリケーションから BAM にランダムにデータが到着することがあり、BAM ではそのような場合にも正しいクエリと集計の結果を得るため、適切な順序でないイベントを隠蔽する必要があるので、ID の使い分けが必要です。</span><span class="sxs-lookup"><span data-stu-id="9361b-124">This is necessary because the data from different applications may arrive to BAM in random order and BAM has to hide the out-of-order events to ensure correct query and aggregation results.</span></span>  
  
-   <span data-ttu-id="9361b-125">Continuation を使用する場合、より多くのデータを交換できるようにアプリケーションを書き換える必要はありません。</span><span class="sxs-lookup"><span data-stu-id="9361b-125">Continuation does not require rewriting your applications to exchange more data.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="9361b-126">参照</span><span class="sxs-lookup"><span data-stu-id="9361b-126">See Also</span></span>  
  
 <span data-ttu-id="9361b-127">[BAM 動的インフラストラクチャ](../core/bam-dynamic-infrastructure.md) </span><span class="sxs-lookup"><span data-stu-id="9361b-127">[BAM Dynamic Infrastructure](../core/bam-dynamic-infrastructure.md) </span></span>  
 <span data-ttu-id="9361b-128">[BAM API (BizTalk Server サンプル)](../core/bam-api-biztalk-server-sample.md) </span><span class="sxs-lookup"><span data-stu-id="9361b-128">[BAM API (BizTalk Server Sample)](../core/bam-api-biztalk-server-sample.md) </span></span>  
 [<span data-ttu-id="9361b-129">BAM エンド ツー エンド (BizTalk Server サンプル)</span><span class="sxs-lookup"><span data-stu-id="9361b-129">BAM End-to-End (BizTalk Server Sample)</span></span>](../core/bam-end-to-end-biztalk-server-sample.md)