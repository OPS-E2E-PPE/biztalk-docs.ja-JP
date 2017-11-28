---
title: "トランザクションを使用して、例外の処理 |Microsoft ドキュメント"
ms.custom: 
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: 
ms.suite: 
ms.tgt_pltfrm: 
ms.topic: article
helpviewer_keywords:
- transactions, orchestrations
- orchestrations, transactions
- orchestrations, errors
- transactions
- errors, orchestrations
- transactions, BizTalk Server Orchestration Engine
- errors, Scope shape [Orchestration Designer]
- Scope shape [Orchestration Designer], errors
- Scope shape [Orchestration Designer], transactions
ms.assetid: bb38f5eb-6641-4e7c-8e2a-c474fc739999
caps.latest.revision: "11"
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: ab32729aa6b4f12aada623587f52728c6bd23240
ms.sourcegitcommit: cb908c540d8f1a692d01dc8f313e16cb4b4e696d
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 09/20/2017
---
# <a name="using-transactions-and-handling-exceptions"></a><span data-ttu-id="133ad-102">トランザクションを使用して、例外の処理</span><span class="sxs-lookup"><span data-stu-id="133ad-102">Using Transactions and Handling Exceptions</span></span>
<span data-ttu-id="133ad-103">オーケストレーションのデザイン時には、問題が発生する可能性のある場所とその最善の対処方法について十分に考慮する必要があります。</span><span class="sxs-lookup"><span data-stu-id="133ad-103">When you design an orchestration, you should consider carefully where problems might occur and how best to deal with them.</span></span> <span data-ttu-id="133ad-104">オーケストレーションの多くは、エラーが発生する可能性のあるいくつかの処理を抱えています。</span><span class="sxs-lookup"><span data-stu-id="133ad-104">Many orchestrations have several potential points of failure.</span></span> <span data-ttu-id="133ad-105">問題が発生する理由は他にも考えられます。たとえば、サーバーのダウンやメッセージ形式の誤りなどです。</span><span class="sxs-lookup"><span data-stu-id="133ad-105">Problems can arise for any number of other reasons; for example, a server might go down or a message might be badly formatted.</span></span>  
  
 <span data-ttu-id="133ad-106">長時間実行または複雑なオーケストレーションでは、状態を追跡してエラー発生時に報告し、問題を的確に、最小限の労力で解決できるようにすることが特に重要です。</span><span class="sxs-lookup"><span data-stu-id="133ad-106">It is especially important for a long-running or complex orchestration to keep track of its state and to report errors as they occur, so that you can resolve problems accurately and with a minimum of effort.</span></span> <span data-ttu-id="133ad-107">これは、方法と考えたようバックアップ全体のトランザクションをロールバックできます行われるトランザクションの一部別されない場合は、できるように、密接に関連するアクションのセットの整合性を維持するためのオーケストレーションの同様に重要です。</span><span class="sxs-lookup"><span data-stu-id="133ad-107">It is equally important for an orchestration to maintain the integrity of a set of closely related actions, so that if part of a transaction takes place but another does not, the entire transaction can be rolled back as though it never occurred.</span></span>  
  
 <span data-ttu-id="133ad-108">BizTalk オーケストレーションでは、トランザクションに外部システムがかかわっている場合でも、作業の原子性 (関連するアクションの整合性) が確保されます。</span><span class="sxs-lookup"><span data-stu-id="133ad-108">BizTalk Orchestration enables you to guarantee the atomicity of work, that is, the integrity of related actions, even when external systems are participating in transactions.</span></span> <span data-ttu-id="133ad-109">エラーを処理し、オーケストレーションの状態を維持し、トランザクション、補正、および例外処理を通じて発生する問題を修正する手段を提供します。</span><span class="sxs-lookup"><span data-stu-id="133ad-109">It gives you tools to handle errors, to maintain the state of an orchestration, and to fix problems as they occur through transactions, compensation, and exception handling.</span></span>  
  
 <span data-ttu-id="133ad-110">オーケストレーション デザイナーにはトランザクションと例外処理のフレームワーク、として、**スコープ**図形です。</span><span class="sxs-lookup"><span data-stu-id="133ad-110">As a framework for transactions and exception handling, Orchestration Designer provides the **Scope** shape.</span></span> <span data-ttu-id="133ad-111">スコープには、トランザクションの種類、補正、および任意の数の例外ハンドラーを設定できます。</span><span class="sxs-lookup"><span data-stu-id="133ad-111">A scope can have a transaction type, a compensation, and any number of exception handlers.</span></span>  
  
 <span data-ttu-id="133ad-112">トランザクションと例外処理を設定する手順を次に示します。</span><span class="sxs-lookup"><span data-stu-id="133ad-112">The steps for setting up a transaction and exception handling are:</span></span>  
  
-   <span data-ttu-id="133ad-113">スコープを作成します。</span><span class="sxs-lookup"><span data-stu-id="133ad-113">Create a scope.</span></span>  
  
-   <span data-ttu-id="133ad-114">必要なトランザクションの種類を特定します。</span><span class="sxs-lookup"><span data-stu-id="133ad-114">Identify the kind of transaction you need.</span></span>  
  
-   <span data-ttu-id="133ad-115">補正する必要のあるものを決定します。</span><span class="sxs-lookup"><span data-stu-id="133ad-115">Determine what will need to be compensated.</span></span>  
  
-   <span data-ttu-id="133ad-116">発生する可能性のあるエラーを特定します。</span><span class="sxs-lookup"><span data-stu-id="133ad-116">Identify potential errors.</span></span>  
  
-   <span data-ttu-id="133ad-117">適切な例外ハンドラーと補正コードを追加します。</span><span class="sxs-lookup"><span data-stu-id="133ad-117">Add appropriate exception handlers and compensation code.</span></span>  
  
## <a name="examples-of-using-transactions-exception-handlings-and-compensations"></a><span data-ttu-id="133ad-118">トランザクションの使用、例外処理および補正の例</span><span class="sxs-lookup"><span data-stu-id="133ad-118">Examples of Using Transactions, Exception Handlings, and Compensations</span></span>  
  
-   [<span data-ttu-id="133ad-119">エラー処理 (BizTalk Server Samples フォルダ)</span><span class="sxs-lookup"><span data-stu-id="133ad-119">Error Handling (BizTalk Server Samples Folder)</span></span>](../core/error-handling-biztalk-server-samples-folder.md)  
  
-   [<span data-ttu-id="133ad-120">補正 (BizTalk Server サンプル)</span><span class="sxs-lookup"><span data-stu-id="133ad-120">Compensation (BizTalk Server Sample)</span></span>](../core/compensation-biztalk-server-sample.md)  
  
-   <span data-ttu-id="133ad-121">サンプルをダウンロードする SDK「オーケストレーション アトミック トランザクションと COM + サービス コンポーネントで」から[http://go.microsoft.com/fwlink/?LinkId=73703](http://go.microsoft.com/fwlink/?LinkId=73703)です。</span><span class="sxs-lookup"><span data-stu-id="133ad-121">Download the SDK sample "Atomic Transactions with COM+ Serviced Components in Orchestrations" from [http://go.microsoft.com/fwlink/?LinkId=73703](http://go.microsoft.com/fwlink/?LinkId=73703).</span></span>  
  
-   <span data-ttu-id="133ad-122">サンプルをダウンロードする SDK「を使用して、アダプターとアトミック トランザクション オーケストレーションでの SQL」から[http://go.microsoft.com/fwlink/?LinkId=73703](http://go.microsoft.com/fwlink/?LinkId=73703)です。</span><span class="sxs-lookup"><span data-stu-id="133ad-122">Download the SDK sample "Using the SQL Adapter with Atomic Transactions in Orchestrations" from [http://go.microsoft.com/fwlink/?LinkId=73703](http://go.microsoft.com/fwlink/?LinkId=73703).</span></span>  
  
-   <span data-ttu-id="133ad-123">サンプルをダウンロードする SDK「オーケストレーションでの実行時間の長いトランザクションの使用」から[http://go.microsoft.com/fwlink/?LinkId=73703](http://go.microsoft.com/fwlink/?LinkId=73703)です。</span><span class="sxs-lookup"><span data-stu-id="133ad-123">Download the SDK sample "Using Long-Running Transactions in Orchestrations" from [http://go.microsoft.com/fwlink/?LinkId=73703](http://go.microsoft.com/fwlink/?LinkId=73703).</span></span>  
  
-   <span data-ttu-id="133ad-124">SDK サンプル「オーケストレーションで例外を処理」をダウンロード[http://go.microsoft.com/fwlink/?LinkId=73703](http://go.microsoft.com/fwlink/?LinkId=73703)です。</span><span class="sxs-lookup"><span data-stu-id="133ad-124">Download the SDK sample "Exception Handling in Orchestrations" from [http://go.microsoft.com/fwlink/?LinkId=73703](http://go.microsoft.com/fwlink/?LinkId=73703).</span></span>  
  
## <a name="in-this-section"></a><span data-ttu-id="133ad-125">このセクションの内容</span><span class="sxs-lookup"><span data-stu-id="133ad-125">In This Section</span></span>  
  
-   [<span data-ttu-id="133ad-126">スコープ</span><span class="sxs-lookup"><span data-stu-id="133ad-126">Scopes</span></span>](../core/scopes.md)  
  
-   [<span data-ttu-id="133ad-127">スコープ図形を構成する方法</span><span class="sxs-lookup"><span data-stu-id="133ad-127">How to Configure the Scope Shape</span></span>](../core/how-to-configure-the-scope-shape.md)  
  
-   [<span data-ttu-id="133ad-128">トランザクション オーケストレーションを行う</span><span class="sxs-lookup"><span data-stu-id="133ad-128">Making Orchestrations Transactional</span></span>](../core/making-orchestrations-transactional.md)  
  
-   [<span data-ttu-id="133ad-129">例外</span><span class="sxs-lookup"><span data-stu-id="133ad-129">Exceptions</span></span>](../core/exceptions.md)  
  
-   [<span data-ttu-id="133ad-130">補正</span><span class="sxs-lookup"><span data-stu-id="133ad-130">Compensation</span></span>](../core/compensation.md)  
  
## <a name="see-also"></a><span data-ttu-id="133ad-131">参照</span><span class="sxs-lookup"><span data-stu-id="133ad-131">See Also</span></span>  
 [<span data-ttu-id="133ad-132">BizTalk メッセージング エンジンを使用します。</span><span class="sxs-lookup"><span data-stu-id="133ad-132">Using the BizTalk Messaging Engine</span></span>](../core/using-the-biztalk-messaging-engine.md)