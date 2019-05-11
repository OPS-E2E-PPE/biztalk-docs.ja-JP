---
title: JD Edwards OneWorld システムの使用 |Microsoft Docs
ms.custom: ''
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: ''
ms.suite: ''
ms.tgt_pltfrm: ''
ms.topic: article
ms.assetid: 5346aa04-ebd7-4545-9062-b349fd73b7f1
caps.latest.revision: 15
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: 0fb7bdef551f0ceb66e8eea5ea1fe073bd0bca72
ms.sourcegitcommit: 381e83d43796a345488d54b3f7413e11d56ad7be
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 05/07/2019
ms.locfileid: "65399925"
---
# <a name="using-a-jd-edwards-oneworld-system"></a><span data-ttu-id="73c0c-102">JD Edwards OneWorld システムの使用</span><span class="sxs-lookup"><span data-stu-id="73c0c-102">Using a JD Edwards OneWorld System</span></span>
<span data-ttu-id="73c0c-103">JD Edwards OneWorld システムはからアクセスできる、 [!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)] JD Edwards OneWorld アダプターを使用してシステム。</span><span class="sxs-lookup"><span data-stu-id="73c0c-103">The JD Edwards OneWorld system is accessible from a [!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)] system by using the JD Edwards OneWorld adapter.</span></span> <span data-ttu-id="73c0c-104">このアダプターは、Microsoft が [!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)]用に提供する 8 つの基幹業務 (LOB) アダプターの 1 つです。</span><span class="sxs-lookup"><span data-stu-id="73c0c-104">This adapter is one of a group of eight line-of-business (LOB) adapters shipped by Microsoft for use with [!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)].</span></span>  
  
 <span data-ttu-id="73c0c-105">JD Edwards OneWorld ラボ作業は、2 つの部分に分かれています。</span><span class="sxs-lookup"><span data-stu-id="73c0c-105">The JD Edwards OneWorld lab work is divided into two parts.</span></span> <span data-ttu-id="73c0c-106">この最初のラボ (ラボ 1) では、JD Edwards OneWorld システムをしなくても使用できます。[!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)]などの Microsoft 製品です。</span><span class="sxs-lookup"><span data-stu-id="73c0c-106">This first lab (Lab 1) allows you to use the JD Edwards OneWorld system without needing [!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)] or any Microsoft products.</span></span> <span data-ttu-id="73c0c-107">JD Edwards OneWorld データベースに接続し、アドレスに基づいて特定のレコードを検索するには、JD Edwards OneWorld クライアント ツールは使用します。</span><span class="sxs-lookup"><span data-stu-id="73c0c-107">You will use the JD Edwards OneWorld Client tool to connect to a JD Edwards OneWorld database and locate a specific record based upon address.</span></span>  
  
 <span data-ttu-id="73c0c-108">2 番目のラボ (ラボ 2) では、BizTalk プロジェクトおよびオーケストレーションを作成します。</span><span class="sxs-lookup"><span data-stu-id="73c0c-108">In the second lab (Lab 2), you will create a BizTalk project and orchestration.</span></span> <span data-ttu-id="73c0c-109">アプリケーションを作成した後は、デプロイし、JD Edwards OneWorld アダプターを使用して JD Edwards OneWorld システムへの接続に使用されます。</span><span class="sxs-lookup"><span data-stu-id="73c0c-109">After you create the application, you will deploy it and use it to connect to a JD Edwards OneWorld system by using the JD Edwards OneWorld adapter.</span></span> <span data-ttu-id="73c0c-110">目標は、アダプターを使用して BizTalk アプリケーションを介してデータにアクセスします。</span><span class="sxs-lookup"><span data-stu-id="73c0c-110">The goal is to access data through the BizTalk application by using the adapter.</span></span>  
  
## <a name="prerequisites"></a><span data-ttu-id="73c0c-111">前提条件</span><span class="sxs-lookup"><span data-stu-id="73c0c-111">Prerequisites</span></span>  
 <span data-ttu-id="73c0c-112">このラボの手順を実行するには、JD Edwards OneWorld クライアント ソフトウェアと最新の更新プログラムをインストールする必要があります。</span><span class="sxs-lookup"><span data-stu-id="73c0c-112">To perform the procedures for this lab, you need to install the JD Edwards OneWorld client software and its latest update.</span></span> <span data-ttu-id="73c0c-113">クライアントのソフトウェア ツールを使用するには、JD Edwards OneWorld データベース、そのデータベースとそのシステム上のユーザー アカウントへのネットワーク接続を必要があります。</span><span class="sxs-lookup"><span data-stu-id="73c0c-113">To use any of the client software tools you will need a JD Edwards OneWorld database, network connectivity to that database, and a user account on that system.</span></span> <span data-ttu-id="73c0c-114">必要としない[!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)]この演習を完了します。</span><span class="sxs-lookup"><span data-stu-id="73c0c-114">You do not need [!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)] to complete this lab.</span></span>  
  
## <a name="lab-1---using-a-jd-edwards-oneworld-system"></a><span data-ttu-id="73c0c-115">ラボ 1 - JD Edwards OneWorld システムの使用</span><span class="sxs-lookup"><span data-stu-id="73c0c-115">Lab 1 - Using a JD Edwards OneWorld System</span></span>  
 <span data-ttu-id="73c0c-116">この演習では、すべてのコンポーネントを使用せず、JD Edwards OneWorld システムを使用します[!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)]します。</span><span class="sxs-lookup"><span data-stu-id="73c0c-116">In this lab, you will use the JD Edwards OneWorld system without using any components of [!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)].</span></span> <span data-ttu-id="73c0c-117">目標は、JD Edwards OneWorld への接続をテストし、2 番目のラボが正しく機能することを確認します。</span><span class="sxs-lookup"><span data-stu-id="73c0c-117">The goals are to test your connectivity to JD Edwards OneWorld and to ensure that the second lab will work correctly.</span></span> <span data-ttu-id="73c0c-118">JD Edwards OneWorld SQL Plus ツールを使用して、作成し、JD Edwards OneWorld データベース内のデータ テーブルを操作します。</span><span class="sxs-lookup"><span data-stu-id="73c0c-118">You will use the JD Edwards OneWorld SQL Plus tool to create and manipulate a data table in a JD Edwards OneWorld database.</span></span>  
  
## <a name="procedures-for-lab-1---using-a-jd-edwards-oneworld-system"></a><span data-ttu-id="73c0c-119">ラボ 1 - JD Edwards OneWorld システムの使用の手順</span><span class="sxs-lookup"><span data-stu-id="73c0c-119">Procedures for Lab 1 - Using a JD Edwards OneWorld System</span></span>  
  
#### <a name="to-log-on-to-jd-edwards-oneworld-by-using-a-browser"></a><span data-ttu-id="73c0c-120">ブラウザーを使用して JD Edwards OneWorld にログオンするには</span><span class="sxs-lookup"><span data-stu-id="73c0c-120">To log on to JD Edwards OneWorld by using a browser</span></span>  
  
-   <span data-ttu-id="73c0c-121">JD Edwards OneWorld アイコンをクリックして、JD Edwards OneWorld システムにログオンします。</span><span class="sxs-lookup"><span data-stu-id="73c0c-121">Log on to the JD Edwards OneWorld system by clicking the JD Edwards OneWorld icon.</span></span> <span data-ttu-id="73c0c-122">入力、**ユーザー ID**、**パスワード**と**環境**、順にクリックします**OK**します。</span><span class="sxs-lookup"><span data-stu-id="73c0c-122">Enter your **User ID**, **Password**, and **Environment**, and then click **OK**.</span></span>  
  
     <span data-ttu-id="73c0c-123">![](../core/media/f04db2ef-d587-4357-b9e8-c96319886e97.gif "f04db2ef-d587-4357-b9e8-c96319886e97")</span><span class="sxs-lookup"><span data-stu-id="73c0c-123">![](../core/media/f04db2ef-d587-4357-b9e8-c96319886e97.gif "f04db2ef-d587-4357-b9e8-c96319886e97")</span></span>  
  
#### <a name="to-locate-and-view-jd-edwards-oneworld-data"></a><span data-ttu-id="73c0c-124">検索して JD Edwards OneWorld のデータを表示するには</span><span class="sxs-lookup"><span data-stu-id="73c0c-124">To locate and view JD Edwards OneWorld data</span></span>  
  
1.  <span data-ttu-id="73c0c-125">成功したログオンを配置するには**JD Edwards OneWorld Explorer**します。</span><span class="sxs-lookup"><span data-stu-id="73c0c-125">A successful logon places you at the **JD Edwards OneWorld Explorer**.</span></span>  
  
     <span data-ttu-id="73c0c-126">![](../core/media/14e8c206-7e38-48f8-9108-e32a7ac9a740.gif "14e8c206-7e38-48f8-9108-e32a7ac9a740")</span><span class="sxs-lookup"><span data-stu-id="73c0c-126">![](../core/media/14e8c206-7e38-48f8-9108-e32a7ac9a740.gif "14e8c206-7e38-48f8-9108-e32a7ac9a740")</span></span>  
  
2.  <span data-ttu-id="73c0c-127">展開**Master Directory**、し**Foundation Systems**、し**アドレス帳**、し**毎日処理**。</span><span class="sxs-lookup"><span data-stu-id="73c0c-127">Expand **Master Directory**, then **Foundation Systems**, then **Address Book**, and then **Daily Processing**.</span></span>  
  
     <span data-ttu-id="73c0c-128">![](../core/media/1f742221-00e5-4697-95ff-64aa63ed567a.gif "1f742221-00e5-4697-95ff-64aa63ed567a")</span><span class="sxs-lookup"><span data-stu-id="73c0c-128">![](../core/media/1f742221-00e5-4697-95ff-64aa63ed567a.gif "1f742221-00e5-4697-95ff-64aa63ed567a")</span></span>  
  
3.  <span data-ttu-id="73c0c-129">右側のウィンドウでダブルクリック**Address Book Revisions**します。</span><span class="sxs-lookup"><span data-stu-id="73c0c-129">In the right-hand window, double-click **Address Book Revisions**.</span></span>  
  
     <span data-ttu-id="73c0c-130">![](../core/media/a6d4e871-9c9c-4bc0-9c4f-4bdfd7cc5031.gif "a6d4e871-9c9c-4bc0-9c4f-4bdfd7cc5031")</span><span class="sxs-lookup"><span data-stu-id="73c0c-130">![](../core/media/a6d4e871-9c9c-4bc0-9c4f-4bdfd7cc5031.gif "a6d4e871-9c9c-4bc0-9c4f-4bdfd7cc5031")</span></span>  
  
4.  <span data-ttu-id="73c0c-131">**Alpha Name**、入力`Ga`を選択します、**表示アドレス**チェック ボックスをオンにして**検索**ツールバーの。</span><span class="sxs-lookup"><span data-stu-id="73c0c-131">For **Alpha Name**, enter `Ga`, select the **Display Address** check box, and then click **Find** on the toolbar.</span></span>  
  
     <span data-ttu-id="73c0c-132">![](../core/media/2f58413f-41a9-4ed9-ba5c-1d6d59eafb01.gif "2f58413f-41a9-4ed9-ba5c-1d6d59eafb01")</span><span class="sxs-lookup"><span data-stu-id="73c0c-132">![](../core/media/2f58413f-41a9-4ed9-ba5c-1d6d59eafb01.gif "2f58413f-41a9-4ed9-ba5c-1d6d59eafb01")</span></span>  
  
     <span data-ttu-id="73c0c-133">**Address Book Revisions - [Work With Addresses]** ダイアログ ボックスで、検索結果として 2 つのレコードが表示されます。</span><span class="sxs-lookup"><span data-stu-id="73c0c-133">In the **Address Book Revisions - [Work With Addresses]** dialog box, two records are displayed as a result of the search.</span></span>  
  
     <span data-ttu-id="73c0c-134">![](../core/media/9284df4e-ca9b-48ab-b2bf-a90d765d4a05.gif "9284df4e-ca9b-48ab-b2bf-a90d765d4a05")</span><span class="sxs-lookup"><span data-stu-id="73c0c-134">![](../core/media/9284df4e-ca9b-48ab-b2bf-a90d765d4a05.gif "9284df4e-ca9b-48ab-b2bf-a90d765d4a05")</span></span>  
  
     <span data-ttu-id="73c0c-135">オフにする代替のデータを検索する方法は、 **Alpha Name**フィールドに、上記のテキスト ボックス内をクリックして、**アドレス番号**列、入力と`500`します。</span><span class="sxs-lookup"><span data-stu-id="73c0c-135">An alternative method of locating data is to clear the **Alpha Name** field, click in the text box above the **Address Number** column, and enter `500`.</span></span> <span data-ttu-id="73c0c-136">クリックして**検索**ツールバーの検索結果を表示します。</span><span class="sxs-lookup"><span data-stu-id="73c0c-136">Click **Find** on the toolbar to display the search results.</span></span>  
  
     <span data-ttu-id="73c0c-137">![](../core/media/a88bd867-9a16-416a-a43e-cdfcc65fc670.gif "a88bd867-9a16-416a-a43e-cdfcc65fc670")</span><span class="sxs-lookup"><span data-stu-id="73c0c-137">![](../core/media/a88bd867-9a16-416a-a43e-cdfcc65fc670.gif "a88bd867-9a16-416a-a43e-cdfcc65fc670")</span></span>  
  
     <span data-ttu-id="73c0c-138">ラボ 2 でがありますを JD Edwards OneWorld アダプターを使用して情報を取得する手順については、**アドレス番号**の`500`します。</span><span class="sxs-lookup"><span data-stu-id="73c0c-138">In Lab 2, there will be instructions for using the JD Edwards OneWorld adapter to retrieve the information for an **Address Number** of `500`.</span></span>  
  
5.  <span data-ttu-id="73c0c-139">**ファイル** メニューのをクリックして**終了**JE Edwards OneWorld クライアント セッションを終了します。</span><span class="sxs-lookup"><span data-stu-id="73c0c-139">On the **File** menu, click **Exit** to exit the JE Edwards OneWorld Client session.</span></span>  
  
## <a name="summary"></a><span data-ttu-id="73c0c-140">まとめ</span><span class="sxs-lookup"><span data-stu-id="73c0c-140">Summary</span></span>  
 <span data-ttu-id="73c0c-141">この演習では、JD Edwards OneWorld クライアント ツールを使用して JD Edwards OneWorld システムにログオンします。</span><span class="sxs-lookup"><span data-stu-id="73c0c-141">In this lab, you used the JD Edwards OneWorld Client tool to log on to the JD Edwards OneWorld system.</span></span> <span data-ttu-id="73c0c-142">、接続された後は、特定のデータを検索し、返されるデータ レコードを表示します。</span><span class="sxs-lookup"><span data-stu-id="73c0c-142">After you were connected, you searched for specific data and viewed the data records returned.</span></span>