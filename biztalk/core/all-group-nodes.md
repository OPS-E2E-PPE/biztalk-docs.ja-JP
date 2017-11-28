---
title: "ノードのすべてのグループ |Microsoft ドキュメント"
ms.custom: 
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: 
ms.suite: 
ms.tgt_pltfrm: 
ms.topic: article
ms.assetid: 0e28d98c-746a-44d8-bed2-ba539b8432aa
caps.latest.revision: "9"
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: f51d6420b7d754ffb8706e2bc729a02df00b4338
ms.sourcegitcommit: cb908c540d8f1a692d01dc8f313e16cb4b4e696d
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 09/20/2017
---
# <a name="all-group-nodes"></a><span data-ttu-id="16bd4-102">[すべてのグループ] ノード</span><span class="sxs-lookup"><span data-stu-id="16bd4-102">All Group Nodes</span></span>
<span data-ttu-id="16bd4-103">BizTalk エディターで、挿入できる、**すべてのグループ**を任意の順序で、0 個または 1 つの時間が表示される他のノードを含むノードです。</span><span class="sxs-lookup"><span data-stu-id="16bd4-103">In BizTalk Editor, you can insert an **All Group** node to contain other nodes that will appear zero or one time, in any order.</span></span> <span data-ttu-id="16bd4-104">XML スキーマ定義 (XSD) 言語で、**すべてグループ**よりも使用上の制限を持つ**シーケンス**と**選択肢**グループ内のいくつかの状況に変換します。ここでことができますを作成する BizTalk エディター、**すべてのグループ**ノード。</span><span class="sxs-lookup"><span data-stu-id="16bd4-104">In XML Schema definition (XSD) language, the **All group** has more usage limitations than **Sequence** and **Choice** groups, which translates to few situations within BizTalk Editor where you will be able to create an **All Group** node.</span></span>  
  
 <span data-ttu-id="16bd4-105">使用する、**すべてのグループ**ノード BizTalk エディターで、追加の手順に従う必要があります: を作成する最も簡単な方法、**すべてのグループ**の値を変更するのには、ノード、 **Group Order Type**親のプロパティ**レコード**ノード**すべて**です。</span><span class="sxs-lookup"><span data-stu-id="16bd4-105">To use an **All Group** node in BizTalk Editor, you need to follow some extra steps: The easiest way to create an **All Group** node is to change the value of the **Group Order Type** property of the parent **Record** node to **All**.</span></span> <span data-ttu-id="16bd4-106">これにより、すべての下位ノードの**レコード**ノードに含まれる、**すべてのグループ**ノード。</span><span class="sxs-lookup"><span data-stu-id="16bd4-106">This ensures that all of the subordinate nodes of the **Record** node are contained within the **All Group** node.</span></span>  <span data-ttu-id="16bd4-107">参照してください**Group Order Type** [!INCLUDE[ui-guidance-developers-reference](../includes/ui-guidance-developers-reference.md)]です。</span><span class="sxs-lookup"><span data-stu-id="16bd4-107">See **Group Order Type** [!INCLUDE[ui-guidance-developers-reference](../includes/ui-guidance-developers-reference.md)].</span></span>
  
 <span data-ttu-id="16bd4-108">使用する別の方法、**すべてのグループ**BizTalk エディターでノードが新しい挿入で始まる**レコード**ノード。</span><span class="sxs-lookup"><span data-stu-id="16bd4-108">Another way to use an **All Group** node in BizTalk Editor begins with inserting a new **Record** node.</span></span> <span data-ttu-id="16bd4-109">新しく挿入した後に**レコード**ノード、変更、**コンテンツ タイプ**プロパティを**ComplexContent**です。</span><span class="sxs-lookup"><span data-stu-id="16bd4-109">After inserting the new **Record** node, change its **Content Type** property to **ComplexContent**.</span></span> <span data-ttu-id="16bd4-110">挿入することができ、**すべてのグループ**ノードの子として、**レコード**ノード。</span><span class="sxs-lookup"><span data-stu-id="16bd4-110">Then you can insert an **All Group** node as a child of the **Record** node.</span></span> <span data-ttu-id="16bd4-111">これが必要な**すべてのグループ**継承が関係しているときにのみ挿入できます。</span><span class="sxs-lookup"><span data-stu-id="16bd4-111">This is required because the **All Group** can only be inserted when inheritance is involved.</span></span> <span data-ttu-id="16bd4-112">指定する格納している**レコード**ノードには、複雑なコンテンツが含まれています、そのデータ型は、データ型に基づくなります**xs:anyType**、拡張機能によって派生します。</span><span class="sxs-lookup"><span data-stu-id="16bd4-112">By specifying that the containing **Record** node contains complex content, its data type becomes based on the data type **xs:anyType**, derived by extension.</span></span>  
  
> [!NOTE]
>  <span data-ttu-id="16bd4-113">BizTalk エディターで、**すべてのグループ**ノードは、文字列で表される\<すべて > スキーマ ツリー ビューでします。</span><span class="sxs-lookup"><span data-stu-id="16bd4-113">In BizTalk Editor, the **All Group** node is represented with the string \<All> in the schema tree view.</span></span> <span data-ttu-id="16bd4-114">参照を設定した場合、**すべてのグループ**ノードなど、x、として表されます\<グループ:x > スキーマ ツリー ビューでします。</span><span class="sxs-lookup"><span data-stu-id="16bd4-114">If you set a reference to an **All Group** node, such as to x, it is represented as \<Group:x> in the schema tree view.</span></span>  
  
## <a name="xsd-representation"></a><span data-ttu-id="16bd4-115">XSD 表記</span><span class="sxs-lookup"><span data-stu-id="16bd4-115">XSD representation</span></span>  
 <span data-ttu-id="16bd4-116">**すべてのグループ**にノードを挿入できる、**レコード**のみ場合は、属性なしの子ノードですが、ノード**レコード**ノード。</span><span class="sxs-lookup"><span data-stu-id="16bd4-116">An **All Group** node can be inserted into a **Record** node, but only if it is the only non-attribute child node of that **Record** node.</span></span> <span data-ttu-id="16bd4-117">次の例を示していますの手順で、新しい方法**すべてのグループ**と XML スキーマ定義 (XSD) 言語で表されるノード、**すべて**(という名前のノードの要素として BizTalk エディターでの手順が実行されます明確にする、id)。</span><span class="sxs-lookup"><span data-stu-id="16bd4-117">The following example shows, in steps, how a new **All Group** node is represented in the XML Schema definition (XSD) language as an **all** element as the steps in BizTalk Editor are performed (with nodes named to clarify their identity).</span></span>  
  
```  
<xs:element name="NewRecord">  
    <xs:complexType />   
</xs:element>  
```  
  
 <span data-ttu-id="16bd4-118">前の XSD フラグメントで示すように、新しいレコードを追加した後、**コンテンツ タイプ**にプロパティが変更された**ComplexContent**、その結果、次の XSD の変更にします。</span><span class="sxs-lookup"><span data-stu-id="16bd4-118">After adding a new record as shown in the preceding XSD fragment, its **Content Type** property is changed to **ComplexContent**, resulting in the following XSD modifications.</span></span>  
  
```  
<xs:element name="NewRecord">  
    <xs:complexType>  
        <xs:complexContent mixed="false">  
             <xs:extension base="xs:anyType" />  
        </xs:complexContent>  
    </xs:complexType>  
</xs:element>  
```  
  
 <span data-ttu-id="16bd4-119">これで、**すべてのグループ**ノードは、次の XSD フラグメントで示すように、新しいレコードの子として挿入できます。</span><span class="sxs-lookup"><span data-stu-id="16bd4-119">Now the **All Group** node can be inserted as a child of the new record, as shown in the following XSD fragment.</span></span>  
  
```  
<xs:element name="NewRecord">  
    <xs:complexType>  
        <xs:complexContent mixed="false">  
            <xs:extension base="xs:anyType">  
                <xs:all />   
             </xs:extension>  
          </xs:complexContent>  
     </xs:complexType>  
</xs:element>  
```  
  
 <span data-ttu-id="16bd4-120">最後に、新しい子として適切なノードを挿入できる**すべてのグループ**ノード。</span><span class="sxs-lookup"><span data-stu-id="16bd4-120">Finally, you can insert appropriate nodes as children of the new **All Group** node.</span></span> <span data-ttu-id="16bd4-121">次の例は、**レコード**ノードおよび**フィールド要素**の新しい子ノードとして挿入ノード**すべてのグループ**ノード。</span><span class="sxs-lookup"><span data-stu-id="16bd4-121">The following example shows a **Record** node and a **Field Element** node inserted as child nodes of the new **All Group** node.</span></span>  
  
```  
<xs:element name="NewRecord">  
    <xs:complexType>  
        <xs:complexContent mixed="false">  
            <xs:extension base="xs:anyType">  
                <xs:all>  
                    <xs:element name="RecordChildOfAllGroup">  
                        <xs:complexType />  
                    </xs:element>  
                    <xs:element name="FieldElementChildOfAllGroup" type="xs:string" />  
                </xs:all>  
            </xs:extension>  
        </xs:complexContent>  
    </xs:complexType>  
</xs:element>  
```  
  
## <a name="see-also"></a><span data-ttu-id="16bd4-122">参照</span><span class="sxs-lookup"><span data-stu-id="16bd4-122">See Also</span></span>  
-  [<span data-ttu-id="16bd4-123">スキーマの BizTalk 表記</span><span class="sxs-lookup"><span data-stu-id="16bd4-123">BizTalk Representation of Schemas</span></span>](../core/biztalk-representation-of-schemas.md)   
-  [<span data-ttu-id="16bd4-124">ノードのプロパティ</span><span class="sxs-lookup"><span data-stu-id="16bd4-124">Node Properties</span></span>](../core/node-properties.md)   
-  <span data-ttu-id="16bd4-125">**シーケンス グループ ノードのプロパティ**[!INCLUDE[ui-guidance-developers-reference](../includes/ui-guidance-developers-reference.md)]</span><span class="sxs-lookup"><span data-stu-id="16bd4-125">**Sequence Group Node Properties** [!INCLUDE[ui-guidance-developers-reference](../includes/ui-guidance-developers-reference.md)]</span></span> 
-  [<span data-ttu-id="16bd4-126">ノードのプロパティを設定する方法</span><span class="sxs-lookup"><span data-stu-id="16bd4-126">How to Set Node Properties</span></span>](../core/how-to-set-node-properties.md)