---
title: WCF サービス モデルを使用して SQL Server からのポーリングに基づいたデータ変更メッセージの受信 |Microsoft Docs
ms.custom: ''
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: ''
ms.suite: ''
ms.tgt_pltfrm: ''
ms.topic: article
ms.assetid: 8713dd38-65ff-4d89-b23b-a93c06c5ff22
caps.latest.revision: 9
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: 9f302a286bef165f5708d9f3c34fc7c3137451a7
ms.sourcegitcommit: 381e83d43796a345488d54b3f7413e11d56ad7be
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 05/07/2019
ms.locfileid: "65368568"
---
# <a name="receive-polling-based-data-changed-messages-from-sql-server-using-the-wcf-service-model"></a>WCF サービス モデルを使用して SQL Server からのポーリングに基づいたデータ変更メッセージを受信します。
構成することができます、 [!INCLUDE[adaptersqlshort](../../includes/adaptersqlshort-md.md)] SQL Server テーブルまたはビューの定期的なデータ変更メッセージを受信します。 データベースをポーリングするアダプターを実行するポーリング ステートメントを指定することができます。 ポーリング ステートメントには、SELECT ステートメントまたはストアド プロシージャを返す結果セットを使用できます。  

 アダプターがポーリングをサポートする方法の詳細については、次を参照してください。 [SQL アダプターを使用して SQL Server でのポーリング](../../adapters-and-accelerators/adapter-sql/polling-in-sql-server-using-the-sql-adapter.md)します。  

> [!NOTE]
>  このトピックでは、使用する方法を示します、**ポーリング**ポーリング メッセージを使用する操作を受信します。 ポーリング操作のメッセージがない厳密に型指定します。 使用する必要がありますを厳密に型指定されたポーリング メッセージを取得する場合、 **TypedPolling**操作。 使用することも必要があります、 **TypedPolling**工程に単一のアプリケーションで複数の操作をポーリングします。 手順を実行する方法について**TypedPolling**操作を参照してください[SQL Server を使用して WCF サービス モデルからデータ変更のポーリングに基づいたメッセージを受信厳密に型指定された](../../adapters-and-accelerators/adapter-sql/receive-strongly-typed-polling-based-data-changed-sql-messages-with-wcf-service.md)します。  

> [!IMPORTANT]
>  単一のアプリケーションでは、複数のポーリング操作を必要するかどうか、指定する必要あります、 **InboundID**接続して一意の URI の一部として接続プロパティです。 指定した受信 ID は一意になるように操作の名前空間に追加されます。  

## <a name="how-this-topic-demonstrates-polling"></a>このトピックでポーリングしていますか  
 示すために、このトピックでどのように[!INCLUDE[adaptersqlshort](../../includes/adaptersqlshort-md.md)]データの受信をサポートは、メッセージの変更、.NET アプリケーションを作成しの WCF サービス コントラクトを生成、**ポーリング**操作。 ポーリングを指定する場合は、関連するプロパティをバインド WCF サービス コントラクトを生成するときに、指定、 **PolledDataAvailableStatement**として。  

```  
SELECT COUNT(*) FROM Employee  
```  

 **PolledDataAvailableStatement**正の値を格納している最初のセルを含む結果セットを返す必要があります。 最初のセルに正の値が含まれていない場合でも、アダプターでは、ポーリング ステートメントは実行されません。  

 ポーリング ステートメントの一部として、次の操作を実行します。  

1. Employee テーブルからすべての行を選択します。  

2. ストアド プロシージャ、EmployeeHistory テーブルに、Employee テーブルからすべてのレコードを移動するには、(MOVE_EMP_DATA) を実行します。  

3. Employee テーブルに新しいレコードを追加するには、(ADD_EMP_DETAILS) ストアド プロシージャを実行します。 この手順は、従業員の名前、表記、および給与をパラメーターとして受け取ります。  

   これらの操作を実行するは、次を指定する必要があります、 **PollingStatement**プロパティをバインドします。  

```  
SELECT * FROM Employee;EXEC MOVE_EMP_DATA;EXEC ADD_EMP_DETAILS John, Tester, 100000   
```  

 ポーリング ステートメントが実行された後に、Employee テーブルからすべてのレコードが選択されているし、SQL Server からメッセージを受信しました。 アダプターによって MOVE_EMP_DATA ストアド プロシージャの実行後は、すべてのレコードが EmployeeHistory テーブルに移動されます。 次に、Employee テーブルに新しいレコードを追加する ADD_EMP_DETAILS ストアド プロシージャが実行されます。 次のポーリングの実行は、1 つのレコードのみ戻ります。 このサイクルでは、サービス ホストを終了するまで続けられます。  

## <a name="configuring-a-polling-query-with-the-sql-adapter-binding-properties"></a>SQL アダプターのプロパティのバインドと、ポーリング クエリの構成  
 次の表にまとめたものです、[!INCLUDE[adaptersqlshort](../../includes/adaptersqlshort-md.md)]バインドのプロパティのデータ変更メッセージを受信するアダプターを構成するために使用します。 ポーリングの .NET アプリケーションの一部として、これらのバインドのプロパティを指定する必要があります。  


|         プロパティのバインド         |                                                                                                                                                                                                                                         説明                                                                                                                                                                                                                                          |
|----------------------------------|----------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------|
|     **InboundOperationType**     |                                                                                                                                                                             実行するかどうかを指定します**ポーリング**、 **TypedPolling**、または**通知**操作を受信します。 既定値は**ポーリング**します。                                                                                                                                                                              |
| **PolledDataAvailableStatement** |                                                                                       すべてのデータがポーリングに使用できるかどうかを判断するアダプターを実行する SQL ステートメントを指定します。 SQL ステートメントには、結果の行と列で構成されるセットを返す必要があります。 SQL ステートメントが指定した行を使用できる場合のみ、 **PollingStatement**プロパティのバインドが実行されます。                                                                                       |
|   **PollingIntervalInSeconds**   |                         秒単位で間隔を指定、[!INCLUDE[adaptersqlshort](../../includes/adaptersqlshort-md.md)]に指定されたステートメントが実行される、 **PolledDataAvailableStatement**プロパティをバインドします。 既定値は 30 秒です。 ポーリング間隔は、連続するポーリングの間隔を決定します。 ステートメントは、指定した期間内で実行される、アダプターは、残りの時間間隔での待機します。                          |
|       **PollingStatement**       | SQL Server データベースのテーブルをポーリングする SQL ステートメントを指定します。 単純な SELECT ステートメントまたはストアド プロシージャのポーリング ステートメントを指定することができます。 既定値は null です。 値を指定する必要があります**PollingStatement**ポーリングを有効にします。 ポーリング ステートメントの実行によって決定される、ポーリングに使用できるデータが場合にのみ、 **PolledDataAvailableStatement**プロパティをバインドします。 セミコロンで区切られた SQL ステートメントの任意の数を指定できます。 |
|      **PollWhileDataFound**      |                            指定するかどうか、[!INCLUDE[adaptersqlshort](../../includes/adaptersqlshort-md.md)]ポーリング間隔を無視し、継続的に指定された SQL ステートメントを実行、 **PolledDataAvailableStatement**データがポーリングされるテーブルで使用できる場合は、プロパティをバインドします。 テーブルのデータがない場合は、アダプターは、指定されたポーリング間隔で SQL ステートメントを実行する元に戻します。 既定値は**false**します。                             |

 これらのプロパティの詳細については、次を参照してください。 [for SQL Server のアダプターのバインド プロパティの BizTalk アダプターについて](../../adapters-and-accelerators/adapter-sql/read-about-the-biztalk-adapter-for-sql-server-adapter-binding-properties.md)します。 使用する方法の詳細については、[!INCLUDE[adaptersqlshort](../../includes/adaptersqlshort-md.md)]を SQL Server をポーリングするには、さらに読み進める。  

## <a name="configuring-polling-in-the-wcf-service-model"></a>WCF サービス モデルでのポーリングの構成  
 受信する、**ポーリング**WCF サービス モデルを使用するときに操作する必要があります。  

1. WCF サービス コントラクト (インターフェイス) を生成、**ポーリング**アダプターによって公開されているメタデータから操作します。 これを行うには、使用する可能性があります、[!INCLUDE[addadapterservreflong](../../includes/addadapterservreflong-md.md)]します。  

2. このインターフェイスからの WCF サービスを実装します。  

3. サービス ホストを使用してこの WCF サービス ホスト (**System.ServiceModel.ServiceHost**)。  

## <a name="about-the-examples-used-in-this-topic"></a>このトピックで使用する例について  
 このトピックの例では、Employee テーブルをポーリングします。 この例は、MOVE_EMP_DATA と ADD_EMP_DETAILS にも使用ストアド プロシージャ。 これらの成果物を生成するスクリプトは、サンプルで提供されます。 サンプルの詳細については、次を参照してください。 [SQL アダプタのサンプル](../../adapters-and-accelerators/adapter-sql/samples-for-the-sql-adapter.md)します。 サンプルについては、 **Polling_ServiceModel**、これは、このトピックに基づいてがで提供されていることも、[!INCLUDE[adaptersqlshort](../../includes/adaptersqlshort-md.md)]サンプル。  

## <a name="the-wcf-service-contract-and-class"></a>WCF サービス コントラクトとクラス  
 使用することができます、 [!INCLUDE[addadapterservrefshort](../../includes/addadapterservrefshort-md.md)] WCF サービス コントラクト (インターフェイス) とサポートのクラスを作成する、**ポーリング**操作。 WCF サービス コントラクトを生成する詳細については、次を参照してください。 [SQL Server のアイテムの WCF クライアントまたは WCF サービス コントラクトを生成](../../adapters-and-accelerators/adapter-sql/generate-a-wcf-client-or-wcf-service-contract-for-sql-server-artifacts.md)します。  

### <a name="the-wcf-service-contract-interface"></a>WCF サービス コントラクト (インターフェイス)  
 次のコードに対して生成された WCF サービス コントラクト (インターフェイス) を示しています、**ポーリング**操作。  

```  
[System.CodeDom.Compiler.GeneratedCodeAttribute("System.ServiceModel", "3.0.0.0")]  
[System.ServiceModel.ServiceContractAttribute(Namespace="http://schemas.microsoft.com/Sql/2008/05/", ConfigurationName="PollingOperation")]  
public interface PollingOperation {  

    // CODEGEN: Generating message contract since the wrapper namespace (http://schemas.microsoft.com/Sql/2008/05/Polling/) of message Polling  
    // does not match the default value (http://schemas.microsoft.com/Sql/2008/05/)  
    [System.ServiceModel.OperationContractAttribute(IsOneWay=true, Action="Polling")]  
    [System.ServiceModel.XmlSerializerFormatAttribute()]  
    void Polling(Polling request);  
}  
```  

### <a name="the-message-contracts"></a>メッセージ コントラクト  
 メッセージ コントラクトの名前空間を変更した、 **InboundID**接続 URI を指定した場合のパラメーター。 この例では、接続 URI の受信の ID を指定されませんでした。 要求メッセージは、データセットを返します。  

```  
[System.Diagnostics.DebuggerStepThroughAttribute()]  
[System.CodeDom.Compiler.GeneratedCodeAttribute("System.ServiceModel", "3.0.0.0")]  
[System.ServiceModel.MessageContractAttribute(WrapperName="Polling", WrapperNamespace="http://schemas.microsoft.com/Sql/2008/05/Polling/", IsWrapped=true)]  
public partial class Polling {  

[System.ServiceModel.MessageBodyMemberAttribute(Namespace="http://schemas.microsoft.com/Sql/2008/05/Polling/", Order=0)]  
    [System.Xml.Serialization.XmlArrayAttribute(IsNullable=true)]  
    [System.Xml.Serialization.XmlArrayItemAttribute("DataSet", Namespace="http://schemas.datacontract.org/2004/07/System.Data", IsNullable=false)]  
    public System.Data.DataSet[] PolledData;  

    public Polling() {  
    }  

    public Polling(System.Data.DataSet[] PolledData) {  
        this.PolledData = PolledData;  
    }  
}  
```  

### <a name="wcf-service-class"></a>WCF サービス クラス  
 [!INCLUDE[addadapterservrefshort](../../includes/addadapterservrefshort-md.md)]をサービス コントラクト (インターフェイス) から実装された WCF サービス クラスのスタブを持つファイルも生成されます。 ファイルの名前は、SqlAdapterBindingService.cs です。 処理するロジックを挿入することができます、**ポーリング**このクラスに直接操作します。 次のコードによって生成される WCF サービス クラスを示しています、[!INCLUDE[addadapterservrefshort](../../includes/addadapterservrefshort-md.md)]します。  

```  
namespace SqlAdapterBindingNamespace {  

    public class SqlAdapterBindingService : PollingOperation {  

        // CODEGEN: Generating message contract since the wrapper namespace (http://schemas.microsoft.com/Sql/2008/05/Polling/) of message Polling   
        // does not match the default value (http://schemas.microsoft.com/Sql/2008/05/)  
        public virtual void Polling(Polling request) {  
            throw new System.NotImplementedException("The method or operation is not implemented.");  
        }  
    }  
}  
```  

## <a name="receiving-inbound-messages-for-polling-operation"></a>ポーリング操作の着信メッセージを受信  
 このセクションを使用してポーリングの受信メッセージを受信する .NET アプリケーションを作成する方法の説明、[!INCLUDE[adaptersqlshort](../../includes/adaptersqlshort-md.md)]します。  

#### <a name="to-receive-polling-messages-from-the-sql-adapter"></a>SQL アダプタからポーリング メッセージを受信するには  

1. 使用して、 [!INCLUDE[addadapterservrefshort](../../includes/addadapterservrefshort-md.md)] WCF サービス コントラクト (インターフェイス) とのヘルパー クラスを生成する、**ポーリング**操作。 詳細については、次を参照してください。 [SQL Server のアイテムの WCF クライアントまたは WCF サービス コントラクトを生成](../../adapters-and-accelerators/adapter-sql/generate-a-wcf-client-or-wcf-service-contract-for-sql-server-artifacts.md)します。 必要に応じて、サービス コントラクトとヘルパー クラスを生成するときにバインドのプロパティを指定することができます。 これは、生成された構成ファイルで設定は正しくことを保証します。  

2. 手順 1. で生成されたインターフェイスとヘルパー クラスからの WCF サービスを実装します。 **ポーリング**から受信したデータの処理エラーが発生した場合、このクラスのメソッドは、ポーリング トランザクションを中止する例外をスローできます、**ポーリング**操作ですそれ以外の場合、メソッドでは。何も返しません。 次のように、WCF サービス クラスを属性する必要があります。  

   ```  
   [ServiceBehavior(InstanceContextMode = InstanceContextMode.Single)]  
   ```  

    内で、**ポーリング**メソッドを直接、アプリケーション ロジックを実装することができます。 このクラスは、SqlAdapterBindingService.cs で確認できます。 この例では、このコードはサブ クラス、 **SqlAdapterBindingService**クラス。 このコードでは、データセットとして受信したポーリング メッセージは、コンソールに書き込まれます。  

   ```  
   [ServiceBehavior(InstanceContextMode = InstanceContextMode.Single)]  

   public class PollingService : SqlAdapterBindingNamespace.SqlAdapterBindingService  
   {  

   public override void Polling(Polling request)  
   {  
       Console.WriteLine("\nNew Polling Records Received");  
       Console.WriteLine("*************************************************");  
       DataSet[] dataArray = request.PolledData;  
       foreach (DataTable tab in dataArray[0].Tables)  
       {  
           foreach (DataRow row in tab.Rows)  
           {  
               for (int i = 0; i < tab.Columns.Count; i++)  
               {  
                   Console.WriteLine(row[i]);  
               }  
           }  
       }  
       Console.WriteLine("*************************************************");  
       Console.WriteLine("\nHit <RETURN> to stop polling");  
       }  
   }  
   ```  

3. [!INCLUDE[adaptersqlshort](../../includes/adaptersqlshort-md.md)]資格情報を受け入れません接続 URI の一部として、SQL Server データベースの資格情報を渡すには、次のクラスを実装する必要があります。 アプリケーションの後半部分の SQL Server 資格情報を渡すには、このクラスをインスタンス化されます。  

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

4. 作成、 **SqlAdapterBinding**とバインドのプロパティを指定することで、ポーリング操作を構成します。 コードで明示的に、または構成で宣言的に、これを行うことができます。 指定する必要がありますには、少なくとも、 **InboundOperationType**、 **PolledDataAvailableStatement**、および**PollingStatement**します。  

   ```  
   SqlAdapterBinding binding = new SqlAdapterBinding();  
   binding.InboundOperationType = InboundOperation.Polling;  
   binding.PolledDataAvailableStatement = "SELECT COUNT (*) FROM EMPLOYEE";  
   binding.PollingStatement = "SELECT * FROM Employee;EXEC MOVE_EMP_DATA;EXEC ADD_EMP_DETAILS John, Tester, 100000";  
   ```  

5. SQL Server データベースの資格情報を指定するには、インスタンス化する、 **PollingCredentials**手順 3 で作成したクラス。  

   ```  
   PollingCredentials credentials = new PollingCredentials();  
   credentials.UserName.UserName = "<Enter user name here>";  
   credentials.UserName.Password = "<Enter password here>";  
   ```  

6. 手順 2 で作成した WCF サービスのインスタンスを作成します。  

   ```  
   // create service instance  
   PollingService service = new PollingService();  
   ```  

7. インスタンスを作成**System.ServiceModel.ServiceHost** WCF サービスと基本の接続 URI を使用しています。 基本の接続 URI は、指定されている場合、受信の ID を含めることはできません。 ここで、資格情報を指定することも必要があります。  

   ```  
   // Enable service host  
   Uri[] baseUri = new Uri[] { new Uri("mssql://mysqlserver//mydatabase") };  
   ServiceHost serviceHost = new ServiceHost(service, baseUri);  
   serviceHost.Description.Behaviors.Add(credentials);  

   ```  

8. サービス ホストにサービス エンドポイントを追加します。 これを行うには :  

   -   手順 4. で作成したバインドを使用します。  

   -   接続の資格情報を含む URI を指定し、必要に応じて、受信の id。  

   -   "PollingOperation"としてコントラクトを指定します。  

   ```  
   // Add service endpoint: be sure to specify PollingOperation as the contract  
   Uri ConnectionUri = new Uri("mssql://mysqlserver//mydatabase?");  
   serviceHost.AddServiceEndpoint("PollingOperation", binding, ConnectionUri);  
   ```  

9. ポーリングのデータを受信するには、サービス ホストを開きます。 アダプターは、クエリが結果セットを返すたびにデータを返します。  

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
 次の例では、Employee テーブルに実行されるポーリング クエリを示します。 ポーリング ステートメントは、次のタスクを実行します。  

1. Employee テーブルからすべてのレコードを選択します。  

2. EmployeeHistory テーブルに、Employee テーブルからすべてのレコードを移動する MOVE_EMP_DATA ストアド プロシージャを実行します。  

3. Employee テーブルに 1 つのレコードを追加する ADD_EMP_DETAILS ストアド プロシージャを実行します。  

   ポーリングの最初のメッセージは、Employee テーブルからすべてのレコードが格納されます。 その後ポーリング メッセージ ADD_EMP_DETAILS ストアド プロシージャによって挿入された最後のレコードのみが含まれます。 アダプターのポーリングを押して、サービス ホストを終了するまでは引き続き`<RETURN>`します。  

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
using System.Data;  

namespace Polling_ServiceModel  
{  
    [ServiceBehavior(InstanceContextMode = InstanceContextMode.Single)]  

    public class PollingService : SqlAdapterBindingNamespace.SqlAdapterBindingService  
    {  

        public override void Polling(Polling request)  
        {  
            Console.WriteLine("\nNew Polling Records Received");  
            Console.WriteLine("*************************************************");  
            DataSet[] dataArray = request.PolledData;  
            foreach (DataTable tab in dataArray[0].Tables)  
            {  
                foreach (DataRow row in tab.Rows)  
                {  
                    for (int i = 0; i < tab.Columns.Count; i++)  
                    {  
                        Console.WriteLine(row[i]);  
                    }  
                }  
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
                binding.InboundOperationType = InboundOperation.Polling;  
                binding.PolledDataAvailableStatement = "SELECT COUNT (*) FROM EMPLOYEE";  
                binding.PollingStatement = "SELECT * FROM Employee;EXEC MOVE_EMP_DATA;EXEC ADD_EMP_DETAILS John, Tester, 100000";  
                Console.WriteLine("Binding properties assigned...");  

                // This URI is used to specify the address for the ServiceEndpoint  
                // It must contain the InboundId (if any) that was used to generate  
                // the WCF service callback interface  
                Uri ConnectionUri = new Uri("mssql://mysqlserver//mydatabase?");  

                // This URI is used to initialize the ServiceHost. It cannot contain  
                // a query_string (InboundID); otherwise,an exception is thrown when  
                // the ServiceHost is initialized.  
                Uri[] baseUri = new Uri[] { new Uri("mssql://mysqlserver//mydatabase") };  

                PollingCredentials credentials = new PollingCredentials();  
                credentials.UserName.UserName = "<Enter user name here>";  
                credentials.UserName.Password = "<Enter password here>";  

                Console.WriteLine("Opening service host...");  
                PollingService service = new PollingService();  
                serviceHost = new ServiceHost(service, baseUri);  
                serviceHost.Description.Behaviors.Add(credentials);  
                serviceHost.AddServiceEndpoint("PollingOperation", binding, ConnectionUri);  
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
 [SQL Server をポーリングする WCF サービス モデルでの SQL アダプタの使用](../../adapters-and-accelerators/adapter-sql/poll-sql-server-using-the-sql-adapter-with-wcf-service-model.md)