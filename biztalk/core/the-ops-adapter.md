---
title: Ops アダプタ |Microsoft Docs
ms.custom: ''
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: ''
ms.suite: ''
ms.tgt_pltfrm: ''
ms.topic: article
helpviewer_keywords:
- adapters, Ops adapters
- Ops adapters, about Ops adapters
- Ops adapters
- process management solution tutorial, Ops adapters
- process management solution tutorial, errors
ms.assetid: 7f747a5f-14af-4e4c-bc29-f083f8f00bd0
caps.latest.revision: 13
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: 052fff3518e3a302c6b632e9852a9d0c8f6b5ceb
ms.sourcegitcommit: 381e83d43796a345488d54b3f7413e11d56ad7be
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 05/07/2019
ms.locfileid: "65277943"
---
# <a name="the-ops-adapter"></a><span data-ttu-id="d1e78-102">Ops アダプタ</span><span class="sxs-lookup"><span data-stu-id="d1e78-102">The Ops Adapter</span></span>
<span data-ttu-id="d1e78-103">ソリューションの設計は、渡すには、可能であれば、問題を示すメッセージとエラーを修正するか、終了順序を決定するオペレーション システムにエラーです。</span><span class="sxs-lookup"><span data-stu-id="d1e78-103">The design of the solution is to pass, where possible, problematic messages and errors to operations systems that make a decision about fixing the error or terminating the order.</span></span> <span data-ttu-id="d1e78-104">新しいエラー報告機能を組み合わせて、Ops アダプタは、多くの場合を処理します。</span><span class="sxs-lookup"><span data-stu-id="d1e78-104">The Ops adapter, combined with the new error reporting feature, handles many of these cases.</span></span>  
  
 <span data-ttu-id="d1e78-105">ソリューションでは、新しいエラー報告機能を使用するように構成のポートでアダプターを使用します。</span><span class="sxs-lookup"><span data-stu-id="d1e78-105">The solution uses the adapter on a port configured to use the new error reporting feature.</span></span> <span data-ttu-id="d1e78-106">アダプターが 2 つのメソッドを呼び出してエラーを受信した場合**初期化**と**Execute**、指定したアセンブリ内のクラスにします。</span><span class="sxs-lookup"><span data-stu-id="d1e78-106">When it receives an error, the adapter calls two methods, **Initialize** and **Execute**, on a class in a specified assembly.</span></span> <span data-ttu-id="d1e78-107">ソリューションでは、これらのメソッドは、正しい操作グループに、エラーを送信します。</span><span class="sxs-lookup"><span data-stu-id="d1e78-107">In the solution, these methods send the error to the correct operations group.</span></span>  
  
 <span data-ttu-id="d1e78-108">ソリューションには、独自に作成し、その他のソリューションでアダプターを使用できますが、簡単にサンプルのハンドラーが含まれています。</span><span class="sxs-lookup"><span data-stu-id="d1e78-108">The solution includes a sample handler, although you can easily write your own and use the adapter in other solutions.</span></span> <span data-ttu-id="d1e78-109">新しいエラー報告機能については、次を参照してください。[できませんでしたメッセージのルーティングを使用して](../core/using-failed-message-routing.md)します。</span><span class="sxs-lookup"><span data-stu-id="d1e78-109">For general information about the new error reporting feature, see [Using Failed Message Routing](../core/using-failed-message-routing.md).</span></span>  
  
> [!NOTE]
>  <span data-ttu-id="d1e78-110">Ops アダプタは、アダプター フレームワークを使用して構築されています。</span><span class="sxs-lookup"><span data-stu-id="d1e78-110">The Ops adapter is built using the Adapter Framework.</span></span> <span data-ttu-id="d1e78-111">アダプタ フレームワークを構築する方法については、次を参照してください。[カスタム アダプターの開発](../core/developing-custom-adapters.md)します。</span><span class="sxs-lookup"><span data-stu-id="d1e78-111">For information about building adapters with the framework, see [Developing Custom Adapters](../core/developing-custom-adapters.md).</span></span>  
  
 <span data-ttu-id="d1e78-112">このセクションでは、アダプターのしくみと、それを構成する方法について説明し、ハンドラー アセンブリ エラーの詳細を提供します。</span><span class="sxs-lookup"><span data-stu-id="d1e78-112">This section describes how the adapter works and how to configure it, and provides details about the error handler assemblies.</span></span> <span data-ttu-id="d1e78-113">セクションの最後で、アダプターを変更またはその他のアプリケーションで使用するユーザーのために、役立つ実装の詳細。</span><span class="sxs-lookup"><span data-stu-id="d1e78-113">The section concludes with implementation details that would be helpful to users who wish to modify the adapter or use it in other applications.</span></span>  
  
## <a name="in-this-section"></a><span data-ttu-id="d1e78-114">このセクションの内容</span><span class="sxs-lookup"><span data-stu-id="d1e78-114">In This Section</span></span>  
  
-   [<span data-ttu-id="d1e78-115">Ops アダプタの使用</span><span class="sxs-lookup"><span data-stu-id="d1e78-115">Using the Ops Adapter</span></span>](../core/using-the-ops-adapter.md)  
  
-   [<span data-ttu-id="d1e78-116">サンプル操作エラー ハンドラー</span><span class="sxs-lookup"><span data-stu-id="d1e78-116">The Sample Operations Error Handler</span></span>](../core/the-sample-operations-error-handler.md)  
  
-   [<span data-ttu-id="d1e78-117">Ops アダプターの実装の詳細</span><span class="sxs-lookup"><span data-stu-id="d1e78-117">Ops Adapter Implementation Details</span></span>](../core/ops-adapter-implementation-details.md)