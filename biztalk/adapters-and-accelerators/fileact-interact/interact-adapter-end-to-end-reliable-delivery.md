---
title: "アダプターのエンド ツー エンドの信頼性の高い配信を対話 |Microsoft ドキュメント"
ms.custom: 
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: 
ms.suite: 
ms.tgt_pltfrm: 
ms.topic: article
ms.assetid: ac7c22f2-ee4a-4e9b-af40-da7eb58daf51
caps.latest.revision: "4"
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: 90ca0fc7ae5872598ed9a61cd7541017a6a39667
ms.sourcegitcommit: cb908c540d8f1a692d01dc8f313e16cb4b4e696d
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 09/20/2017
---
# <a name="interact-adapter-end-to-end-reliable-delivery"></a><span data-ttu-id="d74ac-102">アダプターのエンド ツー エンドの信頼性の高い配信を対話します。</span><span class="sxs-lookup"><span data-stu-id="d74ac-102">InterAct Adapter End-to-End Reliable Delivery</span></span>
<span data-ttu-id="d74ac-103">メッセージやファイルを受信者に送信するときに、メッセージやファイルが配信される、およびビジネスをより詳細度もいいえがこれらに含まれているトランザクションで実行が予想されることを確認することをお勧めします。</span><span class="sxs-lookup"><span data-stu-id="d74ac-103">When sending messages or files to a recipient, we recommend that you ensure that the message or file is delivered, and that the business transaction(s) contained in these are executed no more times than anticipated.</span></span>  
  
 <span data-ttu-id="d74ac-104">両方のエンティティが相互に通信は、(たとえば、永続的なメッセージ指向ミドルウェアおよび使用するインターフェイス アプリケーションによって提供される) 永続的な記憶域を使用することができますが簡単を信頼性の高い配信を実装する場合に通信する方法、メッセージの見かけ上の状態が標準化されています。</span><span class="sxs-lookup"><span data-stu-id="d74ac-104">When both entities communicating with each other can use a persistent storage (for example, provided by a persistent message-oriented middleware and an interface application using it), it is easy to implement a reliable delivery if the way to communicate the perceived status of the message is standardized.</span></span>  
  
 <span data-ttu-id="d74ac-105">次の図は、E2EControl の構造の例を示します。</span><span class="sxs-lookup"><span data-stu-id="d74ac-105">The following figure shows an example of the structure of the E2EControl.</span></span>  
  
 <span data-ttu-id="d74ac-106">![End &#45; へ (& a) #45; 終了コントロール](../../adapters-and-accelerators/fileact-interact/media/63e39b43-118e-4572-9d75-21770253a1ee.gif "63e39b43-118e-4572-9d75-21770253a1ee")</span><span class="sxs-lookup"><span data-stu-id="d74ac-106">![End&#45;to&#45;end control](../../adapters-and-accelerators/fileact-interact/media/63e39b43-118e-4572-9d75-21770253a1ee.gif "63e39b43-118e-4572-9d75-21770253a1ee")</span></span>  
  
 <span data-ttu-id="d74ac-107">図に示した例で要素が、SwInt:Request 内で送信され、受信アプリケーションに SwInt:RequestHandle 内で変更されていない配信します。</span><span class="sxs-lookup"><span data-stu-id="d74ac-107">The element in the example shown in the figure is sent within the SwInt:Request and delivered unchanged within the SwInt:RequestHandle to the receiving application.</span></span> <span data-ttu-id="d74ac-108">02 の行では、要求に一意の識別子を割り当てることができます。</span><span class="sxs-lookup"><span data-stu-id="d74ac-108">Line 02 allows assigning a unique identifier to the request.</span></span> <span data-ttu-id="d74ac-109">この一意識別子は、同じ要求の後各再送信に繰り返されます。</span><span class="sxs-lookup"><span data-stu-id="d74ac-109">This unique identifier is repeated in each subsequent re-transmission of the same request.</span></span>  
  
 <span data-ttu-id="d74ac-110">この識別子を構築する方法は、実装者に左しますが、uuidgen() などのシステム コールに基づいている通常または要求を送信する sha-1 の計算結果がある可能性があります (プレフィックスの付いた Sw:MsgId とし、置換を使用して、base64 でエンコードされた sha-1 s単位)。</span><span class="sxs-lookup"><span data-stu-id="d74ac-110">The way this identifier is constructed is left to the implementer, but typically it is based on a system call such as uuidgen(), or it may be the result of computing a SHA-1 on the request to be sent (with a prefixed Sw:MsgId and then replace it by the base64 encoded SHA-1 string).</span></span> <span data-ttu-id="d74ac-111">主要な要件は、(確率が非常に高い) でグローバルに一意であります。</span><span class="sxs-lookup"><span data-stu-id="d74ac-111">The main requirement is that it is globally unique (with a very high probability).</span></span>  
  
 <span data-ttu-id="d74ac-112">Sw:CreationTime は、元の要求の作成の時間です。</span><span class="sxs-lookup"><span data-stu-id="d74ac-112">The Sw:CreationTime is the time of creation of the original request.</span></span> <span data-ttu-id="d74ac-113">これは、省略可能なパラメーターが、このメッセージの前の通信試行の最終的な検索を制限すると便利です。</span><span class="sxs-lookup"><span data-stu-id="d74ac-113">It is an optional parameter, but it is useful to limit eventual searches for previous communication attempts of this message.</span></span>  
  
 <span data-ttu-id="d74ac-114">Sw:PDIndication 要素は、2 台目またはそれ以上しようとすると、メッセージの転送は、このことを示すために存在します。</span><span class="sxs-lookup"><span data-stu-id="d74ac-114">The element Sw:PDIndication is present to indicate that this is a second or further attempt to transmit the message.</span></span> <span data-ttu-id="d74ac-115">E2EControl を認識する受信側のアプリケーションは、メッセージが受信されたかどうかどうかを検索するのに、Sw:MsgId を使用できます。</span><span class="sxs-lookup"><span data-stu-id="d74ac-115">The receiving application that is aware of the E2EControl can then use the Sw:MsgId to find back whether the message has been received or not.</span></span> <span data-ttu-id="d74ac-116">省略可能な Sw:EmissionList には、前の試行の時刻が含まれています。</span><span class="sxs-lookup"><span data-stu-id="d74ac-116">The optional Sw:EmissionList contains the time of the previous attempts.</span></span> <span data-ttu-id="d74ac-117">この時間では大文字と小文字が (世界時刻) 送信者のローカル時間 Sw:GetDateTime 関数を使用するときに、送信者によって取得したとします。</span><span class="sxs-lookup"><span data-stu-id="d74ac-117">This time is the local time of the sender (in universal time) as got by the Sender when using the Sw:GetDateTime function.</span></span> <span data-ttu-id="d74ac-118">もう一度検索を制限すると便利ですが考えられます。</span><span class="sxs-lookup"><span data-stu-id="d74ac-118">Again this could be useful to limit searches.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="d74ac-119">参照</span><span class="sxs-lookup"><span data-stu-id="d74ac-119">See Also</span></span>  
 <span data-ttu-id="d74ac-120">[アダプターのアーキテクチャを対話します。](../../adapters-and-accelerators/fileact-interact/interact-adapter-architecture.md) </span><span class="sxs-lookup"><span data-stu-id="d74ac-120">[InterAct Adapter Architecture](../../adapters-and-accelerators/fileact-interact/interact-adapter-architecture.md) </span></span>  
 <span data-ttu-id="d74ac-121">[InterAct アダプター コンポーネント](../../adapters-and-accelerators/fileact-interact/interact-adapter-components.md) </span><span class="sxs-lookup"><span data-stu-id="d74ac-121">[InterAct Adapter Components](../../adapters-and-accelerators/fileact-interact/interact-adapter-components.md) </span></span>  
 <span data-ttu-id="d74ac-122">[ビジネスの Exchange に対するアダプターのメッセージを相互作用します。](../../adapters-and-accelerators/fileact-interact/interact-adapter-messages-for-business-exchange.md) </span><span class="sxs-lookup"><span data-stu-id="d74ac-122">[InterAct Adapter Messages for Business Exchange](../../adapters-and-accelerators/fileact-interact/interact-adapter-messages-for-business-exchange.md) </span></span>  
 <span data-ttu-id="d74ac-123">[InterAct アダプターのクライアント アプリケーション](../../adapters-and-accelerators/fileact-interact/interact-adapter-client-application.md) </span><span class="sxs-lookup"><span data-stu-id="d74ac-123">[InterAct Adapter Client Application](../../adapters-and-accelerators/fileact-interact/interact-adapter-client-application.md) </span></span>  
 <span data-ttu-id="d74ac-124">[InterAct アダプタ サーバー アプリケーション](../../adapters-and-accelerators/fileact-interact/interact-adapter-server-application.md) </span><span class="sxs-lookup"><span data-stu-id="d74ac-124">[InterAct Adapter Server Application](../../adapters-and-accelerators/fileact-interact/interact-adapter-server-application.md) </span></span>  
 <span data-ttu-id="d74ac-125">[アダプター ストア アンド フォワードを対話します。](../../adapters-and-accelerators/fileact-interact/interact-adapter-store-and-forward.md) </span><span class="sxs-lookup"><span data-stu-id="d74ac-125">[InterAct Adapter Store and Forward](../../adapters-and-accelerators/fileact-interact/interact-adapter-store-and-forward.md) </span></span>  
 <span data-ttu-id="d74ac-126">[アダプターのセキュリティ アーキテクチャを対話します。](../../adapters-and-accelerators/fileact-interact/interact-adapter-security-architecture.md) </span><span class="sxs-lookup"><span data-stu-id="d74ac-126">[InterAct Adapter Security Architecture](../../adapters-and-accelerators/fileact-interact/interact-adapter-security-architecture.md) </span></span>  
 <span data-ttu-id="d74ac-127">[アダプターの状態を操作の監視](../../adapters-and-accelerators/fileact-interact/interact-adapter-status-monitoring.md) </span><span class="sxs-lookup"><span data-stu-id="d74ac-127">[InterAct Adapter Status Monitoring](../../adapters-and-accelerators/fileact-interact/interact-adapter-status-monitoring.md) </span></span>  
 [<span data-ttu-id="d74ac-128">アダプター否認不可を対話します。</span><span class="sxs-lookup"><span data-stu-id="d74ac-128">InterAct Adapter Non-Repudiation</span></span>](../../adapters-and-accelerators/fileact-interact/interact-adapter-non-repudiation.md)