---
title: WCF サービス モデルを使用して sql ExecuteReader、executescalar、ExecuteNonQuery 操作 |Microsoft Docs
ms.custom: ''
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: ''
ms.suite: ''
ms.tgt_pltfrm: ''
ms.topic: article
ms.assetid: 62f166af-b657-491b-b20d-1ae7886f27ce
caps.latest.revision: 4
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: d9dd50b3353aac683548f9220c441bef21776a37
ms.sourcegitcommit: 266308ec5c6a9d8d80ff298ee6051b4843c5d626
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 06/27/2018
ms.locfileid: "36968835"
---
# <a name="executereader-executescalar-or-executenonquery-operations-in-sql-using-wcf-service-model"></a>WCF サービス モデルを使用して sql ExecuteReader、executescalar、ExecuteNonQuery 操作
[!INCLUDE[adaptersqlshort](../../includes/adaptersqlshort-md.md)]など SQL Server の一般的な操作を公開する**ExecuteNonQuery**、 **ExecuteReader**、および**ExecuteScalar**します。 これらの操作を使用して、SQL Server データベースで任意の SQL ステートメントを実行することができます。 これらの操作は、応答するための SQL ステートメントの種類によって異なります。 アダプターがこれらの操作をサポートする方法の詳細については、[ExecuteNonQuery、ExecuteReader、ExecuteScalar 操作のサポート](../../adapters-and-accelerators/adapter-oracle-ebs/support-for-executenonquery-executereader-and-executescalar-operations.md)を参照してください。  

 このトピックでは、実行する方法を示します、 **ExecuteReader**操作を使用して、 [!INCLUDE[adaptersqlshort](../../includes/adaptersqlshort-md.md)] WCF サービス モデルを使用します。 実行するには、このトピックで説明する手順の同じセットを利用できる**ExecuteNonQuery**と**ExecuteScalar**操作。  

## <a name="about-the-examples-used-in-this-topic"></a>このトピックで使用する例について  
 このトピックの例では、 **ExecuteReader**操作、ADD_EMP_DETAILS を実行するストアド プロシージャ。 このストアド プロシージャでは、Employee テーブルにレコードを追加し、レコードの従業員 ID を返します。 ADD_EMP_DETAILS ストアド プロシージャは、サンプルで提供される SQL スクリプトを実行して作成されます。 サンプルの詳細については、[アダプタ サンプル](../../adapters-and-accelerators/accelerator-rosettanet/adapter-samples.md)を参照してください。 サンプルについては、 **Execute_Reader**、これは、このトピックに基づいてがで提供されていることも、[!INCLUDE[adaptersqlshort](../../includes/adaptersqlshort-md.md)]サンプル。  

## <a name="the-wcf-client-class"></a>WCF クライアント クラス  
 一般的な操作 (ExecuteNonQuery、ExecuteReader、ExecuteScalar のいずれか) を使用してを呼び出すために生成された WCF クライアントの名前、[!INCLUDE[adaptersqlshort](../../includes/adaptersqlshort-md.md)]次の表に記載されています。  

|操作|WCF クライアント名|  
|----------------|---------------------|  
|ExecuteNonQuery、ExecuteReader、ExecuteScalar|GenericTableOpClient|  

### <a name="method-signature-for-invoking-generic-operations"></a>一般的な操作を呼び出すためのメソッド シグネチャ  
 次の表では、汎用的な操作の呼び出しに公開されるメソッドのシグネチャを示します。  

|演算|メソッド シグネチャ|  
|---------------|----------------------|  
|ExecuteNonQuery|int ExecuteNonQuery (クエリ文字列)|  
|ExecuteReader|System.Data.DataSet:operator[] ExecuteReader (クエリ文字列)|  
|ExecuteScalar|文字列 ExecuteScalar(string Query)|  

 例として、汎用の操作メソッドのシグネチャを次のコード スニペットに示します。  

```  
public partial class GenericTableOpClient : System.ServiceModel.ClientBase<GenericTableOp>, GenericTableOp {  
  public int ExecuteNonQuery(string Query);  
  public System.Data.DataSet[] ExecuteReader(string Query);  
  public string ExecuteScalar(string Query);  
}  
```  

 このスニペットで  

-   `GenericTableOpClient` クラスの名前です。 この例では、このクラスを使用する、ExecuteReader、汎用的な操作を呼び出すクライアントを作成します。  

-   `public System.Data.DataSet[] ExecuteReader(string Query)` ストアド プロシージャを ADD_EMP_DETAILS を起動するには、この例では起動されるメソッドです。  

## <a name="creating-a-wcf-client-to-invoke-an-executereader-operation"></a>ExecuteReader 操作を呼び出す、WCF クライアントを作成します。  
 WCF クライアントを使用して SQL Server で操作の実行に必要なアクションの汎用的なセットは、一連のタスクで説明されている[SQL アダプターを使用した WCF チャネル モデルの概要](../../adapters-and-accelerators/adapter-sql/overview-of-the-wcf-channel-model-with-the-sql-adapter.md)します。 このセクションを起動する WCF クライアントを作成する方法を具体的に説明します、 **ExecuteReader**操作、ADD_EMP_DETAILS を実行するストアド プロシージャ。 このストアド プロシージャは、各サンプルに用意されている SQL スクリプトを実行して作成されます。  

#### <a name="to-create-a-wcf-client-to-invoke-executereader-operation"></a>ExecuteReader 操作を呼び出す、WCF クライアントを作成するには  

1. Visual Studio で Visual c# プロジェクトを作成します。 このトピックでは、コンソール アプリケーションを作成します。  

2. WCF クライアント クラスを生成、 **ExecuteReader**ジェネリック操作。 使用して、SQL Server データベースに接続するときに、この操作は、ルート ノードで使用可能な[!INCLUDE[addadapterservrefshort](../../includes/addadapterservrefshort-md.md)]します。 WCF クライアント クラスを生成する詳細については、[SQL Server のアイテムの WCF クライアントまたは WCF サービス コントラクトを生成](../../adapters-and-accelerators/adapter-sql/generate-a-wcf-client-or-wcf-service-contract-for-sql-server-artifacts.md)を参照してください。  

   > [!IMPORTANT]
   >  WCF クライアント クラスを生成する前に必ず設定して、 **EnableBizTalkCompatibilityMode**プロパティを false にバインドします。  

3. ソリューション エクスプ ローラーへの参照を追加`Microsoft.Adapters.Sql`と`Microsoft.ServiceModel.Channels`します。  

4. Program.cs ファイルを開き、次のスニペットの説明に従って、クライアントを作成します。  

   ```  

           GenericTableOpClient client = new GenericTableOpClient("SqlAdapterBinding_GenericTableOp");  
   client.ClientCredentials.UserName.UserName = "<Enter username here>";  
   client.ClientCredentials.UserName.Password = "<Enter password here>";  
   ```  

    このスニペットで`GenericTableOpClient`SqlAdapterBindingClient.cs で定義されている WCF クライアントです。 このファイルがによって生成された、[!INCLUDE[addadapterservrefshort](../../includes/addadapterservrefshort-md.md)]します。 `SqlAdapterBinding_GenericTableOp` クライアント エンドポイント構成の名前を指定され、app.config で定義されます。このファイルがによって生成されても、[!INCLUDE[addadapterservrefshort](../../includes/addadapterservrefshort-md.md)]バインドのプロパティとその他の構成設定が含まれています。  

   > [!NOTE]
   >  このスニペットでは、構成ファイルからバインドおよびエンドポイント アドレスを使用します。 これらの値は、コードで明示的に指定できます。 クライアント バインディングを指定する、さまざまな方法の詳細については、[SQL アダプタのクライアントのバインディングを構成する](../../adapters-and-accelerators/adapter-sql/configure-a-client-binding-for-the-sql-adapter.md)を参照してください。  

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

6. 呼び出す、 **ExecuteReader** ADD_EMP_DETAILS の操作のストアド プロシージャ。 追加する必要があります ExecuteReader 操作を呼び出す前に、`System.Data`をコードに名前空間。  

   ```  
   string query = "EXEC ADD_EMP_DETAILS 'Tom Smith', 'Manager', 500000";  
   DataSet[] dsArray = client.ExecuteReader(query);  

   Console.WriteLine("Invoking the ADD_EMP_DETAILS stored procedure using ExecuteReader");  
   Console.WriteLine("*****************************************************");  
   foreach (DataSet dataSet in dsArray)  
   {  
      foreach (DataTable tab in dsArray[0].Tables)  
      {  
          foreach (DataRow row in tab.Rows)  
          {  
             for (int i = 0; i < tab.Columns.Count; i++)  
             {  
                Console.WriteLine("The ID for the newly added employee is : " + row[i]);  
             }  
          }  
       }  
   }  
   Console.WriteLine("*****************************************************");  

   ```  

7. 次のスニペットの説明に従って、クライアントを閉じます。  

   ```  
   client.Close();  
   Console.WriteLine("Press any key to exit...");  
   Console.ReadLine();  
   ```  

8. プロジェクトをビルドし、それを実行します。 新しく挿入された従業員の従業員 ID は、コンソールに表示されます。
