---
title: "動的な変換を使用して |Microsoft ドキュメント"
ms.custom: 
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: 
ms.suite: 
ms.tgt_pltfrm: 
ms.topic: article
ms.assetid: e1e4aac7-242a-41b6-8df4-4881371f44d1
caps.latest.revision: "4"
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: 1d7f6bc57d009e558188950d9bcb0387f808f835
ms.sourcegitcommit: cb908c540d8f1a692d01dc8f313e16cb4b4e696d
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 09/20/2017
---
# <a name="using-dynamic-transformation"></a><span data-ttu-id="e3f6f-102">動的な変換を使用します。</span><span class="sxs-lookup"><span data-stu-id="e3f6f-102">Using Dynamic Transformation</span></span>
## <a name="overview"></a><span data-ttu-id="e3f6f-103">概要</span><span class="sxs-lookup"><span data-stu-id="e3f6f-103">Overview</span></span>  
 <span data-ttu-id="e3f6f-104">[!INCLUDE[esbToolkit](../includes/esbtoolkit-md.md)]動的変換の 3 つのメカニズムをサポートしています。</span><span class="sxs-lookup"><span data-stu-id="e3f6f-104">The [!INCLUDE[esbToolkit](../includes/esbtoolkit-md.md)] supports three mechanisms for dynamic transformation:</span></span>  
  
-   <span data-ttu-id="e3f6f-105">オーケストレーションとして実装されている動的変換エージェント</span><span class="sxs-lookup"><span data-stu-id="e3f6f-105">A dynamic transformation agent implemented as an orchestration</span></span>  
  
-   <span data-ttu-id="e3f6f-106">コア Web サービスに含まれる Web サービスの動的変換</span><span class="sxs-lookup"><span data-stu-id="e3f6f-106">A dynamic transformation Web service included with the core Web services</span></span>  
  
-   <span data-ttu-id="e3f6f-107">ESB パイプライン コンポーネントによって実行される変換</span><span class="sxs-lookup"><span data-stu-id="e3f6f-107">Transformations executed by ESB pipeline components</span></span>  
  
 <span data-ttu-id="e3f6f-108">このセクションでは、オーケストレーションとして実装されている変換エージェントについて説明します。</span><span class="sxs-lookup"><span data-stu-id="e3f6f-108">This section focuses on the transformation agent implemented as an orchestration.</span></span> <span data-ttu-id="e3f6f-109">Web サービスの変換については、次を参照してください。 [BizTalk ESB Toolkit の Web サービスを使用して](../esb-toolkit/using-the-biztalk-esb-toolkit-web-services.md)です。</span><span class="sxs-lookup"><span data-stu-id="e3f6f-109">For information about the transformation Web service, see [Using the BizTalk ESB Toolkit Web Services](../esb-toolkit/using-the-biztalk-esb-toolkit-web-services.md).</span></span> <span data-ttu-id="e3f6f-110">ESB ディスパッチャー パイプライン コンポーネントについては、次を参照してください。[サポートのパイプライン コンポーネントを使用して](../esb-toolkit/using-the-pipeline-support-components.md)です。</span><span class="sxs-lookup"><span data-stu-id="e3f6f-110">For information about the ESB Dispatcher pipeline components, see [Using the Pipeline Support Components](../esb-toolkit/using-the-pipeline-support-components.md).</span></span>  
  
## <a name="how-it-works"></a><span data-ttu-id="e3f6f-111">しくみ</span><span class="sxs-lookup"><span data-stu-id="e3f6f-111">How It Works</span></span>  
 <span data-ttu-id="e3f6f-112">変換配信エージェントはメッセージをサブスクライブするオーケストレーションを**名前**、現在の属性**ServiceInstance**旅行計画内の要素は**Microsoft.Practices.ESB.Services.Transform**です。</span><span class="sxs-lookup"><span data-stu-id="e3f6f-112">The transformation delivery agent is an orchestration that subscribes to messages where the **Name** attribute of the current **ServiceInstance** element in the itinerary is **Microsoft.Practices.ESB.Services.Transform**.</span></span> <span data-ttu-id="e3f6f-113">エージェントでは、次の操作手順を実行します。</span><span class="sxs-lookup"><span data-stu-id="e3f6f-113">The agent performs the following sequence of operations:</span></span>  
  
1.  <span data-ttu-id="e3f6f-114">型指定されていないメッセージ (system.xml.xmldocument など) を受け取ります。</span><span class="sxs-lookup"><span data-stu-id="e3f6f-114">It receives an un-typed message (System.Xml.XmlDocument).</span></span>  
  
2.  <span data-ttu-id="e3f6f-115">マップの名前は、旅行計画で静的な値として使用できますが、エージェントは競合回避モジュールのマネージャーを使用して、マップの名前を解決しようとします。</span><span class="sxs-lookup"><span data-stu-id="e3f6f-115">If the name of the map is available as a static value in the itinerary, the agent attempts to resolve the name of the map using the resolver manager.</span></span>  
  
3.  <span data-ttu-id="e3f6f-116">入力方向の送信元のメッセージを適切なマップを適用します。</span><span class="sxs-lookup"><span data-stu-id="e3f6f-116">It applies the appropriate map to the inbound source message.</span></span>  
  
4.  <span data-ttu-id="e3f6f-117">マップの出力に、BizTalk メッセージ ボックス データベースに発行します。</span><span class="sxs-lookup"><span data-stu-id="e3f6f-117">It publishes the map output to the BizTalk Message Box database.</span></span>  
  
## <a name="how-to-configure-dynamic-transformation"></a><span data-ttu-id="e3f6f-118">動的な変換を構成する方法</span><span class="sxs-lookup"><span data-stu-id="e3f6f-118">How to Configure Dynamic Transformation</span></span>  
 <span data-ttu-id="e3f6f-119">行程デザイナーを使用して動的な変換を構成する方法の詳細については、次を参照してください。[旅程を使用して日程作成のデザイナー](../esb-toolkit/creating-itineraries-using-itinerary-designer.md)です。</span><span class="sxs-lookup"><span data-stu-id="e3f6f-119">For more information about how to configure Dynamic Transformation using Itinerary Designer, see [Creating Itineraries Using Itinerary Designer](../esb-toolkit/creating-itineraries-using-itinerary-designer.md).</span></span>  
  
## <a name="dynamic-transformation-errors"></a><span data-ttu-id="e3f6f-120">動的な変換エラー</span><span class="sxs-lookup"><span data-stu-id="e3f6f-120">Dynamic Transformation Errors</span></span>  
 <span data-ttu-id="e3f6f-121">動的な変換のメカニズムが作成され、次の場合、ESB フォールト メッセージを発行します。</span><span class="sxs-lookup"><span data-stu-id="e3f6f-121">The dynamic transformation mechanism will create and publish an ESB fault message in the following cases:</span></span>  
  
-   <span data-ttu-id="e3f6f-122">競合回避モジュール コンポーネントは、適用するマップを判断できません。</span><span class="sxs-lookup"><span data-stu-id="e3f6f-122">The resolver component cannot determine which map to apply.</span></span>  
  
-   <span data-ttu-id="e3f6f-123">指定したマップは使用できません (たとえば、指定した、正しくないマップ型、または BizTalk Server 2009 ではまだ展開されているマップ) します。</span><span class="sxs-lookup"><span data-stu-id="e3f6f-123">The specified map is not available (for example, you specified an incorrect map type or a map not yet deployed in BizTalk Server 2009).</span></span>  
  
-   <span data-ttu-id="e3f6f-124">マッピング中にエラーが発生した (たとえば、ソース ドキュメントは、正しいソースの種類または外部アセンブリ内のユーザー定義関数は、BizTalk に展開されていないマップの参照の)。</span><span class="sxs-lookup"><span data-stu-id="e3f6f-124">A failure occurs during mapping (for example, the source document is not of the correct source type or the map references a custom function in an external assembly is not deployed to BizTalk).</span></span>  
  
-   <span data-ttu-id="e3f6f-125">例外は、マップの種類の・ イン タイム (JIT) の解決時に発生します。</span><span class="sxs-lookup"><span data-stu-id="e3f6f-125">An exception occurs during just-in-time (JIT) resolution of the map type.</span></span>  
  
-   <span data-ttu-id="e3f6f-126">出力メッセージのサブスクライバーが存在しません。</span><span class="sxs-lookup"><span data-stu-id="e3f6f-126">No subscriber exists for the output message.</span></span>  
  
-   <span data-ttu-id="e3f6f-127">すべてのシステム例外が発生します。</span><span class="sxs-lookup"><span data-stu-id="e3f6f-127">Any system exception occurs.</span></span>  
  
 <span data-ttu-id="e3f6f-128">例外メッセージを作成し、例外に反応するためのハンドラーを作成するために使用するコンテキスト情報を提供する、開発者の責任です。</span><span class="sxs-lookup"><span data-stu-id="e3f6f-128">It is the developer's responsibility to provide the context information used to populate the exception messages and create handlers to react to the exception.</span></span> <span data-ttu-id="e3f6f-129">データの一部が自動的に使用して、ジェネリック ハンドラーが指定されているか使用可能なターゲット ハンドラーがない場合、例外メッセージを取得します。</span><span class="sxs-lookup"><span data-stu-id="e3f6f-129">Some of the data is automatically available, and a generic handler will pick up the exception message if no target handler is specified or available.</span></span> <span data-ttu-id="e3f6f-130">動的な変換の例外の処理の詳細については、次を参照してください。 [ESB 例外管理を使用して](../esb-toolkit/using-esb-exception-management.md)です。</span><span class="sxs-lookup"><span data-stu-id="e3f6f-130">For more information about handling dynamic transformation exceptions, see [Using ESB Exception Management](../esb-toolkit/using-esb-exception-management.md).</span></span>