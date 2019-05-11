---
title: マッピング ウィザードを使用する方法 |Microsoft Docs
ms.custom: ''
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: ''
ms.suite: ''
ms.tgt_pltfrm: ''
ms.topic: article
ms.assetid: 35b96cea-ead7-43de-8411-62d2c7d6620e
caps.latest.revision: 3
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: 5d6070bc749a6a0a09cc77a51a62c1d0a9bb5c54
ms.sourcegitcommit: 381e83d43796a345488d54b3f7413e11d56ad7be
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 05/07/2019
ms.locfileid: "65383305"
---
# <a name="how-to-use-the-mapping-wizard"></a><span data-ttu-id="5fd10-102">マッピング ウィザードを使用する方法</span><span class="sxs-lookup"><span data-stu-id="5fd10-102">How to Use the Mapping Wizard</span></span>
<span data-ttu-id="5fd10-103">エンタープライズ シングル サインオンのこのバージョンには、関連アプリケーションのマッピングを簡単に作成することができます、マッピング ウィザードが含まれています。</span><span class="sxs-lookup"><span data-stu-id="5fd10-103">This version of Enterprise Single Sign-On includes the Mapping Wizard, which allows you to easily create mappings for affiliate applications.</span></span>  
  
> [!NOTE]
>  <span data-ttu-id="5fd10-104">マッピング ウィザードは、外部ユーザー Id が、Windows ドメイン アカウントに基づいている場合のみ使用できます。</span><span class="sxs-lookup"><span data-stu-id="5fd10-104">You can only use the Mapping Wizard if the External UserID is based on the Windows domain account.</span></span>  
  
### <a name="to-start-the-mapping-wizard"></a><span data-ttu-id="5fd10-105">マッピング ウィザードを開始するには</span><span class="sxs-lookup"><span data-stu-id="5fd10-105">To start the Mapping Wizard</span></span>  
  
1.  <span data-ttu-id="5fd10-106">エンタープライズ シングル サインオンを開きます。</span><span class="sxs-lookup"><span data-stu-id="5fd10-106">Open Enterprise Single Sign-On.</span></span>  
  
2.  <span data-ttu-id="5fd10-107">スコープ ペインで次のようにクリックします。**関連アプリケーション**します。</span><span class="sxs-lookup"><span data-stu-id="5fd10-107">In the scope pane, click **Affiliate Applications**.</span></span>  
  
3.  <span data-ttu-id="5fd10-108">適切な関連アプリケーションを右クリックします。</span><span class="sxs-lookup"><span data-stu-id="5fd10-108">Right click the appropriate affiliate application.</span></span>  
  
4.  <span data-ttu-id="5fd10-109">クリックして**マッピングを作成する**します。</span><span class="sxs-lookup"><span data-stu-id="5fd10-109">Click **Create Mappings**.</span></span> <span data-ttu-id="5fd10-110">マッピング ウィザードが表示されます。</span><span class="sxs-lookup"><span data-stu-id="5fd10-110">The Mapping Wizard appears.</span></span>  
  
5.  <span data-ttu-id="5fd10-111">**マッピング ウィザードへようこそ**</span><span class="sxs-lookup"><span data-stu-id="5fd10-111">**Welcome to the Mapping Wizard**</span></span>  
  
    -   <span data-ttu-id="5fd10-112">これが正しい関連アプリケーションであることを確認し、クリックして**次**します。</span><span class="sxs-lookup"><span data-stu-id="5fd10-112">Verify that this is the correct affiliate application, and click **Next**.</span></span>  
  
6.  <span data-ttu-id="5fd10-113">**マッピング ファイル オプション**ページ</span><span class="sxs-lookup"><span data-stu-id="5fd10-113">**Mappings File Option** page</span></span>  
  
    -   <span data-ttu-id="5fd10-114">ENTSSO では、XML ファイルを通じてマッピングを管理します。</span><span class="sxs-lookup"><span data-stu-id="5fd10-114">ENTSSO manages mappings through an XML file.</span></span> <span data-ttu-id="5fd10-115">新しいファイルを作成または既存のリソースを選択することができます。</span><span class="sxs-lookup"><span data-stu-id="5fd10-115">You can choose to create a new file or use an existing one.</span></span>  
  
7.  <span data-ttu-id="5fd10-116">**ファイルの場所**ページ</span><span class="sxs-lookup"><span data-stu-id="5fd10-116">**Files Location** page</span></span>  
  
    -   <span data-ttu-id="5fd10-117">使用するファイルを選択します。</span><span class="sxs-lookup"><span data-stu-id="5fd10-117">Select the files to be used.</span></span>  
  
    -   <span data-ttu-id="5fd10-118">クリックする必要があります**検証**続行する前にファイルを検証します。</span><span class="sxs-lookup"><span data-stu-id="5fd10-118">You must click **Validate** to validate the files before proceeding.</span></span> <span data-ttu-id="5fd10-119">検証状態が表示されます、**状態**ウィンドウ。</span><span class="sxs-lookup"><span data-stu-id="5fd10-119">The validation status appears in the **Status** window.</span></span>  
  
8.  <span data-ttu-id="5fd10-120">**アカウント**ページ</span><span class="sxs-lookup"><span data-stu-id="5fd10-120">**Accounts** page</span></span>  
  
    -   <span data-ttu-id="5fd10-121">新しいマッピング ファイルを生成し、クリックして 1 つまたは複数のアカウントを選択**検証**です。</span><span class="sxs-lookup"><span data-stu-id="5fd10-121">Choose one or more accounts to generate the new mappings file, and click **Validate**.</span></span>  
  
9. <span data-ttu-id="5fd10-122">**外部のユーザー名**ページ</span><span class="sxs-lookup"><span data-stu-id="5fd10-122">**External User Name** page</span></span>  
  
    -   <span data-ttu-id="5fd10-123">Windows ユーザー アカウントから外部ユーザー名を生成する方法を定義します。</span><span class="sxs-lookup"><span data-stu-id="5fd10-123">Define how the external user name is generated from the Windows user account.</span></span> <span data-ttu-id="5fd10-124">ボックスで選択するで名前を表示する方法を表示できます、**例**ボックス。</span><span class="sxs-lookup"><span data-stu-id="5fd10-124">As you make selections in the boxes, you can see how the names will appear in the **Example** box.</span></span>  
  
10. <span data-ttu-id="5fd10-125">**生成**ページ</span><span class="sxs-lookup"><span data-stu-id="5fd10-125">**Generate** page</span></span>  
  
    -   <span data-ttu-id="5fd10-126">クリックして**開始**マッピング ファイルを生成します。</span><span class="sxs-lookup"><span data-stu-id="5fd10-126">Click **Start** to generate the mappings file.</span></span> <span data-ttu-id="5fd10-127">(営業案件は次のページを表示またはマッピングを作成する前に、必要に応じて、ファイルを編集する必要が)。結果は、次の 3 つのウィンドウに表示されます。</span><span class="sxs-lookup"><span data-stu-id="5fd10-127">(You will have an opportunity on the next page to view or edit the file as necessary before mappings are created.) Results are displayed in the three windows below.</span></span>  
  
    -   <span data-ttu-id="5fd10-128">**数**選択されたアカウント内のマッピングには、近似のためアカウントは、他のアカウントで入れ子にすることができます。</span><span class="sxs-lookup"><span data-stu-id="5fd10-128">The **Number** of mappings in selected accounts is an approximation, because accounts may be nested in other accounts.</span></span>  
  
    -   <span data-ttu-id="5fd10-129">クリックして**ログ ファイルの表示**を調べるエラーまたは警告が発生した可能性があります。</span><span class="sxs-lookup"><span data-stu-id="5fd10-129">Click **View Log File** to examine any errors or warnings that might have occurred.</span></span>  
  
11. <span data-ttu-id="5fd10-130">**オプション**ページ</span><span class="sxs-lookup"><span data-stu-id="5fd10-130">**Options** page</span></span>  
  
    -   <span data-ttu-id="5fd10-131">ファイルが作成されました。</span><span class="sxs-lookup"><span data-stu-id="5fd10-131">Your file has been created.</span></span> <span data-ttu-id="5fd10-132">クリックして**マッピング ファイルの表示/編集**必要な場合。</span><span class="sxs-lookup"><span data-stu-id="5fd10-132">Click **View/Edit Mappings File** if desired.</span></span>  
  
    -   <span data-ttu-id="5fd10-133">クリックして**マッピングを有効にする**する場合は、マッピングを自動的に有効にします。</span><span class="sxs-lookup"><span data-stu-id="5fd10-133">Click **Enable mappings** if you want the mappings to be automatically enabled.</span></span> <span data-ttu-id="5fd10-134">(これをクリックしなかった場合必要があります手動で有効にします。)</span><span class="sxs-lookup"><span data-stu-id="5fd10-134">(If you do not click this, you will have to enable them manually.)</span></span>  
  
    -   <span data-ttu-id="5fd10-135">クリックして**Set Password**を自動的にこれらのマッピングのパスワードを設定します。</span><span class="sxs-lookup"><span data-stu-id="5fd10-135">Click **Set Password** to automatically set the password for these mappings.</span></span>  
  
12. <span data-ttu-id="5fd10-136">**作成**ページ</span><span class="sxs-lookup"><span data-stu-id="5fd10-136">**Create** page</span></span>  
  
    -   <span data-ttu-id="5fd10-137">マッピングを作成する前に次のようにクリックします。 **View Mappings File**必要な場合。</span><span class="sxs-lookup"><span data-stu-id="5fd10-137">Before creating the mappings, click **View Mappings File** if desired.</span></span>  
  
    -   <span data-ttu-id="5fd10-138">準備ができたら、クリックして**開始**マッピング操作を実行します。</span><span class="sxs-lookup"><span data-stu-id="5fd10-138">When you are ready, click **Start** to perform the mapping operation.</span></span> <span data-ttu-id="5fd10-139">状態は、次の 3 つのボックスに表示されます。</span><span class="sxs-lookup"><span data-stu-id="5fd10-139">Your status is displayed in the three boxes below.</span></span>  
  
    -   <span data-ttu-id="5fd10-140">クリックして**ログ ファイルの表示**を調べるエラーまたは警告が発生した可能性があります。</span><span class="sxs-lookup"><span data-stu-id="5fd10-140">Click **View Log File** to examine any errors or warnings that might have occurred.</span></span>  
  
13. <span data-ttu-id="5fd10-141">**マッピング ウィザードの画面を完了します。**</span><span class="sxs-lookup"><span data-stu-id="5fd10-141">**Completing the Mapping Wizard screen**</span></span>  
  
14. <span data-ttu-id="5fd10-142">必要に応じて、オプションを選択し、クリックして**完了**します。</span><span class="sxs-lookup"><span data-stu-id="5fd10-142">Select any options desired, and then click **Finish**.</span></span>