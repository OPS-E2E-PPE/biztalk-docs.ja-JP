---
title: スケジュールに基づくルーティング |Microsoft Docs
ms.custom: ''
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: ''
ms.suite: ''
ms.tgt_pltfrm: ''
ms.topic: article
ms.assetid: 28028721-798c-4302-a532-d863ed8ea88b
caps.latest.revision: 2
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: fe1132920b18cc331786d515b916de2861409339
ms.sourcegitcommit: 381e83d43796a345488d54b3f7413e11d56ad7be
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 05/07/2019
ms.locfileid: "65261561"
---
# <a name="itinerary-based-routing"></a><span data-ttu-id="b56d2-102">スケジュールに基づくルーティング</span><span class="sxs-lookup"><span data-stu-id="b56d2-102">Itinerary-Based Routing</span></span>
<span data-ttu-id="b56d2-103">コア機能の 1 つ、[!INCLUDE[esbToolkit](../includes/esbtoolkit-md.md)]はエンタープライズ レベルのメッセージング アプリケーションの開発を簡略化し、多数の静的なを維持するためのコストを削減するスケジュールに基づくルーティングのプロビジョニングは送信ポートと受信場所。</span><span class="sxs-lookup"><span data-stu-id="b56d2-103">One of the core features of the [!INCLUDE[esbToolkit](../includes/esbtoolkit-md.md)] is the provision of itinerary-based routing that simplifies the development of enterprise-level messaging applications and reduces the costs of maintaining a large number of static send ports and receive locations.</span></span>  
  
 <span data-ttu-id="b56d2-104">スケジュールは、(これは、ルーティング、変換、およびカスタムのサービスを含めることができます) を実行するサービスの一覧と、これらの各サービスを実行するために必要なメタデータの解決に必要な構成情報で構成されます。</span><span class="sxs-lookup"><span data-stu-id="b56d2-104">An itinerary consists of the list of services to execute (which can contain routing, transformation, and custom services) and the configuration information required to resolve the metadata necessary to execute each of these services.</span></span> <span data-ttu-id="b56d2-105">たとえば、旅行プランの 1 つの段階にルーティング サービスを可能性があります。このサービスに関連付けられた解決手順はルーティングは、特定のターゲット エンドポイントについては、Universal Description、検出、および Integration (UDDI) またはビジネス ルール エンジン (BRE) を参照するサービスを指示可能性があります。メッセージ。</span><span class="sxs-lookup"><span data-stu-id="b56d2-105">For example, one stage of the itinerary may be a routing service; the resolution instructions associated with this service may instruct the service to perform a Universal Description, Discovery, and Integration (UDDI) or Business Rules Engine (BRE) lookup for information about a specific target endpoint to which it will route the message.</span></span>  
  
 <span data-ttu-id="b56d2-106">スケジュールは、次の方法で受信メッセージに添付できます。</span><span class="sxs-lookup"><span data-stu-id="b56d2-106">Itineraries can be attached to an inbound message in the following ways:</span></span>  
  
- <span data-ttu-id="b56d2-107">クライアントによって送信されたメッセージでは、スケジュールに関連するデータは含まれません。</span><span class="sxs-lookup"><span data-stu-id="b56d2-107">The message submitted by a client does not contain any itinerary-related data.</span></span> <span data-ttu-id="b56d2-108">受信パイプラインを解決するには、取得、およびメッセージの内容またはコンテキストに基づいて適切なスケジュールをアタッチします。</span><span class="sxs-lookup"><span data-stu-id="b56d2-108">The receiving pipeline resolves, retrieves, and attaches the appropriate itinerary based on message content or context.</span></span>  
  
- <span data-ttu-id="b56d2-109">クライアントによって送信されたメッセージは、スケジュールの名前とバージョン、さらにビジネス アクティビティ監視 (BAM) 追跡の一意の識別子を含むスケジュールの参照データを定義する SOAP ヘッダーを含めることができます。</span><span class="sxs-lookup"><span data-stu-id="b56d2-109">The message submitted by a client can contain a SOAP header that defines the itinerary reference data, which contains the itinerary name and version, as well as a unique identifier for Business Activity Monitoring (BAM) tracking.</span></span> <span data-ttu-id="b56d2-110">受信パイプラインは、この情報を評価し、ESBItineraryDb データベースから適切な旅行プランを取得します。</span><span class="sxs-lookup"><span data-stu-id="b56d2-110">The receiving pipeline evaluates this information and retrieves the appropriate itinerary from the ESBItineraryDb database.</span></span>  
  
- <span data-ttu-id="b56d2-111">クライアントによって送信されたメッセージは、旅行計画の内容全体が含まれていますの itinerary SOAP ヘッダーを持つことができます。</span><span class="sxs-lookup"><span data-stu-id="b56d2-111">The message submitted by a client can have an itinerary SOAP header, which contains the entire content of the itinerary.</span></span> <span data-ttu-id="b56d2-112">この設計は推奨されませんし、テスト目的でのみ使用する必要があります。</span><span class="sxs-lookup"><span data-stu-id="b56d2-112">This design is not recommended and should be used only for testing purposes.</span></span>  
  
  <span data-ttu-id="b56d2-113">日程が受信メッセージの解決された後、受信パイプラインをスケジュールのデータへのアクセスがこのメッセージをサブスクライブする Microsoft BizTalk Server コンポーネントを使用できるプロパティをそれによって、メッセージ コンテキストに昇格させます。</span><span class="sxs-lookup"><span data-stu-id="b56d2-113">After an itinerary is resolved for an inbound message, the receive pipeline promotes the itinerary data to the message context, thereby making the properties available to be accessed by any Microsoft BizTalk Server component that subscribes to this message.</span></span> <span data-ttu-id="b56d2-114">BizTalk Server コンポーネントはスケジュールの現在のステップの詳細を取得、必要な処理を完了または旅行プランを次の手順に進みます。</span><span class="sxs-lookup"><span data-stu-id="b56d2-114">BizTalk Server components can obtain details of the current itinerary step, complete the required processing, and/or advance the itinerary to the next step.</span></span> <span data-ttu-id="b56d2-115">に従って、発行、メッセージを処理するスケジュールで次のサービスこれにより、BizTalk Server の機能をサブスクライブします。</span><span class="sxs-lookup"><span data-stu-id="b56d2-115">This causes the next service in the itinerary to process the message, according to the publish-subscribe functionality of BizTalk Server.</span></span>  
  
  <span data-ttu-id="b56d2-116">ESB の動的な解決メカニズム、変換、スケジュールの処理、およびメッセージの作成については、次を参照してください。[主要なシナリオおよび開発タスク](../esb-toolkit/key-scenarios-and-development-tasks.md)します。</span><span class="sxs-lookup"><span data-stu-id="b56d2-116">For information about the ESB dynamic resolution mechanism, transformations, itinerary processing, and message creation, see [Key Scenarios and Development Tasks](../esb-toolkit/key-scenarios-and-development-tasks.md).</span></span>