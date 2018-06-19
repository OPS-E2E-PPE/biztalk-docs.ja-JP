---
title: ユニオン メカニズムを使用した単純型派生 |Microsoft ドキュメント
ms.custom: ''
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: ''
ms.suite: ''
ms.tgt_pltfrm: ''
ms.topic: article
ms.assetid: e51ae390-78f5-4fb9-9163-2a8023aea1ec
caps.latest.revision: 6
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: 1414fa506f824415de8e8449e8b2b27befd2fc76
ms.sourcegitcommit: cb908c540d8f1a692d01dc8f313e16cb4b4e696d
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 09/20/2017
ms.locfileid: "22270378"
---
# <a name="simple-type-derivation-using-the-union-mechanism"></a>ユニオン メカニズムを使用した単純型の派生
ユニオン メカニズムを使用して既存の単純型から新しい単純型を派生させる場合、一連の型を指定することにより、対応する属性または要素の値に対し、複数の型を割り当てることができます。 たとえば、1 つの属性または要素に対して、日付、時刻、日付/時刻のすべての型を割り当てることができます。  
  
 ユニオン メカニズムを使用して新しい単純型を派生させる方法の概要については、W3C Web サイトを参照してください。 これを他の web サイトのさまざまなリンクは、次を参照してください。 [Web 上の XSD リソース](../core/xsd-resources-on-the-web.md)です。  
  
 いくつかの使用可能な型のユニオンとして単純型を派生させるするには、関連する選択**フィールド要素**ノードまたは**フィールド属性**スキーマ ツリーでおよびその後、[プロパティ] ウィンドウのノードから単純型の選択ドロップダウン リスト、 **Base Data Type**プロパティです。 このプロパティの値を選択するとすぐに、 **Derived By**プロパティが自動的に変更するには、その既定値から**制限**、派生した型の既定値として機能します。 変更する必要があります、 **Derived By**プロパティから**制限**に**共用体**、これにより、 **Base Data Type**として名前を変更するプロパティ**Member Types**プロパティ (ちなみに、名前が変更されたプロパティに移動、プロパティ リストのプロパティのアルファベット順の並べ替えのための別の位置)。  
  
 最後に、チェック ボックスを使用して、**メンバーの種類**ドロップダウン チェックリストをインスタンス メッセージ内の対応する値を許容するその他の種類を選択します。  
  
 変更すると、**フィールド要素**ノードまたは**フィールド属性**ノード (単純型の派生のプロセスを開始し)、基本データ型を持つように入力して、を設定してデータを持つから**Derived By**プロパティを**共用体**、XSD ビューの対応するフラグメントで、次の変更を確認することができます。  
  
-   前に、新しく挿入されると**フィールド要素**という名前のノード**DatesAndOrTimes**です。  
  
    ```  
    <xs:element name="ContainingRecord">  
        <xs:complexType>  
            <xs:sequence>  
  
            </xs:sequence>  
        </xs:complexType>  
    </xs:element>  
  
    ```  
  
-   設定した後、 **Base Data Type**プロパティを**xs:date**、および設定、 **Derived By**プロパティを**共用体**(その後、 **Base Data Type**プロパティの名前を変更する、 **Member Types**プロパティ) も選択して**xs:datetime**と**xs:time**として追加の許可されている型で、 **Member Types**ドロップダウン チェックリストです。  
  
    ```  
    <xs:element name="ContainingRecord">  
        <xs:complexType>  
            <xs:sequence>  
  
            </xs:sequence>  
        </xs:complexType>  
    </xs:element>  
  
    ```  
  
## <a name="see-also"></a>参照  
 [単純型の派生](../core/simple-type-derivation.md)