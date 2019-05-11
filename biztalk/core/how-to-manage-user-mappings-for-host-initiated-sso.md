---
title: 側開始 SSO のホストのユーザー マッピングを管理する方法 |Microsoft Docs
ms.custom: ''
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: ''
ms.suite: ''
ms.tgt_pltfrm: ''
ms.topic: article
helpviewer_keywords:
- maps, host initiated SSO
- host initiated SSO, user maps
ms.assetid: 6b05249e-da35-475b-9c23-5eb556013d57
caps.latest.revision: 10
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: 77310b793b9dfccc85b0fc7898f6a02b69ea5688
ms.sourcegitcommit: 381e83d43796a345488d54b3f7413e11d56ad7be
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 05/07/2019
ms.locfileid: "65336693"
---
# <a name="how-to-manage-user-mappings-for-host-initiated-sso"></a><span data-ttu-id="de942-102">側開始 SSO のホストのユーザー マッピングを管理する方法</span><span class="sxs-lookup"><span data-stu-id="de942-102">How to Manage User Mappings for Host Initiated SSO</span></span>
<span data-ttu-id="de942-103">マッピングを作成、資格情報を設定し、有効化またはマッピングを無効にするには、次の手順を使用します。</span><span class="sxs-lookup"><span data-stu-id="de942-103">Use the following procedures to create mappings, set credentials, and enable or disable mapping.</span></span>  
  
### <a name="to-manage-user-mappings-for-host-initiated-sso-using-the-mmc-snap-in"></a><span data-ttu-id="de942-104">側開始 SSO を MMC スナップインを使用してホストのユーザー マッピングの管理</span><span class="sxs-lookup"><span data-stu-id="de942-104">To manage user mappings for host initiated SSO using the MMC Snap-In</span></span>  
  
1.  <span data-ttu-id="de942-105">**開始** メニューのをクリックして**すべてのプログラム**、 をクリックして**Microsoft エンタープライズ シングル サインオン**、 をクリックし、 **SSO 管理**。</span><span class="sxs-lookup"><span data-stu-id="de942-105">On the **Start** menu, click **All Programs**, click **Microsoft Enterprise Single Sign-On**, and then click **SSO Administration**.</span></span>  
  
2.  <span data-ttu-id="de942-106">ENTSSO MMC スナップインの [スコープ] ウィンドウで、**エンタープライズ シングル サインオン**ノード。</span><span class="sxs-lookup"><span data-stu-id="de942-106">In the scope pane of the ENTSSO MMC Snap-In, expand the **Enterprise Single Sign-On** node.</span></span>  
  
3.  <span data-ttu-id="de942-107">スコープ ペインで次のようにクリックします。**関連アプリケーション**します。</span><span class="sxs-lookup"><span data-stu-id="de942-107">In the scope pane, click **Affiliate Applications**.</span></span>  
  
4.  <span data-ttu-id="de942-108">詳細ペインでは、関連アプリケーションを右クリックし、アクションに対して適切なメニュー項目を選択し。</span><span class="sxs-lookup"><span data-stu-id="de942-108">In the details pane, right-click the affiliate application, and then choose the appropriate menu item for your action.</span></span>  
  
### <a name="to-create-mappings-in-host-initiated-sso-using-the-command-line"></a><span data-ttu-id="de942-109">側開始 SSO をコマンドラインを使用してホストでマッピングを作成します。</span><span class="sxs-lookup"><span data-stu-id="de942-109">To create mappings in host initiated SSO using the command line</span></span>  
  
1. <span data-ttu-id="de942-110">**[スタート]** メニューの **[ファイル名を指定して実行]** をクリックします。</span><span class="sxs-lookup"><span data-stu-id="de942-110">On the **Start** menu, click **Run**.</span></span>  
  
2. <span data-ttu-id="de942-111">**実行**ダイアログ ボックスに「 **cmd**、順にクリックします**OK**します。</span><span class="sxs-lookup"><span data-stu-id="de942-111">In the **Run** dialog box, type **cmd**, and then click **OK**.</span></span>  
  
3. <span data-ttu-id="de942-112">コマンド ラインで、エンタープライズ シングル サインオンのインストール ディレクトリに移動します。</span><span class="sxs-lookup"><span data-stu-id="de942-112">At the command line, go to the Enterprise Single Sign-On installation directory.</span></span> <span data-ttu-id="de942-113">既定値は\<ドライブ\>: \Program Files\Common \enterprise シングル サインオンします。</span><span class="sxs-lookup"><span data-stu-id="de942-113">The default is \<drive\>:\Program Files\Common Files\Enterprise Single Sign-On.</span></span>  
  
4. <span data-ttu-id="de942-114">型**ssomanage – createmappings\<マッピング ファイル\>** ここで、**マッピング ファイル >** xml ファイルの名前を指定します。</span><span class="sxs-lookup"><span data-stu-id="de942-114">Type **ssomanage –createmappings \<mapping file\>**, where **mapping file>** is the name of the xml file.</span></span>  
  
   > [!NOTE]
   >  <span data-ttu-id="de942-115">ユーザー アカウント制御 (UAC) をサポートするシステムでは、管理者特権を使用してこのツールを実行することが必要な場合があります。</span><span class="sxs-lookup"><span data-stu-id="de942-115">On a system that supports User Account Control (UAC), you may need to run the tool with Administrative privileges.</span></span>  
  
    <span data-ttu-id="de942-116">サンプル マッピング ファイルは、以下に示します。</span><span class="sxs-lookup"><span data-stu-id="de942-116">A sample mapping file is shown below:</span></span>  
  
   ```  
   <SSO>  
     <mapping>  
       <windowsDomain>DomainName</windowsDomain>  
       <windowsUserId>UserA</windowsUserId>  
       <externalApplication>SSOApplication</externalApplication>  
   <externalUserId>ExternalUserID that corresponds to UserA</externalUserId>  
     </mapping>  
   </SSO>  
  
   ```  
  
   <span data-ttu-id="de942-117">関連アプリケーションのパスワードの検証機能が有効な場合は、次のように、資格情報を設定する必要があります。</span><span class="sxs-lookup"><span data-stu-id="de942-117">When the Validate Password feature is enabled for the affiliate application, it is necessary to set credentials, as follows:</span></span>  
  
#### <a name="to-set-credentials-for-individual-type-affiliate-applications-using-the-command-line"></a><span data-ttu-id="de942-118">関連アプリケーションのコマンドラインを使用して単独タイプの資格情報を設定するには</span><span class="sxs-lookup"><span data-stu-id="de942-118">To set credentials for individual type affiliate applications using the command line</span></span>  
  
1.  <span data-ttu-id="de942-119">**[スタート]** メニューの **[ファイル名を指定して実行]** をクリックします。</span><span class="sxs-lookup"><span data-stu-id="de942-119">On the **Start** menu, click **Run**.</span></span>  
  
2.  <span data-ttu-id="de942-120">**実行**ダイアログ ボックスに「 **cmd**、順にクリックします**OK**します。</span><span class="sxs-lookup"><span data-stu-id="de942-120">In the **Run** dialog box, type **cmd**, and then click **OK**.</span></span>  
  
3.  <span data-ttu-id="de942-121">コマンド ラインで、エンタープライズ シングル サインオンのインストール ディレクトリに移動します。</span><span class="sxs-lookup"><span data-stu-id="de942-121">At the command line, go to the Enterprise Single Sign-On installation directory.</span></span> <span data-ttu-id="de942-122">既定値は\<ドライブ\>: \Program Files\Common \enterprise シングル サインオンします。</span><span class="sxs-lookup"><span data-stu-id="de942-122">The default is \<drive\>:\Program Files\Common Files\Enterprise Single Sign-On.</span></span>  
  
4.  <span data-ttu-id="de942-123">型**ssomanage-setcredentials \<Windows アカウント名\>\<アプリケーション名\>** します。</span><span class="sxs-lookup"><span data-stu-id="de942-123">Type **ssomanage -setcredentials \<Windows account name\> \<application name\>**.</span></span>  
  
    > [!NOTE]
    >  <span data-ttu-id="de942-124">ユーザー アカウント制御 (UAC) をサポートするシステムでは、管理者特権を使用してこのツールを実行することが必要な場合があります。</span><span class="sxs-lookup"><span data-stu-id="de942-124">On a system that supports User Account Control (UAC), you may need to run the tool with Administrative privileges.</span></span>  
  
#### <a name="to-set-credentials-for-host-group-type-affiliate-applications-using-the-command-line"></a><span data-ttu-id="de942-125">グループの種類が関連するコマンドラインを使用してアプリケーションのホストの資格情報を設定するには</span><span class="sxs-lookup"><span data-stu-id="de942-125">To set credentials for host group type affiliate applications using the command line</span></span>  
  
1.  <span data-ttu-id="de942-126">**[スタート]** メニューの **[ファイル名を指定して実行]** をクリックします。</span><span class="sxs-lookup"><span data-stu-id="de942-126">On the **Start** menu, click **Run**.</span></span>  
  
2.  <span data-ttu-id="de942-127">**実行**ダイアログ ボックスに「 **cmd**、順にクリックします**OK**します。</span><span class="sxs-lookup"><span data-stu-id="de942-127">In the **Run** dialog box, type **cmd**, and then click **OK**.</span></span>  
  
3.  <span data-ttu-id="de942-128">コマンド ラインで、エンタープライズ シングル サインオンのインストール ディレクトリに移動します。</span><span class="sxs-lookup"><span data-stu-id="de942-128">At the command line, go to the Enterprise Single Sign-On installation directory.</span></span> <span data-ttu-id="de942-129">既定値は\<ドライブ\>: \Program Files\Common \enterprise シングル サインオンします。</span><span class="sxs-lookup"><span data-stu-id="de942-129">The default is \<drive\>:\Program Files\Common Files\Enterprise Single Sign-On.</span></span>  
  
4.  <span data-ttu-id="de942-130">型**ssomanage-setcredentials\<外部アカウント名\>\<アプリケーション名\>** します。</span><span class="sxs-lookup"><span data-stu-id="de942-130">Type **ssomanage -setcredentials \<external account name\> \<application name\>**.</span></span>  
  
    > [!NOTE]
    >  <span data-ttu-id="de942-131">ユーザー アカウント制御 (UAC) をサポートするシステムでは、管理者特権を使用してこのツールを実行することが必要な場合があります。</span><span class="sxs-lookup"><span data-stu-id="de942-131">On a system that supports User Account Control (UAC), you may need to run the tool with Administrative privileges.</span></span>  
  
#### <a name="to-enable-mappings-for-individual-type-affiliate-applications-using-the-command-line"></a><span data-ttu-id="de942-132">コマンドラインを使用してアプリケーションを関連する個々 の型のマッピングを有効にするには</span><span class="sxs-lookup"><span data-stu-id="de942-132">To enable mappings for individual type affiliate applications using the command line</span></span>  
  
1.  <span data-ttu-id="de942-133">**[スタート]** メニューの **[ファイル名を指定して実行]** をクリックします。</span><span class="sxs-lookup"><span data-stu-id="de942-133">On the **Start** menu, click **Run**.</span></span>  
  
2.  <span data-ttu-id="de942-134">**実行**ダイアログ ボックスに「 **cmd**、順にクリックします**OK**します。</span><span class="sxs-lookup"><span data-stu-id="de942-134">In the **Run** dialog box, type **cmd**, and then click **OK**.</span></span>  
  
3.  <span data-ttu-id="de942-135">コマンド ラインで、エンタープライズ シングル サインオンのインストール ディレクトリに移動します。</span><span class="sxs-lookup"><span data-stu-id="de942-135">At the command line, go to the Enterprise Single Sign-On installation directory.</span></span> <span data-ttu-id="de942-136">既定値は\<ドライブ\>: \Program Files\Common \enterprise シングル サインオンします。</span><span class="sxs-lookup"><span data-stu-id="de942-136">The default is \<drive\>:\Program Files\Common Files\Enterprise Single Sign-On.</span></span>  
  
4.  <span data-ttu-id="de942-137">型**ssomanage-enablemapping \<Windows アカウント名\>\<アプリケーション名\>** します。</span><span class="sxs-lookup"><span data-stu-id="de942-137">Type **ssomanage -enablemapping \<Windows account name\> \<application name\>**.</span></span>  
  
    > [!NOTE]
    >  <span data-ttu-id="de942-138">ユーザー アカウント制御 (UAC) をサポートするシステムでは、管理者特権を使用してこのツールを実行することが必要な場合があります。</span><span class="sxs-lookup"><span data-stu-id="de942-138">On a system that supports User Account Control (UAC), you may need to run the tool with Administrative privileges.</span></span>  
  
#### <a name="to-disable-mappings-for-individual-type-affiliate-applications-using-the-command-line"></a><span data-ttu-id="de942-139">コマンドラインを使用してアプリケーションを関連する個々 の型のマッピングを無効にするには</span><span class="sxs-lookup"><span data-stu-id="de942-139">To disable mappings for individual type affiliate applications using the command line</span></span>  
  
1.  <span data-ttu-id="de942-140">**[スタート]** メニューの **[ファイル名を指定して実行]** をクリックします。</span><span class="sxs-lookup"><span data-stu-id="de942-140">On the **Start** menu, click **Run**.</span></span>  
  
2.  <span data-ttu-id="de942-141">**実行**ダイアログ ボックスに「 **cmd**、順にクリックします**OK**します。</span><span class="sxs-lookup"><span data-stu-id="de942-141">In the **Run** dialog box, type **cmd**, and then click **OK**.</span></span>  
  
3.  <span data-ttu-id="de942-142">コマンド ラインで、エンタープライズ シングル サインオンのインストール ディレクトリに移動します。</span><span class="sxs-lookup"><span data-stu-id="de942-142">At the command line, go to the Enterprise Single Sign-On installation directory.</span></span> <span data-ttu-id="de942-143">既定値は\<ドライブ\>: \Program Files\Common \enterprise シングル サインオンします。</span><span class="sxs-lookup"><span data-stu-id="de942-143">The default is \<drive\>:\Program Files\Common Files\Enterprise Single Sign-On.</span></span>  
  
4.  <span data-ttu-id="de942-144">型**ssomanage-disablemapping \<Windows アカウント名\>\<アプリケーション名\>** します。</span><span class="sxs-lookup"><span data-stu-id="de942-144">Type **ssomanage -disablemapping \<Windows account name\> \<application name\>**.</span></span>  
  
    > [!NOTE]
    >  <span data-ttu-id="de942-145">ユーザー アカウント制御 (UAC) をサポートするシステムでは、管理者特権を使用してこのツールを実行することが必要な場合があります。</span><span class="sxs-lookup"><span data-stu-id="de942-145">On a system that supports User Account Control (UAC), you may need to run the tool with Administrative privileges.</span></span>  
  
#### <a name="to-enable-mappings-for-host-group-type-affiliate-applications-using-the-command-line"></a><span data-ttu-id="de942-146">コマンドラインを使用してアプリケーションを関連するホスト グループの種類のマッピングを有効にするには</span><span class="sxs-lookup"><span data-stu-id="de942-146">To enable mappings for host group type affiliate applications using the command line</span></span>  
  
1.  <span data-ttu-id="de942-147">**[スタート]** メニューの **[ファイル名を指定して実行]** をクリックします。</span><span class="sxs-lookup"><span data-stu-id="de942-147">On the **Start** menu, click **Run**.</span></span>  
  
2.  <span data-ttu-id="de942-148">**実行**ダイアログ ボックスに「 **cmd**、順にクリックします**OK**します。</span><span class="sxs-lookup"><span data-stu-id="de942-148">In the **Run** dialog box, type **cmd**, and then click **OK**.</span></span>  
  
3.  <span data-ttu-id="de942-149">コマンド ラインで、エンタープライズ シングル サインオンのインストール ディレクトリに移動します。</span><span class="sxs-lookup"><span data-stu-id="de942-149">At the command line, go to the Enterprise Single Sign-On installation directory.</span></span> <span data-ttu-id="de942-150">既定値は\<ドライブ\>: \Program Files\Common \enterprise シングル サインオンします。</span><span class="sxs-lookup"><span data-stu-id="de942-150">The default is \<drive\>:\Program Files\Common Files\Enterprise Single Sign-On.</span></span>  
  
4.  <span data-ttu-id="de942-151">型**ssomanage-enablemapping\<外部アカウント名\>\<アプリケーション名\>** します。</span><span class="sxs-lookup"><span data-stu-id="de942-151">Type **ssomanage -enablemapping \<external account name\> \<application name\>**.</span></span>  
  
    > [!NOTE]
    >  <span data-ttu-id="de942-152">ユーザー アカウント制御 (UAC) をサポートするシステムでは、管理者特権を使用してこのツールを実行することが必要な場合があります。</span><span class="sxs-lookup"><span data-stu-id="de942-152">On a system that supports User Account Control (UAC), you may need to run the tool with Administrative privileges.</span></span>  
  
#### <a name="to-disable-mappings-for-individual-type-affiliate-applications-using-the-command-line"></a><span data-ttu-id="de942-153">コマンドラインを使用してアプリケーションを関連する個々 の型のマッピングを無効にするには</span><span class="sxs-lookup"><span data-stu-id="de942-153">To disable mappings for individual type affiliate applications using the command line</span></span>  
  
1.  <span data-ttu-id="de942-154">**[スタート]** メニューの **[ファイル名を指定して実行]** をクリックします。</span><span class="sxs-lookup"><span data-stu-id="de942-154">On the **Start** menu, click **Run**.</span></span>  
  
2.  <span data-ttu-id="de942-155">**実行**ダイアログ ボックスに「 **cmd**、順にクリックします**OK**します。</span><span class="sxs-lookup"><span data-stu-id="de942-155">In the **Run** dialog box, type **cmd**, and then click **OK**.</span></span>  
  
3.  <span data-ttu-id="de942-156">コマンド ラインで、エンタープライズ シングル サインオンのインストール ディレクトリに移動します。</span><span class="sxs-lookup"><span data-stu-id="de942-156">At the command line, go to the Enterprise Single Sign-On installation directory.</span></span> <span data-ttu-id="de942-157">既定値は\<ドライブ\>: \Program Files\Common \enterprise シングル サインオンします。</span><span class="sxs-lookup"><span data-stu-id="de942-157">The default is \<drive\>:\Program Files\Common Files\Enterprise Single Sign-On.</span></span>  
  
4.  <span data-ttu-id="de942-158">型**ssomanage-disablemapping\<外部アカウント名\>\<アプリケーション名\>** します。</span><span class="sxs-lookup"><span data-stu-id="de942-158">Type **ssomanage -disablemapping \<external account name\> \<application name\>**.</span></span>  
  
    > [!NOTE]
    >  <span data-ttu-id="de942-159">ユーザー アカウント制御 (UAC) をサポートするシステムでは、管理者特権を使用してこのツールを実行することが必要な場合があります。</span><span class="sxs-lookup"><span data-stu-id="de942-159">On a system that supports User Account Control (UAC), you may need to run the tool with Administrative privileges.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="de942-160">参照</span><span class="sxs-lookup"><span data-stu-id="de942-160">See Also</span></span>  
 [<span data-ttu-id="de942-161">ホスト側開始 SSO</span><span class="sxs-lookup"><span data-stu-id="de942-161">Host Initiated SSO</span></span>](../core/host-initiated-sso.md)