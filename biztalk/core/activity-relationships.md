---
title: アクティビティ リレーションシップ |Microsoft ドキュメント
ms.custom: ''
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: ''
ms.suite: ''
ms.tgt_pltfrm: ''
ms.topic: article
helpviewer_keywords:
- activities [BAM], relationships
ms.assetid: da7c7205-18c6-44df-af03-3140214c84e6
caps.latest.revision: 12
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: 3709ad02ed082595665c68485502847b52e5a1d9
ms.sourcegitcommit: cb908c540d8f1a692d01dc8f313e16cb4b4e696d
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 09/20/2017
---
# <a name="activity-relationships"></a><span data-ttu-id="36057-102">アクティビティの関係</span><span class="sxs-lookup"><span data-stu-id="36057-102">Activity Relationships</span></span>
<span data-ttu-id="36057-103">アクティビティ リレーションシップは、アクティビティが他の 1 つまたは複数のアクティビティに関連している場合に存在します。</span><span class="sxs-lookup"><span data-stu-id="36057-103">An activity relationship exists when an activity relates to one or more other activities.</span></span> <span data-ttu-id="36057-104">この例として、単一の発注アクティビティに複数の出荷アクティビティが関連している場合や、単一の出荷アクティビティに 2 つの発注アクティビティの項目が含まれている場合などが挙げられます。</span><span class="sxs-lookup"><span data-stu-id="36057-104">An example of this is having multiple Shipment activities related to a single Purchase Order activity, or one Shipment activity containing items from two Purchase Order activities.</span></span>  
  
 <span data-ttu-id="36057-105">2 つのアクティビティが関連していることを示すには、AddRelatedActivity を呼び出すために、両方のアクティビティの名前とメモリ内の対応する ActivityID が必要です。</span><span class="sxs-lookup"><span data-stu-id="36057-105">To indicate that two activities are related, you need to know both names and have the corresponding ActivityIDs in memory in order to call AddRelatedActivity.</span></span> <span data-ttu-id="36057-106">この API では、対応するアクティビティ レコード間のリンクが作成されます。</span><span class="sxs-lookup"><span data-stu-id="36057-106">This API creates the link between the corresponding activity records.</span></span>  
  
 <span data-ttu-id="36057-107">次の図で強調表示されているコード行は、発注アクティビティ インスタンス #123 と出荷アクティビティ #1549、1550、および 1551 との間にリレーションシップを作成する方法を示しています。</span><span class="sxs-lookup"><span data-stu-id="36057-107">In the following figure, the highlighted lines of code show how you make a relationship between Purchase Order activity instance #123, and Shipment activities #1549, 1550, and 1551.</span></span>  
  
 ![](../core/media/activity-relationships-example.gif "activity_relationships_example")  
  
 <span data-ttu-id="36057-108">ビジネス エンド ユーザーは、Web ページを表示して発注の履歴を確認します。</span><span class="sxs-lookup"><span data-stu-id="36057-108">The business end user looks at one Web page that shows the history of a purchase order.</span></span> <span data-ttu-id="36057-109">午前 10 に示す場合があります。</span><span class="sxs-lookup"><span data-stu-id="36057-109">It may indicate that at 10 A.M.</span></span> <span data-ttu-id="36057-110">受信して、2 日後に承認が、ページが実際のドキュメントへのリンクを提供します。</span><span class="sxs-lookup"><span data-stu-id="36057-110">it arrives, two days later it receives approval, and the page provides a link to the actual documents.</span></span> <span data-ttu-id="36057-111">上記の図のコードにより、このページには、ビジネス エンド ユーザーが対応する出荷 Web ページに移動するためのハイパーリンクも表示されます。</span><span class="sxs-lookup"><span data-stu-id="36057-111">Because of the code in the previous figure, the page will also provide hyperlinks that take the business end user to the corresponding shipment Web pages.</span></span>  
  
> [!NOTE]
>  <span data-ttu-id="36057-112">すべての呼び出しを`AddRelatedActivity`間に行われる必要があります`BeginActivity`と`EndActivity`です。</span><span class="sxs-lookup"><span data-stu-id="36057-112">All calls to `AddRelatedActivity` should happen between `BeginActivity` and `EndActivity`.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="36057-113">参照</span><span class="sxs-lookup"><span data-stu-id="36057-113">See Also</span></span>  
  
 <span data-ttu-id="36057-114">[アクティビティ Continuation](../core/activity-continuation.md) </span><span class="sxs-lookup"><span data-stu-id="36057-114">[Activity Continuation](../core/activity-continuation.md) </span></span>  
 <span data-ttu-id="36057-115">[BAM 動的インフラストラクチャ](../core/bam-dynamic-infrastructure.md) </span><span class="sxs-lookup"><span data-stu-id="36057-115">[BAM Dynamic Infrastructure](../core/bam-dynamic-infrastructure.md) </span></span>  
 <span data-ttu-id="36057-116">[BAM API (BizTalk Server サンプル)](../core/bam-api-biztalk-server-sample.md) </span><span class="sxs-lookup"><span data-stu-id="36057-116">[BAM API (BizTalk Server Sample)](../core/bam-api-biztalk-server-sample.md) </span></span>  
 [<span data-ttu-id="36057-117">オーケストレーションの式 (BizTalk Server サンプル) から BAM API</span><span class="sxs-lookup"><span data-stu-id="36057-117">BAM API from an Orchestration Expression (BizTalk Server Sample)</span></span>](../core/bam-api-from-an-orchestration-expression-biztalk-server-sample.md)