---
title: 例外を処理する方法 |Microsoft Docs
ms.custom: ''
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: ''
ms.suite: ''
ms.tgt_pltfrm: ''
ms.topic: article
helpviewer_keywords:
- errors, handlers
- scopes, errors
- errors, scopes
- handlers [adapters], errors
ms.assetid: 30b88d8a-8737-4700-b856-1b49fdf6b6d0
caps.latest.revision: 5
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: fc50f8371e5417662a8b81ef119e2a33f18e8925
ms.sourcegitcommit: 381e83d43796a345488d54b3f7413e11d56ad7be
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 05/07/2019
ms.locfileid: "65344137"
---
# <a name="how-exceptions-are-handled"></a><span data-ttu-id="07a60-102">例外の処理方法</span><span class="sxs-lookup"><span data-stu-id="07a60-102">How Exceptions Are Handled</span></span>
<span data-ttu-id="07a60-103">スコープ内で例外が発生する、スコープ内での実行の各論理スレッドが停止します。</span><span class="sxs-lookup"><span data-stu-id="07a60-103">When an exception occurs within a scope, each logical thread of execution in the scope is stopped.</span></span> <span data-ttu-id="07a60-104">ランタイム エンジンは、適切な例外の例外ハンドラーが検索しようとします。</span><span class="sxs-lookup"><span data-stu-id="07a60-104">The runtime engine tries to find an exception handler for the appropriate exception.</span></span>  
  
 <span data-ttu-id="07a60-105">特定の型またはその基本型のいずれかに一致する例外ハンドラーが見つかった場合は、コントロールは実行をそのハンドラーとそのコードに渡します。</span><span class="sxs-lookup"><span data-stu-id="07a60-105">If the exception handler is found that matches the specific type or one of its base types, control passes to that handler and its code runs.</span></span>  
  
> [!NOTE]
>  <span data-ttu-id="07a60-106">例外の種類はから派生する必要があります**System.Exception**します。</span><span class="sxs-lookup"><span data-stu-id="07a60-106">The exception type must be derived from **System.Exception**.</span></span>  
  
 <span data-ttu-id="07a60-107">例外ハンドラーはシーケンシャルです。つまり、特定の例外を処理できるかどうかに表示するにはチェックされます。</span><span class="sxs-lookup"><span data-stu-id="07a60-107">Exception handlers are sequential; that is, they will be checked in order to see if they can handle a particular exception.</span></span> <span data-ttu-id="07a60-108">適切に機能するには、一般的な種類の処理後に特定の種類の処理が最初に、ように、例外ハンドラーを配置する必要があります。</span><span class="sxs-lookup"><span data-stu-id="07a60-108">To work properly, exception handlers must be placed so that those handling more specific types come first, followed by those handling more general types.</span></span> <span data-ttu-id="07a60-109">これは、特定の種類の例外が 1 つの基本データ型を処理するように設計ではなく、適切なハンドラーによって処理されることを確認できるようにします。</span><span class="sxs-lookup"><span data-stu-id="07a60-109">This is so that you can ensure that an exception of a specific type is handled by the appropriate handler, rather than one designed to handle a base type.</span></span>  
  
 <span data-ttu-id="07a60-110">例外ハンドラーが正常に完了した場合は、前後のスコープに制御が渡されます。</span><span class="sxs-lookup"><span data-stu-id="07a60-110">If the exception handler completes normally, control passes to the surrounding scope.</span></span> <span data-ttu-id="07a60-111">前後のスコープで例外がスローされていない場合、オーケストレーションを実行し続けます。</span><span class="sxs-lookup"><span data-stu-id="07a60-111">If no exception has been thrown in the surrounding scope, the orchestration continues to run.</span></span> <span data-ttu-id="07a60-112">例外ハンドラーは、throw ステートメントで終わる、元の例外がスローする別の例外を指定しない限り、対象となる前後のスコープに対してもう一度スローされます。</span><span class="sxs-lookup"><span data-stu-id="07a60-112">If the exception handler ends with a throw statement, the original exception is thrown again for the surrounding scope to act upon, unless you specify a different exception that you want to be thrown.</span></span>  
  
 <span data-ttu-id="07a60-113">例外ハンドラーが見つからない、既定の例外ハンドラーが実行されます。</span><span class="sxs-lookup"><span data-stu-id="07a60-113">If no exception handler can be located, the default exception handler will run.</span></span> <span data-ttu-id="07a60-114">スコープの既定の例外ハンドラーは、入れ子になったトランザクションの補正を呼び出すし、もう一度例外をスローします。</span><span class="sxs-lookup"><span data-stu-id="07a60-114">The default exception handler for a scope will call the compensations for any nested transactions, and then throw the exception again.</span></span> <span data-ttu-id="07a60-115">独自の例外ハンドラーを記述する場合は、例外を反映するには、しないこともできます。</span><span class="sxs-lookup"><span data-stu-id="07a60-115">If you write your own exception handler, you can choose not to propagate the exception.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="07a60-116">参照</span><span class="sxs-lookup"><span data-stu-id="07a60-116">See Also</span></span>  
 [<span data-ttu-id="07a60-117">例外</span><span class="sxs-lookup"><span data-stu-id="07a60-117">Exceptions</span></span>](../core/exceptions.md)