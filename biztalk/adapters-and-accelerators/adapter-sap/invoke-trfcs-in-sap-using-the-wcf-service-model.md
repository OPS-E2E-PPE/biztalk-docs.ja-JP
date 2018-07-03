---
title: WCF サービス モデルを使用して SAP の Trfc を呼び出す |Microsoft Docs
ms.custom: ''
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: ''
ms.suite: ''
ms.tgt_pltfrm: ''
ms.topic: article
helpviewer_keywords:
- tRFCs, invoking by using the WCF service model
- WCF service model, invoking tRFCs
ms.assetid: 456fa869-2f1a-42e0-adbf-86bfe0876846
caps.latest.revision: 6
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: 8d28e3cc47a213f122f30c2599063897e0485816
ms.sourcegitcommit: 266308ec5c6a9d8d80ff298ee6051b4843c5d626
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 06/27/2018
ms.locfileid: "37002379"
---
# <a name="invoke-trfcs-in-sap-using-the-wcf-service-model"></a><span data-ttu-id="3066f-102">WCF サービス モデルを使用して SAP の Trfc を呼び出す</span><span class="sxs-lookup"><span data-stu-id="3066f-102">Invoke tRFCs in SAP using the WCF Service Model</span></span>
<span data-ttu-id="3066f-103">トランザクション リモート関数呼び出し (Trfc) の保証、 *1 回限り*SAP システムの RFC を実行します。</span><span class="sxs-lookup"><span data-stu-id="3066f-103">Transactional Remote Function Calls (tRFCs) guarantee a *one-time* execution of an RFC on an SAP system.</span></span> <span data-ttu-id="3066f-104">いずれかの側に表示される、Rfc を呼び出すことができます、 [!INCLUDE[adaptersap_short](../../includes/adaptersap-short-md.md)] tRFC として。</span><span class="sxs-lookup"><span data-stu-id="3066f-104">You can invoke any of the RFCs surfaced by the [!INCLUDE[adaptersap_short](../../includes/adaptersap-short-md.md)] as a tRFC.</span></span> <span data-ttu-id="3066f-105">WCF サービス モデルでの tRFC を呼び出すと、相違点を次の RFC を呼び出すと同様です。</span><span class="sxs-lookup"><span data-stu-id="3066f-105">Invoking a tRFC in the WCF service model is similar to invoking an RFC with the following differences:</span></span>  
  
- <span data-ttu-id="3066f-106">[!INCLUDE[adaptersap_short](../../includes/adaptersap-short-md.md)] Trfc 別のノード (TRFC) の Rfc (RFC) よりも下に表示されます。</span><span class="sxs-lookup"><span data-stu-id="3066f-106">The [!INCLUDE[adaptersap_short](../../includes/adaptersap-short-md.md)] surfaces tRFCs under a different node (TRFC) than RFCs (RFC).</span></span>  
  
- <span data-ttu-id="3066f-107">tRFC クライアント呼び出しでは、SAP のエクスポートおよびパラメーターを変更するための値は返されません。</span><span class="sxs-lookup"><span data-stu-id="3066f-107">tRFC client calls do not return values for SAP export and changing parameters.</span></span>  
  
- <span data-ttu-id="3066f-108">tRFC 操作によって tRFC の SAP トランザクション ID (TID) にマップされている GUID パラメーターを含める、[!INCLUDE[adaptersap_short](../../includes/adaptersap-short-md.md)]します。</span><span class="sxs-lookup"><span data-stu-id="3066f-108">tRFC operations include a GUID parameter that is mapped to the SAP transaction ID (TID) for the tRFC by the [!INCLUDE[adaptersap_short](../../includes/adaptersap-short-md.md)].</span></span>  
  
- <span data-ttu-id="3066f-109">TRFC を呼び出すには、(コミット)、SAP システムの tRFC を確認する RfcConfirmTransID 操作を呼び出す必要があります。</span><span class="sxs-lookup"><span data-stu-id="3066f-109">After you invoke a tRFC, you must invoke the RfcConfirmTransID operation to confirm (commit) the tRFC on the SAP system.</span></span> <span data-ttu-id="3066f-110">この操作は、TRFC ノードのすぐ下に表示されます。</span><span class="sxs-lookup"><span data-stu-id="3066f-110">This operation is surfaced directly under the TRFC node.</span></span>  
  
  <span data-ttu-id="3066f-111">TRFC 操作と RfcConfirmTransID 操作の詳細については、次を参照してください。 [SAP の Trfc に対する操作](../../adapters-and-accelerators/adapter-sap/operations-on-trfcs-in-sap.md)します。</span><span class="sxs-lookup"><span data-stu-id="3066f-111">For more information about tRFC operations and the RfcConfirmTransID operation, see [Operations on tRFCs in SAP](../../adapters-and-accelerators/adapter-sap/operations-on-trfcs-in-sap.md).</span></span>  
  
  <span data-ttu-id="3066f-112">次のセクションを使用して、SAP システムの Trfc を呼び出す方法を説明、[!INCLUDE[adaptersap_short](../../includes/adaptersap-short-md.md)]します。</span><span class="sxs-lookup"><span data-stu-id="3066f-112">The following sections show you how to invoke tRFCs on the SAP system by using the [!INCLUDE[adaptersap_short](../../includes/adaptersap-short-md.md)].</span></span>  
  
## <a name="the-wcf-client-class"></a><span data-ttu-id="3066f-113">WCF クライアント クラス</span><span class="sxs-lookup"><span data-stu-id="3066f-113">The WCF Client Class</span></span>  
 <span data-ttu-id="3066f-114">[!INCLUDE[adaptersap_short](../../includes/adaptersap-short-md.md)]サーフェスの 1 つのサービス コントラクトは、"Trfc"の下のすべての tRFC 操作。</span><span class="sxs-lookup"><span data-stu-id="3066f-114">The [!INCLUDE[adaptersap_short](../../includes/adaptersap-short-md.md)] surfaces all tRFC operations under a single service contract, "Trfc".</span></span> <span data-ttu-id="3066f-115">つまり、1 つの WCF クライアント クラス**TrfcClient**のすべての呼び出し先 tRFC 操作が作成されます。</span><span class="sxs-lookup"><span data-stu-id="3066f-115">This means that a single WCF client class, **TrfcClient**, is created for all of the tRFC operations that you want to invoke.</span></span> <span data-ttu-id="3066f-116">各ターゲット tRFC は、このクラスのメソッドとして表されます。</span><span class="sxs-lookup"><span data-stu-id="3066f-116">Each target tRFC is represented as a method of this class.</span></span> <span data-ttu-id="3066f-117">各メソッドには。</span><span class="sxs-lookup"><span data-stu-id="3066f-117">For each method:</span></span>  
  
- <span data-ttu-id="3066f-118">構造体などの複雑な SAP 型は、SAP の種類のフィールドに対応するプロパティの .NET クラスとして表示されます。</span><span class="sxs-lookup"><span data-stu-id="3066f-118">Complex SAP types such as structures are surfaced as .NET classes with properties that correspond to the fields of the SAP type.</span></span> <span data-ttu-id="3066f-119">これらのクラスは、次の名前空間で定義されている: **microsoft.lobservices.sap._2007._03.Types.Rfc**します。</span><span class="sxs-lookup"><span data-stu-id="3066f-119">These classes are defined in the following namespace: **microsoft.lobservices.sap._2007._03.Types.Rfc**.</span></span>  
  
  <span data-ttu-id="3066f-120">次のコードの一部を示しています、 **TrfcClient**クラスと、SAP システムで BAPI_SALESORDER_CREATEFROMDAT2 (、tRFC) として実行するメソッド。</span><span class="sxs-lookup"><span data-stu-id="3066f-120">The following code shows part of the **TrfcClient** class and the method that invokes BAPI_SALESORDER_CREATEFROMDAT2 (as a tRFC) on the SAP system.</span></span> <span data-ttu-id="3066f-121">**TransactionalRfcOperationIdentifier**パラメーターには、SAP TID にマップされている GUID が含まれています。</span><span class="sxs-lookup"><span data-stu-id="3066f-121">The **TransactionalRfcOperationIdentifier** parameter contains the GUID that is mapped to the SAP TID.</span></span> <span data-ttu-id="3066f-122">すべてのメソッドにパラメーターが表示されます。</span><span class="sxs-lookup"><span data-stu-id="3066f-122">Not all of the parameters to the method are shown.</span></span>  
  
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
  
 <span data-ttu-id="3066f-123">次のコードでは、RfcConfirmTransID 操作用に生成されるメソッドを示します。</span><span class="sxs-lookup"><span data-stu-id="3066f-123">The following code shows the method that is generated for the RfcConfirmTransID operation.</span></span> <span data-ttu-id="3066f-124">このメソッドがの一部として生成されることを確認する必要があります、 **TrfcClient**します。</span><span class="sxs-lookup"><span data-stu-id="3066f-124">You must ensure that this method is generated as part of the **TrfcClient**.</span></span> <span data-ttu-id="3066f-125">RfcConfirmTransID 操作は、TRFC ノードのすぐ下に表示されます。</span><span class="sxs-lookup"><span data-stu-id="3066f-125">The RfcConfirmTransID operation is surfaced directly under the TRFC node.</span></span>  
  
```  
public void RfcConfirmTransID(System.Guid TransactionalRfcOperationIdentifier) {…}  
```  
  
## <a name="how-to-create-a-trfc-client-application"></a><span data-ttu-id="3066f-126">TRFC クライアント アプリケーションを作成する方法</span><span class="sxs-lookup"><span data-stu-id="3066f-126">How to Create a tRFC Client Application</span></span>  
 <span data-ttu-id="3066f-127">Trfc を起動するアプリケーションを作成する手順は、手順と同様ですが、次の例外、Rfc を呼び出すために従ってください。</span><span class="sxs-lookup"><span data-stu-id="3066f-127">The steps to create an application that invokes tRFCs are similar to the steps you follow to invoke RFCs, with the following exceptions:</span></span>  
  
-   <span data-ttu-id="3066f-128">TRFC ノードの下のターゲットの操作を取得する必要があります。</span><span class="sxs-lookup"><span data-stu-id="3066f-128">You must retrieve the target operations under the TRFC node.</span></span>  
  
-   <span data-ttu-id="3066f-129">RfcConfirmTransID 操作を取得する必要があります。</span><span class="sxs-lookup"><span data-stu-id="3066f-129">You must retrieve the RfcConfirmTransID operation.</span></span> <span data-ttu-id="3066f-130">TRFC ノードのすぐ下に表示されます。</span><span class="sxs-lookup"><span data-stu-id="3066f-130">This is surfaced directly under the TRFC node.</span></span>  
  
-   <span data-ttu-id="3066f-131">(コミット)、SAP システムで tRFC 操作のことを確認するには、その tRFC 操作の返された GUID を持つ RfcConfirmTransID 操作を呼び出す必要があります。</span><span class="sxs-lookup"><span data-stu-id="3066f-131">To confirm (commit) a tRFC operation on the SAP system, you must invoke the RfcConfirmTransID operation with the GUID that was returned for that tRFC operation.</span></span>  
  
#### <a name="to-create-a-trfc-client-application"></a><span data-ttu-id="3066f-132">TRFC クライアント アプリケーションを作成するには</span><span class="sxs-lookup"><span data-stu-id="3066f-132">To create a tRFC client application</span></span>  
  
1. <span data-ttu-id="3066f-133">生成、 **TrfcClient**クラス。</span><span class="sxs-lookup"><span data-stu-id="3066f-133">Generate a **TrfcClient** class.</span></span> <span data-ttu-id="3066f-134">使用して、 [!INCLUDE[addadapterservreflong](../../includes/addadapterservreflong-md.md)] 、ServiceModel メタデータ ユーティリティ ツール (svcutil.exe) を生成するか、 **TrfcClient**を操作する Rfc を対象とするクラス。</span><span class="sxs-lookup"><span data-stu-id="3066f-134">Use the [!INCLUDE[addadapterservreflong](../../includes/addadapterservreflong-md.md)] or the ServiceModel Metadata Utility Tool (svcutil.exe) to generate a **TrfcClient** class that targets the RFCs with which you want to work.</span></span> <span data-ttu-id="3066f-135">WCF クライアントを生成する方法の詳細については、次を参照してください。 [WCF クライアントまたは SAP ソリューションの成果物の WCF サービス コントラクトを生成](../../adapters-and-accelerators/adapter-sap/generate-a-wcf-client-or-a-wcf-service-contract-for-sap-solution-artifacts.md)します。</span><span class="sxs-lookup"><span data-stu-id="3066f-135">For more information about how to generate a WCF client, see [Generate a WCF Client or a WCF Service Contract for SAP solution Artifacts](../../adapters-and-accelerators/adapter-sap/generate-a-wcf-client-or-a-wcf-service-contract-for-sap-solution-artifacts.md).</span></span> <span data-ttu-id="3066f-136">RfcConfirmTransID 操作に含まれるように、 **TrfcClient**クラス。</span><span class="sxs-lookup"><span data-stu-id="3066f-136">Ensure that the RfcConfirmTransID operation is included in the **TrfcClient** class.</span></span>  
  
2. <span data-ttu-id="3066f-137">インスタンスを作成、 **TrfcClient**クラスは、手順 1. で生成され、クライアントのバインディングを指定します。</span><span class="sxs-lookup"><span data-stu-id="3066f-137">Create an instance of the **TrfcClient** class generated in step 1 and specify a client binding.</span></span> <span data-ttu-id="3066f-138">クライアントのバインディングを指定するには、バインディングとエンドポイント アドレスを指定する必要があります、 **TrfcClient**が使用されます。</span><span class="sxs-lookup"><span data-stu-id="3066f-138">Specifying a client binding involves specifying the binding and endpoint address that the **TrfcClient** will use.</span></span> <span data-ttu-id="3066f-139">コードで強制的に、または構成で宣言的に、これを行うことができます。</span><span class="sxs-lookup"><span data-stu-id="3066f-139">You can do this either imperatively in code or declaratively in configuration.</span></span> <span data-ttu-id="3066f-140">クライアントのバインディングを指定する方法の詳細については、次を参照してください。 [SAP システムのクライアントのバインディングを構成する](../../adapters-and-accelerators/adapter-sap/configure-a-client-binding-for-the-sap-system.md)します。</span><span class="sxs-lookup"><span data-stu-id="3066f-140">For more information about how to specify a client binding, see [Configure a Client Binding for the SAP System](../../adapters-and-accelerators/adapter-sap/configure-a-client-binding-for-the-sap-system.md).</span></span> <span data-ttu-id="3066f-141">次のコードを初期化します、 **TrfcClient**から構成し、SAP システムの資格情報を設定します。</span><span class="sxs-lookup"><span data-stu-id="3066f-141">The following code initializes the **TrfcClient** from configuration and sets the credentials for the SAP system.</span></span>  
  
   ```  
   TrfcClient trfcClient = new TrfcClient("SAPBinding_Rfc");  
  
   trfcClient.ClientCredentials.UserName.UserName = "YourUserName";  
   trfcClient.ClientCredentials.UserName.Password = "YourPassword";  
   ```  
  
3. <span data-ttu-id="3066f-142">開く、 **TrfcClient**します。</span><span class="sxs-lookup"><span data-stu-id="3066f-142">Open the **TrfcClient**.</span></span>  
  
   ```  
   trfcClient.Open();  
   ```  
  
4. <span data-ttu-id="3066f-143">適切なメソッドの呼び出し、 **TrfcClient**を SAP システムでターゲット tRFC を呼び出す 2 の手順で作成します。</span><span class="sxs-lookup"><span data-stu-id="3066f-143">Invoke the appropriate method on the **TrfcClient** created in step 2 to invoke the target tRFC on the SAP system.</span></span> <span data-ttu-id="3066f-144">GUID を格納しているか、空の GUID を格納している変数を渡すことができます、 **TransactionalRrcOperationIdentifier**パラメーター。</span><span class="sxs-lookup"><span data-stu-id="3066f-144">You can pass a variable that contains a GUID or that contains an empty GUID for the **TransactionalRrcOperationIdentifier** parameter.</span></span> <span data-ttu-id="3066f-145">空の GUID を渡す場合、[!INCLUDE[adaptersap_short](../../includes/adaptersap-short-md.md)]のいずれかが生成されます。</span><span class="sxs-lookup"><span data-stu-id="3066f-145">If you pass an empty GUID, the [!INCLUDE[adaptersap_short](../../includes/adaptersap-short-md.md)] generates one for you.</span></span> <span data-ttu-id="3066f-146">次のコードでは、(すべてのメソッドのパラメーターが表示されます)、SAP システムでの tRFC として BAPI_SALESORDER_CREATEFROMDAT2 を呼び出します。</span><span class="sxs-lookup"><span data-stu-id="3066f-146">The following code invokes BAPI_SALESORDER_CREATEFROMDAT2 as a tRFC on the SAP system (not all parameters to the method are shown).</span></span> <span data-ttu-id="3066f-147">GUID を指定します。</span><span class="sxs-lookup"><span data-stu-id="3066f-147">A GUID is specified.</span></span>  
  
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
  
5. <span data-ttu-id="3066f-148">SAP システムで tRFC に関連付けられている TID を確認するには、起動、 **RfcConfirmTransID**メソッドを**TrfcClient**します。</span><span class="sxs-lookup"><span data-stu-id="3066f-148">To confirm the TID associated with the tRFC on the SAP system, invoke the **RfcConfirmTransID** method on the **TrfcClient**.</span></span> <span data-ttu-id="3066f-149">指定の手順 4. で返される GUID、 **TransactionRfcOperationIdentifier**パラメーター。</span><span class="sxs-lookup"><span data-stu-id="3066f-149">Specify the GUID returned in step 4 for the **TransactionRfcOperationIdentifier**parameter.</span></span>  
  
   ```  
   trfcClient.RfcConfirmTransID(transactionalRfcOperationIdentifier);  
   ```  
  
6. <span data-ttu-id="3066f-150">閉じる、 **TrfcClient**したら (したらすべて Trfc を呼び出す) を使用しています。</span><span class="sxs-lookup"><span data-stu-id="3066f-150">Close the **TrfcClient** when you are done using it (after you have finished invoking all tRFCs).</span></span>  
  
   ```  
   trfcClient.Close();   
   ```  
  
### <a name="example"></a><span data-ttu-id="3066f-151">例</span><span class="sxs-lookup"><span data-stu-id="3066f-151">Example</span></span>  
 <span data-ttu-id="3066f-152">次の例では、BAPI_SALESORDER_CREATE として、tRFC を呼び出す方法を示します。</span><span class="sxs-lookup"><span data-stu-id="3066f-152">The following example shows how to invoke BAPI_SALESORDER_CREATE as a tRFC.</span></span>  
  
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
  
## <a name="see-also"></a><span data-ttu-id="3066f-153">参照</span><span class="sxs-lookup"><span data-stu-id="3066f-153">See Also</span></span>  
<span data-ttu-id="3066f-154">[WCF サービス モデルを使用してアプリケーションを開発します。](../../adapters-and-accelerators/adapter-sap/develop-sap-applications-using-the-wcf-service-model.md) </span><span class="sxs-lookup"><span data-stu-id="3066f-154">[Develop applications using the WCF Service Model](../../adapters-and-accelerators/adapter-sap/develop-sap-applications-using-the-wcf-service-model.md) </span></span>  
 [<span data-ttu-id="3066f-155">SAP の Trfc に対する操作</span><span class="sxs-lookup"><span data-stu-id="3066f-155">Operations on tRFCs in SAP</span></span>](../../adapters-and-accelerators/adapter-sap/operations-on-trfcs-in-sap.md)