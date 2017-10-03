---
title: "オーケストレーションでの直接バインド ポートの操作 |Microsoft ドキュメント"
ms.custom: 
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: 
ms.suite: 
ms.tgt_pltfrm: 
ms.topic: article
ms.assetid: 03a37ac0-5131-4d37-b60b-56763c460463
caps.latest.revision: "9"
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: 7e7b2b59ccdaa23271ee0707f19f4fd2cddc0508
ms.sourcegitcommit: cb908c540d8f1a692d01dc8f313e16cb4b4e696d
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 09/20/2017
---
# <a name="working-with-direct-bound-ports-in-orchestrations"></a><span data-ttu-id="bb04b-102">オーケストレーションでの直接バインド ポートの操作</span><span class="sxs-lookup"><span data-stu-id="bb04b-102">Working with Direct Bound Ports in Orchestrations</span></span>
<span data-ttu-id="bb04b-103">直接バインド ポートの 3 つの種類があります: メッセージ ボックス、自己関連付けを行う、パートナー オーケストレーションとします。</span><span class="sxs-lookup"><span data-stu-id="bb04b-103">There are three types of direct bound ports: MessageBox, self-correlating, and partner orchestration.</span></span>  
  
 <span data-ttu-id="bb04b-104">メッセージ ボックスの直接バインド ポートは、パブリッシュ/サブスクライブ デザイン パターンを可能にします。</span><span class="sxs-lookup"><span data-stu-id="bb04b-104">MessageBox direct bound ports allow for publish-subscribe design patterns.</span></span> <span data-ttu-id="bb04b-105">メッセージ ボックスの直接バインド ポート上の送信メッセージは、メッセージ ボックス データベースに公開され、サブスクリプションに基づいてメッセージの受信者により取得されます。</span><span class="sxs-lookup"><span data-stu-id="bb04b-105">Messages sent on a MessageBox direct bound port are published to the MessageBox database, where message recipients pick them up based on subscriptions.</span></span> <span data-ttu-id="bb04b-106">論理の受信ポートがメッセージ ボックスの直接バインド ポート、メッセージ ボックス データベースから直接メッセージを取得するように構成します。</span><span class="sxs-lookup"><span data-stu-id="bb04b-106">Logical receive ports configured as MessageBox direct bound ports get messages directly from the MessageBox database.</span></span> <span data-ttu-id="bb04b-107">アクティブ化のため**受信**図形、メッセージ ボックスの直接バインド受信ポートを取得、メッセージの種類とフィルター式へのサブスクリプションを通じてメッセージ。</span><span class="sxs-lookup"><span data-stu-id="bb04b-107">For activating **Receive** shapes, the MessageBox direct bound receive ports get the messages through subscriptions to the message type and the filter expression.</span></span> <span data-ttu-id="bb04b-108">非アクティブ化の**受信**図形、メッセージ ボックスの直接バインド受信ポートを取得、メッセージの種類と、関連付けセットへのサブスクリプションを通じてメッセージ。</span><span class="sxs-lookup"><span data-stu-id="bb04b-108">For non-activating **Receive** shapes, the MessageBox direct bound receive ports get the messages through subscriptions to the message type and the correlation set.</span></span>  
  
 <span data-ttu-id="bb04b-109">自己関連付けを行う直接バインド ポートは、非同期のオーケストレーション間通信のデザインを支援します。</span><span class="sxs-lookup"><span data-stu-id="bb04b-109">Self-correlating direct bound ports assist you in designing asynchronous inter-orchestration communication.</span></span> <span data-ttu-id="bb04b-110">自己関連付けを行う直接バインド ポートに送信されたメッセージは、その自己関連付けを行う直接バインド ポートの受信側を作成したオーケストレーションのインスタンスにルーティングされます。</span><span class="sxs-lookup"><span data-stu-id="bb04b-110">Messages sent to a self-correlating direct bound port are routed to the instance of the orchestration that created the receiving end of the self-correlated direct bound port.</span></span>  
  
 <span data-ttu-id="bb04b-111">パートナー オーケストレーションの直接バインド ポートは、オーケストレーション間通信を提供します。</span><span class="sxs-lookup"><span data-stu-id="bb04b-111">Partner orchestration direct bound ports provide for inter-orchestration communication.</span></span> <span data-ttu-id="bb04b-112">パートナー オーケストレーションの直接バインド ポート上の送信メッセージは、対象とする受信者のオーケストレーションに送信でき、パートナー オーケストレーションの直接バインド ポート上の受信メッセージは、目的とする送信者のオーケストレーションから受信できます。</span><span class="sxs-lookup"><span data-stu-id="bb04b-112">Messages sent on a partner orchestration direct bound port can be sent to an intended recipient orchestration, and messages received on a partner orchestration direct bound port can be received from an intended sender orchestration.</span></span>  
  
 <span data-ttu-id="bb04b-113">直接バインドでは、メッセージがオーケストレーションから別のオーケストレーションへ直接送信されるように見えますが、実際には、どの種類の論理ポート経由であっても、送信されるすべてのメッセージは常にメッセージ ボックス データベースを介して伝達されます。</span><span class="sxs-lookup"><span data-stu-id="bb04b-113">Although with direct binding, the message appears to go directly from one orchestration to another, in fact any message sent through any type of logical port always travels through the MessageBox database.</span></span> <span data-ttu-id="bb04b-114">また、直接バインド ポートは単なる論理ポートなので、直接バインドはデザイン時の構成機能でしかありません。</span><span class="sxs-lookup"><span data-stu-id="bb04b-114">Moreover, direct bound ports are only logical ports and therefore direct binding is only a design-time configuration feature.</span></span> <span data-ttu-id="bb04b-115">直接バインド ポートを物理ポートにバインドすることはできず、デザイン時に、直接バインドの構成を変更できるだけです。</span><span class="sxs-lookup"><span data-stu-id="bb04b-115">A direct bound port cannot be bound to a physical port, and you can only change the direct binding configuration at design time.</span></span>  
  
## <a name="in-this-section"></a><span data-ttu-id="bb04b-116">このセクションの内容</span><span class="sxs-lookup"><span data-stu-id="bb04b-116">In This Section</span></span>  
  
-   [<span data-ttu-id="bb04b-117">メッセージ ボックスの直接バインド ポートを使用する方法</span><span class="sxs-lookup"><span data-stu-id="bb04b-117">How to Use MessageBox Direct Bound Ports</span></span>](../core/how-to-use-messagebox-direct-bound-ports.md)  
  
-   [<span data-ttu-id="bb04b-118">自己関連付けを行う Direct を使用する方法のポートのバインド</span><span class="sxs-lookup"><span data-stu-id="bb04b-118">How to Use Self-Correlating Direct Bound Ports</span></span>](../core/how-to-use-self-correlating-direct-bound-ports.md)  
  
-   [<span data-ttu-id="bb04b-119">パートナー オーケストレーション直接バインド ポートを使用する方法</span><span class="sxs-lookup"><span data-stu-id="bb04b-119">How to Use Partner Orchestration Direct Bound Ports</span></span>](../core/how-to-use-partner-orchestration-direct-bound-ports.md)  
  
## <a name="see-also"></a><span data-ttu-id="bb04b-120">参照</span><span class="sxs-lookup"><span data-stu-id="bb04b-120">See Also</span></span>  
 [<span data-ttu-id="bb04b-121">ポートのバインド</span><span class="sxs-lookup"><span data-stu-id="bb04b-121">Port Bindings</span></span>](../core/port-bindings.md)