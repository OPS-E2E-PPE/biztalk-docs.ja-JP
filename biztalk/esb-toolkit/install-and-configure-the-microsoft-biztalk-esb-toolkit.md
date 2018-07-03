---
title: インストールして、Microsoft BizTalk ESB Toolkit の構成 |Microsoft Docs
description: インストールして、BizTalk Server で ESB Toolkit を構成する手順の手順で指示
caps.latest.revision: 8
author: MandiOhlinger
manager: anneta
ms.custom: ''
ms.date: 08/10/2017
ms.prod: biztalk-server
ms.reviewer: ''
ms.suite: ''
ms.tgt_pltfrm: ''
ms.topic: article
ms.assetid: 698843f7-8361-4d02-9278-0e66f2a9f472
ms.author: mandia
ms.openlocfilehash: 7018a6bfa9d55b58cadfa9b808d7c295f88a2c0d
ms.sourcegitcommit: 266308ec5c6a9d8d80ff298ee6051b4843c5d626
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 06/27/2018
ms.locfileid: "36981379"
---
# <a name="install-and-configure-the-microsoft-biztalk-esb-toolkit"></a><span data-ttu-id="a084c-103">インストールして、Microsoft BizTalk ESB Toolkit の構成</span><span class="sxs-lookup"><span data-stu-id="a084c-103">Install and configure the Microsoft BizTalk ESB Toolkit</span></span>
<span data-ttu-id="a084c-104">以降では、BizTalk Server 2013 および新しいバージョンの[!INCLUDE[esbToolkit](../includes/esbtoolkit-md.md)]と統合されて、[!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)]セットアップします。</span><span class="sxs-lookup"><span data-stu-id="a084c-104">Starting with BizTalk Server 2013 and newer versions, [!INCLUDE[esbToolkit](../includes/esbtoolkit-md.md)] is integrated with the [!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)] setup.</span></span> <span data-ttu-id="a084c-105">このトピックでは、インストールして構成する方法を示します[!INCLUDE[esbToolkit](../includes/esbtoolkit-md.md)]、ESB Toolkit をアップグレードするコミュニティによって記述されたリンクも含まれています。</span><span class="sxs-lookup"><span data-stu-id="a084c-105">This topic shows you how to install and configure [!INCLUDE[esbToolkit](../includes/esbtoolkit-md.md)], and also includes a community-written link to upgrade the ESB Toolkit.</span></span>  
  
> [!IMPORTANT]
>  <span data-ttu-id="a084c-106">[!INCLUDE[esbToolkit_short](../includes/esbtoolkit-short-md.md)] のインストールを始める前に、BizTalk Server をインストールしておく必要があります。</span><span class="sxs-lookup"><span data-stu-id="a084c-106">You must have BizTalk Server installed before you start installing the [!INCLUDE[esbToolkit_short](../includes/esbtoolkit-short-md.md)].</span></span>  
  
## <a name="install"></a><span data-ttu-id="a084c-107">インストール</span><span class="sxs-lookup"><span data-stu-id="a084c-107">Install</span></span> 
  
1. <span data-ttu-id="a084c-108">実行、 [!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)] setup.exe ファイルを管理者として。</span><span class="sxs-lookup"><span data-stu-id="a084c-108">Run the [!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)] setup.exe file as Administrator.</span></span> <span data-ttu-id="a084c-109">セットアップでは、次のように選択します。**インストール[!INCLUDE[esbToolkit](../includes/esbtoolkit-md.md)]** します。</span><span class="sxs-lookup"><span data-stu-id="a084c-109">In setup, select **Install [!INCLUDE[esbToolkit](../includes/esbtoolkit-md.md)]**.</span></span>  
  
2. <span data-ttu-id="a084c-110">ライセンス条項に同意し、**次**します。</span><span class="sxs-lookup"><span data-stu-id="a084c-110">Accept the license agreement, and then select **Next**.</span></span>  
  
3. <span data-ttu-id="a084c-111">**[コンポーネントのインストール]** で、インストールするコンポーネントを選択し、**[次へ]** を選択します。</span><span class="sxs-lookup"><span data-stu-id="a084c-111">In **Component Installation**, select the components you want to install, and then select **Next**.</span></span>  
  
4. <span data-ttu-id="a084c-112">**概要**、確認を選択して確認し、**インストール**します。</span><span class="sxs-lookup"><span data-stu-id="a084c-112">In the **Summary**, review what you chose, and then select **Install**.</span></span>  
  
5. <span data-ttu-id="a084c-113">**[完了]** を選択して、インストール ウィザードを終了します。</span><span class="sxs-lookup"><span data-stu-id="a084c-113">Select **Finish** to close the installation wizard.</span></span>  

<span data-ttu-id="a084c-114">インストール ログ ファイルが作成されます、' C:\Users\yourUserName\AppData\Local\Temp\Setup(081017 175042).htm' に似ています。</span><span class="sxs-lookup"><span data-stu-id="a084c-114">An install log file is created, similar to \`C:\Users\yourUserName\AppData\Local\Temp\Setup(081017 175042).htm'.</span></span> 
  
## <a name="configure"></a><span data-ttu-id="a084c-115">[構成]</span><span class="sxs-lookup"><span data-stu-id="a084c-115">Configure</span></span> 
  
> [!IMPORTANT]
>  <span data-ttu-id="a084c-116">[!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)] を構成する前に、[!INCLUDE[esbToolkit_short](../includes/esbtoolkit-short-md.md)] を構成する必要があります。</span><span class="sxs-lookup"><span data-stu-id="a084c-116">You must configure [!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)] before configuring [!INCLUDE[esbToolkit_short](../includes/esbtoolkit-short-md.md)].</span></span>  
  
1. <span data-ttu-id="a084c-117">**開始**メニューの **Microsoft [!INCLUDE[esbToolkit](../includes/esbtoolkit-md.md)]** 、し、 **ESB 構成ツール**です。</span><span class="sxs-lookup"><span data-stu-id="a084c-117">From the **Start** menu, select **Microsoft [!INCLUDE[esbToolkit](../includes/esbtoolkit-md.md)]**, and then select **ESB Configuration Tool**.</span></span>  
  
   > [!IMPORTANT]
   >  <span data-ttu-id="a084c-118">管理者として、ESB 構成ツールを実行します。</span><span class="sxs-lookup"><span data-stu-id="a084c-118">Run the ESB Configuration Tool as an administrator.</span></span>  
  
2. <span data-ttu-id="a084c-119">構成では、次のように選択します。**データベース サーバー**します。</span><span class="sxs-lookup"><span data-stu-id="a084c-119">In the configuration, select **Database Server**.</span></span> <span data-ttu-id="a084c-120">ホストするデータベース サーバー名を入力、[!INCLUDE[esbToolkit_short](../includes/esbtoolkit-short-md.md)]データベース。</span><span class="sxs-lookup"><span data-stu-id="a084c-120">Enter the database server name that hosts the [!INCLUDE[esbToolkit_short](../includes/esbtoolkit-short-md.md)] databases.</span></span>   
  
3. <span data-ttu-id="a084c-121">**IIS Web サービス**、ユーザー アカウントとパスワードを作成する IIS アプリケーションを実行している入力、[!INCLUDE[esbToolkit_short](../includes/esbtoolkit-short-md.md)]します。</span><span class="sxs-lookup"><span data-stu-id="a084c-121">In **IIS Web Services**, enter the user account and password that runs the IIS applications created by the [!INCLUDE[esbToolkit_short](../includes/esbtoolkit-short-md.md)].</span></span> <span data-ttu-id="a084c-122">次に、アプリケーションをホストする IIS web サイトを入力します。</span><span class="sxs-lookup"><span data-stu-id="a084c-122">Next, enter the IIS website that hosts the applications.</span></span>  
  
4. <span data-ttu-id="a084c-123">**BizTalk ユーザー グループ**通常 ESB の構成に使用する既定のユーザー グループを一覧表示されます。</span><span class="sxs-lookup"><span data-stu-id="a084c-123">The **BizTalk User Groups** lists the default user groups typically used for ESB configuration.</span></span>  
  
   > [!IMPORTANT]
   >  <span data-ttu-id="a084c-124">この段階を選択できます**構成の適用**を構成する、[!INCLUDE[esbToolkit_short](../includes/esbtoolkit-short-md.md)]これら既定の設定を使用します。</span><span class="sxs-lookup"><span data-stu-id="a084c-124">At this stage, you can select **Apply Configuration** to configure the [!INCLUDE[esbToolkit_short](../includes/esbtoolkit-short-md.md)] with these default settings.</span></span> <span data-ttu-id="a084c-125">ただし、カスタム構成を実行する場合は、残りのステップを完了します。</span><span class="sxs-lookup"><span data-stu-id="a084c-125">However, if you want to do a custom configuration, complete the remaining steps.</span></span> <span data-ttu-id="a084c-126">次の手順で入力された値は、既定値よりも優先されます。</span><span class="sxs-lookup"><span data-stu-id="a084c-126">Rhe values you enter in the next steps take precedence over the default values.</span></span>  
  
5. <span data-ttu-id="a084c-127">左側のウィンドウで展開**ESB の構成**、展開 \* \* 例外管理 \* をクリックします。</span><span class="sxs-lookup"><span data-stu-id="a084c-127">In the left pane, expand **ESB Configuration**, expand ** Exception Management**, and then:</span></span>  
  
   -   <span data-ttu-id="a084c-128">例外管理データベースを構成しない場合を選択し、**データベース**、オフにし、**例外管理データベースを有効にする**します。</span><span class="sxs-lookup"><span data-stu-id="a084c-128">If you don't want to configure an exception management database, then select **Database**, and uncheck the **Enable Exception Management Database**.</span></span>
  
   -   <span data-ttu-id="a084c-129">新しいデータベースを作成する代わりに、既存のデータベースを使用しを選択する場合**データベース**を選択し、**既存のデータベースを使用して**します。</span><span class="sxs-lookup"><span data-stu-id="a084c-129">If you want to use an existing database instead of creating a new database, then select **Database**, and select the **Use Existing Database**.</span></span> <span data-ttu-id="a084c-130">データベース サーバー名とデータベース名を入力します。</span><span class="sxs-lookup"><span data-stu-id="a084c-130">Enter the database server name and the database name.</span></span>  
  
   -   <span data-ttu-id="a084c-131">例外 web サービスを構成しない場合を選択し、**例外 Web サービス**、オフにし、**例外サービスを有効にする**します。</span><span class="sxs-lookup"><span data-stu-id="a084c-131">If you don't want to configure exception web service, then select **Exception Web Services**, and uncheck **Enable Exception Services**.</span></span>  <span data-ttu-id="a084c-132">別の web サイトでこれらのサービスを実行する場合は、ここで入力することができます。</span><span class="sxs-lookup"><span data-stu-id="a084c-132">If you want to run these services under a different website, you can enter that here.</span></span>  
  
6. <span data-ttu-id="a084c-133">左側のウィンドウで展開**ESB コア コンポーネント**をクリックします。</span><span class="sxs-lookup"><span data-stu-id="a084c-133">In the left pane, expand **ESB Core Components**, and then:</span></span>  
  
   -   <span data-ttu-id="a084c-134">行程データベースを構成しない場合を選択し、**行程データベース**、オフにし、**行程データベース**します。</span><span class="sxs-lookup"><span data-stu-id="a084c-134">If you don't want to configure an itinerary database, then select **Itinerary Database**, and uncheck **Itinerary Database** .</span></span>  
  
   -   <span data-ttu-id="a084c-135">既存の行程データベースを使用する場合を選択し、**行程データベース**を選択し、**既存のデータベースを使用して**します。</span><span class="sxs-lookup"><span data-stu-id="a084c-135">If you want to use an existing itinerary database, then select **Itinerary Database**, and select **Use Existing Database**.</span></span> <span data-ttu-id="a084c-136">データベース サーバー名とデータベース名を入力します。</span><span class="sxs-lookup"><span data-stu-id="a084c-136">Enter the database server name and the database name.</span></span>  
  
   -   <span data-ttu-id="a084c-137">これらの web サービスを構成しない場合を選択し、**コア Web サービス**、オフにし、**コア サービスを有効にする**します。</span><span class="sxs-lookup"><span data-stu-id="a084c-137">If you don't want to configure these web service, then select **Core Web Services**, and uncheck **Enable Core Services**.</span></span> <span data-ttu-id="a084c-138">別の web サイトでこれらのサービスを実行する場合は、ここで入力することができます。</span><span class="sxs-lookup"><span data-stu-id="a084c-138">If you want to run these services under a different website, you can enter that here.</span></span>
  
7. <span data-ttu-id="a084c-139">左側のウィンドウで次のように選択します。**構成**します。</span><span class="sxs-lookup"><span data-stu-id="a084c-139">In the left pane, select **Configuration**.</span></span>  
   <span data-ttu-id="a084c-140">インストールして構成する場合、 [!INCLUDE[esbToolkit_short](../includes/esbtoolkit-short-md.md)] 、1 台のサーバー環境で次のように選択します。**ファイル構成ソース**します。</span><span class="sxs-lookup"><span data-stu-id="a084c-140">If you are installing and configuring the [!INCLUDE[esbToolkit_short](../includes/esbtoolkit-short-md.md)] in a single server environment, select **File Configuration Source**.</span></span> <span data-ttu-id="a084c-141">複数コンピューターの展開をセットアップする場合は、選択、 **SSO 構成ソース**、次を入力します。</span><span class="sxs-lookup"><span data-stu-id="a084c-141">If you are setting up a multiple-machine deployment, select the **SSO Configuration Source**, and then enter the following:</span></span>  
  
   -   <span data-ttu-id="a084c-142">**SSO サーバー**: SSO サーバーの名前を入力します。</span><span class="sxs-lookup"><span data-stu-id="a084c-142">**SSO Server**: Enter the name of the SSO server</span></span>
  
   -   <span data-ttu-id="a084c-143">**構成ファイル**: 省略記号を選択 **([...])**、し esb.config ファイル (\Program Files (x86) \Microsoft BizTalk ESB Toolkit) を参照</span><span class="sxs-lookup"><span data-stu-id="a084c-143">**Configuration file**: Select the ellipsis **(…)**, and then browse to the esb.config file (\Program Files (x86)\Microsoft BizTalk ESB Toolkit)</span></span>
  
   -   <span data-ttu-id="a084c-144">**アプリケーション名**: SSO アプリケーションの名前を入力します。</span><span class="sxs-lookup"><span data-stu-id="a084c-144">**Application Name**: Enter a name for the SSO application.</span></span> <span data-ttu-id="a084c-145">たとえば、入力`ESB Toolkit`します。</span><span class="sxs-lookup"><span data-stu-id="a084c-145">For example,  enter `ESB Toolkit`.</span></span>  
  
   -   <span data-ttu-id="a084c-146">**連絡先情報**: 次の形式で有効な電子メール アドレス、適切な連絡先情報を入力します:`someone@example.com`します。</span><span class="sxs-lookup"><span data-stu-id="a084c-146">**Contact Information**: Enter a valid email address the appropriate contact information in the following format: `someone@example.com`.</span></span>  
  
   -   <span data-ttu-id="a084c-147">**管理者グループ名**: 省略記号を選択 **([...])**、適切な管理グループを参照</span><span class="sxs-lookup"><span data-stu-id="a084c-147">**Administrator Group Name**: Select the ellipsis **(…)**, and then browse to the appropriate admin group</span></span>  
  
   -   <span data-ttu-id="a084c-148">**ユーザー グループ名**: 省略記号を選択 **([...])**、適切なグループを参照</span><span class="sxs-lookup"><span data-stu-id="a084c-148">**User Group Name**: Select the ellipsis **(…)**, and then browse to the appropriate group</span></span>  

8. <span data-ttu-id="a084c-149">選択**構成の適用**します。</span><span class="sxs-lookup"><span data-stu-id="a084c-149">Select **Apply Configuration**.</span></span> <span data-ttu-id="a084c-150">IIS を開き、[!INCLUDE[esbToolkit_short](../includes/esbtoolkit-short-md.md)] に必要なアプリケーションが、[!INCLUDE[esbToolkit_short](../includes/esbtoolkit-short-md.md)] の構成で指定した Web サイトに作成されていることを確認します。</span><span class="sxs-lookup"><span data-stu-id="a084c-150">Open IIS and notice that the applications required for [!INCLUDE[esbToolkit_short](../includes/esbtoolkit-short-md.md)] are now created under the website you specified while configuring [!INCLUDE[esbToolkit_short](../includes/esbtoolkit-short-md.md)].</span></span>  
  
9. <span data-ttu-id="a084c-151">**ESB 構成ツール**を選択します**ESB BizTalk アプリケーション**をクリックします。</span><span class="sxs-lookup"><span data-stu-id="a084c-151">In the **ESB Configuration Tool**, select **ESB BizTalk Applications**, and then:</span></span>  
  
   - <span data-ttu-id="a084c-152">選択**BizTalk Server で ESB コア コンポーネントを有効にする**でアプリケーションを作成する、[!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)]管理コンソール。</span><span class="sxs-lookup"><span data-stu-id="a084c-152">Select **Enable ESB Core Components in BizTalk Server** to create the application in the [!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)] Administration console.</span></span> <span data-ttu-id="a084c-153">選択**既定のバインドを使用して**このアプリケーションを既定のホストにバインドします。</span><span class="sxs-lookup"><span data-stu-id="a084c-153">Select **Use Default Binding** to bind this application to the default host.</span></span> <span data-ttu-id="a084c-154">選択**既定のバインドを使用しない**アプリケーションを既定のホストにバインドしたくない場合。</span><span class="sxs-lookup"><span data-stu-id="a084c-154">Select **Do not use Default Binding** if you do not want to bind the application to the default host.</span></span> <span data-ttu-id="a084c-155">このシナリオでは、アプリケーションが作成されると、ホストにアプリケーションを明示的にバインドする必要があります。</span><span class="sxs-lookup"><span data-stu-id="a084c-155">In this scenario, you must explicitly bind the application to a host once the application is created.</span></span>  
  
   - <span data-ttu-id="a084c-156">選択**BizTalk Server で ESB JMS/WMQ コンポーネントを有効にする**でアプリケーションを作成する、[!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)]管理コンソール。</span><span class="sxs-lookup"><span data-stu-id="a084c-156">Select **Enable ESB JMS/WMQ Components in BizTalk Server** to create the application in the [!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)] Administration console.</span></span> <span data-ttu-id="a084c-157">選択**既定のバインドを使用して**このアプリケーションを既定のホストにバインドします。</span><span class="sxs-lookup"><span data-stu-id="a084c-157">Select **Use Default Binding** to bind this application to the default host.</span></span> <span data-ttu-id="a084c-158">選択**既定のバインドを使用しない**アプリケーションを既定のホストにバインドしたくない場合。</span><span class="sxs-lookup"><span data-stu-id="a084c-158">Select **Do not use Default Binding** if you do not want to bind the application to the default host.</span></span> <span data-ttu-id="a084c-159">このシナリオでは、アプリケーションが作成されると、ホストにアプリケーションを明示的にバインドする必要があります。</span><span class="sxs-lookup"><span data-stu-id="a084c-159">In this scenario, you must explicitly bind the application to a host once the application is created.</span></span>  
  
   - <span data-ttu-id="a084c-160">選択**構成の適用**選択したアプリケーションを作成します。</span><span class="sxs-lookup"><span data-stu-id="a084c-160">Select **Apply Configuration** to create the applications you selected.</span></span> <span data-ttu-id="a084c-161">[!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)] 管理コンソールでアプリケーションが作成されたことを確認します。</span><span class="sxs-lookup"><span data-stu-id="a084c-161">Verify that the applications are created in the [!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)] Administration console.</span></span>  
  
## <a name="upgrade-esb-toolkit--community-addition"></a><span data-ttu-id="a084c-162">ESB Toolkit – コミュニティからの追加をアップグレードします。</span><span class="sxs-lookup"><span data-stu-id="a084c-162">Upgrade ESB Toolkit – Community Addition</span></span>  
 <span data-ttu-id="a084c-163">[インプレース ESB Toolkit 2.1 の 2.2 へのアップグレード](http://www.brianloesgen.com/blog/2013/10/10/in-place-upgrade-of-esb-toolkit-21-to-22.html)(http://www.brianloesgen.com/blog/2013/10/10/in-place-upgrade-of-esb-toolkit-21-to-22.html)</span><span class="sxs-lookup"><span data-stu-id="a084c-163">[In-place upgrade of ESB Toolkit 2.1 to 2.2](http://www.brianloesgen.com/blog/2013/10/10/in-place-upgrade-of-esb-toolkit-21-to-22.html) (http://www.brianloesgen.com/blog/2013/10/10/in-place-upgrade-of-esb-toolkit-21-to-22.html)</span></span>

## <a name="see-also"></a><span data-ttu-id="a084c-164">参照</span><span class="sxs-lookup"><span data-stu-id="a084c-164">See also</span></span>
[<span data-ttu-id="a084c-165">インストールの問題、および一般的なエラー & 解像度をトラブルシューティングします。</span><span class="sxs-lookup"><span data-stu-id="a084c-165">Troubleshoot installation issues, and common errors & resolutions</span></span>](troubleshooting-the-biztalk-esb-toolkit.md)