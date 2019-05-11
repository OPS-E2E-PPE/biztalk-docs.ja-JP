---
title: HL7 バージョン |Microsoft Docs
ms.custom: ''
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: ''
ms.suite: ''
ms.tgt_pltfrm: ''
ms.topic: article
helpviewer_keywords:
- HL7, standards
- HL7, versions
ms.assetid: 47299c6f-55c3-4434-8170-5ad73fe9a84c
caps.latest.revision: 5
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: 9bc04fb6656a3e01c876afd94b76643bf39be3d5
ms.sourcegitcommit: 381e83d43796a345488d54b3f7413e11d56ad7be
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 05/07/2019
ms.locfileid: "65292953"
---
# <a name="hl7-versions"></a><span data-ttu-id="a31b8-102">HL7 のバージョン</span><span class="sxs-lookup"><span data-stu-id="a31b8-102">HL7 Versions</span></span>
<span data-ttu-id="a31b8-103">HL7 バージョン 2 は、1 つの標準ではなく、密接に関連する標準のファミリです。</span><span class="sxs-lookup"><span data-stu-id="a31b8-103">HL7 Version 2 is a family of closely related standards rather than a single standard.</span></span> <span data-ttu-id="a31b8-104">HL7 の組織が、これらの標準 HL7 のバージョン間の互換性規則の適用を上方に対応するように設計されています。</span><span class="sxs-lookup"><span data-stu-id="a31b8-104">The HL7 organization has designed these standards to be upwards compatible through the application of the HL7 inter-version compatibility rules.</span></span> <span data-ttu-id="a31b8-105">これらの規則は、バージョン 2 の範囲内で HL7 のバージョンの規則の下で定義されたインターフェイスはまだ機能の後継バージョンの定義内でを保証します。</span><span class="sxs-lookup"><span data-stu-id="a31b8-105">These rules guarantee that, within the confines of Version 2, an interface defined under the rules of an HL7 version will still function within the definition of successor versions.</span></span> <span data-ttu-id="a31b8-106">受信側のシステムはその実装と、送信を損なうことがなく、以降のバージョンからのメッセージを受信できるように、システムは引き続き以降のバージョンをサポートしている受信者にメッセージを送信することになります。</span><span class="sxs-lookup"><span data-stu-id="a31b8-106">So that a receiving system will be able to accept messages from later versions without breaking its implementation and a sending system will be able to continue to send messages to receivers who support later versions.</span></span>  
  
 <span data-ttu-id="a31b8-107">これは注意して、Microsoft BizTalk Accelerator 用 HL7 ([!INCLUDE[btaBTAHL71.3abbrevnonumber](../../includes/btabtahl71-3abbrevnonumber-md.md)])。</span><span class="sxs-lookup"><span data-stu-id="a31b8-107">It is important to note that Microsoft BizTalk Accelerator for HL7 ([!INCLUDE[btaBTAHL71.3abbrevnonumber](../../includes/btabtahl71-3abbrevnonumber-md.md)]):</span></span>  
  
- <span data-ttu-id="a31b8-108">バージョン 2.5 をバージョン 2.1 からすべてのライブ HL7 バージョンをサポートしています</span><span class="sxs-lookup"><span data-stu-id="a31b8-108">Supports all live HL7 versions from Version 2.1 through Version 2.5</span></span>  
  
- <span data-ttu-id="a31b8-109">HL7 のバージョン間でマップするために必要な機能を提供し、1 つのサイトに複数のバージョンの相互運用が可能</span><span class="sxs-lookup"><span data-stu-id="a31b8-109">Provides the functionality needed to map between HL7 versions, and enables the interoperability of multiple versions at a single site</span></span>  
  
- <span data-ttu-id="a31b8-110">Z セグメントをサポートすることによりローカライズをサポートしている代替の解釈の間のマッピングを有効または標準のメッセージの使用</span><span class="sxs-lookup"><span data-stu-id="a31b8-110">Supports localization by supporting Z segments, and enables mapping between alternate interpretations or uses of the standard messages</span></span>  
  
  <span data-ttu-id="a31b8-111">メッセージングの標準のバージョンの違いに注意する必要があります。</span><span class="sxs-lookup"><span data-stu-id="a31b8-111">It is important to note the difference between the versions of the messaging standard:</span></span>  
  
- <span data-ttu-id="a31b8-112">バージョン 1 は、概念実証としても機能していません。</span><span class="sxs-lookup"><span data-stu-id="a31b8-112">Version 1 functioned as a proof of concept</span></span>  
  
- <span data-ttu-id="a31b8-113">バージョン 2 は、アプリケーション間のメッセージ交換をサポートするためにメッセージの仕様のコレクションを提供します。</span><span class="sxs-lookup"><span data-stu-id="a31b8-113">Version 2 provides a collection of message specifications to support message exchange between applications</span></span>  
  
- <span data-ttu-id="a31b8-114">バージョン 3 は、モデル ベースの統合された一連のさまざまな相互運用性のニーズをサポートする仕様</span><span class="sxs-lookup"><span data-stu-id="a31b8-114">Version 3 will provide a model-based integrated set of specifications to support a range of interoperability needs</span></span>  
  
  <span data-ttu-id="a31b8-115">基本的には、バージョン 2 は、バージョン 3 は、一貫性ととして実行されるメッセージの仕様の本文の長期的な拡張性を確保することに重点を置いています中に指定されたタスクを実行するために必要な仕様をユーザーに提供する実用的な手法で焦点を当てます、。整数。</span><span class="sxs-lookup"><span data-stu-id="a31b8-115">In essence, Version 2 focuses on a pragmatic approach to providing users with the specifications they need to carry out specified tasks, while Version 3 focuses on assuring consistency and long-term extensibility for the body of message specifications taken as a whole.</span></span>  
  
  <span data-ttu-id="a31b8-116">臨床のドキュメント アーキテクチャでは、XML を使用して医療のドキュメントの表現の標準を導入することで、HL7 標準に大幅な拡張機能を提供します。</span><span class="sxs-lookup"><span data-stu-id="a31b8-116">The Clinical Document Architecture provides a significant extension to the HL7 standard by introducing standards for the representation of clinical documents using XML.</span></span>  
  
  <span data-ttu-id="a31b8-117">次の表では、HL7 標準的な開発の進行状況を示します。</span><span class="sxs-lookup"><span data-stu-id="a31b8-117">The following table shows the HL7 standard development progression.</span></span>  
  
|<span data-ttu-id="a31b8-118">イベント</span><span class="sxs-lookup"><span data-stu-id="a31b8-118">Event</span></span>|<span data-ttu-id="a31b8-119">年</span><span class="sxs-lookup"><span data-stu-id="a31b8-119">Year</span></span>|<span data-ttu-id="a31b8-120">詳細</span><span class="sxs-lookup"><span data-stu-id="a31b8-120">Details</span></span>|  
|-----------|----------|-------------|  
|<span data-ttu-id="a31b8-121">HL7 設立</span><span class="sxs-lookup"><span data-stu-id="a31b8-121">HL7 Founded</span></span>|<span data-ttu-id="a31b8-122">1987</span><span class="sxs-lookup"><span data-stu-id="a31b8-122">1987</span></span>|<span data-ttu-id="a31b8-123">最初のミーティング スタンフォード、CA では、12 の参加者を含まれています。</span><span class="sxs-lookup"><span data-stu-id="a31b8-123">The first meeting, in Stanford, CA, included 12 attendees.</span></span>|  
|<span data-ttu-id="a31b8-124">V1.0</span><span class="sxs-lookup"><span data-stu-id="a31b8-124">V1.0</span></span>|<span data-ttu-id="a31b8-125">1987</span><span class="sxs-lookup"><span data-stu-id="a31b8-125">1987</span></span>|<span data-ttu-id="a31b8-126">下書きが HL7 plenary ミーティングに提示します。</span><span class="sxs-lookup"><span data-stu-id="a31b8-126">Draft presented to HL7 plenary meeting.</span></span>|  
|<span data-ttu-id="a31b8-127">V2.0</span><span class="sxs-lookup"><span data-stu-id="a31b8-127">V2.0</span></span>|<span data-ttu-id="a31b8-128">1988</span><span class="sxs-lookup"><span data-stu-id="a31b8-128">1988</span></span>|<span data-ttu-id="a31b8-129">下書きが HL7 plenary ミーティングに提示します。</span><span class="sxs-lookup"><span data-stu-id="a31b8-129">Draft presented to HL7 plenary meeting.</span></span>|  
|<span data-ttu-id="a31b8-130">発行バージョン 2.1 以降</span><span class="sxs-lookup"><span data-stu-id="a31b8-130">V2.1 published</span></span>|<span data-ttu-id="a31b8-131">1990</span><span class="sxs-lookup"><span data-stu-id="a31b8-131">1990</span></span>|<span data-ttu-id="a31b8-132">最初のバージョンを広く実装します。</span><span class="sxs-lookup"><span data-stu-id="a31b8-132">The first widely implemented version</span></span>|  
|<span data-ttu-id="a31b8-133">発行バージョン 2.2</span><span class="sxs-lookup"><span data-stu-id="a31b8-133">V2.2 published</span></span>|<span data-ttu-id="a31b8-134">1994</span><span class="sxs-lookup"><span data-stu-id="a31b8-134">1994</span></span>||  
|<span data-ttu-id="a31b8-135">V.2.3 の発行</span><span class="sxs-lookup"><span data-stu-id="a31b8-135">V.2.3 published</span></span>|<span data-ttu-id="a31b8-136">1997</span><span class="sxs-lookup"><span data-stu-id="a31b8-136">1997</span></span>|<span data-ttu-id="a31b8-137">ANSI の承認</span><span class="sxs-lookup"><span data-stu-id="a31b8-137">ANSI approved</span></span>|  
|<span data-ttu-id="a31b8-138">V2.3.1 の発行</span><span class="sxs-lookup"><span data-stu-id="a31b8-138">V2.3.1 published</span></span>|<span data-ttu-id="a31b8-139">1999</span><span class="sxs-lookup"><span data-stu-id="a31b8-139">1999</span></span>|<span data-ttu-id="a31b8-140">ANSI の承認</span><span class="sxs-lookup"><span data-stu-id="a31b8-140">ANSI approved</span></span>|  
|<span data-ttu-id="a31b8-141">V2.4 の発行</span><span class="sxs-lookup"><span data-stu-id="a31b8-141">V2.4 published</span></span>|<span data-ttu-id="a31b8-142">2000</span><span class="sxs-lookup"><span data-stu-id="a31b8-142">2000</span></span>|<span data-ttu-id="a31b8-143">ANSI の承認</span><span class="sxs-lookup"><span data-stu-id="a31b8-143">ANSI approved</span></span>|  
|<span data-ttu-id="a31b8-144">電子カルテ アーキテクチャ</span><span class="sxs-lookup"><span data-stu-id="a31b8-144">Clinical Document Architecture</span></span>|<span data-ttu-id="a31b8-145">2000</span><span class="sxs-lookup"><span data-stu-id="a31b8-145">2000</span></span>|<span data-ttu-id="a31b8-146">ANSI の承認</span><span class="sxs-lookup"><span data-stu-id="a31b8-146">ANSI approved</span></span>|  
|<span data-ttu-id="a31b8-147">発行 V2.5</span><span class="sxs-lookup"><span data-stu-id="a31b8-147">V2.5 published</span></span>|<span data-ttu-id="a31b8-148">2003</span><span class="sxs-lookup"><span data-stu-id="a31b8-148">2003</span></span>|<span data-ttu-id="a31b8-149">承認のために、ANSI に送信された HL7 以内に承認を完了します。</span><span class="sxs-lookup"><span data-stu-id="a31b8-149">Completed approval within HL7, submitted to ANSI for approval.</span></span>|  
|<span data-ttu-id="a31b8-150">進行中の V3.0</span><span class="sxs-lookup"><span data-stu-id="a31b8-150">V3.0 in progress</span></span>|<span data-ttu-id="a31b8-151">2003</span><span class="sxs-lookup"><span data-stu-id="a31b8-151">2003</span></span>||  
  
## <a name="see-also"></a><span data-ttu-id="a31b8-152">参照</span><span class="sxs-lookup"><span data-stu-id="a31b8-152">See Also</span></span>  
 <span data-ttu-id="a31b8-153">[HL7 メッセージの処理](../../adapters-and-accelerators/accelerator-hl7/processing-hl7-messages.md) </span><span class="sxs-lookup"><span data-stu-id="a31b8-153">[Processing HL7 Messages](../../adapters-and-accelerators/accelerator-hl7/processing-hl7-messages.md) </span></span>  
 <span data-ttu-id="a31b8-154">[HL7 2.X スキーマの使用](../../adapters-and-accelerators/accelerator-hl7/using-hl7-2-x-schemas.md) </span><span class="sxs-lookup"><span data-stu-id="a31b8-154">[Using HL7 2.X Schemas](../../adapters-and-accelerators/accelerator-hl7/using-hl7-2-x-schemas.md) </span></span>  
 <span data-ttu-id="a31b8-155">[HL7 2. XML スキーマの使用](../../adapters-and-accelerators/accelerator-hl7/using-hl7-2-xml-schemas.md) </span><span class="sxs-lookup"><span data-stu-id="a31b8-155">[Using HL7 2.XML Schemas](../../adapters-and-accelerators/accelerator-hl7/using-hl7-2-xml-schemas.md) </span></span>  
 <span data-ttu-id="a31b8-156">[メッセージ モード](../../adapters-and-accelerators/accelerator-hl7/message-modes.md) </span><span class="sxs-lookup"><span data-stu-id="a31b8-156">[Message Modes](../../adapters-and-accelerators/accelerator-hl7/message-modes.md) </span></span>  
 [<span data-ttu-id="a31b8-157">HL7 メッセージング</span><span class="sxs-lookup"><span data-stu-id="a31b8-157">HL7 Messaging</span></span>](../../adapters-and-accelerators/accelerator-hl7/hl7-messaging.md)