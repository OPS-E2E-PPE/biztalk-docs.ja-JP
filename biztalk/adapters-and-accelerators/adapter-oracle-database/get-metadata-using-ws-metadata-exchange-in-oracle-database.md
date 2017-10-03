---
title: "Ws-metadata Exchange を使用して Oracle データベースでメタデータの取得 |Microsoft ドキュメント"
ms.custom: 
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: 
ms.suite: 
ms.tgt_pltfrm: 
ms.topic: article
helpviewer_keywords:
- WS-Metadata Exchange, retrieving metadata
- metadata, retrieving using WS-Metadata Exchange
ms.assetid: 6ff34438-7260-489d-a5f0-6e53f8fe43be
caps.latest.revision: "4"
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: 2be3f829d41b77dc7897d7b3f4300d82e7a3c100
ms.sourcegitcommit: cb908c540d8f1a692d01dc8f313e16cb4b4e696d
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 09/20/2017
---
# <a name="get-metadata-using-ws-metadata-exchange-in-oracle-database"></a>Ws-metadata Exchange を使用して Oracle データベースでメタデータを取得します。
として、[!INCLUDE[firstref_btsWinCommFoundation](../../includes/firstref-btswincommfoundation-md.md)]カスタム バインドを[!INCLUDE[adapteroracle](../../includes/adapteroracle-md.md)]から特定の操作についてのメタデータの取得に使用できる Ws-metadata Exchange (MEX) エンドポイントを公開して、[!INCLUDE[adapteroracle](../../includes/adapteroracle-md.md)]です。  
  
 WCF には、エクスポート、公開、取得、およびサービスに関するメタデータをインポートするための豊富なインフラストラクチャが用意されています。 アダプターと同様に、WCF サービスでは、メタデータを使用して、svcutil.exe などのツールが、サービスを使用するためのクライアント コードを自動的に生成されるようにサービス エンドポイントと対話する方法について説明します。 WCF では、サービスのメタデータを表すのインスタンスとして、 **MetadataSet**型で、Ws-metadata Exchange (MEX) で定義されているメタデータのシリアル化形式に強く関連付けられています。 作成することができます、 **MetadataSet**を使用してアダプターに対する操作の対象となる、 **MetadataExchangeClient**です。  
  
 WCF では、メタデータ交換ができる拡張可能なトピックでは、このドキュメントの範囲を超えてをサポートします。 WCF でのメタデータのサポートの詳細については、次を参照してください。[メタデータ](https://msdn.microsoft.com/library/ms731823.aspx)です。 詳細については特に効果的なアーキテクチャ、クラス、およびメタデータを公開する WCF の名前空間の次を参照してください。[メタデータ アーキテクチャの概要](https://msdn.microsoft.com/library/ms730243.aspx)です。 続行する前にこれらの WCF トピック内の WCF サービスからメタデータの取得に関連するコンテンツを理解しておく必要があります。  
  
 次のトピックには、使用方法に関する情報が含まれて、 **MetadataExchangeClient**メタデータを取得する、[!INCLUDE[adapteroracle_short](../../includes/adapteroracle-short-md.md)]です。  
  
## <a name="using-a-metadataexchangeclient-to-retrieve-metadata"></a>MetadataExchangeClient を使用してメタデータを取得するには  
 使用する、 **MetadataExchangeClient**接続 URI とバインディングを指定する必要があります (**OracleDBBinding**)。 接続 URI では、メタデータを取得する操作を識別します。  
  
 次のセクションでは、接続 URI、重要なバインドのプロパティを指定する方法と使用方法に関する情報を格納する、 **MetadataExchangeClient**アダプターからメタデータを取得します。  
  
### <a name="the-connection-uri"></a>接続 URI  
 使用する、 **MetadataExchangeClient** Oracle 接続 MEX エンドポイントと操作のメタデータを取得する操作を指定する URI を指定する必要があります。 次のように、接続 URI で MEX エンドポイントとターゲットの操作を指定します。  
  
-   クエリ文字列には、"wsdl"パラメーターを含める必要があります。 クエリ文字列の最初のパラメーターは場合、疑問符 (?) の直後に指定されています。 場合は、最初のパラメーターでない場合は、その必要がありますの前に、アンパサンド (&)。  
  
-   1 つまたは複数の"op"パラメーターで、"wsdl"パラメーターに従う必要があります。 各"op"パラメーターは、前にアンパサンド (&) し、ターゲットの操作のメッセージのアクション (ノードの ID) を指定します。  
  
 たとえば、次の接続 URI、SCOTT の挿入および削除操作のターゲットです。EMP テーブルです。 "Wsdl"および"op"パラメーターが強調表示されます。  
  
```  
"oracledb://ADAPTER?wsdl&op=http://Microsoft.LobServices.OracleDB/2007/03/SCOTT/Table/EMP/Insert&op=http://Microsoft.LobServices.OracleDB/2007/03/SCOTT/Table/EMP/Delete"  
```  
  
> [!NOTE]
>  POLLINGSTMT 操作に対して生成された名前空間を変更する場合は、クエリ文字列に PollingId パラメーターを指定する必要があります。  
  
 この接続 URI を渡す方法を**MetadataExchangeClient**クライアントを作成して、アダプターからのメタデータの取得に使用するオーバー ロードされたメソッドのうちに依存します。  
  
 Oracle の接続 URI の詳細については、次を参照してください。 [Oracle Database 接続 URI を作成する](../../adapters-and-accelerators/adapter-oracle-database/create-the-oracle-database-connection-uri.md)です。  
  
### <a name="binding-properties"></a>バインドのプロパティ  
 作成するときに、 **MetadataExchangeClient**を指定する必要があります、 **OracleDBBinding**です。  
  
 アダプターがメタデータを生成する方法に影響を与えるいくつかのバインド プロパティがあります。 これらのプロパティは次のとおりです。  
  
-   **EnableSafeTyping**  
  
-   **UseSchemaInNamespace**  
  
-   **PollingStatement**  
  
> [!IMPORTANT]
>  設定する必要があります、POLLINGSTMT 操作のメタデータを取得する場合、 **PollingStatement**プロパティをバインドします。  
  
 呼び出す前に、アプリケーションに必要な値をこれらのバインディング プロパティを設定することを確認する必要があります、 **GetMetadata**メソッドを**MetadataExchangeClient**です。 詳細については、[!INCLUDE[adapteroracle_short](../../includes/adapteroracle-short-md.md)]バインドのプロパティを参照してください[Oracle データベース アダプターのバインドのプロパティについてお読み](../../adapters-and-accelerators/adapter-oracle-database/read-about-the-oracle-database-adapter-binding-properties.md)です。  
  
### <a name="example"></a>例  
 次の例では、 **MetadataExchangeClient**を Insert、Update、Delete、および、SCOTT に対する Select 操作のサービスの説明 (WSDL ドキュメント) を作成します。EMP テーブルです。 WSDL は、ファイル、EmpOperations.wsdl に保存されます。  
  
```  
using System;  
using System.Collections.Generic;  
using System.Text;  
using System.Collections.ObjectModel;  
  
// Needed for WCF and Oracle Adapter  
using System.ServiceModel;  
using Microsoft.ServiceModel.Channels;  
using Microsoft.Adapters.OracleDB;  
  
// Needced for MetadataExchangeClient class  
using System.ServiceModel.Description;  
// Needed for ServiceDescription class  
using System.Web.Services;  
  
namespace OracleMetadataExchange  
{  
    class Program  
    {  
        static void Main(string[] args)  
        {  
            //create a binding  
            OracleDBBinding binding = new OracleDBBinding();  
  
            //create a metadata exchange client that will retrieve metadata according to the WS-MEX standard  
            MetadataExchangeClient client = new MetadataExchangeClient(binding);  
            client.SoapCredentials.UserName.UserName = "SCOTT";  
            client.SoapCredentials.UserName.Password = "TIGER";  
  
            //set up an endpoint address and specifies the operations for which we want metadata  
            string connectionUri = "oracledb://ADAPTER?wsdl"  
                + "&op="  
                + "http://Microsoft.LobServices.OracleDB/2007/03/SCOTT/Table/EMP/Insert"  
                + "&op="  
                + "http://Microsoft.LobServices.OracleDB/2007/03/SCOTT/Table/EMP/Update"  
                + "&op="  
                + "http://Microsoft.LobServices.OracleDB/2007/03/SCOTT/Table/EMP/Delete"  
                + "&op="  
                + "http://Microsoft.LobServices.OracleDB/2007/03/SCOTT/Table/EMP/Select";  
  
            EndpointAddress address = new EndpointAddress(connectionUri);  
  
            //get the metadata  
            MetadataSet ms = client.GetMetadata(address);  
  
            // Check for the metadata set size   
            Collection<MetadataSection> documentCollection = ms.MetadataSections;  
            if (documentCollection != null && documentCollection.Count > 0)  
            {  
                //get the wsdl from the metadata set  
                System.Web.Services.Description.ServiceDescription wsdl = (System.Web.Services.Description.ServiceDescription)documentCollection[0].Metadata;  
  
                //save the wsdl to a file  
                wsdl.Write("EmpOperations.wsdl");  
  
            }  
  
        }  
    }  
}  
```  
  
## <a name="see-also"></a>参照  
 [Oracle データベースからメタデータをプログラムで取得します。](../../adapters-and-accelerators/adapter-oracle-database/get-metadata-programmatically-from-the-oracle-database.md)