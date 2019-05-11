---
title: HIPAA スキーマのトリガー フィールドの注釈 |Microsoft Docs
ms.custom: ''
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: ''
ms.suite: ''
ms.tgt_pltfrm: ''
ms.topic: article
ms.assetid: e1389284-a2ec-44e7-a2f1-8d26f83fd31d
caps.latest.revision: 8
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: 68f8cd87ff4cb5abd58408e5736aa614d0e6d082
ms.sourcegitcommit: 381e83d43796a345488d54b3f7413e11d56ad7be
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 05/07/2019
ms.locfileid: "65387623"
---
# <a name="hipaa-schema-trigger-field-annotations"></a><span data-ttu-id="b11ef-102">HIPAA スキーマのトリガー フィールドの注釈</span><span class="sxs-lookup"><span data-stu-id="b11ef-102">HIPAA Schema Trigger Field Annotations</span></span>
<span data-ttu-id="b11ef-103">多くの場合、EDI セグメントには、セグメントの意味を変更する修飾子の値が含まれています。</span><span class="sxs-lookup"><span data-stu-id="b11ef-103">EDI segments often contain qualifier values that modify the meaning of the segment.</span></span> <span data-ttu-id="b11ef-104">たとえば、N1 セグメントには "請求先名" を示す "BT" の修飾要素が含まれていたり、"出荷先名" を示す "ST" の修飾要素が含まれていることがあります。</span><span class="sxs-lookup"><span data-stu-id="b11ef-104">For example, an N1 segment can contain a qualifying element of “BT” to signify a “bill-to name,” or it may contain a qualifying element of “ST” to indicate a “ship-to name.”</span></span> <span data-ttu-id="b11ef-105">通常これらのフィールドを解釈する方法を決定するビジネス ロジックに任されており、逆アセンブラー N1 セグメントのすべてのインスタンスを同じ XML レコード名に解決します。ただし、BizTalk Server に付属の HIPAA スキーマが含まれている、EDI 逆アセンブラーで修飾要素の存在に基づいて一意の XML レコードを作成できるようにする注釈。</span><span class="sxs-lookup"><span data-stu-id="b11ef-105">Normally it is left to business logic to determine how to interpret these fields and the disassembler resolves all instances of the N1 segment to the same XML record name; however, the HIPAA schemas shipped with BizTalk Server contain annotations that allow the EDI disassembler to create unique XML records based on the presence of a qualifying element.</span></span>  
  
 <span data-ttu-id="b11ef-106">**トリガー フィールドの実装**</span><span class="sxs-lookup"><span data-stu-id="b11ef-106">**Trigger Field Implementation**</span></span>  
  
 <span data-ttu-id="b11ef-107">トリガー フィールドは、セグメントの要素を記述する XML 属性と値を作成するには、このレコードを原因となるトリガー値のペアとして実装されます。</span><span class="sxs-lookup"><span data-stu-id="b11ef-107">Trigger fields are implemented as a pair of XML attributes that describe the segment element and the trigger value that causes this record to be created.</span></span> <span data-ttu-id="b11ef-108">次の表では、これらの属性について説明します。</span><span class="sxs-lookup"><span data-stu-id="b11ef-108">The following table describes these attributes:</span></span>  
  
|<span data-ttu-id="b11ef-109">属性</span><span class="sxs-lookup"><span data-stu-id="b11ef-109">Attribute</span></span>|<span data-ttu-id="b11ef-110">目的</span><span class="sxs-lookup"><span data-stu-id="b11ef-110">Purpose</span></span>|  
|---------------|-------------|  
|<span data-ttu-id="b11ef-111">trigger_field</span><span class="sxs-lookup"><span data-stu-id="b11ef-111">trigger_field</span></span>|<span data-ttu-id="b11ef-112">トリガーの値を調べるセグメント フィールドです。</span><span class="sxs-lookup"><span data-stu-id="b11ef-112">The segment field that will be inspected for the trigger value.</span></span>|  
|<span data-ttu-id="b11ef-113">trigger_value</span><span class="sxs-lookup"><span data-stu-id="b11ef-113">trigger_value</span></span>|<span data-ttu-id="b11ef-114">トリガーの値。</span><span class="sxs-lookup"><span data-stu-id="b11ef-114">The trigger value(s).</span></span><br /><br /> <span data-ttu-id="b11ef-115">これは、単一の値を含めることがあります。 またはスペース区切りの値のリスト。</span><span class="sxs-lookup"><span data-stu-id="b11ef-115">This may contain a single value, or a space delimited list of values.</span></span>|  
  
 <span data-ttu-id="b11ef-116">次の表に、セグメントの処理後に、HIPAA スキーマ、トリガーをアクティブ化すると、EDI セグメント、および結果の XML データで表示されるトリガーの注釈が表示されます。</span><span class="sxs-lookup"><span data-stu-id="b11ef-116">The following table shows the trigger annotation as it would appear in the HIPAA schema, the EDI segment that will cause the trigger to activate, and the resulting XML data after processing the segment.</span></span>  
  
|<span data-ttu-id="b11ef-117">スキーマ トリガーの注釈</span><span class="sxs-lookup"><span data-stu-id="b11ef-117">Schema Trigger Annotation</span></span>|<span data-ttu-id="b11ef-118">一致する N1 セグメント</span><span class="sxs-lookup"><span data-stu-id="b11ef-118">Matching N1 Segment</span></span>|<span data-ttu-id="b11ef-119">生成される XML データ</span><span class="sxs-lookup"><span data-stu-id="b11ef-119">Resulting XML Data</span></span>|  
|-------------------------------|-------------------------|------------------------|  
|`<xs:element name="TS835W1_1000A_Loop">  <xs:annotation>   <xs:appinfo>    <b:recordInfo structure="delimited" delimiter_type="inherit_record"     field_order="infix" count_ignore="yes" child_delimiter="default"     trigger_field="N1_PayerIdentification_TS835W1_1000A/N101__EntityIdentifierCode"     trigger_value="PR" notes="Payer Identification" />    </xs:appinfo>  </xs:annotation>`|<span data-ttu-id="b11ef-120">N1 \* PR\*Contoso\*される\*0000000 ~</span><span class="sxs-lookup"><span data-stu-id="b11ef-120">N1\*PR\*Contoso\*XV\*0000000~</span></span>|`<ns0:TS835W1_1000A_Loop>  <N1_PayerIdentification_TS835W1_1000A>   <N101__EntityIdentifierCode>PR</N101__EntityIdentifierCode>    <N102__PayerName>Contoso</N102__PayerName>    <N103__IdentificationCodeQualifier>XV</N103__IdentificationCodeQualifier>    <N104__PayerIdentifier>0000000</N104__PayerIdentifier>   </N1_PayerIdentification_TS835W1_1000A>`|  
|`<xs:element name="TS835W1_1000B_Loop">   <xs:annotation>    <xs:appinfo>     <b:recordInfo structure="delimited" delimiter_type="inherit_record"     field_order="infix" count_ignore="yes" child_delimiter="default"     trigger_field="N1_PayeeIdentification_TS835W1_1000B/N101__EntityIdentifierCode"     trigger_value="PE" notes="Payee Identification" />    </xs:appinfo>   </xs:annotation>`|<span data-ttu-id="b11ef-121">N1 \* PE\*Fabrikam\*FI\*9999999 ~</span><span class="sxs-lookup"><span data-stu-id="b11ef-121">N1\*PE\*Fabrikam\*FI\*9999999~</span></span>|`<TS835W1_1000B_Loop>   <N1_PayeeIdentification_TS835W1_1000B>    <N101__EntityIdentifierCode>PE</N101__EntityIdentifierCode>    <N102__PayeeName>Fabrikam</N102__PayeeName>    <N103__IdentificationCodeQualifier>FI</N103__IdentificationCodeQualifier>    <N104__PayeeIdentificationCode>9999999</N104__PayeeIdentificationCode>   </N1_PayeeIdentification_TS835W1_1000B>`|  
  
 <span data-ttu-id="b11ef-122">**トリガー フィールドの EDI 逆アセンブラーの処理**</span><span class="sxs-lookup"><span data-stu-id="b11ef-122">**EDI Disassembler Processing of Trigger Fields**</span></span>  
  
 <span data-ttu-id="b11ef-123">HIPAA トランザクションを受け取ると設定されている場合、EDI 逆アセンブラーは、トリガー フィールドを含むセグメントを検出すると、セグメントとトリガーの組み合わせに固有の XML レコードを生成するトリガー情報を使用します。</span><span class="sxs-lookup"><span data-stu-id="b11ef-123">When receiving a HIPAA transaction set, if the EDI disassembler encounters a segment that contains a trigger field, it uses the trigger information to generate an XML record specific to the segment and trigger combination.</span></span> <span data-ttu-id="b11ef-124">たとえば、次の EDI データでは、N101、PR および PE の異なる値を持つ 2 つの N1 セグメントがあります。</span><span class="sxs-lookup"><span data-stu-id="b11ef-124">For example, in the following EDI data, there are two N1 segments that have different values for N101, PR and PE:</span></span>  
  
```  
  
N1*PR*Contoso*XV*0000000~  
N3*N301__PayerAddressLine~  
N4*N401__PayerCityName*N4*N403__PayerPost**N4*N406~  
……  
N1*PE*Fabrikam*FI*9999999~  
N3*N301__PayeeAddressLine~  
N4*N401__PayeeCityName*N4*N403__PayeePost**N4*N406~  
  
```  
  
 <span data-ttu-id="b11ef-125">スキーマ内のトリガー フィールドの注釈は N101、< n1_payeridentification_ts835w1_1000 a > の値に基づいて別個の 2 つの XML レコードと、EDI 逆アセンブラーによって処理されるときと < N1_PayeeIdentification_TS835W1_1000B >対応する N1 \* PR および N1\*PE。</span><span class="sxs-lookup"><span data-stu-id="b11ef-125">When processed by the EDI disassembler, the trigger field annotations present in the schema will result in two separate XML records based on the value of N101, <N1_PayerIdentification_TS835W1_1000A> and <N1_PayeeIdentification_TS835W1_1000B>, corresponding to N1\*PR and N1\*PE.</span></span>  
  
 <span data-ttu-id="b11ef-126">送信する場合、EDI アセンブラーは、トリガーの注釈を含むフィールド「_」文字に続くサフィックスを削除します。</span><span class="sxs-lookup"><span data-stu-id="b11ef-126">When sending, the EDI assembler will drop the suffix following the “_” character for fields that contain a trigger annotation.</span></span> <span data-ttu-id="b11ef-127">たとえば、両方 < n1_payeridentification_ts835w1_1000 a > および < N1_PayeeIdentification_TS835W1_1000B > は両方になる N1 します。</span><span class="sxs-lookup"><span data-stu-id="b11ef-127">For example, both <N1_PayerIdentification_TS835W1_1000A> and <N1_PayeeIdentification_TS835W1_1000B> will both become N1.</span></span>  
  
 <span data-ttu-id="b11ef-128">**既定のセグメントおよびトリガー フィールド**</span><span class="sxs-lookup"><span data-stu-id="b11ef-128">**Default Segments and Trigger Fields**</span></span>  
  
 <span data-ttu-id="b11ef-129">次の表にはの既定のセグメントおよびトリガー フィールドを HIPAA ドキュメントが BizTalk Server の一部として提供で使用される情報が含まれます。</span><span class="sxs-lookup"><span data-stu-id="b11ef-129">The following table contains information on the default segments and trigger fields used in HIPAA documents supplied as part of BizTalk Server:</span></span>  
  
> [!NOTE]
>  <span data-ttu-id="b11ef-130">トリガー フィールドで使用される個別のトリガー値は、スキーマ間で異なる場合があります。</span><span class="sxs-lookup"><span data-stu-id="b11ef-130">The individual trigger values used with the trigger fields may vary between schemas.</span></span>  
  
|<span data-ttu-id="b11ef-131">トリガーのあるセグメント</span><span class="sxs-lookup"><span data-stu-id="b11ef-131">Segment with Trigger</span></span>|<span data-ttu-id="b11ef-132">トリガー フィールド</span><span class="sxs-lookup"><span data-stu-id="b11ef-132">Trigger field</span></span>|  
|--------------------------|-------------------|  
|<span data-ttu-id="b11ef-133">AMT</span><span class="sxs-lookup"><span data-stu-id="b11ef-133">AMT</span></span>|<span data-ttu-id="b11ef-134">AMT01</span><span class="sxs-lookup"><span data-stu-id="b11ef-134">AMT01</span></span>|  
|<span data-ttu-id="b11ef-135">CRC</span><span class="sxs-lookup"><span data-stu-id="b11ef-135">CRC</span></span>|<span data-ttu-id="b11ef-136">CRC01</span><span class="sxs-lookup"><span data-stu-id="b11ef-136">CRC01</span></span>|  
|<span data-ttu-id="b11ef-137">DTM</span><span class="sxs-lookup"><span data-stu-id="b11ef-137">DTM</span></span>|<span data-ttu-id="b11ef-138">DTM01</span><span class="sxs-lookup"><span data-stu-id="b11ef-138">DTM01</span></span>|  
|<span data-ttu-id="b11ef-139">DTP</span><span class="sxs-lookup"><span data-stu-id="b11ef-139">DTP</span></span>|<span data-ttu-id="b11ef-140">DTP01</span><span class="sxs-lookup"><span data-stu-id="b11ef-140">DTP01</span></span>|  
|<span data-ttu-id="b11ef-141">ENT</span><span class="sxs-lookup"><span data-stu-id="b11ef-141">ENT</span></span>|<span data-ttu-id="b11ef-142">ENT02</span><span class="sxs-lookup"><span data-stu-id="b11ef-142">ENT02</span></span>|  
|<span data-ttu-id="b11ef-143">HI</span><span class="sxs-lookup"><span data-stu-id="b11ef-143">HI</span></span>|<span data-ttu-id="b11ef-144">HI01:01</span><span class="sxs-lookup"><span data-stu-id="b11ef-144">HI01:01</span></span>|  
|<span data-ttu-id="b11ef-145">N1</span><span class="sxs-lookup"><span data-stu-id="b11ef-145">N1</span></span>|<span data-ttu-id="b11ef-146">N101</span><span class="sxs-lookup"><span data-stu-id="b11ef-146">N101</span></span>|  
|<span data-ttu-id="b11ef-147">NM1</span><span class="sxs-lookup"><span data-stu-id="b11ef-147">NM1</span></span>|<span data-ttu-id="b11ef-148">NM01</span><span class="sxs-lookup"><span data-stu-id="b11ef-148">NM01</span></span>|  
|<span data-ttu-id="b11ef-149">上限</span><span class="sxs-lookup"><span data-stu-id="b11ef-149">NTE</span></span>|<span data-ttu-id="b11ef-150">NTE01</span><span class="sxs-lookup"><span data-stu-id="b11ef-150">NTE01</span></span>|  
|<span data-ttu-id="b11ef-151">REF</span><span class="sxs-lookup"><span data-stu-id="b11ef-151">REF</span></span>|<span data-ttu-id="b11ef-152">REF01</span><span class="sxs-lookup"><span data-stu-id="b11ef-152">REF01</span></span>|  
|<span data-ttu-id="b11ef-153">RMR</span><span class="sxs-lookup"><span data-stu-id="b11ef-153">RMR</span></span>|<span data-ttu-id="b11ef-154">RMR01</span><span class="sxs-lookup"><span data-stu-id="b11ef-154">RMR01</span></span>|