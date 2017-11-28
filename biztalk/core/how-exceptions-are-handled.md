---
title: "例外を処理する方法 |Microsoft ドキュメント"
ms.custom: 
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: 
ms.suite: 
ms.tgt_pltfrm: 
ms.topic: article
helpviewer_keywords:
- errors, handlers
- scopes, errors
- errors, scopes
- handlers [adapters], errors
ms.assetid: 30b88d8a-8737-4700-b856-1b49fdf6b6d0
caps.latest.revision: "5"
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: 004e4f29bcfc292edb33bae816a52b588a89771c
ms.sourcegitcommit: cb908c540d8f1a692d01dc8f313e16cb4b4e696d
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 09/20/2017
---
# <a name="how-exceptions-are-handled"></a><span data-ttu-id="7cec7-102">例外の処理方法</span><span class="sxs-lookup"><span data-stu-id="7cec7-102">How Exceptions Are Handled</span></span>
<span data-ttu-id="7cec7-103">スコープ内で例外が発生すると、スコープ内の実行の各論理スレッドは停止します。</span><span class="sxs-lookup"><span data-stu-id="7cec7-103">When an exception occurs within a scope, each logical thread of execution in the scope is stopped.</span></span> <span data-ttu-id="7cec7-104">ランタイム エンジンでは、該当する例外の例外ハンドラーが検索されます。</span><span class="sxs-lookup"><span data-stu-id="7cec7-104">The runtime engine tries to find an exception handler for the appropriate exception.</span></span>  
  
 <span data-ttu-id="7cec7-105">特定の例外や、基本的な例外のいずれかに一致する例外ハンドラーが見つかった場合は、制御がその例外ハンドラーに渡されて、コードが実行されます。</span><span class="sxs-lookup"><span data-stu-id="7cec7-105">If the exception handler is found that matches the specific type or one of its base types, control passes to that handler and its code runs.</span></span>  
  
> [!NOTE]
>  <span data-ttu-id="7cec7-106">例外の種類はから派生する必要があります**System.Exception**です。</span><span class="sxs-lookup"><span data-stu-id="7cec7-106">The exception type must be derived from **System.Exception**.</span></span>  
  
 <span data-ttu-id="7cec7-107">例外ハンドラーはシーケンシャルであり、特定の例外を処理できるかどうかを確認するためにチェックされます。</span><span class="sxs-lookup"><span data-stu-id="7cec7-107">Exception handlers are sequential; that is, they will be checked in order to see if they can handle a particular exception.</span></span> <span data-ttu-id="7cec7-108">正しく機能させるためには、最初により特定の種類の例外を処理し、続いて一般的な種類の例外の処理となっていくように配置する必要があります。</span><span class="sxs-lookup"><span data-stu-id="7cec7-108">To work properly, exception handlers must be placed so that those handling more specific types come first, followed by those handling more general types.</span></span> <span data-ttu-id="7cec7-109">これは、特定の種類の例外が、基本的な例外を処理するためのハンドラーではなく、適切なハンドラーによって確実に処理されるようにするためです。</span><span class="sxs-lookup"><span data-stu-id="7cec7-109">This is so that you can ensure that an exception of a specific type is handled by the appropriate handler, rather than one designed to handle a base type.</span></span>  
  
 <span data-ttu-id="7cec7-110">例外ハンドラーが正常に終了すると、制御が前後のスコープに渡されます。</span><span class="sxs-lookup"><span data-stu-id="7cec7-110">If the exception handler completes normally, control passes to the surrounding scope.</span></span> <span data-ttu-id="7cec7-111">前後のスコープで例外がスローされていない場合、オーケストレーションはそのまま実行されます。</span><span class="sxs-lookup"><span data-stu-id="7cec7-111">If no exception has been thrown in the surrounding scope, the orchestration continues to run.</span></span> <span data-ttu-id="7cec7-112">例外ハンドラーが throw ステートメントで終了すると、スローされる別の例外を指定していない限り、対象となる前後のスコープに対して元の例外が再びスローされます。</span><span class="sxs-lookup"><span data-stu-id="7cec7-112">If the exception handler ends with a throw statement, the original exception is thrown again for the surrounding scope to act upon, unless you specify a different exception that you want to be thrown.</span></span>  
  
 <span data-ttu-id="7cec7-113">例外ハンドラーが見つからない場合は、既定の例外ハンドラーが実行されます。</span><span class="sxs-lookup"><span data-stu-id="7cec7-113">If no exception handler can be located, the default exception handler will run.</span></span> <span data-ttu-id="7cec7-114">スコープの既定の例外ハンドラーは、ネストされたトランザクションの補正を呼び出してから、例外を再度スローします。</span><span class="sxs-lookup"><span data-stu-id="7cec7-114">The default exception handler for a scope will call the compensations for any nested transactions, and then throw the exception again.</span></span> <span data-ttu-id="7cec7-115">独自の例外ハンドラーを記述する場合は、例外を反映しないように選択することができます。</span><span class="sxs-lookup"><span data-stu-id="7cec7-115">If you write your own exception handler, you can choose not to propagate the exception.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="7cec7-116">参照</span><span class="sxs-lookup"><span data-stu-id="7cec7-116">See Also</span></span>  
 [<span data-ttu-id="7cec7-117">例外</span><span class="sxs-lookup"><span data-stu-id="7cec7-117">Exceptions</span></span>](../core/exceptions.md)