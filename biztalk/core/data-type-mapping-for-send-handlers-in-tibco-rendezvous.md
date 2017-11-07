---
title: "TIBCO Rendezvous のデータ型のマッピングの送信ハンドラーの |Microsoft ドキュメント"
ms.custom: 
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: 
ms.suite: 
ms.tgt_pltfrm: 
ms.topic: article
ms.assetid: fa1a9233-8781-45a8-9c55-a18ecaa0f456
caps.latest.revision: "8"
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: bda336d149d373477b26efeb2e4b05de4aac7554
ms.sourcegitcommit: dd7c54feab783ae2f8fe75873363fe9ffc77cd66
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 11/07/2017
---
# <a name="data-type-mapping-for-send-handlers-in-tibco-rendezvous"></a><span data-ttu-id="0f7eb-102">TIBCO Rendezvous での送信ハンドラーのデータ型マッピング</span><span class="sxs-lookup"><span data-stu-id="0f7eb-102">Data Type Mapping for Send Handlers in TIBCO Rendezvous</span></span>
<span data-ttu-id="0f7eb-103">XML スキーマの種類は、TIBCO Rendezvous に型情報 (xsi:type=) が提供されている場合にのみ、TIBCO Rendezvous の型にマップできます。</span><span class="sxs-lookup"><span data-stu-id="0f7eb-103">The mapping from XML schema types to TIBCO Rendezvous types is only possible if TIBCO Rendezvous provides type information (xsi:type=).</span></span> <span data-ttu-id="0f7eb-104">サポートされない型はすべて、可能な場合は、文字列にマップされます。</span><span class="sxs-lookup"><span data-stu-id="0f7eb-104">Any unsupported types are mapped to strings if it is possible.</span></span> <span data-ttu-id="0f7eb-105">マップできない場合、またはポート構成でこのオプションが無効である場合は、エラーが生成されます。</span><span class="sxs-lookup"><span data-stu-id="0f7eb-105">If mapping is not possible, or if the option is disabled in the port configuration, an error is generated.</span></span>  
  
## <a name="xml-schema-to-tibco-rendezvous-data-type-mapping"></a><span data-ttu-id="0f7eb-106">XML スキーマと TIBCO Rendezvous のデータ型マッピング</span><span class="sxs-lookup"><span data-stu-id="0f7eb-106">XML Schema to TIBCO Rendezvous Data Type Mapping</span></span>  
 <span data-ttu-id="0f7eb-107">次の表に、XML スキーマの種類から TIBCO Rendezvous の型への可能なマッピングを示します。</span><span class="sxs-lookup"><span data-stu-id="0f7eb-107">The following table shows the possible mapping from XML schema types to TIBCO Rendezvous types.</span></span>  
  
|<span data-ttu-id="0f7eb-108">XML の種類</span><span class="sxs-lookup"><span data-stu-id="0f7eb-108">XML Type</span></span>|<span data-ttu-id="0f7eb-109">TIBCO RV 型</span><span class="sxs-lookup"><span data-stu-id="0f7eb-109">TIBCO RV Type</span></span>|  
|--------------|-------------------|  
||<span data-ttu-id="0f7eb-110">TIBRVMSG_MSG</span><span class="sxs-lookup"><span data-stu-id="0f7eb-110">TIBRVMSG_MSG</span></span>|  
||<span data-ttu-id="0f7eb-111">TIBRVMSG_XML</span><span class="sxs-lookup"><span data-stu-id="0f7eb-111">TIBRVMSG_XML</span></span>|  
|<span data-ttu-id="0f7eb-112">xsd:dateTime</span><span class="sxs-lookup"><span data-stu-id="0f7eb-112">xsd:dateTime</span></span>|<span data-ttu-id="0f7eb-113">TIBRVMSG_DATETIME</span><span class="sxs-lookup"><span data-stu-id="0f7eb-113">TIBRVMSG_DATETIME</span></span>|  
|<span data-ttu-id="0f7eb-114">xsd:boolean</span><span class="sxs-lookup"><span data-stu-id="0f7eb-114">xsd:boolean</span></span>|<span data-ttu-id="0f7eb-115">TIBRVMSG_BOOL</span><span class="sxs-lookup"><span data-stu-id="0f7eb-115">TIBRVMSG_BOOL</span></span>|  
|<span data-ttu-id="0f7eb-116">xsd:byte</span><span class="sxs-lookup"><span data-stu-id="0f7eb-116">xsd:byte</span></span>|<span data-ttu-id="0f7eb-117">TIBRVMSG_I8</span><span class="sxs-lookup"><span data-stu-id="0f7eb-117">TIBRVMSG_I8</span></span>|  
|<span data-ttu-id="0f7eb-118">xsd:short</span><span class="sxs-lookup"><span data-stu-id="0f7eb-118">xsd:short</span></span>|<span data-ttu-id="0f7eb-119">TIBRVMSG_I16</span><span class="sxs-lookup"><span data-stu-id="0f7eb-119">TIBRVMSG_I16</span></span>|  
|<span data-ttu-id="0f7eb-120">xsd:int</span><span class="sxs-lookup"><span data-stu-id="0f7eb-120">xsd:int</span></span>|<span data-ttu-id="0f7eb-121">TIBRVMSG_I32</span><span class="sxs-lookup"><span data-stu-id="0f7eb-121">TIBRVMSG_I32</span></span>|  
|<span data-ttu-id="0f7eb-122">xsd:long</span><span class="sxs-lookup"><span data-stu-id="0f7eb-122">xsd:long</span></span>|<span data-ttu-id="0f7eb-123">TIBRVMSG_I64</span><span class="sxs-lookup"><span data-stu-id="0f7eb-123">TIBRVMSG_I64</span></span>|  
|<span data-ttu-id="0f7eb-124">xsd:unsignedByte</span><span class="sxs-lookup"><span data-stu-id="0f7eb-124">xsd:unsignedByte</span></span>|<span data-ttu-id="0f7eb-125">TIBRVMSG_U8</span><span class="sxs-lookup"><span data-stu-id="0f7eb-125">TIBRVMSG_U8</span></span>|  
|<span data-ttu-id="0f7eb-126">xsd:unsignedShort</span><span class="sxs-lookup"><span data-stu-id="0f7eb-126">xsd:unsignedShort</span></span>|<span data-ttu-id="0f7eb-127">TIBRVMSG_U16</span><span class="sxs-lookup"><span data-stu-id="0f7eb-127">TIBRVMSG_U16</span></span>|  
|<span data-ttu-id="0f7eb-128">xsd:unsignedInt</span><span class="sxs-lookup"><span data-stu-id="0f7eb-128">xsd:unsignedInt</span></span>|<span data-ttu-id="0f7eb-129">TIBRVMSG_U32</span><span class="sxs-lookup"><span data-stu-id="0f7eb-129">TIBRVMSG_U32</span></span>|  
|<span data-ttu-id="0f7eb-130">xsd:unsignedLong</span><span class="sxs-lookup"><span data-stu-id="0f7eb-130">xsd:unsignedLong</span></span>|<span data-ttu-id="0f7eb-131">TIBRVMSG_U64</span><span class="sxs-lookup"><span data-stu-id="0f7eb-131">TIBRVMSG_U64</span></span>|  
|<span data-ttu-id="0f7eb-132">xsd:float</span><span class="sxs-lookup"><span data-stu-id="0f7eb-132">xsd:float</span></span>|<span data-ttu-id="0f7eb-133">TIBRVMSG_F32</span><span class="sxs-lookup"><span data-stu-id="0f7eb-133">TIBRVMSG_F32</span></span>|  
|<span data-ttu-id="0f7eb-134">xsd:double</span><span class="sxs-lookup"><span data-stu-id="0f7eb-134">xsd:double</span></span>|<span data-ttu-id="0f7eb-135">TIBRVMSG_F64</span><span class="sxs-lookup"><span data-stu-id="0f7eb-135">TIBRVMSG_F64</span></span>|  
|<span data-ttu-id="0f7eb-136">tibrv:IPaddress</span><span class="sxs-lookup"><span data-stu-id="0f7eb-136">tibrv:IPaddress</span></span>|<span data-ttu-id="0f7eb-137">TIBRVMSG_IPADDR32</span><span class="sxs-lookup"><span data-stu-id="0f7eb-137">TIBRVMSG_IPADDR32</span></span>|  
|<span data-ttu-id="0f7eb-138">tibrv:IPport</span><span class="sxs-lookup"><span data-stu-id="0f7eb-138">tibrv:IPport</span></span>|<span data-ttu-id="0f7eb-139">TIBRVMSG_IPPORT16</span><span class="sxs-lookup"><span data-stu-id="0f7eb-139">TIBRVMSG_IPPORT16</span></span>|  
|<span data-ttu-id="0f7eb-140">tibrv:arrayOfByte</span><span class="sxs-lookup"><span data-stu-id="0f7eb-140">tibrv:arrayOfByte</span></span>|<span data-ttu-id="0f7eb-141">TIBRVMSG_I8ARRAY</span><span class="sxs-lookup"><span data-stu-id="0f7eb-141">TIBRVMSG_I8ARRAY</span></span>|  
|<span data-ttu-id="0f7eb-142">tibrv:arrayOfShort</span><span class="sxs-lookup"><span data-stu-id="0f7eb-142">tibrv:arrayOfShort</span></span>|<span data-ttu-id="0f7eb-143">TIBRVMSG_I16ARRAY</span><span class="sxs-lookup"><span data-stu-id="0f7eb-143">TIBRVMSG_I16ARRAY</span></span>|  
|<span data-ttu-id="0f7eb-144">tibrv:arrayOfInt</span><span class="sxs-lookup"><span data-stu-id="0f7eb-144">tibrv:arrayOfInt</span></span>|<span data-ttu-id="0f7eb-145">TIBRVMSG_I32ARRAY</span><span class="sxs-lookup"><span data-stu-id="0f7eb-145">TIBRVMSG_I32ARRAY</span></span>|  
|<span data-ttu-id="0f7eb-146">tibrv:arrayOfLong</span><span class="sxs-lookup"><span data-stu-id="0f7eb-146">tibrv:arrayOfLong</span></span>|<span data-ttu-id="0f7eb-147">TIBRVMSG_I64ARRAY</span><span class="sxs-lookup"><span data-stu-id="0f7eb-147">TIBRVMSG_I64ARRAY</span></span>|  
|<span data-ttu-id="0f7eb-148">tibrv:arrayOfUnsignedByte</span><span class="sxs-lookup"><span data-stu-id="0f7eb-148">tibrv:arrayOfUnsignedByte</span></span>|<span data-ttu-id="0f7eb-149">TIBRVMSG_U8ARRAY</span><span class="sxs-lookup"><span data-stu-id="0f7eb-149">TIBRVMSG_U8ARRAY</span></span>|  
|<span data-ttu-id="0f7eb-150">tibrv:arrayOfUnsignedShort</span><span class="sxs-lookup"><span data-stu-id="0f7eb-150">tibrv:arrayOfUnsignedShort</span></span>|<span data-ttu-id="0f7eb-151">TIBRVMSG_U16ARRAY</span><span class="sxs-lookup"><span data-stu-id="0f7eb-151">TIBRVMSG_U16ARRAY</span></span>|  
|<span data-ttu-id="0f7eb-152">tibrv:arrayOfUnsignedInt</span><span class="sxs-lookup"><span data-stu-id="0f7eb-152">tibrv:arrayOfUnsignedInt</span></span>|<span data-ttu-id="0f7eb-153">TIBRVMSG_U32ARRAY</span><span class="sxs-lookup"><span data-stu-id="0f7eb-153">TIBRVMSG_U32ARRAY</span></span>|  
|<span data-ttu-id="0f7eb-154">tibrv:arrayOfUnsignedLong</span><span class="sxs-lookup"><span data-stu-id="0f7eb-154">tibrv:arrayOfUnsignedLong</span></span>|<span data-ttu-id="0f7eb-155">TIBRVMSG_U64ARRAY</span><span class="sxs-lookup"><span data-stu-id="0f7eb-155">TIBRVMSG_U64ARRAY</span></span>|  
|<span data-ttu-id="0f7eb-156">tibrv:arrayOfFloat</span><span class="sxs-lookup"><span data-stu-id="0f7eb-156">tibrv:arrayOfFloat</span></span>|<span data-ttu-id="0f7eb-157">TIBRVMSG_F32ARRAY</span><span class="sxs-lookup"><span data-stu-id="0f7eb-157">TIBRVMSG_F32ARRAY</span></span>|  
|<span data-ttu-id="0f7eb-158">tibrv:arrayOfDouble</span><span class="sxs-lookup"><span data-stu-id="0f7eb-158">tibrv:arrayOfDouble</span></span>|<span data-ttu-id="0f7eb-159">TIBRVMSG_F64ARRAY</span><span class="sxs-lookup"><span data-stu-id="0f7eb-159">TIBRVMSG_F64ARRAY</span></span>|  
|<span data-ttu-id="0f7eb-160">その他 - デバッグ メッセージあり</span><span class="sxs-lookup"><span data-stu-id="0f7eb-160">Anything else - with a debug message</span></span>|<span data-ttu-id="0f7eb-161">TIBRVMSG_STRING (ログ)</span><span class="sxs-lookup"><span data-stu-id="0f7eb-161">TIBRVMSG_STRING the log.</span></span>|  
  
 <span data-ttu-id="0f7eb-162">BizTalk Adapter for TIBCO Rendezvous はスキーマにアクセスできないので、BizTalk Server から TIBCO Rendezvous に送信する場合は、すべての非文字列フィールドについて XML `xsi:type` 属性を提供する必要があります。</span><span class="sxs-lookup"><span data-stu-id="0f7eb-162">Because BizTalk Adapter for TIBCO Rendezvous does not have access to a schema, when you transmit from BizTalk Server to TIBCO Rendezvous, you must provide the XML `xsi:type` attribute for any non-string field.</span></span> <span data-ttu-id="0f7eb-163">アダプターはこの情報を使用して、TIBCO Rendezvous メッセージに、適切なメッセージ フィールドの型を生成します。</span><span class="sxs-lookup"><span data-stu-id="0f7eb-163">The adapter uses that information to generate the appropriate message field type in the TIBCO Rendezvous message.</span></span>  
  
## <a name="message-mapping-example"></a><span data-ttu-id="0f7eb-164">メッセージ マッピングの例</span><span class="sxs-lookup"><span data-stu-id="0f7eb-164">Message Mapping Example</span></span>  
 <span data-ttu-id="0f7eb-165">次に、BizTalk Server から TIBCO Rendezvous へのメッセージ マッピングの例を示します。</span><span class="sxs-lookup"><span data-stu-id="0f7eb-165">The following example demonstrates mapping a message from BizTalk Server to TIBCO Rendezvous.</span></span> <span data-ttu-id="0f7eb-166">型のマップ方法の詳細は、データ型マッピングの表を参照してください。</span><span class="sxs-lookup"><span data-stu-id="0f7eb-166">Refer to the data type mapping table for information about how types are mapped.</span></span>  
  
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
  
 <span data-ttu-id="0f7eb-167">前のメッセージが構造化された TIBCO Rendezvous メッセージとして生成されると、6 つのフィールドがある最上位 TibcoMsg インスタンスになります。</span><span class="sxs-lookup"><span data-stu-id="0f7eb-167">After the previous message is generated as a structured TIBCO Rendezvous message, it would be a top-level TibcoMsg instance with six fields.</span></span> <span data-ttu-id="0f7eb-168">最後のフィールドは、配列型の 2 つのフィールドで構成されるサブメッセージです (アイテム要素は TIBCO Rendezvous メッセージ フィールドにはマップされず、`array` 型のメッセージ フィールドの要素としてマップされます)。</span><span class="sxs-lookup"><span data-stu-id="0f7eb-168">The last fields are a sub-message, composed of two fields of array types (the 'item' elements are not mapped to TIBCO Rendezvous Message fields, but to elements in one Message Field of type `array`).</span></span> <span data-ttu-id="0f7eb-169">型の仕様を持たない、MarketCap フィールドは文字列フィールドのメッセージとして送信されます。</span><span class="sxs-lookup"><span data-stu-id="0f7eb-169">The MarketCap field, having no type specification, would be sent as a string message field.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="0f7eb-170">参照</span><span class="sxs-lookup"><span data-stu-id="0f7eb-170">See Also</span></span>  
 [<span data-ttu-id="0f7eb-171">TIBCO Rendezvous 送信ハンドラーの作成</span><span class="sxs-lookup"><span data-stu-id="0f7eb-171">Creating TIBCO Rendezvous Send Handlers</span></span>](../core/creating-tibco-rendezvous-send-handlers.md)