---
title: '手順 4: エコー アダプターのメタデータ参照のハンドラーを実装する |Microsoft ドキュメント'
ms.custom: ''
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: ''
ms.suite: ''
ms.tgt_pltfrm: ''
ms.topic: article
ms.assetid: d31fc6c1-e4b5-4529-ba3e-2a8cfb8ece1c
caps.latest.revision: 19
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: f93b4efeb65092c4ca61ab1fc2ef58a0ac53ae4a
ms.sourcegitcommit: cb908c540d8f1a692d01dc8f313e16cb4b4e696d
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 09/20/2017
ms.locfileid: "22226986"
---
# <a name="step-4-implement-the-metadata-browse-handler-for-the-echo-adapter"></a>手順 4: エコー アダプターのメタデータ参照のハンドラーを実装します。
![手順 4. 9 の](../../adapters-and-accelerators/wcf-lob-adapter-sdk/media/step-4of9.gif "Step_4of9")  
  
 **所要時間:** 45 分  
  
 このステップでは、エコー アダプターの [参照] 機能を実装します。 この機能では、アダプター メタデータを取得する対象システムからの接続に基づく参照を実行します。 アダプターの機能に関係なく、アダプターは、[参照] 機能をサポートする必要があります。  
  
 よると、 [!INCLUDE[afproductnameshort](../../includes/afproductnameshort-md.md)]、参照機能をサポートするために実装する必要があります、`Microsoft.ServiceModel.Channels.Common.IMetadataBrowseHandler`インターフェイスです。 エコー アダプターの場合、 [!INCLUDE[afdevwizardnameshort](../../includes/afdevwizardnameshort-md.md)] EchoAdapterMetadataBrowseHandler と呼ばれる、派生クラスが自動的に生成されます。  
  
 次の手順で実装する方法の理解を深めるために、このクラスを更新する、`Microsoft.ServiceModel.Channels.Common.IMetadataBrowseHandler.Browse%2A`メソッドのさまざまなプロパティを設定する方法、`Microsoft.ServiceModel.Channels.MetadataRetrievalNode`オブジェクト、および操作と、アダプターでサポートされているカテゴリのノードが、でどのように表示する方法[!INCLUDE[addadapterservrefshort](../../includes/addadapterservrefshort-md.md)]ツールです。  
  
## <a name="prerequisites"></a>前提条件  
 この手順を開始する前にする必要がありますが正常に完了しました[手順 3: エコー アダプターの接続を実装](../../adapters-and-accelerators/wcf-lob-adapter-sdk/step-3-implement-the-connection-for-the-echo-adapter.md)です。 次のクラスを理解する必要があります。  
  
-   `Microsoft.ServiceModel.Channels.MetadataRetrievalNode`  
  
-   `Microsoft.ServiceModel.Channels.MetadataRetrievalNodeDirections`  
  
-   `Microsoft.ServiceModel.Channels.Common.IMetadataBrowseHandler`  
  
## <a name="the-imetadatabrowsehandler-interface"></a>IMetadataBrowseHandler インターフェイス  
 `Microsoft.ServiceModel.Channels.Common.IMetadataBrowseHandler`としてインターフェイスを定義します。  
  
```  
public interface IMetadataBrowseHandler : IConnectionHandler, IDisposable  
{  
    MetadataRetrievalNode[] Browse(string nodeId, int childStartIndex, int maxChildNodes, TimeSpan timeout);  
}  
```  
  
 `Microsoft.ServiceModel.Channels.Common.IMetadataBrowseHandler.Browse%2A`メソッドの配列を返します`Microsoft.ServiceModel.Channels.MetadataRetrievalNode`オブジェクト メソッドのパラメーターをベースにします。 パラメーターの定義、`Microsoft.ServiceModel.Channels.Common.IMetadataBrowseHandler.Browse%2A`メソッドは次の表で説明します。  
  
> [!NOTE]
>  エコー アダプターの実装では、ノードの ID のみを使用し、エコー アダプターは、少数のノードをサポートするために、他の 3 つのパラメーターを無視します。  
  
|**パラメーター**|**定義**|  
|-------------------|--------------------|  
|NodeId|メタデータ エクスプ ローラーの階層の各項目 (、[!INCLUDE[addadapterservrefshort](../../includes/addadapterservrefshort-md.md)]と<br /><br /> [!INCLUDE[consumeadapterservshort](../../includes/consumeadapterservshort-md.md)])、nodeId がします。 各ノードの ID は一意である必要があり、カテゴリ、または操作することができます。 カテゴリは、サブカテゴリを持つことができます。 **注:** 場合は null または空の文字列 ("")、ルート ノードから (「/」) で既定の操作が取得されます。|  
|childStartIndex|返される最初の子のインデックス。<br /><br /> エコー アダプターによってサポートされていません。|  
|maxChildNodes|返される結果のノードの最大数。 Int32.Max を使用して、結果のすべてのノードを取得します。<br /><br /> エコー アダプターによってサポートされていません。|  
|timeout|操作が完了する許可された最大時間。<br /><br /> エコー アダプターによってサポートされていません。|  
  
 実装する場合、`Microsoft.ServiceModel.Channels.Common.IMetadataBrowseHandler.Browse%2A`メソッドの配列にカテゴリと操作の各ノードを追加する必要があります`Microsoft.ServiceModel.Channels.MetadataRetrievalNode`オブジェクト。 カテゴリとしてノードを指定するには、設定、`Microsoft.ServiceModel.Channels.MetadataRetrievalNode.IsOperation%2A`に`false`です。 操作として、ノードを指定するには、設定、`Microsoft.ServiceModel.Channels.MetadataRetrievalNode.IsOperation%2A`に`true`です。  
  
## <a name="echo-adapter-metadata-browse"></a>エコー アダプター メタデータの参照  
 によっては、ターゲット システムのカテゴリと操作の配列を作成する方法はたくさんあります`Microsoft.ServiceModel.Channels.MetadataRetrievalNode`オブジェクト。 操作とカテゴリを選択するには、公開する操作を表す必要があります。 エコー アダプターが単に作成されますが、`Microsoft.ServiceModel.Channels.MetadataRetrievalNode`ノード ID で、次のノードの各オブジェクトが一覧表示。  
  
```  
EchoMainCategory  (node under the root node)  
        Echo/EchoStrings   (outbound operation)  
        Echo/EchoGreetings(outbound operation)  
        Echo/EchoCustomGreetingFromFile(outbound operation)  
        Echo/OnReceiveEcho (inbound operation)  
```  
  
 EchoMainCategory は、カテゴリ ノード (「/」) のルート ノードの下です。 このノードは、受信および送信の両方の操作のためのカテゴリとしても使用されます。 そのため、作成するときに、`Microsoft.ServiceModel.Channels.MetadataRetrievalNode`そのカテゴリのオブジェクトの次を行うことができます。  
  
```  
MetadataRetrievalNode node = new MetadataRetrievalNode("EchoMainCategory");  
node.IsOperation = false; //category  
node.Direction = MetadataRetrievalNodeDirections.Inbound | MetadataRetrievalNodeDirections.Outbound  //for both inbound and outbound  
```  
  
 エコー/EchoString、EchoMainCategory に属しているなどの送信操作では、次の操作を行うことができます。  
  
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
  
 エコー/OnReceiveEcho、EchoMainCategory に属しているなどの受信操作では、次の操作を行うことができます。  
  
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
  
 ときに、[!INCLUDE[addadapterservrefshort](../../includes/addadapterservrefshort-md.md)]と[!INCLUDE[consumeadapterservshort](../../includes/consumeadapterservshort-md.md)]ツールが既定では、エコー アダプター メタデータを調査、ルート ノード (「/」) から開始します。  
  
 次の図は、(「/」) のルート ノードの下に EchoMainCategory ノードが表示されることを示しています。  
  
 ![](../../adapters-and-accelerators/wcf-lob-adapter-sdk/media/e4b9d0b8-f07f-4342-815f-9ef1507b0980.gif "e4b9d0b8-f07f-4342-815f-9ef1507b0980")  
  
 次の 3 つの送信操作を参照するときに、[!INCLUDE[addadapterservrefshort](../../includes/addadapterservrefshort-md.md)]ツールを**選択コントラクト型**ドロップダウン リスト、選択、**クライアント (送信操作)** オプション。 これらの操作を参照してください、**利用可能なカテゴリと操作**リスト ボックスで、次のようにします。  
  
 ![](../../adapters-and-accelerators/wcf-lob-adapter-sdk/media/c8755805-cbb0-40f1-887a-a3123f71ae7e.gif "c8755805-cbb0-40f1-887a-a3123f71ae7e")  
  
 前の図では、`Microsoft.ServiceModel.Channels.MetadataRetrievalNode.DisplayName%2A`値に表示されます、**名前**の列、**利用可能なカテゴリと操作**ボックスの一覧です。 渡されたパラメーター、`Microsoft.ServiceModel.Channels.MetadataRetrievalNode`にコンス トラクターが、**ノード ID**の列、**利用可能なカテゴリと操作**リスト ボックスで、および`Microsoft.ServiceModel.Channels.MetadataRetrievalNode.Description%2A`値、ツールヒントとして表示されます右クリックすると、説明を含む、`Microsoft.ServiceModel.Channels.MetadataRetrievalNode.DisplayName%2A`です。  
  
 入力方向の操作を表示する、[!INCLUDE[addadapterservrefshort](../../includes/addadapterservrefshort-md.md)]ツールを**選択コントラクト型**ドロップダウン リスト、選択、**サービス (入力方向の操作)** オプション。 受信 OnReceiveEcho 操作を参照してください、**利用可能なカテゴリと操作**リスト ボックスで、次の図に示すようにします。  
  
 ![](../../adapters-and-accelerators/wcf-lob-adapter-sdk/media/26b7b3c7-bc39-46f8-bc73-7d76fd3c02eb.gif "26b7b3c7-bc39-46f8-bc73-7d76fd3c02eb")  
  
## <a name="implementing-the-imetadatabrowsehandler"></a>IMetadataBrowseHandler を実装します。  
 実装するは、エコー アダプターのメタデータの参照を実装する EchoAdapterMetadataBrowseHandler クラスを更新するこの手順で、`Microsoft.ServiceModel.Channels.Common.IMetadataBrowseHandler.Browse%2A`のメソッド、`Microsoft.ServiceModel.Channels.Common.IMetadataBrowseHandler`インターフェイスです。 具体的を作成する、`Microsoft.ServiceModel.Channels.MetadataRetrievalNode`オブジェクトの各カテゴリと操作、そのオブジェクトの適切な値を設定およびの配列を返す`Microsoft.ServiceModel.Channels.MetadataRetrievalNode`カテゴリおよび操作のためのオブジェクト。 ただし、作成するときに、`Microsoft.ServiceModel.Channels.MetadataRetrievalNode`オブジェクトの表示名ではなく、ノード ID を渡す必要があります。  
  
#### <a name="to-update-the-echoadaptermetadatabrowsehandler-class"></a>EchoAdapterMetadataBrowseHandler クラスの更新  
  
1.  ソリューション エクスプ ローラーで、 **EchoAdapterMetadataBrowseHandler.cs**ファイル。  
  
2.  Visual Studio エディターで、任意の場所を右クリック コンテキスト メニューで、エディター内のをポイント**アウトライン**、クリックして**アウトラインの中止**です。  
  
3.  Visual Studio エディターで、内部、**参照**メソッドを置き換える既存のロジックを作成するには、次、 `Microsoft.ServiceModel.Channels.MetadataRetrievalNode` EchoMainCategory のオブジェクト。  
  
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
  
4.  作成する次のロジックの追加を繰り返して、`Microsoft.ServiceModel.Channels.MetadataRetrievalNode`エコー/OnReceiveEcho のオブジェクト。  
  
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
  
5.  作成する次のロジックの追加を繰り返して、`Microsoft.ServiceModel.Channels.MetadataRetrievalNode`エコー/EchoStrings のオブジェクト。  
  
    ```csharp  
    // Outbound operations  
    MetadataRetrievalNode outOpNode1 = new MetadataRetrievalNode("Echo/EchoStrings");  
    outOpNode1.DisplayName = "EchoStrings";  
    outOpNode1.Description = "This operation echoes the incoming string COUNT number of times in a string array.";  
    outOpNode1.Direction = MetadataRetrievalNodeDirections.Outbound;  
    outOpNode1.IsOperation = true;  
    ```  
  
6.  作成する次のコードの追加を繰り返して、`Microsoft.ServiceModel.Channels.MetadataRetrievalNode`エコー/EchoGreetings のオブジェクト。  
  
    ```csharp  
    MetadataRetrievalNode outOpNode2 = new MetadataRetrievalNode("Echo/EchoGreetings");  
    outOpNode2.DisplayName = "EchoGreetings";  
    outOpNode2.Description = "This operation echoes the incoming Greeting object COUNT number of times in an array of type Greeting.";  
    outOpNode2.Direction = MetadataRetrievalNodeDirections.Outbound;  
    outOpNode2.IsOperation = true;  
    ```  
  
7.  作成する次のコードの追加を繰り返して、`Microsoft.ServiceModel.Channels.MetadataRetrievalNode`エコーのオブジェクト/EchoGreetingFromFile です。  
  
    ```csharp  
    MetadataRetrievalNode outOpNode3 = new MetadataRetrievalNode("Echo/EchoCustomGreetingFromFile");  
    outOpNode3.DisplayName = "EchoCustomGreetingFromFile";  
    outOpNode3.Description = "This operation echoes the greeting object by reading its instance from a file. The Greeting object's metadata is obtained from a predefined XSD file.";  
    outOpNode3.Direction = MetadataRetrievalNodeDirections.Outbound;  
    outOpNode3.IsOperation = true;  
    ```  
  
8.  配列を返すには、次のコードの追加を繰り返して`Microsoft.ServiceModel.Channels.MetadataRetrievalNode`オブジェクトまたは一致しない場合は null です。  
  
    ```  
        return new MetadataRetrievalNode[] { inOpNode1, outOpNode1, outOpNode2, outOpNode3 };  
    }  
    return null;  
    ```  
  
9. Visual Studio での**ファイル** メニューのをクリックして**すべて保存**です。  
  
10. **[ビルド]** メニューの **[ソリューションのビルド]** をクリックします。 プロジェクトを正常にビルドする必要があります。 以外の場合は、上記のすべてのステップに従っていることを確認します。  
  
> [!NOTE]
>  これで作業が保存されました。 安全にこの時点で Visual Studio を終了したり、次の手順に進みます[手順 5: エコー アダプターのメタデータの検索ハンドラーの実装](../../adapters-and-accelerators/wcf-lob-adapter-sdk/step-5-implement-the-metadata-search-handler-for-the-echo-adapter.md)です。  
  
## <a name="what-did-i-just-do"></a>でしただけは何ですか。  
 だけに閲覧エコー アダプターの機能を実装することで、メタデータを実装して、`Microsoft.ServiceModel.Channels.Common.IMetadataBrowseHandler.Browse%2A`のメソッド、`Microsoft.ServiceModel.Channels.Common.IMetadataBrowseHandler`インターフェイスです。 具体的には、作成した、`Microsoft.ServiceModel.Channels.MetadataRetrievalNode`カテゴリに属しているオブジェクトを配列として返されます、`Microsoft.ServiceModel.Channels.MetadataRetrievalNode`オブジェクト。 作成した各操作に対して、`Microsoft.ServiceModel.Channels.MetadataRetrievalNode`オブジェクト、し、それらすべてのオブジェクトの配列の`Microsoft.ServiceModel.Channels.MetadataRetrievalNode`します。  
  
## <a name="next-steps"></a>次の手順  
 メタデータの検索し解決機能、および送信メッセージの交換を実装するとします。 最後に、ビルドおよび展開するエコー アダプター。  
  
## <a name="see-also"></a>参照  
 [チュートリアル 1: エコー アダプターを開発します。](../../adapters-and-accelerators/wcf-lob-adapter-sdk/tutorial-1-develop-the-echo-adapter.md)   
 [手順 3: エコー アダプターの接続を実装します。](../../adapters-and-accelerators/wcf-lob-adapter-sdk/step-3-implement-the-connection-for-the-echo-adapter.md)   
 [手順 5: エコー アダプターのメタデータの検索ハンドラーを実装します。](../../adapters-and-accelerators/wcf-lob-adapter-sdk/step-5-implement-the-metadata-search-handler-for-the-echo-adapter.md)