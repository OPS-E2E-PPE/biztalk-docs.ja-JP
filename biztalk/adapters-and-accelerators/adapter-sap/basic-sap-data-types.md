---
title: MySAP アダプターは、BizTalk で基本的な SAP データ タイプ |Microsoft ドキュメント
description: MySAP アダプターの BizTalk アダプター パック (BAP) のサポートされている ABAP とデータベースのデータ型
ms.custom: ''
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: ''
ms.suite: ''
ms.tgt_pltfrm: ''
ms.topic: article
ms.assetid: 296b4813-f175-4a02-8fd3-227ae301bc3d
caps.latest.revision: ''
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: f40e7dc6f98e1de2ff0388a8e7e52fdabafc7681
ms.sourcegitcommit: 8418b1a8f38b7f56979cd6e203f0b591e2f40fe1
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 03/28/2018
---
# <a name="basic-sap-data-types"></a>基本的な SAP データ型
パラメーターの型を[!INCLUDE[adaptersap](../../includes/adaptersap-md.md)]サポートを受けるします。  
  
-   SAP がサポートしている ABAP データ型  
  
-   SAP をサポートするデータベースのデータ型  
  
 このセクションでは、ABAP とデータベースのデータ型と、対応する .NET および XML スキーマ型間のマッピングを表示します。  
  
> [!NOTE]
>  このセクションの情報は、Rfc、tRFCs、および Bapi に適用されます。 SAP データ型は、常に Idoc の文字列 (xsd:string) として表されます。 これは、BizTalk Server のフラット ファイル パーサーをサポートします。  
  
## <a name="supported-abap-data-types"></a>サポートされている ABAP データ型  
 [!INCLUDE[adaptersap](../../includes/adaptersap-md.md)] ABAP データ型に安全に型指定をサポートしています。 安全な入力を有効にすると、これらのデータ型は文字列として表されます。 設定して安全な入力を構成する、 **EnableSafeTyping**プロパティをバインドします。 既定では、セーフである入力は無効になります。 詳細については、[!INCLUDE[adaptersap_short](../../includes/adaptersap-short-md.md)]バインドのプロパティを参照してください[mySAP Business Suite のバインドのプロパティの BizTalk アダプターの説明を読む](../../adapters-and-accelerators/adapter-sap/read-about-biztalk-adapter-for-mysap-business-suite-binding-properties.md)です。  
  
 次の表では、安全な入力が有効でない場合の ABAP データ型の表示方法を示します。 (**EnableSafeTyping**は false)。 安全な入力が有効になっているときに異なる方法で表示されたデータ型は、アスタリスク (*) でマークされます。  
  
|ABAP データ型|RFC 型|XSD 型|.NET の種類|[書式設定文字列]|  
|--------------------|--------------|--------------|---------------|-------------------|  
|I (整数)|RFC_INT|xsd:int|Int32|-|  
|内部 (RFC_INT1)|RFC_INT1|xsd:unsignedByte|Byte|-|  
|内部 (RFC_INT2)|RFC_INT2|xsd:short|Int16|-|  
|F (Float)|RFC_FLOAT|xsd:double|Double|-|  
|P (BCD 数)|RFC_BCD|xsd:decimal 場合の長さ < 28 を =<br />xsd:string 場合長さ > 28|Decimal<br />文字列|10 進数。 小数点以下桁数が 0<br />10 進数。 > 0 の小数点以下桁数|  
|C (文字)|RFC_CHAR|xsd:string|文字列|-|  
|D (日 yyyymmdd 形式で指定) *。|RFC_DATE|xsd:dateTime|DateTime|内部的には、アダプターが値を逆シリアル化、 **DateTime**オブジェクト。 次を呼び出して、 **DateTime.ToUniversalTime**このオブジェクトの値を UTC に変換します。 最後に、日付部分 (**DateTime.Date**)、SAP システムに送信される値を作成するために使用します。 SAP システムは、この日付の値を現地時刻として扱います。<br /><br /> 変換を回避するために UTC として日付の値を指定する必要があります。<br /><br /> -Xsd:dateTime、次のパターンはお勧めします"(\d\d\d\d-\d\d-\d\d)T(00:00:00) (。\*)。Z"です。<br />- **DateTime**セットをオブジェクト**DateTime.Kind**に**DateTimeKind.Utc**です。|  
|T (時刻 hhmmss 形式で指定) *。|RFC_TIME|xsd:dateTime|DateTime|内部的には、アダプターが値を逆シリアル化、 **DateTime**オブジェクト。 次を呼び出して、 **DateTime.ToUniversalTime**このオブジェクトの値を UTC に変換します。 最後に時コンポーネントは、(**DateTime.Time**)、SAP システムに送信される値を作成するために使用します。 SAP システムは、この時刻値を現地時刻として扱います。<br /><br /> 変換を回避するために UTC としては、時刻の値を指定する必要があります。<br /><br /> -Xsd:dateTime、次のパターンはお勧めします。"(0001-01-01)T(\d\d:\d\d:\d\d) (。\*)"です。<br />- **DateTime**セットをオブジェクト**DateTime.Kind**に**DateTimeKind.Utc**です。<br /><br /> たとえば、ローカル時刻が午前 9 時 15 分の場合は、高速として"(001-01-01) T (09: 15:00) Z"|  
|N (数値の文字列) *|RFC_NUM|xsd:int if lenrth <= 9<br />xsd:long 場合長さ 9 > および < = 19<br />xsd:string 場合長さ > 19|Int32<br />long<br />文字列|-|  
|X (バイト)|RFC_BYTE|xsd:base64Binary|Byte[]|-|  
|文字列|RFC_STRING|xsd:string|文字列|-|  
|XSTRING|RFC_BYTE|xsd:base64Binary|Byte[]|-|  
  
 * データ型が安全な入力が有効になっているときに異なる方法で表示されることを示します。  
  
### <a name="safe-typing-enabled"></a>安全な入力が有効になっています。  
 次の表に、安全な入力が有効になっているときに異なる方法で表示された ABAP データ型 (、 **EnableSafeTyping** binding プロパティが true)。  
  
|ABAP データ型|RFC 型|XSD 型|.NET の種類|[書式設定文字列]|  
|--------------------|--------------|--------------|---------------|-------------------|  
|D (日 yyyymmdd 形式で指定)。|RFC_DATE|xsd:string|文字列|SAP の日付形式: yyyymmdd 形式で指定します。<br /><br /> 文字が日付の数字、許可されるは、値は 8 文字の文字列本質的にため|  
|T (時刻 hhmmss 形式で指定)。|RFC_TIME|xsd:string|文字列|SAP 時刻の形式: hhmmss 形式で指定します。<br /><br /> 文字が時刻の数字、許可されるは、値は 6 文字の文字列では基本的にため|  
|N (数値の文字列)|RFC_NUM|xsd:string|文字列|N 個の文字列です。ここで、n numc フィールドの長さを = です。|  
  
 このテーブルに含まれていない ABAP データ型は、安全な入力が有効でない場合と同じ方法で表示されます。  
  
### <a name="support-for-date-and-time-fields"></a>日付と時刻 フィールドのサポート  
 ABAP 日付 (D) と時間 (T) 型が xsd:dateTime; として表示された安全な入力が有効でない場合ただし、日付と時刻型用の表さパターン ファセットは異なります。  
  
-   日付のパターン ファセットは。 `(\d\d\d\d-\d\d-\d\d)T(00:00:00)(.*)`  
  
     たとえば、2007 年 7 月 7 日 (2007-07-07) は、として表されます。  
  
     `(2007-07-07)T(00:00:00)`」を参照してください。  
  
-   時刻のパターン ファセットは。 `(0001-01-01)T(\d\d:\d\d:\d\d)(.*)`  
  
     たとえば、(午後 6 時 30 分と 30 秒) の 18時 30分: 30 は、として表されます。  
  
     `(0001-01-01)T(18:30:30)`」を参照してください。  
  
#### <a name="how-does-the-adapter-represent-minimum-and-maximum-time-values-on-inbound-messages-from-sap"></a>(SAP) からで、アダプターを表すの最小値と受信メッセージの最大の時刻の値がどのようにしますか。  
 [!INCLUDE[adaptersap_short](../../includes/adaptersap-short-md.md)]時刻の値を SAP システムから受信したときに、次のガイドラインを使用します。  
  
-   アダプターでは、000000 (hhmmss) および 240000 (hhmmss) が 0 時間、0 分、および 0 秒として処理します。  
  
## <a name="supported-database-data-types"></a>サポートされているデータベースのデータ型  
 方法、[!INCLUDE[adaptersap](../../includes/adaptersap-md.md)]サーフェス データベースのデータ型は、安全な入力が有効になっているかどうかによっても異なります。 次の表は、どのアダプター サーフェス データベースのデータ型セーフである入力が有効でない場合 (、 **EnableSafeTyping** binding プロパティが false)。 安全な入力が有効になっているときに異なる方法で表示されたデータ型は、アスタリスク (*) でマークされます。  
  
|データベースのデータ型|RFC 型|[XSD]|.NET Type|  
|------------------------|--------------|---------|---------------|  
|ACCP (期間の投稿) *|RFC_NUM|xsd:int|Int32|  
|CHAR|RFC_CHAR|xsd:string|文字列|  
|CLNT (クライアント)|RFC_CHAR|xsd:string|文字列|  
|現在 (通貨フィールド)|RFC_BCD|xsd:decimal**注:** 、 [!INCLUDE[adaptersap_short](../../includes/adaptersap-short-md.md)] 10 進数のパラメーターの定義に基づく小数点以下の値に丸めます。 たとえば、10 進数のパラメーターは、小数点の後に最大 5 桁の数字を使用できますが場合、4.000028 などの値に丸められます 4.00003。|Decimal|  
|CUKY (Currency Key)|RFC_CHAR|xsd:string|文字列|  
|DATS (日付フィールド) *|RFC_DATE|xsd:dateTime<br /><br /> 内部的には、アダプターが値を逆シリアル化、 **DateTime**オブジェクト。 次を呼び出して、 **DateTime.ToUniversalTime**このオブジェクトの値を UTC に変換します。 最後に、日付部分 (**DateTime.Date**)、SAP システムに送信される値を作成するために使用します。 SAP システムは、この日付の値を現地時刻として扱います。<br /><br /> 変換を回避するために UTC として日付の値を指定する必要があります。 次のパターンをお勧めします。"(\d\d\d\d-\d\d-\d\d) T (00: 00:00)(.*) Z"です。|DateTime<br /><br /> Utc 日付の値を指定する必要があります (DateTime.Kind = DateTimeKind.Utc) 変換の回避します。|  
|DEC (時間)|RFC_BCD|xsd:decimal**注:** 、 [!INCLUDE[adaptersap_short](../../includes/adaptersap-short-md.md)] 10 進数のパラメーターの定義に基づく小数点以下の値に丸めます。 たとえば、10 進数のパラメーターは、小数点の後に最大 5 桁の数字を使用できますが場合、4.000028 などの値に丸められます 4.00003。|Decimal|  
|FLTP (浮動小数点)|RFC_FLOAT|xsd:double|Double|  
|INT1|RFC_INT1|xsd:unsignedbyte|Byte|  
|INT2|RFC_INT2|xsd:short|Int16|  
|INT4|RFC_INT|xsd:int|Int32|  
|LANG (言語キー)|RFC_CHAR|xsd:string|文字列|  
|LCHR|RFC_STRING|xsd:string|文字列|  
|LRAW (長いバイト seq)|RFC_BYTE|xsd:base64binary|Byte[]|  
|NUMC*|RFC_NUM|xsd:int<br />xsd:long<br />xsd:string|Int32 場合の長さ < 9 を =<br />Int64 場合長さ > 9 および < = 19<br />文字列長 > 19|  
|PREC (精度)|RFC_INT2|xsd:short|Int16|  
|QUAN (Quantity)|RFC_BCD|xsd:decimal**注:** 、 [!INCLUDE[adaptersap_short](../../includes/adaptersap-short-md.md)] 10 進数のパラメーターの定義に基づく小数点以下の値に丸めます。 たとえば、10 進数のパラメーターは、小数点の後に最大 5 桁の数字を使用できますが場合、4.000028 などの値に丸められます 4.00003。|Decimal|  
|RAW (バイトのシーケンス)|RFC_BYTE|xsd:base64binary|Byte[]|  
|RAWSTRING (可変長)|RFC_BYTE|xsd:base64binary|Byte[]|  
|文字列 (可変長)|RFC_STRING|xsd:string|文字列|  
|TIMS (時刻フィールド) *|RFC_TIME|xsd:datetime<br /><br /> 内部的には、アダプターが値を逆シリアル化、 **DateTime**オブジェクト。 次を呼び出して、 **DateTime.ToUniversalTime**このオブジェクトの値を UTC に変換します。 最後に時コンポーネントは、(**DateTime.Time**)、SAP システムに送信される値を作成するために使用します。 SAP システムは、この時刻値を現地時刻として扱います。<br /><br /> 変換を回避するために UTC としては、時刻の値を指定する必要があります。 次のパターンをお勧めします。"(0001-01-01) T (\d\d:\d\d:\d\d)(.*) Z"です。<br /><br /> たとえば、ローカル時刻が午前 9 時 15 分の場合は、高速として"(001-01-01) T (09: 15:00) Z"|DateTime<br /><br /> Utc 時刻の値を指定する必要があります (DateTime.Kind = DateTimeKind.Utc) 変換の回避します。|  
|単位 (Qty の)|RFC_CHAR|xsd:string|文字列|  
|[サポートされていない]|--|--|文字列|  
  
 * ことアダプター サーフェスのデータ型が異なるセーフである入力が有効になっていることを示します。  
  
### <a name="safe-typing-enabled"></a>安全な入力が有効になっています。  
 次の表は、データベースの安全な入力が有効になっているときに異なる方法で表示されたデータ型を示しています (、 **EnableSafeTyping** binding プロパティが true)。  
  
|データベースのデータ型|RFC 型|[XSD]|.NET の種類|文字列の値の形式|  
|------------------------|--------------|---------|---------------|-------------------------|  
|ACCP (ピリオドと投稿)|RFC_NUM|xsd:string|文字列|文字列|  
|NUMC|RFC_NUM|xsd:string|文字列|文字列|  
|DATS (日付フィールド)|RFC_DATE|xsd:string|文字列|YYYYMMDD|  
|TIMS (時刻フィールド)|RFC_TIME|xsd:string|文字列|HHMMSS|  
  
 このテーブルに含まれていないデータ型は、安全な入力が有効でない場合と同じ方法で表示されます。  
  
## <a name="supported-xsd-facets"></a>サポートされている XSD ファセット  
 [!INCLUDE[adaptersap_short](../../includes/adaptersap-short-md.md)]次の XSD ファセットをサポートしています。  
  
|RFC 型|XSD ファセット (**EnableSafeTyping** = false)|XSD ファセット (**EnableSafeTyping** = true)|  
|--------------|-------------------------------------------------|------------------------------------------------|  
|RFC_BCD|**XSD パターン ファセット**<br /><br /> **小数点以下桁数が 0:** `"([\\-]{0,1})(([0-9]{1,"`  `+ digitsBeforeDecimal +`  `"}))"`<br /><br /> **1 つまたは複数の小数点以下桁数:** `"([\\-]{0,1})(([0-9]{0,"` + `digitsBeforeDecimal +``"}\\.[0-9]{0,"``+ digitsAfterDecimal +``"})&#124;([0-9]{1,"``+ digitsBeforeDecimal +``"}))"`|同じ|  
|RFC_NUM|**XSD totalDigits ファセット**場合の長さ < 19 を =<br /><br /> **XSD パターン ファセット**場合長さ > 19|**XSD の maxLength ファセット (SAP の値の長さによって異なります)**|  
|RFC_DATE|**XSD パターン ファセット**<br /><br /> `"(\d\d\d\d-\d\d-\d\d)T(00:00:00)(.*)"`<br /><br /> パターンには、時刻 00時 00分: 00 に合うようが含まれています。 `xsd:datetime`|**XSD maxLength ファセット 8 を =**|  
|RFC_TIME|**XSD パターン ファセット**<br /><br /> `"(0001-01-01)T(\d\d:\d\d:\d\d)(.*)"`<br /><br /> パターンに合うように 0001-01-01 の日付が含まれています `xsd:datetime`|**XSD maxLength ファセット 6 を =**|  
|RFC_CHAR|**XSD maxLength ファセット**|同じ|  
  
## <a name="unsupported-data-types"></a>サポートされていないデータ型  
 [!INCLUDE[adaptersap_short](../../includes/adaptersap-short-md.md)]次のデータ型をサポートしていません。  
  
-   ITAB II (階層) テーブルの種類  
  
