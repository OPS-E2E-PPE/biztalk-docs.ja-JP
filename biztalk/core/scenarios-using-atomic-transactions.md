---
title: "アトミック トランザクションの使用シナリオ |Microsoft ドキュメント"
ms.custom: 
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: 
ms.suite: 
ms.tgt_pltfrm: 
ms.topic: article
helpviewer_keywords:
- Scope shape [Orchestration Designer], examples
- Scope shape [Orchestration Designer], atomic transactions
- transactions, examples
- transactions, atomic
- atomic transactions, examples
- examples, atomic transactions
ms.assetid: f3481b4e-7e7e-47f0-b8f4-6012a2fc5310
caps.latest.revision: "4"
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: e73cfea7a99e2fafbf115a367dbf0840de3369c3
ms.sourcegitcommit: cb908c540d8f1a692d01dc8f313e16cb4b4e696d
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 09/20/2017
---
# <a name="scenarios-using-atomic-transactions"></a><span data-ttu-id="96c87-102">アトミック トランザクションの使用シナリオ</span><span class="sxs-lookup"><span data-stu-id="96c87-102">Scenarios Using Atomic Transactions</span></span>
<span data-ttu-id="96c87-103">次のシナリオでは、アトミック トランザクションの使用方法について説明します。</span><span class="sxs-lookup"><span data-stu-id="96c87-103">The following scenarios describe the use of atomic transactions.</span></span>  
  
## <a name="scenario-1-an-atomic-transaction-with-com-servicedcomponent"></a><span data-ttu-id="96c87-104">シナリオ 1: アトミック トランザクションと COM + ServicedComponent</span><span class="sxs-lookup"><span data-stu-id="96c87-104">Scenario 1: An Atomic Transaction with COM+ ServicedComponent</span></span>  
 <span data-ttu-id="96c87-105">次のオーケストレーションを使用する方法を示しています、 **RetryTransactionException**とアトミック トランザクションです。</span><span class="sxs-lookup"><span data-stu-id="96c87-105">The following orchestration shows how to use the **RetryTransactionException** with atomic transactions.</span></span> <span data-ttu-id="96c87-106">例外ハンドラーはアトミックのスコープに直接含めることはできませんが、例外ハンドラーを持つ非トランザクション スコープはアトミックのスコープに含めることができます。</span><span class="sxs-lookup"><span data-stu-id="96c87-106">Although exception handlers cannot be directly included for an atomic scope, the scope can include a non-transactional scope that can have an exception handler.</span></span> <span data-ttu-id="96c87-107">**ServicedComponent**は同じ DTC トランザクションに参加し、コンポーネントによって発生する例外がキャッチされ、として再スロー **RetryTransactionException**です。</span><span class="sxs-lookup"><span data-stu-id="96c87-107">The **ServicedComponent** enlists in the same DTC transaction and any exception raised by the component is caught and re-thrown as **RetryTransactionException**.</span></span> <span data-ttu-id="96c87-108">(を想定しています、**再試行**プロパティに設定されている**True**アトミックのスコープに対して)。</span><span class="sxs-lookup"><span data-stu-id="96c87-108">(This assumes that the **Retry** property is set to **True** for the atomic scope).</span></span>  
  
 <span data-ttu-id="96c87-109">オーケストレーションは中断し、メッセージの割り当て図形の操作がロールバックされることを確認場合でも、 **RetryTransactionException**はスローされません。</span><span class="sxs-lookup"><span data-stu-id="96c87-109">Note that the orchestration would have been suspended and the action in the MessageAssignment shape would have been rolled back even if the **RetryTransactionException** is not thrown.</span></span> <span data-ttu-id="96c87-110">ただし、このパターンは、再試行が自動的に行われるアプリケーションでは回復性を高めることができます。</span><span class="sxs-lookup"><span data-stu-id="96c87-110">This pattern, however, allows building resilience in the application where the retries occur automatically.</span></span>  
  
 <span data-ttu-id="96c87-111">**アトミックのトランザクションと COM + ServicedComponent**</span><span class="sxs-lookup"><span data-stu-id="96c87-111">**An atomic transaction with COM+ ServicedComponent**</span></span>  
  
 <span data-ttu-id="96c87-112">![アトミック トランザクションと COM & #43 です。ServicedComponent](../core/media/bts-trans-orch-fig5.gif "BTS_Trans_Orch_Fig5")</span><span class="sxs-lookup"><span data-stu-id="96c87-112">![An atomic transaction with COM&#43; ServicedComponent](../core/media/bts-trans-orch-fig5.gif "BTS_Trans_Orch_Fig5")</span></span>  
  
## <a name="scenario-2-using-transacted-adapters-with-atomic-transactions"></a><span data-ttu-id="96c87-113">シナリオ 2: とアトミック トランザクションのトランザクション アダプターの使用</span><span class="sxs-lookup"><span data-stu-id="96c87-113">Scenario 2: Using Transacted Adapters with Atomic Transactions</span></span>  
 <span data-ttu-id="96c87-114">次のオーケストレーションでは、SQL アダプターをアトミック トランザクションと共に使用する方法について説明します。</span><span class="sxs-lookup"><span data-stu-id="96c87-114">The following orchestration shows how to use the atomic transactions with the SQL adapter.</span></span> <span data-ttu-id="96c87-115">オーケストレーション全体は、新しい顧客の挿入とその顧客の注文明細の挿入という 2 つの論理的な作業に対応する個別のアトミック トランザクションを含む長時間のオーケストレーションとしてマークされています。</span><span class="sxs-lookup"><span data-stu-id="96c87-115">The whole orchestration is marked as long running with individual atomic transactions for the two logical pieces of work: Inserting a new Customer and Insert Order details for the customer.</span></span>  
  
 <span data-ttu-id="96c87-116">注文の挿入が失敗した場合は、理由にかかわらず、顧客の挿入をロールバックする必要があります。</span><span class="sxs-lookup"><span data-stu-id="96c87-116">If, for whatever reason, the Order Insert fails, the Customer Insert should be rolled back.</span></span> <span data-ttu-id="96c87-117">この例では、データベース操作を行う SQL アダプターを使用します。</span><span class="sxs-lookup"><span data-stu-id="96c87-117">The sample uses the SQL adapter to do the database work.</span></span> <span data-ttu-id="96c87-118">前述したように、アトミック トランザクションに関連付けられたスコープは、メッセージがメッセージ ボックス データベースに送信された時点で完了します。</span><span class="sxs-lookup"><span data-stu-id="96c87-118">As mentioned earlier, the scope associated with an atomic transaction completes when the message is sent to the MessageBox database.</span></span> <span data-ttu-id="96c87-119">これは、エンジンが Scope_InsertCustomer スコープと Scope_InsertOrder スコープのメッセージを正常に送信した後で、各スコープがコミットすることを意味しています。</span><span class="sxs-lookup"><span data-stu-id="96c87-119">This implies that after the engine is successful in sending the message in the Scope_InsertCustomer and Scope_InsertOrder scopes, each one of the scopes commits.</span></span> <span data-ttu-id="96c87-120">SQL アダプターは、顧客または注文の実際の挿入に対して新しいトランザクションを作成します。</span><span class="sxs-lookup"><span data-stu-id="96c87-120">The SQL adapter creates a new transaction for the actual Insert of the Customer or the order.</span></span>  
  
 <span data-ttu-id="96c87-121">ポートには、メッセージが送信ポートから正常に送信されたことを確認するための “配信通知” プロパティがあります。</span><span class="sxs-lookup"><span data-stu-id="96c87-121">The Ports have a property “Delivery Notification” for validating that the message has been successfully sent via the Sent Port.</span></span> <span data-ttu-id="96c87-122">“配信通知” プロパティが “送信済み” に設定されている場合、受信サブスクリプションは送信操作のトランザクション コミット ポイントの前に配置されます。</span><span class="sxs-lookup"><span data-stu-id="96c87-122">When the Delivery Notification property is set to “Transmitted”, a receive subscription is placed before the Transactional commit point of the Send Operation.</span></span> <span data-ttu-id="96c87-123">ただし、アトミック スコープの場合、受信サブスクリプションはそれを含んでいる親スコープ内に配置されます。</span><span class="sxs-lookup"><span data-stu-id="96c87-123">However, in case of Atomic Scopes, the receive subscription is placed in the enclosing Parent scope.</span></span>  
  
 <span data-ttu-id="96c87-124">InsertOrder SQL トランザクションが失敗するシナリオでは、"NACK" が返信され、"Scope_InsertOrder" はコミットします。</span><span class="sxs-lookup"><span data-stu-id="96c87-124">In the scenario where the InsertOrder SQL transaction fails, a "Nack" will be sent back and the "Scope_InsertOrder" commits.</span></span> <span data-ttu-id="96c87-125">送信ポートが構成された回数の再試行を終えると、DeliveryFailureException が発生します。</span><span class="sxs-lookup"><span data-stu-id="96c87-125">After the Sent Port exhausts the configured retries, a DeliveryFailureException will be raised.</span></span> <span data-ttu-id="96c87-126">この例外は既定の例外ハンドラーによってキャッチされ、既定の補正プロセスが実行されます。</span><span class="sxs-lookup"><span data-stu-id="96c87-126">This exception will be caught by the default exception handler, which will run the default compensation process.</span></span> <span data-ttu-id="96c87-127">これにより、Scope_InsertCustomer および Scope_InsertOrder に関連付けられた補正ハンドラーが呼び出され、顧客情報の挿入を元に戻す操作が行われます。</span><span class="sxs-lookup"><span data-stu-id="96c87-127">This will invoke the compensation handlers associated with the Scope_InsertCustomer and Scope_InsertOrder, causing the undo operation of inserting the customer information.</span></span>  
  
> [!NOTE]
>  <span data-ttu-id="96c87-128">長時間スコープ内に 2 つのスコープを入れ子にし、長時間スコープの例外ハンドラーから長時間トランザクションをターゲットとする補正図形を呼び出すと、前述したものと同じ動作が行われます。</span><span class="sxs-lookup"><span data-stu-id="96c87-128">Nesting the two scopes in a long running scope and invoking the Compensate shape (targeting the long running transaction) from the exception handler for the long running scope will result in the same behavior as described above.</span></span> <span data-ttu-id="96c87-129">アトミック トランザクションでは入れ子になったトランザクションを許可していないため、オーケストレーション全体をアトミックとしてマークすることはできません。</span><span class="sxs-lookup"><span data-stu-id="96c87-129">The whole orchestration could not be marked atomic as atomic transactions do not allow nested transactions.</span></span>  
  
 <span data-ttu-id="96c87-130">**トランザクション アダプターとアトミック トランザクション**</span><span class="sxs-lookup"><span data-stu-id="96c87-130">**Transacted adapters with atomic transactions**</span></span>  
  
 <span data-ttu-id="96c87-131">![アダプターとアトミック トランザクションをトランザクション](../core/media/bts-trans-orch-fig6.gif "BTS_Trans_Orch_Fig6")</span><span class="sxs-lookup"><span data-stu-id="96c87-131">![Transacted adapters with atomic transactions](../core/media/bts-trans-orch-fig6.gif "BTS_Trans_Orch_Fig6")</span></span>