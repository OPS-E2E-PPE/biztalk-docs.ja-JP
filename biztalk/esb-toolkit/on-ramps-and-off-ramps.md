---
title: オンランプとオフランプ |Microsoft Docs
ms.custom: ''
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: ''
ms.suite: ''
ms.tgt_pltfrm: ''
ms.topic: article
ms.assetid: c0cce5d2-f16f-4bda-94ac-20c4f457cfc7
caps.latest.revision: 3
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: 528a8a42319fce4dbfc6507ec4d0658092e44963
ms.sourcegitcommit: 381e83d43796a345488d54b3f7413e11d56ad7be
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 05/07/2019
ms.locfileid: "65400052"
---
# <a name="on-ramps-and-off-ramps"></a><span data-ttu-id="bc275-102">オンランプとオフランプ</span><span class="sxs-lookup"><span data-stu-id="bc275-102">On-Ramps and Off-Ramps</span></span>
<span data-ttu-id="bc275-103">環境で、[!INCLUDE[esbToolkit](../includes/esbtoolkit-md.md)]が展開されると、BizTalk 受信場所が担当する「入り口」と呼びます ESB 宛てのメッセージの受信。</span><span class="sxs-lookup"><span data-stu-id="bc275-103">In an environment where [!INCLUDE[esbToolkit](../includes/esbtoolkit-md.md)] is deployed, a BizTalk receive location responsible for receiving ESB-destined messages is referred to as an "on-ramp."</span></span> <span data-ttu-id="bc275-104">ESB 入り口を標準の BizTalk 受信場所を構成するには、受信場所を toolkit の一部として提供されているパイプラインのいずれかと関連付けるおよび決定またはの旅程を読み取り、そのパイプラインのコンポーネントを正しく構成しますシナリオに応じて受信メッセージ。</span><span class="sxs-lookup"><span data-stu-id="bc275-104">To configure a standard BizTalk receive location to an ESB on-ramp, associate the receive location with one of the pipelines provided as part of the toolkit, and then correctly configure the components of that pipeline to determine or read the itinerary for the inbound message, depending on your scenario.</span></span>  
  
 <span data-ttu-id="bc275-105">ESB「オフ ランプ」は、BizTalk の動的送信ポートに対応します。</span><span class="sxs-lookup"><span data-stu-id="bc275-105">An ESB "off-ramp" corresponds to a BizTalk dynamic send port.</span></span> <span data-ttu-id="bc275-106">日程が処理されると、値は、システム Properties.xsd スキーマを使用して、関連付けられているメッセージのコンテキスト プロパティに昇格されます。</span><span class="sxs-lookup"><span data-stu-id="bc275-106">As an itinerary is being processed, values are promoted to the context properties of the associated message using the System-Properties.xsd schema.</span></span> <span data-ttu-id="bc275-107">BizTalk パブリッシュ/サブスクライブこれら昇格メカニズムは送信ポート (傾斜オフ) メッセージ配信を完了する動的な経由でメッセージをルーティングするプロパティ。</span><span class="sxs-lookup"><span data-stu-id="bc275-107">The BizTalk publish-subscribe mechanism uses these promoted properties to route a message through a dynamic send port (off-ramp) to complete a message delivery.</span></span>  
  
 <span data-ttu-id="bc275-108">次の表は、オンランプによって提供される、[!INCLUDE[esbToolkit](../includes/esbtoolkit-md.md)]します。</span><span class="sxs-lookup"><span data-stu-id="bc275-108">The following table lists the on-ramps that are provided by the [!INCLUDE[esbToolkit](../includes/esbtoolkit-md.md)].</span></span>  
  
|<span data-ttu-id="bc275-109">名前</span><span class="sxs-lookup"><span data-stu-id="bc275-109">Name</span></span>|<span data-ttu-id="bc275-110">メッセージ交換パターン</span><span class="sxs-lookup"><span data-stu-id="bc275-110">Message exchange pattern</span></span>|<span data-ttu-id="bc275-111">**[説明]**</span><span class="sxs-lookup"><span data-stu-id="bc275-111">**Description**</span></span>|  
|----------|------------------------------|---------------------|  
|<span data-ttu-id="bc275-112">ESB します。ItineraryServices</span><span class="sxs-lookup"><span data-stu-id="bc275-112">ESB.ItineraryServices</span></span>|<span data-ttu-id="bc275-113">一方向</span><span class="sxs-lookup"><span data-stu-id="bc275-113">One-Way</span></span>|<span data-ttu-id="bc275-114">ASMX のランプ;SOAP ヘッダーでは ESB オンランプ コンテンツが必要です。</span><span class="sxs-lookup"><span data-stu-id="bc275-114">ASMX on-ramp; expects ESB itinerary content in SOAP header.</span></span>|  
|<span data-ttu-id="bc275-115">ESB します。ItineraryServices.Response</span><span class="sxs-lookup"><span data-stu-id="bc275-115">ESB.ItineraryServices.Response</span></span>|<span data-ttu-id="bc275-116">要求-応答</span><span class="sxs-lookup"><span data-stu-id="bc275-116">Request-Response</span></span>|<span data-ttu-id="bc275-117">ASMX のランプ;SOAP ヘッダーでは ESB オンランプ コンテンツが必要です。</span><span class="sxs-lookup"><span data-stu-id="bc275-117">ASMX on-ramp; expects ESB itinerary content in SOAP header.</span></span>|  
|<span data-ttu-id="bc275-118">ESB します。ItineraryServices.WCF</span><span class="sxs-lookup"><span data-stu-id="bc275-118">ESB.ItineraryServices.WCF</span></span>|<span data-ttu-id="bc275-119">一方向</span><span class="sxs-lookup"><span data-stu-id="bc275-119">One-Way</span></span>|<span data-ttu-id="bc275-120">Windows Communication Foundation (WCF) に増加します。SOAP ヘッダーでは ESB スケジュールの参照が必要です。</span><span class="sxs-lookup"><span data-stu-id="bc275-120">Windows Communication Foundation (WCF) on-ramp; expects ESB itinerary reference in SOAP header.</span></span>|  
|<span data-ttu-id="bc275-121">ESB します。ItineraryServices.Response.WCF</span><span class="sxs-lookup"><span data-stu-id="bc275-121">ESB.ItineraryServices.Response.WCF</span></span>|<span data-ttu-id="bc275-122">要求-応答</span><span class="sxs-lookup"><span data-stu-id="bc275-122">Request-Response</span></span>|<span data-ttu-id="bc275-123">WCF - 傾斜します。SOAP ヘッダーでは ESB スケジュールの参照が必要です。</span><span class="sxs-lookup"><span data-stu-id="bc275-123">WCF on-ramp; expects ESB itinerary reference in SOAP header.</span></span>|  
|<span data-ttu-id="bc275-124">ESB します。ItineraryServices.Generic.WCF</span><span class="sxs-lookup"><span data-stu-id="bc275-124">ESB.ItineraryServices.Generic.WCF</span></span>|<span data-ttu-id="bc275-125">一方向</span><span class="sxs-lookup"><span data-stu-id="bc275-125">One-Way</span></span>|<span data-ttu-id="bc275-126">WCF - 傾斜します。要求メッセージのみを想定しています。</span><span class="sxs-lookup"><span data-stu-id="bc275-126">WCF on-ramp; expects request message only.</span></span>|  
|<span data-ttu-id="bc275-127">ESB します。ItineraryServices.Generic.Response.WCF</span><span class="sxs-lookup"><span data-stu-id="bc275-127">ESB.ItineraryServices.Generic.Response.WCF</span></span>|<span data-ttu-id="bc275-128">要求-応答</span><span class="sxs-lookup"><span data-stu-id="bc275-128">Request-Response</span></span>|<span data-ttu-id="bc275-129">WCF - 傾斜します。要求メッセージのみを想定しています。</span><span class="sxs-lookup"><span data-stu-id="bc275-129">WCF on-ramp; expects request message only.</span></span>|  
  
 [!INCLUDE[esbToolkit](../includes/esbtoolkit-md.md)] <span data-ttu-id="bc275-130">オンランプ ASMX を構成して、ESB 行程を選択する必要がないです。</span><span class="sxs-lookup"><span data-stu-id="bc275-130">on-ramps that are not ASMX should be configured to select ESB itineraries.</span></span> <span data-ttu-id="bc275-131">ESB スケジュールを選択する方法の詳細については、次を参照してください。[パイプライン コンポーネントを使用して、既存のスケジュールを選択する](../esb-toolkit/using-a-pipeline-component-to-select-an-existing-itinerary.md)します。</span><span class="sxs-lookup"><span data-stu-id="bc275-131">For more information about how to select an ESB itinerary, see [Using a Pipeline Component to Select an Existing Itinerary](../esb-toolkit/using-a-pipeline-component-to-select-an-existing-itinerary.md).</span></span>