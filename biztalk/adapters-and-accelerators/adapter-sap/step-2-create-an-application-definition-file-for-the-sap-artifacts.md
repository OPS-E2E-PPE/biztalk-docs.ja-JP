---
title: '手順 2: SAP アイテム用のアプリケーション定義ファイルの作成 |Microsoft Docs'
ms.custom: ''
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: ''
ms.suite: ''
ms.tgt_pltfrm: ''
ms.topic: article
helpviewer_keywords:
- application definition file, creating a
- Business Data Catalog Definition Editor
- Business Data Catalog
ms.assetid: d254b00e-dbeb-4167-ad57-6f0aa2e7a563
caps.latest.revision: 14
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: 92e97a54a6818456efd2f4ac55ca7e2fc5bc7c35
ms.sourcegitcommit: 266308ec5c6a9d8d80ff298ee6051b4843c5d626
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 06/27/2018
ms.locfileid: "36970387"
---
# <a name="step-2-create-an-application-definition-file-for-the-sap-artifacts"></a><span data-ttu-id="eb327-102">手順 2: SAP アイテム用のアプリケーション定義ファイルを作成します。</span><span class="sxs-lookup"><span data-stu-id="eb327-102">Step 2: Create an Application Definition File for the SAP Artifacts</span></span>
<span data-ttu-id="eb327-103">![手順 4 2](../../adapters-and-accelerators/adapter-oracle-ebs/media/step-2of4.gif "Step_2of4")</span><span class="sxs-lookup"><span data-stu-id="eb327-103">![Step 2 of 4](../../adapters-and-accelerators/adapter-oracle-ebs/media/step-2of4.gif "Step_2of4")</span></span>  
  
 <span data-ttu-id="eb327-104">**所要時間:** 15 分</span><span class="sxs-lookup"><span data-stu-id="eb327-104">**Time to complete:** 15 minutes</span></span>  
  
 <span data-ttu-id="eb327-105">**目標:** Microsoft SharePoint Server でビジネス データ カタログ機能を公開し、基幹業務 (LOB) アプリケーションからのデータがポータルに組み込まれています。</span><span class="sxs-lookup"><span data-stu-id="eb327-105">**Objective:** The Business Data Catalog feature in Microsoft SharePoint Server exposes and incorporates data from line-of-business (LOB) applications into portals.</span></span> <span data-ttu-id="eb327-106">ポータル サイトにこのデータを組み込むには、Microsoft Office SharePoint Server を使用するアプリケーション定義ファイルをビルドする必要があります。</span><span class="sxs-lookup"><span data-stu-id="eb327-106">To incorporate this data into your portal site, you must build an application definition file that Microsoft Office SharePoint Server can consume.</span></span>  
  
 <span data-ttu-id="eb327-107">Microsoft Office SharePoint Server 2007 SDK で使用可能なビジネス データ カタログ定義エディター ツールでは、ビジネス データ カタログ アプリケーション定義ファイルを作成することができます。</span><span class="sxs-lookup"><span data-stu-id="eb327-107">The Business Data Catalog Definition Editor tool, available with Microsoft Office SharePoint Server 2007 SDK,enables you to create an application definition file for the Business Data Catalog.</span></span> <span data-ttu-id="eb327-108">このツールでは、手動でファイルを作成するには、XML エディター必要はありませんので、定義ファイルの XML ファイルが自動的に生成されます。</span><span class="sxs-lookup"><span data-stu-id="eb327-108">This tool automatically generates an XML file for the definition file, so you do not need to manually create the file in an XML editor.</span></span>  
  
 <span data-ttu-id="eb327-109">作成している Microsoft Office SharePoint Server アプリケーションの目的には。</span><span class="sxs-lookup"><span data-stu-id="eb327-109">The purpose of the Microsoft Office SharePoint Server application that you are creating is to:</span></span>  
  
- <span data-ttu-id="eb327-110">顧客名に基づいて、SAP システムの顧客を検索します。</span><span class="sxs-lookup"><span data-stu-id="eb327-110">Search for a customer in the SAP system based on a customer name.</span></span>  
  
- <span data-ttu-id="eb327-111">フェッチされた顧客の一覧から顧客を選択し、顧客の詳細を取得します。</span><span class="sxs-lookup"><span data-stu-id="eb327-111">Select a customer from the list of fetched customers and retrieve the details for the customer.</span></span>  
  
- <span data-ttu-id="eb327-112">フェッチされた顧客の一覧から顧客を選択し、顧客の注文を取得します。</span><span class="sxs-lookup"><span data-stu-id="eb327-112">Select a customer from the list of fetched customers and retrieve the sales orders for the customer.</span></span>  
  
  <span data-ttu-id="eb327-113">これらの要件ごとに、一連のビジネス データ カタログ定義エディター ツールでタスクを完了する必要があります。</span><span class="sxs-lookup"><span data-stu-id="eb327-113">For each of these requirements, you must complete a set of tasks in the Business Data Catalog Definition Editor tool.</span></span> <span data-ttu-id="eb327-114">このトピックでは、これらのタスクを実行する方法について説明します。</span><span class="sxs-lookup"><span data-stu-id="eb327-114">This topic provides instructions on how to perform these tasks.</span></span>  
  
## <a name="prerequisites"></a><span data-ttu-id="eb327-115">前提条件</span><span class="sxs-lookup"><span data-stu-id="eb327-115">Prerequisites</span></span>  
  
-   <span data-ttu-id="eb327-116">Microsoft Office SharePoint Server 2007 SDK の一部としてインストールされているビジネス データ カタログ定義エディターであることを確認します。</span><span class="sxs-lookup"><span data-stu-id="eb327-116">Be sure that you have the Business Data Catalog Definition Editor installed as part of the Microsoft Office SharePoint Server 2007 SDK.</span></span> <span data-ttu-id="eb327-117">SDK をダウンロードする[ http://go.microsoft.com/fwlink/?LinkId=104130](http://go.microsoft.com/fwlink/?LinkId=104130)します。</span><span class="sxs-lookup"><span data-stu-id="eb327-117">You can download the SDK from [http://go.microsoft.com/fwlink/?LinkId=104130](http://go.microsoft.com/fwlink/?LinkId=104130).</span></span>  
  
-   <span data-ttu-id="eb327-118">WCF サービスに発行する」の説明に従って[手順 1: WCF サービスとしての SAP の成果物を公開](../../adapters-and-accelerators/adapter-sap/step-1-publish-the-sap-artifacts-as-a-wcf-service.md)します。</span><span class="sxs-lookup"><span data-stu-id="eb327-118">Publish the WCF service as described in [Step 1: Publish the SAP Artifacts as a WCF Service](../../adapters-and-accelerators/adapter-sap/step-1-publish-the-sap-artifacts-as-a-wcf-service.md).</span></span>  
  
## <a name="creating-an-application-definition-file"></a><span data-ttu-id="eb327-119">アプリケーション定義ファイルを作成します。</span><span class="sxs-lookup"><span data-stu-id="eb327-119">Creating an Application Definition File</span></span>  
 <span data-ttu-id="eb327-120">このトピックでは、WCF サービスのアプリケーション定義ファイルを作成する手順を提供します。</span><span class="sxs-lookup"><span data-stu-id="eb327-120">This topic provides step-by-step instructions to create an application definition file for the WCF service.</span></span>  
  
### <a name="connect-to-the-wcf-lob-service-and-create-entities"></a><span data-ttu-id="eb327-121">WCF LOB サービスに接続して、エンティティを作成します。</span><span class="sxs-lookup"><span data-stu-id="eb327-121">Connect to the WCF LOB Service, and Create Entities</span></span>  
 <span data-ttu-id="eb327-122">Web サービス記述言語 (WSDL) サービスを抽出する WCF サービスに接続する必要があります。</span><span class="sxs-lookup"><span data-stu-id="eb327-122">You must connect to the WCF service to extract the Web Services Description Language (WSDL) for the service.</span></span> <span data-ttu-id="eb327-123">ビジネス データ カタログ定義エディターでは、WSDL からメソッドを抽出します。</span><span class="sxs-lookup"><span data-stu-id="eb327-123">From the WSDL, the Business Data Catalog Definition Editor extracts the methods.</span></span> <span data-ttu-id="eb327-124">エンティティを作成するのには、これらのメソッドを使用できます。</span><span class="sxs-lookup"><span data-stu-id="eb327-124">These methods can be used to create entities.</span></span> <span data-ttu-id="eb327-125">この例では、2 つのエンティティが作成、顧客と販売注文に対して 1 つずつされます。</span><span class="sxs-lookup"><span data-stu-id="eb327-125">For this example, two entities are created, one each for the customer and sales orders.</span></span>  
  
##### <a name="to-connect-to-the-wcf-service-and-create-entities"></a><span data-ttu-id="eb327-126">WCF サービスに接続し、エンティティを作成するには</span><span class="sxs-lookup"><span data-stu-id="eb327-126">To connect to the WCF service and create entities</span></span>  
  
1. <span data-ttu-id="eb327-127">ビジネス データ カタログ定義エディターを起動します。</span><span class="sxs-lookup"><span data-stu-id="eb327-127">Start the Business Data Catalog Definition Editor.</span></span> <span data-ttu-id="eb327-128">**開始** メニューのをクリックして**Microsoft ビジネス データ カタログ定義エディター**します。</span><span class="sxs-lookup"><span data-stu-id="eb327-128">On the **Start** menu, click **Microsoft Business Data Catalog Definition Editor**.</span></span>  
  
2. <span data-ttu-id="eb327-129">ツールバーの**LOB システムの追加**します。</span><span class="sxs-lookup"><span data-stu-id="eb327-129">On the toolbar, click **Add LOB System**.</span></span>  
  
3. <span data-ttu-id="eb327-130">LOB システムの追加 ウィンドウで、次のようにクリックします。 **web サービスへの接続**します。</span><span class="sxs-lookup"><span data-stu-id="eb327-130">In the Add LOB System window, click **Connect to Webservice**.</span></span>  
  
4. <span data-ttu-id="eb327-131">**URL**ボックスに、WCF サービスの URL を入力します。</span><span class="sxs-lookup"><span data-stu-id="eb327-131">In the **URL** box, type the URL for the WCF service.</span></span> <span data-ttu-id="eb327-132">URL は、次の形式である必要があります。</span><span class="sxs-lookup"><span data-stu-id="eb327-132">The URL must be in the following format:</span></span>  
  
   ```  
   https://<computer_name>/Customer_Order/Rfc.svc?wsdl  
   ```  
  
    <span data-ttu-id="eb327-133">Rfc.svc は、Rfc コントラクト用に作成されたファイルです。</span><span class="sxs-lookup"><span data-stu-id="eb327-133">where Rfc.svc is the file created for the Rfc contract.</span></span>  
  
    <span data-ttu-id="eb327-134">WCF サービスが、トピックの説明に従って、正常に発行されるかどうかをテストするときに、URL が使用可能な[手順 1: WCF サービスとしての SAP の成果物を公開](../../adapters-and-accelerators/adapter-sap/step-1-publish-the-sap-artifacts-as-a-wcf-service.md)します。</span><span class="sxs-lookup"><span data-stu-id="eb327-134">The URL is available when you test whether the WCF service is published successfully, as described in the topic [Step 1: Publish the SAP Artifacts as a WCF Service](../../adapters-and-accelerators/adapter-sap/step-1-publish-the-sap-artifacts-as-a-wcf-service.md).</span></span>  
  
5. <span data-ttu-id="eb327-135">**[接続]** をクリックします。</span><span class="sxs-lookup"><span data-stu-id="eb327-135">Click **Connect**.</span></span>  
  
6. <span data-ttu-id="eb327-136">WCF アダプター サービス開発ウィザードで選択した操作を表示するには、クリックして、 **Web メソッドの追加**タブ。次の方法が表示されます。</span><span class="sxs-lookup"><span data-stu-id="eb327-136">To see the operations you selected in the WCF Adapter Service Development Wizard, click the **Add Web Method** tab. You will see the following methods:</span></span>  
  
   - <span data-ttu-id="eb327-137">SD_RFC_CUSTOMER_GET</span><span class="sxs-lookup"><span data-stu-id="eb327-137">SD_RFC_CUSTOMER_GET</span></span>  
  
   - <span data-ttu-id="eb327-138">BAPI_SALESORDER_GETLIST</span><span class="sxs-lookup"><span data-stu-id="eb327-138">BAPI_SALESORDER_GETLIST</span></span>  
  
      <span data-ttu-id="eb327-139">![BDC アプリケーションへの web メソッドの追加](../../adapters-and-accelerators/adapter-sap/media/ea411db2-5cf4-4486-83da-57d3fc332448.gif "ea411db2-5cf4-4486-83da-57d3fc332448")</span><span class="sxs-lookup"><span data-stu-id="eb327-139">![Add web methods to the BDC application](../../adapters-and-accelerators/adapter-sap/media/ea411db2-5cf4-4486-83da-57d3fc332448.gif "ea411db2-5cf4-4486-83da-57d3fc332448")</span></span>  
  
     <span data-ttu-id="eb327-140">メソッドは、デザイン画面にドラッグします。</span><span class="sxs-lookup"><span data-stu-id="eb327-140">Drag the methods to the Design Surface.</span></span> <span data-ttu-id="eb327-141">両方の操作をさまざまなエンティティにドラッグすることを確認します。</span><span class="sxs-lookup"><span data-stu-id="eb327-141">Make sure you drag both operations to the different entities.</span></span>  
  
     <span data-ttu-id="eb327-142">![Web メソッドのエンティティを作成する](../../adapters-and-accelerators/adapter-sap/media/ce4e9bc3-1eae-43ae-8375-e44cf19aaffc.gif "ce4e9bc3-1eae-43ae-8375-e44cf19aaffc")</span><span class="sxs-lookup"><span data-stu-id="eb327-142">![Create entities for the web methods](../../adapters-and-accelerators/adapter-sap/media/ce4e9bc3-1eae-43ae-8375-e44cf19aaffc.gif "ce4e9bc3-1eae-43ae-8375-e44cf19aaffc")</span></span>  
  
7. <span data-ttu-id="eb327-143">**[OK]** をクリックします。</span><span class="sxs-lookup"><span data-stu-id="eb327-143">Click **OK**.</span></span>  
  
8. <span data-ttu-id="eb327-144">**LOB システムの名前を入力** ダイアログ ボックスに名前を入力、 **LOB システム名**ボックス。</span><span class="sxs-lookup"><span data-stu-id="eb327-144">In the **Enter the name for the LOB System** dialog box, type a name in the **LOB System Name** box.</span></span> <span data-ttu-id="eb327-145">この例では、呼び出す**Customer_Order**、順にクリックします**OK**します。</span><span class="sxs-lookup"><span data-stu-id="eb327-145">For this example, call it **Customer_Order**, and then click **OK**.</span></span>  
  
9. <span data-ttu-id="eb327-146">ビジネス データ カタログ定義エディターで 2 つのエンティティとして一覧表示。 **Entity0**と**Entity1**します。</span><span class="sxs-lookup"><span data-stu-id="eb327-146">In the Business Data Catalog Definition Editor, the two entities are listed as **Entity0** and **Entity1**.</span></span> <span data-ttu-id="eb327-147">これらのエンティティにわかりやすい名前を付けます。</span><span class="sxs-lookup"><span data-stu-id="eb327-147">Give these entities friendly names.</span></span> <span data-ttu-id="eb327-148">SD_RFC_CUSTOMER_GET のエンティティの名前変更**顧客**に BAPI_SALESORDER_GETLIST のエンティティの名前変更と**SalesOrder**します。</span><span class="sxs-lookup"><span data-stu-id="eb327-148">Rename the entity for SD_RFC_CUSTOMER_GET to **Customer**, and rename the entity for BAPI_SALESORDER_GETLIST to **SalesOrder**.</span></span> <span data-ttu-id="eb327-149">エンティティの名前を変更するには、次の手順に従います。</span><span class="sxs-lookup"><span data-stu-id="eb327-149">Perform the following steps to rename the entities:</span></span>  
  
    1.  <span data-ttu-id="eb327-150">展開、 **Customer_Order**ノードの順に展開し、**エンティティ**ノード。</span><span class="sxs-lookup"><span data-stu-id="eb327-150">Expand the **Customer_Order** node, and then expand the **Entities** node.</span></span>  
  
    2.  <span data-ttu-id="eb327-151">選択、 **Entity0**ノード。</span><span class="sxs-lookup"><span data-stu-id="eb327-151">Select the **Entity0** node.</span></span>  
  
    3.  <span data-ttu-id="eb327-152">プロパティ ペインで次のように入力します。**顧客**で、**名前**ボックス。</span><span class="sxs-lookup"><span data-stu-id="eb327-152">In the Properties pane, type **Customer** in the **Name** box.</span></span>  
  
         <span data-ttu-id="eb327-153">![エンティティの名前変更](../../adapters-and-accelerators/adapter-sap/media/4e83a036-3ab7-4f74-9f67-420574219d3d.gif "4e83a036-3ab7-4f74-9f67-420574219d3d")</span><span class="sxs-lookup"><span data-stu-id="eb327-153">![Rename the entity](../../adapters-and-accelerators/adapter-sap/media/4e83a036-3ab7-4f74-9f67-420574219d3d.gif "4e83a036-3ab7-4f74-9f67-420574219d3d")</span></span>  
  
    4.  <span data-ttu-id="eb327-154">選択、 **Entity1**ノード。</span><span class="sxs-lookup"><span data-stu-id="eb327-154">Select the **Entity1** node.</span></span>  
  
    5.  <span data-ttu-id="eb327-155">プロパティ ペインで次のように入力します。 **SalesOrder**で、**名前**ボックス。</span><span class="sxs-lookup"><span data-stu-id="eb327-155">In the Properties pane, type **SalesOrder** in the **Name** box.</span></span>  
  
### <a name="specify-user-name-and-password-headers-for-the-methods"></a><span data-ttu-id="eb327-156">メソッドのユーザー名とパスワードのヘッダーを指定します。</span><span class="sxs-lookup"><span data-stu-id="eb327-156">Specify User Name and Password Headers for the Methods</span></span>  
 <span data-ttu-id="eb327-157">SAP システムで、選択した Rfc の WCF サービスを作成するときに、エンドポイント動作の構成の一部としてユーザー名とパスワードのヘッダーを指定します。</span><span class="sxs-lookup"><span data-stu-id="eb327-157">When creating a WCF service for the selected RFCs in the SAP system, you specified user name and password headers as part of the endpoint behavior configuration.</span></span> <span data-ttu-id="eb327-158">参照してください[手順 1: SAP アイテムを WCF サービスとして発行](../../adapters-and-accelerators/adapter-sap/step-1-publish-the-sap-artifacts-as-a-wcf-service.md)します。</span><span class="sxs-lookup"><span data-stu-id="eb327-158">See [Step 1: Publish the SAP Artifacts as a WCF Service](../../adapters-and-accelerators/adapter-sap/step-1-publish-the-sap-artifacts-as-a-wcf-service.md).</span></span> <span data-ttu-id="eb327-159">メソッドのプロパティの同じ値を指定する必要があります。</span><span class="sxs-lookup"><span data-stu-id="eb327-159">You must specify the same values for the method properties.</span></span>  
  
##### <a name="to-specify-user-name-and-password-headers"></a><span data-ttu-id="eb327-160">ユーザー名とパスワードのヘッダーを指定するには</span><span class="sxs-lookup"><span data-stu-id="eb327-160">To specify user name and password headers</span></span>  
  
1.  <span data-ttu-id="eb327-161">SD_RFC_CUSTOMER_GET メソッドのユーザー名とパスワード ヘッダーを追加します。</span><span class="sxs-lookup"><span data-stu-id="eb327-161">Add the user name and password headers for the SD_RFC_CUSTOMER_GET method.</span></span>  
  
    1.  <span data-ttu-id="eb327-162">メタデータ オブジェクト ウィンドウで、展開、**顧客**ノードの順に展開し、**メソッド**ノード。</span><span class="sxs-lookup"><span data-stu-id="eb327-162">In the Metadata Objects pane, expand the **Customer** node, and then expand the **Methods** node.</span></span>  
  
    2.  <span data-ttu-id="eb327-163">SD_RFC_CUSTOMER_GET ノードをクリックし、プロパティ ペインで、に対して省略記号 (...) ボタンをクリックします。、**プロパティ**ボックス。</span><span class="sxs-lookup"><span data-stu-id="eb327-163">Click the SD_RFC_CUSTOMER_GET node, and in the Properties pane click the ellipsis (…) button against the **Properties** box.</span></span>  
  
    3.  <span data-ttu-id="eb327-164">PropertyView コレクション エディター] ウィンドウで、[**追加**、プロパティ ペインで次のように入力します。 **HttpHeaderUserName**の、**名前**ボックス。</span><span class="sxs-lookup"><span data-stu-id="eb327-164">In the PropertyView Collection Editor window, click **Add**, and in the Property pane, type **HttpHeaderUserName** for the **Name** box.</span></span> <span data-ttu-id="eb327-165">同様に、入力**MyUserHeader**の**PropertyValue**ボックス。</span><span class="sxs-lookup"><span data-stu-id="eb327-165">Similarly, type **MyUserHeader** for the **PropertyValue** box.</span></span> <span data-ttu-id="eb327-166">選択**System.String**の**型**ボックス。</span><span class="sxs-lookup"><span data-stu-id="eb327-166">Select **System.String** for the **Type** box.</span></span>  
  
         <span data-ttu-id="eb327-167">![プロパティを追加](../../adapters-and-accelerators/adapter-sap/media/9eef32ac-8a93-45dc-8d07-12b7dbf961ba.gif "9eef32ac-8a93-45dc-8d07-12b7dbf961ba")</span><span class="sxs-lookup"><span data-stu-id="eb327-167">![Add a property](../../adapters-and-accelerators/adapter-sap/media/9eef32ac-8a93-45dc-8d07-12b7dbf961ba.gif "9eef32ac-8a93-45dc-8d07-12b7dbf961ba")</span></span>  
  
    4.  <span data-ttu-id="eb327-168">PropertyView コレクション エディター] ウィンドウで、[**追加**、プロパティ ペインで次のように入力します。 **HttpHeaderPassword**の、**名前**ボックス。</span><span class="sxs-lookup"><span data-stu-id="eb327-168">In the PropertyView Collection Editor window, click **Add**, and in the Property pane, type **HttpHeaderPassword** for the **Name** box.</span></span> <span data-ttu-id="eb327-169">同様に、入力**MyPassHeader**の**PropertyValue**ボックス。</span><span class="sxs-lookup"><span data-stu-id="eb327-169">Similarly, type **MyPassHeader** for the **PropertyValue** box.</span></span> <span data-ttu-id="eb327-170">選択**System.String**の**型**ボックス。</span><span class="sxs-lookup"><span data-stu-id="eb327-170">Select **System.String** for the **Type** box.</span></span>  
  
    5.  <span data-ttu-id="eb327-171">**[OK]** をクリックします。</span><span class="sxs-lookup"><span data-stu-id="eb327-171">Click **OK**.</span></span>  
  
2.  <span data-ttu-id="eb327-172">BAPI_SALESORDER_GETLIST メソッドのユーザー名とパスワード ヘッダーを追加します。</span><span class="sxs-lookup"><span data-stu-id="eb327-172">Add the user name and password headers for the BAPI_SALESORDER_GETLIST method.</span></span>  
  
    1.  <span data-ttu-id="eb327-173">メタデータ オブジェクト ウィンドウで、展開、 **SalesOrder**ノードの順に展開し、**メソッド**ノード。</span><span class="sxs-lookup"><span data-stu-id="eb327-173">In the Metadata Objects pane, expand the **SalesOrder** node, and then expand the **Methods** node.</span></span>  
  
    2.  <span data-ttu-id="eb327-174">BAPI_SALESORDER_GETLIST ノードをクリックし、プロパティ ペインで、に対して省略記号 (...) ボタンをクリックします。、**プロパティ**ボックス。</span><span class="sxs-lookup"><span data-stu-id="eb327-174">Click the BAPI_SALESORDER_GETLIST node, and in the Properties pane click the ellipsis (…) button against the **Properties** box.</span></span>  
  
    3.  <span data-ttu-id="eb327-175">PropertyView コレクション エディター] ウィンドウで、[**追加**、プロパティ ペインで次のように入力します。 **HttpHeaderUserName**の、**名前**ボックス。</span><span class="sxs-lookup"><span data-stu-id="eb327-175">In the PropertyView Collection Editor window, click **Add**, and in the Property pane, type **HttpHeaderUserName** for the **Name** box.</span></span> <span data-ttu-id="eb327-176">同様に、入力**MyUserHeader**の**PropertyValue**ボックス。</span><span class="sxs-lookup"><span data-stu-id="eb327-176">Similarly, type **MyUserHeader** for the **PropertyValue** box.</span></span> <span data-ttu-id="eb327-177">選択**System.String**の**型**ボックス。</span><span class="sxs-lookup"><span data-stu-id="eb327-177">Select **System.String** for the **Type** box.</span></span>  
  
    4.  <span data-ttu-id="eb327-178">PropertyView コレクション エディター] ウィンドウで、[**追加**、プロパティ ペインで次のように入力します。 **HttpHeaderPassword**の、**名前**ボックス。</span><span class="sxs-lookup"><span data-stu-id="eb327-178">In the PropertyView Collection Editor window, click **Add**, and in the Property pane, type **HttpHeaderPassword** for the **Name** box.</span></span> <span data-ttu-id="eb327-179">同様に、入力**MyPassHeader**の**PropertyValue**ボックス。</span><span class="sxs-lookup"><span data-stu-id="eb327-179">Similarly, type **MyPassHeader** for the **PropertyValue** box.</span></span> <span data-ttu-id="eb327-180">選択**System.String**の**型**ボックス。</span><span class="sxs-lookup"><span data-stu-id="eb327-180">Select **System.String** for the **Type** box.</span></span>  
  
    5.  <span data-ttu-id="eb327-181">**[OK]** をクリックします。</span><span class="sxs-lookup"><span data-stu-id="eb327-181">Click **OK**.</span></span>  
  
### <a name="set-up-single-sign-on-for-connecting-to-the-sap-system"></a><span data-ttu-id="eb327-182">SAP システムに接続するためのシングル サインオンの設定します。</span><span class="sxs-lookup"><span data-stu-id="eb327-182">Set up Single Sign-On for Connecting to the SAP System</span></span>  
 <span data-ttu-id="eb327-183">このトピックのすべての手順を実行した後は、SharePoint アプリケーションにインポートできるアプリケーション定義ファイルが作成されます。</span><span class="sxs-lookup"><span data-stu-id="eb327-183">After you have finished performing all the procedures in this topic, you will have created an application definition file that can be imported into a SharePoint application.</span></span> <span data-ttu-id="eb327-184">アプリケーションからは、SAP システムから関連するデータを取得する SAP メソッドを呼び出します。</span><span class="sxs-lookup"><span data-stu-id="eb327-184">From the application, you invoke the SAP methods to retrieve relevant data from the SAP system.</span></span> <span data-ttu-id="eb327-185">これを有効にするには、SharePoint アプリケーションで SAP システムのユーザーとユーザー間のマッピングを作成する必要があります。</span><span class="sxs-lookup"><span data-stu-id="eb327-185">To enable this, you must create a mapping between a user in the SAP system and the user in the SharePoint application.</span></span> <span data-ttu-id="eb327-186">アプリケーション定義ファイルをインポートした後は、SharePoint サーバーの全体管理コンソールでこのマッピングを作成します。</span><span class="sxs-lookup"><span data-stu-id="eb327-186">You create this mapping in SharePoint Central Administration console after you have imported the application definition file.</span></span>  
  
 <span data-ttu-id="eb327-187">ただし、マッピングを作成する必要がありますプロパティを設定する**SecondarySsoApplicationId**ビジネス データ カタログ定義エディターでします。</span><span class="sxs-lookup"><span data-stu-id="eb327-187">However, to create the mapping you must set a property **SecondarySsoApplicationId** in the Business Data Catalog Definition Editor.</span></span>  
  
##### <a name="to-set-the-secondaryssoapplicationid-property"></a><span data-ttu-id="eb327-188">SecondarySsoApplicationId のプロパティを設定するには</span><span class="sxs-lookup"><span data-stu-id="eb327-188">To set the SecondarySsoApplicationId property</span></span>  
  
1.  <span data-ttu-id="eb327-189">メタデータ オブジェクト ウィンドウで、展開、 **Customer_Order**ノードの順に展開し、**インスタンス**ノード。</span><span class="sxs-lookup"><span data-stu-id="eb327-189">In the Metadata Objects pane, expand the **Customer_Order** node, and then expand the **Instances** node.</span></span>  
  
2.  <span data-ttu-id="eb327-190">をクリックして**Customer_Order_Instance**、プロパティ ペインでに対して省略記号 (...) ボタンをクリックし、**プロパティ**ボックス。</span><span class="sxs-lookup"><span data-stu-id="eb327-190">Click **Customer_Order_Instance**, and in the Properties pane, click the ellipsis (…) button against the **Properties** box.</span></span>  
  
3.  <span data-ttu-id="eb327-191">PropertyView コレクション エディター] ウィンドウで、[**追加**、プロパティ ペインで次のように入力します。 **SecondarySsoApplicationId**の、**名前**ボックス。</span><span class="sxs-lookup"><span data-stu-id="eb327-191">In the PropertyView Collection Editor window, click **Add**, and in the Property pane, type **SecondarySsoApplicationId** for the **Name** box.</span></span> <span data-ttu-id="eb327-192">同様に、入力**SAPSSO**の**PropertyValue**ボックス。</span><span class="sxs-lookup"><span data-stu-id="eb327-192">Similarly, type **SAPSSO** for the **PropertyValue** box.</span></span> <span data-ttu-id="eb327-193">選択**System.String**の**型**ボックス。</span><span class="sxs-lookup"><span data-stu-id="eb327-193">Select **System.String** for the **Type** box.</span></span>  
  
     <span data-ttu-id="eb327-194">![SSO プロパティの追加](../../adapters-and-accelerators/adapter-sap/media/1eb813e4-fed2-45c2-8902-9af5dd3369bf.gif "1eb813e4-fed2-45c2-8902-9af5dd3369bf")</span><span class="sxs-lookup"><span data-stu-id="eb327-194">![Add the SSO property](../../adapters-and-accelerators/adapter-sap/media/1eb813e4-fed2-45c2-8902-9af5dd3369bf.gif "1eb813e4-fed2-45c2-8902-9af5dd3369bf")</span></span>  
  
4.  <span data-ttu-id="eb327-195">**[OK]** をクリックします。</span><span class="sxs-lookup"><span data-stu-id="eb327-195">Click **OK**.</span></span>  
  
### <a name="requirement-1-search-for-customers-based-on-customer-name"></a><span data-ttu-id="eb327-196">顧客名に基づいて顧客の要件 1: 検索</span><span class="sxs-lookup"><span data-stu-id="eb327-196">Requirement 1: Search for Customers Based on Customer Name</span></span>  
 <span data-ttu-id="eb327-197">顧客名に基づいて顧客の検索に使用できるアプリケーション定義ファイルを作成するには、次の一連のタスクを行う必要があります。</span><span class="sxs-lookup"><span data-stu-id="eb327-197">To create an application definition file that can be used to search for customers based on customer name, you must perform the following set of tasks.</span></span>  
  
-   <span data-ttu-id="eb327-198">SD_RFC_CUSTOMER_GET メソッドでは、フィルターを作成し、顧客名を格納するパラメーターにマップします。</span><span class="sxs-lookup"><span data-stu-id="eb327-198">In the SD_RFC_CUSTOMER_GET method, create a filter and map it to the parameter that stores the customer name.</span></span>  
  
-   <span data-ttu-id="eb327-199">作成、 **Finder** SD_RFC_CUSTOMER_GET メソッドのメソッドのインスタンス。</span><span class="sxs-lookup"><span data-stu-id="eb327-199">Create a **Finder** method instance for the SD_RFC_CUSTOMER_GET method.</span></span> <span data-ttu-id="eb327-200">A **Finder**メソッドは、フィルターに基づくレコードの一覧を取得します。</span><span class="sxs-lookup"><span data-stu-id="eb327-200">A **Finder** method retrieves a list of records based on a filter.</span></span>  
  
##### <a name="to-create-a-filter-and-map-it-to-the-customer-name-parameter"></a><span data-ttu-id="eb327-201">フィルターを作成して、顧客の name パラメーターにマップするには</span><span class="sxs-lookup"><span data-stu-id="eb327-201">To create a filter, and map it to the customer name parameter</span></span>  
  
1.  <span data-ttu-id="eb327-202">フィルターを作成します。</span><span class="sxs-lookup"><span data-stu-id="eb327-202">Create a filter.</span></span>  
  
    1.  <span data-ttu-id="eb327-203">メタデータ オブジェクト ウィンドウで、展開、**顧客**ノードの順に展開し、**メソッド**ノード。</span><span class="sxs-lookup"><span data-stu-id="eb327-203">In the Metadata Objects pane, expand the **Customer** node, and then expand the **Methods** node.</span></span>  
  
    2.  <span data-ttu-id="eb327-204">SD_RFC_CUSTOMER_GET メソッドを展開し、右クリックして**フィルター**、 をクリックし、**フィルターの追加**します。</span><span class="sxs-lookup"><span data-stu-id="eb327-204">Expand the SD_RFC_CUSTOMER_GET method, right-click **Filters**, and then click **Add Filter**.</span></span>  
  
         <span data-ttu-id="eb327-205">![メソッドにフィルターを追加](../../adapters-and-accelerators/adapter-sap/media/23eaab24-66e4-486f-8f99-02a5e0fef984.gif "23eaab24-66e4-486f-8f99-02a5e0fef984")</span><span class="sxs-lookup"><span data-stu-id="eb327-205">![Add filter to a method](../../adapters-and-accelerators/adapter-sap/media/23eaab24-66e4-486f-8f99-02a5e0fef984.gif "23eaab24-66e4-486f-8f99-02a5e0fef984")</span></span>  
  
    3.  <span data-ttu-id="eb327-206">プロパティ ペインで次のように入力します。 **CustomerName**で、**名前**ボックス。</span><span class="sxs-lookup"><span data-stu-id="eb327-206">In the Properties pane, type **CustomerName** in the **Name** box.</span></span>  
  
         <span data-ttu-id="eb327-207">![フィルターの名前を指定](../../adapters-and-accelerators/adapter-sap/media/0a0d0f85-a16a-4969-a122-097355141c27.gif "0a0d0f85-a16a-4969-a122-097355141c27")</span><span class="sxs-lookup"><span data-stu-id="eb327-207">![Specify a name for the filter](../../adapters-and-accelerators/adapter-sap/media/0a0d0f85-a16a-4969-a122-097355141c27.gif "0a0d0f85-a16a-4969-a122-097355141c27")</span></span>  
  
    4.  <span data-ttu-id="eb327-208">**FilterType**プロパティで、 **WildcardFilter**します。</span><span class="sxs-lookup"><span data-stu-id="eb327-208">For the **FilterType** property, select **WildcardFilter**.</span></span>  
  
2.  <span data-ttu-id="eb327-209">マップをフィルター、 **NAME1** SD_RFC_CUSTOMER_GET メソッドのパラメーター。</span><span class="sxs-lookup"><span data-stu-id="eb327-209">Map the filter to the **NAME1** parameter in the SD_RFC_CUSTOMER_GET method.</span></span>  
  
    1.  <span data-ttu-id="eb327-210">メタデータ オブジェクト ウィンドウで、展開、**顧客**ノードの順に展開し、**メソッド**ノード。</span><span class="sxs-lookup"><span data-stu-id="eb327-210">In the Metadata Objects pane, expand the **Customer** node, and then expand the **Methods** node.</span></span>  
  
    2.  <span data-ttu-id="eb327-211">SD_RFC_CUSTOMER_GET メソッドを展開し、展開、**パラメーター**ノード。</span><span class="sxs-lookup"><span data-stu-id="eb327-211">Expand the SD_RFC_CUSTOMER_GET method, and then expand the **Parameters** node.</span></span>  
  
    3.  <span data-ttu-id="eb327-212">展開、 **NAME1**ノード、2 つ目のクリックと**NAME1**ノード。</span><span class="sxs-lookup"><span data-stu-id="eb327-212">Expand the **NAME1** node, and click the second **NAME1** node.</span></span> <span data-ttu-id="eb327-213">**NAME1**パラメーターには、顧客の名前が含まれています。</span><span class="sxs-lookup"><span data-stu-id="eb327-213">The **NAME1** parameter contains the name of the customer.</span></span>  
  
    4.  <span data-ttu-id="eb327-214">プロパティ ペインで選択**CustomerName**から、 **FilterDescriptor**一覧。</span><span class="sxs-lookup"><span data-stu-id="eb327-214">In the Properties pane, select **CustomerName** from the **FilterDescriptor** list.</span></span>  
  
         <span data-ttu-id="eb327-215">![フィルターをメソッド パラメーターにマップ](../../adapters-and-accelerators/adapter-sap/media/6cc4ef85-503c-4847-95cb-633b902a715d.gif "6cc4ef85-503c-4847-95cb-633b902a715d")</span><span class="sxs-lookup"><span data-stu-id="eb327-215">![Map the filter to a method parameter](../../adapters-and-accelerators/adapter-sap/media/6cc4ef85-503c-4847-95cb-633b902a715d.gif "6cc4ef85-503c-4847-95cb-633b902a715d")</span></span>  
  
##### <a name="to-create-a-finder-method-instance-for-the-sdrfccustomerget-method"></a><span data-ttu-id="eb327-216">SD_RFC_CUSTOMER_GET メソッドの Finder メソッド インスタンスを作成するには</span><span class="sxs-lookup"><span data-stu-id="eb327-216">To create a Finder method instance for the SD_RFC_CUSTOMER_GET method</span></span>  
  
1.  <span data-ttu-id="eb327-217">メタデータ オブジェクト ウィンドウで、展開、**顧客**ノードの順に展開し、**メソッド**ノード。</span><span class="sxs-lookup"><span data-stu-id="eb327-217">In the Metadata Objects pane, expand the **Customer** node, and then expand the **Methods** node.</span></span>  
  
2.  <span data-ttu-id="eb327-218">展開、 **SD_RFC_CUSTOMER_GET**ノードを右クリックして**インスタンス**、順にクリックします**メソッド インスタンスの追加**メソッド インスタンスの作成 ウィンドウを開きます。</span><span class="sxs-lookup"><span data-stu-id="eb327-218">Expand the **SD_RFC_CUSTOMER_GET** node, right-click **Instances**, and then click **Add Method Instance** to open the Create Method Instance window.</span></span>  
  
     <span data-ttu-id="eb327-219">![メソッド インスタンスの追加](../../adapters-and-accelerators/adapter-sap/media/f583f8ef-e364-4665-8514-db033219ba0b.gif "f583f8ef-e364-4665-8514-db033219ba0b")</span><span class="sxs-lookup"><span data-stu-id="eb327-219">![Add a method instance](../../adapters-and-accelerators/adapter-sap/media/f583f8ef-e364-4665-8514-db033219ba0b.gif "f583f8ef-e364-4665-8514-db033219ba0b")</span></span>  
  
3.  <span data-ttu-id="eb327-220">メソッド インスタンスの作成 ウィンドウで、次のようにクリックします。 **Finder**の**メソッド インスタンスの型**します。</span><span class="sxs-lookup"><span data-stu-id="eb327-220">In the Create Method Instance window, click **Finder** for **Method Instance Type**.</span></span> <span data-ttu-id="eb327-221">選択**CUSTOMER_T**の**TypeDescriptor を返す**します。</span><span class="sxs-lookup"><span data-stu-id="eb327-221">Select **CUSTOMER_T** for **Return TypeDescriptor**.</span></span>  
  
     <span data-ttu-id="eb327-222">![Finder メソッド インスタンスの追加](../../adapters-and-accelerators/adapter-sap/media/e9ae47f2-32f5-4586-8467-94e3713d2a06.gif "e9ae47f2-32f5-4586-8467-94e3713d2a06")</span><span class="sxs-lookup"><span data-stu-id="eb327-222">![Add a Finder method instance](../../adapters-and-accelerators/adapter-sap/media/e9ae47f2-32f5-4586-8467-94e3713d2a06.gif "e9ae47f2-32f5-4586-8467-94e3713d2a06")</span></span>  
  
4.  <span data-ttu-id="eb327-223">**[OK]** をクリックします。</span><span class="sxs-lookup"><span data-stu-id="eb327-223">Click **OK**.</span></span>  
  
5.  <span data-ttu-id="eb327-224">プロパティ ペインで次のように入力します。 **GetCustomerByName_Instance**で、**名前**ボックス。</span><span class="sxs-lookup"><span data-stu-id="eb327-224">In the Properties pane, type **GetCustomerByName_Instance** in the **Name** box.</span></span>  
  
     <span data-ttu-id="eb327-225">![メソッド インスタンスの名前を指定](../../adapters-and-accelerators/adapter-sap/media/e44e02e8-b9fb-40ca-a55d-8bdc7ace02b5.gif "e44e02e8-b9fb-40ca-a55d-8bdc7ace02b5")</span><span class="sxs-lookup"><span data-stu-id="eb327-225">![Specify a name for the method instance](../../adapters-and-accelerators/adapter-sap/media/e44e02e8-b9fb-40ca-a55d-8bdc7ace02b5.gif "e44e02e8-b9fb-40ca-a55d-8bdc7ace02b5")</span></span>  
  
### <a name="requirement-2-retrieve-details-for-a-specific-customer-from-the-list-of-customers"></a><span data-ttu-id="eb327-226">要件 2: 顧客の一覧から特定の顧客の詳細を取得します。</span><span class="sxs-lookup"><span data-stu-id="eb327-226">Requirement 2: Retrieve Details for a Specific Customer from the List of Customers</span></span>  
 <span data-ttu-id="eb327-227">顧客名に基づいて顧客の検索に使用できるアプリケーション定義ファイルを作成するには、次の一連のタスクを行う必要があります。</span><span class="sxs-lookup"><span data-stu-id="eb327-227">To create an application definition file that can be used to search for customers based on customer name, you must perform the following set of tasks.</span></span>  
  
-   <span data-ttu-id="eb327-228">SD_RFC_CUSTOMER_GET メソッドでは、識別子を作成し、顧客番号を格納するパラメーターにマップします。</span><span class="sxs-lookup"><span data-stu-id="eb327-228">In the SD_RFC_CUSTOMER_GET method, create an identifier, and map it to the parameter that stores the customer number.</span></span>  
  
-   <span data-ttu-id="eb327-229">作成、 **Specificfinder** SD_RFC_CUSTOMER_GET メソッドのメソッドのインスタンス。</span><span class="sxs-lookup"><span data-stu-id="eb327-229">Create a **Specific Finder** method instance for the SD_RFC_CUSTOMER_GET method.</span></span> <span data-ttu-id="eb327-230">A **Specificfinder**メソッド識別子に基づいて特定のレコードを検索します。</span><span class="sxs-lookup"><span data-stu-id="eb327-230">A **Specific Finder** method finds a specific record based on an identifier.</span></span>  
  
##### <a name="to-create-an-identifier-and-map-it-to-the-customer-number-parameter"></a><span data-ttu-id="eb327-231">識別子を作成し、顧客番号パラメーターにマップするには</span><span class="sxs-lookup"><span data-stu-id="eb327-231">To create an identifier, and map it to the customer number parameter</span></span>  
  
1.  <span data-ttu-id="eb327-232">識別子を作成、**顧客**エンティティ。</span><span class="sxs-lookup"><span data-stu-id="eb327-232">Create an identifier for the **Customer** entity.</span></span>  
  
    1.  <span data-ttu-id="eb327-233">メタデータ オブジェクト ウィンドウで、展開、**顧客**ノード。</span><span class="sxs-lookup"><span data-stu-id="eb327-233">In the Metadata Objects pane, expand the **Customer** node.</span></span>  
  
    2.  <span data-ttu-id="eb327-234">右クリックし、**識別子**ノードをクリックして**追加識別子**します。</span><span class="sxs-lookup"><span data-stu-id="eb327-234">Right-click the **Identifiers** node, and then select **Add Identifier**.</span></span>  
  
         <span data-ttu-id="eb327-235">![メソッドへの識別子の追加](../../adapters-and-accelerators/adapter-sap/media/3adeeda3-426c-41fe-8d5c-5ca5863fb430.gif "3adeeda3-426c-41fe-8d5c-5ca5863fb430")</span><span class="sxs-lookup"><span data-stu-id="eb327-235">![Add an identifier to a method](../../adapters-and-accelerators/adapter-sap/media/3adeeda3-426c-41fe-8d5c-5ca5863fb430.gif "3adeeda3-426c-41fe-8d5c-5ca5863fb430")</span></span>  
  
    3.  <span data-ttu-id="eb327-236">プロパティ ペインで次のように入力します。 **CustomerID**で、**名前**ボックス。</span><span class="sxs-lookup"><span data-stu-id="eb327-236">In the Properties pane, type **CustomerID** in the **Name** box.</span></span>  
  
    4.  <span data-ttu-id="eb327-237">選択**System.String**の**型**ボックス。</span><span class="sxs-lookup"><span data-stu-id="eb327-237">Select **System.String** for the **Type** box.</span></span>  
  
         <span data-ttu-id="eb327-238">![識別子の名前を指定](../../adapters-and-accelerators/adapter-sap/media/a2304bca-9a54-4d2b-ba9f-461cfaafccb0.gif "a2304bca-9a54-4d2b-ba9f-461cfaafccb0")</span><span class="sxs-lookup"><span data-stu-id="eb327-238">![Specify a name for the identifier](../../adapters-and-accelerators/adapter-sap/media/a2304bca-9a54-4d2b-ba9f-461cfaafccb0.gif "a2304bca-9a54-4d2b-ba9f-461cfaafccb0")</span></span>  
  
2.  <span data-ttu-id="eb327-239">識別子をキー SD_RFC_CUSTOMER_GET メソッドのパラメーターにマップします。</span><span class="sxs-lookup"><span data-stu-id="eb327-239">Map the identifier to the key parameter for the SD_RFC_CUSTOMER_GET method.</span></span>  
  
    1.  <span data-ttu-id="eb327-240">メタデータ オブジェクト ウィンドウで、展開、**顧客**ノードの順に展開し、**メソッド**ノード。</span><span class="sxs-lookup"><span data-stu-id="eb327-240">In the Metadata Objects pane, expand the **Customer** node, and then expand the **Methods** node.</span></span>  
  
    2.  <span data-ttu-id="eb327-241">SD_RFC_CUSTOMER_GET メソッドを展開し、展開、**パラメーター**ノード。</span><span class="sxs-lookup"><span data-stu-id="eb327-241">Expand the SD_RFC_CUSTOMER_GET method, and then expand the **Parameters** node.</span></span>  
  
    3.  <span data-ttu-id="eb327-242">展開、 **KUNNR**パラメーターを 2 つ目のクリックして**KUNNR**ノード。</span><span class="sxs-lookup"><span data-stu-id="eb327-242">Expand the **KUNNR** parameter, and then click the second **KUNNR** node.</span></span>  
  
    4.  <span data-ttu-id="eb327-243">プロパティ ペインで選択**CustomerID [Customer]** から、**識別子**一覧。</span><span class="sxs-lookup"><span data-stu-id="eb327-243">In the Properties pane, select **CustomerID[Customer]** from the **Identifier** list.</span></span>  
  
         <span data-ttu-id="eb327-244">![識別子をパラメーターにマップ](../../adapters-and-accelerators/adapter-sap/media/04ff6496-34a7-421b-ae9e-f9263895c153.gif "04ff6496-34a7-421b-ae9e-f9263895c153")</span><span class="sxs-lookup"><span data-stu-id="eb327-244">![Map the identifier to a parameter](../../adapters-and-accelerators/adapter-sap/media/04ff6496-34a7-421b-ae9e-f9263895c153.gif "04ff6496-34a7-421b-ae9e-f9263895c153")</span></span>  
  
3.  <span data-ttu-id="eb327-245">入力パラメーターと戻り値パラメーター間の関連付けを設定します。</span><span class="sxs-lookup"><span data-stu-id="eb327-245">Set up an association between input and return parameters.</span></span>  
  
    1.  <span data-ttu-id="eb327-246">メタデータ オブジェクト ウィンドウで、展開、**顧客**ノードの順に展開し、**メソッド**ノード。</span><span class="sxs-lookup"><span data-stu-id="eb327-246">In the Metadata Objects pane, expand the **Customer** node, and then expand the **Methods** node.</span></span>  
  
    2.  <span data-ttu-id="eb327-247">SD_RFC_CUSTOMER_GET メソッドを展開し、展開、**パラメーター**ノード。</span><span class="sxs-lookup"><span data-stu-id="eb327-247">Expand the SD_RFC_CUSTOMER_GET method, and then expand the **Parameters** node.</span></span>  
  
    3.  <span data-ttu-id="eb327-248">展開、 **CUSTOMER_T** ] ノードの [2 番目の**CUSTOMER_T**ノード、**項目**ノードをクリック、 **KUNNR**ノード。</span><span class="sxs-lookup"><span data-stu-id="eb327-248">Expand the **CUSTOMER_T** node, then the second **CUSTOMER_T** node, then the **Item** node, and then click the **KUNNR** node.</span></span>  
  
    4.  <span data-ttu-id="eb327-249">プロパティ ペインで選択**CustomerID [Customer]** から、**識別子**一覧。</span><span class="sxs-lookup"><span data-stu-id="eb327-249">In the Properties pane, select **CustomerID[Customer]** from the **Identifier** list.</span></span>  
  
##### <a name="to-create-a-specific-finder-method-instance-for-the-sdrfccustomerget-method"></a><span data-ttu-id="eb327-250">SD_RFC_CUSTOMER_GET メソッド Specific Finder メソッド インスタンスを作成するには</span><span class="sxs-lookup"><span data-stu-id="eb327-250">To create a Specific Finder method instance for the SD_RFC_CUSTOMER_GET method</span></span>  
  
1.  <span data-ttu-id="eb327-251">メタデータ オブジェクト ウィンドウで、展開、**顧客**ノードをクリックし、**メソッド**ノード。</span><span class="sxs-lookup"><span data-stu-id="eb327-251">In the Metadata Objects pane, expand the **Customer** node, and then the **Methods** node.</span></span>  
  
2.  <span data-ttu-id="eb327-252">展開、 **SD_RFC_CUSTOMER_GET**ノードを右クリックして**インスタンス**、し、[**メソッド インスタンスの追加**メソッド インスタンスの作成] ウィンドウを開きます。</span><span class="sxs-lookup"><span data-stu-id="eb327-252">Expand the **SD_RFC_CUSTOMER_GET** node, right-click **Instances**, and then select **Add Method Instance** to open the Create Method Instance window.</span></span>  
  
     <span data-ttu-id="eb327-253">![メソッド インスタンスの追加](../../adapters-and-accelerators/adapter-sap/media/f583f8ef-e364-4665-8514-db033219ba0b.gif "f583f8ef-e364-4665-8514-db033219ba0b")</span><span class="sxs-lookup"><span data-stu-id="eb327-253">![Add a method instance](../../adapters-and-accelerators/adapter-sap/media/f583f8ef-e364-4665-8514-db033219ba0b.gif "f583f8ef-e364-4665-8514-db033219ba0b")</span></span>  
  
3.  <span data-ttu-id="eb327-254">メソッド インスタンスの作成 ウィンドウで、次のように選択します。 **Specificfinder**の**メソッド インスタンスの型**します。</span><span class="sxs-lookup"><span data-stu-id="eb327-254">In the Create Method Instance window, select **Specific Finder** for **Method Instance Type**.</span></span> <span data-ttu-id="eb327-255">同様に、選択**CUSTOMER_T**の**戻り値の TypeDescriptor**します。</span><span class="sxs-lookup"><span data-stu-id="eb327-255">Similarly, select **CUSTOMER_T** for **Return TypeDescriptor**.</span></span>  
  
     <span data-ttu-id="eb327-256">![Specific Finder メソッド インスタンスの追加](../../adapters-and-accelerators/adapter-sap/media/838eb512-b967-46e7-a865-0bf3651b02a1.gif "838eb512-b967-46e7-a865-0bf3651b02a1")</span><span class="sxs-lookup"><span data-stu-id="eb327-256">![Add a Specific Finder Method Instance](../../adapters-and-accelerators/adapter-sap/media/838eb512-b967-46e7-a865-0bf3651b02a1.gif "838eb512-b967-46e7-a865-0bf3651b02a1")</span></span>  
  
4.  <span data-ttu-id="eb327-257">**[OK]** をクリックします。</span><span class="sxs-lookup"><span data-stu-id="eb327-257">Click **OK**.</span></span>  
  
5.  <span data-ttu-id="eb327-258">プロパティ ペインで次のように入力します。 **GetCustomerByNumber_Instance**の、**名前**ボックス。</span><span class="sxs-lookup"><span data-stu-id="eb327-258">In the Properties pane, type **GetCustomerByNumber_Instance** for the **Name** box.</span></span>  
  
     <span data-ttu-id="eb327-259">![メソッド インスタンスの名前を指定](../../adapters-and-accelerators/adapter-sap/media/970f543c-cd06-4921-86c9-c110abdc7994.gif "970f543c-cd06-4921-86c9-c110abdc7994")</span><span class="sxs-lookup"><span data-stu-id="eb327-259">![Specify a name for the method instance](../../adapters-and-accelerators/adapter-sap/media/970f543c-cd06-4921-86c9-c110abdc7994.gif "970f543c-cd06-4921-86c9-c110abdc7994")</span></span>  
  
### <a name="requirement-3-retrieve-sales-order-details-for-a-specific-customer-from-the-list-of-customers"></a><span data-ttu-id="eb327-260">要件 3: 顧客の一覧から特定の顧客の販売注文の詳細を取得します。</span><span class="sxs-lookup"><span data-stu-id="eb327-260">Requirement 3: Retrieve Sales Order Details for a Specific Customer from the List of Customers</span></span>  
 <span data-ttu-id="eb327-261">特定の顧客の販売注文の詳細を取得するために使用するアプリケーション定義ファイルを作成するには、次の一連のタスクを行う必要があります。</span><span class="sxs-lookup"><span data-stu-id="eb327-261">To create an application definition file that can be used to retrieve sales order details for a specific customer, you must perform the following set of tasks.</span></span>  
  
-   <span data-ttu-id="eb327-262">間の関連付けを設定、**顧客**と**SalesOrder**エンティティ。</span><span class="sxs-lookup"><span data-stu-id="eb327-262">Set up an association between the **Customer** and **SalesOrder** entities.</span></span>  
  
-   <span data-ttu-id="eb327-263">作成、**アソシエーション**BAPI_SALESORDER_GETLIST メソッドのメソッド。</span><span class="sxs-lookup"><span data-stu-id="eb327-263">Create an **Association** method for the BAPI_SALESORDER_GETLIST method.</span></span>  
  
##### <a name="to-create-an-association-between-the-customer-and-salesorder-entities"></a><span data-ttu-id="eb327-264">顧客と SalesOrder エンティティ間のアソシエーションを作成するには</span><span class="sxs-lookup"><span data-stu-id="eb327-264">To create an association between the Customer and SalesOrder entities</span></span>  
  
1.  <span data-ttu-id="eb327-265">メタデータ オブジェクト ウィンドウで、展開、 **SalesOrder**ノードの順に展開し、**メソッド**ノード。</span><span class="sxs-lookup"><span data-stu-id="eb327-265">In the Metadata Objects pane, expand the **SalesOrder** node, and then expand the **Methods** node.</span></span>  
  
2.  <span data-ttu-id="eb327-266">BAPI_SALESORDER_GETLIST メソッドを展開し、展開、**パラメーター**ノード。</span><span class="sxs-lookup"><span data-stu-id="eb327-266">Expand the BAPI_SALESORDER_GETLIST method, and then expand the **Parameters** node.</span></span>  
  
3.  <span data-ttu-id="eb327-267">展開、 **CUSTOMER_NUMBER**ノード、2 つ目のクリックと**CUSTOMER_NUMBER**ノード。</span><span class="sxs-lookup"><span data-stu-id="eb327-267">Expand the **CUSTOMER_NUMBER** node, and then click the second **CUSTOMER_NUMBER** node.</span></span>  
  
4.  <span data-ttu-id="eb327-268">プロパティ ペインで選択**CustomerID [Customer]** から、**識別子**一覧。</span><span class="sxs-lookup"><span data-stu-id="eb327-268">In the Properties pane, select **CustomerID[Customer]** from the **Identifier** list.</span></span>  
  
     <span data-ttu-id="eb327-269">![2 つのエンティティ間の関連付け作成](../../adapters-and-accelerators/adapter-sap/media/ae7e1e7a-a12b-4905-b002-2a04c7050848.gif "ae7e1e7a-a12b-4905-b002-2a04c7050848")</span><span class="sxs-lookup"><span data-stu-id="eb327-269">![Create association between the two entities](../../adapters-and-accelerators/adapter-sap/media/ae7e1e7a-a12b-4905-b002-2a04c7050848.gif "ae7e1e7a-a12b-4905-b002-2a04c7050848")</span></span>  
  
##### <a name="to-create-an-association-method-instance-for-the-bapisalesordergetlist-method"></a><span data-ttu-id="eb327-270">BAPI_SALESORDER_GETLIST メソッドの Association メソッド インスタンスを作成するには</span><span class="sxs-lookup"><span data-stu-id="eb327-270">To create an Association method instance for the BAPI_SALESORDER_GETLIST method</span></span>  
  
1.  <span data-ttu-id="eb327-271">メタデータ オブジェクト ウィンドウで、展開、 **SalesOrder**ノードの順に展開し、**メソッド**ノード。</span><span class="sxs-lookup"><span data-stu-id="eb327-271">In the Metadata Objects pane, expand the **SalesOrder** node, and then expand the **Methods** node.</span></span>  
  
2.  <span data-ttu-id="eb327-272">展開、 **BAPI_SALESORDER_GETLIST**ノードを右クリックして**インスタンス**、し、[**メソッド インスタンスの追加**メソッド インスタンスの作成] ウィンドウを開きます。</span><span class="sxs-lookup"><span data-stu-id="eb327-272">Expand the **BAPI_SALESORDER_GETLIST** node, right-click **Instances**, and then select **Add Method Instance** to open the Create Method Instance window.</span></span>  
  
     <span data-ttu-id="eb327-273">![Association メソッド インスタンスの追加](../../adapters-and-accelerators/adapter-sap/media/c62a0d01-d4f3-470e-92f1-8a5cf666f8da.gif "c62a0d01-d4f3-470e-92f1-8a5cf666f8da")</span><span class="sxs-lookup"><span data-stu-id="eb327-273">![Add an Association Method Instance](../../adapters-and-accelerators/adapter-sap/media/c62a0d01-d4f3-470e-92f1-8a5cf666f8da.gif "c62a0d01-d4f3-470e-92f1-8a5cf666f8da")</span></span>  
  
3.  <span data-ttu-id="eb327-274">メソッド インスタンスの作成 ウィンドウで、次のように選択します。**アソシエーション**の**メソッド インスタンスの型**します。</span><span class="sxs-lookup"><span data-stu-id="eb327-274">In the Create Method Instance window, select **Association** for **Method Instance Type**.</span></span>  
  
4.  <span data-ttu-id="eb327-275">**ソース エンティティ**一覧で、**顧客**します。</span><span class="sxs-lookup"><span data-stu-id="eb327-275">In the **Source Entities** list, select **Customer**.</span></span>  
  
5.  <span data-ttu-id="eb327-276">**戻り値の TypeDescriptor**一覧で、 **SALES_ORDERS**.</span><span class="sxs-lookup"><span data-stu-id="eb327-276">In the **Return TypeDescriptor** list, select **SALES_ORDERS**..</span></span>  
  
     <span data-ttu-id="eb327-277">![Association メソッド インスタンスの作成](../../adapters-and-accelerators/adapter-sap/media/15975b78-8932-41ce-8c10-41891fc1fb22.gif "15975b78-8932-41ce-8c10-41891fc1fb22")</span><span class="sxs-lookup"><span data-stu-id="eb327-277">![Create an Association Method Instance](../../adapters-and-accelerators/adapter-sap/media/15975b78-8932-41ce-8c10-41891fc1fb22.gif "15975b78-8932-41ce-8c10-41891fc1fb22")</span></span>  
  
6.  <span data-ttu-id="eb327-278">**[OK]** をクリックします。</span><span class="sxs-lookup"><span data-stu-id="eb327-278">Click **OK**.</span></span>  
  
7.  <span data-ttu-id="eb327-279">プロパティ ペインで次のように入力します。 **SalesOrderForCustomer_Instance**の、**名前**ボックス。</span><span class="sxs-lookup"><span data-stu-id="eb327-279">In the Properties pane, type **SalesOrderForCustomer_Instance** for the **Name** box.</span></span>  
  
     <span data-ttu-id="eb327-280">![Association メソッドの名前を指定](../../adapters-and-accelerators/adapter-sap/media/0f1d13e4-e5a3-49ec-92a7-6329c6db1eb0.gif "0f1d13e4-e5a3-49ec-92a7-6329c6db1eb0")</span><span class="sxs-lookup"><span data-stu-id="eb327-280">![Specify a name for the Association Method](../../adapters-and-accelerators/adapter-sap/media/0f1d13e4-e5a3-49ec-92a7-6329c6db1eb0.gif "0f1d13e4-e5a3-49ec-92a7-6329c6db1eb0")</span></span>  
  
### <a name="remove-parameters-of-systemnullable-type"></a><span data-ttu-id="eb327-281">'System.nullable(of 型のパラメーターを削除します。</span><span class="sxs-lookup"><span data-stu-id="eb327-281">Remove Parameters of System.Nullable Type</span></span>  
 <span data-ttu-id="eb327-282">作成するときに、**アソシエーション**メソッド インスタンス SALES_ORDERS として戻り値の型を選択した BAPI_SALESORDER_GETLIST 方法の場合。</span><span class="sxs-lookup"><span data-stu-id="eb327-282">While creating the **Association** method instance for the BAPI_SALESORDER_GETLIST method, you selected the return type as SALES_ORDERS.</span></span> <span data-ttu-id="eb327-283">SALES_ORDER パラメーターを展開する場合、いくつかのパラメーターは System.Nullable 型がわかります。</span><span class="sxs-lookup"><span data-stu-id="eb327-283">If you expand the SALES_ORDER parameter, you will notice some parameters are of System.Nullable type.</span></span> <span data-ttu-id="eb327-284">ビジネス データ カタログ定義エディターで、パラメーターを選択しの値を調べて、入力パラメーターを確認できます、 **TypeName**プロパティ。</span><span class="sxs-lookup"><span data-stu-id="eb327-284">You can see the parameter type by selecting the parameter in the Business Data Catalog Definition Editor, and looking at the value for the **TypeName** property.</span></span>  
  
 <span data-ttu-id="eb327-285">このようなパラメーターでは、ビジネス データ カタログ定義エディターは、"Specified"サフィックスを持つが、同じ名前の別のパラメーターを作成します。</span><span class="sxs-lookup"><span data-stu-id="eb327-285">For such parameters, the Business Data Catalog Definition Editor creates another parameter with the same name but with a “Specified” suffix.</span></span> <span data-ttu-id="eb327-286">たとえば、パラメーターを見て*ITM_NUMBER*と*ITM_NUMBERSpecified*します。</span><span class="sxs-lookup"><span data-stu-id="eb327-286">For example, look at parameters *ITM_NUMBER* and *ITM_NUMBERSpecified*.</span></span> <span data-ttu-id="eb327-287">Microsoft Office SharePoint Server は System.Nullable パラメーターをサポートしていません。</span><span class="sxs-lookup"><span data-stu-id="eb327-287">Microsoft Office SharePoint Server does not support System.Nullable parameters.</span></span> <span data-ttu-id="eb327-288">そのため、System.Nullable パラメーターの型を含むレコードをしようとすると、例外をスローします。</span><span class="sxs-lookup"><span data-stu-id="eb327-288">So, when you try records that contain the System.Nullable parameter type, it throws an exception.</span></span> <span data-ttu-id="eb327-289">そのため、削除する必要あります (必要に応じて、「指定された」サフィックスと同じ名前を持つ)、両方のパラメーターからビジネス データ カタログ定義エディター</span><span class="sxs-lookup"><span data-stu-id="eb327-289">Therefore, you must remove both the parameters (with and without the “Specified” suffix and having the same name) from the Business Data Catalog Definition Editor</span></span>  
  
##### <a name="to-remove-the-parameters-of-systemnullable-type"></a><span data-ttu-id="eb327-290">'System.nullable(of 型のパラメーターを削除する</span><span class="sxs-lookup"><span data-stu-id="eb327-290">To remove the parameters of System.Nullable type</span></span>  
  
1.  <span data-ttu-id="eb327-291">メタデータ オブジェクト ウィンドウで、展開、 **SalesOrder**ノードの順に展開し、**メソッド**ノード。</span><span class="sxs-lookup"><span data-stu-id="eb327-291">In the Metadata Objects pane, expand the **SalesOrder** node, and then expand the **Methods** node.</span></span>  
  
2.  <span data-ttu-id="eb327-292">展開、 **BAPI_SALESORDER_GETLIST**ノードの順に展開し、**パラメーター**ノード。</span><span class="sxs-lookup"><span data-stu-id="eb327-292">Expand the **BAPI_SALESORDER_GETLIST** node, and then expand the **Parameters** node.</span></span>  
  
3.  <span data-ttu-id="eb327-293">展開**SALES_ORDERS**、2 つ目の展開**SALES_ORDERS**、順に展開**項目**します。</span><span class="sxs-lookup"><span data-stu-id="eb327-293">Expand **SALES_ORDERS**, expand the second **SALES_ORDERS**, and then expand **Item**.</span></span>  
  
4.  <span data-ttu-id="eb327-294">名前に"Specified"サフィックスを含むパラメーターを右クリックし、**削除**します。</span><span class="sxs-lookup"><span data-stu-id="eb327-294">Right-click the parameter that contains the "Specified" suffix in the name, and then select **Delete**.</span></span>  
  
5.  <span data-ttu-id="eb327-295">サフィックスが付いて、削除するパラメーターと同じ名前を持つパラメーターを右クリックし、**削除**します。</span><span class="sxs-lookup"><span data-stu-id="eb327-295">Right-click the parameter that has the same name as the parameter you deleted, without the suffix, and then select **Delete**.</span></span> <span data-ttu-id="eb327-296">通常、このパラメーターは、「指定された」サフィックスを持つパラメーターの前に適切なです。</span><span class="sxs-lookup"><span data-stu-id="eb327-296">Typically, this parameter is right before the parameter that has the "Specified" suffix.</span></span>  
  
### <a name="set-default-parameters"></a><span data-ttu-id="eb327-297">既定のパラメーターを設定します。</span><span class="sxs-lookup"><span data-stu-id="eb327-297">Set Default Parameters</span></span>  
 <span data-ttu-id="eb327-298">BAPI_SALESORDER_GETLIST は 2 つのパラメーターを受け取ります。</span><span class="sxs-lookup"><span data-stu-id="eb327-298">The BAPI_SALESORDER_GETLIST takes two parameters.</span></span> <span data-ttu-id="eb327-299">TRANSACTION_GROUP、これらのパラメーターの 1 つは、既定のパラメーターです。</span><span class="sxs-lookup"><span data-stu-id="eb327-299">One of these parameters, TRANSACTION_GROUP, is the default parameter.</span></span> <span data-ttu-id="eb327-300">そのため、このパラメーターの既定値を設定する必要があります。</span><span class="sxs-lookup"><span data-stu-id="eb327-300">So, you must set the default value for this parameter.</span></span>  
  
##### <a name="to-set-the-default-value-for-transactiongroup"></a><span data-ttu-id="eb327-301">TRANSACTION_GROUP の既定値を設定するには</span><span class="sxs-lookup"><span data-stu-id="eb327-301">To set the default value for TRANSACTION_GROUP</span></span>  
  
1.  <span data-ttu-id="eb327-302">メタデータ オブジェクト ウィンドウで、展開、 **SalesOrder**ノードの順に展開し、**メソッド**ノード。</span><span class="sxs-lookup"><span data-stu-id="eb327-302">In the Metadata Objects pane, expand the **SalesOrder** node, and then expand the **Methods** node.</span></span>  
  
2.  <span data-ttu-id="eb327-303">展開、 **BAPI_SALESORDER_GETLIST**ノードの順に展開し、**インスタンス**ノード。</span><span class="sxs-lookup"><span data-stu-id="eb327-303">Expand the **BAPI_SALESORDER_GETLIST** node, and then expand the **Instances** node.</span></span>  
  
3.  <span data-ttu-id="eb327-304">選択、 **SalesOrderForCustomer_Instance**メソッド インスタンス、およびプロパティ ペインで、に対して省略記号ボタン (…) をクリックします。、 **DefaultValues**ボックス。</span><span class="sxs-lookup"><span data-stu-id="eb327-304">Select the **SalesOrderForCustomer_Instance** method instance, and in the Properties pane, click the ellipsis button (…) against the **DefaultValues** box.</span></span>  
  
4.  <span data-ttu-id="eb327-305">編集ウィンドウで  **TRANSACTION_GROUP**ノード、および、 **TRANSACTION_GROUP**ボックスで、既定値 0 を指定します。</span><span class="sxs-lookup"><span data-stu-id="eb327-305">In the Edit window, expand **TRANSACTION_GROUP** node, and for the **TRANSACTION_GROUP** box, specify the default value 0.</span></span>  
  
     <span data-ttu-id="eb327-306">![メソッド インスタンスの既定値を指定](../../adapters-and-accelerators/adapter-sap/media/86e0a42d-61c0-4d5d-ba3f-55b328f79576.gif "86e0a42d-61c0-4d5d-ba3f-55b328f79576")</span><span class="sxs-lookup"><span data-stu-id="eb327-306">![Specify a default value for the method instance](../../adapters-and-accelerators/adapter-sap/media/86e0a42d-61c0-4d5d-ba3f-55b328f79576.gif "86e0a42d-61c0-4d5d-ba3f-55b328f79576")</span></span>  
  
5.  <span data-ttu-id="eb327-307">**[閉じる]** をクリックします。</span><span class="sxs-lookup"><span data-stu-id="eb327-307">Click **Close**.</span></span>  
  
### <a name="export-the-application-definition-to-a-file"></a><span data-ttu-id="eb327-308">アプリケーション定義をファイルにエクスポートします。</span><span class="sxs-lookup"><span data-stu-id="eb327-308">Export the Application Definition to a File</span></span>  
 <span data-ttu-id="eb327-309">SAP システム インスタンスのメタデータを含むアプリケーション定義が作成されました。</span><span class="sxs-lookup"><span data-stu-id="eb327-309">You have now created an application definition that contains the SAP system instance metadata.</span></span> <span data-ttu-id="eb327-310">Microsoft Office SharePoint Server にインポートできる XML ファイルには、この定義をエクスポートする必要があります。</span><span class="sxs-lookup"><span data-stu-id="eb327-310">You must export this definition to an XML file, which can be imported into Microsoft Office SharePoint Server.</span></span>  
  
##### <a name="to-export-the-application-definition-to-a-file"></a><span data-ttu-id="eb327-311">アプリケーション定義をファイルにエクスポートするには</span><span class="sxs-lookup"><span data-stu-id="eb327-311">To export the application definition to a file</span></span>  
  
1.  <span data-ttu-id="eb327-312">メタデータ オブジェクトのウィンドウで右クリックし、 **Customer_Order**ノード、およびクリック**エクスポート**します。</span><span class="sxs-lookup"><span data-stu-id="eb327-312">In the Metadata Objects pane, right-click the **Customer_Order** node, and then click **Export**.</span></span>  
  
2.  <span data-ttu-id="eb327-313">Customer_Order.xml として保存します。</span><span class="sxs-lookup"><span data-stu-id="eb327-313">Save the file as Customer_Order.xml.</span></span>  
  
## <a name="next-steps"></a><span data-ttu-id="eb327-314">次の手順</span><span class="sxs-lookup"><span data-stu-id="eb327-314">Next Steps</span></span>  
 <span data-ttu-id="eb327-315">SAP システムからデータを取得する SharePoint アプリケーションを作成する必要がありますようになりました。</span><span class="sxs-lookup"><span data-stu-id="eb327-315">You must now create a SharePoint application to retrieve data from an SAP system.</span></span> <span data-ttu-id="eb327-316">参照してください[手順 3: SAP からデータを取得する SharePoint アプリケーションを作成](../../adapters-and-accelerators/adapter-sap/step-3-create-a-sharepoint-application-to-retrieve-data-from-sap.md)手順についてはします。</span><span class="sxs-lookup"><span data-stu-id="eb327-316">See [Step 3: Create a SharePoint Application to Retrieve Data from SAP](../../adapters-and-accelerators/adapter-sap/step-3-create-a-sharepoint-application-to-retrieve-data-from-sap.md) for instructions.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="eb327-317">参照</span><span class="sxs-lookup"><span data-stu-id="eb327-317">See Also</span></span>  
 [<span data-ttu-id="eb327-318">チュートリアル 1: SAP システムからのデータを SharePoint サイトに表示する</span><span class="sxs-lookup"><span data-stu-id="eb327-318">Tutorial 1: Presenting Data from an SAP System on a SharePoint Site</span></span>](../../adapters-and-accelerators/adapter-sap/tutorial-1-presenting-data-from-an-sap-system-on-a-sharepoint-site.md)