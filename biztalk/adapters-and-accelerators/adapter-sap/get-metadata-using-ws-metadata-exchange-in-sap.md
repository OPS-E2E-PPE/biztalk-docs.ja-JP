---
title: SAP で Ws-metadata Exchange を使用してメタデータの取得 |Microsoft ドキュメント
ms.custom: ''
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: ''
ms.suite: ''
ms.tgt_pltfrm: ''
ms.topic: article
helpviewer_keywords:
- WS-Metadata Exchange
- how to, retrieve metadata
- retrieving metadata
ms.assetid: 29f85963-ac7f-4e13-96b8-bc2c94a9fcae
caps.latest.revision: 7
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: ae33fd76725abf15f12d95be39997fc29e67403e
ms.sourcegitcommit: cb908c540d8f1a692d01dc8f313e16cb4b4e696d
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 09/20/2017
ms.locfileid: "22216882"
---
# <a name="get-metadata-using-ws-metadata-exchange-in-sap"></a>SAP で Ws-metadata Exchange を使用してメタデータを取得します。
として、[!INCLUDE[firstref_btsWinCommFoundation](../../includes/firstref-btswincommfoundation-md.md)]カスタム バインドを[!INCLUDE[adaptersap](../../includes/adaptersap-md.md)]から特定の操作についてのメタデータの取得に使用できる Ws-metadata Exchange (MEX) エンドポイントを公開して、[!INCLUDE[adaptersap](../../includes/adaptersap-md.md)]です。  
  
 WCF には、エクスポート、公開、取得、およびサービスに関するメタデータをインポートするための豊富なインフラストラクチャが用意されています。 アダプターと同様に、WCF サービスでは、メタデータを使用して、svcutil.exe などのツールが、サービスを使用するためのクライアント コードを自動的に生成されるようにサービス エンドポイントと対話する方法について説明します。 WCF では、サービスのメタデータを表すのインスタンスとして、 **MetadataSet**型で、Ws-metadata Exchange (MEX) で定義されているメタデータのシリアル化形式に強く関連付けられています。 作成することができます、 **MetadataSet**を使用してアダプターに対する操作の対象となる、 **MetadataExchangeClient**です。  
  
 WCF では、メタデータ交換ができる拡張可能なトピックでは、このドキュメントの範囲を超えてをサポートします。 WCF でのメタデータのサポートの詳細についてを参照してください「メタデータ」で、WCF ドキュメント[http://go.microsoft.com/fwlink/?LinkId=105634](http://go.microsoft.com/fwlink/?LinkId=105634)です。 特に優れての詳細については、アーキテクチャ、クラス、および WCF は、メタデータの公開の名前空間を参照してください「メタデータ アーキテクチャの概要」 [http://go.microsoft.com/fwlink/?LinkId=105635](http://go.microsoft.com/fwlink/?LinkId=105635)です。 続行する前にこれらの WCF トピック内の WCF サービスからメタデータの取得に関連するコンテンツを理解しておく必要があります。  
  
 次のトピックには、使用方法に関する情報が含まれて、 **MetadataExchangeClient**メタデータを取得する、[!INCLUDE[adaptersap_short](../../includes/adaptersap-short-md.md)]です。  
  
## <a name="using-a-metadataexchangeclient-to-retrieve-metadata"></a>MetadataExchangeClient を使用してメタデータを取得するには  
 使用する、 **MetadataExchangeClient**接続 URI とバインディングを指定する必要があります (**SAPBinding**)。 接続 URI では、メタデータを取得する操作を識別します。  
  
 次のセクションでは、接続 URI、重要なバインドのプロパティを指定する方法と使用方法に関する情報を格納する、 **MetadataExchangeClient**アダプターからメタデータを取得します。  
  
### <a name="the-connection-uri"></a>接続 URI  
 使用する、 **MetadataExchangeClient** SAP 接続を MEX エンドポイントと操作のメタデータを取得する操作を指定する URI を指定する必要があります。 次のように、接続 URI で MEX エンドポイントとターゲットの操作を指定します。  
  
-   クエリ文字列には、"wsdl"パラメーターを含める必要があります。 クエリ文字列の最初のパラメーターは場合、疑問符 (?) の直後に指定されています。 場合は、最初のパラメーターでない場合は、その必要がありますの前に、アンパサンド (&)。  
  
-   1 つまたは複数の"op"パラメーターで、"wsdl"パラメーターに従う必要があります。 各"op"パラメーターは、前にアンパサンド (&) し、ターゲットの操作のメッセージのアクション (ノードの ID) を指定します。  
  
 たとえば、次の接続 URI SALESORDER_CREATEFROMDAT201 IDOC および SALESORDER_CREATEFROMDAT202 IDOC に対する送信操作のターゲットです。 "Wsdl"および"op"パラメーターが強調表示されます。  
  
```  
"sap://User=YourUserName;Passwd=YourPassword;Client=800;Lang=EN;@a/YourSAPHost/00?wsdl&op=http://Microsoft.LobServices.Sap/2007/03/Idoc/3/SALESORDER_CREATEFROMDAT201//620/Send&op=http://Microsoft.LobServices.Sap/2007/03/Idoc/3/SALESORDER_CREATEFROMDAT202//620/Send"  
```  
  
> [!NOTE]
>  受信操作の接続 URI にリスナーのパラメーターを含める必要はありません。 アダプターは、SAP システムからメタデータを取得するクライアントとして接続します。  
  
 定義されている定数を使用することもできます。`Microsoft.Adapters.SAP.SAPAdapterConstants.ActionConstants`接続 URI を作成するときに、操作を指定するためです。 これは、このトピックの最後のコード例に示します。  
  
 この接続 URI を渡す方法を**MetadataExchangeClient**クライアントを作成して、アダプターからのメタデータの取得に使用するオーバー ロードされたメソッドのうちに依存します。  
  
 SAP 接続 URI の詳細については、次を参照してください。 [SAP システムの接続 URI を作成する](../../adapters-and-accelerators/adapter-sap/create-the-sap-system-connection-uri.md)です。  
  
### <a name="binding-properties"></a>バインドのプロパティ  
 作成するときに、 **MetadataExchangeClient**を指定する必要があります、 **SAPBinding**です。  
  
 アダプターがメタデータを生成する方法に影響を与えるいくつかのバインド プロパティがあります。 これらのプロパティは次のとおりです。  
  
-   **GenerateFlatfileCompatibleIdocSchema**  
  
-   **ReceiveIDocFormat**  
  
-   **EnableSafeTyping**  
  
-   **FlatFileSegmentIndicator**  
  
 呼び出す前に、アプリケーションに必要な値をこれらのバインディング プロパティを設定することを確認する必要があります、 **GetMetadata**メソッドを**MetadataExchangeClient**です。 SAP アダプターのバインドのプロパティの詳細については、次を参照してください。 [mySAP Business Suite バインド プロパティの BizTalk アダプターの説明を読む](../../adapters-and-accelerators/adapter-sap/read-about-biztalk-adapter-for-mysap-business-suite-binding-properties.md)です。  
  
### <a name="example"></a>例  
 次の例では、 **MetadataExchangeClient** BAPI_TRANSACTION_COMMIT および BAPI_TRANSACTION_ROLLBACK 操作のサービスの説明 (WSDL ドキュメント) を作成します。  
  
```  
using System;  
using System.Collections.Generic;  
using System.Text;  
using System.Collections.ObjectModel;  
  
// Needed for WCF and SAP adapter  
using System.ServiceModel;  
using Microsoft.ServiceModel.Channels;  
using Microsoft.Adapters.SAP;  
  
// Needed for MetadataExchangeClient class  
using System.ServiceModel.Description;  
// Needed for ServiceDescription class  
using System.Web.Services;  
  
namespace SapMetadataExchangeClient  
{  
    class Program  
    {  
        static void Main(string[] args)  
        {  
            //Create a binding  
            SAPBinding binding = new SAPBinding();  
  
            //Create a metadata exchange client that will retrieve metadata according to the WS-MEX standard.  
            MetadataExchangeClient client = new MetadataExchangeClient(binding);  
            client.SoapCredentials.UserName.UserName = "YourUserName";  
            client.SoapCredentials.UserName.Password = "YourPassword";  
  
            //Set up an endpoint address and specify the operation for which we want metadata.  
            string connectionUri = "sap://Client=800;lang=EN@A/YourSAPHost/00?wsdl&op="  
                + Microsoft.Adapters.SAP.SAPAdapterConstants.ActionConstants.RfcActionPrefix  
                + "BAPI_TRANSACTION_COMMIT"  
                + "&op="  
                + Microsoft.Adapters.SAP.SAPAdapterConstants.ActionConstants.RfcActionPrefix  
                + "BAPI_TRANSACTION_ROLLBACK";  
  
            EndpointAddress address = new EndpointAddress(connectionUri);  
  
            //Get the metadata.  
            MetadataSet ms = client.GetMetadata(address);  
  
            // Check for the metadata set size.   
            Collection<MetadataSection> documentCollection = ms.MetadataSections;  
            if (documentCollection != null && documentCollection.Count > 0)  
            {  
                //Get the WSDL from the metadata set  
                System.Web.Services.Description.ServiceDescription wsdl = (System.Web.Services.Description.ServiceDescription)documentCollection[0].Metadata;  
  
                //Save the WSDL to a file.  
                wsdl.Write("BapiTx.wsdl");    
  
            }  
  
        }  
    }  
}  
```  
  
## <a name="see-also"></a>参照  
 [SAP からメタデータをプログラムで取得します。](../../adapters-and-accelerators/adapter-sap/get-metadata-programmatically-from-sap.md)   
 [IMetadataRetrievalContract を使用して SAP のメタデータを取得します。](../../adapters-and-accelerators/adapter-sap/get-metadata-in-sap-using-imetadataretrievalcontract.md)