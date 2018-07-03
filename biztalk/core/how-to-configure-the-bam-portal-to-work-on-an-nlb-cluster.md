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
ms.openlocfilehash: adc423fc74cd504f79a1106d196868df20faf974
ms.sourcegitcommit: 266308ec5c6a9d8d80ff298ee6051b4843c5d626
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 06/27/2018
ms.locfileid: "36994467"
---
# <a name="how-to-configure-the-bam-portal-to-work-on-an-nlb-cluster"></a><span data-ttu-id="6e9c0-102">NLB クラスターで機能する BAM ポータルを構成する方法</span><span class="sxs-lookup"><span data-stu-id="6e9c0-102">How to Configure the BAM Portal to Work on an NLB Cluster</span></span>
<span data-ttu-id="6e9c0-103">BAM ポータルは、ネットワーク負荷分散 (NLB) クラスターで機能するように構成できます。</span><span class="sxs-lookup"><span data-stu-id="6e9c0-103">The BAM portal can be configured to work in a network load balancing (NLB) cluster.</span></span>  
  
> [!IMPORTANT]
>  <span data-ttu-id="6e9c0-104">BAM ポータル*のみ*は 32 ビット モードで実行されます。</span><span class="sxs-lookup"><span data-stu-id="6e9c0-104">BAM Portal *only* runs in 32-bit mode.</span></span> <span data-ttu-id="6e9c0-105">IIS を 64 ビット コンピューターにインストールする場合は、ASP.NET 2.0 が 32 ビット モードで有効になっていることを確認します。</span><span class="sxs-lookup"><span data-stu-id="6e9c0-105">If IIS is installed on a 64-bit machine, then confirm ASP.NET 2.0 is enabled in 32-bit mode.</span></span> <span data-ttu-id="6e9c0-106">これを行うには、IIS マネージャーを開き開く**アプリケーション プール**アプリケーション プール (BAMAppPool) を選択し、クリックして**詳細設定**します。</span><span class="sxs-lookup"><span data-stu-id="6e9c0-106">To do this, open IIS Manager, open **Application Pool**, select the application pool (BAMAppPool), and then click **Advanced Settings**.</span></span> <span data-ttu-id="6e9c0-107">**[32 ビット アプリケーションの有効化]** で、**[True]** を選択します。</span><span class="sxs-lookup"><span data-stu-id="6e9c0-107">In **Enable 32-bit applications**, select **True**.</span></span>  
>   
>  <span data-ttu-id="6e9c0-108">BAM ポータルの追加の要件を参照してください。 [BAM ポータルの計画](../core/planning-for-the-bam-portal.md)します。</span><span class="sxs-lookup"><span data-stu-id="6e9c0-108">For additional BAM Portal requirements, see [Planning for the BAM Portal](../core/planning-for-the-bam-portal.md).</span></span>  
  
### <a name="to-prepare-to-configure-bam-portal-on-an-nlb-cluster"></a><span data-ttu-id="6e9c0-109">NLB クラスターで BAM ポータルを構成できるよう準備するには</span><span class="sxs-lookup"><span data-stu-id="6e9c0-109">To prepare to configure BAM portal on an NLB cluster</span></span>  
  
1.  <span data-ttu-id="6e9c0-110">1 台目のコンピューターにポータルをインストールして構成します。</span><span class="sxs-lookup"><span data-stu-id="6e9c0-110">Install and configure the portal on the first computer.</span></span>  
  
    > [!NOTE]
    >  <span data-ttu-id="6e9c0-111">ポータルの構成は 1 台目のコンピューターでのみ行います。</span><span class="sxs-lookup"><span data-stu-id="6e9c0-111">You only configure the portal on the first computer.</span></span> <span data-ttu-id="6e9c0-112">クラスター内の他のコンピューターで BAM ポータルを有効にすることもできますが、構成は 1 台目のコンピューターでのみ行います。</span><span class="sxs-lookup"><span data-stu-id="6e9c0-112">You have the option of enabling the BAM portal on other the other computers in the cluster, but the configuration is done only on the first computer.</span></span>  
  
2.  <span data-ttu-id="6e9c0-113">NLB クラスターに含めるすべてのコンピューターにポータル コンポーネントをインストールし、ポータルを構成したコンピューターの BizTalk グループにクラスター内の他のコンピューターを参加させます。</span><span class="sxs-lookup"><span data-stu-id="6e9c0-113">Install the portal components on all the computers to be included in the NLB cluster, and then join the other computers in the cluster to the BizTalk group of the computer on which the portal is configured.</span></span> <span data-ttu-id="6e9c0-114">BizTalk グループを有効にして、適切なグループに参加させる必要があります。</span><span class="sxs-lookup"><span data-stu-id="6e9c0-114">You must enable the BizTalk groups and join the appropriate group.</span></span>  
  
3.  <span data-ttu-id="6e9c0-115">ポータルをインストールしたコンピューター用に構成した BizTalk 管理データベースを選択します。</span><span class="sxs-lookup"><span data-stu-id="6e9c0-115">Select the BizTalk Management database configured for the computer on which the portal is installed.</span></span>  
  
4.  <span data-ttu-id="6e9c0-116">NLB クラスターを作成します。</span><span class="sxs-lookup"><span data-stu-id="6e9c0-116">Create the NLB cluster.</span></span> <span data-ttu-id="6e9c0-117">作成して、ネットワーク負荷分散クラスターを管理する方法の詳細についてを参照してください「を作成および管理ネットワーク負荷分散クラスターの」 [ http://go.microsoft.com/fwlink/?LinkId=56206](http://go.microsoft.com/fwlink/?LinkId=56206)します。</span><span class="sxs-lookup"><span data-stu-id="6e9c0-117">For more information about how to create and manage network load balancing clusters, see "Create and Manage Network Load Balancing Clusters" at [http://go.microsoft.com/fwlink/?LinkId=56206](http://go.microsoft.com/fwlink/?LinkId=56206).</span></span>  
  
    > [!NOTE]
    >  <span data-ttu-id="6e9c0-118">続行する前に、NLB クラスターが BizTalk Server のコンテキスト外で正しく動作するかどうかを確認してください。</span><span class="sxs-lookup"><span data-stu-id="6e9c0-118">You should confirm that your NLB cluster is working properly outside of the BizTalk Server context before continuing.</span></span>  
  
    > [!NOTE]
    >  <span data-ttu-id="6e9c0-119">ハードウェア ベースの NLB をセットアップするには、ハードウェア プロバイダーのドキュメントを参照してください。</span><span class="sxs-lookup"><span data-stu-id="6e9c0-119">To set up hardware-based NLB, refer to your hardware provider's documentation.</span></span>  
  
### <a name="to-update-the-bam-configuration-to-reflect-the-location-of-the-cluster"></a><span data-ttu-id="6e9c0-120">BAM 構成を更新してクラスターの場所を反映するには</span><span class="sxs-lookup"><span data-stu-id="6e9c0-120">To update the BAM configuration to reflect the location of the cluster</span></span>  
  
1. <span data-ttu-id="6e9c0-121">BAM 管理ユーティリティを使用して現在の BAM 構成を取得します。</span><span class="sxs-lookup"><span data-stu-id="6e9c0-121">Use the BAM Management Utility to get the current BAM configuration.</span></span> <span data-ttu-id="6e9c0-122">これを行うには、次のようにクリックします。**開始**、 をクリック**実行**、および種類[!INCLUDE[btsBiztalkServerPath](../includes/btsbiztalkserverpath-md.md)]の config の取得 \bm--filename:myconfig.xml します。</span><span class="sxs-lookup"><span data-stu-id="6e9c0-122">To do this, click **Start**, click **Run**, and type [!INCLUDE[btsBiztalkServerPath](../includes/btsbiztalkserverpath-md.md)]Tracking\bm get-config -FileName:MyConfig.xml.</span></span>  
  
2. <span data-ttu-id="6e9c0-123">ローカル ホスト名を NLB クラスターの名前と置き換えます。</span><span class="sxs-lookup"><span data-stu-id="6e9c0-123">Replace the local host name with the name of the NLB cluster.</span></span> <span data-ttu-id="6e9c0-124">これを行うには、次のようにクリックします。**開始**、 をクリック**実行**、および「notepad [!INCLUDE[btsBiztalkServerPath](../includes/btsbiztalkserverpath-md.md)]Tracking\MyConfig.xml します。</span><span class="sxs-lookup"><span data-stu-id="6e9c0-124">To do this, click **Start**, click **Run**, and type notepad [!INCLUDE[btsBiztalkServerPath](../includes/btsbiztalkserverpath-md.md)]Tracking\MyConfig.xml.</span></span>  
  
3. <span data-ttu-id="6e9c0-125">ハードウェア ベースの NLB の場合のみ、構成ファイルに次の記述があることを確認します。</span><span class="sxs-lookup"><span data-stu-id="6e9c0-125">For hardware-based NLB only, verify the configuration file has the following:</span></span>  
  
   ```  
   <GlobalProperty Name="BAMVRoot">  
   http://<NLB IP Address>:portname/BAM</GlobalProperty>  
   ```  
  
   > [!NOTE]
   >  <span data-ttu-id="6e9c0-126">ハードウェアベースの NLB で BAM 構成を更新する場合、手順 4. と 5. は必要ありません。</span><span class="sxs-lookup"><span data-stu-id="6e9c0-126">Steps 4 and 5 are not necessary when updating the BAM configuration on hardware-based NLB.</span></span>  
  
4. <span data-ttu-id="6e9c0-127">次の行で、コンピューター名 (machinename) をクラスター名と置き換えて、NLB クラスターを指すように変更します。</span><span class="sxs-lookup"><span data-stu-id="6e9c0-127">Modify the following line to point to the NLB cluster by replacing the computer name (machinename) with the cluster name:</span></span>  
  
   ```  
   <GlobalProperty Name=" BAMVRoot">  http://machinename:portname/BAM  
   </GlobalProperty>   
   ```  
  
5. <span data-ttu-id="6e9c0-128">新しい構成を保存します。</span><span class="sxs-lookup"><span data-stu-id="6e9c0-128">Save the new configuration.</span></span> <span data-ttu-id="6e9c0-129">これを行うには、次のようにクリックします。**開始**、 をクリック**実行**、および種類[!INCLUDE[btsBiztalkServerPath](../includes/btsbiztalkserverpath-md.md)]\bm 更新-config--filename:myconfig.xml。</span><span class="sxs-lookup"><span data-stu-id="6e9c0-129">To do this, click **Start**, click **Run**, and type [!INCLUDE[btsBiztalkServerPath](../includes/btsbiztalkserverpath-md.md)]Tracking\bm update-config -FileName:MyConfig.xml.</span></span>  
  
### <a name="to-edit-the-bam-portal-webconfig-file-to-change-the-bammanagementservice-and-queryservice-urls-to-point-to-the-nlb-server-name-note-this-procedure-is-not-necessary-for-hardware-based-nlb"></a><span data-ttu-id="6e9c0-130">BAM ポータルの web.config ファイルを編集して NLB サーバー名を指すように BAMmanagementService および QueryService の URL を変更するには</span><span class="sxs-lookup"><span data-stu-id="6e9c0-130">To edit the BAM portal web.config file to change the BAMmanagementService and QueryService URLs to point to the NLB server name.</span></span> <span data-ttu-id="6e9c0-131">注: この手順はハードウェア ベースの NLB の必要はありません。</span><span class="sxs-lookup"><span data-stu-id="6e9c0-131">Note: This procedure is not necessary for hardware-based NLB.</span></span>  
  
1. <span data-ttu-id="6e9c0-132">クリックしてメモ帳を使用して web.config ファイルを開く**開始**、**実行**、メモ帳」と入力[!INCLUDE[btsBiztalkServerPath](../includes/btsbiztalkserverpath-md.md)]bamportal \web.config」とをクリックして **[ok]**。</span><span class="sxs-lookup"><span data-stu-id="6e9c0-132">Open the web.config file using Notepad by clicking **Start**, clicking **Run**, typing notepad [!INCLUDE[btsBiztalkServerPath](../includes/btsbiztalkserverpath-md.md)]BAMPortal\web.config, and then clicking **OK**.</span></span>  
  
2. <span data-ttu-id="6e9c0-133">次の 2 行で、コンピューター名 (machinename) とポート名を、クラスター名を指すように変更します。</span><span class="sxs-lookup"><span data-stu-id="6e9c0-133">Modify the following computer name (machinename) and the port name in the following two lines to point to the name of name of the cluster:</span></span>  
  
   ```  
   <add key="BamQueryWSUrl" value="http://machinename:portname /BAM/BAMQueryService/BamQueryService.asmx" />  
   <add key="BamManagementWSUrl" value=" http://machinename:portname/BAM/BAMManagementService/BamManagementService.asmx" />   
   ```  
  
3. <span data-ttu-id="6e9c0-134">ファイルを保存します。</span><span class="sxs-lookup"><span data-stu-id="6e9c0-134">Save the file.</span></span> <span data-ttu-id="6e9c0-135">これを行うには、次のようにクリックします。**ファイル**、 をクリックし、**保存**メモ帳のメニュー バー。</span><span class="sxs-lookup"><span data-stu-id="6e9c0-135">To do this, click **File**, and then click **Save** on the Notepad menu bar.</span></span>  
  
### <a name="to-configure-each-additional-computer-in-the-cluster"></a><span data-ttu-id="6e9c0-136">クラスターに追加した各コンピューターを構成するには</span><span class="sxs-lookup"><span data-stu-id="6e9c0-136">To configure each additional computer in the cluster</span></span>  
  
1. <span data-ttu-id="6e9c0-137">web.config ファイルを、クラスターに追加した各コンピューターの [!INCLUDE[btsBiztalkServerPath](../includes/btsbiztalkserverpath-md.md)]BAMPortal フォルダーにコピーします。</span><span class="sxs-lookup"><span data-stu-id="6e9c0-137">Copy the web.config file to [!INCLUDE[btsBiztalkServerPath](../includes/btsbiztalkserverpath-md.md)]BAMPortal folder on each additional computer in the cluster.</span></span>  
  
   > [!NOTE]
   >  <span data-ttu-id="6e9c0-138">次の手順をすべての参照を**Program Files**フォルダーになります**Program Files (x86)** 64 ビット コンピューター用です。</span><span class="sxs-lookup"><span data-stu-id="6e9c0-138">In the following steps all references to the **Program Files** folder will be **Program Files (x86)** for 64 bit computers.</span></span>  
   > 
   > [!IMPORTANT]
   >  <span data-ttu-id="6e9c0-139">仮想ディレクトリを作成するときには、その設定が 1 台目のコンピューターの BizTalk Server 構成で作成した 3 つの BAM 仮想ディレクトリの設定と正確に同じかどうかを確認してください。これにはまず、</span><span class="sxs-lookup"><span data-stu-id="6e9c0-139">In the following steps, when you are creating the virtual directories, check to make sure they have the exact settings as the three BAM virtual directories created by the BizTalk Server Configuration on first computer.</span></span> <span data-ttu-id="6e9c0-140">ファイル パス、ASP.NET のバージョン、ディレクトリのアクセス許可、およびアプリケーション プールを確認します。</span><span class="sxs-lookup"><span data-stu-id="6e9c0-140">Confirm your file paths, the ASP.NET version, your directory permissions, and application pool.</span></span>  <span data-ttu-id="6e9c0-141">次に、1 台目のコンピューターの設定で使用したドメイン サービス アカウントと同じアカウントを使用して、設定するコンピューターで BAMAppPool を実行します。</span><span class="sxs-lookup"><span data-stu-id="6e9c0-141">Use the same domain service account to run the BAMAppPool on the computer you are setting up as you used when setting up the first computer.</span></span> <span data-ttu-id="6e9c0-142">BAMAppPool がすべてのコンピューターで稼働することを確認します。</span><span class="sxs-lookup"><span data-stu-id="6e9c0-142">Make sure the BAMAppPool is running on all of the computers.</span></span> <span data-ttu-id="6e9c0-143">コピーする必要がある web.config ファイルは 2 つです。</span><span class="sxs-lookup"><span data-stu-id="6e9c0-143">There are two web.config files you must copy.</span></span>  
   > 
   >  <span data-ttu-id="6e9c0-144">web.config ファイルの [!INCLUDE[btsBiztalkServerPath](../includes/btsbiztalkserverpath-md.md)]BAMPortal に加え、[!INCLUDE[btsBiztalkServerPath](../includes/btsbiztalkserverpath-md.md)]BAMPortal\BAMManagementService と [!INCLUDE[btsBiztalkServerPath](../includes/btsbiztalkserverpath-md.md)]BAMPortal\BAMQueryService の web.config ファイルをこのコンピューターの同じフォルダーにコピーする必要があります。</span><span class="sxs-lookup"><span data-stu-id="6e9c0-144">In addition to the web.config file [!INCLUDE[btsBiztalkServerPath](../includes/btsbiztalkserverpath-md.md)]BAMPortal, you must copy the web.config file in [!INCLUDE[btsBiztalkServerPath](../includes/btsbiztalkserverpath-md.md)]BAMPortal\BAMManagementService and [!INCLUDE[btsBiztalkServerPath](../includes/btsbiztalkserverpath-md.md)]BAMPortal\BAMQueryService to the same folders on this computer.</span></span>  
  
2. <span data-ttu-id="6e9c0-145">ハードウェア ベースの NLB の場合のみ、次の 2 行で、コンピューター名 (machinename) とポート名を、クラスター名を指すように変更します。</span><span class="sxs-lookup"><span data-stu-id="6e9c0-145">For hardware-based NLB only, modify the following computer name (machinename) and the port name in the following two lines to point to the name of name of the cluster:</span></span>  
  
   ```  
   <add key="BamQueryWSUrl" value="http://machinename:portname /BAM/BAMQueryService/BamQueryService.asmx" />  
   <add key="BamManagementWSUrl" value=" http://machinename:portname/BAM/BAMManagementService/BamManagementService.asmx" />  
   ```  
  
3. <span data-ttu-id="6e9c0-146">BAMAppPool というアプリケーション プールを作成します。</span><span class="sxs-lookup"><span data-stu-id="6e9c0-146">Create an application pool called BAMAppPool.</span></span>  
  
   > [!NOTE]
   >  <span data-ttu-id="6e9c0-147">仮想ディレクトリのディレクトリ パスは、InstallationFolder%/BamPortal、%installationfolder%/bamportal/bammanagementservice、および %InstallationFolder%/BamPortal/BAMQueryService はずです。</span><span class="sxs-lookup"><span data-stu-id="6e9c0-147">The directory path for the virtual directories should be %InstallationFolder%/BamPortal, %InstallationFolder%/BamPortal/BAMManagementService, and %InstallationFolder%/BamPortal/BAMQueryService.</span></span>  
  
4. <span data-ttu-id="6e9c0-148">BAM という既定の Web サイトの下に、仮想ディレクトリを作成します。</span><span class="sxs-lookup"><span data-stu-id="6e9c0-148">Create a virtual directory under the Default Website called BAM.</span></span>  
  
5. <span data-ttu-id="6e9c0-149">BAM 仮想ディレクトリのアプリケーション プールを BAMAppPool に変更します。</span><span class="sxs-lookup"><span data-stu-id="6e9c0-149">Change the application pool of BAM virtual directory to BAMAppPool.</span></span>  
  
   > [!NOTE]
   >  <span data-ttu-id="6e9c0-150">仮想ディレクトリのディレクトリ パスは、%InstallationFolder%/BamPortal、%InstallationFolder%/BamPortal/BAMManagementService、および %InstallationFolder%/BamPortal/BAMQueryService とする必要があります。</span><span class="sxs-lookup"><span data-stu-id="6e9c0-150">The directory path for the virtual directories should be %InstallationFolder%/BamPortal, %InstallationFolder%/BamPortal/BAMManagementService and %InstallationFolder%/BamPortal/BAMQueryService.</span></span>  
  
6. <span data-ttu-id="6e9c0-151">BAM の下に BAMManagementService という仮想ディレクトリを作成します。</span><span class="sxs-lookup"><span data-stu-id="6e9c0-151">Create a virtual directory called BAMManagementService under BAM.</span></span>  
  
7. <span data-ttu-id="6e9c0-152">BAMManagementService のアプリケーション プールを BAMAppPool に変更します。</span><span class="sxs-lookup"><span data-stu-id="6e9c0-152">Change the application pool of BAMManagementService to BAMAppPool.</span></span>  
  
   > [!NOTE]
   >  <span data-ttu-id="6e9c0-153">仮想ディレクトリのディレクトリ パスは、InstallationFolder%/BamPortal、%installationfolder%/bamportal/bammanagementservice、および %InstallationFolder%/BamPortal/BAMQueryService はずです。</span><span class="sxs-lookup"><span data-stu-id="6e9c0-153">The directory path for the virtual directories should be %InstallationFolder%/BamPortal, %InstallationFolder%/BamPortal/BAMManagementService, and %InstallationFolder%/BamPortal/BAMQueryService.</span></span>  
  
8. <span data-ttu-id="6e9c0-154">BAM の下に BAMQueryService という仮想ディレクトリを作成します。</span><span class="sxs-lookup"><span data-stu-id="6e9c0-154">Create a virtual directory called BAMQueryService under BAM.</span></span>  
  
9. <span data-ttu-id="6e9c0-155">BAMQueryService のアプリケーション プールを BAMAppPool に変更します。</span><span class="sxs-lookup"><span data-stu-id="6e9c0-155">Change the application pool of BAMQueryService to BAMAppPool.</span></span>  
  
10. <span data-ttu-id="6e9c0-156">.NET Framework 4 アプリケーションのバージョンを設定するのにには、BAM、BAMMANAGEMENTSERVICE、および BAMQUERYSERVICE のバージョンを変更するのに仮想ディレクトリ プロパティの ASP NET タブ上にある INETMGR を使用します。</span><span class="sxs-lookup"><span data-stu-id="6e9c0-156">Use the INETMGR, located on the virtual directory Properites ASP NET Tab, to change the version for BAM, BAMMANAGEMENTSERVICE, and BAMQUERYSERVICE to set the version of the Applications to .NET Framework 4.</span></span>  
  
11. <span data-ttu-id="6e9c0-157">「aspnet_setreg.exe -k:"SOFTWARE\Microsoft\BizTalk Server\3.0\BAM\WebServices\identity" -u:BAMWebServiceAccount  -p:Password」を実行します。</span><span class="sxs-lookup"><span data-stu-id="6e9c0-157">Run aspnet_setreg.exe -k:"SOFTWARE\Microsoft\BizTalk Server\3.0\BAM\WebServices\identity" -u:BAMWebServiceAccount  -p:Password.</span></span>  <span data-ttu-id="6e9c0-158">ここで指定するアカウントは、BAM 管理 Web サービス ユーザー アカウントです。</span><span class="sxs-lookup"><span data-stu-id="6e9c0-158">The account specified here is the BAM Management Web Service User account.</span></span>  
  
    > [!CAUTION]
    >  <span data-ttu-id="6e9c0-159">BAM ポータル*のみ*は 32 ビット モードで実行されます。</span><span class="sxs-lookup"><span data-stu-id="6e9c0-159">BAM Portal *only* runs in 32-bit mode.</span></span> <span data-ttu-id="6e9c0-160">IIS を 64 ビット コンピューターにインストールする場合は、ASP.NET 2.0 が 32 ビット モードで有効になっている必要があります。</span><span class="sxs-lookup"><span data-stu-id="6e9c0-160">If IIS is installed on a 64-bit machine, ASP.NET 2.0 must be enabled in 32-bit mode.</span></span> <span data-ttu-id="6e9c0-161">これを行うには、IIS マネージャーを開き開く**アプリケーション プール**アプリケーション プール (BAMAppPool) を選択し、クリックして**詳細設定**します。</span><span class="sxs-lookup"><span data-stu-id="6e9c0-161">To do this, open IIS Manager, open **Application Pool**, select the application pool (BAMAppPool), and then click **Advanced Settings**.</span></span> <span data-ttu-id="6e9c0-162">**[32 ビット アプリケーションの有効化]** で、**[True]** を選択します。</span><span class="sxs-lookup"><span data-stu-id="6e9c0-162">In **Enable 32-bit applications**, select **True**.</span></span>  
    >   
    >  <span data-ttu-id="6e9c0-163">[BAM ポータルの計画](../core/planning-for-the-bam-portal.md)追加の要件を一覧表示されます。</span><span class="sxs-lookup"><span data-stu-id="6e9c0-163">[Planning for the BAM Portal](../core/planning-for-the-bam-portal.md) lists additional requirements.</span></span>  
  
12. <span data-ttu-id="6e9c0-164">SubInACL を実行して、WebServices の AppPool ユーザーに対して読み取り ACL を設定します。コマンド ライン ツールである SubInACL を使用すると、管理者は、ファイル、レジストリ キー、およびサービスに関するセキュリティ情報を入手し、この情報をユーザー間、ローカル グループまたはグローバル グループ間、およびドメイン間で転送できます。</span><span class="sxs-lookup"><span data-stu-id="6e9c0-164">Set the read ACLs for the AppPool user on WebServices by running SubInACL, a command-line tool that enables administrators to obtain security information about files, registry keys, and services, and to transfer this information from user to user, from local or global group to group, and from domain to domain.</span></span>  
  
13. <span data-ttu-id="6e9c0-165">ダウンロードから SubInAcl [ http://go.microsoft.com/fwlink/?LinkId=61990](http://go.microsoft.com/fwlink/?LinkId=61990)します。</span><span class="sxs-lookup"><span data-stu-id="6e9c0-165">Download SubInAcl from [http://go.microsoft.com/fwlink/?LinkId=61990](http://go.microsoft.com/fwlink/?LinkId=61990).</span></span>  
  
14. <span data-ttu-id="6e9c0-166">コマンド プロンプトを開きます。</span><span class="sxs-lookup"><span data-stu-id="6e9c0-166">Open a command prompt.</span></span> <span data-ttu-id="6e9c0-167">これを行うには、次のようにクリックします。**開始**、 をクリック**実行**、型**cmd**、順にクリックします**OK**します。</span><span class="sxs-lookup"><span data-stu-id="6e9c0-167">To do this, click **Start**, click **Run**, type **cmd**, and then click **OK**.</span></span>  
  
15. <span data-ttu-id="6e9c0-168">コマンド プロンプトで、次の入力: subinacl.exe/subkeyreg"HKEY_LOCAL_MACHINE\SOFTWARE\Microsoft\BizTalk Server\3.0\BAM\WebServices""付与/ネットワーク サービスの = = R"</span><span class="sxs-lookup"><span data-stu-id="6e9c0-168">Type the following at the command prompt: subinacl.exe /subkeyreg "HKEY_LOCAL_MACHINE\SOFTWARE\Microsoft\BizTalk Server\3.0\BAM\WebServices" "/grant=Network Service=R"</span></span>  
  
    > [!NOTE]
    >  <span data-ttu-id="6e9c0-169">このコマンドでは、SOFTWAREMicrosoftBizTalk Server3.0BAMWebServicesidentity のレジストリ キーに BAM アプリケーション プール ユーザーの読み取りアクセスを許可します。</span><span class="sxs-lookup"><span data-stu-id="6e9c0-169">The purpose of this command is to grant the BAM Application Pool user read access to the SOFTWAREMicrosoftBizTalk Server3.0BAMWebServicesidentity registry key.</span></span> <span data-ttu-id="6e9c0-170">例では Network Service を使用しています。アプリケーション プール用 IIS では Network Service が既定として使用されます。</span><span class="sxs-lookup"><span data-stu-id="6e9c0-170">The example uses Network Service since it is the default used by IIS for Application Pool.</span></span> <span data-ttu-id="6e9c0-171">既定の IIS 設定を使用しない場合は、展開で使用するアプリケーション プール ユーザーを代わりに指定してください。</span><span class="sxs-lookup"><span data-stu-id="6e9c0-171">If you do not use the default IIS settings, you should substitute the application pool user that your deployment uses.</span></span>  
  
16. <span data-ttu-id="6e9c0-172">コマンド プロンプトで、次の入力: subinacl.exe/keyreg「hkey_local_machine \software\microsoft\biztalk server \3.0」"付与/=\<BAM web サービス アカウント\>"</span><span class="sxs-lookup"><span data-stu-id="6e9c0-172">Type the following at the command prompt: subinacl.exe /keyreg "HKEY_LOCAL_MACHINE\SOFTWARE\Microsoft\BizTalk Server\3.0" "/grant=\<BAM WebService Account\>”</span></span>  
  
    > [!NOTE]
    >  <span data-ttu-id="6e9c0-173">このコマンドの目的は、BAM 管理 Web サービス ユーザー アカウントに SOFTWARE\Microsoft\BizTalk Server\3.0\BAM\WebServices\Identity レジストリ キーへの読み取りアクセスを与えることです。</span><span class="sxs-lookup"><span data-stu-id="6e9c0-173">The purpose of this command is to grant the BAM Management Web Service User account read access to the SOFTWARE\Microsoft\BizTalk Server\3.0\BAM\WebServices\Identity registry key.</span></span>  
  
17. <span data-ttu-id="6e9c0-174">BAMManagement Web サービスが実行されるアプリケーション プールで ASPNET_SETREG キーにアクセスできることを確認します。</span><span class="sxs-lookup"><span data-stu-id="6e9c0-174">Verify that the identity that the application pool that the BAMManagement Web service runs under has read access to the ASPNET_SETREG key.</span></span>  
  
18. <span data-ttu-id="6e9c0-175">コンピューターの管理ツールを使用して、IIS ワーカー プロセス グループ (IIS_WPG) および SharePoint Services グループ (STS_WPG) に、BAM 管理 Web サービス ユーザー アカウントと BAM アプリケーション プール ユーザー アカウントを追加します。</span><span class="sxs-lookup"><span data-stu-id="6e9c0-175">Use the Computer Management administrator tool to add the BAM Management Web service user and the BAM application pool user account to the IIS Worker Process Group (IIS_WPG) and SharePoint services group (STS_WPG).</span></span>  
  
19. <span data-ttu-id="6e9c0-176">アプリケーション プールと Web サービスのユーザーの一時 ASP.NET フォルダーに対するアクセス許可を設定します。 c:\windows\system32\cacls"%windir%\Microsoft.NET\Framework\ バージョン 2.0。\<最小のバージョン番号\>\Temporary ASP.NET Files"/T/E/G \<BAM web サービス アカウント\>: F</span><span class="sxs-lookup"><span data-stu-id="6e9c0-176">Set the permissions on the temporary ASP.NET folders for the applications pool and Web service users: c:\windows\system32\cacls "%windir%\Microsoft.NET\Framework\ v2.0.\<min version number\>\Temporary ASP.NET Files" /T /E /G \<BAM WebService Account\>:F</span></span>  
  
    > [!NOTE]
    >  <span data-ttu-id="6e9c0-177">BAM 管理 Web サービス ユーザー アカウントと BAM アプリケーション プール ユーザー アカウントの両方にアクセス権限を与えてください。</span><span class="sxs-lookup"><span data-stu-id="6e9c0-177">You grant access to both the BAM Management Web Service User account and the BAM App Pool User account.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="6e9c0-178">参照</span><span class="sxs-lookup"><span data-stu-id="6e9c0-178">See Also</span></span>  
 [<span data-ttu-id="6e9c0-179">BAM ポータルの管理</span><span class="sxs-lookup"><span data-stu-id="6e9c0-179">Managing the BAM Portal</span></span>](../core/managing-the-bam-portal.md)