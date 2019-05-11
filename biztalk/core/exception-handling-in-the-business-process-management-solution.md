---
title: ビジネス プロセス管理ソリューションでの例外処理 |Microsoft Docs
ms.custom: ''
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: ''
ms.suite: ''
ms.tgt_pltfrm: ''
ms.topic: article
helpviewer_keywords:
- errors, tutorials
- process management solution tutorial, errors
ms.assetid: ac9fcb33-7dac-448e-88b8-04d4d439ea6a
caps.latest.revision: 12
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: 0d06209f49a4702397ea13407593d9286e1f31be
ms.sourcegitcommit: 381e83d43796a345488d54b3f7413e11d56ad7be
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 05/07/2019
ms.locfileid: "65388311"
---
# <a name="exception-handling-in-the-business-process-management-solution"></a><span data-ttu-id="5b7c3-102">ビジネス プロセス管理ソリューションでの例外処理</span><span class="sxs-lookup"><span data-stu-id="5b7c3-102">Exception Handling in the Business Process Management Solution</span></span>
<span data-ttu-id="5b7c3-103">ビジネス プロセス管理ソリューションが特殊な例外処理のオーケストレーション、アダプタ、パイプライン、マッピングを標準の BizTalk Server 例外処理とを使用し、新しいエラー報告機能のルーティングのエラーにします。</span><span class="sxs-lookup"><span data-stu-id="5b7c3-103">The business process management solution uses a special exception handling orchestration, as well as the standard BizTalk Server exception handling, and for adapter, pipeline, mapping, and routing failures, the new error reporting feature.</span></span> <span data-ttu-id="5b7c3-104">このカスタマイズされたシステムを構築、 **ExceptionHandler**オーケストレーションします。</span><span class="sxs-lookup"><span data-stu-id="5b7c3-104">This customized system is built around the **ExceptionHandler** orchestration.</span></span> <span data-ttu-id="5b7c3-105">ソリューションを使用して、 **ExceptionHandler**オーケストレーション、操作を再試行するか、一時的な問題と成功する可能性の呼び出しを再試行してください。</span><span class="sxs-lookup"><span data-stu-id="5b7c3-105">The solution uses the **ExceptionHandler** orchestration to retry an operation or to retry a call that might succeed after a transient problem.</span></span>  
  
> [!NOTE]
>  <span data-ttu-id="5b7c3-106">など、オーケストレーションのコードを再利用できます**Activate**、使用する、 **ExceptionHandler**オーケストレーションします。</span><span class="sxs-lookup"><span data-stu-id="5b7c3-106">You can re-use code from orchestrations, such as **Activate**, that use the **ExceptionHandler** orchestration.</span></span> <span data-ttu-id="5b7c3-107">という名前のスコープは、これらのオーケストレーションのすべて**CallingCode**添付で**例外**ブロックします。</span><span class="sxs-lookup"><span data-stu-id="5b7c3-107">All of these orchestrations include a scope titled **CallingCode** with an attached **Exception** block.</span></span> <span data-ttu-id="5b7c3-108">コードに置き換えます、 **CallingCode**コードを持つスコープ。</span><span class="sxs-lookup"><span data-stu-id="5b7c3-108">Replace the code in the **CallingCode** scope with your code.</span></span> <span data-ttu-id="5b7c3-109">**例外**ブロックを呼び出す必要変数の定義、 **ExceptionHandler**オーケストレーションします。</span><span class="sxs-lookup"><span data-stu-id="5b7c3-109">The **Exception** block defines all of the variables need to call the **ExceptionHandler** orchestration.</span></span> <span data-ttu-id="5b7c3-110">変数に割り当てられた値を編集します。</span><span class="sxs-lookup"><span data-stu-id="5b7c3-110">Edit the values assigned to the variables.</span></span>  
  
 <span data-ttu-id="5b7c3-111">ソリューションは、エラーが正しくない形式の注文メッセージなどの回復可能な場合、カスタム例外と定義済みのいくつかの BizTalk 例外を使用します。</span><span class="sxs-lookup"><span data-stu-id="5b7c3-111">The solution uses custom exceptions, and a couple pre-defined BizTalk exceptions, for cases where the error is unrecoverable such as a malformed order message.</span></span>  
  
> [!NOTE]
>  <span data-ttu-id="5b7c3-112">ソリューションでは、いくつかのポート上の障害を処理するため、カスタム アダプターを使用します。</span><span class="sxs-lookup"><span data-stu-id="5b7c3-112">The solution uses a custom adapter for handling failures on some ports.</span></span> <span data-ttu-id="5b7c3-113">アダプターの詳細については、次を参照してください。 [、Ops アダプタ](../core/the-ops-adapter.md)します。</span><span class="sxs-lookup"><span data-stu-id="5b7c3-113">For more information about the adapter, see [The Ops Adapter](../core/the-ops-adapter.md).</span></span>  
  
 <span data-ttu-id="5b7c3-114">このセクションについて説明します、 **ExceptionHandler**オーケストレーションとカスタムの例外。</span><span class="sxs-lookup"><span data-stu-id="5b7c3-114">This section describes the **ExceptionHandler** orchestration and the custom exceptions.</span></span> <span data-ttu-id="5b7c3-115">についても説明、簡単に、どのようにエラー報告機能を使用します。</span><span class="sxs-lookup"><span data-stu-id="5b7c3-115">It also discusses, briefly, how the solution employs the error reporting product feature.</span></span>  
  
## <a name="in-this-section"></a><span data-ttu-id="5b7c3-116">このセクションの内容</span><span class="sxs-lookup"><span data-stu-id="5b7c3-116">In This Section</span></span>  
  
-   [<span data-ttu-id="5b7c3-117">ExceptionHandler オーケストレーション</span><span class="sxs-lookup"><span data-stu-id="5b7c3-117">The ExceptionHandler Orchestration</span></span>](../core/the-exceptionhandler-orchestration.md)  
  
-   [<span data-ttu-id="5b7c3-118">カスタム例外</span><span class="sxs-lookup"><span data-stu-id="5b7c3-118">Custom Exceptions</span></span>](../core/custom-exceptions.md)