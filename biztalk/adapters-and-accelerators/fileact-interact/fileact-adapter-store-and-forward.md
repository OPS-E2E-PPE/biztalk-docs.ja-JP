---
title: "FileAct アダプター ストア アンド フォワード |Microsoft ドキュメント"
ms.custom: 
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: 
ms.suite: 
ms.tgt_pltfrm: 
ms.topic: article
ms.assetid: 50110bf0-75c2-426c-9833-65c3117224b2
caps.latest.revision: "6"
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: 1201a5ab5cb45ceba2622aa1c269404acec910df
ms.sourcegitcommit: cb908c540d8f1a692d01dc8f313e16cb4b4e696d
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 09/20/2017
---
# <a name="fileact-adapter-store-and-forward"></a><span data-ttu-id="43272-102">FileAct アダプター ストア アンド フォワード</span><span class="sxs-lookup"><span data-stu-id="43272-102">FileAct Adapter Store and Forward</span></span>
<span data-ttu-id="43272-103">ストアで順方向 (SnF) モードでは、ファイルに配信されると送信時に queue され、変換先にキューから取得されます。</span><span class="sxs-lookup"><span data-stu-id="43272-103">In Store and Forward (SnF) mode, files are delivered to queue at send time, and are retrieved from the queue by the destination.</span></span> <span data-ttu-id="43272-104">中間応答は、ファイルが変換先に安全に配信されるまでに、SWIFTNet によって送信者に返されます。</span><span class="sxs-lookup"><span data-stu-id="43272-104">Intermediate responses are returned by SWIFTNet to the sender until the file is safely delivered to the destination.</span></span>  
  
## <a name="sending-using-snf"></a><span data-ttu-id="43272-105">SnF を使用して送信します。</span><span class="sxs-lookup"><span data-stu-id="43272-105">Sending Using SnF</span></span>  
 <span data-ttu-id="43272-106">一方向の送信ポートを作成する場合、アダプターは SnF モードで動作し、キューにメッセージを送信します。</span><span class="sxs-lookup"><span data-stu-id="43272-106">If you create a one-way send port, the adapter works in SnF mode and sends messages to the queue.</span></span>  
  
## <a name="receiving-using-snf"></a><span data-ttu-id="43272-107">SnF を使用して受信</span><span class="sxs-lookup"><span data-stu-id="43272-107">Receiving Using SnF</span></span>  
 <span data-ttu-id="43272-108">SnF FileAct は、プッシュ モードで動作します。</span><span class="sxs-lookup"><span data-stu-id="43272-108">SnF FileAct operates in Push mode.</span></span> <span data-ttu-id="43272-109">これは、実行時オプションです。</span><span class="sxs-lookup"><span data-stu-id="43272-109">This is a run-time option.</span></span>  
  
 <span data-ttu-id="43272-110">キューからメッセージを取得できないようにするには、前に SWIFTNet SnF はキューを取得する要求を受信する必要があります。</span><span class="sxs-lookup"><span data-stu-id="43272-110">Before being able to retrieve messages from a queue, SWIFTNet SnF should receive a request to acquire the queue.</span></span> <span data-ttu-id="43272-111">これは、アウト オブ COM + コンポーネントを呼び出して、受信アダプターによって行います。</span><span class="sxs-lookup"><span data-stu-id="43272-111">This is accomplished by the receive adapter invoking the out-of-proc COM+ component.</span></span> <span data-ttu-id="43272-112">成功の取得後に、セッションが作成されます。</span><span class="sxs-lookup"><span data-stu-id="43272-112">After a successful acquire, a session is created.</span></span> <span data-ttu-id="43272-113">キューは、要求で指定されたモードで、開けません。</span><span class="sxs-lookup"><span data-stu-id="43272-113">The queue will then be opened in the mode specified in the Request.</span></span> <span data-ttu-id="43272-114">要求を発行した物理ノードに、すべてのメッセージが返されます。</span><span class="sxs-lookup"><span data-stu-id="43272-114">All messages will be returned to the physical node which issued the request.</span></span>  
  
 <span data-ttu-id="43272-115">(対話および FileAct 伝送の混在して、および優先度別に並べ替えることに注意)、指定された順序でメッセージが配信されます。ただし、メッセージのシーケンスが格納されている時間に左右されます。</span><span class="sxs-lookup"><span data-stu-id="43272-115">Messages are delivered in the order specified (note that InterAct and FileAct transmissions can be interspersed, and arranged by priority.) The sequencing of messages, however, is dependent on the time that they were stored.</span></span> <span data-ttu-id="43272-116">FileAct の場合これは、開始時ではなく、ファイル ストレージが完了した時刻です。</span><span class="sxs-lookup"><span data-stu-id="43272-116">In the case of FileAct, this is the time that the file storage is completed, not when it started.</span></span>  
  
### <a name="push-a-file-from-the-queue"></a><span data-ttu-id="43272-117">ファイルをプッシュするキューから</span><span class="sxs-lookup"><span data-stu-id="43272-117">Push a File From the Queue</span></span>  
 <span data-ttu-id="43272-118">FileAct アダプター (サーバー) では、キュー、セッション、およびシーケンスの情報を含む SWIFTNet から、HandleFileRequest を受信します。</span><span class="sxs-lookup"><span data-stu-id="43272-118">The FileAct adapter (server) receives a HandleFileRequest from SWIFTNet, containing the queue, session and sequence information.</span></span> <span data-ttu-id="43272-119">サーバーは、HandleFileResponse で応答します。</span><span class="sxs-lookup"><span data-stu-id="43272-119">The server responds with a HandleFileResponse.</span></span>  
  
 <span data-ttu-id="43272-120">FetchFileRequest は、サーバーから発行され、ファイルがサーバーに配信されます。</span><span class="sxs-lookup"><span data-stu-id="43272-120">The server then issues FetchFileRequest and the file is delivered to the server.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="43272-121">参照</span><span class="sxs-lookup"><span data-stu-id="43272-121">See Also</span></span>  
 <span data-ttu-id="43272-122">[FileAct アダプターのアーキテクチャ](../../adapters-and-accelerators/fileact-interact/fileact-adapter-architecture.md) </span><span class="sxs-lookup"><span data-stu-id="43272-122">[FileAct Adapter Architecture](../../adapters-and-accelerators/fileact-interact/fileact-adapter-architecture.md) </span></span>  
 <span data-ttu-id="43272-123">[FileAct アダプター リアルタイム エンド ツー エンド プリミティブ](../../adapters-and-accelerators/fileact-interact/fileact-adapter-real-time-end-to-end-primitives.md) </span><span class="sxs-lookup"><span data-stu-id="43272-123">[FileAct Adapter Real-Time End-to-End Primitives](../../adapters-and-accelerators/fileact-interact/fileact-adapter-real-time-end-to-end-primitives.md) </span></span>  
 <span data-ttu-id="43272-124">[FileAct アダプターのリアルタイム ローカル プリミティブ](../../adapters-and-accelerators/fileact-interact/fileact-adapter-real-time-local-primitives.md) </span><span class="sxs-lookup"><span data-stu-id="43272-124">[FileAct Adapter Real-Time Local Primitives](../../adapters-and-accelerators/fileact-interact/fileact-adapter-real-time-local-primitives.md) </span></span>  
 <span data-ttu-id="43272-125">[FileAct アダプターのセキュリティ アーキテクチャ](../../adapters-and-accelerators/fileact-interact/fileact-adapter-security-architecture.md) </span><span class="sxs-lookup"><span data-stu-id="43272-125">[FileAct Adapter Security Architecture](../../adapters-and-accelerators/fileact-interact/fileact-adapter-security-architecture.md) </span></span>  
 <span data-ttu-id="43272-126">[FileAct アダプター ファイルおよび転送の識別](../../adapters-and-accelerators/fileact-interact/fileact-adapter-file-and-transfer-identification.md) </span><span class="sxs-lookup"><span data-stu-id="43272-126">[FileAct Adapter File and Transfer Identification](../../adapters-and-accelerators/fileact-interact/fileact-adapter-file-and-transfer-identification.md) </span></span>  
 <span data-ttu-id="43272-127">[FileAct アダプターをサポートする情報の転送](../../adapters-and-accelerators/fileact-interact/fileact-adapter-supporting-information-transfer.md) </span><span class="sxs-lookup"><span data-stu-id="43272-127">[FileAct Adapter Supporting Information Transfer](../../adapters-and-accelerators/fileact-interact/fileact-adapter-supporting-information-transfer.md) </span></span>  
 <span data-ttu-id="43272-128">[FileAct アダプター配信通知](../../adapters-and-accelerators/fileact-interact/fileact-adapter-delivery-notification.md) </span><span class="sxs-lookup"><span data-stu-id="43272-128">[FileAct Adapter Delivery Notification](../../adapters-and-accelerators/fileact-interact/fileact-adapter-delivery-notification.md) </span></span>  
 [<span data-ttu-id="43272-129">FileAct アダプター状態の監視</span><span class="sxs-lookup"><span data-stu-id="43272-129">FileAct Adapter Status Monitoring</span></span>](../../adapters-and-accelerators/fileact-interact/fileact-adapter-status-monitoring.md)