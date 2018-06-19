---
title: FileAct アダプター リアルタイム エンド ツー エンド プリミティブ |Microsoft ドキュメント
ms.custom: ''
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: ''
ms.suite: ''
ms.tgt_pltfrm: ''
ms.topic: article
ms.assetid: f8591120-7259-49cb-90ac-954d8be226ed
caps.latest.revision: 5
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: c95e52d4fbd5ec0df8ee580583f429ffe9e0f08d
ms.sourcegitcommit: cb908c540d8f1a692d01dc8f313e16cb4b4e696d
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 09/20/2017
ms.locfileid: "22224930"
---
# <a name="fileact-adapter-real-time-end-to-end-primitives"></a><span data-ttu-id="8d5ab-102">FileAct アダプター リアルタイム エンド ツー エンド プリミティブ</span><span class="sxs-lookup"><span data-stu-id="8d5ab-102">FileAct Adapter Real-Time End-to-End Primitives</span></span>
<span data-ttu-id="8d5ab-103">SWIFTNet プリミティブが、アプリケーションと SWIFTNet リンク (SNL) の間で交換される XML ドキュメントのペアです。</span><span class="sxs-lookup"><span data-stu-id="8d5ab-103">SWIFTNet primitives are a pair of XML documents exchanged between the application and SWIFTNet Link (SNL).</span></span> <span data-ttu-id="8d5ab-104">各エンド ツー エンド プリミティブ型、そこに側のプリミティブ – クライアント (または送信) の横にあるいずれかと、サーバーで 1 つのバージョンの 2 つ (または受信)。</span><span class="sxs-lookup"><span data-stu-id="8d5ab-104">For each end-to-end primitive, there are two versions of the primitive – one at the client (or send) side and one at the server (or receive) side.</span></span> <span data-ttu-id="8d5ab-105">4 つのメッセージの合計が含まれます。 ファイルの配置のプリミティブ、ファイルの取得のプリミティブ型、およびそれぞれに対して配信通知を送信します。</span><span class="sxs-lookup"><span data-stu-id="8d5ab-105">This comprises a total of four messages: Put File primitive, Get File primitive, and a Send Delivery Notification for each.</span></span>  
  
 <span data-ttu-id="8d5ab-106">FileAct エンド ツー エンド プリミティブを次の図に示します。</span><span class="sxs-lookup"><span data-stu-id="8d5ab-106">The following figure shows the FileAct end-to-end primitives.</span></span>  
  
 <span data-ttu-id="8d5ab-107">![FileAct エンド &#45; へ (& a) #45; エンド プリミティブ](../../adapters-and-accelerators/fileact-interact/media/6e3520cc-9ec4-445c-9114-c7cb760c1068.gif "6e3520cc-9ec4-445c-9114-c7cb760c1068")</span><span class="sxs-lookup"><span data-stu-id="8d5ab-107">![FileAct end&#45;to&#45;end primitives](../../adapters-and-accelerators/fileact-interact/media/6e3520cc-9ec4-445c-9114-c7cb760c1068.gif "6e3520cc-9ec4-445c-9114-c7cb760c1068")</span></span>  
  
## <a name="put-file"></a><span data-ttu-id="8d5ab-108">ファイルを配置します。</span><span class="sxs-lookup"><span data-stu-id="8d5ab-108">Put File</span></span>  
 <span data-ttu-id="8d5ab-109">アプリケーションでは、別の SWIFTNet ユーザーのファイル システムにファイルを送信するファイルの Put プリミティブを開始します。</span><span class="sxs-lookup"><span data-stu-id="8d5ab-109">An application initiates the Put File primitive to send a file to the file system of another SWIFTNet user.</span></span> <span data-ttu-id="8d5ab-110">エンド ツー エンド関数としては、クライアント側とサーバーの両方の側ファイルの Put プリミティブです。</span><span class="sxs-lookup"><span data-stu-id="8d5ab-110">As an end-to-end function, there are both client-side and server side Put File primitives.</span></span> <span data-ttu-id="8d5ab-111">これらが共同して、ファイル転送を正常に完了します。</span><span class="sxs-lookup"><span data-stu-id="8d5ab-111">These collaborate together to successfully complete a file transfer.</span></span>  
  
 <span data-ttu-id="8d5ab-112">このような各共同作業は、1 つのファイルを送信します。</span><span class="sxs-lookup"><span data-stu-id="8d5ab-112">Each such collaboration sends a single file.</span></span> <span data-ttu-id="8d5ab-113">複数のファイルの Put プリミティブは、並列で実行する場合があります。</span><span class="sxs-lookup"><span data-stu-id="8d5ab-113">Multiple Put File primitives may be exercised in parallel.</span></span>  
  
## <a name="get-file"></a><span data-ttu-id="8d5ab-114">ファイルを取得します。</span><span class="sxs-lookup"><span data-stu-id="8d5ab-114">Get File</span></span>  
 <span data-ttu-id="8d5ab-115">アプリケーションでは、別の SWIFTNet ユーザーのファイル システムからファイルを取得するファイルの取得プリミティブを開始します。</span><span class="sxs-lookup"><span data-stu-id="8d5ab-115">An application initiates the Get File primitive to retrieve a file from the file system of another SWIFTNet user.</span></span> <span data-ttu-id="8d5ab-116">エンド ツー エンド関数としては、クライアント側とサーバー側の両方のファイルの取得プリミティブです。</span><span class="sxs-lookup"><span data-stu-id="8d5ab-116">As an end-to-end function, there are both client-side and server-side Get File primitives.</span></span> <span data-ttu-id="8d5ab-117">これらが共同して、ファイル転送を正常に完了します。</span><span class="sxs-lookup"><span data-stu-id="8d5ab-117">These collaborate together to successfully complete a file transfer.</span></span>  
  
 <span data-ttu-id="8d5ab-118">このような各共同作業は、1 つのファイルを取得します。</span><span class="sxs-lookup"><span data-stu-id="8d5ab-118">Each such collaboration retrieves a single file.</span></span> <span data-ttu-id="8d5ab-119">複数のファイルの取得プリミティブは、並列で実行する場合があります。</span><span class="sxs-lookup"><span data-stu-id="8d5ab-119">Multiple Get File primitives may be exercised in parallel.</span></span>  
  
## <a name="send-delivery-notification"></a><span data-ttu-id="8d5ab-120">配信通知を送信します。</span><span class="sxs-lookup"><span data-stu-id="8d5ab-120">Send Delivery Notification</span></span>  
 <span data-ttu-id="8d5ab-121">配置のすべてのファイルとプリミティブのすべての Get ファイルを受信側は、ファイルの転送に関連する配信通知を返すファイル要求の送信側のオプションがあります。</span><span class="sxs-lookup"><span data-stu-id="8d5ab-121">Every Put File and every Get File primitive has the option of having the sending side of the file request that the receiving side return a delivery notification related to the file transfer.</span></span> <span data-ttu-id="8d5ab-122">ファイルの Put プリミティブは、要求メッセージには、配信通知の要求が含まれています。</span><span class="sxs-lookup"><span data-stu-id="8d5ab-122">For a Put File primitive, the request message contains the request for a delivery notification.</span></span>  
  
 <span data-ttu-id="8d5ab-123">ファイルの場合、取得プリミティブは、応答メッセージには、配信通知の要求が含まれています。</span><span class="sxs-lookup"><span data-stu-id="8d5ab-123">In the case of a Get File primitive, the response message contains the request for a delivery notification.</span></span>  
  
 <span data-ttu-id="8d5ab-124">どちらの場合、(実行することによって、転送が完了状態になったことを確認する、状態のプリミティブのいずれか)、ファイルを全体が受信されたことと、ファイルを十分に安全にされたことを確認する (たとえば、バック オフィス システムの場合) に格納された後、受信側のアプリケーションでは、送信者への配信の正の値の確認を返す、配信通知プリミティブとは別に実行します。</span><span class="sxs-lookup"><span data-stu-id="8d5ab-124">In either case, after verifying that the file was received in its entirety (by exercising one of the status primitives to check that the transfer reaches the state Completed) and that the file has been adequately safe stored (for example, on a back-office system), the receiving application separately exercises the Delivery Notification primitive to return a positive confirmation of delivery to the sender.</span></span> <span data-ttu-id="8d5ab-125">エンド ツー エンド関数としては、クライアント側とサーバー側の両方の配信通知プリミティブがあります。</span><span class="sxs-lookup"><span data-stu-id="8d5ab-125">As an end-to-end function, there are both client-side and server-side Delivery Notification primitives.</span></span> <span data-ttu-id="8d5ab-126">これらが共同して、ファイル配信通知を正常に完了します。</span><span class="sxs-lookup"><span data-stu-id="8d5ab-126">These collaborate together to successfully complete a file delivery notification.</span></span>  
  
 <span data-ttu-id="8d5ab-127">配信通知を設定し、送信側と受信側のファイルの間のプロトコルを適用サービス デザイナーが必要です。</span><span class="sxs-lookup"><span data-stu-id="8d5ab-127">Delivery notification requires the service designer to establish and enforce a protocol between the senders and receivers of files.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="8d5ab-128">参照</span><span class="sxs-lookup"><span data-stu-id="8d5ab-128">See Also</span></span>  
 <span data-ttu-id="8d5ab-129">[FileAct アダプターのアーキテクチャ](../../adapters-and-accelerators/fileact-interact/fileact-adapter-architecture.md) </span><span class="sxs-lookup"><span data-stu-id="8d5ab-129">[FileAct Adapter Architecture](../../adapters-and-accelerators/fileact-interact/fileact-adapter-architecture.md) </span></span>  
 <span data-ttu-id="8d5ab-130">[FileAct アダプターのリアルタイム ローカル プリミティブ](../../adapters-and-accelerators/fileact-interact/fileact-adapter-real-time-local-primitives.md) </span><span class="sxs-lookup"><span data-stu-id="8d5ab-130">[FileAct Adapter Real-Time Local Primitives](../../adapters-and-accelerators/fileact-interact/fileact-adapter-real-time-local-primitives.md) </span></span>  
 <span data-ttu-id="8d5ab-131">[FileAct アダプター ストア アンド フォワード](../../adapters-and-accelerators/fileact-interact/fileact-adapter-store-and-forward.md) </span><span class="sxs-lookup"><span data-stu-id="8d5ab-131">[FileAct Adapter Store and Forward](../../adapters-and-accelerators/fileact-interact/fileact-adapter-store-and-forward.md) </span></span>  
 <span data-ttu-id="8d5ab-132">[FileAct アダプターのセキュリティ アーキテクチャ](../../adapters-and-accelerators/fileact-interact/fileact-adapter-security-architecture.md) </span><span class="sxs-lookup"><span data-stu-id="8d5ab-132">[FileAct Adapter Security Architecture](../../adapters-and-accelerators/fileact-interact/fileact-adapter-security-architecture.md) </span></span>  
 <span data-ttu-id="8d5ab-133">[FileAct アダプター ファイルおよび転送の識別](../../adapters-and-accelerators/fileact-interact/fileact-adapter-file-and-transfer-identification.md) </span><span class="sxs-lookup"><span data-stu-id="8d5ab-133">[FileAct Adapter File and Transfer Identification](../../adapters-and-accelerators/fileact-interact/fileact-adapter-file-and-transfer-identification.md) </span></span>  
 <span data-ttu-id="8d5ab-134">[FileAct アダプターをサポートする情報の転送](../../adapters-and-accelerators/fileact-interact/fileact-adapter-supporting-information-transfer.md) </span><span class="sxs-lookup"><span data-stu-id="8d5ab-134">[FileAct Adapter Supporting Information Transfer](../../adapters-and-accelerators/fileact-interact/fileact-adapter-supporting-information-transfer.md) </span></span>  
 <span data-ttu-id="8d5ab-135">[FileAct アダプター配信通知](../../adapters-and-accelerators/fileact-interact/fileact-adapter-delivery-notification.md) </span><span class="sxs-lookup"><span data-stu-id="8d5ab-135">[FileAct Adapter Delivery Notification](../../adapters-and-accelerators/fileact-interact/fileact-adapter-delivery-notification.md) </span></span>  
 [<span data-ttu-id="8d5ab-136">FileAct アダプター状態の監視</span><span class="sxs-lookup"><span data-stu-id="8d5ab-136">FileAct Adapter Status Monitoring</span></span>](../../adapters-and-accelerators/fileact-interact/fileact-adapter-status-monitoring.md)