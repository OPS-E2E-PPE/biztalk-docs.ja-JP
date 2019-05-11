---
title: PeopleSoft の HTTP ホストとポートを作成する |Microsoft Docs
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
ms.openlocfilehash: 18675298b03e380ed53629a74fff31dfb4680068
ms.sourcegitcommit: 381e83d43796a345488d54b3f7413e11d56ad7be
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 05/07/2019
ms.locfileid: "65390103"
---
# <a name="creating-a-peoplesoft-http-host-and-port"></a><span data-ttu-id="b7e57-102">PeopleSoft の HTTP ホストとポートを作成します。</span><span class="sxs-lookup"><span data-stu-id="b7e57-102">Creating a PeopleSoft HTTP Host and Port</span></span>
<span data-ttu-id="b7e57-103">PeopleSoft のメッセージ公開アーキテクチャは、統合ブローカーと呼ばれます。</span><span class="sxs-lookup"><span data-stu-id="b7e57-103">The Message publication architecture in PeopleSoft is known as Integration Broker.</span></span> <span data-ttu-id="b7e57-104">統合ブローカーの主要なコンポーネントは次のとおりです。</span><span class="sxs-lookup"><span data-stu-id="b7e57-104">The main components of Integration Broker are as follows:</span></span>  
  
- <span data-ttu-id="b7e57-105">ゲートウェイ</span><span class="sxs-lookup"><span data-stu-id="b7e57-105">Gateway</span></span>  
  
- <span data-ttu-id="b7e57-106">公開ノード</span><span class="sxs-lookup"><span data-stu-id="b7e57-106">Publishing node</span></span>  
  
- <span data-ttu-id="b7e57-107">サブスクライバー ノード</span><span class="sxs-lookup"><span data-stu-id="b7e57-107">Subscriber node</span></span>  
  
  <span data-ttu-id="b7e57-108">3 つすべてが連携して、HTTP リスナーの URL にメッセージを発行します。</span><span class="sxs-lookup"><span data-stu-id="b7e57-108">All three work together to publish a message to a URL for an HTTP listener.</span></span> <span data-ttu-id="b7e57-109">発行を設定する必要がありますノード。</span><span class="sxs-lookup"><span data-stu-id="b7e57-109">You must set the Publishing node.</span></span> <span data-ttu-id="b7e57-110">PeopleSoft が、既定の公開ノード、ローカル メッセージ ノードとも呼ばれます。</span><span class="sxs-lookup"><span data-stu-id="b7e57-110">PeopleSoft has a default publishing node, also known as local message node.</span></span> <span data-ttu-id="b7e57-111">ノードおよび公開ノードのトランザクションを有効にする必要があります。</span><span class="sxs-lookup"><span data-stu-id="b7e57-111">You must activate the node and the transactions for the publishing node.</span></span> <span data-ttu-id="b7e57-112">サブスクリプション ノードの種類を外部ノードとして設定して、ノードと、トランザクションをアクティブ化する必要があります。</span><span class="sxs-lookup"><span data-stu-id="b7e57-112">You must set the Subscription node with the type as external node, and then activate the node and the transactions.</span></span> <span data-ttu-id="b7e57-113">このノードに対しても HTTP 接続情報を設定でき、型を設定します。</span><span class="sxs-lookup"><span data-stu-id="b7e57-113">For this node, you also set the type to be HTTP and set the connection information.</span></span>  
  
  <span data-ttu-id="b7e57-114">PeopleSoft の HTTP ホストおよび PeopleSoft がイベントを送信ポートを作成するのにには、PeopleSoft Integration Broker を使用します。</span><span class="sxs-lookup"><span data-stu-id="b7e57-114">You use PeopleSoft Integration Broker to create a PeopleSoft HTTP Host and Port where PeopleSoft sends events.</span></span> <span data-ttu-id="b7e57-115">メッセージでの手順を使用して、アクティブおよびルーティングが確認する[メッセージのアクティビティの状態を確認する方法](../core/how-to-verify-activity-status-of-a-message.md)します。</span><span class="sxs-lookup"><span data-stu-id="b7e57-115">You make sure that the message is active and routed by using the procedure in [How to Verify Activity Status of a Message](../core/how-to-verify-activity-status-of-a-message.md).</span></span>  
  
## <a name="in-this-section"></a><span data-ttu-id="b7e57-116">このセクションの内容</span><span class="sxs-lookup"><span data-stu-id="b7e57-116">In This Section</span></span>  
  
-   [<span data-ttu-id="b7e57-117">メッセージのアクティビティの状態を確認する方法</span><span class="sxs-lookup"><span data-stu-id="b7e57-117">How to Verify Activity Status of a Message</span></span>](../core/how-to-verify-activity-status-of-a-message.md)  
  
-   [<span data-ttu-id="b7e57-118">統合ゲートウェイと HTTP 出力コネクタを構成する方法</span><span class="sxs-lookup"><span data-stu-id="b7e57-118">How to Configure the Integration Gateway and HTTP Output Connector</span></span>](../core/how-to-configure-the-integration-gateway-and-http-output-connector.md)  
  
-   [<span data-ttu-id="b7e57-119">新しいゲートウェイ ノードを作成する方法</span><span class="sxs-lookup"><span data-stu-id="b7e57-119">How to Create a New Gateway Node</span></span>](../core/how-to-create-a-new-gateway-node.md)  
  
-   [<span data-ttu-id="b7e57-120">トランザクションを追加する方法</span><span class="sxs-lookup"><span data-stu-id="b7e57-120">How to Add a Transaction</span></span>](../core/how-to-add-a-transaction.md)  
  
-   [<span data-ttu-id="b7e57-121">HTTP ノードをテストする方法</span><span class="sxs-lookup"><span data-stu-id="b7e57-121">How to Test the HTTP Node</span></span>](../core/how-to-test-the-http-node.md)