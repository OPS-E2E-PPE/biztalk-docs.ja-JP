---
title: 信頼性の維持 |Microsoft Docs
ms.custom: ''
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: ''
ms.suite: ''
ms.tgt_pltfrm: ''
ms.topic: article
ms.assetid: 09cdce13-a75b-44d7-8388-7a868bb51c69
caps.latest.revision: 5
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: faf58e24442d2a17bace7b0d56393d1c793b9cd9
ms.sourcegitcommit: 266308ec5c6a9d8d80ff298ee6051b4843c5d626
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 06/27/2018
ms.locfileid: "36985675"
---
# <a name="maintaining-reliability"></a><span data-ttu-id="f566d-102">信頼性の維持</span><span class="sxs-lookup"><span data-stu-id="f566d-102">Maintaining Reliability</span></span>
<span data-ttu-id="f566d-103">このセクションで信頼性に関する問題を解決する方法について説明します、[!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)]システム。</span><span class="sxs-lookup"><span data-stu-id="f566d-103">This section provides information about how you can resolve reliability issues with a [!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)] system.</span></span> <span data-ttu-id="f566d-104">実行される定期的なメンテナンスのチェックでこれらの問題を検出する可能性がある、[ルーチン メンテナンスのチェックリスト](../technical-guides/routine-maintenance-checklists.md)このドキュメントの「します。</span><span class="sxs-lookup"><span data-stu-id="f566d-104">These issues may be discovered by the routine maintenance checks that are performed in the [Routine Maintenance Checklists](../technical-guides/routine-maintenance-checklists.md) section of this document.</span></span>  

 <span data-ttu-id="f566d-105">このセクションのトピックだけでなくは、このドキュメントでその他のトピックは、信頼性の問題を説明します。</span><span class="sxs-lookup"><span data-stu-id="f566d-105">In addition to the topics in this section, other topics in this document address reliability issues.</span></span> <span data-ttu-id="f566d-106">これらのトピックが記載されて[関連セクション](../technical-guides/maintaining-reliability.md#BKMK_Related)以下。</span><span class="sxs-lookup"><span data-stu-id="f566d-106">These topics are listed in [Related Sections](../technical-guides/maintaining-reliability.md#BKMK_Related) below.</span></span>  

## <a name="testing-group-failover"></a><span data-ttu-id="f566d-107">グループのフェールオーバーのテスト</span><span class="sxs-lookup"><span data-stu-id="f566d-107">Testing Group Failover</span></span>  
 <span data-ttu-id="f566d-108">毎月実行される信頼性チェックの一部として、このセクションの手順を実行します。</span><span class="sxs-lookup"><span data-stu-id="f566d-108">Perform the procedures in this section as part of the reliability checks that should be performed monthly.</span></span> <span data-ttu-id="f566d-109">これらの手順には、グループのフェールオーバー ポリシーをテストし、グループ リソースがフェールオーバーできるかどうかをテストが含まれます。</span><span class="sxs-lookup"><span data-stu-id="f566d-109">These procedures include testing the group failover policy, and testing whether the group resources can fail over.</span></span>  

> [!NOTE]  
>  <span data-ttu-id="f566d-110">コンピューターがドメインに参加している場合、Domain Admins グループのメンバーは、この手順を実行できる必要があります。</span><span class="sxs-lookup"><span data-stu-id="f566d-110">If the computer is joined to a domain, members of the Domain Admins group should be able to perform this procedure.</span></span>  

> [!NOTE]  
>  <span data-ttu-id="f566d-111">このセクションでは、手順を実行する必要がありますがログオンして、ローカル コンピューターの Administrators グループのメンバーとして、またはをされている必要が適切な権限が委任します。</span><span class="sxs-lookup"><span data-stu-id="f566d-111">To perform the procedures in this section, you must be logged on as a member of the Administrators group on the local computer, or you must have been delegated the appropriate authority.</span></span>  

 <span data-ttu-id="f566d-112">Windows Server 2008 を実行するコンピューターでグループのフェールオーバーをテストするには、次の手順を実行します。</span><span class="sxs-lookup"><span data-stu-id="f566d-112">Perform the following steps to test group failover on computers running Windows Server 2008.</span></span>  

#### <a name="to-test-a-group-failover-policy"></a><span data-ttu-id="f566d-113">グループのフェールオーバー ポリシーをテストするには</span><span class="sxs-lookup"><span data-stu-id="f566d-113">To test a group failover policy</span></span>  

1.  <span data-ttu-id="f566d-114">インストールされていることを確認、**フェールオーバー クラスタ リング**機能に少なくとも 2 つのコンピューター上には、2 つのノードの Windows フェールオーバー クラスターを作成するための Windows Server 2008 を実行します。</span><span class="sxs-lookup"><span data-stu-id="f566d-114">Make sure you have installed the **Failover Clustering** feature on at least two computer running Windows Server 2008 so as to create a two node Windows Failover Cluster.</span></span> <span data-ttu-id="f566d-115">この機能をインストールする方法については、[フェールオーバー クラスタ リング機能をインストール](http://go.microsoft.com/fwlink/?LinkId=157259)(http://go.microsoft.com/fwlink/?LinkId=157259)を参照してください。</span><span class="sxs-lookup"><span data-stu-id="f566d-115">For instructions on how to install this feature, see [Install the Failover Clustering Feature](http://go.microsoft.com/fwlink/?LinkId=157259) (http://go.microsoft.com/fwlink/?LinkId=157259).</span></span>  

2.  <span data-ttu-id="f566d-116">フェールオーバー クラスター管理 を開く**開始**をクリック**管理ツール**、 をクリックし、**フェールオーバー クラスター管理**します。</span><span class="sxs-lookup"><span data-stu-id="f566d-116">Open Failover Cluster Management by clicking **Start**, clicking **Administrative Tools**, and then clicking **Failover Cluster Management**.</span></span>  

3.  <span data-ttu-id="f566d-117">コンソール ツリーで、クラスター ノードを展開し、展開、**サービスとアプリケーション**ノード、フェールオーバー、クリックしてアプリケーションのクラスター化されたインスタンスを右クリックして**プロパティ**。</span><span class="sxs-lookup"><span data-stu-id="f566d-117">In the console tree, expand the cluster node, expand the **Services and Applications** node, right-click the clustered instance of the application to be failed over, and then click **Properties**.</span></span>  

4.  <span data-ttu-id="f566d-118">**フェールオーバー**タブで、設定 **、指定した期間内の最大エラー** 0 をクリックする **[ok]** します。</span><span class="sxs-lookup"><span data-stu-id="f566d-118">On the **Failover** tab, set **Maximum failures in the specified period** to 0, and then click **OK**.</span></span>  

5.  <span data-ttu-id="f566d-119">コンソール ツリーで、展開、**サービスとアプリケーション**ノード。</span><span class="sxs-lookup"><span data-stu-id="f566d-119">In the console tree, expand the **Services and Applications** node.</span></span>  

6.  <span data-ttu-id="f566d-120">詳細ペインで、リソースを右クリックし、**プロパティ**します。</span><span class="sxs-lookup"><span data-stu-id="f566d-120">In the details pane, right-click a resource, and then click **Properties**.</span></span>  

7.  <span data-ttu-id="f566d-121">**ポリシー**タブで、設定**指定期間内の再起動の試行**0 をクリックする **[ok]** します。</span><span class="sxs-lookup"><span data-stu-id="f566d-121">On the **Policies** tab, set **Maximum restarts in the specified period** to 0, and then click **OK**.</span></span>  

8.  <span data-ttu-id="f566d-122">リソースを右クリックし、をクリックして**その他のアクション**、 をクリックし、**このリソースの障害をシミュレート**します。</span><span class="sxs-lookup"><span data-stu-id="f566d-122">Right-click the resource, click **More Actions**, and then click **Simulate Failure of this resource**.</span></span> <span data-ttu-id="f566d-123">グループが、前の手順で指定したポリシーに基づいて反応かどうかを確認します。</span><span class="sxs-lookup"><span data-stu-id="f566d-123">Verify whether the group reacts based on the policy you specified in the previous step.</span></span>  

9. <span data-ttu-id="f566d-124">クリックして、フェールオーバー、アプリケーションのクラスター化されたインスタンスを右クリックして**プロパティ**します。</span><span class="sxs-lookup"><span data-stu-id="f566d-124">Right-click the clustered instance of the application to be failed over, and then click **Properties**.</span></span>  

10. <span data-ttu-id="f566d-125">**フェールオーバー**タブで、設定**指定期間内の最大エラー数**1、およびクリックに **[ok]** します。</span><span class="sxs-lookup"><span data-stu-id="f566d-125">On the **Failover** tab, set **Maximum failures in the specified period** to 1, and then click **OK**.</span></span>  

11. <span data-ttu-id="f566d-126">リソースを右クリックして**このリソースをオンライン**します。</span><span class="sxs-lookup"><span data-stu-id="f566d-126">Right-click the resource and select **Bring this resource online**.</span></span>  

#### <a name="to-test-whether-group-resources-can-fail-over"></a><span data-ttu-id="f566d-127">グループ リソースがフェールオーバーできるかどうかをテストするには</span><span class="sxs-lookup"><span data-stu-id="f566d-127">To test whether group resources can fail over</span></span>  

1.  <span data-ttu-id="f566d-128">インストールされていることを確認、**フェールオーバー クラスタ リング**Windows Server 2008 を実行しているコンピューター上で機能します。</span><span class="sxs-lookup"><span data-stu-id="f566d-128">Make sure you have installed the **Failover Clustering** feature on the computer running Windows Server 2008.</span></span> <span data-ttu-id="f566d-129">この機能をインストールする方法については、[フェールオーバー クラスタ リング機能をインストール](http://go.microsoft.com/fwlink/?LinkId=157259)(http://go.microsoft.com/fwlink/?LinkId=157259)を参照してください。</span><span class="sxs-lookup"><span data-stu-id="f566d-129">For instructions on how to install this feature, see [Install the Failover Clustering Feature](http://go.microsoft.com/fwlink/?LinkId=157259) (http://go.microsoft.com/fwlink/?LinkId=157259).</span></span>  

2.  <span data-ttu-id="f566d-130">フェールオーバー クラスター管理 を開く**開始**をクリック**管理ツール**、 をクリックし、**フェールオーバー クラスター管理**します。</span><span class="sxs-lookup"><span data-stu-id="f566d-130">Open Failover Cluster Management by clicking **Start**, clicking **Administrative Tools**, and then clicking **Failover Cluster Management**.</span></span>  

3.  <span data-ttu-id="f566d-131">コンソール ツリーで、クラスター ノードを展開し、展開、**サービスとアプリケーション**ノード、クラスター化されたインスタンスをフェールオーバーするアプリケーションの順にクリックします。</span><span class="sxs-lookup"><span data-stu-id="f566d-131">In the console tree, expand the cluster node, expand the **Services and Applications** node, and then click the clustered instance of the application to be failed over.</span></span>  

4.  <span data-ttu-id="f566d-132">**アクション** メニューのをクリックして**このサービスまたはアプリケーションを別のノードに移動**、アプリケーションのフェールオーバー先のノードをクリックします。</span><span class="sxs-lookup"><span data-stu-id="f566d-132">On the **Action** menu, click **Move this service or application to another node**, and then click the node to which the application will be failed over.</span></span>  

5.  <span data-ttu-id="f566d-133">**アクションを確認してください** ダイアログ ボックスで、選択したノードにアプリケーションの移行を選択します。</span><span class="sxs-lookup"><span data-stu-id="f566d-133">In the **Please confirm action** dialog box, choose to move the application to selected node.</span></span>  

6.  <span data-ttu-id="f566d-134">に対して、アプリケーションへの移動先ノードが表示されていることを確認、**現在の所有者**アプリケーションの詳細ウィンドウにします。</span><span class="sxs-lookup"><span data-stu-id="f566d-134">Make sure that the node to which you moved the application to is listed against the **Current Owner** in the details pane of the application.</span></span>  

##  <a name="BKMK_BTSGrp"></a> <span data-ttu-id="f566d-135">BizTalk グループの一部である複数のサーバーのことを確認します。</span><span class="sxs-lookup"><span data-stu-id="f566d-135">Ensuring Multiple Servers Are Part of a BizTalk Group</span></span>  
 <span data-ttu-id="f566d-136">システムの信頼性を確保するには、は、BizTalk グループの一部が少なくとも 2 つの物理 BizTalk サーバーにあります。</span><span class="sxs-lookup"><span data-stu-id="f566d-136">To ensure the reliability of a system, at least two physical BizTalk servers should be part of the BizTalk group.</span></span>  <span data-ttu-id="f566d-137">BizTalk グループにサーバーを追加する必要がある場合は、次に留意してください。</span><span class="sxs-lookup"><span data-stu-id="f566d-137">If you need to add a server to a BizTalk group, keep the following in mind:</span></span>  

- <span data-ttu-id="f566d-138">サーバーは、1 つの BizTalk グループに関連付けられた場合のみできます。</span><span class="sxs-lookup"><span data-stu-id="f566d-138">A server can only be associated with one BizTalk group.</span></span> <span data-ttu-id="f566d-139">サーバーが別のグループに既に属している場合、まず現在のグループからサーバーを削除し、その後でサーバーを新しいグループに追加する必要があります。</span><span class="sxs-lookup"><span data-stu-id="f566d-139">If a server already belongs to another group, you must first remove that server from its current group before you can add it to a new group.</span></span> <span data-ttu-id="f566d-140">BizTalk グループからサーバーを削除する方法の詳細についてを参照してください「する方法をサーバーから、グループの削除」[!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)]ヘルプ[ http://go.microsoft.com/fwlink/?LinkId=155577](http://go.microsoft.com/fwlink/?LinkId=155577)します。</span><span class="sxs-lookup"><span data-stu-id="f566d-140">For more information about removing a server from a BizTalk group, see "How to Remove a Server from a Group" in [!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)] Help at [http://go.microsoft.com/fwlink/?LinkId=155577](http://go.microsoft.com/fwlink/?LinkId=155577).</span></span>  

- <span data-ttu-id="f566d-141">BizTalk Server 環境内の異なるサーバーに関連付けられた BizTalk グループどうしは、メッセージの交換以外の連携を行いません。</span><span class="sxs-lookup"><span data-stu-id="f566d-141">BizTalk groups associated with different servers in a BizTalk Server environment do not interact except to exchange messages.</span></span>  

- <span data-ttu-id="f566d-142">BizTalk Server ランタイムは、BizTalk グループに追加するコンピューターにインストールする必要があります。</span><span class="sxs-lookup"><span data-stu-id="f566d-142">The BizTalk Server runtime must be installed on the computer you want to add to the BizTalk group.</span></span>  

> [!NOTE]  
>  <span data-ttu-id="f566d-143">このトピックの手順を実行するには、必要があるログオンが SSO 管理者グループのメンバーとは、Windows の Administrators グループのメンバーとして。</span><span class="sxs-lookup"><span data-stu-id="f566d-143">To perform the procedures in this topic, you must be logged on as a member of the SSO Administrators group and as a member of the Windows Administrators group.</span></span>  

#### <a name="to-determine-whether-at-least-two-physical-biztalk-servers-are-part-of-the-biztalk-group"></a><span data-ttu-id="f566d-144">2 つの物理的な BizTalk server、BizTalk グループの一部である以上かどうかを判断するには</span><span class="sxs-lookup"><span data-stu-id="f566d-144">To determine whether at least two physical BizTalk servers are part of the BizTalk group</span></span>  

1. <span data-ttu-id="f566d-145">開く、[!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)]管理コンソールをクリックして**開始**をポイントして、**すべてのプログラム**をポイントして、 **Microsoft [!INCLUDE[btsBizTalkServer2006r3ui](../includes/btsbiztalkserver2006r3ui-md.md)]** 、 をクリックし、**BizTalk Server 管理**します。</span><span class="sxs-lookup"><span data-stu-id="f566d-145">Open the [!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)] Administration console by clicking **Start**, pointing to **All Programs**, pointing to **Microsoft [!INCLUDE[btsBizTalkServer2006r3ui](../includes/btsbiztalkserver2006r3ui-md.md)]**, and then clicking **BizTalk Server Administration**.</span></span>  

2. <span data-ttu-id="f566d-146">展開、[!INCLUDE[btsBizTalkServer2006r3ui](../includes/btsbiztalkserver2006r3ui-md.md)]ノード、展開、 **BizTalk グループ**ノードの順に展開し、**プラットフォームの設定**ノード。</span><span class="sxs-lookup"><span data-stu-id="f566d-146">Expand the [!INCLUDE[btsBizTalkServer2006r3ui](../includes/btsbiztalkserver2006r3ui-md.md)] node, expand the **BizTalk Group** node, and then expand the **Platform Settings** node.</span></span>  

3. <span data-ttu-id="f566d-147">をクリックして、**サーバー**ノード。</span><span class="sxs-lookup"><span data-stu-id="f566d-147">Click the **Servers** node.</span></span> <span data-ttu-id="f566d-148">複数のサーバーが表示されていることを確認、**サーバー**ウィンドウ。</span><span class="sxs-lookup"><span data-stu-id="f566d-148">Verify that more than one server is listed in the **Servers** pane.</span></span>  

   > [!NOTE]  
   >  <span data-ttu-id="f566d-149">サーバーに関する情報を表示するには、サーバーを右クリックして**ビュー**、 をクリックし、**グループ ハブ ページ**します。</span><span class="sxs-lookup"><span data-stu-id="f566d-149">To view information about the server, right-click the server, point to **View**, and then click **Group Hub Page**.</span></span>  

#### <a name="to-add-a-server-to-a-biztalk-group"></a><span data-ttu-id="f566d-150">サーバーを BizTalk グループに追加するには</span><span class="sxs-lookup"><span data-stu-id="f566d-150">To add a server to a BizTalk group</span></span>  

1. <span data-ttu-id="f566d-151">を BizTalk グループに追加するコンピューターに次のようにクリックします。**開始**、 をクリックして**すべてのプログラム**、 をクリックして**Microsoft [!INCLUDE[btsBizTalkServer2006r3ui](../includes/btsbiztalkserver2006r3ui-md.md)]** 、 をクリックし、 **BizTalk Server 構成**します。</span><span class="sxs-lookup"><span data-stu-id="f566d-151">On the computer that you want to add to a BizTalk group, click **Start**, click **All Programs**, click **Microsoft [!INCLUDE[btsBizTalkServer2006r3ui](../includes/btsbiztalkserver2006r3ui-md.md)]**, and then click **BizTalk Server Configuration**.</span></span>  

2. <span data-ttu-id="f566d-152">**Microsoft BizTalk Server 2010 構成**、**カスタム構成**します。</span><span class="sxs-lookup"><span data-stu-id="f566d-152">In **Microsoft BizTalk Server 2010 Configuration**, select **Custom configuration**.</span></span>  

3. <span data-ttu-id="f566d-153">**データベース サーバー名**サーバーが参加している BizTalk グループの SQL server の名前を入力します。</span><span class="sxs-lookup"><span data-stu-id="f566d-153">In **Database server name**, type the name of the SQL server for the BizTalk group that the server is joining.</span></span>  

4. <span data-ttu-id="f566d-154">**サービス資格情報**、適切なユーザー名とサービスを使用し、パスワードを入力**構成**します。</span><span class="sxs-lookup"><span data-stu-id="f566d-154">In **Service credential**, type the appropriate user name and password that the services will use, and then click **Configure**.</span></span>  

5. <span data-ttu-id="f566d-155">画面の左側にあるナビゲーション ツリーで、クリックして**エンタープライズ SSO**します。</span><span class="sxs-lookup"><span data-stu-id="f566d-155">In the navigation tree on the left side of the screen, click **Enterprise SSO**.</span></span>  

6. <span data-ttu-id="f566d-156">**エンタープライズ シングル サインオン**] ページで [**既存の SSO システムに参加**します。</span><span class="sxs-lookup"><span data-stu-id="f566d-156">On the **Enterprise Single Sign-On** page, click **Join an existing SSO system**.</span></span>  

   > [!NOTE]  
   >  <span data-ttu-id="f566d-157">サーバー名とデータベース名が、サーバーの参加先 BizTalk グループのマスター SSO データベース サーバーを指していることを確認します。</span><span class="sxs-lookup"><span data-stu-id="f566d-157">Ensure that the server name and database name point to the master SSO database server for the BizTalk group that the server is joining.</span></span>  

7. <span data-ttu-id="f566d-158">画面の左側にあるナビゲーション ツリーで、クリックして**グループ**します。</span><span class="sxs-lookup"><span data-stu-id="f566d-158">In the navigation tree on the left side of the screen, click **Group**.</span></span>  

8. <span data-ttu-id="f566d-159">**グループ**] ページで [**既存の BizTalk グループに参加**します。</span><span class="sxs-lookup"><span data-stu-id="f566d-159">On the **Group** page, click **Join an existing BizTalk Group**.</span></span>  

   > [!NOTE]  
   >  <span data-ttu-id="f566d-160">サーバー名とデータベース名が、サーバーの参加先 BizTalk グループのデータベースをポイントすることを確認します。</span><span class="sxs-lookup"><span data-stu-id="f566d-160">Ensure that the server name and database name point to the databases for the BizTalk group that the server is joining.</span></span>  

9. <span data-ttu-id="f566d-161">メニュー バーでクリックして**構成の適用**このコンピューターでエンタープライズ シングル サインオンとグループの両方を構成します。</span><span class="sxs-lookup"><span data-stu-id="f566d-161">On the menu bar, click **Apply Configuration** to configure both Enterprise Single Sign-On and the group on this computer.</span></span>  

##  <a name="BKMK_Related"></a> <span data-ttu-id="f566d-162">関連項目</span><span class="sxs-lookup"><span data-stu-id="f566d-162">Related Sections</span></span>  

- <span data-ttu-id="f566d-163">ハードウェア RAID で障害が発生したディスクのチェック方法の詳細については、「ディスク プロパティの表示」で、Windows Server 2003 製品ヘルプにあるを参照してください。 [ http://go.microsoft.com/fwlink/?linkid=104161](http://go.microsoft.com/fwlink/?linkid=104161)します。</span><span class="sxs-lookup"><span data-stu-id="f566d-163">For information about checking for failed disks in the hardware RAID, see "View Disk Properties" in the Windows Server 2003 product Help at [http://go.microsoft.com/fwlink/?linkid=104161](http://go.microsoft.com/fwlink/?linkid=104161).</span></span>  

- <span data-ttu-id="f566d-164">手動で中断されたメッセージのチェック方法の詳細についてを参照してください「Investigating オーケストレーション、ポート、およびメッセージのエラー」[!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)]ヘルプ[ http://go.microsoft.com/fwlink/?LinkID=154512](http://go.microsoft.com/fwlink/?LinkID=154512)します。</span><span class="sxs-lookup"><span data-stu-id="f566d-164">For information about manually checking for suspended messages, see "Investigating Orchestration, Port, and Message Failures" in [!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)] Help at [http://go.microsoft.com/fwlink/?LinkID=154512](http://go.microsoft.com/fwlink/?LinkID=154512).</span></span>  

- <span data-ttu-id="f566d-165">各ホストは、少なくとも 2 つの物理 BizTalk サーバーで実行されているインスタンスについては、[BizTalk ホストの高可用性](../technical-guides/high-availability-for-biztalk-hosts.md)を参照してください。</span><span class="sxs-lookup"><span data-stu-id="f566d-165">For information about ensuring that each host has an instance running on at least two physical BizTalk servers, see [High Availability for BizTalk Hosts](../technical-guides/high-availability-for-biztalk-hosts.md).</span></span>  

- <span data-ttu-id="f566d-166">各ホストは、少なくとも 2 つの物理 BizTalk サーバーで実行されているインスタンスについては、[受信ホストをスケール](../technical-guides/scaling-out-receiving-hosts.md)を参照してください。</span><span class="sxs-lookup"><span data-stu-id="f566d-166">For information about ensuring that each host has an instance running on at least two physical BizTalk servers, see [Scaling Out Receiving Hosts](../technical-guides/scaling-out-receiving-hosts.md).</span></span>  

- <span data-ttu-id="f566d-167">クラスター化されたすべてのサービスのフェールオーバーを確認する方法についてはテストされて、参照してください[マスター シークレット サーバーをクラスタ リング](../technical-guides/clustering-the-master-secret-server.md)します。</span><span class="sxs-lookup"><span data-stu-id="f566d-167">For information about ensuring that failover for all clustered services has been tested, see [Clustering the Master Secret Server](../technical-guides/clustering-the-master-secret-server.md).</span></span>  

- <span data-ttu-id="f566d-168">BizTalk データベースが SQL サービスでクラスター化することを確認する方法については、[、BizTalk Server Databases2 をクラスタ リング](../technical-guides/clustering-the-biztalk-server-databases2.md)を参照してください。</span><span class="sxs-lookup"><span data-stu-id="f566d-168">For information about ensuring that the BizTalk databases are clustered under SQL Services, see [Clustering the BizTalk Server Databases2](../technical-guides/clustering-the-biztalk-server-databases2.md).</span></span>  

- <span data-ttu-id="f566d-169">(個別のホストが必要)、不安定なコードが使用されているかどうかを決定する方法の詳細については、[BizTalk ホストの高可用性](../technical-guides/high-availability-for-biztalk-hosts.md)を参照してください。</span><span class="sxs-lookup"><span data-stu-id="f566d-169">For information about determining whether any unstable code is being used (requiring separate hosts), see [High Availability for BizTalk Hosts](../technical-guides/high-availability-for-biztalk-hosts.md).</span></span>  

- <span data-ttu-id="f566d-170">すべての新しい BizTalk アプリケーションの機能テストを実行する方法の詳細については、次を参照してください[アプリケーションのテスト。](../technical-guides/testing-an-application.md)</span><span class="sxs-lookup"><span data-stu-id="f566d-170">For information about performing functional testing of all new BizTalk applications, see [Testing an Application](../technical-guides/testing-an-application.md)</span></span>
