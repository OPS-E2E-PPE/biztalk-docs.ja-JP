---
title: 行程ベースのルーティングを使用して |Microsoft ドキュメント
ms.custom: ''
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: ''
ms.suite: ''
ms.tgt_pltfrm: ''
ms.topic: article
ms.assetid: 1d5b5d13-cbf2-4f3c-8a1a-3bb852f048a0
caps.latest.revision: 3
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: 9a0e0dad0f49e07c0941614dd0130d0e77c459ab
ms.sourcegitcommit: 3371ffd8ceca02e2b3715d53a1e0c0a59045912e
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 06/07/2018
ms.locfileid: "34848986"
---
# <a name="using-itinerary-based-routing"></a><span data-ttu-id="848f5-102">行程ベースのルーティングを使用します。</span><span class="sxs-lookup"><span data-stu-id="848f5-102">Using Itinerary-Based Routing</span></span>
<span data-ttu-id="848f5-103">[!INCLUDE[esbToolkit](../includes/esbtoolkit-md.md)]行程ベースのメッセージのルーティングを特定のメッセージの処理のシーケンスのステップとシナリオを有効にする回覧パターンを実装することによってデザイン時に認識できないため、メッセージごとに異なる場合がありますを提供します。</span><span class="sxs-lookup"><span data-stu-id="848f5-103">The [!INCLUDE[esbToolkit](../includes/esbtoolkit-md.md)] provides itinerary-based message routing by implementing the Routing Slip pattern to enable scenarios when the sequence of processing steps for a particular message is not known at design time and may vary for each message.</span></span> <span data-ttu-id="848f5-104">このパターンの実装では、ルーティング スリップを使用して、XML 形式でこれらの手順のコレクションを表現するし、どの手順が実行時に発生する必要がありますを決定します。</span><span class="sxs-lookup"><span data-stu-id="848f5-104">The implementation of this pattern uses a routing slip to represent a collection of these steps in XML format and determines which steps need to occur during at run time.</span></span> <span data-ttu-id="848f5-105">「ESB 行程」として頻繁に参照回覧の状態は、によって処理されるメッセージに対して実行する必要がありますの手順を定義する宣言型の命令の順序付きセットは、[!INCLUDE[esbToolkit](../includes/esbtoolkit-md.md)]コンポーネントと、BizTalk Server ランタイム。</span><span class="sxs-lookup"><span data-stu-id="848f5-105">A state of the routing slip, frequently referred to as an "ESB itinerary," is an ordered set of declarative instructions that define the steps that must be executed for a message as it is being processed by [!INCLUDE[esbToolkit](../includes/esbtoolkit-md.md)] components and the BizTalk Server runtime.</span></span> <span data-ttu-id="848f5-106">ESB 行程で指定された特定の処理命令に関連付けられている、[!INCLUDE[esbToolkit](../includes/esbtoolkit-md.md)]コンポーネントであり、「ESB itinerary サービスです」とも呼びますが、。</span><span class="sxs-lookup"><span data-stu-id="848f5-106">A particular processing instruction specified in ESB itinerary is associated with the [!INCLUDE[esbToolkit](../includes/esbtoolkit-md.md)] component, which is also referred to as the "ESB itinerary service."</span></span> <span data-ttu-id="848f5-107">ESB itinerary サービスの目的は、処理命令を実行し、回覧を示す次の命令の待機中の状態を更新します。</span><span class="sxs-lookup"><span data-stu-id="848f5-107">The purpose of the ESB itinerary service is to execute the processing instructions and to update the state of the routing slip to indicate the next pending instruction.</span></span>  
  
 <span data-ttu-id="848f5-108">このセクションの日程ベースの処理機能の説明、[!INCLUDE[esbToolkit](../includes/esbtoolkit-md.md)]です。</span><span class="sxs-lookup"><span data-stu-id="848f5-108">This section describes the itinerary-based processing features of the [!INCLUDE[esbToolkit](../includes/esbtoolkit-md.md)].</span></span> <span data-ttu-id="848f5-109">ここで説明する内容は次のとおりです。</span><span class="sxs-lookup"><span data-stu-id="848f5-109">It contains the following topics:</span></span>  
  
-   [<span data-ttu-id="848f5-110">ESB スケジュール管理</span><span class="sxs-lookup"><span data-stu-id="848f5-110">ESB Itinerary Management</span></span>](../esb-toolkit/esb-itinerary-management.md)  
  
-   [<span data-ttu-id="848f5-111">オンランプとオフランプ</span><span class="sxs-lookup"><span data-stu-id="848f5-111">On-Ramps and Off-Ramps</span></span>](../esb-toolkit/on-ramps-and-off-ramps.md)  
  
-   [<span data-ttu-id="848f5-112">スケジュール サービスとしてメッセージングかオーケストレーションを選択する</span><span class="sxs-lookup"><span data-stu-id="848f5-112">Choosing Between Messaging and Orchestration Itinerary Services</span></span>](../esb-toolkit/choosing-between-messaging-and-orchestration-itinerary-services.md)  
  
-   [<span data-ttu-id="848f5-113">パイプライン コンポーネントを利用し、既存のスケジュールを選択する</span><span class="sxs-lookup"><span data-stu-id="848f5-113">Using a Pipeline Component to Select an Existing Itinerary</span></span>](../esb-toolkit/using-a-pipeline-component-to-select-an-existing-itinerary.md)  
  
-   [<span data-ttu-id="848f5-114">パイプライン コンポーネントを利用し、スケジュールを読み取る</span><span class="sxs-lookup"><span data-stu-id="848f5-114">Using a Pipeline Component to Read an Itinerary</span></span>](../esb-toolkit/using-a-pipeline-component-to-read-an-itinerary.md)  
  
-   [<span data-ttu-id="848f5-115">パイプライン コンポーネントを利用し、送信請求 - 応答のスケジュールをキャッシュする</span><span class="sxs-lookup"><span data-stu-id="848f5-115">Using a Pipeline Component to Cache an Itinerary for Solicit-Response</span></span>](../esb-toolkit/using-a-pipeline-component-to-cache-an-itinerary-for-solicit-response.md)  
  
-   [<span data-ttu-id="848f5-116">スケジュール サブスクライバーを作成する</span><span class="sxs-lookup"><span data-stu-id="848f5-116">Creating Itinerary Subscribers</span></span>](../esb-toolkit/creating-itinerary-subscribers.md)  
  
-   [<span data-ttu-id="848f5-117">スケジュール サービスを実行する</span><span class="sxs-lookup"><span data-stu-id="848f5-117">Executing an Itinerary Service</span></span>](../esb-toolkit/executing-an-itinerary-service.md)  
  
-   <span data-ttu-id="848f5-118">ハイパーリンク"http://msdn.microsoft.com/library/ee236752(BTS.10).aspx"[行程ベースのルーティング コンポーネント](../esb-toolkit/itinerary-based-routing-artifacts.md)</span><span class="sxs-lookup"><span data-stu-id="848f5-118">HYPERLINK "http://msdn.microsoft.com/library/ee236752(BTS.10).aspx" [Itinerary-Based Routing Artifacts](../esb-toolkit/itinerary-based-routing-artifacts.md)</span></span>