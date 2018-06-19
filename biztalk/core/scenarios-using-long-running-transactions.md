---
title: 実行時間の長いトランザクションの使用シナリオ |Microsoft ドキュメント
ms.custom: ''
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: ''
ms.suite: ''
ms.tgt_pltfrm: ''
ms.topic: article
helpviewer_keywords:
- transactions, long-running
- long-running transactions, timeouts
- transactions, examples
- long-running transactions, examples
- long-running compensations
- examples, long-running transactions
- examples, custom compensations
ms.assetid: 76b3e0f8-44dc-419e-a73a-c2908b1d8795
caps.latest.revision: 3
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: 05ac14bc6e333f963dda7cb9b33d1ebf371c0546
ms.sourcegitcommit: cb908c540d8f1a692d01dc8f313e16cb4b4e696d
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 09/20/2017
ms.locfileid: "22269922"
---
# <a name="scenarios-using-long-running-transactions"></a><span data-ttu-id="acd00-102">長時間トランザクションの使用シナリオ</span><span class="sxs-lookup"><span data-stu-id="acd00-102">Scenarios Using Long-Running Transactions</span></span>
<span data-ttu-id="acd00-103">次のシナリオでは、長時間トランザクションの使用方法について説明します。</span><span class="sxs-lookup"><span data-stu-id="acd00-103">The following scenarios describe the use of long running transactions.</span></span>  
  
## <a name="scenario-1-using-long-running-transactions-with-timeouts"></a><span data-ttu-id="acd00-104">シナリオ 1: 使用する長時間トランザクションとタイムアウト</span><span class="sxs-lookup"><span data-stu-id="acd00-104">Scenario 1: Using Long Running Transactions with Timeouts</span></span>  
 <span data-ttu-id="acd00-105">長時間スコープはタイムアウトに関連付けることができます。タイムアウトは、長時間実行される作業の実行時間の上限を表す論理時間です。</span><span class="sxs-lookup"><span data-stu-id="acd00-105">Long running scopes can be associated with a timeout, which is a logical time within which the long-running work must complete.</span></span> <span data-ttu-id="acd00-106">スコープが、定義済みのシステム例外、指定した時間内に完了しない場合**TimeoutException**が発生します。</span><span class="sxs-lookup"><span data-stu-id="acd00-106">If the scope does not complete within the specified time, a pre-defined system exception **TimeoutException** is raised.</span></span>  
  
 <span data-ttu-id="acd00-107">長時間プロセスは、オーケストレーション全体を長時間トランザクションとしてマークするか、外側の長時間スコープ内に他のスコープをネストすることによって作成できます。</span><span class="sxs-lookup"><span data-stu-id="acd00-107">You can create long running processes by either marking the entire orchestration as long running or having an outer long running scope nest any other scopes.</span></span> <span data-ttu-id="acd00-108">前者のシナリオではシステムに用意されている例外ハンドラーが実行され、後者のシナリオでは特定の例外ハンドラーを外側のスコープに関連付けることが可能になります。</span><span class="sxs-lookup"><span data-stu-id="acd00-108">In the former scenario, a system-provided exception handler runs, whereas the latter allows associating specific exception handlers to the outer scope.</span></span> <span data-ttu-id="acd00-109">システムに用意されている既定の例外ハンドラーは、ネストされたトランザクション スコープのうち正常に完了したスコープごとに、完了の順番とは逆の順番で補正ハンドラーを実行します。</span><span class="sxs-lookup"><span data-stu-id="acd00-109">The default system-provided exception handler will run the compensation handler for each of the successfully completed nested transactional scopes, if any, in reverse order of their completion.</span></span> <span data-ttu-id="acd00-110">長時間トランザクションの例外ハンドラーで補正図形を使用して自己補正を行った場合も、同じ結果が得られます。</span><span class="sxs-lookup"><span data-stu-id="acd00-110">You can achieve the same through self compensating by using the Compensate shape in the exception handler for a long running transaction.</span></span>  
  
 <span data-ttu-id="acd00-111">次のオーケストレーションは、タイムアウトを長時間トランザクションと関連付ける方法を表しています。</span><span class="sxs-lookup"><span data-stu-id="acd00-111">The following orchestration is a representation of how to associate timeouts with long running transactions.</span></span>  
  
 <span data-ttu-id="acd00-112">**実行時間の長いトランザクションとタイムアウト**</span><span class="sxs-lookup"><span data-stu-id="acd00-112">**Long running transactions with timeouts**</span></span>  
  
 <span data-ttu-id="acd00-113">![長時間トランザクションとタイムアウト](../core/media/bts-trans-orch-fig7.gif "BTS_Trans_Orch_Fig7")</span><span class="sxs-lookup"><span data-stu-id="acd00-113">![Long running transactions with timeouts](../core/media/bts-trans-orch-fig7.gif "BTS_Trans_Orch_Fig7")</span></span>  
  
 <span data-ttu-id="acd00-114">場合によっては、バッチ方式で動作するレガシ システムとの連携が必要になることがあります。</span><span class="sxs-lookup"><span data-stu-id="acd00-114">Sometimes you may need to interface with legacy systems that operate in a batch fashion.</span></span> <span data-ttu-id="acd00-115">このシナリオでは、レガシ システムとの間で注文書が送受信されています。</span><span class="sxs-lookup"><span data-stu-id="acd00-115">This scenario shows a purchase order being received and sent to the legacy system.</span></span> <span data-ttu-id="acd00-116">レガシ システムは注文書を処理し、注文書の受信確認を返します。</span><span class="sxs-lookup"><span data-stu-id="acd00-116">The legacy system processes the purchase order and sends back a purchase order acknowledgement.</span></span> <span data-ttu-id="acd00-117">送信操作では注文書番号によって関連付けセットが初期化され、その関連付けセットに従って受信操作が行われます。</span><span class="sxs-lookup"><span data-stu-id="acd00-117">The send operation initializes a correlation set using the purchase order number and the receive operation follows that correlation set.</span></span> <span data-ttu-id="acd00-118">受信操作も、タイムアウト値が設定された長時間スコープ内にあります。</span><span class="sxs-lookup"><span data-stu-id="acd00-118">The receive operation is also in a long running scope with a timeout value.</span></span>  
  
 <span data-ttu-id="acd00-119">受信を待機しているオーケストレーション インスタンスは、オーケストレーション エンジンによって退避されます。</span><span class="sxs-lookup"><span data-stu-id="acd00-119">The orchestration engine will dehydrate the orchestration instance waiting for the receive.</span></span> <span data-ttu-id="acd00-120">関連付けにより、メッセージの受信後に必ず同じオーケストレーション インスタンスが呼び出されるようになっています。</span><span class="sxs-lookup"><span data-stu-id="acd00-120">The correlation will ensure that the same orchestration instance is invoked after the message is received.</span></span> <span data-ttu-id="acd00-121">タイムアウト値で指定された時間間隔内では、購買注文の受信確認が配信されない場合、 **TimeoutException**がスローされます。</span><span class="sxs-lookup"><span data-stu-id="acd00-121">If the purchase order acknowledgement does not arrive within the time interval specified by the timeout values, a **TimeoutException** will be thrown.</span></span>  
  
## <a name="scenario-2-using-long-running-transactions-with-custom-compensation"></a><span data-ttu-id="acd00-122">シナリオ 2: が長時間トランザクションとカスタム補正を使用します。</span><span class="sxs-lookup"><span data-stu-id="acd00-122">Scenario 2: Using Long Running Transactions with Custom Compensation</span></span>  
 <span data-ttu-id="acd00-123">次のオーケストレーションは、オーケストレーション全体に関連付けられているカスタム補正の関連付けと呼び出しの方法を示しています。</span><span class="sxs-lookup"><span data-stu-id="acd00-123">The following orchestrations demonstrate how to associate and invoke custom compensations associated with entire orchestrations.</span></span> <span data-ttu-id="acd00-124">このシナリオでは、新しい顧客が挿入され、その顧客の注文明細が挿入されます。</span><span class="sxs-lookup"><span data-stu-id="acd00-124">This scenario inserts a new customer and inserts order details for the customer.</span></span> <span data-ttu-id="acd00-125">オーケストレーションのロジックによると、注文の挿入が失敗した場合は顧客の挿入をロールバックする必要があります。</span><span class="sxs-lookup"><span data-stu-id="acd00-125">The logic of the orchestration dictates that if the order insert fails, you should roll back the customer insert.</span></span> <span data-ttu-id="acd00-126">顧客の挿入はレガシ システムで行われる可能性があるため、別個の呼び出し可能なオーケストレーションで示されています。</span><span class="sxs-lookup"><span data-stu-id="acd00-126">The customer insert could be done by a legacy system, and is therefore, demonstrated in a separate callable orchestration.</span></span> <span data-ttu-id="acd00-127">呼び出されたオーケストレーションが、**カスタム**補正処理を行う別のシートを提供する補正のプロパティの設定。</span><span class="sxs-lookup"><span data-stu-id="acd00-127">The called orchestration has the **Custom** property set for compensation, which provides a separate sheet to do the compensation process.</span></span> <span data-ttu-id="acd00-128">補正を実行すると、新しく挿入した顧客が削除されます。</span><span class="sxs-lookup"><span data-stu-id="acd00-128">The compensation is to delete the newly inserted customer.</span></span>  
  
 <span data-ttu-id="acd00-129">呼び出し元オーケストレーションには、注文の挿入を行うための長時間スコープがあります。</span><span class="sxs-lookup"><span data-stu-id="acd00-129">The calling orchestration has a long running scope to do the order insert.</span></span> <span data-ttu-id="acd00-130">このスコープは、外側の長時間スコープ内にネストされています。</span><span class="sxs-lookup"><span data-stu-id="acd00-130">This scope is nested within an outer long running scope.</span></span> <span data-ttu-id="acd00-131">外側のスコープには、例外をキャッチする例外ハンドラーが関連付けられています。</span><span class="sxs-lookup"><span data-stu-id="acd00-131">The outer scope has an exception handler associated to catch any exceptions.</span></span> <span data-ttu-id="acd00-132">このハンドラーは、呼び出し先オーケストレーションに関連付けられているカスタム例外を補正図形で呼び出し、そのオーケストレーションの呼び出しで発生した可能性のある変更をすべてロールバックします。</span><span class="sxs-lookup"><span data-stu-id="acd00-132">The handler uses the Compensate shape to invoke the custom exception associated with the called orchestration to roll back any changes that might have occurred in the call to the orchestration.</span></span>  
  
 <span data-ttu-id="acd00-133">**実行時間の長いトランザクションとカスタム補正**</span><span class="sxs-lookup"><span data-stu-id="acd00-133">**Long running transactions with custom compensation**</span></span>  
  
 <span data-ttu-id="acd00-134">![長時間トランザクションとカスタム補正](../core/media/bts-trans-orch-fig8.gif "BTS_Trans_Orch_Fig8")</span><span class="sxs-lookup"><span data-stu-id="acd00-134">![Long running transactions with custom compensation](../core/media/bts-trans-orch-fig8.gif "BTS_Trans_Orch_Fig8")</span></span>  
  
 <span data-ttu-id="acd00-135">**呼び出し先オーケストレーション (メイン)**</span><span class="sxs-lookup"><span data-stu-id="acd00-135">**Called orchestration (main)**</span></span>  
  
 <span data-ttu-id="acd00-136">![呼び出されたオーケストレーション (&) #40 です。 メイン (&) #41;] (../core/media/bts-trans-orch-fig9.gif "BTS_Trans_Orch_Fig9")</span><span class="sxs-lookup"><span data-stu-id="acd00-136">![Called orchestration &#40;main&#41;](../core/media/bts-trans-orch-fig9.gif "BTS_Trans_Orch_Fig9")</span></span>  
  
 <span data-ttu-id="acd00-137">**呼び出し先オーケストレーション (補正)**</span><span class="sxs-lookup"><span data-stu-id="acd00-137">**Called orchestration (compensation)**</span></span>  
  
 <span data-ttu-id="acd00-138">![呼び出し先オーケストレーション (&) #40 です。 補正 (&) #41;] (../core/media/bts-trans-orch-fig10.gif "BTS_Trans_Orch_Fig10")</span><span class="sxs-lookup"><span data-stu-id="acd00-138">![Called orchestration &#40;compensation&#41;](../core/media/bts-trans-orch-fig10.gif "BTS_Trans_Orch_Fig10")</span></span>