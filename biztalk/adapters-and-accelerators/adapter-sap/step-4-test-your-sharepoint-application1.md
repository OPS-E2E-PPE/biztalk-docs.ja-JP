---
title: "手順 4: テスト、SharePoint アプリケーションの 1 |Microsoft ドキュメント"
ms.custom: 
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: 
ms.suite: 
ms.tgt_pltfrm: 
ms.topic: article
ms.assetid: f7ded5a5-88d5-40aa-814b-70bc0a7dcfa3
caps.latest.revision: "7"
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: 9b8be51df02bd9796b41201c0495758c281e8f14
ms.sourcegitcommit: cb908c540d8f1a692d01dc8f313e16cb4b4e696d
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 09/20/2017
---
# <a name="step-4-test-your-sharepoint-application"></a><span data-ttu-id="67b32-102">手順 4: SharePoint アプリケーションをテストします。</span><span class="sxs-lookup"><span data-stu-id="67b32-102">Step 4: Test Your SharePoint Application</span></span>
<span data-ttu-id="67b32-103">![4 のステップ 4](../../adapters-and-accelerators/adapter-oracle-ebs/media/step-4of4.gif "Step_4of4")</span><span class="sxs-lookup"><span data-stu-id="67b32-103">![Step 4 of 4](../../adapters-and-accelerators/adapter-oracle-ebs/media/step-4of4.gif "Step_4of4")</span></span>  
  
 <span data-ttu-id="67b32-104">**所要時間:** 10 分</span><span class="sxs-lookup"><span data-stu-id="67b32-104">**Time to complete:** 10 minutes</span></span>  
  
 <span data-ttu-id="67b32-105">**目標:** SharePoint サイトに Web パーツを追加するいるし、アプリケーションを作成する必要がありますアプリケーションをテストする SAP システムから一部のデータを取得しています。</span><span class="sxs-lookup"><span data-stu-id="67b32-105">**Objective:** After you have added Web Parts in the SharePoint site and created an application, you must test the application by retrieving some data from the SAP system.</span></span> <span data-ttu-id="67b32-106">このトピックでは、アプリケーションを使用して SAP システムからデータを取得する方法について説明します。</span><span class="sxs-lookup"><span data-stu-id="67b32-106">This topic provides instructions on how to use the application to retrieve the data from the SAP system.</span></span>  
  
## <a name="prerequisites"></a><span data-ttu-id="67b32-107">前提条件</span><span class="sxs-lookup"><span data-stu-id="67b32-107">Prerequisites</span></span>  
  
-   <span data-ttu-id="67b32-108">ビジネス データを取得する適切な Web パーツが含まれる Web パーツ ページを作成する必要があります。</span><span class="sxs-lookup"><span data-stu-id="67b32-108">You should have created the Web Part page that contains the appropriate Web Parts to retrieve business data.</span></span> <span data-ttu-id="67b32-109">参照してください[手順 3: SAP からデータを取得する SharePoint アプリケーションを作成](../../adapters-and-accelerators/adapter-sap/step-3-create-a-sharepoint-application-to-retrieve-data-from-sap.md)です。</span><span class="sxs-lookup"><span data-stu-id="67b32-109">See [Step 3: Create a SharePoint Application to Retrieve Data from SAP](../../adapters-and-accelerators/adapter-sap/step-3-create-a-sharepoint-application-to-retrieve-data-from-sap.md).</span></span>  
  
### <a name="to-test-the-sharepoint-application"></a><span data-ttu-id="67b32-110">SharePoint アプリケーションをテストするには</span><span class="sxs-lookup"><span data-stu-id="67b32-110">To test the SharePoint application</span></span>  
  
1.  <span data-ttu-id="67b32-111">SharePoint 3.0 サーバーの全体管理を開始します。</span><span class="sxs-lookup"><span data-stu-id="67b32-111">Start SharePoint 3.0 Central Administration.</span></span> <span data-ttu-id="67b32-112">をクリックして**開始**、 をポイント**すべてのプログラム**、 をポイント**Microsoft Office Server**、クリックして**SharePoint 3.0 サーバーの全体管理**.</span><span class="sxs-lookup"><span data-stu-id="67b32-112">Click **Start**, point to **All Programs**, point to **Microsoft Office Server**, and then click **SharePoint 3.0 Central Administration**.</span></span>  
  
2.  <span data-ttu-id="67b32-113">左側のナビゲーション ウィンドウで、アプリケーションを作成する、SSP の名前をクリックします。</span><span class="sxs-lookup"><span data-stu-id="67b32-113">In the left navigation pane, click the name of the SSP under which you created the application.</span></span>  
  
3.  <span data-ttu-id="67b32-114">左側のウィンドウでをクリックして**すべてのサイト コンテンツの表示**です。</span><span class="sxs-lookup"><span data-stu-id="67b32-114">In the left pane, click **View All Site Content**.</span></span> <span data-ttu-id="67b32-115">右側のウィンドウでをクリックして**フォーム テンプレート**です。</span><span class="sxs-lookup"><span data-stu-id="67b32-115">In the right pane, click **Form Templates**.</span></span>  
  
4.  <span data-ttu-id="67b32-116">**フォーム カテゴリ**一覧で、クリックして**Customer_SalesOrders**です。</span><span class="sxs-lookup"><span data-stu-id="67b32-116">In the **Form Category** list, click **Customer_SalesOrders**.</span></span> <span data-ttu-id="67b32-117">Web パーツ ページを作成したときに、この名前を指定します。</span><span class="sxs-lookup"><span data-stu-id="67b32-117">You specified this name when you created the Web Part page.</span></span> <span data-ttu-id="67b32-118">次の図は、作成した Web パーツ ページを示します。</span><span class="sxs-lookup"><span data-stu-id="67b32-118">The following figure shows the Web Part page that you created.</span></span>  
  
     <span data-ttu-id="67b32-119">![完成した Web パーツ ページ](../../adapters-and-accelerators/adapter-sap/media/3e9f22b1-8285-40f4-a67d-b51173c93671.gif "3e9f22b1-8285-40f4-a67d-b51173c93671")</span><span class="sxs-lookup"><span data-stu-id="67b32-119">![Completed Web Part page](../../adapters-and-accelerators/adapter-sap/media/3e9f22b1-8285-40f4-a67d-b51173c93671.gif "3e9f22b1-8285-40f4-a67d-b51173c93671")</span></span>  
  
5.  <span data-ttu-id="67b32-120">検索文字列に基づいて顧客を検索します。</span><span class="sxs-lookup"><span data-stu-id="67b32-120">Search for customers based on a search string.</span></span> <span data-ttu-id="67b32-121">たとえば、"John E"で始まる顧客を検索します。</span><span class="sxs-lookup"><span data-stu-id="67b32-121">For example, search for customers with names starting with "John E".</span></span> <span data-ttu-id="67b32-122">そのためには次を行います。</span><span class="sxs-lookup"><span data-stu-id="67b32-122">To do so:</span></span>  
  
    1.  <span data-ttu-id="67b32-123">最初のリストから、顧客の一覧のセクションで  **CustomerName**です。</span><span class="sxs-lookup"><span data-stu-id="67b32-123">In the Customer List section, from the first list, click **CustomerName**.</span></span>  
  
    2.  <span data-ttu-id="67b32-124">2 番目の一覧からクリックして**で始まる**です。</span><span class="sxs-lookup"><span data-stu-id="67b32-124">From the second list, click **starts with**.</span></span>  
  
    3.  <span data-ttu-id="67b32-125">テキスト ボックスで、次のように入力します。 **John E**です。</span><span class="sxs-lookup"><span data-stu-id="67b32-125">In the text box, type **John E**.</span></span>  
  
    4.  <span data-ttu-id="67b32-126">クリックして、**データの取得**リンクまたは ENTER キーを押します。</span><span class="sxs-lookup"><span data-stu-id="67b32-126">Click the **Retrieve Data** link or press ENTER.</span></span> <span data-ttu-id="67b32-127">次の図は、検索条件に適合する SAP システムから取得したレコードを示します。</span><span class="sxs-lookup"><span data-stu-id="67b32-127">The following figure shows the records retrieved from the SAP system that satisfy the search criteria.</span></span>  
  
         <span data-ttu-id="67b32-128">![SAP システムからの結果を検索](../../adapters-and-accelerators/adapter-sap/media/c97e9e2c-0908-46af-9a54-8a4354847c47.gif "c97e9e2c-0908-46af-9a54-8a4354847c47")</span><span class="sxs-lookup"><span data-stu-id="67b32-128">![Search results from the SAP system](../../adapters-and-accelerators/adapter-sap/media/c97e9e2c-0908-46af-9a54-8a4354847c47.gif "c97e9e2c-0908-46af-9a54-8a4354847c47")</span></span>  
  
6.  <span data-ttu-id="67b32-129">リスト内のすべての顧客の詳細を表示できるようになりましたし、販売注文に関連付けられている、顧客、存在する場合。</span><span class="sxs-lookup"><span data-stu-id="67b32-129">You can now see the details of any customer in the list and the sales orders associated with the customers, if any.</span></span> <span data-ttu-id="67b32-130">これを行うには、顧客番号に対して、オプション ボタンをクリックします。</span><span class="sxs-lookup"><span data-stu-id="67b32-130">To do so, click the option button against a customer number.</span></span> <span data-ttu-id="67b32-131">詳細とそれぞれの Web パーツで特定の顧客の販売注文を表示するページを更新します。</span><span class="sxs-lookup"><span data-stu-id="67b32-131">The page refreshes to present the details and the sales orders for a specific customer in the respective Web Parts.</span></span>  
  
     <span data-ttu-id="67b32-132">![SharePoint に表示される SAP データ](../../adapters-and-accelerators/adapter-sap/media/29fc4a9e-facd-4455-bcfe-5f4d866b2dc7.gif "29fc4a9e-facd-4455-bcfe-5f4d866b2dc7")</span><span class="sxs-lookup"><span data-stu-id="67b32-132">![SAP data presented on SharePoint](../../adapters-and-accelerators/adapter-sap/media/29fc4a9e-facd-4455-bcfe-5f4d866b2dc7.gif "29fc4a9e-facd-4455-bcfe-5f4d866b2dc7")</span></span>  
  
     <span data-ttu-id="67b32-133">顧客と関連する販売注文の詳細が正しく表示されている場合は、このチュートリアルを正常に完了しました。</span><span class="sxs-lookup"><span data-stu-id="67b32-133">If the details of the customers and the associated sales order are displayed correctly, you have successfully completed the tutorial.</span></span> <span data-ttu-id="67b32-134">ない場合、または不適切なデータが表示されたら、すべてのタスクが正常に実行するかどうかを確認する作業を慎重に確認します。</span><span class="sxs-lookup"><span data-stu-id="67b32-134">If no or incorrect data is displayed, carefully check your work to make sure you performed all the tasks correctly.</span></span>  
  
## <a name="summary"></a><span data-ttu-id="67b32-135">概要</span><span class="sxs-lookup"><span data-stu-id="67b32-135">Summary</span></span>  
 <span data-ttu-id="67b32-136">このチュートリアルでは、SharePoint ポータルからアクセスする SAP 成果物のための WCF サービスを作成します。</span><span class="sxs-lookup"><span data-stu-id="67b32-136">In this tutorial you created a WCF service for the SAP artifacts you want to access from a SharePoint Portal.</span></span> <span data-ttu-id="67b32-137">SAP システムからデータを表示する Web パーツを作成する SharePoint ポータルにインポートされている SAP 成果物のためのアプリケーション定義を作成します。</span><span class="sxs-lookup"><span data-stu-id="67b32-137">You also created an application definition for the SAP artifacts that is imported into a SharePoint portal to create Web Parts to present data from an SAP system.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="67b32-138">参照</span><span class="sxs-lookup"><span data-stu-id="67b32-138">See Also</span></span>  
 [<span data-ttu-id="67b32-139">チュートリアル 1: SharePoint サイト上の SAP システムからのデータの表示</span><span class="sxs-lookup"><span data-stu-id="67b32-139">Tutorial 1: Presenting Data from an SAP System on a SharePoint Site</span></span>](../../adapters-and-accelerators/adapter-sap/tutorial-1-presenting-data-from-an-sap-system-on-a-sharepoint-site.md)