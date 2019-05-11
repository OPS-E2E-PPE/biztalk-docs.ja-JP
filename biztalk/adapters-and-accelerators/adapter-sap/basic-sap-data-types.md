---
title: BizTalk での mySAP アダプターでの SAP データ型の基本的な |Microsoft Docs
description: BizTalk アダプター パック (BAP) での mySAP アダプターの ABAP とデータベース データ型がサポートされています。
ms.custom: ''
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: ''
ms.suite: ''
ms.tgt_pltfrm: ''
ms.topic: article
ms.assetid: 296b4813-f175-4a02-8fd3-227ae301bc3d
caps.latest.revision: 6
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: 7aba582676b06e69fe1dc2351171f53a633261ff
ms.sourcegitcommit: 381e83d43796a345488d54b3f7413e11d56ad7be
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 05/07/2019
ms.locfileid: "65374203"
---
# <a name="basic-sap-data-types"></a>SAP の基本的なデータ型
パラメーター型ですが、[!INCLUDE[adaptersap](../../includes/adaptersap-md.md)]サポートを受けます。  

- SAP がサポートしている ABAP データ型  

- SAP をサポートするデータベースのデータ型  

  このセクションでは、ABAP とデータベースのデータ型と、対応する .NET および XML スキーマ型間のマッピングを表示します。  

> [!NOTE]
>  このセクションの情報は、Rfc、Trfc、Bapi に適用されます。 SAP のデータ型は常に、Idoc の文字列 (xsd:string) として表されます。 これは、BizTalk Server のフラット ファイル パーサーをサポートします。  

## <a name="supported-abap-data-types"></a>サポートされている ABAP データ型  
 [!INCLUDE[adaptersap](../../includes/adaptersap-md.md)] ABAP 一部のデータ型の安全な入力をサポートします。 安全な入力が有効になっているときに、これらのデータ型は文字列として表されます。 設定して安全な入力を構成する、 **EnableSafeTyping**プロパティをバインドします。 既定では、安全な入力が無効になります。 詳細については、[!INCLUDE[adaptersap_short](../../includes/adaptersap-short-md.md)]バインドのプロパティを参照してください[mySAP Business Suite のバインドのプロパティの BizTalk アダプターについて](../../adapters-and-accelerators/adapter-sap/read-about-biztalk-adapter-for-mysap-business-suite-binding-properties.md)します。  

 次の表では、安全な入力が有効でない場合に、ABAP データ型を表示する方法を示します。 (**EnableSafeTyping**は false)。 安全な入力が有効になっているときに異なる方法で表示されるデータ型は、アスタリスク (*) でマークされます。  

|ABAP データ型|RFC 型|XSD 型|.NET の種類|[書式設定文字列]|  
|--------------------|--------------|--------------|---------------|-------------------|  
|(Integer)|RFC_INT|xsd:int|Int32|-|  
|内部 (RFC_INT1)|RFC_INT1|xsd:unsignedByte|バイト|-|  
|内部 (RFC_INT2)|RFC_INT2|xsd:short|Int16|-|  
|F (Float)|RFC_FLOAT|xsd:double|Double|-|  
|P (BCD 数)|RFC_BCD|xsd:decimal 場合長さ < = 28<br />xsd:string 場合長さ > 28|10 進数<br />String|10 進数。 10 進数の桁数が 0<br />10 進数。 > 0 の小数点以下桁数|  
|C (文字)|RFC_CHAR|xsd:string|String|-|  
|D (日。YYYYMMDD 形式で指定) *|RFC_DATE|xsd:dateTime|DateTime|内部的には、アダプターが、値に逆シリアル化、 **DateTime**オブジェクト。 呼び出します、 **DateTime.ToUniversalTime**メソッドをこのオブジェクトの値を UTC に変換します。 最後に、日付部分 (**DateTime.Date**)、SAP システムに送信される値を作成するために使用します。 この日付の値は、SAP システムは、現地時刻として扱います。<br /><br /> 変換を回避するために UTC として、日付値を指定する必要があります。<br /><br /> -Xsd:dateTime の次のパターンをお勧めします:"(\d\d\d\d-\d\d-\d\d)T(00:00:00) (.\*)Z"です。<br />- **DateTime**オブジェクト セット**DateTime.Kind**に**DateTimeKind.Utc**します。|  
|T (時間。HHMMSS 形式で指定) *|RFC_TIME|xsd:dateTime|DateTime|内部的には、アダプターが、値に逆シリアル化、 **DateTime**オブジェクト。 呼び出します、 **DateTime.ToUniversalTime**メソッドをこのオブジェクトの値を UTC に変換します。 最後に、時刻部分 (**DateTime.Time**)、SAP システムに送信される値を作成するために使用します。 この時刻値は、SAP システムは、現地時刻として扱います。<br /><br /> 変換を回避するために utc 時刻の値を指定してください。<br /><br /> -Xsd:dateTime の次のパターンをお勧めします:"(0001-01-01)T(\d\d:\d\d:\d\d) (.\*)"。<br />- **DateTime**オブジェクト セット**DateTime.Kind**に**DateTimeKind.Utc**します。<br /><br /> ローカル時刻が午前 9 時 15 の場合は、express としてこの例では、"(001-01-01) T (09: 15:00) Z"|  
|N (数値の文字列) *|RFC_NUM|xsd:int 場合 lenrth < 9 を =<br />xsd:long 場合長さ 9 > および < = 19<br />xsd:string 場合 length > 19|Int32<br />long<br />String|-|  
|X (バイト)|RFC_BYTE|xsd:base64Binary|Byte[]|-|  
|文字列|RFC_STRING|xsd:string|String|-|  
|XSTRING|RFC_BYTE|xsd:base64Binary|Byte[]|-|  

 * データ型が安全な入力が有効になっているときに異なる方法で表示されることを示します。  

### <a name="safe-typing-enabled"></a>安全な入力が有効になっています。  
 次の表に、異なる方法で安全な入力が有効になっているときに表示される ABAP データ型 (、 **EnableSafeTyping**バインド プロパティが true)。  

|ABAP データ型|RFC 型|XSD 型|.NET の種類|[書式設定文字列]|  
|--------------------|--------------|--------------|---------------|-------------------|  
|D (日。YYYYMMDD 形式で指定)|RFC_DATE|xsd:string|String|SAP の日付形式:YYYYMMDD 形式で指定します。<br /><br /> 値は 8 文字の文字列では基本的に日付の数字の文字は使用します。|  
|T (時間。HHMMSS 形式で指定)|RFC_TIME|xsd:string|String|SAP の時刻の形式:HHMMSS 形式で指定します。<br /><br /> 値は 6 文字の文字列では基本的に、時間の数字、文字を使用できます。|  
|N (数値の文字列)|RFC_NUM|xsd:string|String|N 個の文字列です。ここで、n numc フィールドの長さを = です。|  

 安全な入力が有効でない場合と同じ方法でこのテーブルにない ABAP データ型は表示されます。  

### <a name="support-for-date-and-time-fields"></a>日付と時刻のフィールドのサポート  
 ABAP 日 (D) と時間 (T) 型が xsd:dateTime; として表示された安全な入力が有効でない場合ただし、日付と時刻の型についても説明するパターン ファセットが異なります。  

-   日付のパターン ファセットを示します。 `(\d\d\d\d-\d\d-\d\d)T(00:00:00)(.*)`  

     たとえば、2007 年 7 月 7 日 (2007-07-07) として表されます。  

     `(2007-07-07)T(00:00:00)`。  

-   時間パターン ファセットを示します。 `(0001-01-01)T(\d\d:\d\d:\d\d)(.*)`  

     たとえば、(6時 30分 pm と 30 秒) の 18時 30分: 30 として表されます。  

     `(0001-01-01)T(18:30:30)`。  

#### <a name="how-does-the-adapter-represent-minimum-and-maximum-time-values-on-inbound-messages-from-sap"></a>(SAP) から、アダプターを表すの最小値と受信メッセージの最大の時刻の値をどのようにか。  
 [!INCLUDE[adaptersap_short](../../includes/adaptersap-short-md.md)] SAP システムから時刻の値を受け取ると、次のガイドラインを使用します。  

-   アダプターでは、000000 (hhmmss) および 240000 (hhmmss) が 0 時間、0 分、および 0 秒として扱われます。  

## <a name="supported-database-data-types"></a>サポートされているデータベースのデータ型  
 方法、[!INCLUDE[adaptersap](../../includes/adaptersap-md.md)]サーフェス データベースのデータ型は、安全な入力が有効になっているかどうかにも依存します。 次の表は、安全な入力が有効でない場合に、データ型に対してアダプター サーフェスで実行されるデータベース (、 **EnableSafeTyping**プロパティのバインドは、false)。 安全な入力が有効になっているときに異なる方法で表示されるデータ型は、アスタリスク (*) でマークされます。  


|     データベースのデータ型      |  RFC 型  |                                                                                                                                                                                                                                                                                                              [XSD]                                                                                                                                                                                                                                                                                                              |                                                     .NET Type                                                      |
|-----------------------------|------------|-------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------|--------------------------------------------------------------------------------------------------------------------|
|   ACCP (転記期間)\*   |  RFC_NUM   |                                                                                                                                                                                                                                                                                                            xsd:int                                                                                                                                                                                                                                                                                                            |                                                       Int32                                                        |
|            CHAR             |  RFC_CHAR  |                                                                                                                                                                                                                                                                                                          xsd:string                                                                                                                                                                                                                                                                                                           |                                                       String                                                       |
|        CLNT (クライアント)        |  RFC_CHAR  |                                                                                                                                                                                                                                                                                                          xsd:string                                                                                                                                                                                                                                                                                                           |                                                       String                                                       |
|    現在 (通貨フィールド)    |  RFC_BCD   |                                                                                                                                                 xsd:decimal**に注意してください。**[!INCLUDE[adaptersap_short](../../includes/adaptersap-short-md.md)] 10 進数のパラメーターの定義に基づく 10 進数の値に丸めます。 たとえば、10 進数のパラメーターは、小数点の後に最大 5 桁の数字を使用できますが場合、4.000028 などの値に丸められます 4.00003。                                                                                                                                                  |                                                      10 進数                                                       |
|     CUKY (Currency Key)     |  RFC_CHAR  |                                                                                                                                                                                                                                                                                                          xsd:string                                                                                                                                                                                                                                                                                                           |                                                       String                                                       |
|     DATS (日付フィールド)\*     |  RFC_DATE  |                                                 xsd:dateTime<br /><br /> 内部的には、アダプターが、値に逆シリアル化、 **DateTime**オブジェクト。 呼び出します、 **DateTime.ToUniversalTime**メソッドをこのオブジェクトの値を UTC に変換します。 最後に、日付部分 (**DateTime.Date**)、SAP システムに送信される値を作成するために使用します。 この日付の値は、SAP システムは、現地時刻として扱います。<br /><br /> 変換を回避するために UTC として、日付値を指定する必要があります。 次のパターンをお勧めします"(\d\d\d\d-\d\d-\d\d)T(00:00:00) (。\*)。Z"です。                                                 | DateTime<br /><br /> Utc 日付の値を指定する必要があります (DateTime.Kind = DateTimeKind.Utc) 変換を回避するためにします。 |
|        DEC (金額)         |  RFC_BCD   |                                                                                                                                                 xsd:decimal**に注意してください。**[!INCLUDE[adaptersap_short](../../includes/adaptersap-short-md.md)] 10 進数のパラメーターの定義に基づく 10 進数の値に丸めます。 たとえば、10 進数のパラメーターは、小数点の後に最大 5 桁の数字を使用できますが場合、4.000028 などの値に丸められます 4.00003。                                                                                                                                                  |                                                      10 進数                                                       |
|    FLTP (浮動小数点)    | RFC_FLOAT  |                                                                                                                                                                                                                                                                                                          xsd:double                                                                                                                                                                                                                                                                                                           |                                                       Double                                                       |
|            INT1             |  RFC_INT1  |                                                                                                                                                                                                                                                                                                       xsd:unsignedbyte                                                                                                                                                                                                                                                                                                        |                                                        バイト                                                        |
|            INT2             |  RFC_INT2  |                                                                                                                                                                                                                                                                                                           xsd:short                                                                                                                                                                                                                                                                                                           |                                                       Int16                                                        |
|            INT4             |  RFC_INT   |                                                                                                                                                                                                                                                                                                            xsd:int                                                                                                                                                                                                                                                                                                            |                                                       Int32                                                        |
|     LANG (言語キー)     |  RFC_CHAR  |                                                                                                                                                                                                                                                                                                          xsd:string                                                                                                                                                                                                                                                                                                           |                                                       String                                                       |
|            LCHR             | RFC_STRING |                                                                                                                                                                                                                                                                                                          xsd:string                                                                                                                                                                                                                                                                                                           |                                                       String                                                       |
|    LRAW (長いバイト seq)     |  RFC_BYTE  |                                                                                                                                                                                                                                                                                                       xsd:base64binary                                                                                                                                                                                                                                                                                                        |                                                       Byte[]                                                       |
|           NUMC\*            |  RFC_NUM   |                                                                                                                                                                                                                                                                                             xsd:int<br />xsd:long<br />xsd:string                                                                                                                                                                                                                                                                                             |                  Int32 場合長さ < 9 を =<br />Int64 場合長さ > 9 および < = 19<br />文字列の場合は長さ > 19                   |
|       PREC (精度)       |  RFC_INT2  |                                                                                                                                                                                                                                                                                                           xsd:short                                                                                                                                                                                                                                                                                                           |                                                       Int16                                                        |
|       QUAN (数量)       |  RFC_BCD   |                                                                                                                                                 xsd:decimal**に注意してください。**[!INCLUDE[adaptersap_short](../../includes/adaptersap-short-md.md)] 10 進数のパラメーターの定義に基づく 10 進数の値に丸めます。 たとえば、10 進数のパラメーターは、小数点の後に最大 5 桁の数字を使用できますが場合、4.000028 などの値に丸められます 4.00003。                                                                                                                                                  |                                                      10 進数                                                       |
|     RAW (バイト シーケンス)     |  RFC_BYTE  |                                                                                                                                                                                                                                                                                                       xsd:base64binary                                                                                                                                                                                                                                                                                                        |                                                       Byte[]                                                       |
| RAWSTRING (可変長) |  RFC_BYTE  |                                                                                                                                                                                                                                                                                                       xsd:base64binary                                                                                                                                                                                                                                                                                                        |                                                       Byte[]                                                       |
|  文字列 (可変長)   | RFC_STRING |                                                                                                                                                                                                                                                                                                          xsd:string                                                                                                                                                                                                                                                                                                           |                                                       String                                                       |
|     TIMS (時刻フィールド)\*     |  RFC_TIME  | xsd:datetime<br /><br /> 内部的には、アダプターが、値に逆シリアル化、 **DateTime**オブジェクト。 呼び出します、 **DateTime.ToUniversalTime**メソッドをこのオブジェクトの値を UTC に変換します。 最後に、時刻部分 (**DateTime.Time**)、SAP システムに送信される値を作成するために使用します。 この時刻値は、SAP システムは、現地時刻として扱います。<br /><br /> 変換を回避するために utc 時刻の値を指定してください。 次のパターンをお勧めします"(0001-01-01)T(\d\d:\d\d:\d\d) (。\*)。Z"です。<br /><br /> ローカル時刻が午前 9 時 15 の場合は、express としてこの例では、"(001-01-01) T (09: 15:00) Z" | DateTime<br /><br /> Utc 時刻の値を指定する必要があります (DateTime.Kind = DateTimeKind.Utc) 変換を回避するためにします。 |
|     単位 (数量の単位)     |  RFC_CHAR  |                                                                                                                                                                                                                                                                                                          xsd:string                                                                                                                                                                                                                                                                                                           |                                                       String                                                       |
|        [サポートされていない]        |     --     |                                                                                                                                                                                                                                                                                                              --                                                                                                                                                                                                                                                                                                               |                                                       String                                                       |

 * ことアダプター サーフェスのデータ型が異なる安全な入力を有効にすることを示します。  

### <a name="safe-typing-enabled"></a>安全な入力が有効になっています。  
 次の表は、データベースに異なる方法で安全な入力が有効になっているときに表示されるデータ型 (、 **EnableSafeTyping**バインド プロパティが true)。  

|データベースのデータ型|RFC 型|[XSD]|.NET の種類|文字列値の形式|  
|------------------------|--------------|---------|---------------|-------------------------|  
|ACCP (転記期間)|RFC_NUM|xsd:string|String|文字列|  
|NUMC|RFC_NUM|xsd:string|String|文字列|  
|DATS (日付フィールド)|RFC_DATE|xsd:string|String|YYYYMMDD|  
|TIMS (時刻フィールド)|RFC_TIME|xsd:string|String|HHMMSS|  

 安全な入力が有効でない場合と同じ方法でこのテーブルに存在しないデータ型は表示されます。  

## <a name="supported-xsd-facets"></a>サポートされている XSD のファセット  
 [!INCLUDE[adaptersap_short](../../includes/adaptersap-short-md.md)]次の XSD ファセットをサポートしています。  

|RFC 型|XSD のファセット (**EnableSafeTyping** = false)|XSD のファセット (**EnableSafeTyping** = true)|  
|--------------|-------------------------------------------------|------------------------------------------------|  
|RFC_BCD|**XSD パターン ファセット**<br /><br /> **小数点以下桁数が 0:** `"([\\-]{0,1})(([0-9]{1,"`  `+ digitsBeforeDecimal +`  `"}))"`<br /><br /> **1 つまたは複数の小数点以下桁数。** `"([\\-]{0,1})(([0-9]{0,"` + `digitsBeforeDecimal +``"}\\.[0-9]{0,"``+ digitsAfterDecimal +``"})&#124;([0-9]{1,"``+ digitsBeforeDecimal +``"}))"`|同じ|  
|RFC_NUM|**XSD totalDigits ファセット**場合長さ < = 19<br /><br /> **XSD パターン ファセット**場合 length > 19|**XSD の maxLength ファセット (SAP の値の長さによって異なります)**|  
|RFC_DATE|**XSD パターン ファセット**<br /><br /> `"(\d\d\d\d-\d\d-\d\d)T(00:00:00)(.*)"`<br /><br /> パターンには、時間 00時 00分: 00 と互換性があるが含まれています。 `xsd:datetime`|**XSD maxLength ファセット = 8**|  
|RFC_TIME|**XSD パターン ファセット**<br /><br /> `"(0001-01-01)T(\d\d:\d\d:\d\d)(.*)"`<br /><br /> パターンに対応するように 0001-01-01 の日付が含まれています `xsd:datetime`|**XSD maxLength ファセット 6 を =**|  
|RFC_CHAR|**XSD maxLength ファセット**|同じ|  

## <a name="unsupported-data-types"></a>サポートされていないデータ型  
 [!INCLUDE[adaptersap_short](../../includes/adaptersap-short-md.md)]は次のデータ型をサポートしていません。  

-   ITAB II (階層) テーブルの種類  

