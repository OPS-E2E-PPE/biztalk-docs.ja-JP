---
title: WCF サービス モデルを使用して SAP で Rfc を呼び出す |Microsoft Docs
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
ms.openlocfilehash: a741ac41c86258567a22bb3a8a8d9ec699064dd0
ms.sourcegitcommit: 381e83d43796a345488d54b3f7413e11d56ad7be
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 05/07/2019
ms.locfileid: "65373317"
---
# <a name="invoke-rfcs-in-sap-using-the-wcf-service-model"></a><span data-ttu-id="05a71-102">WCF サービス モデルを使用して SAP で Rfc を呼び出す</span><span class="sxs-lookup"><span data-stu-id="05a71-102">Invoke RFCs in SAP using the WCF Service Model</span></span>
<span data-ttu-id="05a71-103">[!INCLUDE[adaptersap](../../includes/adaptersap-md.md)]クライアント プログラムで呼び出すことができる操作として、SAP システムで Rfc を表示します。</span><span class="sxs-lookup"><span data-stu-id="05a71-103">The [!INCLUDE[adaptersap](../../includes/adaptersap-md.md)] surfaces RFCs on the SAP system as operations that can be invoked by a client program.</span></span> <span data-ttu-id="05a71-104">WCF サービス モデルでは、これらの操作が生成された WCF クライアント クラスのメソッドとして呼び出されます。</span><span class="sxs-lookup"><span data-stu-id="05a71-104">In the WCF service model, these operations are invoked as methods of a generated WCF client class.</span></span> <span data-ttu-id="05a71-105">使用することができます、[!INCLUDE[addadapterservreflong](../../includes/addadapterservreflong-md.md)]のコードで呼び出す RFC の各メソッドを格納する WCF クライアント クラスを生成します。</span><span class="sxs-lookup"><span data-stu-id="05a71-105">You can use the [!INCLUDE[addadapterservreflong](../../includes/addadapterservreflong-md.md)] to generate a WCF client class that contains methods for each RFC that you want to invoke in your code.</span></span> <span data-ttu-id="05a71-106">[!INCLUDE[addadapterservrefshort](../../includes/addadapterservrefshort-md.md)]も RFC の各によって使用されているパラメーターおよびデータ型をカプセル化する .NET 型を生成します。</span><span class="sxs-lookup"><span data-stu-id="05a71-106">The [!INCLUDE[addadapterservrefshort](../../includes/addadapterservrefshort-md.md)] also generates .NET types to encapsulate the parameters and data types that are used by each RFC.</span></span> <span data-ttu-id="05a71-107">この WCF クライアント クラスのインスタンスを作成し、ターゲットの Rfc を呼び出すメソッドを呼び出すことができます。</span><span class="sxs-lookup"><span data-stu-id="05a71-107">You can then create an instance of this WCF client class and call its methods to invoke the target RFCs.</span></span>  
  
 <span data-ttu-id="05a71-108">次のセクションを使用して SAP システムでの Rfc を呼び出す方法を説明、[!INCLUDE[adaptersap_short](../../includes/adaptersap-short-md.md)]します。</span><span class="sxs-lookup"><span data-stu-id="05a71-108">The following sections show you how to invoke RFCs on the SAP system by using the [!INCLUDE[adaptersap_short](../../includes/adaptersap-short-md.md)].</span></span>  
  
## <a name="the-wcf-client-class"></a><span data-ttu-id="05a71-109">WCF クライアント クラス</span><span class="sxs-lookup"><span data-stu-id="05a71-109">The WCF Client Class</span></span>  
 <span data-ttu-id="05a71-110">[!INCLUDE[adaptersap_short](../../includes/adaptersap-short-md.md)] "Rfc"、1 つのサービス契約の RFC 操作をすべて明らかになります。</span><span class="sxs-lookup"><span data-stu-id="05a71-110">The [!INCLUDE[adaptersap_short](../../includes/adaptersap-short-md.md)] surfaces all RFC operations under a single service contract, "Rfc".</span></span> <span data-ttu-id="05a71-111">つまり、1 つの WCF クライアント クラス**RfcClient**のすべての呼び出し先 RFC 操作が作成されます。</span><span class="sxs-lookup"><span data-stu-id="05a71-111">This means that a single WCF client class, **RfcClient**, is created for all of the RFC operations that you want to invoke.</span></span> <span data-ttu-id="05a71-112">RFC の各ターゲットは、このクラスのメソッドとして表されます。</span><span class="sxs-lookup"><span data-stu-id="05a71-112">Each target RFC is represented as a method of this class.</span></span> <span data-ttu-id="05a71-113">各メソッドには。</span><span class="sxs-lookup"><span data-stu-id="05a71-113">In each method:</span></span>  
  
- <span data-ttu-id="05a71-114">SAP のエクスポートのパラメーターとして表示されますが**アウト**パラメーター</span><span class="sxs-lookup"><span data-stu-id="05a71-114">SAP export parameters are surfaced as **out** parameters</span></span>  
  
- <span data-ttu-id="05a71-115">として SAP 変化するパラメーターが表示された**ref**パラメーター。</span><span class="sxs-lookup"><span data-stu-id="05a71-115">SAP changing parameters are surfaced as **ref** parameters.</span></span>  
  
- <span data-ttu-id="05a71-116">構造体などの複雑な SAP 型は、SAP の種類のフィールドに対応するプロパティの .NET クラスとして表示されます。</span><span class="sxs-lookup"><span data-stu-id="05a71-116">Complex SAP types such as structures are surfaced as .NET classes with properties that correspond to the fields of the SAP type.</span></span> <span data-ttu-id="05a71-117">これらのクラスは、次の名前空間で定義されている: microsoft.lobservices.sap._2007._03.Types.Rfc します。</span><span class="sxs-lookup"><span data-stu-id="05a71-117">These classes are defined in the following namespace: microsoft.lobservices.sap._2007._03.Types.Rfc.</span></span>  
  
  <span data-ttu-id="05a71-118">次のコードの一部を示しています、 **RfcClient**クラスと SD_RFC_CUSTOMER_GET SAP システムで実行するメソッド。</span><span class="sxs-lookup"><span data-stu-id="05a71-118">The following code shows part of the **RfcClient** class and the method that invokes SD_RFC_CUSTOMER_GET on the SAP system.</span></span>  
  
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
  
## <a name="how-to-create-an-rfc-client-application"></a><span data-ttu-id="05a71-119">RFC クライアント アプリケーションを作成する方法</span><span class="sxs-lookup"><span data-stu-id="05a71-119">How to Create an RFC Client Application</span></span>  
 <span data-ttu-id="05a71-120">RFC クライアント アプリケーションを作成するには、次の手順を実行します。</span><span class="sxs-lookup"><span data-stu-id="05a71-120">To create an RFC client application, perform the following steps.</span></span>  
  
#### <a name="to-create-an-rfc-client-application"></a><span data-ttu-id="05a71-121">RFC クライアント アプリケーションを作成するには</span><span class="sxs-lookup"><span data-stu-id="05a71-121">To create an RFC client application</span></span>  
  
1. <span data-ttu-id="05a71-122">生成、 **RfcClient**クラス。</span><span class="sxs-lookup"><span data-stu-id="05a71-122">Generate an **RfcClient** class.</span></span> <span data-ttu-id="05a71-123">使用して、 [!INCLUDE[addadapterservreflong](../../includes/addadapterservreflong-md.md)] 、ServiceModel メタデータ ユーティリティ ツール (svcutil.exe) を生成するか、 **RfcClient**を操作する Rfc を対象とするクラス。</span><span class="sxs-lookup"><span data-stu-id="05a71-123">Use the [!INCLUDE[addadapterservreflong](../../includes/addadapterservreflong-md.md)] or the ServiceModel Metadata Utility Tool (svcutil.exe) to generate an **RfcClient** class that targets the RFCs with which you want to work.</span></span> <span data-ttu-id="05a71-124">WCF クライアントを生成する方法の詳細については、次を参照してください。 [SAP ソリューションの成果物の WCF クライアントまたは WCF サービス コントラクトを生成](../../adapters-and-accelerators/adapter-sap/generate-a-wcf-client-or-a-wcf-service-contract-for-sap-solution-artifacts.md)します。</span><span class="sxs-lookup"><span data-stu-id="05a71-124">For more information about how to generate a WCF client, see [Generate a WCF Client or a WCF Service Contract for SAP Solution Artifacts](../../adapters-and-accelerators/adapter-sap/generate-a-wcf-client-or-a-wcf-service-contract-for-sap-solution-artifacts.md).</span></span>  
  
2. <span data-ttu-id="05a71-125">インスタンスを作成、 **RfcClient**クラスで生成されたステップ 1、およびクライアントのバインディングを指定します。</span><span class="sxs-lookup"><span data-stu-id="05a71-125">Create an instance of the **RfcClient** class generated in step 1, and specify a client binding.</span></span> <span data-ttu-id="05a71-126">クライアントのバインディングを指定するには、バインディングとエンドポイント アドレスを指定する必要があります、 **RfcClient**が使用されます。</span><span class="sxs-lookup"><span data-stu-id="05a71-126">Specifying a client binding involves specifying the binding and endpoint address that the **RfcClient** will use.</span></span> <span data-ttu-id="05a71-127">コードで強制的に、または構成で宣言的に、これを行うことができます。</span><span class="sxs-lookup"><span data-stu-id="05a71-127">You can do this either imperatively in code or declaratively in configuration.</span></span> <span data-ttu-id="05a71-128">クライアントのバインディングを指定する方法の詳細については、次を参照してください。 [SAP システムのクライアントのバインディングを構成する](../../adapters-and-accelerators/adapter-sap/configure-a-client-binding-for-the-sap-system.md)します。</span><span class="sxs-lookup"><span data-stu-id="05a71-128">For more information about how to specify a client binding, see [Configure a Client Binding for the SAP System](../../adapters-and-accelerators/adapter-sap/configure-a-client-binding-for-the-sap-system.md).</span></span> <span data-ttu-id="05a71-129">次のコードを初期化します、 **RfcClient**から構成し、SAP システムの資格情報を設定します。</span><span class="sxs-lookup"><span data-stu-id="05a71-129">The following code initializes the **RfcClient** from configuration and sets the credentials for the SAP system.</span></span>  
  
   ```  
   RfcClient rfcClient = new RfcClient("SAPBinding_Rfc");  
  
   rfcClient.ClientCredentials.UserName.UserName = "YourUserName";  
   rfcClient.ClientCredentials.UserName.Password = "YourPassword";  
   ```  
  
3. <span data-ttu-id="05a71-130">WCF クライアントを開きます。</span><span class="sxs-lookup"><span data-stu-id="05a71-130">Open the WCF client.</span></span>  
  
   ```  
   rfcClient.Open();  
   ```  
  
4. <span data-ttu-id="05a71-131">メソッドを呼び出す、 **RfcClient** SAP システムの操作を実行する 2 の手順で作成します。</span><span class="sxs-lookup"><span data-stu-id="05a71-131">Invoke methods on the **RfcClient** created in step 2 to perform operations on the SAP system.</span></span> <span data-ttu-id="05a71-132">次のコードを呼び出す、 **SD_RFC_CUSTOMER_GET**のメソッド、 **RfcClient**を SAP システムでの RFC を呼び出します。</span><span class="sxs-lookup"><span data-stu-id="05a71-132">The following code invokes the **SD_RFC_CUSTOMER_GET** method of the **RfcClient** to invoke the RFC on the SAP system.</span></span>  
  
   ```  
   microsoft.lobservices.sap._2007._03.Types.Rfc.RFCCUST[] customers =   
       new microsoft.lobservices.sap._2007._03.Types.Rfc.RFCCUST[0];  
  
   rfcClient.SD_RFC_CUSTOMER_GET(string.Empty, "AB*", ref customers);  
   ```  
  
5. <span data-ttu-id="05a71-133">WCF クライアントを閉じます。</span><span class="sxs-lookup"><span data-stu-id="05a71-133">Close the WCF client.</span></span>  
  
   ```  
   rfcClient.Close();   
   ```  
  
### <a name="example"></a><span data-ttu-id="05a71-134">例</span><span class="sxs-lookup"><span data-stu-id="05a71-134">Example</span></span>  
 <span data-ttu-id="05a71-135">"AB"で始まる名前を持つ顧客の一覧を返す SD_RFC_CUSTOMER_GET を起動し、顧客ごとにコンソールに ID と名前を書き込みます完全なコード例を次に示します。</span><span class="sxs-lookup"><span data-stu-id="05a71-135">The following is a complete code example that invokes SD_RFC_CUSTOMER_GET to return a list of customers with names that begin with "AB" and then writes the name and ID for each customer to the console.</span></span> <span data-ttu-id="05a71-136">この例で作成、 **RfcClient**内で、**を使用して**ステートメント。</span><span class="sxs-lookup"><span data-stu-id="05a71-136">This example creates the **RfcClient** inside a **using** statement.</span></span> <span data-ttu-id="05a71-137">明示的に終了する必要はありません、 **RfcClient**; は、実行パスのコンテキストの終了時に閉じられます。</span><span class="sxs-lookup"><span data-stu-id="05a71-137">There is no need to explicitly close the **RfcClient**; it will be closed when the execution path exits the context.</span></span>  
  
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
  
## <a name="see-also"></a><span data-ttu-id="05a71-138">参照</span><span class="sxs-lookup"><span data-stu-id="05a71-138">See Also</span></span>  
<span data-ttu-id="05a71-139">[WCF サービス モデルを使用してアプリケーションを開発します。](../../adapters-and-accelerators/adapter-sap/develop-sap-applications-using-the-wcf-service-model.md) </span><span class="sxs-lookup"><span data-stu-id="05a71-139">[Develop applications using the WCF Service Model](../../adapters-and-accelerators/adapter-sap/develop-sap-applications-using-the-wcf-service-model.md) </span></span>  
 [<span data-ttu-id="05a71-140">RFC 操作のメッセージ スキーマ</span><span class="sxs-lookup"><span data-stu-id="05a71-140">Message Schemas for RFC Operations</span></span>](../../adapters-and-accelerators/adapter-sap/message-schemas-for-rfc-operations.md)