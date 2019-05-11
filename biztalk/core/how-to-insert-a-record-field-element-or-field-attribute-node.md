---
title: レコード、フィールド要素、またはフィールド属性 ノードを挿入する方法 |Microsoft Docs
ms.custom: ''
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: ''
ms.suite: ''
ms.tgt_pltfrm: ''
ms.topic: article
ms.assetid: c26f2281-f1b8-4788-8593-8d6ad29a53f0
caps.latest.revision: 6
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: 8f63693877d9cfdc4cbb519515f64fd07a0e2510
ms.sourcegitcommit: 381e83d43796a345488d54b3f7413e11d56ad7be
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 05/07/2019
ms.locfileid: "65384938"
---
# <a name="how-to-insert-a-record-field-element-or-field-attribute-node"></a>レコード、フィールド要素、またはフィールド属性 ノードを挿入する方法
**レコード**ノード (など、**ルート**ノード)、**フィールド属性**ノード、および**フィールド要素**名前を変更することで、ノードが一意ようにの名前対応するインスタンス メッセージ内の実際、という名前のカスタム要素の名前を表します。 たとえば、名前を付ける場合、**レコード**ノードに FullName という XML 要素が必要です、インスタンス メッセージ内の対応する位置に、FullName。 その場合**レコード**FullName という名前のノードが子**フィールド属性**RequireFullMiddleName という名前のノード (とその**Min Occurs**と**Max Occurs**プロパティを設定**1**)、 **FullName**という名前の属性に対応するインスタンス メッセージ内の要素が必要があります**RequireFullMiddleName**関連付けられています。  
  
 すべて**レコード**XSD ので最初に挿入されるときに、ノードの表現、 **complexType**要素、それ以降ではなく**シーケンス**、**選択肢**、または**すべて**要素。 このため、 **Group Order Type**、 **Group Max Occurs**、および**Group Min Occurs**のプロパティ、**レコード**ノードは使用できません変更。  
  
 子を追加するとすぐに**レコード**または**フィールド要素**ノードを**レコード**ノード、**シーケンス**は xsd 要素を追加内の表現、 **complexType**この最初の子ノードを格納する要素と**Group Order Type**のプロパティ、**レコード**ノードには、値が表示されます。**シーケンス**します。 ほとんどの状況で変更することができます、 **Group Order Type**プロパティから**シーケンス**に**選択肢**、およびより限定的な状況から**シーケンス**に**すべて**ため、いずれかに対応する子ノードを含む要素のペアを変更する**complexType choice**または**complexType/すべて**、それぞれします。  
  
 **フィールド属性**ノードが同じスコープ内に同じノード名を含めることはできません。  
  
 **レコード**と**フィールド要素**次の条件が満たされた場合にのみ、ノードは、同じスコープ内に同じノード名には。  
  
-   同じデータ型があります。  
  
-   いない内、**すべてのグループ**ノード。  
  
### <a name="to-insert-a-new-child-record-node-field-element-node-or-field-attribute-node-within-the-schema-node-or-an-existing-record-node"></a>新しい子レコード ノード、フィールド要素 ノード、またはスキーマ ノードまたは既存のレコード ノード内でフィールド属性 ノードを挿入するには  
  
1.  選択、**スキーマ**ノードまたは既存**レコード**ノード。  
  
2.  **BizTalk**メニューで、**スキーマ ノードの挿入**、 をクリックし、**子レコード**、**子フィールド要素**、または**子フィールド属性**必要に応じて、します。  
  
    > [!NOTE]
    >  選択された種類の子ノードが追加後にいずれかの最後のノード スキーマ ツリーで (内で挿入するときに、**スキーマ**ノード) または選択した既存最後の子ノードの後に**レコード**ノード (場合内で、既存の挿入**レコード**ノード)。  
  
3.  新しく挿入の名前を入力**レコード**、**フィールド要素**、または**フィールド属性**ノード、および ENTER キーを押します。  
  
### <a name="to-insert-a-sibling-record-node-field-attribute-node-or-field-element-node-within-an-existing-record-node"></a>兄弟レコード ノード、フィールド属性 ノード、または既存のレコード ノード内でフィールド要素 ノードを挿入するには  
  
1.  子ノードを選択、**レコード**ノードの兄弟を挿入する**レコード**、**フィールド属性**、または**フィールド要素**ノードです。  
  
2.  **BizTalk**メニューで、**スキーマ ノードの挿入**、 をクリックし、**兄弟レコード**、**兄弟フィールド属性**、または**兄弟フィールド要素**必要に応じて、します。  
  
     選択された種類の兄弟ノードは、選択したノードの兄弟の最後に挿入されます。  
  
3.  新しく挿入の名前を入力**レコード**、**フィールド属性**、または**フィールド要素**ノード、および ENTER キーを押します。  
  
## <a name="see-also"></a>参照  
 [スキーマへのノードの挿入](../core/inserting-nodes-into-a-schema.md)