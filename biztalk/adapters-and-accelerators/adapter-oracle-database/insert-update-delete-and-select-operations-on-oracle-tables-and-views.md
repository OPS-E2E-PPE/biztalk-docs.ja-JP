---
title: "Insert、Update、Delete、および Oracle のテーブルおよびビューに対する Select 操作 |Microsoft ドキュメント"
ms.custom: 
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: 
ms.suite: 
ms.tgt_pltfrm: 
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
caps.latest.revision: "6"
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: 04770dd5004d46df93da71b910cc228be1751ae7
ms.sourcegitcommit: cb908c540d8f1a692d01dc8f313e16cb4b4e696d
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 09/20/2017
---
# <a name="insert-update-delete-and-select-operations-on-oracle-tables-and-views"></a>挿入、更新、削除、および Oracle テーブルとビューの操作の選択
[!INCLUDE[adapteroracle](../../includes/adapteroracle-md.md)] Oracle データベースのテーブルとビューごとに、標準的な操作のセットを表示します。 これらの操作を使用すると、単純な SQL INSERT、UPDATE、SELECT を実行し、対象のテーブル (またはビュー) に WHERE 句で修飾されたステートメントを削除できます。 これらの操作は、データ操作言語 (DML) 操作とも呼ばれます。 たとえば、SQL SELECT クエリを結合演算子を使用して、複雑な操作を実行するには、SQLEXECUTE 操作を行うこともできます。 SQLEXECUTE 操作の詳細については、次を参照してください。 [Oracle データベースで SQLEXECUTE 操作](../../adapters-and-accelerators/adapter-oracle-database/sqlexecute-operation-in-oracle-database.md)です。  
  
 次の表は、DML 操作を[!INCLUDE[adapteroracle_short](../../includes/adapteroracle-short-md.md)]をサポートしています。  
  
|操作|Description|  
|---------------|-----------------|  
|Insert|対象のテーブルまたはビューに対する Insert 操作を実行します。 挿入操作では、対象のテーブルまたはビューに複数のレコードまたは一括挿入をサポートしています。<br /><br /> は、複数のレコードの挿入操作は、テーブルまたは指定されたレコード セットに基づいたビューに行を挿入します。<br /><br /> は、一括挿入操作は、テーブルまたはビューのリストに基づく指定された SQL SELECT クエリと列に行を挿入します。 クエリから返されるレコードは、列リストに基づく対象のテーブルに挿入されます。<br /><br /> 挿入操作の戻り値は、挿入された行の数です。<br /><br /> **注:**両方の複数のレコードを挿入し、同じメッセージ内に一括挿入を組み合わせることができません。<br /><br /> **InlineValue**<br /><br /> 複数のレコード挿入操作ですべての単純なデータ レコードを選択できますと呼ばれる省略可能な属性の値を指定することによって、レコードの値をオーバーライドする**InlineValue**です。 InlineValue 属性は、テーブルまたは日付の列に主キー列のシーケンスまたは (SYSDATE を使用して) システムの日付を挿入することを設定するなどのビューに計算値を挿入を使用することができます。 たとえば、次のステートメントを挿入します。<br /><br /> `<Insert xmlns="http://Microsoft.LobServices.OracleDB/2007/03/SCOTT/Table/ACCOUNTACTIVITY">   <RECORDSET>     <ACCOUNTACTIVITYRECORDINSERT>       <ACCOUNT>10001</ACCOUNT>       <EMPNAME>John</EMPNAME>       <AMOUNT>1500</AMOUNT>       <TRANSDATE InlineValue="SYSDATE">2008-06-21T15:52:19</TRANSDATE>       </ACCOUNTACTIVITYRECORDINSERT >   </RECORDSET> </Insert>`<br /><br /> にもかかわらず"2008-06-21T15:52:19"は"SYSDATE、"InlineValue 属性の値であるトランザクション日付列の値として指定された (システムの日付) に挿入されます、対象のテーブルです。<br /><br /> InlineValue の使用中に次のように属性します。<br /><br /> -InlineValue 属性の定数値を使用しないでください。 たとえばを指定する場合に、INSERT ステートメントで`<EMPNAME InlineValue="John"/>`エラーが発生し、します。 これとに InlineValue 属性の値が渡されるために、-、Oracle、し、ここでは*John*予期される値ではない Oracle データベースに渡される (期待される値は*"John"*)。 従業員名を囲む単一引用符を使用する必要があります。 たとえば、 `<EMPNAME InlineValue="’John’"/>`のようにします。<br /><br /> -InlineValue 属性の選択クエリを使用する場合、SELECT ステートメントをかっこで囲みますも select クエリが単一のレコードだけをフェッチすることを確認してください。 たとえば、 `<EMPNAME InlineValue="(SELECT NAME FROM MS_SAMPLE_EMPLOYEES WHERE ID=123)"/>`のようにします。<br /><br /> **注:**要素が、Oracle データベースで NOT NULL としてマークされている場合は、インライン値を指定した場合でもその要素の値を指定する必要があります。 これを行うがスキーマ検証が失敗します。|  
|Select|対象のテーブルまたは指定された列名と SQL の WHERE 句を指定するフィルター文字列の一覧に基づいたビューを SQL SELECT クエリを実行します。<br /><br /> Select 操作の戻り値は、指定された列と行を含む厳密に型指定された結果セットです。|  
|Update|対象のテーブルまたはビューの更新操作を実行します。 更新するレコードは、SQL の WHERE 句を指定するフィルター文字列によって指定されます。 更新プログラムの値は、テンプレートのレコードで指定されます。<br /><br /> 更新操作の戻り値は、更新された行の数です。|  
|DELETE|対象のテーブルまたは、SQL の WHERE 句に基づいてフィルター文字列で指定されているビューに対して Delete 操作を実行します。<br /><br /> 削除操作の戻り値は、削除された行の数です。|  
  
 詳細については。  
  
-   使用してこれらの操作を実行する[!INCLUDE[btsBizTalkServerNoVersion](../../includes/btsbiztalkservernoversion-md.md)]を参照してください[挿入、更新、削除、および選択操作を使用して BizTalk Server によって](../../adapters-and-accelerators/adapter-oracle-database/insert-update-delete-select-operations-using-biztalk-server-with-oracle-db.md)です。  
  
-   WCF サービス モデルを使用してこれらの操作を実行するを参照してください[Insert、Update、Delete、および WCF サービス モデルを使用して操作を選択して](../../adapters-and-accelerators/adapter-oracle-database/insert-update-delete-select-operations-in-oracle-db-using-a-wcf-service.md)です。  
  
-   WCF チャネル モデルを使用してこれらの操作を実行するを参照してください[WCF チャネル モデルを使用して Oracle データベースで挿入操作を実行](../../adapters-and-accelerators/adapter-oracle-database/run-an-insert-operation-in-oracle-database-using-the-wcf-channel-model.md)です。  
  
-   メッセージの構造と DML 操作を実行するための SOAP アクションを参照してください[、基本的な Insert、Update、Delete、およびテーブルおよびビューに対する選択操作のメッセージ スキーマを](../../adapters-and-accelerators/adapter-oracle-database/message-schemas-for-insert-update-delete-and-select-on-tables-and-views.md)です。  
  
## <a name="see-also"></a>参照  
 [どのような操作をアダプターであるを使用して実行しますか?](https://msdn.microsoft.com/library/cc185219(v=bts.10).aspx)