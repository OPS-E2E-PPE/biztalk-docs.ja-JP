---
title: FileAct アダプターの状態の監視 |Microsoft Docs
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
ms.openlocfilehash: 1701e68b592e7f6eab012d14b1a14d6143c09da9
ms.sourcegitcommit: 381e83d43796a345488d54b3f7413e11d56ad7be
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 05/07/2019
ms.locfileid: "65367154"
---
# <a name="fileact-adapter-status-monitoring"></a><span data-ttu-id="c1d97-102">FileAct アダプターの状態の監視</span><span class="sxs-lookup"><span data-stu-id="c1d97-102">FileAct Adapter Status Monitoring</span></span>
<span data-ttu-id="c1d97-103">ファイル転送、およびこれらの状態遷移の状態は、次の図に示します。</span><span class="sxs-lookup"><span data-stu-id="c1d97-103">The possible states of a file transfer and the transitions between those states are illustrated in the following figure.</span></span>  
  
 <span data-ttu-id="c1d97-104">![FileAct アダプター ファイル転送状態](../../adapters-and-accelerators/fileact-interact/media/2e01feaa-6b68-49a2-a47d-6359be1f4034.gif "2e01feaa-6b68-49a2-a47d-6359be1f4034")</span><span class="sxs-lookup"><span data-stu-id="c1d97-104">![FileAct adapter file transfer states](../../adapters-and-accelerators/fileact-interact/media/2e01feaa-6b68-49a2-a47d-6359be1f4034.gif "2e01feaa-6b68-49a2-a47d-6359be1f4034")</span></span>  
  
 <span data-ttu-id="c1d97-105">ファイル転送の状態は次のとおりです。</span><span class="sxs-lookup"><span data-stu-id="c1d97-105">The file transfer states are:</span></span>  
  
-   <span data-ttu-id="c1d97-106">**開始**– クライアントは、サーバーに、ネゴシエーション メッセージが送信しますが、まだ応答を受け取っていません。</span><span class="sxs-lookup"><span data-stu-id="c1d97-106">**Initiated** – The client has sent the negotiation message to the server, but has not yet received the response.</span></span> <span data-ttu-id="c1d97-107">サーバーは、ネゴシエーションの要求を受け取りましたが、まだ応答は送信されません。</span><span class="sxs-lookup"><span data-stu-id="c1d97-107">The server has received the negotiation request, but has not yet sent the response.</span></span>  
  
-   <span data-ttu-id="c1d97-108">**受け入れられる**転送が進行中 – と、サーバーが要求を受け入れるし、応答メッセージで、TransferAnswer が送信されます。</span><span class="sxs-lookup"><span data-stu-id="c1d97-108">**Accepted** – The server has accepted the request and has sent the TransferAnswer in the response message, and the transfer is still in progress.</span></span>  
  
-   <span data-ttu-id="c1d97-109">**拒否**– サーバー要求を拒否しましたが、応答メッセージには、TransferAnswer および転送が終了します。</span><span class="sxs-lookup"><span data-stu-id="c1d97-109">**Rejected** – The server has rejected the request and has the TransferAnswer in the response message, and has terminated the transfer.</span></span>  
  
-   <span data-ttu-id="c1d97-110">**継続的な**: 転送が進行中とは (定期的に更新上記として) 続行されます。</span><span class="sxs-lookup"><span data-stu-id="c1d97-110">**Ongoing** – The transfer is in progress and is proceeding (renewed periodically as above).</span></span>  
  
-   <span data-ttu-id="c1d97-111">**完了した**– ダイジェスト値の比較を含む、転送の側がに関する限り、ファイル転送が正常に完了します。</span><span class="sxs-lookup"><span data-stu-id="c1d97-111">**Completed** – The file transfer has completed successfully as far as that side of the transfer is concerned, including the comparison of the digest value.</span></span>  
  
-   <span data-ttu-id="c1d97-112">**失敗**– ファイルの転送が、データ アクセスのため通信またはタイムアウトの例外の処理が失敗しました。</span><span class="sxs-lookup"><span data-stu-id="c1d97-112">**Failed** – The file transfer has failed because of a data access, processing, communications or timeout exception.</span></span> <span data-ttu-id="c1d97-113">(注。SWIFTNet リンクでタイムアウトが適用され、値によって決定されます SWIFT)。</span><span class="sxs-lookup"><span data-stu-id="c1d97-113">(Note: Timeout is enforced by SWIFTNet Link, and the value is determined by SWIFT).</span></span>  
  
-   <span data-ttu-id="c1d97-114">**中止**– ファイルの転送が中止されました (いずれかの側面、中止問題)。</span><span class="sxs-lookup"><span data-stu-id="c1d97-114">**Aborted** – The file transfer has been aborted (either side my issue the abort).</span></span>  
  
-   <span data-ttu-id="c1d97-115">**不明なと重複している**– この状態は、タイミングのためのみに発生します。</span><span class="sxs-lookup"><span data-stu-id="c1d97-115">**Unknown and Duplicated** – This state occurs only because of timing.</span></span> <span data-ttu-id="c1d97-116">場合は、送信側、ファイルがあります再送信 (PDIndicator) を重複している可能性があるとしてマークされています。</span><span class="sxs-lookup"><span data-stu-id="c1d97-116">In the case of a sender, the file should be re-sent marked as possibly duplicated (PDIndicator).</span></span> <span data-ttu-id="c1d97-117">場合は、受信側、PDIndicator 意味のあるファイルが既に送信されて、FileAct アダプターは確認、重複の場合に見つかりましたでは、TransferAnswer の重複している現在の試行が終了するのに戻ります。</span><span class="sxs-lookup"><span data-stu-id="c1d97-117">In the case of a receiver, when the PDIndicator implies that the file might have already been sent, the FileAct Adapter will check for the duplication, and if found, will return a TransferAnswer of Duplicated, which will terminate the current attempt.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="c1d97-118">参照</span><span class="sxs-lookup"><span data-stu-id="c1d97-118">See Also</span></span>  
 <span data-ttu-id="c1d97-119">[FileAct アダプターのアーキテクチャ](../../adapters-and-accelerators/fileact-interact/fileact-adapter-architecture.md) </span><span class="sxs-lookup"><span data-stu-id="c1d97-119">[FileAct Adapter Architecture](../../adapters-and-accelerators/fileact-interact/fileact-adapter-architecture.md) </span></span>  
 <span data-ttu-id="c1d97-120">[FileAct アダプターのリアルタイム エンド ツー エンド プリミティブ](../../adapters-and-accelerators/fileact-interact/fileact-adapter-real-time-end-to-end-primitives.md) </span><span class="sxs-lookup"><span data-stu-id="c1d97-120">[FileAct Adapter Real-Time End-to-End Primitives](../../adapters-and-accelerators/fileact-interact/fileact-adapter-real-time-end-to-end-primitives.md) </span></span>  
 <span data-ttu-id="c1d97-121">[FileAct アダプターのリアルタイム ローカル プリミティブ](../../adapters-and-accelerators/fileact-interact/fileact-adapter-real-time-local-primitives.md) </span><span class="sxs-lookup"><span data-stu-id="c1d97-121">[FileAct Adapter Real-Time Local Primitives](../../adapters-and-accelerators/fileact-interact/fileact-adapter-real-time-local-primitives.md) </span></span>  
 <span data-ttu-id="c1d97-122">[FileAct アダプターのストア アンド フォワード](../../adapters-and-accelerators/fileact-interact/fileact-adapter-store-and-forward.md) </span><span class="sxs-lookup"><span data-stu-id="c1d97-122">[FileAct Adapter Store and Forward](../../adapters-and-accelerators/fileact-interact/fileact-adapter-store-and-forward.md) </span></span>  
 <span data-ttu-id="c1d97-123">[FileAct アダプターのセキュリティ アーキテクチャ](../../adapters-and-accelerators/fileact-interact/fileact-adapter-security-architecture.md) </span><span class="sxs-lookup"><span data-stu-id="c1d97-123">[FileAct Adapter Security Architecture](../../adapters-and-accelerators/fileact-interact/fileact-adapter-security-architecture.md) </span></span>  
 <span data-ttu-id="c1d97-124">[FileAct アダプター ファイルおよび転送 Id](../../adapters-and-accelerators/fileact-interact/fileact-adapter-file-and-transfer-identification.md) </span><span class="sxs-lookup"><span data-stu-id="c1d97-124">[FileAct Adapter File and Transfer Identification](../../adapters-and-accelerators/fileact-interact/fileact-adapter-file-and-transfer-identification.md) </span></span>  
 <span data-ttu-id="c1d97-125">[FileAct アダプターのサポート情報の転送](../../adapters-and-accelerators/fileact-interact/fileact-adapter-supporting-information-transfer.md) </span><span class="sxs-lookup"><span data-stu-id="c1d97-125">[FileAct Adapter Supporting Information Transfer](../../adapters-and-accelerators/fileact-interact/fileact-adapter-supporting-information-transfer.md) </span></span>  
 [<span data-ttu-id="c1d97-126">FileAct アダプターの配信通知</span><span class="sxs-lookup"><span data-stu-id="c1d97-126">FileAct Adapter Delivery Notification</span></span>](../../adapters-and-accelerators/fileact-interact/fileact-adapter-delivery-notification.md)