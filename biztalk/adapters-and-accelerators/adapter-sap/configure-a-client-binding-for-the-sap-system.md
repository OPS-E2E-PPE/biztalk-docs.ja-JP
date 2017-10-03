---
title: "バインディングの SAP システムをクライアントの構成 |Microsoft ドキュメント"
ms.custom: 
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: 
ms.suite: 
ms.tgt_pltfrm: 
ms.topic: article
helpviewer_keywords:
- proxy programming, creating a proxy
- creating a proxy
- how to, create a proxy
ms.assetid: bceef132-29ff-4207-a37d-bf94fab484dd
caps.latest.revision: "6"
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: f75253251d18049363255f553ded833748e33875
ms.sourcegitcommit: cb908c540d8f1a692d01dc8f313e16cb4b4e696d
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 09/20/2017
---
# <a name="configure-a-client-binding-for-the-sap-system"></a>SAP システムのバインディングをクライアントを構成します。
WCF クライアント クラスを生成した後を WCF クライアント (インスタンス) を作成し、使用するには、そのメソッドを呼び出す、[!INCLUDE[adaptersap](../../includes/adaptersap-md.md)]です。 操作用の WCF クライアント クラスとヘルパー コードを生成する方法についてを[!INCLUDE[adaptersap_short](../../includes/adaptersap-short-md.md)]公開を参照してください[WCF クライアントまたは SAP ソリューションの成果物のための WCF サービス コントラクトを生成](../../adapters-and-accelerators/adapter-sap/generate-a-wcf-client-or-a-wcf-service-contract-for-sap-solution-artifacts.md)です。  
  
 WCF クライアントを作成するには、エンドポイント アドレスとバインディングを指定する必要があります。 エンドポイントのアドレスは有効な SAP 接続 URI を含める必要があり、バインディングは、SAP バインドのインスタンスである必要があります (**SAPBinding**)。 SAP 接続 URI の詳細については、次を参照してください。 [SAP システム接続 URI を作成する](../../adapters-and-accelerators/adapter-sap/create-the-sap-system-connection-uri.md)です。  
  
 コードまたは構成ファイルでは、SAP バインドとエンドポイント アドレスを指定できます。 使用すると、[!INCLUDE[addadapterservreflong](../../includes/addadapterservreflong-md.md)]プロジェクトの作成も構成ファイル (app.config) で WCF クライアント クラスを生成します。 このファイルには、バインドのプロパティおよび接続情報 (資格情報) を除くで SAP システムに接続するときに指定したを反映する構成設定が含まれています、[!INCLUDE[addadapterservrefshort](../../includes/addadapterservrefshort-md.md)]です。  
  
## <a name="specifying-the-binding-and-endpoint-address-in-code"></a>コードでのバインディングとエンドポイント アドレスの指定  
 次のコードでは、コード内のバインディングとエンドポイント アドレスを指定することによって、WCF クライアントを作成する方法を示します。 使用して SAP システムの資格情報を指定することをお勧め、 **ClientCredentials**接続エンドポイントのアドレスに指定された URI ではなく、WCF クライアントのプロパティです。  
  
```  
// A WCF client that targets an RFC is created  
// by using a binding object and endpoint address  
SAPBinding sapBinding = new SAPBinding();  
EndpointAddress sapAddress = new EndpointAddress("sap://CLIENT=800;LANG=EN;@a/YourSAPHost/00");  
  
RfcClient rfcClient = new RfcClient(sapBinding, sapAddress);  
  
rfcClient.ClientCredentials.UserName.UserName = "YourUserName";  
rfcClient.ClientCredentials.UserName.Password = "YourPassword";  
  
rfcClient.Open();  
```  
  
## <a name="specifying-the-binding-and-endpoint-address-in-a-configuration-file"></a>構成ファイルでのバインディングとエンドポイント アドレスの指定  
 次のコードでは、app.config ファイルでバインディングとエンドポイント アドレスを指定して、WCF クライアントを作成する方法を示します。  
  
```  
// A WCF client that targets an RFC is created  
// by specifying the client endpoint information in app.config  
RfcClient rfcClient = new RfcClient("SAPBinding_Rfc");  
  
rfcClient.ClientCredentials.UserName.UserName = "YourUserName";  
rfcClient.ClientCredentials.UserName.Password = "YourPassword";  
  
rfcClient.Open();  
```  
  
 次の XML は、構成ファイルで、EMP テーブル用に作成された、[!INCLUDE[addadapterservrefshort](../../includes/addadapterservrefshort-md.md)]です。 このファイルには、前の例で参照されているクライアント エンドポイント構成が含まれています。  
  
```  
\<?xml version="1.0" encoding="utf-8"?>  
<configuration xmlns="http://schemas.microsoft.com/.NetConfiguration/v2.0">  
    \<system.serviceModel>  
        <bindings>  
            <sapBinding>  
                <binding name="SAPBinding" closeTimeout="00:01:00" openTimeout="00:01:00"  
                    receiveTimeout="00:10:00" sendTimeout="00:01:00" receiveIdocFormat="Typed"  
                    generateFlatFileCompatibleIdocSchema="true" maxConnectionsPerSystem="50"  
                    enableConnectionPooling="true" idleConnectionTimeout="00:15:00"  
                    flatFileSegmentIndicator="SegmentDefinition" enablePerformanceCounters="false"  
                    autoConfirmSentIdocs="false"  
                    acceptCredentialsInUri="false" padReceivedIdocWithSpaces="false"  
                    enableBizTalkCompatibilityMode="false" />  
            </sapBinding>  
        </bindings>  
        <client>  
            <endpoint address="sap://CLIENT=800;LANG=EN;@a/YourSAPHost/00?RfcSdkTrace=False&AbapDebug=False&UseSapGui=Without"  
                binding="sapBinding" bindingConfiguration="SAPBinding" contract="Rfc"  
                name="SAPBinding_Rfc" />  
        </client>  
    \</system.serviceModel>  
</configuration>  
```  
  
 プロジェクトに複数の WCF クライアントがある場合があります複数のクライアント構成ファイルで定義されているエンドポイント エントリ。 各 WCF クライアント エントリが設定されます (Rfc や Trfc); ターゲット SAP システムの成果物とバインド構成に基づき、一意の名前たとえば、"SAPBinding_Rfc"です。 場合は、プロジェクトで、WCF クライアントを作成する複数回接続すると、複数のバインド構成エントリが作成接続ごとに 1 つです。 これらのバインディングの構成エントリの名前は次のようになります: SAPBinding1、SAPBinding2 などです。 特定の接続中に作成される各クライアント エンドポイント エントリでは、その接続中に作成されたバインド エントリを参照します。  
  
> [!IMPORTANT]
>  [!INCLUDE[adaptersap_short](../../includes/adaptersap-short-md.md)]同じサービス コントラクトのさまざまな操作として、同じ種類 (RFC、TRFC、IDOC など) のさまざまな SAP アイテムを表示します。 例については、次の 2 つの異なる Rfc、RFC_EXAMPLE_A および RFC_EXAMPLE_B、両方が提示される同じサービス コントラクト ("Rfc") の下。 つまり、両方の Rfc を同じ WCF クライアント クラスによって呼び出されること**RfcClient**、両方の Rfc のパラメーターは、同じ名前空間で宣言することです。 そのため、同じの中に両方の Rfc の WCF クライアントを生成する必要があります[!INCLUDE[addadapterservrefshort](../../includes/addadapterservrefshort-md.md)]ソリューションをビルドするときに、名前空間の競合の発生を回避するセッション (接続)。  
  
## <a name="see-also"></a>参照  
[WCF サービス モデルを使用して SAP アプリケーションを開発します。](../../adapters-and-accelerators/adapter-sap/develop-sap-applications-using-the-wcf-service-model.md)   
 [WCF クライアントまたは SAP ソリューションの成果物のための WCF サービス コントラクトを生成します。](../../adapters-and-accelerators/adapter-sap/generate-a-wcf-client-or-a-wcf-service-contract-for-sap-solution-artifacts.md)   
 [SAP システム接続 URI を作成します。](../../adapters-and-accelerators/adapter-sap/create-the-sap-system-connection-uri.md)