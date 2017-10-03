---
title: "TIBCO Rendezvous でのマッピングをメッセージ |Microsoft ドキュメント"
ms.custom: 
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: 
ms.suite: 
ms.tgt_pltfrm: 
ms.topic: article
helpviewer_keywords:
- messages, mapping
- message mapping
- message field elements
ms.assetid: 62793bec-f076-425c-b25e-c4be5bd93cc8
caps.latest.revision: "6"
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: bc5b3559067dbb998240a3fc814d890701e2591c
ms.sourcegitcommit: cb908c540d8f1a692d01dc8f313e16cb4b4e696d
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 09/20/2017
---
# <a name="message-mapping-in-tibco-rendezvous"></a><span data-ttu-id="a3e82-102">TIBCO Rendezvous でのメッセージ マッピング</span><span class="sxs-lookup"><span data-stu-id="a3e82-102">Message Mapping in TIBCO Rendezvous</span></span>
<span data-ttu-id="a3e82-103">TIBCO Rendezvous メッセージは、ヘッダー情報と一連のメッセージ フィールドで構成されています。</span><span class="sxs-lookup"><span data-stu-id="a3e82-103">TIBCO Rendezvous messages are composed of header information and a set of message fields.</span></span> <span data-ttu-id="a3e82-104">ヘッダー情報は、メッセージ コンテキスト プロパティに直接マップされます。</span><span class="sxs-lookup"><span data-stu-id="a3e82-104">The header information is directly mapped to message context properties.</span></span>  
  
## <a name="message-field-elements"></a><span data-ttu-id="a3e82-105">メッセージ フィールドの要素</span><span class="sxs-lookup"><span data-stu-id="a3e82-105">Message Field Elements</span></span>  
 <span data-ttu-id="a3e82-106">メッセージ フィールドは以下の要素で構成されています。</span><span class="sxs-lookup"><span data-stu-id="a3e82-106">A message field is composed of the following elements:</span></span>  
  
|<span data-ttu-id="a3e82-107">要素</span><span class="sxs-lookup"><span data-stu-id="a3e82-107">Element</span></span>|<span data-ttu-id="a3e82-108">Description</span><span class="sxs-lookup"><span data-stu-id="a3e82-108">Description</span></span>|  
|-------------|-----------------|  
|<span data-ttu-id="a3e82-109">**名前**</span><span class="sxs-lookup"><span data-stu-id="a3e82-109">**Name**</span></span>|<span data-ttu-id="a3e82-110">文字の文字列。</span><span class="sxs-lookup"><span data-stu-id="a3e82-110">Character string.</span></span> <span data-ttu-id="a3e82-111">メッセージ内で一意である必要はありません。</span><span class="sxs-lookup"><span data-stu-id="a3e82-111">Does not have to be unique in a message.</span></span>|  
|<span data-ttu-id="a3e82-112">**[Identifier]**</span><span class="sxs-lookup"><span data-stu-id="a3e82-112">**Identifier**</span></span>|<span data-ttu-id="a3e82-113">短整数。</span><span class="sxs-lookup"><span data-stu-id="a3e82-113">Short integer.</span></span> <span data-ttu-id="a3e82-114">メッセージ内で一意です。</span><span class="sxs-lookup"><span data-stu-id="a3e82-114">Unique in a message.</span></span> <span data-ttu-id="a3e82-115">暗黙的に 65535 メッセージ フィールドの数を制限します。</span><span class="sxs-lookup"><span data-stu-id="a3e82-115">Implicitly limits the number of message fields to 65535.</span></span> <span data-ttu-id="a3e82-116">識別子のスコープは、メッセージ (またはサブメッセージ) です。</span><span class="sxs-lookup"><span data-stu-id="a3e82-116">The scope of the identifier is the message (or sub message).</span></span> <span data-ttu-id="a3e82-117">同じメッセージに含まれる 2 つのサブメッセージで、同じ識別子を使用できます。</span><span class="sxs-lookup"><span data-stu-id="a3e82-117">The same identifier can be used in two sub-messages, which are themselves part of a containing message.</span></span>|  
|<span data-ttu-id="a3e82-118">**値**</span><span class="sxs-lookup"><span data-stu-id="a3e82-118">**Value**</span></span>|<span data-ttu-id="a3e82-119">メッセージ フィールドのデータ。</span><span class="sxs-lookup"><span data-stu-id="a3e82-119">The message field data.</span></span>|  
|<span data-ttu-id="a3e82-120">**Count**</span><span class="sxs-lookup"><span data-stu-id="a3e82-120">**Count**</span></span>|<span data-ttu-id="a3e82-121">項目の数 (配列の場合)。</span><span class="sxs-lookup"><span data-stu-id="a3e82-121">Number of items (in the case of an array)</span></span>|  
|<span data-ttu-id="a3e82-122">**型**</span><span class="sxs-lookup"><span data-stu-id="a3e82-122">**Type**</span></span>|<span data-ttu-id="a3e82-123">メッセージ フィールドの種類。</span><span class="sxs-lookup"><span data-stu-id="a3e82-123">The type of the message field.</span></span>|  
  
### <a name="mapping-process"></a><span data-ttu-id="a3e82-124">マッピング プロセス</span><span class="sxs-lookup"><span data-stu-id="a3e82-124">Mapping Process</span></span>  
 <span data-ttu-id="a3e82-125">TIBCO Rendezvous の構造化されたメッセージは、以下のようにして XML 要素にマップされます。</span><span class="sxs-lookup"><span data-stu-id="a3e82-125">TIBCO Rendezvous structured messages are mapped to XML elements in the following way:</span></span>  
  
-   <span data-ttu-id="a3e82-126">**名前**要素名として使用されます。</span><span class="sxs-lookup"><span data-stu-id="a3e82-126">**Name** is used as the element name.</span></span> <span data-ttu-id="a3e82-127">TIBCO Rendezvous のフィールド名には、XML の要素名では使用できない文字でも使用できます。</span><span class="sxs-lookup"><span data-stu-id="a3e82-127">The TIBCO Rendezvous field name may contain characters that are not valid for use in XML element names.</span></span> <span data-ttu-id="a3e82-128">アダプターは、XML と TIBCO Rendezvous 構造化メッセージの間の有効な文字のマッピングを生成します。</span><span class="sxs-lookup"><span data-stu-id="a3e82-128">The adapter generates valid character mappings between XML and TIBCO Rendezvous structured messages.</span></span>  
  
-   <span data-ttu-id="a3e82-129">**識別子**'id' 属性に設定します。</span><span class="sxs-lookup"><span data-stu-id="a3e82-129">**Identifier** is put into an ‘id’ attribute.</span></span>  
  
-   <span data-ttu-id="a3e82-130">**値**要素の本体のある文字列表現が含まれています。</span><span class="sxs-lookup"><span data-stu-id="a3e82-130">**Value** contains a string representation that is the body of the element.</span></span>  
  
-   <span data-ttu-id="a3e82-131">**カウント**は無視されます。</span><span class="sxs-lookup"><span data-stu-id="a3e82-131">**Count** is ignored.</span></span>  
  
-   <span data-ttu-id="a3e82-132">**型**情報は、生成される要素の xsi:type 属性に格納されます。</span><span class="sxs-lookup"><span data-stu-id="a3e82-132">**Type** information is put into an xsi:type attribute for the generated element.</span></span>  
  
     <span data-ttu-id="a3e82-133">詳細については、次を参照してください。 [TIBCO Rendezvous の受信ハンドラーのデータ型マッピング](../core/data-type-mapping-for-receive-handlers-in-tibco-rendezvous.md)です。</span><span class="sxs-lookup"><span data-stu-id="a3e82-133">For more information, see [Data Type Mapping for Receive Handlers in TIBCO Rendezvous](../core/data-type-mapping-for-receive-handlers-in-tibco-rendezvous.md).</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="a3e82-134">参照</span><span class="sxs-lookup"><span data-stu-id="a3e82-134">See Also</span></span>  
 <span data-ttu-id="a3e82-135">[TIBCO Rendezvous の概念](../core/tibco-rendezvous-concepts.md) </span><span class="sxs-lookup"><span data-stu-id="a3e82-135">[TIBCO Rendezvous Concepts](../core/tibco-rendezvous-concepts.md) </span></span>  
 [<span data-ttu-id="a3e82-136">作成元の TIBCO Rendezvous 受信ハンドラー</span><span class="sxs-lookup"><span data-stu-id="a3e82-136">Creating TIBCO Rendezvous Receive Handlers</span></span>](../core/creating-tibco-rendezvous-receive-handlers.md)