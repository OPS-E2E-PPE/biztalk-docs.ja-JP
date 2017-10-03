---
title: "手順 4: テスト SharePoint アプリケーションの Siebel アダプターと |Microsoft ドキュメント"
ms.custom: 
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: 
ms.suite: 
ms.tgt_pltfrm: 
ms.topic: article
ms.assetid: ec1392fa-fdc1-42be-b4dc-75a55d8fa400
caps.latest.revision: "9"
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: 85cebcafcdf768686ed3f7382a0838db5062d96b
ms.sourcegitcommit: cb908c540d8f1a692d01dc8f313e16cb4b4e696d
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 09/20/2017
---
# <a name="step-4-test-your-sharepoint-application-with-the-siebel-adapter"></a><span data-ttu-id="a1c0f-102">手順 4: Siebel アダプターと、SharePoint アプリケーションをテストします。</span><span class="sxs-lookup"><span data-stu-id="a1c0f-102">Step 4: Test Your SharePoint Application with the Siebel adapter</span></span>
<span data-ttu-id="a1c0f-103">![4 のステップ 4](../../adapters-and-accelerators/adapter-oracle-ebs/media/step-4of4.gif "Step_4of4")</span><span class="sxs-lookup"><span data-stu-id="a1c0f-103">![Step 4 of 4](../../adapters-and-accelerators/adapter-oracle-ebs/media/step-4of4.gif "Step_4of4")</span></span>  
  
 <span data-ttu-id="a1c0f-104">**所要時間:** 5 分です。</span><span class="sxs-lookup"><span data-stu-id="a1c0f-104">**Time to complete:** 5 minutes.</span></span>  
  
 <span data-ttu-id="a1c0f-105">**目標:** SharePoint サイトに Web パーツを追加するいるし、アプリケーションを作成する必要がありますアプリケーションをテストする Siebel システムの一部のデータを取得しています。</span><span class="sxs-lookup"><span data-stu-id="a1c0f-105">**Objective:** After you have added Web Parts in the SharePoint site and created an application, you must test the application by retrieving some data from the Siebel system.</span></span> <span data-ttu-id="a1c0f-106">このセクションでは、アプリケーションを使用して、Siebel システムからデータを取得する方法の指示を提供します。</span><span class="sxs-lookup"><span data-stu-id="a1c0f-106">This section provides instructions on how to use the application to retrieve the data from the Siebel system.</span></span>  
  
## <a name="prerequisites"></a><span data-ttu-id="a1c0f-107">前提条件</span><span class="sxs-lookup"><span data-stu-id="a1c0f-107">Prerequisites</span></span>  
 <span data-ttu-id="a1c0f-108">ビジネス データを取得する適切な Web パーツを含む Web パーツ ページを作成する必要があります。</span><span class="sxs-lookup"><span data-stu-id="a1c0f-108">You should have created the Web Part page containing the appropriate Web Parts to retrieve business data.</span></span> <span data-ttu-id="a1c0f-109">参照してください[手順 3: Siebel からデータを取得する SharePoint アプリケーションを作成](../../adapters-and-accelerators/adapter-siebel/step-3-create-a-sharepoint-application-to-retrieve-data-from-siebel.md)です。</span><span class="sxs-lookup"><span data-stu-id="a1c0f-109">See [Step 3: Create a SharePoint Application to Retrieve Data from Siebel](../../adapters-and-accelerators/adapter-siebel/step-3-create-a-sharepoint-application-to-retrieve-data-from-siebel.md).</span></span>  
  
### <a name="to-test-the-sharepoint-application"></a><span data-ttu-id="a1c0f-110">SharePoint アプリケーションをテストするには</span><span class="sxs-lookup"><span data-stu-id="a1c0f-110">To test the SharePoint application</span></span>  
  
1.  <span data-ttu-id="a1c0f-111">SharePoint 3.0 サーバーの全体管理を開始します。</span><span class="sxs-lookup"><span data-stu-id="a1c0f-111">Start SharePoint 3.0 Central Administration.</span></span> <span data-ttu-id="a1c0f-112">をクリックして**開始**、 をポイント**すべてのプログラム**、 をポイント**Microsoft Office Server**、クリックして**SharePoint 3.0 サーバーの全体管理**.</span><span class="sxs-lookup"><span data-stu-id="a1c0f-112">Click **Start**, point to **All Programs**, point to **Microsoft Office Server**, and then click **SharePoint 3.0 Central Administration**.</span></span>  
  
2.  <span data-ttu-id="a1c0f-113">左側のナビゲーション ウィンドウで、アプリケーションを作成する、SSP の名前をクリックします。</span><span class="sxs-lookup"><span data-stu-id="a1c0f-113">In the left navigation pane, click the name of the SSP under which you created the application.</span></span>  
  
3.  <span data-ttu-id="a1c0f-114">左側のウィンドウでをクリックして**すべてのサイト コンテンツの表示**です。</span><span class="sxs-lookup"><span data-stu-id="a1c0f-114">In the left pane, click **View All Site Content**.</span></span> <span data-ttu-id="a1c0f-115">右側のウィンドウからをクリックして**フォーム テンプレート**です。</span><span class="sxs-lookup"><span data-stu-id="a1c0f-115">From the right pane, click **Form Templates**.</span></span>  
  
4.  <span data-ttu-id="a1c0f-116">**フォーム カテゴリ**一覧で、クリックして**Siebel アカウント**です。</span><span class="sxs-lookup"><span data-stu-id="a1c0f-116">In the **Form Category** list, click **Siebel Account**.</span></span> <span data-ttu-id="a1c0f-117">Web パーツ ページを作成中には、この名前を指定します。</span><span class="sxs-lookup"><span data-stu-id="a1c0f-117">You specified this name while creating the Web Part page.</span></span> <span data-ttu-id="a1c0f-118">次の図は、作成した Web パーツ ページを示します。</span><span class="sxs-lookup"><span data-stu-id="a1c0f-118">The following figure shows the Web Part page that you created.</span></span>  
  
     <span data-ttu-id="a1c0f-119">![完成した Web パーツ ページ](../../adapters-and-accelerators/adapter-siebel/media/a0bfe7af-0246-4f0b-aa0d-0ee084456003.gif "a0bfe7af-0246-4f0b-aa0d-0ee084456003")</span><span class="sxs-lookup"><span data-stu-id="a1c0f-119">![Completed Web Part page](../../adapters-and-accelerators/adapter-siebel/media/a0bfe7af-0246-4f0b-aa0d-0ee084456003.gif "a0bfe7af-0246-4f0b-aa0d-0ee084456003")</span></span>  
  
5.  <span data-ttu-id="a1c0f-120">検索文字列に基づくアカウント ビジネス コンポーネントのクエリを実行します。</span><span class="sxs-lookup"><span data-stu-id="a1c0f-120">Query the Account business component based on a search string.</span></span> <span data-ttu-id="a1c0f-121">たとえば、検索式を指定`[Name] LIKE ‘W*’`です。</span><span class="sxs-lookup"><span data-stu-id="a1c0f-121">For example, specify the search expression `[Name] LIKE ‘W*’`.</span></span> <span data-ttu-id="a1c0f-122">そのためには次を行います。</span><span class="sxs-lookup"><span data-stu-id="a1c0f-122">To do so:</span></span>  
  
    1.  <span data-ttu-id="a1c0f-123">**アカウント一覧**セクションの最初のリストから選択**SearchExpression**、し、**と等しい**です。</span><span class="sxs-lookup"><span data-stu-id="a1c0f-123">In the **Account List** section, from the first list, select **SearchExpression**, and then select **is equal to**.</span></span>  
  
    2.  <span data-ttu-id="a1c0f-124">テキスト フィールドに「`[Name] LIKE ‘W*’`です。</span><span class="sxs-lookup"><span data-stu-id="a1c0f-124">In the text field, type `[Name] LIKE ‘W*’`.</span></span>  
  
    3.  <span data-ttu-id="a1c0f-125">をクリックして**データの取得**リンク、または ENTER キーを押します。</span><span class="sxs-lookup"><span data-stu-id="a1c0f-125">Click **Retrieve Data** link, or press ENTER.</span></span> <span data-ttu-id="a1c0f-126">次の図は、検索条件に適合する Siebel システムから取得したレコードを示します。</span><span class="sxs-lookup"><span data-stu-id="a1c0f-126">The following figure shows the records retrieved from the Siebel system that satisfy the search criteria.</span></span>  
  
         <span data-ttu-id="a1c0f-127">![Siebel システムからの結果を検索](../../adapters-and-accelerators/adapter-siebel/media/6c4721ac-c7bc-4626-9ee0-55cf322026cf.gif "6c4721ac-c7bc-4626-9ee0-55cf322026cf")</span><span class="sxs-lookup"><span data-stu-id="a1c0f-127">![Search results from the Siebel system](../../adapters-and-accelerators/adapter-siebel/media/6c4721ac-c7bc-4626-9ee0-55cf322026cf.gif "6c4721ac-c7bc-4626-9ee0-55cf322026cf")</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="a1c0f-128">参照</span><span class="sxs-lookup"><span data-stu-id="a1c0f-128">See Also</span></span>  
 [<span data-ttu-id="a1c0f-129">チュートリアル 1: SharePoint サイト上の Siebel システムからのデータの表示</span><span class="sxs-lookup"><span data-stu-id="a1c0f-129">Tutorial 1: Presenting Data From a Siebel System on a SharePoint Site</span></span>](../../adapters-and-accelerators/adapter-siebel/tutorial-1-presenting-data-from-a-siebel-system-on-a-sharepoint-site.md)