---
title: "ランプでと傾斜 Off |Microsoft ドキュメント"
ms.custom: 
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: 
ms.suite: 
ms.tgt_pltfrm: 
ms.topic: article
ms.assetid: c0cce5d2-f16f-4bda-94ac-20c4f457cfc7
caps.latest.revision: "3"
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: a0aafa69315dba07219ad8510c77cdc9de2d4bce
ms.sourcegitcommit: cb908c540d8f1a692d01dc8f313e16cb4b4e696d
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 09/20/2017
---
# <a name="on-ramps-and-off-ramps"></a><span data-ttu-id="281da-102">ランプで、ランプ オフ</span><span class="sxs-lookup"><span data-stu-id="281da-102">On-Ramps and Off-Ramps</span></span>
<span data-ttu-id="281da-103">環境で、[!INCLUDE[esbToolkit](../includes/esbtoolkit-md.md)]が展開されると、BizTalk 受信場所が担当する「入り口です」と呼びます ESB 宛てのメッセージの受信。</span><span class="sxs-lookup"><span data-stu-id="281da-103">In an environment where [!INCLUDE[esbToolkit](../includes/esbtoolkit-md.md)] is deployed, a BizTalk receive location responsible for receiving ESB-destined messages is referred to as an "on-ramp."</span></span> <span data-ttu-id="281da-104">ESB 入り口に標準の BizTalk 受信場所を構成する受信場所を関連付ける、toolkit の一部として提供されるパイプラインのいずれかと決定またはの日程を読み取るには、そのパイプラインのコンポーネントを正しく構成しますシナリオに応じて、受信メッセージ。</span><span class="sxs-lookup"><span data-stu-id="281da-104">To configure a standard BizTalk receive location to an ESB on-ramp, associate the receive location with one of the pipelines provided as part of the toolkit, and then correctly configure the components of that pipeline to determine or read the itinerary for the inbound message, depending on your scenario.</span></span>  
  
 <span data-ttu-id="281da-105">ESB「出口」は、BizTalk の動的送信ポートに対応します。</span><span class="sxs-lookup"><span data-stu-id="281da-105">An ESB "off-ramp" corresponds to a BizTalk dynamic send port.</span></span> <span data-ttu-id="281da-106">日程が処理されている、値はシステム Properties.xsd スキーマを使用して、関連付けられているメッセージのコンテキスト プロパティに昇格されます。</span><span class="sxs-lookup"><span data-stu-id="281da-106">As an itinerary is being processed, values are promoted to the context properties of the associated message using the System-Properties.xsd schema.</span></span> <span data-ttu-id="281da-107">BizTalk パブリッシュ/サブスクライブ メカニズムで昇格これら送信ポート (出口) メッセージ配信を完了するには動的でメッセージをルーティングするプロパティです。</span><span class="sxs-lookup"><span data-stu-id="281da-107">The BizTalk publish-subscribe mechanism uses these promoted properties to route a message through a dynamic send port (off-ramp) to complete a message delivery.</span></span>  
  
 <span data-ttu-id="281da-108">次の表は、上のランプによって提供される、[!INCLUDE[esbToolkit](../includes/esbtoolkit-md.md)]です。</span><span class="sxs-lookup"><span data-stu-id="281da-108">The following table lists the on-ramps that are provided by the [!INCLUDE[esbToolkit](../includes/esbtoolkit-md.md)].</span></span>  
  
|<span data-ttu-id="281da-109">名前</span><span class="sxs-lookup"><span data-stu-id="281da-109">Name</span></span>|<span data-ttu-id="281da-110">メッセージ交換パターン</span><span class="sxs-lookup"><span data-stu-id="281da-110">Message exchange pattern</span></span>|<span data-ttu-id="281da-111">**Description**</span><span class="sxs-lookup"><span data-stu-id="281da-111">**Description**</span></span>|  
|----------|------------------------------|---------------------|  
|<span data-ttu-id="281da-112">ESB です。ItineraryServices</span><span class="sxs-lookup"><span data-stu-id="281da-112">ESB.ItineraryServices</span></span>|<span data-ttu-id="281da-113">一方向</span><span class="sxs-lookup"><span data-stu-id="281da-113">One-Way</span></span>|<span data-ttu-id="281da-114">ASMX 入り口です。SOAP ヘッダー内では、ESB itinerary コンテンツが必要ですが。</span><span class="sxs-lookup"><span data-stu-id="281da-114">ASMX on-ramp; expects ESB itinerary content in SOAP header.</span></span>|  
|<span data-ttu-id="281da-115">ESB です。ItineraryServices.Response</span><span class="sxs-lookup"><span data-stu-id="281da-115">ESB.ItineraryServices.Response</span></span>|<span data-ttu-id="281da-116">要求-応答</span><span class="sxs-lookup"><span data-stu-id="281da-116">Request-Response</span></span>|<span data-ttu-id="281da-117">ASMX 入り口です。SOAP ヘッダー内では、ESB itinerary コンテンツが必要ですが。</span><span class="sxs-lookup"><span data-stu-id="281da-117">ASMX on-ramp; expects ESB itinerary content in SOAP header.</span></span>|  
|<span data-ttu-id="281da-118">ESB です。ItineraryServices.WCF</span><span class="sxs-lookup"><span data-stu-id="281da-118">ESB.ItineraryServices.WCF</span></span>|<span data-ttu-id="281da-119">一方向</span><span class="sxs-lookup"><span data-stu-id="281da-119">One-Way</span></span>|<span data-ttu-id="281da-120">Windows Communication Foundation (WCF) の入り口です。SOAP ヘッダー内では、ESB itinerary 参照が必要です。</span><span class="sxs-lookup"><span data-stu-id="281da-120">Windows Communication Foundation (WCF) on-ramp; expects ESB itinerary reference in SOAP header.</span></span>|  
|<span data-ttu-id="281da-121">ESB です。ItineraryServices.Response.WCF</span><span class="sxs-lookup"><span data-stu-id="281da-121">ESB.ItineraryServices.Response.WCF</span></span>|<span data-ttu-id="281da-122">要求-応答</span><span class="sxs-lookup"><span data-stu-id="281da-122">Request-Response</span></span>|<span data-ttu-id="281da-123">WCF の入り口です。SOAP ヘッダー内では、ESB itinerary 参照が必要です。</span><span class="sxs-lookup"><span data-stu-id="281da-123">WCF on-ramp; expects ESB itinerary reference in SOAP header.</span></span>|  
|<span data-ttu-id="281da-124">ESB です。ItineraryServices.Generic.WCF</span><span class="sxs-lookup"><span data-stu-id="281da-124">ESB.ItineraryServices.Generic.WCF</span></span>|<span data-ttu-id="281da-125">一方向</span><span class="sxs-lookup"><span data-stu-id="281da-125">One-Way</span></span>|<span data-ttu-id="281da-126">WCF の入り口です。要求メッセージだけが必要です。</span><span class="sxs-lookup"><span data-stu-id="281da-126">WCF on-ramp; expects request message only.</span></span>|  
|<span data-ttu-id="281da-127">ESB です。ItineraryServices.Generic.Response.WCF</span><span class="sxs-lookup"><span data-stu-id="281da-127">ESB.ItineraryServices.Generic.Response.WCF</span></span>|<span data-ttu-id="281da-128">要求-応答</span><span class="sxs-lookup"><span data-stu-id="281da-128">Request-Response</span></span>|<span data-ttu-id="281da-129">WCF の入り口です。要求メッセージだけが必要です。</span><span class="sxs-lookup"><span data-stu-id="281da-129">WCF on-ramp; expects request message only.</span></span>|  
  
 [!INCLUDE[esbToolkit](../includes/esbtoolkit-md.md)]<span data-ttu-id="281da-130">上のランプれない ASMX は、ESB 行程を選択するように構成する必要があります。</span><span class="sxs-lookup"><span data-stu-id="281da-130"> on-ramps that are not ASMX should be configured to select ESB itineraries.</span></span> <span data-ttu-id="281da-131">ESB 行程を選択する方法の詳細については、次を参照してください。[パイプライン コンポーネントを使用して、既存の日程を選択する](../esb-toolkit/using-a-pipeline-component-to-select-an-existing-itinerary.md)です。</span><span class="sxs-lookup"><span data-stu-id="281da-131">For more information about how to select an ESB itinerary, see [Using a Pipeline Component to Select an Existing Itinerary](../esb-toolkit/using-a-pipeline-component-to-select-an-existing-itinerary.md).</span></span>