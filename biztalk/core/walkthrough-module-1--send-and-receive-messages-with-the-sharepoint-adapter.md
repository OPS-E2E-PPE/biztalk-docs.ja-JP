---
title: 'チュートリアル: モジュール 1 - 送信および受信メッセージを Windows SharePoint Services アダプター |Microsoft Docs'
ms.custom: ''
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: ''
ms.suite: ''
ms.tgt_pltfrm: ''
ms.topic: article
helpviewer_keywords:
- Windows SharePoint Services, creating sites
- tutorials, Windows SharePoint Services adapters
- Windows SharePoint Services adapter tutorials, receiving messages
- security, Windows SharePoint Services
- creating, Windows SharePoint Services site
- Windows SharePoint Services, security
- Windows SharePoint Services, document libraries
- Windows SharePoint Services adapters, security
- Windows SharePoint Services
- Windows SharePoint Services adapter tutorials, sending messages
ms.assetid: 6494aef5-bb1d-4a41-8186-1d49625a1013
caps.latest.revision: 41
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: 320b64b75bb73e384e2a1af8281e5b578ecf0330
ms.sourcegitcommit: 266308ec5c6a9d8d80ff298ee6051b4843c5d626
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 06/27/2018
ms.locfileid: "36986435"
---
# <a name="walkthrough-module-1---sending-and-receiving-messages-with-the-windows-sharepoint-services-adapter"></a><span data-ttu-id="d1639-102">チュートリアル: モジュール 1 - Windows SharePoint Services アダプターでメッセージを送受信します。</span><span class="sxs-lookup"><span data-stu-id="d1639-102">Walkthrough: Module 1 - Sending and Receiving Messages with the Windows SharePoint Services Adapter</span></span>
<span data-ttu-id="d1639-103">このチュートリアルでは、Windows SharePoint Services アダプターとコンテンツ ベースのルーティング (CBR) を使用してメッセージを送受信できるように Windows SharePoint Services と [!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)] を構成する方法について説明します。</span><span class="sxs-lookup"><span data-stu-id="d1639-103">This walkthrough shows you how to configure Windows SharePoint Services and [!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)] so you can send and receive a message using the Windows SharePoint Services Adapter and content-based routing (CBR).</span></span> <span data-ttu-id="d1639-104">コンテンツ ベースのルーティングを使用すると、特定のポートに正確にバインドされたメッセージに対するメッセージ サブスクリプションが必要ではなくなります。</span><span class="sxs-lookup"><span data-stu-id="d1639-104">Content-based routing eliminates the need for message subscription for messages that are deterministically bound to specific ports.</span></span> <span data-ttu-id="d1639-105">また、エンベロープのプロパティや受信ポートの構成プロパティに基づいてメッセージをルーティングするユーザーにとって、柔軟性も向上します。</span><span class="sxs-lookup"><span data-stu-id="d1639-105">It also provides additional flexibility for users who want to route messages based on envelope properties or simply based on receive port configuration properties.</span></span> <span data-ttu-id="d1639-106">Windows SharePoint Services アダプターの概要については、次を参照してください。 [、Windows SharePoint Services アダプターとは何ですか?](../core/what-is-the-windows-sharepoint-services-adapter.md)します。</span><span class="sxs-lookup"><span data-stu-id="d1639-106">For an introduction to the Windows SharePoint Services adapter, see [What Is the Windows SharePoint Services Adapter?](../core/what-is-the-windows-sharepoint-services-adapter.md).</span></span>  
  
## <a name="prerequisites"></a><span data-ttu-id="d1639-107">前提条件</span><span class="sxs-lookup"><span data-stu-id="d1639-107">Prerequisites</span></span>  
 <span data-ttu-id="d1639-108">このトピックの手順を実行するための前提条件は、次のとおりです。</span><span class="sxs-lookup"><span data-stu-id="d1639-108">The following are prerequisites for performing the procedures in this topic:</span></span>  
  
- <span data-ttu-id="d1639-109">実行されている BizTalk Server の完全なインストールでのシングル サーバー配置する必要があります[!INCLUDE[btsWinSvr2k8](../includes/btswinsvr2k8-md.md)]または[!INCLUDE[btsWinSvr2k8R2](../includes/btswinsvr2k8r2-md.md)]します。</span><span class="sxs-lookup"><span data-stu-id="d1639-109">You must have a single-server deployment with a complete installation of BizTalk Server running on [!INCLUDE[btsWinSvr2k8](../includes/btswinsvr2k8-md.md)] or [!INCLUDE[btsWinSvr2k8R2](../includes/btswinsvr2k8r2-md.md)].</span></span>  
  
  <span data-ttu-id="d1639-110">マルチ サーバー展開で Windows SharePoint Services アダプターを使用する方法の詳細については、次を参照してください。[設定と、Windows SharePoint Services アダプターを展開する](../core/setting-up-and-deploying-the-windows-sharepoint-services-adapter.md)します。</span><span class="sxs-lookup"><span data-stu-id="d1639-110">For information about using the Windows SharePoint Services adapter in a multiserver deployment, see [Setting Up and Deploying the Windows SharePoint Services Adapter](../core/setting-up-and-deploying-the-windows-sharepoint-services-adapter.md).</span></span>  
  
## <a name="configure-windows-sharepoint-services"></a><span data-ttu-id="d1639-111">Windows SharePoint Services を構成します。</span><span class="sxs-lookup"><span data-stu-id="d1639-111">Configure Windows SharePoint Services</span></span>  
 <span data-ttu-id="d1639-112">ここでは、3 つのドキュメント ライブラリが含まれた、トップレベルの SharePoint Web サイトを作成します。</span><span class="sxs-lookup"><span data-stu-id="d1639-112">In this procedure you create a SharePoint top-level Web site that contains three document libraries.</span></span> <span data-ttu-id="d1639-113">Windows SharePoint Services アダプターでは、これらのライブラリを使用して、メッセージをアップロード元のライブラリからアップロード先のライブラリに移動します。</span><span class="sxs-lookup"><span data-stu-id="d1639-113">The Windows SharePoint Services adapter uses these libraries to move a message from a source library to a destination library.</span></span> <span data-ttu-id="d1639-114">このメッセージはドキュメント ライブラリにもアーカイブされます。</span><span class="sxs-lookup"><span data-stu-id="d1639-114">This message is also archived in a document library.</span></span> <span data-ttu-id="d1639-115">このチュートリアルで Windows Sharepoint Services アダプターによってアクセスする Windows SharePoint Services サイトを提供し、このサイトにアクセスするためのユーザー権限を設定するには、次の手順を実行する必要があります。</span><span class="sxs-lookup"><span data-stu-id="d1639-115">This procedure must be done to provide the Windows Sharepoint Services site that is accessed by the Windows Sharepoint Services adapter in this walkthrough and to set user rights to enable access to this site.</span></span>  
  
#### <a name="create-a-windows-sharepoint-services-site"></a><span data-ttu-id="d1639-116">Windows SharePoint Services サイトの作成</span><span class="sxs-lookup"><span data-stu-id="d1639-116">Create a Windows SharePoint Services site</span></span>  
  
1. <span data-ttu-id="d1639-117">クリックして**開始**、 をポイント**すべてのプログラム**、 をポイント**管理ツール**、順にクリックします**SharePoint サーバーの全体管理。**</span><span class="sxs-lookup"><span data-stu-id="d1639-117">Click **Start**, point to **All Programs**, point to **Administrative Tools**, and then click **SharePoint Central Administration.**</span></span>  
  
2. <span data-ttu-id="d1639-118">[**仮想サーバーの構成**、] をクリックして**トップレベル Web サイトの作成**です。</span><span class="sxs-lookup"><span data-stu-id="d1639-118">Under **Virtual Server Configuration**, click **Create a top-level Web site**.</span></span>  
  
3. <span data-ttu-id="d1639-119">**仮想サーバーのリスト**に、Windows SharePoint Services アダプターをインストールした Web サイトを選択します。</span><span class="sxs-lookup"><span data-stu-id="d1639-119">Under **Virtual Server List**, select the Web site that you installed the Windows SharePoint Services Adapter on.</span></span> <span data-ttu-id="d1639-120">たとえば、 `Default Web Site`のようにします。</span><span class="sxs-lookup"><span data-stu-id="d1639-120">For example, `Default Web Site`.</span></span>  
  
4. <span data-ttu-id="d1639-121">**Web サイトのアドレス**セクションで、 **URL 名**フィールドに「`WSSAdapterWalkthrough`します。</span><span class="sxs-lookup"><span data-stu-id="d1639-121">In the **Web Site Address** section, in the **URL name** field, type `WSSAdapterWalkthrough`.</span></span>  
  
5. <span data-ttu-id="d1639-122">**サイト コレクションの所有者**セクションで、**ユーザー名フィールド、** ユーザー名を入力します。</span><span class="sxs-lookup"><span data-stu-id="d1639-122">In the **Site Collection Owner** section, in the **User name field,** type a user name.</span></span> <span data-ttu-id="d1639-123">このユーザーが Web サイトの所有者になります。[!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)] の特別なアクセス許可は必要ありません。</span><span class="sxs-lookup"><span data-stu-id="d1639-123">This user will be the owner for the Web site and does not need special permissions in [!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)].</span></span>  
  
6. <span data-ttu-id="d1639-124">**サイト コレクションの所有者**セクションで、**電子メール**フィールドに、電子メール アドレスを入力します。</span><span class="sxs-lookup"><span data-stu-id="d1639-124">In the **Site Collection Owner** section, in the **E-mail** field, type in an e-mail address.</span></span>  
  
7. <span data-ttu-id="d1639-125">**[OK]** をクリックします。</span><span class="sxs-lookup"><span data-stu-id="d1639-125">Click **OK**.</span></span>  
  
8. <span data-ttu-id="d1639-126">**最上位サイトが正常に作成された** ページで、先ほど作成した新しいトップレベル Web サイトをクリックします。</span><span class="sxs-lookup"><span data-stu-id="d1639-126">On the **Top-Level Site Successfully Created** page, click the new top-level Web site you just created.</span></span> <span data-ttu-id="d1639-127">たとえば、 `http://<server_name>/sites/WSSAdapterWalkthrough`のようにします。</span><span class="sxs-lookup"><span data-stu-id="d1639-127">For example, `http://<server_name>/sites/WSSAdapterWalkthrough`.</span></span>  
  
9. <span data-ttu-id="d1639-128">選択、**チーム サイト**クリックして、テンプレートの一覧からテンプレート**OK**します。</span><span class="sxs-lookup"><span data-stu-id="d1639-128">Select the **Team Site** template from the list of templates, and then click **OK**.</span></span> <span data-ttu-id="d1639-129">これにより、チーム Web サイトのホーム ページが開きます。</span><span class="sxs-lookup"><span data-stu-id="d1639-129">This will open the Team Web Site Home page.</span></span>  
  
#### <a name="create-a-source-document-library"></a><span data-ttu-id="d1639-130">"アップロード元" のドキュメント ライブラリの作成</span><span class="sxs-lookup"><span data-stu-id="d1639-130">Create a "Source" document library</span></span>  
  
1.  <span data-ttu-id="d1639-131">チーム Web サイトのホーム ページで、上部のナビゲーション バーで、次のようにクリックします。**作成**です。</span><span class="sxs-lookup"><span data-stu-id="d1639-131">On the Team Web Site Home page, on the top navigation bar, click **Create**.</span></span>  
  
2.  <span data-ttu-id="d1639-132">[**ドキュメント ライブラリ**、] をクリックして**ドキュメント ライブラリ**します。</span><span class="sxs-lookup"><span data-stu-id="d1639-132">Under **Document Libraries**, click **Document Library**.</span></span>  
  
3.  <span data-ttu-id="d1639-133">**名前と説明**セクションで、**名前 フィールドに**型`Source`します。</span><span class="sxs-lookup"><span data-stu-id="d1639-133">In the **Name and Description** section, in the **Name field,** type `Source`.</span></span>  
  
4.  <span data-ttu-id="d1639-134">**ナビゲーション**セクションで、**はい**このフォーム ライブラリをクイック起動バーに表示します。</span><span class="sxs-lookup"><span data-stu-id="d1639-134">In the **Navigation** section, select **Yes** to display this form library on the Quick Launch bar.</span></span>  
  
5.  <span data-ttu-id="d1639-135">**ドキュメント テンプレート**セクションで、**ドキュメント テンプレート**ドロップダウン リストで、`None`します。</span><span class="sxs-lookup"><span data-stu-id="d1639-135">In the **Document Template** section, in the **Document Template** drop-down list, select `None`.</span></span>  
  
6.  <span data-ttu-id="d1639-136">**[作成]** をクリックします。</span><span class="sxs-lookup"><span data-stu-id="d1639-136">Click **Create**.</span></span> <span data-ttu-id="d1639-137">ドキュメント ライブラリが作成され、空のライブラリにリダイレクトされます。</span><span class="sxs-lookup"><span data-stu-id="d1639-137">The document library will be created and you will be redirected to the empty library.</span></span>  
  
#### <a name="create-a-destination-document-library"></a><span data-ttu-id="d1639-138">"アップロード先" のドキュメント ライブラリの作成</span><span class="sxs-lookup"><span data-stu-id="d1639-138">Create a "Destination" document library</span></span>  
  
1.  <span data-ttu-id="d1639-139">チーム Web サイトのホーム ページで、上部のナビゲーション バーで、次のようにクリックします。**作成**です。</span><span class="sxs-lookup"><span data-stu-id="d1639-139">On the Team Web Site Home page, on the top navigation bar, click **Create**.</span></span>  
  
2.  <span data-ttu-id="d1639-140">[**ドキュメント ライブラリ**、] をクリックして**ドキュメント ライブラリ**します。</span><span class="sxs-lookup"><span data-stu-id="d1639-140">Under **Document Libraries**, click **Document Library**.</span></span>  
  
3.  <span data-ttu-id="d1639-141">**名前と説明**セクションで、**名前フィールド**、型`Destination`します。</span><span class="sxs-lookup"><span data-stu-id="d1639-141">In the **Name and Description** section, in the **Name field**, type `Destination`.</span></span>  
  
4.  <span data-ttu-id="d1639-142">**ナビゲーション**セクションで、**はい**このフォーム ライブラリをクイック起動バーに表示します。</span><span class="sxs-lookup"><span data-stu-id="d1639-142">In the **Navigation** section, select **Yes** to display this form library on the Quick Launch bar.</span></span>  
  
5.  <span data-ttu-id="d1639-143">**ドキュメント テンプレート**セクションで、**ドキュメント テンプレート**ドロップダウン リストで、`None`します。</span><span class="sxs-lookup"><span data-stu-id="d1639-143">In the **Document Template** section, in the **Document Template** drop-down list, select `None`.</span></span>  
  
6.  <span data-ttu-id="d1639-144">**[作成]** をクリックします。</span><span class="sxs-lookup"><span data-stu-id="d1639-144">Click **Create**.</span></span> <span data-ttu-id="d1639-145">ドキュメント ライブラリが作成され、空のライブラリにリダイレクトされます。</span><span class="sxs-lookup"><span data-stu-id="d1639-145">The document library will be created and you will be redirected to the empty library.</span></span>  
  
#### <a name="create-an-archive-document-library"></a><span data-ttu-id="d1639-146">"アーカイブ" ドキュメント ライブラリの作成</span><span class="sxs-lookup"><span data-stu-id="d1639-146">Create an "Archive" document library</span></span>  
  
1.  <span data-ttu-id="d1639-147">チーム Web サイトのホーム ページで、上部のナビゲーション バーで、次のようにクリックします。**作成**です。</span><span class="sxs-lookup"><span data-stu-id="d1639-147">On the Team Web Site Home page, on the top navigation bar, click **Create**.</span></span>  
  
2.  <span data-ttu-id="d1639-148">[**ドキュメント ライブラリ**、] をクリックして**ドキュメント ライブラリ**します。</span><span class="sxs-lookup"><span data-stu-id="d1639-148">Under **Document Libraries**, click **Document Library**.</span></span>  
  
3.  <span data-ttu-id="d1639-149">**名前**し、[説明] セクションで、**名前フィールド**、型`Archive`します。</span><span class="sxs-lookup"><span data-stu-id="d1639-149">In the **Name** and Description section, in the **Name field**, type `Archive`.</span></span>  
  
4.  <span data-ttu-id="d1639-150">**ナビゲーション**セクションで、**はい**このフォーム ライブラリをクイック起動バーに表示します。</span><span class="sxs-lookup"><span data-stu-id="d1639-150">In the **Navigation** section, select **Yes** to display this form library on the Quick Launch bar.</span></span>  
  
5.  <span data-ttu-id="d1639-151">**ドキュメント テンプレート**セクションで、**ドキュメント テンプレート**ドロップダウン リストで、`None`します。</span><span class="sxs-lookup"><span data-stu-id="d1639-151">In the **Document Template** section, in the **Document Template** drop-down list, select `None`.</span></span>  
  
6.  <span data-ttu-id="d1639-152">**[作成]** をクリックします。</span><span class="sxs-lookup"><span data-stu-id="d1639-152">Click **Create**.</span></span> <span data-ttu-id="d1639-153">ドキュメント ライブラリが作成され、空のライブラリにリダイレクトされます。</span><span class="sxs-lookup"><span data-stu-id="d1639-153">The document library will be created and you will be redirected to the empty library.</span></span>  
  
7.  <span data-ttu-id="d1639-154">`WSSAdapterWalkthrough` Web サイトを閉じます。</span><span class="sxs-lookup"><span data-stu-id="d1639-154">Close the `WSSAdapterWalkthrough` Web site.</span></span>  
  
8.  <span data-ttu-id="d1639-155">閉じる、 **SharePoint Central Administration** Web サイト。</span><span class="sxs-lookup"><span data-stu-id="d1639-155">Close the **SharePoint Central Administration** Web site.</span></span>  
  
#### <a name="configure-windows-security"></a><span data-ttu-id="d1639-156">Windows セキュリティの構成</span><span class="sxs-lookup"><span data-stu-id="d1639-156">Configure Windows security</span></span>  
  
1.  <span data-ttu-id="d1639-157">をクリックして**開始**、 をポイント**すべてのプログラム**、 をポイント**管理ツール**、順にクリックします**コンピュータの管理**します。</span><span class="sxs-lookup"><span data-stu-id="d1639-157">Click **Start**, point to **All Programs**, point to **Administrative Tools**, and then click **Computer Management**.</span></span>  
  
2.  <span data-ttu-id="d1639-158">コンソール ツリーで、展開**ローカル ユーザーとグループ**、 をクリックし、**グループ**します。</span><span class="sxs-lookup"><span data-stu-id="d1639-158">In the console tree, expand **Local Users and Groups**, and then click **Groups**.</span></span>  
  
3.  <span data-ttu-id="d1639-159">右クリックし、 **SharePoint Enabled Hosts**グループで、[**をグループに追加**、] をクリックし、**追加**します。</span><span class="sxs-lookup"><span data-stu-id="d1639-159">Right-click the **SharePoint Enabled Hosts** group, click **Add to Group**, and then click **Add**.</span></span>  
  
4.  <span data-ttu-id="d1639-160">** ダイアログ ボックスの ユーザー、コンピューター、またはグループ****を選択するオブジェクト名の入力**をクリックして、実行には、BizTalk Server ホスト インスタンスを構成したアカウントの名前を入力**OK**します。</span><span class="sxs-lookup"><span data-stu-id="d1639-160">In the **Select Users, Computers, or Groups dialog box**, under **Enter the object names to select**, type the name of the account that you configured the BizTalk Server Host Instance to run under, and then click **OK**.</span></span>  
  
5.  <span data-ttu-id="d1639-161">コンソール ツリーで、展開**サービスとアプリケーション**、 をクリックし、**サービス**します。</span><span class="sxs-lookup"><span data-stu-id="d1639-161">In the console tree, expand **Services and Applications**, and then click **Services**.</span></span>  
  
6.  <span data-ttu-id="d1639-162">右クリック**BizTalk Service BizTalk Group: < biztalk ホスト名 >**、 をクリックし、**再起動**します。</span><span class="sxs-lookup"><span data-stu-id="d1639-162">Right-click **BizTalk Service BizTalk Group: <BizTalk_Host_Name>**, and then click **Restart**.</span></span>  
  
    > [!NOTE]
    >  <span data-ttu-id="d1639-163"><BizTalk ホスト名> は、ホストの名前です。</span><span class="sxs-lookup"><span data-stu-id="d1639-163"><BizTalk_Host_Name> is the name of your host.</span></span> <span data-ttu-id="d1639-164">既定では `BizTalkServerApplication` です。</span><span class="sxs-lookup"><span data-stu-id="d1639-164">By Default, this is `BizTalkServerApplication`.</span></span>  
  
    > [!NOTE]
    >  <span data-ttu-id="d1639-165">サービスを再起動するまで、メンバーシップは有効になりません。</span><span class="sxs-lookup"><span data-stu-id="d1639-165">Membership does not take effect until the service is restarted.</span></span>  
  
7.  <span data-ttu-id="d1639-166">閉じる**コンピュータの管理**します。</span><span class="sxs-lookup"><span data-stu-id="d1639-166">Close **Computer Management**.</span></span>  
  
#### <a name="configure-sharepoint-security"></a><span data-ttu-id="d1639-167">SharePoint セキュリティの構成</span><span class="sxs-lookup"><span data-stu-id="d1639-167">Configure SharePoint security</span></span>  
  
1. <span data-ttu-id="d1639-168">Web ブラウザを開き、作成したサイトの URL に移動します。</span><span class="sxs-lookup"><span data-stu-id="d1639-168">Open a Web browser and navigate to the URL of the site you created.</span></span> <span data-ttu-id="d1639-169">たとえば、 `http://<server_name>/sites/WSSAdapterWalkthrough`のようにします。</span><span class="sxs-lookup"><span data-stu-id="d1639-169">For example, `http://<server_name>/sites/WSSAdapterWalkthrough`.</span></span>  
  
2. <span data-ttu-id="d1639-170">チーム Web サイトのホーム ページで、上部のナビゲーション バーで、次のようにクリックします。**サイト設定**します。</span><span class="sxs-lookup"><span data-stu-id="d1639-170">On the Team Web Site Home page, on the top navigation bar, click **Site Settings**.</span></span>  
  
3. <span data-ttu-id="d1639-171">[**管理**、] をクリックして**ユーザーを管理する**します。</span><span class="sxs-lookup"><span data-stu-id="d1639-171">Under **Administration**, click **Manage users**.</span></span>  
  
4. <span data-ttu-id="d1639-172">**[ユーザーの追加]** をクリックします。</span><span class="sxs-lookup"><span data-stu-id="d1639-172">Click **Add Users**.</span></span>  
  
5. <span data-ttu-id="d1639-173">**手順 1: ユーザーの選択**、アカウントの名前を入力する、[!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)]ホスト インスタンスを実行しています。</span><span class="sxs-lookup"><span data-stu-id="d1639-173">In **Step 1: Choose Users**, type the name of the account that the [!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)] Host Instance is running under.</span></span>  
  
6. <span data-ttu-id="d1639-174">**手順 2: サイト グループの選択**を選択、**リーダー**と**共同作成者**チェック ボックス。</span><span class="sxs-lookup"><span data-stu-id="d1639-174">In **Step 2: Choose Site Groups**, select the **Reader** and **Contributor** check boxes.</span></span>  
  
7. <span data-ttu-id="d1639-175">**[次へ]** をクリックします。</span><span class="sxs-lookup"><span data-stu-id="d1639-175">Click **Next**.</span></span>  
  
8. <span data-ttu-id="d1639-176">クリア、**が追加されたことがあるので、これらのユーザーを通知する次のメールを送信**チェック ボックスをオンにして**完了**します。</span><span class="sxs-lookup"><span data-stu-id="d1639-176">Clear the **Send the following e-mail to let these users now they've been added** check box, and then click **Finish**.</span></span>  
  
9. <span data-ttu-id="d1639-177">`WSSAdapterWalkthrough` Web サイトを閉じます。</span><span class="sxs-lookup"><span data-stu-id="d1639-177">Close the `WSSAdapterWalkthrough` Web site.</span></span>  
  
## <a name="create-and-configure-the-biztalk-server-ports"></a><span data-ttu-id="d1639-178">BizTalk Server のポートの作成と構成</span><span class="sxs-lookup"><span data-stu-id="d1639-178">Create and configure the BizTalk Server ports</span></span>  
 <span data-ttu-id="d1639-179">ここでは、Windows SharePoint Services アダプター用に、[!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)] の受信ポート、受信場所、および送信ポートを作成および構成します。</span><span class="sxs-lookup"><span data-stu-id="d1639-179">In this procedure you will create and configure the [!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)] receive ports, receive locations, and send ports for the Windows SharePoint Services adapter.</span></span> <span data-ttu-id="d1639-180">これらのポートは、Windows Sharepoint Services アダプターによって送受信されたドキュメントが [!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)] で送受信される際のエントリ ポイントです。</span><span class="sxs-lookup"><span data-stu-id="d1639-180">These ports are points of entry into and out of [!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)] for documents received and sent by the Windows Sharepoint Services adapter.</span></span>  
  
#### <a name="create-the-receive-port"></a><span data-ttu-id="d1639-181">受信ポートの作成</span><span class="sxs-lookup"><span data-stu-id="d1639-181">Create the receive port</span></span>  
  
1. <span data-ttu-id="d1639-182">クリックして**開始**、**すべてのプログラム**、 [!INCLUDE[btsBizTalkServerStartMenuItemui](../includes/btsbiztalkserverstartmenuitemui-md.md)]、順にクリックします**BizTalk Server 管理コンソール。**</span><span class="sxs-lookup"><span data-stu-id="d1639-182">Click **Start**, **All Programs**, [!INCLUDE[btsBizTalkServerStartMenuItemui](../includes/btsbiztalkserverstartmenuitemui-md.md)], and then click **BizTalk Server Administration.**</span></span>  
  
2. <span data-ttu-id="d1639-183">展開[!INCLUDE[btsBizTalkServerAdminConsoleui](../includes/btsbiztalkserveradminconsoleui-md.md)]、展開**BizTalk グループ**、展開**アプリケーション**、展開**BizTalk アプリケーション 1**、右クリックして**の受信ポート**、 をクリックして**新規**、 をクリックし、**一方向の受信ポート.**</span><span class="sxs-lookup"><span data-stu-id="d1639-183">Expand [!INCLUDE[btsBizTalkServerAdminConsoleui](../includes/btsbiztalkserveradminconsoleui-md.md)], expand **BizTalk Group**, expand **Applications**, expand **BizTalk Application 1**, right-click **Receive Ports**, click **New**, and then click **One-way Receive Port…**</span></span>  
  
3. <span data-ttu-id="d1639-184">**受信ポートのプロパティ**ダイアログ ボックスで、**全般**、型`FromSource`で、**名前**フィールド。</span><span class="sxs-lookup"><span data-stu-id="d1639-184">In the **Receive Port Properties** dialog box, under **General**, type `FromSource` in the **Name** field.</span></span>  
  
4. <span data-ttu-id="d1639-185">**[OK]** をクリックします。</span><span class="sxs-lookup"><span data-stu-id="d1639-185">Click **OK**.</span></span>  
  
#### <a name="create-the-receive-location"></a><span data-ttu-id="d1639-186">受信場所を作成します。</span><span class="sxs-lookup"><span data-stu-id="d1639-186">Create the receive location</span></span>  
  
1.  <span data-ttu-id="d1639-187">**BizTalk 管理コンソール**を右クリックし、**受信場所**ノード、をクリックして**新規**、順にクリックします**一方向の受信場所**.</span><span class="sxs-lookup"><span data-stu-id="d1639-187">In the **BizTalk Administration Console**, right-click the **Receive Locations** node, click **New**, and then click **One-way Receive Location**.</span></span>  
  
2.  <span data-ttu-id="d1639-188">**受信ポートの選択**ダイアログ ボックスで、 `FromSource`、 をクリックし、 **OK**。</span><span class="sxs-lookup"><span data-stu-id="d1639-188">In the **Select a Receive Port** dialog box, select `FromSource`, and then click **OK**.</span></span>  
  
3.  <span data-ttu-id="d1639-189">**受信場所のプロパティ**ダイアログ ボックスで、**全般**、型`SourceLocation`で、**名前**フィールド。</span><span class="sxs-lookup"><span data-stu-id="d1639-189">In the **Receive Location Properties** dialog box, under **General**, type `SourceLocation` in the **Name** field.</span></span>  
  
4.  <span data-ttu-id="d1639-190">**トランスポート**セクションで、**型**ドロップダウン リストで、`Windows``SharePoint``Services`します。</span><span class="sxs-lookup"><span data-stu-id="d1639-190">In the **Transport** section, in the **Type** drop-down list, select `Windows``SharePoint``Services`.</span></span>  
  
5.  <span data-ttu-id="d1639-191">クリックして**構成**Windows SharePoint Services アダプターのプロパティを構成します。</span><span class="sxs-lookup"><span data-stu-id="d1639-191">Click **Configure** to configure the Windows SharePoint Services adapter properties.</span></span>  
  
6.  <span data-ttu-id="d1639-192">**アダプター Web サービス ポート**プロパティでは、Windows SharePoint Services アダプター Web サービスがインストールされている仮想サーバーのポート番号を入力します。</span><span class="sxs-lookup"><span data-stu-id="d1639-192">In the **Adapter Web Service Port** property, type the port number of the virtual server where the Windows SharePoint Services adapter Web service was installed.</span></span> <span data-ttu-id="d1639-193">既定では、ポート 80 です。</span><span class="sxs-lookup"><span data-stu-id="d1639-193">By default, this is port 80.</span></span>  
  
7.  <span data-ttu-id="d1639-194">型`Archive`で、**アーカイブ場所**プロパティ。</span><span class="sxs-lookup"><span data-stu-id="d1639-194">Type `Archive` in the **Archive Location** property.</span></span>  
  
8.  <span data-ttu-id="d1639-195">型`10`で、**のポーリング間隔**プロパティ。</span><span class="sxs-lookup"><span data-stu-id="d1639-195">Type `10` in the **Polling Interval** property.</span></span>  
  
9. <span data-ttu-id="d1639-196">SharePoint サイトに URL を入力、 **ShareP**ポイント サイトの Url プロパティです。</span><span class="sxs-lookup"><span data-stu-id="d1639-196">Type the URL to your SharePoint site in the **ShareP**oint Site Url property.</span></span> <span data-ttu-id="d1639-197">たとえば、 `http://<server_name>/sites/WSSAdapterWalkthrough`のようにします。</span><span class="sxs-lookup"><span data-stu-id="d1639-197">For example, `http://<server_name>/sites/WSSAdapterWalkthrough`.</span></span>  
  
10. <span data-ttu-id="d1639-198">型`Source`の**ソース ドキュメント ライブラリ**プロパティ。</span><span class="sxs-lookup"><span data-stu-id="d1639-198">Type `Source` for the **Source Document Library** property.</span></span>  
  
11. <span data-ttu-id="d1639-199">**[OK]** をクリックします。</span><span class="sxs-lookup"><span data-stu-id="d1639-199">Click **OK**.</span></span>  
  
12. <span data-ttu-id="d1639-200">**受信場所のプロパティ**ダイアログ ボックスで、`BizTalkServerApplication`として、**受信ハンドラー**します。</span><span class="sxs-lookup"><span data-stu-id="d1639-200">In the **Receive Location Properties** dialog box, select `BizTalkServerApplication` as the **Receive handler**.</span></span>  
  
13. <span data-ttu-id="d1639-201">**受信パイプライン**ドロップダウン リストで、`PassThruReceive`します。</span><span class="sxs-lookup"><span data-stu-id="d1639-201">In the **Receive pipeline** drop-down list, select `PassThruReceive`.</span></span>  
  
14. <span data-ttu-id="d1639-202">**[OK]** をクリックします。</span><span class="sxs-lookup"><span data-stu-id="d1639-202">Click **OK**.</span></span>  
  
#### <a name="create-the-send-port"></a><span data-ttu-id="d1639-203">送信ポートを作成します。</span><span class="sxs-lookup"><span data-stu-id="d1639-203">Create the send port</span></span>  
  
1.  <span data-ttu-id="d1639-204">**BizTalk 管理コンソール**を右クリックし、**送信ポート**ノード、をクリックして**新規**、順にクリックします**静的な一方向送信ポート**.</span><span class="sxs-lookup"><span data-stu-id="d1639-204">In the **BizTalk Administration Console**, right-click the **Send Ports** node, click **New**, and then click **Static One-way Send Port**.</span></span>  
  
2.  <span data-ttu-id="d1639-205">**送信ポートのプロパティ**ダイアログ ボックスで、**全般**、型`SendToDestination`で、**名前**フィールド。</span><span class="sxs-lookup"><span data-stu-id="d1639-205">In the **Send Port Properties** dialog box, under **General**, type `SendToDestination` in the **Name** field.</span></span>  
  
3.  <span data-ttu-id="d1639-206">**トランスポート**セクションで、`Windows SharePoint Services`型。</span><span class="sxs-lookup"><span data-stu-id="d1639-206">In the **Transport** section, select `Windows SharePoint Services` for the type.</span></span>  
  
4.  <span data-ttu-id="d1639-207">クリックして**構成**Windows SharePoint Services アダプターのプロパティを構成します。</span><span class="sxs-lookup"><span data-stu-id="d1639-207">Click **Configure** to configure the Windows SharePoint Services adapter properties.</span></span>  
  
5.  <span data-ttu-id="d1639-208">**アダプター Web サービス ポート**プロパティでは、Windows SharePoint Services アダプター Web サービスがインストールされている仮想サーバーのポート番号を入力します。</span><span class="sxs-lookup"><span data-stu-id="d1639-208">In the **Adapter Web Service Port** property, type the port number of the virtual server where the Windows SharePoint Services adapter Web service was installed.</span></span> <span data-ttu-id="d1639-209">既定では、ポート 80 です。</span><span class="sxs-lookup"><span data-stu-id="d1639-209">By default, this is port 80.</span></span>  
  
6.  <span data-ttu-id="d1639-210">入力`Destination`の**先フォルダー**プロパティ。</span><span class="sxs-lookup"><span data-stu-id="d1639-210">Type in `Destination` for the **Destination Folder** property.</span></span>  
  
7.  <span data-ttu-id="d1639-211">入力`PurchaseOrder1-%MessageID%.xml`の**Filename**プロパティ。</span><span class="sxs-lookup"><span data-stu-id="d1639-211">Type in `PurchaseOrder1-%MessageID%.xml` for the **Filename** property.</span></span>  
  
8.  <span data-ttu-id="d1639-212">設定、**上書き**プロパティを`Yes`します。</span><span class="sxs-lookup"><span data-stu-id="d1639-212">Set the **Overwrite** property to `Yes`.</span></span>  
  
9. <span data-ttu-id="d1639-213">SharePoint サイトに URL を入力、 **SharePoint サイトの Url**プロパティ。</span><span class="sxs-lookup"><span data-stu-id="d1639-213">Type in the URL to your SharePoint site in the **SharePoint Site Url** property.</span></span> <span data-ttu-id="d1639-214">たとえば、 `http://<server_name>/sites/WSSAdapterWalkthrough`のようにします。</span><span class="sxs-lookup"><span data-stu-id="d1639-214">For example, `http://<server_name>/sites/WSSAdapterWalkthrough`.</span></span>  
  
10. <span data-ttu-id="d1639-215">設定、 **Microsoft Office 統合**プロパティを`No`します。</span><span class="sxs-lookup"><span data-stu-id="d1639-215">Set the **Microsoft Office Integration** property to `No`.</span></span>  
  
11. <span data-ttu-id="d1639-216">**[OK]** をクリックします。</span><span class="sxs-lookup"><span data-stu-id="d1639-216">Click **OK**.</span></span>  
  
12. <span data-ttu-id="d1639-217">**送信ポートのプロパティ ダイアログ ボックス**の**送信ハンドラー**ドロップダウン リストで、`BizTalkServerApplication`します。</span><span class="sxs-lookup"><span data-stu-id="d1639-217">In the **Send Port Properties dialog box**, in the **Send handler** drop-down list, select `BizTalkServerApplication`.</span></span>  
  
13. <span data-ttu-id="d1639-218">**送信パイプライン**ドロップダウン リストで、`PassThruTransmit`します。</span><span class="sxs-lookup"><span data-stu-id="d1639-218">In the **Send pipeline** drop-down list, select `PassThruTransmit`.</span></span>  
  
14. <span data-ttu-id="d1639-219">をクリックして、**フィルター**タブ。</span><span class="sxs-lookup"><span data-stu-id="d1639-219">Click the **Filters** tab.</span></span>  
  
15. <span data-ttu-id="d1639-220">選択`WSS.InListName`で、**プロパティ**フィールド。</span><span class="sxs-lookup"><span data-stu-id="d1639-220">Select `WSS.InListName` in the **Property** field.</span></span>  
  
16. <span data-ttu-id="d1639-221">選択`==`で、**演算子**フィールド。</span><span class="sxs-lookup"><span data-stu-id="d1639-221">Select `==` in the **Operator** field.</span></span>  
  
17. <span data-ttu-id="d1639-222">型`Source`で、**値**フィールド。</span><span class="sxs-lookup"><span data-stu-id="d1639-222">Type `Source` in the **Value** field.</span></span>  
  
18. <span data-ttu-id="d1639-223">**[OK]** をクリックします。</span><span class="sxs-lookup"><span data-stu-id="d1639-223">Click **OK**.</span></span>  
  
## <a name="enable-and-start-the-receive-location-and-receive-port"></a><span data-ttu-id="d1639-224">受信場所と受信ポートの有効化と開始</span><span class="sxs-lookup"><span data-stu-id="d1639-224">Enable and start the receive location and receive port</span></span>  
 <span data-ttu-id="d1639-225">ここでは、受信場所を有効にし、受信ポートを開始します。</span><span class="sxs-lookup"><span data-stu-id="d1639-225">In these procedures you enable the receive location and start the receive port.</span></span> <span data-ttu-id="d1639-226">Windows Sharepoint Services アダプターが指定された送信ポートおよび受信場所を使用してメッセージを送受信できるようにするには、次の手順を完了する必要があります。</span><span class="sxs-lookup"><span data-stu-id="d1639-226">This procedure must be completed to allow the Windows Sharepoint Services adapter to send and receive messages through the specified send port and receive location.</span></span>  
  
#### <a name="enable-the-receive-location"></a><span data-ttu-id="d1639-227">受信場所の有効化</span><span class="sxs-lookup"><span data-stu-id="d1639-227">Enable the receive location</span></span>  
  
1.  <span data-ttu-id="d1639-228">**BizTalk 管理コンソール**、クリックして、**受信場所**ノード。</span><span class="sxs-lookup"><span data-stu-id="d1639-228">In the **BizTalk Administration Console**, click the **Receive Locations** node.</span></span>  
  
2.  <span data-ttu-id="d1639-229">右クリックして`SourceLocation`、 をクリックし、**を有効にする**します。</span><span class="sxs-lookup"><span data-stu-id="d1639-229">Right-click `SourceLocation`, and then click **Enable**.</span></span>  
  
#### <a name="start-the-send-port"></a><span data-ttu-id="d1639-230">送信ポートの開始</span><span class="sxs-lookup"><span data-stu-id="d1639-230">Start the send port</span></span>  
  
1.  <span data-ttu-id="d1639-231">**BizTalk 管理コンソール**、クリックして、**送信ポート**ノード。</span><span class="sxs-lookup"><span data-stu-id="d1639-231">In the **BizTalk Administration Console**, click the **Send Ports** node.</span></span>  
  
2.  <span data-ttu-id="d1639-232">右クリック`SendToDestination`、 をクリックし、**開始**します。</span><span class="sxs-lookup"><span data-stu-id="d1639-232">Right-click `SendToDestination`, and then click **Start**.</span></span>  
  
3.  <span data-ttu-id="d1639-233">閉じる、 **BizTalk 管理コンソール**します。</span><span class="sxs-lookup"><span data-stu-id="d1639-233">Close the **BizTalk Administration Console**.</span></span>  
  
## <a name="sending-a-message-through-the-system"></a><span data-ttu-id="d1639-234">システムからのメッセージを送信します。</span><span class="sxs-lookup"><span data-stu-id="d1639-234">Sending a message through the system</span></span>  
 <span data-ttu-id="d1639-235">ここでは、XML ドキュメントを作成し、Windows SharePoint Services Web サイトにアップロードします。</span><span class="sxs-lookup"><span data-stu-id="d1639-235">In this procedure you create an XML document and upload it to the Windows SharePoint Services Web site.</span></span> <span data-ttu-id="d1639-236">そのメッセージは Windows SharePoint Services アダプターによって取得され、アーカイブ ドキュメント ライブラリにアーカイブされた後、アップロード先のドキュメント ライブラリに送信されます。</span><span class="sxs-lookup"><span data-stu-id="d1639-236">The Windows SharePoint Services adapter will take that message, archive it in the Archive document library, and then send it to the Destination document library.</span></span> <span data-ttu-id="d1639-237">この手順は、Windows SharePoint Services アダプターを使用し、SharePoint Web サイトから、[!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)] を経由して SharePoint サービス Web サイトへと送信されるドキュメント フローを示しています。</span><span class="sxs-lookup"><span data-stu-id="d1639-237">This procedure demonstrates how a document flows from a Sharepoint web site, through [!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)], and to a Sharepoint Services Web site using the Windows Sharepoint Services adapter.</span></span>  
  
#### <a name="create-a-working-directory"></a><span data-ttu-id="d1639-238">作業ディレクトリの作成</span><span class="sxs-lookup"><span data-stu-id="d1639-238">Create a working directory</span></span>  
  
-   <span data-ttu-id="d1639-239">呼ばれるコンピューターにディレクトリを作成**WSSAdapterWalkthrough**します。</span><span class="sxs-lookup"><span data-stu-id="d1639-239">Create a directory on your computer called **WSSAdapterWalkthrough**.</span></span> <span data-ttu-id="d1639-240">たとえば、 `C:\WSSAdapterWalkthrough`のようにします。</span><span class="sxs-lookup"><span data-stu-id="d1639-240">For example, `C:\WSSAdapterWalkthrough`.</span></span>  
  
#### <a name="create-an-xml-file"></a><span data-ttu-id="d1639-241">XML ファイルを作成します。</span><span class="sxs-lookup"><span data-stu-id="d1639-241">Create an XML file</span></span>  
  
1.  <span data-ttu-id="d1639-242">をクリックして**開始**、 をポイント**すべてのプログラム**、 をポイント**アクセサリ**、順にクリックします**メモ帳。**</span><span class="sxs-lookup"><span data-stu-id="d1639-242">Click **Start**, point to **All Programs**, point to **Accessories**, and then click **Notepad.**</span></span>  
  
2.  <span data-ttu-id="d1639-243">次のように入力します。</span><span class="sxs-lookup"><span data-stu-id="d1639-243">Type the following:</span></span>  
  
    ```  
    <?xml version="1.0"?>  
    <PurchaseOrder>  
        <ID>1001</ID>  
        <FirstName>John</FirstName>  
        <LastName>Doe</LastName>  
        <Amount>750</Amount>  
    </PurchaseOrder>  
    ```  
  
3.  <span data-ttu-id="d1639-244">このファイルを `PurchaseOrder1.xml` という名前で作業ディレクトリに保存します。</span><span class="sxs-lookup"><span data-stu-id="d1639-244">Save the file in your working directory as `PurchaseOrder1.xml`.</span></span> <span data-ttu-id="d1639-245">たとえば、 `C:\WSSAdapterWalkthrough\PurchaseOrder1.xml`のようにします。</span><span class="sxs-lookup"><span data-stu-id="d1639-245">For example, `C:\WSSAdapterWalkthrough\PurchaseOrder1.xml`.</span></span>  
  
#### <a name="upload-the-xml-file"></a><span data-ttu-id="d1639-246">XML ファイルのアップロード</span><span class="sxs-lookup"><span data-stu-id="d1639-246">Upload the XML file</span></span>  
  
1. <span data-ttu-id="d1639-247">Web ブラウザーを開き、前の作業で作成したサイトの URL に移動します。</span><span class="sxs-lookup"><span data-stu-id="d1639-247">Open a Web browser and navigate to the URL of the site you created in the last task.</span></span> <span data-ttu-id="d1639-248">たとえば、 `http://<server_name>/sites/WSSAdapterWalkthrough`のようにします。</span><span class="sxs-lookup"><span data-stu-id="d1639-248">For example, `http://<server_name>/sites/WSSAdapterWalkthrough`.</span></span>  
  
2. <span data-ttu-id="d1639-249">左側にある [**ドキュメント**、] をクリックして**ソース**します。</span><span class="sxs-lookup"><span data-stu-id="d1639-249">On the left side, under **Documents**, click **Source**.</span></span>  
  
3. <span data-ttu-id="d1639-250">クリックして**ドキュメントのアップロード**します。</span><span class="sxs-lookup"><span data-stu-id="d1639-250">Click **Upload Document**.</span></span>  
  
4. <span data-ttu-id="d1639-251">**名前**ボックスで、入力するか、上記で作成した XML ファイルを参照します。</span><span class="sxs-lookup"><span data-stu-id="d1639-251">In the **Name** box, type or browse to the XML file you created above.</span></span> <span data-ttu-id="d1639-252">たとえば、 `C:\WSSAdapterWalkthrough\PurchaseOrder1.xml`、 をクリックし、**を保存して閉じます**します。</span><span class="sxs-lookup"><span data-stu-id="d1639-252">For example, `C:\WSSAdapterWalkthrough\PurchaseOrder1.xml`, and then click **Save and Close**.</span></span> <span data-ttu-id="d1639-253">これで、ファイルが一覧内に表示されるようになります。</span><span class="sxs-lookup"><span data-stu-id="d1639-253">You should now be able to see the file in the list.</span></span>  
  
5. <span data-ttu-id="d1639-254">ブラウザー ウィンドウを更新します。</span><span class="sxs-lookup"><span data-stu-id="d1639-254">Refresh the browser window.</span></span> <span data-ttu-id="d1639-255">`PurchaseOrder1.xml` ファイルは、このライブラリの一覧に表示されなくなります。</span><span class="sxs-lookup"><span data-stu-id="d1639-255">The `PurchaseOrder1.xml` file will no longer be listed in this library.</span></span>  
  
   > [!NOTE]
   >  <span data-ttu-id="d1639-256">ポーリング間隔が 10 秒に設定されているため、ブラウザーを数回更新する必要がある場合があります。</span><span class="sxs-lookup"><span data-stu-id="d1639-256">You may have to refresh the browser a few times since the polling interval is set at 10 seconds.</span></span>  
  
6. <span data-ttu-id="d1639-257">上部のナビゲーション バーでクリックして**ドキュメントし、リスト**します。</span><span class="sxs-lookup"><span data-stu-id="d1639-257">On the top navigation bar, click **Documents and Lists**.</span></span>  
  
7. <span data-ttu-id="d1639-258">[**ドキュメント ライブラリ**、] をクリックして**先**します。</span><span class="sxs-lookup"><span data-stu-id="d1639-258">Under **Document Libraries**, click **Destination**.</span></span>  
  
8. <span data-ttu-id="d1639-259">アップロード先のドキュメント ライブラリに表示されます、メッセージが表示されています。</span><span class="sxs-lookup"><span data-stu-id="d1639-259">In the Destination Document Library, you will now see your message listed.</span></span> <span data-ttu-id="d1639-260">また、アーカイブ ドキュメント ライブラリにアーカイブされたコピーも表示されます。</span><span class="sxs-lookup"><span data-stu-id="d1639-260">You will also find a copy archived in the Archive Document Library.</span></span>  
  
   > [!NOTE]
   >  <span data-ttu-id="d1639-261">メッセージが [アップロード先のドキュメント ライブラリ] に表示されない場合は、[!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)] ヘルプの「Windows SharePoint Services アダプターのトラブルシューティング」を参照してください。</span><span class="sxs-lookup"><span data-stu-id="d1639-261">If the message does not appear in the Destination Document Library, refer to "Troubleshooting the Windows SharePoint Services Adapter" in [!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)] Help.</span></span>  
  
## <a name="summary"></a><span data-ttu-id="d1639-262">まとめ</span><span class="sxs-lookup"><span data-stu-id="d1639-262">Summary</span></span>  
 <span data-ttu-id="d1639-263">このチュートリアルでは、Windows SharePoint Services アダプターとコンテンツ ベースのルーティング (CBR) を使用してメッセージを送受信できるように Windows SharePoint Services と [!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)] を構成する方法について説明しました。</span><span class="sxs-lookup"><span data-stu-id="d1639-263">In this walkthrough you have seen how to configure Windows SharePoint Services and [!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)] so you can send and receive a message using the Windows SharePoint Services adapter and content-based routing (CBR).</span></span>  
  
## <a name="next-steps"></a><span data-ttu-id="d1639-264">次の手順</span><span class="sxs-lookup"><span data-stu-id="d1639-264">Next Steps</span></span>  
 <span data-ttu-id="d1639-265">これで、このチュートリアルを完了すると、実行、[チュートリアル: モジュール 2 - Windows SharePoint Services アダプターと Office の統合](../core/walkthrough-module-2--integrate-office-with-the-sharepoint-adapter-in-biztalk.md)チュートリアルについては、このチュートリアルと表示を行う作業の発展Windows SharePoint Services アダプターと Office を統合する方法。</span><span class="sxs-lookup"><span data-stu-id="d1639-265">Now that you have completed this walkthrough, perform the [Walkthrough: Module 2 - Integrating Office with the Windows SharePoint Services Adapter](../core/walkthrough-module-2--integrate-office-with-the-sharepoint-adapter-in-biztalk.md) walkthrough, which expands on the work you have done with this walkthrough and shows you how to integrate Office with the Windows SharePoint Services adapter.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="d1639-266">参照</span><span class="sxs-lookup"><span data-stu-id="d1639-266">See Also</span></span>  
 <span data-ttu-id="d1639-267">[Windows SharePoint Services アダプターとは何ですか。](../core/what-is-the-windows-sharepoint-services-adapter.md) </span><span class="sxs-lookup"><span data-stu-id="d1639-267">[What Is the Windows SharePoint Services Adapter?](../core/what-is-the-windows-sharepoint-services-adapter.md) </span></span>  
 [<span data-ttu-id="d1639-268">Windows SharePoint Services アダプターのチュートリアル</span><span class="sxs-lookup"><span data-stu-id="d1639-268">Windows SharePoint Services Adapter Walkthroughs</span></span>](../core/windows-sharepoint-services-adapter-walkthroughs.md)