---
title: SELECT ステートメントを使用して WCF サービス モデルとポーリング Oracle E-business Suite |Microsoft Docs
ms.custom: ''
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: ''
ms.suite: ''
ms.tgt_pltfrm: ''
ms.topic: article
ms.assetid: 521d58e4-73b1-48a8-9a0a-9e733386c1b5
caps.latest.revision: 7
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: 8484acc15d2328ab444a8df6e55dc0ff952899a6
ms.sourcegitcommit: 266308ec5c6a9d8d80ff298ee6051b4843c5d626
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 06/27/2018
ms.locfileid: "37000699"
---
# <a name="poll-oracle-e-business-suite-using-select-statement-with-the-wcf-service-model"></a>SELECT ステートメントを使用して WCF サービス モデルとポーリング Oracle E-business Suite
構成することができます、[!INCLUDE[adapteroraclebusinessshort](../../includes/adapteroraclebusinessshort-md.md)]を継続的に、インターフェイス テーブルをポーリングする SELECT ステートメントを使用して、定期的なデータ変更メッセージを受信するビュー、テーブル、および Oracle E-business Suite でのビューのインターフェイスします。 Oracle E-business Suite をポーリングするアダプターを定期的に実行するポーリング ステートメントと SELECT ステートメントを指定できます。 ポスト ポーリング PL/SQL コード ブロックを指定することも、アダプターがポーリング ステートメントが実行された後に実行します。  

 ポーリングを有効にする、このトピックの説明に従って、特定のバインド プロパティの条件を指定する必要があります。  アダプターがポーリングをサポートする方法の詳細については、[受信呼び出しのポーリングを使用してサポート](../../adapters-and-accelerators/adapter-oracle-ebs/support-for-inbound-calls-using-polling.md)を参照してください。  

## <a name="configuring-a-polling-operation-with-oracle-e-business-suite-adapter-binding-properties"></a>Oracle E-business Suite アダプターのバインドのプロパティをポーリング操作を構成します。  
 次の表にまとめたものです、[!INCLUDE[adapteroraclebusinessshort](../../includes/adapteroraclebusinessshort-md.md)]メッセージのバインドのプロパティを使用するデータを受信するアダプターの構成を変更します。 ポーリング アプリケーションを実行中に、これらのバインドのプロパティを指定する必要があります。  


|         プロパティのバインド         |                                                                                                                                                                                                                            説明                                                                                                                                                                                                                             |
|----------------------------------|--------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------|
|     **InboundOperationType**     |                                                                                                                                                                          実行するかどうかを指定します**ポーリング**または**通知**操作を受信します。 既定値は**ポーリング**します。                                                                                                                                                                          |
| **PolledDataAvailableStatement** |                                                                                                             すべてのデータがポーリングに使用できるかどうかを判断するアダプターを実行する SQL ステートメントを指定します。 指定した SELECT ステートメントのレコードを使用できる場合にのみ、 **PollingInput**プロパティのバインドが実行されます。                                                                                                              |
|       **PollingInterval**        | 秒単位で間隔を指定、[!INCLUDE[adapteroraclebusinessshort](../../includes/adapteroraclebusinessshort-md.md)]に指定されたステートメントが実行される、 **PolledDataAvailableStatement**プロパティをバインドします。 既定値は 30 秒です。 ポーリング間隔は、連続するポーリングの間隔を決定します。 ステートメントは、指定した期間内で実行される、アダプターが間隔内の残りの時間の間スリープします。 |
|         **PollingInput**         |                         ポーリング ステートメントを指定します。 SELECT ステートメントを使用してポーリングする、このバインドのプロパティの SELECT ステートメントを指定する必要があります。 既定値は null です。<br /><br /> 値を指定する必要があります**PollingInput**ポーリングを有効にするプロパティをバインドします。 ポーリング ステートメントの実行によって決定される、ポーリングに使用できるデータが場合にのみ、 **PolledDataAvailableStatement**プロパティをバインドします。                          |
|        **PollingAction**         |                                                                                                                ポーリング操作のアクションを指定します。 使用して、操作に対して生成されたサービスのインターフェイスからポーリング アクションを決定することができます、[!INCLUDE[addadapterservreflong](../../includes/addadapterservreflong-md.md)]します。                                                                                                                |
|      **PostPollStatement**       |                                                                                                                                                                  指定されたステートメントの後に実行されるステートメント ブロックを指定します、 **PollingInput**プロパティのバインドを実行します。                                                                                                                                                                  |
|      **PollWhileDataFound**      |                                    指定するかどうか、[!INCLUDE[adapteroraclebusinessshort](../../includes/adapteroraclebusinessshort-md.md)]ポーリング間隔を無視し、継続的にデータがポーリングされるテーブルで使用できる場合に、ポーリング ステートメントを実行します。 テーブルのデータがない場合は、アダプターは、指定されたポーリング間隔でポーリング ステートメントを実行する元に戻します。 既定値は false です。                                     |

 これらのプロパティの詳細については、[Oracle E-business Suite バインド プロパティの BizTalk アダプターについて](../../adapters-and-accelerators/adapter-oracle-ebs/read-about-the-biztalk-adapter-for-oracle-e-business-suite-binding-properties.md)を参照してください。 使用する方法の詳細については、 [!INCLUDE[adapteroraclebusinessshort](../../includes/adapteroraclebusinessshort-md.md)] Oracle データベースをポーリングするさらに読み進める。  

## <a name="how-this-topic-demonstrates-polling"></a>このトピックでポーリングしていますか  
 示すために、このトピックの「方法、 [!INCLUDE[adapteroraclebusinessshort](../../includes/adapteroraclebusinessshort-md.md)] SELECT ステートメントを使用してメッセージを変更するデータの受信をサポート、ポーリングすると、 **MS_SAMPLE_EMPLOYEE**インターフェイス テーブルに、**アプリケーション オブジェクト ライブラリ**アプリケーション。 Oracle E-business Suite でこれらのオブジェクトを作成するサンプルで提供される create_apps_artifacts.sql スクリプトを実行するときに、このテーブルが作成されます。  

 ポーリング操作を説明するために、次の項目行います。  

-   SELECT ステートメントを指定、 **PolledDataAvailableStatement**データがある場所インターフェイス テーブルの中にポーリングされます (MS_SAMPLE_EMPLOYEE) を決定するプロパティをバインドします。 この例では、としては、このバインド プロパティを設定できます。  

    ```  
    SELECT COUNT (*) FROM MS_SAMPLE_EMPLOYEE  
    ```  

     これにより、MS_SAMPLE_EMPLOYEE インターフェイス テーブルにいくつかのレコードがある場合にのみ、アダプターがポーリング ステートメントを実行します。  

-   SELECT ステートメントを指定、 **PollingInput**プロパティをバインドします。 このステートメントは、MS_SAMPLE_EMPLOYEE インターフェイス テーブル内のすべての行を取得します。 この例では、としては、このバインド プロパティを設定できます。  

    ```  
    SELECT * FROM MS_SAMPLE_EMPLOYEE FOR UPDATE  
    ```  

    > [!NOTE]
    >  SELECT ステートメントで使用される FOR UPDATE 句の詳細については、[Oracle E-business Suite からのポーリングに基づいたデータ変更メッセージを受信](../../adapters-and-accelerators/adapter-oracle-ebs/receive-polling-based-data-changed-messages-from-oracle-e-business-suite.md)を参照してください。  

-   DELETE ステートメントを指定の一部として、 **PostPollStatement**プロパティをバインドします。 このステートメントは、すべてのデータを MS_SAMPLE_EMPLOYEE インターフェイス テーブルから削除されます。 この例では、としては、このバインド プロパティを設定できます。  

    ```  
    DELETE FROM MS_SAMPLE_EMPLOYEE  
    ```  

     このような場合は、次回の指定されたステートメント**PollingInput**は実行すると、それをフェッチできませんすべてのデータ。  

-   多くのデータは MS_SAMPLE_EMPLOYEE インターフェイス テーブルに追加されるまで、新しいレコードを含む MS_SAMPLE_EMPLOYEE インターフェイス テーブルを再作成する必要がありますのでにポーリング メッセージを取得できません。 サンプルで提供される insert_apps_data.sql スクリプトを実行して行うことができます。 このスクリプトを実行した後、次のポーリング操作によって新しいレコードをテーブルに挿入がフェッチされます。  

## <a name="configuring-polling-in-the-wcf-service-model"></a>WCF サービス モデルでのポーリングの構成  
 使用してインターフェイス テーブルをポーリングする、 [!INCLUDE[adapteroraclebusinessshort](../../includes/adapteroraclebusinessshort-md.md)] WCF サービス モデルでは、する必要があります。  

- WCF サービス コントラクト (インターフェイス) を生成、**ポーリング**MS_SAMPLE_EMPLOYEE インターフェイス テーブルで操作します。 これを行うには、使用する可能性があります、[!INCLUDE[addadapterservrefshort](../../includes/addadapterservrefshort-md.md)]します。  

- このインターフェイスからの WCF サービスを実装します。  

- サービス ホストを使用してこの WCF サービス ホスト (**System.ServiceModel.ServiceHost**)。  

## <a name="about-the-examples-used-in-this-topic"></a>このトピックで使用する例について  
 このトピックの例では、MS_SAMPLE_EMPLOYEE インターフェイス テーブルをポーリングします。 テーブルを生成するスクリプトは、サンプルで提供されます。 サンプルの詳細については、[Oracle EBS アダプター用のサンプル](../../adapters-and-accelerators/adapter-oracle-ebs/samples-for-the-oracle-ebs-adapter.md)を参照してください。 サンプルについては、 **SelectPolling_ServiceModel**、これは、このトピックに基づいてがで提供されていることも、[!INCLUDE[adapteroraclebusinessshort](../../includes/adapteroraclebusinessshort-md.md)]サンプル。  

## <a name="the-wcf-service-contract-and-class"></a>WCF サービス コントラクトとクラス  
 使用することができます、 [!INCLUDE[addadapterservrefshort](../../includes/addadapterservrefshort-md.md)] WCF サービス コントラクト (インターフェイス) とサポートのクラスを作成する、**ポーリング**操作。 WCF サービス コントラクトを生成する詳細については、[WCF クライアントまたは Oracle E-business Suite ソリューションの成果物の WCF サービス コントラクトを生成](../../adapters-and-accelerators/adapter-oracle-ebs/create-a-wcf-client-or-wcf-service-contract-for-oracle-ebs-solution-artifacts.md)を参照してください。  

### <a name="the-wcf-service-contract-interface"></a>WCF サービス コントラクト (インターフェイス)  
 次のコードに対して生成された WCF サービス コントラクト (インターフェイス) を示しています、**ポーリング**MS_SAMPLE_EMPLOYEE インターフェイス テーブルに対する操作。  

```  
[System.CodeDom.Compiler.GeneratedCodeAttribute("System.ServiceModel", "3.0.0.0")]  
[System.ServiceModel.ServiceContractAttribute(Namespace="http://schemas.microsoft.com/OracleEBS/", ConfigurationName="InterfaceTables_FND_APPS_MS_SAMPLE_EMPLOYEE")]  
public interface InterfaceTables_FND_APPS_MS_SAMPLE_EMPLOYEE {  

    // CODEGEN: Generating message contract since the wrapper namespace (http://schemas.microsoft.com/OracleEBS/2008/05/InterfaceTables/FND/APPS/MS_SAMPLE_EMPLOYEE) of message Poll   
    // does not match the default value (http://schemas.microsoft.com/OracleEBS/)  
    [System.ServiceModel.OperationContractAttribute(IsOneWay=true, Action="InterfaceTables/Poll/FND/APPS/MS_SAMPLE_EMPLOYEE")]  
    void Poll(Poll request);  
}  
```  

### <a name="the-message-contracts"></a>メッセージ コントラクト  
 メッセージ コントラクトを次に、**ポーリング**MS_SAMPLE_EMPLOYEE インターフェイス テーブルに対する操作。  

```  
[System.Diagnostics.DebuggerStepThroughAttribute()]  
[System.CodeDom.Compiler.GeneratedCodeAttribute("System.ServiceModel", "3.0.0.0")]  
[System.ServiceModel.MessageContractAttribute(WrapperName="Poll", WrapperNamespace="http://schemas.microsoft.com/OracleEBS/2008/05/InterfaceTables/FND/APPS/MS_SAMPLE" +  
    "_EMPLOYEE", IsWrapped=true)]  
public partial class Poll {  

    [System.ServiceModel.MessageBodyMemberAttribute(Namespace="http://schemas.microsoft.com/OracleEBS/2008/05/InterfaceTables/FND/APPS/MS_SAMPLE" +  
        "_EMPLOYEE", Order=0)]  
    public schemas.microsoft.com.OracleEBS._2008._05.TableViewRecord.APPS.MS_SAMPLE_EMPLOYEE.SelectRecord[] DATA;  

    public Poll() {  
    }  

    public Poll(schemas.microsoft.com.OracleEBS._2008._05.TableViewRecord.APPS.MS_SAMPLE_EMPLOYEE.SelectRecord[] DATA) {  
        this.DATA = DATA;  
    }  
}  
```  

### <a name="wcf-service-class"></a>WCF サービス クラス  
 [!INCLUDE[addadapterservrefshort](../../includes/addadapterservrefshort-md.md)]をサービス コントラクト (インターフェイス) から実装された WCF サービス クラスのスタブを持つファイルも生成されます。 ファイルの名前は、OracleEBSBindingService.cs です。 処理するロジックを挿入することができます、**ポーリング**このクラスに直接操作します。 次のコードによって生成される WCF サービス クラスを示しています、[!INCLUDE[addadapterservrefshort](../../includes/addadapterservrefshort-md.md)]します。  

```  
namespace OracleEBSBindingNamespace {  

    public class OracleEBSBindingService : InterfaceTables_FND_APPS_MS_SAMPLE_EMPLOYEE {  

        // CODEGEN: Generating message contract since the wrapper namespace (http://schemas.microsoft.com/OracleEBS/2008/05/InterfaceTables/FND/APPS/MS_SAMPLE_EMPLOYEE) of message Poll   
        // does not match the default value (http://schemas.microsoft.com/OracleEBS/)  
        public virtual void Poll(Poll request) {  
            throw new System.NotImplementedException("The method or operation is not implemented.");  
        }  
    }  
}  
```  

## <a name="receiving-inbound-messages-for-the-poll-operation-using-a-select-statement"></a>SELECT ステートメントを使用して、ポーリング操作の受信メッセージの受信  
 このセクションを使用してポーリングの受信メッセージを受信する .NET アプリケーションを作成する方法の説明、[!INCLUDE[adapteroraclebusinessshort](../../includes/adapteroraclebusinessshort-md.md)]します。  

#### <a name="to-receive-polling-messages-using-a-select-statement"></a>SELECT ステートメントを使用してポーリング メッセージを受信するには  

1. 使用して、 [!INCLUDE[addadapterservrefshort](../../includes/addadapterservrefshort-md.md)] WCF サービス コントラクト (インターフェイス) とのヘルパー クラスを生成する、**ポーリング**MS_SAMPLE_EMPLOYEE インターフェイス テーブルで操作します。 詳細については、[WCF クライアントまたは Oracle E-business Suite ソリューションの成果物の WCF サービス コントラクトを生成](../../adapters-and-accelerators/adapter-oracle-ebs/create-a-wcf-client-or-wcf-service-contract-for-oracle-ebs-solution-artifacts.md)を参照してください。 必要に応じて、サービス コントラクトとヘルパー クラスを生成するときにバインドのプロパティを指定することができます。 これは、生成された構成ファイルで設定は正しくことを保証します。  

2. 手順 1. で生成されたインターフェイスとヘルパー クラスからの WCF サービスを実装します。 **ポーリング**から受信したデータの処理エラーが発生した場合、このクラスのメソッドは、ポーリング トランザクションを中止する例外をスローできます、**ポーリング**操作ですそれ以外の場合メソッドではありません。何も返されます。 次のように、WCF サービス クラスを属性する必要があります。  

   ```  
   [ServiceBehavior(InstanceContextMode = InstanceContextMode.Single)]  
   ```  

    内で、**ポーリング**メソッドを直接、アプリケーション ロジックを実装することができます。 このクラスは、OracleEBSBindingService.cs で確認できます。 この例では、このコードはサブ クラス、 **OracleEBSBindingService**クラス。 このコードでは、ポーリング メッセージは、受信され、コンソールに書き込まれます。  

   ```  
   [ServiceBehavior(InstanceContextMode = InstanceContextMode.Single)]  

   public class PollingService : OracleEBSBindingNamespace.OracleEBSBindingService  
   {  
       public override void Poll(Poll request)  
       {  
           Console.WriteLine("\nNew Polling Records Received");  
           Console.WriteLine("*************************************************");  
           Console.WriteLine("Emp No\tName\tDesignation\tSalary");  
           for (int i = 0; i < request.DATA.Length; i++)  
           {  
               Console.WriteLine("{0}\t{1}\t{2}\t{3}",  
               request.DATA[i].EMP_NO,  
               request.DATA[i].NAME,  
               request.DATA[i].DESIGNATION,  
               request.DATA[i].SALARY);  
           }  
           Console.WriteLine("*************************************************");  
           Console.WriteLine("\nHit <RETURN> to stop polling");  
       }  
   }  
   ```  

3. URI の一部として資格情報を渡すことを回避するために、次のクラスを実装する必要があります。 アプリケーションの後半部分の資格情報を渡すには、このクラスをインスタンス化されます。  

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

4. 作成、 **OracleEBSBinding**とバインドのプロパティを指定することで、ポーリング操作を構成します。 コードで明示的に、または構成で宣言的に、これを行うことができます。 指定する必要がありますには、少なくとも、 **InboundOperationType**、 **PolledDataAvailableStatement**、 **PollingInput**、および**PollingAction**プロパティをバインドします。  

   ```  
   OracleEBSBinding binding = new OracleEBSBinding();  
   binding.InboundOperationType = InboundOperation.Polling;  
   binding.PolledDataAvailableStatement = "SELECT COUNT (*) FROM MS_SAMPLE_EMPLOYEE";  
   binding.PollingInput = "SELECT * FROM MS_SAMPLE_EMPLOYEE FOR UPDATE";  
   binding.PollingAction = "InterfaceTables/Poll/FND/APPS/MS_SAMPLE_EMPLOYEE";  
   binding.PostPollStatement = "DELETE FROM MS_SAMPLE_EMPLOYEE";  
   ```  

5. インターフェイス テーブルをポーリングするため、アプリケーションのコンテキストを設定する必要もあります。 アプリケーションのコンテキストとアプリケーション コンテキストの設定に必要なバインドのプロパティの詳細については、[アプリケーション コンテキストの設定](../../adapters-and-accelerators/adapter-oracle-ebs/set-application-context.md)を参照してください。  

   ```  
   binding.OracleUserName = "myOracleEBSUserName";  
   binding.OraclePassword = "myOracleEBSPassword";  
   binding.OracleEBSResponsibilityName = "myOracleEBSResponsibility";  
   ```  

6. Oracle E-business Suite の資格情報を指定するには、インスタンス化する、 **PollingCredentials**手順 3 で作成したクラス。  

   ```  
   PollingCredentials credentials = new PollingCredentials();  
   credentials.UserName.UserName = "<Enter user name here>";  
   credentials.UserName.Password = "<Enter password here>";  
   ```  

7. 手順 2 で作成した WCF サービスのインスタンスを作成します。  

   ```  
   // create service instance  
   PollingService service = new PollingService();  
   ```  

8. インスタンスを作成**System.ServiceModel.ServiceHost** WCF サービスと基本の接続 URI を使用しています。 基本の接続 URI は、指定されている場合、受信の ID を含めることはできません。 また、資格情報をここで渡す必要があります。  

   ```  
   // Enable service host  
   Uri[] baseUri = new Uri[] { new Uri("oracleebs://ebs_instance_name") };  
   ServiceHost serviceHost = new ServiceHost(service, baseUri);  
   serviceHost.Description.Behaviors.Add(credentials);  

   ```  

9. サービス ホストにサービス エンドポイントを追加します。 これを行うには :  

   - 手順 4. で作成したバインドを使用します。  

   - 接続の資格情報を含む URI を指定し、必要に応じて、受信の id。  

   - MS_SAMPLE_EMPLOYEE インターフェイス テーブルをポーリングするには、"InterfaceTables_FND_APPS_MS_SAMPLE_EMPLOYEE"としてコントラクトを指定します。  

     ```  
     // Add service endpoint: be sure to specify InterfaceTables_FND_APPS_MS_SAMPLE_EMPLOYEE as the contract  
     Uri ConnectionUri = new Uri("oracleebs://ebs_instance_name");  
     serviceHost.AddServiceEndpoint("InterfaceTables_FND_APPS_MS_SAMPLE_EMPLOYEE", binding, ConnectionUri);  
     ```  

10. ポーリングのデータを受信するには、サービス ホストを開きます。 アダプターは、クエリが結果セットを返すたびにデータを返します。  

    ```  
    // Open the service host to begin polling  
    serviceHost.Open();  
    ```  

11. ポーリングを終了するには、サービス ホストを閉じます。  

    > [!IMPORTANT]
    >  アダプターは、サービス ホストが閉じられるまでポーリングを続行します。  

    ```  
    serviceHost.Close();  
    ```  

### <a name="example"></a>例  
 次の例では、MS_SAMPLE_EMPLOYEE インターフェイス テーブルをポーリングするポーリング アプリケーションを示します。 **PollingInput**プロパティには、MS_SAMPLE_EMPLOYEE テーブルからすべてのデータを読み取る select ステートメントが含まれているし、ポーリング後ステートメントは、同じテーブルからすべてのデータを削除します。 最初のポーリング メッセージは、MS_SAMPLE_EMPLOYEE インターフェイス テーブルからすべてのレコードを提供します。 ポーリング後ステートメント、レコードが削除されるため、後続のポーリング メッセージはレコードがありません。 多くのデータは MS_SAMPLE_EMPLOYEE インターフェイス テーブルに追加されるまで、すべてのメッセージのポーリングは利用できません。 そのため、新しいレコードを含む MS_SAMPLE_EMPLOYEE インターフェイス テーブルを再作成する必要があります。 サンプルで提供される insert_apps_data.sql スクリプトを実行して行うことができます。 このスクリプトを実行した後、次のポーリング操作によって新しいレコードをテーブルに挿入がフェッチされます。 アダプターのポーリングを押して、サービス ホストを終了するまでは引き続き`<RETURN>`します。  

```  
using System;  
using System.Collections.Generic;  
using System.Linq;  
using System.Text;  
using Microsoft.Adapters.OracleEBS;  
using Microsoft.ServiceModel.Channels;  
using System.ServiceModel;  
using System.ServiceModel.Description;  
using System.ServiceModel.Channels;  
using System.Collections.ObjectModel;  

namespace SelectPolling_ServiceModel  
{  
    [ServiceBehavior(InstanceContextMode = InstanceContextMode.Single)]  

    public class PollingService : OracleEBSBindingNamespace.OracleEBSBindingService  
    {  
        public override void Poll(Poll request)  
        {  
            Console.WriteLine("\nNew Polling Records Received");  
            Console.WriteLine("*************************************************");  
            Console.WriteLine("Emp No\tName\tDesignation\tSalary");  
            for (int i = 0; i < request.DATA.Length; i++)  
            {  
                Console.WriteLine("{0}\t{1}\t{2}\t{3}",  
                request.DATA[i].EMP_NO,  
                request.DATA[i].NAME,  
                request.DATA[i].DESIGNATION,  
                request.DATA[i].SALARY);  
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

                OracleEBSBinding binding = new OracleEBSBinding();  
                binding.InboundOperationType = InboundOperation.Polling;  
                binding.PolledDataAvailableStatement = "SELECT COUNT (*) FROM MS_SAMPLE_EMPLOYEE";  
                binding.PollingInput = "SELECT * FROM MS_SAMPLE_EMPLOYEE FOR UPDATE";  
                binding.PollingAction = "InterfaceTables/Poll/FND/APPS/MS_SAMPLE_EMPLOYEE";  
                binding.PostPollStatement = "DELETE FROM MS_SAMPLE_EMPLOYEE";  
                binding.OracleUserName = "myOracleEBSUserName";  
                binding.OraclePassword = "myOracleEBSPassword";  
                binding.OracleEBSResponsibilityName = "myOracleEBSResponsibility";  

                // This URI is used to specify the address for the ServiceEndpoint  
                // It must contain the InboundId that was used to generate  
                // the WCF service callback interface  
                Uri ConnectionUri = new Uri("oracleebs://ebs_instance_name");  

                // This URI is used to initialize the ServiceHost. It cannot contain  
                // an InboundID; otherwise,an exception is thrown when  
                // the ServiceHost is initialized.  
                Uri[] baseUri = new Uri[] { new Uri("oracleebs://ebs_instance_name") };  

                PollingCredentials credentials = new PollingCredentials();  
                credentials.UserName.UserName = "<Enter user name here>";  
                credentials.UserName.Password = "<Enter password here>";  

                Console.WriteLine("Opening service host...");  
                PollingService service = new PollingService();  
                serviceHost = new ServiceHost(service, baseUri);  
                serviceHost.Description.Behaviors.Add(credentials);  
                serviceHost.AddServiceEndpoint("InterfaceTables_FND_APPS_MS_SAMPLE_EMPLOYEE", binding, ConnectionUri);  
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
 [WCF サービス モデルを使用してポーリング Oracle E-business Suite](../../adapters-and-accelerators/adapter-oracle-ebs/poll-oracle-e-business-suite-using-the-wcf-service-model.md)