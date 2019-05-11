---
title: ユニオン メカニズムを使用して単純型の派生 |Microsoft Docs
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
ms.openlocfilehash: 0b178b8ee6bf0e09877cc14ac72f30f569162166
ms.sourcegitcommit: 381e83d43796a345488d54b3f7413e11d56ad7be
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 05/07/2019
ms.locfileid: "65393047"
---
# <a name="simple-type-derivation-using-the-union-mechanism"></a><span data-ttu-id="0539d-102">ユニオン メカニズムを使用して単純型の派生</span><span class="sxs-lookup"><span data-stu-id="0539d-102">Simple Type Derivation Using the Union Mechanism</span></span>
<span data-ttu-id="0539d-103">ユニオン メカニズムを使用して、既存の単純型から新しい単純型を派生するときは、複数の型の属性または要素の値ができることを指定に従って、指定した種類の一覧はします。</span><span class="sxs-lookup"><span data-stu-id="0539d-103">When you derive a new simple type from an existing simple type by using the union mechanism, you are specifying that the value for this attribute or element can be of more than one type, according to a list of types that you specify.</span></span> <span data-ttu-id="0539d-104">たとえば、属性または要素の値は、日付、時刻、または日付/時刻値のいずれかを指定できます。</span><span class="sxs-lookup"><span data-stu-id="0539d-104">For example, you can specify that an attribute or element value is either a date, a time, or a date/time value.</span></span>  
  
 <span data-ttu-id="0539d-105">ユニオン メカニズムを使用して新しい単純型の派生について包括的な情報は、W3C web サイトを参照してください。</span><span class="sxs-lookup"><span data-stu-id="0539d-105">For comprehensive information about deriving new simple types by using the union mechanism, refer to the W3C website.</span></span> <span data-ttu-id="0539d-106">これと他の web サイトへのさまざまなリンクは、次を参照してください。 [Web 上の XSD リソース](../core/xsd-resources-on-the-web.md)します。</span><span class="sxs-lookup"><span data-stu-id="0539d-106">For various links to this and other websites, see [XSD Resources on the Web](../core/xsd-resources-on-the-web.md).</span></span>  
  
 <span data-ttu-id="0539d-107">いくつかの使用可能な型の和集合として単純型を派生するには、関連する選択**フィールド要素**ノードまたは**フィールド属性**スキーマ ツリーおよびし、[プロパティ] ウィンドウのノードからの単純型を選択しますドロップダウン リスト、 **Base Data Type**プロパティ。</span><span class="sxs-lookup"><span data-stu-id="0539d-107">To derive a simple type as a union of several possible types, select the relevant **Field Element** node or **Field Attribute** node in the schema tree and then, in the Properties window, select a simple type from the drop-down list for the **Base Data Type** property.</span></span> <span data-ttu-id="0539d-108">、このプロパティの値を選択するとすぐに、 **Derived By**プロパティが自動的に変更するには、その既定値から**制限**、派生した型の既定値として機能します。</span><span class="sxs-lookup"><span data-stu-id="0539d-108">As soon as you have selected a value for this property, the **Derived By** property automatically changes from its default value to **Restriction**, which serves as the default value for type derivation.</span></span> <span data-ttu-id="0539d-109">変更する必要があります、 **Derived By**プロパティから**制限**に**共用体**、原因となる、 **Base Data Type**として名前を変更するプロパティ**メンバー型**プロパティ (名前が変更されたプロパティが移動のためのプロパティのアルファベット順の並べ替えプロパティの一覧で別の位置にちなみに、)。</span><span class="sxs-lookup"><span data-stu-id="0539d-109">You must change the **Derived By** property from **Restriction** to **Union**, which causes the **Base Data Type** property to be renamed as the **Member Types** property (incidentally, the renamed property moves to a different position in the property list due to the alphabetical sorting of the properties).</span></span>  
  
 <span data-ttu-id="0539d-110">最後に、チェック ボックスを使用することができます、**メンバー型**インスタンス メッセージ内の対応する値を許容するその他の種類を選択するドロップダウン チェックリスト。</span><span class="sxs-lookup"><span data-stu-id="0539d-110">Finally, you can use the check boxes in the **Member Types** drop-down checklist to select additional types to allow for corresponding values in instance messages.</span></span>  
  
 <span data-ttu-id="0539d-111">変更すると、**フィールド要素**ノードまたは**フィールド属性**ノード (単純型の派生のプロセスを開始し)、基本データ型に入力し、を設定し、データがあることから**Derived By**プロパティを**共用体**、XSD ビューで対応するフラグメントでは、次の変更を確認できます。</span><span class="sxs-lookup"><span data-stu-id="0539d-111">When you first change a **Field Element** node or **Field Attribute** node from having a data type to having a base data type (thereby starting the process of simple type derivation), and then set the **Derived By** property to **Union**, you can observe the following change in the corresponding fragment in the XSD view.</span></span>  
  
-   <span data-ttu-id="0539d-112">前に、新しく挿入で**フィールド要素**という名前のノード**DatesAndOrTimes**します。</span><span class="sxs-lookup"><span data-stu-id="0539d-112">Before, with a newly inserted **Field Element** node named **DatesAndOrTimes**.</span></span>  
  
    ```  
    <xs:element name="ContainingRecord">  
        <xs:complexType>  
            <xs:sequence>  
  
            </xs:sequence>  
        </xs:complexType>  
    </xs:element>  
  
    ```  
  
-   <span data-ttu-id="0539d-113">設定した後、 **Base Data Type**プロパティを**xs:date**、および設定、 **Derived By**プロパティを**共用体**(その後、 **Base Data Type**プロパティの名前を変更する、**メンバー型**プロパティ) も選択して**xs:datetime**と**xs:time**として追加の許可の種類、**メンバー型**ドロップダウン チェックリスト。</span><span class="sxs-lookup"><span data-stu-id="0539d-113">After setting the **Base Data Type** property to **xs:date**, and setting the **Derived By** property to **Union** (after which the **Base Data Type** property is renamed to be the **Member Types** property), and then also selecting **xs:datetime** and **xs:time** as additional allowed types in the **Member Types** drop-down checklist.</span></span>  
  
    ```  
    <xs:element name="ContainingRecord">  
        <xs:complexType>  
            <xs:sequence>  
  
            </xs:sequence>  
        </xs:complexType>  
    </xs:element>  
  
    ```  
  
## <a name="see-also"></a><span data-ttu-id="0539d-114">参照</span><span class="sxs-lookup"><span data-stu-id="0539d-114">See Also</span></span>  
 [<span data-ttu-id="0539d-115">単純型の派生</span><span class="sxs-lookup"><span data-stu-id="0539d-115">Simple Type Derivation</span></span>](../core/simple-type-derivation.md)