---
title: ACK メッセージ スキーマの種類 |Microsoft Docs
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
ms.openlocfilehash: 923cd9122f1b0d322f5a12d3be38f660a67d054e
ms.sourcegitcommit: 381e83d43796a345488d54b3f7413e11d56ad7be
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 05/07/2019
ms.locfileid: "65247570"
---
# <a name="ack-message-schema-types"></a><span data-ttu-id="a5a82-102">ACK メッセージ スキーマの種類</span><span class="sxs-lookup"><span data-stu-id="a5a82-102">ACK Message Schema Types</span></span>
<span data-ttu-id="a5a82-103">受信確認メッセージのスキーマは 2 つの形式があります。</span><span class="sxs-lookup"><span data-stu-id="a5a82-103">Acknowledgment message schemas come in two forms:</span></span>  

- <span data-ttu-id="a5a82-104">**一般的な確認 (ACK)** します。</span><span class="sxs-lookup"><span data-stu-id="a5a82-104">**General acknowledgment (ACK)**.</span></span> <span data-ttu-id="a5a82-105">一般的な確認 (ACK) を使用するには、アプリケーションが特別な基幹業務アプリケーション レベルの受信確認メッセージを定義していない、またはアプリケーションの処理にエラーが発生しました。</span><span class="sxs-lookup"><span data-stu-id="a5a82-105">You can use a general acknowledgment (ACK) where the application does not define a special line-of-business application level acknowledgment message or where an error occurred that precludes application processing.</span></span> <span data-ttu-id="a5a82-106">これを使用することもできますの受信確認のレベルをそのまま使用します。</span><span class="sxs-lookup"><span data-stu-id="a5a82-106">You can also use it for accept level acknowledgments.</span></span> <span data-ttu-id="a5a82-107">次の表では、ACK メッセージの構造を示します。</span><span class="sxs-lookup"><span data-stu-id="a5a82-107">The following table lists the ACK message structure.</span></span>  


  | <span data-ttu-id="a5a82-108">ACK^varies^ACK</span><span class="sxs-lookup"><span data-stu-id="a5a82-108">ACK^varies^ACK</span></span> | <span data-ttu-id="a5a82-109">一般的な受信確認</span><span class="sxs-lookup"><span data-stu-id="a5a82-109">General acknowledgment</span></span> | <span data-ttu-id="a5a82-110">」の章</span><span class="sxs-lookup"><span data-stu-id="a5a82-110">Chapter</span></span> |
  |----------------|------------------------|---------|
  |      <span data-ttu-id="a5a82-111">MSH</span><span class="sxs-lookup"><span data-stu-id="a5a82-111">MSH</span></span>       |     <span data-ttu-id="a5a82-112">メッセージ ヘッダー</span><span class="sxs-lookup"><span data-stu-id="a5a82-112">Message Header</span></span>     |    <span data-ttu-id="a5a82-113">2</span><span class="sxs-lookup"><span data-stu-id="a5a82-113">2</span></span>    |
  |      <span data-ttu-id="a5a82-114">MSA</span><span class="sxs-lookup"><span data-stu-id="a5a82-114">MSA</span></span>       | <span data-ttu-id="a5a82-115">メッセージの受信確認</span><span class="sxs-lookup"><span data-stu-id="a5a82-115">Message Acknowledgment</span></span> |    <span data-ttu-id="a5a82-116">2</span><span class="sxs-lookup"><span data-stu-id="a5a82-116">2</span></span>    |
  |    <span data-ttu-id="a5a82-117">[エラー]</span><span class="sxs-lookup"><span data-stu-id="a5a82-117">[ ERR ]</span></span>     |         <span data-ttu-id="a5a82-118">[エラー]</span><span class="sxs-lookup"><span data-stu-id="a5a82-118">Error</span></span>          |    <span data-ttu-id="a5a82-119">2</span><span class="sxs-lookup"><span data-stu-id="a5a82-119">2</span></span>    |


- <span data-ttu-id="a5a82-120">**遅延確認応答 (mcf という)** します。</span><span class="sxs-lookup"><span data-stu-id="a5a82-120">**Delayed acknowledgment (MCF)**.</span></span> <span data-ttu-id="a5a82-121">このメッセージは、HL7 バージョン 2.1 の旧バージョンと互換性のためにのみ存在します。</span><span class="sxs-lookup"><span data-stu-id="a5a82-121">This message exists only for backward compatibility with HL7 Version 2.1.</span></span> <span data-ttu-id="a5a82-122">非同期のアプリケーション レベル確認、MCF メッセージの一般的なフォームを作成するプロトコルの一部として使用するとします。</span><span class="sxs-lookup"><span data-stu-id="a5a82-122">You use it as part of the protocol that creates a generic form of an asynchronous application level acknowledgment, the MCF message.</span></span> <span data-ttu-id="a5a82-123">次の表では、MCF メッセージの構造を示します。</span><span class="sxs-lookup"><span data-stu-id="a5a82-123">The following table lists the MCF message structure.</span></span>  

  |<span data-ttu-id="a5a82-124">MCF^varies^ACK</span><span class="sxs-lookup"><span data-stu-id="a5a82-124">MCF^varies^ACK</span></span>|<span data-ttu-id="a5a82-125">受信確認の遅延</span><span class="sxs-lookup"><span data-stu-id="a5a82-125">Delayed Acknowledgment</span></span>|<span data-ttu-id="a5a82-126">」の章</span><span class="sxs-lookup"><span data-stu-id="a5a82-126">Chapter</span></span>|  
  |--------------------|----------------------------|-------------|  
  |<span data-ttu-id="a5a82-127">MSH</span><span class="sxs-lookup"><span data-stu-id="a5a82-127">MSH</span></span>|<span data-ttu-id="a5a82-128">メッセージ ヘッダー</span><span class="sxs-lookup"><span data-stu-id="a5a82-128">Message Header</span></span>|<span data-ttu-id="a5a82-129">2</span><span class="sxs-lookup"><span data-stu-id="a5a82-129">2</span></span>|  
  |<span data-ttu-id="a5a82-130">MSA</span><span class="sxs-lookup"><span data-stu-id="a5a82-130">MSA</span></span>|<span data-ttu-id="a5a82-131">メッセージの受信確認</span><span class="sxs-lookup"><span data-stu-id="a5a82-131">Message Acknowledgment</span></span>|<span data-ttu-id="a5a82-132">2</span><span class="sxs-lookup"><span data-stu-id="a5a82-132">2</span></span>|  
  |<span data-ttu-id="a5a82-133">[エラー]</span><span class="sxs-lookup"><span data-stu-id="a5a82-133">[ ERR ]</span></span>|<span data-ttu-id="a5a82-134">[エラー]</span><span class="sxs-lookup"><span data-stu-id="a5a82-134">Error</span></span>|<span data-ttu-id="a5a82-135">2</span><span class="sxs-lookup"><span data-stu-id="a5a82-135">2</span></span>|  

  <span data-ttu-id="a5a82-136">受信確認メッセージがある、MSH9 フィールドに設定するか**ACK ^\<**<em>トリガー イベント</em>**\>^ ACK**または**MCF ^\<** <em>トリガー イベント</em>**\>^ ACK**します。</span><span class="sxs-lookup"><span data-stu-id="a5a82-136">Acknowledgment messages have the MSH9 field set as either **ACK^\<**<em>trigger event</em>**\>^ACK** or **MCF^\<**<em>trigger event</em>**\>^ACK**.</span></span> <span data-ttu-id="a5a82-137">その結果、MSH9 の最初のコンポーネントは ACK スキーマを決定するための十分です。</span><span class="sxs-lookup"><span data-stu-id="a5a82-137">As a result, the first component of MSH9 is sufficient to determine the ACK schema.</span></span> <span data-ttu-id="a5a82-138">ドキュメント名を Microsoft BizTalk Accelerator 用 HL7 ([!INCLUDE[btaBTAHL71.3abbrevnonumber](../../includes/btabtahl71-3abbrevnonumber-md.md)]) パイプラインの名前空間として HL7 を常に含まれます。</span><span class="sxs-lookup"><span data-stu-id="a5a82-138">The document name that the Microsoft BizTalk Accelerator for HL7 ([!INCLUDE[btaBTAHL71.3abbrevnonumber](../../includes/btabtahl71-3abbrevnonumber-md.md)]) pipeline uses always contains HL7 as the namespace.</span></span> <span data-ttu-id="a5a82-139">型名は、これは ACK または MCF MSH9_1 フィールドの内容です。</span><span class="sxs-lookup"><span data-stu-id="a5a82-139">The type name is the contents of the MSH9_1 field, which is ACK or MCF.</span></span> <span data-ttu-id="a5a82-140">結果として、上記の例のように、[!INCLUDE[btaBTAHL71.3abbrevnonumber](../../includes/btabtahl71-3abbrevnonumber-md.md)]パイプラインが HL7 の名前を持つスキーマを探します。ACK または HL7 します。MCF、MSH9_1 フィールドの値によって決まります。</span><span class="sxs-lookup"><span data-stu-id="a5a82-140">As a result, as in the example above, the [!INCLUDE[btaBTAHL71.3abbrevnonumber](../../includes/btabtahl71-3abbrevnonumber-md.md)] pipeline looks for a schema with the names HL7.ACK or HL7.MCF, depending on the value of the MSH9_1 field.</span></span> <span data-ttu-id="a5a82-141">メッセージ本文のスキーマは、2.X バージョンのすべてのメッセージに同じです。</span><span class="sxs-lookup"><span data-stu-id="a5a82-141">The schema for the message body is the same for all 2.X version messages.</span></span>  

> [!NOTE]
>  <span data-ttu-id="a5a82-142">内のバッチで/バッチ アウト シナリオの確認、ACK ヘッダーの内容は次のようにします。</span><span class="sxs-lookup"><span data-stu-id="a5a82-142">In a batch in/batch out ACK scenario, the contents of the ACK header is as follows:</span></span>  

- [!INCLUDE[btaBTAHL71.3abbrevnonumber](../../includes/btabtahl71-3abbrevnonumber-md.md)] <span data-ttu-id="a5a82-143">MSH1、2、8、15 日に、ユーザー インターフェイスの構成を設定します。</span><span class="sxs-lookup"><span data-stu-id="a5a82-143">sets MSH1, 2, 8 and 15 to what you configure in the user interface.</span></span>  

- [!INCLUDE[btaBTAHL71.3abbrevnonumber](../../includes/btabtahl71-3abbrevnonumber-md.md)] <span data-ttu-id="a5a82-144">MSH7 システム時刻に設定します。</span><span class="sxs-lookup"><span data-stu-id="a5a82-144">sets MSH7 to the system time.</span></span>  

- [!INCLUDE[btaBTAHL71.3abbrevnonumber](../../includes/btabtahl71-3abbrevnonumber-md.md)] <span data-ttu-id="a5a82-145">MSH9 を確認する設定します。</span><span class="sxs-lookup"><span data-stu-id="a5a82-145">sets MSH9 to ACK.</span></span>  

- [!INCLUDE[btaBTAHL71.3abbrevnonumber](../../includes/btabtahl71-3abbrevnonumber-md.md)] <span data-ttu-id="a5a82-146">2.4、2.5 MSH12 に設定します。</span><span class="sxs-lookup"><span data-stu-id="a5a82-146">sets MSH12 to 2.4 or 2.5.</span></span>  

## <a name="see-also"></a><span data-ttu-id="a5a82-147">参照</span><span class="sxs-lookup"><span data-stu-id="a5a82-147">See Also</span></span>  
 <span data-ttu-id="a5a82-148">[作成して、受信確認の処理](../../adapters-and-accelerators/accelerator-hl7/creating-and-processing-acknowledgments.md) </span><span class="sxs-lookup"><span data-stu-id="a5a82-148">[Creating and Processing Acknowledgments](../../adapters-and-accelerators/accelerator-hl7/creating-and-processing-acknowledgments.md) </span></span>  
 <span data-ttu-id="a5a82-149">[メッセージの受信確認セグメント](../../adapters-and-accelerators/accelerator-hl7/message-acknowledgment-segment.md) </span><span class="sxs-lookup"><span data-stu-id="a5a82-149">[Message Acknowledgment Segment](../../adapters-and-accelerators/accelerator-hl7/message-acknowledgment-segment.md) </span></span>  
 <span data-ttu-id="a5a82-150">[Ack を受信するための送信ポートの設定](../../adapters-and-accelerators/accelerator-hl7/setting-up-a-send-port-for-receiving-acks.md) </span><span class="sxs-lookup"><span data-stu-id="a5a82-150">[Setting Up a Send Port for Receiving ACKs](../../adapters-and-accelerators/accelerator-hl7/setting-up-a-send-port-for-receiving-acks.md) </span></span>  
 [<span data-ttu-id="a5a82-151">受信確認エラーの条件</span><span class="sxs-lookup"><span data-stu-id="a5a82-151">Acknowledgment Error Conditions</span></span>](../../adapters-and-accelerators/accelerator-hl7/acknowledgment-error-conditions.md)