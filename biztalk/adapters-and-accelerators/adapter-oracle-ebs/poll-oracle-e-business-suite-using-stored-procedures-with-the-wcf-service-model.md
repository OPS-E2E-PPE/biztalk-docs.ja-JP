---
title: ストアド プロシージャを使用して WCF サービス モデルとポーリング Oracle E-business Suite |Microsoft Docs
ms.custom: ''
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: ''
ms.suite: ''
ms.tgt_pltfrm: ''
ms.topic: article
ms.assetid: 47dcb866-9161-4b28-9481-2761794ce805
caps.latest.revision: 7
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: c2d01bcfd2b004042ce69f4843bb9ae7bb2f323f
ms.sourcegitcommit: 266308ec5c6a9d8d80ff298ee6051b4843c5d626
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 06/27/2018
ms.locfileid: "37007411"
---
# <a name="poll-oracle-e-business-suite-using-stored-procedures-with-the-wcf-service-model"></a>ストアド プロシージャを使用して WCF サービス モデルとポーリング Oracle E-business Suite
構成することができます、 [!INCLUDE[adapteroraclebusinessshort](../../includes/adapteroraclebusinessshort-md.md)] Oracle データベースを定期的にポーリングするストアド プロシージャを使用して、定期的なデータ変更メッセージを受信します。 ストアド プロシージャは、Oracle データベースをポーリングするアダプターを定期的に実行するポーリング ステートメントとして指定できます。  

 ポーリングを有効にする、このトピックの説明に従って、特定のバインド プロパティの条件を指定する必要があります。  アダプターがポーリングをサポートする方法の詳細については、[受信呼び出しのポーリングを使用してサポート](../../adapters-and-accelerators/adapter-oracle-ebs/support-for-inbound-calls-using-polling.md)を参照してください。  

## <a name="configuring-a-polling-operation-with-oracle-e-business-adapter-binding-properties"></a>Oracle E-business アダプターのバインドのプロパティをポーリング操作を構成します。  
 次の表にまとめたものです、[!INCLUDE[adapteroraclebusinessshort](../../includes/adapteroraclebusinessshort-md.md)]バインドのプロパティのデータ変更メッセージを受信するアダプターを構成するために使用します。 ポーリング アプリケーションを実行中に、これらのバインドのプロパティを指定する必要があります。  


|         プロパティのバインド         |                                                                                                                                                                                                                                                                       説明                                                                                                                                                                                                                                                                       |
|----------------------------------|---------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------|
|     **InboundOperationType**     |                                                                                                                                                                                                                   実行するかどうかを指定します、**ポーリング**または**通知**操作を受信します。 既定値は**ポーリング**します。                                                                                                                                                                                                                    |
| **PolledDataAvailableStatement** |                                                                                                                                                       すべてのデータがポーリングに使用できるかどうかを判断するアダプターを実行する SQL ステートメントを指定します。 指定したストアド プロシージャのレコードを使用できる場合にのみ、 **PollingInput**プロパティのバインドが実行されます。                                                                                                                                                       |
|       **PollingInterval**        |                                           秒単位で間隔を指定、[!INCLUDE[adapteroraclebusinessshort](../../includes/adapteroraclebusinessshort-md.md)]に指定されたステートメントが実行される、 **PolledDataAvailableStatement**プロパティをバインドします。 既定値は 30 秒です。 ポーリング間隔は、連続するポーリングの間隔を決定します。 ステートメントは、指定した期間内で実行される、アダプターが間隔内の残りの時間の間スリープします。                                            |
|         **PollingInput**         | ポーリング ステートメントを指定します。 ストアド プロシージャを使用してポーリングする、このバインドのプロパティの全体の要求メッセージを指定する必要があります。 要求メッセージは、送信操作としてストアド プロシージャを呼び出すため、アダプターに送信すると、同じである必要があります。 既定値は null です。<br /><br /> 値を指定する必要があります**PollingInput**ポーリングを有効にするプロパティをバインドします。 ポーリング ステートメントの実行によって決定される、ポーリングに使用できるデータが場合にのみ、 **PolledDataAvailableStatement**プロパティをバインドします。 |
|        **PollingAction**         |                                                                                                                                                          ポーリング操作のアクションを指定します。 使用して、操作に対して生成されたサービスのインターフェイスからポーリング アクションを決定することができます、[!INCLUDE[addadapterservreflong](../../includes/addadapterservreflong-md.md)]します。                                                                                                                                                           |
|      **PostPollStatement**       |                                                                                                                                                                                                            指定されたステートメントの後に実行されるステートメント ブロックを指定します、 **PollingInput**プロパティのバインドを実行します。                                                                                                                                                                                                             |
|      **PollWhileDataFound**      |                                                                               指定するかどうか、[!INCLUDE[adapteroraclebusinessshort](../../includes/adapteroraclebusinessshort-md.md)]ポーリング間隔を無視し、継続的にデータがポーリングされるテーブルで使用できる場合に、ポーリング ステートメントを実行します。 テーブルのデータがない場合は、アダプターは、指定されたポーリング間隔でポーリング ステートメントを実行する元に戻します。 既定値は false です。                                                                               |

 これらのプロパティの詳細については、[Oracle E-business Suite バインド プロパティの BizTalk アダプターについて](../../adapters-and-accelerators/adapter-oracle-ebs/read-about-the-biztalk-adapter-for-oracle-e-business-suite-binding-properties.md)を参照してください。 使用する方法の詳細については、[!INCLUDE[adapteroraclebusinessshort](../../includes/adapteroraclebusinessshort-md.md)]をポーリングするには、次のセクションを参照しています。  

## <a name="how-this-topic-demonstrates-polling"></a>このトピックでポーリングしていますか  
 示すために、このトピックでどのように[!INCLUDE[adapteroraclebusinessshort](../../includes/adapteroraclebusinessshort-md.md)]データの変更、GET_ACTIVITYS を使用するストアド プロシージャを使用して、メッセージの受信をサポートには、Oracle データベースで ACCOUNTACTIVITY テーブルをポーリングするプロシージャが格納されています。 このストアド プロシージャは ACCOUNT_PKG パッケージで使用できます。 データベースでこれらのオブジェクトを作成するサンプルに付属の SQL スクリプトを実行することができます。  

> [!NOTE]
>  例では、このトピックでのポーリングに、ACCOUNTACTIVITY の表に、ベース データベース テーブルは、サンプルに付属のスクリプトを実行してこれを作成します。 インターフェイス テーブルなど、他のテーブルをポーリングするには、このトピックの説明に従って、同じような手順を実行する必要があります。  

 ポーリング操作を説明するために、次の項目行います。  

-   SELECT ステートメントを指定、 **PolledDataAvailableStatement**データがある、テーブルの中にポーリングされます (ACCOUNTACTIVITY) を決定するプロパティをバインドします。 この例では、としては、このバインド プロパティを設定できます。  

    ```  
    SELECT COUNT (*) FROM ACCOUNTACTIVITY  
    ```  

     これにより、ACCOUNTACTIVITY テーブルにいくつかのレコードがある場合にのみ、アダプターがポーリング ステートメントを実行します。  

-   一部として、要求メッセージを提供することで、GET_ACTIVITYS、ストアド プロシージャを実行、 **PollingInput**プロパティをバインドします。 このストアド プロシージャは ACCOUNTACTIVITY テーブル内のすべての行を取得し、アダプターから応答メッセージが表示されます。  

-   ブロックを実行する PL/SQL の一部として、 **PostPollStatement**プロパティをバインドします。 このステートメントは、ACCOUNTACTIVITY テーブルからのすべてのデータをデータベース内の別のテーブルに移動されます。 これは、次回後**PollingInput**が実行すると、それをフェッチできませんすべてのデータとその GET_ACTIVITYS ストアド プロシージャは空の応答メッセージを返します。  

-   多くのデータは ACCOUNTACTIVITY テーブルに追加されるまで新しいレコードを含む ACCOUNTACTIVITY テーブルを再作成する必要がありますので、空の応答メッセージを取得する続けます。 サンプルで提供される more_activity_data.sql スクリプトを実行して行うことができます。 このスクリプトを実行した後、次のポーリング操作によって新しいレコードをテーブルに挿入がフェッチされます。  

## <a name="configuring-polling-in-the-wcf-service-model"></a>WCF サービス モデルでのポーリングの構成  
 使用したストアド プロシージャを使用してポーリングする、 [!INCLUDE[adapteroraclebusinessshort](../../includes/adapteroraclebusinessshort-md.md)] WCF サービス モデルでは、する必要があります。  

- ポーリングするものを使用してストアド プロシージャの WCF サービス コントラクト (インターフェイス) を生成します。 この例での WCF サービス コントラクトを生成する必要があります、 **GET_ACTIVITYS**受信操作としてストアド プロシージャ。 これを行うには、使用する可能性があります、[!INCLUDE[addadapterservrefshort](../../includes/addadapterservrefshort-md.md)]します。  

- このインターフェイスからの WCF サービスを実装します。  

- サービス ホストを使用してこの WCF サービス ホスト (**System.ServiceModel.ServiceHost**)。  

## <a name="about-the-examples-used-in-this-topic"></a>このトピックで使用する例について  
 このトピックでのポーリング、GET_ACTIVITYS を使用して ACCOUNTACTIVITY データベース テーブルの例はストアド プロシージャです。 テーブルとストアド プロシージャを生成するスクリプトは、サンプルで提供されます。 サンプルの詳細については、[Oracle EBS アダプター用のサンプル](../../adapters-and-accelerators/adapter-oracle-ebs/samples-for-the-oracle-ebs-adapter.md)を参照してください。 サンプルについては、 **StoredProcPolling_ServiceModel**、これは、このトピックに基づいてがで提供されていることも、[!INCLUDE[adapteroraclebusinessshort](../../includes/adapteroraclebusinessshort-md.md)]サンプル。  

## <a name="the-wcf-service-contract-and-class"></a>WCF サービス コントラクトとクラス  
 使用することができます、 [!INCLUDE[addadapterservrefshort](../../includes/addadapterservrefshort-md.md)] WCF サービス コントラクト (インターフェイス) とサポートのクラスを作成する、 **GET_ACTIVITYS**操作を受信します。 WCF サービス コントラクトを生成する詳細については、[WCF クライアントまたは Oracle E-business Suite ソリューションの成果物の WCF サービス コントラクトを生成](../../adapters-and-accelerators/adapter-oracle-ebs/create-a-wcf-client-or-wcf-service-contract-for-oracle-ebs-solution-artifacts.md)を参照してください。  

### <a name="the-wcf-service-contract-interface"></a>WCF サービス コントラクト (インターフェイス)  
 次のコードに対して生成された WCF サービス コントラクト (インターフェイス) を示しています、 **GET_ACTIVITYS**操作を受信します。  

```  
[System.CodeDom.Compiler.GeneratedCodeAttribute("System.ServiceModel", "3.0.0.0")]  
[System.ServiceModel.ServiceContractAttribute(Namespace="http://schemas.microsoft.com/OracleEBS/", ConfigurationName="PollingPackageApis_APPS_ACCOUNT_PKG")]  
public interface PollingPackageApis_APPS_ACCOUNT_PKG {  

    // CODEGEN: Generating message contract since the wrapper namespace (http://schemas.microsoft.com/OracleEBS/2008/05/PollingPackageApis/APPS/ACCOUNT_PKG) of message GET_ACTIVITYS   
    // does not match the default value (http://schemas.microsoft.com/OracleEBS/)  
    [System.ServiceModel.OperationContractAttribute(IsOneWay=true, Action="PollingPackageApis/APPS/ACCOUNT_PKG/GET_ACTIVITYS")]  
    void GET_ACTIVITYS(GET_ACTIVITYS request);  
}  
```  

### <a name="the-message-contracts"></a>メッセージ コントラクト  
 メッセージ コントラクトを次に、 **GET_ACTIVITYS**操作を受信します。  

```  
[System.Diagnostics.DebuggerStepThroughAttribute()]  
[System.CodeDom.Compiler.GeneratedCodeAttribute("System.ServiceModel", "3.0.0.0")]  
[System.ServiceModel.MessageContractAttribute(WrapperName="GET_ACTIVITYS", WrapperNamespace="http://schemas.microsoft.com/OracleEBS/2008/05/PollingPackageApis/APPS/ACCOUNT_PK" +  
    "G", IsWrapped=true)]  
public partial class GET_ACTIVITYS {  

    [System.ServiceModel.MessageBodyMemberAttribute(Namespace="http://schemas.microsoft.com/OracleEBS/2008/05/PollingPackageApis/APPS/ACCOUNT_PK" +  
        "G", Order=0)]  
    public schemas.microsoft.com.OracleEBS._2008._05.RecordTypes.APPS.ACCOUNT_PKG.GET_ACTIVITYS.OUTRECSRecord[] OUTRECS;  

    public GET_ACTIVITYS() {  
    }  

    public GET_ACTIVITYS(schemas.microsoft.com.OracleEBS._2008._05.RecordTypes.APPS.ACCOUNT_PKG.GET_ACTIVITYS.OUTRECSRecord[] OUTRECS) {  
        this.OUTRECS = OUTRECS;  
    }  
}  
```  

### <a name="wcf-service-class"></a>WCF サービス クラス  
 [!INCLUDE[addadapterservrefshort](../../includes/addadapterservrefshort-md.md)]をサービス コントラクト (インターフェイス) から実装された WCF サービス クラスのスタブを持つファイルも生成されます。 ファイルの名前は、OracleEBSBindingService.cs です。 処理するロジックを挿入することができます、 **GET_ACTIVITYS**このクラスに直接操作します。 次のコードによって生成される WCF サービス クラスを示しています、[!INCLUDE[addadapterservrefshort](../../includes/addadapterservrefshort-md.md)]します。  

```  
namespace OracleEBSBindingNamespace {  

    public class OracleEBSBindingService : PollingPackageApis_APPS_ACCOUNT_PKG {  

        // CODEGEN: Generating message contract since the wrapper namespace (http://schemas.microsoft.com/OracleEBS/2008/05/PollingPackageApis/APPS/ACCOUNT_PKG) of message GET_ACTIVITYS   
        // does not match the default value (http://schemas.microsoft.com/OracleEBS/)  
        public virtual void GET_ACTIVITYS(GET_ACTIVITYS request) {  
            throw new System.NotImplementedException("The method or operation is not implemented.");  
        }  
    }  
}  
```  

## <a name="receiving-inbound-messages-for-polling-using-a-stored-procedure"></a>ストアド プロシージャを使用してポーリングの受信メッセージの受信  
 このセクションを使用してポーリングの受信メッセージを受信する .NET アプリケーションを作成する方法の説明、[!INCLUDE[adapteroraclebusinessshort](../../includes/adapteroraclebusinessshort-md.md)]します。  

#### <a name="to-receive-polling-messages-using-a-stored-procedure"></a>ストアド プロシージャを使用してポーリング メッセージを受信するには  

1. 使用して、 [!INCLUDE[addadapterservrefshort](../../includes/addadapterservrefshort-md.md)] WCF サービス コントラクト (インターフェイス) とのヘルパー クラスを生成する、 **GET_ACTIVITYS**操作を受信します。 詳細については、[WCF クライアントまたは Oracle E-business Suite ソリューションの成果物の WCF サービス コントラクトを生成](../../adapters-and-accelerators/adapter-oracle-ebs/create-a-wcf-client-or-wcf-service-contract-for-oracle-ebs-solution-artifacts.md)を参照してください。 必要に応じて、サービス コントラクトとヘルパー クラスを生成するときにバインドのプロパティを指定することができます。 これは、生成された構成ファイルで設定は正しくことを保証します。  

2. 手順 1. で生成されたインターフェイスとヘルパー クラスからの WCF サービスを実装します。 **GET_ACTIVITYS**から受信したデータの処理エラーが発生した場合、このクラスのメソッドは、ポーリング トランザクションを中止する例外をスローできます、 **GET_ACTIVITYS**操作です。メソッドは何も返しません。 次のように、WCF サービス クラスを属性する必要があります。  

   ```  
   [ServiceBehavior(InstanceContextMode = InstanceContextMode.Single)]  
   ```  

    内で、 **GET_ACTIVITYS**メソッドを直接、アプリケーション ロジックを実装することができます。 このクラスは、OracleEBSBindingService.cs で確認できます。 この例では、このコードはサブ クラス、 **OracleEBSBindingService**クラス。 このコードでは、ポーリング メッセージは、受信され、コンソールに書き込まれます。  

   ```  
   [ServiceBehavior(InstanceContextMode = InstanceContextMode.Single)]  

   public class PollingService : OracleEBSBindingNamespace.OracleEBSBindingService  
   {  
       public override void  GET_ACTIVITYS(GET_ACTIVITYS request)  
       {  
           Console.WriteLine("\nNew Polling Records Received");  
           Console.WriteLine("*************************************************");  
           Console.WriteLine("Tx Id\tAccount\tAmount\tProcessed");  
           for (int i = 0; i < request.OUTRECS.Length; i++)  
           {  
               Console.WriteLine("{0}\t{1}\t{2}\t{3}",  
               request.OUTRECS[i].TID,  
               request.OUTRECS[i].ACCOUNT,  
               request.OUTRECS[i].AMOUNT,  
               request.OUTRECS[i].PROCESSED);  
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
   binding.PolledDataAvailableStatement = "SELECT COUNT (*) FROM ACCOUNTACTIVITY";  
   binding.PollingInput = "<GET_ACTIVITYS xmlns='http://schemas.microsoft.com/OracleEBS/2008/05/PackageApis/APPS/ACCOUNT_PKG'><INRECS>OPEN ? FOR SELECT * FROM ACCOUNTACTIVITY</INRECS></GET_ACTIVITYS>";  
   binding.PollingAction = "PollingPackageApis/APPS/ACCOUNT_PKG/GET_ACTIVITYS";  
   binding.PostPollStatement = "BEGIN ACCOUNT_PKG.PROCESS_ACTIVITY(); END;";  
   ```  

   > [!NOTE]
   >  注意の値、 **PollingInput**を呼び出すための要求メッセージにはプロパティのバインドが含まれています、 **GET_ACTIVITYS**送信操作としてストアド プロシージャ。  

   > [!IMPORTANT]
   >  この例ではデータベース テーブルをポーリングするため必要はありませんアプリケーション コンテキストを設定します。 ただし場合は、インターフェイス テーブルをポーリングする必要がありますコンテキストを設定するアプリケーションを指定して、 **OracleUserName**、 **OraclePassword**、および**OracleEBSResponsibilityName**プロパティをバインドします。 アプリケーションのコンテキストの詳細については、[アプリケーション コンテキストの設定](../../adapters-and-accelerators/adapter-oracle-ebs/set-application-context.md)を参照してください。  

5. Oracle E-business Suite の資格情報を指定するには、インスタンス化する、 **PollingCredentials**手順 3 で作成したクラス。  

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

7. インスタンスを作成**System.ServiceModel.ServiceHost** WCF サービスと基本の接続 URI を使用しています。 基本の接続 URI は、指定されている場合、受信の ID を含めることはできません。 また、資格情報をここで渡す必要があります。  

   ```  
   // Enable service host  
   Uri[] baseUri = new Uri[] { new Uri("oracleebs://ebs_instance_name") };  
   ServiceHost serviceHost = new ServiceHost(service, baseUri);  
   serviceHost.Description.Behaviors.Add(credentials);  

   ```  

8. サービス ホストにサービス エンドポイントを追加します。 これを行うには :  

   -   手順 4. で作成したバインドを使用します。  

   -   接続の資格情報を含む URI を指定し、必要に応じて、受信の id。  

   -   MS_SAMPLE_EMPLOYEE インターフェイス テーブルをポーリングするには、"PollingPackageApis_APPS_ACCOUNT_PKG"としてコントラクトを指定します。  

   ```  
   // Add service endpoint: be sure to specify PollingPackageApis_APPS_ACCOUNT_PKG as the contract  
   Uri ConnectionUri = new Uri("oracleebs://ebs_instance_name");  
   serviceHost.AddServiceEndpoint("PollingPackageApis_APPS_ACCOUNT_PKG", binding, ConnectionUri);  
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
 次の例では、使用、GET_ACTIVITYS ACCOUNTACTIVITY データベース テーブルをポーリングするポーリング アプリケーション ストアド プロシージャを示します。 **PollingInput** ACCOUNTACTIVITY テーブルからすべてのデータを読み取る GET_ACTIVITYS ストアド プロシージャを呼び出す要求メッセージを含むプロパティのバインドと、ポーリング後ステートメントは、ACCOUNTACTIVITY からすべてのデータを移動しますACTIVITYHISTORY テーブル。  

 最初のポーリング メッセージは、ACCOUNTACTIVITY テーブルからすべてのレコードを提供します。 ポーリング後ステートメント、レコードが削除されるため、後続のポーリング メッセージはレコードがありません。 多くのデータは ACCOUNTACTIVITY テーブルに追加されるまで、新しいレコードを含む ACCOUNTACTIVITY テーブルを再作成する必要がありますのでにポーリング メッセージを取得できません。 サンプルで提供される more_activity_data.sql スクリプトを実行して行うことができます。  

 このスクリプトを実行した後、次のポーリング操作によって新しいレコードをテーブルに挿入がフェッチされます。 アダプターのポーリングを押して、サービス ホストを終了するまでは引き続き`<RETURN>`します。  

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

namespace StoredProcPolling_ServiceModel  
{  
    [ServiceBehavior(InstanceContextMode = InstanceContextMode.Single)]  

    public class PollingService : OracleEBSBindingNamespace.OracleEBSBindingService  
    {  
        public override void  GET_ACTIVITYS(GET_ACTIVITYS request)  
        {  
            Console.WriteLine("\nNew Polling Records Received");  
            Console.WriteLine("*************************************************");  
            Console.WriteLine("Tx Id\tAccount\tAmount\tProcessed");  
            for (int i = 0; i < request.OUTRECS.Length; i++)  
            {  
                Console.WriteLine("{0}\t{1}\t{2}\t{3}",  
                request.OUTRECS[i].TID,  
                request.OUTRECS[i].ACCOUNT,  
                request.OUTRECS[i].AMOUNT,  
                request.OUTRECS[i].PROCESSED);  
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
                binding.PolledDataAvailableStatement = "SELECT COUNT (*) FROM ACCOUNTACTIVITY";  
                binding.PollingInput = "<GET_ACTIVITYS xmlns='http://schemas.microsoft.com/OracleEBS/2008/05/PackageApis/APPS/ACCOUNT_PKG'><INRECS>OPEN ? FOR SELECT * FROM ACCOUNTACTIVITY</INRECS></GET_ACTIVITYS>";  
                binding.PollingAction = "PollingPackageApis/APPS/ACCOUNT_PKG/GET_ACTIVITYS";  
                binding.PostPollStatement = "BEGIN ACCOUNT_PKG.PROCESS_ACTIVITY(); END;";  

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
                serviceHost.AddServiceEndpoint("PollingPackageApis_APPS_ACCOUNT_PKG", binding, ConnectionUri);  
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