---
title: ExceptionHandler オーケストレーション |Microsoft Docs
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
ms.openlocfilehash: c3fd1a3fccf72b73271528d93bb03060aa259a39
ms.sourcegitcommit: 381e83d43796a345488d54b3f7413e11d56ad7be
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 05/07/2019
ms.locfileid: "65298740"
---
# <a name="the-exceptionhandler-orchestration"></a><span data-ttu-id="5853c-102">ExceptionHandler オーケストレーション</span><span class="sxs-lookup"><span data-stu-id="5853c-102">The ExceptionHandler Orchestration</span></span>
<span data-ttu-id="5853c-103">ビジネス プロセス管理ソリューションは 2 種類の例外を使用して: システム例外とアプリケーションの例外。</span><span class="sxs-lookup"><span data-stu-id="5853c-103">The Business Process Management solution uses two kinds of exceptions: system exceptions and application exceptions.</span></span> <span data-ttu-id="5853c-104">システム例外は、リソースのエラーなどを含める-ネットワーク接続の失敗などです。</span><span class="sxs-lookup"><span data-stu-id="5853c-104">System exceptions include things like resource errors—a network connection failing, for example.</span></span> <span data-ttu-id="5853c-105">このような問題は自動的に解決一定の間隔、ソリューションは、システム例外が発生するすべての操作を再試行するための可能性はあります。</span><span class="sxs-lookup"><span data-stu-id="5853c-105">There is a chance that such a problem may resolve itself after an interval so that the solution retries all operations that produce system exceptions.</span></span> <span data-ttu-id="5853c-106">アプリケーションの例外は、モ ノの論理エラーや矛盾の何らかの形式などは、解決する可能性が低くによって生成されます。</span><span class="sxs-lookup"><span data-stu-id="5853c-106">Application exceptions are produced by things less likely to resolve themselves, such as logical errors or some form of inconsistency.</span></span> <span data-ttu-id="5853c-107">ソリューションを使用して、 **ExceptionHandlerOrch**システムとアプリケーションの両方のエラーを処理するオーケストレーションです。</span><span class="sxs-lookup"><span data-stu-id="5853c-107">The solution uses the **ExceptionHandlerOrch** orchestration to process both system and application errors.</span></span>  
  
 <span data-ttu-id="5853c-108">注文処理ステージ (**CableOrder1**、 **CableOrder2**) とそれらのサテライト オーケストレーション (**Activate**、**分析**、 **キャンセル**、**変更**、**完了**、**検証**) すべての使用**ExceptionHandlerOrch**します。</span><span class="sxs-lookup"><span data-stu-id="5853c-108">The order processing stages (**CableOrder1**, **CableOrder2**) and their satellite orchestrations (**Activate**, **Analyze**, **Cancel**, **Change**, **Complete**, **Validate**) all use **ExceptionHandlerOrch**.</span></span>  
  
> [!NOTE]
>  <span data-ttu-id="5853c-109">このセクションを参照することも、 **ExceptionHandlerOrch**オーケストレーションは、Microsoft で開く[!INCLUDE[btsVStudioNoVersion](../includes/btsvstudionoversion-md.md)]します。</span><span class="sxs-lookup"><span data-stu-id="5853c-109">You may want to read this section with the **ExceptionHandlerOrch** orchestration open in Microsoft [!INCLUDE[btsVStudioNoVersion](../includes/btsvstudionoversion-md.md)].</span></span>  
  
## <a name="application-errors"></a><span data-ttu-id="5853c-110">アプリケーション エラー</span><span class="sxs-lookup"><span data-stu-id="5853c-110">Application Errors</span></span>  
 <span data-ttu-id="5853c-111">例外ハンドラーは、呼び出すことによって、エラーを記録する最初の**PostError**のメソッド、 **ErrorHandler**オブジェクト、**ユーティリティ**アセンブリ。</span><span class="sxs-lookup"><span data-stu-id="5853c-111">The exception handler first logs the error by calling the **PostError** method of the **ErrorHandler** object in the **Utilities** assembly.</span></span> <span data-ttu-id="5853c-112">例外ハンドラーは、システム エラーまたはアプリケーション エラー、エラーがあったかどうかをテストします。</span><span class="sxs-lookup"><span data-stu-id="5853c-112">The exception handler then tests whether the error was a system error or an application error.</span></span> <span data-ttu-id="5853c-113">次のスクリーン ショットは、アプリケーション例外を処理するオーケストレーションの分岐を示しています。</span><span class="sxs-lookup"><span data-stu-id="5853c-113">The following screenshot shows the orchestration branch that processes application exceptions:</span></span>  
  
 <span data-ttu-id="5853c-114">![ExceptionHandler オーケストレーションのアプリケーション分岐](../core/media/applicationerrorbranchofexceptionhandler.gif "ApplicationErrorBranchofExceptionHandler")</span><span class="sxs-lookup"><span data-stu-id="5853c-114">![Application Branch of ExceptionHandler Orchestrati](../core/media/applicationerrorbranchofexceptionhandler.gif "ApplicationErrorBranchofExceptionHandler")</span></span>  
  
 <span data-ttu-id="5853c-115">アプリケーション エラーの場合は、オーケストレーションは、エラーと呼び出しを記述する文字列を構築、 **ErrorHandlerOrch**オーケストレーションします。</span><span class="sxs-lookup"><span data-stu-id="5853c-115">For an application error, the orchestration constructs a string describing the error and calls the **ErrorHandlerOrch** orchestration.</span></span> <span data-ttu-id="5853c-116">このオーケストレーションは、オペレーターを決定して、操作を終了またはエラーを修正するかどうかの操作に、エラーを送信します。</span><span class="sxs-lookup"><span data-stu-id="5853c-116">This orchestration sends the error to operations where an operator decides whether to fix the error or terminate the operation.</span></span> <span data-ttu-id="5853c-117">演算子は、エラーを修正する場合、は、ErrorHandlerOrch オーケストレーションからのメッセージがバックアップし、操作を再試行します。</span><span class="sxs-lookup"><span data-stu-id="5853c-117">If the operator fixes the error, the repaired message comes back from the ErrorHandlerOrch orchestration and the operation is retried.</span></span> <span data-ttu-id="5853c-118">例外ハンドラーは呼び出すことによって、 **Invoke**のメソッド、 **Recaller**オブジェクト、**ユーティリティ**アセンブリ。</span><span class="sxs-lookup"><span data-stu-id="5853c-118">The exception handler does this by calling the **Invoke** method of the **Recaller** object in the **Utilities** assembly.</span></span> <span data-ttu-id="5853c-119">**Recaller**オブジェクトでは、リフレクションを使用して、エラーが発生したコードを呼び出します。</span><span class="sxs-lookup"><span data-stu-id="5853c-119">The **Recaller** object uses reflection to call the code that caused the error.</span></span>  
  
 <span data-ttu-id="5853c-120">場合に呼び出し**Invoke**成功すると、例外ハンドラは終了します。</span><span class="sxs-lookup"><span data-stu-id="5853c-120">If the call to **Invoke** succeeds, the exception handler exits.</span></span> <span data-ttu-id="5853c-121">それ以外の場合、バックアップ ループしへの呼び出しを試みる**Invoke**もう一度です。</span><span class="sxs-lookup"><span data-stu-id="5853c-121">Otherwise, it loops back and attempts the call to **Invoke** again.</span></span> <span data-ttu-id="5853c-122">詳細については、 **Recaller**オブジェクトを参照してください[「Recaller オブジェクト](../core/the-recaller-object.md)します。</span><span class="sxs-lookup"><span data-stu-id="5853c-122">For more information about the **Recaller** object, see [The Recaller Object](../core/the-recaller-object.md).</span></span>  
  
## <a name="system-errors"></a><span data-ttu-id="5853c-123">システム エラー</span><span class="sxs-lookup"><span data-stu-id="5853c-123">System Errors</span></span>  
 <span data-ttu-id="5853c-124">次の図は、システム エラー分岐、 **ExceptionHandler**オーケストレーション。</span><span class="sxs-lookup"><span data-stu-id="5853c-124">The following diagram shows the system error branch of the **ExceptionHandler** orchestration:</span></span>  
  
 <span data-ttu-id="5853c-125">![ExceptionHandler オーケストレーションのシステム エラー](../core/media/systemerrorbranchofexceptionhandler.gif "SystemErrorBranchofExceptionHandler")</span><span class="sxs-lookup"><span data-stu-id="5853c-125">![System Error of ExceptionHandler Orchestration](../core/media/systemerrorbranchofexceptionhandler.gif "SystemErrorBranchofExceptionHandler")</span></span>  
  
 <span data-ttu-id="5853c-126">例外ハンドラーの最初の呼び出し、システム エラーが発生して、 **CheckInterrupt**オーケストレーションを呼び出して 1 分間待機します。</span><span class="sxs-lookup"><span data-stu-id="5853c-126">For a system error, the exception handler first calls the **CheckInterrupt** orchestration and then waits for one minute.</span></span> <span data-ttu-id="5853c-127">待機は、ネットワーク接続の問題など、一時的、短期的なエラーを再試行する前にオフにできます。</span><span class="sxs-lookup"><span data-stu-id="5853c-127">The wait allows for temporary, short-term errors such as network connection problems, to clear before trying again.</span></span> <span data-ttu-id="5853c-128">リモート呼び出しを行うときに、ネットワークの問題の可能性は常にあります。</span><span class="sxs-lookup"><span data-stu-id="5853c-128">When making remote calls there is always the chance of a network problem.</span></span>  
  
> [!NOTE]
>  <span data-ttu-id="5853c-129">割り込み可能なデザインでは、一般的な規則としてする中または割り込みが発生したかどうかに表示するには、すべて待機期間後すぐに、割り込みをテストします。</span><span class="sxs-lookup"><span data-stu-id="5853c-129">In an interruptible design, as a general rule, you want to test for an interrupt during or immediately after any waiting period to see if an interrupt has occurred.</span></span>  
  
 <span data-ttu-id="5853c-130">ハンドラーを使用して、待機した後、 **Invoke**のメソッド、 **Recaller**オブジェクトを元のコードを実行します。</span><span class="sxs-lookup"><span data-stu-id="5853c-130">After the wait, the handler uses the **Invoke** method of the **Recaller** object to run the original code.</span></span> <span data-ttu-id="5853c-131">呼び出しが成功した場合、ハンドラーを終了します。</span><span class="sxs-lookup"><span data-stu-id="5853c-131">If the call succeeds, the handler exits.</span></span> <span data-ttu-id="5853c-132">それ以外の場合、ハンドラーが、元のコードを実行するさらに 2 回試行されます。</span><span class="sxs-lookup"><span data-stu-id="5853c-132">Otherwise, the handler will try two more times to run the original code.</span></span> <span data-ttu-id="5853c-133">エラー文字列と呼び出しの 3 つすべての試行が失敗する場合、ハンドラーを構築します、 **ErrorHandlerOrch**オーケストレーションします。</span><span class="sxs-lookup"><span data-stu-id="5853c-133">If all three attempts fail, the handler constructs an error string and calls the **ErrorHandlerOrch** orchestration.</span></span>  
  
 <span data-ttu-id="5853c-134">システム例外の処理、例外発生すると、その例外ブロックがキャッチされます。</span><span class="sxs-lookup"><span data-stu-id="5853c-134">If processing a system exception causes an exception, the exception block catches it:</span></span>  
  
 <span data-ttu-id="5853c-135">![システム エラー分岐の例外ハンドラー](../core/media/exceptionhandlerofsystemerrorbranch.gif "ExceptionHandlerofSystemErrorBranch")</span><span class="sxs-lookup"><span data-stu-id="5853c-135">![Exception Handler for System Error Branch](../core/media/exceptionhandlerofsystemerrorbranch.gif "ExceptionHandlerofSystemErrorBranch")</span></span>  
  
 <span data-ttu-id="5853c-136">例外ハンドラーは、システム例外、またはアプリケーションの例外を示すフラグを設定する場合に、カウント ダウンし、例外の種類の再試行回数をテストします。</span><span class="sxs-lookup"><span data-stu-id="5853c-136">The exception handler tests the type of the exception and either decrements the retry counter if it's a system exception, or sets a flag to indicate an application exception.</span></span>  
  
## <a name="the-errorhandlerorch-orchestration"></a><span data-ttu-id="5853c-137">ErrorHandlerOrch オーケストレーション</span><span class="sxs-lookup"><span data-stu-id="5853c-137">The ErrorHandlerOrch Orchestration</span></span>  
 <span data-ttu-id="5853c-138">次の図の最初の部分を示しています、 **ErrorHandlerOrch**オーケストレーション。</span><span class="sxs-lookup"><span data-stu-id="5853c-138">The following diagram shows the first part of the **ErrorHandlerOrch** orchestration:</span></span>  
  
 <span data-ttu-id="5853c-139">![エラー ハンドラー オーケストレーション、最初の部分](../core/media/errorhandlerfirstpart.gif "ErrorHandlerFirstPart")</span><span class="sxs-lookup"><span data-stu-id="5853c-139">![Error Handler Orchestration, First Part](../core/media/errorhandlerfirstpart.gif "ErrorHandlerFirstPart")</span></span>  
  
 <span data-ttu-id="5853c-140">**ErrorHandlerOrch**オーケストレーションの最初のテスト、 **IsBadOrder** 、エラーが不適切な順序であるかどうかをパラメーター (**IsBadOrder**が true) またはその他のエラー。</span><span class="sxs-lookup"><span data-stu-id="5853c-140">The **ErrorHandlerOrch** orchestration first tests the **IsBadOrder** parameter to see if the error is a bad order (**IsBadOrder** is true) or some other error.</span></span> <span data-ttu-id="5853c-141">エラーが不適切な順序である場合は、元の順序の戻りアドレスからのメッセージの送信先を割り当てます、メッセージをカスタマ サービス システムに送信します。</span><span class="sxs-lookup"><span data-stu-id="5853c-141">If the error is a bad order, it assigns the destination of the message from the original order return address and sends the message back to the customer service system.</span></span> <span data-ttu-id="5853c-142">エラーが不適切な順序でない場合は、オーケストレーションが注文エラー メッセージを作成し、操作システムに送信します。</span><span class="sxs-lookup"><span data-stu-id="5853c-142">If the error is not a bad order, the orchestration creates an order error message and sends it to the operations system.</span></span>  
  
 <span data-ttu-id="5853c-143">いずれかのエラー後に、オーケストレーションは応答メッセージまたは割り込みメッセージがリッスンします。</span><span class="sxs-lookup"><span data-stu-id="5853c-143">After either error, the orchestration then listens for a response message or an interrupt message:</span></span>  
  
 <span data-ttu-id="5853c-144">![エラー ハンドラーの 2 番目の部分](../core/media/errorhandlersecondpart.gif "ErrorHandlerSecondPart")</span><span class="sxs-lookup"><span data-stu-id="5853c-144">![Error Handler Second Part](../core/media/errorhandlersecondpart.gif "ErrorHandlerSecondPart")</span></span>  
  
 <span data-ttu-id="5853c-145">オーケストレーションでは、応答を受信する場合は、呼び出し元に返します。</span><span class="sxs-lookup"><span data-stu-id="5853c-145">If the orchestration receives a response, it returns to the caller.</span></span> <span data-ttu-id="5853c-146">オーケストレーションでは、割り込みメッセージを受信する場合を割り込みポートにメッセージを渡し、カスタムをスローします**InterruptException**します。</span><span class="sxs-lookup"><span data-stu-id="5853c-146">If the orchestration receives an interrupt message, it passes the message on to an interrupt port and throws a custom **InterruptException**.</span></span>  
  
 <span data-ttu-id="5853c-147">ソリューションでを使用する方法と、割り込みを処理する方法の詳細については、次を参照してください。 [、ビジネス プロセス管理ソリューションでの処理を中断](../core/interrupt-handling-in-the-business-process-management-solution.md)します。</span><span class="sxs-lookup"><span data-stu-id="5853c-147">For more information about how the solution uses and handles interrupts, see [Interrupt Handling in the Business Process Management Solution](../core/interrupt-handling-in-the-business-process-management-solution.md).</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="5853c-148">参照</span><span class="sxs-lookup"><span data-stu-id="5853c-148">See Also</span></span>  
 <span data-ttu-id="5853c-149">[ビジネス プロセス管理ソリューションでの例外処理](../core/exception-handling-in-the-business-process-management-solution.md) </span><span class="sxs-lookup"><span data-stu-id="5853c-149">[Exception Handling in the Business Process Management Solution](../core/exception-handling-in-the-business-process-management-solution.md) </span></span>  
 <span data-ttu-id="5853c-150">[カスタム例外](../core/custom-exceptions.md) </span><span class="sxs-lookup"><span data-stu-id="5853c-150">[Custom Exceptions](../core/custom-exceptions.md) </span></span>  
 <span data-ttu-id="5853c-151">[ビジネス プロセス管理ソリューションでの処理を中断します。](../core/interrupt-handling-in-the-business-process-management-solution.md) </span><span class="sxs-lookup"><span data-stu-id="5853c-151">[Interrupt Handling in the Business Process Management Solution](../core/interrupt-handling-in-the-business-process-management-solution.md) </span></span>  
 [<span data-ttu-id="5853c-152">Recaller オブジェクト</span><span class="sxs-lookup"><span data-stu-id="5853c-152">The Recaller Object</span></span>](../core/the-recaller-object.md)