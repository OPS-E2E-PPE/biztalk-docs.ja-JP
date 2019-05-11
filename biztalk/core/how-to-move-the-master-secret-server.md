---
title: マスター シークレット サーバーを移動する方法 |Microsoft Docs
ms.custom: ''
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: ''
ms.suite: ''
ms.tgt_pltfrm: ''
ms.topic: article
helpviewer_keywords:
- managing [Master Secret server], migrating
- migrating, Master Secret server
- Master Secret server, migrating
ms.assetid: 2bc5137e-f81d-486d-bb91-7c5981896f79
caps.latest.revision: 20
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: b71ee8252d0a268bb3d087f53607c8a58e831c85
ms.sourcegitcommit: 381e83d43796a345488d54b3f7413e11d56ad7be
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 05/07/2019
ms.locfileid: "65384484"
---
# <a name="how-to-move-the-master-secret-server"></a><span data-ttu-id="b19be-102">マスター シークレット サーバーを移動する方法</span><span class="sxs-lookup"><span data-stu-id="b19be-102">How to Move the Master Secret Server</span></span>
<span data-ttu-id="b19be-103">このトピックでは、別のサーバーに、1 つのサーバーから Windows Server クラスターにマスター シークレットを移動する手順からマスター シークレットを移動する手順を説明します。</span><span class="sxs-lookup"><span data-stu-id="b19be-103">This topic documents the steps you can follow to move the master secret from one server to another and the steps you can follow to move the master secret from one server to a Windows Server Cluster.</span></span>  
  
### <a name="to-move-the-master-secret-from-one-server-to-another-server"></a><span data-ttu-id="b19be-104">1 つのサーバーから別のサーバーにマスター シークレットを移動するには</span><span class="sxs-lookup"><span data-stu-id="b19be-104">To move the master secret from one server to another server</span></span>  
  
1.  <span data-ttu-id="b19be-105">インストールされていない場合は、Microsoft エンタープライズ シングル サインオン (SSO) サーバーを新しいマスター シークレット サーバーにインストールします。</span><span class="sxs-lookup"><span data-stu-id="b19be-105">Install Microsoft Enterprise Single Sign-On (SSO) Server on the new master secret server if it is not already installed.</span></span> <span data-ttu-id="b19be-106">BizTalk Server の CD の \Platform\SSO\setup.exe から Microsoft エンタープライズ シングル サインオン サーバーのセットアップを起動します。</span><span class="sxs-lookup"><span data-stu-id="b19be-106">Launch Microsoft Enterprise Single Sign-On Server setup from \Platform\SSO\setup.exe on the BizTalk Server CD.</span></span>  
  
2.  <span data-ttu-id="b19be-107">構成されていない場合は、新しいマスター シークレット サーバーでエンタープライズ SSO を構成します。</span><span class="sxs-lookup"><span data-stu-id="b19be-107">Configure Enterprise SSO on the new master secret server if it is not already configured.</span></span> <span data-ttu-id="b19be-108">エンタープライズ SSO を構成するこれらの手順に従います。</span><span class="sxs-lookup"><span data-stu-id="b19be-108">Follow these steps to configure Enterprise SSO:</span></span>  
  
    1.  <span data-ttu-id="b19be-109">構成ツールを開きます。</span><span class="sxs-lookup"><span data-stu-id="b19be-109">Open the Configuration tool.</span></span> <span data-ttu-id="b19be-110">既定では、構成ツールはある\<ドライブ\>: \Program Files\Common \enterprise シングル サインオン On\Configuration.exe します。</span><span class="sxs-lookup"><span data-stu-id="b19be-110">By default, the configuration tool is located at \<drive\>:\Program Files\Common Files\Enterprise Single Sign-On\Configuration.exe.</span></span>  
  
    2.  <span data-ttu-id="b19be-111">クリックして選択**エンタープライズ SSO**左側のウィンドウでします。</span><span class="sxs-lookup"><span data-stu-id="b19be-111">Click to select **Enterprise SSO** in the left pane.</span></span>  
  
    3.  <span data-ttu-id="b19be-112">次のチェック ボックスをオン**を有効にするエンタープライズ シングル サインオン コンピューターこの**右側のウィンドウで。</span><span class="sxs-lookup"><span data-stu-id="b19be-112">Select the check box next to **Enable Enterprise Single Sign-On on this computer** in the right pane.</span></span>  
  
    4.  <span data-ttu-id="b19be-113">オプションをクリックして**既存の SSO システムに参加**します。</span><span class="sxs-lookup"><span data-stu-id="b19be-113">Click the option to **Join an existing SSO System**.</span></span>  
  
    5.  <span data-ttu-id="b19be-114">既存の指定**サーバー名**と**データベース名**sso データベース オプション。</span><span class="sxs-lookup"><span data-stu-id="b19be-114">Specify the existing **Server Name** and **Database Name** for the SSO database options.</span></span>  
  
    6.  <span data-ttu-id="b19be-115">既存のエンタープライズ SSO サービス アカウントを指定、 **Windows サービスのエンタープライズのシングル サインオン サーバー**オプション。</span><span class="sxs-lookup"><span data-stu-id="b19be-115">Specify the existing Enterprise SSO service account for the **Enterprise Single Sign-On Server for the Windows Service** option.</span></span>  
  
        > [!NOTE]
        >  <span data-ttu-id="b19be-116">これには、ドメイン アカウントがあります。</span><span class="sxs-lookup"><span data-stu-id="b19be-116">This must be a domain account.</span></span>  
  
    7.  <span data-ttu-id="b19be-117">オプションをクリックして**構成の適用** をクリック**構成**構成ウィザード ダイアログ ボックスの構成を完了します。</span><span class="sxs-lookup"><span data-stu-id="b19be-117">Click the option to **Apply Configuration** and click **Configure** in the Configuration Wizard dialog box to complete the configuration.</span></span>  
  
    8.  <span data-ttu-id="b19be-118">クリックして**完了**構成ツールを閉じます。</span><span class="sxs-lookup"><span data-stu-id="b19be-118">Click **Finish** and close the Configuration tool.</span></span>  
  
3.  <span data-ttu-id="b19be-119">次の手順では、既存のマスター シークレットをバックアップする[バックアップ マスター シークレットを方法](../core/how-to-back-up-the-master-secret.md)します。</span><span class="sxs-lookup"><span data-stu-id="b19be-119">Back up the existing master secret following the steps in [How to Back Up the Master Secret](../core/how-to-back-up-the-master-secret.md).</span></span>  
  
4.  <span data-ttu-id="b19be-120">新しいマスター シークレット サーバーを参照する SSO データベースのマスター シークレット サーバー名を変更します。</span><span class="sxs-lookup"><span data-stu-id="b19be-120">Change the master secret server name in the SSO database to reference the new master secret server.</span></span> <span data-ttu-id="b19be-121">たとえば、新しいマスター シークレット サーバーの名前があります**NewMSSServer**します。</span><span class="sxs-lookup"><span data-stu-id="b19be-121">For example, the name of the new master secret server may be **NewMSSServer**.</span></span> <span data-ttu-id="b19be-122">これを行うには、元のマスター シークレット サーバーで次の手順に従います。</span><span class="sxs-lookup"><span data-stu-id="b19be-122">To do this, follow these steps on the original master secret server:</span></span>  
  
    1.  <span data-ttu-id="b19be-123">Notepad.exe などのテキスト エディターで、次のコードを貼り付けます。</span><span class="sxs-lookup"><span data-stu-id="b19be-123">Paste the following code in a text editor such as notepad.exe:</span></span>  
  
        ```  
        <sso>  
        <globalInfo>  
        <secretServer>NewMSSServer</secretServer>  
        </globalInfo>  
        </sso>  
        ```  
  
    2.  <span data-ttu-id="b19be-124">.Xml ファイルとして保存します。</span><span class="sxs-lookup"><span data-stu-id="b19be-124">Save the file as .xml file.</span></span> <span data-ttu-id="b19be-125">たとえば、ファイルを保存**NewMSSServer.xml**します。</span><span class="sxs-lookup"><span data-stu-id="b19be-125">For example, save the file as **NewMSSServer.xml**.</span></span>  
  
    3.  <span data-ttu-id="b19be-126">コマンド プロンプトで、エンタープライズ SSO のインストール フォルダーに変更します。</span><span class="sxs-lookup"><span data-stu-id="b19be-126">At a command prompt, change to the Enterprise SSO installation folder.</span></span> <span data-ttu-id="b19be-127">インストール フォルダーは、既定では、\<ドライブ\>: \Program Files\Common \enterprise シングル サインオンします。</span><span class="sxs-lookup"><span data-stu-id="b19be-127">By default, the installation folder is \<drive\>:\Program Files\Common Files\Enterprise Single Sign-On.</span></span>  
  
    4.  <span data-ttu-id="b19be-128">型**ssomanage-updatedb** *XMLFile*データベースのマスター シークレット サーバー名を更新します。</span><span class="sxs-lookup"><span data-stu-id="b19be-128">Type **ssomanage -updatedb** *XMLFile* to update the master secret server name in the database.</span></span>  
  
        > [!NOTE]
        >  <span data-ttu-id="b19be-129">置換*XMLFile*保存した .xml ファイルの名前に置き換えます。</span><span class="sxs-lookup"><span data-stu-id="b19be-129">Replace *XMLFile* with the name of the .xml file that you saved.</span></span>  
  
        > [!NOTE]
        >  <span data-ttu-id="b19be-130">ユーザー アカウント制御 (UAC) をサポートするシステムでは、管理者特権を使用してこのツールを実行することが必要な場合があります。</span><span class="sxs-lookup"><span data-stu-id="b19be-130">On a system that supports User Account Control (UAC), you may need to run the tool with Administrative privileges.</span></span>  
  
5.  <span data-ttu-id="b19be-131">新しいマスター シークレット サーバーでエンタープライズ シングル サインオン サービスを再起動します。</span><span class="sxs-lookup"><span data-stu-id="b19be-131">Restart the Enterprise Single Sign-On service on the new master secret server.</span></span>  
  
6.  <span data-ttu-id="b19be-132">次の手順に従って、新しいマスター シークレット サーバー上にマスター シークレットをバックアップを復元[マスター シークレットを復元する方法](../core/how-to-restore-the-master-secret.md)新しいマスター シークレット サーバーでします。</span><span class="sxs-lookup"><span data-stu-id="b19be-132">Restore the backed-up master secret onto the new master secret server by following the steps in [How to Restore the Master Secret](../core/how-to-restore-the-master-secret.md) on the new master secret server.</span></span>  
  
### <a name="to-move-the-master-secret-from-one-server-to-a-windows-server-cluster"></a><span data-ttu-id="b19be-133">1 つのサーバーから Windows Server クラスターにマスター シークレットを移動するには</span><span class="sxs-lookup"><span data-stu-id="b19be-133">To move the master secret from one server to a Windows Server Cluster</span></span>  
  
1.  <span data-ttu-id="b19be-134">インストールし、次の手順に従って、Windows Server クラスターで、エンタープライズ SSO サービスを構成[マスター シークレット サーバーをクラスター化する方法](../core/how-to-cluster-the-master-secret-server1.md)します。</span><span class="sxs-lookup"><span data-stu-id="b19be-134">Install and configure the Enterprise SSO service on a Windows Server cluster by following the steps in [How to Cluster the Master Secret Server](../core/how-to-cluster-the-master-secret-server1.md).</span></span> <span data-ttu-id="b19be-135">すべての記載された手順以外には、このトピックの手順、 **2 番目のクラスター ノードでマスター シークレットを復元**セクション。</span><span class="sxs-lookup"><span data-stu-id="b19be-135">Complete all of the steps in this topic except for the steps described in the **Restore the master secret on the second cluster node** section.</span></span> <span data-ttu-id="b19be-136">既存のマスター シークレット サーバーをクラスターに移動するためにオプションを選択しないでください**新しい SSO システムを作成する**クラスター ノードにエンタープライズ SSO を構成するときにします。</span><span class="sxs-lookup"><span data-stu-id="b19be-136">Since you will be moving the existing master secret server to the cluster do not choose the option to **Create a new SSO system** when configuring Enterprise SSO on the cluster nodes.</span></span> <span data-ttu-id="b19be-137">各クラスター ノードを構成する場合は、BizTalk Server 構成プログラムで、エンタープライズ SSO 機能の次のオプションを設定します。</span><span class="sxs-lookup"><span data-stu-id="b19be-137">When configuring each cluster node, set the following options for the Enterprise SSO feature in the BizTalk Server Configuration program:</span></span>  
  
    1.  <span data-ttu-id="b19be-138">次に、ボックスをオン**を有効にするエンタープライズ シングル サインオン コンピューターこの**します。</span><span class="sxs-lookup"><span data-stu-id="b19be-138">Check the box next to **Enable Enterprise Single Sign-On on this computer**.</span></span>  
  
    2.  <span data-ttu-id="b19be-139">オプションをクリックして**既存の SSO システムに参加**します。</span><span class="sxs-lookup"><span data-stu-id="b19be-139">Click the option to **Join an existing SSO system**.</span></span>  
  
    3.  <span data-ttu-id="b19be-140">既存の SSO データベース サーバー名とデータベース名の値を入力します。</span><span class="sxs-lookup"><span data-stu-id="b19be-140">Enter values for the existing SSO Database Server Name and Database Name.</span></span>  
  
    4.  <span data-ttu-id="b19be-141">エンタープライズ シングル サインオン サービスを使用するアカウントを指定するときに、既存の SSO サービス アカウントを入力します。</span><span class="sxs-lookup"><span data-stu-id="b19be-141">Enter the existing SSO Service account when specifying the account to use for the Enterprise Single Sign-On Service.</span></span>  
  
2.  <span data-ttu-id="b19be-142">既存のマスター シークレット バックアップ ファイルを各クラスター ノードの \Enterprise でシングル サインオン フォルダーにコピーします。</span><span class="sxs-lookup"><span data-stu-id="b19be-142">Copy the existing master secret backup file to the \Enterprise Single Sign-On folder on each cluster node.</span></span>  
  
3.  <span data-ttu-id="b19be-143">この Windows Server クラスターが 1 つまたは複数のクラスター化された BizTalk ホストをホストする場合は、ssomanage コマンド ライン ユーティリティを使用したクラスター化されたマスター シークレット サーバーにすべてのユーザーの SSO サーバー名を設定します。</span><span class="sxs-lookup"><span data-stu-id="b19be-143">If this Windows Server Cluster will host one or more clustered BizTalk hosts, set the SSO Server name for all users to the clustered master secret server with the ssomanage command line utility.</span></span> <span data-ttu-id="b19be-144">このコマンドは、エンタープライズ SSO のインストール フォルダーから、グループ内の各 BizTalk サーバーで実行する必要があります。</span><span class="sxs-lookup"><span data-stu-id="b19be-144">This command should be run from the Enterprise SSO installation folder on each BizTalk Server in the group.</span></span> <span data-ttu-id="b19be-145">たとえば、次のコマンドラインは、クラスター化されたマスター シークレット サーバーにすべてのユーザーの SSO サーバー名を設定します。</span><span class="sxs-lookup"><span data-stu-id="b19be-145">For example, the following command line will set the SSO Server name for all users to the clustered master secret server:</span></span>  
  
    ```  
    ssomanage -serverall SSOCLUSTER  
    ```  
  
    > [!NOTE]
    >  <span data-ttu-id="b19be-146">*SSOCLUSTER*はこのシナリオをクラスター化されたマスター シークレット サーバーのリソースを含むクラスター グループに作成されるリソースの名前は実際のネットワークのプレース ホルダー、すべての BizTalk ホストを同じクラスター リソースとして作成する必要がありますクラスター化されたエンタープライズ SSO サービス リソースとクラスター グループ。</span><span class="sxs-lookup"><span data-stu-id="b19be-146">*SSOCLUSTER* is a placeholder for the actual network name resource that is created in the cluster group that contains the clustered master secret server resourceIn this scenario, all BizTalk hosts must be created as cluster resources in the same cluster group as the clustered Enterprise SSO service resource.</span></span> <span data-ttu-id="b19be-147">エンタープライズ SSO サービスがクラスター化された Windows Server クラスター ノードの非クラスター化 BizTalk ホスト インスタンスを実行することは、サポートされる構成ではありません。</span><span class="sxs-lookup"><span data-stu-id="b19be-147">Running a non-clustered BizTalk host instance on a Windows Server Cluster node where the Enterprise SSO service is clustered is not a supported configuration.</span></span> <span data-ttu-id="b19be-148">これは、クラスター化されたエンタープライズ SSO サービスは、SSO サービス上の BizTalk ホスト インスタンスの依存関係のための別のノードにフェールオーバーしたときに、非クラスター化 BizTalk ホスト インスタンスが失敗するためです。</span><span class="sxs-lookup"><span data-stu-id="b19be-148">This is because the non-clustered BizTalk host instance will fail when the clustered Enterprise SSO service is failed over to another node due to the dependency of a BizTalk host instance on the SSO service.</span></span>  
  
    > [!NOTE]
    >  <span data-ttu-id="b19be-149">ユーザー アカウント制御 (UAC) をサポートするシステムでは、管理者特権を使用してこのツールを実行することが必要な場合があります。</span><span class="sxs-lookup"><span data-stu-id="b19be-149">On a system that supports User Account Control (UAC), you may need to run the tool with Administrative privileges.</span></span>  
  
4.  <span data-ttu-id="b19be-150">クラスター アドミニストレーターでは、クラスター化されたエンタープライズ SSO サービス リソースを含むクラスター グループを右クリックし、クリックして**オンライン**クラスター グループ内のすべてのリソースを開始します。</span><span class="sxs-lookup"><span data-stu-id="b19be-150">In Cluster Administrator, right-click the cluster group that contains the clustered Enterprise SSO service resource, and click **Bring Online** to start all of the resources in the cluster group.</span></span>  
  
5.  <span data-ttu-id="b19be-151">この Windows Server クラスターをホストする 1 つまたは複数のクラスター化された BizTalk ホストは、更新で、SSO サーバー名、 **BizTalk グループのプロパティ**クラスター化されたマスター シークレット サーバーを参照するページ。</span><span class="sxs-lookup"><span data-stu-id="b19be-151">If this Windows Server Cluster will host one or more clustered BizTalk hosts, update the SSO Server name accessible in the **BizTalk Group Properties** page to reference the clustered master secret server.</span></span> <span data-ttu-id="b19be-152">起動**BizTalk Server 管理**を BizTalk グループを右クリックし、**プロパティ**項目、メニューのエントリを更新**SSO サーバー名**をクリックします。**[Ok]** します。</span><span class="sxs-lookup"><span data-stu-id="b19be-152">Launch **BizTalk Server Administration**, right-click the BizTalk Group and select the **Properties** menu item, then update the entry for **SSO Server name** and click **OK**.</span></span>  
  
    > [!NOTE]
    >  <span data-ttu-id="b19be-153">このシナリオでは、クラスター化されたエンタープライズ SSO サービス リソースと同じクラスター グループ内のクラスター リソースとしてすべての BizTalk ホストを作成する必要があります。</span><span class="sxs-lookup"><span data-stu-id="b19be-153">In this scenario, all BizTalk hosts must be created as cluster resources in the same cluster group as the clustered Enterprise SSO service resource.</span></span> <span data-ttu-id="b19be-154">エンタープライズ SSO サービスがクラスター化された Windows Server クラスター ノードの非クラスター化 BizTalk ホスト インスタンスを実行することは、サポートされる構成ではありません。</span><span class="sxs-lookup"><span data-stu-id="b19be-154">Running a non-clustered BizTalk host instance on a Windows Server Cluster node where the Enterprise SSO service is clustered is not a supported configuration.</span></span> <span data-ttu-id="b19be-155">これは、クラスター化されたエンタープライズ SSO サービスは、SSO サービス上の BizTalk ホスト インスタンスの依存関係のための別のノードにフェールオーバーしたときに、非クラスター化 BizTalk ホスト インスタンスが失敗するためです。</span><span class="sxs-lookup"><span data-stu-id="b19be-155">This is because the non-clustered BizTalk host instance will fail when the clustered Enterprise SSO service is failed over to another node due to the dependency of a BizTalk host instance on the SSO service.</span></span>  
  
6.  <span data-ttu-id="b19be-156">エンタープライズ SSO サービスのクラスター化されたインスタンスを右クリックし、をクリックして**オフライン**、エンタープライズ SSO サービスのクラスター化されたインスタンスを右クリックしておよびクリックして**オンライン**します。</span><span class="sxs-lookup"><span data-stu-id="b19be-156">Right-click the clustered instance of the Enterprise SSO service and click **Take Offline**, then right-click the clustered instance of the Enterprise SSO service and click **Bring Online**.</span></span>  
  
    > [!NOTE]
    >  <span data-ttu-id="b19be-157">この手順を完了していない場合、マスター シークレットを復元する際は成功しません。</span><span class="sxs-lookup"><span data-stu-id="b19be-157">If this step is not completed, attempts to restore the master secret may not succeed.</span></span>  
  
7.  <span data-ttu-id="b19be-158">クラスター化されたマスター シークレット サーバーをホストしている Windows クラスターの各ノードでバックアップされたマスター シークレットを復元します。</span><span class="sxs-lookup"><span data-stu-id="b19be-158">Restore the backed-up master secret on each node of the Windows cluster that houses the clustered master secret server.</span></span> <span data-ttu-id="b19be-159">次の手順では、[マスター シークレットを復元する方法](../core/how-to-restore-the-master-secret.md)クラスター化されたマスター シークレット サーバーをホストしている Windows クラスターの各ノードにします。</span><span class="sxs-lookup"><span data-stu-id="b19be-159">Follow the steps in [How to Restore the Master Secret](../core/how-to-restore-the-master-secret.md) on each node of the Windows cluster that houses the clustered master secret server.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="b19be-160">参照</span><span class="sxs-lookup"><span data-stu-id="b19be-160">See Also</span></span>  
 [<span data-ttu-id="b19be-161">マスター シークレットの管理</span><span class="sxs-lookup"><span data-stu-id="b19be-161">Managing the Master Secret</span></span>](../core/managing-the-master-secret.md)