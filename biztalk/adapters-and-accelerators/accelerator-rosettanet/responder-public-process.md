---
title: 応答側パブリック プロセス |Microsoft ドキュメント
ms.custom: ''
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: ''
ms.suite: ''
ms.tgt_pltfrm: ''
ms.topic: article
helpviewer_keywords:
- messages, message flow
- messages, public processes
- public processes, message flow
- public processes, responder
ms.assetid: 78d83954-2998-44ac-a527-5e5858c61009
caps.latest.revision: 4
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: c89c246bca80fdb648df909cd4f01fca4e2691dc
ms.sourcegitcommit: cb908c540d8f1a692d01dc8f313e16cb4b4e696d
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 09/20/2017
ms.locfileid: "22210866"
---
# <a name="responder-public-process"></a><span data-ttu-id="1ee8d-102">応答側パブリック プロセス</span><span class="sxs-lookup"><span data-stu-id="1ee8d-102">Responder Public Process</span></span>
<span data-ttu-id="1ee8d-103">この応答側のパブリック プロセスは、開始側から RNIF (RosettaNet Implementation Framework) メッセージを受信し、必要に応じて応答します。</span><span class="sxs-lookup"><span data-stu-id="1ee8d-103">This public process on the responder receives the RosettaNet Implementation Framework (RNIF) message from the initiator, and responds accordingly.</span></span>  
  
## <a name="message-flow-in-the-responder-public-process"></a><span data-ttu-id="1ee8d-104">応答側パブリック プロセスにおけるメッセージ フロー</span><span class="sxs-lookup"><span data-stu-id="1ee8d-104">Message Flow in the Responder Public Process</span></span>  
 <span data-ttu-id="1ee8d-105">応答側パブリック プロセスにおけるメッセージ フローは次のとおりです。</span><span class="sxs-lookup"><span data-stu-id="1ee8d-105">The message flow through the responder public process is as follows:</span></span>  
  
1.  <span data-ttu-id="1ee8d-106">応答側パブリック プロセスが応答側メッセージ ボックス データベースから RNIF メッセージを受信します。</span><span class="sxs-lookup"><span data-stu-id="1ee8d-106">The responder public process receives the RNIF message from the responder MessageBox database.</span></span>  
  
2.  <span data-ttu-id="1ee8d-107">パブリック プロセスが Service Content およびヘッダーをアクション メッセージから抽出してプライベート プロセスに送信します。</span><span class="sxs-lookup"><span data-stu-id="1ee8d-107">The public process extracts the service content and headers from the action message, and sends them to the private process.</span></span>  
  
    > [!NOTE]
    >  <span data-ttu-id="1ee8d-108">応答側パブリック プロセスが着信メッセージに対して標準検証 (適用できる場合は、検証アダプターに含まれる追加の検証) を実行します。</span><span class="sxs-lookup"><span data-stu-id="1ee8d-108">The responder public process performs standard validation on the incoming message (and any additional validation included in a validation adapter, if applicable).</span></span> <span data-ttu-id="1ee8d-109">検証が正常に終了すると、パブリック プロセスはアプリケーション アダプターを開始して個々の実装に基づいて通知を実行します。</span><span class="sxs-lookup"><span data-stu-id="1ee8d-109">If validation is successful, then the public process will initiate the application adapter to perform notification in accordance with the specific implementation.</span></span> <span data-ttu-id="1ee8d-110">応答側パブリック プロセスはメッセージ ボックス データベースにメッセージを保存し、`BeginNotify` クラスの `ApplicationAdapter` メソッドを使用して、メッセージ ボックスにメッセージを保存したことを応答側プライベート プロセスに通知します。</span><span class="sxs-lookup"><span data-stu-id="1ee8d-110">The responder public process will save the message in the MessageBox database, and will notify the responder private process that it has saved the message in the MessageBox (using the `BeginNotify` method in the `ApplicationAdapter` class).</span></span> <span data-ttu-id="1ee8d-111">検証アダプターとアプリケーション アダプターに関する詳細については、次を参照してください。 [ValidationAdapter & #91。RN3 &#93;](../../adapters-and-accelerators/accelerator-rosettanet/validationadapter.md)と[ApplicationAdapter & #91。RN3 &#93;](../../adapters-and-accelerators/accelerator-rosettanet/applicationadapter.md).</span><span class="sxs-lookup"><span data-stu-id="1ee8d-111">For more information about the validation adapter and application adapter, see [ValidationAdapter &#91;RN3&#93;](../../adapters-and-accelerators/accelerator-rosettanet/validationadapter.md) and [ApplicationAdapter &#91;RN3&#93;](../../adapters-and-accelerators/accelerator-rosettanet/applicationadapter.md).</span></span>  
  
3.  <span data-ttu-id="1ee8d-112">非同期のシングル アクションの場合、パブリック プロセスは Service Content のメッセージ部を Preamble、Service Header、および Delivery Header (RNIF 2.01 の場合のみ) でラップして、RNIF シグナル メッセージ (受信確認) を作成します。</span><span class="sxs-lookup"><span data-stu-id="1ee8d-112">If the activity is asynchronous and single-action, the public process constructs an RNIF signal message (Acknowledgment Acceptance) by wrapping the service-content message part with the preamble, the service header, and (for RNIF 2.01 only) the delivery header.</span></span> <span data-ttu-id="1ee8d-113">パブリック プロセスは、パーティ間の取引先アグリーメントに保存されている情報 (プロセス構成設定、送信元と送信先パーティの構成情報、および PIP (Partner Interface Process) 変数) を使用して、Preamble、Service Header、および Delivery Header を作成します。</span><span class="sxs-lookup"><span data-stu-id="1ee8d-113">The public process constructs the preamble, the service header, and the delivery header using information stored in the trading partner agreement between the parties: the process configuration settings, configuration information about the source and destination parties, and the Partner Interface Process (PIP) variables.</span></span> <span data-ttu-id="1ee8d-114">その後、開始側にシグナル メッセージを送信します。</span><span class="sxs-lookup"><span data-stu-id="1ee8d-114">The process then sends the signal message to the initiator.</span></span>  
  
    > [!NOTE]
    >  <span data-ttu-id="1ee8d-115">シングル アクション メッセージの場合、メッセージ フローは完了します。</span><span class="sxs-lookup"><span data-stu-id="1ee8d-115">If the message is a single-action message, the message flow is complete.</span></span>  
  
4.  <span data-ttu-id="1ee8d-116">パブリック プロセスは、待機状態 (応答側プライベート プロセスのアクションを待っている状態) になります。</span><span class="sxs-lookup"><span data-stu-id="1ee8d-116">The public process enters a wait state (waiting for action by the responder private process).</span></span>  
  
5.  <span data-ttu-id="1ee8d-117">待機状態 (応答側プライベート プロセスのアクションを待っている状態) は、次のアクションによって終了します。</span><span class="sxs-lookup"><span data-stu-id="1ee8d-117">The following actions can end the wait state (waiting for action by the responder private process):</span></span>  
  
    1.  <span data-ttu-id="1ee8d-118">応答側プライベート プロセスが元のダブル アクション メッセージに応答して、Service Content メッセージおよびヘッダーを返した場合。</span><span class="sxs-lookup"><span data-stu-id="1ee8d-118">The responder private process returns a response service-content message and headers, in response to the original action message (that was a double-action message).</span></span>  
  
         <span data-ttu-id="1ee8d-119">パブリック プロセスがプライベート プロセスから応答サービス コンテンツを受信する場合、パブリック プロセスは Service Content を含む RNIF メッセージを作成します。</span><span class="sxs-lookup"><span data-stu-id="1ee8d-119">If the public process receives response service content from the private process, the public process constructs an RNIF message that contains the service content.</span></span> <span data-ttu-id="1ee8d-120">パブリック プロセスは、送信元と送信先のパーティに関する構成情報を含むヘッダー、およびパーティ間のアグリーメントに保存されている PIP 変数で Service Content のメッセージ部をラップして、メッセージを作成します。</span><span class="sxs-lookup"><span data-stu-id="1ee8d-120">It does so by wrapping the service-content message part with headers that contain the configuration information about the source and destination parties, and the PIP variables stored in the agreement between the parties.</span></span>  
  
         <span data-ttu-id="1ee8d-121">パブリック プロセスが Action/Signal Role リンク ポートを使用して、開始側に RNIF メッセージを送信します。</span><span class="sxs-lookup"><span data-stu-id="1ee8d-121">The public process sends the RNIF message to the initiator using the Action/Signal Role link port.</span></span>  
  
         <span data-ttu-id="1ee8d-122">場合は、パブリック プロセスは通知を受信する[!INCLUDE[btsCoName](../../includes/btsconame-md.md)][!INCLUDE[BTARN_CurrentVersion_FirstRef](../../includes/btarn-currentversion-firstref-md.md)]正常に送信メッセージ、パブリック プロセスとその状態、プライベート プロセスに返信して終了します。</span><span class="sxs-lookup"><span data-stu-id="1ee8d-122">If the public process receives notification that [!INCLUDE[btsCoName](../../includes/btsconame-md.md)][!INCLUDE[BTARN_CurrentVersion_FirstRef](../../includes/btarn-currentversion-firstref-md.md)] did not successfully send the message, the public process sends that status back to the private process, and then ends.</span></span>  
  
         <span data-ttu-id="1ee8d-123">パブリック プロセスは、[!INCLUDE[btaBTARN3.3abbrevnonumber](../../includes/btabtarn3-3abbrevnonumber-md.md)] がメッセージを正常に送信したことを知らせる通知を受信すると、待機状態 (開始側のアクションを待っている状態) になります。</span><span class="sxs-lookup"><span data-stu-id="1ee8d-123">If the public process receives notification that [!INCLUDE[btaBTARN3.3abbrevnonumber](../../includes/btabtarn3-3abbrevnonumber-md.md)] successfully sent the message, the process enters a wait state (waiting for action by the initiator).</span></span> <span data-ttu-id="1ee8d-124">この待機状態は、開始側が応答側のアクションを待つ場合の待機状態に似ています。</span><span class="sxs-lookup"><span data-stu-id="1ee8d-124">This wait state is similar to the wait state that the initiator enters when it is waiting for action by the responder.</span></span>  
  
    2.  <span data-ttu-id="1ee8d-125">パブリック プロセスが、開始側からエラー通知メッセージ (NoF) を受信した場合。</span><span class="sxs-lookup"><span data-stu-id="1ee8d-125">The public process receives a Notification of Failure message (NoF) from the initiator.</span></span>  
  
    > [!NOTE]
    >  <span data-ttu-id="1ee8d-126">応答側プライベート プロセスが、着信メッセージを正常に処理した後に応答側パブリック プロセスに通知します。</span><span class="sxs-lookup"><span data-stu-id="1ee8d-126">The responder private process will notify the responder public process after it has successfully processed the incoming message.</span></span> <span data-ttu-id="1ee8d-127">応答側パブリック プロセスが `EndNotify` クラスの `ApplicationAdapter` メソッドからこの通知を受信した場合のみ、応答側パブリック プロセスが正常に完了したことになります。</span><span class="sxs-lookup"><span data-stu-id="1ee8d-127">Only after the responder public process has received this notification (from the `EndNotify` method in the `ApplicationAdapter` class) will the responder public process be successfully completed.</span></span>  
  
6.  <span data-ttu-id="1ee8d-128">応答側パブリック プロセスは、待機状態 (応答側パブリック プロセスが送信した応答メッセージに対する開始側からのシグナルの受信を待っている状態) になります。</span><span class="sxs-lookup"><span data-stu-id="1ee8d-128">The responder public process enters a wait state (waiting to receive a signal from the initiator in response to the response message that the responder public process sent).</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="1ee8d-129">参照</span><span class="sxs-lookup"><span data-stu-id="1ee8d-129">See Also</span></span>  
 <span data-ttu-id="1ee8d-130">[パブリック プロセス](../../adapters-and-accelerators/accelerator-rosettanet/public-processes.md) </span><span class="sxs-lookup"><span data-stu-id="1ee8d-130">[Public Processes](../../adapters-and-accelerators/accelerator-rosettanet/public-processes.md) </span></span>  
 <span data-ttu-id="1ee8d-131">[開始側パブリック プロセス](../../adapters-and-accelerators/accelerator-rosettanet/initiator-public-process.md) </span><span class="sxs-lookup"><span data-stu-id="1ee8d-131">[Initiator Public Process](../../adapters-and-accelerators/accelerator-rosettanet/initiator-public-process.md) </span></span>  
 <span data-ttu-id="1ee8d-132">[ApplicationAdapter](../../adapters-and-accelerators/accelerator-rosettanet/applicationadapter.md) </span><span class="sxs-lookup"><span data-stu-id="1ee8d-132">[ApplicationAdapter](../../adapters-and-accelerators/accelerator-rosettanet/applicationadapter.md) </span></span>  
 [<span data-ttu-id="1ee8d-133">ValidationAdapter</span><span class="sxs-lookup"><span data-stu-id="1ee8d-133">ValidationAdapter</span></span>](../../adapters-and-accelerators/accelerator-rosettanet/validationadapter.md)