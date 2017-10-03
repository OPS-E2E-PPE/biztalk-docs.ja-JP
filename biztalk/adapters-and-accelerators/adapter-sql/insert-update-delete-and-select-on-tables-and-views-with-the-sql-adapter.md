---
title: "Insert、Update、Delete、およびテーブルとビューを SQL アダプターでの操作の選択 |Microsoft ドキュメント"
ms.custom: 
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: 
ms.suite: 
ms.tgt_pltfrm: 
ms.topic: article
ms.assetid: d0cc39d5-16f2-454a-8e1d-c031592439ae
caps.latest.revision: "16"
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: cae4dfff287414c4f9b1081face9a33bbf9da545
ms.sourcegitcommit: cb908c540d8f1a692d01dc8f313e16cb4b4e696d
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 09/20/2017
---
# <a name="insert-update-delete-and-select-operations-on-tables-and-views-with-the-sql-adapter"></a>Insert、Update、Delete、およびテーブルとビューを SQL アダプターでの操作の選択
[!INCLUDE[adaptersql](../../includes/adaptersql-md.md)]テーブルと、SQL Server データベースのビューごとに、標準的な操作のセットを表示します。 これらの操作を使用すると、対象のテーブルまたはビューの WHERE 句で修飾された単純な INSERT、UPDATE、SELECT、および DELETE ステートメントを実行できます。 これらの操作は、データ操作言語 (DML) 操作とも呼ばれます。  
  
 次の表は、DML 操作を[!INCLUDE[adaptersqlshort](../../includes/adaptersqlshort-md.md)]をサポートしています。  
  
|操作|Description|  
|---------------|-----------------|  
|Insert|対象のテーブルまたはビューに対する Insert 操作を実行します。<br /><br /> -Insert 操作は、入力としてレコードの配列を受け取ります。 各レコードはターゲット テーブルとテーブル内に挿入される行にマップには厳密に型指定します。<br />値を指定された id 列に値を挿入-、 **AllowIdentityInsert** binding プロパティが TRUE に設定します。 詳細については、 **AllowIdentityInsert**バインディング プロパティを参照してください[SQL Server のアダプターのバインド プロパティの BizTalk アダプターの説明を読む](../../adapters-and-accelerators/adapter-sql/read-about-the-biztalk-adapter-for-sql-server-adapter-binding-properties.md)です。<br />-Insert 操作の戻り値は、長い形式のデータ型の配列です。 この配列は、存在する場合に、挿入された行の id 値を格納します。 テーブル内に id 列がない場合、戻り値は NULL です。<br /><br /> 挿入操作のメッセージの一部の値は、次のように扱われます、 [!INCLUDE[adaptersqlshort](../../includes/adaptersqlshort-md.md)]:<br /><br /> の計算列とタイムスタンプ列の指定値は無視されます。<br />-ノードの id 列が null の場合は無視されます。<br /><br /> 挿入操作のメッセージでその他のすべての値。<br /><br /> 場合は、列の値を指定すると、その値は、INSERT ステートメントで使用されます。<br />-特定の列のノードが null の場合は NULL は、INSERT ステートメントで使用されます。 **注:**特定のレコードの INSERT ステートメントで使用できる値がない場合 (つまり、任意の列に値が指定されていませんまたはすべての列値が無視されます)、アダプターは、次の SQL ステートメントを実行します。`insert into <table_name> default values`|  
|Select|対象のテーブルまたはビューのレコード (列) の配列と WHERE 句を指定するクエリ文字列に基づいてに対する SELECT ステートメントを実行します。<br /><br /> 、SELECT ステートメント内の列の一覧については値を指定する必要があります。 すべての列をテーブルまたはビュー内で取得する必要がある場合 *、SELECT ステートメントで指定する必要があります。 特定の列を取得する場合、列の名前をコンマで区切らしてテーブルまたはビューで定義されているように同じ順序で指定する必要があります。<br />-SELECT ステートメントでは、、WHERE 句を含める必要があります。 ただし、WHERE 句の値を指定しない場合か、削除できます、`Query`要素または空のままにします。<br />-選択操作では、更新操作を実行することもできます。 この場合、UPDATE ステートメントは内部に格納、 `Query` SELECT ステートメントの要素。<br /><br /> Select 操作の戻り値は、指定された列と対象のテーブルまたはビューから行を含む厳密に型指定された結果セットです。|  
|Update|対象のテーブルまたはビューの更新操作を実行します。<br /><br /> -更新操作は、入力としてレコードのペアの配列を受け取ります。 各レコードのペアが 2 つのレコードのコレクションと、各レコードは、厳密に型指定された対象のテーブルにします。<br /><br /> -最初のレコードを更新する必要のある新しい値に対応しています、つまり、UPDATE ステートメントの SET 句に対応します。 <br />-2 番目のレコードの行の古い値、つまり、UPDATE ステートメントの WHERE 句に対応します。 **注:**そのレコードのペアの更新ステートメントが実行されていない場合、特定のレコードのペアでは、SET 句で使用できる値はありません、します。 <br />-の値を指定された id 列の値を更新できる、 **AllowIdentityInsert** binding プロパティが TRUE に設定します。 詳細については、 **AllowIdentityInsert**バインディング プロパティを参照してください[SQL Server のアダプターのバインド プロパティの BizTalk アダプターの説明を読む](../../adapters-and-accelerators/adapter-sql/read-about-the-biztalk-adapter-for-sql-server-adapter-binding-properties.md)です。 <br />-更新操作の戻り値は、Int32 データ型では、更新された行の数を表します。<br /> 更新操作のメッセージの一部の値は、次のように扱われます、 [!INCLUDE[adaptersqlshort](../../includes/adaptersqlshort-md.md)]:<br /><br /> の計算列と、メッセージの SET 句内のタイムスタンプ列の指定値は無視されます。<br />ユーザー定義型 (UDT) がバイトの順序付け、UDT 列に指定された値ではない場合、WHERE 句を無視します。<br />Id 列のノードがメッセージの SET 句で null の場合は無視されます。<br />-Id またはタイムスタンプ列のノードが、メッセージの WHERE 句で null の場合は無視されます。<br />-イメージ、XML、Text または Ntext 列のノードが null の場合、メッセージの WHERE 句で、これらの値を比較できないために指定された値は無視されます。<br /><br /> Update 操作のメッセージ内の他のすべての値。<br /><br /> 値がステートメントの SET 句で使用される場合は、UPDATE ステートメントの SET 句で列の値を指定すると、(`set <column_name> = <value>`)。<br />-UPDATE ステートメントで NULL が使用される特定の列のノードが SET 句で null の場合 (`set <column_name> = null`)。<br />-UPDATE ステートメントの WHERE 句で、値は、ステートメントの WHERE 句で使用列の値が指定した場合 (`where <column_name> = <value>`)。<br />-UPDATE ステートメントで NULL が使用される特定の列のノードが、UPDATE ステートメントの WHERE 句で null の場合 (`where <column_name> is null`)。|  
|DELETE|対象のテーブルまたは対象のテーブルと、WHERE 句を指定するフィルター文字列のレコード (列名の一覧) の厳密に型指定された配列に基づいたビューに対して Delete 操作を実行します。<br /><br /> 削除操作の戻り値は、Int32 データ型では、削除された行の数を表します。<br /><br /> 削除操作のメッセージの一部の値は、次のように扱われます、 [!INCLUDE[adaptersqlshort](../../includes/adaptersqlshort-md.md)]:<br /><br /> -イメージ、XML、Text または Ntext 列のノードが null の場合、メッセージの WHERE 句で、これらの値を比較できないために指定された値は無視されます。<br />-Id またはタイムスタンプ列のノードが null の場合は無視されます。<br />-UDT がバイトの順序付け、UDT 列に指定された値ではない場合、WHERE 句を無視します。<br /><br /> 削除操作のメッセージでその他のすべての値。<br /><br /> 値が DELETE ステートメントの WHERE 句で使用される場合は、列の値を指定すると、(`where <column_name> = <value>`)。<br />-DELETE ステートメントで NULL が使用される特定の列のノードが null の場合 (`where <column_name> is null`)。 **注:**場合、特定のレコード (つまり、任意の列に値が指定されていませんか存在すべての列値が無視されたかどうか)、DELETE ステートメント内で使用できる値はありません、アダプターが、DELETE ステートメントを実行できません。|  
  
 詳細については。  
  
-   使用してこれらの操作を実行する[!INCLUDE[btsBizTalkServerNoVersion](../../includes/btsbiztalkservernoversion-md.md)]を参照してください[Insert、update、delete、または BizTalk Server アダプターを使用して、SQL select 操作](../../adapters-and-accelerators/adapter-sql/insert-update-delete-or-select-using-the-sql-adapter-in-biztalk-server.md)です。  
  
-   メッセージの構造と DML 操作を実行するための SOAP アクションを参照してください[Insert、Update、Delete、およびテーブルおよびビューに対する選択操作のメッセージ スキーマを](../../adapters-and-accelerators/adapter-sql/message-schemas-for-insert-update-delete-and-select-on-tables-and-views.md)です。  
  
## <a name="see-also"></a>参照  
 [アダプターを使用して SAP システムへの接続します。](../../adapters-and-accelerators/adapter-sap/connect-to-an-sap-system-using-the-adapter.md)