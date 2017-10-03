---
title: "手順 4: SharePoint アプリケーションのテスト |Microsoft ドキュメント"
ms.custom: 
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: 
ms.suite: 
ms.tgt_pltfrm: 
ms.topic: article
ms.assetid: a859044e-a28e-477e-a20b-f9bb3c9f7405
caps.latest.revision: "7"
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: 427235d27e4e783111ccdb60f799c228737cd008
ms.sourcegitcommit: cb908c540d8f1a692d01dc8f313e16cb4b4e696d
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 09/20/2017
---
# <a name="step-4-test-your-sharepoint-application"></a><span data-ttu-id="cb963-102">手順 4: SharePoint アプリケーションをテストします。</span><span class="sxs-lookup"><span data-stu-id="cb963-102">Step 4: Test your SharePoint application</span></span>
<span data-ttu-id="cb963-103">![4 のステップ 4](../../adapters-and-accelerators/adapter-oracle-ebs/media/step-4of4.gif "Step_4of4")</span><span class="sxs-lookup"><span data-stu-id="cb963-103">![Step 4 of 4](../../adapters-and-accelerators/adapter-oracle-ebs/media/step-4of4.gif "Step_4of4")</span></span>  
  
 <span data-ttu-id="cb963-104">**所要時間:** 10 分</span><span class="sxs-lookup"><span data-stu-id="cb963-104">**Time to complete:** 10 minutes</span></span>  
  
 <span data-ttu-id="cb963-105">**目標:** SharePoint サイトに Web パーツを追加するいるし、アプリケーションを作成する必要がありますアプリケーションをテストする Oracle E-business Suite から一部のデータを取得しています。</span><span class="sxs-lookup"><span data-stu-id="cb963-105">**Objective:** After you have added Web Parts in the SharePoint site and created an application, you must test the application by retrieving some data from the Oracle E-Business Suite.</span></span> <span data-ttu-id="cb963-106">このトピックでは、アプリケーションを使用して、Oracle E-business Suite からデータを取得する方法について説明します。</span><span class="sxs-lookup"><span data-stu-id="cb963-106">This topic provides instructions on how to use the application to retrieve the data from the Oracle E-Business Suite.</span></span>  
  
## <a name="prerequisites"></a><span data-ttu-id="cb963-107">前提条件</span><span class="sxs-lookup"><span data-stu-id="cb963-107">Prerequisites</span></span>  
 <span data-ttu-id="cb963-108">ビジネス データを取得する適切な Web パーツが含まれる Web パーツ ページを作成する必要があります。</span><span class="sxs-lookup"><span data-stu-id="cb963-108">You should have created the Web Part page that contains the appropriate Web Parts to retrieve business data.</span></span> <span data-ttu-id="cb963-109">参照してください[手順 3: Oracle E-business Suite からデータを取得する SharePoint アプリケーションを作成](../../adapters-and-accelerators/adapter-oracle-ebs/step-3-create-a-sharepoint-application-to-retrieve-data-from-oracle-ebs.md)です。</span><span class="sxs-lookup"><span data-stu-id="cb963-109">See [Step 3: Create a SharePoint application to retrieve data from Oracle E-Business Suite](../../adapters-and-accelerators/adapter-oracle-ebs/step-3-create-a-sharepoint-application-to-retrieve-data-from-oracle-ebs.md).</span></span>  
  
### <a name="scenario-1-to-test-the-sharepoint-application-created-using-business-data-list-web-part"></a><span data-ttu-id="cb963-110">シナリオ 1: この SharePoint アプリケーションをテストするには、ビジネス データ一覧 Web パーツを使用して作成されました。</span><span class="sxs-lookup"><span data-stu-id="cb963-110">Scenario 1: To test the SharePoint application created using Business Data List Web Part</span></span>  
  
1.  <span data-ttu-id="cb963-111">SharePoint 3.0 サーバーの全体管理を開始します。</span><span class="sxs-lookup"><span data-stu-id="cb963-111">Start SharePoint 3.0 Central Administration.</span></span> <span data-ttu-id="cb963-112">をクリックして**開始**、 をポイント**すべてのプログラム**、 をポイント**Microsoft Office Server**、クリックして**SharePoint 3.0 サーバーの全体管理**.</span><span class="sxs-lookup"><span data-stu-id="cb963-112">Click **Start**, point to **All Programs**, point to **Microsoft Office Server**, and then click **SharePoint 3.0 Central Administration**.</span></span>  
  
2.  <span data-ttu-id="cb963-113">左側のナビゲーション ウィンドウで、アプリケーションを作成する、SSP の名前をクリックします。</span><span class="sxs-lookup"><span data-stu-id="cb963-113">In the left navigation pane, click the name of the SSP under which you created the application.</span></span>  
  
3.  <span data-ttu-id="cb963-114">左側のウィンドウでをクリックして**すべてのサイト コンテンツの表示**です。</span><span class="sxs-lookup"><span data-stu-id="cb963-114">In the left pane, click **View All Site Content**.</span></span> <span data-ttu-id="cb963-115">右側のウィンドウでをクリックして**フォーム テンプレート**です。</span><span class="sxs-lookup"><span data-stu-id="cb963-115">In the right pane, click **Form Templates**.</span></span>  
  
4.  <span data-ttu-id="cb963-116">**フォーム カテゴリ**一覧で、クリックして**MS_SAMPLE_EMPLOYEE**です。</span><span class="sxs-lookup"><span data-stu-id="cb963-116">In the **Form Category** list, click **MS_SAMPLE_EMPLOYEE**.</span></span> <span data-ttu-id="cb963-117">Web パーツ ページを作成したときに、この名前を指定した[シナリオ 1: ビジネス データ一覧 web パーツを使用してデータを表示](../../adapters-and-accelerators/adapter-oracle-ebs/scenario-1-display-data-using-business-data-list-web-part.md)です。</span><span class="sxs-lookup"><span data-stu-id="cb963-117">You specified this name when you created the Web Part page in [Scenario 1: Display data using Business Data List web part](../../adapters-and-accelerators/adapter-oracle-ebs/scenario-1-display-data-using-business-data-list-web-part.md).</span></span>  
  
5.  <span data-ttu-id="cb963-118">検索文字列に基づく従業員を検索します。</span><span class="sxs-lookup"><span data-stu-id="cb963-118">Search for employees based on a search string.</span></span> <span data-ttu-id="cb963-119">たとえば、すべての従業員を検索する次のように入力します。  **%**  、テキスト ボックスに**データの取得**です。</span><span class="sxs-lookup"><span data-stu-id="cb963-119">For example, to search for all the employees, type **%** in the text box, and click **Retrieve Data**.</span></span> <span data-ttu-id="cb963-120">次の図は、Oracle E-business Suite から取得したレコードを示しています。</span><span class="sxs-lookup"><span data-stu-id="cb963-120">The following figure shows the records retrieved from Oracle E-Business Suite:</span></span>  
  
     <span data-ttu-id="cb963-121">![検索結果](../../adapters-and-accelerators/adapter-oracle-ebs/media/bdc-result.gif "BDC_Result")</span><span class="sxs-lookup"><span data-stu-id="cb963-121">![Search result](../../adapters-and-accelerators/adapter-oracle-ebs/media/bdc-result.gif "BDC_Result")</span></span>  
  
6.  <span data-ttu-id="cb963-122">名または姓を入力して特定の従業員を検索することもできます。</span><span class="sxs-lookup"><span data-stu-id="cb963-122">You can also search for a specific employee by entering their first name or last name:</span></span>  
  
    -   <span data-ttu-id="cb963-123">最初の名前を使用してを検索するには、初期の文字を入力、従業員名に続けて、  **%** 検索条件に一致するすべての従業員のレコードを返す記号。</span><span class="sxs-lookup"><span data-stu-id="cb963-123">To search using the first name, type the initial letters of an employee name followed by the **%** symbol to return records of all the employees matching the search criteria.</span></span>  
  
    -   <span data-ttu-id="cb963-124">使用して、姓と名を検索するには、次のように入力します。  **%** 従業員の姓を続けています。</span><span class="sxs-lookup"><span data-stu-id="cb963-124">To search using the last name, type **%** followed by employee’s last name.</span></span>  
  
    > [!NOTE]
    >  <span data-ttu-id="cb963-125">検索文字列では大文字小文字を区別します。</span><span class="sxs-lookup"><span data-stu-id="cb963-125">The search string is case sensitive.</span></span>  
  
     <span data-ttu-id="cb963-126">![従業員の名で検索](../../adapters-and-accelerators/adapter-oracle-ebs/media/b5044c4d-31ec-46d8-b02c-3b26bfe8178e.gif "b5044c4d-31ec-46d8-b02c-3b26bfe8178e")</span><span class="sxs-lookup"><span data-stu-id="cb963-126">![Searching by first name of an employee](../../adapters-and-accelerators/adapter-oracle-ebs/media/b5044c4d-31ec-46d8-b02c-3b26bfe8178e.gif "b5044c4d-31ec-46d8-b02c-3b26bfe8178e")</span></span>  
  
### <a name="scenario-2-to-test-the-sharepoint-application-created-to-perform-a-full-text-search"></a><span data-ttu-id="cb963-127">シナリオ 2: SharePoint アプリケーションのテストを作成するフルテキスト検索を実行</span><span class="sxs-lookup"><span data-stu-id="cb963-127">Scenario 2: To test the SharePoint application created to perform a full-text search</span></span>  
  
1.  <span data-ttu-id="cb963-128">SharePoint 3.0 サーバーの全体管理を開始します。</span><span class="sxs-lookup"><span data-stu-id="cb963-128">Start SharePoint 3.0 Central Administration.</span></span> <span data-ttu-id="cb963-129">をクリックして**開始**、 をポイント**すべてのプログラム**、 をポイント**Microsoft Office Server**、クリックして**SharePoint 3.0 サーバーの全体管理**.</span><span class="sxs-lookup"><span data-stu-id="cb963-129">Click **Start**, point to **All Programs**, point to **Microsoft Office Server**, and then click **SharePoint 3.0 Central Administration**.</span></span>  
  
2.  <span data-ttu-id="cb963-130">左側のナビゲーション ウィンドウで、アプリケーションを作成する、SSP の名前をクリックします。</span><span class="sxs-lookup"><span data-stu-id="cb963-130">In the left navigation pane, click the name of the SSP under which you created the application.</span></span>  
  
3.  <span data-ttu-id="cb963-131">左側のウィンドウでをクリックして**すべてのサイト コンテンツの表示**です。</span><span class="sxs-lookup"><span data-stu-id="cb963-131">In the left pane, click **View All Site Content**.</span></span> <span data-ttu-id="cb963-132">右側のウィンドウでをクリックして**フォーム テンプレート**です。</span><span class="sxs-lookup"><span data-stu-id="cb963-132">In the right pane, click **Form Templates**.</span></span>  
  
4.  <span data-ttu-id="cb963-133">**フォーム カテゴリ**一覧で、クリックして**MS_SAMPLE_EMPLOYEE_Search**です。</span><span class="sxs-lookup"><span data-stu-id="cb963-133">In the **Form Category** list, click **MS_SAMPLE_EMPLOYEE_Search**.</span></span> <span data-ttu-id="cb963-134">Web パーツ ページを作成したときに、この名前を指定した[シナリオ 2: 検索ボックス Web パーツを使用して検索を実行](../../adapters-and-accelerators/adapter-oracle-ebs/scenario-2-search-using-the-search-box-web-part.md)で[シナリオ 2: 検索ボックス Web パーツを使用して検索を実行](../../adapters-and-accelerators/adapter-oracle-ebs/scenario-2-search-using-the-search-box-web-part.md)です。</span><span class="sxs-lookup"><span data-stu-id="cb963-134">You specified this name when you created the Web Part page in [Scenario 2: Perform a Search Using the Search Box Web Part](../../adapters-and-accelerators/adapter-oracle-ebs/scenario-2-search-using-the-search-box-web-part.md) in [Scenario 2: Perform a Search Using the Search Box Web Part](../../adapters-and-accelerators/adapter-oracle-ebs/scenario-2-search-using-the-search-box-web-part.md).</span></span>  
  
5.  <span data-ttu-id="cb963-135">MS_SAMPLE_EMPLOYEE_Search ページには、MS_SAMPLE EMPLOYEE テーブルのフルテキスト検索を実行することができます、検索ボックスが表示されます。</span><span class="sxs-lookup"><span data-stu-id="cb963-135">The MS_SAMPLE_EMPLOYEE_Search page displays the search box where you can perform a full-text search on the MS_SAMPLE EMPLOYEE table.</span></span> <span data-ttu-id="cb963-136">たとえば、ニューヨークに住んでいるすべての従業員を検索する場合は、「`New York`で検索ボックス、および ENTER キーを押します。</span><span class="sxs-lookup"><span data-stu-id="cb963-136">For example, if you want to search for all the employees who live in New York, type `New York` in the search box, and press ENTER.</span></span>  
  
     <span data-ttu-id="cb963-137">![検索パラメーターの指定](../../adapters-and-accelerators/adapter-oracle-ebs/media/34-search-result.gif "34 _ search_result")</span><span class="sxs-lookup"><span data-stu-id="cb963-137">![Specify a search parameter](../../adapters-and-accelerators/adapter-oracle-ebs/media/34-search-result.gif "34_Search_Result")</span></span>  
  
6.  <span data-ttu-id="cb963-138">検索結果ページが表示されます。</span><span class="sxs-lookup"><span data-stu-id="cb963-138">A page appears with the search results.</span></span> <span data-ttu-id="cb963-139">各一致するレコードは、検索結果 ページでリンクとして表示されます。</span><span class="sxs-lookup"><span data-stu-id="cb963-139">Each matching records is displayed as a link in the search results page.</span></span>  
  
     <span data-ttu-id="cb963-140">![検索結果](../../adapters-and-accelerators/adapter-oracle-ebs/media/05cc6fdc-8c9f-4312-8579-ef1753d02c63.gif "05cc6fdc-8c9f-4312-8579-ef1753d02c63")</span><span class="sxs-lookup"><span data-stu-id="cb963-140">![Search results](../../adapters-and-accelerators/adapter-oracle-ebs/media/05cc6fdc-8c9f-4312-8579-ef1753d02c63.gif "05cc6fdc-8c9f-4312-8579-ef1753d02c63")</span></span>  
  
7.  <span data-ttu-id="cb963-141">対応する従業員レコードを表示する検索結果内のリンクをクリックします。</span><span class="sxs-lookup"><span data-stu-id="cb963-141">Click a link in the search result to view the respective employee record.</span></span>  
  
     <span data-ttu-id="cb963-142">![詳細な従業員レコード](../../adapters-and-accelerators/adapter-oracle-ebs/media/36-search-result2.gif "36 _ search_result2")</span><span class="sxs-lookup"><span data-stu-id="cb963-142">![Detailed employee record](../../adapters-and-accelerators/adapter-oracle-ebs/media/36-search-result2.gif "36_Search_Result2")</span></span>  
  
## <a name="summary"></a><span data-ttu-id="cb963-143">概要</span><span class="sxs-lookup"><span data-stu-id="cb963-143">Summary</span></span>  
 <span data-ttu-id="cb963-144">このチュートリアルでは、SharePoint ポータルからアクセスする Oracle E-business Suite の成果物のための WCF サービスを作成します。</span><span class="sxs-lookup"><span data-stu-id="cb963-144">In this tutorial, you created a WCF service for the Oracle E-Business Suite artifacts you want to access from a SharePoint Portal.</span></span> <span data-ttu-id="cb963-145">Oracle E-business Suite 成果物のための存在し、Oracle E-business Suite でデータを検索する Web パーツを作成する SharePoint ポータルにインポートされているアプリケーション定義を作成します。</span><span class="sxs-lookup"><span data-stu-id="cb963-145">You also created an application definition for the Oracle E-Business Suite artifacts that is imported into a SharePoint portal to create Web Parts to present and search data in Oracle E-Business Suite.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="cb963-146">参照</span><span class="sxs-lookup"><span data-stu-id="cb963-146">See Also</span></span>  
 [<span data-ttu-id="cb963-147">チュートリアル: SharePoint サイト上の Oracle E-business Suite からデータを表示します。</span><span class="sxs-lookup"><span data-stu-id="cb963-147">Tutorial: Present data from Oracle E-Business Suite on a SharePoint Site</span></span>](../../adapters-and-accelerators/adapter-oracle-ebs/tutorial-present-data-from-oracle-e-business-suite-on-a-sharepoint-site.md)