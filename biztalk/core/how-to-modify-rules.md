---
title: 規則を変更する方法 |Microsoft Docs
ms.custom: ''
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: ''
ms.suite: ''
ms.tgt_pltfrm: ''
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
caps.latest.revision: 7
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: 2badd7947e439fe3ba80d86607a1a271d52b5eb6
ms.sourcegitcommit: 381e83d43796a345488d54b3f7413e11d56ad7be
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 05/07/2019
ms.locfileid: "65336007"
---
# <a name="how-to-modify-rules"></a>規則を変更する方法
ルールを変更する機能は、ビジネス ルールのパラダイムの重要な部分です。 2 つの方法で、ポリシー内のルールを変更することができます。 ポリシーの新しいバージョンを作成するか、発行されていないバージョンのポリシーを直接変更します。  
  
 ルールを個別に変更する、新しいルールを追加、または既存のルールを削除できます。 述語および論理演算子をルールの条件から削除して操作を削除する、画面で、アクションを上下に移動するか、または述語や論理演算子、条件内を移動できます。 ただしに注意してください、述語や論理演算子の表示順序が評価の順序を決定していません。  
  
 非アクティブ化する、ポリシーの実行、または非アクティブ化されているルールを再アクティブ化することができる場合、ルールが実行されないように規則を設定することができます。  
  
 前に、または別の優先順位のルールのアクションの後にそのアクションが実行できるように、ルールの優先順位を設定できます。  
  
> [!CAUTION]
>  SQL Server コンピューターを停止する場合は、必ずをすべて保存されていないボキャブラリ バージョンまたはボキャブラリの定義を保存し、変更が失われないように、ビジネス ルール作成ツールを閉じます。  
  
 このトピックには、次のタスクの手順が含まれています。  
  
-   条件またはアクションの引数を変更するには  
  
-   条件内で述語を移動するには  
  
-   条件内で論理演算子を移動するには  
  
-   ルール内のアクションの順序を変更するには  
  
-   述語、論理演算子、またはアクションを削除するには  
  
-   アクティブ化またはルールを非アクティブ化するには  
  
-   ルールの優先順位を設定するには  
  
### <a name="to-change-an-argument-in-a-condition-or-action"></a>条件またはアクションの引数を変更するには  
  
1.  ファクトと定義 ウィンドウで、適切なタブをクリックし、引数として使用する用語に移動します。 という用語は、述語または関数で想定されている型でなければなりません。  
  
2.  用語をクリックし、条件の述語の引数またはアクション内の関数の引数にドラッグします。  
  
### <a name="to-move-a-predicate-within-a-condition"></a>条件内で述語を移動するには  
  
-   述語をクリックし、もう 1 つの論理演算子にドラッグします。  
  
### <a name="to-move-a-logical-operator-within-a-condition"></a>条件内で論理演算子を移動するには  
  
-   論理演算子をクリックし、もう 1 つの論理演算子またはには、それをドラッグ**条件**します。  
  
### <a name="to-change-the-order-of-actions-within-a-rule"></a>ルール内のアクションの順序を変更するには  
  
-   アクションをクリックし、クリックして**アクションを上へ移動**または**下へ移動**します。  
  
    > [!NOTE]
    >  ルールのアクションは、その他のアクションの後に実行されるエンジン制御関数を除き、指定された順序で実行されます。  
  
### <a name="to-delete-a-predicate-logical-operator-or-action"></a>述語、論理演算子、またはアクションを削除するには  
  
-   述語、論理演算子、またはアクションをクリックし、クリックして**削除**します。  
  
### <a name="to-activate-or-deactivate-a-rule"></a>アクティブ化またはルールを非アクティブ化するには  
  
-   ルールをクリックし、[プロパティ] ウィンドウで次のように設定します。 **Active**いずれかに**True**または**False**します。  
  
### <a name="to-set-a-priority-on-a-rule"></a>ルールの優先順位を設定するには  
  
-   ルールをクリックし、[プロパティ] ウィンドウで次のように設定します。**優先度**整数値。  
  
    > [!NOTE]
    >  優先度は相対的と特定の優先順位のルールのアクションのすべての優先度の低い値を持つルールのアクションの前に、順序で実行されます。 優先度の値の既定値は 0 が、正または負の値であることができます。