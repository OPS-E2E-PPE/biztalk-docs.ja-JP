---
title: カスタム例外ハンドラーの作成 |Microsoft Docs
ms.custom: ''
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: ''
ms.suite: ''
ms.tgt_pltfrm: ''
ms.topic: article
ms.assetid: 401aec8d-d9ca-4a88-9e5b-d3ab605dc0a1
caps.latest.revision: 4
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: 2f2e1daaa0877ea1dc4e9abc24b8b1b36463cd7f
ms.sourcegitcommit: 381e83d43796a345488d54b3f7413e11d56ad7be
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 05/07/2019
ms.locfileid: "65400804"
---
# <a name="creating-custom-exception-handlers"></a><span data-ttu-id="90623-102">カスタム例外ハンドラーの作成</span><span class="sxs-lookup"><span data-stu-id="90623-102">Creating Custom Exception Handlers</span></span>
<span data-ttu-id="90623-103">例外を検出して対処するアプリケーション、開発者は、例外ハンドラーを提供する必要があります。</span><span class="sxs-lookup"><span data-stu-id="90623-103">For an application to detect and react to exceptions, developers must provide an exception handler.</span></span> <span data-ttu-id="90623-104">この例外ハンドラーには、例外メッセージの 1 つの型またはシステムまたはアプリケーションの一部またはすべてのパーツから生成される例外メッセージをサブスクライブできます。</span><span class="sxs-lookup"><span data-stu-id="90623-104">This exception handler can subscribe to a single type of exception message or to exception messages generated from some or all parts of a system or an application.</span></span> <span data-ttu-id="90623-105">たとえば、(すべての例外、給与支払いシステムで発生している) などの特定のシステムからのすべてのメッセージ ハンドラーは 1 つのみを必要となるまたは (チェック プロセスを印刷することを検出するなどの特定のエラーのハンドラーを対象となる代わりにあります。失敗)。</span><span class="sxs-lookup"><span data-stu-id="90623-105">For example, you may require only a single handler for all messages from a particular system (such as any exceptions occurring in the payroll system), or you may instead require targeted handlers for specific failures (such as detecting if the check print process fails).</span></span>  
  
 <span data-ttu-id="90623-106">例外の特定の種類を購読するには、次の例に示すようをアクティブ化の受信図形にフィルターを含むオーケストレーションを使用します。</span><span class="sxs-lookup"><span data-stu-id="90623-106">To subscribe to a specific type of exception, use an orchestration that has a filter on the activating Receive shape, as shown in the following example.</span></span>  
  
```csharp  
Microsoft.Practices.ESB.ExceptionHandling.Schemas.Property.FaultCode == "1000";  
```  
  
 <span data-ttu-id="90623-107">フィルター条件は、メッセージが特定のフィルター条件を満たしている場合、ファイル システムまたは電子メール メッセージを送信する送信ポートでもあります。</span><span class="sxs-lookup"><span data-stu-id="90623-107">You may also have a filter condition on a send port that sends a message to the file system or via e-mail if the message meets a specific filter condition.</span></span>  
  
## <a name="sample-exception-handling-projects"></a><span data-ttu-id="90623-108">例外処理のサンプル プロジェクト</span><span class="sxs-lookup"><span data-stu-id="90623-108">Sample Exception Handling Projects</span></span>  
 <span data-ttu-id="90623-109">[!INCLUDE[esbToolkit](../includes/esbtoolkit-md.md)]例外処理を示すいくつかのサンプル BizTalk アプリケーションが含まれています。</span><span class="sxs-lookup"><span data-stu-id="90623-109">The [!INCLUDE[esbToolkit](../includes/esbtoolkit-md.md)] includes several sample BizTalk applications that demonstrate exception handling.</span></span> <span data-ttu-id="90623-110">これらのサンプルは、\Source\Samples\Exception 処理フォルダーにあります。</span><span class="sxs-lookup"><span data-stu-id="90623-110">These samples can be found in the \Source\Samples\Exception Handling folder.</span></span>  
  
 <span data-ttu-id="90623-111">4 つ BizTalk プロジェクトの場合、GlobalBank.ESB.Samples.ExceptionHandling ソリューション内にある ESB 失敗オーケストレーションの例外ルーティング メカニズムを使用する方法を示すもあります。</span><span class="sxs-lookup"><span data-stu-id="90623-111">There are also four BizTalk projects, located in the GlobalBank.ESB.Samples.ExceptionHandling solution, that demonstrate how to use the ESB Failed Orchestration Exception Routing mechanism.</span></span> <span data-ttu-id="90623-112">GlobalBank.ESB BizTalk アプリケーションに展開するのには、これらのプロジェクトが事前構成済み。</span><span class="sxs-lookup"><span data-stu-id="90623-112">These projects are preconfigured to deploy into the GlobalBank.ESB BizTalk application.</span></span> <span data-ttu-id="90623-113">次のプロジェクトに示します。</span><span class="sxs-lookup"><span data-stu-id="90623-113">The projects are the following:</span></span>  
  
- <span data-ttu-id="90623-114">**ESB します。ExceptionHandling.Schemas します。**</span><span class="sxs-lookup"><span data-stu-id="90623-114">**ESB.ExceptionHandling.Schemas.**</span></span> <span data-ttu-id="90623-115">このプロジェクトには、サンプル オーケストレーションでは、使用するスキーマが含まれています。</span><span class="sxs-lookup"><span data-stu-id="90623-115">This project contains the schemas used for the sample orchestrations.</span></span>  
  
- <span data-ttu-id="90623-116">**ESB します。ExceptionHandling.Pipelines します。**</span><span class="sxs-lookup"><span data-stu-id="90623-116">**ESB.ExceptionHandling.Pipelines.**</span></span> <span data-ttu-id="90623-117">このプロジェクトには、すべての例外をサブスクライブする送信ポートで使用される、例外のプロセッサで構成されている送信パイプラインが含まれています。</span><span class="sxs-lookup"><span data-stu-id="90623-117">This project contains the send pipeline configured with the exception processor, used in a send port that subscribes to all exceptions.</span></span> <span data-ttu-id="90623-118">これには、BizTalk、および例外管理フレームワークによって生成される例外によって生成される例外が含まれます。</span><span class="sxs-lookup"><span data-stu-id="90623-118">This includes exceptions generated by BizTalk and exceptions generated by the Exception Management Framework.</span></span>  
  
- <span data-ttu-id="90623-119">**ESB します。ExceptionHandling.Processes します。**</span><span class="sxs-lookup"><span data-stu-id="90623-119">**ESB.ExceptionHandling.Processes.**</span></span> <span data-ttu-id="90623-120">このプロジェクトには、0 からの呼び出しで除算しようとして例外をシミュレートする EAIProcess.odx オーケストレーションが含まれています、 **CreateFaultMessage**と**AddMessage**適切なを生成する方法図 1 に示すエラー メッセージ。</span><span class="sxs-lookup"><span data-stu-id="90623-120">This project contains the EAIProcess.odx orchestration, which simulates an exception by attempting to divide by zero and calls the **CreateFaultMessage** and **AddMessage** methods to generate a suitable fault message, as shown in Figure 1.</span></span>  
  
   <span data-ttu-id="90623-121">![オーケストレーション プロセス サンプル](../esb-toolkit/media/ch4-orchestrationprocessessample.gif "Ch4 OrchestrationProcessesSample")</span><span class="sxs-lookup"><span data-stu-id="90623-121">![Orchestration Processes Sample](../esb-toolkit/media/ch4-orchestrationprocessessample.gif "Ch4-OrchestrationProcessesSample")</span></span>  
  
   <span data-ttu-id="90623-122">**図 1**</span><span class="sxs-lookup"><span data-stu-id="90623-122">**Figure 1**</span></span>  
  
  <span data-ttu-id="90623-123">**プロセスのサンプル プロジェクトで EAIProcess.odx オーケストレーション**</span><span class="sxs-lookup"><span data-stu-id="90623-123">**The EAIProcess.odx orchestration in the Processes sample project**</span></span>  
  
- <span data-ttu-id="90623-124">**ESB します。ExceptionHandling.Handlers します。**</span><span class="sxs-lookup"><span data-stu-id="90623-124">**ESB.ExceptionHandling.Handlers.**</span></span> <span data-ttu-id="90623-125">このプロジェクトには、呼び出す EAIGenericHandler.odx オーケストレーションが含まれています、 **GetMessages**メソッドを反復処理し、 **MessageCollection**を使用して、 **MoveNext**メソッド、図 2 に示すようにします。</span><span class="sxs-lookup"><span data-stu-id="90623-125">This project contains the EAIGenericHandler.odx orchestration, which calls the **GetMessages** method and iterates through the **MessageCollection** using the **MoveNext** method, as shown in Figure 2.</span></span>  
  
  <span data-ttu-id="90623-126">![オーケストレーション ハンドラーのサンプル ジェネリック](../esb-toolkit/media/ch4-orchestrationhandlerssamplegeneric.gif "Ch4 OrchestrationHandlersSampleGeneric")</span><span class="sxs-lookup"><span data-stu-id="90623-126">![Orchestration Handlers Sample Generic](../esb-toolkit/media/ch4-orchestrationhandlerssamplegeneric.gif "Ch4-OrchestrationHandlersSampleGeneric")</span></span>  
  
  <span data-ttu-id="90623-127">**図 2**</span><span class="sxs-lookup"><span data-stu-id="90623-127">**Figure 2**</span></span>  
  
  <span data-ttu-id="90623-128">**ハンドラーのサンプル プロジェクトで EAIGenericHandler.odx オーケストレーション**</span><span class="sxs-lookup"><span data-stu-id="90623-128">**The EAIGenericHandler.odx orchestration in the Handlers sample project**</span></span>  
  
  <span data-ttu-id="90623-129">ESB します。ExceptionHandling.Handlers プロジェクトには、呼び出す EAIProcessHandler.odx オーケストレーションも含まれています、 **GetMessage**と**GetException**メソッド、図 3 に示すようにします。</span><span class="sxs-lookup"><span data-stu-id="90623-129">The ESB.ExceptionHandling.Handlers project also contains the EAIProcessHandler.odx orchestration, which calls the **GetMessage** and **GetException** methods, as shown in Figure 3.</span></span>  
  
  <span data-ttu-id="90623-130">![オーケストレーション ハンドラーのサンプル プロセス](../esb-toolkit/media/ch4-orchestrationhandlerssampleprocess.gif "Ch4 OrchestrationHandlersSampleProcess")</span><span class="sxs-lookup"><span data-stu-id="90623-130">![Orchestration Handlers Sample Process](../esb-toolkit/media/ch4-orchestrationhandlerssampleprocess.gif "Ch4-OrchestrationHandlersSampleProcess")</span></span>  
  
  <span data-ttu-id="90623-131">**図 3**</span><span class="sxs-lookup"><span data-stu-id="90623-131">**Figure 3**</span></span>  
  
  <span data-ttu-id="90623-132">**ハンドラーのサンプル プロジェクトで EAIProcessHandler.odx オーケストレーション**</span><span class="sxs-lookup"><span data-stu-id="90623-132">**The EAIProcessHandler.odx orchestration in the Handlers sample project**</span></span>