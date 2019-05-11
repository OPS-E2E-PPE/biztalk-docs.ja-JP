---
title: TIBCO Rendezvous のデータ型のマッピングの送信ハンドラーの |Microsoft Docs
ms.custom: ''
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: ''
ms.suite: ''
ms.tgt_pltfrm: ''
ms.topic: article
ms.assetid: fa1a9233-8781-45a8-9c55-a18ecaa0f456
caps.latest.revision: 8
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: 57987751e57353820f243d914da08f2fc57a73c3
ms.sourcegitcommit: 381e83d43796a345488d54b3f7413e11d56ad7be
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 05/07/2019
ms.locfileid: "65352662"
---
# <a name="data-type-mapping-for-send-handlers-in-tibco-rendezvous"></a><span data-ttu-id="6475a-102">TIBCO Rendezvous での送信ハンドラーのデータ型マッピング</span><span class="sxs-lookup"><span data-stu-id="6475a-102">Data Type Mapping for Send Handlers in TIBCO Rendezvous</span></span>
<span data-ttu-id="6475a-103">XML スキーマの種類から TIBCO Rendezvous の型へのマッピングは、TIBCO Rendezvous は、型情報を提供します。 場合にのみ実行可能 (xsi:type =)。</span><span class="sxs-lookup"><span data-stu-id="6475a-103">The mapping from XML schema types to TIBCO Rendezvous types is only possible if TIBCO Rendezvous provides type information (xsi:type=).</span></span> <span data-ttu-id="6475a-104">サポートされていない型は、可能な場合、文字列にマップされます。</span><span class="sxs-lookup"><span data-stu-id="6475a-104">Any unsupported types are mapped to strings if it is possible.</span></span> <span data-ttu-id="6475a-105">マッピングが可能であれば、ない場合、またはポートの構成で、オプションが無効になっている場合は、エラーが生成されます。</span><span class="sxs-lookup"><span data-stu-id="6475a-105">If mapping is not possible, or if the option is disabled in the port configuration, an error is generated.</span></span>  
  
## <a name="xml-schema-to-tibco-rendezvous-data-type-mapping"></a><span data-ttu-id="6475a-106">XML スキーマと TIBCO Rendezvous のデータ型のマッピング</span><span class="sxs-lookup"><span data-stu-id="6475a-106">XML Schema to TIBCO Rendezvous Data Type Mapping</span></span>  
 <span data-ttu-id="6475a-107">次の表では、TIBCO Rendezvous の型を XML スキーマ型から可能なマッピングを示します。</span><span class="sxs-lookup"><span data-stu-id="6475a-107">The following table shows the possible mapping from XML schema types to TIBCO Rendezvous types.</span></span>  
  
|<span data-ttu-id="6475a-108">XML 型</span><span class="sxs-lookup"><span data-stu-id="6475a-108">XML Type</span></span>|<span data-ttu-id="6475a-109">TIBCO RV 型</span><span class="sxs-lookup"><span data-stu-id="6475a-109">TIBCO RV Type</span></span>|  
|--------------|-------------------|  
||<span data-ttu-id="6475a-110">TIBRVMSG_MSG</span><span class="sxs-lookup"><span data-stu-id="6475a-110">TIBRVMSG_MSG</span></span>|  
||<span data-ttu-id="6475a-111">TIBRVMSG_XML</span><span class="sxs-lookup"><span data-stu-id="6475a-111">TIBRVMSG_XML</span></span>|  
|<span data-ttu-id="6475a-112">xsd:dateTime</span><span class="sxs-lookup"><span data-stu-id="6475a-112">xsd:dateTime</span></span>|<span data-ttu-id="6475a-113">TIBRVMSG_DATETIME</span><span class="sxs-lookup"><span data-stu-id="6475a-113">TIBRVMSG_DATETIME</span></span>|  
|<span data-ttu-id="6475a-114">xsd:boolean</span><span class="sxs-lookup"><span data-stu-id="6475a-114">xsd:boolean</span></span>|<span data-ttu-id="6475a-115">TIBRVMSG_BOOL</span><span class="sxs-lookup"><span data-stu-id="6475a-115">TIBRVMSG_BOOL</span></span>|  
|<span data-ttu-id="6475a-116">xsd:byte</span><span class="sxs-lookup"><span data-stu-id="6475a-116">xsd:byte</span></span>|<span data-ttu-id="6475a-117">TIBRVMSG_I8</span><span class="sxs-lookup"><span data-stu-id="6475a-117">TIBRVMSG_I8</span></span>|  
|<span data-ttu-id="6475a-118">xsd:short</span><span class="sxs-lookup"><span data-stu-id="6475a-118">xsd:short</span></span>|<span data-ttu-id="6475a-119">TIBRVMSG_I16</span><span class="sxs-lookup"><span data-stu-id="6475a-119">TIBRVMSG_I16</span></span>|  
|<span data-ttu-id="6475a-120">xsd:int</span><span class="sxs-lookup"><span data-stu-id="6475a-120">xsd:int</span></span>|<span data-ttu-id="6475a-121">TIBRVMSG_I32</span><span class="sxs-lookup"><span data-stu-id="6475a-121">TIBRVMSG_I32</span></span>|  
|<span data-ttu-id="6475a-122">xsd:long</span><span class="sxs-lookup"><span data-stu-id="6475a-122">xsd:long</span></span>|<span data-ttu-id="6475a-123">TIBRVMSG_I64</span><span class="sxs-lookup"><span data-stu-id="6475a-123">TIBRVMSG_I64</span></span>|  
|<span data-ttu-id="6475a-124">xsd:unsignedByte</span><span class="sxs-lookup"><span data-stu-id="6475a-124">xsd:unsignedByte</span></span>|<span data-ttu-id="6475a-125">TIBRVMSG_U8</span><span class="sxs-lookup"><span data-stu-id="6475a-125">TIBRVMSG_U8</span></span>|  
|<span data-ttu-id="6475a-126">xsd:unsignedShort</span><span class="sxs-lookup"><span data-stu-id="6475a-126">xsd:unsignedShort</span></span>|<span data-ttu-id="6475a-127">TIBRVMSG_U16</span><span class="sxs-lookup"><span data-stu-id="6475a-127">TIBRVMSG_U16</span></span>|  
|<span data-ttu-id="6475a-128">xsd:unsignedInt</span><span class="sxs-lookup"><span data-stu-id="6475a-128">xsd:unsignedInt</span></span>|<span data-ttu-id="6475a-129">TIBRVMSG_U32</span><span class="sxs-lookup"><span data-stu-id="6475a-129">TIBRVMSG_U32</span></span>|  
|<span data-ttu-id="6475a-130">xsd:unsignedLong</span><span class="sxs-lookup"><span data-stu-id="6475a-130">xsd:unsignedLong</span></span>|<span data-ttu-id="6475a-131">TIBRVMSG_U64</span><span class="sxs-lookup"><span data-stu-id="6475a-131">TIBRVMSG_U64</span></span>|  
|<span data-ttu-id="6475a-132">xsd:float</span><span class="sxs-lookup"><span data-stu-id="6475a-132">xsd:float</span></span>|<span data-ttu-id="6475a-133">TIBRVMSG_F32</span><span class="sxs-lookup"><span data-stu-id="6475a-133">TIBRVMSG_F32</span></span>|  
|<span data-ttu-id="6475a-134">xsd:double</span><span class="sxs-lookup"><span data-stu-id="6475a-134">xsd:double</span></span>|<span data-ttu-id="6475a-135">TIBRVMSG_F64</span><span class="sxs-lookup"><span data-stu-id="6475a-135">TIBRVMSG_F64</span></span>|  
|<span data-ttu-id="6475a-136">tibrv:IPaddress</span><span class="sxs-lookup"><span data-stu-id="6475a-136">tibrv:IPaddress</span></span>|<span data-ttu-id="6475a-137">TIBRVMSG_IPADDR32</span><span class="sxs-lookup"><span data-stu-id="6475a-137">TIBRVMSG_IPADDR32</span></span>|  
|<span data-ttu-id="6475a-138">tibrv:IPport</span><span class="sxs-lookup"><span data-stu-id="6475a-138">tibrv:IPport</span></span>|<span data-ttu-id="6475a-139">TIBRVMSG_IPPORT16</span><span class="sxs-lookup"><span data-stu-id="6475a-139">TIBRVMSG_IPPORT16</span></span>|  
|<span data-ttu-id="6475a-140">tibrv:arrayOfByte</span><span class="sxs-lookup"><span data-stu-id="6475a-140">tibrv:arrayOfByte</span></span>|<span data-ttu-id="6475a-141">TIBRVMSG_I8ARRAY</span><span class="sxs-lookup"><span data-stu-id="6475a-141">TIBRVMSG_I8ARRAY</span></span>|  
|<span data-ttu-id="6475a-142">tibrv:arrayOfShort</span><span class="sxs-lookup"><span data-stu-id="6475a-142">tibrv:arrayOfShort</span></span>|<span data-ttu-id="6475a-143">TIBRVMSG_I16ARRAY</span><span class="sxs-lookup"><span data-stu-id="6475a-143">TIBRVMSG_I16ARRAY</span></span>|  
|<span data-ttu-id="6475a-144">tibrv:arrayOfInt</span><span class="sxs-lookup"><span data-stu-id="6475a-144">tibrv:arrayOfInt</span></span>|<span data-ttu-id="6475a-145">TIBRVMSG_I32ARRAY</span><span class="sxs-lookup"><span data-stu-id="6475a-145">TIBRVMSG_I32ARRAY</span></span>|  
|<span data-ttu-id="6475a-146">tibrv:arrayOfLong</span><span class="sxs-lookup"><span data-stu-id="6475a-146">tibrv:arrayOfLong</span></span>|<span data-ttu-id="6475a-147">TIBRVMSG_I64ARRAY</span><span class="sxs-lookup"><span data-stu-id="6475a-147">TIBRVMSG_I64ARRAY</span></span>|  
|<span data-ttu-id="6475a-148">tibrv:arrayOfUnsignedByte</span><span class="sxs-lookup"><span data-stu-id="6475a-148">tibrv:arrayOfUnsignedByte</span></span>|<span data-ttu-id="6475a-149">TIBRVMSG_U8ARRAY</span><span class="sxs-lookup"><span data-stu-id="6475a-149">TIBRVMSG_U8ARRAY</span></span>|  
|<span data-ttu-id="6475a-150">tibrv:arrayOfUnsignedShort</span><span class="sxs-lookup"><span data-stu-id="6475a-150">tibrv:arrayOfUnsignedShort</span></span>|<span data-ttu-id="6475a-151">TIBRVMSG_U16ARRAY</span><span class="sxs-lookup"><span data-stu-id="6475a-151">TIBRVMSG_U16ARRAY</span></span>|  
|<span data-ttu-id="6475a-152">tibrv:arrayOfUnsignedInt</span><span class="sxs-lookup"><span data-stu-id="6475a-152">tibrv:arrayOfUnsignedInt</span></span>|<span data-ttu-id="6475a-153">TIBRVMSG_U32ARRAY</span><span class="sxs-lookup"><span data-stu-id="6475a-153">TIBRVMSG_U32ARRAY</span></span>|  
|<span data-ttu-id="6475a-154">tibrv:arrayOfUnsignedLong</span><span class="sxs-lookup"><span data-stu-id="6475a-154">tibrv:arrayOfUnsignedLong</span></span>|<span data-ttu-id="6475a-155">TIBRVMSG_U64ARRAY</span><span class="sxs-lookup"><span data-stu-id="6475a-155">TIBRVMSG_U64ARRAY</span></span>|  
|<span data-ttu-id="6475a-156">tibrv:arrayOfFloat</span><span class="sxs-lookup"><span data-stu-id="6475a-156">tibrv:arrayOfFloat</span></span>|<span data-ttu-id="6475a-157">TIBRVMSG_F32ARRAY</span><span class="sxs-lookup"><span data-stu-id="6475a-157">TIBRVMSG_F32ARRAY</span></span>|  
|<span data-ttu-id="6475a-158">tibrv:arrayOfDouble</span><span class="sxs-lookup"><span data-stu-id="6475a-158">tibrv:arrayOfDouble</span></span>|<span data-ttu-id="6475a-159">TIBRVMSG_F64ARRAY</span><span class="sxs-lookup"><span data-stu-id="6475a-159">TIBRVMSG_F64ARRAY</span></span>|  
|<span data-ttu-id="6475a-160">その他 - デバッグ メッセージあり</span><span class="sxs-lookup"><span data-stu-id="6475a-160">Anything else - with a debug message</span></span>|<span data-ttu-id="6475a-161">TIBRVMSG_STRING ログ。</span><span class="sxs-lookup"><span data-stu-id="6475a-161">TIBRVMSG_STRING the log.</span></span>|  
  
 <span data-ttu-id="6475a-162">BizTalk Adapter for TIBCO Rendezvous は、スキーマへのアクセスがあるない BizTalk Server から TIBCO Rendezvous に送信するときに、ために、XML を指定する必要があります`xsi:type`非文字列フィールドの属性。</span><span class="sxs-lookup"><span data-stu-id="6475a-162">Because BizTalk Adapter for TIBCO Rendezvous does not have access to a schema, when you transmit from BizTalk Server to TIBCO Rendezvous, you must provide the XML `xsi:type` attribute for any non-string field.</span></span> <span data-ttu-id="6475a-163">アダプターでは、その情報を使用して、TIBCO Rendezvous メッセージに適切なメッセージ フィールドの型を生成します。</span><span class="sxs-lookup"><span data-stu-id="6475a-163">The adapter uses that information to generate the appropriate message field type in the TIBCO Rendezvous message.</span></span>  
  
## <a name="message-mapping-example"></a><span data-ttu-id="6475a-164">メッセージ マッピングの例</span><span class="sxs-lookup"><span data-stu-id="6475a-164">Message Mapping Example</span></span>  
 <span data-ttu-id="6475a-165">次の例では、BizTalk Server から TIBCO Rendezvous へのメッセージのマッピングを示します。</span><span class="sxs-lookup"><span data-stu-id="6475a-165">The following example demonstrates mapping a message from BizTalk Server to TIBCO Rendezvous.</span></span> <span data-ttu-id="6475a-166">型をマップする方法については、データ型のマッピング テーブルを参照してください。</span><span class="sxs-lookup"><span data-stu-id="6475a-166">Refer to the data type mapping table for information about how types are mapped.</span></span>  
  
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
  
 <span data-ttu-id="6475a-167">前のメッセージが構造化 TIBCO Rendezvous メッセージとして生成されると、6 つのフィールドの最上位 TibcoMsg インスタンスがあります。</span><span class="sxs-lookup"><span data-stu-id="6475a-167">After the previous message is generated as a structured TIBCO Rendezvous message, it would be a top-level TibcoMsg instance with six fields.</span></span> <span data-ttu-id="6475a-168">最後のフィールドは、配列型の 2 つのフィールドから成る、サブ メッセージ ('item' 要素は TIBCO Rendezvous メッセージ フィールドには、型の 1 つのメッセージ フィールド内の要素にマップされていない`array`)。</span><span class="sxs-lookup"><span data-stu-id="6475a-168">The last fields are a sub-message, composed of two fields of array types (the 'item' elements are not mapped to TIBCO Rendezvous Message fields, but to elements in one Message Field of type `array`).</span></span> <span data-ttu-id="6475a-169">型の指定がない、MarketCap フィールドは、メッセージの文字列フィールドとして送信されます。</span><span class="sxs-lookup"><span data-stu-id="6475a-169">The MarketCap field, having no type specification, would be sent as a string message field.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="6475a-170">参照</span><span class="sxs-lookup"><span data-stu-id="6475a-170">See Also</span></span>  
 [<span data-ttu-id="6475a-171">TIBCO Rendezvous 送信ハンドラーの作成</span><span class="sxs-lookup"><span data-stu-id="6475a-171">Creating TIBCO Rendezvous Send Handlers</span></span>](../core/creating-tibco-rendezvous-send-handlers.md)