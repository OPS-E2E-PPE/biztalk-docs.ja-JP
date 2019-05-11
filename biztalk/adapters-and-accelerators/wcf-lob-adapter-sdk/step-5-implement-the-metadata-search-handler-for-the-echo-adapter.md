---
title: 手順 5:エコー アダプターのメタデータ検索ハンドラーの実装 |Microsoft Docs
ms.custom: ''
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: ''
ms.suite: ''
ms.tgt_pltfrm: ''
ms.topic: article
ms.assetid: 1a133a99-1d6c-4634-b928-0f4f23c6f6e4
caps.latest.revision: 17
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: 764f5ff5bdd95ad51cfc5cc9c7495c27905131f2
ms.sourcegitcommit: 381e83d43796a345488d54b3f7413e11d56ad7be
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 05/07/2019
ms.locfileid: "65363141"
---
# <a name="step-5-implement-the-metadata-search-handler-for-the-echo-adapter"></a><span data-ttu-id="7ee8e-102">手順 5:エコー アダプターのメタデータ検索ハンドラーを実装します。</span><span class="sxs-lookup"><span data-stu-id="7ee8e-102">Step 5: Implement the Metadata Search Handler for the Echo Adapter</span></span>
<span data-ttu-id="7ee8e-103">![手順 5. の 9](../../adapters-and-accelerators/wcf-lob-adapter-sdk/media/step-5of9.gif "Step_5of9")</span><span class="sxs-lookup"><span data-stu-id="7ee8e-103">![Step 5 of 9](../../adapters-and-accelerators/wcf-lob-adapter-sdk/media/step-5of9.gif "Step_5of9")</span></span>  
  
 <span data-ttu-id="7ee8e-104">**所要時間:** 30 分</span><span class="sxs-lookup"><span data-stu-id="7ee8e-104">**Time to complete:** 30 minutes</span></span>  
  
 <span data-ttu-id="7ee8e-105">このチュートリアルの手順では、エコー アダプターの検索機能を実装します。</span><span class="sxs-lookup"><span data-stu-id="7ee8e-105">In this step of the tutorial, you implement the search capability of the Echo adapter.</span></span> <span data-ttu-id="7ee8e-106">参照とは異なり、検索は省略可能です。</span><span class="sxs-lookup"><span data-stu-id="7ee8e-106">Unlike browse, search is optional.</span></span> <span data-ttu-id="7ee8e-107">に従って、 [!INCLUDE[afproductnameshort](../../includes/afproductnameshort-md.md)]、検索機能をサポートするために実装する必要があります、`Microsoft.ServiceModel.Channels.Common.IMetadataSearchHandler`インターフェイス。</span><span class="sxs-lookup"><span data-stu-id="7ee8e-107">According to the [!INCLUDE[afproductnameshort](../../includes/afproductnameshort-md.md)], to support search capability, you must implement the `Microsoft.ServiceModel.Channels.Common.IMetadataSearchHandler` interface.</span></span> <span data-ttu-id="7ee8e-108">エコー アダプターの場合、 [!INCLUDE[afdevwizardnameshort](../../includes/afdevwizardnameshort-md.md)] EchoAdapterMetadataSearchHandler と呼ばれる 1 つの派生クラスが自動的に生成されます。</span><span class="sxs-lookup"><span data-stu-id="7ee8e-108">For the Echo adapter, the [!INCLUDE[afdevwizardnameshort](../../includes/afdevwizardnameshort-md.md)] automatically generates one derived class called EchoAdapterMetadataSearchHandler.</span></span>  
  
 <span data-ttu-id="7ee8e-109">最初に、このインターフェイスを実装する方法の理解を深めるために、EchoAdapterMetadataSearchHandler クラスを更新する方法を設定する`Microsoft.ServiceModel.Channels.MetadataRetrievalNode`オブジェクト、および検索結果を表示する方法、[!INCLUDE[addadapterservrefshort](../../includes/addadapterservrefshort-md.md)]ツール。</span><span class="sxs-lookup"><span data-stu-id="7ee8e-109">You first update the EchoAdapterMetadataSearchHandler class to get a better understanding of how to implement this interface, how to populate  `Microsoft.ServiceModel.Channels.MetadataRetrievalNode` object, and how the search results appear in the [!INCLUDE[addadapterservrefshort](../../includes/addadapterservrefshort-md.md)] tool.</span></span>  
  
## <a name="prerequisites"></a><span data-ttu-id="7ee8e-110">前提条件</span><span class="sxs-lookup"><span data-stu-id="7ee8e-110">Prerequisites</span></span>  
 <span data-ttu-id="7ee8e-111">この手順を開始する前に完了[手順 4。エコー アダプターのメタデータ参照ハンドラーを実装する](../../adapters-and-accelerators/wcf-lob-adapter-sdk/step-4-implement-the-metadata-browse-handler-for-the-echo-adapter.md)します。</span><span class="sxs-lookup"><span data-stu-id="7ee8e-111">Before you begin this step, complete [Step 4: Implement the Metadata Browse Handler for the Echo Adapter](../../adapters-and-accelerators/wcf-lob-adapter-sdk/step-4-implement-the-metadata-browse-handler-for-the-echo-adapter.md).</span></span> <span data-ttu-id="7ee8e-112">次のクラスについて明確に理解も必要です。</span><span class="sxs-lookup"><span data-stu-id="7ee8e-112">You must also have a clear understanding about the following classes:</span></span>  
  
-   `Microsoft.ServiceModel.Channels.MetadataRetrievalNode`
  
-   `Microsoft.ServiceModel.Channels.Common.IMetadataSearchHandler`  
  
-   `Microsoft.ServiceModel.Channels.MetadataRetrievalNodeDirections`  
  
## <a name="the-imetadatasearchhandler-interface"></a><span data-ttu-id="7ee8e-113">IMetadataSearchHandler インターフェイス</span><span class="sxs-lookup"><span data-stu-id="7ee8e-113">The IMetadataSearchHandler Interface</span></span>  
 <span data-ttu-id="7ee8e-114">`Microsoft.ServiceModel.Channels.Common.IMetadataSearchHandler`として定義されます。</span><span class="sxs-lookup"><span data-stu-id="7ee8e-114">The `Microsoft.ServiceModel.Channels.Common.IMetadataSearchHandler` is defined as:</span></span>  
  
```  
public interface IMetadataSearchHandler : IConnectionHandler, IDisposable  
{  
    MetadataRetrievalNode[] Search(string nodeId, string searchCriteria, int maxChildNodes, TimeSpan timeout);  
}  
```  
  
 <span data-ttu-id="7ee8e-115">`Microsoft.ServiceModel.Channels.Common.IMetadataSearchHandler.Search%2A`メソッドの配列を返します`Microsoft.ServiceModel.Channels.MetadataRetrievalNode`検索条件に基づいてオブジェクト。</span><span class="sxs-lookup"><span data-stu-id="7ee8e-115">The `Microsoft.ServiceModel.Channels.Common.IMetadataSearchHandler.Search%2A` method returns an array of `Microsoft.ServiceModel.Channels.MetadataRetrievalNode` objects based on the search criteria.</span></span> <span data-ttu-id="7ee8e-116">Search メソッドのパラメーターの定義は、次の表で説明します。</span><span class="sxs-lookup"><span data-stu-id="7ee8e-116">The parameter definitions for the Search method are described in the following table:</span></span>  
  
|<span data-ttu-id="7ee8e-117">**パラメーター**</span><span class="sxs-lookup"><span data-stu-id="7ee8e-117">**Parameter**</span></span>|<span data-ttu-id="7ee8e-118">**定義**</span><span class="sxs-lookup"><span data-stu-id="7ee8e-118">**Definition**</span></span>|  
|-------------------|--------------------|  
|<span data-ttu-id="7ee8e-119">nodeId</span><span class="sxs-lookup"><span data-stu-id="7ee8e-119">nodeId</span></span>|<span data-ttu-id="7ee8e-120">検索を開始するノード ID。</span><span class="sxs-lookup"><span data-stu-id="7ee8e-120">The node ID to start searching from.</span></span> <span data-ttu-id="7ee8e-121">場合は null または空の文字列 ("")、操作は、ルート ノード (「/」) から取得されます。</span><span class="sxs-lookup"><span data-stu-id="7ee8e-121">If null or an empty string (""), operations will be retrieved from the root node ("/").</span></span>|  
|<span data-ttu-id="7ee8e-122">searchCriteria</span><span class="sxs-lookup"><span data-stu-id="7ee8e-122">searchCriteria</span></span>|<span data-ttu-id="7ee8e-123">検索条件は、アダプターに固有です。</span><span class="sxs-lookup"><span data-stu-id="7ee8e-123">The search criteria, which is adapter-specific.</span></span> <span data-ttu-id="7ee8e-124">検索条件が指定されていない場合、アダプターは、すべてのノードを返す必要があります。</span><span class="sxs-lookup"><span data-stu-id="7ee8e-124">If no search criteria are specified, the adapter should return all nodes.</span></span>|  
|<span data-ttu-id="7ee8e-125">maxChildNodes</span><span class="sxs-lookup"><span data-stu-id="7ee8e-125">maxChildNodes</span></span>|<span data-ttu-id="7ee8e-126">返される結果のノードの最大数。</span><span class="sxs-lookup"><span data-stu-id="7ee8e-126">The maximum number of result nodes to return.</span></span> <span data-ttu-id="7ee8e-127">Int32.Max を使用すると、結果のすべてのノードを取得できます。</span><span class="sxs-lookup"><span data-stu-id="7ee8e-127">Use Int32.Max to retrieve all result nodes.</span></span><br /><br /> <span data-ttu-id="7ee8e-128">エコー アダプターによってサポートされていません。</span><span class="sxs-lookup"><span data-stu-id="7ee8e-128">Not supported by the Echo adapter.</span></span>|  
|<span data-ttu-id="7ee8e-129">timeout</span><span class="sxs-lookup"><span data-stu-id="7ee8e-129">timeout</span></span>|<span data-ttu-id="7ee8e-130">操作が完了するに使用できる最大時間。</span><span class="sxs-lookup"><span data-stu-id="7ee8e-130">The maximum time allowed for the operation to complete.</span></span><br /><br /> <span data-ttu-id="7ee8e-131">エコー アダプターによってサポートされていません。</span><span class="sxs-lookup"><span data-stu-id="7ee8e-131">Not supported by the Echo adapter.</span></span>|  
  
 <span data-ttu-id="7ee8e-132">検索の結果をカテゴリのノードまたはノードの操作、またはその両方を返す、アダプターを選択できます。</span><span class="sxs-lookup"><span data-stu-id="7ee8e-132">For search result, your adapter can choose to return either category nodes or operation nodes, or both.</span></span> <span data-ttu-id="7ee8e-133">アダプターが最大検索機能の種類をサポートしています。</span><span class="sxs-lookup"><span data-stu-id="7ee8e-133">It is up to the type of search feature your adapter supports.</span></span>  
  
## <a name="echo-adapter-metadata-search"></a><span data-ttu-id="7ee8e-134">エコー アダプター メタデータの検索</span><span class="sxs-lookup"><span data-stu-id="7ee8e-134">Echo adapter Metadata Search</span></span>  
 <span data-ttu-id="7ee8e-135">によって、ターゲット システムのカテゴリと操作の配列を構築する方法はたくさんあります`Microsoft.ServiceModel.Channels.MetadataRetrievalNode`オブジェクトを返します。</span><span class="sxs-lookup"><span data-stu-id="7ee8e-135">Depending on your target system's categories and operations, there are many ways to build an array of `Microsoft.ServiceModel.Channels.MetadataRetrievalNode` objects to return.</span></span> <span data-ttu-id="7ee8e-136">エコー アダプターは、検索機能を実装する方法は、次の一覧にそのノード ID を持つすべての操作を経由する場合します。</span><span class="sxs-lookup"><span data-stu-id="7ee8e-136">The way Echo adapter implements the search functionality is to go through every operation with its node ID in the following list:</span></span>  
  
```  
Echo/OnReceiveEcho, inbound operation  
Echo/EchoStrings, outbound operation  
Echo/EchoGreetings, outbound operation  
Echo/EchoGreetingFromFile, outbound operation  
```  
  
- <span data-ttu-id="7ee8e-137">ノード ID には、検索条件が一致すると、作成、`Microsoft.ServiceModel.Channels.MetadataRetrievalNode`オブジェクト、操作のノード ID を使用し、値を持つプロパティを割り当てます。</span><span class="sxs-lookup"><span data-stu-id="7ee8e-137">If the node ID then matches the search criteria, it creates a `Microsoft.ServiceModel.Channels.MetadataRetrievalNode` object using the node ID of the operation, and then assigns the properties with values.</span></span> <span data-ttu-id="7ee8e-138">例を次に示します。</span><span class="sxs-lookup"><span data-stu-id="7ee8e-138">For example,</span></span>  
  
  ```  
  MetadataRetrievalNode nodeInbound = new MetadataRetrievalNode("Echo/OnReceiveEcho"); //create the MetadataRetrievalNode using the operation's node ID.  
  nodeInbound.DisplayName = "OnReceiveEcho"; //The Display Name shown in the Name column of the Add Adapter Service Reference Visual Studio Plug-in  
  nodeInbound.Description = "This operation echoes the location and length of a file dropped in the specified file system.";  //The Description shown as the tool tip in the Add Adapter Service Visual Studio Plug-in  
  nodeInbound.Direction = MetadataRetrievalNodeDirections.Inbound;    //It is an inbound operation  
  nodeInbound.IsOperation = true;  //It is an operation, not category.  
  ```  
  
- <span data-ttu-id="7ee8e-139">コレクションにオブジェクトを追加し、 `Microsoft.ServiceModel.Channels.MetadataRetrievalNode`s、たとえば、</span><span class="sxs-lookup"><span data-stu-id="7ee8e-139">And then add the object to a collection of the `Microsoft.ServiceModel.Channels.MetadataRetrievalNode`s, for example,</span></span>  
  
  ```  
  resultList.Add(nodeInbound);  
  ```  
  
- <span data-ttu-id="7ee8e-140">最後に配列形式のコレクションを返します。</span><span class="sxs-lookup"><span data-stu-id="7ee8e-140">Lastly returns the collection in an array format.</span></span>  
  
  ```  
  return resultList.ToArray();  
  ```  
  
  <span data-ttu-id="7ee8e-141">使用することができます、[!INCLUDE[addadapterservrefshort](../../includes/addadapterservrefshort-md.md)]と[!INCLUDE[consumeadapterservshort](../../includes/consumeadapterservshort-md.md)]接続ベースの検索を使用可能な操作を実行するためのツール。</span><span class="sxs-lookup"><span data-stu-id="7ee8e-141">You can use the [!INCLUDE[addadapterservrefshort](../../includes/addadapterservrefshort-md.md)] and [!INCLUDE[consumeadapterservshort](../../includes/consumeadapterservshort-md.md)] tools to perform a connection-based search for the available operations.</span></span> <span data-ttu-id="7ee8e-142">たとえば、次の図を示します文字列の検索条件の場合**Greeting**、検索、 **EchoGreetings**と**EchoGreetingFromFile**操作です。</span><span class="sxs-lookup"><span data-stu-id="7ee8e-142">For example, the following figure shows that when the searching criteria is the string **Greeting**, the search returns the **EchoGreetings** and **EchoGreetingFromFile** operations.</span></span>  
  
  <span data-ttu-id="7ee8e-143">![](../../adapters-and-accelerators/wcf-lob-adapter-sdk/media/874c046a-590f-4047-9b9c-bb8074664755.gif "874c046a-590f-4047-9b9c-bb8074664755")</span><span class="sxs-lookup"><span data-stu-id="7ee8e-143">![](../../adapters-and-accelerators/wcf-lob-adapter-sdk/media/874c046a-590f-4047-9b9c-bb8074664755.gif "874c046a-590f-4047-9b9c-bb8074664755")</span></span>  
  
  <span data-ttu-id="7ee8e-144">一致が検出されない場合、いずれかのツールは次の図に示すように、エラー メッセージを返します。</span><span class="sxs-lookup"><span data-stu-id="7ee8e-144">If no match is found, either tool will return the error message shown in the following figure.</span></span>  
  
  <span data-ttu-id="7ee8e-145">![](../../adapters-and-accelerators/wcf-lob-adapter-sdk/media/cb1f79a2-a63d-4828-9dce-905c026cd1dc.gif "cb1f79a2-a63d-4828-9dce-905c026cd1dc")</span><span class="sxs-lookup"><span data-stu-id="7ee8e-145">![](../../adapters-and-accelerators/wcf-lob-adapter-sdk/media/cb1f79a2-a63d-4828-9dce-905c026cd1dc.gif "cb1f79a2-a63d-4828-9dce-905c026cd1dc")</span></span>  
  
## <a name="implementing-the-imetadatasearchhandler"></a><span data-ttu-id="7ee8e-146">IMetadataSearchHandler を実装します。</span><span class="sxs-lookup"><span data-stu-id="7ee8e-146">Implementing the IMetadataSearchHandler</span></span>  
 <span data-ttu-id="7ee8e-147">実装、`Microsoft.ServiceModel.Channels.Common.IMetadataSearchHandler.Search%2A`のメソッド、`Microsoft.ServiceModel.Channels.Common.IMetadataSearchHandler`インターフェイス。</span><span class="sxs-lookup"><span data-stu-id="7ee8e-147">You will implement the `Microsoft.ServiceModel.Channels.Common.IMetadataSearchHandler.Search%2A` method of the `Microsoft.ServiceModel.Channels.Common.IMetadataSearchHandler` interface.</span></span> <span data-ttu-id="7ee8e-148">操作の表示名が検索条件に一致する場合は作成、 `Microsoft.ServiceModel.Channels.MetadataRetrievalNode` 、その操作のオブジェクトし、の配列にそのオブジェクトを追加、`Microsoft.ServiceModel.Channels.MetadataRetrievalNode`オブジェクト。</span><span class="sxs-lookup"><span data-stu-id="7ee8e-148">If the operation's display name matches the search criteria, you will create a `Microsoft.ServiceModel.Channels.MetadataRetrievalNode` object for that operation, and then add that object to an array of the `Microsoft.ServiceModel.Channels.MetadataRetrievalNode` objects.</span></span>  
  
#### <a name="to-update-the-echoadaptermetadatasearchhandler-class"></a><span data-ttu-id="7ee8e-149">EchoAdapterMetadataSearchHandler クラスを更新するには</span><span class="sxs-lookup"><span data-stu-id="7ee8e-149">To update the EchoAdapterMetadataSearchHandler class</span></span>  
  
1.  <span data-ttu-id="7ee8e-150">ソリューション エクスプ ローラーで、 **EchoAdapterMetadataSearchHandler.cs**ファイル。</span><span class="sxs-lookup"><span data-stu-id="7ee8e-150">In Solution Explorer, double-click the **EchoAdapterMetadataSearchHandler.cs** file.</span></span>  
  
2.  <span data-ttu-id="7ee8e-151">Visual Studio エディターでの内部、**検索**メソッドを次に、既存のロジックを置き換えます。</span><span class="sxs-lookup"><span data-stu-id="7ee8e-151">In the Visual Studio editor, inside the **Search** method, replace the existing logic with the following.</span></span> <span data-ttu-id="7ee8e-152">このロジックを作成、`Microsoft.ServiceModel.Channels.MetadataRetrievalNode`エコー/OnReceiveEcho が指定した検索条件と一致するかどうかのオブジェクトします。</span><span class="sxs-lookup"><span data-stu-id="7ee8e-152">This logic creates a `Microsoft.ServiceModel.Channels.MetadataRetrievalNode` object if Echo/OnReceiveEcho matches the specified search criteria.</span></span>  
  
    ```csharp  
    List<MetadataRetrievalNode> resultList = new List<MetadataRetrievalNode>();  
    if ("OnReceiveEcho".ToLower().Contains(searchCriteria.ToLower()))  
    {  
        MetadataRetrievalNode nodeInbound = new MetadataRetrievalNode("Echo/OnReceiveEcho");  
        nodeInbound.DisplayName = "OnReceiveEcho";  
        nodeInbound.Description = "This operation echoes the location and length of a file dropped in the specified file system.";  
        nodeInbound.Direction = MetadataRetrievalNodeDirections.Inbound;  
        nodeInbound.IsOperation = true;  
        resultList.Add(nodeInbound);  
    }  
    ```  
  
3.  <span data-ttu-id="7ee8e-153">作成するには、次のロジックの追加を続行する`Microsoft.ServiceModel.Channels.MetadataRetrievalNode`エコー/EchoStrings が指定した検索条件と一致するかどうかのオブジェクトします。</span><span class="sxs-lookup"><span data-stu-id="7ee8e-153">Continue adding the following logic to create a `Microsoft.ServiceModel.Channels.MetadataRetrievalNode` object if Echo/EchoStrings matches the specified search criteria.</span></span>  
  
    ```csharp  
    if ("EchoStrings".ToLower().Contains(searchCriteria.ToLower()))  
    {  
        MetadataRetrievalNode outOpNode1 = new MetadataRetrievalNode("Echo/EchoStrings");  
        outOpNode1.DisplayName = "EchoStrings";  
        outOpNode1.Description = "This operation echoes the incoming string COUNT number of times in a string array.";  
        outOpNode1.Direction = MetadataRetrievalNodeDirections.Outbound;  
        outOpNode1.IsOperation = true;  
        resultList.Add(outOpNode1);  
    }  
    ```  
  
4.  <span data-ttu-id="7ee8e-154">作成するには、次のロジックの追加を続行する`Microsoft.ServiceModel.Channels.MetadataRetrievalNode`エコー/EchoGreetings が指定した検索条件と一致するかどうかのオブジェクトします。</span><span class="sxs-lookup"><span data-stu-id="7ee8e-154">Continue adding the following logic to create a `Microsoft.ServiceModel.Channels.MetadataRetrievalNode` object if Echo/EchoGreetings matches the specified search criteria.</span></span>  
  
    ```csharp  
    if ("EchoGreetings".ToLower().Contains(searchCriteria.ToLower()))  
        {  
            MetadataRetrievalNode outOpNode2 = new MetadataRetrievalNode("Echo/EchoGreetings");  
            outOpNode2.DisplayName = "EchoGreetings";  
            outOpNode2.Description = "This operation echoes the incoming Greeting object COUNT number of times in an array of type Greeting.";  
            outOpNode2.Direction = MetadataRetrievalNodeDirections.Outbound;  
            outOpNode2.IsOperation = true;  
            resultList.Add(outOpNode2);  
        }  
    ```  
  
5.  <span data-ttu-id="7ee8e-155">作成する次のコードの追加を続行する`Microsoft.ServiceModel.Channels.MetadataRetrievalNode`エコー/EchoGreetingFromFile が指定した検索条件と一致するかどうかのオブジェクトします。</span><span class="sxs-lookup"><span data-stu-id="7ee8e-155">Continue adding the following code to create a `Microsoft.ServiceModel.Channels.MetadataRetrievalNode` object if Echo/EchoGreetingFromFile matches the specified search criteria.</span></span>  
  
    ```csharp  
    if ("EchoCustomGreetingFromFile".ToLower().Contains(searchCriteria.ToLower()))  
    {  
        MetadataRetrievalNode outOpNode3 = new MetadataRetrievalNode("Echo/EchoCustomGreetingFromFile");  
        outOpNode3.DisplayName = "EchoCustomGreetingFromFile";  
        outOpNode3.Description = "This operation echoes the greeting object by reading its instance from a file. The Greeting object's metadata is obtained from a predefined XSD file.";  
        outOpNode3.Direction = MetadataRetrievalNodeDirections.Outbound;  
        outOpNode3.IsOperation = true;  
        resultList.Add(outOpNode3);  
    }  
    ```  
  
6.  <span data-ttu-id="7ee8e-156">配列を返すには、次のコードの追加を続行`Microsoft.ServiceModel.Channels.MetadataRetrievalNode`オブジェクト。</span><span class="sxs-lookup"><span data-stu-id="7ee8e-156">Continue adding the following code to return an array of `Microsoft.ServiceModel.Channels.MetadataRetrievalNode` objects.</span></span>  
  
    ```csharp  
    return resultList.ToArray();  
    ```  
  
7.  <span data-ttu-id="7ee8e-157">Visual Studio での**ファイル** メニューのをクリックして**すべて保存**します。</span><span class="sxs-lookup"><span data-stu-id="7ee8e-157">In Visual Studio, on the **File** menu, click **Save All**.</span></span>  
  
8.  <span data-ttu-id="7ee8e-158">**[ビルド]** メニューの **[ソリューションのビルド]** をクリックします。</span><span class="sxs-lookup"><span data-stu-id="7ee8e-158">On the **Build** menu, click **Build Solution**.</span></span> <span data-ttu-id="7ee8e-159">プロジェクトを正常にコンパイルする必要があります。</span><span class="sxs-lookup"><span data-stu-id="7ee8e-159">You should successfully compiled the project.</span></span> <span data-ttu-id="7ee8e-160">そうでない場合は、上記のすべての手順に従っていることを確認します。</span><span class="sxs-lookup"><span data-stu-id="7ee8e-160">If not, ensure that you have followed every step above.</span></span>  
  
    > [!NOTE]
    >  <span data-ttu-id="7ee8e-161">これで作業が保存されました。</span><span class="sxs-lookup"><span data-stu-id="7ee8e-161">You saved your work.</span></span> <span data-ttu-id="7ee8e-162">安全にこの時点で Visual Studio を閉じて、次の手順に進むまたは[手順 6。エコー アダプターのメタデータ解決ハンドラーを実装する](../../adapters-and-accelerators/wcf-lob-adapter-sdk/step-6-implement-the-metadata-resolve-handler-for-the-echo-adapter.md)します。</span><span class="sxs-lookup"><span data-stu-id="7ee8e-162">You can safely close Visual Studio at this time or go to the next step, [Step 6: Implement the Metadata Resolve Handler for the Echo Adapter](../../adapters-and-accelerators/wcf-lob-adapter-sdk/step-6-implement-the-metadata-resolve-handler-for-the-echo-adapter.md).</span></span>  
  
## <a name="what-did-i-just-do"></a><span data-ttu-id="7ee8e-163">でしただけ何か。</span><span class="sxs-lookup"><span data-stu-id="7ee8e-163">What Did I Just Do?</span></span>  
 <span data-ttu-id="7ee8e-164">だけ、エコー アダプターの機能を実装することで検索するメタデータが実装されている、`Microsoft.ServiceModel.Channels.Common.IMetadataSearchHandler.Search%2A`のメソッド、`Microsoft.ServiceModel.Channels.Common.IMetadataSearchHandler`インターフェイス。</span><span class="sxs-lookup"><span data-stu-id="7ee8e-164">You just implemented the metadata searching capability of the Echo adapter, by implementing the `Microsoft.ServiceModel.Channels.Common.IMetadataSearchHandler.Search%2A` method of the `Microsoft.ServiceModel.Channels.Common.IMetadataSearchHandler` interface.</span></span> <span data-ttu-id="7ee8e-165">具体的には、作成した、`Microsoft.ServiceModel.Channels.MetadataRetrievalNode`オブジェクトのすべての操作を条件に一致しての配列が返されます、`Microsoft.ServiceModel.Channels.MetadataRetrievalNode`オブジェクト。</span><span class="sxs-lookup"><span data-stu-id="7ee8e-165">Specifically, you created a `Microsoft.ServiceModel.Channels.MetadataRetrievalNode` object for every operation that matches the criteria and then returned an array of the `Microsoft.ServiceModel.Channels.MetadataRetrievalNode` objects.</span></span>  
  
## <a name="next-steps"></a><span data-ttu-id="7ee8e-166">次の手順</span><span class="sxs-lookup"><span data-stu-id="7ee8e-166">Next Steps</span></span>  
 <span data-ttu-id="7ee8e-167">機能、および送信および受信のメッセージ交換機能を解決するメタデータを実装します。</span><span class="sxs-lookup"><span data-stu-id="7ee8e-167">You will implement the metadata resolving capability, and the outbound and inbound message exchange capabilities.</span></span> <span data-ttu-id="7ee8e-168">最後に、ビルドされ、エコー アダプターを展開します。</span><span class="sxs-lookup"><span data-stu-id="7ee8e-168">Finally, you will build and deploy the Echo adapter.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="7ee8e-169">参照</span><span class="sxs-lookup"><span data-stu-id="7ee8e-169">See Also</span></span>  
 <span data-ttu-id="7ee8e-170">[手順 4:エコー アダプターのメタデータ参照ハンドラーを実装します。](../../adapters-and-accelerators/wcf-lob-adapter-sdk/step-4-implement-the-metadata-browse-handler-for-the-echo-adapter.md) </span><span class="sxs-lookup"><span data-stu-id="7ee8e-170">[Step 4: Implement the Metadata Browse Handler for the Echo Adapter](../../adapters-and-accelerators/wcf-lob-adapter-sdk/step-4-implement-the-metadata-browse-handler-for-the-echo-adapter.md) </span></span>  
 <span data-ttu-id="7ee8e-171">[手順 6:エコー アダプターのメタデータ解決ハンドラーを実装します。](../../adapters-and-accelerators/wcf-lob-adapter-sdk/step-6-implement-the-metadata-resolve-handler-for-the-echo-adapter.md) </span><span class="sxs-lookup"><span data-stu-id="7ee8e-171">[Step 6: Implement the Metadata Resolve Handler for the Echo Adapter](../../adapters-and-accelerators/wcf-lob-adapter-sdk/step-6-implement-the-metadata-resolve-handler-for-the-echo-adapter.md) </span></span>  
 [<span data-ttu-id="7ee8e-172">チュートリアル 1:エコー アダプターを開発する</span><span class="sxs-lookup"><span data-stu-id="7ee8e-172">Tutorial 1: Develop the Echo Adapter</span></span>](../../adapters-and-accelerators/wcf-lob-adapter-sdk/tutorial-1-develop-the-echo-adapter.md)