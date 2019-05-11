---
title: スコープ |Microsoft Docs
ms.custom: ''
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: ''
ms.suite: ''
ms.tgt_pltfrm: ''
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
caps.latest.revision: 11
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: 67d10fa444b8bf5a427fe48c70655c233f06eef9
ms.sourcegitcommit: 381e83d43796a345488d54b3f7413e11d56ad7be
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 05/07/2019
ms.locfileid: "65395534"
---
# <a name="scopes"></a><span data-ttu-id="7fc7d-102">スコープ</span><span class="sxs-lookup"><span data-stu-id="7fc7d-102">Scopes</span></span>
<span data-ttu-id="7fc7d-103">スコープとは、アクションをグループ化するためのフレームワークです。</span><span class="sxs-lookup"><span data-stu-id="7fc7d-103">A scope is a framework for grouping actions.</span></span> <span data-ttu-id="7fc7d-104">トランザクションの実行および例外処理には主に使用します。</span><span class="sxs-lookup"><span data-stu-id="7fc7d-104">It is primarily used for transactional execution and exception handling.</span></span>  
  
 <span data-ttu-id="7fc7d-105">1 つのスコープには、1 つ以上のブロックが含まれます。</span><span class="sxs-lookup"><span data-stu-id="7fc7d-105">A scope contains one or more blocks.</span></span> <span data-ttu-id="7fc7d-106">本文が含まれるは必要に応じてが追加された任意の数の例外処理ブロック。</span><span class="sxs-lookup"><span data-stu-id="7fc7d-106">It has a body and can optionally have appended to it any number of exception-handling blocks.</span></span> <span data-ttu-id="7fc7d-107">スコープの性質によって、オプションの補正ブロックを同様があります。</span><span class="sxs-lookup"><span data-stu-id="7fc7d-107">It may have an optional compensation block as well, depending on the nature of the scope.</span></span> <span data-ttu-id="7fc7d-108">いくつかのスコープを使用して、例外の処理だけになります、補正は必要ありません。</span><span class="sxs-lookup"><span data-stu-id="7fc7d-108">Some scopes will be purely for exception handling, and will not require compensation.</span></span> <span data-ttu-id="7fc7d-109">他のスコープを明示的にトランザクションにして、オプションの補正ハンドラーを作成すると共に、既定の補正ハンドラーが常に使用します。</span><span class="sxs-lookup"><span data-stu-id="7fc7d-109">Other scopes will be explicitly transactional, and will always have a default compensation handler, along with an optional compensation handler that you create for it.</span></span> <span data-ttu-id="7fc7d-110">既定の例外ハンドラーと任意の数の用に作成した追加の例外ハンドラー、トランザクション スコープがあります。</span><span class="sxs-lookup"><span data-stu-id="7fc7d-110">A transactional scope will also have a default exception handler and any number of additional exception handlers that you create for it.</span></span>  
  
## <a name="synchronized-scopes"></a><span data-ttu-id="7fc7d-111">同期スコープ</span><span class="sxs-lookup"><span data-stu-id="7fc7d-111">Synchronized scopes</span></span>  
 <span data-ttu-id="7fc7d-112">スコープを同期または同期されていないことを指定することができます。</span><span class="sxs-lookup"><span data-stu-id="7fc7d-112">You can specify that scopes are synchronized or not synchronized.</span></span> <span data-ttu-id="7fc7d-113">スコープを同期することによって内でアクセスがすべての共有データは書き込まれませんにオーケストレーションでの 1 つまたは複数の並列アクションでもないことに書き込まれる、別のアクションが読み取り中にことを確認します。</span><span class="sxs-lookup"><span data-stu-id="7fc7d-113">By synchronizing a scope, you ensure that any shared data that is accessed within it will not be written to by one or more parallel actions in your orchestration, nor will it be written to while another action is reading it.</span></span>  
  
 <span data-ttu-id="7fc7d-114">アトミック トランザクション スコープは常に同期します。</span><span class="sxs-lookup"><span data-stu-id="7fc7d-114">Atomic transaction scopes are always synchronized.</span></span> <span data-ttu-id="7fc7d-115">その例外ハンドラーのいずれかですべてのアクションとして、同期が、同期のスコープ内のすべてのアクションに扱われます。</span><span class="sxs-lookup"><span data-stu-id="7fc7d-115">All actions within a synchronized scope are considered synchronized, as are all actions in any of its exception handlers.</span></span> <span data-ttu-id="7fc7d-116">トランザクション スコープの補正ハンドラーのアクションは同期されません。</span><span class="sxs-lookup"><span data-stu-id="7fc7d-116">Actions in the compensation handler for a transactional scope are not synchronized.</span></span>  
  
> [!CAUTION]
>  <span data-ttu-id="7fc7d-117">実行できることも、デッドロック状態に、プロセスを慎重にデザインしない場合に注意してください。</span><span class="sxs-lookup"><span data-stu-id="7fc7d-117">Note that you can still run into a deadlock condition if you do not design your processes carefully.</span></span> <span data-ttu-id="7fc7d-118">例: オーケストレーション A での並列の 2 つの分岐が、同じメッセージをアクセス、1 つに送信してこのため、両方を受信する同期のスコープでなければなりません。</span><span class="sxs-lookup"><span data-stu-id="7fc7d-118">For example: two branches of a parallel in orchestration A access the same message, one to send it and one to receive it, so both must have a synchronized scope.</span></span> <span data-ttu-id="7fc7d-119">2 番目のオーケストレーションはメッセージを受信し、返信します。</span><span class="sxs-lookup"><span data-stu-id="7fc7d-119">A second orchestration receives the message and sends it back.</span></span> <span data-ttu-id="7fc7d-120">オーケストレーション A の送信元のブランチには、受信側の分岐では、前にロックを受信、デッドロックが終了ことができます。</span><span class="sxs-lookup"><span data-stu-id="7fc7d-120">It is possible that the sending branch in orchestration A will receive its locks before the receiving branch, and you will end up with a deadlock.</span></span>  
  
## <a name="nesting-of-scopes"></a><span data-ttu-id="7fc7d-121">スコープの入れ子</span><span class="sxs-lookup"><span data-stu-id="7fc7d-121">Nesting of scopes</span></span>  
 <span data-ttu-id="7fc7d-122">入れ子にすることができます**スコープ**他の内部の図形**スコープ**図形。</span><span class="sxs-lookup"><span data-stu-id="7fc7d-122">You can nest **Scope** shapes inside other **Scope** shapes.</span></span> <span data-ttu-id="7fc7d-123">入れ子スコープの規則は次のとおりです。</span><span class="sxs-lookup"><span data-stu-id="7fc7d-123">The rules for nesting scopes are as follows:</span></span>  
  
-   <span data-ttu-id="7fc7d-124">同期スコープの例外ハンドラーを含む、同期のスコープ内では、トランザクションまたは同期スコープを入れ子にすることはできません。</span><span class="sxs-lookup"><span data-stu-id="7fc7d-124">Transactional and/or synchronized scopes cannot be nested inside synchronized scopes, including the exception handlers of synchronized scopes.</span></span>  
  
-   <span data-ttu-id="7fc7d-125">アトミック トランザクション スコープは、その内部に入れ子になった他のトランザクション スコープを持つことはできません。</span><span class="sxs-lookup"><span data-stu-id="7fc7d-125">Atomic transaction scopes cannot have any other transactional scopes nested inside them.</span></span>  
  
-   <span data-ttu-id="7fc7d-126">トランザクション スコープは、トランザクションでないスコープまたはオーケストレーション内で入れ子にすることはできません。</span><span class="sxs-lookup"><span data-stu-id="7fc7d-126">Transactional scopes cannot be nested inside nontransactional scopes or orchestrations.</span></span>  
  
-   <span data-ttu-id="7fc7d-127">21 レベルの深さの最大スコープを入れ子にすることができます。</span><span class="sxs-lookup"><span data-stu-id="7fc7d-127">You can nest scopes up to 21 levels deep.</span></span>  
  
-   <span data-ttu-id="7fc7d-128">**オーケストレーションの呼び出し**図形は、スコープ内に含めることができますが、呼び出されたオーケストレーションが扱われます、トランザクションを入れ子になった他と同じと同じ規則が適用されます。</span><span class="sxs-lookup"><span data-stu-id="7fc7d-128">**Call Orchestration** shapes can be included inside scopes, but the called orchestrations are treated the same as any other nested transaction, and the same rules apply.</span></span>  
  
-   <span data-ttu-id="7fc7d-129">**オーケストレーションを開始**図形はスコープ内に含めることができます。</span><span class="sxs-lookup"><span data-stu-id="7fc7d-129">**Start Orchestration** shapes can be included inside scopes.</span></span> <span data-ttu-id="7fc7d-130">入れ子に関する制限事項は、開始したオーケストレーションには適用されません。</span><span class="sxs-lookup"><span data-stu-id="7fc7d-130">Nesting limitations do not apply to started orchestrations.</span></span>  
  
## <a name="scope-variables"></a><span data-ttu-id="7fc7d-131">スコープ変数</span><span class="sxs-lookup"><span data-stu-id="7fc7d-131">Scope variables</span></span>  
 <span data-ttu-id="7fc7d-132">メッセージなどの変数を宣言することができ、相関関係は、スコープ レベルで設定します。</span><span class="sxs-lookup"><span data-stu-id="7fc7d-132">You can declare variables such as messages and correlation sets at the scope level.</span></span> <span data-ttu-id="7fc7d-133">ただし、同じオーケストレーション変数とスコープ変数の名前を使用することはできません。名前の非表示にすることはできません。</span><span class="sxs-lookup"><span data-stu-id="7fc7d-133">You cannot use the same name for a scope variable as for an orchestration variable, however; name hiding is not allowed.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="7fc7d-134">参照</span><span class="sxs-lookup"><span data-stu-id="7fc7d-134">See Also</span></span>  
 <span data-ttu-id="7fc7d-135">[トランザクションを使用して、例外の処理](../core/using-transactions-and-handling-exceptions.md) </span><span class="sxs-lookup"><span data-stu-id="7fc7d-135">[Using Transactions and Handling Exceptions](../core/using-transactions-and-handling-exceptions.md) </span></span>  
 [<span data-ttu-id="7fc7d-136">自動トランザクション</span><span class="sxs-lookup"><span data-stu-id="7fc7d-136">Atomic Transactions</span></span>](../core/atomic-transactions.md)