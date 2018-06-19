---
title: Microsoft BizTalk Adapter for SQL Server - 2013 R2 と 2013 インストール |Microsoft ドキュメント
ms.custom: ''
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: ''
ms.suite: ''
ms.tgt_pltfrm: ''
ms.topic: article
ms.assetid: 56c31d0d-783b-41ee-8265-56c9547e9dca
caps.latest.revision: 31
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: af91ae787d5800738865980609bb86f96a73bfb8
ms.sourcegitcommit: 5abd0ed3f9e4858ffaaec5481bfa8878595e95f7
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 11/28/2017
ms.locfileid: "25967864"
---
# <a name="install-microsoft-biztalk-adapter-for-sql-server---2013-r2-and-2013"></a><span data-ttu-id="3397d-102">Microsoft BizTalk Adapter for SQL Server - 2013 R2 と 2013 インストールします。</span><span class="sxs-lookup"><span data-stu-id="3397d-102">Install Microsoft BizTalk Adapter for SQL Server - 2013 R2 and 2013</span></span>
<span data-ttu-id="3397d-103">インストール、[!INCLUDE[adaptersql_md](../../includes/adaptersql-md.md)]に含まれている[!INCLUDE[bts2013r2_md](../../includes/bts2013r2-md.md)]、またはに付属[!INCLUDE[btsBizTalkServerNoVersion](../../includes/btsbiztalkservernoversion-md.md)]2013。</span><span class="sxs-lookup"><span data-stu-id="3397d-103">Install the [!INCLUDE[adaptersql_md](../../includes/adaptersql-md.md)] included with [!INCLUDE[bts2013r2_md](../../includes/bts2013r2-md.md)], or included with [!INCLUDE[btsBizTalkServerNoVersion](../../includes/btsbiztalkservernoversion-md.md)] 2013.</span></span>

 <span data-ttu-id="3397d-104">[!INCLUDE[adaptersqlshort](../../includes/adaptersqlshort-md.md)]で使用できます。</span><span class="sxs-lookup"><span data-stu-id="3397d-104">The [!INCLUDE[adaptersqlshort](../../includes/adaptersqlshort-md.md)] can be used with:</span></span>  
  
-   <span data-ttu-id="3397d-105">.NET アプリケーション</span><span class="sxs-lookup"><span data-stu-id="3397d-105">A .NET application</span></span>  
  
-   <span data-ttu-id="3397d-106">Microsoft [!INCLUDE[btsBizTalkServerNoVersion](../../includes/btsbiztalkservernoversion-md.md)]</span><span class="sxs-lookup"><span data-stu-id="3397d-106">Microsoft [!INCLUDE[btsBizTalkServerNoVersion](../../includes/btsbiztalkservernoversion-md.md)]</span></span>  
  
 <span data-ttu-id="3397d-107">アダプターを使用する方法に基づき、必要なソフトウェアによって異なります。</span><span class="sxs-lookup"><span data-stu-id="3397d-107">Based on how you use the adapters, the required software varies.</span></span>  
 
<a name="BKMK_Prereqs_NET"></a>   
## <a name="prerequisites-when-using-the-adapter-with-a-net-application"></a><span data-ttu-id="3397d-108">.NET アプリケーションで、アダプターを使用する場合の前提条件</span><span class="sxs-lookup"><span data-stu-id="3397d-108">Prerequisites when using the adapter with a .NET Application</span></span>  
<span data-ttu-id="3397d-109">次のソフトウェアを使用する .NET アプリケーションを作成するコンピューターにインストール、[!INCLUDE[adaptersqlshort](../../includes/adaptersqlshort-md.md)]です。</span><span class="sxs-lookup"><span data-stu-id="3397d-109">Install the following software on the computer where you are writing .NET applications that consume the [!INCLUDE[adaptersqlshort](../../includes/adaptersqlshort-md.md)].</span></span> <span data-ttu-id="3397d-110">示されている順序で、ソフトウェアをインストールします。</span><span class="sxs-lookup"><span data-stu-id="3397d-110">Install the software in the order as listed.</span></span>  

|<span data-ttu-id="3397d-111">2013 R2</span><span class="sxs-lookup"><span data-stu-id="3397d-111">2013 R2</span></span>|<span data-ttu-id="3397d-112">2013</span><span class="sxs-lookup"><span data-stu-id="3397d-112">2013</span></span>|  
|---|---|  
|[!INCLUDE[dotnet451](../../includes/dotnet451-md.md)]|<span data-ttu-id="3397d-113">Microsoft [!INCLUDE[dotnet45](../../includes/dotnet45-md.md)]</span><span class="sxs-lookup"><span data-stu-id="3397d-113">Microsoft [!INCLUDE[dotnet45](../../includes/dotnet45-md.md)]</span></span>|  
|<span data-ttu-id="3397d-114">Visual Studio 2013</span><span class="sxs-lookup"><span data-stu-id="3397d-114">Visual Studio 2013</span></span>|<span data-ttu-id="3397d-115">Visual Studio 2012</span><span class="sxs-lookup"><span data-stu-id="3397d-115">Visual Studio 2012</span></span>|  
|[!INCLUDE[afproductnameshort](../../includes/afproductnameshort-md.md)]|[!INCLUDE[afproductnameshort](../../includes/afproductnameshort-md.md)]|  
|<span data-ttu-id="3397d-116">SQL Server のクライアント ライブラリです。</span><span class="sxs-lookup"><span data-stu-id="3397d-116">The SQL Server client libraries.</span></span> <span data-ttu-id="3397d-117">のインスタンスにアクセスするたびに SQL Server ログインを指定する必要はありません。</span><span class="sxs-lookup"><span data-stu-id="3397d-117">.</span></span>|<span data-ttu-id="3397d-118">SQL Server クライアント ライブラリで.</span><span class="sxs-lookup"><span data-stu-id="3397d-118">The SQL Server client libraries..</span></span>|  

<a name="BKMK_Prereqs_BTS"></a>    
## <a name="prerequisites-when-using-the-adapter-with-biztalk-server"></a><span data-ttu-id="3397d-119">BizTalk Server でアダプターを使用する場合の前提条件</span><span class="sxs-lookup"><span data-stu-id="3397d-119">Prerequisites when using the adapter with BizTalk Server</span></span>  
<span data-ttu-id="3397d-120">次のソフトウェアを使用するコンピューターにインストール、[!INCLUDE[adaptersqlshort](../../includes/adaptersqlshort-md.md)]で[!INCLUDE[btsBizTalkServerNoVersion](../../includes/btsbiztalkservernoversion-md.md)]です。</span><span class="sxs-lookup"><span data-stu-id="3397d-120">Install the following software on the computer where you will be using the [!INCLUDE[adaptersqlshort](../../includes/adaptersqlshort-md.md)] with [!INCLUDE[btsBizTalkServerNoVersion](../../includes/btsbiztalkservernoversion-md.md)].</span></span> <span data-ttu-id="3397d-121">ここで示すように同じ順序でソフトウェアをインストールすることをお勧めします。</span><span class="sxs-lookup"><span data-stu-id="3397d-121">We recommend installing the software in the same order as listed here.</span></span>  
 
 |<span data-ttu-id="3397d-122">2013 R2</span><span class="sxs-lookup"><span data-stu-id="3397d-122">2013 R2</span></span>|<span data-ttu-id="3397d-123">2013</span><span class="sxs-lookup"><span data-stu-id="3397d-123">2013</span></span>|  
|---|---|  
|[!INCLUDE[dotnet451](../../includes/dotnet451-md.md)]|<span data-ttu-id="3397d-124">Microsoft [!INCLUDE[dotnet45](../../includes/dotnet45-md.md)]</span><span class="sxs-lookup"><span data-stu-id="3397d-124">Microsoft [!INCLUDE[dotnet45](../../includes/dotnet45-md.md)]</span></span>|  
|<span data-ttu-id="3397d-125">Visual Studio 2013</span><span class="sxs-lookup"><span data-stu-id="3397d-125">Visual Studio 2013</span></span>|<span data-ttu-id="3397d-126">Visual Studio 2012</span><span class="sxs-lookup"><span data-stu-id="3397d-126">Visual Studio 2012</span></span>|  
|[!INCLUDE[afproductnameshort](../../includes/afproductnameshort-md.md)]<br /><br /> <span data-ttu-id="3397d-127">インストール、[!INCLUDE[consumeadapterservlong](../../includes/consumeadapterservlong-md.md)]の[!INCLUDE[btsVStudioNoVersion](../../includes/btsvstudionoversion-md.md)]に含まれている、[!INCLUDE[afproductnameshort](../../includes/afproductnameshort-md.md)]です。</span><span class="sxs-lookup"><span data-stu-id="3397d-127">Install the [!INCLUDE[consumeadapterservlong](../../includes/consumeadapterservlong-md.md)] for [!INCLUDE[btsVStudioNoVersion](../../includes/btsvstudionoversion-md.md)] included with the [!INCLUDE[afproductnameshort](../../includes/afproductnameshort-md.md)].</span></span> <span data-ttu-id="3397d-128">インストールするには、**カスタム**(選択**BizTalk Server アドイン**) または**完了**のインストール、[!INCLUDE[afproductnameshort](../../includes/afproductnameshort-md.md)]です。</span><span class="sxs-lookup"><span data-stu-id="3397d-128">To install, do a **Custom** (select **BizTalk Server Addin**) or **Complete** installation of the [!INCLUDE[afproductnameshort](../../includes/afproductnameshort-md.md)].</span></span>|[!INCLUDE[afproductnameshort](../../includes/afproductnameshort-md.md)]<br /><br /> <span data-ttu-id="3397d-129">インストール、[!INCLUDE[consumeadapterservlong](../../includes/consumeadapterservlong-md.md)]の[!INCLUDE[btsVStudioNoVersion](../../includes/btsvstudionoversion-md.md)]に含まれている、[!INCLUDE[afproductnameshort](../../includes/afproductnameshort-md.md)]です。</span><span class="sxs-lookup"><span data-stu-id="3397d-129">Install the [!INCLUDE[consumeadapterservlong](../../includes/consumeadapterservlong-md.md)] for [!INCLUDE[btsVStudioNoVersion](../../includes/btsvstudionoversion-md.md)] included with the [!INCLUDE[afproductnameshort](../../includes/afproductnameshort-md.md)].</span></span> <span data-ttu-id="3397d-130">インストールするには、**カスタム**(選択**BizTalk Server アドイン**) または**完了**のインストール、[!INCLUDE[afproductnameshort](../../includes/afproductnameshort-md.md)]です。</span><span class="sxs-lookup"><span data-stu-id="3397d-130">To install, do a **Custom** (select **BizTalk Server Addin**) or **Complete** installation of the [!INCLUDE[afproductnameshort](../../includes/afproductnameshort-md.md)].</span></span>|  
|<span data-ttu-id="3397d-131">BizTalk Server 2013 R2</span><span class="sxs-lookup"><span data-stu-id="3397d-131">BizTalk Server 2013 R2</span></span>|<span data-ttu-id="3397d-132">BizTalk Server 2013</span><span class="sxs-lookup"><span data-stu-id="3397d-132">BizTalk Server 2013</span></span>|  
|<span data-ttu-id="3397d-133">SQL Server のクライアント ライブラリです。</span><span class="sxs-lookup"><span data-stu-id="3397d-133">The SQL Server client libraries.</span></span> |<span data-ttu-id="3397d-134">SQL Server のクライアント ライブラリです。</span><span class="sxs-lookup"><span data-stu-id="3397d-134">The SQL Server client libraries.</span></span> |  

<a name="BKMK_SuppLOB"></a>   
## <a name="supported-sql-server-versions-and-client-libraries"></a><span data-ttu-id="3397d-135">サポートされている SQL Server のバージョンとクライアント ライブラリ</span><span class="sxs-lookup"><span data-stu-id="3397d-135">Supported SQL Server versions and client libraries</span></span>  
 <span data-ttu-id="3397d-136">次のセクションではサポートされている SQL Server のバージョンと、クライアントで必要なライブラリ、[!INCLUDE[adaptersqlshort](../../includes/adaptersqlshort-md.md)]です。</span><span class="sxs-lookup"><span data-stu-id="3397d-136">The following section presents the supported SQL Server versions and the client libraries required by the [!INCLUDE[adaptersqlshort](../../includes/adaptersqlshort-md.md)].</span></span>  
  
-   <span data-ttu-id="3397d-137">**サポートされているサーバー バージョン**: SQL Server 2005、SQL Server 2008 SP1、SQL Server 2008 R2、SQL Server 2012</span><span class="sxs-lookup"><span data-stu-id="3397d-137">**Supported server versions**: SQL Server 2005, SQL Server 2008 SP1, SQL Server 2008 R2, SQL Server 2012</span></span>  
  
-   <span data-ttu-id="3397d-138">**サポートされているクライアント バージョン**: Microsoft[!INCLUDE[dotnet45](../../includes/dotnet45-md.md)]バンドルの SQL Server に接続するクライアント Dll が必要です。</span><span class="sxs-lookup"><span data-stu-id="3397d-138">**Supported client versions**: Microsoft [!INCLUDE[dotnet45](../../includes/dotnet45-md.md)] bundles the client DLLs required to connect to SQL Server.</span></span> <span data-ttu-id="3397d-139">お使いのコンピューターに明示的に任意のクライアント Dll をインストールする必要はありません。</span><span class="sxs-lookup"><span data-stu-id="3397d-139">You do not need to explicitly install any client DLLs on your computer.</span></span>  
  
-   <span data-ttu-id="3397d-140">**必要なドライバー**:</span><span class="sxs-lookup"><span data-stu-id="3397d-140">**Required drivers**:</span></span>  
  
    -   <span data-ttu-id="3397d-141">SQL Server のバージョン、たとえば、Geography に付属して Udt を使用する場合は、次の Dll は、SQL Server 上の操作を実行するアダプターを使用するコンピューター上に存在を確認します。</span><span class="sxs-lookup"><span data-stu-id="3397d-141">If you use the UDTs shipped with the SQL Server versions, for example, Geography, make sure the following DLLs are present on the computer where you use the adapter to perform operations on SQL Server.</span></span> <span data-ttu-id="3397d-142">など、SQL Server 上の操作を実行する BizTalk プロジェクトを作成する場合は、これらの Dll が BizTalk Server が実行されているコンピューター上に存在する必要があります。</span><span class="sxs-lookup"><span data-stu-id="3397d-142">For example, if you create BizTalk projects to perform operations on SQL Server, these DLLs must be present on the computer where BizTalk Server is running.</span></span>  
  
        -   <span data-ttu-id="3397d-143">Microsoft.SqlServer.Types.dll は GAC に追加することを確認します。</span><span class="sxs-lookup"><span data-stu-id="3397d-143">Make sure Microsoft.SqlServer.Types.dll is added to the GAC.</span></span>  
  
        -   <span data-ttu-id="3397d-144">SqlServerSpatial.dll が System32 フォルダーにあることを確認してください。</span><span class="sxs-lookup"><span data-stu-id="3397d-144">Make sure SqlServerSpatial.dll is available in the System32 folder.</span></span>  
  
         <span data-ttu-id="3397d-145">SQL Server セットアップを実行しを選択すると、コンピューターにこれらの Dll をインストールできます**管理ツール-基本**と**管理ツール-完全**で、**機能の選択**ウィザードのページです。</span><span class="sxs-lookup"><span data-stu-id="3397d-145">You can install these DLLs on the computer by running the SQL Server setup and selecting **Management Tools – Basic** and **Management Tools – Complete** in the **Feature Selection** page of the wizard.</span></span>  
  
    -   <span data-ttu-id="3397d-146">FILESTREAM データ型の列に対して操作を実行するアダプターを使用する場合は、SQL クライアント接続 SDK がインストールされている必要があることを確認してください。</span><span class="sxs-lookup"><span data-stu-id="3397d-146">If you use the adapter to perform operations on columns of FILESTREAM data types, make sure you have SQL Client Connectivity SDK installed.</span></span> <span data-ttu-id="3397d-147">SQL Server セットアップを実行しを選択すると、SQL クライアント接続 SDK をインストールすることができます**SQL クライアント接続 SDK**で、**機能の選択**ウィザードのページです。</span><span class="sxs-lookup"><span data-stu-id="3397d-147">You can install the SQL Client Connectivity SDK by running the SQL Server setup and selecting **SQL Client Connectivity SDK** in the **Feature Selection** page of the wizard.</span></span> <span data-ttu-id="3397d-148">アダプターは、FILESTREAM 操作を実行するのに、SQL クライアント接続 SDK と共にインストールされる、sqlncli10.dll を使用します。</span><span class="sxs-lookup"><span data-stu-id="3397d-148">The adapter uses the sqlncli10.dll, installed with the SQL Client Connectivity SDK, to perform FILESTREAM operations.</span></span>  
  
    -   <span data-ttu-id="3397d-149">SQL Server で、独自の Udt を作成する場合は、Udt のそれぞれのアセンブリが GAC に追加を確認します。</span><span class="sxs-lookup"><span data-stu-id="3397d-149">If you create your own UDTs in SQL Server, make sure the respective assemblies for the UDTs are added to the GAC.</span></span>  
  
<a name="BKMK_Compat"></a>   
## <a name="64-bit-support"></a><span data-ttu-id="3397d-150">64 ビットのサポート</span><span class="sxs-lookup"><span data-stu-id="3397d-150">64-bit support</span></span> 

<span data-ttu-id="3397d-151">[!INCLUDE[adaptersqlshort](../../includes/adaptersqlshort-md.md)] 32 ビットまたは 64 ビット ホスト インスタンスで実行できます。</span><span class="sxs-lookup"><span data-stu-id="3397d-151">The [!INCLUDE[adaptersqlshort](../../includes/adaptersqlshort-md.md)] can run in a 32-bit or 64-bit host instance.</span></span>

 <span data-ttu-id="3397d-152">32 ビットおよび 64 ビットのサポートされているインストールのシナリオの詳細については[!INCLUDE[adaptersqlshort](../../includes/adaptersqlshort-md.md)]、します。</span><span class="sxs-lookup"><span data-stu-id="3397d-152">For more information about the supported installation scenarios for the 32-bit and 64-bit [!INCLUDE[adaptersqlshort](../../includes/adaptersqlshort-md.md)],.</span></span> 
  
<a name="BKMK_Install_Adap"></a>   
## <a name="install-the-sql-adapter"></a><span data-ttu-id="3397d-153">SQL アダプターをインストールします。</span><span class="sxs-lookup"><span data-stu-id="3397d-153">Install the SQL Adapter</span></span>  
 <span data-ttu-id="3397d-154">インストールする前にインストールされている前提条件があるかどうかを確認、[!INCLUDE[adaptersqlshort](../../includes/adaptersqlshort-md.md)]です。</span><span class="sxs-lookup"><span data-stu-id="3397d-154">Make sure you have the prerequisites installed before installing the [!INCLUDE[adaptersqlshort](../../includes/adaptersqlshort-md.md)].</span></span>  
  
 <span data-ttu-id="3397d-155">インストールすることができます、[!INCLUDE[adaptersqlshort](../../includes/adaptersqlshort-md.md)]次の 2 つの方法で。</span><span class="sxs-lookup"><span data-stu-id="3397d-155">You can install the [!INCLUDE[adaptersqlshort](../../includes/adaptersqlshort-md.md)] in the following two ways:</span></span>  
  
-   <span data-ttu-id="3397d-156">**対話モードで**セットアップ ウィザードを使用します。</span><span class="sxs-lookup"><span data-stu-id="3397d-156">**In interactive mode** using the setup wizard</span></span>  
  
-   <span data-ttu-id="3397d-157">**サイレント モードで**msiexec を使用して、コマンドで lin</span><span class="sxs-lookup"><span data-stu-id="3397d-157">**In silent mode** using msiexec in the command lin</span></span>  
  
    > [!IMPORTANT]
    >  <span data-ttu-id="3397d-158">インストールするコンピューターで管理者特権を持つ必要があります、[!INCLUDE[adaptersqlshort](../../includes/adaptersqlshort-md.md)]ウィザードまたはコマンドラインを使用してインストールするかどうかのあるかにかかわらず、します。</span><span class="sxs-lookup"><span data-stu-id="3397d-158">You must have administrative privileges on the computer where you will install the [!INCLUDE[adaptersqlshort](../../includes/adaptersqlshort-md.md)], irrespective of whether you are installing by using the wizard or the command line.</span></span>  
  
<a name="BKMK_Install_Scenarios"></a>   
### <a name="32-bit-and-64-bit-install-scenarios"></a><span data-ttu-id="3397d-159">32 ビットおよび 64 ビット インストール シナリオ</span><span class="sxs-lookup"><span data-stu-id="3397d-159">32-bit and 64-bit install scenarios</span></span>
 <span data-ttu-id="3397d-160">[!INCLUDE[btsBizTalkServerNoVersion](../../includes/btsbiztalkservernoversion-md.md)]、[!INCLUDE[adaptersqlshort](../../includes/adaptersqlshort-md.md)]に使用できます。</span><span class="sxs-lookup"><span data-stu-id="3397d-160">With [!INCLUDE[btsBizTalkServerNoVersion](../../includes/btsbiztalkservernoversion-md.md)], the [!INCLUDE[adaptersqlshort](../../includes/adaptersqlshort-md.md)] can be used for:</span></span>  
  
-   [!INCLUDE[btsVStudioNoVersion](../../includes/btsvstudionoversion-md.md)]<span data-ttu-id="3397d-161">デザイン時 (操作のメタデータを生成する) ときにします。</span><span class="sxs-lookup"><span data-stu-id="3397d-161"> design time (when generating metadata for operations).</span></span>  
  
-   <span data-ttu-id="3397d-162">BizTalk Server 管理コンソール デザイン時 (物理ポートの作成) します。</span><span class="sxs-lookup"><span data-stu-id="3397d-162">BizTalk Server Administration console design time (for creating physical ports).</span></span>  
  
    > [!NOTE]
    >  <span data-ttu-id="3397d-163">BizTalk Server 管理コンソールは、32 ビット Microsoft 管理コンソール (MMC) アプリケーションとして実行されます。</span><span class="sxs-lookup"><span data-stu-id="3397d-163">BizTalk Server Administration console runs as a 32-bit Microsoft Management Console (MMC) application.</span></span>  
  
-   <span data-ttu-id="3397d-164">BizTalk ランタイム (ときに送信し、LOB アプリケーションからメッセージを受信)。</span><span class="sxs-lookup"><span data-stu-id="3397d-164">BizTalk run time (when sending and receiving messages from LOB applications).</span></span>  
  
 <span data-ttu-id="3397d-165">同じコンピューターまたは別のコンピューターでこれらすべてのタスクを実行するインストールことができます。</span><span class="sxs-lookup"><span data-stu-id="3397d-165">You can have an installation where you perform all these tasks on the same computer or different computers.</span></span> <span data-ttu-id="3397d-166">両方[!INCLUDE[btsVStudioNoVersion](../../includes/btsvstudionoversion-md.md)]と BizTalk MMC は 32 ビット プロセスが、32 ビットをインストールする必要があります[!INCLUDE[adaptersqlshort](../../includes/adaptersqlshort-md.md)]デザイン時のタスクを実行するコンピューターにします。</span><span class="sxs-lookup"><span data-stu-id="3397d-166">Because both [!INCLUDE[btsVStudioNoVersion](../../includes/btsvstudionoversion-md.md)] and BizTalk MMC are 32-bit processes, you must install the 32-bit [!INCLUDE[adaptersqlshort](../../includes/adaptersqlshort-md.md)] on the computer where you want to perform the design-time tasks.</span></span> <span data-ttu-id="3397d-167">インストールするため、次のシナリオがサポートされている、 [!INCLUDE[adaptersqlshort](../../includes/adaptersqlshort-md.md)] 32 ビットおよび 64 ビット プラットフォーム上でします。</span><span class="sxs-lookup"><span data-stu-id="3397d-167">The following scenarios are supported for installing the [!INCLUDE[adaptersqlshort](../../includes/adaptersqlshort-md.md)] on 32-bit and 64-bit platforms.</span></span>  
  
#### <a name="install-scenarios-on-a-32-bit-platform"></a><span data-ttu-id="3397d-168">32 ビット プラットフォームでのインストール シナリオ</span><span class="sxs-lookup"><span data-stu-id="3397d-168">Install scenarios on a 32-bit platform</span></span>  
 <span data-ttu-id="3397d-169">インストールするときに、次のシナリオがサポートされて、 [!INCLUDE[adaptersqlshort](../../includes/adaptersqlshort-md.md)] 32 ビット プラットフォーム上でします。</span><span class="sxs-lookup"><span data-stu-id="3397d-169">The following scenarios are supported when installing the [!INCLUDE[adaptersqlshort](../../includes/adaptersqlshort-md.md)] on a 32-bit platform.</span></span>  
  
|<span data-ttu-id="3397d-170">Visual Studio のデザイン時</span><span class="sxs-lookup"><span data-stu-id="3397d-170">Visual Studio design time</span></span>|<span data-ttu-id="3397d-171">デザイン時の BizTalk MMC</span><span class="sxs-lookup"><span data-stu-id="3397d-171">BizTalk MMC design time</span></span>|<span data-ttu-id="3397d-172">BizTalk ランタイム</span><span class="sxs-lookup"><span data-stu-id="3397d-172">BizTalk run time</span></span>|<span data-ttu-id="3397d-173">Visual Studio デザイン時またはデザイン時の BizTalk MMC + BizTalk ランタイムします。</span><span class="sxs-lookup"><span data-stu-id="3397d-173">Visual Studio design time and/or  BizTalk MMC design time + BizTalk run time</span></span>|  
|---|---|---|---|  
|<span data-ttu-id="3397d-174">がインストール 32 ビット[!INCLUDE[afproductnameshort](../../includes/afproductnameshort-md.md)]です。</span><span class="sxs-lookup"><span data-stu-id="3397d-174">- Install 32-bit [!INCLUDE[afproductnameshort](../../includes/afproductnameshort-md.md)].</span></span><br /><br /> <span data-ttu-id="3397d-175">がインストール 32 ビット[!INCLUDE[adaptersqlshort](../../includes/adaptersqlshort-md.md)]です。</span><span class="sxs-lookup"><span data-stu-id="3397d-175">- Install 32-bit [!INCLUDE[adaptersqlshort](../../includes/adaptersqlshort-md.md)].</span></span><br /><br /> <span data-ttu-id="3397d-176">32 ビット クライアントとその他の必要な Dll をインストールします。</span><span class="sxs-lookup"><span data-stu-id="3397d-176">- Install 32-bit client and other required DLLs.</span></span>|<span data-ttu-id="3397d-177">がインストール 32 ビット[!INCLUDE[afproductnameshort](../../includes/afproductnameshort-md.md)]です。</span><span class="sxs-lookup"><span data-stu-id="3397d-177">- Install 32-bit [!INCLUDE[afproductnameshort](../../includes/afproductnameshort-md.md)].</span></span><br /><br /> <span data-ttu-id="3397d-178">がインストール 32 ビット[!INCLUDE[adaptersqlshort](../../includes/adaptersqlshort-md.md)]です。</span><span class="sxs-lookup"><span data-stu-id="3397d-178">- Install 32-bit [!INCLUDE[adaptersqlshort](../../includes/adaptersqlshort-md.md)].</span></span><br /><br /> <span data-ttu-id="3397d-179">32 ビット クライアントとその他の必要な Dll をインストールします。</span><span class="sxs-lookup"><span data-stu-id="3397d-179">- Install 32-bit client and other required DLLs.</span></span>|<span data-ttu-id="3397d-180">がインストール 32 ビット[!INCLUDE[afproductnameshort](../../includes/afproductnameshort-md.md)]です。</span><span class="sxs-lookup"><span data-stu-id="3397d-180">- Install 32-bit [!INCLUDE[afproductnameshort](../../includes/afproductnameshort-md.md)].</span></span><br /><br /> <span data-ttu-id="3397d-181">がインストール 32 ビット[!INCLUDE[adaptersqlshort](../../includes/adaptersqlshort-md.md)]です。</span><span class="sxs-lookup"><span data-stu-id="3397d-181">- Install 32-bit [!INCLUDE[adaptersqlshort](../../includes/adaptersqlshort-md.md)].</span></span><br /><br /> <span data-ttu-id="3397d-182">32 ビット クライアントとその他の必要な Dll をインストールします。</span><span class="sxs-lookup"><span data-stu-id="3397d-182">- Install 32-bit client and other required DLLs.</span></span>|<span data-ttu-id="3397d-183">がインストール 32 ビット[!INCLUDE[afproductnameshort](../../includes/afproductnameshort-md.md)]です。</span><span class="sxs-lookup"><span data-stu-id="3397d-183">- Install 32-bit [!INCLUDE[afproductnameshort](../../includes/afproductnameshort-md.md)].</span></span><br /><br /> <span data-ttu-id="3397d-184">がインストール 32 ビット[!INCLUDE[adaptersqlshort](../../includes/adaptersqlshort-md.md)]です。</span><span class="sxs-lookup"><span data-stu-id="3397d-184">- Install 32-bit [!INCLUDE[adaptersqlshort](../../includes/adaptersqlshort-md.md)].</span></span><br /><br /> <span data-ttu-id="3397d-185">32 ビット クライアントとその他の必要な Dll をインストールします。</span><span class="sxs-lookup"><span data-stu-id="3397d-185">- Install 32-bit client and other required DLLs.</span></span>|  
  
#### <a name="install-scenarios-on-a-64-bit-platform"></a><span data-ttu-id="3397d-186">64 ビット プラットフォームでのインストール シナリオ</span><span class="sxs-lookup"><span data-stu-id="3397d-186">Install scenarios on a 64-bit platform</span></span>  
 <span data-ttu-id="3397d-187">インストールするときに、次のシナリオがサポートされて、 [!INCLUDE[adaptersqlshort](../../includes/adaptersqlshort-md.md)] 64 ビット プラットフォーム上でします。</span><span class="sxs-lookup"><span data-stu-id="3397d-187">The following scenarios are supported when installing the [!INCLUDE[adaptersqlshort](../../includes/adaptersqlshort-md.md)] on a 64-bit platform.</span></span>  
  
> [!NOTE]
>  <span data-ttu-id="3397d-188">いずれかを使用してデザイン時のタスクを実行する任意のコンピューターで[!INCLUDE[btsVStudioNoVersion](../../includes/btsvstudionoversion-md.md)]BizTalk MMC で、32 ビットをインストールする必要がありますまたは[!INCLUDE[adaptersqlshort](../../includes/adaptersqlshort-md.md)]です。</span><span class="sxs-lookup"><span data-stu-id="3397d-188">On any computer where you want to perform design-time tasks using either [!INCLUDE[btsVStudioNoVersion](../../includes/btsvstudionoversion-md.md)] or BizTalk MMC, you must install the 32-bit [!INCLUDE[adaptersqlshort](../../includes/adaptersqlshort-md.md)].</span></span>  
  
|<span data-ttu-id="3397d-189">Visual Studio のデザイン時</span><span class="sxs-lookup"><span data-stu-id="3397d-189">Visual Studio design time</span></span>|<span data-ttu-id="3397d-190">デザイン時の BizTalk MMC</span><span class="sxs-lookup"><span data-stu-id="3397d-190">BizTalk MMC design time</span></span>|<span data-ttu-id="3397d-191">BizTalk ランタイム</span><span class="sxs-lookup"><span data-stu-id="3397d-191">BizTalk run time</span></span>|<span data-ttu-id="3397d-192">Visual Studio デザイン時またはデザイン時の BizTalk MMC + BizTalk ランタイムします。</span><span class="sxs-lookup"><span data-stu-id="3397d-192">Visual Studio design time and/or BizTalk MMC design time + BizTalk run time</span></span>|  
|---|---|---|---|  
|<span data-ttu-id="3397d-193">がインストール 64 ビット[!INCLUDE[afproductnameshort](../../includes/afproductnameshort-md.md)]です。</span><span class="sxs-lookup"><span data-stu-id="3397d-193">- Install 64-bit [!INCLUDE[afproductnameshort](../../includes/afproductnameshort-md.md)].</span></span><br /><br /> <span data-ttu-id="3397d-194">がインストール 32 ビット[!INCLUDE[adaptersqlshort](../../includes/adaptersqlshort-md.md)]です。</span><span class="sxs-lookup"><span data-stu-id="3397d-194">- Install 32-bit [!INCLUDE[adaptersqlshort](../../includes/adaptersqlshort-md.md)].</span></span><br /><br /> <span data-ttu-id="3397d-195">32 ビット クライアントとその他の必要な Dll をインストールします。</span><span class="sxs-lookup"><span data-stu-id="3397d-195">- Install 32-bit client and other required DLLs.</span></span>|<span data-ttu-id="3397d-196">がインストール 64 ビット[!INCLUDE[afproductnameshort](../../includes/afproductnameshort-md.md)]です。</span><span class="sxs-lookup"><span data-stu-id="3397d-196">- Install 64-bit [!INCLUDE[afproductnameshort](../../includes/afproductnameshort-md.md)].</span></span><br /><br /> <span data-ttu-id="3397d-197">がインストール 32 ビット[!INCLUDE[adaptersqlshort](../../includes/adaptersqlshort-md.md)]です。</span><span class="sxs-lookup"><span data-stu-id="3397d-197">- Install 32-bit [!INCLUDE[adaptersqlshort](../../includes/adaptersqlshort-md.md)].</span></span><br /><br /> <span data-ttu-id="3397d-198">32 ビット クライアントとその他の必要な Dll をインストールします。</span><span class="sxs-lookup"><span data-stu-id="3397d-198">- Install 32-bit client and other required DLLs.</span></span>|<span data-ttu-id="3397d-199">**32 ビット BizTalk プロセス**:</span><span class="sxs-lookup"><span data-stu-id="3397d-199">**For a 32-bit BizTalk process**:</span></span><br /><br /> <span data-ttu-id="3397d-200">がインストール 64 ビット[!INCLUDE[afproductnameshort](../../includes/afproductnameshort-md.md)]です。</span><span class="sxs-lookup"><span data-stu-id="3397d-200">- Install 64-bit [!INCLUDE[afproductnameshort](../../includes/afproductnameshort-md.md)].</span></span><br /><br /> <span data-ttu-id="3397d-201">がインストール 32 ビット[!INCLUDE[adaptersqlshort](../../includes/adaptersqlshort-md.md)]です。</span><span class="sxs-lookup"><span data-stu-id="3397d-201">- Install 32-bit [!INCLUDE[adaptersqlshort](../../includes/adaptersqlshort-md.md)].</span></span><br /><br /> <span data-ttu-id="3397d-202">32 ビット クライアントとその他の必要な Dll をインストールします。</span><span class="sxs-lookup"><span data-stu-id="3397d-202">- Install 32-bit client and other required DLLs.</span></span><br /><br /> <span data-ttu-id="3397d-203">**64 ビットの BizTalk プロセス**:</span><span class="sxs-lookup"><span data-stu-id="3397d-203">**For a 64-bit BizTalk process**:</span></span><br /><br /> <span data-ttu-id="3397d-204">がインストール 64 ビット[!INCLUDE[afproductnameshort](../../includes/afproductnameshort-md.md)]です。</span><span class="sxs-lookup"><span data-stu-id="3397d-204">- Install 64-bit [!INCLUDE[afproductnameshort](../../includes/afproductnameshort-md.md)].</span></span><br /><br /> <span data-ttu-id="3397d-205">がインストール 64 ビット[!INCLUDE[adaptersqlshort](../../includes/adaptersqlshort-md.md)]です。</span><span class="sxs-lookup"><span data-stu-id="3397d-205">- Install 64-bit [!INCLUDE[adaptersqlshort](../../includes/adaptersqlshort-md.md)].</span></span><br /><br /> <span data-ttu-id="3397d-206">-64 ビット クライアントとその他の必要な Dll をインストールします。</span><span class="sxs-lookup"><span data-stu-id="3397d-206">- Install 64-bit client and other required DLLs.</span></span>|<span data-ttu-id="3397d-207">**32 ビット BizTalk プロセス**:</span><span class="sxs-lookup"><span data-stu-id="3397d-207">**For a 32-bit BizTalk process**:</span></span><br /><br /> <span data-ttu-id="3397d-208">がインストール 64 ビット[!INCLUDE[afproductnameshort](../../includes/afproductnameshort-md.md)]です。</span><span class="sxs-lookup"><span data-stu-id="3397d-208">- Install 64-bit [!INCLUDE[afproductnameshort](../../includes/afproductnameshort-md.md)].</span></span><br /><br /> <span data-ttu-id="3397d-209">がインストール 32 ビット[!INCLUDE[adaptersqlshort](../../includes/adaptersqlshort-md.md)]です。</span><span class="sxs-lookup"><span data-stu-id="3397d-209">- Install 32-bit [!INCLUDE[adaptersqlshort](../../includes/adaptersqlshort-md.md)].</span></span><br /><br /> <span data-ttu-id="3397d-210">32 ビット クライアントとその他の必要な Dll をインストールします。</span><span class="sxs-lookup"><span data-stu-id="3397d-210">- Install 32-bit client and other required DLLs.</span></span><br /><br /> <span data-ttu-id="3397d-211">**64 ビットの BizTalk プロセス**:</span><span class="sxs-lookup"><span data-stu-id="3397d-211">**For a 64-bit BizTalk process**:</span></span><br /><br /> <span data-ttu-id="3397d-212">がインストール 64 ビット[!INCLUDE[afproductnameshort](../../includes/afproductnameshort-md.md)]です。</span><span class="sxs-lookup"><span data-stu-id="3397d-212">- Install 64-bit [!INCLUDE[afproductnameshort](../../includes/afproductnameshort-md.md)].</span></span><br /><br /> <span data-ttu-id="3397d-213">がインストール 64 ビット[!INCLUDE[adaptersqlshort](../../includes/adaptersqlshort-md.md)]です。</span><span class="sxs-lookup"><span data-stu-id="3397d-213">- Install 64-bit [!INCLUDE[adaptersqlshort](../../includes/adaptersqlshort-md.md)].</span></span><br /><br /> <span data-ttu-id="3397d-214">-64 ビット クライアントとその他の必要な Dll をインストールします。</span><span class="sxs-lookup"><span data-stu-id="3397d-214">- Install 64-bit client and other required DLLs.</span></span><br /><br /> <span data-ttu-id="3397d-215">がインストール 32 ビット[!INCLUDE[adaptersqlshort](../../includes/adaptersqlshort-md.md)]です。</span><span class="sxs-lookup"><span data-stu-id="3397d-215">- Install 32-bit [!INCLUDE[adaptersqlshort](../../includes/adaptersqlshort-md.md)].</span></span><br /><br /> <span data-ttu-id="3397d-216">32 ビット クライアントとその他の必要な Dll をインストールします。</span><span class="sxs-lookup"><span data-stu-id="3397d-216">- Install 32-bit client and other required DLLs.</span></span>|  
  
<a name="BKMK_Install_wizard"></a>   
### <a name="install-the-sql-adapter-in-interactive-mode"></a><span data-ttu-id="3397d-217">対話モードでの SQL アダプターをインストールします。</span><span class="sxs-lookup"><span data-stu-id="3397d-217">Install the SQL Adapter in interactive mode</span></span>  
 
1.  <span data-ttu-id="3397d-218">インストーラーを実行します。</span><span class="sxs-lookup"><span data-stu-id="3397d-218">Run the installer.</span></span>  
  
    > [!NOTE]
    >  <span data-ttu-id="3397d-219">インストールする場合、[!INCLUDE[adaptersqlshort](../../includes/adaptersqlshort-md.md)]バーチャル マシンで、セットアップ ウィザードは使用可能なディスク容量については、セットアップがチェックされることを通知 ダイアログ ボックス続行されません可能性があります。</span><span class="sxs-lookup"><span data-stu-id="3397d-219">If you are installing the [!INCLUDE[adaptersqlshort](../../includes/adaptersqlshort-md.md)] on a virtual machine, the setup wizard might not proceed beyond a dialog box informing that the setup is checking for available disk space.</span></span> <span data-ttu-id="3397d-220">このような場合、サイレント インストール オプションを使用することをお勧めします。</span><span class="sxs-lookup"><span data-stu-id="3397d-220">In such cases, we recommend that you use the silent installation option.</span></span>   
  
2.  <span data-ttu-id="3397d-221">[ようこそ] 画面で、情報を参照し、をクリックして**次**です。</span><span class="sxs-lookup"><span data-stu-id="3397d-221">Read the information on the Welcome screen, and then click **Next**.</span></span>  
  
3.  <span data-ttu-id="3397d-222">読み取り、使用許諾契約書 (EULA) に同意し、クリックして**次**です。</span><span class="sxs-lookup"><span data-stu-id="3397d-222">Read and accept the end-user license agreement (EULA), and then click **Next**.</span></span>  
  
4.  <span data-ttu-id="3397d-223">**コピー先フォルダー**  ダイアログ ボックスで、インストールする場所を指定、 [!INCLUDE[adaptersqlshort](../../includes/adaptersqlshort-md.md)]、 をクリックして **[次へ]**、クリックして**インストール**です。</span><span class="sxs-lookup"><span data-stu-id="3397d-223">In the **Destination Folder** dialog box, specify the location where you want to install the [!INCLUDE[adaptersqlshort](../../includes/adaptersqlshort-md.md)], click **Next**, and then click **Install**.</span></span>  
  
5.  <span data-ttu-id="3397d-224">**カスタマー エクスペリエンス向上プログラム** ダイアログ ボックスで、カスタマー エクスペリエンス向上プログラム (CEIP) に登録するかどうかを指定します。</span><span class="sxs-lookup"><span data-stu-id="3397d-224">In the **Customer Experience Improvement Program** dialog box, specify whether you would like to enroll for the Customer Experience Improvement Program (CEIP).</span></span> <span data-ttu-id="3397d-225">CEIP 用の一部として[!INCLUDE[adaptersqlshort](../../includes/adaptersqlshort-md.md)]、次のデータは、Microsoft と共有されます。</span><span class="sxs-lookup"><span data-stu-id="3397d-225">As part of CEIP for [!INCLUDE[adaptersqlshort](../../includes/adaptersqlshort-md.md)], you will share the following data with Microsoft:</span></span>  
  
    -   <span data-ttu-id="3397d-226">インストールしているコンピューターのハードウェアに関連するデータ、[!INCLUDE[adaptersqlshort](../../includes/adaptersqlshort-md.md)]です。</span><span class="sxs-lookup"><span data-stu-id="3397d-226">Data related to the computer hardware on which you are installing the [!INCLUDE[adaptersqlshort](../../includes/adaptersqlshort-md.md)].</span></span>  
  
    -   <span data-ttu-id="3397d-227">使用して接続を使用している SQL Server のバージョンに関連するデータ、[!INCLUDE[adaptersqlshort](../../includes/adaptersqlshort-md.md)]です。</span><span class="sxs-lookup"><span data-stu-id="3397d-227">Data related to the SQL Server versions you are using to connect using the [!INCLUDE[adaptersqlshort](../../includes/adaptersqlshort-md.md)].</span></span>  
  
     <span data-ttu-id="3397d-228">指定し、をクリックして**OK**です。</span><span class="sxs-lookup"><span data-stu-id="3397d-228">Specify your choice and click **OK**.</span></span>  
  
    > [!NOTE]
    >  <span data-ttu-id="3397d-229">常に、基本設定を変更することができます修復モードで、コントロール パネルから、セットアップを実行して、CEIP の登録に関連します。</span><span class="sxs-lookup"><span data-stu-id="3397d-229">You can always change your preference regarding enrolling for CEIP by running the Setup in Repair mode from the Control Panel.</span></span>  
  
6.  <span data-ttu-id="3397d-230">**[完了]** をクリックします。</span><span class="sxs-lookup"><span data-stu-id="3397d-230">Click **Finish**.</span></span>  
  
<a name="BKMK_SilentInst"></a>   
### <a name="install-the-sql-adapter-in-silent-mode"></a><span data-ttu-id="3397d-231">サイレント モードでの SQL アダプターをインストールします。</span><span class="sxs-lookup"><span data-stu-id="3397d-231">Install the SQL adapter in Silent mode</span></span>  
 <span data-ttu-id="3397d-232">次の手順は、のサイレント インストールを実行する方法を示します[!INCLUDE[adaptersqlshort](../../includes/adaptersqlshort-md.md)]を使用して、`msiexec`コマンド。</span><span class="sxs-lookup"><span data-stu-id="3397d-232">The following procedure demonstrates how to perform a silent installation of [!INCLUDE[adaptersqlshort](../../includes/adaptersqlshort-md.md)] using the `msiexec` command.</span></span>  
  
1.  <span data-ttu-id="3397d-233">コマンド プロンプトを開き、および、インストーラーを持っているフォルダーに移動します。</span><span class="sxs-lookup"><span data-stu-id="3397d-233">Open a command prompt, and navigate to the folder where you have the installer.</span></span>  
  
2.  <span data-ttu-id="3397d-234">インストールするには、次のコマンドを実行、 [!INCLUDE[adaptersqlshort](../../includes/adaptersqlshort-md.md)]:</span><span class="sxs-lookup"><span data-stu-id="3397d-234">Run the following command to install the [!INCLUDE[adaptersqlshort](../../includes/adaptersqlshort-md.md)]:</span></span>  
  
    > [!NOTE]
    >  <span data-ttu-id="3397d-235">次のコマンドでの x64 ベースのプラットフォームでサイレント インストールを実行するには、SqlAdapterSetup64.msi で SqlAdapterSetup.msi を置き換えます。</span><span class="sxs-lookup"><span data-stu-id="3397d-235">To perform silent installation on an x64-based platform, in the following commands, replace SqlAdapterSetup.msi with SqlAdapterSetup64.msi.</span></span>  
  
    ```  
    msiexec /i SqlAdapterSetup.msi /qn  
    ```  
  
     <span data-ttu-id="3397d-236">CEIP をサイレント インストールの一部として登録することもできます。</span><span class="sxs-lookup"><span data-stu-id="3397d-236">You can also choose to enroll for CEIP as part of the silent installation.</span></span> <span data-ttu-id="3397d-237">CEIP 用の一部として[!INCLUDE[adaptersqlshort](../../includes/adaptersqlshort-md.md)]、次のデータは、Microsoft と共有されます。</span><span class="sxs-lookup"><span data-stu-id="3397d-237">As part of CEIP for [!INCLUDE[adaptersqlshort](../../includes/adaptersqlshort-md.md)], you will share the following data with Microsoft:</span></span>  
  
    -   <span data-ttu-id="3397d-238">インストールしているコンピューターのハードウェア、[!INCLUDE[adaptersqlshort](../../includes/adaptersqlshort-md.md)]です。</span><span class="sxs-lookup"><span data-stu-id="3397d-238">The computer hardware on which you are installing the [!INCLUDE[adaptersqlshort](../../includes/adaptersqlshort-md.md)].</span></span>  
  
    -   <span data-ttu-id="3397d-239">使用して接続を使用している SQL Server のバージョン、[!INCLUDE[adaptersqlshort](../../includes/adaptersqlshort-md.md)]です。</span><span class="sxs-lookup"><span data-stu-id="3397d-239">The SQL Server versions you are using to connect using the [!INCLUDE[adaptersqlshort](../../includes/adaptersqlshort-md.md)].</span></span>  
  
     <span data-ttu-id="3397d-240">CEIP の登録には、するには、次のコマンドを実行します。</span><span class="sxs-lookup"><span data-stu-id="3397d-240">To enroll for CEIP, run the following command:</span></span>  
  
    ```  
    msiexec /i SqlAdapterSetup.msi /qn CEIP_OPTIN=true  
    ```  
  
     <span data-ttu-id="3397d-241">既定では、このオプションは false です。</span><span class="sxs-lookup"><span data-stu-id="3397d-241">By default, the option is false.</span></span>  
  
     <span data-ttu-id="3397d-242">詳細については、`msiexec`コマンドを入力`msiexec`キーを押して、コマンド ライン`ENTER`を参照してくださいまたは[https://support.microsoft.com/kb/230781](https://support.microsoft.com/kb/230781)です。</span><span class="sxs-lookup"><span data-stu-id="3397d-242">For more information about the `msiexec` command, type `msiexec` on the command line and press `ENTER`, or see [https://support.microsoft.com/kb/230781](https://support.microsoft.com/kb/230781).</span></span>  
  
<a name="BKMK_PostInst"></a>   
## <a name="post-installation-tasks"></a><span data-ttu-id="3397d-243">インストール後のタスク</span><span class="sxs-lookup"><span data-stu-id="3397d-243">Post-installation tasks</span></span>  
  
<a name="BKMK_Register_Bindings"></a>   
#### <a name="register-the-bindings"></a><span data-ttu-id="3397d-244">バインドを登録します。</span><span class="sxs-lookup"><span data-stu-id="3397d-244">Register the Bindings</span></span>  
<span data-ttu-id="3397d-245">次の手順を完了*のみ*machine.config ファイルにアダプターのバインドを登録するセットアップ ウィザードが失敗した場合。</span><span class="sxs-lookup"><span data-stu-id="3397d-245">Complete these steps *only* if the setup wizard fails to register the adapter bindings in the machine.config file.</span></span>  
  
1.  <span data-ttu-id="3397d-246">コンピューター上の machine.config ファイルに移動します。</span><span class="sxs-lookup"><span data-stu-id="3397d-246">Navigate to the machine.config file on the computer.</span></span> <span data-ttu-id="3397d-247">たとえば、32 ビット プラットフォームで、machine.config は下にある使用可能な\<システム ドライブ\>: \WINDOWS\Microsoft.NET\Framework\\< バージョン\>\CONFIG です。</span><span class="sxs-lookup"><span data-stu-id="3397d-247">For example, on a 32-bit platform, the machine.config is available under \<system drive\>:\WINDOWS\Microsoft.NET\Framework\\<version\>\CONFIG.</span></span>  
  
    -   <span data-ttu-id="3397d-248">Microsoft .NET framework 3.5 SP1、 \<*バージョン*\> .NET Framework のバージョン v2.0.50727 がします。</span><span class="sxs-lookup"><span data-stu-id="3397d-248">For Microsoft .NET Framework 3.5 SP1, \<*version*\> is the version v2.0.50727 of the .NET Framework.</span></span>  
  
    -   <span data-ttu-id="3397d-249">Microsoft の[!INCLUDE[netfx40_short](../../includes/netfx40-short-md.md)]、 \<*バージョン*\>は、.NET Framework のバージョン v4.0.30319 します。</span><span class="sxs-lookup"><span data-stu-id="3397d-249">For Microsoft [!INCLUDE[netfx40_short](../../includes/netfx40-short-md.md)], \<*version*\> is the version v4.0.30319 of the .NET Framework.</span></span>  
  
2.  <span data-ttu-id="3397d-250">テキスト エディターを使用してファイルを開きます。</span><span class="sxs-lookup"><span data-stu-id="3397d-250">Open the file using a text editor.</span></span>  
  
3.  <span data-ttu-id="3397d-251">アダプターのバインドを登録します。</span><span class="sxs-lookup"><span data-stu-id="3397d-251">To register the adapter bindings:</span></span>  
  
    1.  <span data-ttu-id="3397d-252">要素"system.serviceModel"を検索し、その下にある、次を追加します。</span><span class="sxs-lookup"><span data-stu-id="3397d-252">Search for the element "system.serviceModel" and add the following under it:</span></span>  
  
        ```  
        <client>  
          <endpoint binding="sqlBinding" contract="IMetadataExchange" name="mssql" />  
        </client>  
        ```  
  
    2.  <span data-ttu-id="3397d-253">"BindingElementExtensions"system.serviceModel\extensions 下にある要素を検索します。</span><span class="sxs-lookup"><span data-stu-id="3397d-253">Search for the element "bindingElementExtensions" under system.serviceModel\extensions.</span></span>  
  
    3.  <span data-ttu-id="3397d-254">"BindingElementExtensions"ノードの下の次のセクションを追加します。</span><span class="sxs-lookup"><span data-stu-id="3397d-254">Add the following section under the "bindingElementExtensions" node.</span></span>  
  
         <span data-ttu-id="3397d-255">[!INCLUDE[adaptersqlshort](../../includes/adaptersqlshort-md.md)]を追加します。</span><span class="sxs-lookup"><span data-stu-id="3397d-255">For the [!INCLUDE[adaptersqlshort](../../includes/adaptersqlshort-md.md)], add:</span></span>  
  
        ```  
        <add name="sqlAdapter" type="Microsoft.Adapters.Sql.SqlAdapterBindingElementExtensionElement,Microsoft.Adapters.Sql, Version=<version>, Culture=neutral, PublicKeyToken=<public key>" />  
        ```  
  
    4.  <span data-ttu-id="3397d-256">"BindingExtensions"system.serviceModel\extensions 下にある要素を検索します。</span><span class="sxs-lookup"><span data-stu-id="3397d-256">Search for the element "bindingExtensions" under system.serviceModel\extensions.</span></span>  
  
    5.  <span data-ttu-id="3397d-257">"BindingExtensions"ノードの下の次のセクションを追加します。</span><span class="sxs-lookup"><span data-stu-id="3397d-257">Add the following section under the "bindingExtensions" node.</span></span>  
  
         <span data-ttu-id="3397d-258">[!INCLUDE[adaptersqlshort](../../includes/adaptersqlshort-md.md)]を追加します。</span><span class="sxs-lookup"><span data-stu-id="3397d-258">For [!INCLUDE[adaptersqlshort](../../includes/adaptersqlshort-md.md)], add:</span></span>  
  
        ```  
        <add name="sqlBinding" type="Microsoft.Adapters.Sql.SqlAdapterBindingCollectionElement,Microsoft.Adapters.Sql, Version=<version>, Culture=neutral, PublicKeyToken=<public key>" />  
        ```  
  
      
  
4.  <span data-ttu-id="3397d-259">machine.config ファイルを保存して閉じます。</span><span class="sxs-lookup"><span data-stu-id="3397d-259">Save and close the machine.config file.</span></span>  
  
<a name="BKMK_PubKey"></a>   
#### <a name="determining-the-public-key-and-version"></a><span data-ttu-id="3397d-260">公開キーとバージョンを決定します。</span><span class="sxs-lookup"><span data-stu-id="3397d-260">Determining the Public Key and Version</span></span>  
<span data-ttu-id="3397d-261">公開キーとバージョンを確認するのには、次の手順を完了、[!INCLUDE[adaptersqlshort](../../includes/adaptersqlshort-md.md)]です。</span><span class="sxs-lookup"><span data-stu-id="3397d-261">Complete the following steps to determine the public key and version for the [!INCLUDE[adaptersqlshort](../../includes/adaptersqlshort-md.md)].</span></span>  
  
1.  <span data-ttu-id="3397d-262">Windows ディレクトリの通常 C:\WINDOWS\assembly に移動します。</span><span class="sxs-lookup"><span data-stu-id="3397d-262">Navigate to the Windows directory, typically C:\WINDOWS\assembly.</span></span>  
  
2.  <span data-ttu-id="3397d-263">対象の公開キーを指定してを選択し、DLL を右クリックして**プロパティ**です。</span><span class="sxs-lookup"><span data-stu-id="3397d-263">Right-click the DLL for which you want the public key, and then select **Properties**.</span></span> <span data-ttu-id="3397d-264">次の表の Dll の名前、[!INCLUDE[adaptersqlshort](../../includes/adaptersqlshort-md.md)]です。</span><span class="sxs-lookup"><span data-stu-id="3397d-264">The following table lists the name of the DLLs for the [!INCLUDE[adaptersqlshort](../../includes/adaptersqlshort-md.md)].</span></span>  
  
    |<span data-ttu-id="3397d-265">[アダプター]</span><span class="sxs-lookup"><span data-stu-id="3397d-265">Adapter</span></span>|<span data-ttu-id="3397d-266">DLL の名前</span><span class="sxs-lookup"><span data-stu-id="3397d-266">Name of the DLL</span></span>|  
    |---|---|  
    |[!INCLUDE[adaptersqlshort](../../includes/adaptersqlshort-md.md)]|<span data-ttu-id="3397d-267">Microsoft.Adapters.Sql.dll</span><span class="sxs-lookup"><span data-stu-id="3397d-267">Microsoft.Adapters.Sql.dll</span></span>|  
  
3.  <span data-ttu-id="3397d-268">**全般** タブの値と比較、**公開キー トークンの**ラベルは、DLL の公開キーを指定します。</span><span class="sxs-lookup"><span data-stu-id="3397d-268">On the **General** tab, the value against the **Public Key Token** label specifies the public key for the DLL.</span></span> <span data-ttu-id="3397d-269">同様の値と比較、**バージョン**ラベルは、DLL のバージョン番号を指定します。</span><span class="sxs-lookup"><span data-stu-id="3397d-269">Similarly, the value against the **Version** label specifies the version number for the DLL.</span></span>  
  
4.  <span data-ttu-id="3397d-270">公開キーをコピーし、をクリックして**キャンセル**です。</span><span class="sxs-lookup"><span data-stu-id="3397d-270">Copy the public key, and then click **Cancel**.</span></span>  
  
<a name="BKMK_Modify_Adap"></a>   
## <a name="update-or-change-the-sql-adapter-installation"></a><span data-ttu-id="3397d-271">更新または変更する SQL アダプターのインストール</span><span class="sxs-lookup"><span data-stu-id="3397d-271">Update or change the SQL adapter installation</span></span>  
 <span data-ttu-id="3397d-272">変更するのには、次の手順を実行、[!INCLUDE[adaptersqlshort](../../includes/adaptersqlshort-md.md)]インストールします。</span><span class="sxs-lookup"><span data-stu-id="3397d-272">Perform the following steps to modify the [!INCLUDE[adaptersqlshort](../../includes/adaptersqlshort-md.md)] installation.</span></span> <span data-ttu-id="3397d-273">あるかどうかを確認、[!INCLUDE[adaptersqlshort](../../includes/adaptersqlshort-md.md)]を変更するセットアップ ウィザードを実行する前にインストールされている、[!INCLUDE[adaptersqlshort](../../includes/adaptersqlshort-md.md)]インストールします。</span><span class="sxs-lookup"><span data-stu-id="3397d-273">Make sure you have the [!INCLUDE[adaptersqlshort](../../includes/adaptersqlshort-md.md)] installed before you run the setup wizard to modify the [!INCLUDE[adaptersqlshort](../../includes/adaptersqlshort-md.md)] installation.</span></span>  
  
 <span data-ttu-id="3397d-274">変更することができます、[!INCLUDE[adaptersqlshort](../../includes/adaptersqlshort-md.md)]次の 2 つの方法でインストールします。</span><span class="sxs-lookup"><span data-stu-id="3397d-274">You can modify the [!INCLUDE[adaptersqlshort](../../includes/adaptersqlshort-md.md)] installation in the following two ways:</span></span>  
  
-   <span data-ttu-id="3397d-275">**対話モードで**セットアップ ウィザードを実行しています。</span><span class="sxs-lookup"><span data-stu-id="3397d-275">**In interactive mode** by running the setup wizard.</span></span>  
  
-   <span data-ttu-id="3397d-276">**サイレント モードで**コマンドラインを使用しています。</span><span class="sxs-lookup"><span data-stu-id="3397d-276">**In silent mode** by using the command line.</span></span>  
  
#### <a name="update-the-sql-adapter-installation-in-interactive-mode"></a><span data-ttu-id="3397d-277">対話モードで SQL アダプターのインストールを更新します。</span><span class="sxs-lookup"><span data-stu-id="3397d-277">Update the SQL Adapter installation in interactive mode</span></span>  
  
1.  <span data-ttu-id="3397d-278">をクリックして**開始**、順にクリック**コントロール パネルの** です。</span><span class="sxs-lookup"><span data-stu-id="3397d-278">Click **Start**, and then click **Control Panel**.</span></span>  
  
2.  <span data-ttu-id="3397d-279">コントロール パネルで、ダブルクリック**プログラムと機能**します。</span><span class="sxs-lookup"><span data-stu-id="3397d-279">In Control Panel, double-click **Programs and Features**.</span></span>  
  
3.  <span data-ttu-id="3397d-280">**プログラムと機能**ウィンドウで、 **Microsoft BizTalk Adapter for SQL Server**、クリックして**変更**です。</span><span class="sxs-lookup"><span data-stu-id="3397d-280">In the **Programs and Features** window, select **Microsoft BizTalk Adapter for SQL Server**, and then click **Change**.</span></span>  
  
4.  <span data-ttu-id="3397d-281">[ようこそ] 画面で、情報を参照し、をクリックして**次**です。</span><span class="sxs-lookup"><span data-stu-id="3397d-281">Read the information on the Welcome screen, and then click **Next**.</span></span>  
  
5.  <span data-ttu-id="3397d-282">**変更、修復、または削除インストール**ダイアログ ボックスで、をクリックして**修復**です。</span><span class="sxs-lookup"><span data-stu-id="3397d-282">In the **Change, repair, or remove installation** dialog box, click **Repair**.</span></span>  
  
6.  <span data-ttu-id="3397d-283">**SQL Server 用 Microsoft BizTalk Adapter を修復する準備が**ダイアログ ボックスで、をクリックして**修復**です。</span><span class="sxs-lookup"><span data-stu-id="3397d-283">In the **Ready to repair Microsoft BizTalk Adapter for SQL Server** dialog box, click **Repair**.</span></span>  
  
7.  <span data-ttu-id="3397d-284">必要に応じて、ユーザーの設定を変更に関して、CEIP を無効にして、をクリックして**OK**です。</span><span class="sxs-lookup"><span data-stu-id="3397d-284">If required, change your preferences regarding opting for CEIP, and then click **OK**.</span></span>  
  
8.  <span data-ttu-id="3397d-285">**[完了]** をクリックします。</span><span class="sxs-lookup"><span data-stu-id="3397d-285">Click **Finish**.</span></span>  
  
#### <a name="update-the-sql-adapter-installation-in-silent-mode"></a><span data-ttu-id="3397d-286">更新プログラムのサイレント モードで SQL アダプターのインストール</span><span class="sxs-lookup"><span data-stu-id="3397d-286">Update the SQL Adapter installation in silent mode</span></span>  
  
1.  <span data-ttu-id="3397d-287">コマンド プロンプトを開きのルート ディレクトリに移動、[!INCLUDE[adaptersqlshort](../../includes/adaptersqlshort-md.md)]インストーラーです。</span><span class="sxs-lookup"><span data-stu-id="3397d-287">Open a command prompt, and navigate to the root directory of the [!INCLUDE[adaptersqlshort](../../includes/adaptersqlshort-md.md)] installer.</span></span>  
  
2.  <span data-ttu-id="3397d-288">次のコマンドを実行します。</span><span class="sxs-lookup"><span data-stu-id="3397d-288">Run the following command:</span></span>  
  
    > [!NOTE]
    >  <span data-ttu-id="3397d-289">変更する、 [!INCLUDE[adaptersqlshort](../../includes/adaptersqlshort-md.md)] SqlAdapterSetup64.msi で次のコマンドでの x64 ベースのプラットフォームにサイレント モードでインストールが SqlAdapterSetup.msi を置き換えます。</span><span class="sxs-lookup"><span data-stu-id="3397d-289">To modify the [!INCLUDE[adaptersqlshort](../../includes/adaptersqlshort-md.md)] installation in silent mode on an x64-based platform, in the following commands, replace SqlAdapterSetup.msi with SqlAdapterSetup64.msi.</span></span>  
  
    ```  
    msiexec /i SqlAdapterSetup.msi /qn /f  
    ```  
  
    > [!IMPORTANT]
    >  <span data-ttu-id="3397d-290">変更中に、[!INCLUDE[adaptersqlshort](../../includes/adaptersqlshort-md.md)]サイレント モードでインストールで CEIP を有効または無効にするための設定を変更することはできません。</span><span class="sxs-lookup"><span data-stu-id="3397d-290">While modifying the [!INCLUDE[adaptersqlshort](../../includes/adaptersqlshort-md.md)] installation in the silent mode, you cannot change your preferences for opting in or out of CEIP.</span></span> <span data-ttu-id="3397d-291">環境設定は変わりません、インストール時に指定したとおり、CEIP_OPTIN を true または false に明示的に設定した場合でもです。</span><span class="sxs-lookup"><span data-stu-id="3397d-291">The preferences will remain the same as you specified during the installation, even if you explicitly set the CEIP_OPTIN to true or false.</span></span>  
  
     <span data-ttu-id="3397d-292">詳細については、`msiexec`コマンドを入力`msiexec`キーを押して、コマンド ライン`ENTER`を参照してくださいまたは[https://support.microsoft.com/kb/230781](https://support.microsoft.com/kb/230781)です。</span><span class="sxs-lookup"><span data-stu-id="3397d-292">For more information about the `msiexec` command, type `msiexec` on the command line and press `ENTER`, or see [https://support.microsoft.com/kb/230781](https://support.microsoft.com/kb/230781).</span></span>   
  
<a name="BKMK_Remove_Adap"></a>   
## <a name="uninstall-or-remove-the-sql-adapter"></a><span data-ttu-id="3397d-293">アンインストールするか、SQL アダプターを削除します。</span><span class="sxs-lookup"><span data-stu-id="3397d-293">Uninstall or remove the SQL Adapter</span></span>  
 <span data-ttu-id="3397d-294">削除するには、次の手順を実行、[!INCLUDE[adaptersqlshort](../../includes/adaptersqlshort-md.md)]コンピューターからです。</span><span class="sxs-lookup"><span data-stu-id="3397d-294">Perform the following steps to remove the [!INCLUDE[adaptersqlshort](../../includes/adaptersqlshort-md.md)] from your computer.</span></span> <span data-ttu-id="3397d-295">あるかどうかを確認、[!INCLUDE[afproductnameshort](../../includes/afproductnameshort-md.md)]を削除するセットアップ ウィザードを実行する前にインストールされている、[!INCLUDE[adaptersqlshort](../../includes/adaptersqlshort-md.md)]です。</span><span class="sxs-lookup"><span data-stu-id="3397d-295">Make sure you have the [!INCLUDE[afproductnameshort](../../includes/afproductnameshort-md.md)] installed before you run the setup wizard to remove the [!INCLUDE[adaptersqlshort](../../includes/adaptersqlshort-md.md)].</span></span>  
  
 <span data-ttu-id="3397d-296">削除することができます、[!INCLUDE[adaptersqlshort](../../includes/adaptersqlshort-md.md)]次の 2 つの方法で。</span><span class="sxs-lookup"><span data-stu-id="3397d-296">You can remove the [!INCLUDE[adaptersqlshort](../../includes/adaptersqlshort-md.md)] in the following two ways:</span></span>  
  
-   <span data-ttu-id="3397d-297">**対話モードで**セットアップ ウィザードを実行しています。</span><span class="sxs-lookup"><span data-stu-id="3397d-297">**In interactive mode** by running the setup wizard.</span></span>  
  
-   <span data-ttu-id="3397d-298">**サイレント モードで**コマンドラインを使用しています。</span><span class="sxs-lookup"><span data-stu-id="3397d-298">**In silent mode** by using the command line.</span></span>  
  
#### <a name="uninstall-in-interactive-mode"></a><span data-ttu-id="3397d-299">対話モードでアンインストールします。</span><span class="sxs-lookup"><span data-stu-id="3397d-299">Uninstall in interactive mode</span></span>  
  
1.  <span data-ttu-id="3397d-300">をクリックして**開始**、順にクリック**コントロール パネルの** です。</span><span class="sxs-lookup"><span data-stu-id="3397d-300">Click **Start**, and then click **Control Panel**.</span></span>  
  
2.  <span data-ttu-id="3397d-301">コントロール パネルで、ダブルクリック**プログラムと機能**します。</span><span class="sxs-lookup"><span data-stu-id="3397d-301">In Control Panel, double-click  **Programs and Features**.</span></span>  
  
3.  <span data-ttu-id="3397d-302">**プログラム追加と削除**ウィンドウで、 **Microsoft BizTalk Adapter for SQL Server**、クリックして**削除**です。</span><span class="sxs-lookup"><span data-stu-id="3397d-302">In the **Add or Remove Programs** window, select **Microsoft BizTalk Adapter for SQL Server**, and then click **Remove**.</span></span>  
  
4.  <span data-ttu-id="3397d-303">ダイアログ ボックスで、**はい**です。</span><span class="sxs-lookup"><span data-stu-id="3397d-303">In the dialog box, click **Yes**.</span></span>  
  
#### <a name="uninstall-in-silent-mode"></a><span data-ttu-id="3397d-304">サイレント モードでアンインストールします。</span><span class="sxs-lookup"><span data-stu-id="3397d-304">Uninstall in silent mode</span></span>  
  
1.  <span data-ttu-id="3397d-305">コマンド プロンプトを開きのルート ディレクトリに移動、[!INCLUDE[adaptersqlshort](../../includes/adaptersqlshort-md.md)]インストーラーです。</span><span class="sxs-lookup"><span data-stu-id="3397d-305">Open a command prompt, and navigate to the root directory of the [!INCLUDE[adaptersqlshort](../../includes/adaptersqlshort-md.md)] installer.</span></span>  
  
2.  <span data-ttu-id="3397d-306">次のコマンドを実行します。</span><span class="sxs-lookup"><span data-stu-id="3397d-306">Run the following command:</span></span>  
  
    > [!NOTE]
    >  <span data-ttu-id="3397d-307">削除する、[!INCLUDE[adaptersqlshort](../../includes/adaptersqlshort-md.md)]サイレント モードで、次のコマンドの x64 ベースのプラットフォーム上で SqlAdapterSetup64.msi で SqlAdapterSetup.msi を置き換えます。</span><span class="sxs-lookup"><span data-stu-id="3397d-307">To remove the [!INCLUDE[adaptersqlshort](../../includes/adaptersqlshort-md.md)] in silent mode on an x64-based platform, in the following commands, replace SqlAdapterSetup.msi with SqlAdapterSetup64.msi.</span></span>  
  
    ```  
    msiexec /x SqlAdapterSetup.msi /qn  
    ```  
  
     <span data-ttu-id="3397d-308">このコマンドを削除、[!INCLUDE[adaptersqlshort](../../includes/adaptersqlshort-md.md)]コンピューターからです。</span><span class="sxs-lookup"><span data-stu-id="3397d-308">This command removes the [!INCLUDE[adaptersqlshort](../../includes/adaptersqlshort-md.md)] from the computer.</span></span>  
  
     <span data-ttu-id="3397d-309">詳細については、`msiexec`コマンドを入力`msiexec`キーを押して、コマンド ライン`ENTER`を参照してくださいまたは[https://support.microsoft.com/kb/230781](https://support.microsoft.com/kb/230781)です。</span><span class="sxs-lookup"><span data-stu-id="3397d-309">For more information about the `msiexec` command, type `msiexec` on the command line and press `ENTER`, or see [https://support.microsoft.com/kb/230781](https://support.microsoft.com/kb/230781).</span></span>  
  
<a name="BKMK_PostRemove"></a>   
### <a name="post-uninstall-task"></a><span data-ttu-id="3397d-310">アンインストール後のタスク</span><span class="sxs-lookup"><span data-stu-id="3397d-310">Post-uninstall task</span></span>  
 <span data-ttu-id="3397d-311">場合、[!INCLUDE[adaptersqlshort](../../includes/adaptersqlshort-md.md)]バインドを削除する、アダプターの削除中にセットアップが失敗した、 [!INCLUDE[adaptersqlshort](../../includes/adaptersqlshort-md.md)]、それらを手動で削除する必要があります。</span><span class="sxs-lookup"><span data-stu-id="3397d-311">If the [!INCLUDE[adaptersqlshort](../../includes/adaptersqlshort-md.md)] setup fails to remove the adapter bindings while removing the [!INCLUDE[adaptersqlshort](../../includes/adaptersqlshort-md.md)], you must remove them manually.</span></span> <span data-ttu-id="3397d-312">次のセクションのバインドを手動で削除する方法について説明、[!INCLUDE[adaptersqlshort](../../includes/adaptersqlshort-md.md)]です。</span><span class="sxs-lookup"><span data-stu-id="3397d-312">The following section describes how to manually remove the bindings for the [!INCLUDE[adaptersqlshort](../../includes/adaptersqlshort-md.md)].</span></span>  
  
<a name="BKMK_Remove_Binding"></a>   
#### <a name="manually-remove-the-bindings"></a><span data-ttu-id="3397d-313">バインドを手動で削除します。</span><span class="sxs-lookup"><span data-stu-id="3397d-313">Manually remove the bindings</span></span>  
 <span data-ttu-id="3397d-314">次の手順を実行*のみ*バインドを削除する、アダプター、machine.config ファイルから、セットアップ ウィザードが失敗した場合。</span><span class="sxs-lookup"><span data-stu-id="3397d-314">Perform these steps *only* if the setup wizard fails to remove the adapter bindings from the machine.config file.</span></span>  
  
1.  <span data-ttu-id="3397d-315">コンピューター上の machine.config ファイルに移動します。</span><span class="sxs-lookup"><span data-stu-id="3397d-315">Navigate to the machine.config file on the computer.</span></span> <span data-ttu-id="3397d-316">たとえば、32 ビット プラットフォームで、machine.config は下にある使用可能な\<システム ドライブ\>: \WINDOWS\Microsoft.NET\Framework\\< バージョン\>\CONFIG です。</span><span class="sxs-lookup"><span data-stu-id="3397d-316">For example, on a 32-bit platform, the machine.config is available under \<system drive\>:\WINDOWS\Microsoft.NET\Framework\\<version\>\CONFIG.</span></span>  
  
    -   <span data-ttu-id="3397d-317">Microsoft .NET framework 3.5 SP1、 \<*バージョン*\> .NET Framework のバージョン v2.0.50727 がします。</span><span class="sxs-lookup"><span data-stu-id="3397d-317">For Microsoft .NET Framework 3.5 SP1, \<*version*\> is the version v2.0.50727 of the .NET Framework.</span></span>  
  
    -   <span data-ttu-id="3397d-318">Microsoft の[!INCLUDE[netfx40_short](../../includes/netfx40-short-md.md)]、 \<*バージョン*\>は、.NET Framework のバージョン v4.0.30319 します。</span><span class="sxs-lookup"><span data-stu-id="3397d-318">For Microsoft [!INCLUDE[netfx40_short](../../includes/netfx40-short-md.md)], \<*version*\> is the version v4.0.30319 of the .NET Framework.</span></span>  
  
2.  <span data-ttu-id="3397d-319">テキスト エディターを使用してファイルを開きます。</span><span class="sxs-lookup"><span data-stu-id="3397d-319">Open the file using a text editor.</span></span>  
  
3.  <span data-ttu-id="3397d-320">アダプターのバインドの登録を削除します。</span><span class="sxs-lookup"><span data-stu-id="3397d-320">To remove the adapter binding registration:</span></span>  
  
    1.  <span data-ttu-id="3397d-321">要素"system.serviceModel"を検索し、次の要素の下を削除します。</span><span class="sxs-lookup"><span data-stu-id="3397d-321">Search for the element "system.serviceModel" and remove the following from under the element:</span></span>  
  
        ```  
        <client>  
          <endpoint binding="sqlBinding" contract="IMetadataExchange" name="mssql" />  
        </client>  
  
        ```  
  
    2.  <span data-ttu-id="3397d-322">"BindingElementExtensions"system.serviceModel\extensions 下にある要素を検索します。</span><span class="sxs-lookup"><span data-stu-id="3397d-322">Search for the element "bindingElementExtensions" under system.serviceModel\extensions.</span></span>  
  
    3.  <span data-ttu-id="3397d-323">"BindingElementExtensions"ノードの下に、次のセクションを削除します。</span><span class="sxs-lookup"><span data-stu-id="3397d-323">Remove the following section under the "bindingElementExtensions" node.</span></span>  
  
         <span data-ttu-id="3397d-324">[!INCLUDE[adaptersqlshort](../../includes/adaptersqlshort-md.md)]、削除します。</span><span class="sxs-lookup"><span data-stu-id="3397d-324">For [!INCLUDE[adaptersqlshort](../../includes/adaptersqlshort-md.md)], remove:</span></span>  
  
        ```  
        <add name="sqlAdapter" type="Microsoft.Adapters.Sql.SqlAdapterBindingElementExtensionElement,Microsoft.Adapters.Sql, Version=<version>, Culture=neutral, PublicKeyToken=<public key>" />  
        ```  
  
    4.  <span data-ttu-id="3397d-325">"BindingExtensions"system.serviceModel\extensions 下にある要素を検索します。</span><span class="sxs-lookup"><span data-stu-id="3397d-325">Search for the element "bindingExtensions" under system.serviceModel\extensions.</span></span>  
  
    5.  <span data-ttu-id="3397d-326">"BindingExtensions"ノードの下に、次のセクションを削除します。</span><span class="sxs-lookup"><span data-stu-id="3397d-326">Remove the following section under the "bindingExtensions" node.</span></span>  
  
         <span data-ttu-id="3397d-327">[!INCLUDE[adaptersqlshort](../../includes/adaptersqlshort-md.md)]、削除します。</span><span class="sxs-lookup"><span data-stu-id="3397d-327">For [!INCLUDE[adaptersqlshort](../../includes/adaptersqlshort-md.md)], remove:</span></span>  
  
        ```  
        <add name="sqlBinding" type="Microsoft.Adapters.Sql.SqlAdapterBindingCollectionElement,Microsoft.Adapters.Sql, Version=<version>, Culture=neutral, PublicKeyToken=<public key>" />  
        ```  
  
4.  <span data-ttu-id="3397d-328">machine.config ファイルを保存して閉じます。</span><span class="sxs-lookup"><span data-stu-id="3397d-328">Save and close the machine.config file.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="3397d-329">参照</span><span class="sxs-lookup"><span data-stu-id="3397d-329">See also</span></span>
[<span data-ttu-id="3397d-330">SQL アダプターをインストールする</span><span class="sxs-lookup"><span data-stu-id="3397d-330">Install the SQL adapter</span></span>](../../adapters-and-accelerators/adapter-sql/install-the-sql-adapter.md)  
[<span data-ttu-id="3397d-331">BizTalk Adapter for SQL Server を理解する</span><span class="sxs-lookup"><span data-stu-id="3397d-331">Understand BizTalk Adapter for SQL Server</span></span>](../../adapters-and-accelerators/adapter-sql/understand-biztalk-adapter-for-sql-server.md)