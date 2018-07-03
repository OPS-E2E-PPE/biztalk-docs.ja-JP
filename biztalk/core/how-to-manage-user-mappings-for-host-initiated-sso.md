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
ms.openlocfilehash: ad232bf81fff96e6cabf367e9c591d02d4296151
ms.sourcegitcommit: 266308ec5c6a9d8d80ff298ee6051b4843c5d626
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 06/27/2018
ms.locfileid: "37006707"
---
# <a name="how-to-manage-user-mappings-for-host-initiated-sso"></a><span data-ttu-id="23c71-102">側開始 SSO のホストのユーザー マッピングを管理する方法</span><span class="sxs-lookup"><span data-stu-id="23c71-102">How to Manage User Mappings for Host Initiated SSO</span></span>
<span data-ttu-id="23c71-103">次の手順を使用して、マッピングの作成、資格情報の設定、およびマッピングの有効化または無効化を行います。</span><span class="sxs-lookup"><span data-stu-id="23c71-103">Use the following procedures to create mappings, set credentials, and enable or disable mapping.</span></span>  
  
### <a name="to-manage-user-mappings-for-host-initiated-sso-using-the-mmc-snap-in"></a><span data-ttu-id="23c71-104">MMC スナップインを使用してホスト側開始 SSO のユーザー マッピングを管理するには</span><span class="sxs-lookup"><span data-stu-id="23c71-104">To manage user mappings for host initiated SSO using the MMC Snap-In</span></span>  
  
1.  <span data-ttu-id="23c71-105">**開始** メニューのをクリックして**すべてのプログラム**、 をクリックして**Microsoft エンタープライズ シングル サインオン**、 をクリックし、 **SSO 管理**。</span><span class="sxs-lookup"><span data-stu-id="23c71-105">On the **Start** menu, click **All Programs**, click **Microsoft Enterprise Single Sign-On**, and then click **SSO Administration**.</span></span>  
  
2.  <span data-ttu-id="23c71-106">ENTSSO MMC スナップインの [スコープ] ウィンドウで、**エンタープライズ シングル サインオン**ノード。</span><span class="sxs-lookup"><span data-stu-id="23c71-106">In the scope pane of the ENTSSO MMC Snap-In, expand the **Enterprise Single Sign-On** node.</span></span>  
  
3.  <span data-ttu-id="23c71-107">スコープ ペインで次のようにクリックします。**関連アプリケーション**します。</span><span class="sxs-lookup"><span data-stu-id="23c71-107">In the scope pane, click **Affiliate Applications**.</span></span>  
  
4.  <span data-ttu-id="23c71-108">詳細ペインで、関連アプリケーションを右クリックし、アクションに適したメニュー項目を選択します。</span><span class="sxs-lookup"><span data-stu-id="23c71-108">In the details pane, right-click the affiliate application, and then choose the appropriate menu item for your action.</span></span>  
  
### <a name="to-create-mappings-in-host-initiated-sso-using-the-command-line"></a><span data-ttu-id="23c71-109">コマンド ラインを使用してホスト側開始 SSO のマッピングを作成するには</span><span class="sxs-lookup"><span data-stu-id="23c71-109">To create mappings in host initiated SSO using the command line</span></span>  
  
1. <span data-ttu-id="23c71-110">**[スタート]** メニューの **[ファイル名を指定して実行]** をクリックします。</span><span class="sxs-lookup"><span data-stu-id="23c71-110">On the **Start** menu, click **Run**.</span></span>  
  
2. <span data-ttu-id="23c71-111">**実行**ダイアログ ボックスに「 **cmd**、順にクリックします**OK**します。</span><span class="sxs-lookup"><span data-stu-id="23c71-111">In the **Run** dialog box, type **cmd**, and then click **OK**.</span></span>  
  
3. <span data-ttu-id="23c71-112">コマンド ラインで、エンタープライズ シングル サインオンのインストール ディレクトリに移動します。</span><span class="sxs-lookup"><span data-stu-id="23c71-112">At the command line, go to the Enterprise Single Sign-On installation directory.</span></span> <span data-ttu-id="23c71-113">既定値は\<ドライブ\>: \Program Files\Common \enterprise シングル サインオンします。</span><span class="sxs-lookup"><span data-stu-id="23c71-113">The default is \<drive\>:\Program Files\Common Files\Enterprise Single Sign-On.</span></span>  
  
4. <span data-ttu-id="23c71-114">型**ssomanage – createmappings\<マッピング ファイル\>** ここで、**マッピング ファイル >** xml ファイルの名前を指定します。</span><span class="sxs-lookup"><span data-stu-id="23c71-114">Type **ssomanage –createmappings \<mapping file\>**, where **mapping file>** is the name of the xml file.</span></span>  
  
   > [!NOTE]
   >  <span data-ttu-id="23c71-115">ユーザー アカウント制御 (UAC) をサポートするシステムでは、管理者特権を使用してこのツールを実行することが必要な場合があります。</span><span class="sxs-lookup"><span data-stu-id="23c71-115">On a system that supports User Account Control (UAC), you may need to run the tool with Administrative privileges.</span></span>  
  
    <span data-ttu-id="23c71-116">サンプル マッピング ファイルを次に示します。</span><span class="sxs-lookup"><span data-stu-id="23c71-116">A sample mapping file is shown below:</span></span>  
  
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
  
   <span data-ttu-id="23c71-117">関連アプリケーションのパスワードの検証機能が有効になっている場合、次のように資格情報を設定する必要があります。</span><span class="sxs-lookup"><span data-stu-id="23c71-117">When the Validate Password feature is enabled for the affiliate application, it is necessary to set credentials, as follows:</span></span>  
  
#### <a name="to-set-credentials-for-individual-type-affiliate-applications-using-the-command-line"></a><span data-ttu-id="23c71-118">コマンド ラインを使用して単独タイプの関連アプリケーションの資格情報を設定するには</span><span class="sxs-lookup"><span data-stu-id="23c71-118">To set credentials for individual type affiliate applications using the command line</span></span>  
  
1.  <span data-ttu-id="23c71-119">**[スタート]** メニューの **[ファイル名を指定して実行]** をクリックします。</span><span class="sxs-lookup"><span data-stu-id="23c71-119">On the **Start** menu, click **Run**.</span></span>  
  
2.  <span data-ttu-id="23c71-120">**実行**ダイアログ ボックスに「 **cmd**、順にクリックします**OK**します。</span><span class="sxs-lookup"><span data-stu-id="23c71-120">In the **Run** dialog box, type **cmd**, and then click **OK**.</span></span>  
  
3.  <span data-ttu-id="23c71-121">コマンド ラインで、エンタープライズ シングル サインオンのインストール ディレクトリに移動します。</span><span class="sxs-lookup"><span data-stu-id="23c71-121">At the command line, go to the Enterprise Single Sign-On installation directory.</span></span> <span data-ttu-id="23c71-122">既定値は\<ドライブ\>: \Program Files\Common \enterprise シングル サインオンします。</span><span class="sxs-lookup"><span data-stu-id="23c71-122">The default is \<drive\>:\Program Files\Common Files\Enterprise Single Sign-On.</span></span>  
  
4.  <span data-ttu-id="23c71-123">型**ssomanage-setcredentials \<Windows アカウント名\>\<アプリケーション名\>** します。</span><span class="sxs-lookup"><span data-stu-id="23c71-123">Type **ssomanage -setcredentials \<Windows account name\> \<application name\>**.</span></span>  
  
    > [!NOTE]
    >  <span data-ttu-id="23c71-124">ユーザー アカウント制御 (UAC) をサポートするシステムでは、管理者特権を使用してこのツールを実行することが必要な場合があります。</span><span class="sxs-lookup"><span data-stu-id="23c71-124">On a system that supports User Account Control (UAC), you may need to run the tool with Administrative privileges.</span></span>  
  
#### <a name="to-set-credentials-for-host-group-type-affiliate-applications-using-the-command-line"></a><span data-ttu-id="23c71-125">コマンド ラインを使用してホスト グループ タイプの関連アプリケーションの資格情報を設定するには</span><span class="sxs-lookup"><span data-stu-id="23c71-125">To set credentials for host group type affiliate applications using the command line</span></span>  
  
1.  <span data-ttu-id="23c71-126">**[スタート]** メニューの **[ファイル名を指定して実行]** をクリックします。</span><span class="sxs-lookup"><span data-stu-id="23c71-126">On the **Start** menu, click **Run**.</span></span>  
  
2.  <span data-ttu-id="23c71-127">**実行**ダイアログ ボックスに「 **cmd**、順にクリックします**OK**します。</span><span class="sxs-lookup"><span data-stu-id="23c71-127">In the **Run** dialog box, type **cmd**, and then click **OK**.</span></span>  
  
3.  <span data-ttu-id="23c71-128">コマンド ラインで、エンタープライズ シングル サインオンのインストール ディレクトリに移動します。</span><span class="sxs-lookup"><span data-stu-id="23c71-128">At the command line, go to the Enterprise Single Sign-On installation directory.</span></span> <span data-ttu-id="23c71-129">既定値は\<ドライブ\>: \Program Files\Common \enterprise シングル サインオンします。</span><span class="sxs-lookup"><span data-stu-id="23c71-129">The default is \<drive\>:\Program Files\Common Files\Enterprise Single Sign-On.</span></span>  
  
4.  <span data-ttu-id="23c71-130">型**ssomanage-setcredentials\<外部アカウント名\>\<アプリケーション名\>** します。</span><span class="sxs-lookup"><span data-stu-id="23c71-130">Type **ssomanage -setcredentials \<external account name\> \<application name\>**.</span></span>  
  
    > [!NOTE]
    >  <span data-ttu-id="23c71-131">ユーザー アカウント制御 (UAC) をサポートするシステムでは、管理者特権を使用してこのツールを実行することが必要な場合があります。</span><span class="sxs-lookup"><span data-stu-id="23c71-131">On a system that supports User Account Control (UAC), you may need to run the tool with Administrative privileges.</span></span>  
  
#### <a name="to-enable-mappings-for-individual-type-affiliate-applications-using-the-command-line"></a><span data-ttu-id="23c71-132">コマンド ラインを使用して単独タイプの関連アプリケーションのマッピングを有効にするには</span><span class="sxs-lookup"><span data-stu-id="23c71-132">To enable mappings for individual type affiliate applications using the command line</span></span>  
  
1.  <span data-ttu-id="23c71-133">**[スタート]** メニューの **[ファイル名を指定して実行]** をクリックします。</span><span class="sxs-lookup"><span data-stu-id="23c71-133">On the **Start** menu, click **Run**.</span></span>  
  
2.  <span data-ttu-id="23c71-134">**実行**ダイアログ ボックスに「 **cmd**、順にクリックします**OK**します。</span><span class="sxs-lookup"><span data-stu-id="23c71-134">In the **Run** dialog box, type **cmd**, and then click **OK**.</span></span>  
  
3.  <span data-ttu-id="23c71-135">コマンド ラインで、エンタープライズ シングル サインオンのインストール ディレクトリに移動します。</span><span class="sxs-lookup"><span data-stu-id="23c71-135">At the command line, go to the Enterprise Single Sign-On installation directory.</span></span> <span data-ttu-id="23c71-136">既定値は\<ドライブ\>: \Program Files\Common \enterprise シングル サインオンします。</span><span class="sxs-lookup"><span data-stu-id="23c71-136">The default is \<drive\>:\Program Files\Common Files\Enterprise Single Sign-On.</span></span>  
  
4.  <span data-ttu-id="23c71-137">型**ssomanage-enablemapping \<Windows アカウント名\>\<アプリケーション名\>** します。</span><span class="sxs-lookup"><span data-stu-id="23c71-137">Type **ssomanage -enablemapping \<Windows account name\> \<application name\>**.</span></span>  
  
    > [!NOTE]
    >  <span data-ttu-id="23c71-138">ユーザー アカウント制御 (UAC) をサポートするシステムでは、管理者特権を使用してこのツールを実行することが必要な場合があります。</span><span class="sxs-lookup"><span data-stu-id="23c71-138">On a system that supports User Account Control (UAC), you may need to run the tool with Administrative privileges.</span></span>  
  
#### <a name="to-disable-mappings-for-individual-type-affiliate-applications-using-the-command-line"></a><span data-ttu-id="23c71-139">コマンド ラインを使用して単独タイプの関連アプリケーションのマッピングを無効にするには</span><span class="sxs-lookup"><span data-stu-id="23c71-139">To disable mappings for individual type affiliate applications using the command line</span></span>  
  
1.  <span data-ttu-id="23c71-140">**[スタート]** メニューの **[ファイル名を指定して実行]** をクリックします。</span><span class="sxs-lookup"><span data-stu-id="23c71-140">On the **Start** menu, click **Run**.</span></span>  
  
2.  <span data-ttu-id="23c71-141">**実行**ダイアログ ボックスに「 **cmd**、順にクリックします**OK**します。</span><span class="sxs-lookup"><span data-stu-id="23c71-141">In the **Run** dialog box, type **cmd**, and then click **OK**.</span></span>  
  
3.  <span data-ttu-id="23c71-142">コマンド ラインで、エンタープライズ シングル サインオンのインストール ディレクトリに移動します。</span><span class="sxs-lookup"><span data-stu-id="23c71-142">At the command line, go to the Enterprise Single Sign-On installation directory.</span></span> <span data-ttu-id="23c71-143">既定値は\<ドライブ\>: \Program Files\Common \enterprise シングル サインオンします。</span><span class="sxs-lookup"><span data-stu-id="23c71-143">The default is \<drive\>:\Program Files\Common Files\Enterprise Single Sign-On.</span></span>  
  
4.  <span data-ttu-id="23c71-144">型**ssomanage-disablemapping \<Windows アカウント名\>\<アプリケーション名\>** します。</span><span class="sxs-lookup"><span data-stu-id="23c71-144">Type **ssomanage -disablemapping \<Windows account name\> \<application name\>**.</span></span>  
  
    > [!NOTE]
    >  <span data-ttu-id="23c71-145">ユーザー アカウント制御 (UAC) をサポートするシステムでは、管理者特権を使用してこのツールを実行することが必要な場合があります。</span><span class="sxs-lookup"><span data-stu-id="23c71-145">On a system that supports User Account Control (UAC), you may need to run the tool with Administrative privileges.</span></span>  
  
#### <a name="to-enable-mappings-for-host-group-type-affiliate-applications-using-the-command-line"></a><span data-ttu-id="23c71-146">コマンド ラインを使用してホスト グループ タイプの関連アプリケーションのマッピングを有効にするには</span><span class="sxs-lookup"><span data-stu-id="23c71-146">To enable mappings for host group type affiliate applications using the command line</span></span>  
  
1.  <span data-ttu-id="23c71-147">**[スタート]** メニューの **[ファイル名を指定して実行]** をクリックします。</span><span class="sxs-lookup"><span data-stu-id="23c71-147">On the **Start** menu, click **Run**.</span></span>  
  
2.  <span data-ttu-id="23c71-148">**実行**ダイアログ ボックスに「 **cmd**、順にクリックします**OK**します。</span><span class="sxs-lookup"><span data-stu-id="23c71-148">In the **Run** dialog box, type **cmd**, and then click **OK**.</span></span>  
  
3.  <span data-ttu-id="23c71-149">コマンド ラインで、エンタープライズ シングル サインオンのインストール ディレクトリに移動します。</span><span class="sxs-lookup"><span data-stu-id="23c71-149">At the command line, go to the Enterprise Single Sign-On installation directory.</span></span> <span data-ttu-id="23c71-150">既定値は\<ドライブ\>: \Program Files\Common \enterprise シングル サインオンします。</span><span class="sxs-lookup"><span data-stu-id="23c71-150">The default is \<drive\>:\Program Files\Common Files\Enterprise Single Sign-On.</span></span>  
  
4.  <span data-ttu-id="23c71-151">型**ssomanage-enablemapping\<外部アカウント名\>\<アプリケーション名\>** します。</span><span class="sxs-lookup"><span data-stu-id="23c71-151">Type **ssomanage -enablemapping \<external account name\> \<application name\>**.</span></span>  
  
    > [!NOTE]
    >  <span data-ttu-id="23c71-152">ユーザー アカウント制御 (UAC) をサポートするシステムでは、管理者特権を使用してこのツールを実行することが必要な場合があります。</span><span class="sxs-lookup"><span data-stu-id="23c71-152">On a system that supports User Account Control (UAC), you may need to run the tool with Administrative privileges.</span></span>  
  
#### <a name="to-disable-mappings-for-individual-type-affiliate-applications-using-the-command-line"></a><span data-ttu-id="23c71-153">コマンド ラインを使用して単独タイプの関連アプリケーションのマッピングを無効にするには</span><span class="sxs-lookup"><span data-stu-id="23c71-153">To disable mappings for individual type affiliate applications using the command line</span></span>  
  
1.  <span data-ttu-id="23c71-154">**[スタート]** メニューの **[ファイル名を指定して実行]** をクリックします。</span><span class="sxs-lookup"><span data-stu-id="23c71-154">On the **Start** menu, click **Run**.</span></span>  
  
2.  <span data-ttu-id="23c71-155">**実行**ダイアログ ボックスに「 **cmd**、順にクリックします**OK**します。</span><span class="sxs-lookup"><span data-stu-id="23c71-155">In the **Run** dialog box, type **cmd**, and then click **OK**.</span></span>  
  
3.  <span data-ttu-id="23c71-156">コマンド ラインで、エンタープライズ シングル サインオンのインストール ディレクトリに移動します。</span><span class="sxs-lookup"><span data-stu-id="23c71-156">At the command line, go to the Enterprise Single Sign-On installation directory.</span></span> <span data-ttu-id="23c71-157">既定値は\<ドライブ\>: \Program Files\Common \enterprise シングル サインオンします。</span><span class="sxs-lookup"><span data-stu-id="23c71-157">The default is \<drive\>:\Program Files\Common Files\Enterprise Single Sign-On.</span></span>  
  
4.  <span data-ttu-id="23c71-158">型**ssomanage-disablemapping\<外部アカウント名\>\<アプリケーション名\>** します。</span><span class="sxs-lookup"><span data-stu-id="23c71-158">Type **ssomanage -disablemapping \<external account name\> \<application name\>**.</span></span>  
  
    > [!NOTE]
    >  <span data-ttu-id="23c71-159">ユーザー アカウント制御 (UAC) をサポートするシステムでは、管理者特権を使用してこのツールを実行することが必要な場合があります。</span><span class="sxs-lookup"><span data-stu-id="23c71-159">On a system that supports User Account Control (UAC), you may need to run the tool with Administrative privileges.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="23c71-160">参照</span><span class="sxs-lookup"><span data-stu-id="23c71-160">See Also</span></span>  
 [<span data-ttu-id="23c71-161">ホスト側開始 SSO</span><span class="sxs-lookup"><span data-stu-id="23c71-161">Host Initiated SSO</span></span>](../core/host-initiated-sso.md)