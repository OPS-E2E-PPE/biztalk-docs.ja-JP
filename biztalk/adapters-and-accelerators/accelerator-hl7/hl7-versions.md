---
title: HL7 バージョン |Microsoft ドキュメント
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
ms.openlocfilehash: 9c7edcfa6c44467c0660efd8a9b4b02df7010de6
ms.sourcegitcommit: cb908c540d8f1a692d01dc8f313e16cb4b4e696d
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 09/20/2017
ms.locfileid: "22204826"
---
# <a name="hl7-versions"></a><span data-ttu-id="5da2b-102">HL7 のバージョン</span><span class="sxs-lookup"><span data-stu-id="5da2b-102">HL7 Versions</span></span>
<span data-ttu-id="5da2b-103">HL7 バージョン 2 は、1 つの標準ではなく、密接に関連する標準のファミリです。</span><span class="sxs-lookup"><span data-stu-id="5da2b-103">HL7 Version 2 is a family of closely related standards rather than a single standard.</span></span> <span data-ttu-id="5da2b-104">HL7 組織には、これらの標準 HL7 間のバージョンの互換性規則のアプリケーションを介して下方互換性があること、設計しました。</span><span class="sxs-lookup"><span data-stu-id="5da2b-104">The HL7 organization has designed these standards to be upwards compatible through the application of the HL7 inter-version compatibility rules.</span></span> <span data-ttu-id="5da2b-105">これらの規則はの境界内にバージョン 2、HL7 のバージョンの規則の下で定義されたインターフェイスがまだ機能する後続のバージョンの定義内を保証します。</span><span class="sxs-lookup"><span data-stu-id="5da2b-105">These rules guarantee that, within the confines of Version 2, an interface defined under the rules of an HL7 version will still function within the definition of successor versions.</span></span> <span data-ttu-id="5da2b-106">受信側システムでは、実装と、送信を分断することがなく以降のバージョンからのメッセージを受信できるように、システムはできなければ以降のバージョンをサポートしている受信者にメッセージを送信し続けます。</span><span class="sxs-lookup"><span data-stu-id="5da2b-106">So that a receiving system will be able to accept messages from later versions without breaking its implementation and a sending system will be able to continue to send messages to receivers who support later versions.</span></span>  
  
 <span data-ttu-id="5da2b-107">重要な点は[!INCLUDE[btsCoName](../../includes/btsconame-md.md)]BizTalk Accelerator 用 HL7 ([!INCLUDE[btaBTAHL71.3abbrevnonumber](../../includes/btabtahl71-3abbrevnonumber-md.md)])。</span><span class="sxs-lookup"><span data-stu-id="5da2b-107">It is important to note that [!INCLUDE[btsCoName](../../includes/btsconame-md.md)] BizTalk Accelerator for HL7 ([!INCLUDE[btaBTAHL71.3abbrevnonumber](../../includes/btabtahl71-3abbrevnonumber-md.md)]):</span></span>  
  
-   <span data-ttu-id="5da2b-108">バージョン 2.5 をバージョン 2.1 からすべてのライブ HL7 バージョンをサポートしています</span><span class="sxs-lookup"><span data-stu-id="5da2b-108">Supports all live HL7 versions from Version 2.1 through Version 2.5</span></span>  
  
-   <span data-ttu-id="5da2b-109">HL7 バージョン間でマップするために必要な機能を提供し、1 つのサイトに複数のバージョンの相互運用が可能</span><span class="sxs-lookup"><span data-stu-id="5da2b-109">Provides the functionality needed to map between HL7 versions, and enables the interoperability of multiple versions at a single site</span></span>  
  
-   <span data-ttu-id="5da2b-110">Z セグメントをサポートすることでローカライズをサポートしていると、代替の意味との間のマッピングを有効または標準のメッセージの使用</span><span class="sxs-lookup"><span data-stu-id="5da2b-110">Supports localization by supporting Z segments, and enables mapping between alternate interpretations or uses of the standard messages</span></span>  
  
 <span data-ttu-id="5da2b-111">ことが重要メッセージングの標準のバージョンの違いに注意してください。</span><span class="sxs-lookup"><span data-stu-id="5da2b-111">It is important to note the difference between the versions of the messaging standard:</span></span>  
  
-   <span data-ttu-id="5da2b-112">バージョン 1 は、概念実証としても機能していません。</span><span class="sxs-lookup"><span data-stu-id="5da2b-112">Version 1 functioned as a proof of concept</span></span>  
  
-   <span data-ttu-id="5da2b-113">バージョン 2 のアプリケーション間のメッセージ交換をサポートするためにメッセージ仕様のコレクションを提供します。</span><span class="sxs-lookup"><span data-stu-id="5da2b-113">Version 2 provides a collection of message specifications to support message exchange between applications</span></span>  
  
-   <span data-ttu-id="5da2b-114">バージョン 3 はさまざまな相互運用性のニーズをサポートする仕様のモデル ベースの統合セットを提供します。</span><span class="sxs-lookup"><span data-stu-id="5da2b-114">Version 3 will provide a model-based integrated set of specifications to support a range of interoperability needs</span></span>  
  
 <span data-ttu-id="5da2b-115">基本的には、バージョン 2 について重点的に一貫性ととしてのメッセージ仕様の本文の長期的な機能拡張を確保することに重点を置いています Version 3 中に指定したタスクは、実行するために必要な仕様をユーザーに提供する実際的なアプローチを整数。</span><span class="sxs-lookup"><span data-stu-id="5da2b-115">In essence, Version 2 focuses on a pragmatic approach to providing users with the specifications they need to carry out specified tasks, while Version 3 focuses on assuring consistency and long-term extensibility for the body of message specifications taken as a whole.</span></span>  
  
 <span data-ttu-id="5da2b-116">医療のドキュメント アーキテクチャでは、標準 XML を使用して治療のドキュメントの形式を導入することにより、HL7 標準に大幅な拡張機能を提供します。</span><span class="sxs-lookup"><span data-stu-id="5da2b-116">The Clinical Document Architecture provides a significant extension to the HL7 standard by introducing standards for the representation of clinical documents using XML.</span></span>  
  
 <span data-ttu-id="5da2b-117">次の表は、HL7 標準的な開発の流れを示します。</span><span class="sxs-lookup"><span data-stu-id="5da2b-117">The following table shows the HL7 standard development progression.</span></span>  
  
|<span data-ttu-id="5da2b-118">イベント</span><span class="sxs-lookup"><span data-stu-id="5da2b-118">Event</span></span>|<span data-ttu-id="5da2b-119">年</span><span class="sxs-lookup"><span data-stu-id="5da2b-119">Year</span></span>|<span data-ttu-id="5da2b-120">詳細</span><span class="sxs-lookup"><span data-stu-id="5da2b-120">Details</span></span>|  
|-----------|----------|-------------|  
|<span data-ttu-id="5da2b-121">HL7 設立されました</span><span class="sxs-lookup"><span data-stu-id="5da2b-121">HL7 Founded</span></span>|<span data-ttu-id="5da2b-122">1987</span><span class="sxs-lookup"><span data-stu-id="5da2b-122">1987</span></span>|<span data-ttu-id="5da2b-123">最初のミーティング スタンフォード、CA では、12 参加者を含まれています。</span><span class="sxs-lookup"><span data-stu-id="5da2b-123">The first meeting, in Stanford, CA, included 12 attendees.</span></span>|  
|<span data-ttu-id="5da2b-124">V1.0</span><span class="sxs-lookup"><span data-stu-id="5da2b-124">V1.0</span></span>|<span data-ttu-id="5da2b-125">1987</span><span class="sxs-lookup"><span data-stu-id="5da2b-125">1987</span></span>|<span data-ttu-id="5da2b-126">下書き HL7 plenary ミーティングに提示します。</span><span class="sxs-lookup"><span data-stu-id="5da2b-126">Draft presented to HL7 plenary meeting.</span></span>|  
|<span data-ttu-id="5da2b-127">バージョン 2.0</span><span class="sxs-lookup"><span data-stu-id="5da2b-127">V2.0</span></span>|<span data-ttu-id="5da2b-128">1988</span><span class="sxs-lookup"><span data-stu-id="5da2b-128">1988</span></span>|<span data-ttu-id="5da2b-129">下書き HL7 plenary ミーティングに提示します。</span><span class="sxs-lookup"><span data-stu-id="5da2b-129">Draft presented to HL7 plenary meeting.</span></span>|  
|<span data-ttu-id="5da2b-130">公開されたバージョン 2.1 以降</span><span class="sxs-lookup"><span data-stu-id="5da2b-130">V2.1 published</span></span>|<span data-ttu-id="5da2b-131">1990</span><span class="sxs-lookup"><span data-stu-id="5da2b-131">1990</span></span>|<span data-ttu-id="5da2b-132">最初にバージョン広く実装されています。</span><span class="sxs-lookup"><span data-stu-id="5da2b-132">The first widely implemented version</span></span>|  
|<span data-ttu-id="5da2b-133">公開されたバージョン 2.2</span><span class="sxs-lookup"><span data-stu-id="5da2b-133">V2.2 published</span></span>|<span data-ttu-id="5da2b-134">1994</span><span class="sxs-lookup"><span data-stu-id="5da2b-134">1994</span></span>||  
|<span data-ttu-id="5da2b-135">パブリッシュされた V.2.3</span><span class="sxs-lookup"><span data-stu-id="5da2b-135">V.2.3 published</span></span>|<span data-ttu-id="5da2b-136">1997</span><span class="sxs-lookup"><span data-stu-id="5da2b-136">1997</span></span>|<span data-ttu-id="5da2b-137">ANSI の承認</span><span class="sxs-lookup"><span data-stu-id="5da2b-137">ANSI approved</span></span>|  
|<span data-ttu-id="5da2b-138">パブリッシュされた V2.3.1</span><span class="sxs-lookup"><span data-stu-id="5da2b-138">V2.3.1 published</span></span>|<span data-ttu-id="5da2b-139">1999</span><span class="sxs-lookup"><span data-stu-id="5da2b-139">1999</span></span>|<span data-ttu-id="5da2b-140">ANSI の承認</span><span class="sxs-lookup"><span data-stu-id="5da2b-140">ANSI approved</span></span>|  
|<span data-ttu-id="5da2b-141">パブリッシュされた V2.4</span><span class="sxs-lookup"><span data-stu-id="5da2b-141">V2.4 published</span></span>|<span data-ttu-id="5da2b-142">2000</span><span class="sxs-lookup"><span data-stu-id="5da2b-142">2000</span></span>|<span data-ttu-id="5da2b-143">ANSI の承認</span><span class="sxs-lookup"><span data-stu-id="5da2b-143">ANSI approved</span></span>|  
|<span data-ttu-id="5da2b-144">ドキュメントのアーキテクチャ</span><span class="sxs-lookup"><span data-stu-id="5da2b-144">Clinical Document Architecture</span></span>|<span data-ttu-id="5da2b-145">2000</span><span class="sxs-lookup"><span data-stu-id="5da2b-145">2000</span></span>|<span data-ttu-id="5da2b-146">ANSI の承認</span><span class="sxs-lookup"><span data-stu-id="5da2b-146">ANSI approved</span></span>|  
|<span data-ttu-id="5da2b-147">パブリッシュされた V2.5</span><span class="sxs-lookup"><span data-stu-id="5da2b-147">V2.5 published</span></span>|<span data-ttu-id="5da2b-148">2003</span><span class="sxs-lookup"><span data-stu-id="5da2b-148">2003</span></span>|<span data-ttu-id="5da2b-149">HL7、承認のための ANSI に送信内での承認を完了します。</span><span class="sxs-lookup"><span data-stu-id="5da2b-149">Completed approval within HL7, submitted to ANSI for approval.</span></span>|  
|<span data-ttu-id="5da2b-150">進行中の V3.0</span><span class="sxs-lookup"><span data-stu-id="5da2b-150">V3.0 in progress</span></span>|<span data-ttu-id="5da2b-151">2003</span><span class="sxs-lookup"><span data-stu-id="5da2b-151">2003</span></span>||  
  
## <a name="see-also"></a><span data-ttu-id="5da2b-152">参照</span><span class="sxs-lookup"><span data-stu-id="5da2b-152">See Also</span></span>  
 <span data-ttu-id="5da2b-153">[HL7 メッセージの処理](../../adapters-and-accelerators/accelerator-hl7/processing-hl7-messages.md) </span><span class="sxs-lookup"><span data-stu-id="5da2b-153">[Processing HL7 Messages](../../adapters-and-accelerators/accelerator-hl7/processing-hl7-messages.md) </span></span>  
 <span data-ttu-id="5da2b-154">[HL7 2.X スキーマの使用](../../adapters-and-accelerators/accelerator-hl7/using-hl7-2-x-schemas.md) </span><span class="sxs-lookup"><span data-stu-id="5da2b-154">[Using HL7 2.X Schemas](../../adapters-and-accelerators/accelerator-hl7/using-hl7-2-x-schemas.md) </span></span>  
 <span data-ttu-id="5da2b-155">[HL7 2. XML スキーマを使用します。](../../adapters-and-accelerators/accelerator-hl7/using-hl7-2-xml-schemas.md) </span><span class="sxs-lookup"><span data-stu-id="5da2b-155">[Using HL7 2.XML Schemas](../../adapters-and-accelerators/accelerator-hl7/using-hl7-2-xml-schemas.md) </span></span>  
 <span data-ttu-id="5da2b-156">[メッセージ モード](../../adapters-and-accelerators/accelerator-hl7/message-modes.md) </span><span class="sxs-lookup"><span data-stu-id="5da2b-156">[Message Modes](../../adapters-and-accelerators/accelerator-hl7/message-modes.md) </span></span>  
 [<span data-ttu-id="5da2b-157">HL7 メッセージ</span><span class="sxs-lookup"><span data-stu-id="5da2b-157">HL7 Messaging</span></span>](../../adapters-and-accelerators/accelerator-hl7/hl7-messaging.md)