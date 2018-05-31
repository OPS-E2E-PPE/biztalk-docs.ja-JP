---
title: TIBCO Rendezvous から受信するデータ型マッピング |Microsoft ドキュメント
ms.custom: ''
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: ''
ms.suite: ''
ms.tgt_pltfrm: ''
ms.topic: article
ms.assetid: 36908a94-3c0d-466e-aa49-f674ba4a26af
caps.latest.revision: 7
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: dcb17ceac0c323bba7a6f25cff0d07473b6d7fa3
ms.sourcegitcommit: dd7c54feab783ae2f8fe75873363fe9ffc77cd66
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 11/07/2017
ms.locfileid: "24014665"
---
# <a name="data-type-mapping-for-receive-handlers-in-tibco-rendezvous"></a><span data-ttu-id="022c1-102">TIBCO Rendezvous の受信ハンドラーのデータ型マッピング</span><span class="sxs-lookup"><span data-stu-id="022c1-102">Data Type Mapping for Receive Handlers in TIBCO Rendezvous</span></span>
<span data-ttu-id="022c1-103">Microsoft BizTalk Adapter for TIBCO Rendezvous は、次の表に示されているように、TIBCO RV の型を XML スキーマの型にマップします。</span><span class="sxs-lookup"><span data-stu-id="022c1-103">Microsoft BizTalk Adapter for TIBCO Rendezvous maps TIBCO RV types to XML Schema types as specified in the following table.</span></span>  
  
## <a name="tibco-rv-to-xml-data-type-mapping"></a><span data-ttu-id="022c1-104">TIBCO RV と XML データ型のマッピング</span><span class="sxs-lookup"><span data-stu-id="022c1-104">TIBCO RV to XML Data Type Mapping</span></span>  
  
|<span data-ttu-id="022c1-105">TIBCO RV 型</span><span class="sxs-lookup"><span data-stu-id="022c1-105">TIBCO RV Type</span></span>|<span data-ttu-id="022c1-106">XML スキーマの型</span><span class="sxs-lookup"><span data-stu-id="022c1-106">XML Schema Type</span></span>|<span data-ttu-id="022c1-107">コメント</span><span class="sxs-lookup"><span data-stu-id="022c1-107">Comments</span></span>|  
|-------------------|---------------------|--------------|  
|<span data-ttu-id="022c1-108">TIBRVMSG_MSG</span><span class="sxs-lookup"><span data-stu-id="022c1-108">TIBRVMSG_MSG</span></span>|<span data-ttu-id="022c1-109">tibrv:message</span><span class="sxs-lookup"><span data-stu-id="022c1-109">tibrv:message</span></span>|<span data-ttu-id="022c1-110">メッセージ全体から構築される完全な XML ドキュメントです。</span><span class="sxs-lookup"><span data-stu-id="022c1-110">Complete XML document constructed from entire message.</span></span>|  
|<span data-ttu-id="022c1-111">TIBRVMSG_XML</span><span class="sxs-lookup"><span data-stu-id="022c1-111">TIBRVMSG_XML</span></span>|<span data-ttu-id="022c1-112">tibrv:rawxml</span><span class="sxs-lookup"><span data-stu-id="022c1-112">tibrv:rawxml</span></span>|<span data-ttu-id="022c1-113">バイトの配列 (アダプターによって解釈されていない) から構築された XML ドキュメントです。</span><span class="sxs-lookup"><span data-stu-id="022c1-113">XML Document constructed from the array of bytes (not interpreted by the adapter).</span></span>|  
|<span data-ttu-id="022c1-114">TIBRVMSG_DATETIME</span><span class="sxs-lookup"><span data-stu-id="022c1-114">TIBRVMSG_DATETIME</span></span>|<span data-ttu-id="022c1-115">xsd:dateTime</span><span class="sxs-lookup"><span data-stu-id="022c1-115">xsd:dateTime</span></span>|<span data-ttu-id="022c1-116">このアダプターは、System.Xml.XmlConvert クラスを使用して、XML スキーマの `dateTime` インスタンスと `System.DateTime` インスタンスとの変換を行います。</span><span class="sxs-lookup"><span data-stu-id="022c1-116">The adapter uses the System.Xml.XmlConvert class to convert between XML Schema `dateTime` and `System.DateTime` instances.</span></span>|  
|<span data-ttu-id="022c1-117">TIBRVMSG_OPAQUE</span><span class="sxs-lookup"><span data-stu-id="022c1-117">TIBRVMSG_OPAQUE</span></span>|<span data-ttu-id="022c1-118">xsd:base64Binary</span><span class="sxs-lookup"><span data-stu-id="022c1-118">xsd:base64Binary</span></span>||  
|<span data-ttu-id="022c1-119">TIBRVMSG_STRING</span><span class="sxs-lookup"><span data-stu-id="022c1-119">TIBRVMSG_STRING</span></span>|<span data-ttu-id="022c1-120">xsd:string</span><span class="sxs-lookup"><span data-stu-id="022c1-120">xsd:string</span></span>||  
|<span data-ttu-id="022c1-121">TIBRVMSG_BOOL</span><span class="sxs-lookup"><span data-stu-id="022c1-121">TIBRVMSG_BOOL</span></span>|<span data-ttu-id="022c1-122">xsd:boolean</span><span class="sxs-lookup"><span data-stu-id="022c1-122">xsd:boolean</span></span>||  
|<span data-ttu-id="022c1-123">TIBRVMSG_I8</span><span class="sxs-lookup"><span data-stu-id="022c1-123">TIBRVMSG_I8</span></span>|<span data-ttu-id="022c1-124">xsd:byte</span><span class="sxs-lookup"><span data-stu-id="022c1-124">xsd:byte</span></span>||  
|<span data-ttu-id="022c1-125">TIBRVMSG_I16</span><span class="sxs-lookup"><span data-stu-id="022c1-125">TIBRVMSG_I16</span></span>|<span data-ttu-id="022c1-126">xsd:short</span><span class="sxs-lookup"><span data-stu-id="022c1-126">xsd:short</span></span>||  
|<span data-ttu-id="022c1-127">TIBRVMSG_I32</span><span class="sxs-lookup"><span data-stu-id="022c1-127">TIBRVMSG_I32</span></span>|<span data-ttu-id="022c1-128">xsd:int</span><span class="sxs-lookup"><span data-stu-id="022c1-128">xsd:int</span></span>||  
|<span data-ttu-id="022c1-129">TIBRVMSG_I64</span><span class="sxs-lookup"><span data-stu-id="022c1-129">TIBRVMSG_I64</span></span>|<span data-ttu-id="022c1-130">xsd:long</span><span class="sxs-lookup"><span data-stu-id="022c1-130">xsd:long</span></span>||  
|<span data-ttu-id="022c1-131">TIBRVMSG_U8</span><span class="sxs-lookup"><span data-stu-id="022c1-131">TIBRVMSG_U8</span></span>|<span data-ttu-id="022c1-132">xsd:unsignedByte</span><span class="sxs-lookup"><span data-stu-id="022c1-132">xsd:unsignedByte</span></span>||  
|<span data-ttu-id="022c1-133">TIBRVMSG_U16</span><span class="sxs-lookup"><span data-stu-id="022c1-133">TIBRVMSG_U16</span></span>|<span data-ttu-id="022c1-134">xsd:unsignedShort</span><span class="sxs-lookup"><span data-stu-id="022c1-134">xsd:unsignedShort</span></span>||  
|<span data-ttu-id="022c1-135">TIBRVMSG_U32</span><span class="sxs-lookup"><span data-stu-id="022c1-135">TIBRVMSG_U32</span></span>|<span data-ttu-id="022c1-136">xsd:unsignedInt</span><span class="sxs-lookup"><span data-stu-id="022c1-136">xsd:unsignedInt</span></span>||  
|<span data-ttu-id="022c1-137">TIBRVMSG_U64</span><span class="sxs-lookup"><span data-stu-id="022c1-137">TIBRVMSG_U64</span></span>|<span data-ttu-id="022c1-138">xsd:unsignedLong</span><span class="sxs-lookup"><span data-stu-id="022c1-138">xsd:unsignedLong</span></span>||  
|<span data-ttu-id="022c1-139">TIBRVMSG_F32</span><span class="sxs-lookup"><span data-stu-id="022c1-139">TIBRVMSG_F32</span></span>|<span data-ttu-id="022c1-140">xsd:float</span><span class="sxs-lookup"><span data-stu-id="022c1-140">xsd:float</span></span>||  
|<span data-ttu-id="022c1-141">TIBRVMSG_F64</span><span class="sxs-lookup"><span data-stu-id="022c1-141">TIBRVMSG_F64</span></span>|<span data-ttu-id="022c1-142">xsd:double</span><span class="sxs-lookup"><span data-stu-id="022c1-142">xsd:double</span></span>||  
|<span data-ttu-id="022c1-143">TIBRVMSG_IPADDR32</span><span class="sxs-lookup"><span data-stu-id="022c1-143">TIBRVMSG_IPADDR32</span></span>|<span data-ttu-id="022c1-144">tibrv:IPaddress</span><span class="sxs-lookup"><span data-stu-id="022c1-144">tibrv:IPaddress</span></span>|<span data-ttu-id="022c1-145">`System.Net.IPAddress.ToString( )` が出力を生成するために使用されます。</span><span class="sxs-lookup"><span data-stu-id="022c1-145">`System.Net.IPAddress.ToString( )` is used to generate the output.</span></span> <span data-ttu-id="022c1-146">内容はネットワークのバイト順になります。</span><span class="sxs-lookup"><span data-stu-id="022c1-146">Content is in network byte order.</span></span> <span data-ttu-id="022c1-147">ToString() によって処理されます。</span><span class="sxs-lookup"><span data-stu-id="022c1-147">ToString() takes care of that.</span></span>|  
|<span data-ttu-id="022c1-148">TIBRVMSG_IPPORT16</span><span class="sxs-lookup"><span data-stu-id="022c1-148">TIBRVMSG_IPPORT16</span></span>|<span data-ttu-id="022c1-149">tibrv:IPport</span><span class="sxs-lookup"><span data-stu-id="022c1-149">tibrv:IPport</span></span>|<span data-ttu-id="022c1-150">コンテンツがネットワークのバイト順で</span><span class="sxs-lookup"><span data-stu-id="022c1-150">Content is in network byte order</span></span>|  
|<span data-ttu-id="022c1-151">TIBRVMSG_I8ARRAY</span><span class="sxs-lookup"><span data-stu-id="022c1-151">TIBRVMSG_I8ARRAY</span></span>|<span data-ttu-id="022c1-152">tibrv:arrayOfByte</span><span class="sxs-lookup"><span data-stu-id="022c1-152">tibrv:arrayOfByte</span></span>|<span data-ttu-id="022c1-153">アダプターによって 'tibrv' スキーマ名前空間が提供されます。</span><span class="sxs-lookup"><span data-stu-id="022c1-153">'tibrv' schema namespace is provided with the adapter.</span></span>|  
|<span data-ttu-id="022c1-154">TIBRVMSG_I16ARRAY</span><span class="sxs-lookup"><span data-stu-id="022c1-154">TIBRVMSG_I16ARRAY</span></span>|<span data-ttu-id="022c1-155">tibrv:arrayOfShort</span><span class="sxs-lookup"><span data-stu-id="022c1-155">tibrv:arrayOfShort</span></span>||  
|<span data-ttu-id="022c1-156">TIBRVMSG_I32ARRAY</span><span class="sxs-lookup"><span data-stu-id="022c1-156">TIBRVMSG_I32ARRAY</span></span>|<span data-ttu-id="022c1-157">tibrv:arrayOfInt</span><span class="sxs-lookup"><span data-stu-id="022c1-157">tibrv:arrayOfInt</span></span>||  
|<span data-ttu-id="022c1-158">TIBRVMSG_I64ARRAY</span><span class="sxs-lookup"><span data-stu-id="022c1-158">TIBRVMSG_I64ARRAY</span></span>|<span data-ttu-id="022c1-159">tibrv:arrayOfLong</span><span class="sxs-lookup"><span data-stu-id="022c1-159">tibrv:arrayOfLong</span></span>||  
|<span data-ttu-id="022c1-160">TIBRVMSG_U8ARRAY</span><span class="sxs-lookup"><span data-stu-id="022c1-160">TIBRVMSG_U8ARRAY</span></span>|<span data-ttu-id="022c1-161">tibrv:arrayOfUnsignedByte</span><span class="sxs-lookup"><span data-stu-id="022c1-161">tibrv:arrayOfUnsignedByte</span></span>||  
|<span data-ttu-id="022c1-162">TIBRVMSG_U16ARRAY</span><span class="sxs-lookup"><span data-stu-id="022c1-162">TIBRVMSG_U16ARRAY</span></span>|<span data-ttu-id="022c1-163">tibrv:arrayOfUnsignedShort</span><span class="sxs-lookup"><span data-stu-id="022c1-163">tibrv:arrayOfUnsignedShort</span></span>||  
|<span data-ttu-id="022c1-164">TIBRVMSG_U32ARRAY</span><span class="sxs-lookup"><span data-stu-id="022c1-164">TIBRVMSG_U32ARRAY</span></span>|<span data-ttu-id="022c1-165">tibrv:arrayOfUnsignedInt</span><span class="sxs-lookup"><span data-stu-id="022c1-165">tibrv:arrayOfUnsignedInt</span></span>||  
|<span data-ttu-id="022c1-166">TIBRVMSG_U64ARRAY</span><span class="sxs-lookup"><span data-stu-id="022c1-166">TIBRVMSG_U64ARRAY</span></span>|<span data-ttu-id="022c1-167">tibrv:arrayOfUnsignedLong</span><span class="sxs-lookup"><span data-stu-id="022c1-167">tibrv:arrayOfUnsignedLong</span></span>||  
|<span data-ttu-id="022c1-168">TIBRVMSG_F32ARRAY</span><span class="sxs-lookup"><span data-stu-id="022c1-168">TIBRVMSG_F32ARRAY</span></span>|<span data-ttu-id="022c1-169">tibrv:arrayOfFloat</span><span class="sxs-lookup"><span data-stu-id="022c1-169">tibrv:arrayOfFloat</span></span>||  
|<span data-ttu-id="022c1-170">TIBRVMSG_F64ARRAY</span><span class="sxs-lookup"><span data-stu-id="022c1-170">TIBRVMSG_F64ARRAY</span></span>|<span data-ttu-id="022c1-171">tibrv:arrayOfDouble</span><span class="sxs-lookup"><span data-stu-id="022c1-171">tibrv:arrayOfDouble</span></span>||  
  
 <span data-ttu-id="022c1-172">TIBCO Rendezvous の配列は、同じ名前のフィールドのシーケンスとは異なります。</span><span class="sxs-lookup"><span data-stu-id="022c1-172">TIBCO Rendezvous arrays differ from a sequence of fields with the same name.</span></span> <span data-ttu-id="022c1-173">たとえば、TIBCO Rendezvous メッセージでは、70,000 の要素を含む配列を持つことは有効ですが、70,000 のフィールドを持つことは有効ではありません。</span><span class="sxs-lookup"><span data-stu-id="022c1-173">For example, in a TIBCO Rendezvous message, it is valid to have an array with 70,000 elements, but it is not valid to have 70,000 fields.</span></span>  
  
 <span data-ttu-id="022c1-174">前の表の配列型のスキーマは次のようになります。</span><span class="sxs-lookup"><span data-stu-id="022c1-174">The schema for the array types in the previous table looks like this:</span></span>  
  
```  
…  
<xsd:complexType name='arrayOfShort'>  
<xsd:sequence>  
<xsd:element name="item" type="xsd:short"/>  
</xsd:sequence>  
</xsd:complexType>  
  
```  
  
 <span data-ttu-id="022c1-175">メッセージ内の配列要素は次のようになります。</span><span class="sxs-lookup"><span data-stu-id="022c1-175">An array element in a message looks like this:</span></span>  
  
```  
<someElement xsi:type='tibrv:arrayOfShort'>  
<item>100</item>  
<item>200</item>  
<item>300</item>  
<item>400</item>  
<item>500</item>  
</someElement>  
  
```  
  
 <span data-ttu-id="022c1-176">IPaddress のスキーマは次のようになります。</span><span class="sxs-lookup"><span data-stu-id="022c1-176">The schema for the IPaddress looks like this:</span></span>  
  
```  
<xsd:simpleType name='IPaddress'>  
  
 <xsd:restriction base="xs:string">  
   <xsd:minLength value="7" />  
   <xsd:maxLength value="15" />  
  
 </xsd:restriction>  
       </xsd:simpleType>   
</xsd:simpleType>  
  
```  
  
 <span data-ttu-id="022c1-177">IPport のスキーマは次のようになります。</span><span class="sxs-lookup"><span data-stu-id="022c1-177">The schema for the IPport looks like this:</span></span>  
  
```  
<xsd:simpleType name='IPport'>  
  
<xsd:restriction base='xsd:ushort'>  
</xsd:simpleType>  
```  
  
## <a name="see-also"></a><span data-ttu-id="022c1-178">参照</span><span class="sxs-lookup"><span data-stu-id="022c1-178">See Also</span></span>  
 <span data-ttu-id="022c1-179">[TIBCO Rendezvous のメッセージ マッピング](../core/message-mapping-in-tibco-rendezvous.md) </span><span class="sxs-lookup"><span data-stu-id="022c1-179">[Message Mapping in TIBCO Rendezvous](../core/message-mapping-in-tibco-rendezvous.md) </span></span>  
 [<span data-ttu-id="022c1-180">TIBCO Rendezvous 受信ハンドラーの作成</span><span class="sxs-lookup"><span data-stu-id="022c1-180">Creating TIBCO Rendezvous Receive Handlers</span></span>](../core/creating-tibco-rendezvous-receive-handlers.md)