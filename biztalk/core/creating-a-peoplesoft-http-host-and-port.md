---
title: PeopleSoft HTTP ホストおよびポートを作成 |Microsoft ドキュメント
ms.custom: ''
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: ''
ms.suite: ''
ms.tgt_pltfrm: ''
ms.topic: article
helpviewer_keywords:
- HTTP port
- HTTP host
ms.assetid: 3e1ce5fd-32ee-409f-b4c8-f2bc68470f17
caps.latest.revision: 8
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: e673b2a2acdcd5248391f245ab990d424aefd298
ms.sourcegitcommit: cb908c540d8f1a692d01dc8f313e16cb4b4e696d
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 09/20/2017
ms.locfileid: "22238114"
---
# <a name="creating-a-peoplesoft-http-host-and-port"></a><span data-ttu-id="d0983-102">PeopleSoft の HTTP ホストとポートを作成する</span><span class="sxs-lookup"><span data-stu-id="d0983-102">Creating a PeopleSoft HTTP Host and Port</span></span>
<span data-ttu-id="d0983-103">PeopleSoft のメッセージ公開アーキテクチャは、Integration Broker と呼ばれています。</span><span class="sxs-lookup"><span data-stu-id="d0983-103">The Message publication architecture in PeopleSoft is known as Integration Broker.</span></span> <span data-ttu-id="d0983-104">Integration Broker の主なコンポーネントは次のとおりです。</span><span class="sxs-lookup"><span data-stu-id="d0983-104">The main components of Integration Broker are as follows:</span></span>  
  
-   <span data-ttu-id="d0983-105">ゲートウェイ</span><span class="sxs-lookup"><span data-stu-id="d0983-105">Gateway</span></span>  
  
-   <span data-ttu-id="d0983-106">公開ノード</span><span class="sxs-lookup"><span data-stu-id="d0983-106">Publishing node</span></span>  
  
-   <span data-ttu-id="d0983-107">サブスクライバー ノード</span><span class="sxs-lookup"><span data-stu-id="d0983-107">Subscriber node</span></span>  
  
 <span data-ttu-id="d0983-108">これら 3 つが連携して、HTTP リスナーの URL にメッセージを公開します。</span><span class="sxs-lookup"><span data-stu-id="d0983-108">All three work together to publish a message to a URL for an HTTP listener.</span></span> <span data-ttu-id="d0983-109">公開ノードを設定する必要があります。</span><span class="sxs-lookup"><span data-stu-id="d0983-109">You must set the Publishing node.</span></span> <span data-ttu-id="d0983-110">PeopleSoft には既定の公開ノードがあり、ローカル メッセージ ノードとも呼ばれます。</span><span class="sxs-lookup"><span data-stu-id="d0983-110">PeopleSoft has a default publishing node, also known as local message node.</span></span> <span data-ttu-id="d0983-111">ノードおよび公開ノードのトランザクションをアクティブ化する必要があります。</span><span class="sxs-lookup"><span data-stu-id="d0983-111">You must activate the node and the transactions for the publishing node.</span></span> <span data-ttu-id="d0983-112">サブスクリプション ノードの種類を外部ノードとして設定した後、ノードとトランザクションをアクティブ化する必要があります。</span><span class="sxs-lookup"><span data-stu-id="d0983-112">You must set the Subscription node with the type as external node, and then activate the node and the transactions.</span></span> <span data-ttu-id="d0983-113">このノードの場合は、また、タイプを HTTP に設定し、接続情報も設定します。</span><span class="sxs-lookup"><span data-stu-id="d0983-113">For this node, you also set the type to be HTTP and set the connection information.</span></span>  
  
 <span data-ttu-id="d0983-114">PeopleSoft によってイベントの送信に使用される PeopleSoft HTTP ホストおよびポートを作成するには、PeopleSoft Integration Broker を使用します。</span><span class="sxs-lookup"><span data-stu-id="d0983-114">You use PeopleSoft Integration Broker to create a PeopleSoft HTTP Host and Port where PeopleSoft sends events.</span></span> <span data-ttu-id="d0983-115">確認すること、メッセージがアクティブでルーティング」の手順を使用して、[メッセージのアクティビティの状態を確認する方法](../core/how-to-verify-activity-status-of-a-message.md)です。</span><span class="sxs-lookup"><span data-stu-id="d0983-115">You make sure that the message is active and routed by using the procedure in [How to Verify Activity Status of a Message](../core/how-to-verify-activity-status-of-a-message.md).</span></span>  
  
## <a name="in-this-section"></a><span data-ttu-id="d0983-116">このセクションの内容</span><span class="sxs-lookup"><span data-stu-id="d0983-116">In This Section</span></span>  
  
-   [<span data-ttu-id="d0983-117">メッセージのアクティビティの状態を確認する方法</span><span class="sxs-lookup"><span data-stu-id="d0983-117">How to Verify Activity Status of a Message</span></span>](../core/how-to-verify-activity-status-of-a-message.md)  
  
-   [<span data-ttu-id="d0983-118">統合ゲートウェイと HTTP 出力コネクタを構成する方法</span><span class="sxs-lookup"><span data-stu-id="d0983-118">How to Configure the Integration Gateway and HTTP Output Connector</span></span>](../core/how-to-configure-the-integration-gateway-and-http-output-connector.md)  
  
-   [<span data-ttu-id="d0983-119">新しいゲートウェイ ノードを作成する方法</span><span class="sxs-lookup"><span data-stu-id="d0983-119">How to Create a New Gateway Node</span></span>](../core/how-to-create-a-new-gateway-node.md)  
  
-   [<span data-ttu-id="d0983-120">トランザクションを追加する方法</span><span class="sxs-lookup"><span data-stu-id="d0983-120">How to Add a Transaction</span></span>](../core/how-to-add-a-transaction.md)  
  
-   [<span data-ttu-id="d0983-121">HTTP ノードをテストする方法</span><span class="sxs-lookup"><span data-stu-id="d0983-121">How to Test the HTTP Node</span></span>](../core/how-to-test-the-http-node.md)