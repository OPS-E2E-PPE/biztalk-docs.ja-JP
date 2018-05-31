---
title: TIBCO Rendezvous でのマッピングをメッセージ |Microsoft ドキュメント
description: メッセージ フィールドと TIBCO Rendezvous の BizTalk アダプター内の XML へのメッセージ マッピング
ms.custom: ''
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: ''
ms.suite: ''
ms.tgt_pltfrm: ''
ms.topic: article
ms.assetid: 62793bec-f076-425c-b25e-c4be5bd93cc8
caps.latest.revision: 6
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: fb80ea4f908aa50dc32755c333aa3ccf2ea4db91
ms.sourcegitcommit: dd7c54feab783ae2f8fe75873363fe9ffc77cd66
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 11/07/2017
ms.locfileid: "24014953"
---
# <a name="message-mapping-in-tibco-rendezvous"></a><span data-ttu-id="c00b3-103">TIBCO Rendezvous でのメッセージ マッピング</span><span class="sxs-lookup"><span data-stu-id="c00b3-103">Message Mapping in TIBCO Rendezvous</span></span>
<span data-ttu-id="c00b3-104">TIBCO Rendezvous メッセージは、ヘッダー情報と一連のメッセージ フィールドで構成されています。</span><span class="sxs-lookup"><span data-stu-id="c00b3-104">TIBCO Rendezvous messages are composed of header information and a set of message fields.</span></span> <span data-ttu-id="c00b3-105">ヘッダー情報は、メッセージ コンテキスト プロパティに直接マップされます。</span><span class="sxs-lookup"><span data-stu-id="c00b3-105">The header information is directly mapped to message context properties.</span></span>  
  
## <a name="message-field-elements"></a><span data-ttu-id="c00b3-106">メッセージ フィールドの要素</span><span class="sxs-lookup"><span data-stu-id="c00b3-106">Message Field Elements</span></span>  
 <span data-ttu-id="c00b3-107">メッセージ フィールドは以下の要素で構成されています。</span><span class="sxs-lookup"><span data-stu-id="c00b3-107">A message field is composed of the following elements:</span></span>  
  
|<span data-ttu-id="c00b3-108">要素</span><span class="sxs-lookup"><span data-stu-id="c00b3-108">Element</span></span>|<span data-ttu-id="c00b3-109">Description</span><span class="sxs-lookup"><span data-stu-id="c00b3-109">Description</span></span>|  
|-------------|-----------------|  
|<span data-ttu-id="c00b3-110">**名前**</span><span class="sxs-lookup"><span data-stu-id="c00b3-110">**Name**</span></span>|<span data-ttu-id="c00b3-111">文字の文字列。</span><span class="sxs-lookup"><span data-stu-id="c00b3-111">Character string.</span></span> <span data-ttu-id="c00b3-112">メッセージ内で一意である必要はありません。</span><span class="sxs-lookup"><span data-stu-id="c00b3-112">Does not have to be unique in a message.</span></span>|  
|<span data-ttu-id="c00b3-113">**[Identifier]**</span><span class="sxs-lookup"><span data-stu-id="c00b3-113">**Identifier**</span></span>|<span data-ttu-id="c00b3-114">短整数。</span><span class="sxs-lookup"><span data-stu-id="c00b3-114">Short integer.</span></span> <span data-ttu-id="c00b3-115">メッセージ内で一意です。</span><span class="sxs-lookup"><span data-stu-id="c00b3-115">Unique in a message.</span></span> <span data-ttu-id="c00b3-116">暗黙的に 65535 メッセージ フィールドの数を制限します。</span><span class="sxs-lookup"><span data-stu-id="c00b3-116">Implicitly limits the number of message fields to 65535.</span></span> <span data-ttu-id="c00b3-117">識別子のスコープは、メッセージ (またはサブメッセージ) です。</span><span class="sxs-lookup"><span data-stu-id="c00b3-117">The scope of the identifier is the message (or sub message).</span></span> <span data-ttu-id="c00b3-118">同じメッセージに含まれる 2 つのサブメッセージで、同じ識別子を使用できます。</span><span class="sxs-lookup"><span data-stu-id="c00b3-118">The same identifier can be used in two sub-messages, which are themselves part of a containing message.</span></span>|  
|<span data-ttu-id="c00b3-119">**値**</span><span class="sxs-lookup"><span data-stu-id="c00b3-119">**Value**</span></span>|<span data-ttu-id="c00b3-120">メッセージ フィールドのデータ。</span><span class="sxs-lookup"><span data-stu-id="c00b3-120">The message field data.</span></span>|  
|<span data-ttu-id="c00b3-121">**Count**</span><span class="sxs-lookup"><span data-stu-id="c00b3-121">**Count**</span></span>|<span data-ttu-id="c00b3-122">項目の数 (配列の場合)。</span><span class="sxs-lookup"><span data-stu-id="c00b3-122">Number of items (in the case of an array)</span></span>|  
|<span data-ttu-id="c00b3-123">**型**</span><span class="sxs-lookup"><span data-stu-id="c00b3-123">**Type**</span></span>|<span data-ttu-id="c00b3-124">メッセージ フィールドの種類。</span><span class="sxs-lookup"><span data-stu-id="c00b3-124">The type of the message field.</span></span>|  
  
### <a name="mapping-process"></a><span data-ttu-id="c00b3-125">マッピング プロセス</span><span class="sxs-lookup"><span data-stu-id="c00b3-125">Mapping Process</span></span>  
 <span data-ttu-id="c00b3-126">TIBCO Rendezvous の構造化されたメッセージは、以下のようにして XML 要素にマップされます。</span><span class="sxs-lookup"><span data-stu-id="c00b3-126">TIBCO Rendezvous structured messages are mapped to XML elements in the following way:</span></span>  
  
-   <span data-ttu-id="c00b3-127">**名前**要素名として使用されます。</span><span class="sxs-lookup"><span data-stu-id="c00b3-127">**Name** is used as the element name.</span></span> <span data-ttu-id="c00b3-128">TIBCO Rendezvous のフィールド名には、XML の要素名では使用できない文字でも使用できます。</span><span class="sxs-lookup"><span data-stu-id="c00b3-128">The TIBCO Rendezvous field name may contain characters that are not valid for use in XML element names.</span></span> <span data-ttu-id="c00b3-129">アダプターは、XML と TIBCO Rendezvous 構造化メッセージの間の有効な文字のマッピングを生成します。</span><span class="sxs-lookup"><span data-stu-id="c00b3-129">The adapter generates valid character mappings between XML and TIBCO Rendezvous structured messages.</span></span>  
  
-   <span data-ttu-id="c00b3-130">**識別子**'id' 属性に設定します。</span><span class="sxs-lookup"><span data-stu-id="c00b3-130">**Identifier** is put into an ‘id’ attribute.</span></span>  
  
-   <span data-ttu-id="c00b3-131">**値**要素の本体のある文字列表現が含まれています。</span><span class="sxs-lookup"><span data-stu-id="c00b3-131">**Value** contains a string representation that is the body of the element.</span></span>  
  
-   <span data-ttu-id="c00b3-132">**カウント**は無視されます。</span><span class="sxs-lookup"><span data-stu-id="c00b3-132">**Count** is ignored.</span></span>  
  
-   <span data-ttu-id="c00b3-133">**型**情報は、生成される要素の xsi:type 属性に格納されます。</span><span class="sxs-lookup"><span data-stu-id="c00b3-133">**Type** information is put into an xsi:type attribute for the generated element.</span></span>  
  
     <span data-ttu-id="c00b3-134">詳細については、次を参照してください。 [TIBCO Rendezvous の受信ハンドラーのデータ型マッピング](../core/data-type-mapping-for-receive-handlers-in-tibco-rendezvous.md)です。</span><span class="sxs-lookup"><span data-stu-id="c00b3-134">For more information, see [Data Type Mapping for Receive Handlers in TIBCO Rendezvous](../core/data-type-mapping-for-receive-handlers-in-tibco-rendezvous.md).</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="c00b3-135">参照</span><span class="sxs-lookup"><span data-stu-id="c00b3-135">See Also</span></span>  
 <span data-ttu-id="c00b3-136">[TIBCO Rendezvous の概念](../core/tibco-rendezvous-concepts.md) </span><span class="sxs-lookup"><span data-stu-id="c00b3-136">[TIBCO Rendezvous Concepts](../core/tibco-rendezvous-concepts.md) </span></span>  
 [<span data-ttu-id="c00b3-137">TIBCO Rendezvous 受信ハンドラーの作成</span><span class="sxs-lookup"><span data-stu-id="c00b3-137">Creating TIBCO Rendezvous Receive Handlers</span></span>](../core/creating-tibco-rendezvous-receive-handlers.md)