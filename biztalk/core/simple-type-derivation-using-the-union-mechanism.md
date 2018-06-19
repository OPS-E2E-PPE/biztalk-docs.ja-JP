---
title: ユニオン メカニズムを使用した単純型派生 |Microsoft ドキュメント
ms.custom: ''
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: ''
ms.suite: ''
ms.tgt_pltfrm: ''
ms.topic: article
ms.assetid: e51ae390-78f5-4fb9-9163-2a8023aea1ec
caps.latest.revision: 6
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: 1414fa506f824415de8e8449e8b2b27befd2fc76
ms.sourcegitcommit: cb908c540d8f1a692d01dc8f313e16cb4b4e696d
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 09/20/2017
ms.locfileid: "22270378"
---
# <a name="simple-type-derivation-using-the-union-mechanism"></a><span data-ttu-id="58cee-102">ユニオン メカニズムを使用した単純型の派生</span><span class="sxs-lookup"><span data-stu-id="58cee-102">Simple Type Derivation Using the Union Mechanism</span></span>
<span data-ttu-id="58cee-103">ユニオン メカニズムを使用して既存の単純型から新しい単純型を派生させる場合、一連の型を指定することにより、対応する属性または要素の値に対し、複数の型を割り当てることができます。</span><span class="sxs-lookup"><span data-stu-id="58cee-103">When you derive a new simple type from an existing simple type by using the union mechanism, you are specifying that the value for this attribute or element can be of more than one type, according to a list of types that you specify.</span></span> <span data-ttu-id="58cee-104">たとえば、1 つの属性または要素に対して、日付、時刻、日付/時刻のすべての型を割り当てることができます。</span><span class="sxs-lookup"><span data-stu-id="58cee-104">For example, you can specify that an attribute or element value is either a date, a time, or a date/time value.</span></span>  
  
 <span data-ttu-id="58cee-105">ユニオン メカニズムを使用して新しい単純型を派生させる方法の概要については、W3C Web サイトを参照してください。</span><span class="sxs-lookup"><span data-stu-id="58cee-105">For comprehensive information about deriving new simple types by using the union mechanism, refer to the W3C website.</span></span> <span data-ttu-id="58cee-106">これを他の web サイトのさまざまなリンクは、次を参照してください。 [Web 上の XSD リソース](../core/xsd-resources-on-the-web.md)です。</span><span class="sxs-lookup"><span data-stu-id="58cee-106">For various links to this and other websites, see [XSD Resources on the Web](../core/xsd-resources-on-the-web.md).</span></span>  
  
 <span data-ttu-id="58cee-107">いくつかの使用可能な型のユニオンとして単純型を派生させるするには、関連する選択**フィールド要素**ノードまたは**フィールド属性**スキーマ ツリーでおよびその後、[プロパティ] ウィンドウのノードから単純型の選択ドロップダウン リスト、 **Base Data Type**プロパティです。</span><span class="sxs-lookup"><span data-stu-id="58cee-107">To derive a simple type as a union of several possible types, select the relevant **Field Element** node or **Field Attribute** node in the schema tree and then, in the Properties window, select a simple type from the drop-down list for the **Base Data Type** property.</span></span> <span data-ttu-id="58cee-108">このプロパティの値を選択するとすぐに、 **Derived By**プロパティが自動的に変更するには、その既定値から**制限**、派生した型の既定値として機能します。</span><span class="sxs-lookup"><span data-stu-id="58cee-108">As soon as you have selected a value for this property, the **Derived By** property automatically changes from its default value to **Restriction**, which serves as the default value for type derivation.</span></span> <span data-ttu-id="58cee-109">変更する必要があります、 **Derived By**プロパティから**制限**に**共用体**、これにより、 **Base Data Type**として名前を変更するプロパティ**Member Types**プロパティ (ちなみに、名前が変更されたプロパティに移動、プロパティ リストのプロパティのアルファベット順の並べ替えのための別の位置)。</span><span class="sxs-lookup"><span data-stu-id="58cee-109">You must change the **Derived By** property from **Restriction** to **Union**, which causes the **Base Data Type** property to be renamed as the **Member Types** property (incidentally, the renamed property moves to a different position in the property list due to the alphabetical sorting of the properties).</span></span>  
  
 <span data-ttu-id="58cee-110">最後に、チェック ボックスを使用して、**メンバーの種類**ドロップダウン チェックリストをインスタンス メッセージ内の対応する値を許容するその他の種類を選択します。</span><span class="sxs-lookup"><span data-stu-id="58cee-110">Finally, you can use the check boxes in the **Member Types** drop-down checklist to select additional types to allow for corresponding values in instance messages.</span></span>  
  
 <span data-ttu-id="58cee-111">変更すると、**フィールド要素**ノードまたは**フィールド属性**ノード (単純型の派生のプロセスを開始し)、基本データ型を持つように入力して、を設定してデータを持つから**Derived By**プロパティを**共用体**、XSD ビューの対応するフラグメントで、次の変更を確認することができます。</span><span class="sxs-lookup"><span data-stu-id="58cee-111">When you first change a **Field Element** node or **Field Attribute** node from having a data type to having a base data type (thereby starting the process of simple type derivation), and then set the **Derived By** property to **Union**, you can observe the following change in the corresponding fragment in the XSD view.</span></span>  
  
-   <span data-ttu-id="58cee-112">前に、新しく挿入されると**フィールド要素**という名前のノード**DatesAndOrTimes**です。</span><span class="sxs-lookup"><span data-stu-id="58cee-112">Before, with a newly inserted **Field Element** node named **DatesAndOrTimes**.</span></span>  
  
    ```  
    <xs:element name="ContainingRecord">  
        <xs:complexType>  
            <xs:sequence>  
  
            </xs:sequence>  
        </xs:complexType>  
    </xs:element>  
  
    ```  
  
-   <span data-ttu-id="58cee-113">設定した後、 **Base Data Type**プロパティを**xs:date**、および設定、 **Derived By**プロパティを**共用体**(その後、 **Base Data Type**プロパティの名前を変更する、 **Member Types**プロパティ) も選択して**xs:datetime**と**xs:time**として追加の許可されている型で、 **Member Types**ドロップダウン チェックリストです。</span><span class="sxs-lookup"><span data-stu-id="58cee-113">After setting the **Base Data Type** property to **xs:date**, and setting the **Derived By** property to **Union** (after which the **Base Data Type** property is renamed to be the **Member Types** property), and then also selecting **xs:datetime** and **xs:time** as additional allowed types in the **Member Types** drop-down checklist.</span></span>  
  
    ```  
    <xs:element name="ContainingRecord">  
        <xs:complexType>  
            <xs:sequence>  
  
            </xs:sequence>  
        </xs:complexType>  
    </xs:element>  
  
    ```  
  
## <a name="see-also"></a><span data-ttu-id="58cee-114">参照</span><span class="sxs-lookup"><span data-stu-id="58cee-114">See Also</span></span>  
 [<span data-ttu-id="58cee-115">単純型の派生</span><span class="sxs-lookup"><span data-stu-id="58cee-115">Simple Type Derivation</span></span>](../core/simple-type-derivation.md)