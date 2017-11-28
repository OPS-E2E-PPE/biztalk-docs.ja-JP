---
title: "ビジネス プロセス管理ソリューションでの例外処理 |Microsoft ドキュメント"
ms.custom: 
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: 
ms.suite: 
ms.tgt_pltfrm: 
ms.topic: article
helpviewer_keywords:
- errors, tutorials
- process management solution tutorial, errors
ms.assetid: ac9fcb33-7dac-448e-88b8-04d4d439ea6a
caps.latest.revision: "12"
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: 1cd3134b8ed4e2fc6fd4a50d9b64397692ea32b7
ms.sourcegitcommit: cb908c540d8f1a692d01dc8f313e16cb4b4e696d
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 09/20/2017
---
# <a name="exception-handling-in-the-business-process-management-solution"></a><span data-ttu-id="b781a-102">ビジネス プロセス管理ソリューションでの例外処理</span><span class="sxs-lookup"><span data-stu-id="b781a-102">Exception Handling in the Business Process Management Solution</span></span>
<span data-ttu-id="b781a-103">ビジネス プロセス管理ソリューションでは、標準の BizTalk Server 例外処理に加えて特殊な例外処理オーケストレーションを使用します。アダプタ、パイプライン、マッピング、およびルーティングのエラーには新しいエラー報告機能を使用します。</span><span class="sxs-lookup"><span data-stu-id="b781a-103">The business process management solution uses a special exception handling orchestration, as well as the standard BizTalk Server exception handling, and for adapter, pipeline, mapping, and routing failures, the new error reporting feature.</span></span> <span data-ttu-id="b781a-104">このカスタマイズされたシステムを構築、 **ExceptionHandler**オーケストレーションです。</span><span class="sxs-lookup"><span data-stu-id="b781a-104">This customized system is built around the **ExceptionHandler** orchestration.</span></span> <span data-ttu-id="b781a-105">ソリューションを使用して、 **ExceptionHandler**操作を再試行するか、一時的な問題の発生後に成功する可能性がありますの呼び出しを再試行するオーケストレーションです。</span><span class="sxs-lookup"><span data-stu-id="b781a-105">The solution uses the **ExceptionHandler** orchestration to retry an operation or to retry a call that might succeed after a transient problem.</span></span>  
  
> [!NOTE]
>  <span data-ttu-id="b781a-106">など、オーケストレーションのコードを再使用できる**Activate**、使用する、 **ExceptionHandler**オーケストレーションです。</span><span class="sxs-lookup"><span data-stu-id="b781a-106">You can re-use code from orchestrations, such as **Activate**, that use the **ExceptionHandler** orchestration.</span></span> <span data-ttu-id="b781a-107">という名前のスコープは、すべてこれらのオーケストレーションの**CallingCode**添付と**例外**ブロックします。</span><span class="sxs-lookup"><span data-stu-id="b781a-107">All of these orchestrations include a scope titled **CallingCode** with an attached **Exception** block.</span></span> <span data-ttu-id="b781a-108">コードで置き換え、 **CallingCode**コードにスコープします。</span><span class="sxs-lookup"><span data-stu-id="b781a-108">Replace the code in the **CallingCode** scope with your code.</span></span> <span data-ttu-id="b781a-109">**例外**ブロックには、すべてを呼び出す変数必要性を定義、 **ExceptionHandler**オーケストレーションです。</span><span class="sxs-lookup"><span data-stu-id="b781a-109">The **Exception** block defines all of the variables need to call the **ExceptionHandler** orchestration.</span></span> <span data-ttu-id="b781a-110">変数に指定されている値は編集することができます。</span><span class="sxs-lookup"><span data-stu-id="b781a-110">Edit the values assigned to the variables.</span></span>  
  
 <span data-ttu-id="b781a-111">注文メッセージの形式が正しくない場合など、エラーが回復不可能である場合は、カスタム例外と定義済みの BizTalk 例外が使用されます。</span><span class="sxs-lookup"><span data-stu-id="b781a-111">The solution uses custom exceptions, and a couple pre-defined BizTalk exceptions, for cases where the error is unrecoverable such as a malformed order message.</span></span>  
  
> [!NOTE]
>  <span data-ttu-id="b781a-112">ポートによっては、ポート エラーの処理にカスタム アダプタが使用される場合があります。</span><span class="sxs-lookup"><span data-stu-id="b781a-112">The solution uses a custom adapter for handling failures on some ports.</span></span> <span data-ttu-id="b781a-113">アダプターに関する詳細については、次を参照してください。 [、Ops アダプタ](../core/the-ops-adapter.md)です。</span><span class="sxs-lookup"><span data-stu-id="b781a-113">For more information about the adapter, see [The Ops Adapter](../core/the-ops-adapter.md).</span></span>  
  
 <span data-ttu-id="b781a-114">このセクションの内容について説明します、 **ExceptionHandler**オーケストレーションとカスタム例外です。</span><span class="sxs-lookup"><span data-stu-id="b781a-114">This section describes the **ExceptionHandler** orchestration and the custom exceptions.</span></span> <span data-ttu-id="b781a-115">さらに、エラー報告機能がどのように使用されるかについても簡単に説明します。</span><span class="sxs-lookup"><span data-stu-id="b781a-115">It also discusses, briefly, how the solution employs the error reporting product feature.</span></span>  
  
## <a name="in-this-section"></a><span data-ttu-id="b781a-116">このセクションの内容</span><span class="sxs-lookup"><span data-stu-id="b781a-116">In This Section</span></span>  
  
-   [<span data-ttu-id="b781a-117">ExceptionHandler オーケストレーション</span><span class="sxs-lookup"><span data-stu-id="b781a-117">The ExceptionHandler Orchestration</span></span>](../core/the-exceptionhandler-orchestration.md)  
  
-   [<span data-ttu-id="b781a-118">カスタム例外</span><span class="sxs-lookup"><span data-stu-id="b781a-118">Custom Exceptions</span></span>](../core/custom-exceptions.md)