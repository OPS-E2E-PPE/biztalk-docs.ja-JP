---
title: メッセージ部分 |Microsoft ドキュメント
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
ms.openlocfilehash: d9b6b02096a0cc75460552a6cd1dd56ef9e6c4e9
ms.sourcegitcommit: cb908c540d8f1a692d01dc8f313e16cb4b4e696d
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 09/20/2017
ms.locfileid: "22205082"
---
# <a name="message-parts"></a><span data-ttu-id="a7eac-102">メッセージ部分</span><span class="sxs-lookup"><span data-stu-id="a7eac-102">Message Parts</span></span>
<span data-ttu-id="a7eac-103">HL7 メッセージには、次の部分が含まれています。 セグメント、データ フィールド、コンポーネント、および必要に応じてこれらのサブコンポーネントです。</span><span class="sxs-lookup"><span data-stu-id="a7eac-103">An HL7 message contains the following parts: segments, data fields, components, and optionally subcomponents.</span></span> <span data-ttu-id="a7eac-104">HL7 メッセージでは、次の階層構造があります。</span><span class="sxs-lookup"><span data-stu-id="a7eac-104">HL7 messages have the following hierarchical structure:</span></span>  
  
 <span data-ttu-id="a7eac-105">Segment</span><span class="sxs-lookup"><span data-stu-id="a7eac-105">Segment</span></span>  
  
 <span data-ttu-id="a7eac-106">データ フィールド</span><span class="sxs-lookup"><span data-stu-id="a7eac-106">Data Field</span></span>  
  
 <span data-ttu-id="a7eac-107">コンポーネント</span><span class="sxs-lookup"><span data-stu-id="a7eac-107">Component</span></span>  
  
 <span data-ttu-id="a7eac-108">サブコンポーネント (省略可能)</span><span class="sxs-lookup"><span data-stu-id="a7eac-108">Subcomponent (optional)</span></span>  
  
 <span data-ttu-id="a7eac-109">**セグメント**</span><span class="sxs-lookup"><span data-stu-id="a7eac-109">**Segments**</span></span>  
  
 <span data-ttu-id="a7eac-110">セグメントは、データ フィールドの論理的なグループです。</span><span class="sxs-lookup"><span data-stu-id="a7eac-110">A segment is a logical grouping of data fields.</span></span> <span data-ttu-id="a7eac-111">セグメントは、メッセージの階層の最上位レベル (階層 1) でです。</span><span class="sxs-lookup"><span data-stu-id="a7eac-111">Segments are at the highest level (depth 1) of the message hierarchy.</span></span> <span data-ttu-id="a7eac-112">各セグメントには、3 文字のリテラル値が含まれる、名前が付いています。</span><span class="sxs-lookup"><span data-stu-id="a7eac-112">Each segment has a name that includes a three-character literal value.</span></span> <span data-ttu-id="a7eac-113">次の表は、ADT メッセージの種類に含まれているセグメント名の例を示します。</span><span class="sxs-lookup"><span data-stu-id="a7eac-113">The following table shows examples of segment names contained by ADT message types.</span></span>  
  
|<span data-ttu-id="a7eac-114">セグメント コード</span><span class="sxs-lookup"><span data-stu-id="a7eac-114">Segment code</span></span>|<span data-ttu-id="a7eac-115">Description</span><span class="sxs-lookup"><span data-stu-id="a7eac-115">Description</span></span>|  
|------------------|-----------------|  
|<span data-ttu-id="a7eac-116">MSH</span><span class="sxs-lookup"><span data-stu-id="a7eac-116">MSH</span></span>|<span data-ttu-id="a7eac-117">メッセージ ヘッダー</span><span class="sxs-lookup"><span data-stu-id="a7eac-117">Message Header</span></span>|  
|<span data-ttu-id="a7eac-118">EVN</span><span class="sxs-lookup"><span data-stu-id="a7eac-118">EVN</span></span>|<span data-ttu-id="a7eac-119">[イベントの種類]</span><span class="sxs-lookup"><span data-stu-id="a7eac-119">Event Type</span></span>|  
|<span data-ttu-id="a7eac-120">PID</span><span class="sxs-lookup"><span data-stu-id="a7eac-120">PID</span></span>|<span data-ttu-id="a7eac-121">患者の情報</span><span class="sxs-lookup"><span data-stu-id="a7eac-121">Patient Information</span></span>|  
  
 <span data-ttu-id="a7eac-122">HL7 メッセージが、*メッセージ ヘッダー*と*本文*です。</span><span class="sxs-lookup"><span data-stu-id="a7eac-122">HL7 messages have a *message header* and *body*.</span></span> <span data-ttu-id="a7eac-123">MSH セグメントがメッセージのヘッダーを定義し、その他のすべての種類のセグメントがメッセージの本文を形成します。</span><span class="sxs-lookup"><span data-stu-id="a7eac-123">The MSH segments define the header of the message and all other types of segments form the body of the message.</span></span>  
  
 <span data-ttu-id="a7eac-124">**データ フィールド**</span><span class="sxs-lookup"><span data-stu-id="a7eac-124">**Data Fields**</span></span>  
  
 <span data-ttu-id="a7eac-125">データ フィールドは、メッセージの階層の深さ 2 で発生する文字の文字列です。</span><span class="sxs-lookup"><span data-stu-id="a7eac-125">A data field is a string of characters that occur at depth 2 of the message hierarchy.</span></span> <span data-ttu-id="a7eac-126">データ型は、データ フィールドを定義します。 単純と複合型。</span><span class="sxs-lookup"><span data-stu-id="a7eac-126">Data types define data fields: Simple and Complex.</span></span>  
  
 <span data-ttu-id="a7eac-127">次の例は、MSH.1 と EVN.1 データ フィールドを含む、MSH および EVN セグメントの階層的なメッセージの構造を示しています。</span><span class="sxs-lookup"><span data-stu-id="a7eac-127">The following example shows the hierarchical message structure of the MSH and EVN segments containing the MSH.1 and EVN.1 data fields:</span></span>  
  
 <span data-ttu-id="a7eac-128">MSH</span><span class="sxs-lookup"><span data-stu-id="a7eac-128">MSH</span></span>  
  
 <span data-ttu-id="a7eac-129">MSH.1</span><span class="sxs-lookup"><span data-stu-id="a7eac-129">MSH.1</span></span>  
  
 <span data-ttu-id="a7eac-130">EVN</span><span class="sxs-lookup"><span data-stu-id="a7eac-130">EVN</span></span>  
  
 <span data-ttu-id="a7eac-131">EVN.1</span><span class="sxs-lookup"><span data-stu-id="a7eac-131">EVN.1</span></span>  
  
 <span data-ttu-id="a7eac-132">**コンポーネントとサブコンポーネント**</span><span class="sxs-lookup"><span data-stu-id="a7eac-132">**Components and Subcomponents**</span></span>  
  
 <span data-ttu-id="a7eac-133">コンポーネントとサブコンポーネントをさらにデータ フィールド内のデータが含まれています。</span><span class="sxs-lookup"><span data-stu-id="a7eac-133">Components and subcomponents further contain the data within data fields.</span></span> <span data-ttu-id="a7eac-134">コンポーネントとサブコンポーネントは、同じフィールド内で繰り返すことができます。</span><span class="sxs-lookup"><span data-stu-id="a7eac-134">Components and subcomponents can repeat within the same field.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="a7eac-135">参照</span><span class="sxs-lookup"><span data-stu-id="a7eac-135">See Also</span></span>  
 <span data-ttu-id="a7eac-136">[HL7 メッセージの処理](../../adapters-and-accelerators/accelerator-hl7/processing-hl7-messages.md) </span><span class="sxs-lookup"><span data-stu-id="a7eac-136">[Processing HL7 Messages](../../adapters-and-accelerators/accelerator-hl7/processing-hl7-messages.md) </span></span>  
 <span data-ttu-id="a7eac-137">[メッセージの処理](../../adapters-and-accelerators/accelerator-hl7/message-processing.md) </span><span class="sxs-lookup"><span data-stu-id="a7eac-137">[Message Processing](../../adapters-and-accelerators/accelerator-hl7/message-processing.md) </span></span>  
 [<span data-ttu-id="a7eac-138">HL7 2.X スキーマの使用</span><span class="sxs-lookup"><span data-stu-id="a7eac-138">Using HL7 2.X Schemas</span></span>](../../adapters-and-accelerators/accelerator-hl7/using-hl7-2-x-schemas.md)