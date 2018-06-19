---
title: WCF サービス モデルを使用して SQL Server のスカラー関数を呼び出す |Microsoft ドキュメント
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
ms.openlocfilehash: 7a04904f1170644498d49670104a842b4c8f9dd2
ms.sourcegitcommit: 5abd0ed3f9e4858ffaaec5481bfa8878595e95f7
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 11/28/2017
ms.locfileid: "25964248"
---
# <a name="invoke-scalar-functions-in-sql-server-by-using-the-wcf-service-model"></a>WCF サービス モデルを使用して SQL Server のスカラー関数を呼び出す
使用することができます、 [!INCLUDE[adaptersqlshort](../../includes/adaptersqlshort-md.md)] SQL Server のスカラー関数を呼び出す、WCF サービス モデルを使用して .NET アプリケーションでします。 アダプターは、SQL サーバー上で直接呼び出すことのできるメソッドとして、スカラー関数を公開します。 アダプターがスカラー関数をサポートする方法の詳細については、次を参照してください。[実行スカラー関数は、SQL アダプターを使用して SQL Server](../../adapters-and-accelerators/adapter-sql/execute-scalar-functions-in-sql-server-using-the-sql-adapter.md)です。  
  
## <a name="how-this-topic-demonstrates-invoking-scalar-functions-using-the-wcf-service-model"></a>どのように、このトピックでは、WCF サービス モデルを使用してスカラー関数の呼び出しを示しています  
 このトピックでは、SQL Server データベース内で、GET_EMP_ID 関数を呼び出す方法を示します。 GET_EMP_ID 関数が受け取る内の従業員の指定、**従業員**テーブルが表示され、対応する従業員 ID を返します。 GET_EMP_ID 関数および**従業員**サンプルに用意されている SQL スクリプトを実行してテーブルを作成します。 詳細については、次を参照してください。[アダプタ サンプル](../../adapters-and-accelerators/accelerator-rosettanet/adapter-samples.md)です。  
  
## <a name="about-the-examples-used-in-this-topic"></a>このトピックで使用する例について  
 このトピックの例では、Employee テーブルに対して GET_EMP_ID スカラー関数が呼び出されます。 GET_EMP_ID 関数および**従業員**サンプルに用意されている SQL スクリプトを実行してテーブルを作成します。 サンプルは、 **ScalarFunction_ServiceModel**、これは、このトピックの内容に基づいても付属、[!INCLUDE[adaptersqlshort](../../includes/adaptersqlshort-md.md)]サンプルです。 詳細については、次を参照してください。[アダプタ サンプル](../../adapters-and-accelerators/accelerator-rosettanet/adapter-samples.md)です。  
  
## <a name="the-wcf-client-class"></a>WCF クライアント クラス  
 SQL Server を使用してスカラー関数を呼び出すことの生成、WCF クライアントの名前、[!INCLUDE[adaptersqlshort](../../includes/adaptersqlshort-md.md)]次の表に記載されています。  
  
|SQL Server のデータベース成果物|WCF クライアント名|  
|----------------------------------|---------------------|  
|スカラー関数|[スキーマ] ScalarFunctions_ クライアント|  
  
 [スキーマ]; SQL Server のコレクション アイテムを =たとえば、dbo します。  
  
### <a name="method-signature-for-invoking-scalar-functions"></a>スカラー関数の呼び出しのメソッドの署名  
 次の表は、テーブルの基本的な操作について、メソッド シグネチャを示します。 署名は、ビューの名前空間と名前のテーブルを置換する点を除いて、表示は、同じです。  
  
|操作|メソッド シグネチャ|  
|---------------|----------------------|  
|スカラー関数の名前|パブリック *< return_type >**< scalar_function_name >*(param1、param2、...)|  
  
 \<*retrun_type* \>関数定義で定義されている戻り値の型を =  
  
 \<*scalar_function_name* \> = スカラー関数の名前。  
  
 たとえば、次のコードにはメソッド シグネチャに関するの WCF クライアント クラスを生成、 **GET_EMP_ID**をパラメーターとしての従業員の表記を取得し、ID (従業員を返します、dbo スキーマ内のスカラー関数整数)。  
  
```  
public partial class ScalarFunctions_dboClient : System.ServiceModel.ClientBase<ScalarFunctions_dbo>, ScalarFunctions_dbo {      
    public System.Nullable<int> GET_EMP_ID(string emp_desig);  
}  
```  
  
 このスニペットで**ScalarFunctions_dboClient**によって生成された SqlAdapterBindingClient.cs で WCF クラスの名前を指定します、[!INCLUDE[addadapterservrefshort](../../includes/addadapterservrefshort-md.md)]です。  
  
### <a name="parameters-for-invoking-scalar-functions"></a>スカラー関数の呼び出しのパラメーター  
 によって公開されるメソッドのパラメーター、[!INCLUDE[adaptersqlshort](../../includes/adaptersqlshort-md.md)]を呼び出すのスカラー関数は、SQL Server のスカラー関数の定義で定義されたパラメーターと同じです。 たとえば、パラメーター GET_EMP_ID スカラー関数を呼び出す emp_desig は、従業員の表記を取得します。  
  
 もう一度、スカラー関数の戻り値は、SQL Server のスカラー関数の定義で定義されている戻り値と同じです。 たとえば、GET_EMP_ID 関数の戻り値は、整数型の従業員の ID です。  
  
## <a name="creating-a-wcf-client-to-invoke-scalar-functions"></a>スカラー関数を呼び出す、WCF クライアントを作成します。  
 WCF クライアントを使用して SQL Server で操作の実行に必要なアクションの汎用的なセットは、一連のタスクで説明されている[SQL アダプターで WCF サービス モデルの概要](../../adapters-and-accelerators/adapter-sql/overview-of-the-wcf-service-model-with-the-sql-adapter.md)です。 このセクションを呼び出すための WCF クライアントを作成する方法について説明、 **GET_EMP_ID**スカラー関数です。  
  
#### <a name="to-create-a-wcf-client"></a>WCF クライアントを作成するには  
  
1.  Visual c# プロジェクトを作成[!INCLUDE[btsVStudioNoVersion](../../includes/btsvstudionoversion-md.md)]です。 このトピックでは、コンソール アプリケーションを作成します。  
  
2.  WCF クライアント クラスを生成、 **GET_EMP_ID**スカラー関数です。 詳細については、WCF クライアント クラスを生成する、次を参照してください。 [SQL Server の成果物のために、WCF クライアントまたは WCF サービス コントラクトを生成](../../adapters-and-accelerators/adapter-sql/generate-a-wcf-client-or-wcf-service-contract-for-sql-server-artifacts.md)です。  
  
3.  ソリューション エクスプ ローラーへの参照を追加`Microsoft.Adapters.Sql`と`Microsoft.ServiceModel.Channels`です。  
  
4.  Program.cs を開き、次のスニペットの説明に従って、クライアントを作成します。  
  
    ```  
  
              ScalarFunctions_dboClient client = new ScalarFunctions_dboClient("SqlAdapterBinding_ScalarFunctions_dbo");  
    client.ClientCredentials.UserName.UserName = "<Enter user name here>";  
    client.ClientCredentials.UserName.Password = "<Enter password here>";  
    ```  
  
     このスニペットで`ScalarFunctions_dboClient`SqlAdapterBindingClient.cs で定義された WCF クライアントです。 このファイルにより生成されて、[!INCLUDE[addadapterservrefshort](../../includes/addadapterservrefshort-md.md)]です。 `SqlAdapterBinding_ScalarFunctions_dbo`クライアント エンドポイント構成の名前を指定、app.config で定義されます。このファイルがによって生成されても、[!INCLUDE[addadapterservrefshort](../../includes/addadapterservrefshort-md.md)]バインドのプロパティおよびその他の構成設定が含まれています。  
  
    > [!NOTE]
    >  このスニペットでは、構成ファイルからバインディングとエンドポイント アドレスを使用します。 これらの値は、コードで明示的に指定できます。 クライアント バインディングを指定し、さまざまな方法の詳細については、次を参照してください。 [SQL アダプタのクライアントのバインディングを構成する](../../adapters-and-accelerators/adapter-sql/configure-a-client-binding-for-the-sql-adapter.md)です。  
  
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
  
6.  呼び出す、 **GET_EMP_ID** "Manager"としての表記である従業員の ID を取得する関数。  
  
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
    >  わかりやすくするため、**従業員**テーブルが"Manager"表記で従業員が 1 つだけです。 対象のテーブルに同じ指定を持つ複数の従業員がある場合は、それに従って関数を定義する必要があります。  
  
7.  次のスニペット」の説明に従って、クライアントを閉じます。  
  
    ```  
    client.Close();  
    Console.WriteLine("Press any key to exit...");  
    Console.ReadLine();  
    ```  
  
8.  プロジェクトをビルドし、それを実行します。 アプリケーションには、"Manager"グループの指定には、従業員の従業員 ID が表示されます。  
  
## <a name="see-also"></a>参照  
[WCF サービス モデルを使用してアプリケーションを開発する](../../adapters-and-accelerators/adapter-sql/develop-sql-applications-using-the-wcf-service-model.md)