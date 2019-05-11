---
title: 既存のレコード、フィールド要素、またはフィールド属性 ノードの新しいインスタンスを作成する方法 |Microsoft Docs
ms.custom: ''
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: ''
ms.suite: ''
ms.tgt_pltfrm: ''
ms.topic: article
ms.assetid: 02380f68-056c-47c4-a0d6-61d599a4685d
caps.latest.revision: 6
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: c7a4e1992bf10ccd51feb69919ecc17a3c5db323
ms.sourcegitcommit: 381e83d43796a345488d54b3f7413e11d56ad7be
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 05/07/2019
ms.locfileid: "65390133"
---
# <a name="how-to-create-a-new-occurrence-of-an-existing-record-field-element-or-field-attribute-node"></a>既存のレコード、フィールド要素、またはフィールド属性 ノードの新しいインスタンスを作成する方法
既存の新しいインスタンスを作成できます**レコード**、**フィールド要素**、または**フィールド属性**ノードすべてに任意のインスタンスに対して行った変更が反映されるようインスタンス。  
  
### <a name="to-create-a-new-instance-of-an-existing-record-field-element-or-field-attribute-node"></a>既存のレコード、フィールド要素、またはフィールド属性 ノードの新しいインスタンスを作成するには  
  
1.  元の選択**レコード**、**フィールド要素**、または**フィールド属性**ノード、ことを確認します、 **Base Data Type**プロパティが正しく設定その**Data Structure Type** (**レコード**ノード) またはその**データ型**(**フィールド要素**と**フィールド属性**ノード) プロパティ、カスタム データ型の名前を入力します。  
  
2.  新しい挿入**レコード**、**フィールド要素**、または**フィールド属性**ノードとカスタム データには、次のプロパティのいずれかの設定は、手順 1 で入力した名前を入力します。  
  
    -   Data Structure Type (**レコード**ノード)  
  
    -   データ型 (**フィールド要素**と**フィールド属性**ノード)  
  
    > [!NOTE]
    >  場合、新しい**レコード**または**フィールド要素**ノードは、元のノードの兄弟、新しいノードに、元のノードとして同じ名前を付けると、同じスコープ内で重複するノードの詳細について確認するメッセージ ボックスが表示されます同じ名前です。 クリックすると**はい**手順 2. でカスタム データ型の名前を選択すると同じアクションを実行します。  
  
> [!NOTE]
>  既存の新しいインスタンスを作成した**レコード**、**フィールド要素**、または**フィールド属性**ノード。  
  
> [!NOTE]
>  一部のプロパティの**レコード**、**フィールド要素**、または**フィールド属性**ノード インスタンスが同じままになります (1 つのインスタンスへの変更はすべてのインスタンスへの変更)、およびその他プロパティは、インスタンスごとに個別に設定できます。  
  
## <a name="see-also"></a>参照  
 [スキーマへのノードの挿入](../core/inserting-nodes-into-a-schema.md)