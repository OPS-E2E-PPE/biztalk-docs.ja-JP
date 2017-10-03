---
title: "Oracle データベースへの接続を作成 |Microsoft ドキュメント"
ms.custom: 
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: 
ms.suite: 
ms.tgt_pltfrm: 
ms.topic: article
helpviewer_keywords: adapter, connecting to the Oracle Database
ms.assetid: 95f7905a-abad-4841-85c4-62cf0cc1e044
caps.latest.revision: "8"
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: 3f9a42994f0cde9df19e3b80e16fcbafbb2d8d5b
ms.sourcegitcommit: cb908c540d8f1a692d01dc8f313e16cb4b4e696d
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 09/20/2017
---
# <a name="create-a-connection-to-the-oracle-database"></a><span data-ttu-id="3ff1d-102">Oracle データベースへの接続を作成します。</span><span class="sxs-lookup"><span data-stu-id="3ff1d-102">Create a connection to the Oracle Database</span></span>
<span data-ttu-id="3ff1d-103">[!INCLUDE[adapteroracle](../../includes/adapteroracle-md.md)]は、[!INCLUDE[firstref_btsWinCommFoundation](../../includes/firstref-btswincommfoundation-md.md)]カスタム バインドします。</span><span class="sxs-lookup"><span data-stu-id="3ff1d-103">The [!INCLUDE[adapteroracle](../../includes/adapteroracle-md.md)] is a [!INCLUDE[firstref_btsWinCommFoundation](../../includes/firstref-btswincommfoundation-md.md)] custom binding.</span></span> <span data-ttu-id="3ff1d-104">そのため、WCF エンドポイントのアドレスを使用して、Oracle データベースへの通信を可能になります。</span><span class="sxs-lookup"><span data-stu-id="3ff1d-104">As such, it enables communication to an Oracle database through a WCF endpoint address.</span></span> <span data-ttu-id="3ff1d-105">WCF では、エンドポイント アドレス、通常表現されますとして、Uniform Resource Identifier ()、サービスのネットワークの場所を識別します。</span><span class="sxs-lookup"><span data-stu-id="3ff1d-105">In WCF, the endpoint address is typically expressed as a Uniform Resource Identifier (URI), which identifies the network location of the service.</span></span> <span data-ttu-id="3ff1d-106">[!INCLUDE[adapteroracle_short](../../includes/adapteroracle-short-md.md)]接続プロパティが含まれて、URI とは、この場所の表現を[!INCLUDE[adapteroracle_short](../../includes/adapteroracle-short-md.md)]Oracle データベースへの接続を確立するために使用します。</span><span class="sxs-lookup"><span data-stu-id="3ff1d-106">The [!INCLUDE[adapteroracle_short](../../includes/adapteroracle-short-md.md)] expresses this location as a connection URI, which contains properties that the [!INCLUDE[adapteroracle_short](../../includes/adapteroracle-short-md.md)] uses to establish a connection to the Oracle database.</span></span>  
  
 <span data-ttu-id="3ff1d-107">接続 URI を指定する必要がありますとします。</span><span class="sxs-lookup"><span data-stu-id="3ff1d-107">You must specify a connection URI when you:</span></span>  
  
-   <span data-ttu-id="3ff1d-108">チャネル ファクトリまたはを使用してチャネル リスナーを作成、[!INCLUDE[nextref_btsWinCommFoundation](../../includes/nextref-btswincommfoundation-md.md)]チャネル モデルまたはを使用して WCF クライアントまたはサービス ホストを作成する場合、[!INCLUDE[nextref_btsWinCommFoundation](../../includes/nextref-btswincommfoundation-md.md)]サービス モデル。</span><span class="sxs-lookup"><span data-stu-id="3ff1d-108">Create a channel factory or a channel listener using the [!INCLUDE[nextref_btsWinCommFoundation](../../includes/nextref-btswincommfoundation-md.md)] channel model or when you create a WCF client or service host using the [!INCLUDE[nextref_btsWinCommFoundation](../../includes/nextref-btswincommfoundation-md.md)] service model.</span></span>  
  
-   <span data-ttu-id="3ff1d-109">物理ポートのバインドを作成、[!INCLUDE[btsBizTalkServerNoVersion](../../includes/btsbiztalkservernoversion-md.md)]ソリューションです。</span><span class="sxs-lookup"><span data-stu-id="3ff1d-109">Create a physical port binding in a [!INCLUDE[btsBizTalkServerNoVersion](../../includes/btsbiztalkservernoversion-md.md)] solution.</span></span>  
  
-   <span data-ttu-id="3ff1d-110">使用して、 [!INCLUDE[addadapterservreflong](../../includes/addadapterservreflong-md.md)] 、WCF クライアント クラスまたは WCF サービス インターフェイスを生成する、[!INCLUDE[nextref_btsWinCommFoundation](../../includes/nextref-btswincommfoundation-md.md)]モデル ソリューションのサービスを提供します。</span><span class="sxs-lookup"><span data-stu-id="3ff1d-110">Use the [!INCLUDE[addadapterservreflong](../../includes/addadapterservreflong-md.md)] to generate a WCF client class or WCF service interface for a [!INCLUDE[nextref_btsWinCommFoundation](../../includes/nextref-btswincommfoundation-md.md)] service model solution.</span></span>  
  
-   <span data-ttu-id="3ff1d-111">使用して、[!INCLUDE[consumeadapterservlong](../../includes/consumeadapterservlong-md.md)]からのメッセージ スキーマを取得する、[!INCLUDE[adapteroracle_short](../../includes/adapteroracle-short-md.md)]の[!INCLUDE[btsBizTalkServerNoVersion](../../includes/btsbiztalkservernoversion-md.md)]ソリューションです。</span><span class="sxs-lookup"><span data-stu-id="3ff1d-111">Use the [!INCLUDE[consumeadapterservlong](../../includes/consumeadapterservlong-md.md)] to retrieve message schemas from the [!INCLUDE[adapteroracle_short](../../includes/adapteroracle-short-md.md)] for a [!INCLUDE[btsBizTalkServerNoVersion](../../includes/btsbiztalkservernoversion-md.md)] solution.</span></span>  
  
-   <span data-ttu-id="3ff1d-112">ServiceModel メタデータ ユーティリティ ツール (svcutil.exe) を使用して、WCF クライアント クラスまたは WCF サービスのモデル ソリューションの WCF サービスのインターフェイスを生成します。</span><span class="sxs-lookup"><span data-stu-id="3ff1d-112">Use the ServiceModel Metadata Utility tool (svcutil.exe) to generate a WCF client class or WCF service interface for a WCF service model solution.</span></span>  
  
 <span data-ttu-id="3ff1d-113">[!INCLUDE[adapteroracle_short](../../includes/adapteroracle-short-md.md)] Oracle データベースへの接続を確立するための 2 つの方法をサポートしています。</span><span class="sxs-lookup"><span data-stu-id="3ff1d-113">The [!INCLUDE[adapteroracle_short](../../includes/adapteroracle-short-md.md)] supports two ways of establishing a connection to the Oracle database:</span></span>  
  
-   <span data-ttu-id="3ff1d-114">**Tnsnames.ora を使用して**です。</span><span class="sxs-lookup"><span data-stu-id="3ff1d-114">**Using tnsnames.ora**.</span></span> <span data-ttu-id="3ff1d-115">この方法では、アダプター クライアントによって提供される URI の接続には、tnsnames.ora ファイルで指定された net サービス名のみが含まれています。</span><span class="sxs-lookup"><span data-stu-id="3ff1d-115">In this approach, the connection URI provided by the adapter client contains only the net service name specified in the tnsnames.ora file.</span></span> <span data-ttu-id="3ff1d-116">アダプターは、サーバー名、サービス名、ポートなしなどに、接続パラメーターを抽出、net サービス名のエントリ、ファイルからなどです。</span><span class="sxs-lookup"><span data-stu-id="3ff1d-116">The adapter extracts the connection parameters such as server name, service name, port no, etc. from the net service name entry in the file.</span></span> <span data-ttu-id="3ff1d-117">このアプローチを使用するのには、tnsnames.ora ファイルに、Oracle データベースの net サービス名を含める、Oracle クライアントを実行しているコンピューターを構成しなければなりません。</span><span class="sxs-lookup"><span data-stu-id="3ff1d-117">To use this approach, the computer running the Oracle client must be configured to include the net service name for the Oracle database in the tnsnames.ora file.</span></span>  
  
    > [!IMPORTANT]
    >  <span data-ttu-id="3ff1d-118">Oracle クライアントの制限により、 **DataSourceName**パラメーター (net サービス名) で、 [Oracle Database 接続 URI を作成する](../../adapters-and-accelerators/adapter-oracle-database/create-the-oracle-database-connection-uri.md)を実行する場合、複数の 39 文字を含めることはできませんトランザクションで操作します。</span><span class="sxs-lookup"><span data-stu-id="3ff1d-118">Due to an Oracle Client limitation, the **DataSourceName** parameter (net service name) in the [Create the Oracle Database connection URI](../../adapters-and-accelerators/adapter-oracle-database/create-the-oracle-database-connection-uri.md) cannot contain more than 39 characters if you are performing operations in a transaction.</span></span> <span data-ttu-id="3ff1d-119">したがっての値が指定されていることを確認してください、 **DataSourceName**パラメーターは 39 文字以下のトランザクションで操作を実行する場合。</span><span class="sxs-lookup"><span data-stu-id="3ff1d-119">Therefore, make sure that the value specified for the **DataSourceName** parameter is less than or equal to 39 characters if you will be performing operations in a transaction.</span></span>  
  
-   <span data-ttu-id="3ff1d-120">**Tnsnames.ora を使用せず**です。</span><span class="sxs-lookup"><span data-stu-id="3ff1d-120">**Without using tnsnames.ora**.</span></span> <span data-ttu-id="3ff1d-121">この方法では、アダプターのクライアントは、接続 URI の直接接続パラメーターを指定します。</span><span class="sxs-lookup"><span data-stu-id="3ff1d-121">In this approach, the adapter clients specify the connection parameters directly in the connection URI.</span></span> <span data-ttu-id="3ff1d-122">これは、操作では、tnsnames.ora ファイル、クライアント コンピューター上に存在する net サービス名は必要ありません。</span><span class="sxs-lookup"><span data-stu-id="3ff1d-122">This does not require the net service name to be present in the tnsnames.ora file on the client computer.</span></span> <span data-ttu-id="3ff1d-123">クライアント コンピューターに存在している tnsname.ora ファイルが、この方法でもは必要はありません。</span><span class="sxs-lookup"><span data-stu-id="3ff1d-123">This approach does not even require the tnsname.ora file to be present on the client computer.</span></span>  
  
    > [!IMPORTANT]
    >  <span data-ttu-id="3ff1d-124">トランザクションで操作を実行している場合、この接続のモードがサポートされていません。</span><span class="sxs-lookup"><span data-stu-id="3ff1d-124">This mode of connectivity is not supported if you are performing operations in a transaction.</span></span> <span data-ttu-id="3ff1d-125">これは、Oracle クライアントの制限によるものです。</span><span class="sxs-lookup"><span data-stu-id="3ff1d-125">This is due to a limitation of Oracle Client.</span></span>  
  
 <span data-ttu-id="3ff1d-126">このセクションのトピックでは、間の接続を確立する方法を記述、[!INCLUDE[adapteroracle](../../includes/adapteroracle-md.md)]と使用することによって Oracle データベース。</span><span class="sxs-lookup"><span data-stu-id="3ff1d-126">The topics in this section describe how to establish a connection between the [!INCLUDE[adapteroracle](../../includes/adapteroracle-md.md)] and the Oracle database by providing you with:</span></span>  
  
-   <span data-ttu-id="3ff1d-127">Oracle クライアントの構成に関する情報。</span><span class="sxs-lookup"><span data-stu-id="3ff1d-127">Information about configuring the Oracle client.</span></span>  
  
-   <span data-ttu-id="3ff1d-128">接続のプロパティと、Oracle の接続 URI の構造に関する情報。</span><span class="sxs-lookup"><span data-stu-id="3ff1d-128">Information about the connection properties and the structure of the Oracle connection URI.</span></span>  
  
-   <span data-ttu-id="3ff1d-129">使用して接続を確立する方法を説明するトピックへのリンク、[!INCLUDE[adapteroracle_short](../../includes/adapteroracle-short-md.md)]です。</span><span class="sxs-lookup"><span data-stu-id="3ff1d-129">Links to topics that show how to establish a connection by using the [!INCLUDE[adapteroracle_short](../../includes/adapteroracle-short-md.md)].</span></span>  
  
-   <span data-ttu-id="3ff1d-130">Windows 認証を使用して Oracle データベースへの接続に関する情報。</span><span class="sxs-lookup"><span data-stu-id="3ff1d-130">Information about connecting to the Oracle database using Windows Authentication.</span></span>  
  
## <a name="in-this-section"></a><span data-ttu-id="3ff1d-131">このセクションの内容</span><span class="sxs-lookup"><span data-stu-id="3ff1d-131">In This Section</span></span>  
  
-   [<span data-ttu-id="3ff1d-132">Oracle データベース アダプターの Oracle クライアントを構成します。</span><span class="sxs-lookup"><span data-stu-id="3ff1d-132">Configure the Oracle Client for the Oracle Database adapter</span></span>](../../adapters-and-accelerators/adapter-oracle-database/configure-the-oracle-client-for-the-oracle-database-adapter.md)  
  
-   [<span data-ttu-id="3ff1d-133">Oracle Database 接続 URI を作成します。</span><span class="sxs-lookup"><span data-stu-id="3ff1d-133">Create the Oracle Database connection URI</span></span>](../../adapters-and-accelerators/adapter-oracle-database/create-the-oracle-database-connection-uri.md)  
  
-   [<span data-ttu-id="3ff1d-134">Windows 認証を使用して Oracle データベースへの接続します。</span><span class="sxs-lookup"><span data-stu-id="3ff1d-134">Connect to the Oracle Database Using Windows Authentication</span></span>](../../adapters-and-accelerators/adapter-oracle-database/connect-to-the-oracle-database-using-windows-authentication.md)  
  
## <a name="see-also"></a><span data-ttu-id="3ff1d-135">参照</span><span class="sxs-lookup"><span data-stu-id="3ff1d-135">See Also</span></span>  
[<span data-ttu-id="3ff1d-136">Oracle データベース アプリケーションを開発します。</span><span class="sxs-lookup"><span data-stu-id="3ff1d-136">Develop your Oracle Database applications</span></span>](../../adapters-and-accelerators/adapter-oracle-database/develop-your-oracle-database-applications.md)