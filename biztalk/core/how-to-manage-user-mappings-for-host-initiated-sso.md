---
title: 側開始 SSO のホストのユーザー マッピングを管理する方法 |Microsoft ドキュメント
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
ms.openlocfilehash: a0bf65bdb3de30d5b701946215b5c7ae7d40d828
ms.sourcegitcommit: 5abd0ed3f9e4858ffaaec5481bfa8878595e95f7
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 11/28/2017
ms.locfileid: "25972384"
---
# <a name="how-to-manage-user-mappings-for-host-initiated-sso"></a><span data-ttu-id="9106b-102">側開始 SSO のホストのユーザー マッピングを管理する方法</span><span class="sxs-lookup"><span data-stu-id="9106b-102">How to Manage User Mappings for Host Initiated SSO</span></span>
<span data-ttu-id="9106b-103">次の手順を使用して、マッピングの作成、資格情報の設定、およびマッピングの有効化または無効化を行います。</span><span class="sxs-lookup"><span data-stu-id="9106b-103">Use the following procedures to create mappings, set credentials, and enable or disable mapping.</span></span>  
  
### <a name="to-manage-user-mappings-for-host-initiated-sso-using-the-mmc-snap-in"></a><span data-ttu-id="9106b-104">MMC スナップインを使用してホスト側開始 SSO のユーザー マッピングを管理するには</span><span class="sxs-lookup"><span data-stu-id="9106b-104">To manage user mappings for host initiated SSO using the MMC Snap-In</span></span>  
  
1.  <span data-ttu-id="9106b-105">**開始** メニューのをクリックして**すべてのプログラム**、 をクリックして**Microsoft エンタープライズ シングル サインオン**、クリックして**SSO 管理**です。</span><span class="sxs-lookup"><span data-stu-id="9106b-105">On the **Start** menu, click **All Programs**, click **Microsoft Enterprise Single Sign-On**, and then click **SSO Administration**.</span></span>  
  
2.  <span data-ttu-id="9106b-106">ENTSSO MMC スナップインの [スコープ] ウィンドウで、展開、**エンタープライズ シングル サインオン**ノード。</span><span class="sxs-lookup"><span data-stu-id="9106b-106">In the scope pane of the ENTSSO MMC Snap-In, expand the **Enterprise Single Sign-On** node.</span></span>  
  
3.  <span data-ttu-id="9106b-107">スコープ ペインで、をクリックして**関連アプリケーション**です。</span><span class="sxs-lookup"><span data-stu-id="9106b-107">In the scope pane, click **Affiliate Applications**.</span></span>  
  
4.  <span data-ttu-id="9106b-108">詳細ペインで、関連アプリケーションを右クリックし、アクションに適したメニュー項目を選択します。</span><span class="sxs-lookup"><span data-stu-id="9106b-108">In the details pane, right-click the affiliate application, and then choose the appropriate menu item for your action.</span></span>  
  
### <a name="to-create-mappings-in-host-initiated-sso-using-the-command-line"></a><span data-ttu-id="9106b-109">コマンド ラインを使用してホスト側開始 SSO のマッピングを作成するには</span><span class="sxs-lookup"><span data-stu-id="9106b-109">To create mappings in host initiated SSO using the command line</span></span>  
  
1.  <span data-ttu-id="9106b-110">**[スタート]** メニューの **[ファイル名を指定して実行]** をクリックします。</span><span class="sxs-lookup"><span data-stu-id="9106b-110">On the **Start** menu, click **Run**.</span></span>  
  
2.  <span data-ttu-id="9106b-111">**実行** ダイアログ ボックスで、「 **cmd**、順にクリック**OK**です。</span><span class="sxs-lookup"><span data-stu-id="9106b-111">In the **Run** dialog box, type **cmd**, and then click **OK**.</span></span>  
  
3.  <span data-ttu-id="9106b-112">コマンド ラインで、エンタープライズ シングル サインオンのインストール ディレクトリに移動します。</span><span class="sxs-lookup"><span data-stu-id="9106b-112">At the command line, go to the Enterprise Single Sign-On installation directory.</span></span> <span data-ttu-id="9106b-113">既定値は\<ドライブ\>: \program files \common files \enterprise シングル サインオンします。</span><span class="sxs-lookup"><span data-stu-id="9106b-113">The default is \<drive\>:\Program Files\Common Files\Enterprise Single Sign-On.</span></span>  
  
4.  <span data-ttu-id="9106b-114">型**ssomanage – createmappings\<マッピング ファイル\>** ここで、**マッピング ファイル >** xml ファイルの名前を指定します。</span><span class="sxs-lookup"><span data-stu-id="9106b-114">Type **ssomanage –createmappings \<mapping file\>**, where **mapping file>** is the name of the xml file.</span></span>  
  
    > [!NOTE]
    >  <span data-ttu-id="9106b-115">ユーザー アカウント制御 (UAC) をサポートするシステムでは、管理者特権を使用してこのツールを実行することが必要な場合があります。</span><span class="sxs-lookup"><span data-stu-id="9106b-115">On a system that supports User Account Control (UAC), you may need to run the tool with Administrative privileges.</span></span>  
  
     <span data-ttu-id="9106b-116">サンプル マッピング ファイルを次に示します。</span><span class="sxs-lookup"><span data-stu-id="9106b-116">A sample mapping file is shown below:</span></span>  
  
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
  
 <span data-ttu-id="9106b-117">関連アプリケーションのパスワードの検証機能が有効になっている場合、次のように資格情報を設定する必要があります。</span><span class="sxs-lookup"><span data-stu-id="9106b-117">When the Validate Password feature is enabled for the affiliate application, it is necessary to set credentials, as follows:</span></span>  
  
#### <a name="to-set-credentials-for-individual-type-affiliate-applications-using-the-command-line"></a><span data-ttu-id="9106b-118">コマンド ラインを使用して単独タイプの関連アプリケーションの資格情報を設定するには</span><span class="sxs-lookup"><span data-stu-id="9106b-118">To set credentials for individual type affiliate applications using the command line</span></span>  
  
1.  <span data-ttu-id="9106b-119">**[スタート]** メニューの **[ファイル名を指定して実行]** をクリックします。</span><span class="sxs-lookup"><span data-stu-id="9106b-119">On the **Start** menu, click **Run**.</span></span>  
  
2.  <span data-ttu-id="9106b-120">**実行** ダイアログ ボックスで、「 **cmd**、順にクリック**OK**です。</span><span class="sxs-lookup"><span data-stu-id="9106b-120">In the **Run** dialog box, type **cmd**, and then click **OK**.</span></span>  
  
3.  <span data-ttu-id="9106b-121">コマンド ラインで、エンタープライズ シングル サインオンのインストール ディレクトリに移動します。</span><span class="sxs-lookup"><span data-stu-id="9106b-121">At the command line, go to the Enterprise Single Sign-On installation directory.</span></span> <span data-ttu-id="9106b-122">既定値は\<ドライブ\>: \program files \common files \enterprise シングル サインオンします。</span><span class="sxs-lookup"><span data-stu-id="9106b-122">The default is \<drive\>:\Program Files\Common Files\Enterprise Single Sign-On.</span></span>  
  
4.  <span data-ttu-id="9106b-123">型**ssomanage-setcredentials \<Windows アカウント名\>\<アプリケーション名\>** です。</span><span class="sxs-lookup"><span data-stu-id="9106b-123">Type **ssomanage -setcredentials \<Windows account name\> \<application name\>**.</span></span>  
  
    > [!NOTE]
    >  <span data-ttu-id="9106b-124">ユーザー アカウント制御 (UAC) をサポートするシステムでは、管理者特権を使用してこのツールを実行することが必要な場合があります。</span><span class="sxs-lookup"><span data-stu-id="9106b-124">On a system that supports User Account Control (UAC), you may need to run the tool with Administrative privileges.</span></span>  
  
#### <a name="to-set-credentials-for-host-group-type-affiliate-applications-using-the-command-line"></a><span data-ttu-id="9106b-125">コマンド ラインを使用してホスト グループ タイプの関連アプリケーションの資格情報を設定するには</span><span class="sxs-lookup"><span data-stu-id="9106b-125">To set credentials for host group type affiliate applications using the command line</span></span>  
  
1.  <span data-ttu-id="9106b-126">**[スタート]** メニューの **[ファイル名を指定して実行]** をクリックします。</span><span class="sxs-lookup"><span data-stu-id="9106b-126">On the **Start** menu, click **Run**.</span></span>  
  
2.  <span data-ttu-id="9106b-127">**実行** ダイアログ ボックスで、「 **cmd**、順にクリック**OK**です。</span><span class="sxs-lookup"><span data-stu-id="9106b-127">In the **Run** dialog box, type **cmd**, and then click **OK**.</span></span>  
  
3.  <span data-ttu-id="9106b-128">コマンド ラインで、エンタープライズ シングル サインオンのインストール ディレクトリに移動します。</span><span class="sxs-lookup"><span data-stu-id="9106b-128">At the command line, go to the Enterprise Single Sign-On installation directory.</span></span> <span data-ttu-id="9106b-129">既定値は\<ドライブ\>: \program files \common files \enterprise シングル サインオンします。</span><span class="sxs-lookup"><span data-stu-id="9106b-129">The default is \<drive\>:\Program Files\Common Files\Enterprise Single Sign-On.</span></span>  
  
4.  <span data-ttu-id="9106b-130">型**ssomanage-setcredentials\<外部アカウント名\>\<アプリケーション名\>** です。</span><span class="sxs-lookup"><span data-stu-id="9106b-130">Type **ssomanage -setcredentials \<external account name\> \<application name\>**.</span></span>  
  
    > [!NOTE]
    >  <span data-ttu-id="9106b-131">ユーザー アカウント制御 (UAC) をサポートするシステムでは、管理者特権を使用してこのツールを実行することが必要な場合があります。</span><span class="sxs-lookup"><span data-stu-id="9106b-131">On a system that supports User Account Control (UAC), you may need to run the tool with Administrative privileges.</span></span>  
  
#### <a name="to-enable-mappings-for-individual-type-affiliate-applications-using-the-command-line"></a><span data-ttu-id="9106b-132">コマンド ラインを使用して単独タイプの関連アプリケーションのマッピングを有効にするには</span><span class="sxs-lookup"><span data-stu-id="9106b-132">To enable mappings for individual type affiliate applications using the command line</span></span>  
  
1.  <span data-ttu-id="9106b-133">**[スタート]** メニューの **[ファイル名を指定して実行]** をクリックします。</span><span class="sxs-lookup"><span data-stu-id="9106b-133">On the **Start** menu, click **Run**.</span></span>  
  
2.  <span data-ttu-id="9106b-134">**実行** ダイアログ ボックスで、「 **cmd**、順にクリック**OK**です。</span><span class="sxs-lookup"><span data-stu-id="9106b-134">In the **Run** dialog box, type **cmd**, and then click **OK**.</span></span>  
  
3.  <span data-ttu-id="9106b-135">コマンド ラインで、エンタープライズ シングル サインオンのインストール ディレクトリに移動します。</span><span class="sxs-lookup"><span data-stu-id="9106b-135">At the command line, go to the Enterprise Single Sign-On installation directory.</span></span> <span data-ttu-id="9106b-136">既定値は\<ドライブ\>: \program files \common files \enterprise シングル サインオンします。</span><span class="sxs-lookup"><span data-stu-id="9106b-136">The default is \<drive\>:\Program Files\Common Files\Enterprise Single Sign-On.</span></span>  
  
4.  <span data-ttu-id="9106b-137">型**ssomanage-enablemapping \<Windows アカウント名\>\<アプリケーション名\>** です。</span><span class="sxs-lookup"><span data-stu-id="9106b-137">Type **ssomanage -enablemapping \<Windows account name\> \<application name\>**.</span></span>  
  
    > [!NOTE]
    >  <span data-ttu-id="9106b-138">ユーザー アカウント制御 (UAC) をサポートするシステムでは、管理者特権を使用してこのツールを実行することが必要な場合があります。</span><span class="sxs-lookup"><span data-stu-id="9106b-138">On a system that supports User Account Control (UAC), you may need to run the tool with Administrative privileges.</span></span>  
  
#### <a name="to-disable-mappings-for-individual-type-affiliate-applications-using-the-command-line"></a><span data-ttu-id="9106b-139">コマンド ラインを使用して単独タイプの関連アプリケーションのマッピングを無効にするには</span><span class="sxs-lookup"><span data-stu-id="9106b-139">To disable mappings for individual type affiliate applications using the command line</span></span>  
  
1.  <span data-ttu-id="9106b-140">**[スタート]** メニューの **[ファイル名を指定して実行]** をクリックします。</span><span class="sxs-lookup"><span data-stu-id="9106b-140">On the **Start** menu, click **Run**.</span></span>  
  
2.  <span data-ttu-id="9106b-141">**実行** ダイアログ ボックスで、「 **cmd**、順にクリック**OK**です。</span><span class="sxs-lookup"><span data-stu-id="9106b-141">In the **Run** dialog box, type **cmd**, and then click **OK**.</span></span>  
  
3.  <span data-ttu-id="9106b-142">コマンド ラインで、エンタープライズ シングル サインオンのインストール ディレクトリに移動します。</span><span class="sxs-lookup"><span data-stu-id="9106b-142">At the command line, go to the Enterprise Single Sign-On installation directory.</span></span> <span data-ttu-id="9106b-143">既定値は\<ドライブ\>: \program files \common files \enterprise シングル サインオンします。</span><span class="sxs-lookup"><span data-stu-id="9106b-143">The default is \<drive\>:\Program Files\Common Files\Enterprise Single Sign-On.</span></span>  
  
4.  <span data-ttu-id="9106b-144">型**ssomanage-disablemapping \<Windows アカウント名\>\<アプリケーション名\>** です。</span><span class="sxs-lookup"><span data-stu-id="9106b-144">Type **ssomanage -disablemapping \<Windows account name\> \<application name\>**.</span></span>  
  
    > [!NOTE]
    >  <span data-ttu-id="9106b-145">ユーザー アカウント制御 (UAC) をサポートするシステムでは、管理者特権を使用してこのツールを実行することが必要な場合があります。</span><span class="sxs-lookup"><span data-stu-id="9106b-145">On a system that supports User Account Control (UAC), you may need to run the tool with Administrative privileges.</span></span>  
  
#### <a name="to-enable-mappings-for-host-group-type-affiliate-applications-using-the-command-line"></a><span data-ttu-id="9106b-146">コマンド ラインを使用してホスト グループ タイプの関連アプリケーションのマッピングを有効にするには</span><span class="sxs-lookup"><span data-stu-id="9106b-146">To enable mappings for host group type affiliate applications using the command line</span></span>  
  
1.  <span data-ttu-id="9106b-147">**[スタート]** メニューの **[ファイル名を指定して実行]** をクリックします。</span><span class="sxs-lookup"><span data-stu-id="9106b-147">On the **Start** menu, click **Run**.</span></span>  
  
2.  <span data-ttu-id="9106b-148">**実行** ダイアログ ボックスで、「 **cmd**、順にクリック**OK**です。</span><span class="sxs-lookup"><span data-stu-id="9106b-148">In the **Run** dialog box, type **cmd**, and then click **OK**.</span></span>  
  
3.  <span data-ttu-id="9106b-149">コマンド ラインで、エンタープライズ シングル サインオンのインストール ディレクトリに移動します。</span><span class="sxs-lookup"><span data-stu-id="9106b-149">At the command line, go to the Enterprise Single Sign-On installation directory.</span></span> <span data-ttu-id="9106b-150">既定値は\<ドライブ\>: \program files \common files \enterprise シングル サインオンします。</span><span class="sxs-lookup"><span data-stu-id="9106b-150">The default is \<drive\>:\Program Files\Common Files\Enterprise Single Sign-On.</span></span>  
  
4.  <span data-ttu-id="9106b-151">型**ssomanage-enablemapping\<外部アカウント名\>\<アプリケーション名\>** です。</span><span class="sxs-lookup"><span data-stu-id="9106b-151">Type **ssomanage -enablemapping \<external account name\> \<application name\>**.</span></span>  
  
    > [!NOTE]
    >  <span data-ttu-id="9106b-152">ユーザー アカウント制御 (UAC) をサポートするシステムでは、管理者特権を使用してこのツールを実行することが必要な場合があります。</span><span class="sxs-lookup"><span data-stu-id="9106b-152">On a system that supports User Account Control (UAC), you may need to run the tool with Administrative privileges.</span></span>  
  
#### <a name="to-disable-mappings-for-individual-type-affiliate-applications-using-the-command-line"></a><span data-ttu-id="9106b-153">コマンド ラインを使用して単独タイプの関連アプリケーションのマッピングを無効にするには</span><span class="sxs-lookup"><span data-stu-id="9106b-153">To disable mappings for individual type affiliate applications using the command line</span></span>  
  
1.  <span data-ttu-id="9106b-154">**[スタート]** メニューの **[ファイル名を指定して実行]** をクリックします。</span><span class="sxs-lookup"><span data-stu-id="9106b-154">On the **Start** menu, click **Run**.</span></span>  
  
2.  <span data-ttu-id="9106b-155">**実行** ダイアログ ボックスで、「 **cmd**、順にクリック**OK**です。</span><span class="sxs-lookup"><span data-stu-id="9106b-155">In the **Run** dialog box, type **cmd**, and then click **OK**.</span></span>  
  
3.  <span data-ttu-id="9106b-156">コマンド ラインで、エンタープライズ シングル サインオンのインストール ディレクトリに移動します。</span><span class="sxs-lookup"><span data-stu-id="9106b-156">At the command line, go to the Enterprise Single Sign-On installation directory.</span></span> <span data-ttu-id="9106b-157">既定値は\<ドライブ\>: \program files \common files \enterprise シングル サインオンします。</span><span class="sxs-lookup"><span data-stu-id="9106b-157">The default is \<drive\>:\Program Files\Common Files\Enterprise Single Sign-On.</span></span>  
  
4.  <span data-ttu-id="9106b-158">型**ssomanage-disablemapping\<外部アカウント名\>\<アプリケーション名\>** です。</span><span class="sxs-lookup"><span data-stu-id="9106b-158">Type **ssomanage -disablemapping \<external account name\> \<application name\>**.</span></span>  
  
    > [!NOTE]
    >  <span data-ttu-id="9106b-159">ユーザー アカウント制御 (UAC) をサポートするシステムでは、管理者特権を使用してこのツールを実行することが必要な場合があります。</span><span class="sxs-lookup"><span data-stu-id="9106b-159">On a system that supports User Account Control (UAC), you may need to run the tool with Administrative privileges.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="9106b-160">参照</span><span class="sxs-lookup"><span data-stu-id="9106b-160">See Also</span></span>  
 [<span data-ttu-id="9106b-161">ホスト側開始 SSO</span><span class="sxs-lookup"><span data-stu-id="9106b-161">Host Initiated SSO</span></span>](../core/host-initiated-sso.md)