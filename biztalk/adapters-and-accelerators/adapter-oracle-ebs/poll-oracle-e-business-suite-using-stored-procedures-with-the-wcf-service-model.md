---
title: "WCF サービス モデルでストアド プロシージャを使用してポーリング Oracle E-business Suite |Microsoft ドキュメント"
ms.custom: 
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: 
ms.suite: 
ms.tgt_pltfrm: 
ms.topic: article
ms.assetid: 47dcb866-9161-4b28-9481-2761794ce805
caps.latest.revision: "7"
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: e27c6bc1c0d8578bc99e5e8665556cb69cc2f819
ms.sourcegitcommit: cb908c540d8f1a692d01dc8f313e16cb4b4e696d
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 09/20/2017
---
# <a name="poll-oracle-e-business-suite-using-stored-procedures-with-the-wcf-service-model"></a>WCF サービス モデルでストアド プロシージャを使用してポーリング Oracle E-business Suite
構成することができます、 [!INCLUDE[adapteroraclebusinessshort](../../includes/adapteroraclebusinessshort-md.md)] Oracle データベースを定期的にポーリングするストアド プロシージャを使用して、定期的なデータの変更メッセージを受信します。 ストアド プロシージャは、アダプターが Oracle データベースをポーリングする定期的に実行されるポーリング ステートメントとして指定できます。  
  
 ポーリングを有効にするには、このトピックの説明に従って、特定のバインディング プロパティの条件を指定する必要があります。  アダプターがポーリングをサポートする方法の詳細については、次を参照してください。[呼び出しをポーリングを使用して受信するためのサポート](../../adapters-and-accelerators/adapter-oracle-ebs/support-for-inbound-calls-using-polling.md)です。  
  
## <a name="configuring-a-polling-operation-with-oracle-e-business-adapter-binding-properties"></a>Oracle E-business アダプターのバインドのプロパティをポーリング操作を構成します。  
 次の表、[!INCLUDE[adapteroraclebusinessshort](../../includes/adapteroraclebusinessshort-md.md)]バインドのプロパティ データの変更メッセージを受信するアダプターを構成するために使用します。 これらのバインディング プロパティを指定すると、ポーリング アプリケーションの実行中にあります。  
  
|プロパティのバインド|Description|  
|----------------------|-----------------|  
|**InboundOperationType**|実行するかどうかを指定します、**ポーリング**または**通知**操作を受信します。 既定値は**ポーリング**です。|  
|**PolledDataAvailableStatement**|すべてのデータがポーリングに使用できるかどうかを判断するアダプターを実行する SQL ステートメントを指定します。 レコードがある場合にのみ、ストアド プロシージャに指定した、 **PollingInput**プロパティのバインドが実行されます。|  
|**PollingInterval**|秒単位で間隔を指定、[!INCLUDE[adapteroraclebusinessshort](../../includes/adapteroraclebusinessshort-md.md)]の指定されたステートメントの実行、 **PolledDataAvailableStatement**プロパティをバインドします。 既定値は 30 秒です。 ポーリング間隔では、連続するポーリングの間隔を決定します。 ステートメントは、指定した期間内で実行される、アダプター休止状態に入ります残り時間の間隔。|  
|**PollingInput**|ポーリング ステートメントを指定します。 ポーリングのストアド プロシージャを使用するには、要求メッセージ全体をこのバインドのプロパティを指定する必要があります。 要求メッセージは、送信操作として、ストアド プロシージャを呼び出すため、アダプターに送信すると、同じである必要があります。 既定値は null です。<br /><br /> 値を指定する必要があります**PollingInput**ポーリングを有効にするプロパティをバインドします。 ポーリング ステートメントの実行によって決定される、ポーリングに使用できるデータが場合にのみ、 **PolledDataAvailableStatement**プロパティをバインドします。|  
|**PollingAction**|ポーリング操作のアクションを指定します。 使用して、操作の生成、サービス インターフェイスからのポーリング動作を指定できます、[!INCLUDE[addadapterservreflong](../../includes/addadapterservreflong-md.md)]です。|  
|**PostPollStatement**|指定されたステートメントの後に実行されるステートメント ブロックを指定します、 **PollingInput**プロパティのバインドを実行します。|  
|**PollWhileDataFound**|指定するかどうか、[!INCLUDE[adapteroraclebusinessshort](../../includes/adapteroraclebusinessshort-md.md)]ポーリング間隔を無視し、継続的にデータで使用できる場合、テーブルをポーリングするポーリング ステートメントを実行します。 テーブルのデータがない場合は、アダプターは、指定されたポーリング間隔でポーリング ステートメントを実行する元に戻します。 既定値は false です。|  
  
 これらのプロパティの詳細については、次を参照してください。 [Oracle E-business Suite バインド プロパティの BizTalk アダプターの説明を読む](../../adapters-and-accelerators/adapter-oracle-ebs/read-about-the-biztalk-adapter-for-oracle-e-business-suite-binding-properties.md)です。 使用する方法の詳細については、[!INCLUDE[adapteroraclebusinessshort](../../includes/adapteroraclebusinessshort-md.md)]をポーリングするには、次のセクションを参照します。  
  
## <a name="how-this-topic-demonstrates-polling"></a>このトピックの内容がポーリングを示しています  
 このトピックの内容を示すため方法、[!INCLUDE[adapteroraclebusinessshort](../../includes/adapteroraclebusinessshort-md.md)]データの変更、GET_ACTIVITYS を使用するストアド プロシージャを使用して、メッセージの受信をサポートには、Oracle データベースで ACCOUNTACTIVITY テーブルをポーリングするプロシージャが格納されています。 このストアド プロシージャは ACCOUNT_PKG パッケージで使用できます。 データベースでこれらのオブジェクトを作成するサンプルに用意されている SQL スクリプトを実行することができます。  
  
> [!NOTE]
>  このトピックのポーリングで、ACCOUNTACTIVITY の表に、これはベース データベース テーブルによって作成されたサンプルに用意されているスクリプトを実行する例です。 インターフェイス テーブルなど、他のテーブルをポーリングするには、このトピックの説明に従って、同様の手順を実行する必要があります。  
  
 ポーリング操作を示すためは、次を操作します。  
  
-   SELECT ステートメントを指定、 **PolledDataAvailableStatement**データがある場所のテーブルでポーリング (ACCOUNTACTIVITY) を決定するプロパティをバインドします。 この例では、このバインディングのプロパティとしてを設定できます。  
  
    ```  
    SELECT COUNT (*) FROM ACCOUNTACTIVITY  
    ```  
  
     これにより、ACCOUNTACTIVITY テーブルにレコードの一部がある場合にのみ、アダプターが、ポーリング ステートメントを実行します。  
  
-   一部として要求メッセージを提供することによって、GET_ACTIVITYS、ストアド プロシージャの実行、 **PollingInput**プロパティをバインドします。 このストアド プロシージャは ACCOUNTACTIVITY テーブル内のすべての行を取得し、アダプターから応答メッセージが表示されます。  
  
-   一部としての PL/SQL ブロックの実行、 **PostPollStatement**プロパティをバインドします。 このステートメントは、データベース内の別のテーブルに ACCOUNTACTIVITY テーブルからすべてのデータが移動されます。 これは、次回後**PollingInput**が実行すると、それはフェッチできませんすべてのデータとため GET_ACTIVITYS ストアド プロシージャは空の応答メッセージを返します。  
  
-   多くのデータは ACCOUNTACTIVITY テーブルに追加するまでは引き続き新しいレコードを含む ACCOUNTACTIVITY テーブルを再作成する必要がありますので、空の応答メッセージを取得します。 サンプルに用意されている more_activity_data.sql スクリプトを実行して、これを行うことができます。 このスクリプトを実行した後、次のポーリング操作によって新しいレコードをテーブルに挿入がフェッチされます。  
  
## <a name="configuring-polling-in-the-wcf-service-model"></a>WCF サービス モデルでのポーリングを構成します。  
 ポーリングを持つストアド プロシージャを使用して、[!INCLUDE[adapteroraclebusinessshort](../../includes/adapteroraclebusinessshort-md.md)]モデルでは、WCF サービス、行う必要があります。  
  
-   ポーリングすることにこれを使用して、ストアド プロシージャの WCF サービス コントラクト (インターフェイス) を生成します。 この例では、WCF サービス コントラクトを生成する必要があります、 **GET_ACTIVITYS**ストアド プロシージャとして、受信操作になります。 これを行うには、使用して、[!INCLUDE[addadapterservrefshort](../../includes/addadapterservrefshort-md.md)]です。  
  
-   このインターフェイスから WCF サービスを実装します。  
  
-   サービス ホストを使用してこの WCF サービスをホスト (**System.ServiceModel.ServiceHost**)。  
  
## <a name="about-the-examples-used-in-this-topic"></a>このトピックで使用する例について  
 このトピックのポーリング、GET_ACTIVITYS を使用した ACCOUNTACTIVITY データベース テーブルの例はストアド プロシージャです。 テーブルおよびストアド プロシージャを生成するスクリプトは、サンプルの値が提供されます。 サンプルの詳細については、次を参照してください。 [Oracle EBS アダプター用のサンプル](../../adapters-and-accelerators/adapter-oracle-ebs/samples-for-the-oracle-ebs-adapter.md)です。 サンプルは、 **StoredProcPolling_ServiceModel**、これは、このトピックの内容に基づいても付属、[!INCLUDE[adapteroraclebusinessshort](../../includes/adapteroraclebusinessshort-md.md)]サンプルです。  
  
## <a name="the-wcf-service-contract-and-class"></a>WCF サービス コントラクトとクラス  
 使用することができます、 [!INCLUDE[addadapterservrefshort](../../includes/addadapterservrefshort-md.md)] WCF サービス コントラクト (インターフェイス) およびサポートするためのクラスを作成する、 **GET_ACTIVITYS**操作を受信します。 詳細については、WCF サービス コントラクトを生成する、次を参照してください。 [WCF クライアントまたは Oracle E-business Suite ソリューションの成果物のための WCF サービス コントラクトを生成](../../adapters-and-accelerators/adapter-oracle-ebs/create-a-wcf-client-or-wcf-service-contract-for-oracle-ebs-solution-artifacts.md)です。  
  
### <a name="the-wcf-service-contract-interface"></a>WCF サービス コントラクト (インターフェイス)  
 次のコードに対して生成される WCF サービス コントラクト (インターフェイス) を示しています、 **GET_ACTIVITYS**操作を受信します。  
  
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
 次に、メッセージ コントラクトを**GET_ACTIVITYS**操作を受信します。  
  
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
 [!INCLUDE[addadapterservrefshort](../../includes/addadapterservrefshort-md.md)]をサービス コントラクト (インターフェイス) から実装、WCF サービス クラスのスタブを持つファイルも生成します。 ファイルの名前は、OracleEBSBindingService.cs です。 処理するロジックを挿入することができます、 **GET_ACTIVITYS**このクラスに直接操作します。 次のコードによって生成された WCF サービス クラスを示しています、[!INCLUDE[addadapterservrefshort](../../includes/addadapterservrefshort-md.md)]です。  
  
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
 このセクションの内容を使用してポーリングの受信メッセージを受信する .NET アプリケーションを記述する方法の手順を説明する、[!INCLUDE[adapteroraclebusinessshort](../../includes/adapteroraclebusinessshort-md.md)]です。  
  
#### <a name="to-receive-polling-messages-using-a-stored-procedure"></a>ストアド プロシージャを使用してポーリング メッセージを受信するには  
  
1.  使用して、 [!INCLUDE[addadapterservrefshort](../../includes/addadapterservrefshort-md.md)] WCF サービス コントラクト (インターフェイス) およびためのヘルパー クラスを生成する、 **GET_ACTIVITYS**操作を受信します。 詳細については、次を参照してください。 [WCF クライアントまたは Oracle E-business Suite ソリューションの成果物のための WCF サービス コントラクトを生成](../../adapters-and-accelerators/adapter-oracle-ebs/create-a-wcf-client-or-wcf-service-contract-for-oracle-ebs-solution-artifacts.md)です。 サービス コントラクトとヘルパー クラスを生成するときに、必要に応じてバインドのプロパティを指定することができます。 これは、生成された構成ファイルで正しく設定されていることを保証します。  
  
2.  手順 1. で生成されたインターフェイスとヘルパー クラスからの WCF サービスを実装します。 **GET_ACTIVITYS**から受信したデータの処理エラーが発生した場合、このクラスのメソッドは、ポーリング トランザクションが中止例外をスローできます、 **GET_ACTIVITYS**操作以外の場合メソッドは何も返しません。 次のように、WCF サービス クラスを属性する必要があります。  
  
    ```  
    [ServiceBehavior(InstanceContextMode = InstanceContextMode.Single)]  
    ```  
  
     内で、 **GET_ACTIVITYS**メソッドを直接、アプリケーション ロジックを実装することができます。 このクラスは、OracleEBSBindingService.cs で確認できます。 この例では、このコードはサブ クラス、 **OracleEBSBindingService**クラスです。 このコードでポーリング メッセージを受信、コンソールに書き込まれます。  
  
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
  
3.  URI の一部として資格情報を渡すを防ぐ次のクラスを実装する必要があります。 アプリケーションの後半では、資格情報を渡すには、このクラスがインスタンス化されします。  
  
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
  
4.  作成、 **OracleEBSBinding**とバインドのプロパティを指定することによって、ポーリング操作を構成します。 これは、コードで明示的にまたは構成で宣言によって行うことができます。 指定する必要がありますには、少なくとも、 **InboundOperationType**、 **PolledDataAvailableStatement**、 **PollingInput**、および**PollingAction**プロパティをバインドします。  
  
    ```  
    OracleEBSBinding binding = new OracleEBSBinding();  
    binding.InboundOperationType = InboundOperation.Polling;  
    binding.PolledDataAvailableStatement = "SELECT COUNT (*) FROM ACCOUNTACTIVITY";  
    binding.PollingInput = "\<GET_ACTIVITYS xmlns='http://schemas.microsoft.com/OracleEBS/2008/05/PackageApis/APPS/ACCOUNT_PKG'><INRECS>OPEN ? FOR SELECT * FROM ACCOUNTACTIVITY</INRECS></GET_ACTIVITYS>";  
    binding.PollingAction = "PollingPackageApis/APPS/ACCOUNT_PKG/GET_ACTIVITYS";  
    binding.PostPollStatement = "BEGIN ACCOUNT_PKG.PROCESS_ACTIVITY(); END;";  
    ```  
  
    > [!NOTE]
    >  注意してくださいの値、 **PollingInput**を呼び出すための要求メッセージにはプロパティのバインドが含まれています、 **GET_ACTIVITYS**ストアド プロシージャとして送信操作です。  
  
    > [!IMPORTANT]
    >  この例では、データベース テーブルをポーリングするためする必要はありませんアプリケーション コンテキストを設定します。 ただし場合は、インターフェイス テーブルがポーリングする必要がありますコンテキストを設定するアプリケーションを指定して、 **OracleUserName**、 **OraclePassword**、および**OracleEBSResponsibilityName**プロパティをバインドします。 アプリケーション コンテキストの詳細については、次を参照してください。[アプリケーション コンテキストの設定](../../adapters-and-accelerators/adapter-oracle-ebs/set-application-context.md)です。  
  
5.  Oracle E-business Suite の資格情報を指定するには、インスタンス化する、 **PollingCredentials**手順 3. で作成したクラスです。  
  
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
  
7.  インスタンスを作成する**System.ServiceModel.ServiceHost** WCF サービスと基本接続 URI を使用しています。 基本の接続 URI は、指定されている場合、受信の ID を含めることはできません。 資格情報を次に渡す必要があります。  
  
    ```  
    // Enable service host  
    Uri[] baseUri = new Uri[] { new Uri("oracleebs://ebs_instance_name") };  
    ServiceHost serviceHost = new ServiceHost(service, baseUri);  
    serviceHost.Description.Behaviors.Add(credentials);  
  
    ```  
  
8.  サービス ホストにサービス エンドポイントを追加します。 これを行うには :  
  
    -   手順 4. で作成したバインディングを使用します。  
  
    -   接続の資格情報を含む URI を指定し、必要に応じて、入力方向の id。  
  
    -   MS_SAMPLE_EMPLOYEE インターフェイス テーブルをポーリングするには、"PollingPackageApis_APPS_ACCOUNT_PKG"としてコントラクトを指定します。  
  
    ```  
    // Add service endpoint: be sure to specify PollingPackageApis_APPS_ACCOUNT_PKG as the contract  
    Uri ConnectionUri = new Uri("oracleebs://ebs_instance_name");  
    serviceHost.AddServiceEndpoint("PollingPackageApis_APPS_ACCOUNT_PKG", binding, ConnectionUri);  
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
 次の例では、ストアド プロシージャを使用して、GET_ACTIVITYS ACCOUNTACTIVITY データベース テーブルをポーリングするポーリング アプリケーションを示します。 **PollingInput** ACCOUNTACTIVITY テーブルからすべてのデータを読み取る GET_ACTIVITYS ストアド プロシージャを呼び出す要求メッセージにはプロパティのバインドが含まれており、ポーリング後ステートメント ACCOUNTACTIVITY からすべてのデータを移動します。ACTIVITYHISTORY テーブル。  
  
 ポーリングの最初のメッセージは、ACCOUNTACTIVITY テーブルからすべてのレコードを示します。 ポーリング後ステートメントは、レコードを削除するため、後続のポーリング メッセージはレコードがありません。 多くのデータは、ACCOUNTACTIVITY テーブルに追加される、まで、新しいレコードを含む ACCOUNTACTIVITY テーブルを再作成する必要がありますのでにポーリング メッセージを取得できません。 サンプルに用意されている more_activity_data.sql スクリプトを実行して、これを行うことができます。  
  
 このスクリプトを実行した後、次のポーリング操作によって新しいレコードをテーブルに挿入がフェッチされます。 アダプターはポーリングを押して、サービス ホストを終了するまで引き続き`<RETURN>`します。  
  
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
                binding.PollingInput = "\<GET_ACTIVITYS xmlns='http://schemas.microsoft.com/OracleEBS/2008/05/PackageApis/APPS/ACCOUNT_PKG'><INRECS>OPEN ? FOR SELECT * FROM ACCOUNTACTIVITY</INRECS></GET_ACTIVITYS>";  
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