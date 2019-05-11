---
title: リスト メカニズムを使用して単純型の派生 |Microsoft Docs
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
ms.openlocfilehash: 318a58f0e0f1aed836bdf7a866a42c7df3941b9a
ms.sourcegitcommit: 381e83d43796a345488d54b3f7413e11d56ad7be
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 05/07/2019
ms.locfileid: "65393159"
---
# <a name="simple-type-derivation-using-the-list-mechanism"></a>リスト メカニズムを使用して単純型の派生
リスト メカニズムを使用して、既存の単純型から新しい単純型を派生するとき、この属性または要素の値は、指定した型の値のスペースで区切られたリストであることが指定されます。 たとえば、属性または要素の値が空白で区切られた整数のリストを指定できます。  
  
 リスト メカニズムを使用して新しい単純型の派生について包括的な情報は、W3C Web サイトを参照してください。 これと他の Web サイトへのさまざまなリンクは、次を参照してください。 [Web 上の XSD リソース](../core/xsd-resources-on-the-web.md)します。  
  
 その型の一覧として単純型を派生するには、関連する選択**フィールド要素**ノードまたは**フィールド属性**ノードをスキーマ ツリーにし、[プロパティ] ウィンドウで、ドロップダウン リストから単純型を選択します一覧表示、 **Base Data Type**プロパティ。 このプロパティの値を選択するとすぐに、 **Derived By**プロパティが自動的に変更するには、その既定値から**制限**、派生した型の既定値として使用されます。 変更する必要があります、 **Derived By**プロパティから**制限**に**一覧**、原因となる、 **Base Data Type**として名前を変更するプロパティ**項目の種類**プロパティ (名前が変更されたプロパティが移動のためのプロパティのアルファベット順の並べ替えプロパティの一覧で別の位置にちなみに、)。  
  
> [!NOTE]
>  制限を使用してリスト メカニズムを同時に、作成するには、名前付きの単純型の派生を制限メカニズムを使用して、アイテムとして使用しているリスト メカニズムを使用して、もう 1 つの単純型の派生の型。 これにより、たとえば、特定の列挙された文字列のセットに属しているスペースで区切られた文字列の一覧に制約される値。  
  
> [!CAUTION]
>  リスト メカニズムを使用して、単純型の派生は複雑になるときに、文字列などの空白文字を許可する 1 つを選択した項目の種類。 リスト メカニズムの一覧で許可されている型の値を区切るスペースを使用するためです。  
  
 変更すると、**フィールド要素**ノードまたは**フィールド属性**ノード (単純型の派生のプロセスを開始し)、基本データ型に入力し、を設定し、データがあることから**Derived By**プロパティを**一覧**、XSD ビューで対応するフラグメントでは、次の変更を確認できます。  
  
-   前に、新しく挿入で**フィールド要素**という名前のノード **"zipcodelist"** します。  
  
    ```  
    <xs:element name="ContainingRecord">  
        <xs:complexType>  
            <xs:sequence>  
                <xs:element name="ZipCodeList" type="xs:string" />  
            </xs:sequence>  
        </xs:complexType>  
    </xs:element>  
  
    ```  
  
-   設定した後、 **Base Data Type**プロパティを xs:integer に設定、 **Derived By**プロパティを**一覧**(その後、 **Base Data Type**プロパティの名前を変更する、**項目の種類**プロパティ)。  
  
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
>  実際のスキーマで最初に定義し、5 桁の整数を制限する整数の単純型の派生を名前になり、派生する、 **"zipcodelist"** に一覧を効果的に制限すること、その型から要素5 桁の整数。  
  
## <a name="see-also"></a>参照  
 [単純型の派生](../core/simple-type-derivation.md)