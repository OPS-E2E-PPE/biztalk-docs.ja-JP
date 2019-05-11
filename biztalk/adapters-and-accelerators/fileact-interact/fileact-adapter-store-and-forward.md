---
title: FileAct アダプターのストア アンド フォワード |Microsoft Docs
ms.custom: ''
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: ''
ms.suite: ''
ms.tgt_pltfrm: ''
ms.topic: article
ms.assetid: 50110bf0-75c2-426c-9833-65c3117224b2
caps.latest.revision: 6
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: 6971d1b65f32018b15bf8ae022ca6d64d23701da
ms.sourcegitcommit: 381e83d43796a345488d54b3f7413e11d56ad7be
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 05/07/2019
ms.locfileid: "65367172"
---
# <a name="fileact-adapter-store-and-forward"></a><span data-ttu-id="bbe59-102">FileAct アダプターのストア アンド フォワード</span><span class="sxs-lookup"><span data-stu-id="bbe59-102">FileAct Adapter Store and Forward</span></span>
<span data-ttu-id="bbe59-103">ストアに順方向 (SnF) モードでは、ファイルに配信し、送信時にキューに登録し、変換先にキューから取得されます。</span><span class="sxs-lookup"><span data-stu-id="bbe59-103">In Store and Forward (SnF) mode, files are delivered to queue at send time, and are retrieved from the queue by the destination.</span></span> <span data-ttu-id="bbe59-104">中間の応答は、ファイルが先に安全に配信されるまでに、SWIFTNet によって送信者に返されます。</span><span class="sxs-lookup"><span data-stu-id="bbe59-104">Intermediate responses are returned by SWIFTNet to the sender until the file is safely delivered to the destination.</span></span>  
  
## <a name="sending-using-snf"></a><span data-ttu-id="bbe59-105">SnF を使用して送信します。</span><span class="sxs-lookup"><span data-stu-id="bbe59-105">Sending Using SnF</span></span>  
 <span data-ttu-id="bbe59-106">一方向の送信ポートを作成する場合、アダプターは SnF モードで動作し、キューにメッセージを送信します。</span><span class="sxs-lookup"><span data-stu-id="bbe59-106">If you create a one-way send port, the adapter works in SnF mode and sends messages to the queue.</span></span>  
  
## <a name="receiving-using-snf"></a><span data-ttu-id="bbe59-107">SnF を使用して受信</span><span class="sxs-lookup"><span data-stu-id="bbe59-107">Receiving Using SnF</span></span>  
 <span data-ttu-id="bbe59-108">SnF FileAct はプッシュ モードで動作します。</span><span class="sxs-lookup"><span data-stu-id="bbe59-108">SnF FileAct operates in Push mode.</span></span> <span data-ttu-id="bbe59-109">これは、実行時オプションです。</span><span class="sxs-lookup"><span data-stu-id="bbe59-109">This is a run-time option.</span></span>  
  
 <span data-ttu-id="bbe59-110">キューからメッセージを取得できないようにするには、前に SWIFTNet SnF はキューを取得する要求を受信する必要があります。</span><span class="sxs-lookup"><span data-stu-id="bbe59-110">Before being able to retrieve messages from a queue, SWIFTNet SnF should receive a request to acquire the queue.</span></span> <span data-ttu-id="bbe59-111">これは、アウト プロセス COM + コンポーネントを呼び出して、受信アダプターによって実現されます。</span><span class="sxs-lookup"><span data-stu-id="bbe59-111">This is accomplished by the receive adapter invoking the out-of-proc COM+ component.</span></span> <span data-ttu-id="bbe59-112">成功した acquire では、セッションが作成されます。</span><span class="sxs-lookup"><span data-stu-id="bbe59-112">After a successful acquire, a session is created.</span></span> <span data-ttu-id="bbe59-113">キューは、要求で指定されたモードで、開けません。</span><span class="sxs-lookup"><span data-stu-id="bbe59-113">The queue will then be opened in the mode specified in the Request.</span></span> <span data-ttu-id="bbe59-114">要求を発行した物理ノードに、すべてのメッセージが返されます。</span><span class="sxs-lookup"><span data-stu-id="bbe59-114">All messages will be returned to the physical node which issued the request.</span></span>  
  
 <span data-ttu-id="bbe59-115">指定された順序 (InterAct および FileAct の送信の混在、および優先度別に並べ替えることに注意) でメッセージが配信されます。ただし、メッセージのシーケンス処理は、格納されているかの時間に依存します。</span><span class="sxs-lookup"><span data-stu-id="bbe59-115">Messages are delivered in the order specified (note that InterAct and FileAct transmissions can be interspersed, and arranged by priority.) The sequencing of messages, however, is dependent on the time that they were stored.</span></span> <span data-ttu-id="bbe59-116">FileAct の場合、開始時ではなく、file storage が完了した時間です。</span><span class="sxs-lookup"><span data-stu-id="bbe59-116">In the case of FileAct, this is the time that the file storage is completed, not when it started.</span></span>  
  
### <a name="push-a-file-from-the-queue"></a><span data-ttu-id="bbe59-117">キューからファイルをプッシュします。</span><span class="sxs-lookup"><span data-stu-id="bbe59-117">Push a File From the Queue</span></span>  
 <span data-ttu-id="bbe59-118">FileAct アダプター (サーバー) では、キュー、セッション、およびシーケンスの情報を含む SWIFTNet から、HandleFileRequest を受信します。</span><span class="sxs-lookup"><span data-stu-id="bbe59-118">The FileAct adapter (server) receives a HandleFileRequest from SWIFTNet, containing the queue, session and sequence information.</span></span> <span data-ttu-id="bbe59-119">サーバーは、HandleFileResponse で応答します。</span><span class="sxs-lookup"><span data-stu-id="bbe59-119">The server responds with a HandleFileResponse.</span></span>  
  
 <span data-ttu-id="bbe59-120">サーバーが、FetchFileRequest を発行し、ファイルがサーバーに配信します。</span><span class="sxs-lookup"><span data-stu-id="bbe59-120">The server then issues FetchFileRequest and the file is delivered to the server.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="bbe59-121">参照</span><span class="sxs-lookup"><span data-stu-id="bbe59-121">See Also</span></span>  
 <span data-ttu-id="bbe59-122">[FileAct アダプターのアーキテクチャ](../../adapters-and-accelerators/fileact-interact/fileact-adapter-architecture.md) </span><span class="sxs-lookup"><span data-stu-id="bbe59-122">[FileAct Adapter Architecture](../../adapters-and-accelerators/fileact-interact/fileact-adapter-architecture.md) </span></span>  
 <span data-ttu-id="bbe59-123">[FileAct アダプターのリアルタイム エンド ツー エンド プリミティブ](../../adapters-and-accelerators/fileact-interact/fileact-adapter-real-time-end-to-end-primitives.md) </span><span class="sxs-lookup"><span data-stu-id="bbe59-123">[FileAct Adapter Real-Time End-to-End Primitives](../../adapters-and-accelerators/fileact-interact/fileact-adapter-real-time-end-to-end-primitives.md) </span></span>  
 <span data-ttu-id="bbe59-124">[FileAct アダプターのリアルタイム ローカル プリミティブ](../../adapters-and-accelerators/fileact-interact/fileact-adapter-real-time-local-primitives.md) </span><span class="sxs-lookup"><span data-stu-id="bbe59-124">[FileAct Adapter Real-Time Local Primitives](../../adapters-and-accelerators/fileact-interact/fileact-adapter-real-time-local-primitives.md) </span></span>  
 <span data-ttu-id="bbe59-125">[FileAct アダプターのセキュリティ アーキテクチャ](../../adapters-and-accelerators/fileact-interact/fileact-adapter-security-architecture.md) </span><span class="sxs-lookup"><span data-stu-id="bbe59-125">[FileAct Adapter Security Architecture](../../adapters-and-accelerators/fileact-interact/fileact-adapter-security-architecture.md) </span></span>  
 <span data-ttu-id="bbe59-126">[FileAct アダプター ファイルおよび転送 Id](../../adapters-and-accelerators/fileact-interact/fileact-adapter-file-and-transfer-identification.md) </span><span class="sxs-lookup"><span data-stu-id="bbe59-126">[FileAct Adapter File and Transfer Identification](../../adapters-and-accelerators/fileact-interact/fileact-adapter-file-and-transfer-identification.md) </span></span>  
 <span data-ttu-id="bbe59-127">[FileAct アダプターのサポート情報の転送](../../adapters-and-accelerators/fileact-interact/fileact-adapter-supporting-information-transfer.md) </span><span class="sxs-lookup"><span data-stu-id="bbe59-127">[FileAct Adapter Supporting Information Transfer](../../adapters-and-accelerators/fileact-interact/fileact-adapter-supporting-information-transfer.md) </span></span>  
 <span data-ttu-id="bbe59-128">[FileAct アダプターの配信通知](../../adapters-and-accelerators/fileact-interact/fileact-adapter-delivery-notification.md) </span><span class="sxs-lookup"><span data-stu-id="bbe59-128">[FileAct Adapter Delivery Notification](../../adapters-and-accelerators/fileact-interact/fileact-adapter-delivery-notification.md) </span></span>  
 [<span data-ttu-id="bbe59-129">FileAct アダプターの状態監視</span><span class="sxs-lookup"><span data-stu-id="bbe59-129">FileAct Adapter Status Monitoring</span></span>](../../adapters-and-accelerators/fileact-interact/fileact-adapter-status-monitoring.md)