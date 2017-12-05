---
title: "基本的な Oracle データ Types1 |Microsoft ドキュメント"
ms.custom: 
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: 
ms.suite: 
ms.tgt_pltfrm: 
ms.topic: article
helpviewer_keywords:
- data types, supported
- data types, unsupported
ms.assetid: 491230b9-b946-4681-a048-5da46102c370
caps.latest.revision: "11"
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: 86349adae1a3ae061cb07c6c770532cf92c74dc8
ms.sourcegitcommit: 5abd0ed3f9e4858ffaaec5481bfa8878595e95f7
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 11/28/2017
---
# <a name="basic-oracle-data-types"></a>基本的な Oracle データ型
このトピックの内容について説明しますが、どのように[!INCLUDE[adapteroracle](../../includes/adapteroracle-md.md)]サーフェスの基本的な Oracle データ型。  
  
## <a name="supported-oracle-data-types"></a>サポートされている Oracle データ型  
 [!INCLUDE[adapteroracle](../../includes/adapteroracle-md.md)]いくつかの Oracle データ型に安全に型指定をサポートしています。 安全な入力を有効にすると、これらのデータ型は文字列として表されます。 設定して安全な入力を構成する、 **EnableSafeTyping**プロパティをバインドします。 既定では、セーフである入力は無効になります。 詳細については、[!INCLUDE[adapteroracle_short](../../includes/adapteroracle-short-md.md)]バインドのプロパティを参照してください[Oracle データベース アダプターのバインドのプロパティについてお読み](../../adapters-and-accelerators/adapter-oracle-database/read-about-the-oracle-database-adapter-binding-properties.md)です。  
  
> [!NOTE]
>  データ型がユーザー定義型 (Udt) 内にある場合、セーフである入力はサポートされていません。  
  
 次の表は、安全な入力が無効になっていると、Oracle データ型を表示する方法を示します (**EnableSafeTyping**は false)。 影響を受ける oracle データ型、 **EnableSafeTyping**プロパティのバインドにアスタリスク (*) でマークされます。  
  
|Oracle データ型|XSD 型|.NET の種類|コメント|  
|----------------------|--------------|---------------|--------------|  
|BFile|入力: xsd:string<br />出力: xsd:base64Binary|文字列<br />Byte[]|BFile データ型は、内部 (RecordType、TableType、UDT、および VArray) などの複合型はサポートされていません。|  
|Blob|xsd:base64Binary|Byte[]|テーブル操作とプロシージャをサポートします。|  
|Char|xsd:string|文字列|テーブル操作とプロシージャをサポートします。|  
|Clob|xsd:string|文字列|テーブル操作とプロシージャをサポートします。|  
|日付 *<br /><br /> (なしセーフである入力内の場合、UDT)|xsd:dateTime|DateTime|日付の値は、タイム ゾーン情報を含めることはできません (UTC または UTC のオフセット)。<br /><br /> -xsd:dateTime 値には、UTC または UTC オフセット<br />-   **DateTime.Kind**する必要があります**DateTimeKind.Unspecified**<br /><br /> タイム ゾーン情報が指定されている場合、アダプターがスローされます、 **XmlReaderParsingException**フィールドを示すメッセージを使用して例外。|  
|Float * *|xsd:float 場合 prec < 7 を =<br />xsd:double 場合 prec 7 > と < 15 を =<br />xsd:string 場合 prec > 15|Float<br />Double<br />文字列|-|  
|IntervalYM|xsd:string<br /><br /> xsd:long、UDT の内部場合|文字列<br /><br /> 長い場合は、UDT の内部|値は、Oracle のネイティブ形式で表す必要があります: 年-月です。たとえば、「1-2」(1 年および 2 か月間) です。|  
|IntervalDS|xsd:string<br /><br /> xsd:duration、UDT の内部場合|文字列<br /><br /> Timespan、UDT の内部場合|値は、Oracle のネイティブ形式で表す必要があります: 1 日 HH:MI:SSxFF です。たとえば、「5 15:30:12.99」|  
|Long|xsd:string|文字列|すべてのテーブルの操作、ストアド プロシージャ、および関数のサポート。 **注:**リリース以降の Oracle データベース 9i、長い形式のデータ型は使用されなくなりました。 Oracle では、LOB データ型を代わりに使用することをお勧めします。 そのため、ときに、Oracle の処理の実行、データベースを使用して、 [!INCLUDE[adapteroracle_short](../../includes/adapteroracle-short-md.md)]、LOB データ型と長さのデータではなく動作する Oracle データベース アイテムを使用することをお勧めの種類。|  
|LongRaw|xsd:base64Binary|Byte[]|-|  
|NChar|xsd:string|文字列|-|  
|NClob|xsd:string|文字列|テーブル操作とプロシージャをサポートします。|  
|数 * *|xsd:decimal 場合 prec < 28 を =<br />xsd:string 場合 prec > 28|Decimal<br />文字列|-|  
|NVarchar2|xsd:string|文字列|-|  
|Raw|xsd:base64Binary|Byte[]|テーブル操作とプロシージャをサポートします。|  
|RowID|xsd:string|文字列|-|  
|タイムスタンプ *<br /><br /> (なしセーフである入力内の場合、UDT)|xsd:dateTime 場合 prec < 7 を =<br />xsd:string 場合 prec > 7|DateTime<br />文字列|タイムスタンプの値は、タイム ゾーン情報を含めることはできません (UTC または UTC のオフセット)。<br /><br /> -xsd:dateTime 値には、UTC または UTC オフセット<br />-   **DateTime.Kind**する必要があります**DateTimeKind.Unspecified**<br /><br /> タイム ゾーン情報が指定されている場合、アダプターがスローされます、 **XmlReaderParsingException**フィールドを示すメッセージを使用して例外。|  
|TimeStampLTZ|xsd:string|文字列|Udt の内部 TimeStampLTZ はサポートされていません。<br /><br /> **UDT の外部**: NLS_TIMESTAMP_TZ_FORMAT で値を表す必要があります。|  
|TimeStampTZ|xsd:string<br /><br /> xsd:dateTime、UDT の内部場合|文字列<br /><br /> DateTime、UDT の内部場合|**UDT の外部**: NLS_TIMESTAMP_TZ_FORMAT で値を表す必要があります。|  
|10 進数 * *|xsd:decimal 場合 prec < 28 を =<br />xsd:string 場合 prec > 28|Decimal<br />文字列|-|  
|varchar2|xsd:string|文字列|-|  
|バイナリ Float * *|xsd:float 場合 prec < 7 を =<br />xsd:string 場合 prec > 7|Float<br />文字列|ロケールと一貫性のある形式で値を指定する必要があります (**System.Globalization.CultureInfo.CurrentCulture**)。 たとえば、英語ロケールで使用ピリオド文字 ('. ')、小数点以下の桁数を指定するにはフランス語のロケールのコンマ文字を使用する (',')。|  
|バイナリ倍 * *|xsd:double 場合 prec < 15 を =<br />xsd:string 場合 prec > 15|Double<br />文字列|-|  
|バイナリ整数 * *|xsd:integer|Int32|プロシージャ、関数、およびパッケージのサポート。|  
|ブール値|xsd:boolean|Null 許容のブール値||  
|XMLTYPE|xsd:string|文字列|最上位レベルのプロシージャのパラメーターはサポートされています。<br /><br /> 予約されているような XML 文字 '**\<**'、'**\>**'、エンティティ表記に置き換える必要があります**(&lt;、 &gt;)**biztalk のアプリケーションを開発するとき、およびチャネル モデルの WCF を使用します。 WCF サービス モデルの場合は必須ではありません。|  
  
 \*これらの Oracle データ型が表示される方法の影響を受ける、 **EnableSafeTyping**プロパティをバインドします。  
  
 \*\*データセットと弱い型指定の REF CURSOR の内部の数値データ型が表示された Oracle を受けたこのような方法、 **EnableSafeTyping**プロパティをバインドします。  
  
> [!IMPORTANT]
>  -   Oracle データ型の値の最大長、 [!INCLUDE[adapteroracle_short](../../includes/adapteroracle-short-md.md)] Oracle データ型に対して ODP.NET でサポートされる値の最大長でバインドされています。  
> -   [!INCLUDE[adapteroracle_short](../../includes/adapteroracle-short-md.md)] .NET 10 進数として内部的に Udt 含まれる Oracle の数値データ型を処理します。 ただしでは、[全般] (つまり、外部の Udt) を、 [!INCLUDE[adapteroracle_short](../../includes/adapteroracle-short-md.md)] OracleDecimal として Oracle の数値データ型を内部的に処理します。  
  
### <a name="safe-typing-enabled"></a>安全な入力が有効になっています。  
 次の表は、影響を受けるセーフ」と入力して、Oracle データ型に変更する方法を示しています、 **EnableSafeTyping**バインディング プロパティは true です。  
  
|Oracle データ型|XSD 型|.NET の種類|解説|  
|----------------------|--------------|---------------|-------------|  
|日付|xsd:string|文字列|値は、Oracle されているで表現する必要があります。|  
|TimeStamp|xsd:string|文字列|値は、Oracle NLS_TIMESTAMP_FORMAT で表現する必要があります。|  
  
> [!IMPORTANT]
>  安全な入力が有効になっている場合、データセットと弱い型指定の REF CURSOR の内部 Oracle 数値データ型は文字列として常に公開されます。  
  
 このテーブルに含まれていない oracle データ型は、安全な入力が有効か無効になっているか、同じ方法で表示されます。  
  
### <a name="validation"></a>検証  
 [!INCLUDE[adapteroracle](../../includes/adapteroracle-md.md)] Oracle データ型の指定した値の明示的な検証は行われません。 ただし、Oracle データ型と安全な入力が有効か無効か、に応じて暗黙的な検証を実行できます。  
  
-   間でシリアル化解除時に、メッセージと、アダプターによって内部的に使用されている .NET 型で XML が渡されます。  
  
-   によって一部のデータ型の ODP.NET します。  
  
