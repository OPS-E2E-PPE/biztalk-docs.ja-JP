---
title: ExceptionHandler オーケストレーション |Microsoft ドキュメント
ms.custom: ''
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: ''
ms.suite: ''
ms.tgt_pltfrm: ''
ms.topic: article
helpviewer_keywords:
- errors, systems
- errors, applications
- applications, errors
- orchestrations, errors [process management solutions]
- process management solution tutorial, errors
ms.assetid: ac154e76-9dfe-433a-948b-e098df705fe5
caps.latest.revision: 27
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: a1b79a1c6d9e6fada206ba0298913fe8f369783c
ms.sourcegitcommit: cb908c540d8f1a692d01dc8f313e16cb4b4e696d
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 09/20/2017
ms.locfileid: "22280026"
---
# <a name="the-exceptionhandler-orchestration"></a><span data-ttu-id="d47a7-102">ExceptionHandler オーケストレーション</span><span class="sxs-lookup"><span data-stu-id="d47a7-102">The ExceptionHandler Orchestration</span></span>
<span data-ttu-id="d47a7-103">ビジネス プロセス管理ソリューションで 2 つの種類の例外を使用します。 システム例外とアプリケーションの例外。</span><span class="sxs-lookup"><span data-stu-id="d47a7-103">The Business Process Management solution uses two kinds of exceptions: system exceptions and application exceptions.</span></span> <span data-ttu-id="d47a7-104">システム例外を含めるようなリソース エラー: ネットワーク接続の失敗、例を示します。</span><span class="sxs-lookup"><span data-stu-id="d47a7-104">System exceptions include things like resource errors—a network connection failing, for example.</span></span> <span data-ttu-id="d47a7-105">このような問題は、時間が経つと自然に解決する可能性があるので、ソリューションはシステム例外の原因となったすべての操作を再試行します。</span><span class="sxs-lookup"><span data-stu-id="d47a7-105">There is a chance that such a problem may resolve itself after an interval so that the solution retries all operations that produce system exceptions.</span></span> <span data-ttu-id="d47a7-106">アプリケーション例外は、論理エラーや不整合など、自然に解決する可能性の少ない事象を原因として生じます。</span><span class="sxs-lookup"><span data-stu-id="d47a7-106">Application exceptions are produced by things less likely to resolve themselves, such as logical errors or some form of inconsistency.</span></span> <span data-ttu-id="d47a7-107">ソリューションを使用して、 **ExceptionHandlerOrch**システムとアプリケーションの両方のエラーを処理するオーケストレーションです。</span><span class="sxs-lookup"><span data-stu-id="d47a7-107">The solution uses the **ExceptionHandlerOrch** orchestration to process both system and application errors.</span></span>  
  
 <span data-ttu-id="d47a7-108">注文処理ステージ (**CableOrder1**、 **CableOrder2**) とそれらのサテライト オーケストレーション (**Activate**、**分析**、 **キャンセル**、**変更**、**完了**、**検証**) すべての使用**ExceptionHandlerOrch**です。</span><span class="sxs-lookup"><span data-stu-id="d47a7-108">The order processing stages (**CableOrder1**, **CableOrder2**) and their satellite orchestrations (**Activate**, **Analyze**, **Cancel**, **Change**, **Complete**, **Validate**) all use **ExceptionHandlerOrch**.</span></span>  
  
> [!NOTE]
>  <span data-ttu-id="d47a7-109">このセクションを参照することも、 **ExceptionHandlerOrch**オーケストレーションは、マイクロソフトで開く[!INCLUDE[btsVStudioNoVersion](../includes/btsvstudionoversion-md.md)]です。</span><span class="sxs-lookup"><span data-stu-id="d47a7-109">You may want to read this section with the **ExceptionHandlerOrch** orchestration open in Microsoft [!INCLUDE[btsVStudioNoVersion](../includes/btsvstudionoversion-md.md)].</span></span>  
  
## <a name="application-errors"></a><span data-ttu-id="d47a7-110">アプリケーション エラー</span><span class="sxs-lookup"><span data-stu-id="d47a7-110">Application Errors</span></span>  
 <span data-ttu-id="d47a7-111">例外ハンドラーでは呼び出すことによって、エラーがログ記録最初、 **PostError**のメソッド、 **ErrorHandler**内のオブジェクト、**ユーティリティ**アセンブリ。</span><span class="sxs-lookup"><span data-stu-id="d47a7-111">The exception handler first logs the error by calling the **PostError** method of the **ErrorHandler** object in the **Utilities** assembly.</span></span> <span data-ttu-id="d47a7-112">次に例外ハンドラはそのエラーがシステム エラーかアプリケーション エラーかを調べます。</span><span class="sxs-lookup"><span data-stu-id="d47a7-112">The exception handler then tests whether the error was a system error or an application error.</span></span> <span data-ttu-id="d47a7-113">次のスクリーンショットは、アプリケーション例外を処理するオーケストレーションの分岐です。</span><span class="sxs-lookup"><span data-stu-id="d47a7-113">The following screenshot shows the orchestration branch that processes application exceptions:</span></span>  
  
 <span data-ttu-id="d47a7-114">![ExceptionHandler オーケストレーションのアプリケーション分岐](../core/media/applicationerrorbranchofexceptionhandler.gif "ApplicationErrorBranchofExceptionHandler")</span><span class="sxs-lookup"><span data-stu-id="d47a7-114">![Application Branch of ExceptionHandler Orchestrati](../core/media/applicationerrorbranchofexceptionhandler.gif "ApplicationErrorBranchofExceptionHandler")</span></span>  
  
 <span data-ttu-id="d47a7-115">アプリケーション エラーの場合は、オーケストレーションがエラーと呼び出しを表す文字列を構築、 **ErrorHandlerOrch**オーケストレーションです。</span><span class="sxs-lookup"><span data-stu-id="d47a7-115">For an application error, the orchestration constructs a string describing the error and calls the **ErrorHandlerOrch** orchestration.</span></span> <span data-ttu-id="d47a7-116">このオーケストレーションは、エラーを修正するか操作を終了するかをオペレータが決定できるように、エラーを操作元に送ります。</span><span class="sxs-lookup"><span data-stu-id="d47a7-116">This orchestration sends the error to operations where an operator decides whether to fix the error or terminate the operation.</span></span> <span data-ttu-id="d47a7-117">オペレータがエラーを修正した場合は、ErrorHandlerOrch オーケストレーションからエラー修正のメッセージが返され、操作が再試行されます。</span><span class="sxs-lookup"><span data-stu-id="d47a7-117">If the operator fixes the error, the repaired message comes back from the ErrorHandlerOrch orchestration and the operation is retried.</span></span> <span data-ttu-id="d47a7-118">例外ハンドラーは、呼び出すことによって、 **Invoke**のメソッド、 **Recaller**内のオブジェクト、**ユーティリティ**アセンブリ。</span><span class="sxs-lookup"><span data-stu-id="d47a7-118">The exception handler does this by calling the **Invoke** method of the **Recaller** object in the **Utilities** assembly.</span></span> <span data-ttu-id="d47a7-119">**Recaller**オブジェクトでは、リフレクションを使用して、エラーの原因となったコードを呼び出します。</span><span class="sxs-lookup"><span data-stu-id="d47a7-119">The **Recaller** object uses reflection to call the code that caused the error.</span></span>  
  
 <span data-ttu-id="d47a7-120">場合に呼び出し**Invoke**成功すると、例外ハンドラは終了します。</span><span class="sxs-lookup"><span data-stu-id="d47a7-120">If the call to **Invoke** succeeds, the exception handler exits.</span></span> <span data-ttu-id="d47a7-121">それ以外の場合、ƒvƒoƒbƒn しへの呼び出しを試みる**Invoke**もう一度です。</span><span class="sxs-lookup"><span data-stu-id="d47a7-121">Otherwise, it loops back and attempts the call to **Invoke** again.</span></span> <span data-ttu-id="d47a7-122">詳細については、 **Recaller**オブジェクトを参照してください[Recaller Object](../core/the-recaller-object.md)です。</span><span class="sxs-lookup"><span data-stu-id="d47a7-122">For more information about the **Recaller** object, see [The Recaller Object](../core/the-recaller-object.md).</span></span>  
  
## <a name="system-errors"></a><span data-ttu-id="d47a7-123">システム エラー</span><span class="sxs-lookup"><span data-stu-id="d47a7-123">System Errors</span></span>  
 <span data-ttu-id="d47a7-124">次の図は、システム エラー分岐の**ExceptionHandler**オーケストレーション。</span><span class="sxs-lookup"><span data-stu-id="d47a7-124">The following diagram shows the system error branch of the **ExceptionHandler** orchestration:</span></span>  
  
 <span data-ttu-id="d47a7-125">![ExceptionHandler オーケストレーションのシステム エラー](../core/media/systemerrorbranchofexceptionhandler.gif "SystemErrorBranchofExceptionHandler")</span><span class="sxs-lookup"><span data-stu-id="d47a7-125">![System Error of ExceptionHandler Orchestration](../core/media/systemerrorbranchofexceptionhandler.gif "SystemErrorBranchofExceptionHandler")</span></span>  
  
 <span data-ttu-id="d47a7-126">システム エラーを例外ハンドラー最初の呼び出し、 **CheckInterrupt**オーケストレーションを 1 分間待機します。</span><span class="sxs-lookup"><span data-stu-id="d47a7-126">For a system error, the exception handler first calls the **CheckInterrupt** orchestration and then waits for one minute.</span></span> <span data-ttu-id="d47a7-127">再試行する前に、ネットワーク接続の問題のように一時的な短時間のエラーが解決するのを待つためです。</span><span class="sxs-lookup"><span data-stu-id="d47a7-127">The wait allows for temporary, short-term errors such as network connection problems, to clear before trying again.</span></span> <span data-ttu-id="d47a7-128">リモートの呼び出しでは常にネットワーク障害の可能性があります。</span><span class="sxs-lookup"><span data-stu-id="d47a7-128">When making remote calls there is always the chance of a network problem.</span></span>  
  
> [!NOTE]
>  <span data-ttu-id="d47a7-129">割り込み可能なデザインでは、通常、割り込みがあったかどうかを待機期間中またはその直後に調べます。</span><span class="sxs-lookup"><span data-stu-id="d47a7-129">In an interruptible design, as a general rule, you want to test for an interrupt during or immediately after any waiting period to see if an interrupt has occurred.</span></span>  
  
 <span data-ttu-id="d47a7-130">ハンドラーを使用して、待機した後、 **Invoke**のメソッド、 **Recaller**オブジェクトを元のコードを実行します。</span><span class="sxs-lookup"><span data-stu-id="d47a7-130">After the wait, the handler uses the **Invoke** method of the **Recaller** object to run the original code.</span></span> <span data-ttu-id="d47a7-131">呼び出しに成功すると、例外ハンドラは終了します。</span><span class="sxs-lookup"><span data-stu-id="d47a7-131">If the call succeeds, the handler exits.</span></span> <span data-ttu-id="d47a7-132">失敗すると、元のコードの実行を 2 度試みます。</span><span class="sxs-lookup"><span data-stu-id="d47a7-132">Otherwise, the handler will try two more times to run the original code.</span></span> <span data-ttu-id="d47a7-133">エラー文字列と呼び出し 3 つすべての試行が失敗する場合、ハンドラーを構築、 **ErrorHandlerOrch**オーケストレーションです。</span><span class="sxs-lookup"><span data-stu-id="d47a7-133">If all three attempts fail, the handler constructs an error string and calls the **ErrorHandlerOrch** orchestration.</span></span>  
  
 <span data-ttu-id="d47a7-134">システム例外の処理で発生した例外は、例外ブロックがキャッチします。</span><span class="sxs-lookup"><span data-stu-id="d47a7-134">If processing a system exception causes an exception, the exception block catches it:</span></span>  
  
 <span data-ttu-id="d47a7-135">![システム エラー分岐の例外ハンドラー](../core/media/exceptionhandlerofsystemerrorbranch.gif "ExceptionHandlerofSystemErrorBranch")</span><span class="sxs-lookup"><span data-stu-id="d47a7-135">![Exception Handler for System Error Branch](../core/media/exceptionhandlerofsystemerrorbranch.gif "ExceptionHandlerofSystemErrorBranch")</span></span>  
  
 <span data-ttu-id="d47a7-136">例外ハンドラは例外の種類を調べて、システム例外の場合は再試行カウンタをカウント ダウンします。アプリケーション例外の場合は、そのフラグを設定します。</span><span class="sxs-lookup"><span data-stu-id="d47a7-136">The exception handler tests the type of the exception and either decrements the retry counter if it's a system exception, or sets a flag to indicate an application exception.</span></span>  
  
## <a name="the-errorhandlerorch-orchestration"></a><span data-ttu-id="d47a7-137">ErrorHandlerOrch オーケストレーション</span><span class="sxs-lookup"><span data-stu-id="d47a7-137">The ErrorHandlerOrch Orchestration</span></span>  
 <span data-ttu-id="d47a7-138">次の図の最初の部分を示しています、 **ErrorHandlerOrch**オーケストレーション。</span><span class="sxs-lookup"><span data-stu-id="d47a7-138">The following diagram shows the first part of the **ErrorHandlerOrch** orchestration:</span></span>  
  
 <span data-ttu-id="d47a7-139">![エラー ハンドラー オーケストレーション、最初の部分](../core/media/errorhandlerfirstpart.gif "ErrorHandlerFirstPart")</span><span class="sxs-lookup"><span data-stu-id="d47a7-139">![Error Handler Orchestration, First Part](../core/media/errorhandlerfirstpart.gif "ErrorHandlerFirstPart")</span></span>  
  
 <span data-ttu-id="d47a7-140">**ErrorHandlerOrch**オーケストレーションの最初のテスト、 **IsBadOrder**パラメーターを参照してエラーが不適切な順序 (**IsBadOrder**が true) またはその他のエラーです。</span><span class="sxs-lookup"><span data-stu-id="d47a7-140">The **ErrorHandlerOrch** orchestration first tests the **IsBadOrder** parameter to see if the error is a bad order (**IsBadOrder** is true) or some other error.</span></span> <span data-ttu-id="d47a7-141">注文が無効である場合は、元の注文の返信先アドレスをメッセージの送信先に指定してメッセージをカスタマ サービス システムに返します。</span><span class="sxs-lookup"><span data-stu-id="d47a7-141">If the error is a bad order, it assigns the destination of the message from the original order return address and sends the message back to the customer service system.</span></span> <span data-ttu-id="d47a7-142">注文に問題がない場合は、オーケストレーションが注文エラー メッセージを作成して操作システムに送ります。</span><span class="sxs-lookup"><span data-stu-id="d47a7-142">If the error is not a bad order, the orchestration creates an order error message and sends it to the operations system.</span></span>  
  
 <span data-ttu-id="d47a7-143">どちらのエラーでも、オーケストレーションは次に応答メッセージまたは割り込みメッセージを待機します。</span><span class="sxs-lookup"><span data-stu-id="d47a7-143">After either error, the orchestration then listens for a response message or an interrupt message:</span></span>  
  
 <span data-ttu-id="d47a7-144">![エラー ハンドラーの 2 番目の部分](../core/media/errorhandlersecondpart.gif "ErrorHandlerSecondPart")</span><span class="sxs-lookup"><span data-stu-id="d47a7-144">![Error Handler Second Part](../core/media/errorhandlersecondpart.gif "ErrorHandlerSecondPart")</span></span>  
  
 <span data-ttu-id="d47a7-145">オーケストレーションは応答を受け取ると、呼び出し元に返します。</span><span class="sxs-lookup"><span data-stu-id="d47a7-145">If the orchestration receives a response, it returns to the caller.</span></span> <span data-ttu-id="d47a7-146">オーケストレーションは割り込みメッセージを受け取る場合を割り込みポートにメッセージを渡しますされ、カスタムのスロー **InterruptException**です。</span><span class="sxs-lookup"><span data-stu-id="d47a7-146">If the orchestration receives an interrupt message, it passes the message on to an interrupt port and throws a custom **InterruptException**.</span></span>  
  
 <span data-ttu-id="d47a7-147">ソリューションでを使用する方法と、割り込みを処理する方法の詳細については、次を参照してください。[ビジネス プロセス管理ソリューションでの処理を中断](../core/interrupt-handling-in-the-business-process-management-solution.md)です。</span><span class="sxs-lookup"><span data-stu-id="d47a7-147">For more information about how the solution uses and handles interrupts, see [Interrupt Handling in the Business Process Management Solution](../core/interrupt-handling-in-the-business-process-management-solution.md).</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="d47a7-148">参照</span><span class="sxs-lookup"><span data-stu-id="d47a7-148">See Also</span></span>  
 <span data-ttu-id="d47a7-149">[ビジネス プロセス管理ソリューションでの例外処理](../core/exception-handling-in-the-business-process-management-solution.md) </span><span class="sxs-lookup"><span data-stu-id="d47a7-149">[Exception Handling in the Business Process Management Solution](../core/exception-handling-in-the-business-process-management-solution.md) </span></span>  
 <span data-ttu-id="d47a7-150">[カスタム例外](../core/custom-exceptions.md) </span><span class="sxs-lookup"><span data-stu-id="d47a7-150">[Custom Exceptions](../core/custom-exceptions.md) </span></span>  
 <span data-ttu-id="d47a7-151">[ビジネス プロセス管理ソリューションでの処理を中断します。](../core/interrupt-handling-in-the-business-process-management-solution.md) </span><span class="sxs-lookup"><span data-stu-id="d47a7-151">[Interrupt Handling in the Business Process Management Solution](../core/interrupt-handling-in-the-business-process-management-solution.md) </span></span>  
 [<span data-ttu-id="d47a7-152">Recaller オブジェクト</span><span class="sxs-lookup"><span data-stu-id="d47a7-152">The Recaller Object</span></span>](../core/the-recaller-object.md)