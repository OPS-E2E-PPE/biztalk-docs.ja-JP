---
title: WCF サービス モデルを使用して Oracle E-business Suite で ExecuteReader、executescalar、ExecuteNonQuery 操作 |Microsoft Docs
ms.custom: ''
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: ''
ms.suite: ''
ms.tgt_pltfrm: ''
ms.topic: article
ms.assetid: 54c42db1-9a4d-4003-af69-f75ff48b575a
caps.latest.revision: 7
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: 0286de636c2ad9fb50fabafe73b5257d18cf70b2
ms.sourcegitcommit: 266308ec5c6a9d8d80ff298ee6051b4843c5d626
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 06/27/2018
ms.locfileid: "36993179"
---
# <a name="executereader-executescalar-or-executenonquery-operations-in-oracle-e-business-suite-using-the-wcf-service-model"></a>WCF サービス モデルを使用して Oracle E-business Suite で ExecuteReader、executescalar、ExecuteNonQuery 操作
[!INCLUDE[adapteroraclebusinessshort](../../includes/adapteroraclebusinessshort-md.md)]などの一般的な操作を公開する**ExecuteNonQuery**、 **ExecuteReader**、および**ExecuteScalar**します。 これらの操作を使用して、Oracle E-business Suite で任意のステートメントを実行することができます。 これらの操作は、応答するためのステートメントの種類によって異なります。 アダプターがこれらの操作をサポートする方法の詳細については、[ExecuteNonQuery、ExecuteReader、ExecuteScalar 操作のサポート](../../adapters-and-accelerators/adapter-oracle-ebs/support-for-executenonquery-executereader-and-executescalar-operations.md)を参照してください。  
  
 このトピックでは、実行する方法を示します、 **ExecuteReader**操作を使用して、 [!INCLUDE[adapteroraclebusinessshort](../../includes/adapteroraclebusinessshort-md.md)] WCF サービス モデルを使用します。 実行するには、このトピックで説明する手順の同じセットを利用できる**ExecuteNonQuery**と**ExecuteScalar**操作。  
  
## <a name="about-the-examples-used-in-this-topic"></a>このトピックで使用する例について  
 このトピックの例では、 **ExecuteReader** MS_SAMPLE_EMPLOYEE インターフェイス テーブルでの選択操作を実行する操作。 サンプルに付属のスクリプトを実行して、テーブルが作成されます。 サンプルの詳細については、[Oracle EBS アダプター用のサンプル](../../adapters-and-accelerators/adapter-oracle-ebs/samples-for-the-oracle-ebs-adapter.md)を参照してください。 サンプルについては、 **ExecuteReader**、これは、このトピックに基づいてがで提供されていることも、[!INCLUDE[adapteroraclebusinessshort](../../includes/adapteroraclebusinessshort-md.md)]サンプル。  
  
## <a name="the-wcf-client-class"></a>WCF クライアント クラス  
 一般的な操作 (ExecuteNonQuery、ExecuteReader、ExecuteScalar のいずれか) を使用してを呼び出すために生成された WCF クライアントの名前、[!INCLUDE[adapteroraclebusinessshort](../../includes/adapteroraclebusinessshort-md.md)]次の表に記載されています。  
  
|操作|WCF クライアント名|  
|----------------|---------------------|  
|ExecuteNonQuery、ExecuteReader、ExecuteScalar|GenericOperation_Client|  
  
### <a name="method-signature-for-invoking-generic-operations"></a>一般的な操作を呼び出すためのメソッド シグネチャ  
 次の表では、汎用的な操作の呼び出しに公開されるメソッドのシグネチャを示します。  
  
|演算|メソッド シグネチャ|  
|---------------|----------------------|  
|ExecuteNonQuery|int ExecuteNonQuery (string、string[] OutputRefCursorNames、System.Data.DataSet:operator[] OutputRefCursors アウト クエリ)|  
|ExecuteReader|System.Data.DataSet ExecuteReader(string Query)|  
|ExecuteScalar|文字列 ExecuteScalar(string Query)|  
  
 例として、汎用の操作メソッドのシグネチャを次のコード スニペットに示します。  
  
```  
public partial class GenericOperation_Client : System.ServiceModel.ClientBase<GenericOperation_>, GenericOperation_ {  
  public int ExecuteNonQuery(string Query, string[] OutputRefCursorNames, out System.Data.DataSet[] OutputRefCursors);  
  public System.Data.DataSet ExecuteReader(string Query);  
  public string ExecuteScalar(string Query);  
}  
```  
  
 このスニペットで  
  
-   `GenericOperation_Client` クラスの名前です。 このクラスは、汎用の操作では、ExecuteReader を呼び出すクライアントを作成するに使用されます。  
  
-   `public System.Data.DataSet ExecuteReader(string Query)` 呼び出す MS_SAMPLE_EMPLOYEE インターフェイス テーブルに対して SELECT ステートメントを実行する方法です。  
  
## <a name="creating-a-wcf-client-to-invoke-an-executereader-operation"></a>ExecuteReader 操作を呼び出す、WCF クライアントを作成します。  
 汎用的な一連の WCF クライアントを使用して Oracle E-business Suite での操作を実行するために必要なアクションは、一連のタスクで説明されている[Oracle E-business Suite アダプターで WCF サービス モデルの概要](../../adapters-and-accelerators/adapter-oracle-ebs/overview-of-the-wcf-service-model-with-the-oracle-e-business-suite-adapter.md)します。 このセクションを呼び出す、WCF クライアントを作成する方法を説明します、 **ExecuteReader**操作。  
  
#### <a name="to-create-a-wcf-client-to-invoke-executereader-operation"></a>ExecuteReader 操作を呼び出す、WCF クライアントを作成するには  
  
1. Visual Studio で Visual c# プロジェクトを作成します。 このトピックでは、コンソール アプリケーションを作成します。  
  
2. WCF クライアント クラスを生成、 **ExecuteReader**ジェネリック操作。 使用して、Oracle E-business Suite に接続するときは、この操作は、ルート ノードで使用可能な[!INCLUDE[addadapterservrefshort](../../includes/addadapterservrefshort-md.md)]します。 WCF クライアント クラスを生成する詳細については、[WCF クライアントまたは Oracle E-business Suite ソリューションの成果物の WCF サービス コントラクトを生成](../../adapters-and-accelerators/adapter-oracle-ebs/create-a-wcf-client-or-wcf-service-contract-for-oracle-ebs-solution-artifacts.md)を参照してください。  
  
   > [!IMPORTANT]
   >  WCF クライアント クラスを生成する前に必ず設定して、 **EnableBizTalkCompatibilityMode**プロパティを false にバインドします。  
  
3. ソリューション エクスプ ローラーへの参照を追加`Microsoft.Adapters.OracleEBS`と`Microsoft.ServiceModel.Channels`します。  
  
4. Program.cs ファイルを開き、次の名前空間を追加します。  
  
   -   `Microsoft.Adapters.OracleEBS`  
  
   -   `System.ServiceModel`  
  
5. Program.cs ファイルでは、以下のスニペットの説明に従って、クライアントを作成します。  
  
   ```  
   OracleEBSBinding binding = new OracleEBSBinding();  
   EndpointAddress address = new EndpointAddress("oracleebs://ebs-72-11");  
   GenericOperation_Client client = new GenericOperation_Client(binding, address);  
   ```  
  
    このスニペットで`GenericOperation_Client`OracleEBSBindingClient.cs で定義されている WCF クライアントです。 このファイルがによって生成された、[!INCLUDE[addadapterservrefshort](../../includes/addadapterservrefshort-md.md)]します。  
  
   > [!NOTE]
   >  このスニペットでは、アプリケーション コードで明示的にバインディングとエンドポイント アドレスを指定するだけ。 これらの値を使用するには、アプリケーション構成ファイルから app.config、によって生成されることも、[!INCLUDE[addadapterservrefshort](../../includes/addadapterservrefshort-md.md)]します。 クライアント バインディングを指定する、さまざまな方法の詳細については、[Oracle E-business suite バインド クライアントを構成する](../../adapters-and-accelerators/adapter-oracle-ebs/configure-a-client-binding-for-the-oracle-e-business-suite.md)を参照してください。  
  
6. クライアントの資格情報を設定します。  
  
   ```  
   client.ClientCredentials.UserName.UserName = "myuser";  
   client.ClientCredentials.UserName.Password = "mypassword";  
   ```  
  
7. インターフェイス テーブルで操作を実行しているため、アプリケーションのコンテキストを設定する必要があります。 この例で、アプリケーションのコンテキストの設定を指定する、 **OracleUserName**、 **OraclePassword**、および**OracleEBSResponsibilityName**プロパティをバインドします。 アプリケーションのコンテキストの詳細については、[アプリケーション コンテキストの設定](../../adapters-and-accelerators/adapter-oracle-ebs/set-application-context.md)を参照してください。  
  
   ```  
   binding.OracleUserName = "myOracleEBSUserName";  
   binding.OraclePassword = "myOracleEBSPassword";  
   binding.OracleEBSResponsibilityName = "myOracleEBSResponsibility";  
   ```  
  
8. 次のスニペットで説明されているように、クライアントを開きます。  
  
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
  
9. 呼び出す、 **ExecuteReader** MS_SAMPLE_EMPLOYEE テーブルに対する SELECT 操作を実行するための操作。 追加する必要があります ExecuteReader 操作を呼び出す前に、`System.Data`をコードに名前空間。  
  
    ```  
    string query = "SELECT * FROM MS_SAMPLE_EMPLOYEE";  
    DataSet ds = client.ExecuteReader(query);  
  
    Console.WriteLine("Invoking the SELECT statement using ExecuteReader");  
    Console.WriteLine("*****************************************************");  
    foreach (DataTable tab in ds.Tables)  
    {  
       foreach (DataRow row in tab.Rows)  
       {  
          Console.WriteLine("The details of the employee are: ");  
          for (int i = 0; i < tab.Columns.Count; i++)  
          {  
             Console.WriteLine(row[i]);  
          }  
          Console.WriteLine();  
       }  
    }  
    Console.WriteLine("*****************************************************");  
    Console.ReadLine();  
  
    ```  
  
10. 次のスニペットの説明に従って、クライアントを閉じます。  
  
    ```  
    client.Close();  
    Console.WriteLine("Press any key to exit...");  
    Console.ReadLine();  
    ```  
  
11. プロジェクトをビルドし、それを実行します。 MS_SAMPLE_EMPLOYEE テーブル内のすべてのレコードは、コンソールに表示されます。  
  
## <a name="see-also"></a>参照  
 [WCF サービス モデルを使用して Oracle E-business Suite のアプリケーションを開発します。](../../adapters-and-accelerators/adapter-oracle-ebs/develop-oracle-e-business-suite-applications-using-the-wcf-service-model.md)