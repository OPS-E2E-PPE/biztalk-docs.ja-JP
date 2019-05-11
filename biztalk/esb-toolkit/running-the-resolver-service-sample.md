---
title: リゾルバー サービス サンプルを実行している |。Microsoft Docs
ms.custom: ''
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: ''
ms.suite: ''
ms.tgt_pltfrm: ''
ms.topic: article
ms.assetid: b4bf0b21-6aa0-4524-9e63-93a172845d4a
caps.latest.revision: 2
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: adb7f35671534a3c425e962d4980d452368f79d7
ms.sourcegitcommit: 381e83d43796a345488d54b3f7413e11d56ad7be
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 05/07/2019
ms.locfileid: "65242700"
---
# <a name="running-the-resolver-service-sample"></a><span data-ttu-id="3c41a-102">リゾルバー サービス サンプルを実行しています。</span><span class="sxs-lookup"><span data-stu-id="3c41a-102">Running the Resolver Service Sample</span></span>
<span data-ttu-id="3c41a-103">リゾルバー サービス サンプルでは、次のシナリオを使用します。</span><span class="sxs-lookup"><span data-stu-id="3c41a-103">The Resolver Service sample demonstrates the following scenarios:</span></span>  

- <span data-ttu-id="3c41a-104">サービス エンドポイント バインド キーを使用して、UDDI3 から URI を解決するには</span><span class="sxs-lookup"><span data-stu-id="3c41a-104">Resolve a service endpoint URI from UDDI3 using a binding key</span></span>  

- <span data-ttu-id="3c41a-105">サービス エンドポイントのカテゴリ化の検索を使用して、UDDI3 から URI を解決するには</span><span class="sxs-lookup"><span data-stu-id="3c41a-105">Resolve a service endpoint URI from UDDI3 using a categorization search</span></span>  

- <span data-ttu-id="3c41a-106">静的な競合回避モジュールを使用して、変換 (BizTalk マップの種類) を解決するには</span><span class="sxs-lookup"><span data-stu-id="3c41a-106">Resolve a transformation (BizTalk Map type) using a STATIC resolver</span></span>  

- <span data-ttu-id="3c41a-107">サービス エンドポイントの静的な競合回避モジュールを使用して、URI を解決するには</span><span class="sxs-lookup"><span data-stu-id="3c41a-107">Resolve a service endpoint URI using a STATIC resolver</span></span>  

- <span data-ttu-id="3c41a-108">サービス エンドポイント、XPath 式を使用して、URI を解決するには</span><span class="sxs-lookup"><span data-stu-id="3c41a-108">Resolve a service endpoint URI using an XPath expression</span></span>  

- <span data-ttu-id="3c41a-109">静的行程リゾルバーを使用するスケジュールを解決するには</span><span class="sxs-lookup"><span data-stu-id="3c41a-109">Resolve an itinerary using a static ITINERARY resolver</span></span>  

- <span data-ttu-id="3c41a-110">行程静的 (Unity) の競合回避モジュールを使用して、スケジュールを解決するには</span><span class="sxs-lookup"><span data-stu-id="3c41a-110">Resolve an itinerary using an ITINERARY-STATIC (Unity) resolver</span></span>  

- <span data-ttu-id="3c41a-111">BRE (BRI リゾルバー) を使用するスケジュールを解決するには</span><span class="sxs-lookup"><span data-stu-id="3c41a-111">Resolve an itinerary using BRE (BRI Resolver)</span></span>  

- <span data-ttu-id="3c41a-112">BRE (BRI リゾルバー) を使用してメッセージを使用するスケジュールを解決するには</span><span class="sxs-lookup"><span data-stu-id="3c41a-112">Resolve an Itinerary using BRE (BRI Resolver) with the Message</span></span>  

- <span data-ttu-id="3c41a-113">サービス エンドポイント URI を解決する BRE を使用します。</span><span class="sxs-lookup"><span data-stu-id="3c41a-113">Resolve a service endpoint URI using BRE</span></span>  

- <span data-ttu-id="3c41a-114">BRE を使用して変換を解決するには</span><span class="sxs-lookup"><span data-stu-id="3c41a-114">Resolve a transformation using BRE</span></span>  

  <span data-ttu-id="3c41a-115">**リゾルバー サービスの ASMX 実装を使用してすべての解決シナリオを実行するには**</span><span class="sxs-lookup"><span data-stu-id="3c41a-115">**To run all the resolution scenarios using the ASMX implementation of the Resolver service**</span></span>  

1. <span data-ttu-id="3c41a-116">GlobalBank.ESB アプリケーションが実行されていない場合は、Microsoft の BizTalk 管理コンソールを使用して、開始します。</span><span class="sxs-lookup"><span data-stu-id="3c41a-116">If the GlobalBank.ESB application is not already running, use the Microsoft BizTalk Administration Console to start it.</span></span>  

2. <span data-ttu-id="3c41a-117">Windows エクスプ ローラーで \Source\Samples\ResolverService フォルダーを開き、RunTestClient_ASMX.cmd ファイルをダブルクリックします。</span><span class="sxs-lookup"><span data-stu-id="3c41a-117">In Windows Explorer, open the \Source\Samples\ResolverService folder, and then double-click the file RunTestClient_ASMX.cmd.</span></span>  

3. <span data-ttu-id="3c41a-118">\Source\Samples\ResolverService\Output フォルダーを開き、前に示した解決要求に対応する結果ファイルを開きます。</span><span class="sxs-lookup"><span data-stu-id="3c41a-118">Open the \Source\Samples\ResolverService\Output folder, and then open the result files, which correspond to the resolution requests listed earlier.</span></span>  

   <span data-ttu-id="3c41a-119">**リゾルバー サービスの WCF 実装を使用してすべての解決シナリオを実行するには**</span><span class="sxs-lookup"><span data-stu-id="3c41a-119">**To run all the resolution scenarios using the WCF implementation of the Resolver service**</span></span>  

4. <span data-ttu-id="3c41a-120">GlobalBank.ESB アプリケーションが実行されていない場合は、BizTalk 管理コンソールを使用して開始します。</span><span class="sxs-lookup"><span data-stu-id="3c41a-120">If the GlobalBank.ESB application is not already running, use the BizTalk Administration Console to start it.</span></span>  

5. <span data-ttu-id="3c41a-121">Windows エクスプ ローラーで \Source\Samples\ResolverService フォルダーを開き、RunTestClient_WCF.cmd ファイルをダブルクリックします。</span><span class="sxs-lookup"><span data-stu-id="3c41a-121">In Windows Explorer, open the \Source\Samples\ResolverService folder, and then double-click the file RunTestClient_WCF.cmd.</span></span>  

6. <span data-ttu-id="3c41a-122">\Source\Samples\ResolverService\Output フォルダーを開き、前に示した解決要求に対応する結果ファイルを開きます。</span><span class="sxs-lookup"><span data-stu-id="3c41a-122">Open the \Source\Samples\ResolverService\Output folder, and then open the result files, which correspond to the resolution requests listed earlier.</span></span>
