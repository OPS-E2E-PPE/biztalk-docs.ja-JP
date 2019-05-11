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
# <a name="step-5-implement-the-metadata-search-handler-for-the-echo-adapter"></a>手順 5:エコー アダプターのメタデータ検索ハンドラーを実装します。
![手順 5. の 9](../../adapters-and-accelerators/wcf-lob-adapter-sdk/media/step-5of9.gif "Step_5of9")  
  
 **所要時間:** 30 分  
  
 このチュートリアルの手順では、エコー アダプターの検索機能を実装します。 参照とは異なり、検索は省略可能です。 に従って、 [!INCLUDE[afproductnameshort](../../includes/afproductnameshort-md.md)]、検索機能をサポートするために実装する必要があります、`Microsoft.ServiceModel.Channels.Common.IMetadataSearchHandler`インターフェイス。 エコー アダプターの場合、 [!INCLUDE[afdevwizardnameshort](../../includes/afdevwizardnameshort-md.md)] EchoAdapterMetadataSearchHandler と呼ばれる 1 つの派生クラスが自動的に生成されます。  
  
 最初に、このインターフェイスを実装する方法の理解を深めるために、EchoAdapterMetadataSearchHandler クラスを更新する方法を設定する`Microsoft.ServiceModel.Channels.MetadataRetrievalNode`オブジェクト、および検索結果を表示する方法、[!INCLUDE[addadapterservrefshort](../../includes/addadapterservrefshort-md.md)]ツール。  
  
## <a name="prerequisites"></a>前提条件  
 この手順を開始する前に完了[手順 4。エコー アダプターのメタデータ参照ハンドラーを実装する](../../adapters-and-accelerators/wcf-lob-adapter-sdk/step-4-implement-the-metadata-browse-handler-for-the-echo-adapter.md)します。 次のクラスについて明確に理解も必要です。  
  
-   `Microsoft.ServiceModel.Channels.MetadataRetrievalNode`
  
-   `Microsoft.ServiceModel.Channels.Common.IMetadataSearchHandler`  
  
-   `Microsoft.ServiceModel.Channels.MetadataRetrievalNodeDirections`  
  
## <a name="the-imetadatasearchhandler-interface"></a>IMetadataSearchHandler インターフェイス  
 `Microsoft.ServiceModel.Channels.Common.IMetadataSearchHandler`として定義されます。  
  
```  
public interface IMetadataSearchHandler : IConnectionHandler, IDisposable  
{  
    MetadataRetrievalNode[] Search(string nodeId, string searchCriteria, int maxChildNodes, TimeSpan timeout);  
}  
```  
  
 `Microsoft.ServiceModel.Channels.Common.IMetadataSearchHandler.Search%2A`メソッドの配列を返します`Microsoft.ServiceModel.Channels.MetadataRetrievalNode`検索条件に基づいてオブジェクト。 Search メソッドのパラメーターの定義は、次の表で説明します。  
  
|**パラメーター**|**定義**|  
|-------------------|--------------------|  
|nodeId|検索を開始するノード ID。 場合は null または空の文字列 ("")、操作は、ルート ノード (「/」) から取得されます。|  
|searchCriteria|検索条件は、アダプターに固有です。 検索条件が指定されていない場合、アダプターは、すべてのノードを返す必要があります。|  
|maxChildNodes|返される結果のノードの最大数。 Int32.Max を使用すると、結果のすべてのノードを取得できます。<br /><br /> エコー アダプターによってサポートされていません。|  
|timeout|操作が完了するに使用できる最大時間。<br /><br /> エコー アダプターによってサポートされていません。|  
  
 検索の結果をカテゴリのノードまたはノードの操作、またはその両方を返す、アダプターを選択できます。 アダプターが最大検索機能の種類をサポートしています。  
  
## <a name="echo-adapter-metadata-search"></a>エコー アダプター メタデータの検索  
 によって、ターゲット システムのカテゴリと操作の配列を構築する方法はたくさんあります`Microsoft.ServiceModel.Channels.MetadataRetrievalNode`オブジェクトを返します。 エコー アダプターは、検索機能を実装する方法は、次の一覧にそのノード ID を持つすべての操作を経由する場合します。  
  
```  
Echo/OnReceiveEcho, inbound operation  
Echo/EchoStrings, outbound operation  
Echo/EchoGreetings, outbound operation  
Echo/EchoGreetingFromFile, outbound operation  
```  
  
- ノード ID には、検索条件が一致すると、作成、`Microsoft.ServiceModel.Channels.MetadataRetrievalNode`オブジェクト、操作のノード ID を使用し、値を持つプロパティを割り当てます。 例を次に示します。  
  
  ```  
  MetadataRetrievalNode nodeInbound = new MetadataRetrievalNode("Echo/OnReceiveEcho"); //create the MetadataRetrievalNode using the operation's node ID.  
  nodeInbound.DisplayName = "OnReceiveEcho"; //The Display Name shown in the Name column of the Add Adapter Service Reference Visual Studio Plug-in  
  nodeInbound.Description = "This operation echoes the location and length of a file dropped in the specified file system.";  //The Description shown as the tool tip in the Add Adapter Service Visual Studio Plug-in  
  nodeInbound.Direction = MetadataRetrievalNodeDirections.Inbound;    //It is an inbound operation  
  nodeInbound.IsOperation = true;  //It is an operation, not category.  
  ```  
  
- コレクションにオブジェクトを追加し、 `Microsoft.ServiceModel.Channels.MetadataRetrievalNode`s、たとえば、  
  
  ```  
  resultList.Add(nodeInbound);  
  ```  
  
- 最後に配列形式のコレクションを返します。  
  
  ```  
  return resultList.ToArray();  
  ```  
  
  使用することができます、[!INCLUDE[addadapterservrefshort](../../includes/addadapterservrefshort-md.md)]と[!INCLUDE[consumeadapterservshort](../../includes/consumeadapterservshort-md.md)]接続ベースの検索を使用可能な操作を実行するためのツール。 たとえば、次の図を示します文字列の検索条件の場合**Greeting**、検索、 **EchoGreetings**と**EchoGreetingFromFile**操作です。  
  
  ![](../../adapters-and-accelerators/wcf-lob-adapter-sdk/media/874c046a-590f-4047-9b9c-bb8074664755.gif "874c046a-590f-4047-9b9c-bb8074664755")  
  
  一致が検出されない場合、いずれかのツールは次の図に示すように、エラー メッセージを返します。  
  
  ![](../../adapters-and-accelerators/wcf-lob-adapter-sdk/media/cb1f79a2-a63d-4828-9dce-905c026cd1dc.gif "cb1f79a2-a63d-4828-9dce-905c026cd1dc")  
  
## <a name="implementing-the-imetadatasearchhandler"></a>IMetadataSearchHandler を実装します。  
 実装、`Microsoft.ServiceModel.Channels.Common.IMetadataSearchHandler.Search%2A`のメソッド、`Microsoft.ServiceModel.Channels.Common.IMetadataSearchHandler`インターフェイス。 操作の表示名が検索条件に一致する場合は作成、 `Microsoft.ServiceModel.Channels.MetadataRetrievalNode` 、その操作のオブジェクトし、の配列にそのオブジェクトを追加、`Microsoft.ServiceModel.Channels.MetadataRetrievalNode`オブジェクト。  
  
#### <a name="to-update-the-echoadaptermetadatasearchhandler-class"></a>EchoAdapterMetadataSearchHandler クラスを更新するには  
  
1.  ソリューション エクスプ ローラーで、 **EchoAdapterMetadataSearchHandler.cs**ファイル。  
  
2.  Visual Studio エディターでの内部、**検索**メソッドを次に、既存のロジックを置き換えます。 このロジックを作成、`Microsoft.ServiceModel.Channels.MetadataRetrievalNode`エコー/OnReceiveEcho が指定した検索条件と一致するかどうかのオブジェクトします。  
  
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
  
3.  作成するには、次のロジックの追加を続行する`Microsoft.ServiceModel.Channels.MetadataRetrievalNode`エコー/EchoStrings が指定した検索条件と一致するかどうかのオブジェクトします。  
  
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
  
4.  作成するには、次のロジックの追加を続行する`Microsoft.ServiceModel.Channels.MetadataRetrievalNode`エコー/EchoGreetings が指定した検索条件と一致するかどうかのオブジェクトします。  
  
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
  
5.  作成する次のコードの追加を続行する`Microsoft.ServiceModel.Channels.MetadataRetrievalNode`エコー/EchoGreetingFromFile が指定した検索条件と一致するかどうかのオブジェクトします。  
  
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
  
6.  配列を返すには、次のコードの追加を続行`Microsoft.ServiceModel.Channels.MetadataRetrievalNode`オブジェクト。  
  
    ```csharp  
    return resultList.ToArray();  
    ```  
  
7.  Visual Studio での**ファイル** メニューのをクリックして**すべて保存**します。  
  
8.  **[ビルド]** メニューの **[ソリューションのビルド]** をクリックします。 プロジェクトを正常にコンパイルする必要があります。 そうでない場合は、上記のすべての手順に従っていることを確認します。  
  
    > [!NOTE]
    >  これで作業が保存されました。 安全にこの時点で Visual Studio を閉じて、次の手順に進むまたは[手順 6。エコー アダプターのメタデータ解決ハンドラーを実装する](../../adapters-and-accelerators/wcf-lob-adapter-sdk/step-6-implement-the-metadata-resolve-handler-for-the-echo-adapter.md)します。  
  
## <a name="what-did-i-just-do"></a>でしただけ何か。  
 だけ、エコー アダプターの機能を実装することで検索するメタデータが実装されている、`Microsoft.ServiceModel.Channels.Common.IMetadataSearchHandler.Search%2A`のメソッド、`Microsoft.ServiceModel.Channels.Common.IMetadataSearchHandler`インターフェイス。 具体的には、作成した、`Microsoft.ServiceModel.Channels.MetadataRetrievalNode`オブジェクトのすべての操作を条件に一致しての配列が返されます、`Microsoft.ServiceModel.Channels.MetadataRetrievalNode`オブジェクト。  
  
## <a name="next-steps"></a>次の手順  
 機能、および送信および受信のメッセージ交換機能を解決するメタデータを実装します。 最後に、ビルドされ、エコー アダプターを展開します。  
  
## <a name="see-also"></a>参照  
 [手順 4:エコー アダプターのメタデータ参照ハンドラーを実装します。](../../adapters-and-accelerators/wcf-lob-adapter-sdk/step-4-implement-the-metadata-browse-handler-for-the-echo-adapter.md)   
 [手順 6:エコー アダプターのメタデータ解決ハンドラーを実装します。](../../adapters-and-accelerators/wcf-lob-adapter-sdk/step-6-implement-the-metadata-resolve-handler-for-the-echo-adapter.md)   
 [チュートリアル 1:エコー アダプターを開発する](../../adapters-and-accelerators/wcf-lob-adapter-sdk/tutorial-1-develop-the-echo-adapter.md)