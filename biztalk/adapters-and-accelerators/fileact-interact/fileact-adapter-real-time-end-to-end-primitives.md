---
title: FileAct アダプターのリアルタイム エンド ツー エンド プリミティブ |Microsoft Docs
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
ms.openlocfilehash: 0532c0240be0032a46100e46d9cd58d4ff4820e9
ms.sourcegitcommit: 381e83d43796a345488d54b3f7413e11d56ad7be
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 05/07/2019
ms.locfileid: "65367177"
---
# <a name="fileact-adapter-real-time-end-to-end-primitives"></a><span data-ttu-id="46def-102">FileAct アダプターのリアルタイム エンド ツー エンド プリミティブ</span><span class="sxs-lookup"><span data-stu-id="46def-102">FileAct Adapter Real-Time End-to-End Primitives</span></span>
<span data-ttu-id="46def-103">SWIFTNet プリミティブは、アプリケーションと SWIFTNet リンク (SNL) 間で交換する XML ドキュメントのペアです。</span><span class="sxs-lookup"><span data-stu-id="46def-103">SWIFTNet primitives are a pair of XML documents exchanged between the application and SWIFTNet Link (SNL).</span></span> <span data-ttu-id="46def-104">各エンド ツー エンド プリミティブ型、そこの側をプリミティブ – クライアント (または送信) の横にあるいずれかと、サーバーで 1 つの 2 つのバージョン (または受信)。</span><span class="sxs-lookup"><span data-stu-id="46def-104">For each end-to-end primitive, there are two versions of the primitive – one at the client (or send) side and one at the server (or receive) side.</span></span> <span data-ttu-id="46def-105">これには、4 つのメッセージの合計が構成されています。各ファイルのプリミティブ型、ファイルの取得のプリミティブ型、および配信通知の送信を配置します。</span><span class="sxs-lookup"><span data-stu-id="46def-105">This comprises a total of four messages: Put File primitive, Get File primitive, and a Send Delivery Notification for each.</span></span>  
  
 <span data-ttu-id="46def-106">FileAct エンド ツー エンド プリミティブの図は、次のとおりです。</span><span class="sxs-lookup"><span data-stu-id="46def-106">The following figure shows the FileAct end-to-end primitives.</span></span>  
  
 <span data-ttu-id="46def-107">![FileAct エンド&#45;に&#45;プリミティブを終了](../../adapters-and-accelerators/fileact-interact/media/6e3520cc-9ec4-445c-9114-c7cb760c1068.gif "6e3520cc-9ec4-445c-9114-c7cb760c1068")</span><span class="sxs-lookup"><span data-stu-id="46def-107">![FileAct end&#45;to&#45;end primitives](../../adapters-and-accelerators/fileact-interact/media/6e3520cc-9ec4-445c-9114-c7cb760c1068.gif "6e3520cc-9ec4-445c-9114-c7cb760c1068")</span></span>  
  
## <a name="put-file"></a><span data-ttu-id="46def-108">ファイルを配置します。</span><span class="sxs-lookup"><span data-stu-id="46def-108">Put File</span></span>  
 <span data-ttu-id="46def-109">アプリケーションは、別の SWIFTNet ユーザーのファイル システムにファイルを送信するファイルの配置プリミティブを開始します。</span><span class="sxs-lookup"><span data-stu-id="46def-109">An application initiates the Put File primitive to send a file to the file system of another SWIFTNet user.</span></span> <span data-ttu-id="46def-110">エンド ツー エンド関数では、クライアント側とサーバーの両方の側ファイルの配置のプリミティブがあります。</span><span class="sxs-lookup"><span data-stu-id="46def-110">As an end-to-end function, there are both client-side and server side Put File primitives.</span></span> <span data-ttu-id="46def-111">これらが協調して、ファイル転送を正常に完了します。</span><span class="sxs-lookup"><span data-stu-id="46def-111">These collaborate together to successfully complete a file transfer.</span></span>  
  
 <span data-ttu-id="46def-112">このような各コラボレーションでは、1 つのファイルを送信します。</span><span class="sxs-lookup"><span data-stu-id="46def-112">Each such collaboration sends a single file.</span></span> <span data-ttu-id="46def-113">複数ファイルの配置のプリミティブは、並列で実行する可能性があります。</span><span class="sxs-lookup"><span data-stu-id="46def-113">Multiple Put File primitives may be exercised in parallel.</span></span>  
  
## <a name="get-file"></a><span data-ttu-id="46def-114">ファイルを取得します。</span><span class="sxs-lookup"><span data-stu-id="46def-114">Get File</span></span>  
 <span data-ttu-id="46def-115">アプリケーションは、別の SWIFTNet ユーザーのファイル システムからファイルを取得するファイルの取得のプリミティブを開始します。</span><span class="sxs-lookup"><span data-stu-id="46def-115">An application initiates the Get File primitive to retrieve a file from the file system of another SWIFTNet user.</span></span> <span data-ttu-id="46def-116">エンド ツー エンド関数では、クライアント側とサーバー側の両方のファイルの取得のプリミティブがあります。</span><span class="sxs-lookup"><span data-stu-id="46def-116">As an end-to-end function, there are both client-side and server-side Get File primitives.</span></span> <span data-ttu-id="46def-117">これらが協調して、ファイル転送を正常に完了します。</span><span class="sxs-lookup"><span data-stu-id="46def-117">These collaborate together to successfully complete a file transfer.</span></span>  
  
 <span data-ttu-id="46def-118">このような各コラボレーションでは、1 つのファイルを取得します。</span><span class="sxs-lookup"><span data-stu-id="46def-118">Each such collaboration retrieves a single file.</span></span> <span data-ttu-id="46def-119">複数のファイルの取得プリミティブは、並列で実行する可能性があります。</span><span class="sxs-lookup"><span data-stu-id="46def-119">Multiple Get File primitives may be exercised in parallel.</span></span>  
  
## <a name="send-delivery-notification"></a><span data-ttu-id="46def-120">配信通知を送信します。</span><span class="sxs-lookup"><span data-stu-id="46def-120">Send Delivery Notification</span></span>  
 <span data-ttu-id="46def-121">配置のすべてのファイルとプリミティブのすべての Get ファイルを受信側は、ファイル転送に関連する配信通知を返すファイル要求の送信側のオプションがあります。</span><span class="sxs-lookup"><span data-stu-id="46def-121">Every Put File and every Get File primitive has the option of having the sending side of the file request that the receiving side return a delivery notification related to the file transfer.</span></span> <span data-ttu-id="46def-122">ファイルの配置のプリミティブでは、要求メッセージには配信通知の要求が含まれます。</span><span class="sxs-lookup"><span data-stu-id="46def-122">For a Put File primitive, the request message contains the request for a delivery notification.</span></span>  
  
 <span data-ttu-id="46def-123">取得プリミティブ、ファイルの場合は、応答メッセージには、配信通知の要求が含まれています。</span><span class="sxs-lookup"><span data-stu-id="46def-123">In the case of a Get File primitive, the response message contains the request for a delivery notification.</span></span>  
  
 <span data-ttu-id="46def-124">どちらの場合 (たとえば、バック オフィス システムの場合) に格納されている (使用することにより、転送が完了状態になったことを確認する状態のプリミティブのいずれか) 全体、ファイルが受信されたことと、ファイルを十分に安全にされたことを確認した後で、受信側アプリケーションでは、配信通知プリミティブを送信者に配信の肯定的な確認を返すとは別に実行します。</span><span class="sxs-lookup"><span data-stu-id="46def-124">In either case, after verifying that the file was received in its entirety (by exercising one of the status primitives to check that the transfer reaches the state Completed) and that the file has been adequately safe stored (for example, on a back-office system), the receiving application separately exercises the Delivery Notification primitive to return a positive confirmation of delivery to the sender.</span></span> <span data-ttu-id="46def-125">エンド ツー エンド関数では、クライアント側とサーバー側の両方の配信通知プリミティブがあります。</span><span class="sxs-lookup"><span data-stu-id="46def-125">As an end-to-end function, there are both client-side and server-side Delivery Notification primitives.</span></span> <span data-ttu-id="46def-126">これらが協調して、ファイルの配信通知を正常に完了します。</span><span class="sxs-lookup"><span data-stu-id="46def-126">These collaborate together to successfully complete a file delivery notification.</span></span>  
  
 <span data-ttu-id="46def-127">配信通知には、サービスのデザイナーを構築し、送信側とファイルの受信側でプロトコルを適用する必要があります。</span><span class="sxs-lookup"><span data-stu-id="46def-127">Delivery notification requires the service designer to establish and enforce a protocol between the senders and receivers of files.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="46def-128">参照</span><span class="sxs-lookup"><span data-stu-id="46def-128">See Also</span></span>  
 <span data-ttu-id="46def-129">[FileAct アダプターのアーキテクチャ](../../adapters-and-accelerators/fileact-interact/fileact-adapter-architecture.md) </span><span class="sxs-lookup"><span data-stu-id="46def-129">[FileAct Adapter Architecture](../../adapters-and-accelerators/fileact-interact/fileact-adapter-architecture.md) </span></span>  
 <span data-ttu-id="46def-130">[FileAct アダプターのリアルタイム ローカル プリミティブ](../../adapters-and-accelerators/fileact-interact/fileact-adapter-real-time-local-primitives.md) </span><span class="sxs-lookup"><span data-stu-id="46def-130">[FileAct Adapter Real-Time Local Primitives](../../adapters-and-accelerators/fileact-interact/fileact-adapter-real-time-local-primitives.md) </span></span>  
 <span data-ttu-id="46def-131">[FileAct アダプターのストア アンド フォワード](../../adapters-and-accelerators/fileact-interact/fileact-adapter-store-and-forward.md) </span><span class="sxs-lookup"><span data-stu-id="46def-131">[FileAct Adapter Store and Forward](../../adapters-and-accelerators/fileact-interact/fileact-adapter-store-and-forward.md) </span></span>  
 <span data-ttu-id="46def-132">[FileAct アダプターのセキュリティ アーキテクチャ](../../adapters-and-accelerators/fileact-interact/fileact-adapter-security-architecture.md) </span><span class="sxs-lookup"><span data-stu-id="46def-132">[FileAct Adapter Security Architecture](../../adapters-and-accelerators/fileact-interact/fileact-adapter-security-architecture.md) </span></span>  
 <span data-ttu-id="46def-133">[FileAct アダプター ファイルおよび転送 Id](../../adapters-and-accelerators/fileact-interact/fileact-adapter-file-and-transfer-identification.md) </span><span class="sxs-lookup"><span data-stu-id="46def-133">[FileAct Adapter File and Transfer Identification](../../adapters-and-accelerators/fileact-interact/fileact-adapter-file-and-transfer-identification.md) </span></span>  
 <span data-ttu-id="46def-134">[FileAct アダプターのサポート情報の転送](../../adapters-and-accelerators/fileact-interact/fileact-adapter-supporting-information-transfer.md) </span><span class="sxs-lookup"><span data-stu-id="46def-134">[FileAct Adapter Supporting Information Transfer](../../adapters-and-accelerators/fileact-interact/fileact-adapter-supporting-information-transfer.md) </span></span>  
 <span data-ttu-id="46def-135">[FileAct アダプターの配信通知](../../adapters-and-accelerators/fileact-interact/fileact-adapter-delivery-notification.md) </span><span class="sxs-lookup"><span data-stu-id="46def-135">[FileAct Adapter Delivery Notification](../../adapters-and-accelerators/fileact-interact/fileact-adapter-delivery-notification.md) </span></span>  
 [<span data-ttu-id="46def-136">FileAct アダプターの状態監視</span><span class="sxs-lookup"><span data-stu-id="46def-136">FileAct Adapter Status Monitoring</span></span>](../../adapters-and-accelerators/fileact-interact/fileact-adapter-status-monitoring.md)