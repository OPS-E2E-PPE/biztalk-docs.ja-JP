---
title: "マッピング ウィザードを使用する方法 |Microsoft ドキュメント"
ms.custom: 
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: 
ms.suite: 
ms.tgt_pltfrm: 
ms.topic: article
ms.assetid: 35b96cea-ead7-43de-8411-62d2c7d6620e
caps.latest.revision: "3"
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: a6b016eb0599924d4927868b6a19d3b57389e5c9
ms.sourcegitcommit: cb908c540d8f1a692d01dc8f313e16cb4b4e696d
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 09/20/2017
---
# <a name="how-to-use-the-mapping-wizard"></a><span data-ttu-id="ef77c-102">マッピング ウィザードの使用方法</span><span class="sxs-lookup"><span data-stu-id="ef77c-102">How to Use the Mapping Wizard</span></span>
<span data-ttu-id="ef77c-103">このバージョンのエンタープライズ シングル サインオンには、関連アプリケーションのマッピングを簡単に作成できるマッピング ウィザードが含まれています。</span><span class="sxs-lookup"><span data-stu-id="ef77c-103">This version of Enterprise Single Sign-On includes the Mapping Wizard, which allows you to easily create mappings for affiliate applications.</span></span>  
  
> [!NOTE]
>  <span data-ttu-id="ef77c-104">マッピング ウィザードは、外部ユーザー ID が Windows ドメイン アカウントに基づいている場合にのみ使用できます。</span><span class="sxs-lookup"><span data-stu-id="ef77c-104">You can only use the Mapping Wizard if the External UserID is based on the Windows domain account.</span></span>  
  
### <a name="to-start-the-mapping-wizard"></a><span data-ttu-id="ef77c-105">マッピング ウィザードを開始するには</span><span class="sxs-lookup"><span data-stu-id="ef77c-105">To start the Mapping Wizard</span></span>  
  
1.  <span data-ttu-id="ef77c-106">エンタープライズ シングル サインオンを開きます。</span><span class="sxs-lookup"><span data-stu-id="ef77c-106">Open Enterprise Single Sign-On.</span></span>  
  
2.  <span data-ttu-id="ef77c-107">スコープ ペインで、をクリックして**関連アプリケーション**です。</span><span class="sxs-lookup"><span data-stu-id="ef77c-107">In the scope pane, click **Affiliate Applications**.</span></span>  
  
3.  <span data-ttu-id="ef77c-108">対象の関連アプリケーションを右クリックします。</span><span class="sxs-lookup"><span data-stu-id="ef77c-108">Right click the appropriate affiliate application.</span></span>  
  
4.  <span data-ttu-id="ef77c-109">をクリックして**マッピングを作成する**です。</span><span class="sxs-lookup"><span data-stu-id="ef77c-109">Click **Create Mappings**.</span></span> <span data-ttu-id="ef77c-110">マッピング ウィザードが表示されます。</span><span class="sxs-lookup"><span data-stu-id="ef77c-110">The Mapping Wizard appears.</span></span>  
  
5.  <span data-ttu-id="ef77c-111">**マッピング ウィザードへようこそ**</span><span class="sxs-lookup"><span data-stu-id="ef77c-111">**Welcome to the Mapping Wizard**</span></span>  
  
    -   <span data-ttu-id="ef77c-112">これが正しい関連アプリケーションであることを確認し、をクリックして**次**です。</span><span class="sxs-lookup"><span data-stu-id="ef77c-112">Verify that this is the correct affiliate application, and click **Next**.</span></span>  
  
6.  <span data-ttu-id="ef77c-113">**マッピング ファイル オプション**ページ</span><span class="sxs-lookup"><span data-stu-id="ef77c-113">**Mappings File Option** page</span></span>  
  
    -   <span data-ttu-id="ef77c-114">ENTSSO では、XML ファイルを通じてマッピングを管理します。</span><span class="sxs-lookup"><span data-stu-id="ef77c-114">ENTSSO manages mappings through an XML file.</span></span> <span data-ttu-id="ef77c-115">新しいファイルを作成するか、既存のファイルを使用するかを選択できます。</span><span class="sxs-lookup"><span data-stu-id="ef77c-115">You can choose to create a new file or use an existing one.</span></span>  
  
7.  <span data-ttu-id="ef77c-116">**ファイルの場所**ページ</span><span class="sxs-lookup"><span data-stu-id="ef77c-116">**Files Location** page</span></span>  
  
    -   <span data-ttu-id="ef77c-117">使用するファイルを選択します。</span><span class="sxs-lookup"><span data-stu-id="ef77c-117">Select the files to be used.</span></span>  
  
    -   <span data-ttu-id="ef77c-118">クリックする必要があります**検証**を続行する前にファイルを検証します。</span><span class="sxs-lookup"><span data-stu-id="ef77c-118">You must click **Validate** to validate the files before proceeding.</span></span> <span data-ttu-id="ef77c-119">検証の状態が表示されます、**ステータス**ウィンドウです。</span><span class="sxs-lookup"><span data-stu-id="ef77c-119">The validation status appears in the **Status** window.</span></span>  
  
8.  <span data-ttu-id="ef77c-120">**アカウント**ページ</span><span class="sxs-lookup"><span data-stu-id="ef77c-120">**Accounts** page</span></span>  
  
    -   <span data-ttu-id="ef77c-121">新しいマッピング ファイルを生成しをクリックしてアカウントを 1 つまたは複数選択**検証**です。</span><span class="sxs-lookup"><span data-stu-id="ef77c-121">Choose one or more accounts to generate the new mappings file, and click **Validate**.</span></span>  
  
9. <span data-ttu-id="ef77c-122">**外部のユーザー名**ページ</span><span class="sxs-lookup"><span data-stu-id="ef77c-122">**External User Name** page</span></span>  
  
    -   <span data-ttu-id="ef77c-123">Windows ユーザー アカウントから外部ユーザー名を生成する方法を定義します。</span><span class="sxs-lookup"><span data-stu-id="ef77c-123">Define how the external user name is generated from the Windows user account.</span></span> <span data-ttu-id="ef77c-124">ボックスで選択するとわかりますで名前がどのように表示されるか、**例**ボックス。</span><span class="sxs-lookup"><span data-stu-id="ef77c-124">As you make selections in the boxes, you can see how the names will appear in the **Example** box.</span></span>  
  
10. <span data-ttu-id="ef77c-125">**生成**ページ</span><span class="sxs-lookup"><span data-stu-id="ef77c-125">**Generate** page</span></span>  
  
    -   <span data-ttu-id="ef77c-126">をクリックして**開始**マッピング ファイルを生成します。</span><span class="sxs-lookup"><span data-stu-id="ef77c-126">Click **Start** to generate the mappings file.</span></span> <span data-ttu-id="ef77c-127">(マッピングが作成される前に、必要に応じて、次のページでファイルを表示または編集できます)。結果は下の 3 つのウィンドウに表示されます。</span><span class="sxs-lookup"><span data-stu-id="ef77c-127">(You will have an opportunity on the next page to view or edit the file as necessary before mappings are created.) Results are displayed in the three windows below.</span></span>  
  
    -   <span data-ttu-id="ef77c-128">**数**で選択したアカウントのマッピングののでは概数、アカウントは、他のアカウントで入れ子にすることがあります。</span><span class="sxs-lookup"><span data-stu-id="ef77c-128">The **Number** of mappings in selected accounts is an approximation, because accounts may be nested in other accounts.</span></span>  
  
    -   <span data-ttu-id="ef77c-129">をクリックして**ログ ファイルの表示**を調べるエラーまたは警告が発生した可能性があります。</span><span class="sxs-lookup"><span data-stu-id="ef77c-129">Click **View Log File** to examine any errors or warnings that might have occurred.</span></span>  
  
11. <span data-ttu-id="ef77c-130">**オプション**ページ</span><span class="sxs-lookup"><span data-stu-id="ef77c-130">**Options** page</span></span>  
  
    -   <span data-ttu-id="ef77c-131">ファイルが作成されました。</span><span class="sxs-lookup"><span data-stu-id="ef77c-131">Your file has been created.</span></span> <span data-ttu-id="ef77c-132">をクリックして**View/edit Mappings File**必要な場合です。</span><span class="sxs-lookup"><span data-stu-id="ef77c-132">Click **View/Edit Mappings File** if desired.</span></span>  
  
    -   <span data-ttu-id="ef77c-133">をクリックして**マッピングを有効にする**する場合は、マッピングを自動的に有効にします。</span><span class="sxs-lookup"><span data-stu-id="ef77c-133">Click **Enable mappings** if you want the mappings to be automatically enabled.</span></span> <span data-ttu-id="ef77c-134">(これをクリックしない場合、手動で有効にする必要があります)。</span><span class="sxs-lookup"><span data-stu-id="ef77c-134">(If you do not click this, you will have to enable them manually.)</span></span>  
  
    -   <span data-ttu-id="ef77c-135">をクリックして**パスワードの設定**を自動的にこれらのマッピングのパスワードを設定します。</span><span class="sxs-lookup"><span data-stu-id="ef77c-135">Click **Set Password** to automatically set the password for these mappings.</span></span>  
  
12. <span data-ttu-id="ef77c-136">**作成**ページ</span><span class="sxs-lookup"><span data-stu-id="ef77c-136">**Create** page</span></span>  
  
    -   <span data-ttu-id="ef77c-137">クリックして、マッピングを作成する前に**View Mappings File**必要な場合です。</span><span class="sxs-lookup"><span data-stu-id="ef77c-137">Before creating the mappings, click **View Mappings File** if desired.</span></span>  
  
    -   <span data-ttu-id="ef77c-138">準備ができたら、をクリックして**開始**マッピング操作を実行します。</span><span class="sxs-lookup"><span data-stu-id="ef77c-138">When you are ready, click **Start** to perform the mapping operation.</span></span> <span data-ttu-id="ef77c-139">状態は下の 3 つのボックスに表示されます。</span><span class="sxs-lookup"><span data-stu-id="ef77c-139">Your status is displayed in the three boxes below.</span></span>  
  
    -   <span data-ttu-id="ef77c-140">をクリックして**ログ ファイルの表示**を調べるエラーまたは警告が発生した可能性があります。</span><span class="sxs-lookup"><span data-stu-id="ef77c-140">Click **View Log File** to examine any errors or warnings that might have occurred.</span></span>  
  
13. <span data-ttu-id="ef77c-141">**マッピング ウィザード画面の完了**</span><span class="sxs-lookup"><span data-stu-id="ef77c-141">**Completing the Mapping Wizard screen**</span></span>  
  
14. <span data-ttu-id="ef77c-142">必要に応じて、オプションを選択し、クリックして**完了**です。</span><span class="sxs-lookup"><span data-stu-id="ef77c-142">Select any options desired, and then click **Finish**.</span></span>