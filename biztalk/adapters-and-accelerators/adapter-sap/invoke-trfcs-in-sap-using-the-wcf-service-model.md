---
title: "WCF サービス モデルを使用して SAP で tRFCs を呼び出す |Microsoft ドキュメント"
ms.custom: 
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: 
ms.suite: 
ms.tgt_pltfrm: 
ms.topic: article
helpviewer_keywords:
- tRFCs, invoking by using the WCF service model
- WCF service model, invoking tRFCs
ms.assetid: 456fa869-2f1a-42e0-adbf-86bfe0876846
caps.latest.revision: "6"
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: 5f23ee3e863318c9d75be9136e7b7fc0fa37b921
ms.sourcegitcommit: cb908c540d8f1a692d01dc8f313e16cb4b4e696d
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 09/20/2017
---
# <a name="invoke-trfcs-in-sap-using-the-wcf-service-model"></a>WCF サービス モデルを使用して SAP で tRFCs を呼び出す
トランザクション リモート関数呼び出し (tRFCs) 保証、*ワンタイム*SAP システムの RFC を実行します。 いずれかの側に表示される、Rfc を呼び出すことができます、 [!INCLUDE[adaptersap_short](../../includes/adaptersap-short-md.md)] tRFC として。 WCF サービス モデルで tRFC の呼び出しは、違いは次の RFC の呼び出しと似ています。  
  
-   [!INCLUDE[adaptersap_short](../../includes/adaptersap-short-md.md)]別のノード (TRFC) の Rfc (RFC) よりも下にある tRFCs を表示します。  
  
-   tRFC クライアント呼び出しでは、SAP のエクスポートおよびパラメーターを変更するための値は返されません。  
  
-   tRFC 操作にはによって tRFC の SAP トランザクション ID (TID) にマップされている GUID パラメーターが含まれて、[!INCLUDE[adaptersap_short](../../includes/adaptersap-short-md.md)]です。  
  
-   TRFC の呼び出し後に呼び出す RfcConfirmTransID 操作 (コミット)、SAP システムで tRFC を確認する必要があります。 この操作は TRFC ノードの直下に確認できます。  
  
 TRFC 操作および RfcConfirmTransID 操作に関する詳細については、次を参照してください。 [SAP で tRFCs に対する操作](../../adapters-and-accelerators/adapter-sap/operations-on-trfcs-in-sap.md)です。  
  
 以降のセクションを使用して SAP システムで tRFCs を呼び出す方法を表示、[!INCLUDE[adaptersap_short](../../includes/adaptersap-short-md.md)]です。  
  
## <a name="the-wcf-client-class"></a>WCF クライアント クラス  
 [!INCLUDE[adaptersap_short](../../includes/adaptersap-short-md.md)] "Trfc"、1 つのサービス コントラクトでのすべての tRFC 操作を表示します。 つまり、1 つの WCF クライアント クラス**TrfcClient**のすべての呼び出し先 tRFC 操作が作成されます。 各ターゲット tRFC は、このクラスのメソッドとして表されます。 それぞれの方法。  
  
-   構造体など、SAP の複合型は、SAP の種類のフィールドに対応するプロパティを持つ .NET クラスとして表示されます。 これらのクラスは、次の名前空間で定義されます: **microsoft.lobservices.sap._2007._03.Types.Rfc**です。  
  
 次のコードの一部を示しています、 **TrfcClient**クラスと、SAP システムに対する BAPI_SALESORDER_CREATEFROMDAT2 (として、tRFC) を呼び出すメソッド。 **TransactionalRfcOperationIdentifier**パラメーターには、SAP TID にマップされている GUID が含まれています。 すべてのメソッドにパラメーターが表示されます。  
  
```  
[System.Diagnostics.DebuggerStepThroughAttribute()]  
[System.CodeDom.Compiler.GeneratedCodeAttribute("System.ServiceModel", "3.0.0.0")]  
public partial class TrfcClient : System.ServiceModel.ClientBase<Trfc>, Trfc {  
  
    ....  
  
    /// <summary>The Metadata for this RFC was generated using the RFC SDK.</summary>  
    public void BAPI_SALESORDER_CREATEFROMDAT2(  
                string BEHAVE_WHEN_ERROR,   
                string BINARY_RELATIONSHIPTYPE,   
                string CONVERT,   
                string INT_NUMBER_ASSIGNMENT,   
                microsoft.lobservices.sap._2007._03.Types.Rfc.BAPISDLS LOGIC_SWITCH,   
                microsoft.lobservices.sap._2007._03.Types.Rfc.BAPISDHD1 ORDER_HEADER_IN,   
  
                …  
  
               microsoft.lobservices.sap._2007._03.Types.Rfc.BAPIADDR1[] PARTNERADDRESSES,   
                microsoft.lobservices.sap._2007._03.Types.Rfc.BAPIRET2[] RETURN,   
                ref System.Guid TransactionalRfcOperationIdentifier) { ...  }  
}  
```  
  
 次のコードでは、RfcConfirmTransID 操作用に生成される方法を示します。 このメソッドがの一部として生成されることを確認する必要があります、 **TrfcClient**です。 RfcConfirmTransID 操作は TRFC ノードの直下に確認できます。  
  
```  
public void RfcConfirmTransID(System.Guid TransactionalRfcOperationIdentifier) {…}  
```  
  
## <a name="how-to-create-a-trfc-client-application"></a>TRFC クライアント アプリケーションを作成する方法  
 TRFCs を起動するアプリケーションを作成する手順は、手順と同様、次の例外を除き、Rfc を呼び出すために従います。  
  
-   TRFC ノード ターゲットの操作を取得する必要があります。  
  
-   RfcConfirmTransID 操作を取得する必要があります。 これは、TRFC ノードの直下に確認できます。  
  
-   (コミット) は、SAP システムに対して tRFC 操作を確認するには、その tRFC 操作の返された GUID を持つ RfcConfirmTransID 操作を呼び出す必要があります。  
  
#### <a name="to-create-a-trfc-client-application"></a>TRFC クライアント アプリケーションを作成するには  
  
1.  生成、 **TrfcClient**クラスです。 使用して、 [!INCLUDE[addadapterservreflong](../../includes/addadapterservreflong-md.md)] 、ServiceModel メタデータ ユーティリティ ツール (svcutil.exe) を生成するか、 **TrfcClient**を操作する Rfc を対象とするクラス。 WCF クライアントを生成する方法の詳細については、次を参照してください。 [WCF クライアントまたは SAP ソリューションの成果物の WCF サービス コントラクトを生成](../../adapters-and-accelerators/adapter-sap/generate-a-wcf-client-or-a-wcf-service-contract-for-sap-solution-artifacts.md)です。 RfcConfirmTransID 操作が含まれており、 **TrfcClient**クラスです。  
  
2.  インスタンスを作成、 **TrfcClient**クラスは、手順 1. で生成され、クライアントのバインディングを指定します。 バインドとエンドポイント アドレスを指定することは、クライアントのバインディングを指定する、 **TrfcClient**が使用されます。 これは、コードで命令として記述または構成で宣言によって行うことができます。 クライアントのバインディングを指定する方法の詳細については、次を参照してください。 [、SAP システムのクライアントのバインディングを構成する](../../adapters-and-accelerators/adapter-sap/configure-a-client-binding-for-the-sap-system.md)です。 次のコードを初期化します、 **TrfcClient**からの構成と、SAP システムの資格情報を設定します。  
  
    ```  
    TrfcClient trfcClient = new TrfcClient("SAPBinding_Rfc");  
  
    trfcClient.ClientCredentials.UserName.UserName = "YourUserName";  
    trfcClient.ClientCredentials.UserName.Password = "YourPassword";  
    ```  
  
3.  開く、 **TrfcClient**です。  
  
    ```  
    trfcClient.Open();  
    ```  
  
4.  に対して、適切なメソッドを呼び出す、 **TrfcClient**を SAP システムでターゲット tRFC を呼び出す 2 の手順で作成します。 GUID を格納しているか、空の GUID を含む変数を渡すことができます、 **TransactionalRrcOperationIdentifier**パラメーター。 空の GUID を渡す場合、[!INCLUDE[adaptersap_short](../../includes/adaptersap-short-md.md)]のいずれかが生成されます。 次のコードは、(すべてのパラメーターをメソッドには表示)、SAP システムで tRFC として BAPI_SALESORDER_CREATEFROMDAT2 を呼び出します。 GUID を指定します。  
  
    ```  
    transactionalRfcOperationIdentifier = Guid.NewGuid();  
  
    //invoke RFC_CUSTOMER_GET as a tRFC  
    trfcClient.BAPI_SALESORDER_CREATEFROMDAT2(  
                                    request.BEHAVE_WHEN_ERROR,  
                                    request.BINARY_RELATIONSHIPTYPE,  
                                    request.CONVERT,  
  
                                    ...  
  
                                    ref transactionalRfcOperationIdentifier);  
    ```  
  
5.  SAP システムで tRFC に関連付けられている TID を確認する呼び出し、 **RfcConfirmTransID**メソッドを**TrfcClient**です。 手順 4 で返される GUID を指定して、 **TransactionRfcOperationIdentifier**パラメーター。  
  
    ```  
    trfcClient.RfcConfirmTransID(transactionalRfcOperationIdentifier);  
    ```  
  
6.  閉じる、 **TrfcClient**したら (したらすべて tRFCs の呼び出し) を使用しています。  
  
    ```  
    trfcClient.Close();   
    ```  
  
### <a name="example"></a>例  
 次の例として、tRFC BAPI_SALESORDER_CREATE を呼び出す方法を示します。  
  
```  
using System;  
using System.Collections.Generic;  
using System.Text;  
  
// Add WCF, the WCF LOB Adapter SDK, and SAP adapter namepaces  
using System.ServiceModel;  
using Microsoft.Adapters.SAP;  
using Microsoft.ServiceModel.Channels;  
  
// Include this namespace for WCF LOB Adapter SDK and SAP exceptions  
using Microsoft.ServiceModel.Channels.Common;  
  
using microsoft.lobservices.sap._2007._03.Types.Rfc;  
  
// This example demonstrates sending BAPI_SALESORDER_CREATEFROMDAT2 as a tRFC. The client has   
// methods to:  
//      send the BAPI (BAPI_SALESORDER_CREATEFROMDAT2)and to  
//      Confirm the transaction (RfcConfirmTransID)  
// An instance of BAPI_SALESORDER_CREATEFROMDAT2Request (generated)   
// is used to format the BAPI before invoking BAPI_SALESORDER_CREATEFROMDAT2. This   
// is not necessary, but is done to make it easier to read the code.  
// tRFC invocations always includes a ref parameter that contains a GUID. You can optionally   
// set this parameter when you invoke the method; however, you must use the value returned by  
// the adapter when you call RfcConfirmTransID to confirm the transaction on the SAP system.   
// You can call the utility method, SAPAdapterUtilities.ConvertGuidToTid, to get the value  
// of the SAP transaction Id from the GUID that the adapter returns.  
namespace SapTrfcClientSM  
{  
    class Program  
    {  
        static void Main(string[] args)  
        {  
            TrfcClient sapTrfcClient = null;  
  
            try  
            {  
                Console.WriteLine("SAP TRFC client sample started");  
                Console.WriteLine("Creating the TRFC client");  
                // Create the SAP Trfc Client from configuration  
                sapTrfcClient = new TrfcClient("SAPBinding_Trfc");  
                sapTrfcClient.ClientCredentials.UserName.UserName = "YourUserName";  
                sapTrfcClient.ClientCredentials.UserName.Password = "YourPassword";  
  
                Console.WriteLine("Opening the TRFC client");  
                // Open the Trfc Client  
                sapTrfcClient.Open();  
  
                // Create a GUID -- note: this is optional. If you do not pass a GUID,  
                // for the TransactionalRfcOperationIdentifier parameter, the SAP adapter will   
                // generate one, associate it with the SAP TID, and set the   
                // TransactionalRfcOperationIdentifier parameter.  
                Guid tidGuid = Guid.NewGuid();  
  
                BAPI_SALESORDER_CREATEFROMDAT2Request request = new BAPI_SALESORDER_CREATEFROMDAT2Request();  
  
                request.ORDER_HEADER_IN = new BAPISDHD1();  
                request.ORDER_HEADER_IN.DOC_TYPE = "TA";  
                request.ORDER_HEADER_IN.SALES_ORG = "1000";  
                request.ORDER_HEADER_IN.DISTR_CHAN = "10";  
                request.ORDER_HEADER_IN.DIVISION = "00";  
                request.ORDER_HEADER_IN.SALES_OFF = "1000";  
                request.ORDER_HEADER_IN.REQ_DATE_H = DateTime.Now;  
                request.ORDER_HEADER_IN.PURCH_DATE = DateTime.Now;  
                request.ORDER_HEADER_IN.PURCH_NO_C = "Cust PO";  
                request.ORDER_HEADER_IN.CURRENCY = "EUR";  
  
                BAPISDITM[] orderItems = new BAPISDITM[1];  
                orderItems[0] = new BAPISDITM();  
                orderItems[0].MATERIAL = "P-109";  
                orderItems[0].PLANT = "1000";  
                orderItems[0].TARGET_QU = "ST";  
                request.ORDER_ITEMS_IN = orderItems;  
  
                BAPIPARNR[] orderPartners = new BAPIPARNR[1];  
                orderPartners[0] = new microsoft.lobservices.sap._2007._03.Types.Rfc.BAPIPARNR();  
                orderPartners[0].PARTN_ROLE = "AG";  
                orderPartners[0].PARTN_NUMB = "0000001390";  
                request.ORDER_PARTNERS = orderPartners;  
  
                // Create a GUID -- note: this is optional. If you do not pass a GUID,  
                // for the TransactionalRfcOperationIdentifier parameter, the SAP adapter will   
                // generate one, associate it with the SAP TID, and set the   
                // TransactionalRfcOperationIdentifier parameter.  
                request.TransactionalRfcOperationIdentifier = Guid.NewGuid();  
  
                Console.WriteLine("Invoking BAPI_SALESORDER_CREATEFROMDAT2 as a tRFC");  
  
                //invoke RFC_CUSTOMER_GET as a tRFC  
                sapTrfcClient.BAPI_SALESORDER_CREATEFROMDAT2(request.BEHAVE_WHEN_ERROR,  
                                                                request.BINARY_RELATIONSHIPTYPE,  
                                                                request.CONVERT,  
                                                                request.INT_NUMBER_ASSIGNMENT,  
                                                                request.LOGIC_SWITCH,  
                                                                request.ORDER_HEADER_IN,  
                                                                request.ORDER_HEADER_INX,  
                                                                request.SALESDOCUMENTIN,  
                                                                request.SENDER,  
                                                                request.TESTRUN,  
                                                                request.EXTENSIONIN,  
                                                                request.ORDER_CCARD,  
                                                                request.ORDER_CFGS_BLOB,  
                                                                request.ORDER_CFGS_INST,  
                                                                request.ORDER_CFGS_PART_OF,  
                                                                request.ORDER_CFGS_REF,  
                                                                request.ORDER_CFGS_REFINST,  
                                                                request.ORDER_CFGS_VALUE,  
                                                                request.ORDER_CFGS_VK,  
                                                                request.ORDER_CONDITIONS_IN,  
                                                                request.ORDER_CONDITIONS_INX,  
                                                                request.ORDER_ITEMS_IN,  
                                                                request.ORDER_ITEMS_INX,  
                                                                request.ORDER_KEYS,  
                                                                request.ORDER_PARTNERS,  
                                                                request.ORDER_SCHEDULES_IN,  
                                                                request.ORDER_SCHEDULES_INX,  
                                                                request.ORDER_TEXT,  
                                                                request.PARTNERADDRESSES,  
                                                                request.RETURN,  
                                                                ref request.TransactionalRfcOperationIdentifier);  
  
                string sapTxId = null;  
                sapTxId = SAPAdapterUtilities.ConvertGuidToTid(request.TransactionalRfcOperationIdentifier);  
  
                Console.WriteLine("BAPI_SALESORDER_CREATEFROMDAT2 Sent");  
                Console.WriteLine("The SAP Transaction Id is " + sapTxId);  
  
                // Invoke the RfcConfirmTransID method to confirm (commit) the transaction on  
                // the SAP system. This step is required to complete the transaction. The SAP  
                // adapter will always return a TranactionalRfcOperationIdentifier, whether   
                // one was supplied in the call or not.  
                sapTrfcClient.RfcConfirmTransID(request.TransactionalRfcOperationIdentifier);  
  
                Console.WriteLine("SAP Transaction {0} has been committed", sapTxId);  
  
                Console.WriteLine("\nHit <RETURN> to end");  
                Console.ReadLine();  
  
            }  
            catch (ConnectionException cex)  
            {  
                Console.WriteLine("Exception occurred connecting to the SAP system");  
                Console.WriteLine(cex.InnerException.Message);  
                throw;  
            }  
            catch (Exception ex)  
            {  
                Console.WriteLine("Exception is: " + ex.Message);  
                if (ex.InnerException != null)  
                {  
                    Console.WriteLine("Inner Exception is: " + ex.InnerException.Message);  
                }  
                throw;  
            }  
            finally  
            {  
                // Close the client  
                if (sapTrfcClient != null)  
                {  
                    if (sapTrfcClient.State == CommunicationState.Opened)  
                        sapTrfcClient.Close();  
                    else  
                        sapTrfcClient.Abort();  
                }  
            }  
  
        }  
    }  
}  
```  
  
## <a name="see-also"></a>参照  
[WCF サービス モデルを使用してアプリケーションを開発します。](../../adapters-and-accelerators/adapter-sap/develop-sap-applications-using-the-wcf-service-model.md)   
 [SAP の tRFCs に対する操作](../../adapters-and-accelerators/adapter-sap/operations-on-trfcs-in-sap.md)