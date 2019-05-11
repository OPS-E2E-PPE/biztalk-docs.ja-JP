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
ms.openlocfilehash: b31823494068dab5f106f79cc404b9b5d35ad7a1
ms.sourcegitcommit: 381e83d43796a345488d54b3f7413e11d56ad7be
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 05/07/2019
ms.locfileid: "65372869"
---
# <a name="send-idocs-to-sap-using-the-wcf-service-model"></a><span data-ttu-id="8667e-102">WCF サービス モデルを使用して sap の Idoc を送信します。</span><span class="sxs-lookup"><span data-stu-id="8667e-102">Send IDOCs to SAP using the WCF Service Model</span></span>
<span data-ttu-id="8667e-103">内部的には、[!INCLUDE[adaptersap](../../includes/adaptersap-md.md)]次の 2 つの Rfc のいずれかを呼び出すことによって、SAP システムに Idoc を送信します。</span><span class="sxs-lookup"><span data-stu-id="8667e-103">Internally, the [!INCLUDE[adaptersap](../../includes/adaptersap-md.md)] sends IDOCs to the SAP system by invoking one of the two following RFCs:</span></span>  
  
- <span data-ttu-id="8667e-104">Idoc のバージョン 3 の IDOC_INBOUND_ASYNCHRONOUS します。</span><span class="sxs-lookup"><span data-stu-id="8667e-104">IDOC_INBOUND_ASYNCHRONOUS for version 3 IDOCs.</span></span>  
  
- <span data-ttu-id="8667e-105">Idoc のバージョン 2 の INBOUND_IDOC_PROCESS します。</span><span class="sxs-lookup"><span data-stu-id="8667e-105">INBOUND_IDOC_PROCESS for version 2 IDOCs.</span></span>  
  
  <span data-ttu-id="8667e-106">適切な RFC、tRFC); を呼び出すことによって、アダプターに IDOC を送信することができます。ただし、アダプターに Idoc を送信するのに次の 2 つの操作を使用することもできます。</span><span class="sxs-lookup"><span data-stu-id="8667e-106">You can send an IDOC to the adapter by invoking the appropriate RFC (or tRFC); however, you can also use the two following operations to send IDOCs to the adapter:</span></span>  
  
- <span data-ttu-id="8667e-107">**SendIdoc** IDOC のルート ノードのすぐ下に表示されます。</span><span class="sxs-lookup"><span data-stu-id="8667e-107">**SendIdoc** is surfaced directly under the IDOC root node.</span></span> <span data-ttu-id="8667e-108">SendIdoc 操作は、IDOC を送信します (弱い型指定の) データを文字列として、[!INCLUDE[adaptersap_short](../../includes/adaptersap-short-md.md)]します。</span><span class="sxs-lookup"><span data-stu-id="8667e-108">The SendIdoc operation sends the IDOC as string (weakly-typed) data to the [!INCLUDE[adaptersap_short](../../includes/adaptersap-short-md.md)].</span></span>  
  
- <span data-ttu-id="8667e-109">**送信**idoc ごとに個別に表示されます。</span><span class="sxs-lookup"><span data-stu-id="8667e-109">**Send** is surfaced individually for each IDOC.</span></span> <span data-ttu-id="8667e-110">送信操作を厳密に型指定されたデータとしての IDOC の送信、[!INCLUDE[adaptersap_short](../../includes/adaptersap-short-md.md)]します。</span><span class="sxs-lookup"><span data-stu-id="8667e-110">The Send operation sends the IDOC as strongly-typed data to the [!INCLUDE[adaptersap_short](../../includes/adaptersap-short-md.md)].</span></span>  
  
  <span data-ttu-id="8667e-111">これらの操作がアダプターに IDOC データを送信する方法を調べる方法に送信されません SAP システム。</span><span class="sxs-lookup"><span data-stu-id="8667e-111">These operations determine how the IDOC data is sent to the adapter, not how it is sent to the SAP system.</span></span> <span data-ttu-id="8667e-112">アダプターは常に、適切な tRFC を使用して、SAP システムに IDOC を送信します。</span><span class="sxs-lookup"><span data-stu-id="8667e-112">The adapter always sends the IDOC to the SAP system by using the appropriate tRFC.</span></span>  
  
  <span data-ttu-id="8667e-113">[!INCLUDE[adaptersap_short](../../includes/adaptersap-short-md.md)] IDOC を送信、tRFC、として SendIdoc と送信の両方の操作が (コミット) IDOC を確認するために使用する GUID パラメーターを公開します。</span><span class="sxs-lookup"><span data-stu-id="8667e-113">Because the [!INCLUDE[adaptersap_short](../../includes/adaptersap-short-md.md)] sends the IDOC as a tRFC, both the Send and SendIdoc operations expose a GUID parameter that you use to confirm (commit) the IDOC.</span></span> <span data-ttu-id="8667e-114">[!INCLUDE[adaptersap_short](../../includes/adaptersap-short-md.md)]この SAP トランザクション ID (TID)、tRFC に関連付けられている GUID を内部的にマップします。</span><span class="sxs-lookup"><span data-stu-id="8667e-114">The [!INCLUDE[adaptersap_short](../../includes/adaptersap-short-md.md)] internally maps this GUID with the SAP transaction ID (TID) that is associated with the tRFC.</span></span> <span data-ttu-id="8667e-115">2 つの方法のいずれかで IDOC を確認できます。</span><span class="sxs-lookup"><span data-stu-id="8667e-115">You can confirm the IDOC in one of two ways:</span></span>  
  
- <span data-ttu-id="8667e-116">使用して、 **AutoConfirmSentIdocs**プロパティをバインドします。</span><span class="sxs-lookup"><span data-stu-id="8667e-116">By using the **AutoConfirmSentIdocs** binding property.</span></span> <span data-ttu-id="8667e-117">このバインドのプロパティ設定されている場合**true**アダプターが自動的に IDOC を送信するために使用する tRFC を確認します。</span><span class="sxs-lookup"><span data-stu-id="8667e-117">If this binding property is set to **true**, the adapter automatically confirms the tRFC used to send the IDOC.</span></span>  
  
- <span data-ttu-id="8667e-118">RfcConfirmTransID を呼び出しています。</span><span class="sxs-lookup"><span data-stu-id="8667e-118">By invoking RfcConfirmTransID.</span></span> <span data-ttu-id="8667e-119">IDOC に関連付けられている GUID を持つには、この操作を呼び出します。</span><span class="sxs-lookup"><span data-stu-id="8667e-119">You invoke this operation with the GUID associated with the IDOC.</span></span>  
  
  <span data-ttu-id="8667e-120">次のセクションでは、SendIdoc と送信操作を使用して、SAP システムに Idoc を送信する方法を説明します。</span><span class="sxs-lookup"><span data-stu-id="8667e-120">The following sections show you how to send IDOCs to an SAP system by using the SendIdoc and Send operations.</span></span> <span data-ttu-id="8667e-121">として、tRFC IDOC を送信するための詳細については、次を参照してください。 [WCF サービス モデルを使用して SAP の Trfc を呼び出す](../../adapters-and-accelerators/adapter-sap/invoke-trfcs-in-sap-using-the-wcf-service-model.md)します。</span><span class="sxs-lookup"><span data-stu-id="8667e-121">For more information to help you send an IDOC as a tRFC, see [Invoke tRFCs in SAP by using the WCF Service Model](../../adapters-and-accelerators/adapter-sap/invoke-trfcs-in-sap-using-the-wcf-service-model.md).</span></span>  
  
## <a name="the-wcf-client-class"></a><span data-ttu-id="8667e-122">WCF クライアント クラス</span><span class="sxs-lookup"><span data-stu-id="8667e-122">The WCF Client Class</span></span>  
  
### <a name="the-sendidoc-operation"></a><span data-ttu-id="8667e-123">SendIdoc 操作</span><span class="sxs-lookup"><span data-stu-id="8667e-123">The SendIdoc Operation</span></span>  
 <span data-ttu-id="8667e-124">[!INCLUDE[adaptersap_short](../../includes/adaptersap-short-md.md)]サーフェスの文字列形式で IDOC を送信する 1 つの操作 (およびサービス コントラクト)。</span><span class="sxs-lookup"><span data-stu-id="8667e-124">The [!INCLUDE[adaptersap_short](../../includes/adaptersap-short-md.md)] surfaces a single operation (and service contract) to send an IDOC in string format.</span></span> <span data-ttu-id="8667e-125">サービス コントラクトの名前は"Idoc"と、WCF クライアント クラスが**IdocClient**します。</span><span class="sxs-lookup"><span data-stu-id="8667e-125">The name of the service contract is "Idoc" and the WCF client class is **IdocClient**.</span></span>  
  
 <span data-ttu-id="8667e-126">このクライアントを使用して、sap の IDOC を送信できます。</span><span class="sxs-lookup"><span data-stu-id="8667e-126">You can send any IDOC to SAP by using this client.</span></span> <span data-ttu-id="8667e-127">1 つのメソッドが含まれている**SendIdoc**、2 つのパラメーターを受け取る。</span><span class="sxs-lookup"><span data-stu-id="8667e-127">It contains a single method, **SendIdoc**, that takes two parameters:</span></span>  
  
- <span data-ttu-id="8667e-128">**idocData** IDOC データを格納した文字列です</span><span class="sxs-lookup"><span data-stu-id="8667e-128">**idocData** is a string that contains the IDOC data</span></span>  
  
- <span data-ttu-id="8667e-129">**guid**は SAP TID にマップされている GUID です。</span><span class="sxs-lookup"><span data-stu-id="8667e-129">**guid** is the GUID that is mapped to the SAP TID.</span></span>  
  
  <span data-ttu-id="8667e-130">次のコードは、SendIdoc 操作に対して生成される WCF クライアントを示しています。</span><span class="sxs-lookup"><span data-stu-id="8667e-130">The following code shows the WCF client that is generated for the SendIdoc operation.</span></span>  
  
```  
[System.Diagnostics.DebuggerStepThroughAttribute()]  
[System.CodeDom.Compiler.GeneratedCodeAttribute("System.ServiceModel", "3.0.0.0")]  
public partial class IdocClient : System.ServiceModel.ClientBase<Idoc>, Idoc {  
  
    public void SendIdoc(string idocData, ref System.Nullable\<System.Guid\> guid) {…}  
}  
```  
  
### <a name="the-send-operation"></a><span data-ttu-id="8667e-131">送信操作</span><span class="sxs-lookup"><span data-stu-id="8667e-131">The Send Operation</span></span>  
 <span data-ttu-id="8667e-132">送信操作は、厳密に型指定されたデータを使用するため、 [!INCLUDE[adaptersap_short](../../includes/adaptersap-short-md.md)] IDOC ごとの一意のサービス コントラクトを明らかになります。</span><span class="sxs-lookup"><span data-stu-id="8667e-132">Because the Send operation uses strongly-typed data, the [!INCLUDE[adaptersap_short](../../includes/adaptersap-short-md.md)] surfaces a unique service contract for each IDOC.</span></span> <span data-ttu-id="8667e-133">インターフェイス (および、WCF クライアント クラス) の名前は、このコントラクトが IDOC の種類、バージョン、リリース番号、および (該当する場合)、CIM 型に基づいて生成されます。</span><span class="sxs-lookup"><span data-stu-id="8667e-133">The name of the interface (and the WCF client class) generated for this contract is based on the IDOC type, version, release number, and CIM type (if relevant).</span></span> <span data-ttu-id="8667e-134">たとえば、WCF クライアント クラスは、"IdocORDERS03V3R620"が、インターフェイス、ORDERS03.v3.620 IDOC のという名前が**IdocORDERS03V3R620Client**します。</span><span class="sxs-lookup"><span data-stu-id="8667e-134">For example for the ORDERS03.v3.620 IDOC, the interface is named "IdocORDERS03V3R620" and the WCF client class is **IdocORDERS03V3R620Client**.</span></span>  
  
 <span data-ttu-id="8667e-135">IDOC の種類ごとの一意のクライアントを生成する必要があります。</span><span class="sxs-lookup"><span data-stu-id="8667e-135">You must generate a unique client for each different type of IDOC.</span></span> <span data-ttu-id="8667e-136">このクライアントには、1 つのメソッドが含まれています。**送信**、2 つのパラメーターを受け取る。</span><span class="sxs-lookup"><span data-stu-id="8667e-136">This client contains a single method, **Send**, that takes two parameters:</span></span>  
  
- <span data-ttu-id="8667e-137">**idocData** IDOC の厳密に型指定されたデータを表すクラスです。</span><span class="sxs-lookup"><span data-stu-id="8667e-137">**idocData** is a class that represents the strongly-typed IDOC data.</span></span>  
  
- <span data-ttu-id="8667e-138">**guid** SAP TID にマップされている GUID の文字列表現です。</span><span class="sxs-lookup"><span data-stu-id="8667e-138">**guid** is a string representation of the GUID that is mapped to the SAP TID.</span></span>  
  
  <span data-ttu-id="8667e-139">次のコードでは、表面化 ORDERS03.v3.620 IDOC の送信操作に対して生成される WCF クライアントを示します。</span><span class="sxs-lookup"><span data-stu-id="8667e-139">The following code shows the WCF client that is generated for the Send operation surfaced for the ORDERS03.v3.620 IDOC.</span></span>  
  
```  
[System.Diagnostics.DebuggerStepThroughAttribute()]  
[System.CodeDom.Compiler.GeneratedCodeAttribute("System.ServiceModel", "3.0.0.0")]  
public partial class IdocORDERS03V3R620Client : System.ServiceModel.ClientBase<IdocORDERS03V3R620>, IdocORDERS03V3R620 {  
  
    ...  
  
    public void Send(ORDERS03 idocData, ref string guid) { ... }  
}  
```  
  
## <a name="how-to-create-an-application-to-send-idocs"></a><span data-ttu-id="8667e-140">Idoc を送信するアプリケーションを作成する方法</span><span class="sxs-lookup"><span data-stu-id="8667e-140">How to Create an Application to Send IDOCs</span></span>  
 <span data-ttu-id="8667e-141">IDOC を SAP システムに送信するには、次の手順を実行します。</span><span class="sxs-lookup"><span data-stu-id="8667e-141">To send an IDOC to an SAP system, perform the following steps.</span></span>  
  
#### <a name="to-send-an-idoc-to-an-sap-system"></a><span data-ttu-id="8667e-142">IDOC を SAP システムに送信するには</span><span class="sxs-lookup"><span data-stu-id="8667e-142">To send an IDOC to an SAP system</span></span>  
  
1. <span data-ttu-id="8667e-143">WCF クライアント クラスを生成します。</span><span class="sxs-lookup"><span data-stu-id="8667e-143">Generate a WCF client class.</span></span> <span data-ttu-id="8667e-144">使用して、[!INCLUDE[addadapterservreflong](../../includes/addadapterservreflong-md.md)]または ServiceModel メタデータ ユーティリティ ツール (svcutil.exe) で WCF クライアント クラスを生成する作業する Idoc を対象とします。</span><span class="sxs-lookup"><span data-stu-id="8667e-144">Use the [!INCLUDE[addadapterservreflong](../../includes/addadapterservreflong-md.md)] or the ServiceModel Metadata Utility Tool (svcutil.exe) to generate the WCF client class that targets the IDOCs with which you want to work.</span></span> <span data-ttu-id="8667e-145">WCF クライアントを生成する方法の詳細については、次を参照してください。 [SAP ソリューションの成果物の WCF クライアントまたは WCF サービス コントラクトを生成する](../../adapters-and-accelerators/adapter-sap/generate-a-wcf-client-or-a-wcf-service-contract-for-sap-solution-artifacts.md)します。</span><span class="sxs-lookup"><span data-stu-id="8667e-145">For more information about how to generate a WCF client, see [Generating a WCF Client or a WCF Service Contract for SAP Solution Artifacts](../../adapters-and-accelerators/adapter-sap/generate-a-wcf-client-or-a-wcf-service-contract-for-sap-solution-artifacts.md).</span></span> <span data-ttu-id="8667e-146">Idoc を明示的に確認する場合は、RfcConfirmTransID 操作用の WCF クライアントを生成することを確認します。</span><span class="sxs-lookup"><span data-stu-id="8667e-146">If you want to explicitly confirm IDOCs, make sure that you generate the WCF client for the RfcConfirmTransID operation.</span></span> <span data-ttu-id="8667e-147">操作は、次のノードの下ではあります。</span><span class="sxs-lookup"><span data-stu-id="8667e-147">Operations can be found under the following nodes:</span></span>  
  
   -   <span data-ttu-id="8667e-148">SendIdoc 操作です。</span><span class="sxs-lookup"><span data-stu-id="8667e-148">SendIdoc operation.</span></span> <span data-ttu-id="8667e-149">直下の IDOC のノードです。</span><span class="sxs-lookup"><span data-stu-id="8667e-149">Directly under the IDOC node.</span></span>  
  
   -   <span data-ttu-id="8667e-150">送信操作です。</span><span class="sxs-lookup"><span data-stu-id="8667e-150">Send operation.</span></span> <span data-ttu-id="8667e-151">ターゲットの IDOC の種類、バージョンおよびリリースの番号に対応するノード。</span><span class="sxs-lookup"><span data-stu-id="8667e-151">Under the node corresponding to the type, version and release number of the target IDOC.</span></span>  
  
   -   <span data-ttu-id="8667e-152">RfcConfirmTransID 操作です。</span><span class="sxs-lookup"><span data-stu-id="8667e-152">RfcConfirmTransID operation.</span></span> <span data-ttu-id="8667e-153">直接 TRFC ノード。</span><span class="sxs-lookup"><span data-stu-id="8667e-153">Directly under the TRFC node.</span></span>  
  
2. <span data-ttu-id="8667e-154">手順 1 で生成された WCF クライアント クラスのインスタンスを作成し、クライアントのバインディングを指定します。</span><span class="sxs-lookup"><span data-stu-id="8667e-154">Create an instance of the WCF client class generated in step 1, and specify a client binding.</span></span> <span data-ttu-id="8667e-155">クライアントのバインディングを指定するには、バインドと WCF クライアントを使用するエンドポイント アドレスを指定する必要があります。</span><span class="sxs-lookup"><span data-stu-id="8667e-155">Specifying a client binding involves specifying the binding and endpoint address that the WCF client will use.</span></span> <span data-ttu-id="8667e-156">コードで強制的に、または構成で宣言的に、これを行うことができます。</span><span class="sxs-lookup"><span data-stu-id="8667e-156">You can do this either imperatively in code or declaratively in configuration.</span></span> <span data-ttu-id="8667e-157">クライアントのバインディングを指定する方法の詳細については、次を参照してください。 [SAP システムのクライアントのバインディングを構成する](../../adapters-and-accelerators/adapter-sap/configure-a-client-binding-for-the-sap-system.md)します。</span><span class="sxs-lookup"><span data-stu-id="8667e-157">For more information about how to specify a client binding, see [Configure a Client Binding for the SAP System](../../adapters-and-accelerators/adapter-sap/configure-a-client-binding-for-the-sap-system.md).</span></span> <span data-ttu-id="8667e-158">次のコードでは、構成からには、(送信操作) の IdocClient を初期化し、SAP システムの資格情報を設定します。</span><span class="sxs-lookup"><span data-stu-id="8667e-158">The following code initializes an IdocClient (for the Send operation) from configuration and sets the credentials for the SAP system.</span></span>  
  
   ```  
   SAPBinding binding = new SAPBinding();  
  
   // Set endpoint address  
   EndpointAddress endpointAddress = new EndpointAddress("sap://CLIENT=800;LANG=EN;@a/YourSAPHost/00?RfcSdkTrace=False&AbapDebug=False&UseSapGui=Without");  
  
   // Create client and set credentials  
   idocClient = new IdocClient(binding, endpointAddress);  
   idocClient.ClientCredentials.UserName.UserName = "YourUserName";  
   idocClient.ClientCredentials.UserName.Password = "YourPassword";;  
   ```  
  
3. <span data-ttu-id="8667e-159">IDOC を送信アダプターは、tRFC 後に SAP システムを確認する場合は、設定、 **AutoConfirmSentIdocs**プロパティをバインド**true**します。</span><span class="sxs-lookup"><span data-stu-id="8667e-159">If you want the adapter to confirm the tRFC on the SAP system after it sends the IDOC, set the **AutoConfirmSentIdocs** binding property to **true**.</span></span> <span data-ttu-id="8667e-160">WCF クライアントを開く前に、これを行う必要があります。</span><span class="sxs-lookup"><span data-stu-id="8667e-160">You must do this before you open the WCF client.</span></span>  
  
   ```  
   // Set AutoConfirmSentIdocs property to true  
   binding.AutoConfirmSentIdocs = true;  
   ```  
  
4. <span data-ttu-id="8667e-161">WCF クライアントを開きます。</span><span class="sxs-lookup"><span data-stu-id="8667e-161">Open the WCF client.</span></span>  
  
   ```  
   idocClient.Open();  
   ```  
  
5. <span data-ttu-id="8667e-162">手順 2 で作成した IDOC を SAP システムに送信する WCF クライアントの適切なメソッドを呼び出します。</span><span class="sxs-lookup"><span data-stu-id="8667e-162">Invoke the appropriate method on the WCF client created in step 2 to send the IDOC to the SAP system.</span></span> <span data-ttu-id="8667e-163">GUID を格納しているかに設定されている変数を渡すことができます**null**の**guid**パラメーター。</span><span class="sxs-lookup"><span data-stu-id="8667e-163">You can pass a variable that contains a GUID or that is set to **null** for the **guid** parameter.</span></span> <span data-ttu-id="8667e-164">GUID を指定しない場合、[!INCLUDE[adaptersap_short](../../includes/adaptersap-short-md.md)]操作のいずれかが生成されます (**guid**は、 **ref**パラメーター)。</span><span class="sxs-lookup"><span data-stu-id="8667e-164">If you do not specify a GUID, the [!INCLUDE[adaptersap_short](../../includes/adaptersap-short-md.md)] generates one for the operation (**guid** is a **ref** parameter).</span></span> <span data-ttu-id="8667e-165">次のコードでは、ファイルから文字列の形式で IDOC を読み取るし、SendIdoc 操作を使用して、SAP システムに送信します。</span><span class="sxs-lookup"><span data-stu-id="8667e-165">The following code reads an IDOC (in string format) from a file and sends it to the SAP system by using the SendIdoc operation.</span></span>  
  
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
  
6. <span data-ttu-id="8667e-166">設定しなかった場合、 **AutoConfirmSentIdocs**バインドのプロパティを**true** (手順 3) でしを確認してください、SAP システムで tRFC します。</span><span class="sxs-lookup"><span data-stu-id="8667e-166">If you did not set the **AutoConfirmSentIdocs** binding property to **true** (in step 3), then you must confirm the tRFC on the SAP system.</span></span> <span data-ttu-id="8667e-167">呼び出す必要がありますこれを行う、 **RfcConfirmTransID**メソッドを**TrfcClient** (作成時に表示されません)。</span><span class="sxs-lookup"><span data-stu-id="8667e-167">To do this you must invoke the **RfcConfirmTransID** method on a **TrfcClient** (creation not shown).</span></span> <span data-ttu-id="8667e-168">パラメーターには、手順 4. で返される GUID を指定します。</span><span class="sxs-lookup"><span data-stu-id="8667e-168">Specify the GUID returned in step 4 for the parameter.</span></span>  
  
   ```  
   trfcClient.RfcConfirmTransID(adapterTxGuid);  
   ```  
  
7. <span data-ttu-id="8667e-169">WCF クライアントを閉じる (および**TrfcClient**使用されている場合、) が終わったら (したら Idoc を送信する) を使用して。</span><span class="sxs-lookup"><span data-stu-id="8667e-169">Close the WCF client (and **TrfcClient**, if used) when you are done using it (after you have finished sending IDOCs).</span></span>  
  
   ```  
   idocClient.Close();   
   ```  
  
### <a name="example"></a><span data-ttu-id="8667e-170">例</span><span class="sxs-lookup"><span data-stu-id="8667e-170">Example</span></span>  
 <span data-ttu-id="8667e-171">次の例は、SendIdoc メソッドを使用して IDOC を SAP システムに送信します。</span><span class="sxs-lookup"><span data-stu-id="8667e-171">The following example sends an IDOC to an SAP system by using the SendIdoc method.</span></span> <span data-ttu-id="8667e-172">IDOC は ORDERS03.txt ファイルから読み取られます。</span><span class="sxs-lookup"><span data-stu-id="8667e-172">The IDOC is read from a file, ORDERS03.txt.</span></span> <span data-ttu-id="8667e-173">このファイルには、ORDERS03 が含まれています。V3.620 IDOC; サンプルに含まれているとただし、SendIdoc 操作を使用して、任意の IDOC を送信することができます。</span><span class="sxs-lookup"><span data-stu-id="8667e-173">This file contains an ORDERS03.V3.620 IDOC and is included with the samples; however, the SendIdoc operation can be used to send any IDOC.</span></span>  
  
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
  
## <a name="see-also"></a><span data-ttu-id="8667e-174">参照</span><span class="sxs-lookup"><span data-stu-id="8667e-174">See Also</span></span>  
[<span data-ttu-id="8667e-175">WCF サービス モデルを使用してアプリケーションを開発する</span><span class="sxs-lookup"><span data-stu-id="8667e-175">Develop applications using the WCF Service Model</span></span>](../../adapters-and-accelerators/adapter-sap/develop-sap-applications-using-the-wcf-service-model.md)