---
title: '手順 3: Siebel からデータを取得する SharePoint アプリケーションの作成 |Microsoft Docs'
ms.custom: ''
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: ''
ms.suite: ''
ms.tgt_pltfrm: ''
ms.topic: article
ms.assetid: 86bde531-2daf-452b-b3e6-5481d66f72e7
caps.latest.revision: 14
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: df6c92b371291f4359c4bbce5e16529700bcc0c8
ms.sourcegitcommit: 266308ec5c6a9d8d80ff298ee6051b4843c5d626
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 06/27/2018
ms.locfileid: "36971867"
---
# <a name="step-3-create-a-sharepoint-application-to-retrieve-data-from-siebel"></a><span data-ttu-id="28852-102">手順 3: Siebel からデータを取得する SharePoint アプリケーションを作成します。</span><span class="sxs-lookup"><span data-stu-id="28852-102">Step 3: Create a SharePoint Application to Retrieve Data from Siebel</span></span>
<span data-ttu-id="28852-103">![手順 4 の 3](../../adapters-and-accelerators/adapter-oracle-ebs/media/step-3of4.gif "Step_3of4")</span><span class="sxs-lookup"><span data-stu-id="28852-103">![Step 3 of 4](../../adapters-and-accelerators/adapter-oracle-ebs/media/step-3of4.gif "Step_3of4")</span></span>  
  
 <span data-ttu-id="28852-104">**所要時間:** 15 分です。</span><span class="sxs-lookup"><span data-stu-id="28852-104">**Time to complete:** 15 minutes.</span></span>  
  
 <span data-ttu-id="28852-105">**目標:** ここでビジネス データ カタログ定義エディターを使用して作成したアプリケーション定義ファイルを取得し、Office SharePoint Server にインポートする必要があります。</span><span class="sxs-lookup"><span data-stu-id="28852-105">**Objective:** You must now take the application definition file you created by using the Business Data Catalog Definition Editor, and import it into Office SharePoint Server.</span></span>  
  
## <a name="prerequisites"></a><span data-ttu-id="28852-106">前提条件</span><span class="sxs-lookup"><span data-stu-id="28852-106">Prerequisites</span></span>  
  
-   <span data-ttu-id="28852-107">作成済み、アプリケーション定義ファイル」の説明に従って[手順 2: Siebel ビジネス コンポーネント操作用のアプリケーション定義ファイルの作成](../../adapters-and-accelerators/adapter-siebel/step-2-create-an-application-definition-file-for-siebel-business-component.md)です。</span><span class="sxs-lookup"><span data-stu-id="28852-107">You should have created an application definition file, as described in [Step 2: Create an Application Definition File for Siebel Business Component Operations](../../adapters-and-accelerators/adapter-siebel/step-2-create-an-application-definition-file-for-siebel-business-component.md).</span></span>  
  
-   <span data-ttu-id="28852-108">Microsoft シングル サインオン サービスを実行する必要があります。</span><span class="sxs-lookup"><span data-stu-id="28852-108">The Microsoft Single Sign-on service must be running.</span></span>  
  
## <a name="how-to-create-a-sharepoint-application"></a><span data-ttu-id="28852-109">SharePoint アプリケーションを作成する方法</span><span class="sxs-lookup"><span data-stu-id="28852-109">How to Create a SharePoint Application</span></span>  
 <span data-ttu-id="28852-110">SharePoint アプリケーションを作成するには、次の手順が含まれます。</span><span class="sxs-lookup"><span data-stu-id="28852-110">Creating a SharePoint application involves the following steps:</span></span>  
  
-   <span data-ttu-id="28852-111">SharePoint でのシングル サインオン (SSO) アプリケーションを作成します。</span><span class="sxs-lookup"><span data-stu-id="28852-111">Create a single sign-on (SSO) application in SharePoint</span></span>  
  
-   <span data-ttu-id="28852-112">共有サービス プロバイダー (SSP) の作成します。</span><span class="sxs-lookup"><span data-stu-id="28852-112">Create a Shared Services Provider (SSP)</span></span>  
  
-   <span data-ttu-id="28852-113">アプリケーション定義ファイルをインポートします。</span><span class="sxs-lookup"><span data-stu-id="28852-113">Import the application definition file</span></span>  
  
-   <span data-ttu-id="28852-114">Web パーツ ページを作成し、Web パーツを追加</span><span class="sxs-lookup"><span data-stu-id="28852-114">Create a Web Part page, and add Web Parts</span></span>  
  
## <a name="creating-an-sso-application-in-sharepoint"></a><span data-ttu-id="28852-115">SharePoint での SSO アプリケーションの作成</span><span class="sxs-lookup"><span data-stu-id="28852-115">Creating an SSO Application in SharePoint</span></span>  
 <span data-ttu-id="28852-116">SharePoint アプリケーションからの Siebel システムのデータにアクセスするには、Siebel のユーザーに、SharePoint ユーザーにマップする SSO アプリケーションを設定する必要があります。</span><span class="sxs-lookup"><span data-stu-id="28852-116">To access the data in a Siebel system from a SharePoint application, you must set up an SSO application that maps a SharePoint user to a Siebel user.</span></span> <span data-ttu-id="28852-117">SharePoint での SSO アプリケーションを作成するには、次の手順が含まれます。</span><span class="sxs-lookup"><span data-stu-id="28852-117">Creating an SSO application in SharePoint involves the following steps:</span></span>  
  
1.  <span data-ttu-id="28852-118">**シングル サインオンの設定をサーバー管理**します。</span><span class="sxs-lookup"><span data-stu-id="28852-118">**Manage server settings for single sign-on**.</span></span> <span data-ttu-id="28852-119">この手順では、管理、シングル サインオン サービスを設定しているユーザー アカウントを指定します。</span><span class="sxs-lookup"><span data-stu-id="28852-119">In this step, you specify a user account that can manage and set up the single sign-on service.</span></span> <span data-ttu-id="28852-120">サーバー設定の管理ページから行うことができます。</span><span class="sxs-lookup"><span data-stu-id="28852-120">You can do so from the Manage Server Settings page.</span></span> <span data-ttu-id="28852-121">このオプションは、SharePoint サーバーの全体管理コンソールから利用できます。</span><span class="sxs-lookup"><span data-stu-id="28852-121">This option is available from the SharePoint Central Administration console.</span></span> <span data-ttu-id="28852-122">この手順の詳細については、ある「構成でシングル サインオン Office SharePoint Server 2007 の」セクションを参照してください[ http://go.microsoft.com/fwlink/?LinkId=105291](http://go.microsoft.com/fwlink/?LinkId=105291)します。</span><span class="sxs-lookup"><span data-stu-id="28852-122">For more information about this step, refer to the “Configure Single Sign-On for Office SharePoint Server 2007” section at [http://go.microsoft.com/fwlink/?LinkId=105291](http://go.microsoft.com/fwlink/?LinkId=105291).</span></span>  
  
2.  <span data-ttu-id="28852-123">**エンタープライズ アプリケーション定義の設定を管理する**します。</span><span class="sxs-lookup"><span data-stu-id="28852-123">**Manage settings for enterprise application definitions**.</span></span> <span data-ttu-id="28852-124">この手順では、エンタープライズ アプリケーション定義の設定を構成します。</span><span class="sxs-lookup"><span data-stu-id="28852-124">In this step, you configure the settings for the enterprise application definition.</span></span> <span data-ttu-id="28852-125">エンタープライズ アプリケーション定義 ページの設定の管理から行うことができます。</span><span class="sxs-lookup"><span data-stu-id="28852-125">You can do so from the Manage Settings for Enterprise Application Definitions page.</span></span> <span data-ttu-id="28852-126">このオプションは、SharePoint サーバーの全体管理コンソールから利用できます。</span><span class="sxs-lookup"><span data-stu-id="28852-126">This option is available from the SharePoint Central Administration console.</span></span>  
  
    1.  <span data-ttu-id="28852-127">サーバーの全体管理で、上部のナビゲーション バーでクリックして**操作**します。</span><span class="sxs-lookup"><span data-stu-id="28852-127">On Central Administration, on the top navigation bar, click **Operations**.</span></span>  
  
    2.  <span data-ttu-id="28852-128">操作 ページで、**セキュリティの構成**セクションで、**でシングル サインオンの設定を管理**。</span><span class="sxs-lookup"><span data-stu-id="28852-128">On the Operations page, in the **Security Configuration** section, click  **Manage settings for single sign-on**.</span></span>  
  
    3.  <span data-ttu-id="28852-129">シングル サインオン ページで、設定の管理で、**エンタープライズ アプリケーション定義の設定**セクションで、**企業アプリケーション定義の設定を管理する**します。</span><span class="sxs-lookup"><span data-stu-id="28852-129">On the Manage Settings for Single Sign-On page, in the **Enterprise Application Definition Settings** section, click **Manage settings for enterprise application definitions**.</span></span>  
  
    4.  <span data-ttu-id="28852-130">エンタープライズ アプリケーション定義の管理 ページで、値を指定、**表示名**、**アプリケーション名**、および**連絡先の電子メール アドレス**フィールド。</span><span class="sxs-lookup"><span data-stu-id="28852-130">On the Manage Enterprise Application Definitions page, provide values for the **Display name**, **Application name**, and the **Contact e-mail address** fields.</span></span>  
  
        > [!IMPORTANT]
        >  <span data-ttu-id="28852-131">**アプリケーション名**フィールドに、指定したのと同じ SSO アプリケーション名を指定するかどうかを確認、 **SecondarySsoApplicationId**として、アプリケーション定義ファイルを作成するときに変数説明されている[手順 2: Siebel ビジネス コンポーネント操作用のアプリケーション定義ファイルの作成](../../adapters-and-accelerators/adapter-siebel/step-2-create-an-application-definition-file-for-siebel-business-component.md)です。</span><span class="sxs-lookup"><span data-stu-id="28852-131">For the **Application name** field, make sure you specify the same SSO application name that you specified for the **SecondarySsoApplicationId** variable while creating the application definition file, as described in [Step 2: Create an Application Definition File for Siebel Business Component Operations](../../adapters-and-accelerators/adapter-siebel/step-2-create-an-application-definition-file-for-siebel-business-component.md).</span></span>  
  
    5.  <span data-ttu-id="28852-132">既定では、他のフィールドのままにし、クリックして**OK**します。</span><span class="sxs-lookup"><span data-stu-id="28852-132">Leave the other fields as default, and click **OK**.</span></span>  
  
3.  <span data-ttu-id="28852-133">**エンタープライズ アプリケーション定義のアカウント情報の管理**します。</span><span class="sxs-lookup"><span data-stu-id="28852-133">**Manage account information for enterprise application definitions**.</span></span> <span data-ttu-id="28852-134">この手順では SharePoint からエンタープライズ アプリケーションに接続するには、個々 のユーザーまたはグループを有効にします。</span><span class="sxs-lookup"><span data-stu-id="28852-134">In this step, you enable individual users or groups to connect to an enterprise application from SharePoint.</span></span> <span data-ttu-id="28852-135">基本的には、この手順でマップするか、個々 のユーザーまたはグループをユーザーに、LOB システムに。</span><span class="sxs-lookup"><span data-stu-id="28852-135">Essentially, in this step you map an individual user or group to a user in the LOB system.</span></span> <span data-ttu-id="28852-136">また、LOB システムへの接続に資格情報を指定します。</span><span class="sxs-lookup"><span data-stu-id="28852-136">You also specify the credentials to connect to the LOB system.</span></span> <span data-ttu-id="28852-137">アカウント情報の管理からのエンタープライズ アプリケーション定義 ページで、これを実行できます。</span><span class="sxs-lookup"><span data-stu-id="28852-137">You can do so from Manage Account Information for Enterprise Application Definitions page.</span></span> <span data-ttu-id="28852-138">このオプションは、SharePoint サーバーの全体管理コンソールから利用できます。</span><span class="sxs-lookup"><span data-stu-id="28852-138">This option is available from the SharePoint Central Administration console.</span></span> <span data-ttu-id="28852-139">この手順の詳細については、ある「エンタープライズ アプリケーション定義のアカウント情報の管理」セクションを参照してください[ http://go.microsoft.com/fwlink/?LinkId=105291](http://go.microsoft.com/fwlink/?LinkId=105291)します。</span><span class="sxs-lookup"><span data-stu-id="28852-139">For more information about this step, refer to the “Manage account information for an enterprise application definition” section at [http://go.microsoft.com/fwlink/?LinkId=105291](http://go.microsoft.com/fwlink/?LinkId=105291).</span></span>  
  
## <a name="creating-a-shared-services-provider"></a><span data-ttu-id="28852-140">共有サービス プロバイダーを作成します。</span><span class="sxs-lookup"><span data-stu-id="28852-140">Creating a Shared Services Provider</span></span>  
 <span data-ttu-id="28852-141">SSP は、共有サービスとその関連リソースの論理グループです。</span><span class="sxs-lookup"><span data-stu-id="28852-141">An SSP is a logical grouping of shared services and their supporting resources.</span></span> <span data-ttu-id="28852-142">SharePoint サーバーの全体管理コンソールを使用して SSP を作成できます。</span><span class="sxs-lookup"><span data-stu-id="28852-142">You can create an SSP using the SharePoint Central Administration console.</span></span>  
  
 <span data-ttu-id="28852-143">SSP の作成中に Web サイトを定義する必要があります。</span><span class="sxs-lookup"><span data-stu-id="28852-143">You must define a Web site while creating an SSP.</span></span> <span data-ttu-id="28852-144">ポート番号とを作成するサイトのアドレスに注意してください。</span><span class="sxs-lookup"><span data-stu-id="28852-144">Remember the port number and the site address you create.</span></span> <span data-ttu-id="28852-145">このサイトには、ビジネス データ カタログ アプリケーション定義をインポートします。</span><span class="sxs-lookup"><span data-stu-id="28852-145">You will import the Business Data Catalog application definition to this site.</span></span>  
  
 <span data-ttu-id="28852-146">SSP の作成の詳細については、次を参照してください。"」の章の概要: を作成し、共有サービス プロバイダーを構成する"で[ http://go.microsoft.com/fwlink/?LinkId=105119](http://go.microsoft.com/fwlink/?LinkId=105119)します。</span><span class="sxs-lookup"><span data-stu-id="28852-146">For more information about creating an SSP, see "Chapter overview: Create and configure Shared Services Providers" at [http://go.microsoft.com/fwlink/?LinkId=105119](http://go.microsoft.com/fwlink/?LinkId=105119).</span></span>  
  
## <a name="importing-the-application-definition-file"></a><span data-ttu-id="28852-147">アプリケーション定義ファイルのインポート</span><span class="sxs-lookup"><span data-stu-id="28852-147">Importing the Application Definition File</span></span>  
 <span data-ttu-id="28852-148">SSP に今すぐアプリケーション定義ファイルをインポートする必要があります。</span><span class="sxs-lookup"><span data-stu-id="28852-148">You must now import the application definition file into the SSP.</span></span>  
  
#### <a name="to-import-the-application-definition-file"></a><span data-ttu-id="28852-149">アプリケーション定義ファイルをインポートするには</span><span class="sxs-lookup"><span data-stu-id="28852-149">To import the application definition file</span></span>  
  
1. <span data-ttu-id="28852-150">SharePoint 3.0 サーバーの全体管理を開始します。</span><span class="sxs-lookup"><span data-stu-id="28852-150">Start SharePoint 3.0 Central Administration.</span></span> <span data-ttu-id="28852-151">クリックして**開始**、 をポイント**すべてのプログラム**、 をポイント**Microsoft Office Server**、順にクリックします**SharePoint 3.0 サーバーの全体管理**.</span><span class="sxs-lookup"><span data-stu-id="28852-151">Click **Start**, point to **All Programs**, point to **Microsoft Office Server**, and then click **SharePoint 3.0 Central Administration**.</span></span>  
  
2. <span data-ttu-id="28852-152">左側のナビゲーション ウィンドウで、アプリケーションの定義をインポートする SSP の名前をクリックします。</span><span class="sxs-lookup"><span data-stu-id="28852-152">In the left navigation pane, click the name of the SSP to which you want to import the application definition.</span></span>  
  
3. <span data-ttu-id="28852-153">**ビジネス データ カタログ**セクションで、**アプリケーション定義のインポート**します。</span><span class="sxs-lookup"><span data-stu-id="28852-153">In the **Business Data Catalog** section, click **Import application definition**.</span></span>  
  
4. <span data-ttu-id="28852-154">Siebel_Account.xml、[参照] を開くと、アプリケーション定義のインポート ページで、ファイルを選択し、**オープン**します。</span><span class="sxs-lookup"><span data-stu-id="28852-154">On the Import Application Definition page that opens, browse to Siebel_Account.xml, select the file, and then click **Open**.</span></span>  
  
5. <span data-ttu-id="28852-155">**[インポート]** をクリックします。</span><span class="sxs-lookup"><span data-stu-id="28852-155">Click **Import**.</span></span>  
  
6. <span data-ttu-id="28852-156">**[OK]** をクリックします。</span><span class="sxs-lookup"><span data-stu-id="28852-156">Click **OK**.</span></span>  
  
   <span data-ttu-id="28852-157">アプリケーションをインポートした後、アプリケーションを表示して、**アプリケーションの表示**リンク。</span><span class="sxs-lookup"><span data-stu-id="28852-157">After importing the application, you can see your application by going to the **View Applications** link.</span></span> <span data-ttu-id="28852-158">アプリケーション内のエンティティを表示するのには、アプリケーション名をクリックします。</span><span class="sxs-lookup"><span data-stu-id="28852-158">Click the application name to see the entities in the application.</span></span>  
  
## <a name="creating-web-parts"></a><span data-ttu-id="28852-159">Web パーツの作成</span><span class="sxs-lookup"><span data-stu-id="28852-159">Creating Web Parts</span></span>  
 <span data-ttu-id="28852-160">表示し、Siebel システムから抽出するビジネス データを管理する SharePoint サイト内の Web パーツを作成する必要があります。</span><span class="sxs-lookup"><span data-stu-id="28852-160">You must now create Web Parts in your SharePoint site to view and manage the business data that will be extracted from the Siebel system.</span></span> <span data-ttu-id="28852-161">Web パーツは、任意の種類の分析、コラボレーションなど、Web ベースの情報を含めることができ、データベース情報を再利用可能なコンポーネントです。</span><span class="sxs-lookup"><span data-stu-id="28852-161">Web Parts are reusable components that can contain any kind of Web-based information, including analytical, collaborative, and database information.</span></span>  
  
 <span data-ttu-id="28852-162">このチュートリアルでは、ビジネス データ カタログ定義エディター内に作成されたメソッド インスタンスの Web パーツが作成されます。</span><span class="sxs-lookup"><span data-stu-id="28852-162">In this tutorial, Web Parts are created for the method instances that were created in Business Data Catalog Definition Editor.</span></span> <span data-ttu-id="28852-163">Office SharePoint Server では、特定の用途の場合は、さまざまな種類の Web パーツを提供します。</span><span class="sxs-lookup"><span data-stu-id="28852-163">Office SharePoint Server provides different kinds of Web Parts for specific use.</span></span> <span data-ttu-id="28852-164">Finder メソッド インスタンスの場合は使用、**ビジネス データ一覧**Web パーツ。</span><span class="sxs-lookup"><span data-stu-id="28852-164">For the Finder method instance, we will use the **Business Data List** Web Part.</span></span> <span data-ttu-id="28852-165">この Web パーツでは、アカウントのビジネス コンポーネントにクエリを実行する検索文字列を指定することができます。</span><span class="sxs-lookup"><span data-stu-id="28852-165">This Web Part enables you to specify a search expression to perform a query on the Account business component.</span></span> <span data-ttu-id="28852-166">このチュートリアルを呼び出してこの、**クエリ アカウント**Web パーツ。</span><span class="sxs-lookup"><span data-stu-id="28852-166">For this tutorial, we call this the **Query Accounts** Web Part.</span></span>  
  
 <span data-ttu-id="28852-167">ここでは、これらの Web パーツを作成する手順について説明します。</span><span class="sxs-lookup"><span data-stu-id="28852-167">This section provides instructions to create these Web Parts.</span></span> <span data-ttu-id="28852-168">Web パーツの作成の詳細についてを参照してください (「ビジネス データ リストのカスタマイズ、Web パーツ、およびサイト」) は、Microsoft Office SharePoint Server 2007 ドキュメント[ http://go.microsoft.com/fwlink/?LinkId=104131](http://go.microsoft.com/fwlink/?LinkId=104131)します。</span><span class="sxs-lookup"><span data-stu-id="28852-168">For more information about creating Web Parts, see the Microsoft Office SharePoint Server 2007 document ("Customize business data lists, Web Parts, and sites") at [http://go.microsoft.com/fwlink/?LinkId=104131](http://go.microsoft.com/fwlink/?LinkId=104131).</span></span>  
  
 <span data-ttu-id="28852-169">Web パーツは、1 つの Web パーツ ページに追加されます。</span><span class="sxs-lookup"><span data-stu-id="28852-169">The Web Parts will be added to a single Web Part page.</span></span> <span data-ttu-id="28852-170">Web パーツを追加する前に、Web パーツ ページを作成する必要があります。</span><span class="sxs-lookup"><span data-stu-id="28852-170">You must create a Web Part page before adding the Web Parts.</span></span> <span data-ttu-id="28852-171">このチュートリアルでは、Web パーツ ページが呼び出されます**Siebel アカウント**します。</span><span class="sxs-lookup"><span data-stu-id="28852-171">For this tutorial, the Web Part page is called **Siebel Account**.</span></span>  
  
### <a name="creating-a-web-part-page"></a><span data-ttu-id="28852-172">Web パーツ ページの作成</span><span class="sxs-lookup"><span data-stu-id="28852-172">Creating a Web Part Page</span></span>  
 <span data-ttu-id="28852-173">ここでは、Web パーツ ページを作成する手順について説明します。</span><span class="sxs-lookup"><span data-stu-id="28852-173">This section provides instructions to create a Web Part page.</span></span>  
  
##### <a name="to-create-a-web-part-page"></a><span data-ttu-id="28852-174">Web パーツ ページを作成するには</span><span class="sxs-lookup"><span data-stu-id="28852-174">To create a web part page</span></span>  
  
1. <span data-ttu-id="28852-175">SharePoint 3.0 サーバーの全体管理を開始します。</span><span class="sxs-lookup"><span data-stu-id="28852-175">Start SharePoint 3.0 Central Administration.</span></span> <span data-ttu-id="28852-176">をクリックして**開始**、 をポイント**すべてのプログラム**、 をポイント**Microsoft Office Server**、 をクリック**SharePoint 3.0 サーバーの全体管理**します。</span><span class="sxs-lookup"><span data-stu-id="28852-176">Click **Start**, point to **All Programs**, point to **Microsoft Office Server**, and click **SharePoint 3.0 Central Administration**.</span></span>  
  
2. <span data-ttu-id="28852-177">左側のナビゲーション ウィンドウで、アプリケーションの定義をインポートする SSP の名前をクリックします。</span><span class="sxs-lookup"><span data-stu-id="28852-177">In the left navigation pane, click the name of the SSP to which you want to import the application definition.</span></span>  
  
3. <span data-ttu-id="28852-178">共有サービス管理 ページで、右上隅から**サイトの操作**、 をクリックし、**作成**です。</span><span class="sxs-lookup"><span data-stu-id="28852-178">On the Shared Services Administration page, from the top right-hand corner, click **Site Actions**, and then click **Create**.</span></span>  
  
    <span data-ttu-id="28852-179">![Web パーツを作成するにはメニュー](../../adapters-and-accelerators/adapter-oracle-ebs/media/a9872c3e-f823-4c47-a538-19242565d2e9.gif "a9872c3e-f823-4c47-a538-19242565d2e9")</span><span class="sxs-lookup"><span data-stu-id="28852-179">![Menu to create a web part](../../adapters-and-accelerators/adapter-oracle-ebs/media/a9872c3e-f823-4c47-a538-19242565d2e9.gif "a9872c3e-f823-4c47-a538-19242565d2e9")</span></span>  
  
4. <span data-ttu-id="28852-180">作成 ページで、 **Web ページ**セクションで、 **Web パーツ ページ**します。</span><span class="sxs-lookup"><span data-stu-id="28852-180">On the Create page, under the **Web Pages** section, click **Web Part Page**.</span></span>  
  
5. <span data-ttu-id="28852-181">新しい Web パーツ ページで、次の操作を行います。</span><span class="sxs-lookup"><span data-stu-id="28852-181">In the New Web Part page, do the following:</span></span>  
  
   1. <span data-ttu-id="28852-182">**名前**フィールドに、ページの名前を指定します。</span><span class="sxs-lookup"><span data-stu-id="28852-182">In the **Name** field, specify a name for the page.</span></span> <span data-ttu-id="28852-183">このチュートリアルと名前を指定`Siebel Account`します。</span><span class="sxs-lookup"><span data-stu-id="28852-183">For this tutorial, specify the name as `Siebel Account`.</span></span>  
  
   2. <span data-ttu-id="28852-184">選択、**ファイルが既に存在する場合に上書き**チェック ボックスで、古いページを作成するページと同じ名前で上書きする場合。</span><span class="sxs-lookup"><span data-stu-id="28852-184">Select the **Overwrite if file already exists** check box, if you want to overwrite old pages with the same name as the page you create.</span></span>  
  
   3. <span data-ttu-id="28852-185">**レイアウト**セクションから、**レイアウト テンプレートの選択**ボックスに、Web パーツ ページのレイアウトを選択します。</span><span class="sxs-lookup"><span data-stu-id="28852-185">In the **Layout** section, from the **Choose a Layout Template** box, select a layout for the Web Part page.</span></span> <span data-ttu-id="28852-186">このチュートリアルでは、次のように選択します。**ページ全体を垂直**します。</span><span class="sxs-lookup"><span data-stu-id="28852-186">For this tutorial, select **Full Page, Vertical**.</span></span>  
  
   4. <span data-ttu-id="28852-187">**保存場所**セクションで、**ドキュメント ライブラリ**一覧で、**フォーム テンプレート**します。</span><span class="sxs-lookup"><span data-stu-id="28852-187">In **the Save Location** section, in the **Document Library** list, select **Form Templates**.</span></span>  
  
   5. <span data-ttu-id="28852-188">**[作成]** をクリックします。</span><span class="sxs-lookup"><span data-stu-id="28852-188">Click **Create**.</span></span> <span data-ttu-id="28852-189">次の図は、作成した後、Web パーツ ページを示します。</span><span class="sxs-lookup"><span data-stu-id="28852-189">The following figure shows a Web Part page after it is just created.</span></span>  
  
       <span data-ttu-id="28852-190">![空の Web パーツ ページ](../../adapters-and-accelerators/adapter-siebel/media/1fa218f5-de81-43be-b1b1-c46de422f112.gif "1fa218f5-de81-43be-b1b1-c46de422f112")</span><span class="sxs-lookup"><span data-stu-id="28852-190">![Empty Web Part page](../../adapters-and-accelerators/adapter-siebel/media/1fa218f5-de81-43be-b1b1-c46de422f112.gif "1fa218f5-de81-43be-b1b1-c46de422f112")</span></span>  
  
      <span data-ttu-id="28852-191">このページを別の Web パーツを追加する必要があります。</span><span class="sxs-lookup"><span data-stu-id="28852-191">You must now add the different Web Parts to this page.</span></span>  
  
### <a name="adding-a-business-data-list-web-part"></a><span data-ttu-id="28852-192">ビジネス データ一覧 Web パーツを追加します。</span><span class="sxs-lookup"><span data-stu-id="28852-192">Adding a Business Data List Web Part</span></span>  
 <span data-ttu-id="28852-193">Web パーツ ページに、ビジネス データ一覧 Web パーツを追加する必要がありますようになりました。</span><span class="sxs-lookup"><span data-stu-id="28852-193">You must now add a Business Data List Web Part to the Web Part page.</span></span> <span data-ttu-id="28852-194">この Web パーツを使用して、検索式を使用して、アカウントのビジネス コンポーネントは照会します。</span><span class="sxs-lookup"><span data-stu-id="28852-194">Using this Web Part, you will query the Account business component using a search expression.</span></span> <span data-ttu-id="28852-195">この Web パーツは、ビジネス データ カタログ定義エディターで作成した Finder メソッド インスタンス (QueryAccount) に対応します。</span><span class="sxs-lookup"><span data-stu-id="28852-195">This Web Part corresponds to the Finder method instance (QueryAccount) you created in the Business Data Catalog Definition Editor.</span></span>  
  
##### <a name="to-add-a-business-data-list-web-part"></a><span data-ttu-id="28852-196">ビジネス データ一覧 Web パーツを追加するには</span><span class="sxs-lookup"><span data-stu-id="28852-196">To add a Business Data List Web Part</span></span>  
  
1.  <span data-ttu-id="28852-197">**Siebel アカウント**ページで、**ヘッダー**セクションで、 **Web パーツの追加**します。</span><span class="sxs-lookup"><span data-stu-id="28852-197">In the **Siebel Account** page, in the **Header** section, click **Add a Web Part**.</span></span>  
  
2.  <span data-ttu-id="28852-198">**Web パーツの追加** ダイアログ ボックスで、**ビジネス データ**セクションで、**ビジネス データ一覧**チェック ボックスをオンにして**追加**します。</span><span class="sxs-lookup"><span data-stu-id="28852-198">In the **Add Web Parts** dialog box, in the **Business Data** section, select the **Business Data List** check box, and then click **Add**.</span></span>  
  
     <span data-ttu-id="28852-199">![ビジネス データ Web パーツを作成するオプション](../../adapters-and-accelerators/adapter-oracle-ebs/media/ae7c952c-1592-495f-9452-c1bffd44421c.gif "ae7c952c-1592-495f-9452-c1bffd44421c")</span><span class="sxs-lookup"><span data-stu-id="28852-199">![Options to create a business data Web Part](../../adapters-and-accelerators/adapter-oracle-ebs/media/ae7c952c-1592-495f-9452-c1bffd44421c.gif "ae7c952c-1592-495f-9452-c1bffd44421c")</span></span>  
  
3.  <span data-ttu-id="28852-200">新しく追加されたビジネス データ一覧 Web パーツ、クリックして、**ツール ウィンドウを開く**リンク。</span><span class="sxs-lookup"><span data-stu-id="28852-200">In the newly added Business Data List Web Part, click the **Open the tool pane** link.</span></span>  
  
     <span data-ttu-id="28852-201">![Web パーツのツール ウィンドウを開く](../../adapters-and-accelerators/adapter-oracle-ebs/media/4e7a1cb1-69dc-4e0d-a211-6a217dc4a549.gif "4e7a1cb1-69dc-4e0d-a211-6a217dc4a549")</span><span class="sxs-lookup"><span data-stu-id="28852-201">![Open the tool pane for Web Part](../../adapters-and-accelerators/adapter-oracle-ebs/media/4e7a1cb1-69dc-4e0d-a211-6a217dc4a549.gif "4e7a1cb1-69dc-4e0d-a211-6a217dc4a549")</span></span>  
  
4.  <span data-ttu-id="28852-202">ビジネス データ一覧のツール ウィンドウが右側のウィンドウで開きます。</span><span class="sxs-lookup"><span data-stu-id="28852-202">The Business Data List tool pane opens in the right pane.</span></span> <span data-ttu-id="28852-203">**ビジネス データ一覧**セクションの**型**フィールドに、をクリックして、**参照**ボタン。</span><span class="sxs-lookup"><span data-stu-id="28852-203">In the **Business Data List** section, for the **Type** field, click the **Browse** button.</span></span>  
  
     <span data-ttu-id="28852-204">![ビジネス データ一覧のツール ウィンドウ](../../adapters-and-accelerators/adapter-siebel/media/3b6e1576-03ce-4fc8-bf5a-7b414ef4408c.gif "3b6e1576-03ce-4fc8-bf5a-7b414ef4408c")</span><span class="sxs-lookup"><span data-stu-id="28852-204">![Business Data List tool pane](../../adapters-and-accelerators/adapter-siebel/media/3b6e1576-03ce-4fc8-bf5a-7b414ef4408c.gif "3b6e1576-03ce-4fc8-bf5a-7b414ef4408c")</span></span>  
  
5.  <span data-ttu-id="28852-205">**ビジネス データの種類の選択**ダイアログ ボックスで、 **Siebel_Account_Instance**アプリケーション、およびクリック**OK**します。</span><span class="sxs-lookup"><span data-stu-id="28852-205">In the **Business Data Type Picker** dialog box, select the **Siebel_Account_Instance** application, and then click **OK**.</span></span>  
  
     <span data-ttu-id="28852-206">![アプリケーション インスタンスの選択](../../adapters-and-accelerators/adapter-siebel/media/a658d06a-83a8-4e4b-9451-ce58e7ac3632.gif "a658d06a-83a8-4e4b-9451-ce58e7ac3632")</span><span class="sxs-lookup"><span data-stu-id="28852-206">![Select the application instance](../../adapters-and-accelerators/adapter-siebel/media/a658d06a-83a8-4e4b-9451-ce58e7ac3632.gif "a658d06a-83a8-4e4b-9451-ce58e7ac3632")</span></span>  
  
6.  <span data-ttu-id="28852-207">展開、**外観**ノード、および、**タイトル**フィールドに、Web パーツのタイトルを指定します。</span><span class="sxs-lookup"><span data-stu-id="28852-207">Expand the **Appearance** node, and in the **Title** field, specify a title for the Web Part.</span></span> <span data-ttu-id="28852-208">この Web パーツでは、指定**Account List**します。</span><span class="sxs-lookup"><span data-stu-id="28852-208">For this Web Part, specify **Account List**.</span></span>  
  
7.  <span data-ttu-id="28852-209">ビジネス データ一覧のツール ウィンドウで、次のようにクリックします。**適用**、 をクリックし、 **OK**します。</span><span class="sxs-lookup"><span data-stu-id="28852-209">In the Business Data List tool pane, click **Apply**, and then click **OK**.</span></span> <span data-ttu-id="28852-210">ビジネス データ一覧 Web パーツは、次のようになります。</span><span class="sxs-lookup"><span data-stu-id="28852-210">The Business Data List Web Part now looks like the following:</span></span>  
  
     <span data-ttu-id="28852-211">![ビジネス データ一覧 Web パーツ](../../adapters-and-accelerators/adapter-siebel/media/06dbb84a-38c3-4ece-b981-5aa7471909ed.gif "06dbb84a-38c3-4ece-b981-5aa7471909ed")</span><span class="sxs-lookup"><span data-stu-id="28852-211">![Business Data List Web Part](../../adapters-and-accelerators/adapter-siebel/media/06dbb84a-38c3-4ece-b981-5aa7471909ed.gif "06dbb84a-38c3-4ece-b981-5aa7471909ed")</span></span>  
  
    > [!NOTE]
    >  <span data-ttu-id="28852-212">パラメーターの列の順序を変更することもできます。</span><span class="sxs-lookup"><span data-stu-id="28852-212">You can also change the order in which the parameter columns appear.</span></span> <span data-ttu-id="28852-213">クリックして行うことができます、**ビューの編集**Web パーツの右上隅にあるリンクです。</span><span class="sxs-lookup"><span data-stu-id="28852-213">You can do so by clicking the **Edit View** link towards the right corner of the Web Part.</span></span>  
  
8.  <span data-ttu-id="28852-214">をクリックして**編集モードの終了**ページの右上隅にあるからです。</span><span class="sxs-lookup"><span data-stu-id="28852-214">Click **Exit Edit Mode** from the top right corner of the page.</span></span>  
  
## <a name="next-steps"></a><span data-ttu-id="28852-215">次の手順</span><span class="sxs-lookup"><span data-stu-id="28852-215">Next Steps</span></span>  
 <span data-ttu-id="28852-216">Siebel システムからデータを取得することによって、SharePoint アプリケーションをテストします。</span><span class="sxs-lookup"><span data-stu-id="28852-216">Test the SharePoint application by retrieving data from a Siebel system.</span></span> <span data-ttu-id="28852-217">参照してください[手順 4: SharePoint アプリケーションをテスト](../../adapters-and-accelerators/adapter-oracle-ebs/step-4-test-your-sharepoint-application.md)します。</span><span class="sxs-lookup"><span data-stu-id="28852-217">See [Step 4: Test Your SharePoint Application](../../adapters-and-accelerators/adapter-oracle-ebs/step-4-test-your-sharepoint-application.md).</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="28852-218">参照</span><span class="sxs-lookup"><span data-stu-id="28852-218">See Also</span></span>  
 [<span data-ttu-id="28852-219">チュートリアル 1: Siebel システムからのデータを SharePoint サイトに表示する</span><span class="sxs-lookup"><span data-stu-id="28852-219">Tutorial 1: Presenting Data From a Siebel System on a SharePoint Site</span></span>](../../adapters-and-accelerators/adapter-siebel/tutorial-1-presenting-data-from-a-siebel-system-on-a-sharepoint-site.md)