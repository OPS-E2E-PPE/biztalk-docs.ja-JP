---
title: Microsoft BizTalk Adapter for SQL Server - 2016 のインストール |Microsoft ドキュメント
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
ms.openlocfilehash: bab2a1edc7f3f19a8f76a041472a8c6d01b7743d
ms.sourcegitcommit: 5abd0ed3f9e4858ffaaec5481bfa8878595e95f7
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 11/28/2017
ms.locfileid: "25967912"
---
# <a name="install-microsoft-biztalk-adapter-for-sql-server---2016"></a><span data-ttu-id="ce42e-102">Microsoft BizTalk Adapter for SQL Server - 2016 のインストールします。</span><span class="sxs-lookup"><span data-stu-id="ce42e-102">Install Microsoft BizTalk Adapter for SQL Server - 2016</span></span>
<span data-ttu-id="ce42e-103">インストール、[!INCLUDE[adaptersql_md](../../includes/adaptersql-md.md)]に含まれている[!INCLUDE[bts2016_md](../../includes/bts2016-md.md)]です。</span><span class="sxs-lookup"><span data-stu-id="ce42e-103">Install the [!INCLUDE[adaptersql_md](../../includes/adaptersql-md.md)] included with [!INCLUDE[bts2016_md](../../includes/bts2016-md.md)].</span></span>

 <span data-ttu-id="ce42e-104">[!INCLUDE[adaptersqlshort](../../includes/adaptersqlshort-md.md)]で使用できます。</span><span class="sxs-lookup"><span data-stu-id="ce42e-104">The [!INCLUDE[adaptersqlshort](../../includes/adaptersqlshort-md.md)] can be used with:</span></span>  
  
-   <span data-ttu-id="ce42e-105">.NET アプリケーション</span><span class="sxs-lookup"><span data-stu-id="ce42e-105">A .NET application</span></span>  
  
-   <span data-ttu-id="ce42e-106">Microsoft [!INCLUDE[btsBizTalkServerNoVersion](../../includes/btsbiztalkservernoversion-md.md)]</span><span class="sxs-lookup"><span data-stu-id="ce42e-106">Microsoft [!INCLUDE[btsBizTalkServerNoVersion](../../includes/btsbiztalkservernoversion-md.md)]</span></span>  
  
 <span data-ttu-id="ce42e-107">アダプターを使用する方法に基づき、必要なソフトウェアによって異なります。</span><span class="sxs-lookup"><span data-stu-id="ce42e-107">Based on how you use the adapters, the required software varies.</span></span>  
 
  
<a name="BKMK_prereq_NET"></a>   
## <a name="prerequisites-when-using-the-adapter-with-a-net-application"></a><span data-ttu-id="ce42e-108">.NET アプリケーションで、アダプターを使用する場合の前提条件</span><span class="sxs-lookup"><span data-stu-id="ce42e-108">Prerequisites when using the adapter with a .NET Application</span></span>  
<span data-ttu-id="ce42e-109">次のソフトウェアを使用する .NET アプリケーションを作成するコンピューターにインストール、[!INCLUDE[adaptersqlshort](../../includes/adaptersqlshort-md.md)]です。</span><span class="sxs-lookup"><span data-stu-id="ce42e-109">Install the following software on the computer where you are writing .NET applications that consume the [!INCLUDE[adaptersqlshort](../../includes/adaptersqlshort-md.md)].</span></span> <span data-ttu-id="ce42e-110">示されている順序で、ソフトウェアをインストールします。</span><span class="sxs-lookup"><span data-stu-id="ce42e-110">Install the software in the order as listed.</span></span>  

||
|---|
|<span data-ttu-id="ce42e-111">Windows Server 2016</span><span class="sxs-lookup"><span data-stu-id="ce42e-111">- Windows Server 2016</span></span> <br /><span data-ttu-id="ce42e-112">Windows Server 2012 R2</span><span class="sxs-lookup"><span data-stu-id="ce42e-112">- Windows Server 2012 R2</span></span> <br /><span data-ttu-id="ce42e-113">Windows 10</span><span class="sxs-lookup"><span data-stu-id="ce42e-113">- Windows 10</span></span> <br /><span data-ttu-id="ce42e-114">-Windows 8.1</span><span class="sxs-lookup"><span data-stu-id="ce42e-114">- Windows 8.1</span></span>    |
|<span data-ttu-id="ce42e-115">.NET Framework 4.6.*x*</span><span class="sxs-lookup"><span data-stu-id="ce42e-115">.NET Framework 4.6.*x*</span></span>|
|<span data-ttu-id="ce42e-116">Visual Studio 2015</span><span class="sxs-lookup"><span data-stu-id="ce42e-116">Visual Studio 2015</span></span>|
|[!INCLUDE[afproductnameshort](../../includes/afproductnameshort-md.md)]|
|<span data-ttu-id="ce42e-117">SQL Server のクライアント ライブラリです。</span><span class="sxs-lookup"><span data-stu-id="ce42e-117">SQL Server client libraries.</span></span> <span data-ttu-id="ce42e-118">参照してください、[サポートされているバージョン](#BKMK_SuppLOB)(」を参照)。</span><span class="sxs-lookup"><span data-stu-id="ce42e-118">See the [supported versions](#BKMK_SuppLOB) (in this topic).</span></span>|

<a name="BKMK_prereq_BTS"></a>     
## <a name="prerequisites-when-using-the-adapter-with-biztalk-server"></a><span data-ttu-id="ce42e-119">BizTalk Server でアダプターを使用する場合の前提条件</span><span class="sxs-lookup"><span data-stu-id="ce42e-119">Prerequisites when using the adapter with BizTalk Server</span></span>  
<span data-ttu-id="ce42e-120">次のソフトウェアを使用しているコンピューターにインストール、[!INCLUDE[adaptersqlshort](../../includes/adaptersqlshort-md.md)]で[!INCLUDE[btsBizTalkServerNoVersion](../../includes/btsbiztalkservernoversion-md.md)]です。</span><span class="sxs-lookup"><span data-stu-id="ce42e-120">Install the following software on the computer where you are using the [!INCLUDE[adaptersqlshort](../../includes/adaptersqlshort-md.md)] with [!INCLUDE[btsBizTalkServerNoVersion](../../includes/btsbiztalkservernoversion-md.md)].</span></span> <span data-ttu-id="ce42e-121">この順で、ソフトウェアをインストールします。</span><span class="sxs-lookup"><span data-stu-id="ce42e-121">Install the software in the order listed.</span></span>  

||
|---|
|<span data-ttu-id="ce42e-122">Windows Server 2016</span><span class="sxs-lookup"><span data-stu-id="ce42e-122">- Windows Server 2016</span></span> <br /><span data-ttu-id="ce42e-123">Windows Server 2012 R2</span><span class="sxs-lookup"><span data-stu-id="ce42e-123">- Windows Server 2012 R2</span></span> <br /><span data-ttu-id="ce42e-124">Windows 10</span><span class="sxs-lookup"><span data-stu-id="ce42e-124">- Windows 10</span></span> <br /><span data-ttu-id="ce42e-125">-Windows 8.1</span><span class="sxs-lookup"><span data-stu-id="ce42e-125">- Windows 8.1</span></span>    |
|<span data-ttu-id="ce42e-126">.NET Framework 4.6.*x*</span><span class="sxs-lookup"><span data-stu-id="ce42e-126">.NET Framework 4.6.*x*</span></span>|
|<span data-ttu-id="ce42e-127">Visual Studio 2015</span><span class="sxs-lookup"><span data-stu-id="ce42e-127">Visual Studio 2015</span></span>|
|[!INCLUDE[afproductnameshort](../../includes/afproductnameshort-md.md)]<br /><br /> <span data-ttu-id="ce42e-128">インストール、[!INCLUDE[consumeadapterservlong](../../includes/consumeadapterservlong-md.md)]の[!INCLUDE[btsVStudioNoVersion](../../includes/btsvstudionoversion-md.md)]に含まれている、[!INCLUDE[afproductnameshort](../../includes/afproductnameshort-md.md)]です。</span><span class="sxs-lookup"><span data-stu-id="ce42e-128">Install the [!INCLUDE[consumeadapterservlong](../../includes/consumeadapterservlong-md.md)] for [!INCLUDE[btsVStudioNoVersion](../../includes/btsvstudionoversion-md.md)] included with the [!INCLUDE[afproductnameshort](../../includes/afproductnameshort-md.md)].</span></span> <span data-ttu-id="ce42e-129">インストールするには、**カスタム**(選択**BizTalk Server アドイン**) または**完了**のインストール、[!INCLUDE[afproductnameshort](../../includes/afproductnameshort-md.md)]です。</span><span class="sxs-lookup"><span data-stu-id="ce42e-129">To install, do a **Custom** (select **BizTalk Server Addin**) or **Complete** installation of the [!INCLUDE[afproductnameshort](../../includes/afproductnameshort-md.md)].</span></span>|
|[!INCLUDE[bts2016_md](../../includes/bts2016-md.md)]|
|<span data-ttu-id="ce42e-130">SQL Server のクライアント ライブラリです。</span><span class="sxs-lookup"><span data-stu-id="ce42e-130">SQL Server client libraries.</span></span> <span data-ttu-id="ce42e-131">参照してください、[サポートされているバージョン](#BKMK_SuppLOB)(」を参照)。</span><span class="sxs-lookup"><span data-stu-id="ce42e-131">See the [supported versions](#BKMK_SuppLOB) (in this topic).</span></span>|

<a name="BKMK_SuppLOB"></a>   
## <a name="supported-sql-server-versions-and-client-libraries"></a><span data-ttu-id="ce42e-132">サポートされている SQL Server のバージョンとクライアント ライブラリ</span><span class="sxs-lookup"><span data-stu-id="ce42e-132">Supported SQL Server versions and client libraries</span></span>  
 <span data-ttu-id="ce42e-133">次のセクションではサポートされている SQL Server のバージョンと、クライアントで必要なライブラリ、[!INCLUDE[adaptersqlshort](../../includes/adaptersqlshort-md.md)]です。</span><span class="sxs-lookup"><span data-stu-id="ce42e-133">The following section presents the supported SQL Server versions and the client libraries required by the [!INCLUDE[adaptersqlshort](../../includes/adaptersqlshort-md.md)].</span></span>  
  
-   <span data-ttu-id="ce42e-134">**サポートされているサーバー バージョン**: SQL Server 2016、SQL Server 2014</span><span class="sxs-lookup"><span data-stu-id="ce42e-134">**Supported server versions**: SQL Server 2016, SQL Server 2014</span></span>
  
-   <span data-ttu-id="ce42e-135">**サポートされているクライアント バージョン**: Microsoft[!INCLUDE[btsDotNetFramework_md](../../includes/btsdotnetframework-md.md)]バンドルの SQL Server に接続するクライアント Dll が必要です。</span><span class="sxs-lookup"><span data-stu-id="ce42e-135">**Supported client versions**: Microsoft [!INCLUDE[btsDotNetFramework_md](../../includes/btsdotnetframework-md.md)] bundles the client DLLs required to connect to SQL Server.</span></span> <span data-ttu-id="ce42e-136">お使いのコンピューターに明示的に任意のクライアント Dll をインストールする必要はありません。</span><span class="sxs-lookup"><span data-stu-id="ce42e-136">You do not need to explicitly install any client DLLs on your computer.</span></span>  
  
-   <span data-ttu-id="ce42e-137">**必要なドライバー**:</span><span class="sxs-lookup"><span data-stu-id="ce42e-137">**Required drivers**:</span></span>  
  
    -   <span data-ttu-id="ce42e-138">SQL Server のバージョン、たとえば、Geography に付属して Udt を使用する場合は、次の Dll は、SQL Server 上の操作を実行するアダプターを使用するコンピューター上に存在を確認します。</span><span class="sxs-lookup"><span data-stu-id="ce42e-138">If you use the UDTs shipped with the SQL Server versions, for example, Geography, make sure the following DLLs are present on the computer where you use the adapter to perform operations on SQL Server.</span></span> <span data-ttu-id="ce42e-139">など、SQL Server 上の操作を実行する BizTalk プロジェクトを作成する場合は、これらの Dll が BizTalk Server が実行されているコンピューター上に存在する必要があります。</span><span class="sxs-lookup"><span data-stu-id="ce42e-139">For example, if you create BizTalk projects to perform operations on SQL Server, these DLLs must be present on the computer where BizTalk Server is running.</span></span>  
  
        -   <span data-ttu-id="ce42e-140">Microsoft.SqlServer.Types.dll は GAC に追加することを確認します。</span><span class="sxs-lookup"><span data-stu-id="ce42e-140">Make sure Microsoft.SqlServer.Types.dll is added to the GAC.</span></span>  
  
        -   <span data-ttu-id="ce42e-141">SqlServerSpatial.dll が System32 フォルダーにあることを確認してください。</span><span class="sxs-lookup"><span data-stu-id="ce42e-141">Make sure SqlServerSpatial.dll is available in the System32 folder.</span></span>  
  
         <span data-ttu-id="ce42e-142">SQL Server セットアップを実行しを選択すると、コンピューターにこれらの Dll をインストールできます**管理ツール-基本**と**管理ツール-完全**で、**機能の選択**ウィザードのページです。</span><span class="sxs-lookup"><span data-stu-id="ce42e-142">You can install these DLLs on the computer by running the SQL Server setup and selecting **Management Tools – Basic** and **Management Tools – Complete** in the **Feature Selection** page of the wizard.</span></span>  
  
    -   <span data-ttu-id="ce42e-143">FILESTREAM データ型の列に対して操作を実行するアダプターを使用する場合は、SQL クライアント接続 SDK がインストールされている必要があることを確認してください。</span><span class="sxs-lookup"><span data-stu-id="ce42e-143">If you use the adapter to perform operations on columns of FILESTREAM data types, make sure you have SQL Client Connectivity SDK installed.</span></span> <span data-ttu-id="ce42e-144">SQL Server セットアップを実行しを選択すると、SQL クライアント接続 SDK をインストールすることができます**SQL クライアント接続 SDK**で、**機能の選択**ウィザードのページです。</span><span class="sxs-lookup"><span data-stu-id="ce42e-144">You can install the SQL Client Connectivity SDK by running the SQL Server setup and selecting **SQL Client Connectivity SDK** in the **Feature Selection** page of the wizard.</span></span> <span data-ttu-id="ce42e-145">アダプターは、FILESTREAM 操作を実行するのに、SQL クライアント接続 SDK と共にインストールされる、sqlncli10.dll を使用します。</span><span class="sxs-lookup"><span data-stu-id="ce42e-145">The adapter uses the sqlncli10.dll, installed with the SQL Client Connectivity SDK, to perform FILESTREAM operations.</span></span>  
  
    -   <span data-ttu-id="ce42e-146">SQL Server で、独自の Udt を作成する場合は、Udt のそれぞれのアセンブリが GAC に追加を確認します。</span><span class="sxs-lookup"><span data-stu-id="ce42e-146">If you create your own UDTs in SQL Server, make sure the respective assemblies for the UDTs are added to the GAC.</span></span>  
  
<a name="BKMK_Compat"></a>   
## <a name="64-bit-support"></a><span data-ttu-id="ce42e-147">64 ビットのサポート</span><span class="sxs-lookup"><span data-stu-id="ce42e-147">64-bit support</span></span> 

<span data-ttu-id="ce42e-148">[!INCLUDE[adaptersqlshort](../../includes/adaptersqlshort-md.md)] 32 ビットまたは 64 ビット ホスト インスタンスで実行できます。</span><span class="sxs-lookup"><span data-stu-id="ce42e-148">The [!INCLUDE[adaptersqlshort](../../includes/adaptersqlshort-md.md)] can run in a 32-bit or 64-bit host instance.</span></span>

 <span data-ttu-id="ce42e-149">32 ビットおよび 64 ビットのサポートされているインストール シナリオについては[!INCLUDE[adaptersqlshort](../../includes/adaptersqlshort-md.md)]を参照してください[32 ビットおよび 64 ビット インストール シナリオ](#BKMK_Install_Scenarios)(」を参照)。</span><span class="sxs-lookup"><span data-stu-id="ce42e-149">For information about the supported installation scenarios for the 32-bit and 64-bit [!INCLUDE[adaptersqlshort](../../includes/adaptersqlshort-md.md)], see  [32-bit and 64-bit install scenarios](#BKMK_Install_Scenarios) (in this topic).</span></span>
  
<a name="BKMK_Install_Adap"></a>   
## <a name="install-the-sql-adapter"></a><span data-ttu-id="ce42e-150">SQL アダプターをインストールします。</span><span class="sxs-lookup"><span data-stu-id="ce42e-150">Install the SQL adapter</span></span>  
 <span data-ttu-id="ce42e-151">インストールする前にインストールされている前提条件があるかどうかを確認、[!INCLUDE[adaptersqlshort](../../includes/adaptersqlshort-md.md)]です。</span><span class="sxs-lookup"><span data-stu-id="ce42e-151">Make sure you have the prerequisites installed before installing the [!INCLUDE[adaptersqlshort](../../includes/adaptersqlshort-md.md)].</span></span> <span data-ttu-id="ce42e-152">参照してください[.NET の前提条件](#BKMK_prereq_NET)(このトピックの)、または[BizTalk Server の前提条件](#BKMK_prereq_BTS)(」を参照)。</span><span class="sxs-lookup"><span data-stu-id="ce42e-152">See [.NET prerequisites](#BKMK_prereq_NET) (in this topic), or [BizTalk Server prerequisites](#BKMK_prereq_BTS) (in this topic).</span></span>
  
 <span data-ttu-id="ce42e-153">インストールすることができます、[!INCLUDE[adaptersqlshort](../../includes/adaptersqlshort-md.md)]次の 2 つの方法で。</span><span class="sxs-lookup"><span data-stu-id="ce42e-153">You can install the [!INCLUDE[adaptersqlshort](../../includes/adaptersqlshort-md.md)] in the following two ways:</span></span>  
  
-   <span data-ttu-id="ce42e-154">**対話モードで**セットアップ ウィザードを使用します。</span><span class="sxs-lookup"><span data-stu-id="ce42e-154">**In interactive mode** using the setup wizard</span></span>
  
-   <span data-ttu-id="ce42e-155">**サイレント モードで**コマンド ラインで msiexec を使用します。</span><span class="sxs-lookup"><span data-stu-id="ce42e-155">**In silent mode** using msiexec in the command line</span></span>  
  
    > [!IMPORTANT]
    >  <span data-ttu-id="ce42e-156">インストールするコンピューターで管理者特権を持つ必要があります、[!INCLUDE[adaptersqlshort](../../includes/adaptersqlshort-md.md)]ウィザードまたはコマンドラインを使用してインストールするかどうかのあるかにかかわらず、します。</span><span class="sxs-lookup"><span data-stu-id="ce42e-156">You must have administrative privileges on the computer where you install the [!INCLUDE[adaptersqlshort](../../includes/adaptersqlshort-md.md)], irrespective of whether you are installing by using the wizard or the command line.</span></span>    

### <a name="BKMK_Install_Scenarios"></a><span data-ttu-id="ce42e-157">32 ビットおよび 64 ビット インストール シナリオ</span><span class="sxs-lookup"><span data-stu-id="ce42e-157">32-bit and 64-bit install scenarios</span></span>
 <span data-ttu-id="ce42e-158">[!INCLUDE[btsBizTalkServerNoVersion](../../includes/btsbiztalkservernoversion-md.md)]、[!INCLUDE[adaptersqlshort](../../includes/adaptersqlshort-md.md)]に使用できます。</span><span class="sxs-lookup"><span data-stu-id="ce42e-158">With [!INCLUDE[btsBizTalkServerNoVersion](../../includes/btsbiztalkservernoversion-md.md)], the [!INCLUDE[adaptersqlshort](../../includes/adaptersqlshort-md.md)] can be used for:</span></span>  
  
-   [!INCLUDE[btsVStudioNoVersion](../../includes/btsvstudionoversion-md.md)]<span data-ttu-id="ce42e-159">デザイン時 (操作のメタデータを生成する) ときにします。</span><span class="sxs-lookup"><span data-stu-id="ce42e-159"> design time (when generating metadata for operations).</span></span>  
  
-   <span data-ttu-id="ce42e-160">BizTalk Server 管理コンソール デザイン時 (物理ポートの作成) します。</span><span class="sxs-lookup"><span data-stu-id="ce42e-160">BizTalk Server Administration console design time (for creating physical ports).</span></span>  
  
    > [!NOTE]
    >  <span data-ttu-id="ce42e-161">BizTalk Server 管理コンソールは、32 ビット Microsoft 管理コンソール (MMC) アプリケーションとして実行されます。</span><span class="sxs-lookup"><span data-stu-id="ce42e-161">BizTalk Server Administration console runs as a 32-bit Microsoft Management Console (MMC) application.</span></span>  
  
-   <span data-ttu-id="ce42e-162">BizTalk ランタイム (ときに送信し、LOB アプリケーションからメッセージを受信)。</span><span class="sxs-lookup"><span data-stu-id="ce42e-162">BizTalk run time (when sending and receiving messages from LOB applications).</span></span>  
  
 <span data-ttu-id="ce42e-163">同じコンピューターまたは別のコンピューターでこれらすべてのタスクを実行するインストールことができます。</span><span class="sxs-lookup"><span data-stu-id="ce42e-163">You can have an installation where you perform all these tasks on the same computer or different computers.</span></span> <span data-ttu-id="ce42e-164">両方[!INCLUDE[btsVStudioNoVersion](../../includes/btsvstudionoversion-md.md)]と BizTalk MMC は 32 ビット プロセスが、32 ビットをインストールする必要があります[!INCLUDE[adaptersqlshort](../../includes/adaptersqlshort-md.md)]デザイン時のタスクを実行するコンピューターにします。</span><span class="sxs-lookup"><span data-stu-id="ce42e-164">Because both [!INCLUDE[btsVStudioNoVersion](../../includes/btsvstudionoversion-md.md)] and BizTalk MMC are 32-bit processes, you must install the 32-bit [!INCLUDE[adaptersqlshort](../../includes/adaptersqlshort-md.md)] on the computer where you want to perform the design-time tasks.</span></span> <span data-ttu-id="ce42e-165">インストールするため、次のシナリオがサポートされている、 [!INCLUDE[adaptersqlshort](../../includes/adaptersqlshort-md.md)] 32 ビットおよび 64 ビット プラットフォーム上でします。</span><span class="sxs-lookup"><span data-stu-id="ce42e-165">The following scenarios are supported for installing the [!INCLUDE[adaptersqlshort](../../includes/adaptersqlshort-md.md)] on 32-bit and 64-bit platforms.</span></span>  
  
#### <a name="32-bit-install-scenarios"></a><span data-ttu-id="ce42e-166">32 ビット インストール シナリオ</span><span class="sxs-lookup"><span data-stu-id="ce42e-166">32-bit install scenarios</span></span>  
 <span data-ttu-id="ce42e-167">インストールするときに、次のシナリオがサポートされて、 [!INCLUDE[adaptersqlshort](../../includes/adaptersqlshort-md.md)] 32 ビット プラットフォーム上でします。</span><span class="sxs-lookup"><span data-stu-id="ce42e-167">The following scenarios are supported when installing the [!INCLUDE[adaptersqlshort](../../includes/adaptersqlshort-md.md)] on a 32-bit platform.</span></span>  
  
|<span data-ttu-id="ce42e-168">Visual Studio のデザイン時</span><span class="sxs-lookup"><span data-stu-id="ce42e-168">Visual Studio design time</span></span>|<span data-ttu-id="ce42e-169">デザイン時の BizTalk MMC</span><span class="sxs-lookup"><span data-stu-id="ce42e-169">BizTalk MMC design time</span></span>|<span data-ttu-id="ce42e-170">BizTalk ランタイム</span><span class="sxs-lookup"><span data-stu-id="ce42e-170">BizTalk run time</span></span>|<span data-ttu-id="ce42e-171">Visual Studio デザイン時またはデザイン時の BizTalk MMC + BizTalk ランタイムします。</span><span class="sxs-lookup"><span data-stu-id="ce42e-171">Visual Studio design time and/or  BizTalk MMC design time + BizTalk run time</span></span>|  
|---|---|---|---|  
|<span data-ttu-id="ce42e-172">がインストール 32 ビット[!INCLUDE[afproductnameshort](../../includes/afproductnameshort-md.md)]です。</span><span class="sxs-lookup"><span data-stu-id="ce42e-172">- Install 32-bit [!INCLUDE[afproductnameshort](../../includes/afproductnameshort-md.md)].</span></span><br /><br /> <span data-ttu-id="ce42e-173">がインストール 32 ビット[!INCLUDE[adaptersqlshort](../../includes/adaptersqlshort-md.md)]です。</span><span class="sxs-lookup"><span data-stu-id="ce42e-173">- Install 32-bit [!INCLUDE[adaptersqlshort](../../includes/adaptersqlshort-md.md)].</span></span><br /><br /> <span data-ttu-id="ce42e-174">32 ビット クライアントとその他の必要な Dll をインストールします。</span><span class="sxs-lookup"><span data-stu-id="ce42e-174">- Install 32-bit client and other required DLLs.</span></span>|<span data-ttu-id="ce42e-175">がインストール 32 ビット[!INCLUDE[afproductnameshort](../../includes/afproductnameshort-md.md)]です。</span><span class="sxs-lookup"><span data-stu-id="ce42e-175">- Install 32-bit [!INCLUDE[afproductnameshort](../../includes/afproductnameshort-md.md)].</span></span><br /><br /> <span data-ttu-id="ce42e-176">がインストール 32 ビット[!INCLUDE[adaptersqlshort](../../includes/adaptersqlshort-md.md)]です。</span><span class="sxs-lookup"><span data-stu-id="ce42e-176">- Install 32-bit [!INCLUDE[adaptersqlshort](../../includes/adaptersqlshort-md.md)].</span></span><br /><br /> <span data-ttu-id="ce42e-177">32 ビット クライアントとその他の必要な Dll をインストールします。</span><span class="sxs-lookup"><span data-stu-id="ce42e-177">- Install 32-bit client and other required DLLs.</span></span>|<span data-ttu-id="ce42e-178">がインストール 32 ビット[!INCLUDE[afproductnameshort](../../includes/afproductnameshort-md.md)]です。</span><span class="sxs-lookup"><span data-stu-id="ce42e-178">- Install 32-bit [!INCLUDE[afproductnameshort](../../includes/afproductnameshort-md.md)].</span></span><br /><br /> <span data-ttu-id="ce42e-179">がインストール 32 ビット[!INCLUDE[adaptersqlshort](../../includes/adaptersqlshort-md.md)]です。</span><span class="sxs-lookup"><span data-stu-id="ce42e-179">- Install 32-bit [!INCLUDE[adaptersqlshort](../../includes/adaptersqlshort-md.md)].</span></span><br /><br /> <span data-ttu-id="ce42e-180">32 ビット クライアントとその他の必要な Dll をインストールします。</span><span class="sxs-lookup"><span data-stu-id="ce42e-180">- Install 32-bit client and other required DLLs.</span></span>|<span data-ttu-id="ce42e-181">がインストール 32 ビット[!INCLUDE[afproductnameshort](../../includes/afproductnameshort-md.md)]です。</span><span class="sxs-lookup"><span data-stu-id="ce42e-181">- Install 32-bit [!INCLUDE[afproductnameshort](../../includes/afproductnameshort-md.md)].</span></span><br /><br /> <span data-ttu-id="ce42e-182">がインストール 32 ビット[!INCLUDE[adaptersqlshort](../../includes/adaptersqlshort-md.md)]です。</span><span class="sxs-lookup"><span data-stu-id="ce42e-182">- Install 32-bit [!INCLUDE[adaptersqlshort](../../includes/adaptersqlshort-md.md)].</span></span><br /><br /> <span data-ttu-id="ce42e-183">32 ビット クライアントとその他の必要な Dll をインストールします。</span><span class="sxs-lookup"><span data-stu-id="ce42e-183">- Install 32-bit client and other required DLLs.</span></span>|  
  
#### <a name="64-bit-install-scenarios"></a><span data-ttu-id="ce42e-184">64 ビット インストール シナリオ</span><span class="sxs-lookup"><span data-stu-id="ce42e-184">64-bit install scenarios</span></span>  
 <span data-ttu-id="ce42e-185">インストールするときに、次のシナリオがサポートされて、 [!INCLUDE[adaptersqlshort](../../includes/adaptersqlshort-md.md)] 64 ビット プラットフォーム上でします。</span><span class="sxs-lookup"><span data-stu-id="ce42e-185">The following scenarios are supported when installing the [!INCLUDE[adaptersqlshort](../../includes/adaptersqlshort-md.md)] on a 64-bit platform.</span></span>  
  
> [!NOTE]
>  <span data-ttu-id="ce42e-186">いずれかを使用してデザイン時のタスクを実行する任意のコンピューターで[!INCLUDE[btsVStudioNoVersion](../../includes/btsvstudionoversion-md.md)]BizTalk MMC で、32 ビットをインストールする必要がありますまたは[!INCLUDE[adaptersqlshort](../../includes/adaptersqlshort-md.md)]です。</span><span class="sxs-lookup"><span data-stu-id="ce42e-186">On any computer where you want to perform design-time tasks using either [!INCLUDE[btsVStudioNoVersion](../../includes/btsvstudionoversion-md.md)] or BizTalk MMC, you must install the 32-bit [!INCLUDE[adaptersqlshort](../../includes/adaptersqlshort-md.md)].</span></span>  
  
|<span data-ttu-id="ce42e-187">Visual Studio のデザイン時</span><span class="sxs-lookup"><span data-stu-id="ce42e-187">Visual Studio design time</span></span>|<span data-ttu-id="ce42e-188">デザイン時の BizTalk MMC</span><span class="sxs-lookup"><span data-stu-id="ce42e-188">BizTalk MMC design time</span></span>|<span data-ttu-id="ce42e-189">BizTalk ランタイム</span><span class="sxs-lookup"><span data-stu-id="ce42e-189">BizTalk run time</span></span>|<span data-ttu-id="ce42e-190">Visual Studio デザイン時またはデザイン時の BizTalk MMC + BizTalk ランタイムします。</span><span class="sxs-lookup"><span data-stu-id="ce42e-190">Visual Studio design time and/or BizTalk MMC design time + BizTalk run time</span></span>|  
|---|---|---|---|  
|<span data-ttu-id="ce42e-191">がインストール 64 ビット[!INCLUDE[afproductnameshort](../../includes/afproductnameshort-md.md)]です。</span><span class="sxs-lookup"><span data-stu-id="ce42e-191">- Install 64-bit [!INCLUDE[afproductnameshort](../../includes/afproductnameshort-md.md)].</span></span><br /><br /> <span data-ttu-id="ce42e-192">がインストール 32 ビット[!INCLUDE[adaptersqlshort](../../includes/adaptersqlshort-md.md)]です。</span><span class="sxs-lookup"><span data-stu-id="ce42e-192">- Install 32-bit [!INCLUDE[adaptersqlshort](../../includes/adaptersqlshort-md.md)].</span></span><br /><br /> <span data-ttu-id="ce42e-193">32 ビット クライアントとその他の必要な Dll をインストールします。</span><span class="sxs-lookup"><span data-stu-id="ce42e-193">- Install 32-bit client and other required DLLs.</span></span>|<span data-ttu-id="ce42e-194">がインストール 64 ビット[!INCLUDE[afproductnameshort](../../includes/afproductnameshort-md.md)]です。</span><span class="sxs-lookup"><span data-stu-id="ce42e-194">- Install 64-bit [!INCLUDE[afproductnameshort](../../includes/afproductnameshort-md.md)].</span></span><br /><br /> <span data-ttu-id="ce42e-195">がインストール 32 ビット[!INCLUDE[adaptersqlshort](../../includes/adaptersqlshort-md.md)]です。</span><span class="sxs-lookup"><span data-stu-id="ce42e-195">- Install 32-bit [!INCLUDE[adaptersqlshort](../../includes/adaptersqlshort-md.md)].</span></span><br /><br /> <span data-ttu-id="ce42e-196">32 ビット クライアントとその他の必要な Dll をインストールします。</span><span class="sxs-lookup"><span data-stu-id="ce42e-196">- Install 32-bit client and other required DLLs.</span></span>|<span data-ttu-id="ce42e-197">**32 ビット BizTalk プロセス**:</span><span class="sxs-lookup"><span data-stu-id="ce42e-197">**For a 32-bit BizTalk process**:</span></span><br /><br /> <span data-ttu-id="ce42e-198">がインストール 64 ビット[!INCLUDE[afproductnameshort](../../includes/afproductnameshort-md.md)]です。</span><span class="sxs-lookup"><span data-stu-id="ce42e-198">- Install 64-bit [!INCLUDE[afproductnameshort](../../includes/afproductnameshort-md.md)].</span></span><br /><br /> <span data-ttu-id="ce42e-199">がインストール 32 ビット[!INCLUDE[adaptersqlshort](../../includes/adaptersqlshort-md.md)]です。</span><span class="sxs-lookup"><span data-stu-id="ce42e-199">- Install 32-bit [!INCLUDE[adaptersqlshort](../../includes/adaptersqlshort-md.md)].</span></span><br /><br /> <span data-ttu-id="ce42e-200">32 ビット クライアントとその他の必要な Dll をインストールします。</span><span class="sxs-lookup"><span data-stu-id="ce42e-200">- Install 32-bit client and other required DLLs.</span></span><br /><br /> <span data-ttu-id="ce42e-201">**64 ビットの BizTalk プロセス**:</span><span class="sxs-lookup"><span data-stu-id="ce42e-201">**For a 64-bit BizTalk process**:</span></span><br /><br /> <span data-ttu-id="ce42e-202">がインストール 64 ビット[!INCLUDE[afproductnameshort](../../includes/afproductnameshort-md.md)]です。</span><span class="sxs-lookup"><span data-stu-id="ce42e-202">- Install 64-bit [!INCLUDE[afproductnameshort](../../includes/afproductnameshort-md.md)].</span></span><br /><br /> <span data-ttu-id="ce42e-203">がインストール 64 ビット[!INCLUDE[adaptersqlshort](../../includes/adaptersqlshort-md.md)]です。</span><span class="sxs-lookup"><span data-stu-id="ce42e-203">- Install 64-bit [!INCLUDE[adaptersqlshort](../../includes/adaptersqlshort-md.md)].</span></span><br /><br /> <span data-ttu-id="ce42e-204">-64 ビット クライアントとその他の必要な Dll をインストールします。</span><span class="sxs-lookup"><span data-stu-id="ce42e-204">- Install 64-bit client and other required DLLs.</span></span>|<span data-ttu-id="ce42e-205">**32 ビット BizTalk プロセス**:</span><span class="sxs-lookup"><span data-stu-id="ce42e-205">**For a 32-bit BizTalk process**:</span></span><br /><br /> <span data-ttu-id="ce42e-206">がインストール 64 ビット[!INCLUDE[afproductnameshort](../../includes/afproductnameshort-md.md)]です。</span><span class="sxs-lookup"><span data-stu-id="ce42e-206">- Install 64-bit [!INCLUDE[afproductnameshort](../../includes/afproductnameshort-md.md)].</span></span><br /><br /> <span data-ttu-id="ce42e-207">がインストール 32 ビット[!INCLUDE[adaptersqlshort](../../includes/adaptersqlshort-md.md)]です。</span><span class="sxs-lookup"><span data-stu-id="ce42e-207">- Install 32-bit [!INCLUDE[adaptersqlshort](../../includes/adaptersqlshort-md.md)].</span></span><br /><br /> <span data-ttu-id="ce42e-208">32 ビット クライアントとその他の必要な Dll をインストールします。</span><span class="sxs-lookup"><span data-stu-id="ce42e-208">- Install 32-bit client and other required DLLs.</span></span><br /><br /> <span data-ttu-id="ce42e-209">**64 ビットの BizTalk プロセス**:</span><span class="sxs-lookup"><span data-stu-id="ce42e-209">**For a 64-bit BizTalk process**:</span></span><br /><br /> <span data-ttu-id="ce42e-210">がインストール 64 ビット[!INCLUDE[afproductnameshort](../../includes/afproductnameshort-md.md)]です。</span><span class="sxs-lookup"><span data-stu-id="ce42e-210">- Install 64-bit [!INCLUDE[afproductnameshort](../../includes/afproductnameshort-md.md)].</span></span><br /><br /> <span data-ttu-id="ce42e-211">がインストール 64 ビット[!INCLUDE[adaptersqlshort](../../includes/adaptersqlshort-md.md)]です。</span><span class="sxs-lookup"><span data-stu-id="ce42e-211">- Install 64-bit [!INCLUDE[adaptersqlshort](../../includes/adaptersqlshort-md.md)].</span></span><br /><br /> <span data-ttu-id="ce42e-212">-64 ビット クライアントとその他の必要な Dll をインストールします。</span><span class="sxs-lookup"><span data-stu-id="ce42e-212">- Install 64-bit client and other required DLLs.</span></span><br /><br /> <span data-ttu-id="ce42e-213">がインストール 32 ビット[!INCLUDE[adaptersqlshort](../../includes/adaptersqlshort-md.md)]です。</span><span class="sxs-lookup"><span data-stu-id="ce42e-213">- Install 32-bit [!INCLUDE[adaptersqlshort](../../includes/adaptersqlshort-md.md)].</span></span><br /><br /> <span data-ttu-id="ce42e-214">32 ビット クライアントとその他の必要な Dll をインストールします。</span><span class="sxs-lookup"><span data-stu-id="ce42e-214">- Install 32-bit client and other required DLLs.</span></span>|  
  
<a name="BKMK_Install_wizard"></a>   
### <a name="install-the-adapter-in-interactive-mode"></a><span data-ttu-id="ce42e-215">対話モードでのアダプターをインストールします。</span><span class="sxs-lookup"><span data-stu-id="ce42e-215">Install the adapter in interactive mode</span></span>  
<span data-ttu-id="ce42e-216">次の手順に従って、インストールを完了、[!INCLUDE[adaptersqlshort](../../includes/adaptersqlshort-md.md)]セットアップ ウィザードを使用します。</span><span class="sxs-lookup"><span data-stu-id="ce42e-216">Complete the following steps to install the [!INCLUDE[adaptersqlshort](../../includes/adaptersqlshort-md.md)] using the setup wizard.</span></span>  
  
1.  <span data-ttu-id="ce42e-217">インストーラーを実行します。</span><span class="sxs-lookup"><span data-stu-id="ce42e-217">Run the installer.</span></span>  
  
    > [!NOTE]
    >  <span data-ttu-id="ce42e-218">インストールする場合、[!INCLUDE[adaptersqlshort](../../includes/adaptersqlshort-md.md)]バーチャル マシンで、セットアップ ウィザードは使用可能なディスク容量については、セットアップがチェックされることを通知 ダイアログ ボックス続行されません可能性があります。</span><span class="sxs-lookup"><span data-stu-id="ce42e-218">If you are installing the [!INCLUDE[adaptersqlshort](../../includes/adaptersqlshort-md.md)] on a virtual machine, the setup wizard might not proceed beyond a dialog box informing that the setup is checking for available disk space.</span></span> <span data-ttu-id="ce42e-219">このような場合、サイレント インストール オプションを使用することをお勧めします。</span><span class="sxs-lookup"><span data-stu-id="ce42e-219">In such cases, we recommend that you use the silent installation option.</span></span> <span data-ttu-id="ce42e-220">詳細については、次を参照してください。[サイレント モードで、SQL アダプターをインストール](#BKMK_SilentInst)(」を参照)。</span><span class="sxs-lookup"><span data-stu-id="ce42e-220">For more information, see [Install the SQL adapter in silent mode](#BKMK_SilentInst) (in this topic).</span></span>
  
2.  <span data-ttu-id="ce42e-221">[ようこそ] 画面で、情報を参照し、をクリックして**次**です。</span><span class="sxs-lookup"><span data-stu-id="ce42e-221">Read the information on the Welcome screen, and then click **Next**.</span></span>  
  
3.  <span data-ttu-id="ce42e-222">読み取り、使用許諾契約書 (EULA) に同意し、クリックして**次**です。</span><span class="sxs-lookup"><span data-stu-id="ce42e-222">Read and accept the end-user license agreement (EULA), and then click **Next**.</span></span>  
  
4.  <span data-ttu-id="ce42e-223">**コピー先フォルダー**  ダイアログ ボックスで、インストールする場所を指定、 [!INCLUDE[adaptersqlshort](../../includes/adaptersqlshort-md.md)]、 をクリックして **[次へ]**、クリックして**インストール**です。</span><span class="sxs-lookup"><span data-stu-id="ce42e-223">In the **Destination Folder** dialog box, specify the location where you want to install the [!INCLUDE[adaptersqlshort](../../includes/adaptersqlshort-md.md)], click **Next**, and then click **Install**.</span></span>  
  
5.  <span data-ttu-id="ce42e-224">**カスタマー エクスペリエンス向上プログラム** ダイアログ ボックスで、カスタマー エクスペリエンス向上プログラム (CEIP) に登録するかどうかを指定します。</span><span class="sxs-lookup"><span data-stu-id="ce42e-224">In the **Customer Experience Improvement Program** dialog box, specify whether you would like to enroll for the Customer Experience Improvement Program (CEIP).</span></span> <span data-ttu-id="ce42e-225">CEIP 用の一部として[!INCLUDE[adaptersqlshort](../../includes/adaptersqlshort-md.md)]、次のデータは、Microsoft と共有されます。</span><span class="sxs-lookup"><span data-stu-id="ce42e-225">As part of CEIP for [!INCLUDE[adaptersqlshort](../../includes/adaptersqlshort-md.md)], you will share the following data with Microsoft:</span></span>  
  
    -   <span data-ttu-id="ce42e-226">インストールしているコンピューターのハードウェアに関連するデータ、[!INCLUDE[adaptersqlshort](../../includes/adaptersqlshort-md.md)]です。</span><span class="sxs-lookup"><span data-stu-id="ce42e-226">Data related to the computer hardware on which you are installing the [!INCLUDE[adaptersqlshort](../../includes/adaptersqlshort-md.md)].</span></span>  
  
    -   <span data-ttu-id="ce42e-227">使用して接続を使用している SQL Server のバージョンに関連するデータ、[!INCLUDE[adaptersqlshort](../../includes/adaptersqlshort-md.md)]です。</span><span class="sxs-lookup"><span data-stu-id="ce42e-227">Data related to the SQL Server versions you are using to connect using the [!INCLUDE[adaptersqlshort](../../includes/adaptersqlshort-md.md)].</span></span>  
  
     <span data-ttu-id="ce42e-228">指定し、をクリックして**OK**です。</span><span class="sxs-lookup"><span data-stu-id="ce42e-228">Specify your choice and click **OK**.</span></span>  
  
    > [!NOTE]
    >  <span data-ttu-id="ce42e-229">常に、基本設定を変更することができます修復モードで、コントロール パネルから、セットアップを実行して、CEIP の登録に関連します。</span><span class="sxs-lookup"><span data-stu-id="ce42e-229">You can always change your preference regarding enrolling for CEIP by running the Setup in Repair mode from the Control Panel.</span></span>  
  
6.  <span data-ttu-id="ce42e-230">**[完了]** をクリックします。</span><span class="sxs-lookup"><span data-stu-id="ce42e-230">Click **Finish**.</span></span>  
  
<a name="BKMK_SilentInst"></a>   
### <a name="install-the-sql-adapter-in-silent-mode"></a><span data-ttu-id="ce42e-231">サイレント モードでの SQL アダプターをインストールします。</span><span class="sxs-lookup"><span data-stu-id="ce42e-231">Install the SQL adapter in silent mode</span></span> 
<span data-ttu-id="ce42e-232">サイレント インストールを行うには、次の手順を完了[!INCLUDE[adaptersqlshort](../../includes/adaptersqlshort-md.md)]を使用して、`msiexec`コマンド。</span><span class="sxs-lookup"><span data-stu-id="ce42e-232">Complete the following steps to do a silent installation of [!INCLUDE[adaptersqlshort](../../includes/adaptersqlshort-md.md)] using the `msiexec` command.</span></span>  
  
1.  <span data-ttu-id="ce42e-233">コマンド プロンプトを開き、および、インストーラーを持っているフォルダーに移動します。</span><span class="sxs-lookup"><span data-stu-id="ce42e-233">Open a command prompt, and navigate to the folder where you have the installer.</span></span>  
  
2.  <span data-ttu-id="ce42e-234">インストールするには、次のコマンドを実行、 [!INCLUDE[adaptersqlshort](../../includes/adaptersqlshort-md.md)]:</span><span class="sxs-lookup"><span data-stu-id="ce42e-234">Run the following command to install the [!INCLUDE[adaptersqlshort](../../includes/adaptersqlshort-md.md)]:</span></span>  
  
    > [!NOTE]
    >  <span data-ttu-id="ce42e-235">次のコマンドでの x64 ベースのプラットフォームでサイレント インストールを実行するには、SqlAdapterSetup64.msi で SqlAdapterSetup.msi を置き換えます。</span><span class="sxs-lookup"><span data-stu-id="ce42e-235">To perform silent installation on an x64-based platform, in the following commands, replace SqlAdapterSetup.msi with SqlAdapterSetup64.msi.</span></span>  
  
    ```  
    msiexec /i SqlAdapterSetup.msi /qn  
    ```  
  
     <span data-ttu-id="ce42e-236">CEIP をサイレント インストールの一部として登録することもできます。</span><span class="sxs-lookup"><span data-stu-id="ce42e-236">You can also choose to enroll for CEIP as part of the silent installation.</span></span> <span data-ttu-id="ce42e-237">CEIP 用の一部として[!INCLUDE[adaptersqlshort](../../includes/adaptersqlshort-md.md)]、次のデータは、Microsoft と共有されます。</span><span class="sxs-lookup"><span data-stu-id="ce42e-237">As part of CEIP for [!INCLUDE[adaptersqlshort](../../includes/adaptersqlshort-md.md)], you will share the following data with Microsoft:</span></span>  
  
    -   <span data-ttu-id="ce42e-238">インストールしているコンピューターのハードウェア、[!INCLUDE[adaptersqlshort](../../includes/adaptersqlshort-md.md)]です。</span><span class="sxs-lookup"><span data-stu-id="ce42e-238">The computer hardware on which you are installing the [!INCLUDE[adaptersqlshort](../../includes/adaptersqlshort-md.md)].</span></span>  
  
    -   <span data-ttu-id="ce42e-239">使用して接続を使用している SQL Server のバージョン、[!INCLUDE[adaptersqlshort](../../includes/adaptersqlshort-md.md)]です。</span><span class="sxs-lookup"><span data-stu-id="ce42e-239">The SQL Server versions you are using to connect using the [!INCLUDE[adaptersqlshort](../../includes/adaptersqlshort-md.md)].</span></span>  
  
     <span data-ttu-id="ce42e-240">CEIP の登録には、するには、次のコマンドを実行します。</span><span class="sxs-lookup"><span data-stu-id="ce42e-240">To enroll for CEIP, run the following command:</span></span>  
  
    ```  
    msiexec /i SqlAdapterSetup.msi /qn CEIP_OPTIN=true  
    ```  
  
     <span data-ttu-id="ce42e-241">既定では、このオプションは false です。</span><span class="sxs-lookup"><span data-stu-id="ce42e-241">By default, the option is false.</span></span>  
  
     <span data-ttu-id="ce42e-242">詳細については、`msiexec`コマンドを入力`msiexec`キーを押して、コマンド ライン`ENTER`を参照してくださいまたは[https://support.microsoft.com/kb/230781](https://support.microsoft.com/kb/230781)です。</span><span class="sxs-lookup"><span data-stu-id="ce42e-242">For more information about the `msiexec` command, type `msiexec` on the command line and press `ENTER`, or see [https://support.microsoft.com/kb/230781](https://support.microsoft.com/kb/230781).</span></span>  
  
<a name="BKMK_PostInst"></a>   
## <a name="post-installation-tasks"></a><span data-ttu-id="ce42e-243">インストール後のタスク</span><span class="sxs-lookup"><span data-stu-id="ce42e-243">Post-installation tasks</span></span>  
  
<a name="BKMK_Register_Bindings"></a>   
#### <a name="register-the-bindings"></a><span data-ttu-id="ce42e-244">バインドを登録します。</span><span class="sxs-lookup"><span data-stu-id="ce42e-244">Register the bindings</span></span>  
<span data-ttu-id="ce42e-245">次の手順を完了*のみ*machine.config ファイルにアダプターのバインドを登録するセットアップ ウィザードが失敗した場合。</span><span class="sxs-lookup"><span data-stu-id="ce42e-245">Complete these steps *only* if the setup wizard fails to register the adapter bindings in the machine.config file.</span></span>  
  
1.  <span data-ttu-id="ce42e-246">コンピューター上の machine.config ファイルに移動します。</span><span class="sxs-lookup"><span data-stu-id="ce42e-246">Navigate to the machine.config file on the computer.</span></span> <span data-ttu-id="ce42e-247">たとえば、32 ビット プラットフォームで、machine.config は下にある使用可能な\<システム ドライブ\>: \WINDOWS\Microsoft.NET\Framework\\< バージョン\>\CONFIG です。</span><span class="sxs-lookup"><span data-stu-id="ce42e-247">For example, on a 32-bit platform, the machine.config is available under \<system drive\>:\WINDOWS\Microsoft.NET\Framework\\<version\>\CONFIG.</span></span>  
  
2.  <span data-ttu-id="ce42e-248">テキスト エディターを使用してファイルを開きます。</span><span class="sxs-lookup"><span data-stu-id="ce42e-248">Open the file using a text editor.</span></span>  
  
3.  <span data-ttu-id="ce42e-249">アダプターのバインドを登録します。</span><span class="sxs-lookup"><span data-stu-id="ce42e-249">To register the adapter bindings:</span></span>  
  
    1.  <span data-ttu-id="ce42e-250">要素"system.serviceModel"を検索し、その下にある、次を追加します。</span><span class="sxs-lookup"><span data-stu-id="ce42e-250">Search for the element "system.serviceModel" and add the following under it:</span></span>  
  
        ```  
        <client>  
          <endpoint binding="sqlBinding" contract="IMetadataExchange" name="mssql" />  
        </client>  
        ```  
  
    2.  <span data-ttu-id="ce42e-251">"BindingElementExtensions"system.serviceModel\extensions 下にある要素を検索します。</span><span class="sxs-lookup"><span data-stu-id="ce42e-251">Search for the element "bindingElementExtensions" under system.serviceModel\extensions.</span></span>  
  
    3.  <span data-ttu-id="ce42e-252">"BindingElementExtensions"ノードの下の次のセクションを追加します。</span><span class="sxs-lookup"><span data-stu-id="ce42e-252">Add the following section under the "bindingElementExtensions" node.</span></span>  
  
         <span data-ttu-id="ce42e-253">[!INCLUDE[adaptersqlshort](../../includes/adaptersqlshort-md.md)]を追加します。</span><span class="sxs-lookup"><span data-stu-id="ce42e-253">For the [!INCLUDE[adaptersqlshort](../../includes/adaptersqlshort-md.md)], add:</span></span>  
  
        ```  
        <add name="sqlAdapter" type="Microsoft.Adapters.Sql.SqlAdapterBindingElementExtensionElement,Microsoft.Adapters.Sql, Version=<version>, Culture=neutral, PublicKeyToken=<public key>" />  
        ```  
  
    4.  <span data-ttu-id="ce42e-254">"BindingExtensions"system.serviceModel\extensions 下にある要素を検索します。</span><span class="sxs-lookup"><span data-stu-id="ce42e-254">Search for the element "bindingExtensions" under system.serviceModel\extensions.</span></span>  
  
    5.  <span data-ttu-id="ce42e-255">"BindingExtensions"ノードの下の次のセクションを追加します。</span><span class="sxs-lookup"><span data-stu-id="ce42e-255">Add the following section under the "bindingExtensions" node.</span></span>  
  
         <span data-ttu-id="ce42e-256">[!INCLUDE[adaptersqlshort](../../includes/adaptersqlshort-md.md)]を追加します。</span><span class="sxs-lookup"><span data-stu-id="ce42e-256">For [!INCLUDE[adaptersqlshort](../../includes/adaptersqlshort-md.md)], add:</span></span>  
  
        ```  
        <add name="sqlBinding" type="Microsoft.Adapters.Sql.SqlAdapterBindingCollectionElement,Microsoft.Adapters.Sql, Version=<version>, Culture=neutral, PublicKeyToken=<public key>" />  
        ```  
  
    > [!NOTE]
    >  <span data-ttu-id="ce42e-257">公開キーを確認する方法については、次を参照してください。[公開キーとバージョンを決定する](#BKMK_PubKey)です。</span><span class="sxs-lookup"><span data-stu-id="ce42e-257">For information about how to determine the public key, see [Determining the Public Key and Version](#BKMK_PubKey).</span></span>  
  
4.  <span data-ttu-id="ce42e-258">machine.config ファイルを保存して閉じます。</span><span class="sxs-lookup"><span data-stu-id="ce42e-258">Save and close the machine.config file.</span></span>  
  
<a name="BKMK_PubKey"></a>   
#### <a name="determining-the-public-key-and-version"></a><span data-ttu-id="ce42e-259">公開キーとバージョンを決定します。</span><span class="sxs-lookup"><span data-stu-id="ce42e-259">Determining the Public Key and Version</span></span>  
<span data-ttu-id="ce42e-260">公開キーとバージョンを確認するのには、次の手順を完了、[!INCLUDE[adaptersqlshort](../../includes/adaptersqlshort-md.md)]です。</span><span class="sxs-lookup"><span data-stu-id="ce42e-260">Complete the following steps to determine the public key and version for the [!INCLUDE[adaptersqlshort](../../includes/adaptersqlshort-md.md)].</span></span>  
  
1.  <span data-ttu-id="ce42e-261">Windows ディレクトリの通常 C:\WINDOWS\assembly に移動します。</span><span class="sxs-lookup"><span data-stu-id="ce42e-261">Navigate to the Windows directory, typically C:\WINDOWS\assembly.</span></span>  
  
2.  <span data-ttu-id="ce42e-262">対象の公開キーを指定してを選択し、DLL を右クリックして**プロパティ**です。</span><span class="sxs-lookup"><span data-stu-id="ce42e-262">Right-click the DLL for which you want the public key, and then select **Properties**.</span></span> <span data-ttu-id="ce42e-263">次の表の Dll の名前、[!INCLUDE[adaptersqlshort](../../includes/adaptersqlshort-md.md)]です。</span><span class="sxs-lookup"><span data-stu-id="ce42e-263">The following table lists the name of the DLLs for the [!INCLUDE[adaptersqlshort](../../includes/adaptersqlshort-md.md)].</span></span>  
  
    |<span data-ttu-id="ce42e-264">[アダプター]</span><span class="sxs-lookup"><span data-stu-id="ce42e-264">Adapter</span></span>|<span data-ttu-id="ce42e-265">DLL の名前</span><span class="sxs-lookup"><span data-stu-id="ce42e-265">Name of the DLL</span></span>|  
    |---|---|  
    |[!INCLUDE[adaptersqlshort](../../includes/adaptersqlshort-md.md)]|<span data-ttu-id="ce42e-266">Microsoft.Adapters.Sql.dll</span><span class="sxs-lookup"><span data-stu-id="ce42e-266">Microsoft.Adapters.Sql.dll</span></span>|  
  
3.  <span data-ttu-id="ce42e-267">**全般** タブの値と比較、**公開キー トークンの**ラベルは、DLL の公開キーを指定します。</span><span class="sxs-lookup"><span data-stu-id="ce42e-267">On the **General** tab, the value against the **Public Key Token** label specifies the public key for the DLL.</span></span> <span data-ttu-id="ce42e-268">同様の値と比較、**バージョン**ラベルは、DLL のバージョン番号を指定します。</span><span class="sxs-lookup"><span data-stu-id="ce42e-268">Similarly, the value against the **Version** label specifies the version number for the DLL.</span></span>  
  
4.  <span data-ttu-id="ce42e-269">公開キーをコピーし、をクリックして**キャンセル**です。</span><span class="sxs-lookup"><span data-stu-id="ce42e-269">Copy the public key, and then click **Cancel**.</span></span>  
  
<a name="BKMK_Modify_Adap"></a>   
## <a name="update-or-change-the-sql-adapter-installation"></a><span data-ttu-id="ce42e-270">更新または変更する SQL アダプターのインストール</span><span class="sxs-lookup"><span data-stu-id="ce42e-270">Update or change the SQL adapter installation</span></span>  
 <span data-ttu-id="ce42e-271">変更するのには、次の手順を実行、[!INCLUDE[adaptersqlshort](../../includes/adaptersqlshort-md.md)]インストールします。</span><span class="sxs-lookup"><span data-stu-id="ce42e-271">Perform the following steps to modify the [!INCLUDE[adaptersqlshort](../../includes/adaptersqlshort-md.md)] installation.</span></span> <span data-ttu-id="ce42e-272">あるかどうかを確認、[!INCLUDE[adaptersqlshort](../../includes/adaptersqlshort-md.md)]を変更するセットアップ ウィザードを実行する前にインストールされている、[!INCLUDE[adaptersqlshort](../../includes/adaptersqlshort-md.md)]インストールします。</span><span class="sxs-lookup"><span data-stu-id="ce42e-272">Make sure you have the [!INCLUDE[adaptersqlshort](../../includes/adaptersqlshort-md.md)] installed before you run the setup wizard to modify the [!INCLUDE[adaptersqlshort](../../includes/adaptersqlshort-md.md)] installation.</span></span>  
  
 <span data-ttu-id="ce42e-273">変更することができます、[!INCLUDE[adaptersqlshort](../../includes/adaptersqlshort-md.md)]次の 2 つの方法でインストールします。</span><span class="sxs-lookup"><span data-stu-id="ce42e-273">You can modify the [!INCLUDE[adaptersqlshort](../../includes/adaptersqlshort-md.md)] installation in the following two ways:</span></span>  
  
-   <span data-ttu-id="ce42e-274">**対話モードで**セットアップ ウィザードを実行しています。</span><span class="sxs-lookup"><span data-stu-id="ce42e-274">**In interactive mode** by running the setup wizard.</span></span>  
  
-   <span data-ttu-id="ce42e-275">**サイレント モードで**コマンドラインを使用しています。</span><span class="sxs-lookup"><span data-stu-id="ce42e-275">**In silent mode** by using the command line.</span></span>  
  
#### <a name="update-the-sql-adapter-installation-in-interactive-mode"></a><span data-ttu-id="ce42e-276">対話モードで SQL アダプターのインストールを更新します。</span><span class="sxs-lookup"><span data-stu-id="ce42e-276">Update the SQL Adapter installation in interactive mode</span></span>  
  
1.  <span data-ttu-id="ce42e-277">をクリックして**開始**、順にクリック**コントロール パネルの** です。</span><span class="sxs-lookup"><span data-stu-id="ce42e-277">Click **Start**, and then click **Control Panel**.</span></span>  
  
2.  <span data-ttu-id="ce42e-278">コントロール パネルで、ダブルクリック**プログラムと機能**します。</span><span class="sxs-lookup"><span data-stu-id="ce42e-278">In Control Panel, double-click **Programs and Features**.</span></span>  
  
3.  <span data-ttu-id="ce42e-279">**プログラムと機能**ウィンドウで、 **Microsoft BizTalk Adapter for SQL Server**、クリックして**変更**です。</span><span class="sxs-lookup"><span data-stu-id="ce42e-279">In the **Programs and Features** window, select **Microsoft BizTalk Adapter for SQL Server**, and then click **Change**.</span></span>  
  
4.  <span data-ttu-id="ce42e-280">[ようこそ] 画面で、情報を参照し、をクリックして**次**です。</span><span class="sxs-lookup"><span data-stu-id="ce42e-280">Read the information on the Welcome screen, and then click **Next**.</span></span>  
  
5.  <span data-ttu-id="ce42e-281">**変更、修復、または削除インストール**ダイアログ ボックスで、をクリックして**修復**です。</span><span class="sxs-lookup"><span data-stu-id="ce42e-281">In the **Change, repair, or remove installation** dialog box, click **Repair**.</span></span>  
  
6.  <span data-ttu-id="ce42e-282">**SQL Server 用 Microsoft BizTalk Adapter を修復する準備が**ダイアログ ボックスで、をクリックして**修復**です。</span><span class="sxs-lookup"><span data-stu-id="ce42e-282">In the **Ready to repair Microsoft BizTalk Adapter for SQL Server** dialog box, click **Repair**.</span></span>  
  
7.  <span data-ttu-id="ce42e-283">必要に応じて、ユーザーの設定を変更に関して、CEIP を無効にして、をクリックして**OK**です。</span><span class="sxs-lookup"><span data-stu-id="ce42e-283">If required, change your preferences regarding opting for CEIP, and then click **OK**.</span></span>  
  
8.  <span data-ttu-id="ce42e-284">**[完了]** をクリックします。</span><span class="sxs-lookup"><span data-stu-id="ce42e-284">Click **Finish**.</span></span>  
  
#### <a name="update-the-sql-adapter-installation-in-silent-mode"></a><span data-ttu-id="ce42e-285">更新プログラムのサイレント モードで SQL アダプターのインストール</span><span class="sxs-lookup"><span data-stu-id="ce42e-285">Update the SQL Adapter installation in silent mode</span></span>  
  
1.  <span data-ttu-id="ce42e-286">コマンド プロンプトを開きのルート ディレクトリに移動、[!INCLUDE[adaptersqlshort](../../includes/adaptersqlshort-md.md)]インストーラーです。</span><span class="sxs-lookup"><span data-stu-id="ce42e-286">Open a command prompt, and navigate to the root directory of the [!INCLUDE[adaptersqlshort](../../includes/adaptersqlshort-md.md)] installer.</span></span>  
  
2.  <span data-ttu-id="ce42e-287">次のコマンドを実行します。</span><span class="sxs-lookup"><span data-stu-id="ce42e-287">Run the following command:</span></span>  
  
    > [!NOTE]
    >  <span data-ttu-id="ce42e-288">変更する、 [!INCLUDE[adaptersqlshort](../../includes/adaptersqlshort-md.md)] SqlAdapterSetup64.msi で次のコマンドでの x64 ベースのプラットフォームにサイレント モードでインストールが SqlAdapterSetup.msi を置き換えます。</span><span class="sxs-lookup"><span data-stu-id="ce42e-288">To modify the [!INCLUDE[adaptersqlshort](../../includes/adaptersqlshort-md.md)] installation in silent mode on an x64-based platform, in the following commands, replace SqlAdapterSetup.msi with SqlAdapterSetup64.msi.</span></span>  
  
    ```  
    msiexec /i SqlAdapterSetup.msi /qn /f  
    ```  
  
    > [!IMPORTANT]
    >  <span data-ttu-id="ce42e-289">変更中に、[!INCLUDE[adaptersqlshort](../../includes/adaptersqlshort-md.md)]サイレント モードでインストールで CEIP を有効または無効にするための設定を変更することはできません。</span><span class="sxs-lookup"><span data-stu-id="ce42e-289">While modifying the [!INCLUDE[adaptersqlshort](../../includes/adaptersqlshort-md.md)] installation in the silent mode, you cannot change your preferences for opting in or out of CEIP.</span></span> <span data-ttu-id="ce42e-290">環境設定は変わりません、インストール時に指定したとおり、CEIP_OPTIN を true または false に明示的に設定した場合でもです。</span><span class="sxs-lookup"><span data-stu-id="ce42e-290">The preferences will remain the same as you specified during the installation, even if you explicitly set the CEIP_OPTIN to true or false.</span></span>  
  
     <span data-ttu-id="ce42e-291">詳細については、`msiexec`コマンドの種類を`msiexec`キーを押して、コマンド ライン`ENTER`を参照してくださいまたは[https://support.microsoft.com/kb/230781](https://support.microsoft.com/kb/230781)です。</span><span class="sxs-lookup"><span data-stu-id="ce42e-291">For more information about the `msiexec` command type `msiexec` on the command line and press `ENTER`, or see [https://support.microsoft.com/kb/230781](https://support.microsoft.com/kb/230781).</span></span>  
  
<a name="BKMK_Remove_Adap"></a>   
## <a name="uninstall-or-remove-the-sql-adapter"></a><span data-ttu-id="ce42e-292">アンインストールするか、SQL アダプターを削除します。</span><span class="sxs-lookup"><span data-stu-id="ce42e-292">Uninstall or remove the SQL Adapter</span></span>  
 <span data-ttu-id="ce42e-293">削除するには、次の手順を実行、[!INCLUDE[adaptersqlshort](../../includes/adaptersqlshort-md.md)]コンピューターからです。</span><span class="sxs-lookup"><span data-stu-id="ce42e-293">Perform the following steps to remove the [!INCLUDE[adaptersqlshort](../../includes/adaptersqlshort-md.md)] from your computer.</span></span> <span data-ttu-id="ce42e-294">あるかどうかを確認、[!INCLUDE[afproductnameshort](../../includes/afproductnameshort-md.md)]を削除するセットアップ ウィザードを実行する前にインストールされている、[!INCLUDE[adaptersqlshort](../../includes/adaptersqlshort-md.md)]です。</span><span class="sxs-lookup"><span data-stu-id="ce42e-294">Make sure you have the [!INCLUDE[afproductnameshort](../../includes/afproductnameshort-md.md)] installed before you run the setup wizard to remove the [!INCLUDE[adaptersqlshort](../../includes/adaptersqlshort-md.md)].</span></span>  
  
 <span data-ttu-id="ce42e-295">削除することができます、[!INCLUDE[adaptersqlshort](../../includes/adaptersqlshort-md.md)]次の 2 つの方法で。</span><span class="sxs-lookup"><span data-stu-id="ce42e-295">You can remove the [!INCLUDE[adaptersqlshort](../../includes/adaptersqlshort-md.md)] in the following two ways:</span></span>  
  
-   <span data-ttu-id="ce42e-296">**対話モードで**セットアップ ウィザードを実行しています。</span><span class="sxs-lookup"><span data-stu-id="ce42e-296">**In interactive mode** by running the setup wizard.</span></span>  
  
-   <span data-ttu-id="ce42e-297">**サイレント モードで**コマンドラインを使用しています。</span><span class="sxs-lookup"><span data-stu-id="ce42e-297">**In silent mode** by using the command line.</span></span>  
  
#### <a name="uninstall-the-sql-adapter-in-interactive-mode"></a><span data-ttu-id="ce42e-298">対話モードで SQL アダプターをアンインストールします。</span><span class="sxs-lookup"><span data-stu-id="ce42e-298">Uninstall the SQL Adapter in interactive mode</span></span>  
  
1.  <span data-ttu-id="ce42e-299">をクリックして**開始**、順にクリック**コントロール パネルの** です。</span><span class="sxs-lookup"><span data-stu-id="ce42e-299">Click **Start**, and then click **Control Panel**.</span></span>  
  
2.  <span data-ttu-id="ce42e-300">コントロール パネルで、ダブルクリック**プログラムと機能**します。</span><span class="sxs-lookup"><span data-stu-id="ce42e-300">In Control Panel, double-click  **Programs and Features**.</span></span>  
  
3.  <span data-ttu-id="ce42e-301">**プログラム追加と削除**ウィンドウで、 **Microsoft BizTalk Adapter for SQL Server**、クリックして**削除**です。</span><span class="sxs-lookup"><span data-stu-id="ce42e-301">In the **Add or Remove Programs** window, select **Microsoft BizTalk Adapter for SQL Server**, and then click **Remove**.</span></span>  
  
4.  <span data-ttu-id="ce42e-302">ダイアログ ボックスで、**はい**です。</span><span class="sxs-lookup"><span data-stu-id="ce42e-302">In the dialog box, click **Yes**.</span></span>  
  
#### <a name="uninstall-the-sql-adapter-in-silent-mode"></a><span data-ttu-id="ce42e-303">サイレント モードで SQL アダプターをアンインストールします。</span><span class="sxs-lookup"><span data-stu-id="ce42e-303">Uninstall the SQL Adapter in silent mode</span></span>  
  
1.  <span data-ttu-id="ce42e-304">コマンド プロンプトを開きのルート ディレクトリに移動、[!INCLUDE[adaptersqlshort](../../includes/adaptersqlshort-md.md)]インストーラーです。</span><span class="sxs-lookup"><span data-stu-id="ce42e-304">Open a command prompt, and navigate to the root directory of the [!INCLUDE[adaptersqlshort](../../includes/adaptersqlshort-md.md)] installer.</span></span>  
  
2.  <span data-ttu-id="ce42e-305">次のコマンドを実行します。</span><span class="sxs-lookup"><span data-stu-id="ce42e-305">Run the following command:</span></span>  
  
    > [!NOTE]
    >  <span data-ttu-id="ce42e-306">削除する、[!INCLUDE[adaptersqlshort](../../includes/adaptersqlshort-md.md)]サイレント モードで、次のコマンドの x64 ベースのプラットフォーム上で SqlAdapterSetup64.msi で SqlAdapterSetup.msi を置き換えます。</span><span class="sxs-lookup"><span data-stu-id="ce42e-306">To remove the [!INCLUDE[adaptersqlshort](../../includes/adaptersqlshort-md.md)] in silent mode on an x64-based platform, in the following commands, replace SqlAdapterSetup.msi with SqlAdapterSetup64.msi.</span></span>  
  
    ```  
    msiexec /x SqlAdapterSetup.msi /qn  
    ```  
  
     <span data-ttu-id="ce42e-307">このコマンドを削除、[!INCLUDE[adaptersqlshort](../../includes/adaptersqlshort-md.md)]コンピューターからです。</span><span class="sxs-lookup"><span data-stu-id="ce42e-307">This command removes the [!INCLUDE[adaptersqlshort](../../includes/adaptersqlshort-md.md)] from the computer.</span></span>  
  
     <span data-ttu-id="ce42e-308">詳細については、`msiexec`コマンドを入力`msiexec`キーを押して、コマンド ライン`ENTER`を参照してくださいまたは[https://support.microsoft.com/kb/230781](https://support.microsoft.com/kb/230781)です。</span><span class="sxs-lookup"><span data-stu-id="ce42e-308">For more information about the `msiexec` command, type `msiexec` on the command line and press `ENTER`, or see [https://support.microsoft.com/kb/230781](https://support.microsoft.com/kb/230781).</span></span>  
  
<a name="BKMK_PostRemove"></a>   
### <a name="post-uninstall-task"></a><span data-ttu-id="ce42e-309">アンインストール後のタスク</span><span class="sxs-lookup"><span data-stu-id="ce42e-309">Post-uninstall task</span></span>  
 <span data-ttu-id="ce42e-310">場合、[!INCLUDE[adaptersqlshort](../../includes/adaptersqlshort-md.md)]バインドを削除する、アダプターの削除中にセットアップが失敗した、 [!INCLUDE[adaptersqlshort](../../includes/adaptersqlshort-md.md)]、それらを手動で削除する必要があります。</span><span class="sxs-lookup"><span data-stu-id="ce42e-310">If the [!INCLUDE[adaptersqlshort](../../includes/adaptersqlshort-md.md)] setup fails to remove the adapter bindings while removing the [!INCLUDE[adaptersqlshort](../../includes/adaptersqlshort-md.md)], you must remove them manually.</span></span> <span data-ttu-id="ce42e-311">次のセクションのバインドを手動で削除する方法について説明、[!INCLUDE[adaptersqlshort](../../includes/adaptersqlshort-md.md)]です。</span><span class="sxs-lookup"><span data-stu-id="ce42e-311">The following section describes how to manually remove the bindings for the [!INCLUDE[adaptersqlshort](../../includes/adaptersqlshort-md.md)].</span></span>  
  
<span data-ttu-id="ce42e-312">次の手順を完了*のみ*バインドを削除する、アダプター、machine.config ファイルから、セットアップ ウィザードが失敗した場合。</span><span class="sxs-lookup"><span data-stu-id="ce42e-312">Complete these steps *only* if the setup wizard fails to remove the adapter bindings from the machine.config file.</span></span>  
  
1.  <span data-ttu-id="ce42e-313">コンピューター上の machine.config ファイルに移動します。</span><span class="sxs-lookup"><span data-stu-id="ce42e-313">Navigate to the machine.config file on the computer.</span></span> <span data-ttu-id="ce42e-314">たとえば、32 ビット プラットフォームで、machine.config は下にある使用可能な\<システム ドライブ\>: \WINDOWS\Microsoft.NET\Framework\\< バージョン\>\CONFIG です。</span><span class="sxs-lookup"><span data-stu-id="ce42e-314">For example, on a 32-bit platform, the machine.config is available under \<system drive\>:\WINDOWS\Microsoft.NET\Framework\\<version\>\CONFIG.</span></span>  
  
    -   <span data-ttu-id="ce42e-315">Microsoft .NET framework 3.5 SP1、 \<*バージョン*\> .NET Framework のバージョン v2.0.50727 がします。</span><span class="sxs-lookup"><span data-stu-id="ce42e-315">For Microsoft .NET Framework 3.5 SP1, \<*version*\> is the version v2.0.50727 of the .NET Framework.</span></span>  
  
    -   <span data-ttu-id="ce42e-316">Microsoft の[!INCLUDE[netfx40_short](../../includes/netfx40-short-md.md)]、 \<*バージョン*\>は、.NET Framework のバージョン v4.0.30319 します。</span><span class="sxs-lookup"><span data-stu-id="ce42e-316">For Microsoft [!INCLUDE[netfx40_short](../../includes/netfx40-short-md.md)], \<*version*\> is the version v4.0.30319 of the .NET Framework.</span></span>  
  
2.  <span data-ttu-id="ce42e-317">テキスト エディターを使用してファイルを開きます。</span><span class="sxs-lookup"><span data-stu-id="ce42e-317">Open the file using a text editor.</span></span>  
  
3.  <span data-ttu-id="ce42e-318">アダプターのバインドの登録を削除します。</span><span class="sxs-lookup"><span data-stu-id="ce42e-318">To remove the adapter binding registration:</span></span>  
  
    1.  <span data-ttu-id="ce42e-319">要素"system.serviceModel"を検索し、次の要素の下を削除します。</span><span class="sxs-lookup"><span data-stu-id="ce42e-319">Search for the element "system.serviceModel" and remove the following from under the element:</span></span>  
  
        ```  
        <client>  
          <endpoint binding="sqlBinding" contract="IMetadataExchange" name="mssql" />  
        </client>  
  
        ```  
  
    2.  <span data-ttu-id="ce42e-320">"BindingElementExtensions"system.serviceModel\extensions 下にある要素を検索します。</span><span class="sxs-lookup"><span data-stu-id="ce42e-320">Search for the element "bindingElementExtensions" under system.serviceModel\extensions.</span></span>  
  
    3.  <span data-ttu-id="ce42e-321">"BindingElementExtensions"ノードの下に、次のセクションを削除します。</span><span class="sxs-lookup"><span data-stu-id="ce42e-321">Remove the following section under the "bindingElementExtensions" node.</span></span>  
  
         <span data-ttu-id="ce42e-322">[!INCLUDE[adaptersqlshort](../../includes/adaptersqlshort-md.md)]、削除します。</span><span class="sxs-lookup"><span data-stu-id="ce42e-322">For [!INCLUDE[adaptersqlshort](../../includes/adaptersqlshort-md.md)], remove:</span></span>  
  
        ```  
        <add name="sqlAdapter" type="Microsoft.Adapters.Sql.SqlAdapterBindingElementExtensionElement,Microsoft.Adapters.Sql, Version=<version>, Culture=neutral, PublicKeyToken=<public key>" />  
        ```  
  
    4.  <span data-ttu-id="ce42e-323">"BindingExtensions"system.serviceModel\extensions 下にある要素を検索します。</span><span class="sxs-lookup"><span data-stu-id="ce42e-323">Search for the element "bindingExtensions" under system.serviceModel\extensions.</span></span>  
  
    5.  <span data-ttu-id="ce42e-324">"BindingExtensions"ノードの下に、次のセクションを削除します。</span><span class="sxs-lookup"><span data-stu-id="ce42e-324">Remove the following section under the "bindingExtensions" node.</span></span>  
  
         <span data-ttu-id="ce42e-325">[!INCLUDE[adaptersqlshort](../../includes/adaptersqlshort-md.md)]、削除します。</span><span class="sxs-lookup"><span data-stu-id="ce42e-325">For [!INCLUDE[adaptersqlshort](../../includes/adaptersqlshort-md.md)], remove:</span></span>  
  
        ```  
        <add name="sqlBinding" type="Microsoft.Adapters.Sql.SqlAdapterBindingCollectionElement,Microsoft.Adapters.Sql, Version=<version>, Culture=neutral, PublicKeyToken=<public key>" />  
        ```  
  
4.  <span data-ttu-id="ce42e-326">machine.config ファイルを保存して閉じます。</span><span class="sxs-lookup"><span data-stu-id="ce42e-326">Save and close the machine.config file.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="ce42e-327">参照</span><span class="sxs-lookup"><span data-stu-id="ce42e-327">See also</span></span>
[<span data-ttu-id="ce42e-328">SQL アダプターをインストールする</span><span class="sxs-lookup"><span data-stu-id="ce42e-328">Install the SQL adapter</span></span>](../../adapters-and-accelerators/adapter-sql/install-the-sql-adapter.md)  
[<span data-ttu-id="ce42e-329">BizTalk Adapter for SQL Server を理解する</span><span class="sxs-lookup"><span data-stu-id="ce42e-329">Understand BizTalk Adapter for SQL Server</span></span>](../../adapters-and-accelerators/adapter-sql/understand-biztalk-adapter-for-sql-server.md)