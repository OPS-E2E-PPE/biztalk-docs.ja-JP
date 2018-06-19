---
title: 実行時間の長いトランザクション |Microsoft ドキュメント
ms.custom: ''
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: ''
ms.suite: ''
ms.tgt_pltfrm: ''
ms.topic: article
helpviewer_keywords:
- long-running transactions, about long-running transactions
- atomic transactions, long-running transactions
- long-running transactions, orchestrations
- long-running transactions, nesting
- scopes, examples
- orchestrations, transactions
- compensations, long-running transactions
- compensations, customizing
- transactions, long-running
- transactions, compensation blocks
- long-running transactions
- long-running transactions, timeouts
- compensations, examples
- fault tolerance, long-running transactions
- transactions, examples
- orchestrations, long-running transactions
- transactions, atomic
- transactions, fault tolerance
- scopes, long-running transactions
- long-running transactions, fault tolerance
- transactions, nesting
- examples, scopes
ms.assetid: 4bf4d0c8-903a-411f-963b-bd4cfdfc2958
caps.latest.revision: 9
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: 86c419c79b9de6287a0361dfe4e2e6b9dc555153
ms.sourcegitcommit: cb908c540d8f1a692d01dc8f313e16cb4b4e696d
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 09/20/2017
ms.locfileid: "22262778"
---
# <a name="long-running-transactions"></a><span data-ttu-id="5da16-102">長時間トランザクション</span><span class="sxs-lookup"><span data-stu-id="5da16-102">Long-Running Transactions</span></span>
<span data-ttu-id="5da16-103">長時間トランザクションは、BizTalk オーケストレーションでよく使用される重要なコンストラクターです。</span><span class="sxs-lookup"><span data-stu-id="5da16-103">Long-running transactions are important, commonly used constructs in BizTalk orchestrations.</span></span> <span data-ttu-id="5da16-104">スコープ ベースのカスタム補正、スコープ ベースのカスタム例外処理、およびトランザクションの入れ子に対応した機能があり、各機能を活用することで、堅牢なトランザクション アーキテクチャをきわめて柔軟に設計することができます。</span><span class="sxs-lookup"><span data-stu-id="5da16-104">They provide you with facilities for custom scope-based compensation, custom scope-based exception handling, and the ability to nest transactions, all of which give you great flexibility in designing robust transaction architecture.</span></span>  
  
 <span data-ttu-id="5da16-105">長時間トランザクションは、トランザクションの実行が長時間にわたる可能性があり、かつ完全な ACID プロパティを必要としない場合 (つまり、必ずしも他のトランザクションからデータを分離する必要がない場合) に使用します。</span><span class="sxs-lookup"><span data-stu-id="5da16-105">You use a long-running transaction when the transaction might need to run for an extended time and you do not need full ACID properties (that is, you do not need to guarantee isolation of data from other transactions).</span></span> <span data-ttu-id="5da16-106">長時間トランザクションは、長時間にわたって非アクティブになる可能性があります。多くの場合、その原因は外部メッセージの到着の待機にあります。</span><span class="sxs-lookup"><span data-stu-id="5da16-106">A long-running transaction might have long periods of inactivity, often due to waiting for external messages to arrive.</span></span>  
  
 <span data-ttu-id="5da16-107">長時間トランザクションには一貫性と持続性はありますが、原子性と分離性はありません。</span><span class="sxs-lookup"><span data-stu-id="5da16-107">Long-running transactions possess consistency, and durability, but not atomicity and isolation.</span></span> <span data-ttu-id="5da16-108">長時間トランザクション内のデータはロックされないため、他のプロセスやアプリケーションによって変更されることがあります。</span><span class="sxs-lookup"><span data-stu-id="5da16-108">The data within a long-running transaction is not locked; other processes or applications can modify it.</span></span> <span data-ttu-id="5da16-109">長時間にわたってロックをかけるのは実際的ではないため、状態の更新に関する分離プロパティは保持されません。</span><span class="sxs-lookup"><span data-stu-id="5da16-109">The isolation property for state updates is not maintained because holding locks for a long duration is impractical.</span></span>  
  
 <span data-ttu-id="5da16-110">長時間トランザクションのコミットは、アトミックのトランザクションのコミットとは異なります。</span><span class="sxs-lookup"><span data-stu-id="5da16-110">Commitment of a long-running transaction is different than commitment of an atomic transaction.</span></span> <span data-ttu-id="5da16-111">結果に関して分散調整が暗黙の前提になることはありません (長時間トランザクションは単一のオーケストレーション インスタンス内にのみ存在します)。</span><span class="sxs-lookup"><span data-stu-id="5da16-111">There is no implicit assumption of distributed coordination regarding the outcome (a long-running transaction exists only within a single orchestration instance).</span></span> <span data-ttu-id="5da16-112">代わりに、実行時間の長いトランザクションは、最後のステートメントが完了した時点でコミットされたと見なされます。</span><span class="sxs-lookup"><span data-stu-id="5da16-112">Instead, a long-running transaction is considered committed when the last statement in it has completed.</span></span> <span data-ttu-id="5da16-113">トランザクションが中断された場合、状態の "自動" ロールバックは行われません。</span><span class="sxs-lookup"><span data-stu-id="5da16-113">There is no "auto" rollback of state in case of a transaction abort.</span></span> <span data-ttu-id="5da16-114">これは、例外処理および補正処理を使ったプログラムによって実現できます。</span><span class="sxs-lookup"><span data-stu-id="5da16-114">You can achieve this programmatically through the exception and compensation handlers.</span></span>  
  
 <span data-ttu-id="5da16-115">スコープでは、変数、メッセージ、および .NET コンポーネントを宣言することによってスコープ固有の状態を定義できます。</span><span class="sxs-lookup"><span data-stu-id="5da16-115">A scope can define its own state by declaring variables, messages, and .NET components.</span></span> <span data-ttu-id="5da16-116">長時間トランザクションは、そのトランザクション固有のスコープやその外側のスコープの状態情報、およびオーケストレーション内でグローバルに定義されている状態情報にアクセスできます。</span><span class="sxs-lookup"><span data-stu-id="5da16-116">A long-running transaction has access to the state information of its own scope, any scope that encloses it, and any state information that is globally defined within the orchestration.</span></span> <span data-ttu-id="5da16-117">囲んでいない任意のスコープの状態情報へのアクセスはありません。</span><span class="sxs-lookup"><span data-stu-id="5da16-117">It does not have access to the state information of any scopes that do not enclose it.</span></span>  
  
## <a name="nesting"></a><span data-ttu-id="5da16-118">入れ子</span><span class="sxs-lookup"><span data-stu-id="5da16-118">Nesting</span></span>  
 <span data-ttu-id="5da16-119">長時間トランザクションには、アトミックのトランザクションや他の長時間トランザクションを含めることができます。</span><span class="sxs-lookup"><span data-stu-id="5da16-119">Long-running transactions can contain atomic transactions or other long-running transactions.</span></span> <span data-ttu-id="5da16-120">入れ子の深さは任意です。</span><span class="sxs-lookup"><span data-stu-id="5da16-120">They can be nested to arbitrary depths.</span></span> <span data-ttu-id="5da16-121">たとえば、1 つのトランザクションに他の 2 つの長時間トランザクションを含め、そのそれぞれにアトミック トランザクションを含めることができます。</span><span class="sxs-lookup"><span data-stu-id="5da16-121">For example, your transaction might contain two other long-running transactions, each of which might contain atomic transactions.</span></span>  
  
 <span data-ttu-id="5da16-122">入れ子は、トランザクション全体の 1 つ以上のコンポーネントをアトミックにすると同時に、トランザクション全体を長時間トランザクションにする必要がある場合に特に役立ちます。</span><span class="sxs-lookup"><span data-stu-id="5da16-122">Nesting is particularly useful when one or more components of the overall transaction need to be atomic while the overall transaction needs to be long-running.</span></span> <span data-ttu-id="5da16-123">注文書の受け取りと調達を例に考えてみます。</span><span class="sxs-lookup"><span data-stu-id="5da16-123">Consider the example of receiving and fulfilling a purchase order.</span></span> <span data-ttu-id="5da16-124">注文書はいつ届くかわからず、注文調達の各種手順が発生するまでに時間がかかる可能性のある状況であっても、プロセス全体を 1 つのトランザクションとして扱うことが望ましい場合があります。</span><span class="sxs-lookup"><span data-stu-id="5da16-124">The purchase order can arrive at any time, and the various steps in fulfilling the order might take time to occur, but you still want to treat the entire process as a transaction.</span></span> <span data-ttu-id="5da16-125">この場合、トランザクション全体は明らかに長時間トランザクションにする必要がありますが、領収書発行などの個々の手順はアトミックにする必要があるケースも考えられます。</span><span class="sxs-lookup"><span data-stu-id="5da16-125">The overall transaction in this case clearly needs to be long-running, but an individual step, such as acknowledging a payment, might need to be atomic.</span></span>  
  
> [!NOTE]
>  <span data-ttu-id="5da16-126">トランザクションでないスコープまたはオーケストレーション内でトランザクション スコープを入れ子にすることはできません。</span><span class="sxs-lookup"><span data-stu-id="5da16-126">You cannot nest a transactional scope within a scope or orchestration that is not transactional.</span></span> <span data-ttu-id="5da16-127">外側のスコープまたはオーケストレーションがトランザクションでないと状態が管理されないため、内側のスコープの状態管理を適切に処理する必要があります。</span><span class="sxs-lookup"><span data-stu-id="5da16-127">An enclosing scope or orchestration that is not transactional will not manage state, as it must to properly handle the state management of any scopes within it.</span></span>  
  
> [!NOTE]
>  <span data-ttu-id="5da16-128">同期トランザクションに他のトランザクションや同期スコープを含めることはできません。</span><span class="sxs-lookup"><span data-stu-id="5da16-128">A synchronized transaction cannot include any other transactions or synchronized scopes.</span></span>  
  
## <a name="compensation"></a><span data-ttu-id="5da16-129">[補正]</span><span class="sxs-lookup"><span data-stu-id="5da16-129">Compensation</span></span>  
 <span data-ttu-id="5da16-130">長時間トランザクションでは、トランザクションのアクティビティをコミット後に補正するために呼び出される補正ブロックを指定できるようになっています。</span><span class="sxs-lookup"><span data-stu-id="5da16-130">A long-running transaction can specify a compensation block that will be called to compensate for the transaction's activities, after it commits.</span></span> <span data-ttu-id="5da16-131">可能であれば単純にトランザクションを元に戻したり、何らかの方法でトランザクションの影響を緩和する他の関数 (通知など) を実行したりすることができます。</span><span class="sxs-lookup"><span data-stu-id="5da16-131">It might simply undo the transaction where feasible, or perform some other function, such as notification, that helps mitigate the effects of the transaction in some way.</span></span> <span data-ttu-id="5da16-132">独自の補正コードを追加しなければ、ランタイム エンジンにより既定で内側のトランザクション (長時間トランザクションとアトミックのトランザクションの両方) の補正ブロックが逆順に呼び出されます。つまり、最後にコミットされたトランザクションの補正ブロックが最初に呼び出され、最初にコミットされたトランザクションの補正ブロックが最後に呼び出されます。</span><span class="sxs-lookup"><span data-stu-id="5da16-132">If you do not add your own compensation code, the runtime engine will by default call the compensation blocks of the inner transactions, both long-running and atomic, in reverse order, starting with the last transaction committed and finishing with the first transaction committed.</span></span>  
  
> [!NOTE]
>  <span data-ttu-id="5da16-133">補正の対象となるのは、正常にコミットされたトランザクションのみです。</span><span class="sxs-lookup"><span data-stu-id="5da16-133">Compensation can only be done on a transaction that has committed successfully.</span></span>  
  
## <a name="fault-tolerance"></a><span data-ttu-id="5da16-134">フォールト トレランス</span><span class="sxs-lookup"><span data-stu-id="5da16-134">Fault tolerance</span></span>  
 <span data-ttu-id="5da16-135">トランザクションでは、内部エラー (コンピューターの障害やソフトウェア エラーなど) と外部エラー (取り消しメッセージなど) の両方の修復に対応するフォールト トレランスがサポートされています。</span><span class="sxs-lookup"><span data-stu-id="5da16-135">Transactions support fault tolerance for recovery from both internal faults (such as machine failures and software faults) and external faults (such as cancel messages).</span></span> <span data-ttu-id="5da16-136">長時間トランザクション内の部分的な更新は ACID トランザクションであるため、トランザクション エラーが発生した場合、自動的にはロールバックされません。</span><span class="sxs-lookup"><span data-stu-id="5da16-136">Partial updates within long-running transactions are not rolled back automatically when a transaction failure occurs, as they are in ACID transactions.</span></span>  
  
 <span data-ttu-id="5da16-137">エラーが発生すると、長時間トランザクションの例外コード ブロックが呼び出されます。</span><span class="sxs-lookup"><span data-stu-id="5da16-137">The exception code block for the long-running transaction is called when a fault occurs.</span></span> <span data-ttu-id="5da16-138">例外コード ブロックには、トランザクションの実行時に発生したエラーを処理するために記述する一連のエラー ハンドラーが含まれています。</span><span class="sxs-lookup"><span data-stu-id="5da16-138">The exception code block contains a set of fault handlers that you write to deal with any of the faults that can arise during the execution of the transaction.</span></span> <span data-ttu-id="5da16-139">メッセージ、変数、およびオブジェクトの最後に認識された状態に基づいてエラーを処理することができます。</span><span class="sxs-lookup"><span data-stu-id="5da16-139">You can rely on the last known state of the messages, variables, and objects in handling the fault.</span></span>  
  
 <span data-ttu-id="5da16-140">通常は、例外発生時に例外ハンドラーでオーケストレーションの状態を評価し、その状態に基づいて必要なアクションを実行し、入れ子になっているトランザクションの補正を呼び出すことをお勧めします。</span><span class="sxs-lookup"><span data-stu-id="5da16-140">You will typically want your exception handler to evaluate the state of the orchestration at the time the exception occurs, take any necessary action based on that state, and call the compensations of any nested transactions.</span></span>  
  
 <span data-ttu-id="5da16-141">長時間トランザクションの実行は、エラーが発生した時点で中止されます。</span><span class="sxs-lookup"><span data-stu-id="5da16-141">The execution of the long-running transaction is interrupted when a fault occurs.</span></span> <span data-ttu-id="5da16-142">エラーが発生したトランザクションを再開することはできません。</span><span class="sxs-lookup"><span data-stu-id="5da16-142">It cannot be resumed after a fault occurs.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="5da16-143">参照</span><span class="sxs-lookup"><span data-stu-id="5da16-143">See Also</span></span>  
 <span data-ttu-id="5da16-144">[実行時間の長いトランザクションの使用シナリオ](../core/scenarios-using-long-running-transactions.md) </span><span class="sxs-lookup"><span data-stu-id="5da16-144">[Scenarios Using Long-Running Transactions](../core/scenarios-using-long-running-transactions.md) </span></span>  
 <span data-ttu-id="5da16-145">[アトミック トランザクション](../core/atomic-transactions.md) </span><span class="sxs-lookup"><span data-stu-id="5da16-145">[Atomic Transactions](../core/atomic-transactions.md) </span></span>  
 [<span data-ttu-id="5da16-146">トランザクションを使用して、例外の処理</span><span class="sxs-lookup"><span data-stu-id="5da16-146">Using Transactions and Handling Exceptions</span></span>](../core/using-transactions-and-handling-exceptions.md)