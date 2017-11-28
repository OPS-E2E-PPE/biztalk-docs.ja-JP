---
title: "スコープ |Microsoft ドキュメント"
ms.custom: 
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: 
ms.suite: 
ms.tgt_pltfrm: 
ms.topic: article
helpviewer_keywords:
- scopes, exception handling
- Scope shape [Orchestration Designer], nesting
- scopes, variables
- scopes, Scope shape [Orchestration Designer]
- Scope shape [Orchestration Designer], exception handling
- scopes, transactions
- scopes, synchronization
- scopes, nesting
- Scope shape [Orchestration Designer], transactions
ms.assetid: 51d81ce4-0034-4415-b6ab-4c952737c1bd
caps.latest.revision: "11"
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: 2bc4d1b5d926540477293591ade8123126be1b84
ms.sourcegitcommit: cb908c540d8f1a692d01dc8f313e16cb4b4e696d
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 09/20/2017
---
# <a name="scopes"></a><span data-ttu-id="9b4f2-102">スコープ</span><span class="sxs-lookup"><span data-stu-id="9b4f2-102">Scopes</span></span>
<span data-ttu-id="9b4f2-103">スコープは、アクションをグループ化するためのフレームワークです。</span><span class="sxs-lookup"><span data-stu-id="9b4f2-103">A scope is a framework for grouping actions.</span></span> <span data-ttu-id="9b4f2-104">これは主に、トランザクションの実行および例外処理に使用されます。</span><span class="sxs-lookup"><span data-stu-id="9b4f2-104">It is primarily used for transactional execution and exception handling.</span></span>  
  
 <span data-ttu-id="9b4f2-105">1 つのスコープには、1 つ以上のブロックが含まれます。</span><span class="sxs-lookup"><span data-stu-id="9b4f2-105">A scope contains one or more blocks.</span></span> <span data-ttu-id="9b4f2-106">スコープには本体があり、オプションとして任意の数の例外処理ブロックを付加できます。</span><span class="sxs-lookup"><span data-stu-id="9b4f2-106">It has a body and can optionally have appended to it any number of exception-handling blocks.</span></span> <span data-ttu-id="9b4f2-107">スコープの特性に応じて、オプションの補正ブロックも使用できます。</span><span class="sxs-lookup"><span data-stu-id="9b4f2-107">It may have an optional compensation block as well, depending on the nature of the scope.</span></span> <span data-ttu-id="9b4f2-108">スコープによっては、例外処理だけに使用され、補正が不要な場合もあります。</span><span class="sxs-lookup"><span data-stu-id="9b4f2-108">Some scopes will be purely for exception handling, and will not require compensation.</span></span> <span data-ttu-id="9b4f2-109">明示的にトランザクションに使用されるスコープもあり、それらは常に、ユーザーが既定の補正ハンドラーに対して作成するオプションの補正ハンドラーと共に、既定の補正ハンドラーを持ちます。</span><span class="sxs-lookup"><span data-stu-id="9b4f2-109">Other scopes will be explicitly transactional, and will always have a default compensation handler, along with an optional compensation handler that you create for it.</span></span> <span data-ttu-id="9b4f2-110">トランザクション スコープには、既定の例外ハンドラー、および既定の例外ハンドラーに対してユーザーが作成する任意の数の追加の例外ハンドラーもあります。</span><span class="sxs-lookup"><span data-stu-id="9b4f2-110">A transactional scope will also have a default exception handler and any number of additional exception handlers that you create for it.</span></span>  
  
## <a name="synchronized-scopes"></a><span data-ttu-id="9b4f2-111">同期スコープ</span><span class="sxs-lookup"><span data-stu-id="9b4f2-111">Synchronized scopes</span></span>  
 <span data-ttu-id="9b4f2-112">スコープを同期するか、同期しないかを指定できます。</span><span class="sxs-lookup"><span data-stu-id="9b4f2-112">You can specify that scopes are synchronized or not synchronized.</span></span> <span data-ttu-id="9b4f2-113">スコープを同期することによって、スコープ内でアクセスされた任意の共有データがオーケストレーション内の 1 つ以上の並列アクションによって書き込まることがなくなり、別のアクションがそのデータを読み取っている間にそのデータに対する書き込みが行われることもなくなります。</span><span class="sxs-lookup"><span data-stu-id="9b4f2-113">By synchronizing a scope, you ensure that any shared data that is accessed within it will not be written to by one or more parallel actions in your orchestration, nor will it be written to while another action is reading it.</span></span>  
  
 <span data-ttu-id="9b4f2-114">アトミック トランザクション スコープは、常に同期されます。</span><span class="sxs-lookup"><span data-stu-id="9b4f2-114">Atomic transaction scopes are always synchronized.</span></span> <span data-ttu-id="9b4f2-115">同期されたスコープ内のすべてのアクションは、同期済みと見なされます。同様に、そのスコープの任意の例外ハンドラーのすべてのアクションも同期済みと見なされます。</span><span class="sxs-lookup"><span data-stu-id="9b4f2-115">All actions within a synchronized scope are considered synchronized, as are all actions in any of its exception handlers.</span></span> <span data-ttu-id="9b4f2-116">トランザクション スコープの補正ハンドラーのアクションは、同期されません。</span><span class="sxs-lookup"><span data-stu-id="9b4f2-116">Actions in the compensation handler for a transactional scope are not synchronized.</span></span>  
  
> [!CAUTION]
>  <span data-ttu-id="9b4f2-117">処理方法を慎重に計画しないと、デッドロック状態が発生する可能性があることに注意してください。</span><span class="sxs-lookup"><span data-stu-id="9b4f2-117">Note that you can still run into a deadlock condition if you do not design your processes carefully.</span></span> <span data-ttu-id="9b4f2-118">たとえば、オーケストレーション A の 1 つの並列の 2 つの分岐は、それぞれ同じメッセージにアクセスし、1 つはメッセージを送信し、もう 1 つはメッセージを受信します。このため、両方の分岐が同期スコープを持つ必要があります。</span><span class="sxs-lookup"><span data-stu-id="9b4f2-118">For example: two branches of a parallel in orchestration A access the same message, one to send it and one to receive it, so both must have a synchronized scope.</span></span> <span data-ttu-id="9b4f2-119">2 番目のオーケストレーションはメッセージを受信し、返信します。</span><span class="sxs-lookup"><span data-stu-id="9b4f2-119">A second orchestration receives the message and sends it back.</span></span> <span data-ttu-id="9b4f2-120">オーケストレーション A の送信側の分岐が、受信側の分岐の前にロックを受信し、デッドロック状態で終了する可能性があります。</span><span class="sxs-lookup"><span data-stu-id="9b4f2-120">It is possible that the sending branch in orchestration A will receive its locks before the receiving branch, and you will end up with a deadlock.</span></span>  
  
## <a name="nesting-of-scopes"></a><span data-ttu-id="9b4f2-121">スコープの入れ子</span><span class="sxs-lookup"><span data-stu-id="9b4f2-121">Nesting of scopes</span></span>  
 <span data-ttu-id="9b4f2-122">入れ子にすることができます**スコープ**他の内部の図形**スコープ**図形です。</span><span class="sxs-lookup"><span data-stu-id="9b4f2-122">You can nest **Scope** shapes inside other **Scope** shapes.</span></span> <span data-ttu-id="9b4f2-123">スコープを入れ子にするための規則は次のとおりです。</span><span class="sxs-lookup"><span data-stu-id="9b4f2-123">The rules for nesting scopes are as follows:</span></span>  
  
-   <span data-ttu-id="9b4f2-124">トランザクション スコープまたは同期スコープは、同期スコープ内 (同期スコープの例外ハンドラーを含む) に入れ子にすることはできません。</span><span class="sxs-lookup"><span data-stu-id="9b4f2-124">Transactional and/or synchronized scopes cannot be nested inside synchronized scopes, including the exception handlers of synchronized scopes.</span></span>  
  
-   <span data-ttu-id="9b4f2-125">アトミック トランザクションのスコープ内には、その他のトランザクション スコープを入れ子にすることはできません。</span><span class="sxs-lookup"><span data-stu-id="9b4f2-125">Atomic transaction scopes cannot have any other transactional scopes nested inside them.</span></span>  
  
-   <span data-ttu-id="9b4f2-126">トランザクション スコープは、トランザクションでないスコープまたはオーケストレーション内に入れ子にすることはできません。</span><span class="sxs-lookup"><span data-stu-id="9b4f2-126">Transactional scopes cannot be nested inside nontransactional scopes or orchestrations.</span></span>  
  
-   <span data-ttu-id="9b4f2-127">スコープは 21 レベル分の深さまで入れ子にすることができます。</span><span class="sxs-lookup"><span data-stu-id="9b4f2-127">You can nest scopes up to 21 levels deep.</span></span>  
  
-   <span data-ttu-id="9b4f2-128">**オーケストレーションの呼び出し**図形はスコープ内に含めることができますが、呼び出されたオーケストレーションは処理、他のと同じで入れ子にされたトランザクション、および同じ規則が適用されます。</span><span class="sxs-lookup"><span data-stu-id="9b4f2-128">**Call Orchestration** shapes can be included inside scopes, but the called orchestrations are treated the same as any other nested transaction, and the same rules apply.</span></span>  
  
-   <span data-ttu-id="9b4f2-129">**オーケストレーションを開始**図形はスコープ内に含めることができます。</span><span class="sxs-lookup"><span data-stu-id="9b4f2-129">**Start Orchestration** shapes can be included inside scopes.</span></span> <span data-ttu-id="9b4f2-130">入れ子に関する制限事項は、開始したオーケストレーションには適用されません。</span><span class="sxs-lookup"><span data-stu-id="9b4f2-130">Nesting limitations do not apply to started orchestrations.</span></span>  
  
## <a name="scope-variables"></a><span data-ttu-id="9b4f2-131">スコープ変数</span><span class="sxs-lookup"><span data-stu-id="9b4f2-131">Scope variables</span></span>  
 <span data-ttu-id="9b4f2-132">スコープ レベルで、メッセージ、関連付けセットなどの変数を宣言できます。</span><span class="sxs-lookup"><span data-stu-id="9b4f2-132">You can declare variables such as messages and correlation sets at the scope level.</span></span> <span data-ttu-id="9b4f2-133">ただし; オーケストレーション変数とスコープ変数に同じ名前を使用することはできません。名前の隠ぺいすることはできません。</span><span class="sxs-lookup"><span data-stu-id="9b4f2-133">You cannot use the same name for a scope variable as for an orchestration variable, however; name hiding is not allowed.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="9b4f2-134">参照</span><span class="sxs-lookup"><span data-stu-id="9b4f2-134">See Also</span></span>  
 <span data-ttu-id="9b4f2-135">[トランザクションを使用して、例外の処理](../core/using-transactions-and-handling-exceptions.md) </span><span class="sxs-lookup"><span data-stu-id="9b4f2-135">[Using Transactions and Handling Exceptions](../core/using-transactions-and-handling-exceptions.md) </span></span>  
 [<span data-ttu-id="9b4f2-136">アトミック トランザクション</span><span class="sxs-lookup"><span data-stu-id="9b4f2-136">Atomic Transactions</span></span>](../core/atomic-transactions.md)