---
title: "Ops アダプタ |Microsoft ドキュメント"
ms.custom: 
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: 
ms.suite: 
ms.tgt_pltfrm: 
ms.topic: article
helpviewer_keywords:
- adapters, Ops adapters
- Ops adapters, about Ops adapters
- Ops adapters
- process management solution tutorial, Ops adapters
- process management solution tutorial, errors
ms.assetid: 7f747a5f-14af-4e4c-bc29-f083f8f00bd0
caps.latest.revision: "13"
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: 67463adf4e1e960ab6608e67595a679804aa223e
ms.sourcegitcommit: cb908c540d8f1a692d01dc8f313e16cb4b4e696d
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 09/20/2017
---
# <a name="the-ops-adapter"></a><span data-ttu-id="c5925-102">Ops アダプタ</span><span class="sxs-lookup"><span data-stu-id="c5925-102">The Ops Adapter</span></span>
<span data-ttu-id="c5925-103">このソリューションは、エラーの修正や注文の中止に関して決定を行うオペレーティング システムに、問題を示すメッセージやエラーが可能な限り渡されるようにデザインされています。</span><span class="sxs-lookup"><span data-stu-id="c5925-103">The design of the solution is to pass, where possible, problematic messages and errors to operations systems that make a decision about fixing the error or terminating the order.</span></span> <span data-ttu-id="c5925-104">Ops アダプタは新しいエラー報告機能を使用して、このような状況を処理します。</span><span class="sxs-lookup"><span data-stu-id="c5925-104">The Ops adapter, combined with the new error reporting feature, handles many of these cases.</span></span>  
  
 <span data-ttu-id="c5925-105">このソリューションでは、新しいエラー報告機能が有効に設定されているポートでアダプタを使用します。</span><span class="sxs-lookup"><span data-stu-id="c5925-105">The solution uses the adapter on a port configured to use the new error reporting feature.</span></span> <span data-ttu-id="c5925-106">アダプターが 2 つのメソッドを呼び出してエラーを受け取ることと、**初期化**と**Execute**、指定したアセンブリ内のクラスにします。</span><span class="sxs-lookup"><span data-stu-id="c5925-106">When it receives an error, the adapter calls two methods, **Initialize** and **Execute**, on a class in a specified assembly.</span></span> <span data-ttu-id="c5925-107">このソリューションでは、これらのメソッドがエラーを正しい操作グループに送信します。</span><span class="sxs-lookup"><span data-stu-id="c5925-107">In the solution, these methods send the error to the correct operations group.</span></span>  
  
 <span data-ttu-id="c5925-108">サンプル ハンドラがソリューションに含まれていますが、独自のハンドラを簡単に作成して、アダプタを他のソリューションで使用することができます。</span><span class="sxs-lookup"><span data-stu-id="c5925-108">The solution includes a sample handler, although you can easily write your own and use the adapter in other solutions.</span></span> <span data-ttu-id="c5925-109">新しいエラー報告機能に関する概要については、次を参照してください。[できませんでしたメッセージのルーティングを使用して](../core/using-failed-message-routing.md)です。</span><span class="sxs-lookup"><span data-stu-id="c5925-109">For general information about the new error reporting feature, see [Using Failed Message Routing](../core/using-failed-message-routing.md).</span></span>  
  
> [!NOTE]
>  <span data-ttu-id="c5925-110">Ops アダプタは、アダプター フレームワークを使用して作成されています。</span><span class="sxs-lookup"><span data-stu-id="c5925-110">The Ops adapter is built using the Adapter Framework.</span></span> <span data-ttu-id="c5925-111">フレームワークでアダプタのビルドについては、次を参照してください。[カスタム アダプターの開発](../core/developing-custom-adapters.md)です。</span><span class="sxs-lookup"><span data-stu-id="c5925-111">For information about building adapters with the framework, see [Developing Custom Adapters](../core/developing-custom-adapters.md).</span></span>  
  
 <span data-ttu-id="c5925-112">このセクションでは、アダプタのしくみとその設定方法と、エラー ハンドラ アセンブリについて詳しく説明します。</span><span class="sxs-lookup"><span data-stu-id="c5925-112">This section describes how the adapter works and how to configure it, and provides details about the error handler assemblies.</span></span> <span data-ttu-id="c5925-113">このセクションの最後では、アダプタを変更したり、他の用途に使用するユーザーに役立つ実装の詳細を説明します。</span><span class="sxs-lookup"><span data-stu-id="c5925-113">The section concludes with implementation details that would be helpful to users who wish to modify the adapter or use it in other applications.</span></span>  
  
## <a name="in-this-section"></a><span data-ttu-id="c5925-114">このセクションの内容</span><span class="sxs-lookup"><span data-stu-id="c5925-114">In This Section</span></span>  
  
-   [<span data-ttu-id="c5925-115">Ops アダプタの使用</span><span class="sxs-lookup"><span data-stu-id="c5925-115">Using the Ops Adapter</span></span>](../core/using-the-ops-adapter.md)  
  
-   [<span data-ttu-id="c5925-116">サンプル操作エラー ハンドラ</span><span class="sxs-lookup"><span data-stu-id="c5925-116">The Sample Operations Error Handler</span></span>](../core/the-sample-operations-error-handler.md)  
  
-   [<span data-ttu-id="c5925-117">Ops アダプタの実装の詳細</span><span class="sxs-lookup"><span data-stu-id="c5925-117">Ops Adapter Implementation Details</span></span>](../core/ops-adapter-implementation-details.md)