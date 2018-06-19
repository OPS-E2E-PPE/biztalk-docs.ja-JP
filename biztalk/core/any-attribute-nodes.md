---
title: いずれかの属性ノード |Microsoft ドキュメント
ms.custom: ''
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: ''
ms.suite: ''
ms.tgt_pltfrm: ''
ms.topic: article
ms.assetid: fa2d25bc-3a8f-4fd9-acad-341b8e80c737
caps.latest.revision: 6
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: 82490a114149e3d4f71e3598900be5599c8a36e2
ms.sourcegitcommit: 5abd0ed3f9e4858ffaaec5481bfa8878595e95f7
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 11/28/2017
ms.locfileid: "25964648"
---
# <a name="any-attribute-nodes"></a><span data-ttu-id="6a6eb-102">任意の属性ノード</span><span class="sxs-lookup"><span data-stu-id="6a6eb-102">Any Attribute Nodes</span></span>
<span data-ttu-id="6a6eb-103">BizTalk エディターで行うこともできます、**すべての属性**ノードを対象の 0 個以上の不明な属性が表示されるインスタンス メッセージ内の (既知の) 要素を示します。</span><span class="sxs-lookup"><span data-stu-id="6a6eb-103">In BizTalk Editor, you can use an **Any Attribute** node to indicate a (known) element within an instance message for which zero or more unknown attributes may appear.</span></span> <span data-ttu-id="6a6eb-104">特定の要素がインスタンス メッセージ内の特定の場所に出現することはあらかじめわかっているが、そこにどのような属性が入るかが不確定の場合に使用できます。</span><span class="sxs-lookup"><span data-stu-id="6a6eb-104">This accommodates situations in which you know that a particular element will be present at a particular location within an instance message, but you are not sure exactly what attributes that element might include.</span></span> <span data-ttu-id="6a6eb-105">配置した場合、**すべての属性**内のノード、**レコード**ノードは関連する要素に関連付けられている、BizTalk で処理する、その要素すべて関連付けられている属性がされている唯一の要件構文的に解決 (attributeName ="attributeValue") です。</span><span class="sxs-lookup"><span data-stu-id="6a6eb-105">If you place an **Any Attribute** node within the **Record** node associated with the relevant element, BizTalk can process that element, with the only requirement being that any associated attributes are syntactically correct (attributeName="attributeValue").</span></span>  
  
> [!NOTE]
>  <span data-ttu-id="6a6eb-106">BizTalk エディターで、**すべての属性**ノードは、文字列で表される\<AnyAttribute\>スキーマ ツリー ビューでします。</span><span class="sxs-lookup"><span data-stu-id="6a6eb-106">In BizTalk Editor, the **Any Attribute** node is represented with the string \<AnyAttribute\> in the schema tree view.</span></span>  
  
> [!NOTE]
>  <span data-ttu-id="6a6eb-107">整形式 XML としてメッセージの未知の部分を検証を使用して内容を制御できます、 **Process Contents**プロパティです。</span><span class="sxs-lookup"><span data-stu-id="6a6eb-107">You can control the degree to which the unknown portion of the message is validated as well-formed XML by using the **Process Contents** property.</span></span> <span data-ttu-id="6a6eb-108">多くの場合を設定する必要があります、 **Process Contents**プロパティを**Skip**の場所にあるインスタンス メッセージの内容を**すべての属性**に処理するノード.</span><span class="sxs-lookup"><span data-stu-id="6a6eb-108">In many cases you may need to set the **Process Contents** property to **Skip** for the contents of an instance message at the location of the **Any Attribute** node to be processed.</span></span> <span data-ttu-id="6a6eb-109">既定値を保持**Strict**の**Process Contents**プロパティは、インスタンス メッセージの検証の成功をできなくなります。</span><span class="sxs-lookup"><span data-stu-id="6a6eb-109">Retaining the default value of **Strict** for the **Process Contents** property will prevent instance message validation from passing.</span></span>  
>
> <span data-ttu-id="6a6eb-110">このプロパティの詳細について[!INCLUDE[ui-guidance-developers-reference](../includes/ui-guidance-developers-reference.md)]です。</span><span class="sxs-lookup"><span data-stu-id="6a6eb-110">More details on this property [!INCLUDE[ui-guidance-developers-reference](../includes/ui-guidance-developers-reference.md)].</span></span>
  
## <a name="xsd-representation"></a><span data-ttu-id="6a6eb-111">XSD 表記</span><span class="sxs-lookup"><span data-stu-id="6a6eb-111">XSD representation</span></span>  
 <span data-ttu-id="6a6eb-112">ときに、**すべての属性**ノードに追加された、**レコード**ノードまたは、**属性グループ**、1 つの XML タグにノードが追加、対応する XML スキーマ定義 (XSD) 言語スキーマの表記。</span><span class="sxs-lookup"><span data-stu-id="6a6eb-112">When an **Any Attribute** node is added to a **Record** node or to an **Attribute Group** node, a single XML tag is added to the corresponding XML Schema definition (XSD) language representation of the schema.</span></span> <span data-ttu-id="6a6eb-113">次の例では、新しい**すべての属性**、XSD 表現が示すように、ノードで太字を既存に追加された**レコード**ノードが格納されている、**フィールド要素**ノード。</span><span class="sxs-lookup"><span data-stu-id="6a6eb-113">In the following example, a new **Any Attribute** node, whose XSD representation is shown in bold, has been added to an existing **Record** node that already contains a **Field Element** node.</span></span>  
  
```  
<xs:element name="ExistingRecord">  
    <xs:complexType>  
        <xs:sequence>  
            <xs:element name="ExistingFieldElement" type="xs:string" />  
        </xs:sequence>  
        <xs:anyAttribute />  
    </xs:complexType>  
</xs:element  
```  
  
 <span data-ttu-id="6a6eb-114">前の例では、新しいの XSD 表記で**すべての属性**ノードを追加、 **anyAttribute**を含むの末尾に要素 (**レコード**ノード) **要素**要素、外部、**シーケンス**要素と内、 **complexType**要素。</span><span class="sxs-lookup"><span data-stu-id="6a6eb-114">In the preceding example, the XSD representation of the new **Any Attribute** node adds an **anyAttribute** element to the end of the containing (**Record** node) **element** element, outside the **sequence** element and within the **complexType** element.</span></span> <span data-ttu-id="6a6eb-115">ここではすべて**属性**以外でこれらの要素、**属性グループ**ノード、それを含んでいるに追加されます**要素**要素。</span><span class="sxs-lookup"><span data-stu-id="6a6eb-115">This is where all **attribute** elements, other than those with an **Attribute Group** node, are added to their containing **element** elements.</span></span>  
  
 <span data-ttu-id="6a6eb-116">ここでは、およびあると仮定して、 **Process Contents**のプロパティ、**すべての属性**に設定されているノード**Skip**内で、インスタンス メッセージは、このスキーマ フラグメントで、によって左右されます**ExistingRecord**要素が必要とし、適切な形式の XML 構文に関する限り、任意の属性を含めることができます、します。</span><span class="sxs-lookup"><span data-stu-id="6a6eb-116">Now, and assuming that the **Process Contents** property of the **Any Attribute** node is set to **Skip**, within an instance message governed by this schema fragment, an **ExistingRecord** element is expected, and it can contain any attributes so long as they are well-formed with respect to XML syntax.</span></span> <span data-ttu-id="6a6eb-117">(この例では XSD に準拠してにも必要があります、 **ExistingFieldElement**要素もします)。</span><span class="sxs-lookup"><span data-stu-id="6a6eb-117">(To conform to the XSD fragment in this example, it must also contain the **ExistingFieldElement** element as well.)</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="6a6eb-118">参照</span><span class="sxs-lookup"><span data-stu-id="6a6eb-118">See Also</span></span>  
 <span data-ttu-id="6a6eb-119">[スキーマの BizTalk 表記](../core/biztalk-representation-of-schemas.md) </span><span class="sxs-lookup"><span data-stu-id="6a6eb-119">[BizTalk Representation of Schemas](../core/biztalk-representation-of-schemas.md) </span></span>  
 <span data-ttu-id="6a6eb-120">[ノードのプロパティ](../core/node-properties.md) </span><span class="sxs-lookup"><span data-stu-id="6a6eb-120">[Node Properties](../core/node-properties.md) </span></span>  
 <span data-ttu-id="6a6eb-121">[ノードのプロパティを設定する方法](../core/how-to-set-node-properties.md) </span><span class="sxs-lookup"><span data-stu-id="6a6eb-121">[How to Set Node Properties](../core/how-to-set-node-properties.md) </span></span>  
 <span data-ttu-id="6a6eb-122">[[すべての要素] ノード](../core/any-element-nodes.md)</span><span class="sxs-lookup"><span data-stu-id="6a6eb-122">[Any Element Nodes](../core/any-element-nodes.md)</span></span>