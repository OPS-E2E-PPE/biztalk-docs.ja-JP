---
title: 挿入、更新、削除、または WCF サービス モデルを使用して Oracle データベースで操作の選択 |Microsoft ドキュメント
ms.custom: ''
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: ''
ms.suite: ''
ms.tgt_pltfrm: ''
ms.topic: article
helpviewer_keywords:
- WCF service model, Delete operation
- WCF service model, Select operation
- WCF service model, Insert operation
- WCF service model, Update operation
ms.assetid: d1a9f44f-ea0b-4dd6-9489-fa0d963848c4
caps.latest.revision: 5
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: f312f0fa967c08fabbc27c9269abaae68b9ac958
ms.sourcegitcommit: cb908c540d8f1a692d01dc8f313e16cb4b4e696d
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 09/20/2017
ms.locfileid: "22217490"
---
# <a name="insert-update-delete-or-select-operations-in-oracle-database-using-the-wcf-service-model"></a>挿入、更新、削除、または WCF サービス モデルを使用して Oracle データベースで操作の選択
[!INCLUDE[adapteroracle](../../includes/adapteroracle-md.md)]基本的な Insert、Update、Delete、および Oracle データベースのテーブルおよびビューに対する Select 操作のセットを表示します。 これらの操作を使用すると、単純な SQL INSERT、UPDATE、SELECT を実行し、対象のテーブルまたはビューの WHERE 句で修飾されたステートメントを削除できます。 たとえば、SQL SELECT クエリを結合演算子を使用して、複雑な操作を実行するには、SQLEXECUTE 操作を行うこともできます。 SQLEXECUTE 操作の詳細については、次を参照してください。 [WCF サービス モデルを使用して Oracle データベース SQLEXECUTE 操作を実行する](../../adapters-and-accelerators/adapter-oracle-database/run-sqlexecute-operation-in-oracle-database-using-the-wcf-service-model.md)です。  
  
 次の表に、SQL の基本的な操作を[!INCLUDE[adapteroracle_short](../../includes/adapteroracle-short-md.md)]テーブルとビューを表示します。 これらの操作の詳細については、次を参照してください。 [、基本的な Insert、Update、Delete、およびテーブルおよびビューに対する選択操作のメッセージ スキーマを](../../adapters-and-accelerators/adapter-oracle-database/message-schemas-for-insert-update-delete-and-select-on-tables-and-views.md)です。  
  
|操作|Description|  
|---------------|-----------------|  
|Insert|挿入操作では、対象のテーブルまたはビューに複数のレコードまたは一括挿入をサポートしています。<br /><br /> は、複数のレコードの挿入操作は、テーブルまたは指定されたレコード セットに基づいたビューに行を挿入します。<br />は、一括挿入操作は、テーブルまたはビューのリストに基づく指定された SQL SELECT クエリと列に行を挿入します。 クエリから返されるレコードは、列リストに基づく対象のテーブルに挿入されます。|  
|Select|指定された列名と SQL の WHERE 句を指定するフィルター文字列の一覧に基づいて、対象テーブルでの SQL SELECT クエリを実行します。|  
|Update|対象のテーブルの更新プログラムを実行します。 更新するレコードは、SQL の WHERE 句を指定するフィルター文字列によって指定されます。 更新プログラムの値は、テンプレートのレコードで指定されます。|  
|DELETE|SQL の WHERE 句に基づいてフィルター文字列で指定されている対象のテーブルに対して DELETE を実行します。|  
  
## <a name="about-the-examples-used-in-this-topic"></a>このトピックで使用する例について  
 このトピックの例では、/SCOTT/ACCOUNTACTIVITY テーブルを使用します。 このテーブルを生成するスクリプトは、SDK サンプルの値が提供されます。 SDK サンプルの詳細については、次を参照してください。 [SDK 内のサンプル](../../core/samples-in-the-sdk.md)です。  
  
## <a name="the-wcf-client-class"></a>WCF クライアント クラス  
 基本的な SQL 操作の生成、WCF クライアントの名前を[!INCLUDE[adapteroracle_short](../../includes/adapteroracle-short-md.md)]サーフェスは、テーブルまたは次の表のように、ビューの名前に基づきます。  
  
|Oracle データベース アイテム|WCF クライアント名|  
|------------------------------|---------------------|  
|テーブル|[スキーマ]テーブル [TABLE_NAME] クライアント|  
|表示|[スキーマ]ビュー [VIEW_NAME] クライアント|  
  
 [スキーマ] コレクションの Oracle の成果物を =たとえば、SCOTT です。  
  
 [TABLE_NAME] テーブルの名前を =たとえば、ACCOUNTACTIVITY です。  
  
 [VIEW_NAME] ビューの名前を = です。  
  
 次の表は、テーブルの基本的な SQL 操作のメソッドのシグニチャを示します。 署名は、ビューの名前空間と名前のテーブルを置換する点を除いて、表示は、同じです。  
  
|操作|メソッド シグネチャ|  
|---------------|----------------------|  
|Insert|挿入長い ([TABLE_NS]. [TABLE_NAME] RECORDINSERT [RECORDSET、それらを文字列クエリの文字列) です。|  
|Select|[TABLE_NS] です。[TABLE_NAME]RECORDSELECT を選択 (それら、フィルターの文字列の文字列) です。|  
|Update|時間を更新 ([TABLE_NS]. [TABLE_NAME] RECORDUPDATE レコード セットをフィルターの文字列) です。|  
|DELETE|長い Delete (フィルターの文字列) です。|  
  
 [TABLE_NS] テーブルの名前空間の名前を =たとえば、microsoft.lobservices.oracledb._2007._03.SCOTT です。Table.ACCOUNTACTIVITY です。  
  
 [TABLE_NAME] テーブルの名前を =たとえば、ACCOUNTACTIVITY です。  
  
 Insert、Update、および Select 操作で使用されるレコードの種類は、すべてが、テーブルで定義されているまたは名前空間を表示します。  
  
 SCOTT/ACCOUNTACTIVITY テーブルでの操作、Delete、Insert、Select および Update の次のコードに示す WCF クライアント クラスのメソッド シグネチャが生成されます。  
  
```  
public partial class SCOTTTableACCOUNTACTIVITYClient : System.ServiceModel.ClientBase<SCOTTTableACCOUNTACTIVITY>, SCOTTTableACCOUNTACTIVITY {  
  
    public long Delete(string FILTER);  
  
    public long Insert(microsoft.lobservices.oracledb._2007._03.SCOTT.Table.ACCOUNTACTIVITY.ACCOUNTACTIVITYRECORDINSERT[] RECORDSET, string COLUMN_NAMES, string QUERY);  
  
    public microsoft.lobservices.oracledb._2007._03.SCOTT.Table.ACCOUNTACTIVITY.ACCOUNTACTIVITYRECORDSELECT[] Select(string COLUMN_NAMES, string FILTER);  
  
    public long Update(microsoft.lobservices.oracledb._2007._03.SCOTT.Table.ACCOUNTACTIVITY.ACCOUNTACTIVITYRECORDUPDATE RECORDSET, string FILTER);  
}  
```  
  
## <a name="invoking-the-basic-sql-operations"></a>基本的な SQL の操作を呼び出す  
 WCF クライアントを使用して、テーブルまたはビューの基本的な SQL 操作を呼び出すには、次の手順を実行します。  
  
1.  対象のテーブルまたはビューの WCF クライアント クラスを生成します。 このクラスは、ターゲットの成果物に呼び出すことができる操作のメソッドを含める必要があります。  
  
2.  WCF クライアント クラスのインスタンスを作成し、テーブルまたはビューに対する操作を実行するには、そのメソッドを呼び出します。  
  
 詳細については、WCF クライアント クラスを作成し、に対して操作を呼び出す方法については、[!INCLUDE[adapteroracle_short](../../includes/adapteroracle-short-md.md)]を参照してください[Oracle データベース アダプターで WCF サービス モデルの概要](../../adapters-and-accelerators/adapter-oracle-database/overview-of-the-wcf-service-model-with-the-oracle-database-adapter.md)です。  
  
 [!INCLUDE[adapteroracle_short](../../includes/adapteroracle-short-md.md)] Oracle データベースで、トランザクション内で各操作を実行します。 このトランザクションの分離レベルを設定して制御することができます、 **TransactionIsolationLevel**プロパティをバインドします。 詳細については、[!INCLUDE[adapteroracle_short](../../includes/adapteroracle-short-md.md)]バインドのプロパティを参照してください[BizTalk Adapter 用 Oracle Database バインド プロパティの操作](https://msdn.microsoft.com/library/dd788467.aspx)です。  
  
 次のセクションでは、コード内の各基本 SQL 操作を呼び出す方法について詳しく説明します。  
  
###  <a name="BKMK_InsertOperation"></a>挿入操作  
 次の表は、複数のレコード挿入のパラメーターを設定し、一括挿入操作する方法を示します。  
  
|挿入操作の種類|レコード セット|それら|QUERY|  
|---------------------------|---------------|-------------------|-----------|  
|複数のレコード|ターゲットに挿入する必要がある INSERTRECORDS のコレクション。|null|null|  
|一括|null|ターゲット内の列名のコンマ区切りの一覧たとえば、「TID, アカウント」です。 列の一覧では、これには、挿入された行ごとに、クエリの結果を配置する列を指定します。 クエリでは、数と型の両方で列リストで指定された列に一致する結果セットを返す必要があります。|データベース テーブルまたはビューをターゲットに挿入する、結果セットを返します上の SQL SELECT クエリたとえば、"NEW_TRANSACTIONS WHERE アカウントから選択 (TID、アカウント) = 100001"です。 結果セットは、数と型の両方で列リストと一致する必要があります。|  
  
 挿入操作では、ターゲットに挿入されたレコードの数を返します。  
  
> [!IMPORTANT]
>  WCF サービス モデルでは、挿入操作で使用されるレコード セットは、厳密に型指定されたです。 Nillable 列の値を設定することができます**null** ; の挿入操作からその列を除外するレコードにただし、値は設定できません、nillable ではない列の**null**です。 つまり、複数のレコードの挿入操作、各レコードのすべての非 nillable 列の値を指定する必要があります。 さらは基本的な SQL 操作のストリーミング サポート、WCF サービス モデルを使用する場合です。 複数のレコードの挿入操作には、大量のレコード セットが含まれている場合、重要な考慮事項があります。 詳細については、次を参照してください。 [WCF サービス モデルを使用して基本的な SQL 操作の呼び出しの制限事項](#BKMK_LimitationsInvoking)です。  
  
 次のコードは、複数レコードの挿入操作 (2 つのレコード) を ACCOUNTACTIVITY テーブルを対象とするを示します。  
  
```  
// Insert records  
                using (SCOTTTableACCOUNTACTIVITYClient aaTableClient =   
                    new SCOTTTableACCOUNTACTIVITYClient("OracleDBBinding_SCOTT.Table.ACCOUNTACTIVITY"))  
                {  
                    long recsInserted;  
  
                    aaTableClient.ClientCredentials.UserName.UserName = "SCOTT";  
                    aaTableClient.ClientCredentials.UserName.Password = "TIGER";  
  
                    try  
                    {  
                        aaTableClient.Open();  
                    }  
                    catch (Exception ex)  
                    {  
                        // handle exception  
                        Console.WriteLine("Exception: " + ex.Message);  
                        throw;  
                    }  
  
                    // Do a multiple record Insert of 2 records for account 100001  
  
                    microsoft.lobservices.oracledb._2007._03.SCOTT.Table.ACCOUNTACTIVITY.ACCOUNTACTIVITYRECORDINSERT[] insertRecs =  
                        new microsoft.lobservices.oracledb._2007._03.SCOTT.Table.ACCOUNTACTIVITY.ACCOUNTACTIVITYRECORDINSERT[2];  
  
                                  TID__COMPLEX_TYPE tid = new TID__COMPLEX_TYPE();  
                                  tid.InlineValue = "tidSequence.NextVal()";  
  
                                  ACCOUNT__COMPLEX_TYPE account = new ACCOUNT__COMPLEX_TYPE();  
                                  account.Value = 100001;  
  
                    AMOUNT__COMPLEX_TYPE amount = new AMOUNT__COMPLEX_TYPE();  
                    amount.Value = 400;  
  
                    TRANSDATE__COMPLEX_TYPE transdate = new TRANSDATE__COMPLEX_TYPE();  
                    transdate.Value = DateTime.Now.Date;  
  
                    PROCESSED__COMPLEX_TYPE processed = new PROCESSED__COMPLEX_TYPE();  
                    processed.Value = "n";  
  
                    DESCRIPTION__COMPLEX_TYPE description1 = new DESCRIPTION__COMPLEX_TYPE();  
                    description1.Value = "Inserted Record #1";  
  
                    DESCRIPTION__COMPLEX_TYPE description2 = new DESCRIPTION__COMPLEX_TYPE();  
                    description2.Value = "Inserted Record #2";  
  
                    insertRecs[0] =   
                        new microsoft.lobservices.oracledb._2007._03.SCOTT.Table.ACCOUNTACTIVITY.ACCOUNTACTIVITYRECORDINSERT();  
                    insertRecs[0].TID = tid;  
                    insertRecs[0].ACCOUNT = account;  
                    insertRecs[0].AMOUNT = amount;  
                    insertRecs[0].TRANSDATE = transdate;  
                    insertRecs[0].DESCRIPTION = description1;  
                    insertRecs[0].PROCESSED = processed;  
  
                    insertRecs[1] =   
                        new microsoft.lobservices.oracledb._2007._03.SCOTT.Table.ACCOUNTACTIVITY.ACCOUNTACTIVITYRECORDINSERT();  
                    insertRecs[1].TID = tid;  
                    insertRecs[1].ACCOUNT = account;  
                    insertRecs[1].AMOUNT = amount;  
                    insertRecs[1].TRANSDATE = transdate;  
                    insertRecs[1].DESCRIPTION = description2;  
                    insertRecs[1].PROCESSED = processed;  
  
                    try  
                    {  
                        recsInserted = aaTableClient.Insert(insertRecs, null, null);  
                    }  
                    catch (Exception ex)  
                    {  
                        // handle exception  
                        Console.WriteLine("Exception: " + ex.Message);  
                        throw;  
                    }  
  
                    Console.WriteLine("Insert Done: {0} records inserted", recsInserted);  
```  
  
### <a name="select-operation"></a>操作を選択します。  
 次の表は、Select 操作のパラメーターを示します。  
  
|それら|FILTER|  
|-------------------|------------|  
|ターゲット内の列名のコンマ区切りの一覧たとえば、「TID, アカウント」です。 列の一覧では、結果セットに返される対象の列を指定します。 列リストで指定されていない列は、返されるレコード セット内の .NET の既定値に設定されます。 Nillable 列は、この値は**null**です。|クエリの対象の行を指定する SQL の WHERE 句の内容たとえば、"説明 'Insert レコード 1' を ="です。 このパラメーターを設定することができます**null**ターゲットのすべての行を取得します。|  
  
 選択操作は、対象の行の型に基づいて厳密に型指定されたレコード セットを返します。  
  
> [!IMPORTANT]
>  WCF サービス モデルを使用すると、基本的な SQL 操作のストリーミング サポートはありません。 クエリでは、大量のレコード セットが返された場合は、WCF チャネル モデルを使用してパフォーマンスを向上させることができます。 詳細については、次を参照してください。 [WCF サービス モデルを使用して基本的な SQL 操作の呼び出しの制限事項](#BKMK_LimitationsInvoking)です。  
  
 次のコードは、ACCOUNTACTIVITY テーブルを対象とする選択操作を示しています。 返されたレコードは、コンソールに書き込まれます。  
  
```  
// Declare a variable to hold the result set  
microsoft.lobservices.oracledb._2007._03.SCOTT.Table.ACCOUNTACTIVITY.ACCOUNTACTIVITYRECORDSELECT[] selectRecords;  
  
// Select all records and write them to the console  
try  
{  
    selectRecords = aaTableClient.Select("*", null);  
}  
catch (Exception ex)  
{  
    // handle exception  
}  
  
Console.WriteLine("ACCOUNTACTIVITY before any operations");  
for (int i = 0; i \< selectRecords.Length; i++)  
{  
    Console.WriteLine("{0}\t{1}\t{2}\t{3}\t{4}", selectRecords[i].TID,  
    selectRecords[i].ACCOUNT,  
    selectRecords[i].AMOUNT,  
    selectRecords[i].TRANSDATE,  
    selectRecords[i].DESCRIPTION);  
}  
```  
  
> [!NOTE]
>  このコードは、作成、構成、および WCF クライアントのインスタンスを開く手順を省略します。 次の手順を含む例は、次を参照してください。 [Insert 操作](#BKMK_InsertOperation)です。  
  
### <a name="update-operation"></a>更新操作  
 次の表は、更新操作のパラメーターを示します。  
  
|レコード セット|FILTER|  
|---------------|------------|  
|ターゲットの行の種類に基づいて厳密に型指定されたテンプレートのレコードです。 テンプレートのレコードでは、特定の行の値の更新を指定します。 Nillable 行列では、特定の行で列を更新できないことを示すために、null 値を指定できます。|ターゲットで更新する行を指定する SQL の WHERE 句の内容です。 たとえば、"説明 'Inserted レコード 1' を ="です。|  
  
 更新操作では、ターゲットから削除された行の数を返します。  
  
> [!IMPORTANT]
>  WCF サービス モデルでは、更新操作で使用されるテンプレート レコードは、厳密に型指定されたがします。 その値を設定して、更新操作からの列を省略するには、列が nillable の場合は、 **null**テンプレート レコードです。 ただし、場合、列は、nillable ではありません必要があります設定するテンプレート レコード内の値。 たとえば、列が主キーの場合は、値を含める必要があります。 詳細については、次を参照してください。 [WCF サービス モデルを使用して基本的な SQL 操作の呼び出しの制限事項](#BKMK_LimitationsInvoking)です。  
  
 次のコードでは、ACCOUNTACTIVITY テーブルを対象とする更新操作を示します。  
  
```  
long recsUpdated;  
  
...  
  
// Create updated template. The TID, TIME, AMOUNT, and DESCRIPTION fields will be updated  
microsoft.lobservices.oracledb._2007._03.SCOTT.Table.ACCOUNTACTIVITY.ACCOUNTACTIVITYRECORDUPDATE updateRecord =  
    new microsoft.lobservices.oracledb._2007._03.SCOTT.Table.ACCOUNTACTIVITY.ACCOUNTACTIVITYRECORDUPDATE();  
        updateRecord.TID = tidSequence.NextVal();  
        updateRecord.ACCOUNT = null;  
        updateRecord.AMOUNT = 300;  
        updateRecord.TRANSDATE = DateTime.Now.Date;  
        updateRecord.DESCRIPTION = "Updated Record #2";  
        updateRecord.PROCESSED = null;  
  
// Set filter string to specify the target record by using the DESCRIPTION field  
string filter = "DESCRIPTION = 'Inserted Record #2'";  
  
try  
{  
    recsUpdated = aaTableClient.Update(updateRecord, filter);  
}  
catch (Exception ex)  
{  
    // handle exception  
    ...  
}  
  
Console.WriteLine("{0} records updated", recsUpdated);  
```  
  
> [!NOTE]
>  このコードは、作成、構成、および WCF クライアントのインスタンスを開く手順を省略します。 次の手順を含む例は、次を参照してください。 [Insert 操作](#BKMK_InsertOperation)です。  
  
### <a name="delete-operation"></a>削除操作  
 次の表は、削除操作のパラメーターを示します。  
  
|FILTER|  
|------------|  
|ターゲットから削除する行を指定する SQL の WHERE 句の内容です。 たとえば、"説明 'Inserted レコード 1' を ="です。|  
  
 削除操作では、ターゲットから削除された行の数を返します。 次のコードは、ACCOUNTACTIVITY テーブルを対象とする削除操作を示しています。  
  
```  
// Set filter string equal to the DESCRIPTION field of the target record  
string filter = "DESCRIPTION = 'Inserted Record #1'";  
  
try  
{  
    recsDeleted = aaTableClient.Delete(filter);  
}  
catch (Exception ex)  
{  
    // handle exception  
  
    ...  
}  
Console.WriteLine("{0} records deleted", recsDeleted);  
```  
  
> [!NOTE]
>  このコードは、作成、構成、および WCF クライアントのインスタンスを開く手順を省略します。 次の手順を含む例については、[挿入操作](#BKMK_InsertOperation)です。  
  
##  <a name="BKMK_LimitationsInvoking"></a>WCF サービス モデルを使用して基本的な SQL 操作を呼び出すことの制限事項  
 WCF クライアントを使用して SQL の基本的な操作を呼び出すときは、次の制限事項があります。  
  
-   **操作を挿入します。** 複数のレコード挿入操作で使用されるレコード セット厳密に型指定されたは、そのためにすべての行の列が含まれます。 [!INCLUDE[adapteroracle_short](../../includes/adapteroracle-short-md.md)]ことを意味するレコード内で null 値を解釈すること、列は、挿入操作から除外する必要があります。 ただし、null 値に設定することはできませんので nillable 以外の列を除外することはできません。 そのため、複数のレコード挿入操作を実行するときに非 nillable 列の値を指定する必要があります。  
  
-   **操作を挿入します。** [!INCLUDE[adapteroracle_short](../../includes/adapteroracle-short-md.md)]解釈、 **DbNull**列が複数のレコード挿入操作から除外されることを意味する nillable のデータ列の値。 つまり nillable 列を設定することはできません**DbNull**複数レコードの Oracle データベースで操作を挿入します。  
  
-   **操作を挿入します。** 大量のレコード セットを含む複数のレコードの挿入操作用のストリーミング サポートされていません。  
  
-   **操作を更新します。** 更新操作で使用されるテンプレート レコードは厳密に型指定された、そのためにすべての行の列が含まれます [!INCLUDE[adapteroracle_short](../../includes/adapteroracle-short-md.md)]ことを意味するには、このレコードに null 値を解釈する、列は、更新操作から除外する必要があります以外の場合は、null 値にできないするために非 nillable 列を除外することはできませんただし、します。 したがって、更新操作を実行するときに、nillable 以外の列の値を指定する必要があります。  
  
-   **操作を更新します。** [!INCLUDE[adapteroracle_short](../../includes/adapteroracle-short-md.md)]解釈、 **DbNull**列を操作から除外することを意味するテンプレート レコードで nillable データ列の値。 つまり nillable 列を設定することはできません**DbNull**更新操作を使用して Oracle データベースでします。  
  
-   **操作を選択します。** 大量のレコード セットを返す SELECT クエリのストリーミング サポートはありません。  
  
 これらの制限が課題のシナリオでは、モデルを使用して、WCF チャネルのため、操作を呼び出すことができます。  
  
-   WCF チャネル モデルを使用すると、更新、挿入操作から特定のデータ列を除外できます。  
  
-   基本的な SQL 操作の WCF チャネル モデルはノード レベルのストリーミング サポートを提供、[!INCLUDE[adapteroracle_short](../../includes/adapteroracle-short-md.md)]を公開します。  
  
 モデルを使用して、WCF チャネルでの詳細については、[!INCLUDE[adapteroracle_short](../../includes/adapteroracle-short-md.md)]を参照してください[開発 Oracle データベースのアプリケーション モデルを使用して、WCF チャネル](../../adapters-and-accelerators/adapter-oracle-database/develop-oracle-database-applications-using-the-wcf-channel-model.md)です。  
  
## <a name="see-also"></a>参照  
 [WCF チャネル モデルを使用して Oracle データベース アプリケーションを開発します。](../../adapters-and-accelerators/adapter-oracle-database/develop-oracle-database-applications-using-the-wcf-channel-model.md)