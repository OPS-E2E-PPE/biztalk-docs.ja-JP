---
title: FileAct アダプターとは何ですか。 | Microsoft Docs
ms.custom: ''
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: ''
ms.suite: ''
ms.tgt_pltfrm: ''
ms.topic: article
ms.assetid: 05ec8f1e-57f9-4e2d-ab8b-22b5c4b28055
caps.latest.revision: 9
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: dc6fe9b28e4ea2b5eee087b61866827a766c3e3f
ms.sourcegitcommit: 266308ec5c6a9d8d80ff298ee6051b4843c5d626
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 06/27/2018
ms.locfileid: "36971491"
---
# <a name="what-is-the-fileact-adapter"></a><span data-ttu-id="98dc1-103">FileAct アダプターとは何ですか。</span><span class="sxs-lookup"><span data-stu-id="98dc1-103">What Is the FileAct Adapter?</span></span>
<span data-ttu-id="98dc1-104">SWIFTNet 用に FileAct アダプターは、ファイルの転送で、世界銀行間金融電気通信 (SWIFT) Secure IP Network (SIPN) を BizTalk Server と、Society 間の接続を提供します。</span><span class="sxs-lookup"><span data-stu-id="98dc1-104">The FileAct adapter for SWIFTNet provides connectivity between BizTalk Server and the Society for Worldwide Interbank Financial Telecommunication (SWIFT) Secure IP Network (SIPN) for the transfer of files.</span></span> <span data-ttu-id="98dc1-105">SIPN は、金融機関、金融業界インフラストラクチャ、顧客との接続をセキュリティで保護されたプライベート ネットワーク経由でメッセージやファイルを転送します。</span><span class="sxs-lookup"><span data-stu-id="98dc1-105">The SIPN transfers messages and files over a secure private network which connects financial institutions, financial industry infrastructures, and customers.</span></span> <span data-ttu-id="98dc1-106">FileAct アダプターは SWIFTNet リンク (SNL) アプリケーション プログラミング インターフェイス (API) s を SIPN への接続を使用します。</span><span class="sxs-lookup"><span data-stu-id="98dc1-106">The FileAct adapter uses the SWIFTNet Link (SNL) application programming interface (API)s to connect to the SIPN.</span></span>  
  
 <span data-ttu-id="98dc1-107">FileAct アダプターでは、安全に SWIFT の参加者のメカニズムを備えていて、ファイルとそれらのファイルに関連する情報を確実に交換します。</span><span class="sxs-lookup"><span data-stu-id="98dc1-107">The FileAct adapter provides a mechanism for SWIFT participants to securely and reliably exchange files and information pertaining to those files.</span></span> <span data-ttu-id="98dc1-108">次の機能がサポートされています。</span><span class="sxs-lookup"><span data-stu-id="98dc1-108">It supports the following functionality:</span></span>  
  
-   <span data-ttu-id="98dc1-109">SWIFTNet ユーザーにファイルを送信します。</span><span class="sxs-lookup"><span data-stu-id="98dc1-109">Sending files to a SWIFTNet User</span></span>  
  
-   <span data-ttu-id="98dc1-110">SWIFTNet ユーザーからファイルを取得します。</span><span class="sxs-lookup"><span data-stu-id="98dc1-110">Retrieving files from a SWIFTNet User</span></span>  
  
-   <span data-ttu-id="98dc1-111">配信通知の受信側でのファイルの受信を確認します。</span><span class="sxs-lookup"><span data-stu-id="98dc1-111">Delivery notification confirming file receipt by a receiver</span></span>  
  
-   <span data-ttu-id="98dc1-112">進行中の転送を中止します。</span><span class="sxs-lookup"><span data-stu-id="98dc1-112">Abort of transfers in progress</span></span>  
  
-   <span data-ttu-id="98dc1-113">ファイル転送状態の監視</span><span class="sxs-lookup"><span data-stu-id="98dc1-113">File transfer state monitoring</span></span>  
  
-   <span data-ttu-id="98dc1-114">同時実行のファイル転送</span><span class="sxs-lookup"><span data-stu-id="98dc1-114">Concurrent file transfers</span></span>  
  
-   <span data-ttu-id="98dc1-115">データの信頼性と整合性の保証</span><span class="sxs-lookup"><span data-stu-id="98dc1-115">Assurance of data authenticity and integrity</span></span>  
  
-   <span data-ttu-id="98dc1-116">転送中のファイル データの機密性</span><span class="sxs-lookup"><span data-stu-id="98dc1-116">Confidentiality of file data in transit</span></span>  
  
-   <span data-ttu-id="98dc1-117">ファイル転送の否認不可</span><span class="sxs-lookup"><span data-stu-id="98dc1-117">Non-repudiation of file transfers</span></span>  
  
-   <span data-ttu-id="98dc1-118">タイムスタンプ</span><span class="sxs-lookup"><span data-stu-id="98dc1-118">Time-stamping</span></span>  
  
## <a name="the-fileact-service"></a><span data-ttu-id="98dc1-119">FileAct サービス</span><span class="sxs-lookup"><span data-stu-id="98dc1-119">The FileAct Service</span></span>  
 <span data-ttu-id="98dc1-120">SWIFTNet 用に FileAct アダプターでは、構造化された金融メッセージまたはサイズの大きなレポートのバッチなどのファイルの転送を安全かつ高い信頼性を提供します。</span><span class="sxs-lookup"><span data-stu-id="98dc1-120">The FileAct adapter for SWIFTNet provides secure and reliable transfer of files, such as batches of structured financial messages or large reports.</span></span> <span data-ttu-id="98dc1-121">一般的なアプリケーションには、反復的なクレジット転送年金または給与支払、証券の付加価値のある情報とレポート、および規制レポートなどが含まれます。</span><span class="sxs-lookup"><span data-stu-id="98dc1-121">Typical applications include repetitive credit transfers such as pension or salary payments, securities value-added information and reporting, and regulatory reporting.</span></span> <span data-ttu-id="98dc1-122">SWIFTNet FileAct には、さまざまなメッセージングのモードが提供しています。</span><span class="sxs-lookup"><span data-stu-id="98dc1-122">SWIFTNet FileAct offers a variety of messaging modes:</span></span>  
  
- <span data-ttu-id="98dc1-123">**ストア アンド フォワード ファイル転送します。**</span><span class="sxs-lookup"><span data-stu-id="98dc1-123">**Store-and-forward file transfer.**</span></span> <span data-ttu-id="98dc1-124">不確実性とかどうか、本物でオンラインになって、ファイルを送信する時間について心配することの不便の SWIFTNet FileAct ストア アンド フォワードの機能を削除します。</span><span class="sxs-lookup"><span data-stu-id="98dc1-124">SWIFTNet FileAct’s store-and-forward capability removes the uncertainty and inconvenience of worrying about whether or not your correspondents are online at the time you transmit the file.</span></span> <span data-ttu-id="98dc1-125">ファイルは、受信者がメッセージを受信する準備がすぐに配信されます。</span><span class="sxs-lookup"><span data-stu-id="98dc1-125">The file is delivered as soon as the recipient is ready to receive it.</span></span> <span data-ttu-id="98dc1-126">その結果、多数の異なるタイム ゾーンのうちいくつかあります本物のファイルを送信するための望ましい方法を提供します。</span><span class="sxs-lookup"><span data-stu-id="98dc1-126">As a result, it provides an ideal way to send files to large numbers of correspondents, some of which may be in different time zones.</span></span>  
  
- <span data-ttu-id="98dc1-127">**リアルタイムのファイル転送。**</span><span class="sxs-lookup"><span data-stu-id="98dc1-127">**Real-time file transfer.**</span></span> <span data-ttu-id="98dc1-128">リアルタイム メッセージングは、格納および転送時にオンラインになっている本物を宛先とするファイルを転送する低コストの選択肢を提供します。</span><span class="sxs-lookup"><span data-stu-id="98dc1-128">Real-time messaging offers a lower-cost alternative to store and forward for files that are destined for correspondents that are online at the time of transmission.</span></span> <span data-ttu-id="98dc1-129">その結果、いくつかの大きな本物またはインフラストラクチャの市場にファイルを送信するために最適です。</span><span class="sxs-lookup"><span data-stu-id="98dc1-129">As a result it is ideal for sending files to a few large correspondents or market infrastructures.</span></span>  
  
- <span data-ttu-id="98dc1-130">**リアルタイムのファイルを取得します。**</span><span class="sxs-lookup"><span data-stu-id="98dc1-130">**Real-time file retrieval.**</span></span> <span data-ttu-id="98dc1-131">これは、通常のワークステーション ベースのシステム コンテキストで、多くの場合、SWIFTNet 参照と組み合わせてのファイルを取得するために使用する対話型のサービスです。</span><span class="sxs-lookup"><span data-stu-id="98dc1-131">This is an interactive service typically used to retrieve files in the context of workstation-based systems and often in conjunction with SWIFTNet Browse.</span></span> <span data-ttu-id="98dc1-132">このモードがサポートします。</span><span class="sxs-lookup"><span data-stu-id="98dc1-132">We will support this mode.</span></span>  
  
  <span data-ttu-id="98dc1-133">(ファイル単位) では、オプションの SWIFTNet FileAct 機能は次のとおりです。</span><span class="sxs-lookup"><span data-stu-id="98dc1-133">The optional SWIFTNet FileAct features (on a file by file basis) include:</span></span>  
  
- <span data-ttu-id="98dc1-134">**メッセージの優先度。**</span><span class="sxs-lookup"><span data-stu-id="98dc1-134">**Message priority.**</span></span> <span data-ttu-id="98dc1-135">ファイル転送は、処理、本物を適切なために、メッセージで「緊急」としてフラグことができます。</span><span class="sxs-lookup"><span data-stu-id="98dc1-135">File transfers can be flagged as “Urgent” in the message, to allow for appropriate processing by your correspondents.</span></span>  
  
- <span data-ttu-id="98dc1-136">**配信通知 (リアルタイムおよびストア アンド フォワード モード)。**</span><span class="sxs-lookup"><span data-stu-id="98dc1-136">**Delivery notification (real-time and store-and-forward modes).**</span></span> <span data-ttu-id="98dc1-137">相手が、ファイルを受信することの確認を提供します。</span><span class="sxs-lookup"><span data-stu-id="98dc1-137">Provides confirmation that your correspondent received your file.</span></span>  
  
- <span data-ttu-id="98dc1-138">**出力と受信の非否認します。**</span><span class="sxs-lookup"><span data-stu-id="98dc1-138">**Non-repudiation of emission and reception.**</span></span> <span data-ttu-id="98dc1-139">に関して問題が発生した場合は、ファイル転送が行われるように要求を確認する SWIFT を使用できます。</span><span class="sxs-lookup"><span data-stu-id="98dc1-139">In case of dispute, allows SWIFT to confirm that the file transfer did take place as claimed.</span></span>  
  
  <span data-ttu-id="98dc1-140">SWIFTNet FileAct の標準機能には、SWIFTNet PKI のセキュリティが含まれます。<strong>します。</strong></span><span class="sxs-lookup"><span data-stu-id="98dc1-140">The standard SWIFTNet FileAct features include SWIFTNet PKI security<strong>.</strong></span></span> <span data-ttu-id="98dc1-141">SWIFTNet FileAct は SWIFTNet PKI を使用して保護し、メッセージの認証と整合性の制御を提供します。</span><span class="sxs-lookup"><span data-stu-id="98dc1-141">SWIFTNet FileAct is secured with SWIFTNet PKI and offers message authentication and integrity control.</span></span>  
  
  <span data-ttu-id="98dc1-142">すべてのメッセージと SWIFTNet で交換されるファイルは、ユーザーをバイパスできませんセキュリティ、検証、およびプラットフォームのルーティング規則のことを確認する一連の一般的に行われます。</span><span class="sxs-lookup"><span data-stu-id="98dc1-142">All messages and files exchanged on SWIFTNet undergo a common set of checks to ensure that no user can bypass the security, validation and routing rules of the platform.</span></span> <span data-ttu-id="98dc1-143">これらのチェックは、SWIFTAlliance ゲートウェイ (SAG) アプリケーションによって実行されます。</span><span class="sxs-lookup"><span data-stu-id="98dc1-143">These checks are performed by the SWIFTAlliance Gateway (SAG) application.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="98dc1-144">参照</span><span class="sxs-lookup"><span data-stu-id="98dc1-144">See Also</span></span>  
 <span data-ttu-id="98dc1-145">[概要 FileAct および InterAct アダプター](../../adapters-and-accelerators/fileact-interact/getting-started-with-the-fileact-and-interact-adapters.md) </span><span class="sxs-lookup"><span data-stu-id="98dc1-145">[Getting Started with the FileAct and InterAct Adapters](../../adapters-and-accelerators/fileact-interact/getting-started-with-the-fileact-and-interact-adapters.md) </span></span>  
 <span data-ttu-id="98dc1-146">[SWIFTNet とは何ですか。](../../adapters-and-accelerators/fileact-interact/what-is-swiftnet.md) </span><span class="sxs-lookup"><span data-stu-id="98dc1-146">[What Is SWIFTNet?](../../adapters-and-accelerators/fileact-interact/what-is-swiftnet.md) </span></span>  
 [<span data-ttu-id="98dc1-147">InterAct アダプターとは</span><span class="sxs-lookup"><span data-stu-id="98dc1-147">What Is the InterAct Adapter?</span></span>](../../adapters-and-accelerators/fileact-interact/what-is-the-interact-adapter.md)