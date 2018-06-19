---
title: トランザクション |Microsoft ドキュメント
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
ms.openlocfilehash: 74827beade56e6e54414371c9796454d3b48609e
ms.sourcegitcommit: cb908c540d8f1a692d01dc8f313e16cb4b4e696d
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 09/20/2017
ms.locfileid: "22279186"
---
# <a name="transactions"></a><span data-ttu-id="3bdf8-102">トランザクション</span><span class="sxs-lookup"><span data-stu-id="3bdf8-102">Transactions</span></span>
<span data-ttu-id="3bdf8-103">BizTalk Server オーケストレーション エンジンは、状態を管理し、ビジネス ロジックを適用し、複雑な処理やトランザクション セットの実行をサポートするアプリケーションを呼び出します。</span><span class="sxs-lookup"><span data-stu-id="3bdf8-103">The BizTalk Server Orchestration Engine manages the state, applies business logic, and invokes the supporting applications of complex processes and/or transaction sets.</span></span>  
  
 <span data-ttu-id="3bdf8-104">ビジネス プロセスは、アトミック トランザクションを使用した個々の作業として構成することが可能で、エラーや長時間実行されるトランザクションが発生した場合は、自動的にすべての変更をロールバックします。ネストされたトランザクションを含めたり、エラーから回復するためにカスタム例外処理を使用することも可能です。</span><span class="sxs-lookup"><span data-stu-id="3bdf8-104">Business processes can be composed as discrete pieces of work using atomic transactions that automatically roll back all changes in case of errors or long running, which can contain nested transactions and use custom exception handling to recover from error scenarios.</span></span> <span data-ttu-id="3bdf8-105">このようなトランザクション セマンティクスは通常、オーケストレーション デザイナーの Scope コンストラクターを使用して管理します。</span><span class="sxs-lookup"><span data-stu-id="3bdf8-105">These transactional semantics are typically managed through the Scope construct in the Orchestration Designer.</span></span>  
  
 <span data-ttu-id="3bdf8-106">長時間プロセスは、完了するまでに数日から数週間以上かかる場合があります。</span><span class="sxs-lookup"><span data-stu-id="3bdf8-106">The long running processes can span days, weeks, and longer time durations.</span></span> <span data-ttu-id="3bdf8-107">長時間プロセスは、通常、送信されるメッセージを受信したメッセージを関連付けるために相関関係を使用します。</span><span class="sxs-lookup"><span data-stu-id="3bdf8-107">The long running processes typically utilize correlation to correlate messages that are received to the messages that may be sent.</span></span> <span data-ttu-id="3bdf8-108">オーケストレーション エンジンは通常、このようなインスタンスを退避してシステム リソースを保持し、関連付けられたメッセージを受け取るとプロセスを回復させます。</span><span class="sxs-lookup"><span data-stu-id="3bdf8-108">The orchestration engine typically dehydrates these instances to conserve system resources and re-hydrates the process upon receipt of these correlated messages.</span></span> <span data-ttu-id="3bdf8-109">オーケストレーション エンジンは、一定のチェックポイントでオーケストレーションの状態をメッセージ ボックス データベースに格納し、アプリケーション例外またはシステム例外からの復旧に使用します。</span><span class="sxs-lookup"><span data-stu-id="3bdf8-109">The orchestration engine persists the orchestration state to the MessageBox database at known checkpoints to recover from any application or system exceptions.</span></span>  
  
 <span data-ttu-id="3bdf8-110">BizTalk オーケストレーション エンジンに提供されているトランザクション プログラミング モデルでは、例外処理や失敗したトランザクションからの復旧のほか、エラーや長時間実行されるトランザクションが発生した場合に自動的に作業内容をロールバックするアトミック トランザクションをサポートしています。これには、カスタム例外処理に加え、他のトランザクションを含めることも可能です。</span><span class="sxs-lookup"><span data-stu-id="3bdf8-110">The transactional programming model provided for the BizTalk Orchestration engine includes support for exception handling and recovery from failed transactions, atomic transactions that automatically roll back their actions if an error occurs, or long-running transactions that can contain other transactions as well as custom exception handling.</span></span>  
  
## <a name="in-this-section"></a><span data-ttu-id="3bdf8-111">このセクションの内容</span><span class="sxs-lookup"><span data-stu-id="3bdf8-111">In This Section</span></span>  
  
-   [<span data-ttu-id="3bdf8-112">アトミック トランザクション</span><span class="sxs-lookup"><span data-stu-id="3bdf8-112">Atomic Transactions</span></span>](../core/atomic-transactions.md)  
  
-   [<span data-ttu-id="3bdf8-113">アトミック トランザクションの使用シナリオ</span><span class="sxs-lookup"><span data-stu-id="3bdf8-113">Scenarios Using Atomic Transactions</span></span>](../core/scenarios-using-atomic-transactions.md)  
  
-   [<span data-ttu-id="3bdf8-114">実行時間の長いトランザクション</span><span class="sxs-lookup"><span data-stu-id="3bdf8-114">Long-Running Transactions</span></span>](../core/long-running-transactions.md)  
  
-   [<span data-ttu-id="3bdf8-115">実行時間の長いトランザクションの使用シナリオ</span><span class="sxs-lookup"><span data-stu-id="3bdf8-115">Scenarios Using Long-Running Transactions</span></span>](../core/scenarios-using-long-running-transactions.md)  
  
-   [<span data-ttu-id="3bdf8-116">オーケストレーションの永続性</span><span class="sxs-lookup"><span data-stu-id="3bdf8-116">Persistence in Orchestrations</span></span>](../core/persistence-in-orchestrations.md)