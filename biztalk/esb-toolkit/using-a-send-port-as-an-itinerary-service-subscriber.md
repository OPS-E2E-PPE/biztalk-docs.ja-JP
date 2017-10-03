---
title: "送信ポートを使用して、Itinerary サービス サブスクライバーとして |Microsoft ドキュメント"
ms.custom: 
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: 
ms.suite: 
ms.tgt_pltfrm: 
ms.topic: article
ms.assetid: 898b461c-4d0d-4703-a8ca-7f52f3f15f70
caps.latest.revision: "3"
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: 5213b22c1bdfaa505dbf4b62a03095bcec5a1746
ms.sourcegitcommit: cb908c540d8f1a692d01dc8f313e16cb4b4e696d
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 09/20/2017
---
# <a name="using-a-send-port-as-an-itinerary-service-subscriber"></a><span data-ttu-id="d747c-102">Itinerary サービス サブスクライバーとして、送信ポートを使用します。</span><span class="sxs-lookup"><span data-stu-id="d747c-102">Using a Send Port as an Itinerary Service Subscriber</span></span>
<span data-ttu-id="d747c-103">Itinerary サービス サブスクライバーとして、送信ポートを使用する方法の例は、としては、図 1 は、次の条件に一致するメッセージを取得する動的な一方向送信ポートのフィルター条件を示します。</span><span class="sxs-lookup"><span data-stu-id="d747c-103">As an example of how to use a send port as an itinerary service subscriber, Figure 1 shows the filter conditions for a dynamic one-way sent port that picks up messages that meet the following conditions:</span></span>  
  
-   <span data-ttu-id="d747c-104">**IsRequestResponse = False**</span><span class="sxs-lookup"><span data-stu-id="d747c-104">**IsRequestResponse = False**</span></span>  
  
-   <span data-ttu-id="d747c-105">**ServiceName = DynamicTest**</span><span class="sxs-lookup"><span data-stu-id="d747c-105">**ServiceName = DynamicTest**</span></span>  
  
-   <span data-ttu-id="d747c-106">**ServiceState = 保留中**</span><span class="sxs-lookup"><span data-stu-id="d747c-106">**ServiceState = Pending**</span></span>  
  
-   <span data-ttu-id="d747c-107">**ServiceType メッセージングを =**</span><span class="sxs-lookup"><span data-stu-id="d747c-107">**ServiceType = Messaging**</span></span>  
  
 <span data-ttu-id="d747c-108">![送信ポート](../esb-toolkit/media/ch4-sendport.gif "Ch4 SendPort")</span><span class="sxs-lookup"><span data-stu-id="d747c-108">![Send Port](../esb-toolkit/media/ch4-sendport.gif "Ch4-SendPort")</span></span>  
  
 <span data-ttu-id="d747c-109">**図 1**</span><span class="sxs-lookup"><span data-stu-id="d747c-109">**Figure 1**</span></span>  
  
 <span data-ttu-id="d747c-110">**送信ポート フィルターの例**</span><span class="sxs-lookup"><span data-stu-id="d747c-110">**Example of send port filters**</span></span>  
  
 <span data-ttu-id="d747c-111">送信ポートのフィルター式を使用すると、itinerary の増加を使用してメッセージ ボックス データベースからピックアップされますメッセージのプロパティと値のセットを指定します。</span><span class="sxs-lookup"><span data-stu-id="d747c-111">Use send port filter expressions to specify the property and value sets of messages it will pick up from the Message Box database through the itinerary on-ramp.</span></span>  
  
> [!NOTE]
>  <span data-ttu-id="d747c-112">特定で可能なです。 フォーカスのあるフィルター条件を使用することが重要それ以外の場合、意図しないメッセージは、大容量の環境で問題が発生する可能性がありますのピックアップのリスクがあります。</span><span class="sxs-lookup"><span data-stu-id="d747c-112">It is important to use filter conditions that are as specific and focused as possible; otherwise, there is a risk of picking up unintended messages, which could cause problems in a high-volume environment.</span></span> <span data-ttu-id="d747c-113">システム Properties.xsd スキーマでは、サブスクリプションのフィルターのプロパティを定義します。</span><span class="sxs-lookup"><span data-stu-id="d747c-113">The schema System-Properties.xsd defines the filter properties of subscriptions.</span></span>