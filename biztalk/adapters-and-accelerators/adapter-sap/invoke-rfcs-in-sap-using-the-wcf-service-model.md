---
title: WCF サービス モデルを使用して SAP Rfc を呼び出す |Microsoft ドキュメント
ms.custom: ''
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: ''
ms.suite: ''
ms.tgt_pltfrm: ''
ms.topic: article
helpviewer_keywords:
- invoking RFCs, using the WCF service model
- WCF service model, invoking RFCs
ms.assetid: 06a373e2-5d16-4480-81ec-611bd0b9749c
caps.latest.revision: 6
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: b8a18e9ae4990ecd5e85c57fc86919f239d51cbe
ms.sourcegitcommit: cb908c540d8f1a692d01dc8f313e16cb4b4e696d
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 09/20/2017
ms.locfileid: "22217522"
---
# <a name="invoke-rfcs-in-sap-using-the-wcf-service-model"></a>WCF サービス モデルを使用して SAP Rfc を呼び出す
[!INCLUDE[adaptersap](../../includes/adaptersap-md.md)]クライアント プログラムで呼び出すことができる操作として、SAP システムでの Rfc を表示します。 WCF サービス モデルでは、これらの操作が生成された WCF クライアント クラスのメソッドとして呼び出されます。 使用することができます、[!INCLUDE[addadapterservreflong](../../includes/addadapterservreflong-md.md)]用、コードで起動する RFC の各メソッドを含む WCF クライアント クラスを生成します。 [!INCLUDE[addadapterservrefshort](../../includes/addadapterservrefshort-md.md)]も RFC の各によって使用されているパラメーターとデータ型をカプセル化する .NET 型を生成します。 この WCF クライアント クラスのインスタンスを作成し、ターゲットの Rfc を起動するには、そのメソッドを呼び出すことができます。  
  
 以降のセクションを使用して SAP システムでの Rfc を呼び出す方法を表示、[!INCLUDE[adaptersap_short](../../includes/adaptersap-short-md.md)]です。  
  
## <a name="the-wcf-client-class"></a>WCF クライアント クラス  
 [!INCLUDE[adaptersap_short](../../includes/adaptersap-short-md.md)] "Rfc"、1 つのサービス コントラクトでのすべての RFC 操作を表示します。 つまり、1 つの WCF クライアント クラス**RfcClient**のすべての呼び出しをする RFC 操作が作成されます。 RFC の各ターゲットは、このクラスのメソッドとして表されます。 各メソッドには。  
  
-   SAP のエクスポートのパラメーターは、として表示された**アウト**パラメーター  
  
-   SAP 変化させるパラメーターは、として表示された**ref**パラメーター。  
  
-   構造体など、SAP の複合型は、SAP の種類のフィールドに対応するプロパティを持つ .NET クラスとして表示されます。 これらのクラスは、次の名前空間で定義されます: microsoft.lobservices.sap._2007._03.Types.Rfc です。  
  
 次のコードの一部を示しています、 **RfcClient**クラスと、SAP システムに対する SD_RFC_CUSTOMER_GET を呼び出すメソッド。  
  
```  
 [System.Diagnostics.DebuggerStepThroughAttribute()]  
[System.CodeDom.Compiler.GeneratedCodeAttribute("System.ServiceModel", "3.0.0.0")]  
public partial class RfcClient : System.ServiceModel.ClientBase<Rfc>, Rfc {  
  
    ...  
  
    /// <summary>The metadata for this RFC was generated using the RFC SDK.</summary>  
    /// <param name="KUNNR">Customer number</param>  
    /// <param name="NAME1">Name of the customer</param>  
    /// <param name="CUSTOMER_T">Table of the selected customers</param>  
    /// <returns></returns>  
    public void SD_RFC_CUSTOMER_GET(string KUNNR, string NAME1, ref microsoft.lobservices.sap._2007._03.Types.Rfc.RFCCUST[] CUSTOMER_T) {...}  
}  
```  
  
## <a name="how-to-create-an-rfc-client-application"></a>RFC クライアント アプリケーションを作成する方法  
 RFC クライアント アプリケーションを作成するには、次の手順を実行します。  
  
#### <a name="to-create-an-rfc-client-application"></a>RFC クライアント アプリケーションを作成するには  
  
1.  生成、 **RfcClient**クラスです。 使用して、 [!INCLUDE[addadapterservreflong](../../includes/addadapterservreflong-md.md)] 、ServiceModel メタデータ ユーティリティ ツール (svcutil.exe) を生成するか、 **RfcClient**を操作する Rfc を対象とするクラス。 WCF クライアントを生成する方法の詳細については、次を参照してください。 [SAP ソリューションの成果物のため、WCF クライアントまたは WCF サービス コントラクトを生成](../../adapters-and-accelerators/adapter-sap/generate-a-wcf-client-or-a-wcf-service-contract-for-sap-solution-artifacts.md)です。  
  
2.  インスタンスを作成、 **RfcClient**クラスで生成された手順 1、およびクライアントのバインディングを指定します。 バインドとエンドポイント アドレスを指定することは、クライアントのバインディングを指定する、 **RfcClient**が使用されます。 これは、コードで命令として記述または構成で宣言によって行うことができます。 クライアントのバインディングを指定する方法の詳細については、次を参照してください。 [、SAP システムのクライアントのバインディングを構成する](../../adapters-and-accelerators/adapter-sap/configure-a-client-binding-for-the-sap-system.md)です。 次のコードを初期化します、 **RfcClient**からの構成と、SAP システムの資格情報を設定します。  
  
    ```  
    RfcClient rfcClient = new RfcClient("SAPBinding_Rfc");  
  
    rfcClient.ClientCredentials.UserName.UserName = "YourUserName";  
    rfcClient.ClientCredentials.UserName.Password = "YourPassword";  
    ```  
  
3.  WCF クライアントを開きます。  
  
    ```  
    rfcClient.Open();  
    ```  
  
4.  に対してメソッドを呼び出す、 **RfcClient** SAP システムでの操作を実行する 2 の手順で作成します。 次のコードを呼び出す、 **SD_RFC_CUSTOMER_GET**のメソッド、 **RfcClient**を SAP システムで RFC を呼び出します。  
  
    ```  
    microsoft.lobservices.sap._2007._03.Types.Rfc.RFCCUST[] customers =   
        new microsoft.lobservices.sap._2007._03.Types.Rfc.RFCCUST[0];  
  
    rfcClient.SD_RFC_CUSTOMER_GET(string.Empty, "AB*", ref customers);  
    ```  
  
5.  WCF クライアントを閉じます。  
  
    ```  
    rfcClient.Close();   
    ```  
  
### <a name="example"></a>例  
 "AB"で始まる名前を含む顧客の一覧を返す SD_RFC_CUSTOMER_GET を起動し、各顧客のコンソールに名前と ID に書き込みますを完全なコード例を次に示します。 この例で作成、 **RfcClient**内、**を使用して**ステートメントです。 明示的に閉じる必要はありません、 **RfcClient**; 実行パスのコンテキストの終了時に閉じられます。  
  
```  
using System;  
using System.Collections.Generic;  
using System.Text;  
  
using System.ServiceModel;  
using Microsoft.ServiceModel.Channels;  
using Microsoft.Adapters.SAP;  
  
namespace SapRfcClientSM  
{  
    class Program  
    {  
        static void Main(string[] args)  
        {  
            try  
            {  
                // Create client from configuration  
                using (RfcClient rfcClient = new RfcClient("SAPBinding_Rfc"))  
                {  
  
                    rfcClient.ClientCredentials.UserName.UserName = "YourUserName";  
                    rfcClient.ClientCredentials.UserName.Password = "YourPassword";  
  
                    // Open client  
                    rfcClient.Open();  
  
                    microsoft.lobservices.sap._2007._03.Types.Rfc.RFCCUST[] customers = new microsoft.lobservices.sap._2007._03.Types.Rfc.RFCCUST[0];  
  
                    // Invoke SD_RFC_CUSTOMER_GET  
                    rfcClient.SD_RFC_CUSTOMER_GET(string.Empty, "AB*", ref customers);  
  
                    // Write the results to the console  
                    foreach (microsoft.lobservices.sap._2007._03.Types.Rfc.RFCCUST customer in customers)  
                    {  
                        Console.WriteLine("Customer Name = " + customer.NAME1);  
                        Console.WriteLine("         Id   = " + customer.KUNNR);  
                        Console.WriteLine();  
                    }  
                }  
            }  
            catch (Exception ex)  
            {  
                Console.WriteLine(ex.Message);  
                if (ex.InnerException != null)  
                    Console.WriteLine("Inner exception is :" + ex.InnerException);  
            }  
        }  
    }  
}  
```  
  
## <a name="see-also"></a>参照  
[WCF サービス モデルを使用してアプリケーションを開発します。](../../adapters-and-accelerators/adapter-sap/develop-sap-applications-using-the-wcf-service-model.md)   
 [RFC 操作のメッセージ スキーマ](../../adapters-and-accelerators/adapter-sap/message-schemas-for-rfc-operations.md)