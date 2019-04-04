---
title: WCF サービス モデルを使用して sql ストアド プロシージャを厳密に型指定されたを呼び出す |Microsoft Docs
ms.custom: ''
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: ''
ms.suite: ''
ms.tgt_pltfrm: ''
ms.topic: article
ms.assetid: d56df5f6-b046-4fe4-a5b4-b29906093beb
caps.latest.revision: 6
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: b88cae88a01ea3f04da3b3672153da7d00ea7633
ms.sourcegitcommit: 266308ec5c6a9d8d80ff298ee6051b4843c5d626
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 06/27/2018
ms.locfileid: "36966819"
---
# <a name="invoke-strongly-typed-stored-procedures-in-sql-using-wcf-service-model"></a>WCF サービス モデルを使用して sql ストアド プロシージャを厳密に型指定されたを呼び出す
下に一覧表示、プロシージャを呼び出すと、 **Strongly-Typed プロシージャ**内のノード、[!INCLUDE[addadapterservrefshort](../../includes/addadapterservrefshort-md.md)]出力は、厳密に型指定された結果セットの形式。 このトピックでは、厳密に型指定された結果セットを返す SQL Server でのストアド プロシージャを呼び出す、WCF クライアントを作成する方法について説明します。  
  
> [!NOTE]
>  ユーザー定義型の列を含むテーブルに対して操作を実行している場合ことを確認するを参照してください[テーブルとユーザー定義型を持つビューで操作](../../adapters-and-accelerators/adapter-sql/operations-on-tables-and-views-with-user-defined-types-using-the-sql-adapter.md)アプリケーションの開発を開始する前にします。  
  
## <a name="about-the-examples-used-in-this-topic"></a>このトピックで使用する例について  
 このトピックの例では、GET_EMP_DETAILS ストアド プロシージャを使用します。 このストアド プロシージャは、入力パラメーターとして従業員 ID を受け取りし、その ID を持つ従業員のすべての対応する列を返します GET_EMP_DETAILS ストアド プロシージャは、サンプルで提供される SQL スクリプトを実行して作成されます。 サンプルの詳細については、[アダプタ サンプル](../../adapters-and-accelerators/accelerator-rosettanet/adapter-samples.md)を参照してください。 サンプルについては、 **Execute_TypedStoredProcedure**、これは、このトピックに基づいてがで提供されていることも、[!INCLUDE[adaptersqlshort](../../includes/adaptersqlshort-md.md)]サンプル。  
  
## <a name="the-wcf-client-class"></a>WCF クライアント クラス  
 ストアド プロシージャを呼び出すために生成された WCF クライアントの名前、 **Strongly-Typed プロシージャ**ノードを使用して、[!INCLUDE[adaptersqlshort](../../includes/adaptersqlshort-md.md)]次の表に記載されています。  
  
|SQL Server データベースの成果物|WCF クライアント名|  
|----------------------------------|---------------------|  
|プロシージャ (下、 **Strongly-Typed プロシージャ**ノード)|TypedProcedures_ クライアントの [スキーマ]|  
  
 [スキーマ]; プロシージャが所属するスキーマとはたとえば"dbo"とします。  
  
### <a name="method-signature-for-invoking-stored-procedures"></a>ストアド プロシージャを呼び出すためのメソッド シグネチャ  
 次の表では、ストアド プロシージャを呼び出すに公開されるメソッドのシグネチャを示します。  
  
|演算|メソッド シグネチャ|  
|---------------|----------------------|  
|プロシージャ名|[PROC_NS][プロシージャ名](param1、param2、.\)|  
  
 [PROC_NS] は、プロシージャの名前空間です。たとえば schemas.microsoft.com.Sql._2008._05.ProceduresResultSets.dbo.GET_EMP_DETAILS.StoredProcedureResultSet0  
  
 [procedure_name] は、プロシージャの名前たとえば GET_EMP_DETAILS  
  
 たとえば、GET_EMP_DETAILS プロシージャを呼び出すメソッドのシグネチャを次のコード スニペットに示します。  
  
```  
public partial class TypedProcedures_dboClient : System.ServiceModel.ClientBase<TypedProcedures_dbo>, TypedProcedures_dbo{  
public schemas.microsoft.com.Sql._2008._05.ProceduresResultSets.dbo.GET_EMP_DETAILS.StoredProcedureResultSet0[]   
  GET_EMP_DETAILS(System.Nullable<int> emp_id, out int ReturnValue);  
}  
```  
  
 このスニペットで  
  
-   `TypedProcedures_dboClient` クラスの名前です。 この例では、このクラスを使用してストアド プロシージャを呼び出すクライアントを作成します。  
  
-   `public schemas.microsoft.com.Sql._2008._05.ProceduresResultSets.dbo.GET_EMP_DETAILS.StoredProcedureResultSet0[] GET_EMP_DETAILS(System.Nullable<int> emp_id, out int ReturnValue)` この例では、呼び出すメソッドは、ストアド プロシージャを起動します。 このストアド プロシージャは、従業員 ID を受け取り、厳密に型指定された結果セットを返します。  
  
## <a name="creating-a-wcf-client-to-invoke-a-stored-procedure-in-sql-server"></a>SQL Server でストアド プロシージャを呼び出す、WCF クライアントを作成します。  
 WCF クライアントを使用して SQL Server で操作の実行に必要なアクションの汎用的なセットは、一連のタスクで説明されている[SQL アダプターを使用した WCF サービス モデルの概要](overview-of-the-wcf-service-model-with-the-sql-adapter.md)します。 具体的には、WCF クライアントを呼び出すストアド プロシージャ、これは厳密に型指定の結果セットを作成する方法について説明します。 このトピックでは、例として、GET_EMP_DETAILS ストアド プロシージャを呼び出します。 このストアド プロシージャは、各サンプルに用意されている SQL スクリプトを実行して作成されます。  
  
1. Visual Studio で Visual c# プロジェクトを作成します。 このトピックでは、コンソール アプリケーションを作成します。  
  
2. GET_EMP_DETAILS ストアド プロシージャの WCF クライアント クラスを生成します。 対象のプロシージャを選択するかどうかを確認、 **Strongly-Typed プロシージャ**ノード。 WCF クライアント クラスを生成する詳細については、[SQL Server のアイテムの WCF クライアントまたは WCF サービス コントラクトを生成](generate-a-wcf-client-or-wcf-service-contract-for-sql-server-artifacts.md)を参照してください。  
  
   > [!IMPORTANT]
   >  WCF クライアント クラスを生成する前に必ず設定して、 **EnableBizTalkCompatibilityMode**プロパティを false にバインドします。  
  
3. ソリューション エクスプ ローラーへの参照を追加`Microsoft.Adapters.Sql`と`Microsoft.ServiceModel.Channels`します。  
  
4. Program.cs ファイルを開き、次のスニペットの説明に従って、クライアントを作成します。  
  
   ```  
  
             TypedProcedures_dboClient client = new TypedProcedures_dboClient("SqlAdapterBinding_TypedProcedures_dbo");  
   client.ClientCredentials.UserName.UserName = "<Enter username here>";  
   client.ClientCredentials.UserName.Password = "<Enter username here>";  
   ```  
  
    このスニペットで`TypedProcedures_dboClient`SqlAdapterBindingClient.cs で定義されている WCF クライアントです。 このファイルがによって生成された、[!INCLUDE[addadapterservrefshort](../../includes/addadapterservrefshort-md.md)]します。 `SqlAdapterBinding_TypedProcedures_dbo` クライアント エンドポイント構成の名前を指定され、app.config で定義されます。このファイルがによって生成されても、[!INCLUDE[addadapterservrefshort](../../includes/addadapterservrefshort-md.md)]バインドのプロパティとその他の構成設定が含まれています。  
  
   > [!NOTE]
   >  このスニペットでは、構成ファイルからバインドおよびエンドポイント アドレスを使用します。 これらの値は、コードで明示的に指定できます。 クライアント バインディングを指定する、さまざまな方法の詳細については、[SQL アダプタのクライアントのバインディングを構成する](configure-a-client-binding-for-the-sql-adapter.md)を参照してください。  
  
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
  
6. 以下のスニペットの説明に従って GET_EMP_DETAILS ストアド プロシージャを呼び出します。  
  
   ```  
   // Create array of type as specified in the method signature  
   schemas.microsoft.com.Sql._2008._05.ProceduresResultSets.dbo.GET_EMP_DETAILS.StoredProcedureResultSet0[] resultSet =  
      new schemas.microsoft.com.Sql._2008._05.ProceduresResultSets.dbo.GET_EMP_DETAILS.StoredProcedureResultSet0[1];  
   int returnCode;  
  
   try  
   {  
      Console.WriteLine("Calling a stored procedure...");  
      resultSet = client.GET_EMP_DETAILS(10001, out returnCode);  //Invoke the stored procedure  
   }  
   catch (Exception ex)  
   {  
      Console.WriteLine("Exception: " + ex.Message);  
      throw;  
   }  
   Console.WriteLine("The details for the employee with ID '10001' are:");  
   Console.WriteLine("*************************************************");  
  
   for (int i = 0; i < resultSet.Length; i++)  
      {  
         Console.WriteLine("Employee Name        : " + resultSet[i].Name);  
         Console.WriteLine("Employee Designation : " + resultSet[i].Designation);  
         Console.WriteLine("Employee Salary      : " + resultSet[i].Salary);  
      }  
  
   Console.WriteLine("*************************************************");  
  
   ```  
  
7. 次のスニペットの説明に従って、クライアントを閉じます。  
  
   ```  
   client.Close();  
   Console.WriteLine("Press any key to exit...");  
   Console.ReadLine();  
   ```  
  
8. プロジェクトをビルドし、それを実行します。 名前を指定、および給与の従業員 ID は、コンソールに表示されます。  
  
## <a name="see-also"></a>参照  
[WCF サービス モデルを使用してアプリケーションを開発する](develop-sql-applications-using-the-wcf-service-model.md)