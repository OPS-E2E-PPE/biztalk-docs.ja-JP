---
title: 手順 4:SharePoint アプリケーションのテスト |Microsoft Docs
ms.custom: ''
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: ''
ms.suite: ''
ms.tgt_pltfrm: ''
ms.topic: article
ms.assetid: a859044e-a28e-477e-a20b-f9bb3c9f7405
caps.latest.revision: 7
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: 1ac732b009f25628651fae133e83acd7fcd5deb2
ms.sourcegitcommit: 381e83d43796a345488d54b3f7413e11d56ad7be
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 05/07/2019
ms.locfileid: "65374546"
---
# <a name="step-4-test-your-sharepoint-application"></a><span data-ttu-id="81299-102">手順 4:SharePoint アプリケーションをテストします。</span><span class="sxs-lookup"><span data-stu-id="81299-102">Step 4: Test your SharePoint application</span></span>
<span data-ttu-id="81299-103">![手順 4 の 4](../../adapters-and-accelerators/adapter-oracle-ebs/media/step-4of4.gif "Step_4of4")</span><span class="sxs-lookup"><span data-stu-id="81299-103">![Step 4 of 4](../../adapters-and-accelerators/adapter-oracle-ebs/media/step-4of4.gif "Step_4of4")</span></span>  
  
 <span data-ttu-id="81299-104">**所要時間:** 10 分</span><span class="sxs-lookup"><span data-stu-id="81299-104">**Time to complete:** 10 minutes</span></span>  
  
 <span data-ttu-id="81299-105">**目標:** SharePoint サイトで Web パーツを追加し、アプリケーションを作成した後は、Oracle E-business Suite から一部のデータを取得することによってアプリケーションをテストする必要があります。</span><span class="sxs-lookup"><span data-stu-id="81299-105">**Objective:** After you have added Web Parts in the SharePoint site and created an application, you must test the application by retrieving some data from the Oracle E-Business Suite.</span></span> <span data-ttu-id="81299-106">このトピックでは、アプリケーションを使用して、Oracle E-business Suite からデータを取得する方法を説明します。</span><span class="sxs-lookup"><span data-stu-id="81299-106">This topic provides instructions on how to use the application to retrieve the data from the Oracle E-Business Suite.</span></span>  
  
## <a name="prerequisites"></a><span data-ttu-id="81299-107">前提条件</span><span class="sxs-lookup"><span data-stu-id="81299-107">Prerequisites</span></span>  
 <span data-ttu-id="81299-108">ビジネス データを取得する適切な Web パーツが含まれる Web パーツ ページを作成する必要があります。</span><span class="sxs-lookup"><span data-stu-id="81299-108">You should have created the Web Part page that contains the appropriate Web Parts to retrieve business data.</span></span> <span data-ttu-id="81299-109">参照してください[手順 3。Oracle E-business Suite からデータを取得する SharePoint アプリケーションを作成](../../adapters-and-accelerators/adapter-oracle-ebs/step-3-create-a-sharepoint-application-to-retrieve-data-from-oracle-ebs.md)です。</span><span class="sxs-lookup"><span data-stu-id="81299-109">See [Step 3: Create a SharePoint application to retrieve data from Oracle E-Business Suite](../../adapters-and-accelerators/adapter-oracle-ebs/step-3-create-a-sharepoint-application-to-retrieve-data-from-oracle-ebs.md).</span></span>  
  
### <a name="scenario-1-to-test-the-sharepoint-application-created-using-business-data-list-web-part"></a><span data-ttu-id="81299-110">シナリオ 1:ビジネス データ一覧 Web パーツを使用して作成した SharePoint アプリケーションをテストするには</span><span class="sxs-lookup"><span data-stu-id="81299-110">Scenario 1: To test the SharePoint application created using Business Data List Web Part</span></span>  
  
1.  <span data-ttu-id="81299-111">SharePoint 3.0 サーバーの全体管理を開始します。</span><span class="sxs-lookup"><span data-stu-id="81299-111">Start SharePoint 3.0 Central Administration.</span></span> <span data-ttu-id="81299-112">クリックして**開始**、 をポイント**すべてのプログラム**、 をポイント**Microsoft Office Server**、順にクリックします**SharePoint 3.0 サーバーの全体管理**.</span><span class="sxs-lookup"><span data-stu-id="81299-112">Click **Start**, point to **All Programs**, point to **Microsoft Office Server**, and then click **SharePoint 3.0 Central Administration**.</span></span>  
  
2.  <span data-ttu-id="81299-113">左側のナビゲーション ウィンドウで、アプリケーションを作成する SSP の名前をクリックします。</span><span class="sxs-lookup"><span data-stu-id="81299-113">In the left navigation pane, click the name of the SSP under which you created the application.</span></span>  
  
3.  <span data-ttu-id="81299-114">左側のウィンドウで次のようにクリックします。**すべてのサイト コンテンツの表示**します。</span><span class="sxs-lookup"><span data-stu-id="81299-114">In the left pane, click **View All Site Content**.</span></span> <span data-ttu-id="81299-115">右側のウィンドウで次のようにクリックします。**フォーム テンプレート**します。</span><span class="sxs-lookup"><span data-stu-id="81299-115">In the right pane, click **Form Templates**.</span></span>  
  
4.  <span data-ttu-id="81299-116">**フォーム カテゴリ**一覧で、 **MS_SAMPLE_EMPLOYEE**します。</span><span class="sxs-lookup"><span data-stu-id="81299-116">In the **Form Category** list, click **MS_SAMPLE_EMPLOYEE**.</span></span> <span data-ttu-id="81299-117">Web パーツ ページを作成するときに、この名前を指定した[シナリオ 1。ビジネス データ一覧 web パーツを使用してデータを表示](../../adapters-and-accelerators/adapter-oracle-ebs/scenario-1-display-data-using-business-data-list-web-part.md)します。</span><span class="sxs-lookup"><span data-stu-id="81299-117">You specified this name when you created the Web Part page in [Scenario 1: Display data using Business Data List web part](../../adapters-and-accelerators/adapter-oracle-ebs/scenario-1-display-data-using-business-data-list-web-part.md).</span></span>  
  
5.  <span data-ttu-id="81299-118">検索文字列に基づいて従業員を検索します。</span><span class="sxs-lookup"><span data-stu-id="81299-118">Search for employees based on a search string.</span></span> <span data-ttu-id="81299-119">たとえば、すべての従業員を検索するに次のように入力します。 **%** テキスト ボックスに、をクリックします**データの取得**します。</span><span class="sxs-lookup"><span data-stu-id="81299-119">For example, to search for all the employees, type **%** in the text box, and click **Retrieve Data**.</span></span> <span data-ttu-id="81299-120">次の図は、Oracle E-business Suite から取得したレコードを示しています。</span><span class="sxs-lookup"><span data-stu-id="81299-120">The following figure shows the records retrieved from Oracle E-Business Suite:</span></span>  
  
     <span data-ttu-id="81299-121">![検索結果](../../adapters-and-accelerators/adapter-oracle-ebs/media/bdc-result.gif "BDC_Result")</span><span class="sxs-lookup"><span data-stu-id="81299-121">![Search result](../../adapters-and-accelerators/adapter-oracle-ebs/media/bdc-result.gif "BDC_Result")</span></span>  
  
6.  <span data-ttu-id="81299-122">名または姓を入力して特定の従業員を検索することもできます。</span><span class="sxs-lookup"><span data-stu-id="81299-122">You can also search for a specific employee by entering their first name or last name:</span></span>  
  
    -   <span data-ttu-id="81299-123">最初の名前を使用して検索するには、従業員名の後の最初の文字を入力、 **%** シンボルの検索条件に一致するすべての従業員レコードを返します。</span><span class="sxs-lookup"><span data-stu-id="81299-123">To search using the first name, type the initial letters of an employee name followed by the **%** symbol to return records of all the employees matching the search criteria.</span></span>  
  
    -   <span data-ttu-id="81299-124">最後の名前を使用して検索するには、入力**%** 従業員の姓を続けています。</span><span class="sxs-lookup"><span data-stu-id="81299-124">To search using the last name, type **%** followed by employee’s last name.</span></span>  
  
    > [!NOTE]
    >  <span data-ttu-id="81299-125">検索文字列が大文字小文字を区別します。</span><span class="sxs-lookup"><span data-stu-id="81299-125">The search string is case sensitive.</span></span>  
  
     <span data-ttu-id="81299-126">![従業員の名で検索](../../adapters-and-accelerators/adapter-oracle-ebs/media/b5044c4d-31ec-46d8-b02c-3b26bfe8178e.gif "b5044c4d-31ec-46d8-b02c-3b26bfe8178e")</span><span class="sxs-lookup"><span data-stu-id="81299-126">![Searching by first name of an employee](../../adapters-and-accelerators/adapter-oracle-ebs/media/b5044c4d-31ec-46d8-b02c-3b26bfe8178e.gif "b5044c4d-31ec-46d8-b02c-3b26bfe8178e")</span></span>  
  
### <a name="scenario-2-to-test-the-sharepoint-application-created-to-perform-a-full-text-search"></a><span data-ttu-id="81299-127">シナリオ 2: フルテキスト検索を実行するために作成する SharePoint アプリケーションをテストするには</span><span class="sxs-lookup"><span data-stu-id="81299-127">Scenario 2: To test the SharePoint application created to perform a full-text search</span></span>  
  
1.  <span data-ttu-id="81299-128">SharePoint 3.0 サーバーの全体管理を開始します。</span><span class="sxs-lookup"><span data-stu-id="81299-128">Start SharePoint 3.0 Central Administration.</span></span> <span data-ttu-id="81299-129">クリックして**開始**、 をポイント**すべてのプログラム**、 をポイント**Microsoft Office Server**、順にクリックします**SharePoint 3.0 サーバーの全体管理**.</span><span class="sxs-lookup"><span data-stu-id="81299-129">Click **Start**, point to **All Programs**, point to **Microsoft Office Server**, and then click **SharePoint 3.0 Central Administration**.</span></span>  
  
2.  <span data-ttu-id="81299-130">左側のナビゲーション ウィンドウで、アプリケーションを作成する SSP の名前をクリックします。</span><span class="sxs-lookup"><span data-stu-id="81299-130">In the left navigation pane, click the name of the SSP under which you created the application.</span></span>  
  
3.  <span data-ttu-id="81299-131">左側のウィンドウで次のようにクリックします。**すべてのサイト コンテンツの表示**します。</span><span class="sxs-lookup"><span data-stu-id="81299-131">In the left pane, click **View All Site Content**.</span></span> <span data-ttu-id="81299-132">右側のウィンドウで次のようにクリックします。**フォーム テンプレート**します。</span><span class="sxs-lookup"><span data-stu-id="81299-132">In the right pane, click **Form Templates**.</span></span>  
  
4.  <span data-ttu-id="81299-133">**フォーム カテゴリ**一覧で、 **MS_SAMPLE_EMPLOYEE_Search**します。</span><span class="sxs-lookup"><span data-stu-id="81299-133">In the **Form Category** list, click **MS_SAMPLE_EMPLOYEE_Search**.</span></span> <span data-ttu-id="81299-134">Web パーツ ページを作成するときに、この名前を指定した[シナリオ 2。検索ボックス Web パーツを使用して検索を実行](../../adapters-and-accelerators/adapter-oracle-ebs/scenario-2-search-using-the-search-box-web-part.md)で[シナリオ 2。検索ボックス Web パーツを使用して検索を実行](../../adapters-and-accelerators/adapter-oracle-ebs/scenario-2-search-using-the-search-box-web-part.md)します。</span><span class="sxs-lookup"><span data-stu-id="81299-134">You specified this name when you created the Web Part page in [Scenario 2: Perform a Search Using the Search Box Web Part](../../adapters-and-accelerators/adapter-oracle-ebs/scenario-2-search-using-the-search-box-web-part.md) in [Scenario 2: Perform a Search Using the Search Box Web Part](../../adapters-and-accelerators/adapter-oracle-ebs/scenario-2-search-using-the-search-box-web-part.md).</span></span>  
  
5.  <span data-ttu-id="81299-135">MS_SAMPLE_EMPLOYEE_Search ページには、MS_SAMPLE EMPLOYEE テーブルのフルテキスト検索を実行することができます、検索ボックスが表示されます。</span><span class="sxs-lookup"><span data-stu-id="81299-135">The MS_SAMPLE_EMPLOYEE_Search page displays the search box where you can perform a full-text search on the MS_SAMPLE EMPLOYEE table.</span></span> <span data-ttu-id="81299-136">たとえば、ニューヨークに居住するすべての従業員を検索する場合は、「`New York`で検索ボックスに、ENTER キーを押します。</span><span class="sxs-lookup"><span data-stu-id="81299-136">For example, if you want to search for all the employees who live in New York, type `New York` in the search box, and press ENTER.</span></span>  
  
     <span data-ttu-id="81299-137">![検索パラメーターを指定](../../adapters-and-accelerators/adapter-oracle-ebs/media/34-search-result.gif "34 _ search_result")</span><span class="sxs-lookup"><span data-stu-id="81299-137">![Specify a search parameter](../../adapters-and-accelerators/adapter-oracle-ebs/media/34-search-result.gif "34_Search_Result")</span></span>  
  
6.  <span data-ttu-id="81299-138">検索結果ページが表示されます。</span><span class="sxs-lookup"><span data-stu-id="81299-138">A page appears with the search results.</span></span> <span data-ttu-id="81299-139">各一致するレコードが検索結果ページにリンクとして表示されます。</span><span class="sxs-lookup"><span data-stu-id="81299-139">Each matching records is displayed as a link in the search results page.</span></span>  
  
     <span data-ttu-id="81299-140">![検索結果](../../adapters-and-accelerators/adapter-oracle-ebs/media/05cc6fdc-8c9f-4312-8579-ef1753d02c63.gif "05cc6fdc-8c9f-4312-8579-ef1753d02c63")</span><span class="sxs-lookup"><span data-stu-id="81299-140">![Search results](../../adapters-and-accelerators/adapter-oracle-ebs/media/05cc6fdc-8c9f-4312-8579-ef1753d02c63.gif "05cc6fdc-8c9f-4312-8579-ef1753d02c63")</span></span>  
  
7.  <span data-ttu-id="81299-141">対応する従業員レコードを表示する検索結果内のリンクをクリックします。</span><span class="sxs-lookup"><span data-stu-id="81299-141">Click a link in the search result to view the respective employee record.</span></span>  
  
     <span data-ttu-id="81299-142">![従業員レコードの詳細な](../../adapters-and-accelerators/adapter-oracle-ebs/media/36-search-result2.gif "36 _ search_result2")</span><span class="sxs-lookup"><span data-stu-id="81299-142">![Detailed employee record](../../adapters-and-accelerators/adapter-oracle-ebs/media/36-search-result2.gif "36_Search_Result2")</span></span>  
  
## <a name="summary"></a><span data-ttu-id="81299-143">まとめ</span><span class="sxs-lookup"><span data-stu-id="81299-143">Summary</span></span>  
 <span data-ttu-id="81299-144">このチュートリアルでは、SharePoint ポータルからアクセスする Oracle E-business Suite の成果物の WCF サービスを作成します。</span><span class="sxs-lookup"><span data-stu-id="81299-144">In this tutorial, you created a WCF service for the Oracle E-Business Suite artifacts you want to access from a SharePoint Portal.</span></span> <span data-ttu-id="81299-145">Oracle E-business Suite の成果物の存在し、Oracle E-business Suite でデータを検索する Web パーツを作成する SharePoint ポータルにインポートされているアプリケーション定義を作成します。</span><span class="sxs-lookup"><span data-stu-id="81299-145">You also created an application definition for the Oracle E-Business Suite artifacts that is imported into a SharePoint portal to create Web Parts to present and search data in Oracle E-Business Suite.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="81299-146">参照</span><span class="sxs-lookup"><span data-stu-id="81299-146">See Also</span></span>  
 [<span data-ttu-id="81299-147">チュートリアル: SharePoint サイト上の Oracle E-business Suite からデータを表示します。</span><span class="sxs-lookup"><span data-stu-id="81299-147">Tutorial: Present data from Oracle E-Business Suite on a SharePoint Site</span></span>](../../adapters-and-accelerators/adapter-oracle-ebs/tutorial-present-data-from-oracle-e-business-suite-on-a-sharepoint-site.md)