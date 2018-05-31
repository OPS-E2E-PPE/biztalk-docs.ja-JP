---
title: PeopleSoft システムの使用 |Microsoft ドキュメント
ms.custom: ''
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: ''
ms.suite: ''
ms.tgt_pltfrm: ''
ms.topic: article
ms.assetid: c228ac23-184f-4c08-922b-ba84f5f2c52f
caps.latest.revision: 18
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: c93e025ddb2ccec4b0088c20837a4f307f40aada
ms.sourcegitcommit: cb908c540d8f1a692d01dc8f313e16cb4b4e696d
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 09/20/2017
ms.locfileid: "22287378"
---
# <a name="using-a-peoplesoft-system"></a><span data-ttu-id="6ef7b-102">PeopleSoft システムの使用</span><span class="sxs-lookup"><span data-stu-id="6ef7b-102">Using a PeopleSoft System</span></span>
<span data-ttu-id="6ef7b-103">PeopleSoft システムは、[!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)] システムから PeopleSoft アダプターを使用してアクセスできます。</span><span class="sxs-lookup"><span data-stu-id="6ef7b-103">The PeopleSoft system is accessible from a [!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)] system by using the PeopleSoft adapter.</span></span> <span data-ttu-id="6ef7b-104">このアダプターは、Microsoft が [!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)] 用に提供する 8 つの基幹業務 (LOB) アダプターの 1 つです。</span><span class="sxs-lookup"><span data-stu-id="6ef7b-104">This adapter is one of a group of eight line-of-business (LOB) adapters shipped by Microsoft for use with [!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)].</span></span>  
  
 <span data-ttu-id="6ef7b-105">PeopleSoft ラボ作業は 2 つのパートに分かれています。</span><span class="sxs-lookup"><span data-stu-id="6ef7b-105">The PeopleSoft lab work is divided into two parts.</span></span> <span data-ttu-id="6ef7b-106">この最初のラボ (ラボ 1) では、[!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)] またはその他の Microsoft 製品 (Internet Explorer は例外ですが、任意のブラウザーを使用可能) を使用しなくても、PeopleSoft システムを使用できます。</span><span class="sxs-lookup"><span data-stu-id="6ef7b-106">This first lab (Lab 1) allows you to use the PeopleSoft system without needing [!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)] or any Microsoft products (except perhaps Internet Explorer, but you can use any browser).</span></span> <span data-ttu-id="6ef7b-107">このラボでは、PeopleSoft システムに接続して単純なデータ レコードを検索し、変更します。</span><span class="sxs-lookup"><span data-stu-id="6ef7b-107">In this lab, you will connect to the PeopleSoft system to locate and modify a simple data record.</span></span>  
  
 <span data-ttu-id="6ef7b-108">2 番目のラボ (ラボ 2) では、BizTalk プロジェクトおよびオーケストレーションを作成します。</span><span class="sxs-lookup"><span data-stu-id="6ef7b-108">In the second lab (Lab 2), you will create a BizTalk project and orchestration.</span></span> <span data-ttu-id="6ef7b-109">アプリケーションの作成後、そのアプリケーションを展開および利用し、PeopleSoft アダプターを使用して PeopleSoft システムに接続します。</span><span class="sxs-lookup"><span data-stu-id="6ef7b-109">After you create the application, you will deploy it and use it to connect to a PeopleSoft system by using the PeopleSoft adapter.</span></span> <span data-ttu-id="6ef7b-110">目標は、アダプターを使用して BizTalk アプリケーションを介してデータにアクセスすることです。</span><span class="sxs-lookup"><span data-stu-id="6ef7b-110">The goal is to access data through the BizTalk application by using the adapter.</span></span>  
  
## <a name="prerequisites"></a><span data-ttu-id="6ef7b-111">前提条件</span><span class="sxs-lookup"><span data-stu-id="6ef7b-111">Prerequisites</span></span>  
 <span data-ttu-id="6ef7b-112">このラボの手順を実行するには、ブラウザー、インターネット接続、および PeopleSoft のユーザー アカウントが必要です。</span><span class="sxs-lookup"><span data-stu-id="6ef7b-112">To perform the procedures for this lab, you need a browser and an Internet connection, along with a user account on a PeopleSoft system.</span></span> <span data-ttu-id="6ef7b-113">また、PeopleSoft システムに Web でアクセスするには、参照先を知っている必要があります。</span><span class="sxs-lookup"><span data-stu-id="6ef7b-113">You need to know the location to browse to for gaining Web access to your PeopleSoft system.</span></span> <span data-ttu-id="6ef7b-114">[!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)] または他の Microsoft テクノロジは必要ありません。</span><span class="sxs-lookup"><span data-stu-id="6ef7b-114">You do not need [!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)] or any other Microsoft technologies.</span></span>  
  
## <a name="lab-1---using-a-peoplesoft-system"></a><span data-ttu-id="6ef7b-115">ラボ 1 - PeopleSoft システムの使用</span><span class="sxs-lookup"><span data-stu-id="6ef7b-115">Lab 1 - Using a PeopleSoft System</span></span>  
 <span data-ttu-id="6ef7b-116">このラボでは、[!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)] のコンポーネントを使用せずに、PeopleSoft システムを使用します。</span><span class="sxs-lookup"><span data-stu-id="6ef7b-116">In this lab, you will use the PeopleSoft system without using any components of [!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)].</span></span> <span data-ttu-id="6ef7b-117">目標は、2 番目のラボが適切に動作するように、PeopleSoft への接続をテストすることです。</span><span class="sxs-lookup"><span data-stu-id="6ef7b-117">The goal is to test your connectivity to PeopleSoft to ensure that the second lab will work correctly.</span></span> <span data-ttu-id="6ef7b-118">まず、Web インターフェイスを介して PeopleSoft システムに接続します。システムには、Internet Explorer などのブラウザーを使用してログオンできます。</span><span class="sxs-lookup"><span data-stu-id="6ef7b-118">Initially you connect to the PeopleSoft system through its Web interface that allows you to log on by using a browser such as Internet Explorer.</span></span>  
  
## <a name="procedures-for-lab-1---using-a-peoplesoft-system"></a><span data-ttu-id="6ef7b-119">ラボ 1 の手順 - PeopleSoft システムの使用</span><span class="sxs-lookup"><span data-stu-id="6ef7b-119">Procedures for Lab 1 - Using a PeopleSoft System</span></span>  
  
#### <a name="to-log-on-to-peoplesoft-by-using-a-browser"></a><span data-ttu-id="6ef7b-120">ブラウザーを使用して PeopleSoft にログオンするには</span><span class="sxs-lookup"><span data-stu-id="6ef7b-120">To log on to PeopleSoft by using a browser</span></span>  
  
-   <span data-ttu-id="6ef7b-121">PeopleSoft ログオン ページを参照して、PeopleSoft システムにログインします。</span><span class="sxs-lookup"><span data-stu-id="6ef7b-121">Log on to the PeopleSoft system by browsing to a PeopleSoft logon page.</span></span> <span data-ttu-id="6ef7b-122">入力、**ユーザー ID**と**パスワード** をクリックし、**サイン イン**です。</span><span class="sxs-lookup"><span data-stu-id="6ef7b-122">Enter your **User ID** and **Password** and then click **Sign In**.</span></span>  
  
     ![](../core/media/1e3e5c0f-316b-4aa3-946e-3bb3665b0ddb.gif "1e3e5c0f-316b-4aa3-946e-3bb3665b0ddb")  
  
#### <a name="to-locate-and-modify-peoplesoft-data"></a><span data-ttu-id="6ef7b-123">PeopleSoft データを検索および変更するには</span><span class="sxs-lookup"><span data-stu-id="6ef7b-123">To locate and modify PeopleSoft data</span></span>  
  
1.  <span data-ttu-id="6ef7b-124">ログオンが完了すると、レイアウトを選択して表示するコンテンツを個人用に設定できるページが表示されます。</span><span class="sxs-lookup"><span data-stu-id="6ef7b-124">A successful logon places you at the page to personalize the content you see by choosing its layout.</span></span> <span data-ttu-id="6ef7b-125">下へスクロールし、展開**財務/サプライ チェーンの設定**、 をクリックして**共通定義**をクリックして**場所**、順にクリック**場所**もう一度です。</span><span class="sxs-lookup"><span data-stu-id="6ef7b-125">Scroll down and expand **Set Up Financials/Supply Chain**, click **Common Definitions**, click **Location**, and then click **Location** again.</span></span> <span data-ttu-id="6ef7b-126">表示、**場所**検索インターフェイスです。</span><span class="sxs-lookup"><span data-stu-id="6ef7b-126">This brings you to the **Location** search interface.</span></span>  
  
     ![](../core/media/62a89cd4-464c-42fd-91cd-60ceeab5b006.gif "62a89cd4-464c-42fd-91cd-60ceeab5b006")  
  
2.  <span data-ttu-id="6ef7b-127">検索を開始するには、次のように設定します**SetID**に **=** 、設定されて**場所コード**に**で始まる**、入力 **、。**、クリックして**検索**です。</span><span class="sxs-lookup"><span data-stu-id="6ef7b-127">To begin the search, set **SetID** to **=**, set **Location Code** to **begins with**, enter **A**, and then click **Search**.</span></span> <span data-ttu-id="6ef7b-128">A で始まる名前の都市が表示されます、**検索結果**インターフェイスのセクションです。</span><span class="sxs-lookup"><span data-stu-id="6ef7b-128">This displays cities whose names start with A in the **Search Results** section of the interface.</span></span>  
  
     ![](../core/media/86661144-c666-4d72-9227-9f17df715ba4.gif "86661144-c666-4d72-9227-9f17df715ba4")  
  
3.  <span data-ttu-id="6ef7b-129">詳細情報を表示するには、いずれかの場所をクリックします。</span><span class="sxs-lookup"><span data-stu-id="6ef7b-129">Click one of the locations to get its detail information.</span></span> <span data-ttu-id="6ef7b-130">たとえば、次の図に、ユーザーがクリックした、 **AUS01**内のリンク、**場所コード**列です。</span><span class="sxs-lookup"><span data-stu-id="6ef7b-130">For example, in the figure below, the user clicked the **AUS01** link in the **Location Code** column.</span></span>  
  
4.  <span data-ttu-id="6ef7b-131">フィールドのいずれかに新しいデータの一部を入力してください (など、**アドレス 2**フィールド) をクリック**保存**左下隅にあります。</span><span class="sxs-lookup"><span data-stu-id="6ef7b-131">Enter some new data into one of the fields (such as the **Address 2** field) and click **Save** in the lower-left corner.</span></span> <span data-ttu-id="6ef7b-132">新しく入力したデータはレコードに保存されます。</span><span class="sxs-lookup"><span data-stu-id="6ef7b-132">This saves the newly entered data into the record.</span></span>  
  
     ![](../core/media/b6eb137c-c0b0-4906-8fbd-1bc036069fb0.gif "b6eb137c-c0b0-4906-8fbd-1bc036069fb0")  
  
5.  <span data-ttu-id="6ef7b-133">この変更が確実に行われたことを確認するには、手順 2. のプロセスを繰り返して同じレコードを再検索し、レコードの変更結果を確認します。</span><span class="sxs-lookup"><span data-stu-id="6ef7b-133">To verify the success of this change, repeat the process from step 2, find this same record again, and observe the changes made to the record.</span></span>  
  
6.  <span data-ttu-id="6ef7b-134">ウィンドウの右上隅の部分で、クリックして**サインアウト**PeopleSoft セッションを終了します。</span><span class="sxs-lookup"><span data-stu-id="6ef7b-134">In the upper-right portion of the window, click **Sign out** to end your PeopleSoft session.</span></span>  
  
     ![](../core/media/7760b541-5155-453e-a682-4780412f3c13.gif "7760b541-5155-453e-a682-4780412f3c13")  
  
    > [!NOTE]
    >  <span data-ttu-id="6ef7b-135">次のラボでは、PeopleSoft アダプターを使用して、変更した場所レコード (AUS01) の情報を取得する手順を示します。</span><span class="sxs-lookup"><span data-stu-id="6ef7b-135">In the next lab there are instructions for using the PeopleSoft adapter to retrieve the information for the location record (AUS01) that you modified.</span></span>  
  
## <a name="summary"></a><span data-ttu-id="6ef7b-136">概要</span><span class="sxs-lookup"><span data-stu-id="6ef7b-136">Summary</span></span>  
 <span data-ttu-id="6ef7b-137">このラボでは、ブラウザーを介して PeopleSoft システムにログオンしました。</span><span class="sxs-lookup"><span data-stu-id="6ef7b-137">In this lab you logged on to the PeopleSoft system through a browser.</span></span> <span data-ttu-id="6ef7b-138">接続後にデータを検索し、レコードのアドレス フィールドを操作および更新しました。</span><span class="sxs-lookup"><span data-stu-id="6ef7b-138">After you were connected, you searched for data, and then manipulated and updated a record's address field.</span></span> <span data-ttu-id="6ef7b-139">変更終了後は、ブラウザーで変更されたデータを表示し、変更が適切に実行されたことを確認しました。</span><span class="sxs-lookup"><span data-stu-id="6ef7b-139">After committing the change, you could view the modified data in the browser to verify that the change executed properly.</span></span>