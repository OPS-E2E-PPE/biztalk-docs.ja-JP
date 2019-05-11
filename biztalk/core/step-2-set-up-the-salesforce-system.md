---
title: 手順 2:Salesforce システムのセットアップ |Microsoft Docs
ms.custom: ''
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: ''
ms.suite: ''
ms.tgt_pltfrm: ''
ms.topic: article
ms.assetid: 0a4b09fb-70a7-4eec-b1e3-f05de0e84df1
caps.latest.revision: 7
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: f6bd461605bbb9fbdedf1a83d005501b035af2ff
ms.sourcegitcommit: 381e83d43796a345488d54b3f7413e11d56ad7be
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 05/07/2019
ms.locfileid: "65392710"
---
# <a name="step-2-set-up-the-salesforce-system"></a><span data-ttu-id="1ba67-102">手順 2:Salesforce システムを設定します。</span><span class="sxs-lookup"><span data-stu-id="1ba67-102">Step 2: Set up the Salesforce System</span></span>
<span data-ttu-id="1ba67-103">この手順では、営業案件が正常に閉じられたときに通知を送信する Salesforce を構成します。</span><span class="sxs-lookup"><span data-stu-id="1ba67-103">In this step, you configure Salesforce to send notifications when an opportunity is successfully closed.</span></span> <span data-ttu-id="1ba67-104">通知を送信するには、次の手順を実行する必要があります。</span><span class="sxs-lookup"><span data-stu-id="1ba67-104">Before you can send notifications, you need to perform the following steps:</span></span>  
  
-   <span data-ttu-id="1ba67-105">Salesforce でアカウントを作成します。</span><span class="sxs-lookup"><span data-stu-id="1ba67-105">Create an account in Salesforce.</span></span> <span data-ttu-id="1ba67-106">アカウントは、Northwind の顧客を表します。</span><span class="sxs-lookup"><span data-stu-id="1ba67-106">An account represents a customer for Northwind.</span></span>  
  
-   <span data-ttu-id="1ba67-107">アカウントの営業案件を作成します。</span><span class="sxs-lookup"><span data-stu-id="1ba67-107">Create an opportunity for the account.</span></span> <span data-ttu-id="1ba67-108">営業案件は顧客に見込める販売機会を表します。</span><span class="sxs-lookup"><span data-stu-id="1ba67-108">An opportunity represents a prospective sales opportunity with the customer.</span></span> <span data-ttu-id="1ba67-109">営業案件の一部として、また、顧客が興味を製品の詳細を追加します。</span><span class="sxs-lookup"><span data-stu-id="1ba67-109">As part of the opportunity, you also add the product details that the customer is interested in.</span></span>  
  
-   <span data-ttu-id="1ba67-110">Salesforce でワークフローを作成します。</span><span class="sxs-lookup"><span data-stu-id="1ba67-110">Create a workflow in Salesforce.</span></span>  
  
-   <span data-ttu-id="1ba67-111">Salesforce の接続型アプリケーションの定義を作成します。</span><span class="sxs-lookup"><span data-stu-id="1ba67-111">Create a Salesforce connected application definition.</span></span>  
  
> [!NOTE]
>  <span data-ttu-id="1ba67-112">このトピックの手順では、既に Salesforce 開発者アカウントがあることを前提としています。</span><span class="sxs-lookup"><span data-stu-id="1ba67-112">The steps in this topic assume that you already have a Salesforce developer account.</span></span> <span data-ttu-id="1ba67-113">Salesforce で新しい開発者アカウントを作成するには[ http://go.microsoft.com/fwlink/?LinkId=296424](http://go.microsoft.com/fwlink/?LinkId=296424)します。</span><span class="sxs-lookup"><span data-stu-id="1ba67-113">To create a new developer account in Salesforce, go to [http://go.microsoft.com/fwlink/?LinkId=296424](http://go.microsoft.com/fwlink/?LinkId=296424).</span></span>  
  
### <a name="to-create-an-account-in-salesforce"></a><span data-ttu-id="1ba67-114">Salesforce でアカウントを作成するには</span><span class="sxs-lookup"><span data-stu-id="1ba67-114">To create an Account in Salesforce</span></span>  
  
1.  <span data-ttu-id="1ba67-115">開発者の資格情報を使用して Salesforce.com ポータルにログオンします。</span><span class="sxs-lookup"><span data-stu-id="1ba67-115">Log on to the Salesforce.com portal using your developer credentials.</span></span>  
  
2.  <span data-ttu-id="1ba67-116">ポータルで、をクリックして、**アカウント**タブをクリックし、をクリックし、**新規**します。</span><span class="sxs-lookup"><span data-stu-id="1ba67-116">On the portal, click the **Accounts** tab, and then click **New**.</span></span>  
  
3.  <span data-ttu-id="1ba67-117">**新しいアカウント** ページで、さまざまなフィールドの値を指定します。</span><span class="sxs-lookup"><span data-stu-id="1ba67-117">On the **New Account** page, provide values for the various fields.</span></span> <span data-ttu-id="1ba67-118">値を指定する**アカウント名**は必須です。</span><span class="sxs-lookup"><span data-stu-id="1ba67-118">Specifying a value for **Account Name** is mandatory.</span></span> <span data-ttu-id="1ba67-119">このチュートリアルでは、指定のアカウント名に`Customer1`します。</span><span class="sxs-lookup"><span data-stu-id="1ba67-119">For this tutorial, specify the account name as `Customer1`.</span></span>  
  
4.  <span data-ttu-id="1ba67-120">**[保存]** をクリックします。</span><span class="sxs-lookup"><span data-stu-id="1ba67-120">Click **Save**.</span></span>  
  
### <a name="to-create-an-opportunity-for-the-customer"></a><span data-ttu-id="1ba67-121">顧客の営業案件を作成するには</span><span class="sxs-lookup"><span data-stu-id="1ba67-121">To create an Opportunity for the customer</span></span>  
  
1. <span data-ttu-id="1ba67-122">Salesforce.com ポータルで、**機会**タブ。</span><span class="sxs-lookup"><span data-stu-id="1ba67-122">On the Salesforce.com portal, click the **Opportunities** tab.</span></span>  
  
2. <span data-ttu-id="1ba67-123">**最近の営業案件**セクションで、**新規**します。</span><span class="sxs-lookup"><span data-stu-id="1ba67-123">In the **Recent Opportunities** section, click **New**.</span></span>  
  
3. <span data-ttu-id="1ba67-124">新しい営業案件 ページで、次の値を指定します。</span><span class="sxs-lookup"><span data-stu-id="1ba67-124">In the New Opportunity page, specify the following values:</span></span>  
  
   1. <span data-ttu-id="1ba67-125">指定、**営業案件名**、たとえば、`Opportunity with Customer 1`します。</span><span class="sxs-lookup"><span data-stu-id="1ba67-125">Specify an **Opportunity Name**, for example, `Opportunity with Customer 1`.</span></span>  
  
   2. <span data-ttu-id="1ba67-126">指定、**アカウント名**します。</span><span class="sxs-lookup"><span data-stu-id="1ba67-126">Specify the **Account Name**.</span></span> <span data-ttu-id="1ba67-127">これは、この営業案件が関連付けられているアカウントを表します。</span><span class="sxs-lookup"><span data-stu-id="1ba67-127">This represents the account with which this opportunity is associated.</span></span> <span data-ttu-id="1ba67-128">このチュートリアルでは、アカウントを設定`Customer1`します。</span><span class="sxs-lookup"><span data-stu-id="1ba67-128">For this tutorial, set the Account to `Customer1`.</span></span> <span data-ttu-id="1ba67-129">前の手順では、このアカウントを作成します。</span><span class="sxs-lookup"><span data-stu-id="1ba67-129">You created this account in the previous procedure.</span></span>  
  
   3. <span data-ttu-id="1ba67-130">指定、**終了日**します。</span><span class="sxs-lookup"><span data-stu-id="1ba67-130">Specify a **Close Date**.</span></span> <span data-ttu-id="1ba67-131">これは、営業案件を閉じる必要があります、日付を表します。</span><span class="sxs-lookup"><span data-stu-id="1ba67-131">This represents the date by which the opportunity should be closed.</span></span>  
  
   4. <span data-ttu-id="1ba67-132">指定、**ステージ**します。</span><span class="sxs-lookup"><span data-stu-id="1ba67-132">Specify a **Stage**.</span></span> <span data-ttu-id="1ba67-133">これは、営業案件の現在のステージを示します。</span><span class="sxs-lookup"><span data-stu-id="1ba67-133">This denotes the current stage for the opportunity.</span></span> <span data-ttu-id="1ba67-134">最初に、設定できます営業案件、たとえば、 **Needs Analysis**します。</span><span class="sxs-lookup"><span data-stu-id="1ba67-134">To start with, you can set the opportunity to anything, for example, **Needs Analysis**.</span></span>  
  
       <span data-ttu-id="1ba67-135">![Salesforce の営業案件を作成](../core/media/bts-sf-create-opp.jpg "BTS_SF_Create_Opp")</span><span class="sxs-lookup"><span data-stu-id="1ba67-135">![Create an opportunity in Salesforce](../core/media/bts-sf-create-opp.jpg "BTS_SF_Create_Opp")</span></span>  
  
      > [!NOTE]
      >  <span data-ttu-id="1ba67-136">ステージ設定しないことを確認**Closed Won**で開始します。</span><span class="sxs-lookup"><span data-stu-id="1ba67-136">Make sure you do not set the stage to **Closed Won** to start with.</span></span> <span data-ttu-id="1ba67-137">ステージに設定するたびに、このチュートリアルでシナリオ**Closed Won**リレー エンドポイントに、通知が送信[!INCLUDE[winazure](../includes/winazure-md.md)][!INCLUDE[sb](../includes/sb-md.md)]します。</span><span class="sxs-lookup"><span data-stu-id="1ba67-137">For the scenario in this tutorial, every time the stage is set to **Closed Won** a notification is sent to a relay endpoint on [!INCLUDE[winazure](../includes/winazure-md.md)][!INCLUDE[sb](../includes/sb-md.md)].</span></span> <span data-ttu-id="1ba67-138">設定されていない、ソリューションの部分をまだにステージを設定する必要がありますいないように**Closed Won**します。</span><span class="sxs-lookup"><span data-stu-id="1ba67-138">We haven’t set up that part of the solution yet, so you should not set the stage to **Closed Won**.</span></span>  
  
   5. <span data-ttu-id="1ba67-139">その他のオプションのフィールドの値を指定し、クリックして**保存**します。</span><span class="sxs-lookup"><span data-stu-id="1ba67-139">Specify values for other optional fields and then click **Save**.</span></span>  
  
   6. <span data-ttu-id="1ba67-140">営業案件 ページ customer1 の 、**製品**セクションで、**追加製品**します。</span><span class="sxs-lookup"><span data-stu-id="1ba67-140">On the Opportunity page for Customer1, under the **Products** section, click **Add Product**.</span></span>  
  
   7. <span data-ttu-id="1ba67-141">製品の一覧から顧客は、対象の製品を選択し、順にクリックします**選択**します。</span><span class="sxs-lookup"><span data-stu-id="1ba67-141">From the list of products, select the products that the customer is interested in, and then click **Select**.</span></span>  
  
   8. <span data-ttu-id="1ba67-142">選択した製品ごとに、クリックして、顧客が、ある数量を指定**保存**します。</span><span class="sxs-lookup"><span data-stu-id="1ba67-142">For each selected product, specify a quantity that the customer wants, and then click **Save**.</span></span>  
  
       <span data-ttu-id="1ba67-143">![営業案件に製品を追加](../core/media/bts-sf-add-product.gif "BTS_SF_Add_Product")</span><span class="sxs-lookup"><span data-stu-id="1ba67-143">![Add products to an opportunity](../core/media/bts-sf-add-product.gif "BTS_SF_Add_Product")</span></span>  
  
## <a name="create-a-salesforce-workflow"></a><span data-ttu-id="1ba67-144">Salesforce ワークフローを作成します。</span><span class="sxs-lookup"><span data-stu-id="1ba67-144">Create a Salesforce Workflow</span></span>  
 <span data-ttu-id="1ba67-145">この手順では、営業案件が正常にクローズするたびに通知を送信するワークフローを作成します。</span><span class="sxs-lookup"><span data-stu-id="1ba67-145">In this step we create a workflow to send out a notification every time an opportunity is closed successfully.</span></span> <span data-ttu-id="1ba67-146">通知は SOAP メッセージの形式し、でホストされるリレー エンドポイントに送信される[!INCLUDE[winazure](../includes/winazure-md.md)][!INCLUDE[sb](../includes/sb-md.md)]します。</span><span class="sxs-lookup"><span data-stu-id="1ba67-146">The notification is in the form of a SOAP message and is sent to a relay endpoint hosted on [!INCLUDE[winazure](../includes/winazure-md.md)][!INCLUDE[sb](../includes/sb-md.md)].</span></span>  
  
#### <a name="to-create-a-workflow-for-opportunities"></a><span data-ttu-id="1ba67-147">営業案件のワークフローを作成するには</span><span class="sxs-lookup"><span data-stu-id="1ba67-147">To create a workflow for opportunities</span></span>  
  
1. <span data-ttu-id="1ba67-148">Salesforce のポータル ページの右上隅にあるログイン名をクリックします。 をクリック**セットアップ**します。</span><span class="sxs-lookup"><span data-stu-id="1ba67-148">On the Salesforce portal, click your login name at the top right corner of the page, and then click **Setup**.</span></span>  
  
2. <span data-ttu-id="1ba67-149">左側のウィンドウで **アプリ セットアップ**、展開**作成**、展開**ワークフローおよび承認**、順にクリックします**ワークフロー ルール**します。</span><span class="sxs-lookup"><span data-stu-id="1ba67-149">In the left pane, under **App Setup**, expand **Create**, expand **Workflow & Approvals**, and then click **Workflow Rules**.</span></span>  
  
   > [!NOTE]
   >  <span data-ttu-id="1ba67-150">最初に、ワークフロー ルール ページを開いている場合は、Salesforce でのワークフローのしくみを理解するための情報が表示されます。</span><span class="sxs-lookup"><span data-stu-id="1ba67-150">If you are opening the Workflow Rules page for the first time, you will be presented with some information to understand how workflows work in Salesforce.</span></span> <span data-ttu-id="1ba67-151">情報を確認し、クリックして**続行**します。</span><span class="sxs-lookup"><span data-stu-id="1ba67-151">Read through the information and then click **Continue**.</span></span>  
  
3. <span data-ttu-id="1ba67-152">**すべてのワークフロー ルール**] ページで [**新しいルール**します。</span><span class="sxs-lookup"><span data-stu-id="1ba67-152">On the **All Workflow Rules** page, click **New Rule**.</span></span>  
  
4. <span data-ttu-id="1ba67-153">**オブジェクトの選択**一覧で、**機会**、順にクリックします**次**します。</span><span class="sxs-lookup"><span data-stu-id="1ba67-153">From the **Select Object** list, click **Opportunity**, and then click **Next**.</span></span>  
  
5. <span data-ttu-id="1ba67-154">次のページで、次のように指定します。</span><span class="sxs-lookup"><span data-stu-id="1ba67-154">In the next page, specify the following:</span></span>  
  
   1.  <span data-ttu-id="1ba67-155">設定、**ルール名**として`Closed Opportunity`します。</span><span class="sxs-lookup"><span data-stu-id="1ba67-155">Set the **Rule Name** as `Closed Opportunity`.</span></span>  
  
   2.  <span data-ttu-id="1ba67-156">設定、**評価基準**として**を作成し、その後の条件を満たすには、編集、いつ**します。</span><span class="sxs-lookup"><span data-stu-id="1ba67-156">Set the **Evaluation Criteria** as **created, and any time it’s edited to subsequently meet criteria**.</span></span>  
  
   3.  <span data-ttu-id="1ba67-157">**ルールの条件**、設定、ルールを実行するときに、**条件が満たされた**します。</span><span class="sxs-lookup"><span data-stu-id="1ba67-157">For the **Rule Criteria**, set to run the rule when the **criteria are met**.</span></span>  
  
   4.  <span data-ttu-id="1ba67-158">設定**フィールド**に**営業案件。ステージ**、**演算子**に**equals**、および**値**に`Closed Won`します。</span><span class="sxs-lookup"><span data-stu-id="1ba67-158">Set **Field** to **Opportunity: Stage**, **Operator** to **equals**, and **Value** to `Closed Won`.</span></span>  
  
        <span data-ttu-id="1ba67-159">![Salesforce ワークフローを作成する](../core/media/bts-sf-create-workflow.jpg "BTS_SF_Create_Workflow")</span><span class="sxs-lookup"><span data-stu-id="1ba67-159">![Create a Salesforce workflow](../core/media/bts-sf-create-workflow.jpg "BTS_SF_Create_Workflow")</span></span>  
  
   5.  <span data-ttu-id="1ba67-160">クリックして**保存 (&) [次へ]** します。</span><span class="sxs-lookup"><span data-stu-id="1ba67-160">Click **Save & Next**.</span></span>  
  
6. <span data-ttu-id="1ba67-161">新しいルールのワークフロー アクションを定義します。</span><span class="sxs-lookup"><span data-stu-id="1ba67-161">Define the workflow action for the new rule:</span></span>  
  
   1. <span data-ttu-id="1ba67-162">**ワークフロー アクションの指定**] ページで [**ワークフロー アクションの追加**ボタンをクリックし、をクリックし、**新しい送信メッセージ**します。</span><span class="sxs-lookup"><span data-stu-id="1ba67-162">On the **Specify Workflow Actions** page, click **Add Workflow Action** button and then click **New Outbound Message**.</span></span>  
  
   2. <span data-ttu-id="1ba67-163">設定、**名前**と**一意の名前**フィールドを`NewOp1`します。</span><span class="sxs-lookup"><span data-stu-id="1ba67-163">Set the **Name** and **Unique Name** fields to `NewOp1`.</span></span>  
  
   3. <span data-ttu-id="1ba67-164">次のように、説明を指定、`Message sent when an opportunity is successfully closed`します。</span><span class="sxs-lookup"><span data-stu-id="1ba67-164">Specify a description, such as, the `Message sent when an opportunity is successfully closed`.</span></span>  
  
   4. <span data-ttu-id="1ba67-165">指定、**エンドポイント URL**として`https://btssalesforce.servicebus.windows.net/notifications/opportunity`します。</span><span class="sxs-lookup"><span data-stu-id="1ba67-165">Specify the **Endpoint URL** as `https://btssalesforce.servicebus.windows.net/notifications/opportunity`.</span></span>  
  
       <span data-ttu-id="1ba67-166">ここでは、 **btssalesforce**は、[!INCLUDE[sb](../includes/sb-md.md)]前の手順で作成した名前空間。</span><span class="sxs-lookup"><span data-stu-id="1ba67-166">Here, **btssalesforce** is your [!INCLUDE[sb](../includes/sb-md.md)] namespace that you created in earlier steps.</span></span> <span data-ttu-id="1ba67-167">**/notifications/** はこのチュートリアルの後の手順で作成するリレーを表します。</span><span class="sxs-lookup"><span data-stu-id="1ba67-167">**/notifications/opportunity/** represents the relay that we will create in later steps of this tutorial.</span></span>  
  
      > [!NOTE]
      >  <span data-ttu-id="1ba67-168">指定する必要があります、[!INCLUDE[sb](../includes/sb-md.md)]先ほど作成した名前空間。</span><span class="sxs-lookup"><span data-stu-id="1ba67-168">You must specify the [!INCLUDE[sb](../includes/sb-md.md)] namespace that you created earlier.</span></span>  
  
   5. <span data-ttu-id="1ba67-169">確認します、**保護されたコンポーネント**チェック ボックスがオフ、**セッション ID の送信**チェック ボックスをオンします。</span><span class="sxs-lookup"><span data-stu-id="1ba67-169">Make sure the **Protected Component** check box is clear and the **Send Session ID** check box is checked.</span></span>  
  
   6. <span data-ttu-id="1ba67-170">**営業案件を送信するフィールド**から関連するフィールドを選択、**使用可能なフィールド**ボックスの一覧をクリックして、**追加**ボタンをクリックします。</span><span class="sxs-lookup"><span data-stu-id="1ba67-170">For **Opportunity fields to send** select the relevant fields from the **Available Fields** list and then click the **Add** button.</span></span>  
  
   7. <span data-ttu-id="1ba67-171">クリックして**保存**順にクリックします**完了**します。</span><span class="sxs-lookup"><span data-stu-id="1ba67-171">Click **Save** and then click **Done**.</span></span>  
  
   8. <span data-ttu-id="1ba67-172">左側のウィンドウで **アプリ セットアップ**、展開**作成**、展開**ワークフローおよび承認**、順にクリックします**ワークフロー ルール**します。</span><span class="sxs-lookup"><span data-stu-id="1ba67-172">In the left pane, under **App Setup**, expand **Create**, expand **Workflow & Approvals**, and then click **Workflow Rules**.</span></span> <span data-ttu-id="1ba67-173">いることを確認、**クローズされた営業案件**ルールが表示されます。</span><span class="sxs-lookup"><span data-stu-id="1ba67-173">Verify that the **Closed Opportunity** rule is listed there.</span></span> <span data-ttu-id="1ba67-174">、**アクション**の列、**クローズされた営業案件**ルールで、**アクティブ化**ルールを有効にします。</span><span class="sxs-lookup"><span data-stu-id="1ba67-174">Under the **Action** column for the **Closed Opportunity** rule, click **Activate** to activate the rule.</span></span>  
  
## <a name="create-a-salesforce-connected-application"></a><span data-ttu-id="1ba67-175">Salesforce を作成するアプリケーションの接続</span><span class="sxs-lookup"><span data-stu-id="1ba67-175">Create a Salesforce Connected Application</span></span>  
 <span data-ttu-id="1ba67-176">接続されているアプリケーション定義を作成するには、Salesforce に接続するための OAuth トークンを要求するために必要なキーのセットが生成されます。</span><span class="sxs-lookup"><span data-stu-id="1ba67-176">Creating a connected application definition generates a set of keys required to request OAuth tokens to access to connect to Salesforce.</span></span> <span data-ttu-id="1ba67-177">このチュートリアルの後のステージで[!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)]接続されているアプリケーション定義を使用して Salesforce にクエリを接続しているアプリケーションになります。</span><span class="sxs-lookup"><span data-stu-id="1ba67-177">In the later stages of this tutorial, [!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)] will be the connected application that queries Salesforce using the connected application definition.</span></span>  
  
#### <a name="to-create-a-connected-application-for-salesforce"></a><span data-ttu-id="1ba67-178">Salesforce に接続されているアプリケーションを作成するには</span><span class="sxs-lookup"><span data-stu-id="1ba67-178">To create a connected application for Salesforce</span></span>  
  
1. <span data-ttu-id="1ba67-179">Salesforce のポータル ページの右上隅にあるログイン名をクリックします。 をクリック**セットアップ**します。</span><span class="sxs-lookup"><span data-stu-id="1ba67-179">On the Salesforce portal, click your login name at the top right corner of the page, and then click **Setup**.</span></span>  
  
2. <span data-ttu-id="1ba67-180">左側のウィンドウで **アプリ セットアップ**、展開**作成**、順に展開**アプリ**します。</span><span class="sxs-lookup"><span data-stu-id="1ba67-180">In the left pane, under **App Setup**, expand **Create**, and then expand **Apps**.</span></span> <span data-ttu-id="1ba67-181">**アプリ**ページの**接続アプリ**セクションで、**新規**します。</span><span class="sxs-lookup"><span data-stu-id="1ba67-181">On the **Apps** page, under the **Connected Apps** section, click **New**.</span></span>  
  
3. <span data-ttu-id="1ba67-182">**新しい接続アプリケーション** ページで、次を指定します。</span><span class="sxs-lookup"><span data-stu-id="1ba67-182">In the **New Connection App** page, specify the following:</span></span>  
  
   1. <span data-ttu-id="1ba67-183">**接続型アプリケーション名**、指定`BizTalk_Salesforce`します。</span><span class="sxs-lookup"><span data-stu-id="1ba67-183">For **Connected App Name**, specify `BizTalk_Salesforce`.</span></span>  
  
   2. <span data-ttu-id="1ba67-184">**開発者名**名前に、ログを指定します。</span><span class="sxs-lookup"><span data-stu-id="1ba67-184">For **Developer Name**, specify your log on name.</span></span>  
  
   3. <span data-ttu-id="1ba67-185">**Contact Email**電子メールを指定します。</span><span class="sxs-lookup"><span data-stu-id="1ba67-185">For **Contact Email**, specify your e-mail.</span></span>  
  
   4. <span data-ttu-id="1ba67-186">**コールバック URL**、有効な URL を指定します。</span><span class="sxs-lookup"><span data-stu-id="1ba67-186">For **Callback URL**, specify a valid URL.</span></span>  
  
      > [!NOTE]
      >  <span data-ttu-id="1ba67-187">このシナリオでは、Salesforce での認証方法、ためここで指定する値は使用されません。</span><span class="sxs-lookup"><span data-stu-id="1ba67-187">Because of the way we authenticate with Salesforce in this scenario, the value you specify here is not used.</span></span>  
  
   5. <span data-ttu-id="1ba67-188">**使用可能な OAuth スコープ**を選択します**フル アクセス**、 **、いつでも、あなたに代わって要求を実行**、および**アクセスデータと管理** をクリックし、**追加**に移動するボタン、 **OAuth スコープの選択**します。</span><span class="sxs-lookup"><span data-stu-id="1ba67-188">Under **Available OAuth Scopes**, select **Full access**, **Perform requests on your behalf at any time**, and **Access and manage your data** and then click the **Add** button to move them into the **Selected OAuth Scopes**.</span></span>  
  
   6. <span data-ttu-id="1ba67-189">**[保存]** をクリックします。</span><span class="sxs-lookup"><span data-stu-id="1ba67-189">Click **Save**.</span></span> <span data-ttu-id="1ba67-190">表示されるページに関する情報を格納する、**コンシューマー キー**と**コンシューマー シークレット**します。</span><span class="sxs-lookup"><span data-stu-id="1ba67-190">The page that appears contains information about the **Consumer Key** and **Consumer Secret**.</span></span> <span data-ttu-id="1ba67-191">これらの値をメモしてをおく必要があります。</span><span class="sxs-lookup"><span data-stu-id="1ba67-191">You must make a note of these values.</span></span> <span data-ttu-id="1ba67-192">これらの値から Salesforce に接続中に必要になります[!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)]します。</span><span class="sxs-lookup"><span data-stu-id="1ba67-192">You will need these values while connecting to Salesforce from [!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)].</span></span>  
  
       <span data-ttu-id="1ba67-193">![Salesforce へのアクセスのキーを](../core/media/bts-sf-consumer-keys.jpg "BTS_SF_Consumer_Keys")</span><span class="sxs-lookup"><span data-stu-id="1ba67-193">![Keys for Salesforce access](../core/media/bts-sf-consumer-keys.jpg "BTS_SF_Consumer_Keys")</span></span>  
  
4. <span data-ttu-id="1ba67-194">最後に、不明なネットワークの場所から Salesforce に接続するために必要なセキュリティ トークンを生成します。</span><span class="sxs-lookup"><span data-stu-id="1ba67-194">Finally, generate a security token required for connecting to Salesforce from unknown network locations.</span></span>  
  
   1.  <span data-ttu-id="1ba67-195">Salesforce ポータルの左側のウィンドウで **個人セットアップ**、展開**個人情報**、順にクリックします**Reset My Security Token**します。</span><span class="sxs-lookup"><span data-stu-id="1ba67-195">On the left pane of the Salesforce portal, under **Personal Setup**, expand **Personal Information**, and then click **Reset My Security Token**.</span></span>  
  
   2.  <span data-ttu-id="1ba67-196">警告を確認し、クリックして**セキュリティ トークンのリセット**します。</span><span class="sxs-lookup"><span data-stu-id="1ba67-196">Read the warning and then click **Reset Security Token**.</span></span>  
  
   3.  <span data-ttu-id="1ba67-197">Salesforce アカウントを作成するときに指定した電子メール アドレスでセキュリティ トークンを受信する必要があります。</span><span class="sxs-lookup"><span data-stu-id="1ba67-197">You should receive the security token at the e-mail address you specified while creating your Salesforce account.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="1ba67-198">参照</span><span class="sxs-lookup"><span data-stu-id="1ba67-198">See Also</span></span>  
 [<span data-ttu-id="1ba67-199">チュートリアル 6:BizTalk Server 2013 を Salesforce と統合します。</span><span class="sxs-lookup"><span data-stu-id="1ba67-199">Tutorial 6: Integrating BizTalk Server 2013 with Salesforce</span></span>](Tutorial:%20Integrating%20BizTalk%20Server%202013%20with%20Salesforce.md)