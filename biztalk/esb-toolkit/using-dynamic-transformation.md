---
title: 動的な変換を使用して |Microsoft Docs
ms.custom: ''
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: ''
ms.suite: ''
ms.tgt_pltfrm: ''
ms.topic: article
ms.assetid: e1e4aac7-242a-41b6-8df4-4881371f44d1
caps.latest.revision: 4
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: 81476c0bdcdbcf3d5647dd7bc83b37a70d6e7557
ms.sourcegitcommit: 381e83d43796a345488d54b3f7413e11d56ad7be
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 05/07/2019
ms.locfileid: "65396442"
---
# <a name="using-dynamic-transformation"></a><span data-ttu-id="d61f9-102">動的な変換を使用します。</span><span class="sxs-lookup"><span data-stu-id="d61f9-102">Using Dynamic Transformation</span></span>
## <a name="overview"></a><span data-ttu-id="d61f9-103">概要</span><span class="sxs-lookup"><span data-stu-id="d61f9-103">Overview</span></span>  
 <span data-ttu-id="d61f9-104">[!INCLUDE[esbToolkit](../includes/esbtoolkit-md.md)]動的変換用の 3 つのメカニズムをサポートしています。</span><span class="sxs-lookup"><span data-stu-id="d61f9-104">The [!INCLUDE[esbToolkit](../includes/esbtoolkit-md.md)] supports three mechanisms for dynamic transformation:</span></span>  
  
- <span data-ttu-id="d61f9-105">動的変換エージェントがオーケストレーションとして実装されています</span><span class="sxs-lookup"><span data-stu-id="d61f9-105">A dynamic transformation agent implemented as an orchestration</span></span>  
  
- <span data-ttu-id="d61f9-106">動的変換コア Web サービスに含まれている Web サービス</span><span class="sxs-lookup"><span data-stu-id="d61f9-106">A dynamic transformation Web service included with the core Web services</span></span>  
  
- <span data-ttu-id="d61f9-107">ESB パイプライン コンポーネントによって実行される変換</span><span class="sxs-lookup"><span data-stu-id="d61f9-107">Transformations executed by ESB pipeline components</span></span>  
  
  <span data-ttu-id="d61f9-108">このセクションでは、オーケストレーションとして実装されている変換エージェントについて説明します。</span><span class="sxs-lookup"><span data-stu-id="d61f9-108">This section focuses on the transformation agent implemented as an orchestration.</span></span> <span data-ttu-id="d61f9-109">Web サービスの変換については、次を参照してください。 [BizTalk ESB Toolkit Web サービスを使用して](../esb-toolkit/using-the-biztalk-esb-toolkit-web-services.md)します。</span><span class="sxs-lookup"><span data-stu-id="d61f9-109">For information about the transformation Web service, see [Using the BizTalk ESB Toolkit Web Services](../esb-toolkit/using-the-biztalk-esb-toolkit-web-services.md).</span></span> <span data-ttu-id="d61f9-110">ESB ディスパッチャー パイプラインのコンポーネントについては、次を参照してください。[パイプライン サポート コンポーネントを使用して](../esb-toolkit/using-the-pipeline-support-components.md)します。</span><span class="sxs-lookup"><span data-stu-id="d61f9-110">For information about the ESB Dispatcher pipeline components, see [Using the Pipeline Support Components](../esb-toolkit/using-the-pipeline-support-components.md).</span></span>  
  
## <a name="how-it-works"></a><span data-ttu-id="d61f9-111">しくみ</span><span class="sxs-lookup"><span data-stu-id="d61f9-111">How It Works</span></span>  
 <span data-ttu-id="d61f9-112">変換の配信エージェントはメッセージをサブスクライブするオーケストレーションは、場所、**名前**、現在の属性**ServiceInstance**旅行計画内の要素が**Microsoft.Practices.ESB.Services.Transform**します。</span><span class="sxs-lookup"><span data-stu-id="d61f9-112">The transformation delivery agent is an orchestration that subscribes to messages where the **Name** attribute of the current **ServiceInstance** element in the itinerary is **Microsoft.Practices.ESB.Services.Transform**.</span></span> <span data-ttu-id="d61f9-113">エージェントは、次の一連の操作を実行します。</span><span class="sxs-lookup"><span data-stu-id="d61f9-113">The agent performs the following sequence of operations:</span></span>  
  
1.  <span data-ttu-id="d61f9-114">型指定されていないメッセージ (System.Xml.XmlDocument) を受け取ります。</span><span class="sxs-lookup"><span data-stu-id="d61f9-114">It receives an un-typed message (System.Xml.XmlDocument).</span></span>  
  
2.  <span data-ttu-id="d61f9-115">マップの名前を日程で静的な値として使用できる場合、エージェントは競合回避モジュールのマネージャーを使用して、マップの名前を解決しようとします。</span><span class="sxs-lookup"><span data-stu-id="d61f9-115">If the name of the map is available as a static value in the itinerary, the agent attempts to resolve the name of the map using the resolver manager.</span></span>  
  
3.  <span data-ttu-id="d61f9-116">適切なマップは、受信した送信元メッセージに適用されます。</span><span class="sxs-lookup"><span data-stu-id="d61f9-116">It applies the appropriate map to the inbound source message.</span></span>  
  
4.  <span data-ttu-id="d61f9-117">BizTalk メッセージ ボックス データベースにマップの出力を発行します。</span><span class="sxs-lookup"><span data-stu-id="d61f9-117">It publishes the map output to the BizTalk Message Box database.</span></span>  
  
## <a name="how-to-configure-dynamic-transformation"></a><span data-ttu-id="d61f9-118">動的な変換を構成する方法</span><span class="sxs-lookup"><span data-stu-id="d61f9-118">How to Configure Dynamic Transformation</span></span>  
 <span data-ttu-id="d61f9-119">旅行プラン デザイナーを使用して動的な変換を構成する方法の詳細については、次を参照してください。[旅行プランを使用してスケジュールの作成のデザイナー](../esb-toolkit/creating-itineraries-using-itinerary-designer.md)します。</span><span class="sxs-lookup"><span data-stu-id="d61f9-119">For more information about how to configure Dynamic Transformation using Itinerary Designer, see [Creating Itineraries Using Itinerary Designer](../esb-toolkit/creating-itineraries-using-itinerary-designer.md).</span></span>  
  
## <a name="dynamic-transformation-errors"></a><span data-ttu-id="d61f9-120">動的変換エラー</span><span class="sxs-lookup"><span data-stu-id="d61f9-120">Dynamic Transformation Errors</span></span>  
 <span data-ttu-id="d61f9-121">動的変換メカニズムは作成し、次の場合に、ESB エラー メッセージを発行します。</span><span class="sxs-lookup"><span data-stu-id="d61f9-121">The dynamic transformation mechanism will create and publish an ESB fault message in the following cases:</span></span>  
  
- <span data-ttu-id="d61f9-122">競合回避モジュール コンポーネントは、適用に割り当てられている特定できません。</span><span class="sxs-lookup"><span data-stu-id="d61f9-122">The resolver component cannot determine which map to apply.</span></span>  
  
- <span data-ttu-id="d61f9-123">指定したマップは利用できません (たとえば、指定した、正しくないマップ型または BizTalk Server 2009 でまだ展開されているマップ) します。</span><span class="sxs-lookup"><span data-stu-id="d61f9-123">The specified map is not available (for example, you specified an incorrect map type or a map not yet deployed in BizTalk Server 2009).</span></span>  
  
- <span data-ttu-id="d61f9-124">マッピング中にエラーが発生した (たとえば、ソース ドキュメントは、正しいソースの種類または外部アセンブリ内のユーザー定義関数が BizTalk に配置されているマップの参照)。</span><span class="sxs-lookup"><span data-stu-id="d61f9-124">A failure occurs during mapping (for example, the source document is not of the correct source type or the map references a custom function in an external assembly is not deployed to BizTalk).</span></span>  
  
- <span data-ttu-id="d61f9-125">マップの種類のジャストイン タイム (JIT) の解決中に例外が発生します。</span><span class="sxs-lookup"><span data-stu-id="d61f9-125">An exception occurs during just-in-time (JIT) resolution of the map type.</span></span>  
  
- <span data-ttu-id="d61f9-126">出力メッセージのサブスクライバーが存在しません。</span><span class="sxs-lookup"><span data-stu-id="d61f9-126">No subscriber exists for the output message.</span></span>  
  
- <span data-ttu-id="d61f9-127">すべてのシステム例外が発生します。</span><span class="sxs-lookup"><span data-stu-id="d61f9-127">Any system exception occurs.</span></span>  
  
  <span data-ttu-id="d61f9-128">例外メッセージを設定して、例外に対応するためのハンドラーを作成するために使用するコンテキスト情報を提供する、開発者の役目です。</span><span class="sxs-lookup"><span data-stu-id="d61f9-128">It is the developer's responsibility to provide the context information used to populate the exception messages and create handlers to react to the exception.</span></span> <span data-ttu-id="d61f9-129">データの一部が自動的に使用して、ターゲット ハンドラーが指定されたか使用できない場合は、ジェネリック ハンドラーを例外メッセージを選択します。</span><span class="sxs-lookup"><span data-stu-id="d61f9-129">Some of the data is automatically available, and a generic handler will pick up the exception message if no target handler is specified or available.</span></span> <span data-ttu-id="d61f9-130">動的な変換の例外の処理の詳細については、次を参照してください。 [ESB 例外管理を使用して](../esb-toolkit/using-esb-exception-management.md)します。</span><span class="sxs-lookup"><span data-stu-id="d61f9-130">For more information about handling dynamic transformation exceptions, see [Using ESB Exception Management](../esb-toolkit/using-esb-exception-management.md).</span></span>