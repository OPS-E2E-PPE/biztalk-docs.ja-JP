---
title: 制約メカニズムを使用した単純型派生 |Microsoft ドキュメント
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
ms.openlocfilehash: dda4b8ad64f1edf262446f1633eda109ba7074ec
ms.sourcegitcommit: cb908c540d8f1a692d01dc8f313e16cb4b4e696d
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 09/20/2017
ms.locfileid: "22271730"
---
# <a name="simple-type-derivation-using-the-restriction-mechanism"></a><span data-ttu-id="ed1d1-102">制約メカニズムを使用した単純型の派生</span><span class="sxs-lookup"><span data-stu-id="ed1d1-102">Simple Type Derivation Using the Restriction Mechanism</span></span>

## <a name="overview"></a><span data-ttu-id="ed1d1-103">概要</span><span class="sxs-lookup"><span data-stu-id="ed1d1-103">Overview</span></span>
<span data-ttu-id="ed1d1-104">制約メカニズムを使用して既存の単純型から新しい単純型を派生させる場合、インスタンス メッセージの属性値または要素値に使用できる値を、基本単純型で許容された値のサブセットに制限するのが一般的です。</span><span class="sxs-lookup"><span data-stu-id="ed1d1-104">When you derive a new simple type from an existing simple type by using the restriction mechanism, you are typically restricting the values allowed in an instance message for that attribute or element value to a subset of those values allowed by the base simple type.</span></span> <span data-ttu-id="ed1d1-105">たとえば、文字列型は、複数の列挙文字列のいずれかに制限できます。</span><span class="sxs-lookup"><span data-stu-id="ed1d1-105">For example, you can restrict a string type to be one of several enumerated strings.</span></span>  
  
 <span data-ttu-id="ed1d1-106">制約メカニズムを使用して新規の単純型を派生させる方法の概要については、W3C Web サイトを参照してください。</span><span class="sxs-lookup"><span data-stu-id="ed1d1-106">For comprehensive information about deriving new simple types by using the restriction mechanism, refer to the W3C website.</span></span> <span data-ttu-id="ed1d1-107">これを他の web サイトのさまざまなリンクは、次を参照してください。 [Web 上の XSD リソース](../core/xsd-resources-on-the-web.md)です。</span><span class="sxs-lookup"><span data-stu-id="ed1d1-107">For various links to this and other websites, see [XSD Resources on the Web](../core/xsd-resources-on-the-web.md).</span></span>  
  
## <a name="field-element-and-field-attribute"></a><span data-ttu-id="ed1d1-108">Field 要素とフィールド属性</span><span class="sxs-lookup"><span data-stu-id="ed1d1-108">Field Element and Field Attribute</span></span>
 <span data-ttu-id="ed1d1-109">制限を使用して単純型を派生するには、関連する選択**フィールド要素**ノードまたは**フィールド属性**スキーマ ツリーでおよびその後、[プロパティ] ウィンドウのノードは、ドロップダウン リストから単純型を選択一覧表示、 **Base Data Type**プロパティです。</span><span class="sxs-lookup"><span data-stu-id="ed1d1-109">To derive a simple type by using restriction, select the relevant **Field Element** node or **Field Attribute** node in the schema tree and then, in the Properties window, select a simple type from the drop-down list for the **Base Data Type** property.</span></span> <span data-ttu-id="ed1d1-110">このプロパティの値を選択するとすぐに、 **Derived By**プロパティが自動的に変更するには、その既定値から**制限**、派生した型の既定値として機能します。</span><span class="sxs-lookup"><span data-stu-id="ed1d1-110">As soon as you have selected a value for this property, the **Derived By** property automatically changes from its default value to **Restriction**, which serves as the default value for type derivation.</span></span> <span data-ttu-id="ed1d1-111">呼ばれるプロパティのまったく新しいカテゴリも、**制限**、プロパティ ウィンドウで使用可能になります。</span><span class="sxs-lookup"><span data-stu-id="ed1d1-111">Also, a whole new category of properties, called **Restriction**, becomes available in the Properties window.</span></span>  
  
 <span data-ttu-id="ed1d1-112">この新しいカテゴリで設定できるプロパティは、選択した基本データ型によって異なります。</span><span class="sxs-lookup"><span data-stu-id="ed1d1-112">Depending on the base data type you select, different properties are available to be set in this new category.</span></span> <span data-ttu-id="ed1d1-113">たとえば、基本データ型が数値の場合、プロパティ**MaxFacet Type** (ときに**MaxFacet Value**設定されている)、 **MaxFacet Value**、 **MinFacet Type**(ときに**MinFacet Value**設定されている)、および**MinFacet Value**値の許容包含または排他範囲の定義に使用できます。</span><span class="sxs-lookup"><span data-stu-id="ed1d1-113">For example, if the base data type is numeric, the properties **MaxFacet Type** (when **MaxFacet Value** is set), **MaxFacet Value**, **MinFacet Type** (when **MinFacet Value** is set), and **MinFacet Value** are available for defining an inclusive or exclusive range of allowed values.</span></span> <span data-ttu-id="ed1d1-114">基本データ型が文字列型の場合、**長さ**、**最大長**、および**最小の長さ**プロパティは、文字列の長さの制限値を使用できます。</span><span class="sxs-lookup"><span data-stu-id="ed1d1-114">If the base data type is a string type, the **Length**, **Maximum Length**, and **Minimum Length** properties are available for constraining the length of the string.</span></span>  
  
 <span data-ttu-id="ed1d1-115">[フィールド] ノードの各種制約プロパティの詳細については、次を参照してください。、**フィールド要素 ノード プロパティ**[!INCLUDE[ui-guidance-developers-reference](../includes/ui-guidance-developers-reference.md)]です。</span><span class="sxs-lookup"><span data-stu-id="ed1d1-115">For more information about the various restriction properties of field nodes, see the **Field Element Node Properties** [!INCLUDE[ui-guidance-developers-reference](../includes/ui-guidance-developers-reference.md)].</span></span>
  
 <span data-ttu-id="ed1d1-116">変更すると、**フィールド要素**ノードまたは**フィールド属性**から基本データ型 (単純型の派生のプロセスを開始し) のままにするデータ型を持つノード、 **Derived によって**プロパティに設定**制限**文字列の最大値に、列挙ベースの制限を指定して、XSD ビューの対応するフラグメントでは、次の変更を確認することができます。</span><span class="sxs-lookup"><span data-stu-id="ed1d1-116">When you first change a **Field Element** node or **Field Attribute** node from having a data type to having a base data type (thereby starting the process of simple type derivation), leave the **Derived By** property set to **Restriction**, and provide an enumeration-based restriction to the allowed string values, you can observe the following changes in the corresponding fragment in the XSD view:</span></span>  
  
-   <span data-ttu-id="ed1d1-117">前に、新しく挿入されると**フィールド要素**という名前のノード**WestCoastStates**です。</span><span class="sxs-lookup"><span data-stu-id="ed1d1-117">Before, with a newly inserted **Field Element** node named **WestCoastStates**.</span></span>  
  
    ```  
    <xs:element name="ContainingRecord">  
        <xs:complexType>  
            <xs:sequence>  
                <xs:element name="WestCoastStates" type="xs:string" />  
            </xs:sequence>  
        </xs:complexType>  
    </xs:element>  
    ```  
  
-   <span data-ttu-id="ed1d1-118">設定した後、 **Base Data Type**プロパティを"xs:string"し、既定値のままにして**制限**の**Derived By**プロパティです。</span><span class="sxs-lookup"><span data-stu-id="ed1d1-118">After setting the **Base Data Type** property to "xs:string", and leaving the derivation default of **Restriction** for the **Derived By** property.</span></span>  
  
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
  
-   <span data-ttu-id="ed1d1-119">設定した後、**列挙**米国本土の西海岸の 3 つの状態の名前を Restriction カテゴリのプロパティです。</span><span class="sxs-lookup"><span data-stu-id="ed1d1-119">After setting the **Enumeration** property in the Restriction category to the names of the three states on the west coast of the continental United States.</span></span>  
  
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
  
## <a name="see-also"></a><span data-ttu-id="ed1d1-120">参照</span><span class="sxs-lookup"><span data-stu-id="ed1d1-120">See Also</span></span>  
 [<span data-ttu-id="ed1d1-121">単純型の派生</span><span class="sxs-lookup"><span data-stu-id="ed1d1-121">Simple Type Derivation</span></span>](../core/simple-type-derivation.md)