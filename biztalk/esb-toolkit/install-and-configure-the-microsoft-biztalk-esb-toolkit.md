---
title: "インストールして、Microsoft BizTalk ESB Toolkit の構成 |Microsoft ドキュメント"
description: "インストールして、BizTalk Server で ESB Toolkit を構成する手順の手順を実行して命令"
caps.latest.revision: "8"
author: MandiOhlinger
manager: anneta
ms.custom: 
ms.date: 08/10/2017
ms.prod: biztalk-server
ms.reviewer: 
ms.suite: 
ms.tgt_pltfrm: 
ms.topic: article
ms.assetid: 698843f7-8361-4d02-9278-0e66f2a9f472
ms.author: mandia
ms.openlocfilehash: 33805fe58298e4f4729161a62742d3b204996b00
ms.sourcegitcommit: cb908c540d8f1a692d01dc8f313e16cb4b4e696d
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 09/20/2017
---
# <a name="install-and-configure-the-microsoft-biztalk-esb-toolkit"></a><span data-ttu-id="6e6a4-103">インストールして、Microsoft BizTalk ESB Toolkit の構成</span><span class="sxs-lookup"><span data-stu-id="6e6a4-103">Install and configure the Microsoft BizTalk ESB Toolkit</span></span>
<span data-ttu-id="6e6a4-104">BizTalk Server 2013 と新しいバージョンでは、開始[!INCLUDE[esbToolkit](../includes/esbtoolkit-md.md)]と統合されて、[!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)]セットアップします。</span><span class="sxs-lookup"><span data-stu-id="6e6a4-104">Starting with BizTalk Server 2013 and newer versions, [!INCLUDE[esbToolkit](../includes/esbtoolkit-md.md)] is integrated with the [!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)] setup.</span></span> <span data-ttu-id="6e6a4-105">このトピックは、インストールおよび構成する方法を示します[!INCLUDE[esbToolkit](../includes/esbtoolkit-md.md)]、し、ESB Toolkit のアップグレードをコミュニティに書き込まれたリンクも含まれます。</span><span class="sxs-lookup"><span data-stu-id="6e6a4-105">This topic shows you how to install and configure [!INCLUDE[esbToolkit](../includes/esbtoolkit-md.md)], and also includes a community-written link to upgrade the ESB Toolkit.</span></span>  
  
> [!IMPORTANT]
>  <span data-ttu-id="6e6a4-106">[!INCLUDE[esbToolkit_short](../includes/esbtoolkit-short-md.md)] のインストールを始める前に、BizTalk Server をインストールしておく必要があります。</span><span class="sxs-lookup"><span data-stu-id="6e6a4-106">You must have BizTalk Server installed before you start installing the [!INCLUDE[esbToolkit_short](../includes/esbtoolkit-short-md.md)].</span></span>  
  
## <a name="install"></a><span data-ttu-id="6e6a4-107">Install</span><span class="sxs-lookup"><span data-stu-id="6e6a4-107">Install</span></span> 
  
1.  <span data-ttu-id="6e6a4-108">実行、 [!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)] setup.exe ファイルを管理者として。</span><span class="sxs-lookup"><span data-stu-id="6e6a4-108">Run the [!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)] setup.exe file as Administrator.</span></span> <span data-ttu-id="6e6a4-109">セットアップに、次のように選択します。**インストール[!INCLUDE[esbToolkit](../includes/esbtoolkit-md.md)]**です。</span><span class="sxs-lookup"><span data-stu-id="6e6a4-109">In setup, select **Install [!INCLUDE[esbToolkit](../includes/esbtoolkit-md.md)]**.</span></span>  
  
2.  <span data-ttu-id="6e6a4-110">ライセンス契約に同意し、**次**です。</span><span class="sxs-lookup"><span data-stu-id="6e6a4-110">Accept the license agreement, and then select **Next**.</span></span>  
  
3.  <span data-ttu-id="6e6a4-111">[**コンポーネントのインストール**] で、インストールするコンポーネントを選択し、[**次へ**] を選択します。</span><span class="sxs-lookup"><span data-stu-id="6e6a4-111">In **Component Installation**, select the components you want to install, and then select **Next**.</span></span>  
  
4.  <span data-ttu-id="6e6a4-112">**概要**、確認を選択して確認し、**インストール**です。</span><span class="sxs-lookup"><span data-stu-id="6e6a4-112">In the **Summary**, review what you chose, and then select **Install**.</span></span>  
  
5.  <span data-ttu-id="6e6a4-113">[**完了**] を選択して、インストール ウィザードを終了します。</span><span class="sxs-lookup"><span data-stu-id="6e6a4-113">Select **Finish** to close the installation wizard.</span></span>  

<span data-ttu-id="6e6a4-114">インストール ログ ファイルが作成、' C:\Users\yourUserName\AppData\Local\Temp\Setup(081017 175042).htm' に似ています。</span><span class="sxs-lookup"><span data-stu-id="6e6a4-114">An install log file is created, similar to \`C:\Users\yourUserName\AppData\Local\Temp\Setup(081017 175042).htm'.</span></span> 
  
## <a name="configure"></a><span data-ttu-id="6e6a4-115">[構成]</span><span class="sxs-lookup"><span data-stu-id="6e6a4-115">Configure</span></span> 
  
> [!IMPORTANT]
>  <span data-ttu-id="6e6a4-116">[!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)] を構成する前に、[!INCLUDE[esbToolkit_short](../includes/esbtoolkit-short-md.md)] を構成する必要があります。</span><span class="sxs-lookup"><span data-stu-id="6e6a4-116">You must configure [!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)] before configuring [!INCLUDE[esbToolkit_short](../includes/esbtoolkit-short-md.md)].</span></span>  
  
1.  <span data-ttu-id="6e6a4-117">**開始**メニューの **Microsoft [!INCLUDE[esbToolkit](../includes/esbtoolkit-md.md)]** 、し、 **ESB 構成ツール**です。</span><span class="sxs-lookup"><span data-stu-id="6e6a4-117">From the **Start** menu, select **Microsoft [!INCLUDE[esbToolkit](../includes/esbtoolkit-md.md)]**, and then select **ESB Configuration Tool**.</span></span>  
  
    > [!IMPORTANT]
    >  <span data-ttu-id="6e6a4-118">ESB 構成ツールを管理者として実行します。</span><span class="sxs-lookup"><span data-stu-id="6e6a4-118">Run the ESB Configuration Tool as an administrator.</span></span>  
  
2.  <span data-ttu-id="6e6a4-119">構成では、次のように選択します。**データベース サーバー**です。</span><span class="sxs-lookup"><span data-stu-id="6e6a4-119">In the configuration, select **Database Server**.</span></span> <span data-ttu-id="6e6a4-120">ホストするデータベース サーバー名を入力、[!INCLUDE[esbToolkit_short](../includes/esbtoolkit-short-md.md)]データベース。</span><span class="sxs-lookup"><span data-stu-id="6e6a4-120">Enter the database server name that hosts the [!INCLUDE[esbToolkit_short](../includes/esbtoolkit-short-md.md)] databases.</span></span>   
  
3.  <span data-ttu-id="6e6a4-121">**IIS Web サービス**、ユーザー アカウントとによって作成された IIS アプリケーションを実行しているパスワードを入力、[!INCLUDE[esbToolkit_short](../includes/esbtoolkit-short-md.md)]です。</span><span class="sxs-lookup"><span data-stu-id="6e6a4-121">In **IIS Web Services**, enter the user account and password that runs the IIS applications created by the [!INCLUDE[esbToolkit_short](../includes/esbtoolkit-short-md.md)].</span></span> <span data-ttu-id="6e6a4-122">次に、アプリケーションをホストする IIS web サイトを入力します。</span><span class="sxs-lookup"><span data-stu-id="6e6a4-122">Next, enter the IIS website that hosts the applications.</span></span>  
  
4.  <span data-ttu-id="6e6a4-123">**BizTalk ユーザー グループ**通常 ESB の構成に使用する既定のユーザー グループを一覧表示します。</span><span class="sxs-lookup"><span data-stu-id="6e6a4-123">The **BizTalk User Groups** lists the default user groups typically used for ESB configuration.</span></span>  
  
    > [!IMPORTANT]
    >  <span data-ttu-id="6e6a4-124">この段階を選択できます**構成の適用**を構成するのには[!INCLUDE[esbToolkit_short](../includes/esbtoolkit-short-md.md)]これらの既定の設定でします。</span><span class="sxs-lookup"><span data-stu-id="6e6a4-124">At this stage, you can select **Apply Configuration** to configure the [!INCLUDE[esbToolkit_short](../includes/esbtoolkit-short-md.md)] with these default settings.</span></span> <span data-ttu-id="6e6a4-125">ただし、カスタム構成を実行する場合は、残りのステップを完了します。</span><span class="sxs-lookup"><span data-stu-id="6e6a4-125">However, if you want to do a custom configuration, complete the remaining steps.</span></span> <span data-ttu-id="6e6a4-126">次の手順で入力された値は、既定値よりも優先されます。</span><span class="sxs-lookup"><span data-stu-id="6e6a4-126">Rhe values you enter in the next steps take precedence over the default values.</span></span>  
  
5.  <span data-ttu-id="6e6a4-127">左側のウィンドウで展開**ESB 構成**、展開 * * 例外管理 * *、し。</span><span class="sxs-lookup"><span data-stu-id="6e6a4-127">In the left pane, expand **ESB Configuration**, expand ** Exception Management**, and then:</span></span>  
  
    -   <span data-ttu-id="6e6a4-128">例外管理データベースを構成しない場合を選択し、**データベース**、オフにし、**例外管理データベースを有効にする**です。</span><span class="sxs-lookup"><span data-stu-id="6e6a4-128">If you don't want to configure an exception management database, then select **Database**, and uncheck the **Enable Exception Management Database**.</span></span>
  
    -   <span data-ttu-id="6e6a4-129">新しいデータベースを作成する代わりに、既存のデータベースを使用しを選択する場合**データベース**を選択し、**既存のデータベースを使用して**です。</span><span class="sxs-lookup"><span data-stu-id="6e6a4-129">If you want to use an existing database instead of creating a new database, then select **Database**, and select the **Use Existing Database**.</span></span> <span data-ttu-id="6e6a4-130">データベース サーバー名とデータベース名を入力します。</span><span class="sxs-lookup"><span data-stu-id="6e6a4-130">Enter the database server name and the database name.</span></span>  
  
    -   <span data-ttu-id="6e6a4-131">例外 web サービスを構成しない場合を選択し、**例外 Web サービス**、オフにし、**例外サービスを有効に**です。</span><span class="sxs-lookup"><span data-stu-id="6e6a4-131">If you don't want to configure exception web service, then select **Exception Web Services**, and uncheck **Enable Exception Services**.</span></span>  <span data-ttu-id="6e6a4-132">別の web サイトの下でこれらのサービスを実行する場合は、ここで入力することができます。</span><span class="sxs-lookup"><span data-stu-id="6e6a4-132">If you want to run these services under a different website, you can enter that here.</span></span>  
  
6.  <span data-ttu-id="6e6a4-133">左側のウィンドウで展開**ESB コア コンポーネント**、し。</span><span class="sxs-lookup"><span data-stu-id="6e6a4-133">In the left pane, expand **ESB Core Components**, and then:</span></span>  
  
    -   <span data-ttu-id="6e6a4-134">行程データベースを構成しない場合を選択し、**行程データベース**、オフにし、**行程データベース**です。</span><span class="sxs-lookup"><span data-stu-id="6e6a4-134">If you don't want to configure an itinerary database, then select **Itinerary Database**, and uncheck **Itinerary Database** .</span></span>  
  
    -   <span data-ttu-id="6e6a4-135">既存行程データベースを使用する場合を選択し、**行程データベース**を選択して**既存のデータベースを使用して**です。</span><span class="sxs-lookup"><span data-stu-id="6e6a4-135">If you want to use an existing itinerary database, then select **Itinerary Database**, and select **Use Existing Database**.</span></span> <span data-ttu-id="6e6a4-136">データベース サーバー名とデータベース名を入力します。</span><span class="sxs-lookup"><span data-stu-id="6e6a4-136">Enter the database server name and the database name.</span></span>  
  
    -   <span data-ttu-id="6e6a4-137">これらの web サービスを構成しない場合を選択し、**コア Web サービス**、オフにし、**コア サービスを有効に**です。</span><span class="sxs-lookup"><span data-stu-id="6e6a4-137">If you don't want to configure these web service, then select **Core Web Services**, and uncheck **Enable Core Services**.</span></span> <span data-ttu-id="6e6a4-138">別の web サイトの下でこれらのサービスを実行する場合は、ここで入力することができます。</span><span class="sxs-lookup"><span data-stu-id="6e6a4-138">If you want to run these services under a different website, you can enter that here.</span></span>
  
7.  <span data-ttu-id="6e6a4-139">左のペインで選択**構成**です。</span><span class="sxs-lookup"><span data-stu-id="6e6a4-139">In the left pane, select **Configuration**.</span></span>  
    <span data-ttu-id="6e6a4-140">インストールして構成する場合、[!INCLUDE[esbToolkit_short](../includes/esbtoolkit-short-md.md)]単一サーバー環境で次のように選択します。**ファイル構成ソース**です。</span><span class="sxs-lookup"><span data-stu-id="6e6a4-140">If you are installing and configuring the [!INCLUDE[esbToolkit_short](../includes/esbtoolkit-short-md.md)] in a single server environment, select **File Configuration Source**.</span></span> <span data-ttu-id="6e6a4-141">複数コンピューターの展開を設定する場合は、選択、 **SSO 構成ソース**、次を入力します。</span><span class="sxs-lookup"><span data-stu-id="6e6a4-141">If you are setting up a multiple-machine deployment, select the **SSO Configuration Source**, and then enter the following:</span></span>  
  
    -   <span data-ttu-id="6e6a4-142">**SSO サーバー**: SSO サーバーの名前を入力してください</span><span class="sxs-lookup"><span data-stu-id="6e6a4-142">**SSO Server**: Enter the name of the SSO server</span></span>
  
    -   <span data-ttu-id="6e6a4-143">**構成ファイル**: は、省略記号**([...])**、し esb.config ファイル (\Program Files (x86) \Microsoft BizTalk ESB Toolkit) を参照</span><span class="sxs-lookup"><span data-stu-id="6e6a4-143">**Configuration file**: Select the ellipsis **(…)**, and then browse to the esb.config file (\Program Files (x86)\Microsoft BizTalk ESB Toolkit)</span></span>
  
    -   <span data-ttu-id="6e6a4-144">**アプリケーション名**: SSO アプリケーションの名前を入力します。</span><span class="sxs-lookup"><span data-stu-id="6e6a4-144">**Application Name**: Enter a name for the SSO application.</span></span> <span data-ttu-id="6e6a4-145">たとえば、入力`ESB Toolkit`です。</span><span class="sxs-lookup"><span data-stu-id="6e6a4-145">For example,  enter `ESB Toolkit`.</span></span>  
  
    -   <span data-ttu-id="6e6a4-146">**連絡先情報**: 次の形式で有効な電子メール アドレス、適切な連絡先情報を入力してください:`someone@example.com`です。</span><span class="sxs-lookup"><span data-stu-id="6e6a4-146">**Contact Information**: Enter a valid email address the appropriate contact information in the following format: `someone@example.com`.</span></span>  
  
    -   <span data-ttu-id="6e6a4-147">**管理者グループ名**: は、省略記号**([...])**、適切な管理グループを参照</span><span class="sxs-lookup"><span data-stu-id="6e6a4-147">**Administrator Group Name**: Select the ellipsis **(…)**, and then browse to the appropriate admin group</span></span>  
  
    -   <span data-ttu-id="6e6a4-148">**ユーザー グループ名**: は、省略記号**([...])**、適切なグループを参照</span><span class="sxs-lookup"><span data-stu-id="6e6a4-148">**User Group Name**: Select the ellipsis **(…)**, and then browse to the appropriate group</span></span>  

8.  <span data-ttu-id="6e6a4-149">選択**構成を適用**です。</span><span class="sxs-lookup"><span data-stu-id="6e6a4-149">Select **Apply Configuration**.</span></span> <span data-ttu-id="6e6a4-150">IIS を開き、[!INCLUDE[esbToolkit_short](../includes/esbtoolkit-short-md.md)] に必要なアプリケーションが、[!INCLUDE[esbToolkit_short](../includes/esbtoolkit-short-md.md)] の構成で指定した Web サイトに作成されていることを確認します。</span><span class="sxs-lookup"><span data-stu-id="6e6a4-150">Open IIS and notice that the applications required for [!INCLUDE[esbToolkit_short](../includes/esbtoolkit-short-md.md)] are now created under the website you specified while configuring [!INCLUDE[esbToolkit_short](../includes/esbtoolkit-short-md.md)].</span></span>  
  
9. <span data-ttu-id="6e6a4-151">**ESB 構成ツール** **ESB BizTalk アプリケーション**、し。</span><span class="sxs-lookup"><span data-stu-id="6e6a4-151">In the **ESB Configuration Tool**, select **ESB BizTalk Applications**, and then:</span></span>  
  
    -   <span data-ttu-id="6e6a4-152">選択**BizTalk Server で ESB コア コンポーネントを有効にする**でアプリケーションを作成する、[!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)]管理コンソールです。</span><span class="sxs-lookup"><span data-stu-id="6e6a4-152">Select **Enable ESB Core Components in BizTalk Server** to create the application in the [!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)] Administration console.</span></span> <span data-ttu-id="6e6a4-153">選択**既定のバインドを使用**に既定のホストをこのアプリケーションをバインドします。</span><span class="sxs-lookup"><span data-stu-id="6e6a4-153">Select **Use Default Binding** to bind this application to the default host.</span></span> <span data-ttu-id="6e6a4-154">選択**既定のバインドを使用しないでください**アプリケーションを既定のホストにバインドしたくない場合。</span><span class="sxs-lookup"><span data-stu-id="6e6a4-154">Select **Do not use Default Binding** if you do not want to bind the application to the default host.</span></span> <span data-ttu-id="6e6a4-155">このシナリオでは、アプリケーションを作成した後、ホストにアプリケーションを明示的に連結する必要があります。</span><span class="sxs-lookup"><span data-stu-id="6e6a4-155">In this scenario, you must explicitly bind the application to a host once the application is created.</span></span>  
  
    -   <span data-ttu-id="6e6a4-156">選択**BizTalk Server で ESB JMS/WMQ コンポーネントを有効にする**でアプリケーションを作成する、[!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)]管理コンソールです。</span><span class="sxs-lookup"><span data-stu-id="6e6a4-156">Select **Enable ESB JMS/WMQ Components in BizTalk Server** to create the application in the [!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)] Administration console.</span></span> <span data-ttu-id="6e6a4-157">選択**既定のバインドを使用**に既定のホストをこのアプリケーションをバインドします。</span><span class="sxs-lookup"><span data-stu-id="6e6a4-157">Select **Use Default Binding** to bind this application to the default host.</span></span> <span data-ttu-id="6e6a4-158">選択**既定のバインドを使用しないでください**アプリケーションを既定のホストにバインドしたくない場合。</span><span class="sxs-lookup"><span data-stu-id="6e6a4-158">Select **Do not use Default Binding** if you do not want to bind the application to the default host.</span></span> <span data-ttu-id="6e6a4-159">このシナリオでは、アプリケーションを作成した後、ホストにアプリケーションを明示的に連結する必要があります。</span><span class="sxs-lookup"><span data-stu-id="6e6a4-159">In this scenario, you must explicitly bind the application to a host once the application is created.</span></span>  
  
    -   <span data-ttu-id="6e6a4-160">選択**構成の適用**選択したアプリケーションを作成します。</span><span class="sxs-lookup"><span data-stu-id="6e6a4-160">Select **Apply Configuration** to create the applications you selected.</span></span> <span data-ttu-id="6e6a4-161">[!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)] 管理コンソールでアプリケーションが作成されたことを確認します。</span><span class="sxs-lookup"><span data-stu-id="6e6a4-161">Verify that the applications are created in the [!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)] Administration console.</span></span>  
  
## <a name="upgrade-esb-toolkit--community-addition"></a><span data-ttu-id="6e6a4-162">コミュニティによる補足 – ESB Toolkit のアップグレードします。</span><span class="sxs-lookup"><span data-stu-id="6e6a4-162">Upgrade ESB Toolkit – Community Addition</span></span>  
 <span data-ttu-id="6e6a4-163">[ESB Toolkit 2.1 から 2.2 へのインプレース アップグレード](http://www.brianloesgen.com/blog/2013/10/10/in-place-upgrade-of-esb-toolkit-21-to-22.html) (http://www.brianloesgen.com/blog/2013/10/10/in-place-upgrade-of-esb-toolkit-21-to-22.html)</span><span class="sxs-lookup"><span data-stu-id="6e6a4-163">[In-place upgrade of ESB Toolkit 2.1 to 2.2](http://www.brianloesgen.com/blog/2013/10/10/in-place-upgrade-of-esb-toolkit-21-to-22.html) (http://www.brianloesgen.com/blog/2013/10/10/in-place-upgrade-of-esb-toolkit-21-to-22.html)</span></span>

## <a name="see-also"></a><span data-ttu-id="6e6a4-164">参照</span><span class="sxs-lookup"><span data-stu-id="6e6a4-164">See also</span></span>
[<span data-ttu-id="6e6a4-165">インストールの問題、一般的なエラーと解像度をトラブルシューティングします。</span><span class="sxs-lookup"><span data-stu-id="6e6a4-165">Troubleshoot installation issues, and common errors & resolutions</span></span>](troubleshooting-the-biztalk-esb-toolkit.md)