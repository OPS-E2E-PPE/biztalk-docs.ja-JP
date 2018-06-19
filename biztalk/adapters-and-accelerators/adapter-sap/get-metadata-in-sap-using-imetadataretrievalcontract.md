---
title: IMetadataRetrievalContract を使用して SAP のメタデータの取得 |Microsoft ドキュメント
ms.custom: ''
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: ''
ms.suite: ''
ms.tgt_pltfrm: ''
ms.topic: article
helpviewer_keywords:
- how to, search metadata
- searching metadata
- how to, browse metadata
- browsing metadata
ms.assetid: 0944fc39-9ee5-4702-8b52-e0bc87f202c6
caps.latest.revision: 5
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: efa36eee26dd9467a71f7e8dd4d28d2e37e26606
ms.sourcegitcommit: cb908c540d8f1a692d01dc8f313e16cb4b4e696d
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 09/20/2017
ms.locfileid: "22218274"
---
# <a name="get-metadata-in-sap-using-imetadataretrievalcontract"></a><span data-ttu-id="1129c-102">IMetadataRetrievalContract を使用して SAP のメタデータを取得します。</span><span class="sxs-lookup"><span data-stu-id="1129c-102">Get Metadata in SAP using IMetadataRetrievalContract</span></span>
<span data-ttu-id="1129c-103">[!INCLUDE[adaptersap](../../includes/adaptersap-md.md)]公開、 **IMetadataRetrievalContract**は Web サービス記述言語 (WSDL) ドキュメントの形式でメタデータを取得して SAP システムのアイテムを検索および参照を使用できるエンドポイント操作です。</span><span class="sxs-lookup"><span data-stu-id="1129c-103">The [!INCLUDE[adaptersap](../../includes/adaptersap-md.md)] exposes an **IMetadataRetrievalContract**endpoint that you can use to browse and search for SAP system artifacts and to retrieve metadata in the form of a Web Services Description Language (WSDL) document for operations.</span></span>  
  
 <span data-ttu-id="1129c-104">**IMetadataRetrievalContract**インターフェイスは、[!INCLUDE[afproductnamelong](../../includes/afproductnamelong-md.md)]とメタデータの参照、検索、および検索の機能を提供します。</span><span class="sxs-lookup"><span data-stu-id="1129c-104">The **IMetadataRetrievalContract** interface is implemented by the [!INCLUDE[afproductnamelong](../../includes/afproductnamelong-md.md)] and provides metadata browse, search, and retrieval capabilities.</span></span> <span data-ttu-id="1129c-105">加え、 **IMetadataRetrievalContract** 、インターフェイス、[!INCLUDE[afproductnameshort](../../includes/afproductnameshort-md.md)]公開、 **MetadataRetrievalClient**インターフェイスを実装するクラス。</span><span class="sxs-lookup"><span data-stu-id="1129c-105">In addition to the **IMetadataRetrievalContract** interface, the [!INCLUDE[afproductnameshort](../../includes/afproductnameshort-md.md)] exposes the **MetadataRetrievalClient** class, which implements the interface.</span></span> <span data-ttu-id="1129c-106">使用するか、 **IMetadataRetrievalContract**チャネルまたは**MetadataRetrievalClient**を使用するメタデータ; 参照、検索、およびメタデータを取得する公開されたメソッドは各ケースで同じです。</span><span class="sxs-lookup"><span data-stu-id="1129c-106">You can use either an **IMetadataRetrievalContract** channel or a **MetadataRetrievalClient** to work with metadata; the methods exposed to browse, search, and retrieve metadata are the same in each case.</span></span>  
  
 <span data-ttu-id="1129c-107">次のセクションでは、使用する方法に関する情報を提供する、 **IMetadataRetrievalContract**インターフェイスです。</span><span class="sxs-lookup"><span data-stu-id="1129c-107">The following sections provide information about how to use the **IMetadataRetrievalContract** interface.</span></span>  
  
## <a name="the-imetadataretrievalcontract-interface"></a><span data-ttu-id="1129c-108">IMetadataRetrievalContract インターフェイス</span><span class="sxs-lookup"><span data-stu-id="1129c-108">The IMetadataRetrievalContract Interface</span></span>  
 <span data-ttu-id="1129c-109">次の表を使用するときに使用される重要なクラスに関する情報を提供する、 **IMetadataRetrievalContract**インターフェイスです。</span><span class="sxs-lookup"><span data-stu-id="1129c-109">The following table provides information about important classes that are used when you work with the **IMetadataRetrievalContract** interface.</span></span>  
  
|<span data-ttu-id="1129c-110">クラスまたはインターフェイス</span><span class="sxs-lookup"><span data-stu-id="1129c-110">Class or Interface</span></span>|<span data-ttu-id="1129c-111">Description</span><span class="sxs-lookup"><span data-stu-id="1129c-111">Description</span></span>|  
|------------------------|-----------------|  
|<span data-ttu-id="1129c-112">**IMetadataRetrievalContract**インターフェイス</span><span class="sxs-lookup"><span data-stu-id="1129c-112">**IMetadataRetrievalContract** interface</span></span><br /><br /> <span data-ttu-id="1129c-113">(Microsoft.ServiceModel.Channels)</span><span class="sxs-lookup"><span data-stu-id="1129c-113">(Microsoft.ServiceModel.Channels)</span></span>|<span data-ttu-id="1129c-114">定義、**参照**、**検索**、および**GetMetadata**メソッドです。</span><span class="sxs-lookup"><span data-stu-id="1129c-114">Defines the **Browse**, **Search**, and **GetMetadata** methods.</span></span> <span data-ttu-id="1129c-115">いずれかを使用してこれらのメソッドを呼び出す、 **IMetadataRetrievalContract**チャネルまたは**MetadataRetrievalClient**アダプター メタデータを使用します。</span><span class="sxs-lookup"><span data-stu-id="1129c-115">You invoke these methods either by using an **IMetadataRetrievalContract** channel or a **MetadataRetrievalClient** to work with adapter metadata.</span></span>|  
|<span data-ttu-id="1129c-116">**MetadataRetrievalClient**クラス</span><span class="sxs-lookup"><span data-stu-id="1129c-116">**MetadataRetrievalClient** class</span></span><br /><br /> <span data-ttu-id="1129c-117">(Microsoft.ServiceModel.Channels)</span><span class="sxs-lookup"><span data-stu-id="1129c-117">(Microsoft.ServiceModel.Channels)</span></span>|<span data-ttu-id="1129c-118">実装して、 **IMetadataRetrievalContract**インターフェイスです。</span><span class="sxs-lookup"><span data-stu-id="1129c-118">Implements the **IMetadataRetrievalContract** interface.</span></span> <span data-ttu-id="1129c-119">このクラスのインスタンスを作成し、提供することで、SAP システムのように構成することができます、 **SAPBinding**と**EndpointAddress**です。</span><span class="sxs-lookup"><span data-stu-id="1129c-119">You can create an instance of this class and configure it for your SAP system by providing an **SAPBinding** and an **EndpointAddress**.</span></span> <span data-ttu-id="1129c-120">メタデータを使用するには、そのメソッドを呼び出すことができます。</span><span class="sxs-lookup"><span data-stu-id="1129c-120">Then you can invoke its methods to work with metadata.</span></span>|  
|<span data-ttu-id="1129c-121">**MetadataRetrievalNode**クラス</span><span class="sxs-lookup"><span data-stu-id="1129c-121">**MetadataRetrievalNode** class</span></span><br /><br /> <span data-ttu-id="1129c-122">(Microsoft.ServiceModel.Channels)</span><span class="sxs-lookup"><span data-stu-id="1129c-122">(Microsoft.ServiceModel.Channels)</span></span>|<span data-ttu-id="1129c-123">アダプター メタデータのノードを表します。</span><span class="sxs-lookup"><span data-stu-id="1129c-123">Represents a metadata node on the adapter.</span></span> <span data-ttu-id="1129c-124">**参照**と**検索**メソッドには、この種類のノードが返されます、 **GetMetadata**メソッドには、パラメーターとしてこの型のノードです。</span><span class="sxs-lookup"><span data-stu-id="1129c-124">The **Browse** and **Search** methods return nodes of this type, and the **GetMetadata** method takes nodes of this type as a parameter.</span></span>|  
|<span data-ttu-id="1129c-125">**ServiceDescription**クラス</span><span class="sxs-lookup"><span data-stu-id="1129c-125">**ServiceDescription** class</span></span><br /><br /> <span data-ttu-id="1129c-126">(System.Web.Services.Description)</span><span class="sxs-lookup"><span data-stu-id="1129c-126">(System.Web.Services.Description)</span></span>|<span data-ttu-id="1129c-127">作成および有効な WSDL ドキュメント ファイルの書式設定する手段を提供します。</span><span class="sxs-lookup"><span data-stu-id="1129c-127">Provides a means of creating and formatting a valid WSDL document file.</span></span> <span data-ttu-id="1129c-128">**GetMetadata**メソッドを返します、 **ServiceDescription**オブジェクト。</span><span class="sxs-lookup"><span data-stu-id="1129c-128">The **GetMetadata** method returns a **ServiceDescription** object.</span></span>|  
  
 <span data-ttu-id="1129c-129">詳細については、 **IMetadataRetrievalContract** 、インターフェイス、 **MetadataRetrievalClient**クラス、および**MetadataRetrievalNode**クラスは、を参照してください**Microsoft.ServiceModel.Channels**での参照をマネージ[http://go.microsoft.com/fwlink/?LinkId=105566](http://go.microsoft.com/fwlink/?LinkId=105566)です。</span><span class="sxs-lookup"><span data-stu-id="1129c-129">For more information about the **IMetadataRetrievalContract** interface, the **MetadataRetrievalClient** class, and the **MetadataRetrievalNode** class; see the **Microsoft.ServiceModel.Channels** managed reference at [http://go.microsoft.com/fwlink/?LinkId=105566](http://go.microsoft.com/fwlink/?LinkId=105566).</span></span>  
  
### <a name="metadata-node-ids"></a><span data-ttu-id="1129c-130">メタデータのノード Id</span><span class="sxs-lookup"><span data-stu-id="1129c-130">Metadata Node IDs</span></span>  
 <span data-ttu-id="1129c-131">アダプターは、ノードの階層ツリーとしてそのメタデータを整理します。</span><span class="sxs-lookup"><span data-stu-id="1129c-131">The adapter organizes its metadata as a hierarchical tree of nodes.</span></span> <span data-ttu-id="1129c-132">このツリー構造内では、メタデータのノードの 2 つの種類があります。</span><span class="sxs-lookup"><span data-stu-id="1129c-132">Within this tree structure there are two types of metadata nodes:</span></span>  
  
-   <span data-ttu-id="1129c-133">**操作のノード**SAP アイテムで、アダプターを表示する操作を表します。</span><span class="sxs-lookup"><span data-stu-id="1129c-133">**Operation nodes** represent operations that the adapter surfaces on SAP artifacts.</span></span> <span data-ttu-id="1129c-134">操作のノードは、ツリーのリーフです。</span><span class="sxs-lookup"><span data-stu-id="1129c-134">Operation nodes are the leaves of the tree.</span></span>  
  
-   <span data-ttu-id="1129c-135">**カテゴリ ノード**アダプターでの操作に SAP アイテムと直接対応しない SAP アイテムのグループを表します。</span><span class="sxs-lookup"><span data-stu-id="1129c-135">**Category nodes** represent SAP artifacts and groupings of SAP artifacts that do not directly correspond to an operation on the adapter.</span></span> <span data-ttu-id="1129c-136">カテゴリのノードがツリーの分岐その他のカテゴリ ノードおよび操作のノードが含まれます。</span><span class="sxs-lookup"><span data-stu-id="1129c-136">Category nodes are the branches of the tree; they contain other category nodes and/or operation nodes.</span></span> <span data-ttu-id="1129c-137">たとえば、RFC 機能グループまたは SAP ビジネス オブジェクトは、カテゴリのノードとして表されます。</span><span class="sxs-lookup"><span data-stu-id="1129c-137">For example, RFC functional groups or SAP business objects are represented as category nodes.</span></span>  
  
 <span data-ttu-id="1129c-138">アダプター メタデータの各ノードが一意のノード ID で識別されます。</span><span class="sxs-lookup"><span data-stu-id="1129c-138">Each metadata node surfaced by the adapter is identified by a unique node ID.</span></span> <span data-ttu-id="1129c-139">メタデータのノード、アダプターによって公開される Id の詳細については、次を参照してください。[メタデータのノード Id](../../adapters-and-accelerators/adapter-sap/metadata-node-ids4.md)です。</span><span class="sxs-lookup"><span data-stu-id="1129c-139">For more information about the metadata node IDs surfaced by the adapter, see [Metadata Node IDs](../../adapters-and-accelerators/adapter-sap/metadata-node-ids4.md).</span></span> <span data-ttu-id="1129c-140">これらのノード Id を使用して使用すると、ターゲット SAP アイテムを指定する、 **IMetadataRetrievalContract**インターフェイスを参照、検索、およびメタデータを取得します。</span><span class="sxs-lookup"><span data-stu-id="1129c-140">You use these node IDs to specify target SAP artifacts when you use the **IMetadataRetrievalContract** interface to browse, search, and retrieve metadata.</span></span> <span data-ttu-id="1129c-141">定義されている定数を使用することができます`Microsoft.Adapters.SAP.SAPAdapterConstants.MetadataConstants`と`Microsoft.Adapters.SAP.SAPAdapterConstants.ActionConstants`メタデータ ノード Id を構築するためです。</span><span class="sxs-lookup"><span data-stu-id="1129c-141">You can use the constants defined in `Microsoft.Adapters.SAP.SAPAdapterConstants.MetadataConstants` and `Microsoft.Adapters.SAP.SAPAdapterConstants.ActionConstants` to help you construct metadata node IDs.</span></span>  
  
### <a name="binding-properties"></a><span data-ttu-id="1129c-142">バインドのプロパティ</span><span class="sxs-lookup"><span data-stu-id="1129c-142">Binding Properties</span></span>  
 <span data-ttu-id="1129c-143">使用するかどうか、 **IMetadataRetrievalContract**チャネルまたは**IMetadataRetrievalClient**メタデータを使用する必要がありますを指定する、 **SAPBinding**を作成する場合、インスタンス。</span><span class="sxs-lookup"><span data-stu-id="1129c-143">Whether you use an **IMetadataRetrievalContract** channel or an **IMetadataRetrievalClient** to work with metadata, you must specify an **SAPBinding** when you create the instance.</span></span>  
  
 <span data-ttu-id="1129c-144">アダプターがメタデータを生成する方法に影響を与えるいくつかのバインド プロパティがあります。</span><span class="sxs-lookup"><span data-stu-id="1129c-144">There are several binding properties that affect how the adapter generates metadata.</span></span> <span data-ttu-id="1129c-145">これらのプロパティは次のとおりです。</span><span class="sxs-lookup"><span data-stu-id="1129c-145">These properties are:</span></span>  
  
-   <span data-ttu-id="1129c-146">**GenerateFlatfileCompatibleIdocSchema**</span><span class="sxs-lookup"><span data-stu-id="1129c-146">**GenerateFlatfileCompatibleIdocSchema**</span></span>  
  
-   <span data-ttu-id="1129c-147">**ReceiveIDocFormat**</span><span class="sxs-lookup"><span data-stu-id="1129c-147">**ReceiveIDocFormat**</span></span>  
  
-   <span data-ttu-id="1129c-148">**EnableSafeTyping**</span><span class="sxs-lookup"><span data-stu-id="1129c-148">**EnableSafeTyping**</span></span>  
  
-   <span data-ttu-id="1129c-149">**FlatFileSegmentIndicator**</span><span class="sxs-lookup"><span data-stu-id="1129c-149">**FlatFileSegmentIndicator**</span></span>  
  
 <span data-ttu-id="1129c-150">メタデータの取得オブジェクトを開く前に、アプリケーションに必要な値をこれらのバインディング プロパティを設定することを確認する必要があります。</span><span class="sxs-lookup"><span data-stu-id="1129c-150">You should ensure that these binding properties are set to the values required for your application before you open the metadata retrieval object.</span></span> <span data-ttu-id="1129c-151">SAP アダプターのバインドのプロパティの詳細については、次を参照してください。 [mySAP Business Suite バインド プロパティの BizTalk アダプターの説明を読む](../../adapters-and-accelerators/adapter-sap/read-about-biztalk-adapter-for-mysap-business-suite-binding-properties.md)です。</span><span class="sxs-lookup"><span data-stu-id="1129c-151">For more information about the SAP adapter binding properties, see [Read about  BizTalk Adapter for mySAP Business Suite Binding Properties](../../adapters-and-accelerators/adapter-sap/read-about-biztalk-adapter-for-mysap-business-suite-binding-properties.md).</span></span>  
  
### <a name="browsing-metadata-nodes"></a><span data-ttu-id="1129c-152">メタデータのノードを参照</span><span class="sxs-lookup"><span data-stu-id="1129c-152">Browsing Metadata Nodes</span></span>  
 <span data-ttu-id="1129c-153">使用する、**参照**を親ノードに含まれているすべてのメタデータのノードを返すメソッド。</span><span class="sxs-lookup"><span data-stu-id="1129c-153">You use the **Browse** method to return all the metadata nodes that are contained in a parent node.</span></span> <span data-ttu-id="1129c-154">次の例は、SAP システムでは、最初の 3 つの RFC 機能グループの参照します。</span><span class="sxs-lookup"><span data-stu-id="1129c-154">The following example browses for the first three RFC functional groups on the SAP system.</span></span> <span data-ttu-id="1129c-155">この例では**クライアント**のインスタンスは、 **MetadataRetrievalClient**です。</span><span class="sxs-lookup"><span data-stu-id="1129c-155">In this example, **client** is an instance of **MetadataRetrievalClient**.</span></span>  
  
```  
// The first parameter is the node ID.   
// The second parameter is the start index.  
// The third parameter is the maximum number of nodes to return.  
IMetadataRetrievalNode[] nodes = client.Browse(Microsoft.Adapters.SAP.SAPAdapterConstants.MetadataConstants.RfcSection, 0, 3);  
```  
  
> [!IMPORTANT]
>  <span data-ttu-id="1129c-156">カテゴリのノードを参照することができますのみ操作のノードを参照することはできません。</span><span class="sxs-lookup"><span data-stu-id="1129c-156">You can only browse category nodes; you cannot browse operation nodes.</span></span>  
  
### <a name="searching-for-metadata-nodes"></a><span data-ttu-id="1129c-157">メタデータのノードの検索</span><span class="sxs-lookup"><span data-stu-id="1129c-157">Searching for Metadata Nodes</span></span>  
 <span data-ttu-id="1129c-158">使用する、**検索**の親ノードに含まれるノードの検索を実行するメソッド。</span><span class="sxs-lookup"><span data-stu-id="1129c-158">You use the **Search** method to perform a search for nodes contained by a parent node.</span></span> <span data-ttu-id="1129c-159">アスタリスクを指定することができます (\*) ワイルドカード文字です。</span><span class="sxs-lookup"><span data-stu-id="1129c-159">You can specify the asterisk (\*) wildcard character.</span></span> <span data-ttu-id="1129c-160">この文字は、0 個以上の文字と一致します。</span><span class="sxs-lookup"><span data-stu-id="1129c-160">This character matches zero or more characters.</span></span> <span data-ttu-id="1129c-161">次の例は、文字列"BAPI"が含まれるすべての Rfc の検索を示しています。</span><span class="sxs-lookup"><span data-stu-id="1129c-161">The following example shows a search for all RFCs that contain the string "BAPI".</span></span> <span data-ttu-id="1129c-162">この例では**クライアント**のインスタンスは、 **MetadataRetrievalClient**です。</span><span class="sxs-lookup"><span data-stu-id="1129c-162">In this example, **client** is an instance of **MetadataRetrievalClient**.</span></span>  
  
```  
// Search for all nodes that contain "BAPI" under the RFC node.  
// The parameters are the parent node ID, the search expression, and   
// the maximum number of nodes to return.  
IMetadataRetrievalNode[] nodes = client.Search(Microsoft.Adapters.SAP.SAPAdapterConstants.MetadataConstants.RfcSection, "*BAPI*", int.MaxValue);  
```  
  
> [!IMPORTANT]
>  <span data-ttu-id="1129c-163">検索は、限られた一連のノードでのみサポートされます。</span><span class="sxs-lookup"><span data-stu-id="1129c-163">Searching is only supported on a limited set of nodes.</span></span> <span data-ttu-id="1129c-164">検索式でサポートされているワイルドカード文字および検索がサポートされているノードに関する詳細については、次を参照してください。[メタデータのノード Id](../../adapters-and-accelerators/adapter-sap/metadata-node-ids4.md)です。</span><span class="sxs-lookup"><span data-stu-id="1129c-164">For more information about the nodes on which search is supported and about the wildcard character supported in search expressions, see [Metadata Node IDs](../../adapters-and-accelerators/adapter-sap/metadata-node-ids4.md).</span></span>  
  
### <a name="retrieving-metadata-wsdl-for-operations"></a><span data-ttu-id="1129c-165">操作のメタデータ (WSDL) を取得します。</span><span class="sxs-lookup"><span data-stu-id="1129c-165">Retrieving Metadata (WSDL) for Operations</span></span>  
 <span data-ttu-id="1129c-166">使用する、 **GetMetadata**操作のノードのグループに対するサービスの説明 (WSDL ドキュメント) を取得します。</span><span class="sxs-lookup"><span data-stu-id="1129c-166">You use the **GetMetadata** method to retrieve a service description (WSDL document) for a group of operation nodes.</span></span> <span data-ttu-id="1129c-167">次の例では、BAPI_TRANSACTION_COMMIT RFC のサービスの説明を取得します。</span><span class="sxs-lookup"><span data-stu-id="1129c-167">The following example retrieves a service description for the BAPI_TRANSACTION_COMMIT RFC.</span></span> <span data-ttu-id="1129c-168">この例では**クライアント**のインスタンスは、 **MetadataRetrievalClient**です。</span><span class="sxs-lookup"><span data-stu-id="1129c-168">In this example, **client** is an instance of **MetadataRetrievalClient**.</span></span> <span data-ttu-id="1129c-169">操作ノードのノードの ID がその操作の操作のメッセージと同じことに注意してください。</span><span class="sxs-lookup"><span data-stu-id="1129c-169">Note that the node ID for an operation node is equivalent to the message action for that operation.</span></span>  
  
```  
// Get a WSDL document that specifies a contract that contains the  
// BAPI_TRANSACTION_COMMIT operation.  
MetadataRetrievalNode[] nodes = new MetadataRetrievalNode[1];  
nodes[0] = new MetadataRetrievalNode();  
nodes[0].NodeId = Microsoft.Adapters.SAP.SAPAdapterConstants.ActionConstants.RfcActionPrefix + "BAPI_TRANSACTION_COMMIT";  
nodes[0].IsOperation = true;  
  
System.Web.Services.Description.ServiceDescription description = client.GetMetadata(nodes);  
```  
  
> [!IMPORTANT]
>  <span data-ttu-id="1129c-170">内の操作のノードを指定する必要がありますのみ、 **GetMetadata**メソッドです。</span><span class="sxs-lookup"><span data-stu-id="1129c-170">You should only specify operation nodes in the **GetMetadata** method.</span></span>  
  
### <a name="using-a-metadataretrievalclient"></a><span data-ttu-id="1129c-171">使用して、MetadataRetrievalClient</span><span class="sxs-lookup"><span data-stu-id="1129c-171">Using a MetadataRetrievalClient</span></span>  
 <span data-ttu-id="1129c-172">作成と使用、 **MetadataRetrievalClient**他の WCF クライアントは、ほぼ同じです。</span><span class="sxs-lookup"><span data-stu-id="1129c-172">Creating and using a **MetadataRetrievalClient** is much the same as any other WCF client.</span></span> <span data-ttu-id="1129c-173">エンドポイントとのインスタンスを指定して、クライアントを作成する**SAPBinding**です。</span><span class="sxs-lookup"><span data-stu-id="1129c-173">You create the client by specifying an endpoint and an instance of **SAPBinding**.</span></span> <span data-ttu-id="1129c-174">構成で宣言またはコードで強制的に、これを行うことができます。</span><span class="sxs-lookup"><span data-stu-id="1129c-174">You can do this either declaratively in configuration or imperatively in your code.</span></span> <span data-ttu-id="1129c-175">次のメソッドを呼び出し、 **MetadataRetrievalClient**を参照するには、検索、およびアダプターからメタデータを取得します。</span><span class="sxs-lookup"><span data-stu-id="1129c-175">You then invoke the methods of the **MetadataRetrievalClient** to browse, search, and retrieve metadata from the adapter.</span></span>  
  
 <span data-ttu-id="1129c-176">次の例を使用する方法を示しています、 **MetadataRetrievalClient**を参照するには、検索、およびメタデータを取得、[!INCLUDE[adaptersap_short](../../includes/adaptersap-short-md.md)]です。</span><span class="sxs-lookup"><span data-stu-id="1129c-176">The following example shows how to use a **MetadataRetrievalClient** to browse, search, and retrieve metadata from the [!INCLUDE[adaptersap_short](../../includes/adaptersap-short-md.md)].</span></span>  
  
```  
using System;  
using System.Collections.Generic;  
using System.Text;  
  
using System.ServiceModel;  
using Microsoft.Adapters.SAP;  
using Microsoft.ServiceModel.Channels;  
  
using System.Web.Services.Description;  
  
namespace SapMetaDataBrowseClient  
{  
    class NodeWriter  
    {  
        // This method writes the value of a collection of metadata retrieval nodes  
        // to the console.  
        public void Write(string title, MetadataRetrievalNode[] nodes)  
        {  
            Console.WriteLine(title);  
            Console.WriteLine();  
  
            //Write all the nodes returned to the console.  
            foreach (MetadataRetrievalNode node in nodes)  
            {  
                Console.WriteLine("NodeId = " + node.NodeId);  
                Console.WriteLine("\tDirection   = " + node.Direction.ToString());  
                Console.WriteLine("\tIsOperation = " + node.IsOperation.ToString());  
                Console.WriteLine("\tDisplayName = " + node.DisplayName);  
                Console.WriteLine("\tDescription = " + node.Description);  
            }  
            Console.WriteLine();  
        }  
    }  
  
    class Program  
    {  
        static void Main(string[] args)  
        {  
            MetadataRetrievalClient browser = null;  
            NodeWriter nodeWriter = new NodeWriter();  
  
            try  
            {  
                // Create a binding  
                SAPBinding binding = new SAPBinding();  
  
                EndpointAddress address = new EndpointAddress("sap://Client=800;lang=EN@A/YourSAPHost/00");  
  
                browser = new MetadataRetrievalClient(binding, address);  
                browser.ClientCredentials.UserName.UserName = "YourUserName";  
                browser.ClientCredentials.UserName.Password = "YourPassword";  
                browser.Open();  
  
                // Return the nodes directly under the root.  
                // The parameters are the parent node ID, the start index, and the maximum number  
                // of nodes to return.  
                MetadataRetrievalNode[] nodes = browser.Browse(MetadataRetrievalNode.Root.NodeId, 0, int.MaxValue);  
                nodeWriter.Write("Browse results for the root node:", nodes);  
  
                // Return first 3 RFC group nodes.  
                nodes = browser.Browse(Microsoft.Adapters.SAP.SAPAdapterConstants.MetadataConstants.RfcSection, 0, 3);  
                nodeWriter.Write(String.Format("Browse results for the first {1} nodes of {0}:", Microsoft.Adapters.SAP.SAPAdapterConstants.MetadataConstants.RfcSection, nodes.Length), nodes);  
  
                // Search for first 3 nodes that begin with "BAPI_TRANSACTION" under the RFC node.  
                // The parameters are the parent node ID, the search expression, and the maximum number  
                // of nodes to return.  
                nodes = browser.Search(Microsoft.Adapters.SAP.SAPAdapterConstants.MetadataConstants.RfcSection, "*BAPI_TRANSACTION*", 3);  
                nodeWriter.Write(String.Format("Search results for \"*BAPI_TRANSACTION*\" under {0} node:", Microsoft.Adapters.SAP.SAPAdapterConstants.MetadataConstants.RfcSection), nodes);  
  
                // Get a WSDL document that specifies a contract that contains the operations  
                // found in the search and write it to a file.  
                // You could explicitly specify operations as in the following:  
                //    nodes[0] = new MetadataRetrievalNode();  
                //    nodes[0].NodeId = Microsoft.Adapters.SAP.SAPAdapterConstants.ActionConstants.RfcActionPrefix + "BAPI_TRANSACTION_COMMIT";  
                //    nodes[0].IsOperation = true;  
                // Note that the operation NodeId is equivalent to the message action.  
                System.Web.Services.Description.ServiceDescription description = browser.GetMetadata(nodes);  
                description.Write("SampleContract.wsdl");  
            }  
            catch (Exception ex)  
            {  
                Console.WriteLine("Exception is: " + ex.Message);  
            }  
            finally  
            {  
                if (browser != null)  
                {  
                    if (browser.State == CommunicationState.Opened)  
                        browser.Close();  
                    else  
                        browser.Abort();  
                }  
            }  
        }  
    }  
}  
```  
  
 <span data-ttu-id="1129c-177">次のコンソールでこのプログラムの出力は、次に示します。</span><span class="sxs-lookup"><span data-stu-id="1129c-177">The following shows the output of this program on the console.</span></span> <span data-ttu-id="1129c-178">それぞれのメソッドに返されるメタデータの取得のノードの構造を確認できます。</span><span class="sxs-lookup"><span data-stu-id="1129c-178">You can see the structure of the metadata retrieval nodes returned for each method.</span></span> <span data-ttu-id="1129c-179">プログラムは、また、ファイルを検索によって返されるノードで構成されるサービス コントラクトを説明する WSDL ドキュメントを書き込みます。</span><span class="sxs-lookup"><span data-stu-id="1129c-179">The program also writes a WSDL document that describes a service contract consisting of the nodes returned by the search to a file.</span></span> <span data-ttu-id="1129c-180">(ほとんどの SAP インストールでは、サービスの説明が含まれません、BAPI_TRANSACTION_COMMIT および BAPI_TRANSACTION_ROLLBACK 操作します。)</span><span class="sxs-lookup"><span data-stu-id="1129c-180">(For most SAP installations, the service description will contain the BAPI_TRANSACTION_COMMIT and BAPI_TRANSACTION_ROLLBACK operations.)</span></span>  
  
```  
Browse results for the root node:  
  
NodeId = http://Microsoft.LobServices.Sap/2007/03/BAPISECTION/000001  
        Direction   = Outbound  
        IsOperation = False  
        DisplayName = BAPI  
        Description = BAPI  
NodeId = http://Microsoft.LobServices.Sap/2007/03/IDOCSECTION/  
        Direction   = Inbound, Outbound  
        IsOperation = False  
        DisplayName = IDOC  
        Description = IDOC  
NodeId = http://Microsoft.LobServices.Sap/2007/03/RFCSECTION/  
        Direction   = Inbound, Outbound  
        IsOperation = False  
        DisplayName = RFC  
        Description = RFC  
NodeId = http://Microsoft.LobServices.Sap/2007/03/TRFCSECTION/  
        Direction   = Inbound, Outbound  
        IsOperation = False  
        DisplayName = TRFC  
        Description = TRFC  
  
Browse results for the first 3 nodes of http://Microsoft.LobServices.Sap/2007/03  
/RFCSECTION/:  
  
NodeId = http://Microsoft.LobServices.Sap/2007/03/RFCGROUP/A  
        Direction   = Inbound, Outbound  
        IsOperation = False  
        DisplayName = Asset Accounting  
        Description = Asset Accounting  
NodeId = http://Microsoft.LobServices.Sap/2007/03/RFCGROUP/S  
        Direction   = Inbound, Outbound  
        IsOperation = False  
        DisplayName = Basis  
        Description = Basis  
NodeId = http://Microsoft.LobServices.Sap/2007/03/RFCGROUP/B  
        Direction   = Inbound, Outbound  
        IsOperation = False  
        DisplayName = Business Information Warehouse  
        Description = Business Information Warehouse  
  
Search results for "*BAPI_TRANSACTION*" under http://Microsoft.LobServices.Sap/2  
007/03/RFCSECTION/ node:  
  
NodeId = http://Microsoft.LobServices.Sap/2007/03/Rfc/BAPI_TRANSACTION_COMMIT  
        Direction   = Inbound, Outbound  
        IsOperation = True  
        DisplayName = BAPI_TRANSACTION_COMMIT  
        Description = Execute external Commit when using BAPIs  
NodeId = http://Microsoft.LobServices.Sap/2007/03/Rfc/BAPI_TRANSACTION_ROLLBACK  
        Direction   = Inbound, Outbound  
        IsOperation = True  
        DisplayName = BAPI_TRANSACTION_ROLLBACK  
        Description = Execute external Rollback when using BAPIs  
  
```  
  
## <a name="using-an-imetadataretrievalcontract-channel"></a><span data-ttu-id="1129c-181">IMetadataRetrievalContract チャネルを使用します。</span><span class="sxs-lookup"><span data-stu-id="1129c-181">Using an IMetadataRetrievalContract Channel</span></span>  
 <span data-ttu-id="1129c-182">作成することも、 **IMetadataRetrievalContract**チャネルし、このチャネルを使用して、参照、検索、およびアダプターからメタデータを取得します。</span><span class="sxs-lookup"><span data-stu-id="1129c-182">You can also create an **IMetadataRetrievalContract** channel and then use this channel to browse, search, and retrieve metadata from the adapter.</span></span> <span data-ttu-id="1129c-183">(メソッドのシグネチャが同じである、 **MetadataRetrievalClient**クラスです)。その方法を次の例に示します。</span><span class="sxs-lookup"><span data-stu-id="1129c-183">(The method signatures are the same as for the **MetadataRetrievalClient** class.) The following example shows how to do this.</span></span>  
  
```  
…  
//Create a binding and endpoint address.  
SAPBinding binding = new SAPBinding();  
EndpointAddress address = new EndpointAddress("sap://Client=800;lang=EN@A/YourSAPHost/00");  
  
//Create and open a channel factory that will return an IMetadataRetrievalContract object, on which browse, search, and get can be performed.  
ChannelFactory<IMetadataRetrievalContract> factory = new ChannelFactory<IMetadataRetrievalContract>(binding, address);  
factory.Credentials.UserName.UserName = "YourUserName";  
factory.Credentials.UserName.Password = "YourPassword";  
factory.Open();  
  
//Obtain an IMetadataRetrievalContract channel from the factory.  
IMetadataRetrievalContract channel = factory.CreateChannel();  
  
//Perform a search using the channel.  
MetadataRetrievalNode[] nodes = channel.Search(Microsoft.Adapters.SAP.SAPAdapterConstants.MetadataConstants.RfcSection, "BAPI_TRANSACTION*", int.MaxValue);  
…  
```  
  
## <a name="see-also"></a><span data-ttu-id="1129c-184">参照</span><span class="sxs-lookup"><span data-stu-id="1129c-184">See Also</span></span>  
 [<span data-ttu-id="1129c-185">SAP からメタデータをプログラムで取得します。</span><span class="sxs-lookup"><span data-stu-id="1129c-185">Retrieving Metadata Programmatically from SAP</span></span>](../../adapters-and-accelerators/adapter-sap/get-metadata-programmatically-from-sap.md)