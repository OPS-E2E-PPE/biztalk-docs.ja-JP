---
title: WCF サービス モデルを使用して Oracle データベースでのポーリングに基づいたデータ変更メッセージの受信 |Microsoft Docs
ms.custom: ''
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: ''
ms.suite: ''
ms.tgt_pltfrm: ''
ms.topic: article
helpviewer_keywords:
- WCF service model, receiving polling-based messages
- how to, receive polling-based message
- polling-based messages, receiving by using the WCF service model
ms.assetid: 0324e8bf-d9d1-46f5-b896-b9fc8e61d514
caps.latest.revision: 7
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: cda98a1600df28fab476114e697cd47e24316251
ms.sourcegitcommit: 266308ec5c6a9d8d80ff298ee6051b4843c5d626
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 06/27/2018
ms.locfileid: "37012603"
---
# <a name="receive-polling-based-data-changed-messages-in-oracle-database-using-the-wcf-service-model"></a>WCF サービス モデルを使用して Oracle データベースでのポーリングに基づいたデータ変更メッセージを受信します。
構成することができます、[!INCLUDE[adapteroracle](../../includes/adapteroracle-md.md)]ポーリング ベースのデータを受信するには、Oracle のテーブルまたはビューに対するメッセージを変更します。 データ変更メッセージを受信するには、定期的に、アダプターが Oracle のテーブルまたはビューにオプションの PL/SQL コード ブロックを続けるに対する SQL クエリを実行します。 によって SQL クエリの結果が返されるし、[!INCLUDE[adapteroracle_short](../../includes/adapteroracle-short-md.md)]受信 POLLINGSTMT 操作の設定、厳密に型指定された結果としてアプリケーションにします。 使用してデータベースを構成し、Oracle のポーリングを実行するためのメカニズムの詳細については、[!INCLUDE[adapteroracle_short](../../includes/adapteroracle-short-md.md)]を参照してください[Oracle データベース アダプターのポーリングに基づいたデータ変更メッセージを受信](../../adapters-and-accelerators/adapter-oracle-database/receive-polling-based-data-changed-messages-in-oracle-database-adapter.md)します。 続行する前に、このトピックで確認することを強くお勧めします。  
  
 WCF サービス モデルを使用する場合は、POLLINGSTMT 操作を受信するには、次の必要があります。  
  
- アダプターによって公開されているメタデータから POLLINGSTMT 操作用には、WCF サービス コントラクト (インターフェイス) を生成します。 これを行うには、使用する、[!INCLUDE[addadapterservreflong](../../includes/addadapterservreflong-md.md)]または ServiceModel メタデータ ユーティリティ ツール (svcutil.exe)。  
  
- このインターフェイスからの WCF サービスを実装します。  
  
- サービス ホストを使用してこの WCF サービス ホスト (**System.ServiceModel.ServiceHost**)。  
  
  このセクションのトピックでは、情報および Oracle データベースのテーブルおよび WCF サービス モデルでのビューにポーリングを実行するために手順を説明します。  
  
## <a name="about-the-examples-used-in-this-topic"></a>このトピックで使用する例について  
 このトピックの例では、/SCOTT/ACCOUNTACTIVITY テーブルと/SCOTT/Package/ACCOUNT_PKG/PROCESS_ACTIVITY 関数を使用します。 これらの成果物を生成するスクリプトが付属、[!INCLUDE[adapterpacknoversion](../../includes/adapterpacknoversion-md.md)]サンプル。 サンプルの詳細については、次を参照してください。[アダプタ サンプル](../../adapters-and-accelerators/accelerator-rosettanet/adapter-samples.md)します。  
  
## <a name="configuring-polling-in-the-wcf-service-model"></a>WCF サービス モデルでのポーリングの構成  
 構成する、 [!INCLUDE[adapteroracle_short](../../includes/adapteroracle-short-md.md)] Oracle データベースのテーブルおよびビューのバインドのプロパティとオプションの接続プロパティ (パラメーター) を設定してポーリングを実行します。 これらのプロパティの一部は必須ですが、およびデザイン時と実行時の両方でいくつかに影響を与える設定する必要があります。  
  
- デザイン時に、設定する接続パラメーターとバインドのプロパティを WCF サービス コントラクトを生成する Oracle データベースに接続するとき。  
  
- 実行時に、サービス ホストを作成するために使用 OracleDBBinding オブジェクトにバインドのプロパティを設定します。 サービス ホストにサービスのリスナーを追加する場合は、接続パラメーターを設定します。  
  
  バインドのプロパティとポーリングを構成するために使用する接続パラメーターの概要を次に示します。  
  
- **PollingStatement**プロパティをバインドします。 デザイン時と実行時の両方にこのバインドのプロパティを設定する必要があります。  
  
- 省略可能なバインドのプロパティ。 これらは、実行時に設定するのみ必要です。  
  
- **AcceptCredentialsInUri**プロパティをバインドします。 このバインドのプロパティを設定する必要があります**true**実行時の接続 URI 内の資格情報を有効にする場合にします。 サービス ホストにサービス エンドポイントを追加するときに、ユーザー名とパスワードを接続 URI に存在することがあります。  
  
- **PollingId**接続 URI の文字列パラメーターをクエリします。 POLLINGSTMT 操作の名前空間を変更する場合は、デザイン時と実行時の両方では、この接続プロパティを設定する必要があります。  
  
  バインドのプロパティとポーリングを構成するために使用する接続パラメーターの詳細については、次を参照してください。 [Oracle データベース アダプターのポーリングに基づいたデータ変更メッセージを受信](../../adapters-and-accelerators/adapter-oracle-database/receive-polling-based-data-changed-messages-in-oracle-database-adapter.md)します。  
  
## <a name="the-wcf-service-contract-and-class"></a>WCF サービス コントラクトとクラス  
 いずれかを使用する、[!INCLUDE[addadapterservreflong](../../includes/addadapterservreflong-md.md)]または、ServiceModel メタデータ ユーティリティ ツール (svcutil.exe) を作成する WCF サービス コントラクト (インターフェイス) と POLLINGSTMT 操作のクラスをサポートします。  
  
 POLLINGSTMT 操作のサービス コントラクトを生成するこれらのツールのいずれかで、Oracle データベースに接続する場合。  
  
- 指定する必要があります、 **PollingStatement**プロパティをバインドします。 アダプターは、正しいメタデータ POLLINGSTMT 操作によって返される結果の厳密に型指定されたセットを生成するのに、このバインドのプロパティで、SELECT ステートメントを使用します。  
  
- 必要に応じて、接続 URI で PollingId パラメーターを指定することができます。 アダプターでは、このパラメーターを使用して、POLLINGSTMT 操作の名前空間を生成します。  
  
  次の例。  
  
- **PollingStatement** "SELECT * から ACCOUNTACTIVITY FOR UPDATE"に設定されます。  
  
- **PollingId** "AcctActivity"に設定されます。  
  
### <a name="the-wcf-service-contract-interface"></a>WCF サービス コントラクト (インターフェイス)  
 次のコードでは、POLLINGSTMT 操作用に生成する WCF サービス コントラクト (インターフェイス) を示します。  
  
```  
[System.CodeDom.Compiler.GeneratedCodeAttribute("System.ServiceModel", "3.0.0.0")]  
[System.ServiceModel.ServiceContractAttribute(Namespace="http://Microsoft.LobServices.OracleDB/2007/03", ConfigurationName="POLLINGSTMT_OperationGroup")]  
public interface POLLINGSTMT_OperationGroup {  
  
    // CODEGEN: Generating message contract since the wrapper namespace (http://Microsoft.LobServices.OracleDB/2007/03/POLLINGSTMTAcctActivity)  
    // of message POLLINGSTMT does not match the default value (http://Microsoft.LobServices.OracleDB/2007/03)  
    [System.ServiceModel.OperationContractAttribute(IsOneWay=true, Action="http://Microsoft.LobServices.OracleDB/2007/03/POLLINGSTMT")]  
    void POLLINGSTMT(POLLINGSTMT request);  
}  
```  
  
### <a name="the-message-contracts"></a>メッセージ コントラクト  
 接続 URI の PollingId パラメーターでは、メッセージ コントラクトの名前空間が変更されます。 要求メッセージは、厳密に型指定されたレコードのセットを返します。  
  
```  
[System.Diagnostics.DebuggerStepThroughAttribute()]  
[System.CodeDom.Compiler.GeneratedCodeAttribute("System.ServiceModel", "3.0.0.0")]  
[System.ServiceModel.MessageContractAttribute(WrapperName="POLLINGSTMT", WrapperNamespace="http://Microsoft.LobServices.OracleDB/2007/03/POLLINGSTMTAcctActivity", IsWrapped=true)]  
public partial class POLLINGSTMT {  
  
    [System.ServiceModel.MessageBodyMemberAttribute(Namespace="http://Microsoft.LobServices.OracleDB/2007/03/POLLINGSTMTAcctActivity", Order=0)]  
    public microsoft.lobservices.oracledb._2007._03.POLLINGSTMTAcctActivity.POLLINGSTMTRECORD[] POLLINGSTMTRECORD;  
  
    public POLLINGSTMT() {  
    }  
  
    public POLLINGSTMT(microsoft.lobservices.oracledb._2007._03.POLLINGSTMTAcctActivity.POLLINGSTMTRECORD[] POLLINGSTMTRECORD) {  
        this.POLLINGSTMTRECORD = POLLINGSTMTRECORD;  
    }  
}  
```  
  
### <a name="the-data-contract-namespace"></a>データ コントラクトの Namespace  
 データ コントラクトは、サービスと交換されるデータを抽象的に記述するクライアントの間の正式な取り決めです。 これは、通信するために、クライアントとサービスする必要はありません同一の型では、同じデータ コントラクトのみを共有します。  
  
 メッセージの変更データが発生した場合、データ コントラクト名前空間も変更 PollingId パラメーターで (指定した) 場合の接続 URI です。 データ コントラクトは、クエリの結果セット内の厳密に型指定されたレコードを表すクラスで構成されます。 クラス定義の詳細については、この例では省略されます。 クラスには、結果セット内の列を表すプロパティが含まれています。  
  
 次の例では、PollingId"AcctActivity"が使用されます。  
  
```  
namespace microsoft.lobservices.oracledb._2007._03.POLLINGSTMTAcctActivity {  
    using System.Runtime.Serialization;  
  
    [System.Diagnostics.DebuggerStepThroughAttribute()]  
    [System.CodeDom.Compiler.GeneratedCodeAttribute("System.Runtime.Serialization", "3.0.0.0")]  
    [System.Runtime.Serialization.DataContractAttribute(Name="POLLINGSTMTRECORD", Namespace="http://Microsoft.LobServices.OracleDB/2007/03/POLLINGSTMTAcctActivity")]  
    public partial class POLLINGSTMTRECORD : object, System.Runtime.Serialization.IExtensibleDataObject {…}  
     }  
}  
```  
  
### <a name="wcf-service-class"></a>WCF サービス クラス  
 [!INCLUDE[addadapterservrefshort](../../includes/addadapterservrefshort-md.md)]をサービス コントラクト (インターフェイス) から実装された WCF サービス クラスのスタブを持つファイルも生成されます。 ファイルの名前は、OracleDBBindingService.cs です。 このクラスに直接 POLLINGSTMT 操作を処理するロジックを挿入することができます。 Svcutil.exe を使用して、サービス コントラクト インターフェイスを生成する場合、必要がありますこのクラスの実装自分でします。 次のコードによって生成される WCF サービス クラスを示しています、[!INCLUDE[addadapterservrefshort](../../includes/addadapterservrefshort-md.md)]します。  
  
```  
namespace OracleDBBindingNamespace {  
  
    public class OracleDBBindingService : POLLINGSTMT_OperationGroup {  
  
        // CODEGEN: Generating message contract since the wrapper namespace (http://Microsoft.LobServices.OracleDB/2007/03/POLLINGSTMTAcctActivity)   
        // of message POLLINGSTMT does not match the default value (http://Microsoft.LobServices.OracleDB/2007/03)  
        public virtual void POLLINGSTMT(POLLINGSTMT request) {  
            throw new System.NotImplementedException("The method or operation is not implemented.");  
        }  
    }  
}  
```  
  
## <a name="receiving-the-pollingstmt-operation"></a>POLLINGSTMT 操作の受信  
  
#### <a name="to-receive-polling-data-from-the-oracle-database-adapter"></a>Oracle データベース アダプターのポーリングのデータを受信するには  
  
1. 使用して、[!INCLUDE[addadapterservrefshort](../../includes/addadapterservrefshort-md.md)]または WCF を生成する svcutil.exe サービス コントラクト (インターフェイス) と POLLINGSTMT 操作用にヘルパー クラス。 詳細については、次を参照してください。 [WCF クライアントまたは Oracle データベース ソリューションの成果物の WCF サービス コントラクトを生成](../../adapters-and-accelerators/adapter-oracle-database/create-a-wcf-client-or-wcf-service-contract-for-oracle-db-solution-artifacts.md)します。 設定する必要がありますには、少なくとも、 **PollingStatement**アダプターに接続するときにプロパティをバインドします。 必要に応じて、接続 URI で PollingId パラメーターを指定することができます。 使用する場合、[!INCLUDE[addadapterservrefshort](../../includes/addadapterservrefshort-md.md)]構成のために必要な設定のすべてのバインディング パラメーター。 これは、生成された構成ファイルで設定は正しくことを保証します。  
  
2. 手順 1. で生成されたインターフェイスとヘルパー クラスからの WCF サービスを実装します。 このクラスの POLLINGSTMT メソッドは、POLLINGSTMT 操作から受信したデータの処理エラーが発生した場合、ポーリング トランザクションを中止する例外をスローできます。それ以外の場合、メソッドは何も返しません。 次のように、WCF サービス クラスを属性する必要があります。  
  
   ```  
   [ServiceBehavior(InstanceContextMode = InstanceContextMode.Single)]  
   ```  
  
   1. 使用した場合、[!INCLUDE[addadapterservrefshort](../../includes/addadapterservrefshort-md.md)]インターフェイスを生成するには、直接のロジックを実装できる、 **POLLINGSTMT**に生成されたメソッド**OracleDBBindingService**クラス。 このクラスは、OracleDBBindingService.cs で確認できます。 この例では、このコードはサブ クラス、 **OracleDBBindingService**クラス。  
  
      ```  
      [ServiceBehavior(InstanceContextMode = InstanceContextMode.Single)]  
  
      public class PollingStmtService : OracleDBBindingService  
      {  
          public override void POLLINGSTMT(POLLINGSTMT request)  
          {  
              Console.WriteLine("\nNew Polling Records Received");  
              Console.WriteLine("Tx Id\tAccount\tAmount\tDate\t\t\tDescription");  
              for (int i = 0; i < request.POLLINGSTMTRECORD.Length; i++)  
              {  
                  Console.WriteLine("{0}\t{1}\t{2}\t{3}\t{4}", request.POLLINGSTMTRECORD[i].TID,  
                                      request.POLLINGSTMTRECORD[i].ACCOUNT,  
                                      request.POLLINGSTMTRECORD[i].AMOUNT,  
                                      request.POLLINGSTMTRECORD[i].TRANSDATE,  
                                      request.POLLINGSTMTRECORD[i].DESCRIPTION);  
              }  
          }  
      }  
      ```  
  
   2. Svcutil.exe を使用してインターフェイスを生成した場合は、インターフェイスを実装する WCF サービスを作成しのロジックを実装する必要があります、 **POLLINGSTMT**このクラスのメソッド。  
  
3. 手順 2 で作成した WCF サービスのインスタンスを作成します。  
  
   ```  
   // create service instance  
   PollingStmtService pollingInstance = new PollingStmtService();  
   ```  
  
4. インスタンスを作成**System.ServiceModel.ServiceHost** WCF サービスと基本の接続 URI を使用しています。 基本の接続 URI には、userinfoparams またはクエリ文字列を含めることはできません。  
  
   ```  
   // Enable service host  
   Uri[] baseUri = new Uri[] { new Uri("oracledb://Adapter") };  
   ServiceHost srvHost = new ServiceHost(pollingInstance, baseUri);  
   ```  
  
5. 作成、 **OracleDBBinding**し、そのバインドのプロパティを設定してポーリング操作を構成します。 コードで明示的に、または構成で宣言的に、これを行うことができます。 少なくとも、ポーリング ステートメントとポーリング間隔を指定する必要があります。 この例では、する資格情報を指定の URI の一部としても設定する必要がありますので、 **AcceptCredentialsInUri**に**true**します。  
  
   ```  
   // Create and configure a binding for the service endpoint. NOTE: binding  
   // parameters are set here for clarity, but these are already set in the  
   // the generated configuration file  
   OracleDBBinding binding = new OracleDBBinding();  
  
   // The credentials are included in the connection URI, so set this property to true  
   binding.AcceptCredentialsInUri = true;  
  
   // Same as statement specified in Configure Adapter dialog box  
   binding.PollingStatement = "SELECT * FROM ACCOUNTACTIVITY FOR UPDATE";  
   binding.PostPollStatement = "BEGIN ACCOUNT_PKG.PROCESS_ACTIVITY(); END;";  
  
   // Be sure to set the interval long enough to complete processing before  
   // the next poll  
   binding.PollingInterval = 15;  
   // Polling is transactional; be sure to set an adequate isolation level   
   // for your environment  
   binding.TransactionIsolationLevel = TransactionIsolationLevel.ReadCommitted;  
   ```  
  
6. サービス ホストにサービス エンドポイントを追加します。 これを行うには :  
  
   -   手順 5. で作成したバインドを使用します。  
  
   -   接続の資格情報を含む URI を指定し、必要に応じて、PollingId 場合。  
  
   -   "POLLINGSTMT_OperationGroup"としてコントラクトを指定します。  
  
   ```  
   // Add service endpoint: be sure to specify POLLINGSTMT_OperationGroup as the contract  
   Uri serviceUri = new Uri("oracledb://User=SCOTT;Password=TIGER@Adapter?PollingId=AcctActivity");  
   srvHost.AddServiceEndpoint("POLLINGSTMT_OperationGroup", binding, serviceUri);  
   ```  
  
7. ポーリングのデータを受信するには、サービス ホストを開きます。 アダプターは、クエリが結果セットを返すたびにデータを返します。  
  
   ```  
   // Open the service host to begin polling  
   srvHost.Open();  
   ```  
  
8. ポーリングを終了するには、サービス ホストを閉じます。  
  
   > [!IMPORTANT]
   >  アダプターは、サービス ホストが閉じられるまでポーリングを続行します。  
  
   ```  
   srvHost.Close();  
   ```  
  
### <a name="example"></a>例  
 次の例では、SCOTT/ACCOUNTACTIVITY テーブルに対して実行されるポーリング クエリを示します。 ポーリング後ステートメントは、処理済みレコードを別のテーブル/SCOTT/ACCOUNTHISTORY に移動する Oracle 関数を呼び出します。 接続 URI の"AccountActivity"PollingId パラメーターを設定して POLLINGSTMT 操作の名前空間が変更されます。 この例では、生成されたをサブクラス化して POLLINGSTMT 操作用の WCF サービスを作成**OracleDBBindingService**クラス。 ただし、生成されたクラス内で直接、ロジックを実装できます。  
  
```  
using System;  
using System.Collections.Generic;  
using System.Text;  
  
// Add these three references to use the Oracle adapter  
using System.ServiceModel;  
using Microsoft.ServiceModel.Channels;  
using Microsoft.Adapters.OracleDB;  
  
using microsoft.lobservices.oracledb._2007._03.POLLINGSTMTAcctActivity;  
using OracleDBBindingNamespace;  
  
namespace OraclePollingSM  
{  
    [ServiceBehavior(InstanceContextMode = InstanceContextMode.Single)]  
  
    public class PollingStmtService : OracleDBBindingService  
    {  
        public override void POLLINGSTMT(POLLINGSTMT request)  
        {  
            Console.WriteLine("\nNew Polling Records Received");  
            Console.WriteLine("Tx Id\tAccount\tAmount\tDate\t\t\tDescription");  
            for (int i = 0; i < request.POLLINGSTMTRECORD.Length; i++)  
            {  
                Console.WriteLine("{0}\t{1}\t{2}\t{3}\t{4}", request.POLLINGSTMTRECORD[i].TID,  
                                    request.POLLINGSTMTRECORD[i].ACCOUNT,  
                                    request.POLLINGSTMTRECORD[i].AMOUNT,  
                                    request.POLLINGSTMTRECORD[i].TRANSDATE,  
                                    request.POLLINGSTMTRECORD[i].DESCRIPTION);  
  
            }  
            Console.WriteLine("\nHit <RETURN> to stop polling");  
         }  
    }  
  
    class Program  
    {  
        static void Main(string[] args)  
        {  
            ServiceHost srvHost = null;  
  
            // This URI is used to specify the address for the ServiceEndpoint  
            // It must contain credentials and the PollingId (if any) that was used to generate  
            // the WCF service callback interface  
            Uri serviceUri = new Uri("OracleDb://User=SCOTT;Password=TIGER@Adapter?PollingId=AcctActivity");  
  
            // This URI is used to initialize the ServiceHost. It cannot contain  
            // userinfoparms (credentials) or a query_string (PollingId); otherwise,  
            // an exception is thrown when the ServiceHost is initialized.  
            Uri[] baseUri = new Uri[] { new Uri("OracleDb://Adapter") };  
  
            Console.WriteLine("Sample started, initializing service host -- please wait");  
  
            // create an instanc of the WCF service callback class  
            PollingStmtService pollingInstance = new PollingStmtService();  
  
            try  
            {  
                // Create a ServiceHost with the service callback instance and a base URI (address)  
                srvHost = new ServiceHost(pollingInstance, baseUri);  
  
                // Create and configure a binding for the service endpoint. Note: binding  
                // parameters are set here for clarity but these are already set in the  
                // generated configuration file  
                //  
                // The following properties are set  
                //    AcceptCredentialsInUri (true) to enable credentials in the connection URI for AddServiceEndpoint  
                //    PollingStatement  
                //    PostPollStatement calls PROCESS_ACTIVITY on Oracle. This procedure moves the queried records to  
                //                      the ACCOUNTHISTORY table  
                //    PollingInterval (15 seconds)  
                //    TransactionIsolationLevel   
  
                OracleDBBinding binding = new OracleDBBinding();  
  
                // The Credentials are included in the Connection Uri so set this property true  
                binding.AcceptCredentialsInUri = true;  
  
                // Same as statement specified in Configure Adapter dialog box  
                binding.InboundOperationType = InboundOperation.Polling;  
                binding.PollingStatement = "SELECT * FROM ACCOUNTACTIVITY FOR UPDATE";  
                binding.PostPollStatement = "BEGIN ACCOUNT_PKG.PROCESS_ACTIVITY(); END;";  
  
                // Be sure to set the interval long enough to complete processing before  
                // the next poll  
                binding.PollingInterval = 15;  
  
                // Polling is transactional, be sure to set an adequate isolation level   
                // for your environment  
                binding.TransactionIsolationLevel = TransactionIsolationLevel.ReadCommitted;  
  
                // Add service endpoint: be sure to specify POLLINGSTMT_OperationGroup as the contract  
                srvHost.AddServiceEndpoint("POLLINGSTMT_OperationGroup", binding, serviceUri);  
  
                Console.WriteLine("Opening the service host");  
                // Open the service host to begin polling  
                srvHost.Open();  
  
                // Wait to receive request  
                Console.WriteLine("\nPolling started. Returned records will be written to the console.");  
                Console.WriteLine("Hit <RETURN> to stop polling");  
                Console.ReadLine();  
            }  
            catch (Exception e)  
            {  
                Console.WriteLine("Exception :" + e.Message);  
                Console.ReadLine();  
  
                /* If there is an Oracle Error it will be specified in the inner exception */  
                if (e.InnerException != null)  
                {  
                    Console.WriteLine("InnerException: " + e.InnerException.Message);  
                    Console.ReadLine();  
                }  
            }  
            finally  
            {  
                // IMPORTANT: you must close the ServiceHost to stop polling  
                if (srvHost.State == CommunicationState.Opened)  
                    srvHost.Close();  
                else  
                    srvHost.Abort();  
            }  
  
        }  
    }  
}  
```  
  
## <a name="see-also"></a>参照  
 [WCF サービス モデルを使用して Oracle データベース アプリケーションを開発します。](../../adapters-and-accelerators/adapter-oracle-database/develop-oracle-database-applications-using-the-wcf-service-model.md)