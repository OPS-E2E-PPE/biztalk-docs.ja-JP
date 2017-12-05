---
title: "すべての要素ノード |Microsoft ドキュメント"
ms.custom: 
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: 
ms.suite: 
ms.tgt_pltfrm: 
ms.topic: article
ms.assetid: c7e30fcf-31bc-4d48-9bc7-0be90e927127
caps.latest.revision: "7"
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: f556a5629fd98d910cbbbd83632ac1a6a1702e74
ms.sourcegitcommit: 5abd0ed3f9e4858ffaaec5481bfa8878595e95f7
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 11/28/2017
---
# <a name="any-element-nodes"></a><span data-ttu-id="71d05-102">すべての要素ノード</span><span class="sxs-lookup"><span data-stu-id="71d05-102">Any Element Nodes</span></span>
<span data-ttu-id="71d05-103">BizTalk エディターで行うこともできます、 **Any 要素**不明な要素が表示されるインスタンス メッセージ内の場所を示すためにノードです。</span><span class="sxs-lookup"><span data-stu-id="71d05-103">In BizTalk Editor, you can use an **Any Element** node to indicate a location within an instance message where unknown elements may appear.</span></span> <span data-ttu-id="71d05-104">これにより、特定の要素がインスタンス メッセージ内の特定の場所に出現することはあらかじめわかっているが、要素の名前や複雑さの程度が不確定な状況にも対応できます。</span><span class="sxs-lookup"><span data-stu-id="71d05-104">This accommodates situations in which you know that some element might appear at a particular location within an instance message, but you do not know the name of the element, or how complicated it might be.</span></span> <span data-ttu-id="71d05-105">配置した場合、 **Any 要素**ノードのスキーマでは、BizTalk 内で適切な位置には、このようなメッセージの不明な部分を処理できます。</span><span class="sxs-lookup"><span data-stu-id="71d05-105">If you place an **Any Element** node at the appropriate location within the schema, BizTalk can process such unknown portions of a message.</span></span> <span data-ttu-id="71d05-106">唯一の要件は、対応する XML が整形式であることです。</span><span class="sxs-lookup"><span data-stu-id="71d05-106">The only requirement is that the corresponding XML is well-formed.</span></span>  
  
> [!NOTE]
>  <span data-ttu-id="71d05-107">BizTalk エディターで、 **Any 要素**ノードは、文字列で表されます\<任意\>スキーマ ツリー ビューでします。</span><span class="sxs-lookup"><span data-stu-id="71d05-107">In BizTalk Editor, the **Any Element** node is represented with the string \<Any\> in the schema tree view.</span></span>  
  
> [!NOTE]
>  <span data-ttu-id="71d05-108">整形式 XML としてメッセージの未知の部分を検証を使用して内容を制御できます、 **Process Contents**プロパティです。</span><span class="sxs-lookup"><span data-stu-id="71d05-108">You can control the degree to which the unknown portion of the message is validated as well-formed XML by using the **Process Contents** property.</span></span> <span data-ttu-id="71d05-109">多くの場合を設定する必要があります、 **Process Contents**プロパティを**Skip**の場所にあるインスタンス メッセージの内容を**Any 要素**に処理するノードです。</span><span class="sxs-lookup"><span data-stu-id="71d05-109">In many cases you may need to set the **Process Contents** property to **Skip** for the contents of an instance message at the location of the **Any Element** node to be processed.</span></span> <span data-ttu-id="71d05-110">既定値を保持**Strict**の**Process Contents**プロパティは、インスタンス メッセージの検証の成功をできなくなります。</span><span class="sxs-lookup"><span data-stu-id="71d05-110">Retaining the default value of **Strict** for the **Process Contents** property will prevent instance message validation from passing.</span></span>  
> 
> <span data-ttu-id="71d05-111">このプロパティの詳細について[!INCLUDE[ui-guidance-developers-reference](../includes/ui-guidance-developers-reference.md)]です。</span><span class="sxs-lookup"><span data-stu-id="71d05-111">More details on this property [!INCLUDE[ui-guidance-developers-reference](../includes/ui-guidance-developers-reference.md)].</span></span>
  
## <a name="xsd-representation"></a><span data-ttu-id="71d05-112">XSD 表記</span><span class="sxs-lookup"><span data-stu-id="71d05-112">XSD representation</span></span>  
 <span data-ttu-id="71d05-113">ときに、 **Any 要素**ノードに追加された、**レコード**ノード、または別のノードを追加するように、**シーケンス グループ**、**選択肢グループ**、または**すべてのグループ**ノード、1 つの XML タグが、対応する XML スキーマ定義 (XSD) 言語表記のスキーマに追加します。</span><span class="sxs-lookup"><span data-stu-id="71d05-113">When an **Any Element** node is added to a **Record** node, or to another node to which it can be added such as a **Sequence Group**, **Choice Group**, or **All Group** node, a single XML tag is added to the corresponding XML Schema definition (XSD) language representation of the schema.</span></span> <span data-ttu-id="71d05-114">次の例では、新しい**Any 要素**を既存の XSD 表記が太字で示すように、ノードが追加されました**レコード**ノードが格納されている、**フィールド要素**ノード。</span><span class="sxs-lookup"><span data-stu-id="71d05-114">In the following example, a new **Any Element** node, whose XSD representation is shown in bold type, has been added to an existing **Record** node that already contains a **Field Element** node.</span></span>  
  
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
  
 <span data-ttu-id="71d05-115">想定されるので、 **Process Contents**のプロパティ、**すべての要素**に設定されているノード**Skip**内でこのスキーマ フラグメントで、によって管理されるインスタンスメッセージ**ExistingRecord**要素が通常含まれる、 **ExistingFieldElement**任意の複雑性の任意の 1 つの要素の後に文字列データを含む要素です。</span><span class="sxs-lookup"><span data-stu-id="71d05-115">Assuming that the **Process Contents** property of the **Any Element** node is set to **Skip**, within an instance message governed by this schema fragment, an **ExistingRecord** element is expected to contain an **ExistingFieldElement** element containing string data, followed by any single element of arbitrary complexity.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="71d05-116">参照</span><span class="sxs-lookup"><span data-stu-id="71d05-116">See Also</span></span>  
 <span data-ttu-id="71d05-117">[スキーマの BizTalk 表記](../core/biztalk-representation-of-schemas.md) </span><span class="sxs-lookup"><span data-stu-id="71d05-117">[BizTalk Representation of Schemas](../core/biztalk-representation-of-schemas.md) </span></span>  
 <span data-ttu-id="71d05-118">[ノードのプロパティ](../core/node-properties.md) </span><span class="sxs-lookup"><span data-stu-id="71d05-118">[Node Properties](../core/node-properties.md) </span></span>  
 <span data-ttu-id="71d05-119">[ノードのプロパティを設定する方法](../core/how-to-set-node-properties.md) </span><span class="sxs-lookup"><span data-stu-id="71d05-119">[How to Set Node Properties](../core/how-to-set-node-properties.md) </span></span>  
 <span data-ttu-id="71d05-120">[[すべての属性] ノード](../core/any-attribute-nodes.md)</span><span class="sxs-lookup"><span data-stu-id="71d05-120">[Any Attribute Nodes](../core/any-attribute-nodes.md)</span></span>