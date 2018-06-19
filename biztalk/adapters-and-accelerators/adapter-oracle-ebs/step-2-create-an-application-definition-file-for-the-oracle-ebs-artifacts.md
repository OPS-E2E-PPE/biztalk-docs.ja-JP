---
title: '手順 2: Oracle E-business Suite 成果物のためのアプリケーション定義ファイルの作成 |Microsoft ドキュメント'
ms.custom: ''
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: ''
ms.suite: ''
ms.tgt_pltfrm: ''
ms.topic: article
ms.assetid: 2665afde-0337-4795-ab4c-6223d39fdf9c
caps.latest.revision: 10
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: 4ed4340893d351d8406212b585e6216de19c634c
ms.sourcegitcommit: cb908c540d8f1a692d01dc8f313e16cb4b4e696d
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 09/20/2017
ms.locfileid: "22219306"
---
# <a name="step-2-create-an-application-definition-file-for-the-oracle-e-business-suite-artifacts"></a><span data-ttu-id="f2dc5-102">手順 2: Oracle E-business Suite 成果物のためのアプリケーション定義ファイルを作成します。</span><span class="sxs-lookup"><span data-stu-id="f2dc5-102">Step 2: Create an application definition file for the Oracle E-Business Suite artifacts</span></span>
<span data-ttu-id="f2dc5-103">![手順 4 2](../../adapters-and-accelerators/adapter-oracle-ebs/media/step-2of4.gif "Step_2of4")</span><span class="sxs-lookup"><span data-stu-id="f2dc5-103">![Step 2 of 4](../../adapters-and-accelerators/adapter-oracle-ebs/media/step-2of4.gif "Step_2of4")</span></span>  
  
 <span data-ttu-id="f2dc5-104">**所要時間:** 15 分</span><span class="sxs-lookup"><span data-stu-id="f2dc5-104">**Time to complete:** 15 minutes</span></span>  
  
 <span data-ttu-id="f2dc5-105">**目標:** Microsoft SharePoint Server でビジネス データ カタログの機能を公開し、ポータルに基幹業務 (LOB) アプリケーションからのデータが組み込まれています。</span><span class="sxs-lookup"><span data-stu-id="f2dc5-105">**Objective:** The Business Data Catalog feature in Microsoft SharePoint Server exposes and incorporates data from line-of-business (LOB) applications into portals.</span></span> <span data-ttu-id="f2dc5-106">ポータル サイトにこのデータを組み込むには、Microsoft Office SharePoint Server を使用できるアプリケーション定義ファイルをビルドする必要があります。</span><span class="sxs-lookup"><span data-stu-id="f2dc5-106">To incorporate this data into your portal site, you must build an application definition file that Microsoft Office SharePoint Server can consume.</span></span>  
  
 <span data-ttu-id="f2dc5-107">Microsoft Office SharePoint Server 2007 SDK で利用可能なビジネス データ カタログ定義エディター ツールでは、ビジネス データ カタログ アプリケーション定義ファイルを作成することができます。</span><span class="sxs-lookup"><span data-stu-id="f2dc5-107">The Business Data Catalog Definition Editor tool, available with Microsoft Office SharePoint Server 2007 SDK, enables you to create an application definition file for the Business Data Catalog.</span></span> <span data-ttu-id="f2dc5-108">手動で作成、ファイル、XML エディター必要はありませんので、このツールは自動的に定義ファイルの XML ファイルを生成します。</span><span class="sxs-lookup"><span data-stu-id="f2dc5-108">This tool automatically generates an XML file for the definition file, so you do not need to manually create the file in an XML editor.</span></span>  
  
 <span data-ttu-id="f2dc5-109">作成している Microsoft Office SharePoint Server アプリケーションの目的には。</span><span class="sxs-lookup"><span data-stu-id="f2dc5-109">The purpose of the Microsoft Office SharePoint Server application that you are creating is to:</span></span>  
  
-   <span data-ttu-id="f2dc5-110">ビジネス データ一覧 Web パーツを使用して MS_SAMPLE_EMPLOYEE インターフェイス テーブル内の従業員のクエリは、従業員の名前に基づいています。</span><span class="sxs-lookup"><span data-stu-id="f2dc5-110">Query for an employee in the MS_SAMPLE_EMPLOYEE interface table using a Business Data List Web Part based on an employee name.</span></span>  
  
-   <span data-ttu-id="f2dc5-111">Microsoft Office SharePoint Server から MS_SAMPLE_EMPLOYEE インターフェイス テーブルにフルテキスト検索を実行します。</span><span class="sxs-lookup"><span data-stu-id="f2dc5-111">Perform a full-text search from Microsoft Office SharePoint Server on the MS_SAMPLE_EMPLOYEE interface table.</span></span>  
  
 <span data-ttu-id="f2dc5-112">これらの要件ごとに、一連のビジネス データ カタログ定義エディター ツールでタスクを完了する必要があります。</span><span class="sxs-lookup"><span data-stu-id="f2dc5-112">For each of these requirements, you must complete a set of tasks in the Business Data Catalog Definition Editor tool.</span></span> <span data-ttu-id="f2dc5-113">このトピックでは、これらのタスクを実行する方法についてを説明します。</span><span class="sxs-lookup"><span data-stu-id="f2dc5-113">This topic provides instructions on how to perform these tasks.</span></span>  
  
## <a name="prerequisites"></a><span data-ttu-id="f2dc5-114">前提条件</span><span class="sxs-lookup"><span data-stu-id="f2dc5-114">Prerequisites</span></span>  
  
-   <span data-ttu-id="f2dc5-115">ビジネス データ カタログの定義を Microsoft Office SharePoint Server 2007 SDK の一部としてインストールされているエディターを行ったことを確認します。</span><span class="sxs-lookup"><span data-stu-id="f2dc5-115">Be sure that you have the Business Data Catalog Definition Editor installed as part of the Microsoft Office SharePoint Server 2007 SDK.</span></span> <span data-ttu-id="f2dc5-116">SDK をダウンロードする[http://go.microsoft.com/fwlink/?LinkId=104130](http://go.microsoft.com/fwlink/?LinkId=104130)です。</span><span class="sxs-lookup"><span data-stu-id="f2dc5-116">You can download the SDK from [http://go.microsoft.com/fwlink/?LinkId=104130](http://go.microsoft.com/fwlink/?LinkId=104130).</span></span>  
  
-   <span data-ttu-id="f2dc5-117">」の説明に従って、WCF サービスを発行[手順 1: create Oracle E-business アダプターを使用し、WCF サービスを発行](../../adapters-and-accelerators/adapter-oracle-ebs/step-1-use-the-oracle-e-business-adapter-to-create-and-publish-a-wcf-service.md)です。</span><span class="sxs-lookup"><span data-stu-id="f2dc5-117">Publish the WCF service as described in [Step 1: Use the Oracle E-Business Adapter to Create and Publish a WCF Service](../../adapters-and-accelerators/adapter-oracle-ebs/step-1-use-the-oracle-e-business-adapter-to-create-and-publish-a-wcf-service.md).</span></span>  
  

  
##  <a name="Connect"></a><span data-ttu-id="f2dc5-118">WCF LOB サービスに接続し、エンティティの作成</span><span class="sxs-lookup"><span data-stu-id="f2dc5-118">Connect to the WCF LOB Service and Create Entity</span></span>  
 <span data-ttu-id="f2dc5-119">Web サービス記述言語 (WSDL) サービスを抽出する WCF サービスに接続する必要があります。</span><span class="sxs-lookup"><span data-stu-id="f2dc5-119">You must connect to the WCF service to extract the Web Services Description Language (WSDL) for the service.</span></span> <span data-ttu-id="f2dc5-120">ビジネス データ カタログ定義エディターは、WSDL からメソッドを抽出します。</span><span class="sxs-lookup"><span data-stu-id="f2dc5-120">From the WSDL, the Business Data Catalog Definition Editor extracts the methods.</span></span> <span data-ttu-id="f2dc5-121">これらのメソッドは、エンティティの作成に使用できます。</span><span class="sxs-lookup"><span data-stu-id="f2dc5-121">These methods can be used to create entities.</span></span> <span data-ttu-id="f2dc5-122">このチュートリアルでは、エンティティが作成されます。</span><span class="sxs-lookup"><span data-stu-id="f2dc5-122">For this tutorial, an entity is created.</span></span>  
  
#### <a name="to-connect-to-the-wcf-service-and-create-entities"></a><span data-ttu-id="f2dc5-123">WCF サービスに接続し、エンティティを作成するには</span><span class="sxs-lookup"><span data-stu-id="f2dc5-123">To connect to the WCF service and create entities</span></span>  
  
1.  <span data-ttu-id="f2dc5-124">ビジネス データ カタログ定義エディターを起動します。</span><span class="sxs-lookup"><span data-stu-id="f2dc5-124">Start the Business Data Catalog Definition Editor.</span></span> <span data-ttu-id="f2dc5-125">**開始** メニューのをクリックして**Microsoft ビジネス データ カタログ定義エディター**です。</span><span class="sxs-lookup"><span data-stu-id="f2dc5-125">On the **Start** menu, click **Microsoft Business Data Catalog Definition Editor**.</span></span>  
  
2.  <span data-ttu-id="f2dc5-126">ツールバーで、をクリックして**LOB システムの追加**です。</span><span class="sxs-lookup"><span data-stu-id="f2dc5-126">On the toolbar, click **Add LOB System**.</span></span>  
  
3.  <span data-ttu-id="f2dc5-127">LOB システムの追加] ウィンドウで、[ **web サービスへの接続**です。</span><span class="sxs-lookup"><span data-stu-id="f2dc5-127">In the Add LOB System window, click **Connect to Webservice**.</span></span>  
  
4.  <span data-ttu-id="f2dc5-128">**URL**ボックスには、WCF サービスの URL を入力します。</span><span class="sxs-lookup"><span data-stu-id="f2dc5-128">In the **URL** box, type the URL for the WCF service.</span></span> <span data-ttu-id="f2dc5-129">このチュートリアルでは、URL になります。</span><span class="sxs-lookup"><span data-stu-id="f2dc5-129">For this tutorial, the URL will be:</span></span>  
  
    ```  
    https://<COMPUTER_NAME>:<PORT_NUMBER>/MS_SAMPLE_EMPLOYEE/InterfaceTables_FND_APPS_MS_SAMPLE_EMPLOYEE.svc  
    ```  
  
     <span data-ttu-id="f2dc5-130">WCF サービスが」の説明に従って、正常に発行されるかどうかをテストするときに、URL が使用可能な[手順 1: create Oracle E-business アダプターを使用し、WCF サービスを発行](../../adapters-and-accelerators/adapter-oracle-ebs/step-1-use-the-oracle-e-business-adapter-to-create-and-publish-a-wcf-service.md)です。</span><span class="sxs-lookup"><span data-stu-id="f2dc5-130">The URL is available when you test whether the WCF service is published successfully, as described in [Step 1: Use the Oracle E-Business Adapter to Create and Publish a WCF Service](../../adapters-and-accelerators/adapter-oracle-ebs/step-1-use-the-oracle-e-business-adapter-to-create-and-publish-a-wcf-service.md).</span></span>  
  
5.  <span data-ttu-id="f2dc5-131">**[接続]** をクリックします。</span><span class="sxs-lookup"><span data-stu-id="f2dc5-131">Click **Connect**.</span></span>  
  
6.  <span data-ttu-id="f2dc5-132">WCF アダプター サービス開発ウィザードで選択した操作を表示するをクリックして、 **Web メソッドの追加**タブです。次のメソッドが表示されます:**選択**です。</span><span class="sxs-lookup"><span data-stu-id="f2dc5-132">To see the operations you selected in the WCF Adapter Service Development Wizard, click the **Add Web Method** tab. You will see the following method: **Select**.</span></span>  
  
7.  <span data-ttu-id="f2dc5-133">ドラッグ、**選択**デザイン画面にメソッドです。</span><span class="sxs-lookup"><span data-stu-id="f2dc5-133">Drag the **Select** methods to the Design Surface.</span></span> <span data-ttu-id="f2dc5-134">メソッドをデザイン画面にドラッグするとエンティティが作成され、メソッドがそのエンティティの一部になります。</span><span class="sxs-lookup"><span data-stu-id="f2dc5-134">As you drag the method to the Design Surface, an entity is created, and the method becomes part of that entity.</span></span>  
  
     <span data-ttu-id="f2dc5-135">![デザイン画面に Select メソッドの追加](../../adapters-and-accelerators/adapter-oracle-ebs/media/05-add-lob-system.gif "05 _ add_lob_system")</span><span class="sxs-lookup"><span data-stu-id="f2dc5-135">![Add Select method to the Design Surface](../../adapters-and-accelerators/adapter-oracle-ebs/media/05-add-lob-system.gif "05_Add_LOB_System")</span></span>  
  
8.  <span data-ttu-id="f2dc5-136">**[OK]** をクリックします。</span><span class="sxs-lookup"><span data-stu-id="f2dc5-136">Click **OK**.</span></span>  
  
9. <span data-ttu-id="f2dc5-137">**LOB システムの名前を入力** ダイアログ ボックスに名前を入力、 **LOB システム名**ボックス。</span><span class="sxs-lookup"><span data-stu-id="f2dc5-137">In the **Enter the name for the LOB System** dialog box, type a name in the **LOB System Name** box.</span></span> <span data-ttu-id="f2dc5-138">この例では、呼び出すこと**MS_SAMPLE_EMPLOYEE**、順にクリック**OK**です。</span><span class="sxs-lookup"><span data-stu-id="f2dc5-138">For this example, call it **MS_SAMPLE_EMPLOYEE**, and then click **OK**.</span></span>  
  
10. <span data-ttu-id="f2dc5-139">ビジネス データ カタログ定義エディターで、新しく作成されたエンティティと表示されている**Entity0**です。</span><span class="sxs-lookup"><span data-stu-id="f2dc5-139">In the Business Data Catalog Definition Editor, the newly created entity is listed as **Entity0**.</span></span> <span data-ttu-id="f2dc5-140">エンティティの名前を変更**従業員**です。</span><span class="sxs-lookup"><span data-stu-id="f2dc5-140">Rename the entity to **Employee**.</span></span> <span data-ttu-id="f2dc5-141">エンティティの名前を変更する次の手順に従います。</span><span class="sxs-lookup"><span data-stu-id="f2dc5-141">Perform the following steps to rename the entity:</span></span>  
  
    1.  <span data-ttu-id="f2dc5-142">展開、 **MS_SAMPLE_EMPLOYEE**  ノードの順に展開し、**エンティティ**ノード。</span><span class="sxs-lookup"><span data-stu-id="f2dc5-142">Expand the **MS_SAMPLE_EMPLOYEE** node, and then expand the **Entities** node.</span></span>  
  
    2.  <span data-ttu-id="f2dc5-143">選択、 **Entity0**ノード。</span><span class="sxs-lookup"><span data-stu-id="f2dc5-143">Select the **Entity0** node.</span></span>  
  
    3.  <span data-ttu-id="f2dc5-144">プロパティ ウィンドウで、次のように入力します。**従業員**で、**名前**ボックス。</span><span class="sxs-lookup"><span data-stu-id="f2dc5-144">In the Properties pane, type **Employee** in the **Name** box.</span></span>  
  
         <span data-ttu-id="f2dc5-145">![エンティティの名前変更](../../adapters-and-accelerators/adapter-oracle-ebs/media/06-entity-name.gif "06 _ entity_name")</span><span class="sxs-lookup"><span data-stu-id="f2dc5-145">![Rename the entity](../../adapters-and-accelerators/adapter-oracle-ebs/media/06-entity-name.gif "06_Entity_Name")</span></span>  
  
##  <a name="Headers"></a><span data-ttu-id="f2dc5-146">メソッドのユーザー名とパスワードのヘッダーを指定します。</span><span class="sxs-lookup"><span data-stu-id="f2dc5-146">Specify User Name and Password Headers for the Methods</span></span>  
 <span data-ttu-id="f2dc5-147">内のエンドポイント動作の構成の一部としてユーザー名とパスワードのヘッダーを指定した Oracle E-business Suite で MS_SAMPLE_EMPLOYEE インターフェイス テーブルに対する Select 操作の WCF サービスの作成、ときに[手順 1: Oracle の使用作成し、WCF サービスを発行 E-business アダプター](../../adapters-and-accelerators/adapter-oracle-ebs/step-1-use-the-oracle-e-business-adapter-to-create-and-publish-a-wcf-service.md)です。</span><span class="sxs-lookup"><span data-stu-id="f2dc5-147">When creating a WCF service for the Select operation on the MS_SAMPLE_EMPLOYEE interface table in Oracle E-Business Suite, you specified user name and password headers as part of the endpoint behavior configuration in [Step 1: Use the Oracle E-Business Adapter to Create and Publish a WCF Service](../../adapters-and-accelerators/adapter-oracle-ebs/step-1-use-the-oracle-e-business-adapter-to-create-and-publish-a-wcf-service.md).</span></span> <span data-ttu-id="f2dc5-148">Select メソッドのプロパティに同じ値を指定する必要があります。</span><span class="sxs-lookup"><span data-stu-id="f2dc5-148">You must specify the same values for the Select method property.</span></span>  
  
#### <a name="to-specify-user-name-and-password-headers-for-the-select-method"></a><span data-ttu-id="f2dc5-149">Select メソッドのユーザー名とパスワードのヘッダーを指定するには</span><span class="sxs-lookup"><span data-stu-id="f2dc5-149">To specify user name and password headers for the Select method</span></span>  
  
1.  <span data-ttu-id="f2dc5-150">メタデータ オブジェクト ペインで、展開、**従業員** ノードの順に展開し、**メソッド**ノード。</span><span class="sxs-lookup"><span data-stu-id="f2dc5-150">In the Metadata Objects pane, expand the **Employee** node, and then expand the **Methods** node.</span></span>  
  
2.  <span data-ttu-id="f2dc5-151">をクリックして、**選択**ノード、プロパティ ペインでに対して省略記号 (...) ボタンをクリックし、**プロパティ**ボックス。</span><span class="sxs-lookup"><span data-stu-id="f2dc5-151">Click the **Select** node, and in the Properties pane click the ellipsis (…) button against the **Properties** box.</span></span>  
  
3.  <span data-ttu-id="f2dc5-152">PropertyView コレクション エディター] ウィンドウで、[**追加**、プロパティ ウィンドウで、次のように入力します。 **HttpHeaderUserName**の、**名前**ボックス。</span><span class="sxs-lookup"><span data-stu-id="f2dc5-152">In the PropertyView Collection Editor window, click **Add**, and in the Property pane, type **HttpHeaderUserName** for the **Name** box.</span></span> <span data-ttu-id="f2dc5-153">型**MyUserHeader**の**PropertyValue**ボックス。</span><span class="sxs-lookup"><span data-stu-id="f2dc5-153">Type **MyUserHeader** for the **PropertyValue** box.</span></span> <span data-ttu-id="f2dc5-154">選択**System.String**の**型**ボックス。</span><span class="sxs-lookup"><span data-stu-id="f2dc5-154">Select **System.String** for the **Type** box.</span></span>  
  
4.  <span data-ttu-id="f2dc5-155">PropertyView コレクション エディター] ウィンドウで、[**追加**、プロパティ ウィンドウで、次のように入力します。 **HttpHeaderPassword**の、**名前**ボックス。</span><span class="sxs-lookup"><span data-stu-id="f2dc5-155">In the PropertyView Collection Editor window, click **Add**, and in the Property pane, type **HttpHeaderPassword** for the **Name** box.</span></span> <span data-ttu-id="f2dc5-156">同様に、入力**MyPasswordHeader**の**PropertyValue**ボックス。</span><span class="sxs-lookup"><span data-stu-id="f2dc5-156">Similarly, type **MyPasswordHeader** for the **PropertyValue** box.</span></span> <span data-ttu-id="f2dc5-157">選択**System.String**の**型**ボックス。</span><span class="sxs-lookup"><span data-stu-id="f2dc5-157">Select **System.String** for the **Type** box.</span></span>  
  
     <span data-ttu-id="f2dc5-158">![プロパティを追加](../../adapters-and-accelerators/adapter-oracle-ebs/media/07-propertviewcollection-editor.gif "07 _ propertviewcollection_editor")</span><span class="sxs-lookup"><span data-stu-id="f2dc5-158">![Add a property](../../adapters-and-accelerators/adapter-oracle-ebs/media/07-propertviewcollection-editor.gif "07_PropertViewCollection_Editor")</span></span>  
  
5.  <span data-ttu-id="f2dc5-159">**[OK]** をクリックします。</span><span class="sxs-lookup"><span data-stu-id="f2dc5-159">Click **OK**.</span></span>  
  
##  <a name="Scenario1"></a><span data-ttu-id="f2dc5-160">ビジネス データ一覧 Web パーツを使用している従業員のシナリオ 1: クエリ</span><span class="sxs-lookup"><span data-stu-id="f2dc5-160">Scenario 1: Query for Employees using a Business Data List Web Part</span></span>  
 <span data-ttu-id="f2dc5-161">従業員がビジネス データ一覧 Web パーツを検索するために使用して従業員の名前に基づくできるアプリケーション定義ファイルを作成するには、次の一連のタスクを行う必要があります。</span><span class="sxs-lookup"><span data-stu-id="f2dc5-161">To create an application definition file that can be used to search for employees from a Business Data List Web Part and based on employee name, you must perform the following set of tasks.</span></span>  
  
1.  <span data-ttu-id="f2dc5-162">**選択**メソッド、フィルターを作成し、マップ、**フィルター**パラメーター。</span><span class="sxs-lookup"><span data-stu-id="f2dc5-162">In the **Select** method, create a filter and map it to the **FILTER** parameter.</span></span>  
  
2.  <span data-ttu-id="f2dc5-163">作成、 **Finder**メソッド インスタンスの**選択**メソッドです。</span><span class="sxs-lookup"><span data-stu-id="f2dc5-163">Create a **Finder** method instance for the **Select** method.</span></span> <span data-ttu-id="f2dc5-164">A **Finder**メソッドはフィルターに基づくレコードの一覧を取得します。</span><span class="sxs-lookup"><span data-stu-id="f2dc5-164">A **Finder** method retrieves a list of records based on a filter.</span></span>  
  
#### <a name="to-create-a-filter-and-map-it-to-the-filter-parameter"></a><span data-ttu-id="f2dc5-165">フィルターを作成して、フィルター パラメーターにマップするには</span><span class="sxs-lookup"><span data-stu-id="f2dc5-165">To create a filter, and map it to the FILTER parameter</span></span>  
  
1.  <span data-ttu-id="f2dc5-166">フィルターを作成します。</span><span class="sxs-lookup"><span data-stu-id="f2dc5-166">Create a filter.</span></span>  
  
    1.  <span data-ttu-id="f2dc5-167">メタデータ オブジェクト ペインで、展開、**従業員** ノードの順に展開し、**メソッド**ノード。</span><span class="sxs-lookup"><span data-stu-id="f2dc5-167">In the Metadata Objects pane, expand the **Employee** node, and then expand the **Methods** node.</span></span>  
  
    2.  <span data-ttu-id="f2dc5-168">展開、**選択**メソッドを右クリックして**フィルター**、順にクリック**フィルターの追加**です。</span><span class="sxs-lookup"><span data-stu-id="f2dc5-168">Expand the **Select** method, right-click **Filters**, and then click **Add Filter**.</span></span>  
  
         <span data-ttu-id="f2dc5-169">![SELECT メソッドにフィルターを追加](../../adapters-and-accelerators/adapter-oracle-ebs/media/08-add-filter.gif "08 _ add_filter")</span><span class="sxs-lookup"><span data-stu-id="f2dc5-169">![Add a filter to the SELECT method](../../adapters-and-accelerators/adapter-oracle-ebs/media/08-add-filter.gif "08_Add_Filter")</span></span>  
  
    3.  <span data-ttu-id="f2dc5-170">プロパティ ペインでの**FilterType**プロパティで、 **Equals**です。</span><span class="sxs-lookup"><span data-stu-id="f2dc5-170">In the Properties pane, for the **FilterType** property, select **Equals**.</span></span>  
  
    4.  <span data-ttu-id="f2dc5-171">プロパティ ウィンドウで、次のように入力します。 **EmployeeName**で、**名前**ボックス。</span><span class="sxs-lookup"><span data-stu-id="f2dc5-171">In the Properties pane, type **EmployeeName** in the **Name** box.</span></span>  
  
         <span data-ttu-id="f2dc5-172">![フィルター プロパティを指定](../../adapters-and-accelerators/adapter-oracle-ebs/media/09-filter-properties.gif "09 _ filter_properties")</span><span class="sxs-lookup"><span data-stu-id="f2dc5-172">![Specify filter properties](../../adapters-and-accelerators/adapter-oracle-ebs/media/09-filter-properties.gif "09_Filter_Properties")</span></span>  
  
2.  <span data-ttu-id="f2dc5-173">マップをフィルター、**フィルター**内のパラメーター、**選択**メソッドです。</span><span class="sxs-lookup"><span data-stu-id="f2dc5-173">Map the filter to the **FILTER** parameter in the **Select** method.</span></span>  
  
    1.  <span data-ttu-id="f2dc5-174">メタデータ オブジェクト ペインで、展開、**従業員** ノードの順に展開し、**メソッド**ノード。</span><span class="sxs-lookup"><span data-stu-id="f2dc5-174">In the Metadata Objects pane, expand the **Employee** node, and then expand the **Methods** node.</span></span>  
  
    2.  <span data-ttu-id="f2dc5-175">展開、**選択**メソッドの順に展開し、**パラメーター**ノード。</span><span class="sxs-lookup"><span data-stu-id="f2dc5-175">Expand the **Select** method, and then expand the **Parameters** node.</span></span>  
  
    3.  <span data-ttu-id="f2dc5-176">展開、**フィルター**ノード、2 つ目のクリックと**フィルター**ノード。</span><span class="sxs-lookup"><span data-stu-id="f2dc5-176">Expand the **FILTER** node, and click the second **FILTER** node.</span></span>  
  
    4.  <span data-ttu-id="f2dc5-177">プロパティ ウィンドウで、次のように選択します。 **EmployeeName**から、 **FilterDescriptor**  ボックスの一覧です。</span><span class="sxs-lookup"><span data-stu-id="f2dc5-177">In the Properties pane, select **EmployeeName** from the **FilterDescriptor** list.</span></span>  
  
         <span data-ttu-id="f2dc5-178">![フィルターを Select メソッド パラメーターにマップ](../../adapters-and-accelerators/adapter-oracle-ebs/media/10-map-filter.gif "10_Map_Filter")</span><span class="sxs-lookup"><span data-stu-id="f2dc5-178">![Map the filter to the Select method parameter](../../adapters-and-accelerators/adapter-oracle-ebs/media/10-map-filter.gif "10_Map_Filter")</span></span>  
  
#### <a name="to-create-a-finder-method-instance-for-the-select-method"></a><span data-ttu-id="f2dc5-179">Select メソッドの Finder メソッド インスタンスを作成するには</span><span class="sxs-lookup"><span data-stu-id="f2dc5-179">To create a Finder method instance for the Select method</span></span>  
  
1.  <span data-ttu-id="f2dc5-180">メタデータ オブジェクト ペインで、展開、**従業員** ノードの順に展開し、**メソッド**ノード。</span><span class="sxs-lookup"><span data-stu-id="f2dc5-180">In the Metadata Objects pane, expand the **Employee** node, and then expand the **Methods** node.</span></span>  
  
2.  <span data-ttu-id="f2dc5-181">展開、**を選択** ノードを右クリックして**インスタンス**、順にクリック**メソッド インスタンスの追加**です。</span><span class="sxs-lookup"><span data-stu-id="f2dc5-181">Expand the **Select** node, right-click **Instances**, and then click **Add Method Instance**.</span></span>  
  
     <span data-ttu-id="f2dc5-182">![メソッド インスタンスの追加](../../adapters-and-accelerators/adapter-oracle-ebs/media/11-add-method-instance.gif "11 _ add_method_instance")</span><span class="sxs-lookup"><span data-stu-id="f2dc5-182">![Add a method instance](../../adapters-and-accelerators/adapter-oracle-ebs/media/11-add-method-instance.gif "11_Add_Method_Instance")</span></span>  
  
3.  <span data-ttu-id="f2dc5-183">メソッド インスタンスの作成 ウィンドウで、をクリックして**Finder**の**メソッド インスタンスの型**です。</span><span class="sxs-lookup"><span data-stu-id="f2dc5-183">In the Create Method Instance window, click **Finder** for **Method Instance Type**.</span></span> <span data-ttu-id="f2dc5-184">選択**返す**の**TypeDescriptor を返す**です。</span><span class="sxs-lookup"><span data-stu-id="f2dc5-184">Select **Return** for **Return TypeDescriptor**.</span></span>  
  
     <span data-ttu-id="f2dc5-185">![Finder メソッド インスタンスの作成](../../adapters-and-accelerators/adapter-oracle-ebs/media/12-create-method-instance.gif "12 _ create_method_instance")</span><span class="sxs-lookup"><span data-stu-id="f2dc5-185">![Create a Finder method instance](../../adapters-and-accelerators/adapter-oracle-ebs/media/12-create-method-instance.gif "12_Create_Method_Instance")</span></span>  
  
4.  <span data-ttu-id="f2dc5-186">**[OK]** をクリックします。</span><span class="sxs-lookup"><span data-stu-id="f2dc5-186">Click **OK**.</span></span>  
  
5.  <span data-ttu-id="f2dc5-187">プロパティ ウィンドウで、次のように入力します。 **Finder_Instance**で、**名前**ボックス。</span><span class="sxs-lookup"><span data-stu-id="f2dc5-187">In the Properties pane, type **Finder_Instance** in the **Name** box.</span></span>  
  
     <span data-ttu-id="f2dc5-188">![Finder メソッド インスタンスの名前を指定](../../adapters-and-accelerators/adapter-oracle-ebs/media/13-instance-property.gif "13 _ instance_property")</span><span class="sxs-lookup"><span data-stu-id="f2dc5-188">![Specify a name for the Finder method instance](../../adapters-and-accelerators/adapter-oracle-ebs/media/13-instance-property.gif "13_Instance_Property")</span></span>  
  
##  <a name="Scenario2"></a><span data-ttu-id="f2dc5-189">Microsoft Office SharePoint Server から MS_SAMPLE_EMPLOYEE インターフェイス テーブルのシナリオ 2: フル テキスト検索</span><span class="sxs-lookup"><span data-stu-id="f2dc5-189">Scenario 2: Full-Text Search on MS_SAMPLE_EMPLOYEE Interface Table from Microsoft Office SharePoint Server</span></span>  
 <span data-ttu-id="f2dc5-190">Microsoft Office SharePoint Server から MS_SAMPLE_EMPLOYEE インターフェイス テーブルでフルテキスト検索を実行するために使用するアプリケーション定義ファイルを作成するには、次の一連のタスクを行う必要があります。</span><span class="sxs-lookup"><span data-stu-id="f2dc5-190">To create an application definition file that can be used to perform a full-text search on MS_SAMPLE_EMPLOYEE interface table from Microsoft Office SharePoint Server, you must perform the following set of tasks.</span></span>  
  
-   <span data-ttu-id="f2dc5-191">**選択**メソッドを識別子を作成し、フィルター パラメーターおよび従業員の名前を格納する戻り値にマップします。</span><span class="sxs-lookup"><span data-stu-id="f2dc5-191">In the **Select** method, create an identifier, and map it to the FILTER parameter and the return value that stores the employee name.</span></span>  
  
-   <span data-ttu-id="f2dc5-192">作成、 **Specific Finder**メソッド インスタンスの**選択**です。</span><span class="sxs-lookup"><span data-stu-id="f2dc5-192">Create a **Specific Finder** method instance for the **Select**.</span></span> <span data-ttu-id="f2dc5-193">**Specific Finder**メソッドは、特定のレコードの識別子に基づいて、つまり、従業員の名前を検索します。</span><span class="sxs-lookup"><span data-stu-id="f2dc5-193">The **Specific Finder** method will find a specific record based on the identifier, that is, an employee name.</span></span>  
  
-   <span data-ttu-id="f2dc5-194">ID Enumerator メソッド インスタンスを作成します。</span><span class="sxs-lookup"><span data-stu-id="f2dc5-194">Create an ID Enumerator method instance.</span></span>  
  
#### <a name="to-create-an-identifier-and-map-it-to-the-filter-parameter-and-employee-name-return-value"></a><span data-ttu-id="f2dc5-195">識別子を作成し、フィルター パラメーターと従業員の名前の戻り値にマップするには</span><span class="sxs-lookup"><span data-stu-id="f2dc5-195">To create an identifier, and map it to the FILTER parameter and employee name return value</span></span>  
  
1.  <span data-ttu-id="f2dc5-196">識別子を作成、**従業員**エンティティです。</span><span class="sxs-lookup"><span data-stu-id="f2dc5-196">Create an identifier for the **Employee** entity.</span></span>  
  
    1.  <span data-ttu-id="f2dc5-197">メタデータ オブジェクト ペインで、展開、**従業員**ノード。</span><span class="sxs-lookup"><span data-stu-id="f2dc5-197">In the Metadata Objects pane, expand the **Employee** node.</span></span>  
  
    2.  <span data-ttu-id="f2dc5-198">右クリックし、**識別子**ノードをクリックして**識別子の追加**です。</span><span class="sxs-lookup"><span data-stu-id="f2dc5-198">Right-click the **Identifiers** node, and then select **Add Identifier**.</span></span>  
  
         <span data-ttu-id="f2dc5-199">![識別子の作成](../../adapters-and-accelerators/adapter-oracle-ebs/media/14-create-identifier.gif "14 _ create_identifier")</span><span class="sxs-lookup"><span data-stu-id="f2dc5-199">![Create an Identifier](../../adapters-and-accelerators/adapter-oracle-ebs/media/14-create-identifier.gif "14_Create_Identifier")</span></span>  
  
    3.  <span data-ttu-id="f2dc5-200">プロパティ ウィンドウで、次のように入力します。 **EmployeeName**で、**名前**ボックス。</span><span class="sxs-lookup"><span data-stu-id="f2dc5-200">In the Properties pane, type **EmployeeName** in the **Name** box.</span></span>  
  
    4.  <span data-ttu-id="f2dc5-201">選択**System.String**の**型**ボックス。</span><span class="sxs-lookup"><span data-stu-id="f2dc5-201">Select **System.String** for the **Type** box.</span></span>  
  
         <span data-ttu-id="f2dc5-202">![識別子のプロパティを指定](../../adapters-and-accelerators/adapter-oracle-ebs/media/15-identifier-properties.gif "15_Identifier_Properties")</span><span class="sxs-lookup"><span data-stu-id="f2dc5-202">![Specify identifier properties](../../adapters-and-accelerators/adapter-oracle-ebs/media/15-identifier-properties.gif "15_Identifier_Properties")</span></span>  
  
2.  <span data-ttu-id="f2dc5-203">フィルター パラメーターに、id を割り当てる、**選択**メソッドです。</span><span class="sxs-lookup"><span data-stu-id="f2dc5-203">Map the identifier to the FILTER parameter for the **Select** method.</span></span>  
  
    1.  <span data-ttu-id="f2dc5-204">メタデータ オブジェクト ペインで、展開、**従業員** ノードの順に展開し、**メソッド**ノード。</span><span class="sxs-lookup"><span data-stu-id="f2dc5-204">In the Metadata Objects pane, expand the **Employee** node, and then expand the **Methods** node.</span></span>  
  
    2.  <span data-ttu-id="f2dc5-205">展開、**選択**メソッドの順に展開し、**パラメーター**ノード。</span><span class="sxs-lookup"><span data-stu-id="f2dc5-205">Expand the **Select** method, and then expand the **Parameters** node.</span></span>  
  
    3.  <span data-ttu-id="f2dc5-206">展開して、**フィルター**パラメーター、もう 1 つをクリックして**フィルター**ノード。</span><span class="sxs-lookup"><span data-stu-id="f2dc5-206">Expand the **FILTER** parameter, and then click the second **FILTER** node.</span></span>  
  
    4.  <span data-ttu-id="f2dc5-207">プロパティ ウィンドウで、次のように選択します。 **EmployeeName [Employee]** から、**識別子** ボックスの一覧です。</span><span class="sxs-lookup"><span data-stu-id="f2dc5-207">In the Properties pane, select **EmployeeName[Employee]** from the **Identifier** list.</span></span>  
  
         <span data-ttu-id="f2dc5-208">![フィルターのパラメーターの識別子を設定](../../adapters-and-accelerators/adapter-oracle-ebs/media/16-set-identifier.gif "16 _ set_identifier")</span><span class="sxs-lookup"><span data-stu-id="f2dc5-208">![Setting identifier for the FILTER parameter](../../adapters-and-accelerators/adapter-oracle-ebs/media/16-set-identifier.gif "16_Set_Identifier")</span></span>  
  
3.  <span data-ttu-id="f2dc5-209">従業員の名前の戻り値に識別子をマップします。</span><span class="sxs-lookup"><span data-stu-id="f2dc5-209">Map the identifier to the employee name return value.</span></span>  
  
    1.  <span data-ttu-id="f2dc5-210">メタデータ オブジェクト ペインで、展開、**従業員** ノードの順に展開し、**メソッド**ノード。</span><span class="sxs-lookup"><span data-stu-id="f2dc5-210">In the Metadata Objects pane, expand the **Employee** node, and then expand the **Methods** node.</span></span>  
  
    2.  <span data-ttu-id="f2dc5-211">展開、**選択**メソッドの順に展開し、**パラメーター**ノード。</span><span class="sxs-lookup"><span data-stu-id="f2dc5-211">Expand the **Select** method, and then expand the **Parameters** node.</span></span>  
  
    3.  <span data-ttu-id="f2dc5-212">展開、**を返す**] ノードの [2 番目**返す**ノード、**項目**ノードをクリックして、**名前**ノード。</span><span class="sxs-lookup"><span data-stu-id="f2dc5-212">Expand the **Return** node, then the second **Return** node, then the **Item** node, and then click the **Name** node.</span></span>  
  
    4.  <span data-ttu-id="f2dc5-213">プロパティ ウィンドウで、次のように選択します。 **EmployeeName [Employee]** から、**識別子** ボックスの一覧です。</span><span class="sxs-lookup"><span data-stu-id="f2dc5-213">In the Properties pane, select **EmployeeName[Employee]** from the **Identifier** list.</span></span>  
  
#### <a name="to-create-a-specific-finder-method-instance-for-the-select-method"></a><span data-ttu-id="f2dc5-214">Select メソッドの Specific Finder メソッド インスタンスを作成するには</span><span class="sxs-lookup"><span data-stu-id="f2dc5-214">To create a Specific Finder method instance for the Select method</span></span>  
  
1.  <span data-ttu-id="f2dc5-215">メタデータ オブジェクト ペインで、展開、**従業員**ノード、し、**メソッド**ノード。</span><span class="sxs-lookup"><span data-stu-id="f2dc5-215">In the Metadata Objects pane, expand the **Employee** node, and then the **Methods** node.</span></span>  
  
2.  <span data-ttu-id="f2dc5-216">展開、**選択** ノードを右クリックして**インスタンス**、し、**メソッド インスタンスの追加**メソッド インスタンスの作成 ウィンドウを開きます。</span><span class="sxs-lookup"><span data-stu-id="f2dc5-216">Expand the **Select** node, right-click **Instances**, and then select **Add Method Instance** to open the Create Method Instance window.</span></span>  
  
     <span data-ttu-id="f2dc5-217">![メソッド インスタンスの追加](../../adapters-and-accelerators/adapter-oracle-ebs/media/11-add-method-instance.gif "11 _ add_method_instance")</span><span class="sxs-lookup"><span data-stu-id="f2dc5-217">![Add a method instance](../../adapters-and-accelerators/adapter-oracle-ebs/media/11-add-method-instance.gif "11_Add_Method_Instance")</span></span>  
  
3.  <span data-ttu-id="f2dc5-218">メソッド インスタンスの作成 ウィンドウで、次のように選択します。 **Specific Finder**の**メソッド インスタンスの型**です。</span><span class="sxs-lookup"><span data-stu-id="f2dc5-218">In the Create Method Instance window, select **Specific Finder** for **Method Instance Type**.</span></span> <span data-ttu-id="f2dc5-219">選択**返す**の**TypeDescriptor を返す**です。</span><span class="sxs-lookup"><span data-stu-id="f2dc5-219">Select **Return** for **Return TypeDescriptor**.</span></span>  
  
     <span data-ttu-id="f2dc5-220">![Specific Finder メソッド インスタンスの追加](../../adapters-and-accelerators/adapter-oracle-ebs/media/17-specific-finder.gif "17 _ specific_finder")</span><span class="sxs-lookup"><span data-stu-id="f2dc5-220">![Add a Specific Finder method instance](../../adapters-and-accelerators/adapter-oracle-ebs/media/17-specific-finder.gif "17_Specific_Finder")</span></span>  
  
4.  <span data-ttu-id="f2dc5-221">**[OK]** をクリックします。</span><span class="sxs-lookup"><span data-stu-id="f2dc5-221">Click **OK**.</span></span>  
  
5.  <span data-ttu-id="f2dc5-222">プロパティ ウィンドウで、次のように入力します。 **SpeciFinder_Instance**の、**名前**ボックス。</span><span class="sxs-lookup"><span data-stu-id="f2dc5-222">In the Properties pane, type **SpeciFinder_Instance** for the **Name** box.</span></span>  
  
#### <a name="to-create-an-id-enumerator-method-instance-for-the-select-method"></a><span data-ttu-id="f2dc5-223">Select メソッドの Id Enumerator メソッド インスタンスを作成するには</span><span class="sxs-lookup"><span data-stu-id="f2dc5-223">To create an Id Enumerator method instance for the Select method</span></span>  
  
1.  <span data-ttu-id="f2dc5-224">メタデータ オブジェクト ペインで、展開、**従業員**ノード、し、**メソッド**ノード。</span><span class="sxs-lookup"><span data-stu-id="f2dc5-224">In the Metadata Objects pane, expand the **Employee** node, and then the **Methods** node.</span></span>  
  
2.  <span data-ttu-id="f2dc5-225">展開、**選択** ノードを右クリックして**インスタンス**、し、**メソッド インスタンスの追加**メソッド インスタンスの作成 ウィンドウを開きます。</span><span class="sxs-lookup"><span data-stu-id="f2dc5-225">Expand the **Select** node, right-click **Instances**, and then select **Add Method Instance** to open the Create Method Instance window.</span></span>  
  
     <span data-ttu-id="f2dc5-226">![メソッド インスタンスの追加](../../adapters-and-accelerators/adapter-oracle-ebs/media/11-add-method-instance.gif "11 _ add_method_instance")</span><span class="sxs-lookup"><span data-stu-id="f2dc5-226">![Add a method instance](../../adapters-and-accelerators/adapter-oracle-ebs/media/11-add-method-instance.gif "11_Add_Method_Instance")</span></span>  
  
3.  <span data-ttu-id="f2dc5-227">メソッド インスタンスの作成 ウィンドウで、次のように選択します。 **Id Enumerator**の**メソッド インスタンスの型**です。</span><span class="sxs-lookup"><span data-stu-id="f2dc5-227">In the Create Method Instance window, select **Id Enumerator** for **Method Instance Type**.</span></span> <span data-ttu-id="f2dc5-228">選択**返す**の**TypeDescriptor を返す**です。</span><span class="sxs-lookup"><span data-stu-id="f2dc5-228">Select **Return** for **Return TypeDescriptor**.</span></span>  
  
     <span data-ttu-id="f2dc5-229">![Id Enumerator メソッド インスタンスの作成](../../adapters-and-accelerators/adapter-oracle-ebs/media/18-id-enumerator.gif "18 _ id_enumerator")</span><span class="sxs-lookup"><span data-stu-id="f2dc5-229">![Create an Id Enumerator method instance](../../adapters-and-accelerators/adapter-oracle-ebs/media/18-id-enumerator.gif "18_ID_Enumerator")</span></span>  
  
4.  <span data-ttu-id="f2dc5-230">**[OK]** をクリックします。</span><span class="sxs-lookup"><span data-stu-id="f2dc5-230">Click **OK**.</span></span>  
  
5.  <span data-ttu-id="f2dc5-231">プロパティ ウィンドウで、次のように入力します。 **IDEnumerator_Instance**の、**名前**ボックス。</span><span class="sxs-lookup"><span data-stu-id="f2dc5-231">In the Properties pane, type **IDEnumerator_Instance** for the **Name** box.</span></span>  
  
##  <a name="Defaults"></a><span data-ttu-id="f2dc5-232">メソッド インスタンスの既定のパラメーターを設定します。</span><span class="sxs-lookup"><span data-stu-id="f2dc5-232">Set Default Parameters for the Method Instances</span></span>  
 <span data-ttu-id="f2dc5-233">Select メソッドでは、列名を指定する必要があります。</span><span class="sxs-lookup"><span data-stu-id="f2dc5-233">The Select method requires you to specify the column names.</span></span> <span data-ttu-id="f2dc5-234">したがって、既定値を指定する必要があります、**それら**Finder、固有の検索、および Id Enumerator メソッド インスタンスのパラメーターが以前に作成します。</span><span class="sxs-lookup"><span data-stu-id="f2dc5-234">Therefore, you need to specify a default value for the **COLUMN_NAMES** parameter for the Finder, Specific Finder, and Id Enumerator method instances created earlier.</span></span> <span data-ttu-id="f2dc5-235">既定値を指定するはもさらに、**フィルター** Id Enumerator メソッド インスタンスのパラメーターです。</span><span class="sxs-lookup"><span data-stu-id="f2dc5-235">Additionally, you should also specify a default value for the **FILTER** parameter for the Id Enumerator method instance.</span></span>  
  
#### <a name="to-set-the-default-parameters-for-the-method-instances"></a><span data-ttu-id="f2dc5-236">メソッド インスタンスの既定のパラメーターを設定するには</span><span class="sxs-lookup"><span data-stu-id="f2dc5-236">To set the default parameters for the method instances</span></span>  
  
1.  <span data-ttu-id="f2dc5-237">メタデータ オブジェクト ペインで、展開、**従業員** ノードの順に展開し、**メソッド**ノード。</span><span class="sxs-lookup"><span data-stu-id="f2dc5-237">In the Metadata Objects pane, expand the **Employee** node, and then expand the **Methods** node.</span></span>  
  
2.  <span data-ttu-id="f2dc5-238">展開、**選択**ノードの順に展開し、**パラメーター**ノード。</span><span class="sxs-lookup"><span data-stu-id="f2dc5-238">Expand the **Select** node, and then expand the **Parameters** node.</span></span>  
  
3.  <span data-ttu-id="f2dc5-239">展開して、**それら**ノードをクリックし、**それら**パラメーター。</span><span class="sxs-lookup"><span data-stu-id="f2dc5-239">Expand the **COLUMN_NAMES** node, and then select the **COLUMN_NAMES** parameter.</span></span>  
  
4.  <span data-ttu-id="f2dc5-240">プロパティ ウィンドウで、に対して省略記号ボタン (...) をクリックして、 **DefaultValues**ボックス。</span><span class="sxs-lookup"><span data-stu-id="f2dc5-240">In the Properties pane, click the ellipsis button (…) against the **DefaultValues** box.</span></span>  
  
5.  <span data-ttu-id="f2dc5-241">**DefaultValueView コレクション エディター**ダイアログ ボックスで、をクリックして**追加**、プロパティ ウィンドウで、をクリックして**Finder_Instance**で、 **SelectMethodInstance**  ボックスの一覧です。</span><span class="sxs-lookup"><span data-stu-id="f2dc5-241">In the **DefaultValueView Collection Editor** dialog box, click **Add**, and in the property pane, click **Finder_Instance** in the **SelectMethodInstance** list.</span></span>  
  
     <span data-ttu-id="f2dc5-242">![Finder インスタンスの既定値を指定する](../../adapters-and-accelerators/adapter-oracle-ebs/media/19-finderinstance-defaults.gif "19 _ finderinstance_defaults")</span><span class="sxs-lookup"><span data-stu-id="f2dc5-242">![Specifying default value for the Finder instance](../../adapters-and-accelerators/adapter-oracle-ebs/media/19-finderinstance-defaults.gif "19_FinderInstance_Defaults")</span></span>  
  
6.  <span data-ttu-id="f2dc5-243">型`*`で、**値**ボックス。</span><span class="sxs-lookup"><span data-stu-id="f2dc5-243">Type `*` in the **Value** box.</span></span>  
  
7.  <span data-ttu-id="f2dc5-244">同様に、手順 5. と 6. の既定値を追加、 **SpecificFinder_Instance**と**IDEnumerator_Instance**メソッドのインスタンス。</span><span class="sxs-lookup"><span data-stu-id="f2dc5-244">Similarly, repeat steps 5 and 6 to add default values for the **SpecificFinder_Instance** and **IDEnumerator_Instance** method instances.</span></span>  
  
8.  <span data-ttu-id="f2dc5-245">**DefaultValueView コレクション エディター**ダイアログ ボックスで、をクリックして**OK**です。</span><span class="sxs-lookup"><span data-stu-id="f2dc5-245">In the **DefaultValueView Collection Editor** dialog box, click **OK**.</span></span>  
  
9. <span data-ttu-id="f2dc5-246">既定値を次に、追加、**フィルター**のパラメーター、 **IDEnumerator_Instance**メソッド インスタンス。</span><span class="sxs-lookup"><span data-stu-id="f2dc5-246">Next, add a default value for the **FILTER** parameter for the **IDEnumerator_Instance** method instance.</span></span> <span data-ttu-id="f2dc5-247">展開して、**フィルター**ノードをクリックし、**フィルター**パラメーター。</span><span class="sxs-lookup"><span data-stu-id="f2dc5-247">Expand the **FILTER** node, and then select the **FILTER** parameter.</span></span>  
  
10. <span data-ttu-id="f2dc5-248">プロパティ ウィンドウで、に対して省略記号ボタン (...) をクリックして、 **DefaultValues**ボックス。</span><span class="sxs-lookup"><span data-stu-id="f2dc5-248">In the Properties pane, click the ellipsis button (…) against the **DefaultValues** box.</span></span>  
  
11. <span data-ttu-id="f2dc5-249">**DefaultValueView コレクション エディター**ダイアログ ボックスで、をクリックして**追加**、プロパティ ウィンドウで、をクリックして**IDEnumerator_Instance**で、 **SelectMethodInstance**  ボックスの一覧です。</span><span class="sxs-lookup"><span data-stu-id="f2dc5-249">In the **DefaultValueView Collection Editor** dialog box, click **Add**, and in the property pane, click **IDEnumerator_Instance** in the **SelectMethodInstance** list.</span></span>  
  
12. <span data-ttu-id="f2dc5-250">型`%`で、**値**ボックス。</span><span class="sxs-lookup"><span data-stu-id="f2dc5-250">Type `%` in the **Value** box.</span></span>  
  
     <span data-ttu-id="f2dc5-251">![Id Enumerator インスタンスの既定値](../../adapters-and-accelerators/adapter-oracle-ebs/media/20-idenumeratorinstance-defaults.gif "20 _ idenumeratorinstance_defaults")</span><span class="sxs-lookup"><span data-stu-id="f2dc5-251">![Default values for the Id Enumerator instance](../../adapters-and-accelerators/adapter-oracle-ebs/media/20-idenumeratorinstance-defaults.gif "20_IDEnumeratorInstance_Defaults")</span></span>  
  
13. <span data-ttu-id="f2dc5-252">**DefaultValueView コレクション エディター**ダイアログ ボックスで、をクリックして**OK**です。</span><span class="sxs-lookup"><span data-stu-id="f2dc5-252">In the **DefaultValueView Collection Editor** dialog box, click **OK**.</span></span>  
  
##  <a name="SSO"></a><span data-ttu-id="f2dc5-253">Oracle E-business Suite に接続するためのシングル サインオンの設定します。</span><span class="sxs-lookup"><span data-stu-id="f2dc5-253">Set up Single Sign-On for Connecting to Oracle E-Business Suite</span></span>  
 <span data-ttu-id="f2dc5-254">このトピックのすべてのプロシージャの実行が完了したら後、は、SharePoint アプリケーションにインポートできるアプリケーション定義ファイルが作成されます。</span><span class="sxs-lookup"><span data-stu-id="f2dc5-254">After you have finished performing all the procedures in this topic, you will have created an application definition file that can be imported into a SharePoint application.</span></span> <span data-ttu-id="f2dc5-255">アプリケーションから Oracle E-business Suite から関連データを取得するメソッドを呼び出します。</span><span class="sxs-lookup"><span data-stu-id="f2dc5-255">From the application, you invoke the methods to retrieve relevant data from Oracle E-Business Suite.</span></span> <span data-ttu-id="f2dc5-256">これを有効にするには、SharePoint アプリケーションで Oracle E-business Suite でのユーザーとユーザー間のマッピングを作成する必要があります。</span><span class="sxs-lookup"><span data-stu-id="f2dc5-256">To enable this, you must create a mapping between a user in the Oracle E-Business Suite and the user in the SharePoint application.</span></span> <span data-ttu-id="f2dc5-257">アプリケーション定義ファイルをインポートした後は、SharePoint サーバーの全体管理コンソールの このマッピングを作成します。</span><span class="sxs-lookup"><span data-stu-id="f2dc5-257">You create this mapping in SharePoint Central Administration console after you have imported the application definition file.</span></span>  
  
 <span data-ttu-id="f2dc5-258">ただし、マッピングを作成する必要がありますプロパティを設定する**SecondarySsoApplicationId**ビジネス データ カタログ定義エディターにします。</span><span class="sxs-lookup"><span data-stu-id="f2dc5-258">However, to create the mapping you must set a property **SecondarySsoApplicationId** in the Business Data Catalog Definition Editor.</span></span>  
  
#### <a name="to-set-the-secondaryssoapplicationid-property"></a><span data-ttu-id="f2dc5-259">SecondarySsoApplicationId のプロパティを設定するには</span><span class="sxs-lookup"><span data-stu-id="f2dc5-259">To set the SecondarySsoApplicationId property</span></span>  
  
1.  <span data-ttu-id="f2dc5-260">メタデータ オブジェクト ペインで、展開、 **MS_SAMPLE_EMPLOYEE**  ノードの順に展開し、**インスタンス**ノード。</span><span class="sxs-lookup"><span data-stu-id="f2dc5-260">In the Metadata Objects pane, expand the **MS_SAMPLE_EMPLOYEE** node, and then expand the **Instances** node.</span></span>  
  
2.  <span data-ttu-id="f2dc5-261">をクリックして**MS_SAMPLE_EMPLOYEE_Instance**、プロパティ ペインでに対して省略記号 (...) ボタンをクリックし、**プロパティ**ボックス。</span><span class="sxs-lookup"><span data-stu-id="f2dc5-261">Click **MS_SAMPLE_EMPLOYEE_Instance**, and in the Properties pane, click the ellipsis (…) button against the **Properties** box.</span></span>  
  
3.  <span data-ttu-id="f2dc5-262">**PropertyView コレクション エディター**ダイアログ ボックスで、をクリックして**追加**、プロパティ ウィンドウで、次のように入力します**SecondarySsoApplicationId**の、**名前。** ボックス。</span><span class="sxs-lookup"><span data-stu-id="f2dc5-262">In the **PropertyView Collection Editor** dialog box, click **Add**, and in the Property pane, type **SecondarySsoApplicationId** for the **Name** box.</span></span> <span data-ttu-id="f2dc5-263">同様に、入力**OracleSSO**の**PropertyValue**ボックス。</span><span class="sxs-lookup"><span data-stu-id="f2dc5-263">Similarly, type **OracleSSO** for the **PropertyValue** box.</span></span> <span data-ttu-id="f2dc5-264">選択**System.String**の**型**ボックス。</span><span class="sxs-lookup"><span data-stu-id="f2dc5-264">Select **System.String** for the **Type** box.</span></span>  
  
     <span data-ttu-id="f2dc5-265">![SSO プロパティの追加](../../adapters-and-accelerators/adapter-oracle-ebs/media/21-sso.gif "21 _ sso")</span><span class="sxs-lookup"><span data-stu-id="f2dc5-265">![Add the SSO Property](../../adapters-and-accelerators/adapter-oracle-ebs/media/21-sso.gif "21_SSO")</span></span>  
  
4.  <span data-ttu-id="f2dc5-266">**[OK]** をクリックします。</span><span class="sxs-lookup"><span data-stu-id="f2dc5-266">Click **OK**.</span></span>  
  
##  <a name="Export"></a><span data-ttu-id="f2dc5-267">アプリケーション定義をファイルにエクスポートします。</span><span class="sxs-lookup"><span data-stu-id="f2dc5-267">Export the Application Definition to a File</span></span>  
 <span data-ttu-id="f2dc5-268">Oracle E-business Suite インスタンスのメタデータを含んでいるアプリケーション定義が作成されました。</span><span class="sxs-lookup"><span data-stu-id="f2dc5-268">You have now created an application definition that contains Oracle E-Business Suite instance metadata.</span></span> <span data-ttu-id="f2dc5-269">Microsoft Office SharePoint Server にインポートできる XML ファイルにこの定義をエクスポートする必要があります。</span><span class="sxs-lookup"><span data-stu-id="f2dc5-269">You must export this definition to an XML file, which can be imported into Microsoft Office SharePoint Server.</span></span>  
  
#### <a name="to-export-the-application-definition-to-a-file"></a><span data-ttu-id="f2dc5-270">アプリケーション定義をファイルにエクスポートするには</span><span class="sxs-lookup"><span data-stu-id="f2dc5-270">To export the application definition to a file</span></span>  
  
1.  <span data-ttu-id="f2dc5-271">メタデータ オブジェクト ペインで右クリックし、 **MS_SAMPLE_EMPLOYEE**ノードをクリックして**エクスポート**です。</span><span class="sxs-lookup"><span data-stu-id="f2dc5-271">In the Metadata Objects pane, right-click the **MS_SAMPLE_EMPLOYEE** node, and then click **Export**.</span></span>  
  
2.  <span data-ttu-id="f2dc5-272">Employee.xml としてファイルを保存します。</span><span class="sxs-lookup"><span data-stu-id="f2dc5-272">Save the file as Employee.xml.</span></span>  
  
## <a name="next-steps"></a><span data-ttu-id="f2dc5-273">次の手順</span><span class="sxs-lookup"><span data-stu-id="f2dc5-273">Next Steps</span></span>  
 <span data-ttu-id="f2dc5-274">Oracle E-business Suite からデータを取得する SharePoint アプリケーションを作成する必要がありますようになりました。</span><span class="sxs-lookup"><span data-stu-id="f2dc5-274">You must now create a SharePoint application to retrieve data from Oracle E-Business Suite.</span></span> <span data-ttu-id="f2dc5-275">手順については、次を参照してください。[手順 3: Oracle E-business Suite からデータを取得する SharePoint アプリケーションを作成](../../adapters-and-accelerators/adapter-oracle-ebs/step-3-create-a-sharepoint-application-to-retrieve-data-from-oracle-ebs.md)です。</span><span class="sxs-lookup"><span data-stu-id="f2dc5-275">For instructions, see [Step 3: Create a SharePoint Application to Retrieve Data from Oracle E-Business Suite](../../adapters-and-accelerators/adapter-oracle-ebs/step-3-create-a-sharepoint-application-to-retrieve-data-from-oracle-ebs.md).</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="f2dc5-276">参照</span><span class="sxs-lookup"><span data-stu-id="f2dc5-276">See Also</span></span>  
 [<span data-ttu-id="f2dc5-277">チュートリアル: SharePoint サイト上の Oracle E-business Suite からデータを表示します。</span><span class="sxs-lookup"><span data-stu-id="f2dc5-277">Tutorial: Present Data from Oracle E-Business Suite on a SharePoint Site</span></span>](Tutorial:%20Present%20data%20from%20Oracle%20E-Business%20Suite%20on%20a%20SharePoint%20Site.md)