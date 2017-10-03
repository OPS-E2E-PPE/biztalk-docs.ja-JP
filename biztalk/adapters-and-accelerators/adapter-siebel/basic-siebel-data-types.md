---
title: "Siebel の基本的なデータの種類 |Microsoft ドキュメント"
ms.custom: 
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: 
ms.suite: 
ms.tgt_pltfrm: 
ms.topic: article
helpviewer_keywords: Siebel data types, supported
ms.assetid: bf86f639-6c45-49db-9e58-79c3ad2c9978
caps.latest.revision: "4"
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: 0266f445c2fd8a7cba9a0e2089b9542813230580
ms.sourcegitcommit: cb908c540d8f1a692d01dc8f313e16cb4b4e696d
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 09/20/2017
---
# <a name="basic-siebel-data-types"></a>Siebel の基本的なデータ型
このセクションで Siebel データ型をサポートする方法について説明します、[!INCLUDE[adaptersiebel](../../includes/adaptersiebel-md.md)]です。  
  
## <a name="supported-siebel-data-types"></a>サポートされる Siebel データ型  
 次の表は、Siebel データ型を[!INCLUDE[adaptersiebel_short](../../includes/adaptersiebel-short-md.md)]サポートし、それらの表示、アダプターによって BizTalk (XSD 型) と WCF サービス モデル (.NET 型) にします。 アスタリスクでマークされた型では、次の表に、メモを参照してください。  
  
|データ型|XSD 型|.NET の種類|Description|  
|---------------|--------------|---------------|-----------------|  
|DTYPE_BOOL|xsd:boolean|ブール値|-|  
|DTYPE_CURRENCY|xsd:decimal|Decimal|-|  
|DTYPE_DATE|xsd:dateTime*|DateTime|値は、世界協定時刻 (UTC) をすることはできません。<br /><br /> -Xsd:dateTime、値が必要に、このパターンに従う:"(\d\d\d\d-\d\d-\d\d)T(00:00:00) (.\*)"です。<br />- **DateTime**オブジェクト、**DateTime.Kind**する必要があります**DateTimeKind.Unspecified**です。<br /><br /> アダプターによって、時刻部分は無視されます。<br /><br /> 送信メッセージの場合は、アダプターは、指定された値が UTC (z または UTC オフセット) でないことを確認する実行時の検証を実行します。 その検証に失敗した場合、アダプターは例外をスローします。<br /><br /> ときにこの型は、(以下に示す規則に基づく) xsd:string として公開されています。<br /><br /> -形式は、基になるデータベースによって決まります。<br />-値には、実行時の検証は実行されません。|  
|DTYPE_DATETIME|xsd:dateTime*|DateTime|値は、日付と時刻の両方のコンポーネントを含めることができ、UTC をすることはできません。<br /><br /> - **DateTime**オブジェクト、 **DateTime.Kind**する必要があります**DateTimeKind.Unspecified**です。<br /><br /> 送信メッセージにについては、アダプターは、これらの条件が満たされていることを確認する実行時検証を実行します。検証に失敗した場合、アダプターは例外をスローします。<br /><br /> ときにこの型は、(以下に示す規則に基づく) xsd:string として公開されています。<br /><br /> -形式は、基になるデータベースによって決まります。<br />-値には、実行時の検証は実行されません。|  
|DTYPE_ID|xsd:string|文字列|-|  
|DTYPE_INTEGER|xsd:int|Int32|-|  
|DTYPE_NOTE|xsd:string|文字列|-|  
|DTYPE_NUMBER|xsd:decimal|Decimal|-|  
|DTYPE_PHONE|xsd:string|文字列|-|  
|DTYPE_TEXT|xsd:string|文字列|-|  
|DTYPE_TIME|xsd:dateTime*|DateTime|値は、UTC をすることはできません。<br /><br /> -Xsd:dateTime、値が必要に、このパターンに従う: (1753-01-01)T(\d\d:\d\d:\d\d) (.\*)"です。<br />- **DateTime**オブジェクト**、DateTime.Kind**する必要があります**DateTimeKind.Unspecified**です。<br /><br /> 送信メッセージの場合は、アダプターは、指定された値が UTC (z または UTC オフセット) でないことを確認する実行時の検証を実行します。 その検証に失敗した場合、アダプターは例外をスローします。<br /><br /> ときにこの型は、(以下に示す規則に基づく) xsd:string として公開されています。<br /><br /> -形式は、基になるデータベースによって決まります。<br />-値には、実行時の検証は実行されません。|  
|DTYPE_UTCDATETIME|xsd:dateTime*|DateTime|値は、日付と時刻の両方のコンポーネントを含めることができ、UTC があります。<br /><br /> -に対して xsd:dateTime、UTC ('Z' 表記または UTC オフセット) の値を表現する必要があります。<br />- **DateTime**オブジェクト**DateTime.Kind**する必要があります**DateTimeKind.Utc**です。<br /><br /> 送信メッセージにについては、アダプターは、これらの条件が満たされていることを確認する実行時検証を実行します。検証に失敗した場合、アダプターは例外をスローします。<br /><br /> ときにこの型は、(以下に示す規則に基づく) xsd:string として公開されています。<br /><br /> -形式は、基になるデータベースによって決まります。<br />-値には、実行時の検証は実行されません。|  
  
 ビジネス サービス メソッドの引数の型を次に示します。  
  
 日付  
 DTYPE_DATE と同じです。  
  
 数値  
 DTYPE_NUMBER と同じです。  
  
 文字列  
 DTYPE_TEXT と同じです。  
  
 階層  
 XSD 型の xsd:string にし、.Net 型の文字列に対応しています。  XML メッセージで CDATA ノードに配置することがあります。  
  
 統合オブジェクト  
 階層と同じです。  
  
 *、アダプターでは、次のようにビジネス コンポーネントで DTYPE_DATE、DTYPE_DATETIME、DTYPE_TIME、および DTYPE_UTCDATETIME のフィールドを表す xsd:dateTime または xsd:string を使用するかどうかを判断します。  
  
1.  ビジネス コンポーネントのフィールドが前のデータ型のいずれかの場合、アダプターとして公開、xsd:dateTime 内の型が DateTime 型にマップする .Net)。  
  
2.  ビジネス コンポーネントのフィールドがデータ型を持たない場合、アダプターとして公開 (これは、文字列型にマップする .Net) で xsd:string です。  
  
## <a name="supported-facets-for-the-xml-schema-types"></a>XML スキーマ型のサポートされているファセット  
 [!INCLUDE[adaptersiebel_short](../../includes/adaptersiebel-short-md.md)] XML スキーマ型の次のファセットをサポートしています。  
  
|Siebel の種類|ファセット|  
|-----------------|-----------|  
|DTYPE_BOOL|なし|  
|DTYPE_CURRENCY|有効桁数 (22)、小数点以下桁数|  
|DTYPE_DATE|(\d\d\d\d-\d\d-\d\d)T(00:00:00)(.*)|  
|DTYPE_DATETIME|なし|  
|DTYPE_ID|MaxLength (15)|  
|DTYPE_INTEGER|有効桁数 (22)|  
|DTYPE_NOTE|MaxLength (16384)|  
|DTYPE_NUMBER|有効桁数 (22)、小数点以下桁数|  
|DTYPE_PHONE|MaxLength (40)|  
|DTYPE_TEXT|MaxLength (2048)|  
|DTYPE_TIME|(1753-01-01)T(\d\d:\d\d:\d\d)(.*)|  
|DTYPE_UTCDATETIME|なし|  
  
 制御するいくつかの規則は、次のとおり、ファセット、およびその値を公開する方法とタイミング。  
  
 フィールドの長さの属性が値 0 より大きい値に設定されている場合 (上記の表では、かっこで指定された) 最大値以下。  
  
-   有効桁数ファセットは次のように公開されます。  
  
    -   有効桁数属性が、フィールドに設定されている場合は、同じ値が有効桁数ファセットとしてパブリッシュされます。  
  
    -   有効桁数属性は、フィールドに設定されていない場合、長さの値は、Precision facet としてパブリッシュされます。  
  
-   場合にのみ両方は、小数点以下桁数のファセットが公開されます。  
  
    -   有効桁数属性が発行されました  
  
    -   Scale 属性が設定フィールドの値を 0 より大きく、Precision facet の一部としてパブリッシュされた値よりも小さい  
  
-   MaxLength ファセットは、Length 属性に指定された値です。 これから取得されて、フィールド定義のリポジトリ。 フィールド定義リポジトリに長さが指定されていない場合に、前の表では、かっこで指定された値は公開を取得します。  
  
### <a name="special-cases-related-to-siebel-data-types"></a>Siebel データ型に関連する特殊なケース  
 次の規則では、ビジネス コンポーネントのフィールドのファセットが使用される操作のコンテキストに基づいてに影響します。 これらの規則は、INSERT および UPDATE 操作のみに適用できます。 クエリ操作では、ビジネス コンポーネントのすべてのフィールドがユーザーに公開されます。  
  
 **ビジネス コンポーネントのフィールドは、Siebel に必須としてマークされています**  
  
 ビジネス コンポーネントのフィールドが Siebel システムで必須としてマークされていますが、前の既定のインスタンスまたは後の既定値は、フィールドを設定した場合でも[!INCLUDE[adaptersiebel_short](../../includes/adaptersiebel-short-md.md)]フィールド省略可能としてマークします。 そのため、ユーザーは、挿入または更新する値を提供する場合、アダプターは、その値を処理します。 値が指定されていない場合、Siebel は前 default/後 default 値を使用します。  
  
 **Siebel の 読み取り専用とマークされていないビジネス コンポーネントのフィールド**  
  
 ビジネス コンポーネントのフィールドは読み取り専用としてマークされていない場合、[!INCLUDE[adaptersiebel_short](../../includes/adaptersiebel-short-md.md)]書き込み可能なフィールドとして公開します。 ただし、これには、いくつかのこの規則の例外があります。 これらの設定は、次のとおりです。  
  
-   ビジネス コンポーネントのフィールドがある場合、 **Calculated**  フィールドに Siebel、Insert または Update 操作では表示されません Siebel は自動的に対処するため**Calculated**フィールドです。  
  
-   ビジネス コンポーネントのフィールドは、明示的な結合 (別のテーブルにテーブルの結合) から取得した場合は、通常、読み取り専用であります。 ただし Siebel は、候補リストのフィールドである場合、このフィールドに書き込まれるデータです。 そのため、ビジネス コンポーネントのフィールドから場合、明示的な結合フィールドが候補リストのフィールドではありません、し、これはために表示されません Insert または Update 操作でアダプター クライアントは、このようなフィールドにデータを書き込むことはできません。  
  
 **ビジネス コンポーネントで指定されていないフィールドのデータ型**  
  
 Business component のフィールドのデータ型が指定されていない場合、[!INCLUDE[adaptersiebel_short](../../includes/adaptersiebel-short-md.md)]次のヒューリスティックを使用して、フィールド メタデータを公開します。  
  
-   かどうか、このフィールドは、特別なフィールド (つまり候補リストまたは結合など)、[!INCLUDE[adaptersiebel_short](../../includes/adaptersiebel-short-md.md)]ビジネス コンポーネント マップ先でマップされたフィールドを検索します。 そのフィールドに関連付けられている型の場合、[!INCLUDE[adaptersiebel_short](../../includes/adaptersiebel-short-md.md)]するフィールドの型として公開されます。 ただし、その型が DTYPE_DATE、DTYPE_TIME、DTYPE_DATETIME、または、DTYPE_UTCDATETIME 場合、 [!INCLUDE[adaptersiebel_short](../../includes/adaptersiebel-short-md.md)] xsd:string 型としてフィールドを公開します。 マップされたフィールドは、関連付けられた型を持っていない場合、 [!INCLUDE[adaptersiebel_short](../../includes/adaptersiebel-short-md.md)] xsd:string 型として、元のフィールドを公開します。  
  
-   フィールドの候補リストまたは結合フィールドがない場合、 [!INCLUDE[adaptersiebel_short](../../includes/adaptersiebel-short-md.md)] xsd:string 型として公開されます。  
  
 **データ型、フィールド長、または親ビジネス コンポーネントの有効桁数は使用できません。**  
  
 かどうか、データが型、長さ、または親ビジネス コンポーネント (ビジネス コンポーネントの候補リストまたは MVLs に基づく子ビジネス コンポーネントを含む) の有効桁数のフィールド、[!INCLUDE[adaptersiebel_short](../../includes/adaptersiebel-short-md.md)]データ型、長さ、有効桁数、およびスケールに関する情報を取得しますビジネス コンポーネントの候補リストまたは MVL ビジネス コンポーネントです。  
  
## <a name="see-also"></a>参照  
 [メッセージと BizTalk Adapter for Siebel eBusiness Applications のメッセージ スキーマ](../../adapters-and-accelerators/adapter-siebel/messages-and-message-schemas-for-siebel-adapter-in-biztalk.md)