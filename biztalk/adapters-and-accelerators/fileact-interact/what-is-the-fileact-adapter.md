---
title: "FileAct アダプターとは何ですか。 | Microsoft Docs"
ms.custom: 
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: 
ms.suite: 
ms.tgt_pltfrm: 
ms.topic: article
ms.assetid: 05ec8f1e-57f9-4e2d-ab8b-22b5c4b28055
caps.latest.revision: "9"
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: 62b83fc723bbebce857eb442384b14179c1072ad
ms.sourcegitcommit: cb908c540d8f1a692d01dc8f313e16cb4b4e696d
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 09/20/2017
---
# <a name="what-is-the-fileact-adapter"></a><span data-ttu-id="84140-103">FileAct アダプターとは何ですか。</span><span class="sxs-lookup"><span data-stu-id="84140-103">What Is the FileAct Adapter?</span></span>
<span data-ttu-id="84140-104">SWIFTNet の FileAct アダプターは、ファイルを転送するための世界銀行間財務通信 (SWIFT) セキュリティで保護された IP ネットワーク (SIPN) の BizTalk Server と、Society 間の接続に提供します。</span><span class="sxs-lookup"><span data-stu-id="84140-104">The FileAct adapter for SWIFTNet provides connectivity between BizTalk Server and the Society for Worldwide Interbank Financial Telecommunication (SWIFT) Secure IP Network (SIPN) for the transfer of files.</span></span> <span data-ttu-id="84140-105">SIPN は、金融機関、金融業界インフラストラクチャ、および顧客を接続するセキュリティで保護されたプライベート ネットワーク経由でメッセージとファイルを転送します。</span><span class="sxs-lookup"><span data-stu-id="84140-105">The SIPN transfers messages and files over a secure private network which connects financial institutions, financial industry infrastructures, and customers.</span></span> <span data-ttu-id="84140-106">FileAct アダプターは、SWIFTNet リンク (SNL) アプリケーション プログラミング インターフェイス (API) s、SIPN への接続に使用します。</span><span class="sxs-lookup"><span data-stu-id="84140-106">The FileAct adapter uses the SWIFTNet Link (SNL) application programming interface (API)s to connect to the SIPN.</span></span>  
  
 <span data-ttu-id="84140-107">FileAct アダプターは、安全に SWIFT の参加者のメカニズムを提供し、ファイルとそれらのファイルに関連する情報を確実に交換します。</span><span class="sxs-lookup"><span data-stu-id="84140-107">The FileAct adapter provides a mechanism for SWIFT participants to securely and reliably exchange files and information pertaining to those files.</span></span> <span data-ttu-id="84140-108">次の機能がサポートされています。</span><span class="sxs-lookup"><span data-stu-id="84140-108">It supports the following functionality:</span></span>  
  
-   <span data-ttu-id="84140-109">SWIFTNet ユーザーにファイルを送信します。</span><span class="sxs-lookup"><span data-stu-id="84140-109">Sending files to a SWIFTNet User</span></span>  
  
-   <span data-ttu-id="84140-110">SWIFTNet ユーザーからファイルを取得します。</span><span class="sxs-lookup"><span data-stu-id="84140-110">Retrieving files from a SWIFTNet User</span></span>  
  
-   <span data-ttu-id="84140-111">配信通知の受信側でのファイルの受信を確認します。</span><span class="sxs-lookup"><span data-stu-id="84140-111">Delivery notification confirming file receipt by a receiver</span></span>  
  
-   <span data-ttu-id="84140-112">進行中の転送を中止します。</span><span class="sxs-lookup"><span data-stu-id="84140-112">Abort of transfers in progress</span></span>  
  
-   <span data-ttu-id="84140-113">ファイルの転送の状態の監視</span><span class="sxs-lookup"><span data-stu-id="84140-113">File transfer state monitoring</span></span>  
  
-   <span data-ttu-id="84140-114">同時実行のファイル転送</span><span class="sxs-lookup"><span data-stu-id="84140-114">Concurrent file transfers</span></span>  
  
-   <span data-ttu-id="84140-115">データの完全性と整合性の保証</span><span class="sxs-lookup"><span data-stu-id="84140-115">Assurance of data authenticity and integrity</span></span>  
  
-   <span data-ttu-id="84140-116">転送中にファイル データの機密性</span><span class="sxs-lookup"><span data-stu-id="84140-116">Confidentiality of file data in transit</span></span>  
  
-   <span data-ttu-id="84140-117">ファイル転送の否認不可</span><span class="sxs-lookup"><span data-stu-id="84140-117">Non-repudiation of file transfers</span></span>  
  
-   <span data-ttu-id="84140-118">タイムスタンプ</span><span class="sxs-lookup"><span data-stu-id="84140-118">Time-stamping</span></span>  
  
## <a name="the-fileact-service"></a><span data-ttu-id="84140-119">FileAct サービス</span><span class="sxs-lookup"><span data-stu-id="84140-119">The FileAct Service</span></span>  
 <span data-ttu-id="84140-120">SWIFTNet の FileAct アダプターは、構造化された財務メッセージまたはサイズの大きなレポートのバッチなどのファイルの安全性と信頼性の高い転送を提供します。</span><span class="sxs-lookup"><span data-stu-id="84140-120">The FileAct adapter for SWIFTNet provides secure and reliable transfer of files, such as batches of structured financial messages or large reports.</span></span> <span data-ttu-id="84140-121">一般的なアプリケーションには、反復的なクレジット転送年金または給与支払、証券付加価値のある情報とレポート、および規制 reporting などが含まれます。</span><span class="sxs-lookup"><span data-stu-id="84140-121">Typical applications include repetitive credit transfers such as pension or salary payments, securities value-added information and reporting, and regulatory reporting.</span></span> <span data-ttu-id="84140-122">SWIFTNet FileAct には、さまざまなメッセージング モードが提供しています。</span><span class="sxs-lookup"><span data-stu-id="84140-122">SWIFTNet FileAct offers a variety of messaging modes:</span></span>  
  
-   <span data-ttu-id="84140-123">**ストア アンド フォワード ファイル転送します。**</span><span class="sxs-lookup"><span data-stu-id="84140-123">**Store-and-forward file transfer.**</span></span> <span data-ttu-id="84140-124">SWIFTNet FileAct ストア アンド フォワードの機能は、不確実性とするかどうか、ユーザーはオンライン時のファイルを送信する心配不便さを削除します。</span><span class="sxs-lookup"><span data-stu-id="84140-124">SWIFTNet FileAct’s store-and-forward capability removes the uncertainty and inconvenience of worrying about whether or not your correspondents are online at the time you transmit the file.</span></span> <span data-ttu-id="84140-125">ファイルは、受信者がメッセージを受信する準備がすぐに配信されます。</span><span class="sxs-lookup"><span data-stu-id="84140-125">The file is delivered as soon as the recipient is ready to receive it.</span></span> <span data-ttu-id="84140-126">その結果、多数のうち一部異なるタイム ゾーンでは、ユーザーにファイルを送信するための望ましい方法を提供します。</span><span class="sxs-lookup"><span data-stu-id="84140-126">As a result, it provides an ideal way to send files to large numbers of correspondents, some of which may be in different time zones.</span></span>  
  
-   <span data-ttu-id="84140-127">**リアルタイムのファイル転送します。**</span><span class="sxs-lookup"><span data-stu-id="84140-127">**Real-time file transfer.**</span></span> <span data-ttu-id="84140-128">リアルタイムのメッセージング、格納および転送時にオンラインになっている相手の送信先となるファイルの転送に低コストの選択肢が用意されています。</span><span class="sxs-lookup"><span data-stu-id="84140-128">Real-time messaging offers a lower-cost alternative to store and forward for files that are destined for correspondents that are online at the time of transmission.</span></span> <span data-ttu-id="84140-129">その結果、いくつかの大きな見または市場インフラストラクチャにファイルを送信するために最適です。</span><span class="sxs-lookup"><span data-stu-id="84140-129">As a result it is ideal for sending files to a few large correspondents or market infrastructures.</span></span>  
  
-   <span data-ttu-id="84140-130">**リアルタイムのファイルを取得します。**</span><span class="sxs-lookup"><span data-stu-id="84140-130">**Real-time file retrieval.**</span></span> <span data-ttu-id="84140-131">これは、通常ワークステーション ベースのシステムのコンテキストでは、多くの場合、SWIFTNet 参照と共にのファイルを取得するために使用する対話型サービスです。</span><span class="sxs-lookup"><span data-stu-id="84140-131">This is an interactive service typically used to retrieve files in the context of workstation-based systems and often in conjunction with SWIFTNet Browse.</span></span> <span data-ttu-id="84140-132">このモードがサポートされます。</span><span class="sxs-lookup"><span data-stu-id="84140-132">We will support this mode.</span></span>  
  
 <span data-ttu-id="84140-133">(ファイルをファイルごと) に省略可能な SWIFTNet FileAct 機能は次のとおりです。</span><span class="sxs-lookup"><span data-stu-id="84140-133">The optional SWIFTNet FileAct features (on a file by file basis) include:</span></span>  
  
-   <span data-ttu-id="84140-134">**メッセージの優先度。**</span><span class="sxs-lookup"><span data-stu-id="84140-134">**Message priority.**</span></span> <span data-ttu-id="84140-135">ファイル転送フラグを設定できます「緊急」としてメッセージで、適切な相手の処理を許可します。</span><span class="sxs-lookup"><span data-stu-id="84140-135">File transfers can be flagged as “Urgent” in the message, to allow for appropriate processing by your correspondents.</span></span>  
  
-   <span data-ttu-id="84140-136">**配信通知 (リアルタイムおよびストア アンド フォワード モード)。**</span><span class="sxs-lookup"><span data-stu-id="84140-136">**Delivery notification (real-time and store-and-forward modes).**</span></span> <span data-ttu-id="84140-137">相手には、ファイルが受信されたことの確認を提供します。</span><span class="sxs-lookup"><span data-stu-id="84140-137">Provides confirmation that your correspondent received your file.</span></span>  
  
-   <span data-ttu-id="84140-138">**否認不可の出力と受信します。**</span><span class="sxs-lookup"><span data-stu-id="84140-138">**Non-repudiation of emission and reception.**</span></span> <span data-ttu-id="84140-139">に関して問題が発生した場合に、ファイル転送が行われるように要求を確認する SWIFT を使用できます。</span><span class="sxs-lookup"><span data-stu-id="84140-139">In case of dispute, allows SWIFT to confirm that the file transfer did take place as claimed.</span></span>  
  
 <span data-ttu-id="84140-140">標準の SWIFTNet FileAct 機能に SWIFTNet PKI のセキュリティは、**です。**</span><span class="sxs-lookup"><span data-stu-id="84140-140">The standard SWIFTNet FileAct features include SWIFTNet PKI security**.**</span></span> <span data-ttu-id="84140-141">SWIFTNet FileAct は SWIFTNet PKI を使用して保護し、メッセージの認証と整合性の制御を提供します。</span><span class="sxs-lookup"><span data-stu-id="84140-141">SWIFTNet FileAct is secured with SWIFTNet PKI and offers message authentication and integrity control.</span></span>  
  
 <span data-ttu-id="84140-142">すべてのメッセージと SWIFTNet で交換されるファイルには、一般的な一連のあるユーザーをバイパスできませんセキュリティ、検証、およびプラットフォームのルーティング規則を確認するチェックが行われます。</span><span class="sxs-lookup"><span data-stu-id="84140-142">All messages and files exchanged on SWIFTNet undergo a common set of checks to ensure that no user can bypass the security, validation and routing rules of the platform.</span></span> <span data-ttu-id="84140-143">これらのチェックは、SWIFTAlliance ゲートウェイ (SAG) アプリケーションによって実行されます。</span><span class="sxs-lookup"><span data-stu-id="84140-143">These checks are performed by the SWIFTAlliance Gateway (SAG) application.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="84140-144">参照</span><span class="sxs-lookup"><span data-stu-id="84140-144">See Also</span></span>  
 <span data-ttu-id="84140-145">[入門、FileAct および InterAct アダプター](../../adapters-and-accelerators/fileact-interact/getting-started-with-the-fileact-and-interact-adapters.md) </span><span class="sxs-lookup"><span data-stu-id="84140-145">[Getting Started with the FileAct and InterAct Adapters](../../adapters-and-accelerators/fileact-interact/getting-started-with-the-fileact-and-interact-adapters.md) </span></span>  
 <span data-ttu-id="84140-146">[SWIFTNet とは何ですか。](../../adapters-and-accelerators/fileact-interact/what-is-swiftnet.md) </span><span class="sxs-lookup"><span data-stu-id="84140-146">[What Is SWIFTNet?](../../adapters-and-accelerators/fileact-interact/what-is-swiftnet.md) </span></span>  
 [<span data-ttu-id="84140-147">アダプターを操作しますか?</span><span class="sxs-lookup"><span data-stu-id="84140-147">What Is the InterAct Adapter?</span></span>](../../adapters-and-accelerators/fileact-interact/what-is-the-interact-adapter.md)