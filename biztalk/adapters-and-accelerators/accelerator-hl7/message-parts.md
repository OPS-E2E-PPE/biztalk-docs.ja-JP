---
title: メッセージ部分 |Microsoft Docs
ms.custom: ''
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: ''
ms.suite: ''
ms.tgt_pltfrm: ''
ms.topic: article
helpviewer_keywords:
- messages, segments
- messages, fields
- messages, message parts
- segments, messages
ms.assetid: 2bb6557e-cd4a-42b7-8bc2-f8b53a59517e
caps.latest.revision: 3
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: 2c67694dbfe2e0cdfbc330e36d51dcf8e5a3fccd
ms.sourcegitcommit: 381e83d43796a345488d54b3f7413e11d56ad7be
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 05/07/2019
ms.locfileid: "65303684"
---
# <a name="message-parts"></a><span data-ttu-id="9637d-102">メッセージ部分</span><span class="sxs-lookup"><span data-stu-id="9637d-102">Message Parts</span></span>
<span data-ttu-id="9637d-103">HL7 メッセージには次の部分が含まれています。 セグメント、データ フィールド、コンポーネント、および必要に応じてサブコンポーネント。</span><span class="sxs-lookup"><span data-stu-id="9637d-103">An HL7 message contains the following parts: segments, data fields, components, and optionally subcomponents.</span></span> <span data-ttu-id="9637d-104">HL7 メッセージでは、次の階層構造があります。</span><span class="sxs-lookup"><span data-stu-id="9637d-104">HL7 messages have the following hierarchical structure:</span></span>  
  
 <span data-ttu-id="9637d-105">Segment</span><span class="sxs-lookup"><span data-stu-id="9637d-105">Segment</span></span>  
  
 <span data-ttu-id="9637d-106">データ フィールド</span><span class="sxs-lookup"><span data-stu-id="9637d-106">Data Field</span></span>  
  
 <span data-ttu-id="9637d-107">コンポーネント</span><span class="sxs-lookup"><span data-stu-id="9637d-107">Component</span></span>  
  
 <span data-ttu-id="9637d-108">サブコンポーネントの情報 (省略可能)</span><span class="sxs-lookup"><span data-stu-id="9637d-108">Subcomponent (optional)</span></span>  
  
 <span data-ttu-id="9637d-109">**セグメント**</span><span class="sxs-lookup"><span data-stu-id="9637d-109">**Segments**</span></span>  
  
 <span data-ttu-id="9637d-110">セグメントは、データ フィールドの論理的なグループです。</span><span class="sxs-lookup"><span data-stu-id="9637d-110">A segment is a logical grouping of data fields.</span></span> <span data-ttu-id="9637d-111">メッセージの階層の最上位レベル (階層 1) でのセグメントがいます。</span><span class="sxs-lookup"><span data-stu-id="9637d-111">Segments are at the highest level (depth 1) of the message hierarchy.</span></span> <span data-ttu-id="9637d-112">各セグメントは、3 文字のリテラル値を含む名前を持ちます。</span><span class="sxs-lookup"><span data-stu-id="9637d-112">Each segment has a name that includes a three-character literal value.</span></span> <span data-ttu-id="9637d-113">次の表では、ADT メッセージの種類に含まれているセグメント名の例を示します。</span><span class="sxs-lookup"><span data-stu-id="9637d-113">The following table shows examples of segment names contained by ADT message types.</span></span>  
  
|<span data-ttu-id="9637d-114">セグメントのコード</span><span class="sxs-lookup"><span data-stu-id="9637d-114">Segment code</span></span>|<span data-ttu-id="9637d-115">説明</span><span class="sxs-lookup"><span data-stu-id="9637d-115">Description</span></span>|  
|------------------|-----------------|  
|<span data-ttu-id="9637d-116">MSH</span><span class="sxs-lookup"><span data-stu-id="9637d-116">MSH</span></span>|<span data-ttu-id="9637d-117">メッセージ ヘッダー</span><span class="sxs-lookup"><span data-stu-id="9637d-117">Message Header</span></span>|  
|<span data-ttu-id="9637d-118">EVN</span><span class="sxs-lookup"><span data-stu-id="9637d-118">EVN</span></span>|<span data-ttu-id="9637d-119">イベントの種類</span><span class="sxs-lookup"><span data-stu-id="9637d-119">Event Type</span></span>|  
|<span data-ttu-id="9637d-120">PID</span><span class="sxs-lookup"><span data-stu-id="9637d-120">PID</span></span>|<span data-ttu-id="9637d-121">患者の情報</span><span class="sxs-lookup"><span data-stu-id="9637d-121">Patient Information</span></span>|  
  
 <span data-ttu-id="9637d-122">HL7 メッセージが、*メッセージ ヘッダー*と*本文*します。</span><span class="sxs-lookup"><span data-stu-id="9637d-122">HL7 messages have a *message header* and *body*.</span></span> <span data-ttu-id="9637d-123">MSH セグメントがメッセージのヘッダーを定義し、他のすべての種類のセグメントがメッセージの本文を形成します。</span><span class="sxs-lookup"><span data-stu-id="9637d-123">The MSH segments define the header of the message and all other types of segments form the body of the message.</span></span>  
  
 <span data-ttu-id="9637d-124">**データ フィールド**</span><span class="sxs-lookup"><span data-stu-id="9637d-124">**Data Fields**</span></span>  
  
 <span data-ttu-id="9637d-125">データ フィールドは、メッセージの階層の深さ 2 で出現する文字の文字列です。</span><span class="sxs-lookup"><span data-stu-id="9637d-125">A data field is a string of characters that occur at depth 2 of the message hierarchy.</span></span> <span data-ttu-id="9637d-126">データ型は、データ フィールドを定義します。単純および複雑な。</span><span class="sxs-lookup"><span data-stu-id="9637d-126">Data types define data fields: Simple and Complex.</span></span>  
  
 <span data-ttu-id="9637d-127">次の例は、MSH.1 と EVN.1 データ フィールドを含む MSH および EVN セグメントの階層的なメッセージの構造を示しています。</span><span class="sxs-lookup"><span data-stu-id="9637d-127">The following example shows the hierarchical message structure of the MSH and EVN segments containing the MSH.1 and EVN.1 data fields:</span></span>  
  
 <span data-ttu-id="9637d-128">MSH</span><span class="sxs-lookup"><span data-stu-id="9637d-128">MSH</span></span>  
  
 <span data-ttu-id="9637d-129">MSH.1</span><span class="sxs-lookup"><span data-stu-id="9637d-129">MSH.1</span></span>  
  
 <span data-ttu-id="9637d-130">EVN</span><span class="sxs-lookup"><span data-stu-id="9637d-130">EVN</span></span>  
  
 <span data-ttu-id="9637d-131">EVN.1</span><span class="sxs-lookup"><span data-stu-id="9637d-131">EVN.1</span></span>  
  
 <span data-ttu-id="9637d-132">**コンポーネントとサブコンポーネント**</span><span class="sxs-lookup"><span data-stu-id="9637d-132">**Components and Subcomponents**</span></span>  
  
 <span data-ttu-id="9637d-133">コンポーネントとサブコンポーネントをさらに データ フィールド内のデータが含まれます。</span><span class="sxs-lookup"><span data-stu-id="9637d-133">Components and subcomponents further contain the data within data fields.</span></span> <span data-ttu-id="9637d-134">コンポーネントとサブコンポーネントは、同じフィールド内で繰り返すことができます。</span><span class="sxs-lookup"><span data-stu-id="9637d-134">Components and subcomponents can repeat within the same field.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="9637d-135">参照</span><span class="sxs-lookup"><span data-stu-id="9637d-135">See Also</span></span>  
 <span data-ttu-id="9637d-136">[HL7 メッセージの処理](../../adapters-and-accelerators/accelerator-hl7/processing-hl7-messages.md) </span><span class="sxs-lookup"><span data-stu-id="9637d-136">[Processing HL7 Messages](../../adapters-and-accelerators/accelerator-hl7/processing-hl7-messages.md) </span></span>  
 <span data-ttu-id="9637d-137">[メッセージの処理](../../adapters-and-accelerators/accelerator-hl7/message-processing.md) </span><span class="sxs-lookup"><span data-stu-id="9637d-137">[Message Processing](../../adapters-and-accelerators/accelerator-hl7/message-processing.md) </span></span>  
 [<span data-ttu-id="9637d-138">HL7 2.X スキーマの使用</span><span class="sxs-lookup"><span data-stu-id="9637d-138">Using HL7 2.X Schemas</span></span>](../../adapters-and-accelerators/accelerator-hl7/using-hl7-2-x-schemas.md)