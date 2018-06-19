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
# <a name="get-metadata-in-sap-using-imetadataretrievalcontract"></a>IMetadataRetrievalContract を使用して SAP のメタデータを取得します。
[!INCLUDE[adaptersap](../../includes/adaptersap-md.md)]公開、 **IMetadataRetrievalContract**は Web サービス記述言語 (WSDL) ドキュメントの形式でメタデータを取得して SAP システムのアイテムを検索および参照を使用できるエンドポイント操作です。  
  
 **IMetadataRetrievalContract**インターフェイスは、[!INCLUDE[afproductnamelong](../../includes/afproductnamelong-md.md)]とメタデータの参照、検索、および検索の機能を提供します。 加え、 **IMetadataRetrievalContract** 、インターフェイス、[!INCLUDE[afproductnameshort](../../includes/afproductnameshort-md.md)]公開、 **MetadataRetrievalClient**インターフェイスを実装するクラス。 使用するか、 **IMetadataRetrievalContract**チャネルまたは**MetadataRetrievalClient**を使用するメタデータ; 参照、検索、およびメタデータを取得する公開されたメソッドは各ケースで同じです。  
  
 次のセクションでは、使用する方法に関する情報を提供する、 **IMetadataRetrievalContract**インターフェイスです。  
  
## <a name="the-imetadataretrievalcontract-interface"></a>IMetadataRetrievalContract インターフェイス  
 次の表を使用するときに使用される重要なクラスに関する情報を提供する、 **IMetadataRetrievalContract**インターフェイスです。  
  
|クラスまたはインターフェイス|Description|  
|------------------------|-----------------|  
|**IMetadataRetrievalContract**インターフェイス<br /><br /> (Microsoft.ServiceModel.Channels)|定義、**参照**、**検索**、および**GetMetadata**メソッドです。 いずれかを使用してこれらのメソッドを呼び出す、 **IMetadataRetrievalContract**チャネルまたは**MetadataRetrievalClient**アダプター メタデータを使用します。|  
|**MetadataRetrievalClient**クラス<br /><br /> (Microsoft.ServiceModel.Channels)|実装して、 **IMetadataRetrievalContract**インターフェイスです。 このクラスのインスタンスを作成し、提供することで、SAP システムのように構成することができます、 **SAPBinding**と**EndpointAddress**です。 メタデータを使用するには、そのメソッドを呼び出すことができます。|  
|**MetadataRetrievalNode**クラス<br /><br /> (Microsoft.ServiceModel.Channels)|アダプター メタデータのノードを表します。 **参照**と**検索**メソッドには、この種類のノードが返されます、 **GetMetadata**メソッドには、パラメーターとしてこの型のノードです。|  
|**ServiceDescription**クラス<br /><br /> (System.Web.Services.Description)|作成および有効な WSDL ドキュメント ファイルの書式設定する手段を提供します。 **GetMetadata**メソッドを返します、 **ServiceDescription**オブジェクト。|  
  
 詳細については、 **IMetadataRetrievalContract** 、インターフェイス、 **MetadataRetrievalClient**クラス、および**MetadataRetrievalNode**クラスは、を参照してください**Microsoft.ServiceModel.Channels**での参照をマネージ[http://go.microsoft.com/fwlink/?LinkId=105566](http://go.microsoft.com/fwlink/?LinkId=105566)です。  
  
### <a name="metadata-node-ids"></a>メタデータのノード Id  
 アダプターは、ノードの階層ツリーとしてそのメタデータを整理します。 このツリー構造内では、メタデータのノードの 2 つの種類があります。  
  
-   **操作のノード**SAP アイテムで、アダプターを表示する操作を表します。 操作のノードは、ツリーのリーフです。  
  
-   **カテゴリ ノード**アダプターでの操作に SAP アイテムと直接対応しない SAP アイテムのグループを表します。 カテゴリのノードがツリーの分岐その他のカテゴリ ノードおよび操作のノードが含まれます。 たとえば、RFC 機能グループまたは SAP ビジネス オブジェクトは、カテゴリのノードとして表されます。  
  
 アダプター メタデータの各ノードが一意のノード ID で識別されます。 メタデータのノード、アダプターによって公開される Id の詳細については、次を参照してください。[メタデータのノード Id](../../adapters-and-accelerators/adapter-sap/metadata-node-ids4.md)です。 これらのノード Id を使用して使用すると、ターゲット SAP アイテムを指定する、 **IMetadataRetrievalContract**インターフェイスを参照、検索、およびメタデータを取得します。 定義されている定数を使用することができます`Microsoft.Adapters.SAP.SAPAdapterConstants.MetadataConstants`と`Microsoft.Adapters.SAP.SAPAdapterConstants.ActionConstants`メタデータ ノード Id を構築するためです。  
  
### <a name="binding-properties"></a>バインドのプロパティ  
 使用するかどうか、 **IMetadataRetrievalContract**チャネルまたは**IMetadataRetrievalClient**メタデータを使用する必要がありますを指定する、 **SAPBinding**を作成する場合、インスタンス。  
  
 アダプターがメタデータを生成する方法に影響を与えるいくつかのバインド プロパティがあります。 これらのプロパティは次のとおりです。  
  
-   **GenerateFlatfileCompatibleIdocSchema**  
  
-   **ReceiveIDocFormat**  
  
-   **EnableSafeTyping**  
  
-   **FlatFileSegmentIndicator**  
  
 メタデータの取得オブジェクトを開く前に、アプリケーションに必要な値をこれらのバインディング プロパティを設定することを確認する必要があります。 SAP アダプターのバインドのプロパティの詳細については、次を参照してください。 [mySAP Business Suite バインド プロパティの BizTalk アダプターの説明を読む](../../adapters-and-accelerators/adapter-sap/read-about-biztalk-adapter-for-mysap-business-suite-binding-properties.md)です。  
  
### <a name="browsing-metadata-nodes"></a>メタデータのノードを参照  
 使用する、**参照**を親ノードに含まれているすべてのメタデータのノードを返すメソッド。 次の例は、SAP システムでは、最初の 3 つの RFC 機能グループの参照します。 この例では**クライアント**のインスタンスは、 **MetadataRetrievalClient**です。  
  
```  
// The first parameter is the node ID.   
// The second parameter is the start index.  
// The third parameter is the maximum number of nodes to return.  
IMetadataRetrievalNode[] nodes = client.Browse(Microsoft.Adapters.SAP.SAPAdapterConstants.MetadataConstants.RfcSection, 0, 3);  
```  
  
> [!IMPORTANT]
>  カテゴリのノードを参照することができますのみ操作のノードを参照することはできません。  
  
### <a name="searching-for-metadata-nodes"></a>メタデータのノードの検索  
 使用する、**検索**の親ノードに含まれるノードの検索を実行するメソッド。 アスタリスクを指定することができます (\*) ワイルドカード文字です。 この文字は、0 個以上の文字と一致します。 次の例は、文字列"BAPI"が含まれるすべての Rfc の検索を示しています。 この例では**クライアント**のインスタンスは、 **MetadataRetrievalClient**です。  
  
```  
// Search for all nodes that contain "BAPI" under the RFC node.  
// The parameters are the parent node ID, the search expression, and   
// the maximum number of nodes to return.  
IMetadataRetrievalNode[] nodes = client.Search(Microsoft.Adapters.SAP.SAPAdapterConstants.MetadataConstants.RfcSection, "*BAPI*", int.MaxValue);  
```  
  
> [!IMPORTANT]
>  検索は、限られた一連のノードでのみサポートされます。 検索式でサポートされているワイルドカード文字および検索がサポートされているノードに関する詳細については、次を参照してください。[メタデータのノード Id](../../adapters-and-accelerators/adapter-sap/metadata-node-ids4.md)です。  
  
### <a name="retrieving-metadata-wsdl-for-operations"></a>操作のメタデータ (WSDL) を取得します。  
 使用する、 **GetMetadata**操作のノードのグループに対するサービスの説明 (WSDL ドキュメント) を取得します。 次の例では、BAPI_TRANSACTION_COMMIT RFC のサービスの説明を取得します。 この例では**クライアント**のインスタンスは、 **MetadataRetrievalClient**です。 操作ノードのノードの ID がその操作の操作のメッセージと同じことに注意してください。  
  
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
>  内の操作のノードを指定する必要がありますのみ、 **GetMetadata**メソッドです。  
  
### <a name="using-a-metadataretrievalclient"></a>使用して、MetadataRetrievalClient  
 作成と使用、 **MetadataRetrievalClient**他の WCF クライアントは、ほぼ同じです。 エンドポイントとのインスタンスを指定して、クライアントを作成する**SAPBinding**です。 構成で宣言またはコードで強制的に、これを行うことができます。 次のメソッドを呼び出し、 **MetadataRetrievalClient**を参照するには、検索、およびアダプターからメタデータを取得します。  
  
 次の例を使用する方法を示しています、 **MetadataRetrievalClient**を参照するには、検索、およびメタデータを取得、[!INCLUDE[adaptersap_short](../../includes/adaptersap-short-md.md)]です。  
  
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
  
 次のコンソールでこのプログラムの出力は、次に示します。 それぞれのメソッドに返されるメタデータの取得のノードの構造を確認できます。 プログラムは、また、ファイルを検索によって返されるノードで構成されるサービス コントラクトを説明する WSDL ドキュメントを書き込みます。 (ほとんどの SAP インストールでは、サービスの説明が含まれません、BAPI_TRANSACTION_COMMIT および BAPI_TRANSACTION_ROLLBACK 操作します。)  
  
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
  
## <a name="using-an-imetadataretrievalcontract-channel"></a>IMetadataRetrievalContract チャネルを使用します。  
 作成することも、 **IMetadataRetrievalContract**チャネルし、このチャネルを使用して、参照、検索、およびアダプターからメタデータを取得します。 (メソッドのシグネチャが同じである、 **MetadataRetrievalClient**クラスです)。その方法を次の例に示します。  
  
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
  
## <a name="see-also"></a>参照  
 [SAP からメタデータをプログラムで取得します。](../../adapters-and-accelerators/adapter-sap/get-metadata-programmatically-from-sap.md)