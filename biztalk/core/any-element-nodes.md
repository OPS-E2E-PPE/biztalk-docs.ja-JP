---
title: すべての要素ノード |Microsoft Docs
ms.custom: ''
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: ''
ms.suite: ''
ms.tgt_pltfrm: ''
ms.topic: article
ms.assetid: c7e30fcf-31bc-4d48-9bc7-0be90e927127
caps.latest.revision: 7
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: 3d5581ed73c6bb2fdf625a976a33d906bd5d2836
ms.sourcegitcommit: 381e83d43796a345488d54b3f7413e11d56ad7be
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 05/07/2019
ms.locfileid: "65359165"
---
# <a name="any-element-nodes"></a><span data-ttu-id="bb058-102">すべての要素ノード</span><span class="sxs-lookup"><span data-stu-id="bb058-102">Any Element Nodes</span></span>
<span data-ttu-id="bb058-103">使用できる BizTalk エディターで、 **Any 要素**ノードが、不明な要素が表示されるインスタンス メッセージ内の場所を示すことです。</span><span class="sxs-lookup"><span data-stu-id="bb058-103">In BizTalk Editor, you can use an **Any Element** node to indicate a location within an instance message where unknown elements may appear.</span></span> <span data-ttu-id="bb058-104">不確定の場合に、いくつかの要素がインスタンス メッセージ内の特定の場所に表示されるが、要素の名前がわからないことがわかってまたは複雑な方法があります。</span><span class="sxs-lookup"><span data-stu-id="bb058-104">This accommodates situations in which you know that some element might appear at a particular location within an instance message, but you do not know the name of the element, or how complicated it might be.</span></span> <span data-ttu-id="bb058-105">配置した場合、 **Any 要素**ノードのスキーマでは、BizTalk 内で適切な位置には、メッセージのような未知の部分を処理できます。</span><span class="sxs-lookup"><span data-stu-id="bb058-105">If you place an **Any Element** node at the appropriate location within the schema, BizTalk can process such unknown portions of a message.</span></span> <span data-ttu-id="bb058-106">唯一の要件は、対応する XML が整形式であります。</span><span class="sxs-lookup"><span data-stu-id="bb058-106">The only requirement is that the corresponding XML is well-formed.</span></span>  
  
> [!NOTE]
>  <span data-ttu-id="bb058-107">BizTalk エディターで、**すべての要素**ノードが文字列で表される\<任意\>スキーマ ツリー ビューで。</span><span class="sxs-lookup"><span data-stu-id="bb058-107">In BizTalk Editor, the **Any Element** node is represented with the string \<Any\> in the schema tree view.</span></span>  
> 
> [!NOTE]
>  <span data-ttu-id="bb058-108">整形式 XML として、メッセージの未知の部分を検証を使用して程度を制御することができます、 **Process Contents**プロパティ。</span><span class="sxs-lookup"><span data-stu-id="bb058-108">You can control the degree to which the unknown portion of the message is validated as well-formed XML by using the **Process Contents** property.</span></span> <span data-ttu-id="bb058-109">多くの場合は、設定する必要があります、 **Process Contents**プロパティを**スキップ**の位置にあるインスタンス メッセージの内容として、 **Any 要素**処理するノード。</span><span class="sxs-lookup"><span data-stu-id="bb058-109">In many cases you may need to set the **Process Contents** property to **Skip** for the contents of an instance message at the location of the **Any Element** node to be processed.</span></span> <span data-ttu-id="bb058-110">既定値を保持**Strict**の**Process Contents**プロパティがインスタンス メッセージの検証の成功を防ぐためです。</span><span class="sxs-lookup"><span data-stu-id="bb058-110">Retaining the default value of **Strict** for the **Process Contents** property will prevent instance message validation from passing.</span></span>  
> 
> <span data-ttu-id="bb058-111">このプロパティについて詳しく[!INCLUDE[ui-guidance-developers-reference](../includes/ui-guidance-developers-reference.md)]します。</span><span class="sxs-lookup"><span data-stu-id="bb058-111">More details on this property [!INCLUDE[ui-guidance-developers-reference](../includes/ui-guidance-developers-reference.md)].</span></span>
  
## <a name="xsd-representation"></a><span data-ttu-id="bb058-112">XSD 表記</span><span class="sxs-lookup"><span data-stu-id="bb058-112">XSD representation</span></span>  
 <span data-ttu-id="bb058-113">ときに、 **Any 要素**にノードを追加、**レコード**ノード、または別のノードを追加するように、**シーケンス グループ**、 **グループの選択**、または**すべてのグループ**ノード、1 つの XML タグが、対応する XML スキーマ定義 (XSD) 言語表記のスキーマに追加します。</span><span class="sxs-lookup"><span data-stu-id="bb058-113">When an **Any Element** node is added to a **Record** node, or to another node to which it can be added such as a **Sequence Group**, **Choice Group**, or **All Group** node, a single XML tag is added to the corresponding XML Schema definition (XSD) language representation of the schema.</span></span> <span data-ttu-id="bb058-114">次の例では、新しい**Any 要素**を既存の XSD 表記が太字で表示されているノードが追加されました**レコード**既に含まれているノード、**フィールド要素**ノード。</span><span class="sxs-lookup"><span data-stu-id="bb058-114">In the following example, a new **Any Element** node, whose XSD representation is shown in bold type, has been added to an existing **Record** node that already contains a **Field Element** node.</span></span>  
  
```  
<xs:element name="ExistingRecord">  
    <xs:complexType>  
        <xs:sequence>  
             <xs:element name="ExistingFieldElement" type="xs:string" />  
            <xs:any />  
        </xs:sequence>  
    </xs:complexType>  
</xs:element>  
```  
  
 <span data-ttu-id="bb058-115">仮定すると、 **Process Contents**のプロパティ、 **Any 要素**にノードが設定されている**スキップ**内でこのスキーマのフラグメントをによって管理されるインスタンスメッセージ**ExistingRecord**要素が格納する必要があります、 **ExistingFieldElement**任意の複雑さの任意の 1 つの要素の後に、文字列データを含む要素。</span><span class="sxs-lookup"><span data-stu-id="bb058-115">Assuming that the **Process Contents** property of the **Any Element** node is set to **Skip**, within an instance message governed by this schema fragment, an **ExistingRecord** element is expected to contain an **ExistingFieldElement** element containing string data, followed by any single element of arbitrary complexity.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="bb058-116">参照</span><span class="sxs-lookup"><span data-stu-id="bb058-116">See Also</span></span>  
 <span data-ttu-id="bb058-117">[スキーマの BizTalk 表記](../core/biztalk-representation-of-schemas.md) </span><span class="sxs-lookup"><span data-stu-id="bb058-117">[BizTalk Representation of Schemas](../core/biztalk-representation-of-schemas.md) </span></span>  
 <span data-ttu-id="bb058-118">[ノードのプロパティ](../core/node-properties.md) </span><span class="sxs-lookup"><span data-stu-id="bb058-118">[Node Properties](../core/node-properties.md) </span></span>  
 <span data-ttu-id="bb058-119">[ノードのプロパティを設定する方法](../core/how-to-set-node-properties.md) </span><span class="sxs-lookup"><span data-stu-id="bb058-119">[How to Set Node Properties](../core/how-to-set-node-properties.md) </span></span>  
 <span data-ttu-id="bb058-120">[[すべての属性] ノード](../core/any-attribute-nodes.md)</span><span class="sxs-lookup"><span data-stu-id="bb058-120">[Any Attribute Nodes](../core/any-attribute-nodes.md)</span></span>