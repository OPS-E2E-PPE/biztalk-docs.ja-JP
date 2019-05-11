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
# <a name="rule-engine"></a><span data-ttu-id="6ee25-102">ルール エンジン</span><span class="sxs-lookup"><span data-stu-id="6ee25-102">Rule Engine</span></span>
<span data-ttu-id="6ee25-103">このセクションでは、いくつかのコンポーネント、機能、およびビジネス ルール エンジンの操作について説明します。</span><span class="sxs-lookup"><span data-stu-id="6ee25-103">This section describes several components, functionalities, and operations of the Business Rule engine.</span></span> <span data-ttu-id="6ee25-104">ルール エンジンは、ルール セットの実行コンテキストを提供します。</span><span class="sxs-lookup"><span data-stu-id="6ee25-104">The rule engine provides the execution context for a rule set.</span></span> <span data-ttu-id="6ee25-105">**RuleEngine**オブジェクトは、実装を次のプラグイン コンポーネントを使用します。</span><span class="sxs-lookup"><span data-stu-id="6ee25-105">The **RuleEngine** object uses the following plug–in components for implementation:</span></span>  
  
-   <span data-ttu-id="6ee25-106">**ルールセット実行子 (推論エンジン)** します。</span><span class="sxs-lookup"><span data-stu-id="6ee25-106">**Ruleset executor (inference engine)**.</span></span> <span data-ttu-id="6ee25-107">ルール条件の評価とアクションの実行を担当するアルゴリズムを実装します。</span><span class="sxs-lookup"><span data-stu-id="6ee25-107">Implements the algorithm responsible for rule condition evaluation and action execution.</span></span> <span data-ttu-id="6ee25-108">既定のルール セット実行子は、メモリ内の操作を最適化するために設計されています、順行連鎖推論エンジンのネットワーク ベース識別です。</span><span class="sxs-lookup"><span data-stu-id="6ee25-108">The default rule set executor is a discrimination network-based forward-chaining inference engine designed to optimize in-memory operation.</span></span>  
  
-   <span data-ttu-id="6ee25-109">**ルールセット変換者**します。</span><span class="sxs-lookup"><span data-stu-id="6ee25-109">**Ruleset translator**.</span></span> <span data-ttu-id="6ee25-110">入力として受け取り、 **RuleSet**オブジェクトをルール セットの実行可能な表現を生成します。</span><span class="sxs-lookup"><span data-stu-id="6ee25-110">Takes as input a **RuleSet** object and produces an executable representation of the rule set.</span></span> <span data-ttu-id="6ee25-111">既定のメモリ内変換は、ルール セットの定義からコンパイルされた識別ネットワークを作成します。</span><span class="sxs-lookup"><span data-stu-id="6ee25-111">The default in-memory translator creates a compiled discrimination network from the rule set definition.</span></span>  
  
-   <span data-ttu-id="6ee25-112">**ルール セット追跡インターセプター**します。</span><span class="sxs-lookup"><span data-stu-id="6ee25-112">**Rule set tracking interceptor**.</span></span> <span data-ttu-id="6ee25-113">ルール セット実行子 (推論エンジン) からの出力を受信し、ルール セット追跡と監視ツールに転送します。</span><span class="sxs-lookup"><span data-stu-id="6ee25-113">Receives output from the rule set executor (inference engine) and forwards it to rule set tracking and monitoring tools.</span></span>  
  
## <a name="in-this-section"></a><span data-ttu-id="6ee25-114">このセクションの内容</span><span class="sxs-lookup"><span data-stu-id="6ee25-114">In This Section</span></span>  
  
-   [<span data-ttu-id="6ee25-115">条件の評価とアクションの実行</span><span class="sxs-lookup"><span data-stu-id="6ee25-115">Condition Evaluation and Action Execution</span></span>](../core/condition-evaluation-and-action-execution.md)  
  
-   [<span data-ttu-id="6ee25-116">議題と優先度</span><span class="sxs-lookup"><span data-stu-id="6ee25-116">Agenda and Priority</span></span>](../core/agenda-and-priority.md)  
  
-   [<span data-ttu-id="6ee25-117">エンジン制御関数</span><span class="sxs-lookup"><span data-stu-id="6ee25-117">Engine Control Functions</span></span>](../core/engine-control-functions.md)  
  
-   [<span data-ttu-id="6ee25-118">ビジネス ルール エンジンでのデータ アクセス</span><span class="sxs-lookup"><span data-stu-id="6ee25-118">Data Access in the Business Rule Engine</span></span>](../core/data-access-in-the-business-rule-engine.md)  
  
-   [<span data-ttu-id="6ee25-119">ルール アクションの副作用</span><span class="sxs-lookup"><span data-stu-id="6ee25-119">Rule Action Side Effects</span></span>](../core/rule-action-side-effects.md)  
  
-   [<span data-ttu-id="6ee25-120">ビジネス ルール エンジンにおけるクラス継承のサポート</span><span class="sxs-lookup"><span data-stu-id="6ee25-120">Support for Class Inheritance in the Business Rule Engine</span></span>](../core/support-for-class-inheritance-in-the-business-rule-engine.md)  
  
-   [<span data-ttu-id="6ee25-121">ルール エンジンの構成およびチューニング パラメーター</span><span class="sxs-lookup"><span data-stu-id="6ee25-121">Rule Engine Configuration and Tuning Parameters</span></span>](../core/rule-engine-configuration-and-tuning-parameters.md)  
  
-   [<span data-ttu-id="6ee25-122">ルール エンジン使用時のパフォーマンスに関する考慮事項</span><span class="sxs-lookup"><span data-stu-id="6ee25-122">Performance Considerations When Using the Rule Engine</span></span>](../core/performance-considerations-when-using-the-rule-engine.md)  
  
## <a name="see-also"></a><span data-ttu-id="6ee25-123">参照</span><span class="sxs-lookup"><span data-stu-id="6ee25-123">See Also</span></span>  
 [<span data-ttu-id="6ee25-124">ビジネス ルール エンジン</span><span class="sxs-lookup"><span data-stu-id="6ee25-124">Business Rules Engine</span></span>](../core/business-rules-engine.md)