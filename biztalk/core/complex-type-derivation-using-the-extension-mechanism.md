---
title: 拡張メカニズムを使用する複合型の派生 |Microsoft ドキュメント
ms.custom: ''
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: ''
ms.suite: ''
ms.tgt_pltfrm: ''
ms.topic: article
ms.assetid: 7125fb5b-f77a-47c9-8000-f2332940df89
caps.latest.revision: 7
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: c5d36778b5ad99a0273e6199f59bdd337429a74b
ms.sourcegitcommit: 36350889f318e1f7e0ac9506dc8df794d475bda6
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 04/20/2018
---
# <a name="complex-type-derivation-using-the-extension-mechanism"></a>拡張メカニズムを使用した複合型の派生
拡張機能によって派生する複合型は、基本データ型の機能的なスーパーセットです。 名前が示すように、基本データ型に基づいて、拡張する型を定義します。 このトピックでは、2 つの要素 **ShippingAddress** と **BillingAddress** 複合グローバル型に基づきます **GlobalAddrType**します。 **ShippingAddress** だけで定義されている型の **GlobalAddrType**, であるのに対し **BillingAddress** 型を拡張する定義 **GlobalAddrType**します。 別の要素を追加の例では、最後に **BillingAddress**, 、名前付き **部門**, 文字列型および Accounts Payable の既定値を指定しています。  
  
 拡張メカニズムを使用して新規の複合型を派生させる情報の概要については、W3C Web サイトを参照してください。 これを他の web サイトのさまざまなリンクは、次を参照してください。 [Web 上の XSD リソース](../core/xsd-resources-on-the-web.md)です。  
  
 スキーマ ツリーの別の場所での拡張機能によって複合グローバル型から派生させるのには、新しいを挿入して開始 **レコード** 目的の場所にあるノードです。 設定し、その **Base Data Type** プロパティを複合グローバル型の名前にします。  
  
 次の例で **BillingAddress** 、新たに挿入の名前を指定 **レコード** ノード、および **GlobalAddrType** 元となる、派生元および拡張する複合グローバル型の名前を指定します。 スキーマ ツリー ビューで後 **Base Data Type** に設定されている **GlobalAddrType**, 、重複するノード構造はという名前のノードの下に表示されます **BillingAddress**, という名前のノードを使用して、隣接するノード構造と同じ、 **ShippingAddress**します。 これらの違いは、 **BillingAddress** ノード構造は基本データ型から拡張でき、 **GlobalAddrType**, 、および **ShippingAddress** 構造は常に同じ基本データ型に **GlobalAddrType**します。  
  
-   前に、新しく挿入されたノードと名前付き **BillingAddress**します。  
  
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
  
-   複合基本型から派生させた後 **GlobalAddrType**, 、拡張機能でします。  
  
    ```  
    <xs:schema>  
        <xs:element name="Root">  
            <xs:complexType>  
                <xs:sequence>  
                    <xs:element name="ShippingAddress" type="GlobalAddrType" />  
                    <xs:element name="BillingAddress">  
                        <xs:complexType>  
                            <xs:complexContent mixed="false">  
                                <xs:extension base="GlobalAddrType" />  
                            </xs:complexContent>  
                        </xs:complexType>  
                    </xs:element>  
                </xs:sequence>  
            </xs:complexType>  
        </xs:element>  
        <xs:complexType name="GlobalAddrType">  
        [Address structure defined globally here.]   
        </xs:complexType>  
    </xs:schema>  
    ```  
  
 ノードを挿入して拡張機能を基本データ型を指定する、 **BillingAddress** スキーマ ツリー内のノードです。 次の XSD フラグメントは、ときに空の拡張機能の要素が展開された方法を示しています、 **シーケンス グループ** の新しい子ノードが挿入される、 **BillingAddress** ノードし、 **フィールド要素** という名前のノード **PaymentType**, の子ノードとして挿入、 **シーケンス グループ** ノードです。  
  
```  
<xs:extension base="GlobalAddrType">  
    <xs:sequence>  
        <xs:element default="Accounts Payable"  
            name="Department" type="xs:string" />  
    </xs:sequence>  
</xs:extension>  
```  
  
## <a name="see-also"></a>参照  
 [複合グローバル型の派生](../core/complex-global-type-derivation.md)