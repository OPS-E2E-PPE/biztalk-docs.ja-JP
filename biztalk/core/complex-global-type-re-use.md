---
title: 複合グローバル型を再利用 |Microsoft Docs
ms.custom: ''
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: ''
ms.suite: ''
ms.tgt_pltfrm: ''
ms.topic: article
ms.assetid: 3d0d8018-f2c6-44cc-9330-2385ac8887eb
caps.latest.revision: 7
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: 63d8d743878e268a0f75ff27ca5bf6842a43b10b
ms.sourcegitcommit: 381e83d43796a345488d54b3f7413e11d56ad7be
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 05/07/2019
ms.locfileid: "65356773"
---
# <a name="complex-global-type-re-use"></a><span data-ttu-id="a713f-102">複合グローバル型を再利用</span><span class="sxs-lookup"><span data-stu-id="a713f-102">Complex Global Type Re-use</span></span>
<span data-ttu-id="a713f-103">使用する、複雑なグローバル型は、スキーマ ツリーの別の場所で開始新しいを挿入して**レコード**目的の場所にあるノード。</span><span class="sxs-lookup"><span data-stu-id="a713f-103">To use a complex global type as is, in another location in the schema tree, begin by inserting a new **Record** node at the desired location.</span></span> <span data-ttu-id="a713f-104">設定し、その**Data Structure Type**プロパティを複合グローバル型の名前にします。</span><span class="sxs-lookup"><span data-stu-id="a713f-104">Then set its **Data Structure Type** property to the name of a complex global type.</span></span>  
  
 <span data-ttu-id="a713f-105">次の例では、 **BillingAddress**新しく挿入の名前を指定**レコード**ノード、および**GlobalAddrType**これを採用する複合グローバル型の名前を指定します。</span><span class="sxs-lookup"><span data-stu-id="a713f-105">In the following example, **BillingAddress** is the name of the newly inserted **Record** node, and **GlobalAddrType** is the name of the complex global type that it adopts.</span></span> <span data-ttu-id="a713f-106">という名前のノードの下で、スキーマ ツリー ビューでは、重複するノード構造が表示されます**BillingAddress**という名前のノードの下の隣接するノード構造と同じ、 **ShippingAddress**します。</span><span class="sxs-lookup"><span data-stu-id="a713f-106">In the schema tree view, a duplicate node structure would be displayed below the node named **BillingAddress**, identical to the adjacent node structure under the node named **ShippingAddress**.</span></span>  
  
-   <span data-ttu-id="a713f-107">前に、新しく挿入されたノードを持つという**BillingAddress**します。</span><span class="sxs-lookup"><span data-stu-id="a713f-107">Before, with a newly inserted node named **BillingAddress**.</span></span>  
  
    ```  
    <xs:schema>  
        <xs:element name="Root">  
            <xs:complexType>  
                <xs:sequence>  
                    <xs:element name="ShippingAddress" type="GlobalAddrType" />  
                    <xs:element name="BillingAddress">  
                        <xs:sequence />  
                    </xs:element>  
                </xs:sequence>  
            </xs:complexType>  
        </xs:element>  
        <xs:complexType name="GlobalAddrType">  
        [Address structure defined globally here.]  
        </xs:complexType>  
    </xs:schema>  
    ```  
  
-   <span data-ttu-id="a713f-108">複合基本型を使用した後**GlobalAddrType**などです。</span><span class="sxs-lookup"><span data-stu-id="a713f-108">After using the complex base type **GlobalAddrType**, as is.</span></span>  
  
    ```  
    <xs:schema>  
        <xs:element name="Root">  
            <xs:complexType>  
                <xs:sequence>  
                    <xs:element name="ShippingAddress" type="GlobalAddrType" />  
                    <xs:element name="BillingAddress" type="GlobalAddrType" />  
                </xs:sequence>  
            </xs:complexType>  
        </xs:element>  
        <xs:complexType name="GlobalAddrType">  
        [Address structure defined globally here.]  
        </xs:complexType>  
    </xs:schema>  
    ```  
  
## <a name="see-also"></a><span data-ttu-id="a713f-109">参照</span><span class="sxs-lookup"><span data-stu-id="a713f-109">See Also</span></span>  
 [<span data-ttu-id="a713f-110">複合グローバル型の使用方法</span><span class="sxs-lookup"><span data-stu-id="a713f-110">Ways to Use Complex Global Types</span></span>](../core/ways-to-use-complex-global-types.md)