---
title: "WCF サービス モデルを使用して SAP での Bapi を呼び出す |Microsoft ドキュメント"
ms.custom: 
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: 
ms.suite: 
ms.tgt_pltfrm: 
ms.topic: article
helpviewer_keywords:
- BAPIs, invoking by using the WCF service model
- WCF service model, invoking BAPIs
ms.assetid: be3c48d6-2213-4ae5-97f4-634fbc423022
caps.latest.revision: "8"
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: 437c88516cfb771e0e5ae10807391235d602eb37
ms.sourcegitcommit: cb908c540d8f1a692d01dc8f313e16cb4b4e696d
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 09/20/2017
---
# <a name="invoke-bapis-in-sap-using-the-wcf-service-model"></a>WCF サービス モデルを使用して SAP での Bapi を呼び出し
[!INCLUDE[adaptersap_short](../../includes/adaptersap-short-md.md)]として Bapi を表示します。  
  
-   **RFC 操作**です。 [RFC] ノードに表示された Bapi の他の任意の RFC のように、[!INCLUDE[addadapterservrefshort](../../includes/addadapterservrefshort-md.md)]です。  
  
-   **SAP ビジネス オブジェクトのメソッド**です。 BAPI ノードの下のビジネス オブジェクトによって、ビジネス オブジェクトのメソッドとしての Bapi の表示、[!INCLUDE[addadapterservrefshort](../../includes/addadapterservrefshort-md.md)]です。  
  
 RFC 操作、またはビジネス オブジェクトのメソッドとして BAPI を呼び出すと、各 BAPI は常に、LUW SAP システムでの一部です。  
  
 方法の概要については[!INCLUDE[adaptersap_short](../../includes/adaptersap-short-md.md)]サポートの Bapi を参照してください[SAP での Bapi の操作](../../adapters-and-accelerators/adapter-sap/operations-on-bapis-in-sap.md)です。  
  
 Bapi のビジネス オブジェクト メソッドとして呼び出す WCF サービス モデルを使用する場合は、SAP business の各オブジェクトは、WCF クライアント クラスで表されるされ、そのビジネス オブジェクトの Bapi は、クライアント上のメソッドとして表されます。 使用することができます、[!INCLUDE[addadapterservreflong](../../includes/addadapterservreflong-md.md)]をコードで起動するそれぞれの BAPI のメソッドを格納する、特定のビジネス オブジェクトの WCF クライアント クラスを生成します。 [!INCLUDE[addadapterservrefshort](../../includes/addadapterservrefshort-md.md)]も各 BAPI によって使用されているパラメーターとデータ型をカプセル化する .NET 型を生成します。 この WCF クライアント クラスのインスタンスを作成し、ターゲット Bapi を起動するには、そのメソッドを呼び出すことができます。  
  
 次のセクションでは、ビジネス オブジェクトのメソッドとして Bapi を呼び出すし、WCF サービス モデルでの BAPI のトランザクションのサポートについて説明する方法を示します。  
  
## <a name="the-wcf-client-class"></a>WCF クライアント クラス  
 [!INCLUDE[adaptersap_short](../../includes/adaptersap-short-md.md)]ビジネス オブジェクトごとに、別のサービス コントラクトを表示します。 これは、各ビジネス オブジェクトの一意の WCF クライアント クラスを作成することを意味します。 このクラスの名前は、ビジネス オブジェクトの種類に基づいています。 たとえば、Sales Order ビジネス オブジェクト (ビジネス オブジェクトの種類 BUS2032) には、WCF クライアント クラスは**BapiBUS2032Client**です。 ビジネス オブジェクト内の各ターゲット BAPI は、生成された WCF クライアント クラスのメソッドとして表されます。 各メソッドには。  
  
-   SAP のエクスポートのパラメーターは、として表示された**アウト**パラメーター  
  
-   SAP 呼び出しのパラメーターは、として表示された**ref**パラメーター。  
  
-   構造体など、SAP の複合型は、SAP の種類のフィールドに対応するプロパティを持つ .NET クラスとして表示されます。 これらのクラスは、次の名前空間で定義されます: microsoft.lobservices.sap._2007._03.Types.Rfc です。  
  
 BAPI_TRANSACTION_COMMIT と BAPI_TRANSACTION_ROLLBACK がビジネス オブジェクトごとに表示され、WCF クライアントでこれらを常に含める必要があります。  
  
 次のコードは、販売注文のビジネス オブジェクトに対して生成される WCF クライアント クラスの一部を示しています。 このクライアントには、CREATEFROMDAT2、BAPI_TRANSACTION_COMMIT および BAPI_TRANSACTION_ROLLBACK を呼び出すメソッドが含まれています。 わかりやすくするためには、コンス トラクターおよびその他のコードを省略されています。  
  
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
  
## <a name="bapi-transactions-in-the-wcf-service-model"></a>WCF サービス モデルでの BAPI のトランザクション  
 すべての BAPI RFC、またはビジネス オブジェクトのメソッドとしてメソッドが呼び出されたかどうかの一部であるトランザクション (LUW)、SAP システムで同じ SAP 接続経由で受信したすべての BAPI の SAP システムでの同じ BAPI トランザクションの一部であります。 SAP がコミットまたは、BAPI_TRANSACTION_COMMIT または接続で BAPI_TRANSACTION_ROLLBACK を受信したときに、BAPI トランザクションをロールバックします。 コミットまたはロールバックが実行された後、接続経由で受信した次の BAPI は新しいトランザクションを開始します。  
  
 アダプターは、各 WCF チャネルは、専用の SAP 接続がします。 WCF サービス モデルで、各 WCF クライアントに使用される送信メッセージを SAP システムである内部チャネルがあります。 これは、特定の WCF クライアントを使用して呼び出される Bapi SAP システムで一意の BAPI トランザクションの一部であることを意味します。 これにより、モデルを使用して、WCF サービスをビジネス オブジェクト メソッドとして Bapi を呼び出す際に重要な制限です。 SAP business の各オブジェクトは、専用の WCF クライアント クラスで表される、ために、同じトランザクションの一部として 2 つの異なるビジネス オブジェクトから Bapi を呼び出すことはできません。 この問題を回避方法では、RFC 操作として Bapi を呼び出します。 これは、ため、 [!INCLUDE[addadapterservrefshort](../../includes/addadapterservrefshort-md.md)] RFC 操作の場合は、1 つの WCF クライアントを生成し、そのクライアントを使用して呼び出されたすべての操作が同じ WCF チャネル経由で送信されるため、します。  
  
> [!IMPORTANT]
>  同じ BAPI トランザクション内で異なる SAP ビジネス オブジェクトの Bapi を含める場合は、(同じ WCF クライアントを使用) の RFC 操作として呼び出す必要があります。 ビジネス オブジェクト メソッドとして呼び出すことはできません。  
  
 コミットまたは SAP システムでの BAPI のトランザクションがロールバックするには、BAPI_TRANSACTION_COMMIT または BAPI_TRANSACTION_ROLLBACK を呼び出します。 アダプターは、これら 2 つの Bapi を表示します。  
  
-   RFC 操作として [基準] ノードの下。  
  
-   各ビジネス オブジェクト。  
  
 アダプターが SAP で BAPI トランザクションをサポートする方法の詳細については、次を参照してください。 [SAP での Bapi の操作](../../adapters-and-accelerators/adapter-sap/operations-on-bapis-in-sap.md)です。  
  
## <a name="how-to-create-an-application-that-invokes-bapis-as-methods-of-business-objects"></a>ビジネス オブジェクトのメソッドとして Bapi を起動するアプリケーションを作成する方法  
 このセクションでは、ビジネス オブジェクトのメソッドとして Bapi を起動する方法に関する情報を提供します。 同じ基本的な手順は、WCF クライアントを対象とする RFC 操作として Bapi を作成し、各 BAPI の呼び出しに使用する点を除いて RFC 操作として Bapi を呼び出すに従う必要があります。  
  
 BAPI のクライアント アプリケーションを作成するには、次の手順を実行します。  
  
#### <a name="to-create-an-bapi-client-application"></a>BAPI クライアント アプリケーションを作成するには  
  
1.  WCF クライアント クラスを生成します。 使用して、 [!INCLUDE[addadapterservreflong](../../includes/addadapterservreflong-md.md)] ServiceModel メタデータ ユーティリティ ツール (svcutil.exe) を WCF クライアント クラス (またはクラス) を生成するビジネス オブジェクトを対象として Bapi 操作するか。 必ず、BAPI_TRANSACTION_COMMIT と各ターゲット ビジネス オブジェクトの公開された BAPI_TRANSACTION_ROLLBACK メソッド (Bapi) を含めるようにします。 WCF クライアントを生成する方法の詳細については、次を参照してください。 [SAP ソリューションの成果物のため、WCF クライアントまたは WCF サービス コントラクトを生成する](../../adapters-and-accelerators/adapter-sap/generate-a-wcf-client-or-a-wcf-service-contract-for-sap-solution-artifacts.md)です。  
  
2.  手順 1 で生成される WCF クライアント クラスのインスタンスを作成して作成し、WCF クライアントを構成します。 WCF クライアントを構成するには、バインディングと、クライアントが使用するエンドポイントのアドレス指定が含まれます。 これは、コードで命令として記述または構成で宣言によって行うことができます。 クライアントのバインディングを指定する方法の詳細については、次を参照してください。 [、SAP システムのクライアントのバインディングを構成する](../../adapters-and-accelerators/adapter-sap/configure-a-client-binding-for-the-sap-system.md)です。 次のコードは、Sales Order (BUS2032) SAP ビジネス オブジェクトの構成から WCF クライアントを初期化し、SAP システムの資格情報を設定します。  
  
    ```  
    BapiBUS2032Client bapiClient = new BapiBUS2032Client("SAPBinding_BapiBUS2032");  
  
    bapiClient.ClientCredentials.UserName.UserName = "YourUserName";  
    bapiClient.ClientCredentials.UserName.Password = "YourPassword";  
    ```  
  
3.  WCF クライアントを開きます。  
  
    ```  
    bapiClient.Open();  
    ```  
  
4.  SAP システムでの Bapi の適切なを起動する手順 2. で作成された WCF クライアントでメソッドを呼び出します。 SAP システムでの Bapi の複数を呼び出すことができます。  
  
5.  トランザクションを終了します。  
  
    1.  トランザクションをコミットする BAPI_TRANSACTION_COMMIT メソッドの呼び出し。  
  
        ```  
        bapiClient.BAPI_TRANSACTION_COMMIT("X");  
        ```  
  
    2.  トランザクションをロールバックする BAPI_TRANSACTION_ROLLBACK メソッドの呼び出し。  
  
        ```  
        bapiClient.BAPI_TRANSACTION_ROLLBACK();  
        ```  
  
6.  WCF クライアントを閉じます。  
  
    ```  
    bapiClient.Close();   
    ```  
  
### <a name="example"></a>例  
 次の例では、販売注文のビジネス オブジェクトで CREATEFROMDAT2 BAPI を呼び出します。 BAPI を数回呼び出し、トランザクションをコミットする BAPI_TRANSACTION_COMMIT を呼び出します。 BAPI を呼び出すときに、エラーが発生する場合は、トランザクションをロールバックして、例外ハンドラーの BAPI_TRANSACTION_ROLLBACK が呼び出されます。  
  
 CREATEFROMDAT2 メソッドは多くのパラメーターです。これらは、ここでは簡略化のための例では省略されます。 Microsoft に付属のサンプルでの BAPI のトランザクションを示すサンプルが見つかります[!INCLUDE[adapterpacknoversion](../../includes/adapterpacknoversion-md.md)]です。 詳細については、次を参照してください。 [SAP アダプターのサンプル](../../adapters-and-accelerators/adapter-sap/samples-for-the-sap-adapter.md)です。  
  
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
[WCF サービス モデルを使用してアプリケーションを開発します。](../../adapters-and-accelerators/adapter-sap/develop-sap-applications-using-the-wcf-service-model.md)  
 [SAP での Bapi の操作](../../adapters-and-accelerators/adapter-sap/operations-on-bapis-in-sap.md)