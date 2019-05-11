---
title: ポリシーとルールを作成する方法 |Microsoft Docs
ms.custom: ''
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: ''
ms.suite: ''
ms.tgt_pltfrm: ''
ms.topic: article
helpviewer_keywords:
- creating, business rules
- policies, rules
- policies, predicates
- business rules, creating
- creating, policies
- policies, logical operators
- policies, examples
- policies, default actions
- policies
- policies, arguments
- policies, creating
ms.assetid: 59f06a67-edde-443b-9fbb-55ec4429837a
caps.latest.revision: 9
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: 57fa00774f1c27b6a3de323369c3d260851ecade
ms.sourcegitcommit: 381e83d43796a345488d54b3f7413e11d56ad7be
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 05/07/2019
ms.locfileid: "65385465"
---
# <a name="how-to-create-policies-and-rules"></a>ポリシーとルールを作成する方法
論理グループの論理演算子の条件で規則を作成することができます (**AND**、 **OR**、および**いない**) 述語 (の組み込みまたはユーザー定義関数に適用or 演算子) を受け取る引数 (組み込みまたはユーザー定義のファクトの参照)。 右クリックすることができますも**条件**or 論理演算子、コンテキスト メニューから論理演算子および組み込み述語を選択します。  
  
 ルールの条件を評価する場合に実行されるアクション (組み込みまたはユーザー定義関数) を定義する**true**します。  
  
> [!NOTE]
>  ルールでは、複数の述語を含めると、すべての述語する必要があります、論理演算子を引数として表示されます。 (最上位は単一の .NET メンバー、db 列、またはブール型の XML フィールド/属性を使用できます)  
  
### <a name="to-create-a-policy"></a>ポリシーを作成するには  
  
1.  ポリシー エクスプローラ ペインで右クリック**ポリシー**、 をクリックし、**新しいポリシーの追加**します。  
  
     新しいフォルダーを**Policy1**、下に作成されます**ポリシー**します。 既定では、新しいポリシーのバージョン 1 が作成されます。  
  
2.  クリックして**Policy1**します。  
  
3.  名前のプロパティ ウィンドウで名前を入力します。  
  
### <a name="to-add-a-rule-to-a-policy-version"></a>ポリシーのバージョンにルールを追加するには  
  
-   ポリシー エクスプ ローラー] ウィンドウで **[ポリシー]** を右クリックして**バージョン 1.0 (未保存)**、し、[**新しいルールの追加**します。  
  
### <a name="to-add-a-logical-operator-to-a-rule-condition"></a>ルールの条件に論理演算子を追加するには  
  
-   ルールの定義 ウィンドウで、右クリック**条件**のいずれかをクリックして**論理積の追加**、**論理和の追加**、または**論理否定の追加**.  
  
### <a name="to-add-a-built-in-predicate-to-a-rule-condition-or-logical-operator"></a>ルール条件または論理演算子に組み込みの述語を追加するには  
  
1.  [ファクト エクスプ ローラー] ウィンドウ、**ボキャブラリ**タブをクリックし、をクリックし、**述語**フォルダー。  
  
2.  公開された述語のボキャブラリのバージョンを展開し、希望の述語をクリックします。  
  
3.  論理演算子、またはに述語をドラッグ**条件**ルールには、1 つしか述語が含まれる場合。  
  
    > [!NOTE]
    >  データ要素が述語として機能しますが、データ ソースから直接、述語に追加することもできます (に評価される**true**または**false**)。  
  
### <a name="to-add-a-built-in-action-to-a-rule"></a>ルールに、組み込みアクションを追加するには  
  
1.  [ファクト エクスプ ローラー] ウィンドウ、**ボキャブラリ**タブをクリックし、をクリックし、**関数**フォルダー。  
  
2.  公開された関数のボキャブラリのバージョンを展開し、関数をクリックします。  
  
3.  関数をドラッグして**アクション**します。 右クリックすることができますも**アクション**、コンテキスト メニューから組み込みアクションを選択します。  
  
### <a name="to-add-an-argument-to-a-condition-or-action"></a>条件またはアクションに引数を追加するには  
  
1.  [ファクト エクスプ ローラー] ウィンドウ、**ボキャブラリ**] タブの [をボキャブラリ フォルダーをクリックします。  
  
2.  公開された、ボキャブラリのバージョンを展開し、目的の用語をクリックします。 という用語は、述語または関数で想定されている型でなければなりません。  
  
3.  用語を条件の述語の引数またはアクション内の関数の引数にドラッグします。  
  
    > [!NOTE]
    >  データ ソースから直接、引数を追加することもできます。 または XML の場合で指定できます、フィールドの種類、プロパティ フィールドを選択するときにもちろんあります自体には、データとの互換性提供されるデータの要素が述語またはアクションで想定されている型の。 データ ソースから直接には、引数を追加するには、[ファクト エクスプ ローラー] ウィンドウで、適切なタブをクリックして、項目に移動して述語の引数または関数の引数にドラッグします。  
  
    > [!NOTE]
    >  引数をクリックし、使用する定数値を入力して直接引数に定数値を追加できます。