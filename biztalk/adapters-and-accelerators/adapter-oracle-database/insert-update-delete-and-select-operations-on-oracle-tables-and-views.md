---
title: Insert、Update、Delete、および Oracle のテーブルおよびビューに対する Select 操作 |Microsoft Docs
ms.custom: ''
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: ''
ms.suite: ''
ms.tgt_pltfrm: ''
ms.topic: article
helpviewer_keywords:
- operations, on tables and views
- operations, performing
- data manipulation language
- Delete operation
- Insert operation
- Update operation
- DELETE statement
- DML operation
- Select operation
- INSERT statement
- UPDATE statement
ms.assetid: af65fac4-3c16-40c4-ae7a-9c1757223f99
caps.latest.revision: 6
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: 4b8ea0ed25119e43565a29c6d7c94a2e81a6ca6e
ms.sourcegitcommit: 266308ec5c6a9d8d80ff298ee6051b4843c5d626
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 06/27/2018
ms.locfileid: "36989971"
---
# <a name="insert-update-delete-and-select-operations-on-oracle-tables-and-views"></a>挿入、更新、削除、および Oracle のテーブルとビューで操作を選択します。
[!INCLUDE[adapteroracle](../../includes/adapteroracle-md.md)] Oracle データベースのテーブルおよびビューごとに標準の操作のセットを明らかになります。 これらの操作を使用すると、単純な SQL INSERT、UPDATE、SELECT を実行し、DELETE ステートメントの対象のテーブル (またはビュー) に WHERE 句で修飾できます。 これらの操作は、データ操作言語 (DML) 操作とも呼ばれます。 たとえば、SQL SELECT クエリの結合演算子を使用するより複雑な操作を実行するには、SQLEXECUTE 操作を使用できます。 SQLEXECUTE 操作の詳細については、次を参照してください。 [Oracle データベースで SQLEXECUTE 操作](../../adapters-and-accelerators/adapter-oracle-database/sqlexecute-operation-in-oracle-database.md)します。  
  
 次の表は、DML 操作を[!INCLUDE[adapteroracle_short](../../includes/adapteroracle-short-md.md)]をサポートしています。  
  
|演算|説明|  
|---------------|-----------------|  
|Insert|対象テーブルまたはビューに対する挿入操作を実行します。 挿入操作では、対象のテーブルまたはビューに複数のレコードまたは一括挿入をサポートしています。<br /><br /> -複数のレコードの挿入操作では、テーブルまたは指定されたレコード セットに基づいたビューに行を挿入します。<br /><br /> -一括挿入操作では、テーブルまたは指定した SQL SELECT クエリ、列リストに基づいたビューに行を挿入します。 クエリから返されるレコードは、列リストに基づく対象テーブルに挿入されます。<br /><br /> 挿入操作の戻り値では、挿入された行の数です。<br /><br /> **注:** 両方の複数のレコードを挿入し、同じメッセージで一括挿入を組み合わせることはできません。<br /><br /> **InlineValue**<br /><br /> という名前の省略可能な属性の値を指定することで、レコードの値を上書きする複数レコードの挿入操作ですべての単純なデータ レコードを選択できます**InlineValue**します。 テーブルまたはビューの日付列に主キー列 (SYSDATE を使用) のシステム日付を挿入するシーケンスを使用する、またはの設定などに計算値を挿入する InlineValue 属性を使用できます。 たとえば、次のステートメントを挿入します。<br /><br /> `<Insert xmlns="http://Microsoft.LobServices.OracleDB/2007/03/SCOTT/Table/ACCOUNTACTIVITY">   <RECORDSET>     <ACCOUNTACTIVITYRECORDINSERT>       <ACCOUNT>10001</ACCOUNT>       <EMPNAME>John</EMPNAME>       <AMOUNT>1500</AMOUNT>       <TRANSDATE InlineValue="SYSDATE">2008-06-21T15:52:19</TRANSDATE>       </ACCOUNTACTIVITYRECORDINSERT >   </RECORDSET> </Insert>`<br /><br /> でも"2008-06-21T15:52:19"は"SYSDATE、"InlineValue 属性の値であるトランザクション日付列の値として指定された (システムの日付) に挿入される対象のテーブル。<br /><br /> InlineValue の使用中に次のように属性します。<br /><br /> -InlineValue 属性の定数値を使用しないでください。 たとえば、INSERT ステートメントで指定した場合で`<EMPNAME InlineValue="John"/>`エラーが発生し、します。 として InlineValue 属性の値が渡されるため、これは-この場合は、Oracle に*John*予期される値ではない Oracle データベースに渡される (期待される値は *"John"*)。 従業員名を囲む単一引用符を使用する必要があります。 たとえば、「 `<EMPNAME InlineValue="’John’"/>`」のように入力します。<br /><br /> -InlineValue 属性の選択クエリを使用する場合は、SELECT ステートメントをかっこで囲み、select クエリが 1 つのレコードのみをフェッチすることも確認する必要があります。 たとえば、「 `<EMPNAME InlineValue="(SELECT NAME FROM MS_SAMPLE_EMPLOYEES WHERE ID=123)"/>`」のように入力します。<br /><br /> **注:** 要素は、Oracle データベースで NOT NULL としてマークすると、インラインの値を指定した場合でも、その要素の値を指定する必要があります。 失敗すると、スキーマ検証が失敗します。|  
|Select|対象のテーブルまたは指定された列の名前と SQL の WHERE 句を指定するフィルター文字列の一覧に基づいたビューでは、SQL SELECT クエリを実行します。<br /><br /> Select 操作の戻り値は、指定した列と行を含む厳密に型指定された結果セットです。|  
|更新|対象のテーブルまたはビューの更新操作を実行します。 更新するレコードは、SQL の WHERE 句を指定するフィルター文字列によって指定されます。 更新プログラムの値は、テンプレートのレコードで指定されます。<br /><br /> 更新操作の戻り値では、更新された行の数です。|  
|DELETE|対象のテーブルまたはビューのフィルター文字列で指定されている SQL の WHERE 句に基づいて削除操作を実行します。<br /><br /> 削除操作の戻り値では、削除された行の数です。|  
  
 詳細については。  
  
- 使用してこれらの操作を実行する[!INCLUDE[btsBizTalkServerNoVersion](../../includes/btsbiztalkservernoversion-md.md)]を参照してください[Insert、Update、Delete、および選択の操作を使用して BizTalk Server によって](../../adapters-and-accelerators/adapter-oracle-database/insert-update-delete-select-operations-using-biztalk-server-with-oracle-db.md)します。  
  
- WCF サービス モデルを使用してこれらの操作を実行するを参照してください[Insert、Update、Delete、および WCF サービス モデルを使用して操作を選択](../../adapters-and-accelerators/adapter-oracle-database/insert-update-delete-select-operations-in-oracle-db-using-a-wcf-service.md)します。  
  
- WCF チャネル モデルを使用してこれらの操作を実行するを参照してください[WCF チャネル モデルを使用して Oracle データベースで挿入操作を実行](../../adapters-and-accelerators/adapter-oracle-database/run-an-insert-operation-in-oracle-database-using-the-wcf-channel-model.md)します。  
  
- メッセージの構造と DML 操作を実行するための SOAP アクションを参照してください[、基本的な挿入、更新、削除、およびテーブルおよびビューの選択操作のメッセージ スキーマ](../../adapters-and-accelerators/adapter-oracle-database/message-schemas-for-insert-update-delete-and-select-on-tables-and-views.md)します。  
  
## <a name="see-also"></a>参照  
 [どのような操作は、アダプターを使用して実行しますか?](https://msdn.microsoft.com/library/cc185219(v=bts.10).aspx)