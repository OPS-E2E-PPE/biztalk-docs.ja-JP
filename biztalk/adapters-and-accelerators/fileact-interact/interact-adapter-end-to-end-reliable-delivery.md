---
title: アダプターのエンド ツー エンドの信頼性の高い配信を対話 |Microsoft Docs
ms.custom: ''
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: ''
ms.suite: ''
ms.tgt_pltfrm: ''
ms.topic: article
ms.assetid: ac7c22f2-ee4a-4e9b-af40-da7eb58daf51
caps.latest.revision: 4
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: 3b2d7ccacde04243c2635bbe5adcafad3f2b9987
ms.sourcegitcommit: 381e83d43796a345488d54b3f7413e11d56ad7be
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 05/07/2019
ms.locfileid: "65366700"
---
# <a name="interact-adapter-end-to-end-reliable-delivery"></a><span data-ttu-id="2a906-102">アダプターのエンド ツー エンドの信頼性の高い配信を操作します。</span><span class="sxs-lookup"><span data-stu-id="2a906-102">InterAct Adapter End-to-End Reliable Delivery</span></span>
<span data-ttu-id="2a906-103">受信者にメッセージやファイルを送信するときに、メッセージやファイルを配信できる、およびこれらに含まれているトランザクションではいいえ回を実行よりもビジネスが予想を必ず確認することをお勧めします。</span><span class="sxs-lookup"><span data-stu-id="2a906-103">When sending messages or files to a recipient, we recommend that you ensure that the message or file is delivered, and that the business transaction(s) contained in these are executed no more times than anticipated.</span></span>  
  
 <span data-ttu-id="2a906-104">簡単に場合は、信頼性の高い配信を実装できますが互いと通信する 2 つのエンティティは、(たとえば、永続的なメッセージ指向ミドルウェアおよび使用するインターフェイス アプリケーションによって提供される) 永続的なストレージを使用することができます、ときに通信する方法、メッセージの状態が認識されるを標準化します。</span><span class="sxs-lookup"><span data-stu-id="2a906-104">When both entities communicating with each other can use a persistent storage (for example, provided by a persistent message-oriented middleware and an interface application using it), it is easy to implement a reliable delivery if the way to communicate the perceived status of the message is standardized.</span></span>  
  
 <span data-ttu-id="2a906-105">次の図は、E2EControl の構造の例を示します。</span><span class="sxs-lookup"><span data-stu-id="2a906-105">The following figure shows an example of the structure of the E2EControl.</span></span>  
  
 <span data-ttu-id="2a906-106">![終了&#45;に&#45;コントロールの終了](../../adapters-and-accelerators/fileact-interact/media/63e39b43-118e-4572-9d75-21770253a1ee.gif "63e39b43-118e-4572-9d75-21770253a1ee")</span><span class="sxs-lookup"><span data-stu-id="2a906-106">![End&#45;to&#45;end control](../../adapters-and-accelerators/fileact-interact/media/63e39b43-118e-4572-9d75-21770253a1ee.gif "63e39b43-118e-4572-9d75-21770253a1ee")</span></span>  
  
 <span data-ttu-id="2a906-107">図に示す例では、要素は、SwInt:Request 内で送信され、受信アプリケーションに SwInt:RequestHandle 内でそのまま配信。</span><span class="sxs-lookup"><span data-stu-id="2a906-107">The element in the example shown in the figure is sent within the SwInt:Request and delivered unchanged within the SwInt:RequestHandle to the receiving application.</span></span> <span data-ttu-id="2a906-108">02 の行では、要求に一意の識別子を割り当てることができます。</span><span class="sxs-lookup"><span data-stu-id="2a906-108">Line 02 allows assigning a unique identifier to the request.</span></span> <span data-ttu-id="2a906-109">この一意の識別子が同じ要求の各後続の再送信に繰り返されます。</span><span class="sxs-lookup"><span data-stu-id="2a906-109">This unique identifier is repeated in each subsequent re-transmission of the same request.</span></span>  
  
 <span data-ttu-id="2a906-110">この識別子を構築する方法は、実装者は、左しますが、uuidgen() などのシステム コールに基づいて通常または送信される要求に sha-1 の計算結果がある可能性があります (プレフィックスの付いた Sw:MsgId と置き換えます、base64 でエンコードされた sha-1 s文字列の場合)。</span><span class="sxs-lookup"><span data-stu-id="2a906-110">The way this identifier is constructed is left to the implementer, but typically it is based on a system call such as uuidgen(), or it may be the result of computing a SHA-1 on the request to be sent (with a prefixed Sw:MsgId and then replace it by the base64 encoded SHA-1 string).</span></span> <span data-ttu-id="2a906-111">主な要件は、(非常に高い確率) でグローバルに一意であります。</span><span class="sxs-lookup"><span data-stu-id="2a906-111">The main requirement is that it is globally unique (with a very high probability).</span></span>  
  
 <span data-ttu-id="2a906-112">Sw:CreationTime は、元の要求の作成の時間です。</span><span class="sxs-lookup"><span data-stu-id="2a906-112">The Sw:CreationTime is the time of creation of the original request.</span></span> <span data-ttu-id="2a906-113">オプションのパラメーターが、このメッセージの前の通信の試行の最終的な検索を制限すると便利です。</span><span class="sxs-lookup"><span data-stu-id="2a906-113">It is an optional parameter, but it is useful to limit eventual searches for previous communication attempts of this message.</span></span>  
  
 <span data-ttu-id="2a906-114">Sw:PDIndication 要素では、2 台目またはメッセージの送信試行をさらにこれがある存在します。</span><span class="sxs-lookup"><span data-stu-id="2a906-114">The element Sw:PDIndication is present to indicate that this is a second or further attempt to transmit the message.</span></span> <span data-ttu-id="2a906-115">E2EControl を認識する受信側アプリケーションは、メッセージが受信されたかどうかどうかを検索するのに、Sw:MsgId を使用できます。</span><span class="sxs-lookup"><span data-stu-id="2a906-115">The receiving application that is aware of the E2EControl can then use the Sw:MsgId to find back whether the message has been received or not.</span></span> <span data-ttu-id="2a906-116">省略可能な Sw:EmissionList には、前の試行の時間が含まれています。</span><span class="sxs-lookup"><span data-stu-id="2a906-116">The optional Sw:EmissionList contains the time of the previous attempts.</span></span> <span data-ttu-id="2a906-117">この時間はローカル時刻 (世界協定時刻) の送信者の Sw:GetDateTime 関数を使用する場合は、送信側が必要があります。</span><span class="sxs-lookup"><span data-stu-id="2a906-117">This time is the local time of the sender (in universal time) as got by the Sender when using the Sw:GetDateTime function.</span></span> <span data-ttu-id="2a906-118">もう一度これが検索の制限に役立つことでした。</span><span class="sxs-lookup"><span data-stu-id="2a906-118">Again this could be useful to limit searches.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="2a906-119">参照</span><span class="sxs-lookup"><span data-stu-id="2a906-119">See Also</span></span>  
 <span data-ttu-id="2a906-120">[InterAct アダプターのアーキテクチャ](../../adapters-and-accelerators/fileact-interact/interact-adapter-architecture.md) </span><span class="sxs-lookup"><span data-stu-id="2a906-120">[InterAct Adapter Architecture](../../adapters-and-accelerators/fileact-interact/interact-adapter-architecture.md) </span></span>  
 <span data-ttu-id="2a906-121">[InterAct アダプターのコンポーネント](../../adapters-and-accelerators/fileact-interact/interact-adapter-components.md) </span><span class="sxs-lookup"><span data-stu-id="2a906-121">[InterAct Adapter Components](../../adapters-and-accelerators/fileact-interact/interact-adapter-components.md) </span></span>  
 <span data-ttu-id="2a906-122">[業務用 Exchange 用の interAct アダプターのメッセージ](../../adapters-and-accelerators/fileact-interact/interact-adapter-messages-for-business-exchange.md) </span><span class="sxs-lookup"><span data-stu-id="2a906-122">[InterAct Adapter Messages for Business Exchange](../../adapters-and-accelerators/fileact-interact/interact-adapter-messages-for-business-exchange.md) </span></span>  
 <span data-ttu-id="2a906-123">[InterAct アダプターのクライアント アプリケーション](../../adapters-and-accelerators/fileact-interact/interact-adapter-client-application.md) </span><span class="sxs-lookup"><span data-stu-id="2a906-123">[InterAct Adapter Client Application](../../adapters-and-accelerators/fileact-interact/interact-adapter-client-application.md) </span></span>  
 <span data-ttu-id="2a906-124">[InterAct アダプタ サーバー アプリケーション](../../adapters-and-accelerators/fileact-interact/interact-adapter-server-application.md) </span><span class="sxs-lookup"><span data-stu-id="2a906-124">[InterAct Adapter Server Application](../../adapters-and-accelerators/fileact-interact/interact-adapter-server-application.md) </span></span>  
 <span data-ttu-id="2a906-125">[InterAct アダプター ストア アンド フォワード](../../adapters-and-accelerators/fileact-interact/interact-adapter-store-and-forward.md) </span><span class="sxs-lookup"><span data-stu-id="2a906-125">[InterAct Adapter Store and Forward](../../adapters-and-accelerators/fileact-interact/interact-adapter-store-and-forward.md) </span></span>  
 <span data-ttu-id="2a906-126">[InterAct アダプターのセキュリティ アーキテクチャ](../../adapters-and-accelerators/fileact-interact/interact-adapter-security-architecture.md) </span><span class="sxs-lookup"><span data-stu-id="2a906-126">[InterAct Adapter Security Architecture](../../adapters-and-accelerators/fileact-interact/interact-adapter-security-architecture.md) </span></span>  
 <span data-ttu-id="2a906-127">[InterAct アダプターの状態の監視](../../adapters-and-accelerators/fileact-interact/interact-adapter-status-monitoring.md) </span><span class="sxs-lookup"><span data-stu-id="2a906-127">[InterAct Adapter Status Monitoring](../../adapters-and-accelerators/fileact-interact/interact-adapter-status-monitoring.md) </span></span>  
 [<span data-ttu-id="2a906-128">InterAct アダプターの否認不可</span><span class="sxs-lookup"><span data-stu-id="2a906-128">InterAct Adapter Non-Repudiation</span></span>](../../adapters-and-accelerators/fileact-interact/interact-adapter-non-repudiation.md)