---
title: WCF サービスの Model1 を使用して Oracle データベースの変更通知の受信 |Microsoft Docs
ms.custom: ''
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: ''
ms.suite: ''
ms.tgt_pltfrm: ''
ms.topic: article
ms.assetid: e0f0e2bf-3e76-43cc-85dc-7483dbce1cb5
caps.latest.revision: 6
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: d980b13224918ae66d4ae35ec67f1bf3c3dba8ca
ms.sourcegitcommit: 266308ec5c6a9d8d80ff298ee6051b4843c5d626
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 06/27/2018
ms.locfileid: "36971091"
---
# <a name="receive-oracle-database-change-notifications-using-the-wcf-service-model1"></a>WCF サービスの Model1 を使用して Oracle データベースの変更通知を受信します。
このトピックでは、構成する方法を示します、 [!INCLUDE[adapteroracle_short](../../includes/adapteroracle-short-md.md)] Oracle データベースからクエリ通知メッセージを受信します。 通知を示すために、テーブル、ACCOUNTACTIVITY、「処理済み」列を含むについて考えてみます。 [状態] 列の値に設定がこのテーブルに新しいレコードが挿入されると、' n ' です。 として「処理済み」列が含まれるすべてのレコードを取得する SQL ステートメントを使用して通知を登録することで通知を受信するアダプターを構成することができます 'n' です。 SQL ステートメントを指定することによって行うことができます、 **NotificationStatement**プロパティをバインドします。 アダプターのクライアントが通知を受け取ると、Oracle データベースで、後続のタスクを実行するロジックを含めることができます。 わかりやすくする、この例ではアダプター クライアントの一覧として「処理済み」列が含まれるテーブル内のすべてのレコード 'n' です。  
  
## <a name="configuring-notifications-with-the-oracle-database-adapter-binding-properties"></a>バインドのプロパティの Oracle データベース アダプターを使用した通知の構成  
 次の表にまとめたものです、[!INCLUDE[adapteroracle_short](../../includes/adapteroracle-short-md.md)]バインドのプロパティ構成の Oracle データベースから通知を受信するために使用します。 通知を受信する .NET アプリケーションを実行中には、これらのバインドのプロパティを指定する必要があります。  
  
|プロパティのバインド|説明|  
|----------------------|-----------------|  
|**InboundOperationType**|実行する受信操作を指定します。 通知メッセージを受信するこれを設定**通知**します。|  
|**NotificationPort**|Oracle データベースからのデータベース変更通知をリッスンする ODP.NET を開く必要があるポート番号を指定します。|  
|**NotificationStatement**|クエリ通知に登録するために使用する SELECT ステートメントを指定します。 アダプターは、指定した SELECT ステートメントの変更の結果セットの場合にのみ、通知メッセージを取得します。|  
|**NotifyOnListenerStart**|リスナーが開始されると、アダプターがアダプター クライアントに通知を送信するかどうかを指定します。|  
  
 これらのプロパティの詳細については、次を参照してください。 [for Oracle Database バインド プロパティを構成する](../../adapters-and-accelerators/adapter-oracle-database/configure-the-binding-properties-for-oracle-database.md)します。 使用する方法の詳細については、 [!INCLUDE[adapteroracle_short](../../includes/adapteroracle-short-md.md)] Oracle データベースから通知を受信するさらに読み進める。  
  
## <a name="configuring-notifications-using-the-wcf-service-model"></a>WCF サービス モデルを使用して通知を構成します。  
 WCF サービス モデルを使用して通知を受信するには、次の必要があります。  
  
- WCF サービス コントラクト (インターフェイス) を生成、**通知**アダプターによって公開されているメタデータから操作します。 これを行うには、使用する可能性があります、[!INCLUDE[addadapterservrefshort](../../includes/addadapterservrefshort-md.md)]します。  
  
- 用の WCF クライアントを生成、**選択**ACCOUNTACTIVITY テーブルに対する操作。 これを行うには、使用する可能性があります、[!INCLUDE[addadapterservrefshort](../../includes/addadapterservrefshort-md.md)]します。  
  
- このインターフェイスからの WCF サービスを実装します。  
  
- サービス ホストを使用してこの WCF サービス ホスト (**System.ServiceModel.ServiceHost**)。  
  
## <a name="the-wcf-service-contract-and-class"></a>WCF サービス コントラクトとクラス  
 使用することができます、 [!INCLUDE[addadapterservrefshort](../../includes/addadapterservrefshort-md.md)] WCF サービス コントラクト (インターフェイス) とサポートのクラスを作成する、**通知**操作。 WCF サービス コントラクトを生成する詳細については、次を参照してください。 [WCF クライアントまたは Oracle データベース ソリューションの成果物の WCF サービス コントラクトを生成](../../adapters-and-accelerators/adapter-oracle-database/create-a-wcf-client-or-wcf-service-contract-for-oracle-db-solution-artifacts.md)します。  
  
### <a name="the-wcf-service-contract-interface"></a>WCF サービス コントラクト (インターフェイス)  
 次のコードに対して生成された WCF サービス コントラクト (インターフェイス) を示しています、**通知**操作。  
  
```  
[System.CodeDom.Compiler.GeneratedCodeAttribute("System.ServiceModel", "3.0.0.0")]  
[System.ServiceModel.ServiceContractAttribute(Namespace="http://Microsoft.LobServices.OracleDB/2007/03", ConfigurationName="Notification_OperationGroup")]  
public interface Notification_OperationGroup {  
  
    // CODEGEN: Generating message contract since the wrapper namespace (http://Microsoft.LobServices.OracleDB/2007/03/Notification/) of message Notification  
    // does not match the default value (http://Microsoft.LobServices.OracleDB/2007/03)  
    [System.ServiceModel.OperationContractAttribute(IsOneWay=true, Action="http://Microsoft.LobServices.OracleDB/2007/03/Notification")]  
    void Notification(Notification request);  
}  
```  
  
### <a name="the-message-contracts"></a>メッセージ コントラクト  
 通知操作のメッセージ コントラクトを次に示します。  
  
```  
[System.Diagnostics.DebuggerStepThroughAttribute()]  
[System.CodeDom.Compiler.GeneratedCodeAttribute("System.ServiceModel", "3.0.0.0")]  
[System.ServiceModel.MessageContractAttribute(WrapperName="Notification", WrapperNamespace="http://Microsoft.LobServices.OracleDB/2007/03/Notification/", IsWrapped=true)]  
public partial class Notification {  
  
    [System.ServiceModel.MessageBodyMemberAttribute(Namespace="http://Microsoft.LobServices.OracleDB/2007/03/Notification/", Order=0)]  
    public microsoft.lobservices.oracledb._2007._03.Notification.NotificationDetails[] Details;  
  
    [System.ServiceModel.MessageBodyMemberAttribute(Namespace="http://Microsoft.LobServices.OracleDB/2007/03/Notification/", Order=1)]  
    public string Info;  
  
    [System.ServiceModel.MessageBodyMemberAttribute(Namespace="http://Microsoft.LobServices.OracleDB/2007/03/Notification/", Order=2)]  
    public string[] ResourceNames;  
  
    [System.ServiceModel.MessageBodyMemberAttribute(Namespace="http://Microsoft.LobServices.OracleDB/2007/03/Notification/", Order=3)]  
    public string Source;  
  
    [System.ServiceModel.MessageBodyMemberAttribute(Namespace="http://Microsoft.LobServices.OracleDB/2007/03/Notification/", Order=4)]  
    public string Type;  
  
    public Notification() {  
    }  
  
    public Notification(microsoft.lobservices.oracledb._2007._03.Notification.NotificationDetails[] Details, string Info, string[] ResourceNames, string Source, string Type) {  
        this.Details = Details;  
        this.Info = Info;  
        this.ResourceNames = ResourceNames;  
        this.Source = Source;  
        this.Type = Type;  
    }  
}  
```  
  
### <a name="wcf-service-class"></a>WCF サービス クラス  
 [!INCLUDE[addadapterservrefshort](../../includes/addadapterservrefshort-md.md)]をサービス コントラクト (インターフェイス) から実装された WCF サービス クラスのスタブを持つファイルも生成されます。 ファイルの名前は、OracleDBBindingService.cs です。 処理するロジックを挿入することができます、**通知**このクラスに直接操作します。 次のコードによって生成される WCF サービス クラスを示しています、[!INCLUDE[addadapterservrefshort](../../includes/addadapterservrefshort-md.md)]します。  
  
```  
namespace OracleDBBindingNamespace {  
  
    public class OracleDBBindingService : Notification_OperationGroup {  
  
        // CODEGEN: Generating message contract since the wrapper namespace (http://Microsoft.LobServices.OracleDB/2007/03/Notification/) of message Notification  
        // does not match the default value (http://Microsoft.LobServices.OracleDB/2007/03)  
        public virtual void Notification(Notification request) {  
            throw new System.NotImplementedException("The method or operation is not implemented.");  
        }  
    }  
}  
```  
  
## <a name="receiving-database-change-notifications-using-wcf-service-model"></a>WCF サービス モデルを使用して、受信側のデータベース変更通知  
 このセクションを使用してクエリ通知を受信する .NET アプリケーションを作成する方法の説明、[!INCLUDE[adapteroracle_short](../../includes/adapteroracle-short-md.md)]します。  
  
#### <a name="to-receive-query-notifications"></a>クエリ通知を受信するには  
  
1. 使用して、[!INCLUDE[addadapterservrefshort](../../includes/addadapterservrefshort-md.md)]用の WCF クライアントを生成する**選択**操作、 **ACCOUNTACTIVITY**テーブル。 このクライアントを使用して、通知メッセージを受信した後、Select 操作を実行します。 TableOperation.cs をプロジェクトに新しいクラスを追加し、選択操作を実行する次のコード スニペットを追加します。  
  
   ```  
   using System;  
   using System.Collections.Generic;  
   using System.Linq;  
   using System.Text;  
  
   namespace Notification_ServiceModel  
   {  
       class TableOperation  
       {  
           public void TableOp()  
           {  
               //////////////////////////////////////////////////////////////////////  
               // CREATING THE CLIENT AND SETTING CLIENT CREDENTIALS  
               //////////////////////////////////////////////////////////////////////  
  
               SCOTT_Table_ACCOUNTACTIVITYClient client = new SCOTT_Table_ACCOUNTACTIVITYClient("OracleDBBinding_SCOTT_Table_ACCOUNTACTIVITY");  
               client.ClientCredentials.UserName.UserName = "SCOTT";  
               client.ClientCredentials.UserName.Password = "TIGER";  
  
               ////////////////////////////////////////////////////////////////////  
               // OPENING THE CLIENT  
               //////////////////////////////////////////////////////////////////////  
               try  
               {  
                   Console.WriteLine("Opening the client ...");  
                   client.Open();  
               }  
               catch (Exception ex)  
               {  
                   Console.WriteLine("Exception: " + ex.Message);  
                   throw;  
               }  
  
               ////////////////////////////////////////////////////////////////////////////////////////  
               // SELECTING THE LAST INSERTED VALUE  
               ////////////////////////////////////////////////////////////////////////////////////////  
  
               Console.WriteLine("The application will now select the last inserted record");  
  
               microsoft.lobservices.oracledb._2007._03.SCOTT.Table.ACCOUNTACTIVITY.ACCOUNTACTIVITYRECORDSELECT[] selectRecords;  
  
               try  
               {  
                   selectRecords = client.Select("*", "WHERE PROCESSED = 'n'");  
               }  
               catch (Exception ex)  
               {  
                   Console.WriteLine("Exception: " + ex.Message);  
                   throw;  
               }  
  
               Console.WriteLine("The details of the newly added records are:");  
               Console.WriteLine("********************************************");  
               for (int i = 0; i < selectRecords.Length; i++)  
               {  
                   Console.WriteLine("Transaction ID   : " + selectRecords[i].TID);  
                   Console.WriteLine("Account ID       : " + selectRecords[i].ACCOUNT);  
                   Console.WriteLine("Processed Status : " + selectRecords[i].PROCESSED);  
                   Console.WriteLine();  
               }  
               Console.WriteLine("********************************************");  
           }  
       }  
   }  
  
   ```  
  
2. 使用して、 [!INCLUDE[addadapterservrefshort](../../includes/addadapterservrefshort-md.md)] WCF サービス コントラクト (インターフェイス) とのヘルパー クラスを生成する、**通知**操作。  
  
    詳細については、次を参照してください。 [WCF クライアントまたは Oracle データベース ソリューションの成果物の WCF サービス コントラクトを生成](../../adapters-and-accelerators/adapter-oracle-database/create-a-wcf-client-or-wcf-service-contract-for-oracle-db-solution-artifacts.md)します。 必要に応じて、サービス コントラクトとヘルパー クラスを生成するときにバインドのプロパティを指定することができます。 これは、生成された構成ファイルで設定は正しくことを保証します。  
  
3. 手順 2 で生成されたインターフェイスとヘルパー クラスからの WCF サービスを実装します。 **通知**から受信したデータの処理エラーが発生した場合、このクラスのメソッドは、操作を中止する例外をスローできます、**通知**操作ですそれ以外の場合、メソッドでは。何も返しません。 次のように、WCF サービス クラスを属性する必要があります。  
  
   ```  
   [ServiceBehavior(InstanceContextMode = InstanceContextMode.Single)]  
   ```  
  
    内で、**通知**メソッドを直接、アプリケーション ロジックを実装することができます。 このクラスは、OracleDBBindingService.cs で確認できます。 この例では、このコードはサブ クラス、 **OracleDBBindingService**クラス。 このコードでは、通知メッセージを受信は、コンソールに書き込まれます。 さらに、 **TableOp**内のメソッド、 **TableOperation**選択操作を実行するクラスが呼び出されます。  
  
   ```  
   [ServiceBehavior(InstanceContextMode = InstanceContextMode.Single)]  
  
       public class NotificationService : OracleDBBindingNamespace.OracleDBBindingService  
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
   ```  
  
4. Oracle データベースの資格情報を渡すには、次のクラスを実装する必要があります。 アプリケーションの後半部分の資格情報を渡すには、このクラスをインスタンス化されます。  
  
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
  
5. 作成、 **OracleDBBinding**とバインドのプロパティを指定することでクエリ通知を受信するアダプターを構成します。 コードで明示的に、または構成で宣言的に、これを行うことができます。 指定する必要がありますには、少なくとも、 **InboundOperationType**と**NotificationStatement**プロパティをバインドします。  
  
   ```  
   OracleDBBinding binding = new OracleDBBinding();  
   binding.InboundOperationType = InboundOperation.Notification;  
   binding.NotificationStatement = "SELECT TID,ACCOUNT,PROCESSED FROM APPS.ACCOUNTACTIVITY WHERE PROCESSED = 'n'";  
   binding.NotifyOnListenerStart = true;  
   binding.NotificationPort = 10;  
   ```  
  
   > [!IMPORTANT]
   >  値、 **NotificationPort**プロパティのバインドは、Windows ファイアウォールの例外リストに追加する必要があります、同じポート番号に設定する必要があります。 Windows ファイアウォールの例外リストにポートを追加する方法については、次を参照してください。 [ http://go.microsoft.com/fwlink/?LinkId=196959](http://go.microsoft.com/fwlink/?LinkId=196959)します。  
  
   > [!IMPORTANT]
   >  設定しない場合、 **NotificationPort**バインディング プロパティ、アダプターは、このバインドのプロパティの場合は-1 の既定値を想定しています。 このような場合は、通知メッセージを受信する Windows ファイアウォールを完全に無効にする必要があります。  
  
6. Oracle データベースの資格情報を指定するには、インスタンス化する、 **NotificationCredentials**手順 4. で作成したクラス。  
  
   ```  
   NotificationCredentials credentials = new NotificationCredentials();  
   credentials.UserName.UserName = "SCOTT";  
   credentials.UserName.Password = "TIGER";  
   ```  
  
7. 手順 3 で作成した WCF サービスのインスタンスを作成します。  
  
   ```  
   // create service instance  
   NotificationService service = new NotificationService();  
   ```  
  
8. インスタンスを作成**System.ServiceModel.ServiceHost** WCF サービスと基本の接続 URI を使用しています。 ここで、資格情報を指定することも必要があります。  
  
   ```  
   // Enable service host  
   Uri[] baseUri = new Uri[] { new Uri("oracledb://adapter") };  
   ServiceHost serviceHost = new ServiceHost(service, baseUri);  
   serviceHost.Description.Behaviors.Add(credentials);  
  
   ```  
  
9. サービス ホストにサービス エンドポイントを追加します。 これを行うには :  
  
   - 手順 5. で作成したバインドを使用します。  
  
   - 接続の資格情報を含む URI を指定し、必要に応じて、受信の id。  
  
   - "Notification_OperationGroup"としてコントラクトを指定します。  
  
     ```  
     // Add service endpoint: be sure to specify Notification_OperationGroup as the contract  
     Uri ConnectionUri = new Uri("oracledb://adapter");  
     serviceHost.AddServiceEndpoint("Notification_OperationGroup", binding, ConnectionUri);  
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
 次の例では、ACCOUNTACTIVITY テーブル通知メッセージを受信する .NET アプリケーションを示します。  
  
> [!NOTE]
>  次のコード スニペットをインスタンス化、 **TableOperation.cs**クラスを呼び出す、 **TableOp**メソッド。 クラスとメソッドについては、手順 1. で説明します。  
  
```  
using System;  
using System.Collections.Generic;  
using System.Linq;  
using System.Text;  
using Microsoft.Adapters.OracleDB;  
using Microsoft.ServiceModel.Channels;  
using System.ServiceModel;  
using System.ServiceModel.Description;  
using System.ServiceModel.Channels;  
using System.Collections.ObjectModel;  
  
namespace Notification_ServiceModel  
{  
    [ServiceBehavior(InstanceContextMode = InstanceContextMode.Single)]  
  
    public class NotificationService : OracleDBBindingNamespace.OracleDBBindingService  
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
                Console.WriteLine("Sample started...");  
                Console.WriteLine("Press any key to start receiving notifications...");  
                Console.ReadLine();  
  
                OracleDBBinding binding = new OracleDBBinding();  
                binding.InboundOperationType = InboundOperation.Notification;  
                binding.NotificationStatement = "SELECT TID,ACCOUNT,PROCESSED FROM APPS.ACCOUNTACTIVITY WHERE PROCESSED = 'n'";  
                binding.NotifyOnListenerStart = true;  
                binding.NotificationPort = 10;  
  
                // This URI is used to specify the address for the ServiceEndpoint  
                // It must contain the InboundId that was used to generate  
                // the WCF service callback interface  
                Uri ConnectionUri = new Uri("oracledb://adapter");  
  
                // This URI is used to initialize the ServiceHost. It cannot contain  
                // an InboundID; otherwise,an exception is thrown when  
                // the ServiceHost is initialized.  
                Uri[] baseUri = new Uri[] { new Uri("oracledb://adapter") };  
  
                NotificationCredentials credentials = new NotificationCredentials();  
                credentials.UserName.UserName = "SCOTT";  
                credentials.UserName.Password = "TIGER";  
  
                Console.WriteLine("Opening service host...");  
                NotificationService service = new NotificationService();  
                serviceHost = new ServiceHost(service, baseUri);  
                serviceHost.Description.Behaviors.Add(credentials);  
                serviceHost.AddServiceEndpoint("Notification_OperationGroup", binding, ConnectionUri);  
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
 [WCF サービス モデルを使用して Oracle データベース アプリケーションを開発します。](../../adapters-and-accelerators/adapter-oracle-database/develop-oracle-database-applications-using-the-wcf-service-model.md)