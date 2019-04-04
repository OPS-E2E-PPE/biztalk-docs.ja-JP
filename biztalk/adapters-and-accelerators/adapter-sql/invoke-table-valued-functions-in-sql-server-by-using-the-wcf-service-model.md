---
title: WCF サービス モデルを使用して SQL Server でのテーブル値関数を呼び出す |Microsoft Docs
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
ms.openlocfilehash: f4243973f6e6b04cddec14261d5b1acedff4b9e0
ms.sourcegitcommit: 266308ec5c6a9d8d80ff298ee6051b4843c5d626
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 06/27/2018
ms.locfileid: "36989163"
---
# <a name="invoke-table-valued-functions-in-sql-server-by-using-the-wcf-service-model"></a>WCF サービス モデルを使用して SQL Server でのテーブル値関数を呼び出す
使用することができます、[!INCLUDE[adaptersqlshort](../../includes/adaptersqlshort-md.md)]で SQL Server でのテーブル値関数を呼び出すための WCF サービス モデルを使用して .NET アプリケーション。 アダプターは、SQL サーバー上で直接呼び出すことができるメソッドとして、テーブル値関数を公開します。 アダプターがスカラー関数をサポートする方法の詳細については、[SQL アダプターを使用して SQL Server での Execute Table-Valued 関数](../../adapters-and-accelerators/adapter-sql/execute-table-valued-functions-in-sql-server-using-the-sql-adapter.md)を参照してください。  
  
 このトピックでは、SQL Server データベースで TVF_EMPLOYEE 関数を呼び出す方法を示します。 TVF_EMPLOYEE 関数は、従業員の指定、**従業員**テーブルが表示され、従業員のレコードを返します。 TVF_EMPLOYEE 関数と**従業員**サンプルで提供される SQL スクリプトを実行してテーブルが作成されます。 詳細については、[アダプタ サンプル](../../adapters-and-accelerators/accelerator-rosettanet/adapter-samples.md)を参照してください。  
  
## <a name="about-the-examples-used-in-this-topic"></a>このトピックで使用する例について  
 このトピックの例で TVF_EMPLOYEE テーブル値関数が呼び出される、**従業員**テーブル。 TVF_EMPLOYEE 関数と**従業員**サンプルで提供される SQL スクリプトを実行してテーブルが作成されます。 サンプルについては、 **TableFunction_ServiceModel**、これは、このトピックに基づいてがで提供されていることも、[!INCLUDE[adaptersqlshort](../../includes/adaptersqlshort-md.md)]サンプル。 詳細については、[アダプタ サンプル](../../adapters-and-accelerators/accelerator-rosettanet/adapter-samples.md)を参照してください。  
  
## <a name="the-wcf-client-class"></a>WCF クライアント クラス  
 SQL Server を使用してスカラー関数を呼び出すために生成された WCF クライアントの名前、[!INCLUDE[adaptersqlshort](../../includes/adaptersqlshort-md.md)]次の表に記載されています。  
  
|SQL Server データベースの成果物|WCF クライアント名|  
|----------------------------------|---------------------|  
|テーブル値関数|[スキーマ] TableValuedFunctions_ クライアント|  
  
 [スキーマ] コレクションの SQL Server のアイテム、=たとえば、dbo です。  
  
### <a name="method-signature-for-invoking-table-valued-functions"></a>テーブル値関数を呼び出すためのメソッド シグネチャ  
 次の表では、テーブルに対する基本操作のメソッド シグネチャを示します。 署名は、ビューの名前空間と名前のテーブルを置換する点を除いて表示は、同じです。  
  
|演算|メソッド シグネチャ|  
|---------------|----------------------|  
|テーブル値関数の名前|パブリック名前空間 [FUNCTION_NAME] [FUNCTION_NAME] (param1、param2、.\)|  
  
 [NAMESPACE] 名前空間、たとえば、schemas.microsoft.com.Sql._2008._05.Types.TableFunctionReturnTables.dbo.TVF_EMPLOYEE を =  
  
 [FUNCTION_NAME] = テーブル値関数の名前。  
  
 WCF クライアント クラスを生成の例として、次のコードがメソッド シグネチャを示します、 **TVF_EMPLOYEE**をパラメーターとしての従業員の表記を取得し、従業員が返されます、dbo スキーマ内のスカラー関数レコードです。  
  
```  
public partial class TableValuedFunctions_dboClient : System.ServiceModel.ClientBase<TableValuedFunctions_dbo>, TableValuedFunctions_dbo {      
    public schemas.microsoft.com.Sql._2008._05.Types.TableFunctionReturnTables.dbo.TVF_EMPLOYEE[] TVF_EMPLOYEE(string emp_desig);  
}  
```  
  
 このスニペットで**TableValuedFunctions_dboClient**によって生成された SqlAdapterBindingClient.cs で WCF クラスの名前を指定します、[!INCLUDE[addadapterservrefshort](../../includes/addadapterservrefshort-md.md)]します。  
  
### <a name="parameters-for-invoking-table-valued-functions"></a>テーブル値関数の呼び出しのパラメーター  
 によって公開されるメソッドのパラメーター、[!INCLUDE[adaptersqlshort](../../includes/adaptersqlshort-md.md)]を呼び出す、テーブル値関数は、SQL Server で、関数定義で定義されているパラメーターと同じです。 たとえば、TVF_EMPLOYEE テーブル値関数を呼び出すためのパラメーターは emp_desig は、従業員の指定を済みます。  
  
 ここでも、テーブル値関数の戻り値は、SQL Server での関数定義で定義されている戻り値と同じです。 たとえば、TVF_EMPLOYEE 関数の戻り値は type[] schemas.microsoft.com.Sql._2008._05.Types.TableFunctionReturnTables.dbo.TVF_EMPLOYEE のレコードの配列です。  
  
## <a name="creating-a-wcf-client-to-invoke-table-valued-functions"></a>テーブル値関数を呼び出すための WCF クライアントを作成します。  
 WCF クライアントを使用して SQL Server で操作の実行に必要なアクションの汎用的なセットは、一連のタスクで説明されている[SQL アダプターを使用した WCF サービス モデルの概要](overview-of-the-wcf-service-model-with-the-sql-adapter.md)します。 このセクションを呼び出す、WCF クライアントを作成する方法を説明します、 **TVF_EMPLOYEE**テーブル値関数。  
  
 
1. Visual c# プロジェクトを作成[!INCLUDE[btsVStudioNoVersion](../../includes/btsVStudioNoVersion-md.md)]です。 このトピックでは、コンソール アプリケーションを作成します。  
  
2. WCF クライアント クラスを生成、 **TVF_EMPLOYEE**スカラー関数。 WCF クライアント クラスを生成する詳細については、[SQL Server のアイテムの WCF クライアントまたは WCF サービス コントラクトを生成](generate-a-wcf-client-or-wcf-service-contract-for-sql-server-artifacts.md)を参照してください。  
  
3. ソリューション エクスプ ローラーへの参照を追加`Microsoft.Adapters.Sql`と`Microsoft.ServiceModel.Channels`します。  
  
4. Program.cs を開き、次のスニペットの説明に従って、クライアントを作成します。  
  
   ```  
  
             TableValuedFunctions_dboClient client = new TableValuedFunctions_dboClient("SqlAdapterBinding_TableValuedFunctions_dbo");  
   client.ClientCredentials.UserName.UserName = "<Enter user name here>";  
   client.ClientCredentials.UserName.Password = "<Enter password here>";  
   ```  
  
    このスニペットで`TableValuedFunctions_dboClient`SqlAdapterBindingClient.cs で定義されている WCF クライアントです。 このファイルがによって生成された、[!INCLUDE[addadapterservrefshort](../../includes/addadapterservrefshort-md.md)]します。 `SqlAdapterBinding_TableValuedFunctions_dbo` クライアント エンドポイント構成の名前を指定され、app.config で定義されます。このファイルがによって生成されても、[!INCLUDE[addadapterservrefshort](../../includes/addadapterservrefshort-md.md)]バインドのプロパティとその他の構成設定が含まれています。  
  
   > [!NOTE]
   >  このスニペットでは、構成ファイルからバインドおよびエンドポイント アドレスを使用します。 これらの値は、コードで明示的に指定できます。 クライアント バインディングを指定し、さまざまな方法の詳細については、[SQL アダプタのクライアントのバインディングを構成する](configure-a-client-binding-for-the-sql-adapter.md)を参照してください。  
  
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
  
6. 呼び出す、 **TVF_EMPLOYEE** "Manager"の指定を持つすべての従業員レコードを取得します。  
  
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
  
7. 次のスニペットの説明に従って、クライアントを閉じます。  
  
   ```  
   client.Close();  
   Console.WriteLine("Press any key to exit...");  
   Console.ReadLine();  
   ```  
  
8. プロジェクトをビルドし、それを実行します。 アプリケーションでは、従業員 ID、名、および"Manager"指定付きのすべての従業員の給与が表示されます。  
  
## <a name="see-also"></a>参照  
[WCF サービス モデルを使用してアプリケーションを開発する](develop-sql-applications-using-the-wcf-service-model.md)