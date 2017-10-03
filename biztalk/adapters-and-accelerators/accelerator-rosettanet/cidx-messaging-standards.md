---
title: "CIDX メッセージ規格 |Microsoft ドキュメント"
ms.custom: 
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: 
ms.suite: 
ms.tgt_pltfrm: 
ms.topic: article
helpviewer_keywords:
- CIDX, RosettaNet
- RosettaNet, CIDX
ms.assetid: 6f70fa56-1fc3-4016-ac9e-6af18026292a
caps.latest.revision: "3"
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: 4d37cd02f92a8a13857071d0b3d84ab40c480787
ms.sourcegitcommit: cb908c540d8f1a692d01dc8f313e16cb4b4e696d
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 09/20/2017
---
# <a name="cidx-messaging-standards"></a><span data-ttu-id="982ad-102">CIDX メッセージ規格</span><span class="sxs-lookup"><span data-stu-id="982ad-102">CIDX Messaging Standards</span></span>
<span data-ttu-id="982ad-103">CIDX (Chemical Industry Data Exchange) は、標準化されたメッセージ交換の Chem eStandards をサポートおよび維持する標準化機構です。</span><span class="sxs-lookup"><span data-stu-id="982ad-103">CIDX (Chemical Industry Data Exchange) operates as a standards organization that supports and maintains the Chem eStandards for standardized message exchange.</span></span> <span data-ttu-id="982ad-104">化学工業分野の企業では、この規格を利用して、業界特有のメッセージングのニーズに対応します。</span><span class="sxs-lookup"><span data-stu-id="982ad-104">Companies in the chemical industry use these standards for their industry-specific messaging needs.</span></span>  
  
 <span data-ttu-id="982ad-105">CIDX では、XML ドキュメントの交換を可能にするために、メッセージ層に RNIF (RosettaNet Implementation Framework) を採用しています。</span><span class="sxs-lookup"><span data-stu-id="982ad-105">CIDX has adopted the RosettaNet Implementation Framework (RNIF) at the messaging layer to enable the exchange of XML documents.</span></span> <span data-ttu-id="982ad-106">CIDX では、RNIF 規格のパブリック プロセス層は採用していません。</span><span class="sxs-lookup"><span data-stu-id="982ad-106">CIDX has not adopted the public-process layer of the RNIF standards.</span></span>  
  
 <span data-ttu-id="982ad-107">Chem eStandards は、システムが交換するメッセージの Service Content を記述する XML 文書型定義 (DTD) を定義します。</span><span class="sxs-lookup"><span data-stu-id="982ad-107">Chem eStandards define XML document type definitions (DTDs) that describe the service content of a message that systems exchange.</span></span> <span data-ttu-id="982ad-108">メッセージの構造は RNIF 1.1 RosettaNet オブジェクトと同じですが、Service Content と一部のヘッダー値が異なります。</span><span class="sxs-lookup"><span data-stu-id="982ad-108">The message is the same as an RNIF 1.1 RosettaNet object in structure, with differences in the service content and some header values.</span></span> <span data-ttu-id="982ad-109">CIDX 規格と RosettaNet メッセージに一致がある場合、CIDX 規格では RosettaNet の要素名とデータ構造を採用します。</span><span class="sxs-lookup"><span data-stu-id="982ad-109">When there is a match between CIDX standards and RosettaNet messages, the CIDX standard adopts RosettaNet element names and data structures.</span></span>  
  
 <span data-ttu-id="982ad-110">CIDX では、これまでメッセージ交換に EDI (Electronic Document Interchange) を使用していましたが、XML テクノロジに基づいた新しいドキュメント セットを作成しました。</span><span class="sxs-lookup"><span data-stu-id="982ad-110">CIDX has traditionally used electronic document interchange (EDI) for message exchange, but has formed a new set of documents based on XML technologies.</span></span> <span data-ttu-id="982ad-111">Chem eStandards により、EDI メッセージの XML レプリカが作成されます。</span><span class="sxs-lookup"><span data-stu-id="982ad-111">Chem eStandards provide XML replicas of EDI messages.</span></span>  
  
 <span data-ttu-id="982ad-112">Chem eStandards により、各取り引きに対して個別のメッセージが作成されます。</span><span class="sxs-lookup"><span data-stu-id="982ad-112">Chem eStandards create individual messages for every business transaction.</span></span> <span data-ttu-id="982ad-113">Chem eStandards では、テクニカル応答とトランザクション応答の 2 種類のメッセージ応答を使用します。</span><span class="sxs-lookup"><span data-stu-id="982ad-113">Chem eStandards use two types of message responses: technical responses and transaction responses.</span></span> <span data-ttu-id="982ad-114">安全で信頼できるメッセージ処理のために、Chem eStandards では RNIF 1.1 の通知タイプ プロセスのみを使用します。</span><span class="sxs-lookup"><span data-stu-id="982ad-114">For secure and reliable messaging, Chem eStandards only use Notification type processes of RNIF 1.1.</span></span> <span data-ttu-id="982ad-115">PIP (Partner Interface Process) 0A1 は使用しません。</span><span class="sxs-lookup"><span data-stu-id="982ad-115">Chem eStandards do not use Partner Interface Process (PIP) 0A1.</span></span>  
  
## <a name="cidx-and-rosettanet-differences"></a><span data-ttu-id="982ad-116">CIDX と RosettaNet の違い</span><span class="sxs-lookup"><span data-stu-id="982ad-116">CIDX and RosettaNet Differences</span></span>  
 <span data-ttu-id="982ad-117">次の表に、RosettaNet と CIDX の違いの一部を示します。</span><span class="sxs-lookup"><span data-stu-id="982ad-117">The following table shows some of the differences between RosettaNet and CIDX.</span></span>  
  
|<span data-ttu-id="982ad-118">RosettaNet の実装</span><span class="sxs-lookup"><span data-stu-id="982ad-118">RosettaNet implementation</span></span>|<span data-ttu-id="982ad-119">CIDX の実装</span><span class="sxs-lookup"><span data-stu-id="982ad-119">CIDX implementation</span></span>|  
|-------------------------------|-------------------------|  
|<span data-ttu-id="982ad-120">RosettaNet は、MIME (Multipurpose Internet Mail Extensions) の種類として "Application/x-RosettaNet" を使用します。</span><span class="sxs-lookup"><span data-stu-id="982ad-120">RosettaNet uses the "Application/x-RosettaNet" as the Multipurpose Internet Mail Extensions (MIME) type.</span></span>|<span data-ttu-id="982ad-121">CIDX は、MIME の種類として "Application/x-ChemXML" を使用します。</span><span class="sxs-lookup"><span data-stu-id="982ad-121">CIDX uses "Application/x-ChemXML" as the MIME type.</span></span>|  
|<span data-ttu-id="982ad-122">RosettaNet は、RosettaNet ヘッダーとして GlobalAdministeringAuthorityCode = RosettaNet を使用します。</span><span class="sxs-lookup"><span data-stu-id="982ad-122">For RosettaNet headers, RosettaNet uses GlobalAdministeringAuthorityCode = RosettaNet</span></span>|<span data-ttu-id="982ad-123">CIDX は、GlobalAdministeringAuthorityCode = CIDX を使用します。</span><span class="sxs-lookup"><span data-stu-id="982ad-123">CIDX uses GlobalAdministeringAuthorityCode = CIDX</span></span>|  
|<span data-ttu-id="982ad-124">RosettaNet は、シングル アクションとダブル アクションのメッセージをサポートします。</span><span class="sxs-lookup"><span data-stu-id="982ad-124">RosettaNet supports single-action and double-action messages.</span></span>|<span data-ttu-id="982ad-125">CIDX は、シングル アクションのメッセージのみをサポートします。</span><span class="sxs-lookup"><span data-stu-id="982ad-125">CIDX supports only single-action messages.</span></span>|  
|<span data-ttu-id="982ad-126">RosettaNet は、PIP 0A1 (エラー通知) をサポートします。</span><span class="sxs-lookup"><span data-stu-id="982ad-126">RosettaNet supports PIP 0A1 (Notification of Failure).</span></span>|<span data-ttu-id="982ad-127">CIDX は、PIP 0A1 をサポートしません。</span><span class="sxs-lookup"><span data-stu-id="982ad-127">CIDX does not support PIP 0A1.</span></span>|  
|<span data-ttu-id="982ad-128">RosettaNet メッセージの種類は、Transaction または Notification です。</span><span class="sxs-lookup"><span data-stu-id="982ad-128">RosettaNet messages can be of Transaction or Notification type.</span></span>|<span data-ttu-id="982ad-129">CIDX メッセージの種類はすべて Notification です。</span><span class="sxs-lookup"><span data-stu-id="982ad-129">All CIDX messages are of the Notification type.</span></span>|  
|<span data-ttu-id="982ad-130">RosettaNet では、PIP 仕様に基づいて PIP 構成設定を作成する必要があります。</span><span class="sxs-lookup"><span data-stu-id="982ad-130">In RosettaNet, you must derive PIP Configuration Settings from the PIP specifications.</span></span>|<span data-ttu-id="982ad-131">CIDX では、CIDX Chem eStandards 仕様に基づいて PIP 構成設定を作成する必要があります。</span><span class="sxs-lookup"><span data-stu-id="982ad-131">In CIDX, you must derive PIP Configuration Settings from the CIDX Chem eStandards specifications.</span></span>|  
  
## <a name="see-also"></a><span data-ttu-id="982ad-132">参照</span><span class="sxs-lookup"><span data-stu-id="982ad-132">See Also</span></span>  
 <span data-ttu-id="982ad-133">[RosettaNet および CIDX メッセージ規格](../../adapters-and-accelerators/accelerator-rosettanet/rosettanet-and-cidx-messaging-standards.md) </span><span class="sxs-lookup"><span data-stu-id="982ad-133">[RosettaNet and CIDX Messaging Standards](../../adapters-and-accelerators/accelerator-rosettanet/rosettanet-and-cidx-messaging-standards.md) </span></span>  
 <span data-ttu-id="982ad-134">[RNIF 規格](../../adapters-and-accelerators/accelerator-rosettanet/rnif-standard.md) </span><span class="sxs-lookup"><span data-stu-id="982ad-134">[RNIF Standard](../../adapters-and-accelerators/accelerator-rosettanet/rnif-standard.md) </span></span>  
 <span data-ttu-id="982ad-135">[RosettaNet Pip](../../adapters-and-accelerators/accelerator-rosettanet/rosettanet-pips.md) </span><span class="sxs-lookup"><span data-stu-id="982ad-135">[RosettaNet PIPs](../../adapters-and-accelerators/accelerator-rosettanet/rosettanet-pips.md) </span></span>  
 [<span data-ttu-id="982ad-136">CIDX サポート</span><span class="sxs-lookup"><span data-stu-id="982ad-136">CIDX Support</span></span>](../../adapters-and-accelerators/accelerator-rosettanet/cidx-support.md)