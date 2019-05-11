---
title: 挿入、更新、削除、または WCF サービス モデルを使用して SQL の操作を選択します |。Microsoft Docs
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
ms.openlocfilehash: ed0b353ddfd5a04ba2eafc0205d7d154e2049c33
ms.sourcegitcommit: 381e83d43796a345488d54b3f7413e11d56ad7be
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 05/07/2019
ms.locfileid: "65369436"
---
# <a name="insert-update-delete-or-select-operations-in-sql-using-the-wcf-service-model"></a>挿入、更新、削除、または WCF サービス モデルを使用して SQL の操作を選択します。
[!INCLUDE[adaptersql](../../includes/adaptersql-md.md)]一連の SQL Server データベースのテーブルおよびビューに対する Insert、Select、Update、および Delete の基本的な操作を検出します。 これらの操作を使用すると、実行の単純な SQL Insert、Select、Update、および Delete ステートメントで Where 修飾対象のテーブルまたはビューの句。 このトピックでは、WCF サービス モデルを使用してこれらの操作を実行する方法について説明します。  
  
 アダプターがこれらの操作をサポートする方法の詳細については、次を参照してください。 [Insert、Update、Delete、およびテーブルとビューを SQL アダプターを使用した操作の選択](../../adapters-and-accelerators/adapter-sql/insert-update-delete-and-select-on-tables-and-views-with-the-sql-adapter.md)します。  
  
> [!NOTE]
>  ユーザー定義型の列を含むテーブルに対して操作を実行している場合ことを確認するを参照してください[テーブルと、SQL アダプターを使用してユーザー定義型を持つビューで操作](../../adapters-and-accelerators/adapter-sql/operations-on-tables-and-views-with-user-defined-types-using-the-sql-adapter.md)アプリケーションの開発を開始する前にします。  
  
## <a name="about-the-examples-used-in-this-topic"></a>このトピックで使用する例について  
 このトピックの例では、Employee テーブルに対する操作を実行します。 サンプルで提供される SQL スクリプトを実行して、従業員テーブルが作成されます。 サンプルの詳細については、次を参照してください。[アダプタ サンプル](../../adapters-and-accelerators/accelerator-rosettanet/adapter-samples.md)します。 サンプルについては、 **EmployeeBasicOps**、これは、このトピックに基づいてがで提供されていることも、[!INCLUDE[adaptersqlshort](../../includes/adaptersqlshort-md.md)]サンプル。  
  
## <a name="the-wcf-client-class"></a>WCF クライアント クラス  
 基本的な SQL 操作に対して生成された WCF クライアントの名前を[!INCLUDE[adaptersqlshort](../../includes/adaptersqlshort-md.md)]検出、次の表に示すように、テーブルまたはビューの名前に基づきます。  
  
|SQL Server データベースの成果物|WCF クライアント名|  
|----------------------------------|---------------------|  
|テーブル|TableOp_ [Schema] _ [TABLE_NAME] のクライアント|  
|表示|ViewOp_ [Schema] _ [VIEW_NAME] のクライアント|  
  
 [スキーマ] コレクションの SQL Server のアイテム、=たとえば、dbo です。  
  
 [TABLE_NAME] テーブルの名前を =たとえば、従業員です。  
  
 [VIEW_NAME] ビューの名前を =たとえば、Employee_View です。  
  
### <a name="method-signature-for-invoking-operations-on-tables"></a>テーブルに対する操作を呼び出すためのメソッド シグネチャ  
 次の表では、テーブルに対する基本操作のメソッド シグネチャを示します。 署名は、ビューの名前空間と名前のテーブルを置換する点を除いて表示は、同じです。  
  
|演算|メソッド シグネチャ|  
|---------------|----------------------|  
|Insert|long[] Insert([TABLE_NS].[TABLE_NAME][] Rows);|  
|Select|[TABLE_NS].[TABLE_NAME][] Select(string COLUMNS, string QUERY);|  
|更新|int Update([TABLE_NS].[TABLE_NAME].RowPair[] Rows);|  
|DELETE|int Delete([TABLE_NS].[TABLE_NAME][] Rows);|  
  
 [TABLE_NS] テーブル、名前空間の名前を =たとえば、schemas.microsoft.com.Sql._2008._05.Types.Tables.dbo.Employee します。  
  
 [TABLE_NAME] テーブルの名前を =たとえば、従業員です。  
  
 例としては、次のコードは、既定値"dbo"スキーマの Employee テーブルに対する Delete、Insert、Select および Update 操作に対して生成された WCF クライアント クラスのメソッド シグネチャを示します。  
  
```  
public partial class TableOp_dbo_EmployeeClient : System.ServiceModel.ClientBase<TableOp_dbo_Employee>, TableOp_dbo_Employee {      
    public int Delete(schemas.microsoft.com.Sql._2008._05.Types.Tables.dbo.Employee[] Rows);  
  
    public long[] Insert(schemas.microsoft.com.Sql._2008._05.Types.Tables.dbo.Employee[] Rows);  
  
    public schemas.microsoft.com.Sql._2008._05.Types.Tables.dbo.Employee[] Select(string Columns, string Query);  
  
    public int Update(schemas.microsoft.com.Sql._2008._05.TableOp.dbo.Employee.RowPair[] Rows);  
}  
```  
  
 このスニペットで TableOp_dbo_EmployeeClient はによって生成された SqlAdapterBindingClient.cs で WCF クラスの名前、[!INCLUDE[addadapterservrefshort](../../includes/addadapterservrefshort-md.md)]します。  
  
### <a name="parameters-for-table-operations"></a>テーブル操作のパラメーター  
 このセクションでは、各テーブルの操作に必要なパラメーターを提供します。  
  
 **挿入操作**  
  
|挿入操作の種類|レコード セット|  
|---------------------------|---------------|  
|複数のレコード|テーブルに挿入する必要があります INSERTRECORDS のコレクション。|  
  
 挿入操作では、長い形式のデータ型の配列を返し、存在する場合、挿入された行の id 値を格納します。 テーブル内に id 列がない場合、戻り値は NULL です。  
  
 **操作を選択します。**  
  
|それら|QUERY|  
|-------------------|-----------|  
|は、ターゲット内の列名のコンマ区切りの一覧たとえば、「Employee_ID, 指定」です。 列の一覧には、結果セットで返される対象の列を指定します。 列リストで指定されていない列は、返されたレコード セット内の .NET の既定値に設定されます。 Nillable 列は、この値は**null**します。|クエリの対象の行を指定する SQL の WHERE 句の内容たとえば、"指定 = 'マネージャー'"です。 このパラメーターを設定する**null**をターゲットのすべての行を返します。|  
  
 選択操作の戻り値は、指定された列と対象のテーブルまたはビューから行を含む厳密に型指定された結果セットです。  
  
 **更新操作**  
  
|ペアの最初の行|ペアの 2 行目|  
|---------------------------|----------------------------|  
|ペアが、更新する必要がある新しい値に対応するレコードの最初のレコードは、対応、UPDATE ステートメントの SET 句にします。 使用して設定できます`RowPair.After`します。|レコードのペアの 2 番目のレコード行の古い値、つまり、UPDATE ステートメントの WHERE 句に対応します。 使用して設定できます`RowPair.Before`します。|  
  
 更新操作の戻り値では、Int32 データ型では、更新された行の数を表します。  
  
> [!IMPORTANT]
>  更新する必要のあるレコードを指定するには、中にすべての値が更新されていない場合でも、すべての列の値を指定する必要があります。 たとえば場合は、行は 5 つの列を備え、更新操作では、2 つだけの列を更新 RowPair.Before の一部として、すべての 5 つの列値を渡す必要があります。 ただし、RowPair.After、更新される列のみを指定できます。  
  
 **削除操作**  
  
 削除操作はレコードの配列を厳密に型指定の入力として受け取ります。 削除操作の戻り値では、Int32 データ型では、削除された行の数を表します。  
  
## <a name="creating-a-wcf-client-to-invoke-operations-on-tables-and-views"></a>テーブルおよびビューの操作を呼び出すための WCF クライアントを作成します。  
 WCF クライアントを使用して SQL Server で操作の実行に必要なアクションの汎用的なセットは、一連のタスクで説明されている[SQL アダプターを使用した WCF サービス モデルの概要](../../adapters-and-accelerators/adapter-sql/overview-of-the-wcf-service-model-with-the-sql-adapter.md)します。 このセクションでは、基本的な Insert、Select、Update、テーブルに対する削除操作を呼び出すための WCF クライアントを作成する方法について説明します。  
  
#### <a name="to-create-a-wcf-client-to-perform-operations-on-tables"></a>テーブルに対する操作を実行する WCF クライアントを作成するには  
  
1. Visual Studio で Visual c# プロジェクトを作成します。 このトピックでは、コンソール アプリケーションを作成します。  
  
2. Insert、Select、Update、WCF クライアント クラスを生成し、Employee テーブルに対して操作を削除します。 WCF クライアント クラスを生成する詳細については、次を参照してください。 [SQL Server のアイテムの WCF クライアントまたは WCF サービス コントラクトを生成](../../adapters-and-accelerators/adapter-sql/generate-a-wcf-client-or-wcf-service-contract-for-sql-server-artifacts.md)します。  
  
   > [!IMPORTANT]
   >  WCF クライアント クラスを生成する前に必ず設定して、 **EnableBizTalkCompatibilityMode**プロパティを false にバインドします。  
  
3. ソリューション エクスプ ローラーへの参照を追加`Microsoft.Adapters.Sql`と`Microsoft.ServiceModel.Channels`します。  
  
4. Program.cs ファイルを開き、次のスニペットの説明に従って、クライアントを作成します。  
  
   ```  
  
             TableOp_dbo_EmployeeClient client = new TableOp_dbo_EmployeeClient("SqlAdapterBinding_TableOp_dbo_Employee");  
   client.ClientCredentials.UserName.UserName = "<Enter user name here>";  
   client.ClientCredentials.UserName.Password = "<Enter password here>";  
   ```  
  
    このスニペットで`TableOp_dbo_EmployeeClient`SqlAdapterBindingClient.cs で定義されている WCF クライアントです。 このファイルがによって生成された、[!INCLUDE[addadapterservrefshort](../../includes/addadapterservrefshort-md.md)]します。 `SqlAdapterBinding_TableOp_dbo_Employee` クライアント エンドポイント構成の名前を指定され、app.config で定義されます。このファイルがによって生成されても、[!INCLUDE[addadapterservrefshort](../../includes/addadapterservrefshort-md.md)]バインドのプロパティとその他の構成設定が含まれています。  
  
   > [!NOTE]
   >  このスニペットでは、構成ファイルからバインドおよびエンドポイント アドレスを使用します。 これらの値は、コードで明示的に指定できます。 クライアント バインディングを指定する、さまざまな方法の詳細については、次を参照してください。 [SQL アダプタのクライアントのバインディングを構成する](../../adapters-and-accelerators/adapter-sql/configure-a-client-binding-for-the-sql-adapter.md)します。  
  
5. 次のスニペットで説明されているように、クライアントを開きます。  
  
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
  
6. Employee テーブルに対する挿入操作を呼び出します。  
  
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
  
    Select を実行する前のコード スニペットを置き換えることができます更新、または同様の操作を削除します。 単一のアプリケーションですべての操作を実行するコード スニペットを追加することもできます。 これらの操作を実行する方法のコード スニペット。  
  
7. 次のスニペットの説明に従って、クライアントを閉じます。  
  
   ```  
   client.Close();  
   Console.WriteLine("Press any key to exit...");  
   Console.ReadLine();  
   ```  
  
8. プロジェクトをビルドし、それを実行します。 アプリケーションでは、Employee テーブルにレコードを挿入します。  
  
###   <a name="select-operation"></a>操作を選択します。  
 次のコードでは、Employee テーブルを対象とする操作を選択します。 選択操作では、テーブルに挿入された最後のレコードを選択します。 返されるレコードは、コンソールに書き込まれます。  
  
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
 次のコードでは、Employee テーブルを対象とする削除操作を示します。  
  
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