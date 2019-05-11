---
title: トランザクション |Microsoft Docs
ms.custom: ''
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: ''
ms.suite: ''
ms.tgt_pltfrm: ''
ms.topic: article
helpviewer_keywords:
- orchestrations, transactions
- Orchestration Designer, BizTalk Server Orchestration Engine
- BizTalk Server Orchestration Engine
- Orchestration Designer, transactions
ms.assetid: d9a748c7-be9f-4965-a30f-6b05bd6b42a3
caps.latest.revision: 8
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: 376d27c4d0371a207cae974c8a9f74da0cd36e9d
ms.sourcegitcommit: 381e83d43796a345488d54b3f7413e11d56ad7be
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 05/07/2019
ms.locfileid: "65399203"
---
# <a name="transactions"></a><span data-ttu-id="4c95b-102">トランザクション</span><span class="sxs-lookup"><span data-stu-id="4c95b-102">Transactions</span></span>
<span data-ttu-id="4c95b-103">BizTalk Server オーケストレーション エンジンは、状態を管理、ビジネス ロジックを適用し、複雑なプロセスやトランザクション セットのサポートのアプリケーションを呼び出します。</span><span class="sxs-lookup"><span data-stu-id="4c95b-103">The BizTalk Server Orchestration Engine manages the state, applies business logic, and invokes the supporting applications of complex processes and/or transaction sets.</span></span>  
  
 <span data-ttu-id="4c95b-104">ビジネス プロセスは、個別の作業のエラーが発生した場合、すべての変更を自動的にロールバックするアトミックのトランザクションの使用または実行時間が長いと、入れ子になったトランザクションを含めることができ、カスタム例外処理を使用して、エラーから復旧しているとして構成することができます。シナリオ。</span><span class="sxs-lookup"><span data-stu-id="4c95b-104">Business processes can be composed as discrete pieces of work using atomic transactions that automatically roll back all changes in case of errors or long running, which can contain nested transactions and use custom exception handling to recover from error scenarios.</span></span> <span data-ttu-id="4c95b-105">このようなトランザクション セマンティクスが管理には通常、オーケストレーション デザイナーの Scope コンス トラクターを使用します。</span><span class="sxs-lookup"><span data-stu-id="4c95b-105">These transactional semantics are typically managed through the Scope construct in the Orchestration Designer.</span></span>  
  
 <span data-ttu-id="4c95b-106">実行時間の長いプロセスは、日、週、およびより長い期間にまたがることができます。</span><span class="sxs-lookup"><span data-stu-id="4c95b-106">The long running processes can span days, weeks, and longer time durations.</span></span> <span data-ttu-id="4c95b-107">実行時間の長いプロセスは、通常、送信されるメッセージを受信したメッセージを関連付ける相関関係を利用します。</span><span class="sxs-lookup"><span data-stu-id="4c95b-107">The long running processes typically utilize correlation to correlate messages that are received to the messages that may be sent.</span></span> <span data-ttu-id="4c95b-108">通常、オーケストレーション エンジンはシステム リソースを節約するためにこれらのインスタンスを退避し、これらの関連付けられたメッセージの受信時にプロセスを再入力します。</span><span class="sxs-lookup"><span data-stu-id="4c95b-108">The orchestration engine typically dehydrates these instances to conserve system resources and re-hydrates the process upon receipt of these correlated messages.</span></span> <span data-ttu-id="4c95b-109">オーケストレーション エンジンは、任意のアプリケーションまたはシステム例外から回復する既知のチェックポイントでメッセージ ボックス データベースにオーケストレーションの状態を保持します。</span><span class="sxs-lookup"><span data-stu-id="4c95b-109">The orchestration engine persists the orchestration state to the MessageBox database at known checkpoints to recover from any application or system exceptions.</span></span>  
  
 <span data-ttu-id="4c95b-110">BizTalk オーケストレーション エンジンには、例外処理、および失敗したトランザクションからの復旧のサポートが含まれています指定されたトランザクション プログラミング モデル、アトミック トランザクションを自動的にロールバック アクション、エラーが発生した、または。その他のトランザクションとカスタム例外処理に含めることができる実行時間の長いトランザクション。</span><span class="sxs-lookup"><span data-stu-id="4c95b-110">The transactional programming model provided for the BizTalk Orchestration engine includes support for exception handling and recovery from failed transactions, atomic transactions that automatically roll back their actions if an error occurs, or long-running transactions that can contain other transactions as well as custom exception handling.</span></span>  
  
## <a name="in-this-section"></a><span data-ttu-id="4c95b-111">このセクションの内容</span><span class="sxs-lookup"><span data-stu-id="4c95b-111">In This Section</span></span>  
  
-   [<span data-ttu-id="4c95b-112">自動トランザクション</span><span class="sxs-lookup"><span data-stu-id="4c95b-112">Atomic Transactions</span></span>](../core/atomic-transactions.md)  
  
-   [<span data-ttu-id="4c95b-113">アトミック トランザクションの使用シナリオ</span><span class="sxs-lookup"><span data-stu-id="4c95b-113">Scenarios Using Atomic Transactions</span></span>](../core/scenarios-using-atomic-transactions.md)  
  
-   [<span data-ttu-id="4c95b-114">長時間トランザクション</span><span class="sxs-lookup"><span data-stu-id="4c95b-114">Long-Running Transactions</span></span>](../core/long-running-transactions.md)  
  
-   [<span data-ttu-id="4c95b-115">長時間トランザクションの使用シナリオ</span><span class="sxs-lookup"><span data-stu-id="4c95b-115">Scenarios Using Long-Running Transactions</span></span>](../core/scenarios-using-long-running-transactions.md)  
  
-   [<span data-ttu-id="4c95b-116">オーケストレーションでの永続化</span><span class="sxs-lookup"><span data-stu-id="4c95b-116">Persistence in Orchestrations</span></span>](../core/persistence-in-orchestrations.md)