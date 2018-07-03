---
title: ノードのすべてのグループ |Microsoft Docs
ms.custom: ''
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: ''
ms.suite: ''
ms.tgt_pltfrm: ''
ms.topic: article
ms.assetid: 0e28d98c-746a-44d8-bed2-ba539b8432aa
caps.latest.revision: 9
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: 084b12f16e72507a7d5568bdee022925eca52c0e
ms.sourcegitcommit: 266308ec5c6a9d8d80ff298ee6051b4843c5d626
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 06/27/2018
ms.locfileid: "36989235"
---
# <a name="all-group-nodes"></a><span data-ttu-id="1415a-102">[すべてのグループ] ノード</span><span class="sxs-lookup"><span data-stu-id="1415a-102">All Group Nodes</span></span>
<span data-ttu-id="1415a-103">BizTalk エディターでは、挿入できる、**すべてのグループ**を任意の順序で、0 個または 1 時間に表示される他のノードを含むノードです。</span><span class="sxs-lookup"><span data-stu-id="1415a-103">In BizTalk Editor, you can insert an **All Group** node to contain other nodes that will appear zero or one time, in any order.</span></span> <span data-ttu-id="1415a-104">XML スキーマ定義 (XSD) 言語で、**すべてグループ**よりも使用上の制限が**シーケンス**と**選択肢**グループで、内のいくつかの状況に変換します作成することをするは、BizTalk エディター、**すべてのグループ**ノード。</span><span class="sxs-lookup"><span data-stu-id="1415a-104">In XML Schema definition (XSD) language, the **All group** has more usage limitations than **Sequence** and **Choice** groups, which translates to few situations within BizTalk Editor where you will be able to create an **All Group** node.</span></span>  

 <span data-ttu-id="1415a-105">使用する、**すべてのグループ**ノード BizTalk エディターで、いくつか追加の手順に従う必要があります: を作成する最も簡単な方法、**すべてのグループ**ノードがの値を変更するには、 **Group Order Type**親のプロパティ**レコード**ノード**すべて**します。</span><span class="sxs-lookup"><span data-stu-id="1415a-105">To use an **All Group** node in BizTalk Editor, you need to follow some extra steps: The easiest way to create an **All Group** node is to change the value of the **Group Order Type** property of the parent **Record** node to **All**.</span></span> <span data-ttu-id="1415a-106">これにより、すべての下位ノードの**レコード**内に含まれるノード、**すべてのグループ**ノード。</span><span class="sxs-lookup"><span data-stu-id="1415a-106">This ensures that all of the subordinate nodes of the **Record** node are contained within the **All Group** node.</span></span>  <span data-ttu-id="1415a-107">参照してください**Group Order Type** [!INCLUDE[ui-guidance-developers-reference](../includes/ui-guidance-developers-reference.md)]します。</span><span class="sxs-lookup"><span data-stu-id="1415a-107">See **Group Order Type** [!INCLUDE[ui-guidance-developers-reference](../includes/ui-guidance-developers-reference.md)].</span></span>

 <span data-ttu-id="1415a-108">使用する別の方法、**すべてのグループ**BizTalk エディターでノードが新しい挿入で始まる**レコード**ノード。</span><span class="sxs-lookup"><span data-stu-id="1415a-108">Another way to use an **All Group** node in BizTalk Editor begins with inserting a new **Record** node.</span></span> <span data-ttu-id="1415a-109">新しく挿入した後に**レコード**ノードで、変更、**コンテンツの種類**プロパティを**ComplexContent**します。</span><span class="sxs-lookup"><span data-stu-id="1415a-109">After inserting the new **Record** node, change its **Content Type** property to **ComplexContent**.</span></span> <span data-ttu-id="1415a-110">挿入することができ、**すべてのグループ**ノードの子として、**レコード**ノード。</span><span class="sxs-lookup"><span data-stu-id="1415a-110">Then you can insert an **All Group** node as a child of the **Record** node.</span></span> <span data-ttu-id="1415a-111">これは、必要なため、**すべてのグループ**継承が関係する場合にのみ挿入できます。</span><span class="sxs-lookup"><span data-stu-id="1415a-111">This is required because the **All Group** can only be inserted when inheritance is involved.</span></span> <span data-ttu-id="1415a-112">指定することで、格納している**レコード**ノードは、複雑なコンテンツを含む、データ型に基づいてそのデータ型になります**xs:anyType**、拡張機能によって派生します。</span><span class="sxs-lookup"><span data-stu-id="1415a-112">By specifying that the containing **Record** node contains complex content, its data type becomes based on the data type **xs:anyType**, derived by extension.</span></span>  

> [!NOTE]
>  <span data-ttu-id="1415a-113">BizTalk エディターで、**すべてのグループ**ノードが文字列で表される\<すべて > スキーマ ツリー ビューで。</span><span class="sxs-lookup"><span data-stu-id="1415a-113">In BizTalk Editor, the **All Group** node is represented with the string \<All> in the schema tree view.</span></span> <span data-ttu-id="1415a-114">参照を設定した場合、**すべてのグループ**ノードなど、x として表されます\<グループ: x > スキーマ ツリー ビューで。</span><span class="sxs-lookup"><span data-stu-id="1415a-114">If you set a reference to an **All Group** node, such as to x, it is represented as \<Group:x> in the schema tree view.</span></span>  

## <a name="xsd-representation"></a><span data-ttu-id="1415a-115">XSD 表記</span><span class="sxs-lookup"><span data-stu-id="1415a-115">XSD representation</span></span>  
 <span data-ttu-id="1415a-116">**すべてのグループ**にノードを挿入できる、**レコード**のみ場合はその属性なしの子ノードが、ノード**レコード**ノード。</span><span class="sxs-lookup"><span data-stu-id="1415a-116">An **All Group** node can be inserted into a **Record** node, but only if it is the only non-attribute child node of that **Record** node.</span></span> <span data-ttu-id="1415a-117">次の例を示していますの手順では、新しい**すべてのグループ**と XML スキーマ定義 (XSD) 言語で表されるノード、**すべて**要素を BizTalk エディターでの手順としては、(という名前のノードで実行されます明確にする id)。</span><span class="sxs-lookup"><span data-stu-id="1415a-117">The following example shows, in steps, how a new **All Group** node is represented in the XML Schema definition (XSD) language as an **all** element as the steps in BizTalk Editor are performed (with nodes named to clarify their identity).</span></span>  

```  
<xs:element name="NewRecord">  
    <xs:complexType />   
</xs:element>  
```  

 <span data-ttu-id="1415a-118">前の XSD フラグメントで示すように、新しいレコードを追加した後、**コンテンツの種類**にプロパティが変更された**ComplexContent**、次の XSD の変更の結果として得られる。</span><span class="sxs-lookup"><span data-stu-id="1415a-118">After adding a new record as shown in the preceding XSD fragment, its **Content Type** property is changed to **ComplexContent**, resulting in the following XSD modifications.</span></span>  

```  
<xs:element name="NewRecord">  
    <xs:complexType>  
        <xs:complexContent mixed="false">  
             <xs:extension base="xs:anyType" />  
        </xs:complexContent>  
    </xs:complexType>  
</xs:element>  
```  

 <span data-ttu-id="1415a-119">これで、**すべてのグループ**ノードは、次の XSD フラグメントで示すように、新しいレコードの子として挿入できます。</span><span class="sxs-lookup"><span data-stu-id="1415a-119">Now the **All Group** node can be inserted as a child of the new record, as shown in the following XSD fragment.</span></span>  

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

 <span data-ttu-id="1415a-120">最後に、新しい子として適切なノードを挿入できます**すべてのグループ**ノード。</span><span class="sxs-lookup"><span data-stu-id="1415a-120">Finally, you can insert appropriate nodes as children of the new **All Group** node.</span></span> <span data-ttu-id="1415a-121">次の例は、**レコード**ノードと**フィールド要素**ノードの新しい子ノードとして挿入**すべてのグループ**ノード。</span><span class="sxs-lookup"><span data-stu-id="1415a-121">The following example shows a **Record** node and a **Field Element** node inserted as child nodes of the new **All Group** node.</span></span>  

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

## <a name="see-also"></a><span data-ttu-id="1415a-122">参照</span><span class="sxs-lookup"><span data-stu-id="1415a-122">See Also</span></span>  
- [<span data-ttu-id="1415a-123">スキーマの BizTalk 表記</span><span class="sxs-lookup"><span data-stu-id="1415a-123">BizTalk Representation of Schemas</span></span>](../core/biztalk-representation-of-schemas.md)   
- [<span data-ttu-id="1415a-124">ノードのプロパティ</span><span class="sxs-lookup"><span data-stu-id="1415a-124">Node Properties</span></span>](../core/node-properties.md)   
- <span data-ttu-id="1415a-125">**シーケンス グループ ノードのプロパティ** [!INCLUDE[ui-guidance-developers-reference](../includes/ui-guidance-developers-reference.md)]</span><span class="sxs-lookup"><span data-stu-id="1415a-125">**Sequence Group Node Properties** [!INCLUDE[ui-guidance-developers-reference](../includes/ui-guidance-developers-reference.md)]</span></span> 
- [<span data-ttu-id="1415a-126">ノードのプロパティを設定する方法</span><span class="sxs-lookup"><span data-stu-id="1415a-126">How to Set Node Properties</span></span>](../core/how-to-set-node-properties.md)
