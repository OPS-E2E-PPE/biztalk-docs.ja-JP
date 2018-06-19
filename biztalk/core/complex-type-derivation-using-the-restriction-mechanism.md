---
title: 制約メカニズムを使用する複合型の派生 |Microsoft ドキュメント
ms.custom: ''
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: ''
ms.suite: ''
ms.tgt_pltfrm: ''
ms.topic: article
ms.assetid: c3003d88-6b75-4dcb-834f-1babcf7449cb
caps.latest.revision: 7
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: ddbd9d8266d9c289b9b4bae9dd7060906e01ebd7
ms.sourcegitcommit: cb908c540d8f1a692d01dc8f313e16cb4b4e696d
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 09/20/2017
ms.locfileid: "22233482"
---
# <a name="complex-type-derivation-using-the-restriction-mechanism"></a>制約メカニズムを使用した複合型の派生
制約による派生は、BizTalk エディターの機能では、拡張による派生と類似しています。 制約機能によって派生した複合型は、基本データ型と似ています。ただし、基本データ型の宣言よりも複合型の宣言の方が制限が多くあります。 実際には、新しい型で表される値は、単純型の制約と同様に、基本データ型で表される値のサブセットです。 基本データ型の値を対象として作成されるアプリケーションには、制限された型の任意の値を正常に処理する機能が必要になります。  
  
 制約メカニズムを使用して新規の複合型を派生する方法の概要については、W3C Web サイトを参照してください。 これを他の web サイトのさまざまなリンクは、次を参照してください。 [Web 上の XSD リソース](../core/xsd-resources-on-the-web.md)です。  
  
 スキーマ ツリーで、別の場所での制限によって複合グローバル型から派生する新しい挿入することによって開始**レコード**目的の場所にあるノード。 設定し、その**Base Data Type**プロパティ、複合グローバル型の名前にします。 最後の設定を変更、 **Derived By**プロパティの既定値から**拡張子**(少なくとも基本データ型設定されている場合) に**制限**です。  
  
 次の例では、 **BillingAddress**新しく挿入されるの名前を指定**レコード**ノード、および**GlobalAddrType**元である場合は、複合グローバル型の名前を指定します派生元およびを制限します。 名前付きノードの下に、スキーマ ツリー ビューで、重複するノード構造が表示されます**BillingAddress**、という名前のノードの下にある隣接するノード構造と同一**ShippingAddress**です。 これらの違いは、 **BillingAddress**されるノードの構造は基本データ型に対する制約が**GlobalAddrType**、および**ShippingAddress**構造は常に同じ基本データ型に**GlobalAddrType**です。  
  
 基本データ型を制限すると、新しいノードを挿入できません。ただし、既存のノードのプロパティを変更すると、指定できる値または動作をさらに制限できます。  
  
-   前で、 **Derived By**にプロパティがまだ設定**拡張子**です。  
  
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
  
-   切り替え後、 **Derived By**プロパティから**拡張子**に**制限**です。  
  
    ```  
    <xs:schema>  
        <xs:element name="Root">  
            <xs:complexType>  
                <xs:sequence>  
                    <xs:element name="ShippingAddress" type="GlobalAddrType" />  
                    <xs:element name="BillingAddress">  
                        <xs:complexType>  
                            <xs:complexContent mixed="false">  
                                <xs:restriction base="GlobalAddrType">  
                   [Duplicate of address structure now appears  
                   here, ready to be restricted with additional  
                   attributes, set using the properties of the  
                   relevant nodes in the schema tree.]  
                                </xs:restriction>  
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
  
## <a name="see-also"></a>参照  
 [複合グローバル型の派生](../core/complex-global-type-derivation.md)