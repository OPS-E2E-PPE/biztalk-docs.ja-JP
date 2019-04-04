---
title: 挿入、更新、削除、または WCF サービス モデルを使用して Oracle データベースで操作を選択します |。Microsoft Docs
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
ms.openlocfilehash: 91fa9b1828a8519dcbf7e1efba1db99ba84f1d0d
ms.sourcegitcommit: 266308ec5c6a9d8d80ff298ee6051b4843c5d626
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 06/27/2018
ms.locfileid: "36982451"
---
# <a name="insert-update-delete-or-select-operations-in-oracle-database-using-the-wcf-service-model"></a>挿入、更新、削除、または WCF サービス モデルを使用して Oracle データベースで操作を選択します。
[!INCLUDE[adapteroracle](../../includes/adapteroracle-md.md)]サーフェスの基本的な Insert、Update、Delete、および Oracle データベースのテーブルおよびビューに対する Select 操作のセット。 これらの操作を使用すると、単純な SQL INSERT、UPDATE、SELECT を実行し、DELETE ステートメントの対象のテーブルまたはビューの WHERE 句で修飾できます。 たとえば、SQL SELECT クエリの結合演算子を使用するより複雑な操作を実行するには、SQLEXECUTE 操作を使用できます。 SQLEXECUTE 操作の詳細については、[WCF サービス モデルを使用して Oracle Database SQLEXECUTE 操作を実行する](../../adapters-and-accelerators/adapter-oracle-database/run-sqlexecute-operation-in-oracle-database-using-the-wcf-service-model.md)を参照してください。  
  
 次の表は、SQL の基本的な操作をまとめたものですが、[!INCLUDE[adapteroracle_short](../../includes/adapteroracle-short-md.md)]テーブルとビューのサーフェイス。 これらの操作の詳細については、[、基本的な挿入、更新、削除、およびテーブルおよびビューの選択操作のメッセージ スキーマ](../../adapters-and-accelerators/adapter-oracle-database/message-schemas-for-insert-update-delete-and-select-on-tables-and-views.md)を参照してください。  
  
|演算|説明|  
|---------------|-----------------|  
|Insert|挿入操作では、対象のテーブルまたはビューに複数のレコードまたは一括挿入をサポートしています。<br /><br /> -複数のレコードの挿入操作では、テーブルまたは指定されたレコード セットに基づいたビューに行を挿入します。<br />-一括挿入操作では、テーブルまたは指定した SQL SELECT クエリ、列リストに基づいたビューに行を挿入します。 クエリから返されるレコードは、列リストに基づく対象テーブルに挿入されます。|  
|Select|指定された列の名前と SQL の WHERE 句を指定するフィルター文字列の一覧に基づく対象テーブルに対して SQL SELECT クエリを実行します。|  
|更新|対象テーブルに対して更新プログラムを実行します。 更新するレコードは、SQL の WHERE 句を指定するフィルター文字列によって指定されます。 更新プログラムの値は、テンプレートのレコードで指定されます。|  
|DELETE|フィルター文字列で指定されている SQL の WHERE 句に基づいて対象テーブルに対して DELETE を実行します。|  
  
## <a name="about-the-examples-used-in-this-topic"></a>このトピックで使用する例について  
 このトピックの例では、/SCOTT/ACCOUNTACTIVITY テーブルを使用します。 このテーブルを生成するスクリプトは SDK のサンプルで提供されます。 SDK サンプルの詳細については、[SDK 内のサンプル](../../core/samples-in-the-sdk.md)を参照してください。  
  
## <a name="the-wcf-client-class"></a>WCF クライアント クラス  
 基本的な SQL 操作に対して生成された WCF クライアントの名前を[!INCLUDE[adapteroracle_short](../../includes/adapteroracle-short-md.md)]サーフェスは、テーブルまたは次の表のように、ビューの名前に基づきます。  
  
|Oracle データベース成果物|WCF クライアント名|  
|------------------------------|---------------------|  
|テーブル|[スキーマ]テーブル [TABLE_NAME] のクライアント|  
|表示|[スキーマ]ビュー [VIEW_NAME] クライアント|  
  
 [スキーマ] コレクションの Oracle の成果物を =たとえば、SCOTT です。  
  
 [TABLE_NAME] テーブルの名前を =たとえば、ACCOUNTACTIVITY です。  
  
 [VIEW_NAME] ビューの名前を = です。  
  
 次の表では、テーブルに対する基本的な SQL 操作のメソッド シグネチャを示します。 署名は、ビューの名前空間と名前のテーブルを置換する点を除いて表示は、同じです。  
  
|演算|メソッド シグネチャ|  
|---------------|----------------------|  
|Insert|挿入時間の長い ([TABLE_NS]. [TABLE_NAME] RECORDINSERT [レコード セット、それらをクエリ文字列の文字列)。|  
|Select|[TABLE_NS]。[TABLE_NAME]RECORDSELECT] を選択します (文字列それら、文字列フィルター)|  
|更新|更新時間の長い ([TABLE_NS]. [TABLE_NAME] RECORDUPDATE はレコード セット、文字列フィルター)|  
|DELETE|時間の長い (文字列フィルター) を削除します。|  
  
 [TABLE_NS] テーブル、名前空間の名前を =たとえば、microsoft.lobservices.oracledb._2007._03.SCOTT します。Table.ACCOUNTACTIVITY します。  
  
 [TABLE_NAME] テーブルの名前を =たとえば、ACCOUNTACTIVITY です。  
  
 Insert、Update、および選択操作で使用されるレコードの種類では、すべてが、テーブルで定義されているまたは名前空間を表示します。  
  
 SCOTT/ACCOUNTACTIVITY テーブルに対する操作、Delete、Insert、Select および Update の次のコードに示す WCF クライアント クラスのメソッド シグネチャが生成されます。  
  
```  
public partial class SCOTTTableACCOUNTACTIVITYClient : System.ServiceModel.ClientBase<SCOTTTableACCOUNTACTIVITY>, SCOTTTableACCOUNTACTIVITY {  
  
    public long Delete(string FILTER);  
  
    public long Insert(microsoft.lobservices.oracledb._2007._03.SCOTT.Table.ACCOUNTACTIVITY.ACCOUNTACTIVITYRECORDINSERT[] RECORDSET, string COLUMN_NAMES, string QUERY);  
  
    public microsoft.lobservices.oracledb._2007._03.SCOTT.Table.ACCOUNTACTIVITY.ACCOUNTACTIVITYRECORDSELECT[] Select(string COLUMN_NAMES, string FILTER);  
  
    public long Update(microsoft.lobservices.oracledb._2007._03.SCOTT.Table.ACCOUNTACTIVITY.ACCOUNTACTIVITYRECORDUPDATE RECORDSET, string FILTER);  
}  
```  
  
## <a name="invoking-the-basic-sql-operations"></a>基本的な SQL の操作を呼び出す  
 WCF クライアントを使用してテーブルまたはビューに対する基本的な SQL 操作を呼び出すには、次の手順を実行します。  
  
1. 対象のテーブルまたはビューの WCF クライアント クラスを生成します。 このクラスは、対象のアイテムに呼び出す操作のメソッドを含める必要があります。  
  
2. WCF クライアント クラスのインスタンスを作成し、テーブルまたはビューに対する操作を実行するには、そのメソッドを呼び出します。  
  
   WCF クライアント クラスを作成し、操作を呼び出す方法についての詳細、[!INCLUDE[adapteroracle_short](../../includes/adapteroracle-short-md.md)]を参照してください[Oracle データベース アダプターを使用した WCF サービス モデルの概要](../../adapters-and-accelerators/adapter-oracle-database/overview-of-the-wcf-service-model-with-the-oracle-database-adapter.md)します。  
  
   [!INCLUDE[adapteroracle_short](../../includes/adapteroracle-short-md.md)] Oracle データベースで、トランザクション内で各操作を実行します。 このトランザクションの分離レベルを設定して制御することができます、 **TransactionIsolationLevel**プロパティをバインドします。 詳細については、[!INCLUDE[adapteroracle_short](../../includes/adapteroracle-short-md.md)]バインドのプロパティを参照してください[BizTalk Adapter for Oracle Database バインド プロパティの操作](https://msdn.microsoft.com/library/dd788467.aspx)します。  
  
   次のセクションでは、コードで基本的な各 SQL 操作を呼び出す方法の詳細について詳しく説明します。  
  
###  <a name="BKMK_InsertOperation"></a> 挿入操作  
 次の表では、複数のレコード挿入にパラメーターを設定し、一括挿入操作する方法を示します。  
  
|挿入操作の種類|レコード セット|それら|QUERY|  
|---------------------------|---------------|-------------------|-----------|  
|複数のレコード|ターゲットに挿入する必要があります INSERTRECORDS のコレクション。|null|null|  
|一括|null|は、ターゲット内の列名のコンマ区切りの一覧たとえば、「TID, アカウント」です。 列の一覧には、列を挿入された行ごとに、クエリの結果を配置する必要がありますを指定します。 クエリでは、両方の数と種類で列リストで指定された列に一致する結果セットを返す必要があります。|データベース テーブルまたはビューを返す結果セットは、ターゲットに挿入する SQL SELECT クエリたとえば、"NEW_TRANSACTIONS WHERE アカウントから選択する (TID, アカウント) = 100001"。 結果セットは、両方の数と種類で列リストと一致する必要があります。|  
  
 挿入操作では、ターゲットに挿入されたレコードの数を返します。  
  
> [!IMPORTANT]
>  WCF サービス モデルでは、挿入操作で使用されるレコード セットは、厳密に型指定されたです。 Nillable 列の値を設定する**null**で挿入操作; から列を除外するレコードただしは設定できませんを nillable 以外の列の値**null**します。 つまり、複数のレコードの挿入操作、各レコード内のすべての非 nillable 列の値を指定する必要があります。 さらはありません、基本的な SQL 操作のストリーミング サポート、WCF サービス モデルを使用する場合です。 場合は、複数のレコードの挿入操作では、大量のレコード セットでは、重要な考慮事項があります。 詳細については、[WCF サービス モデルを使用して基本的な SQL 操作の呼び出しの制限事項](#BKMK_LimitationsInvoking)を参照してください。  
  
 次のコードは、複数レコード挿入の操作 (2 つのレコード) を ACCOUNTACTIVITY テーブルを対象とします。  
  
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
 次の表では、選択操作のパラメーターを示します。  
  
|それら|FILTER|  
|-------------------|------------|  
|は、ターゲット内の列名のコンマ区切りの一覧たとえば、「TID, アカウント」です。 列の一覧には、結果セットで返される対象の列を指定します。 列リストで指定されていない列は、返されたレコード セット内の .NET の既定値に設定されます。 Nillable 列は、この値は**null**します。|クエリの対象の行を指定する SQL の WHERE 句の内容たとえば、"説明 = 'Insert レコード 1'"です。 このパラメーターを設定する**null**をターゲットのすべての行を返します。|  
  
 選択操作では、対象の行の型に基づいて厳密に型指定されたレコード セットを返します。  
  
> [!IMPORTANT]
>  WCF サービス モデルを使用すると、基本的な SQL 操作のストリーミング サポートはありません。 クエリでは、大量のレコード セットが返された場合は、WCF チャネル モデルを使用してパフォーマンスを向上させることができます。 詳細については、[WCF サービス モデルを使用して基本的な SQL 操作の呼び出しの制限事項](#BKMK_LimitationsInvoking)を参照してください。  
  
 次のコードでは、ACCOUNTACTIVITY テーブルを対象とする操作を選択します。 返されるレコードは、コンソールに書き込まれます。  
  
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
>  このコードは、作成、構成、および WCF クライアントのインスタンスを開く手順を省略します。 次の手順を含む、例では、[挿入操作](#BKMK_InsertOperation)を参照してください。  
  
### <a name="update-operation"></a>更新操作  
 次の表では、更新操作のパラメーターを示します。  
  
|レコード セット|FILTER|  
|---------------|------------|  
|対象の行の型に基づいて厳密に型指定されたテンプレートのレコードです。 テンプレートのレコードには、対象の行の更新プログラムの値を指定します。 Nillable 行の列を特定の行で、列を更新しないことを示すために null 値を指定できます。|ターゲットで更新する行を指定する SQL の WHERE 句の内容。 たとえば、"説明 = 'Inserted レコード 1'"です。|  
  
 更新操作では、ターゲットから削除された行の数を返します。  
  
> [!IMPORTANT]
>  WCF サービス モデルでは、更新操作で使用されるテンプレート レコードは、厳密に型指定されたが。 列が nillable の場合は、その値に設定して、更新操作から列を省略できます**null**テンプレート レコードでただし、列は、nillable がない場合する必要があります設定テンプレート レコード内の値。 たとえば、列が主キーの場合、値を含める必要があります。 詳細については、[WCF サービス モデルを使用して基本的な SQL 操作の呼び出しの制限事項](#BKMK_LimitationsInvoking)を参照してください。  
  
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
>  このコードは、作成、構成、および WCF クライアントのインスタンスを開く手順を省略します。 次の手順を含む、例では、[挿入操作](#BKMK_InsertOperation)を参照してください。  
  
### <a name="delete-operation"></a>削除操作  
 次の表では、削除操作のパラメーターを示します。  
  
|FILTER|  
|------------|  
|ターゲットから削除する行を指定する SQL の WHERE 句の内容。 たとえば、"説明 = 'Inserted レコード 1'"です。|  
  
 削除操作は、ターゲットから削除された行の数を返します。 次のコードでは、ACCOUNTACTIVITY テーブルを対象とする削除操作を示します。  
  
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
>  このコードは、作成、構成、および WCF クライアントのインスタンスを開く手順を省略します。 次の手順を含む、例では、、[挿入操作](#BKMK_InsertOperation)を参照してください。  
  
##  <a name="BKMK_LimitationsInvoking"></a> WCF サービス モデルを使用して基本的な SQL 操作の呼び出しの制限事項  
 WCF クライアントを使用して SQL の基本的な操作を呼び出すときに、次の制限があります。  
  
- **操作を挿入します。** 複数のレコード挿入操作で使用されるレコード セットは厳密に型指定され、そのためにすべての行の列が含まれます。 [!INCLUDE[adapteroracle_short](../../includes/adapteroracle-short-md.md)]を意味するレコード内の null 値を解釈するには、列は、挿入操作から除外する必要があります。 ただし、null 値に設定することはできませんので nillable 以外の列を除外することはできません。 そのため、複数のレコード挿入操作を実行するときに nillable ではない列の値を指定する必要があります。  
  
- **操作を挿入します。** [!INCLUDE[adapteroracle_short](../../includes/adapteroracle-short-md.md)]解釈、 **DbNull**列を複数のレコード挿入操作から除外することを意味する nillable データ列の値。 つまりに nillable 列を設定することはできません**DbNull**複数レコードの Oracle データベースで操作を挿入します。  
  
- **操作を挿入します。** 大量のレコード セットに関連する複数のレコードの挿入操作のストリーミング サポートはありません。  
  
- **操作を更新します。** 更新操作で使用されるテンプレート レコードは厳密に型指定し、そのためにすべての行の列が含まれます [!INCLUDE[adapteroracle_short](../../includes/adapteroracle-short-md.md)]を意味するには、このレコードに null 値を解釈するには、列は更新操作から除外する必要があります。 ただし、それらを null 値にできないので nillable 以外の列を除外することはできません。 したがって、更新操作を実行するときは、nillable 以外の列の値を指定する必要があります。  
  
- **操作を更新します。** [!INCLUDE[adapteroracle_short](../../includes/adapteroracle-short-md.md)]解釈、 **DbNull** nillable データの列に列を操作から除外することを意味するテンプレートのレコード値。 つまりに nillable 列を設定することはできません**DbNull**更新操作を使用して Oracle データベースでします。  
  
- **操作を選択します。** 大量のレコード セットを返す SELECT クエリのストリーミング サポートはありません。  
  
  これらの制限に課題が存在する場合は、ために、WCF チャネル モデルを使用して、操作を呼び出すことができます。  
  
- WCF チャネル モデルを使用すると、更新、挿入操作から特定のデータ列を除外できます。  
  
- WCF チャネル モデル ノード レベルのストリーミング サポートの基本的な SQL 操作を提供、[!INCLUDE[adapteroracle_short](../../includes/adapteroracle-short-md.md)]を公開します。  
  
  使用した WCF チャネル モデルを使用しての詳細については、[!INCLUDE[adapteroracle_short](../../includes/adapteroracle-short-md.md)]を参照してください[開発 Oracle データベース アプリケーションを使用して、WCF チャネル モデル](../../adapters-and-accelerators/adapter-oracle-database/develop-oracle-database-applications-using-the-wcf-channel-model.md)します。  
  
## <a name="see-also"></a>参照  
 [WCF チャネル モデルを使用して Oracle データベース アプリケーションを開発します。](../../adapters-and-accelerators/adapter-oracle-database/develop-oracle-database-applications-using-the-wcf-channel-model.md)