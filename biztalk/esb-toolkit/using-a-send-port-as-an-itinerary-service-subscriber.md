---
title: 送信ポートを使用して、スケジュール サービス サブスクライバーとして |Microsoft Docs
ms.custom: ''
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: ''
ms.suite: ''
ms.tgt_pltfrm: ''
ms.topic: article
ms.assetid: 898b461c-4d0d-4703-a8ca-7f52f3f15f70
caps.latest.revision: 3
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: 81ab596b01c515fad670b959c00e0571b5e9962c
ms.sourcegitcommit: 381e83d43796a345488d54b3f7413e11d56ad7be
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 05/07/2019
ms.locfileid: "65396480"
---
# <a name="using-a-send-port-as-an-itinerary-service-subscriber"></a><span data-ttu-id="ae928-102">スケジュール サービス サブスクライバーとして送信ポートを使用します。</span><span class="sxs-lookup"><span data-stu-id="ae928-102">Using a Send Port as an Itinerary Service Subscriber</span></span>
<span data-ttu-id="ae928-103">スケジュール サービス サブスクライバーとして送信ポートを使用する方法の例としては、図 1 を次の条件を満たすメッセージを取得する動的な一方向送信ポートのフィルター条件を示します。</span><span class="sxs-lookup"><span data-stu-id="ae928-103">As an example of how to use a send port as an itinerary service subscriber, Figure 1 shows the filter conditions for a dynamic one-way sent port that picks up messages that meet the following conditions:</span></span>  
  
- <span data-ttu-id="ae928-104">**IsRequestResponse = False**</span><span class="sxs-lookup"><span data-stu-id="ae928-104">**IsRequestResponse = False**</span></span>  
  
- <span data-ttu-id="ae928-105">**ServiceName = DynamicTest**</span><span class="sxs-lookup"><span data-stu-id="ae928-105">**ServiceName = DynamicTest**</span></span>  
  
- <span data-ttu-id="ae928-106">**ServiceState = 保留中**</span><span class="sxs-lookup"><span data-stu-id="ae928-106">**ServiceState = Pending**</span></span>  
  
- <span data-ttu-id="ae928-107">**ServiceType メッセージングを =**</span><span class="sxs-lookup"><span data-stu-id="ae928-107">**ServiceType = Messaging**</span></span>  
  
  <span data-ttu-id="ae928-108">![送信ポート](../esb-toolkit/media/ch4-sendport.gif "Ch4 SendPort")</span><span class="sxs-lookup"><span data-stu-id="ae928-108">![Send Port](../esb-toolkit/media/ch4-sendport.gif "Ch4-SendPort")</span></span>  
  
  <span data-ttu-id="ae928-109">**図 1**</span><span class="sxs-lookup"><span data-stu-id="ae928-109">**Figure 1**</span></span>  
  
  <span data-ttu-id="ae928-110">**送信ポート フィルターの例**</span><span class="sxs-lookup"><span data-stu-id="ae928-110">**Example of send port filters**</span></span>  
  
  <span data-ttu-id="ae928-111">送信ポートのフィルター式を使用するが選択 itinerary の傾斜を使用して、メッセージ ボックス データベースからメッセージのプロパティと値のセットを指定します。</span><span class="sxs-lookup"><span data-stu-id="ae928-111">Use send port filter expressions to specify the property and value sets of messages it will pick up from the Message Box database through the itinerary on-ramp.</span></span>  
  
> [!NOTE]
>  <span data-ttu-id="ae928-112">できるだけ; フォーカスがある、特定のフィルター条件を使用することが重要それ以外の場合、意図しないメッセージは、大規模環境で問題が発生する可能性がありますのリスクがあります。</span><span class="sxs-lookup"><span data-stu-id="ae928-112">It is important to use filter conditions that are as specific and focused as possible; otherwise, there is a risk of picking up unintended messages, which could cause problems in a high-volume environment.</span></span> <span data-ttu-id="ae928-113">システム Properties.xsd スキーマでは、サブスクリプションのフィルターのプロパティを定義します。</span><span class="sxs-lookup"><span data-stu-id="ae928-113">The schema System-Properties.xsd defines the filter properties of subscriptions.</span></span>