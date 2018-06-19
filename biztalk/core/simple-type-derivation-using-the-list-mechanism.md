---
title: リスト メカニズムを使用した単純型の派生 |Microsoft ドキュメント
ms.custom: ''
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: ''
ms.suite: ''
ms.tgt_pltfrm: ''
ms.topic: article
ms.assetid: 14f3c7b7-7585-4297-9177-2deaef8355f0
caps.latest.revision: 8
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: aafc6a540e9595f426858bc16fedfb1f8fe0bc8f
ms.sourcegitcommit: cb908c540d8f1a692d01dc8f313e16cb4b4e696d
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 09/20/2017
ms.locfileid: "22270962"
---
# <a name="simple-type-derivation-using-the-list-mechanism"></a>リスト メカニズムを使用した単純型の派生
リスト メカニズムを使用して既存の単純型から新しい単純型を派生させる場合、この型の属性や要素の値を、空白で区切られた一覧として指定できます。この一覧には、指定された型の値が示されます。 たとえば、属性または要素の値を、整数型の値が示される空白区切りの一覧として指定できます。  
  
 リスト メカニズムを使用して新しい単純型を派生する場合の概要については、W3C Web サイトを参照してください。 これを他の Web サイトのさまざまなリンクは、次を参照してください。 [Web 上の XSD リソース](../core/xsd-resources-on-the-web.md)です。  
  
 その型の一覧として単純型を派生するには、関連する選択**フィールド要素**ノードまたは**フィールド属性**スキーマ ツリーでおよびその後、[プロパティ] ウィンドウのノードは、ドロップダウン リストから単純型を選択一覧表示、 **Base Data Type**プロパティです。 このプロパティの値を選択するとすぐに、 **Derived By**プロパティが自動的に変更するには、その既定値から**制限**、派生した型の既定値として機能します。 変更する必要があります、 **Derived By**プロパティから**制限**に**リスト**、これにより、 **Base Data Type**として名前を変更するプロパティ**項目の種類**プロパティ (ちなみに、名前が変更されたプロパティに移動、プロパティ リストのプロパティのアルファベット順の並べ替えのための別の位置)。  
  
> [!NOTE]
>  制約メカニズムとリスト メカニズムを一緒に使用できます。制約メカニズムを使用して、名前付きの単純型の派生を作成し、さらにリスト メカニズムを使用して、作成した派生を別の単純型の派生内で項目の種類として使用できます。 これにより、空白で区切られた文字列の一覧に強制的に含まれる値などが発生します。この一覧には、特定の文字列のセットが列挙されます。  
  
> [!CAUTION]
>  単純型の派生にリスト メカニズムを使用すると、選択した項目の種類が文字列などの空白文字を許可する場合に、複雑になる可能性があります。 このため、リスト メカニズムは、空白文字を使用して、一覧で許可されている型の値を区切ります。  
  
 変更すると、**フィールド要素**ノードまたは**フィールド属性**ノード (単純型の派生のプロセスを開始し)、基本データ型を持つように入力して、を設定してデータを持つから**Derived By**プロパティを**一覧**、XSD ビューの対応するフラグメントで、次の変更を確認することができます。  
  
-   前に、新しく挿入されると**フィールド要素**という名前のノード **"zipcodelist"** です。  
  
    ```  
    <xs:element name="ContainingRecord">  
        <xs:complexType>  
            <xs:sequence>  
                <xs:element name="ZipCodeList" type="xs:string" />  
            </xs:sequence>  
        </xs:complexType>  
    </xs:element>  
  
    ```  
  
-   設定した後、 **Base Data Type** xs:integer、および設定するプロパティ、 **Derived By**プロパティを**リスト**(その後、 **Base Data Type**プロパティの名前を変更する、**項目の種類**プロパティ)。  
  
    ```  
    <xs:element name="ContainingRecord">  
        <xs:complexType>  
            <xs:sequence>  
                <xs:element name="ZipCodeList">  
                    <xs:simpleType>  
               <xs:list itemType="xs:integer" />   
                       </xs:simpleType>  
                </xs:element>  
            </xs:sequence>  
        </xs:complexType>  
    </xs:element>  
  
    ```  
  
> [!NOTE]
>  実際のスキーマがあります最初を定義し、名前を 5 桁の数値を整数に制限する整数の単純型から派生する方がよいとその派生するために、 **"zipcodelist"** にリストを効果的に制限する、その型から要素5 桁の数字を持つ整数。  
  
## <a name="see-also"></a>参照  
 [単純型の派生](../core/simple-type-derivation.md)