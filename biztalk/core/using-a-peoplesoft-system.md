---
title: PeopleSoft システムの使用 |Microsoft Docs
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
ms.openlocfilehash: 9b7f98086c5e2be4e236a5691e4ff5633ac5f45b
ms.sourcegitcommit: 381e83d43796a345488d54b3f7413e11d56ad7be
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 05/07/2019
ms.locfileid: "65399943"
---
# <a name="using-a-peoplesoft-system"></a><span data-ttu-id="62d9c-102">PeopleSoft システムの使用</span><span class="sxs-lookup"><span data-stu-id="62d9c-102">Using a PeopleSoft System</span></span>
<span data-ttu-id="62d9c-103">PeopleSoft システムは、 [!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)] システムから PeopleSoft アダプターを使用してアクセスできます。</span><span class="sxs-lookup"><span data-stu-id="62d9c-103">The PeopleSoft system is accessible from a [!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)] system by using the PeopleSoft adapter.</span></span> <span data-ttu-id="62d9c-104">このアダプターは、Microsoft が [!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)]用に提供する 8 つの基幹業務 (LOB) アダプターの 1 つです。</span><span class="sxs-lookup"><span data-stu-id="62d9c-104">This adapter is one of a group of eight line-of-business (LOB) adapters shipped by Microsoft for use with [!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)].</span></span>  
  
 <span data-ttu-id="62d9c-105">PeopleSoft ラボ作業は、2 つの部分に分かれています。</span><span class="sxs-lookup"><span data-stu-id="62d9c-105">The PeopleSoft lab work is divided into two parts.</span></span> <span data-ttu-id="62d9c-106">この最初のラボ (ラボ 1) では、PeopleSoft システムをしなくても使用できます。[!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)]などの Microsoft 製品 (ただし、おそらくが Internet Explorer では、任意のブラウザーを使用できます)。</span><span class="sxs-lookup"><span data-stu-id="62d9c-106">This first lab (Lab 1) allows you to use the PeopleSoft system without needing [!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)] or any Microsoft products (except perhaps Internet Explorer, but you can use any browser).</span></span> <span data-ttu-id="62d9c-107">このラボでは、単純なデータ レコードの変更を見つけて、PeopleSoft システムに接続します。</span><span class="sxs-lookup"><span data-stu-id="62d9c-107">In this lab, you will connect to the PeopleSoft system to locate and modify a simple data record.</span></span>  
  
 <span data-ttu-id="62d9c-108">2 番目のラボ (ラボ 2) では、BizTalk プロジェクトおよびオーケストレーションを作成します。</span><span class="sxs-lookup"><span data-stu-id="62d9c-108">In the second lab (Lab 2), you will create a BizTalk project and orchestration.</span></span> <span data-ttu-id="62d9c-109">アプリケーションを作成した後は、デプロイし、PeopleSoft アダプターを使用して PeopleSoft システムへの接続に使用されます。</span><span class="sxs-lookup"><span data-stu-id="62d9c-109">After you create the application, you will deploy it and use it to connect to a PeopleSoft system by using the PeopleSoft adapter.</span></span> <span data-ttu-id="62d9c-110">目標は、アダプターを使用して BizTalk アプリケーションを介してデータにアクセスします。</span><span class="sxs-lookup"><span data-stu-id="62d9c-110">The goal is to access data through the BizTalk application by using the adapter.</span></span>  
  
## <a name="prerequisites"></a><span data-ttu-id="62d9c-111">前提条件</span><span class="sxs-lookup"><span data-stu-id="62d9c-111">Prerequisites</span></span>  
 <span data-ttu-id="62d9c-112">このラボの手順を実行するには、ブラウザーと PeopleSoft システムでユーザー アカウントと共に、インターネットに接続が必要です。</span><span class="sxs-lookup"><span data-stu-id="62d9c-112">To perform the procedures for this lab, you need a browser and an Internet connection, along with a user account on a PeopleSoft system.</span></span> <span data-ttu-id="62d9c-113">PeopleSoft システムへの Web アクセスを得るために参照する場所を知る必要があります。</span><span class="sxs-lookup"><span data-stu-id="62d9c-113">You need to know the location to browse to for gaining Web access to your PeopleSoft system.</span></span> <span data-ttu-id="62d9c-114">必要としない[!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)]または他の Microsoft テクノロジです。</span><span class="sxs-lookup"><span data-stu-id="62d9c-114">You do not need [!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)] or any other Microsoft technologies.</span></span>  
  
## <a name="lab-1---using-a-peoplesoft-system"></a><span data-ttu-id="62d9c-115">ラボ 1 - PeopleSoft システムの使用</span><span class="sxs-lookup"><span data-stu-id="62d9c-115">Lab 1 - Using a PeopleSoft System</span></span>  
 <span data-ttu-id="62d9c-116">このラボでのすべてのコンポーネントを使用せず、PeopleSoft システムを使用する、[!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)]します。</span><span class="sxs-lookup"><span data-stu-id="62d9c-116">In this lab, you will use the PeopleSoft system without using any components of [!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)].</span></span> <span data-ttu-id="62d9c-117">目標は、2 番目のラボが正しく機能することを確認する PeopleSoft への接続をテストします。</span><span class="sxs-lookup"><span data-stu-id="62d9c-117">The goal is to test your connectivity to PeopleSoft to ensure that the second lab will work correctly.</span></span> <span data-ttu-id="62d9c-118">最初に Internet Explorer などのブラウザーを使用してログオンすることができる Web インターフェイスを介して PeopleSoft システムに接続します。</span><span class="sxs-lookup"><span data-stu-id="62d9c-118">Initially you connect to the PeopleSoft system through its Web interface that allows you to log on by using a browser such as Internet Explorer.</span></span>  
  
## <a name="procedures-for-lab-1---using-a-peoplesoft-system"></a><span data-ttu-id="62d9c-119">ラボ 1 - PeopleSoft システムの使用の手順</span><span class="sxs-lookup"><span data-stu-id="62d9c-119">Procedures for Lab 1 - Using a PeopleSoft System</span></span>  
  
#### <a name="to-log-on-to-peoplesoft-by-using-a-browser"></a><span data-ttu-id="62d9c-120">ブラウザーを使用して PeopleSoft にログオンするには</span><span class="sxs-lookup"><span data-stu-id="62d9c-120">To log on to PeopleSoft by using a browser</span></span>  
  
-   <span data-ttu-id="62d9c-121">PeopleSoft ログオン ページを参照して、PeopleSoft システムにログオンします。</span><span class="sxs-lookup"><span data-stu-id="62d9c-121">Log on to the PeopleSoft system by browsing to a PeopleSoft logon page.</span></span> <span data-ttu-id="62d9c-122">入力、**ユーザー ID**と**パスワード**順にクリックします**サインイン**します。</span><span class="sxs-lookup"><span data-stu-id="62d9c-122">Enter your **User ID** and **Password** and then click **Sign In**.</span></span>  
  
     <span data-ttu-id="62d9c-123">![](../core/media/1e3e5c0f-316b-4aa3-946e-3bb3665b0ddb.gif "1e3e5c0f-316b-4aa3-946e-3bb3665b0ddb")</span><span class="sxs-lookup"><span data-stu-id="62d9c-123">![](../core/media/1e3e5c0f-316b-4aa3-946e-3bb3665b0ddb.gif "1e3e5c0f-316b-4aa3-946e-3bb3665b0ddb")</span></span>  
  
#### <a name="to-locate-and-modify-peoplesoft-data"></a><span data-ttu-id="62d9c-124">PeopleSoft データを検索および変更</span><span class="sxs-lookup"><span data-stu-id="62d9c-124">To locate and modify PeopleSoft data</span></span>  
  
1.  <span data-ttu-id="62d9c-125">成功したログオンは、レイアウトを選択して表示するコンテンツを個人用に設定するページに配置します。</span><span class="sxs-lookup"><span data-stu-id="62d9c-125">A successful logon places you at the page to personalize the content you see by choosing its layout.</span></span> <span data-ttu-id="62d9c-126">下へスクロールし、展開**財務/サプライ チェーンの設定**、 をクリックして**共通定義**、 をクリックして**場所**、 をクリックし、**場所**もう一度です。</span><span class="sxs-lookup"><span data-stu-id="62d9c-126">Scroll down and expand **Set Up Financials/Supply Chain**, click **Common Definitions**, click **Location**, and then click **Location** again.</span></span> <span data-ttu-id="62d9c-127">表示、**場所**検索インターフェイス。</span><span class="sxs-lookup"><span data-stu-id="62d9c-127">This brings you to the **Location** search interface.</span></span>  
  
     <span data-ttu-id="62d9c-128">![](../core/media/62a89cd4-464c-42fd-91cd-60ceeab5b006.gif "62a89cd4-464c-42fd-91cd-60ceeab5b006")</span><span class="sxs-lookup"><span data-stu-id="62d9c-128">![](../core/media/62a89cd4-464c-42fd-91cd-60ceeab5b006.gif "62a89cd4-464c-42fd-91cd-60ceeab5b006")</span></span>  
  
2.  <span data-ttu-id="62d9c-129">検索を開始するには、次のように設定します**SetID**に **=** に設定して、**場所コード**に**で始まる**、入力 **、。**、 をクリックし、**検索**します。</span><span class="sxs-lookup"><span data-stu-id="62d9c-129">To begin the search, set **SetID** to **=**, set **Location Code** to **begins with**, enter **A**, and then click **Search**.</span></span> <span data-ttu-id="62d9c-130">A で始まる名前の都市が表示されます、**検索結果**インターフェイスのセクション。</span><span class="sxs-lookup"><span data-stu-id="62d9c-130">This displays cities whose names start with A in the **Search Results** section of the interface.</span></span>  
  
     <span data-ttu-id="62d9c-131">![](../core/media/86661144-c666-4d72-9227-9f17df715ba4.gif "86661144-c666-4d72-9227-9f17df715ba4")</span><span class="sxs-lookup"><span data-stu-id="62d9c-131">![](../core/media/86661144-c666-4d72-9227-9f17df715ba4.gif "86661144-c666-4d72-9227-9f17df715ba4")</span></span>  
  
3.  <span data-ttu-id="62d9c-132">詳細情報を取得する場所のいずれかをクリックします。</span><span class="sxs-lookup"><span data-stu-id="62d9c-132">Click one of the locations to get its detail information.</span></span> <span data-ttu-id="62d9c-133">たとえば、次の図に、ユーザー クリックして、 **AUS01**のリンクを**場所コード**列。</span><span class="sxs-lookup"><span data-stu-id="62d9c-133">For example, in the figure below, the user clicked the **AUS01** link in the **Location Code** column.</span></span>  
  
4.  <span data-ttu-id="62d9c-134">フィールドのいずれかに新しいデータを入力します (など、**アドレス 2**フィールド) をクリック**保存**左上隅にあります。</span><span class="sxs-lookup"><span data-stu-id="62d9c-134">Enter some new data into one of the fields (such as the **Address 2** field) and click **Save** in the lower-left corner.</span></span> <span data-ttu-id="62d9c-135">これにより、新しく入力したデータがレコードに保存します。</span><span class="sxs-lookup"><span data-stu-id="62d9c-135">This saves the newly entered data into the record.</span></span>  
  
     <span data-ttu-id="62d9c-136">![](../core/media/b6eb137c-c0b0-4906-8fbd-1bc036069fb0.gif "b6eb137c-c0b0-4906-8fbd-1bc036069fb0")</span><span class="sxs-lookup"><span data-stu-id="62d9c-136">![](../core/media/b6eb137c-c0b0-4906-8fbd-1bc036069fb0.gif "b6eb137c-c0b0-4906-8fbd-1bc036069fb0")</span></span>  
  
5.  <span data-ttu-id="62d9c-137">この変更の成功を確認し、手順 2 からプロセスを繰り返しますし、この同じレコードを見つけ、レコードに加え、変更を確認します。</span><span class="sxs-lookup"><span data-stu-id="62d9c-137">To verify the success of this change, repeat the process from step 2, find this same record again, and observe the changes made to the record.</span></span>  
  
6.  <span data-ttu-id="62d9c-138">ウィンドウの右上部分でクリックして**サインアウト**PeopleSoft セッションを終了します。</span><span class="sxs-lookup"><span data-stu-id="62d9c-138">In the upper-right portion of the window, click **Sign out** to end your PeopleSoft session.</span></span>  
  
     <span data-ttu-id="62d9c-139">![](../core/media/7760b541-5155-453e-a682-4780412f3c13.gif "7760b541-5155-453e-a682-4780412f3c13")</span><span class="sxs-lookup"><span data-stu-id="62d9c-139">![](../core/media/7760b541-5155-453e-a682-4780412f3c13.gif "7760b541-5155-453e-a682-4780412f3c13")</span></span>  
  
    > [!NOTE]
    >  <span data-ttu-id="62d9c-140">次の実習では、PeopleSoft アダプターを使用して、変更した場所レコード (AUS01) の情報を取得するための手順。</span><span class="sxs-lookup"><span data-stu-id="62d9c-140">In the next lab there are instructions for using the PeopleSoft adapter to retrieve the information for the location record (AUS01) that you modified.</span></span>  
  
## <a name="summary"></a><span data-ttu-id="62d9c-141">まとめ</span><span class="sxs-lookup"><span data-stu-id="62d9c-141">Summary</span></span>  
 <span data-ttu-id="62d9c-142">このラボでログオンして、ブラウザーを介して PeopleSoft システムにします。</span><span class="sxs-lookup"><span data-stu-id="62d9c-142">In this lab you logged on to the PeopleSoft system through a browser.</span></span> <span data-ttu-id="62d9c-143">、接続された後、データの検索し操作し、レコードのアドレス フィールドを更新します。</span><span class="sxs-lookup"><span data-stu-id="62d9c-143">After you were connected, you searched for data, and then manipulated and updated a record's address field.</span></span> <span data-ttu-id="62d9c-144">変更をコミットした後でしたデータを表示する変更されたことを確認するには、ブラウザーで適切に実行された変更。</span><span class="sxs-lookup"><span data-stu-id="62d9c-144">After committing the change, you could view the modified data in the browser to verify that the change executed properly.</span></span>