---
title: 開始側パブリック プロセス |Microsoft ドキュメント
ms.custom: ''
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: ''
ms.suite: ''
ms.tgt_pltfrm: ''
ms.topic: article
helpviewer_keywords:
- public processes, initiator
- CIDX, 0A1 messages
- messages, 0A1 messages
- messages, message flow
- messages, public processes
- 0A1 messages
- public processes, message flow
ms.assetid: 371d0792-d346-405b-a8f4-2dfa64dd1566
caps.latest.revision: 4
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: df1565915d36f3036543ff69c5da680d5949dc74
ms.sourcegitcommit: cb908c540d8f1a692d01dc8f313e16cb4b4e696d
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 09/20/2017
ms.locfileid: "22210706"
---
# <a name="initiator-public-process"></a><span data-ttu-id="10756-102">開始側パブリック プロセス</span><span class="sxs-lookup"><span data-stu-id="10756-102">Initiator Public Process</span></span>
<span data-ttu-id="10756-103">このプロセスは、開始 RNIF ビジネス メッセージを作成して送信することにより、開始側システムで RNIF (RosettaNet Implementation Framework) メッセージングを開始します。</span><span class="sxs-lookup"><span data-stu-id="10756-103">This process initiates RosettaNet Implementation Framework (RNIF) messaging on the initiator system by creating and sending the initial RNIF business message.</span></span>  
  
## <a name="message-flow-in-the-initiator-public-process"></a><span data-ttu-id="10756-104">開始側パブリック プロセスのメッセージ フロー</span><span class="sxs-lookup"><span data-stu-id="10756-104">Message Flow in the Initiator Public Process</span></span>  
 <span data-ttu-id="10756-105">開始側パブリック プロセスのメッセージ フローは次のとおりです。</span><span class="sxs-lookup"><span data-stu-id="10756-105">The message flow through the initiator public process is as follows:</span></span>  
  
1.  <span data-ttu-id="10756-106">開始側パブリック プロセスは、サービス コンテンツ ポートを介して、Service Content と添付ファイルをプライベート プロセスから受信します。</span><span class="sxs-lookup"><span data-stu-id="10756-106">The initiator public process receives the service content and attachments from the private process through the service-content port.</span></span>  
  
2.  <span data-ttu-id="10756-107">パブリック プロセスはプライベート プロセスに応答を送信しますが、これ以上の処理は行いません。</span><span class="sxs-lookup"><span data-stu-id="10756-107">The public process sends the response to the private process, and does no further processing.</span></span>  
  
3.  <span data-ttu-id="10756-108">場合は、パブリック プロセスは通知を受信する[!INCLUDE[btsCoName](../../includes/btsconame-md.md)][!INCLUDE[BTARN_CurrentVersion_FirstRef](../../includes/btarn-currentversion-firstref-md.md)]正常に送信メッセージ、パブリック プロセスとその状態、開始側プライベート プロセスに戻る、終了します。</span><span class="sxs-lookup"><span data-stu-id="10756-108">If the public process receives notification that [!INCLUDE[btsCoName](../../includes/btsconame-md.md)][!INCLUDE[BTARN_CurrentVersion_FirstRef](../../includes/btarn-currentversion-firstref-md.md)] did not successfully send the message, the public process sends that status back to the initiator private process, and then ends.</span></span>  
  
4.  <span data-ttu-id="10756-109">[!INCLUDE[btaBTARN3.3abbrevnonumber](../../includes/btabtarn3-3abbrevnonumber-md.md)] がメッセージを正常に送信したことを知らせる通知を受信すると、パブリック プロセスは (応答側のアクションを待つ) 待機状態になります。</span><span class="sxs-lookup"><span data-stu-id="10756-109">If the public process receives notification that [!INCLUDE[btaBTARN3.3abbrevnonumber](../../includes/btabtarn3-3abbrevnonumber-md.md)] successfully sent the message, the process enters a wait state (waiting for action by the responder).</span></span>  
  
5.  <span data-ttu-id="10756-110">次のアクションが発生すると、待機状態が終了します。</span><span class="sxs-lookup"><span data-stu-id="10756-110">The following actions can end the wait state:</span></span>  
  
    1.  <span data-ttu-id="10756-111">パブリック プロセスが、応答側から受信確認シグナルを受信した場合。</span><span class="sxs-lookup"><span data-stu-id="10756-111">The public process receives an acknowledgement signal from the responder.</span></span>  
  
         <span data-ttu-id="10756-112">シグナルの否認不可が必須 (プロセス構成で設定されている) の場合、プロセスはダイジェストを読み取り、シグナルのダイジェストと元のアクション メッセージのダイジェストを関連付けてから、シグナルを保存します。</span><span class="sxs-lookup"><span data-stu-id="10756-112">If non-repudiation for the signal is required (as set in the process configuration settings), the process reads the digest, correlates the digest in the signal with the digest in the original action message, and then persists the signal.</span></span>  
  
         <span data-ttu-id="10756-113">パブリック プロセスが、シグナルのヘッダーと Service Content をプライベート プロセスに送信した場合。</span><span class="sxs-lookup"><span data-stu-id="10756-113">The public process sends the headers and service content of the signal to the private process.</span></span>  
  
    2.  <span data-ttu-id="10756-114">パブリック プロセスが、応答側からダブル アクションの応答メッセージを受信した場合。</span><span class="sxs-lookup"><span data-stu-id="10756-114">The public process receives a double-action response message from the responder.</span></span>  
  
         <span data-ttu-id="10756-115">プロセスが、Service Content とヘッダーを応答メッセージから抽出し、プライベート プロセスに送信した場合。</span><span class="sxs-lookup"><span data-stu-id="10756-115">The process extracts the service content and headers from the response message, and sends them to the private process.</span></span>  
  
         <span data-ttu-id="10756-116">動作が同期の場合、プロセスは Service Content メッセージ部を Preamble、Service Header、Delivery Header (RNIF 2.01 の場合のみ) でラップして、RNIF シグナル メッセージを作成します。</span><span class="sxs-lookup"><span data-stu-id="10756-116">If the activity is synchronous, the process constructs an RNIF signal message by wrapping the service-content message part with the preamble, service header, and delivery header (for RNIF 2.01).</span></span> <span data-ttu-id="10756-117">プロセスは、開始側と応答側の間での取引先アグリーメントに保存されている情報 (双方の構成情報と PIP 変数) を使って Preamble とヘッダーを作成します。</span><span class="sxs-lookup"><span data-stu-id="10756-117">The process creates the preamble and headers using configuration information about the source and destination parties, and the PIP variables stored in the trading partner agreement between the parties.</span></span> <span data-ttu-id="10756-118">次に、シグナル メッセージを応答側に送信します。</span><span class="sxs-lookup"><span data-stu-id="10756-118">The process then sends the signal message to the responder.</span></span>  
  
         <span data-ttu-id="10756-119">動作が非同期の場合、プロセスが終了します。</span><span class="sxs-lookup"><span data-stu-id="10756-119">If the activity is asynchronous, the process ends.</span></span>  
  
    3.  <span data-ttu-id="10756-120">パブリック プロセスが、応答側からエラー通知メッセージ (NoF) を受信した場合。</span><span class="sxs-lookup"><span data-stu-id="10756-120">The public process receives a Notification of Failure (NoF) message from the responder.</span></span> <span data-ttu-id="10756-121">パブリック プロセスは、対応する状態メッセージを開始側プライベート プロセスに送信します。</span><span class="sxs-lookup"><span data-stu-id="10756-121">The public process sends a corresponding status message to the initiator private process.</span></span> <span data-ttu-id="10756-122">プライベート プロセスがエラーを処理し、両方のプロセスを終了します。</span><span class="sxs-lookup"><span data-stu-id="10756-122">The private process then handles the error and ends both processes.</span></span>  
  
    4.  <span data-ttu-id="10756-123">パブリック プロセスが、(プロセス構成で設定されている) 受信確認までの時間内に受信確認シグナルを受け取らなかった場合。</span><span class="sxs-lookup"><span data-stu-id="10756-123">The public process does not receive an acknowledgement signal from the responder within the Time to Acknowledge period (as set in the process configuration settings).</span></span> <span data-ttu-id="10756-124">この場合、次のいずれかが発生します。</span><span class="sxs-lookup"><span data-stu-id="10756-124">If so, one of the following occurs:</span></span>  
  
         <span data-ttu-id="10756-125">(プロセス構成で設定されている) 再試行回数が 0 になっておらず、動作が非同期の場合、パブリック プロセスはメッセージを再送信します。</span><span class="sxs-lookup"><span data-stu-id="10756-125">If the number of retries (as set in the process configuration settings) has not reached zero, and the activity is asynchronous, the public process sends the message again.</span></span>  
  
         <span data-ttu-id="10756-126">(プロセス構成で設定されている) 再試行回数が 0 になっておらず、動作が同期の場合、パブリック プロセスは 0A1 メッセージを開始します。</span><span class="sxs-lookup"><span data-stu-id="10756-126">If the number of retries (as set in the process configuration settings) has not reached zero, and the activity is synchronous, the public process initiates a 0A1 message.</span></span>  
  
        > [!NOTE]
        >  <span data-ttu-id="10756-127">CIDX は、0A1 メッセージをサポートしていません。</span><span class="sxs-lookup"><span data-stu-id="10756-127">CIDX does not support 0A1 messages.</span></span>  
  
         <span data-ttu-id="10756-128">正常に送信できずに再試行回数が 0 になった場合、パブリック プロセスはエラー メッセージを送信します。設定が CIDX でない場合は、パブリック プロセスは 0A1 メッセージを送信します。</span><span class="sxs-lookup"><span data-stu-id="10756-128">If the number of retries reaches zero without a successful send, the public process posts an error message, and if this is not CIDX, the public process sends a 0A1 message.</span></span>  
  
         <span data-ttu-id="10756-129">動作が同期で、設定が CIDX でないとき、パブリック プロセスは 0A1 メッセージを開始します。</span><span class="sxs-lookup"><span data-stu-id="10756-129">If the activity is synchronous, and this is not CIDX, the public process initiates a 0A1 message.</span></span>  
  
    5.  <span data-ttu-id="10756-130">アクションが Time to Perform で定めた実行までの時間内に発生しない場合で、設定が CIDX でないとき、パブリック プロセスは 0A1 メッセージを送信します。</span><span class="sxs-lookup"><span data-stu-id="10756-130">If no action occurs within the Time to Perform period, and this is not CIDX, the public process sends a 0A1 message.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="10756-131">参照</span><span class="sxs-lookup"><span data-stu-id="10756-131">See Also</span></span>  
 <span data-ttu-id="10756-132">[パブリック プロセス](../../adapters-and-accelerators/accelerator-rosettanet/public-processes.md) </span><span class="sxs-lookup"><span data-stu-id="10756-132">[Public Processes](../../adapters-and-accelerators/accelerator-rosettanet/public-processes.md) </span></span>  
 [<span data-ttu-id="10756-133">応答側パブリック プロセス</span><span class="sxs-lookup"><span data-stu-id="10756-133">Responder Public Process</span></span>](../../adapters-and-accelerators/accelerator-rosettanet/responder-public-process.md)