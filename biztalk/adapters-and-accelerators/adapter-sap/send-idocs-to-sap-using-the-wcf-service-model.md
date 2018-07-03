---
title: WCF サービス モデルを使用して sap の Idoc の送信 |Microsoft Docs
ms.custom: ''
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: ''
ms.suite: ''
ms.tgt_pltfrm: ''
ms.topic: article
helpviewer_keywords:
- WCF service model, sending IDOCs to SAP
- IDOCs, sending to SAP by using the WCF service model
ms.assetid: 84077234-b82b-4e88-b858-ce2cb1383fb4
caps.latest.revision: 5
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: 7efff52b335acb9ab1835bdecf38caf8d0e67e71
ms.sourcegitcommit: 266308ec5c6a9d8d80ff298ee6051b4843c5d626
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 06/27/2018
ms.locfileid: "36988227"
---
# <a name="send-idocs-to-sap-using-the-wcf-service-model"></a>WCF サービス モデルを使用して sap の Idoc を送信します。
内部的には、[!INCLUDE[adaptersap](../../includes/adaptersap-md.md)]次の 2 つの Rfc のいずれかを呼び出すことによって、SAP システムに Idoc を送信します。  
  
- Idoc のバージョン 3 の IDOC_INBOUND_ASYNCHRONOUS します。  
  
- Idoc のバージョン 2 の INBOUND_IDOC_PROCESS します。  
  
  適切な RFC、tRFC); を呼び出すことによって、アダプターに IDOC を送信することができます。ただし、アダプターに Idoc を送信するのに次の 2 つの操作を使用することもできます。  
  
- **SendIdoc** IDOC のルート ノードのすぐ下に表示されます。 SendIdoc 操作は、IDOC を送信します (弱い型指定の) データを文字列として、[!INCLUDE[adaptersap_short](../../includes/adaptersap-short-md.md)]します。  
  
- **送信**idoc ごとに個別に表示されます。 送信操作を厳密に型指定されたデータとしての IDOC の送信、[!INCLUDE[adaptersap_short](../../includes/adaptersap-short-md.md)]します。  
  
  これらの操作がアダプターに IDOC データを送信する方法を調べる方法に送信されません SAP システム。 アダプターは常に、適切な tRFC を使用して、SAP システムに IDOC を送信します。  
  
  [!INCLUDE[adaptersap_short](../../includes/adaptersap-short-md.md)] IDOC を送信、tRFC、として SendIdoc と送信の両方の操作が (コミット) IDOC を確認するために使用する GUID パラメーターを公開します。 [!INCLUDE[adaptersap_short](../../includes/adaptersap-short-md.md)]この SAP トランザクション ID (TID)、tRFC に関連付けられている GUID を内部的にマップします。 2 つの方法のいずれかで IDOC を確認できます。  
  
- 使用して、 **AutoConfirmSentIdocs**プロパティをバインドします。 このバインドのプロパティ設定されている場合**true**アダプターが自動的に IDOC を送信するために使用する tRFC を確認します。  
  
- RfcConfirmTransID を呼び出しています。 IDOC に関連付けられている GUID を持つには、この操作を呼び出します。  
  
  次のセクションでは、SendIdoc と送信操作を使用して、SAP システムに Idoc を送信する方法を説明します。 として、tRFC IDOC を送信するための詳細については、次を参照してください。 [WCF サービス モデルを使用して SAP の Trfc を呼び出す](../../adapters-and-accelerators/adapter-sap/invoke-trfcs-in-sap-using-the-wcf-service-model.md)します。  
  
## <a name="the-wcf-client-class"></a>WCF クライアント クラス  
  
### <a name="the-sendidoc-operation"></a>SendIdoc 操作  
 [!INCLUDE[adaptersap_short](../../includes/adaptersap-short-md.md)]サーフェスの文字列形式で IDOC を送信する 1 つの操作 (およびサービス コントラクト)。 サービス コントラクトの名前は"Idoc"と、WCF クライアント クラスが**IdocClient**します。  
  
 このクライアントを使用して、sap の IDOC を送信できます。 1 つのメソッドが含まれている**SendIdoc**、2 つのパラメーターを受け取る。  
  
- **idocData** IDOC データを格納した文字列です  
  
- **guid**は SAP TID にマップされている GUID です。  
  
  次のコードは、SendIdoc 操作に対して生成される WCF クライアントを示しています。  
  
```  
[System.Diagnostics.DebuggerStepThroughAttribute()]  
[System.CodeDom.Compiler.GeneratedCodeAttribute("System.ServiceModel", "3.0.0.0")]  
public partial class IdocClient : System.ServiceModel.ClientBase<Idoc>, Idoc {  
  
    public void SendIdoc(string idocData, ref System.Nullable\<System.Guid\> guid) {…}  
}  
```  
  
### <a name="the-send-operation"></a>送信操作  
 送信操作は、厳密に型指定されたデータを使用するため、 [!INCLUDE[adaptersap_short](../../includes/adaptersap-short-md.md)] IDOC ごとの一意のサービス コントラクトを明らかになります。 インターフェイス (および、WCF クライアント クラス) の名前は、このコントラクトが IDOC の種類、バージョン、リリース番号、および (該当する場合)、CIM 型に基づいて生成されます。 たとえば、WCF クライアント クラスは、"IdocORDERS03V3R620"が、インターフェイス、ORDERS03.v3.620 IDOC のという名前が**IdocORDERS03V3R620Client**します。  
  
 IDOC の種類ごとの一意のクライアントを生成する必要があります。 このクライアントには、1 つのメソッドが含まれています。**送信**、2 つのパラメーターを受け取る。  
  
- **idocData** IDOC の厳密に型指定されたデータを表すクラスです。  
  
- **guid** SAP TID にマップされている GUID の文字列表現です。  
  
  次のコードでは、表面化 ORDERS03.v3.620 IDOC の送信操作に対して生成される WCF クライアントを示します。  
  
```  
[System.Diagnostics.DebuggerStepThroughAttribute()]  
[System.CodeDom.Compiler.GeneratedCodeAttribute("System.ServiceModel", "3.0.0.0")]  
public partial class IdocORDERS03V3R620Client : System.ServiceModel.ClientBase<IdocORDERS03V3R620>, IdocORDERS03V3R620 {  
  
    ...  
  
    public void Send(ORDERS03 idocData, ref string guid) { ... }  
}  
```  
  
## <a name="how-to-create-an-application-to-send-idocs"></a>Idoc を送信するアプリケーションを作成する方法  
 IDOC を SAP システムに送信するには、次の手順を実行します。  
  
#### <a name="to-send-an-idoc-to-an-sap-system"></a>IDOC を SAP システムに送信するには  
  
1. WCF クライアント クラスを生成します。 使用して、[!INCLUDE[addadapterservreflong](../../includes/addadapterservreflong-md.md)]または ServiceModel メタデータ ユーティリティ ツール (svcutil.exe) で WCF クライアント クラスを生成する作業する Idoc を対象とします。 WCF クライアントを生成する方法の詳細については、次を参照してください。 [SAP ソリューションの成果物の WCF クライアントまたは WCF サービス コントラクトを生成する](../../adapters-and-accelerators/adapter-sap/generate-a-wcf-client-or-a-wcf-service-contract-for-sap-solution-artifacts.md)します。 Idoc を明示的に確認する場合は、RfcConfirmTransID 操作用の WCF クライアントを生成することを確認します。 操作は、次のノードの下ではあります。  
  
   -   SendIdoc 操作です。 直下の IDOC のノードです。  
  
   -   送信操作です。 ターゲットの IDOC の種類、バージョンおよびリリースの番号に対応するノード。  
  
   -   RfcConfirmTransID 操作です。 直接 TRFC ノード。  
  
2. 手順 1 で生成された WCF クライアント クラスのインスタンスを作成し、クライアントのバインディングを指定します。 クライアントのバインディングを指定するには、バインドと WCF クライアントを使用するエンドポイント アドレスを指定する必要があります。 コードで強制的に、または構成で宣言的に、これを行うことができます。 クライアントのバインディングを指定する方法の詳細については、次を参照してください。 [SAP システムのクライアントのバインディングを構成する](../../adapters-and-accelerators/adapter-sap/configure-a-client-binding-for-the-sap-system.md)します。 次のコードでは、構成からには、(送信操作) の IdocClient を初期化し、SAP システムの資格情報を設定します。  
  
   ```  
   SAPBinding binding = new SAPBinding();  
  
   // Set endpoint address  
   EndpointAddress endpointAddress = new EndpointAddress("sap://CLIENT=800;LANG=EN;@a/YourSAPHost/00?RfcSdkTrace=False&AbapDebug=False&UseSapGui=Without");  
  
   // Create client and set credentials  
   idocClient = new IdocClient(binding, endpointAddress);  
   idocClient.ClientCredentials.UserName.UserName = "YourUserName";  
   idocClient.ClientCredentials.UserName.Password = "YourPassword";;  
   ```  
  
3. IDOC を送信アダプターは、tRFC 後に SAP システムを確認する場合は、設定、 **AutoConfirmSentIdocs**プロパティをバインド**true**します。 WCF クライアントを開く前に、これを行う必要があります。  
  
   ```  
   // Set AutoConfirmSentIdocs property to true  
   binding.AutoConfirmSentIdocs = true;  
   ```  
  
4. WCF クライアントを開きます。  
  
   ```  
   idocClient.Open();  
   ```  
  
5. 手順 2 で作成した IDOC を SAP システムに送信する WCF クライアントの適切なメソッドを呼び出します。 GUID を格納しているかに設定されている変数を渡すことができます**null**の**guid**パラメーター。 GUID を指定しない場合、[!INCLUDE[adaptersap_short](../../includes/adaptersap-short-md.md)]操作のいずれかが生成されます (**guid**は、 **ref**パラメーター)。 次のコードでは、ファイルから文字列の形式で IDOC を読み取るし、SendIdoc 操作を使用して、SAP システムに送信します。  
  
   ```  
   // Read IDOC into string variable  
   using (StreamReader reader = new StreamReader("ORDERS03.txt"))  
   {  
   idocData = reader.ReadToEnd();  
   }  
  
   //Get a new GUID to pass to SendIdoc. You can also assign a null  
   //value to have the adapter generate a GUID.  
   adapterTxGuid = Guid.NewGuid();  
  
   //Invoke SendIdoc on the client to send the IDOC to the SAP system  
   idocClient.SendIdoc(idocData, ref adapterTxGuid);  
   ```  
  
6. 設定しなかった場合、 **AutoConfirmSentIdocs**バインドのプロパティを**true** (手順 3) でしを確認してください、SAP システムで tRFC します。 呼び出す必要がありますこれを行う、 **RfcConfirmTransID**メソッドを**TrfcClient** (作成時に表示されません)。 パラメーターには、手順 4. で返される GUID を指定します。  
  
   ```  
   trfcClient.RfcConfirmTransID(adapterTxGuid);  
   ```  
  
7. WCF クライアントを閉じる (および**TrfcClient**使用されている場合、) が終わったら (したら Idoc を送信する) を使用して。  
  
   ```  
   idocClient.Close();   
   ```  
  
### <a name="example"></a>例  
 次の例は、SendIdoc メソッドを使用して IDOC を SAP システムに送信します。 IDOC は ORDERS03.txt ファイルから読み取られます。 このファイルには、ORDERS03 が含まれています。V3.620 IDOC; サンプルに含まれているとただし、SendIdoc 操作を使用して、任意の IDOC を送信することができます。  
  
```  
using System;  
using System.Collections.Generic;  
using System.Text;  
  
using System.IO;  
  
// Add WCF, WCF LOB Adapter SDK, and SAP adapter namepaces  
using System.ServiceModel;  
using Microsoft.Adapters.SAP;  
using Microsoft.ServiceModel.Channels;  
  
// Include this namespace for WCF LOB Adapter SDK and SAP exceptions  
using Microsoft.ServiceModel.Channels.Common;  
  
// This example sends a flat IDOC to the SAP system by using the SendIdoc operation.  
namespace SapIdocStringClientSM  
{  
    class Program  
    {  
        static void Main(string[] args)  
        {  
            // variable for the IDOC client  
            IdocClient idocClient = null;  
  
            Console.WriteLine("IDOC string client sample started");  
            try  
            {  
                // Variable for the GUID  
                System.Nullable<System.Guid> adapterTxGuid;  
                // string to hold the Idoc data  
                string idocData;  
                // string to hold the SAP transaction ID (TID)  
                string sapTxId;  
  
                // The client can be configured from app.config, but it is   
                // explicitly configured here for demonstration.  
                // set AutoConfirmSentIdocs property to true  
                SAPBinding binding = new SAPBinding();  
                binding.AutoConfirmSentIdocs = true;  
  
                // Set endpoint address  
                EndpointAddress endpointAddress = new EndpointAddress("sap://CLIENT=800;LANG=EN;@a/YourSAPServer/00?RfcSdkTrace=False&AbapDebug=False&UseSapGui=Without");  
  
                // Create client and set credentials  
                idocClient = new IdocClient(binding, endpointAddress);  
                idocClient.ClientCredentials.UserName.UserName = "YourUserName";  
                idocClient.ClientCredentials.UserName.Password = "YourPassword";  
  
                // Open the client and send the Idoc  
                idocClient.Open();  
  
                // Read IDOC into string variable  
                using (StreamReader reader = new StreamReader("ORDERS03.txt"))  
                {  
                    idocData = reader.ReadToEnd();  
                }  
  
                //Get a new GUID to pass to SendIdoc. You can also assign a null.  
                //value to have the adapter generate a GUID.  
                adapterTxGuid = Guid.NewGuid();  
  
                //Invoke SendIdoc on the client to send the IDOC to the SAP system.  
                idocClient.SendIdoc(idocData, ref adapterTxGuid);  
  
                // The AutoConfirmSentIdocs binding property is set to true, so there is no need to  
                // confirm the IDOC. If this property is not set to true, you must call the   
                // RfcConfirmTransID method of a TrfcClient with adapterTxGuid to   
                // confirm the transaction on the SAP system.   
  
                // Get SAP tx id from GUID  
                sapTxId = SAPAdapterUtilities.ConvertGuidToTid((Guid) adapterTxGuid);  
  
                Console.WriteLine("IDOC sent");  
                Console.WriteLine("The SAP Transaction Id is : " + sapTxId);  
  
            catch (Exception ex)  
            {  
                Console.WriteLine("Exception is: " + ex.Message);  
                if (ex.InnerException != null)  
                {  
                    Console.WriteLine("Inner Exception is: " + ex.InnerException.Message);  
                }  
            }  
            finally  
            {  
                // Close the IDOC client  
                if (idocClient != null)  
                {  
                    if (idocClient.State == CommunicationState.Opened)  
                        idocClient.Close();  
                    else  
                        idocClient.Abort();  
                }  
            }  
  
        }  
    }  
}  
```  
  
## <a name="see-also"></a>参照  
[WCF サービス モデルを使用してアプリケーションを開発する](../../adapters-and-accelerators/adapter-sap/develop-sap-applications-using-the-wcf-service-model.md)