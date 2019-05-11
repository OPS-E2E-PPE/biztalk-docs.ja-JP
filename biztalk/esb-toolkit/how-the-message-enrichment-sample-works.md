---
title: メッセージ強化サンプルのしくみ |Microsoft Docs
ms.custom: ''
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: ''
ms.suite: ''
ms.tgt_pltfrm: ''
ms.topic: article
ms.assetid: 1188c1c9-b133-4438-b41c-ea6cffcf40fd
caps.latest.revision: 2
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: 2d304fbcaaf13b6f2b00b6de0e4813f3084203d0
ms.sourcegitcommit: 381e83d43796a345488d54b3f7413e11d56ad7be
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 05/07/2019
ms.locfileid: "65279096"
---
# <a name="how-the-message-enrichment-sample-works"></a><span data-ttu-id="1db03-102">メッセージ強化サンプルのしくみ</span><span class="sxs-lookup"><span data-stu-id="1db03-102">How the Message Enrichment Sample Works</span></span>
 <span data-ttu-id="1db03-103">Message Enrichment サンプルを再利用可能な汎用サービスとしての統合パターンをカプセル化することを示します。</span><span class="sxs-lookup"><span data-stu-id="1db03-103">The Message Enrichment sample demonstrates that it is possible to encapsulate an integration pattern as a generic reusable service.</span></span> <span data-ttu-id="1db03-104">この場合、サンプルは、コンテンツ エンリッチャー パターンを実装します。</span><span class="sxs-lookup"><span data-stu-id="1db03-104">In this case the sample implements the Content Enricher pattern.</span></span> <span data-ttu-id="1db03-105">順番に参照については、外部サービスに送信するメッセージを準備する変換とからのデータが含まれる新しいメッセージに応答を組み込むことにし、別の変換を使用してコンテンツ エンリッチャー パターンが通常は、元のメッセージ。</span><span class="sxs-lookup"><span data-stu-id="1db03-105">The Content Enricher pattern generally involves using a transform to prepare a message for transmission to an external service in order to lookup information, and then another transform to incorporate the response into a new message which also contains data from the original message.</span></span> <span data-ttu-id="1db03-106">汎用的な方法で、パターンを実装するためには、メッセージ強化サンプルは、最大で 2 つの競合回避モジュールを使用して、外部ソースから情報を使用してメッセージの強化を構成できますオーケストレーションに基づく itinerary サービスを提供します。</span><span class="sxs-lookup"><span data-stu-id="1db03-106">In order to implement the pattern in a generic fashion, the Message Enrichment sample provides an orchestration-based itinerary service that can use up to two resolvers to configure enrichment of a message using information from an external source.</span></span>
  
 <span data-ttu-id="1db03-107">最初の競合回避モジュールは、ルーティング情報を返す必要があります。返すこともできますも並行して情報を変換します。</span><span class="sxs-lookup"><span data-stu-id="1db03-107">The first resolver must return routing information; it can also return transform information alongside it.</span></span> <span data-ttu-id="1db03-108">受信メッセージにルーティングされる前に、変換が適用される指定した場合、競合回避モジュールで指定された場所にします。</span><span class="sxs-lookup"><span data-stu-id="1db03-108">If specified, the transform is applied to the incoming message before being routed to the location specified by the resolver.</span></span> <span data-ttu-id="1db03-109">提供されているサンプル旅行プランでは、Wcf-custom アダプターのプロバイダーは GetOrderDetails をという名前の GlobalBankESB データベース内の SQL ストアド プロシージャを実行し、結果を返すに使用されます。</span><span class="sxs-lookup"><span data-stu-id="1db03-109">In the provided sample itinerary, the WCF-Custom adapter provider is used to execute a SQL stored procedure within the GlobalBankESB database named GetOrderDetails and return the result.</span></span>  
  
 <span data-ttu-id="1db03-110">必要に応じて、2 つ目の競合回避モジュールに指定できます。</span><span class="sxs-lookup"><span data-stu-id="1db03-110">Optionally, a second resolver can be included.</span></span> <span data-ttu-id="1db03-111">指定した場合、2 つ目の競合回避モジュールは、変換の情報を含める必要があります。</span><span class="sxs-lookup"><span data-stu-id="1db03-111">If provided, the second resolver must include transformation information.</span></span> <span data-ttu-id="1db03-112">この変換は、元のメッセージと、入力として、どのデータ ソースに接続がによって返される結果に与えられます。</span><span class="sxs-lookup"><span data-stu-id="1db03-112">This transform will be given the original message and the result, returned by whichever data source was contacted, as input.</span></span> <span data-ttu-id="1db03-113">サンプルの旅程をテーブル ループ functoid を使用して、元のメッセージ、およびストアド プロシージャの結果から情報をプルし、結果として得られる InventoryOrder メッセージ内に含めるマップが参照されます。</span><span class="sxs-lookup"><span data-stu-id="1db03-113">In the sample itinerary, a map is referenced that uses a table looping functoid to pull information out of the original message and the result of the stored procedure and include it inside the resulting InventoryOrder message.</span></span>
