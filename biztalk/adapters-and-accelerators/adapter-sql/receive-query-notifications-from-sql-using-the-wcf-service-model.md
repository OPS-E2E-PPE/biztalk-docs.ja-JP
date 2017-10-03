---
title: "WCF サービス モデルを使用して SQL からクエリ通知を受け取る |Microsoft ドキュメント"
ms.custom: 
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: 
ms.suite: 
ms.tgt_pltfrm: 
ms.topic: article
ms.assetid: 1c9def31-3c5a-4326-b798-31bde0ff2568
caps.latest.revision: "10"
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: 5507bbb21d1b5648a10be2230dd4476eacca1c78
ms.sourcegitcommit: cb908c540d8f1a692d01dc8f313e16cb4b4e696d
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 09/20/2017
---
# <a name="receive-query-notifications-from-sql-using-the-wcf-service-model"></a>WCF サービス モデルを使用して SQL のクエリ通知を受信します。
このトピックの内容を構成する方法を示しています、 [!INCLUDE[adaptersqlshort](../../includes/adaptersqlshort-md.md)] SQL Server データベースからクエリ通知メッセージを受信します。 通知を示すためには、テーブル、従業員、"Status"列を含むを検討してください。 このテーブルに新しいレコードが挿入されると、[状態] 列の値は 0 に設定します。 [状態] 列が「0」であるすべてのレコードを取得する SQL ステートメントを使用して通知を登録することによって通知を受信するアダプターを構成します。 これを行うための SQL ステートメントを指定することによって、 **NotificationStatement**プロパティをバインドします。 アダプターのクライアントは、通知を受信した後、SQL Server データベースで、それ以降の作業を実行するためのロジックを格納できます。 わかりやすくするため、この例では、アダプターのクライアントが「0」として、[状態] 列を持つテーブル内のすべてのレコードを一覧表示します。  
  
> [!NOTE]
>  ユーザー定義型の列を含むテーブルでの操作を実行する場合、必ずするを参照してください[操作と、SQL アダプターを使用してユーザー定義型のテーブルとビューを](../../adapters-and-accelerators/adapter-sql/operations-on-tables-and-views-with-user-defined-types-using-the-sql-adapter.md)トピック アプリケーションの開発を開始する前に.  
  
## <a name="configuring-notifications-with-the-sql-adapter-binding-properties"></a>SQL アダプターのプロパティのバインドと通知の構成  
 次の表、[!INCLUDE[adaptersqlshort](../../includes/adaptersqlshort-md.md)]バインドのプロパティ構成の SQL Server から通知を受信するために使用します。 これらのバインディング プロパティを指定すると、SQL Server データベースから通知を受信する .NET アプリケーションの実行中にあります。  
  
|プロパティのバインド|Description|  
|----------------------|-----------------|  
|**InboundOperationType**|受信操作を実行することを指定します。 通知メッセージを受信するには、これを設定**通知**です。|  
|**NotificationStatement**|SQL ステートメントを指定します (選択または EXEC \<*ストアド プロシージャ*>) のクエリ通知を登録するために使用します。 アダプターは、指定された SQL ステートメントの変更の結果セットの場合にのみ、SQL Server から通知メッセージを取得します。|  
|**NotifyOnListenerStart**|リスナーが開始されたときに、アダプターがアダプターのクライアントに通知を送信するかどうかを指定します。|  
  
 これらのプロパティの詳細については、次を参照してください。 [SQL Server のアダプターのバインド プロパティの BizTalk アダプターの説明を読む](../../adapters-and-accelerators/adapter-sql/read-about-the-biztalk-adapter-for-sql-server-adapter-binding-properties.md)です。 使用する方法の詳細については、[!INCLUDE[adaptersqlshort](../../includes/adaptersqlshort-md.md)]さらに通知を受信する SQL Server から、読み取る。  
  
## <a name="configuring-notifications-using-the-wcf-service-model"></a>WCF サービス モデルを使用して通知を構成します。  
 WCF サービス モデルを使用して通知を受信するには、次の必要があります。  
  
1.  WCF サービス コントラクト (インターフェイス) を生成、**通知**アダプターによって公開されるメタデータから操作します。 これを行うには、使用して、[!INCLUDE[addadapterservrefshort](../../includes/addadapterservrefshort-md.md)]です。  
  
2.  用の WCF クライアントを生成、**選択**Employee テーブルに対して操作します。 これを行うには、使用して、[!INCLUDE[addadapterservrefshort](../../includes/addadapterservrefshort-md.md)]です。  
  
3.  このインターフェイスから WCF サービスを実装します。  
  
4.  サービス ホストを使用してこの WCF サービスをホスト (**System.ServiceModel.ServiceHost**)。  
  
## <a name="about-the-examples-used-in-this-topic"></a>このトピックで使用する例について  
 このトピックの例では、Employee テーブルに対して通知を受信します。 テーブルを生成するスクリプトは、サンプルの値が提供されます。 サンプルの詳細については、次を参照してください。 [SQL アダプタ サンプル](../../adapters-and-accelerators/adapter-sql/samples-for-the-sql-adapter.md)です。 サンプルは、 **Notification_ServiceModel**、これは、このトピックの内容に基づいても付属、[!INCLUDE[adaptersqlshort](../../includes/adaptersqlshort-md.md)]サンプルです。  
  
## <a name="the-wcf-service-contract-and-class"></a>WCF サービス コントラクトとクラス  
 使用することができます、 [!INCLUDE[addadapterservrefshort](../../includes/addadapterservrefshort-md.md)] WCF サービス コントラクト (インターフェイス) およびサポートするためのクラスを作成する、**通知**操作します。 詳細については、WCF サービス コントラクトを生成する、次を参照してください。 [SQL Server の成果物のために、WCF クライアントまたは WCF サービス コントラクトを生成](../../adapters-and-accelerators/adapter-sql/generate-a-wcf-client-or-wcf-service-contract-for-sql-server-artifacts.md)です。  
  
### <a name="the-wcf-service-contract-interface"></a>WCF サービス コントラクト (インターフェイス)  
 次のコードに対して生成される WCF サービス コントラクト (インターフェイス) を示しています、**通知**操作します。  
  
```  
[System.CodeDom.Compiler.GeneratedCodeAttribute("System.ServiceModel", "3.0.0.0")]  
[System.ServiceModel.ServiceContractAttribute(Namespace="http://schemas.microsoft.com/Sql/2008/05/", ConfigurationName="NotificationOperation")]  
public interface NotificationOperation {  
  
    // CODEGEN: Generating message contract since the wrapper namespace (http://schemas.microsoft.com/Sql/2008/05/Notification/) of message  
    // Notification does not match the default value (http://schemas.microsoft.com/Sql/2008/05/)  
    [System.ServiceModel.OperationContractAttribute(IsOneWay=true, Action="Notification")]  
    void Notification(Notification request);  
}  
```  
  
### <a name="the-message-contracts"></a>メッセージ コントラクト  
 通知操作のメッセージ コントラクトを次に示します。  
  
```  
[System.Diagnostics.DebuggerStepThroughAttribute()]  
[System.CodeDom.Compiler.GeneratedCodeAttribute("System.ServiceModel", "3.0.0.0")]  
[System.ServiceModel.MessageContractAttribute(WrapperName="Notification", WrapperNamespace="http://schemas.microsoft.com/Sql/2008/05/Notification/", IsWrapped=true)]  
public partial class Notification {  
  
    [System.ServiceModel.MessageBodyMemberAttribute(Namespace="http://schemas.microsoft.com/Sql/2008/05/Notification/", Order=0)]  
    public string Info;  
  
    [System.ServiceModel.MessageBodyMemberAttribute(Namespace="http://schemas.microsoft.com/Sql/2008/05/Notification/", Order=1)]  
    public string Source;  
  
    [System.ServiceModel.MessageBodyMemberAttribute(Namespace="http://schemas.microsoft.com/Sql/2008/05/Notification/", Order=2)]  
    public string Type;  
  
    public Notification() {  
    }  
  
    public Notification(string Info, string Source, string Type) {  
        this.Info = Info;  
        this.Source = Source;  
        this.Type = Type;  
    }  
}  
```  
  
### <a name="wcf-service-class"></a>WCF サービス クラス  
 [!INCLUDE[addadapterservrefshort](../../includes/addadapterservrefshort-md.md)]をサービス コントラクト (インターフェイス) から実装、WCF サービス クラスのスタブを持つファイルも生成します。 ファイルの名前は、SqlAdapterBindingService.cs です。 処理するロジックを挿入することができます、**通知**このクラスに直接操作します。 次のコードによって生成された WCF サービス クラスを示しています、[!INCLUDE[addadapterservrefshort](../../includes/addadapterservrefshort-md.md)]です。  
  
```  
namespace SqlAdapterBindingNamespace {  
  
    public class SqlAdapterBindingService : NotificationOperation {  
  
        // CODEGEN: Generating message contract since the wrapper namespace (http://schemas.microsoft.com/Sql/2008/05/Notification/)   
        // of message Notification does not match the default value (http://schemas.microsoft.com/Sql/2008/05/)  
        public virtual void Notification(Notification request) {  
            throw new System.NotImplementedException("The method or operation is not implemented.");  
        }  
    }  
}  
```  
  
## <a name="receiving-query-notifications-using-wcf-service-model"></a>WCF サービスのモデルを使用してクエリ通知を受信  
 このセクションの内容を使用してクエリ通知を受信する .NET アプリケーションを作成する方法の手順を説明する、[!INCLUDE[adaptersqlshort](../../includes/adaptersqlshort-md.md)]です。  
  
#### <a name="to-receive-query-notifications"></a>クエリ通知を受信するには  
  
1.  使用して、[!INCLUDE[addadapterservrefshort](../../includes/addadapterservrefshort-md.md)]用の WCF クライアントを生成する**選択**での操作、**従業員**テーブル。 通知メッセージを受信後に Select 操作を実行するのにこのクライアントを使用します。 新しいクラスを TableOperation.cs をプロジェクトに追加し、Select 操作を実行する次のコード スニペットを追加します。  
  
    ```  
    using System;  
    using System.Collections.Generic;  
    using System.Linq;  
    using System.Text;  
  
    namespace Notification_ServiceModel  
    {  
        public class TableOperation  
        {  
            public void TableOp()  
            {  
                ///////////////////////////////////////////////////////////////////////  
                // CREATING THE CLIENT  
                ///////////////////////////////////////////////////////////////////////  
  
                TableOp_dbo_EmployeeClient client = new TableOp_dbo_EmployeeClient("SqlAdapterBinding_TableOp_dbo_Employee");  
  
                client.ClientCredentials.UserName.UserName = "<Enter user name here>";  
                client.ClientCredentials.UserName.Password = "<Enter password here>";  
  
                ///////////////////////////////////////////////////////////////////////  
                // OPENING THE CLIENT  
                ///////////////////////////////////////////////////////////////////////  
  
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
  
                ///////////////////////////////////////////////////////////////////////  
                // SELECTING THE LAST INSERTED RECORD FROM THE TABLE  
                ///////////////////////////////////////////////////////////////////////  
                schemas.microsoft.com.Sql._2008._05.Types.Tables.dbo.Employee[] selectRecords;  
  
                try  
                {  
                    selectRecords = client.Select("*", "where Status=0");  
                }  
  
                catch (Exception ex)  
                {  
                    Console.WriteLine("Exception: " + ex.Message);  
                    throw;  
                }  
  
                Console.WriteLine("The details of the newly added employee are:");  
                Console.WriteLine("********************************************");  
                for (int i = 0; i \< selectRecords.Length; i++)  
                {  
                    Console.WriteLine("Employee Name      : " + selectRecords[i].Name);  
                    Console.WriteLine("Employee Designation: " + selectRecords[i].Designation);  
                    Console.WriteLine("Employee Status    : " + selectRecords[i].Status);  
                    Console.WriteLine();  
                }  
                Console.WriteLine("********************************************");  
  
    ```  
  
    > [!IMPORTANT]
    >  このコード スニペットは、Point UDT 列を含む Employee テーブルでの操作を実行するため、アプリケーションの実行中に、プロジェクトの \bin\Debug フォルダーの下、UDT の DLL を配置することを確認します。  
  
2.  使用して、 [!INCLUDE[addadapterservrefshort](../../includes/addadapterservrefshort-md.md)] WCF サービス コントラクト (インターフェイス) およびためのヘルパー クラスを生成する、**通知**操作します。  
  
     詳細については、次を参照してください。 [SQL Server の成果物のために、WCF クライアントまたは WCF サービス コントラクトを生成](../../adapters-and-accelerators/adapter-sql/generate-a-wcf-client-or-wcf-service-contract-for-sql-server-artifacts.md)です。 サービス コントラクトとヘルパー クラスを生成するときに、必要に応じてバインドのプロパティを指定することができます。 これは、生成された構成ファイルで正しく設定されていることを保証します。  
  
3.  手順 2. で生成されたインターフェイスとヘルパー クラスからの WCF サービスを実装します。 **通知**から受信したデータの処理エラーが発生した場合、このクラスのメソッドは、操作を中止する例外をスローできます、**通知**操作ですそれ以外の場合、メソッドは。何も返しません。 次のように、WCF サービス クラスを属性する必要があります。  
  
    ```  
    [ServiceBehavior(InstanceContextMode = InstanceContextMode.Single)]  
    ```  
  
     内で、**通知**メソッドを直接、アプリケーション ロジックを実装することができます。 このクラスは、SqlAdapterBindingService.cs で確認できます。 この例では、このコードはサブ クラス、 **SqlAdapterBindingService**クラスです。 このコードでは、受信した通知メッセージは、コンソールに書き込まれます。 さらに、 **TableOp**メソッド内で、 **TableOperation**選択操作を実行するクラスが呼び出されます。  
  
    ```  
    [ServiceBehavior(InstanceContextMode = InstanceContextMode.Single)]  
  
    public class NotificationService : SqlAdapterBindingNamespace.SqlAdapterBindingService  
    {  
        public override void Notification(Notification request)  
        {  
            Console.WriteLine("\nNew Notification Received");  
            Console.WriteLine("*************************************************");  
            Console.WriteLine(request.Info);  
            Console.WriteLine(request.Source);  
            Console.WriteLine(request.Type);  
            Console.WriteLine("*************************************************");  
  
            // Invoke th TableOp method in the TableOperation class  
            TableOperation Ops = new TableOperation();  
            Ops.TableOp();  
        }  
    }  
    ```  
  
4.  [!INCLUDE[adaptersqlshort](../../includes/adaptersqlshort-md.md)]資格情報を受け入れません接続 URI の一部として、SQL Server データベースの資格情報を渡すには、次のクラスを実装する必要があります。 アプリケーションの後半で、SQL Server 資格情報を渡すには、このクラスがインスタンス化されします。  
  
    ```  
    class NotificationCredentials : ClientCredentials, IServiceBehavior  
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
            ClientCredentials clone = new NotificationCredentials();  
            clone.UserName.UserName = this.UserName.UserName;  
            clone.UserName.Password = this.UserName.Password;  
            return clone;  
        }  
    }  
    ```  
  
5.  作成、 **SqlAdapterBinding**とバインドのプロパティを指定することでクエリ通知を受信するアダプターを構成します。 これは、コードで明示的にまたは構成で宣言によって行うことができます。 指定する必要がありますには、少なくとも、 **InboundOperationType**と**NotificationStatement**プロパティをバインドします。  
  
    ```  
    SqlAdapterBinding binding = new SqlAdapterBinding();  
    binding.InboundOperationType = InboundOperation.Notification;  
    binding.NotificationStatement = "SELECT Employee_ID, Name FROM dbo.Employee WHERE Status=0";  
    binding.NotifyOnListenerStart = true;  
    ```  
  
6.  SQL Server データベース資格情報を指定するには、インスタンス化する、 **NotificationCredentials**手順 4. で作成したクラスです。  
  
    ```  
    NotificationCredentials credentials = new NotificationCredentials();  
    credentials.UserName.UserName = "<Enter user name here>";  
    credentials.UserName.Password = "<Enter password here>";  
    ```  
  
7.  手順 3 で作成した WCF サービスのインスタンスを作成します。  
  
    ```  
    // create service instance  
    NotificationService service = new NotificationService();  
    ```  
  
8.  インスタンスを作成する**System.ServiceModel.ServiceHost** WCF サービスと基本接続 URI を使用しています。 また、ここで、資格情報を指定する必要があります。  
  
    ```  
    // Enable service host  
    Uri[] baseUri = new Uri[] { new Uri("mssql://mysqlserver//mydatabase") };  
    ServiceHost serviceHost = new ServiceHost(service, baseUri);  
    serviceHost.Description.Behaviors.Add(credentials);  
  
    ```  
  
9. サービス ホストにサービス エンドポイントを追加します。 これを行うには :  
  
    -   手順 5. で作成したバインディングを使用します。  
  
    -   接続の資格情報を含む URI を指定し、必要に応じて、入力方向の id。  
  
    -   "NotificationOperation"としてコントラクトを指定します。  
  
    ```  
    // Add service endpoint: be sure to specify NotificationOperation as the contract  
    Uri ConnectionUri = new Uri("mssql://mysqlserver//mydatabase?");  
    serviceHost.AddServiceEndpoint("NotificationOperation", binding, ConnectionUri);  
    ```  
  
10. 通知メッセージを受信するには、サービス ホストを開きます。  
  
    ```  
    // Open the service host to begin receiving notifications  
    serviceHost.Open();  
    ```  
  
11. 通知の受信を停止するには、サービス ホストを閉じます。  
  
    ```  
    serviceHost.Close();  
    ```  
  
### <a name="example"></a>例  
 次の例では、Employee テーブルの通知メッセージを受信する .NET アプリケーションを示します。  
  
> [!NOTE]
>  次のコード スニペットをインスタンス化、 **TableOperation.cs**クラスとなり、 **TableOp**メソッドです。 クラスとメソッドについては、手順 1. で説明します。  
  
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
  
namespace Notification_ServiceModel  
{  
    [ServiceBehavior(InstanceContextMode = InstanceContextMode.Single)]  
    public class NotificationService : SqlAdapterBindingNamespace.SqlAdapterBindingService  
    {  
        public override void Notification(Notification request)  
        {  
            Console.WriteLine("\nNew Notification Received");  
            Console.WriteLine("*************************************************");  
            Console.WriteLine(request.Info);  
            Console.WriteLine(request.Source);  
            Console.WriteLine(request.Type);  
            Console.WriteLine("*************************************************");  
            TableOperation Ops = new TableOperation();  
            Ops.TableOp();  
        }  
    }  
  
    class NotificationCredentials : ClientCredentials, IServiceBehavior  
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
            ClientCredentials clone = new NotificationCredentials();  
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
                SqlAdapterBinding binding = new SqlAdapterBinding();  
                binding.InboundOperationType = InboundOperation.Notification;  
                binding.NotificationStatement = "SELECT Employee_ID, Name FROM dbo.Employee WHERE Status=0";  
                binding.NotifyOnListenerStart = true;  
  
                // This URI is used to specify the address for the ServiceEndpoint  
                // It must contain the InboundId (if any) that was used to generate  
                // the WCF service callback interface  
                Uri ConnectionUri = new Uri("mssql://mysqlserver//mydatabase?");  
  
                // This URI is used to initialize the ServiceHost. It cannot contain  
                // a query_string (InboundID); otherwise,an exception is thrown when  
                // the ServiceHost is initialized.  
                Uri[] baseUri = new Uri[] { new Uri("mssql://mysqlserver//mydatabase") };  
  
                NotificationCredentials credentials = new NotificationCredentials();  
                credentials.UserName.UserName = "<Enter user name here>";  
                credentials.UserName.Password = "<Enter password here>";  
  
                Console.WriteLine("Opening service host...");  
                NotificationService service = new NotificationService();  
                serviceHost = new ServiceHost(service, baseUri);  
                serviceHost.Description.Behaviors.Add(credentials);  
                serviceHost.AddServiceEndpoint("NotificationOperation", binding, ConnectionUri);  
                serviceHost.Open();  
                Console.WriteLine("Service host opened...");  
                Console.WriteLine("Waiting for notification...");  
  
                Console.WriteLine("\nHit <RETURN> to stop receiving notification");  
                Console.ReadLine();  
            }  
            catch (Exception e)  
            {  
                Console.WriteLine("Exception :" + e.Message);  
                Console.ReadLine();  
  
                // If there is an error it will be specified in the inner exception   
                if (e.InnerException != null)  
                {  
                    Console.WriteLine("InnerException: " + e.InnerException.Message);  
                    Console.ReadLine();  
                }  
            }  
            finally  
            {  
                // IMPORTANT: you must close the ServiceHost to stop receiving notifications  
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
[WCF サービス モデルを使用して SQL アプリケーションを開発します。](../../adapters-and-accelerators/adapter-sql/develop-sql-applications-using-the-wcf-service-model.md)