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
# <a name="complex-global-type-re-use"></a>複合グローバル型の再利用
使用する、複雑なグローバル型は、別の場所にスキーマ ツリーで、開始、新しいを挿入して**レコード**目的の場所にあるノード。 設定し、その**Data Structure Type**プロパティ、複合グローバル型の名前にします。  
  
 次の例では、 **BillingAddress**新しく挿入されるの名前を指定**レコード**ノード、および**GlobalAddrType**採用されていますが、複合グローバル型の名前を指定します。 名前付きノードの下に、スキーマ ツリー ビューで、重複するノード構造が表示されます**BillingAddress**、という名前のノードの下にある隣接するノード構造と同一**ShippingAddress**です。  
  
-   前に、新しく挿入されたノードを持つという**BillingAddress**です。  
  
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
  
-   複合基本型を使用した後**GlobalAddrType**をそのままです。  
  
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
  
## <a name="see-also"></a>参照  
 [複合グローバル型を使用する方法](../core/ways-to-use-complex-global-types.md)