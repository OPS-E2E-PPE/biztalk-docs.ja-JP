---
title: ルール |Microsoft Docs
ms.custom: ''
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: ''
ms.suite: ''
ms.tgt_pltfrm: ''
ms.topic: article
helpviewer_keywords:
- business rules, actions
- Business Rules Engine, business rules
- business rules, about business rules
- business rules, conditions
- business rules, facts
- business rules
ms.assetid: b288dd07-33f1-42fe-bbfb-02674ef3b3ca
caps.latest.revision: 8
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: d51492beb69b2789100f7328e84323cfff7ae2c9
ms.sourcegitcommit: 381e83d43796a345488d54b3f7413e11d56ad7be
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 05/07/2019
ms.locfileid: "65254623"
---
# <a name="rules"></a>ルール
ビジネス ルールは、ビジネス プロセスの運営を管理する宣言ステートメントです。 ルールは、条件とアクションで構成されます。 条件が評価されに評価されると、 **true**、ルール エンジンは、1 つまたは複数のアクションを開始します。  
  
 ビジネス ルール フレームワークでのルールは、次の形式を使用して定義されます。  
  
 IF`condition`し`action`  
  
 次に例を示します。  
  
 IF 金額が使用可能な資金以下  
  
 取引を行い、レシートを印刷し、  
  
 このルールは、データまたはトランザクションの量と使用可能な資金の形式で、ファクトの 2 つの通貨値の比較の形式でのビジネス ロジックを適用することで、トランザクションを実施するかどうかを判断します。  
  
 作成、変更、バージョンについては、ビジネス ルール作成ツールを使用して、ビジネス ルールを展開できます。 前のタスクをプログラムで実行することができます。  
  
## <a name="conditions"></a>条件  
 条件は、true または false のファクトに適用される 1 つまたは複数の述語から成る (ブール) 式です。  
  
 この例では、述語**に等しいまたはそれよりも小さい**ファクトに適用される**量**と**使用可能な資金**します。 この条件がいずれかに評価されることは常に**true**または**false**します。  
  
 論理演算子と述語を組み合わせることができます**AND**、**または**、および**いない**は可能性のある非常に大きく、論理式は常に評価するフォームにいずれか**true**または**false**します。  
  
## <a name="actions"></a>アクション  
 アクションは、条件の評価の機能的な結果です。 ルールの条件が満たされた場合は、対応するアクションが開始されます。  
  
 この例では「取引を行う」と「レシートを印刷」は状況、および条件 (この場合は、"量が少ない場合に使用可能な資金以下") の指定が true の場合のみが実行されるアクションです。  
  
 アクションは、メソッドの呼び出しによって、オブジェクトのプロパティを設定または XML ドキュメントやデータベース テーブルに対する集合演算によって、ビジネス ルール フレームワークで表現されます。  
  
## <a name="facts"></a>ファクト  
 ファクトは、ルールを適用するデータです。 この例では、「金額」と「使用可能な資金」がファクトです。 詳細については、次を参照してください。[ファクト](../core/facts.md)します。  
  
## <a name="see-also"></a>参照  
 [ポリシーとルールを作成する方法](../core/how-to-create-policies-and-rules.md)