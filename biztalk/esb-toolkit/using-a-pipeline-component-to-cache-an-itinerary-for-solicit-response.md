---
title: 送信請求-応答の日程をキャッシュするパイプライン コンポーネントを使用して |Microsoft ドキュメント
ms.custom: ''
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: ''
ms.suite: ''
ms.tgt_pltfrm: ''
ms.topic: article
ms.assetid: add07ebf-785c-4c53-be69-efd40677a758
caps.latest.revision: 3
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: 64b6822a4f4ca70e88ee86277e00645982595b47
ms.sourcegitcommit: cb908c540d8f1a692d01dc8f313e16cb4b4e696d
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 09/20/2017
ms.locfileid: "22294994"
---
# <a name="using-a-pipeline-component-to-cache-an-itinerary-for-solicit-response"></a><span data-ttu-id="e767e-102">パイプライン コンポーネントを使用して、送信請求-応答の日程をキャッシュするには</span><span class="sxs-lookup"><span data-stu-id="e767e-102">Using a Pipeline Component to Cache an Itinerary for Solicit-Response</span></span>
<span data-ttu-id="e767e-103">送信するメッセージ、 [!INCLUDE[esbToolkit](../includes/esbtoolkit-md.md)] itinerary 入り口は旅程を一方向または双方向 (要求-応答) 行程経由させることです。</span><span class="sxs-lookup"><span data-stu-id="e767e-103">Messages submitted through a [!INCLUDE[esbToolkit](../includes/esbtoolkit-md.md)] itinerary on-ramp can go through either a one-way itinerary or a two-way (request-response) itinerary.</span></span> <span data-ttu-id="e767e-104">要求-応答の日程をサポートするには、itinerary メカニズムは BizTalk 動的な送信請求-応答送信ポートのキャッシュを提供する必要があります。</span><span class="sxs-lookup"><span data-stu-id="e767e-104">To support request-response itineraries, the itinerary mechanism must provide caching for BizTalk dynamic Solicit-Response send ports.</span></span>  
  
 <span data-ttu-id="e767e-105">ESB 行程キャッシュのパイプライン コンポーネントは、キャッシュ発信メッセージ コンテキストに保存されている旅程を配置し、応答メッセージにアタッチ構成可能なキャッシュ キーを使用して、送信ポートによって返されます。</span><span class="sxs-lookup"><span data-stu-id="e767e-105">The ESB Itinerary Cache pipeline component places the itinerary stored in the outbound message context into the cache and attaches it to the response message; it is returned by the send port using the configurable caching key.</span></span> <span data-ttu-id="e767e-106">これにより、itinerary サービスを処理し、旅行計画に現在のサービスの後に定義されている後続のサービスを実行できます。</span><span class="sxs-lookup"><span data-stu-id="e767e-106">This allows the itinerary service to process and execute subsequent services defined after the current service in the itinerary.</span></span>  
  
 <span data-ttu-id="e767e-107">ESB 行程キャッシュ パイプライン コンポーネントは、既定では、図 1 に示すように ItineraryReceiveSend BizTalk パイプラインに存在します。</span><span class="sxs-lookup"><span data-stu-id="e767e-107">By default, the ESB Itinerary Cache pipeline component resides in the ItineraryReceiveSend BizTalk pipeline, as shown in Figure 1.</span></span> <span data-ttu-id="e767e-108">このパイプラインは、送信請求-応答送信ポートの受信パイプラインとしてのみ使用する必要があります。</span><span class="sxs-lookup"><span data-stu-id="e767e-108">This pipeline should be used only as the receive pipeline for a Solicit-Response send port.</span></span>  
  
 <span data-ttu-id="e767e-109">![パイプライン コンポーネントのキャッシュ](../esb-toolkit/media/ch4-pipelinecomponentcache.gif "Ch4 PipelineComponentCache")</span><span class="sxs-lookup"><span data-stu-id="e767e-109">![Pipeline Component Cache](../esb-toolkit/media/ch4-pipelinecomponentcache.gif "Ch4-PipelineComponentCache")</span></span>  
  
 <span data-ttu-id="e767e-110">**図 1**</span><span class="sxs-lookup"><span data-stu-id="e767e-110">**Figure 1**</span></span>  
  
 <span data-ttu-id="e767e-111">**ESB 行程キャッシュ パイプライン コンポーネント**</span><span class="sxs-lookup"><span data-stu-id="e767e-111">**The ESB Itinerary Cache Pipeline component**</span></span>  
  
 <span data-ttu-id="e767e-112">使用する BizTalk の ESB 行程キャッシュ パイプライン コンポーネントは、送信請求-応答送信ポートのパイプラインを受信します。</span><span class="sxs-lookup"><span data-stu-id="e767e-112">Use the ESB Itinerary Cache Pipeline component in a BizTalk receive pipeline for a Solicit-Response send port.</span></span>