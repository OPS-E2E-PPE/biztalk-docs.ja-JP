---
title: "複合グローバル型を再利用 |Microsoft ドキュメント"
ms.custom: 
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: 
ms.suite: 
ms.tgt_pltfrm: 
ms.topic: article
ms.assetid: 3d0d8018-f2c6-44cc-9330-2385ac8887eb
caps.latest.revision: "7"
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: 492d1c345b1ac540bc2410c554be29996fc52dd6
ms.sourcegitcommit: cb908c540d8f1a692d01dc8f313e16cb4b4e696d
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 09/20/2017
---
# <a name="complex-global-type-re-use"></a><span data-ttu-id="6a548-102">複合グローバル型の再利用</span><span class="sxs-lookup"><span data-stu-id="6a548-102">Complex Global Type Re-use</span></span>
<span data-ttu-id="6a548-103">使用する、複雑なグローバル型は、別の場所にスキーマ ツリーで、開始、新しいを挿入して**レコード**目的の場所にあるノード。</span><span class="sxs-lookup"><span data-stu-id="6a548-103">To use a complex global type as is, in another location in the schema tree, begin by inserting a new **Record** node at the desired location.</span></span> <span data-ttu-id="6a548-104">設定し、その**Data Structure Type**プロパティ、複合グローバル型の名前にします。</span><span class="sxs-lookup"><span data-stu-id="6a548-104">Then set its **Data Structure Type** property to the name of a complex global type.</span></span>  
  
 <span data-ttu-id="6a548-105">次の例では、 **BillingAddress**新しく挿入されるの名前を指定**レコード**ノード、および**GlobalAddrType**採用されていますが、複合グローバル型の名前を指定します。</span><span class="sxs-lookup"><span data-stu-id="6a548-105">In the following example, **BillingAddress** is the name of the newly inserted **Record** node, and **GlobalAddrType** is the name of the complex global type that it adopts.</span></span> <span data-ttu-id="6a548-106">名前付きノードの下に、スキーマ ツリー ビューで、重複するノード構造が表示されます**BillingAddress**、という名前のノードの下にある隣接するノード構造と同一**ShippingAddress**です。</span><span class="sxs-lookup"><span data-stu-id="6a548-106">In the schema tree view, a duplicate node structure would be displayed below the node named **BillingAddress**, identical to the adjacent node structure under the node named **ShippingAddress**.</span></span>  
  
-   <span data-ttu-id="6a548-107">前に、新しく挿入されたノードを持つという**BillingAddress**です。</span><span class="sxs-lookup"><span data-stu-id="6a548-107">Before, with a newly inserted node named **BillingAddress**.</span></span>  
  
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
  
-   <span data-ttu-id="6a548-108">複合基本型を使用した後**GlobalAddrType**をそのままです。</span><span class="sxs-lookup"><span data-stu-id="6a548-108">After using the complex base type **GlobalAddrType**, as is.</span></span>  
  
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
  
## <a name="see-also"></a><span data-ttu-id="6a548-109">参照</span><span class="sxs-lookup"><span data-stu-id="6a548-109">See Also</span></span>  
 [<span data-ttu-id="6a548-110">複合グローバル型を使用する方法</span><span class="sxs-lookup"><span data-stu-id="6a548-110">Ways to Use Complex Global Types</span></span>](../core/ways-to-use-complex-global-types.md)