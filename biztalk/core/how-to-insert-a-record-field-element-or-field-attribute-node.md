---
title: "レコード、フィールド要素、またはフィールド属性 ノードを挿入する方法 |Microsoft ドキュメント"
ms.custom: 
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: 
ms.suite: 
ms.tgt_pltfrm: 
ms.topic: article
ms.assetid: c26f2281-f1b8-4788-8593-8d6ad29a53f0
caps.latest.revision: "6"
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: 1341a0f2d89070d42620396a8c86d497b5d646ef
ms.sourcegitcommit: cb908c540d8f1a692d01dc8f313e16cb4b4e696d
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 09/20/2017
---
# <a name="how-to-insert-a-record-field-element-or-field-attribute-node"></a>レコード、フィールド要素、またはフィールド属性 ノードを挿入する方法
**レコード**ノード (など、**ルート**ノード)、**フィールド属性**ノード、および**フィールド要素**ノードは、一意な名前を変更できるように、名前は、対応するインスタンス メッセージに、カスタム名前付きの実際の要素の名前を表します。 たとえば、名前を付ける場合、**レコード**ノードに FullName という XML 要素が必要と、インスタンス メッセージ内の対応する位置に、FullName。 場合は、その**レコード**FullName という名前のノードが子**フィールド属性**RequireFullMiddleName という名前のノード (とその**Min Occurs**と**Max Occurs**プロパティに設定**1**) では、 **FullName**対応するインスタンス メッセージ内の要素をという名前の属性である必要があります**RequireFullMiddleName**関連付けられています。  
  
 すべて**レコード**最初に挿入すると、ノードは、XSD ので表されます、 **complexType**要素が、それ以降ではなく**シーケンス**、**選択肢**、または**すべて**要素。 このため、 **Group Order Type**、 **Group Max Occurs**、および**Group Min Occurs**のプロパティ、**レコード**ノードが利用できません。変更。  
  
 子を追加するとすぐに**レコード**または**フィールド要素**ノードを**レコード** ノード、**シーケンス**XSD には、要素を追加してください。内の表現、 **complexType**この最初の子ノードを格納する要素と**Group Order Type**のプロパティ、**レコード**ノードは値を示します**シーケンス**です。 ほとんどの状況で変更することができます、 **Group Order Type**プロパティから**シーケンス**に**選択肢**、および制限が多くの状況でから**シーケンス**に**すべて**これにより、いずれかに対応する子ノードを含む要素のペアを変更する**complexType/選択肢**または**complexType またはすべて**、それぞれします。  
  
 **フィールド属性**ノードは、同じスコープ内に重複したノード名を持つことはできません。  
  
 **レコード**と**フィールド要素**ノードは、次の条件が満たされた場合にのみ、同じスコープ内に重複したノード名を持つことができます。  
  
-   同じデータ型である。  
  
-   いない内、**すべてのグループ**ノード。  
  
### <a name="to-insert-a-new-child-record-node-field-element-node-or-field-attribute-node-within-the-schema-node-or-an-existing-record-node"></a>[スキーマ] ノードまたは既存の [レコード] ノード内に新しい子の [レコード] ノード、[フィールド要素] ノード、または [フィールド属性] ノードを挿入するには  
  
1.  選択、**スキーマ**ノードまたは既存**レコード**ノード。  
  
2.  **BizTalk**  メニューのをポイント**スキーマ ノードの挿入**、クリックして**子レコード**、**子フィールド要素**、または**子フィールド属性** をクリックします。  
  
    > [!NOTE]
    >  選択した型の子ノードが後に追加するか最後のノード、スキーマ ツリー内 (内に挿入するときに、**スキーマ**ノード) または既存最後の子ノードの選択した後に**レコード**ノード (場合内で、既存の挿入**レコード**ノード)。  
  
3.  新しく挿入されるの名前を入力**レコード**、**フィールド要素**、または**フィールド属性**ノード、および、ENTER キーを押します。  
  
### <a name="to-insert-a-sibling-record-node-field-attribute-node-or-field-element-node-within-an-existing-record-node"></a>既存の [レコード] ノード内に兄弟の [レコード] ノード、[フィールド属性] ノード、または [フィールド要素] ノードを挿入するには  
  
1.  子ノードを選択、**レコード**ノードの兄弟を挿入する**レコード**、**フィールド属性**、または**フィールド要素**ノードです。  
  
2.  **BizTalk**  メニューのをポイント**スキーマ ノードの挿入**、クリックして**兄弟レコード**、**兄弟フィールド属性**、または**兄弟フィールド要素** をクリックします。  
  
     選択された種類の兄弟ノードは、選択されたノードの兄弟の最後に挿入されます。  
  
3.  新しく挿入されるの名前を入力**レコード**、**フィールド属性**、または**フィールド要素**ノード、および、ENTER キーを押します。  
  
## <a name="see-also"></a>参照  
 [スキーマにノードを挿入](../core/inserting-nodes-into-a-schema.md)