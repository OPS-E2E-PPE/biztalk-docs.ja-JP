---
title: 基本的な Siebel データ型 |Microsoft Docs
ms.custom: ''
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: ''
ms.suite: ''
ms.tgt_pltfrm: ''
ms.topic: article
helpviewer_keywords:
- Siebel data types, supported
ms.assetid: bf86f639-6c45-49db-9e58-79c3ad2c9978
caps.latest.revision: 4
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: e996e84df20ecf1fad5feb86affae96ba83507e6
ms.sourcegitcommit: 381e83d43796a345488d54b3f7413e11d56ad7be
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 05/07/2019
ms.locfileid: "65372002"
---
# <a name="basic-siebel-data-types"></a>基本的な Siebel データ型
このセクションで Siebel データ型をサポートする方法について説明します、[!INCLUDE[adaptersiebel](../../includes/adaptersiebel-md.md)]します。  

## <a name="supported-siebel-data-types"></a>サポートされる Siebel データ型  
 次の表は、Siebel データ型を[!INCLUDE[adaptersiebel_short](../../includes/adaptersiebel-short-md.md)]方法によって表される、アダプターの BizTalk (XSD 型) と WCF サービス モデル (.NET 型) とサポートしています。 アスタリスクでマークされた型、表の次の注を参照してください。  


|     データ型     |    XSD 型    | .NET の種類 |                                                                                                                                                                                                                                                                                                                                                                             説明                                                                                                                                                                                                                                                                                                                                                                              |
|-------------------|----------------|-----------|----------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------|
|    DTYPE_BOOL     |  xsd:boolean   |  ブール値  |                                                                                                                                                                                                                                                                                                                                                                                  -                                                                                                                                                                                                                                                                                                                                                                                   |
|  DTYPE_CURRENCY   |  xsd:decimal   |  10 進数  |                                                                                                                                                                                                                                                                                                                                                                                  -                                                                                                                                                                                                                                                                                                                                                                                   |
|    DTYPE_DATE     | xsd:dateTime\* | DateTime  | 値は世界協定時刻 (UTC) にはできません。<br /><br /> このパターンに従う xsd:dateTime の値が予測されます:"(\d\d\d\d-\d\d-\d\d)T(00:00:00) (.\*)"。<br />- **DateTime**オブジェクト、**DateTime.Kind**あります**DateTimeKind.Unspecified**します。<br /><br /> アダプターによって、時刻部分は無視されます。<br /><br /> 送信メッセージの場合は、アダプターは、指定された値が UTC (z または UTC オフセット) でないことを確認するランタイム検証を実行します。 検証に失敗した場合、アダプターは例外をスローします。<br /><br /> ときにこの型は、xsd:string (以下で説明するルールに基づく) として公開されます。<br /><br /> 形式は、基になるデータベースによって決まります。<br />-値には、実行時の検証を実行されません。 |
|  DTYPE_DATETIME   | xsd:dateTime\* | DateTime  |                                                                                          値は、日付と時刻の両方のコンポーネントを含めることができ、UTC をすることはできません。<br /><br /> - **DateTime**オブジェクト、 **DateTime.Kind**あります**DateTimeKind.Unspecified**します。<br /><br /> 送信メッセージの場合、アダプターです。 これらの条件が満たされていることを確認するための実行時検証を実行します検証に失敗した場合、アダプターは例外をスローします。<br /><br /> ときにこの型は、xsd:string (以下で説明するルールに基づく) として公開されます。<br /><br /> 形式は、基になるデータベースによって決まります。<br />-値には、実行時検証を実行されません。                                                                                           |
|     DTYPE_ID      |   xsd:string   |  String   |                                                                                                                                                                                                                                                                                                                                                                                  -                                                                                                                                                                                                                                                                                                                                                                                   |
|   DTYPE_INTEGER   |    xsd:int     |   Int32   |                                                                                                                                                                                                                                                                                                                                                                                  -                                                                                                                                                                                                                                                                                                                                                                                   |
|    DTYPE_NOTE     |   xsd:string   |  String   |                                                                                                                                                                                                                                                                                                                                                                                  -                                                                                                                                                                                                                                                                                                                                                                                   |
|   DTYPE_NUMBER    |  xsd:decimal   |  10 進数  |                                                                                                                                                                                                                                                                                                                                                                                  -                                                                                                                                                                                                                                                                                                                                                                                   |
|    DTYPE_PHONE    |   xsd:string   |  String   |                                                                                                                                                                                                                                                                                                                                                                                  -                                                                                                                                                                                                                                                                                                                                                                                   |
|    DTYPE_TEXT     |   xsd:string   |  String   |                                                                                                                                                                                                                                                                                                                                                                                  -                                                                                                                                                                                                                                                                                                                                                                                   |
|    DTYPE_TIME     | xsd:dateTime\* | DateTime  |                                       値は UTC にはできません。<br /><br /> Xsd:dateTime の値がこのパターンに従う必要です。(1753-01-01)T(\d\d:\d\d:\d\d) (.\*)"。<br />- **DateTime**オブジェクト<strong>、DateTime.Kind</strong>あります**DateTimeKind.Unspecified**します。<br /><br /> 送信メッセージの場合は、アダプターは、指定された値が UTC (z または UTC オフセット) でないことを確認するランタイム検証を実行します。 検証に失敗した場合、アダプターは例外をスローします。<br /><br /> ときにこの型は、xsd:string (以下で説明するルールに基づく) として公開されます。<br /><br /> 形式は、基になるデータベースによって決まります。<br />-値には、実行時検証を実行されません。                                       |
| DTYPE_UTCDATETIME | xsd:dateTime\* | DateTime  |                                                   値は、日付と時刻の両方のコンポーネントを含めることができ、UTC である必要があります。<br /><br /> Xsd:dateTime の値を UTC ('Z' notation または UTC オフセット) で表現する必要があります。<br />- **DateTime**オブジェクト**DateTime.Kind**あります**DateTimeKind.Utc**します。<br /><br /> 送信メッセージの場合、アダプターです。 これらの条件が満たされていることを確認するための実行時検証を実行します検証に失敗した場合、アダプターは例外をスローします。<br /><br /> ときにこの型は、xsd:string (以下で説明するルールに基づく) として公開されます。<br /><br /> 形式は、基になるデータベースによって決まります。<br />-値には、実行時検証を実行されません。                                                   |

 以下は、ビジネス サービス メソッドの引数の型です。  

 date  
 DTYPE_DATE と同じです。  

 数値  
 DTYPE_NUMBER と同じです。  

 String  
 DTYPE_TEXT と同じです。  

 Hieararchy  
 XSD 型の xsd:string を .Net 型の文字列に対応しています。  XML メッセージでは、CDATA のノードに配置することがあります。  

 統合オブジェクト  
 階層と同じです。  

 *、アダプターは、次のようにビジネス コンポーネントで DTYPE_DATE、DTYPE_DATETIME、DTYPE_TIME、および DTYPE_UTCDATETIME のフィールドを表す xsd:dateTime または xsd:string を使用するかどうかを決定します。  

1.  ビジネス コンポーネントのフィールドの前のデータ型のいずれかの場合、アダプターとして公開、xsd:dateTime (これは、DateTime 型にマップする .Net) の型。  

2.  ビジネス コンポーネントのフィールドがデータ型を持たない場合、アダプターとして公開 xsd:string (これは、文字列型にマップする .Net) にします。  

## <a name="supported-facets-for-the-xml-schema-types"></a>サポートされている XML スキーマ型のファセット  
 [!INCLUDE[adaptersiebel_short](../../includes/adaptersiebel-short-md.md)] XML スキーマ型の次のファセットをサポートしています。  

|Siebel の種類|ファセット|  
|-----------------|-----------|  
|DTYPE_BOOL|なし|  
|DTYPE_CURRENCY|有効桁数 (22) スケール|  
|DTYPE_DATE|(\d\d\d\d-\d\d-\d\d)T(00:00:00)(.*)|  
|DTYPE_DATETIME|なし|  
|DTYPE_ID|MaxLength (15)|  
|DTYPE_INTEGER|有効桁数 (22)|  
|DTYPE_NOTE|MaxLength (16384)|  
|DTYPE_NUMBER|有効桁数 (22) スケール|  
|DTYPE_PHONE|MaxLength (40)|  
|DTYPE_TEXT|MaxLength (2048)|  
|DTYPE_TIME|(1753-01-01)T(\d\d:\d\d:\d\d)(.*)|  
|DTYPE_UTCDATETIME|なし|  

 次にいくつかのルールを管理する方法とタイミング、ファセットと、その値が公開されます。  

 フィールドの長さ属性が 0 より大きい値に設定されている場合、最大値 (上記の表では、かっこで指定)。  

-   有効桁数ファセットは、次のように公開されます。  

    -   有効桁数の属性がフィールドに設定されている場合は、同じ値が有効桁数ファセットとして発行されます。  

    -   有効桁数の属性がフィールドに設定されていない場合、長さの値は、有効桁数ファセットとして発行されます。  

-   場合にだけ、Scale ファセットが発行されます。  

    -   発行された有効桁数属性  

    -   Scale 属性がフィールドの値に設定、0 を超えると、有効桁数ファセットの一部としてパブリッシュ値よりも小さい  

-   MaxLength ファセットは、Length 属性に指定された値です。 これフィールド定義のリポジトリから取得されます。 フィールド定義のリポジトリで、長さが指定されていない場合に、前の表では、かっこで指定された値が公開されます。  

### <a name="special-cases-related-to-siebel-data-types"></a>Siebel データ型に関連する特殊なケース  
 次の規則では、ビジネス コンポーネントのフィールドのファセットが使用される操作のコンテキストに基づいてに影響します。 これらの規則は、INSERT および UPDATE 操作にのみ適用できます。 クエリ操作の場合は、ビジネス コンポーネントのすべてのフィールドは、ユーザーに公開されます。  

 **Siebel の必須としてマークされているビジネス コンポーネントのフィールド**  

 Siebel システムで必須としてマークされたビジネス コンポーネント フィールドがフィールドに、既定の前または後の既定値を設定した場合でも[!INCLUDE[adaptersiebel_short](../../includes/adaptersiebel-short-md.md)]省略可能としてフィールドをマークします。 そのため、ユーザーが値を挿入または更新すると、アダプターはその値を処理します。 値が指定されていない場合、Siebel には、事前 default/後 default 値が使用されます。  

 **Siebel の READ ONLY とマークされていないビジネス コンポーネントのフィールド**  

 ビジネス コンポーネントのフィールドが読み取り専用としてマークされていない場合、[!INCLUDE[adaptersiebel_short](../../includes/adaptersiebel-short-md.md)]書き込み可能なフィールドとして公開します。 ただし、この規則の例外のいくつかがあります。 これらの数値は、次のとおりです。  

- ビジネス コンポーネントのフィールドがある場合、 **Calculated**フィールドでは、Siebel、Insert または Update 操作では表示されませんの Siebel が自動的に行ってくれますので**Calculated**フィールド。  

- ビジネス コンポーネントのフィールドを明示的な結合 (別のテーブルにテーブルの結合) を取得した場合、通常は読み取り専用です。 ただし Siebel は、候補リスト フィールドである場合、このフィールドに書き込まれるデータです。 そのため、ビジネス コンポーネントのフィールドは、明示的な結合フィールドが候補リスト フィールドではない場合は、し、これはために表示されません Insert または Update 操作でアダプター クライアントは、このようなフィールドにデータを書き込むことはできません。  

  **ビジネス コンポーネントで指定されていないフィールドのデータ型**  

  ビジネス コンポーネントでフィールドのデータ型が指定されていない場合、[!INCLUDE[adaptersiebel_short](../../includes/adaptersiebel-short-md.md)]は、次のヒューリスティックを使用してフィールドのメタデータを公開します。  

- 特別なフィールド (つまり候補リストまたは結合) かどうか、フィールドには、[!INCLUDE[adaptersiebel_short](../../includes/adaptersiebel-short-md.md)]は転送先のビジネス コンポーネントにマップされたフィールドを検索します。 そのフィールドにそれに関連付けられている型がある場合、[!INCLUDE[adaptersiebel_short](../../includes/adaptersiebel-short-md.md)]フィールドの型として公開されます。 ただし、その型が DTYPE_DATE、DTYPE_TIME、DTYPE_DATETIME、または、DTYPE_UTCDATETIME 場合、 [!INCLUDE[adaptersiebel_short](../../includes/adaptersiebel-short-md.md)] xsd:string 型としてフィールドが公開されます。 マップされたフィールドは、関連付けられた型を持っていない場合、 [!INCLUDE[adaptersiebel_short](../../includes/adaptersiebel-short-md.md)] xsd:string 型として、元のフィールドが公開されます。  

- フィールドの候補リストまたは結合フィールドがない場合、 [!INCLUDE[adaptersiebel_short](../../includes/adaptersiebel-short-md.md)] xsd:string 型として公開されます。  

  **データ型、フィールド長、または親ビジネス コンポーネントの有効桁数は使用できません。**  

  かどうか、データが型長さは、または親ビジネス コンポーネント (ビジネス コンポーネントの候補リストまたは MVLs に基づく子ビジネス コンポーネントを含む) の有効桁数のフィールド、[!INCLUDE[adaptersiebel_short](../../includes/adaptersiebel-short-md.md)]データ型、長さ、有効桁数、およびスケールからの情報を取得します。ビジネス コンポーネントの候補リストまたは MVL ビジネス コンポーネント。  

## <a name="see-also"></a>参照  
 [メッセージと BizTalk Adapter for Siebel eBusiness Applications のメッセージ スキーマ](../../adapters-and-accelerators/adapter-siebel/messages-and-message-schemas-for-siebel-adapter-in-biztalk.md)