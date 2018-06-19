---
title: '手順 3: SAP からデータを取得する SharePoint アプリケーションの作成 |Microsoft ドキュメント'
ms.custom: ''
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: ''
ms.suite: ''
ms.tgt_pltfrm: ''
ms.topic: article
helpviewer_keywords:
- SSO application, creating an
- Business Data Catalog Definition Editor
- application definition file, importing
- Web Part
- SSP
- Web Part page, creating a
- Shared Services Provider, creating a
ms.assetid: 7158caec-9dc0-477c-9db3-179e634e5196
caps.latest.revision: 11
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: 879a4b48da7645471e53db357f7c0a6260117f99
ms.sourcegitcommit: cb908c540d8f1a692d01dc8f313e16cb4b4e696d
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 09/20/2017
ms.locfileid: "22219538"
---
# <a name="step-3-create-a-sharepoint-application-to-retrieve-data-from-sap"></a><span data-ttu-id="d52e3-102">手順 3: SAP からデータを取得する SharePoint アプリケーションを作成します。</span><span class="sxs-lookup"><span data-stu-id="d52e3-102">Step 3: Create a SharePoint Application to Retrieve Data from SAP</span></span>
<span data-ttu-id="d52e3-103">![手順 4 の 3](../../adapters-and-accelerators/adapter-oracle-ebs/media/step-3of4.gif "Step_3of4")</span><span class="sxs-lookup"><span data-stu-id="d52e3-103">![Step 3 of 4](../../adapters-and-accelerators/adapter-oracle-ebs/media/step-3of4.gif "Step_3of4")</span></span>  
  
 <span data-ttu-id="d52e3-104">**所要時間:** 15 分</span><span class="sxs-lookup"><span data-stu-id="d52e3-104">**Time to complete:** 15 minutes</span></span>  
  
 <span data-ttu-id="d52e3-105">**目標:** 今すぐビジネス データ カタログ定義エディター ツールを使用して作成したアプリケーション定義ファイルを実行し、Microsoft Office SharePoint Server にインポートする必要があります。</span><span class="sxs-lookup"><span data-stu-id="d52e3-105">**Objective:** You must now take the application definition file that you created by using the Business Data Catalog Definition Editor tool, and import it into Microsoft Office SharePoint Server.</span></span>  
  
## <a name="prerequisites"></a><span data-ttu-id="d52e3-106">前提条件</span><span class="sxs-lookup"><span data-stu-id="d52e3-106">Prerequisites</span></span>  
  
-   <span data-ttu-id="d52e3-107">必要がありますがファイルを作成したアプリケーションの定義」の説明に従って[手順 2: SAP 成果物のため、アプリケーション定義ファイルを作成する](../../adapters-and-accelerators/adapter-sap/step-2-create-an-application-definition-file-for-the-sap-artifacts.md)です。</span><span class="sxs-lookup"><span data-stu-id="d52e3-107">You should have created an application definition file as described in [Step 2: Create an Application Definition File for the SAP Artifacts](../../adapters-and-accelerators/adapter-sap/step-2-create-an-application-definition-file-for-the-sap-artifacts.md).</span></span>  
  
-   <span data-ttu-id="d52e3-108">Microsoft シングル サインオン サービスを実行する必要があります。</span><span class="sxs-lookup"><span data-stu-id="d52e3-108">The Microsoft Single Sign-on service must be running.</span></span>  
  
## <a name="how-to-create-a-sharepoint-application"></a><span data-ttu-id="d52e3-109">SharePoint アプリケーションを作成する方法</span><span class="sxs-lookup"><span data-stu-id="d52e3-109">How to Create a SharePoint Application</span></span>  
 <span data-ttu-id="d52e3-110">SharePoint アプリケーションを作成するには、次の手順が含まれます。</span><span class="sxs-lookup"><span data-stu-id="d52e3-110">Creating a SharePoint application involves the following steps:</span></span>  
  
-   <span data-ttu-id="d52e3-111">SharePoint でのシングル サインオン (SSO) アプリケーションを作成します。</span><span class="sxs-lookup"><span data-stu-id="d52e3-111">Create a single sign-on (SSO) application in SharePoint</span></span>  
  
-   <span data-ttu-id="d52e3-112">共有サービス プロバイダーを作成します。</span><span class="sxs-lookup"><span data-stu-id="d52e3-112">Create a Shared Services provider</span></span>  
  
-   <span data-ttu-id="d52e3-113">アプリケーション定義ファイルをインポートします。</span><span class="sxs-lookup"><span data-stu-id="d52e3-113">Import the application definition file</span></span>  
  
-   <span data-ttu-id="d52e3-114">Web パーツ ページを作成し、Web パーツを追加</span><span class="sxs-lookup"><span data-stu-id="d52e3-114">Create a Web Part page, and add Web Parts</span></span>  
  
 <span data-ttu-id="d52e3-115">このトピックでは、次の手順を実行する方法を示します。</span><span class="sxs-lookup"><span data-stu-id="d52e3-115">This topic demonstrates how to perform these steps.</span></span>  
  
## <a name="creating-an-sso-application-in-sharepoint"></a><span data-ttu-id="d52e3-116">SharePoint での SSO アプリケーションの作成</span><span class="sxs-lookup"><span data-stu-id="d52e3-116">Creating an SSO Application in SharePoint</span></span>  
 <span data-ttu-id="d52e3-117">SharePoint アプリケーションから SAP システムでデータにアクセスするには、SAP のユーザーに、SharePoint ユーザーにマップする SSO アプリケーションを設定する必要があります。</span><span class="sxs-lookup"><span data-stu-id="d52e3-117">To access the data in an SAP system from a SharePoint application, you must set up an SSO application that maps a SharePoint user to an SAP user.</span></span> <span data-ttu-id="d52e3-118">SharePoint で SSO アプリケーションを作成するには、次の手順が含まれます。</span><span class="sxs-lookup"><span data-stu-id="d52e3-118">Creating an SSO application in SharePoint involves the following steps:</span></span>  
  
1.  <span data-ttu-id="d52e3-119">**シングル サインオンの設定をサーバー管理**です。</span><span class="sxs-lookup"><span data-stu-id="d52e3-119">**Manage server settings for single sign-on**.</span></span> <span data-ttu-id="d52e3-120">このステップでは、管理、シングル サインオン サービスを設定したりできるユーザー アカウントを指定します。</span><span class="sxs-lookup"><span data-stu-id="d52e3-120">In this step, you specify a user account that can manage and set up the single sign-on service.</span></span> <span data-ttu-id="d52e3-121">サーバー設定の管理 ページで、これを行うことができます。</span><span class="sxs-lookup"><span data-stu-id="d52e3-121">You can do so on the Manage Server Settings page.</span></span> <span data-ttu-id="d52e3-122">このオプションを指定する場合は、SharePoint サーバーの全体管理コンソールで実行できます。</span><span class="sxs-lookup"><span data-stu-id="d52e3-122">This option is available from the SharePoint Central Administration console.</span></span> <span data-ttu-id="d52e3-123">この手順の詳細についてで「構成に対するシングル サインオン - Office SharePoint Server 2007」セクションを参照してください[http://go.microsoft.com/fwlink/?LinkId=105291](http://go.microsoft.com/fwlink/?LinkId=105291)です。</span><span class="sxs-lookup"><span data-stu-id="d52e3-123">For more information about this step, refer to the “Configure Single Sign-On for Office SharePoint Server 2007” section at [http://go.microsoft.com/fwlink/?LinkId=105291](http://go.microsoft.com/fwlink/?LinkId=105291).</span></span>  
  
2.  <span data-ttu-id="d52e3-124">**エンタープライズ アプリケーション定義の設定を管理**です。</span><span class="sxs-lookup"><span data-stu-id="d52e3-124">**Manage settings for enterprise application definitions**.</span></span> <span data-ttu-id="d52e3-125">このステップでは、エンタープライズ アプリケーション定義の設定を構成します。</span><span class="sxs-lookup"><span data-stu-id="d52e3-125">In this step, you configure the settings for the enterprise application definition.</span></span> <span data-ttu-id="d52e3-126">エンタープライズ アプリケーション定義 ページの設定の管理から行うことができます。</span><span class="sxs-lookup"><span data-stu-id="d52e3-126">You can do so from the Manage Settings for Enterprise Application Definitions page.</span></span> <span data-ttu-id="d52e3-127">このオプションを指定する場合は、SharePoint サーバーの全体管理コンソールで実行できます。</span><span class="sxs-lookup"><span data-stu-id="d52e3-127">This option is available from the SharePoint Central Administration console.</span></span>  
  
    1.  <span data-ttu-id="d52e3-128">サーバーの全体管理で、上部のナビゲーション バーで、をクリックして**Operations**です。</span><span class="sxs-lookup"><span data-stu-id="d52e3-128">On Central Administration, on the top navigation bar, click **Operations**.</span></span>  
  
    2.  <span data-ttu-id="d52e3-129">[操作] ページで、**セキュリティの構成**セクションで、をクリックして**でのシングル サインオンの設定を管理**です。</span><span class="sxs-lookup"><span data-stu-id="d52e3-129">On the Operations page, in the **Security Configuration** section, click  **Manage settings for single sign-on**.</span></span>  
  
    3.  <span data-ttu-id="d52e3-130">シングル サインオン] ページの設定の管理で、**エンタープライズ アプリケーション定義の設定**セクションで、[**企業アプリケーション定義の設定を管理**です。</span><span class="sxs-lookup"><span data-stu-id="d52e3-130">On the Manage Settings for Single Sign-On page, in the **Enterprise Application Definition Settings** section, click **Manage settings for enterprise application definitions**.</span></span>  
  
    4.  <span data-ttu-id="d52e3-131">[エンタープライズ アプリケーション定義の管理] ページで、値を指定して、**表示名**、**アプリケーション名**、および**連絡先の電子メール アドレス**フィールドです。</span><span class="sxs-lookup"><span data-stu-id="d52e3-131">On the Manage Enterprise Application Definitions page, provide values for the **Display name**, **Application name**, and the **Contact e-mail address** fields.</span></span>  
  
        > [!IMPORTANT]
        >  <span data-ttu-id="d52e3-132">**アプリケーション名**フィールドに、指定した同じ SSO アプリケーション名を指定するかどうかを確認、 **SecondarySsoApplicationId**として、アプリケーション定義ファイルの作成中に変数説明されている[手順 2: SAP 成果物のため、アプリケーション定義ファイルを作成する](../../adapters-and-accelerators/adapter-sap/step-2-create-an-application-definition-file-for-the-sap-artifacts.md)です。</span><span class="sxs-lookup"><span data-stu-id="d52e3-132">For the **Application name** field, make sure you specify the same SSO application name that you specified for the **SecondarySsoApplicationId** variable while creating the application definition file, as described in [Step 2: Create an Application Definition File for the SAP Artifacts](../../adapters-and-accelerators/adapter-sap/step-2-create-an-application-definition-file-for-the-sap-artifacts.md).</span></span>  
  
    5.  <span data-ttu-id="d52e3-133">既定では、他のフィールドのままにし、をクリックして**OK**です。</span><span class="sxs-lookup"><span data-stu-id="d52e3-133">Leave the other fields as default, and click **OK**.</span></span>  
  
3.  <span data-ttu-id="d52e3-134">**エンタープライズ アプリケーション定義のアカウント情報を管理する**です。</span><span class="sxs-lookup"><span data-stu-id="d52e3-134">**Manage account information for enterprise application definitions**.</span></span> <span data-ttu-id="d52e3-135">このステップでは SharePoint からエンタープライズ アプリケーションに接続するには、個々 のユーザーまたはグループを有効にします。</span><span class="sxs-lookup"><span data-stu-id="d52e3-135">In this step, you enable individual users or groups to connect to an enterprise application from SharePoint.</span></span> <span data-ttu-id="d52e3-136">基本的には、この手順でマップする個々 のユーザーまたはグループのユーザーに LOB システムに。</span><span class="sxs-lookup"><span data-stu-id="d52e3-136">Essentially, in this step you map an individual user or group to a user in the LOB system.</span></span> <span data-ttu-id="d52e3-137">また、LOB システムへの接続に資格情報を指定します。</span><span class="sxs-lookup"><span data-stu-id="d52e3-137">You also specify the credentials to connect to the LOB system.</span></span> <span data-ttu-id="d52e3-138">エンタープライズ アプリケーション定義 ページのアカウント情報の管理から行うことができます。</span><span class="sxs-lookup"><span data-stu-id="d52e3-138">You can do so from the Manage Account Information for Enterprise Application Definitions page.</span></span> <span data-ttu-id="d52e3-139">このオプションを指定する場合は、SharePoint サーバーの全体管理コンソールで実行できます。</span><span class="sxs-lookup"><span data-stu-id="d52e3-139">This option is available from the SharePoint Central Administration console.</span></span> <span data-ttu-id="d52e3-140">この手順の詳細についてで「エンタープライズ アプリケーション定義のアカウント情報の管理」セクションを参照してください[http://go.microsoft.com/fwlink/?LinkId=105291](http://go.microsoft.com/fwlink/?LinkId=105291)です。</span><span class="sxs-lookup"><span data-stu-id="d52e3-140">For more information about this step, refer to the “Manage account information for an enterprise application definition” section at [http://go.microsoft.com/fwlink/?LinkId=105291](http://go.microsoft.com/fwlink/?LinkId=105291).</span></span>  
  
## <a name="creating-a-shared-services-provider"></a><span data-ttu-id="d52e3-141">共有サービス プロバイダーを作成します。</span><span class="sxs-lookup"><span data-stu-id="d52e3-141">Creating a Shared Services Provider</span></span>  
 <span data-ttu-id="d52e3-142">共有サービス プロバイダーは、共有サービスとその関連リソースの論理的なグループです。</span><span class="sxs-lookup"><span data-stu-id="d52e3-142">A Shared Service Provider is a logical grouping of shared services and their supporting resources.</span></span> <span data-ttu-id="d52e3-143">SSP は、SharePoint サーバーの全体管理コンソールを使用して作成できます。</span><span class="sxs-lookup"><span data-stu-id="d52e3-143">You can create an SSP by using the SharePoint Central Administration console.</span></span>  
  
 <span data-ttu-id="d52e3-144">SSP を作成するときに、Web サイトを定義する必要があります。</span><span class="sxs-lookup"><span data-stu-id="d52e3-144">You must define a Web site when creating an SSP.</span></span> <span data-ttu-id="d52e3-145">ポート番号と、サイト アドレスを作成することに注意してください。</span><span class="sxs-lookup"><span data-stu-id="d52e3-145">Remember the port number and the site address that you create.</span></span> <span data-ttu-id="d52e3-146">このサイトには、ビジネス データ カタログ アプリケーション定義をインポートします。</span><span class="sxs-lookup"><span data-stu-id="d52e3-146">You will import the Business Data Catalog application definition to this site.</span></span>  
  
 <span data-ttu-id="d52e3-147">SSP の作成の詳細については、次を参照してください。"章の概要: を作成し、共有サービス プロバイダーを構成する"で[http://go.microsoft.com/fwlink/?LinkId=105119](http://go.microsoft.com/fwlink/?LinkId=105119)です。</span><span class="sxs-lookup"><span data-stu-id="d52e3-147">For more information about creating an SSP, see "Chapter overview: Create and configure Shared Services Providers" at [http://go.microsoft.com/fwlink/?LinkId=105119](http://go.microsoft.com/fwlink/?LinkId=105119).</span></span>  
  
## <a name="importing-the-application-definition-file"></a><span data-ttu-id="d52e3-148">アプリケーション定義ファイルのインポート</span><span class="sxs-lookup"><span data-stu-id="d52e3-148">Importing the Application Definition File</span></span>  
 <span data-ttu-id="d52e3-149">SSP にアプリケーション定義ファイルをインポートする必要があります。</span><span class="sxs-lookup"><span data-stu-id="d52e3-149">You must now import the application definition file into the SSP.</span></span>  
  
#### <a name="to-import-the-application-definition-file"></a><span data-ttu-id="d52e3-150">アプリケーション定義ファイルをインポートするには</span><span class="sxs-lookup"><span data-stu-id="d52e3-150">To import the application definition file</span></span>  
  
1.  <span data-ttu-id="d52e3-151">SharePoint 3.0 サーバーの全体管理を開始します。</span><span class="sxs-lookup"><span data-stu-id="d52e3-151">Start SharePoint 3.0 Central Administration.</span></span> <span data-ttu-id="d52e3-152">をクリックして**開始**、 をポイント**すべてのプログラム**、 をポイント**Microsoft Office Server**、クリックして**SharePoint 3.0 サーバーの全体管理**.</span><span class="sxs-lookup"><span data-stu-id="d52e3-152">Click **Start**, point to **All Programs**, point to **Microsoft Office Server**, and then click **SharePoint 3.0 Central Administration**.</span></span>  
  
2.  <span data-ttu-id="d52e3-153">左側のナビゲーション ウィンドウで、アプリケーション定義をインポートする SSP の名前をクリックします。</span><span class="sxs-lookup"><span data-stu-id="d52e3-153">In the left navigation pane, click the name of the SSP to which you want to import the application definition.</span></span>  
  
3.  <span data-ttu-id="d52e3-154">**ビジネス データ カタログ**セクションで、**アプリケーション定義のインポート**です。</span><span class="sxs-lookup"><span data-stu-id="d52e3-154">In the **Business Data Catalog** section, click **Import application definition**.</span></span>  
  
4.  <span data-ttu-id="d52e3-155">Customer_Orders.xml、[参照] を開くと、アプリケーション定義のインポート ページで、ファイルを選択し、をクリックして**開く**です。</span><span class="sxs-lookup"><span data-stu-id="d52e3-155">On the Import Application Definition page that opens, browse to Customer_Orders.xml, select the file, and then click **Open**.</span></span>  
  
5.  <span data-ttu-id="d52e3-156">**[インポート]** をクリックします。</span><span class="sxs-lookup"><span data-stu-id="d52e3-156">Click **Import**.</span></span>  
  
6.  <span data-ttu-id="d52e3-157">**[OK]** をクリックします。</span><span class="sxs-lookup"><span data-stu-id="d52e3-157">Click **OK**.</span></span>  
  
     <span data-ttu-id="d52e3-158">アプリケーションをインポートした後に移動して、アプリケーションを表示することができます、**ビュー アプリケーション**リンクします。</span><span class="sxs-lookup"><span data-stu-id="d52e3-158">After importing the application, you can view your application by going to the **View Applications** link.</span></span> <span data-ttu-id="d52e3-159">アプリケーション内のエンティティを表示するのには、アプリケーション名をクリックします。</span><span class="sxs-lookup"><span data-stu-id="d52e3-159">Click the application name to see the entities in the application.</span></span>  
  
## <a name="creating-web-parts"></a><span data-ttu-id="d52e3-160">Web パーツを作成します。</span><span class="sxs-lookup"><span data-stu-id="d52e3-160">Creating Web Parts</span></span>  
 <span data-ttu-id="d52e3-161">SharePoint サイトの表示および SAP システムから抽出するビジネス データを管理する Web パーツを作成する必要があります。</span><span class="sxs-lookup"><span data-stu-id="d52e3-161">You must now create Web Parts in your SharePoint site to view and manage the business data that will be extracted from the SAP system.</span></span> <span data-ttu-id="d52e3-162">Web パーツは、任意の種類の分析、コラボレーションなど、Web ベースの情報を含むおよびデータベース情報が使用できる再利用可能なコンポーネントです。</span><span class="sxs-lookup"><span data-stu-id="d52e3-162">Web Parts are reusable components that can contain any kind of Web-based information, including analytical, collaborative, and database information.</span></span>  
  
 <span data-ttu-id="d52e3-163">このチュートリアルでは、Web パーツは、ビジネス データ カタログ定義エディターで作成されたメソッドのインスタンスに対して作成されます。</span><span class="sxs-lookup"><span data-stu-id="d52e3-163">In this tutorial, Web Parts are created for the method instances that were created in the Business Data Catalog Definition Editor.</span></span> <span data-ttu-id="d52e3-164">Office SharePoint Server では、特定の使用の Web パーツのさまざまな種類を提供します。</span><span class="sxs-lookup"><span data-stu-id="d52e3-164">Office SharePoint Server provides different kinds of Web Parts for specific use.</span></span> <span data-ttu-id="d52e3-165">次の Web パーツは、ここで使用されます。</span><span class="sxs-lookup"><span data-stu-id="d52e3-165">The following Web Parts are used here:</span></span>  
  
-   <span data-ttu-id="d52e3-166">**ビジネス データ一覧**用の Web パーツ、 **Finder**メソッド インスタンス。</span><span class="sxs-lookup"><span data-stu-id="d52e3-166">**Business Data List** Web Part for the **Finder** method instance.</span></span> <span data-ttu-id="d52e3-167">この Web パーツでは、SAP システムから顧客の一覧を取得する検索文字列を指定することができます。</span><span class="sxs-lookup"><span data-stu-id="d52e3-167">This Web Part enables you to specify a search expression to retrieve a list of customers from the SAP system.</span></span> <span data-ttu-id="d52e3-168">このチュートリアルでは、これには、検索の顧客の Web パーツを呼び出されます。</span><span class="sxs-lookup"><span data-stu-id="d52e3-168">For this tutorial, this is called the Search Customers Web Part.</span></span>  
  
-   <span data-ttu-id="d52e3-169">**ビジネス データ項目**用の Web パーツ、 **Specific Finder**メソッド インスタンス。</span><span class="sxs-lookup"><span data-stu-id="d52e3-169">**Business Data Item** Web Part for the **Specific Finder** method instance.</span></span> <span data-ttu-id="d52e3-170">この Web パーツは、検索の顧客の Web パーツから選択した特定の顧客の詳細を表示します。</span><span class="sxs-lookup"><span data-stu-id="d52e3-170">This Web Part presents the details for a specific customer that you select from the Search Customers Web Part.</span></span> <span data-ttu-id="d52e3-171">この Web パーツは、検索の顧客の Web パーツにマップされます。</span><span class="sxs-lookup"><span data-stu-id="d52e3-171">This Web Part is mapped to the Search Customer Web Part.</span></span>  <span data-ttu-id="d52e3-172">このチュートリアルでは、これには、顧客の詳細の Web パーツを呼び出されます。</span><span class="sxs-lookup"><span data-stu-id="d52e3-172">For this tutorial, this is called the Customer Details Web Part.</span></span>  
  
-   <span data-ttu-id="d52e3-173">**ビジネス データ関連一覧**用の Web パーツ、**アソシエーション**メソッド インスタンス。</span><span class="sxs-lookup"><span data-stu-id="d52e3-173">**Business Data Related List** Web Part for the **Association** method instance.</span></span> <span data-ttu-id="d52e3-174">この Web パーツには、検索の顧客の Web パーツから選択した特定の顧客の販売注文が一覧表示します。</span><span class="sxs-lookup"><span data-stu-id="d52e3-174">This Web Part lists the sales orders for a specific customer that you select from the Search Customers Web Part.</span></span> <span data-ttu-id="d52e3-175">この Web パーツは、検索の顧客の Web パーツに関連付けられます。</span><span class="sxs-lookup"><span data-stu-id="d52e3-175">This Web Part is associated with the Search Customer Web Part.</span></span>  <span data-ttu-id="d52e3-176">このチュートリアルでは、これには、販売注文の詳細の Web パーツを呼び出されます。</span><span class="sxs-lookup"><span data-stu-id="d52e3-176">For this tutorial, this is called the Sales Order Details Web Part.</span></span>  
  
 <span data-ttu-id="d52e3-177">このセクションでは、これらの Web パーツを作成して、それらの間の関連付けを作成する手順を示します。</span><span class="sxs-lookup"><span data-stu-id="d52e3-177">This section provides instructions to create these Web Parts and to create associations between them.</span></span> <span data-ttu-id="d52e3-178">Web パーツの作成の詳細についてを参照してください「ビジネス データ リストのカスタマイズ、Web パーツ、およびサイト」で[http://go.microsoft.com/fwlink/?LinkId=104131](http://go.microsoft.com/fwlink/?LinkId=104131)です。</span><span class="sxs-lookup"><span data-stu-id="d52e3-178">For more information about creating Web Parts, see "Customize business data lists, Web Parts, and sites" at [http://go.microsoft.com/fwlink/?LinkId=104131](http://go.microsoft.com/fwlink/?LinkId=104131).</span></span>  
  
 <span data-ttu-id="d52e3-179">Web パーツは、1 つの Web パーツ ページに追加されます。</span><span class="sxs-lookup"><span data-stu-id="d52e3-179">The Web Parts will be added to a single Web Part page.</span></span> <span data-ttu-id="d52e3-180">Web パーツを追加する前に、Web パーツ ページを作成する必要があります。</span><span class="sxs-lookup"><span data-stu-id="d52e3-180">You must create a Web Part page before adding the Web Parts.</span></span> <span data-ttu-id="d52e3-181">このチュートリアルでは、この Web パーツ ページを Customer_SalesOrders と呼びます。</span><span class="sxs-lookup"><span data-stu-id="d52e3-181">For this tutorial, this Web Part page is called Customer_SalesOrders.</span></span>  
  
### <a name="creating-a-web-part-page"></a><span data-ttu-id="d52e3-182">Web パーツ ページを作成します。</span><span class="sxs-lookup"><span data-stu-id="d52e3-182">Creating a Web Part Page</span></span>  
 <span data-ttu-id="d52e3-183">このセクションでは、Web パーツ ページを作成する手順を説明します。</span><span class="sxs-lookup"><span data-stu-id="d52e3-183">This section provides instructions to create a Web Part page.</span></span>  
  
##### <a name="to-create-a-web-part-page"></a><span data-ttu-id="d52e3-184">Web パーツ ページを作成するには</span><span class="sxs-lookup"><span data-stu-id="d52e3-184">To create a Web Part page</span></span>  
  
1.  <span data-ttu-id="d52e3-185">SharePoint 3.0 サーバーの全体管理を開始します。</span><span class="sxs-lookup"><span data-stu-id="d52e3-185">Start SharePoint 3.0 Central Administration.</span></span> <span data-ttu-id="d52e3-186">をクリックして**開始**、 をポイント**すべてのプログラム**、 をポイント**Microsoft Office Server**、 をクリック**SharePoint 3.0 サーバーの全体管理**です。</span><span class="sxs-lookup"><span data-stu-id="d52e3-186">Click **Start**, point to **All Programs**, point to **Microsoft Office Server**, and click **SharePoint 3.0 Central Administration**.</span></span>  
  
2.  <span data-ttu-id="d52e3-187">左側のナビゲーション ウィンドウで、アプリケーション定義をインポートする SSP の名前をクリックします。</span><span class="sxs-lookup"><span data-stu-id="d52e3-187">In the left navigation pane, click the name of the SSP to which you want to import the application definition.</span></span>  
  
3.  <span data-ttu-id="d52e3-188">共有サービスの管理 ページの右上隅で、をクリックして**サイトの操作**、クリックして**作成**です。</span><span class="sxs-lookup"><span data-stu-id="d52e3-188">On the Shared Services Administration page, in the upper-right corner, click **Site Actions**, and then click **Create**.</span></span>  
  
     <span data-ttu-id="d52e3-189">![Web パーツを作成するにはメニュー](../../adapters-and-accelerators/adapter-oracle-ebs/media/a9872c3e-f823-4c47-a538-19242565d2e9.gif "a9872c3e-f823-4c47-a538-19242565d2e9")</span><span class="sxs-lookup"><span data-stu-id="d52e3-189">![Menu to create a web part](../../adapters-and-accelerators/adapter-oracle-ebs/media/a9872c3e-f823-4c47-a538-19242565d2e9.gif "a9872c3e-f823-4c47-a538-19242565d2e9")</span></span>  
  
4.  <span data-ttu-id="d52e3-190">作成 ページで、 **Web ページ**セクションで、 **Web パーツ ページ**です。</span><span class="sxs-lookup"><span data-stu-id="d52e3-190">On the Create page, in the **Web Pages** section, click **Web Part Page**.</span></span>  
  
5.  <span data-ttu-id="d52e3-191">新しい Web パーツ ページには、次の操作を行います。</span><span class="sxs-lookup"><span data-stu-id="d52e3-191">On the New Web Part page, do the following:</span></span>  
  
    1.  <span data-ttu-id="d52e3-192">**名前**フィールドに、ページの名前を入力します。</span><span class="sxs-lookup"><span data-stu-id="d52e3-192">In the **Name** field, type a name for the page.</span></span> <span data-ttu-id="d52e3-193">このチュートリアルでは、名前を入力しますとして**Customer_SalesOrders**です。</span><span class="sxs-lookup"><span data-stu-id="d52e3-193">For this tutorial, type the name as **Customer_SalesOrders**.</span></span>  
  
    2.  <span data-ttu-id="d52e3-194">選択、**ファイルが既に存在する場合に上書き**チェック ボックスを作成する新しいページと同じ名前の古いページを上書きする場合。</span><span class="sxs-lookup"><span data-stu-id="d52e3-194">Select the **Overwrite if file already exists** check box, if you want to overwrite old pages with the same name as the new page you create.</span></span>  
  
    3.  <span data-ttu-id="d52e3-195">**レイアウト** セクションから、**レイアウト テンプレートを選択して**ボックスで、Web パーツ ページのレイアウトを選択します。</span><span class="sxs-lookup"><span data-stu-id="d52e3-195">In the **Layout** section, from the **Choose a Layout Template** box, select a layout for the Web Part page.</span></span> <span data-ttu-id="d52e3-196">このチュートリアルでは、次のように選択します。**ヘッダー、左の列、本文**です。</span><span class="sxs-lookup"><span data-stu-id="d52e3-196">For this tutorial, select **Header, Left Column, Body**.</span></span>  
  
    4.  <span data-ttu-id="d52e3-197">**保存場所**セクションで、**ドキュメント ライブラリ**一覧で、クリックして**フォーム テンプレート**です。</span><span class="sxs-lookup"><span data-stu-id="d52e3-197">In the **Save Location** section, in the **Document Library** list, click **Form Templates**.</span></span>  
  
    5.  <span data-ttu-id="d52e3-198">**[作成]** をクリックします。</span><span class="sxs-lookup"><span data-stu-id="d52e3-198">Click **Create**.</span></span> <span data-ttu-id="d52e3-199">次の図は、作成した後、Web パーツ ページを示します。</span><span class="sxs-lookup"><span data-stu-id="d52e3-199">The following figure shows a Web Part page after it is just created.</span></span>  
  
         <span data-ttu-id="d52e3-200">![空の Web パーツ ページ](../../adapters-and-accelerators/adapter-sap/media/6aa68c43-59df-47c4-95a6-453f7c668025.gif "6aa68c43-59df-47c4-95a6-453f7c668025")</span><span class="sxs-lookup"><span data-stu-id="d52e3-200">![Empty Web Part page](../../adapters-and-accelerators/adapter-sap/media/6aa68c43-59df-47c4-95a6-453f7c668025.gif "6aa68c43-59df-47c4-95a6-453f7c668025")</span></span>  
  
    6.  <span data-ttu-id="d52e3-201">このページを別の Web パーツを追加する必要があります。</span><span class="sxs-lookup"><span data-stu-id="d52e3-201">You must now add the different Web Parts to this page.</span></span>  
  
### <a name="adding-a-business-data-list-web-part"></a><span data-ttu-id="d52e3-202">ビジネス データ一覧 Web パーツを追加します。</span><span class="sxs-lookup"><span data-stu-id="d52e3-202">Adding a Business Data List Web Part</span></span>  
 <span data-ttu-id="d52e3-203">ビジネス データ一覧 Web パーツを Web パーツ ページに追加する必要があります。</span><span class="sxs-lookup"><span data-stu-id="d52e3-203">You must now add a Business Data List Web Part to the Web Part page.</span></span> <span data-ttu-id="d52e3-204">この Web パーツを使用して、検索式に一致する SAP システムから顧客の一覧が取得されます。</span><span class="sxs-lookup"><span data-stu-id="d52e3-204">Using this Web Part you will retrieve a list of customers from the SAP system that matches a search expression.</span></span> <span data-ttu-id="d52e3-205">この Web パーツに対応する、 **Finder**メソッド インスタンス (*GetCustomerByName_Instance*) で、ビジネス データ カタログ定義エディターを作成しました。</span><span class="sxs-lookup"><span data-stu-id="d52e3-205">This Web Part corresponds to the **Finder** method instance (*GetCustomerByName_Instance*) that you created in the Business Data Catalog Definition Editor.</span></span>  
  
##### <a name="to-add-a-business-data-list-web-part"></a><span data-ttu-id="d52e3-206">ビジネス データ一覧 Web パーツを追加するには</span><span class="sxs-lookup"><span data-stu-id="d52e3-206">To add a Business Data List Web Part</span></span>  
  
1.  <span data-ttu-id="d52e3-207">Customer_SalesOrders ページで、、**ヘッダー**セクションで、 **Web パーツの追加**です。</span><span class="sxs-lookup"><span data-stu-id="d52e3-207">On the Customer_SalesOrders page, in the **Header** section, click **Add a Web Part**.</span></span>  
  
2.  <span data-ttu-id="d52e3-208">**Web パーツの追加** ダイアログ ボックスで、**ビジネス データ** セクションで、選択、**ビジネス データ一覧**チェック ボックスをクリックして**追加**です。</span><span class="sxs-lookup"><span data-stu-id="d52e3-208">In the **Add Web Parts** dialog box, in the **Business Data** section, select the **Business Data List** check box, and then click **Add**.</span></span>  
  
     <span data-ttu-id="d52e3-209">![ビジネス データ Web パーツを作成するオプションを](../../adapters-and-accelerators/adapter-oracle-ebs/media/ae7c952c-1592-495f-9452-c1bffd44421c.gif "ae7c952c-1592-495f-9452-c1bffd44421c")</span><span class="sxs-lookup"><span data-stu-id="d52e3-209">![Options to create a business data Web Part](../../adapters-and-accelerators/adapter-oracle-ebs/media/ae7c952c-1592-495f-9452-c1bffd44421c.gif "ae7c952c-1592-495f-9452-c1bffd44421c")</span></span>  
  
3.  <span data-ttu-id="d52e3-210">新しく追加されたビジネス データ一覧 Web パーツ、クリックして、**ツール ウィンドウを開いて**リンクします。</span><span class="sxs-lookup"><span data-stu-id="d52e3-210">In the newly added Business Data List Web Part, click the **Open the tool pane** link.</span></span>  
  
     <span data-ttu-id="d52e3-211">![Web パーツのツール ウィンドウを開いて](../../adapters-and-accelerators/adapter-oracle-ebs/media/4e7a1cb1-69dc-4e0d-a211-6a217dc4a549.gif "4e7a1cb1-69dc-4e0d-a211-6a217dc4a549")</span><span class="sxs-lookup"><span data-stu-id="d52e3-211">![Open the tool pane for Web Part](../../adapters-and-accelerators/adapter-oracle-ebs/media/4e7a1cb1-69dc-4e0d-a211-6a217dc4a549.gif "4e7a1cb1-69dc-4e0d-a211-6a217dc4a549")</span></span>  
  
4.  <span data-ttu-id="d52e3-212">ビジネス データ一覧のツール ウィンドウは、右側のウィンドウで開きます。</span><span class="sxs-lookup"><span data-stu-id="d52e3-212">The Business Data List tool pane opens in the right pane.</span></span> <span data-ttu-id="d52e3-213">**ビジネス データ一覧** セクションの**型**フィールドで、をクリックして、**参照**ボタンをクリックします。</span><span class="sxs-lookup"><span data-stu-id="d52e3-213">In the **Business Data List** section, for the **Type** field, click the **Browse** button.</span></span>  
  
     <span data-ttu-id="d52e3-214">![ビジネス データ一覧のツール ウィンドウ](../../adapters-and-accelerators/adapter-sap/media/580c58bf-bfc7-4d48-8c62-8ca4eee4ab48.gif "580c58bf-bfc7-4d48-8c62-8ca4eee4ab48")</span><span class="sxs-lookup"><span data-stu-id="d52e3-214">![Business Data List tool pane](../../adapters-and-accelerators/adapter-sap/media/580c58bf-bfc7-4d48-8c62-8ca4eee4ab48.gif "580c58bf-bfc7-4d48-8c62-8ca4eee4ab48")</span></span>  
  
5.  <span data-ttu-id="d52e3-215">**ビジネス データの種類の選択**ダイアログ ボックスで、 **Customer_Order_Instance**クリックしてアプリケーションでは、 **OK**です。</span><span class="sxs-lookup"><span data-stu-id="d52e3-215">In the **Business Data Type Picker** dialog box, select the **Customer_Order_Instance** application, and then click **OK**.</span></span>  
  
     <span data-ttu-id="d52e3-216">![アプリケーション インスタンスの選択](../../adapters-and-accelerators/adapter-sap/media/79967c27-9c76-4394-89bc-38c63649bdda.gif "79967c27-9c76-4394-89bc-38c63649bdda")</span><span class="sxs-lookup"><span data-stu-id="d52e3-216">![Select the application instance](../../adapters-and-accelerators/adapter-sap/media/79967c27-9c76-4394-89bc-38c63649bdda.gif "79967c27-9c76-4394-89bc-38c63649bdda")</span></span>  
  
6.  <span data-ttu-id="d52e3-217">展開、**外観**ノード、および、**タイトル**ボックスで、Web パーツのタイトルを入力します。</span><span class="sxs-lookup"><span data-stu-id="d52e3-217">Expand the **Appearance** node, and in the **Title** box, type a title for the Web Part.</span></span> <span data-ttu-id="d52e3-218">この Web パーツの次のように入力します。**顧客リスト**です。</span><span class="sxs-lookup"><span data-stu-id="d52e3-218">For this Web Part, type **Customer List**.</span></span>  
  
7.  <span data-ttu-id="d52e3-219">ビジネス データ一覧のツール ウィンドウで、をクリックして**適用**、クリックして**OK**です。</span><span class="sxs-lookup"><span data-stu-id="d52e3-219">In the Business Data List tool pane, click **Apply**, and then click **OK**.</span></span> <span data-ttu-id="d52e3-220">ビジネス データ一覧 Web パーツは、次のようになります。</span><span class="sxs-lookup"><span data-stu-id="d52e3-220">The Business Data List Web Part now looks like the following:</span></span>  
  
     <span data-ttu-id="d52e3-221">![ビジネス データ一覧 Web パーツ](../../adapters-and-accelerators/adapter-sap/media/185fb3f3-98b0-4efe-960d-91312912ad7d.gif "185fb3f3-98b0-4efe-960d-91312912ad7d")</span><span class="sxs-lookup"><span data-stu-id="d52e3-221">![Business Data List Web Part](../../adapters-and-accelerators/adapter-sap/media/185fb3f3-98b0-4efe-960d-91312912ad7d.gif "185fb3f3-98b0-4efe-960d-91312912ad7d")</span></span>  
  
8.  <span data-ttu-id="d52e3-222">Web パーツには、SD_RFC_CUSTOMER_GET RFC を実行することによって返されるフィールドが一覧表示します。</span><span class="sxs-lookup"><span data-stu-id="d52e3-222">The Web Part lists the fields that are returned by executing the SD_RFC_CUSTOMER_GET RFC.</span></span> <span data-ttu-id="d52e3-223">SharePoint ポータルに表示したくないフィールドを削除することができます。</span><span class="sxs-lookup"><span data-stu-id="d52e3-223">You can remove the fields that you do not want to display on the SharePoint portal.</span></span> <span data-ttu-id="d52e3-224">削除するには、フィールドをクリックして、**ビューの編集**Web パーツの右上隅にリンクします。</span><span class="sxs-lookup"><span data-stu-id="d52e3-224">To remove the fields, click the **Edit View** link in the upper-right corner of the Web Part.</span></span>  
  
9. <span data-ttu-id="d52e3-225">ビューの編集 ページの 列 セクションで、表示しない列に対して、チェック ボックスをオフにします。</span><span class="sxs-lookup"><span data-stu-id="d52e3-225">On the Edit View page, in the Columns section, clear the check boxes against the columns that you do not want to display.</span></span>  
  
     <span data-ttu-id="d52e3-226">![SharePoint 内の特定の列の表示](../../adapters-and-accelerators/adapter-sap/media/24213b67-aafe-4534-91a7-06bde7bcbf7c.gif "24213b67-aafe-4534-91a7-06bde7bcbf7c")</span><span class="sxs-lookup"><span data-stu-id="d52e3-226">![View specific columns in SharePoint](../../adapters-and-accelerators/adapter-sap/media/24213b67-aafe-4534-91a7-06bde7bcbf7c.gif "24213b67-aafe-4534-91a7-06bde7bcbf7c")</span></span>  
  
10. <span data-ttu-id="d52e3-227">**[OK]** をクリックします。</span><span class="sxs-lookup"><span data-stu-id="d52e3-227">Click **OK**.</span></span>  
  
### <a name="adding-a-business-data-item-web-part"></a><span data-ttu-id="d52e3-228">ビジネス データ項目の Web パーツを追加します。</span><span class="sxs-lookup"><span data-stu-id="d52e3-228">Adding a Business Data Item Web Part</span></span>  
 <span data-ttu-id="d52e3-229">ビジネス データ項目の Web パーツを Web パーツ ページに追加する必要があります。</span><span class="sxs-lookup"><span data-stu-id="d52e3-229">You must now add a Business Data Item Web Part to the Web Part page.</span></span> <span data-ttu-id="d52e3-230">この Web パーツは、先ほど作成したビジネス データ一覧 Web パーツに接続します。</span><span class="sxs-lookup"><span data-stu-id="d52e3-230">You will also connect this Web Part to the Business Data List Web Part that you just created.</span></span> <span data-ttu-id="d52e3-231">これにより、ビジネス データ一覧 Web パーツで選択した顧客の詳細を表示することができます。</span><span class="sxs-lookup"><span data-stu-id="d52e3-231">By doing so, you will be able to see the details for a customer that you select in the Business Data List Web Part.</span></span> <span data-ttu-id="d52e3-232">この Web パーツに対応する、 **Specific Finder**メソッド インスタンス (*GetCustomerByNumber_Instance*) で、ビジネス データ カタログ定義エディターを作成しました。</span><span class="sxs-lookup"><span data-stu-id="d52e3-232">This Web Part corresponds to the **Specific Finder** method instance (*GetCustomerByNumber_Instance*) that you created in the Business Data Catalog Definition Editor.</span></span>  
  
##### <a name="to-add-a-business-data-item-web-part"></a><span data-ttu-id="d52e3-233">ビジネス データ項目の Web パーツを追加するには</span><span class="sxs-lookup"><span data-stu-id="d52e3-233">To add a Business Data Item Web Part</span></span>  
  
1.  <span data-ttu-id="d52e3-234">Customer_SalesOrders ページの右上隅で、をクリックして**サイトの操作**、クリックして**ページの編集**です。</span><span class="sxs-lookup"><span data-stu-id="d52e3-234">On the Customer_SalesOrders page, in the upper-right corner, click **Site Actions**, and then click **Edit Page**.</span></span>  
  
2.  <span data-ttu-id="d52e3-235">Customer_SalesOrders] ページで、**左列**セクションで、[ **Web パーツの追加**です。</span><span class="sxs-lookup"><span data-stu-id="d52e3-235">On the Customer_SalesOrders page, in the **Left Column** section, click **Add a Web Part**.</span></span>  
  
3.  <span data-ttu-id="d52e3-236">**Web パーツの追加** ダイアログ ボックスで、**ビジネス データ** セクションで、選択、**ビジネス データ項目**チェック ボックスをクリックして**追加**です。</span><span class="sxs-lookup"><span data-stu-id="d52e3-236">In the **Add Web Parts** dialog box, in the **Business Data** section, select the **Business Data Item** check box, and then click **Add**.</span></span>  
  
4.  <span data-ttu-id="d52e3-237">新しく追加されたビジネス データ項目 Web パーツをクリックして、**ツール ウィンドウを開く**リンクします。</span><span class="sxs-lookup"><span data-stu-id="d52e3-237">In the newly added Business Data Item Web Part, click the **Open the tool pane** link.</span></span>  
  
5.  <span data-ttu-id="d52e3-238">ビジネス データ項目のツール ウィンドウは、右側のウィンドウで開きます。</span><span class="sxs-lookup"><span data-stu-id="d52e3-238">The Business Data Item tool pane opens in the right pane.</span></span> <span data-ttu-id="d52e3-239">**ビジネス データ項目** セクションの**型**フィールドで、をクリックして、**参照**ボタンをクリックします。</span><span class="sxs-lookup"><span data-stu-id="d52e3-239">In the **Business Data Item** section, for the **Type** field, click the **Browse** button.</span></span>  
  
     <span data-ttu-id="d52e3-240">![ビジネス データ項目のツール ウィンドウ](../../adapters-and-accelerators/adapter-sap/media/29322df5-4ce3-4c1f-a658-39a355dfe2aa.gif "29322df5-4ce3-4c1f-a658-39a355dfe2aa")</span><span class="sxs-lookup"><span data-stu-id="d52e3-240">![Business Data Item tool pane](../../adapters-and-accelerators/adapter-sap/media/29322df5-4ce3-4c1f-a658-39a355dfe2aa.gif "29322df5-4ce3-4c1f-a658-39a355dfe2aa")</span></span>  
  
6.  <span data-ttu-id="d52e3-241">**ビジネス データの種類の選択**ダイアログ ボックスで、 **Customer_Order_Instance**クリックしてアプリケーションでは、 **OK**です。</span><span class="sxs-lookup"><span data-stu-id="d52e3-241">In the **Business Data Type Picker** dialog box, select the **Customer_Order_Instance** application, and then click **OK**.</span></span>  
  
7.  <span data-ttu-id="d52e3-242">**ビュー**一覧で、**既定**です。</span><span class="sxs-lookup"><span data-stu-id="d52e3-242">In the **View** list, select **Default**.</span></span>  
  
8.  <span data-ttu-id="d52e3-243">ままにして、**項目**リストが空です。</span><span class="sxs-lookup"><span data-stu-id="d52e3-243">Leave the **Item** list empty.</span></span>  
  
    > [!NOTE]
    >  <span data-ttu-id="d52e3-244">**項目**フィールドに、顧客名または詳細を表示する顧客番号を指定する必要があります。</span><span class="sxs-lookup"><span data-stu-id="d52e3-244">For the **Item** field, you must specify a customer name or customer number for which you want to see the details.</span></span> <span data-ttu-id="d52e3-245">入力パラメーターとして機能するにはこの Web パーツ。</span><span class="sxs-lookup"><span data-stu-id="d52e3-245">That serves as an input parameter for this Web Part.</span></span> <span data-ttu-id="d52e3-246">ビジネス データ一覧 Web パーツに接続して、入力パラメーターを取得するため項目を明示的に指定することが必要ありません。</span><span class="sxs-lookup"><span data-stu-id="d52e3-246">Because you will be getting the input parameter by connecting to the Business Data List Web Part, you need not specify an item explicitly.</span></span>  
  
9. <span data-ttu-id="d52e3-247">**フィールド**セクションで、**選択**ページに表示するフィールドを選択します。</span><span class="sxs-lookup"><span data-stu-id="d52e3-247">In the **Fields** section, click **Choose** to select the fields you want to display on the page.</span></span>  
  
10. <span data-ttu-id="d52e3-248">展開、**外観**ノード、および、**タイトル**フィールドに、Web パーツのタイトルを指定します。</span><span class="sxs-lookup"><span data-stu-id="d52e3-248">Expand the **Appearance** node, and in the **Title** field, specify a title for the Web Part.</span></span> <span data-ttu-id="d52e3-249">この Web パーツを指定する **、特定の顧客の詳細**です。</span><span class="sxs-lookup"><span data-stu-id="d52e3-249">For this Web Part, specify **Details for a Specific Customer**.</span></span>  
  
11. <span data-ttu-id="d52e3-250">をクリックして**適用**、順にクリック**OK**です。</span><span class="sxs-lookup"><span data-stu-id="d52e3-250">Click **Apply**, and then click **OK**.</span></span>  
  
12. <span data-ttu-id="d52e3-251">Web パーツを接続、**顧客リスト**Web パーツ。</span><span class="sxs-lookup"><span data-stu-id="d52e3-251">Connect the Web Part to the **Customer List** Web Part.</span></span> <span data-ttu-id="d52e3-252">そのためには次を行います。</span><span class="sxs-lookup"><span data-stu-id="d52e3-252">To do so:</span></span>  
  
    1.  <span data-ttu-id="d52e3-253">をクリックして**編集**Web パーツの右上寄りです。</span><span class="sxs-lookup"><span data-stu-id="d52e3-253">Click **edit** towards the upper-right corner of the Web Part.</span></span>  
  
    2.  <span data-ttu-id="d52e3-254">コンテキスト メニューのをポイント**接続**、 をポイント**から項目を取得**、 をクリック**顧客リスト**です。</span><span class="sxs-lookup"><span data-stu-id="d52e3-254">From the context menu point to **Connections**, point to **Get Item From**, and click **Customer List**.</span></span>  
  
         <span data-ttu-id="d52e3-255">![2 つの Web パーツを接続](../../adapters-and-accelerators/adapter-sap/media/505aead7-f498-448f-a7cb-55d0a121f91f.gif "505aead7-f498-448f-a7cb-55d0a121f91f")</span><span class="sxs-lookup"><span data-stu-id="d52e3-255">![Connect two Web Parts](../../adapters-and-accelerators/adapter-sap/media/505aead7-f498-448f-a7cb-55d0a121f91f.gif "505aead7-f498-448f-a7cb-55d0a121f91f")</span></span>  
  
### <a name="adding-a-business-data-related-list-web-part"></a><span data-ttu-id="d52e3-256">リスト Web パーツに関連するビジネス データの追加</span><span class="sxs-lookup"><span data-stu-id="d52e3-256">Adding a Business Data Related List Web Part</span></span>  
 <span data-ttu-id="d52e3-257">Web パーツ ページに、ビジネス データ関連一覧 Web パーツを追加する必要があります。</span><span class="sxs-lookup"><span data-stu-id="d52e3-257">You must now add a Business Data Related List Web Part to the Web Part page.</span></span> <span data-ttu-id="d52e3-258">この Web パーツは、先ほど作成したビジネス データ一覧 Web パーツに接続します。</span><span class="sxs-lookup"><span data-stu-id="d52e3-258">You will also connect this Web Part to the Business Data List Web Part you created earlier.</span></span> <span data-ttu-id="d52e3-259">これにより、ビジネス データ一覧 Web パーツで選択した顧客の販売注文を表示することができます。</span><span class="sxs-lookup"><span data-stu-id="d52e3-259">By doing so, you will be able to see the sales orders for a customer that you select in the Business Data List Web Part.</span></span> <span data-ttu-id="d52e3-260">この Web パーツに対応する、**アソシエーション**メソッド インスタンス (*SalesOrderForCustomer_Instance*) で、ビジネス データ カタログ定義エディターを作成しました。</span><span class="sxs-lookup"><span data-stu-id="d52e3-260">This Web Part corresponds to the **Association** method instance (*SalesOrderForCustomer_Instance*) you created in the Business Data Catalog Definition Editor.</span></span>  
  
##### <a name="to-add-a-business-data-related-list-web-part"></a><span data-ttu-id="d52e3-261">ビジネス データ関連一覧 Web パーツを追加するには</span><span class="sxs-lookup"><span data-stu-id="d52e3-261">To add a Business Data Related List Web Part</span></span>  
  
1.  <span data-ttu-id="d52e3-262">Customer_SalesOrders] ページで、**本文**セクションで、[ **Web パーツの追加**です。</span><span class="sxs-lookup"><span data-stu-id="d52e3-262">On the Customer_SalesOrders page, in the **Body** section, click **Add a Web Part**.</span></span>  
  
2.  <span data-ttu-id="d52e3-263">**Web パーツの追加** ダイアログ ボックスで、**ビジネス データ** セクションで、select、**ビジネス データ関連一覧**チェック ボックスをオンし、をクリックして**追加**です。</span><span class="sxs-lookup"><span data-stu-id="d52e3-263">In the **Add Web Parts** dialog box, in the **Business Data** section, select the **Business Data Related List** check box, and click **Add**.</span></span>  
  
3.  <span data-ttu-id="d52e3-264">新しく追加されたビジネス データ関連一覧 Web パーツで、をクリックして、**ツール ウィンドウを開いて**リンクします。</span><span class="sxs-lookup"><span data-stu-id="d52e3-264">In the newly added Business Data Related List Web Part, click the **Open the tool pane** link.</span></span>  
  
4.  <span data-ttu-id="d52e3-265">ビジネス データ関連一覧のツール ウィンドウは、右側のウィンドウで開きます。</span><span class="sxs-lookup"><span data-stu-id="d52e3-265">The Business Data Related List tool pane opens in the right pane.</span></span> <span data-ttu-id="d52e3-266">**ビジネス データ関連一覧** セクションの**型**フィールドで、をクリックして、**参照**ボタンをクリックします。</span><span class="sxs-lookup"><span data-stu-id="d52e3-266">In the **Business Data Related List** section, for the **Type** field, click the **Browse** button.</span></span>  
  
     <span data-ttu-id="d52e3-267">![ビジネス データ関連一覧](../../adapters-and-accelerators/adapter-sap/media/1914e12d-27f0-4ecb-9605-3177183a2d44.gif "1914e12d-27f0-4ecb-9605-3177183a2d44")</span><span class="sxs-lookup"><span data-stu-id="d52e3-267">![Business Data Related List](../../adapters-and-accelerators/adapter-sap/media/1914e12d-27f0-4ecb-9605-3177183a2d44.gif "1914e12d-27f0-4ecb-9605-3177183a2d44")</span></span>  
  
5.  <span data-ttu-id="d52e3-268">**ビジネス データの種類の選択**ダイアログ ボックスで、 **Customer_Order_Instance**クリックしてアプリケーションでは、 **OK**です。</span><span class="sxs-lookup"><span data-stu-id="d52e3-268">In the **Business Data Type Picker** dialog box, select the **Customer_Order_Instance** application, and then click **OK**.</span></span> <span data-ttu-id="d52e3-269">**リレーションシップ**一覧の設定の名前を持つ、**アソシエーション**メソッド インスタンス (*SalesOrderForCustomer_Instance*)。</span><span class="sxs-lookup"><span data-stu-id="d52e3-269">The **Relationship** list populates with the name of the **Association** method instance (*SalesOrderForCustomer_Instance*).</span></span>  
  
6.  <span data-ttu-id="d52e3-270">展開、**外観**ノード、および、**タイトル**ボックスで、Web パーツのタイトルを入力します。</span><span class="sxs-lookup"><span data-stu-id="d52e3-270">Expand the **Appearance** node, and in the **Title** box, type a title for the Web Part.</span></span> <span data-ttu-id="d52e3-271">この Web パーツの次のように入力します。**特定の顧客の販売注文**です。</span><span class="sxs-lookup"><span data-stu-id="d52e3-271">For this Web Part, type **Sales Order for a Specific Customer**.</span></span>  
  
7.  <span data-ttu-id="d52e3-272">をクリックして**適用**、順にクリック**OK**です。</span><span class="sxs-lookup"><span data-stu-id="d52e3-272">Click **Apply**, and then click **OK**.</span></span>  
  
8.  <span data-ttu-id="d52e3-273">Web パーツには、BAPI_SALESORDER_GETLIST RFC を実行することによって返されるフィールドが一覧表示します。</span><span class="sxs-lookup"><span data-stu-id="d52e3-273">The Web Part lists the fields that are returned by executing the BAPI_SALESORDER_GETLIST RFC.</span></span> <span data-ttu-id="d52e3-274">SharePoint ポータルに表示したくないフィールドを削除することができます。</span><span class="sxs-lookup"><span data-stu-id="d52e3-274">You can remove the fields that you do not want to display on the SharePoint portal.</span></span> <span data-ttu-id="d52e3-275">削除するには、フィールドをクリックして、**ビューの編集**Web パーツの右上隅にリンクします。</span><span class="sxs-lookup"><span data-stu-id="d52e3-275">To remove the fields, click the **Edit View** link in the upper-right corner of the Web Part.</span></span>  
  
9. <span data-ttu-id="d52e3-276">[ビューの編集] ページで、**列**セクションで、表示しない列に対して、テキスト ボックスをオフにします。</span><span class="sxs-lookup"><span data-stu-id="d52e3-276">On the Edit View page, in the **Columns** section, clear the text boxes against the columns that you do not want to display.</span></span>  
  
10. <span data-ttu-id="d52e3-277">**[OK]** をクリックします。</span><span class="sxs-lookup"><span data-stu-id="d52e3-277">Click **OK**.</span></span>  
  
11. <span data-ttu-id="d52e3-278">Web パーツを接続、**顧客リスト**Web パーツ。</span><span class="sxs-lookup"><span data-stu-id="d52e3-278">Connect the Web Part to the **Customer List** Web Part.</span></span> <span data-ttu-id="d52e3-279">そのためには次を行います。</span><span class="sxs-lookup"><span data-stu-id="d52e3-279">To do so:</span></span>  
  
    1.  <span data-ttu-id="d52e3-280">をクリックして**編集**の右上寄り、**特定の顧客の販売注文**Web パーツ。</span><span class="sxs-lookup"><span data-stu-id="d52e3-280">Click **edit** towards the upper-right corner of the **Sales Order for a Specific Customer** Web Part.</span></span>  
  
    2.  <span data-ttu-id="d52e3-281">コンテキスト メニューのをポイント**接続**、 をポイント**関連項目を取得**、順にクリック**顧客リスト**です。</span><span class="sxs-lookup"><span data-stu-id="d52e3-281">From the context menu, point to **Connections**, point to **Get Related Item From**, and then click **Customer List**.</span></span>  
  
12. <span data-ttu-id="d52e3-282">をクリックして**編集モードの終了**ページの右上隅からです。</span><span class="sxs-lookup"><span data-stu-id="d52e3-282">Click **Exit Edit Mode** from the upper-right corner of the page.</span></span>  
  
## <a name="next-steps"></a><span data-ttu-id="d52e3-283">次の手順</span><span class="sxs-lookup"><span data-stu-id="d52e3-283">Next Steps</span></span>  
 <span data-ttu-id="d52e3-284">SAP システムからデータを取得することによって、SharePoint アプリケーションをテストします。</span><span class="sxs-lookup"><span data-stu-id="d52e3-284">Test the SharePoint application by retrieving data from an SAP system.</span></span> <span data-ttu-id="d52e3-285">参照してください[手順 4: SharePoint アプリケーションをテスト](../../adapters-and-accelerators/adapter-sap/step-4-test-your-sharepoint-application1.md)です。</span><span class="sxs-lookup"><span data-stu-id="d52e3-285">See [Step 4: Test Your SharePoint Application](../../adapters-and-accelerators/adapter-sap/step-4-test-your-sharepoint-application1.md).</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="d52e3-286">参照</span><span class="sxs-lookup"><span data-stu-id="d52e3-286">See Also</span></span>  
 [<span data-ttu-id="d52e3-287">チュートリアル 1: SharePoint サイト上の SAP システムからのデータの表示</span><span class="sxs-lookup"><span data-stu-id="d52e3-287">Tutorial 1: Presenting Data from an SAP System on a SharePoint Site</span></span>](../../adapters-and-accelerators/adapter-sap/tutorial-1-presenting-data-from-an-sap-system-on-a-sharepoint-site.md)