---
title: FileAct アダプターのリアルタイム ローカル プリミティブ |Microsoft Docs
ms.custom: ''
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: ''
ms.suite: ''
ms.tgt_pltfrm: ''
ms.topic: article
ms.assetid: ef4da4f8-3de2-4d35-8f8a-1e12937e52a1
caps.latest.revision: 4
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: ac26a598dad808908b6be1b9fe7ecff3ed1f9f6e
ms.sourcegitcommit: 381e83d43796a345488d54b3f7413e11d56ad7be
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 05/07/2019
ms.locfileid: "65367184"
---
# <a name="fileact-adapter-real-time-local-primitives"></a><span data-ttu-id="3d4ea-102">FileAct アダプターのリアルタイム ローカル プリミティブ</span><span class="sxs-lookup"><span data-stu-id="3d4ea-102">FileAct Adapter Real-Time Local Primitives</span></span>
<span data-ttu-id="3d4ea-103">ローカル プリミティブでは、2 つのメッセージ、各クライアント SWIFTNet リンク (SNL) とローカル FileAct サブシステム間で交換される必要があります。</span><span class="sxs-lookup"><span data-stu-id="3d4ea-103">Local primitives involve two messages each, which are exchanged between the client SWIFTNet Link (SNL) and the local FileAct subsystem.</span></span>  
  
 <span data-ttu-id="3d4ea-104">FileAct ローカル プリミティブの図は、次のとおりです。</span><span class="sxs-lookup"><span data-stu-id="3d4ea-104">The following figure shows the FileAct local primitives.</span></span>  
  
 <span data-ttu-id="3d4ea-105">![FileAct ローカル プリミティブ](../../adapters-and-accelerators/fileact-interact/media/67ca0c3b-3c81-401d-87cb-473c68cae63f.gif "67ca0c3b-3c81-401d-87cb-473c68cae63f")</span><span class="sxs-lookup"><span data-stu-id="3d4ea-105">![FileAct local primitives](../../adapters-and-accelerators/fileact-interact/media/67ca0c3b-3c81-401d-87cb-473c68cae63f.gif "67ca0c3b-3c81-401d-87cb-473c68cae63f")</span></span>  
  
## <a name="get-status-for-a-single-transfer"></a><span data-ttu-id="3d4ea-106">1 つの転送の状態を取得します。</span><span class="sxs-lookup"><span data-stu-id="3d4ea-106">Get Status for a Single Transfer</span></span>  
 <span data-ttu-id="3d4ea-107">Get Status がプリミティブでは、ローカル永続的なコンテキストから 1 つの転送に関するステータス情報を取得します。</span><span class="sxs-lookup"><span data-stu-id="3d4ea-107">The Get Status primitive retrieves status information concerning one transfer from the local persistent context.</span></span>  
  
## <a name="subscribe-to-transfer-events"></a><span data-ttu-id="3d4ea-108">イベントの転送を購読します。</span><span class="sxs-lookup"><span data-stu-id="3d4ea-108">Subscribe to Transfer Events</span></span>  
 <span data-ttu-id="3d4ea-109">イベントのサブスクライブ プリミティブを使用してでは、イベントごとのイベントごとにプログレッシブ転送状態情報を受信する可能性があります。</span><span class="sxs-lookup"><span data-stu-id="3d4ea-109">Progressive transfer status information may be received on an event-by-event basis by using the Subscribe Event primitive.</span></span> <span data-ttu-id="3d4ea-110">各ファイルの転送は、ネゴシエーション中にイベント エンドポイントと呼ばれる名前付きエンティティにリンクすることがあります。</span><span class="sxs-lookup"><span data-stu-id="3d4ea-110">Each file transfer may be linked to a named entity called an event endpoint during the negotiation.</span></span> <span data-ttu-id="3d4ea-111">イベントのサブスクライブ プリミティブを呼び出すイベント サーバーは、1 つのようなイベント エンドポイント自体にすべてのイベント レポートを指示します。</span><span class="sxs-lookup"><span data-stu-id="3d4ea-111">An event server that invokes the Subscribe Event primitive directs all the event reports for one such an event endpoint to itself.</span></span>  
  
 <span data-ttu-id="3d4ea-112">イベント、サーバーは、特性 (さまざまなレベルの詳細のほか、さまざまなイベントの種類) にサブスクライブできます。</span><span class="sxs-lookup"><span data-stu-id="3d4ea-112">An event server can subscribe to characteristics (different levels of detail, as well as to different event types).</span></span>  
  
 <span data-ttu-id="3d4ea-113">イベント、サーバーは、イベントの複数のエンドポイントにサブスクライブするプリミティブ複数回を呼び出す可能性があります。</span><span class="sxs-lookup"><span data-stu-id="3d4ea-113">An event server may invoke the primitive multiple times to subscribe to multiple event endpoints.</span></span> <span data-ttu-id="3d4ea-114">サーバーの 1 つのみのイベントは、特定の時点で任意のエンドポイントの特定のイベントを定期受信できます。</span><span class="sxs-lookup"><span data-stu-id="3d4ea-114">Only one event server may subscribe to any particular event endpoint at a given time.</span></span> <span data-ttu-id="3d4ea-115">さらに、イベントのサーバーを呼び出すことができます、プリミティブ型の特性を変更するため、同じイベント エンドポイントを複数回。</span><span class="sxs-lookup"><span data-stu-id="3d4ea-115">Additionally, an event server can invoke the primitive multiple times for the same event endpoint for changing the characteristics.</span></span>  
  
## <a name="receive-transfer-events"></a><span data-ttu-id="3d4ea-116">転送イベントを受信します。</span><span class="sxs-lookup"><span data-stu-id="3d4ea-116">Receive Transfer Events</span></span>  
 <span data-ttu-id="3d4ea-117">受信イベントの転送が進行中の転送に関するイベントの状態情報を処理するプリミティブ。</span><span class="sxs-lookup"><span data-stu-id="3d4ea-117">Receive Transfer Events is the primitive that handles the event-by-event status information concerning transfers-in-progress.</span></span> <span data-ttu-id="3d4ea-118">設定されているイベントのサブスクライブがプリミティブ サブスクリプションの条件に応答します。</span><span class="sxs-lookup"><span data-stu-id="3d4ea-118">It responds to the terms of a subscription that is set up by the Subscribe Event primitive.</span></span> <span data-ttu-id="3d4ea-119">このプリミティブは、転送の送信または受信側に実装できます。</span><span class="sxs-lookup"><span data-stu-id="3d4ea-119">This primitive can be implemented at the sending or receiving side of a transfer.</span></span>  
  
## <a name="abort-transfer"></a><span data-ttu-id="3d4ea-120">転送を中止します。</span><span class="sxs-lookup"><span data-stu-id="3d4ea-120">Abort Transfer</span></span>  
 <span data-ttu-id="3d4ea-121">ユーザー アプリケーションは、転送の実行中の中止のプリミティブを使用してを中止可能性があります。</span><span class="sxs-lookup"><span data-stu-id="3d4ea-121">A user application may abort a transfer-in-progress using the Abort primitive.</span></span> <span data-ttu-id="3d4ea-122">中止プリミティブは、プリミティブを送信側または進行中の転送の受信側のいずれかから実行することがあります。</span><span class="sxs-lookup"><span data-stu-id="3d4ea-122">The Abort primitive is a primitive that may be exercised from either the sending-side or the receiving-side of a transfer-in-progress.</span></span> <span data-ttu-id="3d4ea-123">開始するか、転送を受け入れ、それぞれの側によって独自の側からその転送を保護するアクセス キーとして使用される転送キーを確立するオプションがあります。</span><span class="sxs-lookup"><span data-stu-id="3d4ea-123">When initiating or accepting a transfer, each side has the option of establishing a transfer key that serves as an access key to protect that transfer from its own side.</span></span> <span data-ttu-id="3d4ea-124">進行中の転送の転送キーを確立している場合に停止できません側から中止プリミティブの演習では、転送のキー値を指定せずします。</span><span class="sxs-lookup"><span data-stu-id="3d4ea-124">If a transfer key is established for a transfer-in-progress, it may not be aborted from that side without supplying the transfer key value in the exercise of the Abort primitive.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="3d4ea-125">参照</span><span class="sxs-lookup"><span data-stu-id="3d4ea-125">See Also</span></span>  
 <span data-ttu-id="3d4ea-126">[FileAct アダプターのアーキテクチャ](../../adapters-and-accelerators/fileact-interact/fileact-adapter-architecture.md) </span><span class="sxs-lookup"><span data-stu-id="3d4ea-126">[FileAct Adapter Architecture](../../adapters-and-accelerators/fileact-interact/fileact-adapter-architecture.md) </span></span>  
 <span data-ttu-id="3d4ea-127">[FileAct アダプターのリアルタイム エンド ツー エンド プリミティブ](../../adapters-and-accelerators/fileact-interact/fileact-adapter-real-time-end-to-end-primitives.md) </span><span class="sxs-lookup"><span data-stu-id="3d4ea-127">[FileAct Adapter Real-Time End-to-End Primitives](../../adapters-and-accelerators/fileact-interact/fileact-adapter-real-time-end-to-end-primitives.md) </span></span>  
 <span data-ttu-id="3d4ea-128">[FileAct アダプターのストア アンド フォワード](../../adapters-and-accelerators/fileact-interact/fileact-adapter-store-and-forward.md) </span><span class="sxs-lookup"><span data-stu-id="3d4ea-128">[FileAct Adapter Store and Forward](../../adapters-and-accelerators/fileact-interact/fileact-adapter-store-and-forward.md) </span></span>  
 <span data-ttu-id="3d4ea-129">[FileAct アダプターのセキュリティ アーキテクチャ](../../adapters-and-accelerators/fileact-interact/fileact-adapter-security-architecture.md) </span><span class="sxs-lookup"><span data-stu-id="3d4ea-129">[FileAct Adapter Security Architecture](../../adapters-and-accelerators/fileact-interact/fileact-adapter-security-architecture.md) </span></span>  
 <span data-ttu-id="3d4ea-130">[FileAct アダプター ファイルおよび転送 Id](../../adapters-and-accelerators/fileact-interact/fileact-adapter-file-and-transfer-identification.md) </span><span class="sxs-lookup"><span data-stu-id="3d4ea-130">[FileAct Adapter File and Transfer Identification](../../adapters-and-accelerators/fileact-interact/fileact-adapter-file-and-transfer-identification.md) </span></span>  
 <span data-ttu-id="3d4ea-131">[FileAct アダプターのサポート情報の転送](../../adapters-and-accelerators/fileact-interact/fileact-adapter-supporting-information-transfer.md) </span><span class="sxs-lookup"><span data-stu-id="3d4ea-131">[FileAct Adapter Supporting Information Transfer](../../adapters-and-accelerators/fileact-interact/fileact-adapter-supporting-information-transfer.md) </span></span>  
 <span data-ttu-id="3d4ea-132">[FileAct アダプターの配信通知](../../adapters-and-accelerators/fileact-interact/fileact-adapter-delivery-notification.md) </span><span class="sxs-lookup"><span data-stu-id="3d4ea-132">[FileAct Adapter Delivery Notification](../../adapters-and-accelerators/fileact-interact/fileact-adapter-delivery-notification.md) </span></span>  
 [<span data-ttu-id="3d4ea-133">FileAct アダプターの状態監視</span><span class="sxs-lookup"><span data-stu-id="3d4ea-133">FileAct Adapter Status Monitoring</span></span>](../../adapters-and-accelerators/fileact-interact/fileact-adapter-status-monitoring.md)