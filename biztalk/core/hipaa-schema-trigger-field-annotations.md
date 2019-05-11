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
# <a name="hipaa-schema-trigger-field-annotations"></a>HIPAA スキーマのトリガー フィールドの注釈
多くの場合、EDI セグメントには、セグメントの意味を変更する修飾子の値が含まれています。 たとえば、N1 セグメントには "請求先名" を示す "BT" の修飾要素が含まれていたり、"出荷先名" を示す "ST" の修飾要素が含まれていることがあります。 通常これらのフィールドを解釈する方法を決定するビジネス ロジックに任されており、逆アセンブラー N1 セグメントのすべてのインスタンスを同じ XML レコード名に解決します。ただし、BizTalk Server に付属の HIPAA スキーマが含まれている、EDI 逆アセンブラーで修飾要素の存在に基づいて一意の XML レコードを作成できるようにする注釈。  
  
 **トリガー フィールドの実装**  
  
 トリガー フィールドは、セグメントの要素を記述する XML 属性と値を作成するには、このレコードを原因となるトリガー値のペアとして実装されます。 次の表では、これらの属性について説明します。  
  
|属性|目的|  
|---------------|-------------|  
|trigger_field|トリガーの値を調べるセグメント フィールドです。|  
|trigger_value|トリガーの値。<br /><br /> これは、単一の値を含めることがあります。 またはスペース区切りの値のリスト。|  
  
 次の表に、セグメントの処理後に、HIPAA スキーマ、トリガーをアクティブ化すると、EDI セグメント、および結果の XML データで表示されるトリガーの注釈が表示されます。  
  
|スキーマ トリガーの注釈|一致する N1 セグメント|生成される XML データ|  
|-------------------------------|-------------------------|------------------------|  
|`<xs:element name="TS835W1_1000A_Loop">  <xs:annotation>   <xs:appinfo>    <b:recordInfo structure="delimited" delimiter_type="inherit_record"     field_order="infix" count_ignore="yes" child_delimiter="default"     trigger_field="N1_PayerIdentification_TS835W1_1000A/N101__EntityIdentifierCode"     trigger_value="PR" notes="Payer Identification" />    </xs:appinfo>  </xs:annotation>`|N1 * PR\*Contoso\*される\*0000000 ~|`<ns0:TS835W1_1000A_Loop>  <N1_PayerIdentification_TS835W1_1000A>   <N101__EntityIdentifierCode>PR</N101__EntityIdentifierCode>    <N102__PayerName>Contoso</N102__PayerName>    <N103__IdentificationCodeQualifier>XV</N103__IdentificationCodeQualifier>    <N104__PayerIdentifier>0000000</N104__PayerIdentifier>   </N1_PayerIdentification_TS835W1_1000A>`|  
|`<xs:element name="TS835W1_1000B_Loop">   <xs:annotation>    <xs:appinfo>     <b:recordInfo structure="delimited" delimiter_type="inherit_record"     field_order="infix" count_ignore="yes" child_delimiter="default"     trigger_field="N1_PayeeIdentification_TS835W1_1000B/N101__EntityIdentifierCode"     trigger_value="PE" notes="Payee Identification" />    </xs:appinfo>   </xs:annotation>`|N1 * PE\*Fabrikam\*FI\*9999999 ~|`<TS835W1_1000B_Loop>   <N1_PayeeIdentification_TS835W1_1000B>    <N101__EntityIdentifierCode>PE</N101__EntityIdentifierCode>    <N102__PayeeName>Fabrikam</N102__PayeeName>    <N103__IdentificationCodeQualifier>FI</N103__IdentificationCodeQualifier>    <N104__PayeeIdentificationCode>9999999</N104__PayeeIdentificationCode>   </N1_PayeeIdentification_TS835W1_1000B>`|  
  
 **トリガー フィールドの EDI 逆アセンブラーの処理**  
  
 HIPAA トランザクションを受け取ると設定されている場合、EDI 逆アセンブラーは、トリガー フィールドを含むセグメントを検出すると、セグメントとトリガーの組み合わせに固有の XML レコードを生成するトリガー情報を使用します。 たとえば、次の EDI データでは、N101、PR および PE の異なる値を持つ 2 つの N1 セグメントがあります。  
  
```  
  
N1*PR*Contoso*XV*0000000~  
N3*N301__PayerAddressLine~  
N4*N401__PayerCityName*N4*N403__PayerPost**N4*N406~  
……  
N1*PE*Fabrikam*FI*9999999~  
N3*N301__PayeeAddressLine~  
N4*N401__PayeeCityName*N4*N403__PayeePost**N4*N406~  
  
```  
  
 スキーマ内のトリガー フィールドの注釈は N101、< n1_payeridentification_ts835w1_1000 a > の値に基づいて別個の 2 つの XML レコードと、EDI 逆アセンブラーによって処理されるときと < N1_PayeeIdentification_TS835W1_1000B >対応する N1 * PR および N1\*PE。  
  
 送信する場合、EDI アセンブラーは、トリガーの注釈を含むフィールド「_」文字に続くサフィックスを削除します。 たとえば、両方 < n1_payeridentification_ts835w1_1000 a > および < N1_PayeeIdentification_TS835W1_1000B > は両方になる N1 します。  
  
 **既定のセグメントおよびトリガー フィールド**  
  
 次の表にはの既定のセグメントおよびトリガー フィールドを HIPAA ドキュメントが BizTalk Server の一部として提供で使用される情報が含まれます。  
  
> [!NOTE]
>  トリガー フィールドで使用される個別のトリガー値は、スキーマ間で異なる場合があります。  
  
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
|上限|NTE01|  
|REF|REF01|  
|RMR|RMR01|