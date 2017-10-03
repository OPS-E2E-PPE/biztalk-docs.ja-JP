---
title: "手順 4: アダプターにアクセスする Sharepoint アプリケーションの作成 |Microsoft ドキュメント"
ms.custom: 
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: 
ms.suite: 
ms.tgt_pltfrm: 
ms.topic: article
ms.assetid: e2d8c398-370a-4c62-961d-0eab6066ad5a
caps.latest.revision: "6"
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: 3360bbdf5ae5a6a8dde9851c544342ea6a6bc1cc
ms.sourcegitcommit: cb908c540d8f1a692d01dc8f313e16cb4b4e696d
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 09/20/2017
---
# <a name="step-4-create-a-sharepoint-application-to-access-the-adapter"></a><span data-ttu-id="7425e-102">手順 4: アダプターにアクセスする Sharepoint アプリケーションを作成します。</span><span class="sxs-lookup"><span data-stu-id="7425e-102">Step 4: Create a Sharepoint Application to Access the Adapter</span></span>
<span data-ttu-id="7425e-103">![4 のステップ 4](../../adapters-and-accelerators/adapter-oracle-ebs/media/step-4of4.gif "Step_4of4")</span><span class="sxs-lookup"><span data-stu-id="7425e-103">![Step 4 of 4](../../adapters-and-accelerators/adapter-oracle-ebs/media/step-4of4.gif "Step_4of4")</span></span>  
  
 <span data-ttu-id="7425e-104">**所要時間:** 15 分</span><span class="sxs-lookup"><span data-stu-id="7425e-104">**Time to complete:** 15 minutes</span></span>  
  
 <span data-ttu-id="7425e-105">このステップでは、ビジネス データ カタログ定義エディター ツールを使用して作成したアプリケーション定義ファイルを実行し、Microsoft Office SharePoint Server にインポートします。</span><span class="sxs-lookup"><span data-stu-id="7425e-105">In this step you take the application definition file that you created using the Business Data Catalog Definition Editor tool, and import it into Microsoft Office SharePoint Server.</span></span>  
  
## <a name="prerequisites"></a><span data-ttu-id="7425e-106">前提条件</span><span class="sxs-lookup"><span data-stu-id="7425e-106">Prerequisites</span></span>  
  
-   <span data-ttu-id="7425e-107">必要がありますがファイルを作成したアプリケーション」の説明に従って[手順 3: アプリケーション定義ファイルを作成する](../../adapters-and-accelerators/wcf-lob-adapter-sdk/step-3-create-an-application-definition-file.md)です。</span><span class="sxs-lookup"><span data-stu-id="7425e-107">You should have created an application file as described in [Step 3: Create an Application Definition File](../../adapters-and-accelerators/wcf-lob-adapter-sdk/step-3-create-an-application-definition-file.md).</span></span>  
  
-   <span data-ttu-id="7425e-108">Microsoft シングル サインオン サービスを実行する必要があります。</span><span class="sxs-lookup"><span data-stu-id="7425e-108">The Microsoft Single Sign-On service must be running.</span></span>  
  
## <a name="how-to-create-a-sharepoint-application"></a><span data-ttu-id="7425e-109">SharePoint アプリケーションを作成する方法</span><span class="sxs-lookup"><span data-stu-id="7425e-109">How to Create a SharePoint Application</span></span>  
 <span data-ttu-id="7425e-110">SharePoint アプリケーションを作成するには、次の手順が含まれます。</span><span class="sxs-lookup"><span data-stu-id="7425e-110">Creating a SharePoint application involves the following steps:</span></span>  
  
-   <span data-ttu-id="7425e-111">SharePoint でのシングル サインオン (SSO) アプリケーションを作成します。</span><span class="sxs-lookup"><span data-stu-id="7425e-111">Create a Single Sign-On (SSO) application in SharePoint.</span></span>  
  
-   <span data-ttu-id="7425e-112">共有サービス プロバイダーを作成し、アプリケーション定義ファイルをインポートします。</span><span class="sxs-lookup"><span data-stu-id="7425e-112">Create a Shared Services Provider, and import the application definition file.</span></span>  
  
-   <span data-ttu-id="7425e-113">Web パーツ ページを作成し、Web パーツを追加します。</span><span class="sxs-lookup"><span data-stu-id="7425e-113">Create a Web Part page, and add Web Parts.</span></span>  
  
 <span data-ttu-id="7425e-114">このトピックでは、次の手順を実行する方法を示します。</span><span class="sxs-lookup"><span data-stu-id="7425e-114">This topic demonstrates how to perform these steps.</span></span>  
  
## <a name="creating-an-sso-application-in-sharepoint"></a><span data-ttu-id="7425e-115">SharePoint での SSO アプリケーションの作成</span><span class="sxs-lookup"><span data-stu-id="7425e-115">Creating an SSO Application in SharePoint</span></span>  
 <span data-ttu-id="7425e-116">SharePoint アプリケーションからユーザーの資格情報をエコー アダプターに渡すには、ユーザー アカウントまたはグループにマップされている SSO アプリケーションを設定する必要があります。</span><span class="sxs-lookup"><span data-stu-id="7425e-116">To pass user credentials to the Echo adapter from a SharePoint application, you must set up an SSO application that maps to a user account or group.</span></span>  
  
#### <a name="manage-server-settings-for-single-sign-on"></a><span data-ttu-id="7425e-117">シングル サインオン用のサーバー設定を管理します。</span><span class="sxs-lookup"><span data-stu-id="7425e-117">Manage server settings for Single Sign-On</span></span>  
  
1.  <span data-ttu-id="7425e-118">SharePoint 3.0 サーバーの全体管理を開始します。</span><span class="sxs-lookup"><span data-stu-id="7425e-118">Start SharePoint 3.0 Central Administration.</span></span> <span data-ttu-id="7425e-119">**開始** メニューのをポイント**すべてのプログラム**、 をポイント**Microsoft Office Server**、クリックして**SharePoint 3.0 サーバーの全体管理**.</span><span class="sxs-lookup"><span data-stu-id="7425e-119">On the **Start** menu, point to **All Programs**, point to **Microsoft Office Server**, and then click **SharePoint 3.0 Central Administration**.</span></span>  
  
2.  <span data-ttu-id="7425e-120">上部のナビゲーション バーで、をクリックして**Operations**です。</span><span class="sxs-lookup"><span data-stu-id="7425e-120">On the top navigation bar, click **Operations**.</span></span>  
  
3.  <span data-ttu-id="7425e-121">[操作] ページで、**セキュリティの構成**セクションで、をクリックして**でのシングル サインオンの設定を管理**です。</span><span class="sxs-lookup"><span data-stu-id="7425e-121">On the Operations page, in the **Security Configuration** section, click **Manage settings for single sign-on**.</span></span>  
  
4.  <span data-ttu-id="7425e-122">シングル サインオン] ページの設定の管理で、**サーバー設定**セクションで、[**サーバー設定の管理**です。</span><span class="sxs-lookup"><span data-stu-id="7425e-122">On the Manage Settings for Single Sign-On page, in the **Server Settings** section, click **Manage Server Settings**.</span></span>  
  
5.  <span data-ttu-id="7425e-123">このページの情報が、シングル サインオンのインストールの正しいことを確認します。</span><span class="sxs-lookup"><span data-stu-id="7425e-123">Ensure that the information on this page is correct for your Single Sign-On installation.</span></span> <span data-ttu-id="7425e-124">これらの操作の詳細についてを参照してください「でのシングル サインオン (Office SharePoint Server) を構成する」で[http://go.microsoft.com/fwlink/?LinkId=105291](http://go.microsoft.com/fwlink/?LinkId=105291)です。</span><span class="sxs-lookup"><span data-stu-id="7425e-124">For more information about these operations, see “Configure single sign-on (Office SharePoint Server)” at [http://go.microsoft.com/fwlink/?LinkId=105291](http://go.microsoft.com/fwlink/?LinkId=105291).</span></span>  
  
#### <a name="manage-settings-for-enterprise-application-definitions"></a><span data-ttu-id="7425e-125">エンタープライズ アプリケーション定義の設定を管理します。</span><span class="sxs-lookup"><span data-stu-id="7425e-125">Manage settings for enterprise application definitions</span></span>  
  
1.  <span data-ttu-id="7425e-126">SharePoint サーバーの全体管理で、上部のナビゲーション バーで、をクリックして**Operations**です。</span><span class="sxs-lookup"><span data-stu-id="7425e-126">In SharePoint Central Administration, on the top navigation bar, click **Operations**.</span></span>  
  
2.  <span data-ttu-id="7425e-127">[操作] ページで、**セキュリティの構成**セクションで、をクリックして**でのシングル サインオンの設定の管理**です。</span><span class="sxs-lookup"><span data-stu-id="7425e-127">On the Operations page, in the **Security Configuration** section, click **Manage Settings for single sign-on**.</span></span>  
  
3.  <span data-ttu-id="7425e-128">シングル サインオン] ページの設定の管理で、**エンタープライズ アプリケーション定義の設定**セクションで、[**企業アプリケーション定義の設定の管理**です。</span><span class="sxs-lookup"><span data-stu-id="7425e-128">On the Manage Settings for Single Sign-On page, in the **Enterprise Application Definition Settings** section, click **Manage Settings for enterprise application definitions**.</span></span>  
  
4.  <span data-ttu-id="7425e-129">エンタープライズ アプリケーション定義の管理 ページで、**新しい項目の**します。</span><span class="sxs-lookup"><span data-stu-id="7425e-129">On the Manage Enterprise Application Definitions page, click **New Item**.</span></span>  
  
5.  <span data-ttu-id="7425e-130">作成エンタープライズ アプリケーション定義 ページ、設定、**表示名**フィールドを**EchoSSO**、し、設定、**アプリケーション名**フィールドを**EchoSSO**です。</span><span class="sxs-lookup"><span data-stu-id="7425e-130">On the Create Enterprise Application Definitions Page, set the **Display name** field to **EchoSSO**, and then set the **Application name** field to **EchoSSO**.</span></span> <span data-ttu-id="7425e-131">この値の一致で指定した SecondarySsoApplicationId[手順 3: アプリケーション定義ファイルを作成する](../../adapters-and-accelerators/wcf-lob-adapter-sdk/step-3-create-an-application-definition-file.md)です。</span><span class="sxs-lookup"><span data-stu-id="7425e-131">This value should match the SecondarySsoApplicationId you specified in [Step 3: Create an Application Definition File](../../adapters-and-accelerators/wcf-lob-adapter-sdk/step-3-create-an-application-definition-file.md).</span></span>  
  
6.  <span data-ttu-id="7425e-132">**連絡先の電子メール アドレス**フィールドで、お客様の電子メール アドレスを入力し、をクリックして**OK**です。</span><span class="sxs-lookup"><span data-stu-id="7425e-132">In the **Contact e-mail address** field, enter your e-mail address, and then click **OK**.</span></span>  
  
#### <a name="manage-account-information-for-enterprise-application-definitions"></a><span data-ttu-id="7425e-133">エンタープライズ アプリケーション定義のアカウント情報を管理します。</span><span class="sxs-lookup"><span data-stu-id="7425e-133">Manage account information for enterprise application definitions</span></span>  
  
1.  <span data-ttu-id="7425e-134">SharePoint サーバーの全体管理で、上部のナビゲーション バーで、をクリックして**Operations**です。</span><span class="sxs-lookup"><span data-stu-id="7425e-134">In SharePoint Central Administration, on the top navigation bar, click **Operations**.</span></span>  
  
2.  <span data-ttu-id="7425e-135">操作 ページで、**セキュリティ構成セクション**、 をクリックして**でのシングル サインオンの設定を管理**です。</span><span class="sxs-lookup"><span data-stu-id="7425e-135">On the Operations page, in the **Security Configuration Section**, click **Manage settings for single sign-on**.</span></span>  
  
3.  <span data-ttu-id="7425e-136">シングル サインオン] ページの設定の管理で、**エンタープライズ アプリケーション定義の設定**セクションで、[**管理アカウントについて、エンタープライズ アプリケーション定義**です。</span><span class="sxs-lookup"><span data-stu-id="7425e-136">On the Manage Settings for Single Sign-On page, in the **Enterprise Application Definition Settings** section, click **Manage account information for enterprise application definitions**.</span></span>  
  
4.  <span data-ttu-id="7425e-137">[エンタープライズ アプリケーション定義の管理アカウント情報、選択**EchoSSO**から、**エンタープライズ アプリケーション定義**] ボックスの一覧です。</span><span class="sxs-lookup"><span data-stu-id="7425e-137">On the Manage Account Information for an Enterprise Application Definition, select **EchoSSO** from the **Enterprise application definition** list.</span></span>  
  
5.  <span data-ttu-id="7425e-138">**グループ アカウント名**フィールドに、このアプリケーションの定義をセキュリティで保護するために使用する Windows グループを入力します。</span><span class="sxs-lookup"><span data-stu-id="7425e-138">In the **Group account name** field, type the Windows group that will be used to secure this application definition.</span></span> <span data-ttu-id="7425e-139">たとえば、 **DOMAIN\Domain ユーザー**です。</span><span class="sxs-lookup"><span data-stu-id="7425e-139">For example, **DOMAIN\Domain Users**.</span></span>  
  
6.  <span data-ttu-id="7425e-140">**[設定]**をクリックします。</span><span class="sxs-lookup"><span data-stu-id="7425e-140">Click **Set**.</span></span>  
  
7.  <span data-ttu-id="7425e-141">EchoSSO アカウント情報の提供 ページで、 **Username**フィールド型**testuser**、し、**パスワード**フィールド型**testpassword**.</span><span class="sxs-lookup"><span data-stu-id="7425e-141">On the Provide EchoSSO Account Information page, in the **Username** field type **testuser**, and then in the **Password** field type **testpassword**.</span></span>  
  
8.  <span data-ttu-id="7425e-142">をクリックして**OK**、順にクリック**完了**です。</span><span class="sxs-lookup"><span data-stu-id="7425e-142">Click **OK**, and then click **Done**.</span></span>  
  
## <a name="creating-a-shared-services-provider-and-importing-the-application-definition-file"></a><span data-ttu-id="7425e-143">共有サービス プロバイダーを作成し、アプリケーション定義ファイルをインポートします。</span><span class="sxs-lookup"><span data-stu-id="7425e-143">Creating a Shared Services Provider and importing the application definition file</span></span>  
 <span data-ttu-id="7425e-144">共有サービス プロバイダー (SSP) は、共有サービスとその関連リソースの論理グループです。</span><span class="sxs-lookup"><span data-stu-id="7425e-144">A Shared Services Provider (SSP) is a logical grouping of shared services and their supporting resources.</span></span> <span data-ttu-id="7425e-145">SSP を作成するには、SharePoint サーバーの全体管理コンソールを使用します。</span><span class="sxs-lookup"><span data-stu-id="7425e-145">You can create an SSP by using the SharePoint Central Administration Console.</span></span> <span data-ttu-id="7425e-146">この例は、SSP. で動作します。</span><span class="sxs-lookup"><span data-stu-id="7425e-146">This example will work in any SSP.</span></span> <span data-ttu-id="7425e-147">SSP の作成の詳細については、次を参照してください。"章の概要: を作成および構成共有サービスのプロバイダー"で[http://go.microsoft.com/fwlink/?LinkId=105119](http://go.microsoft.com/fwlink/?LinkId=105119)です。</span><span class="sxs-lookup"><span data-stu-id="7425e-147">For more information about creating an SSP, see “Chapter overview: Create and Configure Shared Services Providers” at [http://go.microsoft.com/fwlink/?LinkId=105119](http://go.microsoft.com/fwlink/?LinkId=105119).</span></span>  
  
### <a name="to-import-the-application-definition-file"></a><span data-ttu-id="7425e-148">アプリケーション定義ファイルをインポートするには</span><span class="sxs-lookup"><span data-stu-id="7425e-148">To import the application definition file</span></span>  
  
1.  <span data-ttu-id="7425e-149">SharePoint 3.0 サーバーの全体管理を開始します。</span><span class="sxs-lookup"><span data-stu-id="7425e-149">Start SharePoint 3.0 Central Administration.</span></span> <span data-ttu-id="7425e-150">**開始** メニューのをポイント**すべてのプログラム**、 をポイント**Microsoft Office Server**、クリックして**SharePoint 3.0 サーバーの全体管理**.</span><span class="sxs-lookup"><span data-stu-id="7425e-150">On the **Start** menu, point to **All Programs**, point to **Microsoft Office Server**, and then click **SharePoint 3.0 Central Administration**.</span></span>  
  
2.  <span data-ttu-id="7425e-151">左側のナビゲーション ウィンドウで、アプリケーション定義をインポートする SSP の名前をクリックします。</span><span class="sxs-lookup"><span data-stu-id="7425e-151">In the left navigation pane, click the name of the SSP to which you want to import the application definition.</span></span>  
  
3.  <span data-ttu-id="7425e-152">**ビジネス データ カタログ**セクションで、**アプリケーション定義のインポート**です。</span><span class="sxs-lookup"><span data-stu-id="7425e-152">In the **Business Data Catalog** section, click **Import application definition**.</span></span>  
  
4.  <span data-ttu-id="7425e-153">アプリケーション定義のインポート ページで、をクリックして**参照**、し EchoWS.xml ファイルを選択します。</span><span class="sxs-lookup"><span data-stu-id="7425e-153">On the Import Application Definition page, click **Browse**, and then select the EchoWS.xml file.</span></span>  
  
5.  <span data-ttu-id="7425e-154">をクリックして**インポート**、順にクリック**OK**です。</span><span class="sxs-lookup"><span data-stu-id="7425e-154">Click **Import**, and then click **OK**.</span></span>  
  
## <a name="creating-web-parts"></a><span data-ttu-id="7425e-155">Web パーツを作成します。</span><span class="sxs-lookup"><span data-stu-id="7425e-155">Creating Web Parts</span></span>  
 <span data-ttu-id="7425e-156">ビジネス データ カタログ定義エディターで作成したメソッドのインスタンスを使用するように SharePoint サイトで Web パーツを作成する必要があります。</span><span class="sxs-lookup"><span data-stu-id="7425e-156">You must now create Web Parts in your SharePoint site to use the method instance created in the Business Data Catalog Definition Editor.</span></span> <span data-ttu-id="7425e-157">Web パーツは、任意の種類の分析、コラボレーションなど、Web ベースの情報を含むおよびデータベース情報が使用できる再利用可能なコンポーネントです。</span><span class="sxs-lookup"><span data-stu-id="7425e-157">Web Parts are reusable components that can contain any kind of Web-based information, including analytical, collaborative, and database information.</span></span>  
  
#### <a name="to-create-a-web-part-page"></a><span data-ttu-id="7425e-158">Web パーツ ページを作成するには</span><span class="sxs-lookup"><span data-stu-id="7425e-158">To create a Web Part page</span></span>  
  
1.  <span data-ttu-id="7425e-159">SharePoint 3.0 サーバーの全体管理を開始します。</span><span class="sxs-lookup"><span data-stu-id="7425e-159">Start SharePoint 3.0 Central Administration.</span></span> <span data-ttu-id="7425e-160">**開始** メニューのをポイント**すべてのプログラム**、 をポイント**Microsoft Office Server**、クリックして**SharePoint 3.0 サーバーの全体管理**.</span><span class="sxs-lookup"><span data-stu-id="7425e-160">On the **Start** menu, point to **All Programs**, point to **Microsoft Office Server**, and then click **SharePoint 3.0 Central Administration**.</span></span>  
  
2.  <span data-ttu-id="7425e-161">左側のナビゲーション ウィンドウで、アプリケーション定義ファイルをインポートした SSP の名前をクリックします。</span><span class="sxs-lookup"><span data-stu-id="7425e-161">In the left navigation pane, click the name of the SSP in which you imported the application definition file.</span></span>  
  
3.  <span data-ttu-id="7425e-162">共有サービスの管理 ページの右上隅で、をクリックして**サイトの操作**、クリックして**作成**です。</span><span class="sxs-lookup"><span data-stu-id="7425e-162">On the Shared Services Administration page, in the upper-right corner, click **Site Actions**, and then click **Create**.</span></span>  
  
     <span data-ttu-id="7425e-163">![サイトの操作を作成する](../../adapters-and-accelerators/wcf-lob-adapter-sdk/media/13f43659-ef61-48db-ac19-2d553367ec7e.gif "13f43659-ef61-48db-ac19-2d553367ec7e")</span><span class="sxs-lookup"><span data-stu-id="7425e-163">![Create Site Actions](../../adapters-and-accelerators/wcf-lob-adapter-sdk/media/13f43659-ef61-48db-ac19-2d553367ec7e.gif "13f43659-ef61-48db-ac19-2d553367ec7e")</span></span>  
  
4.  <span data-ttu-id="7425e-164">**作成** ページの 、 **Web ページ**セクションで、 **Web パーツ ページ**です。</span><span class="sxs-lookup"><span data-stu-id="7425e-164">On the **Create** page, in the **Web Pages** section, click **Web Part Page**.</span></span>  
  
5.  <span data-ttu-id="7425e-165">[新しい Web パーツ] ページで、**名前**フィールドに「 **EchoPart**、し、[**ページ全体を垂直方向**から、 **レイアウトテンプレートを選択した**] ボックスの一覧です。</span><span class="sxs-lookup"><span data-stu-id="7425e-165">On the New Web Part page, in the **Name** field, type **EchoPart**, and then select **Full Page, Vertical** from the **Chose a Layout Template** list.</span></span>  
  
6.  <span data-ttu-id="7425e-166">**[作成]**をクリックします。</span><span class="sxs-lookup"><span data-stu-id="7425e-166">Click **Create**.</span></span>  
  
#### <a name="to-add-a-business-data-web-part"></a><span data-ttu-id="7425e-167">ビジネス データ Web パーツを追加するには</span><span class="sxs-lookup"><span data-stu-id="7425e-167">To add a Business Data Web Part</span></span>  
  
1.  <span data-ttu-id="7425e-168">**[Web パーツの追加]**をクリックします。</span><span class="sxs-lookup"><span data-stu-id="7425e-168">Click **Add a Web Part**.</span></span>  
  
2.  <span data-ttu-id="7425e-169">**Web パーツの追加**ダイアログ ボックスで、**ビジネス データ一覧**、クリックして**追加**です。</span><span class="sxs-lookup"><span data-stu-id="7425e-169">In the **Add Web Parts** dialog box, select **Business Data List**, and then click **Add**.</span></span>  
  
     <span data-ttu-id="7425e-170">![ビジネス データ一覧](../../adapters-and-accelerators/wcf-lob-adapter-sdk/media/cd9e6bc8-c37e-49d2-9eaa-77246bb593df.gif "cd9e6bc8-c37e-49d2-9eaa-77246bb593df")</span><span class="sxs-lookup"><span data-stu-id="7425e-170">![Business Data List](../../adapters-and-accelerators/wcf-lob-adapter-sdk/media/cd9e6bc8-c37e-49d2-9eaa-77246bb593df.gif "cd9e6bc8-c37e-49d2-9eaa-77246bb593df")</span></span>  
  
3.  <span data-ttu-id="7425e-171">をクリックして**ツール ウィンドウを開いて**です。</span><span class="sxs-lookup"><span data-stu-id="7425e-171">Click **Open the tool pane**.</span></span>  
  
4.  <span data-ttu-id="7425e-172">ビジネス データ一覧のツール ウィンドウは、右側のウィンドウで開きます。</span><span class="sxs-lookup"><span data-stu-id="7425e-172">The Business Data List tool pane opens in the right pane.</span></span> <span data-ttu-id="7425e-173">**ビジネス データ一覧** セクションの**型**フィールドで、をクリックして、**参照**ボタンをクリックします。</span><span class="sxs-lookup"><span data-stu-id="7425e-173">In the **Business Data List** section, for the **Type** field, click the **Browse** button.</span></span>  
  
     <span data-ttu-id="7425e-174">![種類を選択して](../../adapters-and-accelerators/wcf-lob-adapter-sdk/media/a054ed0e-0880-4154-9050-a00da356a4f6.gif "a054ed0e-0880-4154-9050-a00da356a4f6")</span><span class="sxs-lookup"><span data-stu-id="7425e-174">![Select the Type](../../adapters-and-accelerators/wcf-lob-adapter-sdk/media/a054ed0e-0880-4154-9050-a00da356a4f6.gif "a054ed0e-0880-4154-9050-a00da356a4f6")</span></span>  
  
5.  <span data-ttu-id="7425e-175">**ビジネス データの種類の選択**ダイアログ ボックスで、 **EchoWSLob_Instance**クリックしてアプリケーションでは、 **OK**です。</span><span class="sxs-lookup"><span data-stu-id="7425e-175">In the **Business Data Type Picker** dialog box, select the **EchoWSLob_Instance** application, and then click **OK**.</span></span>  
  
6.  <span data-ttu-id="7425e-176">ビジネス データ一覧のツール ウィンドウで、をクリックして**OK**です。</span><span class="sxs-lookup"><span data-stu-id="7425e-176">On the Business Data List tool pane, click **OK**.</span></span>  
  
7.  <span data-ttu-id="7425e-177">EchoGreetings メソッドに渡すグリーティング値を入力できるフィールドが表示されます。</span><span class="sxs-lookup"><span data-stu-id="7425e-177">You are presented with a field that allows you to enter a greeting value to pass to the EchoGreetings method.</span></span> <span data-ttu-id="7425e-178">応答メッセージ フィールドにデータを入力し、クリックして**データの取得**です。</span><span class="sxs-lookup"><span data-stu-id="7425e-178">Enter data in the greeting field and click **Retrieve Data**.</span></span> <span data-ttu-id="7425e-179">これにより、IIS でホストされている Echo アダプターの EchoGreetings メソッドを呼び出し、応答を返します。</span><span class="sxs-lookup"><span data-stu-id="7425e-179">This invokes the EchoGreetings method of the Echo adapter hosted in IIS and returns a response.</span></span>  
  
     <span data-ttu-id="7425e-180">![EchoGreetings 一覧](../../adapters-and-accelerators/wcf-lob-adapter-sdk/media/f5a22fcd-2ae6-4384-9879-f0abd0255325.gif "f5a22fcd-2ae6-4384-9879-f0abd0255325")</span><span class="sxs-lookup"><span data-stu-id="7425e-180">![EchoGreetings List](../../adapters-and-accelerators/wcf-lob-adapter-sdk/media/f5a22fcd-2ae6-4384-9879-f0abd0255325.gif "f5a22fcd-2ae6-4384-9879-f0abd0255325")</span></span>  
  
    > [!NOTE]
    >  <span data-ttu-id="7425e-181">[名前] 列では、ユーザー情報は含まれませんが、BDC をのみ表示されます。名前です。</span><span class="sxs-lookup"><span data-stu-id="7425e-181">The name column does not contain the user information, but only displays BDC.Name.</span></span> <span data-ttu-id="7425e-182">これは、BDC が単純なレコード構造のみを必要とし、[名前] フィールドで表される複雑な構造は表示されません。</span><span class="sxs-lookup"><span data-stu-id="7425e-182">This occurs because the BDC expects only a simple record structure, and does not display the complex structure represented by the name field.</span></span>  
  
8.  <span data-ttu-id="7425e-183">をクリックして**編集モードの終了**ページの上にあるからです。</span><span class="sxs-lookup"><span data-stu-id="7425e-183">Click **Exit Edit Mode** from the upper corner of the page.</span></span>  
  
## <a name="what-did-i-just-do"></a><span data-ttu-id="7425e-184">でしただけは何ですか。</span><span class="sxs-lookup"><span data-stu-id="7425e-184">What did I just do?</span></span>  
 <span data-ttu-id="7425e-185">アプリケーション定義をインポートし、この定義を使用して、操作を呼び出し、EchoGreetings エコー アダプターの Web パーツを作成する、SharePoint 3.0 サーバーの全体管理を使用しました。</span><span class="sxs-lookup"><span data-stu-id="7425e-185">You have used the SharePoint 3.0 Central Administration to import an application definition, and create Web Parts that use this definition to invoke the EchoGreetings operation of the Echo adapter.</span></span>  
  
## <a name="next-steps"></a><span data-ttu-id="7425e-186">次の手順</span><span class="sxs-lookup"><span data-stu-id="7425e-186">Next Steps</span></span>  
 <span data-ttu-id="7425e-187">このチュートリアルが完了しました。</span><span class="sxs-lookup"><span data-stu-id="7425e-187">This tutorial is complete.</span></span> <span data-ttu-id="7425e-188">詳細については、ビジネス データ カタログを使用して参照してください「ビジネス データ カタログ」 [http://go.microsoft.com/fwlink/?LinkId=119921](http://go.microsoft.com/fwlink/?LinkId=119921)です。</span><span class="sxs-lookup"><span data-stu-id="7425e-188">For more information using the Business Data Catalog, see “Business Data Catalog” at [http://go.microsoft.com/fwlink/?LinkId=119921](http://go.microsoft.com/fwlink/?LinkId=119921).</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="7425e-189">参照</span><span class="sxs-lookup"><span data-stu-id="7425e-189">See Also</span></span>  
 [<span data-ttu-id="7425e-190">チュートリアル 3: IIS でエコー アダプターをホストします。</span><span class="sxs-lookup"><span data-stu-id="7425e-190">Tutorial 3: Hosting the Echo Adapter in IIS</span></span>](../../adapters-and-accelerators/wcf-lob-adapter-sdk/tutorial-3-hosting-the-echo-adapter-in-iis.md)