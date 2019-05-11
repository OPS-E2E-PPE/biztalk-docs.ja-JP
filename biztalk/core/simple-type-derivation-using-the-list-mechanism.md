---
title: リスト メカニズムを使用して単純型の派生 |Microsoft Docs
ms.custom: ''
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: ''
ms.suite: ''
ms.tgt_pltfrm: ''
ms.topic: article
ms.assetid: 14f3c7b7-7585-4297-9177-2deaef8355f0
caps.latest.revision: 8
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: 318a58f0e0f1aed836bdf7a866a42c7df3941b9a
ms.sourcegitcommit: 381e83d43796a345488d54b3f7413e11d56ad7be
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 05/07/2019
ms.locfileid: "65393159"
---
# <a name="simple-type-derivation-using-the-list-mechanism"></a><span data-ttu-id="968a2-102">リスト メカニズムを使用して単純型の派生</span><span class="sxs-lookup"><span data-stu-id="968a2-102">Simple Type Derivation Using the List Mechanism</span></span>
<span data-ttu-id="968a2-103">リスト メカニズムを使用して、既存の単純型から新しい単純型を派生するとき、この属性または要素の値は、指定した型の値のスペースで区切られたリストであることが指定されます。</span><span class="sxs-lookup"><span data-stu-id="968a2-103">When you derive a new simple type from an existing simple type by using the list mechanism, you are specifying that the value for this attribute or element can be a space-separated list of values of the specified type.</span></span> <span data-ttu-id="968a2-104">たとえば、属性または要素の値が空白で区切られた整数のリストを指定できます。</span><span class="sxs-lookup"><span data-stu-id="968a2-104">For example, you can specify that an attribute or element value is a space-separated list of integers.</span></span>  
  
 <span data-ttu-id="968a2-105">リスト メカニズムを使用して新しい単純型の派生について包括的な情報は、W3C Web サイトを参照してください。</span><span class="sxs-lookup"><span data-stu-id="968a2-105">For comprehensive information about deriving new simple types by using the list mechanism, refer to the W3C Web site.</span></span> <span data-ttu-id="968a2-106">これと他の Web サイトへのさまざまなリンクは、次を参照してください。 [Web 上の XSD リソース](../core/xsd-resources-on-the-web.md)します。</span><span class="sxs-lookup"><span data-stu-id="968a2-106">For various links to this and other Web sites, see [XSD Resources on the Web](../core/xsd-resources-on-the-web.md).</span></span>  
  
 <span data-ttu-id="968a2-107">その型の一覧として単純型を派生するには、関連する選択**フィールド要素**ノードまたは**フィールド属性**ノードをスキーマ ツリーにし、[プロパティ] ウィンドウで、ドロップダウン リストから単純型を選択します一覧表示、 **Base Data Type**プロパティ。</span><span class="sxs-lookup"><span data-stu-id="968a2-107">To derive a simple type as a list of that type, select the relevant **Field Element** node or **Field Attribute** node in the schema tree and then, in the Properties window, select a simple type from the drop-down list for the **Base Data Type** property.</span></span> <span data-ttu-id="968a2-108">このプロパティの値を選択するとすぐに、 **Derived By**プロパティが自動的に変更するには、その既定値から**制限**、派生した型の既定値として使用されます。</span><span class="sxs-lookup"><span data-stu-id="968a2-108">As soon as you select a value for this property, the **Derived By** property automatically changes from its default value to **Restriction**, which serves as the default value for type derivation.</span></span> <span data-ttu-id="968a2-109">変更する必要があります、 **Derived By**プロパティから**制限**に**一覧**、原因となる、 **Base Data Type**として名前を変更するプロパティ**項目の種類**プロパティ (名前が変更されたプロパティが移動のためのプロパティのアルファベット順の並べ替えプロパティの一覧で別の位置にちなみに、)。</span><span class="sxs-lookup"><span data-stu-id="968a2-109">You must change the **Derived By** property from **Restriction** to **List**, which causes the **Base Data Type** property to be renamed as the **Item Type** property (incidentally, the renamed property moves to a different position in the property list due to the alphabetical sorting of the properties).</span></span>  
  
> [!NOTE]
>  <span data-ttu-id="968a2-110">制限を使用してリスト メカニズムを同時に、作成するには、名前付きの単純型の派生を制限メカニズムを使用して、アイテムとして使用しているリスト メカニズムを使用して、もう 1 つの単純型の派生の型。</span><span class="sxs-lookup"><span data-stu-id="968a2-110">You can use the restriction and list mechanisms together, creating a named simple type derivation by using the restriction mechanism, and then using that as the item type in another simple type derivation by using the list mechanism.</span></span> <span data-ttu-id="968a2-111">これにより、たとえば、特定の列挙された文字列のセットに属しているスペースで区切られた文字列の一覧に制約される値。</span><span class="sxs-lookup"><span data-stu-id="968a2-111">This can result, for example, in a value that is constrained to be a list of space-separated strings belonging to a particular enumerated set of strings.</span></span>  
  
> [!CAUTION]
>  <span data-ttu-id="968a2-112">リスト メカニズムを使用して、単純型の派生は複雑になるときに、文字列などの空白文字を許可する 1 つを選択した項目の種類。</span><span class="sxs-lookup"><span data-stu-id="968a2-112">Using the list mechanism for simple type derivation can be complicated when the item type you choose is one that itself allows spaces, such as strings.</span></span> <span data-ttu-id="968a2-113">リスト メカニズムの一覧で許可されている型の値を区切るスペースを使用するためです。</span><span class="sxs-lookup"><span data-stu-id="968a2-113">This is because the list mechanism uses spaces to separate values of the allowed type in the list.</span></span>  
  
 <span data-ttu-id="968a2-114">変更すると、**フィールド要素**ノードまたは**フィールド属性**ノード (単純型の派生のプロセスを開始し)、基本データ型に入力し、を設定し、データがあることから**Derived By**プロパティを**一覧**、XSD ビューで対応するフラグメントでは、次の変更を確認できます。</span><span class="sxs-lookup"><span data-stu-id="968a2-114">When you first change a **Field Element** node or **Field Attribute** node from having a data type to having a base data type (thereby starting the process of simple type derivation), and then set the **Derived By** property to **List**, you can observe the following change in the corresponding fragment in the XSD view:</span></span>  
  
-   <span data-ttu-id="968a2-115">前に、新しく挿入で**フィールド要素**という名前のノード **"zipcodelist"** します。</span><span class="sxs-lookup"><span data-stu-id="968a2-115">Before, with a newly inserted **Field Element** node named **ZipCodeList**.</span></span>  
  
    ```  
    <xs:element name="ContainingRecord">  
        <xs:complexType>  
            <xs:sequence>  
                <xs:element name="ZipCodeList" type="xs:string" />  
            </xs:sequence>  
        </xs:complexType>  
    </xs:element>  
  
    ```  
  
-   <span data-ttu-id="968a2-116">設定した後、 **Base Data Type**プロパティを xs:integer に設定、 **Derived By**プロパティを**一覧**(その後、 **Base Data Type**プロパティの名前を変更する、**項目の種類**プロパティ)。</span><span class="sxs-lookup"><span data-stu-id="968a2-116">After setting the **Base Data Type** property to xs:integer, and setting the **Derived By** property to **List** (after which the **Base Data Type** property is renamed to be the **Item Type** property).</span></span>  
  
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
>  <span data-ttu-id="968a2-117">実際のスキーマで最初に定義し、5 桁の整数を制限する整数の単純型の派生を名前になり、派生する、 **"zipcodelist"** に一覧を効果的に制限すること、その型から要素5 桁の整数。</span><span class="sxs-lookup"><span data-stu-id="968a2-117">In a real-life schema, it would be better to first define and name a simple type derivation of integer that restricts the integer to five digits, and then to derive the **ZipCodeList** element from that type, effectively limiting the list to integers having five digits.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="968a2-118">参照</span><span class="sxs-lookup"><span data-stu-id="968a2-118">See Also</span></span>  
 [<span data-ttu-id="968a2-119">単純型の派生</span><span class="sxs-lookup"><span data-stu-id="968a2-119">Simple Type Derivation</span></span>](../core/simple-type-derivation.md)