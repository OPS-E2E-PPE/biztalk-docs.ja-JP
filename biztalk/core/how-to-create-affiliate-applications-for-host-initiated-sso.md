---
title: 側開始 SSO 関連アプリケーション ホストを作成する方法 |Microsoft Docs
ms.custom: ''
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: ''
ms.suite: ''
ms.tgt_pltfrm: ''
ms.topic: article
helpviewer_keywords:
- applications [SSO], host initiated SSO
- creating, applications [SSO]
- host initiated SSO, creating affiliate applications
ms.assetid: 06202d21-055a-46bc-acff-da461f5673f1
caps.latest.revision: 10
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: d207766ce830da973a4767213810f07432c743fc
ms.sourcegitcommit: 381e83d43796a345488d54b3f7413e11d56ad7be
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 05/07/2019
ms.locfileid: "65339832"
---
# <a name="how-to-create-affiliate-applications-for-host-initiated-sso"></a><span data-ttu-id="01c74-102">ホスト側開始 SSO 関連アプリケーションを作成する方法</span><span class="sxs-lookup"><span data-stu-id="01c74-102">How to Create Affiliate Applications for Host Initiated SSO</span></span>
<span data-ttu-id="01c74-103">2 種類のアプリケーションを定義できます。</span><span class="sxs-lookup"><span data-stu-id="01c74-103">You can define two types of applications:</span></span>  
  
-   <span data-ttu-id="01c74-104">**個別**は Windows および Windows 以外のユーザーに一対一のリレーションシップがあります。</span><span class="sxs-lookup"><span data-stu-id="01c74-104">**Individual** There is a 1 to 1 relationship between Windows users and non-Windows users.</span></span>  
  
-   <span data-ttu-id="01c74-105">**ホスト グループ**同じ Windows アカウントに複数の Windows 以外のユーザーをマップすることができます。</span><span class="sxs-lookup"><span data-stu-id="01c74-105">**Host Group** Multiple non-Windows users can be mapped to the same Windows account.</span></span>  
  
### <a name="to-create-an-affiliate-application-using-the-mmc-snap-in"></a><span data-ttu-id="01c74-106">MMC スナップインを使用して関連アプリケーションを作成するには</span><span class="sxs-lookup"><span data-stu-id="01c74-106">To create an affiliate application using the MMC Snap-In</span></span>  
  
1.  <span data-ttu-id="01c74-107">**開始** メニューのをクリックして**すべてのプログラム**、 をクリックして**Microsoft エンタープライズ シングル サインオン**、 をクリックし、 **SSO 管理**。</span><span class="sxs-lookup"><span data-stu-id="01c74-107">On the **Start** menu, click **All Programs**, click **Microsoft Enterprise Single Sign-On**, and then click **SSO Administration**.</span></span>  
  
2.  <span data-ttu-id="01c74-108">ENTSSO MMC スナップインの [スコープ] ウィンドウで、**エンタープライズ シングル サインオン**ノード。</span><span class="sxs-lookup"><span data-stu-id="01c74-108">In the scope pane of the ENTSSO MMC Snap-In, expand the **Enterprise Single Sign-On** node.</span></span>  
  
3.  <span data-ttu-id="01c74-109">右クリック**関連アプリケーション**、 をクリックし、**アプリケーションの作成**を開く、**エンタープライズ シングル サインオン アプリケーション ウィザード**します。</span><span class="sxs-lookup"><span data-stu-id="01c74-109">Right-click **Affiliate Applications**, and then click **Create Application** to open the **Enterprise Single Sign-On Application Wizard**.</span></span>  
  
4.  <span data-ttu-id="01c74-110">ウィザードを使用して、関連アプリケーションのプロパティ を選択します。</span><span class="sxs-lookup"><span data-stu-id="01c74-110">Use the wizard to select the properties of your affiliate application.</span></span>  
  
### <a name="to-create-an-individual-type-affiliate-application-using-the-command-line"></a><span data-ttu-id="01c74-111">コマンドラインを使用してアプリケーションを関連する個々 の型を作成するには</span><span class="sxs-lookup"><span data-stu-id="01c74-111">To create an individual type affiliate application using the command line</span></span>  
  
1.  <span data-ttu-id="01c74-112">**[スタート]** メニューの **[ファイル名を指定して実行]** をクリックします。</span><span class="sxs-lookup"><span data-stu-id="01c74-112">On the **Start** menu, click **Run**.</span></span>  
  
2.  <span data-ttu-id="01c74-113">**実行**ダイアログ ボックスに「 **cmd**、順にクリックします**OK**します。</span><span class="sxs-lookup"><span data-stu-id="01c74-113">In the **Run** dialog box, type **cmd**, and then click **OK**.</span></span>  
  
3.  <span data-ttu-id="01c74-114">コマンド ラインで、エンタープライズ シングル サインオンのインストール ディレクトリに移動します。</span><span class="sxs-lookup"><span data-stu-id="01c74-114">At the command line, go to the Enterprise Single Sign-On installation directory.</span></span> <span data-ttu-id="01c74-115">既定値は\<ドライブ\>: \Program Files\Common \enterprise シングル サインオンします。</span><span class="sxs-lookup"><span data-stu-id="01c74-115">The default is \<drive\>:\Program Files\Common Files\Enterprise Single Sign-On.</span></span>  
  
4.  <span data-ttu-id="01c74-116">型**ssomanage – createapps \<AffApp.xml\>** AffApp.xml は xml ファイルの名前です。</span><span class="sxs-lookup"><span data-stu-id="01c74-116">Type **ssomanage –createapps \<AffApp.xml\>**, where AffApp.xml is the name of the xml file.</span></span>  
  
    > [!NOTE]
    >  <span data-ttu-id="01c74-117">ユーザー アカウント制御 (UAC) をサポートするシステムでは、管理者特権を使用してこのツールを実行することが必要な場合があります。</span><span class="sxs-lookup"><span data-stu-id="01c74-117">On a system that supports User Account Control (UAC), you may need to run the tool with Administrative privileges.</span></span>  
  
     <span data-ttu-id="01c74-118">サンプル ファイルは、以下に示します。</span><span class="sxs-lookup"><span data-stu-id="01c74-118">A sample file is shown below:</span></span>  
  
    ```  
    <?xml version="1.0"?>  
    <SSO>  
      <application name="SSOApp_Host1">  
        <description>An Individual Type Affiliate Application for Host Initiated SSO</description>  
        <contact>someone@companyname.com</contact>  
        <appUserAccount>DomainName\AppUserGroup_HISSO</appUserAccount>  
        <appAdminAccount>DomainName\AppAdminGroup_HISSO</appAdminAccount>  
        <field ordinal="0" label="User ID" masked="no" />  
        <field ordinal="1" label="Password" masked="yes" />  
        <flags windowsInitiatedSSO="no" enableApp="yes" />  
      </application>  
    </SSO>  
  
    ```  
  
### <a name="to-create-a-host-group-type-affiliate-application-using-the-command-line"></a><span data-ttu-id="01c74-119">グループ タイプの関連アプリケーションのコマンドラインを使用してホストを作成するには</span><span class="sxs-lookup"><span data-stu-id="01c74-119">To create a host group type affiliate application using the command line</span></span>  
  
1.  <span data-ttu-id="01c74-120">**[スタート]** メニューの **[ファイル名を指定して実行]** をクリックします。</span><span class="sxs-lookup"><span data-stu-id="01c74-120">On the **Start** menu, click **Run**.</span></span>  
  
2.  <span data-ttu-id="01c74-121">**実行**ダイアログ ボックスに「 **cmd**、順にクリックします**OK**します。</span><span class="sxs-lookup"><span data-stu-id="01c74-121">In the **Run** dialog box, type **cmd**, and then click **OK**.</span></span>  
  
3.  <span data-ttu-id="01c74-122">コマンド ラインで、エンタープライズ シングル サインオンのインストール ディレクトリに移動します。</span><span class="sxs-lookup"><span data-stu-id="01c74-122">At the command line, go to the Enterprise Single Sign-On installation directory.</span></span> <span data-ttu-id="01c74-123">既定値は\<ドライブ\>: \Program Files\Common \enterprise シングル サインオンします。</span><span class="sxs-lookup"><span data-stu-id="01c74-123">The default is \<drive\>:\Program Files\Common Files\Enterprise Single Sign-On.</span></span>  
  
4.  <span data-ttu-id="01c74-124">型**ssomanage – createapps \<AffApp.xml\>** AffApp.xml は xml ファイルの名前です。</span><span class="sxs-lookup"><span data-stu-id="01c74-124">Type **ssomanage –createapps \<AffApp.xml\>**, where AffApp.xml is the name of the xml file.</span></span>  
  
    > [!NOTE]
    >  <span data-ttu-id="01c74-125">ユーザー アカウント制御 (UAC) をサポートするシステムでは、管理者特権を使用してこのツールを実行することが必要な場合があります。</span><span class="sxs-lookup"><span data-stu-id="01c74-125">On a system that supports User Account Control (UAC), you may need to run the tool with Administrative privileges.</span></span>  
  
     <span data-ttu-id="01c74-126">サンプル ファイルは、以下に示します。</span><span class="sxs-lookup"><span data-stu-id="01c74-126">A sample file is shown below:</span></span>  
  
    ```  
    <?xml version="1.0"?>  
    <SSO>  
      <application name="SSOApp_HostGroupApp1">  
        <description>A Group Type Affiliate Application for Host Initiated SSO associating multiple non-Windows user to a single Windows user account(DomainName\WindowsUserAccount1)</description>  
        <contact>someone@companyname.com</contact>  
        <windowsAccount>DomainName\WindowsUserAccount1</windowsAccount>  
        <appAdminAccount>DomainName\AppAdminGroup_HISSO</appAdminAccount>  
        <field ordinal="0" label="User ID" masked="no" />  
        <field ordinal="1" label="Password" masked="yes" />  
        <flags  enableApp="yes" />  
      </application>  
    </SSO>  
  
    ```  
  
### <a name="to-create-an-affiliate-application-supporting-both-windows-initiated-sso-and-host-initiated-sso-using-the-command-line"></a><span data-ttu-id="01c74-127">両方の Windows をサポートしているアプリケーションが SSO を開始する、関連を作成して、ホスト側開始 SSO のコマンドラインを使用</span><span class="sxs-lookup"><span data-stu-id="01c74-127">To create an affiliate application supporting both Windows initiated SSO and host initiated SSO using the command line</span></span>  
  
1.  <span data-ttu-id="01c74-128">**[スタート]** メニューの **[ファイル名を指定して実行]** をクリックします。</span><span class="sxs-lookup"><span data-stu-id="01c74-128">On the **Start** menu, click **Run**.</span></span>  
  
2.  <span data-ttu-id="01c74-129">**実行**ダイアログ ボックスに「 **cmd**、順にクリックします**OK**します。</span><span class="sxs-lookup"><span data-stu-id="01c74-129">In the **Run** dialog box, type **cmd**, and then click **OK**.</span></span>  
  
3.  <span data-ttu-id="01c74-130">コマンド ラインで、エンタープライズ シングル サインオンのインストール ディレクトリに移動します。</span><span class="sxs-lookup"><span data-stu-id="01c74-130">At the command line, go to the Enterprise Single Sign-On installation directory.</span></span> <span data-ttu-id="01c74-131">既定値は\<ドライブ\>: \Program Files\Common \enterprise シングル サインオンします。</span><span class="sxs-lookup"><span data-stu-id="01c74-131">The default is \<drive\>:\Program Files\Common Files\Enterprise Single Sign-On.</span></span>  
  
4.  <span data-ttu-id="01c74-132">型**ssomanage – createapps \<AffApp.xml\>** AffApp.xml は xml ファイルの名前です。</span><span class="sxs-lookup"><span data-stu-id="01c74-132">Type **ssomanage –createapps \<AffApp.xml\>**, where AffApp.xml is the name of the xml file.</span></span>  
  
    > [!NOTE]
    >  <span data-ttu-id="01c74-133">ユーザー アカウント制御 (UAC) をサポートするシステムでは、管理者特権を使用してこのツールを実行することが必要な場合があります。</span><span class="sxs-lookup"><span data-stu-id="01c74-133">On a system that supports User Account Control (UAC), you may need to run the tool with Administrative privileges.</span></span>  
  
     <span data-ttu-id="01c74-134">サンプル ファイルは、以下に示します。</span><span class="sxs-lookup"><span data-stu-id="01c74-134">A sample file is shown below:</span></span>  
  
    ```  
    <?xml version="1.0" ?>   
    - <SSO>  
    - <application name="SSOApp1">  
      <description>An Individual Type Affiliate Application for both Host Initiated SSO and Windows Initiated SSO</description>   
      <contact>someone@companyname.com</contact>   
      <appUserAccount>DomainName\AppUserGroup</appUserAccount>   
      <appAdminAccount>DomainName\AppAdminGroup</appAdminAccount>   
      <field ordinal="0" label="User ID" masked="no" />   
      <field ordinal="1" label="Password" masked="yes" />   
      <flags  enableApp="yes" />   
      </application>  
      </SSO>  
  
    ```  
  
## <a name="see-also"></a><span data-ttu-id="01c74-135">参照</span><span class="sxs-lookup"><span data-stu-id="01c74-135">See Also</span></span>  
 [<span data-ttu-id="01c74-136">ホスト側開始 SSO</span><span class="sxs-lookup"><span data-stu-id="01c74-136">Host Initiated SSO</span></span>](../core/host-initiated-sso.md)