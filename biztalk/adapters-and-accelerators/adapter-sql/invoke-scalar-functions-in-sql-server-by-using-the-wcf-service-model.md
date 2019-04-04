---
title: WCF サービス モデルを使用して SQL Server のスカラー関数を呼び出す |Microsoft Docs
ms.custom: ''
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: ''
ms.suite: ''
ms.tgt_pltfrm: ''
ms.topic: article
ms.assetid: a331e275-3c81-41a8-9ba1-3a801ebc259a
caps.latest.revision: 7
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: d26d2a7b13804f621b04484f2466af727b8fbf26
ms.sourcegitcommit: 266308ec5c6a9d8d80ff298ee6051b4843c5d626
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 06/27/2018
ms.locfileid: "36998595"
---
# <a name="invoke-scalar-functions-in-sql-server-by-using-the-wcf-service-model"></a>WCF サービス モデルを使用して SQL Server のスカラー関数を呼び出す
使用することができます、[!INCLUDE[adaptersqlshort](../../includes/adaptersqlshort-md.md)]で SQL Server のスカラー関数を呼び出す、WCF サービス モデルを使用して .NET アプリケーション。 アダプターは、SQL サーバー上で直接呼び出すことができるメソッドとしてスカラー関数を公開します。 アダプターがスカラー関数をサポートする方法の詳細については、[SQL アダプターを使用して SQL server のスカラー関数の実行](../../adapters-and-accelerators/adapter-sql/execute-scalar-functions-in-sql-server-using-the-sql-adapter.md)を参照してください。  

## <a name="how-this-topic-demonstrates-invoking-scalar-functions-using-the-wcf-service-model"></a>このトピックの WCF サービス モデルを使用してスカラー関数の呼び出しがについて説明する方法  
 このトピックでは、SQL Server データベースで GET_EMP_ID 関数を呼び出す方法を示します。 GET_EMP_ID 関数は、従業員の指定、**従業員**テーブルし、対応する従業員 ID を返します。 GET_EMP_ID 関数と**従業員**サンプルで提供される SQL スクリプトを実行してテーブルが作成されます。 詳細については、[アダプタ サンプル](../../adapters-and-accelerators/accelerator-rosettanet/adapter-samples.md)を参照してください。  

## <a name="about-the-examples-used-in-this-topic"></a>このトピックで使用する例について  
 このトピックの例では、Employee テーブルに対して GET_EMP_ID スカラー関数が呼び出されます。 GET_EMP_ID 関数と**従業員**サンプルで提供される SQL スクリプトを実行してテーブルが作成されます。 サンプルについては、 **ScalarFunction_ServiceModel**、これは、このトピックに基づいてがで提供されていることも、[!INCLUDE[adaptersqlshort](../../includes/adaptersqlshort-md.md)]サンプル。 詳細については、[アダプタ サンプル](../../adapters-and-accelerators/accelerator-rosettanet/adapter-samples.md)を参照してください。  

## <a name="the-wcf-client-class"></a>WCF クライアント クラス  
 SQL Server を使用してスカラー関数を呼び出すために生成された WCF クライアントの名前、[!INCLUDE[adaptersqlshort](../../includes/adaptersqlshort-md.md)]次の表に記載されています。  

|SQL Server データベースの成果物|WCF クライアント名|  
|----------------------------------|---------------------|  
|スカラー関数|[スキーマ] ScalarFunctions_ クライアント|  

 [スキーマ] コレクションの SQL Server のアイテム、=たとえば、dbo です。  

### <a name="method-signature-for-invoking-scalar-functions"></a>スカラー関数を呼び出すためのメソッド シグネチャ  
 次の表では、テーブルに対する基本操作のメソッド シグネチャを示します。 署名は、ビューの名前空間と名前のテーブルを置換する点を除いて表示は、同じです。  


|      演算       |                             メソッド シグネチャ                             |
|----------------------|--------------------------------------------------------------------------|
| スカラー関数の名前 | パブリック *< return_type >*<em>< scalar_function_name ></em>(param1、param2、...) |

 \<*retrun_type* \>関数定義で定義されている戻り値の型を =  

 \<*scalar_function_name* \> = スカラー関数の名前。  

 WCF クライアント クラスを生成の例として、次のコードがメソッド シグネチャを示します、 **GET_EMP_ID**をパラメーターとしての従業員の表記を取得し、ID (従業員を返します、dbo スキーマ内のスカラー関数整数)。  

```  
public partial class ScalarFunctions_dboClient : System.ServiceModel.ClientBase<ScalarFunctions_dbo>, ScalarFunctions_dbo {      
    public System.Nullable<int> GET_EMP_ID(string emp_desig);  
}  
```  

 このスニペットで**ScalarFunctions_dboClient**によって生成された SqlAdapterBindingClient.cs で WCF クラスの名前を指定します、[!INCLUDE[addadapterservrefshort](../../includes/addadapterservrefshort-md.md)]します。  

### <a name="parameters-for-invoking-scalar-functions"></a>スカラー関数の呼び出しのパラメーター  
 によって公開されるメソッドのパラメーター、[!INCLUDE[adaptersqlshort](../../includes/adaptersqlshort-md.md)]関数ではスカラーを呼び出すには、SQL Server のスカラー関数の定義で定義されているパラメーターと同じです。 たとえば、GET_EMP_ID スカラー関数を呼び出すためのパラメーターは emp_desig は、従業員の指定を済みます。  

 ここでも、スカラー関数の戻り値は、SQL Server のスカラー関数の定義で定義されている戻り値と同じです。 たとえば、GET_EMP_ID 関数の戻り値は、整数型の従業員の ID。  

## <a name="creating-a-wcf-client-to-invoke-scalar-functions"></a>スカラー関数を呼び出すための WCF クライアントを作成します。  
 WCF クライアントを使用して SQL Server で操作の実行に必要なアクションの汎用的なセットは、一連のタスクで説明されている[SQL アダプターを使用した WCF サービス モデルの概要](../../adapters-and-accelerators/adapter-sql/overview-of-the-wcf-service-model-with-the-sql-adapter.md)します。 このセクションを呼び出す、WCF クライアントを作成する方法を説明します、 **GET_EMP_ID**スカラー関数。  

#### <a name="to-create-a-wcf-client"></a>WCF クライアントを作成するには  

1. Visual c# プロジェクトを作成[!INCLUDE[btsVStudioNoVersion](../../includes/btsvstudionoversion-md.md)]です。 このトピックでは、コンソール アプリケーションを作成します。  

2. WCF クライアント クラスを生成、 **GET_EMP_ID**スカラー関数。 WCF クライアント クラスを生成する詳細については、[SQL Server のアイテムの WCF クライアントまたは WCF サービス コントラクトを生成](../../adapters-and-accelerators/adapter-sql/generate-a-wcf-client-or-wcf-service-contract-for-sql-server-artifacts.md)を参照してください。  

3. ソリューション エクスプ ローラーへの参照を追加`Microsoft.Adapters.Sql`と`Microsoft.ServiceModel.Channels`します。  

4. Program.cs を開き、次のスニペットの説明に従って、クライアントを作成します。  

   ```  

             ScalarFunctions_dboClient client = new ScalarFunctions_dboClient("SqlAdapterBinding_ScalarFunctions_dbo");  
   client.ClientCredentials.UserName.UserName = "<Enter user name here>";  
   client.ClientCredentials.UserName.Password = "<Enter password here>";  
   ```  

    このスニペットで`ScalarFunctions_dboClient`SqlAdapterBindingClient.cs で定義されている WCF クライアントです。 このファイルがによって生成された、[!INCLUDE[addadapterservrefshort](../../includes/addadapterservrefshort-md.md)]します。 `SqlAdapterBinding_ScalarFunctions_dbo` クライアント エンドポイント構成の名前を指定され、app.config で定義されます。このファイルがによって生成されても、[!INCLUDE[addadapterservrefshort](../../includes/addadapterservrefshort-md.md)]バインドのプロパティとその他の構成設定が含まれています。  

   > [!NOTE]
   >  このスニペットでは、構成ファイルからバインドおよびエンドポイント アドレスを使用します。 これらの値は、コードで明示的に指定できます。 クライアント バインディングを指定し、さまざまな方法の詳細については、[SQL アダプタのクライアントのバインディングを構成する](../../adapters-and-accelerators/adapter-sql/configure-a-client-binding-for-the-sql-adapter.md)を参照してください。  

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

6. 呼び出す、 **GET_EMP_ID** "Manager"として指定である従業員の ID を取得する関数。  

   ```  
   Console.WriteLine("Invoking the GET_EMP_ID function");  
   string emp_designation = "Manager";  
   try  
   {  
         System.Nullable<int> emp_id = client.GET_EMP_ID(emp_designation);  
         Console.WriteLine("The Employee ID for the employee with 'Manager' designation is:" + emp_id);  
   }  
   catch (Exception e)  
   {  
         Console.WriteLine("Exception: " + e.Message);  
         throw;  
   }  
   ```  

   > [!NOTE]
   >  わかりやすく、**従業員**テーブルが 1 つだけの従業員に"Manager"の形式。 先のテーブルに同じ指定以上の従業員がある場合は、それに応じて関数を定義する必要があります。  

7. 次のスニペットの説明に従って、クライアントを閉じます。  

   ```  
   client.Close();  
   Console.WriteLine("Press any key to exit...");  
   Console.ReadLine();  
   ```  

8. プロジェクトをビルドし、それを実行します。 アプリケーションでは、"Manager"の指定では、従業員の従業員 ID が表示されます。  

## <a name="see-also"></a>参照  
[WCF サービス モデルを使用してアプリケーションを開発する](../../adapters-and-accelerators/adapter-sql/develop-sql-applications-using-the-wcf-service-model.md)