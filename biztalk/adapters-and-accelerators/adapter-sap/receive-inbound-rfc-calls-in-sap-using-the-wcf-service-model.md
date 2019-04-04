---
title: WCF サービス モデルを使用して SAP で受信 RFC 呼び出しを受け取る |Microsoft Docs
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
ms.openlocfilehash: e9650567f9f2072662af7f75d735a5a647de6d10
ms.sourcegitcommit: 266308ec5c6a9d8d80ff298ee6051b4843c5d626
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 06/27/2018
ms.locfileid: "37014187"
---
# <a name="receive-inbound-rfc-calls-in-sap-using-the-wcf-service-model"></a><span data-ttu-id="202bc-102">WCF サービス モデルを使用して SAP で受信 RFC 呼び出しを受信します。</span><span class="sxs-lookup"><span data-stu-id="202bc-102">Receive Inbound RFC Calls in SAP using the WCF Service Model</span></span>
<span data-ttu-id="202bc-103">[!INCLUDE[adaptersap](../../includes/adaptersap-md.md)] SAP システムによって呼び出される Rfc を受信する RFC サーバーとして機能できます。</span><span class="sxs-lookup"><span data-stu-id="202bc-103">The [!INCLUDE[adaptersap](../../includes/adaptersap-md.md)] can act as an RFC server to receive RFCs invoked by a SAP system.</span></span>  
  
 <span data-ttu-id="202bc-104">WCF サービス モデルでは、受信 Rfc を受信するには、次の必要があります。</span><span class="sxs-lookup"><span data-stu-id="202bc-104">To receive the inbound RFCs in the WCF service model, you must:</span></span>  
  
- <span data-ttu-id="202bc-105">RFC 転送先が SAP システムに存在することを確認します。</span><span class="sxs-lookup"><span data-stu-id="202bc-105">Ensure that an RFC destination exists on the SAP system.</span></span>  
  
- <span data-ttu-id="202bc-106">RFC が SAP システムで定義されていることを確認します。</span><span class="sxs-lookup"><span data-stu-id="202bc-106">Ensure that the RFC is defined on the SAP system.</span></span>  
  
- <span data-ttu-id="202bc-107">RFC 操作、アダプターによって公開されているメタデータからの WCF サービス コントラクト (インターフェイス) を生成します。</span><span class="sxs-lookup"><span data-stu-id="202bc-107">Generate a WCF service contract (interface) for the RFC operation from the metadata exposed by the adapter.</span></span> <span data-ttu-id="202bc-108">これを行うには、使用する、[!INCLUDE[addadapterservreflong](../../includes/addadapterservreflong-md.md)]または ServiceModel メタデータ ユーティリティ ツール (svcutil.exe)。</span><span class="sxs-lookup"><span data-stu-id="202bc-108">To do this, you use the [!INCLUDE[addadapterservreflong](../../includes/addadapterservreflong-md.md)] or the ServiceModel Metadata Utility Tool (svcutil.exe).</span></span>  
  
- <span data-ttu-id="202bc-109">このインターフェイスからの WCF サービスを実装します。</span><span class="sxs-lookup"><span data-stu-id="202bc-109">Implement a WCF service from this interface.</span></span> <span data-ttu-id="202bc-110">WCF サービスのメソッドは、RFC を処理し、アダプターに応答を返すために必要なロジックを含めることが (つまり、SAP システム)。</span><span class="sxs-lookup"><span data-stu-id="202bc-110">The methods of the WCF service contain the logic necessary to process the RFC and return a response to the adapter (and hence the SAP system).</span></span>  
  
- <span data-ttu-id="202bc-111">サービス ホストを使用してこの WCF サービス ホスト (**System.ServiceModel.ServiceHost**)。</span><span class="sxs-lookup"><span data-stu-id="202bc-111">Host this WCF service using a service host (**System.ServiceModel.ServiceHost**).</span></span>  
  
  <span data-ttu-id="202bc-112">次のセクションでは、Rfc を使用して、SAP システムから受信する方法を説明、[!INCLUDE[adaptersap_short](../../includes/adaptersap-short-md.md)]します。</span><span class="sxs-lookup"><span data-stu-id="202bc-112">The following sections show you how to receive RFCs from the SAP system by using the [!INCLUDE[adaptersap_short](../../includes/adaptersap-short-md.md)].</span></span>  
  
## <a name="how-to-set-up-the-sap-system-to-send-an-rfc-to-the-sap-adapter"></a><span data-ttu-id="202bc-113">SAP アダプターを RFC を送信する SAP システムを設定する方法</span><span class="sxs-lookup"><span data-stu-id="202bc-113">How to Set up the SAP System to Send an RFC to the SAP Adapter</span></span>  
 <span data-ttu-id="202bc-114">SAP システムから RFC を送信する前に、[!INCLUDE[adaptersap_short](../../includes/adaptersap-short-md.md)]を次が SAP システムに該当することを確認する必要があります。</span><span class="sxs-lookup"><span data-stu-id="202bc-114">Before you can send an RFC from the SAP system to the [!INCLUDE[adaptersap_short](../../includes/adaptersap-short-md.md)], you must ensure that the following are true on the SAP system:</span></span>  
  
- <span data-ttu-id="202bc-115">RFC 転送先の[!INCLUDE[adaptersap_short](../../includes/adaptersap-short-md.md)]存在する必要があります。</span><span class="sxs-lookup"><span data-stu-id="202bc-115">An RFC destination for the [!INCLUDE[adaptersap_short](../../includes/adaptersap-short-md.md)] must exist.</span></span> <span data-ttu-id="202bc-116">[!INCLUDE[adaptersap_short](../../includes/adaptersap-short-md.md)]自身の SAP システムから Rfc を受信する RFC 転送先を登録します。</span><span class="sxs-lookup"><span data-stu-id="202bc-116">The [!INCLUDE[adaptersap_short](../../includes/adaptersap-short-md.md)] registers itself with an RFC destination to receive RFCs from the SAP system.</span></span> <span data-ttu-id="202bc-117">SAP 接続、SAP ゲートウェイ ホスト、SAP ゲートウェイ サービスと、アダプター自身を登録に使用する SAP プログラム ID などの URI でパラメーターを指定します。</span><span class="sxs-lookup"><span data-stu-id="202bc-117">You supply parameters in the SAP connection URI such as the SAP Gateway Host, the SAP Gateway Service, and the SAP Program ID that the adapter uses to register itself.</span></span> <span data-ttu-id="202bc-118">SAP で RFC 転送先をセットアップする方法については、[RFC を作成する、RFC 変換先、および RFC を送信する SAP システムから](creating-an-rfc-in-an-sap-system.md)を参照してください。</span><span class="sxs-lookup"><span data-stu-id="202bc-118">For information about how to setup an RFC destination on SAP, see [Create an RFC, RFC destination, and send an RFC from SAP system](creating-an-rfc-in-an-sap-system.md).</span></span>  
  
- <span data-ttu-id="202bc-119">RFC は、SAP システムで定義する必要があります。</span><span class="sxs-lookup"><span data-stu-id="202bc-119">The RFC must be defined on the SAP system.</span></span> <span data-ttu-id="202bc-120">SAP システムに対する RFC を定義する関数モジュールを作成する必要があります。</span><span class="sxs-lookup"><span data-stu-id="202bc-120">You must create a function module that defines the RFC on the SAP system.</span></span> <span data-ttu-id="202bc-121">[!INCLUDE[adaptersap_short](../../includes/adaptersap-short-md.md)] (デザイン時と実行時に両方)、RFC に関するメタデータを取得する SAP システムの RFC 定義を使用します。</span><span class="sxs-lookup"><span data-stu-id="202bc-121">The [!INCLUDE[adaptersap_short](../../includes/adaptersap-short-md.md)] uses the RFC definition on the SAP system to retrieve metadata about the RFC (both at design time and at run time).</span></span> <span data-ttu-id="202bc-122">詳細については、[SAP システムでの RFC を作成する](../../adapters-and-accelerators/adapter-sap/creating-an-rfc-in-an-sap-system.md)を参照してください。</span><span class="sxs-lookup"><span data-stu-id="202bc-122">For more information see [Creating an RFC in an SAP System](../../adapters-and-accelerators/adapter-sap/creating-an-rfc-in-an-sap-system.md).</span></span>  
  
  > [!NOTE]
  >  <span data-ttu-id="202bc-123">SAP システムの RFC を定義する必要があります。ただし、RFC を実装するクライアント コードでアダプターにします。</span><span class="sxs-lookup"><span data-stu-id="202bc-123">You must define the RFC on the SAP system; however you implement the RFC in your adapter client code.</span></span> <span data-ttu-id="202bc-124">アダプターは、RFC のメタデータを取得できるように、SAP システムで、RFC を定義する必要があります。</span><span class="sxs-lookup"><span data-stu-id="202bc-124">The RFC must be defined on the SAP system so that the adapter can retrieve metadata for the RFC.</span></span>  
  
  <span data-ttu-id="202bc-125">次は、RFC を 2 つの整数を追加し、その結果を返しますの SAP システムのソース コードの例です。</span><span class="sxs-lookup"><span data-stu-id="202bc-125">The following is an example of the source code on the SAP system for an RFC that adds two integers and returns their result.</span></span> <span data-ttu-id="202bc-126">コードは、指定した変換先をだけで、RFC を呼び出します。</span><span class="sxs-lookup"><span data-stu-id="202bc-126">The code merely calls the RFC through a specified destination.</span></span> <span data-ttu-id="202bc-127">関数の実装は、[!INCLUDE[adaptersap_short](../../includes/adaptersap-short-md.md)]クライアント コード。</span><span class="sxs-lookup"><span data-stu-id="202bc-127">The implementation of the function is done by the [!INCLUDE[adaptersap_short](../../includes/adaptersap-short-md.md)] client code.</span></span>  
  
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
  
## <a name="the-wcf-service-contract-for-an-rfc"></a><span data-ttu-id="202bc-128">RFC の WCF サービス コントラクト</span><span class="sxs-lookup"><span data-stu-id="202bc-128">The WCF Service Contract for an RFC</span></span>  
 <span data-ttu-id="202bc-129">使用する、[!INCLUDE[addadapterservreflong](../../includes/addadapterservreflong-md.md)]または SAP システムから受信する Rfc を WCF サービス コントラクトを生成する ServiceModel メタデータ ユーティリティ ツール (svcutil.exe)。</span><span class="sxs-lookup"><span data-stu-id="202bc-129">You use the [!INCLUDE[addadapterservreflong](../../includes/addadapterservreflong-md.md)] or the ServiceModel Metadata Utility Tool (svcutil.exe) to generate a WCF service contract for the RFCs that you want to receive from the SAP system.</span></span> <span data-ttu-id="202bc-130">次のセクションでは、マネージ コード クラスと Z_RFC_MKD_ADD 操作用に生成するインターフェイスを示します。</span><span class="sxs-lookup"><span data-stu-id="202bc-130">The following sections show the managed code classes and interfaces generated for the Z_RFC_MKD_ADD operation.</span></span>  
  
### <a name="the-rfc-interface-wcf-service-contract"></a><span data-ttu-id="202bc-131">Rfc インターフェイス (WCF サービス コントラクト)</span><span class="sxs-lookup"><span data-stu-id="202bc-131">The Rfc Interface (WCF service contract)</span></span>  
 <span data-ttu-id="202bc-132">[!INCLUDE[adaptersap_short](../../includes/adaptersap-short-md.md)] "Rfc"、1 つのサービス契約の RFC 操作をすべて明らかになります。</span><span class="sxs-lookup"><span data-stu-id="202bc-132">The [!INCLUDE[adaptersap_short](../../includes/adaptersap-short-md.md)] surfaces all RFC operations under a single service contract, "Rfc".</span></span> <span data-ttu-id="202bc-133">つまり、1 つのインターフェイス**Rfc**のすべての受信する RFC 操作が作成されます。</span><span class="sxs-lookup"><span data-stu-id="202bc-133">This means that a single interface, **Rfc**, is created for all of the RFC operations that you want to receive.</span></span> <span data-ttu-id="202bc-134">RFC 操作の各ターゲットは、このインターフェイスのメソッドとして表されます。</span><span class="sxs-lookup"><span data-stu-id="202bc-134">Each target RFC operation is represented as a method of this interface.</span></span> <span data-ttu-id="202bc-135">各メソッドは、操作の要求メッセージのメッセージ コントラクトを表し、操作の応答メッセージのメッセージ コントラクトを表すオブジェクトを返しますが、1 つのパラメーターを受け取ります。</span><span class="sxs-lookup"><span data-stu-id="202bc-135">Each method takes a single parameter, which represents the message contract for the request message of the operation, and returns an object, which represents the message contract of the response message of the operation.</span></span>  
  
```  
[System.CodeDom.Compiler.GeneratedCodeAttribute("System.ServiceModel", "3.0.0.0")]  
[System.ServiceModel.ServiceContractAttribute(Namespace="http://Microsoft.LobServices.Sap/2007/03/", ConfigurationName="Rfc")]  
public interface Rfc {  
  
    // CODEGEN: Generating message contract since the wrapper namespace (http://Microsoft.LobServices.Sap/2007/03/Rfc/) of message Z_RFC_MKD_ADDRequest does not match the default value (http://Microsoft.LobServices.Sap/2007/03/)  
    [System.ServiceModel.OperationContractAttribute(Action="http://Microsoft.LobServices.Sap/2007/03/Rfc/Z_RFC_MKD_ADD", ReplyAction="http://Microsoft.LobServices.Sap/2007/03/Rfc/Z_RFC_MKD_ADD/response")]  
    Z_RFC_MKD_ADDResponse Z_RFC_MKD_ADD(Z_RFC_MKD_ADDRequest request);  
}  
  
```  
  
### <a name="the-request-and-response-messages"></a><span data-ttu-id="202bc-136">要求と応答メッセージ</span><span class="sxs-lookup"><span data-stu-id="202bc-136">The Request and Response Messages</span></span>  
 <span data-ttu-id="202bc-137">RFC の各操作は、要求メッセージを表し、応答メッセージを表すオブジェクトを返しますパラメーターを受け取ります。</span><span class="sxs-lookup"><span data-stu-id="202bc-137">Each RFC operation takes a parameter that represents the request message and returns an object that represents the response message.</span></span> <span data-ttu-id="202bc-138">要求メッセージのプロパティには、インポートおよび RFC の (入力) 変更するパラメーターが含まれます。</span><span class="sxs-lookup"><span data-stu-id="202bc-138">The properties of the request message contain the IMPORT and (input) CHANGING parameters of the RFC.</span></span> <span data-ttu-id="202bc-139">応答メッセージのプロパティは、エクスポートを含み、(出力) 操作のパラメーターを変更します。</span><span class="sxs-lookup"><span data-stu-id="202bc-139">The properties of the response message contain the EXPORT and (output) CHANGING parameters for the operation.</span></span>  
  
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
  
### <a name="the-generated-wcf-service"></a><span data-ttu-id="202bc-140">生成された WCF サービス</span><span class="sxs-lookup"><span data-stu-id="202bc-140">The Generated WCF Service</span></span>  
 <span data-ttu-id="202bc-141">[!INCLUDE[addadapterservrefshort](../../includes/addadapterservrefshort-md.md)] WCF サービス コントラクトを実装する WCF サービスも生成されます (**Rfc**)。</span><span class="sxs-lookup"><span data-stu-id="202bc-141">The [!INCLUDE[addadapterservrefshort](../../includes/addadapterservrefshort-md.md)] also generates a WCF service that implements the WCF service contract (**Rfc**).</span></span> <span data-ttu-id="202bc-142">このクラスのメソッドがスタブとして作成されました。</span><span class="sxs-lookup"><span data-stu-id="202bc-142">The methods of this class are stubbed.</span></span> <span data-ttu-id="202bc-143">このクラスは、別のファイルに生成されます。</span><span class="sxs-lookup"><span data-stu-id="202bc-143">This class is generated in a separate file.</span></span> <span data-ttu-id="202bc-144">このクラスのメソッドに直接コードを実装できます。</span><span class="sxs-lookup"><span data-stu-id="202bc-144">You can implement your code directly in the methods of this class.</span></span>  
  
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
  
## <a name="how-to-create-an-rfc-server-application"></a><span data-ttu-id="202bc-145">RFC サーバー アプリケーションを作成する方法</span><span class="sxs-lookup"><span data-stu-id="202bc-145">How to Create an RFC Server Application</span></span>  
 <span data-ttu-id="202bc-146">Rfc を WCF サービス モデルを使用して SAP システムから受信するには」の手順に従ってできます[SAP アダプターを使用した WCF サービス モデルの概要](../../adapters-and-accelerators/adapter-sap/overview-of-the-wcf-service-model-with-the-sap-adapter.md)します。</span><span class="sxs-lookup"><span data-stu-id="202bc-146">To receive RFCs from the SAP system by using the WCF service model, you can follow the steps in [Overview of the WCF Service Model with the SAP Adapter](../../adapters-and-accelerators/adapter-sap/overview-of-the-wcf-service-model-with-the-sap-adapter.md).</span></span> <span data-ttu-id="202bc-147">必ずサービス エンドポイント (プロシージャを作成および WCF サービスを実装するための手順 6) を追加するときに、サービス コントラクトの 'Rfc' を指定してください。</span><span class="sxs-lookup"><span data-stu-id="202bc-147">Be sure to specify 'Rfc' for the service contract when you add the service endpoint (step 6 of the procedure for creating and implementing a WCF service).</span></span>  
  
 <span data-ttu-id="202bc-148">次のコードを使用して、SAP システムから、Z_RFC_MKD_RFC を受信する方法の完全な例を示しています、[!INCLUDE[adaptersap_short](../../includes/adaptersap-short-md.md)]します。</span><span class="sxs-lookup"><span data-stu-id="202bc-148">The following code shows a complete example of how to receive the Z_RFC_MKD_RFC from an SAP system by using the [!INCLUDE[adaptersap_short](../../includes/adaptersap-short-md.md)].</span></span> <span data-ttu-id="202bc-149">この RFC は、2 つの整数パラメーターを受け取り、SAP システムに結果を返します。</span><span class="sxs-lookup"><span data-stu-id="202bc-149">This RFC takes two integer parameters and returns the result to the SAP system.</span></span>  
  
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
  
## <a name="see-also"></a><span data-ttu-id="202bc-150">参照</span><span class="sxs-lookup"><span data-stu-id="202bc-150">See Also</span></span>  
<span data-ttu-id="202bc-151">[WCF サービス モデルを使用してアプリケーションを開発します。](../../adapters-and-accelerators/adapter-sap/develop-sap-applications-using-the-wcf-service-model.md) </span><span class="sxs-lookup"><span data-stu-id="202bc-151">[Develop applications using the WCF Service Model](../../adapters-and-accelerators/adapter-sap/develop-sap-applications-using-the-wcf-service-model.md) </span></span>  
 [<span data-ttu-id="202bc-152">RFC 操作のメッセージ スキーマ</span><span class="sxs-lookup"><span data-stu-id="202bc-152">Message Schemas for RFC Operations</span></span>](../../adapters-and-accelerators/adapter-sap/message-schemas-for-rfc-operations.md)