---
title: "動的解決のサンプルについては、双方向のメッセージング シナリオ |Microsoft ドキュメント"
ms.custom: 
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: 
ms.suite: 
ms.tgt_pltfrm: 
ms.topic: article
ms.assetid: e89792f1-c725-46c4-946c-23211e2f892a
caps.latest.revision: "4"
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: 852b1f203b693c7783c7eb461c521f3fbe0ceffe
ms.sourcegitcommit: cb908c540d8f1a692d01dc8f313e16cb4b4e696d
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 09/20/2017
---
# <a name="two-way-messaging-scenarios-for-the-dynamic-resolution-sample"></a><span data-ttu-id="683dc-102">動的解決のサンプルについては、双方向のメッセージング シナリオ</span><span class="sxs-lookup"><span data-stu-id="683dc-102">Two-Way Messaging Scenarios for the Dynamic Resolution Sample</span></span>
<span data-ttu-id="683dc-103">このトピックの双方向のメッセージング シナリオを実行する方法を示しています、[!INCLUDE[esbToolkit](../includes/esbtoolkit-md.md)]動的解決のサンプルです。</span><span class="sxs-lookup"><span data-stu-id="683dc-103">This topic shows how you can run the two-way messaging scenarios for the [!INCLUDE[esbToolkit](../includes/esbtoolkit-md.md)] Dynamic Resolution sample.</span></span>  
  
 <span data-ttu-id="683dc-104">**動的解決のサンプルの双方向のメッセージング シナリオを実行するには**</span><span class="sxs-lookup"><span data-stu-id="683dc-104">**To run the two-way messaging scenarios for the Dynamic Resolution sample**</span></span>  
  
1.  <span data-ttu-id="683dc-105">最初にこのサンプルを実行する前に、受信場所の URL が適切な Web サービスを指していることを確認してください。</span><span class="sxs-lookup"><span data-stu-id="683dc-105">Before you run this sample for the first time, make sure that the receive location URL points to the appropriate Web service.</span></span> <span data-ttu-id="683dc-106">Web サービス URL/ESB を指定します。NorthAmericanServices/CustomerOrder.asmx、DynamicResolutionReqResp_SOAP の場所が表示されます。</span><span class="sxs-lookup"><span data-stu-id="683dc-106">Specify the Web service URL /ESB.NorthAmericanServices/CustomerOrder.asmx for the DynamicResolutionReqResp_SOAP receive location.</span></span> <span data-ttu-id="683dc-107">また、DynamicResolutionSolicitResp をという名前の動的送信ポートが存在することを確認します。</span><span class="sxs-lookup"><span data-stu-id="683dc-107">Also, make sure that the dynamic send port named DynamicResolutionSolicitResp exists.</span></span>  
  
    > [!NOTE]
    >  <span data-ttu-id="683dc-108">動的解決サンプルでは、動的な解決を使用してメッセージを送信し、カナダの Web サービス (http://localhost/ESB.CanadianServices/SubmitPOService.asmx) から応答を受信します。</span><span class="sxs-lookup"><span data-stu-id="683dc-108">The Dynamic Resolution sample uses dynamic resolution to send messages to, and receive responses from, the Canadian Web service (http://localhost/ESB.CanadianServices/SubmitPOService.asmx).</span></span> <span data-ttu-id="683dc-109">このサンプルの静的な送信ポートが定義されていないためにです。</span><span class="sxs-lookup"><span data-stu-id="683dc-109">This is why a static send port is not defined for this sample.</span></span> <span data-ttu-id="683dc-110">動的解決のコンポーネントは、解像度から、送信 URL を取得し、受信場所のアダプターのプロバイダー フレームワーク、DynamicResolutionReqResp_SOAP 内で構成されている ESBReceiveXml パイプラインによって呼び出されます。</span><span class="sxs-lookup"><span data-stu-id="683dc-110">The dynamic resolution component retrieves the outbound URL from the Resolution and Adapter Provider Framework called by the ESBReceiveXml pipeline, which is configured within the DynamicResolutionReqResp_SOAP receive location.</span></span> <span data-ttu-id="683dc-111">双方向のメッセージングの例の一部では、ESBMapSend パイプラインは、解決して、Microsoft BizTalk マップを実行します。</span><span class="sxs-lookup"><span data-stu-id="683dc-111">In some of the two-way messaging examples, the ESBMapSend pipeline resolves and executes Microsoft BizTalk maps.</span></span>  
  
2.  <span data-ttu-id="683dc-112">GlobalBank.ESB アプリケーションが既に実行されていない場合は、BizTalk 管理コンソールを使用して、開始します。</span><span class="sxs-lookup"><span data-stu-id="683dc-112">If the GlobalBank.ESB application is not already running, use the BizTalk Administration Console to start it.</span></span>  
  
3.  <span data-ttu-id="683dc-113">実行する例を決定します。</span><span class="sxs-lookup"><span data-stu-id="683dc-113">Decide which example you want to execute.</span></span> <span data-ttu-id="683dc-114">双方向のすべてのメッセージング シナリオでは、ESB を使用します。NorthAmericanServices Web サービスにある http://localhost/ESB.NorthAmericanServices/CustomerOrder.asmx DynamicResolutionReqResp_SOAP をという名前の受信場所を使用する BizTalk に要求メッセージを公開します。</span><span class="sxs-lookup"><span data-stu-id="683dc-114">All two-way messaging scenarios use the ESB.NorthAmericanServices Web service located at http://localhost/ESB.NorthAmericanServices/CustomerOrder.asmx to publish the request message to BizTalk, which uses the receive location named DynamicResolutionReqResp_SOAP.</span></span> <span data-ttu-id="683dc-115">10 の双方向メッセージングの例は、それぞれ固有のバインド ファイルで表されます。</span><span class="sxs-lookup"><span data-stu-id="683dc-115">There are 10 two-way messaging examples, each represented by a unique binding file.</span></span> <span data-ttu-id="683dc-116">次の表では、これらの例は、その関連付けられたバインド ファイルと説明の一覧表示します。</span><span class="sxs-lookup"><span data-stu-id="683dc-116">The following tables list these examples, with their associated binding files and descriptions.</span></span>  
  
    |<span data-ttu-id="683dc-117">SOAP 送信 (submitOrder アクション) が SOAP 受信、BRE の競合回避モジュールを使用します。</span><span class="sxs-lookup"><span data-stu-id="683dc-117">SOAP Inbound to SOAP Outbound (submitOrder Action) Using the BRE Resolver</span></span>|  
    |---------------------------------------------------------------------------------|  
    |<span data-ttu-id="683dc-118">GlobalBank.ESB.DynamicResolution_SubmitOrder_To_SubmitOrder_BRE_Bindings.xml をという名前のバインド ファイルを使用して、受信場所を設定し、送信ポートのプロパティです。</span><span class="sxs-lookup"><span data-stu-id="683dc-118">Uses the binding file named GlobalBank.ESB.DynamicResolution_SubmitOrder_To_SubmitOrder_BRE_Bindings.xml to set the receive location and send port properties.</span></span>|  
    |<span data-ttu-id="683dc-119">エンドポイント解決のため、受信場所で ESB ディスパッチャーを使用します。</span><span class="sxs-lookup"><span data-stu-id="683dc-119">Uses the ESB Dispatcher at the receive location for endpoint resolution.</span></span>|  
  
    |<span data-ttu-id="683dc-120">SOAP 送信 (submitOrder アクション) が SOAP 受信エンドポイントおよび変換の解像度、BRE の競合回避モジュールを使用します。</span><span class="sxs-lookup"><span data-stu-id="683dc-120">SOAP Inbound to SOAP Outbound (submitOrder Action) Using the BRE Resolver for Endpoint and Transformation Resolution</span></span>|  
    |----------------------------------------------------------------------------------------------------------------------------|  
    |<span data-ttu-id="683dc-121">GlobalBank.ESB.DynamicResolution_SubmitOrder_To_SubmitOrder_BRE_Routing_AND_ Transform_Bindings.xml をという名前のバインド ファイルを使用して、受信場所を設定し、送信ポートのプロパティです。</span><span class="sxs-lookup"><span data-stu-id="683dc-121">Uses the binding file named GlobalBank.ESB.DynamicResolution_SubmitOrder_To_SubmitOrder_BRE_Routing_AND_ Transform_Bindings.xml to set the receive location and send port properties.</span></span>|  
    |<span data-ttu-id="683dc-122">使用して、出力方向の送信ポートで ESB ディスパッチャー コンポーネントのパイプラインし、発信の受信場所のパイプライン、マップを動的に解決しています。</span><span class="sxs-lookup"><span data-stu-id="683dc-122">Uses the ESB Dispatcher component on the outbound send port pipeline and the outbound receive location pipeline to dynamically resolve and execute the map.</span></span>|  
    |<span data-ttu-id="683dc-123">エンドポイント解決のため、受信場所で ESB ディスパッチャーを使用します。</span><span class="sxs-lookup"><span data-stu-id="683dc-123">Uses the ESB Dispatcher at the receive location for endpoint resolution.</span></span>|  
  
    |<span data-ttu-id="683dc-124">SOAP 受信 SOAP 送信 (submitOrder アクション) を静的な競合回避モジュールを使用します。</span><span class="sxs-lookup"><span data-stu-id="683dc-124">SOAP Inbound to SOAP Outbound (submitOrder Action) Using the STATIC Resolver</span></span>|  
    |------------------------------------------------------------------------------------|  
    |<span data-ttu-id="683dc-125">GlobalBank.ESB.DynamicResolution_SubmitOrder_To_SubmitOrder_STATIC_Bindings.xml をという名前のバインド ファイルを使用して、受信場所を設定し、送信ポートのプロパティです。</span><span class="sxs-lookup"><span data-stu-id="683dc-125">Uses the binding file named GlobalBank.ESB.DynamicResolution_SubmitOrder_To_SubmitOrder_STATIC_Bindings.xml to set the receive location and send port properties.</span></span>|  
    |<span data-ttu-id="683dc-126">受信ポートでマップを静的に設定します。</span><span class="sxs-lookup"><span data-stu-id="683dc-126">Sets the maps statically at the receive port.</span></span>|  
    |<span data-ttu-id="683dc-127">エンドポイント解決のため、受信場所で ESB ディスパッチャーを使用します。</span><span class="sxs-lookup"><span data-stu-id="683dc-127">Uses the ESB Dispatcher at the receive location for endpoint resolution.</span></span>|  
  
    |<span data-ttu-id="683dc-128">SOAP 送信 (submitOrder アクション) が SOAP 受信サーバーを使用して、UDDI リゾルバーに対して、Microsoft UDDI</span><span class="sxs-lookup"><span data-stu-id="683dc-128">SOAP Inbound to SOAP Outbound (submitOrder Action) Using the UDDI Resolver Against the Microsoft UDDI Server</span></span>|  
    |--------------------------------------------------------------------------------------------------------------------|  
    |<span data-ttu-id="683dc-129">GlobalBank.ESB.DynamicResolution_SubmitOrder_To_SubmitOrder_UDDI_MSFTREGISTRY_ Bindings.xml をという名前のバインド ファイルを使用して、受信場所を設定し、送信ポートのプロパティです。</span><span class="sxs-lookup"><span data-stu-id="683dc-129">Uses the binding file named GlobalBank.ESB.DynamicResolution_SubmitOrder_To_SubmitOrder_UDDI_MSFTREGISTRY_ Bindings.xml to set the receive location and send port properties.</span></span>|  
    |<span data-ttu-id="683dc-130">受信ポートでマップを静的に設定します。</span><span class="sxs-lookup"><span data-stu-id="683dc-130">Sets the maps statically at the receive port.</span></span>|  
    |<span data-ttu-id="683dc-131">エンドポイント解決のため、受信場所で ESB ディスパッチャーを使用します。</span><span class="sxs-lookup"><span data-stu-id="683dc-131">Uses the ESB Dispatcher at the receive location for endpoint resolution.</span></span>|  
  
    > [!NOTE]
    >  <span data-ttu-id="683dc-132">前の例では、ターゲット UDDI サーバー上に存在する 1 つに、バインド ファイル内のサービス キーを変更する必要があります。</span><span class="sxs-lookup"><span data-stu-id="683dc-132">For the preceding example, you must change the service key in the binding file to one that exists on the target UDDI server.</span></span>  
  
    |<span data-ttu-id="683dc-133">SOAP 送信 (submitOrder アクション) が SOAP 受信サーバーを使用して、UDDI リゾルバーに対して、SOA ソフトウェア UDDI</span><span class="sxs-lookup"><span data-stu-id="683dc-133">SOAP Inbound to SOAP Outbound (submitOrder Action) Using the UDDI Resolver Against the SOA Software UDDI Server</span></span>|  
    |-----------------------------------------------------------------------------------------------------------------------|  
    |<span data-ttu-id="683dc-134">GlobalBank.ESB.DynamicResolution_SubmitOrder_To_SubmitOrder_UDDI_SOAREGISTRY_ Bindings.xml をという名前のバインド ファイルを使用して、受信場所を設定し、送信ポートのプロパティです。</span><span class="sxs-lookup"><span data-stu-id="683dc-134">Uses the binding file named GlobalBank.ESB.DynamicResolution_SubmitOrder_To_SubmitOrder_UDDI_SOAREGISTRY_ Bindings.xml to set the receive location and send port properties.</span></span>|  
    |<span data-ttu-id="683dc-135">受信ポートでマップを静的に設定します。</span><span class="sxs-lookup"><span data-stu-id="683dc-135">Sets the maps statically at the receive port.</span></span>|  
    |<span data-ttu-id="683dc-136">エンドポイント解決のため、受信場所で ESB ディスパッチャーを使用します。</span><span class="sxs-lookup"><span data-stu-id="683dc-136">Uses the ESB Dispatcher at the receive location for endpoint resolution.</span></span>|  
  
    |<span data-ttu-id="683dc-137">SOAP 受信 SOAP 送信 (submitOrder アクション) を XPATH の競合回避モジュールを使用します。</span><span class="sxs-lookup"><span data-stu-id="683dc-137">SOAP Inbound to SOAP Outbound (submitOrder Action) Using the XPATH Resolver</span></span>|  
    |-----------------------------------------------------------------------------------|  
    |<span data-ttu-id="683dc-138">GlobalBank.ESB.DynamicResolution_SubmitOrder_To_SubmitOrder_XPATH_Bindings.xml をという名前のバインド ファイルを使用して、受信場所を設定し、送信ポートのプロパティです。</span><span class="sxs-lookup"><span data-stu-id="683dc-138">Uses the binding file named GlobalBank.ESB.DynamicResolution_SubmitOrder_To_SubmitOrder_XPATH_Bindings.xml to set the receive location and send port properties.</span></span>|  
    |<span data-ttu-id="683dc-139">受信ポートでマップを静的に設定します。</span><span class="sxs-lookup"><span data-stu-id="683dc-139">Sets the maps statically at the receive port.</span></span>|  
    |<span data-ttu-id="683dc-140">エンドポイント解決のため、受信場所で ESB ディスパッチャーを使用します。</span><span class="sxs-lookup"><span data-stu-id="683dc-140">Uses the ESB Dispatcher at the receive location for endpoint resolution.</span></span>|  
    |<span data-ttu-id="683dc-141">メッセージには、エンドポイント構成の ID が含まれています。 = http://localhost/ESB.CanadianServices/SubmitPOService.asmx および customerName http://globalbank.esb.dynamicresolution.com/canadianservices/を = です。</span><span class="sxs-lookup"><span data-stu-id="683dc-141">The message contains the endpoint configuration ID=http://localhost/ESB.CanadianServices/SubmitPOService.asmx and customerName=http://globalbank.esb.dynamicresolution.com/canadianservices/.</span></span>|  
  
    |<span data-ttu-id="683dc-142">SOAP 送信 (submitPurchase アクション) が SOAP 受信、BRE の競合回避モジュールのエンドポイントと変換の解決策を使用します。</span><span class="sxs-lookup"><span data-stu-id="683dc-142">SOAP Inbound to SOAP Outbound (submitPurchase Action) Using the BRE Resolver Endpoint and Transformation Resolution</span></span>|  
    |---------------------------------------------------------------------------------------------------------------------------|  
    |<span data-ttu-id="683dc-143">GlobalBank.ESB.DynamicResolution_SubmitOrder_To_SubmitPurchaseOrder_BRE_Routing_ AND_Transform_Bindings.xml をという名前のバインド ファイルを使用して、受信場所を設定し、送信ポートのプロパティです。</span><span class="sxs-lookup"><span data-stu-id="683dc-143">Uses the binding file named GlobalBank.ESB.DynamicResolution_SubmitOrder_To_SubmitPurchaseOrder_BRE_Routing_ AND_Transform_Bindings.xml to set the receive location and send port properties.</span></span>|  
    |<span data-ttu-id="683dc-144">使用して、出力方向の送信ポートで ESB ディスパッチャー コンポーネントのパイプラインし、発信の受信場所のパイプライン、マップを動的に解決しています。</span><span class="sxs-lookup"><span data-stu-id="683dc-144">Uses the ESB Dispatcher component on the outbound send port pipeline and the outbound receive location pipeline to dynamically resolve and execute the map.</span></span>|  
    |<span data-ttu-id="683dc-145">エンドポイント解決のため、受信場所で ESB ディスパッチャーを使用します。</span><span class="sxs-lookup"><span data-stu-id="683dc-145">Uses the ESB Dispatcher at the receive location for endpoint resolution.</span></span>|  
    |<span data-ttu-id="683dc-146">BRE の競合回避モジュールの変更、**アクション**から**submitOrder**に**submitPurchase**です。</span><span class="sxs-lookup"><span data-stu-id="683dc-146">The BRE Resolver changes the **Action** from **submitOrder** to **submitPurchase**.</span></span>|  
  
    |<span data-ttu-id="683dc-147">SOAP 受信 SOAP 送信 (submitPurchase アクション) を静的な競合回避モジュールを使用します。</span><span class="sxs-lookup"><span data-stu-id="683dc-147">SOAP Inbound to SOAP Outbound (submitPurchase Action) Using the STATIC Resolver</span></span>|  
    |---------------------------------------------------------------------------------------|  
    |<span data-ttu-id="683dc-148">GlobalBank.ESB.DynamicResolution_SubmitOrder_To_SubmitPurchaseOrder_STATIC_ Bindings.xml をという名前のバインド ファイルを使用して、受信場所を設定し、送信ポートのプロパティです。</span><span class="sxs-lookup"><span data-stu-id="683dc-148">Uses the binding file named GlobalBank.ESB.DynamicResolution_SubmitOrder_To_SubmitPurchaseOrder_STATIC_ Bindings.xml to set the receive location and send port properties.</span></span>|  
    |<span data-ttu-id="683dc-149">受信ポートでマップを静的に設定します。</span><span class="sxs-lookup"><span data-stu-id="683dc-149">Sets the maps statically at the receive port.</span></span>|  
    |<span data-ttu-id="683dc-150">エンドポイント解決のため、受信場所で ESB ディスパッチャーを使用します。</span><span class="sxs-lookup"><span data-stu-id="683dc-150">Uses the ESB Dispatcher at the receive location for endpoint resolution.</span></span>|  
    |<span data-ttu-id="683dc-151">静的な競合回避モジュールの変更、**アクション**から**submitOrder**に**submitPurchase**です。</span><span class="sxs-lookup"><span data-stu-id="683dc-151">The STATIC Resolver changes the **Action** from **submitOrder** to **submitPurchase**.</span></span>|  
  
4.  <span data-ttu-id="683dc-152">GlobalBank.ESB アプリケーションを実行するメッセージの例については、バインド ファイルをインポートします。</span><span class="sxs-lookup"><span data-stu-id="683dc-152">Import the binding file for the messaging example you want to execute into the GlobalBank.ESB application.</span></span>  
  
5.  <span data-ttu-id="683dc-153">Microsoft InfoPath、.NET の Web サービス Studio またはその他の適切なメカニズムを使用して、NorthAmerican Web サービスを呼び出します。</span><span class="sxs-lookup"><span data-stu-id="683dc-153">Call the NorthAmerican Web service using Microsoft InfoPath, the .NET Web Service Studio, or any other appropriate mechanism.</span></span> <span data-ttu-id="683dc-154">操作に必要なすべてのパラメーターを含めることを確認します。</span><span class="sxs-lookup"><span data-stu-id="683dc-154">Make sure that you include all parameters required by the operation.</span></span>  
  
6.  <span data-ttu-id="683dc-155">返されたメッセージ応答を探します。</span><span class="sxs-lookup"><span data-stu-id="683dc-155">Look for the returned message response.</span></span> <span data-ttu-id="683dc-156">指定した場合、 **submitOrder**アクションのテキスト"Submit Order"の値が前に、 **ID**フィールドに返されたメッセージ。</span><span class="sxs-lookup"><span data-stu-id="683dc-156">If you specified the **submitOrder** action, the text "Submit Order" will precede the value of the **ID** field in the returned message.</span></span> <span data-ttu-id="683dc-157">指定した場合、 **submitPurchase**操作の「送信購買」テキストの値が前に、 **ID**フィールドに返されたメッセージ。</span><span class="sxs-lookup"><span data-stu-id="683dc-157">If you specified the **submitPurchase** action, the text "Submit Purchase" will precede the value of the **ID** field in the returned message.</span></span>  
  
 <span data-ttu-id="683dc-158">このサンプルでの ESB ディスパッチャーと ESB ディスパッチャーの逆アセンブラー パイプライン コンポーネントの使用方法を理解するのを参照してください。 [「動的解決サンプルの動作](../esb-toolkit/how-the-dynamic-resolution-sample-works.md)です。</span><span class="sxs-lookup"><span data-stu-id="683dc-158">To understand how the sample uses the ESB Dispatcher and ESB Dispatcher Disassembler pipeline components, see [How the Dynamic Resolution Sample Works](../esb-toolkit/how-the-dynamic-resolution-sample-works.md).</span></span>