---
title: "ESB Itinerary セレクター コンポーネント |Microsoft ドキュメント"
ms.custom: 
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: 
ms.suite: 
ms.tgt_pltfrm: 
ms.topic: article
ms.assetid: c2cd8a85-e036-4817-9541-3fd720ca04ef
caps.latest.revision: "3"
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: c83cdd0b2022eb7dc4ad78e5702f5c21e4c4f432
ms.sourcegitcommit: cb908c540d8f1a692d01dc8f313e16cb4b4e696d
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 09/20/2017
---
# <a name="the-esb-itinerary-selector-component"></a><span data-ttu-id="3df11-102">ESB Itinerary セレクター コンポーネント</span><span class="sxs-lookup"><span data-stu-id="3df11-102">The ESB Itinerary Selector Component</span></span>
<span data-ttu-id="3df11-103">ESB 行程セレクター コンポーネントには、行程をによる競合回避モジュールのヘルプ メッセージの適切なサーバー側日程を選択すると、ESB を通過する SOAP ヘッダーがない入力方向のメッセージが可能です。</span><span class="sxs-lookup"><span data-stu-id="3df11-103">The ESB Itinerary Selector component allows incoming messages that do not have the itinerary SOAP header to pass through the ESB by selecting an appropriate server-side itinerary for the message with the help of a resolver.</span></span> <span data-ttu-id="3df11-104">コンポーネントは、クライアントによって要求されるとおり、名前と、日程のバージョンを定義する SOAP ヘッダーを使用するメッセージも使用されます。</span><span class="sxs-lookup"><span data-stu-id="3df11-104">The component is also used for messages that use a SOAP header to define the name and version of an itinerary, as requested by the client.</span></span>  
  
## <a name="installation"></a><span data-ttu-id="3df11-105">インストール</span><span class="sxs-lookup"><span data-stu-id="3df11-105">Installation</span></span>  
 <span data-ttu-id="3df11-106">ESB コアを自動的にインストールするとインストール、 **ItinerarySelector**コンポーネントを BizTalk Server パイプライン コンポーネント フォルダーでします。</span><span class="sxs-lookup"><span data-stu-id="3df11-106">Installing the ESB Core automatically installs the **ItinerarySelector** component in the BizTalk Server Pipeline Components folder.</span></span>  
  
## <a name="how-it-works"></a><span data-ttu-id="3df11-107">しくみ</span><span class="sxs-lookup"><span data-stu-id="3df11-107">How It Works</span></span>  
 <span data-ttu-id="3df11-108">ESB 行程セレクター コンポーネントは、受信パイプラインにのみ存在でく Microsoft BizTalk パイプライン コンポーネントです。</span><span class="sxs-lookup"><span data-stu-id="3df11-108">The ESB Itinerary Selector component is a Microsoft BizTalk pipeline component that can reside only in a receive pipeline.</span></span> <span data-ttu-id="3df11-109">コンポーネントは、メッセージの処理に使用するためのサーバー側旅程を選択します。</span><span class="sxs-lookup"><span data-stu-id="3df11-109">The component selects a server-side itinerary for use in processing a message.</span></span> <span data-ttu-id="3df11-110">コンポーネントがその構成を読み取り、使用して、メッセージが受信パイプラインのコンポーネントを通過するよう、 **ResolverConnectionString**を呼び出すときに使用する適切な旅程を検索する正しい競合回避モジュールのプロパティメッセージを処理しています。</span><span class="sxs-lookup"><span data-stu-id="3df11-110">As the message passes through the component in a receive pipeline, the component reads its configuration and uses the **ResolverConnectionString** property to call the correct resolver to look up the appropriate itinerary to use when processing the message.</span></span> <span data-ttu-id="3df11-111">行程セレクター コンポーネントは、メッセージを検証し、メッセージは、次の処理ステージを続けるようにするために必要なプロパティを昇格させる行程パイプライン コンポーネントと同じ手順を実行します。</span><span class="sxs-lookup"><span data-stu-id="3df11-111">The Itinerary Selector component then performs the same steps as the Itinerary pipeline component to validate the message and promote the properties necessary to ensure the message continues to the next processing stage.</span></span>  
  
## <a name="using-the-esb-itinerary-selector-component"></a><span data-ttu-id="3df11-112">ESB Itinerary セレクター コンポーネントを使用します。</span><span class="sxs-lookup"><span data-stu-id="3df11-112">Using the ESB Itinerary Selector Component</span></span>  
 <span data-ttu-id="3df11-113">ESB 行程コンポーネントは、受信パイプラインに追加し、受信場所、パイプラインを使用できます。</span><span class="sxs-lookup"><span data-stu-id="3df11-113">You can add the ESB Itinerary component to a receive pipeline and then use the pipeline in a receive location.</span></span> <span data-ttu-id="3df11-114">WCF 入り口、名前とバージョン (SOAP ヘッダーで表される) ように、クライアントによって要求された行程の日程静的リゾルバーでのこのコンポーネントを構成するとき、メッセージ コンテキストから取得され、適切な選択に使用行程です。</span><span class="sxs-lookup"><span data-stu-id="3df11-114">When this component is configured with the ITINERARY-STATIC resolver in WCF on-ramp, the name and version of the itinerary requested by the client (as represented in the SOAP header) will be retrieved from the message context and used to select the appropriate itinerary.</span></span>  
  
## <a name="component-properties"></a><span data-ttu-id="3df11-115">コンポーネント プロパティ</span><span class="sxs-lookup"><span data-stu-id="3df11-115">Component Properties</span></span>  
 <span data-ttu-id="3df11-116">ESB 行程セレクター コンポーネントは、次の 3 つのパブリック プロパティを公開します。</span><span class="sxs-lookup"><span data-stu-id="3df11-116">The ESB Itinerary Selector component exposes three public properties:</span></span>  
  
-   <span data-ttu-id="3df11-117">**IgnoreErrorKey**です。</span><span class="sxs-lookup"><span data-stu-id="3df11-117">**IgnoreErrorKey**.</span></span> <span data-ttu-id="3df11-118">このプロパティは定義かどうか、競合回避モジュールでエラーが返される場合は、メッセージの処理、行程なし (に設定すると**True**) または中断しています。</span><span class="sxs-lookup"><span data-stu-id="3df11-118">This property defines whether, if an error is returned by the resolver, the message should be processed without the itinerary (when set to **True**) or suspended.</span></span>  
  
-   <span data-ttu-id="3df11-119">**ItineraryFactKey**です。</span><span class="sxs-lookup"><span data-stu-id="3df11-119">**ItineraryFactKey**.</span></span> <span data-ttu-id="3df11-120">これは、選択した日程の実際の XML を含む競合回避モジュールによって返されたディクショナリのキーを表します。</span><span class="sxs-lookup"><span data-stu-id="3df11-120">This represents the key in the dictionary returned by the resolver that contains the actual XML of the Itinerary selected.</span></span> <span data-ttu-id="3df11-121">一般に、 **Resolver.Itinerary**カスタム競合回避モジュールを使用しない場合、します。</span><span class="sxs-lookup"><span data-stu-id="3df11-121">Generally, **Resolver.Itinerary**, unless a custom resolver is used.</span></span>  
  
-   <span data-ttu-id="3df11-122">**ResolverConnectionString**です。</span><span class="sxs-lookup"><span data-stu-id="3df11-122">**ResolverConnectionString**.</span></span> <span data-ttu-id="3df11-123">これは、競合回避モジュールを使用して選択する名前と値のペアを含む競合回避モジュールの接続文字列やルックアップ日程です。</span><span class="sxs-lookup"><span data-stu-id="3df11-123">This is a resolver connection string that contains name-value pairs that a resolver can use to select and/or look-up an itinerary.</span></span>