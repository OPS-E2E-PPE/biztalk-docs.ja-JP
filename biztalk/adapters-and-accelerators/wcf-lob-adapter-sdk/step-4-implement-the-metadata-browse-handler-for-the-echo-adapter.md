---
title: "手順 4: エコー アダプターのメタデータ参照のハンドラーを実装する |Microsoft ドキュメント"
ms.custom: 
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: 
ms.suite: 
ms.tgt_pltfrm: 
ms.topic: article
ms.assetid: d31fc6c1-e4b5-4529-ba3e-2a8cfb8ece1c
caps.latest.revision: "19"
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: f93b4efeb65092c4ca61ab1fc2ef58a0ac53ae4a
ms.sourcegitcommit: cb908c540d8f1a692d01dc8f313e16cb4b4e696d
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 09/20/2017
---
# <a name="step-4-implement-the-metadata-browse-handler-for-the-echo-adapter"></a><span data-ttu-id="08d88-102">手順 4: エコー アダプターのメタデータ参照のハンドラーを実装します。</span><span class="sxs-lookup"><span data-stu-id="08d88-102">Step 4: Implement the Metadata Browse Handler for the Echo Adapter</span></span>
<span data-ttu-id="08d88-103">![手順 4. 9 の](../../adapters-and-accelerators/wcf-lob-adapter-sdk/media/step-4of9.gif "Step_4of9")</span><span class="sxs-lookup"><span data-stu-id="08d88-103">![Step 4 of 9](../../adapters-and-accelerators/wcf-lob-adapter-sdk/media/step-4of9.gif "Step_4of9")</span></span>  
  
 <span data-ttu-id="08d88-104">**所要時間:** 45 分</span><span class="sxs-lookup"><span data-stu-id="08d88-104">**Time to complete:** 45 minutes</span></span>  
  
 <span data-ttu-id="08d88-105">このステップでは、エコー アダプターの [参照] 機能を実装します。</span><span class="sxs-lookup"><span data-stu-id="08d88-105">In this step, you implement the browse capability of the Echo adapter.</span></span> <span data-ttu-id="08d88-106">この機能では、アダプター メタデータを取得する対象システムからの接続に基づく参照を実行します。</span><span class="sxs-lookup"><span data-stu-id="08d88-106">This capability allows your adapter to perform a connection-based browse to obtain metadata from the target system.</span></span> <span data-ttu-id="08d88-107">アダプターの機能に関係なく、アダプターは、[参照] 機能をサポートする必要があります。</span><span class="sxs-lookup"><span data-stu-id="08d88-107">Regardless of your adapter's capabilities, your adapter must support the browse capability.</span></span>  
  
 <span data-ttu-id="08d88-108">よると、 [!INCLUDE[afproductnameshort](../../includes/afproductnameshort-md.md)]、参照機能をサポートするために実装する必要があります、`Microsoft.ServiceModel.Channels.Common.IMetadataBrowseHandler`インターフェイスです。</span><span class="sxs-lookup"><span data-stu-id="08d88-108">According to the [!INCLUDE[afproductnameshort](../../includes/afproductnameshort-md.md)], to support browse capability, you must implement the `Microsoft.ServiceModel.Channels.Common.IMetadataBrowseHandler` interface.</span></span> <span data-ttu-id="08d88-109">エコー アダプターの場合、 [!INCLUDE[afdevwizardnameshort](../../includes/afdevwizardnameshort-md.md)] EchoAdapterMetadataBrowseHandler と呼ばれる、派生クラスが自動的に生成されます。</span><span class="sxs-lookup"><span data-stu-id="08d88-109">For the Echo adapter, the [!INCLUDE[afdevwizardnameshort](../../includes/afdevwizardnameshort-md.md)] automatically generates the derived class called EchoAdapterMetadataBrowseHandler.</span></span>  
  
 <span data-ttu-id="08d88-110">次の手順で実装する方法の理解を深めるために、このクラスを更新する、`Microsoft.ServiceModel.Channels.Common.IMetadataBrowseHandler.Browse%2A`メソッドのさまざまなプロパティを設定する方法、`Microsoft.ServiceModel.Channels.MetadataRetrievalNode`オブジェクト、および操作と、アダプターでサポートされているカテゴリのノードが、でどのように表示する方法[!INCLUDE[addadapterservrefshort](../../includes/addadapterservrefshort-md.md)]ツールです。</span><span class="sxs-lookup"><span data-stu-id="08d88-110">In the following steps, you update this class to get a better understanding of how to implement the `Microsoft.ServiceModel.Channels.Common.IMetadataBrowseHandler.Browse%2A` method, how to set various properties of the `Microsoft.ServiceModel.Channels.MetadataRetrievalNode` object, and how the operation and category nodes supported by the adapter appear in the [!INCLUDE[addadapterservrefshort](../../includes/addadapterservrefshort-md.md)] tool.</span></span>  
  
## <a name="prerequisites"></a><span data-ttu-id="08d88-111">前提条件</span><span class="sxs-lookup"><span data-stu-id="08d88-111">Prerequisites</span></span>  
 <span data-ttu-id="08d88-112">この手順を開始する前にする必要がありますが正常に完了しました[手順 3: エコー アダプターの接続を実装](../../adapters-and-accelerators/wcf-lob-adapter-sdk/step-3-implement-the-connection-for-the-echo-adapter.md)です。</span><span class="sxs-lookup"><span data-stu-id="08d88-112">Before you begin this step, you must have successfully completed [Step 3: Implement the Connection for the Echo Adapter](../../adapters-and-accelerators/wcf-lob-adapter-sdk/step-3-implement-the-connection-for-the-echo-adapter.md).</span></span> <span data-ttu-id="08d88-113">次のクラスを理解する必要があります。</span><span class="sxs-lookup"><span data-stu-id="08d88-113">You must also understand the following classes:</span></span>  
  
-   `Microsoft.ServiceModel.Channels.MetadataRetrievalNode`  
  
-   `Microsoft.ServiceModel.Channels.MetadataRetrievalNodeDirections`  
  
-   `Microsoft.ServiceModel.Channels.Common.IMetadataBrowseHandler`  
  
## <a name="the-imetadatabrowsehandler-interface"></a><span data-ttu-id="08d88-114">IMetadataBrowseHandler インターフェイス</span><span class="sxs-lookup"><span data-stu-id="08d88-114">The IMetadataBrowseHandler Interface</span></span>  
 <span data-ttu-id="08d88-115">`Microsoft.ServiceModel.Channels.Common.IMetadataBrowseHandler`としてインターフェイスを定義します。</span><span class="sxs-lookup"><span data-stu-id="08d88-115">The `Microsoft.ServiceModel.Channels.Common.IMetadataBrowseHandler` interface is defined as:</span></span>  
  
```  
public interface IMetadataBrowseHandler : IConnectionHandler, IDisposable  
{  
    MetadataRetrievalNode[] Browse(string nodeId, int childStartIndex, int maxChildNodes, TimeSpan timeout);  
}  
```  
  
 <span data-ttu-id="08d88-116">`Microsoft.ServiceModel.Channels.Common.IMetadataBrowseHandler.Browse%2A`メソッドの配列を返します`Microsoft.ServiceModel.Channels.MetadataRetrievalNode`オブジェクト メソッドのパラメーターをベースにします。</span><span class="sxs-lookup"><span data-stu-id="08d88-116">The `Microsoft.ServiceModel.Channels.Common.IMetadataBrowseHandler.Browse%2A` method returns an array of `Microsoft.ServiceModel.Channels.MetadataRetrievalNode` objects based on the method parameters.</span></span> <span data-ttu-id="08d88-117">パラメーターの定義、`Microsoft.ServiceModel.Channels.Common.IMetadataBrowseHandler.Browse%2A`メソッドは次の表で説明します。</span><span class="sxs-lookup"><span data-stu-id="08d88-117">The parameter definitions for the `Microsoft.ServiceModel.Channels.Common.IMetadataBrowseHandler.Browse%2A` method are described in the following table.</span></span>  
  
> [!NOTE]
>  <span data-ttu-id="08d88-118">エコー アダプターの実装では、ノードの ID のみを使用し、エコー アダプターは、少数のノードをサポートするために、他の 3 つのパラメーターを無視します。</span><span class="sxs-lookup"><span data-stu-id="08d88-118">The Echo adapter implementation uses only the node ID and ignores the other three parameters, since the Echo adapter supports only a few nodes.</span></span>  
  
|<span data-ttu-id="08d88-119">**パラメーター**</span><span class="sxs-lookup"><span data-stu-id="08d88-119">**Parameter**</span></span>|<span data-ttu-id="08d88-120">**定義**</span><span class="sxs-lookup"><span data-stu-id="08d88-120">**Definition**</span></span>|  
|-------------------|--------------------|  
|<span data-ttu-id="08d88-121">NodeId</span><span class="sxs-lookup"><span data-stu-id="08d88-121">nodeId</span></span>|<span data-ttu-id="08d88-122">メタデータ エクスプ ローラーの階層の各項目 (、[!INCLUDE[addadapterservrefshort](../../includes/addadapterservrefshort-md.md)]と</span><span class="sxs-lookup"><span data-stu-id="08d88-122">Each item in the hierarchy of the metadata explorer (the [!INCLUDE[addadapterservrefshort](../../includes/addadapterservrefshort-md.md)] and</span></span><br /><br /> [!INCLUDE[consumeadapterservshort](../../includes/consumeadapterservshort-md.md)]<span data-ttu-id="08d88-123">)、nodeId がします。</span><span class="sxs-lookup"><span data-stu-id="08d88-123">) has a nodeId.</span></span> <span data-ttu-id="08d88-124">各ノードの ID は一意である必要があり、カテゴリ、または操作することができます。</span><span class="sxs-lookup"><span data-stu-id="08d88-124">Each node ID must be unique and can be a category or an operation.</span></span> <span data-ttu-id="08d88-125">カテゴリは、サブカテゴリを持つことができます。</span><span class="sxs-lookup"><span data-stu-id="08d88-125">The category can have subcategories.</span></span> <span data-ttu-id="08d88-126">**注:**場合は null または空の文字列 ("")、ルート ノードから (「/」) で既定の操作が取得されます。</span><span class="sxs-lookup"><span data-stu-id="08d88-126">**Note:**  If null or an empty string (""), operations are retrieved from the root node ("/") by default.</span></span>|  
|<span data-ttu-id="08d88-127">childStartIndex</span><span class="sxs-lookup"><span data-stu-id="08d88-127">childStartIndex</span></span>|<span data-ttu-id="08d88-128">返される最初の子のインデックス。</span><span class="sxs-lookup"><span data-stu-id="08d88-128">The index of the first child to return.</span></span><br /><br /> <span data-ttu-id="08d88-129">エコー アダプターによってサポートされていません。</span><span class="sxs-lookup"><span data-stu-id="08d88-129">Not supported by the Echo adapter.</span></span>|  
|<span data-ttu-id="08d88-130">maxChildNodes</span><span class="sxs-lookup"><span data-stu-id="08d88-130">maxChildNodes</span></span>|<span data-ttu-id="08d88-131">返される結果のノードの最大数。</span><span class="sxs-lookup"><span data-stu-id="08d88-131">The maximum number of result nodes to return.</span></span> <span data-ttu-id="08d88-132">Int32.Max を使用して、結果のすべてのノードを取得します。</span><span class="sxs-lookup"><span data-stu-id="08d88-132">Use Int32.Max to retrieve all result nodes.</span></span><br /><br /> <span data-ttu-id="08d88-133">エコー アダプターによってサポートされていません。</span><span class="sxs-lookup"><span data-stu-id="08d88-133">Not supported by the Echo adapter.</span></span>|  
|<span data-ttu-id="08d88-134">timeout</span><span class="sxs-lookup"><span data-stu-id="08d88-134">timeout</span></span>|<span data-ttu-id="08d88-135">操作が完了する許可された最大時間。</span><span class="sxs-lookup"><span data-stu-id="08d88-135">The maximum time allowed for the operation to complete.</span></span><br /><br /> <span data-ttu-id="08d88-136">エコー アダプターによってサポートされていません。</span><span class="sxs-lookup"><span data-stu-id="08d88-136">Not supported by the Echo adapter.</span></span>|  
  
 <span data-ttu-id="08d88-137">実装する場合、`Microsoft.ServiceModel.Channels.Common.IMetadataBrowseHandler.Browse%2A`メソッドの配列にカテゴリと操作の各ノードを追加する必要があります`Microsoft.ServiceModel.Channels.MetadataRetrievalNode`オブジェクト。</span><span class="sxs-lookup"><span data-stu-id="08d88-137">When implementing the `Microsoft.ServiceModel.Channels.Common.IMetadataBrowseHandler.Browse%2A` method, you must add every category and operation node to the array of `Microsoft.ServiceModel.Channels.MetadataRetrievalNode` objects.</span></span> <span data-ttu-id="08d88-138">カテゴリとしてノードを指定するには、設定、`Microsoft.ServiceModel.Channels.MetadataRetrievalNode.IsOperation%2A`に`false`です。</span><span class="sxs-lookup"><span data-stu-id="08d88-138">To specify a node as category, set the `Microsoft.ServiceModel.Channels.MetadataRetrievalNode.IsOperation%2A` to `false`.</span></span> <span data-ttu-id="08d88-139">操作として、ノードを指定するには、設定、`Microsoft.ServiceModel.Channels.MetadataRetrievalNode.IsOperation%2A`に`true`です。</span><span class="sxs-lookup"><span data-stu-id="08d88-139">To specify a node as operation, set the `Microsoft.ServiceModel.Channels.MetadataRetrievalNode.IsOperation%2A` to `true`.</span></span>  
  
## <a name="echo-adapter-metadata-browse"></a><span data-ttu-id="08d88-140">エコー アダプター メタデータの参照</span><span class="sxs-lookup"><span data-stu-id="08d88-140">Echo Adapter Metadata Browse</span></span>  
 <span data-ttu-id="08d88-141">によっては、ターゲット システムのカテゴリと操作の配列を作成する方法はたくさんあります`Microsoft.ServiceModel.Channels.MetadataRetrievalNode`オブジェクト。</span><span class="sxs-lookup"><span data-stu-id="08d88-141">Depending on your target system's categories and operations, there are many ways to build an array of `Microsoft.ServiceModel.Channels.MetadataRetrievalNode` objects.</span></span> <span data-ttu-id="08d88-142">操作とカテゴリを選択するには、公開する操作を表す必要があります。</span><span class="sxs-lookup"><span data-stu-id="08d88-142">The operations and categories you choose should represent the operations you want to expose.</span></span> <span data-ttu-id="08d88-143">エコー アダプターが単に作成されますが、`Microsoft.ServiceModel.Channels.MetadataRetrievalNode`ノード ID で、次のノードの各オブジェクトが一覧表示。</span><span class="sxs-lookup"><span data-stu-id="08d88-143">But for the Echo adapter, it simply creates a `Microsoft.ServiceModel.Channels.MetadataRetrievalNode` object for each of the following nodes with node ID listed:</span></span>  
  
```  
EchoMainCategory  (node under the root node)  
        Echo/EchoStrings   (outbound operation)  
        Echo/EchoGreetings(outbound operation)  
        Echo/EchoCustomGreetingFromFile(outbound operation)  
        Echo/OnReceiveEcho (inbound operation)  
```  
  
 <span data-ttu-id="08d88-144">EchoMainCategory は、カテゴリ ノード (「/」) のルート ノードの下です。</span><span class="sxs-lookup"><span data-stu-id="08d88-144">The EchoMainCategory is the category node under the root node ("/").</span></span> <span data-ttu-id="08d88-145">このノードは、受信および送信の両方の操作のためのカテゴリとしても使用されます。</span><span class="sxs-lookup"><span data-stu-id="08d88-145">This node is also used as the category for both inbound and outbound operations.</span></span> <span data-ttu-id="08d88-146">そのため、作成するときに、`Microsoft.ServiceModel.Channels.MetadataRetrievalNode`そのカテゴリのオブジェクトの次を行うことができます。</span><span class="sxs-lookup"><span data-stu-id="08d88-146">Hence, when creating the `Microsoft.ServiceModel.Channels.MetadataRetrievalNode` object for that category, you can do the following:</span></span>  
  
```  
MetadataRetrievalNode node = new MetadataRetrievalNode("EchoMainCategory");  
node.IsOperation = false; //category  
node.Direction = MetadataRetrievalNodeDirections.Inbound | MetadataRetrievalNodeDirections.Outbound  //for both inbound and outbound  
```  
  
 <span data-ttu-id="08d88-147">エコー/EchoString、EchoMainCategory に属しているなどの送信操作では、次の操作を行うことができます。</span><span class="sxs-lookup"><span data-stu-id="08d88-147">For an outbound operation such as Echo/EchoString that belongs to the EchoMainCategory, you can do the following:</span></span>  
  
```  
if( "EchoMainCategory".CompareTo(nodeId) == 0 ) //category is EchoMainCategory  
      {  
          // Outbound operations  
          MetadataRetrievalNode outOpNode1 = new MetadataRetrievalNode("Echo/EchoStrings");  
          outOpNode1.DisplayName = "EchoStrings";  
          outOpNode1.Description = "This operation echoes the incoming string COUNT number of times in a string array.";  
          outOpNode1.Direction = MetadataRetrievalNodeDirections.Outbound;  
          outOpNode1.IsOperation = true;  
```  
  
 <span data-ttu-id="08d88-148">エコー/OnReceiveEcho、EchoMainCategory に属しているなどの受信操作では、次の操作を行うことができます。</span><span class="sxs-lookup"><span data-stu-id="08d88-148">For an inbound operation such as Echo/OnReceiveEcho that belongs to the EchoMainCategory, you can do the following:</span></span>  
  
```  
  if( "EchoMainCategory".CompareTo(nodeId) == 0 ) //category is EchoMainCategory  
        {             
// Inbound operations  
            MetadataRetrievalNode inOpNode1 = new MetadataRetrievalNode("Echo/OnReceiveEcho");  
            inOpNode1.DisplayName = "OnReceiveEcho";  
            inOpNode1.Description = "This operation echoes the location and length of a file dropped in the specified file system.";  
            inOpNode1.Direction = MetadataRetrievalNodeDirections.Inbound;  
            inOpNode1.IsOperation = true;  
```  
  
 <span data-ttu-id="08d88-149">ときに、[!INCLUDE[addadapterservrefshort](../../includes/addadapterservrefshort-md.md)]と[!INCLUDE[consumeadapterservshort](../../includes/consumeadapterservshort-md.md)]ツールが既定では、エコー アダプター メタデータを調査、ルート ノード (「/」) から開始します。</span><span class="sxs-lookup"><span data-stu-id="08d88-149">When the [!INCLUDE[addadapterservrefshort](../../includes/addadapterservrefshort-md.md)] and [!INCLUDE[consumeadapterservshort](../../includes/consumeadapterservshort-md.md)] tools explore the Echo adapter metadata, by default, it starts from the root node ("/").</span></span>  
  
 <span data-ttu-id="08d88-150">次の図は、(「/」) のルート ノードの下に EchoMainCategory ノードが表示されることを示しています。</span><span class="sxs-lookup"><span data-stu-id="08d88-150">The following figure shows that the EchoMainCategory node appears under the root node ("/"):</span></span>  
  
 ![](../../adapters-and-accelerators/wcf-lob-adapter-sdk/media/e4b9d0b8-f07f-4342-815f-9ef1507b0980.gif "e4b9d0b8-f07f-4342-815f-9ef1507b0980")  
  
 <span data-ttu-id="08d88-151">次の 3 つの送信操作を参照するときに、[!INCLUDE[addadapterservrefshort](../../includes/addadapterservrefshort-md.md)]ツールを**選択コントラクト型**ドロップダウン リスト、選択、**クライアント (送信操作)**オプション。</span><span class="sxs-lookup"><span data-stu-id="08d88-151">To browse the three outbound operations, in the [!INCLUDE[addadapterservrefshort](../../includes/addadapterservrefshort-md.md)] tool, in the **Select contract type** drop-down list,select the **Client (Outbound operations)** option.</span></span> <span data-ttu-id="08d88-152">これらの操作を参照してください、**利用可能なカテゴリと操作**リスト ボックスで、次のようにします。</span><span class="sxs-lookup"><span data-stu-id="08d88-152">You see those operations in the **Available categories and operations** list box, as shown below:</span></span>  
  
 ![](../../adapters-and-accelerators/wcf-lob-adapter-sdk/media/c8755805-cbb0-40f1-887a-a3123f71ae7e.gif "c8755805-cbb0-40f1-887a-a3123f71ae7e")  
  
 <span data-ttu-id="08d88-153">前の図では、`Microsoft.ServiceModel.Channels.MetadataRetrievalNode.DisplayName%2A`値に表示されます、**名前**の列、**利用可能なカテゴリと操作**ボックスの一覧です。</span><span class="sxs-lookup"><span data-stu-id="08d88-153">In the previous figure, notice that the `Microsoft.ServiceModel.Channels.MetadataRetrievalNode.DisplayName%2A` value appears in the **Name** column of the **Available categories and operations** list box.</span></span> <span data-ttu-id="08d88-154">渡されたパラメーター、`Microsoft.ServiceModel.Channels.MetadataRetrievalNode`にコンス トラクターが、**ノード ID**の列、**利用可能なカテゴリと操作**リスト ボックスで、および`Microsoft.ServiceModel.Channels.MetadataRetrievalNode.Description%2A`値、ツールヒントとして表示されます右クリックすると、説明を含む、`Microsoft.ServiceModel.Channels.MetadataRetrievalNode.DisplayName%2A`です。</span><span class="sxs-lookup"><span data-stu-id="08d88-154">The parameter passed into the `Microsoft.ServiceModel.Channels.MetadataRetrievalNode` constructor appears in the **Node ID** column of the **Available categories and operations** list box, and the `Microsoft.ServiceModel.Channels.MetadataRetrievalNode.Description%2A` value appears as the tool tip that contains the description, when you right-click the `Microsoft.ServiceModel.Channels.MetadataRetrievalNode.DisplayName%2A`.</span></span>  
  
 <span data-ttu-id="08d88-155">入力方向の操作を表示する、[!INCLUDE[addadapterservrefshort](../../includes/addadapterservrefshort-md.md)]ツールを**選択コントラクト型**ドロップダウン リスト、選択、**サービス (入力方向の操作)**オプション。</span><span class="sxs-lookup"><span data-stu-id="08d88-155">To see the inbound operations, in the [!INCLUDE[addadapterservrefshort](../../includes/addadapterservrefshort-md.md)] tool, in the **Select contract type** drop-down list,select the **Service (Inbound operations)** option.</span></span> <span data-ttu-id="08d88-156">受信 OnReceiveEcho 操作を参照してください、**利用可能なカテゴリと操作**リスト ボックスで、次の図に示すようにします。</span><span class="sxs-lookup"><span data-stu-id="08d88-156">You see the inbound OnReceiveEcho operation in the **Available categories and operations** list box, as shown in the following figure:</span></span>  
  
 ![](../../adapters-and-accelerators/wcf-lob-adapter-sdk/media/26b7b3c7-bc39-46f8-bc73-7d76fd3c02eb.gif "26b7b3c7-bc39-46f8-bc73-7d76fd3c02eb")  
  
## <a name="implementing-the-imetadatabrowsehandler"></a><span data-ttu-id="08d88-157">IMetadataBrowseHandler を実装します。</span><span class="sxs-lookup"><span data-stu-id="08d88-157">Implementing the IMetadataBrowseHandler</span></span>  
 <span data-ttu-id="08d88-158">実装するは、エコー アダプターのメタデータの参照を実装する EchoAdapterMetadataBrowseHandler クラスを更新するこの手順で、`Microsoft.ServiceModel.Channels.Common.IMetadataBrowseHandler.Browse%2A`のメソッド、`Microsoft.ServiceModel.Channels.Common.IMetadataBrowseHandler`インターフェイスです。</span><span class="sxs-lookup"><span data-stu-id="08d88-158">In this step, you update the EchoAdapterMetadataBrowseHandler class to implement the Echo adapter's metadata browse, that is, to implement the `Microsoft.ServiceModel.Channels.Common.IMetadataBrowseHandler.Browse%2A` method of the `Microsoft.ServiceModel.Channels.Common.IMetadataBrowseHandler` interface.</span></span> <span data-ttu-id="08d88-159">具体的を作成する、`Microsoft.ServiceModel.Channels.MetadataRetrievalNode`オブジェクトの各カテゴリと操作、そのオブジェクトの適切な値を設定およびの配列を返す`Microsoft.ServiceModel.Channels.MetadataRetrievalNode`カテゴリおよび操作のためのオブジェクト。</span><span class="sxs-lookup"><span data-stu-id="08d88-159">Specifically, you create a `Microsoft.ServiceModel.Channels.MetadataRetrievalNode` object for each category and operation, set appropriate values for that object, and then return the array of `Microsoft.ServiceModel.Channels.MetadataRetrievalNode` objects for category and operations.</span></span> <span data-ttu-id="08d88-160">ただし、作成するときに、`Microsoft.ServiceModel.Channels.MetadataRetrievalNode`オブジェクトの表示名ではなく、ノード ID を渡す必要があります。</span><span class="sxs-lookup"><span data-stu-id="08d88-160">Keep in mind that when you create a `Microsoft.ServiceModel.Channels.MetadataRetrievalNode` object, you need to pass in the node ID, not the display name.</span></span>  
  
#### <a name="to-update-the-echoadaptermetadatabrowsehandler-class"></a><span data-ttu-id="08d88-161">EchoAdapterMetadataBrowseHandler クラスの更新</span><span class="sxs-lookup"><span data-stu-id="08d88-161">To update the EchoAdapterMetadataBrowseHandler class</span></span>  
  
1.  <span data-ttu-id="08d88-162">ソリューション エクスプ ローラーで、 **EchoAdapterMetadataBrowseHandler.cs**ファイル。</span><span class="sxs-lookup"><span data-stu-id="08d88-162">In Solution Explorer, double-click the **EchoAdapterMetadataBrowseHandler.cs** file.</span></span>  
  
2.  <span data-ttu-id="08d88-163">Visual Studio エディターで、任意の場所を右クリック コンテキスト メニューで、エディター内のをポイント**アウトライン**、クリックして**アウトラインの中止**です。</span><span class="sxs-lookup"><span data-stu-id="08d88-163">In the Visual Studio editor, right-click anywhere within the editor, in the context menu, point to **Outlining**, and then click **Stop Outlining**.</span></span>  
  
3.  <span data-ttu-id="08d88-164">Visual Studio エディターで、内部、**参照**メソッドを置き換える既存のロジックを作成するには、次、 `Microsoft.ServiceModel.Channels.MetadataRetrievalNode` EchoMainCategory のオブジェクト。</span><span class="sxs-lookup"><span data-stu-id="08d88-164">In the Visual Studio editor, inside the **Browse** method, replace the existing logic with the following to create a `Microsoft.ServiceModel.Channels.MetadataRetrievalNode` object for EchoMainCategory.</span></span>  
  
    ```csharp  
    if (MetadataRetrievalNode.Root.NodeId.Equals(nodeId))  
    {  
        MetadataRetrievalNode node = new MetadataRetrievalNode("EchoMainCategory");  
        node.DisplayName = "Main Category";  
        node.IsOperation = false;  
        node.Description = "This category contains inbound and outbound categories.";  
        node.Direction = MetadataRetrievalNodeDirections.Inbound | MetadataRetrievalNodeDirections.Outbound;  
        return new MetadataRetrievalNode[] { node };  
    }  
    ```  
  
4.  <span data-ttu-id="08d88-165">作成する次のロジックの追加を繰り返して、`Microsoft.ServiceModel.Channels.MetadataRetrievalNode`エコー/OnReceiveEcho のオブジェクト。</span><span class="sxs-lookup"><span data-stu-id="08d88-165">Continue adding the following logic to create a `Microsoft.ServiceModel.Channels.MetadataRetrievalNode` object for Echo/OnReceiveEcho.</span></span>  
  
    ```csharp  
    if( "EchoMainCategory".CompareTo(nodeId) == 0 )  
    {  
        // Inbound operations  
        MetadataRetrievalNode inOpNode1 = new MetadataRetrievalNode("Echo/OnReceiveEcho");  
        inOpNode1.DisplayName = "OnReceiveEcho";  
        inOpNode1.Description = "This operation echos the location and length of a file dropped in the specified file system.";  
        inOpNode1.Direction = MetadataRetrievalNodeDirections.Inbound;  
        inOpNode1.IsOperation = true;  
    ```  
  
5.  <span data-ttu-id="08d88-166">作成する次のロジックの追加を繰り返して、`Microsoft.ServiceModel.Channels.MetadataRetrievalNode`エコー/EchoStrings のオブジェクト。</span><span class="sxs-lookup"><span data-stu-id="08d88-166">Continue adding the following logic to create a `Microsoft.ServiceModel.Channels.MetadataRetrievalNode` object for Echo/EchoStrings.</span></span>  
  
    ```csharp  
    // Outbound operations  
    MetadataRetrievalNode outOpNode1 = new MetadataRetrievalNode("Echo/EchoStrings");  
    outOpNode1.DisplayName = "EchoStrings";  
    outOpNode1.Description = "This operation echoes the incoming string COUNT number of times in a string array.";  
    outOpNode1.Direction = MetadataRetrievalNodeDirections.Outbound;  
    outOpNode1.IsOperation = true;  
    ```  
  
6.  <span data-ttu-id="08d88-167">作成する次のコードの追加を繰り返して、`Microsoft.ServiceModel.Channels.MetadataRetrievalNode`エコー/EchoGreetings のオブジェクト。</span><span class="sxs-lookup"><span data-stu-id="08d88-167">Continue adding the following code to create a `Microsoft.ServiceModel.Channels.MetadataRetrievalNode` object for Echo/EchoGreetings.</span></span>  
  
    ```csharp  
    MetadataRetrievalNode outOpNode2 = new MetadataRetrievalNode("Echo/EchoGreetings");  
    outOpNode2.DisplayName = "EchoGreetings";  
    outOpNode2.Description = "This operation echoes the incoming Greeting object COUNT number of times in an array of type Greeting.";  
    outOpNode2.Direction = MetadataRetrievalNodeDirections.Outbound;  
    outOpNode2.IsOperation = true;  
    ```  
  
7.  <span data-ttu-id="08d88-168">作成する次のコードの追加を繰り返して、`Microsoft.ServiceModel.Channels.MetadataRetrievalNode`エコーのオブジェクト/EchoGreetingFromFile です。</span><span class="sxs-lookup"><span data-stu-id="08d88-168">Continue adding the following code to create a `Microsoft.ServiceModel.Channels.MetadataRetrievalNode` object for Echo/ EchoGreetingFromFile.</span></span>  
  
    ```csharp  
    MetadataRetrievalNode outOpNode3 = new MetadataRetrievalNode("Echo/EchoCustomGreetingFromFile");  
    outOpNode3.DisplayName = "EchoCustomGreetingFromFile";  
    outOpNode3.Description = "This operation echoes the greeting object by reading its instance from a file. The Greeting object's metadata is obtained from a predefined XSD file.";  
    outOpNode3.Direction = MetadataRetrievalNodeDirections.Outbound;  
    outOpNode3.IsOperation = true;  
    ```  
  
8.  <span data-ttu-id="08d88-169">配列を返すには、次のコードの追加を繰り返して`Microsoft.ServiceModel.Channels.MetadataRetrievalNode`オブジェクトまたは一致しない場合は null です。</span><span class="sxs-lookup"><span data-stu-id="08d88-169">Continue adding the following code to return an array of `Microsoft.ServiceModel.Channels.MetadataRetrievalNode` objects or null if not matched.</span></span>  
  
    ```  
        return new MetadataRetrievalNode[] { inOpNode1, outOpNode1, outOpNode2, outOpNode3 };  
    }  
    return null;  
    ```  
  
9. <span data-ttu-id="08d88-170">Visual Studio での**ファイル** メニューのをクリックして**すべて保存**です。</span><span class="sxs-lookup"><span data-stu-id="08d88-170">In Visual Studio, on the **File** menu, click **Save All**.</span></span>  
  
10. <span data-ttu-id="08d88-171">**[ビルド]** メニューの **[ソリューションのビルド]**をクリックします。</span><span class="sxs-lookup"><span data-stu-id="08d88-171">On the **Build** menu, click **Build Solution**.</span></span> <span data-ttu-id="08d88-172">プロジェクトを正常にビルドする必要があります。</span><span class="sxs-lookup"><span data-stu-id="08d88-172">You should successfully build the project.</span></span> <span data-ttu-id="08d88-173">以外の場合は、上記のすべてのステップに従っていることを確認します。</span><span class="sxs-lookup"><span data-stu-id="08d88-173">If not, ensure that you have followed every step above.</span></span>  
  
> [!NOTE]
>  <span data-ttu-id="08d88-174">これで作業が保存されました。</span><span class="sxs-lookup"><span data-stu-id="08d88-174">You saved your work.</span></span> <span data-ttu-id="08d88-175">安全にこの時点で Visual Studio を終了したり、次の手順に進みます[手順 5: エコー アダプターのメタデータの検索ハンドラーの実装](../../adapters-and-accelerators/wcf-lob-adapter-sdk/step-5-implement-the-metadata-search-handler-for-the-echo-adapter.md)です。</span><span class="sxs-lookup"><span data-stu-id="08d88-175">You can safely close Visual Studio at this time or go to the next step, [Step 5: Implement the Metadata Search Handler for the Echo Adapter](../../adapters-and-accelerators/wcf-lob-adapter-sdk/step-5-implement-the-metadata-search-handler-for-the-echo-adapter.md).</span></span>  
  
## <a name="what-did-i-just-do"></a><span data-ttu-id="08d88-176">でしただけは何ですか。</span><span class="sxs-lookup"><span data-stu-id="08d88-176">What Did I Just Do?</span></span>  
 <span data-ttu-id="08d88-177">だけに閲覧エコー アダプターの機能を実装することで、メタデータを実装して、`Microsoft.ServiceModel.Channels.Common.IMetadataBrowseHandler.Browse%2A`のメソッド、`Microsoft.ServiceModel.Channels.Common.IMetadataBrowseHandler`インターフェイスです。</span><span class="sxs-lookup"><span data-stu-id="08d88-177">You just implemented the metadata browsing capability of the Echo adapter, by implementing the `Microsoft.ServiceModel.Channels.Common.IMetadataBrowseHandler.Browse%2A` method of the `Microsoft.ServiceModel.Channels.Common.IMetadataBrowseHandler` interface.</span></span> <span data-ttu-id="08d88-178">具体的には、作成した、`Microsoft.ServiceModel.Channels.MetadataRetrievalNode`カテゴリに属しているオブジェクトを配列として返されます、`Microsoft.ServiceModel.Channels.MetadataRetrievalNode`オブジェクト。</span><span class="sxs-lookup"><span data-stu-id="08d88-178">Specifically, you created a `Microsoft.ServiceModel.Channels.MetadataRetrievalNode` object for the category, and then returned it as an array of the `Microsoft.ServiceModel.Channels.MetadataRetrievalNode` objects.</span></span> <span data-ttu-id="08d88-179">作成した各操作に対して、`Microsoft.ServiceModel.Channels.MetadataRetrievalNode`オブジェクト、し、それらすべてのオブジェクトの配列の`Microsoft.ServiceModel.Channels.MetadataRetrievalNode`します。</span><span class="sxs-lookup"><span data-stu-id="08d88-179">For each operation, you created a `Microsoft.ServiceModel.Channels.MetadataRetrievalNode` object, and then returned all those objects in an array of `Microsoft.ServiceModel.Channels.MetadataRetrievalNode`.</span></span>  
  
## <a name="next-steps"></a><span data-ttu-id="08d88-180">次の手順</span><span class="sxs-lookup"><span data-stu-id="08d88-180">Next Steps</span></span>  
 <span data-ttu-id="08d88-181">メタデータの検索し解決機能、および送信メッセージの交換を実装するとします。</span><span class="sxs-lookup"><span data-stu-id="08d88-181">You implement metadata searching and resolving capabilities, and the outbound message exchange.</span></span> <span data-ttu-id="08d88-182">最後に、ビルドおよび展開するエコー アダプター。</span><span class="sxs-lookup"><span data-stu-id="08d88-182">Finally, you build and deploy the Echo adapter.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="08d88-183">参照</span><span class="sxs-lookup"><span data-stu-id="08d88-183">See Also</span></span>  
 <span data-ttu-id="08d88-184">[チュートリアル 1: エコー アダプターを開発します。](../../adapters-and-accelerators/wcf-lob-adapter-sdk/tutorial-1-develop-the-echo-adapter.md) </span><span class="sxs-lookup"><span data-stu-id="08d88-184">[Tutorial 1: Develop the Echo Adapter](../../adapters-and-accelerators/wcf-lob-adapter-sdk/tutorial-1-develop-the-echo-adapter.md) </span></span>  
 <span data-ttu-id="08d88-185">[手順 3: エコー アダプターの接続を実装します。](../../adapters-and-accelerators/wcf-lob-adapter-sdk/step-3-implement-the-connection-for-the-echo-adapter.md) </span><span class="sxs-lookup"><span data-stu-id="08d88-185">[Step 3: Implement the Connection for the Echo Adapter](../../adapters-and-accelerators/wcf-lob-adapter-sdk/step-3-implement-the-connection-for-the-echo-adapter.md) </span></span>  
 [<span data-ttu-id="08d88-186">手順 5: エコー アダプターのメタデータの検索ハンドラーを実装します。</span><span class="sxs-lookup"><span data-stu-id="08d88-186">Step 5: Implement the Metadata Search Handler for the Echo Adapter</span></span>](../../adapters-and-accelerators/wcf-lob-adapter-sdk/step-5-implement-the-metadata-search-handler-for-the-echo-adapter.md)