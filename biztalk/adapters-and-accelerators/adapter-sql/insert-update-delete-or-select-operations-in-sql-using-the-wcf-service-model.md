---
title: 挿入、更新、削除、または WCF サービス モデルを使用して SQL の操作の選択 |Microsoft ドキュメント
ms.custom: ''
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: ''
ms.suite: ''
ms.tgt_pltfrm: ''
ms.topic: article
ms.assetid: 340048ad-ce28-4acf-ae4e-f18bdb3b6f47
caps.latest.revision: 14
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: d2bc522a1b0b60a9ba0b8407228dd1db65c4e6f0
ms.sourcegitcommit: 8418b1a8f38b7f56979cd6e203f0b591e2f40fe1
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 03/23/2018
ms.locfileid: "22226090"
---
# <a name="insert-update-delete-or-select-operations-in-sql-using-the-wcf-service-model"></a>挿入、更新、削除、または WCF サービス モデルを使用して SQL の操作の選択
[!INCLUDE[adaptersql](../../includes/adaptersql-md.md)]一連の SQL Server データベース テーブルおよびビューの基本的な Insert、Select、Update、および削除操作を検出します。 これらの操作を使用することができますを実行して単純な SQL Insert、Select、Update、Delete ステートメントで Where 修飾対象のテーブルまたはビューの句。 このトピックでは、WCF サービス モデルを使用してこれらの操作を実行する方法について説明します。  
  
 アダプターがこれらの操作をサポートする方法の詳細については、次を参照してください。 [Insert、Update、Delete、およびテーブルおよび SQL アダプターとビューの選択操作](../../adapters-and-accelerators/adapter-sql/insert-update-delete-and-select-on-tables-and-views-with-the-sql-adapter.md)です。  
  
> [!NOTE]
>  ユーザー定義型の列を含むテーブルでの操作を実行する場合、必ずするを参照してください[テーブルと、SQL アダプターを使用してユーザー定義型を持つビューに対して操作](../../adapters-and-accelerators/adapter-sql/operations-on-tables-and-views-with-user-defined-types-using-the-sql-adapter.md)アプリケーションの開発を開始する前にします。  
  
## <a name="about-the-examples-used-in-this-topic"></a>このトピックで使用する例について  
 このトピックの例では、Employee テーブルでの操作を実行します。 サンプルに用意されている SQL スクリプトを実行して、従業員テーブルが作成されます。 サンプルの詳細については、次を参照してください。[アダプタ サンプル](../../adapters-and-accelerators/accelerator-rosettanet/adapter-samples.md)です。 サンプルは、 **EmployeeBasicOps**、これは、このトピックの内容に基づいても付属、[!INCLUDE[adaptersqlshort](../../includes/adaptersqlshort-md.md)]サンプルです。  
  
## <a name="the-wcf-client-class"></a>WCF クライアント クラス  
 基本的な SQL 操作の生成、WCF クライアントの名前を[!INCLUDE[adaptersqlshort](../../includes/adaptersqlshort-md.md)]検出は次の表に示すと、テーブルまたはビューの名前に基づいています。  
  
|SQL Server のデータベース成果物|WCF クライアント名|  
|----------------------------------|---------------------|  
|Table|TableOp_[Schema]_[TABLE_NAME]Client|  
|表示|ViewOp_[Schema]_[VIEW_NAME]Client|  
  
 [スキーマ]; SQL Server のコレクション アイテムを =たとえば、dbo します。  
  
 [TABLE_NAME] テーブルの名前を =たとえば、従業員です。  
  
 [VIEW_NAME] ビューの名前を =たとえば、Employee_View です。  
  
### <a name="method-signature-for-invoking-operations-on-tables"></a>テーブルに対する操作を呼び出すためのメソッド シグネチャ  
 次の表は、テーブルの基本的な操作について、メソッド シグネチャを示します。 署名は、ビューの名前空間と名前のテーブルを置換する点を除いて、表示は、同じです。  
  
|操作|メソッド シグネチャ|  
|---------------|----------------------|  
|Insert|長い [挿入 ([TABLE_NS]. [TABLE_NAME] 行) です。|  
|Select|[TABLE_NS].[TABLE_NAME][] Select(string COLUMNS, string QUERY);|  
|Update|int 更新 ([TABLE_NS]. [TABLE_NAME] です。RowPair:operator[] 行) です。|  
|Del|int Delete([TABLE_NS].[TABLE_NAME][] Rows);|  
  
 [TABLE_NS] テーブルの名前空間の名前を =たとえば、schemas.microsoft.com.Sql._2008._05.Types.Tables.dbo.Employee です。  
  
 [TABLE_NAME] テーブルの名前を =たとえば、従業員です。  
  
 例としては、次のコードは、既定値"dbo"スキーマの下にある従業員テーブルで Delete、Insert、Select および Update 操作に対して生成される WCF クライアント クラスのメソッドのシグニチャを示します。  
  
```  
public partial class TableOp_dbo_EmployeeClient : System.ServiceModel.ClientBase<TableOp_dbo_Employee>, TableOp_dbo_Employee {      
    public int Delete(schemas.microsoft.com.Sql._2008._05.Types.Tables.dbo.Employee[] Rows);  
  
    public long[] Insert(schemas.microsoft.com.Sql._2008._05.Types.Tables.dbo.Employee[] Rows);  
  
    public schemas.microsoft.com.Sql._2008._05.Types.Tables.dbo.Employee[] Select(string Columns, string Query);  
  
    public int Update(schemas.microsoft.com.Sql._2008._05.TableOp.dbo.Employee.RowPair[] Rows);  
}  
```  
  
 このスニペットでは、TableOp_dbo_EmployeeClient はによって生成された SqlAdapterBindingClient.cs で WCF クラスの名前、[!INCLUDE[addadapterservrefshort](../../includes/addadapterservrefshort-md.md)]です。  
  
### <a name="parameters-for-table-operations"></a>テーブル操作のパラメーター  
 このセクションでは、各テーブルの操作に必要なパラメーターを説明します。  
  
 **挿入操作**  
  
|挿入操作の種類|レコード セット|  
|---------------------------|---------------|  
|複数のレコード|テーブルに挿入する必要があります INSERTRECORDS のコレクション。|  
  
 挿入操作では、長い形式のデータ型の配列を返し、存在する場合、挿入された行の id 値を格納します。 テーブル内に id 列がない場合、戻り値は NULL です。  
  
 **操作を選択します。**  
  
|COLUMN_NAMES|QUERY|  
|-------------------|-----------|  
|ターゲット内の列名のコンマ区切りの一覧たとえば、「Employee_ID, 表記」です。 列の一覧では、結果セットに返される対象の列を指定します。 列リストで指定されていない列は、返されるレコード セット内の .NET の既定値に設定されます。 Nillable 列は、この値は**null**です。|クエリの対象の行を指定する SQL の WHERE 句の内容たとえば、"表記 = 'Manager'"です。 このパラメーターを設定することができます**null**ターゲットのすべての行を取得します。|  
  
 Select 操作の戻り値は、指定された列と対象のテーブルまたはビューから行を含む厳密に型指定された結果セットです。  
  
 **更新操作**  
  
|ペアの最初の行|ペアの 2 番目の行|  
|---------------------------|----------------------------|  
|ペアが、更新する必要のある新しい値に対応するレコードの最初のレコードに対応して、UPDATE ステートメントの SET 句。 使用して設定できます`RowPair.After`です。|レコードのペアの 2 番目のレコードの行の古い値、つまり、UPDATE ステートメントの WHERE 句に対応します。 使用して設定できます`RowPair.Before`です。|  
  
 更新操作の戻り値は、Int32 データ型では、更新された行の数を表します。  
  
> [!IMPORTANT]
>  更新する必要のあるレコードを指定する際にすべての値が更新されていない場合でも、すべての列の値を指定する必要があります。 たとえば、行に 5 つの列があり、ユーザーが、更新操作が RowPair.Before の一部としてのみに 2 つの列を更新は、5 つの列のすべての値を渡す必要があります。 ただし、RowPair.After、更新される列のみを指定できます。  
  
 **削除操作**  
  
 削除操作は、レコードの配列を厳密に型指定された入力として受け取ります。 削除操作の戻り値は、Int32 データ型では、削除された行の数を表します。  
  
## <a name="creating-a-wcf-client-to-invoke-operations-on-tables-and-views"></a>テーブルおよびビューの操作の呼び出しに WCF クライアントを作成します。  
 WCF クライアントを使用して SQL Server で操作の実行に必要なアクションの汎用的なセットは、一連のタスクで説明されている[SQL アダプターで WCF サービス モデルの概要](../../adapters-and-accelerators/adapter-sql/overview-of-the-wcf-service-model-with-the-sql-adapter.md)です。 このセクションでは、基本的な Insert、Select、Update、テーブルに対する削除操作を呼び出すための WCF クライアントを作成する方法について説明します。  
  
#### <a name="to-create-a-wcf-client-to-perform-operations-on-tables"></a>テーブルに対する操作を実行する WCF クライアントを作成するには  
  
1.  Visual Studio で Visual c# プロジェクトを作成します。 このトピックでは、コンソール アプリケーションを作成します。  
  
2.  Insert、Select、Update の WCF クライアント クラスを生成し、Employee テーブルの操作を削除します。 詳細については、WCF クライアント クラスを生成する、次を参照してください。 [SQL Server の成果物のために、WCF クライアントまたは WCF サービス コントラクトを生成](../../adapters-and-accelerators/adapter-sql/generate-a-wcf-client-or-wcf-service-contract-for-sql-server-artifacts.md)です。  
  
    > [!IMPORTANT]
    >  WCF クライアント クラスを生成する前に必ず設定してください、 **EnableBizTalkCompatibilityMode**プロパティを false にバインドします。  
  
3.  ソリューション エクスプ ローラーへの参照を追加`Microsoft.Adapters.Sql`と`Microsoft.ServiceModel.Channels`です。  
  
4.  Program.cs ファイルを開き、次のスニペットの説明に従って、クライアントを作成します。  
  
    ```  
  
              TableOp_dbo_EmployeeClient client = new TableOp_dbo_EmployeeClient("SqlAdapterBinding_TableOp_dbo_Employee");  
    client.ClientCredentials.UserName.UserName = "<Enter user name here>";  
    client.ClientCredentials.UserName.Password = "<Enter password here>";  
    ```  
  
     このスニペットで`TableOp_dbo_EmployeeClient`SqlAdapterBindingClient.cs で定義された WCF クライアントです。 このファイルにより生成されて、[!INCLUDE[addadapterservrefshort](../../includes/addadapterservrefshort-md.md)]です。 `SqlAdapterBinding_TableOp_dbo_Employee` クライアント エンドポイント構成の名前を指定、app.config で定義されます。このファイルがによって生成されても、[!INCLUDE[addadapterservrefshort](../../includes/addadapterservrefshort-md.md)]バインドのプロパティおよびその他の構成設定が含まれています。  
  
    > [!NOTE]
    >  このスニペットでは、構成ファイルからバインディングとエンドポイント アドレスを使用します。 これらの値は、コードで明示的に指定できます。 クライアント バインディングを指定するさまざまな方法の詳細については、次を参照してください。 [SQL アダプタのクライアントのバインディングを構成する](../../adapters-and-accelerators/adapter-sql/configure-a-client-binding-for-the-sql-adapter.md)です。  
  
5.  次のスニペット」の説明に従って、クライアントを開きます。  
  
    ```  
    try  
    {  
       Console.WriteLine("Opening Client...");  
       client.Open();  
    }  
    catch (Exception ex)  
    {  
       Console.WriteLine("Exception: " + ex.Message);  
       throw;  
    }  
    ```  
  
6.  Employee テーブルに対する挿入操作を呼び出します。  
  
    ```  
    long[] recordsInserted;  
  
    schemas.microsoft.com.Sql._2008._05.Types.Tables.dbo.Employee[] insertRecord =  
    new schemas.microsoft.com.Sql._2008._05.Types.Tables.dbo.Employee[1];  
  
    insertRecord[0] = new schemas.microsoft.com.Sql._2008._05.Types.Tables.dbo.Employee();  
    insertRecord[0].Name = "John Smith";  
    insertRecord[0].Designation = "Manager";  
    insertRecord[0].Salary = 500000;  
  
    try  
    {  
       Console.WriteLine("Inserting new table entry...");  
       recordsInserted = client.Insert(insertRecord);  
    }  
    catch (Exception ex)  
    {  
       Console.WriteLine("Exception: " + ex.Message);  
       throw;  
    }  
  
    Console.WriteLine("Record inserted");  
    Console.WriteLine("Press any key to continue ...");  
    Console.ReadLine();  
    ```  
  
     Select を実行する上記のコード スニペットを置き換えることができますを更新、または同様の操作を削除します。 1 つのアプリケーションのすべての操作を実行するコード スニペットを追加することもできます。 これらの操作を実行する方法のコード スニペット。  
  
7.  次のスニペット」の説明に従って、クライアントを閉じます。  
  
    ```  
    client.Close();  
    Console.WriteLine("Press any key to exit...");  
    Console.ReadLine();  
    ```  
  
8.  プロジェクトをビルドし、それを実行します。 アプリケーションは、Employee テーブルにレコードを挿入します。  
  
###   <a name="select-operation"></a>操作を選択します。  
 次のコードは、Employee テーブルを対象とする選択操作を示しています。 選択操作は、テーブルに挿入された最後のレコードを選択します。 返されたレコードは、コンソールに書き込まれます。  
  
```  
schemas.microsoft.com.Sql._2008._05.Types.Tables.dbo.Employee[] selectRecords;  
  
try  
{  
   Console.WriteLine("Selecting Row...");  
   selectRecords = client.Select("*", "where [Employee_ID] = (select IDENT_CURRENT('Employee'))");  
}  
  
catch (Exception ex)  
{  
   Console.WriteLine("Exception: " + ex.Message);  
   throw;  
}  
  
Console.WriteLine("The details of the newly added employee are:");  
Console.WriteLine("********************************************");  
for (int i = 0; i < selectRecords.Length; i++)  
{  
   Console.WriteLine("Employee ID        : " + selectRecords[i].Employee_ID);  
   Console.WriteLine("Employee Name      : " + selectRecords[i].Name);  
   Console.WriteLine("Employee Desigation: " + selectRecords[i].Designation);  
   Console.WriteLine();  
}  
Console.WriteLine("********************************************");  
Console.WriteLine("Press any key to continue ...");  
Console.ReadLine();  
```  
  
###   <a name="update-operation"></a>更新操作  
 次のコードでは、Employee テーブルを対象とする更新操作を示します。  
  
```  
int result;  
  
schemas.microsoft.com.Sql._2008._05.TableOp.dbo.Employee.RowPair updateRecordPair =  
   new schemas.microsoft.com.Sql._2008._05.TableOp.dbo.Employee.RowPair();  
  
schemas.microsoft.com.Sql._2008._05.Types.Tables.dbo.Employee updateRecord =   
   new schemas.microsoft.com.Sql._2008._05.Types.Tables.dbo.Employee();  
  
schemas.microsoft.com.Sql._2008._05.TableOp.dbo.Employee.RowPair[] updateArray =  
   new schemas.microsoft.com.Sql._2008._05.TableOp.dbo.Employee.RowPair[1];  
  
updateRecord = insertRecord[0];  
updateRecord.Name = "Jeff Smith";  
  
updateRecordPair.After = updateRecord;  
updateRecordPair.Before = selectRecords[0];  
  
updateArray[0] = updateRecordPair;  
  
try  
{  
   Console.WriteLine("Updating the database...");  
   result = client.Update(updateArray);  
}  
catch (Exception ex)  
{  
   Console.WriteLine("Exception: " + ex.Message);  
   throw;  
}  
  
Console.WriteLine("Updated Record for {0}", updateRecordPair.Before.Name);  
Console.WriteLine("The new name for the employee is {0}", updateRecordPair.After.Name);  
Console.WriteLine("Press any key to continue ...");  
Console.ReadLine();  
```  
  
###   <a name="delete-operation"></a>削除操作  
 次のコードは、Employee テーブルを対象とする削除操作を示しています。  
  
```  
int deleteSuccess;  
  
schemas.microsoft.com.Sql._2008._05.Types.Tables.dbo.Employee[] deleteRecords =  
   new schemas.microsoft.com.Sql._2008._05.Types.Tables.dbo.Employee[1];  
  
deleteRecords = client.Select("*", "where [Employee_ID] = (select IDENT_CURRENT('Employee'))");  
  
Console.WriteLine("Following employees will be deleted from the database:");  
for (int i = 0; i < deleteRecords.Length; i++)  
{  
   Console.WriteLine("Name: {0}", deleteRecords[i].Name);  
}  
Console.WriteLine("Press any key to begin deletion...");  
Console.ReadLine();  
  
try  
{  
   Console.WriteLine("Deleting employee record...");  
   deleteSuccess = client.Delete(deleteRecords);  
}  
  
catch (Exception ex)  
{  
   Console.WriteLine("Exception: " + ex.Message);  
   throw;  
}  
```  
  
## <a name="see-also"></a>参照  
[WCF サービス モデルを使用してアプリケーションを開発する](../../adapters-and-accelerators/adapter-sql/develop-sql-applications-using-the-wcf-service-model.md)