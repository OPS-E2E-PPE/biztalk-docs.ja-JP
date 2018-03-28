---
title: BizTalk で Oracle EBS アダプターでの Oracle データ型の基本 |Microsoft ドキュメント
description: データと XSD 型、安全な型指定、および Oracle E-business Suite BizTalk アダプター パック (BAP) 内での検証
ms.custom: ''
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: ''
ms.suite: ''
ms.tgt_pltfrm: ''
ms.topic: article
ms.assetid: 008bf621-8b4e-450d-b354-ee26b91592f2
caps.latest.revision: ''
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: 9012e2ef6adaf94f55b87bbccfc24b7fb889fbf3
ms.sourcegitcommit: 8418b1a8f38b7f56979cd6e203f0b591e2f40fe1
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 03/28/2018
---
# <a name="basic-oracle-data-types"></a>基本的な Oracle データ型
このトピックの内容について説明しますが、どのように[!INCLUDE[adapteroracleebusinesslong](../../includes/adapteroracleebusinesslong-md.md)]サーフェスの基本的な Oracle データ型。  
  
## <a name="supported-oracle-data-types"></a>サポートされている Oracle データ型  
 [!INCLUDE[adapteroraclebusinessshort](../../includes/adapteroraclebusinessshort-md.md)]いくつかの Oracle データ型に安全に型指定をサポートしています。 安全な入力を有効にすると、これらのデータ型は文字列として表されます。 有効にして安全な入力を構成する、 **EnableSafeTyping**プロパティ (既定で無効になっています) をバインドします。 詳細については、[!INCLUDE[adapteroraclebusinessshort](../../includes/adapteroraclebusinessshort-md.md)]バインドのプロパティを参照してください[Oracle E-business Suite バインド プロパティの BizTalk アダプターの説明を読む](../../adapters-and-accelerators/adapter-oracle-ebs/read-about-the-biztalk-adapter-for-oracle-e-business-suite-binding-properties.md)です。  
  
> [!NOTE]
>  データ型がユーザー定義型 (Udt) 内にある場合、セーフである入力はサポートされていません。  
  
 次の表は、安全な入力が無効になっていると、Oracle データ型を表示する方法を示します (**EnableSafeTyping**は**false**)。 影響を受ける oracle データ型、 **EnableSafeTyping**プロパティのバインドにアスタリスク (*) でマークされます。  
  
|Oracle データ型|XSD 型|.NET の種類|コメント|  
|----------------------|--------------|---------------|--------------|  
|BFile|入力: xsd:string<br /><br /> output: xsd:base64Binary|文字列<br /><br /> Byte[]|BFile データ型は、内部 (RecordType、TableType、UDT、および VArray) などの複合型はサポートされていません。|  
|Blob|xsd:base64Binary|Byte[]|-|  
|Char|xsd:string|文字列|-|  
|Clob|xsd:string|文字列|-|  
|日付 *<br /><br /> (なしセーフである入力内の場合、UDT)|xsd:dateTime|DateTime|日付の値は、タイム ゾーン情報を含めることはできません (UTC または UTC のオフセット)。<br /><br /> -xsd:dateTime 値には、UTC または UTC オフセット<br />-   **DateTime.Kind**する必要があります**DateTimeKind.Unspecified**<br /><br /> タイム ゾーン情報が指定されている場合、アダプターがスローされます、 **XmlReaderParsingException**フィールドを示すメッセージを使用して例外。 **注:** 、[!INCLUDE[adapteroraclebusinessshort](../../includes/adapteroraclebusinessshort-md.md)]のため xsd:date ではなく xsd:dateTime として Oracle の日付データ型を公開します。 <ul><li>Oracle の日付データ型は、時刻の値を含めることもできます。</li><li>.NET が xsd:date のと同じではありません。</li></ul>|  
|Float * *|xsd:float 場合 prec < 7 を =<br /><br /> xsd:double 場合 prec 7 > と < 15 を =<br /><br /> xsd:string 場合 prec > 15|Float<br /><br /> Double<br /><br /> 文字列|10 進数の文字と桁区切り記号で指定された形式と一貫性の値を指定する必要があります、 **NumericCharacters**下にあるプロパティのバインド、 **MlsSettings**プロパティをバインドします。 値が指定されていない場合、 **NumericCharacters**バインディング プロパティ、アダプター設定を使用して MLS ODP.NET コンピューターにクライアントを同じアダプターがインストールされています。|  
|IntervalDS|xsd:string<br /><br /> xsd:duration、UDT の内部場合|文字列<br /><br /> Timespan、UDT の内部場合|アダプターは、OracleIntervalDS.ToString メソッドを使用して文字列として IntervalDS データを返します。<br /><br /> 値は、Oracle のネイティブ形式で表す必要があります: 1 日 HH:MI:SSxFF (「5 15:30:12.99」など)。|  
|IntervalYM|xsd:string<br /><br /> xsd:long if inside an UDT|文字列<br /><br /> 長い場合は、UDT の内部|アダプターは、OracleIntervalYM.ToString メソッドを使用して文字列として IntervalYM データを返します。<br /><br /> 値は、Oracle のネイティブ形式で表す必要があります: 年-月です。たとえば、「1-2」(1 年および 2 か月間) です。|  
|Long|xsd:string|文字列|リリース以降の Oracle データベース 9i、長い形式のデータ型は推奨されません。 Oracle では、代わりに、ラージ オブジェクト (LOB) データ型を使用することをお勧めします。 したがって、ときに、Oracle の処理の実行、データベースを使用して、 [!INCLUDE[adapteroracle_short](../../includes/adapteroracle-short-md.md)]、LOB データ型と長さのデータではなく動作する Oracle データベース アイテムを使用することをお勧めの種類。|  
|LongRaw|xsd:base64Binary|Byte[]|-|  
|NChar|xsd:string|文字列|-|  
|NClob|xsd:string|文字列||  
|数 * *|xsd:decimal 場合 prec < 28 を =<br /><br /> xsd:string 場合 prec > 28|Decimal<br />文字列|-|  
|NVarchar2|xsd:string|文字列|-|  
|Raw|xsd:base64Binary|Byte[]||  
|RowID|xsd:string|文字列|-|  
|TimeStamp*<br /><br /> (なしセーフである入力内の場合、UDT)|xsd:dateTime if prec <= 7<br /><br /> xsd:string 場合 prec > 7|DateTime<br /><br /> 文字列|文字列 (prec > 7) として公開されている、ときに、Oracle NLS_TIMESTAMP_FORMAT で値を表現する必要があります。 TimeStamp データ型の文字列形式を指定することができます、 **TimeStampFormat**下にあるプロパティのバインド、 **MlsSettings**プロパティをバインドします。 値が指定されていない場合、 **TimeStampFormat**バインディング プロパティ、アダプター設定を使用して MLS ODP.NET コンピューターにクライアントを同じアダプターがインストールされています。<br /><br /> タイムスタンプの値は、タイム ゾーン情報を含めることはできません (UTC または UTC のオフセット)。<br /><br /> -xsd:dateTime 値には、UTC または UTC オフセット<br />-   **DateTime.Kind**する必要があります**DateTimeKind.Unspecified**<br /><br /> タイム ゾーン情報が指定されている場合、アダプターがスローされます、 **XmlReaderParsingException**フィールドを示すメッセージを使用して例外。|  
|TimeStampLTZ|xsd:string|文字列|Udt の内部 TimeStampLTZ はサポートされていません。<br /><br /> **UDT の外部**: Oracle NLS_TIMESTAMP_TZ_FORMAT で値を表す必要があります。 TimeStampLTZ データ型の文字列形式を指定することができます、 **TimeStampTZFormat**下にあるプロパティのバインド、 **MlsSettings**プロパティをバインドします。 値が指定されていない場合、 **TimeStampTZFormat**バインディング プロパティ、アダプター設定を使用して MLS ODP.NET コンピューターにクライアントを同じアダプターがインストールされています。|  
|TimeStampTZ|xsd:string<br /><br /> xsd:dateTime、UDT の内部場合|文字列<br /><br /> DateTime、UDT の内部場合|**UDT の外部**: Oracle NLS_TIMESTAMP_TZ_FORMAT で値を表す必要があります。 TimeStampTZ データ型の文字列形式を指定することができます、 **TimeStampTZFormat**下にあるプロパティのバインド、 **MlsSettings**プロパティをバインドします。 値が指定されていない場合、 **TimeStampTZFormat**バインディング プロパティ、アダプター設定を使用して MLS ODP.NET コンピューターにクライアントを同じアダプターがインストールされています。|  
|10 進数 * *|xsd:decimal 場合 prec < 28 を =<br /><br /> xsd:string 場合 prec > 28|Decimal<br /><br /> 文字列|-|  
|Varchar2|xsd:string|文字列|-|  
|バイナリ Float * *|xsd:float 場合 prec < 7 を =<br /><br /> xsd:string 場合 prec > 7|Float<br /><br /> 文字列|10 進数の文字と桁区切り記号で指定された形式と一貫性の値を指定する必要があります、 **NumericCharacters**下にあるプロパティのバインド、 **MlsSettings**プロパティをバインドします。 値が指定されていない場合、 **NumericCharacters**バインディング プロパティ、アダプター設定を使用して MLS ODP.NET コンピューターにクライアントを同じアダプターがインストールされています。|  
|バイナリ倍 * *|xsd:double 場合 prec < 15 を =<br /><br /> xsd:string 場合 prec > 15|Double<br /><br /> 文字列|-|  
|バイナリ整数 * *|xsd:integer|Int32||  
|ブール値|xsd:boolean|Null 許容のブール値||  
|XMLTYPE|xsd:string|文字列|最上位レベルのプロシージャのパラメーターはサポートされています。<br /><br /> 予約されているような XML 文字 '**\<**'、'**\>**'、エンティティ表記に置き換える必要があります**(&lt;、 &gt;)**biztalk のアプリケーションを開発するとき、およびチャネル モデルの WCF を使用します。 WCF サービス モデルの場合は必須ではありません。|  
  
 \*これらの Oracle データ型が表示される方法の影響を受ける、 **EnableSafeTyping**プロパティをバインドします。  
  
 \*\*データセットと弱い型指定の REF CURSOR の内部の数値データ型が表示された Oracle を受けたこのような方法、 **EnableSafeTyping**プロパティをバインドします。  
  
> [!IMPORTANT]
>  -   Oracle データ型の値の最大長、 [!INCLUDE[adapteroraclebusinessshort](../../includes/adapteroraclebusinessshort-md.md)] Oracle データ型に対して ODP.NET でサポートされる値の最大長でバインドされています。  
> -   [!INCLUDE[adapteroraclebusinessshort](../../includes/adapteroraclebusinessshort-md.md)] .NET 10 進数として内部的に Udt 含まれる Oracle の数値データ型を処理します。 ただしでは、[全般] (つまり、外部の Udt) を、 [!INCLUDE[adapteroraclebusinessshort](../../includes/adapteroraclebusinessshort-md.md)] OracleDecimal として Oracle の数値データ型を内部的に処理します。  
  
## <a name="safe-typing-enabled"></a>安全な入力が有効になっています。  
 次の表は、影響を受けるセーフ」と入力して、Oracle データ型に変更する方法を示しています、 **EnableSafeTyping**プロパティのバインドは**true**です。  
  
> [!NOTE]
>  このテーブルに含まれていない oracle データ型は、安全な入力が有効か無効になっているか、同じ方法で表示されます。  
  
|Oracle データ型|XSD 型|.NET の種類|解説|  
|----------------------|--------------|---------------|-------------|  
|日付|xsd:string|文字列|値は、Oracle されているで表現する必要があります。 日付データ型の形式を指定することができます、 **DateFormat**下にあるプロパティのバインド、 **MlsSettings**プロパティをバインドします。 値が指定されていない場合、 **DateFormat**バインディング プロパティ、アダプター設定を使用して MLS ODP.NET コンピューターにクライアントを同じアダプターがインストールされています。|  
|TimeStamp|xsd:string|文字列|値は、Oracle NLS_TIMESTAMP_FORMAT で表現する必要があります。 TimeStamp データ型の文字列形式を指定することができます、 **TimeStampFormat**下にあるプロパティのバインド、 **MlsSettings**プロパティをバインドします。 値が指定されていない場合、 **TimeStampFormat**バインディング プロパティ、アダプター設定を使用して MLS ODP.NET コンピューターにクライアントを同じアダプターがインストールされています。|  
  
> [!IMPORTANT]
>  安全な入力が有効になっている場合、データセットと弱い型指定の REF CURSOR の内部 Oracle 数値データ型は文字列として常に公開されます。  
  
## <a name="validation"></a>検証  
 [!INCLUDE[adapteroraclebusinessshort](../../includes/adapteroraclebusinessshort-md.md)] Oracle データ型の指定した値の明示的な検証は行われません。 ただし、Oracle データ型と安全な入力が有効か無効か、に応じて暗黙的な検証を実行できます。  
  
-   間でシリアル化解除時に、メッセージと、アダプターによって内部的に使用されている .NET 型で XML が渡されます。  
  
-   によって一部のデータ型の ODP.NET します。  
  
## <a name="see-also"></a>参照  
 [BizTalk Adapter for Oracle E-Business Suite 用のメッセージとメッセージ スキーマ](../../adapters-and-accelerators/adapter-oracle-ebs/messages-and-message-schemas-for-biztalk-adapter-for-oracle-e-business-suite.md)