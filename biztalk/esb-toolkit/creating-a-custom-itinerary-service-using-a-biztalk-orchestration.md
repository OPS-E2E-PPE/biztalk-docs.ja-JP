---
title: BizTalk オーケストレーションを使用してカスタム Itinerary サービスを作成する |Microsoft ドキュメント
ms.custom: ''
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: ''
ms.suite: ''
ms.tgt_pltfrm: ''
ms.topic: article
ms.assetid: 3bd7ed38-02a3-41b1-9990-754d5539f15e
caps.latest.revision: 4
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: 723c0bc93192267f404d42e7fe859bb37ea59895
ms.sourcegitcommit: cb908c540d8f1a692d01dc8f313e16cb4b4e696d
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 09/20/2017
ms.locfileid: "22289810"
---
# <a name="creating-a-custom-itinerary-service-using-a-biztalk-orchestration"></a><span data-ttu-id="e357c-102">BizTalk オーケストレーションを使用してカスタム Itinerary サービスを作成します。</span><span class="sxs-lookup"><span data-stu-id="e357c-102">Creating a Custom Itinerary Service Using a BizTalk Orchestration</span></span>
<span data-ttu-id="e357c-103">Itinerary フレームワークの一部である、[!INCLUDE[esbToolkit](../includes/esbtoolkit-md.md)]オーケストレーションを使用して、itinerary 手順の実行をサポートします。</span><span class="sxs-lookup"><span data-stu-id="e357c-103">The itinerary framework that is part of the [!INCLUDE[esbToolkit](../includes/esbtoolkit-md.md)] supports execution of itinerary steps using orchestrations.</span></span> <span data-ttu-id="e357c-104">以下のことがありますが、機能の要件に基づいて、Microsoft BizTalk Server オーケストレーションとしてカスタム itinerary サービスを実装することができます。</span><span class="sxs-lookup"><span data-stu-id="e357c-104">You can implement a custom itinerary service as a Microsoft BizTalk Server orchestration based on your functional requirements, which may include the following:</span></span>  
  
-   <span data-ttu-id="e357c-105">複数のサービスの呼び出し (に示すように、[をインストールして、スキャッター/ギャザー サンプルを実行している](../esb-toolkit/installing-and-running-the-scatter-gather-sample.md))</span><span class="sxs-lookup"><span data-stu-id="e357c-105">Multiple service invocations (as demonstrated by the [Installing and Running the Scatter-Gather Sample](../esb-toolkit/installing-and-running-the-scatter-gather-sample.md))</span></span>  
  
-   <span data-ttu-id="e357c-106">プロトコル仲介およびメッセージの相関関係 (たとえば、HTTP、MQSeries)</span><span class="sxs-lookup"><span data-stu-id="e357c-106">Protocol mediation and message correlation (for example, HTTP-MQSeries)</span></span>  
  
-   <span data-ttu-id="e357c-107">複雑なルーティングの決定に基づいてメッセージを強化外部データからソース</span><span class="sxs-lookup"><span data-stu-id="e357c-107">Complex routing decisions based on message enrichment from external data sources</span></span>  
  
-   <span data-ttu-id="e357c-108">ビジネス処理のロジック</span><span class="sxs-lookup"><span data-stu-id="e357c-108">Business processing logic</span></span>  
  
 <span data-ttu-id="e357c-109">BizTalk Server オーケストレーションを使用して実装すべて itinerary サービスは、次の場合です。</span><span class="sxs-lookup"><span data-stu-id="e357c-109">Every itinerary service implemented using a BizTalk Server orchestration is responsible for the following:</span></span>  
  
-   <span data-ttu-id="e357c-110">例外と ESB 例外処理のフレームワークまたは (一方向の日程) の再送信をサポートする省略可能なカスタム例外ハンドラーを使用して、エラー処理</span><span class="sxs-lookup"><span data-stu-id="e357c-110">Exception and error handling using the ESB Exception Handling Framework or optional custom exception handlers that support resubmission (one-way itineraries)</span></span>  
  
-   <span data-ttu-id="e357c-111">旅行計画を進めると、次の itinerary サービス ステップが実行できるように、BizTalk Server を経由して送信メッセージを発行</span><span class="sxs-lookup"><span data-stu-id="e357c-111">Advancing the itinerary and publishing outbound messages through BizTalk Server so that the next itinerary service step can execute</span></span>  
  
#### <a name="to-create-a-custom-itinerary-service-using-a-biztalk-server-orchestration"></a><span data-ttu-id="e357c-112">BizTalk Server オーケストレーションを使用してカスタム itinerary サービスを作成するには</span><span class="sxs-lookup"><span data-stu-id="e357c-112">To create a custom itinerary service using a BizTalk Server orchestration</span></span>  
  
1.  <span data-ttu-id="e357c-113">新しいオーケストレーション; を含む新しい BizTalk Server プロジェクトを作成します。たとえば、MyCustomeItineraryService.odx です。</span><span class="sxs-lookup"><span data-stu-id="e357c-113">Create new BizTalk Server project containing a new orchestration; for example, MyCustomeItineraryService.odx.</span></span>  
  
2.  <span data-ttu-id="e357c-114">次のアセンブリへの参照を追加します。</span><span class="sxs-lookup"><span data-stu-id="e357c-114">Add references to the following assemblies:</span></span>  
  
    -   <span data-ttu-id="e357c-115">**Microsoft.Practices.ESB.Itinerary**</span><span class="sxs-lookup"><span data-stu-id="e357c-115">**Microsoft.Practices.ESB.Itinerary**</span></span>  
  
    -   <span data-ttu-id="e357c-116">**Microsoft.Practices.ESB.Itinerary.Schemas**</span><span class="sxs-lookup"><span data-stu-id="e357c-116">**Microsoft.Practices.ESB.Itinerary.Schemas**</span></span>  
  
    -   <span data-ttu-id="e357c-117">**Microsoft.Practices.ESB.ExceptionHandling**</span><span class="sxs-lookup"><span data-stu-id="e357c-117">**Microsoft.Practices.ESB.ExceptionHandling**</span></span>  
  
    -   <span data-ttu-id="e357c-118">**Microsoft.Practices.ESB.ExceptionHandling.Faults**</span><span class="sxs-lookup"><span data-stu-id="e357c-118">**Microsoft.Practices.ESB.ExceptionHandling.Faults**</span></span>  
  
3.  <span data-ttu-id="e357c-119">論理の直接バインドを定義するポートとアクティブ化された受信図形をオーケストレーションで受信します。</span><span class="sxs-lookup"><span data-stu-id="e357c-119">Define a logical direct-bound receive port and an activated receive shape in the orchestration.</span></span>  
  
4.  <span data-ttu-id="e357c-120">オーケストレーションが実行されるように、メッセージの itinerary コンテキストからオーケストレーションをアクティブ化するためのサブスクリプション フィルターを定義、 **MyCustomItineraryService**手順です。</span><span class="sxs-lookup"><span data-stu-id="e357c-120">Define a subscription filter to activate the orchestration from the message itinerary context so that the orchestration executes the **MyCustomItineraryService** step.</span></span> <span data-ttu-id="e357c-121">次のコードでは、適切なフィルターの例を示します。</span><span class="sxs-lookup"><span data-stu-id="e357c-121">The following code shows an example of a suitable filter.</span></span>  
  
    ```csharp  
    (Microsoft.Practices.ESB.Itinerary.Schemas.ServiceName   
        == "MyCustomItineraryService")   
    && (Microsoft.Practices.ESB.Itinerary.Schemas.ServiceState == "Pending")  
    && (Microsoft.Practices.ESB.Itinerary.Schemas.ServiceType   
        == "Orchestration")  
    ```  
  
5.  <span data-ttu-id="e357c-122">型のオーケストレーションを定義する**Microsoft.Practices.ESB.Itinerary.ItineraryStep**です。</span><span class="sxs-lookup"><span data-stu-id="e357c-122">Define an orchestration of type **Microsoft.Practices.ESB.Itinerary.ItineraryStep**.</span></span> <span data-ttu-id="e357c-123">次のコードに示すように、この変数を設定するオーケストレーションに式アクティビティを追加します。</span><span class="sxs-lookup"><span data-stu-id="e357c-123">Add an expression activity to the orchestration that populates this variable, as shown in the following code.</span></span>  
  
    ```csharp  
    // Retrieve the current itinerary step.  
    itinerary = new Microsoft.Practices.ESB.Itinerary.SerializableItineraryWrapper();  
    step = new Microsoft.Practices.ESB.Itinerary.SerializableItineraryStepWrapper();  
  
    itinerary.Itinerary = Microsoft.Practices.ESB.Itinerary.ItineraryOMFactory.Create(InboundMessage);  
    step.ItineraryStep = itinerary.Itinerary.GetItineraryStep(InboundMessage);  
  
    ```  
  
6.  <span data-ttu-id="e357c-124">手順については、[次へ] itinerary; 送信メッセージを作成する旅行計画に、カスタム実装を追加します。たとえば、OutboundMsg です。</span><span class="sxs-lookup"><span data-stu-id="e357c-124">Add your custom implementation to the itinerary that creates the outbound message for the next itinerary steps; for example, OutboundMsg.</span></span>  
  
7.  <span data-ttu-id="e357c-125">受信メッセージからメッセージ コンテキストを使用する次の式アクティビティを使用して旅程を進めます。</span><span class="sxs-lookup"><span data-stu-id="e357c-125">Advance the itinerary using the following expression activity that uses the message context from inbound message.</span></span>  
  
    ```csharp  
    OutboundMessage(*) = InboundMessage(*);   
    itinerary.Itinerary.Advance(OutboundMessage, itineraryStep.ItineraryStep);  
    ```  
  
8.  <span data-ttu-id="e357c-126">[次へ] の itinerary サービスを有効に直接バインドの送信ポートを通じて更新行程、送信メッセージを送信します。</span><span class="sxs-lookup"><span data-stu-id="e357c-126">Send the outbound message with the updated itinerary through a direct-bound send port to activate the next itinerary service.</span></span>  
  
 <span data-ttu-id="e357c-127">BizTalk Server オーケストレーションを使用してカスタム itinerary サービスの実装の詳細については、次を参照してください[のインストールと旅程ランプでサンプルを実行して](../esb-toolkit/installing-and-running-the-itinerary-on-ramp-sample.md)と[インストールしてスキャッター/ギャザーを実行する。サンプル](../esb-toolkit/installing-and-running-the-scatter-gather-sample.md)です。</span><span class="sxs-lookup"><span data-stu-id="e357c-127">For more information about implementing a custom itinerary service using BizTalk Server orchestrations, see [Installing and Running the Itinerary On-Ramp Sample](../esb-toolkit/installing-and-running-the-itinerary-on-ramp-sample.md) and [Installing and Running the Scatter-Gather Sample](../esb-toolkit/installing-and-running-the-scatter-gather-sample.md).</span></span>