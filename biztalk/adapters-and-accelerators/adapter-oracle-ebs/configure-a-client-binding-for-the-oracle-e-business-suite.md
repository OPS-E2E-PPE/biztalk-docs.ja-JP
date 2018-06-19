---
title: Oracle E-business Suite のバインド、クライアントの構成 |Microsoft ドキュメント
ms.custom: ''
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: ''
ms.suite: ''
ms.tgt_pltfrm: ''
ms.topic: article
ms.assetid: 1347cbca-5567-43f8-a75e-a23b108692bc
caps.latest.revision: 11
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: 6a1f3eafdf423926dab4cf48efae8db3044aba9b
ms.sourcegitcommit: 5abd0ed3f9e4858ffaaec5481bfa8878595e95f7
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 11/28/2017
ms.locfileid: "25962592"
---
# <a name="configure-a-client-binding-for-the-oracle-e-business-suite"></a><span data-ttu-id="81e0f-102">Oracle E-business Suite のバインド、クライアントを構成します。</span><span class="sxs-lookup"><span data-stu-id="81e0f-102">Configure a client binding for the Oracle E-Business Suite</span></span>
<span data-ttu-id="81e0f-103">WCF クライアント クラスを生成した後を WCF クライアント (インスタンス) を作成し、使用するには、そのメソッドを呼び出す、[!INCLUDE[adapteroraclebusinessshort](../../includes/adapteroraclebusinessshort-md.md)]です。</span><span class="sxs-lookup"><span data-stu-id="81e0f-103">After you have generated the WCF client class, you can create a WCF client (instance) and invoke its methods to consume the [!INCLUDE[adapteroraclebusinessshort](../../includes/adapteroraclebusinessshort-md.md)].</span></span>  
  
 <span data-ttu-id="81e0f-104">WCF クライアントを作成するには、エンドポイント アドレスとバインディングを指定する必要があります。</span><span class="sxs-lookup"><span data-stu-id="81e0f-104">To create the WCF client, you must specify an endpoint address and a binding.</span></span> <span data-ttu-id="81e0f-105">エンドポイントのアドレスは有効な Oracle E-business Suite 接続 URI を含める必要があり、バインディングは、Oracle E-business Suite バインドのインスタンスである必要があります (**OracleEBSBinding**)。</span><span class="sxs-lookup"><span data-stu-id="81e0f-105">The endpoint address must contain a valid Oracle E-Business Suite connection URI, and the binding must be an instance of an Oracle E-Business Suite binding (**OracleEBSBinding**).</span></span> <span data-ttu-id="81e0f-106">Oracle E-business Suite 接続 URI の詳細については、次を参照してください。 [Oracle E-business Suite への接続を作成する](../../adapters-and-accelerators/adapter-oracle-ebs/create-a-connection-to-oracle-e-business-suite.md)です。</span><span class="sxs-lookup"><span data-stu-id="81e0f-106">For more information about the Oracle E-Business Suite connection URI, see [Create a Connection to the Oracle E-Business Suite](../../adapters-and-accelerators/adapter-oracle-ebs/create-a-connection-to-oracle-e-business-suite.md).</span></span> <span data-ttu-id="81e0f-107">接続 URI の一部としてユーザーの資格情報を指定されていないことをお勧めします。</span><span class="sxs-lookup"><span data-stu-id="81e0f-107">We recommend that you do not specify the user credentials as part of the connection URI.</span></span> <span data-ttu-id="81e0f-108">代わりに使用することは、 **ClientCredentials**このトピックで説明したように、WCF クライアントのプロパティです。</span><span class="sxs-lookup"><span data-stu-id="81e0f-108">You may instead use the **ClientCredentials** property of the WCF client, as explained in this topic.</span></span>  
  
 <span data-ttu-id="81e0f-109">コードまたは構成ファイルでは、Oracle E-business Suite バインドとエンドポイント アドレスを指定できます。</span><span class="sxs-lookup"><span data-stu-id="81e0f-109">You can specify the Oracle E-Business Suite binding and the endpoint address in your code or in a configuration file.</span></span> <span data-ttu-id="81e0f-110">使用すると、[!INCLUDE[addadapterservreflong](../../includes/addadapterservreflong-md.md)]プロジェクトの作成も構成ファイル (app.config) で WCF クライアント クラスを生成します。</span><span class="sxs-lookup"><span data-stu-id="81e0f-110">When you use the [!INCLUDE[addadapterservreflong](../../includes/addadapterservreflong-md.md)] to generate the WCF client class, a configuration file (app.config) is also created for your project.</span></span> <span data-ttu-id="81e0f-111">このファイルには、バインドのプロパティおよび接続情報 (資格情報) を除くと Oracle E-business Suite に接続されているときに指定したを反映する構成設定が含まれています、[!INCLUDE[addadapterservrefshort](../../includes/addadapterservrefshort-md.md)]です。</span><span class="sxs-lookup"><span data-stu-id="81e0f-111">This file contains configuration settings that reflect the binding properties and connection information (except credentials) that you specified when you connected to the Oracle E-Business Suite with the [!INCLUDE[addadapterservrefshort](../../includes/addadapterservrefshort-md.md)].</span></span>  
  
## <a name="specifying-the-binding-and-endpoint-address-in-code"></a><span data-ttu-id="81e0f-112">コードでのバインディングとエンドポイント アドレスの指定</span><span class="sxs-lookup"><span data-stu-id="81e0f-112">Specifying the Binding and Endpoint Address in Code</span></span>  
 <span data-ttu-id="81e0f-113">次のコードを使用してコード内のバインドとエンドポイント アドレスを指定することによって、WCF クライアントを作成する方法を示しています、 **ClientCredentials** WCF クライアントのプロパティです。</span><span class="sxs-lookup"><span data-stu-id="81e0f-113">The following code shows how to create a WCF client by specifying the binding and endpoint address in code using the **ClientCredentials** property of the WCF client.</span></span>  
  
```  
//Create an Oracle EBS binding and set the binding properties  
OracleEBSBinding binding = new OracleEBSBinding();  
binding.OracleUserName = "myOracleEBSUser";  
binding.OraclePassword = "myOracleEBSPassword";  
binding.OracleEBSResponsibilityName = "Responsibility";  
binding.OracleEBSOrganizationId = "204";  
  
//Create the client endpoint   
EndpointAddress address = new EndpointAddress("oracleebs://<oracleebs_instance_name>/");  
  
//Create the client and specify the credentials  
ConcurrentPrograms_ARClient client = new ConcurrentPrograms_ARClient(binding,address);  
client.ClientCredentials.UserName.UserName = "myuser";  
client.ClientCredentials.UserName.Password = "mypassword";  
  
//Open the client  
client.Open();  
```  
  
## <a name="specifying-the-binding-and-endpoint-address-in-a-configuration-file"></a><span data-ttu-id="81e0f-114">構成ファイルでのバインディングとエンドポイント アドレスの指定</span><span class="sxs-lookup"><span data-stu-id="81e0f-114">Specifying the Binding and Endpoint Address in a Configuration File</span></span>  
 <span data-ttu-id="81e0f-115">次のコードでは、app.config ファイルでバインディングとエンドポイント アドレスを指定して、WCF クライアントを作成する方法を示します。</span><span class="sxs-lookup"><span data-stu-id="81e0f-115">The following code shows how to create a WCF client by specifying the binding and endpoint address in an app.config file.</span></span>  
  
```  
//Create the client by specifying the endpoint name in the app.config. In this case, the binding properties  
//must also be specified in the app.config.  
ConcurrentPrograms_ARClient client = new ConcurrentPrograms_ARClient("OracleEBSBinding_ConcurrentPrograms_AR");  
  
//Specify the credentials   
client.ClientCredentials.UserName.UserName = "myuser";  
client.ClientCredentials.UserName.Password = "mypassword";  
  
client.Open();  
```  
  
 <span data-ttu-id="81e0f-116">次の XML の作成、構成ファイルを示しています、**顧客インターフェイス**によって同時実行プログラム、[!INCLUDE[addadapterservrefshort](../../includes/addadapterservrefshort-md.md)]です。</span><span class="sxs-lookup"><span data-stu-id="81e0f-116">The following XML shows the configuration file created for the **Customer Interface** concurrent program by the [!INCLUDE[addadapterservrefshort](../../includes/addadapterservrefshort-md.md)].</span></span> <span data-ttu-id="81e0f-117">このファイルには、前の例で参照されているクライアント エンドポイント構成が含まれています。</span><span class="sxs-lookup"><span data-stu-id="81e0f-117">This file contains the client endpoint configuration referenced in the preceding example.</span></span>  
  
```  
<?xml version="1.0" encoding="utf-8"?>  
<configuration xmlns="http://schemas.microsoft.com/.NetConfiguration/v2.0">  
    <system.serviceModel>  
        <bindings>  
            <oracleEBSBinding>  
                <binding openTimeout="00:05:00" name="OracleEBSBinding" closeTimeout="00:01:00"  
                    receiveTimeout="00:10:00" sendTimeout="00:01:00" clientCredentialType="Database"  
                    inboundOperationType="Polling" metadataPooling="true" statementCachePurge="false"  
                    statementCacheSize="10" pollWhileDataFound="false" pollingInterval="30"  
                    useOracleConnectionPool="true" minPoolSize="1" maxPoolSize="100"  
                    incrPoolSize="5" decrPoolSize="1" connectionLifetime="0" acceptCredentialsInUri="false"  
                    useAmbientTransaction="true" notifyOnListenerStart="true"  
                    notificationPort="-1" dataFetchSize="65536" longDatatypeColumnSize="32512"  
                    skipNilNodes="true" maxOutputAssociativeArrayElements="32"  
                    enableSafeTyping="false" insertBatchSize="20" useSchemaInNameSpace="true"  
                    enableBizTalkCompatibilityMode="true">  
                    <mlsSettings language="" dateFormat="" dateLanguage="" numericCharacters=""  
                        sort="" territory="" comparison="" currency="" dualCurrency=""  
                        iSOCurrency="" calendar="" lengthSemantics="" nCharConversionException="true"  
                        timeStampFormat="" timeStampTZFormat="" timeZone="" />  
                </binding>  
            </oracleEBSBinding>  
        </bindings>  
        <client>  
            <endpoint address="oracleebs://ebs-70-12/" binding="oracleEBSBinding"  
                bindingConfiguration="OracleEBSBinding" contract="ConcurrentPrograms_AR"  
                name="OracleEBSBinding_ConcurrentPrograms_AR" />  
        </client>  
    </system.serviceModel>  
</configuration>  
```  
  
 <span data-ttu-id="81e0f-118">プロジェクトに複数の WCF クライアントがある場合があります複数のクライアント構成ファイルで定義されているエンドポイント エントリ。</span><span class="sxs-lookup"><span data-stu-id="81e0f-118">If a project has more than one WCF client, there will be multiple client endpoint entries defined in the configuration file.</span></span> <span data-ttu-id="81e0f-119">WCF クライアントの各エントリには、バインド構成とターゲット Oracle E-business Suite の成果物に基づき、一意の名前があります。</span><span class="sxs-lookup"><span data-stu-id="81e0f-119">Each WCF client entry will have a unique name based on its binding configuration and target Oracle E-Business Suite artifact.</span></span> <span data-ttu-id="81e0f-120">場合は、プロジェクトで、WCF クライアントを作成する複数回接続すると、複数のバインド構成エントリが作成接続ごとに 1 つです。</span><span class="sxs-lookup"><span data-stu-id="81e0f-120">If you connect multiple times to create the WCF clients in your project, multiple binding configuration entries will be created, one for each connection.</span></span> <span data-ttu-id="81e0f-121">これらのバインディングの構成エントリの名前は次のようになります: OracleEBSBinding、OracleEBSBinding1 などです。</span><span class="sxs-lookup"><span data-stu-id="81e0f-121">These binding configuration entries will be named in the following manner: OracleEBSBinding, OracleEBSBinding1, and so on.</span></span> <span data-ttu-id="81e0f-122">特定の接続中に作成される各クライアント エンドポイント エントリでは、その接続中に作成されたバインド エントリを参照します。</span><span class="sxs-lookup"><span data-stu-id="81e0f-122">Each client endpoint entry created during a specific connection will reference the binding entry created during that connection.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="81e0f-123">参照</span><span class="sxs-lookup"><span data-stu-id="81e0f-123">See Also</span></span>  
 [<span data-ttu-id="81e0f-124">WCF サービス モデルを使用して Oracle E-business Suite アプリケーションの開発します。</span><span class="sxs-lookup"><span data-stu-id="81e0f-124">Develop Oracle E-Business Suite Applications using the WCF Service Model</span></span>](../../adapters-and-accelerators/adapter-oracle-ebs/develop-oracle-e-business-suite-applications-using-the-wcf-service-model.md)