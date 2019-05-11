---
title: 実行時間の長いトランザクション |Microsoft Docs
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
ms.openlocfilehash: 99fb048c158b758e125d82f50ce2771bf0ede94f
ms.sourcegitcommit: 381e83d43796a345488d54b3f7413e11d56ad7be
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 05/07/2019
ms.locfileid: "65330389"
---
# <a name="long-running-transactions"></a><span data-ttu-id="3873f-102">長時間トランザクション</span><span class="sxs-lookup"><span data-stu-id="3873f-102">Long-Running Transactions</span></span>
<span data-ttu-id="3873f-103">実行時間の長いトランザクションとは、BizTalk オーケストレーションでの重要な一般的に使用の構成要素です。</span><span class="sxs-lookup"><span data-stu-id="3873f-103">Long-running transactions are important, commonly used constructs in BizTalk orchestrations.</span></span> <span data-ttu-id="3873f-104">スコープ ベースのカスタム補正、スコープに基づくカスタム例外処理、およびすべての柔軟で堅牢なトランザクション アーキテクチャの設計、トランザクションを入れ子に機能するための機能を提供します。</span><span class="sxs-lookup"><span data-stu-id="3873f-104">They provide you with facilities for custom scope-based compensation, custom scope-based exception handling, and the ability to nest transactions, all of which give you great flexibility in designing robust transaction architecture.</span></span>  
  
 <span data-ttu-id="3873f-105">トランザクションが長時間にわたって実行する必要があり、完全な ACID プロパティを必要としないときに、実行時間の長いトランザクションを使用する (つまり、する必要はありません他のトランザクションからデータの分離を保証するために)。</span><span class="sxs-lookup"><span data-stu-id="3873f-105">You use a long-running transaction when the transaction might need to run for an extended time and you do not need full ACID properties (that is, you do not need to guarantee isolation of data from other transactions).</span></span> <span data-ttu-id="3873f-106">長期間続いた場合、外部メッセージが到着するを待つためには、多くの場合、実行時間の長いトランザクションがあります。</span><span class="sxs-lookup"><span data-stu-id="3873f-106">A long-running transaction might have long periods of inactivity, often due to waiting for external messages to arrive.</span></span>  
  
 <span data-ttu-id="3873f-107">実行時間の長いトランザクションの一貫性と持続性がいない原子性と分離を持ちます。</span><span class="sxs-lookup"><span data-stu-id="3873f-107">Long-running transactions possess consistency, and durability, but not atomicity and isolation.</span></span> <span data-ttu-id="3873f-108">実行時間の長いトランザクション内でデータがロックされていません。他のプロセスやアプリケーションを変更できます。</span><span class="sxs-lookup"><span data-stu-id="3873f-108">The data within a long-running transaction is not locked; other processes or applications can modify it.</span></span> <span data-ttu-id="3873f-109">ロックを保持する時間が長くなるが実用的でないために、状態の更新に関する分離プロパティは保持されません。</span><span class="sxs-lookup"><span data-stu-id="3873f-109">The isolation property for state updates is not maintained because holding locks for a long duration is impractical.</span></span>  
  
 <span data-ttu-id="3873f-110">実行時間の長いトランザクションのコミットメントは、アトミック トランザクションのコミットメントと異なります。</span><span class="sxs-lookup"><span data-stu-id="3873f-110">Commitment of a long-running transaction is different than commitment of an atomic transaction.</span></span> <span data-ttu-id="3873f-111">(1 つのオーケストレーション インスタンス内でのみ実行時間の長いトランザクションが存在する) 結果に関して分散調整の暗黙的な前提はありません。</span><span class="sxs-lookup"><span data-stu-id="3873f-111">There is no implicit assumption of distributed coordination regarding the outcome (a long-running transaction exists only within a single orchestration instance).</span></span> <span data-ttu-id="3873f-112">代わりに、実行時間の長いトランザクションは、その最後のステートメントが完了した時点でコミットされたと見なされます。</span><span class="sxs-lookup"><span data-stu-id="3873f-112">Instead, a long-running transaction is considered committed when the last statement in it has completed.</span></span> <span data-ttu-id="3873f-113">トランザクションが中断された場合、状態の「自動」ロールバックはありません。</span><span class="sxs-lookup"><span data-stu-id="3873f-113">There is no "auto" rollback of state in case of a transaction abort.</span></span> <span data-ttu-id="3873f-114">この操作は、例外処理および補正ハンドラーを使用してプログラムによって実現できます。</span><span class="sxs-lookup"><span data-stu-id="3873f-114">You can achieve this programmatically through the exception and compensation handlers.</span></span>  
  
 <span data-ttu-id="3873f-115">スコープは、変数、メッセージ、および .NET コンポーネントを宣言することで、独自の状態を定義できます。</span><span class="sxs-lookup"><span data-stu-id="3873f-115">A scope can define its own state by declaring variables, messages, and .NET components.</span></span> <span data-ttu-id="3873f-116">実行時間の長いトランザクションでは、独自のスコープ、任意のスコープを囲む、および、オーケストレーション内でグローバルに定義されているすべての状態情報の状態情報へのアクセス権を持ちます。</span><span class="sxs-lookup"><span data-stu-id="3873f-116">A long-running transaction has access to the state information of its own scope, any scope that encloses it, and any state information that is globally defined within the orchestration.</span></span> <span data-ttu-id="3873f-117">囲んでいない任意のスコープの状態情報へのアクセスはありません。</span><span class="sxs-lookup"><span data-stu-id="3873f-117">It does not have access to the state information of any scopes that do not enclose it.</span></span>  
  
## <a name="nesting"></a><span data-ttu-id="3873f-118">入れ子</span><span class="sxs-lookup"><span data-stu-id="3873f-118">Nesting</span></span>  
 <span data-ttu-id="3873f-119">実行時間の長いトランザクションはアトミックのトランザクションやその他の実行時間の長いトランザクションに含めることができます。</span><span class="sxs-lookup"><span data-stu-id="3873f-119">Long-running transactions can contain atomic transactions or other long-running transactions.</span></span> <span data-ttu-id="3873f-120">これらは、任意の深さに入れ子にできます。</span><span class="sxs-lookup"><span data-stu-id="3873f-120">They can be nested to arbitrary depths.</span></span> <span data-ttu-id="3873f-121">たとえば、トランザクションには、それぞれのアトミック トランザクションを含めることがあります、その他の 2 つの実行時間の長いトランザクションが含まれます。</span><span class="sxs-lookup"><span data-stu-id="3873f-121">For example, your transaction might contain two other long-running transactions, each of which might contain atomic transactions.</span></span>  
  
 <span data-ttu-id="3873f-122">入れ子が 1 つの場合に特に役立ちますか、トランザクション全体の複数のコンポーネントはトランザクション全体が長期間実行する必要がありますにアトミックである必要があります。</span><span class="sxs-lookup"><span data-stu-id="3873f-122">Nesting is particularly useful when one or more components of the overall transaction need to be atomic while the overall transaction needs to be long-running.</span></span> <span data-ttu-id="3873f-123">受け取りと調達、注文書の使用例を検討してください。</span><span class="sxs-lookup"><span data-stu-id="3873f-123">Consider the example of receiving and fulfilling a purchase order.</span></span> <span data-ttu-id="3873f-124">注文書は、いつでも関係なく着信できると、注文のさまざまな手順が発生する時間をかかる場合がありますが、プロセス全体をトランザクションとして処理します。</span><span class="sxs-lookup"><span data-stu-id="3873f-124">The purchase order can arrive at any time, and the various steps in fulfilling the order might take time to occur, but you still want to treat the entire process as a transaction.</span></span> <span data-ttu-id="3873f-125">全体的なトランザクションここで明確にする必要がある実行時間の長いが、領収など、個々 のステップがアトミックである必要があります。</span><span class="sxs-lookup"><span data-stu-id="3873f-125">The overall transaction in this case clearly needs to be long-running, but an individual step, such as acknowledging a payment, might need to be atomic.</span></span>  
  
> [!NOTE]
>  <span data-ttu-id="3873f-126">スコープまたはトランザクションでないオーケストレーション内でトランザクション スコープを入れ子にすることはできません。</span><span class="sxs-lookup"><span data-stu-id="3873f-126">You cannot nest a transactional scope within a scope or orchestration that is not transactional.</span></span> <span data-ttu-id="3873f-127">外側のスコープまたはオーケストレーションがトランザクションでない状態が管理されない、ように、内側のスコープの状態管理を適切に処理する必要があります。</span><span class="sxs-lookup"><span data-stu-id="3873f-127">An enclosing scope or orchestration that is not transactional will not manage state, as it must to properly handle the state management of any scopes within it.</span></span>  
  
> [!NOTE]
>  <span data-ttu-id="3873f-128">同期トランザクションや同期スコープを他のトランザクションを含めることはできません。</span><span class="sxs-lookup"><span data-stu-id="3873f-128">A synchronized transaction cannot include any other transactions or synchronized scopes.</span></span>  
  
## <a name="compensation"></a><span data-ttu-id="3873f-129">補正</span><span class="sxs-lookup"><span data-stu-id="3873f-129">Compensation</span></span>  
 <span data-ttu-id="3873f-130">実行時間の長いトランザクションはコミット後のトランザクションのアクティビティを補正するために呼び出される補正ブロックを指定できます。</span><span class="sxs-lookup"><span data-stu-id="3873f-130">A long-running transaction can specify a compensation block that will be called to compensate for the transaction's activities, after it commits.</span></span> <span data-ttu-id="3873f-131">可能であれば、トランザクションを元に戻す、何らかの方法でトランザクションの影響を軽減できます通知など、他の機能を実行またはその可能性がありますだけです。</span><span class="sxs-lookup"><span data-stu-id="3873f-131">It might simply undo the transaction where feasible, or perform some other function, such as notification, that helps mitigate the effects of the transaction in some way.</span></span> <span data-ttu-id="3873f-132">独自の補正コードを追加しない場合、ランタイム エンジンが既定では呼び出し実行時間の長いと、アトミックの内側のトランザクションの補正ブロック逆の順序で最後にコミットされたトランザクションを開始および終了した後、最初のトランザクションのコミットします。</span><span class="sxs-lookup"><span data-stu-id="3873f-132">If you do not add your own compensation code, the runtime engine will by default call the compensation blocks of the inner transactions, both long-running and atomic, in reverse order, starting with the last transaction committed and finishing with the first transaction committed.</span></span>  
  
> [!NOTE]
>  <span data-ttu-id="3873f-133">補正は、正常にコミットされたトランザクションでのみ実行できます。</span><span class="sxs-lookup"><span data-stu-id="3873f-133">Compensation can only be done on a transaction that has committed successfully.</span></span>  
  
## <a name="fault-tolerance"></a><span data-ttu-id="3873f-134">フォールト トレランス</span><span class="sxs-lookup"><span data-stu-id="3873f-134">Fault tolerance</span></span>  
 <span data-ttu-id="3873f-135">トランザクションは、内部エラー (コンピューターの障害やソフトウェア障害) などと外部エラー (取り消しメッセージなど) の両方からの復旧のフォールト トレランスをサポートします。</span><span class="sxs-lookup"><span data-stu-id="3873f-135">Transactions support fault tolerance for recovery from both internal faults (such as machine failures and software faults) and external faults (such as cancel messages).</span></span> <span data-ttu-id="3873f-136">実行時間の長いトランザクション内での部分的な更新プログラムはロールバックされません自動的にトランザクションに失敗した場合、ACID トランザクションのようにします。</span><span class="sxs-lookup"><span data-stu-id="3873f-136">Partial updates within long-running transactions are not rolled back automatically when a transaction failure occurs, as they are in ACID transactions.</span></span>  
  
 <span data-ttu-id="3873f-137">実行時間の長いトランザクションの例外コード ブロックは、障害が発生したときに呼び出されます。</span><span class="sxs-lookup"><span data-stu-id="3873f-137">The exception code block for the long-running transaction is called when a fault occurs.</span></span> <span data-ttu-id="3873f-138">例外コード ブロックには、一連エラー ハンドラーを記述すると、トランザクションの実行時に発生するエラーの処理にはが含まれています。</span><span class="sxs-lookup"><span data-stu-id="3873f-138">The exception code block contains a set of fault handlers that you write to deal with any of the faults that can arise during the execution of the transaction.</span></span> <span data-ttu-id="3873f-139">メッセージ、変数、およびエラーを処理内のオブジェクトの最後の既知の状態を利用できます。</span><span class="sxs-lookup"><span data-stu-id="3873f-139">You can rely on the last known state of the messages, variables, and objects in handling the fault.</span></span>  
  
 <span data-ttu-id="3873f-140">例外が発生した時にオーケストレーションの状態の評価をその状態に基づいて必要なアクションを実行し、入れ子になったトランザクションの補正を呼び出す例外ハンドラーは通常します。</span><span class="sxs-lookup"><span data-stu-id="3873f-140">You will typically want your exception handler to evaluate the state of the orchestration at the time the exception occurs, take any necessary action based on that state, and call the compensations of any nested transactions.</span></span>  
  
 <span data-ttu-id="3873f-141">エラーが発生した場合は、実行時間の長いトランザクションの実行が中断されます。</span><span class="sxs-lookup"><span data-stu-id="3873f-141">The execution of the long-running transaction is interrupted when a fault occurs.</span></span> <span data-ttu-id="3873f-142">エラーが発生した後に再開できません。</span><span class="sxs-lookup"><span data-stu-id="3873f-142">It cannot be resumed after a fault occurs.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="3873f-143">参照</span><span class="sxs-lookup"><span data-stu-id="3873f-143">See Also</span></span>  
 <span data-ttu-id="3873f-144">[実行時間の長いトランザクションの使用シナリオ](../core/scenarios-using-long-running-transactions.md) </span><span class="sxs-lookup"><span data-stu-id="3873f-144">[Scenarios Using Long-Running Transactions](../core/scenarios-using-long-running-transactions.md) </span></span>  
 <span data-ttu-id="3873f-145">[アトミック トランザクション](../core/atomic-transactions.md) </span><span class="sxs-lookup"><span data-stu-id="3873f-145">[Atomic Transactions](../core/atomic-transactions.md) </span></span>  
 [<span data-ttu-id="3873f-146">トランザクションの使用と例外の処理</span><span class="sxs-lookup"><span data-stu-id="3873f-146">Using Transactions and Handling Exceptions</span></span>](../core/using-transactions-and-handling-exceptions.md)