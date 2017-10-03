---
title: "制約メカニズムを使用した単純型派生 |Microsoft ドキュメント"
ms.custom: 
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: 
ms.suite: 
ms.tgt_pltfrm: 
ms.topic: article
ms.assetid: e4ca712e-9563-4917-9bfc-1033a36773e8
caps.latest.revision: "7"
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: dda4b8ad64f1edf262446f1633eda109ba7074ec
ms.sourcegitcommit: cb908c540d8f1a692d01dc8f313e16cb4b4e696d
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 09/20/2017
---
# <a name="simple-type-derivation-using-the-restriction-mechanism"></a>制約メカニズムを使用した単純型の派生

## <a name="overview"></a>概要
制約メカニズムを使用して既存の単純型から新しい単純型を派生させる場合、インスタンス メッセージの属性値または要素値に使用できる値を、基本単純型で許容された値のサブセットに制限するのが一般的です。 たとえば、文字列型は、複数の列挙文字列のいずれかに制限できます。  
  
 制約メカニズムを使用して新規の単純型を派生させる方法の概要については、W3C Web サイトを参照してください。 これを他の web サイトのさまざまなリンクは、次を参照してください。 [Web 上の XSD リソース](../core/xsd-resources-on-the-web.md)です。  
  
## <a name="field-element-and-field-attribute"></a>Field 要素とフィールド属性
 制限を使用して単純型を派生するには、関連する選択**フィールド要素**ノードまたは**フィールド属性**スキーマ ツリーでおよびその後、[プロパティ] ウィンドウのノードは、ドロップダウン リストから単純型を選択一覧表示、 **Base Data Type**プロパティです。 このプロパティの値を選択するとすぐに、 **Derived By**プロパティが自動的に変更するには、その既定値から**制限**、派生した型の既定値として機能します。 呼ばれるプロパティのまったく新しいカテゴリも、**制限**、プロパティ ウィンドウで使用可能になります。  
  
 この新しいカテゴリで設定できるプロパティは、選択した基本データ型によって異なります。 たとえば、基本データ型が数値の場合、プロパティ**MaxFacet Type** (ときに**MaxFacet Value**設定されている)、 **MaxFacet Value**、 **MinFacet Type**(ときに**MinFacet Value**設定されている)、および**MinFacet Value**値の許容包含または排他範囲の定義に使用できます。 基本データ型が文字列型の場合、**長さ**、**最大長**、および**最小の長さ**プロパティは、文字列の長さの制限値を使用できます。  
  
 [フィールド] ノードの各種制約プロパティの詳細については、次を参照してください。、**フィールド要素 ノード プロパティ**[!INCLUDE[ui-guidance-developers-reference](../includes/ui-guidance-developers-reference.md)]です。
  
 変更すると、**フィールド要素**ノードまたは**フィールド属性**から基本データ型 (単純型の派生のプロセスを開始し) のままにするデータ型を持つノード、 **Derived によって**プロパティに設定**制限**文字列の最大値に、列挙ベースの制限を指定して、XSD ビューの対応するフラグメントでは、次の変更を確認することができます。  
  
-   前に、新しく挿入されると**フィールド要素**という名前のノード**WestCoastStates**です。  
  
    ```  
    <xs:element name="ContainingRecord">  
        <xs:complexType>  
            <xs:sequence>  
                <xs:element name="WestCoastStates" type="xs:string" />  
            </xs:sequence>  
        </xs:complexType>  
    </xs:element>  
    ```  
  
-   設定した後、 **Base Data Type**プロパティを"xs:string"し、既定値のままにして**制限**の**Derived By**プロパティです。  
  
    ```  
    <xs:element name="ContainingRecord">  
        <xs:complexType>  
            <xs:sequence>  
                <xs:element name="WestCoastStates" >  
                    <xs:simpleType>  
                        <xs:restriction base="xs:string" />  
                    </xs:simpleType>  
                </xs:element>  
            </xs:sequence>  
        </xs:complexType>  
    </xs:element>  
    ```  
  
-   設定した後、**列挙**米国本土の西海岸の 3 つの状態の名前を Restriction カテゴリのプロパティです。  
  
    ```  
    <xs:element name="ContainingRecord">  
        <xs:complexType>  
            <xs:sequence>  
                <xs:element name="WestCoastStates">  
                    <xs:simpleType>  
                        <xs:restriction base="xs:string" />  
                            <xs:enumeration value="Washington" />  
                            <xs:enumeration value="Oregon" />  
                            <xs:enumeration value="California" />  
                        </xs:restriction>  
                    </xs:simpleType>  
                </xs:element>  
            </xs:sequence>  
        </xs:complexType>  
    </xs:element>  
    ```  
  
## <a name="see-also"></a>参照  
 [単純型の派生](../core/simple-type-derivation.md)