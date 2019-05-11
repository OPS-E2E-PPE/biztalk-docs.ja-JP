---
title: Ws-metadata Exchange を使用して sap メタデータの取得 |Microsoft Docs
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
ms.openlocfilehash: 4f5ae9cebdef84870379d3fe28c0ef72bc1dea71
ms.sourcegitcommit: 381e83d43796a345488d54b3f7413e11d56ad7be
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 05/07/2019
ms.locfileid: "65373391"
---
# <a name="get-metadata-using-ws-metadata-exchange-in-sap"></a>SAP で Ws-metadata Exchange を使用してメタデータを取得します。
として、[!INCLUDE[firstref_btsWinCommFoundation](../../includes/firstref-btswincommfoundation-md.md)]カスタム バインドを[!INCLUDE[adaptersap](../../includes/adaptersap-md.md)]から特定の操作のメタデータの取得に使用できる Ws-metadata Exchange (MEX) エンドポイントを公開して、[!INCLUDE[adaptersap](../../includes/adaptersap-md.md)]します。  
  
 WCF には、エクスポート、公開、取得、およびサービスに関するメタデータをインポートするためのさまざまなインフラストラクチャが用意されています。 アダプターなどの WCF サービスでは、メタデータを使用して、svcutil.exe などのツールが、サービスを使用するためのクライアント コードを自動的に生成されるように、サービス エンドポイントと対話する方法について説明します。 WCF では、サービスのメタデータを表すのインスタンスとして、 **MetadataSet**型で、Ws-metadata Exchange (MEX) で定義されているメタデータのシリアル化形式には厳密に関連付けられています。 作成することができます、 **MetadataSet**を対象となる操作を使用して、アダプター、 **MetadataExchangeClient**します。  
  
 WCF では、メタデータ交換は、包括的なトピックと、このドキュメントの範囲を超えてをサポートします。 WCF でのメタデータのサポートの詳細についてを参照してください「メタデータ」で、WCF ドキュメント[ http://go.microsoft.com/fwlink/?LinkId=105634](http://go.microsoft.com/fwlink/?LinkId=105634)します。 特に適切なアーキテクチャについては、クラス、およびメタデータについては、WCF が公開する名前空間を参照してください「メタデータ アーキテクチャの概要」 [ http://go.microsoft.com/fwlink/?LinkId=105635](http://go.microsoft.com/fwlink/?LinkId=105635)します。 続行する前にこれらの WCF トピック内の WCF サービスからメタデータの取得に関連するコンテンツを理解しておく必要があります。  
  
 次のトピックでは、使用する方法については、 **MetadataExchangeClient**メタデータを取得する、[!INCLUDE[adaptersap_short](../../includes/adaptersap-short-md.md)]します。  
  
## <a name="using-a-metadataexchangeclient-to-retrieve-metadata"></a>MetadataExchangeClient を使用してメタデータを取得するには  
 使用する、 **MetadataExchangeClient**接続 URI とバインディングを指定する必要があります (**SAPBinding**)。 接続 URI では、メタデータを取得する操作を識別します。  
  
 次のセクションでは、接続 URI、重要なバインドのプロパティを指定する方法と使用方法に関する情報を格納する、 **MetadataExchangeClient**アダプターからメタデータを取得します。  
  
### <a name="the-connection-uri"></a>接続 URI  
 使用する、 **MetadataExchangeClient** SAP 接続 MEX エンドポイントと操作、またはメタデータを取得する操作を指定する URI を指定する必要があります。 次のように、接続 URI で MEX エンドポイントとターゲットの操作を指定します。  
  
- クエリ文字列で"wsdl"パラメーターを含める必要があります。 クエリ文字列の最初のパラメーターは場合、疑問符 (?) の直後に指定します。 最初のパラメーターではない場合、アンパサンドを付ける必要があります (&)。  
  
- 1 つまたは複数の"op"パラメーターで"wsdl"パラメーターに従う必要があります。 各"op"パラメーターは、前にアンパサンド (&) を対象の操作のメッセージのアクション (ノード ID) を指定します。  
  
  たとえば、次の接続 URI SALESORDER_CREATEFROMDAT201 IDOC と SALESORDER_CREATEFROMDAT202 IDOC に対する送信操作の対象です。 "Wsdl"と"op"パラメーターが強調表示されます。  
  
```  
"sap://User=YourUserName;Passwd=YourPassword;Client=800;Lang=EN;@a/YourSAPHost/00?wsdl&op=http://Microsoft.LobServices.Sap/2007/03/Idoc/3/SALESORDER_CREATEFROMDAT201//620/Send&op=http://Microsoft.LobServices.Sap/2007/03/Idoc/3/SALESORDER_CREATEFROMDAT202//620/Send"  
```  
  
> [!NOTE]
>  受信操作の接続 URI でリスナーのパラメーターを含める必要はありません。 アダプターは、SAP システムからメタデータを取得するクライアントとして接続します。  
  
 定義した定数を使用することもできます。`Microsoft.Adapters.SAP.SAPAdapterConstants.ActionConstants`接続 URI を作成するときに、操作を指定するためにします。 これについては、このトピックの最後のコード例に示します。  
  
 この接続の URI を渡す方法を**MetadataExchangeClient**のどのクライアントを作成して、アダプターからのメタデータの取得に使用するオーバー ロードされたメソッドに依存します。  
  
 SAP 接続 URI の詳細については、次を参照してください。 [SAP システム接続 URI を使用すると、作成](../../adapters-and-accelerators/adapter-sap/create-the-sap-system-connection-uri.md)です。  
  
### <a name="binding-properties"></a>バインドのプロパティ  
 作成するときに、 **MetadataExchangeClient**を指定する必要があります、 **SAPBinding**します。  
  
 アダプターがメタデータを生成する方法に影響を与えるいくつかのバインド プロパティがあります。 これらのプロパティは次のとおりです。  
  
- **GenerateFlatfileCompatibleIdocSchema**  
  
- **ReceiveIDocFormat**  
  
- **EnableSafeTyping**  
  
- **FlatFileSegmentIndicator**  
  
  これらのバインドのプロパティを呼び出す前に、アプリケーションに必要な値に設定されていることを確認する必要があります、 **GetMetadata**メソッドを**MetadataExchangeClient**します。 SAP アダプターのバインド プロパティの詳細については、次を参照してください。 [mySAP Business Suite バインド プロパティの BizTalk アダプターについて](../../adapters-and-accelerators/adapter-sap/read-about-biztalk-adapter-for-mysap-business-suite-binding-properties.md)します。  
  
### <a name="example"></a>例  
 次の例では、 **MetadataExchangeClient** BAPI_TRANSACTION_COMMIT と BAPI_TRANSACTION_ROLLBACK の操作のためのサービスの説明 (WSDL ドキュメント) を作成します。  
  
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
 [SAP からプログラムでメタデータの取得](../../adapters-and-accelerators/adapter-sap/get-metadata-programmatically-from-sap.md)   
 [IMetadataRetrievalContract を使用して sap メタデータの取得](../../adapters-and-accelerators/adapter-sap/get-metadata-in-sap-using-imetadataretrievalcontract.md)