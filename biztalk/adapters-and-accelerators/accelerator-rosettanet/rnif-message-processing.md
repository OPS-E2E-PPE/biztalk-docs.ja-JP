---
title: "RNIF メッセージの処理 |Microsoft ドキュメント"
ms.custom: 
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: 
ms.suite: 
ms.tgt_pltfrm: 
ms.topic: article
helpviewer_keywords:
- RosettaNet Implementation Framework (RNIF)
- RosettaNet, about RosettaNet
- RNIF
- RNIF, non-repudiation
- RNIF, BizTalk Accelerator for RosettaNet
- non-repudiation
- RNIF, about RNIF
- BizTalk Accelerator for RosettaNet, RNIF
- RosettaNet
ms.assetid: 994f15bc-765c-4220-8ab1-176919e9e821
caps.latest.revision: "5"
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: 34ff8794c6dcc94571607207b4c13e9dd2bf54cc
ms.sourcegitcommit: cb908c540d8f1a692d01dc8f313e16cb4b4e696d
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 09/20/2017
---
# <a name="rnif-message-processing"></a><span data-ttu-id="7ead9-102">RNIF メッセージの処理</span><span class="sxs-lookup"><span data-stu-id="7ead9-102">RNIF Message Processing</span></span>
<span data-ttu-id="7ead9-103">RosettaNet 組織は、RNIF (RosettaNet Implementation Framework) 仕様でメッセージ交換を定義しています。</span><span class="sxs-lookup"><span data-stu-id="7ead9-103">The RosettaNet organization defines message exchange in the RosettaNet Implementation Framework (RNIF) specifications.</span></span> <span data-ttu-id="7ead9-104">RNIF は、統合システムがメッセージを転送する方法を定義します。</span><span class="sxs-lookup"><span data-stu-id="7ead9-104">RNIF defines how integration systems will transport messages.</span></span> [!INCLUDE[btaBTARN3.3abbrevnonumber](../../includes/btabtarn3-3abbrevnonumber-md.md)]<span data-ttu-id="7ead9-105">完全に新機能に追加する機能、RNIF 仕様を実装する[!INCLUDE[btsCoName](../../includes/btsconame-md.md)][!INCLUDE[BTARN_CurrentVersion_FirstRef](../../includes/btarn-currentversion-firstref-md.md)]ネイティブ ボックスを提供します。</span><span class="sxs-lookup"><span data-stu-id="7ead9-105"> fully implements the RNIF specifications, adding that functionality to what [!INCLUDE[btsCoName](../../includes/btsconame-md.md)][!INCLUDE[BTARN_CurrentVersion_FirstRef](../../includes/btarn-currentversion-firstref-md.md)] natively provides out-of-the-box.</span></span>  
  
 <span data-ttu-id="7ead9-106">RNIF 通信は複雑です。</span><span class="sxs-lookup"><span data-stu-id="7ead9-106">RNIF communications are complex.</span></span> <span data-ttu-id="7ead9-107">RNIF 処理を実行するパブリック プロセスには、さまざまな検証チェックと複雑なワークフロー ロジックが含まれます。</span><span class="sxs-lookup"><span data-stu-id="7ead9-107">The public processes that perform RNIF processing include a variety of validation checks and complex workflow logic.</span></span> [!INCLUDE[btaBTARN3.3abbrevnonumber](../../includes/btabtarn3-3abbrevnonumber-md.md)]<span data-ttu-id="7ead9-108">この機能をネイティブに提供します。</span><span class="sxs-lookup"><span data-stu-id="7ead9-108"> provides this functionality natively.</span></span> <span data-ttu-id="7ead9-109">そのため、RNIF ロジックを最初から開発したり保守することなく、RosettaNet 準拠システムを使用できます。</span><span class="sxs-lookup"><span data-stu-id="7ead9-109">This lets you use a RosettaNet-compliant system without developing or maintaining RNIF logic from scratch.</span></span>  
  
## <a name="btarn-support-for-rnif"></a><span data-ttu-id="7ead9-110">BTARN の RNIF のサポート</span><span class="sxs-lookup"><span data-stu-id="7ead9-110">BTARN Support for RNIF</span></span>  
 [!INCLUDE[btaBTARN3.3abbrevnonumber](../../includes/btabtarn3-3abbrevnonumber-md.md)]<span data-ttu-id="7ead9-111"> では、RNIF の両方のバージョン、RNIF 1.1 と RNIF 2.0 (V02.00.01) をサポートしています。</span><span class="sxs-lookup"><span data-stu-id="7ead9-111"> supports both versions of RNIF: RNIF 1.1 and RNIF 2.0 (V02.00.01).</span></span> <span data-ttu-id="7ead9-112">RNIF 2.0 には、RNIF 1.1 でサポートされる機能に加え、暗号化、添付ファイル、および同期トランザクションを含む重要な機能が追加されています。</span><span class="sxs-lookup"><span data-stu-id="7ead9-112">RNIF 2.0 added significant functionality beyond that supported by RNIF 1.1, including encryption, attachments, and synchronous transactions.</span></span> <span data-ttu-id="7ead9-113">RNIF 2.0 には RNIF 1.1 との下位互換性はありません。</span><span class="sxs-lookup"><span data-stu-id="7ead9-113">RNIF 2.0 is not backward compatible with RNIF 1.1.</span></span>  
  
> [!NOTE]
>  [!INCLUDE[btaBTARN3.3abbrevnonumber](../../includes/btabtarn3-3abbrevnonumber-md.md)]<span data-ttu-id="7ead9-114"> は、RosettaNet Ready RNIF 2.0 に準拠しています。</span><span class="sxs-lookup"><span data-stu-id="7ead9-114"> is RosettaNet Ready RNIF 2.0 compliant.</span></span>  
  
 <span data-ttu-id="7ead9-115">この 2 つのバージョンでは RosettaNet メッセージの定義方法が異なります。</span><span class="sxs-lookup"><span data-stu-id="7ead9-115">The two versions define the RosettaNet message differently.</span></span> <span data-ttu-id="7ead9-116">異なるメッセージ コンテナの詳細については、次を参照してください。 [RNIF 規格](../../adapters-and-accelerators/accelerator-rosettanet/rnif-standard.md)です。</span><span class="sxs-lookup"><span data-stu-id="7ead9-116">For more information about the different message containers, see [RNIF Standard](../../adapters-and-accelerators/accelerator-rosettanet/rnif-standard.md).</span></span>  
  
 <span data-ttu-id="7ead9-117">統合システムは、HTTP/HTTPS および SMTP; 経由で RNIF 転送を実行します。ただし、 [!INCLUDE[btaBTARN3.3abbrevnonumber](../../includes/btabtarn3-3abbrevnonumber-md.md)] HTTP、HTTPS のみを実装します。</span><span class="sxs-lookup"><span data-stu-id="7ead9-117">Integration systems perform RNIF transfer over HTTP/HTTPS and SMTP; however, [!INCLUDE[btaBTARN3.3abbrevnonumber](../../includes/btabtarn3-3abbrevnonumber-md.md)] implements only HTTP/HTTPS.</span></span> [!INCLUDE[btaBTARN3.3abbrevnonumber](../../includes/btabtarn3-3abbrevnonumber-md.md)]<span data-ttu-id="7ead9-118">RNIF 1.1 での添付ファイルと同期トランザクションができませんでした。</span><span class="sxs-lookup"><span data-stu-id="7ead9-118"> does not support attachments and synchronous transactions in RNIF 1.1.</span></span>  
  
### <a name="non-repudiation"></a><span data-ttu-id="7ead9-119">否認不可</span><span class="sxs-lookup"><span data-stu-id="7ead9-119">Non-Repudiation</span></span>  
 <span data-ttu-id="7ead9-120">RNIF 規格には、否認不可の要件が盛り込まれています。</span><span class="sxs-lookup"><span data-stu-id="7ead9-120">The RNIF standard includes a requirement for non-repudiation.</span></span> <span data-ttu-id="7ead9-121">[!INCLUDE[btaBTARN3.3abbrevnonumber](../../includes/btabtarn3-3abbrevnonumber-md.md)] によって送受信されるワイヤ形式のメッセージを送受信したことを法的に証明できるように、このメッセージを否認不可データベースに格納します。</span><span class="sxs-lookup"><span data-stu-id="7ead9-121">This involves storing the wire format of any message received or sent by [!INCLUDE[btaBTARN3.3abbrevnonumber](../../includes/btabtarn3-3abbrevnonumber-md.md)] in a non-repudiation database, so that you can prove legally that you have received or sent it.</span></span> <span data-ttu-id="7ead9-122">このため、[!INCLUDE[btaBTARN3.3abbrevnonumber](../../includes/btabtarn3-3abbrevnonumber-md.md)] では、着信メッセージ用に [!INCLUDE[btaBTARN3.3abbrevnonumber](../../includes/btabtarn3-3abbrevnonumber-md.md)]Archive データベースの MessageStorageIn テーブルが、送信メッセージ用に同データベースの MessageStorageOut テーブルが使用されます。</span><span class="sxs-lookup"><span data-stu-id="7ead9-122">For this purpose, [!INCLUDE[btaBTARN3.3abbrevnonumber](../../includes/btabtarn3-3abbrevnonumber-md.md)] uses the MessageStorageIn table in the [!INCLUDE[btaBTARN3.3abbrevnonumber](../../includes/btabtarn3-3abbrevnonumber-md.md)]Archive database for incoming messages and the MessageStorageOut table in the same database for outgoing messages.</span></span>  
  
 <span data-ttu-id="7ead9-123">プロセス構成プロファイルで、Service Content と受信確認に対して個別に否認不可要件を設定します。</span><span class="sxs-lookup"><span data-stu-id="7ead9-123">You set non-repudiation requirements for service content and for acknowledgements separately in the process configuration profile.</span></span> <span data-ttu-id="7ead9-124">一方または両方を設定した場合、**発信元とコンテンツの否認**と**否認不可のために必要な**オプション`True`、し[!INCLUDE[btaBTARN3.3abbrevnonumber](../../includes/btabtarn3-3abbrevnonumber-md.md)]次のデータを格納します。</span><span class="sxs-lookup"><span data-stu-id="7ead9-124">If you set one or both of the **Non-Repudiation of Origin and Content** and **Non-Repudiation Required** options to `True`, then [!INCLUDE[btaBTARN3.3abbrevnonumber](../../includes/btabtarn3-3abbrevnonumber-md.md)] will store the following data:</span></span>  
  
|<span data-ttu-id="7ead9-125">data</span><span class="sxs-lookup"><span data-stu-id="7ead9-125">Data</span></span>|<span data-ttu-id="7ead9-126">目次</span><span class="sxs-lookup"><span data-stu-id="7ead9-126">Contents</span></span>|  
|----------|--------------|  
|<span data-ttu-id="7ead9-127">RecordID</span><span class="sxs-lookup"><span data-stu-id="7ead9-127">RecordID</span></span>|<span data-ttu-id="7ead9-128">格納されたメッセージ専用の一意の ID</span><span class="sxs-lookup"><span data-stu-id="7ead9-128">Proprietary unique ID of the stored message</span></span>|  
|<span data-ttu-id="7ead9-129">MessageCategory</span><span class="sxs-lookup"><span data-stu-id="7ead9-129">MessageCategory</span></span>|<span data-ttu-id="7ead9-130">要求 (0)、応答 (1)、またはシグナル (2)</span><span class="sxs-lookup"><span data-stu-id="7ead9-130">Request (0), Response (1), or Signal (2)</span></span>|  
|<span data-ttu-id="7ead9-131">DestinationParty</span><span class="sxs-lookup"><span data-stu-id="7ead9-131">DestinationParty</span></span>|<span data-ttu-id="7ead9-132">送信先パーティの名前</span><span class="sxs-lookup"><span data-stu-id="7ead9-132">Name of the destination party</span></span>|  
|<span data-ttu-id="7ead9-133">SourceParty</span><span class="sxs-lookup"><span data-stu-id="7ead9-133">SourceParty</span></span>|<span data-ttu-id="7ead9-134">送信元パーティの名前</span><span class="sxs-lookup"><span data-stu-id="7ead9-134">Name of the source party</span></span>|  
|<span data-ttu-id="7ead9-135">PIPCode</span><span class="sxs-lookup"><span data-stu-id="7ead9-135">PIPCode</span></span>|<span data-ttu-id="7ead9-136">PIP3A4 など</span><span class="sxs-lookup"><span data-stu-id="7ead9-136">For example, PIP3A4</span></span>|  
|<span data-ttu-id="7ead9-137">PIPVersion</span><span class="sxs-lookup"><span data-stu-id="7ead9-137">PIPVersion</span></span>|<span data-ttu-id="7ead9-138">V02.00 など</span><span class="sxs-lookup"><span data-stu-id="7ead9-138">For example, V02.00</span></span>|  
|<span data-ttu-id="7ead9-139">MessageContent</span><span class="sxs-lookup"><span data-stu-id="7ead9-139">MessageContent</span></span>|<span data-ttu-id="7ead9-140">バイナリ形式のメッセージ</span><span class="sxs-lookup"><span data-stu-id="7ead9-140">Message in binary format</span></span>|  
|<span data-ttu-id="7ead9-141">MessageTrackingID</span><span class="sxs-lookup"><span data-stu-id="7ead9-141">MessageTrackingID</span></span>|<span data-ttu-id="7ead9-142">メッセージのメッセージ追跡 ID</span><span class="sxs-lookup"><span data-stu-id="7ead9-142">Message tracking ID of the message</span></span>|  
|<span data-ttu-id="7ead9-143">PIPInstanceID</span><span class="sxs-lookup"><span data-stu-id="7ead9-143">PIPInstanceID</span></span>|<span data-ttu-id="7ead9-144">プロセスの PIP インスタンス ID</span><span class="sxs-lookup"><span data-stu-id="7ead9-144">PIP instance ID of the process</span></span>|  
  
## <a name="see-also"></a><span data-ttu-id="7ead9-145">参照</span><span class="sxs-lookup"><span data-stu-id="7ead9-145">See Also</span></span>  
 <span data-ttu-id="7ead9-146">[BizTalk Server に BizTalk Accelerator for RosettaNet の追加](../../adapters-and-accelerators/accelerator-rosettanet/what-biztalk-accelerator-for-rosettanet-adds-to-biztalk-server.md) </span><span class="sxs-lookup"><span data-stu-id="7ead9-146">[What BizTalk Accelerator for RosettaNet Adds to BizTalk Server](../../adapters-and-accelerators/accelerator-rosettanet/what-biztalk-accelerator-for-rosettanet-adds-to-biztalk-server.md) </span></span>  
 [<span data-ttu-id="7ead9-147">PIP の実装</span><span class="sxs-lookup"><span data-stu-id="7ead9-147">PIP Implementation</span></span>](../../adapters-and-accelerators/accelerator-rosettanet/pip-implementation.md)