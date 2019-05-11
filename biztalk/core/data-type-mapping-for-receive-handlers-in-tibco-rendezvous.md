---
title: TIBCO Rendezvous から受信するデータ型マッピング |Microsoft Docs
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
ms.openlocfilehash: 37f064021c58e2d870df8e1110a07ce42d0dc9ab
ms.sourcegitcommit: 381e83d43796a345488d54b3f7413e11d56ad7be
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 05/07/2019
ms.locfileid: "65389960"
---
# <a name="data-type-mapping-for-receive-handlers-in-tibco-rendezvous"></a><span data-ttu-id="32289-102">データ型マッピングの TIBCO Rendezvous 受信ハンドラー</span><span class="sxs-lookup"><span data-stu-id="32289-102">Data Type Mapping for Receive Handlers in TIBCO Rendezvous</span></span>
<span data-ttu-id="32289-103">Microsoft BizTalk Adapter for TIBCO Rendezvous は、TIBCO RV の型を次の表で指定された XML スキーマ型にマップします。</span><span class="sxs-lookup"><span data-stu-id="32289-103">Microsoft BizTalk Adapter for TIBCO Rendezvous maps TIBCO RV types to XML Schema types as specified in the following table.</span></span>  
  
## <a name="tibco-rv-to-xml-data-type-mapping"></a><span data-ttu-id="32289-104">TIBCO RV と XML データ型マッピング</span><span class="sxs-lookup"><span data-stu-id="32289-104">TIBCO RV to XML Data Type Mapping</span></span>  
  
|<span data-ttu-id="32289-105">TIBCO RV 型</span><span class="sxs-lookup"><span data-stu-id="32289-105">TIBCO RV Type</span></span>|<span data-ttu-id="32289-106">XML スキーマ型</span><span class="sxs-lookup"><span data-stu-id="32289-106">XML Schema Type</span></span>|<span data-ttu-id="32289-107">コメント</span><span class="sxs-lookup"><span data-stu-id="32289-107">Comments</span></span>|  
|-------------------|---------------------|--------------|  
|<span data-ttu-id="32289-108">TIBRVMSG_MSG</span><span class="sxs-lookup"><span data-stu-id="32289-108">TIBRVMSG_MSG</span></span>|<span data-ttu-id="32289-109">tibrv:message</span><span class="sxs-lookup"><span data-stu-id="32289-109">tibrv:message</span></span>|<span data-ttu-id="32289-110">完全な XML ドキュメントがメッセージ全体から構築します。</span><span class="sxs-lookup"><span data-stu-id="32289-110">Complete XML document constructed from entire message.</span></span>|  
|<span data-ttu-id="32289-111">TIBRVMSG_XML</span><span class="sxs-lookup"><span data-stu-id="32289-111">TIBRVMSG_XML</span></span>|<span data-ttu-id="32289-112">tibrv:rawxml</span><span class="sxs-lookup"><span data-stu-id="32289-112">tibrv:rawxml</span></span>|<span data-ttu-id="32289-113">(アダプターによって解釈されない) バイトの配列から構築された XML ドキュメントです。</span><span class="sxs-lookup"><span data-stu-id="32289-113">XML Document constructed from the array of bytes (not interpreted by the adapter).</span></span>|  
|<span data-ttu-id="32289-114">TIBRVMSG_DATETIME</span><span class="sxs-lookup"><span data-stu-id="32289-114">TIBRVMSG_DATETIME</span></span>|<span data-ttu-id="32289-115">xsd:dateTime</span><span class="sxs-lookup"><span data-stu-id="32289-115">xsd:dateTime</span></span>|<span data-ttu-id="32289-116">アダプターでは、System.Xml.XmlConvert クラスを使用して、XML スキーマ間で変換`dateTime`と`System.DateTime`インスタンス。</span><span class="sxs-lookup"><span data-stu-id="32289-116">The adapter uses the System.Xml.XmlConvert class to convert between XML Schema `dateTime` and `System.DateTime` instances.</span></span>|  
|<span data-ttu-id="32289-117">TIBRVMSG_OPAQUE</span><span class="sxs-lookup"><span data-stu-id="32289-117">TIBRVMSG_OPAQUE</span></span>|<span data-ttu-id="32289-118">xsd:base64Binary</span><span class="sxs-lookup"><span data-stu-id="32289-118">xsd:base64Binary</span></span>||  
|<span data-ttu-id="32289-119">TIBRVMSG_STRING</span><span class="sxs-lookup"><span data-stu-id="32289-119">TIBRVMSG_STRING</span></span>|<span data-ttu-id="32289-120">xsd:string</span><span class="sxs-lookup"><span data-stu-id="32289-120">xsd:string</span></span>||  
|<span data-ttu-id="32289-121">TIBRVMSG_BOOL</span><span class="sxs-lookup"><span data-stu-id="32289-121">TIBRVMSG_BOOL</span></span>|<span data-ttu-id="32289-122">xsd:boolean</span><span class="sxs-lookup"><span data-stu-id="32289-122">xsd:boolean</span></span>||  
|<span data-ttu-id="32289-123">TIBRVMSG_I8</span><span class="sxs-lookup"><span data-stu-id="32289-123">TIBRVMSG_I8</span></span>|<span data-ttu-id="32289-124">xsd:byte</span><span class="sxs-lookup"><span data-stu-id="32289-124">xsd:byte</span></span>||  
|<span data-ttu-id="32289-125">TIBRVMSG_I16</span><span class="sxs-lookup"><span data-stu-id="32289-125">TIBRVMSG_I16</span></span>|<span data-ttu-id="32289-126">xsd:short</span><span class="sxs-lookup"><span data-stu-id="32289-126">xsd:short</span></span>||  
|<span data-ttu-id="32289-127">TIBRVMSG_I32</span><span class="sxs-lookup"><span data-stu-id="32289-127">TIBRVMSG_I32</span></span>|<span data-ttu-id="32289-128">xsd:int</span><span class="sxs-lookup"><span data-stu-id="32289-128">xsd:int</span></span>||  
|<span data-ttu-id="32289-129">TIBRVMSG_I64</span><span class="sxs-lookup"><span data-stu-id="32289-129">TIBRVMSG_I64</span></span>|<span data-ttu-id="32289-130">xsd:long</span><span class="sxs-lookup"><span data-stu-id="32289-130">xsd:long</span></span>||  
|<span data-ttu-id="32289-131">TIBRVMSG_U8</span><span class="sxs-lookup"><span data-stu-id="32289-131">TIBRVMSG_U8</span></span>|<span data-ttu-id="32289-132">xsd:unsignedByte</span><span class="sxs-lookup"><span data-stu-id="32289-132">xsd:unsignedByte</span></span>||  
|<span data-ttu-id="32289-133">TIBRVMSG_U16</span><span class="sxs-lookup"><span data-stu-id="32289-133">TIBRVMSG_U16</span></span>|<span data-ttu-id="32289-134">xsd:unsignedShort</span><span class="sxs-lookup"><span data-stu-id="32289-134">xsd:unsignedShort</span></span>||  
|<span data-ttu-id="32289-135">TIBRVMSG_U32</span><span class="sxs-lookup"><span data-stu-id="32289-135">TIBRVMSG_U32</span></span>|<span data-ttu-id="32289-136">xsd:unsignedInt</span><span class="sxs-lookup"><span data-stu-id="32289-136">xsd:unsignedInt</span></span>||  
|<span data-ttu-id="32289-137">TIBRVMSG_U64</span><span class="sxs-lookup"><span data-stu-id="32289-137">TIBRVMSG_U64</span></span>|<span data-ttu-id="32289-138">xsd:unsignedLong</span><span class="sxs-lookup"><span data-stu-id="32289-138">xsd:unsignedLong</span></span>||  
|<span data-ttu-id="32289-139">TIBRVMSG_F32</span><span class="sxs-lookup"><span data-stu-id="32289-139">TIBRVMSG_F32</span></span>|<span data-ttu-id="32289-140">xsd:float</span><span class="sxs-lookup"><span data-stu-id="32289-140">xsd:float</span></span>||  
|<span data-ttu-id="32289-141">TIBRVMSG_F64</span><span class="sxs-lookup"><span data-stu-id="32289-141">TIBRVMSG_F64</span></span>|<span data-ttu-id="32289-142">xsd:double</span><span class="sxs-lookup"><span data-stu-id="32289-142">xsd:double</span></span>||  
|<span data-ttu-id="32289-143">TIBRVMSG_IPADDR32</span><span class="sxs-lookup"><span data-stu-id="32289-143">TIBRVMSG_IPADDR32</span></span>|<span data-ttu-id="32289-144">tibrv:IPaddress</span><span class="sxs-lookup"><span data-stu-id="32289-144">tibrv:IPaddress</span></span>|<span data-ttu-id="32289-145">`System.Net.IPAddress.ToString( )` 出力の生成に使用されます。</span><span class="sxs-lookup"><span data-stu-id="32289-145">`System.Net.IPAddress.ToString( )` is used to generate the output.</span></span> <span data-ttu-id="32289-146">コンテンツは、ネットワークのバイト順では。</span><span class="sxs-lookup"><span data-stu-id="32289-146">Content is in network byte order.</span></span> <span data-ttu-id="32289-147">ToString() によって処理されます。</span><span class="sxs-lookup"><span data-stu-id="32289-147">ToString() takes care of that.</span></span>|  
|<span data-ttu-id="32289-148">TIBRVMSG_IPPORT16</span><span class="sxs-lookup"><span data-stu-id="32289-148">TIBRVMSG_IPPORT16</span></span>|<span data-ttu-id="32289-149">tibrv:IPport</span><span class="sxs-lookup"><span data-stu-id="32289-149">tibrv:IPport</span></span>|<span data-ttu-id="32289-150">コンテンツがネットワークのバイト順で</span><span class="sxs-lookup"><span data-stu-id="32289-150">Content is in network byte order</span></span>|  
|<span data-ttu-id="32289-151">TIBRVMSG_I8ARRAY</span><span class="sxs-lookup"><span data-stu-id="32289-151">TIBRVMSG_I8ARRAY</span></span>|<span data-ttu-id="32289-152">tibrv:arrayOfByte</span><span class="sxs-lookup"><span data-stu-id="32289-152">tibrv:arrayOfByte</span></span>|<span data-ttu-id="32289-153">アダプター 'によって tibrv' スキーマ名前空間が提供されます。</span><span class="sxs-lookup"><span data-stu-id="32289-153">'tibrv' schema namespace is provided with the adapter.</span></span>|  
|<span data-ttu-id="32289-154">TIBRVMSG_I16ARRAY</span><span class="sxs-lookup"><span data-stu-id="32289-154">TIBRVMSG_I16ARRAY</span></span>|<span data-ttu-id="32289-155">tibrv:arrayOfShort</span><span class="sxs-lookup"><span data-stu-id="32289-155">tibrv:arrayOfShort</span></span>||  
|<span data-ttu-id="32289-156">TIBRVMSG_I32ARRAY</span><span class="sxs-lookup"><span data-stu-id="32289-156">TIBRVMSG_I32ARRAY</span></span>|<span data-ttu-id="32289-157">tibrv:arrayOfInt</span><span class="sxs-lookup"><span data-stu-id="32289-157">tibrv:arrayOfInt</span></span>||  
|<span data-ttu-id="32289-158">TIBRVMSG_I64ARRAY</span><span class="sxs-lookup"><span data-stu-id="32289-158">TIBRVMSG_I64ARRAY</span></span>|<span data-ttu-id="32289-159">tibrv:arrayOfLong</span><span class="sxs-lookup"><span data-stu-id="32289-159">tibrv:arrayOfLong</span></span>||  
|<span data-ttu-id="32289-160">TIBRVMSG_U8ARRAY</span><span class="sxs-lookup"><span data-stu-id="32289-160">TIBRVMSG_U8ARRAY</span></span>|<span data-ttu-id="32289-161">tibrv:arrayOfUnsignedByte</span><span class="sxs-lookup"><span data-stu-id="32289-161">tibrv:arrayOfUnsignedByte</span></span>||  
|<span data-ttu-id="32289-162">TIBRVMSG_U16ARRAY</span><span class="sxs-lookup"><span data-stu-id="32289-162">TIBRVMSG_U16ARRAY</span></span>|<span data-ttu-id="32289-163">tibrv:arrayOfUnsignedShort</span><span class="sxs-lookup"><span data-stu-id="32289-163">tibrv:arrayOfUnsignedShort</span></span>||  
|<span data-ttu-id="32289-164">TIBRVMSG_U32ARRAY</span><span class="sxs-lookup"><span data-stu-id="32289-164">TIBRVMSG_U32ARRAY</span></span>|<span data-ttu-id="32289-165">tibrv:arrayOfUnsignedInt</span><span class="sxs-lookup"><span data-stu-id="32289-165">tibrv:arrayOfUnsignedInt</span></span>||  
|<span data-ttu-id="32289-166">TIBRVMSG_U64ARRAY</span><span class="sxs-lookup"><span data-stu-id="32289-166">TIBRVMSG_U64ARRAY</span></span>|<span data-ttu-id="32289-167">tibrv:arrayOfUnsignedLong</span><span class="sxs-lookup"><span data-stu-id="32289-167">tibrv:arrayOfUnsignedLong</span></span>||  
|<span data-ttu-id="32289-168">TIBRVMSG_F32ARRAY</span><span class="sxs-lookup"><span data-stu-id="32289-168">TIBRVMSG_F32ARRAY</span></span>|<span data-ttu-id="32289-169">tibrv:arrayOfFloat</span><span class="sxs-lookup"><span data-stu-id="32289-169">tibrv:arrayOfFloat</span></span>||  
|<span data-ttu-id="32289-170">TIBRVMSG_F64ARRAY</span><span class="sxs-lookup"><span data-stu-id="32289-170">TIBRVMSG_F64ARRAY</span></span>|<span data-ttu-id="32289-171">tibrv:arrayOfDouble</span><span class="sxs-lookup"><span data-stu-id="32289-171">tibrv:arrayOfDouble</span></span>||  
  
 <span data-ttu-id="32289-172">TIBCO Rendezvous の配列は、同じ名前のフィールドのシーケンスとは異なります。</span><span class="sxs-lookup"><span data-stu-id="32289-172">TIBCO Rendezvous arrays differ from a sequence of fields with the same name.</span></span> <span data-ttu-id="32289-173">たとえば、TIBCO Rendezvous メッセージでは、70,000 の要素を持つ配列を指定することが、70,000 のフィールドには無効です。</span><span class="sxs-lookup"><span data-stu-id="32289-173">For example, in a TIBCO Rendezvous message, it is valid to have an array with 70,000 elements, but it is not valid to have 70,000 fields.</span></span>  
  
 <span data-ttu-id="32289-174">前の表に、配列型のスキーマのようになります。</span><span class="sxs-lookup"><span data-stu-id="32289-174">The schema for the array types in the previous table looks like this:</span></span>  
  
```  
…  
<xsd:complexType name='arrayOfShort'>  
<xsd:sequence>  
<xsd:element name="item" type="xsd:short"/>  
</xsd:sequence>  
</xsd:complexType>  
  
```  
  
 <span data-ttu-id="32289-175">メッセージ内の配列要素のようになります。</span><span class="sxs-lookup"><span data-stu-id="32289-175">An array element in a message looks like this:</span></span>  
  
```  
<someElement xsi:type='tibrv:arrayOfShort'>  
<item>100</item>  
<item>200</item>  
<item>300</item>  
<item>400</item>  
<item>500</item>  
</someElement>  
  
```  
  
 <span data-ttu-id="32289-176">IPaddress のスキーマのようになります。</span><span class="sxs-lookup"><span data-stu-id="32289-176">The schema for the IPaddress looks like this:</span></span>  
  
```  
<xsd:simpleType name='IPaddress'>  
  
 <xsd:restriction base="xs:string">  
   <xsd:minLength value="7" />  
   <xsd:maxLength value="15" />  
  
 </xsd:restriction>  
       </xsd:simpleType>   
</xsd:simpleType>  
  
```  
  
 <span data-ttu-id="32289-177">IPport のスキーマのようになります。</span><span class="sxs-lookup"><span data-stu-id="32289-177">The schema for the IPport looks like this:</span></span>  
  
```  
<xsd:simpleType name='IPport'>  
  
<xsd:restriction base='xsd:ushort'>  
</xsd:simpleType>  
```  
  
## <a name="see-also"></a><span data-ttu-id="32289-178">参照</span><span class="sxs-lookup"><span data-stu-id="32289-178">See Also</span></span>  
 <span data-ttu-id="32289-179">[TIBCO Rendezvous でのメッセージ マッピング](../core/message-mapping-in-tibco-rendezvous.md) </span><span class="sxs-lookup"><span data-stu-id="32289-179">[Message Mapping in TIBCO Rendezvous](../core/message-mapping-in-tibco-rendezvous.md) </span></span>  
 [<span data-ttu-id="32289-180">TIBCO Rendezvous 受信ハンドラーの作成</span><span class="sxs-lookup"><span data-stu-id="32289-180">Creating TIBCO Rendezvous Receive Handlers</span></span>](../core/creating-tibco-rendezvous-receive-handlers.md)