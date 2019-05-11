---
title: 手順 4:テスト、SharePoint アプリケーション 1 |Microsoft Docs
ms.custom: ''
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: ''
ms.suite: ''
ms.tgt_pltfrm: ''
ms.topic: article
ms.assetid: f7ded5a5-88d5-40aa-814b-70bc0a7dcfa3
caps.latest.revision: 7
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: 40160ef6e2e3a27a10a74779aa7eb8d282b2a30b
ms.sourcegitcommit: 381e83d43796a345488d54b3f7413e11d56ad7be
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 05/07/2019
ms.locfileid: "65372792"
---
# <a name="step-4-test-your-sharepoint-application"></a><span data-ttu-id="80cfd-102">手順 4:SharePoint アプリケーションをテストします。</span><span class="sxs-lookup"><span data-stu-id="80cfd-102">Step 4: Test Your SharePoint Application</span></span>
<span data-ttu-id="80cfd-103">![手順 4 の 4](../../adapters-and-accelerators/adapter-oracle-ebs/media/step-4of4.gif "Step_4of4")</span><span class="sxs-lookup"><span data-stu-id="80cfd-103">![Step 4 of 4](../../adapters-and-accelerators/adapter-oracle-ebs/media/step-4of4.gif "Step_4of4")</span></span>  
  
 <span data-ttu-id="80cfd-104">**所要時間:** 10 分</span><span class="sxs-lookup"><span data-stu-id="80cfd-104">**Time to complete:** 10 minutes</span></span>  
  
 <span data-ttu-id="80cfd-105">**目標:** SharePoint サイトで Web パーツを追加し、アプリケーションを作成した後は、SAP システムから一部のデータを取得することによってアプリケーションをテストする必要があります。</span><span class="sxs-lookup"><span data-stu-id="80cfd-105">**Objective:** After you have added Web Parts in the SharePoint site and created an application, you must test the application by retrieving some data from the SAP system.</span></span> <span data-ttu-id="80cfd-106">このトピックでは、アプリケーションを使用して、SAP システムからデータを取得する方法を説明します。</span><span class="sxs-lookup"><span data-stu-id="80cfd-106">This topic provides instructions on how to use the application to retrieve the data from the SAP system.</span></span>  
  
## <a name="prerequisites"></a><span data-ttu-id="80cfd-107">前提条件</span><span class="sxs-lookup"><span data-stu-id="80cfd-107">Prerequisites</span></span>  
  
-   <span data-ttu-id="80cfd-108">ビジネス データを取得する適切な Web パーツが含まれる Web パーツ ページを作成する必要があります。</span><span class="sxs-lookup"><span data-stu-id="80cfd-108">You should have created the Web Part page that contains the appropriate Web Parts to retrieve business data.</span></span> <span data-ttu-id="80cfd-109">参照してください[手順 3。SAP からデータを取得する SharePoint アプリケーションを作成](../../adapters-and-accelerators/adapter-sap/step-3-create-a-sharepoint-application-to-retrieve-data-from-sap.md)です。</span><span class="sxs-lookup"><span data-stu-id="80cfd-109">See [Step 3: Create a SharePoint Application to Retrieve Data from SAP](../../adapters-and-accelerators/adapter-sap/step-3-create-a-sharepoint-application-to-retrieve-data-from-sap.md).</span></span>  
  
### <a name="to-test-the-sharepoint-application"></a><span data-ttu-id="80cfd-110">SharePoint アプリケーションをテストするには</span><span class="sxs-lookup"><span data-stu-id="80cfd-110">To test the SharePoint application</span></span>  
  
1.  <span data-ttu-id="80cfd-111">SharePoint 3.0 サーバーの全体管理を開始します。</span><span class="sxs-lookup"><span data-stu-id="80cfd-111">Start SharePoint 3.0 Central Administration.</span></span> <span data-ttu-id="80cfd-112">クリックして**開始**、 をポイント**すべてのプログラム**、 をポイント**Microsoft Office Server**、順にクリックします**SharePoint 3.0 サーバーの全体管理**.</span><span class="sxs-lookup"><span data-stu-id="80cfd-112">Click **Start**, point to **All Programs**, point to **Microsoft Office Server**, and then click **SharePoint 3.0 Central Administration**.</span></span>  
  
2.  <span data-ttu-id="80cfd-113">左側のナビゲーション ウィンドウで、アプリケーションを作成する SSP の名前をクリックします。</span><span class="sxs-lookup"><span data-stu-id="80cfd-113">In the left navigation pane, click the name of the SSP under which you created the application.</span></span>  
  
3.  <span data-ttu-id="80cfd-114">左側のウィンドウで次のようにクリックします。**すべてのサイト コンテンツの表示**します。</span><span class="sxs-lookup"><span data-stu-id="80cfd-114">In the left pane, click **View All Site Content**.</span></span> <span data-ttu-id="80cfd-115">右側のウィンドウで次のようにクリックします。**フォーム テンプレート**します。</span><span class="sxs-lookup"><span data-stu-id="80cfd-115">In the right pane, click **Form Templates**.</span></span>  
  
4.  <span data-ttu-id="80cfd-116">**フォーム カテゴリ**一覧で、 **Customer_SalesOrders**します。</span><span class="sxs-lookup"><span data-stu-id="80cfd-116">In the **Form Category** list, click **Customer_SalesOrders**.</span></span> <span data-ttu-id="80cfd-117">Web パーツ ページを作成したときに、この名前を指定します。</span><span class="sxs-lookup"><span data-stu-id="80cfd-117">You specified this name when you created the Web Part page.</span></span> <span data-ttu-id="80cfd-118">次の図は、作成した Web パーツ ページを示します。</span><span class="sxs-lookup"><span data-stu-id="80cfd-118">The following figure shows the Web Part page that you created.</span></span>  
  
     <span data-ttu-id="80cfd-119">![完成した Web パーツ ページ](../../adapters-and-accelerators/adapter-sap/media/3e9f22b1-8285-40f4-a67d-b51173c93671.gif "3e9f22b1-8285-40f4-a67d-b51173c93671")</span><span class="sxs-lookup"><span data-stu-id="80cfd-119">![Completed Web Part page](../../adapters-and-accelerators/adapter-sap/media/3e9f22b1-8285-40f4-a67d-b51173c93671.gif "3e9f22b1-8285-40f4-a67d-b51173c93671")</span></span>  
  
5.  <span data-ttu-id="80cfd-120">検索文字列に基づいて顧客を検索します。</span><span class="sxs-lookup"><span data-stu-id="80cfd-120">Search for customers based on a search string.</span></span> <span data-ttu-id="80cfd-121">たとえば、"John E"で始まる顧客の検索します。</span><span class="sxs-lookup"><span data-stu-id="80cfd-121">For example, search for customers with names starting with "John E".</span></span> <span data-ttu-id="80cfd-122">そのためには次を行います。</span><span class="sxs-lookup"><span data-stu-id="80cfd-122">To do so:</span></span>  
  
    1.  <span data-ttu-id="80cfd-123">最初のリストから、顧客の一覧] セクションで [ **CustomerName**します。</span><span class="sxs-lookup"><span data-stu-id="80cfd-123">In the Customer List section, from the first list, click **CustomerName**.</span></span>  
  
    2.  <span data-ttu-id="80cfd-124">2 番目の一覧からクリックして**で始まる**します。</span><span class="sxs-lookup"><span data-stu-id="80cfd-124">From the second list, click **starts with**.</span></span>  
  
    3.  <span data-ttu-id="80cfd-125">テキスト ボックスに「 **John E**します。</span><span class="sxs-lookup"><span data-stu-id="80cfd-125">In the text box, type **John E**.</span></span>  
  
    4.  <span data-ttu-id="80cfd-126">をクリックして、**データの取得**リンクまたは ENTER キーを押します。</span><span class="sxs-lookup"><span data-stu-id="80cfd-126">Click the **Retrieve Data** link or press ENTER.</span></span> <span data-ttu-id="80cfd-127">次の図は、検索条件に適合する SAP システムから取得したレコードを示します。</span><span class="sxs-lookup"><span data-stu-id="80cfd-127">The following figure shows the records retrieved from the SAP system that satisfy the search criteria.</span></span>  
  
         <span data-ttu-id="80cfd-128">![SAP システムからの結果を検索](../../adapters-and-accelerators/adapter-sap/media/c97e9e2c-0908-46af-9a54-8a4354847c47.gif "c97e9e2c-0908-46af-9a54-8a4354847c47")</span><span class="sxs-lookup"><span data-stu-id="80cfd-128">![Search results from the SAP system](../../adapters-and-accelerators/adapter-sap/media/c97e9e2c-0908-46af-9a54-8a4354847c47.gif "c97e9e2c-0908-46af-9a54-8a4354847c47")</span></span>  
  
6.  <span data-ttu-id="80cfd-129">存在する場合に、販売注文に関連付けられた、顧客とリスト内のすべての顧客の詳細を確認できますようになりました。</span><span class="sxs-lookup"><span data-stu-id="80cfd-129">You can now see the details of any customer in the list and the sales orders associated with the customers, if any.</span></span> <span data-ttu-id="80cfd-130">これを行うには、顧客数に対して、オプション ボタンをクリックします。</span><span class="sxs-lookup"><span data-stu-id="80cfd-130">To do so, click the option button against a customer number.</span></span> <span data-ttu-id="80cfd-131">詳細、およびそれぞれの Web パーツで特定の顧客の販売注文を表示するページを更新します。</span><span class="sxs-lookup"><span data-stu-id="80cfd-131">The page refreshes to present the details and the sales orders for a specific customer in the respective Web Parts.</span></span>  
  
     <span data-ttu-id="80cfd-132">![SharePoint に表示される SAP データ](../../adapters-and-accelerators/adapter-sap/media/29fc4a9e-facd-4455-bcfe-5f4d866b2dc7.gif "29fc4a9e-facd-4455-bcfe-5f4d866b2dc7")</span><span class="sxs-lookup"><span data-stu-id="80cfd-132">![SAP data presented on SharePoint](../../adapters-and-accelerators/adapter-sap/media/29fc4a9e-facd-4455-bcfe-5f4d866b2dc7.gif "29fc4a9e-facd-4455-bcfe-5f4d866b2dc7")</span></span>  
  
     <span data-ttu-id="80cfd-133">顧客と関連付けられている販売注文の詳細が正しく表示されている場合は、このチュートリアルを正常に完了しました。</span><span class="sxs-lookup"><span data-stu-id="80cfd-133">If the details of the customers and the associated sales order are displayed correctly, you have successfully completed the tutorial.</span></span> <span data-ttu-id="80cfd-134">ない場合または不適切なデータが表示される、すべてのタスクが正常に実行するかどうかを確認する作業を慎重に確認します。</span><span class="sxs-lookup"><span data-stu-id="80cfd-134">If no or incorrect data is displayed, carefully check your work to make sure you performed all the tasks correctly.</span></span>  
  
## <a name="summary"></a><span data-ttu-id="80cfd-135">まとめ</span><span class="sxs-lookup"><span data-stu-id="80cfd-135">Summary</span></span>  
 <span data-ttu-id="80cfd-136">このチュートリアルでは、SharePoint ポータルからアクセスする SAP アイテム用の WCF サービスを作成します。</span><span class="sxs-lookup"><span data-stu-id="80cfd-136">In this tutorial you created a WCF service for the SAP artifacts you want to access from a SharePoint Portal.</span></span> <span data-ttu-id="80cfd-137">SAP システムからデータを表示する Web パーツを作成する SharePoint ポータルにインポートされる SAP アイテム用のアプリケーション定義を作成します。</span><span class="sxs-lookup"><span data-stu-id="80cfd-137">You also created an application definition for the SAP artifacts that is imported into a SharePoint portal to create Web Parts to present data from an SAP system.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="80cfd-138">参照</span><span class="sxs-lookup"><span data-stu-id="80cfd-138">See Also</span></span>  
 [<span data-ttu-id="80cfd-139">チュートリアル 1:SAP システムからのデータを SharePoint サイトに表示する</span><span class="sxs-lookup"><span data-stu-id="80cfd-139">Tutorial 1: Presenting Data from an SAP System on a SharePoint Site</span></span>](../../adapters-and-accelerators/adapter-sap/tutorial-1-presenting-data-from-an-sap-system-on-a-sharepoint-site.md)