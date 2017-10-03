---
title: "TIBCO Rendezvous のデータ型のマッピングの送信ハンドラーの |Microsoft ドキュメント"
ms.custom: 
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: 
ms.suite: 
ms.tgt_pltfrm: 
ms.topic: article
helpviewer_keywords:
- XML schemas, mapping to Redevous types
- message mapping, examples
- XML schemas, schema types
- data type mapping, send handlers
- examples, message mapping
- send handlers, data type mapping
ms.assetid: fa1a9233-8781-45a8-9c55-a18ecaa0f456
caps.latest.revision: "8"
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: b6c54cb7ae684aa2f617ca615ed55703e331de46
ms.sourcegitcommit: cb908c540d8f1a692d01dc8f313e16cb4b4e696d
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 09/20/2017
---
# <a name="data-type-mapping-for-send-handlers-in-tibco-rendezvous"></a><span data-ttu-id="b956b-102">TIBCO Rendezvous での送信ハンドラーのデータ型マッピング</span><span class="sxs-lookup"><span data-stu-id="b956b-102">Data Type Mapping for Send Handlers in TIBCO Rendezvous</span></span>
<span data-ttu-id="b956b-103">XML スキーマの種類は、TIBCO Rendezvous に型情報 (xsi:type=) が提供されている場合にのみ、TIBCO Rendezvous の型にマップできます。</span><span class="sxs-lookup"><span data-stu-id="b956b-103">The mapping from XML schema types to TIBCO Rendezvous types is only possible if TIBCO Rendezvous provides type information (xsi:type=).</span></span> <span data-ttu-id="b956b-104">サポートされない型はすべて、可能な場合は、文字列にマップされます。</span><span class="sxs-lookup"><span data-stu-id="b956b-104">Any unsupported types are mapped to strings if it is possible.</span></span> <span data-ttu-id="b956b-105">マップできない場合、またはポート構成でこのオプションが無効である場合は、エラーが生成されます。</span><span class="sxs-lookup"><span data-stu-id="b956b-105">If mapping is not possible, or if the option is disabled in the port configuration, an error is generated.</span></span>  
  
## <a name="xml-schema-to-tibco-rendezvous-data-type-mapping"></a><span data-ttu-id="b956b-106">XML スキーマと TIBCO Rendezvous のデータ型マッピング</span><span class="sxs-lookup"><span data-stu-id="b956b-106">XML Schema to TIBCO Rendezvous Data Type Mapping</span></span>  
 <span data-ttu-id="b956b-107">次の表に、XML スキーマの種類から TIBCO Rendezvous の型への可能なマッピングを示します。</span><span class="sxs-lookup"><span data-stu-id="b956b-107">The following table shows the possible mapping from XML schema types to TIBCO Rendezvous types.</span></span>  
  
|<span data-ttu-id="b956b-108">XML の種類</span><span class="sxs-lookup"><span data-stu-id="b956b-108">XML Type</span></span>|<span data-ttu-id="b956b-109">TIBCO RV 型</span><span class="sxs-lookup"><span data-stu-id="b956b-109">TIBCO RV Type</span></span>|  
|--------------|-------------------|  
||<span data-ttu-id="b956b-110">TIBRVMSG_MSG</span><span class="sxs-lookup"><span data-stu-id="b956b-110">TIBRVMSG_MSG</span></span>|  
||<span data-ttu-id="b956b-111">TIBRVMSG_XML</span><span class="sxs-lookup"><span data-stu-id="b956b-111">TIBRVMSG_XML</span></span>|  
|<span data-ttu-id="b956b-112">xsd:dateTime</span><span class="sxs-lookup"><span data-stu-id="b956b-112">xsd:dateTime</span></span>|<span data-ttu-id="b956b-113">TIBRVMSG_DATETIME</span><span class="sxs-lookup"><span data-stu-id="b956b-113">TIBRVMSG_DATETIME</span></span>|  
|<span data-ttu-id="b956b-114">xsd:boolean</span><span class="sxs-lookup"><span data-stu-id="b956b-114">xsd:boolean</span></span>|<span data-ttu-id="b956b-115">TIBRVMSG_BOOL</span><span class="sxs-lookup"><span data-stu-id="b956b-115">TIBRVMSG_BOOL</span></span>|  
|<span data-ttu-id="b956b-116">xsd:byte</span><span class="sxs-lookup"><span data-stu-id="b956b-116">xsd:byte</span></span>|<span data-ttu-id="b956b-117">TIBRVMSG_I8</span><span class="sxs-lookup"><span data-stu-id="b956b-117">TIBRVMSG_I8</span></span>|  
|<span data-ttu-id="b956b-118">xsd:short</span><span class="sxs-lookup"><span data-stu-id="b956b-118">xsd:short</span></span>|<span data-ttu-id="b956b-119">TIBRVMSG_I16</span><span class="sxs-lookup"><span data-stu-id="b956b-119">TIBRVMSG_I16</span></span>|  
|<span data-ttu-id="b956b-120">xsd:int</span><span class="sxs-lookup"><span data-stu-id="b956b-120">xsd:int</span></span>|<span data-ttu-id="b956b-121">TIBRVMSG_I32</span><span class="sxs-lookup"><span data-stu-id="b956b-121">TIBRVMSG_I32</span></span>|  
|<span data-ttu-id="b956b-122">xsd:long</span><span class="sxs-lookup"><span data-stu-id="b956b-122">xsd:long</span></span>|<span data-ttu-id="b956b-123">TIBRVMSG_I64</span><span class="sxs-lookup"><span data-stu-id="b956b-123">TIBRVMSG_I64</span></span>|  
|<span data-ttu-id="b956b-124">xsd:unsignedByte</span><span class="sxs-lookup"><span data-stu-id="b956b-124">xsd:unsignedByte</span></span>|<span data-ttu-id="b956b-125">TIBRVMSG_U8</span><span class="sxs-lookup"><span data-stu-id="b956b-125">TIBRVMSG_U8</span></span>|  
|<span data-ttu-id="b956b-126">xsd:unsignedShort</span><span class="sxs-lookup"><span data-stu-id="b956b-126">xsd:unsignedShort</span></span>|<span data-ttu-id="b956b-127">TIBRVMSG_U16</span><span class="sxs-lookup"><span data-stu-id="b956b-127">TIBRVMSG_U16</span></span>|  
|<span data-ttu-id="b956b-128">xsd:unsignedInt</span><span class="sxs-lookup"><span data-stu-id="b956b-128">xsd:unsignedInt</span></span>|<span data-ttu-id="b956b-129">TIBRVMSG_U32</span><span class="sxs-lookup"><span data-stu-id="b956b-129">TIBRVMSG_U32</span></span>|  
|<span data-ttu-id="b956b-130">xsd:unsignedLong</span><span class="sxs-lookup"><span data-stu-id="b956b-130">xsd:unsignedLong</span></span>|<span data-ttu-id="b956b-131">TIBRVMSG_U64</span><span class="sxs-lookup"><span data-stu-id="b956b-131">TIBRVMSG_U64</span></span>|  
|<span data-ttu-id="b956b-132">xsd:float</span><span class="sxs-lookup"><span data-stu-id="b956b-132">xsd:float</span></span>|<span data-ttu-id="b956b-133">TIBRVMSG_F32</span><span class="sxs-lookup"><span data-stu-id="b956b-133">TIBRVMSG_F32</span></span>|  
|<span data-ttu-id="b956b-134">xsd:double</span><span class="sxs-lookup"><span data-stu-id="b956b-134">xsd:double</span></span>|<span data-ttu-id="b956b-135">TIBRVMSG_F64</span><span class="sxs-lookup"><span data-stu-id="b956b-135">TIBRVMSG_F64</span></span>|  
|<span data-ttu-id="b956b-136">tibrv:IPaddress</span><span class="sxs-lookup"><span data-stu-id="b956b-136">tibrv:IPaddress</span></span>|<span data-ttu-id="b956b-137">TIBRVMSG_IPADDR32</span><span class="sxs-lookup"><span data-stu-id="b956b-137">TIBRVMSG_IPADDR32</span></span>|  
|<span data-ttu-id="b956b-138">tibrv:IPport</span><span class="sxs-lookup"><span data-stu-id="b956b-138">tibrv:IPport</span></span>|<span data-ttu-id="b956b-139">TIBRVMSG_IPPORT16</span><span class="sxs-lookup"><span data-stu-id="b956b-139">TIBRVMSG_IPPORT16</span></span>|  
|<span data-ttu-id="b956b-140">tibrv:arrayOfByte</span><span class="sxs-lookup"><span data-stu-id="b956b-140">tibrv:arrayOfByte</span></span>|<span data-ttu-id="b956b-141">TIBRVMSG_I8ARRAY</span><span class="sxs-lookup"><span data-stu-id="b956b-141">TIBRVMSG_I8ARRAY</span></span>|  
|<span data-ttu-id="b956b-142">tibrv:arrayOfShort</span><span class="sxs-lookup"><span data-stu-id="b956b-142">tibrv:arrayOfShort</span></span>|<span data-ttu-id="b956b-143">TIBRVMSG_I16ARRAY</span><span class="sxs-lookup"><span data-stu-id="b956b-143">TIBRVMSG_I16ARRAY</span></span>|  
|<span data-ttu-id="b956b-144">tibrv:arrayOfInt</span><span class="sxs-lookup"><span data-stu-id="b956b-144">tibrv:arrayOfInt</span></span>|<span data-ttu-id="b956b-145">TIBRVMSG_I32ARRAY</span><span class="sxs-lookup"><span data-stu-id="b956b-145">TIBRVMSG_I32ARRAY</span></span>|  
|<span data-ttu-id="b956b-146">tibrv:arrayOfLong</span><span class="sxs-lookup"><span data-stu-id="b956b-146">tibrv:arrayOfLong</span></span>|<span data-ttu-id="b956b-147">TIBRVMSG_I64ARRAY</span><span class="sxs-lookup"><span data-stu-id="b956b-147">TIBRVMSG_I64ARRAY</span></span>|  
|<span data-ttu-id="b956b-148">tibrv:arrayOfUnsignedByte</span><span class="sxs-lookup"><span data-stu-id="b956b-148">tibrv:arrayOfUnsignedByte</span></span>|<span data-ttu-id="b956b-149">TIBRVMSG_U8ARRAY</span><span class="sxs-lookup"><span data-stu-id="b956b-149">TIBRVMSG_U8ARRAY</span></span>|  
|<span data-ttu-id="b956b-150">tibrv:arrayOfUnsignedShort</span><span class="sxs-lookup"><span data-stu-id="b956b-150">tibrv:arrayOfUnsignedShort</span></span>|<span data-ttu-id="b956b-151">TIBRVMSG_U16ARRAY</span><span class="sxs-lookup"><span data-stu-id="b956b-151">TIBRVMSG_U16ARRAY</span></span>|  
|<span data-ttu-id="b956b-152">tibrv:arrayOfUnsignedInt</span><span class="sxs-lookup"><span data-stu-id="b956b-152">tibrv:arrayOfUnsignedInt</span></span>|<span data-ttu-id="b956b-153">TIBRVMSG_U32ARRAY</span><span class="sxs-lookup"><span data-stu-id="b956b-153">TIBRVMSG_U32ARRAY</span></span>|  
|<span data-ttu-id="b956b-154">tibrv:arrayOfUnsignedLong</span><span class="sxs-lookup"><span data-stu-id="b956b-154">tibrv:arrayOfUnsignedLong</span></span>|<span data-ttu-id="b956b-155">TIBRVMSG_U64ARRAY</span><span class="sxs-lookup"><span data-stu-id="b956b-155">TIBRVMSG_U64ARRAY</span></span>|  
|<span data-ttu-id="b956b-156">tibrv:arrayOfFloat</span><span class="sxs-lookup"><span data-stu-id="b956b-156">tibrv:arrayOfFloat</span></span>|<span data-ttu-id="b956b-157">TIBRVMSG_F32ARRAY</span><span class="sxs-lookup"><span data-stu-id="b956b-157">TIBRVMSG_F32ARRAY</span></span>|  
|<span data-ttu-id="b956b-158">tibrv:arrayOfDouble</span><span class="sxs-lookup"><span data-stu-id="b956b-158">tibrv:arrayOfDouble</span></span>|<span data-ttu-id="b956b-159">TIBRVMSG_F64ARRAY</span><span class="sxs-lookup"><span data-stu-id="b956b-159">TIBRVMSG_F64ARRAY</span></span>|  
|<span data-ttu-id="b956b-160">その他 - デバッグ メッセージあり</span><span class="sxs-lookup"><span data-stu-id="b956b-160">Anything else - with a debug message</span></span>|<span data-ttu-id="b956b-161">TIBRVMSG_STRING (ログ)</span><span class="sxs-lookup"><span data-stu-id="b956b-161">TIBRVMSG_STRING the log.</span></span>|  
  
 <span data-ttu-id="b956b-162">BizTalk Adapter for TIBCO Rendezvous はスキーマにアクセスできないので、BizTalk Server から TIBCO Rendezvous に送信する場合は、すべての非文字列フィールドについて XML `xsi:type` 属性を提供する必要があります。</span><span class="sxs-lookup"><span data-stu-id="b956b-162">Because BizTalk Adapter for TIBCO Rendezvous does not have access to a schema, when you transmit from BizTalk Server to TIBCO Rendezvous, you must provide the XML `xsi:type` attribute for any non-string field.</span></span> <span data-ttu-id="b956b-163">アダプターはこの情報を使用して、TIBCO Rendezvous メッセージに、適切なメッセージ フィールドの型を生成します。</span><span class="sxs-lookup"><span data-stu-id="b956b-163">The adapter uses that information to generate the appropriate message field type in the TIBCO Rendezvous message.</span></span>  
  
## <a name="message-mapping-example"></a><span data-ttu-id="b956b-164">メッセージ マッピングの例</span><span class="sxs-lookup"><span data-stu-id="b956b-164">Message Mapping Example</span></span>  
 <span data-ttu-id="b956b-165">次に、BizTalk Server から TIBCO Rendezvous へのメッセージ マッピングの例を示します。</span><span class="sxs-lookup"><span data-stu-id="b956b-165">The following example demonstrates mapping a message from BizTalk Server to TIBCO Rendezvous.</span></span> <span data-ttu-id="b956b-166">型のマップ方法の詳細は、データ型マッピングの表を参照してください。</span><span class="sxs-lookup"><span data-stu-id="b956b-166">Refer to the data type mapping table for information about how types are mapped.</span></span>  
  
```  
<ns:QuoteUpdate xmlns:xsi http://www.w3.org/2001/XMLSchema-instance"  
xmlns:xsd http://www.w3.org/2001/XMLSchema"  
xmlns:tibrv="http://schemas.microsoft.com/TibcoRendezvous/Types"  
xmlns:ns="some namespace for this message [value not important, unless the schema is also used for receive ports]">  
  
<ns:SymbolName id=1 xsi:type="xsd:string">MSFT</ns:SymbolName>  
  
<ns:LastTrade id=2 xsi:type="xsd:double">28.40</ns:LastTrade>   
<ns:DayLow id=3 xsi:type="xsd:double">28.25</ns:DayLow>  
  
```  
  
|||  
|-|-|  
|`<ns:DayHigh`|`id=4 xsi:type="xsd:double">28.40</ns:DayHigh>`|  
|`<ns:MarketCap`|`id=10>262575234981</ns:MarketCap>`|  
|`<ns:Bids`|`id=100 xsi:type="tibrv:message">`|  
  
```  
<ns:TopBids id=1 xsi:type="tibrv:arrayOfDouble">  
<item>28.40</item>  
<item>28.39</item>  
<item>28.39</item>  
<item>28.39</item>  
<item>28.38</item>  
  
</ns:TopBids>  
  
<ns:BidsSize id=2 xsi:type="tibrv:arrayOfLong">  
<item>500</item>  
<item>1000</item>  
<item>100</item>  
<item>100</item>  
<item>2000</item>  
  
</ns:BidsSize>  
</ns:Bids>  
</ns:QuoteUpdate>  
  
```  
  
 <span data-ttu-id="b956b-167">前のメッセージが構造化された TIBCO Rendezvous メッセージとして生成されると、6 つのフィールドがある最上位 TibcoMsg インスタンスになります。</span><span class="sxs-lookup"><span data-stu-id="b956b-167">After the previous message is generated as a structured TIBCO Rendezvous message, it would be a top-level TibcoMsg instance with six fields.</span></span> <span data-ttu-id="b956b-168">最後のフィールドは、配列型の 2 つのフィールドで構成されるサブメッセージです (アイテム要素は TIBCO Rendezvous メッセージ フィールドにはマップされず、`array` 型のメッセージ フィールドの要素としてマップされます)。</span><span class="sxs-lookup"><span data-stu-id="b956b-168">The last fields are a sub-message, composed of two fields of array types (the 'item' elements are not mapped to TIBCO Rendezvous Message fields, but to elements in one Message Field of type `array`).</span></span> <span data-ttu-id="b956b-169">型の仕様を持たない、MarketCap フィールドは文字列フィールドのメッセージとして送信されます。</span><span class="sxs-lookup"><span data-stu-id="b956b-169">The MarketCap field, having no type specification, would be sent as a string message field.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="b956b-170">参照</span><span class="sxs-lookup"><span data-stu-id="b956b-170">See Also</span></span>  
 [<span data-ttu-id="b956b-171">TIBCO Rendezvous 送信ハンドラーを作成します。</span><span class="sxs-lookup"><span data-stu-id="b956b-171">Creating TIBCO Rendezvous Send Handlers</span></span>](../core/creating-tibco-rendezvous-send-handlers.md)