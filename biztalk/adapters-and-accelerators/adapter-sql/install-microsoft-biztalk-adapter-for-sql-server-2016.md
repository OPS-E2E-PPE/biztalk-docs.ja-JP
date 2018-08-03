---
title: Microsoft BizTalk Adapter for SQL Server - 2016 のインストール |Microsoft Docs
ms.custom: ''
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: ''
ms.suite: ''
ms.tgt_pltfrm: ''
ms.topic: article
ms.assetid: bcc6b94e-1cac-4b90-8567-05b33caa9bf3
caps.latest.revision: 5
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: 65205828e4ab178a0fec29c37cc1854f6a570242
ms.sourcegitcommit: 266308ec5c6a9d8d80ff298ee6051b4843c5d626
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 06/27/2018
ms.locfileid: "36966979"
---
# <a name="install-microsoft-biztalk-adapter-for-sql-server---2016"></a><span data-ttu-id="3abf8-102">Microsoft BizTalk Adapter for SQL Server - 2016 のインストールします。</span><span class="sxs-lookup"><span data-stu-id="3abf8-102">Install Microsoft BizTalk Adapter for SQL Server - 2016</span></span>
<span data-ttu-id="3abf8-103">インストール、[!INCLUDE[adaptersql_md](../../includes/adaptersql-md.md)]に含まれている[!INCLUDE[bts2016_md](../../includes/bts2016-md.md)]します。</span><span class="sxs-lookup"><span data-stu-id="3abf8-103">Install the [!INCLUDE[adaptersql_md](../../includes/adaptersql-md.md)] included with [!INCLUDE[bts2016_md](../../includes/bts2016-md.md)].</span></span>

 <span data-ttu-id="3abf8-104">[!INCLUDE[adaptersqlshort](../../includes/adaptersqlshort-md.md)]で使用できます。</span><span class="sxs-lookup"><span data-stu-id="3abf8-104">The [!INCLUDE[adaptersqlshort](../../includes/adaptersqlshort-md.md)] can be used with:</span></span>  

- <span data-ttu-id="3abf8-105">.NET アプリケーション</span><span class="sxs-lookup"><span data-stu-id="3abf8-105">A .NET application</span></span>  

- <span data-ttu-id="3abf8-106">Microsoft [!INCLUDE[btsBizTalkServerNoVersion](../../includes/btsbiztalkservernoversion-md.md)]</span><span class="sxs-lookup"><span data-stu-id="3abf8-106">Microsoft [!INCLUDE[btsBizTalkServerNoVersion](../../includes/btsbiztalkservernoversion-md.md)]</span></span>  

  <span data-ttu-id="3abf8-107">アダプターを使用する方法に基づき、必要なソフトウェアによって異なります。</span><span class="sxs-lookup"><span data-stu-id="3abf8-107">Based on how you use the adapters, the required software varies.</span></span>  


<a name="BKMK_prereq_NET"></a>   
## <a name="prerequisites-when-using-the-adapter-with-a-net-application"></a><span data-ttu-id="3abf8-108">.NET アプリケーション、アダプターを使用する際の前提条件</span><span class="sxs-lookup"><span data-stu-id="3abf8-108">Prerequisites when using the adapter with a .NET Application</span></span>  
<span data-ttu-id="3abf8-109">次のソフトウェアを使用する .NET アプリケーションを作成するコンピューターにインストール、[!INCLUDE[adaptersqlshort](../../includes/adaptersqlshort-md.md)]します。</span><span class="sxs-lookup"><span data-stu-id="3abf8-109">Install the following software on the computer where you are writing .NET applications that consume the [!INCLUDE[adaptersqlshort](../../includes/adaptersqlshort-md.md)].</span></span> <span data-ttu-id="3abf8-110">記載されている順序で、ソフトウェアをインストールします。</span><span class="sxs-lookup"><span data-stu-id="3abf8-110">Install the software in the order as listed.</span></span>  

||
|---|
|<span data-ttu-id="3abf8-111">Windows Server 2016</span><span class="sxs-lookup"><span data-stu-id="3abf8-111">- Windows Server 2016</span></span> <br /><span data-ttu-id="3abf8-112">-Windows Server 2012 R2</span><span class="sxs-lookup"><span data-stu-id="3abf8-112">- Windows Server 2012 R2</span></span> <br /><span data-ttu-id="3abf8-113">Windows 10</span><span class="sxs-lookup"><span data-stu-id="3abf8-113">- Windows 10</span></span> <br /><span data-ttu-id="3abf8-114">-Windows 8.1</span><span class="sxs-lookup"><span data-stu-id="3abf8-114">- Windows 8.1</span></span>    |
|<span data-ttu-id="3abf8-115">.NET Framework 4.6.*x*</span><span class="sxs-lookup"><span data-stu-id="3abf8-115">.NET Framework 4.6.*x*</span></span>|
|<span data-ttu-id="3abf8-116">Visual Studio 2015</span><span class="sxs-lookup"><span data-stu-id="3abf8-116">Visual Studio 2015</span></span>|
|[!INCLUDE[afproductnameshort](../../includes/afproductnameshort-md.md)]|
|<span data-ttu-id="3abf8-117">SQL Server のクライアント ライブラリ。</span><span class="sxs-lookup"><span data-stu-id="3abf8-117">SQL Server client libraries.</span></span> <span data-ttu-id="3abf8-118">参照してください、[サポートされているバージョン](#BKMK_SuppLOB)(」を参照)。</span><span class="sxs-lookup"><span data-stu-id="3abf8-118">See the [supported versions](#BKMK_SuppLOB) (in this topic).</span></span>|

<a name="BKMK_prereq_BTS"></a>     
## <a name="prerequisites-when-using-the-adapter-with-biztalk-server"></a><span data-ttu-id="3abf8-119">BizTalk Server でアダプターを使用する場合の前提条件</span><span class="sxs-lookup"><span data-stu-id="3abf8-119">Prerequisites when using the adapter with BizTalk Server</span></span>  
<span data-ttu-id="3abf8-120">次のソフトウェアを使用しているコンピューターにインストール、[!INCLUDE[adaptersqlshort](../../includes/adaptersqlshort-md.md)]で[!INCLUDE[btsBizTalkServerNoVersion](../../includes/btsbiztalkservernoversion-md.md)]します。</span><span class="sxs-lookup"><span data-stu-id="3abf8-120">Install the following software on the computer where you are using the [!INCLUDE[adaptersqlshort](../../includes/adaptersqlshort-md.md)] with [!INCLUDE[btsBizTalkServerNoVersion](../../includes/btsbiztalkservernoversion-md.md)].</span></span> <span data-ttu-id="3abf8-121">表示された順に、ソフトウェアをインストールします。</span><span class="sxs-lookup"><span data-stu-id="3abf8-121">Install the software in the order listed.</span></span>  

||
|---|
|<span data-ttu-id="3abf8-122">Windows Server 2016</span><span class="sxs-lookup"><span data-stu-id="3abf8-122">- Windows Server 2016</span></span> <br /><span data-ttu-id="3abf8-123">-Windows Server 2012 R2</span><span class="sxs-lookup"><span data-stu-id="3abf8-123">- Windows Server 2012 R2</span></span> <br /><span data-ttu-id="3abf8-124">Windows 10</span><span class="sxs-lookup"><span data-stu-id="3abf8-124">- Windows 10</span></span> <br /><span data-ttu-id="3abf8-125">-Windows 8.1</span><span class="sxs-lookup"><span data-stu-id="3abf8-125">- Windows 8.1</span></span>    |
|<span data-ttu-id="3abf8-126">.NET Framework 4.6.*x*</span><span class="sxs-lookup"><span data-stu-id="3abf8-126">.NET Framework 4.6.*x*</span></span>|
|<span data-ttu-id="3abf8-127">Visual Studio 2015</span><span class="sxs-lookup"><span data-stu-id="3abf8-127">Visual Studio 2015</span></span>|
|[!INCLUDE[afproductnameshort](../../includes/afproductnameshort-md.md)]<br /><br /> <span data-ttu-id="3abf8-128">インストール、[!INCLUDE[consumeadapterservlong](../../includes/consumeadapterservlong-md.md)]の[!INCLUDE[btsVStudioNoVersion](../../includes/btsvstudionoversion-md.md)]に含まれている、[!INCLUDE[afproductnameshort](../../includes/afproductnameshort-md.md)]します。</span><span class="sxs-lookup"><span data-stu-id="3abf8-128">Install the [!INCLUDE[consumeadapterservlong](../../includes/consumeadapterservlong-md.md)] for [!INCLUDE[btsVStudioNoVersion](../../includes/btsvstudionoversion-md.md)] included with the [!INCLUDE[afproductnameshort](../../includes/afproductnameshort-md.md)].</span></span> <span data-ttu-id="3abf8-129">インストールするには、**カスタム**(選択**BizTalk Server アドイン**) または**完了**のインストール、[!INCLUDE[afproductnameshort](../../includes/afproductnameshort-md.md)]します。</span><span class="sxs-lookup"><span data-stu-id="3abf8-129">To install, do a **Custom** (select **BizTalk Server Addin**) or **Complete** installation of the [!INCLUDE[afproductnameshort](../../includes/afproductnameshort-md.md)].</span></span>|
|[!INCLUDE[bts2016_md](../../includes/bts2016-md.md)]|
|<span data-ttu-id="3abf8-130">SQL Server のクライアント ライブラリ。</span><span class="sxs-lookup"><span data-stu-id="3abf8-130">SQL Server client libraries.</span></span> <span data-ttu-id="3abf8-131">参照してください、[サポートされているバージョン](#BKMK_SuppLOB)(」を参照)。</span><span class="sxs-lookup"><span data-stu-id="3abf8-131">See the [supported versions](#BKMK_SuppLOB) (in this topic).</span></span>|

<a name="BKMK_SuppLOB"></a>   
## <a name="supported-sql-server-versions-and-client-libraries"></a><span data-ttu-id="3abf8-132">サポートされている SQL Server のバージョンとクライアント ライブラリ</span><span class="sxs-lookup"><span data-stu-id="3abf8-132">Supported SQL Server versions and client libraries</span></span>  
 <span data-ttu-id="3abf8-133">次のセクションではサポートされている SQL Server のバージョンと、クライアントで必要なライブラリ、[!INCLUDE[adaptersqlshort](../../includes/adaptersqlshort-md.md)]します。</span><span class="sxs-lookup"><span data-stu-id="3abf8-133">The following section presents the supported SQL Server versions and the client libraries required by the [!INCLUDE[adaptersqlshort](../../includes/adaptersqlshort-md.md)].</span></span>  

- <span data-ttu-id="3abf8-134">**サポートされているサーバー バージョン**: SQL Server 2016、SQL Server 2014</span><span class="sxs-lookup"><span data-stu-id="3abf8-134">**Supported server versions**: SQL Server 2016, SQL Server 2014</span></span>

- <span data-ttu-id="3abf8-135">**サポートされているクライアント バージョン**: Microsoft [!INCLUDE[btsDotNetFramework_md](../../includes/btsdotnetframework-md.md)] SQL Server に接続するために必要なクライアント Dll バンドルします。</span><span class="sxs-lookup"><span data-stu-id="3abf8-135">**Supported client versions**: Microsoft [!INCLUDE[btsDotNetFramework_md](../../includes/btsdotnetframework-md.md)] bundles the client DLLs required to connect to SQL Server.</span></span> <span data-ttu-id="3abf8-136">コンピューターに任意のクライアントの Dll を明示的にインストールする必要はありません。</span><span class="sxs-lookup"><span data-stu-id="3abf8-136">You do not need to explicitly install any client DLLs on your computer.</span></span>  

- <span data-ttu-id="3abf8-137">**ドライバーに必要な**:</span><span class="sxs-lookup"><span data-stu-id="3abf8-137">**Required drivers**:</span></span>  

  - <span data-ttu-id="3abf8-138">SQL Server のバージョン、たとえば、geography 型に付属の Udt を使用する場合、次の Dll は SQL Server での操作を実行するアダプターを使用するコンピューター上に存在することを確認します。</span><span class="sxs-lookup"><span data-stu-id="3abf8-138">If you use the UDTs shipped with the SQL Server versions, for example, Geography, make sure the following DLLs are present on the computer where you use the adapter to perform operations on SQL Server.</span></span> <span data-ttu-id="3abf8-139">たとえば、SQL Server での操作を実行する BizTalk プロジェクトを作成する場合これらの Dll は BizTalk Server が実行されているコンピューター上に存在である必要があります。</span><span class="sxs-lookup"><span data-stu-id="3abf8-139">For example, if you create BizTalk projects to perform operations on SQL Server, these DLLs must be present on the computer where BizTalk Server is running.</span></span>  

    - <span data-ttu-id="3abf8-140">Microsoft.SqlServer.Types.dll は GAC に追加することを確認します。</span><span class="sxs-lookup"><span data-stu-id="3abf8-140">Make sure Microsoft.SqlServer.Types.dll is added to the GAC.</span></span>  

    - <span data-ttu-id="3abf8-141">SqlServerSpatial.dll が System32 フォルダーにあることを確認します。</span><span class="sxs-lookup"><span data-stu-id="3abf8-141">Make sure SqlServerSpatial.dll is available in the System32 folder.</span></span>  

      <span data-ttu-id="3abf8-142">コンピューターにこれらの Dll をインストールするには、SQL Server セットアップを実行し、選択**管理ツール-基本**と**管理ツール-完全**で、**機能の選択**ウィザードのページ。</span><span class="sxs-lookup"><span data-stu-id="3abf8-142">You can install these DLLs on the computer by running the SQL Server setup and selecting **Management Tools – Basic** and **Management Tools – Complete** in the **Feature Selection** page of the wizard.</span></span>  

  - <span data-ttu-id="3abf8-143">FILESTREAM データ型の列に対する操作を実行するアダプターを使用する場合は、SQL Client Connectivity SDK がインストールされている必要があることを確認してください。</span><span class="sxs-lookup"><span data-stu-id="3abf8-143">If you use the adapter to perform operations on columns of FILESTREAM data types, make sure you have SQL Client Connectivity SDK installed.</span></span> <span data-ttu-id="3abf8-144">SQL クライアント接続 SDK をインストールするには、SQL Server セットアップを実行し、選択**SQL Client Connectivity SDK**で、**機能の選択**ウィザードのページ。</span><span class="sxs-lookup"><span data-stu-id="3abf8-144">You can install the SQL Client Connectivity SDK by running the SQL Server setup and selecting **SQL Client Connectivity SDK** in the **Feature Selection** page of the wizard.</span></span> <span data-ttu-id="3abf8-145">アダプターは、FILESTREAM 操作を実行するのに SQL クライアント接続 sdk では、インストールされている、sqlncli10.dll を使用します。</span><span class="sxs-lookup"><span data-stu-id="3abf8-145">The adapter uses the sqlncli10.dll, installed with the SQL Client Connectivity SDK, to perform FILESTREAM operations.</span></span>  

  - <span data-ttu-id="3abf8-146">SQL Server で、独自の Udt を作成する場合は、Udt のそれぞれのアセンブリを GAC に追加して確認します。</span><span class="sxs-lookup"><span data-stu-id="3abf8-146">If you create your own UDTs in SQL Server, make sure the respective assemblies for the UDTs are added to the GAC.</span></span>  

<a name="BKMK_Compat"></a>   
## <a name="64-bit-support"></a><span data-ttu-id="3abf8-147">64 ビットのサポート</span><span class="sxs-lookup"><span data-stu-id="3abf8-147">64-bit support</span></span> 

<span data-ttu-id="3abf8-148">[!INCLUDE[adaptersqlshort](../../includes/adaptersqlshort-md.md)] 32 ビットまたは 64 ビット ホスト インスタンスで実行できます。</span><span class="sxs-lookup"><span data-stu-id="3abf8-148">The [!INCLUDE[adaptersqlshort](../../includes/adaptersqlshort-md.md)] can run in a 32-bit or 64-bit host instance.</span></span>

 <span data-ttu-id="3abf8-149">32 ビットおよび 64 ビットのサポートされているインストール シナリオについて[!INCLUDE[adaptersqlshort](../../includes/adaptersqlshort-md.md)]を参照してください[32 ビットおよび 64 ビット インストール シナリオ](#BKMK_Install_Scenarios)(」を参照)。</span><span class="sxs-lookup"><span data-stu-id="3abf8-149">For information about the supported installation scenarios for the 32-bit and 64-bit [!INCLUDE[adaptersqlshort](../../includes/adaptersqlshort-md.md)], see  [32-bit and 64-bit install scenarios](#BKMK_Install_Scenarios) (in this topic).</span></span>

<a name="BKMK_Install_Adap"></a>   
## <a name="install-the-sql-adapter"></a><span data-ttu-id="3abf8-150">SQL アダプターをインストールします。</span><span class="sxs-lookup"><span data-stu-id="3abf8-150">Install the SQL adapter</span></span>  
 <span data-ttu-id="3abf8-151">インストールする前にインストールされている前提条件があるかどうかを確認、[!INCLUDE[adaptersqlshort](../../includes/adaptersqlshort-md.md)]します。</span><span class="sxs-lookup"><span data-stu-id="3abf8-151">Make sure you have the prerequisites installed before installing the [!INCLUDE[adaptersqlshort](../../includes/adaptersqlshort-md.md)].</span></span> <span data-ttu-id="3abf8-152">参照してください[.NET の前提条件](#BKMK_prereq_NET)(このトピックの)、または[BizTalk Server の前提条件](#BKMK_prereq_BTS)(」を参照)。</span><span class="sxs-lookup"><span data-stu-id="3abf8-152">See [.NET prerequisites](#BKMK_prereq_NET) (in this topic), or [BizTalk Server prerequisites](#BKMK_prereq_BTS) (in this topic).</span></span>

 <span data-ttu-id="3abf8-153">インストールすることができます、[!INCLUDE[adaptersqlshort](../../includes/adaptersqlshort-md.md)]次の 2 つの方法で。</span><span class="sxs-lookup"><span data-stu-id="3abf8-153">You can install the [!INCLUDE[adaptersqlshort](../../includes/adaptersqlshort-md.md)] in the following two ways:</span></span>  

- <span data-ttu-id="3abf8-154">**対話モードで**セットアップ ウィザードを使用</span><span class="sxs-lookup"><span data-stu-id="3abf8-154">**In interactive mode** using the setup wizard</span></span>

- <span data-ttu-id="3abf8-155">**サイレント モードで**コマンド ラインで msiexec を使用します。</span><span class="sxs-lookup"><span data-stu-id="3abf8-155">**In silent mode** using msiexec in the command line</span></span>  

  > [!IMPORTANT]
  >  <span data-ttu-id="3abf8-156">インストールするコンピューターで管理者特権が必要、[!INCLUDE[adaptersqlshort](../../includes/adaptersqlshort-md.md)]のウィザードまたはコマンドラインを使用してインストールするかどうかに関係なく、します。</span><span class="sxs-lookup"><span data-stu-id="3abf8-156">You must have administrative privileges on the computer where you install the [!INCLUDE[adaptersqlshort](../../includes/adaptersqlshort-md.md)], irrespective of whether you are installing by using the wizard or the command line.</span></span>    

### <a name="BKMK_Install_Scenarios"></a> <span data-ttu-id="3abf8-157">32 ビットおよび 64 ビット インストール シナリオ</span><span class="sxs-lookup"><span data-stu-id="3abf8-157">32-bit and 64-bit install scenarios</span></span>
 <span data-ttu-id="3abf8-158">[!INCLUDE[btsBizTalkServerNoVersion](../../includes/btsbiztalkservernoversion-md.md)]、[!INCLUDE[adaptersqlshort](../../includes/adaptersqlshort-md.md)]に使用できます。</span><span class="sxs-lookup"><span data-stu-id="3abf8-158">With [!INCLUDE[btsBizTalkServerNoVersion](../../includes/btsbiztalkservernoversion-md.md)], the [!INCLUDE[adaptersqlshort](../../includes/adaptersqlshort-md.md)] can be used for:</span></span>  

- [!INCLUDE[btsVStudioNoVersion](../../includes/btsvstudionoversion-md.md)]<span data-ttu-id="3abf8-159"> デザイン時 (操作のメタデータを生成) するときにします。</span><span class="sxs-lookup"><span data-stu-id="3abf8-159"> design time (when generating metadata for operations).</span></span>  

- <span data-ttu-id="3abf8-160">(物理ポートを作成) するための BizTalk Server 管理コンソールのデザイン時。</span><span class="sxs-lookup"><span data-stu-id="3abf8-160">BizTalk Server Administration console design time (for creating physical ports).</span></span>  

  > [!NOTE]
  >  <span data-ttu-id="3abf8-161">BizTalk Server 管理コンソールは、32 ビットの Microsoft 管理コンソール (MMC) アプリケーションとして実行されます。</span><span class="sxs-lookup"><span data-stu-id="3abf8-161">BizTalk Server Administration console runs as a 32-bit Microsoft Management Console (MMC) application.</span></span>  

- <span data-ttu-id="3abf8-162">BizTalk の実行時間 (LOB アプリケーションからメッセージを送受信) するときにします。</span><span class="sxs-lookup"><span data-stu-id="3abf8-162">BizTalk run time (when sending and receiving messages from LOB applications).</span></span>  

  <span data-ttu-id="3abf8-163">同じコンピューターまたは別のコンピューター上のこれらすべてのタスクを実行するインストールしてあることができます。</span><span class="sxs-lookup"><span data-stu-id="3abf8-163">You can have an installation where you perform all these tasks on the same computer or different computers.</span></span> <span data-ttu-id="3abf8-164">両方[!INCLUDE[btsVStudioNoVersion](../../includes/btsvstudionoversion-md.md)]BizTalk MMC は 32 ビット プロセスとは、32 ビットをインストールする必要があります[!INCLUDE[adaptersqlshort](../../includes/adaptersqlshort-md.md)]デザイン時のタスクを実行するコンピューター。</span><span class="sxs-lookup"><span data-stu-id="3abf8-164">Because both [!INCLUDE[btsVStudioNoVersion](../../includes/btsvstudionoversion-md.md)] and BizTalk MMC are 32-bit processes, you must install the 32-bit [!INCLUDE[adaptersqlshort](../../includes/adaptersqlshort-md.md)] on the computer where you want to perform the design-time tasks.</span></span> <span data-ttu-id="3abf8-165">インストールするため、次のシナリオがサポートされている、 [!INCLUDE[adaptersqlshort](../../includes/adaptersqlshort-md.md)] 32 ビットおよび 64 ビット プラットフォーム上でします。</span><span class="sxs-lookup"><span data-stu-id="3abf8-165">The following scenarios are supported for installing the [!INCLUDE[adaptersqlshort](../../includes/adaptersqlshort-md.md)] on 32-bit and 64-bit platforms.</span></span>  

#### <a name="32-bit-install-scenarios"></a><span data-ttu-id="3abf8-166">32 ビット インストール シナリオ</span><span class="sxs-lookup"><span data-stu-id="3abf8-166">32-bit install scenarios</span></span>  
 <span data-ttu-id="3abf8-167">インストールするときに、次のシナリオがサポートされて、 [!INCLUDE[adaptersqlshort](../../includes/adaptersqlshort-md.md)] 32 ビット プラットフォームで。</span><span class="sxs-lookup"><span data-stu-id="3abf8-167">The following scenarios are supported when installing the [!INCLUDE[adaptersqlshort](../../includes/adaptersqlshort-md.md)] on a 32-bit platform.</span></span>  


|                                                                                                               <span data-ttu-id="3abf8-168">Visual Studio のデザイン時</span><span class="sxs-lookup"><span data-stu-id="3abf8-168">Visual Studio design time</span></span>                                                                                                                |                                                                                                                <span data-ttu-id="3abf8-169">デザイン時の BizTalk MMC</span><span class="sxs-lookup"><span data-stu-id="3abf8-169">BizTalk MMC design time</span></span>                                                                                                                 |                                                                                                                    <span data-ttu-id="3abf8-170">BizTalk ランタイム</span><span class="sxs-lookup"><span data-stu-id="3abf8-170">BizTalk run time</span></span>                                                                                                                    |                                                                                      <span data-ttu-id="3abf8-171">Visual Studio のデザイン時またはデザイン時の BizTalk MMC + BizTalk ランタイムします。</span><span class="sxs-lookup"><span data-stu-id="3abf8-171">Visual Studio design time and/or  BizTalk MMC design time + BizTalk run time</span></span>                                                                                      |
|--------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------|--------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------|--------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------|--------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------|
| <span data-ttu-id="3abf8-172">-32 ビットのインストール[!INCLUDE[afproductnameshort](../../includes/afproductnameshort-md.md)]します。</span><span class="sxs-lookup"><span data-stu-id="3abf8-172">- Install 32-bit [!INCLUDE[afproductnameshort](../../includes/afproductnameshort-md.md)].</span></span><br /><br /> <span data-ttu-id="3abf8-173">-32 ビットのインストール[!INCLUDE[adaptersqlshort](../../includes/adaptersqlshort-md.md)]します。</span><span class="sxs-lookup"><span data-stu-id="3abf8-173">- Install 32-bit [!INCLUDE[adaptersqlshort](../../includes/adaptersqlshort-md.md)].</span></span><br /><br /> <span data-ttu-id="3abf8-174">32 ビット クライアントとその他の必要な Dll をインストールします。</span><span class="sxs-lookup"><span data-stu-id="3abf8-174">- Install 32-bit client and other required DLLs.</span></span> | <span data-ttu-id="3abf8-175">-32 ビットのインストール[!INCLUDE[afproductnameshort](../../includes/afproductnameshort-md.md)]します。</span><span class="sxs-lookup"><span data-stu-id="3abf8-175">- Install 32-bit [!INCLUDE[afproductnameshort](../../includes/afproductnameshort-md.md)].</span></span><br /><br /> <span data-ttu-id="3abf8-176">-32 ビットのインストール[!INCLUDE[adaptersqlshort](../../includes/adaptersqlshort-md.md)]します。</span><span class="sxs-lookup"><span data-stu-id="3abf8-176">- Install 32-bit [!INCLUDE[adaptersqlshort](../../includes/adaptersqlshort-md.md)].</span></span><br /><br /> <span data-ttu-id="3abf8-177">32 ビット クライアントとその他の必要な Dll をインストールします。</span><span class="sxs-lookup"><span data-stu-id="3abf8-177">- Install 32-bit client and other required DLLs.</span></span> | <span data-ttu-id="3abf8-178">-32 ビットのインストール[!INCLUDE[afproductnameshort](../../includes/afproductnameshort-md.md)]します。</span><span class="sxs-lookup"><span data-stu-id="3abf8-178">- Install 32-bit [!INCLUDE[afproductnameshort](../../includes/afproductnameshort-md.md)].</span></span><br /><br /> <span data-ttu-id="3abf8-179">-32 ビットのインストール[!INCLUDE[adaptersqlshort](../../includes/adaptersqlshort-md.md)]します。</span><span class="sxs-lookup"><span data-stu-id="3abf8-179">- Install 32-bit [!INCLUDE[adaptersqlshort](../../includes/adaptersqlshort-md.md)].</span></span><br /><br /> <span data-ttu-id="3abf8-180">32 ビット クライアントとその他の必要な Dll をインストールします。</span><span class="sxs-lookup"><span data-stu-id="3abf8-180">- Install 32-bit client and other required DLLs.</span></span> | <span data-ttu-id="3abf8-181">-32 ビットのインストール[!INCLUDE[afproductnameshort](../../includes/afproductnameshort-md.md)]します。</span><span class="sxs-lookup"><span data-stu-id="3abf8-181">- Install 32-bit [!INCLUDE[afproductnameshort](../../includes/afproductnameshort-md.md)].</span></span><br /><br /> <span data-ttu-id="3abf8-182">-32 ビットのインストール[!INCLUDE[adaptersqlshort](../../includes/adaptersqlshort-md.md)]します。</span><span class="sxs-lookup"><span data-stu-id="3abf8-182">- Install 32-bit [!INCLUDE[adaptersqlshort](../../includes/adaptersqlshort-md.md)].</span></span><br /><br /> <span data-ttu-id="3abf8-183">32 ビット クライアントとその他の必要な Dll をインストールします。</span><span class="sxs-lookup"><span data-stu-id="3abf8-183">- Install 32-bit client and other required DLLs.</span></span> |

#### <a name="64-bit-install-scenarios"></a><span data-ttu-id="3abf8-184">64 ビット インストール シナリオ</span><span class="sxs-lookup"><span data-stu-id="3abf8-184">64-bit install scenarios</span></span>  
 <span data-ttu-id="3abf8-185">インストールするときに、次のシナリオがサポートされて、 [!INCLUDE[adaptersqlshort](../../includes/adaptersqlshort-md.md)] 64 ビット プラットフォームで。</span><span class="sxs-lookup"><span data-stu-id="3abf8-185">The following scenarios are supported when installing the [!INCLUDE[adaptersqlshort](../../includes/adaptersqlshort-md.md)] on a 64-bit platform.</span></span>  

> [!NOTE]
>  <span data-ttu-id="3abf8-186">いずれかを使用して、デザイン時のタスクを実行する任意のコンピューターで[!INCLUDE[btsVStudioNoVersion](../../includes/btsvstudionoversion-md.md)]BizTalk MMC で、32 ビットをインストールする必要がありますまたは[!INCLUDE[adaptersqlshort](../../includes/adaptersqlshort-md.md)]します。</span><span class="sxs-lookup"><span data-stu-id="3abf8-186">On any computer where you want to perform design-time tasks using either [!INCLUDE[btsVStudioNoVersion](../../includes/btsvstudionoversion-md.md)] or BizTalk MMC, you must install the 32-bit [!INCLUDE[adaptersqlshort](../../includes/adaptersqlshort-md.md)].</span></span>  

|                                                                                                               <span data-ttu-id="3abf8-187">Visual Studio のデザイン時</span><span class="sxs-lookup"><span data-stu-id="3abf8-187">Visual Studio design time</span></span>                                                                                                                |                                                                                                                <span data-ttu-id="3abf8-188">デザイン時の BizTalk MMC</span><span class="sxs-lookup"><span data-stu-id="3abf8-188">BizTalk MMC design time</span></span>                                                                                                                 |                                                                                                                                                                                                                                                                                                   <span data-ttu-id="3abf8-189">BizTalk ランタイム</span><span class="sxs-lookup"><span data-stu-id="3abf8-189">BizTalk run time</span></span>                                                                                                                                                                                                                                                                                                    |                                                                                                                                                                                                                                                                                                                                                    <span data-ttu-id="3abf8-190">Visual Studio のデザイン時またはデザイン時の BizTalk MMC + BizTalk ランタイムします。</span><span class="sxs-lookup"><span data-stu-id="3abf8-190">Visual Studio design time and/or BizTalk MMC design time + BizTalk run time</span></span>                                                                                                                                                                                                                                                                                                                                                     |
|--------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------|--------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------|-----------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------|------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------|
| <span data-ttu-id="3abf8-191">-64 ビットのインストール[!INCLUDE[afproductnameshort](../../includes/afproductnameshort-md.md)]します。</span><span class="sxs-lookup"><span data-stu-id="3abf8-191">- Install 64-bit [!INCLUDE[afproductnameshort](../../includes/afproductnameshort-md.md)].</span></span><br /><br /> <span data-ttu-id="3abf8-192">-32 ビットのインストール[!INCLUDE[adaptersqlshort](../../includes/adaptersqlshort-md.md)]します。</span><span class="sxs-lookup"><span data-stu-id="3abf8-192">- Install 32-bit [!INCLUDE[adaptersqlshort](../../includes/adaptersqlshort-md.md)].</span></span><br /><br /> <span data-ttu-id="3abf8-193">32 ビット クライアントとその他の必要な Dll をインストールします。</span><span class="sxs-lookup"><span data-stu-id="3abf8-193">- Install 32-bit client and other required DLLs.</span></span> | <span data-ttu-id="3abf8-194">-64 ビットのインストール[!INCLUDE[afproductnameshort](../../includes/afproductnameshort-md.md)]します。</span><span class="sxs-lookup"><span data-stu-id="3abf8-194">- Install 64-bit [!INCLUDE[afproductnameshort](../../includes/afproductnameshort-md.md)].</span></span><br /><br /> <span data-ttu-id="3abf8-195">-32 ビットのインストール[!INCLUDE[adaptersqlshort](../../includes/adaptersqlshort-md.md)]します。</span><span class="sxs-lookup"><span data-stu-id="3abf8-195">- Install 32-bit [!INCLUDE[adaptersqlshort](../../includes/adaptersqlshort-md.md)].</span></span><br /><br /> <span data-ttu-id="3abf8-196">32 ビット クライアントとその他の必要な Dll をインストールします。</span><span class="sxs-lookup"><span data-stu-id="3abf8-196">- Install 32-bit client and other required DLLs.</span></span> | <span data-ttu-id="3abf8-197">**32 ビット BizTalk プロセスの**:</span><span class="sxs-lookup"><span data-stu-id="3abf8-197">**For a 32-bit BizTalk process**:</span></span><br /><br /> <span data-ttu-id="3abf8-198">-64 ビットのインストール[!INCLUDE[afproductnameshort](../../includes/afproductnameshort-md.md)]します。</span><span class="sxs-lookup"><span data-stu-id="3abf8-198">- Install 64-bit [!INCLUDE[afproductnameshort](../../includes/afproductnameshort-md.md)].</span></span><br /><br /> <span data-ttu-id="3abf8-199">-32 ビットのインストール[!INCLUDE[adaptersqlshort](../../includes/adaptersqlshort-md.md)]します。</span><span class="sxs-lookup"><span data-stu-id="3abf8-199">- Install 32-bit [!INCLUDE[adaptersqlshort](../../includes/adaptersqlshort-md.md)].</span></span><br /><br /> <span data-ttu-id="3abf8-200">32 ビット クライアントとその他の必要な Dll をインストールします。</span><span class="sxs-lookup"><span data-stu-id="3abf8-200">- Install 32-bit client and other required DLLs.</span></span><br /><br /> <span data-ttu-id="3abf8-201">**64 ビットの BizTalk プロセスの**:</span><span class="sxs-lookup"><span data-stu-id="3abf8-201">**For a 64-bit BizTalk process**:</span></span><br /><br /> <span data-ttu-id="3abf8-202">-64 ビットのインストール[!INCLUDE[afproductnameshort](../../includes/afproductnameshort-md.md)]します。</span><span class="sxs-lookup"><span data-stu-id="3abf8-202">- Install 64-bit [!INCLUDE[afproductnameshort](../../includes/afproductnameshort-md.md)].</span></span><br /><br /> <span data-ttu-id="3abf8-203">-64 ビットのインストール[!INCLUDE[adaptersqlshort](../../includes/adaptersqlshort-md.md)]します。</span><span class="sxs-lookup"><span data-stu-id="3abf8-203">- Install 64-bit [!INCLUDE[adaptersqlshort](../../includes/adaptersqlshort-md.md)].</span></span><br /><br /> <span data-ttu-id="3abf8-204">-64 ビット クライアントとその他の必要な Dll をインストールします。</span><span class="sxs-lookup"><span data-stu-id="3abf8-204">- Install 64-bit client and other required DLLs.</span></span> | <span data-ttu-id="3abf8-205">**32 ビット BizTalk プロセスの**:</span><span class="sxs-lookup"><span data-stu-id="3abf8-205">**For a 32-bit BizTalk process**:</span></span><br /><br /> <span data-ttu-id="3abf8-206">-64 ビットのインストール[!INCLUDE[afproductnameshort](../../includes/afproductnameshort-md.md)]します。</span><span class="sxs-lookup"><span data-stu-id="3abf8-206">- Install 64-bit [!INCLUDE[afproductnameshort](../../includes/afproductnameshort-md.md)].</span></span><br /><br /> <span data-ttu-id="3abf8-207">-32 ビットのインストール[!INCLUDE[adaptersqlshort](../../includes/adaptersqlshort-md.md)]します。</span><span class="sxs-lookup"><span data-stu-id="3abf8-207">- Install 32-bit [!INCLUDE[adaptersqlshort](../../includes/adaptersqlshort-md.md)].</span></span><br /><br /> <span data-ttu-id="3abf8-208">32 ビット クライアントとその他の必要な Dll をインストールします。</span><span class="sxs-lookup"><span data-stu-id="3abf8-208">- Install 32-bit client and other required DLLs.</span></span><br /><br /> <span data-ttu-id="3abf8-209">**64 ビットの BizTalk プロセスの**:</span><span class="sxs-lookup"><span data-stu-id="3abf8-209">**For a 64-bit BizTalk process**:</span></span><br /><br /> <span data-ttu-id="3abf8-210">-64 ビットのインストール[!INCLUDE[afproductnameshort](../../includes/afproductnameshort-md.md)]します。</span><span class="sxs-lookup"><span data-stu-id="3abf8-210">- Install 64-bit [!INCLUDE[afproductnameshort](../../includes/afproductnameshort-md.md)].</span></span><br /><br /> <span data-ttu-id="3abf8-211">-64 ビットのインストール[!INCLUDE[adaptersqlshort](../../includes/adaptersqlshort-md.md)]します。</span><span class="sxs-lookup"><span data-stu-id="3abf8-211">- Install 64-bit [!INCLUDE[adaptersqlshort](../../includes/adaptersqlshort-md.md)].</span></span><br /><br /> <span data-ttu-id="3abf8-212">-64 ビット クライアントとその他の必要な Dll をインストールします。</span><span class="sxs-lookup"><span data-stu-id="3abf8-212">- Install 64-bit client and other required DLLs.</span></span><br /><br /> <span data-ttu-id="3abf8-213">-32 ビットのインストール[!INCLUDE[adaptersqlshort](../../includes/adaptersqlshort-md.md)]します。</span><span class="sxs-lookup"><span data-stu-id="3abf8-213">- Install 32-bit [!INCLUDE[adaptersqlshort](../../includes/adaptersqlshort-md.md)].</span></span><br /><br /> <span data-ttu-id="3abf8-214">32 ビット クライアントとその他の必要な Dll をインストールします。</span><span class="sxs-lookup"><span data-stu-id="3abf8-214">- Install 32-bit client and other required DLLs.</span></span> |

<a name="BKMK_Install_wizard"></a>   
### <a name="install-the-adapter-in-interactive-mode"></a><span data-ttu-id="3abf8-215">対話モードでアダプターをインストールします。</span><span class="sxs-lookup"><span data-stu-id="3abf8-215">Install the adapter in interactive mode</span></span>  
<span data-ttu-id="3abf8-216">インストールするには、次の手順を完了、[!INCLUDE[adaptersqlshort](../../includes/adaptersqlshort-md.md)]セットアップ ウィザードを使用します。</span><span class="sxs-lookup"><span data-stu-id="3abf8-216">Complete the following steps to install the [!INCLUDE[adaptersqlshort](../../includes/adaptersqlshort-md.md)] using the setup wizard.</span></span>  

1. <span data-ttu-id="3abf8-217">インストーラーを実行します。</span><span class="sxs-lookup"><span data-stu-id="3abf8-217">Run the installer.</span></span>  

   > [!NOTE]
   >  <span data-ttu-id="3abf8-218">インストールする場合、[!INCLUDE[adaptersqlshort](../../includes/adaptersqlshort-md.md)]仮想マシンで、セットアップ ウィザードは、セットアップを使用可能なディスク領域にチェックすることを知らせるダイアログ ボックスを超える続行されません可能性があります。</span><span class="sxs-lookup"><span data-stu-id="3abf8-218">If you are installing the [!INCLUDE[adaptersqlshort](../../includes/adaptersqlshort-md.md)] on a virtual machine, the setup wizard might not proceed beyond a dialog box informing that the setup is checking for available disk space.</span></span> <span data-ttu-id="3abf8-219">このような場合は、サイレント インストール オプションを使用することをお勧めします。</span><span class="sxs-lookup"><span data-stu-id="3abf8-219">In such cases, we recommend that you use the silent installation option.</span></span> <span data-ttu-id="3abf8-220">詳細については、次を参照してください。[サイレント モードで SQL アダプターをインストール](#BKMK_SilentInst)(」を参照)。</span><span class="sxs-lookup"><span data-stu-id="3abf8-220">For more information, see [Install the SQL adapter in silent mode](#BKMK_SilentInst) (in this topic).</span></span>

2. <span data-ttu-id="3abf8-221">クリックして、ようこそ画面の情報を読み取る**次**します。</span><span class="sxs-lookup"><span data-stu-id="3abf8-221">Read the information on the Welcome screen, and then click **Next**.</span></span>  

3. <span data-ttu-id="3abf8-222">読み取り、使用許諾契約書 (EULA) に同意し、クリックして**次**します。</span><span class="sxs-lookup"><span data-stu-id="3abf8-222">Read and accept the end-user license agreement (EULA), and then click **Next**.</span></span>  

4. <span data-ttu-id="3abf8-223">**先フォルダー**  ダイアログ ボックスで、インストールする場所を指定、 [!INCLUDE[adaptersqlshort](../../includes/adaptersqlshort-md.md)]、 をクリックして**次**、順にクリックします**インストール**。</span><span class="sxs-lookup"><span data-stu-id="3abf8-223">In the **Destination Folder** dialog box, specify the location where you want to install the [!INCLUDE[adaptersqlshort](../../includes/adaptersqlshort-md.md)], click **Next**, and then click **Install**.</span></span>  

5. <span data-ttu-id="3abf8-224">**カスタマー エクスペリエンス向上プログラム** ダイアログ ボックスで、カスタマー エクスペリエンス向上プログラム (CEIP) に登録するかどうかを指定します。</span><span class="sxs-lookup"><span data-stu-id="3abf8-224">In the **Customer Experience Improvement Program** dialog box, specify whether you would like to enroll for the Customer Experience Improvement Program (CEIP).</span></span> <span data-ttu-id="3abf8-225">CEIP の一部として[!INCLUDE[adaptersqlshort](../../includes/adaptersqlshort-md.md)]、次のデータは、Microsoft と共有されます。</span><span class="sxs-lookup"><span data-stu-id="3abf8-225">As part of CEIP for [!INCLUDE[adaptersqlshort](../../includes/adaptersqlshort-md.md)], you will share the following data with Microsoft:</span></span>  

   - <span data-ttu-id="3abf8-226">インストール先コンピューターのハードウェアに関連するデータ、[!INCLUDE[adaptersqlshort](../../includes/adaptersqlshort-md.md)]します。</span><span class="sxs-lookup"><span data-stu-id="3abf8-226">Data related to the computer hardware on which you are installing the [!INCLUDE[adaptersqlshort](../../includes/adaptersqlshort-md.md)].</span></span>  

   - <span data-ttu-id="3abf8-227">関連データを使用して接続を使用している SQL Server のバージョンを[!INCLUDE[adaptersqlshort](../../includes/adaptersqlshort-md.md)]します。</span><span class="sxs-lookup"><span data-stu-id="3abf8-227">Data related to the SQL Server versions you are using to connect using the [!INCLUDE[adaptersqlshort](../../includes/adaptersqlshort-md.md)].</span></span>  

     <span data-ttu-id="3abf8-228">選択を指定し、クリックして**OK**します。</span><span class="sxs-lookup"><span data-stu-id="3abf8-228">Specify your choice and click **OK**.</span></span>  

   > [!NOTE]
   >  <span data-ttu-id="3abf8-229">常に、基本設定を変更することができます、コントロール パネルから修復モードでセットアップを実行して、CEIP の登録に関連します。</span><span class="sxs-lookup"><span data-stu-id="3abf8-229">You can always change your preference regarding enrolling for CEIP by running the Setup in Repair mode from the Control Panel.</span></span>  

6. <span data-ttu-id="3abf8-230">**[完了]** をクリックします。</span><span class="sxs-lookup"><span data-stu-id="3abf8-230">Click **Finish**.</span></span>  

<a name="BKMK_SilentInst"></a>   
### <a name="install-the-sql-adapter-in-silent-mode"></a><span data-ttu-id="3abf8-231">サイレント モードで SQL アダプターをインストールします。</span><span class="sxs-lookup"><span data-stu-id="3abf8-231">Install the SQL adapter in silent mode</span></span> 
<span data-ttu-id="3abf8-232">サイレント インストールを行うには、次の手順を完了[!INCLUDE[adaptersqlshort](../../includes/adaptersqlshort-md.md)]を使用して、`msiexec`コマンド。</span><span class="sxs-lookup"><span data-stu-id="3abf8-232">Complete the following steps to do a silent installation of [!INCLUDE[adaptersqlshort](../../includes/adaptersqlshort-md.md)] using the `msiexec` command.</span></span>  

1. <span data-ttu-id="3abf8-233">コマンド プロンプトを開き、インストーラーがあるフォルダーに移動します。</span><span class="sxs-lookup"><span data-stu-id="3abf8-233">Open a command prompt, and navigate to the folder where you have the installer.</span></span>  

2. <span data-ttu-id="3abf8-234">インストールするには、次のコマンドを実行、 [!INCLUDE[adaptersqlshort](../../includes/adaptersqlshort-md.md)]:</span><span class="sxs-lookup"><span data-stu-id="3abf8-234">Run the following command to install the [!INCLUDE[adaptersqlshort](../../includes/adaptersqlshort-md.md)]:</span></span>  

   > [!NOTE]
   >  <span data-ttu-id="3abf8-235">次のコマンドでの x64 ベースのプラットフォームでサイレント インストールを実行するには、SqlAdapterSetup64.msi で SqlAdapterSetup.msi を置き換えます。</span><span class="sxs-lookup"><span data-stu-id="3abf8-235">To perform silent installation on an x64-based platform, in the following commands, replace SqlAdapterSetup.msi with SqlAdapterSetup64.msi.</span></span>  

   ```  
   msiexec /i SqlAdapterSetup.msi /qn  
   ```  

    <span data-ttu-id="3abf8-236">サイレント インストールの一環として、CEIP に登録することもできます。</span><span class="sxs-lookup"><span data-stu-id="3abf8-236">You can also choose to enroll for CEIP as part of the silent installation.</span></span> <span data-ttu-id="3abf8-237">CEIP の一部として[!INCLUDE[adaptersqlshort](../../includes/adaptersqlshort-md.md)]、次のデータは、Microsoft と共有されます。</span><span class="sxs-lookup"><span data-stu-id="3abf8-237">As part of CEIP for [!INCLUDE[adaptersqlshort](../../includes/adaptersqlshort-md.md)], you will share the following data with Microsoft:</span></span>  

   - <span data-ttu-id="3abf8-238">インストール先コンピューターのハードウェア、[!INCLUDE[adaptersqlshort](../../includes/adaptersqlshort-md.md)]します。</span><span class="sxs-lookup"><span data-stu-id="3abf8-238">The computer hardware on which you are installing the [!INCLUDE[adaptersqlshort](../../includes/adaptersqlshort-md.md)].</span></span>  

   - <span data-ttu-id="3abf8-239">使用して接続を使用している SQL Server のバージョン、[!INCLUDE[adaptersqlshort](../../includes/adaptersqlshort-md.md)]します。</span><span class="sxs-lookup"><span data-stu-id="3abf8-239">The SQL Server versions you are using to connect using the [!INCLUDE[adaptersqlshort](../../includes/adaptersqlshort-md.md)].</span></span>  

     <span data-ttu-id="3abf8-240">CEIP を登録するには、次のコマンドを実行します。</span><span class="sxs-lookup"><span data-stu-id="3abf8-240">To enroll for CEIP, run the following command:</span></span>  

   ```  
   msiexec /i SqlAdapterSetup.msi /qn CEIP_OPTIN=true  
   ```  

    <span data-ttu-id="3abf8-241">既定では、オプションは false です。</span><span class="sxs-lookup"><span data-stu-id="3abf8-241">By default, the option is false.</span></span>  

    <span data-ttu-id="3abf8-242">詳細については、`msiexec`のコマンドを入力`msiexec`キーを押して、コマンド ラインで`ENTER`を参照してくださいまたは[ https://support.microsoft.com/kb/230781](https://support.microsoft.com/kb/230781)します。</span><span class="sxs-lookup"><span data-stu-id="3abf8-242">For more information about the `msiexec` command, type `msiexec` on the command line and press `ENTER`, or see [https://support.microsoft.com/kb/230781](https://support.microsoft.com/kb/230781).</span></span>  

<a name="BKMK_PostInst"></a>   
## <a name="post-installation-tasks"></a><span data-ttu-id="3abf8-243">インストール後のタスク</span><span class="sxs-lookup"><span data-stu-id="3abf8-243">Post-installation tasks</span></span>  

<a name="BKMK_Register_Bindings"></a>   
#### <a name="register-the-bindings"></a><span data-ttu-id="3abf8-244">バインドを登録します。</span><span class="sxs-lookup"><span data-stu-id="3abf8-244">Register the bindings</span></span>  
<span data-ttu-id="3abf8-245">次の手順を完了*のみ*machine.config ファイルでアダプターのバインドを登録するセットアップ ウィザードが失敗した場合。</span><span class="sxs-lookup"><span data-stu-id="3abf8-245">Complete these steps *only* if the setup wizard fails to register the adapter bindings in the machine.config file.</span></span>  

1. <span data-ttu-id="3abf8-246">コンピューターの machine.config ファイルに移動します。</span><span class="sxs-lookup"><span data-stu-id="3abf8-246">Navigate to the machine.config file on the computer.</span></span> <span data-ttu-id="3abf8-247">たとえば、32 ビット プラットフォームで、machine.config はで使用可能な\<システム ドライブ\>: \WINDOWS\Microsoft.NET\Framework\\< バージョン\>\CONFIG します。</span><span class="sxs-lookup"><span data-stu-id="3abf8-247">For example, on a 32-bit platform, the machine.config is available under \<system drive\>:\WINDOWS\Microsoft.NET\Framework\\<version\>\CONFIG.</span></span>  

2. <span data-ttu-id="3abf8-248">テキスト エディターを使用してファイルを開きます。</span><span class="sxs-lookup"><span data-stu-id="3abf8-248">Open the file using a text editor.</span></span>  

3. <span data-ttu-id="3abf8-249">アダプターのバインドを登録するには。</span><span class="sxs-lookup"><span data-stu-id="3abf8-249">To register the adapter bindings:</span></span>  

   1. <span data-ttu-id="3abf8-250">要素の"system.serviceModel"を検索し、その下にある、次を追加します。</span><span class="sxs-lookup"><span data-stu-id="3abf8-250">Search for the element "system.serviceModel" and add the following under it:</span></span>  

      ```  
      <client>  
        <endpoint binding="sqlBinding" contract="IMetadataExchange" name="mssql" />  
      </client>  
      ```  

   2. <span data-ttu-id="3abf8-251">"BindingElementExtensions"system.serviceModel\extensions 下の要素を検索します。</span><span class="sxs-lookup"><span data-stu-id="3abf8-251">Search for the element "bindingElementExtensions" under system.serviceModel\extensions.</span></span>  

   3. <span data-ttu-id="3abf8-252">"BindingElementExtensions"ノードの下の次のセクションを追加します。</span><span class="sxs-lookup"><span data-stu-id="3abf8-252">Add the following section under the "bindingElementExtensions" node.</span></span>  

       <span data-ttu-id="3abf8-253">[!INCLUDE[adaptersqlshort](../../includes/adaptersqlshort-md.md)]を追加します。</span><span class="sxs-lookup"><span data-stu-id="3abf8-253">For the [!INCLUDE[adaptersqlshort](../../includes/adaptersqlshort-md.md)], add:</span></span>  

      ```  
      <add name="sqlAdapter" type="Microsoft.Adapters.Sql.SqlAdapterBindingElementExtensionElement,Microsoft.Adapters.Sql, Version=<version>, Culture=neutral, PublicKeyToken=<public key>" />  
      ```  

   4. <span data-ttu-id="3abf8-254">"BindingExtensions"system.serviceModel\extensions 下の要素を検索します。</span><span class="sxs-lookup"><span data-stu-id="3abf8-254">Search for the element "bindingExtensions" under system.serviceModel\extensions.</span></span>  

   5. <span data-ttu-id="3abf8-255">"BindingExtensions"ノードの下の次のセクションを追加します。</span><span class="sxs-lookup"><span data-stu-id="3abf8-255">Add the following section under the "bindingExtensions" node.</span></span>  

       <span data-ttu-id="3abf8-256">[!INCLUDE[adaptersqlshort](../../includes/adaptersqlshort-md.md)]を追加します。</span><span class="sxs-lookup"><span data-stu-id="3abf8-256">For [!INCLUDE[adaptersqlshort](../../includes/adaptersqlshort-md.md)], add:</span></span>  

      ```  
      <add name="sqlBinding" type="Microsoft.Adapters.Sql.SqlAdapterBindingCollectionElement,Microsoft.Adapters.Sql, Version=<version>, Culture=neutral, PublicKeyToken=<public key>" />  
      ```  

   > [!NOTE]
   >  <span data-ttu-id="3abf8-257">公開キーを確認する方法については、次を参照してください。[公開キーとバージョンを決定する](#BKMK_PubKey)します。</span><span class="sxs-lookup"><span data-stu-id="3abf8-257">For information about how to determine the public key, see [Determining the Public Key and Version](#BKMK_PubKey).</span></span>  

4. <span data-ttu-id="3abf8-258">machine.config ファイルを保存して閉じます。</span><span class="sxs-lookup"><span data-stu-id="3abf8-258">Save and close the machine.config file.</span></span>  

<a name="BKMK_PubKey"></a>   
#### <a name="determining-the-public-key-and-version"></a><span data-ttu-id="3abf8-259">公開キーとバージョンを決定します。</span><span class="sxs-lookup"><span data-stu-id="3abf8-259">Determining the Public Key and Version</span></span>  
<span data-ttu-id="3abf8-260">公開キーとバージョンを確認するのには、次の手順を完了、[!INCLUDE[adaptersqlshort](../../includes/adaptersqlshort-md.md)]します。</span><span class="sxs-lookup"><span data-stu-id="3abf8-260">Complete the following steps to determine the public key and version for the [!INCLUDE[adaptersqlshort](../../includes/adaptersqlshort-md.md)].</span></span>  

1. <span data-ttu-id="3abf8-261">Windows ディレクトリの通常 C:\WINDOWS\assembly に移動します。</span><span class="sxs-lookup"><span data-stu-id="3abf8-261">Navigate to the Windows directory, typically C:\WINDOWS\assembly.</span></span>  

2. <span data-ttu-id="3abf8-262">DLL を公開キーを必要し、し、選択を右クリックして**プロパティ**します。</span><span class="sxs-lookup"><span data-stu-id="3abf8-262">Right-click the DLL for which you want the public key, and then select **Properties**.</span></span> <span data-ttu-id="3abf8-263">次の表に、用の Dll の名前、[!INCLUDE[adaptersqlshort](../../includes/adaptersqlshort-md.md)]します。</span><span class="sxs-lookup"><span data-stu-id="3abf8-263">The following table lists the name of the DLLs for the [!INCLUDE[adaptersqlshort](../../includes/adaptersqlshort-md.md)].</span></span>  


   |                              <span data-ttu-id="3abf8-264">[アダプター]</span><span class="sxs-lookup"><span data-stu-id="3abf8-264">Adapter</span></span>                              |      <span data-ttu-id="3abf8-265">DLL の名前</span><span class="sxs-lookup"><span data-stu-id="3abf8-265">Name of the DLL</span></span>       |
   |-------------------------------------------------------------------|----------------------------|
   | [!INCLUDE[adaptersqlshort](../../includes/adaptersqlshort-md.md)] | <span data-ttu-id="3abf8-266">Microsoft.Adapters.Sql.dll</span><span class="sxs-lookup"><span data-stu-id="3abf8-266">Microsoft.Adapters.Sql.dll</span></span> |


3. <span data-ttu-id="3abf8-267">**全般**タブの値を比較、**公開キー トークンの**ラベルは、DLL の公開キーを指定します。</span><span class="sxs-lookup"><span data-stu-id="3abf8-267">On the **General** tab, the value against the **Public Key Token** label specifies the public key for the DLL.</span></span> <span data-ttu-id="3abf8-268">に対して同様に、値、**バージョン**ラベルは、DLL のバージョン番号を指定します。</span><span class="sxs-lookup"><span data-stu-id="3abf8-268">Similarly, the value against the **Version** label specifies the version number for the DLL.</span></span>  

4. <span data-ttu-id="3abf8-269">クリックして、公開キーをコピー**キャンセル**します。</span><span class="sxs-lookup"><span data-stu-id="3abf8-269">Copy the public key, and then click **Cancel**.</span></span>  

<a name="BKMK_Modify_Adap"></a>   
## <a name="update-or-change-the-sql-adapter-installation"></a><span data-ttu-id="3abf8-270">更新または変更する SQL アダプターのインストール</span><span class="sxs-lookup"><span data-stu-id="3abf8-270">Update or change the SQL adapter installation</span></span>  
 <span data-ttu-id="3abf8-271">変更するのには、次の手順を実行、[!INCLUDE[adaptersqlshort](../../includes/adaptersqlshort-md.md)]インストールします。</span><span class="sxs-lookup"><span data-stu-id="3abf8-271">Perform the following steps to modify the [!INCLUDE[adaptersqlshort](../../includes/adaptersqlshort-md.md)] installation.</span></span> <span data-ttu-id="3abf8-272">あるかどうかを確認、[!INCLUDE[adaptersqlshort](../../includes/adaptersqlshort-md.md)]変更には、セットアップ ウィザードを実行する前にインストールされている、[!INCLUDE[adaptersqlshort](../../includes/adaptersqlshort-md.md)]インストールします。</span><span class="sxs-lookup"><span data-stu-id="3abf8-272">Make sure you have the [!INCLUDE[adaptersqlshort](../../includes/adaptersqlshort-md.md)] installed before you run the setup wizard to modify the [!INCLUDE[adaptersqlshort](../../includes/adaptersqlshort-md.md)] installation.</span></span>  

 <span data-ttu-id="3abf8-273">変更することができます、[!INCLUDE[adaptersqlshort](../../includes/adaptersqlshort-md.md)]次の 2 つの方法でインストールします。</span><span class="sxs-lookup"><span data-stu-id="3abf8-273">You can modify the [!INCLUDE[adaptersqlshort](../../includes/adaptersqlshort-md.md)] installation in the following two ways:</span></span>  

-   <span data-ttu-id="3abf8-274">**対話モードで**セットアップ ウィザードを実行しています。</span><span class="sxs-lookup"><span data-stu-id="3abf8-274">**In interactive mode** by running the setup wizard.</span></span>  

-   <span data-ttu-id="3abf8-275">**サイレント モードで**コマンドラインを使用しています。</span><span class="sxs-lookup"><span data-stu-id="3abf8-275">**In silent mode** by using the command line.</span></span>  

#### <a name="update-the-sql-adapter-installation-in-interactive-mode"></a><span data-ttu-id="3abf8-276">対話モードで SQL アダプターのインストールを更新します。</span><span class="sxs-lookup"><span data-stu-id="3abf8-276">Update the SQL Adapter installation in interactive mode</span></span>  

1.  <span data-ttu-id="3abf8-277">クリックして**開始**、順にクリックします**コントロール パネルの **します。</span><span class="sxs-lookup"><span data-stu-id="3abf8-277">Click **Start**, and then click **Control Panel**.</span></span>  

2.  <span data-ttu-id="3abf8-278">コントロール パネルで、ダブルクリック**プログラムと機能**します。</span><span class="sxs-lookup"><span data-stu-id="3abf8-278">In Control Panel, double-click **Programs and Features**.</span></span>  

3.  <span data-ttu-id="3abf8-279">**プログラムと機能**ウィンドウで、 **Microsoft BizTalk Adapter for SQL Server**、 をクリックし、**変更**します。</span><span class="sxs-lookup"><span data-stu-id="3abf8-279">In the **Programs and Features** window, select **Microsoft BizTalk Adapter for SQL Server**, and then click **Change**.</span></span>  

4.  <span data-ttu-id="3abf8-280">クリックして、ようこそ画面の情報を読み取る**次**します。</span><span class="sxs-lookup"><span data-stu-id="3abf8-280">Read the information on the Welcome screen, and then click **Next**.</span></span>  

5.  <span data-ttu-id="3abf8-281">**変更、修復、または削除インストール**ダイアログ ボックスで、をクリックして**修復**。</span><span class="sxs-lookup"><span data-stu-id="3abf8-281">In the **Change, repair, or remove installation** dialog box, click **Repair**.</span></span>  

6.  <span data-ttu-id="3abf8-282">**For SQL Server の Microsoft BizTalk Adapter の修復の準備完了**ダイアログ ボックスで、をクリックして**修復**します。</span><span class="sxs-lookup"><span data-stu-id="3abf8-282">In the **Ready to repair Microsoft BizTalk Adapter for SQL Server** dialog box, click **Repair**.</span></span>  

7.  <span data-ttu-id="3abf8-283">必要に応じて、設定を変更します。 クリックして、CEIP のオプトインに関する **[ok]** します。</span><span class="sxs-lookup"><span data-stu-id="3abf8-283">If required, change your preferences regarding opting for CEIP, and then click **OK**.</span></span>  

8.  <span data-ttu-id="3abf8-284">**[完了]** をクリックします。</span><span class="sxs-lookup"><span data-stu-id="3abf8-284">Click **Finish**.</span></span>  

#### <a name="update-the-sql-adapter-installation-in-silent-mode"></a><span data-ttu-id="3abf8-285">更新プログラムをサイレント モードで SQL アダプターのインストール</span><span class="sxs-lookup"><span data-stu-id="3abf8-285">Update the SQL Adapter installation in silent mode</span></span>  

1. <span data-ttu-id="3abf8-286">コマンド プロンプトを開きのルート ディレクトリに移動し、[!INCLUDE[adaptersqlshort](../../includes/adaptersqlshort-md.md)]インストーラー。</span><span class="sxs-lookup"><span data-stu-id="3abf8-286">Open a command prompt, and navigate to the root directory of the [!INCLUDE[adaptersqlshort](../../includes/adaptersqlshort-md.md)] installer.</span></span>  

2. <span data-ttu-id="3abf8-287">次のコマンドを実行します。</span><span class="sxs-lookup"><span data-stu-id="3abf8-287">Run the following command:</span></span>  

   > [!NOTE]
   >  <span data-ttu-id="3abf8-288">変更する、[!INCLUDE[adaptersqlshort](../../includes/adaptersqlshort-md.md)]次のコマンドでの x64 ベースのプラットフォームでサイレント モードでインストールが SqlAdapterSetup64.msi で SqlAdapterSetup.msi を置き換えます。</span><span class="sxs-lookup"><span data-stu-id="3abf8-288">To modify the [!INCLUDE[adaptersqlshort](../../includes/adaptersqlshort-md.md)] installation in silent mode on an x64-based platform, in the following commands, replace SqlAdapterSetup.msi with SqlAdapterSetup64.msi.</span></span>  

   ```  
   msiexec /i SqlAdapterSetup.msi /qn /f  
   ```  

   > [!IMPORTANT]
   >  <span data-ttu-id="3abf8-289">変更中に、[!INCLUDE[adaptersqlshort](../../includes/adaptersqlshort-md.md)]サイレント モードでインストール、または ceip のオプトインの設定を変更することはできません。</span><span class="sxs-lookup"><span data-stu-id="3abf8-289">While modifying the [!INCLUDE[adaptersqlshort](../../includes/adaptersqlshort-md.md)] installation in the silent mode, you cannot change your preferences for opting in or out of CEIP.</span></span> <span data-ttu-id="3abf8-290">環境設定は、同じまま、インストール時に指定した true または false に、CEIP_OPTIN を明示的に設定した場合でもです。</span><span class="sxs-lookup"><span data-stu-id="3abf8-290">The preferences will remain the same as you specified during the installation, even if you explicitly set the CEIP_OPTIN to true or false.</span></span>  

    <span data-ttu-id="3abf8-291">詳細については、`msiexec`コマンドの種類`msiexec`キーを押して、コマンド ラインで`ENTER`を参照してくださいまたは[ https://support.microsoft.com/kb/230781](https://support.microsoft.com/kb/230781)します。</span><span class="sxs-lookup"><span data-stu-id="3abf8-291">For more information about the `msiexec` command type `msiexec` on the command line and press `ENTER`, or see [https://support.microsoft.com/kb/230781](https://support.microsoft.com/kb/230781).</span></span>  

<a name="BKMK_Remove_Adap"></a>   
## <a name="uninstall-or-remove-the-sql-adapter"></a><span data-ttu-id="3abf8-292">アンインストールするか、SQL アダプターを削除します。</span><span class="sxs-lookup"><span data-stu-id="3abf8-292">Uninstall or remove the SQL Adapter</span></span>  
 <span data-ttu-id="3abf8-293">削除するには、次の手順を実行、[!INCLUDE[adaptersqlshort](../../includes/adaptersqlshort-md.md)]コンピューターから。</span><span class="sxs-lookup"><span data-stu-id="3abf8-293">Perform the following steps to remove the [!INCLUDE[adaptersqlshort](../../includes/adaptersqlshort-md.md)] from your computer.</span></span> <span data-ttu-id="3abf8-294">必ず、[!INCLUDE[afproductnameshort](../../includes/afproductnameshort-md.md)]を削除するセットアップ ウィザードを実行する前にインストールされている、 [!INCLUDE[adaptersqlshort](../../includes/adaptersqlshort-md.md)]。</span><span class="sxs-lookup"><span data-stu-id="3abf8-294">Make sure you have the [!INCLUDE[afproductnameshort](../../includes/afproductnameshort-md.md)] installed before you run the setup wizard to remove the [!INCLUDE[adaptersqlshort](../../includes/adaptersqlshort-md.md)].</span></span>  

 <span data-ttu-id="3abf8-295">削除することができます、[!INCLUDE[adaptersqlshort](../../includes/adaptersqlshort-md.md)]次の 2 つの方法で。</span><span class="sxs-lookup"><span data-stu-id="3abf8-295">You can remove the [!INCLUDE[adaptersqlshort](../../includes/adaptersqlshort-md.md)] in the following two ways:</span></span>  

-   <span data-ttu-id="3abf8-296">**対話モードで**セットアップ ウィザードを実行しています。</span><span class="sxs-lookup"><span data-stu-id="3abf8-296">**In interactive mode** by running the setup wizard.</span></span>  

-   <span data-ttu-id="3abf8-297">**サイレント モードで**コマンドラインを使用しています。</span><span class="sxs-lookup"><span data-stu-id="3abf8-297">**In silent mode** by using the command line.</span></span>  

#### <a name="uninstall-the-sql-adapter-in-interactive-mode"></a><span data-ttu-id="3abf8-298">対話モードで SQL アダプターをアンインストールします。</span><span class="sxs-lookup"><span data-stu-id="3abf8-298">Uninstall the SQL Adapter in interactive mode</span></span>  

1.  <span data-ttu-id="3abf8-299">クリックして**開始**、順にクリックします**コントロール パネルの **します。</span><span class="sxs-lookup"><span data-stu-id="3abf8-299">Click **Start**, and then click **Control Panel**.</span></span>  

2.  <span data-ttu-id="3abf8-300">コントロール パネルで、ダブルクリック**プログラムと機能**します。</span><span class="sxs-lookup"><span data-stu-id="3abf8-300">In Control Panel, double-click  **Programs and Features**.</span></span>  

3.  <span data-ttu-id="3abf8-301">**プログラム追加と削除**ウィンドウで、 **Microsoft BizTalk Adapter for SQL Server**、 をクリックし、**削除**します。</span><span class="sxs-lookup"><span data-stu-id="3abf8-301">In the **Add or Remove Programs** window, select **Microsoft BizTalk Adapter for SQL Server**, and then click **Remove**.</span></span>  

4.  <span data-ttu-id="3abf8-302">ダイアログ ボックスで、次のようにクリックします。**はい**します。</span><span class="sxs-lookup"><span data-stu-id="3abf8-302">In the dialog box, click **Yes**.</span></span>  

#### <a name="uninstall-the-sql-adapter-in-silent-mode"></a><span data-ttu-id="3abf8-303">サイレント モードで SQL アダプターをアンインストールします。</span><span class="sxs-lookup"><span data-stu-id="3abf8-303">Uninstall the SQL Adapter in silent mode</span></span>  

1. <span data-ttu-id="3abf8-304">コマンド プロンプトを開きのルート ディレクトリに移動し、[!INCLUDE[adaptersqlshort](../../includes/adaptersqlshort-md.md)]インストーラー。</span><span class="sxs-lookup"><span data-stu-id="3abf8-304">Open a command prompt, and navigate to the root directory of the [!INCLUDE[adaptersqlshort](../../includes/adaptersqlshort-md.md)] installer.</span></span>  

2. <span data-ttu-id="3abf8-305">次のコマンドを実行します。</span><span class="sxs-lookup"><span data-stu-id="3abf8-305">Run the following command:</span></span>  

   > [!NOTE]
   >  <span data-ttu-id="3abf8-306">削除する、[!INCLUDE[adaptersqlshort](../../includes/adaptersqlshort-md.md)]サイレント モードで、次のコマンドでの x64 ベースのプラットフォームでは、SqlAdapterSetup64.msi で SqlAdapterSetup.msi を置き換えます。</span><span class="sxs-lookup"><span data-stu-id="3abf8-306">To remove the [!INCLUDE[adaptersqlshort](../../includes/adaptersqlshort-md.md)] in silent mode on an x64-based platform, in the following commands, replace SqlAdapterSetup.msi with SqlAdapterSetup64.msi.</span></span>  

   ```  
   msiexec /x SqlAdapterSetup.msi /qn  
   ```  

    <span data-ttu-id="3abf8-307">このコマンドを削除、[!INCLUDE[adaptersqlshort](../../includes/adaptersqlshort-md.md)]コンピューターから。</span><span class="sxs-lookup"><span data-stu-id="3abf8-307">This command removes the [!INCLUDE[adaptersqlshort](../../includes/adaptersqlshort-md.md)] from the computer.</span></span>  

    <span data-ttu-id="3abf8-308">詳細については、`msiexec`のコマンドを入力`msiexec`キーを押して、コマンド ラインで`ENTER`を参照してくださいまたは[ https://support.microsoft.com/kb/230781](https://support.microsoft.com/kb/230781)します。</span><span class="sxs-lookup"><span data-stu-id="3abf8-308">For more information about the `msiexec` command, type `msiexec` on the command line and press `ENTER`, or see [https://support.microsoft.com/kb/230781](https://support.microsoft.com/kb/230781).</span></span>  

<a name="BKMK_PostRemove"></a>   
### <a name="post-uninstall-task"></a><span data-ttu-id="3abf8-309">アンインストール後のタスク</span><span class="sxs-lookup"><span data-stu-id="3abf8-309">Post-uninstall task</span></span>  
 <span data-ttu-id="3abf8-310">場合、[!INCLUDE[adaptersqlshort](../../includes/adaptersqlshort-md.md)]の削除中に、アダプターのバインドを削除に失敗する、 [!INCLUDE[adaptersqlshort](../../includes/adaptersqlshort-md.md)]、手動で削除する必要があります。</span><span class="sxs-lookup"><span data-stu-id="3abf8-310">If the [!INCLUDE[adaptersqlshort](../../includes/adaptersqlshort-md.md)] setup fails to remove the adapter bindings while removing the [!INCLUDE[adaptersqlshort](../../includes/adaptersqlshort-md.md)], you must remove them manually.</span></span> <span data-ttu-id="3abf8-311">次のセクションのバインドを手動で削除する方法を説明する、[!INCLUDE[adaptersqlshort](../../includes/adaptersqlshort-md.md)]します。</span><span class="sxs-lookup"><span data-stu-id="3abf8-311">The following section describes how to manually remove the bindings for the [!INCLUDE[adaptersqlshort](../../includes/adaptersqlshort-md.md)].</span></span>  

<span data-ttu-id="3abf8-312">次の手順を完了*のみ*セットアップ ウィザードが、machine.config ファイルからアダプターのバインドを削除できない場合。</span><span class="sxs-lookup"><span data-stu-id="3abf8-312">Complete these steps *only* if the setup wizard fails to remove the adapter bindings from the machine.config file.</span></span>  

1. <span data-ttu-id="3abf8-313">コンピューターの machine.config ファイルに移動します。</span><span class="sxs-lookup"><span data-stu-id="3abf8-313">Navigate to the machine.config file on the computer.</span></span> <span data-ttu-id="3abf8-314">たとえば、32 ビット プラットフォームで、machine.config はで使用可能な\<システム ドライブ\>: \WINDOWS\Microsoft.NET\Framework\\< バージョン\>\CONFIG します。</span><span class="sxs-lookup"><span data-stu-id="3abf8-314">For example, on a 32-bit platform, the machine.config is available under \<system drive\>:\WINDOWS\Microsoft.NET\Framework\\<version\>\CONFIG.</span></span>  

   - <span data-ttu-id="3abf8-315">Microsoft .NET framework 3.5 SP1 では、 \<*バージョン*\>は .NET Framework のバージョン v2.0.50727 します。</span><span class="sxs-lookup"><span data-stu-id="3abf8-315">For Microsoft .NET Framework 3.5 SP1, \<*version*\> is the version v2.0.50727 of the .NET Framework.</span></span>  

   - <span data-ttu-id="3abf8-316">Microsoft の[!INCLUDE[netfx40_short](../../includes/netfx40-short-md.md)]、 \<*バージョン*\>は .NET Framework のバージョン v4.0.30319 します。</span><span class="sxs-lookup"><span data-stu-id="3abf8-316">For Microsoft [!INCLUDE[netfx40_short](../../includes/netfx40-short-md.md)], \<*version*\> is the version v4.0.30319 of the .NET Framework.</span></span>  

2. <span data-ttu-id="3abf8-317">テキスト エディターを使用してファイルを開きます。</span><span class="sxs-lookup"><span data-stu-id="3abf8-317">Open the file using a text editor.</span></span>  

3. <span data-ttu-id="3abf8-318">アダプターのバインディング登録を削除するには。</span><span class="sxs-lookup"><span data-stu-id="3abf8-318">To remove the adapter binding registration:</span></span>  

   1. <span data-ttu-id="3abf8-319">要素の"system.serviceModel"を検索し、次の要素の下からを削除します。</span><span class="sxs-lookup"><span data-stu-id="3abf8-319">Search for the element "system.serviceModel" and remove the following from under the element:</span></span>  

      ```  
      <client>  
        <endpoint binding="sqlBinding" contract="IMetadataExchange" name="mssql" />  
      </client>  

      ```  

   2. <span data-ttu-id="3abf8-320">"BindingElementExtensions"system.serviceModel\extensions 下の要素を検索します。</span><span class="sxs-lookup"><span data-stu-id="3abf8-320">Search for the element "bindingElementExtensions" under system.serviceModel\extensions.</span></span>  

   3. <span data-ttu-id="3abf8-321">"BindingElementExtensions"ノードの下に、次のセクションを削除します。</span><span class="sxs-lookup"><span data-stu-id="3abf8-321">Remove the following section under the "bindingElementExtensions" node.</span></span>  

       <span data-ttu-id="3abf8-322">[!INCLUDE[adaptersqlshort](../../includes/adaptersqlshort-md.md)]、削除します。</span><span class="sxs-lookup"><span data-stu-id="3abf8-322">For [!INCLUDE[adaptersqlshort](../../includes/adaptersqlshort-md.md)], remove:</span></span>  

      ```  
      <add name="sqlAdapter" type="Microsoft.Adapters.Sql.SqlAdapterBindingElementExtensionElement,Microsoft.Adapters.Sql, Version=<version>, Culture=neutral, PublicKeyToken=<public key>" />  
      ```  

   4. <span data-ttu-id="3abf8-323">"BindingExtensions"system.serviceModel\extensions 下の要素を検索します。</span><span class="sxs-lookup"><span data-stu-id="3abf8-323">Search for the element "bindingExtensions" under system.serviceModel\extensions.</span></span>  

   5. <span data-ttu-id="3abf8-324">"BindingExtensions"ノードの下に、次のセクションを削除します。</span><span class="sxs-lookup"><span data-stu-id="3abf8-324">Remove the following section under the "bindingExtensions" node.</span></span>  

       <span data-ttu-id="3abf8-325">[!INCLUDE[adaptersqlshort](../../includes/adaptersqlshort-md.md)]、削除します。</span><span class="sxs-lookup"><span data-stu-id="3abf8-325">For [!INCLUDE[adaptersqlshort](../../includes/adaptersqlshort-md.md)], remove:</span></span>  

      ```  
      <add name="sqlBinding" type="Microsoft.Adapters.Sql.SqlAdapterBindingCollectionElement,Microsoft.Adapters.Sql, Version=<version>, Culture=neutral, PublicKeyToken=<public key>" />  
      ```  

4. <span data-ttu-id="3abf8-326">machine.config ファイルを保存して閉じます。</span><span class="sxs-lookup"><span data-stu-id="3abf8-326">Save and close the machine.config file.</span></span>  

## <a name="see-also"></a><span data-ttu-id="3abf8-327">参照</span><span class="sxs-lookup"><span data-stu-id="3abf8-327">See also</span></span>
[<span data-ttu-id="3abf8-328">SQL アダプターをインストールする</span><span class="sxs-lookup"><span data-stu-id="3abf8-328">Install the SQL adapter</span></span>](../../adapters-and-accelerators/adapter-sql/install-the-sql-adapter.md)  
[<span data-ttu-id="3abf8-329">BizTalk Adapter for SQL Server を理解する</span><span class="sxs-lookup"><span data-stu-id="3abf8-329">Understand BizTalk Adapter for SQL Server</span></span>](../../adapters-and-accelerators/adapter-sql/understand-biztalk-adapter-for-sql-server.md)