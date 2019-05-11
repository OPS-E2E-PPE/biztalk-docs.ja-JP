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
# <a name="complex-global-type-re-use"></a>複合グローバル型を再利用
使用する、複雑なグローバル型は、スキーマ ツリーの別の場所で開始新しいを挿入して**レコード**目的の場所にあるノード。 設定し、その**Data Structure Type**プロパティを複合グローバル型の名前にします。  
  
 次の例では、 **BillingAddress**新しく挿入の名前を指定**レコード**ノード、および**GlobalAddrType**これを採用する複合グローバル型の名前を指定します。 という名前のノードの下で、スキーマ ツリー ビューでは、重複するノード構造が表示されます**BillingAddress**という名前のノードの下の隣接するノード構造と同じ、 **ShippingAddress**します。  
  
-   前に、新しく挿入されたノードを持つという**BillingAddress**します。  
  
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
  
-   複合基本型を使用した後**GlobalAddrType**などです。  
  
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
 [複合グローバル型の使用方法](../core/ways-to-use-complex-global-types.md)