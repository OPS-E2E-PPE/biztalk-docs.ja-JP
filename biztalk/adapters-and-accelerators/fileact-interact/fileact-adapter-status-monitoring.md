---
title: FileAct アダプター状態の監視 |Microsoft ドキュメント
ms.custom: ''
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: ''
ms.suite: ''
ms.tgt_pltfrm: ''
ms.topic: article
ms.assetid: 15833004-4276-4975-a0e7-8fff3c82576b
caps.latest.revision: 5
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: 7c5b717a02631d47b864cc9180cba2fba673c5da
ms.sourcegitcommit: cb908c540d8f1a692d01dc8f313e16cb4b4e696d
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 09/20/2017
ms.locfileid: "22223042"
---
# <a name="fileact-adapter-status-monitoring"></a><span data-ttu-id="2699c-102">FileAct アダプター状態の監視</span><span class="sxs-lookup"><span data-stu-id="2699c-102">FileAct Adapter Status Monitoring</span></span>
<span data-ttu-id="2699c-103">ファイル転送およびそれらの状態間の遷移の状態は、次の図に示します。</span><span class="sxs-lookup"><span data-stu-id="2699c-103">The possible states of a file transfer and the transitions between those states are illustrated in the following figure.</span></span>  
  
 <span data-ttu-id="2699c-104">![FileAct アダプター ファイル転送状態](../../adapters-and-accelerators/fileact-interact/media/2e01feaa-6b68-49a2-a47d-6359be1f4034.gif "2e01feaa-6b68-49a2-a47d-6359be1f4034")</span><span class="sxs-lookup"><span data-stu-id="2699c-104">![FileAct adapter file transfer states](../../adapters-and-accelerators/fileact-interact/media/2e01feaa-6b68-49a2-a47d-6359be1f4034.gif "2e01feaa-6b68-49a2-a47d-6359be1f4034")</span></span>  
  
 <span data-ttu-id="2699c-105">ファイル転送の状態は次のとおりです。</span><span class="sxs-lookup"><span data-stu-id="2699c-105">The file transfer states are:</span></span>  
  
-   <span data-ttu-id="2699c-106">**開始**– クライアントがサーバーに、ネゴシエーション メッセージが送信するが、まだ応答を受け取っていません。</span><span class="sxs-lookup"><span data-stu-id="2699c-106">**Initiated** – The client has sent the negotiation message to the server, but has not yet received the response.</span></span> <span data-ttu-id="2699c-107">サーバーは、ネゴシエーション要求を受け取りましたが、応答を送信されていません。</span><span class="sxs-lookup"><span data-stu-id="2699c-107">The server has received the negotiation request, but has not yet sent the response.</span></span>  
  
-   <span data-ttu-id="2699c-108">**受け入れ**転送が進行中 – と、サーバーが、要求が承認され、応答メッセージで、TransferAnswer を受信しました。</span><span class="sxs-lookup"><span data-stu-id="2699c-108">**Accepted** – The server has accepted the request and has sent the TransferAnswer in the response message, and the transfer is still in progress.</span></span>  
  
-   <span data-ttu-id="2699c-109">**拒否**– サーバーは要求を拒否しました、TransferAnswer が応答メッセージ、および転送が終了します。</span><span class="sxs-lookup"><span data-stu-id="2699c-109">**Rejected** – The server has rejected the request and has the TransferAnswer in the response message, and has terminated the transfer.</span></span>  
  
-   <span data-ttu-id="2699c-110">**継続的な**– 転送中は、(前述のように定期的に更新された) 処理を続行します。</span><span class="sxs-lookup"><span data-stu-id="2699c-110">**Ongoing** – The transfer is in progress and is proceeding (renewed periodically as above).</span></span>  
  
-   <span data-ttu-id="2699c-111">**完了**– 限り転送の指定された側は、ダイジェスト値の比較を含む、ファイル転送が正常に完了します。</span><span class="sxs-lookup"><span data-stu-id="2699c-111">**Completed** – The file transfer has completed successfully as far as that side of the transfer is concerned, including the comparison of the digest value.</span></span>  
  
-   <span data-ttu-id="2699c-112">**失敗**– ファイルの転送処理に失敗しました、データ アクセスのため、通信するか、タイムアウト例外。</span><span class="sxs-lookup"><span data-stu-id="2699c-112">**Failed** – The file transfer has failed because of a data access, processing, communications or timeout exception.</span></span> <span data-ttu-id="2699c-113">(注: SWIFTNet リンクによってタイムアウトが適用され、値は SWIFT によって決まります)。</span><span class="sxs-lookup"><span data-stu-id="2699c-113">(Note: Timeout is enforced by SWIFTNet Link, and the value is determined by SWIFT).</span></span>  
  
-   <span data-ttu-id="2699c-114">**中止**– ファイルの転送が中止されました (いずれか該当の問題、中止の側面)。</span><span class="sxs-lookup"><span data-stu-id="2699c-114">**Aborted** – The file transfer has been aborted (either side my issue the abort).</span></span>  
  
-   <span data-ttu-id="2699c-115">**不明なと重複している**– タイミングのためだけにこの状態が発生します。</span><span class="sxs-lookup"><span data-stu-id="2699c-115">**Unknown and Duplicated** – This state occurs only because of timing.</span></span> <span data-ttu-id="2699c-116">場合は、送信側ファイルすることは再送信 (PDIndicator) の重複する可能性のあるとしてマークされています。</span><span class="sxs-lookup"><span data-stu-id="2699c-116">In the case of a sender, the file should be re-sent marked as possibly duplicated (PDIndicator).</span></span> <span data-ttu-id="2699c-117">場合は、受信するとき、PDIndicator 意味こと、ファイルが既に送信されて、FileAct アダプターは確認、重複の場合に検出されたは、TransferAnswer が重複している現在の試行を終了するを返します。</span><span class="sxs-lookup"><span data-stu-id="2699c-117">In the case of a receiver, when the PDIndicator implies that the file might have already been sent, the FileAct Adapter will check for the duplication, and if found, will return a TransferAnswer of Duplicated, which will terminate the current attempt.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="2699c-118">参照</span><span class="sxs-lookup"><span data-stu-id="2699c-118">See Also</span></span>  
 <span data-ttu-id="2699c-119">[FileAct アダプターのアーキテクチャ](../../adapters-and-accelerators/fileact-interact/fileact-adapter-architecture.md) </span><span class="sxs-lookup"><span data-stu-id="2699c-119">[FileAct Adapter Architecture](../../adapters-and-accelerators/fileact-interact/fileact-adapter-architecture.md) </span></span>  
 <span data-ttu-id="2699c-120">[FileAct アダプター リアルタイム エンド ツー エンド プリミティブ](../../adapters-and-accelerators/fileact-interact/fileact-adapter-real-time-end-to-end-primitives.md) </span><span class="sxs-lookup"><span data-stu-id="2699c-120">[FileAct Adapter Real-Time End-to-End Primitives](../../adapters-and-accelerators/fileact-interact/fileact-adapter-real-time-end-to-end-primitives.md) </span></span>  
 <span data-ttu-id="2699c-121">[FileAct アダプターのリアルタイム ローカル プリミティブ](../../adapters-and-accelerators/fileact-interact/fileact-adapter-real-time-local-primitives.md) </span><span class="sxs-lookup"><span data-stu-id="2699c-121">[FileAct Adapter Real-Time Local Primitives](../../adapters-and-accelerators/fileact-interact/fileact-adapter-real-time-local-primitives.md) </span></span>  
 <span data-ttu-id="2699c-122">[FileAct アダプター ストア アンド フォワード](../../adapters-and-accelerators/fileact-interact/fileact-adapter-store-and-forward.md) </span><span class="sxs-lookup"><span data-stu-id="2699c-122">[FileAct Adapter Store and Forward](../../adapters-and-accelerators/fileact-interact/fileact-adapter-store-and-forward.md) </span></span>  
 <span data-ttu-id="2699c-123">[FileAct アダプターのセキュリティ アーキテクチャ](../../adapters-and-accelerators/fileact-interact/fileact-adapter-security-architecture.md) </span><span class="sxs-lookup"><span data-stu-id="2699c-123">[FileAct Adapter Security Architecture](../../adapters-and-accelerators/fileact-interact/fileact-adapter-security-architecture.md) </span></span>  
 <span data-ttu-id="2699c-124">[FileAct アダプター ファイルおよび転送の識別](../../adapters-and-accelerators/fileact-interact/fileact-adapter-file-and-transfer-identification.md) </span><span class="sxs-lookup"><span data-stu-id="2699c-124">[FileAct Adapter File and Transfer Identification](../../adapters-and-accelerators/fileact-interact/fileact-adapter-file-and-transfer-identification.md) </span></span>  
 <span data-ttu-id="2699c-125">[FileAct アダプターをサポートする情報の転送](../../adapters-and-accelerators/fileact-interact/fileact-adapter-supporting-information-transfer.md) </span><span class="sxs-lookup"><span data-stu-id="2699c-125">[FileAct Adapter Supporting Information Transfer](../../adapters-and-accelerators/fileact-interact/fileact-adapter-supporting-information-transfer.md) </span></span>  
 [<span data-ttu-id="2699c-126">FileAct アダプター配信通知</span><span class="sxs-lookup"><span data-stu-id="2699c-126">FileAct Adapter Delivery Notification</span></span>](../../adapters-and-accelerators/fileact-interact/fileact-adapter-delivery-notification.md)