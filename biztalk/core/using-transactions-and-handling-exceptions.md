---
title: トランザクションを使用して、例外の処理 |Microsoft Docs
ms.custom: ''
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: ''
ms.suite: ''
ms.tgt_pltfrm: ''
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
caps.latest.revision: 11
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: eac1ae71e9ff176156691fbb30a79c9d423b58da
ms.sourcegitcommit: 381e83d43796a345488d54b3f7413e11d56ad7be
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 05/07/2019
ms.locfileid: "65396749"
---
# <a name="using-transactions-and-handling-exceptions"></a><span data-ttu-id="d28cd-102">トランザクションを使用して、例外の処理</span><span class="sxs-lookup"><span data-stu-id="d28cd-102">Using Transactions and Handling Exceptions</span></span>
<span data-ttu-id="d28cd-103">オーケストレーションを設計するときは慎重に考慮する問題が発生する可能性とそれらに対処する最適な方法です。</span><span class="sxs-lookup"><span data-stu-id="d28cd-103">When you design an orchestration, you should consider carefully where problems might occur and how best to deal with them.</span></span> <span data-ttu-id="d28cd-104">多くのオーケストレーションでは、いくつかの潜在的な障害点があります。</span><span class="sxs-lookup"><span data-stu-id="d28cd-104">Many orchestrations have several potential points of failure.</span></span> <span data-ttu-id="d28cd-105">問題は、任意の数の他の理由が発生します。たとえば、サーバー ダウンまたはメッセージの形式が正しくありません。</span><span class="sxs-lookup"><span data-stu-id="d28cd-105">Problems can arise for any number of other reasons; for example, a server might go down or a message might be badly formatted.</span></span>  
  
 <span data-ttu-id="d28cd-106">これは、方法は、正確かつ最小限の労力で、問題を解決できるように、発生したエラーを報告して、状態の追跡を維持する時間の長い実行または複雑なオーケストレーションの特に重要です。</span><span class="sxs-lookup"><span data-stu-id="d28cd-106">It is especially important for a long-running or complex orchestration to keep track of its state and to report errors as they occur, so that you can resolve problems accurately and with a minimum of effort.</span></span> <span data-ttu-id="d28cd-107">考えたものとしてバックアップ、トランザクションの一部が行われる別されない場合は、トランザクション全体をロールバックできるように、密接に関連する操作の一連の整合性を維持するためのオーケストレーションにも同様に重要です。</span><span class="sxs-lookup"><span data-stu-id="d28cd-107">It is equally important for an orchestration to maintain the integrity of a set of closely related actions, so that if part of a transaction takes place but another does not, the entire transaction can be rolled back as though it never occurred.</span></span>  
  
 <span data-ttu-id="d28cd-108">BizTalk オーケストレーションでは、作業の原子性を保証することができます、つまり、関連するアクションの整合性も外部システムに参加しているトランザクションです。</span><span class="sxs-lookup"><span data-stu-id="d28cd-108">BizTalk Orchestration enables you to guarantee the atomicity of work, that is, the integrity of related actions, even when external systems are participating in transactions.</span></span> <span data-ttu-id="d28cd-109">トランザクション、補正、および例外処理を通じて発生する問題を解決して、オーケストレーションの状態を維持するために、エラーを処理する手段を提供します。</span><span class="sxs-lookup"><span data-stu-id="d28cd-109">It gives you tools to handle errors, to maintain the state of an orchestration, and to fix problems as they occur through transactions, compensation, and exception handling.</span></span>  
  
 <span data-ttu-id="d28cd-110">オーケストレーション デザイナーには、トランザクションと例外処理のフレームワークとして、**スコープ**図形。</span><span class="sxs-lookup"><span data-stu-id="d28cd-110">As a framework for transactions and exception handling, Orchestration Designer provides the **Scope** shape.</span></span> <span data-ttu-id="d28cd-111">スコープには、トランザクションの種類、補正、および任意の数の例外ハンドラーを設定できます。</span><span class="sxs-lookup"><span data-stu-id="d28cd-111">A scope can have a transaction type, a compensation, and any number of exception handlers.</span></span>  
  
 <span data-ttu-id="d28cd-112">トランザクションと例外処理を設定するための手順は次のとおりです。</span><span class="sxs-lookup"><span data-stu-id="d28cd-112">The steps for setting up a transaction and exception handling are:</span></span>  
  
-   <span data-ttu-id="d28cd-113">スコープを作成します。</span><span class="sxs-lookup"><span data-stu-id="d28cd-113">Create a scope.</span></span>  
  
-   <span data-ttu-id="d28cd-114">必要なトランザクションの種類を識別します。</span><span class="sxs-lookup"><span data-stu-id="d28cd-114">Identify the kind of transaction you need.</span></span>  
  
-   <span data-ttu-id="d28cd-115">補正する必要がありますを決定します。</span><span class="sxs-lookup"><span data-stu-id="d28cd-115">Determine what will need to be compensated.</span></span>  
  
-   <span data-ttu-id="d28cd-116">潜在的なエラーを特定します。</span><span class="sxs-lookup"><span data-stu-id="d28cd-116">Identify potential errors.</span></span>  
  
-   <span data-ttu-id="d28cd-117">適切な例外ハンドラーと補正コードを追加します。</span><span class="sxs-lookup"><span data-stu-id="d28cd-117">Add appropriate exception handlers and compensation code.</span></span>  
  
## <a name="examples-of-using-transactions-exception-handlings-and-compensations"></a><span data-ttu-id="d28cd-118">トランザクション、例外処理および補正の使用例</span><span class="sxs-lookup"><span data-stu-id="d28cd-118">Examples of Using Transactions, Exception Handlings, and Compensations</span></span>  
  
-   [<span data-ttu-id="d28cd-119">エラー処理 (BizTalk Server サンプル フォルダー)</span><span class="sxs-lookup"><span data-stu-id="d28cd-119">Error Handling (BizTalk Server Samples Folder)</span></span>](../core/error-handling-biztalk-server-samples-folder.md)  
  
-   [<span data-ttu-id="d28cd-120">補正 (BizTalk Server サンプル)</span><span class="sxs-lookup"><span data-stu-id="d28cd-120">Compensation (BizTalk Server Sample)</span></span>](../core/compensation-biztalk-server-sample.md)  
  
-   <span data-ttu-id="d28cd-121">SDK サンプル「オーケストレーション アトミック トランザクションと COM + サービス コンポーネントで」からダウンロード[ http://go.microsoft.com/fwlink/?LinkId=73703](http://go.microsoft.com/fwlink/?LinkId=73703)します。</span><span class="sxs-lookup"><span data-stu-id="d28cd-121">Download the SDK sample "Atomic Transactions with COM+ Serviced Components in Orchestrations" from [http://go.microsoft.com/fwlink/?LinkId=73703](http://go.microsoft.com/fwlink/?LinkId=73703).</span></span>  
  
-   <span data-ttu-id="d28cd-122">「を使用して、SQL アダプターとアトミック トランザクション オーケストレーションでの」SDK サンプルからダウンロード[ http://go.microsoft.com/fwlink/?LinkId=73703](http://go.microsoft.com/fwlink/?LinkId=73703)します。</span><span class="sxs-lookup"><span data-stu-id="d28cd-122">Download the SDK sample "Using the SQL Adapter with Atomic Transactions in Orchestrations" from [http://go.microsoft.com/fwlink/?LinkId=73703](http://go.microsoft.com/fwlink/?LinkId=73703).</span></span>  
  
-   <span data-ttu-id="d28cd-123">SDK サンプル「オーケストレーションでの実行時間の長いトランザクションの使用」をからダウンロード[ http://go.microsoft.com/fwlink/?LinkId=73703](http://go.microsoft.com/fwlink/?LinkId=73703)します。</span><span class="sxs-lookup"><span data-stu-id="d28cd-123">Download the SDK sample "Using Long-Running Transactions in Orchestrations" from [http://go.microsoft.com/fwlink/?LinkId=73703](http://go.microsoft.com/fwlink/?LinkId=73703).</span></span>  
  
-   <span data-ttu-id="d28cd-124">SDK サンプル「オーケストレーションで例外を処理」をからダウンロード[ http://go.microsoft.com/fwlink/?LinkId=73703](http://go.microsoft.com/fwlink/?LinkId=73703)します。</span><span class="sxs-lookup"><span data-stu-id="d28cd-124">Download the SDK sample "Exception Handling in Orchestrations" from [http://go.microsoft.com/fwlink/?LinkId=73703](http://go.microsoft.com/fwlink/?LinkId=73703).</span></span>  
  
## <a name="in-this-section"></a><span data-ttu-id="d28cd-125">このセクションの内容</span><span class="sxs-lookup"><span data-stu-id="d28cd-125">In This Section</span></span>  
  
-   [<span data-ttu-id="d28cd-126">スコープ</span><span class="sxs-lookup"><span data-stu-id="d28cd-126">Scopes</span></span>](../core/scopes.md)  
  
-   [<span data-ttu-id="d28cd-127">スコープ図形を構成する方法</span><span class="sxs-lookup"><span data-stu-id="d28cd-127">How to Configure the Scope Shape</span></span>](../core/how-to-configure-the-scope-shape.md)  
  
-   [<span data-ttu-id="d28cd-128">オーケストレーションのトランザクション化</span><span class="sxs-lookup"><span data-stu-id="d28cd-128">Making Orchestrations Transactional</span></span>](../core/making-orchestrations-transactional.md)  
  
-   [<span data-ttu-id="d28cd-129">例外</span><span class="sxs-lookup"><span data-stu-id="d28cd-129">Exceptions</span></span>](../core/exceptions.md)  
  
-   [<span data-ttu-id="d28cd-130">補正</span><span class="sxs-lookup"><span data-stu-id="d28cd-130">Compensation</span></span>](../core/compensation.md)  
  
## <a name="see-also"></a><span data-ttu-id="d28cd-131">参照</span><span class="sxs-lookup"><span data-stu-id="d28cd-131">See Also</span></span>  
 [<span data-ttu-id="d28cd-132">BizTalk メッセージング エンジンを使用します。</span><span class="sxs-lookup"><span data-stu-id="d28cd-132">Using the BizTalk Messaging Engine</span></span>](../core/using-the-biztalk-messaging-engine.md)