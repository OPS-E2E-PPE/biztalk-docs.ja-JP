---
title: "既存のレコード、フィールド要素、またはフィールド属性 ノードの新しいインスタンスを作成する方法 |Microsoft ドキュメント"
ms.custom: 
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: 
ms.suite: 
ms.tgt_pltfrm: 
ms.topic: article
ms.assetid: 02380f68-056c-47c4-a0d6-61d599a4685d
caps.latest.revision: "6"
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: 64f8974de22b7ee99a02d551553cb5e36f31a0d9
ms.sourcegitcommit: cb908c540d8f1a692d01dc8f313e16cb4b4e696d
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 09/20/2017
---
# <a name="how-to-create-a-new-occurrence-of-an-existing-record-field-element-or-field-attribute-node"></a>既存のレコード、フィールド要素、またはフィールド属性 ノードの新しいインスタンスを作成する方法
既存の新しいインスタンスを作成する**レコード**、**フィールド要素**、または**フィールド属性**ノードすべてに任意のインスタンスに対して行った変更が反映されるようインスタンス。  
  
### <a name="to-create-a-new-instance-of-an-existing-record-field-element-or-field-attribute-node"></a>既存の[レコード] ノード、[フィールド要素] ノード、または[フィールド属性] ノードの新しいインスタンスを作成するには  
  
1.  元の選択**レコード**、**フィールド要素**、または**フィールド属性**ノード、ことを確認、 **Base Data Type**プロパティが正しく設定その**Data Structure Type** (**レコード**ノード) またはその**データ型**(**フィールド要素**と**フィールド属性**ノード) プロパティ、カスタム データ型の名前を入力します。  
  
2.  新しい挿入**レコード**、**フィールド要素**、または**フィールド属性**ノードとカスタム データを次のプロパティのいずれかのセットは、手順 1. で入力した名前を入力します。  
  
    -   Data Structure Type (**レコード**ノード)  
  
    -   データ型 (**フィールド要素**と**フィールド属性**ノード)  
  
    > [!NOTE]
    >  場合、新しい**レコード**または**フィールド要素**ノードは、元のノードの兄弟、新しいノードに、元のノードと同じ名前を付けると、同じスコープ内で重複するノードについて確認するメッセージ ボックスが表示されます同じ名前です。 クリックすると**はい**手順 2. でカスタム データ型の名前を選択すると、同じ処理を実行します。  
  
> [!NOTE]
>  既存の新しいインスタンスを作成した**レコード**、**フィールド要素**、または**フィールド属性**ノード。  
  
> [!NOTE]
>  一部のプロパティの**レコード**、**フィールド要素**、または**フィールド属性**ノード インスタンスが同じままになります (1 つのインスタンスへの変更がすべてのインスタンスへの変更)、およびその他のプロパティは、インスタンスごとに個別に設定できます。  
  
## <a name="see-also"></a>参照  
 [スキーマにノードを挿入](../core/inserting-nodes-into-a-schema.md)