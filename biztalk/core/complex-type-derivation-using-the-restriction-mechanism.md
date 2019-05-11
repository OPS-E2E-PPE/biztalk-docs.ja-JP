---
title: 制約メカニズムを使用して複合型の派生 |Microsoft Docs
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
ms.openlocfilehash: a9b1b4234f4bb39da70f1e59719e1f145440a0b6
ms.sourcegitcommit: 381e83d43796a345488d54b3f7413e11d56ad7be
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 05/07/2019
ms.locfileid: "65356806"
---
# <a name="complex-type-derivation-using-the-restriction-mechanism"></a>制約メカニズムを使用して複合型の派生
制限による派生は、BizTalk エディターの機能では、拡張による派生と似ています。 制限による派生複合型は、基本データ型に似ていますが、その宣言は、基本データ型の宣言よりも制限。 実際には、新しい型で表される値は、(単純型の制約の場合と同様)、基本データ型によって表される値のサブセットです。 基本データ型の値として作成されるアプリケーションは、制限付きの型の値のいずれかを正常に処理できるはずです。  
  
 制約メカニズムを使用して、新しい複合型の派生について包括的な情報は、W3C web サイトを参照してください。 これと他の web サイトへのさまざまなリンクは、次を参照してください。 [Web 上の XSD リソース](../core/xsd-resources-on-the-web.md)します。  
  
 スキーマ ツリーの別の場所の制約機能によって複合グローバル型から派生する新しいを挿入することから始めます**レコード**目的の場所にあるノード。 設定し、その**Base Data Type**プロパティを複合グローバル型の名前にします。 設定が最後に、変更、 **Derived By**プロパティの既定値から**拡張子**(少なくとも基本データ型を設定されている場合) に**制限**します。  
  
 次の例では、 **BillingAddress**新しく挿入の名前を指定**レコード**ノード、および**GlobalAddrType**元である場合は、複合グローバル型の名前を指定します派生元および制限します。 という名前のノードの下で、スキーマ ツリー ビューでは、重複するノード構造が表示されます**BillingAddress**という名前のノードの下の隣接するノード構造と同じ、 **ShippingAddress**します。 これらの相違点は、 **BillingAddress**されるノードの構造は基本データ型に対する制約が**GlobalAddrType**、および**ShippingAddress**構造は常に同じ基本データ型に**GlobalAddrType**します。  
  
 基本データ型を制限することを選択してため、新しいノードを挿入することはできませんが、さらに、使用可能な値や動作を制限する既存のノードのプロパティを変更することができます。  
  
-   前に、使用、 **Derived By**プロパティに設定**拡張子**。  
  
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
  
-   切り替え後、 **Derived By**プロパティから**拡張子**に**制限**します。  
  
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