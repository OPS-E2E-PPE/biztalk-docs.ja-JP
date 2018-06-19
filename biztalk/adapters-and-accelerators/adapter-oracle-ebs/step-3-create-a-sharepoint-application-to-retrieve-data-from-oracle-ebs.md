---
title: '手順 3: Oracle E-business Suite からデータを取得する SharePoint アプリケーションの作成 |Microsoft ドキュメント'
ms.custom: ''
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: ''
ms.suite: ''
ms.tgt_pltfrm: ''
ms.topic: article
ms.assetid: eaa16011-9284-4ccf-8132-9c1e14cc6aa7
caps.latest.revision: 4
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: 4fe9d6fc34fa039bb4b3861deb35fb51524180ab
ms.sourcegitcommit: cb908c540d8f1a692d01dc8f313e16cb4b4e696d
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 09/20/2017
ms.locfileid: "22217202"
---
# <a name="step-3-create-a-sharepoint-application-to-retrieve-data-from-oracle-e-business-suite"></a><span data-ttu-id="fd33c-102">手順 3: Oracle E-business Suite からデータを取得する SharePoint アプリケーションを作成します。</span><span class="sxs-lookup"><span data-stu-id="fd33c-102">Step 3: Create a SharePoint application to retrieve data from Oracle E-Business Suite</span></span>
<span data-ttu-id="fd33c-103">![手順 4 の 3](../../adapters-and-accelerators/adapter-oracle-ebs/media/step-3of4.gif "Step_3of4")</span><span class="sxs-lookup"><span data-stu-id="fd33c-103">![Step 3 of 4](../../adapters-and-accelerators/adapter-oracle-ebs/media/step-3of4.gif "Step_3of4")</span></span>  
  
 <span data-ttu-id="fd33c-104">**所要時間:** 15 分</span><span class="sxs-lookup"><span data-stu-id="fd33c-104">**Time to complete:** 15 minutes</span></span>  
  
 <span data-ttu-id="fd33c-105">**目標:** 今すぐ Microsoft Office SharePoint Server にアプリケーション定義ファイルをインポートし、Oracle E-business Suite からデータを取得するアプリケーションを設定する必要があります。</span><span class="sxs-lookup"><span data-stu-id="fd33c-105">**Objective:** You must now import the application definition file in Microsoft Office SharePoint Server, and set up an application to retrieve data from Oracle E-Business Suite.</span></span>  
  
## <a name="prerequisites"></a><span data-ttu-id="fd33c-106">前提条件</span><span class="sxs-lookup"><span data-stu-id="fd33c-106">Prerequisites</span></span>  
  
-   <span data-ttu-id="fd33c-107">必要がありますがファイルを作成したアプリケーションの定義」の説明に従って[手順 2: Oracle E-business Suite 成果物のため、アプリケーション定義ファイルを作成する](../../adapters-and-accelerators/adapter-oracle-ebs/step-2-create-an-application-definition-file-for-the-oracle-ebs-artifacts.md)です。</span><span class="sxs-lookup"><span data-stu-id="fd33c-107">You should have created an application definition file as described in [Step 2: Create an Application Definition File for the Oracle E-Business Suite Artifacts](../../adapters-and-accelerators/adapter-oracle-ebs/step-2-create-an-application-definition-file-for-the-oracle-ebs-artifacts.md).</span></span>  
  
-   <span data-ttu-id="fd33c-108">Microsoft シングル サインオン サービスを実行する必要があります。</span><span class="sxs-lookup"><span data-stu-id="fd33c-108">The Microsoft Single Sign-on service must be running.</span></span>  
  
 
  
##  <a name="SSO"></a><span data-ttu-id="fd33c-109">SharePoint での SSO アプリケーションの作成</span><span class="sxs-lookup"><span data-stu-id="fd33c-109">Creating an SSO Application in SharePoint</span></span>  
 <span data-ttu-id="fd33c-110">SharePoint アプリケーションから Oracle E-business Suite でのデータにアクセスするには、Oracle E-business Suite のユーザーに、SharePoint ユーザーにマップする SSO アプリケーションを設定する必要があります。</span><span class="sxs-lookup"><span data-stu-id="fd33c-110">To access the data in Oracle E-Business Suite from a SharePoint application, you must set up an SSO application that maps a SharePoint user to an Oracle E-Business Suite user.</span></span> <span data-ttu-id="fd33c-111">SharePoint で SSO アプリケーションを作成するには、次の手順が含まれます。</span><span class="sxs-lookup"><span data-stu-id="fd33c-111">Creating an SSO application in SharePoint involves the following steps:</span></span>  
  
1.  <span data-ttu-id="fd33c-112">**シングル サインオンの設定をサーバー管理**です。</span><span class="sxs-lookup"><span data-stu-id="fd33c-112">**Manage server settings for single sign-on**.</span></span> <span data-ttu-id="fd33c-113">このステップでは、管理、シングル サインオン サービスを設定したりできるユーザー アカウントを指定します。</span><span class="sxs-lookup"><span data-stu-id="fd33c-113">In this step, you specify a user account that can manage and set up the single sign-on service.</span></span> <span data-ttu-id="fd33c-114">サーバー設定の管理 ページで、これを行うことができます。</span><span class="sxs-lookup"><span data-stu-id="fd33c-114">You can do so on the Manage Server Settings page.</span></span> <span data-ttu-id="fd33c-115">このオプションを指定する場合は、SharePoint サーバーの全体管理コンソールで実行できます。</span><span class="sxs-lookup"><span data-stu-id="fd33c-115">This option is available from the SharePoint Central Administration console.</span></span> <span data-ttu-id="fd33c-116">この手順の詳細についてで「構成に対するシングル サインオン - Office SharePoint Server 2007」セクションを参照してください[http://go.microsoft.com/fwlink/?LinkId=105291](http://go.microsoft.com/fwlink/?LinkId=105291)です。</span><span class="sxs-lookup"><span data-stu-id="fd33c-116">For more information about this step, refer to the “Configure Single Sign-On for Office SharePoint Server 2007” section at [http://go.microsoft.com/fwlink/?LinkId=105291](http://go.microsoft.com/fwlink/?LinkId=105291).</span></span>  
  
2.  <span data-ttu-id="fd33c-117">**エンタープライズ アプリケーション定義の設定を管理**です。</span><span class="sxs-lookup"><span data-stu-id="fd33c-117">**Manage settings for enterprise application definitions**.</span></span> <span data-ttu-id="fd33c-118">このステップでは、エンタープライズ アプリケーション定義の設定を構成します。</span><span class="sxs-lookup"><span data-stu-id="fd33c-118">In this step, you configure the settings for the enterprise application definition.</span></span> <span data-ttu-id="fd33c-119">エンタープライズ アプリケーション定義 ページの設定の管理から行うことができます。</span><span class="sxs-lookup"><span data-stu-id="fd33c-119">You can do so from the Manage Settings for Enterprise Application Definitions page.</span></span> <span data-ttu-id="fd33c-120">このオプションを指定する場合は、SharePoint サーバーの全体管理コンソールで実行できます。</span><span class="sxs-lookup"><span data-stu-id="fd33c-120">This option is available from the SharePoint Central Administration console.</span></span>  
  
    1.  <span data-ttu-id="fd33c-121">サーバーの全体管理で、上部のナビゲーション バーで、をクリックして**Operations**です。</span><span class="sxs-lookup"><span data-stu-id="fd33c-121">On Central Administration, on the top navigation bar, click **Operations**.</span></span>  
  
    2.  <span data-ttu-id="fd33c-122">[操作] ページで、**セキュリティの構成**セクションで、をクリックして**でのシングル サインオンの設定を管理**です。</span><span class="sxs-lookup"><span data-stu-id="fd33c-122">On the Operations page, in the **Security Configuration** section, click  **Manage settings for single sign-on**.</span></span>  
  
    3.  <span data-ttu-id="fd33c-123">シングル サインオン] ページの設定の管理で、**エンタープライズ アプリケーション定義の設定**セクションで、[**企業アプリケーション定義の設定を管理**です。</span><span class="sxs-lookup"><span data-stu-id="fd33c-123">On the Manage Settings for Single Sign-On page, in the **Enterprise Application Definition Settings** section, click **Manage settings for enterprise application definitions**.</span></span>  
  
    4.  <span data-ttu-id="fd33c-124">[エンタープライズ アプリケーション定義の管理] ページで、値を指定して、**表示名**、**アプリケーション名**、および**連絡先の電子メール アドレス**フィールドです。</span><span class="sxs-lookup"><span data-stu-id="fd33c-124">On the Manage Enterprise Application Definitions page, provide values for the **Display name**, **Application name**, and the **Contact e-mail address** fields.</span></span>  
  
        > [!IMPORTANT]
        >  <span data-ttu-id="fd33c-125">**アプリケーション名**フィールドに、指定した同じ SSO アプリケーション名を指定するかどうかを確認、 **SecondarySsoApplicationId**として、アプリケーション定義ファイルの作成中に変数説明されている[手順 2: Oracle E-business Suite 成果物のため、アプリケーション定義ファイルを作成する](../../adapters-and-accelerators/adapter-oracle-ebs/step-2-create-an-application-definition-file-for-the-oracle-ebs-artifacts.md)です。</span><span class="sxs-lookup"><span data-stu-id="fd33c-125">For the **Application name** field, make sure you specify the same SSO application name that you specified for the **SecondarySsoApplicationId** variable while creating the application definition file, as described in [Step 2: Create an Application Definition File for the Oracle E-Business Suite Artifacts](../../adapters-and-accelerators/adapter-oracle-ebs/step-2-create-an-application-definition-file-for-the-oracle-ebs-artifacts.md).</span></span>  
  
    5.  <span data-ttu-id="fd33c-126">既定では、他のフィールドのままにし、をクリックして**OK**です。</span><span class="sxs-lookup"><span data-stu-id="fd33c-126">Leave the other fields as default, and click **OK**.</span></span>  
  
3.  <span data-ttu-id="fd33c-127">**エンタープライズ アプリケーション定義のアカウント情報を管理する**です。</span><span class="sxs-lookup"><span data-stu-id="fd33c-127">**Manage account information for enterprise application definitions**.</span></span> <span data-ttu-id="fd33c-128">このステップでは SharePoint からエンタープライズ アプリケーションに接続するには、個々 のユーザーまたはグループを有効にします。</span><span class="sxs-lookup"><span data-stu-id="fd33c-128">In this step, you enable individual users or groups to connect to an enterprise application from SharePoint.</span></span> <span data-ttu-id="fd33c-129">基本的には、この手順でマップする個々 のユーザーまたはグループのユーザーに LOB システムに。</span><span class="sxs-lookup"><span data-stu-id="fd33c-129">Essentially, in this step you map an individual user or group to a user in the LOB system.</span></span> <span data-ttu-id="fd33c-130">また、LOB システムへの接続に資格情報を指定します。</span><span class="sxs-lookup"><span data-stu-id="fd33c-130">You also specify the credentials to connect to the LOB system.</span></span> <span data-ttu-id="fd33c-131">エンタープライズ アプリケーション定義 ページのアカウント情報の管理から行うことができます。</span><span class="sxs-lookup"><span data-stu-id="fd33c-131">You can do so from the Manage Account Information for Enterprise Application Definitions page.</span></span> <span data-ttu-id="fd33c-132">このオプションを指定する場合は、SharePoint サーバーの全体管理コンソールで実行できます。</span><span class="sxs-lookup"><span data-stu-id="fd33c-132">This option is available from the SharePoint Central Administration console.</span></span> <span data-ttu-id="fd33c-133">この手順の詳細についてで「エンタープライズ アプリケーション定義のアカウント情報の管理」セクションを参照してください[http://go.microsoft.com/fwlink/?LinkId=105291](http://go.microsoft.com/fwlink/?LinkId=105291)です。</span><span class="sxs-lookup"><span data-stu-id="fd33c-133">For more information about this step, refer to the “Manage account information for an enterprise application definition” section at [http://go.microsoft.com/fwlink/?LinkId=105291](http://go.microsoft.com/fwlink/?LinkId=105291).</span></span>  
  
##  <a name="SSP"></a><span data-ttu-id="fd33c-134">共有サービス プロバイダーを作成します。</span><span class="sxs-lookup"><span data-stu-id="fd33c-134">Creating a Shared Services Provider</span></span>  
 <span data-ttu-id="fd33c-135">共有サービス プロバイダーは、共有サービスとその関連リソースの論理的なグループです。</span><span class="sxs-lookup"><span data-stu-id="fd33c-135">A Shared Service Provider is a logical grouping of shared services and their supporting resources.</span></span> <span data-ttu-id="fd33c-136">SSP は、SharePoint サーバーの全体管理コンソールを使用して作成できます。</span><span class="sxs-lookup"><span data-stu-id="fd33c-136">You can create an SSP by using the SharePoint Central Administration console.</span></span>  
  
 <span data-ttu-id="fd33c-137">SSP を作成するときに、Web サイトを定義する必要があります。</span><span class="sxs-lookup"><span data-stu-id="fd33c-137">You must define a Web site when creating an SSP.</span></span> <span data-ttu-id="fd33c-138">ポート番号と、サイト アドレスを作成することに注意してください。</span><span class="sxs-lookup"><span data-stu-id="fd33c-138">Remember the port number and the site address that you create.</span></span> <span data-ttu-id="fd33c-139">このサイトには、ビジネス データ カタログ アプリケーション定義をインポートします。</span><span class="sxs-lookup"><span data-stu-id="fd33c-139">You will import the Business Data Catalog application definition to this site.</span></span>  
  
 <span data-ttu-id="fd33c-140">SSP の作成の詳細については、次を参照してください。"章の概要: を作成し、共有サービス プロバイダーを構成する"で[http://go.microsoft.com/fwlink/?LinkId=105119](http://go.microsoft.com/fwlink/?LinkId=105119)です。</span><span class="sxs-lookup"><span data-stu-id="fd33c-140">For more information about creating an SSP, see "Chapter overview: Create and configure Shared Services Providers" at [http://go.microsoft.com/fwlink/?LinkId=105119](http://go.microsoft.com/fwlink/?LinkId=105119).</span></span>  
  
##  <a name="Import"></a><span data-ttu-id="fd33c-141">アプリケーション定義ファイルのインポート</span><span class="sxs-lookup"><span data-stu-id="fd33c-141">Importing the Application Definition File</span></span>  
 <span data-ttu-id="fd33c-142">SSP にアプリケーション定義ファイルをインポートする必要があります。</span><span class="sxs-lookup"><span data-stu-id="fd33c-142">You must now import the application definition file into the SSP.</span></span>  
  
#### <a name="to-import-the-application-definition-file"></a><span data-ttu-id="fd33c-143">アプリケーション定義ファイルをインポートするには</span><span class="sxs-lookup"><span data-stu-id="fd33c-143">To import the application definition file</span></span>  
  
1.  <span data-ttu-id="fd33c-144">SharePoint 3.0 サーバーの全体管理を開始します。</span><span class="sxs-lookup"><span data-stu-id="fd33c-144">Start SharePoint 3.0 Central Administration.</span></span> <span data-ttu-id="fd33c-145">をクリックして**開始**、 をポイント**すべてのプログラム**、 をポイント**Microsoft Office Server**、クリックして**SharePoint 3.0 サーバーの全体管理**.</span><span class="sxs-lookup"><span data-stu-id="fd33c-145">Click **Start**, point to **All Programs**, point to **Microsoft Office Server**, and then click **SharePoint 3.0 Central Administration**.</span></span>  
  
2.  <span data-ttu-id="fd33c-146">左側のナビゲーション ウィンドウで、アプリケーション定義をインポートする SSP の名前をクリックします。</span><span class="sxs-lookup"><span data-stu-id="fd33c-146">In the left navigation pane, click the name of the SSP to which you want to import the application definition.</span></span>  
  
3.  <span data-ttu-id="fd33c-147">**ビジネス データ カタログ**セクションで、**アプリケーション定義のインポート**です。</span><span class="sxs-lookup"><span data-stu-id="fd33c-147">In the **Business Data Catalog** section, click **Import application definition**.</span></span>  
  
4.  <span data-ttu-id="fd33c-148">Employee.xml、[参照] を開くと、アプリケーション定義のインポート ページで、ファイルを選択し、をクリックして**開く**です。</span><span class="sxs-lookup"><span data-stu-id="fd33c-148">On the Import Application Definition page that opens, browse to Employee.xml, select the file, and then click **Open**.</span></span>  
  
5.  <span data-ttu-id="fd33c-149">**[インポート]** をクリックします。</span><span class="sxs-lookup"><span data-stu-id="fd33c-149">Click **Import**.</span></span>  
  
6.  <span data-ttu-id="fd33c-150">アプリケーション定義ファイルが正常にインポートされると、クリックして**OK**です。</span><span class="sxs-lookup"><span data-stu-id="fd33c-150">After the application definition file is imported successfully, click **OK**.</span></span>  
  
     <span data-ttu-id="fd33c-151">アプリケーション定義ファイル、MS_SAMPLE_EMPLOYEE のインポートの結果として作成されたアプリケーションが表示されます。</span><span class="sxs-lookup"><span data-stu-id="fd33c-151">The application created as a result of importing the application definition file, MS_SAMPLE_EMPLOYEE, appears.</span></span>  
  
     <span data-ttu-id="fd33c-152">![SharePoint でアプリケーション](../../adapters-and-accelerators/adapter-oracle-ebs/media/b0695720-0113-49dc-8eb6-c685aceada6c.gif "b0695720-0113-49dc-8eb6-c685aceada6c")</span><span class="sxs-lookup"><span data-stu-id="fd33c-152">![The application in SharePoint](../../adapters-and-accelerators/adapter-oracle-ebs/media/b0695720-0113-49dc-8eb6-c685aceada6c.gif "b0695720-0113-49dc-8eb6-c685aceada6c")</span></span>  
  
## <a name="next-steps"></a><span data-ttu-id="fd33c-153">次の手順</span><span class="sxs-lookup"><span data-stu-id="fd33c-153">Next Steps</span></span>  
 <span data-ttu-id="fd33c-154">ここで、表示し、Oracle E-business Suite から抽出するビジネス データを検索する SharePoint サイトを作成する Web パーツを作成する準備ができたらです。</span><span class="sxs-lookup"><span data-stu-id="fd33c-154">Now, you are ready to create Web Parts to create a SharePoint site to view and search the business data that will be extracted from Oracle E-Business Suite.</span></span> <span data-ttu-id="fd33c-155">A: を作成します</span><span class="sxs-lookup"><span data-stu-id="fd33c-155">We will create a:</span></span>  
  
-   <span data-ttu-id="fd33c-156">MS_SAMPLE_EMPLOYEE インターフェイス テーブルから従業員レコードを表示するビジネス データ一覧 Web パーツ。</span><span class="sxs-lookup"><span data-stu-id="fd33c-156">Business Data List Web Part to display employee records from the MS_SAMPLE_EMPLOYEE interface table.</span></span> <span data-ttu-id="fd33c-157">参照してください[シナリオ 1: ビジネス データ一覧 Web パーツを使用してデータを表示](../../adapters-and-accelerators/adapter-oracle-ebs/scenario-1-display-data-using-business-data-list-web-part.md)です。</span><span class="sxs-lookup"><span data-stu-id="fd33c-157">See [Scenario 1: Display Data Using Business Data List Web Part](../../adapters-and-accelerators/adapter-oracle-ebs/scenario-1-display-data-using-business-data-list-web-part.md).</span></span>  
  
-   <span data-ttu-id="fd33c-158">MS_SAMPLE_EMPLOYEE インターフェイス テーブルでフルテキスト検索を実行するには、ボックス Web パーツを検索します。</span><span class="sxs-lookup"><span data-stu-id="fd33c-158">Search Box Web Part to perform a full-text search on the MS_SAMPLE_EMPLOYEE interface table.</span></span> <span data-ttu-id="fd33c-159">参照してください[シナリオ 2: 検索ボックス Web パーツを使用して検索](../../adapters-and-accelerators/adapter-oracle-ebs/scenario-2-search-using-the-search-box-web-part.md)です。</span><span class="sxs-lookup"><span data-stu-id="fd33c-159">See [Scenario 2: Search Using the Search Box Web Part](../../adapters-and-accelerators/adapter-oracle-ebs/scenario-2-search-using-the-search-box-web-part.md).</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="fd33c-160">参照</span><span class="sxs-lookup"><span data-stu-id="fd33c-160">See Also</span></span>  
 [<span data-ttu-id="fd33c-161">チュートリアル: SharePoint サイト上の Oracle E-business Suite からデータを表示します。</span><span class="sxs-lookup"><span data-stu-id="fd33c-161">Tutorial: Present Data from Oracle E-Business Suite on a SharePoint Site</span></span>](Tutorial:%20Present%20data%20from%20Oracle%20E-Business%20Suite%20on%20a%20SharePoint%20Site.md)