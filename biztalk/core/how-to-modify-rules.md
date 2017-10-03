---
title: "規則を変更する方法 |Microsoft ドキュメント"
ms.custom: 
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: 
ms.suite: 
ms.tgt_pltfrm: 
ms.topic: article
helpviewer_keywords:
- business rules, activating
- deactivating business rules
- business rules, priorities
- activating business rules
- business rules, deactivating
- modifying, business rules
- business rules, modifying
ms.assetid: 661b2637-b5d6-4bde-9c42-24cd9e9d241c
caps.latest.revision: "7"
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: fce3fb78ce67b6c82f2301dfcb4cb2175aee0dde
ms.sourcegitcommit: cb908c540d8f1a692d01dc8f313e16cb4b4e696d
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 09/20/2017
---
# <a name="how-to-modify-rules"></a>規則を変更する方法
ルールを変更する機能は、ビジネス ルールのパラダイムにおいて重要な役割を果たします。 2 つの方法で、ポリシー内のルールを変更することができます。 ポリシーの新しいバージョンを作成するかによって発行されていないバージョンのポリシーを直接変更します。  
  
 ルールは個別に修正できるほか、新しいルールを追加したり、既存のルールを削除することもできます。 他にも、述語や論理演算子をルールの条件から削除する、アクションを削除する、アクションを上下に移動する、述語や論理演算子を同じ条件内で移動するなどの操作ができます。 ただし、述語および論理演算子の表示上の順序が、評価の順序を決定するわけではないという点に注意してください。  
  
 ルールを非アクティブに設定すると、ポリシーの実行時にルールが実行されないようにできます。また、非アクティブ化されたルールを再度アクティブ化することもできます。  
  
 ルールに優先度を設定することにより、別の優先度を持つルールのアクションが実行される前または実行された後に、そのルールのアクションを実行させることができます。  
  
> [!CAUTION]
>  SQL Server コンピューターを停止させる必要がある場合は、まだ保存されていないボキャブラリ バージョンまたはボキャブラリ定義をすべて保存してからビジネス ルール作成ツールを閉じる必要があります。そのようにしないと、変更が失われます。  
  
 このトピックでは、次の操作の手順について説明します。  
  
-   条件またはアクションの引数を変更するには  
  
-   条件内で述語を移動するには  
  
-   条件内で論理演算子を移動するには  
  
-   ルール内のアクションの順序を変更するには  
  
-   述語、論理演算子、またはアクションを削除するには  
  
-   ルールをアクティブ化または非アクティブ化するには  
  
-   ルールに優先度を設定するには  
  
### <a name="to-change-an-argument-in-a-condition-or-action"></a>条件またはアクションの引数を変更するには  
  
1.  [ファクト エクスプローラー] ウィンドウで、適切なタブをクリックし、引数として使用する用語に移動します。 用語の型は、述語または関数に想定されている型と一致している必要があります。  
  
2.  用語をクリックし、条件内の述語の引数またはアクション内の関数の引数にドラッグします。  
  
### <a name="to-move-a-predicate-within-a-condition"></a>条件内で述語を移動するには  
  
-   述語をクリックし、別の論理演算子にドラッグします。  
  
### <a name="to-move-a-logical-operator-within-a-condition"></a>条件内で論理演算子を移動するには  
  
-   論理演算子をクリックし、別の論理演算子またはには、それをドラッグ**条件**です。  
  
### <a name="to-change-the-order-of-actions-within-a-rule"></a>ルール内のアクションの順序を変更するには  
  
-   アクションをクリックし、をクリックして**上に移動**または**下へ移動**です。  
  
    > [!NOTE]
    >  ルールのアクションは、他のアクションの後に実行されるエンジンの制御関数を除き、指定された順序で実行されます。  
  
### <a name="to-delete-a-predicate-logical-operator-or-action"></a>述語、論理演算子、またはアクションを削除するには  
  
-   述語、論理演算子、またはアクション、をクリックし、をクリックして**削除**です。  
  
### <a name="to-activate-or-deactivate-a-rule"></a>ルールをアクティブ化または非アクティブ化するには  
  
-   ルールをクリックし、[プロパティ] ウィンドウで次のように設定します。 **Active**いずれかに**True**または**False**です。  
  
### <a name="to-set-a-priority-on-a-rule"></a>ルールに優先度を設定するには  
  
-   ルールをクリックし、[プロパティ] ウィンドウで次のように設定します。**優先度**整数値にします。  
  
    > [!NOTE]
    >  優先度は相対的に使用されます。特定の優先度を持つルールのすべてのアクションは、より低い優先度値を持つルールのアクションよりも前に実行されます。 優先度には正数または負数を設定できます。既定値は 0 です。