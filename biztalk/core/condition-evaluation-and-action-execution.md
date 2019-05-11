---
title: 条件の評価とアクションの実行 |Microsoft Docs
ms.custom: ''
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: ''
ms.suite: ''
ms.tgt_pltfrm: ''
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
caps.latest.revision: 8
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: c3d971f805ab546bd758166429bdca47e5073a72
ms.sourcegitcommit: 381e83d43796a345488d54b3f7413e11d56ad7be
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 05/07/2019
ms.locfileid: "65356492"
---
# <a name="condition-evaluation-and-action-execution"></a>条件の評価とアクションの実行
ビジネス ルール フレームワークでは、ルールを .NET オブジェクト、XML ドキュメント、またはデータベース テーブルにリンクできる効率的な推論エンジンを提供します。  
  
 ビジネス ルール エンジンは、ポリシーの実行に 3 つのステージのアルゴリズムを使用します。 各段階は次のとおりです。  
  
- **一致**します。 一致ステージでは、ファクトはファクトの種類 (オブジェクト参照は、ルール エンジンの作業メモリに保持) を使用する述語と照合されます、ルールの条件で定義された述語を使用します。 、効率を高める、ポリシー内のすべてのルールで行われるパターンに一致して、ルール間で共有される条件が 1 回だけ一致します。 部分的な条件の一致を後続のパターン マッチング操作を短縮するための作業メモリに格納できます。 パターン照合フェーズの出力は、ルール エンジンの議題の更新プログラムで構成されます。  
  
- **競合解決**します。 競合解決の段階で、事前に定義された解決スキームに基づいて、次の一連のルールのアクションを実行するかを判断する実行の候補となる規則が確認されます。 照合ステージ中に検出されたすべての候補ルールは、ルール エンジンの議題に追加されます。  
  
   既定の競合解決スキームは、ポリシー内でルールの優先度に基づいています。 優先順位は、ビジネス ルール作成ツールでルールの構成可能なプロパティです。 数値が大きいほど、高いほど、優先度はしたがって複数のルールがトリガーされた場合、優先順位の高いアクションは最初に実行されます。  
  
- **アクション**します。 アクション ステージでは、解決済みのルールのアクションが実行されます。 ルールの処理は続行のサイクルがルール エンジンに新しいファクトをアサートすることができますに注意してください。 これは順行連鎖とも呼ばれます。 アルゴリズムは、現在実行中のルールを決して横取りに注意してください。 現在発生しているルールのすべてのアクションは、一致フェーズが繰り返される前に実行されます。 ただし、一致フェーズがもう一度開始する前に、議題の他のルールは起動しません。 一致フェーズを実行する前に、議題から削除する議題のこれらのルールがあります。  
  
  次の例は、一致-競合解決-アクションの 3 つのステージのアルゴリズムを示しています。  
  
  **規則 1:収入を評価します。**  
  
- 宣言型の表現。  
  
   申請者の収入とローンの比率が 0.2 未満の場合にのみ、申請者の信用格付けを取得する必要があります。  
  
- 場合は、ビジネス オブジェクトを使用して表現から。  
  
  ```  
  IF Application.Income / Property.Price < 0.2    
  THEN Assert new CreditRating( Application)   
  ```  
  
  **規則 2:信用格付けを評価します。**  
  
- 宣言型の表現。  
  
   申請者の信用格付けが 725 を上回る場合にのみ、応募者を承認する必要があります。  
  
- 場合、し、ビジネス オブジェクトを使用して形式。  
  
  ```  
  IF Application.SSN = CreditRating.SSN AND CreditRating.Value > 725    
  THEN SendApprovalLetter(Application)    
  ```  
  
  ファクトは、次の表にまとめたものです。  
  
|[ファクト]|フィールド|  
|----------|------------|  
|Application-住宅ローン アプリケーションを表す XML ドキュメント|-Income $65,000 を =<br />-SSN = XXX-XX XXXX|  
|プロパティ – 購入されているプロパティを表す XML ドキュメント|-価格 $225,000 を =|  
|CreditRating – ローン申請者の信用格付けを含む XML ドキュメント|-値 = 0 ~ 800<br />-SSN = XXX-XX XXXX|  
  
 最初に、ルール エンジンの作業メモリと議題が空です。 アプリケーションが Application と Property のファクトを追加した後、次のようにルール エンジン作業メモリと議題が更新されます。  
  
|作業メモリ|議題|  
|--------------------|------------|  
|-アプリケーション<br />-プロパティ|ルール 1|  
  
 議題に追加されてルール 1 の条件 (Application.Income/Property.Price < 0.2) に評価される**true**一致フェーズ中にします。 CreditRating ファクト、作業メモリにルール 2 の条件が評価されなかったためです。 議題に専用のルールは、ルール 1 であるため、ルールが実行され、議題から消えます。 ルール 1 の結果を新しいファクト (申請者の CreditRating ドキュメント) で定義されている 1 つのアクション作業メモリに追加されます。 ルール 1 の実行が完了すると、一致フェーズに制御が戻ります。 一致するようにのみ新しいオブジェクトは CreditRating ファクトでは、一致フェーズの結果次に示します。  
  
|作業メモリ|議題|  
|--------------------|------------|  
|-アプリケーション<br />-プロパティ<br />-   CreditRating|Rule 2|  
  
 この時点でルール 2 が実行され、申請者に、承認状を送信する関数の呼び出しで。 Rule 2 が完了すると、順行連鎖アルゴリズムの実行は、一致フェーズに返します。 一致するように新しいファクトが不要になったため、議題が空、順行連鎖は終了し、そのポリシーの実行は完了します。  
  
## <a name="see-also"></a>参照  
 [ルール エンジン](../core/rule-engine.md)