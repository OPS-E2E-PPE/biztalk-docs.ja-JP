---
title: "リスト メカニズムを使用した単純型の派生 |Microsoft ドキュメント"
ms.custom: 
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: 
ms.suite: 
ms.tgt_pltfrm: 
ms.topic: article
ms.assetid: 14f3c7b7-7585-4297-9177-2deaef8355f0
caps.latest.revision: "8"
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: aafc6a540e9595f426858bc16fedfb1f8fe0bc8f
ms.sourcegitcommit: cb908c540d8f1a692d01dc8f313e16cb4b4e696d
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 09/20/2017
---
# <a name="simple-type-derivation-using-the-list-mechanism"></a><span data-ttu-id="db7bf-102">リスト メカニズムを使用した単純型の派生</span><span class="sxs-lookup"><span data-stu-id="db7bf-102">Simple Type Derivation Using the List Mechanism</span></span>
<span data-ttu-id="db7bf-103">リスト メカニズムを使用して既存の単純型から新しい単純型を派生させる場合、この型の属性や要素の値を、空白で区切られた一覧として指定できます。この一覧には、指定された型の値が示されます。</span><span class="sxs-lookup"><span data-stu-id="db7bf-103">When you derive a new simple type from an existing simple type by using the list mechanism, you are specifying that the value for this attribute or element can be a space-separated list of values of the specified type.</span></span> <span data-ttu-id="db7bf-104">たとえば、属性または要素の値を、整数型の値が示される空白区切りの一覧として指定できます。</span><span class="sxs-lookup"><span data-stu-id="db7bf-104">For example, you can specify that an attribute or element value is a space-separated list of integers.</span></span>  
  
 <span data-ttu-id="db7bf-105">リスト メカニズムを使用して新しい単純型を派生する場合の概要については、W3C Web サイトを参照してください。</span><span class="sxs-lookup"><span data-stu-id="db7bf-105">For comprehensive information about deriving new simple types by using the list mechanism, refer to the W3C Web site.</span></span> <span data-ttu-id="db7bf-106">これを他の Web サイトのさまざまなリンクは、次を参照してください。 [Web 上の XSD リソース](../core/xsd-resources-on-the-web.md)です。</span><span class="sxs-lookup"><span data-stu-id="db7bf-106">For various links to this and other Web sites, see [XSD Resources on the Web](../core/xsd-resources-on-the-web.md).</span></span>  
  
 <span data-ttu-id="db7bf-107">その型の一覧として単純型を派生するには、関連する選択**フィールド要素**ノードまたは**フィールド属性**スキーマ ツリーでおよびその後、[プロパティ] ウィンドウのノードは、ドロップダウン リストから単純型を選択一覧表示、 **Base Data Type**プロパティです。</span><span class="sxs-lookup"><span data-stu-id="db7bf-107">To derive a simple type as a list of that type, select the relevant **Field Element** node or **Field Attribute** node in the schema tree and then, in the Properties window, select a simple type from the drop-down list for the **Base Data Type** property.</span></span> <span data-ttu-id="db7bf-108">このプロパティの値を選択するとすぐに、 **Derived By**プロパティが自動的に変更するには、その既定値から**制限**、派生した型の既定値として機能します。</span><span class="sxs-lookup"><span data-stu-id="db7bf-108">As soon as you select a value for this property, the **Derived By** property automatically changes from its default value to **Restriction**, which serves as the default value for type derivation.</span></span> <span data-ttu-id="db7bf-109">変更する必要があります、 **Derived By**プロパティから**制限**に**リスト**、これにより、 **Base Data Type**として名前を変更するプロパティ**項目の種類**プロパティ (ちなみに、名前が変更されたプロパティに移動、プロパティ リストのプロパティのアルファベット順の並べ替えのための別の位置)。</span><span class="sxs-lookup"><span data-stu-id="db7bf-109">You must change the **Derived By** property from **Restriction** to **List**, which causes the **Base Data Type** property to be renamed as the **Item Type** property (incidentally, the renamed property moves to a different position in the property list due to the alphabetical sorting of the properties).</span></span>  
  
> [!NOTE]
>  <span data-ttu-id="db7bf-110">制約メカニズムとリスト メカニズムを一緒に使用できます。制約メカニズムを使用して、名前付きの単純型の派生を作成し、さらにリスト メカニズムを使用して、作成した派生を別の単純型の派生内で項目の種類として使用できます。</span><span class="sxs-lookup"><span data-stu-id="db7bf-110">You can use the restriction and list mechanisms together, creating a named simple type derivation by using the restriction mechanism, and then using that as the item type in another simple type derivation by using the list mechanism.</span></span> <span data-ttu-id="db7bf-111">これにより、空白で区切られた文字列の一覧に強制的に含まれる値などが発生します。この一覧には、特定の文字列のセットが列挙されます。</span><span class="sxs-lookup"><span data-stu-id="db7bf-111">This can result, for example, in a value that is constrained to be a list of space-separated strings belonging to a particular enumerated set of strings.</span></span>  
  
> [!CAUTION]
>  <span data-ttu-id="db7bf-112">単純型の派生にリスト メカニズムを使用すると、選択した項目の種類が文字列などの空白文字を許可する場合に、複雑になる可能性があります。</span><span class="sxs-lookup"><span data-stu-id="db7bf-112">Using the list mechanism for simple type derivation can be complicated when the item type you choose is one that itself allows spaces, such as strings.</span></span> <span data-ttu-id="db7bf-113">このため、リスト メカニズムは、空白文字を使用して、一覧で許可されている型の値を区切ります。</span><span class="sxs-lookup"><span data-stu-id="db7bf-113">This is because the list mechanism uses spaces to separate values of the allowed type in the list.</span></span>  
  
 <span data-ttu-id="db7bf-114">変更すると、**フィールド要素**ノードまたは**フィールド属性**ノード (単純型の派生のプロセスを開始し)、基本データ型を持つように入力して、を設定してデータを持つから**Derived By**プロパティを**一覧**、XSD ビューの対応するフラグメントで、次の変更を確認することができます。</span><span class="sxs-lookup"><span data-stu-id="db7bf-114">When you first change a **Field Element** node or **Field Attribute** node from having a data type to having a base data type (thereby starting the process of simple type derivation), and then set the **Derived By** property to **List**, you can observe the following change in the corresponding fragment in the XSD view:</span></span>  
  
-   <span data-ttu-id="db7bf-115">前に、新しく挿入されると**フィールド要素**という名前のノード**"zipcodelist"**です。</span><span class="sxs-lookup"><span data-stu-id="db7bf-115">Before, with a newly inserted **Field Element** node named **ZipCodeList**.</span></span>  
  
    ```  
    <xs:element name="ContainingRecord">  
        <xs:complexType>  
            <xs:sequence>  
                <xs:element name="ZipCodeList" type="xs:string" />  
            </xs:sequence>  
        </xs:complexType>  
    </xs:element>  
  
    ```  
  
-   <span data-ttu-id="db7bf-116">設定した後、 **Base Data Type** xs:integer、および設定するプロパティ、 **Derived By**プロパティを**リスト**(その後、 **Base Data Type**プロパティの名前を変更する、**項目の種類**プロパティ)。</span><span class="sxs-lookup"><span data-stu-id="db7bf-116">After setting the **Base Data Type** property to xs:integer, and setting the **Derived By** property to **List** (after which the **Base Data Type** property is renamed to be the **Item Type** property).</span></span>  
  
    ```  
    <xs:element name="ContainingRecord">  
        <xs:complexType>  
            <xs:sequence>  
                <xs:element name="ZipCodeList">  
                    <xs:simpleType>  
               <xs:list itemType="xs:integer" />   
                       </xs:simpleType>  
                </xs:element>  
            </xs:sequence>  
        </xs:complexType>  
    </xs:element>  
  
    ```  
  
> [!NOTE]
>  <span data-ttu-id="db7bf-117">実際のスキーマがあります最初を定義し、名前を 5 桁の数値を整数に制限する整数の単純型から派生する方がよいとその派生するために、 **"zipcodelist"**にリストを効果的に制限する、その型から要素5 桁の数字を持つ整数。</span><span class="sxs-lookup"><span data-stu-id="db7bf-117">In a real-life schema, it would be better to first define and name a simple type derivation of integer that restricts the integer to five digits, and then to derive the **ZipCodeList** element from that type, effectively limiting the list to integers having five digits.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="db7bf-118">参照</span><span class="sxs-lookup"><span data-stu-id="db7bf-118">See Also</span></span>  
 [<span data-ttu-id="db7bf-119">単純型の派生</span><span class="sxs-lookup"><span data-stu-id="db7bf-119">Simple Type Derivation</span></span>](../core/simple-type-derivation.md)