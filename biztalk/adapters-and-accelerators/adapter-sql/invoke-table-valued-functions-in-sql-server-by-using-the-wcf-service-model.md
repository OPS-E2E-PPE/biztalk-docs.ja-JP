---
title: WCF サービス モデルを使用して SQL Server でのテーブル値関数を呼び出す |Microsoft ドキュメント
ms.custom: ''
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: ''
ms.suite: ''
ms.tgt_pltfrm: ''
ms.topic: article
ms.assetid: 48688bcc-36b4-4cc1-b078-17e7a5e1cf8c
caps.latest.revision: 4
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: a736a82e57f71568f8718a6e4d41e7b649004120
ms.sourcegitcommit: cb908c540d8f1a692d01dc8f313e16cb4b4e696d
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 09/20/2017
ms.locfileid: "22224698"
---
# <a name="invoke-table-valued-functions-in-sql-server-by-using-the-wcf-service-model"></a>WCF サービス モデルを使用して SQL Server でのテーブル値関数を呼び出す
使用することができます、[!INCLUDE[adaptersqlshort](../../includes/adaptersqlshort-md.md)]モデルを使用して、WCF サービスを SQL Server でのテーブル値関数を呼び出す .NET アプリケーションでします。 アダプターは、SQL サーバー上で直接呼び出すことのできるメソッドとして、テーブル値関数を公開します。 アダプターがスカラー関数をサポートする方法の詳細については、次を参照してください。 [SQL アダプターを使用して SQL Server で Execute Table-Valued 関数](../../adapters-and-accelerators/adapter-sql/execute-table-valued-functions-in-sql-server-using-the-sql-adapter.md)です。  
  
 このトピックでは、SQL Server データベース内で、TVF_EMPLOYEE 関数を呼び出す方法を示します。 TVF_EMPLOYEE 関数が受け取る内の従業員の指定、**従業員**テーブルが表示され、従業員のレコードを返します。 TVF_EMPLOYEE 関数および**従業員**サンプルに用意されている SQL スクリプトを実行してテーブルを作成します。 詳細については、次を参照してください。[アダプタ サンプル](../../adapters-and-accelerators/accelerator-rosettanet/adapter-samples.md)です。  
  
## <a name="about-the-examples-used-in-this-topic"></a>このトピックで使用する例について  
 このトピックの例で TVF_EMPLOYEE テーブル値関数が呼び出される、**従業員**テーブル。 TVF_EMPLOYEE 関数および**従業員**サンプルに用意されている SQL スクリプトを実行してテーブルを作成します。 サンプルは、 **TableFunction_ServiceModel**、これは、このトピックの内容に基づいても付属、[!INCLUDE[adaptersqlshort](../../includes/adaptersqlshort-md.md)]サンプルです。 詳細については、次を参照してください。[アダプタ サンプル](../../adapters-and-accelerators/accelerator-rosettanet/adapter-samples.md)です。  
  
## <a name="the-wcf-client-class"></a>WCF クライアント クラス  
 SQL Server を使用してスカラー関数を呼び出すことの生成、WCF クライアントの名前、[!INCLUDE[adaptersqlshort](../../includes/adaptersqlshort-md.md)]次の表に記載されています。  
  
|SQL Server のデータベース成果物|WCF クライアント名|  
|----------------------------------|---------------------|  
|テーブル値関数|[スキーマ] TableValuedFunctions_ クライアント|  
  
 [スキーマ]; SQL Server のコレクション アイテムを =たとえば、dbo します。  
  
### <a name="method-signature-for-invoking-table-valued-functions"></a>テーブル値関数を呼び出すためのメソッド シグネチャ  
 次の表は、テーブルの基本的な操作について、メソッド シグネチャを示します。 署名は、ビューの名前空間と名前のテーブルを置換する点を除いて、表示は、同じです。  
  
|操作|メソッド シグネチャ|  
|---------------|----------------------|  
|テーブル値関数の名前|パブリックの名前空間 [FUNCTION_NAME] [FUNCTION_NAME] (param1、param2、.\)|  
  
 [名前空間] schemas.microsoft.com.Sql._2008._05.Types.TableFunctionReturnTables.dbo.TVF_EMPLOYEE など、名前空間を =  
  
 [FUNCTION_NAME]、テーブル値関数の名前を = です。  
  
 たとえば、次のコードにはメソッド シグネチャに関するの WCF クライアント クラスを生成、 **TVF_EMPLOYEE**をパラメーターとしての従業員の表記を取得し、従業員が返されます、dbo スキーマ内のスカラー関数レコードです。  
  
```  
public partial class TableValuedFunctions_dboClient : System.ServiceModel.ClientBase<TableValuedFunctions_dbo>, TableValuedFunctions_dbo {      
    public schemas.microsoft.com.Sql._2008._05.Types.TableFunctionReturnTables.dbo.TVF_EMPLOYEE[] TVF_EMPLOYEE(string emp_desig);  
}  
```  
  
 このスニペットで**TableValuedFunctions_dboClient**によって生成された SqlAdapterBindingClient.cs で WCF クラスの名前を指定します、[!INCLUDE[addadapterservrefshort](../../includes/addadapterservrefshort-md.md)]です。  
  
### <a name="parameters-for-invoking-table-valued-functions"></a>テーブル値関数の呼び出しのパラメーター  
 によって公開されるメソッドのパラメーター、[!INCLUDE[adaptersqlshort](../../includes/adaptersqlshort-md.md)]を呼び出す、テーブル値関数は、SQL Server で、関数定義で定義されたパラメーターと同じです。 たとえば、パラメーター TVF_EMPLOYEE テーブル値関数を呼び出す emp_desig は、従業員の表記を取得します。  
  
 ここでも、テーブル値関数の戻り値は、SQL Server 内で関数定義で定義されている戻り値と同じです。 たとえば、TVF_EMPLOYEE 関数の戻り値は type[] schemas.microsoft.com.Sql._2008._05.Types.TableFunctionReturnTables.dbo.TVF_EMPLOYEE のレコードの配列です。  
  
## <a name="creating-a-wcf-client-to-invoke-table-valued-functions"></a>テーブル値関数を呼び出すための WCF クライアントを作成します。  
 WCF クライアントを使用して SQL Server で操作の実行に必要なアクションの汎用的なセットは、一連のタスクで説明されている[SQL アダプターで WCF サービス モデルの概要](overview-of-the-wcf-service-model-with-the-sql-adapter.md)です。 このセクションを呼び出すための WCF クライアントを作成する方法について説明、 **TVF_EMPLOYEE**テーブル値関数です。  
  
 
1.  Visual c# プロジェクトを作成[!INCLUDE[btsVStudioNoVersion](../../includes/btsVStudioNoVersion-md.md)]です。 このトピックでは、コンソール アプリケーションを作成します。  
  
2.  WCF クライアント クラスを生成、 **TVF_EMPLOYEE**スカラー関数です。 詳細については、WCF クライアント クラスを生成する、次を参照してください。 [SQL Server の成果物のために、WCF クライアントまたは WCF サービス コントラクトを生成](generate-a-wcf-client-or-wcf-service-contract-for-sql-server-artifacts.md)です。  
  
3.  ソリューション エクスプ ローラーへの参照を追加`Microsoft.Adapters.Sql`と`Microsoft.ServiceModel.Channels`です。  
  
4.  Program.cs を開き、次のスニペットの説明に従って、クライアントを作成します。  
  
    ```  
  
              TableValuedFunctions_dboClient client = new TableValuedFunctions_dboClient("SqlAdapterBinding_TableValuedFunctions_dbo");  
    client.ClientCredentials.UserName.UserName = "<Enter user name here>";  
    client.ClientCredentials.UserName.Password = "<Enter password here>";  
    ```  
  
     このスニペットで`TableValuedFunctions_dboClient`SqlAdapterBindingClient.cs で定義された WCF クライアントです。 このファイルにより生成されて、[!INCLUDE[addadapterservrefshort](../../includes/addadapterservrefshort-md.md)]です。 `SqlAdapterBinding_TableValuedFunctions_dbo`クライアント エンドポイント構成の名前を指定、app.config で定義されます。このファイルがによって生成されても、[!INCLUDE[addadapterservrefshort](../../includes/addadapterservrefshort-md.md)]バインドのプロパティおよびその他の構成設定が含まれています。  
  
    > [!NOTE]
    >  このスニペットでは、構成ファイルからバインディングとエンドポイント アドレスを使用します。 これらの値は、コードで明示的に指定できます。 クライアント バインディングを指定し、さまざまな方法の詳細については、次を参照してください。 [SQL アダプタのクライアントのバインディングを構成する](configure-a-client-binding-for-the-sql-adapter.md)です。  
  
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
  
6.  呼び出す、 **TVF_EMPLOYEE** "Manager"表記を持つすべての従業員レコードを取得します。  
  
    ```  
    Console.WriteLine("Invoking the TVF_EMPLOYEE function");  
    schemas.microsoft.com.Sql._2008._05.Types.TableFunctionReturnTables.dbo.TVF_EMPLOYEE[] emp_details;  
    string emp_designation = "Manager";  
  
    try  
    {  
        emp_details = client.TVF_EMPLOYEE(emp_designation);  
    }  
    catch (Exception e)  
    {  
        Console.WriteLine("Exception: " + e.Message);  
        throw;  
    }  
    Console.WriteLine("The details for the employee with the 'Manager' designation are:");  
    Console.WriteLine("*******************************************************************");  
    for (int i = 0; i < emp_details.Length; i++)  
    {  
        Console.WriteLine("Employee ID        : " + emp_details[i].Employee_ID);  
        Console.WriteLine("Employee Name      : " + emp_details[i].Name);  
        Console.WriteLine("Employee Desigation: " + emp_details[i].Designation);  
        Console.WriteLine("Employee Salary    : " + emp_details[i].Salary);  
        Console.WriteLine();  
    }  
    ```  
  
7.  次のスニペット」の説明に従って、クライアントを閉じます。  
  
    ```  
    client.Close();  
    Console.WriteLine("Press any key to exit...");  
    Console.ReadLine();  
    ```  
  
8.  プロジェクトをビルドし、それを実行します。 アプリケーションでは、従業員 ID、名、および"Manager"が指定のすべての従業員の給与が表示されます。  
  
## <a name="see-also"></a>参照  
[WCF サービス モデルを使用してアプリケーションを開発します。](develop-sql-applications-using-the-wcf-service-model.md)