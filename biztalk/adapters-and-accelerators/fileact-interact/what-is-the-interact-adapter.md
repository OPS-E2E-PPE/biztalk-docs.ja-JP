---
title: アダプターを操作しますか? | Microsoft Docs
ms.custom: ''
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: ''
ms.suite: ''
ms.tgt_pltfrm: ''
ms.topic: article
ms.assetid: a09063df-c6c4-41b9-96a1-e5059777fa72
caps.latest.revision: 7
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: 25877b95a440faef802d3d2ba7861687d7e4b108
ms.sourcegitcommit: cb908c540d8f1a692d01dc8f313e16cb4b4e696d
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 09/20/2017
ms.locfileid: "22224754"
---
# <a name="what-is-the-interact-adapter"></a><span data-ttu-id="8d3e9-103">アダプターを操作しますか?</span><span class="sxs-lookup"><span data-stu-id="8d3e9-103">What Is the InterAct Adapter?</span></span>
<span data-ttu-id="8d3e9-104">対話 SWIFTNet のアダプタでは、メッセージの転送を BizTalk Server と SWIFT セキュリティで保護された IP ネットワーク (SIPN) 間の接続を提供します。</span><span class="sxs-lookup"><span data-stu-id="8d3e9-104">The InterAct Adapter for SWIFTNet provides connectivity between BizTalk Server and the SWIFT Secure IP Network (SIPN) for the transfer of messages.</span></span> <span data-ttu-id="8d3e9-105">SIPN は、金融機関、金融業界インフラストラクチャ、および顧客の相互接続をセキュリティで保護されたプライベート ネットワーク経由でメッセージとファイルを転送します。</span><span class="sxs-lookup"><span data-stu-id="8d3e9-105">The SIPN transfers messages and files over a secure private network which interconnects financial institutions, financial industry infrastructures, and customers.</span></span> <span data-ttu-id="8d3e9-106">InterAct アダプターは、SWIFTNet リンク (SNL) アプリケーション プログラミング インターフェイス (API) s、SIPN への接続に使用します。</span><span class="sxs-lookup"><span data-stu-id="8d3e9-106">The InterAct adapter uses the SWIFTNet Link (SNL) application programming interface (API)s to connect to the SIPN.</span></span>  
  
 <span data-ttu-id="8d3e9-107">SWIFTNet 対話安全性と信頼性の高いメッセージ交換の各構造化された財務を提供します。</span><span class="sxs-lookup"><span data-stu-id="8d3e9-107">SWIFTNet InterAct provides secure and reliable exchange of individual structured financial messages.</span></span> <span data-ttu-id="8d3e9-108">SWIFT の顧客のメッセージングの要件は、お客様がメッセージも異なります。</span><span class="sxs-lookup"><span data-stu-id="8d3e9-108">SWIFT customers’ messaging requirements vary from customer to customer but also from message to message.</span></span>  
  
 <span data-ttu-id="8d3e9-109">次の機能がサポートされています。</span><span class="sxs-lookup"><span data-stu-id="8d3e9-109">It supports the following functionality:</span></span>  
  
-   <span data-ttu-id="8d3e9-110">PKI のセキュリティ</span><span class="sxs-lookup"><span data-stu-id="8d3e9-110">PKI security</span></span>  
  
-   <span data-ttu-id="8d3e9-111">メッセージの検証</span><span class="sxs-lookup"><span data-stu-id="8d3e9-111">Message validation</span></span>  
  
-   <span data-ttu-id="8d3e9-112">構成可能なサーバーの全体のルーティング</span><span class="sxs-lookup"><span data-stu-id="8d3e9-112">Configurable central routing</span></span>  
  
-   <span data-ttu-id="8d3e9-113">メッセージの優先順位</span><span class="sxs-lookup"><span data-stu-id="8d3e9-113">Message priority</span></span>  
  
-   <span data-ttu-id="8d3e9-114">ストアおよび転送メッセージの配信通知</span><span class="sxs-lookup"><span data-stu-id="8d3e9-114">Delivery notification for store and forward messages</span></span>  
  
-   <span data-ttu-id="8d3e9-115">否認不可の出力と受信確認のです。</span><span class="sxs-lookup"><span data-stu-id="8d3e9-115">Non-repudiation of emission and receipt.</span></span>  
  
 <span data-ttu-id="8d3e9-116">アダプターを使用する対話 SWIFTNet の外部から提供されるアプリケーションとの対話機能を活用します。</span><span class="sxs-lookup"><span data-stu-id="8d3e9-116">You use the InterAct Adapter for SWIFTNet with externally supplied applications to utilize the features of InterAct.</span></span> <span data-ttu-id="8d3e9-117">このアダプターには、転送、および監査したりしません exchange プリミティブを除き、メッセージの内容を確認するメッセージの内容に関する情報がありません。</span><span class="sxs-lookup"><span data-stu-id="8d3e9-117">This adapter has no knowledge of the contents of the messages to be transferred, and will not audit nor validate the contents of the messages, except for the exchange primitives.</span></span>  
  
## <a name="interact-message-exchange"></a><span data-ttu-id="8d3e9-118">InterAct メッセージ交換</span><span class="sxs-lookup"><span data-stu-id="8d3e9-118">InterAct Message Exchange</span></span>  
 <span data-ttu-id="8d3e9-119">SWIFTNet 対話安全性と信頼性の高いメッセージ交換の各構造化された財務を提供します。</span><span class="sxs-lookup"><span data-stu-id="8d3e9-119">SWIFTNet InterAct provides secure and reliable exchange of individual structured financial messages.</span></span> <span data-ttu-id="8d3e9-120">SWIFT の顧客のメッセージングの要件は、お客様がメッセージも異なります。</span><span class="sxs-lookup"><span data-stu-id="8d3e9-120">SWIFT customers’ messaging requirements vary from customer to customer but also from message to message.</span></span> <span data-ttu-id="8d3e9-121">SWIFTNet 対話は、多様な通信モードがあります。</span><span class="sxs-lookup"><span data-stu-id="8d3e9-121">SWIFTNet InterAct offers you a broad range of telecommunication modes:</span></span>  
  
-   <span data-ttu-id="8d3e9-122">**ストア アンド フォワードのメッセージング**</span><span class="sxs-lookup"><span data-stu-id="8d3e9-122">**Store-and-forward messaging.**</span></span> <span data-ttu-id="8d3e9-123">ストア アンド フォワードの SWIFTNet 対話の機能は、多数のユーザーの多くできない可能性がありますオンライン転送時に、見宛てのメッセージに適しています。</span><span class="sxs-lookup"><span data-stu-id="8d3e9-123">SWIFTNet InterAct’s store-and-forward capability is designed for messages destined for a large number of correspondents, many of whom may not be online at the time of transmission.</span></span> <span data-ttu-id="8d3e9-124">不確実性とするかどうか、ユーザーはオンライン時のメッセージを送信する心配不便さを削除します。</span><span class="sxs-lookup"><span data-stu-id="8d3e9-124">It removes the uncertainty and inconvenience of worrying about whether or not your correspondents are on-line at the time you send the message.</span></span> <span data-ttu-id="8d3e9-125">メッセージは受信者がメッセージを受信する準備がすぐに配信されます。</span><span class="sxs-lookup"><span data-stu-id="8d3e9-125">The message is delivered as soon as the recipient is ready to receive it.</span></span> <span data-ttu-id="8d3e9-126">その結果、多数のうち一部異なるタイム ゾーンでは、相手に個々 の命令、確認、およびレポートを送信するための望ましい方法を提供します。</span><span class="sxs-lookup"><span data-stu-id="8d3e9-126">As a result, it provides an ideal way to send individual instructions, confirmations and reports to large numbers of correspondents, some of which may be in different time zones.</span></span>  
  
-   <span data-ttu-id="8d3e9-127">**リアルタイムのメッセージングです。**</span><span class="sxs-lookup"><span data-stu-id="8d3e9-127">**Real-time messaging.**</span></span> <span data-ttu-id="8d3e9-128">リアルタイムのメッセージング、格納および転送時にオンラインになっている見宛てのメッセージの転送に低コストの代替手段が用意されています。</span><span class="sxs-lookup"><span data-stu-id="8d3e9-128">Real-time messaging offers a low-cost alternative to store and forward for messages which are destined for correspondents that are online at the time of transmission.</span></span> <span data-ttu-id="8d3e9-129">その結果、いくつかの大きな見または市場のインフラストラクチャへのメッセージの個別の命令、確認、およびレポートを送信するために最適です。</span><span class="sxs-lookup"><span data-stu-id="8d3e9-129">As a result, it is ideal for sending individual instructions, confirmations and reports, to a few large correspondents or for messages to market infrastructures.</span></span>  
  
 <span data-ttu-id="8d3e9-130">(メッセージのメッセージごと) に省略可能な SWIFTNet 対話機能は次のとおりです。</span><span class="sxs-lookup"><span data-stu-id="8d3e9-130">The optional SWIFTNet InterAct features (on a message by message basis) include:</span></span>  
  
-   <span data-ttu-id="8d3e9-131">**メッセージの優先度。**</span><span class="sxs-lookup"><span data-stu-id="8d3e9-131">**Message priority.**</span></span> <span data-ttu-id="8d3e9-132">メッセージは、メッセージで、適切な相手の処理を許可する「緊急」としてフラグを設定することができます。</span><span class="sxs-lookup"><span data-stu-id="8d3e9-132">Messages can be flagged as “Urgent” in the message, to allow for appropriate processing by your correspondents.</span></span>  
  
-   <span data-ttu-id="8d3e9-133">**配信通知 (ストア アンド フォワード モード)。**</span><span class="sxs-lookup"><span data-stu-id="8d3e9-133">**Delivery notification (store-and-forward mode).**</span></span> <span data-ttu-id="8d3e9-134">相手がメッセージを受信することの確認は、します。</span><span class="sxs-lookup"><span data-stu-id="8d3e9-134">Provides confirmation that your correspondent received your message</span></span>  
  
-   <span data-ttu-id="8d3e9-135">**否認不可の出力と受信します。**</span><span class="sxs-lookup"><span data-stu-id="8d3e9-135">**Non-repudiation of emission and reception.**</span></span> <span data-ttu-id="8d3e9-136">に関して問題が発生した場合、メッセージ交換が行われるように要求を確認する SWIFT を使用できます。</span><span class="sxs-lookup"><span data-stu-id="8d3e9-136">In case of dispute, allows SWIFT to confirm that the message exchange did take place as claimed.</span></span>  
  
 <span data-ttu-id="8d3e9-137">標準の SWIFTNet 対話機能には、SWIFTNet PKI のセキュリティが含まれます。</span><span class="sxs-lookup"><span data-stu-id="8d3e9-137">The standard SWIFTNet InterAct features include SWIFTNet PKI security.</span></span> <span data-ttu-id="8d3e9-138">SWIFTNet FileAct は SWIFTNet PKI を使用して保護し、メッセージの認証と整合性の制御を提供します。</span><span class="sxs-lookup"><span data-stu-id="8d3e9-138">SWIFTNet FileAct is secured with SWIFTNet PKI and offers message authentication and integrity control.</span></span>  
  
 <span data-ttu-id="8d3e9-139">すべてのメッセージと SWIFTNet で交換されるファイルには、一般的な一連のあるユーザーをバイパスできませんセキュリティ、検証、およびプラットフォームのルーティング規則を確認するチェックが行われます。</span><span class="sxs-lookup"><span data-stu-id="8d3e9-139">All messages and files exchanged on SWIFTNet undergo a common set of checks to ensure that no user can bypass the security, validation and routing rules of the platform.</span></span> <span data-ttu-id="8d3e9-140">これらのチェックは、SWIFTAlliance ゲートウェイ (SAG) アプリケーションによって実行されます。</span><span class="sxs-lookup"><span data-stu-id="8d3e9-140">These checks are performed by the SWIFTAlliance Gateway (SAG) application.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="8d3e9-141">参照</span><span class="sxs-lookup"><span data-stu-id="8d3e9-141">See Also</span></span>  
 <span data-ttu-id="8d3e9-142">[入門、FileAct および InterAct アダプター](../../adapters-and-accelerators/fileact-interact/getting-started-with-the-fileact-and-interact-adapters.md) </span><span class="sxs-lookup"><span data-stu-id="8d3e9-142">[Getting Started with the FileAct and InterAct Adapters](../../adapters-and-accelerators/fileact-interact/getting-started-with-the-fileact-and-interact-adapters.md) </span></span>  
 <span data-ttu-id="8d3e9-143">[SWIFTNet とは何ですか。](../../adapters-and-accelerators/fileact-interact/what-is-swiftnet.md) </span><span class="sxs-lookup"><span data-stu-id="8d3e9-143">[What Is SWIFTNet?](../../adapters-and-accelerators/fileact-interact/what-is-swiftnet.md) </span></span>  
 [<span data-ttu-id="8d3e9-144">FileAct アダプターとは何ですか。</span><span class="sxs-lookup"><span data-stu-id="8d3e9-144">What Is the FileAct Adapter?</span></span>](../../adapters-and-accelerators/fileact-interact/what-is-the-fileact-adapter.md)