---
title: TIBCO Rendezvous でのマッピングをメッセージ |Microsoft Docs
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
ms.openlocfilehash: e8d3b287bc1475227231301275500fca32e90da6
ms.sourcegitcommit: 381e83d43796a345488d54b3f7413e11d56ad7be
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 05/07/2019
ms.locfileid: "65326208"
---
# <a name="message-mapping-in-tibco-rendezvous"></a><span data-ttu-id="243fc-103">TIBCO Rendezvous でのメッセージ マッピング</span><span class="sxs-lookup"><span data-stu-id="243fc-103">Message Mapping in TIBCO Rendezvous</span></span>
<span data-ttu-id="243fc-104">TIBCO Rendezvous メッセージはヘッダー情報とメッセージ フィールドのセットで構成されます。</span><span class="sxs-lookup"><span data-stu-id="243fc-104">TIBCO Rendezvous messages are composed of header information and a set of message fields.</span></span> <span data-ttu-id="243fc-105">ヘッダー情報は、メッセージ コンテキスト プロパティに直接マップされます。</span><span class="sxs-lookup"><span data-stu-id="243fc-105">The header information is directly mapped to message context properties.</span></span>  
  
## <a name="message-field-elements"></a><span data-ttu-id="243fc-106">メッセージ フィールドの要素</span><span class="sxs-lookup"><span data-stu-id="243fc-106">Message Field Elements</span></span>  
 <span data-ttu-id="243fc-107">メッセージ フィールドは、次の要素で構成されます。</span><span class="sxs-lookup"><span data-stu-id="243fc-107">A message field is composed of the following elements:</span></span>  
  
|<span data-ttu-id="243fc-108">要素</span><span class="sxs-lookup"><span data-stu-id="243fc-108">Element</span></span>|<span data-ttu-id="243fc-109">説明</span><span class="sxs-lookup"><span data-stu-id="243fc-109">Description</span></span>|  
|-------------|-----------------|  
|<span data-ttu-id="243fc-110">**名前**</span><span class="sxs-lookup"><span data-stu-id="243fc-110">**Name**</span></span>|<span data-ttu-id="243fc-111">文字の文字列。</span><span class="sxs-lookup"><span data-stu-id="243fc-111">Character string.</span></span> <span data-ttu-id="243fc-112">メッセージに一意であることはありません。</span><span class="sxs-lookup"><span data-stu-id="243fc-112">Does not have to be unique in a message.</span></span>|  
|<span data-ttu-id="243fc-113">**[Identifier]**</span><span class="sxs-lookup"><span data-stu-id="243fc-113">**Identifier**</span></span>|<span data-ttu-id="243fc-114">短整数。</span><span class="sxs-lookup"><span data-stu-id="243fc-114">Short integer.</span></span> <span data-ttu-id="243fc-115">メッセージに一意です。</span><span class="sxs-lookup"><span data-stu-id="243fc-115">Unique in a message.</span></span> <span data-ttu-id="243fc-116">暗黙的に 65535 までのメッセージ フィールドの数を制限します。</span><span class="sxs-lookup"><span data-stu-id="243fc-116">Implicitly limits the number of message fields to 65535.</span></span> <span data-ttu-id="243fc-117">識別子のスコープは、メッセージ (またはサブ メッセージ) です。</span><span class="sxs-lookup"><span data-stu-id="243fc-117">The scope of the identifier is the message (or sub message).</span></span> <span data-ttu-id="243fc-118">同じ識別子をそれ自体が 2 つのサブのメッセージで使用できるメッセージに含まれるの一部です。</span><span class="sxs-lookup"><span data-stu-id="243fc-118">The same identifier can be used in two sub-messages, which are themselves part of a containing message.</span></span>|  
|<span data-ttu-id="243fc-119">**[値]**</span><span class="sxs-lookup"><span data-stu-id="243fc-119">**Value**</span></span>|<span data-ttu-id="243fc-120">メッセージ フィールドのデータ。</span><span class="sxs-lookup"><span data-stu-id="243fc-120">The message field data.</span></span>|  
|<span data-ttu-id="243fc-121">**Count**</span><span class="sxs-lookup"><span data-stu-id="243fc-121">**Count**</span></span>|<span data-ttu-id="243fc-122">(配列) の場合は項目の数</span><span class="sxs-lookup"><span data-stu-id="243fc-122">Number of items (in the case of an array)</span></span>|  
|<span data-ttu-id="243fc-123">**型**</span><span class="sxs-lookup"><span data-stu-id="243fc-123">**Type**</span></span>|<span data-ttu-id="243fc-124">メッセージ フィールドの型。</span><span class="sxs-lookup"><span data-stu-id="243fc-124">The type of the message field.</span></span>|  
  
### <a name="mapping-process"></a><span data-ttu-id="243fc-125">マッピング プロセス</span><span class="sxs-lookup"><span data-stu-id="243fc-125">Mapping Process</span></span>  
 <span data-ttu-id="243fc-126">構造化 TIBCO Rendezvous メッセージは、次のように XML 要素にマップされます。</span><span class="sxs-lookup"><span data-stu-id="243fc-126">TIBCO Rendezvous structured messages are mapped to XML elements in the following way:</span></span>  
  
-   <span data-ttu-id="243fc-127">**名前**要素名として使用されます。</span><span class="sxs-lookup"><span data-stu-id="243fc-127">**Name** is used as the element name.</span></span> <span data-ttu-id="243fc-128">TIBCO Rendezvous のフィールド名は、XML 要素名で使用するために無効な文字を含めることができます。</span><span class="sxs-lookup"><span data-stu-id="243fc-128">The TIBCO Rendezvous field name may contain characters that are not valid for use in XML element names.</span></span> <span data-ttu-id="243fc-129">アダプターにより生成される文字の有効な XML と TIBCO Rendezvous 間のマッピングがメッセージを構造化します。</span><span class="sxs-lookup"><span data-stu-id="243fc-129">The adapter generates valid character mappings between XML and TIBCO Rendezvous structured messages.</span></span>  
  
-   <span data-ttu-id="243fc-130">**識別子**'id' 属性に格納されます。</span><span class="sxs-lookup"><span data-stu-id="243fc-130">**Identifier** is put into an ‘id’ attribute.</span></span>  
  
-   <span data-ttu-id="243fc-131">**値**要素の本体である文字列表記を含みます。</span><span class="sxs-lookup"><span data-stu-id="243fc-131">**Value** contains a string representation that is the body of the element.</span></span>  
  
-   <span data-ttu-id="243fc-132">**カウント**は無視されます。</span><span class="sxs-lookup"><span data-stu-id="243fc-132">**Count** is ignored.</span></span>  
  
-   <span data-ttu-id="243fc-133">**型**情報は生成された要素の xsi:type 属性に配置されます。</span><span class="sxs-lookup"><span data-stu-id="243fc-133">**Type** information is put into an xsi:type attribute for the generated element.</span></span>  
  
     <span data-ttu-id="243fc-134">詳細については、次を参照してください。 [Data Type Mapping for TIBCO rendezvous 受信ハンドラー](../core/data-type-mapping-for-receive-handlers-in-tibco-rendezvous.md)します。</span><span class="sxs-lookup"><span data-stu-id="243fc-134">For more information, see [Data Type Mapping for Receive Handlers in TIBCO Rendezvous](../core/data-type-mapping-for-receive-handlers-in-tibco-rendezvous.md).</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="243fc-135">参照</span><span class="sxs-lookup"><span data-stu-id="243fc-135">See Also</span></span>  
 <span data-ttu-id="243fc-136">[TIBCO Rendezvous の概念](../core/tibco-rendezvous-concepts.md) </span><span class="sxs-lookup"><span data-stu-id="243fc-136">[TIBCO Rendezvous Concepts](../core/tibco-rendezvous-concepts.md) </span></span>  
 [<span data-ttu-id="243fc-137">TIBCO Rendezvous 受信ハンドラーの作成</span><span class="sxs-lookup"><span data-stu-id="243fc-137">Creating TIBCO Rendezvous Receive Handlers</span></span>](../core/creating-tibco-rendezvous-receive-handlers.md)