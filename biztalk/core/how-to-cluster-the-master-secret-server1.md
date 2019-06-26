---
title: マスター シークレットの Server1 をクラスター化する方法 |Microsoft Docs
ms.custom: ''
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: ''
ms.suite: ''
ms.tgt_pltfrm: ''
ms.topic: article
helpviewer_keywords:
- Master Secret server, second node
- Master Secret server, restoring
- clustering, Master Secret server
- Master Secret server, clustering
ms.assetid: ef817fa4-e43d-4e3d-8686-5bd675708001
caps.latest.revision: 47
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: 88f7b25a8cf3138862e65f7c8bd96f041fc512d1
ms.sourcegitcommit: 381e83d43796a345488d54b3f7413e11d56ad7be
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 05/07/2019
ms.locfileid: "65386953"
---
# <a name="how-to-cluster-the-master-secret-server"></a><span data-ttu-id="11124-102">マスター シークレット サーバーをクラスター化する方法</span><span class="sxs-lookup"><span data-stu-id="11124-102">How to Cluster the Master Secret Server</span></span>
<span data-ttu-id="11124-103">マスタ シークレット サーバーでエンタープライズ シングル サインオン (SSO) サービスを正常にクラスターのこのセクションの指示に従うことをお勧めします。</span><span class="sxs-lookup"><span data-stu-id="11124-103">We recommended that you follow the instructions in this section to cluster the Enterprise Single Sign-On (SSO) service on the master secret server successfully.</span></span>  
  
 <span data-ttu-id="11124-104">マスター シークレット サーバーをクラスター化するときにシングル サインオン サーバー、マスター シークレット サーバーのアクティブなクラスター化されたインスタンスと通信します。</span><span class="sxs-lookup"><span data-stu-id="11124-104">When you cluster the master secret server, the Single Sign-On servers communicate with the active clustered instance of the master secret server.</span></span> <span data-ttu-id="11124-105">同様に、マスター シークレット サーバーのアクティブなクラスター化されたインスタンスは、SSO データベースと通信します。</span><span class="sxs-lookup"><span data-stu-id="11124-105">Similarly, the active clustered instance of the master secret server communicates with the SSO database.</span></span>  
  
 <span data-ttu-id="11124-106">この手順を実行する SSO 管理者である必要があります。</span><span class="sxs-lookup"><span data-stu-id="11124-106">You must be an SSO administrator to perform this procedure.</span></span>  
  
> [!CAUTION]
>  <span data-ttu-id="11124-107">ネットワーク負荷分散 (NLB) クラスターで、マスター シークレット サーバーをインストールすることはできません。</span><span class="sxs-lookup"><span data-stu-id="11124-107">You cannot install the master secret server on a Network Load Balancing (NLB) cluster.</span></span>  
  
### <a name="to-install-and-configure-enterprise-sso-on-the-cluster-nodes"></a><span data-ttu-id="11124-108">インストールして、クラスター ノードにエンタープライズ SSO を構成するには</span><span class="sxs-lookup"><span data-stu-id="11124-108">To install and configure Enterprise SSO on the cluster nodes</span></span>  
  
1. <span data-ttu-id="11124-109">インストール[!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)]各クラスター ノードにします。</span><span class="sxs-lookup"><span data-stu-id="11124-109">Install [!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)] on each cluster node.</span></span> <span data-ttu-id="11124-110">**コンポーネントのインストール**、**エンタープライズ シングル サインオン管理モジュール**と**エンタープライズ シングル サインオン マスター シークレット サーバー**します。</span><span class="sxs-lookup"><span data-stu-id="11124-110">In **Component Installation**, select **Enterprise Single Sign-On Administration Module** and **Enterprise Single Sign-On Master Secret Server**.</span></span> <span data-ttu-id="11124-111">インストールが正常に完了したら後、は、**いない**実行、[!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)]構成します。</span><span class="sxs-lookup"><span data-stu-id="11124-111">After installation has completed successfully, do **not** run the [!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)] Configuration.</span></span>  
  
2. <span data-ttu-id="11124-112">作成**SSO 管理者**と**SSO 関連管理者**ドメイン グループです。</span><span class="sxs-lookup"><span data-stu-id="11124-112">Create **SSO Administrators** and **SSO Affiliate Administrators** domain groups.</span></span> <span data-ttu-id="11124-113">エンタープライズ SSO サービスのクラスター化されたインスタンスを作成するには、ドメイン グループとしてこれらのグループを作成する必要があります。</span><span class="sxs-lookup"><span data-stu-id="11124-113">To create a clustered instance of the Enterprise SSO service, you must create these groups as domain groups.</span></span>  
  
3. <span data-ttu-id="11124-114">作成またはのメンバであるドメイン アカウントを指定、 **SSO 管理者**ドメイン グループです。</span><span class="sxs-lookup"><span data-stu-id="11124-114">Create or designate a domain account that is a member of the **SSO Administrators** domain group.</span></span> <span data-ttu-id="11124-115">このドメイン アカウントとしてログオンする各ノードで、エンタープライズ SSO サービスが構成されます。</span><span class="sxs-lookup"><span data-stu-id="11124-115">The Enterprise SSO service on each node is configured to log on as this domain account.</span></span> <span data-ttu-id="11124-116">このアカウントが必要、**サービスとしてログオン**クラスター内の各ノードで右。</span><span class="sxs-lookup"><span data-stu-id="11124-116">This account must have the **Log on as a service** right on each node in the cluster.</span></span>  
  
4. <span data-ttu-id="11124-117">ドメインに構成プロセス中にログオンに使用しているアカウントを追加**SSO 管理者**グループ。</span><span class="sxs-lookup"><span data-stu-id="11124-117">Add the account that you are using to log on during the configuration process to the domain **SSO Administrators** group.</span></span>  
  
   > [!IMPORTANT]
   >  <span data-ttu-id="11124-118">手順 3 と 4 が完了していない場合、エンタープライズ SSO サービスの構成が失敗します。</span><span class="sxs-lookup"><span data-stu-id="11124-118">Configuration of the Enterprise SSO service fails if steps 3 and 4 are not completed.</span></span>  
  
5. <span data-ttu-id="11124-119">開始、[!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)]構成します。</span><span class="sxs-lookup"><span data-stu-id="11124-119">Start the [!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)] Configuration.</span></span>  
  
6. <span data-ttu-id="11124-120">選択**カスタム構成**オプションし、入力、**データベース サーバー名**、**ユーザー名**、および**パスワード**値。</span><span class="sxs-lookup"><span data-stu-id="11124-120">Select **Custom Configuration** option and enter the **Database server name**, **User name**, and **Password** values.</span></span> <span data-ttu-id="11124-121">選択**構成**を続行します。</span><span class="sxs-lookup"><span data-stu-id="11124-121">Select **Configure** to continue.</span></span>  
  
   > [!NOTE]
   >  <span data-ttu-id="11124-122">必ずためこの時点で、エンタープライズ SSO サービスを構成だけを入力できます先ほど作成したここで、ドメイン アカウント。</span><span class="sxs-lookup"><span data-stu-id="11124-122">Since you are only be configuring the Enterprise SSO service at this time, you can just enter the domain account that you created earlier here.</span></span>  
  
7. <span data-ttu-id="11124-123">選択、**エンタープライズ SSO**左側のウィンドウからオプションを選択し、エンタープライズ SSO 機能の次のオプションを設定します。</span><span class="sxs-lookup"><span data-stu-id="11124-123">Select the **Enterprise SSO** option from the left pane and set the following options for the Enterprise SSO feature:</span></span>  
  
   1.  <span data-ttu-id="11124-124">選択、**を有効にするエンタープライズ シングル サインオン コンピューターこの**チェック ボックスをオンします。</span><span class="sxs-lookup"><span data-stu-id="11124-124">Select the **Enable Enterprise Single Sign-On on this computer** check box.</span></span>  
  
   2.  <span data-ttu-id="11124-125">選択**新しい SSO システムを作成する**します。</span><span class="sxs-lookup"><span data-stu-id="11124-125">Select **Create a new SSO system**.</span></span>  
  
   3.  <span data-ttu-id="11124-126">入力、**データ ストア**の**サーバー名**と**データベース名**値。</span><span class="sxs-lookup"><span data-stu-id="11124-126">Enter the **Data stores** for **Server Name** and **Database Name** values.</span></span>  
  
   4.  <span data-ttu-id="11124-127">先ほど作成したドメイン アカウントが、エンタープライズ SSO サービスに関連付けられているアカウントであることを確認します。</span><span class="sxs-lookup"><span data-stu-id="11124-127">Verify that the domain account that you created earlier is the account that is associated with the Enterprise SSO service.</span></span>  
  
   5.  <span data-ttu-id="11124-128">SSO 管理者ロールに関連付けられたグループとして、先ほど作成したドメイン SSO 管理者グループを入力します。</span><span class="sxs-lookup"><span data-stu-id="11124-128">Enter the domain SSO Administrators group that you created earlier as the group associated with the SSO Administrator(s) role.</span></span>  
  
   6.  <span data-ttu-id="11124-129">SSO 関連管理者ロールに関連付けられたグループとして、先ほど作成したドメイン SSO 関連管理者グループを入力します。</span><span class="sxs-lookup"><span data-stu-id="11124-129">Enter the domain SSO Affiliate Administrators group that you created earlier as the group associated with the SSO Affiliate Administrator(s) role.</span></span>  
  
8. <span data-ttu-id="11124-130">選択、**エンタープライズ SSO シークレットのバックアップ**左側のウィンドウからオプションを選択し、エンタープライズ SSO シークレットをバックアップするための適切なパラメーターを提供します。</span><span class="sxs-lookup"><span data-stu-id="11124-130">Select the **Enterprise SSO Secret Backup** option from the left pane and provide the appropriate parameters for backing up the Enterprise SSO secret.</span></span> <span data-ttu-id="11124-131">既定では、エンタープライズ SSO シークレットがバックアップされる *\<ドライブ\>* : \enterprise シングル サインオン \Program Files\Common\\*SSOxxxx*.bak です。</span><span class="sxs-lookup"><span data-stu-id="11124-131">By default, the Enterprise SSO secret is backed up to *\<drive\>*:\Program Files\Common Files\Enterprise Single Sign-On\\*SSOxxxx*.bak.</span></span>  
  
9. <span data-ttu-id="11124-132">をクリックして、**構成の適用**と概要を確認します。</span><span class="sxs-lookup"><span data-stu-id="11124-132">Click the **Apply Configuration** and review the Summary.</span></span>  
  
10. <span data-ttu-id="11124-133">をクリックして**次**構成を適用します。</span><span class="sxs-lookup"><span data-stu-id="11124-133">Click **Next** to apply the configuration.</span></span>  
  
11. <span data-ttu-id="11124-134">クリックして**完了**構成ウィザードを閉じます。</span><span class="sxs-lookup"><span data-stu-id="11124-134">Click **Finish** to close the Configuration wizard.</span></span>  
  
12. <span data-ttu-id="11124-135">閉じる、[!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)]構成します。</span><span class="sxs-lookup"><span data-stu-id="11124-135">Close the [!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)] configuration.</span></span>  
  
13. <span data-ttu-id="11124-136">パッシブ クラスター ノードと開始のログオン、[!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)]構成します。</span><span class="sxs-lookup"><span data-stu-id="11124-136">Log on to the passive cluster node and start the [!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)] Configuration.</span></span>  
  
14. <span data-ttu-id="11124-137">選択、**カスタム構成**オプションし、同じ値を入力します、**データベース サーバー名**、**ユーザー名**、および**パスワード**です最初のクラスター ノードを構成するときに入力したとします。</span><span class="sxs-lookup"><span data-stu-id="11124-137">Choose the **Custom Configuration** option and enter the same values for the **Database server name**, **User name**, and **Password** that you entered when configuring the first cluster node.</span></span> <span data-ttu-id="11124-138">これらの値を入力すると、次のようにクリックします。**構成**を続行します。</span><span class="sxs-lookup"><span data-stu-id="11124-138">After entering these values, click **Configure** to continue.</span></span>  
  
15. <span data-ttu-id="11124-139">選択、**エンタープライズ SSO**左側のウィンドウからオプションを選択し、エンタープライズ SSO 機能の次のオプションを設定します。</span><span class="sxs-lookup"><span data-stu-id="11124-139">Select the **Enterprise SSO** option from the left pane and set the following options for the Enterprise SSO feature:</span></span>  
  
    1.  <span data-ttu-id="11124-140">選択、**を有効にするエンタープライズ シングル サインオン コンピューターこの**オプション。</span><span class="sxs-lookup"><span data-stu-id="11124-140">Select the **Enable Enterprise Single Sign-On on this computer** option.</span></span>  
  
    2.  <span data-ttu-id="11124-141">選択**既存の SSO システムに参加**します。</span><span class="sxs-lookup"><span data-stu-id="11124-141">Select **Join an existing SSO system**.</span></span>  
  
    3.  <span data-ttu-id="11124-142">SSO データベースの同じ値を入力**サーバー名**と**データベース名**最初のクラスター ノードを構成するときに入力したことです。</span><span class="sxs-lookup"><span data-stu-id="11124-142">Enter the same values for the SSO Database **Server Name** and **Database Name** that you entered when configuring the first cluster node.</span></span>  
  
    4.  <span data-ttu-id="11124-143">最初のクラスター ノードを構成するときに入力したドメイン アカウントには、同じ値を入力します。</span><span class="sxs-lookup"><span data-stu-id="11124-143">Enter the same value for the domain account that you entered when configuring the first cluster node.</span></span>  
  
16. <span data-ttu-id="11124-144">選択**構成の適用**結果を表示します。</span><span class="sxs-lookup"><span data-stu-id="11124-144">Select **Apply Configuration** to display the Summary.</span></span>  
  
17. <span data-ttu-id="11124-145">選択**次**構成を適用します。</span><span class="sxs-lookup"><span data-stu-id="11124-145">Select **Next** to apply the configuration.</span></span>  
  
18. <span data-ttu-id="11124-146">選択**完了**構成ウィザードを閉じます。</span><span class="sxs-lookup"><span data-stu-id="11124-146">Select **Finish** to close the Configuration wizard.</span></span>  
  
19. <span data-ttu-id="11124-147">閉じる、[!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)]構成します。</span><span class="sxs-lookup"><span data-stu-id="11124-147">Close the [!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)] Configuration.</span></span>  
  
### <a name="to-update-the-master-secret-server-name-in-the-sso-database"></a><span data-ttu-id="11124-148">SSO データベースのマスター シークレット サーバー名を更新するには</span><span class="sxs-lookup"><span data-stu-id="11124-148">To update the master secret server name in the SSO database</span></span>  
  
1.  <span data-ttu-id="11124-149">停止して、エンタープライズ SSO サービスを再起動するアクティブなクラスター ノードでコマンド プロンプトから次のコマンドを入力します。</span><span class="sxs-lookup"><span data-stu-id="11124-149">Type the following commands from a command prompt on the active cluster node to stop and restart the Enterprise SSO service:</span></span>  
  
    ```  
    net stop entsso  
    ```  
  
     <span data-ttu-id="11124-150">、</span><span class="sxs-lookup"><span data-stu-id="11124-150">and</span></span>  
  
    ```  
    net start entsso  
    ```  
  
2.  <span data-ttu-id="11124-151">SSO データベースのマスター シークレット サーバー名を次の手順に従って、クラスター名に変更します。</span><span class="sxs-lookup"><span data-stu-id="11124-151">Change the master secret server name in the SSO database to the cluster name by following these steps:</span></span>  
  
    > [!NOTE]
    >  <span data-ttu-id="11124-152">クラスター名が定義されているクラスターで作成したネットワーク名リソース名グループ/クラスター化されたサービスまたはアプリケーションをクラスター化されたエンタープライズ SSO サービスにが含まれます。</span><span class="sxs-lookup"><span data-stu-id="11124-152">The cluster name is the name defined for the network name resource that you have created in the cluster group / clustered service or application that will contain the clustered Enterprise SSO service.</span></span> <span data-ttu-id="11124-153">たとえば、名前があります*BIZTALKCLUSTER*します。</span><span class="sxs-lookup"><span data-stu-id="11124-153">For example, the name may be *BIZTALKCLUSTER*.</span></span>  
  
    1.  <span data-ttu-id="11124-154">テキスト エディターで、次のコードを貼り付けます。</span><span class="sxs-lookup"><span data-stu-id="11124-154">Paste the following code in a text editor:</span></span>  
  
        ```  
        <sso>  
          <globalInfo>  
            <secretServer>BIZTALKCLUSTER</secretServer>  
          </globalInfo>  
        </sso>  
        ```  
  
        > [!NOTE]
        >  <span data-ttu-id="11124-155">*BIZTALKCLUSTER*クラスターで作成される実際のネットワーク名リソースのプレース ホルダーは、グループ/クラスター化されたサービスまたはアプリケーション。</span><span class="sxs-lookup"><span data-stu-id="11124-155">*BIZTALKCLUSTER* is a placeholder for the actual network name resource that is created in the cluster group / clustered service or application.</span></span>  
  
    2.  <span data-ttu-id="11124-156">.Xml ファイルとして保存します。</span><span class="sxs-lookup"><span data-stu-id="11124-156">Save the file as an .xml file.</span></span> <span data-ttu-id="11124-157">たとえば、ssocluster.xml ファイルを保存します。</span><span class="sxs-lookup"><span data-stu-id="11124-157">For example, save the file as SSOCLUSTER.xml.</span></span>  
  
    3.  <span data-ttu-id="11124-158">コマンド プロンプトで、エンタープライズ SSO のインストール フォルダーに変更します。</span><span class="sxs-lookup"><span data-stu-id="11124-158">At a command prompt, change to the Enterprise SSO installation folder.</span></span> <span data-ttu-id="11124-159">インストール フォルダーは、既定では、 *\<ドライブ\>* : \Program Files\Common \enterprise シングル サインオンします。</span><span class="sxs-lookup"><span data-stu-id="11124-159">By default, the installation folder is *\<drive\>*:\Program Files\Common Files\Enterprise Single Sign-On.</span></span>  
  
    4.  <span data-ttu-id="11124-160">データベースのマスター シークレット サーバー名を更新するコマンド プロンプトで次のコマンドを入力します。</span><span class="sxs-lookup"><span data-stu-id="11124-160">Type the following command at the command prompt to update the master secret server name in the database:</span></span>  
  
        ```  
        ssomanage -updatedb XMLFile  
        ```  
  
        > [!NOTE]
        >  <span data-ttu-id="11124-161">*XMLFile*は以前に保存した .xml ファイルの名前のプレース ホルダーです。</span><span class="sxs-lookup"><span data-stu-id="11124-161">*XMLFile* is a placeholder for the name of the .xml file that you saved earlier.</span></span>  
  
### <a name="to-create-the-clustered-enterprise-sso-resource"></a><span data-ttu-id="11124-162">クラスター化されたエンタープライズ SSO リソースを作成するには</span><span class="sxs-lookup"><span data-stu-id="11124-162">To create the clustered Enterprise SSO resource</span></span>  
  
1.  <span data-ttu-id="11124-163">「フォールト トレランスで BizTalk Server でを使用してクラスターを向上させる Windows Server」ホワイト ペーパーの手順に従って、クラスターはクラスター化された分散トランザクション コーディネーター (MSDTC) リソースで構成されていない場合[ http://go.microsoft.com/fwlink/?LinkId=69207 ](http://go.microsoft.com/fwlink/?LinkId=69207)クラスター化された MSDTC リソースを作成します。</span><span class="sxs-lookup"><span data-stu-id="11124-163">If the cluster is not configured with a clustered Distributed Transaction Coordinator (MSDTC) resource then follow the steps in the "Improving Fault Tolerance in BizTalk Server by Using a Windows Server Cluster" white paper at [http://go.microsoft.com/fwlink/?LinkId=69207](http://go.microsoft.com/fwlink/?LinkId=69207) to create a clustered MSDTC resource.</span></span>  
  
2.  <span data-ttu-id="11124-164">クリックして**開始**、**プログラム**、**管理ツール**、し**フェールオーバー クラスター管理**フェールオーバー クラスターを起動するには管理プログラム。</span><span class="sxs-lookup"><span data-stu-id="11124-164">Click **Start**, **Programs**, **Administrative Tools**, and then **Failover Cluster Management** to start the Failover Cluster Management program.</span></span>  
  
3.  <span data-ttu-id="11124-165">左側のウィンドウで右クリック**フェールオーバー クラスター管理** をクリック**クラスターの管理**します。</span><span class="sxs-lookup"><span data-stu-id="11124-165">In the left hand pane, right-click **Failover Cluster Management** and click **Manage a Cluster**.</span></span>  
  
4.  <span data-ttu-id="11124-166">**を管理するクラスターを選択** ダイアログ ボックスに、管理する をクリックしてクラスターを入力**OK**。</span><span class="sxs-lookup"><span data-stu-id="11124-166">On the **Select a cluster to manage** dialog box, enter the cluster to be managed and click **OK**.</span></span>  
  
5.  <span data-ttu-id="11124-167">左側にあるウィンドウをクリックして、クラスター化されたサービスまたはアプリケーションを選択する、IP アドレスおよびネットワーク名リソースが含まれています。</span><span class="sxs-lookup"><span data-stu-id="11124-167">In the left hand pane click to select a clustered service or application that contains an IP Address and Network Name resource.</span></span> <span data-ttu-id="11124-168">次の手順では、[ディスク、IP アドレス、および名前リソースをクラスター グループを作成する方法](../core/how-to-create-a-cluster-group-with-a-disk-ip-address-and-name-resource1.md)が既に存在しない場合は、IP アドレスおよびネットワーク名リソース グループを作成します。</span><span class="sxs-lookup"><span data-stu-id="11124-168">Follow the steps in [How to Create a Cluster Group with a Disk, IP Address, and Name Resource](../core/how-to-create-a-cluster-group-with-a-disk-ip-address-and-name-resource1.md) to create a group with an IP Address and Network Name resource if one does not already exist.</span></span>  
  
    > [!NOTE]
    >  <span data-ttu-id="11124-169">クラスター化されたエンタープライズ SSO サービスは、同じグループ内のクラスター化された物理ディスク リソースの使用を明示的に要求されません。</span><span class="sxs-lookup"><span data-stu-id="11124-169">A clustered Enterprise SSO service does not explicitly require the use of a clustered Physical Disk resource in the same group.</span></span>  
  
6.  <span data-ttu-id="11124-170">クラスター化されたサービスまたはアプリケーションを右クリックし、[**リソースを追加**、] をクリック**汎用サービス**を表示する、**の新しいリソース ウィザード**ダイアログ。</span><span class="sxs-lookup"><span data-stu-id="11124-170">Right-click the clustered service or application, point to **Add a resource**, and click **Generic Service** to display the **New Resource Wizard** dialog.</span></span>  
  
    > [!IMPORTANT]
    >  <span data-ttu-id="11124-171">**汎用サービス パラメーター**  ダイアログ ボックスで、クリックして選択しない場合、**コンピューター名のネットワーク名を使う**チェック ボックスをオン SSO クライアント コンピューターでは、次のようなエラーを生成しますときに、。エンタープライズ SSO サービスのクラスター化されたこのインスタンスに接続しようとしてください。</span><span class="sxs-lookup"><span data-stu-id="11124-171">In the **Generic Service Parameters** dialog box, if you do not click to select the **Use Network Name for computer name** check box, SSO client computers will generate an error similar to the following when they try to contact this clustered instance of the Enterprise SSO service:</span></span>  
    >   
    >  <span data-ttu-id="11124-172">マスター シークレットを取得できませんでした。</span><span class="sxs-lookup"><span data-stu-id="11124-172">Failed to retrieve master secrets.</span></span>  
    >   
    >  <span data-ttu-id="11124-173">マスター シークレット サーバー名が正しいことと、使用可能なであることを確認します。</span><span class="sxs-lookup"><span data-stu-id="11124-173">Verify that the master secret server name is correct and that it is available.</span></span> <span data-ttu-id="11124-174">シークレット サーバー名:ENTSSO エラー コード:0x800706D9、エンドポイントがあるエンドポイント マッパーから使用できます。</span><span class="sxs-lookup"><span data-stu-id="11124-174">Secret Server Name: ENTSSO Error Code: 0x800706D9, there are no more endpoints available from the endpoint mapper.</span></span>  
  
7.  <span data-ttu-id="11124-175">**サービスの選択**のページ、**リソースの新規作成ウィザード**をクリックして選択**エンタープライズ シングル サインオン サービス** をクリック**次**します。</span><span class="sxs-lookup"><span data-stu-id="11124-175">On the **Select Service** page of the **New Resource Wizard**, click to select **Enterprise Single Sign-On Service** and click **Next**.</span></span>  
  
8.  <span data-ttu-id="11124-176">**確認**ページ クリック **[次へ]** します。</span><span class="sxs-lookup"><span data-stu-id="11124-176">On the **Confirmation** page click **Next**.</span></span>  
  
9. <span data-ttu-id="11124-177">**概要**ページ クリック**完了**。</span><span class="sxs-lookup"><span data-stu-id="11124-177">On the **Summary** page click **Finish**.</span></span> <span data-ttu-id="11124-178">エンタープライズ シングル サインオン サービスのクラスター化されたインスタンスは、下に表示されます**その他のリソース**の中央のペインで、**フェールオーバー クラスター管理**インターフェイス。</span><span class="sxs-lookup"><span data-stu-id="11124-178">A clustered instance of the Enterprise Single Sign-On Service will appear under **Other Resources** in the center pane of the **Failover Cluster Management** interface.</span></span>  
  
10. <span data-ttu-id="11124-179">エンタープライズ シングル サインオン サービスのクラスター化されたインスタンスを右クリックして**プロパティ**を表示する、**エンタープライズ シングル サインオン サービスのプロパティ** ダイアログ ボックス。</span><span class="sxs-lookup"><span data-stu-id="11124-179">Right-click the clustered instance of the Enterprise Single Sign-On Service and select **Properties** to display the **Enterprise Single Sign-On Service Properties** dialog box.</span></span>  
  
11. <span data-ttu-id="11124-180">をクリックして、**依存関係**プロパティ ダイアログ ボックスのタブ**挿入**します。</span><span class="sxs-lookup"><span data-stu-id="11124-180">Click the **Dependencies** tab of the properties dialog box and click **Insert**.</span></span>  
  
12. <span data-ttu-id="11124-181">ドロップダウン ボックスをクリックします。**リソース**を選択、**名:** リソースをクリックします **[ok]** します。</span><span class="sxs-lookup"><span data-stu-id="11124-181">Click the drop down box under **Resource**, select the **Name:** resource and click **OK**.</span></span>  
  
### <a name="to-restore-the-master-secret-on-the-second-cluster-node"></a><span data-ttu-id="11124-182">2 番目のクラスター ノードでマスター シークレットを復元するには</span><span class="sxs-lookup"><span data-stu-id="11124-182">To restore the master secret on the second cluster node</span></span>  
  
1.  <span data-ttu-id="11124-183">フェールオーバー クラスターの管理では、クラスター化されたサービスまたはアプリケーションをクラスター化されたエンタープライズ シングル サインオン サービスを含む右クリックし、順にクリックします**このサービスまたはアプリケーションをオンライン**内のリソースのすべてを開始するにはクラスター化されたサービスまたはアプリケーション。</span><span class="sxs-lookup"><span data-stu-id="11124-183">In Failover Cluster Management, right click the clustered service or application that contains the clustered Enterprise Single Sign-On service and then click **Bring this service or application online** to start all of the resources in the clustered service or application.</span></span>  
  
2.  <span data-ttu-id="11124-184">クラスター化されたサービスまたはアプリケーションを右クリックし、**このサービスまたはアプリケーションを別のノードに移動**、2 番目のノードをクリックします。</span><span class="sxs-lookup"><span data-stu-id="11124-184">Right-click the clustered service or application, point to **Move this service or application to another node**, and click the second node.</span></span> <span data-ttu-id="11124-185">この手順では、クラスター化されたサービスまたは 2 番目のノードに最初のノードからクラスター化されたエンタープライズ シングル サインオン サービスを含むアプリケーションを移動します。</span><span class="sxs-lookup"><span data-stu-id="11124-185">This step moves the clustered service or application that contains the clustered Enterprise Single Sign-On service from the first node to the second node.</span></span>  
  
3.  <span data-ttu-id="11124-186">クラスター化されたエンタープライズ シングル サインオン サービスを右クリックし、をクリックして**このサービスまたはアプリケーションをオフラインに**、エンタープライズ SSO サービスのクラスター化されたインスタンスを右クリックしておよびクリックして**このサービスまたはアプリケーションをオンライン**します。</span><span class="sxs-lookup"><span data-stu-id="11124-186">Right-click the clustered Enterprise Single Sign-On service and click **Take this service or application offline**, then right-click the clustered instance of the Enterprise SSO service and click **Bring this service or application online**.</span></span>  
  
    > [!NOTE]
    >  <span data-ttu-id="11124-187">この手順を完了していない場合、マスター シークレットを復元する試行が失敗します。</span><span class="sxs-lookup"><span data-stu-id="11124-187">If this step is not completed the attempt to restore the master secret may not succeed.</span></span>  
  
4.  <span data-ttu-id="11124-188">最初のノードから 2 番目のノードのインストール フォルダーでシングル サインオン \Enterprise にマスター シークレットのバックアップ ファイルをコピーします。</span><span class="sxs-lookup"><span data-stu-id="11124-188">Copy the master secret backup file from the first node to the \Enterprise Single Sign-On installation folder on the second node.</span></span> <span data-ttu-id="11124-189">インストール フォルダーは、既定では、 *\<ドライブ\>* : \Program Files\Common \enterprise シングル サインオンします。</span><span class="sxs-lookup"><span data-stu-id="11124-189">By default, the installation folder is *\<drive\>*:\Program Files\Common Files\Enterprise Single Sign-On.</span></span>  
  
5.  <span data-ttu-id="11124-190">2 番目のノードには、コマンド プロンプトで、ログオン、エンタープライズ SSO のインストール フォルダーに移動します。</span><span class="sxs-lookup"><span data-stu-id="11124-190">Log on to the second node and at a command prompt, change to the Enterprise SSO installation folder.</span></span>  
  
6.  <span data-ttu-id="11124-191">2 番目のノードにマスター シークレットを復元するコマンド プロンプトから次のコマンドを入力します。</span><span class="sxs-lookup"><span data-stu-id="11124-191">Type the following command from the command prompt to restore the master secret to the second node:</span></span>  
  
    ```  
    ssoconfig -restoresecret RestoreFile  
    ```  
  
    > [!NOTE]
    >  <span data-ttu-id="11124-192">置換*RestoreFile*のパスと、マスター シークレットを含むバックアップ ファイルの名前を使用します。</span><span class="sxs-lookup"><span data-stu-id="11124-192">Replace *RestoreFile* with the path of and the name of the backup file that contains the master secret.</span></span>  
  
     <span data-ttu-id="11124-193">マスター シークレットは、次の場所にレジストリに格納されます。</span><span class="sxs-lookup"><span data-stu-id="11124-193">The master secret is stored in the registry at the following location:</span></span>  
  
     <span data-ttu-id="11124-194">HKEY_LOCAL_MACHINE\SOFTWARE\Microsoft\ENTSSO\SSOSS</span><span class="sxs-lookup"><span data-stu-id="11124-194">HKEY_LOCAL_MACHINE\SOFTWARE\Microsoft\ENTSSO\SSOSS</span></span>  
  
7.  <span data-ttu-id="11124-195">クラスター化されたサービスまたはフェールオーバー機能を確認するには、その他のクラスター ノードにこのクラスター ノードからクラスター化されたエンタープライズ シングル サインオン サービスを含むアプリケーションを移動します。</span><span class="sxs-lookup"><span data-stu-id="11124-195">Move the clustered service or application that contains the clustered Enterprise Single Sign-On service from this cluster node to other cluster node to ensure failover functionality.</span></span> <span data-ttu-id="11124-196">クラスター グループに戻す、フェールバック機能を確認します。</span><span class="sxs-lookup"><span data-stu-id="11124-196">Then move the cluster group back to verify fail-back functionality.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="11124-197">参照</span><span class="sxs-lookup"><span data-stu-id="11124-197">See Also</span></span>  
 [<span data-ttu-id="11124-198">ディスク、IP アドレス、および名前リソースをクラスター グループを作成する方法</span><span class="sxs-lookup"><span data-stu-id="11124-198">How to Create a Cluster Group with a Disk, IP Address, and Name Resource</span></span>](../core/how-to-create-a-cluster-group-with-a-disk-ip-address-and-name-resource1.md)
