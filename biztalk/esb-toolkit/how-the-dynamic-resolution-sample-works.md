---
title: 動的解決サンプルのしくみ |Microsoft Docs
ms.custom: ''
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: ''
ms.suite: ''
ms.tgt_pltfrm: ''
ms.topic: article
ms.assetid: 7789316d-f2c4-4018-a8e8-dd9359f1664f
caps.latest.revision: 2
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: 207299cefb5632072fdced38f3c25ad495a6d775
ms.sourcegitcommit: 381e83d43796a345488d54b3f7413e11d56ad7be
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 05/07/2019
ms.locfileid: "65400800"
---
# <a name="how-the-dynamic-resolution-sample-works"></a><span data-ttu-id="ca7ea-102">動的解決サンプルのしくみ</span><span class="sxs-lookup"><span data-stu-id="ca7ea-102">How the Dynamic Resolution Sample Works</span></span>
<span data-ttu-id="ca7ea-103">動的解決サンプルでは、前のセクションで説明されているすべてのメッセージの例の ESB ディスパッチャー逆アセンブラー パイプライン コンポーネントを使用します。</span><span class="sxs-lookup"><span data-stu-id="ca7ea-103">The Dynamic Resolution sample uses the ESB Dispatcher Disassembler pipeline component for all the messaging examples described in the previous section.</span></span>  

 <span data-ttu-id="ca7ea-104">一方向メッセージング シナリオでは、例は、STATIC、BRE、または XPATH 競合回避モジュールを使用してエンドポイントを解決し、ファイル、FTP、または MQSeries ファイルからのプロトコルを仲介します。</span><span class="sxs-lookup"><span data-stu-id="ca7ea-104">For one-way messaging scenarios, the example resolves the endpoint using the STATIC, BRE, or XPATH Resolver and brokers the protocol from FILE to FILE, FTP, or MQSeries.</span></span>  

 <span data-ttu-id="ca7ea-105">双方向メッセージング シナリオでは、例は、STATIC、BRE、UDDI、または XPATH 競合回避モジュールを使用してエンドポイントを解決しを SOAP または Wcf-basichttp SOAP からプロトコルを仲介します。</span><span class="sxs-lookup"><span data-stu-id="ca7ea-105">For two-way messaging scenarios, the example resolves the endpoint using the STATIC, BRE, UDDI, or XPATH Resolver and brokers the protocol from SOAP to either SOAP or WCF-BasicHttp.</span></span> <span data-ttu-id="ca7ea-106">さらに、例は解決して、解決の結果を確認するメッセージ コンテキスト プロパティとメッセージ本文に含まれているファクトを使用して BRE リゾルバーを使用して、Microsoft BizTalk マップを実行します。</span><span class="sxs-lookup"><span data-stu-id="ca7ea-106">In addition, the examples resolve and execute Microsoft BizTalk maps using the BRE Resolver, which uses facts contained in the message context properties and the message body to determine the resolution result.</span></span>  

 <span data-ttu-id="ca7ea-107">解決プロセスの結果は、双方向のすべての例が、ESB を自分のメッセージを送信します。CanadianServices Web サービスがある http://localhost/ESB.CanadianServices/SubmitPOService.asmx します。</span><span class="sxs-lookup"><span data-stu-id="ca7ea-107">The result of the resolution process is that all the two-way examples submit their message to the ESB.CanadianServices Web service located at http://localhost/ESB.CanadianServices/SubmitPOService.asmx.</span></span> <span data-ttu-id="ca7ea-108">さらに、解決の結果に応じて、例を実行しますか、 **submitOrder**または**submitPurchase**アクション。</span><span class="sxs-lookup"><span data-stu-id="ca7ea-108">In addition, depending on the resolution result, the example executes either the **submitOrder** or the **submitPurchase** action.</span></span> <span data-ttu-id="ca7ea-109">さらに、ESB ディスパッチャー逆アセンブラー パイプライン コンポーネントには、BizTalk マップを指定されているか、解決操作に応じて動的に実行します。</span><span class="sxs-lookup"><span data-stu-id="ca7ea-109">Additionally, the ESB Dispatcher Disassembler pipeline component dynamically executes a BizTalk map, depending on the specified or the resolved action.</span></span>  

 <span data-ttu-id="ca7ea-110">図 1 は、構成されている、DynamicResolutionReqResp_SOAP のパイプラインは受信場所を示します。</span><span class="sxs-lookup"><span data-stu-id="ca7ea-110">Figure 1 shows the configured pipelines for the DynamicResolutionReqResp_SOAP receive location.</span></span>  

 <span data-ttu-id="ca7ea-111">![動的解決のパイプライン](../esb-toolkit/media/ch6-dynamicresolutionpipelines.gif "Ch6 DynamicResolutionPipelines")</span><span class="sxs-lookup"><span data-stu-id="ca7ea-111">![Dynamic Resolution Pipelines](../esb-toolkit/media/ch6-dynamicresolutionpipelines.gif "Ch6-DynamicResolutionPipelines")</span></span>  

 <span data-ttu-id="ca7ea-112">**図 1**</span><span class="sxs-lookup"><span data-stu-id="ca7ea-112">**Figure 1**</span></span>  

 <span data-ttu-id="ca7ea-113">**動的解決サンプル アプリケーションの場所を受信する、DynamicResolutionReqResp_SOAP の構成済みのパイプライン**</span><span class="sxs-lookup"><span data-stu-id="ca7ea-113">**The configured pipelines of the DynamicResolutionReqResp_SOAP receive location of the Dynamic Resolution sample application**</span></span>  

 <span data-ttu-id="ca7ea-114">図 2 は、ESB ディスパッチャー逆アセンブラーを使用する ESBReceiveXML コンポーネントのインスタンスごとにプロパティを示します。</span><span class="sxs-lookup"><span data-stu-id="ca7ea-114">Figure 2 shows the per-instance properties of the ESBReceiveXML component that uses the ESB Dispatcher Disassembler.</span></span>  

 <span data-ttu-id="ca7ea-115">![動的解決の受信 XML](../esb-toolkit/media/ch6-dynamicresolutionreceivexml.gif "Ch6 DynamicResolutionReceiveXML")</span><span class="sxs-lookup"><span data-stu-id="ca7ea-115">![Dynamic Resolution Receive XML](../esb-toolkit/media/ch6-dynamicresolutionreceivexml.gif "Ch6-DynamicResolutionReceiveXML")</span></span>  

 <span data-ttu-id="ca7ea-116">**図 2**</span><span class="sxs-lookup"><span data-stu-id="ca7ea-116">**Figure 2**</span></span>  

 <span data-ttu-id="ca7ea-117">**動的解決サンプル アプリケーションの ESBReceiveXML パイプラインでコンポーネントのインスタンスごとのプロパティ**</span><span class="sxs-lookup"><span data-stu-id="ca7ea-117">**The per-instance properties for the components in the ESBReceiveXML pipeline of the Dynamic Resolution sample application**</span></span>  

 <span data-ttu-id="ca7ea-118">図 2 に、次のプロパティが表示されます。</span><span class="sxs-lookup"><span data-stu-id="ca7ea-118">The following properties are shown in Figure 2:</span></span>  

- <span data-ttu-id="ca7ea-119">**有効になっている**します。</span><span class="sxs-lookup"><span data-stu-id="ca7ea-119">**Enabled**.</span></span> <span data-ttu-id="ca7ea-120">このプロパティは、パイプラインがアクティブかどうかを決定します。</span><span class="sxs-lookup"><span data-stu-id="ca7ea-120">This property determines whether the pipeline is active.</span></span> <span data-ttu-id="ca7ea-121">設定されている場合**False**メッセージが処理を行わなくても通過します。</span><span class="sxs-lookup"><span data-stu-id="ca7ea-121">If this is set to **False**, messages pass through without processing.</span></span>  

- <span data-ttu-id="ca7ea-122">**エンドポイント**します。</span><span class="sxs-lookup"><span data-stu-id="ca7ea-122">**Endpoint**.</span></span> <span data-ttu-id="ca7ea-123">このプロパティは、接続文字列を読み込むには、どの競合回避モジュールを判断するために使用して、エンドポイント構成を指定します。</span><span class="sxs-lookup"><span data-stu-id="ca7ea-123">This property is the connection string used to determine which resolver to load, and it specifies the endpoint configuration.</span></span>  

- <span data-ttu-id="ca7ea-124">**MapName**します。</span><span class="sxs-lookup"><span data-stu-id="ca7ea-124">**MapName**.</span></span> <span data-ttu-id="ca7ea-125">このプロパティは、どの競合回避モジュールを読み込むとを実行するには、どの BizTalk マップを決定するために使用する接続文字列です。</span><span class="sxs-lookup"><span data-stu-id="ca7ea-125">This property is the connection string used to determine which resolver to load and which BizTalk map to execute.</span></span> <span data-ttu-id="ca7ea-126">競合回避モジュールの接続文字列ではなく、マップの完全修飾名を指定できます。</span><span class="sxs-lookup"><span data-stu-id="ca7ea-126">It can be the fully qualified name of a map instead of a resolver connection string.</span></span>  

- <span data-ttu-id="ca7ea-127">**検証**です。</span><span class="sxs-lookup"><span data-stu-id="ca7ea-127">**Validate**.</span></span> <span data-ttu-id="ca7ea-128">設定すると**True** (既定の設定、)、ESB ディスパッチャー逆アセンブラー コンポーネントに指示するマップで定義されている送信元スキーマに対してソース メッセージの検証に ESB 変換サービスは解決され、実行します。</span><span class="sxs-lookup"><span data-stu-id="ca7ea-128">When set to **True** (the default setting), the ESB Dispatcher Disassembler component instructs the ESB Transformation service to validate the source message against the source schema defined in the map that is will resolve and execute.</span></span>  

  <span data-ttu-id="ca7ea-129">図 3 は、ESB ディスパッチャーを使用する ESBSendPassthrough コンポーネントのインスタンスごとにプロパティを示します。</span><span class="sxs-lookup"><span data-stu-id="ca7ea-129">Figure 3 shows the per-instance properties of the ESBSendPassthrough component that uses the ESB Dispatcher.</span></span>  

  <span data-ttu-id="ca7ea-130">![動的解決の送信パススルー](../esb-toolkit/media/ch6-dynamicresolutionsendpassthrough.gif "Ch6 DynamicResolutionSendPassthrough")</span><span class="sxs-lookup"><span data-stu-id="ca7ea-130">![Dynamic Resolution Send Passthrough](../esb-toolkit/media/ch6-dynamicresolutionsendpassthrough.gif "Ch6-DynamicResolutionSendPassthrough")</span></span>  

  <span data-ttu-id="ca7ea-131">**図 3**</span><span class="sxs-lookup"><span data-stu-id="ca7ea-131">**Figure 3**</span></span>  

  <span data-ttu-id="ca7ea-132">**動的解決サンプル アプリケーションの ESBSendPassthrough パイプラインでコンポーネントのインスタンスごとのプロパティ**</span><span class="sxs-lookup"><span data-stu-id="ca7ea-132">**The per-instance properties for the components in the ESBSendPassthrough pipeline of the Dynamic Resolution sample application**</span></span>  

  <span data-ttu-id="ca7ea-133">図 3 に、次のプロパティが表示されます。</span><span class="sxs-lookup"><span data-stu-id="ca7ea-133">The following properties are shown in Figure 3:</span></span>  

- <span data-ttu-id="ca7ea-134">**有効になっている**します。</span><span class="sxs-lookup"><span data-stu-id="ca7ea-134">**Enabled**.</span></span> <span data-ttu-id="ca7ea-135">このプロパティは、パイプラインがアクティブかどうかを決定します。</span><span class="sxs-lookup"><span data-stu-id="ca7ea-135">This property determines whether the pipeline is active.</span></span> <span data-ttu-id="ca7ea-136">設定されている場合**False**メッセージが処理を行わなくても通過します。</span><span class="sxs-lookup"><span data-stu-id="ca7ea-136">If this is set to **False**, messages pass through without processing.</span></span>  

- <span data-ttu-id="ca7ea-137">**エンドポイント**します。</span><span class="sxs-lookup"><span data-stu-id="ca7ea-137">**Endpoint**.</span></span> <span data-ttu-id="ca7ea-138">このプロパティは、どの競合回避モジュールをロードし、エンドポイント構成を決定するために使用する接続文字列です。</span><span class="sxs-lookup"><span data-stu-id="ca7ea-138">This property is the connection string used to determine which resolver to load and the end-point configuration.</span></span>  

- <span data-ttu-id="ca7ea-139">**MapName**します。</span><span class="sxs-lookup"><span data-stu-id="ca7ea-139">**MapName**.</span></span> <span data-ttu-id="ca7ea-140">このプロパティは、どの競合回避モジュールを読み込むとを実行するには、どの BizTalk マップを決定するために使用する接続文字列です。</span><span class="sxs-lookup"><span data-stu-id="ca7ea-140">This property is the connection string used to determine which resolver to load and which BizTalk map to execute.</span></span> <span data-ttu-id="ca7ea-141">マップの完全修飾名は、競合回避モジュールの接続文字列の代わりに使用できます。</span><span class="sxs-lookup"><span data-stu-id="ca7ea-141">A fully qualified name of a map can be used in place of a resolver's connection string.</span></span>  

- <span data-ttu-id="ca7ea-142">**検証**です。</span><span class="sxs-lookup"><span data-stu-id="ca7ea-142">**Validate**.</span></span> <span data-ttu-id="ca7ea-143">設定すると**True** (既定の設定、)、ESB ディスパッチャー逆アセンブラー コンポーネントに指示するマップで定義されている送信元スキーマに対してソース メッセージの検証に ESB 変換サービスは解決され、実行します。</span><span class="sxs-lookup"><span data-stu-id="ca7ea-143">When set to **True** (the default setting), the ESB Dispatcher Disassembler component instructs the ESB Transformation service to validate the source message against the source schema defined in the map that is will resolve and execute.</span></span>
