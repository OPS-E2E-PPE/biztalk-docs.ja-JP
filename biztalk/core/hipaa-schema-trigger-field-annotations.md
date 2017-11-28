---
title: "HIPAA スキーマのトリガー フィールドの注釈 |Microsoft ドキュメント"
ms.custom: 
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: 
ms.suite: 
ms.tgt_pltfrm: 
ms.topic: article
ms.assetid: e1389284-a2ec-44e7-a2f1-8d26f83fd31d
caps.latest.revision: "8"
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: 9d3bf6d53ec95ebfc57cff646ce5658fc6b1f4a2
ms.sourcegitcommit: cb908c540d8f1a692d01dc8f313e16cb4b4e696d
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 09/20/2017
---
# <a name="hipaa-schema-trigger-field-annotations"></a><span data-ttu-id="d0b82-102">HIPAA スキーマのトリガー フィールドの注釈</span><span class="sxs-lookup"><span data-stu-id="d0b82-102">HIPAA Schema Trigger Field Annotations</span></span>
<span data-ttu-id="d0b82-103">多くの場合、EDI セグメントには、セグメントの意味を変更する修飾子の値が含まれています。</span><span class="sxs-lookup"><span data-stu-id="d0b82-103">EDI segments often contain qualifier values that modify the meaning of the segment.</span></span> <span data-ttu-id="d0b82-104">たとえば、N1 セグメントには "請求先名" を示す "BT" の修飾要素が含まれていたり、"出荷先名" を示す "ST" の修飾要素が含まれていることがあります。</span><span class="sxs-lookup"><span data-stu-id="d0b82-104">For example, an N1 segment can contain a qualifying element of “BT” to signify a “bill-to name,” or it may contain a qualifying element of “ST” to indicate a “ship-to name.”</span></span> <span data-ttu-id="d0b82-105">通常、これらのフィールドを解釈する方法はビジネス ロジックに任されており、逆アセンブラーでは N1 セグメントのすべてのインスタンスを同じ XML レコード名に解決します。しかし、[!INCLUDE[btsBizTalkServer2006r3](../includes/btsbiztalkserver2006r3-md.md)] 付属の HIPAA スキーマに含まれている注釈を使用すると、逆アセンブラーで修飾要素の存在に基づいて一意の XML レコードを作成できます。</span><span class="sxs-lookup"><span data-stu-id="d0b82-105">Normally it is left to business logic to determine how to interpret these fields and the disassembler resolves all instances of the N1 segment to the same XML record name; however, the HIPAA schemas shipped with [!INCLUDE[btsBizTalkServer2006r3](../includes/btsbiztalkserver2006r3-md.md)] contain annotations that allow the EDI disassembler to create unique XML records based on the presence of a qualifying element.</span></span>  
  
 <span data-ttu-id="d0b82-106">**トリガー フィールドの実装**</span><span class="sxs-lookup"><span data-stu-id="d0b82-106">**Trigger Field Implementation**</span></span>  
  
 <span data-ttu-id="d0b82-107">トリガー フィールドは、セグメントの要素およびこのレコードの作成の起因となるトリガー値を説明する、ペアの XML 属性として実装されています。</span><span class="sxs-lookup"><span data-stu-id="d0b82-107">Trigger fields are implemented as a pair of XML attributes that describe the segment element and the trigger value that causes this record to be created.</span></span> <span data-ttu-id="d0b82-108">次の表は、これらの属性の説明です。</span><span class="sxs-lookup"><span data-stu-id="d0b82-108">The following table describes these attributes:</span></span>  
  
|<span data-ttu-id="d0b82-109">属性</span><span class="sxs-lookup"><span data-stu-id="d0b82-109">Attribute</span></span>|<span data-ttu-id="d0b82-110">用途</span><span class="sxs-lookup"><span data-stu-id="d0b82-110">Purpose</span></span>|  
|---------------|-------------|  
|<span data-ttu-id="d0b82-111">trigger_field</span><span class="sxs-lookup"><span data-stu-id="d0b82-111">trigger_field</span></span>|<span data-ttu-id="d0b82-112">トリガー値を調べるセグメント フィールドです。</span><span class="sxs-lookup"><span data-stu-id="d0b82-112">The segment field that will be inspected for the trigger value.</span></span>|  
|<span data-ttu-id="d0b82-113">trigger_value</span><span class="sxs-lookup"><span data-stu-id="d0b82-113">trigger_value</span></span>|<span data-ttu-id="d0b82-114">トリガーの値です。</span><span class="sxs-lookup"><span data-stu-id="d0b82-114">The trigger value(s).</span></span><br /><br /> <span data-ttu-id="d0b82-115">1 つの値、または空白で区切られた値のリストを含めることができます。</span><span class="sxs-lookup"><span data-stu-id="d0b82-115">This may contain a single value, or a space delimited list of values.</span></span>|  
  
 <span data-ttu-id="d0b82-116">次の表は、HIPAA スキーマ、トリガーをアクティブ化する EDI セグメント、およびセグメント処理の結果となる XML データに表示されるトリガーの注釈を示します。</span><span class="sxs-lookup"><span data-stu-id="d0b82-116">The following table shows the trigger annotation as it would appear in the HIPAA schema, the EDI segment that will cause the trigger to activate, and the resulting XML data after processing the segment.</span></span>  
  
|<span data-ttu-id="d0b82-117">スキーマ トリガーの注釈</span><span class="sxs-lookup"><span data-stu-id="d0b82-117">Schema Trigger Annotation</span></span>|<span data-ttu-id="d0b82-118">一致する N1 セグメント</span><span class="sxs-lookup"><span data-stu-id="d0b82-118">Matching N1 Segment</span></span>|<span data-ttu-id="d0b82-119">生成される XML データ</span><span class="sxs-lookup"><span data-stu-id="d0b82-119">Resulting XML Data</span></span>|  
|-------------------------------|-------------------------|------------------------|  
|`<xs:element name="TS835W1_1000A_Loop">  <xs:annotation>   <xs:appinfo>    <b:recordInfo structure="delimited" delimiter_type="inherit_record"     field_order="infix" count_ignore="yes" child_delimiter="default"     trigger_field="N1_PayerIdentification_TS835W1_1000A/N101__EntityIdentifierCode"     trigger_value="PR" notes="Payer Identification" />    </xs:appinfo>  </xs:annotation>`|<span data-ttu-id="d0b82-120">N1 * PR\*Contoso\*XV\*0000000 ~</span><span class="sxs-lookup"><span data-stu-id="d0b82-120">N1*PR\*Contoso\*XV\*0000000~</span></span>|`<ns0:TS835W1_1000A_Loop>  <N1_PayerIdentification_TS835W1_1000A>   <N101__EntityIdentifierCode>PR</N101__EntityIdentifierCode>    <N102__PayerName>Contoso</N102__PayerName>    <N103__IdentificationCodeQualifier>XV</N103__IdentificationCodeQualifier>    <N104__PayerIdentifier>0000000</N104__PayerIdentifier>   </N1_PayerIdentification_TS835W1_1000A>`|  
|`<xs:element name="TS835W1_1000B_Loop">   <xs:annotation>    <xs:appinfo>     <b:recordInfo structure="delimited" delimiter_type="inherit_record"     field_order="infix" count_ignore="yes" child_delimiter="default"     trigger_field="N1_PayeeIdentification_TS835W1_1000B/N101__EntityIdentifierCode"     trigger_value="PE" notes="Payee Identification" />    </xs:appinfo>   </xs:annotation>`|<span data-ttu-id="d0b82-121">N1 * PE\*Fabrikam\*FI\*9999999 ~</span><span class="sxs-lookup"><span data-stu-id="d0b82-121">N1*PE\*Fabrikam\*FI\*9999999~</span></span>|`<TS835W1_1000B_Loop>   <N1_PayeeIdentification_TS835W1_1000B>    <N101__EntityIdentifierCode>PE</N101__EntityIdentifierCode>    <N102__PayeeName>Fabrikam</N102__PayeeName>    <N103__IdentificationCodeQualifier>FI</N103__IdentificationCodeQualifier>    <N104__PayeeIdentificationCode>9999999</N104__PayeeIdentificationCode>   </N1_PayeeIdentification_TS835W1_1000B>`|  
  
 <span data-ttu-id="d0b82-122">**トリガー フィールドの EDI 逆アセンブラーの処理**</span><span class="sxs-lookup"><span data-stu-id="d0b82-122">**EDI Disassembler Processing of Trigger Fields**</span></span>  
  
 <span data-ttu-id="d0b82-123">設定すると HIPAA のトランザクションを受け取ると、EDI 逆アセンブラーは、トリガー フィールドを含むセグメントを検出すると、トリガー情報を使用して、セグメントとトリガーの組み合わせに固有の XML レコードを生成します。</span><span class="sxs-lookup"><span data-stu-id="d0b82-123">When receiving a HIPAA transaction set, if the EDI disassembler encounters a segment that contains a trigger field, it uses the trigger information to generate an XML record specific to the segment and trigger combination.</span></span> <span data-ttu-id="d0b82-124">たとえば、次の EDI データには、N101、PR および PE について異なる値を持つ 2 つの N1 セグメントがあります。</span><span class="sxs-lookup"><span data-stu-id="d0b82-124">For example, in the following EDI data, there are two N1 segments that have different values for N101, PR and PE:</span></span>  
  
```  
  
N1*PR*Contoso*XV*0000000~  
N3*N301__PayerAddressLine~  
N4*N401__PayerCityName*N4*N403__PayerPost**N4*N406~  
……  
N1*PE*Fabrikam*FI*9999999~  
N3*N301__PayeeAddressLine~  
N4*N401__PayeeCityName*N4*N403__PayeePost**N4*N406~  
  
```  
  
 <span data-ttu-id="d0b82-125">スキーマ内のトリガー フィールドの注釈は N101、< n1_payeridentification_ts835w1_1000 a > の値に基づいて 2 つの独立した XML レコードと、EDI 逆アセンブラーによって処理された、および < N1_PayeeIdentification_TS835W1_1000B >N1 に対応する * PR および N1\*PE です。</span><span class="sxs-lookup"><span data-stu-id="d0b82-125">When processed by the EDI disassembler, the trigger field annotations present in the schema will result in two separate XML records based on the value of N101, <N1_PayerIdentification_TS835W1_1000A> and <N1_PayeeIdentification_TS835W1_1000B>, corresponding to N1*PR and N1\*PE.</span></span>  
  
 <span data-ttu-id="d0b82-126">送信時に EDI アセンブラーでは、トリガーの注釈を含むフィールドの "_" 文字に続くサフィックスを削除します。</span><span class="sxs-lookup"><span data-stu-id="d0b82-126">When sending, the EDI assembler will drop the suffix following the “_” character for fields that contain a trigger annotation.</span></span> <span data-ttu-id="d0b82-127">たとえば、<N1_PayerIdentification_TS835W1_1000A> および <N1_PayeeIdentification_TS835W1_1000B> は、いずれも "N1" となります。</span><span class="sxs-lookup"><span data-stu-id="d0b82-127">For example, both <N1_PayerIdentification_TS835W1_1000A> and <N1_PayeeIdentification_TS835W1_1000B> will both become N1.</span></span>  
  
 <span data-ttu-id="d0b82-128">**既定のセグメントおよびトリガー フィールド**</span><span class="sxs-lookup"><span data-stu-id="d0b82-128">**Default Segments and Trigger Fields**</span></span>  
  
 <span data-ttu-id="d0b82-129">次の表は、[!INCLUDE[btsBizTalkServer2006r3](../includes/btsbiztalkserver2006r3-md.md)] の一部として提供されている HIPAA ドキュメントで使用される既定のセグメントおよびトリガー フィールドについての情報を示します。</span><span class="sxs-lookup"><span data-stu-id="d0b82-129">The following table contains information on the default segments and trigger fields used in HIPAA documents supplied as part of [!INCLUDE[btsBizTalkServer2006r3](../includes/btsbiztalkserver2006r3-md.md)]:</span></span>  
  
> [!NOTE]
>  <span data-ttu-id="d0b82-130">トリガー フィールドで使用される個別のトリガー値は、スキーマによって異なります。</span><span class="sxs-lookup"><span data-stu-id="d0b82-130">The individual trigger values used with the trigger fields may vary between schemas.</span></span>  
  
|<span data-ttu-id="d0b82-131">トリガーのあるセグメント</span><span class="sxs-lookup"><span data-stu-id="d0b82-131">Segment with Trigger</span></span>|<span data-ttu-id="d0b82-132">トリガー フィールド</span><span class="sxs-lookup"><span data-stu-id="d0b82-132">Trigger field</span></span>|  
|--------------------------|-------------------|  
|<span data-ttu-id="d0b82-133">AMT</span><span class="sxs-lookup"><span data-stu-id="d0b82-133">AMT</span></span>|<span data-ttu-id="d0b82-134">AMT01</span><span class="sxs-lookup"><span data-stu-id="d0b82-134">AMT01</span></span>|  
|<span data-ttu-id="d0b82-135">CRC</span><span class="sxs-lookup"><span data-stu-id="d0b82-135">CRC</span></span>|<span data-ttu-id="d0b82-136">CRC01</span><span class="sxs-lookup"><span data-stu-id="d0b82-136">CRC01</span></span>|  
|<span data-ttu-id="d0b82-137">DTM</span><span class="sxs-lookup"><span data-stu-id="d0b82-137">DTM</span></span>|<span data-ttu-id="d0b82-138">DTM01</span><span class="sxs-lookup"><span data-stu-id="d0b82-138">DTM01</span></span>|  
|<span data-ttu-id="d0b82-139">DTP</span><span class="sxs-lookup"><span data-stu-id="d0b82-139">DTP</span></span>|<span data-ttu-id="d0b82-140">DTP01</span><span class="sxs-lookup"><span data-stu-id="d0b82-140">DTP01</span></span>|  
|<span data-ttu-id="d0b82-141">ENT</span><span class="sxs-lookup"><span data-stu-id="d0b82-141">ENT</span></span>|<span data-ttu-id="d0b82-142">ENT02</span><span class="sxs-lookup"><span data-stu-id="d0b82-142">ENT02</span></span>|  
|<span data-ttu-id="d0b82-143">HI</span><span class="sxs-lookup"><span data-stu-id="d0b82-143">HI</span></span>|<span data-ttu-id="d0b82-144">HI01:01</span><span class="sxs-lookup"><span data-stu-id="d0b82-144">HI01:01</span></span>|  
|<span data-ttu-id="d0b82-145">N1</span><span class="sxs-lookup"><span data-stu-id="d0b82-145">N1</span></span>|<span data-ttu-id="d0b82-146">N101</span><span class="sxs-lookup"><span data-stu-id="d0b82-146">N101</span></span>|  
|<span data-ttu-id="d0b82-147">NM1</span><span class="sxs-lookup"><span data-stu-id="d0b82-147">NM1</span></span>|<span data-ttu-id="d0b82-148">NM01</span><span class="sxs-lookup"><span data-stu-id="d0b82-148">NM01</span></span>|  
|<span data-ttu-id="d0b82-149">NTE</span><span class="sxs-lookup"><span data-stu-id="d0b82-149">NTE</span></span>|<span data-ttu-id="d0b82-150">NTE01</span><span class="sxs-lookup"><span data-stu-id="d0b82-150">NTE01</span></span>|  
|<span data-ttu-id="d0b82-151">REF</span><span class="sxs-lookup"><span data-stu-id="d0b82-151">REF</span></span>|<span data-ttu-id="d0b82-152">REF01</span><span class="sxs-lookup"><span data-stu-id="d0b82-152">REF01</span></span>|  
|<span data-ttu-id="d0b82-153">RMR</span><span class="sxs-lookup"><span data-stu-id="d0b82-153">RMR</span></span>|<span data-ttu-id="d0b82-154">RMR01</span><span class="sxs-lookup"><span data-stu-id="d0b82-154">RMR01</span></span>|