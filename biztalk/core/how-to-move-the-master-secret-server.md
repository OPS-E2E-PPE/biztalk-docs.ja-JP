---
title: "マスター シークレット サーバーを移動する方法 |Microsoft ドキュメント"
ms.custom: 
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: 
ms.suite: 
ms.tgt_pltfrm: 
ms.topic: article
helpviewer_keywords:
- managing [Master Secret server], migrating
- migrating, Master Secret server
- Master Secret server, migrating
ms.assetid: 2bc5137e-f81d-486d-bb91-7c5981896f79
caps.latest.revision: "20"
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: 8b35fae6551a95c1c2009ac9786aa791d189f338
ms.sourcegitcommit: cb908c540d8f1a692d01dc8f313e16cb4b4e696d
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 09/20/2017
---
# <a name="how-to-move-the-master-secret-server"></a><span data-ttu-id="50081-102">マスター シークレット サーバーを移動する方法</span><span class="sxs-lookup"><span data-stu-id="50081-102">How to Move the Master Secret Server</span></span>
<span data-ttu-id="50081-103">このトピックでは、マスター シークレットをあるサーバーから別のサーバーに移動するための手順、およびマスター シークレットをあるサーバーから Windows Server クラスターに移動するための手順について説明します。</span><span class="sxs-lookup"><span data-stu-id="50081-103">This topic documents the steps you can follow to move the master secret from one server to another and the steps you can follow to move the master secret from one server to a Windows Server Cluster.</span></span>  
  
### <a name="to-move-the-master-secret-from-one-server-to-another-server"></a><span data-ttu-id="50081-104">マスター シークレットをあるサーバーから別のサーバーに移動するには</span><span class="sxs-lookup"><span data-stu-id="50081-104">To move the master secret from one server to another server</span></span>  
  
1.  <span data-ttu-id="50081-105">新しいマスター シークレット サーバーに Microsoft エンタープライズ シングル サインオン (SSO) サーバーがインストールされていない場合はインストールします。</span><span class="sxs-lookup"><span data-stu-id="50081-105">Install Microsoft Enterprise Single Sign-On (SSO) Server on the new master secret server if it is not already installed.</span></span> <span data-ttu-id="50081-106">Microsoft エンタープライズ シングル サインオン サーバーのセットアップは、[!INCLUDE[btsBizTalkServer2006r3](../includes/btsbiztalkserver2006r3-md.md)] CD-ROM の \Platform\SSO\setup.exe から起動します。</span><span class="sxs-lookup"><span data-stu-id="50081-106">Launch Microsoft Enterprise Single Sign-On Server setup from \Platform\SSO\setup.exe on the [!INCLUDE[btsBizTalkServer2006r3](../includes/btsbiztalkserver2006r3-md.md)] CD.</span></span>  
  
2.  <span data-ttu-id="50081-107">新しいマスター シークレット サーバーでエンタープライズ SSO が構成されていない場合は構成します。</span><span class="sxs-lookup"><span data-stu-id="50081-107">Configure Enterprise SSO on the new master secret server if it is not already configured.</span></span> <span data-ttu-id="50081-108">エンタープライズ SSO を構成するには、次の手順を実行します。</span><span class="sxs-lookup"><span data-stu-id="50081-108">Follow these steps to configure Enterprise SSO:</span></span>  
  
    1.  <span data-ttu-id="50081-109">構成ツールを起動します。</span><span class="sxs-lookup"><span data-stu-id="50081-109">Open the Configuration tool.</span></span> <span data-ttu-id="50081-110">既定では、構成ツールにある\<ドライブ >: \program files \common files \enterprise Single sign-on On\Configuration.exe です。</span><span class="sxs-lookup"><span data-stu-id="50081-110">By default, the configuration tool is located at \<drive>:\Program Files\Common Files\Enterprise Single Sign-On\Configuration.exe.</span></span>  
  
    2.  <span data-ttu-id="50081-111">クリックして選択**エンタープライズ SSO**左側のウィンドウでします。</span><span class="sxs-lookup"><span data-stu-id="50081-111">Click to select **Enterprise SSO** in the left pane.</span></span>  
  
    3.  <span data-ttu-id="50081-112">次のチェック ボックスをオン**を有効にするエンタープライズ シングル サインオンこのコンピューターに**右側のウィンドウでします。</span><span class="sxs-lookup"><span data-stu-id="50081-112">Select the check box next to **Enable Enterprise Single Sign-On on this computer** in the right pane.</span></span>  
  
    4.  <span data-ttu-id="50081-113">オプションをクリックして**既存の SSO システムに参加**です。</span><span class="sxs-lookup"><span data-stu-id="50081-113">Click the option to **Join an existing SSO System**.</span></span>  
  
    5.  <span data-ttu-id="50081-114">既存の指定**サーバー名**と**データベース名**SSO データベースのオプションです。</span><span class="sxs-lookup"><span data-stu-id="50081-114">Specify the existing **Server Name** and **Database Name** for the SSO database options.</span></span>  
  
    6.  <span data-ttu-id="50081-115">既存のエンタープライズ SSO サービス アカウントを指定、**エンタープライズ シングル サインオン サーバーの Windows サービスの**オプション。</span><span class="sxs-lookup"><span data-stu-id="50081-115">Specify the existing Enterprise SSO service account for the **Enterprise Single Sign-On Server for the Windows Service** option.</span></span>  
  
        > [!NOTE]
        >  <span data-ttu-id="50081-116">これは、ドメイン アカウントである必要があります。</span><span class="sxs-lookup"><span data-stu-id="50081-116">This must be a domain account.</span></span>  
  
    7.  <span data-ttu-id="50081-117">オプションをクリックして**構成の適用** をクリック**構成**構成ウィザード ダイアログ ボックスで、構成を完了します。</span><span class="sxs-lookup"><span data-stu-id="50081-117">Click the option to **Apply Configuration** and click **Configure** in the Configuration Wizard dialog box to complete the configuration.</span></span>  
  
    8.  <span data-ttu-id="50081-118">をクリックして**完了**し、構成ツールを閉じます。</span><span class="sxs-lookup"><span data-stu-id="50081-118">Click **Finish** and close the Configuration tool.</span></span>  
  
3.  <span data-ttu-id="50081-119">」の手順に従って、既存のマスター シークレットをバックアップ[バックアップ マスター シークレットを方法](../core/how-to-back-up-the-master-secret.md)です。</span><span class="sxs-lookup"><span data-stu-id="50081-119">Back up the existing master secret following the steps in [How to Back Up the Master Secret](../core/how-to-back-up-the-master-secret.md).</span></span>  
  
4.  <span data-ttu-id="50081-120">新しいマスター シークレット サーバーを参照するように、SSO データベースのマスター シークレット サーバー名を変更します。</span><span class="sxs-lookup"><span data-stu-id="50081-120">Change the master secret server name in the SSO database to reference the new master secret server.</span></span> <span data-ttu-id="50081-121">たとえば、新しいマスター シークレット サーバーの名前があります**NewMSSServer**です。</span><span class="sxs-lookup"><span data-stu-id="50081-121">For example, the name of the new master secret server may be **NewMSSServer**.</span></span> <span data-ttu-id="50081-122">SSO データベースのマスター シークレット サーバー名を変更するには、元のマスター シークレット サーバーで次の手順を実行します。</span><span class="sxs-lookup"><span data-stu-id="50081-122">To do this, follow these steps on the original master secret server:</span></span>  
  
    1.  <span data-ttu-id="50081-123">notepad.exe などのテキスト エディターに次のコードを貼り付けます。</span><span class="sxs-lookup"><span data-stu-id="50081-123">Paste the following code in a text editor such as notepad.exe:</span></span>  
  
        ```  
        <sso>  
        <globalInfo>  
        <secretServer>NewMSSServer</secretServer>  
        </globalInfo>  
        </sso>  
        ```  
  
    2.  <span data-ttu-id="50081-124">ファイルを .xml ファイルとして保存します。</span><span class="sxs-lookup"><span data-stu-id="50081-124">Save the file as .xml file.</span></span> <span data-ttu-id="50081-125">たとえば、としてファイルを保存**NewMSSServer.xml**です。</span><span class="sxs-lookup"><span data-stu-id="50081-125">For example, save the file as **NewMSSServer.xml**.</span></span>  
  
    3.  <span data-ttu-id="50081-126">コマンド プロンプトで、エンタープライズ SSO のインストール フォルダーに移動します。</span><span class="sxs-lookup"><span data-stu-id="50081-126">At a command prompt, change to the Enterprise SSO installation folder.</span></span> <span data-ttu-id="50081-127">インストール フォルダーは、既定では、\<ドライブ >: \program files \common files \enterprise シングル サインオンします。</span><span class="sxs-lookup"><span data-stu-id="50081-127">By default, the installation folder is \<drive>:\Program Files\Common Files\Enterprise Single Sign-On.</span></span>  
  
    4.  <span data-ttu-id="50081-128">型**ssomanage-updatedb** *XMLFile*データベースのマスター シークレット サーバー名を更新します。</span><span class="sxs-lookup"><span data-stu-id="50081-128">Type **ssomanage -updatedb** *XMLFile* to update the master secret server name in the database.</span></span>  
  
        > [!NOTE]
        >  <span data-ttu-id="50081-129">置き換える*XMLFile*保存した .xml ファイルの名前に置き換えます。</span><span class="sxs-lookup"><span data-stu-id="50081-129">Replace *XMLFile* with the name of the .xml file that you saved.</span></span>  
  
        > [!NOTE]
        >  <span data-ttu-id="50081-130">ユーザー アカウント制御 (UAC) をサポートするシステムでは、管理者特権を使用してこのツールを実行することが必要な場合があります。</span><span class="sxs-lookup"><span data-stu-id="50081-130">On a system that supports User Account Control (UAC), you may need to run the tool with Administrative privileges.</span></span>  
  
5.  <span data-ttu-id="50081-131">新しいマスター シークレット サーバーで、エンタープライズ シングル サインオン サービスを再開します。</span><span class="sxs-lookup"><span data-stu-id="50081-131">Restart the Enterprise Single Sign-On service on the new master secret server.</span></span>  
  
6.  <span data-ttu-id="50081-132">次の手順に従って、新しいマスター シークレット サーバー上にバックアップしたマスター シークレットを復元[マスター シークレットを復元する方法](../core/how-to-restore-the-master-secret.md)新しいマスター シークレット サーバーでします。</span><span class="sxs-lookup"><span data-stu-id="50081-132">Restore the backed-up master secret onto the new master secret server by following the steps in [How to Restore the Master Secret](../core/how-to-restore-the-master-secret.md) on the new master secret server.</span></span>  
  
### <a name="to-move-the-master-secret-from-one-server-to-a-windows-server-cluster"></a><span data-ttu-id="50081-133">マスター シークレットをサーバーから Windows Server クラスターに移動するには</span><span class="sxs-lookup"><span data-stu-id="50081-133">To move the master secret from one server to a Windows Server Cluster</span></span>  
  
1.  <span data-ttu-id="50081-134">インストールし、次の手順に従って、Windows Server クラスターで、エンタープライズ SSO サービスを構成する[マスター シークレット サーバーをクラスター化する方法](../core/how-to-cluster-the-master-secret-server1.md)です。</span><span class="sxs-lookup"><span data-stu-id="50081-134">Install and configure the Enterprise SSO service on a Windows Server cluster by following the steps in [How to Cluster the Master Secret Server](../core/how-to-cluster-the-master-secret-server1.md).</span></span> <span data-ttu-id="50081-135">すべての手順で説明する手順は除くには、このトピックで、 **2 番目のクラスター ノードでマスター シークレットを復元**セクションです。</span><span class="sxs-lookup"><span data-stu-id="50081-135">Complete all of the steps in this topic except for the steps described in the **Restore the master secret on the second cluster node** section.</span></span> <span data-ttu-id="50081-136">既存のマスター シークレット サーバーをクラスターに移動するためにオプションを選択しない**新しい SSO システムを作成する**クラスター ノードにエンタープライズ SSO を構成するときにします。</span><span class="sxs-lookup"><span data-stu-id="50081-136">Since you will be moving the existing master secret server to the cluster do not choose the option to **Create a new SSO system** when configuring Enterprise SSO on the cluster nodes.</span></span> <span data-ttu-id="50081-137">各クラスター ノードを構成する際に、BizTalk Server 構成プログラムで、エンタープライズ SSO の機能に対して、次のオプションを設定します。</span><span class="sxs-lookup"><span data-stu-id="50081-137">When configuring each cluster node, set the following options for the Enterprise SSO feature in the BizTalk Server Configuration program:</span></span>  
  
    1.  <span data-ttu-id="50081-138">横にチェック ボックスをオン**を有効にするエンタープライズ シングル サインオンこのコンピューターに**です。</span><span class="sxs-lookup"><span data-stu-id="50081-138">Check the box next to **Enable Enterprise Single Sign-On on this computer**.</span></span>  
  
    2.  <span data-ttu-id="50081-139">オプションをクリックして**既存の SSO システムに参加**です。</span><span class="sxs-lookup"><span data-stu-id="50081-139">Click the option to **Join an existing SSO system**.</span></span>  
  
    3.  <span data-ttu-id="50081-140">既存の SSO データベース サーバー名およびデータベース名を入力します。</span><span class="sxs-lookup"><span data-stu-id="50081-140">Enter values for the existing SSO Database Server Name and Database Name.</span></span>  
  
    4.  <span data-ttu-id="50081-141">エンタープライズ シングル サインオン サービスに使用するアカウントを指定するときに既存の SSO サービス アカウントを入力します。</span><span class="sxs-lookup"><span data-stu-id="50081-141">Enter the existing SSO Service account when specifying the account to use for the Enterprise Single Sign-On Service.</span></span>  
  
2.  <span data-ttu-id="50081-142">既存のマスター シークレットのバックアップ ファイルを、各クラスター ノードの \Enterprise Single Sign-On フォルダーにコピーします。</span><span class="sxs-lookup"><span data-stu-id="50081-142">Copy the existing master secret backup file to the \Enterprise Single Sign-On folder on each cluster node.</span></span>  
  
3.  <span data-ttu-id="50081-143">この Windows Server クラスターでは、1 つまたは複数のクラスター化された BizTalk ホストをホストする、ssomanage コマンド ライン ユーティリティを使用して、クラスター化されたマスター シークレット サーバーにすべてのユーザーの SSO サーバー名を設定します。</span><span class="sxs-lookup"><span data-stu-id="50081-143">If this Windows Server Cluster will host one or more clustered BizTalk hosts, set the SSO Server name for all users to the clustered master secret server with the ssomanage command line utility.</span></span> <span data-ttu-id="50081-144">このコマンドは、グループ内の BizTalk Server ごとに、エンタープライズ SSO のインストール フォルダーから実行する必要があります。</span><span class="sxs-lookup"><span data-stu-id="50081-144">This command should be run from the Enterprise SSO installation folder on each BizTalk Server in the group.</span></span> <span data-ttu-id="50081-145">たとえば、次のコマンド ラインを使用して、すべてのユーザーの SSO サーバー名をクラスター化されたマスター シークレット サーバーに設定します。</span><span class="sxs-lookup"><span data-stu-id="50081-145">For example, the following command line will set the SSO Server name for all users to the clustered master secret server:</span></span>  
  
    ```  
    ssomanage -serverall SSOCLUSTER  
    ```  
  
    > [!NOTE]
    >  <span data-ttu-id="50081-146">*SSOCLUSTER*は、このシナリオをマスター シークレット サーバーをクラスター化されたリソースを含むクラスター グループに作成されるリソースの名前は、実際のネットワークのプレース ホルダー、すべての BizTalk ホストを同じクラスター リソースとして作成する必要がありますクラスター化されたエンタープライズ SSO サービス リソースとクラスター グループ。</span><span class="sxs-lookup"><span data-stu-id="50081-146">*SSOCLUSTER* is a placeholder for the actual network name resource that is created in the cluster group that contains the clustered master secret server resourceIn this scenario, all BizTalk hosts must be created as cluster resources in the same cluster group as the clustered Enterprise SSO service resource.</span></span> <span data-ttu-id="50081-147">エンタープライズ SSO サービスがクラスター化されていない Windows Server クラスター ノードで、非クラスター化 BizTalk ホスト インスタンスを実行することは、構成上サポートされていません。</span><span class="sxs-lookup"><span data-stu-id="50081-147">Running a non-clustered BizTalk host instance on a Windows Server Cluster node where the Enterprise SSO service is clustered is not a supported configuration.</span></span> <span data-ttu-id="50081-148">これは、SSO サービス上の BizTalk ホスト インスタンスの依存性が原因で、クラスター化されたエンタープライズ SSO サービスが他のノードにフェールオーバーするときに、非クラスター化 BizTalk ホスト インスタンスが失敗するためです。</span><span class="sxs-lookup"><span data-stu-id="50081-148">This is because the non-clustered BizTalk host instance will fail when the clustered Enterprise SSO service is failed over to another node due to the dependency of a BizTalk host instance on the SSO service.</span></span>  
  
    > [!NOTE]
    >  <span data-ttu-id="50081-149">ユーザー アカウント制御 (UAC) をサポートするシステムでは、管理者特権を使用してこのツールを実行することが必要な場合があります。</span><span class="sxs-lookup"><span data-stu-id="50081-149">On a system that supports User Account Control (UAC), you may need to run the tool with Administrative privileges.</span></span>  
  
4.  <span data-ttu-id="50081-150">クラスター アドミニストレーターは、クラスター化されたエンタープライズ SSO サービス リソースを含むクラスター グループを右クリックし、クリックして**オンライン**クラスター グループ内のすべてのリソースを開始します。</span><span class="sxs-lookup"><span data-stu-id="50081-150">In Cluster Administrator, right-click the cluster group that contains the clustered Enterprise SSO service resource, and click **Bring Online** to start all of the resources in the cluster group.</span></span>  
  
5.  <span data-ttu-id="50081-151">この Windows Server クラスターをホストする 1 つまたは複数のクラスター化された BizTalk ホストは、更新で、SSO サーバー名、 **BizTalk グループのプロパティ**クラスター化されたマスター シークレット サーバーを参照するページ。</span><span class="sxs-lookup"><span data-stu-id="50081-151">If this Windows Server Cluster will host one or more clustered BizTalk hosts, update the SSO Server name accessible in the **BizTalk Group Properties** page to reference the clustered master secret server.</span></span> <span data-ttu-id="50081-152">起動**BizTalk Server 管理コンソール**を BizTalk グループを右クリックし、**プロパティ**メニュー更新し、エントリを**SSO サーバー名** をクリック**Ok**です。</span><span class="sxs-lookup"><span data-stu-id="50081-152">Launch **BizTalk Server Administration**, right-click the BizTalk Group and select the **Properties** menu item, then update the entry for **SSO Server name** and click **OK**.</span></span>  
  
    > [!NOTE]
    >  <span data-ttu-id="50081-153">このシナリオでは、クラスター化されたエンタープライズ SSO サービス リソースと同じクラスター グループ内のクラスター リソースとして、すべての BizTalk ホストを作成する必要があります。</span><span class="sxs-lookup"><span data-stu-id="50081-153">In this scenario, all BizTalk hosts must be created as cluster resources in the same cluster group as the clustered Enterprise SSO service resource.</span></span> <span data-ttu-id="50081-154">エンタープライズ SSO サービスがクラスター化されていない Windows Server クラスター ノードで、非クラスター化 BizTalk ホスト インスタンスを実行することは、構成上サポートされていません。</span><span class="sxs-lookup"><span data-stu-id="50081-154">Running a non-clustered BizTalk host instance on a Windows Server Cluster node where the Enterprise SSO service is clustered is not a supported configuration.</span></span> <span data-ttu-id="50081-155">これは、SSO サービス上の BizTalk ホスト インスタンスの依存性が原因で、クラスター化されたエンタープライズ SSO サービスが他のノードにフェールオーバーするときに、非クラスター化 BizTalk ホスト インスタンスが失敗するためです。</span><span class="sxs-lookup"><span data-stu-id="50081-155">This is because the non-clustered BizTalk host instance will fail when the clustered Enterprise SSO service is failed over to another node due to the dependency of a BizTalk host instance on the SSO service.</span></span>  
  
6.  <span data-ttu-id="50081-156">エンタープライズ SSO サービスのクラスター化されたインスタンスを右クリックし、をクリックして**オフライン**、エンタープライズ SSO サービスのクラスター化されたインスタンスを右クリックしてをクリックして**オンライン**です。</span><span class="sxs-lookup"><span data-stu-id="50081-156">Right-click the clustered instance of the Enterprise SSO service and click **Take Offline**, then right-click the clustered instance of the Enterprise SSO service and click **Bring Online**.</span></span>  
  
    > [!NOTE]
    >  <span data-ttu-id="50081-157">この手順を完了していない場合、マスター シークレットを復元する試行が失敗します。</span><span class="sxs-lookup"><span data-stu-id="50081-157">If this step is not completed, attempts to restore the master secret may not succeed.</span></span>  
  
7.  <span data-ttu-id="50081-158">クラスター化されたマスター シークレット サーバーをホストする Windows クラスターの各ノードで、バックアップしておいたマスター シークレットを復元します。</span><span class="sxs-lookup"><span data-stu-id="50081-158">Restore the backed-up master secret on each node of the Windows cluster that houses the clustered master secret server.</span></span> <span data-ttu-id="50081-159">手順に従います[マスター シークレットを復元する方法](../core/how-to-restore-the-master-secret.md)クラスター化されたマスター シークレット サーバーをホストする Windows クラスターの各ノードにします。</span><span class="sxs-lookup"><span data-stu-id="50081-159">Follow the steps in [How to Restore the Master Secret](../core/how-to-restore-the-master-secret.md) on each node of the Windows cluster that houses the clustered master secret server.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="50081-160">参照</span><span class="sxs-lookup"><span data-stu-id="50081-160">See Also</span></span>  
 [<span data-ttu-id="50081-161">マスタ シークレットの管理</span><span class="sxs-lookup"><span data-stu-id="50081-161">Managing the Master Secret</span></span>](../core/managing-the-master-secret.md)