---
title: スケジュール サブスクライバーを作成する |Microsoft Docs
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
ms.openlocfilehash: 2998b47ec136414af896cadb40b8336fe41ef2ae
ms.sourcegitcommit: 381e83d43796a345488d54b3f7413e11d56ad7be
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 05/07/2019
ms.locfileid: "65394671"
---
# <a name="creating-itinerary-subscribers"></a><span data-ttu-id="aebac-102">スケジュール サブスクライバーを作成します。</span><span class="sxs-lookup"><span data-stu-id="aebac-102">Creating Itinerary Subscribers</span></span>
<span data-ttu-id="aebac-103">BizTalk Server 受信パイプライン経由でメッセージ ボックス データベースに到着するメッセージを自動的に公開します。これにより、メッセージは、関連するサブスクライバーの乗車の準備ができています。</span><span class="sxs-lookup"><span data-stu-id="aebac-103">BizTalk Server automatically publishes messages arriving through a receive pipeline to the Message Box database; this makes the messages ready for pick-up by the relevant subscriber.</span></span> <span data-ttu-id="aebac-104">この減結合アプローチは、最大限の柔軟性を提供します、適切にスケールし、発行を使用するために、BizTalk ソリューションを開発することをお勧めのメカニズムをサブスクライブします。</span><span class="sxs-lookup"><span data-stu-id="aebac-104">This decoupled approach is the preferred way to develop BizTalk solutions because it provides maximum flexibility, scales well, and uses the publish-subscribe mechanism.</span></span>  
  
 <span data-ttu-id="aebac-105">スケジュール サービス サブスクライバーで作成する 2 つの方法はあります。</span><span class="sxs-lookup"><span data-stu-id="aebac-105">There are two ways to create an itinerary service subscriber:</span></span>  
  
-   [<span data-ttu-id="aebac-106">スケジュール サービス サブスクライバーとして送信ポートを利用する</span><span class="sxs-lookup"><span data-stu-id="aebac-106">Using a Send Port as an Itinerary Service Subscriber</span></span>](../esb-toolkit/using-a-send-port-as-an-itinerary-service-subscriber.md)  
  
-   [<span data-ttu-id="aebac-107">スケジュール サービス サブスクライバーとしてオーケストレーションを利用する</span><span class="sxs-lookup"><span data-stu-id="aebac-107">Using an Orchestration as an Itinerary Service Subscriber</span></span>](../esb-toolkit/using-an-orchestration-as-an-itinerary-service-subscriber.md)