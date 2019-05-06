---
title: WCF サービス モデルを使用して SAP の Bapi を呼び出す |Microsoft Docs
ms.custom: ''
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: ''
ms.suite: ''
ms.tgt_pltfrm: ''
ms.topic: article
helpviewer_keywords:
- BAPIs, invoking by using the WCF service model
- WCF service model, invoking BAPIs
ms.assetid: be3c48d6-2213-4ae5-97f4-634fbc423022
caps.latest.revision: 8
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: b6f5cab88b0f672f9f09bdeb7795c0a58213f92f
ms.sourcegitcommit: 266308ec5c6a9d8d80ff298ee6051b4843c5d626
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 06/27/2018
ms.locfileid: "37002443"
---
# <a name="invoke-bapis-in-sap-using-the-wcf-service-model"></a>WCF サービス モデルを使用して SAP の Bapi を呼び出す
[!INCLUDE[adaptersap_short](../../includes/adaptersap-short-md.md)]として Bapi 明らかになります。  
  
- **RFC 操作**します。 [RFC] ノードに表示されますなどその他の任意の RFC、Bapi、[!INCLUDE[addadapterservrefshort](../../includes/addadapterservrefshort-md.md)]します。  
  
- **SAP ビジネス オブジェクトのメソッド**します。 BAPI ノードの下のビジネス オブジェクトによって表示される Bapi、ビジネス オブジェクトのメソッドとして、[!INCLUDE[addadapterservrefshort](../../includes/addadapterservrefshort-md.md)]します。  
  
  RFC 操作として、またはビジネス オブジェクト メソッドとして BAPI を呼び出すかどうか各 BAPI、常に、LUW で SAP システムの一部です。  
  
  方法の概要については[!INCLUDE[adaptersap_short](../../includes/adaptersap-short-md.md)]サポート Bapi を参照してください[SAP の Bapi に対する操作](../../adapters-and-accelerators/adapter-sap/operations-on-bapis-in-sap.md)します。  
  
  WCF サービス モデルを使用してビジネス オブジェクト メソッドとして Bapi を呼び出すと、各 SAP ビジネス オブジェクトは、WCF クライアント クラスで表されるし、そのビジネス オブジェクトの Bapi はクライアント上のメソッドとして表されます。 使用することができます、[!INCLUDE[addadapterservreflong](../../includes/addadapterservreflong-md.md)]をコードで呼び出す各 BAPI のメソッドを格納する、特定のビジネス オブジェクトの WCF クライアント クラスを生成します。 [!INCLUDE[addadapterservrefshort](../../includes/addadapterservrefshort-md.md)]も各 BAPI によって使用されているパラメーターおよびデータ型をカプセル化する .NET 型を生成します。 この WCF クライアント クラスのインスタンスを作成し、ターゲットの Bapi を呼び出すメソッドを呼び出すことができます。  
  
  次のセクションでは、ビジネス オブジェクトのメソッドとして Bapi を呼び出すし、WCF サービス モデルでの BAPI トランザクションのサポート方法について説明する方法を示します。  
  
## <a name="the-wcf-client-class"></a>WCF クライアント クラス  
 [!INCLUDE[adaptersap_short](../../includes/adaptersap-short-md.md)]さまざまなサービス コントラクトはビジネス オブジェクトごとに、明らかになります。 これは、各ビジネス オブジェクトの一意の WCF クライアント クラスが作成されたことを意味します。 このクラスの名前は、ビジネス オブジェクトの種類に基づきます。 たとえば、Sales Order ビジネス オブジェクト (ビジネス オブジェクト タイプ BUS2032) の WCF クライアント クラスは**BapiBUS2032Client**します。 ビジネス オブジェクト内の各ターゲット BAPI が生成された WCF クライアント クラスのメソッドとして表されます。 各メソッドには。  
  
- SAP のエクスポートのパラメーターとして表示されますが**アウト**パラメーター  
  
- として SAP 呼び出しのパラメーターが表示された**ref**パラメーター。  
  
- 構造体などの複雑な SAP 型は、SAP の種類のフィールドに対応するプロパティの .NET クラスとして表示されます。 これらのクラスは、次の名前空間で定義されている: microsoft.lobservices.sap._2007._03.Types.Rfc します。  
  
  BAPI_TRANSACTION_COMMIT と BAPI_TRANSACTION_ROLLBACK が各ビジネス オブジェクトの表示し、WCF クライアントでこれらを常に含める必要があります。  
  
  次のコードでは、販売注文のビジネス オブジェクトに対して生成された WCF クライアント クラスの一部を示します。 このクライアントには、メソッド呼び出す CREATEFROMDAT2、BAPI_TRANSACTION_COMMIT および BAPI_TRANSACTION_ROLLBACK にはが含まれています。 わかりやすくするためには、コンストラクターと他のコードを省略されています。  
  
```  
[System.Diagnostics.DebuggerStepThroughAttribute()]  
[System.CodeDom.Compiler.GeneratedCodeAttribute("System.ServiceModel", "3.0.0.0")]  
public partial class BapiBUS2032Client : System.ServiceModel.ClientBase<BapiBUS2032>, BapiBUS2032 {  
  
    // Code has been removed for clarity  
  
    /// <summary>The Metadata for this RFC was generated using the RFC SDK.</summary>  
    /// <param name="SALESDOCUMENT">Number of Generated Document</param>  
    /// <param name="BEHAVE_WHEN_ERROR">Error Handling</param>  
    /// …  
    /// <param name="ORDER_TEXT">Texts</param>  
    /// <param name="PARTNERADDRESSES">BAPI Reference Structure for Addresses (Org./Company)</param>  
    /// <param name="RETURN">Return Messages</param>  
    /// <returns></returns>  
    public string CREATEFROMDAT2(  
                string BEHAVE_WHEN_ERROR,   
                string BINARY_RELATIONSHIPTYPE,   
                string CONVERT,   
                string INT_NUMBER_ASSIGNMENT,   
                microsoft.lobservices.sap._2007._03.Types.Rfc.BAPISDLS LOGIC_SWITCH,   
                microsoft.lobservices.sap._2007._03.Types.Rfc.BAPISDHD1 ORDER_HEADER_IN,   
                microsoft.lobservices.sap._2007._03.Types.Rfc.BAPISDHD1X ORDER_HEADER_INX,   
                string SALESDOCUMENTIN,   
                microsoft.lobservices.sap._2007._03.Types.Rfc.BAPI_SENDER SENDER,   
                string TESTRUN,   
                ref microsoft.lobservices.sap._2007._03.Types.Rfc.BAPIPAREX[] EXTENSIONIN,   
                ref microsoft.lobservices.sap._2007._03.Types.Rfc.BAPICCARD[] ORDER_CCARD,   
                ref microsoft.lobservices.sap._2007._03.Types.Rfc.BAPICUBLB[] ORDER_CFGS_BLOB,   
                ref microsoft.lobservices.sap._2007._03.Types.Rfc.BAPICUINS[] ORDER_CFGS_INST,   
                ref microsoft.lobservices.sap._2007._03.Types.Rfc.BAPICUPRT[] ORDER_CFGS_PART_OF,   
                ref microsoft.lobservices.sap._2007._03.Types.Rfc.BAPICUCFG[] ORDER_CFGS_REF,   
                ref microsoft.lobservices.sap._2007._03.Types.Rfc.BAPICUREF[] ORDER_CFGS_REFINST,   
                ref microsoft.lobservices.sap._2007._03.Types.Rfc.BAPICUVAL[] ORDER_CFGS_VALUE,   
                ref microsoft.lobservices.sap._2007._03.Types.Rfc.BAPICUVK[] ORDER_CFGS_VK,   
                ref microsoft.lobservices.sap._2007._03.Types.Rfc.BAPICOND[] ORDER_CONDITIONS_IN,   
                ref microsoft.lobservices.sap._2007._03.Types.Rfc.BAPICONDX[] ORDER_CONDITIONS_INX,   
                ref microsoft.lobservices.sap._2007._03.Types.Rfc.BAPISDITM[] ORDER_ITEMS_IN,   
                ref microsoft.lobservices.sap._2007._03.Types.Rfc.BAPISDITMX[] ORDER_ITEMS_INX,   
                ref microsoft.lobservices.sap._2007._03.Types.Rfc.BAPISDKEY[] ORDER_KEYS,   
                ref microsoft.lobservices.sap._2007._03.Types.Rfc.BAPIPARNR[] ORDER_PARTNERS,   
                ref microsoft.lobservices.sap._2007._03.Types.Rfc.BAPISCHDL[] ORDER_SCHEDULES_IN,   
                ref microsoft.lobservices.sap._2007._03.Types.Rfc.BAPISCHDLX[] ORDER_SCHEDULES_INX,   
                ref microsoft.lobservices.sap._2007._03.Types.Rfc.BAPISDTEXT[] ORDER_TEXT,   
                ref microsoft.lobservices.sap._2007._03.Types.Rfc.BAPIADDR1[] PARTNERADDRESSES,   
                ref microsoft.lobservices.sap._2007._03.Types.Rfc.BAPIRET2[] RETURN) { ...}  
  
    /// <summary>The Metadata for this RFC was generated using the RFC SDK.</summary>  
    /// <param name="RETURN">Confirmations</param>  
    /// <param name="WAIT">Using the command `COMMIT AND WAIT`</param>  
    /// <returns></returns>  
    public microsoft.lobservices.sap._2007._03.Types.Rfc.BAPIRET2 BAPI_TRANSACTION_COMMIT(string WAIT) { ... }  
  
    /// <summary>The Metadata for this RFC was generated using the RFC SDK.</summary>  
    /// <param name="RETURN">Confirmations</param>  
    /// <returns></returns>  
    public microsoft.lobservices.sap._2007._03.Types.Rfc.BAPIRET2 BAPI_TRANSACTION_ROLLBACK() { ... }  
}  
```  
  
## <a name="bapi-transactions-in-the-wcf-service-model"></a>WCF サービス モデルでの BAPI トランザクション  
 すべての BAPI RFC、またはビジネス オブジェクトのメソッドとして呼び出されるかどうかの一部であるトランザクション (LUW) SAP システム同じ SAP 接続経由で受信したすべての BAPI SAP システムで同じ BAPI トランザクションの一部であります。 SAP では、コミットまたは、BAPI_TRANSACTION_COMMIT または接続での BAPI_TRANSACTION_ROLLBACK の受信時に、BAPI トランザクションをロールバックします。 コミットまたはロールバックが実行されて、[次へ] の BAPI 接続経由で受信した新しいトランザクションが開始されます。  
  
 アダプターの各 WCF チャネルは、専用の SAP 接続が。 WCF サービス モデルでは、各 WCF クライアントは、SAP システムへの送信に使用されるメッセージの内部チャネルが。 これは、特定の WCF クライアントを使用して呼び出される Bapi SAP システムで一意の BAPI トランザクションの一部であることを意味します。 これは、WCF サービス モデルを使用してビジネス オブジェクト メソッドとして Bapi を呼び出すときに、重大な制限事項です。 各 SAP ビジネス オブジェクトは、専用の WCF クライアント クラスによって表される、ため、同じトランザクションの一部として 2 つの異なるビジネス オブジェクトからの Bapi を呼び出すことはできません。 RFC 操作として Bapi を呼び出すにはこの問題を回避します。 ため、これは、 [!INCLUDE[addadapterservrefshort](../../includes/addadapterservrefshort-md.md)] RFC の操作の 1 つの WCF クライアントを生成し、そのため、そのクライアントを使用して呼び出されたすべての操作が同じ WCF チャネル経由で送信されます。  
  
> [!IMPORTANT]
>  同じ BAPI トランザクション内で別の SAP ビジネス オブジェクトからの Bapi を含める場合は、(同じ WCF クライアントを使用) の RFC 操作として呼び出す必要があります。 ビジネス オブジェクト メソッドとして呼び出すことはできません。  
  
 BAPI_TRANSACTION_COMMIT または BAPI_TRANSACTION_ROLLBACK コミットまたは SAP システムでの BAPI トランザクションのロールバックを呼び出すことができます。 アダプターでは、これら 2 つの Bapi が表示されます。  
  
- RFC 操作として [基準] ノードの下。  
  
- 各ビジネス オブジェクト。  
  
  アダプターが SAP の BAPI トランザクションをサポートする方法の詳細については、[SAP の Bapi に対する操作](../../adapters-and-accelerators/adapter-sap/operations-on-bapis-in-sap.md)を参照してください。  
  
## <a name="how-to-create-an-application-that-invokes-bapis-as-methods-of-business-objects"></a>ビジネス オブジェクトのメソッドとして Bapi を起動するアプリケーションを作成する方法  
 このセクションでは、ビジネス オブジェクトのメソッドとして Bapi を呼び出す方法について説明します。 同じ基本手順は、WCF クライアントを対象とする RFC 操作として Bapi を作成し、各 BAPI を呼び出すために使用する点を除いて RFC の操作として Bapi を呼び出すに従う必要があります。  
  
 BAPI のクライアント アプリケーションを作成するには、次の手順を実行します。  
  
#### <a name="to-create-an-bapi-client-application"></a>BAPI クライアント アプリケーションを作成するには  
  
1. WCF クライアント クラスを生成します。 使用して、 [!INCLUDE[addadapterservreflong](../../includes/addadapterservreflong-md.md)] ServiceModel メタデータ ユーティリティ ツール (svcutil.exe) を WCF クライアント クラス (またはクラス) を生成するビジネス オブジェクトを対象として Bapi を操作するか。 必ず、BAPI_TRANSACTION_COMMIT とターゲットのビジネス オブジェクトごとに公開される BAPI_TRANSACTION_ROLLBACK メソッド (Bapi) が含まれます。 WCF クライアントを生成する方法の詳細については、[SAP ソリューションの成果物の WCF クライアントまたは WCF サービス コントラクトを生成する](../../adapters-and-accelerators/adapter-sap/generate-a-wcf-client-or-a-wcf-service-contract-for-sap-solution-artifacts.md)を参照してください。  
  
2. 手順 1 で生成された WCF クライアント クラスのインスタンスを作成し、作成し、WCF クライアントを構成します。 WCF クライアントを構成するには、バインドと、クライアントが使用するエンドポイント アドレスを指定する必要があります。 コードで強制的に、または構成で宣言的に、これを行うことができます。 クライアントのバインディングを指定する方法の詳細については、[SAP システムのクライアントのバインディングを構成する](../../adapters-and-accelerators/adapter-sap/configure-a-client-binding-for-the-sap-system.md)を参照してください。 次のコードでは、構成から販売注文 (BUS2032) SAP ビジネス オブジェクト用の WCF クライアントを初期化し、SAP システムの資格情報を設定します。  
  
   ```  
   BapiBUS2032Client bapiClient = new BapiBUS2032Client("SAPBinding_BapiBUS2032");  
  
   bapiClient.ClientCredentials.UserName.UserName = "YourUserName";  
   bapiClient.ClientCredentials.UserName.Password = "YourPassword";  
   ```  
  
3. WCF クライアントを開きます。  
  
   ```  
   bapiClient.Open();  
   ```  
  
4. SAP システムで適切な Bapi を呼び出す手順 2. で作成された WCF クライアントのメソッドを呼び出します。 SAP システムで複数の Bapi を呼び出すことができます。  
  
5. トランザクションを終了するには。  
  
   1.  トランザクションをコミットする BAPI_TRANSACTION_COMMIT メソッドの呼び出し。  
  
       ```  
       bapiClient.BAPI_TRANSACTION_COMMIT("X");  
       ```  
  
   2.  トランザクションをロールバックする BAPI_TRANSACTION_ROLLBACK メソッドの呼び出し。  
  
       ```  
       bapiClient.BAPI_TRANSACTION_ROLLBACK();  
       ```  
  
6. WCF クライアントを閉じます。  
  
   ```  
   bapiClient.Close();   
   ```  
  
### <a name="example"></a>例  
 次の例では、販売注文のビジネス オブジェクトで CREATEFROMDAT2 BAPI を呼び出します。 複数回、BAPI を呼び出すし、トランザクションをコミットする BAPI_TRANSACTION_COMMIT を呼び出します。 BAPI を呼び出すときにエラーが発生する場合は、トランザクションをロールバックして、例外ハンドラーの BAPI_TRANSACTION_ROLLBACK が呼び出されます。  
  
 CREATEFROMDAT2 メソッドは、多くのパラメーターを受け取ります。これらは、簡潔にする例では省略されます。 Microsoft に付属のサンプルでの BAPI トランザクションを示すサンプルが見つかります[!INCLUDE[adapterpacknoversion](../../includes/adapterpacknoversion-md.md)]します。 詳細については、[SAP アダプターのサンプル](../../adapters-and-accelerators/adapter-sap/samples-for-the-sap-adapter.md)を参照してください。  
  
```  
using System;  
using System.Collections.Generic;  
using System.Text;  
  
// Add WCF, Adapter LOB SDK, and SAP Adapter namepaces  
using System.ServiceModel;  
using Microsoft.Adapters.SAP;  
using Microsoft.ServiceModel.Channels;  
  
// Include this namespace for Adapter LOB SDK and SAP exceptions  
using Microsoft.ServiceModel.Channels.Common;  
  
using microsoft.lobservices.sap._2007._03.Types.Rfc;  
  
// This Example demonstrates BAPI transactions. Two sales orders are  
// created using the CREATEFROMDAT2 method of a SAP Business Object.   
// After the orders are created, the BAPI transaction is committed.   
// If an exception occurs when sending the BAPIs, the BAPI transaction is   
// rolled back.  
//   
  
namespace SapBapiTxClientSM  
{  
    class Program  
    {  
        static void Main(string[] args)  
        {  
            // Create the BAPI client from the generated endpoint configuration.  
  
            BapiBUS2032Client bapiClient = null;  
  
            Console.WriteLine("BAPI transaction sample started");  
            Console.WriteLine("\nCreating business object client");  
  
            try  
            {  
                bapiClient = new BapiBUS2032Client("SAPBinding_BapiBUS2032");  
  
                bapiClient.ClientCredentials.UserName.UserName = "YourUserName";  
                bapiClient.ClientCredentials.UserName.Password = "YourPassword";  
  
                // Open the BAPI Client  
                bapiClient.Open();  
  
                ...  
  
                // send first BAPI  
                try  
                {  
                    string salesDocNumber1 = bapiClient.CREATEFROMDAT2(  
                        ...  
                        // parameters ommitted  
                        ...                          
                        );  
                }  
                catch (Exception ex)  
                {  
                    bapiClient.BAPI_TRANSACTION_ROLLBACK();  
                    throw;  
                }  
  
                ...  
  
                // send second BAPI  
                try  
                {  
                    string salesDocNumber1 = bapiClient.CREATEFROMDAT2(  
                        ...  
                        // parameters omitted  
                        ...                          
                        );  
                }  
                catch (Exception ex)  
                {  
                    bapiClient.BAPI_TRANSACTION_ROLLBACK();  
                    throw;  
                }  
  
                ...  
  
                // Commit BAPI Transaction  
                try  
                {  
                    bapiClient.BAPI_TRANSACTION.Commit();  
                }  
                catch (Exception ex)  
                {  
                    bapiClient.BAPI_TRANSACTION_ROLLBACK();  
                    throw;  
                }  
  
                ...  
  
            }  
            catch (ConnectionException cex)  
            {  
                // Get here if problem connecting to the SAP system   
  
                Console.WriteLine("Exception occurred connecting to the SAP system");  
                Console.WriteLine(cex.InnerException.Message);  
            }  
            catch (TargetSystemException tex)  
            {  
                // Get here if the SAP system returns an exception  
  
                Console.WriteLine("Exception occurred on the SAP System");  
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
            finally  
            {  
            // Close the client when finished  
                if (bapiClient != null)  
                {  
                    if (bapiClient.State == CommunicationState.Opened)  
                        bapiClient.Close();  
                    else  
                        bapiClient.Abort();  
                }  
            }  
        }  
    }  
}  
```  
  
## <a name="see-also"></a>参照  
[WCF サービス モデルを使用してアプリケーションを開発する](../../adapters-and-accelerators/adapter-sap/develop-sap-applications-using-the-wcf-service-model.md)  
 [Sap Bapi に対する操作](../../adapters-and-accelerators/adapter-sap/operations-on-bapis-in-sap.md)