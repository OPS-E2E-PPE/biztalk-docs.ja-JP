---
title: "SAP で Ws-metadata Exchange を使用してメタデータの取得 |Microsoft ドキュメント"
ms.custom: 
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: 
ms.suite: 
ms.tgt_pltfrm: 
ms.topic: article
helpviewer_keywords:
- WS-Metadata Exchange
- how to, retrieve metadata
- retrieving metadata
ms.assetid: 29f85963-ac7f-4e13-96b8-bc2c94a9fcae
caps.latest.revision: "7"
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: ae33fd76725abf15f12d95be39997fc29e67403e
ms.sourcegitcommit: cb908c540d8f1a692d01dc8f313e16cb4b4e696d
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 09/20/2017
---
# <a name="get-metadata-using-ws-metadata-exchange-in-sap"></a><span data-ttu-id="f8aaa-102">SAP で Ws-metadata Exchange を使用してメタデータを取得します。</span><span class="sxs-lookup"><span data-stu-id="f8aaa-102">Get Metadata Using WS-Metadata Exchange in SAP</span></span>
<span data-ttu-id="f8aaa-103">として、[!INCLUDE[firstref_btsWinCommFoundation](../../includes/firstref-btswincommfoundation-md.md)]カスタム バインドを[!INCLUDE[adaptersap](../../includes/adaptersap-md.md)]から特定の操作についてのメタデータの取得に使用できる Ws-metadata Exchange (MEX) エンドポイントを公開して、[!INCLUDE[adaptersap](../../includes/adaptersap-md.md)]です。</span><span class="sxs-lookup"><span data-stu-id="f8aaa-103">As a [!INCLUDE[firstref_btsWinCommFoundation](../../includes/firstref-btswincommfoundation-md.md)] custom binding, the [!INCLUDE[adaptersap](../../includes/adaptersap-md.md)] exposes a WS-Metadata Exchange (MEX) endpoint that you can use to retrieve metadata for specific operations from the [!INCLUDE[adaptersap](../../includes/adaptersap-md.md)].</span></span>  
  
 <span data-ttu-id="f8aaa-104">WCF には、エクスポート、公開、取得、およびサービスに関するメタデータをインポートするための豊富なインフラストラクチャが用意されています。</span><span class="sxs-lookup"><span data-stu-id="f8aaa-104">WCF provides a rich infrastructure for exporting, publishing, retrieving and importing metadata about a service.</span></span> <span data-ttu-id="f8aaa-105">アダプターと同様に、WCF サービスでは、メタデータを使用して、svcutil.exe などのツールが、サービスを使用するためのクライアント コードを自動的に生成されるようにサービス エンドポイントと対話する方法について説明します。</span><span class="sxs-lookup"><span data-stu-id="f8aaa-105">WCF services, like the adapter, use metadata to describe how to interact with the service endpoints so that tools, like svcutil.exe, can automatically generate client code for consuming the service.</span></span> <span data-ttu-id="f8aaa-106">WCF では、サービスのメタデータを表すのインスタンスとして、 **MetadataSet**型で、Ws-metadata Exchange (MEX) で定義されているメタデータのシリアル化形式に強く関連付けられています。</span><span class="sxs-lookup"><span data-stu-id="f8aaa-106">WCF represents the metadata for a service as an instance of the **MetadataSet** type, which is strongly tied to the metadata serialization format defined in WS-Metadata Exchange (MEX).</span></span> <span data-ttu-id="f8aaa-107">作成することができます、 **MetadataSet**を使用してアダプターに対する操作の対象となる、 **MetadataExchangeClient**です。</span><span class="sxs-lookup"><span data-stu-id="f8aaa-107">You can create a **MetadataSet** for targeted operations on the adapter by using a **MetadataExchangeClient**.</span></span>  
  
 <span data-ttu-id="f8aaa-108">WCF では、メタデータ交換ができる拡張可能なトピックでは、このドキュメントの範囲を超えてをサポートします。</span><span class="sxs-lookup"><span data-stu-id="f8aaa-108">WCF support for metadata exchange is an expansive topic and beyond the scope of this documentation.</span></span> <span data-ttu-id="f8aaa-109">WCF でのメタデータのサポートの詳細についてを参照してください「メタデータ」で、WCF ドキュメント[http://go.microsoft.com/fwlink/?LinkId=105634](http://go.microsoft.com/fwlink/?LinkId=105634)です。</span><span class="sxs-lookup"><span data-stu-id="f8aaa-109">For more information about support for metadata in WCF, see "Metadata" in the WCF documentation at [http://go.microsoft.com/fwlink/?LinkId=105634](http://go.microsoft.com/fwlink/?LinkId=105634).</span></span> <span data-ttu-id="f8aaa-110">特に優れての詳細については、アーキテクチャ、クラス、および WCF は、メタデータの公開の名前空間を参照してください「メタデータ アーキテクチャの概要」 [http://go.microsoft.com/fwlink/?LinkId=105635](http://go.microsoft.com/fwlink/?LinkId=105635)です。</span><span class="sxs-lookup"><span data-stu-id="f8aaa-110">For a particularly good description of the architecture, classes, and namespaces that WCF exposes for metadata, see "Metadata Architecture Overview" at [http://go.microsoft.com/fwlink/?LinkId=105635](http://go.microsoft.com/fwlink/?LinkId=105635).</span></span> <span data-ttu-id="f8aaa-111">続行する前にこれらの WCF トピック内の WCF サービスからメタデータの取得に関連するコンテンツを理解しておく必要があります。</span><span class="sxs-lookup"><span data-stu-id="f8aaa-111">You should familiarize yourself with the content related to retrieving metadata from a WCF service in these WCF topics before proceeding.</span></span>  
  
 <span data-ttu-id="f8aaa-112">次のトピックには、使用方法に関する情報が含まれて、 **MetadataExchangeClient**メタデータを取得する、[!INCLUDE[adaptersap_short](../../includes/adaptersap-short-md.md)]です。</span><span class="sxs-lookup"><span data-stu-id="f8aaa-112">The following topics contain information about how to use a **MetadataExchangeClient** to retrieve metadata from the [!INCLUDE[adaptersap_short](../../includes/adaptersap-short-md.md)].</span></span>  
  
## <a name="using-a-metadataexchangeclient-to-retrieve-metadata"></a><span data-ttu-id="f8aaa-113">MetadataExchangeClient を使用してメタデータを取得するには</span><span class="sxs-lookup"><span data-stu-id="f8aaa-113">Using a MetadataExchangeClient to Retrieve Metadata</span></span>  
 <span data-ttu-id="f8aaa-114">使用する、 **MetadataExchangeClient**接続 URI とバインディングを指定する必要があります (**SAPBinding**)。</span><span class="sxs-lookup"><span data-stu-id="f8aaa-114">To use a **MetadataExchangeClient** you must specify a connection URI and a binding (**SAPBinding**).</span></span> <span data-ttu-id="f8aaa-115">接続 URI では、メタデータを取得する操作を識別します。</span><span class="sxs-lookup"><span data-stu-id="f8aaa-115">The connection URI identifies the operations for which you want to retrieve metadata.</span></span>  
  
 <span data-ttu-id="f8aaa-116">次のセクションでは、接続 URI、重要なバインドのプロパティを指定する方法と使用方法に関する情報を格納する、 **MetadataExchangeClient**アダプターからメタデータを取得します。</span><span class="sxs-lookup"><span data-stu-id="f8aaa-116">The following sections contain information about how to specify the connection URI, important binding properties, and how to use a **MetadataExchangeClient** to retrieve metadata from the adapter.</span></span>  
  
### <a name="the-connection-uri"></a><span data-ttu-id="f8aaa-117">接続 URI</span><span class="sxs-lookup"><span data-stu-id="f8aaa-117">The Connection URI</span></span>  
 <span data-ttu-id="f8aaa-118">使用する、 **MetadataExchangeClient** SAP 接続を MEX エンドポイントと操作のメタデータを取得する操作を指定する URI を指定する必要があります。</span><span class="sxs-lookup"><span data-stu-id="f8aaa-118">To use the **MetadataExchangeClient** you must supply a SAP connection URI that specifies a MEX endpoint and the operation or operations for which you want to retrieve metadata.</span></span> <span data-ttu-id="f8aaa-119">次のように、接続 URI で MEX エンドポイントとターゲットの操作を指定します。</span><span class="sxs-lookup"><span data-stu-id="f8aaa-119">You specify a MEX endpoint and target operations in the connection URI in the following manner:</span></span>  
  
-   <span data-ttu-id="f8aaa-120">クエリ文字列には、"wsdl"パラメーターを含める必要があります。</span><span class="sxs-lookup"><span data-stu-id="f8aaa-120">You must include the "wsdl" parameter in the query string.</span></span> <span data-ttu-id="f8aaa-121">クエリ文字列の最初のパラメーターは場合、疑問符 (?) の直後に指定されています。</span><span class="sxs-lookup"><span data-stu-id="f8aaa-121">If it is the first parameter in the query string, it is specified just after the question mark (?).</span></span> <span data-ttu-id="f8aaa-122">場合は、最初のパラメーターでない場合は、その必要がありますの前に、アンパサンド (&)。</span><span class="sxs-lookup"><span data-stu-id="f8aaa-122">If it is not the first parameter, it should be preceded with an ampersand (&).</span></span>  
  
-   <span data-ttu-id="f8aaa-123">1 つまたは複数の"op"パラメーターで、"wsdl"パラメーターに従う必要があります。</span><span class="sxs-lookup"><span data-stu-id="f8aaa-123">You must follow the "wsdl" parameter by one or more "op" parameters.</span></span> <span data-ttu-id="f8aaa-124">各"op"パラメーターは、前にアンパサンド (&) し、ターゲットの操作のメッセージのアクション (ノードの ID) を指定します。</span><span class="sxs-lookup"><span data-stu-id="f8aaa-124">Each "op" parameter is preceded by an ampersand (&) and specifies the message action (node ID) of a target operation.</span></span>  
  
 <span data-ttu-id="f8aaa-125">たとえば、次の接続 URI SALESORDER_CREATEFROMDAT201 IDOC および SALESORDER_CREATEFROMDAT202 IDOC に対する送信操作のターゲットです。</span><span class="sxs-lookup"><span data-stu-id="f8aaa-125">For example, the following connection URI targets the Send operation for the SALESORDER_CREATEFROMDAT201 IDOC and the SALESORDER_CREATEFROMDAT202 IDOC.</span></span> <span data-ttu-id="f8aaa-126">"Wsdl"および"op"パラメーターが強調表示されます。</span><span class="sxs-lookup"><span data-stu-id="f8aaa-126">The "wsdl" and "op" parameters are highlighted.</span></span>  
  
```  
"sap://User=YourUserName;Passwd=YourPassword;Client=800;Lang=EN;@a/YourSAPHost/00?wsdl&op=http://Microsoft.LobServices.Sap/2007/03/Idoc/3/SALESORDER_CREATEFROMDAT201//620/Send&op=http://Microsoft.LobServices.Sap/2007/03/Idoc/3/SALESORDER_CREATEFROMDAT202//620/Send"  
```  
  
> [!NOTE]
>  <span data-ttu-id="f8aaa-127">受信操作の接続 URI にリスナーのパラメーターを含める必要はありません。</span><span class="sxs-lookup"><span data-stu-id="f8aaa-127">It is not necessary to include listener parameters in the connection URI for inbound operations.</span></span> <span data-ttu-id="f8aaa-128">アダプターは、SAP システムからメタデータを取得するクライアントとして接続します。</span><span class="sxs-lookup"><span data-stu-id="f8aaa-128">The adapter connects as a client to retrieve metadata from the SAP system.</span></span>  
  
 <span data-ttu-id="f8aaa-129">定義されている定数を使用することもできます。`Microsoft.Adapters.SAP.SAPAdapterConstants.ActionConstants`接続 URI を作成するときに、操作を指定するためです。</span><span class="sxs-lookup"><span data-stu-id="f8aaa-129">You can also use the constants defined at `Microsoft.Adapters.SAP.SAPAdapterConstants.ActionConstants` to help you specify operations when you create a connection URI.</span></span> <span data-ttu-id="f8aaa-130">これは、このトピックの最後のコード例に示します。</span><span class="sxs-lookup"><span data-stu-id="f8aaa-130">This is demonstrated in the code example at the end of this topic.</span></span>  
  
 <span data-ttu-id="f8aaa-131">この接続 URI を渡す方法を**MetadataExchangeClient**クライアントを作成して、アダプターからのメタデータの取得に使用するオーバー ロードされたメソッドのうちに依存します。</span><span class="sxs-lookup"><span data-stu-id="f8aaa-131">How you pass this connection URI to the **MetadataExchangeClient** depends on which of the overloaded methods you use to create the client and retrieve metadata from the adapter.</span></span>  
  
 <span data-ttu-id="f8aaa-132">SAP 接続 URI の詳細については、次を参照してください。 [SAP システムの接続 URI を作成する](../../adapters-and-accelerators/adapter-sap/create-the-sap-system-connection-uri.md)です。</span><span class="sxs-lookup"><span data-stu-id="f8aaa-132">For more information about the SAP connection URI, see [Create the SAP System Connection URI](../../adapters-and-accelerators/adapter-sap/create-the-sap-system-connection-uri.md).</span></span>  
  
### <a name="binding-properties"></a><span data-ttu-id="f8aaa-133">バインドのプロパティ</span><span class="sxs-lookup"><span data-stu-id="f8aaa-133">Binding Properties</span></span>  
 <span data-ttu-id="f8aaa-134">作成するときに、 **MetadataExchangeClient**を指定する必要があります、 **SAPBinding**です。</span><span class="sxs-lookup"><span data-stu-id="f8aaa-134">When you create the **MetadataExchangeClient**, you must specify an **SAPBinding**.</span></span>  
  
 <span data-ttu-id="f8aaa-135">アダプターがメタデータを生成する方法に影響を与えるいくつかのバインド プロパティがあります。</span><span class="sxs-lookup"><span data-stu-id="f8aaa-135">There are several binding properties that affect how the adapter generates metadata.</span></span> <span data-ttu-id="f8aaa-136">これらのプロパティは次のとおりです。</span><span class="sxs-lookup"><span data-stu-id="f8aaa-136">These properties are:</span></span>  
  
-   <span data-ttu-id="f8aaa-137">**GenerateFlatfileCompatibleIdocSchema**</span><span class="sxs-lookup"><span data-stu-id="f8aaa-137">**GenerateFlatfileCompatibleIdocSchema**</span></span>  
  
-   <span data-ttu-id="f8aaa-138">**ReceiveIDocFormat**</span><span class="sxs-lookup"><span data-stu-id="f8aaa-138">**ReceiveIDocFormat**</span></span>  
  
-   <span data-ttu-id="f8aaa-139">**EnableSafeTyping**</span><span class="sxs-lookup"><span data-stu-id="f8aaa-139">**EnableSafeTyping**</span></span>  
  
-   <span data-ttu-id="f8aaa-140">**FlatFileSegmentIndicator**</span><span class="sxs-lookup"><span data-stu-id="f8aaa-140">**FlatFileSegmentIndicator**</span></span>  
  
 <span data-ttu-id="f8aaa-141">呼び出す前に、アプリケーションに必要な値をこれらのバインディング プロパティを設定することを確認する必要があります、 **GetMetadata**メソッドを**MetadataExchangeClient**です。</span><span class="sxs-lookup"><span data-stu-id="f8aaa-141">You should ensure that these binding properties are set to the values required for your application before you invoke the **GetMetadata** method on the **MetadataExchangeClient**.</span></span> <span data-ttu-id="f8aaa-142">SAP アダプターのバインドのプロパティの詳細については、次を参照してください。 [mySAP Business Suite バインド プロパティの BizTalk アダプターの説明を読む](../../adapters-and-accelerators/adapter-sap/read-about-biztalk-adapter-for-mysap-business-suite-binding-properties.md)です。</span><span class="sxs-lookup"><span data-stu-id="f8aaa-142">For more information about the SAP adapter binding properties, see [Read about BizTalk Adapter for mySAP Business Suite Binding Properties](../../adapters-and-accelerators/adapter-sap/read-about-biztalk-adapter-for-mysap-business-suite-binding-properties.md).</span></span>  
  
### <a name="example"></a><span data-ttu-id="f8aaa-143">例</span><span class="sxs-lookup"><span data-stu-id="f8aaa-143">Example</span></span>  
 <span data-ttu-id="f8aaa-144">次の例では、 **MetadataExchangeClient** BAPI_TRANSACTION_COMMIT および BAPI_TRANSACTION_ROLLBACK 操作のサービスの説明 (WSDL ドキュメント) を作成します。</span><span class="sxs-lookup"><span data-stu-id="f8aaa-144">The following example uses a **MetadataExchangeClient** to create a service description (WSDL document) for the BAPI_TRANSACTION_COMMIT and BAPI_TRANSACTION_ROLLBACK operations.</span></span>  
  
```  
using System;  
using System.Collections.Generic;  
using System.Text;  
using System.Collections.ObjectModel;  
  
// Needed for WCF and SAP adapter  
using System.ServiceModel;  
using Microsoft.ServiceModel.Channels;  
using Microsoft.Adapters.SAP;  
  
// Needed for MetadataExchangeClient class  
using System.ServiceModel.Description;  
// Needed for ServiceDescription class  
using System.Web.Services;  
  
namespace SapMetadataExchangeClient  
{  
    class Program  
    {  
        static void Main(string[] args)  
        {  
            //Create a binding  
            SAPBinding binding = new SAPBinding();  
  
            //Create a metadata exchange client that will retrieve metadata according to the WS-MEX standard.  
            MetadataExchangeClient client = new MetadataExchangeClient(binding);  
            client.SoapCredentials.UserName.UserName = "YourUserName";  
            client.SoapCredentials.UserName.Password = "YourPassword";  
  
            //Set up an endpoint address and specify the operation for which we want metadata.  
            string connectionUri = "sap://Client=800;lang=EN@A/YourSAPHost/00?wsdl&op="  
                + Microsoft.Adapters.SAP.SAPAdapterConstants.ActionConstants.RfcActionPrefix  
                + "BAPI_TRANSACTION_COMMIT"  
                + "&op="  
                + Microsoft.Adapters.SAP.SAPAdapterConstants.ActionConstants.RfcActionPrefix  
                + "BAPI_TRANSACTION_ROLLBACK";  
  
            EndpointAddress address = new EndpointAddress(connectionUri);  
  
            //Get the metadata.  
            MetadataSet ms = client.GetMetadata(address);  
  
            // Check for the metadata set size.   
            Collection<MetadataSection> documentCollection = ms.MetadataSections;  
            if (documentCollection != null && documentCollection.Count > 0)  
            {  
                //Get the WSDL from the metadata set  
                System.Web.Services.Description.ServiceDescription wsdl = (System.Web.Services.Description.ServiceDescription)documentCollection[0].Metadata;  
  
                //Save the WSDL to a file.  
                wsdl.Write("BapiTx.wsdl");    
  
            }  
  
        }  
    }  
}  
```  
  
## <a name="see-also"></a><span data-ttu-id="f8aaa-145">参照</span><span class="sxs-lookup"><span data-stu-id="f8aaa-145">See Also</span></span>  
 <span data-ttu-id="f8aaa-146">[SAP からメタデータをプログラムで取得します。](../../adapters-and-accelerators/adapter-sap/get-metadata-programmatically-from-sap.md) </span><span class="sxs-lookup"><span data-stu-id="f8aaa-146">[Retrieving Metadata Programmatically from SAP](../../adapters-and-accelerators/adapter-sap/get-metadata-programmatically-from-sap.md) </span></span>  
 [<span data-ttu-id="f8aaa-147">IMetadataRetrievalContract を使用して SAP のメタデータを取得します。</span><span class="sxs-lookup"><span data-stu-id="f8aaa-147">Retrieving Metadata in SAP using IMetadataRetrievalContract</span></span>](../../adapters-and-accelerators/adapter-sap/get-metadata-in-sap-using-imetadataretrievalcontract.md)