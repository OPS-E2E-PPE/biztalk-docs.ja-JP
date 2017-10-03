---
title: "カスタム Itinerary メッセージング サービスを作成する |Microsoft ドキュメント"
ms.custom: 
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: 
ms.suite: 
ms.tgt_pltfrm: 
ms.topic: article
ms.assetid: 2de44c21-68ca-4cf1-a117-bcb35af1b4a9
caps.latest.revision: "2"
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: bcf96e8f76a9d2a6ad51bac462c2da101812911d
ms.sourcegitcommit: cb908c540d8f1a692d01dc8f313e16cb4b4e696d
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 09/20/2017
---
# <a name="creating-a-custom-itinerary-messaging-service"></a><span data-ttu-id="83d39-102">カスタム Itinerary メッセージング サービスを作成します。</span><span class="sxs-lookup"><span data-stu-id="83d39-102">Creating a Custom Itinerary Messaging Service</span></span>
<span data-ttu-id="83d39-103">Itinerary フレームワークの一部である、[!INCLUDE[esbToolkit](../includes/esbtoolkit-md.md)]を実装するクラスを使用して、itinerary 手順の実行をサポートしている、 **IMessagingService** itinerary メッセージング サービスを実行するインターフェイスです。</span><span class="sxs-lookup"><span data-stu-id="83d39-103">The itinerary framework that is part of the [!INCLUDE[esbToolkit](../includes/esbtoolkit-md.md)] supports execution of itinerary steps using classes implementing the **IMessagingService** interface that execute itinerary messaging services.</span></span> <span data-ttu-id="83d39-104">サービスで、次を担当するときに、カスタムのメッセージング サービスを実装できます。</span><span class="sxs-lookup"><span data-stu-id="83d39-104">You can implement a custom messaging service when you want the service to be responsible for the following:</span></span>  
  
-   <span data-ttu-id="83d39-105">Itinerary で構成されているカスタム メッセージの検証</span><span class="sxs-lookup"><span data-stu-id="83d39-105">Custom message validation configured in the itinerary</span></span>  
  
-   <span data-ttu-id="83d39-106">Itinerary で構成されているカスタム メッセージ変換</span><span class="sxs-lookup"><span data-stu-id="83d39-106">Custom message transformation configured in the itinerary</span></span>  
  
-   <span data-ttu-id="83d39-107">メッセージのカスタム処理</span><span class="sxs-lookup"><span data-stu-id="83d39-107">Custom processing of the message</span></span>  
  
 <span data-ttu-id="83d39-108">これらすべてのケースでは、実装するカスタムの itinerary サービスは、インターセプターとして機能し、ディスパッチャー パイプライン コンポーネントによって呼び出されます。</span><span class="sxs-lookup"><span data-stu-id="83d39-108">In all these cases, a custom itinerary service that you implement acts as an interceptor and is called by the Dispatcher pipeline component.</span></span>  
  
 <span data-ttu-id="83d39-109">カスタム メッセージに基づく itinerary のサービス、またはメッセージング サービス、すべての実装、 **IMessagingService**インターフェイスです。</span><span class="sxs-lookup"><span data-stu-id="83d39-109">Custom messaging-based itinerary services, or messaging services, all implement the **IMessagingService** interface.</span></span> <span data-ttu-id="83d39-110">このインターフェイスを公開、**名前**と**SupportsDisassemble**プロパティおよび**Execute**と**ShouldAdvanceStep**メソッドです。</span><span class="sxs-lookup"><span data-stu-id="83d39-110">This interface exposes the **Name** and **SupportsDisassemble** properties and the **Execute** and **ShouldAdvanceStep** methods.</span></span>  
  
 <span data-ttu-id="83d39-111">**名前**プロパティは、サービスの名前、行程に表示されます。</span><span class="sxs-lookup"><span data-stu-id="83d39-111">The **Name** property is the name of the service as it will appear in an itinerary.</span></span> <span data-ttu-id="83d39-112">Itinerary サービス構成 Esb.config ファイルで構成されている名前と一致している必要があります。</span><span class="sxs-lookup"><span data-stu-id="83d39-112">It must match the configured name in the itinerary services configuration in the Esb.config file.</span></span>  
  
 <span data-ttu-id="83d39-113">**SupportsDisassemble**プロパティは、サポートを作成するカスタムのメッセージング サービスを逆アセンブルするかどうかと複数の競合回避モジュールの実行を示します。</span><span class="sxs-lookup"><span data-stu-id="83d39-113">The **SupportsDisassemble** property indicates whether the custom messaging service you are creating supports disassemble and the execution of multiple resolvers.</span></span>  
  
 <span data-ttu-id="83d39-114">**ShouldAdvanceStep**メソッドは、現在の itinerary ステップと現在のメッセージでは取得し、サービスの実行後に、ディスパッチャーが旅行計画を進める必要があるかどうかを示すブール値を返します。</span><span class="sxs-lookup"><span data-stu-id="83d39-114">The **ShouldAdvanceStep** method takes in the current itinerary step, and the current message, and returns a Boolean value that indicates whether the dispatcher should advance the itinerary after the service executes.</span></span> <span data-ttu-id="83d39-115">ほとんどの場合、このメソッドが返す**true**です。</span><span class="sxs-lookup"><span data-stu-id="83d39-115">In almost all cases, this method should return **true**.</span></span>  
  
 <span data-ttu-id="83d39-116">**Execute**メソッド メッセージング サービスの最も重要なは、実行時に実行されるロジックを含んでいます。</span><span class="sxs-lookup"><span data-stu-id="83d39-116">The **Execute** method is of greatest importance for a messaging service and contains the logic that will be executed at run time.</span></span> <span data-ttu-id="83d39-117">パイプラインのコンテキスト、メッセージ、競合回避モジュールの文字列および現在の itinerary ステップにかかる更新されたメッセージを返します。</span><span class="sxs-lookup"><span data-stu-id="83d39-117">It takes in the pipeline context, the message, the resolver string, and the current itinerary step; and it returns the updated message.</span></span>  
  
 <span data-ttu-id="83d39-118">参照の実装、 **Execute**メソッドは、ESB の RoutingService.cs ファイルで検出されたことができます。次のコードに示すように Itinerary.Services プロジェクトです。</span><span class="sxs-lookup"><span data-stu-id="83d39-118">A reference implementation of the **Execute** method can be found in the RoutingService.cs file of the ESB.Itinerary.Services project, as shown in the following code.</span></span>  
  
```csharp  
public IBaseMessage ExecuteRoute(IPipelineContext context, IBaseMessage msg, string resolverString)  
        {  
            if (context == null)  
                throw new ArgumentNullException("context");  
            if (msg == null)  
                throw new ArgumentNullException("msg");  
            if (string.IsNullOrEmpty(resolverString))  
                throw new ArgumentException(Properties.Resources.ArgumentStringRequired, "resolverString");  
            try  
            {  
                ResolverInfo info = ResolverMgr.GetResolverInfo(ResolutionType.Endpoint, resolverString);  
                if (!info.Success)  
                    throw new RoutingException(Properties.Resources.ResolverStringInvalid, resolverString);  
  
                // Resolve configuration for routing.  
                Dictionary<string, string> resolverDictionary = ResolverMgr.Resolve(info, msg, context);  
  
                if (string.IsNullOrEmpty(resolverDictionary["Resolver.TransportLocation"]))  
                    throw new RoutingException(Properties.Resources.TransportLocationNotResolved, resolverString);  
  
                AdapterMgr.SetEndpoint(resolverDictionary, msg.Context);  
  
                return msg;  
            }  
            catch (System.Exception ex)  
            {  
                EventLogger.Write(MethodInfo.GetCurrentMethod(), ex);  
                throw;  
            }        
        }  
```  
  
 <span data-ttu-id="83d39-119">**メッセージングのカスタム itinerary サービスを実装するには**</span><span class="sxs-lookup"><span data-stu-id="83d39-119">**To implement a custom itinerary service for messaging**</span></span>  
  
1.  <span data-ttu-id="83d39-120">派生するクラスを含むアセンブリを作成**IMessagingService;**で、 **Execute**メソッド (存在する場合)、メッセージまたはメッセージのコンテキストを変更するために必要なすべてのロジックが含まれます。</span><span class="sxs-lookup"><span data-stu-id="83d39-120">Create an assembly with a class that derives from **IMessagingService;** in the **Execute** method, include all logic necessary to make modifications to the message or the message context (if any).</span></span>  
  
2.  <span data-ttu-id="83d39-121">内のエントリを追加、 **itineraryServices** Esb.config ファイルを追加して、サービスのセクションで、  **\<itineraryService >**と GUID を持つ要素、 **id**属性をサービスとしての名前、**名前**属性とクラスの完全修飾名、**型**属性、**メッセージング**として**スコープ**属性、および、許可されているステージ (たとえば、 **OnRampReceive**、 **OnRampSend**、 **OffRampSend**、 **OffRampReceive**、 **AllSend**、 **AllReceive**、または**すべて**) として、**ステージ**属性。</span><span class="sxs-lookup"><span data-stu-id="83d39-121">Add an entry in the **itineraryServices** section of the Esb.config file for your service by adding an **\<itineraryService>** element with a GUID as the **id** attribute, the name of the service as the **name** attribute, the fully qualified name of the class as the **type** attribute, **Messaging** as the **scope** attribute, and the allowed stage (for example, **OnRampReceive**, **OnRampSend**, **OffRampSend**, **OffRampReceive**, **AllSend**, **AllReceive**, or **All**) as the **stage** attribute.</span></span>  
  
3.  <span data-ttu-id="83d39-122">グローバル アセンブリ キャッシュに新しいアセンブリを登録します。</span><span class="sxs-lookup"><span data-stu-id="83d39-122">Register the new assembly in the global assembly cache.</span></span>