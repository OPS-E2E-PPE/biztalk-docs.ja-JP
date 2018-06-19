---
title: '手順 3: アプリケーション定義ファイルの作成 |Microsoft ドキュメント'
ms.custom: ''
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: ''
ms.suite: ''
ms.tgt_pltfrm: ''
ms.topic: article
ms.assetid: 843fafdb-571e-4da4-ad04-7dc7f23e03ac
caps.latest.revision: 16
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: ce22a63e8267c36c1306974caa0faa5f9aa6be4b
ms.sourcegitcommit: cb908c540d8f1a692d01dc8f313e16cb4b4e696d
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 09/20/2017
ms.locfileid: "22227010"
---
# <a name="step-3-create-an-application-definition-file"></a><span data-ttu-id="b725d-102">手順 3: アプリケーション定義ファイルを作成します。</span><span class="sxs-lookup"><span data-stu-id="b725d-102">Step 3: Create an Application Definition File</span></span>
<span data-ttu-id="b725d-103">![手順 4 の 3](../../adapters-and-accelerators/adapter-oracle-ebs/media/step-3of4.gif "Step_3of4")</span><span class="sxs-lookup"><span data-stu-id="b725d-103">![Step 3 of 4](../../adapters-and-accelerators/adapter-oracle-ebs/media/step-3of4.gif "Step_3of4")</span></span>  
  
 <span data-ttu-id="b725d-104">**所要時間:** 15 分</span><span class="sxs-lookup"><span data-stu-id="b725d-104">**Time to complete:** 15 minutes</span></span>  
  
 <span data-ttu-id="b725d-105">Microsoft Office SharePoint Server でビジネス データ カタログの機能は、公開し、ポータルに基幹業務 (LOB) アプリケーションからのデータが組み込まれています。</span><span class="sxs-lookup"><span data-stu-id="b725d-105">The Business Data Catalog feature in Microsoft Office SharePoint Server exposes and incorporates data from line-of-business (LOB) applications into portals.</span></span> <span data-ttu-id="b725d-106">ポータル サイトにこのデータを組み込むには、Microsoft Office SharePoint Server を使用できるアプリケーション定義ファイルをビルドする必要があります。</span><span class="sxs-lookup"><span data-stu-id="b725d-106">To incorporate this data into your portal site, you must build an application definition file that Microsoft Office SharePoint Server can consume.</span></span>  
  
 <span data-ttu-id="b725d-107">このステップでは、Microsoft Office SharePoint Server 2007 SDK で利用可能なビジネス データ カタログ定義エディター ツールを使用してのビジネス データ カタログ アプリケーション定義ファイルを作成します。</span><span class="sxs-lookup"><span data-stu-id="b725d-107">In this step you use the Business Data Catalog Definition Editor tool, available with the Microsoft Office SharePoint Server 2007 SDK, to create an application definition file for the Business Data Catalog.</span></span> <span data-ttu-id="b725d-108">この定義ファイルでは、エコー アダプターの EchoGreetings メソッドをについて説明し、アダプターと通信するように SharePoint を有効にする後の手順で使用されます。</span><span class="sxs-lookup"><span data-stu-id="b725d-108">This definition file describes the EchoGreetings method of the Echo adapter, and will be used in later steps to enable SharePoint to communicate with the adapter.</span></span>  
  
 <span data-ttu-id="b725d-109">作成している Microsoft Office SharePoint Server アプリケーションの目的は、使用すると、エコー アダプターの EchoGreetings メソッドを呼び出すし、SharePoint Web パーツを使用して応答を返すを開始します。</span><span class="sxs-lookup"><span data-stu-id="b725d-109">The purpose of the Microsoft Office SharePoint Server application that you are creating is to allow you to invoke the EchoGreetings method of the Echo adapter and return the response using a SharePoint Web Part.</span></span>  
  
## <a name="prerequisites"></a><span data-ttu-id="b725d-110">前提条件</span><span class="sxs-lookup"><span data-stu-id="b725d-110">Prerequisites</span></span>  
 <span data-ttu-id="b725d-111">作成した[手順 2: Web プロジェクトを配置](../../adapters-and-accelerators/wcf-lob-adapter-sdk/step-2-deploy-the-web-project.md)です。</span><span class="sxs-lookup"><span data-stu-id="b725d-111">You should have completed [Step 2: Deploy the Web Project](../../adapters-and-accelerators/wcf-lob-adapter-sdk/step-2-deploy-the-web-project.md).</span></span> <span data-ttu-id="b725d-112">エディターへアクセス、ビジネス データ カタログの定義、Microsoft Office SharePoint Server 2007 SDK の一部としてインストールされている必要があります。</span><span class="sxs-lookup"><span data-stu-id="b725d-112">You must also have access to the Business Data Catalog Definition Editor, which is installed as part of the Microsoft Office SharePoint Server 2007 SDK.</span></span> <span data-ttu-id="b725d-113">SDK をダウンロードする[http://go.microsoft.com/fwlink/?LinkId=104130](http://go.microsoft.com/fwlink/?LinkId=104130)です。</span><span class="sxs-lookup"><span data-stu-id="b725d-113">You can download the SDK from [http://go.microsoft.com/fwlink/?LinkId=104130](http://go.microsoft.com/fwlink/?LinkId=104130).</span></span>  
  
## <a name="creating-an-application-definition-file"></a><span data-ttu-id="b725d-114">アプリケーション定義ファイルを作成します。</span><span class="sxs-lookup"><span data-stu-id="b725d-114">Creating an Application Definition File</span></span>  
 <span data-ttu-id="b725d-115">このトピックでは、IIS でホストされる WCF アダプター SharePoint ビジネス データ カタログへの接続用のアプリケーション定義ファイルを作成する手順を説明します。</span><span class="sxs-lookup"><span data-stu-id="b725d-115">This topic provides step-by-step instructions to create an application definition file for connecting the SharePoint Business Data Catalog with the WCF adapter hosted in IIS.</span></span>  
  
#### <a name="to-connect-to-the-wcf-adapter-service-and-create-entities"></a><span data-ttu-id="b725d-116">WCF アダプターのサービスに接続し、エンティティを作成するには</span><span class="sxs-lookup"><span data-stu-id="b725d-116">To connect to the WCF adapter service and create entities</span></span>  
  
1.  <span data-ttu-id="b725d-117">**スタート メニュー**、 をポイント**すべてのプログラム**、クリックして**Microsoft ビジネス データ カタログ定義エディター**です。</span><span class="sxs-lookup"><span data-stu-id="b725d-117">From the **Start menu**, point to **All Programs**, and then click **Microsoft Business Data Catalog Definition Editor**.</span></span>  
  
2.  <span data-ttu-id="b725d-118">ツールバーで、をクリックして**LOB システムの追加**です。</span><span class="sxs-lookup"><span data-stu-id="b725d-118">On the toolbar, click **Add LOB System**.</span></span>  
  
3.  <span data-ttu-id="b725d-119">LOB システムの追加] ウィンドウで、[ **web サービスへの接続**です。</span><span class="sxs-lookup"><span data-stu-id="b725d-119">In the Add LOB System window, click **Connect to Webservice**.</span></span>  
  
4.  <span data-ttu-id="b725d-120">**URL**ボックスには、WCF サービスの URL を入力します。</span><span class="sxs-lookup"><span data-stu-id="b725d-120">In the **URL** box, type the URL for the WCF service.</span></span> <span data-ttu-id="b725d-121">URL は、次の形式である必要があります。`https://machinename/EchoWeb/EchoOutboundContract.svc?wsdl`</span><span class="sxs-lookup"><span data-stu-id="b725d-121">The URL must be in the following format: `https://machinename/EchoWeb/EchoOutboundContract.svc?wsdl`</span></span>  
  
5.  <span data-ttu-id="b725d-122">**[接続]** をクリックします。</span><span class="sxs-lookup"><span data-stu-id="b725d-122">Click **Connect**.</span></span>  
  
6.  <span data-ttu-id="b725d-123">使用可能な操作を表示するをクリックして、 **Web メソッドの追加**タブです。EchoGreetings メソッドが表示されます。</span><span class="sxs-lookup"><span data-stu-id="b725d-123">To see the available operations, click the **Add Web Method** tab. You should see the EchoGreetings method.</span></span> <span data-ttu-id="b725d-124">メソッドは、デザイン画面にドラッグします。</span><span class="sxs-lookup"><span data-stu-id="b725d-124">Drag the method to the Design Surface.</span></span>  
  
7.  <span data-ttu-id="b725d-125">**[OK]** をクリックします。</span><span class="sxs-lookup"><span data-stu-id="b725d-125">Click **OK**.</span></span>  
  
8.  <span data-ttu-id="b725d-126">**LOB システムの名前を入力** ダイアログ ボックスに名前を入力、 **LOB システム名**ボックス。</span><span class="sxs-lookup"><span data-stu-id="b725d-126">In the **Enter the name for the LOB System** dialog box, type a name in the **LOB System Name** box.</span></span> <span data-ttu-id="b725d-127">この例では、次を入力してください。 **EchoWSLOB**、クリックして**OK**です。</span><span class="sxs-lookup"><span data-stu-id="b725d-127">For this example, enter **EchoWSLOB**, and then click **OK**.</span></span>  
  
9. <span data-ttu-id="b725d-128">展開、 **EchoWSLob**  ノードの順に展開し、**エンティティ**ノード。</span><span class="sxs-lookup"><span data-stu-id="b725d-128">Expand the **EchoWSLob** node, and then expand the **Entities** node.</span></span> <span data-ttu-id="b725d-129">選択**Entity0**プロパティ ウィンドウの入力**EchoGreetings**の値として、**名前**プロパティです。</span><span class="sxs-lookup"><span data-stu-id="b725d-129">Select **Entity0** and in the Properties pane type **EchoGreetings** as the value for the **Name** property.</span></span>  
  
     <span data-ttu-id="b725d-130">![エンティティ名](../../adapters-and-accelerators/wcf-lob-adapter-sdk/media/942e7853-451e-4cf5-8884-09fb7d8dc19d.gif "942e7853-451e-4cf5-8884-09fb7d8dc19d")</span><span class="sxs-lookup"><span data-stu-id="b725d-130">![Entity Name](../../adapters-and-accelerators/wcf-lob-adapter-sdk/media/942e7853-451e-4cf5-8884-09fb7d8dc19d.gif "942e7853-451e-4cf5-8884-09fb7d8dc19d")</span></span>  
  
## <a name="specify-user-name-and-password-headers-for-the-method"></a><span data-ttu-id="b725d-131">メソッドのユーザー名とパスワードのヘッダーを指定します。</span><span class="sxs-lookup"><span data-stu-id="b725d-131">Specify User Name and Password Headers for the Method</span></span>  
 <span data-ttu-id="b725d-132">WCF アダプターを呼び出すときに、LOB システムに渡されるユーザーの資格情報を提供する必要があります。</span><span class="sxs-lookup"><span data-stu-id="b725d-132">When calling a WCF adapter, you may have to provide user credentials that will be passed to the LOB system.</span></span> <span data-ttu-id="b725d-133">[手順 1: Web プロジェクトを作成するアダプター サービス開発ウィザードを使用して](../../adapters-and-accelerators/wcf-lob-adapter-sdk/step-1-use-the-adapter-service-development-wizard-to-create-the-web-project.md)、MyUserHeader および MyPassHeader フィールドにユーザー名とパスワード情報が提供されることを要求するようにエコー アダプターを構成します。</span><span class="sxs-lookup"><span data-stu-id="b725d-133">In [Step 1: Use the Adapter Service Development Wizard to Create the Web Project](../../adapters-and-accelerators/wcf-lob-adapter-sdk/step-1-use-the-adapter-service-development-wizard-to-create-the-web-project.md), you configured the Echo adapter to require that user name and password information be provided in the MyUserHeader and MyPassHeader fields.</span></span> <span data-ttu-id="b725d-134">このアプリケーション定義ファイルの同じフィールド名を使用する必要があります。</span><span class="sxs-lookup"><span data-stu-id="b725d-134">You must now use the same field names for this application definition file.</span></span>  
  
#### <a name="to-specify-user-name-and-password-headers"></a><span data-ttu-id="b725d-135">ユーザー名とパスワードのヘッダーを指定するには</span><span class="sxs-lookup"><span data-stu-id="b725d-135">To specify user name and password headers</span></span>  
  
1.  <span data-ttu-id="b725d-136">メタデータ オブジェクト ペインで、展開、 **EchoGreetings**  ノードの順に展開し、**メソッド**ノード。</span><span class="sxs-lookup"><span data-stu-id="b725d-136">In the Metadata Objects pane, expand the **EchoGreetings** node, and then expand the **Methods** node.</span></span>  
  
2.  <span data-ttu-id="b725d-137">クリックして、 **EchoGreetings**ノードのプロパティ ウィンドウで、省略記号ボタンをクリックし、 **(...)** ボタンをクリックして、**プロパティ**フィールドです。</span><span class="sxs-lookup"><span data-stu-id="b725d-137">Click the **EchoGreetings** node and, in the Properties pane, click the ellipsis **(…)** button in the **Properties** field.</span></span>  
  
3.  <span data-ttu-id="b725d-138">PropertyView コレクション エディター ウィンドウで、**追加**、し、、**名前**型、プロパティ ペインのフィールド**HttpHeaderUserName**です。</span><span class="sxs-lookup"><span data-stu-id="b725d-138">In the PropertyView Collection Editor window, click **Add**, and in the **Name** field of the Property pane, type  **HttpHeaderUserName**.</span></span>  
  
     <span data-ttu-id="b725d-139">![Username ヘッダー フィールドの指定](../../adapters-and-accelerators/wcf-lob-adapter-sdk/media/8da4d1b7-0792-407a-ba93-ba749138dd14.gif "8da4d1b7-0792-407a-ba93-ba749138dd14")</span><span class="sxs-lookup"><span data-stu-id="b725d-139">![Specify Username Header Fields](../../adapters-and-accelerators/wcf-lob-adapter-sdk/media/8da4d1b7-0792-407a-ba93-ba749138dd14.gif "8da4d1b7-0792-407a-ba93-ba749138dd14")</span></span>  
  
4.  <span data-ttu-id="b725d-140">**PropertyValue**フィールドに「 **MyUserHeader**です。</span><span class="sxs-lookup"><span data-stu-id="b725d-140">In the **PropertyValue**field, type **MyUserHeader**.</span></span>  
  
5.  <span data-ttu-id="b725d-141">をクリックして**追加**、およびプロパティ ペイン型**HttpHeaderPassword** [名前] フィールドを入力し、 **MyPassHeader**の**PropertyValue**フィールドです。</span><span class="sxs-lookup"><span data-stu-id="b725d-141">Click **Add**, and in the Property pane type **HttpHeaderPassword** for the Name field, then type **MyPassHeader** for the **PropertyValue** field.</span></span>  
  
6.  <span data-ttu-id="b725d-142">**[OK]** をクリックします。</span><span class="sxs-lookup"><span data-stu-id="b725d-142">Click **OK**.</span></span>  
  
## <a name="set-up-single-sign-on-for-connecting-to-the-echo-adapter"></a><span data-ttu-id="b725d-143">エコー アダプターに接続するためのシングル サインオンを設定します。</span><span class="sxs-lookup"><span data-stu-id="b725d-143">Set up Single Sign-On for Connecting to the Echo Adapter</span></span>  
 <span data-ttu-id="b725d-144">SharePoint からシングル サインオン情報を使用して、認証の値を持つ MyUserHeader および MyPassHeader を設定します。</span><span class="sxs-lookup"><span data-stu-id="b725d-144">SharePoint uses information from Single Sign-On to populate the MyUserHeader and MyPassHeader with authentication values.</span></span> <span data-ttu-id="b725d-145">シングル サインオンには、このアプリケーション定義ファイルをリンクするには、SecondarySsoApplicationId を指定する必要があります。</span><span class="sxs-lookup"><span data-stu-id="b725d-145">To link this application definition file to Single Sign-On, you must provide a SecondarySsoApplicationId.</span></span>  
  
#### <a name="to-set-the-secondaryssoapplicationid-property"></a><span data-ttu-id="b725d-146">SecondarySsoApplicationId のプロパティを設定するには</span><span class="sxs-lookup"><span data-stu-id="b725d-146">To set the SecondarySsoApplicationId property</span></span>  
  
1.  <span data-ttu-id="b725d-147">メタデータ オブジェクト ペインで、展開、 **EchoWSLOB**  ノードの順に展開し、**インスタンス**ノード。</span><span class="sxs-lookup"><span data-stu-id="b725d-147">In the Metadata Objects pane, expand the **EchoWSLOB** node, and then expand the **Instances** node.</span></span>  
  
2.  <span data-ttu-id="b725d-148">をクリックして**EchoWSLOB_Instance**、プロパティ ペインで、省略記号ボタンをクリックして **([...])** ボタンをクリックして、**プロパティ**フィールドです。</span><span class="sxs-lookup"><span data-stu-id="b725d-148">Click **EchoWSLOB_Instance**, and in the Properties pane, click the ellipsis **(…)** button in the **Properties** field.</span></span>  
  
3.  <span data-ttu-id="b725d-149">PropertyView コレクション エディター] ウィンドウで、[**追加**、プロパティ ウィンドウで、次のように入力します。 **SecondarySsoApplicationId**で、**名前**フィールドです。</span><span class="sxs-lookup"><span data-stu-id="b725d-149">In the PropertyView Collection Editor window, click **Add**, and in the Property pane, type **SecondarySsoApplicationId** in the **Name** field.</span></span>  
  
4.  <span data-ttu-id="b725d-150">**PropertyValue**フィールドに「 **EchoSSO**です。</span><span class="sxs-lookup"><span data-stu-id="b725d-150">In the **PropertyValue** field, type **EchoSSO**.</span></span>  
  
     <span data-ttu-id="b725d-151">![Secondaryssoapplicationid の](../../adapters-and-accelerators/wcf-lob-adapter-sdk/media/68e6be61-77af-46b1-8ff0-b8538c526228.gif "68e6be61-77af-46b1-8ff0-b8538c526228")</span><span class="sxs-lookup"><span data-stu-id="b725d-151">![Set the SecondarySsoApplicationId](../../adapters-and-accelerators/wcf-lob-adapter-sdk/media/68e6be61-77af-46b1-8ff0-b8538c526228.gif "68e6be61-77af-46b1-8ff0-b8538c526228")</span></span>  
  
5.  <span data-ttu-id="b725d-152">**[OK]** をクリックします。</span><span class="sxs-lookup"><span data-stu-id="b725d-152">Click **OK**.</span></span>  
  
## <a name="create-input-filters-and-default-values"></a><span data-ttu-id="b725d-153">入力フィルターと既定値を作成します。</span><span class="sxs-lookup"><span data-stu-id="b725d-153">Create Input Filters and Default Values</span></span>  
 <span data-ttu-id="b725d-154">アプリケーション定義ファイルを Web サービスに渡すことができるユーザーの入力を受け付けることがあります。</span><span class="sxs-lookup"><span data-stu-id="b725d-154">The application definition file must be able to  accept user input that can be passed to a Web service.</span></span> <span data-ttu-id="b725d-155">これを実現するには、次の一連のタスクを実行する必要があります。</span><span class="sxs-lookup"><span data-stu-id="b725d-155">To accomplish this, you must perform the following set of tasks:</span></span>  
  
#### <a name="to-create-a-filter-and-map-it-to-the-greeting-parameter"></a><span data-ttu-id="b725d-156">フィルターを作成してあいさつ文パラメーターにマップするには</span><span class="sxs-lookup"><span data-stu-id="b725d-156">To create a filter, and map it to the greeting parameter</span></span>  
  
1.  <span data-ttu-id="b725d-157">メタデータ オブジェクト ペインで、展開、 **EchoWSLOB**  ノードの順に展開し、**メソッド**ノード。</span><span class="sxs-lookup"><span data-stu-id="b725d-157">In the Metadata Objects pane, expand the **EchoWSLOB** node, and then expand the **Methods** node.</span></span>  
  
2.  <span data-ttu-id="b725d-158">展開、 **EchoGreetings**メソッドを右クリックして**フィルター**、クリックして**フィルターの追加**です。</span><span class="sxs-lookup"><span data-stu-id="b725d-158">Expand the **EchoGreetings** method, right-click **Filters**, and then click **Add Filter**.</span></span>  
  
3.  <span data-ttu-id="b725d-159">プロパティ ウィンドウで、次のように入力します。 **Greeting**で、**名前**フィールドです。</span><span class="sxs-lookup"><span data-stu-id="b725d-159">In the Properties pane, type **Greeting** in the **Name** field.</span></span>  
  
     <span data-ttu-id="b725d-160">![フィルター名の設定](../../adapters-and-accelerators/wcf-lob-adapter-sdk/media/74036b9e-7eec-4156-b238-840e67a2f00c.gif "74036b9e-7eec-4156-b238-840e67a2f00c")</span><span class="sxs-lookup"><span data-stu-id="b725d-160">![Set the Filter Name](../../adapters-and-accelerators/wcf-lob-adapter-sdk/media/74036b9e-7eec-4156-b238-840e67a2f00c.gif "74036b9e-7eec-4156-b238-840e67a2f00c")</span></span>  
  
4.  <span data-ttu-id="b725d-161">メタデータ オブジェクト ペインで、展開、 **EchoWSLOB**  ノードの順に展開し、**メソッド**ノード</span><span class="sxs-lookup"><span data-stu-id="b725d-161">In the Metadata Objects pane, expand the **EchoWSLOB** node, and then expand the **Methods** node</span></span>  
  
5.  <span data-ttu-id="b725d-162">展開、 **EchoGreetings**メソッドの順に展開し、**パラメーター**ノード。</span><span class="sxs-lookup"><span data-stu-id="b725d-162">Expand the **EchoGreetings** method, and then expand the **Parameters** node.</span></span>  
  
6.  <span data-ttu-id="b725d-163">展開、 **greeting**ノード、2 番目の順に展開および**greeting**ノード。</span><span class="sxs-lookup"><span data-stu-id="b725d-163">Expand the **greeting** node, and then expand the second **greeting** node.</span></span>  
  
7.  <span data-ttu-id="b725d-164">をクリックして、 **greetingText**ノード、プロパティ ウィンドウで、次のように選択します。 **Greeting**から、 **FilterDescriptor**  ボックスの一覧です。</span><span class="sxs-lookup"><span data-stu-id="b725d-164">Click the **greetingText** node, and in the Properties pane, select **Greeting** from the **FilterDescriptor** list.</span></span>  
  
#### <a name="to-create-a-finder-method-instance-for-the-echogreetings-method"></a><span data-ttu-id="b725d-165">EchoGreetings メソッドの Finder メソッド インスタンスを作成するには</span><span class="sxs-lookup"><span data-stu-id="b725d-165">To create a Finder method instance for the EchoGreetings method</span></span>  
  
1.  <span data-ttu-id="b725d-166">メタデータ オブジェクト ペインで、展開、 **EchoWSLOB**  ノードの順に展開し、**メソッド**ノード。</span><span class="sxs-lookup"><span data-stu-id="b725d-166">In the Metadata Objects pane, expand the **EchoWSLOB** node, and then expand the **Methods** node.</span></span>  
  
2.  <span data-ttu-id="b725d-167">展開、 **EchoGreetings**メソッドを右クリックして**インスタンス**、クリックして**メソッド インスタンスの追加**メソッド インスタンスの作成 ウィンドウを開きます。</span><span class="sxs-lookup"><span data-stu-id="b725d-167">Expand the **EchoGreetings** method, right-click **Instances**, and then click **Add Method Instance** to open the Create Method Instance window.</span></span>  
  
3.  <span data-ttu-id="b725d-168">メソッド インスタンスの作成] ウィンドウで、をクリックして**Finder**の**メソッド インスタンスの型**、し、[**返す**の**戻り値の TypeDescriptor**.</span><span class="sxs-lookup"><span data-stu-id="b725d-168">In the Create Method Instance window, click **Finder** for **Method Instance Type**, and then select **Return** for **Return TypeDescriptor**.</span></span>  
  
     <span data-ttu-id="b725d-169">![メソッド インスタンスの作成](../../adapters-and-accelerators/wcf-lob-adapter-sdk/media/a932a7a0-c004-46bf-af5c-cc7392bafa43.gif "a932a7a0-c004-46bf-af5c-cc7392bafa43")</span><span class="sxs-lookup"><span data-stu-id="b725d-169">![Create the Method Instance](../../adapters-and-accelerators/wcf-lob-adapter-sdk/media/a932a7a0-c004-46bf-af5c-cc7392bafa43.gif "a932a7a0-c004-46bf-af5c-cc7392bafa43")</span></span>  
  
4.  <span data-ttu-id="b725d-170">**[OK]** をクリックします。</span><span class="sxs-lookup"><span data-stu-id="b725d-170">Click **OK**.</span></span>  
  
5.  <span data-ttu-id="b725d-171">プロパティ ウィンドウで、次のように入力します。 **EchoGreetings_Instance**で、**名前**フィールドです。</span><span class="sxs-lookup"><span data-stu-id="b725d-171">In the Properties pane, type **EchoGreetings_Instance** in the **Name** field.</span></span>  
  
#### <a name="to-set-default-parameters"></a><span data-ttu-id="b725d-172">既定のパラメーターを設定するには</span><span class="sxs-lookup"><span data-stu-id="b725d-172">To set default parameters</span></span>  
  
1.  <span data-ttu-id="b725d-173">メタデータ オブジェクト ペインで、展開、 **EchoWSLOB**  ノードの順に展開し、**メソッド**ノード。</span><span class="sxs-lookup"><span data-stu-id="b725d-173">In the Metadata Objects pane, expand the **EchoWSLOB** node, and then expand the **Methods** node.</span></span>  
  
2.  <span data-ttu-id="b725d-174">展開、 **EchoGreetings**メソッドの順に展開し、**インスタンス**ノード。</span><span class="sxs-lookup"><span data-stu-id="b725d-174">Expand the **EchoGreetings** method, and then expand the **Instances** node.</span></span>  
  
3.  <span data-ttu-id="b725d-175">選択、 **EchoGreetings_Instance**メソッドをインスタンス化、およびプロパティ ウィンドウで、省略記号ボタン (...) をクリックして、 **DefaultValues**フィールドです。</span><span class="sxs-lookup"><span data-stu-id="b725d-175">Select the **EchoGreetings_Instance** method instance, and in the Properties pane, click the ellipsis button (…) in the **DefaultValues** field.</span></span>  
  
4.  <span data-ttu-id="b725d-176">編集ウィンドウで、展開、 **greeting**ノード、2 番目の順に展開および**greeting**ノード。</span><span class="sxs-lookup"><span data-stu-id="b725d-176">In the Edit window, expand the **greeting** node, and then expand the second **greeting** node.</span></span> <span data-ttu-id="b725d-177">展開して、**名前**ノードをツリー構造が完全に表示されるまでです。</span><span class="sxs-lookup"><span data-stu-id="b725d-177">Expand the **name** node, until the tree structure is fully displayed.</span></span>  
  
5.  <span data-ttu-id="b725d-178">編集ウィンドウでは、よう、フィールドの値を設定します。</span><span class="sxs-lookup"><span data-stu-id="b725d-178">In the Edit window, set the field values as follows:</span></span>  
  
    |<span data-ttu-id="b725d-179">設定対象</span><span class="sxs-lookup"><span data-stu-id="b725d-179">Set this</span></span>|<span data-ttu-id="b725d-180">次の値に設定</span><span class="sxs-lookup"><span data-stu-id="b725d-180">To this</span></span>|  
    |--------------|-------------|  
    |<span data-ttu-id="b725d-181">**id**</span><span class="sxs-lookup"><span data-stu-id="b725d-181">**id**</span></span>|<span data-ttu-id="b725d-182">GUID 値では、たとえば 27829ed4 583a-40-c fb8cdd9dc98d ad87 4。</span><span class="sxs-lookup"><span data-stu-id="b725d-182">A GUID value, for example 27829ed4-583a-40c4-ad87-fb8cdd9dc98d.</span></span>|  
    |<span data-ttu-id="b725d-183">**sentDateTime**</span><span class="sxs-lookup"><span data-stu-id="b725d-183">**sentDateTime**</span></span>|<span data-ttu-id="b725d-184">現在の日付と時刻、に対する 05/15/08 のたとえば午前 9時 12分</span><span class="sxs-lookup"><span data-stu-id="b725d-184">The current date and time, for example 05/15/08 9:12 AM</span></span>|  
    |<span data-ttu-id="b725d-185">**firstName**</span><span class="sxs-lookup"><span data-stu-id="b725d-185">**firstName**</span></span>|<span data-ttu-id="b725d-186">First</span><span class="sxs-lookup"><span data-stu-id="b725d-186">First</span></span>|  
    |<span data-ttu-id="b725d-187">**middleName**</span><span class="sxs-lookup"><span data-stu-id="b725d-187">**middleName**</span></span>|<span data-ttu-id="b725d-188">Middle</span><span class="sxs-lookup"><span data-stu-id="b725d-188">Middle</span></span>|  
    |<span data-ttu-id="b725d-189">**[氏名]**</span><span class="sxs-lookup"><span data-stu-id="b725d-189">**lastName**</span></span>|<span data-ttu-id="b725d-190">Last</span><span class="sxs-lookup"><span data-stu-id="b725d-190">Last</span></span>|  
  
     <span data-ttu-id="b725d-191">![既定のパラメーター](../../adapters-and-accelerators/wcf-lob-adapter-sdk/media/70250957-9680-48ce-8bce-420ff18bb47a.gif "70250957-9680-48ce-8bce-420ff18bb47a")</span><span class="sxs-lookup"><span data-stu-id="b725d-191">![Default Parameters](../../adapters-and-accelerators/wcf-lob-adapter-sdk/media/70250957-9680-48ce-8bce-420ff18bb47a.gif "70250957-9680-48ce-8bce-420ff18bb47a")</span></span>  
  
6.  <span data-ttu-id="b725d-192">**[閉じる]** をクリックします。</span><span class="sxs-lookup"><span data-stu-id="b725d-192">Click **Close**.</span></span>  
  
### <a name="to-export-the-application-definition-file"></a><span data-ttu-id="b725d-193">アプリケーション定義ファイルをエクスポートするには</span><span class="sxs-lookup"><span data-stu-id="b725d-193">To export the application definition file</span></span>  
  
1.  <span data-ttu-id="b725d-194">メタデータ オブジェクト ペインで右クリックし、 **EchoWSLOB**ノードをクリックして**エクスポート**です。</span><span class="sxs-lookup"><span data-stu-id="b725d-194">In the Metadata Objects pane, right-click the **EchoWSLOB** node, and then click **Export**.</span></span>  
  
2.  <span data-ttu-id="b725d-195">EchoWS.xml としてファイルを保存します。</span><span class="sxs-lookup"><span data-stu-id="b725d-195">Save the file as EchoWS.xml.</span></span>  
  
## <a name="what-did-i-just-do"></a><span data-ttu-id="b725d-196">でしただけは何ですか。</span><span class="sxs-lookup"><span data-stu-id="b725d-196">What did I just do?</span></span>  
 <span data-ttu-id="b725d-197">ビジネス データ カタログ定義エディター ツールを使用する IIS でホストされているアダプターとの接続を有効にするのに Microsoft Office SharePoint Server 2007 にインポートできるアプリケーション定義ファイルを作成します。</span><span class="sxs-lookup"><span data-stu-id="b725d-197">You have used the Business Data Catalog Definition Editor tool to create an application definition file that can be imported into Microsoft Office SharePoint Server 2007 to enable connectivity with your adapter that is hosted in IIS.</span></span>  
  
## <a name="next-steps"></a><span data-ttu-id="b725d-198">次の手順</span><span class="sxs-lookup"><span data-stu-id="b725d-198">Next Steps</span></span>  
 <span data-ttu-id="b725d-199">この手順で作成したアプリケーション定義ファイルに基づく SharePoint アプリケーションを作成する必要がありますようになりました。</span><span class="sxs-lookup"><span data-stu-id="b725d-199">You must now create a SharePoint application based on the application definition file created in this step.</span></span> <span data-ttu-id="b725d-200">参照してください[手順 4: アダプターにアクセスする Sharepoint アプリケーションを作成](../../adapters-and-accelerators/wcf-lob-adapter-sdk/step-4-create-a-sharepoint-application-to-access-the-adapter.md)手順についてはします。</span><span class="sxs-lookup"><span data-stu-id="b725d-200">See [Step 4: Create a Sharepoint Application to Access the Adapter](../../adapters-and-accelerators/wcf-lob-adapter-sdk/step-4-create-a-sharepoint-application-to-access-the-adapter.md) for instructions.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="b725d-201">参照</span><span class="sxs-lookup"><span data-stu-id="b725d-201">See Also</span></span>  
 [<span data-ttu-id="b725d-202">チュートリアル 3: IIS でエコー アダプターをホストします。</span><span class="sxs-lookup"><span data-stu-id="b725d-202">Tutorial 3: Hosting the Echo Adapter in IIS</span></span>](../../adapters-and-accelerators/wcf-lob-adapter-sdk/tutorial-3-hosting-the-echo-adapter-in-iis.md)