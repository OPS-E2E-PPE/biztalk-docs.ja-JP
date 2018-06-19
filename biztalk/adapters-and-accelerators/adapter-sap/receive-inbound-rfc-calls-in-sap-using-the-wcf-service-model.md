---
title: RFC 呼び出しの受信を WCF サービス モデルを使用して SAP で受信 |Microsoft ドキュメント
ms.custom: ''
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: ''
ms.suite: ''
ms.tgt_pltfrm: ''
ms.topic: article
helpviewer_keywords:
- WCF service model, receiving inbound RFC calls
- RFC calls, receiving inbound using the WCF service model
ms.assetid: 064d70d7-1603-467f-9aba-ecab78a567ff
caps.latest.revision: 6
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: a415e3ab0ecbaab8778254d817241e5cafb61a92
ms.sourcegitcommit: cb908c540d8f1a692d01dc8f313e16cb4b4e696d
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 09/20/2017
ms.locfileid: "22218458"
---
# <a name="receive-inbound-rfc-calls-in-sap-using-the-wcf-service-model"></a>WCF サービス モデルを使用して SAP で受信 RFC 呼び出しの受信します。
[!INCLUDE[adaptersap](../../includes/adaptersap-md.md)] SAP システムによって呼び出される Rfc を受信する RFC サーバーとして機能できます。  
  
 WCF サービス モデルで、受信の Rfc を受信するには、次の必要があります。  
  
-   SAP システムで、RFC 変換先が存在することを確認します。  
  
-   RFC が SAP システムで定義されていることを確認します。  
  
-   アダプターによって公開されるメタデータから RFC 操作のためには、WCF サービス コントラクト (インターフェイス) を生成します。 これを行うには、使用する、[!INCLUDE[addadapterservreflong](../../includes/addadapterservreflong-md.md)]または ServiceModel メタデータ ユーティリティ ツール (svcutil.exe)。  
  
-   このインターフェイスから WCF サービスを実装します。 WCF サービスのメソッドは、RFC の処理をアダプターに応答を返すために必要なロジックを含む (つまり、SAP システム)。  
  
-   サービス ホストを使用してこの WCF サービスをホスト (**System.ServiceModel.ServiceHost**)。  
  
 以降のセクションを使用して SAP システムからの Rfc を受信する方法を表示、[!INCLUDE[adaptersap_short](../../includes/adaptersap-short-md.md)]です。  
  
## <a name="how-to-set-up-the-sap-system-to-send-an-rfc-to-the-sap-adapter"></a>RFC を SAP アダプターに送信する SAP システムを設定する方法  
 SAP システムから、RFC を送信する前に、[!INCLUDE[adaptersap_short](../../includes/adaptersap-short-md.md)]次が SAP システムで該当することを確認する必要があります。  
  
-   RFC 変換先、[!INCLUDE[adaptersap_short](../../includes/adaptersap-short-md.md)]存在する必要があります。 [!INCLUDE[adaptersap_short](../../includes/adaptersap-short-md.md)]は自身の Rfc を SAP システムから受信するため、RFC 変換先に登録します。 SAP 接続 SAP ゲートウェイ ホスト、SAP ゲートウェイ サービス、および、アダプター自身を登録に使用する SAP プログラム ID などの URI でパラメーターを指定するとします。 SAP に、RFC 変換先をセットアップする方法については、次を参照してください。 [Create RFC、RFC 変換先、および送信の SAP システムから RFC](creating-an-rfc-in-an-sap-system.md)です。  
  
-   SAP システムでは、RFC を定義する必要があります。 SAP システムで、RFC を定義する関数モジュールを作成する必要があります。 [!INCLUDE[adaptersap_short](../../includes/adaptersap-short-md.md)] SAP システムで、RFC 定義を使用して、RFC (デザイン時および実行時に両方) に関するメタデータを取得します。 詳細については、次を参照してください。 [SAP システムで RFC を作成する](../../adapters-and-accelerators/adapter-sap/creating-an-rfc-in-an-sap-system.md)です。  
  
    > [!NOTE]
    >  SAP システムの RFC を定義する必要があります。ただし、RFC を実装するクライアント コードでアダプターにします。 アダプターは、RFC のメタデータを取得できるように、SAP システムで RFC を定義する必要があります。  
  
 RFC を 2 つの整数を追加し、その結果を返しますの SAP システム上のソース コードの例を次に示します。 コードでは、指定した宛先を介して、RFC だけ呼び出します。 関数の実装は、[!INCLUDE[adaptersap_short](../../includes/adaptersap-short-md.md)]クライアント コード。  
  
```  
FUNCTION Z_RFC_SAMPLE_ADD.  
*"---------------------------------------------------------------------*"*"Local interface:  
*"  IMPORTING  
*"     VALUE(X) TYPE  INT4  
*"     VALUE(Y) TYPE  INT4  
*"     VALUE(DEST) TYPE  CHAR20 DEFAULT 'SAPADAPTER'  
*"  EXPORTING  
*"     VALUE(RESULT) TYPE  INT4  
*"---------------------------------------------------------------------CALL FUNCTION 'Z_RFC_MKD_ADD' DESTINATION DEST  
  EXPORTING X = X  
            Y = Y  
  IMPORTING RESULT = RESULT.  
  
ENDFUNCTION.  
```  
  
## <a name="the-wcf-service-contract-for-an-rfc"></a>RFC の WCF サービス コントラクト  
 使用する、[!INCLUDE[addadapterservreflong](../../includes/addadapterservreflong-md.md)]または、ServiceModel メタデータ ユーティリティ ツール (svcutil.exe) を SAP システムから受信する Rfc に WCF サービス コントラクトを生成します。 以降のセクションでは、マネージ コード クラスと Z_RFC_MKD_ADD 操作に対して生成されたインターフェイスを表示します。  
  
### <a name="the-rfc-interface-wcf-service-contract"></a>Rfc インターフェイス (WCF サービス コントラクト)  
 [!INCLUDE[adaptersap_short](../../includes/adaptersap-short-md.md)] "Rfc"、1 つのサービス コントラクトでのすべての RFC 操作を表示します。 つまり、1 つのインターフェイス**Rfc**のすべての受信する RFC 操作が作成されます。 RFC 操作の各ターゲットは、このインターフェイスのメソッドとして表されます。 各メソッドには、単一のパラメーターを操作の要求メッセージのメッセージ コントラクトを表します。 操作の応答メッセージのメッセージ コントラクトを表すオブジェクトを返します。  
  
```  
[System.CodeDom.Compiler.GeneratedCodeAttribute("System.ServiceModel", "3.0.0.0")]  
[System.ServiceModel.ServiceContractAttribute(Namespace="http://Microsoft.LobServices.Sap/2007/03/", ConfigurationName="Rfc")]  
public interface Rfc {  
  
    // CODEGEN: Generating message contract since the wrapper namespace (http://Microsoft.LobServices.Sap/2007/03/Rfc/) of message Z_RFC_MKD_ADDRequest does not match the default value (http://Microsoft.LobServices.Sap/2007/03/)  
    [System.ServiceModel.OperationContractAttribute(Action="http://Microsoft.LobServices.Sap/2007/03/Rfc/Z_RFC_MKD_ADD", ReplyAction="http://Microsoft.LobServices.Sap/2007/03/Rfc/Z_RFC_MKD_ADD/response")]  
    Z_RFC_MKD_ADDResponse Z_RFC_MKD_ADD(Z_RFC_MKD_ADDRequest request);  
}  
  
```  
  
### <a name="the-request-and-response-messages"></a>要求および応答メッセージ  
 RFC の各操作は、要求メッセージを表し、応答メッセージを表すオブジェクトを取得するパラメーターを受け取ります。 要求メッセージのプロパティは、インポートおよび rfc (入力) の変化させるパラメーターを格納します。 応答メッセージのプロパティは、エクスポートを含めるし、(出力) 操作のパラメーターを変更します。  
  
```  
[System.Diagnostics.DebuggerStepThroughAttribute()]  
[System.CodeDom.Compiler.GeneratedCodeAttribute("System.ServiceModel", "3.0.0.0")]  
[System.ServiceModel.MessageContractAttribute(WrapperName="Z_RFC_MKD_ADD", WrapperNamespace="http://Microsoft.LobServices.Sap/2007/03/Rfc/", IsWrapped=true)]  
public partial class Z_RFC_MKD_ADDRequest {  
  
    [System.ServiceModel.MessageBodyMemberAttribute(Namespace="http://Microsoft.LobServices.Sap/2007/03/Rfc/", Order=0)]  
    public string DEST;  
  
    [System.ServiceModel.MessageBodyMemberAttribute(Namespace="http://Microsoft.LobServices.Sap/2007/03/Rfc/", Order=1)]  
    public System.Nullable<int> X;  
  
    [System.ServiceModel.MessageBodyMemberAttribute(Namespace="http://Microsoft.LobServices.Sap/2007/03/Rfc/", Order=2)]  
    public System.Nullable<int> Y;  
  
    public Z_RFC_MKD_ADDRequest() {  
    }  
  
    public Z_RFC_MKD_ADDRequest(string DEST, System.Nullable<int> X, System.Nullable<int> Y) {  
        this.DEST = DEST;  
        this.X = X;  
        this.Y = Y;  
    }  
}  
  
[System.Diagnostics.DebuggerStepThroughAttribute()]  
[System.CodeDom.Compiler.GeneratedCodeAttribute("System.ServiceModel", "3.0.0.0")]  
[System.ServiceModel.MessageContractAttribute(WrapperName="Z_RFC_MKD_ADDResponse", WrapperNamespace="http://Microsoft.LobServices.Sap/2007/03/Rfc/", IsWrapped=true)]  
public partial class Z_RFC_MKD_ADDResponse {  
  
    [System.ServiceModel.MessageBodyMemberAttribute(Namespace="http://Microsoft.LobServices.Sap/2007/03/Rfc/", Order=0)]  
    public int RESULT;  
  
    public Z_RFC_MKD_ADDResponse() {  
    }  
  
    public Z_RFC_MKD_ADDResponse(int RESULT) {  
        this.RESULT = RESULT;  
    }  
}  
```  
  
### <a name="the-generated-wcf-service"></a>生成された WCF サービス  
 [!INCLUDE[addadapterservrefshort](../../includes/addadapterservrefshort-md.md)]もで WCF サービス コントラクトを実装する WCF サービスが生成されます (**Rfc**)。 このクラスのメソッドがスタブとして作成します。 このクラスは、別のファイルに生成されます。 このクラスのメソッド内で直接コードを実装できます。  
  
```  
namespace SAPBindingNamespace {  
  
    public class SAPBindingService : Rfc {  
  
        // CODEGEN: Generating message contract since the wrapper namespace (http://Microsoft.LobServices.Sap/2007/03/Rfc/) of message Z_RFC_MKD_ADDRequest does not match the default value (http://Microsoft.LobServices.Sap/2007/03/)  
        public virtual Z_RFC_MKD_ADDResponse Z_RFC_MKD_ADD(Z_RFC_MKD_ADDRequest request) {  
            throw new System.NotImplementedException("The method or operation is not implemented.");  
        }  
    }  
}  
```  
  
## <a name="how-to-create-an-rfc-server-application"></a>RFC サーバー アプリケーションを作成する方法  
 SAP システムからの Rfc を受信するには、WCF サービス モデルを使用して、する」の手順を行うことができる[SAP アダプターで WCF サービス モデルの概要](../../adapters-and-accelerators/adapter-sap/overview-of-the-wcf-service-model-with-the-sap-adapter.md)です。 必ず、サービス エンドポイント (の作成と WCF サービスを実装する手順の手順 6) を追加するときに、サービス コントラクトの 'Rfc' を指定してください。  
  
 次のコードを使用して SAP システムから、Z_RFC_MKD_RFC を受信する方法の完全な例を示しています、[!INCLUDE[adaptersap_short](../../includes/adaptersap-short-md.md)]です。 この RFC では、2 つの整数パラメーターを SAP システムに、結果を返します。  
  
```  
using System;  
using System.Collections.Generic;  
using System.Text;  
  
// Add WCF, WCF LOB Adapter SDK, and SAP adapter namepaces  
using System.ServiceModel;  
using Microsoft.Adapters.SAP;  
using Microsoft.ServiceModel.Channels;  
  
// Include this namespace for the WCF LOB Adapter SDK and SAP adapter exceptions  
using Microsoft.ServiceModel.Channels.Common;  
  
namespace SapRfcServerSM  
{  
    // Implement a WCF service callback class by sub-classing the generated service callback class (SAPBindingService).  
    // You must annotate this class with the InstanceContextMode.Single ServiceBehavior  
    // If you implement your code in SAPBindingService.cs be sure to annotate the SAPBindingService class  
    // The callback method should return a Z_RFC_MKD_ADDResponse to indicate successful processing  
    // or throw an exception to indicate an error.  
    [ServiceBehavior(InstanceContextMode = InstanceContextMode.Single,UseSynchronizationContext = false)]  
    class RfcServerClass : SAPBindingNamespace.SAPBindingService  
    {  
  
        public override Z_RFC_MKD_ADDResponse Z_RFC_MKD_ADD(Z_RFC_MKD_ADDRequest request)  
        {  
            // If either parameter is null, throw an exception   
            if (request.X == null || request.Y == null)  
                throw new System.ArgumentNullException();  
  
            int result = (int) (request.X + request.Y);  
  
            Console.WriteLine("\nRfc Received");  
            Console.WriteLine("X =\t\t" + request.X.ToString());  
            Console.WriteLine("Y =\t\t" + request.Y.ToString());  
            Console.WriteLine("Result =\t" + result);  
            Console.WriteLine("\nHit <RETURN> to end");  
  
            return new Z_RFC_MKD_ADDResponse(result);  
        }  
  
    }  
  
    class Program  
    {  
        static void Main(string[] args)  
        {  
            // Listener connection for the service URI -- the connection URI must contain credentials  
            Uri serviceUri = new Uri("sap://User=YourUserName;Passwd=YourPassword;Client=800;Lang=EN;@a/ADAPSAP47/00?ListenerGwServ=SAPGW00&ListenerGwHost=ADAPSAP47&ListenerProgramId=ADDER");  
  
            // The baseUri cannot contain userinfoparams or query_string parameters  
            Uri[] baseUri = new Uri[] { new Uri("sap://a/ADAPSAP47/00") };  
  
            Console.WriteLine("RFC server sample started");  
  
            // create service instance  
            RfcServerClass rfcServerInstance = new RfcServerClass();  
  
            try  
            {  
                Console.WriteLine("Initializing service host -- please wait");  
                // Create and initialize a service host  
                using (ServiceHost srvHost = new ServiceHost(rfcServerInstance, baseUri))  
                {  
  
                    // Add service endpoint   
                    // Specify AcceptCredentalsInUri=true for the binding  
                    // NOTE: The contract for the service endpoint is "Rfc".  
                    //       This is the generated WCF service callback interface (see SAPBindingInterface.cs).  
                    SAPBinding binding = new SAPBinding();  
                    binding.AcceptCredentialsInUri = true;  
                    srvHost.AddServiceEndpoint("Rfc", binding, serviceUri);  
                    srvHost.Open();  
  
                    Console.WriteLine("\nReady to receive Z_RFC_MKD_ADD RFC");  
                    Console.WriteLine("Hit <RETURN> to end");  
  
                    // Wait to receive request  
                    Console.ReadLine();  
                }  
            }  
            catch (ConnectionException cex)  
            {  
                Console.WriteLine("Exception occurred connecting to the SAP system");  
                Console.WriteLine(cex.InnerException.Message);  
            }  
            catch (TargetSystemException tex)  
            {  
                Console.WriteLine("Exception occurred on the SAP system");  
                Console.WriteLine(tex.InnerException.Message);  
            }  
            catch (Exception ex)  
            {  
                Console.WriteLine("Exception is: " + ex.Message);  
                if (ex.InnerException != null)  
                {  
                    Console.WriteLine("Inner Exception is: " + ex.InnerException.Message);  
                }  
            }  
        }  
    }  
}  
```  
  
## <a name="see-also"></a>参照  
[WCF サービス モデルを使用してアプリケーションを開発します。](../../adapters-and-accelerators/adapter-sap/develop-sap-applications-using-the-wcf-service-model.md)   
 [RFC 操作のメッセージ スキーマ](../../adapters-and-accelerators/adapter-sap/message-schemas-for-rfc-operations.md)