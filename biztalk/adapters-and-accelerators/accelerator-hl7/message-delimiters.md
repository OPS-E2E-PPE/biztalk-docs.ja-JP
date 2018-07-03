---
title: メッセージの区切り記号 |Microsoft Docs
ms.custom: ''
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: ''
ms.suite: ''
ms.tgt_pltfrm: ''
ms.topic: article
helpviewer_keywords:
- messages, events
- messages, XML messages
- events
- delimiters
- messages, delimiters
- flat files
- XML messages
- messages, flat files
ms.assetid: d25bf6db-5512-4c82-be0e-00da024c55d1
caps.latest.revision: 3
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: 3339ded8edf46f7c5b96317cdf7a3ec822ec808b
ms.sourcegitcommit: 266308ec5c6a9d8d80ff298ee6051b4843c5d626
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 06/27/2018
ms.locfileid: "37001499"
---
# <a name="message-delimiters"></a><span data-ttu-id="cef36-102">メッセージの区切り記号</span><span class="sxs-lookup"><span data-stu-id="cef36-102">Message Delimiters</span></span>
<span data-ttu-id="cef36-103">HL7 標準によって定義されたメッセージのイベントは、次の形式をとります。</span><span class="sxs-lookup"><span data-stu-id="cef36-103">Message events defined by HL7 standards take the following form:</span></span>  
  
- <span data-ttu-id="cef36-104">**フラット ファイル**します。</span><span class="sxs-lookup"><span data-stu-id="cef36-104">**Flat files**.</span></span> <span data-ttu-id="cef36-105">HL7 2.4 以前のバージョンによって定義されたメッセージのイベントは、フラット ファイルの形式になります。</span><span class="sxs-lookup"><span data-stu-id="cef36-105">Message events defined by HL7 versions 2.4 and earlier take the form of flat files.</span></span>  
  
- <span data-ttu-id="cef36-106">**XML**します。</span><span class="sxs-lookup"><span data-stu-id="cef36-106">**XML**.</span></span> <span data-ttu-id="cef36-107">HL7 バージョン 2. XML およびバージョン 3 で定義されたメッセージのイベントは、XML ファイルの形式になります。</span><span class="sxs-lookup"><span data-stu-id="cef36-107">Message events defined by HL7 versions 2.XML and version 3 take the form of XML files.</span></span>  
  
  <span data-ttu-id="cef36-108">標準 HL7 が位置指定の形式に従っていないために、セグメント、フィールド、コンポーネント、およびフラット ファイルのサブコンポーネントの情報のレベルを定義するのに区切り記号を使用します。</span><span class="sxs-lookup"><span data-stu-id="cef36-108">Since the HL7 standard does not follow positional format, it uses delimiters to define the segment, field, component, and subcomponent levels of flat files.</span></span> <span data-ttu-id="cef36-109">HL7 のフラット ファイルによって使用される既定の区切り記号を次の表に示します。</span><span class="sxs-lookup"><span data-stu-id="cef36-109">The following table lists the default delimiters used by HL7 flat files.</span></span>  
  
|<span data-ttu-id="cef36-110">区切り記号</span><span class="sxs-lookup"><span data-stu-id="cef36-110">Delimiter</span></span>|<span data-ttu-id="cef36-111">値</span><span class="sxs-lookup"><span data-stu-id="cef36-111">Value</span></span>|<span data-ttu-id="cef36-112">使用方法</span><span class="sxs-lookup"><span data-stu-id="cef36-112">Usage</span></span>|  
|---------------|-----------|-----------|  
|<span data-ttu-id="cef36-113">[ セグメント終端記号]</span><span class="sxs-lookup"><span data-stu-id="cef36-113">Segment terminator</span></span>|<span data-ttu-id="cef36-114">\<cr\></span><span class="sxs-lookup"><span data-stu-id="cef36-114">\<cr\></span></span>|<span data-ttu-id="cef36-115">キャリッジ リターンとは、セグメントのレコードを終了します。</span><span class="sxs-lookup"><span data-stu-id="cef36-115">A carriage return terminates a segment record.</span></span> <span data-ttu-id="cef36-116">この値を変更することはできません。</span><span class="sxs-lookup"><span data-stu-id="cef36-116">You cannot change this value.</span></span>|  
|<span data-ttu-id="cef36-117">フィールドの区切り記号</span><span class="sxs-lookup"><span data-stu-id="cef36-117">Field separator</span></span>|<span data-ttu-id="cef36-118">&#124;</span><span class="sxs-lookup"><span data-stu-id="cef36-118">&#124;</span></span>|<span data-ttu-id="cef36-119">パイプ文字では、セグメント内で 2 つの連続するデータ フィールドを区切ります。</span><span class="sxs-lookup"><span data-stu-id="cef36-119">A pipe character separates two adjacent data fields within a segment.</span></span> <span data-ttu-id="cef36-120">この文字は、各セグメントには、最初のデータ フィールドからセグメント ID も分離します。</span><span class="sxs-lookup"><span data-stu-id="cef36-120">This character also separates the segment ID from the first data field in each segment.</span></span>|  
|<span data-ttu-id="cef36-121">[コンポーネントの区切り記号]</span><span class="sxs-lookup"><span data-stu-id="cef36-121">Component separator</span></span>|^|<span data-ttu-id="cef36-122">Hat の文字データの横にあるコンポーネントの分離、HL7 標準で許可されている場所のフィールドします。</span><span class="sxs-lookup"><span data-stu-id="cef36-122">A hat character separates adjacent components of data fields where allowed by the HL7 standard.</span></span>|  
|<span data-ttu-id="cef36-123">サブコンポーネントの区切り記号</span><span class="sxs-lookup"><span data-stu-id="cef36-123">Subcomponent separator</span></span>|&|<span data-ttu-id="cef36-124">アンパサンド文字は、データの隣接するサブコンポーネントを区切る HL7 標準で許可されている場所のフィールドします。</span><span class="sxs-lookup"><span data-stu-id="cef36-124">An ampersand character separates adjacent subcomponents of data fields where allowed by the HL7 standard.</span></span> <span data-ttu-id="cef36-125">サブコンポーネントがない場合は、この文字を省略できます。</span><span class="sxs-lookup"><span data-stu-id="cef36-125">If there are no subcomponents, then you can omit this character.</span></span>|  
|<span data-ttu-id="cef36-126">繰り返し区切り記号</span><span class="sxs-lookup"><span data-stu-id="cef36-126">Repetition separator</span></span>|~|<span data-ttu-id="cef36-127">チルダ文字は、コンポーネントまたはサブコンポーネント フィールド内の複数の発生を区切る HL7 標準で許可します。</span><span class="sxs-lookup"><span data-stu-id="cef36-127">A tilde character separates multiple occurrences of components or subcomponents in a field where allowed by the HL7 standard.</span></span>|  
|<span data-ttu-id="cef36-128">[エスケープ文字]</span><span class="sxs-lookup"><span data-stu-id="cef36-128">Escape character</span></span>|<span data-ttu-id="cef36-129">\|ST、テキサス州または FT のデータ型に準拠している任意のフィールドと ED データ型のデータ (4 番目) のコンポーネントは、エスケープ文字を使用します。</span><span class="sxs-lookup"><span data-stu-id="cef36-129">\|You use an escape character with any field that conforms to an ST, TX, or FT data type, or with the data (fourth) component of the ED data type.</span></span> <span data-ttu-id="cef36-130">メッセージにエスケープ文字が存在しない場合は、この文字を省略できます。</span><span class="sxs-lookup"><span data-stu-id="cef36-130">If no escape characters exist in a message, you can omit this character.</span></span> <span data-ttu-id="cef36-131">ただし、メッセージのサブコンポーネントを使用する場合に追加する必要があります。</span><span class="sxs-lookup"><span data-stu-id="cef36-131">However, you must include it if you use subcomponents in the message.</span></span>|  
  
## <a name="see-also"></a><span data-ttu-id="cef36-132">参照</span><span class="sxs-lookup"><span data-stu-id="cef36-132">See Also</span></span>  
 <span data-ttu-id="cef36-133">[HL7 メッセージの処理](../../adapters-and-accelerators/accelerator-hl7/processing-hl7-messages.md) </span><span class="sxs-lookup"><span data-stu-id="cef36-133">[Processing HL7 Messages](../../adapters-and-accelerators/accelerator-hl7/processing-hl7-messages.md) </span></span>  
 <span data-ttu-id="cef36-134">[メッセージの処理](../../adapters-and-accelerators/accelerator-hl7/message-processing.md) </span><span class="sxs-lookup"><span data-stu-id="cef36-134">[Message Processing](../../adapters-and-accelerators/accelerator-hl7/message-processing.md) </span></span>  
 [<span data-ttu-id="cef36-135">HL7 2.X スキーマの使用</span><span class="sxs-lookup"><span data-stu-id="cef36-135">Using HL7 2.X Schemas</span></span>](../../adapters-and-accelerators/accelerator-hl7/using-hl7-2-x-schemas.md)