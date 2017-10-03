---
title: "手順 3: Siebel からデータを取得する SharePoint アプリケーションの作成 |Microsoft ドキュメント"
ms.custom: 
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: 
ms.suite: 
ms.tgt_pltfrm: 
ms.topic: article
ms.assetid: 86bde531-2daf-452b-b3e6-5481d66f72e7
caps.latest.revision: "14"
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: 94537b57a731e5d71459518fcbb0a528b6240d19
ms.sourcegitcommit: cb908c540d8f1a692d01dc8f313e16cb4b4e696d
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 09/20/2017
---
# <a name="step-3-create-a-sharepoint-application-to-retrieve-data-from-siebel"></a><span data-ttu-id="5986a-102">手順 3: Siebel からデータを取得する SharePoint アプリケーションを作成します。</span><span class="sxs-lookup"><span data-stu-id="5986a-102">Step 3: Create a SharePoint Application to Retrieve Data from Siebel</span></span>
<span data-ttu-id="5986a-103">![手順 4 の 3](../../adapters-and-accelerators/adapter-oracle-ebs/media/step-3of4.gif "Step_3of4")</span><span class="sxs-lookup"><span data-stu-id="5986a-103">![Step 3 of 4](../../adapters-and-accelerators/adapter-oracle-ebs/media/step-3of4.gif "Step_3of4")</span></span>  
  
 <span data-ttu-id="5986a-104">**所要時間:** 15 分です。</span><span class="sxs-lookup"><span data-stu-id="5986a-104">**Time to complete:** 15 minutes.</span></span>  
  
 <span data-ttu-id="5986a-105">**目標:**今すぐアプリケーション定義ファイルをエディターを使用して、ビジネス データ カタログの定義を作成して、Office SharePoint Server にインポートする必要があります。</span><span class="sxs-lookup"><span data-stu-id="5986a-105">**Objective:** You must now take the application definition file you created by using the Business Data Catalog Definition Editor, and import it into Office SharePoint Server.</span></span>  
  
## <a name="prerequisites"></a><span data-ttu-id="5986a-106">前提条件</span><span class="sxs-lookup"><span data-stu-id="5986a-106">Prerequisites</span></span>  
  
-   <span data-ttu-id="5986a-107">必要がありますが作成した、アプリケーション定義ファイル」の説明に従って[手順 2: Siebel ビジネス コンポーネント操作のアプリケーション定義ファイルを作成](../../adapters-and-accelerators/adapter-siebel/step-2-create-an-application-definition-file-for-siebel-business-component.md)です。</span><span class="sxs-lookup"><span data-stu-id="5986a-107">You should have created an application definition file, as described in [Step 2: Create an Application Definition File for Siebel Business Component Operations](../../adapters-and-accelerators/adapter-siebel/step-2-create-an-application-definition-file-for-siebel-business-component.md).</span></span>  
  
-   <span data-ttu-id="5986a-108">Microsoft シングル サインオン サービスを実行する必要があります。</span><span class="sxs-lookup"><span data-stu-id="5986a-108">The Microsoft Single Sign-on service must be running.</span></span>  
  
## <a name="how-to-create-a-sharepoint-application"></a><span data-ttu-id="5986a-109">SharePoint アプリケーションを作成する方法</span><span class="sxs-lookup"><span data-stu-id="5986a-109">How to Create a SharePoint Application</span></span>  
 <span data-ttu-id="5986a-110">SharePoint アプリケーションを作成するには、次の手順が含まれます。</span><span class="sxs-lookup"><span data-stu-id="5986a-110">Creating a SharePoint application involves the following steps:</span></span>  
  
-   <span data-ttu-id="5986a-111">SharePoint でのシングル サインオン (SSO) アプリケーションを作成します。</span><span class="sxs-lookup"><span data-stu-id="5986a-111">Create a single sign-on (SSO) application in SharePoint</span></span>  
  
-   <span data-ttu-id="5986a-112">共有サービス プロバイダー (SSP) を作成します。</span><span class="sxs-lookup"><span data-stu-id="5986a-112">Create a Shared Services Provider (SSP)</span></span>  
  
-   <span data-ttu-id="5986a-113">アプリケーション定義ファイルをインポートします。</span><span class="sxs-lookup"><span data-stu-id="5986a-113">Import the application definition file</span></span>  
  
-   <span data-ttu-id="5986a-114">Web パーツ ページを作成し、Web パーツを追加</span><span class="sxs-lookup"><span data-stu-id="5986a-114">Create a Web Part page, and add Web Parts</span></span>  
  
## <a name="creating-an-sso-application-in-sharepoint"></a><span data-ttu-id="5986a-115">SharePoint での SSO アプリケーションの作成</span><span class="sxs-lookup"><span data-stu-id="5986a-115">Creating an SSO Application in SharePoint</span></span>  
 <span data-ttu-id="5986a-116">SharePoint アプリケーションからの Siebel システム データにアクセスするには、Siebel のユーザーに、SharePoint ユーザーにマップする SSO アプリケーションを設定する必要があります。</span><span class="sxs-lookup"><span data-stu-id="5986a-116">To access the data in a Siebel system from a SharePoint application, you must set up an SSO application that maps a SharePoint user to a Siebel user.</span></span> <span data-ttu-id="5986a-117">SharePoint で SSO アプリケーションを作成するには、次の手順が含まれます。</span><span class="sxs-lookup"><span data-stu-id="5986a-117">Creating an SSO application in SharePoint involves the following steps:</span></span>  
  
1.  <span data-ttu-id="5986a-118">**シングル サインオンの設定をサーバー管理**です。</span><span class="sxs-lookup"><span data-stu-id="5986a-118">**Manage server settings for single sign-on**.</span></span> <span data-ttu-id="5986a-119">このステップでは、管理、シングル サインオン サービスを設定したりできるユーザー アカウントを指定します。</span><span class="sxs-lookup"><span data-stu-id="5986a-119">In this step, you specify a user account that can manage and set up the single sign-on service.</span></span> <span data-ttu-id="5986a-120">サーバー設定の管理ページから行うことができます。</span><span class="sxs-lookup"><span data-stu-id="5986a-120">You can do so from the Manage Server Settings page.</span></span> <span data-ttu-id="5986a-121">このオプションを指定する場合は、SharePoint サーバーの全体管理コンソールで実行できます。</span><span class="sxs-lookup"><span data-stu-id="5986a-121">This option is available from the SharePoint Central Administration console.</span></span> <span data-ttu-id="5986a-122">この手順の詳細についてで「構成に対するシングル サインオン - Office SharePoint Server 2007」セクションを参照してください[http://go.microsoft.com/fwlink/?LinkId=105291](http://go.microsoft.com/fwlink/?LinkId=105291)です。</span><span class="sxs-lookup"><span data-stu-id="5986a-122">For more information about this step, refer to the “Configure Single Sign-On for Office SharePoint Server 2007” section at [http://go.microsoft.com/fwlink/?LinkId=105291](http://go.microsoft.com/fwlink/?LinkId=105291).</span></span>  
  
2.  <span data-ttu-id="5986a-123">**エンタープライズ アプリケーション定義の設定を管理**です。</span><span class="sxs-lookup"><span data-stu-id="5986a-123">**Manage settings for enterprise application definitions**.</span></span> <span data-ttu-id="5986a-124">このステップでは、エンタープライズ アプリケーション定義の設定を構成します。</span><span class="sxs-lookup"><span data-stu-id="5986a-124">In this step, you configure the settings for the enterprise application definition.</span></span> <span data-ttu-id="5986a-125">エンタープライズ アプリケーション定義 ページの設定の管理から行うことができます。</span><span class="sxs-lookup"><span data-stu-id="5986a-125">You can do so from the Manage Settings for Enterprise Application Definitions page.</span></span> <span data-ttu-id="5986a-126">このオプションを指定する場合は、SharePoint サーバーの全体管理コンソールで実行できます。</span><span class="sxs-lookup"><span data-stu-id="5986a-126">This option is available from the SharePoint Central Administration console.</span></span>  
  
    1.  <span data-ttu-id="5986a-127">サーバーの全体管理で、上部のナビゲーション バーで、をクリックして**Operations**です。</span><span class="sxs-lookup"><span data-stu-id="5986a-127">On Central Administration, on the top navigation bar, click **Operations**.</span></span>  
  
    2.  <span data-ttu-id="5986a-128">[操作] ページで、**セキュリティの構成**セクションで、をクリックして**でのシングル サインオンの設定を管理**です。</span><span class="sxs-lookup"><span data-stu-id="5986a-128">On the Operations page, in the **Security Configuration** section, click  **Manage settings for single sign-on**.</span></span>  
  
    3.  <span data-ttu-id="5986a-129">シングル サインオン] ページの設定の管理で、**エンタープライズ アプリケーション定義の設定**セクションで、[**企業アプリケーション定義の設定を管理**です。</span><span class="sxs-lookup"><span data-stu-id="5986a-129">On the Manage Settings for Single Sign-On page, in the **Enterprise Application Definition Settings** section, click **Manage settings for enterprise application definitions**.</span></span>  
  
    4.  <span data-ttu-id="5986a-130">[エンタープライズ アプリケーション定義の管理] ページで、値を指定して、**表示名**、**アプリケーション名**、および**連絡先の電子メール アドレス**フィールドです。</span><span class="sxs-lookup"><span data-stu-id="5986a-130">On the Manage Enterprise Application Definitions page, provide values for the **Display name**, **Application name**, and the **Contact e-mail address** fields.</span></span>  
  
        > [!IMPORTANT]
        >  <span data-ttu-id="5986a-131">**アプリケーション名**フィールドに、指定した同じ SSO アプリケーション名を指定するかどうかを確認、 **SecondarySsoApplicationId**として、アプリケーション定義ファイルの作成中に変数説明されている[手順 2: Siebel ビジネス コンポーネント操作のアプリケーション定義ファイルを作成](../../adapters-and-accelerators/adapter-siebel/step-2-create-an-application-definition-file-for-siebel-business-component.md)です。</span><span class="sxs-lookup"><span data-stu-id="5986a-131">For the **Application name** field, make sure you specify the same SSO application name that you specified for the **SecondarySsoApplicationId** variable while creating the application definition file, as described in [Step 2: Create an Application Definition File for Siebel Business Component Operations](../../adapters-and-accelerators/adapter-siebel/step-2-create-an-application-definition-file-for-siebel-business-component.md).</span></span>  
  
    5.  <span data-ttu-id="5986a-132">既定では、他のフィールドのままにし、をクリックして**OK**です。</span><span class="sxs-lookup"><span data-stu-id="5986a-132">Leave the other fields as default, and click **OK**.</span></span>  
  
3.  <span data-ttu-id="5986a-133">**エンタープライズ アプリケーション定義のアカウント情報を管理する**です。</span><span class="sxs-lookup"><span data-stu-id="5986a-133">**Manage account information for enterprise application definitions**.</span></span> <span data-ttu-id="5986a-134">このステップでは SharePoint からエンタープライズ アプリケーションに接続するには、個々 のユーザーまたはグループを有効にします。</span><span class="sxs-lookup"><span data-stu-id="5986a-134">In this step, you enable individual users or groups to connect to an enterprise application from SharePoint.</span></span> <span data-ttu-id="5986a-135">基本的には、この手順でマップする個々 のユーザーまたはグループのユーザーに LOB システムに。</span><span class="sxs-lookup"><span data-stu-id="5986a-135">Essentially, in this step you map an individual user or group to a user in the LOB system.</span></span> <span data-ttu-id="5986a-136">また、LOB システムへの接続に資格情報を指定します。</span><span class="sxs-lookup"><span data-stu-id="5986a-136">You also specify the credentials to connect to the LOB system.</span></span> <span data-ttu-id="5986a-137">そのため操作は、エンタープライズ アプリケーション定義 ページのアカウント情報の管理から実行できます。</span><span class="sxs-lookup"><span data-stu-id="5986a-137">You can do so from Manage Account Information for Enterprise Application Definitions page.</span></span> <span data-ttu-id="5986a-138">このオプションを指定する場合は、SharePoint サーバーの全体管理コンソールで実行できます。</span><span class="sxs-lookup"><span data-stu-id="5986a-138">This option is available from the SharePoint Central Administration console.</span></span> <span data-ttu-id="5986a-139">この手順の詳細についてで「エンタープライズ アプリケーション定義のアカウント情報の管理」セクションを参照してください[http://go.microsoft.com/fwlink/?LinkId=105291](http://go.microsoft.com/fwlink/?LinkId=105291)です。</span><span class="sxs-lookup"><span data-stu-id="5986a-139">For more information about this step, refer to the “Manage account information for an enterprise application definition” section at [http://go.microsoft.com/fwlink/?LinkId=105291](http://go.microsoft.com/fwlink/?LinkId=105291).</span></span>  
  
## <a name="creating-a-shared-services-provider"></a><span data-ttu-id="5986a-140">共有サービス プロバイダーを作成します。</span><span class="sxs-lookup"><span data-stu-id="5986a-140">Creating a Shared Services Provider</span></span>  
 <span data-ttu-id="5986a-141">SSP は、共有サービスとその関連リソースの論理グループです。</span><span class="sxs-lookup"><span data-stu-id="5986a-141">An SSP is a logical grouping of shared services and their supporting resources.</span></span> <span data-ttu-id="5986a-142">SharePoint サーバーの全体管理コンソールを使用して SSP を作成することができます。</span><span class="sxs-lookup"><span data-stu-id="5986a-142">You can create an SSP using the SharePoint Central Administration console.</span></span>  
  
 <span data-ttu-id="5986a-143">SSP の作成中に Web サイトを定義する必要があります。</span><span class="sxs-lookup"><span data-stu-id="5986a-143">You must define a Web site while creating an SSP.</span></span> <span data-ttu-id="5986a-144">ポート番号および作成するサイトのアドレスに注意してください。</span><span class="sxs-lookup"><span data-stu-id="5986a-144">Remember the port number and the site address you create.</span></span> <span data-ttu-id="5986a-145">このサイトには、ビジネス データ カタログ アプリケーション定義をインポートします。</span><span class="sxs-lookup"><span data-stu-id="5986a-145">You will import the Business Data Catalog application definition to this site.</span></span>  
  
 <span data-ttu-id="5986a-146">SSP の作成の詳細については、次を参照してください。"章の概要: を作成し、共有サービス プロバイダーを構成する"で[http://go.microsoft.com/fwlink/?LinkId=105119](http://go.microsoft.com/fwlink/?LinkId=105119)です。</span><span class="sxs-lookup"><span data-stu-id="5986a-146">For more information about creating an SSP, see "Chapter overview: Create and configure Shared Services Providers" at [http://go.microsoft.com/fwlink/?LinkId=105119](http://go.microsoft.com/fwlink/?LinkId=105119).</span></span>  
  
## <a name="importing-the-application-definition-file"></a><span data-ttu-id="5986a-147">アプリケーション定義ファイルのインポート</span><span class="sxs-lookup"><span data-stu-id="5986a-147">Importing the Application Definition File</span></span>  
 <span data-ttu-id="5986a-148">SSP にアプリケーション定義ファイルをインポートする必要があります。</span><span class="sxs-lookup"><span data-stu-id="5986a-148">You must now import the application definition file into the SSP.</span></span>  
  
#### <a name="to-import-the-application-definition-file"></a><span data-ttu-id="5986a-149">アプリケーション定義ファイルをインポートするには</span><span class="sxs-lookup"><span data-stu-id="5986a-149">To import the application definition file</span></span>  
  
1.  <span data-ttu-id="5986a-150">SharePoint 3.0 サーバーの全体管理を開始します。</span><span class="sxs-lookup"><span data-stu-id="5986a-150">Start SharePoint 3.0 Central Administration.</span></span> <span data-ttu-id="5986a-151">をクリックして**開始**、 をポイント**すべてのプログラム**、 をポイント**Microsoft Office Server**、クリックして**SharePoint 3.0 サーバーの全体管理**.</span><span class="sxs-lookup"><span data-stu-id="5986a-151">Click **Start**, point to **All Programs**, point to **Microsoft Office Server**, and then click **SharePoint 3.0 Central Administration**.</span></span>  
  
2.  <span data-ttu-id="5986a-152">左側のナビゲーション ウィンドウで、アプリケーション定義をインポートする SSP の名前をクリックします。</span><span class="sxs-lookup"><span data-stu-id="5986a-152">In the left navigation pane, click the name of the SSP to which you want to import the application definition.</span></span>  
  
3.  <span data-ttu-id="5986a-153">**ビジネス データ カタログ**セクションで、**アプリケーション定義のインポート**です。</span><span class="sxs-lookup"><span data-stu-id="5986a-153">In the **Business Data Catalog** section, click **Import application definition**.</span></span>  
  
4.  <span data-ttu-id="5986a-154">Siebel_Account.xml、[参照] を開くと、アプリケーション定義のインポート ページで、ファイルを選択し、をクリックして**開く**です。</span><span class="sxs-lookup"><span data-stu-id="5986a-154">On the Import Application Definition page that opens, browse to Siebel_Account.xml, select the file, and then click **Open**.</span></span>  
  
5.  <span data-ttu-id="5986a-155">**[インポート]**をクリックします。</span><span class="sxs-lookup"><span data-stu-id="5986a-155">Click **Import**.</span></span>  
  
6.  <span data-ttu-id="5986a-156">**[OK]**をクリックします。</span><span class="sxs-lookup"><span data-stu-id="5986a-156">Click **OK**.</span></span>  
  
 <span data-ttu-id="5986a-157">アプリケーションをインポートした後に移動して、アプリケーションを表示できます、**ビュー アプリケーション**リンクします。</span><span class="sxs-lookup"><span data-stu-id="5986a-157">After importing the application, you can see your application by going to the **View Applications** link.</span></span> <span data-ttu-id="5986a-158">アプリケーション内のエンティティを表示するのには、アプリケーション名をクリックします。</span><span class="sxs-lookup"><span data-stu-id="5986a-158">Click the application name to see the entities in the application.</span></span>  
  
## <a name="creating-web-parts"></a><span data-ttu-id="5986a-159">Web パーツを作成します。</span><span class="sxs-lookup"><span data-stu-id="5986a-159">Creating Web Parts</span></span>  
 <span data-ttu-id="5986a-160">SharePoint サイトの表示し、Siebel システムから抽出するビジネス データを管理する Web パーツを作成する必要があります。</span><span class="sxs-lookup"><span data-stu-id="5986a-160">You must now create Web Parts in your SharePoint site to view and manage the business data that will be extracted from the Siebel system.</span></span> <span data-ttu-id="5986a-161">Web パーツは、任意の種類の分析、コラボレーションなど、Web ベースの情報を含むおよびデータベース情報が使用できる再利用可能なコンポーネントです。</span><span class="sxs-lookup"><span data-stu-id="5986a-161">Web Parts are reusable components that can contain any kind of Web-based information, including analytical, collaborative, and database information.</span></span>  
  
 <span data-ttu-id="5986a-162">このチュートリアルでは、Web パーツは、ビジネス データ カタログ定義エディターで作成されたメソッドのインスタンスに対して作成されます。</span><span class="sxs-lookup"><span data-stu-id="5986a-162">In this tutorial, Web Parts are created for the method instances that were created in Business Data Catalog Definition Editor.</span></span> <span data-ttu-id="5986a-163">Office SharePoint Server では、特定の使用の Web パーツのさまざまな種類を提供します。</span><span class="sxs-lookup"><span data-stu-id="5986a-163">Office SharePoint Server provides different kinds of Web Parts for specific use.</span></span> <span data-ttu-id="5986a-164">Finder メソッド インスタンスは、使用、**ビジネス データ一覧**Web パーツ。</span><span class="sxs-lookup"><span data-stu-id="5986a-164">For the Finder method instance, we will use the **Business Data List** Web Part.</span></span> <span data-ttu-id="5986a-165">この Web パーツでは、アカウントのビジネス コンポーネントでクエリを実行する検索文字列を指定することができます。</span><span class="sxs-lookup"><span data-stu-id="5986a-165">This Web Part enables you to specify a search expression to perform a query on the Account business component.</span></span> <span data-ttu-id="5986a-166">このチュートリアルを呼び出してこの、**クエリ アカウント**Web パーツ。</span><span class="sxs-lookup"><span data-stu-id="5986a-166">For this tutorial, we call this the **Query Accounts** Web Part.</span></span>  
  
 <span data-ttu-id="5986a-167">このセクションでは、これらの Web パーツを作成する手順を説明します。</span><span class="sxs-lookup"><span data-stu-id="5986a-167">This section provides instructions to create these Web Parts.</span></span> <span data-ttu-id="5986a-168">Web パーツの作成の詳細についてを参照してください (「ビジネス データ リストのカスタマイズ、Web パーツ、およびサイト」)、Microsoft Office SharePoint Server 2007 ドキュメント[http://go.microsoft.com/fwlink/?LinkId=104131](http://go.microsoft.com/fwlink/?LinkId=104131)です。</span><span class="sxs-lookup"><span data-stu-id="5986a-168">For more information about creating Web Parts, see the Microsoft Office SharePoint Server 2007 document ("Customize business data lists, Web Parts, and sites") at [http://go.microsoft.com/fwlink/?LinkId=104131](http://go.microsoft.com/fwlink/?LinkId=104131).</span></span>  
  
 <span data-ttu-id="5986a-169">Web パーツは、1 つの Web パーツ ページに追加されます。</span><span class="sxs-lookup"><span data-stu-id="5986a-169">The Web Parts will be added to a single Web Part page.</span></span> <span data-ttu-id="5986a-170">Web パーツを追加する前に、Web パーツ ページを作成する必要があります。</span><span class="sxs-lookup"><span data-stu-id="5986a-170">You must create a Web Part page before adding the Web Parts.</span></span> <span data-ttu-id="5986a-171">このチュートリアルでは、Web パーツ ページと呼ばれる**Siebel アカウント**です。</span><span class="sxs-lookup"><span data-stu-id="5986a-171">For this tutorial, the Web Part page is called **Siebel Account**.</span></span>  
  
### <a name="creating-a-web-part-page"></a><span data-ttu-id="5986a-172">Web パーツ ページを作成します。</span><span class="sxs-lookup"><span data-stu-id="5986a-172">Creating a Web Part Page</span></span>  
 <span data-ttu-id="5986a-173">このセクションでは、Web パーツ ページを作成する手順を説明します。</span><span class="sxs-lookup"><span data-stu-id="5986a-173">This section provides instructions to create a Web Part page.</span></span>  
  
##### <a name="to-create-a-web-part-page"></a><span data-ttu-id="5986a-174">Web パーツ ページを作成するには</span><span class="sxs-lookup"><span data-stu-id="5986a-174">To create a web part page</span></span>  
  
1.  <span data-ttu-id="5986a-175">SharePoint 3.0 サーバーの全体管理を開始します。</span><span class="sxs-lookup"><span data-stu-id="5986a-175">Start SharePoint 3.0 Central Administration.</span></span> <span data-ttu-id="5986a-176">をクリックして**開始**、 をポイント**すべてのプログラム**、 をポイント**Microsoft Office Server**、 をクリック**SharePoint 3.0 サーバーの全体管理**です。</span><span class="sxs-lookup"><span data-stu-id="5986a-176">Click **Start**, point to **All Programs**, point to **Microsoft Office Server**, and click **SharePoint 3.0 Central Administration**.</span></span>  
  
2.  <span data-ttu-id="5986a-177">左側のナビゲーション ウィンドウで、アプリケーション定義をインポートする SSP の名前をクリックします。</span><span class="sxs-lookup"><span data-stu-id="5986a-177">In the left navigation pane, click the name of the SSP to which you want to import the application definition.</span></span>  
  
3.  <span data-ttu-id="5986a-178">共有サービスの管理 ページで、右上隅から**サイトの操作**、クリックして**作成**です。</span><span class="sxs-lookup"><span data-stu-id="5986a-178">On the Shared Services Administration page, from the top right-hand corner, click **Site Actions**, and then click **Create**.</span></span>  
  
     <span data-ttu-id="5986a-179">![Web パーツを作成するにはメニュー](../../adapters-and-accelerators/adapter-oracle-ebs/media/a9872c3e-f823-4c47-a538-19242565d2e9.gif "a9872c3e-f823-4c47-a538-19242565d2e9")</span><span class="sxs-lookup"><span data-stu-id="5986a-179">![Menu to create a web part](../../adapters-and-accelerators/adapter-oracle-ebs/media/a9872c3e-f823-4c47-a538-19242565d2e9.gif "a9872c3e-f823-4c47-a538-19242565d2e9")</span></span>  
  
4.  <span data-ttu-id="5986a-180">作成 ページで、 **Web ページ**セクションで、 **Web パーツ ページ**です。</span><span class="sxs-lookup"><span data-stu-id="5986a-180">On the Create page, under the **Web Pages** section, click **Web Part Page**.</span></span>  
  
5.  <span data-ttu-id="5986a-181">新しい Web パーツ ページで、次の操作を行います。</span><span class="sxs-lookup"><span data-stu-id="5986a-181">In the New Web Part page, do the following:</span></span>  
  
    1.  <span data-ttu-id="5986a-182">**名前**フィールドに、ページの名前を指定します。</span><span class="sxs-lookup"><span data-stu-id="5986a-182">In the **Name** field, specify a name for the page.</span></span> <span data-ttu-id="5986a-183">このチュートリアルでは、名前を指定、として`Siebel Account`です。</span><span class="sxs-lookup"><span data-stu-id="5986a-183">For this tutorial, specify the name as `Siebel Account`.</span></span>  
  
    2.  <span data-ttu-id="5986a-184">選択、**ファイルが既に存在する場合に上書き**チェック ボックスを作成するページと同じ名前で古いページを上書きする場合。</span><span class="sxs-lookup"><span data-stu-id="5986a-184">Select the **Overwrite if file already exists** check box, if you want to overwrite old pages with the same name as the page you create.</span></span>  
  
    3.  <span data-ttu-id="5986a-185">**レイアウト** セクションから、**レイアウト テンプレートを選択して**ボックスで、Web パーツ ページのレイアウトを選択します。</span><span class="sxs-lookup"><span data-stu-id="5986a-185">In the **Layout** section, from the **Choose a Layout Template** box, select a layout for the Web Part page.</span></span> <span data-ttu-id="5986a-186">このチュートリアルでは、次のように選択します。**ページ全体を垂直方向**です。</span><span class="sxs-lookup"><span data-stu-id="5986a-186">For this tutorial, select **Full Page, Vertical**.</span></span>  
  
    4.  <span data-ttu-id="5986a-187">**保存場所**セクションで、**ドキュメント ライブラリ**一覧で、**フォーム テンプレート**です。</span><span class="sxs-lookup"><span data-stu-id="5986a-187">In **the Save Location** section, in the **Document Library** list, select **Form Templates**.</span></span>  
  
    5.  <span data-ttu-id="5986a-188">**[作成]**をクリックします。</span><span class="sxs-lookup"><span data-stu-id="5986a-188">Click **Create**.</span></span> <span data-ttu-id="5986a-189">次の図は、作成した後、Web パーツ ページを示します。</span><span class="sxs-lookup"><span data-stu-id="5986a-189">The following figure shows a Web Part page after it is just created.</span></span>  
  
         <span data-ttu-id="5986a-190">![空の Web パーツ ページ](../../adapters-and-accelerators/adapter-siebel/media/1fa218f5-de81-43be-b1b1-c46de422f112.gif "1fa218f5-de81-43be-b1b1-c46de422f112")</span><span class="sxs-lookup"><span data-stu-id="5986a-190">![Empty Web Part page](../../adapters-and-accelerators/adapter-siebel/media/1fa218f5-de81-43be-b1b1-c46de422f112.gif "1fa218f5-de81-43be-b1b1-c46de422f112")</span></span>  
  
     <span data-ttu-id="5986a-191">このページを別の Web パーツを追加する必要があります。</span><span class="sxs-lookup"><span data-stu-id="5986a-191">You must now add the different Web Parts to this page.</span></span>  
  
### <a name="adding-a-business-data-list-web-part"></a><span data-ttu-id="5986a-192">ビジネス データ一覧 Web パーツを追加します。</span><span class="sxs-lookup"><span data-stu-id="5986a-192">Adding a Business Data List Web Part</span></span>  
 <span data-ttu-id="5986a-193">ビジネス データ一覧 Web パーツを Web パーツ ページに追加する必要があります。</span><span class="sxs-lookup"><span data-stu-id="5986a-193">You must now add a Business Data List Web Part to the Web Part page.</span></span> <span data-ttu-id="5986a-194">この Web パーツを使用して、検索式を使用してアカウントのビジネス コンポーネントは照会します。</span><span class="sxs-lookup"><span data-stu-id="5986a-194">Using this Web Part, you will query the Account business component using a search expression.</span></span> <span data-ttu-id="5986a-195">この Web パーツは、ビジネス データ カタログ定義エディターで作成した Finder メソッド インスタンス (QueryAccount) に対応します。</span><span class="sxs-lookup"><span data-stu-id="5986a-195">This Web Part corresponds to the Finder method instance (QueryAccount) you created in the Business Data Catalog Definition Editor.</span></span>  
  
##### <a name="to-add-a-business-data-list-web-part"></a><span data-ttu-id="5986a-196">ビジネス データ一覧 Web パーツを追加するには</span><span class="sxs-lookup"><span data-stu-id="5986a-196">To add a Business Data List Web Part</span></span>  
  
1.  <span data-ttu-id="5986a-197">**Siebel アカウント** ページの 、**ヘッダー**セクションで、 **Web パーツの追加**です。</span><span class="sxs-lookup"><span data-stu-id="5986a-197">In the **Siebel Account** page, in the **Header** section, click **Add a Web Part**.</span></span>  
  
2.  <span data-ttu-id="5986a-198">**Web パーツの追加** ダイアログ ボックスで、**ビジネス データ** セクションで、選択、**ビジネス データ一覧**チェック ボックスをクリックして**追加**です。</span><span class="sxs-lookup"><span data-stu-id="5986a-198">In the **Add Web Parts** dialog box, in the **Business Data** section, select the **Business Data List** check box, and then click **Add**.</span></span>  
  
     <span data-ttu-id="5986a-199">![ビジネス データ Web パーツを作成するオプションを](../../adapters-and-accelerators/adapter-oracle-ebs/media/ae7c952c-1592-495f-9452-c1bffd44421c.gif "ae7c952c-1592-495f-9452-c1bffd44421c")</span><span class="sxs-lookup"><span data-stu-id="5986a-199">![Options to create a business data Web Part](../../adapters-and-accelerators/adapter-oracle-ebs/media/ae7c952c-1592-495f-9452-c1bffd44421c.gif "ae7c952c-1592-495f-9452-c1bffd44421c")</span></span>  
  
3.  <span data-ttu-id="5986a-200">新しく追加されたビジネス データ一覧 Web パーツ、クリックして、**ツール ウィンドウを開いて**リンクします。</span><span class="sxs-lookup"><span data-stu-id="5986a-200">In the newly added Business Data List Web Part, click the **Open the tool pane** link.</span></span>  
  
     <span data-ttu-id="5986a-201">![Web パーツのツール ウィンドウを開いて](../../adapters-and-accelerators/adapter-oracle-ebs/media/4e7a1cb1-69dc-4e0d-a211-6a217dc4a549.gif "4e7a1cb1-69dc-4e0d-a211-6a217dc4a549")</span><span class="sxs-lookup"><span data-stu-id="5986a-201">![Open the tool pane for Web Part](../../adapters-and-accelerators/adapter-oracle-ebs/media/4e7a1cb1-69dc-4e0d-a211-6a217dc4a549.gif "4e7a1cb1-69dc-4e0d-a211-6a217dc4a549")</span></span>  
  
4.  <span data-ttu-id="5986a-202">ビジネス データ一覧のツール ウィンドウは、右側のウィンドウで開きます。</span><span class="sxs-lookup"><span data-stu-id="5986a-202">The Business Data List tool pane opens in the right pane.</span></span> <span data-ttu-id="5986a-203">**ビジネス データ一覧** セクションの**型**フィールドで、をクリックして、**参照**ボタンをクリックします。</span><span class="sxs-lookup"><span data-stu-id="5986a-203">In the **Business Data List** section, for the **Type** field, click the **Browse** button.</span></span>  
  
     <span data-ttu-id="5986a-204">![ビジネス データ一覧のツール ウィンドウ](../../adapters-and-accelerators/adapter-siebel/media/3b6e1576-03ce-4fc8-bf5a-7b414ef4408c.gif "3b6e1576-03ce-4fc8-bf5a-7b414ef4408c")</span><span class="sxs-lookup"><span data-stu-id="5986a-204">![Business Data List tool pane](../../adapters-and-accelerators/adapter-siebel/media/3b6e1576-03ce-4fc8-bf5a-7b414ef4408c.gif "3b6e1576-03ce-4fc8-bf5a-7b414ef4408c")</span></span>  
  
5.  <span data-ttu-id="5986a-205">**ビジネス データの種類の選択**ダイアログ ボックスで、 **Siebel_Account_Instance**クリックしてアプリケーションでは、 **OK**です。</span><span class="sxs-lookup"><span data-stu-id="5986a-205">In the **Business Data Type Picker** dialog box, select the **Siebel_Account_Instance** application, and then click **OK**.</span></span>  
  
     <span data-ttu-id="5986a-206">![アプリケーション インスタンスの選択](../../adapters-and-accelerators/adapter-siebel/media/a658d06a-83a8-4e4b-9451-ce58e7ac3632.gif "a658d06a-83a8-4e4b-9451-ce58e7ac3632")</span><span class="sxs-lookup"><span data-stu-id="5986a-206">![Select the application instance](../../adapters-and-accelerators/adapter-siebel/media/a658d06a-83a8-4e4b-9451-ce58e7ac3632.gif "a658d06a-83a8-4e4b-9451-ce58e7ac3632")</span></span>  
  
6.  <span data-ttu-id="5986a-207">展開、**外観**ノード、および、**タイトル**フィールドに、Web パーツのタイトルを指定します。</span><span class="sxs-lookup"><span data-stu-id="5986a-207">Expand the **Appearance** node, and in the **Title** field, specify a title for the Web Part.</span></span> <span data-ttu-id="5986a-208">この Web パーツを指定する**アカウント一覧**です。</span><span class="sxs-lookup"><span data-stu-id="5986a-208">For this Web Part, specify **Account List**.</span></span>  
  
7.  <span data-ttu-id="5986a-209">ビジネス データ一覧のツール ウィンドウで、をクリックして**適用**、クリックして**OK**です。</span><span class="sxs-lookup"><span data-stu-id="5986a-209">In the Business Data List tool pane, click **Apply**, and then click **OK**.</span></span> <span data-ttu-id="5986a-210">ビジネス データ一覧 Web パーツは、次のようになります。</span><span class="sxs-lookup"><span data-stu-id="5986a-210">The Business Data List Web Part now looks like the following:</span></span>  
  
     <span data-ttu-id="5986a-211">![ビジネス データ一覧 Web パーツ](../../adapters-and-accelerators/adapter-siebel/media/06dbb84a-38c3-4ece-b981-5aa7471909ed.gif "06dbb84a-38c3-4ece-b981-5aa7471909ed")</span><span class="sxs-lookup"><span data-stu-id="5986a-211">![Business Data List Web Part](../../adapters-and-accelerators/adapter-siebel/media/06dbb84a-38c3-4ece-b981-5aa7471909ed.gif "06dbb84a-38c3-4ece-b981-5aa7471909ed")</span></span>  
  
    > [!NOTE]
    >  <span data-ttu-id="5986a-212">パラメーターの列の順序を変更することもできます。</span><span class="sxs-lookup"><span data-stu-id="5986a-212">You can also change the order in which the parameter columns appear.</span></span> <span data-ttu-id="5986a-213">これを行う をクリックして、**ビューの編集**Web パーツの右上隅にあるリンクします。</span><span class="sxs-lookup"><span data-stu-id="5986a-213">You can do so by clicking the **Edit View** link towards the right corner of the Web Part.</span></span>  
  
8.  <span data-ttu-id="5986a-214">をクリックして**編集モードの終了**ページの右上隅にあるからです。</span><span class="sxs-lookup"><span data-stu-id="5986a-214">Click **Exit Edit Mode** from the top right corner of the page.</span></span>  
  
## <a name="next-steps"></a><span data-ttu-id="5986a-215">次の手順</span><span class="sxs-lookup"><span data-stu-id="5986a-215">Next Steps</span></span>  
 <span data-ttu-id="5986a-216">Siebel システムからデータを取得することによって、SharePoint アプリケーションをテストします。</span><span class="sxs-lookup"><span data-stu-id="5986a-216">Test the SharePoint application by retrieving data from a Siebel system.</span></span> <span data-ttu-id="5986a-217">参照してください[手順 4: SharePoint アプリケーションをテスト](../../adapters-and-accelerators/adapter-oracle-ebs/step-4-test-your-sharepoint-application.md)です。</span><span class="sxs-lookup"><span data-stu-id="5986a-217">See [Step 4: Test Your SharePoint Application](../../adapters-and-accelerators/adapter-oracle-ebs/step-4-test-your-sharepoint-application.md).</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="5986a-218">参照</span><span class="sxs-lookup"><span data-stu-id="5986a-218">See Also</span></span>  
 [<span data-ttu-id="5986a-219">チュートリアル 1: SharePoint サイト上の Siebel システムからのデータの表示</span><span class="sxs-lookup"><span data-stu-id="5986a-219">Tutorial 1: Presenting Data From a Siebel System on a SharePoint Site</span></span>](../../adapters-and-accelerators/adapter-siebel/tutorial-1-presenting-data-from-a-siebel-system-on-a-sharepoint-site.md)