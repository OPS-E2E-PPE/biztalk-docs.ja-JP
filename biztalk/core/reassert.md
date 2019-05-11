---
title: 再アサート |Microsoft Docs
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
ms.openlocfilehash: 23cebbb268e57d71a1702a03d2516892c1851e8c
ms.sourcegitcommit: 381e83d43796a345488d54b3f7413e11d56ad7be
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 05/07/2019
ms.locfileid: "65398247"
---
# <a name="reassert"></a><span data-ttu-id="a2aff-102">再アサート</span><span class="sxs-lookup"><span data-stu-id="a2aff-102">Reassert</span></span>
<span data-ttu-id="a2aff-103">*再アサート*を呼び出す意味、 **Assert**エンジンにあるオブジェクトに対して関数の作業メモリ。</span><span class="sxs-lookup"><span data-stu-id="a2aff-103">To *reassert* means to call the **Assert** function on an object that is already in the engine's working memory.</span></span> <span data-ttu-id="a2aff-104">Reassert コマンドは、続けて assert コマンドは、オブジェクトに対して retract コマンドの発行と同じです。</span><span class="sxs-lookup"><span data-stu-id="a2aff-104">A reassert command is equivalent to issuing a retract command for the object, followed by an assert command.</span></span>  
  
## <a name="net-objects"></a><span data-ttu-id="a2aff-105">.NET オブジェクト</span><span class="sxs-lookup"><span data-stu-id="a2aff-105">.NET Objects</span></span>  
 <span data-ttu-id="a2aff-106">オブジェクトが最初に取り消され、(述語またはアクションの場合) 内のオブジェクトを使用するルールの議題に関するアクションが削除されます。</span><span class="sxs-lookup"><span data-stu-id="a2aff-106">The object is first retracted and any actions on the agenda for rules that use the object (in a predicate or action) are removed.</span></span> <span data-ttu-id="a2aff-107">オブジェクトが作業メモリにアサートしが新しくアサートされている任意のオブジェクトとして評価します。</span><span class="sxs-lookup"><span data-stu-id="a2aff-107">The object is then asserted back into working memory and evaluated as any object that is newly asserted.</span></span> <span data-ttu-id="a2aff-108">つまり、述語内でオブジェクトを使用するルールが再評価され、そのアクションが議題に適切に追加されます。</span><span class="sxs-lookup"><span data-stu-id="a2aff-108">This means that any rules that use the object in a predicate are re-evaluated and their actions are added to the agenda as appropriate.</span></span> <span data-ttu-id="a2aff-109">以前に評価されるルール**true**とのみを使用して、アクション内のオブジェクトがある、議題に再び追加します。</span><span class="sxs-lookup"><span data-stu-id="a2aff-109">Any rules that previously evaluated to **true** and only use the object in their actions will have their actions re-added to the agenda.</span></span>  
  
## <a name="typedxmldocument"></a><span data-ttu-id="a2aff-110">TypedXmlDocument</span><span class="sxs-lookup"><span data-stu-id="a2aff-110">TypedXmlDocument</span></span>  
 <span data-ttu-id="a2aff-111">ときに最上位レベル**TypedXmlDocument** (**TXD**) 再アサートされて、子**TXD**があるときに作成されます最上位レベル**TXD**最初にはアサートされる子の状態に応じて異なる動作がある**TXD**秒。</span><span class="sxs-lookup"><span data-stu-id="a2aff-111">When a top level **TypedXmlDocument** (**TXD**) is reasserted, the child **TXD**s that are created when the top level **TXD** is initially asserted have different behaviors depending on the state of the child **TXD**s.</span></span> <span data-ttu-id="a2aff-112">場合は、新しい子ノードまたはがダーティの場合、そのフィールドの少なくとも 1 つが変更されているポリシーで、ルールのアクション、アサートを使用して、つまりまたはアクションを再アサートする子ノードが子ノードで実行されます。</span><span class="sxs-lookup"><span data-stu-id="a2aff-112">In the case of a new child node or a child node that is dirty, meaning that at least one of its fields has been changed in the policy by using a rule action, an assert, or reassert action is performed on the child node.</span></span> <span data-ttu-id="a2aff-113">ダーティでない既存の子ノードは、作業メモリに残ります。</span><span class="sxs-lookup"><span data-stu-id="a2aff-113">Any existing child node that is not dirty remains in the working memory.</span></span> <span data-ttu-id="a2aff-114">次の例は、その親ノードが再アサートされたときに、子ノードの動作を説明する簡単なシナリオです。</span><span class="sxs-lookup"><span data-stu-id="a2aff-114">The following example is a simplified scenario that describes the behaviors of the child nodes when their parent node is reasserted.</span></span>  
  
 <span data-ttu-id="a2aff-115">3 つを使用する必要があると仮定**TXD**作業メモリに現在の秒。**P**、 **C**1、 **C**2、および**C**3。</span><span class="sxs-lookup"><span data-stu-id="a2aff-115">Assume there are three **TXD**s currently in the working memory: **P**, **C**1, **C**2, and **C**3.</span></span> <span data-ttu-id="a2aff-116">**P**最上位レベル**TXD**、親ノードです。 各子ノードには、フィールドが含まれています。 **x**します。</span><span class="sxs-lookup"><span data-stu-id="a2aff-116">**P** is the top level **TXD**, the parent node; each child node contains a field **x**.</span></span>  
  
 <span data-ttu-id="a2aff-117">**P**</span><span class="sxs-lookup"><span data-stu-id="a2aff-117">**P**</span></span>  
  
 <span data-ttu-id="a2aff-118">**C**1 (**C**1 **。x** = 1)</span><span class="sxs-lookup"><span data-stu-id="a2aff-118">**C**1 (**C**1.**x** = 1)</span></span>  
  
 <span data-ttu-id="a2aff-119">**C**2 (**C**2 **。x** = 1)</span><span class="sxs-lookup"><span data-stu-id="a2aff-119">**C**2 (**C**2.**x** = 1)</span></span>  
  
 <span data-ttu-id="a2aff-120">**C**3 (**C**3 **。x** = 1)</span><span class="sxs-lookup"><span data-stu-id="a2aff-120">**C**3 (**C**3.**x** = 1)</span></span>  
  
 <span data-ttu-id="a2aff-121">次に、ルール アクションの結果として、次の操作が実行されたと仮定します。</span><span class="sxs-lookup"><span data-stu-id="a2aff-121">Next, assume the following operations have been performed as a result of rule action:</span></span>  
  
-   <span data-ttu-id="a2aff-122">フィールド (**x**) の場合は値**C**2 が更新されます。</span><span class="sxs-lookup"><span data-stu-id="a2aff-122">The field (**x**) value for **C**2 is updated.</span></span>  
  
-   <span data-ttu-id="a2aff-123">**C**ユーザー コードを使用して 3 が削除されます。</span><span class="sxs-lookup"><span data-stu-id="a2aff-123">**C**3 is deleted by using user code.</span></span>  
  
-   <span data-ttu-id="a2aff-124">追加の子ノード、 **D**に追加されます**P**ユーザー コードを使用しています。</span><span class="sxs-lookup"><span data-stu-id="a2aff-124">An additional child node, **D**, is added to **P** by using user code.</span></span>  
  
> [!NOTE]
>  <span data-ttu-id="a2aff-125">ノードはないダーティであるが、エンジンが関知しない操作からビジネス ルール エンジン。</span><span class="sxs-lookup"><span data-stu-id="a2aff-125">A node will not be marked dirty by the Business Rule Engine from operations, of which the engine is not aware.</span></span> <span data-ttu-id="a2aff-126">などの追加、削除、または外部アプリケーションでプログラムでノードを変更します。</span><span class="sxs-lookup"><span data-stu-id="a2aff-126">For example, adding, deleting, or modifying a node programmatically in an external application.</span></span>  
  
 <span data-ttu-id="a2aff-127">作業メモリ内のオブジェクトの新しい表現は次のとおりです。</span><span class="sxs-lookup"><span data-stu-id="a2aff-127">The new representation of the objects in working memory is as follows.</span></span>  
  
 <span data-ttu-id="a2aff-128">**P**</span><span class="sxs-lookup"><span data-stu-id="a2aff-128">**P**</span></span>  
  
 <span data-ttu-id="a2aff-129">**C**1 (**C**1 **。x** = 1)</span><span class="sxs-lookup"><span data-stu-id="a2aff-129">**C**1 (**C**1.**x** = 1)</span></span>  
  
 <span data-ttu-id="a2aff-130">**C**2 (**C**2 **。x** = *0*)</span><span class="sxs-lookup"><span data-stu-id="a2aff-130">**C**2 (**C**2.**x** = *0*)</span></span>  
  
 <span data-ttu-id="a2aff-131">**D**</span><span class="sxs-lookup"><span data-stu-id="a2aff-131">**D**</span></span>  
  
 <span data-ttu-id="a2aff-132">ここで、再アサート**P**します。子ノードの動作を以下にまとめました。</span><span class="sxs-lookup"><span data-stu-id="a2aff-132">Now, reassert **P**. The following points summarize the behaviors of the child nodes:</span></span>  
  
-   <span data-ttu-id="a2aff-133">ノード**C**更新されているそのフィールドの後にダーティになったため、2 がアサートします。</span><span class="sxs-lookup"><span data-stu-id="a2aff-133">Node **C**2 is reasserted, because it has become dirty after its field being updated.</span></span>  
  
-   <span data-ttu-id="a2aff-134">ノード**C**3 が作業メモリから取り消されます。</span><span class="sxs-lookup"><span data-stu-id="a2aff-134">Node **C**3 is retracted from the working memory.</span></span>  
  
-   <span data-ttu-id="a2aff-135">ノード**D**作業メモリにアサートされます。</span><span class="sxs-lookup"><span data-stu-id="a2aff-135">Node **D** is asserted into the working memory.</span></span>  
  
-   <span data-ttu-id="a2aff-136">ノード**C**する前に更新されていないために、1 は未変更のままで、作業メモリ**P**が再アサートされます。</span><span class="sxs-lookup"><span data-stu-id="a2aff-136">Node **C**1 remains unchanged in the working memory, because it was not updated before **P** was reasserted.</span></span>  
  
## <a name="typeddatatable"></a><span data-ttu-id="a2aff-137">TypedDataTable</span><span class="sxs-lookup"><span data-stu-id="a2aff-137">TypedDataTable</span></span>  
 <span data-ttu-id="a2aff-138">場合**再アサート**で発生したは、 **TypedDataRow**、その行が取り消され、作業メモリにアサートされます。</span><span class="sxs-lookup"><span data-stu-id="a2aff-138">If **Reassert** is issued on a **TypedDataRow**, that row is retracted and then asserted into working memory.</span></span> <span data-ttu-id="a2aff-139">場合**再アサート**で発生したは、 **TypedDataTable**、関連するすべて**TypedDataRow**s が取り消され、アサートされます。</span><span class="sxs-lookup"><span data-stu-id="a2aff-139">If **Reassert** is issued on the **TypedDataTable**, all associated **TypedDataRow**s are retracted and then asserted.</span></span>  
  
## <a name="dataconnection"></a><span data-ttu-id="a2aff-140">DataConnection</span><span class="sxs-lookup"><span data-stu-id="a2aff-140">DataConnection</span></span>  
 <span data-ttu-id="a2aff-141">すべて**TypedDataRow**して取得された、 **DataConnection**が取り消されます。</span><span class="sxs-lookup"><span data-stu-id="a2aff-141">All **TypedDataRow**s retrieved through the **DataConnection** are retracted.</span></span> <span data-ttu-id="a2aff-142">使用するすべての述語、 **DataConnection**は再評価、原因、 **DataConnection**を作成、関連するクエリを再実行する**TypedDataRow**s。</span><span class="sxs-lookup"><span data-stu-id="a2aff-142">All predicates that use the **DataConnection** are then re-evaluated, causing the **DataConnection** to be requeried to create the relevant **TypedDataRow**s.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="a2aff-143">参照</span><span class="sxs-lookup"><span data-stu-id="a2aff-143">See Also</span></span>  
 [<span data-ttu-id="a2aff-144">エンジン制御関数</span><span class="sxs-lookup"><span data-stu-id="a2aff-144">Engine Control Functions</span></span>](../core/engine-control-functions.md)