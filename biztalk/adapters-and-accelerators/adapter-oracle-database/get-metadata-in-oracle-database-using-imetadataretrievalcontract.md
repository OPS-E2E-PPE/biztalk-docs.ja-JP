---
title: IMetadataRetrievalContract を使用して Oracle データベースでメタデータの取得 |Microsoft Docs
ms.custom: ''
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: ''
ms.suite: ''
ms.tgt_pltfrm: ''
ms.topic: article
helpviewer_keywords:
- metadata, retrieving using IMetadataRetrievalContract
ms.assetid: 7d32694f-4384-4c2f-be72-ac52c7b2e9f5
caps.latest.revision: 4
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: b9510c7ae534251218826a31eea1cc39c8d1f139
ms.sourcegitcommit: 266308ec5c6a9d8d80ff298ee6051b4843c5d626
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 06/27/2018
ms.locfileid: "36977995"
---
# <a name="get-metadata-in-oracle-database-using-imetadataretrievalcontract"></a><span data-ttu-id="15bea-102">IMetadataRetrievalContract を使用して Oracle データベースでメタデータを取得します。</span><span class="sxs-lookup"><span data-stu-id="15bea-102">Get Metadata in Oracle Database Using IMetadataRetrievalContract</span></span>
<span data-ttu-id="15bea-103">[!INCLUDE[adapteroracle](../../includes/adapteroracle-md.md)]公開、 **IMetadataRetrievalContract**Oracle データベース アイテムを検索および参照して、フォームの Web サービス記述言語 (WSDL での操作のメタデータを取得するを使用するエンドポイント) ドキュメントです。</span><span class="sxs-lookup"><span data-stu-id="15bea-103">The [!INCLUDE[adapteroracle](../../includes/adapteroracle-md.md)] exposes an **IMetadataRetrievalContract**endpoint that you can use to browse and search for Oracle database artifacts and to retrieve metadata for operations in the form of a Web Services Description Language (WSDL) document.</span></span>  
  
 <span data-ttu-id="15bea-104">**IMetadataRetrievalContract**インターフェイスによって実装されます、[!INCLUDE[afproductnamelong](../../includes/afproductnamelong-md.md)]とメタデータの参照、検索、および検索機能を提供します。</span><span class="sxs-lookup"><span data-stu-id="15bea-104">The **IMetadataRetrievalContract** interface is implemented by the [!INCLUDE[afproductnamelong](../../includes/afproductnamelong-md.md)] and provides metadata browse, search, and retrieval capabilities.</span></span> <span data-ttu-id="15bea-105">加え、 **IMetadataRetrievalContract** 、インターフェイス、[!INCLUDE[afproductnameshort](../../includes/afproductnameshort-md.md)]公開、 **MetadataRetrievalClient**クラス、インターフェイスを実装します。</span><span class="sxs-lookup"><span data-stu-id="15bea-105">In addition to the **IMetadataRetrievalContract** interface, the [!INCLUDE[afproductnameshort](../../includes/afproductnameshort-md.md)] exposes the **MetadataRetrievalClient** class, which implements the interface.</span></span> <span data-ttu-id="15bea-106">いずれかを使用することができます、 **IMetadataRetrievalContract**チャネルまたは**MetadataRetrievalClient**を使用するメタデータ参照、検索、およびメタデータを取得する公開されたメソッドはいずれの場合も同じです。</span><span class="sxs-lookup"><span data-stu-id="15bea-106">You can use either an **IMetadataRetrievalContract** channel or a **MetadataRetrievalClient** to work with metadata; the methods exposed to browse, search, and retrieve metadata are the same in each case.</span></span>  
  
 <span data-ttu-id="15bea-107">次のセクションでは、使用する方法に関する情報を提供する、 **IMetadataRetrievalContract**インターフェイス。</span><span class="sxs-lookup"><span data-stu-id="15bea-107">The following sections provide information about how to use the **IMetadataRetrievalContract** interface.</span></span>  
  
## <a name="the-imetadataretrievalcontract-interface"></a><span data-ttu-id="15bea-108">IMetadataRetrievalContract インターフェイス</span><span class="sxs-lookup"><span data-stu-id="15bea-108">The IMetadataRetrievalContract Interface</span></span>  
 <span data-ttu-id="15bea-109">次の表を使用するときに使用される重要なクラスに関する情報を提供する、 **IMetadataRetrievalContract**インターフェイス。</span><span class="sxs-lookup"><span data-stu-id="15bea-109">The following table provides information about important classes that are used when you work with the **IMetadataRetrievalContract** interface.</span></span>  
  
|<span data-ttu-id="15bea-110">クラスまたはインターフェイス</span><span class="sxs-lookup"><span data-stu-id="15bea-110">Class or Interface</span></span>|<span data-ttu-id="15bea-111">説明</span><span class="sxs-lookup"><span data-stu-id="15bea-111">Description</span></span>|  
|------------------------|-----------------|  
|<span data-ttu-id="15bea-112">**IMetadataRetrievalContract**インターフェイス</span><span class="sxs-lookup"><span data-stu-id="15bea-112">**IMetadataRetrievalContract** interface</span></span><br /><br /> <span data-ttu-id="15bea-113">(Microsoft.ServiceModel.Channels)</span><span class="sxs-lookup"><span data-stu-id="15bea-113">(Microsoft.ServiceModel.Channels)</span></span>|<span data-ttu-id="15bea-114">定義、**参照**、**検索**、および**GetMetadata**メソッド。</span><span class="sxs-lookup"><span data-stu-id="15bea-114">Defines the **Browse**, **Search**, and **GetMetadata** methods.</span></span> <span data-ttu-id="15bea-115">いずれかを使用してこれらのメソッドを呼び出す、 **IMetadataRetrievalContract**チャネルまたは**MetadataRetrievalClient**アダプター メタデータを操作します。</span><span class="sxs-lookup"><span data-stu-id="15bea-115">You invoke these methods either by using an **IMetadataRetrievalContract** channel or a **MetadataRetrievalClient** to work with adapter metadata.</span></span>|  
|<span data-ttu-id="15bea-116">**MetadataRetrievalClient**クラス</span><span class="sxs-lookup"><span data-stu-id="15bea-116">**MetadataRetrievalClient** class</span></span><br /><br /> <span data-ttu-id="15bea-117">(Microsoft.ServiceModel.Channels)</span><span class="sxs-lookup"><span data-stu-id="15bea-117">(Microsoft.ServiceModel.Channels)</span></span>|<span data-ttu-id="15bea-118">実装、 **IMetadataRetrievalContract**インターフェイス。</span><span class="sxs-lookup"><span data-stu-id="15bea-118">Implements the **IMetadataRetrievalContract** interface.</span></span> <span data-ttu-id="15bea-119">このクラスのインスタンスを作成し、提供することで、Oracle データベース用に構成することができます、 **OracleDBBinding**と**EndpointAddress**します。</span><span class="sxs-lookup"><span data-stu-id="15bea-119">You can create an instance of this class and configure it for your Oracle database by providing an **OracleDBBinding** and an **EndpointAddress**.</span></span> <span data-ttu-id="15bea-120">メタデータを使用するには、そのメソッドを呼び出すことができます。</span><span class="sxs-lookup"><span data-stu-id="15bea-120">Then you can invoke its methods to work with metadata.</span></span>|  
|<span data-ttu-id="15bea-121">**MetadataRetrievalNode**クラス</span><span class="sxs-lookup"><span data-stu-id="15bea-121">**MetadataRetrievalNode** class</span></span><br /><br /> <span data-ttu-id="15bea-122">(Microsoft.ServiceModel.Channels)</span><span class="sxs-lookup"><span data-stu-id="15bea-122">(Microsoft.ServiceModel.Channels)</span></span>|<span data-ttu-id="15bea-123">アダプター メタデータのノードを表します。</span><span class="sxs-lookup"><span data-stu-id="15bea-123">Represents a metadata node on the adapter.</span></span> <span data-ttu-id="15bea-124">**参照**と**検索**メソッドは、この型のノードを返す、 **GetMetadata**メソッドはこの型をパラメーターとしてのノードを受け取ります。</span><span class="sxs-lookup"><span data-stu-id="15bea-124">The **Browse** and **Search** methods return nodes of this type, and the **GetMetadata** method takes nodes of this type as a parameter.</span></span>|  
|<span data-ttu-id="15bea-125">**ServiceDescription**クラス</span><span class="sxs-lookup"><span data-stu-id="15bea-125">**ServiceDescription** class</span></span><br /><br /> <span data-ttu-id="15bea-126">(System.Web.Services.Description)</span><span class="sxs-lookup"><span data-stu-id="15bea-126">(System.Web.Services.Description)</span></span>|<span data-ttu-id="15bea-127">作成および有効な WSDL ドキュメントのファイルを書式設定の手段を提供します。</span><span class="sxs-lookup"><span data-stu-id="15bea-127">Provides a means of creating and formatting a valid WSDL document file.</span></span> <span data-ttu-id="15bea-128">**GetMetadata**メソッドを返します。 を**ServiceDescription**オブジェクト。</span><span class="sxs-lookup"><span data-stu-id="15bea-128">The **GetMetadata** method returns a **ServiceDescription** object.</span></span>|  
  
 
### <a name="metadata-node-ids"></a><span data-ttu-id="15bea-129">メタデータ ノード Id</span><span class="sxs-lookup"><span data-stu-id="15bea-129">Metadata Node IDs</span></span>  
 <span data-ttu-id="15bea-130">アダプターは、ノードの階層ツリーとしてのメタデータを整理します。</span><span class="sxs-lookup"><span data-stu-id="15bea-130">The adapter organizes its metadata as a hierarchical tree of nodes.</span></span> <span data-ttu-id="15bea-131">このツリー構造内では、メタデータのノードの 2 つの種類があります。</span><span class="sxs-lookup"><span data-stu-id="15bea-131">Within this tree structure there are two types of metadata nodes:</span></span>  
  
- <span data-ttu-id="15bea-132">**操作のノード**Oracle データベース アイテムで、アダプターを表示する操作を表します。</span><span class="sxs-lookup"><span data-stu-id="15bea-132">**Operation nodes** represent operations that the adapter surfaces on Oracle database artifacts.</span></span> <span data-ttu-id="15bea-133">操作のノードでは、ツリーのリーフです。</span><span class="sxs-lookup"><span data-stu-id="15bea-133">Operation nodes are the leaves of the tree.</span></span>  
  
- <span data-ttu-id="15bea-134">**カテゴリ ノード**アダプターでの操作に Oracle データベース アイテムと直接対応している Oracle データベース アイテムのグループを表します。</span><span class="sxs-lookup"><span data-stu-id="15bea-134">**Category nodes** represent Oracle database artifacts and groupings of Oracle database artifacts that do not directly correspond to an operation on the adapter.</span></span> <span data-ttu-id="15bea-135">カテゴリのノードは、ツリーの分岐その他のカテゴリ ノードやノードの操作が含まれます。</span><span class="sxs-lookup"><span data-stu-id="15bea-135">Category nodes are the branches of the tree; they contain other category nodes and/or operation nodes.</span></span> <span data-ttu-id="15bea-136">たとえば、Oracle のテーブルおよびパッケージは、カテゴリのノードとして表されます。</span><span class="sxs-lookup"><span data-stu-id="15bea-136">For example, Oracle tables and packages are represented as category nodes.</span></span>  
  
  <span data-ttu-id="15bea-137">アダプター メタデータの各ノードは、一意のノード ID によって識別されます。</span><span class="sxs-lookup"><span data-stu-id="15bea-137">Each metadata node surfaced by the adapter is identified by a unique node ID.</span></span> <span data-ttu-id="15bea-138">メタデータ ノード Id のアダプターの詳細については、[メタデータ ノード Id](../../adapters-and-accelerators/adapter-oracle-database/metadata-node-ids3.md)を参照してください。</span><span class="sxs-lookup"><span data-stu-id="15bea-138">For more information about the metadata node IDs surfaced by the adapter, see [Metadata Node IDs](../../adapters-and-accelerators/adapter-oracle-database/metadata-node-ids3.md).</span></span> <span data-ttu-id="15bea-139">これらのノード Id を使用して、使用するときに、Oracle データベース アイテムのターゲットを指定する、 **IMetadataRetrievalContract**参照、検索、およびメタデータを取得するインターフェイス。</span><span class="sxs-lookup"><span data-stu-id="15bea-139">You use these node IDs to specify target Oracle database artifacts when you use the **IMetadataRetrievalContract** interface to browse, search, and retrieve metadata.</span></span>  
  
### <a name="binding-properties"></a><span data-ttu-id="15bea-140">バインドのプロパティ</span><span class="sxs-lookup"><span data-stu-id="15bea-140">Binding Properties</span></span>  
 <span data-ttu-id="15bea-141">使用するかどうか、 **IMetadataRetrievalContract**チャネルまたは**IMetadataRetrievalClient**メタデータを使用することを指定する必要があります、 **OracleDBBinding**ときにします。インスタンスを作成します。</span><span class="sxs-lookup"><span data-stu-id="15bea-141">Whether you use an **IMetadataRetrievalContract** channel or an **IMetadataRetrievalClient** to work with metadata, you must specify an **OracleDBBinding** when you create the instance.</span></span>  
  
 <span data-ttu-id="15bea-142">アダプターがメタデータを生成する方法に影響を与えるいくつかのバインド プロパティがあります。</span><span class="sxs-lookup"><span data-stu-id="15bea-142">There are several binding properties that affect how the adapter generates metadata.</span></span> <span data-ttu-id="15bea-143">これらのプロパティは次のとおりです。</span><span class="sxs-lookup"><span data-stu-id="15bea-143">These properties are:</span></span>  
  
-   <span data-ttu-id="15bea-144">**EnableSafeTyping**</span><span class="sxs-lookup"><span data-stu-id="15bea-144">**EnableSafeTyping**</span></span>  
  
-   <span data-ttu-id="15bea-145">**UseSchemaInNamespace**</span><span class="sxs-lookup"><span data-stu-id="15bea-145">**UseSchemaInNamespace**</span></span>  
  
-   <span data-ttu-id="15bea-146">**PollingStatement**</span><span class="sxs-lookup"><span data-stu-id="15bea-146">**PollingStatement**</span></span>  
  
> [!IMPORTANT]
>  <span data-ttu-id="15bea-147">設定する必要があります、POLLINGSTMT 操作のメタデータを取得する場合、 **PollingStatement**プロパティをバインドします。</span><span class="sxs-lookup"><span data-stu-id="15bea-147">If you want to retrieve metadata for the POLLINGSTMT operation you must set the **PollingStatement** binding property.</span></span>  
  
 <span data-ttu-id="15bea-148">これらのバインドのプロパティがメタデータの取得オブジェクトを開く前に、アプリケーションに必要な値に設定されているを確認してください。</span><span class="sxs-lookup"><span data-stu-id="15bea-148">You should ensure that these binding properties are set to the values required for your application before you open the metadata retrieval object.</span></span> <span data-ttu-id="15bea-149">詳細については、[!INCLUDE[adapteroracle_short](../../includes/adapteroracle-short-md.md)]バインドのプロパティを参照してください[Oracle データベース アダプターのバインドのプロパティについて](../../adapters-and-accelerators/adapter-oracle-database/read-about-the-oracle-database-adapter-binding-properties.md)します。</span><span class="sxs-lookup"><span data-stu-id="15bea-149">For more information about the [!INCLUDE[adapteroracle_short](../../includes/adapteroracle-short-md.md)] binding properties, see [Read about the Oracle Database adapter binding properties](../../adapters-and-accelerators/adapter-oracle-database/read-about-the-oracle-database-adapter-binding-properties.md).</span></span>  
  
### <a name="browsing-metadata-nodes"></a><span data-ttu-id="15bea-150">メタデータのノードを参照</span><span class="sxs-lookup"><span data-stu-id="15bea-150">Browsing Metadata Nodes</span></span>  
 <span data-ttu-id="15bea-151">使用する、**参照**を親ノードに含まれているすべてのメタデータのノードを返すメソッド。</span><span class="sxs-lookup"><span data-stu-id="15bea-151">You use the **Browse** method to return all the metadata nodes that are contained in a parent node.</span></span> <span data-ttu-id="15bea-152">次の例は、Oracle データベースで最初の 3 つのスキーマを参照します。</span><span class="sxs-lookup"><span data-stu-id="15bea-152">The following example browses for the first three schemas on the Oracle database.</span></span> <span data-ttu-id="15bea-153">この例で**クライアント**のインスタンスである**MetadataRetrievalClient**します。</span><span class="sxs-lookup"><span data-stu-id="15bea-153">In this example, **client** is an instance of **MetadataRetrievalClient**.</span></span>  
  
```  
// The first parameter is the node ID.   
// The second parameter is the start index.  
// The third parameter is the maximum number of nodes to return.  
                MetadataRetrievalNode[] nodes = client.Browse(MetadataRetrievalNode.Root.NodeId, 0, 3);  
```  
  
> [!IMPORTANT]
>  <span data-ttu-id="15bea-154">カテゴリのノードのみを参照できます。操作のノードを参照することはできません。</span><span class="sxs-lookup"><span data-stu-id="15bea-154">You can only browse category nodes; you cannot browse operation nodes.</span></span>  
  
### <a name="searching-for-metadata-nodes"></a><span data-ttu-id="15bea-155">メタデータのノードの検索</span><span class="sxs-lookup"><span data-stu-id="15bea-155">Searching for Metadata Nodes</span></span>  
 <span data-ttu-id="15bea-156">使用する、**検索**親ノードが格納されているノードの検索を実行するメソッド。</span><span class="sxs-lookup"><span data-stu-id="15bea-156">You use the **Search** method to perform a search for nodes contained by a parent node.</span></span> <span data-ttu-id="15bea-157">アダプターは、検索式です。 ワイルドカード文字をサポートしていますたとえばパーセント (%) を指定する 0 個以上の文字と一致するワイルドカード文字です。</span><span class="sxs-lookup"><span data-stu-id="15bea-157">The adapter supports wildcard characters in search expressions; for example you can specify the percent (%) wildcard character to match zero or more characters.</span></span> <span data-ttu-id="15bea-158">次の例では、文字列"EMP"が含まれる SCOTT スキーマ内のすべてのテーブルの検索を示します。</span><span class="sxs-lookup"><span data-stu-id="15bea-158">The following example shows a search for all the tables in the SCOTT schema that contain the string "EMP".</span></span> <span data-ttu-id="15bea-159">この例で**クライアント**のインスタンスである**MetadataRetrievalClient**します。</span><span class="sxs-lookup"><span data-stu-id="15bea-159">In this example, **client** is an instance of **MetadataRetrievalClient**.</span></span>  
  
```  
// Search for all nodes that contain "EMP" under the SCOTT.Table node.  
// The parameters are the parent node ID, the search expression, and   
// the maximum number of nodes to return.  
IMetadataRetrievalNode[] nodes = client.Search("http://Microsoft.LobServices.OracleDB/2007/03/SCOTT/Table", "%EMP%", 3);  
  
```  
  
> [!IMPORTANT]
>  <span data-ttu-id="15bea-160">検索は限られた一連のノードでのみサポートします。</span><span class="sxs-lookup"><span data-stu-id="15bea-160">Searching is only supported on a limited set of nodes.</span></span> <span data-ttu-id="15bea-161">検索式でサポートされているワイルドカード文字および検索がサポートされているノードに関する詳細については、[メタデータ ノード Id](../../adapters-and-accelerators/adapter-oracle-database/metadata-node-ids3.md)を参照してください。</span><span class="sxs-lookup"><span data-stu-id="15bea-161">For more information about the nodes on which search is supported and about the wildcard characters supported in search expressions, see [Metadata Node IDs](../../adapters-and-accelerators/adapter-oracle-database/metadata-node-ids3.md).</span></span>  
  
### <a name="retrieving-metadata-wsdl-for-operations"></a><span data-ttu-id="15bea-162">操作のメタデータ (WSDL) を取得します。</span><span class="sxs-lookup"><span data-stu-id="15bea-162">Retrieving Metadata (WSDL) for Operations</span></span>  
 <span data-ttu-id="15bea-163">使用する、 **GetMetadata**操作のノードのグループのサービスの説明 (WSDL ドキュメント) を取得します。</span><span class="sxs-lookup"><span data-stu-id="15bea-163">You use the **GetMetadata** method to retrieve a service description (WSDL document) for a group of operation nodes.</span></span> <span data-ttu-id="15bea-164">次の例では、サービスの説明を含むすべての操作をサーフェス、scott のアダプターを取得します。ノード ID を指定することで、EMP テーブル</span><span class="sxs-lookup"><span data-stu-id="15bea-164">The following example retrieves a service description that contains all of the operations that the adapter surfaces for the SCOTT.EMP table by specifying its node ID.</span></span> <span data-ttu-id="15bea-165">この例で**クライアント**のインスタンスである**MetadataRetrievalClient**します。</span><span class="sxs-lookup"><span data-stu-id="15bea-165">In this example, **client** is an instance of **MetadataRetrievalClient**.</span></span>  
  
```  
// Get a service description that contains all of the operations   
// surfaced for the SCOTT.EMP table. The IsOperation  
// property is set false because this is a category node.  
nodes = new MetadataRetrievalNode[1];  
nodes[0] = new MetadataRetrievalNode();  
nodes[0].NodeId = "http://Microsoft.LobServices.OracleDB/2007/03/SCOTT/Table/EMP";  
nodes[0].IsOperation = false;  
System.Web.Services.Description.ServiceDescription description = client.GetMetadata(nodes);  
  
```  
  
> [!IMPORTANT]
>  <span data-ttu-id="15bea-166">**IsOperation**プロパティはカテゴリのノードとノードの操作が true の場合は false を指定します。</span><span class="sxs-lookup"><span data-stu-id="15bea-166">The **IsOperation** property should be false for category nodes and true for operation nodes.</span></span>  
  
### <a name="using-a-metadataretrievalclient"></a><span data-ttu-id="15bea-167">MetadataRetrievalClient を使用します。</span><span class="sxs-lookup"><span data-stu-id="15bea-167">Using a MetadataRetrievalClient</span></span>  
 <span data-ttu-id="15bea-168">作成と使用、 **MetadataRetrievalClient**他の WCF クライアントをほぼ同じです。</span><span class="sxs-lookup"><span data-stu-id="15bea-168">Creating and using a **MetadataRetrievalClient** is much the same as any other WCF client.</span></span> <span data-ttu-id="15bea-169">エンドポイントとのインスタンスを指定してクライアントを作成する**OracleDBBinding**します。</span><span class="sxs-lookup"><span data-stu-id="15bea-169">You create the client by specifying an endpoint and an instance of **OracleDBBinding**.</span></span> <span data-ttu-id="15bea-170">構成で宣言またはコードで強制的に、これを行うことができます。</span><span class="sxs-lookup"><span data-stu-id="15bea-170">You can do this either declaratively in configuration or imperatively in your code.</span></span> <span data-ttu-id="15bea-171">メソッドを呼び出して、 **MetadataRetrievalClient**を参照するには、検索、およびアダプターからメタデータを取得します。</span><span class="sxs-lookup"><span data-stu-id="15bea-171">You then invoke the methods of the **MetadataRetrievalClient** to browse, search, and retrieve metadata from the adapter.</span></span>  
  
 <span data-ttu-id="15bea-172">次の例は、使用する方法を示します、 **MetadataRetrievalClient**を参照するには、検索、およびメタデータを取得、[!INCLUDE[adapteroracle_short](../../includes/adapteroracle-short-md.md)]します。</span><span class="sxs-lookup"><span data-stu-id="15bea-172">The following example shows how to use a **MetadataRetrievalClient** to browse, search, and retrieve metadata from the [!INCLUDE[adapteroracle_short](../../includes/adapteroracle-short-md.md)].</span></span> <span data-ttu-id="15bea-173">例を示します。</span><span class="sxs-lookup"><span data-stu-id="15bea-173">The example demonstrates:</span></span>  
  
-   <span data-ttu-id="15bea-174">Oracle データベース スキーマのメタデータのツリーのルート ノードを参照します。</span><span class="sxs-lookup"><span data-stu-id="15bea-174">Browsing the root node of the metadata tree for Oracle Database schemas.</span></span>  
  
-   <span data-ttu-id="15bea-175">名前に文字列"EMP"を含む SCOTT スキーマ内のテーブルを検索します。</span><span class="sxs-lookup"><span data-stu-id="15bea-175">Searching for the tables in the SCOTT schema with names that contain the string "EMP".</span></span>  
  
-   <span data-ttu-id="15bea-176">すべての SCOTT でサポートされる操作のメタデータを取得しています。EMP テーブルにカテゴリ ノードを渡すことによって、 **GetMetadata**メソッド。</span><span class="sxs-lookup"><span data-stu-id="15bea-176">Retrieving metadata for all of the operations supported for the SCOTT.EMP table by passing a category node to the **GetMetadata** method.</span></span>  
  
-   <span data-ttu-id="15bea-177">POLLINGSTMT 操作のノードを渡すことによって、POLLINGSTMT 操作のメタデータの取得、 **GetMetadata**メソッド.</span><span class="sxs-lookup"><span data-stu-id="15bea-177">Retrieving metadata for the POLLINGSTMT operation by passing the POLLINGSTMT operation node to the **GetMetadata** method..</span></span>  
  
```  
using System;  
using System.Collections.Generic;  
using System.Text;  
  
using System.ServiceModel;  
using Microsoft.Adapters.OracleDB;  
using Microsoft.ServiceModel.Channels;  
  
using System.Web.Services.Description;  
  
namespace OracleMetadataRetrieval  
{  
    class NodeWriter  
    {  
        // This method writes the value of a collection of metadata retrieval nodes  
        // to the console  
        public void Write(string title, MetadataRetrievalNode[] nodes)  
        {  
            Console.WriteLine(title);  
            Console.WriteLine();  
  
            //write all the nodes returned to the console.  
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
            MetadataRetrievalClient client = null;  
            NodeWriter nodeWriter = new NodeWriter();  
  
            try  
            {  
                // create a binding and   
                // set the PollingStatement binding property if you want to  
                // return metadata for the POLLINGSTMT operation  
                OracleDBBinding binding = new OracleDBBinding();  
                binding.PollingStatement = "SELECT * FROM EMP";  
  
                // Set PollingId parameter if you want to alter the namespace of the POLLINGSTMT operation  
                EndpointAddress address = new EndpointAddress("oracledb://ADAPTER?PollingId=1");  
  
                client = new MetadataRetrievalClient(binding, address);  
                client.ClientCredentials.UserName.UserName = "SCOTT";  
                client.ClientCredentials.UserName.Password = "TIGER";  
                client.Open();  
  
                // Browse for the first 3 (schema) nodes directly under the root  
                // The parameters are the parent Node ID, the start index, and the maximum number  
                // of nodes to return  
                MetadataRetrievalNode[] nodes = client.Browse(MetadataRetrievalNode.Root.NodeId, 0, 3);  
                nodeWriter.Write("Browse results for the root node:", nodes);  
  
                // Search for first 3 tables that contain "EMP" in the SCOTT schema  
                // The parameters are the parent node ID, the search expression, and the maximum number  
                // of nodes to return  
                nodes = client.Search("http://Microsoft.LobServices.OracleDB/2007/03/SCOTT/Table", "%EMP%", 3);  
                nodeWriter.Write(String.Format("Search results for \"%EMP%\" under {0} node:", "http://Microsoft.LobServices.OracleDB/2007/03/SCOTT/Table"), nodes);  
  
                // Get a WSDL document that specifies a contract that contains the operations  
                // surfaced for the SCOTT.EMP table. The IsOperation property is set false  
                // because this is a category node.  
                nodes = new MetadataRetrievalNode[1];  
                nodes[0] = new MetadataRetrievalNode();  
                nodes[0].NodeId = "http://Microsoft.LobServices.OracleDB/2007/03/SCOTT/Table/EMP";  
                nodes[0].IsOperation = false;  
                System.Web.Services.Description.ServiceDescription description = client.GetMetadata(nodes);  
                description.Write("EmpTableContract.wsdl");  
  
                // Get a WSDL document that specifies a contract that contains the   
                // the POLLINGSTMT operation. The IsOperation property is set true  
                // because this is an operation node.  
                // Note that the operation NodeId is equivalent to the message action.  
                nodes = new MetadataRetrievalNode[1];  
                nodes[0] = new MetadataRetrievalNode();  
                nodes[0].NodeId = "http://Microsoft.LobServices.OracleDB/2007/03/POLLINGSTMT";  
                nodes[0].IsOperation = true;  
                description = client.GetMetadata(nodes);  
                description.Write("PollingContract.wsdl");  
  
            }  
            catch (Exception ex)  
            {  
                Console.WriteLine("Exception is: " + ex.Message);  
            }  
            finally  
            {  
                if (client != null)  
                {  
                    if (client.State == CommunicationState.Opened)  
                        client.Close();  
                    else  
                        client.Abort();  
                }  
            }  
        }  
    }  
}  
```  
  
 <span data-ttu-id="15bea-178">次は、コンソールでこのプログラムの出力を示します。</span><span class="sxs-lookup"><span data-stu-id="15bea-178">The following shows the output of this program on the console.</span></span> <span data-ttu-id="15bea-179">各メソッドによって返されるメタデータ取得のノードの構造を確認できます。</span><span class="sxs-lookup"><span data-stu-id="15bea-179">You can see the structure of the metadata retrieval nodes returned by each method.</span></span> <span data-ttu-id="15bea-180">また、プログラムは 2 つの WSDL ドキュメントをファイルに書き込みます。</span><span class="sxs-lookup"><span data-stu-id="15bea-180">The program also writes two WSDL documents to files.</span></span>  
  
```  
Browse results for the root node:  
  
NodeId = http://Microsoft.LobServices.OracleDB/2007/03/ADAPTERTEST  
        Direction   = Outbound  
        IsOperation = False  
        DisplayName = ADAPTERTEST  
        Description = Owned By ADAPTERTEST  
NodeId = http://Microsoft.LobServices.OracleDB/2007/03/ADAPTEST  
        Direction   = Outbound  
        IsOperation = False  
        DisplayName = ADAPTEST  
        Description = Owned By ADAPTEST  
NodeId = http://Microsoft.LobServices.OracleDB/2007/03/ADMIN123  
        Direction   = Outbound  
        IsOperation = False  
        DisplayName = ADMIN123  
        Description = Owned By ADMIN123  
  
Search results for "%EMP%" under http://Microsoft.LobServices.OracleDB/2007/03/SCOTT/Table node:  
  
NodeId = http://Microsoft.LobServices.OracleDB/2007/03/SCOTT/Table/AEMP  
        Direction   = Outbound  
        IsOperation = False  
        DisplayName = AEMP  
        Description = Table.AEMP  
NodeId = http://Microsoft.LobServices.OracleDB/2007/03/SCOTT/Table/EMP  
        Direction   = Outbound  
        IsOperation = False  
        DisplayName = EMP  
        Description = Table.EMP  
NodeId = http://Microsoft.LobServices.OracleDB/2007/03/SCOTT/Table/EMP1  
        Direction   = Outbound  
        IsOperation = False  
        DisplayName = EMP1  
        Description = Table.EMP1  
```  
  
## <a name="using-an-imetadataretrievalcontract-channel"></a><span data-ttu-id="15bea-181">IMetadataRetrievalContract チャネルを使用してください。</span><span class="sxs-lookup"><span data-stu-id="15bea-181">Using an IMetadataRetrievalContract Channel</span></span>  
 <span data-ttu-id="15bea-182">作成することも、 **IMetadataRetrievalContract**チャネルし、このチャネルを使用して、参照、検索、およびアダプターからメタデータを取得します。</span><span class="sxs-lookup"><span data-stu-id="15bea-182">You can also create an **IMetadataRetrievalContract** channel and then use this channel to browse, search, and retrieve metadata from the adapter.</span></span> <span data-ttu-id="15bea-183">(メソッドのシグネチャが同じである、 **MetadataRetrievalClient**クラスです)。その方法を次の例に示します。</span><span class="sxs-lookup"><span data-stu-id="15bea-183">(The method signatures are the same as for the **MetadataRetrievalClient** class.) The following example shows how to do this.</span></span>  
  
```  
…  
//Create a binding and endpoint address.  
OracleDBBinding binding = new OracleDBBinding();  
EndpointAddress address = new EndpointAddress("oracledb://ADAPTER/");  
  
//Create and open a channel factory that will return an IMetadataRetrievalContract object, on which browse, search, and get can be performed.  
ChannelFactory<IMetadataRetrievalContract> factory = new ChannelFactory<IMetadataRetrievalContract>(binding, address);  
factory.Credentials.UserName.UserName = "SCOTT";  
factory.Credentials.UserName.Password = "TIGER";  
factory.Open();  
  
//Obtain an IMetadataRetrievalContract channel from the factory.  
IMetadataRetrievalContract channel = factory.CreateChannel();  
  
//Perform a search using the channel.  
MetadataRetrievalNode[] nodes = channel.Search("http://Microsoft.LobServices.OracleDB/2007/03/SCOTT/Table", "%EMP%", int.MaxValue);  
…  
```  
  
## <a name="see-also"></a><span data-ttu-id="15bea-184">参照</span><span class="sxs-lookup"><span data-stu-id="15bea-184">See Also</span></span>  
 [<span data-ttu-id="15bea-185">Oracle データベースからメタデータをプログラムで取得します。</span><span class="sxs-lookup"><span data-stu-id="15bea-185">Get Metadata Programmatically from the Oracle Database</span></span>](../../adapters-and-accelerators/adapter-oracle-database/get-metadata-programmatically-from-the-oracle-database.md)