---
title: 計画し、WCF LOB Adapter SDK を使用して、アダプターの設計 |Microsoft Docs
ms.custom: ''
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: ''
ms.suite: ''
ms.tgt_pltfrm: ''
ms.topic: article
ms.assetid: 2dfbfa6c-2f87-40bb-93d4-6fbb37a235c5
caps.latest.revision: 7
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: 82d907cdc2538bb4ed024f0aaf38bf04cf80cf59
ms.sourcegitcommit: 381e83d43796a345488d54b3f7413e11d56ad7be
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 05/07/2019
ms.locfileid: "65363432"
---
# <a name="plan-and-design-your-adapter-using-the-wcf-lob-adapter-sdk"></a><span data-ttu-id="b3ba2-102">計画し、WCF LOB Adapter SDK を使用して、アダプターの設計</span><span class="sxs-lookup"><span data-stu-id="b3ba2-102">Plan and design your adapter using the WCF LOB Adapter SDK</span></span>

## <a name="overview"></a><span data-ttu-id="b3ba2-103">概要</span><span class="sxs-lookup"><span data-stu-id="b3ba2-103">Overview</span></span>
<span data-ttu-id="b3ba2-104">アダプターを使用して開発を含む、任意の開発作業の重要な部分は、計画、[!INCLUDE[afproductnameshort](../../includes/afproductnameshort-md.md)]します。</span><span class="sxs-lookup"><span data-stu-id="b3ba2-104">Planning is an important part of any development effort, including adapters developed with the [!INCLUDE[afproductnameshort](../../includes/afproductnameshort-md.md)].</span></span> <span data-ttu-id="b3ba2-105">エラーを適切に、アダプターに予期しない動作を特定の API によって提供される主な機能が不足している可能性があります、アダプターの開発時に、基幹業務システムおよび関連するさまざまな実装の詳細と対話するための戦略を計画するには予期されたは、ユーザー、または頻繁に更新し、修復を必要とします。</span><span class="sxs-lookup"><span data-stu-id="b3ba2-105">Failure to adequately plan strategies for interacting with the line-of-business system and the different implementation details involved when developing an adapter could cause your adapter to behave unexpectedly, to lack certain key features provided by the API and expected by the user, or to require frequent update and repair.</span></span>  
  
 <span data-ttu-id="b3ba2-106">このセクションには、アダプターをデザインするための情報が含まれています。</span><span class="sxs-lookup"><span data-stu-id="b3ba2-106">This section contains the information needed to design your adapter.</span></span> <span data-ttu-id="b3ba2-107">この情報を使用して、ユーザーのニーズを満たす設計を計画できます。</span><span class="sxs-lookup"><span data-stu-id="b3ba2-107">Using this information, you can plan a design that meets the needs of your users.</span></span>  
  
## <a name="get-started"></a><span data-ttu-id="b3ba2-108">作業開始</span><span class="sxs-lookup"><span data-stu-id="b3ba2-108">Get started</span></span>
  
-   [<span data-ttu-id="b3ba2-109">LOB システムを知って理解する</span><span class="sxs-lookup"><span data-stu-id="b3ba2-109">Know and understand your LOB system</span></span>](understand-the-lob-system-with-the-wcf-lob-adapter-sdk.md) 
  
-   [<span data-ttu-id="b3ba2-110">WCF LOB Adapter SDK でサポートされているメッセージ交換パターンを表示します。</span><span class="sxs-lookup"><span data-stu-id="b3ba2-110">View the supported message exchange patterns in the WCF LOB Adapter SDK</span></span>](view-the-supported-message-exchange-patterns-in-the-wcf-lob-adapter-sdk.md)  
  
-   [<span data-ttu-id="b3ba2-111">WCF LOB Adapter SDK を使用する場合は、URI スキームとアドレス指定の形式を選択します</span><span class="sxs-lookup"><span data-stu-id="b3ba2-111">Select a URI scheme and addressing format when using the WCF LOB Adapter SDK</span></span>](select-a-uri-scheme-and-addressing-format-when-using-the-wcf-lob-adapter-sdk.md)  
  
-   [<span data-ttu-id="b3ba2-112">WCF LOB Adapter SDK で作成されたアダプターで WCF セキュリティを概要します。</span><span class="sxs-lookup"><span data-stu-id="b3ba2-112">Understand WCF security on the adapter created with the WCF LOB Adapter SDK</span></span>](understand-wcf-security-on-the-adapter-created-with-the-wcf-lob-adapter-sdk.md)  
  
-   [<span data-ttu-id="b3ba2-113">WCF でのトランザクションを理解する</span><span class="sxs-lookup"><span data-stu-id="b3ba2-113">Understand transactions in WCF</span></span>](atomic-consistent-isolated-durable-transactions-with-the-wcf-lob-adapter-sdk.md)  
  
-   [<span data-ttu-id="b3ba2-114">メタデータの検索と、WCF LOB Adapter SDK のアダプターを使用した参照について</span><span class="sxs-lookup"><span data-stu-id="b3ba2-114">About metadata search and browse with your WCF LOB Adapter SDK adapter</span></span>](about-metadata-search-and-browse-with-your-wcf-lob-adapter-sdk-adapter.md)
  
## <a name="see-also"></a><span data-ttu-id="b3ba2-115">参照</span><span class="sxs-lookup"><span data-stu-id="b3ba2-115">See Also</span></span>  
[<span data-ttu-id="b3ba2-116">アダプターを計画して設計する</span><span class="sxs-lookup"><span data-stu-id="b3ba2-116">Plan and architect your adapter</span></span>](plan-and-design-an-adapter-using-the-wcf-lob-adapter-sdk.md)