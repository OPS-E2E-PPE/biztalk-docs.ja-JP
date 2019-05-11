---
title: 制約メカニズムを使用して単純型の派生 |Microsoft Docs
ms.custom: ''
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: ''
ms.suite: ''
ms.tgt_pltfrm: ''
ms.topic: article
ms.assetid: e4ca712e-9563-4917-9bfc-1033a36773e8
caps.latest.revision: 7
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: 46cfded2bd9995e99972108f46aa53c883fffc99
ms.sourcegitcommit: 381e83d43796a345488d54b3f7413e11d56ad7be
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 05/07/2019
ms.locfileid: "65393069"
---
# <a name="simple-type-derivation-using-the-restriction-mechanism"></a>制約メカニズムを使用して単純型の派生

## <a name="overview"></a>概要
制約メカニズムを使用して、既存の単純型から新しい単純型を派生するときは、基本の単純型で許容された値のサブセットにその属性または要素の値のインスタンス メッセージで使用できる値を制限している通常します。 たとえば、いくつかの列挙された文字列のいずれかを指定する文字列型を制限できます。  
  
 制約メカニズムを使用して新しい単純型の派生について包括的な情報は、W3C web サイトを参照してください。 これと他の web サイトへのさまざまなリンクは、次を参照してください。 [Web 上の XSD リソース](../core/xsd-resources-on-the-web.md)します。  
  
## <a name="field-element-and-field-attribute"></a>フィールド要素とフィールド属性
 制限を使用して単純型を派生するには、関連する選択**フィールド要素**ノードまたは**フィールド属性**ノードをスキーマ ツリーにし、[プロパティ] ウィンドウで、ドロップダウン リストから単純型を選択します一覧表示、 **Base Data Type**プロパティ。 、このプロパティの値を選択するとすぐに、 **Derived By**プロパティが自動的に変更するには、その既定値から**制限**、派生した型の既定値として機能します。 という名前のプロパティのまったく新しいカテゴリではまた、**制限**、[プロパティ] ウィンドウに表示されます。  
  
 選択した基本データ型によっては、さまざまなプロパティはこの新しいカテゴリで設定できます。 たとえば、基本データ型が数値でプロパティ**MaxFacet Type** (と**MaxFacet Value**設定されている)、 **MaxFacet Value**、 **MinFacet Type**(と**MinFacet Value**設定されている)、および**MinFacet Value**の値の許容の包含または除外範囲の定義に使用します。 基本データ型が文字列型の場合、**長さ**、**最大長**、および**長さ**プロパティは、文字列の長さの制限値を使用できます。  
  
 [フィールド] ノードの各種制約プロパティの詳細については、次を参照してください。、**フィールド要素 ノード プロパティ**[!INCLUDE[ui-guidance-developers-reference](../includes/ui-guidance-developers-reference.md)]します。
  
 変更すると、**フィールド要素**ノードまたは**フィールド属性**から基本データ型 (単純型の派生のプロセスを開始し) のままにするデータ型を持つノード、 **派生して**プロパティに設定**制限**、および文字列の最大値に列挙ベースの制限を提供、XSD ビューで対応するフラグメントで次の変更を確認できます。  
  
-   前に、新しく挿入で**フィールド要素**という名前のノード**WestCoastStates**します。  
  
    ```  
    <xs:element name="ContainingRecord">  
        <xs:complexType>  
            <xs:sequence>  
                <xs:element name="WestCoastStates" type="xs:string" />  
            </xs:sequence>  
        </xs:complexType>  
    </xs:element>  
    ```  
  
-   設定した後、 **Base Data Type**プロパティを"xs:string"し、既定値のままにして**制限**の**Derived By**プロパティ。  
  
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
  
-   設定した後、**列挙**米国本土西海岸の 3 つの状態の名前に Restriction カテゴリのプロパティ。  
  
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