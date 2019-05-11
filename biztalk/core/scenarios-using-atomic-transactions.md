---
title: アトミック トランザクションの使用シナリオ |Microsoft Docs
ms.custom: ''
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: ''
ms.suite: ''
ms.tgt_pltfrm: ''
ms.topic: article
helpviewer_keywords:
- Scope shape [Orchestration Designer], examples
- Scope shape [Orchestration Designer], atomic transactions
- transactions, examples
- transactions, atomic
- atomic transactions, examples
- examples, atomic transactions
ms.assetid: f3481b4e-7e7e-47f0-b8f4-6012a2fc5310
caps.latest.revision: 4
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: d959fdb9135a804346a869811072f826906b5876
ms.sourcegitcommit: 381e83d43796a345488d54b3f7413e11d56ad7be
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 05/07/2019
ms.locfileid: "65308165"
---
# <a name="scenarios-using-atomic-transactions"></a><span data-ttu-id="f3fc2-102">アトミック トランザクションの使用シナリオ</span><span class="sxs-lookup"><span data-stu-id="f3fc2-102">Scenarios Using Atomic Transactions</span></span>
<span data-ttu-id="f3fc2-103">次のシナリオでは、アトミック トランザクションの使用方法について説明します。</span><span class="sxs-lookup"><span data-stu-id="f3fc2-103">The following scenarios describe the use of atomic transactions.</span></span>  
  
## <a name="scenario-1-an-atomic-transaction-with-com-servicedcomponent"></a><span data-ttu-id="f3fc2-104">シナリオ 1:アトミックのトランザクションと COM + ServicedComponent</span><span class="sxs-lookup"><span data-stu-id="f3fc2-104">Scenario 1: An Atomic Transaction with COM+ ServicedComponent</span></span>  
 <span data-ttu-id="f3fc2-105">次のオーケストレーションを使用する方法を示しています、 **RetryTransactionException**とアトミック トランザクション。</span><span class="sxs-lookup"><span data-stu-id="f3fc2-105">The following orchestration shows how to use the **RetryTransactionException** with atomic transactions.</span></span> <span data-ttu-id="f3fc2-106">例外ハンドラーが直接にすることはできませんが、アトミックのスコープに含まれる、スコープは、例外ハンドラーを持つことができますを非トランザクション スコープを含めることができます。</span><span class="sxs-lookup"><span data-stu-id="f3fc2-106">Although exception handlers cannot be directly included for an atomic scope, the scope can include a non-transactional scope that can have an exception handler.</span></span> <span data-ttu-id="f3fc2-107">**ServicedComponent**は同じ DTC トランザクションに参加し、コンポーネントによって発生する例外がキャッチされ、再度としてスロー **RetryTransactionException**します。</span><span class="sxs-lookup"><span data-stu-id="f3fc2-107">The **ServicedComponent** enlists in the same DTC transaction and any exception raised by the component is caught and re-thrown as **RetryTransactionException**.</span></span> <span data-ttu-id="f3fc2-108">(が、**再試行**プロパティに設定されて**True**アトミックのスコープに対して)。</span><span class="sxs-lookup"><span data-stu-id="f3fc2-108">(This assumes that the **Retry** property is set to **True** for the atomic scope).</span></span>  
  
 <span data-ttu-id="f3fc2-109">オーケストレーション中断されたとメッセージの割り当て図形の操作がロールバックされる場合でも、 **RetryTransactionException**はスローされません。</span><span class="sxs-lookup"><span data-stu-id="f3fc2-109">Note that the orchestration would have been suspended and the action in the MessageAssignment shape would have been rolled back even if the **RetryTransactionException** is not thrown.</span></span> <span data-ttu-id="f3fc2-110">このパターンでは、ただし、により、アプリケーションの回復性を高める、再試行が自動的に発生します。</span><span class="sxs-lookup"><span data-stu-id="f3fc2-110">This pattern, however, allows building resilience in the application where the retries occur automatically.</span></span>  
  
 <span data-ttu-id="f3fc2-111">**アトミックのトランザクションと COM + ServicedComponent**</span><span class="sxs-lookup"><span data-stu-id="f3fc2-111">**An atomic transaction with COM+ ServicedComponent**</span></span>  
  
 <span data-ttu-id="f3fc2-112">![アトミック トランザクションと COM&#43; ServicedComponent](../core/media/bts-trans-orch-fig5.gif "BTS_Trans_Orch_Fig5")</span><span class="sxs-lookup"><span data-stu-id="f3fc2-112">![An atomic transaction with COM&#43; ServicedComponent](../core/media/bts-trans-orch-fig5.gif "BTS_Trans_Orch_Fig5")</span></span>  
  
## <a name="scenario-2-using-transacted-adapters-with-atomic-transactions"></a><span data-ttu-id="f3fc2-113">シナリオ 2: アトミック トランザクションのトランザクション アダプターを使用します。</span><span class="sxs-lookup"><span data-stu-id="f3fc2-113">Scenario 2: Using Transacted Adapters with Atomic Transactions</span></span>  
 <span data-ttu-id="f3fc2-114">次のオーケストレーションは、SQL アダプターとアトミック トランザクションを使用する方法を示します。</span><span class="sxs-lookup"><span data-stu-id="f3fc2-114">The following orchestration shows how to use the atomic transactions with the SQL adapter.</span></span> <span data-ttu-id="f3fc2-115">オーケストレーション全体は、2 つの論理部分の作業の個々 のアトミック トランザクションの実行時間が長いでマークされます。顧客の新しい顧客と注文の挿入の詳細を挿入しています。</span><span class="sxs-lookup"><span data-stu-id="f3fc2-115">The whole orchestration is marked as long running with individual atomic transactions for the two logical pieces of work: Inserting a new Customer and Insert Order details for the customer.</span></span>  
  
 <span data-ttu-id="f3fc2-116">何らかの理由で注文の挿入が失敗する場合は、顧客の挿入ロールバックするか。</span><span class="sxs-lookup"><span data-stu-id="f3fc2-116">If, for whatever reason, the Order Insert fails, the Customer Insert should be rolled back.</span></span> <span data-ttu-id="f3fc2-117">サンプルでは、データベースの作業を行う SQL アダプタを使用します。</span><span class="sxs-lookup"><span data-stu-id="f3fc2-117">The sample uses the SQL adapter to do the database work.</span></span> <span data-ttu-id="f3fc2-118">前述のように、メッセージ ボックス データベースにメッセージが送信されるときに、アトミック トランザクションに関連付けられたスコープを完了します。</span><span class="sxs-lookup"><span data-stu-id="f3fc2-118">As mentioned earlier, the scope associated with an atomic transaction completes when the message is sent to the MessageBox database.</span></span> <span data-ttu-id="f3fc2-119">つまり、エンジンが Scope_InsertCustomer および Scope_InsertOrder スコープでメッセージの送信に成功した後は、各スコープのコミットすることです。</span><span class="sxs-lookup"><span data-stu-id="f3fc2-119">This implies that after the engine is successful in sending the message in the Scope_InsertCustomer and Scope_InsertOrder scopes, each one of the scopes commits.</span></span> <span data-ttu-id="f3fc2-120">SQL アダプターは、顧客または注文の実際の挿入に対して新しいトランザクションを作成します。</span><span class="sxs-lookup"><span data-stu-id="f3fc2-120">The SQL adapter creates a new transaction for the actual Insert of the Customer or the order.</span></span>  
  
 <span data-ttu-id="f3fc2-121">ポートでは、メッセージが送信ポートから正常に送信された検証するためプロパティ「配信通知」があります。</span><span class="sxs-lookup"><span data-stu-id="f3fc2-121">The Ports have a property “Delivery Notification” for validating that the message has been successfully sent via the Sent Port.</span></span> <span data-ttu-id="f3fc2-122">配信通知プロパティが「送信済み」に設定されている場合、受信サブスクリプションは、送信操作のトランザクション コミット ポイントの前に配置されます。</span><span class="sxs-lookup"><span data-stu-id="f3fc2-122">When the Delivery Notification property is set to “Transmitted”, a receive subscription is placed before the Transactional commit point of the Send Operation.</span></span> <span data-ttu-id="f3fc2-123">ただし、アトミックのスコープの場合は、受信サブスクリプションは、外側の親スコープに配置されます。</span><span class="sxs-lookup"><span data-stu-id="f3fc2-123">However, in case of Atomic Scopes, the receive subscription is placed in the enclosing Parent scope.</span></span>  
  
 <span data-ttu-id="f3fc2-124">InsertOrder SQL トランザクションが失敗するシナリオでは、戻る ボタンと"Scope_InsertOrder"コミット"Nack"が送信されます。</span><span class="sxs-lookup"><span data-stu-id="f3fc2-124">In the scenario where the InsertOrder SQL transaction fails, a "Nack" will be sent back and the "Scope_InsertOrder" commits.</span></span> <span data-ttu-id="f3fc2-125">送信ポートが構成されている再試行では、後に、DeliveryFailureException が生成されます。</span><span class="sxs-lookup"><span data-stu-id="f3fc2-125">After the Sent Port exhausts the configured retries, a DeliveryFailureException will be raised.</span></span> <span data-ttu-id="f3fc2-126">この例外は、既定の補正プロセスが実行される既定の例外ハンドラーによってキャッチされます。</span><span class="sxs-lookup"><span data-stu-id="f3fc2-126">This exception will be caught by the default exception handler, which will run the default compensation process.</span></span> <span data-ttu-id="f3fc2-127">これにより、Scope_InsertCustomer および Scope_InsertOrder、顧客情報の挿入元に戻す操作の原因に関連付けられている補正ハンドラーが呼び出されます。</span><span class="sxs-lookup"><span data-stu-id="f3fc2-127">This will invoke the compensation handlers associated with the Scope_InsertCustomer and Scope_InsertOrder, causing the undo operation of inserting the customer information.</span></span>  
  
> [!NOTE]
>  <span data-ttu-id="f3fc2-128">長時間スコープ内の 2 つのスコープの入れ子と長時間スコープの例外ハンドラーから補正図形 (実行時間の長いトランザクションを対象とする) を呼び出すことが前述のように同じ動作に発生します。</span><span class="sxs-lookup"><span data-stu-id="f3fc2-128">Nesting the two scopes in a long running scope and invoking the Compensate shape (targeting the long running transaction) from the exception handler for the long running scope will result in the same behavior as described above.</span></span> <span data-ttu-id="f3fc2-129">オーケストレーション全体でしたいないアトミックとしてマークするアトミック トランザクションは、入れ子になったトランザクションを許可しません。</span><span class="sxs-lookup"><span data-stu-id="f3fc2-129">The whole orchestration could not be marked atomic as atomic transactions do not allow nested transactions.</span></span>  
  
 <span data-ttu-id="f3fc2-130">**トランザクション アダプターとアトミック トランザクション**</span><span class="sxs-lookup"><span data-stu-id="f3fc2-130">**Transacted adapters with atomic transactions**</span></span>  
  
 <span data-ttu-id="f3fc2-131">![アダプターとアトミック トランザクションをトランザクション](../core/media/bts-trans-orch-fig6.gif "BTS_Trans_Orch_Fig6")</span><span class="sxs-lookup"><span data-stu-id="f3fc2-131">![Transacted adapters with atomic transactions](../core/media/bts-trans-orch-fig6.gif "BTS_Trans_Orch_Fig6")</span></span>