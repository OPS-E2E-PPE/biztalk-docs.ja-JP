---
title: 挿入、更新、削除、またはインターフェイスのテーブルとビューの WCF サービス モデルを使用して操作の選択 |Microsoft ドキュメント
ms.custom: ''
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: ''
ms.suite: ''
ms.tgt_pltfrm: ''
ms.topic: article
ms.assetid: ae613c0e-4d9a-4c66-99e4-dd0443f1d495
caps.latest.revision: 9
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: 4fc9e3968b760be10b428e39662ec3d09db490cd
ms.sourcegitcommit: cb908c540d8f1a692d01dc8f313e16cb4b4e696d
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 09/20/2017
ms.locfileid: "22218146"
---
# <a name="insert-update-delete-or-select-operations-on-interface-tables-and-views-using-the-wcf-service-model"></a>挿入、更新、削除、またはインターフェイスのテーブルとビューの WCF サービス モデルを使用して操作の選択
[!INCLUDE[adapteroraclebusinessshort](../../includes/adapteroraclebusinessshort-md.md)]インターフェイス テーブルの基本的な Insert、Select、Update、および Delete の操作のセットを検出します。 これらの操作を使用すると、単純な Insert、Select、Update を実行し、対象のインターフェイス テーブルに対する WHERE 句で修飾されたステートメントを削除できます。 このトピックでは、WCF サービス モデルを使用してこれらの操作を実行する方法について説明します。  
  
> [!NOTE]
>  [!INCLUDE[adapteroraclebusinessshort](../../includes/adapteroraclebusinessshort-md.md)]のみを選択インターフェイス ビューで操作をサポートしています。  
  
 アダプターがこれらの操作をサポートする方法の詳細については、次を参照してください。[インターフェイス テーブルとのインターフェイス ビューで操作](../../adapters-and-accelerators/adapter-oracle-ebs/operations-on-interface-tables-and-interface-views.md)です。  
  
## <a name="about-the-examples-used-in-this-topic"></a>このトピックで使用する例について  
 このトピックの例では、MS_SAMPLE_EMPLOYEE インターフェイス テーブルでの操作を実行します。 サンプルに用意されているスクリプトを実行して、テーブルが作成されます。 サンプルの詳細については、次を参照してください。 [Oracle EBS アダプター用のサンプル](../../adapters-and-accelerators/adapter-oracle-ebs/samples-for-the-oracle-ebs-adapter.md)です。 サンプルは、 **Interface_Table_Ops**、これは、このトピックの内容に基づいても付属、[!INCLUDE[adapteroraclebusinessshort](../../includes/adapteroraclebusinessshort-md.md)]サンプルです。  
  
## <a name="the-wcf-client-class"></a>WCF クライアント クラス  
 基本的な操作の生成、WCF クライアントの名前を[!INCLUDE[adapteroraclebusinessshort](../../includes/adapteroraclebusinessshort-md.md)]検出次の表に示すように、テーブルまたはビューの名前に基づきます。  
  
|成果物|WCF クライアント名|  
|--------------|---------------------|  
|インターフェイス テーブル|InterfaceTables_ [APP_NAME] _ [SCHEMA]\_[TABLE_NAME] クライアント|  
|インターフェイス ビュー|InterfaceViews_ [APP_NAME] _ [SCHEMA]\_[VIEW_NAME] クライアント|  
  
 [構成]、Oracle E-business Suite アプリケーションの実際の名前を =たとえばのヘルプ。  
  
 [スキーマ]; の成果物のコレクションを =たとえば、アプリです。  
  
 [TABLE_NAME] テーブルの名前を =たとえば、MS_SAMPLE_EMPLOYEE です。  
  
 [VIEW_NAME] ビューの名前を =たとえば、MS_SAMPLE_EMPLOYEE_View です。  
  
### <a name="method-signature-for-invoking-operations-on-tables"></a>テーブルに対する操作を呼び出すためのメソッド シグネチャ  
 テーブル上の基本的な操作について、メソッド シグネチャを次の表に示します。 署名は、ビューの名前空間と名前のテーブルを置換する点を除いて、表示は、同じです。  
  
|操作|メソッド シグネチャ|  
|---------------|----------------------|  
|Insert|文字列の挿入 (InsertRecord [レコード セット)。|  
|Select|SelectRecord を選択 (それら、フィルターの文字列の文字列) です。|  
|Update|文字列の更新プログラム (UpdateRecord RECORDSET、フィルターの文字列です。)|  
|DELETE|文字列の削除 (フィルターの文字列) です。|  
  
 たとえば、次のコードは生成された WCF クライアント クラスのメソッド シグネチャは、選択して 既定のアプリ スキーマ MS_SAMPLE_EMPLOYEE インターフェイス テーブルでの Update 操作、削除、挿入します。  
  
```  
public partial class InterfaceTables_FND_APPS_MS_SAMPLE_EMPLOYEEClient : System.ServiceModel.ClientBase<InterfaceTables_FND_APPS_MS_SAMPLE_EMPLOYEE>, InterfaceTables_FND_APPS_MS_SAMPLE_EMPLOYEE {      
    public SelectRecord[] Select(string COLUMN_NAMES, string FILTER);  
  
    public string Insert(InsertRecord[] RECORDSET);  
  
    public string Update(UpdateRecord RECORDSET, string FILTER);  
  
    public string Delete(string FILTER);  
}  
```  
  
 このスニペットで**InterfaceTables_FND_APPS_MS_SAMPLE_EMPLOYEEClient**によって生成された OracleEBSBindingClient.cs で WCF クラスの名前を指定します、[!INCLUDE[addadapterservrefshort](../../includes/addadapterservrefshort-md.md)]です。  
  
### <a name="parameters-for-table-operations"></a>テーブル操作のパラメーター  
 このセクションでは、各テーブルの操作に必要なパラメーターを説明します。  
  
 **操作を選択します。**  
  
|それら|FILTER|  
|-------------------|------------|  
|ターゲット内の列名のコンマ区切りの一覧たとえば、「EMP_NO, 表記」です。 列の一覧では、結果セットに返される対象の列を指定します。 列リストで指定されていない列は、返されるレコード セット内の .NET の既定値に設定されます。 Nillable 列は、この値は**null**です。|クエリの対象の行を指定する WHERE 句の内容たとえば、"表記 = 'Manager'"です。 このパラメーターを設定することができます**null**ターゲットのすべての行を取得します。|  
  
 Select 操作の戻り値は、指定された列と行を含む厳密に型指定された結果セットです。  
  
 **挿入操作**  
  
|挿入操作の種類|レコード セット|  
|---------------------------|---------------|  
|複数のレコード|テーブルに挿入する必要があります INSERTRECORDS のコレクション。|  
  
 挿入操作の戻り値は、挿入された行の数です。  
  
 **更新操作**  
  
|レコード セット|FILTER|  
|---------------|------------|  
|テーブルで更新する必要があるレコードのコレクション。|クエリの対象の行を指定する WHERE 句の内容たとえば、"表記 = 'Manager'"です。 このパラメーターを設定することができます**null**ターゲットのすべての行を取得します。|  
  
 更新操作の戻り値は、更新された行の数です。  
  
 **削除操作**  
  
 操作は、削除は、削除する行を指定する WHERE 句を入力します。 削除操作の戻り値は、削除された行の数です。  
  
## <a name="creating-a-wcf-client-to-invoke-operations-on-interface-tables-and-interface-views"></a>インターフェイス テーブルに対する操作の呼び出しに WCF クライアントを作成してビューのインターフェイス  
 WCF クライアントを使用して Oracle E-business Suite で操作の実行に必要なアクションの汎用的なセットは、一連のタスクで説明されている[Oracle E-business Suite アダプターで WCF チャネル モデルの概要](../../adapters-and-accelerators/adapter-oracle-ebs/overview-of-the-wcf-channel-model-with-the-oracle-e-business-suite-adapter.md)です。 このセクションでは、基本的な Insert、Select、Update、インターフェイス テーブルに対する Delete 操作を呼び出すための WCF クライアントを作成する方法について説明します。  
  
#### <a name="to-create-a-wcf-client-to-perform-operations-on-tables"></a>テーブルに対する操作を実行する WCF クライアントを作成するには  
  
1.  Visual Studio で Visual c# プロジェクトを作成します。 このトピックでは、コンソール アプリケーションを作成します。  
  
2.  Insert、Select、Update の WCF クライアント クラスを生成し、MS_SAMPLE_EMPLOYEE インターフェイス テーブルの操作を削除します。 詳細については、WCF クライアント クラスを生成する、次を参照してください。 [WCF クライアントまたは Oracle E-business Suite ソリューションの成果物のための WCF サービス コントラクトを生成](../../adapters-and-accelerators/adapter-oracle-ebs/create-a-wcf-client-or-wcf-service-contract-for-oracle-ebs-solution-artifacts.md)です。  
  
    > [!IMPORTANT]
    >  WCF クライアント クラスを生成する前に必ず設定してください、 **EnableBizTalkCompatibilityMode**プロパティを false にバインドします。  
  
3.  ソリューション エクスプ ローラーへの参照を追加`Microsoft.Adapters.OracleEBS`と`Microsoft.ServiceModel.Channels`です。  
  
4.  Program.cs ファイルを開き、次の名前空間を追加します。  
  
    -   `Microsoft.Adapters.OracleEBS`  
  
    -   `System.ServiceModel`  
  
5.  Program.cs ファイルを開き、次のスニペットの説明に従って、クライアントを作成します。  
  
    ```  
    OracleEBSBinding binding = new OracleEBSBinding();  
    EndpointAddress address = new EndpointAddress("oracleebs://ebs_instance_name");  
    InterfaceTables_FND_APPS_MS_SAMPLE_EMPLOYEEClient client = new InterfaceTables_FND_APPS_MS_SAMPLE_EMPLOYEEClient(binding, address);  
    ```  
  
     このスニペットで`InterfaceTables_FND_APPS_MS_SAMPLE_EMPLOYEEClient`OracleEBSBindingClient.cs で定義された WCF クライアントです。 このファイルにより生成されて、[!INCLUDE[addadapterservrefshort](../../includes/addadapterservrefshort-md.md)]です。  
  
    > [!NOTE]
    >  このスニペットでは、アプリケーション コードで明示的にバインドとエンドポイント アドレスを指定するだけです。 これらの値を使用するには、アプリケーション構成ファイルから、app.config、によって生成されるも、[!INCLUDE[addadapterservrefshort](../../includes/addadapterservrefshort-md.md)]です。 クライアント バインディングを指定するさまざまな方法の詳細については、次を参照してください。 [for Oracle E-business Suite バインド クライアントを構成する](../../adapters-and-accelerators/adapter-oracle-ebs/configure-a-client-binding-for-the-oracle-e-business-suite.md)です。  
  
6.  クライアントの資格情報を設定します。  
  
    ```  
    client.ClientCredentials.UserName.UserName = "myuser";  
    client.ClientCredentials.UserName.Password = "mypassword";  
    ```  
  
7.  インターフェイス テーブルに対する操作を実行しているため、アプリケーションのコンテキストを設定する必要があります。 この例では、アプリケーションのコンテキストを設定するを指定する、 **OracleUserName**、 **OraclePassword**、および**OracleEBSResponsibilityName**プロパティをバインドします。 アプリケーション コンテキストの詳細については、次を参照してください。[アプリケーション コンテキストの設定](../../adapters-and-accelerators/adapter-oracle-ebs/set-application-context.md)です。  
  
    ```  
    binding.OracleUserName = "myOracleEBSUserName";  
    binding.OraclePassword = "myOracleEBSPassword";  
    binding.OracleEBSResponsibilityName = "myOracleEBSResponsibility";  
    ```  
  
8.  次のスニペット」の説明に従って、クライアントを開きます。  
  
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
  
9. MS_SAMPLE_EMPLOYEE テーブルに対する挿入操作を呼び出します。  
  
    ```  
    Console.WriteLine("The application will insert a record in the MS_SAMPLE_EMPLOYEE interface table");  
  
    // The date values cannot contain time zone information. Hence, you must use  
    // DateTimeKind.Unspecified to not include the time zone information.  
    DateTime date = new DateTime(DateTime.Now.Ticks, DateTimeKind.Unspecified);  
  
    string result;  
  
    InsertRecord[] recordSet = new InsertRecord[1];  
  
    EMP_NO__COMPLEX_TYPE emp_no = new EMP_NO__COMPLEX_TYPE();  
    emp_no.Value = "10007";  
  
    NAME__COMPLEX_TYPE name = new NAME__COMPLEX_TYPE();  
    name.Value = "John Smith";  
  
    DESIGNATION__COMPLEX_TYPE desig = new DESIGNATION__COMPLEX_TYPE();  
    desig.Value = "Manager";  
  
    SALARY__COMPLEX_TYPE salary = new SALARY__COMPLEX_TYPE();  
    salary.Value = "500000";  
  
    JOIN_DATE__COMPLEX_TYPE doj = new JOIN_DATE__COMPLEX_TYPE();  
    doj.Value = date;  
  
    recordSet[0] = new InsertRecord();  
    recordSet[0].EMP_NO = emp_no;  
    recordSet[0].NAME = name;  
    recordSet[0].DESIGNATION = desig;  
    recordSet[0].SALARY = salary;  
    recordSet[0].JOIN_DATE = doj;  
  
    try  
    {  
       result = client.Insert(recordSet);   
    }  
    catch (Exception ex)  
    {  
       Console.WriteLine("Exception: " + ex.Message);  
       throw;  
    }  
  
    Console.WriteLine("Number of records inserted= " + result);  
    Console.WriteLine("Press any key to continue...");  
    Console.ReadLine();  
  
    ```  
  
     Select を実行する上記のコード スニペットを置き換えることができますを更新、または同様の操作を削除します。 1 つのアプリケーションのすべての操作を実行するコード スニペットを追加することもできます。 これらの操作を実行する方法のコード スニペットを参照してください。[操作の選択](#BKMK_Select)、[更新操作](#BKMK_Update)、および[削除操作](#BKMK_Delete)それぞれします。  
  
10. 次のスニペット」の説明に従って、クライアントを閉じます。  
  
    ```  
    client.Close();  
    Console.WriteLine("Press any key to exit...");  
    Console.ReadLine();  
    ```  
  
11. プロジェクトをビルドし、それを実行します。 アプリケーションは、MS_SAMPLE_EMPLOYEE テーブルにレコードを挿入します。  
  
###  <a name="BKMK_Select"></a>操作を選択します。  
 次のコードは、MS_SAMPLE_EMPLOYEE インターフェイス テーブルを対象とする選択操作を示しています。 選択操作は、テーブルに挿入された最後のレコードを選択します。 返されたレコードは、コンソールに書き込まれます。  
  
```  
Console.WriteLine("The application will now select the last inserted record");  
SelectRecord[] selectRecords;  
try  
{  
   selectRecords = client.Select("*", "WHERE EMP_NO LIKE 10007");  
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
   Console.WriteLine("Employee ID         : " + selectRecords[i].EMP_NO);  
   Console.WriteLine("Employee Name       : " + selectRecords[i].NAME);  
   Console.WriteLine("Employee Desigation : " + selectRecords[i].DESIGNATION);  
   Console.WriteLine("Employee Salary     : " + selectRecords[i].SALARY);  
   Console.WriteLine();  
}  
Console.WriteLine("********************************************");  
Console.WriteLine("Press any key to continue ...");  
Console.ReadLine();  
```  
  
###  <a name="BKMK_Update"></a>更新操作  
 次のコードでは、MS_SAMPLE_EMPLOYEE インターフェイス テーブルを対象とする更新操作を示します。  
  
```  
Console.WriteLine("The application will now update the employee name in the newly inserted record");  
string recordsUpdated;  
UpdateRecord updateRecordSet = new UpdateRecord();  
updateRecordSet.NAME = "Tom Smith";  
updateRecordSet.DESIGNATION = "Accountant";  
  
try  
{  
   recordsUpdated = client.Update(updateRecordSet, "WHERE EMP_NO LIKE 10007");  
}  
catch (Exception ex)  
{  
   Console.WriteLine("Exception: " + ex.Message);  
   throw;  
}  
  
Console.WriteLine("No of records updated: " + recordsUpdated);  
Console.WriteLine("Press any key to continue...");  
Console.ReadLine();  
```  
  
###  <a name="BKMK_Delete"></a>削除操作  
 次のコードは、MS_SAMPLE_EMPLOYEE インターフェイス テーブルを対象とする削除操作を示しています。  
  
```  
Console.WriteLine("The sample will now delete the record that it first inserted");  
string deletedRecords;  
try  
{  
   deletedRecords = client.Delete("WHERE EMP_NO LIKE 10007");  
}  
catch (Exception ex)  
{  
   Console.WriteLine("Exception: " + ex.Message);  
   throw;  
}  
Console.WriteLine("No of records deleted: " + deletedRecords);  
Console.WriteLine("Press any key to exit...");  
Console.ReadLine();  
```  
  
## <a name="see-also"></a>参照  
 [WCF サービス モデルを使用して Oracle E-business Suite アプリケーションを開発します。](../../adapters-and-accelerators/adapter-oracle-ebs/develop-oracle-e-business-suite-applications-using-the-wcf-service-model.md)