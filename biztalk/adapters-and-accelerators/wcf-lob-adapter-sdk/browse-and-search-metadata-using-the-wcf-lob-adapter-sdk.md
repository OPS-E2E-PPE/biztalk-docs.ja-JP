---
title: 参照および WCF LOB Adapter SDK を使用してメタデータの検索 |Microsoft Docs
ms.custom: ''
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: ''
ms.suite: ''
ms.tgt_pltfrm: ''
ms.topic: article
ms.assetid: fbb4add7-6cc8-4b93-b559-471b6e31c01a
caps.latest.revision: 6
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: ccf9889f395937f5ef1f4c6b1acda6b9413fc867
ms.sourcegitcommit: 381e83d43796a345488d54b3f7413e11d56ad7be
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 05/07/2019
ms.locfileid: "65363843"
---
# <a name="browse-and-search-metadata-using-the-wcf-lob-adapter-sdk"></a><span data-ttu-id="1b73d-102">WCF LOB Adapter SDK を使用してメタデータを参照および検索</span><span class="sxs-lookup"><span data-stu-id="1b73d-102">Browse and search metadata using the WCF LOB Adapter SDK</span></span>
<span data-ttu-id="1b73d-103">このセクションでは、IMetadataBrowseHandler と IMetadataSearchHandler をそれぞれ実装でアダプターを使用した参照および検索機能を公開する方法について説明します。</span><span class="sxs-lookup"><span data-stu-id="1b73d-103">This section provides information about how to expose browse and search functionality with an adapter by implementing IMetadataBrowseHandler and IMetadataSearchHandler, respectively.</span></span>  
  
## <a name="imetadatabrowsehandler"></a><span data-ttu-id="1b73d-104">IMetadataBrowseHandler</span><span class="sxs-lookup"><span data-stu-id="1b73d-104">IMetadataBrowseHandler</span></span>  
 <span data-ttu-id="1b73d-105">プロジェクトにアダプターを追加するときに IMetadataBrowseHandler はカテゴリと、アダプターをサポートする操作を参照できます。</span><span class="sxs-lookup"><span data-stu-id="1b73d-105">When adding an adapter to a project, IMetadataBrowseHandler allows browsing of the categories and operations that the adapter supports.</span></span> <span data-ttu-id="1b73d-106">これにより、アダプターのコンシューマー、デザイン時にメタデータ情報を表示して、クライアントの処理を必要とする操作のみを選択できます。</span><span class="sxs-lookup"><span data-stu-id="1b73d-106">This allows the adapter consumer to view metadata information at design time, and to select only the operations that the client process requires.</span></span>  
  
 <span data-ttu-id="1b73d-107">使用する場合、[!INCLUDE[addadapterservreflong](../../includes/addadapterservreflong-md.md)]または[!INCLUDE[consumeadapterservlong](../../includes/consumeadapterservlong-md.md)]、IMetadataBrowseHandler の設定をプロジェクトに、アダプターを追加する、**選択のコントラクト型**、**カテゴリを選択**、および**利用可能なカテゴリと操作**ボックス。</span><span class="sxs-lookup"><span data-stu-id="1b73d-107">When using the [!INCLUDE[addadapterservreflong](../../includes/addadapterservreflong-md.md)] or [!INCLUDE[consumeadapterservlong](../../includes/consumeadapterservlong-md.md)] to add an adapter to a project, the IMetadataBrowseHandler populates the **Select contract type**, **Select a Category**, and **Available categories and operations** boxes.</span></span>  
  
 <span data-ttu-id="1b73d-108">![操作を参照する](../../adapters-and-accelerators/wcf-lob-adapter-sdk/media/b143971c-a50b-4ef2-a973-dfe4aa4fc17e.gif "b143971c-a50b-4ef2-a973-dfe4aa4fc17e")</span><span class="sxs-lookup"><span data-stu-id="1b73d-108">![Browse Operations](../../adapters-and-accelerators/wcf-lob-adapter-sdk/media/b143971c-a50b-4ef2-a973-dfe4aa4fc17e.gif "b143971c-a50b-4ef2-a973-dfe4aa4fc17e")</span></span>  
  
 <span data-ttu-id="1b73d-109">次の例では、IMetadataBrowseHandler を実装する方法を示します。</span><span class="sxs-lookup"><span data-stu-id="1b73d-109">The following example demonstrates how to implement IMetadataBrowseHandler.</span></span> <span data-ttu-id="1b73d-110">これは、カテゴリと、アダプターをサポートする操作に関する情報を含む MetadataRetrievalNode 配列を構築します。</span><span class="sxs-lookup"><span data-stu-id="1b73d-110">It constructs a MetadataRetrievalNode array containing information on the categories and operations that the adapter supports.</span></span>  
  
```csharp  
public class EchoAdapterMetadataBrowseHandler : EchoAdapterHandlerBase, IMetadataBrowseHandler  
    {  
        /// <summary>  
        /// Initializes a new instance of the EchoAdapterMetadataBrowseHandler class  
        /// </summary>  
        public EchoAdapterMetadataBrowseHandler(EchoAdapterConnection connection  
            , MetadataLookup metadataLookup)  
            : base(connection, metadataLookup)  
        {  
        }  
  
        #region IMetadataBrowseHandler Members  
  
        /// <summary>  
        /// Retrieves an array of MetadataRetrievalNodes from the target system.  
        /// The browse operation will return nodes starting from the childStartIndex in the path provided in absoluteName, and the number of nodes returned is limited by maxChildNodes.  
        /// The method should complete within the specified timespan or throw a timeout exception.  
        /// If absoluteName is null or an empty string, return nodes starting from the root + childStartIndex.  
        /// If childStartIndex is zero, then return starting at the node indicated by absoluteName (or the root node if absoluteName is null or empty).  
        /// </summary>  
        public MetadataRetrievalNode[] Browse(string nodeId  
            , int childStartIndex  
            , int maxChildNodes, TimeSpan timeout)  
        {  
            // note we don't support timeout in this sample  
            if (MetadataRetrievalNode.Root.NodeId.Equals(nodeId))  
            {  
                MetadataRetrievalNode node = new MetadataRetrievalNode("EchoMainCategory");  
                node.DisplayName = "Main Category";  
                node.IsOperation = false;  
                node.Description = "This category contains inbound and outbound categories.";  
                node.Direction = MetadataRetrievalNodeDirections.Inbound | MetadataRetrievalNodeDirections.Outbound;  
                return new MetadataRetrievalNode[] { node };  
            }  
            else if( "EchoMainCategory".CompareTo(nodeId) == 0 )  
            {  
                // Inbound operations  
                MetadataRetrievalNode inOpNode1 = new MetadataRetrievalNode("Echo/OnReceiveEcho");  
                inOpNode1.DisplayName = "OnReceiveEcho";  
                inOpNode1.Description = "This operation echoes the location and length of a file dropped in the specified file system.";  
                inOpNode1.Direction = MetadataRetrievalNodeDirections.Inbound;  
                inOpNode1.IsOperation = true;  
                // Outbound operations  
                MetadataRetrievalNode outOpNode1 = new MetadataRetrievalNode("Echo/EchoStrings");  
                outOpNode1.DisplayName = "EchoStrings";  
                outOpNode1.Description = "This operation echoes the incoming string COUNT number of times in a string array.";  
                outOpNode1.Direction = MetadataRetrievalNodeDirections.Outbound;  
                outOpNode1.IsOperation = true;  
                MetadataRetrievalNode outOpNode2 = new MetadataRetrievalNode("Echo/EchoGreetings");  
                outOpNode2.DisplayName = "EchoGreetings";  
                outOpNode2.Description = "This operation echoes the incoming Greeting object COUNT number of times in an array of type Greeting.";  
                outOpNode2.Direction = MetadataRetrievalNodeDirections.Outbound;  
                outOpNode2.IsOperation = true;  
                MetadataRetrievalNode outOpNode3 = new MetadataRetrievalNode("Echo/EchoCustomGreetingFromFile");  
                outOpNode3.DisplayName = "EchoCustomGreetingFromFile";  
                outOpNode3.Description = "This operation echoes the greeting object by reading its instance from a file. The Greeting object's metadata is obtained from a predefined XSD file.";  
                outOpNode3.Direction = MetadataRetrievalNodeDirections.Outbound;  
                outOpNode3.IsOperation = true;  
                return new MetadataRetrievalNode[] { inOpNode1, outOpNode1, outOpNode2, outOpNode3 };  
            }  
  
            return null;  
        }  
  
        #endregion IMetadataBrowseHandler Members  
    }  
```  
  
## <a name="imetadatasearchhandler"></a><span data-ttu-id="1b73d-111">IMetadataSearchHandler</span><span class="sxs-lookup"><span data-stu-id="1b73d-111">IMetadataSearchHandler</span></span>  
 <span data-ttu-id="1b73d-112">アダプターで IMetadataSearchHandler を実装するには、操作名の一部などの検索語句を入力して、デザイン時に使用可能な操作を検索する機能が提供します。</span><span class="sxs-lookup"><span data-stu-id="1b73d-112">Implementing IMetadataSearchHandler within an adapter provides the ability to search for available operations at design time by entering a search term, such as a portion of an operation name.</span></span> <span data-ttu-id="1b73d-113">これは、アダプターは、返される操作を制限する検索値を入力するため、多くの操作を含まれている場合に非常に役立ちます。</span><span class="sxs-lookup"><span data-stu-id="1b73d-113">This is very useful if your adapter contains many operations, since you can enter search values to limit the operations returned.</span></span>  
  
 <span data-ttu-id="1b73d-114">使用する場合、[!INCLUDE[addadapterservreflong](../../includes/addadapterservreflong-md.md)]または[!INCLUDE[consumeadapterservlong](../../includes/consumeadapterservlong-md.md)]IMetadataSearchHandler 解決で入力された文字列の検索をプロジェクトに、アダプターを追加する、**カテゴリで検索**ボックス、および照合の一覧の項目を返します、 **利用可能なカテゴリと操作**ボックス。</span><span class="sxs-lookup"><span data-stu-id="1b73d-114">When using the [!INCLUDE[addadapterservreflong](../../includes/addadapterservreflong-md.md)] or [!INCLUDE[consumeadapterservlong](../../includes/consumeadapterservlong-md.md)] to add an adapter to a project, the IMetadataSearchHandler resolves search strings entered in the **Search in category** box, and returns a list of matching items in the **Available categories and operations** box.</span></span>  
  
 <span data-ttu-id="1b73d-115">![検索操作](../../adapters-and-accelerators/wcf-lob-adapter-sdk/media/48dc9ca6-8697-42bf-9419-5fa35a19937f.gif "48dc9ca6-8697-42bf-9419-5fa35a19937f")</span><span class="sxs-lookup"><span data-stu-id="1b73d-115">![Search Operations](../../adapters-and-accelerators/wcf-lob-adapter-sdk/media/48dc9ca6-8697-42bf-9419-5fa35a19937f.gif "48dc9ca6-8697-42bf-9419-5fa35a19937f")</span></span>  
  
 <span data-ttu-id="1b73d-116">検索を実行することもできます。 WSDL またはアダプターのプロキシを生成するときに svcutil.exe を使用しての op の形式でクエリ文字列としての検索 の値を渡すことによって = 値。</span><span class="sxs-lookup"><span data-stu-id="1b73d-116">You can also perform searches with svcutil.exe when generating WSDL or proxy for an adapter, by passing the search value as a query string in the format of op=value.</span></span> <span data-ttu-id="1b73d-117">次にエコー/EchoStrings 操作情報のみを返す svcutil.exe を使用する例を示します。</span><span class="sxs-lookup"><span data-stu-id="1b73d-117">The following is an example of using svcutil.exe to return only the Echo/EchoStrings operation information.</span></span>  
  
```  
svcutil.exe “echov2://lobhostname/lobapplication?enableAuthentication=False&op=Echo/EchoStrings” /target:metadata  
  
```  
  
> [!NOTE]
>  <span data-ttu-id="1b73d-118">[!INCLUDE[afproductnameshort](../../includes/afproductnameshort-md.md)]エコー \*、%echo% などの既定ワイルドカード検索機能は提供されません。</span><span class="sxs-lookup"><span data-stu-id="1b73d-118">The [!INCLUDE[afproductnameshort](../../includes/afproductnameshort-md.md)] does not provide a default wildcard search functionality such as Echo\* or %Echo%.</span></span> <span data-ttu-id="1b73d-119">ワイルドカードまたは機能に一致するパターンを実装するために、アダプター作成者の責任です。</span><span class="sxs-lookup"><span data-stu-id="1b73d-119">It is up to the adapter author to implement wildcard or pattern matching functionality.</span></span>  
  
 <span data-ttu-id="1b73d-120">次の例では、IMetadataSearchHandler を実装する方法を示します。</span><span class="sxs-lookup"><span data-stu-id="1b73d-120">The following example demonstrates how to implement IMetadataSearchHandler.</span></span> <span data-ttu-id="1b73d-121">これは、カテゴリと、アダプターをサポートする操作に関する情報を含む MetadataRetrievalNode 配列を構築します。</span><span class="sxs-lookup"><span data-stu-id="1b73d-121">It constructs a MetadataRetrievalNode array containing information about the categories and operations that the adapter supports.</span></span>  
  
```csharp  
public class EchoAdapterMetadataSearchHandler : EchoAdapterHandlerBase, IMetadataSearchHandler  
    {  
        /// <summary>  
        /// Initializes a new instance of the EchoAdapterMetadataSearchHandler class  
        /// </summary>  
        public EchoAdapterMetadataSearchHandler(EchoAdapterConnection connection  
            , MetadataLookup metadataLookup)  
            : base(connection, metadataLookup)  
        {  
        }  
  
        #region IMetadataSearchHandler Members  
  
        /// <summary>  
        /// Retrieves an array of MetadataRetrievalNodes (see Microsoft.ServiceModel.Channels) from the target system.  
        /// The search will begin at the path provided in absoluteName, which points to a location in the tree of metadata nodes.  
        /// The contents of the array are filtered by SearchCriteria and the number of nodes returned is limited by maxChildNodes.  
        /// The method should complete within the specified timespan or throw a timeout exception.  If absoluteName is null or an empty string, return nodes starting from the root.  
        /// If SearchCriteria is null or an empty string, return all nodes.  
        /// </summary>  
        public MetadataRetrievalNode[] Search(string nodeId  
            , string searchCriteria  
            , int maxChildNodes, TimeSpan timeout)  
        {  
  
            List<MetadataRetrievalNode> resultList = new List<MetadataRetrievalNode>();  
            if ("OnReceiveEcho".ToLower().Contains(searchCriteria.ToLower()))  
            {  
                MetadataRetrievalNode nodeInbound = new MetadataRetrievalNode("Echo/OnReceiveEcho");  
                nodeInbound.DisplayName = "OnReceiveEcho";  
                nodeInbound.Description = "This operation echos the location and length of a file dropped in the specified file system.";  
                nodeInbound.Direction = MetadataRetrievalNodeDirections.Inbound;  
                nodeInbound.IsOperation = true;  
                resultList.Add(nodeInbound);  
            }  
            if ("EchoStrings".ToLower().Contains(searchCriteria.ToLower()))  
            {  
                MetadataRetrievalNode outOpNode1 = new MetadataRetrievalNode("Echo/EchoStrings");  
                outOpNode1.DisplayName = "EchoStrings";  
                outOpNode1.Description = "This operation echoes the incoming string COUNT number of times in a string array.";  
                outOpNode1.Direction = MetadataRetrievalNodeDirections.Outbound;  
                outOpNode1.IsOperation = true;  
                resultList.Add(outOpNode1);  
            }  
            if ("EchoGreetings".ToLower().Contains(searchCriteria.ToLower()))  
            {  
                MetadataRetrievalNode outOpNode2 = new MetadataRetrievalNode("Echo/EchoGreetings");  
                outOpNode2.DisplayName = "EchoGreetings";  
                outOpNode2.Description = "This operation echoes the incoming Greeting object COUNT number of times in an array of type Greeting.";  
                outOpNode2.Direction = MetadataRetrievalNodeDirections.Outbound;  
                outOpNode2.IsOperation = true;  
                resultList.Add(outOpNode2);  
            }  
            if ("EchoCustomGreetingFromFile".ToLower().Contains(searchCriteria.ToLower()))  
            {  
                MetadataRetrievalNode outOpNode3 = new MetadataRetrievalNode("Echo/EchoCustomGreetingFromFile");  
                outOpNode3.DisplayName = "EchoCustomGreetingFromFile";  
                outOpNode3.Description = "This operation echoes the greeting object by reading its instance from a file. The Greeting object's metadata is obtained from a predefined XSD file.";  
                outOpNode3.Direction = MetadataRetrievalNodeDirections.Outbound;  
                outOpNode3.IsOperation = true;  
                resultList.Add(outOpNode3);  
            }  
            return resultList.ToArray();  
        }  
  
        #endregion IMetadataSearchHandler Members  
    }  
```  
  
## <a name="see-also"></a><span data-ttu-id="1b73d-122">参照</span><span class="sxs-lookup"><span data-stu-id="1b73d-122">See Also</span></span>  
 [<span data-ttu-id="1b73d-123">開発アクティビティ</span><span class="sxs-lookup"><span data-stu-id="1b73d-123">Development Activities</span></span>](../../esb-toolkit/development-activities.md)