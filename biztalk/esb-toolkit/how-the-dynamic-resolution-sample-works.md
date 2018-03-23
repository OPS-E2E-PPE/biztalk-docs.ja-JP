---
title: 動的解決のサンプルの動作 |Microsoft ドキュメント
ms.custom: ''
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: ''
ms.suite: ''
ms.tgt_pltfrm: ''
ms.topic: article
ms.assetid: 7789316d-f2c4-4018-a8e8-dd9359f1664f
caps.latest.revision: ''
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: fe7d7b473482c432c8e3ae9ca48cab414a9e9573
ms.sourcegitcommit: 8418b1a8f38b7f56979cd6e203f0b591e2f40fe1
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 03/23/2018
---
# <a name="how-the-dynamic-resolution-sample-works"></a><span data-ttu-id="86aa5-102">動的解決のサンプルのしくみ</span><span class="sxs-lookup"><span data-stu-id="86aa5-102">How the Dynamic Resolution Sample Works</span></span>
<span data-ttu-id="86aa5-103">動的解決サンプルでは、前のセクションで説明されているすべてのメッセージ例については、ESB ディスパッチャー逆アセンブラー パイプライン コンポーネントを使用します。</span><span class="sxs-lookup"><span data-stu-id="86aa5-103">The Dynamic Resolution sample uses the ESB Dispatcher Disassembler pipeline component for all the messaging examples described in the previous section.</span></span>  
  
 <span data-ttu-id="86aa5-104">一方向のメッセージング シナリオでは、この例は、STATIC、BRE、または XPATH 競合回避モジュールを使用してエンドポイントを解決し、ファイル、FTP、または MQSeries には、ファイルからのプロトコルを仲介する機能します。</span><span class="sxs-lookup"><span data-stu-id="86aa5-104">For one-way messaging scenarios, the example resolves the endpoint using the STATIC, BRE, or XPATH Resolver and brokers the protocol from FILE to FILE, FTP, or MQSeries.</span></span>  
  
 <span data-ttu-id="86aa5-105">双方向のメッセージング シナリオでは、この例は、STATIC、BRE、UDDI、または XPATH 競合回避モジュールを使用してエンドポイントを解決し、SOAP または Wcf-basichttp SOAP からプロトコルを仲介する機能します。</span><span class="sxs-lookup"><span data-stu-id="86aa5-105">For two-way messaging scenarios, the example resolves the endpoint using the STATIC, BRE, UDDI, or XPATH Resolver and brokers the protocol from SOAP to either SOAP or WCF-BasicHttp.</span></span> <span data-ttu-id="86aa5-106">さらに、例は解決し、メッセージ コンテキスト プロパティと、メッセージ本文に含まれるファクトを使用して、解決の結果を決定する BRE リゾルバーを使用して、Microsoft BizTalk マップを実行します。</span><span class="sxs-lookup"><span data-stu-id="86aa5-106">In addition, the examples resolve and execute Microsoft BizTalk maps using the BRE Resolver, which uses facts contained in the message context properties and the message body to determine the resolution result.</span></span>  
  
 <span data-ttu-id="86aa5-107">解決プロセスの結果は、双方向のすべての例が、ESB にそのメッセージを送信します。Http://localhost/ESB.CanadianServices/SubmitPOService.asmx にある CanadianServices Web サービスです。</span><span class="sxs-lookup"><span data-stu-id="86aa5-107">The result of the resolution process is that all the two-way examples submit their message to the ESB.CanadianServices Web service located at http://localhost/ESB.CanadianServices/SubmitPOService.asmx.</span></span> <span data-ttu-id="86aa5-108">さらに、解決の結果に応じて、例を実行するか、 **submitOrder**または**submitPurchase**アクション。</span><span class="sxs-lookup"><span data-stu-id="86aa5-108">In addition, depending on the resolution result, the example executes either the **submitOrder** or the **submitPurchase** action.</span></span> <span data-ttu-id="86aa5-109">さらに、ESB ディスパッチャーの逆アセンブラー パイプライン コンポーネントでは、動的に指定されたまたは解決済みのアクションによって、BizTalk マップを実行します。</span><span class="sxs-lookup"><span data-stu-id="86aa5-109">Additionally, the ESB Dispatcher Disassembler pipeline component dynamically executes a BizTalk map, depending on the specified or the resolved action.</span></span>  
  
 <span data-ttu-id="86aa5-110">図 1 は、構成されたパイプライン、DynamicResolutionReqResp_SOAP の受信場所を示します。</span><span class="sxs-lookup"><span data-stu-id="86aa5-110">Figure 1 shows the configured pipelines for the DynamicResolutionReqResp_SOAP receive location.</span></span>  
  
 <span data-ttu-id="86aa5-111">![動的解決のパイプライン](../esb-toolkit/media/ch6-dynamicresolutionpipelines.gif "Ch6 DynamicResolutionPipelines")</span><span class="sxs-lookup"><span data-stu-id="86aa5-111">![Dynamic Resolution Pipelines](../esb-toolkit/media/ch6-dynamicresolutionpipelines.gif "Ch6-DynamicResolutionPipelines")</span></span>  
  
 <span data-ttu-id="86aa5-112">**図 1**</span><span class="sxs-lookup"><span data-stu-id="86aa5-112">**Figure 1**</span></span>  
  
 <span data-ttu-id="86aa5-113">**構成されたパイプライン、DynamicResolutionReqResp_SOAP の受信動的解決のサンプル アプリケーションの場所**</span><span class="sxs-lookup"><span data-stu-id="86aa5-113">**The configured pipelines of the DynamicResolutionReqResp_SOAP receive location of the Dynamic Resolution sample application**</span></span>  
  
 <span data-ttu-id="86aa5-114">図 2 は、ESB ディスパッチャー逆アセンブラーを使用する ESBReceiveXML コンポーネントのインスタンスごとにプロパティを示します。</span><span class="sxs-lookup"><span data-stu-id="86aa5-114">Figure 2 shows the per-instance properties of the ESBReceiveXML component that uses the ESB Dispatcher Disassembler.</span></span>  
  
 <span data-ttu-id="86aa5-115">![動的解決の受信 XML](../esb-toolkit/media/ch6-dynamicresolutionreceivexml.gif "Ch6 DynamicResolutionReceiveXML")</span><span class="sxs-lookup"><span data-stu-id="86aa5-115">![Dynamic Resolution Receive XML](../esb-toolkit/media/ch6-dynamicresolutionreceivexml.gif "Ch6-DynamicResolutionReceiveXML")</span></span>  
  
 <span data-ttu-id="86aa5-116">**図 2**</span><span class="sxs-lookup"><span data-stu-id="86aa5-116">**Figure 2**</span></span>  
  
 <span data-ttu-id="86aa5-117">**動的解決のサンプル アプリケーションの ESBReceiveXML パイプライン内のコンポーネントのインスタンスごとにプロパティ**</span><span class="sxs-lookup"><span data-stu-id="86aa5-117">**The per-instance properties for the components in the ESBReceiveXML pipeline of the Dynamic Resolution sample application**</span></span>  
  
 <span data-ttu-id="86aa5-118">図 2 には、次のプロパティを示します。</span><span class="sxs-lookup"><span data-stu-id="86aa5-118">The following properties are shown in Figure 2:</span></span>  
  
-   <span data-ttu-id="86aa5-119">**有効になっている**です。</span><span class="sxs-lookup"><span data-stu-id="86aa5-119">**Enabled**.</span></span> <span data-ttu-id="86aa5-120">このプロパティは、パイプラインがアクティブかどうかを判断します。</span><span class="sxs-lookup"><span data-stu-id="86aa5-120">This property determines whether the pipeline is active.</span></span> <span data-ttu-id="86aa5-121">設定されている場合**False**、処理されずにメッセージが通過します。</span><span class="sxs-lookup"><span data-stu-id="86aa5-121">If this is set to **False**, messages pass through without processing.</span></span>  
  
-   <span data-ttu-id="86aa5-122">**エンドポイント**です。</span><span class="sxs-lookup"><span data-stu-id="86aa5-122">**Endpoint**.</span></span> <span data-ttu-id="86aa5-123">このプロパティは、接続文字列を読み込むには、どの競合回避モジュールを決定するために使用し、エンドポイントの構成を指定します。</span><span class="sxs-lookup"><span data-stu-id="86aa5-123">This property is the connection string used to determine which resolver to load, and it specifies the endpoint configuration.</span></span>  
  
-   <span data-ttu-id="86aa5-124">**MapName**です。</span><span class="sxs-lookup"><span data-stu-id="86aa5-124">**MapName**.</span></span> <span data-ttu-id="86aa5-125">このプロパティは、どの競合回避モジュールを読み込むと、BizTalk マップを実行するために使用する接続文字列です。</span><span class="sxs-lookup"><span data-stu-id="86aa5-125">This property is the connection string used to determine which resolver to load and which BizTalk map to execute.</span></span> <span data-ttu-id="86aa5-126">競合回避モジュールの接続文字列の代わりに、マップの完全修飾名があります。</span><span class="sxs-lookup"><span data-stu-id="86aa5-126">It can be the fully qualified name of a map instead of a resolver connection string.</span></span>  
  
-   <span data-ttu-id="86aa5-127">**検証**です。</span><span class="sxs-lookup"><span data-stu-id="86aa5-127">**Validate**.</span></span> <span data-ttu-id="86aa5-128">設定すると**True** (既定の設定) を ESB ディスパッチャー逆アセンブラー コンポーネントに指示、ESB 変換サービスは、マップで定義されている送信元スキーマに対してソース メッセージの検証には解決し、実行します。</span><span class="sxs-lookup"><span data-stu-id="86aa5-128">When set to **True** (the default setting), the ESB Dispatcher Disassembler component instructs the ESB Transformation service to validate the source message against the source schema defined in the map that is will resolve and execute.</span></span>  
  
 <span data-ttu-id="86aa5-129">図 3 は、ESB ディスパッチャーを使用する ESBSendPassthrough コンポーネントのインスタンスごとにプロパティを示します。</span><span class="sxs-lookup"><span data-stu-id="86aa5-129">Figure 3 shows the per-instance properties of the ESBSendPassthrough component that uses the ESB Dispatcher.</span></span>  
  
 <span data-ttu-id="86aa5-130">![動的解決の送信パススルー](../esb-toolkit/media/ch6-dynamicresolutionsendpassthrough.gif "Ch6 DynamicResolutionSendPassthrough")</span><span class="sxs-lookup"><span data-stu-id="86aa5-130">![Dynamic Resolution Send Passthrough](../esb-toolkit/media/ch6-dynamicresolutionsendpassthrough.gif "Ch6-DynamicResolutionSendPassthrough")</span></span>  
  
 <span data-ttu-id="86aa5-131">**図 3**</span><span class="sxs-lookup"><span data-stu-id="86aa5-131">**Figure 3**</span></span>  
  
 <span data-ttu-id="86aa5-132">**動的解決のサンプル アプリケーションの ESBSendPassthrough パイプライン内のコンポーネントのインスタンスごとにプロパティ**</span><span class="sxs-lookup"><span data-stu-id="86aa5-132">**The per-instance properties for the components in the ESBSendPassthrough pipeline of the Dynamic Resolution sample application**</span></span>  
  
 <span data-ttu-id="86aa5-133">図 3 に、次のプロパティを示します。</span><span class="sxs-lookup"><span data-stu-id="86aa5-133">The following properties are shown in Figure 3:</span></span>  
  
-   <span data-ttu-id="86aa5-134">**有効になっている**です。</span><span class="sxs-lookup"><span data-stu-id="86aa5-134">**Enabled**.</span></span> <span data-ttu-id="86aa5-135">このプロパティは、パイプラインがアクティブかどうかを判断します。</span><span class="sxs-lookup"><span data-stu-id="86aa5-135">This property determines whether the pipeline is active.</span></span> <span data-ttu-id="86aa5-136">設定されている場合**False**、処理されずにメッセージが通過します。</span><span class="sxs-lookup"><span data-stu-id="86aa5-136">If this is set to **False**, messages pass through without processing.</span></span>  
  
-   <span data-ttu-id="86aa5-137">**エンドポイント**です。</span><span class="sxs-lookup"><span data-stu-id="86aa5-137">**Endpoint**.</span></span> <span data-ttu-id="86aa5-138">このプロパティは、ロード テストとエンドポイント構成にどの競合回避モジュールを決定するために使用する接続文字列です。</span><span class="sxs-lookup"><span data-stu-id="86aa5-138">This property is the connection string used to determine which resolver to load and the end-point configuration.</span></span>  
  
-   <span data-ttu-id="86aa5-139">**MapName**です。</span><span class="sxs-lookup"><span data-stu-id="86aa5-139">**MapName**.</span></span> <span data-ttu-id="86aa5-140">このプロパティは、どの競合回避モジュールを読み込むと、BizTalk マップを実行するために使用する接続文字列です。</span><span class="sxs-lookup"><span data-stu-id="86aa5-140">This property is the connection string used to determine which resolver to load and which BizTalk map to execute.</span></span> <span data-ttu-id="86aa5-141">マップの完全修飾名は、競合回避モジュールの接続文字列の代わりに使用できます。</span><span class="sxs-lookup"><span data-stu-id="86aa5-141">A fully qualified name of a map can be used in place of a resolver's connection string.</span></span>  
  
-   <span data-ttu-id="86aa5-142">**検証**です。</span><span class="sxs-lookup"><span data-stu-id="86aa5-142">**Validate**.</span></span> <span data-ttu-id="86aa5-143">設定すると**True** (既定の設定) を ESB ディスパッチャー逆アセンブラー コンポーネントに指示、ESB 変換サービスは、マップで定義されている送信元スキーマに対してソース メッセージの検証には解決し、実行します。</span><span class="sxs-lookup"><span data-stu-id="86aa5-143">When set to **True** (the default setting), the ESB Dispatcher Disassembler component instructs the ESB Transformation service to validate the source message against the source schema defined in the map that is will resolve and execute.</span></span>