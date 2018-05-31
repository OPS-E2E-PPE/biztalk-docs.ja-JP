---
title: リゾルバー サービスのサンプルを実行している |Microsoft ドキュメント
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
ms.openlocfilehash: bb9d7e3e4d4bce4e46653f7b650004928368eced
ms.sourcegitcommit: cb908c540d8f1a692d01dc8f313e16cb4b4e696d
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 09/20/2017
ms.locfileid: "22294754"
---
# <a name="running-the-resolver-service-sample"></a><span data-ttu-id="f2caa-102">リゾルバー サービスのサンプルを実行しています。</span><span class="sxs-lookup"><span data-stu-id="f2caa-102">Running the Resolver Service Sample</span></span>
<span data-ttu-id="f2caa-103">リゾルバー サービス サンプルでは、次のシナリオを使用します。</span><span class="sxs-lookup"><span data-stu-id="f2caa-103">The Resolver Service sample demonstrates the following scenarios:</span></span>  
  
-   <span data-ttu-id="f2caa-104">サービス エンドポイント バインド キーを使用して、UDDI3 から URI を解決するには</span><span class="sxs-lookup"><span data-stu-id="f2caa-104">Resolve a service endpoint URI from UDDI3 using a binding key</span></span>  
  
-   <span data-ttu-id="f2caa-105">サービス エンドポイントのカテゴリ化検索を使用して、UDDI3 から URI を解決するには</span><span class="sxs-lookup"><span data-stu-id="f2caa-105">Resolve a service endpoint URI from UDDI3 using a categorization search</span></span>  
  
-   <span data-ttu-id="f2caa-106">静的な競合回避モジュールを使用して、変換 (BizTalk マップの種類) を解決するには</span><span class="sxs-lookup"><span data-stu-id="f2caa-106">Resolve a transformation (BizTalk Map type) using a STATIC resolver</span></span>  
  
-   <span data-ttu-id="f2caa-107">サービス エンドポイントに静的な競合回避モジュールを使用して URI を解決するには</span><span class="sxs-lookup"><span data-stu-id="f2caa-107">Resolve a service endpoint URI using a STATIC resolver</span></span>  
  
-   <span data-ttu-id="f2caa-108">サービス エンドポイント、XPath 式を使用して URI を解決するには</span><span class="sxs-lookup"><span data-stu-id="f2caa-108">Resolve a service endpoint URI using an XPath expression</span></span>  
  
-   <span data-ttu-id="f2caa-109">静的行程リゾルバーを使用して、日程を解決するには</span><span class="sxs-lookup"><span data-stu-id="f2caa-109">Resolve an itinerary using a static ITINERARY resolver</span></span>  
  
-   <span data-ttu-id="f2caa-110">行程静的 (Unity) リゾルバーを使用して、日程を解決するには</span><span class="sxs-lookup"><span data-stu-id="f2caa-110">Resolve an itinerary using an ITINERARY-STATIC (Unity) resolver</span></span>  
  
-   <span data-ttu-id="f2caa-111">BRE (BRI リゾルバー) を使用して、日程を解決するには</span><span class="sxs-lookup"><span data-stu-id="f2caa-111">Resolve an itinerary using BRE (BRI Resolver)</span></span>  
  
-   <span data-ttu-id="f2caa-112">BRE (BRI リゾルバー) を使用して、メッセージと共に日程を解決するには</span><span class="sxs-lookup"><span data-stu-id="f2caa-112">Resolve an Itinerary using BRE (BRI Resolver) with the Message</span></span>  
  
-   <span data-ttu-id="f2caa-113">サービス エンドポイントの URI を解決するには BRE を使用して</span><span class="sxs-lookup"><span data-stu-id="f2caa-113">Resolve a service endpoint URI using BRE</span></span>  
  
-   <span data-ttu-id="f2caa-114">BRE を使用して変換を解決するには</span><span class="sxs-lookup"><span data-stu-id="f2caa-114">Resolve a transformation using BRE</span></span>  
  
 <span data-ttu-id="f2caa-115">**ASMX、リゾルバー サービスの実装を使用するすべての解像度シナリオを実行するには**</span><span class="sxs-lookup"><span data-stu-id="f2caa-115">**To run all the resolution scenarios using the ASMX implementation of the Resolver service**</span></span>  
  
1.  <span data-ttu-id="f2caa-116">GlobalBank.ESB アプリケーションが既に実行されていない場合は、Microsoft BizTalk 管理コンソールを使用して、開始します。</span><span class="sxs-lookup"><span data-stu-id="f2caa-116">If the GlobalBank.ESB application is not already running, use the Microsoft BizTalk Administration Console to start it.</span></span>  
  
2.  <span data-ttu-id="f2caa-117">Windows エクスプ ローラーで、\Source\Samples\ResolverService フォルダーを開き RunTestClient_ASMX.cmd ファイルをダブルクリックします。</span><span class="sxs-lookup"><span data-stu-id="f2caa-117">In Windows Explorer, open the \Source\Samples\ResolverService folder, and then double-click the file RunTestClient_ASMX.cmd.</span></span>  
  
3.  <span data-ttu-id="f2caa-118">\Source\Samples\ResolverService\Output フォルダーを開き、以前に一覧表示する解決要求に対応する結果ファイルを開きます。</span><span class="sxs-lookup"><span data-stu-id="f2caa-118">Open the \Source\Samples\ResolverService\Output folder, and then open the result files, which correspond to the resolution requests listed earlier.</span></span>  
  
 <span data-ttu-id="f2caa-119">**リゾルバー サービスの WCF 実装を使用してすべての解像度シナリオを実行するには**</span><span class="sxs-lookup"><span data-stu-id="f2caa-119">**To run all the resolution scenarios using the WCF implementation of the Resolver service**</span></span>  
  
1.  <span data-ttu-id="f2caa-120">GlobalBank.ESB アプリケーションが既に実行されていない場合は、BizTalk 管理コンソールを使用して、開始します。</span><span class="sxs-lookup"><span data-stu-id="f2caa-120">If the GlobalBank.ESB application is not already running, use the BizTalk Administration Console to start it.</span></span>  
  
2.  <span data-ttu-id="f2caa-121">Windows エクスプ ローラーで、\Source\Samples\ResolverService フォルダーを開き RunTestClient_WCF.cmd ファイルをダブルクリックします。</span><span class="sxs-lookup"><span data-stu-id="f2caa-121">In Windows Explorer, open the \Source\Samples\ResolverService folder, and then double-click the file RunTestClient_WCF.cmd.</span></span>  
  
3.  <span data-ttu-id="f2caa-122">\Source\Samples\ResolverService\Output フォルダーを開き、以前に一覧表示する解決要求に対応する結果ファイルを開きます。</span><span class="sxs-lookup"><span data-stu-id="f2caa-122">Open the \Source\Samples\ResolverService\Output folder, and then open the result files, which correspond to the resolution requests listed earlier.</span></span>