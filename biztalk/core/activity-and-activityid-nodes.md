---
title: アクティビティ ノードと ActivityID ノード |Microsoft Docs
ms.custom: ''
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: ''
ms.suite: ''
ms.tgt_pltfrm: ''
ms.topic: article
helpviewer_keywords:
- ActivityID nodes [Tracking Profile Editor]
- Activity nodes [Tracking Profile Editor]
- Tracking Profile Editor, node descriptions
- activities [BAM], definitions
ms.assetid: 94d4130a-53c5-4cd5-916a-4a6bd9acbf23
caps.latest.revision: 9
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: e0ad89c82f7eac4aca14ca3d424a5bda6056f95f
ms.sourcegitcommit: 381e83d43796a345488d54b3f7413e11d56ad7be
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 05/07/2019
ms.locfileid: "65361818"
---
# <a name="activity-and-activityid-nodes"></a><span data-ttu-id="9dbb2-102">アクティビティ ノードと ActivityID ノード</span><span class="sxs-lookup"><span data-stu-id="9dbb2-102">Activity and ActivityID Nodes</span></span>
<span data-ttu-id="9dbb2-103">アクティビティ ノードと ActivityID ノードは、アクティビティ定義の格納と識別に使用します。</span><span class="sxs-lookup"><span data-stu-id="9dbb2-103">Activity and ActivityID nodes are used to contain and identify an activity definition.</span></span> <span data-ttu-id="9dbb2-104">アクティビティ ノードは、アクティビティ定義に含まれる項目の親フォルダーです。</span><span class="sxs-lookup"><span data-stu-id="9dbb2-104">The Activity node is the parent folder for the items in the activity definition.</span></span> <span data-ttu-id="9dbb2-105">すべてのデータ項目とビジネス イベント ノードは、関連付けられているアクティビティ ノードの下位ノードで、アクティビティ ノードに含まれています。</span><span class="sxs-lookup"><span data-stu-id="9dbb2-105">All data items and business event nodes are subordinate to and contained within the associated activity node.</span></span> <span data-ttu-id="9dbb2-106">アクティビティ ノードの名前は、アクティビティ自体の名前が反映されます。</span><span class="sxs-lookup"><span data-stu-id="9dbb2-106">The name of the Activity node should reflect the name of the activity itself.</span></span>  
  
 <span data-ttu-id="9dbb2-107">ActivityID ノードは、アクティビティ定義で自動的に生成される項目で、アクティビティの一意な識別子を保持することを目的としています。</span><span class="sxs-lookup"><span data-stu-id="9dbb2-107">The ActivityID node is an automatically generated item in the activity definition and is intended to hold a unique identifier for the activity.</span></span> <span data-ttu-id="9dbb2-108">ActivityID ノードは、ユーザーが指定した識別子またはシステムによって生成された識別子を追跡する場合に使用できます。</span><span class="sxs-lookup"><span data-stu-id="9dbb2-108">The ActivityID node can be used to track user supplied identifiers or identifiers that are system generated.</span></span> <span data-ttu-id="9dbb2-109">たとえば、システムで注文番号を一意な識別子として保持している場合、注文番号を ActivityID として使用することができます。この場合、ActivityID の値は、注文書のスキーマに含まれる PO 番号フィールドなどのイベント ソースからマップすることになります。</span><span class="sxs-lookup"><span data-stu-id="9dbb2-109">For example, in a scenario in which you have purchase order number as a unique identifier across all purchase orders in the system, you can use it as the ActivityID, in which case you will map the value of the ActivityID from some event source, such as the PO number field in the purchase order schema.</span></span> <span data-ttu-id="9dbb2-110">ただし、注文番号の値が一意な識別子ではない場合は、ノードに値をマップする必要はありません。ノードに値をマップしないと、BAM により、実行時に一意な識別子が自動的に生成されます。</span><span class="sxs-lookup"><span data-stu-id="9dbb2-110">On the other hand, if the purchase order value is not unique, then you can leave the node unmapped, and BAM will automatically generate unique identifiers at run-time.</span></span>  
  
 <span data-ttu-id="9dbb2-111">アクティビティは他のアクティビティに関連付けることができます。</span><span class="sxs-lookup"><span data-stu-id="9dbb2-111">Activities can be related to other activities.</span></span> <span data-ttu-id="9dbb2-112">一部のシナリオでは、このようなリレーションシップは明示的に監視モデルの一部となります。</span><span class="sxs-lookup"><span data-stu-id="9dbb2-112">In some scenarios these relationships are explicitly part of the observation model.</span></span>  <span data-ttu-id="9dbb2-113">具体的には、ユーザー ビューに 2 つ以上のアクティビティが含まれている場合、これらのアクティビティ間にはリレーションシップが自動的に作成されます。</span><span class="sxs-lookup"><span data-stu-id="9dbb2-113">Specifically, when any user view includes two or more activities, there is an automatic relationship between those activities.</span></span>  <span data-ttu-id="9dbb2-114">このようなリレーションシップが存在する場合、既知のピア アクティビティごとに、アクティビティ ツリーのアクティビティ ノードの下にリレーションシップ ノードが自動的に作成されます。</span><span class="sxs-lookup"><span data-stu-id="9dbb2-114">When such a relationship exists, a relationship node is automatically created in the activity tree, under the Activity node, for each known peer activity.</span></span> <span data-ttu-id="9dbb2-115">データ リレーションシップが存在し、それらのデータが展開されるビューが存在しない場合は、アクティビティ ツリーにリレーションシップ ノードを手動で追加することができます。</span><span class="sxs-lookup"><span data-stu-id="9dbb2-115">In scenarios where there  is a data relationship and no spanning view exists, you can manually add a relationship node to  the activity tree.</span></span>  
  
 <span data-ttu-id="9dbb2-116">どちらの場合も、リレーションシップ ノードは、関連するアクティビティの識別子を提供することを目的としています。</span><span class="sxs-lookup"><span data-stu-id="9dbb2-116">In either case, the purpose of the relationship node is to provide an identifier for the related activity.</span></span> <span data-ttu-id="9dbb2-117">たとえば、発注と出荷の間には多対多のリレーションシップが存在することがあります (1 つの PO に複数回の出荷で対応したり、1 回の出荷が複数の PO の製品に対応することがあります)。</span><span class="sxs-lookup"><span data-stu-id="9dbb2-117">For example, purchase orders and shipments can have a many-to-many relationship (one PO is fulfilled by multiple shipments; one shipment can carry a product satisfying many POs).</span></span>  <span data-ttu-id="9dbb2-118">各発注アクティビティ レコードが複数の関連する出荷に対するポインターを持ったり、各出荷アクティビティ レコードが 1 つ以上の発注に対してポインターを持ったりすることがあります。</span><span class="sxs-lookup"><span data-stu-id="9dbb2-118">The activity record for each purchase order can have multiple pointers to related shipments, and each shipment activity record could point to one or more Purchase Orders.</span></span>  <span data-ttu-id="9dbb2-119">データベースの観点では、リレーションシップ ノードの値は、他のアクティビティのテーブルに対する外部キーになります。</span><span class="sxs-lookup"><span data-stu-id="9dbb2-119">In database terms, the value of the relationship node is the foreign key into the table for the other activity.</span></span>  
  
## <a name="working-with-activity-id-nodes"></a><span data-ttu-id="9dbb2-120">ActivityID ノードの操作</span><span class="sxs-lookup"><span data-stu-id="9dbb2-120">Working with Activity ID nodes</span></span>  
 <span data-ttu-id="9dbb2-121">たとえば、次のシナリオ: EquityLoan オーケストレーションに LoanProcess アクティビティ フォルダーが含まれています。</span><span class="sxs-lookup"><span data-stu-id="9dbb2-121">For example, consider the following scenario: the EquityLoan orchestration contains the activity folder LoanProcess.</span></span> <span data-ttu-id="9dbb2-122">このオーケストレーションで次のビジネス イベントを参照しているとします。</span><span class="sxs-lookup"><span data-stu-id="9dbb2-122">It references business events including the following:</span></span>  
  
- <span data-ttu-id="9dbb2-123">LoanApplicationReceived</span><span class="sxs-lookup"><span data-stu-id="9dbb2-123">LoanApplicationReceived</span></span>  
  
- <span data-ttu-id="9dbb2-124">CHRequest</span><span class="sxs-lookup"><span data-stu-id="9dbb2-124">CHRequest</span></span>  
  
- <span data-ttu-id="9dbb2-125">CHResponse</span><span class="sxs-lookup"><span data-stu-id="9dbb2-125">CHResponse</span></span>  
  
- <span data-ttu-id="9dbb2-126">AppraisalRequest</span><span class="sxs-lookup"><span data-stu-id="9dbb2-126">AppraisalRequest</span></span>  
  
- <span data-ttu-id="9dbb2-127">AppraisalResponse</span><span class="sxs-lookup"><span data-stu-id="9dbb2-127">AppraisalResponse</span></span>  
  
- <span data-ttu-id="9dbb2-128">承認</span><span class="sxs-lookup"><span data-stu-id="9dbb2-128">Approved</span></span>  
  
- <span data-ttu-id="9dbb2-129">拒否</span><span class="sxs-lookup"><span data-stu-id="9dbb2-129">Denied</span></span>  
  
  <span data-ttu-id="9dbb2-130">ソリューション開発者は ActivityID ノードを使用して、アクティビティを一意に識別するデータ (注文番号など) を抽出できます。サンプル シナリオでは、メッセージの SSN フィールドのデータを抽出しました。</span><span class="sxs-lookup"><span data-stu-id="9dbb2-130">The ActivityID node enables the solution developer to extract data that uniquely identifies the activity, such as a purchase order number, or, in the case of the sample scenario, the SSN field of the message.</span></span> <span data-ttu-id="9dbb2-131">データを ActivityID ノードにドラッグしない場合、ビジネス アクティビティは、自動的に生成された GUID により識別されます。</span><span class="sxs-lookup"><span data-stu-id="9dbb2-131">If you do not drag any data to the ActivityID node, an automatically generated GUID identifies the business activities.</span></span>  
  
  <span data-ttu-id="9dbb2-132">異なるオーケストレーションに含まれているビジネス イベントまたはマイルストーンの間でリレーションシップを定義するには、ターゲット オーケストレーションで ActivityID を参照する必要があります。</span><span class="sxs-lookup"><span data-stu-id="9dbb2-132">To define the relationship between business events or milestones in different orchestrations, the target orchestration must reference the ActivityID.</span></span> <span data-ttu-id="9dbb2-133">TPE を使用してリレーションシップを実装する方法の詳細については、次を参照してください。[リレーションシップ ノード](../core/relationship-nodes.md)します。</span><span class="sxs-lookup"><span data-stu-id="9dbb2-133">For more information about how to implement relationships using TPE, see [Relationship Nodes](../core/relationship-nodes.md).</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="9dbb2-134">参照</span><span class="sxs-lookup"><span data-stu-id="9dbb2-134">See Also</span></span>  
 [<span data-ttu-id="9dbb2-135">TPE アクティビティ ビューのノード</span><span class="sxs-lookup"><span data-stu-id="9dbb2-135">TPE Activity View Nodes</span></span>](../core/tpe-activity-view-nodes.md)