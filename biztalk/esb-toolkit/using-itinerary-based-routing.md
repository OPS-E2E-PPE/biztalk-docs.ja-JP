---
title: スケジュールに基づくルーティングを使用して |Microsoft Docs
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
ms.openlocfilehash: 4adcb32367a42403e769111f7b3d3d343c604671
ms.sourcegitcommit: 266308ec5c6a9d8d80ff298ee6051b4843c5d626
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 06/27/2018
ms.locfileid: "36978691"
---
# <a name="using-itinerary-based-routing"></a><span data-ttu-id="49f4d-102">スケジュールに基づくルーティングを使用します。</span><span class="sxs-lookup"><span data-stu-id="49f4d-102">Using Itinerary-Based Routing</span></span>
<span data-ttu-id="49f4d-103">[!INCLUDE[esbToolkit](../includes/esbtoolkit-md.md)]スケジュールに基づくメッセージのルーティング シナリオを有効にすると、特定のメッセージの処理のシーケンスのステップに回覧用紙がパターンを実装することでデザイン時に認識できないため、メッセージごとに異なる場合がありますを提供します。</span><span class="sxs-lookup"><span data-stu-id="49f4d-103">The [!INCLUDE[esbToolkit](../includes/esbtoolkit-md.md)] provides itinerary-based message routing by implementing the Routing Slip pattern to enable scenarios when the sequence of processing steps for a particular message is not known at design time and may vary for each message.</span></span> <span data-ttu-id="49f4d-104">このパターンの実装では、ルーティング スリップを使用して、XML 形式でこれらの手順のコレクションを表現するし、どの手順が実行時に発生する必要がありますを決定します。</span><span class="sxs-lookup"><span data-stu-id="49f4d-104">The implementation of this pattern uses a routing slip to represent a collection of these steps in XML format and determines which steps need to occur during at run time.</span></span> <span data-ttu-id="49f4d-105">「ESB 行程」と呼ばれる頻繁に回覧用紙の状態は、手順は、によって処理されるメッセージに対して実行する必要がありますを定義する宣言型の命令の順序付けされたセット[!INCLUDE[esbToolkit](../includes/esbtoolkit-md.md)]コンポーネントと BizTalk Server ランタイム。</span><span class="sxs-lookup"><span data-stu-id="49f4d-105">A state of the routing slip, frequently referred to as an "ESB itinerary," is an ordered set of declarative instructions that define the steps that must be executed for a message as it is being processed by [!INCLUDE[esbToolkit](../includes/esbtoolkit-md.md)] components and the BizTalk Server runtime.</span></span> <span data-ttu-id="49f4d-106">ESB スケジュールで指定された特定の処理命令が関連付けられている、[!INCLUDE[esbToolkit](../includes/esbtoolkit-md.md)]コンポーネントで、「ESB スケジュール サービス」ですとも呼ばれます。</span><span class="sxs-lookup"><span data-stu-id="49f4d-106">A particular processing instruction specified in ESB itinerary is associated with the [!INCLUDE[esbToolkit](../includes/esbtoolkit-md.md)] component, which is also referred to as the "ESB itinerary service."</span></span> <span data-ttu-id="49f4d-107">ESB スケジュール サービスの目的は、処理命令を実行し、回覧先を示す次の命令の待機中の状態を更新するには。</span><span class="sxs-lookup"><span data-stu-id="49f4d-107">The purpose of the ESB itinerary service is to execute the processing instructions and to update the state of the routing slip to indicate the next pending instruction.</span></span>  

 <span data-ttu-id="49f4d-108">このセクションの処理のスケジュールに基づく機能を説明します、[!INCLUDE[esbToolkit](../includes/esbtoolkit-md.md)]します。</span><span class="sxs-lookup"><span data-stu-id="49f4d-108">This section describes the itinerary-based processing features of the [!INCLUDE[esbToolkit](../includes/esbtoolkit-md.md)].</span></span> <span data-ttu-id="49f4d-109">ここで説明する内容は次のとおりです。</span><span class="sxs-lookup"><span data-stu-id="49f4d-109">It contains the following topics:</span></span>  

- [<span data-ttu-id="49f4d-110">ESB スケジュール管理</span><span class="sxs-lookup"><span data-stu-id="49f4d-110">ESB Itinerary Management</span></span>](../esb-toolkit/esb-itinerary-management.md)  

- [<span data-ttu-id="49f4d-111">オンランプとオフランプ</span><span class="sxs-lookup"><span data-stu-id="49f4d-111">On-Ramps and Off-Ramps</span></span>](../esb-toolkit/on-ramps-and-off-ramps.md)  

- [<span data-ttu-id="49f4d-112">スケジュール サービスとしてメッセージングかオーケストレーションを選択する</span><span class="sxs-lookup"><span data-stu-id="49f4d-112">Choosing Between Messaging and Orchestration Itinerary Services</span></span>](../esb-toolkit/choosing-between-messaging-and-orchestration-itinerary-services.md)  

- [<span data-ttu-id="49f4d-113">パイプライン コンポーネントを利用し、既存のスケジュールを選択する</span><span class="sxs-lookup"><span data-stu-id="49f4d-113">Using a Pipeline Component to Select an Existing Itinerary</span></span>](../esb-toolkit/using-a-pipeline-component-to-select-an-existing-itinerary.md)  

- [<span data-ttu-id="49f4d-114">パイプライン コンポーネントを利用し、スケジュールを読み取る</span><span class="sxs-lookup"><span data-stu-id="49f4d-114">Using a Pipeline Component to Read an Itinerary</span></span>](../esb-toolkit/using-a-pipeline-component-to-read-an-itinerary.md)  

- [<span data-ttu-id="49f4d-115">パイプライン コンポーネントを利用し、送信請求 - 応答のスケジュールをキャッシュする</span><span class="sxs-lookup"><span data-stu-id="49f4d-115">Using a Pipeline Component to Cache an Itinerary for Solicit-Response</span></span>](../esb-toolkit/using-a-pipeline-component-to-cache-an-itinerary-for-solicit-response.md)  

- [<span data-ttu-id="49f4d-116">スケジュール サブスクライバーを作成する</span><span class="sxs-lookup"><span data-stu-id="49f4d-116">Creating Itinerary Subscribers</span></span>](../esb-toolkit/creating-itinerary-subscribers.md)  

- [<span data-ttu-id="49f4d-117">スケジュール サービスを実行する</span><span class="sxs-lookup"><span data-stu-id="49f4d-117">Executing an Itinerary Service</span></span>](../esb-toolkit/executing-an-itinerary-service.md)  

- <span data-ttu-id="49f4d-118">HYPERLINK"<http://msdn.microsoft.com/library/ee236752(BTS.10).aspx>"[スケジュールに基づくルーティング アイテム](../esb-toolkit/itinerary-based-routing-artifacts.md)</span><span class="sxs-lookup"><span data-stu-id="49f4d-118">HYPERLINK "<http://msdn.microsoft.com/library/ee236752(BTS.10).aspx>" [Itinerary-Based Routing Artifacts](../esb-toolkit/itinerary-based-routing-artifacts.md)</span></span>
