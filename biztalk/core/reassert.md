---
title: 再アサート |Microsoft ドキュメント
ms.custom: ''
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: ''
ms.suite: ''
ms.tgt_pltfrm: ''
ms.topic: article
helpviewer_keywords:
- Assert function [Business Rules Engine]
ms.assetid: 9cd640a2-bfeb-4c7a-b737-1c92cc122a9c
caps.latest.revision: 9
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: 22fcc8be7760d85a12cb05c53137177703c0fa73
ms.sourcegitcommit: cb908c540d8f1a692d01dc8f313e16cb4b4e696d
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 09/20/2017
---
# <a name="reassert"></a><span data-ttu-id="dfe1b-102">再アサート</span><span class="sxs-lookup"><span data-stu-id="dfe1b-102">Reassert</span></span>
<span data-ttu-id="dfe1b-103">*Reassert*を呼び出す意味、 **Assert**エンジンに既にあるオブジェクトに対して関数の作業メモリです。</span><span class="sxs-lookup"><span data-stu-id="dfe1b-103">To *reassert* means to call the **Assert** function on an object that is already in the engine's working memory.</span></span> <span data-ttu-id="dfe1b-104">reassert コマンドは、オブジェクトに対して retract コマンドを発行し、続けて assert コマンドを発行することと同じです。</span><span class="sxs-lookup"><span data-stu-id="dfe1b-104">A reassert command is equivalent to issuing a retract command for the object, followed by an assert command.</span></span>  
  
## <a name="net-objects"></a><span data-ttu-id="dfe1b-105">.NET オブジェクト</span><span class="sxs-lookup"><span data-stu-id="dfe1b-105">.NET Objects</span></span>  
 <span data-ttu-id="dfe1b-106">最初にオブジェクトが取り消され、述語またはアクション内でオブジェクトを使用しているルールの議題に関するアクションが削除されます。</span><span class="sxs-lookup"><span data-stu-id="dfe1b-106">The object is first retracted and any actions on the agenda for rules that use the object (in a predicate or action) are removed.</span></span> <span data-ttu-id="dfe1b-107">オブジェクトは作業メモリにアサートされ、新たにアサートされたオブジェクトとして評価されます。</span><span class="sxs-lookup"><span data-stu-id="dfe1b-107">The object is then asserted back into working memory and evaluated as any object that is newly asserted.</span></span> <span data-ttu-id="dfe1b-108">したがって、述語内でオブジェクトを使用するルールが再評価され、そのアクションが議題に適切に追加されます。</span><span class="sxs-lookup"><span data-stu-id="dfe1b-108">This means that any rules that use the object in a predicate are re-evaluated and their actions are added to the agenda as appropriate.</span></span> <span data-ttu-id="dfe1b-109">以前に評価される規則**true**とのみを使用して、アクション内のオブジェクトが議題に再び追加します。</span><span class="sxs-lookup"><span data-stu-id="dfe1b-109">Any rules that previously evaluated to **true** and only use the object in their actions will have their actions re-added to the agenda.</span></span>  
  
## <a name="typedxmldocument"></a><span data-ttu-id="dfe1b-110">TypedXmlDocument</span><span class="sxs-lookup"><span data-stu-id="dfe1b-110">TypedXmlDocument</span></span>  
 <span data-ttu-id="dfe1b-111">ときに最上位レベル**TypedXmlDocument** (**TXD**) 再アサートは、子**TXD**s 時に作成される最上位レベル**TXD**の初期値アサートされる子の状態に応じて異なる動作がある**TXD**s。</span><span class="sxs-lookup"><span data-stu-id="dfe1b-111">When a top level **TypedXmlDocument** (**TXD**) is reasserted, the child **TXD**s that are created when the top level **TXD** is initially asserted have different behaviors depending on the state of the child **TXD**s.</span></span> <span data-ttu-id="dfe1b-112">場合は、新しい子ノードまたは子ノードがダーティの場合、つまり、そのフィールドの少なくとも 1 つが変更されているポリシーで、ルールのアクション、アサートを使用して、またはアクションを再アサートは子ノードで実行されます。</span><span class="sxs-lookup"><span data-stu-id="dfe1b-112">In the case of a new child node or a child node that is dirty, meaning that at least one of its fields has been changed in the policy by using a rule action, an assert, or reassert action is performed on the child node.</span></span> <span data-ttu-id="dfe1b-113">ダーティではない既存の子ノードは、作業メモリに残されます。</span><span class="sxs-lookup"><span data-stu-id="dfe1b-113">Any existing child node that is not dirty remains in the working memory.</span></span> <span data-ttu-id="dfe1b-114">次の例は、親ノードが再アサートされたときの子ノードの動作を説明する簡単なシナリオです。</span><span class="sxs-lookup"><span data-stu-id="dfe1b-114">The following example is a simplified scenario that describes the behaviors of the child nodes when their parent node is reasserted.</span></span>  
  
 <span data-ttu-id="dfe1b-115">3 つを使用する必要があると**TXD**作業メモリに現在 s: **P**、 **C**1、 **C**2、および**C**3 です。</span><span class="sxs-lookup"><span data-stu-id="dfe1b-115">Assume there are three **TXD**s currently in the working memory: **P**, **C**1, **C**2, and **C**3.</span></span> <span data-ttu-id="dfe1b-116">**P**最上位レベル**TXD**、親ノードです。 各子ノードには、フィールドが含まれています。 **x**です。</span><span class="sxs-lookup"><span data-stu-id="dfe1b-116">**P** is the top level **TXD**, the parent node; each child node contains a field **x**.</span></span>  
  
 <span data-ttu-id="dfe1b-117">**P**</span><span class="sxs-lookup"><span data-stu-id="dfe1b-117">**P**</span></span>  
  
 <span data-ttu-id="dfe1b-118">**C**1 (**C**1 **。x** = 1)</span><span class="sxs-lookup"><span data-stu-id="dfe1b-118">**C**1 (**C**1.**x** = 1)</span></span>  
  
 <span data-ttu-id="dfe1b-119">**C**2 (**C**2 **。x** = 1)</span><span class="sxs-lookup"><span data-stu-id="dfe1b-119">**C**2 (**C**2.**x** = 1)</span></span>  
  
 <span data-ttu-id="dfe1b-120">**C**3 (**C**3 **。x** = 1)</span><span class="sxs-lookup"><span data-stu-id="dfe1b-120">**C**3 (**C**3.**x** = 1)</span></span>  
  
 <span data-ttu-id="dfe1b-121">次に、ルール アクションの結果として、次の操作が実行されたと仮定します。</span><span class="sxs-lookup"><span data-stu-id="dfe1b-121">Next, assume the following operations have been performed as a result of rule action:</span></span>  
  
-   <span data-ttu-id="dfe1b-122">フィールド (**x**) の場合は値**C**2 を更新します。</span><span class="sxs-lookup"><span data-stu-id="dfe1b-122">The field (**x**) value for **C**2 is updated.</span></span>  
  
-   <span data-ttu-id="dfe1b-123">**C**3 がユーザー コードを使用して削除します。</span><span class="sxs-lookup"><span data-stu-id="dfe1b-123">**C**3 is deleted by using user code.</span></span>  
  
-   <span data-ttu-id="dfe1b-124">追加の子ノードでは、 **D**に追加**P**ユーザー コードを使用しています。</span><span class="sxs-lookup"><span data-stu-id="dfe1b-124">An additional child node, **D**, is added to **P** by using user code.</span></span>  
  
> [!NOTE]
>  <span data-ttu-id="dfe1b-125">エンジンが関知しない操作によってビジネス ルール エンジンがノードをダーティであると識別することはありません。</span><span class="sxs-lookup"><span data-stu-id="dfe1b-125">A node will not be marked dirty by the Business Rule Engine from operations, of which the engine is not aware.</span></span> <span data-ttu-id="dfe1b-126">たとえば、外部アプリケーション内でプログラムによってノードが追加、削除、または変更された場合です。</span><span class="sxs-lookup"><span data-stu-id="dfe1b-126">For example, adding, deleting, or modifying a node programmatically in an external application.</span></span>  
  
 <span data-ttu-id="dfe1b-127">作業メモリ内のオブジェクトの新しい表現は次のようになります。</span><span class="sxs-lookup"><span data-stu-id="dfe1b-127">The new representation of the objects in working memory is as follows.</span></span>  
  
 <span data-ttu-id="dfe1b-128">**P**</span><span class="sxs-lookup"><span data-stu-id="dfe1b-128">**P**</span></span>  
  
 <span data-ttu-id="dfe1b-129">**C**1 (**C**1 **。x** = 1)</span><span class="sxs-lookup"><span data-stu-id="dfe1b-129">**C**1 (**C**1.**x** = 1)</span></span>  
  
 <span data-ttu-id="dfe1b-130">**C**2 (**C**2 **。x** = *0*)</span><span class="sxs-lookup"><span data-stu-id="dfe1b-130">**C**2 (**C**2.**x** = *0*)</span></span>  
  
 <span data-ttu-id="dfe1b-131">**D**</span><span class="sxs-lookup"><span data-stu-id="dfe1b-131">**D**</span></span>  
  
 <span data-ttu-id="dfe1b-132">ここで、再アサート**P**です。次に子ノードの動作を簡単に説明します。</span><span class="sxs-lookup"><span data-stu-id="dfe1b-132">Now, reassert **P**. The following points summarize the behaviors of the child nodes:</span></span>  
  
-   <span data-ttu-id="dfe1b-133">ノード**C**そのフィールドが更新された後にダーティになったために、2 が再アサートします。</span><span class="sxs-lookup"><span data-stu-id="dfe1b-133">Node **C**2 is reasserted, because it has become dirty after its field being updated.</span></span>  
  
-   <span data-ttu-id="dfe1b-134">ノード**C**3 は作業メモリから取り消されます。</span><span class="sxs-lookup"><span data-stu-id="dfe1b-134">Node **C**3 is retracted from the working memory.</span></span>  
  
-   <span data-ttu-id="dfe1b-135">ノード**D**が作業メモリにアサートします。</span><span class="sxs-lookup"><span data-stu-id="dfe1b-135">Node **D** is asserted into the working memory.</span></span>  
  
-   <span data-ttu-id="dfe1b-136">ノード**C**する前に更新されませんでしたので 1 の作業メモリに変更されないまま**P**が再アサートします。</span><span class="sxs-lookup"><span data-stu-id="dfe1b-136">Node **C**1 remains unchanged in the working memory, because it was not updated before **P** was reasserted.</span></span>  
  
## <a name="typeddatatable"></a><span data-ttu-id="dfe1b-137">TypedDataTable</span><span class="sxs-lookup"><span data-stu-id="dfe1b-137">TypedDataTable</span></span>  
 <span data-ttu-id="dfe1b-138">場合**Reassert**で発行される、 **TypedDataRow**、その行が取り消され、作業メモリにアサートされます。</span><span class="sxs-lookup"><span data-stu-id="dfe1b-138">If **Reassert** is issued on a **TypedDataRow**, that row is retracted and then asserted into working memory.</span></span> <span data-ttu-id="dfe1b-139">場合**Reassert**で発行される、 **TypedDataTable**、関連付けられているすべて**TypedDataRow**s が取り消され、アサートされます。</span><span class="sxs-lookup"><span data-stu-id="dfe1b-139">If **Reassert** is issued on the **TypedDataTable**, all associated **TypedDataRow**s are retracted and then asserted.</span></span>  
  
## <a name="dataconnection"></a><span data-ttu-id="dfe1b-140">DataConnection</span><span class="sxs-lookup"><span data-stu-id="dfe1b-140">DataConnection</span></span>  
 <span data-ttu-id="dfe1b-141">すべて**TypedDataRow**使用して取得された、 **DataConnection**が取り消されます。</span><span class="sxs-lookup"><span data-stu-id="dfe1b-141">All **TypedDataRow**s retrieved through the **DataConnection** are retracted.</span></span> <span data-ttu-id="dfe1b-142">使用するすべての述語、 **DataConnection**はし、再評価され、 **DataConnection**に関連するを作成するクエリで**TypedDataRow**s。</span><span class="sxs-lookup"><span data-stu-id="dfe1b-142">All predicates that use the **DataConnection** are then re-evaluated, causing the **DataConnection** to be requeried to create the relevant **TypedDataRow**s.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="dfe1b-143">参照</span><span class="sxs-lookup"><span data-stu-id="dfe1b-143">See Also</span></span>  
 [<span data-ttu-id="dfe1b-144">エンジン制御関数</span><span class="sxs-lookup"><span data-stu-id="dfe1b-144">Engine Control Functions</span></span>](../core/engine-control-functions.md)