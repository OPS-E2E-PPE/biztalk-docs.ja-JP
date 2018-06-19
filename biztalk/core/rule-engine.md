---
title: ルール エンジン |Microsoft ドキュメント
ms.custom: ''
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: ''
ms.suite: ''
ms.tgt_pltfrm: ''
ms.topic: article
helpviewer_keywords:
- RuleEngine object
- Business Rules Engine, ruleset executor
- Business Rules Engine, ruleset translator
- Business Rules Engine, ruleset tracking interceptor
- Business Rules Engine, Business Rules Engine
ms.assetid: c4043a1f-357f-47bc-84e1-5e4bd9f8b5b8
caps.latest.revision: 11
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: b0dc2d293697ccbb64851591037440d0371c1346
ms.sourcegitcommit: cb908c540d8f1a692d01dc8f313e16cb4b4e696d
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 09/20/2017
ms.locfileid: "22268730"
---
# <a name="rule-engine"></a>ルール エンジン
ここでは、ビジネス ルール エンジンのいくつかのコンポーネント、機能、および操作について説明します。 ルール エンジンには、ルール セットの実行コンテキストが用意されています。 **RuleEngine**オブジェクトが実装するため、次のプラグイン コンポーネントを使用します。  
  
-   **ルールセット実行子 (推論エンジン)** です。 ルール条件の評価とアクションの実行を担当するアルゴリズムを実装します。 既定のルールセット実行子は、メモリ内作業工程を最適化するように設計されたネットワークベースの順行連鎖推論エンジンです。  
  
-   **ルールセット変換者**です。 入力として受け取り、 **RuleSet**オブジェクトをルール セットの実行可能ファイル形式を生成します。 既定のメモリ内変換者は、ルールセットの定義から、コンパイルされた識別ネットワークを作成します。  
  
-   **ルール セット追跡インターセプター**です。 ルールセット実行子 (推論エンジン) から出力を受け取って、ルールセット追跡監視ツールに転送します。  
  
## <a name="in-this-section"></a>このセクションの内容  
  
-   [条件の評価とアクションの実行](../core/condition-evaluation-and-action-execution.md)  
  
-   [議題と優先度](../core/agenda-and-priority.md)  
  
-   [エンジン制御関数](../core/engine-control-functions.md)  
  
-   [ビジネス ルール エンジンでのデータ アクセス](../core/data-access-in-the-business-rule-engine.md)  
  
-   [ルール アクションの副作用](../core/rule-action-side-effects.md)  
  
-   [ビジネス ルール エンジンにおけるクラス継承のサポート](../core/support-for-class-inheritance-in-the-business-rule-engine.md)  
  
-   [ルール エンジンの構成およびチューニング パラメーター](../core/rule-engine-configuration-and-tuning-parameters.md)  
  
-   [ルール エンジンを使用する場合のパフォーマンスに関する考慮事項](../core/performance-considerations-when-using-the-rule-engine.md)  
  
## <a name="see-also"></a>参照  
 [ビジネス ルール エンジン](../core/business-rules-engine.md)