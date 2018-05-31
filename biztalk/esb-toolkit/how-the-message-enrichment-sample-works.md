---
title: メッセージ強化サンプルのしくみ |Microsoft ドキュメント
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
ms.openlocfilehash: 5ef516b992acbcee2936edb6341cbf1434ba4c79
ms.sourcegitcommit: 7497f6f23d7aadfa8535d0530493f8b4a2a50a0b
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 09/22/2017
ms.locfileid: "22303674"
---
# <a name="how-the-message-enrichment-sample-works"></a><span data-ttu-id="5b191-102">メッセージ強化サンプルのしくみ</span><span class="sxs-lookup"><span data-stu-id="5b191-102">How the Message Enrichment Sample Works</span></span>
 <span data-ttu-id="5b191-103">Message Enrichment サンプルは、汎用の再利用可能なサービスとの統合パターンをカプセル化することを示します。</span><span class="sxs-lookup"><span data-stu-id="5b191-103">The Message Enrichment sample demonstrates that it is possible to encapsulate an integration pattern as a generic reusable service.</span></span> <span data-ttu-id="5b191-104">ここでは、サンプルは、コンテンツ Enricher パターンを実装します。</span><span class="sxs-lookup"><span data-stu-id="5b191-104">In this case the sample implements the Content Enricher pattern.</span></span> <span data-ttu-id="5b191-105">参照情報を表示する順序での外部サービスに送信するメッセージを準備するための変換とからのデータが含まれる新しいメッセージに応答を組み込むし、別の変換を使用してコンテンツ Enricher パターンが一般的には、元のメッセージ。</span><span class="sxs-lookup"><span data-stu-id="5b191-105">The Content Enricher pattern generally involves using a transform to prepare a message for transmission to an external service in order to lookup information, and then another transform to incorporate the response into a new message which also contains data from the original message.</span></span> <span data-ttu-id="5b191-106">汎用的なやり方で、パターンを実装するためには、Message Enrichment サンプルを最大 2 つの競合回避モジュールを使用して、外部ソースから情報を使用して、メッセージの強化を構成するオーケストレーションに基づく itinerary サービスを提供します。</span><span class="sxs-lookup"><span data-stu-id="5b191-106">In order to implement the pattern in a generic fashion, the Message Enrichment sample provides an orchestration-based itinerary service that can use up to two resolvers to configure enrichment of a message using information from an external source.</span></span>
  
 <span data-ttu-id="5b191-107">最初の競合回避モジュールは、ルーティング情報を返す必要があります。返すことも平行して情報を変換します。</span><span class="sxs-lookup"><span data-stu-id="5b191-107">The first resolver must return routing information; it can also return transform information alongside it.</span></span> <span data-ttu-id="5b191-108">ルーティングされる前に受信メッセージに変換が適用される、指定した場合、競合回避モジュールで指定された場所にします。</span><span class="sxs-lookup"><span data-stu-id="5b191-108">If specified, the transform is applied to the incoming message before being routed to the location specified by the resolver.</span></span> <span data-ttu-id="5b191-109">提供されたサンプル行程 GetOrderDetails をという名前の GlobalBankESB データベース内の SQL ストアド プロシージャを実行し、結果を返す、Wcf-custom アダプター プロバイダーが使用されます。</span><span class="sxs-lookup"><span data-stu-id="5b191-109">In the provided sample itinerary, the WCF-Custom adapter provider is used to execute a SQL stored procedure within the GlobalBankESB database named GetOrderDetails and return the result.</span></span>  
  
 <span data-ttu-id="5b191-110">必要に応じて、2 番目の競合回避モジュールを含めることできます。</span><span class="sxs-lookup"><span data-stu-id="5b191-110">Optionally, a second resolver can be included.</span></span> <span data-ttu-id="5b191-111">指定した場合、2 番目の競合回避モジュールは、変換情報を含める必要があります。</span><span class="sxs-lookup"><span data-stu-id="5b191-111">If provided, the second resolver must include transformation information.</span></span> <span data-ttu-id="5b191-112">この変換は、元のメッセージと、入力として、どのデータ ソースに接続がによって返される結果に与えられます。</span><span class="sxs-lookup"><span data-stu-id="5b191-112">This transform will be given the original message and the result, returned by whichever data source was contacted, as input.</span></span> <span data-ttu-id="5b191-113">サンプル行程が元のメッセージと、ストアド プロシージャの結果から情報をプルし、結果として得られる InventoryOrder メッセージ内に含めることに、テーブル ループ functoid を使用するマップが参照されます。</span><span class="sxs-lookup"><span data-stu-id="5b191-113">In the sample itinerary, a map is referenced that uses a table looping functoid to pull information out of the original message and the result of the stored procedure and include it inside the resulting InventoryOrder message.</span></span>
