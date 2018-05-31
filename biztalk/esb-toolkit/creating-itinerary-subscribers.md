---
title: Itinerary サブスクライバーを作成 |Microsoft ドキュメント
ms.custom: ''
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: ''
ms.suite: ''
ms.tgt_pltfrm: ''
ms.topic: article
ms.assetid: 84a76aeb-8d40-490a-8ae6-7abfdd2d2573
caps.latest.revision: 3
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: 5f470ed5268c445ab3b7175f1cba07ff1de52a27
ms.sourcegitcommit: 3fc338e52d5dbca2c3ea1685a2faafc7582fe23a
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 12/01/2017
ms.locfileid: "26007195"
---
# <a name="creating-itinerary-subscribers"></a><span data-ttu-id="803b0-102">Itinerary サブスクライバーを作成します。</span><span class="sxs-lookup"><span data-stu-id="803b0-102">Creating Itinerary Subscribers</span></span>
<span data-ttu-id="803b0-103">BizTalk Server メッセージ ボックス データベースに、受信パイプライン経由で到着するメッセージを自動的に公開します。これにより、メッセージが、関連するサブスクライバーで収集できる状態にします。</span><span class="sxs-lookup"><span data-stu-id="803b0-103">BizTalk Server automatically publishes messages arriving through a receive pipeline to the Message Box database; this makes the messages ready for pick-up by the relevant subscriber.</span></span> <span data-ttu-id="803b0-104">この分離方法は、最大限の柔軟性を提供のスケールを設定し、発行を使用しているために、BizTalk ソリューションを開発することをお勧めのメカニズムをサブスクライブします。</span><span class="sxs-lookup"><span data-stu-id="803b0-104">This decoupled approach is the preferred way to develop BizTalk solutions because it provides maximum flexibility, scales well, and uses the publish-subscribe mechanism.</span></span>  
  
 <span data-ttu-id="803b0-105">2 つの方法でサブスクライバーを itinerary サービスを作成するにがあります。</span><span class="sxs-lookup"><span data-stu-id="803b0-105">There are two ways to create an itinerary service subscriber:</span></span>  
  
-   [<span data-ttu-id="803b0-106">スケジュール サービス サブスクライバーとして送信ポートを利用する</span><span class="sxs-lookup"><span data-stu-id="803b0-106">Using a Send Port as an Itinerary Service Subscriber</span></span>](../esb-toolkit/using-a-send-port-as-an-itinerary-service-subscriber.md)  
  
-   [<span data-ttu-id="803b0-107">スケジュール サービス サブスクライバーとしてオーケストレーションを利用する</span><span class="sxs-lookup"><span data-stu-id="803b0-107">Using an Orchestration as an Itinerary Service Subscriber</span></span>](../esb-toolkit/using-an-orchestration-as-an-itinerary-service-subscriber.md)