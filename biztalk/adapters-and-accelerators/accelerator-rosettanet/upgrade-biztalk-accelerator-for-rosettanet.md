---
title: BizTalk Server では、RosettaNet アクセラレータ (BTARN) のアップグレード |Microsoft Docs"
description: BTARN を BizTalk Server では、現在のバージョンに更新するアップグレードの手順に従います
author: MandiOhlinger
manager: anneta
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.suite: ''
ms.tgt_pltfrm: ''
ms.topic: article
ms.assetid: ''
ms.author: mandia
ms.openlocfilehash: 6149a1afd765aa2b030394ec15b73c7dd6072231
ms.sourcegitcommit: 381e83d43796a345488d54b3f7413e11d56ad7be
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 05/07/2019
ms.locfileid: "65300001"
---
# <a name="upgrade-the-rosettanet-accelerator"></a><span data-ttu-id="27e86-103">RosettaNet アクセラレータをアップグレードします。</span><span class="sxs-lookup"><span data-stu-id="27e86-103">Upgrade the RosettaNet accelerator</span></span>

## <a name="upgrade-overview"></a><span data-ttu-id="27e86-104">アップグレードの概要</span><span class="sxs-lookup"><span data-stu-id="27e86-104">Upgrade overview</span></span>
<span data-ttu-id="27e86-105">BizTalk Accelerator for RosettaNet (BTARN) のインストールの以前のバージョンは、現在のバージョンにアップグレードできます。</span><span class="sxs-lookup"><span data-stu-id="27e86-105">You can upgrade the previous version of the BizTalk Accelerator for RosettaNet (BTARN) installation to the current version.</span></span> <span data-ttu-id="27e86-106">アップグレード プロセスには、BizTalk Server をアップグレードして、BTARN のアップグレードが含まれます。</span><span class="sxs-lookup"><span data-stu-id="27e86-106">The upgrade process involves upgrading BizTalk Server, and then upgrading BTARN.</span></span>  
  
 <span data-ttu-id="27e86-107">BTARN の以前のバージョンからアップグレードすることができます、BTARN のインストール プログラムを実行しています。</span><span class="sxs-lookup"><span data-stu-id="27e86-107">You can upgrade from the previous version of BTARN to a by running the BTARN installation program.</span></span> <span data-ttu-id="27e86-108">セットアップでは、BTRAN の構成情報を現在のバージョンに移行します。</span><span class="sxs-lookup"><span data-stu-id="27e86-108">The setup migrates the BTRAN configuration information to the current version.</span></span>  
  
 <span data-ttu-id="27e86-109">BTARN マルチ サーバー環境では、してから BTARN には、すべての BizTalk Server をアップグレードする必要があります。</span><span class="sxs-lookup"><span data-stu-id="27e86-109">In a multi-server BTARN environment, you should upgrade all BizTalk Servers first, and then to BTARN.</span></span> <span data-ttu-id="27e86-110">次の順序で、サーバーを移行するには。</span><span class="sxs-lookup"><span data-stu-id="27e86-110">Migrate your servers in the following order:</span></span>  
  
- <span data-ttu-id="27e86-111">BizTalk グループをホストするサーバー</span><span class="sxs-lookup"><span data-stu-id="27e86-111">The server hosting the BizTalk Group</span></span>  
  
- <span data-ttu-id="27e86-112">各処理ノード</span><span class="sxs-lookup"><span data-stu-id="27e86-112">Each processing node</span></span>  
  
- <span data-ttu-id="27e86-113">BAM ポータル サーバー</span><span class="sxs-lookup"><span data-stu-id="27e86-113">The BAM portal server</span></span>  
  
  <span data-ttu-id="27e86-114">BTARN では、アップグレード プロセスで、次のことを確認します。</span><span class="sxs-lookup"><span data-stu-id="27e86-114">In the BTARN upgrade process, ensure you do the following:</span></span>  
  
- <span data-ttu-id="27e86-115">SQL Server (MSSQLSERVER) サービスが実行されていることを確認します。</span><span class="sxs-lookup"><span data-stu-id="27e86-115">Check if the SQL Server (MSSQLSERVER) service is running.</span></span>  
  
- <span data-ttu-id="27e86-116">サイレント インストールは実行されません。</span><span class="sxs-lookup"><span data-stu-id="27e86-116">Do not run a silent installation.</span></span>  
  
## <a name="upgrade-steps"></a><span data-ttu-id="27e86-117">アップグレード手順</span><span class="sxs-lookup"><span data-stu-id="27e86-117">Upgrade steps</span></span>  
  
1.  <span data-ttu-id="27e86-118">BizTalk Server をアップグレードします。</span><span class="sxs-lookup"><span data-stu-id="27e86-118">Upgrade BizTalk Server.</span></span> <span data-ttu-id="27e86-119">参照してください[BizTalk Server 新機能については、インストール、構成、およびアップグレード](../../install-and-config-guides/biztalk-server-what-s-new-installation-configuration-and-upgrade.md)します。</span><span class="sxs-lookup"><span data-stu-id="27e86-119">See [BizTalk Server What's New, Installation, Configuration, and Upgrade](../../install-and-config-guides/biztalk-server-what-s-new-installation-configuration-and-upgrade.md).</span></span>
  
2.  <span data-ttu-id="27e86-120">BTARN データベースとメッセージ スキーマを BTARN をバックアップします。</span><span class="sxs-lookup"><span data-stu-id="27e86-120">Back up the BTARN database and BTARN message schemas.</span></span>  
  
    > [!NOTE]
    >  <span data-ttu-id="27e86-121">安全上の理由から BTARN データベースをバックアップする必要があります。</span><span class="sxs-lookup"><span data-stu-id="27e86-121">You should back up the BTARN database for safety reasons.</span></span> <span data-ttu-id="27e86-122">インストール プログラムは、BTRAN データベースを新しいバージョンに移行します。</span><span class="sxs-lookup"><span data-stu-id="27e86-122">The installation program migrates the BTRAN database to the newer version.</span></span>  
  
3.  <span data-ttu-id="27e86-123">すべてのファイルをバックアップ、 *< ドライブ\>*: \Program Files\\Microsoft BizTalk Accelerator の RosettaNet フォルダーに対して行ったが、変更、ファイルなど、sdk。</span><span class="sxs-lookup"><span data-stu-id="27e86-123">Back up any files under the *<drive\>*:\Program Files\\Microsoft BizTalk Accelerator for RosettaNet folder that you have made changes to, for example, files in the SDK.</span></span>  
  
4.  <span data-ttu-id="27e86-124">該当するプロジェクトまたは 1 つ以上の BTARN アセンブリの以前のバージョンへの参照を持つアセンブリを展開解除します。</span><span class="sxs-lookup"><span data-stu-id="27e86-124">Undeploy any projects or assemblies that have references to one or more of the previous versions of BTARN assemblies.</span></span>  
  
5.  <span data-ttu-id="27e86-125">Visual Studio で、次の順序で、すべての BTARN アセンブリを手動で解除します。</span><span class="sxs-lookup"><span data-stu-id="27e86-125">In Visual Studio, manually undeploy all BTARN assemblies, in the following order:</span></span>  
  
    -   <span data-ttu-id="27e86-126">Microsoft.Solutions.BTARN.CommonTypes</span><span class="sxs-lookup"><span data-stu-id="27e86-126">Microsoft.Solutions.BTARN.CommonTypes</span></span>  
  
    -   <span data-ttu-id="27e86-127">Microsoft.Solutions.BTARN.GlobalSchemas</span><span class="sxs-lookup"><span data-stu-id="27e86-127">Microsoft.Solutions.BTARN.GlobalSchemas</span></span>  
  
    -   <span data-ttu-id="27e86-128">Microsoft.Solutions.BTARN.PipelineReceive</span><span class="sxs-lookup"><span data-stu-id="27e86-128">Microsoft.Solutions.BTARN.PipelineReceive</span></span>  
  
    -   <span data-ttu-id="27e86-129">Microsoft.Solutions.BTARN.PipelineSend</span><span class="sxs-lookup"><span data-stu-id="27e86-129">Microsoft.Solutions.BTARN.PipelineSend</span></span>  
  
    -   <span data-ttu-id="27e86-130">Microsoft.Solutions.BTARN.PrivateInitiator</span><span class="sxs-lookup"><span data-stu-id="27e86-130">Microsoft.Solutions.BTARN.PrivateInitiator</span></span>  
  
    -   <span data-ttu-id="27e86-131">Microsoft.Solutions.BTARN.PrivateResponder</span><span class="sxs-lookup"><span data-stu-id="27e86-131">Microsoft.Solutions.BTARN.PrivateResponder</span></span>  
  
    -   <span data-ttu-id="27e86-132">Microsoft.Solutions.BTARN.PublicInitiator</span><span class="sxs-lookup"><span data-stu-id="27e86-132">Microsoft.Solutions.BTARN.PublicInitiator</span></span>  
  
    -   <span data-ttu-id="27e86-133">Microsoft.Solutions.BTARN.PublicResponder</span><span class="sxs-lookup"><span data-stu-id="27e86-133">Microsoft.Solutions.BTARN.PublicResponder</span></span>  
  
    -   <span data-ttu-id="27e86-134">Microsoft.Solutions.BTARN.Schemas.RNIFv11</span><span class="sxs-lookup"><span data-stu-id="27e86-134">Microsoft.Solutions.BTARN.Schemas.RNIFv11</span></span>  
  
    -   <span data-ttu-id="27e86-135">Microsoft.Solutions.BTARN.Schemas.RNIFv20</span><span class="sxs-lookup"><span data-stu-id="27e86-135">Microsoft.Solutions.BTARN.Schemas.RNIFv20</span></span>  
  
    -   <span data-ttu-id="27e86-136">[Microsoft.solutions.btarn.schemas.rnpips]</span><span class="sxs-lookup"><span data-stu-id="27e86-136">Microsoft.Solutions.BTARN.Schemas.RNPIPs</span></span>  
  
6.  <span data-ttu-id="27e86-137">BTARN のインストールを実行します。</span><span class="sxs-lookup"><span data-stu-id="27e86-137">Run the BTARN installation.</span></span> <span data-ttu-id="27e86-138">参照してください[インストール RosettaNet アクセラレータの構成と](install-configure-biztalk-accelerator-for-rosettanet.md)します。</span><span class="sxs-lookup"><span data-stu-id="27e86-138">See [Install and configure the RosettaNet accelerator](install-configure-biztalk-accelerator-for-rosettanet.md).</span></span>
  
7.  <span data-ttu-id="27e86-139">使用**BTSTask.exe** (\Program Files\Microsoft BizTalk Server) を次の順序で BTARN アセンブリを手動で再デプロイします。</span><span class="sxs-lookup"><span data-stu-id="27e86-139">Use **BTSTask.exe** (\Program Files\Microsoft BizTalk Server) to manually redeploy the BTARN assemblies in the following order:</span></span>  
  
    -   <span data-ttu-id="27e86-140">Microsoft.Solutions.BTARN.CommonTypes</span><span class="sxs-lookup"><span data-stu-id="27e86-140">Microsoft.Solutions.BTARN.CommonTypes</span></span>  
  
    -   <span data-ttu-id="27e86-141">Microsoft.Solutions.BTARN.GlobalSchemas</span><span class="sxs-lookup"><span data-stu-id="27e86-141">Microsoft.Solutions.BTARN.GlobalSchemas</span></span>  
  
    -   <span data-ttu-id="27e86-142">Microsoft.Solutions.BTARN.PipelineReceive</span><span class="sxs-lookup"><span data-stu-id="27e86-142">Microsoft.Solutions.BTARN.PipelineReceive</span></span>  
  
    -   <span data-ttu-id="27e86-143">Microsoft.Solutions.BTARN.PipelineSend</span><span class="sxs-lookup"><span data-stu-id="27e86-143">Microsoft.Solutions.BTARN.PipelineSend</span></span>  
  
    -   <span data-ttu-id="27e86-144">Microsoft.Solutions.BTARN.PrivateInitiator</span><span class="sxs-lookup"><span data-stu-id="27e86-144">Microsoft.Solutions.BTARN.PrivateInitiator</span></span>  
  
    -   <span data-ttu-id="27e86-145">Microsoft.Solutions.BTARN.PrivateResponder</span><span class="sxs-lookup"><span data-stu-id="27e86-145">Microsoft.Solutions.BTARN.PrivateResponder</span></span>  
  
    -   <span data-ttu-id="27e86-146">Microsoft.Solutions.BTARN.PublicInitiator</span><span class="sxs-lookup"><span data-stu-id="27e86-146">Microsoft.Solutions.BTARN.PublicInitiator</span></span>  
  
    -   <span data-ttu-id="27e86-147">Microsoft.Solutions.BTARN.PublicResponder</span><span class="sxs-lookup"><span data-stu-id="27e86-147">Microsoft.Solutions.BTARN.PublicResponder</span></span>  
  
    -   <span data-ttu-id="27e86-148">Microsoft.Solutions.BTARN.Schemas.RNIFv11</span><span class="sxs-lookup"><span data-stu-id="27e86-148">Microsoft.Solutions.BTARN.Schemas.RNIFv11</span></span>  
  
    -   <span data-ttu-id="27e86-149">Microsoft.Solutions.BTARN.Schemas.RNIFv20</span><span class="sxs-lookup"><span data-stu-id="27e86-149">Microsoft.Solutions.BTARN.Schemas.RNIFv20</span></span>  
  
    -   <span data-ttu-id="27e86-150">[Microsoft.solutions.btarn.schemas.rnpips]</span><span class="sxs-lookup"><span data-stu-id="27e86-150">Microsoft.Solutions.BTARN.Schemas.RNPIPs</span></span>  
  
    > [!NOTE]
    >  <span data-ttu-id="27e86-151">詳細については**BTSTask.exe**、BizTalk Server ヘルプの「BTSTask コマンドライン リファレンス」を参照してください。</span><span class="sxs-lookup"><span data-stu-id="27e86-151">For more information about **BTSTask.exe**, see the "BTSTask Command-line Reference" topic in BizTalk Server Help.</span></span>  
  
8.  <span data-ttu-id="27e86-152">該当するプロジェクトまたは 1 つまたは複数の [BTARN アセンブリへの参照を持つアセンブリを再構築します。</span><span class="sxs-lookup"><span data-stu-id="27e86-152">Rebuild any projects or assemblies that have a reference to one or more of the [BTARN assemblies.</span></span> <span data-ttu-id="27e86-153">使用**BTSTask.exe**を手動でこれらのプロジェクトを再デプロイします。</span><span class="sxs-lookup"><span data-stu-id="27e86-153">Use **BTSTask.exe** to manually redeploy these projects.</span></span>  
  
9. <span data-ttu-id="27e86-154">次のような IIS で仮想フォルダーを ASP.NET 2.0 から ASP.NET 4.0 をアップグレードします。</span><span class="sxs-lookup"><span data-stu-id="27e86-154">Upgrade the virtual folders in IIS from ASP.NET 2.0 to ASP.NET 4.0 for the following:</span></span>  
  
    -   <span data-ttu-id="27e86-155">BTARNApp</span><span class="sxs-lookup"><span data-stu-id="27e86-155">BTARNApp</span></span>  
  
    -   <span data-ttu-id="27e86-156">BTARNHttpReceive</span><span class="sxs-lookup"><span data-stu-id="27e86-156">BTARNHttpReceive</span></span>  
  
10. <span data-ttu-id="27e86-157">すべての変更を適用するには、コンピューターを再起動します。</span><span class="sxs-lookup"><span data-stu-id="27e86-157">Restart the computer to apply any modifications done.</span></span>  
  
