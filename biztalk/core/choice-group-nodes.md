---
title: ノードのグループの選択 |Microsoft Docs
ms.custom: ''
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: ''
ms.suite: ''
ms.tgt_pltfrm: ''
ms.topic: article
ms.assetid: 466b525d-4d8c-4b8e-830d-eee27845c0dc
caps.latest.revision: 6
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: c61dc6e070e6dd4832cdba999c44b74d9e80e05f
ms.sourcegitcommit: 381e83d43796a345488d54b3f7413e11d56ad7be
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 05/07/2019
ms.locfileid: "65357335"
---
# <a name="choice-group-nodes"></a><span data-ttu-id="02d80-102">ノードのグループの選択</span><span class="sxs-lookup"><span data-stu-id="02d80-102">Choice Group Nodes</span></span>
<span data-ttu-id="02d80-103">BizTalk エディターでは、挿入できる、**グループの選択**を他のノード (またはノードのサブツリー全体) を含むノード インスタンス メッセージにうちの 1 つだけ表示されることができます。</span><span class="sxs-lookup"><span data-stu-id="02d80-103">In BizTalk Editor, you can insert a **Choice Group** node to contain other nodes (or entire subtrees of nodes), only one of which can appear in an instance message.</span></span> <span data-ttu-id="02d80-104">指定されたインスタンス メッセージでは、有効な場合、必要があります存在の選択肢の 1 つだけです。</span><span class="sxs-lookup"><span data-stu-id="02d80-104">A given instance message, if valid, will have only one of the choices present.</span></span> <span data-ttu-id="02d80-105">含まれているノードは、XML 要素に対応するノードである必要がありますが、XML 属性に対応するノードをすることはできません。</span><span class="sxs-lookup"><span data-stu-id="02d80-105">The contained nodes must be nodes that correspond to XML elements, but cannot be nodes that correspond to XML attributes.</span></span>  

> [!NOTE]
>  <span data-ttu-id="02d80-106">BizTalk エディターで、**グループの選択**ノードが文字列で表される\<選択肢\>スキーマ ツリー ビューで。</span><span class="sxs-lookup"><span data-stu-id="02d80-106">In BizTalk Editor, the **Choice Group** node is represented with the string \<Choice\> in the schema tree view.</span></span> <span data-ttu-id="02d80-107">参照を設定した場合、**グループの選択**x などのノードとして表されます\<グループ: x\>スキーマ ツリー ビューで。</span><span class="sxs-lookup"><span data-stu-id="02d80-107">If you set a reference to a **Choice Group** node, such as x, it is represented as \<Group:x\> in the schema tree view.</span></span>  

## <a name="xsd-representation"></a><span data-ttu-id="02d80-108">XSD 表記</span><span class="sxs-lookup"><span data-stu-id="02d80-108">XSD representation</span></span>  
 <span data-ttu-id="02d80-109">ときに、**グループの選択**ノードが挿入、**レコード**ノード内の他の子ノードの最後に挿入されます、**シーケンス**、**選択肢**、または**すべて**内の要素、**レコード**ノード。</span><span class="sxs-lookup"><span data-stu-id="02d80-109">When a **Choice Group** node is inserted into a **Record** node, it is inserted at the end of any other child nodes within the **sequence**, **choice**, or **all** element in the **Record** node.</span></span> <span data-ttu-id="02d80-110">次の例を示しています、太字で、新しい**グループの選択**と XML スキーマ定義 (XSD) 言語で表されるノードを**選択肢**の末尾に挿入される要素、**シーケンス**内の要素を**レコード**ノード (ノードが自身の id を明確にするという名前) が使用されます。</span><span class="sxs-lookup"><span data-stu-id="02d80-110">The following example shows, in bold type, how a new **Choice Group** node is represented in the XML Schema definition (XSD) language as a **choice** element inserted at the end of the **sequence** element in a **Record** node (with nodes named to clarify their identity).</span></span>  

```  
<xs:element name="ContainingRecord">  
    <xs:complexType>  
        <xs:sequence>  
            <xs:element name="ExistingFieldElement" type="xs:string" />  
        </xs:sequence>  
    </xs:complexType>  
</xs:element>  

```  

 <span data-ttu-id="02d80-111">既定で、**選択肢**の要素を指定、 **minOccurs**属性のオプションがない、発生する必要があることを示すゼロ (0) の値。</span><span class="sxs-lookup"><span data-stu-id="02d80-111">By default, the **choice** element is given a **minOccurs** attribute value of zero (0), indicating that none of the choices need occur.</span></span> <span data-ttu-id="02d80-112">Visual Studio のプロパティ ウィンドウでこの値を変更することができる場合、**グループの選択**スキーマ ツリー ビューでノードを選択します。</span><span class="sxs-lookup"><span data-stu-id="02d80-112">You can change this value in the Visual Studio Properties window when the **Choice Group** node is selected in the schema tree view.</span></span>  

 <span data-ttu-id="02d80-113">次の例は、同じ**選択肢**xsd 要素**要素**要素が 2 つの下位に対応する**レコード**ノード。</span><span class="sxs-lookup"><span data-stu-id="02d80-113">The following example shows the same **choice** element with the XSD **element** elements corresponding to two subordinate **Record** nodes.</span></span>  

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

 <span data-ttu-id="02d80-114">この例では、2 つの兄弟で**レコード**ノードを使用して、インスタンス メッセージは、a レコードで、米国の住所情報または世界中の住所情報を持つレコードがかことについて説明します。</span><span class="sxs-lookup"><span data-stu-id="02d80-114">In this example, two sibling **Record** nodes are used to describe the fact that an instance message will either have a record with United States address information in it, or a record with worldwide address information in it.</span></span> <span data-ttu-id="02d80-115">さらに、 **minOccurs**と**maxOccurs**のプロパティ、**グループの選択**ノード両方に設定されている 1 つ (1) Visual Studio のプロパティ ウィンドウでその結果、 *minOccurs*と*maxOccurs*の属性、**選択肢**XSD 表記で 1 つ (1) に設定されている要素。</span><span class="sxs-lookup"><span data-stu-id="02d80-115">Further, the **minOccurs** and **maxOccurs** properties of the **Choice Group** node have both been set to one (1) in the Visual Studio Properties window, resulting in the *minOccurs* and *maxOccurs* attributes of the **choice** element being set to one (1) in the XSD representation.</span></span>  

## <a name="see-also"></a><span data-ttu-id="02d80-116">参照</span><span class="sxs-lookup"><span data-stu-id="02d80-116">See Also</span></span>  
- [<span data-ttu-id="02d80-117">スキーマの BizTalk 表記</span><span class="sxs-lookup"><span data-stu-id="02d80-117">BizTalk Representation of Schemas</span></span>](../core/biztalk-representation-of-schemas.md)   
- [<span data-ttu-id="02d80-118">ノードのプロパティ</span><span class="sxs-lookup"><span data-stu-id="02d80-118">Node Properties</span></span>](../core/node-properties.md)   
- <span data-ttu-id="02d80-119">**シーケンス グループ ノードのプロパティ** [!INCLUDE[ui-guidance-developers-reference](../includes/ui-guidance-developers-reference.md)]</span><span class="sxs-lookup"><span data-stu-id="02d80-119">**Sequence Group Node Properties** [!INCLUDE[ui-guidance-developers-reference](../includes/ui-guidance-developers-reference.md)]</span></span>     
- [<span data-ttu-id="02d80-120">ノードのプロパティを設定する方法</span><span class="sxs-lookup"><span data-stu-id="02d80-120">How to Set Node Properties</span></span>](../core/how-to-set-node-properties.md)
