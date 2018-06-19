---
title: ACK メッセージ スキーマの種類 |Microsoft ドキュメント
ms.custom: ''
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: ''
ms.suite: ''
ms.tgt_pltfrm: ''
ms.topic: article
helpviewer_keywords:
- schemas, ACK schemas
- acknowledgements, ACK schema types
- ACK messages
ms.assetid: da6981a0-a70a-481e-8db4-4a6851f205f1
caps.latest.revision: 3
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: 09537a9fda34ee1148e3e4d880f17f35f83f761c
ms.sourcegitcommit: 5abd0ed3f9e4858ffaaec5481bfa8878595e95f7
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 11/28/2017
ms.locfileid: "25960960"
---
# <a name="ack-message-schema-types"></a><span data-ttu-id="bec11-102">ACK メッセージ スキーマの種類</span><span class="sxs-lookup"><span data-stu-id="bec11-102">ACK Message Schema Types</span></span>
<span data-ttu-id="bec11-103">受信確認メッセージのスキーマは 2 つの形式があります。</span><span class="sxs-lookup"><span data-stu-id="bec11-103">Acknowledgment message schemas come in two forms:</span></span>  
  
-   <span data-ttu-id="bec11-104">**一般的な確認 (ACK)** です。</span><span class="sxs-lookup"><span data-stu-id="bec11-104">**General acknowledgment (ACK)**.</span></span> <span data-ttu-id="bec11-105">アプリケーションは、特定の基幹業務アプリケーション レベルの受信確認メッセージを定義していない、またはエラーが発生したアプリケーションの処理が除外は、一般的な確認 (ACK) を使用できます。</span><span class="sxs-lookup"><span data-stu-id="bec11-105">You can use a general acknowledgment (ACK) where the application does not define a special line-of-business application level acknowledgment message or where an error occurred that precludes application processing.</span></span> <span data-ttu-id="bec11-106">これを使用することもできますのレベルの受信確認をそのまま使用します。</span><span class="sxs-lookup"><span data-stu-id="bec11-106">You can also use it for accept level acknowledgments.</span></span> <span data-ttu-id="bec11-107">次の表は、ACK メッセージの構造を示します。</span><span class="sxs-lookup"><span data-stu-id="bec11-107">The following table lists the ACK message structure.</span></span>  
  
    |<span data-ttu-id="bec11-108">ACK ^ 異なります ^ ACK</span><span class="sxs-lookup"><span data-stu-id="bec11-108">ACK^varies^ACK</span></span>|<span data-ttu-id="bec11-109">一般的な受信確認</span><span class="sxs-lookup"><span data-stu-id="bec11-109">General acknowledgment</span></span>|<span data-ttu-id="bec11-110">章</span><span class="sxs-lookup"><span data-stu-id="bec11-110">Chapter</span></span>|  
    |--------------------|----------------------------|-------------|  
    |<span data-ttu-id="bec11-111">MSH</span><span class="sxs-lookup"><span data-stu-id="bec11-111">MSH</span></span>|<span data-ttu-id="bec11-112">メッセージ ヘッダー</span><span class="sxs-lookup"><span data-stu-id="bec11-112">Message Header</span></span>|<span data-ttu-id="bec11-113">2</span><span class="sxs-lookup"><span data-stu-id="bec11-113">2</span></span>|  
    |<span data-ttu-id="bec11-114">MSA</span><span class="sxs-lookup"><span data-stu-id="bec11-114">MSA</span></span>|<span data-ttu-id="bec11-115">メッセージの受信確認</span><span class="sxs-lookup"><span data-stu-id="bec11-115">Message Acknowledgment</span></span>|<span data-ttu-id="bec11-116">2</span><span class="sxs-lookup"><span data-stu-id="bec11-116">2</span></span>|  
    |<span data-ttu-id="bec11-117">[エラー]</span><span class="sxs-lookup"><span data-stu-id="bec11-117">[ ERR ]</span></span>|<span data-ttu-id="bec11-118">[エラー]</span><span class="sxs-lookup"><span data-stu-id="bec11-118">Error</span></span>|<span data-ttu-id="bec11-119">2</span><span class="sxs-lookup"><span data-stu-id="bec11-119">2</span></span>|  
  
-   <span data-ttu-id="bec11-120">**遅延確認応答 (MCF)** です。</span><span class="sxs-lookup"><span data-stu-id="bec11-120">**Delayed acknowledgment (MCF)**.</span></span> <span data-ttu-id="bec11-121">このメッセージは、HL7 バージョン 2.1 で旧バージョンとの互換性のためだけ存在します。</span><span class="sxs-lookup"><span data-stu-id="bec11-121">This message exists only for backward compatibility with HL7 Version 2.1.</span></span> <span data-ttu-id="bec11-122">非同期のアプリケーション レベル受信確認、MCF メッセージの一般的なフォームを作成するプロトコルの一部として使用するとします。</span><span class="sxs-lookup"><span data-stu-id="bec11-122">You use it as part of the protocol that creates a generic form of an asynchronous application level acknowledgment, the MCF message.</span></span> <span data-ttu-id="bec11-123">次の表は、MCF メッセージの構造を示します。</span><span class="sxs-lookup"><span data-stu-id="bec11-123">The following table lists the MCF message structure.</span></span>  
  
    |<span data-ttu-id="bec11-124">MCF ^ 異なります ^ ACK</span><span class="sxs-lookup"><span data-stu-id="bec11-124">MCF^varies^ACK</span></span>|<span data-ttu-id="bec11-125">受信確認の遅延</span><span class="sxs-lookup"><span data-stu-id="bec11-125">Delayed Acknowledgment</span></span>|<span data-ttu-id="bec11-126">章</span><span class="sxs-lookup"><span data-stu-id="bec11-126">Chapter</span></span>|  
    |--------------------|----------------------------|-------------|  
    |<span data-ttu-id="bec11-127">MSH</span><span class="sxs-lookup"><span data-stu-id="bec11-127">MSH</span></span>|<span data-ttu-id="bec11-128">メッセージ ヘッダー</span><span class="sxs-lookup"><span data-stu-id="bec11-128">Message Header</span></span>|<span data-ttu-id="bec11-129">2</span><span class="sxs-lookup"><span data-stu-id="bec11-129">2</span></span>|  
    |<span data-ttu-id="bec11-130">MSA</span><span class="sxs-lookup"><span data-stu-id="bec11-130">MSA</span></span>|<span data-ttu-id="bec11-131">メッセージの受信確認</span><span class="sxs-lookup"><span data-stu-id="bec11-131">Message Acknowledgment</span></span>|<span data-ttu-id="bec11-132">2</span><span class="sxs-lookup"><span data-stu-id="bec11-132">2</span></span>|  
    |<span data-ttu-id="bec11-133">[エラー]</span><span class="sxs-lookup"><span data-stu-id="bec11-133">[ ERR ]</span></span>|<span data-ttu-id="bec11-134">[エラー]</span><span class="sxs-lookup"><span data-stu-id="bec11-134">Error</span></span>|<span data-ttu-id="bec11-135">2</span><span class="sxs-lookup"><span data-stu-id="bec11-135">2</span></span>|  
  
 <span data-ttu-id="bec11-136">受信確認メッセージがある、MSH9 フィールドに設定するか**ACK ^\<***トリガー イベント***\>^ ACK**または**MCF ^\<** *トリガー イベント***\>^ ACK**です。</span><span class="sxs-lookup"><span data-stu-id="bec11-136">Acknowledgment messages have the MSH9 field set as either **ACK^\<***trigger event***\>^ACK** or **MCF^\<***trigger event***\>^ACK**.</span></span> <span data-ttu-id="bec11-137">その結果、MSH9 の最初のコンポーネントは ACK スキーマを決定するだけで十分です。</span><span class="sxs-lookup"><span data-stu-id="bec11-137">As a result, the first component of MSH9 is sufficient to determine the ACK schema.</span></span> <span data-ttu-id="bec11-138">ドキュメント名を[!INCLUDE[btsCoName](../../includes/btsconame-md.md)]BizTalk Accelerator 用 HL7 ([!INCLUDE[btaBTAHL71.3abbrevnonumber](../../includes/btabtahl71-3abbrevnonumber-md.md)]) パイプラインには、名前空間として HL7 常に含まれています。</span><span class="sxs-lookup"><span data-stu-id="bec11-138">The document name that the [!INCLUDE[btsCoName](../../includes/btsconame-md.md)] BizTalk Accelerator for HL7 ([!INCLUDE[btaBTAHL71.3abbrevnonumber](../../includes/btabtahl71-3abbrevnonumber-md.md)]) pipeline uses always contains HL7 as the namespace.</span></span> <span data-ttu-id="bec11-139">型名は、これは ACK または MCF MSH9_1 フィールドの内容です。</span><span class="sxs-lookup"><span data-stu-id="bec11-139">The type name is the contents of the MSH9_1 field, which is ACK or MCF.</span></span> <span data-ttu-id="bec11-140">上記の例と同様にその結果、[!INCLUDE[btaBTAHL71.3abbrevnonumber](../../includes/btabtahl71-3abbrevnonumber-md.md)]パイプラインは、HL7 の名前を持つスキーマを検索します。ACK または HL7 します。MCF、MSH9_1 フィールドの値によって決まります。</span><span class="sxs-lookup"><span data-stu-id="bec11-140">As a result, as in the example above, the [!INCLUDE[btaBTAHL71.3abbrevnonumber](../../includes/btabtahl71-3abbrevnonumber-md.md)] pipeline looks for a schema with the names HL7.ACK or HL7.MCF, depending on the value of the MSH9_1 field.</span></span> <span data-ttu-id="bec11-141">メッセージ本文のスキーマは、同じ 2.X バージョンのすべてのメッセージです。</span><span class="sxs-lookup"><span data-stu-id="bec11-141">The schema for the message body is the same for all 2.X version messages.</span></span>  
  
> [!NOTE]
>  <span data-ttu-id="bec11-142">内のバッチで/ACK シナリオでは、ACK のヘッダーの内容をバッチは次のようにします。</span><span class="sxs-lookup"><span data-stu-id="bec11-142">In a batch in/batch out ACK scenario, the contents of the ACK header is as follows:</span></span>  
  
-   [!INCLUDE[btaBTAHL71.3abbrevnonumber](../../includes/btabtahl71-3abbrevnonumber-md.md)]<span data-ttu-id="bec11-143">MSH1、2、8、およびユーザー インターフェイスでの構成を 15 に設定します。</span><span class="sxs-lookup"><span data-stu-id="bec11-143"> sets MSH1, 2, 8 and 15 to what you configure in the user interface.</span></span>  
  
-   [!INCLUDE[btaBTAHL71.3abbrevnonumber](../../includes/btabtahl71-3abbrevnonumber-md.md)]<span data-ttu-id="bec11-144">システム時刻を MSH7 を設定します。</span><span class="sxs-lookup"><span data-stu-id="bec11-144"> sets MSH7 to the system time.</span></span>  
  
-   [!INCLUDE[btaBTAHL71.3abbrevnonumber](../../includes/btabtahl71-3abbrevnonumber-md.md)]<span data-ttu-id="bec11-145">確認を MSH9 に設定します。</span><span class="sxs-lookup"><span data-stu-id="bec11-145"> sets MSH9 to ACK.</span></span>  
  
-   [!INCLUDE[btaBTAHL71.3abbrevnonumber](../../includes/btabtahl71-3abbrevnonumber-md.md)]<span data-ttu-id="bec11-146">2.4 または 2.5 MSH12 に設定します。</span><span class="sxs-lookup"><span data-stu-id="bec11-146"> sets MSH12 to 2.4 or 2.5.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="bec11-147">参照</span><span class="sxs-lookup"><span data-stu-id="bec11-147">See Also</span></span>  
 <span data-ttu-id="bec11-148">[作成して、受信確認の処理](../../adapters-and-accelerators/accelerator-hl7/creating-and-processing-acknowledgments.md) </span><span class="sxs-lookup"><span data-stu-id="bec11-148">[Creating and Processing Acknowledgments](../../adapters-and-accelerators/accelerator-hl7/creating-and-processing-acknowledgments.md) </span></span>  
 <span data-ttu-id="bec11-149">[メッセージ受信確認セグメント](../../adapters-and-accelerators/accelerator-hl7/message-acknowledgment-segment.md) </span><span class="sxs-lookup"><span data-stu-id="bec11-149">[Message Acknowledgment Segment](../../adapters-and-accelerators/accelerator-hl7/message-acknowledgment-segment.md) </span></span>  
 <span data-ttu-id="bec11-150">[Ack を受信するための送信ポートの設定](../../adapters-and-accelerators/accelerator-hl7/setting-up-a-send-port-for-receiving-acks.md) </span><span class="sxs-lookup"><span data-stu-id="bec11-150">[Setting Up a Send Port for Receiving ACKs](../../adapters-and-accelerators/accelerator-hl7/setting-up-a-send-port-for-receiving-acks.md) </span></span>  
 [<span data-ttu-id="bec11-151">受信確認エラーの条件</span><span class="sxs-lookup"><span data-stu-id="bec11-151">Acknowledgment Error Conditions</span></span>](../../adapters-and-accelerators/accelerator-hl7/acknowledgment-error-conditions.md)