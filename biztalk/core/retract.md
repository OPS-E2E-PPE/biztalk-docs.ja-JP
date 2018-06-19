---
title: 取り消し |Microsoft ドキュメント
ms.custom: ''
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: ''
ms.suite: ''
ms.tgt_pltfrm: ''
ms.topic: article
helpviewer_keywords:
- Retract function [Business Rules Engine], TypedData table
- Retract function [Business Rules Engine], TypedXMLDocument
- Retract function [Business Rules Engine]
- Retract function [Business Rules Engine], DataConnection
- Retract function [Business Rules Engine], .NET objects
- .NET objects
ms.assetid: 24b6b894-6810-4497-a122-8c91f0b2e816
caps.latest.revision: 7
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: 17eb4739412d310d2a69b53c8470abc7461ce3ce
ms.sourcegitcommit: cb908c540d8f1a692d01dc8f313e16cb4b4e696d
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 09/20/2017
ms.locfileid: "22270114"
---
# <a name="retract"></a><span data-ttu-id="44f13-102">取り消し</span><span class="sxs-lookup"><span data-stu-id="44f13-102">Retract</span></span>
<span data-ttu-id="44f13-103">使用することができます、 **Retract**関数をビジネス ルール エンジンの作業メモリからオブジェクトを削除します。</span><span class="sxs-lookup"><span data-stu-id="44f13-103">You can use the **Retract** function to remove objects from the Business Rule Engine's working memory.</span></span> <span data-ttu-id="44f13-104">ここでは、ルール エンジンの作業メモリからさまざまな種類のエンティティを取り消す操作に関係する動作について説明します。</span><span class="sxs-lookup"><span data-stu-id="44f13-104">The following paragraphs describe the behavior associated with retracting entities of different types from the rule engine's working memory.</span></span>  
  
## <a name="net-objects"></a><span data-ttu-id="44f13-105">.NET オブジェクト</span><span class="sxs-lookup"><span data-stu-id="44f13-105">.NET Objects</span></span>  
 <span data-ttu-id="44f13-106">使用して、ポリシーで .NET オブジェクトが取り消され、 **Retract**関数。</span><span class="sxs-lookup"><span data-stu-id="44f13-106">A .NET object is retracted in a policy by using the **Retract** function.</span></span> <span data-ttu-id="44f13-107">この関数は、として、ビジネス ルール作成ツールで使用できる、**関数**ボキャブラリ項目: クラス (ないアセンブリまたはメソッド) にドラッグ、 **Retract**パラメーター。</span><span class="sxs-lookup"><span data-stu-id="44f13-107">This function is available in the Business Rule Composer as a **Functions** vocabulary item: drag the class (not the assembly or method) into the **Retract** parameter.</span></span>  
  
> [!NOTE]
>  <span data-ttu-id="44f13-108">メソッドをドラッグする場合、 **Retract**関数、エンジンは、メソッドによって返されるオブジェクトを取り消すしようとします。</span><span class="sxs-lookup"><span data-stu-id="44f13-108">If you drag a method into the **Retract** function, the engine attempts to retract the object returned by the method.</span></span>  
  
 <span data-ttu-id="44f13-109">.NET オブジェクトを取り消すと、ルール エンジンの作業メモリからそのオブジェクトが削除され、次に示される影響を受けます。</span><span class="sxs-lookup"><span data-stu-id="44f13-109">Retracting a .NET object removes it from the rule engine's working memory and has the following impact:</span></span>  
  
-   <span data-ttu-id="44f13-110">述語でオブジェクトを使用しているルールでは、議題にアクションが存在する場合、議題からアクションを削除します。</span><span class="sxs-lookup"><span data-stu-id="44f13-110">Rules that use the object in a predicate have their actions removed from the agenda (if any exist on the agenda).</span></span>  
  
-   <span data-ttu-id="44f13-111">オブジェクトを使用している議題のアクションは、議題から削除されます。</span><span class="sxs-lookup"><span data-stu-id="44f13-111">Actions on the agenda that use the objects are removed from the agenda.</span></span>  
  
    > [!NOTE]
    >  <span data-ttu-id="44f13-112">前に、その他のアクションが議題によりも上位を既に実行されている可能性があります、 **Retract**関数が呼び出されました。</span><span class="sxs-lookup"><span data-stu-id="44f13-112">Other actions higher up on the agenda may have already executed before the **Retract** function was called.</span></span>  
  
-   <span data-ttu-id="44f13-113">オブジェクトがエンジンによって評価されなくなります。</span><span class="sxs-lookup"><span data-stu-id="44f13-113">The object is no longer evaluated by the engine.</span></span>  
  
## <a name="typedxmldocument"></a><span data-ttu-id="44f13-114">TypedXmlDocument</span><span class="sxs-lookup"><span data-stu-id="44f13-114">TypedXmlDocument</span></span>  
 <span data-ttu-id="44f13-115">オリジナルを取り消すことができますか**TypedXmlDocument**をエンジンにアサートされたまたは子の 1 つを取り消す**TypedXmlDocument**の親ノードから作成された s **XmlDocument**.</span><span class="sxs-lookup"><span data-stu-id="44f13-115">You can either retract the original **TypedXmlDocument** that was asserted into the engine or retract one of the child **TypedXmlDocument**s created from a node of the parent **XmlDocument**.</span></span>  
  
 <span data-ttu-id="44f13-116">例として、次の XML を使用することができますか、取り消し、 **TypedXmlDocument**順序またはの一方または両方に関連付けられている、 **TypedXmlDocument**s orderline に関連付けられています。</span><span class="sxs-lookup"><span data-stu-id="44f13-116">Using the following XML as an example, you can either retract the **TypedXmlDocument** associated with order or one or both of the **TypedXmlDocument**s associated with orderline.</span></span>  
  
```  
<order>  
   <orderline customer="Joe" linenumber="001">  
      <product name="router" quantity="10" cost="550" />  
   </orderline>  
   <orderline customer="Jane" linenumber="002">  
      <product name="switch" quantity="1" cost="300" />  
   </orderline>  
</order>  
```  
  
 <span data-ttu-id="44f13-117">注文オブジェクトを取り消すには、スキーマの最上位のノードを XML スキーマ ファクト ペインにドラッグします。</span><span class="sxs-lookup"><span data-stu-id="44f13-117">To retract the order object, you would drag the top node for the schema in the XML Schemas fact pane.</span></span> <span data-ttu-id="44f13-118">このノードが".xsd"で終わるし、ドキュメント ルート ノード (ドキュメント要素ノードではなく); を表します初期を表す「/」セレクターが**TypedXmlDocument**です。</span><span class="sxs-lookup"><span data-stu-id="44f13-118">This node ends in ".xsd" and represents the document root node (not the document element node); it has a "/" selector that refers to the initial **TypedXmlDocument**.</span></span> <span data-ttu-id="44f13-119">ときに、親**TypedXmlDocument**が取り消される場合、すべて**TypedXmlDocument**インスタンスに関連付けられている、 **TypedXmlDocument** (すべて**TypedXmlDocument**呼び出すことによって作成された、 **Assert**関数は、ポリシーで使用されるセレクターに基づいた) 作業メモリから削除されます。</span><span class="sxs-lookup"><span data-stu-id="44f13-119">When the parent **TypedXmlDocument** is retracted, all **TypedXmlDocument** instances associated with the **TypedXmlDocument** (all **TypedXmlDocument**s created by calling the **Assert** function based on selectors used in the policy) are removed from working memory.</span></span>  
  
 <span data-ttu-id="44f13-120">取り消すには、個々 の子のみ**TypedXmlDocument** (つまり、orderline) に XML スキーマ ペインからこのノードをドラッグすることができます、 **Retract**関数。</span><span class="sxs-lookup"><span data-stu-id="44f13-120">To retract only an individual child **TypedXmlDocument** (that is an orderline), you can drag this node from the XML Schemas pane into the **Retract** function.</span></span> <span data-ttu-id="44f13-121">重要な点はすべて**TypedXmlDocument**s は最上位レベルに関連付けられた**TypedXmlDocument**を最初にアサートされたではなく、 **TypedXmlDocument**XML ツリーの階層で上に表示されます。</span><span class="sxs-lookup"><span data-stu-id="44f13-121">It is important to note that all **TypedXmlDocument**s are associated with the top-level **TypedXmlDocument** that was originally asserted, and not with the **TypedXmlDocument** that appears above it in the XML tree hierarchy.</span></span> <span data-ttu-id="44f13-122">たとえば、製品が、 **TypedXmlDocument** 、orderline オブジェクト以下ためになります、注文に関連付けられた**TypedXmlDocument**、orderline ではなく**TypedXmlDocument**です。</span><span class="sxs-lookup"><span data-stu-id="44f13-122">For example, product is a **TypedXmlDocument** below the orderline object; therefore, it would be associated with the order **TypedXmlDocument**, and not with the orderline **TypedXmlDocument**.</span></span> <span data-ttu-id="44f13-123">ほとんどのインスタンスで、この区別は重要ではありません。</span><span class="sxs-lookup"><span data-stu-id="44f13-123">In most instances, this distinction is not important.</span></span> <span data-ttu-id="44f13-124">ただし、注文オブジェクトを取り消すと、Orderline オブジェクトと Product オブジェクトも取り消されます。</span><span class="sxs-lookup"><span data-stu-id="44f13-124">However, if you retract the order object, the orderline and product objects are also retracted.</span></span> <span data-ttu-id="44f13-125">Orderline オブジェクトを取り消すと、そのオブジェクトだけが取り消されます。Product オブジェクトは取り消されません。</span><span class="sxs-lookup"><span data-stu-id="44f13-125">If you retract the orderline object, only that object is retracted, and not the product object.</span></span>  
  
 <span data-ttu-id="44f13-126">エンジンだけを処理してオブジェクト インスタンスの追跡 (**TypedXmlDocument**s) ときに作成された、 **TypedXmlDocument**が最初にアサートされました。</span><span class="sxs-lookup"><span data-stu-id="44f13-126">The engine only works with and tracks object instances (**TypedXmlDocument**s) that it created when the **TypedXmlDocument** was initially asserted.</span></span> <span data-ttu-id="44f13-127">他のノードを作成する場合: セレクター ポリシーで選択されたノードを兄弟ノードなど、— しない限り、これらのノードがルールで評価されません**TypedXmlDocument**s が作成され、それらのアサートします。</span><span class="sxs-lookup"><span data-stu-id="44f13-127">If you create additional nodes—for example, sibling nodes to a node that was selected through a selector in the policy—these nodes are not evaluated in rules unless **TypedXmlDocument**s are created and asserted for them.</span></span> <span data-ttu-id="44f13-128">これらの新しい、下位のアサート**TypedXmlDocuments** 、規則が、最上位レベルで評価する**TypedXmlDocument**それらの情報を持っていません。</span><span class="sxs-lookup"><span data-stu-id="44f13-128">Asserting these new, lower-level **TypedXmlDocuments** causes them to be evaluated in rules, but the top-level **TypedXmlDocument** does not have knowledge of them.</span></span> <span data-ttu-id="44f13-129">ときに、最上位**TypedXmlDocument**が取り消される場合、新しい、個別にアサートされた**TypedXmlDocument**自動的に取り消される場合。</span><span class="sxs-lookup"><span data-stu-id="44f13-129">When the top-level **TypedXmlDocument** is retracted, the new, independently asserted **TypedXmlDocument**s isl not automatically retracted.</span></span> <span data-ttu-id="44f13-130">その結果、新しいノードが作成される場合を取り消し、完全に再アサートする最も簡単な通常**XmlDocument**です。</span><span class="sxs-lookup"><span data-stu-id="44f13-130">As a result, if new nodes are created, it is typically most straightforward to retract and reassert the full **XmlDocument**.</span></span>  
  
 <span data-ttu-id="44f13-131">**TypedXmlDocument**クラスはさまざまな操作の一部としてカスタム .NET メンバー内で呼び出すことが便利なメソッドをサポートします。</span><span class="sxs-lookup"><span data-stu-id="44f13-131">The **TypedXmlDocument** class supports a number of useful methods that can be called within a custom .NET member as part of an action.</span></span> <span data-ttu-id="44f13-132">取得する機能が含まれます、 **XmlNode**に関連付けられている、 **TypedXmlDocument**または親**TypedXmlDocument**です。</span><span class="sxs-lookup"><span data-stu-id="44f13-132">These include the ability to get the **XmlNode** associated with the **TypedXmlDocument** or the parent **TypedXmlDocument**.</span></span>  
  
## <a name="typeddatatable"></a><span data-ttu-id="44f13-133">TypedDataTable</span><span class="sxs-lookup"><span data-stu-id="44f13-133">TypedDataTable</span></span>  
 <span data-ttu-id="44f13-134">個別を撤回する**TypedDataRow**s または全体**TypedDataTable**です。</span><span class="sxs-lookup"><span data-stu-id="44f13-134">You can retract either individual **TypedDataRow**s or the entire **TypedDataTable**.</span></span> <span data-ttu-id="44f13-135">テーブルを取り消す場合、含まれるすべての行が作業メモリから取り消されます。</span><span class="sxs-lookup"><span data-stu-id="44f13-135">If you retract a table, all the containing rows are retracted from working memory.</span></span>  
  
 <span data-ttu-id="44f13-136">全体を取り消す**TypedDataTable**ヘルパー関数を使用してアクセスする必要があります、**親**プロパティ**TypedDataRow**、たとえば。</span><span class="sxs-lookup"><span data-stu-id="44f13-136">To retract the entire **TypedDataTable** you need to use a helper function to access the **Parent** property on **TypedDataRow**, for example:</span></span>  
  
```  
Retract(MyHelper.GetTypedDataTable(TypedDataRow))  
```  
  
 <span data-ttu-id="44f13-137">前のアクションでは、テーブルをドラッグして**TypedDataRow**です。</span><span class="sxs-lookup"><span data-stu-id="44f13-137">In the preceding action, you would drag the table into **TypedDataRow**.</span></span> <span data-ttu-id="44f13-138">**GetTypedDataTable**の値を返すよう**TypedDataRow.Parent**です。</span><span class="sxs-lookup"><span data-stu-id="44f13-138">In **GetTypedDataTable** you would return the value of **TypedDataRow.Parent**.</span></span>  
  
 <span data-ttu-id="44f13-139">同様に**TypedXmlDocument**新規で追加、アサートする場合は、s、 **TypedDataRow**秒であり、同じ**DataTable**アサートの後に、 **TypedDataTable**、個々 のエンティティと取り消しとして扱われます、 **TypedDataTable**発生するわけでこれらの取り消し余分な**TypedDataRow**s。</span><span class="sxs-lookup"><span data-stu-id="44f13-139">As with **TypedXmlDocument**s, if you assert additional, new **TypedDataRow**s for the same **DataTable** after asserting the **TypedDataTable**, they are treated as individual entities and retracting the **TypedDataTable** does not result in the retraction of these extra **TypedDataRow**s.</span></span> <span data-ttu-id="44f13-140">のみ、 **TypedDataRow**に格納されている、 **TypedDataTable**がアサートされたときに取り消されます。</span><span class="sxs-lookup"><span data-stu-id="44f13-140">Only the **TypedDataRow**s contained in the **TypedDataTable** when it was asserted are retracted.</span></span>  
  
## <a name="dataconnection"></a><span data-ttu-id="44f13-141">DataConnection</span><span class="sxs-lookup"><span data-stu-id="44f13-141">DataConnection</span></span>  
 <span data-ttu-id="44f13-142">ときに、 **DataConnection**が取り消される場合、すべて**TypedDataRow**によって構築されたクエリを使用して、データベースから取得される、 **DataConnection**から取り消されます作業メモリです。</span><span class="sxs-lookup"><span data-stu-id="44f13-142">When a **DataConnection** is retracted, all **TypedDataRow**s retrieved from the database through the query constructed by the **DataConnection** are retracted from working memory.</span></span> <span data-ttu-id="44f13-143">**DataConnection**自体も取り消されます、つまり、これ以上ありません**TypedDataRow**s はから取得する、 **DataConnection** (つまりの使用、 **DataConnection**他の述語またはアクションで)。</span><span class="sxs-lookup"><span data-stu-id="44f13-143">The **DataConnection** itself is also retracted, meaning that no more **TypedDataRow**s will be retrieved through the **DataConnection** (that is, through use of the **DataConnection** in other predicates or actions).</span></span>  
  
 <span data-ttu-id="44f13-144">使用する場合、 **DataConnection**、個別の操作を取り消し、 **TypedDataRow**が不整合な状態に、エンジンを設定します。</span><span class="sxs-lookup"><span data-stu-id="44f13-144">When using a **DataConnection**, any retract operation on an individual **TypedDataRow** puts the engine into an inconsistent state.</span></span> <span data-ttu-id="44f13-145">そのため、操作が個別の許可されていません**TypedDataRow**に関連付けられている、 **DataConnection**です。</span><span class="sxs-lookup"><span data-stu-id="44f13-145">Therefore, operations are not allowed on individual **TypedDataRow**s associated with a **DataConnection**.</span></span> <span data-ttu-id="44f13-146">テーブルをドラッグする場合 (を使用して、 **DataConnection**パラメーター) に、 **Retract**関数、したが取り消されます、 **DataConnection**です。</span><span class="sxs-lookup"><span data-stu-id="44f13-146">If you drag the table (using the **DataConnection** parameter) into the **Retract** function, you will be retracting the **DataConnection**.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="44f13-147">参照</span><span class="sxs-lookup"><span data-stu-id="44f13-147">See Also</span></span>  
 [<span data-ttu-id="44f13-148">エンジン制御関数</span><span class="sxs-lookup"><span data-stu-id="44f13-148">Engine Control Functions</span></span>](../core/engine-control-functions.md)