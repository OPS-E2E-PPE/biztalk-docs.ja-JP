---
title: バインドの SAP システムのクライアントの構成 |Microsoft Docs
ms.custom: ''
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: ''
ms.suite: ''
ms.tgt_pltfrm: ''
ms.topic: article
helpviewer_keywords:
- proxy programming, creating a proxy
- creating a proxy
- how to, create a proxy
ms.assetid: bceef132-29ff-4207-a37d-bf94fab484dd
caps.latest.revision: 6
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: 6788d735a1c2d91937473661365e7da393426b65
ms.sourcegitcommit: 381e83d43796a345488d54b3f7413e11d56ad7be
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 05/07/2019
ms.locfileid: "65373958"
---
# <a name="configure-a-client-binding-for-the-sap-system"></a><span data-ttu-id="2e291-102">クライアントの SAP システムのバインドを構成します。</span><span class="sxs-lookup"><span data-stu-id="2e291-102">Configure a client binding for the SAP system</span></span>
<span data-ttu-id="2e291-103">WCF クライアント クラスを生成した後は、WCF クライアント (インスタンス) の作成し、使用するメソッドの呼び出し、[!INCLUDE[adaptersap](../../includes/adaptersap-md.md)]します。</span><span class="sxs-lookup"><span data-stu-id="2e291-103">After you have generated the WCF client class, you can create a WCF client (instance) and invoke its methods to consume the [!INCLUDE[adaptersap](../../includes/adaptersap-md.md)].</span></span> <span data-ttu-id="2e291-104">操作のための WCF クライアント クラスとヘルパー コードを生成する方法についてを[!INCLUDE[adaptersap_short](../../includes/adaptersap-short-md.md)]公開を参照してください[WCF クライアントまたは SAP ソリューションの成果物の WCF サービス コントラクトを生成](../../adapters-and-accelerators/adapter-sap/generate-a-wcf-client-or-a-wcf-service-contract-for-sap-solution-artifacts.md)します。</span><span class="sxs-lookup"><span data-stu-id="2e291-104">For information about how to generate the WCF client class and helper code for operations that the [!INCLUDE[adaptersap_short](../../includes/adaptersap-short-md.md)] exposes, see [Generate a WCF client or a WCF service contract for SAP solution artifacts](../../adapters-and-accelerators/adapter-sap/generate-a-wcf-client-or-a-wcf-service-contract-for-sap-solution-artifacts.md).</span></span>  
  
 <span data-ttu-id="2e291-105">WCF クライアントを作成するには、エンドポイント アドレスとバインディングを指定する必要があります。</span><span class="sxs-lookup"><span data-stu-id="2e291-105">To create the WCF client, you must specify an endpoint address and a binding.</span></span> <span data-ttu-id="2e291-106">エンドポイント アドレスが有効な SAP 接続 URI を含める必要があり、バインドは、SAP バインドのインスタンスである必要があります (**SAPBinding**)。</span><span class="sxs-lookup"><span data-stu-id="2e291-106">The endpoint address must contain a valid SAP connection URI, and the binding must be an instance of an SAP Binding (**SAPBinding**).</span></span> <span data-ttu-id="2e291-107">SAP 接続 URI の詳細については、次を参照してください。 [SAP システム接続 URI の作成](../../adapters-and-accelerators/adapter-sap/create-the-sap-system-connection-uri.md)です。</span><span class="sxs-lookup"><span data-stu-id="2e291-107">For more information about the SAP connection URI, see [Create the SAP system connection URI](../../adapters-and-accelerators/adapter-sap/create-the-sap-system-connection-uri.md).</span></span>  
  
 <span data-ttu-id="2e291-108">コードまたは構成ファイルでは、SAP バインドとエンドポイント アドレスを指定できます。</span><span class="sxs-lookup"><span data-stu-id="2e291-108">You can specify the SAP Binding and the endpoint address in your code or in a configuration file.</span></span> <span data-ttu-id="2e291-109">使用すると、[!INCLUDE[addadapterservreflong](../../includes/addadapterservreflong-md.md)]プロジェクトの作成も構成ファイル (app.config) で WCF クライアント クラスを生成します。</span><span class="sxs-lookup"><span data-stu-id="2e291-109">When you use the [!INCLUDE[addadapterservreflong](../../includes/addadapterservreflong-md.md)] to generate the WCF client class, a configuration file (app.config) is also created for your project.</span></span> <span data-ttu-id="2e291-110">このファイルに情報を反映するバインドのプロパティと接続 (資格情報) を除くで SAP システムに接続するときに指定した構成設定が含まれています、[!INCLUDE[addadapterservrefshort](../../includes/addadapterservrefshort-md.md)]します。</span><span class="sxs-lookup"><span data-stu-id="2e291-110">This file contains configuration settings that reflect the binding properties and connection information (except credentials) that you specified when you connected to the SAP system with the [!INCLUDE[addadapterservrefshort](../../includes/addadapterservrefshort-md.md)].</span></span>  
  
## <a name="specifying-the-binding-and-endpoint-address-in-code"></a><span data-ttu-id="2e291-111">バインディングとエンドポイント アドレスを指定するコード</span><span class="sxs-lookup"><span data-stu-id="2e291-111">Specifying the Binding and Endpoint Address in Code</span></span>  
 <span data-ttu-id="2e291-112">次のコードでは、コードでバインディングとエンドポイント アドレスを指定することで、WCF クライアントを作成する方法を示します。</span><span class="sxs-lookup"><span data-stu-id="2e291-112">The following code shows how to create a WCF client by specifying the binding and endpoint address in code.</span></span> <span data-ttu-id="2e291-113">使用して、SAP システムの資格情報を指定することをお勧め、 **ClientCredentials**接続エンドポイントのアドレスの指定された URI ではなく、WCF クライアントのプロパティ。</span><span class="sxs-lookup"><span data-stu-id="2e291-113">It is good practice to specify the SAP system credentials by using the **ClientCredentials** property of the WCF client rather than in the connection URI supplied for the endpoint address.</span></span>  
  
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
  
## <a name="specifying-the-binding-and-endpoint-address-in-a-configuration-file"></a><span data-ttu-id="2e291-114">構成ファイルでバインディングとエンドポイント アドレスを指定します。</span><span class="sxs-lookup"><span data-stu-id="2e291-114">Specifying the Binding and Endpoint Address in a Configuration File</span></span>  
 <span data-ttu-id="2e291-115">次のコードでは、app.config ファイルでバインディングとエンドポイント アドレスを指定することで、WCF クライアントを作成する方法を示します。</span><span class="sxs-lookup"><span data-stu-id="2e291-115">The following code shows how to create a WCF client by specifying the binding and endpoint address in an app.config file.</span></span>  
  
```  
// A WCF client that targets an RFC is created  
// by specifying the client endpoint information in app.config  
RfcClient rfcClient = new RfcClient("SAPBinding_Rfc");  
  
rfcClient.ClientCredentials.UserName.UserName = "YourUserName";  
rfcClient.ClientCredentials.UserName.Password = "YourPassword";  
  
rfcClient.Open();  
```  
  
 <span data-ttu-id="2e291-116">次の XML は、EMP テーブルの作成、構成ファイル、[!INCLUDE[addadapterservrefshort](../../includes/addadapterservrefshort-md.md)]します。</span><span class="sxs-lookup"><span data-stu-id="2e291-116">The following XML shows the configuration file created for the EMP table by the [!INCLUDE[addadapterservrefshort](../../includes/addadapterservrefshort-md.md)].</span></span> <span data-ttu-id="2e291-117">このファイルには、前の例で参照されているクライアント エンドポイント構成が含まれています。</span><span class="sxs-lookup"><span data-stu-id="2e291-117">This file contains the client endpoint configuration referenced in the preceding example.</span></span>  
  
```  
<?xml version="1.0" encoding="utf-8"?>  
<configuration xmlns="http://schemas.microsoft.com/.NetConfiguration/v2.0">  
    <system.serviceModel>  
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
    </system.serviceModel>  
</configuration>  
```  
  
 <span data-ttu-id="2e291-118">プロジェクトには、複数の WCF クライアントがある場合があります複数のクライアント構成ファイルで定義されているエンドポイントのエントリ。</span><span class="sxs-lookup"><span data-stu-id="2e291-118">If a project has more than one WCF client, there will be multiple client endpoint entries defined in the configuration file.</span></span> <span data-ttu-id="2e291-119">WCF クライアントの各エントリは、バインド構成とターゲットの SAP システムのアイテム (Rfc、Trfc); などに基づいて一意の名前になりますたとえば、"SAPBinding_Rfc"です。</span><span class="sxs-lookup"><span data-stu-id="2e291-119">Each WCF client entry will have a unique name based on its binding configuration and target SAP system artifacts (such as Rfc and Trfc); for example, "SAPBinding_Rfc".</span></span> <span data-ttu-id="2e291-120">プロジェクトで、WCF クライアントを作成するための複数回を接続する場合は、複数のバインド構成エントリが作成されます、接続ごとに 1 つ。</span><span class="sxs-lookup"><span data-stu-id="2e291-120">If you connect multiple times to create the WCF clients in your project, multiple binding configuration entries will be created, one for each connection.</span></span> <span data-ttu-id="2e291-121">これらのバインド構成エントリは次の方法で名前が付けられます。SAPBinding1、SAPBinding2、しにします。</span><span class="sxs-lookup"><span data-stu-id="2e291-121">These binding configuration entries will be named in the following manner: SAPBinding1, SAPBinding2, and so on.</span></span> <span data-ttu-id="2e291-122">特定の接続中に作成される各クライアントのエンドポイント エントリは、その接続中に作成されたバインド エントリを参照します。</span><span class="sxs-lookup"><span data-stu-id="2e291-122">Each client endpoint entry created during a specific connection will reference the binding entry created during that connection.</span></span>  
  
> [!IMPORTANT]
>  <span data-ttu-id="2e291-123">[!INCLUDE[adaptersap_short](../../includes/adaptersap-short-md.md)]として、同じサービス コントラクトのさまざまなオペレーション (RFC、TRFC、IDOC など)、同じ種類の異なる SAP アイテムを表示します。</span><span class="sxs-lookup"><span data-stu-id="2e291-123">The [!INCLUDE[adaptersap_short](../../includes/adaptersap-short-md.md)] surfaces different SAP artifacts of the same type (such as RFC, TRFC, and IDOC) as different operations of the same service contract.</span></span> <span data-ttu-id="2e291-124">たとえば、2 つの異なる Rfc、RFC_EXAMPLE_A および RFC_EXAMPLE_B、両方が提示される同じサービス契約 ("Rfc")。</span><span class="sxs-lookup"><span data-stu-id="2e291-124">For example, two different RFCs, RFC_EXAMPLE_A and RFC_EXAMPLE_B, will both be surfaced under the same service contract ("Rfc").</span></span> <span data-ttu-id="2e291-125">これは、両方の Rfc を同じ WCF クライアント クラスによって呼び出されることを意味**RfcClient**と同じ名前空間の両方の Rfc パラメーターが宣言されます。</span><span class="sxs-lookup"><span data-stu-id="2e291-125">This means that both RFCs will be invoked by the same WCF client class, **RfcClient**, and that the parameters for both RFCs will be declared in the same namespace.</span></span> <span data-ttu-id="2e291-126">そのため、中に同じ両方 Rfc 用の WCF クライアントを生成する必要があります[!INCLUDE[addadapterservrefshort](../../includes/addadapterservrefshort-md.md)]ソリューションをビルドするときに、名前空間の競合の発生を回避するためにセッション (接続)。</span><span class="sxs-lookup"><span data-stu-id="2e291-126">Therefore, you must generate the WCF client for both RFCs during the same [!INCLUDE[addadapterservrefshort](../../includes/addadapterservrefshort-md.md)] session (connection) to avoid experiencing a namespace collision when you build your solution.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="2e291-127">参照</span><span class="sxs-lookup"><span data-stu-id="2e291-127">See Also</span></span>  
<span data-ttu-id="2e291-128">[WCF サービス モデルを使用して SAP アプリケーションを開発します。](../../adapters-and-accelerators/adapter-sap/develop-sap-applications-using-the-wcf-service-model.md) </span><span class="sxs-lookup"><span data-stu-id="2e291-128">[Develop SAP applications using the WCF Service Model](../../adapters-and-accelerators/adapter-sap/develop-sap-applications-using-the-wcf-service-model.md) </span></span>  
 <span data-ttu-id="2e291-129">[WCF クライアントまたは SAP ソリューションの成果物の WCF サービス コントラクトを生成します。](../../adapters-and-accelerators/adapter-sap/generate-a-wcf-client-or-a-wcf-service-contract-for-sap-solution-artifacts.md) </span><span class="sxs-lookup"><span data-stu-id="2e291-129">[Generate a WCF client or a WCF service contract for SAP solution artifacts](../../adapters-and-accelerators/adapter-sap/generate-a-wcf-client-or-a-wcf-service-contract-for-sap-solution-artifacts.md) </span></span>  
 [<span data-ttu-id="2e291-130">SAP システム接続 URI を作成します。</span><span class="sxs-lookup"><span data-stu-id="2e291-130">Create the SAP system connection URI</span></span>](../../adapters-and-accelerators/adapter-sap/create-the-sap-system-connection-uri.md)