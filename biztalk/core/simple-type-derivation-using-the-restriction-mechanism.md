---
title: 制約メカニズムを使用して単純型の派生 |Microsoft Docs
ms.custom: ''
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: ''
ms.suite: ''
ms.tgt_pltfrm: ''
ms.topic: article
ms.assetid: e4ca712e-9563-4917-9bfc-1033a36773e8
caps.latest.revision: 7
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: 46cfded2bd9995e99972108f46aa53c883fffc99
ms.sourcegitcommit: 381e83d43796a345488d54b3f7413e11d56ad7be
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 05/07/2019
ms.locfileid: "65393069"
---
# <a name="simple-type-derivation-using-the-restriction-mechanism"></a><span data-ttu-id="e32ee-102">制約メカニズムを使用して単純型の派生</span><span class="sxs-lookup"><span data-stu-id="e32ee-102">Simple Type Derivation Using the Restriction Mechanism</span></span>

## <a name="overview"></a><span data-ttu-id="e32ee-103">概要</span><span class="sxs-lookup"><span data-stu-id="e32ee-103">Overview</span></span>
<span data-ttu-id="e32ee-104">制約メカニズムを使用して、既存の単純型から新しい単純型を派生するときは、基本の単純型で許容された値のサブセットにその属性または要素の値のインスタンス メッセージで使用できる値を制限している通常します。</span><span class="sxs-lookup"><span data-stu-id="e32ee-104">When you derive a new simple type from an existing simple type by using the restriction mechanism, you are typically restricting the values allowed in an instance message for that attribute or element value to a subset of those values allowed by the base simple type.</span></span> <span data-ttu-id="e32ee-105">たとえば、いくつかの列挙された文字列のいずれかを指定する文字列型を制限できます。</span><span class="sxs-lookup"><span data-stu-id="e32ee-105">For example, you can restrict a string type to be one of several enumerated strings.</span></span>  
  
 <span data-ttu-id="e32ee-106">制約メカニズムを使用して新しい単純型の派生について包括的な情報は、W3C web サイトを参照してください。</span><span class="sxs-lookup"><span data-stu-id="e32ee-106">For comprehensive information about deriving new simple types by using the restriction mechanism, refer to the W3C website.</span></span> <span data-ttu-id="e32ee-107">これと他の web サイトへのさまざまなリンクは、次を参照してください。 [Web 上の XSD リソース](../core/xsd-resources-on-the-web.md)します。</span><span class="sxs-lookup"><span data-stu-id="e32ee-107">For various links to this and other websites, see [XSD Resources on the Web](../core/xsd-resources-on-the-web.md).</span></span>  
  
## <a name="field-element-and-field-attribute"></a><span data-ttu-id="e32ee-108">フィールド要素とフィールド属性</span><span class="sxs-lookup"><span data-stu-id="e32ee-108">Field Element and Field Attribute</span></span>
 <span data-ttu-id="e32ee-109">制限を使用して単純型を派生するには、関連する選択**フィールド要素**ノードまたは**フィールド属性**ノードをスキーマ ツリーにし、[プロパティ] ウィンドウで、ドロップダウン リストから単純型を選択します一覧表示、 **Base Data Type**プロパティ。</span><span class="sxs-lookup"><span data-stu-id="e32ee-109">To derive a simple type by using restriction, select the relevant **Field Element** node or **Field Attribute** node in the schema tree and then, in the Properties window, select a simple type from the drop-down list for the **Base Data Type** property.</span></span> <span data-ttu-id="e32ee-110">、このプロパティの値を選択するとすぐに、 **Derived By**プロパティが自動的に変更するには、その既定値から**制限**、派生した型の既定値として機能します。</span><span class="sxs-lookup"><span data-stu-id="e32ee-110">As soon as you have selected a value for this property, the **Derived By** property automatically changes from its default value to **Restriction**, which serves as the default value for type derivation.</span></span> <span data-ttu-id="e32ee-111">という名前のプロパティのまったく新しいカテゴリではまた、**制限**、[プロパティ] ウィンドウに表示されます。</span><span class="sxs-lookup"><span data-stu-id="e32ee-111">Also, a whole new category of properties, called **Restriction**, becomes available in the Properties window.</span></span>  
  
 <span data-ttu-id="e32ee-112">選択した基本データ型によっては、さまざまなプロパティはこの新しいカテゴリで設定できます。</span><span class="sxs-lookup"><span data-stu-id="e32ee-112">Depending on the base data type you select, different properties are available to be set in this new category.</span></span> <span data-ttu-id="e32ee-113">たとえば、基本データ型が数値でプロパティ**MaxFacet Type** (と**MaxFacet Value**設定されている)、 **MaxFacet Value**、 **MinFacet Type**(と**MinFacet Value**設定されている)、および**MinFacet Value**の値の許容の包含または除外範囲の定義に使用します。</span><span class="sxs-lookup"><span data-stu-id="e32ee-113">For example, if the base data type is numeric, the properties **MaxFacet Type** (when **MaxFacet Value** is set), **MaxFacet Value**, **MinFacet Type** (when **MinFacet Value** is set), and **MinFacet Value** are available for defining an inclusive or exclusive range of allowed values.</span></span> <span data-ttu-id="e32ee-114">基本データ型が文字列型の場合、**長さ**、**最大長**、および**長さ**プロパティは、文字列の長さの制限値を使用できます。</span><span class="sxs-lookup"><span data-stu-id="e32ee-114">If the base data type is a string type, the **Length**, **Maximum Length**, and **Minimum Length** properties are available for constraining the length of the string.</span></span>  
  
 <span data-ttu-id="e32ee-115">[フィールド] ノードの各種制約プロパティの詳細については、次を参照してください。、**フィールド要素 ノード プロパティ**[!INCLUDE[ui-guidance-developers-reference](../includes/ui-guidance-developers-reference.md)]します。</span><span class="sxs-lookup"><span data-stu-id="e32ee-115">For more information about the various restriction properties of field nodes, see the **Field Element Node Properties** [!INCLUDE[ui-guidance-developers-reference](../includes/ui-guidance-developers-reference.md)].</span></span>
  
 <span data-ttu-id="e32ee-116">変更すると、**フィールド要素**ノードまたは**フィールド属性**から基本データ型 (単純型の派生のプロセスを開始し) のままにするデータ型を持つノード、 **派生して**プロパティに設定**制限**、および文字列の最大値に列挙ベースの制限を提供、XSD ビューで対応するフラグメントで次の変更を確認できます。</span><span class="sxs-lookup"><span data-stu-id="e32ee-116">When you first change a **Field Element** node or **Field Attribute** node from having a data type to having a base data type (thereby starting the process of simple type derivation), leave the **Derived By** property set to **Restriction**, and provide an enumeration-based restriction to the allowed string values, you can observe the following changes in the corresponding fragment in the XSD view:</span></span>  
  
-   <span data-ttu-id="e32ee-117">前に、新しく挿入で**フィールド要素**という名前のノード**WestCoastStates**します。</span><span class="sxs-lookup"><span data-stu-id="e32ee-117">Before, with a newly inserted **Field Element** node named **WestCoastStates**.</span></span>  
  
    ```  
    <xs:element name="ContainingRecord">  
        <xs:complexType>  
            <xs:sequence>  
                <xs:element name="WestCoastStates" type="xs:string" />  
            </xs:sequence>  
        </xs:complexType>  
    </xs:element>  
    ```  
  
-   <span data-ttu-id="e32ee-118">設定した後、 **Base Data Type**プロパティを"xs:string"し、既定値のままにして**制限**の**Derived By**プロパティ。</span><span class="sxs-lookup"><span data-stu-id="e32ee-118">After setting the **Base Data Type** property to "xs:string", and leaving the derivation default of **Restriction** for the **Derived By** property.</span></span>  
  
    ```  
    <xs:element name="ContainingRecord">  
        <xs:complexType>  
            <xs:sequence>  
                <xs:element name="WestCoastStates" >  
                    <xs:simpleType>  
                        <xs:restriction base="xs:string" />  
                    </xs:simpleType>  
                </xs:element>  
            </xs:sequence>  
        </xs:complexType>  
    </xs:element>  
    ```  
  
-   <span data-ttu-id="e32ee-119">設定した後、**列挙**米国本土西海岸の 3 つの状態の名前に Restriction カテゴリのプロパティ。</span><span class="sxs-lookup"><span data-stu-id="e32ee-119">After setting the **Enumeration** property in the Restriction category to the names of the three states on the west coast of the continental United States.</span></span>  
  
    ```  
    <xs:element name="ContainingRecord">  
        <xs:complexType>  
            <xs:sequence>  
                <xs:element name="WestCoastStates">  
                    <xs:simpleType>  
                        <xs:restriction base="xs:string" />  
                            <xs:enumeration value="Washington" />  
                            <xs:enumeration value="Oregon" />  
                            <xs:enumeration value="California" />  
                        </xs:restriction>  
                    </xs:simpleType>  
                </xs:element>  
            </xs:sequence>  
        </xs:complexType>  
    </xs:element>  
    ```  
  
## <a name="see-also"></a><span data-ttu-id="e32ee-120">参照</span><span class="sxs-lookup"><span data-stu-id="e32ee-120">See Also</span></span>  
 [<span data-ttu-id="e32ee-121">単純型の派生</span><span class="sxs-lookup"><span data-stu-id="e32ee-121">Simple Type Derivation</span></span>](../core/simple-type-derivation.md)