---
title: "条件の評価とアクションの実行 |Microsoft ドキュメント"
ms.custom: 
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: 
ms.suite: 
ms.tgt_pltfrm: 
ms.topic: article
helpviewer_keywords:
- Action stage [Business Rules Engine]
- examples, business rules
- Business Rules Engine, policies
- Match stage [Business Rules Engine]
- business rules, examples
- Business Rules Engine, algorithm
- Business Rules Engine, examples
- conflict resolution [Business Rules Engine]
- Business Rules Engine, stages
ms.assetid: dcaa32c2-3403-4f54-92e2-128686bfc193
caps.latest.revision: "8"
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: 2814a97c1907b1bb29eee2a718d04d14cfe901a6
ms.sourcegitcommit: cb908c540d8f1a692d01dc8f313e16cb4b4e696d
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 09/20/2017
---
# <a name="condition-evaluation-and-action-execution"></a>条件の評価とアクションの実行
ビジネス ルール フレームワークは、.NET オブジェクト、XML ドキュメント、データベース テーブルにルールをリンクすることができる効率的な推論エンジンを提供します。  
  
 ビジネス ルール エンジンは、ポリシーの実行に 3 つのステージのアルゴリズムを使用します。 この 3 つのステージを次に示します。  
  
-   **一致**です。 一致ステージでは、ルール条件で定義された述語を使用して、ファクトの種類 (ルール エンジンの作業メモリに保存されているオブジェクト参照) を使用する述語とファクトが照合されます。 パターン照合はポリシーのすべてのルールに対して行われますが、効率を高めるために、ルール間で共有される条件は一度しか照合されません。 条件の一致を部分的に作業メモリに保存することにより、以降のパターン照合操作の効率を高めることができます。 パターン照合フェーズの出力には、ルール エンジンの議題に対する更新が含まれています。  
  
-   **競合解決**です。 競合解決ステージでは、実行の候補となるルールを確認し、あらかじめ指定した解決スキームに基づいて、次に実行するルール アクションのセットを決定します。 一致ステージで検出された候補ルールはすべてルール エンジンの議題に追加されます。  
  
     既定の競合解決スキームでは、ポリシー内のルールの優先度がベースになります。 優先度は、ビジネス ルール作成ツールで構成が可能なルールのプロパティです。 番号が大きいほど、優先度は高くなります。複数のルールが呼び出された場合は、優先度の高いアクションが最初に実行されます。  
  
-   **アクション**です。 アクション ステージでは、解決されたルールのアクションが実行されます。 ルール アクションは、ルール エンジンに新しいファクトをアサートすることができるので、その結果、サイクルを継続できます。 これは順行連鎖とも呼びます。 重要な点は、現在実行中のルールがアルゴリズムに横取りされないということです。 現在実行中のルールのアクションはすべて、一致フェーズが繰り返される前に実行されます。 ただし、一致フェーズが再開しなければ、議題の他のルールが実行されることはありません。 そのため、一致フェーズが原因で、議題の他のルールが実行前に議題から削除されることがあります。  
  
 次の例は、一致 - 競合解決 - アクションの 3 つのステージのアルゴリズムを示します。  
  
 **ルール 1: 収入を評価します。**  
  
-   宣言型表記  
  
     申請者の信用格付けは、申請者の収入とローンの比率が 0.2 未満の場合にのみ入手します。  
  
-   場合は、ビジネス オブジェクトを使用して表現し。  
  
    ```  
    IF Application.Income / Property.Price < 0.2    
    THEN Assert new CreditRating( Application)   
    ```  
  
 **信用格付けの評価ルール 2。**  
  
-   宣言型表記  
  
     申請者は、申請者の信用格付けが 725 を上回る場合にのみ承認されます。  
  
-   場合など、ビジネス オブジェクトを使用して形式。  
  
    ```  
    IF Application.SSN = CreditRating.SSN AND CreditRating.Value > 725    
    THEN SendApprovalLetter(Application)    
    ```  
  
 ファクトを次の表にまとめます。  
  
|[ファクト]|フィールド|  
|----------|------------|  
|Application - 住宅ローン申請を表す XML ドキュメント|-Income ドル 65,000 を =<br />-SSN = XXX XX XXXX|  
|Property - 購入する資産を表す XML ドキュメント|-価格ドル 225,000 を =|  
|CreditRating – ローン申請者の信用格付けが含まれる XML ドキュメント|値 = 0 ~ 800<br />-SSN = XXX XX XXXX|  
  
 ルール エンジン作業メモリと議題は、最初は空です。 Application と Property のファクトが追加されると、ルール エンジン作業メモリと議題は次のように更新されます。  
  
|作業メモリ|議題|  
|--------------------|------------|  
|-アプリケーション<br />-プロパティ|ルール 1|  
  
 ルール 1 はため議題に追加されますその条件 (Application.Income/Property.Price < 0.2) に評価される**true**一致フェーズ中にします。 作業メモリに CreditRating ファクトは存在しないため、ルール 2 の条件は評価されません。 議題のルールはルール 1 のみなので、このルールは実行され、その後、議題から削除されます。 ルール 1 に定義された 1 つのアクションにより、新しいファクト (申請者の CreditRating ドキュメント) が作業メモリに追加されます。 ルール 1 の実行が完了すると、制御が一致フェーズに戻されます。 照合対象となる新しいオブジェクトは CreditRating ファクトしかないため、一致フェーズの結果は次のようになります。  
  
|作業メモリ|議題|  
|--------------------|------------|  
|-アプリケーション<br />-プロパティ<br />-CreditRating|規則 2|  
  
 この時点でルール 2 が実行され、申請者に対して承認通知を送付する機能が呼び出されます。 ルール 2 が完了すると、順行連鎖アルゴリズムの実行は一致フェーズに戻されます。 照合する新しいファクトが存在せず、議題が空であるため、順行連鎖は終了し、ポリシー実行は完了します。  
  
## <a name="see-also"></a>参照  
 [ルール エンジン](../core/rule-engine.md)