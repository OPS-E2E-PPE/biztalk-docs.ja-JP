---
title: "手順 5: エコー アダプターのメタデータ検索ハンドラーを実装する |Microsoft ドキュメント"
ms.custom: 
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: 
ms.suite: 
ms.tgt_pltfrm: 
ms.topic: article
ms.assetid: 1a133a99-1d6c-4634-b928-0f4f23c6f6e4
caps.latest.revision: "17"
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: 8d241499e10a944eb1941b680bc73b97ce6ffd93
ms.sourcegitcommit: cb908c540d8f1a692d01dc8f313e16cb4b4e696d
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 09/20/2017
---
# <a name="step-5-implement-the-metadata-search-handler-for-the-echo-adapter"></a><span data-ttu-id="953ae-102">手順 5: エコー アダプターのメタデータの検索ハンドラーを実装します。</span><span class="sxs-lookup"><span data-stu-id="953ae-102">Step 5: Implement the Metadata Search Handler for the Echo Adapter</span></span>
<span data-ttu-id="953ae-103">![手順 5. の 9](../../adapters-and-accelerators/wcf-lob-adapter-sdk/media/step-5of9.gif "Step_5of9")</span><span class="sxs-lookup"><span data-stu-id="953ae-103">![Step 5 of 9](../../adapters-and-accelerators/wcf-lob-adapter-sdk/media/step-5of9.gif "Step_5of9")</span></span>  
  
 <span data-ttu-id="953ae-104">**所要時間:** 30 分</span><span class="sxs-lookup"><span data-stu-id="953ae-104">**Time to complete:** 30 minutes</span></span>  
  
 <span data-ttu-id="953ae-105">チュートリアルのこの手順では、エコー アダプターの検索機能を実装します。</span><span class="sxs-lookup"><span data-stu-id="953ae-105">In this step of the tutorial, you implement the search capability of the Echo adapter.</span></span> <span data-ttu-id="953ae-106">参照とは異なり、検索はオプションです。</span><span class="sxs-lookup"><span data-stu-id="953ae-106">Unlike browse, search is optional.</span></span> <span data-ttu-id="953ae-107">よると、 [!INCLUDE[afproductnameshort](../../includes/afproductnameshort-md.md)]、検索機能をサポートするために実装する必要があります、`Microsoft.ServiceModel.Channels.Common.IMetadataSearchHandler`インターフェイスです。</span><span class="sxs-lookup"><span data-stu-id="953ae-107">According to the [!INCLUDE[afproductnameshort](../../includes/afproductnameshort-md.md)], to support search capability, you must implement the `Microsoft.ServiceModel.Channels.Common.IMetadataSearchHandler` interface.</span></span> <span data-ttu-id="953ae-108">エコー アダプターの場合、 [!INCLUDE[afdevwizardnameshort](../../includes/afdevwizardnameshort-md.md)] EchoAdapterMetadataSearchHandler と呼ばれる 1 つの派生クラスが自動的に生成されます。</span><span class="sxs-lookup"><span data-stu-id="953ae-108">For the Echo adapter, the [!INCLUDE[afdevwizardnameshort](../../includes/afdevwizardnameshort-md.md)] automatically generates one derived class called EchoAdapterMetadataSearchHandler.</span></span>  
  
 <span data-ttu-id="953ae-109">最初に、このインターフェイスを実装する方法の理解を深めるために EchoAdapterMetadataSearchHandler クラスを更新する設定する方法について`Microsoft.ServiceModel.Channels.MetadataRetrievalNode`オブジェクト、およびで、検索結果の表示方法、[!INCLUDE[addadapterservrefshort](../../includes/addadapterservrefshort-md.md)]ツールです。</span><span class="sxs-lookup"><span data-stu-id="953ae-109">You first update the EchoAdapterMetadataSearchHandler class to get a better understanding of how to implement this interface, how to populate  `Microsoft.ServiceModel.Channels.MetadataRetrievalNode` object, and how the search results appear in the [!INCLUDE[addadapterservrefshort](../../includes/addadapterservrefshort-md.md)] tool.</span></span>  
  
## <a name="prerequisites"></a><span data-ttu-id="953ae-110">前提条件</span><span class="sxs-lookup"><span data-stu-id="953ae-110">Prerequisites</span></span>  
 <span data-ttu-id="953ae-111">この手順を開始する前に完了[手順 4: エコー アダプターのメタデータ参照ハンドラーの実装](../../adapters-and-accelerators/wcf-lob-adapter-sdk/step-4-implement-the-metadata-browse-handler-for-the-echo-adapter.md)です。</span><span class="sxs-lookup"><span data-stu-id="953ae-111">Before you begin this step, complete [Step 4: Implement the Metadata Browse Handler for the Echo Adapter](../../adapters-and-accelerators/wcf-lob-adapter-sdk/step-4-implement-the-metadata-browse-handler-for-the-echo-adapter.md).</span></span> <span data-ttu-id="953ae-112">次のクラスについて明確に理解も必要です。</span><span class="sxs-lookup"><span data-stu-id="953ae-112">You must also have a clear understanding about the following classes:</span></span>  
  
-   `Microsoft.ServiceModel.Channels.MetadataRetrievalNode`
  
-   `Microsoft.ServiceModel.Channels.Common.IMetadataSearchHandler`  
  
-   `Microsoft.ServiceModel.Channels.MetadataRetrievalNodeDirections`  
  
## <a name="the-imetadatasearchhandler-interface"></a><span data-ttu-id="953ae-113">IMetadataSearchHandler インターフェイス</span><span class="sxs-lookup"><span data-stu-id="953ae-113">The IMetadataSearchHandler Interface</span></span>  
 <span data-ttu-id="953ae-114">`Microsoft.ServiceModel.Channels.Common.IMetadataSearchHandler`として定義されます。</span><span class="sxs-lookup"><span data-stu-id="953ae-114">The `Microsoft.ServiceModel.Channels.Common.IMetadataSearchHandler` is defined as:</span></span>  
  
```  
public interface IMetadataSearchHandler : IConnectionHandler, IDisposable  
{  
    MetadataRetrievalNode[] Search(string nodeId, string searchCriteria, int maxChildNodes, TimeSpan timeout);  
}  
```  
  
 <span data-ttu-id="953ae-115">`Microsoft.ServiceModel.Channels.Common.IMetadataSearchHandler.Search%2A`メソッドの配列を返します`Microsoft.ServiceModel.Channels.MetadataRetrievalNode`オブジェクトの検索条件をベースにします。</span><span class="sxs-lookup"><span data-stu-id="953ae-115">The `Microsoft.ServiceModel.Channels.Common.IMetadataSearchHandler.Search%2A` method returns an array of `Microsoft.ServiceModel.Channels.MetadataRetrievalNode` objects based on the search criteria.</span></span> <span data-ttu-id="953ae-116">Search メソッドのパラメーターの定義は、次の表で説明します。</span><span class="sxs-lookup"><span data-stu-id="953ae-116">The parameter definitions for the Search method are described in the following table:</span></span>  
  
|<span data-ttu-id="953ae-117">**パラメーター**</span><span class="sxs-lookup"><span data-stu-id="953ae-117">**Parameter**</span></span>|<span data-ttu-id="953ae-118">**定義**</span><span class="sxs-lookup"><span data-stu-id="953ae-118">**Definition**</span></span>|  
|-------------------|--------------------|  
|<span data-ttu-id="953ae-119">NodeId</span><span class="sxs-lookup"><span data-stu-id="953ae-119">nodeId</span></span>|<span data-ttu-id="953ae-120">検索を開始するノード ID。</span><span class="sxs-lookup"><span data-stu-id="953ae-120">The node ID to start searching from.</span></span> <span data-ttu-id="953ae-121">場合は null または空の文字列 ("")、操作をルート ノード (「/」) から取得されます。</span><span class="sxs-lookup"><span data-stu-id="953ae-121">If null or an empty string (""), operations will be retrieved from the root node ("/").</span></span>|  
|<span data-ttu-id="953ae-122">searchCriteria</span><span class="sxs-lookup"><span data-stu-id="953ae-122">searchCriteria</span></span>|<span data-ttu-id="953ae-123">検索条件は、アダプターに固有です。</span><span class="sxs-lookup"><span data-stu-id="953ae-123">The search criteria, which is adapter-specific.</span></span> <span data-ttu-id="953ae-124">検索条件が指定されていない場合、アダプターは、すべてのノードを返す必要があります。</span><span class="sxs-lookup"><span data-stu-id="953ae-124">If no search criteria are specified, the adapter should return all nodes.</span></span>|  
|<span data-ttu-id="953ae-125">maxChildNodes</span><span class="sxs-lookup"><span data-stu-id="953ae-125">maxChildNodes</span></span>|<span data-ttu-id="953ae-126">返される結果のノードの最大数。</span><span class="sxs-lookup"><span data-stu-id="953ae-126">The maximum number of result nodes to return.</span></span> <span data-ttu-id="953ae-127">Int32.Max を使用して、結果のすべてのノードを取得します。</span><span class="sxs-lookup"><span data-stu-id="953ae-127">Use Int32.Max to retrieve all result nodes.</span></span><br /><br /> <span data-ttu-id="953ae-128">エコー アダプターによってサポートされていません。</span><span class="sxs-lookup"><span data-stu-id="953ae-128">Not supported by the Echo adapter.</span></span>|  
|<span data-ttu-id="953ae-129">timeout</span><span class="sxs-lookup"><span data-stu-id="953ae-129">timeout</span></span>|<span data-ttu-id="953ae-130">操作が完了する許可された最大時間。</span><span class="sxs-lookup"><span data-stu-id="953ae-130">The maximum time allowed for the operation to complete.</span></span><br /><br /> <span data-ttu-id="953ae-131">エコー アダプターによってサポートされていません。</span><span class="sxs-lookup"><span data-stu-id="953ae-131">Not supported by the Echo adapter.</span></span>|  
  
 <span data-ttu-id="953ae-132">検索結果、アダプターは、カテゴリのノードまたは操作のノード、またはその両方を返すを選択できます。</span><span class="sxs-lookup"><span data-stu-id="953ae-132">For search result, your adapter can choose to return either category nodes or operation nodes, or both.</span></span> <span data-ttu-id="953ae-133">アダプターはまで検索機能の種類をサポートしています。</span><span class="sxs-lookup"><span data-stu-id="953ae-133">It is up to the type of search feature your adapter supports.</span></span>  
  
## <a name="echo-adapter-metadata-search"></a><span data-ttu-id="953ae-134">エコー アダプター メタデータの検索</span><span class="sxs-lookup"><span data-stu-id="953ae-134">Echo adapter Metadata Search</span></span>  
 <span data-ttu-id="953ae-135">によっては、ターゲット システムのカテゴリと操作の配列を作成する方法はたくさんあります`Microsoft.ServiceModel.Channels.MetadataRetrievalNode`で返されるオブジェクト。</span><span class="sxs-lookup"><span data-stu-id="953ae-135">Depending on your target system's categories and operations, there are many ways to build an array of `Microsoft.ServiceModel.Channels.MetadataRetrievalNode` objects to return.</span></span> <span data-ttu-id="953ae-136">エコー アダプター検索機能を実装する方法は、次の一覧には、そのノード ID を持つすべての操作を経由します。</span><span class="sxs-lookup"><span data-stu-id="953ae-136">The way Echo adapter implements the search functionality is to go through every operation with its node ID in the following list:</span></span>  
  
```  
Echo/OnReceiveEcho, inbound operation  
Echo/EchoStrings, outbound operation  
Echo/EchoGreetings, outbound operation  
Echo/EchoGreetingFromFile, outbound operation  
```  
  
-   <span data-ttu-id="953ae-137">作成し、ノード ID には、検索条件が一致すると、`Microsoft.ServiceModel.Channels.MetadataRetrievalNode`オブジェクトの操作のノード ID を使用し、値を持つプロパティを割り当てます。</span><span class="sxs-lookup"><span data-stu-id="953ae-137">If the node ID then matches the search criteria, it creates a `Microsoft.ServiceModel.Channels.MetadataRetrievalNode` object using the node ID of the operation, and then assigns the properties with values.</span></span> <span data-ttu-id="953ae-138">例を次に示します。</span><span class="sxs-lookup"><span data-stu-id="953ae-138">For example,</span></span>  
  
    ```  
    MetadataRetrievalNode nodeInbound = new MetadataRetrievalNode("Echo/OnReceiveEcho"); //create the MetadataRetrievalNode using the operation's node ID.  
    nodeInbound.DisplayName = "OnReceiveEcho"; //The Display Name shown in the Name column of the Add Adapter Service Reference Visual Studio Plug-in  
    nodeInbound.Description = "This operation echoes the location and length of a file dropped in the specified file system.";  //The Description shown as the tool tip in the Add Adapter Service Visual Studio Plug-in  
    nodeInbound.Direction = MetadataRetrievalNodeDirections.Inbound;    //It is an inbound operation  
    nodeInbound.IsOperation = true;  //It is an operation, not category.  
    ```  
  
-   <span data-ttu-id="953ae-139">コレクションにオブジェクトを追加したり、 `Microsoft.ServiceModel.Channels.MetadataRetrievalNode`s、たとえば、</span><span class="sxs-lookup"><span data-stu-id="953ae-139">And then add the object to a collection of the `Microsoft.ServiceModel.Channels.MetadataRetrievalNode`s, for example,</span></span>  
  
    ```  
    resultList.Add(nodeInbound);  
    ```  
  
-   <span data-ttu-id="953ae-140">最後に配列形式のコレクションを返します。</span><span class="sxs-lookup"><span data-stu-id="953ae-140">Lastly returns the collection in an array format.</span></span>  
  
    ```  
    return resultList.ToArray();  
    ```  
  
 <span data-ttu-id="953ae-141">使用することができます、[!INCLUDE[addadapterservrefshort](../../includes/addadapterservrefshort-md.md)]と[!INCLUDE[consumeadapterservshort](../../includes/consumeadapterservshort-md.md)]接続ベースの検索を使用可能な操作を実行するためのツールです。</span><span class="sxs-lookup"><span data-stu-id="953ae-141">You can use the [!INCLUDE[addadapterservrefshort](../../includes/addadapterservrefshort-md.md)] and [!INCLUDE[consumeadapterservshort](../../includes/consumeadapterservshort-md.md)] tools to perform a connection-based search for the available operations.</span></span> <span data-ttu-id="953ae-142">たとえば、次の図を検索条件が、文字列の場合**Greeting**、検索、 **EchoGreetings**と**EchoGreetingFromFile**操作です。</span><span class="sxs-lookup"><span data-stu-id="953ae-142">For example, the following figure shows that when the searching criteria is the string **Greeting**, the search returns the **EchoGreetings** and **EchoGreetingFromFile** operations.</span></span>  
  
 ![](../../adapters-and-accelerators/wcf-lob-adapter-sdk/media/874c046a-590f-4047-9b9c-bb8074664755.gif "874c046a-590f-4047-9b9c-bb8074664755")  
  
 <span data-ttu-id="953ae-143">一致するものが見つからない場合、どちらのツールは次の図に示すように、エラー メッセージを返します。</span><span class="sxs-lookup"><span data-stu-id="953ae-143">If no match is found, either tool will return the error message shown in the following figure.</span></span>  
  
 ![](../../adapters-and-accelerators/wcf-lob-adapter-sdk/media/cb1f79a2-a63d-4828-9dce-905c026cd1dc.gif "cb1f79a2-a63d-4828-9dce-905c026cd1dc")  
  
## <a name="implementing-the-imetadatasearchhandler"></a><span data-ttu-id="953ae-144">IMetadataSearchHandler を実装します。</span><span class="sxs-lookup"><span data-stu-id="953ae-144">Implementing the IMetadataSearchHandler</span></span>  
 <span data-ttu-id="953ae-145">実装、`Microsoft.ServiceModel.Channels.Common.IMetadataSearchHandler.Search%2A`のメソッド、`Microsoft.ServiceModel.Channels.Common.IMetadataSearchHandler`インターフェイスです。</span><span class="sxs-lookup"><span data-stu-id="953ae-145">You will implement the `Microsoft.ServiceModel.Channels.Common.IMetadataSearchHandler.Search%2A` method of the `Microsoft.ServiceModel.Channels.Common.IMetadataSearchHandler` interface.</span></span> <span data-ttu-id="953ae-146">操作の表示名には、検索条件が一致すると場合、は、作成、`Microsoft.ServiceModel.Channels.MetadataRetrievalNode`その操作のオブジェクトし、型の配列をそのオブジェクトを追加、`Microsoft.ServiceModel.Channels.MetadataRetrievalNode`オブジェクト。</span><span class="sxs-lookup"><span data-stu-id="953ae-146">If the operation's display name matches the search criteria, you will create a `Microsoft.ServiceModel.Channels.MetadataRetrievalNode` object for that operation, and then add that object to an array of the `Microsoft.ServiceModel.Channels.MetadataRetrievalNode` objects.</span></span>  
  
#### <a name="to-update-the-echoadaptermetadatasearchhandler-class"></a><span data-ttu-id="953ae-147">EchoAdapterMetadataSearchHandler クラスの更新</span><span class="sxs-lookup"><span data-stu-id="953ae-147">To update the EchoAdapterMetadataSearchHandler class</span></span>  
  
1.  <span data-ttu-id="953ae-148">ソリューション エクスプ ローラーで、 **EchoAdapterMetadataSearchHandler.cs**ファイル。</span><span class="sxs-lookup"><span data-stu-id="953ae-148">In Solution Explorer, double-click the **EchoAdapterMetadataSearchHandler.cs** file.</span></span>  
  
2.  <span data-ttu-id="953ae-149">Visual Studio エディターで、内部、**検索**メソッド、既存のロジックを次に置き換えます。</span><span class="sxs-lookup"><span data-stu-id="953ae-149">In the Visual Studio editor, inside the **Search** method, replace the existing logic with the following.</span></span> <span data-ttu-id="953ae-150">このロジックを作成、`Microsoft.ServiceModel.Channels.MetadataRetrievalNode`エコー/OnReceiveEcho が指定した検索条件に一致するかどうかのオブジェクトします。</span><span class="sxs-lookup"><span data-stu-id="953ae-150">This logic creates a `Microsoft.ServiceModel.Channels.MetadataRetrievalNode` object if Echo/OnReceiveEcho matches the specified search criteria.</span></span>  
  
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
  
3.  <span data-ttu-id="953ae-151">作成する次のロジックの追加を繰り返して、`Microsoft.ServiceModel.Channels.MetadataRetrievalNode`エコー/EchoStrings が指定した検索条件に一致するかどうかのオブジェクトします。</span><span class="sxs-lookup"><span data-stu-id="953ae-151">Continue adding the following logic to create a `Microsoft.ServiceModel.Channels.MetadataRetrievalNode` object if Echo/EchoStrings matches the specified search criteria.</span></span>  
  
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
  
4.  <span data-ttu-id="953ae-152">作成する次のロジックの追加を繰り返して、`Microsoft.ServiceModel.Channels.MetadataRetrievalNode`エコー/EchoGreetings が指定した検索条件に一致するかどうかのオブジェクトします。</span><span class="sxs-lookup"><span data-stu-id="953ae-152">Continue adding the following logic to create a `Microsoft.ServiceModel.Channels.MetadataRetrievalNode` object if Echo/EchoGreetings matches the specified search criteria.</span></span>  
  
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
  
5.  <span data-ttu-id="953ae-153">作成する次のコードの追加を繰り返して、`Microsoft.ServiceModel.Channels.MetadataRetrievalNode`エコー/EchoGreetingFromFile が指定した検索条件に一致するかどうかのオブジェクトします。</span><span class="sxs-lookup"><span data-stu-id="953ae-153">Continue adding the following code to create a `Microsoft.ServiceModel.Channels.MetadataRetrievalNode` object if Echo/EchoGreetingFromFile matches the specified search criteria.</span></span>  
  
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
  
6.  <span data-ttu-id="953ae-154">配列を返すには、次のコードの追加を繰り返して`Microsoft.ServiceModel.Channels.MetadataRetrievalNode`オブジェクト。</span><span class="sxs-lookup"><span data-stu-id="953ae-154">Continue adding the following code to return an array of `Microsoft.ServiceModel.Channels.MetadataRetrievalNode` objects.</span></span>  
  
    ```csharp  
    return resultList.ToArray();  
    ```  
  
7.  <span data-ttu-id="953ae-155">Visual Studio での**ファイル** メニューのをクリックして**すべて保存**です。</span><span class="sxs-lookup"><span data-stu-id="953ae-155">In Visual Studio, on the **File** menu, click **Save All**.</span></span>  
  
8.  <span data-ttu-id="953ae-156">**[ビルド]** メニューの **[ソリューションのビルド]**をクリックします。</span><span class="sxs-lookup"><span data-stu-id="953ae-156">On the **Build** menu, click **Build Solution**.</span></span> <span data-ttu-id="953ae-157">プロジェクトを正常にコンパイルする必要があります。</span><span class="sxs-lookup"><span data-stu-id="953ae-157">You should successfully compiled the project.</span></span> <span data-ttu-id="953ae-158">以外の場合は、上記のすべてのステップに従っていることを確認します。</span><span class="sxs-lookup"><span data-stu-id="953ae-158">If not, ensure that you have followed every step above.</span></span>  
  
    > [!NOTE]
    >  <span data-ttu-id="953ae-159">これで作業が保存されました。</span><span class="sxs-lookup"><span data-stu-id="953ae-159">You saved your work.</span></span> <span data-ttu-id="953ae-160">安全にこの時点で Visual Studio を終了したり、次の手順に進みます[手順 6: エコー アダプターのメタデータを解決するハンドラーの実装](../../adapters-and-accelerators/wcf-lob-adapter-sdk/step-6-implement-the-metadata-resolve-handler-for-the-echo-adapter.md)です。</span><span class="sxs-lookup"><span data-stu-id="953ae-160">You can safely close Visual Studio at this time or go to the next step, [Step 6: Implement the Metadata Resolve Handler for the Echo Adapter](../../adapters-and-accelerators/wcf-lob-adapter-sdk/step-6-implement-the-metadata-resolve-handler-for-the-echo-adapter.md).</span></span>  
  
## <a name="what-did-i-just-do"></a><span data-ttu-id="953ae-161">でしただけは何ですか。</span><span class="sxs-lookup"><span data-stu-id="953ae-161">What Did I Just Do?</span></span>  
 <span data-ttu-id="953ae-162">単に検索エコー アダプターの機能を実装することで、メタデータを実装して、`Microsoft.ServiceModel.Channels.Common.IMetadataSearchHandler.Search%2A`のメソッド、`Microsoft.ServiceModel.Channels.Common.IMetadataSearchHandler`インターフェイスです。</span><span class="sxs-lookup"><span data-stu-id="953ae-162">You just implemented the metadata searching capability of the Echo adapter, by implementing the `Microsoft.ServiceModel.Channels.Common.IMetadataSearchHandler.Search%2A` method of the `Microsoft.ServiceModel.Channels.Common.IMetadataSearchHandler` interface.</span></span> <span data-ttu-id="953ae-163">具体的には、作成した、`Microsoft.ServiceModel.Channels.MetadataRetrievalNode`オブジェクトの配列を返すし、条件を一致するすべての操作に、`Microsoft.ServiceModel.Channels.MetadataRetrievalNode`オブジェクト。</span><span class="sxs-lookup"><span data-stu-id="953ae-163">Specifically, you created a `Microsoft.ServiceModel.Channels.MetadataRetrievalNode` object for every operation that matches the criteria and then returned an array of the `Microsoft.ServiceModel.Channels.MetadataRetrievalNode` objects.</span></span>  
  
## <a name="next-steps"></a><span data-ttu-id="953ae-164">次の手順</span><span class="sxs-lookup"><span data-stu-id="953ae-164">Next Steps</span></span>  
 <span data-ttu-id="953ae-165">機能、および送信および受信のメッセージ交換の機能を解決するメタデータを実装します。</span><span class="sxs-lookup"><span data-stu-id="953ae-165">You will implement the metadata resolving capability, and the outbound and inbound message exchange capabilities.</span></span> <span data-ttu-id="953ae-166">最後に、ビルドされ、エコー アダプターを展開します。</span><span class="sxs-lookup"><span data-stu-id="953ae-166">Finally, you will build and deploy the Echo adapter.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="953ae-167">参照</span><span class="sxs-lookup"><span data-stu-id="953ae-167">See Also</span></span>  
 <span data-ttu-id="953ae-168">[手順 4: エコー アダプターのメタデータ参照のハンドラーを実装します。](../../adapters-and-accelerators/wcf-lob-adapter-sdk/step-4-implement-the-metadata-browse-handler-for-the-echo-adapter.md) </span><span class="sxs-lookup"><span data-stu-id="953ae-168">[Step 4: Implement the Metadata Browse Handler for the Echo Adapter](../../adapters-and-accelerators/wcf-lob-adapter-sdk/step-4-implement-the-metadata-browse-handler-for-the-echo-adapter.md) </span></span>  
 <span data-ttu-id="953ae-169">[手順 6: エコー アダプター メタデータの解決ハンドラーを実装します。](../../adapters-and-accelerators/wcf-lob-adapter-sdk/step-6-implement-the-metadata-resolve-handler-for-the-echo-adapter.md) </span><span class="sxs-lookup"><span data-stu-id="953ae-169">[Step 6: Implement the Metadata Resolve Handler for the Echo Adapter](../../adapters-and-accelerators/wcf-lob-adapter-sdk/step-6-implement-the-metadata-resolve-handler-for-the-echo-adapter.md) </span></span>  
 [<span data-ttu-id="953ae-170">チュートリアル 1: エコー アダプターを開発します。</span><span class="sxs-lookup"><span data-stu-id="953ae-170">Tutorial 1: Develop the Echo Adapter</span></span>](../../adapters-and-accelerators/wcf-lob-adapter-sdk/tutorial-1-develop-the-echo-adapter.md)