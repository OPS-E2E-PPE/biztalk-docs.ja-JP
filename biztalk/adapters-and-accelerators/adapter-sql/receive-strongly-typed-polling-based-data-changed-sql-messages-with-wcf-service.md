---
title: "厳密に型指定されたポーリング ベース データが変更されてから受信 WCF サービスのモデルを使用して SQL Server |Microsoft ドキュメント"
ms.custom: 
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: 
ms.suite: 
ms.tgt_pltfrm: 
ms.topic: article
ms.assetid: b55eda71-1226-43f2-bc2f-e6b35563210b
caps.latest.revision: "8"
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: 4a56ed382f6fa9c106b091b62406feba2dffe704
ms.sourcegitcommit: cb908c540d8f1a692d01dc8f313e16cb4b4e696d
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 09/20/2017
---
# <a name="receive-strongly-typed-polling-based-data-changed-messages-from-sql-server-using-wcf-service-model"></a>厳密に型指定されたポーリング ベース データが変更されてから受信 WCF サービスのモデルを使用して SQL Server
構成することができます、 [!INCLUDE[adaptersqlshort](../../includes/adaptersqlshort-md.md)] SQL Server から厳密に型指定されたポーリング メッセージを受信します。 データベースをポーリングするアダプターを実行するポーリング ステートメントを指定することができます。 ポーリング ステートメントには、SELECT ステートメントまたは結果セットを返すストアド プロシージャを使用できます。 厳密に型指定された結果セットを受信するシナリオで、厳密に型指定されたポーリングを使用する必要があります。 アダプターが厳密に型指定されたポーリングをサポートする方法の詳細については、次を参照してください。[呼び出しをポーリングを使用して受信するためのサポート](../../adapters-and-accelerators/adapter-oracle-ebs/support-for-inbound-calls-using-polling.md)です。  
  
> [!IMPORTANT]
>  かどうかは、単一のアプリケーションに複数のポーリング操作を必要がありますを指定する、 **InboundID**接続一意にする URI の一部として接続プロパティです。 指定した受信 ID は、一意にする操作の名前空間に追加されます。  
  
## <a name="how-this-topic-demonstrates-polling"></a>このトピックの内容がポーリングを示しています  
 このトピックの内容を示すため方法、[!INCLUDE[adaptersqlshort](../../includes/adaptersqlshort-md.md)]メッセージの変更、.NET アプリケーションを作成およびの WCF サービス コントラクトを生成する厳密に型指定されたデータの受信をサポート、 **TypedPolling**操作します。 WCF サービス コントラクトを生成するときに、次を指定することを確認します。  
  
-   指定する必要があります、 **InboundID**接続 URI の一部として。  
  
-   ポーリング ステートメントを指定する必要があります、 **PollingStatement**プロパティをバインドします。  
  
 さらに、その他を指定する場合は、ポーリング関連プロキシ クラスを生成中にバインディングのプロパティを指定して、 **PolledDataAvailableStatement**として。  
  
```  
SELECT COUNT(*) FROM Employee  
```  
  
 **PolledDataAvailableStatement**正の値を含む最初のセルを含む結果セットを返す必要があります。 最初のセルには正の値が含まれていない場合でも、アダプターでは、ポーリング ステートメントは実行されません。  
  
 ポーリング ステートメントの一部として、次の操作を実行します。  
  
1.  Employee テーブルからすべての行を選択します。  
  
2.  ストアド プロシージャ、EmployeeHistory テーブルには Employee テーブルからすべてのレコードを移動するには、(MOVE_EMP_DATA) を実行します。  
  
3.  Employee テーブルに新しいレコードを追加するには、(ADD_EMP_DETAILS) ストアド プロシージャを実行します。 この手順は、従業員名、指定、および給与をパラメーターとして受け取ります。  
  
 これらの操作を実行するは、次を指定する必要があります、 **PollingStatement** WCF サービス コントラクトとヘルパー クラスを生成するときにプロパティをバインドします。  
  
```  
SELECT * FROM Employee;EXEC MOVE_EMP_DATA;EXEC ADD_EMP_DETAILS John, Tester, 100000   
```  
  
 ポーリング ステートメントが実行された後に、Employee テーブルのすべてのレコードが選択されており、SQL Server からメッセージを受信します。 アダプターによって MOVE_EMP_DATA ストアド プロシージャの実行後は、すべてのレコードが EmployeeHistory テーブルに移動されます。 次に、Employee テーブルに新しいレコードを追加する ADD_EMP_DETAILS ストアド プロシージャが実行されます。 次のポーリングの実行には、1 つのレコードだけを返します。 このサイクルは、サービス ホストを終了するまで続けられます。  
  
## <a name="configuring-typed-polling-with-the-sql-adapter-binding-properties"></a>SQL アダプターのプロパティをバインドに型指定されたポーリングを構成します。  
 次の表、[!INCLUDE[adaptersqlshort](../../includes/adaptersqlshort-md.md)]バインドのプロパティ データの変更メッセージを受信するアダプターを構成するために使用します。 以外の場合、 **PollingStatement**バインディング プロパティでは、バインド プロパティをすべてここで示した必要な .NET アプリケーションの実行中にします。 指定する必要があります、 **PollingStatement** WCF サービス コントラクトを生成する前にプロパティのバインド**TypedPolling**操作します。  
  
|プロパティのバインド|Description|  
|----------------------|-----------------|  
|**InboundOperationType**|実行するかどうかを指定します**ポーリング**、 **TypedPolling**、または**通知**操作を受信します。 既定値は**ポーリング**です。 厳密に型指定されたポーリング メッセージを受信するには、これを設定**TypedPolling**です。|  
|**PolledDataAvailableStatement**|すべてのデータがポーリングに使用できるかどうかを判断するアダプターを実行する SQL ステートメントを指定します。 SQL ステートメントには、結果の行と列で構成されるセットを返す必要があります。 SQL ステートメントが指定した行がある場合のみ、 **PollingStatement**プロパティのバインドが実行されます。|  
|**PollingIntervalInSeconds**|秒単位で間隔を指定、[!INCLUDE[adaptersqlshort](../../includes/adaptersqlshort-md.md)]の指定されたステートメントの実行、 **PolledDataAvailableStatement**プロパティをバインドします。 既定値は 30 秒です。 ポーリング間隔では、連続するポーリングの間隔を決定します。 ステートメントは、指定した期間内で実行される、アダプターは、間隔の残り時間を待機します。|  
|**PollingStatement**|SQL Server データベース テーブルをポーリングする SQL ステートメントを指定します。 単純な SELECT ステートメントまたはストアド プロシージャのポーリング ステートメントを指定できます。 既定値は null です。 値を指定する必要があります**PollingStatement**ポーリングを有効にします。 ポーリング ステートメントの実行によって決定される、ポーリングに使用できるデータが場合にのみ、 **PolledDataAvailableStatement**プロパティをバインドします。 セミコロンで区切られた SQL ステートメントの任意の数を指定できます。 **重要:**の**TypedPolling**メタデータを生成する前にこのバインドのプロパティを指定する必要があります。|  
|**PollWhileDataFound**|指定するかどうか、[!INCLUDE[adaptersqlshort](../../includes/adaptersqlshort-md.md)]ポーリング間隔を無視し、継続的に指定された SQL ステートメントを実行、 **PolledDataAvailableStatement**をポーリングするテーブルにデータがある場合、プロパティをバインドします。 テーブルのデータがない場合は、アダプターは、指定されたポーリング間隔で SQL ステートメントを実行する元に戻します。 既定値は**false**です。|  
  
 これらのプロパティの詳細については、次を参照してください。 [SQL Server のアダプターのバインド プロパティの BizTalk アダプターの説明を読む](../../adapters-and-accelerators/adapter-sql/read-about-the-biztalk-adapter-for-sql-server-adapter-binding-properties.md)です。 使用する方法の詳細については、 [!INCLUDE[adaptersqlshort](../../includes/adaptersqlshort-md.md)] SQL サーバーのポーリングを読みます。  
  
## <a name="configuring-strongly-typed-polling-in-the-wcf-service-model"></a>WCF サービス モデルで厳密に型指定されたポーリングを構成します。  
 受信する、**ポーリング**WCF サービス モデルを使用して操作を行う必要があります。  
  
1.  WCF サービス コントラクト (インターフェイス) を生成、 **TypedPolling**アダプターによって公開されるメタデータから操作します。 これを行うには、使用して、[!INCLUDE[addadapterservreflong](../../includes/addadapterservreflong-md.md)]です。 この例の WCF サービス コントラクトを生成するときに確認します。  
  
    -   指定する、 **InboundID**として**従業員**です。  
  
    -   ポーリング ステートメントを指定する、 **PollingStatement**プロパティをバインドします。 この例では、ポーリング ステートメントとして指定します。  
  
        ```  
        SELECT * FROM Employee;EXEC MOVE_EMP_DATA;EXEC ADD_EMP_DETAILS John, Tester, 100000  
        ```  
  
2.  このインターフェイスから WCF サービスを実装します。  
  
3.  サービス ホストを使用してこの WCF サービスをホスト (**System.ServiceModel.ServiceHost**)。  
  
## <a name="about-the-examples-used-in-this-topic"></a>このトピックで使用する例について  
 このトピックの例では、Employee テーブルをポーリングします。 この例は、MOVE_EMP_DATA と ADD_EMP_DETAILS にも使用ストアド プロシージャです。 これらの成果物を生成するスクリプトは、サンプルの値が提供されます。 サンプルの詳細については、次を参照してください。 [SQL アダプタ サンプル](../../adapters-and-accelerators/adapter-sql/samples-for-the-sql-adapter.md)です。 サンプルは、 **TypedPolling_ServiceModel**、これは、このトピックの内容に基づいても付属、[!INCLUDE[adaptersqlshort](../../includes/adaptersqlshort-md.md)]サンプルです。  
  
## <a name="the-wcf-service-contract-and-class"></a>WCF サービス コントラクトとクラス  
 使用することができます、 [!INCLUDE[addadapterservrefshort](../../includes/addadapterservrefshort-md.md)] WCF サービス コントラクト (インターフェイス) およびサポートするためのクラスを作成する、 **TypedPolling**操作します。 詳細については、WCF サービス コントラクトを生成する、次を参照してください。 [SQL Server の成果物のために、WCF クライアントまたは WCF サービス コントラクトを生成](../../adapters-and-accelerators/adapter-sql/generate-a-wcf-client-or-wcf-service-contract-for-sql-server-artifacts.md)です。  
  
### <a name="the-wcf-service-contract-interface"></a>WCF サービス コントラクト (インターフェイス)  
 次のコードに対して生成される WCF サービス コントラクト (インターフェイス) を示しています、 **TypedPolling**操作します。  
  
```  
[System.CodeDom.Compiler.GeneratedCodeAttribute("System.ServiceModel", "3.0.0.0")]  
[System.ServiceModel.ServiceContractAttribute(Namespace="http://schemas.microsoft.com/Sql/2008/05/", ConfigurationName="TypedPolling_Employee")]  
public interface TypedPolling_Employee {  
  
    // CODEGEN: Generating message contract since the wrapper namespace (http://schemas.microsoft.com/Sql/2008/05/TypedPolling/Employee) of message TypedPolling  
    // does not match the default value (http://schemas.microsoft.com/Sql/2008/05/)  
    [System.ServiceModel.OperationContractAttribute(IsOneWay=true, Action="TypedPolling")]  
    void TypedPolling(TypedPolling request);  
}  
```  
  
### <a name="the-message-contracts"></a>メッセージ コントラクト  
 メッセージ コントラクトの名前空間の変更では、 **InboundID**接続 URI を指定した場合のパラメーターです。 この例でとして着信 ID を指定した**従業員**です。 要求メッセージは、厳密に型指定された結果セットを返します。  
  
```  
[System.Diagnostics.DebuggerStepThroughAttribute()]  
[System.CodeDom.Compiler.GeneratedCodeAttribute("System.ServiceModel", "3.0.0.0")]  
[System.ServiceModel.MessageContractAttribute(WrapperName="TypedPolling", WrapperNamespace="http://schemas.microsoft.com/Sql/2008/05/TypedPolling/Employee", IsWrapped=true)]  
public partial class TypedPolling {  
  
[System.ServiceModel.MessageBodyMemberAttribute(Namespace="http://schemas.microsoft.com/Sql/2008/05/TypedPolling/Employee", Order=0)]  
    public schemas.microsoft.com.Sql._2008._05.TypedPolling.Employee.TypedPollingResultSet0[] TypedPollingResultSet0;  
  
[System.ServiceModel.MessageBodyMemberAttribute(Namespace="http://schemas.microsoft.com/Sql/2008/05/TypedPolling/Employee", Order=1)]  
    public schemas.microsoft.com.Sql._2008._05.TypedPolling.Employee.TypedPollingResultSet1[] TypedPollingResultSet1;  
  
    public TypedPolling() {  
    }  
  
    public TypedPolling(schemas.microsoft.com.Sql._2008._05.TypedPolling.Employee.TypedPollingResultSet0[] TypedPollingResultSet0, schemas.microsoft.com.Sql._2008._05.TypedPolling.Employee.TypedPollingResultSet1[] TypedPollingResultSet1) {  
        this.TypedPollingResultSet0 = TypedPollingResultSet0;  
        this.TypedPollingResultSet1 = TypedPollingResultSet1;  
    }  
}  
```  
  
### <a name="wcf-service-class"></a>WCF サービス クラス  
 [!INCLUDE[addadapterservrefshort](../../includes/addadapterservrefshort-md.md)]をサービス コントラクト (インターフェイス) から実装、WCF サービス クラスのスタブを持つファイルも生成します。 ファイルの名前は、SqlAdapterBindingService.cs です。 処理するロジックを挿入することができます、 **TypedPolling**このクラスに直接操作します。 次のコードによって生成された WCF サービス クラスを示しています、[!INCLUDE[addadapterservrefshort](../../includes/addadapterservrefshort-md.md)]です。  
  
```  
namespace SqlAdapterBindingNamespace {  
  
    public class SqlAdapterBindingService : TypedPolling_Employee {  
  
        // CODEGEN: Generating message contract since the wrapper namespace (http://schemas.microsoft.com/Sql/2008/05/TypedPolling/Employee) of message TypedPolling  
        // does not match the default value (http://schemas.microsoft.com/Sql/2008/05/)  
        public virtual void TypedPolling(TypedPolling request) {  
            throw new System.NotImplementedException("The method or operation is not implemented.");  
        }  
    }  
}  
```  
  
## <a name="receiving-strongly-typed-inbound-messages-for-polling-operation"></a>厳密に型指定されたポーリング操作に対して受信メッセージの受信  
 このセクションの内容を使用して受信ポーリングの厳密に型指定されたメッセージを受信する .NET アプリケーションを記述する方法の手順を説明する、[!INCLUDE[adaptersqlshort](../../includes/adaptersqlshort-md.md)]です。  
  
#### <a name="to-receive-polling-messages-from-the-sql-adapter"></a>SQL アダプタからポーリング メッセージを受信するには  
  
1.  使用して、 [!INCLUDE[addadapterservrefshort](../../includes/addadapterservrefshort-md.md)] WCF サービス コントラクト (インターフェイス) およびためのヘルパー クラスを生成する、 **TypedPolling**操作します。 この例の WCF サービス コントラクトを生成するときに、次を指定することを確認します。  
  
    -   指定する必要があります、 **InboundID**として**従業員**です。  
  
    -   ポーリング ステートメントを指定する必要があります、 **PollingStatement**プロパティをバインドします。 この例では、ポーリング ステートメントとして指定します。  
  
        ```  
        SELECT * FROM Employee;EXEC MOVE_EMP_DATA;EXEC ADD_EMP_DETAILS John, Tester, 100000  
        ```  
  
     詳細については、次を参照してください。 [SQL Server の成果物のために、WCF クライアントまたは WCF サービス コントラクトを生成](../../adapters-and-accelerators/adapter-sql/generate-a-wcf-client-or-wcf-service-contract-for-sql-server-artifacts.md)です。 サービス コントラクトとヘルパー クラスを生成するときに、必要に応じてバインドのプロパティを指定することができます。 これは、生成された構成ファイルで正しく設定されていることを保証します。  
  
2.  手順 1. で生成されたインターフェイスとヘルパー クラスからの WCF サービスを実装します。 **TypedPolling**から受信したデータの処理エラーが発生した場合、このクラスのメソッドは、ポーリング トランザクションが中止例外をスローできます、 **TypedPolling**操作以外の場合、メソッドは何も返しません。 次のように、WCF サービス クラスを属性する必要があります。  
  
    ```  
    [ServiceBehavior(InstanceContextMode = InstanceContextMode.Single)]  
    ```  
  
     内で、 **TypedPolling**メソッドを直接、アプリケーション ロジックを実装することができます。 このクラスは、SqlAdapterBindingService.cs で確認できます。 この例では、このコードはサブ クラス、 **SqlAdapterBindingService**クラスです。 このコードでは、厳密に型指定された結果セットとして受信したポーリング メッセージは、コンソールに書き込まれます。  
  
    ```  
    [ServiceBehavior(InstanceContextMode = InstanceContextMode.Single)]  
  
    public class PollingService : SqlAdapterBindingNamespace.SqlAdapterBindingService  
    {  
        public override void TypedPolling(TypedPolling request)  
        {  
            Console.WriteLine("\nNew Polling Records Received");  
            Console.WriteLine("*************************************************");  
            Console.WriteLine("Employee ID\tName\tDesignation\tSalary");  
  
            for (int i = 0; i < request.TypedPollingResultSet0.Length; i++)  
            {  
                Console.WriteLine("{0}\t{1}\t{2}\t{3}",  
                request.TypedPollingResultSet0[i].Employee_ID,  
                request.TypedPollingResultSet0[i].Name,  
                request.TypedPollingResultSet0[i].Designation,  
                request.TypedPollingResultSet0[i].Salary);  
            }  
            Console.WriteLine("*************************************************");  
            Console.WriteLine("\nHit <RETURN> to stop polling");  
        }  
    }  
    ```  
  
3.  [!INCLUDE[adaptersqlshort](../../includes/adaptersqlshort-md.md)]資格情報を受け入れません接続 URI の一部として、SQL Server データベースの資格情報を渡すには、次のクラスを実装する必要があります。 アプリケーションの後半で、SQL Server 資格情報を渡すには、このクラスがインスタンス化されします。  
  
    ```  
    class PollingCredentials : ClientCredentials, IServiceBehavior  
    {  
        public void AddBindingParameters(ServiceDescription serviceDescription, ServiceHostBase serviceHostBase, Collection<ServiceEndpoint> endpoints, BindingParameterCollection bindingParameters)  
        {  
            bindingParameters.Add(this);  
        }  
  
        public void ApplyDispatchBehavior(ServiceDescription serviceDescription, ServiceHostBase serviceHostBase)  
        { }  
  
        public void Validate(ServiceDescription serviceDescription, ServiceHostBase serviceHostBase)  
        { }  
  
        protected override ClientCredentials CloneCore()  
        {  
            ClientCredentials clone = new PollingCredentials();  
            clone.UserName.UserName = this.UserName.UserName;  
            clone.UserName.Password = this.UserName.Password;  
            return clone;  
        }  
    }  
    ```  
  
4.  作成、 **SqlAdapterBinding**とバインドのプロパティを指定することによって、ポーリング操作を構成します。 これは、コードで明示的にまたは構成で宣言によって行うことができます。 指定する必要がありますには、少なくとも、 **InboundOperationType**、 **PolledDataAvailableStatement**、および**PollingStatement**です。  
  
    ```  
    SqlAdapterBinding binding = new SqlAdapterBinding();  
    binding.InboundOperationType = InboundOperation.TypedPolling;  
    binding.PolledDataAvailableStatement = "SELECT COUNT (*) FROM EMPLOYEE";  
    binding.PollingStatement = "SELECT * FROM Employee;EXEC MOVE_EMP_DATA;EXEC ADD_EMP_DETAILS John, Tester, 100000";  
    ```  
  
5.  SQL Server データベース資格情報を指定するには、インスタンス化する、 **PollingCredentials**手順 3. で作成したクラスです。  
  
    ```  
    PollingCredentials credentials = new PollingCredentials();  
    credentials.UserName.UserName = "<Enter user name here>";  
    credentials.UserName.Password = "<Enter password here>";  
    ```  
  
6.  手順 2 で作成した WCF サービスのインスタンスを作成します。  
  
    ```  
    // create service instance  
    PollingService service = new PollingService();  
    ```  
  
7.  インスタンスを作成する**System.ServiceModel.ServiceHost** WCF サービスと基本接続 URI を使用しています。 基本の接続 URI は、着信 ID を含めることはできません。 また、ここで、資格情報を指定する必要があります。  
  
    ```  
    // Enable service host  
    Uri[] baseUri = new Uri[] { new Uri("mssql://mysqlserver//mydatabase") };  
    ServiceHost serviceHost = new ServiceHost(service, baseUri);  
    serviceHost.Description.Behaviors.Add(credentials);  
  
    ```  
  
8.  サービス ホストにサービス エンドポイントを追加します。 これを行うには :  
  
    -   手順 4. で作成したバインディングを使用します。  
  
    -   接続の資格情報を含む URI を指定し、必要に応じて、入力方向の id。  
  
    -   "TypedPolling_Employee"としてコントラクトを指定します。  
  
    ```  
    // Add service endpoint: be sure to specify TypedPolling_Employee as the contract  
    Uri ConnectionUri = new Uri("mssql://mysqlserver//mydatabase?InboundID=Empliyee");  
    serviceHost.AddServiceEndpoint("TypedPolling_Employee", binding, ConnectionUri);  
    ```  
  
9. ポーリングのデータを受信するには、サービス ホストを開きます。 アダプターは、クエリが結果セットを返すときにデータを返します。  
  
    ```  
    // Open the service host to begin polling  
    serviceHost.Open();  
    ```  
  
10. ポーリングを終了するには、サービス ホストを閉じます。  
  
    > [!IMPORTANT]
    >  アダプターは、サービス ホストが閉じられるまでポーリングを続行します。  
  
    ```  
    serviceHost.Close();  
    ```  
  
### <a name="example"></a>例  
 次の例では、Employee テーブルに実行されるポーリング クエリを示します。 ポーリング ステートメントでは、次のタスクを実行します。  
  
1.  Employee テーブルからすべてのレコードを選択します。  
  
2.  EmployeeHistory テーブルに、Employee テーブルからすべてのレコードを移動する MOVE_EMP_DATA ストアド プロシージャを実行します。  
  
3.  Employee テーブルに 1 つのレコードを追加する ADD_EMP_DETAILS ストアド プロシージャを実行します。  
  
 ポーリングの最初のメッセージは、Employee テーブルのすべてのレコードが含まれます。 その後ポーリング メッセージ ADD_EMP_DETAILS ストアド プロシージャによって挿入された最後のレコードのみが含まれます。 アダプターはポーリングを押して、サービス ホストを終了するまで引き続き`<RETURN>`します。  
  
```  
using System;  
using System.Collections.Generic;  
using System.Linq;  
using System.Text;  
  
using Microsoft.Adapters.Sql;  
using Microsoft.ServiceModel.Channels;  
using System.ServiceModel;  
using System.ServiceModel.Description;  
using System.ServiceModel.Channels;  
using System.Collections.ObjectModel;  
  
namespace TypedPolling_ServiceModel  
{  
    [ServiceBehavior(InstanceContextMode = InstanceContextMode.Single)]  
  
    public class PollingService : SqlAdapterBindingNamespace.SqlAdapterBindingService  
    {  
        public override void TypedPolling(TypedPolling request)  
        {  
            Console.WriteLine("\nNew Polling Records Received");  
            Console.WriteLine("*************************************************");  
            Console.WriteLine("Employee ID\tName\tDesignation\tSalary");  
  
            for (int i = 0; i < request.TypedPollingResultSet0.Length; i++)  
            {  
                Console.WriteLine("{0}\t{1}\t{2}\t{3}",  
                request.TypedPollingResultSet0[i].Employee_ID,  
                request.TypedPollingResultSet0[i].Name,  
                request.TypedPollingResultSet0[i].Designation,  
                request.TypedPollingResultSet0[i].Salary);  
            }  
            Console.WriteLine("*************************************************");  
            Console.WriteLine("\nHit <RETURN> to stop polling");  
        }  
    }  
  
    class PollingCredentials : ClientCredentials, IServiceBehavior  
    {  
        public void AddBindingParameters(ServiceDescription serviceDescription, ServiceHostBase serviceHostBase, Collection<ServiceEndpoint> endpoints, BindingParameterCollection bindingParameters)  
        {  
            bindingParameters.Add(this);  
        }  
  
        public void ApplyDispatchBehavior(ServiceDescription serviceDescription, ServiceHostBase serviceHostBase)  
        { }  
  
        public void Validate(ServiceDescription serviceDescription, ServiceHostBase serviceHostBase)  
        { }  
  
        protected override ClientCredentials CloneCore()  
        {  
            ClientCredentials clone = new PollingCredentials();  
            clone.UserName.UserName = this.UserName.UserName;  
            clone.UserName.Password = this.UserName.Password;  
            return clone;  
        }  
    }  
  
    class Program  
    {  
        static void Main(string[] args)  
        {  
            ServiceHost serviceHost = null;  
            try  
            {  
                Console.WriteLine("Sample started...");  
                Console.WriteLine("Press any key to start polling...");  
                Console.ReadLine();  
  
                SqlAdapterBinding binding = new SqlAdapterBinding();  
                binding.InboundOperationType = InboundOperation.TypedPolling;  
                binding.PolledDataAvailableStatement = "SELECT COUNT (*) FROM EMPLOYEE";  
                binding.PollingStatement = "SELECT * FROM Employee;EXEC MOVE_EMP_DATA;EXEC ADD_EMP_DETAILS John, Tester, 100000";  
                Console.WriteLine("Binding properties assigned...");  
  
                // This URI is used to specify the address for the ServiceEndpoint  
                // It must contain the InboundId that was used to generate  
                // the WCF service callback interface  
                Uri ConnectionUri = new Uri("mssql://mysqlserver//mydatabase?InboundId=Employee");  
  
                // This URI is used to initialize the ServiceHost. It cannot contain  
                // the InboundID; otherwise,an exception is thrown when  
                // the ServiceHost is initialized.  
                Uri[] baseUri = new Uri[] { new Uri("mssql://mysqlserver//mydatabase") };  
  
                PollingCredentials credentials = new PollingCredentials();  
                credentials.UserName.UserName = "<Enter user name here>";  
                credentials.UserName.Password = "<Enter password here>";  
  
                Console.WriteLine("Opening service host...");  
                PollingService service = new PollingService();  
                serviceHost = new ServiceHost(service, baseUri);  
                serviceHost.Description.Behaviors.Add(credentials);  
                serviceHost.AddServiceEndpoint("TypedPolling_Employee", binding, ConnectionUri);  
                serviceHost.Open();  
                Console.WriteLine("Service host opened...");  
                Console.WriteLine("Polling started...");  
                Console.ReadLine();  
            }  
            catch (Exception e)  
            {  
                Console.WriteLine("Exception :" + e.Message);  
                Console.ReadLine();  
  
                /* If there is an error it will be specified in the inner exception */  
                if (e.InnerException != null)  
                {  
                    Console.WriteLine("InnerException: " + e.InnerException.Message);  
                    Console.ReadLine();  
                }  
            }  
            finally  
            {  
                // IMPORTANT: you must close the ServiceHost to stop polling  
                if (serviceHost.State == CommunicationState.Opened)  
                    serviceHost.Close();  
                else  
                    serviceHost.Abort();  
            }  
        }  
    }  
}  
  
```  
  
## <a name="see-also"></a>参照  
 [WCF サービス モデルで、SQL アダプターを使用して SQL サーバーにポーリング](../../adapters-and-accelerators/adapter-sql/poll-sql-server-using-the-sql-adapter-with-wcf-service-model.md)