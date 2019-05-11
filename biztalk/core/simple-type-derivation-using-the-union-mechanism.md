---
title: ユニオン メカニズムを使用して単純型の派生 |Microsoft Docs
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
ms.openlocfilehash: 0b178b8ee6bf0e09877cc14ac72f30f569162166
ms.sourcegitcommit: 381e83d43796a345488d54b3f7413e11d56ad7be
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 05/07/2019
ms.locfileid: "65393047"
---
# <a name="simple-type-derivation-using-the-union-mechanism"></a>ユニオン メカニズムを使用して単純型の派生
ユニオン メカニズムを使用して、既存の単純型から新しい単純型を派生するときは、複数の型の属性または要素の値ができることを指定に従って、指定した種類の一覧はします。 たとえば、属性または要素の値は、日付、時刻、または日付/時刻値のいずれかを指定できます。  
  
 ユニオン メカニズムを使用して新しい単純型の派生について包括的な情報は、W3C web サイトを参照してください。 これと他の web サイトへのさまざまなリンクは、次を参照してください。 [Web 上の XSD リソース](../core/xsd-resources-on-the-web.md)します。  
  
 いくつかの使用可能な型の和集合として単純型を派生するには、関連する選択**フィールド要素**ノードまたは**フィールド属性**スキーマ ツリーおよびし、[プロパティ] ウィンドウのノードからの単純型を選択しますドロップダウン リスト、 **Base Data Type**プロパティ。 、このプロパティの値を選択するとすぐに、 **Derived By**プロパティが自動的に変更するには、その既定値から**制限**、派生した型の既定値として機能します。 変更する必要があります、 **Derived By**プロパティから**制限**に**共用体**、原因となる、 **Base Data Type**として名前を変更するプロパティ**メンバー型**プロパティ (名前が変更されたプロパティが移動のためのプロパティのアルファベット順の並べ替えプロパティの一覧で別の位置にちなみに、)。  
  
 最後に、チェック ボックスを使用することができます、**メンバー型**インスタンス メッセージ内の対応する値を許容するその他の種類を選択するドロップダウン チェックリスト。  
  
 変更すると、**フィールド要素**ノードまたは**フィールド属性**ノード (単純型の派生のプロセスを開始し)、基本データ型に入力し、を設定し、データがあることから**Derived By**プロパティを**共用体**、XSD ビューで対応するフラグメントでは、次の変更を確認できます。  
  
-   前に、新しく挿入で**フィールド要素**という名前のノード**DatesAndOrTimes**します。  
  
    ```  
    <xs:element name="ContainingRecord">  
        <xs:complexType>  
            <xs:sequence>  
  
            </xs:sequence>  
        </xs:complexType>  
    </xs:element>  
  
    ```  
  
-   設定した後、 **Base Data Type**プロパティを**xs:date**、および設定、 **Derived By**プロパティを**共用体**(その後、 **Base Data Type**プロパティの名前を変更する、**メンバー型**プロパティ) も選択して**xs:datetime**と**xs:time**として追加の許可の種類、**メンバー型**ドロップダウン チェックリスト。  
  
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