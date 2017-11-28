---
title: "Itinerary サブスクライバーを作成 |Microsoft ドキュメント"
ms.custom: 
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: 
ms.suite: 
ms.tgt_pltfrm: 
ms.topic: article
ms.assetid: 84a76aeb-8d40-490a-8ae6-7abfdd2d2573
caps.latest.revision: "3"
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: 81e9790c36d1af9d48942c5de7ccc8eab6d87a5c
ms.sourcegitcommit: cb908c540d8f1a692d01dc8f313e16cb4b4e696d
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 09/20/2017
---
# <a name="creating-itinerary-subscribers"></a><span data-ttu-id="3123e-102">Itinerary サブスクライバーを作成します。</span><span class="sxs-lookup"><span data-stu-id="3123e-102">Creating Itinerary Subscribers</span></span>
[!INCLUDE[prague](../includes/prague-md.md)]<span data-ttu-id="3123e-103">受信パイプライン経由でメッセージ ボックス データベースに到着するメッセージを自動的に発行します。これにより、メッセージが、関連するサブスクライバーで収集できる状態にします。</span><span class="sxs-lookup"><span data-stu-id="3123e-103"> automatically publishes messages arriving through a receive pipeline to the Message Box database; this makes the messages ready for pick-up by the relevant subscriber.</span></span> <span data-ttu-id="3123e-104">この分離方法は、最大限の柔軟性を提供のスケールを設定し、発行を使用しているために、BizTalk ソリューションを開発することをお勧めのメカニズムをサブスクライブします。</span><span class="sxs-lookup"><span data-stu-id="3123e-104">This decoupled approach is the preferred way to develop BizTalk solutions because it provides maximum flexibility, scales well, and uses the publish-subscribe mechanism.</span></span>  
  
 <span data-ttu-id="3123e-105">2 つの方法でサブスクライバーを itinerary サービスを作成するにがあります。</span><span class="sxs-lookup"><span data-stu-id="3123e-105">There are two ways to create an itinerary service subscriber:</span></span>  
  
-   [<span data-ttu-id="3123e-106">Itinerary サービス サブスクライバーとして、送信ポートを使用します。</span><span class="sxs-lookup"><span data-stu-id="3123e-106">Using a Send Port as an Itinerary Service Subscriber</span></span>](../esb-toolkit/using-a-send-port-as-an-itinerary-service-subscriber.md)  
  
-   [<span data-ttu-id="3123e-107">Itinerary サービス サブスクライバーとして、オーケストレーションを使用します。</span><span class="sxs-lookup"><span data-stu-id="3123e-107">Using an Orchestration as an Itinerary Service Subscriber</span></span>](../esb-toolkit/using-an-orchestration-as-an-itinerary-service-subscriber.md)