---
title: CIDX メッセージ規格 |Microsoft Docs
ms.custom: ''
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: ''
ms.suite: ''
ms.tgt_pltfrm: ''
ms.topic: article
helpviewer_keywords:
- CIDX, RosettaNet
- RosettaNet, CIDX
ms.assetid: 6f70fa56-1fc3-4016-ac9e-6af18026292a
caps.latest.revision: 3
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: a39b76ef67374796d9ba569a50e7d5357dac819d
ms.sourcegitcommit: 381e83d43796a345488d54b3f7413e11d56ad7be
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 05/07/2019
ms.locfileid: "65284861"
---
# <a name="cidx-messaging-standards"></a><span data-ttu-id="4a408-102">CIDX メッセージ規格</span><span class="sxs-lookup"><span data-stu-id="4a408-102">CIDX Messaging Standards</span></span>
<span data-ttu-id="4a408-103">CIDX (Chemical Industry Data Exchange) は、サポートおよび標準化されたメッセージ交換の Chem eStandards を維持する標準化機構として動作します。</span><span class="sxs-lookup"><span data-stu-id="4a408-103">CIDX (Chemical Industry Data Exchange) operates as a standards organization that supports and maintains the Chem eStandards for standardized message exchange.</span></span> <span data-ttu-id="4a408-104">企業、化学工業分野では、業界固有のメッセージング ニーズにこれらの標準を使用します。</span><span class="sxs-lookup"><span data-stu-id="4a408-104">Companies in the chemical industry use these standards for their industry-specific messaging needs.</span></span>  
  
 <span data-ttu-id="4a408-105">CIDX は、Framework RNIF (RosettaNet Implementation) メッセージング層で XML ドキュメントの交換を有効にするを採用しています。</span><span class="sxs-lookup"><span data-stu-id="4a408-105">CIDX has adopted the RosettaNet Implementation Framework (RNIF) at the messaging layer to enable the exchange of XML documents.</span></span> <span data-ttu-id="4a408-106">CIDX は、RNIF 規格のパブリック プロセス層を採用していません。</span><span class="sxs-lookup"><span data-stu-id="4a408-106">CIDX has not adopted the public-process layer of the RNIF standards.</span></span>  
  
 <span data-ttu-id="4a408-107">Chem eStandards では、システムが交換するメッセージの service content を記述する XML ドキュメント型定義 (Dtd) を定義します。</span><span class="sxs-lookup"><span data-stu-id="4a408-107">Chem eStandards define XML document type definitions (DTDs) that describe the service content of a message that systems exchange.</span></span> <span data-ttu-id="4a408-108">メッセージでは、service content と一部のヘッダー値に違い構造で、RNIF 1.1 RosettaNet オブジェクトと同じです。</span><span class="sxs-lookup"><span data-stu-id="4a408-108">The message is the same as an RNIF 1.1 RosettaNet object in structure, with differences in the service content and some header values.</span></span> <span data-ttu-id="4a408-109">CIDX 規格と RosettaNet メッセージの間の一致がある場合は、RosettaNet の要素名とデータ構造体、CIDX 規格が採用されます。</span><span class="sxs-lookup"><span data-stu-id="4a408-109">When there is a match between CIDX standards and RosettaNet messages, the CIDX standard adopts RosettaNet element names and data structures.</span></span>  
  
 <span data-ttu-id="4a408-110">CIDX が、メッセージ交換の場合は、電子ドキュメント交換 (EDI) を使用していましたが形式の XML テクノロジに基づいたドキュメントの新しいセット。</span><span class="sxs-lookup"><span data-stu-id="4a408-110">CIDX has traditionally used electronic document interchange (EDI) for message exchange, but has formed a new set of documents based on XML technologies.</span></span> <span data-ttu-id="4a408-111">Chem eStandards では、EDI メッセージの XML レプリカを提供します。</span><span class="sxs-lookup"><span data-stu-id="4a408-111">Chem eStandards provide XML replicas of EDI messages.</span></span>  
  
 <span data-ttu-id="4a408-112">Chem eStandards では、各取引に対して個別のメッセージを作成します。</span><span class="sxs-lookup"><span data-stu-id="4a408-112">Chem eStandards create individual messages for every business transaction.</span></span> <span data-ttu-id="4a408-113">Chem eStandards を使用して、2 つの種類のメッセージ応答: テクニカル応答とトランザクション応答します。</span><span class="sxs-lookup"><span data-stu-id="4a408-113">Chem eStandards use two types of message responses: technical responses and transaction responses.</span></span> <span data-ttu-id="4a408-114">安全で信頼性の高いメッセージング、Chem eStandards は RNIF 1.1 の通知タイプ プロセスのみを使用します。</span><span class="sxs-lookup"><span data-stu-id="4a408-114">For secure and reliable messaging, Chem eStandards only use Notification type processes of RNIF 1.1.</span></span> <span data-ttu-id="4a408-115">Chem eStandards では、プロセス PIP (Partner Interface) 0A1 は使用しないでください。</span><span class="sxs-lookup"><span data-stu-id="4a408-115">Chem eStandards do not use Partner Interface Process (PIP) 0A1.</span></span>  
  
## <a name="cidx-and-rosettanet-differences"></a><span data-ttu-id="4a408-116">CIDX と RosettaNet の違い</span><span class="sxs-lookup"><span data-stu-id="4a408-116">CIDX and RosettaNet Differences</span></span>  
 <span data-ttu-id="4a408-117">次の表では、RosettaNet と CIDX の違いの一部を示します。</span><span class="sxs-lookup"><span data-stu-id="4a408-117">The following table shows some of the differences between RosettaNet and CIDX.</span></span>  
  
|<span data-ttu-id="4a408-118">RosettaNet の実装</span><span class="sxs-lookup"><span data-stu-id="4a408-118">RosettaNet implementation</span></span>|<span data-ttu-id="4a408-119">CIDX の実装</span><span class="sxs-lookup"><span data-stu-id="4a408-119">CIDX implementation</span></span>|  
|-------------------------------|-------------------------|  
|<span data-ttu-id="4a408-120">RosettaNet は、Multipurpose Internet Mail Extensions (MIME) の種類として、"Application/x RosettaNet"を使用します。</span><span class="sxs-lookup"><span data-stu-id="4a408-120">RosettaNet uses the "Application/x-RosettaNet" as the Multipurpose Internet Mail Extensions (MIME) type.</span></span>|<span data-ttu-id="4a408-121">CIDX は、MIME の種類として"アプリケーション/x-ChemXML"を使用します。</span><span class="sxs-lookup"><span data-stu-id="4a408-121">CIDX uses "Application/x-ChemXML" as the MIME type.</span></span>|  
|<span data-ttu-id="4a408-122">RosettaNet ヘッダー、RosettaNet 使用 GlobalAdministeringAuthorityCode = RosettaNet</span><span class="sxs-lookup"><span data-stu-id="4a408-122">For RosettaNet headers, RosettaNet uses GlobalAdministeringAuthorityCode = RosettaNet</span></span>|<span data-ttu-id="4a408-123">CIDX は GlobalAdministeringAuthorityCode = CIDX</span><span class="sxs-lookup"><span data-stu-id="4a408-123">CIDX uses GlobalAdministeringAuthorityCode = CIDX</span></span>|  
|<span data-ttu-id="4a408-124">RosettaNet では、シングル アクションとダブル アクション メッセージをサポートします。</span><span class="sxs-lookup"><span data-stu-id="4a408-124">RosettaNet supports single-action and double-action messages.</span></span>|<span data-ttu-id="4a408-125">CIDX では、シングル アクション メッセージのみをサポートします。</span><span class="sxs-lookup"><span data-stu-id="4a408-125">CIDX supports only single-action messages.</span></span>|  
|<span data-ttu-id="4a408-126">RosettaNet PIP 0A1 をサポートしています (エラー通知)。</span><span class="sxs-lookup"><span data-stu-id="4a408-126">RosettaNet supports PIP 0A1 (Notification of Failure).</span></span>|<span data-ttu-id="4a408-127">CIDX は、PIP 0A1 をサポートしていません。</span><span class="sxs-lookup"><span data-stu-id="4a408-127">CIDX does not support PIP 0A1.</span></span>|  
|<span data-ttu-id="4a408-128">RosettaNet メッセージのトランザクションまたは通知のできる型。</span><span class="sxs-lookup"><span data-stu-id="4a408-128">RosettaNet messages can be of Transaction or Notification type.</span></span>|<span data-ttu-id="4a408-129">CIDX のすべてのメッセージでは、通知の種類です。</span><span class="sxs-lookup"><span data-stu-id="4a408-129">All CIDX messages are of the Notification type.</span></span>|  
|<span data-ttu-id="4a408-130">RosettaNet では、PIP 仕様から PIP 構成設定を派生する必要があります。</span><span class="sxs-lookup"><span data-stu-id="4a408-130">In RosettaNet, you must derive PIP Configuration Settings from the PIP specifications.</span></span>|<span data-ttu-id="4a408-131">CIDX では、CIDX Chem eStandards 仕様から PIP 構成設定を派生する必要があります。</span><span class="sxs-lookup"><span data-stu-id="4a408-131">In CIDX, you must derive PIP Configuration Settings from the CIDX Chem eStandards specifications.</span></span>|  
  
## <a name="see-also"></a><span data-ttu-id="4a408-132">参照</span><span class="sxs-lookup"><span data-stu-id="4a408-132">See Also</span></span>  
 <span data-ttu-id="4a408-133">[RosettaNet および CIDX メッセージ規格](../../adapters-and-accelerators/accelerator-rosettanet/rosettanet-and-cidx-messaging-standards.md) </span><span class="sxs-lookup"><span data-stu-id="4a408-133">[RosettaNet and CIDX Messaging Standards](../../adapters-and-accelerators/accelerator-rosettanet/rosettanet-and-cidx-messaging-standards.md) </span></span>  
 <span data-ttu-id="4a408-134">[RNIF 規格](../../adapters-and-accelerators/accelerator-rosettanet/rnif-standard.md) </span><span class="sxs-lookup"><span data-stu-id="4a408-134">[RNIF Standard](../../adapters-and-accelerators/accelerator-rosettanet/rnif-standard.md) </span></span>  
 <span data-ttu-id="4a408-135">[RosettaNet Pip](../../adapters-and-accelerators/accelerator-rosettanet/rosettanet-pips.md) </span><span class="sxs-lookup"><span data-stu-id="4a408-135">[RosettaNet PIPs](../../adapters-and-accelerators/accelerator-rosettanet/rosettanet-pips.md) </span></span>  
 [<span data-ttu-id="4a408-136">CIDX サポート</span><span class="sxs-lookup"><span data-stu-id="4a408-136">CIDX Support</span></span>](../../adapters-and-accelerators/accelerator-rosettanet/cidx-support.md)