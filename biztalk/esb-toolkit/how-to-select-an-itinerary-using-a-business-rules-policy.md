---
title: '方法: ビジネス ルール ポリシーを使用して、日程の選択 |Microsoft ドキュメント'
ms.custom: ''
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: ''
ms.suite: ''
ms.tgt_pltfrm: ''
ms.topic: article
ms.assetid: 9f6373a8-d9d6-46c6-95e3-f62dd33c342a
caps.latest.revision: 4
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: 521b3768251cfcd31defe271a21d4b2d0bc771e6
ms.sourcegitcommit: 3fc338e52d5dbca2c3ea1685a2faafc7582fe23a
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 12/01/2017
ms.locfileid: "26010587"
---
# <a name="how-to-select-an-itinerary-using-a-business-rules-policy"></a><span data-ttu-id="3e162-102">方法: ビジネス ルール ポリシーを使用して、日程を選択</span><span class="sxs-lookup"><span data-stu-id="3e162-102">How to: Select an Itinerary Using a Business Rules Policy</span></span>
## <a name="goal"></a><span data-ttu-id="3e162-103">[目標]</span><span class="sxs-lookup"><span data-stu-id="3e162-103">Goal</span></span>  
 <span data-ttu-id="3e162-104">このセクションでは、受信したメッセージの内容に基づく日程を選択するために使用するビジネス ルールを作成する方法と、汎用 itinerary 入り口をこれらのルールを呼び出す内行程セレクター パイプライン コンポーネントを構成する方法を示します。</span><span class="sxs-lookup"><span data-stu-id="3e162-104">This section demonstrates how to create business rules that can be used to select an itinerary based on the content of a received message and how to configure the Itinerary Selector pipeline component within a generic itinerary on-ramp to call these rules.</span></span> <span data-ttu-id="3e162-105">このセクションをメッセージのルーティングが異なり、顧客が存在する領域に基づいたビジネス シナリオについて説明します。</span><span class="sxs-lookup"><span data-stu-id="3e162-105">This section describes a business scenario in which messages are routed differently, based on the region in which the customer resides.</span></span>  
  
 <span data-ttu-id="3e162-106">このトピックでは、次の手順を行います。</span><span class="sxs-lookup"><span data-stu-id="3e162-106">In this How-to topic, you will complete the following steps:</span></span>  
  
-   <span data-ttu-id="3e162-107">グローバル銀行の顧客の Western と東部部門の日程をモデル。</span><span class="sxs-lookup"><span data-stu-id="3e162-107">Model itineraries for the Western and Eastern divisions of customer Global Bank.</span></span>  
  
-   <span data-ttu-id="3e162-108">要求の処理の日程を選択するために使用するビジネス ルール ポリシーを作成します。</span><span class="sxs-lookup"><span data-stu-id="3e162-108">Create business rules policies that will be used to select an itinerary for processing request.</span></span>  
  
-   <span data-ttu-id="3e162-109">ビジネス ルール ポリシーを使用して、適切な旅程を選択、行程セレクター パイプライン コンポーネントを構成します。</span><span class="sxs-lookup"><span data-stu-id="3e162-109">Configure the Itinerary Selector pipeline component to use a business rules policy to select the appropriate itinerary.</span></span>  
  
## <a name="prerequisites"></a><span data-ttu-id="3e162-110">前提条件</span><span class="sxs-lookup"><span data-stu-id="3e162-110">Prerequisites</span></span>  
 <span data-ttu-id="3e162-111">この操作方法に関するトピックの手順の完了が必要、[開発活動の前提条件](../esb-toolkit/prerequisites-for-the-development-activities.md)です。</span><span class="sxs-lookup"><span data-stu-id="3e162-111">The procedures in this How-to topic require the completion of the [Prerequisites for the Development Activities](../esb-toolkit/prerequisites-for-the-development-activities.md).</span></span>  
  
## <a name="before-you-begin"></a><span data-ttu-id="3e162-112">はじめに</span><span class="sxs-lookup"><span data-stu-id="3e162-112">Before You Begin</span></span>  
 <span data-ttu-id="3e162-113">このトピックの「操作方法に関する手順を実行する前に、次のタスクを実行します。</span><span class="sxs-lookup"><span data-stu-id="3e162-113">Complete the following tasks before you perform the steps later in this How-to topic:</span></span>  
  
-   <span data-ttu-id="3e162-114">GlobalBank 西部テスト メッセージを作成します。</span><span class="sxs-lookup"><span data-stu-id="3e162-114">Create the GlobalBank West test message.</span></span>  
  
-   <span data-ttu-id="3e162-115">GlobalBank 東部テスト メッセージを作成します。</span><span class="sxs-lookup"><span data-stu-id="3e162-115">Create the GlobalBank East test message.</span></span>  
  
 <span data-ttu-id="3e162-116">次の手順では、これらの各を行う方法について説明します。</span><span class="sxs-lookup"><span data-stu-id="3e162-116">The following procedures describe how to do each of these.</span></span>  
  
#### <a name="to-create-the-globalbank-west-test-message"></a><span data-ttu-id="3e162-117">GlobalBank 西部テスト メッセージを作成するには</span><span class="sxs-lookup"><span data-stu-id="3e162-117">To create the GlobalBank West test message</span></span>  
  
1.  <span data-ttu-id="3e162-118">Windows エクスプローラで、C:\HowTos を参照します。</span><span class="sxs-lookup"><span data-stu-id="3e162-118">In Windows Explorer, browse to C:\HowTos.</span></span>  
  
2.  <span data-ttu-id="3e162-119">NAOrderDoc.xml のコピーを作成し、コピー West.xml を名前します。</span><span class="sxs-lookup"><span data-stu-id="3e162-119">Create a copy of NAOrderDoc.xml, and then name the copy West.xml.</span></span>  
  
3.  <span data-ttu-id="3e162-120">メモ帳で、West.xml を開きの値を変更、 **customerName**要素**GlobalBankWest**です。</span><span class="sxs-lookup"><span data-stu-id="3e162-120">In Notepad, open West.xml, and then change the value of the **customerName** element to **GlobalBankWest**.</span></span>  
  
4.  <span data-ttu-id="3e162-121">Utf-8 として West.xml を保存し、メモ帳を閉じます。</span><span class="sxs-lookup"><span data-stu-id="3e162-121">Save West.xml as UTF-8, and then close Notepad.</span></span>  
  
#### <a name="to-create-the-globalbank-east-test-message"></a><span data-ttu-id="3e162-122">GlobalBank 東部テスト メッセージを作成するには</span><span class="sxs-lookup"><span data-stu-id="3e162-122">To create the GlobalBank East test message</span></span>  
  
1.  <span data-ttu-id="3e162-123">Windows エクスプローラで、C:\HowTos を参照します。</span><span class="sxs-lookup"><span data-stu-id="3e162-123">In Windows Explorer, browse to C:\HowTos.</span></span>  
  
2.  <span data-ttu-id="3e162-124">NAOrderDoc.xml のコピーを作成し、コピー East.xml を名前します。</span><span class="sxs-lookup"><span data-stu-id="3e162-124">Create a copy of NAOrderDoc.xml, and then name the copy East.xml.</span></span>  
  
3.  <span data-ttu-id="3e162-125">メモ帳で、East.xml を開きの値を変更、 **customerName**要素**GlobalBankEast**です。</span><span class="sxs-lookup"><span data-stu-id="3e162-125">In Notepad, open East.xml, and then change the value of the **customerName** element to **GlobalBankEast**.</span></span>  
  
4.  <span data-ttu-id="3e162-126">Utf-8 として East.xml を保存し、メモ帳を閉じます。</span><span class="sxs-lookup"><span data-stu-id="3e162-126">Save East.xml as UTF-8, and then close Notepad.</span></span>  
  
## <a name="steps"></a><span data-ttu-id="3e162-127">手順</span><span class="sxs-lookup"><span data-stu-id="3e162-127">Steps</span></span>  
  
#### <a name="to-create-a-business-rules-engine-bre-policy-to-select-an-itinerary-using-custom-message-properties"></a><span data-ttu-id="3e162-128">カスタム メッセージ プロパティを使用して、日程を選択するビジネス ルール エンジン (BRE) ポリシーを作成するには</span><span class="sxs-lookup"><span data-stu-id="3e162-128">To create a Business Rules Engine (BRE) policy to select an itinerary using custom message properties</span></span>  
  
1.  <span data-ttu-id="3e162-129">をクリックして**開始**タスク バーで、をポイント**すべてのプログラム**、 をポイント**BizTalk Server**、順にクリック**ビジネス ルール作成ツール**です。</span><span class="sxs-lookup"><span data-stu-id="3e162-129">Click **Start** on the taskbar, point to **All Programs**, point to **BizTalk Server**, and then click **Business Rule Composer**.</span></span>  
  
2.  <span data-ttu-id="3e162-130">ポリシー エクスプ ローラーで右クリック**ポリシー**、クリックして**新しいポリシーの追加**です。</span><span class="sxs-lookup"><span data-stu-id="3e162-130">In Policy Explorer, right-click **Policies**, and then click **Add New Policy**.</span></span> <span data-ttu-id="3e162-131">ポリシーに名前**ResolveItineraryBasedOnCustomer**です。</span><span class="sxs-lookup"><span data-stu-id="3e162-131">Name the policy **ResolveItineraryBasedOnCustomer**.</span></span>  
  
    > [!NOTE]
    >  <span data-ttu-id="3e162-132">この操作方法に関するトピック」で作成されたものと同じビジネス ルール ポリシーと旅程を使用して[する方法: インターチェンジを分割し、結果として得られるメッセージをルーティング、複数ファイルの場所を使用して個別旅程](../esb-toolkit/split-an-interchange-and-route-messages-to-multiple-locations-using-itineraries.md)です。</span><span class="sxs-lookup"><span data-stu-id="3e162-132">This How-to topic uses the same business rules policy and itineraries as those created in the topic [How to: Split an Interchange and Route the Resulting Messages to Multiple File Locations Using Distinct Itineraries](../esb-toolkit/split-an-interchange-and-route-messages-to-multiple-locations-using-itineraries.md).</span></span> <span data-ttu-id="3e162-133">そのセクションを完了している場合は、このトピックの「"を作成し、ESB 入り口を構成する」の手順にスキップできます。</span><span class="sxs-lookup"><span data-stu-id="3e162-133">If you have already completed that section, you can skip to the procedure, "To create and configure an ESB on-ramp" later in this topic.</span></span>  
  
#### <a name="to-add-a-selection-rule-for-customer-globalbank-west"></a><span data-ttu-id="3e162-134">GlobalBank 西部の顧客の選択ルールを追加するには</span><span class="sxs-lookup"><span data-stu-id="3e162-134">To add a selection rule for customer GlobalBank West</span></span>  
  
1.  <span data-ttu-id="3e162-135">**ResolveItineraryBasedOnCustomer**ポリシーを右クリックして**バージョン 1.0 (未保存)**、順にクリック**新しいルールの追加**です。</span><span class="sxs-lookup"><span data-stu-id="3e162-135">In the **ResolveItineraryBasedOnCustomer** policy, right-click **Version 1.0 (not saved)**, and then click **Add New Rule**.</span></span> <span data-ttu-id="3e162-136">ルールの名前として**SetGlobalBankWestItinerary**です。</span><span class="sxs-lookup"><span data-stu-id="3e162-136">Name the rule **SetGlobalBankWestItinerary**.</span></span>  
  
2.  <span data-ttu-id="3e162-137">ファクト エクスプ ローラーで、をクリックして、 **XML スキーマ** タブを右クリックして**スキーマ**、クリックして**参照**です。</span><span class="sxs-lookup"><span data-stu-id="3e162-137">In Facts Explorer, click the **XML Schemas** tab, right-click **Schemas**, and then click **Browse**.</span></span>  
  
3.  <span data-ttu-id="3e162-138">**スキーマ ファイル** ダイアログ ボックスで、C:\Projects\Microsoft.Practices.ESB\Source\Samples\DynamicResolution\Source\ESB を参照します。DynamicResolution.Schemas、select **NAOrderDoc.xsd**、クリックして**開く**です。</span><span class="sxs-lookup"><span data-stu-id="3e162-138">In the **Schema Files** dialog box, browse to C:\Projects\Microsoft.Practices.ESB\Source\Samples\DynamicResolution\Source\ESB.DynamicResolution.Schemas, select **NAOrderDoc.xsd**, and then click **Open**.</span></span>  
  
    > [!NOTE]
    >  <span data-ttu-id="3e162-139">これは、テストに使用する左右のメッセージを作成するために使用された NAOrderDoc.xml メッセージを定義するスキーマです。</span><span class="sxs-lookup"><span data-stu-id="3e162-139">This is the schema that defines the NAOrderDoc.xml message, which was used to create the West and East messages you will use for testing.</span></span>  
  
4.  <span data-ttu-id="3e162-140">ファクト エクスプ ローラーでクリックして**NAOrderDoc.xsd**をクリックして、**ドキュメントの種類**のプロパティ] ウィンドウと [入力プロパティ**GlobalBank.ESB.DynamicResolution.Schemas.NAOrderDoc**.</span><span class="sxs-lookup"><span data-stu-id="3e162-140">In Facts Explorer, click **NAOrderDoc.xsd**, click the **Document Type** property in the Properties pane, and then type **GlobalBank.ESB.DynamicResolution.Schemas.NAOrderDoc**.</span></span>  
  
    > [!NOTE]
    >  <span data-ttu-id="3e162-141">これは、スキーマの完全修飾名です。</span><span class="sxs-lookup"><span data-stu-id="3e162-141">This is the fully qualified name of the schema.</span></span>  
  
5.  <span data-ttu-id="3e162-142">ファクト エクスプ ローラーで、 **NAOrderDoc.xsd**の順に展開および**OrderDoc**です。</span><span class="sxs-lookup"><span data-stu-id="3e162-142">In Facts Explorer, expand **NAOrderDoc.xsd**, and then expand **OrderDoc**.</span></span>  
  
6.  <span data-ttu-id="3e162-143">ルール ウィンドウで、右クリック**条件**、 をポイント**述語**、順にクリック**等しい**です。</span><span class="sxs-lookup"><span data-stu-id="3e162-143">In the Rule window, right-click **Conditions**, point to **Predicates**, and then click **Equal**.</span></span>  
  
7.  <span data-ttu-id="3e162-144">ファクト エクスプ ローラーからドラッグして、 **customerName**要素を**argument1**ノードの下**条件**です。</span><span class="sxs-lookup"><span data-stu-id="3e162-144">From Facts Explorer, drag the **customerName** element to the **argument1** node under **Conditions**.</span></span>  
  
8.  <span data-ttu-id="3e162-145">をクリックして、 **argument2**ノード、および入力**GlobalBankWest**です。</span><span class="sxs-lookup"><span data-stu-id="3e162-145">Click the **argument2** node, and then type **GlobalBankWest**.</span></span>  
  
9. <span data-ttu-id="3e162-146">ファクト エクスプ ローラーで、をクリックして、**ボキャブラリ**タブです。展開して、 **ESB です。行程**ボキャブラリ、展開**バージョン 1.1**、し、ドラッグ、**行程名の設定**定義**アクション**です。</span><span class="sxs-lookup"><span data-stu-id="3e162-146">In Facts Explorer, click the **Vocabularies** tab. Expand the **ESB.Itinerary** vocabulary, expand **Version 1.1**, and then drag the **Set Itinerary Name** definition to **Actions**.</span></span>  
  
10. <span data-ttu-id="3e162-147">をクリックして**\<空の文字列\>**、し、入力**GlobalBankWestItinerary**です。</span><span class="sxs-lookup"><span data-stu-id="3e162-147">Click **\<empty string\>**, and then type **GlobalBankWestItinerary**.</span></span>  
  
    > [!NOTE]
    >  <span data-ttu-id="3e162-148">このトピックの後半 GlobalBank 西からメッセージを処理するこの日程を作成します。</span><span class="sxs-lookup"><span data-stu-id="3e162-148">Later in this How-to topic, you will create this itinerary to process messages from GlobalBank West.</span></span>  
  
#### <a name="to-add-a-selection-rule-for-customer-globalbank-east"></a><span data-ttu-id="3e162-149">GlobalBank 東部の顧客の選択ルールを追加するには</span><span class="sxs-lookup"><span data-stu-id="3e162-149">To add a selection rule for Customer GlobalBank East</span></span>  
  
1.  <span data-ttu-id="3e162-150">ポリシー エクスプ ローラーで右クリックし、 **SetGlobalBankWestItinerary**ルールは、クリックして**コピー**です。</span><span class="sxs-lookup"><span data-stu-id="3e162-150">In Policy Explorer, right-click the **SetGlobalBankWestItinerary** rule, and then click **Copy**.</span></span>  
  
2.  <span data-ttu-id="3e162-151">右クリック**バージョン 1.0 (未保存)**、クリックして**貼り付け**です。</span><span class="sxs-lookup"><span data-stu-id="3e162-151">Right-click **Version 1.0 (not saved)**, and then click **Paste**.</span></span>  
  
3.  <span data-ttu-id="3e162-152">**新しいルールの名前** ダイアログ ボックスで、「 **SetGlobalBankEastItinerary**、順にクリック**OK**です。</span><span class="sxs-lookup"><span data-stu-id="3e162-152">In the **New Rule Name** dialog box, type **SetGlobalBankEastItinerary**, and then click **OK**.</span></span>  
  
4.  <span data-ttu-id="3e162-153">ポリシー エクスプ ローラーで、をクリックして、 **SetGlobalBankEastItinerary**ルール。</span><span class="sxs-lookup"><span data-stu-id="3e162-153">In Policy Explorer, click the **SetGlobalBankEastItinerary** rule.</span></span>  
  
5.  <span data-ttu-id="3e162-154">**条件**セクションを右クリックして**GlobalBankWest**、クリックして**引数の再設定**です。</span><span class="sxs-lookup"><span data-stu-id="3e162-154">In the **Conditions** section, right-click **GlobalBankWest**, and then click **Reset argument**.</span></span>  
  
6.  <span data-ttu-id="3e162-155">をクリックして**argument2**、し、入力**GlobalBankEast**です。</span><span class="sxs-lookup"><span data-stu-id="3e162-155">Click **argument2**, and then type **GlobalBankEast**.</span></span>  
  
7.  <span data-ttu-id="3e162-156">**アクション**セクションを右クリックして**GlobalBankWestItinerary**、クリックして**引数の再設定**です。</span><span class="sxs-lookup"><span data-stu-id="3e162-156">In the **Actions** section, right-click **GlobalBankWestItinerary**, and then click **Reset argument**.</span></span>  
  
8.  <span data-ttu-id="3e162-157">をクリックして**\<空の文字列\>** し入力**GlobalBankEastItinerary**です。</span><span class="sxs-lookup"><span data-stu-id="3e162-157">Click **\<empty string\>** and then type **GlobalBankEastItinerary**.</span></span>  
  
    > [!NOTE]
    >  <span data-ttu-id="3e162-158">操作方法に関するトピックの後半 GlobalBank 東部からメッセージを処理するこの行程を作成します。</span><span class="sxs-lookup"><span data-stu-id="3e162-158">Later in the How-to topic, you will create this itinerary to process messages from GlobalBank East.</span></span>  
  
#### <a name="to-publish-and-deploy-the-policy"></a><span data-ttu-id="3e162-159">発行して、ポリシーを展開するには</span><span class="sxs-lookup"><span data-stu-id="3e162-159">To publish and deploy the policy</span></span>  
  
1.  <span data-ttu-id="3e162-160">ポリシー エクスプ ローラーで、、 **ResolveItineraryBasedOnCustomer**ポリシーを右クリック**バージョン 1.0 (未保存)**、クリックして**発行**です。</span><span class="sxs-lookup"><span data-stu-id="3e162-160">In Policy Explorer, under the **ResolveItineraryBasedOnCustomer** policy, right click **Version 1.0 (not saved)**, and then click **Publish**.</span></span>  
  
2.  <span data-ttu-id="3e162-161">ポリシー エクスプ ローラーで、、 **ResolveItineraryBasedOnCustomer**ポリシーを右クリック**バージョン 1.0 - 公開済み**、クリックして**展開**です。</span><span class="sxs-lookup"><span data-stu-id="3e162-161">In Policy Explorer, under the **ResolveItineraryBasedOnCustomer** policy, right click **Version 1.0 - Published**, and then click **Deploy**.</span></span>  
  
#### <a name="to-create-an-esb-itinerary-domain-specific-language-dsl-model-for-globalbank-west-messages"></a><span data-ttu-id="3e162-162">GlobalBank 西部メッセージの ESB itinerary ドメイン固有言語 (DSL) モデルを作成するには</span><span class="sxs-lookup"><span data-stu-id="3e162-162">To create an ESB itinerary domain-specific language (DSL) model for GlobalBank West messages</span></span>  
  
1.  <span data-ttu-id="3e162-163">Visual Studio で、C:\HowTos\Patterns\Patterns.sln を開きます。</span><span class="sxs-lookup"><span data-stu-id="3e162-163">In Visual Studio, open C:\HowTos\Patterns\Patterns.sln.</span></span>  
  
2.  <span data-ttu-id="3e162-164">ソリューション エクスプ ローラーで右クリックし、 **ItineraryLibrary**プロジェクトをポイントし、**追加**、クリックして**新しい行程**です。</span><span class="sxs-lookup"><span data-stu-id="3e162-164">In Solution Explorer, right-click the **ItineraryLibrary** project, point to **Add**, and then click **New Itinerary**.</span></span>  
  
3.  <span data-ttu-id="3e162-165">**新しい項目の追加**ダイアログ ボックスの [テンプレート] ペインで、クリックして**ItineraryDsl**です。</span><span class="sxs-lookup"><span data-stu-id="3e162-165">In the **Add New Item** dialog box, in the Templates pane, click **ItineraryDsl**.</span></span>  
  
4.  <span data-ttu-id="3e162-166">**名前**ボックスに、入力**GlobalBankWestItinerary**、クリックして**追加**です。</span><span class="sxs-lookup"><span data-stu-id="3e162-166">In the **Name** box, type **GlobalBankWestItinerary**, and then click **Add**.</span></span>  
  
#### <a name="to-configure-the-properties-of-the-globalbank-west-itinerary"></a><span data-ttu-id="3e162-167">GlobalBank 西部旅行計画のプロパティを構成するには</span><span class="sxs-lookup"><span data-stu-id="3e162-167">To configure the properties of the GlobalBank West itinerary</span></span>  
  
1.  <span data-ttu-id="3e162-168">Visual Studio でのデザイン画面をクリックして**GlobalBankWestItinerary.itinerary**です。</span><span class="sxs-lookup"><span data-stu-id="3e162-168">In Visual Studio, click the design surface of **GlobalBankWestItinerary.itinerary**.</span></span> <span data-ttu-id="3e162-169">**GlobalBankWestItinerary**プロパティ ウィンドウで、次のプロパティを構成します。</span><span class="sxs-lookup"><span data-stu-id="3e162-169">In the **GlobalBankWestItinerary** Properties window, configure the following properties:</span></span>  
  
    1.  <span data-ttu-id="3e162-170">**モデル エクスポーター**ドロップダウン リストをクリックして**データベース行程エクスポーター**です。</span><span class="sxs-lookup"><span data-stu-id="3e162-170">In the **Model Exporter** drop-down list, click **Database Itinerary Exporter**.</span></span>  
  
    2.  <span data-ttu-id="3e162-171">横にある省略記号ボタン (...) をクリックして、**行程データベース**プロパティです。</span><span class="sxs-lookup"><span data-stu-id="3e162-171">Click the ellipsis button (...) next to the **Itinerary Database** property.</span></span>  
  
    3.  <span data-ttu-id="3e162-172">**接続プロパティ**ダイアログ ボックスで、itinerary リポジトリ データベースをホストする SQL Server を選択し、データベースの名前を指定 (既定の名前は**EsbItineraryDb**)。</span><span class="sxs-lookup"><span data-stu-id="3e162-172">In the **Connection Properties** dialog box, choose the SQL Server that hosts the itinerary repository database, and then specify the name of the database (the default name is **EsbItineraryDb**).</span></span>  
  
2.  <span data-ttu-id="3e162-173">**行程ステータス**ドロップダウン リストをクリックして**配置済み**です。</span><span class="sxs-lookup"><span data-stu-id="3e162-173">In the **Itinerary Status** drop-down list, click **Deployed**.</span></span>  
  
    > [!NOTE]
    >  <span data-ttu-id="3e162-174">この手順では、; の中央リポジトリに旅行計画をエクスポートできます。日程を選択し、メッセージの受信時にこのリポジトリからアタッチされます。</span><span class="sxs-lookup"><span data-stu-id="3e162-174">This step enables you to export the itinerary to a central repository; itineraries can be selected and attached from this repository upon message reception.</span></span> <span data-ttu-id="3e162-175">後で、ビジネス ルール エンジンは、(BRI) 競合回避モジュールを使用して受信メッセージを評価し、このリポジトリから適切な旅程を選択する行程セレクター パイプライン コンポーネントを構成します。</span><span class="sxs-lookup"><span data-stu-id="3e162-175">You will later configure the Itinerary Selector pipeline component to use the Business Rules Engine resolver (BRI) to evaluate inbound messages and select the appropriate itinerary from this repository.</span></span>  
  
#### <a name="to-define-the-structure-of-the-itinerary"></a><span data-ttu-id="3e162-176">旅行計画の構造を定義するには</span><span class="sxs-lookup"><span data-stu-id="3e162-176">To define the structure of the itinerary</span></span>  
  
1.  <span data-ttu-id="3e162-177">ツールボックスからドラッグして、**入り口**デザイン画面にモデル要素。</span><span class="sxs-lookup"><span data-stu-id="3e162-177">From the Toolbox, drag an **On-Ramp** model element to the design surface.</span></span> <span data-ttu-id="3e162-178">**OnRamp1**プロパティ ウィンドウで、次のプロパティを構成します。</span><span class="sxs-lookup"><span data-stu-id="3e162-178">In the **OnRamp1** Properties window, configure the following properties:</span></span>  
  
    1.  <span data-ttu-id="3e162-179">クリックして、**名前**プロパティ、および入力**ReceiveNAOrder**です。</span><span class="sxs-lookup"><span data-stu-id="3e162-179">Click the **Name** property, and then type **ReceiveNAOrder**.</span></span>  
  
    2.  <span data-ttu-id="3e162-180">**Extender**ドロップダウン リストをクリックして**入り口 ESB サービス拡張**です。</span><span class="sxs-lookup"><span data-stu-id="3e162-180">In the **Extender** drop-down list, click **On-Ramp ESB Service Extension**.</span></span>  
  
    3.  <span data-ttu-id="3e162-181">**BizTalk アプリケーション**ドロップダウン リストをクリックして**Microsoft.Practices.ESB**です。</span><span class="sxs-lookup"><span data-stu-id="3e162-181">In the **BizTalk Application** drop-down list, click **Microsoft.Practices.ESB**.</span></span>  
  
    4.  <span data-ttu-id="3e162-182">**受信ポート**ドロップダウン リストをクリックして**OnRamp.Itinerary**です。</span><span class="sxs-lookup"><span data-stu-id="3e162-182">In the **Receive Port** drop-down list, click **OnRamp.Itinerary**.</span></span>  
  
2.  <span data-ttu-id="3e162-183">ツールボックスからドラッグして、**出口**デザイン画面に要素をモデル化の右側に配置し、 **ReceiveNAOrder**モデル要素。</span><span class="sxs-lookup"><span data-stu-id="3e162-183">From the Toolbox, drag an **Off-Ramp** model element to the design surface, and then place it to the right of the **ReceiveNAOrder** model element.</span></span> <span data-ttu-id="3e162-184">**OffRamp1**プロパティ ウィンドウで、次のプロパティを構成します。</span><span class="sxs-lookup"><span data-stu-id="3e162-184">In the **OffRamp1** Properties window, configure the following properties:</span></span>  
  
    1.  <span data-ttu-id="3e162-185">クリックして、**名前**プロパティ、および入力**SendNAOrder**です。</span><span class="sxs-lookup"><span data-stu-id="3e162-185">Click the **Name** property, and then type **SendNAOrder**.</span></span>  
  
    2.  <span data-ttu-id="3e162-186">**Extender**ドロップダウン リストをクリックして**出口 ESB サービス拡張**です。</span><span class="sxs-lookup"><span data-stu-id="3e162-186">In the **Extender** drop-down list, click **Off-Ramp ESB Service Extension**.</span></span>  
  
    3.  <span data-ttu-id="3e162-187">**BizTalk アプリケーション**ドロップダウン リストをクリックして**GlobalBank.ESB**です。</span><span class="sxs-lookup"><span data-stu-id="3e162-187">In the **BizTalk Application** drop-down list, click **GlobalBank.ESB**.</span></span>  
  
    4.  <span data-ttu-id="3e162-188">**送信ポート**ドロップダウン リストをクリックして**DynamicResolutionOneWay**です。</span><span class="sxs-lookup"><span data-stu-id="3e162-188">In the **Send Port** drop-down list, click **DynamicResolutionOneWay**.</span></span>  
  
3.  <span data-ttu-id="3e162-189">ツールボックスからドラッグ、**行程サービス**モデルをデザイン画面に要素との間に配置し、 **ReceiveNAOrder**モデル要素と**SendNAOrder**モデル要素。</span><span class="sxs-lookup"><span data-stu-id="3e162-189">From the Toolbox, drag an **Itinerary Service** model element to the design surface, and then place it between the **ReceiveNAOrder** model element and the **SendNAOrder** model element.</span></span> <span data-ttu-id="3e162-190">**ItineraryService1**プロパティ ウィンドウで、次のプロパティを構成します。</span><span class="sxs-lookup"><span data-stu-id="3e162-190">In the **ItineraryService1** Properties window, configure the following properties:</span></span>  
  
    1.  <span data-ttu-id="3e162-191">クリックして、**名前**プロパティ、および入力**RouteMessage**です。</span><span class="sxs-lookup"><span data-stu-id="3e162-191">Click the **Name** property, and then type **RouteMessage**.</span></span>  
  
    2.  <span data-ttu-id="3e162-192">**行程サービス エクステンダー**ドロップダウン リストをクリックして**出口行程サービス拡張**です。</span><span class="sxs-lookup"><span data-stu-id="3e162-192">In the **Itinerary Service Extender** drop-down list, click **Off-Ramp Itinerary Service Extension**.</span></span>  
  
    3.  <span data-ttu-id="3e162-193">**出口**ドロップダウン リストで、展開**SendNAOrder**、クリックして**送信ハンドラー**です。</span><span class="sxs-lookup"><span data-stu-id="3e162-193">In the **Off-Ramp** drop-down list, expand **SendNAOrder**, and then click **Send Handlers**.</span></span>  
  
4.  <span data-ttu-id="3e162-194">右クリックし、**リゾルバー**のコレクション、 **RouteMessage**モデル要素をクリックして**新しいリゾルバーを追加**です。</span><span class="sxs-lookup"><span data-stu-id="3e162-194">Right-click the **Resolver** collection of the **RouteMessage** model element, and then click **Add new Resolver**.</span></span> <span data-ttu-id="3e162-195">**Resolver1**プロパティ ウィンドウで、次のプロパティを構成します。</span><span class="sxs-lookup"><span data-stu-id="3e162-195">In the **Resolver1** Properties window, configure the following properties:</span></span>  
  
    1.  <span data-ttu-id="3e162-196">クリックして、**名前**プロパティ、および入力**StaticResolver**です。</span><span class="sxs-lookup"><span data-stu-id="3e162-196">Click the **Name** property, and then type **StaticResolver**.</span></span>  
  
    2.  <span data-ttu-id="3e162-197">**リゾルバーの実装**ドロップダウン リストをクリックして**静的競合回避モジュールの拡張機能**します。</span><span class="sxs-lookup"><span data-stu-id="3e162-197">In the **Resolver Implementation** drop-down list, click **Static Resolver Extension**.</span></span>  
  
    3.  <span data-ttu-id="3e162-198">**トランスポート名**ドロップダウン リストをクリックして**ファイル**です。</span><span class="sxs-lookup"><span data-stu-id="3e162-198">In the **Transport Name** drop-down list, click **FILE**.</span></span>  
  
    4.  <span data-ttu-id="3e162-199">クリックして、**トランスポート場所**プロパティ、および入力**C:\HowTos\Out\West%MessageID%.xml**です。</span><span class="sxs-lookup"><span data-stu-id="3e162-199">Click the **Transport Location** property, and then type **C:\HowTos\Out\West%MessageID%.xml**.</span></span>  
  
5.  <span data-ttu-id="3e162-200">ツールボックスで、をクリックして**コネクタ**です。</span><span class="sxs-lookup"><span data-stu-id="3e162-200">In the Toolbox, click **Connector**.</span></span> <span data-ttu-id="3e162-201">接続をドラッグして、 **ReceiveNAOrder**モデル要素を**RouteMessage**モデル要素。</span><span class="sxs-lookup"><span data-stu-id="3e162-201">Drag a connection from the **ReceiveNAOrder** model element to the **RouteMessage** model element.</span></span>  
  
6.  <span data-ttu-id="3e162-202">ツールボックスで、をクリックして**コネクタ**です。</span><span class="sxs-lookup"><span data-stu-id="3e162-202">In the Toolbox, click **Connector**.</span></span> <span data-ttu-id="3e162-203">接続をドラッグして、 **RouteMessage**モデル要素を**SendNAOrder**モデル要素。</span><span class="sxs-lookup"><span data-stu-id="3e162-203">Drag a connection from the **RouteMessage** model element to the **SendNAOrder** model element.</span></span>  
  
#### <a name="to-export-the-model-to-the-itinerary-database"></a><span data-ttu-id="3e162-204">行程データベースにモデルをエクスポートするには</span><span class="sxs-lookup"><span data-stu-id="3e162-204">To export the model to the itinerary database</span></span>  
  
1.  <span data-ttu-id="3e162-205">Visual Studio でのデザイン画面を右クリックし、 **GlobalBankWestItinerary**行程をクリックして**モデルのエクスポート**です。</span><span class="sxs-lookup"><span data-stu-id="3e162-205">In Visual Studio, right-click the design surface of the **GlobalBankWestItinerary** itinerary, and then click **Export Model**.</span></span>  
  
    > [!NOTE]
    >  <span data-ttu-id="3e162-206">Itinerary は行程データベースにエクスポートされてし、旅程セレクター コンポーネントによって使用されるようになりました。</span><span class="sxs-lookup"><span data-stu-id="3e162-206">The itinerary has been exported to the itinerary database and can now be used by the Itinerary Selector component.</span></span>  
  
2.  <span data-ttu-id="3e162-207">すべてのプロジェクトの成果物を保存します。</span><span class="sxs-lookup"><span data-stu-id="3e162-207">Save all project artifacts.</span></span>  
  
#### <a name="to-create-an-esb-itinerary-dsl-model-for-globalbank-east-message"></a><span data-ttu-id="3e162-208">GlobalBank 東部メッセージの ESB itinerary DSL モデルを作成するには</span><span class="sxs-lookup"><span data-stu-id="3e162-208">To create an ESB itinerary DSL model for GlobalBank East message</span></span>  
  
1.  <span data-ttu-id="3e162-209">Visual Studio で、C:\HowTos\Patterns.sln を開きます。</span><span class="sxs-lookup"><span data-stu-id="3e162-209">In Visual Studio, open C:\HowTos\Patterns.sln.</span></span>  
  
2.  <span data-ttu-id="3e162-210">ソリューション エクスプ ローラーで右クリックし、 **ItineraryLibrary**プロジェクトをポイントし、**追加**、クリックして**新しい行程**です。</span><span class="sxs-lookup"><span data-stu-id="3e162-210">In Solution Explorer, right-click the **ItineraryLibrary** project, point to **Add**, and then click **New Itinerary**.</span></span>  
  
3.  <span data-ttu-id="3e162-211">**新しい項目の追加**ダイアログ ボックスの [テンプレート] ペインで、クリックして**ItineraryDsl**です。</span><span class="sxs-lookup"><span data-stu-id="3e162-211">In the **Add New Item** dialog box, in the Templates pane, click **ItineraryDsl**.</span></span>  
  
4.  <span data-ttu-id="3e162-212">**名前**ボックスに、入力**GlobalBankEastItinerary**、クリックして**追加**です。</span><span class="sxs-lookup"><span data-stu-id="3e162-212">In the **Name** box, type **GlobalBankEastItinerary**, and then click **Add**.</span></span>  
  
#### <a name="to-configure-the-properties-of-the-globalbank-east-itinerary"></a><span data-ttu-id="3e162-213">GlobalBank 東部旅行計画のプロパティを構成するには</span><span class="sxs-lookup"><span data-stu-id="3e162-213">To configure the properties of the GlobalBank East itinerary</span></span>  
  
1.  <span data-ttu-id="3e162-214">Visual Studio でのデザイン画面をクリックして**GlobalBankEastItinerary.itinerary**です。</span><span class="sxs-lookup"><span data-stu-id="3e162-214">In Visual Studio, click the design surface of **GlobalBankEastItinerary.itinerary**.</span></span> <span data-ttu-id="3e162-215">**GlobalBankEastItinerary**プロパティ ウィンドウで、次のプロパティを構成します。</span><span class="sxs-lookup"><span data-stu-id="3e162-215">In the **GlobalBankEastItinerary** Properties window, configure the following properties:</span></span>  
  
    1.  <span data-ttu-id="3e162-216">**モデル エクスポーター**ドロップダウン リストをクリックして**データベース行程エクスポーター**です。</span><span class="sxs-lookup"><span data-stu-id="3e162-216">In the **Model Exporter** drop-down list, click **Database Itinerary Exporter**.</span></span>  
  
    2.  <span data-ttu-id="3e162-217">横にある省略記号ボタン (...) をクリックして、**行程データベース**プロパティです。</span><span class="sxs-lookup"><span data-stu-id="3e162-217">Click the ellipsis button (...) next to the **Itinerary Database** property.</span></span>  
  
    3.  <span data-ttu-id="3e162-218">**接続プロパティ**ダイアログ ボックスで、itinerary リポジトリ データベースをホストする SQL Server を選択し、データベースの名前を指定 (既定の名前は**EsbItineraryDb**)。</span><span class="sxs-lookup"><span data-stu-id="3e162-218">In the **Connection Properties** dialog box, choose the SQL Server that hosts the itinerary repository database, and then specify the name of the database (the default name is **EsbItineraryDb**).</span></span>  
  
2.  <span data-ttu-id="3e162-219">**行程ステータス**ドロップダウン リストをクリックして**配置済み**です。</span><span class="sxs-lookup"><span data-stu-id="3e162-219">In the **Itinerary Status** drop-down list, click **Deployed**.</span></span>  
  
    > [!NOTE]
    >  <span data-ttu-id="3e162-220">この手順では、; の中央リポジトリに旅行計画をエクスポートできます。日程を選択し、メッセージが受信したときに、このリポジトリからアタッチされます。</span><span class="sxs-lookup"><span data-stu-id="3e162-220">This step enables you to export the itinerary to a central repository; itineraries can be selected and attached from this repository when messages are received.</span></span> <span data-ttu-id="3e162-221">後で、BRI 競合回避モジュールを使用して受信メッセージを評価し、このリポジトリから適切な旅程を選択する行程セレクター パイプライン コンポーネントを構成します。</span><span class="sxs-lookup"><span data-stu-id="3e162-221">You will later configure the Itinerary Selector pipeline component to use the BRI resolver to evaluate inbound messages and select the appropriate itinerary from this repository.</span></span>  
  
#### <a name="to-define-the-structure-of-the-itinerary"></a><span data-ttu-id="3e162-222">旅行計画の構造を定義するには</span><span class="sxs-lookup"><span data-stu-id="3e162-222">To define the structure of the itinerary</span></span>  
  
1.  <span data-ttu-id="3e162-223">ツールボックスからドラッグして、**入り口**デザイン画面にモデル要素。</span><span class="sxs-lookup"><span data-stu-id="3e162-223">From the Toolbox, drag an **On-Ramp** model element to the design surface.</span></span> <span data-ttu-id="3e162-224">**OnRamp1**プロパティ ウィンドウで、次のプロパティを構成します。</span><span class="sxs-lookup"><span data-stu-id="3e162-224">In the **OnRamp1** Properties window, configure the following properties:</span></span>  
  
    1.  <span data-ttu-id="3e162-225">クリックして、**名前**プロパティ、および入力**ReceiveNAOrder**です。</span><span class="sxs-lookup"><span data-stu-id="3e162-225">Click the **Name** property, and then type **ReceiveNAOrder**.</span></span>  
  
    2.  <span data-ttu-id="3e162-226">**Extender**ドロップダウン リストをクリックして**入り口 ESB サービス拡張**です。</span><span class="sxs-lookup"><span data-stu-id="3e162-226">In the **Extender** drop-down list, click **On-Ramp ESB Service Extension**.</span></span>  
  
    3.  <span data-ttu-id="3e162-227">**BizTalk アプリケーション**ドロップダウン リストをクリックして**Microsoft.Practices.ESB**です。</span><span class="sxs-lookup"><span data-stu-id="3e162-227">In the **BizTalk Application** drop-down list, click **Microsoft.Practices.ESB**.</span></span>  
  
    4.  <span data-ttu-id="3e162-228">**受信ポート**ドロップダウン リストをクリックして**OnRamp.Itinerary**です。</span><span class="sxs-lookup"><span data-stu-id="3e162-228">In the **Receive Port** drop-down list, click **OnRamp.Itinerary**.</span></span>  
  
2.  <span data-ttu-id="3e162-229">ツールボックスからドラッグして、**出口**デザイン画面に要素をモデル化の右側に配置し、 **ReceiveNAOrder**モデル要素。</span><span class="sxs-lookup"><span data-stu-id="3e162-229">From the Toolbox, drag an **Off-Ramp** model element to the design surface, and then place it to the right of the **ReceiveNAOrder** model element.</span></span> <span data-ttu-id="3e162-230">**OffRamp1**プロパティ ウィンドウで、次のプロパティを構成します。</span><span class="sxs-lookup"><span data-stu-id="3e162-230">In the **OffRamp1** Properties window, configure the following properties:</span></span>  
  
    1.  <span data-ttu-id="3e162-231">クリックして、**名前**プロパティ、および入力**SendNAOrder**です。</span><span class="sxs-lookup"><span data-stu-id="3e162-231">Click the **Name** property, and then type **SendNAOrder**.</span></span>  
  
    2.  <span data-ttu-id="3e162-232">**Extender**ドロップダウン リストをクリックして**出口 ESB サービス拡張**です。</span><span class="sxs-lookup"><span data-stu-id="3e162-232">In the **Extender** drop-down list, click **Off-Ramp ESB Service Extension**.</span></span>  
  
    3.  <span data-ttu-id="3e162-233">**BizTalk アプリケーション**ドロップダウン リストをクリックして**GlobalBank.ESB**です。</span><span class="sxs-lookup"><span data-stu-id="3e162-233">In the **BizTalk Application** drop-down list, click **GlobalBank.ESB**.</span></span>  
  
    4.  <span data-ttu-id="3e162-234">**送信ポート**ドロップダウン リストをクリックして**DynamicResolutionOneWay**です。</span><span class="sxs-lookup"><span data-stu-id="3e162-234">In the **Send Port** drop-down list, click **DynamicResolutionOneWay**.</span></span>  
  
3.  <span data-ttu-id="3e162-235">ツールボックスからドラッグ、**行程サービス**モデルをデザイン画面に要素との間に配置し、 **ReceiveNAOrder**モデル要素と**SendNAOrder**モデル要素。</span><span class="sxs-lookup"><span data-stu-id="3e162-235">From the Toolbox, drag an **Itinerary Service** model element to the design surface, and then place it between the **ReceiveNAOrder** model element and the **SendNAOrder** model element.</span></span> <span data-ttu-id="3e162-236">**ItineraryService1**プロパティ ウィンドウで、次のプロパティを構成します。</span><span class="sxs-lookup"><span data-stu-id="3e162-236">In the **ItineraryService1** Properties window, configure the following properties:</span></span>  
  
    1.  <span data-ttu-id="3e162-237">クリックして、**名前**プロパティ、および入力**RouteMessage**です。</span><span class="sxs-lookup"><span data-stu-id="3e162-237">Click the **Name** property, and then type **RouteMessage**.</span></span>  
  
    2.  <span data-ttu-id="3e162-238">**行程サービス エクステンダー**ドロップダウン リストをクリックして**出口行程サービス拡張**です。</span><span class="sxs-lookup"><span data-stu-id="3e162-238">In the **Itinerary Service Extender** drop-down list, click **Off-Ramp Itinerary Service Extension**.</span></span>  
  
    3.  <span data-ttu-id="3e162-239">**出口**ドロップダウン リストで、展開**SendNAOrder**、クリックして**送信ハンドラー**です。</span><span class="sxs-lookup"><span data-stu-id="3e162-239">In the **Off-Ramp** drop-down list, expand **SendNAOrder**, and then click **Send Handlers**.</span></span>  
  
4.  <span data-ttu-id="3e162-240">右クリックし、**リゾルバー**のコレクション、 **RouteMessage**モデル要素をクリックして**新しいリゾルバーを追加**です。</span><span class="sxs-lookup"><span data-stu-id="3e162-240">Right-click the **Resolver** collection of the **RouteMessage** model element, and then click **Add new Resolver**.</span></span> <span data-ttu-id="3e162-241">**Resolver1**プロパティ ウィンドウで、次のプロパティを構成します。</span><span class="sxs-lookup"><span data-stu-id="3e162-241">In the **Resolver1** Properties window, configure the following properties:</span></span>  
  
    1.  <span data-ttu-id="3e162-242">クリックして、**名前**プロパティ、および入力**StaticResolver**です。</span><span class="sxs-lookup"><span data-stu-id="3e162-242">Click the **Name** property, and then type **StaticResolver**.</span></span>  
  
    2.  <span data-ttu-id="3e162-243">**リゾルバーの実装**ドロップダウン リストをクリックして**静的競合回避モジュールの拡張機能**します。</span><span class="sxs-lookup"><span data-stu-id="3e162-243">In the **Resolver Implementation** drop-down list, click **Static Resolver Extension**.</span></span>  
  
    3.  <span data-ttu-id="3e162-244">**トランスポート名**ドロップダウン リストをクリックして**ファイル**です。</span><span class="sxs-lookup"><span data-stu-id="3e162-244">In the **Transport Name** drop-down list, click **FILE**.</span></span>  
  
    4.  <span data-ttu-id="3e162-245">クリックして、**トランスポート場所**プロパティ、および入力**C:\HowTos\Out\East%MessageID%.xml**です。</span><span class="sxs-lookup"><span data-stu-id="3e162-245">Click the **Transport Location** property, and then type **C:\HowTos\Out\East%MessageID%.xml**.</span></span>  
  
5.  <span data-ttu-id="3e162-246">ツールボックスで、をクリックして**コネクタ**です。</span><span class="sxs-lookup"><span data-stu-id="3e162-246">In the Toolbox, click **Connector**.</span></span> <span data-ttu-id="3e162-247">接続をドラッグして、 **ReceiveNAOrder**モデル要素を**RouteMessage**モデル要素。</span><span class="sxs-lookup"><span data-stu-id="3e162-247">Drag a connection from the **ReceiveNAOrder** model element to the **RouteMessage** model element.</span></span>  
  
6.  <span data-ttu-id="3e162-248">ツールボックスで、をクリックして**コネクタ**です。</span><span class="sxs-lookup"><span data-stu-id="3e162-248">In the Toolbox, click **Connector**.</span></span> <span data-ttu-id="3e162-249">接続をドラッグして、 **RouteMessage**モデル要素を**SendNAOrder**モデル要素。</span><span class="sxs-lookup"><span data-stu-id="3e162-249">Drag a connection from the **RouteMessage** model element to the **SendNAOrder** model element.</span></span>  
  
#### <a name="to-export-the-model-to-the-itinerary-database"></a><span data-ttu-id="3e162-250">行程データベースにモデルをエクスポートするには</span><span class="sxs-lookup"><span data-stu-id="3e162-250">To export the model to the itinerary database</span></span>  
  
1.  <span data-ttu-id="3e162-251">Visual Studio でのデザイン画面を右クリックし、 **GlobalBankEastItinerary**行程をクリックして**モデルのエクスポート**です。</span><span class="sxs-lookup"><span data-stu-id="3e162-251">In Visual Studio, right-click the design surface of the **GlobalBankEastItinerary** itinerary, and then click **Export Model**.</span></span>  
  
    > [!NOTE]
    >  <span data-ttu-id="3e162-252">Itinerary は行程データベースにエクスポートされてし、旅程セレクター コンポーネントによって使用されるようになりました。</span><span class="sxs-lookup"><span data-stu-id="3e162-252">The itinerary has been exported to the itinerary database and can now be used by the Itinerary Selector component.</span></span>  
  
2.  <span data-ttu-id="3e162-253">すべてのプロジェクトの成果物を保存します。</span><span class="sxs-lookup"><span data-stu-id="3e162-253">Save all project artifacts.</span></span>  
  
#### <a name="to-create-and-configure-an-esb-on-ramp"></a><span data-ttu-id="3e162-254">作成し、ESB 入り口を構成します。</span><span class="sxs-lookup"><span data-stu-id="3e162-254">To create and configure an ESB on-ramp</span></span>  
  
1.  <span data-ttu-id="3e162-255">をクリックして**開始**タスク バーで、をポイント**すべてのプログラム**、 をポイント**BizTalk Server**、順にクリック**BizTalk Server 管理コンソール**です。</span><span class="sxs-lookup"><span data-stu-id="3e162-255">Click **Start** on the taskbar, point to **All Programs**, point to **BizTalk Server**, and then click **BizTalk Server Administration**.</span></span>  
  
2.  <span data-ttu-id="3e162-256">BizTalk Server 管理コンソールで、展開**BizTalk グループ**、展開**アプリケーション**の順に展開および**Microsoft.Practices.ESB**です。</span><span class="sxs-lookup"><span data-stu-id="3e162-256">In the BizTalk Server Administration Console, expand **BizTalk Group**, expand **Applications**, and then expand **Microsoft.Practices.ESB**.</span></span>  
  
3.  <span data-ttu-id="3e162-257">右クリック**受信場所**、 をポイント**新規**、クリックして**一方向の受信場所**です。</span><span class="sxs-lookup"><span data-stu-id="3e162-257">Right-click **Receive Locations**, point to **New**, and then click **One-way Receive Location**.</span></span>  
  
4.  <span data-ttu-id="3e162-258">**受信ポートの選択**ダイアログ ボックスで、をクリックして**OnRamp.Itinerary**、クリックして **[ok]** です。</span><span class="sxs-lookup"><span data-stu-id="3e162-258">In the **Select a Receive Port** dialog box, click **OnRamp.Itinerary**, and then click **OK**.</span></span>  
  
5.  <span data-ttu-id="3e162-259">**受信場所のプロパティ** ダイアログ ボックスで、**名前**ボックスに、入力**OnRamp.Itinerary.HowTo**です。</span><span class="sxs-lookup"><span data-stu-id="3e162-259">In the **Receive Location Properties** dialog box, in the **Name** box, type **OnRamp.Itinerary.HowTo**.</span></span>  
  
6.  <span data-ttu-id="3e162-260">**型**ドロップダウン リストをクリックして**ファイル**、順にクリック**構成**です。</span><span class="sxs-lookup"><span data-stu-id="3e162-260">In the **Type** drop-down list, click **FILE**, and then click **Configure**.</span></span>  
  
7.  <span data-ttu-id="3e162-261">**FILE トランスポートのプロパティ** ダイアログ ボックスで、**受信フォルダー**ボックスに、入力**C:\HowTos\DropFolder**、クリックして**ok**です。</span><span class="sxs-lookup"><span data-stu-id="3e162-261">In the **FILE Transport Properties** dialog box, in the **Receive folder** box, type **C:\HowTos\DropFolder**, and then click **OK**.</span></span>  
  
#### <a name="to-configure-the-itinerary-selector-pipeline-component"></a><span data-ttu-id="3e162-262">行程セレクター パイプライン コンポーネントを構成するには</span><span class="sxs-lookup"><span data-stu-id="3e162-262">To configure the Itinerary Selector pipeline component</span></span>  
  
1.  <span data-ttu-id="3e162-263">**受信場所のプロパティ** ダイアログ ボックスで、**受信パイプライン**ドロップダウン リストをクリックして**ItinerarySelectReceiveXml**、省略記号ボタン (... をクリックして).</span><span class="sxs-lookup"><span data-stu-id="3e162-263">In the **Receive Location Properties** dialog box, in the **Receive pipeline** drop-down list, click **ItinerarySelectReceiveXml**, and then click the ellipsis button (...).</span></span>  
  
2.  <span data-ttu-id="3e162-264">使用して、**パイプラインの構成**、次を構成するダイアログ ボックス**行程セレクター**コンポーネントのプロパティ。</span><span class="sxs-lookup"><span data-stu-id="3e162-264">Use the **Configure Pipeline** dialog box to configure the following **Itinerary Selector** component properties:</span></span>  
  
    1.  <span data-ttu-id="3e162-265">クリックして、 **ItineraryFactKey**プロパティ、および入力**Resolver.Itinerary**です。</span><span class="sxs-lookup"><span data-stu-id="3e162-265">Click the **ItineraryFactKey** property, and then type **Resolver.Itinerary**.</span></span>  
  
    2.  <span data-ttu-id="3e162-266">クリックして、 **ResolverConnectionString**プロパティ、および入力**BRI:\\\policy=ResolveItineraryBasedOnCustomer;useMsg=true;recognizeMessageFormat=true です。**</span><span class="sxs-lookup"><span data-stu-id="3e162-266">Click the **ResolverConnectionString** property, and then type **BRI:\\\policy=ResolveItineraryBasedOnCustomer;useMsg=true;recognizeMessageFormat=true;**</span></span>  
  
    3.  <span data-ttu-id="3e162-267">をクリックして**OK**を閉じる、**パイプラインの構成** ダイアログ ボックス。</span><span class="sxs-lookup"><span data-stu-id="3e162-267">Click **OK** to close the **Configure Pipeline** dialog box.</span></span>  
  
3.  <span data-ttu-id="3e162-268">をクリックして**OK**を閉じる、**受信場所のプロパティ** ダイアログ ボックス。</span><span class="sxs-lookup"><span data-stu-id="3e162-268">Click **OK** to close the **Receive Location Properties** dialog box.</span></span>  
  
4.  <span data-ttu-id="3e162-269">BizTalk Server 管理コンソールを右クリックし、 **OnRamp.Itinerary.HowTo**受信場所をクリックして**を有効にする**です。</span><span class="sxs-lookup"><span data-stu-id="3e162-269">In the BizTalk Server Administration Console, right-click the **OnRamp.Itinerary.HowTo** receive location, and then click **Enable**.</span></span>  
  
#### <a name="to-test-the-itinerary-selector-and-business-rules"></a><span data-ttu-id="3e162-270">Itinerary セレクターとビジネス ルールをテストするには</span><span class="sxs-lookup"><span data-stu-id="3e162-270">To test the itinerary selector and business rules</span></span>  
  
1.  <span data-ttu-id="3e162-271">Windows エクスプローラで、C:\HowTos を参照します。</span><span class="sxs-lookup"><span data-stu-id="3e162-271">In Windows Explorer, browse to C:\HowTos.</span></span>  
  
2.  <span data-ttu-id="3e162-272">コピー (移動しないでください)、East.xml と West.xml フォルダーにファイルを DropFolder です。</span><span class="sxs-lookup"><span data-stu-id="3e162-272">Copy (do not move) the files East.xml and West.xml to the DropFolder folder.</span></span>  
  
3.  <span data-ttu-id="3e162-273">C:\HowTos\Out を参照します。East%MessageID%.xml と West%MessageID%.xml メッセージがディレクトリに書き込まれたことを確認します。</span><span class="sxs-lookup"><span data-stu-id="3e162-273">Browse to C:\HowTos\Out. Verify that the East%MessageID%.xml and West%MessageID%.xml messages have been written to the directory.</span></span>  
  
    > [!NOTE]
    >  <span data-ttu-id="3e162-274">顧客の要素の値を除いて同一でも、行程セレクター パイプライン コンポーネントの解像度に基づいて、別の日程を使用して、メッセージが処理されました。</span><span class="sxs-lookup"><span data-stu-id="3e162-274">Though identical except for the value of the customer element, the messages were processed using different itineraries, based on the resolution of the Itinerary Selector pipeline component.</span></span>  
  
4.  <span data-ttu-id="3e162-275">BizTalk Server 管理コンソールを右クリックし、 **OnRamp.Itinerary.HowTo**受信場所をクリックして**を無効にする**です。</span><span class="sxs-lookup"><span data-stu-id="3e162-275">In the BizTalk Server Administration Console, right-click the **OnRamp.Itinerary.HowTo** receive location, and then click **Disable**.</span></span>  
  
5.  <span data-ttu-id="3e162-276">後に、 **OnRamp.Itinerary.HowTo**受信場所が無効になっている、右クリックし、をクリックして**削除**です。</span><span class="sxs-lookup"><span data-stu-id="3e162-276">After the **OnRamp.Itinerary.HowTo** receive location is disabled, right-click it, and then click **Delete**.</span></span> <span data-ttu-id="3e162-277">**受信場所のことを確認して削除**ダイアログ ボックスで、をクリックして**はい**です。</span><span class="sxs-lookup"><span data-stu-id="3e162-277">In the **Confirm delete receive location** dialog box, click **Yes**.</span></span>  
  
## <a name="additional-resources"></a><span data-ttu-id="3e162-278">その他のリソース</span><span class="sxs-lookup"><span data-stu-id="3e162-278">Additional Resources</span></span>  
 <span data-ttu-id="3e162-279">詳細については、次の関連項目を参照してください。</span><span class="sxs-lookup"><span data-stu-id="3e162-279">For more information, see the following related topics:</span></span>  
  
-   [<span data-ttu-id="3e162-280">方法: 別個のスケジュールを利用し、インターチェンジを分割して結果的に生成されたメッセージを複数のファイルの場所に送る</span><span class="sxs-lookup"><span data-stu-id="3e162-280">How to: Split an Interchange and Route the Resulting Messages to Multiple File Locations Using Distinct Itineraries</span></span>](../esb-toolkit/split-an-interchange-and-route-messages-to-multiple-locations-using-itineraries.md)  
  
-   [<span data-ttu-id="3e162-281">開発アクティビティ</span><span class="sxs-lookup"><span data-stu-id="3e162-281">Development Activities</span></span>](../esb-toolkit/development-activities.md)  
  
-   [<span data-ttu-id="3e162-282">動的解決サンプルをインストールし、実行する</span><span class="sxs-lookup"><span data-stu-id="3e162-282">Installing and Running the Dynamic Resolution Sample</span></span>](../esb-toolkit/installing-and-running-the-dynamic-resolution-sample.md)  
  
-   [<span data-ttu-id="3e162-283">動的な解決とルーティングを利用する</span><span class="sxs-lookup"><span data-stu-id="3e162-283">Using Dynamic Resolution and Routing</span></span>](../esb-toolkit/using-dynamic-resolution-and-routing.md)  
  
-   [<span data-ttu-id="3e162-284">メッセージ ルーティング パターン</span><span class="sxs-lookup"><span data-stu-id="3e162-284">Message Routing Patterns</span></span>](../esb-toolkit/message-routing-patterns.md)