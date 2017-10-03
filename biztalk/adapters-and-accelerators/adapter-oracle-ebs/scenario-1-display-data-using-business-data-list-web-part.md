---
title: "シナリオ 1: ビジネス データ一覧 web パーツを使用してデータの表示 |Microsoft ドキュメント"
ms.custom: 
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: 
ms.suite: 
ms.tgt_pltfrm: 
ms.topic: article
ms.assetid: b3831814-8b70-4352-b22f-cebd08750ef5
caps.latest.revision: "6"
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: e1add974ca3ad0b80b7838b120920f4de47f1650
ms.sourcegitcommit: cb908c540d8f1a692d01dc8f313e16cb4b4e696d
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 09/20/2017
---
# <a name="scenario-1-display-data-using-business-data-list-web-part"></a><span data-ttu-id="74afc-102">シナリオ 1: ビジネス データ一覧 web パーツを使用してデータを表示します。</span><span class="sxs-lookup"><span data-stu-id="74afc-102">Scenario 1: Display data using Business Data List web part</span></span>
<span data-ttu-id="74afc-103">使用して、**ビジネス データ一覧**用の Web パーツ、 **Finder**メソッド インスタンス。</span><span class="sxs-lookup"><span data-stu-id="74afc-103">We will use the **Business Data List** Web Part for the **Finder** method instance.</span></span> <span data-ttu-id="74afc-104">この Web パーツでは、Oracle E-business Suite から従業員の一覧を取得する検索文字列を指定することができます。</span><span class="sxs-lookup"><span data-stu-id="74afc-104">This Web Part enables you to specify a search expression to retrieve a list of employees from Oracle E-Business Suite.</span></span> <span data-ttu-id="74afc-105">このチュートリアルでは、これには、ディスプレイの従業員の Web パーツを呼び出されます。</span><span class="sxs-lookup"><span data-stu-id="74afc-105">For this tutorial, this is called the Display Employees Web Part.</span></span> <span data-ttu-id="74afc-106">このセクションでは、この Web パーツを作成する手順を説明します。</span><span class="sxs-lookup"><span data-stu-id="74afc-106">This section provides instructions to create this Web Part.</span></span> <span data-ttu-id="74afc-107">Web パーツの作成の詳細についてを参照してください「ビジネス データ リストのカスタマイズ、Web パーツ、およびサイト」で[http://go.microsoft.com/fwlink/?LinkId=104131](http://go.microsoft.com/fwlink/?LinkId=104131)です。</span><span class="sxs-lookup"><span data-stu-id="74afc-107">For more information about creating Web Parts, see "Customize business data lists, Web Parts, and sites" at [http://go.microsoft.com/fwlink/?LinkId=104131](http://go.microsoft.com/fwlink/?LinkId=104131).</span></span>  
  
 <span data-ttu-id="74afc-108">Web パーツを追加する前に、Web パーツ ページを作成する必要があります。</span><span class="sxs-lookup"><span data-stu-id="74afc-108">You must create a Web Part page before adding the Web Parts.</span></span>  
  
## <a name="creating-a-web-part-page"></a><span data-ttu-id="74afc-109">Web パーツ ページを作成します。</span><span class="sxs-lookup"><span data-stu-id="74afc-109">Creating a Web Part Page</span></span>  
 <span data-ttu-id="74afc-110">このセクションでは、Web パーツ ページを作成する手順を説明します。</span><span class="sxs-lookup"><span data-stu-id="74afc-110">This section provides instructions to create a Web Part page.</span></span>  
  
###  <span data-ttu-id="74afc-111"><a name="WebPart"></a>Web パーツ ページを作成するには</span><span class="sxs-lookup"><span data-stu-id="74afc-111"><a name="WebPart"></a> To create a Web Part page</span></span>  
  
1.  <span data-ttu-id="74afc-112">SharePoint 3.0 サーバーの全体管理を開始します。</span><span class="sxs-lookup"><span data-stu-id="74afc-112">Start SharePoint 3.0 Central Administration.</span></span> <span data-ttu-id="74afc-113">をクリックして**開始**、 をポイント**すべてのプログラム**、 をポイント**Microsoft Office Server**、 をクリック**SharePoint 3.0 サーバーの全体管理**です。</span><span class="sxs-lookup"><span data-stu-id="74afc-113">Click **Start**, point to **All Programs**, point to **Microsoft Office Server**, and click **SharePoint 3.0 Central Administration**.</span></span>  
  
2.  <span data-ttu-id="74afc-114">左側のナビゲーション ウィンドウで、アプリケーション定義をインポートする SSP の名前をクリックします。</span><span class="sxs-lookup"><span data-stu-id="74afc-114">In the left navigation pane, click the name of the SSP to which you want to import the application definition.</span></span>  
  
3.  <span data-ttu-id="74afc-115">共有サービスの管理 ページの右上隅で、をクリックして**サイトの操作**、クリックして**作成**です。</span><span class="sxs-lookup"><span data-stu-id="74afc-115">On the Shared Services Administration page, in the upper-right corner, click **Site Actions**, and then click **Create**.</span></span>  
  
     <span data-ttu-id="74afc-116">![Web パーツを作成するにはメニュー](../../adapters-and-accelerators/adapter-oracle-ebs/media/a9872c3e-f823-4c47-a538-19242565d2e9.gif "a9872c3e-f823-4c47-a538-19242565d2e9")</span><span class="sxs-lookup"><span data-stu-id="74afc-116">![Menu to create a web part](../../adapters-and-accelerators/adapter-oracle-ebs/media/a9872c3e-f823-4c47-a538-19242565d2e9.gif "a9872c3e-f823-4c47-a538-19242565d2e9")</span></span>  
  
4.  <span data-ttu-id="74afc-117">作成 ページで、 **Web ページ**セクションで、 **Web パーツ ページ**です。</span><span class="sxs-lookup"><span data-stu-id="74afc-117">On the Create page, in the **Web Pages** section, click **Web Part Page**.</span></span>  
  
5.  <span data-ttu-id="74afc-118">新しい Web パーツ ページには、次の操作を行います。</span><span class="sxs-lookup"><span data-stu-id="74afc-118">On the New Web Part page, do the following:</span></span>  
  
    1.  <span data-ttu-id="74afc-119">**名前**フィールドに、ページの名前を入力します。</span><span class="sxs-lookup"><span data-stu-id="74afc-119">In the **Name** field, type a name for the page.</span></span> <span data-ttu-id="74afc-120">このチュートリアルでは、名前を入力しますとして**MS_SAMPLE_EMPLOYEE**です。</span><span class="sxs-lookup"><span data-stu-id="74afc-120">For this tutorial, type the name as **MS_SAMPLE_EMPLOYEE**.</span></span>  
  
    2.  <span data-ttu-id="74afc-121">選択、**ファイルが既に存在する場合に上書き**チェック ボックスを作成する新しいページと同じ名前の古いページを上書きする場合。</span><span class="sxs-lookup"><span data-stu-id="74afc-121">Select the **Overwrite if file already exists** check box, if you want to overwrite old pages with the same name as the new page you create.</span></span>  
  
    3.  <span data-ttu-id="74afc-122">**レイアウト** セクションから、**レイアウト テンプレートを選択して**ボックスで、Web パーツ ページのレイアウトを選択します。</span><span class="sxs-lookup"><span data-stu-id="74afc-122">In the **Layout** section, from the **Choose a Layout Template** box, select a layout for the Web Part page.</span></span> <span data-ttu-id="74afc-123">このチュートリアルでは、次のように選択します。**ページ全体を垂直方向**です。</span><span class="sxs-lookup"><span data-stu-id="74afc-123">For this tutorial, select **Full Page, Vertical**.</span></span>  
  
    4.  <span data-ttu-id="74afc-124">**保存場所**セクションで、**ドキュメント ライブラリ**一覧で、クリックして**フォーム テンプレート**です。</span><span class="sxs-lookup"><span data-stu-id="74afc-124">In the **Save Location** section, in the **Document Library** list, click **Form Templates**.</span></span>  
  
    5.  <span data-ttu-id="74afc-125">**[作成]**をクリックします。</span><span class="sxs-lookup"><span data-stu-id="74afc-125">Click **Create**.</span></span> <span data-ttu-id="74afc-126">次の図は、作成した後、Web パーツ ページを示します。</span><span class="sxs-lookup"><span data-stu-id="74afc-126">The following figure shows the Web Part page after it is created.</span></span>  
  
         <span data-ttu-id="74afc-127">![新しい WebPart ページ](../../adapters-and-accelerators/adapter-oracle-ebs/media/23-web-part.gif "23 _ web_part")</span><span class="sxs-lookup"><span data-stu-id="74afc-127">![The new WebPart page](../../adapters-and-accelerators/adapter-oracle-ebs/media/23-web-part.gif "23_Web_Part")</span></span>  
  
    6.  <span data-ttu-id="74afc-128">このページに Web パーツを追加する必要があります。</span><span class="sxs-lookup"><span data-stu-id="74afc-128">You must now add the Web Parts to this page.</span></span>  
  
## <a name="adding-a-business-data-list-web-part"></a><span data-ttu-id="74afc-129">ビジネス データ一覧 Web パーツを追加します。</span><span class="sxs-lookup"><span data-stu-id="74afc-129">Adding a Business Data List Web Part</span></span>  
 <span data-ttu-id="74afc-130">ビジネス データ一覧 Web パーツを Web パーツ ページに追加する必要があります。</span><span class="sxs-lookup"><span data-stu-id="74afc-130">You must now add a Business Data List Web Part to the Web Part page.</span></span> <span data-ttu-id="74afc-131">この Web パーツを使用して、検索式に一致する Oracle E-business Suite で MS_SAMPLE_EMPLOYEE インターフェイス テーブルから従業員レコードの一覧が取得されます。</span><span class="sxs-lookup"><span data-stu-id="74afc-131">Using this Web Part you will retrieve a list of employee records from the MS_SAMPLE_EMPLOYEE interface table in Oracle E-Business Suite that matches a search expression.</span></span> <span data-ttu-id="74afc-132">この Web パーツに対応する、 **Finder**メソッド インスタンス (*Finder_Instance*) で、ビジネス データ カタログ定義エディターを作成しました。</span><span class="sxs-lookup"><span data-stu-id="74afc-132">This Web Part corresponds to the **Finder** method instance (*Finder_Instance*) that you created in the Business Data Catalog Definition Editor.</span></span>  
  
#### <a name="to-add-a-business-data-list-web-part"></a><span data-ttu-id="74afc-133">ビジネス データ一覧 Web パーツを追加するには</span><span class="sxs-lookup"><span data-stu-id="74afc-133">To add a Business Data List Web Part</span></span>  
  
1.  <span data-ttu-id="74afc-134">MS_SAMPLE_EMPLOYEE ページで、をクリックして**Web パーツの追加**です。</span><span class="sxs-lookup"><span data-stu-id="74afc-134">On the MS_SAMPLE_EMPLOYEE page, click **Add a Web Part**.</span></span>  
  
2.  <span data-ttu-id="74afc-135">**Web パーツの追加** ダイアログ ボックスで、**ビジネス データ** セクションで、選択、**ビジネス データ一覧**チェック ボックスをクリックして**追加**です。</span><span class="sxs-lookup"><span data-stu-id="74afc-135">In the **Add Web Parts** dialog box, in the **Business Data** section, select the **Business Data List** check box, and then click **Add**.</span></span>  
  
     <span data-ttu-id="74afc-136">![ビジネス データ Web パーツを作成するオプションを](../../adapters-and-accelerators/adapter-oracle-ebs/media/ae7c952c-1592-495f-9452-c1bffd44421c.gif "ae7c952c-1592-495f-9452-c1bffd44421c")</span><span class="sxs-lookup"><span data-stu-id="74afc-136">![Options to create a business data Web Part](../../adapters-and-accelerators/adapter-oracle-ebs/media/ae7c952c-1592-495f-9452-c1bffd44421c.gif "ae7c952c-1592-495f-9452-c1bffd44421c")</span></span>  
  
3.  <span data-ttu-id="74afc-137">新しく追加されたビジネス データ一覧 Web パーツ、クリックして、**ツール ウィンドウを開いて**リンクします。</span><span class="sxs-lookup"><span data-stu-id="74afc-137">In the newly added Business Data List Web Part, click the **Open the tool pane** link.</span></span>  
  
     <span data-ttu-id="74afc-138">![Web パーツのツール ウィンドウを開いて](../../adapters-and-accelerators/adapter-oracle-ebs/media/4e7a1cb1-69dc-4e0d-a211-6a217dc4a549.gif "4e7a1cb1-69dc-4e0d-a211-6a217dc4a549")</span><span class="sxs-lookup"><span data-stu-id="74afc-138">![Open the tool pane for Web Part](../../adapters-and-accelerators/adapter-oracle-ebs/media/4e7a1cb1-69dc-4e0d-a211-6a217dc4a549.gif "4e7a1cb1-69dc-4e0d-a211-6a217dc4a549")</span></span>  
  
4.  <span data-ttu-id="74afc-139">ビジネス データ一覧のツール ウィンドウは、右側のウィンドウで開きます。</span><span class="sxs-lookup"><span data-stu-id="74afc-139">The Business Data List tool pane opens in the right pane.</span></span> <span data-ttu-id="74afc-140">**ビジネス データ一覧** セクションの**型**フィールドで、をクリックして、**参照**ボタンをクリックします。</span><span class="sxs-lookup"><span data-stu-id="74afc-140">In the **Business Data List** section, for the **Type** field, click the **Browse** button.</span></span>  
  
     <span data-ttu-id="74afc-141">![ビジネス データ一覧のツール ウィンドウ](../../adapters-and-accelerators/adapter-oracle-ebs/media/24-bdc-browse.gif "24 _ bdc_browse")</span><span class="sxs-lookup"><span data-stu-id="74afc-141">![Business Data List tool pane](../../adapters-and-accelerators/adapter-oracle-ebs/media/24-bdc-browse.gif "24_BDC_Browse")</span></span>  
  
5.  <span data-ttu-id="74afc-142">**ビジネス データの種類の選択**ダイアログ ボックスで、 **MS_SAMPLE_EMPLOYEE_Instance**クリックしてアプリケーションでは、 **OK**です。</span><span class="sxs-lookup"><span data-stu-id="74afc-142">In the **Business Data Type Picker** dialog box, select the **MS_SAMPLE_EMPLOYEE_Instance** application, and then click **OK**.</span></span>  
  
     <span data-ttu-id="74afc-143">![アプリケーション インスタンスの選択](../../adapters-and-accelerators/adapter-oracle-ebs/media/25-bdc-picker.gif "25 _ bdc_picker")</span><span class="sxs-lookup"><span data-stu-id="74afc-143">![Select the application instance](../../adapters-and-accelerators/adapter-oracle-ebs/media/25-bdc-picker.gif "25_BDC_Picker")</span></span>  
  
6.  <span data-ttu-id="74afc-144">展開、**外観**ノード、および、**タイトル**ボックスで、Web パーツのタイトルを入力します。</span><span class="sxs-lookup"><span data-stu-id="74afc-144">Expand the **Appearance** node, and in the **Title** box, type a title for the Web Part.</span></span> <span data-ttu-id="74afc-145">この Web パーツの次のように入力します。**従業員一覧**です。</span><span class="sxs-lookup"><span data-stu-id="74afc-145">For this Web Part, type **Employee List**.</span></span>  
  
7.  <span data-ttu-id="74afc-146">ビジネス データ一覧のツール ウィンドウで、をクリックして**適用**、クリックして**OK**です。</span><span class="sxs-lookup"><span data-stu-id="74afc-146">In the Business Data List tool pane, click **Apply**, and then click **OK**.</span></span> <span data-ttu-id="74afc-147">ビジネス データ一覧 Web パーツは、次のようになります。</span><span class="sxs-lookup"><span data-stu-id="74afc-147">The Business Data List Web Part now looks like the following:</span></span>  
  
     <span data-ttu-id="74afc-148">![ビジネス データ一覧 Web パーツ](../../adapters-and-accelerators/adapter-oracle-ebs/media/26-bdc-webpart.gif "26 _ bdc_webpart")</span><span class="sxs-lookup"><span data-stu-id="74afc-148">![Business Data List Web Part](../../adapters-and-accelerators/adapter-oracle-ebs/media/26-bdc-webpart.gif "26_BDC_WebPart")</span></span>  
  
8.  <span data-ttu-id="74afc-149">Web パーツには、MS_SAMPLE_EMPLOYEE インターフェイス テーブルに対する選択操作を実行することによって返されるフィールドが一覧表示します。</span><span class="sxs-lookup"><span data-stu-id="74afc-149">The Web Part lists the fields that are returned by executing the Select operation on the MS_SAMPLE_EMPLOYEE interface table.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="74afc-150">参照</span><span class="sxs-lookup"><span data-stu-id="74afc-150">See Also</span></span>  
 <span data-ttu-id="74afc-151">[手順 3: Oracle E-business Suite からデータを取得する SharePoint アプリケーションを作成します。](../../adapters-and-accelerators/adapter-oracle-ebs/step-3-create-a-sharepoint-application-to-retrieve-data-from-oracle-ebs.md) </span><span class="sxs-lookup"><span data-stu-id="74afc-151">[Step 3: Create a SharePoint Application to Retrieve Data from Oracle E-Business Suite](../../adapters-and-accelerators/adapter-oracle-ebs/step-3-create-a-sharepoint-application-to-retrieve-data-from-oracle-ebs.md) </span></span>  
 [<span data-ttu-id="74afc-152">検索ボックス Web パーツを使用して検索をシナリオ 2。</span><span class="sxs-lookup"><span data-stu-id="74afc-152">Scenario 2: Search Using the Search Box Web Part</span></span>](../../adapters-and-accelerators/adapter-oracle-ebs/scenario-2-search-using-the-search-box-web-part.md)