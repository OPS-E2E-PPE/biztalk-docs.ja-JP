---
title: 'シナリオ 2: 検索ボックス web パーツを使用して検索を |Microsoft ドキュメント'
ms.custom: ''
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: ''
ms.suite: ''
ms.tgt_pltfrm: ''
ms.topic: article
ms.assetid: a233772f-7577-4ac5-b55a-cb1ba2f464c7
caps.latest.revision: 9
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: 03e536df00499e8965632a3952eb3ae50e3f83df
ms.sourcegitcommit: cb908c540d8f1a692d01dc8f313e16cb4b4e696d
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 09/20/2017
ms.locfileid: "22218546"
---
# <a name="scenario-2--search-using-the-search-box-web-part"></a><span data-ttu-id="05726-102">検索ボックス web パーツを使用して検索をシナリオ 2。</span><span class="sxs-lookup"><span data-stu-id="05726-102">Scenario 2:  Search using the search box web part</span></span>
<span data-ttu-id="05726-103">Microsoft Office SharePoint server の全文検索を実行できるを使用して検索アプリケーションを構成する検索の設定を構成する Oracle E-business Suite で MS_SAMPLE_EMPLOYEE インターフェイス テーブル。</span><span class="sxs-lookup"><span data-stu-id="05726-103">We will configure the search settings in Microsoft Office SharePoint Server to configure a search application using which you can perform a full text search on the MS_SAMPLE_EMPLOYEE interface table in Oracle E-Business Suite.</span></span> <span data-ttu-id="05726-104">後から検索を行うことができますに検索ボックス Web パーツを追加します。</span><span class="sxs-lookup"><span data-stu-id="05726-104">Later, we will add a Search Box Web Part to from where you can perform the search.</span></span>  
  
 
  
##  <a name="Define"></a><span data-ttu-id="05726-105">コンテンツのソースを定義します。</span><span class="sxs-lookup"><span data-stu-id="05726-105">Define the Content Source</span></span>  
 <span data-ttu-id="05726-106">このセクションでは、Microsoft Office SharePoint Server が、データをクロールする場所からのコンテンツ ソースの定義について説明します。</span><span class="sxs-lookup"><span data-stu-id="05726-106">This section talks about defining a content source from where Microsoft Office SharePoint Server can crawl the data.</span></span> <span data-ttu-id="05726-107">メソッドのインスタンスに作成される Id の列挙子へのコンテンツのマッピングが含まれます[手順 2: Oracle E-business Suite 成果物のためのアプリケーション定義ファイルを作成する](../../adapters-and-accelerators/adapter-oracle-ebs/step-2-create-an-application-definition-file-for-the-oracle-ebs-artifacts.md)です。</span><span class="sxs-lookup"><span data-stu-id="05726-107">This involves mapping the content to the Id Enumerator method instance created in [Step 2: Create an application definition file for the Oracle E-Business Suite artifacts](../../adapters-and-accelerators/adapter-oracle-ebs/step-2-create-an-application-definition-file-for-the-oracle-ebs-artifacts.md).</span></span>  
  
#### <a name="to-define-a-content-source"></a><span data-ttu-id="05726-108">コンテンツ ソースを定義するには</span><span class="sxs-lookup"><span data-stu-id="05726-108">To define a content source</span></span>  
  
1.  <span data-ttu-id="05726-109">SharePoint 3.0 サーバーの全体管理を開始します。</span><span class="sxs-lookup"><span data-stu-id="05726-109">Start SharePoint 3.0 Central Administration.</span></span> <span data-ttu-id="05726-110">をクリックして**開始**、 をポイント**すべてのプログラム**、 をポイント**Microsoft Office Server**、クリックして**SharePoint 3.0 サーバーの全体管理**.</span><span class="sxs-lookup"><span data-stu-id="05726-110">Click **Start**, point to **All Programs**, point to **Microsoft Office Server**, and then click **SharePoint 3.0 Central Administration**.</span></span>  
  
2.  <span data-ttu-id="05726-111">左側のナビゲーション ウィンドウで、名前の共有サービス プロバイダー (SSP) の検索アプリケーションを構成する場合をクリックします。</span><span class="sxs-lookup"><span data-stu-id="05726-111">In the left navigation pane, click the name of the Shared Service Provider (SSP) where you want to configure the search application.</span></span>  
  
3.  <span data-ttu-id="05726-112">[ホーム] ページで、**検索**セクションで、をクリックして**検索設定**です。</span><span class="sxs-lookup"><span data-stu-id="05726-112">On the Home page, in the **Search** section, click **Search settings**.</span></span>  
  
4.  <span data-ttu-id="05726-113">検索設定の構成 ページの下の左ペインで、**クロール**をクリックして**既定のコンテンツへのアクセス アカウント**コンテンツをクロールするときに、既定のアカウントとして使用するアカウントを指定します。</span><span class="sxs-lookup"><span data-stu-id="05726-113">On the Configure Search Settings page, in the left pane under **Crawling**, click **Default content access account** to specify an account to use as the default account when crawling content.</span></span>  
  
5.  <span data-ttu-id="05726-114">[既定のコンテンツのアクセス アカウント] ページで、ユーザー名とパスワードの資格情報を指定し、クリックして**OK**です。</span><span class="sxs-lookup"><span data-stu-id="05726-114">On the Default Content Access Account page, specify the user name and password credentials, and click **OK**.</span></span> <span data-ttu-id="05726-115">検索の管理 ページに戻ります。</span><span class="sxs-lookup"><span data-stu-id="05726-115">You will return to the Search Administration page.</span></span>  
  
6.  <span data-ttu-id="05726-116">下の左ペインで**クロール**をクリックして**コンテンツ ソース**です。</span><span class="sxs-lookup"><span data-stu-id="05726-116">In the left pane under **Crawling**, click **Content Sources**.</span></span>  
  
7.  <span data-ttu-id="05726-117">コンテンツ ソースの管理 ページで、**新しいコンテンツ ソース**です。</span><span class="sxs-lookup"><span data-stu-id="05726-117">On the Manage Content Sources page, click **New Content Source**.</span></span>  
  
8.  <span data-ttu-id="05726-118">コンテンツ ソースの管理 ページで、**新しいコンテンツ ソース**です。</span><span class="sxs-lookup"><span data-stu-id="05726-118">On the Manage Content Sources page, click **New Content Source**.</span></span>  
  
9. <span data-ttu-id="05726-119">[コンテンツ ソースの追加] ページで。</span><span class="sxs-lookup"><span data-stu-id="05726-119">On the Add Content Source page:</span></span>  
  
    1.  <span data-ttu-id="05726-120">型`MS_SAMPLE_EMPLOYEE`で、**名前**ボックス。</span><span class="sxs-lookup"><span data-stu-id="05726-120">Type `MS_SAMPLE_EMPLOYEE` in the **Name** box.</span></span>  
  
    2.  <span data-ttu-id="05726-121">**コンテンツ ソースの種類**領域で、をクリックして**ビジネス データ**です。</span><span class="sxs-lookup"><span data-stu-id="05726-121">In the **Content Source Type** area, click **Business Data**.</span></span>  
  
    3.  <span data-ttu-id="05726-122">**アプリケーション**領域で、をクリックして**クロールには、アプリケーションが選択されている**、し、、 **MS_SAMPLE_EMPLOYEE_Instance**チェック ボックスをオンします。</span><span class="sxs-lookup"><span data-stu-id="05726-122">In the **Applications** area, click **Crawl selected applications**, and then select the **MS_SAMPLE_EMPLOYEE_Instance** check box.</span></span>  
  
    4.  <span data-ttu-id="05726-123">**フル クロールの開始**領域で、**このコンテンツ ソースのフル クロールを開始**チェック ボックスをクリックして**OK**です。</span><span class="sxs-lookup"><span data-stu-id="05726-123">In the **Start Full Crawl** area, select the **Start full crawl of this content source** check box, and then click **OK**.</span></span>  
  
         <span data-ttu-id="05726-124">![コンテンツ ソースの追加](../../adapters-and-accelerators/adapter-oracle-ebs/media/27-add-content-source.gif "27 _ add_content_source")</span><span class="sxs-lookup"><span data-stu-id="05726-124">![Add content source](../../adapters-and-accelerators/adapter-oracle-ebs/media/27-add-content-source.gif "27_Add_Content_Source")</span></span>  
  
10. <span data-ttu-id="05726-125">追加された新しいコンテンツ ソースのコンテンツ ソースの管理ページに戻るされます。</span><span class="sxs-lookup"><span data-stu-id="05726-125">You will return to the Manage Content Sources page with the new content source added.</span></span> <span data-ttu-id="05726-126">Oracle E-business Suite で MS_SAMPLE_EMPLOYEE インターフェイス テーブル内のデータをコンテンツ ソースがクロールされます。</span><span class="sxs-lookup"><span data-stu-id="05726-126">The content source will crawl through the data in the MS_SAMPLE_EMPLOYEE interface table in the Oracle E-Business Suite.</span></span> <span data-ttu-id="05726-127">クロールが完了するまで待機します。</span><span class="sxs-lookup"><span data-stu-id="05726-127">Wait until the crawling is completed.</span></span>  
  
11. <span data-ttu-id="05726-128">下の左ペインで**クロール**をクリックして**クロール ログ**、クロールが成功したことを確認するログ ファイルを確認してください。</span><span class="sxs-lookup"><span data-stu-id="05726-128">In the left pane under **Crawling**, click **Crawl Log**, and then verify the log file to ensure that the crawling is successful.</span></span>  
  
##  <a name="Scope"></a><span data-ttu-id="05726-129">クロールされたコンテンツのスコープを定義します。</span><span class="sxs-lookup"><span data-stu-id="05726-129">Define a Scope for the Crawled Content</span></span>  
  
1.  <span data-ttu-id="05726-130">SharePoint 3.0 サーバーの全体管理を開始します。</span><span class="sxs-lookup"><span data-stu-id="05726-130">Start SharePoint 3.0 Central Administration.</span></span> <span data-ttu-id="05726-131">をクリックして**開始**、 をポイント**すべてのプログラム**、 をポイント**Microsoft Office Server**、クリックして**SharePoint 3.0 サーバーの全体管理**.</span><span class="sxs-lookup"><span data-stu-id="05726-131">Click **Start**, point to **All Programs**, point to **Microsoft Office Server**, and then click **SharePoint 3.0 Central Administration**.</span></span>  
  
2.  <span data-ttu-id="05726-132">左側のナビゲーション ウィンドウで、名前の共有サービス プロバイダー (SSP) の検索アプリケーションを構成する場合をクリックします。</span><span class="sxs-lookup"><span data-stu-id="05726-132">In the left navigation pane, click the name of the Shared Service Provider (SSP) where you want to configure the search application.</span></span>  
  
3.  <span data-ttu-id="05726-133">[ホーム] ページで、**検索**セクションで、をクリックして**検索設定**です。</span><span class="sxs-lookup"><span data-stu-id="05726-133">On the Home page, in the **Search** section, click **Search settings**.</span></span>  
  
4.  <span data-ttu-id="05726-134">検索設定の構成 ページの下の左ペインで、**クエリを実行し、結果**をクリックして**スコープ**データのクロールのスコープを定義します。</span><span class="sxs-lookup"><span data-stu-id="05726-134">On the Configure Search Settings page, in the left pane under **Queries and Results**, click **Scopes** to define a scope for the crawling of data.</span></span>  
  
5.  <span data-ttu-id="05726-135">スコープの表示 ページで、をクリックして**新しいスコープ**です。</span><span class="sxs-lookup"><span data-stu-id="05726-135">On the View Scopes page, click **New Scope**.</span></span>  
  
6.  <span data-ttu-id="05726-136">[スコープの作成] ページで、次のように入力します。`MS_SAMPLE_EMPLOYEE_Search`で、**タイトル**ボックスと [] をクリック**OK**です。</span><span class="sxs-lookup"><span data-stu-id="05726-136">On the Create Scope page, type `MS_SAMPLE_EMPLOYEE_Search` in the **Title** box, and then click **OK**.</span></span>  
  
     <span data-ttu-id="05726-137">![スコープを作成する](../../adapters-and-accelerators/adapter-oracle-ebs/media/28-create-scope.gif "28 _ create_scope")</span><span class="sxs-lookup"><span data-stu-id="05726-137">![Create a scope](../../adapters-and-accelerators/adapter-oracle-ebs/media/28-create-scope.gif "28_Create_Scope")</span></span>  
  
7.  <span data-ttu-id="05726-138">追加された新しいスコープを持つ範囲の表示 ページに戻るされます。</span><span class="sxs-lookup"><span data-stu-id="05726-138">You will return to the View Scopes page with the new scope added.</span></span> <span data-ttu-id="05726-139">**更新ステータス**、新しく追加されたスコープの列をクリックして、**規則を追加**リンクします。</span><span class="sxs-lookup"><span data-stu-id="05726-139">In the **Update Status** column for the newly added scope, click the **Add rules** link.</span></span>  
  
8.  <span data-ttu-id="05726-140">スコープ規則の追加のページ。</span><span class="sxs-lookup"><span data-stu-id="05726-140">On the Add Scope Rule page:</span></span>  
  
    1.  <span data-ttu-id="05726-141">**スコープ規則の種類**領域で、をクリックして**コンテンツ ソース**です。</span><span class="sxs-lookup"><span data-stu-id="05726-141">In the **Scope Rule Type** area, click **Content Source**.</span></span>  
  
    2.  <span data-ttu-id="05726-142">**コンテンツ ソース**一覧で、をクリックして**MS_SAMPLE_EMPLOYEE**、順にクリック**OK**です。</span><span class="sxs-lookup"><span data-stu-id="05726-142">In the **Content Source** list, click **MS_SAMPLE_EMPLOYEE**, and then click **OK**.</span></span>  
  
         <span data-ttu-id="05726-143">![スコープ規則の追加](../../adapters-and-accelerators/adapter-oracle-ebs/media/29-add-scope-rule.gif "29 _ add_scope_rule")</span><span class="sxs-lookup"><span data-stu-id="05726-143">![Add a scope rule](../../adapters-and-accelerators/adapter-oracle-ebs/media/29-add-scope-rule.gif "29_Add_Scope_Rule")</span></span>  
  
9. <span data-ttu-id="05726-144">スコープに追加された規則とスコープの表示ページに戻るされます。</span><span class="sxs-lookup"><span data-stu-id="05726-144">You will return to the View Scopes page with the rule added for the scope.</span></span> <span data-ttu-id="05726-145">左側のウィンドウでをクリックして**検索管理**です。</span><span class="sxs-lookup"><span data-stu-id="05726-145">In the left pane, click **Search Administration**.</span></span>  
  
10. <span data-ttu-id="05726-146">[検索の管理] ページで、検索、**更新プログラムを必要とするスコープ**行ををクリックして、**更新プログラムを今すぐ開始**リンクします。</span><span class="sxs-lookup"><span data-stu-id="05726-146">On the Search Administration page, locate the **Scopes needing update** row, and click the **Start update now** link.</span></span>  
  
 <span data-ttu-id="05726-147">**スコープ更新ステータス**行範囲の更新の状態が表示されます。</span><span class="sxs-lookup"><span data-stu-id="05726-147">The **Scope update status** row will display the status of the scope update.</span></span> <span data-ttu-id="05726-148">更新が完了するまで待機します。</span><span class="sxs-lookup"><span data-stu-id="05726-148">Wait until the update is complete.</span></span> <span data-ttu-id="05726-149">更新が完了したら、スコープが使用できるようにします。</span><span class="sxs-lookup"><span data-stu-id="05726-149">After the updated is completed, the scope is ready to be used.</span></span>  
  
##  <a name="AddScope"></a><span data-ttu-id="05726-150">検索ドロップダウン リストに、スコープを追加します。</span><span class="sxs-lookup"><span data-stu-id="05726-150">Add the Scope to the Search Dropdown</span></span>  
 <span data-ttu-id="05726-151">検索範囲を作成した後に使用できるようにする、Microsoft Office SharePoint Server で、検索ドロップダウン リストに、スコープを追加する必要があります。</span><span class="sxs-lookup"><span data-stu-id="05726-151">After you have created the search scope, you must add the scope to the search dropdown in Microsoft Office SharePoint Server so that it can be used.</span></span>  
  
#### <a name="to-add-the-scope-to-the-search-dropdown"></a><span data-ttu-id="05726-152">検索ドロップダウン リストに、スコープを追加するには</span><span class="sxs-lookup"><span data-stu-id="05726-152">To add the scope to the search dropdown</span></span>  
  
1.  <span data-ttu-id="05726-153">SharePoint 3.0 サーバーの全体管理を開始します。</span><span class="sxs-lookup"><span data-stu-id="05726-153">Start SharePoint 3.0 Central Administration.</span></span> <span data-ttu-id="05726-154">をクリックして**開始**、 をポイント**すべてのプログラム**、 をポイント**Microsoft Office Server**、クリックして**SharePoint 3.0 サーバーの全体管理**.</span><span class="sxs-lookup"><span data-stu-id="05726-154">Click **Start**, point to **All Programs**, point to **Microsoft Office Server**, and then click **SharePoint 3.0 Central Administration**.</span></span>  
  
2.  <span data-ttu-id="05726-155">左側のナビゲーション ウィンドウで、名前の共有サービス プロバイダー (SSP) の検索アプリケーションを構成する場合をクリックします。</span><span class="sxs-lookup"><span data-stu-id="05726-155">In the left navigation pane, click the name of the Shared Service Provider (SSP) where you want to configure the search application.</span></span>  
  
3.  <span data-ttu-id="05726-156">共有サービスの管理 ページの右上隅で、をクリックして**サイトの操作**、クリックして**サイト設定**です。</span><span class="sxs-lookup"><span data-stu-id="05726-156">On the Shared Services Administration page, in the upper-right corner, click **Site Actions**, and then click **Site Settings**.</span></span>  
  
4.  <span data-ttu-id="05726-157">[サイト設定] ページで、**サイト コレクションの管理**セクションで、をクリックして**検索範囲**です。</span><span class="sxs-lookup"><span data-stu-id="05726-157">On the Site Settings page, in the **Site Collection Administration** section, click **Search scopes**.</span></span>  
  
5.  <span data-ttu-id="05726-158">スコープの表示 ページで、をクリックして、**検索ドロップダウン**リンクします。</span><span class="sxs-lookup"><span data-stu-id="05726-158">On the View Scopes page, click the **Search Dropdown** link.</span></span>  
  
     <span data-ttu-id="05726-159">![表示スコープ](../../adapters-and-accelerators/adapter-oracle-ebs/media/30-view-scope.gif "30_View_Scope")</span><span class="sxs-lookup"><span data-stu-id="05726-159">![View scopes](../../adapters-and-accelerators/adapter-oracle-ebs/media/30-view-scope.gif "30_View_Scope")</span></span>  
  
6.  <span data-ttu-id="05726-160">[スコープ表示グループの編集] ページで。</span><span class="sxs-lookup"><span data-stu-id="05726-160">On the Edit Scope Display Group page:</span></span>  
  
    1.  <span data-ttu-id="05726-161">**スコープ**領域で、選択、 **MS_SAMPLE_EMPLOYEE_Search**チェック ボックスをオンします。</span><span class="sxs-lookup"><span data-stu-id="05726-161">In the **Scopes** area, select the **MS_SAMPLE_EMPLOYEE_Search** check box.</span></span>  
  
    2.  <span data-ttu-id="05726-162">**既定のスコープ**領域で、をクリックして**MS_SAMPLE_EMPLOYEE_Search**で、**既定のスコープ**ボックスの一覧し、をクリックして **[ok]** です。</span><span class="sxs-lookup"><span data-stu-id="05726-162">In the **Default Scope** area, click **MS_SAMPLE_EMPLOYEE_Search** in the **Default Scope** list, and then click **OK**.</span></span>  
  
         <span data-ttu-id="05726-163">![スコープ表示グループの編集ページ](../../adapters-and-accelerators/adapter-oracle-ebs/media/31-edit-scope-display-group.gif "31 _ edit_scope_display_group")</span><span class="sxs-lookup"><span data-stu-id="05726-163">![Edit Scope Display Group page](../../adapters-and-accelerators/adapter-oracle-ebs/media/31-edit-scope-display-group.gif "31_Edit_Scope_Display_Group")</span></span>  
  
7.  <span data-ttu-id="05726-164">検索ドロップダウン表示グループに追加された MS_SAMPLE_EMPLOYEE_Search スコープを持つ範囲の表示 ページに戻るされます。</span><span class="sxs-lookup"><span data-stu-id="05726-164">You will return to the View Scopes page with the MS_SAMPLE_EMPLOYEE_Search scope added in the Search Dropdown display group.</span></span>  
  
##  <a name="SearchWebPart"></a><span data-ttu-id="05726-165">検索ボックス Web パーツを追加します。</span><span class="sxs-lookup"><span data-stu-id="05726-165">Add the Search Box Web Part</span></span>  
 <span data-ttu-id="05726-166">Oracle E-business Suite で MS_SAMPLE_EMPLOYEE インターフェイス テーブルでフルテキスト検索を実行するユーザーを有効にするには、ようになりました、Web パーツ ページを作成し、検索ボックス Web パーツを追加する必要があります。</span><span class="sxs-lookup"><span data-stu-id="05726-166">To enable the users to perform a full-text search on the MS_SAMPLE_EMPLOYEE interface table in Oracle E-Business Suite, you must now create a Web part page, and add a Search Box Web Part to it.</span></span>  
  
#### <a name="to-add-the-search-box-web-part"></a><span data-ttu-id="05726-167">検索ボックス Web パーツを追加するには</span><span class="sxs-lookup"><span data-stu-id="05726-167">To add the Search Box Web Part</span></span>  
  
1.  <span data-ttu-id="05726-168">呼ばれる Web パーツ ページを作成する**MS_SAMPLE_EMPLOYEE_Search**です。</span><span class="sxs-lookup"><span data-stu-id="05726-168">Create a Web Part page called **MS_SAMPLE_EMPLOYEE_Search**.</span></span> <span data-ttu-id="05726-169">Web パーツ ページを作成するための手順を確認する「[シナリオ 1: ビジネス データ一覧 web パーツを使用してデータを表示](../../adapters-and-accelerators/adapter-oracle-ebs/scenario-1-display-data-using-business-data-list-web-part.md)で[シナリオ 1: ビジネス データ一覧 web パーツを使用してデータを表示](../../adapters-and-accelerators/adapter-oracle-ebs/scenario-1-display-data-using-business-data-list-web-part.md)です。</span><span class="sxs-lookup"><span data-stu-id="05726-169">To know the steps for creating a Web Part page, see [Scenario 1: Display data using Business Data List web part](../../adapters-and-accelerators/adapter-oracle-ebs/scenario-1-display-data-using-business-data-list-web-part.md) in [Scenario 1: Display data using Business Data List web part](../../adapters-and-accelerators/adapter-oracle-ebs/scenario-1-display-data-using-business-data-list-web-part.md).</span></span>  
  
2.  <span data-ttu-id="05726-170">MS_SAMPLE_EMPLOYEE_Search ページで、をクリックして**Web パーツの追加**です。</span><span class="sxs-lookup"><span data-stu-id="05726-170">On the MS_SAMPLE_EMPLOYEE_Search page, click **Add a Web Part**.</span></span>  
  
3.  <span data-ttu-id="05726-171">**Web パーツの追加** ダイアログ ボックスで、**検索** セクションで、選択、**検索ボックス**チェック ボックスをクリックして**追加**です。</span><span class="sxs-lookup"><span data-stu-id="05726-171">In the **Add Web Parts** dialog box, in the **Search** section, select the **Search Box** check box, and then click **Add**.</span></span>  
  
     <span data-ttu-id="05726-172">![検索ボックス Web パーツの追加](../../adapters-and-accelerators/adapter-oracle-ebs/media/32-search-web-part.gif "32 _ search_web_part")</span><span class="sxs-lookup"><span data-stu-id="05726-172">![Add the Search Box Web Part](../../adapters-and-accelerators/adapter-oracle-ebs/media/32-search-web-part.gif "32_Search_Web_Part")</span></span>  
  
4.  <span data-ttu-id="05726-173">検索ボックス Web パーツが MS_SAMPLE_EMPLOYEE_Search ページに追加されます。</span><span class="sxs-lookup"><span data-stu-id="05726-173">The Search Box Web part is added to the MS_SAMPLE_EMPLOYEE_Search page.</span></span>  
  
     <span data-ttu-id="05726-174">![検索ボックス Web パーツ](../../adapters-and-accelerators/adapter-oracle-ebs/media/33-search-web-part-final.gif "33 _ search_web_part_final")</span><span class="sxs-lookup"><span data-stu-id="05726-174">![Search Box Web Part](../../adapters-and-accelerators/adapter-oracle-ebs/media/33-search-web-part-final.gif "33_Search_Web_Part_Final")</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="05726-175">参照</span><span class="sxs-lookup"><span data-stu-id="05726-175">See Also</span></span>  
 [<span data-ttu-id="05726-176">手順 3: Oracle E-business Suite からデータを取得する SharePoint アプリケーションを作成します。</span><span class="sxs-lookup"><span data-stu-id="05726-176">Step 3: Create a SharePoint application to retrieve data from Oracle E-Business Suite</span></span>](../../adapters-and-accelerators/adapter-oracle-ebs/step-3-create-a-sharepoint-application-to-retrieve-data-from-oracle-ebs.md)  
 [<span data-ttu-id="05726-177">シナリオ 1: ビジネス データ一覧 web パーツを使用してデータを表示します。</span><span class="sxs-lookup"><span data-stu-id="05726-177">Scenario 1: Display data using Business Data List web part</span></span>](../../adapters-and-accelerators/adapter-oracle-ebs/scenario-1-display-data-using-business-data-list-web-part.md)