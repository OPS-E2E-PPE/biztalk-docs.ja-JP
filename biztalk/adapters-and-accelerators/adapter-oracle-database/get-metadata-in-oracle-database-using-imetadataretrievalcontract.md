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
ms.openlocfilehash: 679a1be842b27431669e60089143c1972aaa0693
ms.sourcegitcommit: 381e83d43796a345488d54b3f7413e11d56ad7be
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 05/07/2019
ms.locfileid: "65376566"
---
# <a name="get-metadata-in-oracle-database-using-imetadataretrievalcontract"></a>IMetadataRetrievalContract を使用して Oracle データベースでメタデータを取得します。
[!INCLUDE[adapteroracle](../../includes/adapteroracle-md.md)]公開、 **IMetadataRetrievalContract**Oracle データベース アイテムを検索および参照して、フォームの Web サービス記述言語 (WSDL での操作のメタデータを取得するを使用するエンドポイント) ドキュメントです。  
  
 **IMetadataRetrievalContract**インターフェイスによって実装されます、[!INCLUDE[afproductnamelong](../../includes/afproductnamelong-md.md)]とメタデータの参照、検索、および検索機能を提供します。 加え、 **IMetadataRetrievalContract** 、インターフェイス、[!INCLUDE[afproductnameshort](../../includes/afproductnameshort-md.md)]公開、 **MetadataRetrievalClient**クラス、インターフェイスを実装します。 いずれかを使用することができます、 **IMetadataRetrievalContract**チャネルまたは**MetadataRetrievalClient**を使用するメタデータ参照、検索、およびメタデータを取得する公開されたメソッドはいずれの場合も同じです。  
  
 次のセクションでは、使用する方法に関する情報を提供する、 **IMetadataRetrievalContract**インターフェイス。  
  
## <a name="the-imetadataretrievalcontract-interface"></a>IMetadataRetrievalContract インターフェイス  
 次の表を使用するときに使用される重要なクラスに関する情報を提供する、 **IMetadataRetrievalContract**インターフェイス。  
  
|クラスまたはインターフェイス|説明|  
|------------------------|-----------------|  
|**IMetadataRetrievalContract**インターフェイス<br /><br /> (Microsoft.ServiceModel.Channels)|定義、**参照**、**検索**、および**GetMetadata**メソッド。 いずれかを使用してこれらのメソッドを呼び出す、 **IMetadataRetrievalContract**チャネルまたは**MetadataRetrievalClient**アダプター メタデータを操作します。|  
|**MetadataRetrievalClient**クラス<br /><br /> (Microsoft.ServiceModel.Channels)|実装、 **IMetadataRetrievalContract**インターフェイス。 このクラスのインスタンスを作成し、提供することで、Oracle データベース用に構成することができます、 **OracleDBBinding**と**EndpointAddress**します。 メタデータを使用するには、そのメソッドを呼び出すことができます。|  
|**MetadataRetrievalNode**クラス<br /><br /> (Microsoft.ServiceModel.Channels)|アダプター メタデータのノードを表します。 **参照**と**検索**メソッドは、この型のノードを返す、 **GetMetadata**メソッドはこの型をパラメーターとしてのノードを受け取ります。|  
|**ServiceDescription**クラス<br /><br /> (System.Web.Services.Description)|作成および有効な WSDL ドキュメントのファイルを書式設定の手段を提供します。 **GetMetadata**メソッドを返します。 を**ServiceDescription**オブジェクト。|  
  
 
### <a name="metadata-node-ids"></a>メタデータ ノード Id  
 アダプターは、ノードの階層ツリーとしてのメタデータを整理します。 このツリー構造内では、メタデータのノードの 2 つの種類があります。  
  
- **操作のノード**Oracle データベース アイテムで、アダプターを表示する操作を表します。 操作のノードでは、ツリーのリーフです。  
  
- **カテゴリ ノード**アダプターでの操作に Oracle データベース アイテムと直接対応している Oracle データベース アイテムのグループを表します。 カテゴリのノードは、ツリーの分岐その他のカテゴリ ノードやノードの操作が含まれます。 たとえば、Oracle のテーブルおよびパッケージは、カテゴリのノードとして表されます。  
  
  アダプター メタデータの各ノードは、一意のノード ID によって識別されます。 メタデータ ノード Id のアダプターの詳細については、次を参照してください。[メタデータ ノード Id](../../adapters-and-accelerators/adapter-oracle-database/metadata-node-ids3.md)します。 これらのノード Id を使用して、使用するときに、Oracle データベース アイテムのターゲットを指定する、 **IMetadataRetrievalContract**参照、検索、およびメタデータを取得するインターフェイス。  
  
### <a name="binding-properties"></a>バインドのプロパティ  
 使用するかどうか、 **IMetadataRetrievalContract**チャネルまたは**IMetadataRetrievalClient**メタデータを使用することを指定する必要があります、 **OracleDBBinding**ときにします。インスタンスを作成します。  
  
 アダプターがメタデータを生成する方法に影響を与えるいくつかのバインド プロパティがあります。 これらのプロパティは次のとおりです。  
  
-   **EnableSafeTyping**  
  
-   **UseSchemaInNamespace**  
  
-   **PollingStatement**  
  
> [!IMPORTANT]
>  設定する必要があります、POLLINGSTMT 操作のメタデータを取得する場合、 **PollingStatement**プロパティをバインドします。  
  
 これらのバインドのプロパティがメタデータの取得オブジェクトを開く前に、アプリケーションに必要な値に設定されているを確認してください。 詳細については、[!INCLUDE[adapteroracle_short](../../includes/adapteroracle-short-md.md)]バインドのプロパティを参照してください[Oracle データベース アダプターのバインドのプロパティについて](../../adapters-and-accelerators/adapter-oracle-database/read-about-the-oracle-database-adapter-binding-properties.md)します。  
  
### <a name="browsing-metadata-nodes"></a>メタデータのノードを参照  
 使用する、**参照**を親ノードに含まれているすべてのメタデータのノードを返すメソッド。 次の例は、Oracle データベースで最初の 3 つのスキーマを参照します。 この例で**クライアント**のインスタンスである**MetadataRetrievalClient**します。  
  
```  
// The first parameter is the node ID.   
// The second parameter is the start index.  
// The third parameter is the maximum number of nodes to return.  
                MetadataRetrievalNode[] nodes = client.Browse(MetadataRetrievalNode.Root.NodeId, 0, 3);  
```  
  
> [!IMPORTANT]
>  カテゴリのノードのみを参照できます。操作のノードを参照することはできません。  
  
### <a name="searching-for-metadata-nodes"></a>メタデータのノードの検索  
 使用する、**検索**親ノードが格納されているノードの検索を実行するメソッド。 アダプターは、検索式です。 ワイルドカード文字をサポートしていますたとえば、パーセント (%) を指定できます。0 個以上の文字と一致するワイルドカード文字です。 次の例では、文字列"EMP"が含まれる SCOTT スキーマ内のすべてのテーブルの検索を示します。 この例で**クライアント**のインスタンスである**MetadataRetrievalClient**します。  
  
```  
// Search for all nodes that contain "EMP" under the SCOTT.Table node.  
// The parameters are the parent node ID, the search expression, and   
// the maximum number of nodes to return.  
IMetadataRetrievalNode[] nodes = client.Search("http://Microsoft.LobServices.OracleDB/2007/03/SCOTT/Table", "%EMP%", 3);  
  
```  
  
> [!IMPORTANT]
>  検索は限られた一連のノードでのみサポートします。 検索式でサポートされているワイルドカード文字および検索がサポートされているノードに関する詳細については、次を参照してください。[メタデータ ノード Id](../../adapters-and-accelerators/adapter-oracle-database/metadata-node-ids3.md)します。  
  
### <a name="retrieving-metadata-wsdl-for-operations"></a>操作のメタデータ (WSDL) を取得します。  
 使用する、 **GetMetadata**操作のノードのグループのサービスの説明 (WSDL ドキュメント) を取得します。 次の例では、サービスの説明を含むすべての操作をサーフェス、scott のアダプターを取得します。ノード ID を指定することで、EMP テーブル この例で**クライアント**のインスタンスである**MetadataRetrievalClient**します。  
  
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
>  **IsOperation**プロパティはカテゴリのノードとノードの操作が true の場合は false を指定します。  
  
### <a name="using-a-metadataretrievalclient"></a>MetadataRetrievalClient を使用します。  
 作成と使用、 **MetadataRetrievalClient**他の WCF クライアントをほぼ同じです。 エンドポイントとのインスタンスを指定してクライアントを作成する**OracleDBBinding**します。 構成で宣言またはコードで強制的に、これを行うことができます。 メソッドを呼び出して、 **MetadataRetrievalClient**を参照するには、検索、およびアダプターからメタデータを取得します。  
  
 次の例は、使用する方法を示します、 **MetadataRetrievalClient**を参照するには、検索、およびメタデータを取得、[!INCLUDE[adapteroracle_short](../../includes/adapteroracle-short-md.md)]します。 例を示します。  
  
-   Oracle データベース スキーマのメタデータのツリーのルート ノードを参照します。  
  
-   名前に文字列"EMP"を含む SCOTT スキーマ内のテーブルを検索します。  
  
-   すべての SCOTT でサポートされる操作のメタデータを取得しています。EMP テーブルにカテゴリ ノードを渡すことによって、 **GetMetadata**メソッド。  
  
-   POLLINGSTMT 操作のノードを渡すことによって、POLLINGSTMT 操作のメタデータの取得、 **GetMetadata**メソッド.  
  
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
  
 次は、コンソールでこのプログラムの出力を示します。 各メソッドによって返されるメタデータ取得のノードの構造を確認できます。 また、プログラムは 2 つの WSDL ドキュメントをファイルに書き込みます。  
  
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
  
## <a name="using-an-imetadataretrievalcontract-channel"></a>IMetadataRetrievalContract チャネルを使用してください。  
 作成することも、 **IMetadataRetrievalContract**チャネルし、このチャネルを使用して、参照、検索、およびアダプターからメタデータを取得します。 (メソッドのシグネチャが同じである、 **MetadataRetrievalClient**クラスです)。その方法を次の例に示します。  
  
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
  
## <a name="see-also"></a>参照  
 [Oracle データベースからメタデータをプログラムで取得します。](../../adapters-and-accelerators/adapter-oracle-database/get-metadata-programmatically-from-the-oracle-database.md)