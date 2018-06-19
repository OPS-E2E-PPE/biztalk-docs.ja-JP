---
title: HIPAA スキーマのトリガー フィールドの注釈 |Microsoft ドキュメント
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
ms.openlocfilehash: f8c50db43b14899439877fde8ce0ee476feb5095
ms.sourcegitcommit: 8418b1a8f38b7f56979cd6e203f0b591e2f40fe1
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 03/28/2018
ms.locfileid: "26005307"
---
# <a name="hipaa-schema-trigger-field-annotations"></a>HIPAA スキーマのトリガー フィールドの注釈
多くの場合、EDI セグメントには、セグメントの意味を変更する修飾子の値が含まれています。 たとえば、N1 セグメントには "請求先名" を示す "BT" の修飾要素が含まれていたり、"出荷先名" を示す "ST" の修飾要素が含まれていることがあります。 通常これらのフィールドを解釈する方法を決定するビジネス ロジックに任されており、逆アセンブラーが同じ XML レコード名を N1 セグメントのすべてのインスタンスを解決します。ただし、BizTalk Server に付属の HIPAA スキーマが含まれている注釈 EDI 逆アセンブラーで修飾要素の存在に基づいて一意の XML レコードを作成できるようにします。  
  
 **トリガー フィールドの実装**  
  
 トリガー フィールドは、セグメントの要素およびこのレコードの作成の起因となるトリガー値を説明する、ペアの XML 属性として実装されています。 次の表は、これらの属性の説明です。  
  
|属性|用途|  
|---------------|-------------|  
|trigger_field|トリガー値を調べるセグメント フィールドです。|  
|trigger_value|トリガーの値です。<br /><br /> 1 つの値、または空白で区切られた値のリストを含めることができます。|  
  
 次の表は、HIPAA スキーマ、トリガーをアクティブ化する EDI セグメント、およびセグメント処理の結果となる XML データに表示されるトリガーの注釈を示します。  
  
|スキーマ トリガーの注釈|一致する N1 セグメント|生成される XML データ|  
|-------------------------------|-------------------------|------------------------|  
|`<xs:element name="TS835W1_1000A_Loop">  <xs:annotation>   <xs:appinfo>    <b:recordInfo structure="delimited" delimiter_type="inherit_record"     field_order="infix" count_ignore="yes" child_delimiter="default"     trigger_field="N1_PayerIdentification_TS835W1_1000A/N101__EntityIdentifierCode"     trigger_value="PR" notes="Payer Identification" />    </xs:appinfo>  </xs:annotation>`|N1 * PR\*Contoso\*XV\*0000000 ~|`<ns0:TS835W1_1000A_Loop>  <N1_PayerIdentification_TS835W1_1000A>   <N101__EntityIdentifierCode>PR</N101__EntityIdentifierCode>    <N102__PayerName>Contoso</N102__PayerName>    <N103__IdentificationCodeQualifier>XV</N103__IdentificationCodeQualifier>    <N104__PayerIdentifier>0000000</N104__PayerIdentifier>   </N1_PayerIdentification_TS835W1_1000A>`|  
|`<xs:element name="TS835W1_1000B_Loop">   <xs:annotation>    <xs:appinfo>     <b:recordInfo structure="delimited" delimiter_type="inherit_record"     field_order="infix" count_ignore="yes" child_delimiter="default"     trigger_field="N1_PayeeIdentification_TS835W1_1000B/N101__EntityIdentifierCode"     trigger_value="PE" notes="Payee Identification" />    </xs:appinfo>   </xs:annotation>`|N1 * PE\*Fabrikam\*FI\*9999999 ~|`<TS835W1_1000B_Loop>   <N1_PayeeIdentification_TS835W1_1000B>    <N101__EntityIdentifierCode>PE</N101__EntityIdentifierCode>    <N102__PayeeName>Fabrikam</N102__PayeeName>    <N103__IdentificationCodeQualifier>FI</N103__IdentificationCodeQualifier>    <N104__PayeeIdentificationCode>9999999</N104__PayeeIdentificationCode>   </N1_PayeeIdentification_TS835W1_1000B>`|  
  
 **トリガー フィールドの EDI 逆アセンブラーの処理**  
  
 HIPAA トランザクション セットの受信 EDI 逆アセンブラーは、トリガー フィールドを含むセグメントを検出すると、ときに、セグメントとトリガーの組み合わせに固有の XML レコードを生成するのにトリガー情報を使用します。 たとえば、次の EDI データには、N101、PR および PE について異なる値を持つ 2 つの N1 セグメントがあります。  
  
```  
  
N1*PR*Contoso*XV*0000000~  
N3*N301__PayerAddressLine~  
N4*N401__PayerCityName*N4*N403__PayerPost**N4*N406~  
……  
N1*PE*Fabrikam*FI*9999999~  
N3*N301__PayeeAddressLine~  
N4*N401__PayeeCityName*N4*N403__PayeePost**N4*N406~  
  
```  
  
 スキーマ内のトリガー フィールドの注釈は < n1_payeridentification_ts835w1_1000 a > N101 の値に基づいて 2 つの独立した XML レコードと、EDI 逆アセンブラーによって処理されるときに、< N1_PayeeIdentification_TS835W1_1000B > N1 に対応する * PR および N1\*PE です。  
  
 送信時に EDI アセンブラーでは、トリガーの注釈を含むフィールドの "_" 文字に続くサフィックスを削除します。 たとえば、<N1_PayerIdentification_TS835W1_1000A> および <N1_PayeeIdentification_TS835W1_1000B> は、いずれも "N1" となります。  
  
 **既定のセグメントおよびトリガー フィールド**  
  
 次の表には、既定の区分および BizTalk Server の一部として HIPAA ドキュメントで使用されるトリガー フィールドの情報が含まれています。  
  
> [!NOTE]
>  トリガー フィールドで使用される個別のトリガー値は、スキーマによって異なります。  
  
|トリガーのあるセグメント|トリガー フィールド|  
|--------------------------|-------------------|  
|AMT|AMT01|  
|CRC|CRC01|  
|DTM|DTM01|  
|DTP|DTP01|  
|ENT|ENT02|  
|HI|HI01:01|  
|N1|N101|  
|NM1|NM01|  
|NTE|NTE01|  
|REF|REF01|  
|RMR|RMR01|