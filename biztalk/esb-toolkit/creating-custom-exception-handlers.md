---
title: "カスタム例外ハンドラーの作成 |Microsoft ドキュメント"
ms.custom: 
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: 
ms.suite: 
ms.tgt_pltfrm: 
ms.topic: article
ms.assetid: 401aec8d-d9ca-4a88-9e5b-d3ab605dc0a1
caps.latest.revision: "4"
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: 91f725084c838d026f9028f0ac2e684ec2d727c6
ms.sourcegitcommit: cb908c540d8f1a692d01dc8f313e16cb4b4e696d
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 09/20/2017
---
# <a name="creating-custom-exception-handlers"></a><span data-ttu-id="b90f2-102">カスタム例外ハンドラーの作成</span><span class="sxs-lookup"><span data-stu-id="b90f2-102">Creating Custom Exception Handlers</span></span>
<span data-ttu-id="b90f2-103">例外を検出して処理するアプリケーションは、開発者は、例外ハンドラーを提供する必要があります。</span><span class="sxs-lookup"><span data-stu-id="b90f2-103">For an application to detect and react to exceptions, developers must provide an exception handler.</span></span> <span data-ttu-id="b90f2-104">この例外ハンドラーは、例外メッセージの単一の型と、システムまたはアプリケーションの一部またはすべての部分から生成された例外メッセージをサブスクライブできます。</span><span class="sxs-lookup"><span data-stu-id="b90f2-104">This exception handler can subscribe to a single type of exception message or to exception messages generated from some or all parts of a system or an application.</span></span> <span data-ttu-id="b90f2-105">たとえば、(など、例外、給与支払いシステムで発生している)、特定のシステムからのすべてのメッセージを 1 つのハンドラーのみが必要な場合があります。 か (チェック プロセスを印刷することを検出するなどの特定のエラーのハンドラーを対象となる代わりにあります。失敗する)。</span><span class="sxs-lookup"><span data-stu-id="b90f2-105">For example, you may require only a single handler for all messages from a particular system (such as any exceptions occurring in the payroll system), or you may instead require targeted handlers for specific failures (such as detecting if the check print process fails).</span></span>  
  
 <span data-ttu-id="b90f2-106">特定の種類の例外をサブスクライブするには、次の例で示すようにフィルターを持つ、アクティブ化受信図形 オーケストレーションを使用します。</span><span class="sxs-lookup"><span data-stu-id="b90f2-106">To subscribe to a specific type of exception, use an orchestration that has a filter on the activating Receive shape, as shown in the following example.</span></span>  
  
```csharp  
Microsoft.Practices.ESB.ExceptionHandling.Schemas.Property.FaultCode == "1000";  
```  
  
 <span data-ttu-id="b90f2-107">フィルター条件は、メッセージが特定のフィルター条件を満たしている場合、ファイル システムまたは電子メール メッセージを送信する送信ポートでもあります。</span><span class="sxs-lookup"><span data-stu-id="b90f2-107">You may also have a filter condition on a send port that sends a message to the file system or via e-mail if the message meets a specific filter condition.</span></span>  
  
## <a name="sample-exception-handling-projects"></a><span data-ttu-id="b90f2-108">例外処理のサンプル プロジェクト</span><span class="sxs-lookup"><span data-stu-id="b90f2-108">Sample Exception Handling Projects</span></span>  
 <span data-ttu-id="b90f2-109">[!INCLUDE[esbToolkit](../includes/esbtoolkit-md.md)]例外処理を示すいくつかのサンプル BizTalk アプリケーションが含まれています。</span><span class="sxs-lookup"><span data-stu-id="b90f2-109">The [!INCLUDE[esbToolkit](../includes/esbtoolkit-md.md)] includes several sample BizTalk applications that demonstrate exception handling.</span></span> <span data-ttu-id="b90f2-110">これらのサンプルは、\Source\Samples\Exception 処理フォルダーで確認できます。</span><span class="sxs-lookup"><span data-stu-id="b90f2-110">These samples can be found in the \Source\Samples\Exception Handling folder.</span></span>  
  
 <span data-ttu-id="b90f2-111">次の 4 つ BizTalk プロジェクト、GlobalBank.ESB.Samples.ExceptionHandling ソリューション内にある、ESB 失敗オーケストレーション例外ルーティング機構を使用する方法を示すもあります。</span><span class="sxs-lookup"><span data-stu-id="b90f2-111">There are also four BizTalk projects, located in the GlobalBank.ESB.Samples.ExceptionHandling solution, that demonstrate how to use the ESB Failed Orchestration Exception Routing mechanism.</span></span> <span data-ttu-id="b90f2-112">GlobalBank.ESB BizTalk アプリケーションに展開するのには、これらのプロジェクトがあらかじめ設定されています。</span><span class="sxs-lookup"><span data-stu-id="b90f2-112">These projects are preconfigured to deploy into the GlobalBank.ESB BizTalk application.</span></span> <span data-ttu-id="b90f2-113">次のプロジェクトに示します。</span><span class="sxs-lookup"><span data-stu-id="b90f2-113">The projects are the following:</span></span>  
  
-   <span data-ttu-id="b90f2-114">**ESB です。ExceptionHandling.Schemas です。**</span><span class="sxs-lookup"><span data-stu-id="b90f2-114">**ESB.ExceptionHandling.Schemas.**</span></span> <span data-ttu-id="b90f2-115">このプロジェクトには、サンプル オーケストレーションに使用するスキーマが含まれています。</span><span class="sxs-lookup"><span data-stu-id="b90f2-115">This project contains the schemas used for the sample orchestrations.</span></span>  
  
-   <span data-ttu-id="b90f2-116">**ESB です。ExceptionHandling.Pipelines です。**</span><span class="sxs-lookup"><span data-stu-id="b90f2-116">**ESB.ExceptionHandling.Pipelines.**</span></span> <span data-ttu-id="b90f2-117">このプロジェクトには、すべての例外をサブスクライブする送信ポートで使用される、例外のプロセッサで構成されている送信パイプラインが含まれています。</span><span class="sxs-lookup"><span data-stu-id="b90f2-117">This project contains the send pipeline configured with the exception processor, used in a send port that subscribes to all exceptions.</span></span> <span data-ttu-id="b90f2-118">これには、BizTalk、および例外管理フレームワークによって生成される例外によって生成される例外が含まれます。</span><span class="sxs-lookup"><span data-stu-id="b90f2-118">This includes exceptions generated by BizTalk and exceptions generated by the Exception Management Framework.</span></span>  
  
-   <span data-ttu-id="b90f2-119">**ESB です。ExceptionHandling.Processes です。**</span><span class="sxs-lookup"><span data-stu-id="b90f2-119">**ESB.ExceptionHandling.Processes.**</span></span> <span data-ttu-id="b90f2-120">このプロジェクトには、0 との呼び出しで除算しようとして例外をシミュレートする EAIProcess.odx オーケストレーションが含まれています、 **CreateFaultMessage**と**AddMessage**適切なを生成する方法図 1 に示すエラー メッセージ。</span><span class="sxs-lookup"><span data-stu-id="b90f2-120">This project contains the EAIProcess.odx orchestration, which simulates an exception by attempting to divide by zero and calls the **CreateFaultMessage** and **AddMessage** methods to generate a suitable fault message, as shown in Figure 1.</span></span>  
  
     <span data-ttu-id="b90f2-121">![オーケストレーションで処理サンプル](../esb-toolkit/media/ch4-orchestrationprocessessample.gif "Ch4 OrchestrationProcessesSample")</span><span class="sxs-lookup"><span data-stu-id="b90f2-121">![Orchestration Processes Sample](../esb-toolkit/media/ch4-orchestrationprocessessample.gif "Ch4-OrchestrationProcessesSample")</span></span>  
  
     <span data-ttu-id="b90f2-122">**図 1**</span><span class="sxs-lookup"><span data-stu-id="b90f2-122">**Figure 1**</span></span>  
  
 <span data-ttu-id="b90f2-123">**プロセスのサンプル プロジェクトで EAIProcess.odx オーケストレーション**</span><span class="sxs-lookup"><span data-stu-id="b90f2-123">**The EAIProcess.odx orchestration in the Processes sample project**</span></span>  
  
-   <span data-ttu-id="b90f2-124">**ESB です。ExceptionHandling.Handlers です。**</span><span class="sxs-lookup"><span data-stu-id="b90f2-124">**ESB.ExceptionHandling.Handlers.**</span></span> <span data-ttu-id="b90f2-125">このプロジェクトに呼び出す EAIGenericHandler.odx オーケストレーションが含まれています、 **GetMessages**メソッドを繰り返し処理して、 **MessageCollection**を使用して、 **MoveNext**メソッド、図 2 に示すようにします。</span><span class="sxs-lookup"><span data-stu-id="b90f2-125">This project contains the EAIGenericHandler.odx orchestration, which calls the **GetMessages** method and iterates through the **MessageCollection** using the **MoveNext** method, as shown in Figure 2.</span></span>  
  
 <span data-ttu-id="b90f2-126">![オーケストレーション ハンドラーのサンプル ジェネリック](../esb-toolkit/media/ch4-orchestrationhandlerssamplegeneric.gif "Ch4 OrchestrationHandlersSampleGeneric")</span><span class="sxs-lookup"><span data-stu-id="b90f2-126">![Orchestration Handlers Sample Generic](../esb-toolkit/media/ch4-orchestrationhandlerssamplegeneric.gif "Ch4-OrchestrationHandlersSampleGeneric")</span></span>  
  
 <span data-ttu-id="b90f2-127">**図 2**</span><span class="sxs-lookup"><span data-stu-id="b90f2-127">**Figure 2**</span></span>  
  
 <span data-ttu-id="b90f2-128">**ハンドラーのサンプル プロジェクトで EAIGenericHandler.odx オーケストレーション**</span><span class="sxs-lookup"><span data-stu-id="b90f2-128">**The EAIGenericHandler.odx orchestration in the Handlers sample project**</span></span>  
  
 <span data-ttu-id="b90f2-129">ESB です。ExceptionHandling.Handlers プロジェクトには、呼び出す EAIProcessHandler.odx オーケストレーションも含まれています、 **GetMessage**と**GetException**メソッド、図 3 に示すようにします。</span><span class="sxs-lookup"><span data-stu-id="b90f2-129">The ESB.ExceptionHandling.Handlers project also contains the EAIProcessHandler.odx orchestration, which calls the **GetMessage** and **GetException** methods, as shown in Figure 3.</span></span>  
  
 <span data-ttu-id="b90f2-130">![オーケストレーション ハンドラーのサンプル プロセス](../esb-toolkit/media/ch4-orchestrationhandlerssampleprocess.gif "Ch4 OrchestrationHandlersSampleProcess")</span><span class="sxs-lookup"><span data-stu-id="b90f2-130">![Orchestration Handlers Sample Process](../esb-toolkit/media/ch4-orchestrationhandlerssampleprocess.gif "Ch4-OrchestrationHandlersSampleProcess")</span></span>  
  
 <span data-ttu-id="b90f2-131">**図 3**</span><span class="sxs-lookup"><span data-stu-id="b90f2-131">**Figure 3**</span></span>  
  
 <span data-ttu-id="b90f2-132">**ハンドラーのサンプル プロジェクトで EAIProcessHandler.odx オーケストレーション**</span><span class="sxs-lookup"><span data-stu-id="b90f2-132">**The EAIProcessHandler.odx orchestration in the Handlers sample project**</span></span>