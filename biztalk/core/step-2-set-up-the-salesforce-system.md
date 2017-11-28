---
title: "手順 2: Salesforce システムのセットアップ |Microsoft ドキュメント"
ms.custom: 
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: 
ms.suite: 
ms.tgt_pltfrm: 
ms.topic: article
ms.assetid: 0a4b09fb-70a7-4eec-b1e3-f05de0e84df1
caps.latest.revision: "7"
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: d65a1c741103b9c8f1e9493b7bd2aa56eef8cf18
ms.sourcegitcommit: cb908c540d8f1a692d01dc8f313e16cb4b4e696d
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 09/20/2017
---
# <a name="step-2-set-up-the-salesforce-system"></a><span data-ttu-id="babb2-102">手順 2: Salesforce システムをセットアップします。</span><span class="sxs-lookup"><span data-stu-id="babb2-102">Step 2: Set up the Salesforce System</span></span>
<span data-ttu-id="babb2-103">このステップでは、営業案件が正常にクローズされたときに通知を送信するように Salesforce を構成します。</span><span class="sxs-lookup"><span data-stu-id="babb2-103">In this step, you configure Salesforce to send notifications when an opportunity is successfully closed.</span></span> <span data-ttu-id="babb2-104">通知を送信する前に、次の手順を実行する必要があります。</span><span class="sxs-lookup"><span data-stu-id="babb2-104">Before you can send notifications, you need to perform the following steps:</span></span>  
  
-   <span data-ttu-id="babb2-105">Salesforce でアカウントを作成する。</span><span class="sxs-lookup"><span data-stu-id="babb2-105">Create an account in Salesforce.</span></span> <span data-ttu-id="babb2-106">アカウントは Northwind の顧客を表します。</span><span class="sxs-lookup"><span data-stu-id="babb2-106">An account represents a customer for Northwind.</span></span>  
  
-   <span data-ttu-id="babb2-107">アカウントの営業案件を作成する。</span><span class="sxs-lookup"><span data-stu-id="babb2-107">Create an opportunity for the account.</span></span> <span data-ttu-id="babb2-108">営業案件は顧客に見込める販売機会を表します。</span><span class="sxs-lookup"><span data-stu-id="babb2-108">An opportunity represents a prospective sales opportunity with the customer.</span></span> <span data-ttu-id="babb2-109">営業案件の一部として、顧客が興味を持っている製品詳細を追加します。</span><span class="sxs-lookup"><span data-stu-id="babb2-109">As part of the opportunity, you also add the product details that the customer is interested in.</span></span>  
  
-   <span data-ttu-id="babb2-110">Salesforce でワークフローを作成する。</span><span class="sxs-lookup"><span data-stu-id="babb2-110">Create a workflow in Salesforce.</span></span>  
  
-   <span data-ttu-id="babb2-111">Salesforce の接続型アプリケーション定義を作成する。</span><span class="sxs-lookup"><span data-stu-id="babb2-111">Create a Salesforce connected application definition.</span></span>  
  
> [!NOTE]
>  <span data-ttu-id="babb2-112">このトピックでは、既に Salesforce 開発者アカウントを持っていることを前提として手順を示しています。</span><span class="sxs-lookup"><span data-stu-id="babb2-112">The steps in this topic assume that you already have a Salesforce developer account.</span></span> <span data-ttu-id="babb2-113">Salesforce で新しい開発者アカウントを作成するには[http://go.microsoft.com/fwlink/?LinkId=296424](http://go.microsoft.com/fwlink/?LinkId=296424)です。</span><span class="sxs-lookup"><span data-stu-id="babb2-113">To create a new developer account in Salesforce, go to [http://go.microsoft.com/fwlink/?LinkId=296424](http://go.microsoft.com/fwlink/?LinkId=296424).</span></span>  
  
### <a name="to-create-an-account-in-salesforce"></a><span data-ttu-id="babb2-114">Salesforce でアカウントを作成するには</span><span class="sxs-lookup"><span data-stu-id="babb2-114">To create an Account in Salesforce</span></span>  
  
1.  <span data-ttu-id="babb2-115">開発者資格情報を使用して Salesforce.com ポータルにログオンします。</span><span class="sxs-lookup"><span data-stu-id="babb2-115">Log on to the Salesforce.com portal using your developer credentials.</span></span>  
  
2.  <span data-ttu-id="babb2-116">ポータルで、をクリックして、**アカウント** タブをクリックして**新規**です。</span><span class="sxs-lookup"><span data-stu-id="babb2-116">On the portal, click the **Accounts** tab, and then click **New**.</span></span>  
  
3.  <span data-ttu-id="babb2-117">**新しいアカウント** ページで、さまざまなフィールドの値を指定します。</span><span class="sxs-lookup"><span data-stu-id="babb2-117">On the **New Account** page, provide values for the various fields.</span></span> <span data-ttu-id="babb2-118">値を指定する**アカウント名**は必須です。</span><span class="sxs-lookup"><span data-stu-id="babb2-118">Specifying a value for **Account Name** is mandatory.</span></span> <span data-ttu-id="babb2-119">このチュートリアルでは、指定のアカウント名に`Customer1`です。</span><span class="sxs-lookup"><span data-stu-id="babb2-119">For this tutorial, specify the account name as `Customer1`.</span></span>  
  
4.  <span data-ttu-id="babb2-120">**[保存]**をクリックします。</span><span class="sxs-lookup"><span data-stu-id="babb2-120">Click **Save**.</span></span>  
  
### <a name="to-create-an-opportunity-for-the-customer"></a><span data-ttu-id="babb2-121">顧客の営業案件を作成するには</span><span class="sxs-lookup"><span data-stu-id="babb2-121">To create an Opportunity for the customer</span></span>  
  
1.  <span data-ttu-id="babb2-122">Salesforce.com ポータルで、をクリックして、**機会**タブです。</span><span class="sxs-lookup"><span data-stu-id="babb2-122">On the Salesforce.com portal, click the **Opportunities** tab.</span></span>  
  
2.  <span data-ttu-id="babb2-123">**最近の営業案件**セクションで、**新規**です。</span><span class="sxs-lookup"><span data-stu-id="babb2-123">In the **Recent Opportunities** section, click **New**.</span></span>  
  
3.  <span data-ttu-id="babb2-124">[新しい営業案件] ページで、次の値を指定します。</span><span class="sxs-lookup"><span data-stu-id="babb2-124">In the New Opportunity page, specify the following values:</span></span>  
  
    1.  <span data-ttu-id="babb2-125">指定して、**営業案件名**など、`Opportunity with Customer 1`です。</span><span class="sxs-lookup"><span data-stu-id="babb2-125">Specify an **Opportunity Name**, for example, `Opportunity with Customer 1`.</span></span>  
  
    2.  <span data-ttu-id="babb2-126">指定して、**アカウント名**です。</span><span class="sxs-lookup"><span data-stu-id="babb2-126">Specify the **Account Name**.</span></span> <span data-ttu-id="babb2-127">これは、この営業案件が関連付けられるアカウントを表します。</span><span class="sxs-lookup"><span data-stu-id="babb2-127">This represents the account with which this opportunity is associated.</span></span> <span data-ttu-id="babb2-128">このチュートリアルでは、アカウントを設定`Customer1`です。</span><span class="sxs-lookup"><span data-stu-id="babb2-128">For this tutorial, set the Account to `Customer1`.</span></span> <span data-ttu-id="babb2-129">このアカウントは、前の手順で作成したアカウントです。</span><span class="sxs-lookup"><span data-stu-id="babb2-129">You created this account in the previous procedure.</span></span>  
  
    3.  <span data-ttu-id="babb2-130">指定して、**終了日**です。</span><span class="sxs-lookup"><span data-stu-id="babb2-130">Specify a **Close Date**.</span></span> <span data-ttu-id="babb2-131">これは営業案件をクローズする日付を表しています。</span><span class="sxs-lookup"><span data-stu-id="babb2-131">This represents the date by which the opportunity should be closed.</span></span>  
  
    4.  <span data-ttu-id="babb2-132">指定して、**ステージ**です。</span><span class="sxs-lookup"><span data-stu-id="babb2-132">Specify a **Stage**.</span></span> <span data-ttu-id="babb2-133">これは営業案件の現在のステージを示しています。</span><span class="sxs-lookup"><span data-stu-id="babb2-133">This denotes the current stage for the opportunity.</span></span> <span data-ttu-id="babb2-134">最初に、することができますに設定する営業案件、たとえば、 **Needs Analysis**です。</span><span class="sxs-lookup"><span data-stu-id="babb2-134">To start with, you can set the opportunity to anything, for example, **Needs Analysis**.</span></span>  
  
         <span data-ttu-id="babb2-135">![Salesforce で営業案件を作成](../core/media/bts-sf-create-opp.jpg "BTS_SF_Create_Opp")</span><span class="sxs-lookup"><span data-stu-id="babb2-135">![Create an opportunity in Salesforce](../core/media/bts-sf-create-opp.jpg "BTS_SF_Create_Opp")</span></span>  
  
        > [!NOTE]
        >  <span data-ttu-id="babb2-136">ステージ設定しないことを確認**Closed Won**で開始します。</span><span class="sxs-lookup"><span data-stu-id="babb2-136">Make sure you do not set the stage to **Closed Won** to start with.</span></span> <span data-ttu-id="babb2-137">設定されているステージするたびに、このチュートリアルのシナリオの**Closed Won**リレー エンドポイントに通知が送信[!INCLUDE[winazure](../includes/winazure-md.md)][!INCLUDE[sb](../includes/sb-md.md)]です。</span><span class="sxs-lookup"><span data-stu-id="babb2-137">For the scenario in this tutorial, every time the stage is set to **Closed Won** a notification is sent to a relay endpoint on [!INCLUDE[winazure](../includes/winazure-md.md)][!INCLUDE[sb](../includes/sb-md.md)].</span></span> <span data-ttu-id="babb2-138">おをセットアップしていない、ソリューションの部分をまだにステージを設定する必要がありますいないように**Closed Won**です。</span><span class="sxs-lookup"><span data-stu-id="babb2-138">We haven’t set up that part of the solution yet, so you should not set the stage to **Closed Won**.</span></span>  
  
    5.  <span data-ttu-id="babb2-139">その他のオプションのフィールドに値を指定し、クリックして**保存**です。</span><span class="sxs-lookup"><span data-stu-id="babb2-139">Specify values for other optional fields and then click **Save**.</span></span>  
  
    6.  <span data-ttu-id="babb2-140">営業案件 ページの Customer1 の 、**製品**セクションで、**製品の追加**です。</span><span class="sxs-lookup"><span data-stu-id="babb2-140">On the Opportunity page for Customer1, under the **Products** section, click **Add Product**.</span></span>  
  
    7.  <span data-ttu-id="babb2-141">製品の一覧から、顧客が興味を持っている製品を選択し、をクリックして**選択**です。</span><span class="sxs-lookup"><span data-stu-id="babb2-141">From the list of products, select the products that the customer is interested in, and then click **Select**.</span></span>  
  
    8.  <span data-ttu-id="babb2-142">選択した製品の指定、顧客が、数量をクリックして**保存**です。</span><span class="sxs-lookup"><span data-stu-id="babb2-142">For each selected product, specify a quantity that the customer wants, and then click **Save**.</span></span>  
  
         <span data-ttu-id="babb2-143">![営業案件に製品を追加](../core/media/bts-sf-add-product.gif "BTS_SF_Add_Product")</span><span class="sxs-lookup"><span data-stu-id="babb2-143">![Add products to an opportunity](../core/media/bts-sf-add-product.gif "BTS_SF_Add_Product")</span></span>  
  
## <a name="create-a-salesforce-workflow"></a><span data-ttu-id="babb2-144">Salesforce ワークフローを作成する</span><span class="sxs-lookup"><span data-stu-id="babb2-144">Create a Salesforce Workflow</span></span>  
 <span data-ttu-id="babb2-145">このステップでは、営業案件が正常にクローズするたびに通知を送信するワークフローを作成します。</span><span class="sxs-lookup"><span data-stu-id="babb2-145">In this step we create a workflow to send out a notification every time an opportunity is closed successfully.</span></span> <span data-ttu-id="babb2-146">通知は、SOAP メッセージの形式し、でホストされるリレー エンドポイントに送信された[!INCLUDE[winazure](../includes/winazure-md.md)][!INCLUDE[sb](../includes/sb-md.md)]です。</span><span class="sxs-lookup"><span data-stu-id="babb2-146">The notification is in the form of a SOAP message and is sent to a relay endpoint hosted on [!INCLUDE[winazure](../includes/winazure-md.md)][!INCLUDE[sb](../includes/sb-md.md)].</span></span>  
  
#### <a name="to-create-a-workflow-for-opportunities"></a><span data-ttu-id="babb2-147">営業案件のワークフローを作成するには</span><span class="sxs-lookup"><span data-stu-id="babb2-147">To create a workflow for opportunities</span></span>  
  
1.  <span data-ttu-id="babb2-148">Salesforce ポータル上で、ページの右上隅にあるログイン名をクリックし、をクリックして**セットアップ**です。</span><span class="sxs-lookup"><span data-stu-id="babb2-148">On the Salesforce portal, click your login name at the top right corner of the page, and then click **Setup**.</span></span>  
  
2.  <span data-ttu-id="babb2-149">左側のウィンドウで **アプリ セットアップ**、展開**作成**、展開**ワークフローと承認**、順にクリック**ワークフロー ルール**です。</span><span class="sxs-lookup"><span data-stu-id="babb2-149">In the left pane, under **App Setup**, expand **Create**, expand **Workflow & Approvals**, and then click **Workflow Rules**.</span></span>  
  
    > [!NOTE]
    >  <span data-ttu-id="babb2-150">[ワークフローのルール] ページを初めて開く場合は、Salesforce におけるワークフローを理解するための情報が表示されます。</span><span class="sxs-lookup"><span data-stu-id="babb2-150">If you are opening the Workflow Rules page for the first time, you will be presented with some information to understand how workflows work in Salesforce.</span></span> <span data-ttu-id="babb2-151">情報を読み、をクリックして**続行**です。</span><span class="sxs-lookup"><span data-stu-id="babb2-151">Read through the information and then click **Continue**.</span></span>  
  
3.  <span data-ttu-id="babb2-152">**すべてのワークフロー ルール**] ページで [**新しいルール**です。</span><span class="sxs-lookup"><span data-stu-id="babb2-152">On the **All Workflow Rules** page, click **New Rule**.</span></span>  
  
4.  <span data-ttu-id="babb2-153">**オブジェクトの選択**一覧で、をクリックして**営業案件**、順にクリック**次**です。</span><span class="sxs-lookup"><span data-stu-id="babb2-153">From the **Select Object** list, click **Opportunity**, and then click **Next**.</span></span>  
  
5.  <span data-ttu-id="babb2-154">次のページで、次の項目を指定します。</span><span class="sxs-lookup"><span data-stu-id="babb2-154">In the next page, specify the following:</span></span>  
  
    1.  <span data-ttu-id="babb2-155">設定、**ルール名**として`Closed Opportunity`です。</span><span class="sxs-lookup"><span data-stu-id="babb2-155">Set the **Rule Name** as `Closed Opportunity`.</span></span>  
  
    2.  <span data-ttu-id="babb2-156">設定、**評価基準**として**作成されると、し、いつでもは、その後の条件を満たす編集**です。</span><span class="sxs-lookup"><span data-stu-id="babb2-156">Set the **Evaluation Criteria** as **created, and any time it’s edited to subsequently meet criteria**.</span></span>  
  
    3.  <span data-ttu-id="babb2-157">**規則の条件**、設定をルールを実行するときに、**条件が満たされた**です。</span><span class="sxs-lookup"><span data-stu-id="babb2-157">For the **Rule Criteria**, set to run the rule when the **criteria are met**.</span></span>  
  
    4.  <span data-ttu-id="babb2-158">設定**フィールド**に**営業案件: ステージ**、**演算子**に**equals**、および**値**に`Closed Won`.</span><span class="sxs-lookup"><span data-stu-id="babb2-158">Set **Field** to **Opportunity: Stage**, **Operator** to **equals**, and **Value** to `Closed Won`.</span></span>  
  
         <span data-ttu-id="babb2-159">![Salesforce ワークフローを作成する](../core/media/bts-sf-create-workflow.jpg "BTS_SF_Create_Workflow")</span><span class="sxs-lookup"><span data-stu-id="babb2-159">![Create a Salesforce workflow](../core/media/bts-sf-create-workflow.jpg "BTS_SF_Create_Workflow")</span></span>  
  
    5.  <span data-ttu-id="babb2-160">をクリックして**保存 (&) 次へ**です。</span><span class="sxs-lookup"><span data-stu-id="babb2-160">Click **Save & Next**.</span></span>  
  
6.  <span data-ttu-id="babb2-161">新しいルールのワークフロー アクションを次のように定義します。</span><span class="sxs-lookup"><span data-stu-id="babb2-161">Define the workflow action for the new rule:</span></span>  
  
    1.  <span data-ttu-id="babb2-162">**ワークフロー アクションの指定**] ページで [**ワークフロー アクションの追加**ボタンをクリックし、をクリックして**新しい送信メッセージ**です。</span><span class="sxs-lookup"><span data-stu-id="babb2-162">On the **Specify Workflow Actions** page, click **Add Workflow Action** button and then click **New Outbound Message**.</span></span>  
  
    2.  <span data-ttu-id="babb2-163">設定、**名前**と**一意の名前**フィールドを`NewOp1`です。</span><span class="sxs-lookup"><span data-stu-id="babb2-163">Set the **Name** and **Unique Name** fields to `NewOp1`.</span></span>  
  
    3.  <span data-ttu-id="babb2-164">、のように、説明を指定、`Message sent when an opportunity is successfully closed`です。</span><span class="sxs-lookup"><span data-stu-id="babb2-164">Specify a description, such as, the `Message sent when an opportunity is successfully closed`.</span></span>  
  
    4.  <span data-ttu-id="babb2-165">指定して、**エンドポイント URL**として`https://btssalesforce.servicebus.windows.net/notifications/opportunity`です。</span><span class="sxs-lookup"><span data-stu-id="babb2-165">Specify the **Endpoint URL** as `https://btssalesforce.servicebus.windows.net/notifications/opportunity`.</span></span>  
  
         <span data-ttu-id="babb2-166">ここでは、 **btssalesforce**は、[!INCLUDE[sb](../includes/sb-md.md)]前半の手順で作成した名前空間。</span><span class="sxs-lookup"><span data-stu-id="babb2-166">Here, **btssalesforce** is your [!INCLUDE[sb](../includes/sb-md.md)] namespace that you created in earlier steps.</span></span> <span data-ttu-id="babb2-167">**/notifications/**リレーを作成するのには、このチュートリアルの後の手順を表します。</span><span class="sxs-lookup"><span data-stu-id="babb2-167">**/notifications/opportunity/** represents the relay that we will create in later steps of this tutorial.</span></span>  
  
        > [!NOTE]
        >  <span data-ttu-id="babb2-168">先に作成した [!INCLUDE[sb](../includes/sb-md.md)] 名前空間を指定する必要があります。</span><span class="sxs-lookup"><span data-stu-id="babb2-168">You must specify the [!INCLUDE[sb](../includes/sb-md.md)] namespace that you created earlier.</span></span>  
  
    5.  <span data-ttu-id="babb2-169">確認してください、**保護されたコンポーネント**チェック ボックスがオフと**セッション ID の送信**のチェック ボックスをオンします。</span><span class="sxs-lookup"><span data-stu-id="babb2-169">Make sure the **Protected Component** check box is clear and the **Send Session ID** check box is checked.</span></span>  
  
    6.  <span data-ttu-id="babb2-170">**を送信する機会がフィールド**から関連するフィールドを選択して、**利用可能なフィールド**を一覧表示し、をクリックして、**追加**ボタンをクリックします。</span><span class="sxs-lookup"><span data-stu-id="babb2-170">For **Opportunity fields to send** select the relevant fields from the **Available Fields** list and then click the **Add** button.</span></span>  
  
    7.  <span data-ttu-id="babb2-171">をクリックして**保存** をクリックし、**完了**です。</span><span class="sxs-lookup"><span data-stu-id="babb2-171">Click **Save** and then click **Done**.</span></span>  
  
    8.  <span data-ttu-id="babb2-172">左側のウィンドウで **アプリ セットアップ**、展開**作成**、展開**ワークフローと承認**、順にクリック**ワークフロー ルール**です。</span><span class="sxs-lookup"><span data-stu-id="babb2-172">In the left pane, under **App Setup**, expand **Create**, expand **Workflow & Approvals**, and then click **Workflow Rules**.</span></span> <span data-ttu-id="babb2-173">いることを確認、**クローズされた営業案件**ルールが一覧表示します。</span><span class="sxs-lookup"><span data-stu-id="babb2-173">Verify that the **Closed Opportunity** rule is listed there.</span></span> <span data-ttu-id="babb2-174">下にある、**アクション**の列、**クローズされた営業案件**ルール をクリックして**Activate**ルールを有効にします。</span><span class="sxs-lookup"><span data-stu-id="babb2-174">Under the **Action** column for the **Closed Opportunity** rule, click **Activate** to activate the rule.</span></span>  
  
## <a name="create-a-salesforce-connected-application"></a><span data-ttu-id="babb2-175">Salesforce の接続型アプリケーションを作成する</span><span class="sxs-lookup"><span data-stu-id="babb2-175">Create a Salesforce Connected Application</span></span>  
 <span data-ttu-id="babb2-176">接続型アプリケーションの定義を作成すると、Salesforce に接続するための OAuth トークンの要求に必要な一連のキーが生成されます。</span><span class="sxs-lookup"><span data-stu-id="babb2-176">Creating a connected application definition generates a set of keys required to request OAuth tokens to access to connect to Salesforce.</span></span> <span data-ttu-id="babb2-177">このチュートリアルの後のステージでは、[!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)] が接続型アプリケーションとなり、接続型アプリケーションの定義を使用して Salesforce にクエリを送信します。</span><span class="sxs-lookup"><span data-stu-id="babb2-177">In the later stages of this tutorial, [!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)] will be the connected application that queries Salesforce using the connected application definition.</span></span>  
  
#### <a name="to-create-a-connected-application-for-salesforce"></a><span data-ttu-id="babb2-178">Salesforce 向けの接続型アプリケーションを作成するには</span><span class="sxs-lookup"><span data-stu-id="babb2-178">To create a connected application for Salesforce</span></span>  
  
1.  <span data-ttu-id="babb2-179">Salesforce ポータル上で、ページの右上隅にあるログイン名をクリックし、をクリックして**セットアップ**です。</span><span class="sxs-lookup"><span data-stu-id="babb2-179">On the Salesforce portal, click your login name at the top right corner of the page, and then click **Setup**.</span></span>  
  
2.  <span data-ttu-id="babb2-180">左側のウィンドウで **アプリ セットアップ**、展開**作成**、順に展開**アプリ**です。</span><span class="sxs-lookup"><span data-stu-id="babb2-180">In the left pane, under **App Setup**, expand **Create**, and then expand **Apps**.</span></span> <span data-ttu-id="babb2-181">**アプリ** ページの 、**接続型アプリケーション**セクションで、**新規**です。</span><span class="sxs-lookup"><span data-stu-id="babb2-181">On the **Apps** page, under the **Connected Apps** section, click **New**.</span></span>  
  
3.  <span data-ttu-id="babb2-182">**新しい接続アプリケーション** ページで、次を指定します。</span><span class="sxs-lookup"><span data-stu-id="babb2-182">In the **New Connection App** page, specify the following:</span></span>  
  
    1.  <span data-ttu-id="babb2-183">**アプリ名を接続している**、指定`BizTalk_Salesforce`です。</span><span class="sxs-lookup"><span data-stu-id="babb2-183">For **Connected App Name**, specify `BizTalk_Salesforce`.</span></span>  
  
    2.  <span data-ttu-id="babb2-184">**開発者名**名前に、ログを指定します。</span><span class="sxs-lookup"><span data-stu-id="babb2-184">For **Developer Name**, specify your log on name.</span></span>  
  
    3.  <span data-ttu-id="babb2-185">**Contact Email**電子メールを指定します。</span><span class="sxs-lookup"><span data-stu-id="babb2-185">For **Contact Email**, specify your e-mail.</span></span>  
  
    4.  <span data-ttu-id="babb2-186">**コールバック URL**、有効な URL を指定します。</span><span class="sxs-lookup"><span data-stu-id="babb2-186">For **Callback URL**, specify a valid URL.</span></span>  
  
        > [!NOTE]
        >  <span data-ttu-id="babb2-187">このシナリオで使用する Salesforce での認証方法では、ここで指定する値は使用しません。</span><span class="sxs-lookup"><span data-stu-id="babb2-187">Because of the way we authenticate with Salesforce in this scenario, the value you specify here is not used.</span></span>  
  
    5.  <span data-ttu-id="babb2-188">下にある**OAuth の使用可能なスコープ**を選択**フル アクセス**、 **、あなたに代わって要求をいつでも実行**、および**アクセスデータを管理および**をクリックし、**追加**に移動するボタン、 **OAuth スコープの選択**です。</span><span class="sxs-lookup"><span data-stu-id="babb2-188">Under **Available OAuth Scopes**, select **Full access**, **Perform requests on your behalf at any time**, and **Access and manage your data** and then click the **Add** button to move them into the **Selected OAuth Scopes**.</span></span>  
  
    6.  <span data-ttu-id="babb2-189">**[保存]**をクリックします。</span><span class="sxs-lookup"><span data-stu-id="babb2-189">Click **Save**.</span></span> <span data-ttu-id="babb2-190">表示されるページに関する情報を格納する、**コンシューマー キー**と**コンシューマー シークレット**です。</span><span class="sxs-lookup"><span data-stu-id="babb2-190">The page that appears contains information about the **Consumer Key** and **Consumer Secret**.</span></span> <span data-ttu-id="babb2-191">これらの値はメモしておく必要があります。</span><span class="sxs-lookup"><span data-stu-id="babb2-191">You must make a note of these values.</span></span> <span data-ttu-id="babb2-192">[!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)] から Salesforce に接続する際には、これらの値が必要です。</span><span class="sxs-lookup"><span data-stu-id="babb2-192">You will need these values while connecting to Salesforce from [!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)].</span></span>  
  
         <span data-ttu-id="babb2-193">![Salesforce アクセス キー](../core/media/bts-sf-consumer-keys.jpg "BTS_SF_Consumer_Keys")</span><span class="sxs-lookup"><span data-stu-id="babb2-193">![Keys for Salesforce access](../core/media/bts-sf-consumer-keys.jpg "BTS_SF_Consumer_Keys")</span></span>  
  
4.  <span data-ttu-id="babb2-194">最後に、未知のネットワークの場所から Salesforce に接続する際に必要となるセキュリティ トークンを生成します。</span><span class="sxs-lookup"><span data-stu-id="babb2-194">Finally, generate a security token required for connecting to Salesforce from unknown network locations.</span></span>  
  
    1.  <span data-ttu-id="babb2-195">Salesforce ポータルの左側のウィンドウで **個人セットアップ**、展開**個人情報**、順にクリック**Reset My Security Token**です。</span><span class="sxs-lookup"><span data-stu-id="babb2-195">On the left pane of the Salesforce portal, under **Personal Setup**, expand **Personal Information**, and then click **Reset My Security Token**.</span></span>  
  
    2.  <span data-ttu-id="babb2-196">警告を確認し、クリックして**Reset Security Token**です。</span><span class="sxs-lookup"><span data-stu-id="babb2-196">Read the warning and then click **Reset Security Token**.</span></span>  
  
    3.  <span data-ttu-id="babb2-197">Salesforce アカウントの作成の際に指定した電子メール アドレスに、セキュリティ トークンが送信されます。</span><span class="sxs-lookup"><span data-stu-id="babb2-197">You should receive the security token at the e-mail address you specified while creating your Salesforce account.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="babb2-198">参照</span><span class="sxs-lookup"><span data-stu-id="babb2-198">See Also</span></span>  
 [<span data-ttu-id="babb2-199">チュートリアル 6: Salesforce との BizTalk Server 2013 の統合</span><span class="sxs-lookup"><span data-stu-id="babb2-199">Tutorial 6: Integrating BizTalk Server 2013 with Salesforce</span></span>](Tutorial:%20Integrating%20BizTalk%20Server%202013%20with%20Salesforce.md)