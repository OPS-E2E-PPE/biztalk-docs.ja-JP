---
title: "ルール |Microsoft ドキュメント"
ms.custom: 
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: 
ms.suite: 
ms.tgt_pltfrm: 
ms.topic: article
helpviewer_keywords:
- business rules, actions
- Business Rules Engine, business rules
- business rules, about business rules
- business rules, conditions
- business rules, facts
- business rules
ms.assetid: b288dd07-33f1-42fe-bbfb-02674ef3b3ca
caps.latest.revision: "8"
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: 35f398cf98181d17833be79fbe9d282e8515e052
ms.sourcegitcommit: cb908c540d8f1a692d01dc8f313e16cb4b4e696d
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 09/20/2017
---
# <a name="rules"></a>ルール
ビジネス ルールはビジネス プロセスの運営を管理する宣言型ステートメントです。 ルールは条件とアクションで構成されます。 条件を評価するに評価されると、 **true**、ルール エンジンは、1 つまたは複数のアクションを開始します。  
  
 ビジネス ルール フレームワークのルールは次の形式で定義されます。  
  
 IF`condition`し、`action`  
  
 次の例を参照してください。  
  
 金額が使用可能な資金以下である  
  
 取引を行い、レシートを印刷する  
  
 このルールはビジネス ロジックを適用して、データまたはファクトの 2 つの金額、ここでは取り引き金額と使用可能な資金を比較し、取り引きを行うかどうかを決定します。  
  
 ビジネス ルールの作成、変更、バージョン管理、展開にはビジネス ルール作成ツールを使用します。 プログラムを記述する方法もあります。  
  
## <a name="conditions"></a>[条件]  
 条件はファクトについての述語から成る true/false (ブール値) 式です。  
  
 この例では、述語**以下に**ファクトに適用される**量**と**使用可能な資金**です。 この条件は常にいずれかの評価**true**または**false**です。  
  
 論理演算子と述語を組み合わせることができます**AND**、**または**、および**いない**フォーム可能性のある非常に大きく、論理式ですが評価が常にいずれか**true**または**false**です。  
  
## <a name="actions"></a>アクション  
 アクションは条件評価の機能的な結果です。 ルールの条件が満たされると、対応するアクションが開始されます。  
  
 例では、"取り引きを行う" と "レシートを印刷する" というアクションが、条件 (金額が使用可能な資金以下である) が true の場合にのみ実行されます。  
  
 ビジネス ルール フレームワークでは、アクションはメソッドの呼び出しやオブジェクトのプロパティ設定、XML ドキュメントやデータベース テーブルに対する集合演算という形で表現されます。  
  
## <a name="facts"></a>ファクト  
 ファクトはルールを適用するデータです。 この例では、"金額" と "使用可能な資金" がファクトです。 詳細については、次を参照してください。[ファクト](../core/facts.md)です。  
  
## <a name="see-also"></a>参照  
 [ポリシーとルールを作成する方法](../core/how-to-create-policies-and-rules.md)