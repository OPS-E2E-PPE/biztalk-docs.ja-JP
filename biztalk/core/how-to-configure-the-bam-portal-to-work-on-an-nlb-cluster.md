---
title: NLB クラスターで機能する BAM ポータルを構成する方法 |Microsoft Docs
ms.custom: ''
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: ''
ms.suite: ''
ms.tgt_pltfrm: ''
ms.topic: article
ms.assetid: 96c04fde-dc12-42fb-9193-aa74819fe880
caps.latest.revision: 22
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: f0273433cf06fd0c455d6ed5a0be05198a149b4c
ms.sourcegitcommit: 381e83d43796a345488d54b3f7413e11d56ad7be
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 05/07/2019
ms.locfileid: "65386173"
---
# <a name="how-to-configure-the-bam-portal-to-work-on-an-nlb-cluster"></a><span data-ttu-id="e71af-102">NLB クラスターで機能する BAM ポータルを構成する方法</span><span class="sxs-lookup"><span data-stu-id="e71af-102">How to Configure the BAM Portal to Work on an NLB Cluster</span></span>
<span data-ttu-id="e71af-103">ネットワーク負荷分散 (NLB) クラスターで機能する BAM ポータルを構成できます。</span><span class="sxs-lookup"><span data-stu-id="e71af-103">The BAM portal can be configured to work in a network load balancing (NLB) cluster.</span></span>  
  
> [!IMPORTANT]
>  <span data-ttu-id="e71af-104">BAM ポータル*のみ*は 32 ビット モードで実行されます。</span><span class="sxs-lookup"><span data-stu-id="e71af-104">BAM Portal *only* runs in 32-bit mode.</span></span> <span data-ttu-id="e71af-105">64 ビット コンピューターで IIS がインストールされている場合、ASP.NET 2.0 が 32 ビット モードで有効になっているを確認します。</span><span class="sxs-lookup"><span data-stu-id="e71af-105">If IIS is installed on a 64-bit machine, then confirm ASP.NET 2.0 is enabled in 32-bit mode.</span></span> <span data-ttu-id="e71af-106">これを行うには、IIS マネージャーを開き開く**アプリケーション プール**アプリケーション プール (BAMAppPool) を選択し、クリックして**詳細設定**します。</span><span class="sxs-lookup"><span data-stu-id="e71af-106">To do this, open IIS Manager, open **Application Pool**, select the application pool (BAMAppPool), and then click **Advanced Settings**.</span></span> <span data-ttu-id="e71af-107">**[32 ビット アプリケーションの有効化]** で、**[True]** を選択します。</span><span class="sxs-lookup"><span data-stu-id="e71af-107">In **Enable 32-bit applications**, select **True**.</span></span>  
>   
>  <span data-ttu-id="e71af-108">BAM ポータルの追加の要件を参照してください。 [BAM ポータルの計画](../core/planning-for-the-bam-portal.md)します。</span><span class="sxs-lookup"><span data-stu-id="e71af-108">For additional BAM Portal requirements, see [Planning for the BAM Portal](../core/planning-for-the-bam-portal.md).</span></span>  
  
### <a name="to-prepare-to-configure-bam-portal-on-an-nlb-cluster"></a><span data-ttu-id="e71af-109">NLB クラスターで BAM ポータルを構成する準備を行う</span><span class="sxs-lookup"><span data-stu-id="e71af-109">To prepare to configure BAM portal on an NLB cluster</span></span>  
  
1.  <span data-ttu-id="e71af-110">インストールし、最初のコンピューターで、ポータルを構成します。</span><span class="sxs-lookup"><span data-stu-id="e71af-110">Install and configure the portal on the first computer.</span></span>  
  
    > [!NOTE]
    >  <span data-ttu-id="e71af-111">最初のコンピューターでポータルを構成するだけです。</span><span class="sxs-lookup"><span data-stu-id="e71af-111">You only configure the portal on the first computer.</span></span> <span data-ttu-id="e71af-112">クラスター内の他のコンピューターで BAM ポータルを有効にするオプションがありますが、構成は、最初のコンピューターでのみ行われます。</span><span class="sxs-lookup"><span data-stu-id="e71af-112">You have the option of enabling the BAM portal on other the other computers in the cluster, but the configuration is done only on the first computer.</span></span>  
  
2.  <span data-ttu-id="e71af-113">NLB クラスターに含まれるすべてのコンピューターにポータル コンポーネントをインストールし、ポータルが構成されているコンピューターの BizTalk グループにクラスター内の他のコンピューターを参加します。</span><span class="sxs-lookup"><span data-stu-id="e71af-113">Install the portal components on all the computers to be included in the NLB cluster, and then join the other computers in the cluster to the BizTalk group of the computer on which the portal is configured.</span></span> <span data-ttu-id="e71af-114">BizTalk グループを有効にし、適切なグループに参加する必要があります。</span><span class="sxs-lookup"><span data-stu-id="e71af-114">You must enable the BizTalk groups and join the appropriate group.</span></span>  
  
3.  <span data-ttu-id="e71af-115">ポータルがインストールされているコンピューター用に構成された BizTalk 管理データベースを選択します。</span><span class="sxs-lookup"><span data-stu-id="e71af-115">Select the BizTalk Management database configured for the computer on which the portal is installed.</span></span>  
  
4.  <span data-ttu-id="e71af-116">NLB クラスターを作成します。</span><span class="sxs-lookup"><span data-stu-id="e71af-116">Create the NLB cluster.</span></span> <span data-ttu-id="e71af-117">作成して、ネットワーク負荷分散クラスターを管理する方法の詳細についてを参照してください「を作成および管理ネットワーク負荷分散クラスターの」 [ http://go.microsoft.com/fwlink/?LinkId=56206](http://go.microsoft.com/fwlink/?LinkId=56206)します。</span><span class="sxs-lookup"><span data-stu-id="e71af-117">For more information about how to create and manage network load balancing clusters, see "Create and Manage Network Load Balancing Clusters" at [http://go.microsoft.com/fwlink/?LinkId=56206](http://go.microsoft.com/fwlink/?LinkId=56206).</span></span>  
  
    > [!NOTE]
    >  <span data-ttu-id="e71af-118">NLB クラスターが正しく動作する BizTalk Server のコンテキスト外で続行する前に確認してください。</span><span class="sxs-lookup"><span data-stu-id="e71af-118">You should confirm that your NLB cluster is working properly outside of the BizTalk Server context before continuing.</span></span>  
  
    > [!NOTE]
    >  <span data-ttu-id="e71af-119">ハードウェア ベースの NLB を設定するには、ハードウェア プロバイダーのドキュメントを参照してください。</span><span class="sxs-lookup"><span data-stu-id="e71af-119">To set up hardware-based NLB, refer to your hardware provider's documentation.</span></span>  
  
### <a name="to-update-the-bam-configuration-to-reflect-the-location-of-the-cluster"></a><span data-ttu-id="e71af-120">クラスターの場所を反映するように BAM 構成を更新するには</span><span class="sxs-lookup"><span data-stu-id="e71af-120">To update the BAM configuration to reflect the location of the cluster</span></span>  
  
1. <span data-ttu-id="e71af-121">現在の BAM 構成を取得するのにには、BAM 管理ユーティリティを使用します。</span><span class="sxs-lookup"><span data-stu-id="e71af-121">Use the BAM Management Utility to get the current BAM configuration.</span></span> <span data-ttu-id="e71af-122">これを行うには、次のようにクリックします。**開始**、 をクリック**実行**、および種類[!INCLUDE[btsBiztalkServerPath](../includes/btsbiztalkserverpath-md.md)]の config の取得 \bm--filename:myconfig.xml します。</span><span class="sxs-lookup"><span data-stu-id="e71af-122">To do this, click **Start**, click **Run**, and type [!INCLUDE[btsBiztalkServerPath](../includes/btsbiztalkserverpath-md.md)]Tracking\bm get-config -FileName:MyConfig.xml.</span></span>  
  
2. <span data-ttu-id="e71af-123">ローカル ホスト名を NLB クラスターの名前に置き換えます。</span><span class="sxs-lookup"><span data-stu-id="e71af-123">Replace the local host name with the name of the NLB cluster.</span></span> <span data-ttu-id="e71af-124">これを行うには、次のようにクリックします。**開始**、 をクリック**実行**、および「notepad [!INCLUDE[btsBiztalkServerPath](../includes/btsbiztalkserverpath-md.md)]Tracking\MyConfig.xml します。</span><span class="sxs-lookup"><span data-stu-id="e71af-124">To do this, click **Start**, click **Run**, and type notepad [!INCLUDE[btsBiztalkServerPath](../includes/btsbiztalkserverpath-md.md)]Tracking\MyConfig.xml.</span></span>  
  
3. <span data-ttu-id="e71af-125">ハードウェア ベースの NLB のみの場合は、構成ファイルは、次を確認します。</span><span class="sxs-lookup"><span data-stu-id="e71af-125">For hardware-based NLB only, verify the configuration file has the following:</span></span>  
  
   ```  
   <GlobalProperty Name="BAMVRoot">  
   http://<NLB IP Address>:portname/BAM</GlobalProperty>  
   ```  
  
   > [!NOTE]
   >  <span data-ttu-id="e71af-126">ハードウェア ベースの NLB で BAM 構成を更新するときに、手順 4. と 5. は必要ありません。</span><span class="sxs-lookup"><span data-stu-id="e71af-126">Steps 4 and 5 are not necessary when updating the BAM configuration on hardware-based NLB.</span></span>  
  
4. <span data-ttu-id="e71af-127">コンピューター名 (machinename) をクラスター名に置き換えることにより、NLB クラスターを指す次の行を変更します。</span><span class="sxs-lookup"><span data-stu-id="e71af-127">Modify the following line to point to the NLB cluster by replacing the computer name (machinename) with the cluster name:</span></span>  
  
   ```  
   <GlobalProperty Name=" BAMVRoot">  http://machinename:portname/BAM  
   </GlobalProperty>   
   ```  
  
5. <span data-ttu-id="e71af-128">新しい構成を保存します。</span><span class="sxs-lookup"><span data-stu-id="e71af-128">Save the new configuration.</span></span> <span data-ttu-id="e71af-129">これを行うには、次のようにクリックします。**開始**、 をクリック**実行**、および種類[!INCLUDE[btsBiztalkServerPath](../includes/btsbiztalkserverpath-md.md)]\bm 更新-config--filename:myconfig.xml。</span><span class="sxs-lookup"><span data-stu-id="e71af-129">To do this, click **Start**, click **Run**, and type [!INCLUDE[btsBiztalkServerPath](../includes/btsbiztalkserverpath-md.md)]Tracking\bm update-config -FileName:MyConfig.xml.</span></span>  
  
### <a name="to-edit-the-bam-portal-webconfig-file-to-change-the-bammanagementservice-and-queryservice-urls-to-point-to-the-nlb-server-name-note-this-procedure-is-not-necessary-for-hardware-based-nlb"></a><span data-ttu-id="e71af-130">NLB サーバー名を指すように BAMmanagementService および QueryService の Url を変更する BAM ポータルの web.config ファイルを編集します。</span><span class="sxs-lookup"><span data-stu-id="e71af-130">To edit the BAM portal web.config file to change the BAMmanagementService and QueryService URLs to point to the NLB server name.</span></span> <span data-ttu-id="e71af-131">注:この手順は、ハードウェア ベースの NLB の必要はありません。</span><span class="sxs-lookup"><span data-stu-id="e71af-131">Note: This procedure is not necessary for hardware-based NLB.</span></span>  
  
1. <span data-ttu-id="e71af-132">クリックしてメモ帳を使用して web.config ファイルを開く**開始**、**実行**、メモ帳」と入力[!INCLUDE[btsBiztalkServerPath](../includes/btsbiztalkserverpath-md.md)]bamportal \web.config」とをクリックして **[ok]**。</span><span class="sxs-lookup"><span data-stu-id="e71af-132">Open the web.config file using Notepad by clicking **Start**, clicking **Run**, typing notepad [!INCLUDE[btsBiztalkServerPath](../includes/btsbiztalkserverpath-md.md)]BAMPortal\web.config, and then clicking **OK**.</span></span>  
  
2. <span data-ttu-id="e71af-133">次のコンピューター名 (machinename) と、クラスターの名前の名前を指す次の 2 行でポートの名前を変更します。</span><span class="sxs-lookup"><span data-stu-id="e71af-133">Modify the following computer name (machinename) and the port name in the following two lines to point to the name of name of the cluster:</span></span>  
  
   ```  
   <add key="BamQueryWSUrl" value="http://machinename:portname /BAM/BAMQueryService/BamQueryService.asmx" />  
   <add key="BamManagementWSUrl" value=" http://machinename:portname/BAM/BAMManagementService/BamManagementService.asmx" />   
   ```  
  
3. <span data-ttu-id="e71af-134">ファイルを保存します。</span><span class="sxs-lookup"><span data-stu-id="e71af-134">Save the file.</span></span> <span data-ttu-id="e71af-135">これを行うには、次のようにクリックします。**ファイル**、 をクリックし、**保存**メモ帳のメニュー バー。</span><span class="sxs-lookup"><span data-stu-id="e71af-135">To do this, click **File**, and then click **Save** on the Notepad menu bar.</span></span>  
  
### <a name="to-configure-each-additional-computer-in-the-cluster"></a><span data-ttu-id="e71af-136">クラスターで追加した各コンピューターを構成するには</span><span class="sxs-lookup"><span data-stu-id="e71af-136">To configure each additional computer in the cluster</span></span>  
  
1. <span data-ttu-id="e71af-137">Web.config ファイルのコピー [!INCLUDE[btsBiztalkServerPath](../includes/btsbiztalkserverpath-md.md)]BAMPortal フォルダー、クラスターに追加した各コンピューターにします。</span><span class="sxs-lookup"><span data-stu-id="e71af-137">Copy the web.config file to [!INCLUDE[btsBiztalkServerPath](../includes/btsbiztalkserverpath-md.md)]BAMPortal folder on each additional computer in the cluster.</span></span>  
  
   > [!NOTE]
   >  <span data-ttu-id="e71af-138">次の手順をすべての参照を**Program Files**フォルダーになります**Program Files (x86)** 64 ビット コンピューター用です。</span><span class="sxs-lookup"><span data-stu-id="e71af-138">In the following steps all references to the **Program Files** folder will be **Program Files (x86)** for 64 bit computers.</span></span>  
   > 
   > [!IMPORTANT]
   >  <span data-ttu-id="e71af-139">次の手順では、仮想ディレクトリを作成するときは、最初のコンピューターで BizTalk Server 構成で作成された 3 つの BAM 仮想ディレクトリとして正確な設定があるかどうかを確認することを確認します。</span><span class="sxs-lookup"><span data-stu-id="e71af-139">In the following steps, when you are creating the virtual directories, check to make sure they have the exact settings as the three BAM virtual directories created by the BizTalk Server Configuration on first computer.</span></span> <span data-ttu-id="e71af-140">ファイルのパス、ASP.NET のバージョン、ディレクトリのアクセス許可、およびアプリケーション プールを確認します。</span><span class="sxs-lookup"><span data-stu-id="e71af-140">Confirm your file paths, the ASP.NET version, your directory permissions, and application pool.</span></span>  <span data-ttu-id="e71af-141">最初のコンピューターを設定するときに使用したのを設定しているコンピューターで BAMAppPool を実行するのにには、同じドメインのサービス アカウントを使用します。</span><span class="sxs-lookup"><span data-stu-id="e71af-141">Use the same domain service account to run the BAMAppPool on the computer you are setting up as you used when setting up the first computer.</span></span> <span data-ttu-id="e71af-142">BAMAppPool がすべてのコンピューターで実行されていることを確認します。</span><span class="sxs-lookup"><span data-stu-id="e71af-142">Make sure the BAMAppPool is running on all of the computers.</span></span> <span data-ttu-id="e71af-143">これは、2 つの web.config ファイルをコピーする必要があります。</span><span class="sxs-lookup"><span data-stu-id="e71af-143">There are two web.config files you must copy.</span></span>  
   > 
   >  <span data-ttu-id="e71af-144">Web.config ファイルに加えて[!INCLUDE[btsBiztalkServerPath](../includes/btsbiztalkserverpath-md.md)]BAMPortal、web.config ファイルをコピーする必要があります[!INCLUDE[btsBiztalkServerPath](../includes/btsbiztalkserverpath-md.md)]bamportal \bammanagementservice と[!INCLUDE[btsBiztalkServerPath](../includes/btsbiztalkserverpath-md.md)]bamportal \bamqueryservice の同じフォルダーにこのコンピューターにします。</span><span class="sxs-lookup"><span data-stu-id="e71af-144">In addition to the web.config file [!INCLUDE[btsBiztalkServerPath](../includes/btsbiztalkserverpath-md.md)]BAMPortal, you must copy the web.config file in [!INCLUDE[btsBiztalkServerPath](../includes/btsbiztalkserverpath-md.md)]BAMPortal\BAMManagementService and [!INCLUDE[btsBiztalkServerPath](../includes/btsbiztalkserverpath-md.md)]BAMPortal\BAMQueryService to the same folders on this computer.</span></span>  
  
2. <span data-ttu-id="e71af-145">ハードウェア ベースの nlb のみの場合は、次のコンピューター名 (machinename) と、クラスターの名前の名前を指す次の 2 行でポートの名前を変更します。</span><span class="sxs-lookup"><span data-stu-id="e71af-145">For hardware-based NLB only, modify the following computer name (machinename) and the port name in the following two lines to point to the name of name of the cluster:</span></span>  
  
   ```  
   <add key="BamQueryWSUrl" value="http://machinename:portname /BAM/BAMQueryService/BamQueryService.asmx" />  
   <add key="BamManagementWSUrl" value=" http://machinename:portname/BAM/BAMManagementService/BamManagementService.asmx" />  
   ```  
  
3. <span data-ttu-id="e71af-146">BAMAppPool というアプリケーション プールを作成します。</span><span class="sxs-lookup"><span data-stu-id="e71af-146">Create an application pool called BAMAppPool.</span></span>  
  
   > [!NOTE]
   >  <span data-ttu-id="e71af-147">仮想ディレクトリのディレクトリ パスは、InstallationFolder%/BamPortal、%installationfolder%/bamportal/bammanagementservice、および %InstallationFolder%/BamPortal/BAMQueryService はずです。</span><span class="sxs-lookup"><span data-stu-id="e71af-147">The directory path for the virtual directories should be %InstallationFolder%/BamPortal, %InstallationFolder%/BamPortal/BAMManagementService, and %InstallationFolder%/BamPortal/BAMQueryService.</span></span>  
  
4. <span data-ttu-id="e71af-148">BAM という既定の web サイトの下の仮想ディレクトリを作成します。</span><span class="sxs-lookup"><span data-stu-id="e71af-148">Create a virtual directory under the Default Website called BAM.</span></span>  
  
5. <span data-ttu-id="e71af-149">BAM 仮想ディレクトリのアプリケーション プールを BAMAppPool に変更します。</span><span class="sxs-lookup"><span data-stu-id="e71af-149">Change the application pool of BAM virtual directory to BAMAppPool.</span></span>  
  
   > [!NOTE]
   >  <span data-ttu-id="e71af-150">仮想ディレクトリのディレクトリ パスには、InstallationFolder%/BamPortal、%InstallationFolder%/BamPortal/BAMManagementService と %InstallationFolder%/BamPortal/BAMQueryService を指定します。</span><span class="sxs-lookup"><span data-stu-id="e71af-150">The directory path for the virtual directories should be %InstallationFolder%/BamPortal, %InstallationFolder%/BamPortal/BAMManagementService and %InstallationFolder%/BamPortal/BAMQueryService.</span></span>  
  
6. <span data-ttu-id="e71af-151">BAM の下に BAMManagementService という仮想ディレクトリを作成します。</span><span class="sxs-lookup"><span data-stu-id="e71af-151">Create a virtual directory called BAMManagementService under BAM.</span></span>  
  
7. <span data-ttu-id="e71af-152">BAMManagementService のアプリケーション プールを BAMAppPool に変更します。</span><span class="sxs-lookup"><span data-stu-id="e71af-152">Change the application pool of BAMManagementService to BAMAppPool.</span></span>  
  
   > [!NOTE]
   >  <span data-ttu-id="e71af-153">仮想ディレクトリのディレクトリ パスは、InstallationFolder%/BamPortal、%installationfolder%/bamportal/bammanagementservice、および %InstallationFolder%/BamPortal/BAMQueryService はずです。</span><span class="sxs-lookup"><span data-stu-id="e71af-153">The directory path for the virtual directories should be %InstallationFolder%/BamPortal, %InstallationFolder%/BamPortal/BAMManagementService, and %InstallationFolder%/BamPortal/BAMQueryService.</span></span>  
  
8. <span data-ttu-id="e71af-154">BAM の下に BAMQueryService という仮想ディレクトリを作成します。</span><span class="sxs-lookup"><span data-stu-id="e71af-154">Create a virtual directory called BAMQueryService under BAM.</span></span>  
  
9. <span data-ttu-id="e71af-155">BAMQueryService のアプリケーション プールを BAMAppPool に変更します。</span><span class="sxs-lookup"><span data-stu-id="e71af-155">Change the application pool of BAMQueryService to BAMAppPool.</span></span>  
  
10. <span data-ttu-id="e71af-156">.NET Framework 4 アプリケーションのバージョンを設定するのにには、BAM、BAMMANAGEMENTSERVICE、および BAMQUERYSERVICE のバージョンを変更するのに仮想ディレクトリ プロパティの ASP NET タブ上にある INETMGR を使用します。</span><span class="sxs-lookup"><span data-stu-id="e71af-156">Use the INETMGR, located on the virtual directory Properites ASP NET Tab, to change the version for BAM, BAMMANAGEMENTSERVICE, and BAMQUERYSERVICE to set the version of the Applications to .NET Framework 4.</span></span>  
  
11. <span data-ttu-id="e71af-157">Run aspnet_setreg.exe -k:"SOFTWARE\Microsoft\BizTalk Server\3.0\BAM\WebServices\identity" -u:BAMWebServiceAccount  -p:Password.</span><span class="sxs-lookup"><span data-stu-id="e71af-157">Run aspnet_setreg.exe -k:"SOFTWARE\Microsoft\BizTalk Server\3.0\BAM\WebServices\identity" -u:BAMWebServiceAccount  -p:Password.</span></span>  <span data-ttu-id="e71af-158">アカウントを指定、BAM 管理 Web サービスのユーザー アカウントを次に示します。</span><span class="sxs-lookup"><span data-stu-id="e71af-158">The account specified here is the BAM Management Web Service User account.</span></span>  
  
    > [!CAUTION]
    >  <span data-ttu-id="e71af-159">BAM ポータル*のみ*は 32 ビット モードで実行されます。</span><span class="sxs-lookup"><span data-stu-id="e71af-159">BAM Portal *only* runs in 32-bit mode.</span></span> <span data-ttu-id="e71af-160">64 ビット コンピューターで IIS がインストールされている場合は、32 ビット モードで ASP.NET 2.0 を有効にする必要があります。</span><span class="sxs-lookup"><span data-stu-id="e71af-160">If IIS is installed on a 64-bit machine, ASP.NET 2.0 must be enabled in 32-bit mode.</span></span> <span data-ttu-id="e71af-161">これを行うには、IIS マネージャーを開き開く**アプリケーション プール**アプリケーション プール (BAMAppPool) を選択し、クリックして**詳細設定**します。</span><span class="sxs-lookup"><span data-stu-id="e71af-161">To do this, open IIS Manager, open **Application Pool**, select the application pool (BAMAppPool), and then click **Advanced Settings**.</span></span> <span data-ttu-id="e71af-162">**[32 ビット アプリケーションの有効化]** で、**[True]** を選択します。</span><span class="sxs-lookup"><span data-stu-id="e71af-162">In **Enable 32-bit applications**, select **True**.</span></span>  
    >   
    >  <span data-ttu-id="e71af-163">[BAM ポータルの計画](../core/planning-for-the-bam-portal.md)追加の要件を一覧表示されます。</span><span class="sxs-lookup"><span data-stu-id="e71af-163">[Planning for the BAM Portal](../core/planning-for-the-bam-portal.md) lists additional requirements.</span></span>  
  
12. <span data-ttu-id="e71af-164">読み取りを設定 SubInACL、管理者はファイル、レジストリ キー、およびサービスに関するセキュリティ情報を取得し、ローカル コンピューターからユーザーに、この情報を転送できるようにするコマンド ライン ツールを実行して、WebServices の AppPool ユーザー用の Acl またはグローバル グループとグループ、ドメインにドメインからです。</span><span class="sxs-lookup"><span data-stu-id="e71af-164">Set the read ACLs for the AppPool user on WebServices by running SubInACL, a command-line tool that enables administrators to obtain security information about files, registry keys, and services, and to transfer this information from user to user, from local or global group to group, and from domain to domain.</span></span>  
  
13. <span data-ttu-id="e71af-165">ダウンロードから SubInAcl [ http://go.microsoft.com/fwlink/?LinkId=61990](http://go.microsoft.com/fwlink/?LinkId=61990)します。</span><span class="sxs-lookup"><span data-stu-id="e71af-165">Download SubInAcl from [http://go.microsoft.com/fwlink/?LinkId=61990](http://go.microsoft.com/fwlink/?LinkId=61990).</span></span>  
  
14. <span data-ttu-id="e71af-166">コマンド プロンプトを開きます。</span><span class="sxs-lookup"><span data-stu-id="e71af-166">Open a command prompt.</span></span> <span data-ttu-id="e71af-167">これを行うには、次のようにクリックします。**開始**、 をクリック**実行**、型**cmd**、順にクリックします**OK**します。</span><span class="sxs-lookup"><span data-stu-id="e71af-167">To do this, click **Start**, click **Run**, type **cmd**, and then click **OK**.</span></span>  
  
15. <span data-ttu-id="e71af-168">コマンド プロンプトで、次の入力: subinacl.exe/subkeyreg"HKEY_LOCAL_MACHINE\SOFTWARE\Microsoft\BizTalk Server\3.0\BAM\WebServices""付与/ネットワーク サービスの = = R"</span><span class="sxs-lookup"><span data-stu-id="e71af-168">Type the following at the command prompt: subinacl.exe /subkeyreg "HKEY_LOCAL_MACHINE\SOFTWARE\Microsoft\BizTalk Server\3.0\BAM\WebServices" "/grant=Network Service=R"</span></span>  
  
    > [!NOTE]
    >  <span data-ttu-id="e71af-169">このコマンドでは、SOFTWAREMicrosoftBizTalk Server3.0BAMWebServicesidentity のレジストリ キーに BAM アプリケーション プール ユーザーの読み取りアクセスを許可します。</span><span class="sxs-lookup"><span data-stu-id="e71af-169">The purpose of this command is to grant the BAM Application Pool user read access to the SOFTWAREMicrosoftBizTalk Server3.0BAMWebServicesidentity registry key.</span></span> <span data-ttu-id="e71af-170">アプリケーション プールの IIS によって使用される既定値であるために、ネットワーク サービスを使用します。</span><span class="sxs-lookup"><span data-stu-id="e71af-170">The example uses Network Service since it is the default used by IIS for Application Pool.</span></span> <span data-ttu-id="e71af-171">既定の IIS 設定を使用しない場合は、配置で使用するアプリケーション プール ユーザーを置き換える必要があります。</span><span class="sxs-lookup"><span data-stu-id="e71af-171">If you do not use the default IIS settings, you should substitute the application pool user that your deployment uses.</span></span>  
  
16. <span data-ttu-id="e71af-172">コマンド プロンプトで、次の入力: subinacl.exe/keyreg「hkey_local_machine \software\microsoft\biztalk server \3.0」"付与/=\<BAM web サービス アカウント\>"</span><span class="sxs-lookup"><span data-stu-id="e71af-172">Type the following at the command prompt: subinacl.exe /keyreg "HKEY_LOCAL_MACHINE\SOFTWARE\Microsoft\BizTalk Server\3.0" "/grant=\<BAM WebService Account\>”</span></span>  
  
    > [!NOTE]
    >  <span data-ttu-id="e71af-173">このコマンドでは、SOFTWARE\Microsoft\BizTalk Server\3.0\BAM\WebServices\Identity のレジストリ キーに、BAM 管理 Web サービスのユーザー アカウントの読み取りアクセスを許可します。</span><span class="sxs-lookup"><span data-stu-id="e71af-173">The purpose of this command is to grant the BAM Management Web Service User account read access to the SOFTWARE\Microsoft\BizTalk Server\3.0\BAM\WebServices\Identity registry key.</span></span>  
  
17. <span data-ttu-id="e71af-174">BAMManagement Web サービス アプリケーション プールを実行する id に ASPNET_SETREG キーに読み取りアクセスがあることを確認します。</span><span class="sxs-lookup"><span data-stu-id="e71af-174">Verify that the identity that the application pool that the BAMManagement Web service runs under has read access to the ASPNET_SETREG key.</span></span>  
  
18. <span data-ttu-id="e71af-175">コンピューターの管理の管理者ツールを使用すると、IIS ワーカー プロセス グループ (IIS_WPG) および SharePoint services グループ (STS_WPG) に BAM 管理 Web サービスのユーザーと BAM アプリケーション プールのユーザー アカウントを追加できます。</span><span class="sxs-lookup"><span data-stu-id="e71af-175">Use the Computer Management administrator tool to add the BAM Management Web service user and the BAM application pool user account to the IIS Worker Process Group (IIS_WPG) and SharePoint services group (STS_WPG).</span></span>  
  
19. <span data-ttu-id="e71af-176">アプリケーション プールと Web サービスのユーザーの一時 ASP.NET フォルダーに対するアクセス許可を設定します。 c:\windows\system32\cacls"%windir%\Microsoft.NET\Framework\ バージョン 2.0。\<最小のバージョン番号\>\Temporary ASP.NET Files"/T/E/G \<BAM web サービス アカウント\>: F</span><span class="sxs-lookup"><span data-stu-id="e71af-176">Set the permissions on the temporary ASP.NET folders for the applications pool and Web service users: c:\windows\system32\cacls "%windir%\Microsoft.NET\Framework\ v2.0.\<min version number\>\Temporary ASP.NET Files" /T /E /G \<BAM WebService Account\>:F</span></span>  
  
    > [!NOTE]
    >  <span data-ttu-id="e71af-177">BAM 管理 Web サービスのユーザー アカウントと BAM アプリケーション プール ユーザー アカウントの両方へのアクセスを付与します。</span><span class="sxs-lookup"><span data-stu-id="e71af-177">You grant access to both the BAM Management Web Service User account and the BAM App Pool User account.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="e71af-178">参照</span><span class="sxs-lookup"><span data-stu-id="e71af-178">See Also</span></span>  
 [<span data-ttu-id="e71af-179">BAM ポータルの管理</span><span class="sxs-lookup"><span data-stu-id="e71af-179">Managing the BAM Portal</span></span>](../core/managing-the-bam-portal.md)