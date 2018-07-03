---
title: 拡張機能のメカニズムを使用して複合型の派生 |Microsoft Docs
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
ms.openlocfilehash: 2addaf540407c7b899cc81a7512fead9bb205ad5
ms.sourcegitcommit: 266308ec5c6a9d8d80ff298ee6051b4843c5d626
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 06/27/2018
ms.locfileid: "37022232"
---
# <a name="complex-type-derivation-using-the-extension-mechanism"></a>拡張メカニズムを使用した複合型の派生
拡張機能によって派生する複合型は、基本データ型の機能的なスーパーセットです。 名前が示すように、基本データ型に基づいて、拡張する型を定義します。 このトピックでは、2 つの要素**ShippingAddress**と**BillingAddress**複合グローバル型に基づきます**GlobalAddrType**します。 **ShippingAddress**に型の定義は**GlobalAddrType**であるのに対し**BillingAddress**型を拡張するように定義**GlobalAddrType**します。 別の要素を追加の例では、最後に、 **BillingAddress**、名前付き**部門**文字列型および Accounts Payable の既定値を指定しています。  
  
 拡張メカニズムを使用して新規の複合型を派生させる情報の概要については、W3C Web サイトを参照してください。 これと他の web サイトへのさまざまなリンクは、次を参照してください。 [Web 上の XSD リソース](../core/xsd-resources-on-the-web.md)します。  
  
 スキーマ ツリーの別の場所での拡張機能によって複合グローバル型から派生する新しい挿入することで開始**レコード**目的の場所にあるノード。 設定し、その**Base Data Type**プロパティを複合グローバル型の名前にします。  
  
 次の例では、 **BillingAddress**新しく挿入の名前を指定**レコード**ノード、および**GlobalAddrType**元である場合は、複合グローバル型の名前を指定します派生元および拡張します。 スキーマ ツリー ビューで後**Base Data Type**に設定されている**GlobalAddrType**、重複するノード構造がという名前のノードの下に表示**BillingAddress**、という名前のノードの下の隣接するノード構造と同じ**ShippingAddress**します。 これらの相違点は、 **BillingAddress**されるノードの構造は基本データ型よりも拡張可能な**GlobalAddrType**、および**ShippingAddress**構造体を基本データ型と同じままになります**GlobalAddrType**します。  
  
- 前に、新しく挿入されたノードを持つという**BillingAddress**します。  
  
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
  
- 複合基本型から派生させた後**GlobalAddrType**、拡張機能で。  
  
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
  
  ノードを挿入して拡張機能を基本データ型を指定する、 **BillingAddress**スキーマ ツリー内のノード。 次の XSD フラグメントは、ときに空の拡張機能の要素が展開された方法を示しています、**シーケンス グループ**の新しい子ノードを挿入、 **BillingAddress**ノードをクリックし、**フィールド要素**という名前のノード**PaymentType**の子ノードとして挿入されます、**シーケンス グループ**ノード。  
  
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