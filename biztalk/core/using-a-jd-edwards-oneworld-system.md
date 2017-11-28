---
title: "JD Edwards OneWorld システムを使用して |Microsoft ドキュメント"
ms.custom: 
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: 
ms.suite: 
ms.tgt_pltfrm: 
ms.topic: article
ms.assetid: 5346aa04-ebd7-4545-9062-b349fd73b7f1
caps.latest.revision: "15"
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: 835432e50bce3f347e6f769fb8182ab35fc4f949
ms.sourcegitcommit: cb908c540d8f1a692d01dc8f313e16cb4b4e696d
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 09/20/2017
---
# <a name="using-a-jd-edwards-oneworld-system"></a><span data-ttu-id="8801f-102">JD Edwards OneWorld システムの使用</span><span class="sxs-lookup"><span data-stu-id="8801f-102">Using a JD Edwards OneWorld System</span></span>
<span data-ttu-id="8801f-103">JD Edwards OneWorld システムに [!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)] システムからアクセスするには、JD Edwards OneWorld アダプターを使用します。</span><span class="sxs-lookup"><span data-stu-id="8801f-103">The JD Edwards OneWorld system is accessible from a [!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)] system by using the JD Edwards OneWorld adapter.</span></span> <span data-ttu-id="8801f-104">このアダプターは、Microsoft が [!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)] 用に提供する 8 つの基幹業務 (LOB) アダプターの 1 つです。</span><span class="sxs-lookup"><span data-stu-id="8801f-104">This adapter is one of a group of eight line-of-business (LOB) adapters shipped by Microsoft for use with [!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)].</span></span>  
  
 <span data-ttu-id="8801f-105">JD Edwards OneWorld ラボ作業は 2 つのパートに分かれています。</span><span class="sxs-lookup"><span data-stu-id="8801f-105">The JD Edwards OneWorld lab work is divided into two parts.</span></span> <span data-ttu-id="8801f-106">この最初のラボ (ラボ 1) では、JD Edwards OneWorld システムを使用しますが、[!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)] などの Microsoft 製品はなくてもかまいません。</span><span class="sxs-lookup"><span data-stu-id="8801f-106">This first lab (Lab 1) allows you to use the JD Edwards OneWorld system without needing [!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)] or any Microsoft products.</span></span> <span data-ttu-id="8801f-107">JD Edwards OneWorld クライアント ツールを使用して JD Edwards OneWorld データベースに接続し、アドレスに基づいて特定のレコードを見つけます。</span><span class="sxs-lookup"><span data-stu-id="8801f-107">You will use the JD Edwards OneWorld Client tool to connect to a JD Edwards OneWorld database and locate a specific record based upon address.</span></span>  
  
 <span data-ttu-id="8801f-108">2 番目のラボ (ラボ 2) では、BizTalk プロジェクトおよびオーケストレーションを作成します。</span><span class="sxs-lookup"><span data-stu-id="8801f-108">In the second lab (Lab 2), you will create a BizTalk project and orchestration.</span></span> <span data-ttu-id="8801f-109">アプリケーションを作成したら、アプリケーションを展開し、JD Edwards OneWorld アダプターを使用して JD Edwards OneWorld システムに接続します。</span><span class="sxs-lookup"><span data-stu-id="8801f-109">After you create the application, you will deploy it and use it to connect to a JD Edwards OneWorld system by using the JD Edwards OneWorld adapter.</span></span> <span data-ttu-id="8801f-110">目標は、アダプターを使用して BizTalk アプリケーションを介してデータにアクセスすることです。</span><span class="sxs-lookup"><span data-stu-id="8801f-110">The goal is to access data through the BizTalk application by using the adapter.</span></span>  
  
## <a name="prerequisites"></a><span data-ttu-id="8801f-111">前提条件</span><span class="sxs-lookup"><span data-stu-id="8801f-111">Prerequisites</span></span>  
 <span data-ttu-id="8801f-112">このラボの手順を実行するには、JD Edwards OneWorld クライアント ソフトウェアと最新の更新プログラムをインストールする必要があります。</span><span class="sxs-lookup"><span data-stu-id="8801f-112">To perform the procedures for this lab, you need to install the JD Edwards OneWorld client software and its latest update.</span></span> <span data-ttu-id="8801f-113">クライアント ソフトウェア ツールを使用するには、JD Edwards OneWorld データベースと、このデータベースへのネットワーク接続、およびそのシステムでのユーザー アカウントが必要です。</span><span class="sxs-lookup"><span data-stu-id="8801f-113">To use any of the client software tools you will need a JD Edwards OneWorld database, network connectivity to that database, and a user account on that system.</span></span> <span data-ttu-id="8801f-114">このラボでは、[!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)] はなくてもかまいません。</span><span class="sxs-lookup"><span data-stu-id="8801f-114">You do not need [!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)] to complete this lab.</span></span>  
  
## <a name="lab-1---using-a-jd-edwards-oneworld-system"></a><span data-ttu-id="8801f-115">ラボ 1 - JD Edwards OneWorld システムを使用する</span><span class="sxs-lookup"><span data-stu-id="8801f-115">Lab 1 - Using a JD Edwards OneWorld System</span></span>  
 <span data-ttu-id="8801f-116">このラボでは、[!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)] のコンポーネントは一切使用せずに JD Edwards OneWorld システムを使用します。</span><span class="sxs-lookup"><span data-stu-id="8801f-116">In this lab, you will use the JD Edwards OneWorld system without using any components of [!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)].</span></span> <span data-ttu-id="8801f-117">目標は、JD Edwards OneWorld への接続のテストと、2 番目のラボが適切に動作する環境であることの確認です。</span><span class="sxs-lookup"><span data-stu-id="8801f-117">The goals are to test your connectivity to JD Edwards OneWorld and to ensure that the second lab will work correctly.</span></span> <span data-ttu-id="8801f-118">JD Edwards OneWorld データベース内のデータ テーブルの作成と操作には、JD Edwards OneWorld SQL Plus ツールを使用します。</span><span class="sxs-lookup"><span data-stu-id="8801f-118">You will use the JD Edwards OneWorld SQL Plus tool to create and manipulate a data table in a JD Edwards OneWorld database.</span></span>  
  
## <a name="procedures-for-lab-1---using-a-jd-edwards-oneworld-system"></a><span data-ttu-id="8801f-119">ラボ 1 の手順 - JD Edwards OneWorld システムを使用する</span><span class="sxs-lookup"><span data-stu-id="8801f-119">Procedures for Lab 1 - Using a JD Edwards OneWorld System</span></span>  
  
#### <a name="to-log-on-to-jd-edwards-oneworld-by-using-a-browser"></a><span data-ttu-id="8801f-120">ブラウザーを使用して JD Edwards OneWorld にログインするには</span><span class="sxs-lookup"><span data-stu-id="8801f-120">To log on to JD Edwards OneWorld by using a browser</span></span>  
  
-   <span data-ttu-id="8801f-121">JD Edwards OneWorld システムにログインするには、JD Edwards OneWorld アイコンをクリックします。</span><span class="sxs-lookup"><span data-stu-id="8801f-121">Log on to the JD Edwards OneWorld system by clicking the JD Edwards OneWorld icon.</span></span> <span data-ttu-id="8801f-122">入力してください、**ユーザー ID**、**パスワード**、および**環境**、順にクリック**OK**です。</span><span class="sxs-lookup"><span data-stu-id="8801f-122">Enter your **User ID**, **Password**, and **Environment**, and then click **OK**.</span></span>  
  
     ![](../core/media/f04db2ef-d587-4357-b9e8-c96319886e97.gif "f04db2ef-d587-4357-b9e8-c96319886e97")  
  
#### <a name="to-locate-and-view-jd-edwards-oneworld-data"></a><span data-ttu-id="8801f-123">JD Edwards OneWorld のデータを見つけて表示するには</span><span class="sxs-lookup"><span data-stu-id="8801f-123">To locate and view JD Edwards OneWorld data</span></span>  
  
1.  <span data-ttu-id="8801f-124">成功したログオンを配置するには**JD Edwards OneWorld Explorer**です。</span><span class="sxs-lookup"><span data-stu-id="8801f-124">A successful logon places you at the **JD Edwards OneWorld Explorer**.</span></span>  
  
     ![](../core/media/14e8c206-7e38-48f8-9108-e32a7ac9a740.gif "14e8c206-7e38-48f8-9108-e32a7ac9a740")  
  
2.  <span data-ttu-id="8801f-125">展開**Master Directory**、し**Foundation Systems**、し**アドレス帳**、し**毎日の処理**です。</span><span class="sxs-lookup"><span data-stu-id="8801f-125">Expand **Master Directory**, then **Foundation Systems**, then **Address Book**, and then **Daily Processing**.</span></span>  
  
     ![](../core/media/1f742221-00e5-4697-95ff-64aa63ed567a.gif "1f742221-00e5-4697-95ff-64aa63ed567a")  
  
3.  <span data-ttu-id="8801f-126">右側のウィンドウをダブルクリック**Address Book Revisions**です。</span><span class="sxs-lookup"><span data-stu-id="8801f-126">In the right-hand window, double-click **Address Book Revisions**.</span></span>  
  
     ![](../core/media/a6d4e871-9c9c-4bc0-9c4f-4bdfd7cc5031.gif "a6d4e871-9c9c-4bc0-9c4f-4bdfd7cc5031")  
  
4.  <span data-ttu-id="8801f-127">**Alpha Name**、入力`Ga`を選択、**表示アドレス**チェック ボックスをオンし、をクリックして**検索**ツールバーのです。</span><span class="sxs-lookup"><span data-stu-id="8801f-127">For **Alpha Name**, enter `Ga`, select the **Display Address** check box, and then click **Find** on the toolbar.</span></span>  
  
     ![](../core/media/2f58413f-41a9-4ed9-ba5c-1d6d59eafb01.gif "2f58413f-41a9-4ed9-ba5c-1d6d59eafb01")  
  
     <span data-ttu-id="8801f-128">**Address Book Revisions - [Work With Addresses]**ダイアログ ボックスで、2 つのレコードが、検索結果として表示されます。</span><span class="sxs-lookup"><span data-stu-id="8801f-128">In the **Address Book Revisions - [Work With Addresses]** dialog box, two records are displayed as a result of the search.</span></span>  
  
     ![](../core/media/9284df4e-ca9b-48ab-b2bf-a90d765d4a05.gif "9284df4e-ca9b-48ab-b2bf-a90d765d4a05")  
  
     <span data-ttu-id="8801f-129">オフには、データを検索する代替方法、 **Alpha Name**フィールドに、上のテキスト ボックス内をクリックして、**アドレス番号**列、入力と`500`です。</span><span class="sxs-lookup"><span data-stu-id="8801f-129">An alternative method of locating data is to clear the **Alpha Name** field, click in the text box above the **Address Number** column, and enter `500`.</span></span> <span data-ttu-id="8801f-130">をクリックして**検索**ツールバーの検索結果を表示します。</span><span class="sxs-lookup"><span data-stu-id="8801f-130">Click **Find** on the toolbar to display the search results.</span></span>  
  
     ![](../core/media/a88bd867-9a16-416a-a43e-cdfcc65fc670.gif "a88bd867-9a16-416a-a43e-cdfcc65fc670")  
  
     <span data-ttu-id="8801f-131">ラボ 2 でがあります、JD Edwards OneWorld アダプターを使用して情報を取得するための指示、**アドレス番号**の`500`します。</span><span class="sxs-lookup"><span data-stu-id="8801f-131">In Lab 2, there will be instructions for using the JD Edwards OneWorld adapter to retrieve the information for an **Address Number** of `500`.</span></span>  
  
5.  <span data-ttu-id="8801f-132">**ファイル** メニューのをクリックして**終了**では Edwards OneWorld クライアント セッションを終了します。</span><span class="sxs-lookup"><span data-stu-id="8801f-132">On the **File** menu, click **Exit** to exit the JE Edwards OneWorld Client session.</span></span>  
  
## <a name="summary"></a><span data-ttu-id="8801f-133">概要</span><span class="sxs-lookup"><span data-stu-id="8801f-133">Summary</span></span>  
 <span data-ttu-id="8801f-134">このラボでは、JD Edwards OneWorld クライアント ツールを使用して JD Edwards OneWorld システムにログインしました。</span><span class="sxs-lookup"><span data-stu-id="8801f-134">In this lab, you used the JD Edwards OneWorld Client tool to log on to the JD Edwards OneWorld system.</span></span> <span data-ttu-id="8801f-135">システムに接続した後で、特定のデータを検索して返されたデータ レコードを表示しました。</span><span class="sxs-lookup"><span data-stu-id="8801f-135">After you were connected, you searched for specific data and viewed the data records returned.</span></span>