---
title: "グループの選択ノード |Microsoft ドキュメント"
ms.custom: 
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: 
ms.suite: 
ms.tgt_pltfrm: 
ms.topic: article
ms.assetid: 466b525d-4d8c-4b8e-830d-eee27845c0dc
caps.latest.revision: "6"
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: ec6edafcb01e2c0ce155585e4fbe2f9d61b1cf1c
ms.sourcegitcommit: cb908c540d8f1a692d01dc8f313e16cb4b4e696d
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 09/20/2017
---
# <a name="choice-group-nodes"></a><span data-ttu-id="2f6e2-102">選択肢グループ ノード</span><span class="sxs-lookup"><span data-stu-id="2f6e2-102">Choice Group Nodes</span></span>
<span data-ttu-id="2f6e2-103">挿入できる BizTalk エディターで、**選択肢グループ**を他のノード (またはノードのサブツリー全体) を含むノード インスタンス メッセージにうちの 1 つだけ表示されることができます。</span><span class="sxs-lookup"><span data-stu-id="2f6e2-103">In BizTalk Editor, you can insert a **Choice Group** node to contain other nodes (or entire subtrees of nodes), only one of which can appear in an instance message.</span></span> <span data-ttu-id="2f6e2-104">この場合、インスタンス メッセージには、選択されたいずれかのノードだけが含まれます。</span><span class="sxs-lookup"><span data-stu-id="2f6e2-104">A given instance message, if valid, will have only one of the choices present.</span></span> <span data-ttu-id="2f6e2-105">取り込むノードは、XML 要素に対応するノードであることが必要です。ただし、XML 属性に対応するノードではありません。</span><span class="sxs-lookup"><span data-stu-id="2f6e2-105">The contained nodes must be nodes that correspond to XML elements, but cannot be nodes that correspond to XML attributes.</span></span>  
  
> [!NOTE]
>  <span data-ttu-id="2f6e2-106">BizTalk エディターで、**選択肢グループ**ノードは、文字列で表されます\<選択肢 > スキーマ ツリー ビューでします。</span><span class="sxs-lookup"><span data-stu-id="2f6e2-106">In BizTalk Editor, the **Choice Group** node is represented with the string \<Choice> in the schema tree view.</span></span> <span data-ttu-id="2f6e2-107">参照を設定した場合、**選択肢グループ**x などのノードとして表されます\<グループ:x > スキーマ ツリー ビューでします。</span><span class="sxs-lookup"><span data-stu-id="2f6e2-107">If you set a reference to a **Choice Group** node, such as x, it is represented as \<Group:x> in the schema tree view.</span></span>  
  
## <a name="xsd-representation"></a><span data-ttu-id="2f6e2-108">XSD 表記</span><span class="sxs-lookup"><span data-stu-id="2f6e2-108">XSD representation</span></span>  
 <span data-ttu-id="2f6e2-109">ときに、**グループの選択**ノードが挿入、**レコード**ノード内の他の子ノードの最後に挿入されます、**シーケンス**、**選択肢**、または**すべて**内の要素、**レコード**ノード。</span><span class="sxs-lookup"><span data-stu-id="2f6e2-109">When a **Choice Group** node is inserted into a **Record** node, it is inserted at the end of any other child nodes within the **sequence**, **choice**, or **all** element in the **Record** node.</span></span> <span data-ttu-id="2f6e2-110">次の例を示しています、太字で新しい方法**選択肢グループ**と XML スキーマ定義 (XSD) 言語で表されるノード、**選択肢**の最後に挿入される要素、**シーケンス**内の要素、**レコード**(ノードが自身の id を明確にするという名前) を持つノード。</span><span class="sxs-lookup"><span data-stu-id="2f6e2-110">The following example shows, in bold type, how a new **Choice Group** node is represented in the XML Schema definition (XSD) language as a **choice** element inserted at the end of the **sequence** element in a **Record** node (with nodes named to clarify their identity).</span></span>  
  
```  
<xs:element name="ContainingRecord">  
    <xs:complexType>  
        <xs:sequence>  
            <xs:element name="ExistingFieldElement" type="xs:string" />  
        </xs:sequence>  
    </xs:complexType>  
</xs:element>  
  
```  
  
 <span data-ttu-id="2f6e2-111">既定では、**選択肢**要素が指定された、 **minOccurs**属性ゼロ (0)、オプションがない、発生する必要があることを示す値を指定します。</span><span class="sxs-lookup"><span data-stu-id="2f6e2-111">By default, the **choice** element is given a **minOccurs** attribute value of zero (0), indicating that none of the choices need occur.</span></span> <span data-ttu-id="2f6e2-112">Visual Studio プロパティ ウィンドウでこの値を変更することができる場合、**グループの選択**スキーマ ツリー ビューでノードを選択します。</span><span class="sxs-lookup"><span data-stu-id="2f6e2-112">You can change this value in the Visual Studio Properties window when the **Choice Group** node is selected in the schema tree view.</span></span>  
  
 <span data-ttu-id="2f6e2-113">次の例は、同じ**選択肢**XSD を持つ要素**要素**2 つの下位に対応する要素**レコード**ノード。</span><span class="sxs-lookup"><span data-stu-id="2f6e2-113">The following example shows the same **choice** element with the XSD **element** elements corresponding to two subordinate **Record** nodes.</span></span>  
  
```  
<xs:element name="ContainingRecord">  
    <xs:complexType>  
        <xs:sequence>  
            <xs:element name="ExistingFieldElement" type="xs:string" />  
            <xs:choice minOccurs="1" maxOccurs="1">  
                <xs:element name="usAddress">  
                    <xs:complexType>  
                        <xs:sequence>  
                        </xs:sequence>  
                    </xs:complexType>  
                </xs:element>  
                <xs:element name="foreignAddress">  
                    <xs:complexType>  
                        <xs:sequence>  
                        </xs:sequence>  
                    </xs:complexType>  
                </xs:element>  
            </xs:choice>  
        </xs:sequence>  
    </xs:complexType>  
</xs:element>  
```  
  
 <span data-ttu-id="2f6e2-114">この例では、2 つの兄弟で**レコード**ノードは、インスタンス メッセージは、米国の住所情報を持つレコード、またはその国際的な住所情報を持つレコードにあるか、ファクトの記述に使用します。</span><span class="sxs-lookup"><span data-stu-id="2f6e2-114">In this example, two sibling **Record** nodes are used to describe the fact that an instance message will either have a record with United States address information in it, or a record with worldwide address information in it.</span></span> <span data-ttu-id="2f6e2-115">さらに、 **minOccurs**と**maxOccurs**のプロパティ、**選択肢グループ**ノード両方設定されている (1) 1 つに、Visual Studio プロパティ ウィンドウで、その結果、 *minOccurs*と*maxOccurs*の属性、**選択肢**XSD 表記で 1 つ (1) に設定されている要素です。</span><span class="sxs-lookup"><span data-stu-id="2f6e2-115">Further, the **minOccurs** and **maxOccurs** properties of the **Choice Group** node have both been set to one (1) in the Visual Studio Properties window, resulting in the *minOccurs* and *maxOccurs* attributes of the **choice** element being set to one (1) in the XSD representation.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="2f6e2-116">参照</span><span class="sxs-lookup"><span data-stu-id="2f6e2-116">See Also</span></span>  
-  [<span data-ttu-id="2f6e2-117">スキーマの BizTalk 表記</span><span class="sxs-lookup"><span data-stu-id="2f6e2-117">BizTalk Representation of Schemas</span></span>](../core/biztalk-representation-of-schemas.md)   
-  [<span data-ttu-id="2f6e2-118">ノードのプロパティ</span><span class="sxs-lookup"><span data-stu-id="2f6e2-118">Node Properties</span></span>](../core/node-properties.md)   
-  <span data-ttu-id="2f6e2-119">**シーケンス グループ ノードのプロパティ**[!INCLUDE[ui-guidance-developers-reference](../includes/ui-guidance-developers-reference.md)]</span><span class="sxs-lookup"><span data-stu-id="2f6e2-119">**Sequence Group Node Properties** [!INCLUDE[ui-guidance-developers-reference](../includes/ui-guidance-developers-reference.md)]</span></span>     
-  [<span data-ttu-id="2f6e2-120">ノードのプロパティを設定する方法</span><span class="sxs-lookup"><span data-stu-id="2f6e2-120">How to Set Node Properties</span></span>](../core/how-to-set-node-properties.md)