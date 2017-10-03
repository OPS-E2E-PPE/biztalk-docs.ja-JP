---
title: "行程ベースのルーティング |Microsoft ドキュメント"
ms.custom: 
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: 
ms.suite: 
ms.tgt_pltfrm: 
ms.topic: article
ms.assetid: 28028721-798c-4302-a532-d863ed8ea88b
caps.latest.revision: "2"
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: 1fbfe8877202a2f691bd30fd2b56fc3032240ee9
ms.sourcegitcommit: cb908c540d8f1a692d01dc8f313e16cb4b4e696d
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 09/20/2017
---
# <a name="itinerary-based-routing"></a><span data-ttu-id="32d86-102">行程ベースのルーティング</span><span class="sxs-lookup"><span data-stu-id="32d86-102">Itinerary-Based Routing</span></span>
<span data-ttu-id="32d86-103">コア機能の 1 つ、[!INCLUDE[esbToolkit](../includes/esbtoolkit-md.md)]はエンタープライズ レベルのメッセージング アプリケーションの開発を簡略化し、多数の静的なを維持するためのコストを削減する行程ベースのルーティングのプロビジョニングの送信ポートと受信場所。</span><span class="sxs-lookup"><span data-stu-id="32d86-103">One of the core features of the [!INCLUDE[esbToolkit](../includes/esbtoolkit-md.md)] is the provision of itinerary-based routing that simplifies the development of enterprise-level messaging applications and reduces the costs of maintaining a large number of static send ports and receive locations.</span></span>  
  
 <span data-ttu-id="32d86-104">(これは、ルーティング、変換、およびカスタムのサービスを含めることができます) を実行するサービスの一覧および各サービスの実行に必要なメタデータを解決するのには必要な構成情報の日程で構成されます。</span><span class="sxs-lookup"><span data-stu-id="32d86-104">An itinerary consists of the list of services to execute (which can contain routing, transformation, and custom services) and the configuration information required to resolve the metadata necessary to execute each of these services.</span></span> <span data-ttu-id="32d86-105">たとえば、旅行計画の 1 つの段階は、ルーティング サービス可能性があります。このサービスに関連付けられている解像度の手順については、特定のターゲット エンドポイントはルーティング Universal Description、検出、および Integration (UDDI) またはビジネス ルール エンジン (BRE) を参照するサービスを指示可能性があります。メッセージ。</span><span class="sxs-lookup"><span data-stu-id="32d86-105">For example, one stage of the itinerary may be a routing service; the resolution instructions associated with this service may instruct the service to perform a Universal Description, Discovery, and Integration (UDDI) or Business Rules Engine (BRE) lookup for information about a specific target endpoint to which it will route the message.</span></span>  
  
 <span data-ttu-id="32d86-106">行程は、次のように、受信メッセージに添付できます。</span><span class="sxs-lookup"><span data-stu-id="32d86-106">Itineraries can be attached to an inbound message in the following ways:</span></span>  
  
-   <span data-ttu-id="32d86-107">クライアントによって送信されるメッセージに行程に関連するデータが含まれていません。</span><span class="sxs-lookup"><span data-stu-id="32d86-107">The message submitted by a client does not contain any itinerary-related data.</span></span> <span data-ttu-id="32d86-108">受信パイプラインを解決するには、取得、およびメッセージの内容またはコンテキストに基づいて適切な旅程をアタッチします。</span><span class="sxs-lookup"><span data-stu-id="32d86-108">The receiving pipeline resolves, retrieves, and attaches the appropriate itinerary based on message content or context.</span></span>  
  
-   <span data-ttu-id="32d86-109">クライアントによって送信されるメッセージには、ビジネス アクティビティ監視 (BAM) 追跡の一意の識別子だけでなく、itinerary 名とバージョンを含む itinerary 参照データを定義する SOAP ヘッダーを含めることができます。</span><span class="sxs-lookup"><span data-stu-id="32d86-109">The message submitted by a client can contain a SOAP header that defines the itinerary reference data, which contains the itinerary name and version, as well as a unique identifier for Business Activity Monitoring (BAM) tracking.</span></span> <span data-ttu-id="32d86-110">受信パイプラインは、この情報を評価し、ESBItineraryDb データベースから適切な旅程を取得します。</span><span class="sxs-lookup"><span data-stu-id="32d86-110">The receiving pipeline evaluates this information and retrieves the appropriate itinerary from the ESBItineraryDb database.</span></span>  
  
-   <span data-ttu-id="32d86-111">クライアントによって送信されるメッセージには、旅行計画の内容全体を含む itinerary は SOAP ヘッダーを持つことができます。</span><span class="sxs-lookup"><span data-stu-id="32d86-111">The message submitted by a client can have an itinerary SOAP header, which contains the entire content of the itinerary.</span></span> <span data-ttu-id="32d86-112">この設計はお勧めできませんテスト目的でのみ使用する必要があります。</span><span class="sxs-lookup"><span data-stu-id="32d86-112">This design is not recommended and should be used only for testing purposes.</span></span>  
  
 <span data-ttu-id="32d86-113">日程が受信メッセージの解決した後、受信パイプラインは itinerary データにこのメッセージをサブスクライブする任意の Microsoft BizTalk Server コンポーネントがアクセスして使用可能なプロパティをし、それによって、メッセージ コンテキストに昇格させます。</span><span class="sxs-lookup"><span data-stu-id="32d86-113">After an itinerary is resolved for an inbound message, the receive pipeline promotes the itinerary data to the message context, thereby making the properties available to be accessed by any Microsoft BizTalk Server component that subscribes to this message.</span></span> <span data-ttu-id="32d86-114">BizTalk Server コンポーネントでは、現在の itinerary ステップの詳細を取得、必要な処理を完了、および次の手順に旅行計画を進めることができます。</span><span class="sxs-lookup"><span data-stu-id="32d86-114">BizTalk Server components can obtain details of the current itinerary step, complete the required processing, and/or advance the itinerary to the next step.</span></span> <span data-ttu-id="32d86-115">これにより、次のサービス内、メッセージの処理に旅行計画に従って、発行-BizTalk Server の機能をサブスクライブします。</span><span class="sxs-lookup"><span data-stu-id="32d86-115">This causes the next service in the itinerary to process the message, according to the publish-subscribe functionality of BizTalk Server.</span></span>  
  
 <span data-ttu-id="32d86-116">ESB の動的な解決メカニズム、変換、itinerary の処理、およびメッセージの作成については、次を参照してください。[主要なシナリオと開発タスク](../esb-toolkit/key-scenarios-and-development-tasks.md)です。</span><span class="sxs-lookup"><span data-stu-id="32d86-116">For information about the ESB dynamic resolution mechanism, transformations, itinerary processing, and message creation, see [Key Scenarios and Development Tasks](../esb-toolkit/key-scenarios-and-development-tasks.md).</span></span>