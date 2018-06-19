---
title: オーケストレーションに図形を追加する方法 |Microsoft ドキュメント
ms.custom: ''
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: ''
ms.suite: ''
ms.tgt_pltfrm: ''
ms.topic: article
helpviewer_keywords:
- shapes, orchestrations
- orchestrations, shapes
- Construct Message shape [Orchestration Designer]
- Message Assignment shape [Orchestration Designer]
- Scope shape [Orchestration Designer]
ms.assetid: d39eb12c-cdc6-4918-93d9-536db1dfb889
caps.latest.revision: 6
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: b9fa6634adb20ffcf927da0af6f58e9daa2800ac
ms.sourcegitcommit: cb908c540d8f1a692d01dc8f313e16cb4b4e696d
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 09/20/2017
ms.locfileid: "22246954"
---
# <a name="how-to-add-shapes-to-orchestrations"></a>オーケストレーションに図形を追加する方法
このセクションでは、オーケストレーションに図形を追加する手順と、オーケストレーションから図形を削除する手順について説明します。 使用できる図形の詳細については、次を参照してください。[オーケストレーション図形](../core/orchestration-shapes.md)です。  
  
### <a name="to-add-a-shape-to-an-orchestration"></a>オーケストレーションに図形を追加するには  
  
1.  ツールボックスで、上、 **BizTalk オーケストレーション** タブで、オーケストレーション デザイン画面で図形を区分線にドラッグします。  
  
     - または -  
  
2.  区分線または図形を追加する図形のプレース ホルダーを右クリックを指す**図形の挿入**を追加する図形の名前をクリックします。  
  
    > [!NOTE]
    >  構成が不十分な図形にはスマート タグが表示されます。  
  
> [!NOTE]
>  **変換**図形と**メッセージの割り当て**図形のみ存在できます、**メッセージの構築**図形です。 これらの図形のいずれかの外側のオーケストレーションに追加するかどうか、**メッセージの構築**図形、新しい内側の自動的に配置されている**メッセージの構築**図形です。  
  
> [!NOTE]
>  **例外をキャッチ**と**補正**ブロックは、次ののみ存在できます、**スコープ**図形です。  
  
### <a name="to-remove-a-shape-from-an-orchestration"></a>オーケストレーションから図形を削除するには  
  
1.  デザイン画面で図形を右クリックし、をクリックして**削除**です。  
  
     - または -  
  
2.  図形を選択してキーを押して、**削除**キー。  
  
## <a name="see-also"></a>参照  
 [オーケストレーションの作成](../core/creating-orchestrations.md)