---
title: 参照および WCF LOB Adapter SDK を使用してメタデータの検索 |Microsoft ドキュメント
ms.custom: ''
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: ''
ms.suite: ''
ms.tgt_pltfrm: ''
ms.topic: article
ms.assetid: fbb4add7-6cc8-4b93-b559-471b6e31c01a
caps.latest.revision: ''
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: 67f4717c8621b798ff960487dfd156c4f0934dfc
ms.sourcegitcommit: 8418b1a8f38b7f56979cd6e203f0b591e2f40fe1
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 03/28/2018
---
# <a name="browse-and-search-metadata-using-the-wcf-lob-adapter-sdk"></a>WCF LOB Adapter SDK を使用してメタデータを参照および検索
このセクションでは、それぞれ IMetadataBrowseHandler と IMetadataSearchHandler を実装することによって、アダプターでの参照および検索機能を公開する方法に関する情報を提供します。  
  
## <a name="imetadatabrowsehandler"></a>IMetadataBrowseHandler  
 アダプターをプロジェクトに追加すると、IMetadataBrowseHandler はカテゴリと、アダプターをサポートする操作の参照を許可します。 これにより、アダプターのコンシューマー、デザイン時にメタデータ情報を表示して、クライアントの処理を必要とする操作のみを選択します。  
  
 使用する場合、[!INCLUDE[addadapterservreflong](../../includes/addadapterservreflong-md.md)]または[!INCLUDE[consumeadapterservlong](../../includes/consumeadapterservlong-md.md)]、IMetadataBrowseHandler に入力アダプターをプロジェクトに追加するには**選択コントラクト型**、**カテゴリを選択**、および**利用可能なカテゴリと操作**ボックス。  
  
 ![参照操作](../../adapters-and-accelerators/wcf-lob-adapter-sdk/media/b143971c-a50b-4ef2-a973-dfe4aa4fc17e.gif "b143971c-a50b-4ef2-a973-dfe4aa4fc17e")  
  
 次の例では、IMetadataBrowseHandler を実装する方法を示します。 カテゴリと、アダプターをサポートする操作に関する情報を含む MetadataRetrievalNode 配列を構築します。  
  
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
  
## <a name="imetadatasearchhandler"></a>IMetadataSearchHandler  
 アダプターで IMetadataSearchHandler を実装する操作名の一部など、検索語句を入力して、デザイン時に使用可能な操作を検索する機能を提供します。 これは、アダプターは、返される操作を制限するための検索値を入力するため、多くの操作を含まれている場合に非常に役立ちます。  
  
 使用する場合、[!INCLUDE[addadapterservreflong](../../includes/addadapterservreflong-md.md)]または[!INCLUDE[consumeadapterservlong](../../includes/consumeadapterservlong-md.md)]IMetadataSearchHandler 解決で入力文字列を検索する際、プロジェクトにアダプターを追加するには**カテゴリで検索**ボックス、および照合の一覧の項目を返します、 **利用可能なカテゴリと操作**ボックス。  
  
 ![検索操作](../../adapters-and-accelerators/wcf-lob-adapter-sdk/media/48dc9ca6-8697-42bf-9419-5fa35a19937f.gif "48dc9ca6-8697-42bf-9419-5fa35a19937f")  
  
 検索を実行することもできます。 op の形式でクエリ文字列として検索する値を渡すことによって = 値 WSDL またはアダプターのプロキシを生成するときに svcutil.exe を使用します。 エコー/EchoStrings 操作情報のみを返す svcutil.exe を使用する例を次に示します。  
  
```  
svcutil.exe “echov2://lobhostname/lobapplication?enableAuthentication=False&op=Echo/EchoStrings” /target:metadata  
  
```  
  
> [!NOTE]
>  [!INCLUDE[afproductnameshort](../../includes/afproductnameshort-md.md)]エコー *、% エコー % などの既定ワイルドカード検索機能は提供されません。 ワイルドカードまたは機能に一致するパターンを実装するアダプターの作成者の責任です。  
  
 次の例では、IMetadataSearchHandler を実装する方法を示します。 カテゴリと、アダプターをサポートする操作に関する情報を含む MetadataRetrievalNode 配列を構築します。  
  
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
  
## <a name="see-also"></a>参照  
 [開発アクティビティ](../../esb-toolkit/development-activities.md)