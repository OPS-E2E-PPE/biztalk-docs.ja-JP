---
title: 手順 4:アダプターにアクセスする Sharepoint アプリケーションの作成 |Microsoft Docs
ms.custom: ''
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: ''
ms.suite: ''
ms.tgt_pltfrm: ''
ms.topic: article
ms.assetid: e2d8c398-370a-4c62-961d-0eab6066ad5a
caps.latest.revision: 6
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: 37ee9f9c458fc16d7934d64ddb736a5f0c7f30a2
ms.sourcegitcommit: 381e83d43796a345488d54b3f7413e11d56ad7be
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 05/07/2019
ms.locfileid: "65363163"
---
# <a name="step-4-create-a-sharepoint-application-to-access-the-adapter"></a><span data-ttu-id="71f00-102">手順 4:アダプターにアクセスする Sharepoint アプリケーションを作成します。</span><span class="sxs-lookup"><span data-stu-id="71f00-102">Step 4: Create a Sharepoint Application to Access the Adapter</span></span>
<span data-ttu-id="71f00-103">![手順 4 の 4](../../adapters-and-accelerators/adapter-oracle-ebs/media/step-4of4.gif "Step_4of4")</span><span class="sxs-lookup"><span data-stu-id="71f00-103">![Step 4 of 4](../../adapters-and-accelerators/adapter-oracle-ebs/media/step-4of4.gif "Step_4of4")</span></span>  
  
 <span data-ttu-id="71f00-104">**所要時間:** 15 分</span><span class="sxs-lookup"><span data-stu-id="71f00-104">**Time to complete:** 15 minutes</span></span>  
  
 <span data-ttu-id="71f00-105">この手順では、ビジネス データ カタログ定義エディター ツールを使用して作成したアプリケーション定義ファイルを取得し、Microsoft Office SharePoint Server にインポートします。</span><span class="sxs-lookup"><span data-stu-id="71f00-105">In this step you take the application definition file that you created using the Business Data Catalog Definition Editor tool, and import it into Microsoft Office SharePoint Server.</span></span>  
  
## <a name="prerequisites"></a><span data-ttu-id="71f00-106">前提条件</span><span class="sxs-lookup"><span data-stu-id="71f00-106">Prerequisites</span></span>  
  
-   <span data-ttu-id="71f00-107">作成済みアプリケーションのファイル」の説明に従って[手順 3。アプリケーション定義ファイルを作成](../../adapters-and-accelerators/wcf-lob-adapter-sdk/step-3-create-an-application-definition-file.md)です。</span><span class="sxs-lookup"><span data-stu-id="71f00-107">You should have created an application file as described in [Step 3: Create an Application Definition File](../../adapters-and-accelerators/wcf-lob-adapter-sdk/step-3-create-an-application-definition-file.md).</span></span>  
  
-   <span data-ttu-id="71f00-108">Microsoft シングル サインオン サービスを実行する必要があります。</span><span class="sxs-lookup"><span data-stu-id="71f00-108">The Microsoft Single Sign-On service must be running.</span></span>  
  
## <a name="how-to-create-a-sharepoint-application"></a><span data-ttu-id="71f00-109">SharePoint アプリケーションを作成する方法</span><span class="sxs-lookup"><span data-stu-id="71f00-109">How to Create a SharePoint Application</span></span>  
 <span data-ttu-id="71f00-110">SharePoint アプリケーションを作成するには、次の手順が含まれます。</span><span class="sxs-lookup"><span data-stu-id="71f00-110">Creating a SharePoint application involves the following steps:</span></span>  
  
- <span data-ttu-id="71f00-111">SharePoint でのシングル サインオン (SSO) アプリケーションを作成します。</span><span class="sxs-lookup"><span data-stu-id="71f00-111">Create a Single Sign-On (SSO) application in SharePoint.</span></span>  
  
- <span data-ttu-id="71f00-112">共有サービス プロバイダーを作成し、アプリケーション定義ファイルをインポートします。</span><span class="sxs-lookup"><span data-stu-id="71f00-112">Create a Shared Services Provider, and import the application definition file.</span></span>  
  
- <span data-ttu-id="71f00-113">Web パーツ ページを作成し、Web パーツを追加します。</span><span class="sxs-lookup"><span data-stu-id="71f00-113">Create a Web Part page, and add Web Parts.</span></span>  
  
  <span data-ttu-id="71f00-114">このトピックでは、次の手順を実行する方法を示します。</span><span class="sxs-lookup"><span data-stu-id="71f00-114">This topic demonstrates how to perform these steps.</span></span>  
  
## <a name="creating-an-sso-application-in-sharepoint"></a><span data-ttu-id="71f00-115">SharePoint での SSO アプリケーションの作成</span><span class="sxs-lookup"><span data-stu-id="71f00-115">Creating an SSO Application in SharePoint</span></span>  
 <span data-ttu-id="71f00-116">SharePoint アプリケーションからユーザーの資格情報をエコー アダプターに渡すには、ユーザー アカウントまたはグループにマップする SSO アプリケーションを設定する必要があります。</span><span class="sxs-lookup"><span data-stu-id="71f00-116">To pass user credentials to the Echo adapter from a SharePoint application, you must set up an SSO application that maps to a user account or group.</span></span>  
  
#### <a name="manage-server-settings-for-single-sign-on"></a><span data-ttu-id="71f00-117">シングル サインオン用のサーバー設定を管理します。</span><span class="sxs-lookup"><span data-stu-id="71f00-117">Manage server settings for Single Sign-On</span></span>  
  
1.  <span data-ttu-id="71f00-118">SharePoint 3.0 サーバーの全体管理を開始します。</span><span class="sxs-lookup"><span data-stu-id="71f00-118">Start SharePoint 3.0 Central Administration.</span></span> <span data-ttu-id="71f00-119">**開始**メニューで、**すべてのプログラム**、 をポイント**Microsoft Office Server**、 をクリックし、 **SharePoint 3.0 サーバーの全体管理**.</span><span class="sxs-lookup"><span data-stu-id="71f00-119">On the **Start** menu, point to **All Programs**, point to **Microsoft Office Server**, and then click **SharePoint 3.0 Central Administration**.</span></span>  
  
2.  <span data-ttu-id="71f00-120">上部のナビゲーション バーでクリックして**操作**します。</span><span class="sxs-lookup"><span data-stu-id="71f00-120">On the top navigation bar, click **Operations**.</span></span>  
  
3.  <span data-ttu-id="71f00-121">操作 ページで、**セキュリティの構成**セクションで、**でシングル サインオンの設定を管理**。</span><span class="sxs-lookup"><span data-stu-id="71f00-121">On the Operations page, in the **Security Configuration** section, click **Manage settings for single sign-on**.</span></span>  
  
4.  <span data-ttu-id="71f00-122">シングル サインオン] ページで、次の管理設定で、**サーバー設定**セクションで、[**サーバー設定の管理**します。</span><span class="sxs-lookup"><span data-stu-id="71f00-122">On the Manage Settings for Single Sign-On page, in the **Server Settings** section, click **Manage Server Settings**.</span></span>  
  
5.  <span data-ttu-id="71f00-123">このページの情報が、シングル サインオンのインストールの正しいことを確認します。</span><span class="sxs-lookup"><span data-stu-id="71f00-123">Ensure that the information on this page is correct for your Single Sign-On installation.</span></span> <span data-ttu-id="71f00-124">これらの操作の詳細についてを参照してください「シングル サインオン (Office SharePoint Server) の構成」 [ http://go.microsoft.com/fwlink/?LinkId=105291](http://go.microsoft.com/fwlink/?LinkId=105291)します。</span><span class="sxs-lookup"><span data-stu-id="71f00-124">For more information about these operations, see “Configure single sign-on (Office SharePoint Server)” at [http://go.microsoft.com/fwlink/?LinkId=105291](http://go.microsoft.com/fwlink/?LinkId=105291).</span></span>  
  
#### <a name="manage-settings-for-enterprise-application-definitions"></a><span data-ttu-id="71f00-125">エンタープライズ アプリケーション定義の設定を管理します。</span><span class="sxs-lookup"><span data-stu-id="71f00-125">Manage settings for enterprise application definitions</span></span>  
  
1.  <span data-ttu-id="71f00-126">SharePoint サーバーの全体管理で、上部のナビゲーション バーでクリックして**操作**します。</span><span class="sxs-lookup"><span data-stu-id="71f00-126">In SharePoint Central Administration, on the top navigation bar, click **Operations**.</span></span>  
  
2.  <span data-ttu-id="71f00-127">操作 ページで、**セキュリティの構成**セクションで、**でシングル サインオンの設定の管理**。</span><span class="sxs-lookup"><span data-stu-id="71f00-127">On the Operations page, in the **Security Configuration** section, click **Manage Settings for single sign-on**.</span></span>  
  
3.  <span data-ttu-id="71f00-128">シングル サインオン] ページで、次の管理設定で、**エンタープライズ アプリケーション定義の設定**セクションで、[**企業アプリケーション定義の設定の管理**します。</span><span class="sxs-lookup"><span data-stu-id="71f00-128">On the Manage Settings for Single Sign-On page, in the **Enterprise Application Definition Settings** section, click **Manage Settings for enterprise application definitions**.</span></span>  
  
4.  <span data-ttu-id="71f00-129">エンタープライズ アプリケーション定義の管理 ページで、次のようにクリックします。**新しい項目の**します。</span><span class="sxs-lookup"><span data-stu-id="71f00-129">On the Manage Enterprise Application Definitions page, click **New Item**.</span></span>  
  
5.  <span data-ttu-id="71f00-130">作成エンタープライズ アプリケーション定義 ページで、設定、**表示名**フィールドを**EchoSSO**、し、設定、**アプリケーション名**フィールドを**EchoSSO**します。</span><span class="sxs-lookup"><span data-stu-id="71f00-130">On the Create Enterprise Application Definitions Page, set the **Display name** field to **EchoSSO**, and then set the **Application name** field to **EchoSSO**.</span></span> <span data-ttu-id="71f00-131">この値がで指定した SecondarySsoApplicationId と一致する必要があります[手順 3。アプリケーション定義ファイルを作成](../../adapters-and-accelerators/wcf-lob-adapter-sdk/step-3-create-an-application-definition-file.md)です。</span><span class="sxs-lookup"><span data-stu-id="71f00-131">This value should match the SecondarySsoApplicationId you specified in [Step 3: Create an Application Definition File](../../adapters-and-accelerators/wcf-lob-adapter-sdk/step-3-create-an-application-definition-file.md).</span></span>  
  
6.  <span data-ttu-id="71f00-132">**連絡先の電子メール アドレス**フィールドを電子メール アドレスを入力し、をクリックし、 **OK**します。</span><span class="sxs-lookup"><span data-stu-id="71f00-132">In the **Contact e-mail address** field, enter your e-mail address, and then click **OK**.</span></span>  
  
#### <a name="manage-account-information-for-enterprise-application-definitions"></a><span data-ttu-id="71f00-133">エンタープライズ アプリケーション定義のアカウント情報を管理します。</span><span class="sxs-lookup"><span data-stu-id="71f00-133">Manage account information for enterprise application definitions</span></span>  
  
1.  <span data-ttu-id="71f00-134">SharePoint サーバーの全体管理で、上部のナビゲーション バーでクリックして**操作**します。</span><span class="sxs-lookup"><span data-stu-id="71f00-134">In SharePoint Central Administration, on the top navigation bar, click **Operations**.</span></span>  
  
2.  <span data-ttu-id="71f00-135">操作 ページで、**セキュリティ構成セクション**、 をクリックして**でシングル サインオンの設定を管理**します。</span><span class="sxs-lookup"><span data-stu-id="71f00-135">On the Operations page, in the **Security Configuration Section**, click **Manage settings for single sign-on**.</span></span>  
  
3.  <span data-ttu-id="71f00-136">シングル サインオン] ページで、次の管理設定で、**エンタープライズ アプリケーション定義の設定**セクションで、[**管理アカウントについて、エンタープライズ アプリケーション定義**します。</span><span class="sxs-lookup"><span data-stu-id="71f00-136">On the Manage Settings for Single Sign-On page, in the **Enterprise Application Definition Settings** section, click **Manage account information for enterprise application definitions**.</span></span>  
  
4.  <span data-ttu-id="71f00-137">エンタープライズ アプリケーション定義の管理アカウントは、次のように選択します。 **EchoSSO**から、**エンタープライズ アプリケーション定義**一覧。</span><span class="sxs-lookup"><span data-stu-id="71f00-137">On the Manage Account Information for an Enterprise Application Definition, select **EchoSSO** from the **Enterprise application definition** list.</span></span>  
  
5.  <span data-ttu-id="71f00-138">**グループ アカウント名**フィールドに、このアプリケーションの定義をセキュリティで保護するために使用する Windows グループを入力します。</span><span class="sxs-lookup"><span data-stu-id="71f00-138">In the **Group account name** field, type the Windows group that will be used to secure this application definition.</span></span> <span data-ttu-id="71f00-139">たとえば、 **DOMAIN\Domain ユーザー**します。</span><span class="sxs-lookup"><span data-stu-id="71f00-139">For example, **DOMAIN\Domain Users**.</span></span>  
  
6.  <span data-ttu-id="71f00-140">**[設定]** をクリックします。</span><span class="sxs-lookup"><span data-stu-id="71f00-140">Click **Set**.</span></span>  
  
7.  <span data-ttu-id="71f00-141">EchoSSO アカウント情報の提供 ページで、 **Username**フィールドに「 **testuser**、し、**パスワード**フィールドに「 **testpassword**.</span><span class="sxs-lookup"><span data-stu-id="71f00-141">On the Provide EchoSSO Account Information page, in the **Username** field type **testuser**, and then in the **Password** field type **testpassword**.</span></span>  
  
8.  <span data-ttu-id="71f00-142">をクリックして**OK**、順にクリックします**完了**します。</span><span class="sxs-lookup"><span data-stu-id="71f00-142">Click **OK**, and then click **Done**.</span></span>  
  
## <a name="creating-a-shared-services-provider-and-importing-the-application-definition-file"></a><span data-ttu-id="71f00-143">共有サービス プロバイダーを作成し、アプリケーション定義ファイルをインポートします。</span><span class="sxs-lookup"><span data-stu-id="71f00-143">Creating a Shared Services Provider and importing the application definition file</span></span>  
 <span data-ttu-id="71f00-144">共有サービス プロバイダー (SSP) は、共有サービスとその関連リソースの論理グループです。</span><span class="sxs-lookup"><span data-stu-id="71f00-144">A Shared Services Provider (SSP) is a logical grouping of shared services and their supporting resources.</span></span> <span data-ttu-id="71f00-145">SSP は、SharePoint サーバーの全体管理コンソールを使用して作成できます。</span><span class="sxs-lookup"><span data-stu-id="71f00-145">You can create an SSP by using the SharePoint Central Administration Console.</span></span> <span data-ttu-id="71f00-146">この例は、任意 SSP. で動作します。</span><span class="sxs-lookup"><span data-stu-id="71f00-146">This example will work in any SSP.</span></span> <span data-ttu-id="71f00-147">SSP の作成の詳細については、次を参照してください。"」の章の概要。作成し、共有サービス プロバイダーを構成する"で[ http://go.microsoft.com/fwlink/?LinkId=105119](http://go.microsoft.com/fwlink/?LinkId=105119)します。</span><span class="sxs-lookup"><span data-stu-id="71f00-147">For more information about creating an SSP, see “Chapter overview: Create and Configure Shared Services Providers” at [http://go.microsoft.com/fwlink/?LinkId=105119](http://go.microsoft.com/fwlink/?LinkId=105119).</span></span>  
  
### <a name="to-import-the-application-definition-file"></a><span data-ttu-id="71f00-148">アプリケーション定義ファイルをインポートするには</span><span class="sxs-lookup"><span data-stu-id="71f00-148">To import the application definition file</span></span>  
  
1.  <span data-ttu-id="71f00-149">SharePoint 3.0 サーバーの全体管理を開始します。</span><span class="sxs-lookup"><span data-stu-id="71f00-149">Start SharePoint 3.0 Central Administration.</span></span> <span data-ttu-id="71f00-150">**開始**メニューで、**すべてのプログラム**、 をポイント**Microsoft Office Server**、 をクリックし、 **SharePoint 3.0 サーバーの全体管理**.</span><span class="sxs-lookup"><span data-stu-id="71f00-150">On the **Start** menu, point to **All Programs**, point to **Microsoft Office Server**, and then click **SharePoint 3.0 Central Administration**.</span></span>  
  
2.  <span data-ttu-id="71f00-151">左側のナビゲーション ウィンドウで、アプリケーションの定義をインポートする SSP の名前をクリックします。</span><span class="sxs-lookup"><span data-stu-id="71f00-151">In the left navigation pane, click the name of the SSP to which you want to import the application definition.</span></span>  
  
3.  <span data-ttu-id="71f00-152">**ビジネス データ カタログ**セクションで、**アプリケーション定義のインポート**します。</span><span class="sxs-lookup"><span data-stu-id="71f00-152">In the **Business Data Catalog** section, click **Import application definition**.</span></span>  
  
4.  <span data-ttu-id="71f00-153">アプリケーション定義のインポート ページで、次のようにクリックします。**参照**、し EchoWS.xml ファイルを選択します。</span><span class="sxs-lookup"><span data-stu-id="71f00-153">On the Import Application Definition page, click **Browse**, and then select the EchoWS.xml file.</span></span>  
  
5.  <span data-ttu-id="71f00-154">クリックして**インポート**、順にクリックします**OK**します。</span><span class="sxs-lookup"><span data-stu-id="71f00-154">Click **Import**, and then click **OK**.</span></span>  
  
## <a name="creating-web-parts"></a><span data-ttu-id="71f00-155">Web パーツの作成</span><span class="sxs-lookup"><span data-stu-id="71f00-155">Creating Web Parts</span></span>  
 <span data-ttu-id="71f00-156">ビジネス データ カタログ定義エディターで作成メソッドのインスタンスを使用する SharePoint サイトで Web パーツを作成する必要があります。</span><span class="sxs-lookup"><span data-stu-id="71f00-156">You must now create Web Parts in your SharePoint site to use the method instance created in the Business Data Catalog Definition Editor.</span></span> <span data-ttu-id="71f00-157">Web パーツは、任意の種類の分析、コラボレーションなど、Web ベースの情報を含めることができ、データベース情報を再利用可能なコンポーネントです。</span><span class="sxs-lookup"><span data-stu-id="71f00-157">Web Parts are reusable components that can contain any kind of Web-based information, including analytical, collaborative, and database information.</span></span>  
  
#### <a name="to-create-a-web-part-page"></a><span data-ttu-id="71f00-158">Web パーツ ページを作成するには</span><span class="sxs-lookup"><span data-stu-id="71f00-158">To create a Web Part page</span></span>  
  
1.  <span data-ttu-id="71f00-159">SharePoint 3.0 サーバーの全体管理を開始します。</span><span class="sxs-lookup"><span data-stu-id="71f00-159">Start SharePoint 3.0 Central Administration.</span></span> <span data-ttu-id="71f00-160">**開始**メニューで、**すべてのプログラム**、 をポイント**Microsoft Office Server**、 をクリックし、 **SharePoint 3.0 サーバーの全体管理**.</span><span class="sxs-lookup"><span data-stu-id="71f00-160">On the **Start** menu, point to **All Programs**, point to **Microsoft Office Server**, and then click **SharePoint 3.0 Central Administration**.</span></span>  
  
2.  <span data-ttu-id="71f00-161">左側のナビゲーション ウィンドウで、アプリケーション定義ファイルをインポートした SSP の名前をクリックします。</span><span class="sxs-lookup"><span data-stu-id="71f00-161">In the left navigation pane, click the name of the SSP in which you imported the application definition file.</span></span>  
  
3.  <span data-ttu-id="71f00-162">共有サービス管理 ページで、右上隅にある**サイトの操作**、 をクリックし、**作成**です。</span><span class="sxs-lookup"><span data-stu-id="71f00-162">On the Shared Services Administration page, in the upper-right corner, click **Site Actions**, and then click **Create**.</span></span>  
  
     <span data-ttu-id="71f00-163">![サイトの操作を作成する](../../adapters-and-accelerators/wcf-lob-adapter-sdk/media/13f43659-ef61-48db-ac19-2d553367ec7e.gif "13f43659-ef61-48db-ac19-2d553367ec7e")</span><span class="sxs-lookup"><span data-stu-id="71f00-163">![Create Site Actions](../../adapters-and-accelerators/wcf-lob-adapter-sdk/media/13f43659-ef61-48db-ac19-2d553367ec7e.gif "13f43659-ef61-48db-ac19-2d553367ec7e")</span></span>  
  
4.  <span data-ttu-id="71f00-164">**作成**ページで、 **Web ページ**セクションで、 **Web パーツ ページ**します。</span><span class="sxs-lookup"><span data-stu-id="71f00-164">On the **Create** page, in the **Web Pages** section, click **Web Part Page**.</span></span>  
  
5.  <span data-ttu-id="71f00-165">新しい Web パーツ] ページで、**名前**フィールドに「 **EchoPart**、し、[**ページ全体を垂直**から、 **レイアウトテンプレートを選択した**一覧。</span><span class="sxs-lookup"><span data-stu-id="71f00-165">On the New Web Part page, in the **Name** field, type **EchoPart**, and then select **Full Page, Vertical** from the **Chose a Layout Template** list.</span></span>  
  
6.  <span data-ttu-id="71f00-166">**[作成]** をクリックします。</span><span class="sxs-lookup"><span data-stu-id="71f00-166">Click **Create**.</span></span>  
  
#### <a name="to-add-a-business-data-web-part"></a><span data-ttu-id="71f00-167">ビジネス データ Web パーツを追加するには</span><span class="sxs-lookup"><span data-stu-id="71f00-167">To add a Business Data Web Part</span></span>  
  
1.  <span data-ttu-id="71f00-168">**[Web パーツの追加]** をクリックします。</span><span class="sxs-lookup"><span data-stu-id="71f00-168">Click **Add a Web Part**.</span></span>  
  
2.  <span data-ttu-id="71f00-169">**Web パーツの追加**ダイアログ ボックスで、**ビジネス データ一覧**、 をクリックし、**追加**します。</span><span class="sxs-lookup"><span data-stu-id="71f00-169">In the **Add Web Parts** dialog box, select **Business Data List**, and then click **Add**.</span></span>  
  
     <span data-ttu-id="71f00-170">![ビジネス データ一覧](../../adapters-and-accelerators/wcf-lob-adapter-sdk/media/cd9e6bc8-c37e-49d2-9eaa-77246bb593df.gif "cd9e6bc8-c37e-49d2-9eaa-77246bb593df")</span><span class="sxs-lookup"><span data-stu-id="71f00-170">![Business Data List](../../adapters-and-accelerators/wcf-lob-adapter-sdk/media/cd9e6bc8-c37e-49d2-9eaa-77246bb593df.gif "cd9e6bc8-c37e-49d2-9eaa-77246bb593df")</span></span>  
  
3.  <span data-ttu-id="71f00-171">クリックして**ツール ウィンドウを開く**します。</span><span class="sxs-lookup"><span data-stu-id="71f00-171">Click **Open the tool pane**.</span></span>  
  
4.  <span data-ttu-id="71f00-172">ビジネス データ一覧のツール ウィンドウが右側のウィンドウで開きます。</span><span class="sxs-lookup"><span data-stu-id="71f00-172">The Business Data List tool pane opens in the right pane.</span></span> <span data-ttu-id="71f00-173">**ビジネス データ一覧**セクションの**型**フィールドに、をクリックして、**参照**ボタン。</span><span class="sxs-lookup"><span data-stu-id="71f00-173">In the **Business Data List** section, for the **Type** field, click the **Browse** button.</span></span>  
  
     <span data-ttu-id="71f00-174">![種類を選択して](../../adapters-and-accelerators/wcf-lob-adapter-sdk/media/a054ed0e-0880-4154-9050-a00da356a4f6.gif "a054ed0e-0880-4154-9050-a00da356a4f6")</span><span class="sxs-lookup"><span data-stu-id="71f00-174">![Select the Type](../../adapters-and-accelerators/wcf-lob-adapter-sdk/media/a054ed0e-0880-4154-9050-a00da356a4f6.gif "a054ed0e-0880-4154-9050-a00da356a4f6")</span></span>  
  
5.  <span data-ttu-id="71f00-175">**ビジネス データの種類の選択**ダイアログ ボックスで、 **EchoWSLob_Instance**アプリケーション、およびクリック**OK**します。</span><span class="sxs-lookup"><span data-stu-id="71f00-175">In the **Business Data Type Picker** dialog box, select the **EchoWSLob_Instance** application, and then click **OK**.</span></span>  
  
6.  <span data-ttu-id="71f00-176">ビジネス データ一覧のツール ウィンドウで、をクリックして**OK**します。</span><span class="sxs-lookup"><span data-stu-id="71f00-176">On the Business Data List tool pane, click **OK**.</span></span>  
  
7.  <span data-ttu-id="71f00-177">EchoGreetings メソッドに渡される応答メッセージの値を入力することを許可するフィールドが表示されます。</span><span class="sxs-lookup"><span data-stu-id="71f00-177">You are presented with a field that allows you to enter a greeting value to pass to the EchoGreetings method.</span></span> <span data-ttu-id="71f00-178">応答メッセージのフィールドにデータを入力し、クリックして**データの取得**します。</span><span class="sxs-lookup"><span data-stu-id="71f00-178">Enter data in the greeting field and click **Retrieve Data**.</span></span> <span data-ttu-id="71f00-179">これにより、IIS でホストされているエコー アダプターの EchoGreetings メソッドを呼び出し、応答を返します。</span><span class="sxs-lookup"><span data-stu-id="71f00-179">This invokes the EchoGreetings method of the Echo adapter hosted in IIS and returns a response.</span></span>  
  
     <span data-ttu-id="71f00-180">![EchoGreetings 一覧](../../adapters-and-accelerators/wcf-lob-adapter-sdk/media/f5a22fcd-2ae6-4384-9879-f0abd0255325.gif "f5a22fcd-2ae6-4384-9879-f0abd0255325")</span><span class="sxs-lookup"><span data-stu-id="71f00-180">![EchoGreetings List](../../adapters-and-accelerators/wcf-lob-adapter-sdk/media/f5a22fcd-2ae6-4384-9879-f0abd0255325.gif "f5a22fcd-2ae6-4384-9879-f0abd0255325")</span></span>  
  
    > [!NOTE]
    >  <span data-ttu-id="71f00-181">[名前] 列にユーザーの情報が含まれていませんが、BDC をのみが表示されます。名前。</span><span class="sxs-lookup"><span data-stu-id="71f00-181">The name column does not contain the user information, but only displays BDC.Name.</span></span> <span data-ttu-id="71f00-182">これは、BDC 単純なレコード構造体、のみを要求し、[名前] フィールドで表される複雑な構造は表示されないために発生します。</span><span class="sxs-lookup"><span data-stu-id="71f00-182">This occurs because the BDC expects only a simple record structure, and does not display the complex structure represented by the name field.</span></span>  
  
8.  <span data-ttu-id="71f00-183">クリックして**編集モードの終了**ページの上部隅から。</span><span class="sxs-lookup"><span data-stu-id="71f00-183">Click **Exit Edit Mode** from the upper corner of the page.</span></span>  
  
## <a name="what-did-i-just-do"></a><span data-ttu-id="71f00-184">でしただけ何か。</span><span class="sxs-lookup"><span data-stu-id="71f00-184">What did I just do?</span></span>  
 <span data-ttu-id="71f00-185">アプリケーション定義をインポートし、この定義を使用してエコー アダプターの EchoGreetings 操作を呼び出す Web パーツを作成するのには、SharePoint 3.0 サーバーの全体管理を使用しました。</span><span class="sxs-lookup"><span data-stu-id="71f00-185">You have used the SharePoint 3.0 Central Administration to import an application definition, and create Web Parts that use this definition to invoke the EchoGreetings operation of the Echo adapter.</span></span>  
  
## <a name="next-steps"></a><span data-ttu-id="71f00-186">次の手順</span><span class="sxs-lookup"><span data-stu-id="71f00-186">Next Steps</span></span>  
 <span data-ttu-id="71f00-187">このチュートリアルが完了しました。</span><span class="sxs-lookup"><span data-stu-id="71f00-187">This tutorial is complete.</span></span> <span data-ttu-id="71f00-188">詳細については、ビジネス データ カタログを使用して参照してください「ビジネス データ カタログ」 [ http://go.microsoft.com/fwlink/?LinkId=119921](http://go.microsoft.com/fwlink/?LinkId=119921)します。</span><span class="sxs-lookup"><span data-stu-id="71f00-188">For more information using the Business Data Catalog, see “Business Data Catalog” at [http://go.microsoft.com/fwlink/?LinkId=119921](http://go.microsoft.com/fwlink/?LinkId=119921).</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="71f00-189">参照</span><span class="sxs-lookup"><span data-stu-id="71f00-189">See Also</span></span>  
 [<span data-ttu-id="71f00-190">チュートリアル 3: IIS でエコー アダプターをホストする</span><span class="sxs-lookup"><span data-stu-id="71f00-190">Tutorial 3: Hosting the Echo Adapter in IIS</span></span>](../../adapters-and-accelerators/wcf-lob-adapter-sdk/tutorial-3-hosting-the-echo-adapter-in-iis.md)