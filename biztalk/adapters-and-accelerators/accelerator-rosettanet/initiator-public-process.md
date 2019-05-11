---
title: 開始側パブリック プロセス |Microsoft Docs
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
ms.openlocfilehash: 50506911108d21247f5da9cadc76cd505417a8d9
ms.sourcegitcommit: 381e83d43796a345488d54b3f7413e11d56ad7be
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 05/07/2019
ms.locfileid: "65283499"
---
# <a name="initiator-public-process"></a><span data-ttu-id="8649f-102">開始側パブリック プロセス</span><span class="sxs-lookup"><span data-stu-id="8649f-102">Initiator Public Process</span></span>
<span data-ttu-id="8649f-103">このプロセスは、RosettaNet Implementation Framework (RNIF) が作成、RNIF ビジネス メッセージを送信することで、開始側システムでメッセージングを開始します。</span><span class="sxs-lookup"><span data-stu-id="8649f-103">This process initiates RosettaNet Implementation Framework (RNIF) messaging on the initiator system by creating and sending the initial RNIF business message.</span></span>  
  
## <a name="message-flow-in-the-initiator-public-process"></a><span data-ttu-id="8649f-104">開始側パブリック プロセスにおけるメッセージ フロー</span><span class="sxs-lookup"><span data-stu-id="8649f-104">Message Flow in the Initiator Public Process</span></span>  
 <span data-ttu-id="8649f-105">開始側パブリック プロセスを経由するメッセージ フローは次のとおりです。</span><span class="sxs-lookup"><span data-stu-id="8649f-105">The message flow through the initiator public process is as follows:</span></span>  
  
1. <span data-ttu-id="8649f-106">開始側パブリック プロセスは、サービス コンテンツ ポートを介してプライベート プロセスからの service content と添付ファイルを受け取ります。</span><span class="sxs-lookup"><span data-stu-id="8649f-106">The initiator public process receives the service content and attachments from the private process through the service-content port.</span></span>  
  
2. <span data-ttu-id="8649f-107">パブリック プロセスは、プライベートのプロセスへの応答を送信し、さらなる処理は行われません。</span><span class="sxs-lookup"><span data-stu-id="8649f-107">The public process sends the response to the private process, and does no further processing.</span></span>  
  
3. <span data-ttu-id="8649f-108">マイクロソフトに通知を受信するパブリック プロセス場合、[!INCLUDE[BTARN_CurrentVersion_FirstRef](../../includes/btarn-currentversion-firstref-md.md)]メッセージ正常に送信して、パブリック プロセスとその状態、開始側プライベート プロセスに戻るを終了します。</span><span class="sxs-lookup"><span data-stu-id="8649f-108">If the public process receives notification that Microsoft [!INCLUDE[BTARN_CurrentVersion_FirstRef](../../includes/btarn-currentversion-firstref-md.md)] did not successfully send the message, the public process sends that status back to the initiator private process, and then ends.</span></span>  
  
4. <span data-ttu-id="8649f-109">場合は、パブリック プロセスは、通知を受信する[!INCLUDE[btaBTARN3.3abbrevnonumber](../../includes/btabtarn3-3abbrevnonumber-md.md)]プロセス メッセージを正常に送信するには、(応答側のアクションを待つ) 待機状態になります。</span><span class="sxs-lookup"><span data-stu-id="8649f-109">If the public process receives notification that [!INCLUDE[btaBTARN3.3abbrevnonumber](../../includes/btabtarn3-3abbrevnonumber-md.md)] successfully sent the message, the process enters a wait state (waiting for action by the responder).</span></span>  
  
5. <span data-ttu-id="8649f-110">次の操作には、待機状態を終了できます。</span><span class="sxs-lookup"><span data-stu-id="8649f-110">The following actions can end the wait state:</span></span>  
  
   1.  <span data-ttu-id="8649f-111">パブリック プロセスは、応答側から受信確認シグナルを受信します。</span><span class="sxs-lookup"><span data-stu-id="8649f-111">The public process receives an acknowledgement signal from the responder.</span></span>  
  
        <span data-ttu-id="8649f-112">場合は、シグナルの否認 (で設定されているプロセス構成設定)、必要なプロセス ダイジェスト、シグナルのダイジェストを関連付けて元のアクション メッセージのダイジェストを読み取って、シグナルを保存し。</span><span class="sxs-lookup"><span data-stu-id="8649f-112">If non-repudiation for the signal is required (as set in the process configuration settings), the process reads the digest, correlates the digest in the signal with the digest in the original action message, and then persists the signal.</span></span>  
  
        <span data-ttu-id="8649f-113">パブリック プロセスは、ヘッダーと、シグナルの service content をプライベート プロセスに送信します。</span><span class="sxs-lookup"><span data-stu-id="8649f-113">The public process sends the headers and service content of the signal to the private process.</span></span>  
  
   2.  <span data-ttu-id="8649f-114">パブリック プロセスは、応答側からダブル アクション応答メッセージを受信します。</span><span class="sxs-lookup"><span data-stu-id="8649f-114">The public process receives a double-action response message from the responder.</span></span>  
  
        <span data-ttu-id="8649f-115">プロセスでは、service content とヘッダーを応答メッセージから抽出され、プライベート プロセスに送信されます。</span><span class="sxs-lookup"><span data-stu-id="8649f-115">The process extracts the service content and headers from the response message, and sends them to the private process.</span></span>  
  
        <span data-ttu-id="8649f-116">アクティビティが同期の場合、プロセス (RNIF 2.01 の場合) の preamble、service header、および配信のヘッダーを使用して、service content メッセージ部をラップすることによって、RNIF シグナル メッセージを構築します。</span><span class="sxs-lookup"><span data-stu-id="8649f-116">If the activity is synchronous, the process constructs an RNIF signal message by wrapping the service-content message part with the preamble, service header, and delivery header (for RNIF 2.01).</span></span> <span data-ttu-id="8649f-117">Preamble とヘッダーの送信元と送信先のパーティとパーティ間の取引先のパートナー アグリーメントに格納されている PIP 変数に関する構成情報を使用して、プロセスを作成します。</span><span class="sxs-lookup"><span data-stu-id="8649f-117">The process creates the preamble and headers using configuration information about the source and destination parties, and the PIP variables stored in the trading partner agreement between the parties.</span></span> <span data-ttu-id="8649f-118">次に、プロセスは応答側にシグナル メッセージを送信します。</span><span class="sxs-lookup"><span data-stu-id="8649f-118">The process then sends the signal message to the responder.</span></span>  
  
        <span data-ttu-id="8649f-119">アクティビティが非同期の場合、プロセスを終了します。</span><span class="sxs-lookup"><span data-stu-id="8649f-119">If the activity is asynchronous, the process ends.</span></span>  
  
   3.  <span data-ttu-id="8649f-120">パブリック プロセスは、応答側からエラー通知 (NoF) メッセージを受け取ります。</span><span class="sxs-lookup"><span data-stu-id="8649f-120">The public process receives a Notification of Failure (NoF) message from the responder.</span></span> <span data-ttu-id="8649f-121">パブリック プロセスは、開始側プライベート プロセスに対応するステータス メッセージを送信します。</span><span class="sxs-lookup"><span data-stu-id="8649f-121">The public process sends a corresponding status message to the initiator private process.</span></span> <span data-ttu-id="8649f-122">プライベート プロセスは、エラーを処理し、両方のプロセスを終了します。</span><span class="sxs-lookup"><span data-stu-id="8649f-122">The private process then handles the error and ends both processes.</span></span>  
  
   4.  <span data-ttu-id="8649f-123">パブリック プロセスでは、時間内、応答側から受信確認シグナルは (プロセス構成設定で設定した) として確認期間に受信しません。</span><span class="sxs-lookup"><span data-stu-id="8649f-123">The public process does not receive an acknowledgement signal from the responder within the Time to Acknowledge period (as set in the process configuration settings).</span></span> <span data-ttu-id="8649f-124">そうである場合、次のいずれかが発生します。</span><span class="sxs-lookup"><span data-stu-id="8649f-124">If so, one of the following occurs:</span></span>  
  
        <span data-ttu-id="8649f-125">(プロセス構成設定で設定) と再試行の回数が 0 になっておらず、アクティビティが非同期場合は、パブリック プロセスは、メッセージをもう一度送信します。</span><span class="sxs-lookup"><span data-stu-id="8649f-125">If the number of retries (as set in the process configuration settings) has not reached zero, and the activity is asynchronous, the public process sends the message again.</span></span>  
  
        <span data-ttu-id="8649f-126">(プロセス構成設定で設定) と再試行の回数が 0 になっていないと、動作が同期、パブリック プロセスは 0A1 メッセージを開始します。</span><span class="sxs-lookup"><span data-stu-id="8649f-126">If the number of retries (as set in the process configuration settings) has not reached zero, and the activity is synchronous, the public process initiates a 0A1 message.</span></span>  
  
       > [!NOTE]
       >  <span data-ttu-id="8649f-127">CIDX は、0A1 メッセージをサポートしていません。</span><span class="sxs-lookup"><span data-stu-id="8649f-127">CIDX does not support 0A1 messages.</span></span>  
  
        <span data-ttu-id="8649f-128">パブリック プロセスが、エラー メッセージを投稿する再試行の回数が正常に送信ゼロに達すると、これが CIDX でない場合、パブリック プロセスは 0A1 メッセージを送信します。</span><span class="sxs-lookup"><span data-stu-id="8649f-128">If the number of retries reaches zero without a successful send, the public process posts an error message, and if this is not CIDX, the public process sends a 0A1 message.</span></span>  
  
        <span data-ttu-id="8649f-129">このアクティビティは、同期が CIDX でない場合は、パブリック プロセスは 0A1 メッセージを開始します。</span><span class="sxs-lookup"><span data-stu-id="8649f-129">If the activity is synchronous, and this is not CIDX, the public process initiates a 0A1 message.</span></span>  
  
   5.  <span data-ttu-id="8649f-130">アクション内に行われない、時間、実行期間に、これが CIDX でない場合は、パブリック プロセスは 0A1 メッセージを送信します。</span><span class="sxs-lookup"><span data-stu-id="8649f-130">If no action occurs within the Time to Perform period, and this is not CIDX, the public process sends a 0A1 message.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="8649f-131">参照</span><span class="sxs-lookup"><span data-stu-id="8649f-131">See Also</span></span>  
 <span data-ttu-id="8649f-132">[パブリック プロセス](../../adapters-and-accelerators/accelerator-rosettanet/public-processes.md) </span><span class="sxs-lookup"><span data-stu-id="8649f-132">[Public Processes](../../adapters-and-accelerators/accelerator-rosettanet/public-processes.md) </span></span>  
 [<span data-ttu-id="8649f-133">レスポンダー パブリック プロセス</span><span class="sxs-lookup"><span data-stu-id="8649f-133">Responder Public Process</span></span>](../../adapters-and-accelerators/accelerator-rosettanet/responder-public-process.md)