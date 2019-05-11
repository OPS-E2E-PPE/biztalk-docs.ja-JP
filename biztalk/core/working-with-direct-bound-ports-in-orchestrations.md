---
title: オーケストレーションでの直接バインド ポートの操作 |Microsoft Docs
ms.custom: ''
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: ''
ms.suite: ''
ms.tgt_pltfrm: ''
ms.topic: article
ms.assetid: 03a37ac0-5131-4d37-b60b-56763c460463
caps.latest.revision: 9
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: 3344298fbd569d1e8e3161d6857bddb6fb453aeb
ms.sourcegitcommit: 381e83d43796a345488d54b3f7413e11d56ad7be
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 05/07/2019
ms.locfileid: "65277287"
---
# <a name="working-with-direct-bound-ports-in-orchestrations"></a><span data-ttu-id="9cafd-102">オーケストレーションでの直接バインド ポートの操作</span><span class="sxs-lookup"><span data-stu-id="9cafd-102">Working with Direct Bound Ports in Orchestrations</span></span>
<span data-ttu-id="9cafd-103">直接バインド ポートには次の 3 種類があります。メッセージ ボックス、自己関連付けを行う、パートナー オーケストレーションとします。</span><span class="sxs-lookup"><span data-stu-id="9cafd-103">There are three types of direct bound ports: MessageBox, self-correlating, and partner orchestration.</span></span>  
  
 <span data-ttu-id="9cafd-104">メッセージ ボックスの直接バインド ポートでは、発行/サブスクライブ デザイン パターン。</span><span class="sxs-lookup"><span data-stu-id="9cafd-104">MessageBox direct bound ports allow for publish-subscribe design patterns.</span></span> <span data-ttu-id="9cafd-105">メッセージ ボックスの直接バインド ポートで送信されるメッセージは、メッセージの受信者により取得サブスクリプションに基づいて、メッセージ ボックス データベースに発行されます。</span><span class="sxs-lookup"><span data-stu-id="9cafd-105">Messages sent on a MessageBox direct bound port are published to the MessageBox database, where message recipients pick them up based on subscriptions.</span></span> <span data-ttu-id="9cafd-106">論理演算には、メッセージ ボックスの直接バインド ポートは、メッセージ ボックス データベースから直接メッセージを取得するように構成されたポートが表示されます。</span><span class="sxs-lookup"><span data-stu-id="9cafd-106">Logical receive ports configured as MessageBox direct bound ports get messages directly from the MessageBox database.</span></span> <span data-ttu-id="9cafd-107">アクティブ化のため**受信**図形、メッセージ ボックスの直接バインド受信メッセージの種類とフィルター式へのサブスクリプションを通じてメッセージをポートを取得します。</span><span class="sxs-lookup"><span data-stu-id="9cafd-107">For activating **Receive** shapes, the MessageBox direct bound receive ports get the messages through subscriptions to the message type and the filter expression.</span></span> <span data-ttu-id="9cafd-108">非アクティブ化の**受信**図形、メッセージ ボックスの直接バインド受信メッセージの種類および関連付けセットへのサブスクリプションを通じてメッセージをポートを取得します。</span><span class="sxs-lookup"><span data-stu-id="9cafd-108">For non-activating **Receive** shapes, the MessageBox direct bound receive ports get the messages through subscriptions to the message type and the correlation set.</span></span>  
  
 <span data-ttu-id="9cafd-109">自己関連付けを行う直接バインド ポートは、非同期のオーケストレーション間通信の設計に役立ちます。</span><span class="sxs-lookup"><span data-stu-id="9cafd-109">Self-correlating direct bound ports assist you in designing asynchronous inter-orchestration communication.</span></span> <span data-ttu-id="9cafd-110">自己関連付けを行う直接バインド ポートに送信されるメッセージは、相関自己の直接バインド ポートの受信側を作成したオーケストレーションのインスタンスにルーティングされます。</span><span class="sxs-lookup"><span data-stu-id="9cafd-110">Messages sent to a self-correlating direct bound port are routed to the instance of the orchestration that created the receiving end of the self-correlated direct bound port.</span></span>  
  
 <span data-ttu-id="9cafd-111">パートナー オーケストレーションの直接バインド ポートをオーケストレーション間通信を提供します。</span><span class="sxs-lookup"><span data-stu-id="9cafd-111">Partner orchestration direct bound ports provide for inter-orchestration communication.</span></span> <span data-ttu-id="9cafd-112">目的の送信者のオーケストレーションからの直接バインド ポートは、目的の受信者のオーケストレーションに送信できるパートナー オーケストレーションの送信されたメッセージとパートナー オーケストレーションの直接バインド ポートで受信したメッセージを受信できます。</span><span class="sxs-lookup"><span data-stu-id="9cafd-112">Messages sent on a partner orchestration direct bound port can be sent to an intended recipient orchestration, and messages received on a partner orchestration direct bound port can be received from an intended sender orchestration.</span></span>  
  
 <span data-ttu-id="9cafd-113">進むには 1 つのオーケストレーションから直接、実際にを通じて送信されるメッセージに直接バインドでメッセージが表示されますが、任意の種類の論理ポートは常にメッセージ ボックス データベースを通過します。</span><span class="sxs-lookup"><span data-stu-id="9cafd-113">Although with direct binding, the message appears to go directly from one orchestration to another, in fact any message sent through any type of logical port always travels through the MessageBox database.</span></span> <span data-ttu-id="9cafd-114">さらに、直接バインド ポートは単なる論理ポートと、したがってバインディングは、デザイン時構成機能だけがリダイレクトされます。</span><span class="sxs-lookup"><span data-stu-id="9cafd-114">Moreover, direct bound ports are only logical ports and therefore direct binding is only a design-time configuration feature.</span></span> <span data-ttu-id="9cafd-115">直接バインド ポートを物理ポートにバインドできませんし、デザイン時に直接バインドの構成のみを変更できます。</span><span class="sxs-lookup"><span data-stu-id="9cafd-115">A direct bound port cannot be bound to a physical port, and you can only change the direct binding configuration at design time.</span></span>  
  
## <a name="in-this-section"></a><span data-ttu-id="9cafd-116">このセクションの内容</span><span class="sxs-lookup"><span data-stu-id="9cafd-116">In This Section</span></span>  
  
-   [<span data-ttu-id="9cafd-117">メッセージ ボックスの直接バインド ポートを使用する方法</span><span class="sxs-lookup"><span data-stu-id="9cafd-117">How to Use MessageBox Direct Bound Ports</span></span>](../core/how-to-use-messagebox-direct-bound-ports.md)  
  
-   [<span data-ttu-id="9cafd-118">自己関連付けを行う Direct を使用する方法のポートのバインド</span><span class="sxs-lookup"><span data-stu-id="9cafd-118">How to Use Self-Correlating Direct Bound Ports</span></span>](../core/how-to-use-self-correlating-direct-bound-ports.md)  
  
-   [<span data-ttu-id="9cafd-119">パートナー オーケストレーション直接バインド ポートの使用方法</span><span class="sxs-lookup"><span data-stu-id="9cafd-119">How to Use Partner Orchestration Direct Bound Ports</span></span>](../core/how-to-use-partner-orchestration-direct-bound-ports.md)  
  
## <a name="see-also"></a><span data-ttu-id="9cafd-120">参照</span><span class="sxs-lookup"><span data-stu-id="9cafd-120">See Also</span></span>  
 [<span data-ttu-id="9cafd-121">ポートのバインド</span><span class="sxs-lookup"><span data-stu-id="9cafd-121">Port Bindings</span></span>](../core/port-bindings.md)