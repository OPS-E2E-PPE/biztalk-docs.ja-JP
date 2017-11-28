---
title: "Ws-metadata Exchange を使用して Oracle データベースでメタデータの取得 |Microsoft ドキュメント"
ms.custom: 
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: 
ms.suite: 
ms.tgt_pltfrm: 
ms.topic: article
helpviewer_keywords:
- WS-Metadata Exchange, retrieving metadata
- metadata, retrieving using WS-Metadata Exchange
ms.assetid: 6ff34438-7260-489d-a5f0-6e53f8fe43be
caps.latest.revision: "4"
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: 2be3f829d41b77dc7897d7b3f4300d82e7a3c100
ms.sourcegitcommit: cb908c540d8f1a692d01dc8f313e16cb4b4e696d
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 09/20/2017
---
# <a name="get-metadata-using-ws-metadata-exchange-in-oracle-database"></a><span data-ttu-id="af64b-102">Ws-metadata Exchange を使用して Oracle データベースでメタデータを取得します。</span><span class="sxs-lookup"><span data-stu-id="af64b-102">Get Metadata Using WS-Metadata Exchange in Oracle Database</span></span>
<span data-ttu-id="af64b-103">として、[!INCLUDE[firstref_btsWinCommFoundation](../../includes/firstref-btswincommfoundation-md.md)]カスタム バインドを[!INCLUDE[adapteroracle](../../includes/adapteroracle-md.md)]から特定の操作についてのメタデータの取得に使用できる Ws-metadata Exchange (MEX) エンドポイントを公開して、[!INCLUDE[adapteroracle](../../includes/adapteroracle-md.md)]です。</span><span class="sxs-lookup"><span data-stu-id="af64b-103">As a [!INCLUDE[firstref_btsWinCommFoundation](../../includes/firstref-btswincommfoundation-md.md)] custom binding, the [!INCLUDE[adapteroracle](../../includes/adapteroracle-md.md)] exposes a WS-Metadata Exchange (MEX) endpoint that you can use to retrieve metadata for specific operations from the [!INCLUDE[adapteroracle](../../includes/adapteroracle-md.md)].</span></span>  
  
 <span data-ttu-id="af64b-104">WCF には、エクスポート、公開、取得、およびサービスに関するメタデータをインポートするための豊富なインフラストラクチャが用意されています。</span><span class="sxs-lookup"><span data-stu-id="af64b-104">WCF provides a rich infrastructure for exporting, publishing, retrieving and importing metadata about a service.</span></span> <span data-ttu-id="af64b-105">アダプターと同様に、WCF サービスでは、メタデータを使用して、svcutil.exe などのツールが、サービスを使用するためのクライアント コードを自動的に生成されるようにサービス エンドポイントと対話する方法について説明します。</span><span class="sxs-lookup"><span data-stu-id="af64b-105">WCF services, like the adapter, use metadata to describe how to interact with the service endpoints so that tools, like svcutil.exe, can automatically generate client code for consuming the service.</span></span> <span data-ttu-id="af64b-106">WCF では、サービスのメタデータを表すのインスタンスとして、 **MetadataSet**型で、Ws-metadata Exchange (MEX) で定義されているメタデータのシリアル化形式に強く関連付けられています。</span><span class="sxs-lookup"><span data-stu-id="af64b-106">WCF represents the metadata for a service as an instance of the **MetadataSet** type, which is strongly tied to the metadata serialization format defined in WS-Metadata Exchange (MEX).</span></span> <span data-ttu-id="af64b-107">作成することができます、 **MetadataSet**を使用してアダプターに対する操作の対象となる、 **MetadataExchangeClient**です。</span><span class="sxs-lookup"><span data-stu-id="af64b-107">You can create a **MetadataSet** for targeted operations on the adapter by using a **MetadataExchangeClient**.</span></span>  
  
 <span data-ttu-id="af64b-108">WCF では、メタデータ交換ができる拡張可能なトピックでは、このドキュメントの範囲を超えてをサポートします。</span><span class="sxs-lookup"><span data-stu-id="af64b-108">WCF support for metadata exchange is an expansive topic and beyond the scope of this documentation.</span></span> <span data-ttu-id="af64b-109">WCF でのメタデータのサポートの詳細については、次を参照してください。[メタデータ](https://msdn.microsoft.com/library/ms731823.aspx)です。</span><span class="sxs-lookup"><span data-stu-id="af64b-109">For more information about support for metadata in WCF, see [Metadata](https://msdn.microsoft.com/library/ms731823.aspx).</span></span> <span data-ttu-id="af64b-110">詳細については特に効果的なアーキテクチャ、クラス、およびメタデータを公開する WCF の名前空間の次を参照してください。[メタデータ アーキテクチャの概要](https://msdn.microsoft.com/library/ms730243.aspx)です。</span><span class="sxs-lookup"><span data-stu-id="af64b-110">For a particularly good description of the architecture, classes, and namespaces that WCF exposes for metadata, see [Metadata Architecture Overview](https://msdn.microsoft.com/library/ms730243.aspx).</span></span> <span data-ttu-id="af64b-111">続行する前にこれらの WCF トピック内の WCF サービスからメタデータの取得に関連するコンテンツを理解しておく必要があります。</span><span class="sxs-lookup"><span data-stu-id="af64b-111">You should familiarize yourself with the content related to retrieving metadata from a WCF service in these WCF topics before proceeding.</span></span>  
  
 <span data-ttu-id="af64b-112">次のトピックには、使用方法に関する情報が含まれて、 **MetadataExchangeClient**メタデータを取得する、[!INCLUDE[adapteroracle_short](../../includes/adapteroracle-short-md.md)]です。</span><span class="sxs-lookup"><span data-stu-id="af64b-112">The following topics contain information about how to use a **MetadataExchangeClient** to retrieve metadata from the [!INCLUDE[adapteroracle_short](../../includes/adapteroracle-short-md.md)].</span></span>  
  
## <a name="using-a-metadataexchangeclient-to-retrieve-metadata"></a><span data-ttu-id="af64b-113">MetadataExchangeClient を使用してメタデータを取得するには</span><span class="sxs-lookup"><span data-stu-id="af64b-113">Using a MetadataExchangeClient to Retrieve Metadata</span></span>  
 <span data-ttu-id="af64b-114">使用する、 **MetadataExchangeClient**接続 URI とバインディングを指定する必要があります (**OracleDBBinding**)。</span><span class="sxs-lookup"><span data-stu-id="af64b-114">To use a **MetadataExchangeClient** you must specify a connection URI and a binding (**OracleDBBinding**).</span></span> <span data-ttu-id="af64b-115">接続 URI では、メタデータを取得する操作を識別します。</span><span class="sxs-lookup"><span data-stu-id="af64b-115">The connection URI identifies the operations for which you want to retrieve metadata.</span></span>  
  
 <span data-ttu-id="af64b-116">次のセクションでは、接続 URI、重要なバインドのプロパティを指定する方法と使用方法に関する情報を格納する、 **MetadataExchangeClient**アダプターからメタデータを取得します。</span><span class="sxs-lookup"><span data-stu-id="af64b-116">The following sections contain information about how to specify the connection URI, important binding properties, and how to use a **MetadataExchangeClient** to retrieve metadata from the adapter.</span></span>  
  
### <a name="the-connection-uri"></a><span data-ttu-id="af64b-117">接続 URI</span><span class="sxs-lookup"><span data-stu-id="af64b-117">The Connection URI</span></span>  
 <span data-ttu-id="af64b-118">使用する、 **MetadataExchangeClient** Oracle 接続 MEX エンドポイントと操作のメタデータを取得する操作を指定する URI を指定する必要があります。</span><span class="sxs-lookup"><span data-stu-id="af64b-118">To use the **MetadataExchangeClient** you must supply an Oracle connection URI that specifies a MEX endpoint and the operation or operations for which you want to retrieve metadata.</span></span> <span data-ttu-id="af64b-119">次のように、接続 URI で MEX エンドポイントとターゲットの操作を指定します。</span><span class="sxs-lookup"><span data-stu-id="af64b-119">You specify a MEX endpoint and target operations in the connection URI in the following manner:</span></span>  
  
-   <span data-ttu-id="af64b-120">クエリ文字列には、"wsdl"パラメーターを含める必要があります。</span><span class="sxs-lookup"><span data-stu-id="af64b-120">You must include the "wsdl" parameter in the query string.</span></span> <span data-ttu-id="af64b-121">クエリ文字列の最初のパラメーターは場合、疑問符 (?) の直後に指定されています。</span><span class="sxs-lookup"><span data-stu-id="af64b-121">If it is the first parameter in the query string, it is specified just after the question mark (?).</span></span> <span data-ttu-id="af64b-122">場合は、最初のパラメーターでない場合は、その必要がありますの前に、アンパサンド (&)。</span><span class="sxs-lookup"><span data-stu-id="af64b-122">If it is not the first parameter, it should be preceded with an ampersand (&).</span></span>  
  
-   <span data-ttu-id="af64b-123">1 つまたは複数の"op"パラメーターで、"wsdl"パラメーターに従う必要があります。</span><span class="sxs-lookup"><span data-stu-id="af64b-123">You must follow the "wsdl" parameter by one or more "op" parameters.</span></span> <span data-ttu-id="af64b-124">各"op"パラメーターは、前にアンパサンド (&) し、ターゲットの操作のメッセージのアクション (ノードの ID) を指定します。</span><span class="sxs-lookup"><span data-stu-id="af64b-124">Each "op" parameter is preceded by an ampersand (&) and specifies the message action (node ID) of a target operation.</span></span>  
  
 <span data-ttu-id="af64b-125">たとえば、次の接続 URI、SCOTT の挿入および削除操作のターゲットです。EMP テーブルです。</span><span class="sxs-lookup"><span data-stu-id="af64b-125">For example, the following connection URI targets the Insert and Delete operations for the SCOTT.EMP table.</span></span> <span data-ttu-id="af64b-126">"Wsdl"および"op"パラメーターが強調表示されます。</span><span class="sxs-lookup"><span data-stu-id="af64b-126">The "wsdl" and "op" parameters are highlighted.</span></span>  
  
```  
"oracledb://ADAPTER?wsdl&op=http://Microsoft.LobServices.OracleDB/2007/03/SCOTT/Table/EMP/Insert&op=http://Microsoft.LobServices.OracleDB/2007/03/SCOTT/Table/EMP/Delete"  
```  
  
> [!NOTE]
>  <span data-ttu-id="af64b-127">POLLINGSTMT 操作に対して生成された名前空間を変更する場合は、クエリ文字列に PollingId パラメーターを指定する必要があります。</span><span class="sxs-lookup"><span data-stu-id="af64b-127">If you want to modify the namespace generated for the POLLINGSTMT operation you should specify a PollingId parameter in the query string.</span></span>  
  
 <span data-ttu-id="af64b-128">この接続 URI を渡す方法を**MetadataExchangeClient**クライアントを作成して、アダプターからのメタデータの取得に使用するオーバー ロードされたメソッドのうちに依存します。</span><span class="sxs-lookup"><span data-stu-id="af64b-128">How you pass this connection URI to the **MetadataExchangeClient** depends on which of the overloaded methods you use to create the client and retrieve metadata from the adapter.</span></span>  
  
 <span data-ttu-id="af64b-129">Oracle の接続 URI の詳細については、次を参照してください。 [Oracle Database 接続 URI を作成する](../../adapters-and-accelerators/adapter-oracle-database/create-the-oracle-database-connection-uri.md)です。</span><span class="sxs-lookup"><span data-stu-id="af64b-129">For more information about the Oracle connection URI, see [Create the Oracle Database connection URI](../../adapters-and-accelerators/adapter-oracle-database/create-the-oracle-database-connection-uri.md).</span></span>  
  
### <a name="binding-properties"></a><span data-ttu-id="af64b-130">バインドのプロパティ</span><span class="sxs-lookup"><span data-stu-id="af64b-130">Binding Properties</span></span>  
 <span data-ttu-id="af64b-131">作成するときに、 **MetadataExchangeClient**を指定する必要があります、 **OracleDBBinding**です。</span><span class="sxs-lookup"><span data-stu-id="af64b-131">When you create the **MetadataExchangeClient**, you must specify an **OracleDBBinding**.</span></span>  
  
 <span data-ttu-id="af64b-132">アダプターがメタデータを生成する方法に影響を与えるいくつかのバインド プロパティがあります。</span><span class="sxs-lookup"><span data-stu-id="af64b-132">There are several binding properties that affect how the adapter generates metadata.</span></span> <span data-ttu-id="af64b-133">これらのプロパティは次のとおりです。</span><span class="sxs-lookup"><span data-stu-id="af64b-133">These properties are:</span></span>  
  
-   <span data-ttu-id="af64b-134">**EnableSafeTyping**</span><span class="sxs-lookup"><span data-stu-id="af64b-134">**EnableSafeTyping**</span></span>  
  
-   <span data-ttu-id="af64b-135">**UseSchemaInNamespace**</span><span class="sxs-lookup"><span data-stu-id="af64b-135">**UseSchemaInNamespace**</span></span>  
  
-   <span data-ttu-id="af64b-136">**PollingStatement**</span><span class="sxs-lookup"><span data-stu-id="af64b-136">**PollingStatement**</span></span>  
  
> [!IMPORTANT]
>  <span data-ttu-id="af64b-137">設定する必要があります、POLLINGSTMT 操作のメタデータを取得する場合、 **PollingStatement**プロパティをバインドします。</span><span class="sxs-lookup"><span data-stu-id="af64b-137">If you want to retrieve metadata for the POLLINGSTMT operation you must set the **PollingStatement** binding property.</span></span>  
  
 <span data-ttu-id="af64b-138">呼び出す前に、アプリケーションに必要な値をこれらのバインディング プロパティを設定することを確認する必要があります、 **GetMetadata**メソッドを**MetadataExchangeClient**です。</span><span class="sxs-lookup"><span data-stu-id="af64b-138">You should ensure that these binding properties are set to the values required for your application before you invoke the **GetMetadata** method on the **MetadataExchangeClient**.</span></span> <span data-ttu-id="af64b-139">詳細については、[!INCLUDE[adapteroracle_short](../../includes/adapteroracle-short-md.md)]バインドのプロパティを参照してください[Oracle データベース アダプターのバインドのプロパティについてお読み](../../adapters-and-accelerators/adapter-oracle-database/read-about-the-oracle-database-adapter-binding-properties.md)です。</span><span class="sxs-lookup"><span data-stu-id="af64b-139">For more information about the [!INCLUDE[adapteroracle_short](../../includes/adapteroracle-short-md.md)] binding properties, see [Read about the Oracle Database adapter binding properties](../../adapters-and-accelerators/adapter-oracle-database/read-about-the-oracle-database-adapter-binding-properties.md).</span></span>  
  
### <a name="example"></a><span data-ttu-id="af64b-140">例</span><span class="sxs-lookup"><span data-stu-id="af64b-140">Example</span></span>  
 <span data-ttu-id="af64b-141">次の例では、 **MetadataExchangeClient**を Insert、Update、Delete、および、SCOTT に対する Select 操作のサービスの説明 (WSDL ドキュメント) を作成します。EMP テーブルです。</span><span class="sxs-lookup"><span data-stu-id="af64b-141">The following example uses a **MetadataExchangeClient** to create a service description (WSDL document) for the Insert, Update, Delete, and Select operations on the SCOTT.EMP table.</span></span> <span data-ttu-id="af64b-142">WSDL は、ファイル、EmpOperations.wsdl に保存されます。</span><span class="sxs-lookup"><span data-stu-id="af64b-142">The WSDL is saved to a file, EmpOperations.wsdl.</span></span>  
  
```  
using System;  
using System.Collections.Generic;  
using System.Text;  
using System.Collections.ObjectModel;  
  
// Needed for WCF and Oracle Adapter  
using System.ServiceModel;  
using Microsoft.ServiceModel.Channels;  
using Microsoft.Adapters.OracleDB;  
  
// Needced for MetadataExchangeClient class  
using System.ServiceModel.Description;  
// Needed for ServiceDescription class  
using System.Web.Services;  
  
namespace OracleMetadataExchange  
{  
    class Program  
    {  
        static void Main(string[] args)  
        {  
            //create a binding  
            OracleDBBinding binding = new OracleDBBinding();  
  
            //create a metadata exchange client that will retrieve metadata according to the WS-MEX standard  
            MetadataExchangeClient client = new MetadataExchangeClient(binding);  
            client.SoapCredentials.UserName.UserName = "SCOTT";  
            client.SoapCredentials.UserName.Password = "TIGER";  
  
            //set up an endpoint address and specifies the operations for which we want metadata  
            string connectionUri = "oracledb://ADAPTER?wsdl"  
                + "&op="  
                + "http://Microsoft.LobServices.OracleDB/2007/03/SCOTT/Table/EMP/Insert"  
                + "&op="  
                + "http://Microsoft.LobServices.OracleDB/2007/03/SCOTT/Table/EMP/Update"  
                + "&op="  
                + "http://Microsoft.LobServices.OracleDB/2007/03/SCOTT/Table/EMP/Delete"  
                + "&op="  
                + "http://Microsoft.LobServices.OracleDB/2007/03/SCOTT/Table/EMP/Select";  
  
            EndpointAddress address = new EndpointAddress(connectionUri);  
  
            //get the metadata  
            MetadataSet ms = client.GetMetadata(address);  
  
            // Check for the metadata set size   
            Collection<MetadataSection> documentCollection = ms.MetadataSections;  
            if (documentCollection != null && documentCollection.Count > 0)  
            {  
                //get the wsdl from the metadata set  
                System.Web.Services.Description.ServiceDescription wsdl = (System.Web.Services.Description.ServiceDescription)documentCollection[0].Metadata;  
  
                //save the wsdl to a file  
                wsdl.Write("EmpOperations.wsdl");  
  
            }  
  
        }  
    }  
}  
```  
  
## <a name="see-also"></a><span data-ttu-id="af64b-143">参照</span><span class="sxs-lookup"><span data-stu-id="af64b-143">See Also</span></span>  
 [<span data-ttu-id="af64b-144">Oracle データベースからメタデータをプログラムで取得します。</span><span class="sxs-lookup"><span data-stu-id="af64b-144">Get Metadata Programmatically from the Oracle Database</span></span>](../../adapters-and-accelerators/adapter-oracle-database/get-metadata-programmatically-from-the-oracle-database.md)