---
title: ルール エンジン |Microsoft Docs
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
ms.openlocfilehash: 30e250dcc058202d91066e1d2d4cd367a8dfad06
ms.sourcegitcommit: 381e83d43796a345488d54b3f7413e11d56ad7be
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 05/07/2019
ms.locfileid: "65254629"
---
# <a name="rule-engine"></a>ルール エンジン
このセクションでは、いくつかのコンポーネント、機能、およびビジネス ルール エンジンの操作について説明します。 ルール エンジンは、ルール セットの実行コンテキストを提供します。 **RuleEngine**オブジェクトは、実装を次のプラグイン コンポーネントを使用します。  
  
-   **ルールセット実行子 (推論エンジン)** します。 ルール条件の評価とアクションの実行を担当するアルゴリズムを実装します。 既定のルール セット実行子は、メモリ内の操作を最適化するために設計されています、順行連鎖推論エンジンのネットワーク ベース識別です。  
  
-   **ルールセット変換者**します。 入力として受け取り、 **RuleSet**オブジェクトをルール セットの実行可能な表現を生成します。 既定のメモリ内変換は、ルール セットの定義からコンパイルされた識別ネットワークを作成します。  
  
-   **ルール セット追跡インターセプター**します。 ルール セット実行子 (推論エンジン) からの出力を受信し、ルール セット追跡と監視ツールに転送します。  
  
## <a name="in-this-section"></a>このセクションの内容  
  
-   [条件の評価とアクションの実行](../core/condition-evaluation-and-action-execution.md)  
  
-   [議題と優先度](../core/agenda-and-priority.md)  
  
-   [エンジン制御関数](../core/engine-control-functions.md)  
  
-   [ビジネス ルール エンジンでのデータ アクセス](../core/data-access-in-the-business-rule-engine.md)  
  
-   [ルール アクションの副作用](../core/rule-action-side-effects.md)  
  
-   [ビジネス ルール エンジンにおけるクラス継承のサポート](../core/support-for-class-inheritance-in-the-business-rule-engine.md)  
  
-   [ルール エンジンの構成およびチューニング パラメーター](../core/rule-engine-configuration-and-tuning-parameters.md)  
  
-   [ルール エンジン使用時のパフォーマンスに関する考慮事項](../core/performance-considerations-when-using-the-rule-engine.md)  
  
## <a name="see-also"></a>参照  
 [ビジネス ルール エンジン](../core/business-rules-engine.md)