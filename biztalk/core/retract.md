---
title: 取り消し |Microsoft Docs
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
ms.openlocfilehash: 94967d573bf4293c0a2dcf6bf6c718f79d19736f
ms.sourcegitcommit: 381e83d43796a345488d54b3f7413e11d56ad7be
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 05/07/2019
ms.locfileid: "65399083"
---
# <a name="retract"></a><span data-ttu-id="b38ce-102">取り消し</span><span class="sxs-lookup"><span data-stu-id="b38ce-102">Retract</span></span>
<span data-ttu-id="b38ce-103">使用することができます、 **Retract**ビジネス ルール エンジンの作業メモリからオブジェクトを削除する関数。</span><span class="sxs-lookup"><span data-stu-id="b38ce-103">You can use the **Retract** function to remove objects from the Business Rule Engine's working memory.</span></span> <span data-ttu-id="b38ce-104">次の段落では、ルール エンジンの作業メモリからさまざまな種類のエンティティを取り消す操作に関連付けられている動作を説明します。</span><span class="sxs-lookup"><span data-stu-id="b38ce-104">The following paragraphs describe the behavior associated with retracting entities of different types from the rule engine's working memory.</span></span>  
  
## <a name="net-objects"></a><span data-ttu-id="b38ce-105">.NET オブジェクト</span><span class="sxs-lookup"><span data-stu-id="b38ce-105">.NET Objects</span></span>  
 <span data-ttu-id="b38ce-106">ポリシーを使用して .NET オブジェクトが取り消され、 **Retract**関数。</span><span class="sxs-lookup"><span data-stu-id="b38ce-106">A .NET object is retracted in a policy by using the **Retract** function.</span></span> <span data-ttu-id="b38ce-107">この関数は、ビジネス ルール作成ツールとして、**関数**ボキャブラリ項目: (しないアセンブリまたはメソッド) のクラスをドラッグ、 **Retract**パラメーター。</span><span class="sxs-lookup"><span data-stu-id="b38ce-107">This function is available in the Business Rule Composer as a **Functions** vocabulary item: drag the class (not the assembly or method) into the **Retract** parameter.</span></span>  
  
> [!NOTE]
>  <span data-ttu-id="b38ce-108">メソッドをドラッグする場合、 **Retract**関数、エンジンは、メソッドによって返されるオブジェクトを取り消すとします。</span><span class="sxs-lookup"><span data-stu-id="b38ce-108">If you drag a method into the **Retract** function, the engine attempts to retract the object returned by the method.</span></span>  
  
 <span data-ttu-id="b38ce-109">.NET オブジェクトを取り消すと、ルール エンジンの作業メモリから削除されます、次の影響します。</span><span class="sxs-lookup"><span data-stu-id="b38ce-109">Retracting a .NET object removes it from the rule engine's working memory and has the following impact:</span></span>  
  
-   <span data-ttu-id="b38ce-110">述語でオブジェクトを使用する規則があるアクションを (議題にある) 場合、議題から削除します。</span><span class="sxs-lookup"><span data-stu-id="b38ce-110">Rules that use the object in a predicate have their actions removed from the agenda (if any exist on the agenda).</span></span>  
  
-   <span data-ttu-id="b38ce-111">オブジェクトを使用する議題のアクションは、議題から削除されます。</span><span class="sxs-lookup"><span data-stu-id="b38ce-111">Actions on the agenda that use the objects are removed from the agenda.</span></span>  
  
    > [!NOTE]
    >  <span data-ttu-id="b38ce-112">前に、その他のアクションが議題の上位を既に実行されている可能性があります、 **Retract**関数が呼び出されました。</span><span class="sxs-lookup"><span data-stu-id="b38ce-112">Other actions higher up on the agenda may have already executed before the **Retract** function was called.</span></span>  
  
-   <span data-ttu-id="b38ce-113">オブジェクトは、不要になったエンジンによって評価されます。</span><span class="sxs-lookup"><span data-stu-id="b38ce-113">The object is no longer evaluated by the engine.</span></span>  
  
## <a name="typedxmldocument"></a><span data-ttu-id="b38ce-114">TypedXmlDocument</span><span class="sxs-lookup"><span data-stu-id="b38ce-114">TypedXmlDocument</span></span>  
 <span data-ttu-id="b38ce-115">元を取り消すことができますか**TypedXmlDocument**をエンジンにアサートされたまたは子の 1 つを取り消す**TypedXmlDocument**の親ノードから作成された s **XmlDocument**.</span><span class="sxs-lookup"><span data-stu-id="b38ce-115">You can either retract the original **TypedXmlDocument** that was asserted into the engine or retract one of the child **TypedXmlDocument**s created from a node of the parent **XmlDocument**.</span></span>  
  
 <span data-ttu-id="b38ce-116">例として、次の XML を使用することができます取り消すか、 **TypedXmlDocument**順序または 1 つまたは両方に関連付けられている、 **TypedXmlDocument**s orderline に関連付けられています。</span><span class="sxs-lookup"><span data-stu-id="b38ce-116">Using the following XML as an example, you can either retract the **TypedXmlDocument** associated with order or one or both of the **TypedXmlDocument**s associated with orderline.</span></span>  
  
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
  
 <span data-ttu-id="b38ce-117">注文オブジェクトを取り消すには、XML スキーマ ファクト ペインで、スキーマの最上位ノードをドラッグします。</span><span class="sxs-lookup"><span data-stu-id="b38ce-117">To retract the order object, you would drag the top node for the schema in the XML Schemas fact pane.</span></span> <span data-ttu-id="b38ce-118">このノードが".xsd"で終わるし、ドキュメントのルート ノード (ドキュメントの要素ノードではなく); を表します最初に参照する「/」セレクターが**TypedXmlDocument**します。</span><span class="sxs-lookup"><span data-stu-id="b38ce-118">This node ends in ".xsd" and represents the document root node (not the document element node); it has a "/" selector that refers to the initial **TypedXmlDocument**.</span></span> <span data-ttu-id="b38ce-119">ときに、親**TypedXmlDocument**が取り消される場合、すべて**TypedXmlDocument**インスタンスに関連付けられている、 **TypedXmlDocument** (すべて**TypedXmlDocument**呼び出すことによって作成された、 **Assert**関数は、ポリシーで使用されるセレクターに基づく) が作業メモリから削除します。</span><span class="sxs-lookup"><span data-stu-id="b38ce-119">When the parent **TypedXmlDocument** is retracted, all **TypedXmlDocument** instances associated with the **TypedXmlDocument** (all **TypedXmlDocument**s created by calling the **Assert** function based on selectors used in the policy) are removed from working memory.</span></span>  
  
 <span data-ttu-id="b38ce-120">取り消すには、個々 の子のみ**TypedXmlDocument** (つまり、orderline) に XML スキーマ ペインからこのノードをドラッグすることができます、 **Retract**関数。</span><span class="sxs-lookup"><span data-stu-id="b38ce-120">To retract only an individual child **TypedXmlDocument** (that is an orderline), you can drag this node from the XML Schemas pane into the **Retract** function.</span></span> <span data-ttu-id="b38ce-121">重要な点がすべて**TypedXmlDocument**s は、最上位レベルに関連付けられた**TypedXmlDocument**を最初にアサートされたではなく、 **TypedXmlDocument**XML ツリーの階層で上位に表示されます。</span><span class="sxs-lookup"><span data-stu-id="b38ce-121">It is important to note that all **TypedXmlDocument**s are associated with the top-level **TypedXmlDocument** that was originally asserted, and not with the **TypedXmlDocument** that appears above it in the XML tree hierarchy.</span></span> <span data-ttu-id="b38ce-122">たとえば、製品は、 **TypedXmlDocument** orderline オブジェクト; の下、なります、注文に関連付けられて**TypedXmlDocument**、orderline ではなく**TypedXmlDocument**します。</span><span class="sxs-lookup"><span data-stu-id="b38ce-122">For example, product is a **TypedXmlDocument** below the orderline object; therefore, it would be associated with the order **TypedXmlDocument**, and not with the orderline **TypedXmlDocument**.</span></span> <span data-ttu-id="b38ce-123">ほとんどの状況では、この区別は重要ではありません。</span><span class="sxs-lookup"><span data-stu-id="b38ce-123">In most instances, this distinction is not important.</span></span> <span data-ttu-id="b38ce-124">ただし、order オブジェクトを取り消す場合も、orderline オブジェクトと product オブジェクトが取り消されます。</span><span class="sxs-lookup"><span data-stu-id="b38ce-124">However, if you retract the order object, the orderline and product objects are also retracted.</span></span> <span data-ttu-id="b38ce-125">Orderline オブジェクトを取り消す場合は、そのオブジェクトのみが取り消され、および製品オブジェクトではありません。</span><span class="sxs-lookup"><span data-stu-id="b38ce-125">If you retract the orderline object, only that object is retracted, and not the product object.</span></span>  
  
 <span data-ttu-id="b38ce-126">エンジンでのみ動作し、トラック オブジェクト インスタンス (**TypedXmlDocument**s) ときに作成する、 **TypedXmlDocument**が最初にアサートされました。</span><span class="sxs-lookup"><span data-stu-id="b38ce-126">The engine only works with and tracks object instances (**TypedXmlDocument**s) that it created when the **TypedXmlDocument** was initially asserted.</span></span> <span data-ttu-id="b38ce-127">他のノードを作成する場合: セレクター、ポリシーで選択されたノードに対する兄弟ノードなど、しない限り、これらのノードがルールで評価されません**TypedXmlDocument**s が作成され、それらのアサートします。</span><span class="sxs-lookup"><span data-stu-id="b38ce-127">If you create additional nodes—for example, sibling nodes to a node that was selected through a selector in the policy—these nodes are not evaluated in rules unless **TypedXmlDocument**s are created and asserted for them.</span></span> <span data-ttu-id="b38ce-128">これらの新しいより低いレベル アサート**TypedXmlDocuments**によってそれらの規則が最上位レベルで評価される**TypedXmlDocument**それらの情報を持っていません。</span><span class="sxs-lookup"><span data-stu-id="b38ce-128">Asserting these new, lower-level **TypedXmlDocuments** causes them to be evaluated in rules, but the top-level **TypedXmlDocument** does not have knowledge of them.</span></span> <span data-ttu-id="b38ce-129">ときに、最上位**TypedXmlDocument**が取り消される場合、新しい、個別にアサートされた**TypedXmlDocument**自動的に取り消される場合。</span><span class="sxs-lookup"><span data-stu-id="b38ce-129">When the top-level **TypedXmlDocument** is retracted, the new, independently asserted **TypedXmlDocument**s isl not automatically retracted.</span></span> <span data-ttu-id="b38ce-130">その結果、新しいノードを作成すると、あるを取り消し、完全な再アサートする最も簡単な通常**XmlDocument**します。</span><span class="sxs-lookup"><span data-stu-id="b38ce-130">As a result, if new nodes are created, it is typically most straightforward to retract and reassert the full **XmlDocument**.</span></span>  
  
 <span data-ttu-id="b38ce-131">**TypedXmlDocument**クラスは、さまざまなアクションの一部としてカスタム .NET メンバー内で呼び出すことができる便利なメソッドをサポートしています。</span><span class="sxs-lookup"><span data-stu-id="b38ce-131">The **TypedXmlDocument** class supports a number of useful methods that can be called within a custom .NET member as part of an action.</span></span> <span data-ttu-id="b38ce-132">取得する機能が含まれます、 **XmlNode**に関連付けられている、 **TypedXmlDocument**または親**TypedXmlDocument**します。</span><span class="sxs-lookup"><span data-stu-id="b38ce-132">These include the ability to get the **XmlNode** associated with the **TypedXmlDocument** or the parent **TypedXmlDocument**.</span></span>  
  
## <a name="typeddatatable"></a><span data-ttu-id="b38ce-133">TypedDataTable</span><span class="sxs-lookup"><span data-stu-id="b38ce-133">TypedDataTable</span></span>  
 <span data-ttu-id="b38ce-134">どちらにもを撤回する**TypedDataRow**全体または**TypedDataTable**します。</span><span class="sxs-lookup"><span data-stu-id="b38ce-134">You can retract either individual **TypedDataRow**s or the entire **TypedDataTable**.</span></span> <span data-ttu-id="b38ce-135">テーブルを取り消す場合、含んでいるすべての行は作業メモリから取り消されます。</span><span class="sxs-lookup"><span data-stu-id="b38ce-135">If you retract a table, all the containing rows are retracted from working memory.</span></span>  
  
 <span data-ttu-id="b38ce-136">全体を取り消す**TypedDataTable**ヘルパー関数を使用してアクセスする必要があります、**親**プロパティ**TypedDataRow**、たとえば。</span><span class="sxs-lookup"><span data-stu-id="b38ce-136">To retract the entire **TypedDataTable** you need to use a helper function to access the **Parent** property on **TypedDataRow**, for example:</span></span>  
  
```  
Retract(MyHelper.GetTypedDataTable(TypedDataRow))  
```  
  
 <span data-ttu-id="b38ce-137">前のアクションでは、テーブルをドラッグして**TypedDataRow**します。</span><span class="sxs-lookup"><span data-stu-id="b38ce-137">In the preceding action, you would drag the table into **TypedDataRow**.</span></span> <span data-ttu-id="b38ce-138">**GetTypedDataTable**の値を返すよう**TypedDataRow.Parent**します。</span><span class="sxs-lookup"><span data-stu-id="b38ce-138">In **GetTypedDataTable** you would return the value of **TypedDataRow.Parent**.</span></span>  
  
 <span data-ttu-id="b38ce-139">同様**TypedXmlDocument**新規で追加すると、アサートする場合は、s、 **TypedDataRow**の同じ**DataTable**アサートした後、 **TypedDataTable**、個々 のエンティティと縮小として扱われます、 **TypedDataTable**は行われませんこれらの取り消しで余分な**TypedDataRow**秒。</span><span class="sxs-lookup"><span data-stu-id="b38ce-139">As with **TypedXmlDocument**s, if you assert additional, new **TypedDataRow**s for the same **DataTable** after asserting the **TypedDataTable**, they are treated as individual entities and retracting the **TypedDataTable** does not result in the retraction of these extra **TypedDataRow**s.</span></span> <span data-ttu-id="b38ce-140">のみ、 **TypedDataRow**に格納されている、 **TypedDataTable**がアサートされたときに取り消されます。</span><span class="sxs-lookup"><span data-stu-id="b38ce-140">Only the **TypedDataRow**s contained in the **TypedDataTable** when it was asserted are retracted.</span></span>  
  
## <a name="dataconnection"></a><span data-ttu-id="b38ce-141">DataConnection</span><span class="sxs-lookup"><span data-stu-id="b38ce-141">DataConnection</span></span>  
 <span data-ttu-id="b38ce-142">ときに、 **DataConnection**が取り消される場合、すべて**TypedDataRow**によって構築されたクエリを使用して、データベースから取得される、 **DataConnection**がから取り消されます作業メモリ。</span><span class="sxs-lookup"><span data-stu-id="b38ce-142">When a **DataConnection** is retracted, all **TypedDataRow**s retrieved from the database through the query constructed by the **DataConnection** are retracted from working memory.</span></span> <span data-ttu-id="b38ce-143">**DataConnection**も取り消されます、つまり、これ以上ありません**TypedDataRow**s を通じて取得は、 **DataConnection** (つまり、までの使用、 **DataConnection**他の述語またはアクションで)。</span><span class="sxs-lookup"><span data-stu-id="b38ce-143">The **DataConnection** itself is also retracted, meaning that no more **TypedDataRow**s will be retrieved through the **DataConnection** (that is, through use of the **DataConnection** in other predicates or actions).</span></span>  
  
 <span data-ttu-id="b38ce-144">使用する場合、 **DataConnection**、個々 の操作を取り消し、 **TypedDataRow**エンジンは、不整合な状態にします。</span><span class="sxs-lookup"><span data-stu-id="b38ce-144">When using a **DataConnection**, any retract operation on an individual **TypedDataRow** puts the engine into an inconsistent state.</span></span> <span data-ttu-id="b38ce-145">そのため、操作が個別に許可されていません**TypedDataRow**に関連付けられている、 **DataConnection**します。</span><span class="sxs-lookup"><span data-stu-id="b38ce-145">Therefore, operations are not allowed on individual **TypedDataRow**s associated with a **DataConnection**.</span></span> <span data-ttu-id="b38ce-146">テーブルをドラッグする場合 (を使用して、 **DataConnection**パラメーター) に、 **Retract**関数、したが取り消されます、 **DataConnection**します。</span><span class="sxs-lookup"><span data-stu-id="b38ce-146">If you drag the table (using the **DataConnection** parameter) into the **Retract** function, you will be retracting the **DataConnection**.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="b38ce-147">参照</span><span class="sxs-lookup"><span data-stu-id="b38ce-147">See Also</span></span>  
 [<span data-ttu-id="b38ce-148">エンジン制御関数</span><span class="sxs-lookup"><span data-stu-id="b38ce-148">Engine Control Functions</span></span>](../core/engine-control-functions.md)