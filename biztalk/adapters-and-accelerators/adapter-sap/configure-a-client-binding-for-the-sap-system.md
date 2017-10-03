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
# <a name="configure-a-client-binding-for-the-sap-system"></a><span data-ttu-id="967c0-102">SAP システムのバインディングをクライアントを構成します。</span><span class="sxs-lookup"><span data-stu-id="967c0-102">Configure a client binding for the SAP system</span></span>
<span data-ttu-id="967c0-103">WCF クライアント クラスを生成した後を WCF クライアント (インスタンス) を作成し、使用するには、そのメソッドを呼び出す、[!INCLUDE[adaptersap](../../includes/adaptersap-md.md)]です。</span><span class="sxs-lookup"><span data-stu-id="967c0-103">After you have generated the WCF client class, you can create a WCF client (instance) and invoke its methods to consume the [!INCLUDE[adaptersap](../../includes/adaptersap-md.md)].</span></span> <span data-ttu-id="967c0-104">操作用の WCF クライアント クラスとヘルパー コードを生成する方法についてを[!INCLUDE[adaptersap_short](../../includes/adaptersap-short-md.md)]公開を参照してください[WCF クライアントまたは SAP ソリューションの成果物のための WCF サービス コントラクトを生成](../../adapters-and-accelerators/adapter-sap/generate-a-wcf-client-or-a-wcf-service-contract-for-sap-solution-artifacts.md)です。</span><span class="sxs-lookup"><span data-stu-id="967c0-104">For information about how to generate the WCF client class and helper code for operations that the [!INCLUDE[adaptersap_short](../../includes/adaptersap-short-md.md)] exposes, see [Generate a WCF client or a WCF service contract for SAP solution artifacts](../../adapters-and-accelerators/adapter-sap/generate-a-wcf-client-or-a-wcf-service-contract-for-sap-solution-artifacts.md).</span></span>  
  
 <span data-ttu-id="967c0-105">WCF クライアントを作成するには、エンドポイント アドレスとバインディングを指定する必要があります。</span><span class="sxs-lookup"><span data-stu-id="967c0-105">To create the WCF client, you must specify an endpoint address and a binding.</span></span> <span data-ttu-id="967c0-106">エンドポイントのアドレスは有効な SAP 接続 URI を含める必要があり、バインディングは、SAP バインドのインスタンスである必要があります (**SAPBinding**)。</span><span class="sxs-lookup"><span data-stu-id="967c0-106">The endpoint address must contain a valid SAP connection URI, and the binding must be an instance of an SAP Binding (**SAPBinding**).</span></span> <span data-ttu-id="967c0-107">SAP 接続 URI の詳細については、次を参照してください。 [SAP システム接続 URI を作成する](../../adapters-and-accelerators/adapter-sap/create-the-sap-system-connection-uri.md)です。</span><span class="sxs-lookup"><span data-stu-id="967c0-107">For more information about the SAP connection URI, see [Create the SAP system connection URI](../../adapters-and-accelerators/adapter-sap/create-the-sap-system-connection-uri.md).</span></span>  
  
 <span data-ttu-id="967c0-108">コードまたは構成ファイルでは、SAP バインドとエンドポイント アドレスを指定できます。</span><span class="sxs-lookup"><span data-stu-id="967c0-108">You can specify the SAP Binding and the endpoint address in your code or in a configuration file.</span></span> <span data-ttu-id="967c0-109">使用すると、[!INCLUDE[addadapterservreflong](../../includes/addadapterservreflong-md.md)]プロジェクトの作成も構成ファイル (app.config) で WCF クライアント クラスを生成します。</span><span class="sxs-lookup"><span data-stu-id="967c0-109">When you use the [!INCLUDE[addadapterservreflong](../../includes/addadapterservreflong-md.md)] to generate the WCF client class, a configuration file (app.config) is also created for your project.</span></span> <span data-ttu-id="967c0-110">このファイルには、バインドのプロパティおよび接続情報 (資格情報) を除くで SAP システムに接続するときに指定したを反映する構成設定が含まれています、[!INCLUDE[addadapterservrefshort](../../includes/addadapterservrefshort-md.md)]です。</span><span class="sxs-lookup"><span data-stu-id="967c0-110">This file contains configuration settings that reflect the binding properties and connection information (except credentials) that you specified when you connected to the SAP system with the [!INCLUDE[addadapterservrefshort](../../includes/addadapterservrefshort-md.md)].</span></span>  
  
## <a name="specifying-the-binding-and-endpoint-address-in-code"></a><span data-ttu-id="967c0-111">コードでのバインディングとエンドポイント アドレスの指定</span><span class="sxs-lookup"><span data-stu-id="967c0-111">Specifying the Binding and Endpoint Address in Code</span></span>  
 <span data-ttu-id="967c0-112">次のコードでは、コード内のバインディングとエンドポイント アドレスを指定することによって、WCF クライアントを作成する方法を示します。</span><span class="sxs-lookup"><span data-stu-id="967c0-112">The following code shows how to create a WCF client by specifying the binding and endpoint address in code.</span></span> <span data-ttu-id="967c0-113">使用して SAP システムの資格情報を指定することをお勧め、 **ClientCredentials**接続エンドポイントのアドレスに指定された URI ではなく、WCF クライアントのプロパティです。</span><span class="sxs-lookup"><span data-stu-id="967c0-113">It is good practice to specify the SAP system credentials by using the **ClientCredentials** property of the WCF client rather than in the connection URI supplied for the endpoint address.</span></span>  
  
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
  
## <a name="specifying-the-binding-and-endpoint-address-in-a-configuration-file"></a><span data-ttu-id="967c0-114">構成ファイルでのバインディングとエンドポイント アドレスの指定</span><span class="sxs-lookup"><span data-stu-id="967c0-114">Specifying the Binding and Endpoint Address in a Configuration File</span></span>  
 <span data-ttu-id="967c0-115">次のコードでは、app.config ファイルでバインディングとエンドポイント アドレスを指定して、WCF クライアントを作成する方法を示します。</span><span class="sxs-lookup"><span data-stu-id="967c0-115">The following code shows how to create a WCF client by specifying the binding and endpoint address in an app.config file.</span></span>  
  
```  
// A WCF client that targets an RFC is created  
// by specifying the client endpoint information in app.config  
RfcClient rfcClient = new RfcClient("SAPBinding_Rfc");  
  
rfcClient.ClientCredentials.UserName.UserName = "YourUserName";  
rfcClient.ClientCredentials.UserName.Password = "YourPassword";  
  
rfcClient.Open();  
```  
  
 <span data-ttu-id="967c0-116">次の XML は、構成ファイルで、EMP テーブル用に作成された、[!INCLUDE[addadapterservrefshort](../../includes/addadapterservrefshort-md.md)]です。</span><span class="sxs-lookup"><span data-stu-id="967c0-116">The following XML shows the configuration file created for the EMP table by the [!INCLUDE[addadapterservrefshort](../../includes/addadapterservrefshort-md.md)].</span></span> <span data-ttu-id="967c0-117">このファイルには、前の例で参照されているクライアント エンドポイント構成が含まれています。</span><span class="sxs-lookup"><span data-stu-id="967c0-117">This file contains the client endpoint configuration referenced in the preceding example.</span></span>  
  
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
  
 <span data-ttu-id="967c0-118">プロジェクトに複数の WCF クライアントがある場合があります複数のクライアント構成ファイルで定義されているエンドポイント エントリ。</span><span class="sxs-lookup"><span data-stu-id="967c0-118">If a project has more than one WCF client, there will be multiple client endpoint entries defined in the configuration file.</span></span> <span data-ttu-id="967c0-119">各 WCF クライアント エントリが設定されます (Rfc や Trfc); ターゲット SAP システムの成果物とバインド構成に基づき、一意の名前たとえば、"SAPBinding_Rfc"です。</span><span class="sxs-lookup"><span data-stu-id="967c0-119">Each WCF client entry will have a unique name based on its binding configuration and target SAP system artifacts (such as Rfc and Trfc); for example, "SAPBinding_Rfc".</span></span> <span data-ttu-id="967c0-120">場合は、プロジェクトで、WCF クライアントを作成する複数回接続すると、複数のバインド構成エントリが作成接続ごとに 1 つです。</span><span class="sxs-lookup"><span data-stu-id="967c0-120">If you connect multiple times to create the WCF clients in your project, multiple binding configuration entries will be created, one for each connection.</span></span> <span data-ttu-id="967c0-121">これらのバインディングの構成エントリの名前は次のようになります: SAPBinding1、SAPBinding2 などです。</span><span class="sxs-lookup"><span data-stu-id="967c0-121">These binding configuration entries will be named in the following manner: SAPBinding1, SAPBinding2, and so on.</span></span> <span data-ttu-id="967c0-122">特定の接続中に作成される各クライアント エンドポイント エントリでは、その接続中に作成されたバインド エントリを参照します。</span><span class="sxs-lookup"><span data-stu-id="967c0-122">Each client endpoint entry created during a specific connection will reference the binding entry created during that connection.</span></span>  
  
> [!IMPORTANT]
>  <span data-ttu-id="967c0-123">[!INCLUDE[adaptersap_short](../../includes/adaptersap-short-md.md)]同じサービス コントラクトのさまざまな操作として、同じ種類 (RFC、TRFC、IDOC など) のさまざまな SAP アイテムを表示します。</span><span class="sxs-lookup"><span data-stu-id="967c0-123">The [!INCLUDE[adaptersap_short](../../includes/adaptersap-short-md.md)] surfaces different SAP artifacts of the same type (such as RFC, TRFC, and IDOC) as different operations of the same service contract.</span></span> <span data-ttu-id="967c0-124">例については、次の 2 つの異なる Rfc、RFC_EXAMPLE_A および RFC_EXAMPLE_B、両方が提示される同じサービス コントラクト ("Rfc") の下。</span><span class="sxs-lookup"><span data-stu-id="967c0-124">For example, two different RFCs, RFC_EXAMPLE_A and RFC_EXAMPLE_B, will both be surfaced under the same service contract ("Rfc").</span></span> <span data-ttu-id="967c0-125">つまり、両方の Rfc を同じ WCF クライアント クラスによって呼び出されること**RfcClient**、両方の Rfc のパラメーターは、同じ名前空間で宣言することです。</span><span class="sxs-lookup"><span data-stu-id="967c0-125">This means that both RFCs will be invoked by the same WCF client class, **RfcClient**, and that the parameters for both RFCs will be declared in the same namespace.</span></span> <span data-ttu-id="967c0-126">そのため、同じの中に両方の Rfc の WCF クライアントを生成する必要があります[!INCLUDE[addadapterservrefshort](../../includes/addadapterservrefshort-md.md)]ソリューションをビルドするときに、名前空間の競合の発生を回避するセッション (接続)。</span><span class="sxs-lookup"><span data-stu-id="967c0-126">Therefore, you must generate the WCF client for both RFCs during the same [!INCLUDE[addadapterservrefshort](../../includes/addadapterservrefshort-md.md)] session (connection) to avoid experiencing a namespace collision when you build your solution.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="967c0-127">参照</span><span class="sxs-lookup"><span data-stu-id="967c0-127">See Also</span></span>  
<span data-ttu-id="967c0-128">[WCF サービス モデルを使用して SAP アプリケーションを開発します。](../../adapters-and-accelerators/adapter-sap/develop-sap-applications-using-the-wcf-service-model.md) </span><span class="sxs-lookup"><span data-stu-id="967c0-128">[Develop SAP applications using the WCF Service Model](../../adapters-and-accelerators/adapter-sap/develop-sap-applications-using-the-wcf-service-model.md) </span></span>  
 <span data-ttu-id="967c0-129">[WCF クライアントまたは SAP ソリューションの成果物のための WCF サービス コントラクトを生成します。](../../adapters-and-accelerators/adapter-sap/generate-a-wcf-client-or-a-wcf-service-contract-for-sap-solution-artifacts.md) </span><span class="sxs-lookup"><span data-stu-id="967c0-129">[Generate a WCF client or a WCF service contract for SAP solution artifacts](../../adapters-and-accelerators/adapter-sap/generate-a-wcf-client-or-a-wcf-service-contract-for-sap-solution-artifacts.md) </span></span>  
 [<span data-ttu-id="967c0-130">SAP システム接続 URI を作成します。</span><span class="sxs-lookup"><span data-stu-id="967c0-130">Create the SAP system connection URI</span></span>](../../adapters-and-accelerators/adapter-sap/create-the-sap-system-connection-uri.md)