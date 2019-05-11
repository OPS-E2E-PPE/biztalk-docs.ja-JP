---
title: ESB スケジュール セレクター コンポーネント |Microsoft Docs
ms.custom: ''
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: ''
ms.suite: ''
ms.tgt_pltfrm: ''
ms.topic: article
ms.assetid: c2cd8a85-e036-4817-9541-3fd720ca04ef
caps.latest.revision: 3
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: fcce1fb4ab067e4620bbbca9134e5ac5f5c58889
ms.sourcegitcommit: 381e83d43796a345488d54b3f7413e11d56ad7be
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 05/07/2019
ms.locfileid: "65399770"
---
# <a name="the-esb-itinerary-selector-component"></a><span data-ttu-id="02922-102">ESB スケジュール セレクター コンポーネント</span><span class="sxs-lookup"><span data-stu-id="02922-102">The ESB Itinerary Selector Component</span></span>
<span data-ttu-id="02922-103">ESB スケジュール セレクター コンポーネントは、旅行プランの競合回避モジュールのヘルプのメッセージに対して適切なサーバー側日程を選択して、ESB を通過する SOAP ヘッダーを持たない、受信メッセージを使用できます。</span><span class="sxs-lookup"><span data-stu-id="02922-103">The ESB Itinerary Selector component allows incoming messages that do not have the itinerary SOAP header to pass through the ESB by selecting an appropriate server-side itinerary for the message with the help of a resolver.</span></span> <span data-ttu-id="02922-104">コンポーネントは、クライアントによって要求されると、SOAP ヘッダーを使用して、日程のバージョンと名前を定義するメッセージも使用されます。</span><span class="sxs-lookup"><span data-stu-id="02922-104">The component is also used for messages that use a SOAP header to define the name and version of an itinerary, as requested by the client.</span></span>  
  
## <a name="installation"></a><span data-ttu-id="02922-105">インストール</span><span class="sxs-lookup"><span data-stu-id="02922-105">Installation</span></span>  
 <span data-ttu-id="02922-106">ESB コアを自動的にインストールするインストール、 **ItinerarySelector**コンポーネントを BizTalk Server パイプライン コンポーネント フォルダーでします。</span><span class="sxs-lookup"><span data-stu-id="02922-106">Installing the ESB Core automatically installs the **ItinerarySelector** component in the BizTalk Server Pipeline Components folder.</span></span>  
  
## <a name="how-it-works"></a><span data-ttu-id="02922-107">しくみ</span><span class="sxs-lookup"><span data-stu-id="02922-107">How It Works</span></span>  
 <span data-ttu-id="02922-108">ESB スケジュール セレクター コンポーネントは、受信パイプラインにのみ配置できる Microsoft BizTalk パイプライン コンポーネントです。</span><span class="sxs-lookup"><span data-stu-id="02922-108">The ESB Itinerary Selector component is a Microsoft BizTalk pipeline component that can reside only in a receive pipeline.</span></span> <span data-ttu-id="02922-109">コンポーネントは、メッセージの処理で使用するためのサーバー側旅行プランを選択します。</span><span class="sxs-lookup"><span data-stu-id="02922-109">The component selects a server-side itinerary for use in processing a message.</span></span> <span data-ttu-id="02922-110">コンポーネントがその構成が読み込まれを使用して、メッセージが受信パイプラインでコンポーネントを通過すると、 **ResolverConnectionString**を呼び出すときに使用する適切な旅行プランを検索する適切な競合回避モジュールのプロパティメッセージを処理します。</span><span class="sxs-lookup"><span data-stu-id="02922-110">As the message passes through the component in a receive pipeline, the component reads its configuration and uses the **ResolverConnectionString** property to call the correct resolver to look up the appropriate itinerary to use when processing the message.</span></span> <span data-ttu-id="02922-111">スケジュール セレクター コンポーネントは、行程のパイプライン コンポーネントを検証して、メッセージ、メッセージは、次の処理ステージを続けるようにするために必要なプロパティを昇格させると、同じ手順を実行します。</span><span class="sxs-lookup"><span data-stu-id="02922-111">The Itinerary Selector component then performs the same steps as the Itinerary pipeline component to validate the message and promote the properties necessary to ensure the message continues to the next processing stage.</span></span>  
  
## <a name="using-the-esb-itinerary-selector-component"></a><span data-ttu-id="02922-112">ESB スケジュール セレクター コンポーネントを使用します。</span><span class="sxs-lookup"><span data-stu-id="02922-112">Using the ESB Itinerary Selector Component</span></span>  
 <span data-ttu-id="02922-113">ESB スケジュール コンポーネントを受信パイプラインに追加し、受信場所のパイプラインを使用できます。</span><span class="sxs-lookup"><span data-stu-id="02922-113">You can add the ESB Itinerary component to a receive pipeline and then use the pipeline in a receive location.</span></span> <span data-ttu-id="02922-114">WCF の傾斜、名とバージョン (SOAP ヘッダーで表される) ように、クライアントによって要求されたスケジュールの旅程静的リゾルバーでこのコンポーネントを構成するときに、メッセージ コンテキストから取得され、適切な選択に使用旅行プラン。</span><span class="sxs-lookup"><span data-stu-id="02922-114">When this component is configured with the ITINERARY-STATIC resolver in WCF on-ramp, the name and version of the itinerary requested by the client (as represented in the SOAP header) will be retrieved from the message context and used to select the appropriate itinerary.</span></span>  
  
## <a name="component-properties"></a><span data-ttu-id="02922-115">コンポーネント プロパティ</span><span class="sxs-lookup"><span data-stu-id="02922-115">Component Properties</span></span>  
 <span data-ttu-id="02922-116">ESB スケジュール セレクター コンポーネントは、3 つのパブリック プロパティを公開します。</span><span class="sxs-lookup"><span data-stu-id="02922-116">The ESB Itinerary Selector component exposes three public properties:</span></span>  
  
-   <span data-ttu-id="02922-117">**IgnoreErrorKey**します。</span><span class="sxs-lookup"><span data-stu-id="02922-117">**IgnoreErrorKey**.</span></span> <span data-ttu-id="02922-118">このプロパティが定義かどうか、競合回避モジュールでエラーが返された場合、メッセージの処理、スケジュールなし (に設定すると**True**) または中断します。</span><span class="sxs-lookup"><span data-stu-id="02922-118">This property defines whether, if an error is returned by the resolver, the message should be processed without the itinerary (when set to **True**) or suspended.</span></span>  
  
-   <span data-ttu-id="02922-119">**ItineraryFactKey**します。</span><span class="sxs-lookup"><span data-stu-id="02922-119">**ItineraryFactKey**.</span></span> <span data-ttu-id="02922-120">これは、選択したスケジュールの実際の XML を格納した競合回避モジュールによって返されたディクショナリのキーを表します。</span><span class="sxs-lookup"><span data-stu-id="02922-120">This represents the key in the dictionary returned by the resolver that contains the actual XML of the Itinerary selected.</span></span> <span data-ttu-id="02922-121">一般に、 **Resolver.Itinerary**カスタム競合回避モジュールを使用しない限り、します。</span><span class="sxs-lookup"><span data-stu-id="02922-121">Generally, **Resolver.Itinerary**, unless a custom resolver is used.</span></span>  
  
-   <span data-ttu-id="02922-122">**ResolverConnectionString**します。</span><span class="sxs-lookup"><span data-stu-id="02922-122">**ResolverConnectionString**.</span></span> <span data-ttu-id="02922-123">これは、競合回避モジュールを使用する名前と値のペアを含む競合回避モジュールの接続文字列や、旅行プランを検索します。</span><span class="sxs-lookup"><span data-stu-id="02922-123">This is a resolver connection string that contains name-value pairs that a resolver can use to select and/or look-up an itinerary.</span></span>