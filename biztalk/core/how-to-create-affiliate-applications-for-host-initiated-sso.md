---
title: "側開始 SSO 関連アプリケーション ホストを作成する方法 |Microsoft ドキュメント"
ms.custom: 
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: 
ms.suite: 
ms.tgt_pltfrm: 
ms.topic: article
helpviewer_keywords:
- applications [SSO], host initiated SSO
- creating, applications [SSO]
- host initiated SSO, creating affiliate applications
ms.assetid: 06202d21-055a-46bc-acff-da461f5673f1
caps.latest.revision: "10"
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: 23525d3b2f72d59e2b0f44257c707f22e6bc2bab
ms.sourcegitcommit: cb908c540d8f1a692d01dc8f313e16cb4b4e696d
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 09/20/2017
---
# <a name="how-to-create-affiliate-applications-for-host-initiated-sso"></a><span data-ttu-id="5f11e-102">ホスト側開始 SSO 関連アプリケーションを作成する方法</span><span class="sxs-lookup"><span data-stu-id="5f11e-102">How to Create Affiliate Applications for Host Initiated SSO</span></span>
<span data-ttu-id="5f11e-103">定義できるアプリケーションには、次の 2 種類があります。</span><span class="sxs-lookup"><span data-stu-id="5f11e-103">You can define two types of applications:</span></span>  
  
-   <span data-ttu-id="5f11e-104">**各**Windows および Windows 以外のユーザー間で 1 対 1 リレーションシップが存在します。</span><span class="sxs-lookup"><span data-stu-id="5f11e-104">**Individual** There is a 1 to 1 relationship between Windows users and non-Windows users.</span></span>  
  
-   <span data-ttu-id="5f11e-105">**ホスト グループ**複数の Windows ではないユーザーは、同じ Windows アカウントにマップすることができます。</span><span class="sxs-lookup"><span data-stu-id="5f11e-105">**Host Group** Multiple non-Windows users can be mapped to the same Windows account.</span></span>  
  
### <a name="to-create-an-affiliate-application-using-the-mmc-snap-in"></a><span data-ttu-id="5f11e-106">MMC スナップインを使用して関連アプリケーションを作成するには</span><span class="sxs-lookup"><span data-stu-id="5f11e-106">To create an affiliate application using the MMC Snap-In</span></span>  
  
1.  <span data-ttu-id="5f11e-107">**開始** メニューのをクリックして**すべてのプログラム**、 をクリックして**Microsoft エンタープライズ シングル サインオン**、クリックして**SSO 管理**です。</span><span class="sxs-lookup"><span data-stu-id="5f11e-107">On the **Start** menu, click **All Programs**, click **Microsoft Enterprise Single Sign-On**, and then click **SSO Administration**.</span></span>  
  
2.  <span data-ttu-id="5f11e-108">ENTSSO MMC スナップインの [スコープ] ウィンドウで、展開、**エンタープライズ シングル サインオン**ノード。</span><span class="sxs-lookup"><span data-stu-id="5f11e-108">In the scope pane of the ENTSSO MMC Snap-In, expand the **Enterprise Single Sign-On** node.</span></span>  
  
3.  <span data-ttu-id="5f11e-109">右クリック**関連アプリケーション**、クリックして**アプリケーションの作成**を開くには、**エンタープライズ シングル サインオン アプリケーション ウィザード**です。</span><span class="sxs-lookup"><span data-stu-id="5f11e-109">Right-click **Affiliate Applications**, and then click **Create Application** to open the **Enterprise Single Sign-On Application Wizard**.</span></span>  
  
4.  <span data-ttu-id="5f11e-110">このウィザードを使用して、関連アプリケーションのプロパティを選択します。</span><span class="sxs-lookup"><span data-stu-id="5f11e-110">Use the wizard to select the properties of your affiliate application.</span></span>  
  
### <a name="to-create-an-individual-type-affiliate-application-using-the-command-line"></a><span data-ttu-id="5f11e-111">コマンド ラインを使用して単独タイプの関連アプリケーションを作成するには</span><span class="sxs-lookup"><span data-stu-id="5f11e-111">To create an individual type affiliate application using the command line</span></span>  
  
1.  <span data-ttu-id="5f11e-112">**[スタート]** メニューの **[ファイル名を指定して実行]**をクリックします。</span><span class="sxs-lookup"><span data-stu-id="5f11e-112">On the **Start** menu, click **Run**.</span></span>  
  
2.  <span data-ttu-id="5f11e-113">**実行** ダイアログ ボックスで、「 **cmd**、順にクリック**OK**です。</span><span class="sxs-lookup"><span data-stu-id="5f11e-113">In the **Run** dialog box, type **cmd**, and then click **OK**.</span></span>  
  
3.  <span data-ttu-id="5f11e-114">コマンド ラインで、エンタープライズ シングル サインオンのインストール ディレクトリに移動します。</span><span class="sxs-lookup"><span data-stu-id="5f11e-114">At the command line, go to the Enterprise Single Sign-On installation directory.</span></span> <span data-ttu-id="5f11e-115">既定値は\<ドライブ >: \program files \common files \enterprise シングル サインオンします。</span><span class="sxs-lookup"><span data-stu-id="5f11e-115">The default is \<drive>:\Program Files\Common Files\Enterprise Single Sign-On.</span></span>  
  
4.  <span data-ttu-id="5f11e-116">型**ssomanage – createapps」と入力\<AffApp.xml >**AffApp.xml は xml ファイルの名前を指定します。</span><span class="sxs-lookup"><span data-stu-id="5f11e-116">Type **ssomanage –createapps \<AffApp.xml>**, where AffApp.xml is the name of the xml file.</span></span>  
  
    > [!NOTE]
    >  <span data-ttu-id="5f11e-117">ユーザー アカウント制御 (UAC) をサポートするシステムでは、管理者特権を使用してこのツールを実行することが必要な場合があります。</span><span class="sxs-lookup"><span data-stu-id="5f11e-117">On a system that supports User Account Control (UAC), you may need to run the tool with Administrative privileges.</span></span>  
  
     <span data-ttu-id="5f11e-118">サンプル ファイルを次に示します。</span><span class="sxs-lookup"><span data-stu-id="5f11e-118">A sample file is shown below:</span></span>  
  
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
  
### <a name="to-create-a-host-group-type-affiliate-application-using-the-command-line"></a><span data-ttu-id="5f11e-119">コマンド ラインを使用してホスト グループ タイプの関連アプリケーションを作成するには</span><span class="sxs-lookup"><span data-stu-id="5f11e-119">To create a host group type affiliate application using the command line</span></span>  
  
1.  <span data-ttu-id="5f11e-120">**[スタート]** メニューの **[ファイル名を指定して実行]**をクリックします。</span><span class="sxs-lookup"><span data-stu-id="5f11e-120">On the **Start** menu, click **Run**.</span></span>  
  
2.  <span data-ttu-id="5f11e-121">**実行** ダイアログ ボックスで、「 **cmd**、順にクリック**OK**です。</span><span class="sxs-lookup"><span data-stu-id="5f11e-121">In the **Run** dialog box, type **cmd**, and then click **OK**.</span></span>  
  
3.  <span data-ttu-id="5f11e-122">コマンド ラインで、エンタープライズ シングル サインオンのインストール ディレクトリに移動します。</span><span class="sxs-lookup"><span data-stu-id="5f11e-122">At the command line, go to the Enterprise Single Sign-On installation directory.</span></span> <span data-ttu-id="5f11e-123">既定値は\<ドライブ >: \program files \common files \enterprise シングル サインオンします。</span><span class="sxs-lookup"><span data-stu-id="5f11e-123">The default is \<drive>:\Program Files\Common Files\Enterprise Single Sign-On.</span></span>  
  
4.  <span data-ttu-id="5f11e-124">型**ssomanage – createapps」と入力\<AffApp.xml >**AffApp.xml は xml ファイルの名前を指定します。</span><span class="sxs-lookup"><span data-stu-id="5f11e-124">Type **ssomanage –createapps \<AffApp.xml>**, where AffApp.xml is the name of the xml file.</span></span>  
  
    > [!NOTE]
    >  <span data-ttu-id="5f11e-125">ユーザー アカウント制御 (UAC) をサポートするシステムでは、管理者特権を使用してこのツールを実行することが必要な場合があります。</span><span class="sxs-lookup"><span data-stu-id="5f11e-125">On a system that supports User Account Control (UAC), you may need to run the tool with Administrative privileges.</span></span>  
  
     <span data-ttu-id="5f11e-126">サンプル ファイルを次に示します。</span><span class="sxs-lookup"><span data-stu-id="5f11e-126">A sample file is shown below:</span></span>  
  
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
  
### <a name="to-create-an-affiliate-application-supporting-both-windows-initiated-sso-and-host-initiated-sso-using-the-command-line"></a><span data-ttu-id="5f11e-127">コマンド ラインを使用して Windows 側開始 SSO とホスト側開始 SSO の両方をサポートする関連アプリケーションを作成するには</span><span class="sxs-lookup"><span data-stu-id="5f11e-127">To create an affiliate application supporting both Windows initiated SSO and host initiated SSO using the command line</span></span>  
  
1.  <span data-ttu-id="5f11e-128">**[スタート]** メニューの **[ファイル名を指定して実行]**をクリックします。</span><span class="sxs-lookup"><span data-stu-id="5f11e-128">On the **Start** menu, click **Run**.</span></span>  
  
2.  <span data-ttu-id="5f11e-129">**実行** ダイアログ ボックスで、「 **cmd**、順にクリック**OK**です。</span><span class="sxs-lookup"><span data-stu-id="5f11e-129">In the **Run** dialog box, type **cmd**, and then click **OK**.</span></span>  
  
3.  <span data-ttu-id="5f11e-130">コマンド ラインで、エンタープライズ シングル サインオンのインストール ディレクトリに移動します。</span><span class="sxs-lookup"><span data-stu-id="5f11e-130">At the command line, go to the Enterprise Single Sign-On installation directory.</span></span> <span data-ttu-id="5f11e-131">既定値は\<ドライブ >: \program files \common files \enterprise シングル サインオンします。</span><span class="sxs-lookup"><span data-stu-id="5f11e-131">The default is \<drive>:\Program Files\Common Files\Enterprise Single Sign-On.</span></span>  
  
4.  <span data-ttu-id="5f11e-132">型**ssomanage – createapps」と入力\<AffApp.xml >**AffApp.xml は xml ファイルの名前を指定します。</span><span class="sxs-lookup"><span data-stu-id="5f11e-132">Type **ssomanage –createapps \<AffApp.xml>**, where AffApp.xml is the name of the xml file.</span></span>  
  
    > [!NOTE]
    >  <span data-ttu-id="5f11e-133">ユーザー アカウント制御 (UAC) をサポートするシステムでは、管理者特権を使用してこのツールを実行することが必要な場合があります。</span><span class="sxs-lookup"><span data-stu-id="5f11e-133">On a system that supports User Account Control (UAC), you may need to run the tool with Administrative privileges.</span></span>  
  
     <span data-ttu-id="5f11e-134">サンプル ファイルを次に示します。</span><span class="sxs-lookup"><span data-stu-id="5f11e-134">A sample file is shown below:</span></span>  
  
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
  
## <a name="see-also"></a><span data-ttu-id="5f11e-135">参照</span><span class="sxs-lookup"><span data-stu-id="5f11e-135">See Also</span></span>  
 [<span data-ttu-id="5f11e-136">ホスト側開始 SSO</span><span class="sxs-lookup"><span data-stu-id="5f11e-136">Host Initiated SSO</span></span>](../core/host-initiated-sso.md)