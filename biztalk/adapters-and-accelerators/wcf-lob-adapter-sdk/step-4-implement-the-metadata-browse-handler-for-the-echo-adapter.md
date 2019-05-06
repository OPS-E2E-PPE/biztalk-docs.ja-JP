---
title: '手順 4: エコー アダプターのメタデータ参照ハンドラーを実装する |Microsoft Docs'
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
ms.openlocfilehash: c50110fff32b81bdaa429a479cefe8041d919356
ms.sourcegitcommit: 266308ec5c6a9d8d80ff298ee6051b4843c5d626
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 06/27/2018
ms.locfileid: "37003419"
---
# <a name="step-4-implement-the-metadata-browse-handler-for-the-echo-adapter"></a>手順 4: エコー アダプターのメタデータ参照ハンドラーを実装する.
![手順 9 の 4](../../adapters-and-accelerators/wcf-lob-adapter-sdk/media/step-4of9.gif "Step_4of9")  
  
 **所要時間:** 45 分  
  
 この手順では、エコー アダプターの [参照] 機能を実装します。 この機能により、ターゲット システムからメタデータを取得する接続ベースの参照を実行するアダプター。 アダプターの機能に関係なく、アダプターは、[参照] 機能をサポートする必要があります。  
  
 に従って、 [!INCLUDE[afproductnameshort](../../includes/afproductnameshort-md.md)]、参照機能をサポートするために実装する必要があります、`Microsoft.ServiceModel.Channels.Common.IMetadataBrowseHandler`インターフェイス。 エコー アダプターの場合、 [!INCLUDE[afdevwizardnameshort](../../includes/afdevwizardnameshort-md.md)] EchoAdapterMetadataBrowseHandler という派生クラスが自動的に生成されます。  
  
 次の手順で実装する方法の理解を深めるために、このクラスを更新する、`Microsoft.ServiceModel.Channels.Common.IMetadataBrowseHandler.Browse%2A`メソッドのさまざまなプロパティを設定する方法、`Microsoft.ServiceModel.Channels.MetadataRetrievalNode`オブジェクト、および操作と、アダプターでサポートされているカテゴリのノードが、でどのように表示する方法[!INCLUDE[addadapterservrefshort](../../includes/addadapterservrefshort-md.md)]ツール。  
  
## <a name="prerequisites"></a>前提条件  
 この手順を開始する前にする必要がありますが正常に完了して[手順 3: エコー アダプターの接続を実装](../../adapters-and-accelerators/wcf-lob-adapter-sdk/step-3-implement-the-connection-for-the-echo-adapter.md)します。 次のクラスを理解することも必要があります。  
  
-   `Microsoft.ServiceModel.Channels.MetadataRetrievalNode`  
  
-   `Microsoft.ServiceModel.Channels.MetadataRetrievalNodeDirections`  
  
-   `Microsoft.ServiceModel.Channels.Common.IMetadataBrowseHandler`  
  
## <a name="the-imetadatabrowsehandler-interface"></a>IMetadataBrowseHandler インターフェイス  
 `Microsoft.ServiceModel.Channels.Common.IMetadataBrowseHandler`としてインターフェイスが定義されます。  
  
```  
public interface IMetadataBrowseHandler : IConnectionHandler, IDisposable  
{  
    MetadataRetrievalNode[] Browse(string nodeId, int childStartIndex, int maxChildNodes, TimeSpan timeout);  
}  
```  
  
 `Microsoft.ServiceModel.Channels.Common.IMetadataBrowseHandler.Browse%2A`メソッドの配列を返します`Microsoft.ServiceModel.Channels.MetadataRetrievalNode`オブジェクト メソッドのパラメーターをベースにします。 パラメーターの定義、`Microsoft.ServiceModel.Channels.Common.IMetadataBrowseHandler.Browse%2A`メソッドは次の表で説明します。  
  
> [!NOTE]
>  エコー アダプターの実装では、ノード ID のみを使用し、エコー アダプターは、いくつかのノードのみをサポートするために、その他の 3 つのパラメーターを無視します。  
  
|  **パラメーター**  |                                                                                                                                                                                                                               **定義**                                                                                                                                                                                                                                |
|-----------------|-----------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------|
|     nodeId      | メタデータ エクスプ ローラーの階層の各項目 (、[!INCLUDE[addadapterservrefshort](../../includes/addadapterservrefshort-md.md)]と<br /><br /> [!INCLUDE[consumeadapterservshort](../../includes/consumeadapterservshort-md.md)])、nodeId が。 各ノードの ID は一意である必要があり、カテゴリ、または操作することができます。 カテゴリのサブカテゴリを持つことができます。 **注:** 場合は null または空の文字列 ("")、ルート ノードから (「/」) 既定では、操作が取得されます。 |
| childStartIndex |                                                                                                                                                                                           返す最初の子のインデックス。<br /><br /> エコー アダプターによってサポートされていません。                                                                                                                                                                                            |
|  maxChildNodes  |                                                                                                                                                                  返される結果のノードの最大数。 Int32.Max を使用すると、結果のすべてのノードを取得できます。<br /><br /> エコー アダプターによってサポートされていません。                                                                                                                                                                   |
|     timeout     |                                                                                                                                                                                   操作が完了するに使用できる最大時間。<br /><br /> エコー アダプターによってサポートされていません。                                                                                                                                                                                    |
  
 実装する場合、`Microsoft.ServiceModel.Channels.Common.IMetadataBrowseHandler.Browse%2A`メソッドの配列にカテゴリと操作のすべてのノードを追加する必要があります`Microsoft.ServiceModel.Channels.MetadataRetrievalNode`オブジェクト。 カテゴリとしてノードを指定するには、設定、`Microsoft.ServiceModel.Channels.MetadataRetrievalNode.IsOperation%2A`に`false`します。 操作として、ノードを指定するには、設定、`Microsoft.ServiceModel.Channels.MetadataRetrievalNode.IsOperation%2A`に`true`します。  
  
## <a name="echo-adapter-metadata-browse"></a>エコー アダプター メタデータの参照  
 によって、ターゲット システムのカテゴリと操作の配列を構築する方法はたくさんあります`Microsoft.ServiceModel.Channels.MetadataRetrievalNode`オブジェクト。 操作とカテゴリを選択するには、公開する操作を表す必要があります。 エコー アダプターが単に作成されますが、`Microsoft.ServiceModel.Channels.MetadataRetrievalNode`ノード ID を持つ次のノードの各オブジェクトが一覧表示。  
  
```  
EchoMainCategory  (node under the root node)  
        Echo/EchoStrings   (outbound operation)  
        Echo/EchoGreetings(outbound operation)  
        Echo/EchoCustomGreetingFromFile(outbound operation)  
        Echo/OnReceiveEcho (inbound operation)  
```  
  
 EchoMainCategory は、(「/」) のルート ノードの下のカテゴリ ノードです。 このノードは、受信と送信の両方の操作のためのカテゴリとしても使用されます。 そのため、作成するときに、`Microsoft.ServiceModel.Channels.MetadataRetrievalNode`オブジェクト、そのカテゴリを次を行うことができます。  
  
```  
MetadataRetrievalNode node = new MetadataRetrievalNode("EchoMainCategory");  
node.IsOperation = false; //category  
node.Direction = MetadataRetrievalNodeDirections.Inbound | MetadataRetrievalNodeDirections.Outbound  //for both inbound and outbound  
```  
  
 など、EchoMainCategory に属している Echo/EchoString 送信操作の場合は、次の操作を行うことができます。  
  
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
  
 ときに、[!INCLUDE[addadapterservrefshort](../../includes/addadapterservrefshort-md.md)]と[!INCLUDE[consumeadapterservshort](../../includes/consumeadapterservshort-md.md)]ツールが既定では、エコー アダプターのメタデータを調べる、ルート ノード (「/」) から開始します。  
  
 次の図は、(「/」) のルート ノードの下に EchoMainCategory ノードが表示されることを示しています。  
  
 ![](../../adapters-and-accelerators/wcf-lob-adapter-sdk/media/e4b9d0b8-f07f-4342-815f-9ef1507b0980.gif "e4b9d0b8-f07f-4342-815f-9ef1507b0980")  
  
 次の 3 つの送信操作を参照する、[!INCLUDE[addadapterservrefshort](../../includes/addadapterservrefshort-md.md)]ツール、**コントラクト型を選択します**ドロップダウン リスト、選択、**クライアント (送信操作)** オプション。 これらの操作を参照してください、**利用可能なカテゴリと操作**リスト ボックスで、次に示すよう。  
  
 ![](../../adapters-and-accelerators/wcf-lob-adapter-sdk/media/c8755805-cbb0-40f1-887a-a3123f71ae7e.gif "c8755805-cbb0-40f1-887a-a3123f71ae7e")  
  
 上の図でわかるように、`Microsoft.ServiceModel.Channels.MetadataRetrievalNode.DisplayName%2A`値に表示されます、**名前**の列、**利用可能なカテゴリと操作**ボックスの一覧。 渡されるパラメーター、`Microsoft.ServiceModel.Channels.MetadataRetrievalNode`にコンストラクターが、**ノード ID**の列、**利用可能なカテゴリと操作**リスト ボックスで、および`Microsoft.ServiceModel.Channels.MetadataRetrievalNode.Description%2A`値、ツールヒントとして表示されます右クリックすると、説明を含む、`Microsoft.ServiceModel.Channels.MetadataRetrievalNode.DisplayName%2A`します。  
  
 受信の操作を参照してください、[!INCLUDE[addadapterservrefshort](../../includes/addadapterservrefshort-md.md)]ツール、**コントラクト型を選択します**ドロップダウン リスト、選択、**サービス (受信操作)** オプション。 受信 OnReceiveEcho 操作を参照してください、**利用可能なカテゴリと操作**リスト ボックスで、次の図に示すようにします。  
  
 ![](../../adapters-and-accelerators/wcf-lob-adapter-sdk/media/26b7b3c7-bc39-46f8-bc73-7d76fd3c02eb.gif "26b7b3c7-bc39-46f8-bc73-7d76fd3c02eb")  
  
## <a name="implementing-the-imetadatabrowsehandler"></a>IMetadataBrowseHandler を実装します。  
 エコー アダプターのメタデータの参照を実装するために、実装するために、EchoAdapterMetadataBrowseHandler クラスを更新するこの手順で、`Microsoft.ServiceModel.Channels.Common.IMetadataBrowseHandler.Browse%2A`のメソッド、`Microsoft.ServiceModel.Channels.Common.IMetadataBrowseHandler`インターフェイス。 具体的には、作成、`Microsoft.ServiceModel.Channels.MetadataRetrievalNode`オブジェクトの各カテゴリと操作をそのオブジェクトの適切な値を設定しての配列を返す`Microsoft.ServiceModel.Channels.MetadataRetrievalNode`カテゴリと操作のオブジェクト。 注意を作成するとき、`Microsoft.ServiceModel.Channels.MetadataRetrievalNode`オブジェクトの表示名ではなく、ノード ID を渡す必要があります。  
  
#### <a name="to-update-the-echoadaptermetadatabrowsehandler-class"></a>EchoAdapterMetadataBrowseHandler クラスを更新するには  
  
1.  ソリューション エクスプ ローラーで、 **EchoAdapterMetadataBrowseHandler.cs**ファイル。  
  
2.  Visual Studio エディターで、任意の場所を右クリック コンテキスト メニューで、エディター内をポイント**アウトライン**、 をクリックし、**アウトラインの中止**します。  
  
3.  Visual Studio エディターで内で、**参照**メソッドを作成するには、次のように、既存のロジックを置き換える、 `Microsoft.ServiceModel.Channels.MetadataRetrievalNode` EchoMainCategory のオブジェクト。  
  
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
  
4.  作成するには、次のロジックの追加を続行する`Microsoft.ServiceModel.Channels.MetadataRetrievalNode`エコー/OnReceiveEcho のオブジェクト。  
  
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
  
5.  作成するには、次のロジックの追加を続行する`Microsoft.ServiceModel.Channels.MetadataRetrievalNode`エコー/EchoStrings のオブジェクト。  
  
    ```csharp  
    // Outbound operations  
    MetadataRetrievalNode outOpNode1 = new MetadataRetrievalNode("Echo/EchoStrings");  
    outOpNode1.DisplayName = "EchoStrings";  
    outOpNode1.Description = "This operation echoes the incoming string COUNT number of times in a string array.";  
    outOpNode1.Direction = MetadataRetrievalNodeDirections.Outbound;  
    outOpNode1.IsOperation = true;  
    ```  
  
6.  作成する次のコードの追加を続行する`Microsoft.ServiceModel.Channels.MetadataRetrievalNode`エコー/EchoGreetings のオブジェクト。  
  
    ```csharp  
    MetadataRetrievalNode outOpNode2 = new MetadataRetrievalNode("Echo/EchoGreetings");  
    outOpNode2.DisplayName = "EchoGreetings";  
    outOpNode2.Description = "This operation echoes the incoming Greeting object COUNT number of times in an array of type Greeting.";  
    outOpNode2.Direction = MetadataRetrievalNodeDirections.Outbound;  
    outOpNode2.IsOperation = true;  
    ```  
  
7.  作成する次のコードの追加を続行する`Microsoft.ServiceModel.Channels.MetadataRetrievalNode`エコーのオブジェクト/EchoGreetingFromFile します。  
  
    ```csharp  
    MetadataRetrievalNode outOpNode3 = new MetadataRetrievalNode("Echo/EchoCustomGreetingFromFile");  
    outOpNode3.DisplayName = "EchoCustomGreetingFromFile";  
    outOpNode3.Description = "This operation echoes the greeting object by reading its instance from a file. The Greeting object's metadata is obtained from a predefined XSD file.";  
    outOpNode3.Direction = MetadataRetrievalNodeDirections.Outbound;  
    outOpNode3.IsOperation = true;  
    ```  
  
8.  配列を返すには、次のコードの追加を続行`Microsoft.ServiceModel.Channels.MetadataRetrievalNode`オブジェクトまたは一致しない場合は null です。  
  
    ```  
        return new MetadataRetrievalNode[] { inOpNode1, outOpNode1, outOpNode2, outOpNode3 };  
    }  
    return null;  
    ```  
  
9. Visual Studio での**ファイル** メニューのをクリックして**すべて保存**します。  
  
10. **[ビルド]** メニューの **[ソリューションのビルド]** をクリックします。 プロジェクトを正常にビルドする必要があります。 そうでない場合は、上記のすべての手順に従っていることを確認します。  
  
> [!NOTE]
>  これで作業が保存されました。 安全にこの時点で Visual Studio を閉じて、次の手順に進むまたは[手順 5: エコー アダプターのメタデータ検索ハンドラーを実装](../../adapters-and-accelerators/wcf-lob-adapter-sdk/step-5-implement-the-metadata-search-handler-for-the-echo-adapter.md)します。  
  
## <a name="what-did-i-just-do"></a>でしただけ何か。  
 だけ、エコー アダプターの機能を実装することによって参照メタデータを実装した、`Microsoft.ServiceModel.Channels.Common.IMetadataBrowseHandler.Browse%2A`のメソッド、`Microsoft.ServiceModel.Channels.Common.IMetadataBrowseHandler`インターフェイス。 具体的には、作成した、`Microsoft.ServiceModel.Channels.MetadataRetrievalNode`カテゴリについて、オブジェクトし、の配列として返されます、`Microsoft.ServiceModel.Channels.MetadataRetrievalNode`オブジェクト。 作成した各操作に対して、`Microsoft.ServiceModel.Channels.MetadataRetrievalNode`オブジェクト、し、それらすべてのオブジェクトの配列の`Microsoft.ServiceModel.Channels.MetadataRetrievalNode`します。  
  
## <a name="next-steps"></a>次の手順  
 メタデータの検索し解決の機能と、送信メッセージ交換を実装します。 最後に、ビルドし、エコー アダプターを展開します。  
  
## <a name="see-also"></a>参照  
 [チュートリアル 1: エコー アダプターを開発します。](../../adapters-and-accelerators/wcf-lob-adapter-sdk/tutorial-1-develop-the-echo-adapter.md)   
 [手順 3: エコー アダプターの接続を実装します。](../../adapters-and-accelerators/wcf-lob-adapter-sdk/step-3-implement-the-connection-for-the-echo-adapter.md)   
 [手順 5: エコー アダプターのメタデータ検索ハンドラーを実装する](../../adapters-and-accelerators/wcf-lob-adapter-sdk/step-5-implement-the-metadata-search-handler-for-the-echo-adapter.md)