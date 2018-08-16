---
title: '方法: ビジネス ルール ポリシーを使用するスケジュールを選択します |。Microsoft Docs'
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
ms.openlocfilehash: 12496da0de4057e96be0b714ad1af048ee6b8ef1
ms.sourcegitcommit: 266308ec5c6a9d8d80ff298ee6051b4843c5d626
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 06/27/2018
ms.locfileid: "36976963"
---
# <a name="how-to-select-an-itinerary-using-a-business-rules-policy"></a><span data-ttu-id="3deb9-102">方法: ビジネス ルール ポリシーを使用するスケジュールを選択します。</span><span class="sxs-lookup"><span data-stu-id="3deb9-102">How to: Select an Itinerary Using a Business Rules Policy</span></span>
## <a name="goal"></a><span data-ttu-id="3deb9-103">[目標]</span><span class="sxs-lookup"><span data-stu-id="3deb9-103">Goal</span></span>  
 <span data-ttu-id="3deb9-104">このセクションでは、受信したメッセージの内容に基づいて、旅行プランを選択するのに使用できるビジネス ルールを作成する方法と、汎用的なスケジュールに導入これらのルールの呼び出し内での旅程セレクター パイプライン コンポーネントを構成する方法を示します。</span><span class="sxs-lookup"><span data-stu-id="3deb9-104">This section demonstrates how to create business rules that can be used to select an itinerary based on the content of a received message and how to configure the Itinerary Selector pipeline component within a generic itinerary on-ramp to call these rules.</span></span> <span data-ttu-id="3deb9-105">このセクションでメッセージがルーティングされる異なる方法で、顧客が存在するリージョンに基づくビジネス シナリオについて説明します。</span><span class="sxs-lookup"><span data-stu-id="3deb9-105">This section describes a business scenario in which messages are routed differently, based on the region in which the customer resides.</span></span>  
  
 <span data-ttu-id="3deb9-106">このトピックでは、次の手順を行います。</span><span class="sxs-lookup"><span data-stu-id="3deb9-106">In this How-to topic, you will complete the following steps:</span></span>  
  
-   <span data-ttu-id="3deb9-107">西と東 Global 銀行の顧客の事業部のモデルのスケジュール。</span><span class="sxs-lookup"><span data-stu-id="3deb9-107">Model itineraries for the Western and Eastern divisions of customer Global Bank.</span></span>  
  
-   <span data-ttu-id="3deb9-108">要求を処理するスケジュールを選択するために使用するビジネス ルール ポリシーを作成します。</span><span class="sxs-lookup"><span data-stu-id="3deb9-108">Create business rules policies that will be used to select an itinerary for processing request.</span></span>  
  
-   <span data-ttu-id="3deb9-109">ビジネス ルール ポリシーを使用して、適切なスケジュールを選択するスケジュール セレクターのパイプライン コンポーネントを構成します。</span><span class="sxs-lookup"><span data-stu-id="3deb9-109">Configure the Itinerary Selector pipeline component to use a business rules policy to select the appropriate itinerary.</span></span>  
  
## <a name="prerequisites"></a><span data-ttu-id="3deb9-110">前提条件</span><span class="sxs-lookup"><span data-stu-id="3deb9-110">Prerequisites</span></span>  
 <span data-ttu-id="3deb9-111">この操作方法に関するトピックの手順の完了が必要、[開発活動の前提条件](../esb-toolkit/prerequisites-for-the-development-activities.md)します。</span><span class="sxs-lookup"><span data-stu-id="3deb9-111">The procedures in this How-to topic require the completion of the [Prerequisites for the Development Activities](../esb-toolkit/prerequisites-for-the-development-activities.md).</span></span>  
  
## <a name="before-you-begin"></a><span data-ttu-id="3deb9-112">はじめに</span><span class="sxs-lookup"><span data-stu-id="3deb9-112">Before You Begin</span></span>  
 <span data-ttu-id="3deb9-113">この操作方法に関するトピックの後半の手順を実行する前に、次のタスクを実行します。</span><span class="sxs-lookup"><span data-stu-id="3deb9-113">Complete the following tasks before you perform the steps later in this How-to topic:</span></span>  
  
- <span data-ttu-id="3deb9-114">GlobalBank 西部テスト メッセージを作成します。</span><span class="sxs-lookup"><span data-stu-id="3deb9-114">Create the GlobalBank West test message.</span></span>  
  
- <span data-ttu-id="3deb9-115">GlobalBank 東部のテスト メッセージを作成します。</span><span class="sxs-lookup"><span data-stu-id="3deb9-115">Create the GlobalBank East test message.</span></span>  
  
  <span data-ttu-id="3deb9-116">次の手順では、これらの各方法について説明します。</span><span class="sxs-lookup"><span data-stu-id="3deb9-116">The following procedures describe how to do each of these.</span></span>  
  
#### <a name="to-create-the-globalbank-west-test-message"></a><span data-ttu-id="3deb9-117">GlobalBank 西部テスト メッセージを作成するには</span><span class="sxs-lookup"><span data-stu-id="3deb9-117">To create the GlobalBank West test message</span></span>  
  
1.  <span data-ttu-id="3deb9-118">Windows エクスプ ローラーでは、C:\HowTos を参照します。</span><span class="sxs-lookup"><span data-stu-id="3deb9-118">In Windows Explorer, browse to C:\HowTos.</span></span>  
  
2.  <span data-ttu-id="3deb9-119">NAOrderDoc.xml のコピーを作成し、コピー West.xml、名前を付けます。</span><span class="sxs-lookup"><span data-stu-id="3deb9-119">Create a copy of NAOrderDoc.xml, and then name the copy West.xml.</span></span>  
  
3.  <span data-ttu-id="3deb9-120">メモ帳で、West.xml を開きの値を変更、 **customerName**要素**GlobalBankWest**します。</span><span class="sxs-lookup"><span data-stu-id="3deb9-120">In Notepad, open West.xml, and then change the value of the **customerName** element to **GlobalBankWest**.</span></span>  
  
4.  <span data-ttu-id="3deb9-121">West.xml を utf-8 として保存し、メモ帳を終了します。</span><span class="sxs-lookup"><span data-stu-id="3deb9-121">Save West.xml as UTF-8, and then close Notepad.</span></span>  
  
#### <a name="to-create-the-globalbank-east-test-message"></a><span data-ttu-id="3deb9-122">GlobalBank 東部テスト メッセージを作成するには</span><span class="sxs-lookup"><span data-stu-id="3deb9-122">To create the GlobalBank East test message</span></span>  
  
1.  <span data-ttu-id="3deb9-123">Windows エクスプ ローラーでは、C:\HowTos を参照します。</span><span class="sxs-lookup"><span data-stu-id="3deb9-123">In Windows Explorer, browse to C:\HowTos.</span></span>  
  
2.  <span data-ttu-id="3deb9-124">NAOrderDoc.xml のコピーを作成し、コピー East.xml、名前を付けます。</span><span class="sxs-lookup"><span data-stu-id="3deb9-124">Create a copy of NAOrderDoc.xml, and then name the copy East.xml.</span></span>  
  
3.  <span data-ttu-id="3deb9-125">メモ帳で、East.xml を開きの値を変更、 **customerName**要素**GlobalBankEast**します。</span><span class="sxs-lookup"><span data-stu-id="3deb9-125">In Notepad, open East.xml, and then change the value of the **customerName** element to **GlobalBankEast**.</span></span>  
  
4.  <span data-ttu-id="3deb9-126">East.xml を utf-8 として保存し、メモ帳を終了します。</span><span class="sxs-lookup"><span data-stu-id="3deb9-126">Save East.xml as UTF-8, and then close Notepad.</span></span>  
  
## <a name="steps"></a><span data-ttu-id="3deb9-127">手順</span><span class="sxs-lookup"><span data-stu-id="3deb9-127">Steps</span></span>  
  
#### <a name="to-create-a-business-rules-engine-bre-policy-to-select-an-itinerary-using-custom-message-properties"></a><span data-ttu-id="3deb9-128">カスタム メッセージ プロパティを使用するスケジュールを選択するビジネス ルール エンジン (BRE) ポリシーを作成するには</span><span class="sxs-lookup"><span data-stu-id="3deb9-128">To create a Business Rules Engine (BRE) policy to select an itinerary using custom message properties</span></span>  
  
1.  <span data-ttu-id="3deb9-129">クリックして**開始**タスク バーで、をポイント**すべてのプログラム**、 をポイント**BizTalk Server**、順にクリックします**ビジネス ルール作成ツール**します。</span><span class="sxs-lookup"><span data-stu-id="3deb9-129">Click **Start** on the taskbar, point to **All Programs**, point to **BizTalk Server**, and then click **Business Rule Composer**.</span></span>  
  
2.  <span data-ttu-id="3deb9-130">ポリシー エクスプ ローラーで右クリック**ポリシー**、 をクリックし、**新しいポリシーの追加**します。</span><span class="sxs-lookup"><span data-stu-id="3deb9-130">In Policy Explorer, right-click **Policies**, and then click **Add New Policy**.</span></span> <span data-ttu-id="3deb9-131">ポリシーの名前**ResolveItineraryBasedOnCustomer**します。</span><span class="sxs-lookup"><span data-stu-id="3deb9-131">Name the policy **ResolveItineraryBasedOnCustomer**.</span></span>  
  
    > [!NOTE]
    >  <span data-ttu-id="3deb9-132">このトピックのトピックで作成されたものと同じビジネス ルール ポリシーとスケジュールを使用して[方法: インターチェンジを分割し、結果として得られるメッセージをルーティング、複数ファイルの場所を使用して異なる日程](../esb-toolkit/split-an-interchange-and-route-messages-to-multiple-locations-using-itineraries.md)します。</span><span class="sxs-lookup"><span data-stu-id="3deb9-132">This How-to topic uses the same business rules policy and itineraries as those created in the topic [How to: Split an Interchange and Route the Resulting Messages to Multiple File Locations Using Distinct Itineraries](../esb-toolkit/split-an-interchange-and-route-messages-to-multiple-locations-using-itineraries.md).</span></span> <span data-ttu-id="3deb9-133">そのセクションを完了している場合は、このトピックの「"を作成して、ESB 入り口を構成する 手順を省略できます。</span><span class="sxs-lookup"><span data-stu-id="3deb9-133">If you have already completed that section, you can skip to the procedure, "To create and configure an ESB on-ramp" later in this topic.</span></span>  
  
#### <a name="to-add-a-selection-rule-for-customer-globalbank-west"></a><span data-ttu-id="3deb9-134">GlobalBank 西部の顧客の選択規則を追加するには</span><span class="sxs-lookup"><span data-stu-id="3deb9-134">To add a selection rule for customer GlobalBank West</span></span>  
  
1.  <span data-ttu-id="3deb9-135">**ResolveItineraryBasedOnCustomer**ポリシーを右クリックして**バージョン 1.0 (未保存)**、順にクリックします**新しいルールの追加**します。</span><span class="sxs-lookup"><span data-stu-id="3deb9-135">In the **ResolveItineraryBasedOnCustomer** policy, right-click **Version 1.0 (not saved)**, and then click **Add New Rule**.</span></span> <span data-ttu-id="3deb9-136">ルールの名前として**SetGlobalBankWestItinerary**します。</span><span class="sxs-lookup"><span data-stu-id="3deb9-136">Name the rule **SetGlobalBankWestItinerary**.</span></span>  
  
2.  <span data-ttu-id="3deb9-137">ファクト エクスプ ローラーでクリックして、 **XML スキーマ** タブを右クリックして**スキーマ**、順にクリックします**参照**します。</span><span class="sxs-lookup"><span data-stu-id="3deb9-137">In Facts Explorer, click the **XML Schemas** tab, right-click **Schemas**, and then click **Browse**.</span></span>  
  
3.  <span data-ttu-id="3deb9-138">**スキーマ ファイル** ダイアログ ボックスで、C:\Projects\Microsoft.Practices.ESB\Source\Samples\DynamicResolution\Source\ESB を参照します。DynamicResolution.Schemas で、 **NAOrderDoc.xsd**、 をクリックし、**オープン**します。</span><span class="sxs-lookup"><span data-stu-id="3deb9-138">In the **Schema Files** dialog box, browse to C:\Projects\Microsoft.Practices.ESB\Source\Samples\DynamicResolution\Source\ESB.DynamicResolution.Schemas, select **NAOrderDoc.xsd**, and then click **Open**.</span></span>  
  
    > [!NOTE]
    >  <span data-ttu-id="3deb9-139">テストに使用する西部と東部のメッセージを作成するために使用された NAOrderDoc.xml メッセージを定義するスキーマです。</span><span class="sxs-lookup"><span data-stu-id="3deb9-139">This is the schema that defines the NAOrderDoc.xml message, which was used to create the West and East messages you will use for testing.</span></span>  
  
4.  <span data-ttu-id="3deb9-140">ファクト エクスプ ローラーでクリックして**NAOrderDoc.xsd**、クリックして、**ドキュメントの種類**プロパティのプロパティ ウィンドウと入力し、 **GlobalBank.ESB.DynamicResolution.Schemas.NAOrderDoc**.</span><span class="sxs-lookup"><span data-stu-id="3deb9-140">In Facts Explorer, click **NAOrderDoc.xsd**, click the **Document Type** property in the Properties pane, and then type **GlobalBank.ESB.DynamicResolution.Schemas.NAOrderDoc**.</span></span>  
  
    > [!NOTE]
    >  <span data-ttu-id="3deb9-141">これは、スキーマの完全修飾名です。</span><span class="sxs-lookup"><span data-stu-id="3deb9-141">This is the fully qualified name of the schema.</span></span>  
  
5.  <span data-ttu-id="3deb9-142">ファクト エクスプ ローラーで、 **NAOrderDoc.xsd**、順に展開**OrderDoc**します。</span><span class="sxs-lookup"><span data-stu-id="3deb9-142">In Facts Explorer, expand **NAOrderDoc.xsd**, and then expand **OrderDoc**.</span></span>  
  
6.  <span data-ttu-id="3deb9-143">ルール ウィンドウで、右クリック**条件**、 をポイント**述語**、 をクリックし、**等しい**。</span><span class="sxs-lookup"><span data-stu-id="3deb9-143">In the Rule window, right-click **Conditions**, point to **Predicates**, and then click **Equal**.</span></span>  
  
7.  <span data-ttu-id="3deb9-144">ファクト エクスプ ローラーからドラッグして、 **customerName**要素を **[引数 1]** ノードの下**条件**します。</span><span class="sxs-lookup"><span data-stu-id="3deb9-144">From Facts Explorer, drag the **customerName** element to the **argument1** node under **Conditions**.</span></span>  
  
8.  <span data-ttu-id="3deb9-145">をクリックして、 **[引数 2]** ノード、および入力**GlobalBankWest**します。</span><span class="sxs-lookup"><span data-stu-id="3deb9-145">Click the **argument2** node, and then type **GlobalBankWest**.</span></span>  
  
9. <span data-ttu-id="3deb9-146">ファクト エクスプ ローラーでクリックして、**ボキャブラリ**タブ。展開、 **ESB します。旅行プラン**ボキャブラリ、展開**バージョン 1.1**、し、ドラッグ、**旅行プラン名の設定**の定義を**アクション**します。</span><span class="sxs-lookup"><span data-stu-id="3deb9-146">In Facts Explorer, click the **Vocabularies** tab. Expand the **ESB.Itinerary** vocabulary, expand **Version 1.1**, and then drag the **Set Itinerary Name** definition to **Actions**.</span></span>  
  
10. <span data-ttu-id="3deb9-147">クリックして**\<空の文字列\>**、し、入力**GlobalBankWestItinerary**します。</span><span class="sxs-lookup"><span data-stu-id="3deb9-147">Click **\<empty string\>**, and then type **GlobalBankWestItinerary**.</span></span>  
  
    > [!NOTE]
    >  <span data-ttu-id="3deb9-148">このトピックの後半では、GlobalBank 西部からメッセージを処理するこの旅行プランが作成されます。</span><span class="sxs-lookup"><span data-stu-id="3deb9-148">Later in this How-to topic, you will create this itinerary to process messages from GlobalBank West.</span></span>  
  
#### <a name="to-add-a-selection-rule-for-customer-globalbank-east"></a><span data-ttu-id="3deb9-149">GlobalBank 東部の顧客の選択規則を追加するには</span><span class="sxs-lookup"><span data-stu-id="3deb9-149">To add a selection rule for Customer GlobalBank East</span></span>  
  
1.  <span data-ttu-id="3deb9-150">ポリシー エクスプ ローラーで右クリックし、 **SetGlobalBankWestItinerary**ルールは、クリックして**コピー**します。</span><span class="sxs-lookup"><span data-stu-id="3deb9-150">In Policy Explorer, right-click the **SetGlobalBankWestItinerary** rule, and then click **Copy**.</span></span>  
  
2.  <span data-ttu-id="3deb9-151">右クリック**バージョン 1.0 (未保存)**、 をクリックし、**貼り付け**します。</span><span class="sxs-lookup"><span data-stu-id="3deb9-151">Right-click **Version 1.0 (not saved)**, and then click **Paste**.</span></span>  
  
3.  <span data-ttu-id="3deb9-152">**新しいルール名**ダイアログ ボックスに「 **SetGlobalBankEastItinerary**、順にクリックします**OK**します。</span><span class="sxs-lookup"><span data-stu-id="3deb9-152">In the **New Rule Name** dialog box, type **SetGlobalBankEastItinerary**, and then click **OK**.</span></span>  
  
4.  <span data-ttu-id="3deb9-153">ポリシー エクスプ ローラーでクリックして、 **SetGlobalBankEastItinerary**ルール。</span><span class="sxs-lookup"><span data-stu-id="3deb9-153">In Policy Explorer, click the **SetGlobalBankEastItinerary** rule.</span></span>  
  
5.  <span data-ttu-id="3deb9-154">**条件**セクションを右クリックして**GlobalBankWest**、 をクリックし、**引数の再設定**します。</span><span class="sxs-lookup"><span data-stu-id="3deb9-154">In the **Conditions** section, right-click **GlobalBankWest**, and then click **Reset argument**.</span></span>  
  
6.  <span data-ttu-id="3deb9-155">クリックして **[引数 2]**、し、入力**GlobalBankEast**します。</span><span class="sxs-lookup"><span data-stu-id="3deb9-155">Click **argument2**, and then type **GlobalBankEast**.</span></span>  
  
7.  <span data-ttu-id="3deb9-156">**アクション**セクションで、右クリック**GlobalBankWestItinerary**、 をクリックし、**引数の再設定**します。</span><span class="sxs-lookup"><span data-stu-id="3deb9-156">In the **Actions** section, right-click **GlobalBankWestItinerary**, and then click **Reset argument**.</span></span>  
  
8.  <span data-ttu-id="3deb9-157">クリックして**\<空の文字列\>** し入力**GlobalBankEastItinerary**します。</span><span class="sxs-lookup"><span data-stu-id="3deb9-157">Click **\<empty string\>** and then type **GlobalBankEastItinerary**.</span></span>  
  
    > [!NOTE]
    >  <span data-ttu-id="3deb9-158">に関する「方法」トピックの後半では、GlobalBank 東部からメッセージを処理するこの旅行プランを作成されます。 します</span><span class="sxs-lookup"><span data-stu-id="3deb9-158">Later in the How-to topic, you will create this itinerary to process messages from GlobalBank East.</span></span>  
  
#### <a name="to-publish-and-deploy-the-policy"></a><span data-ttu-id="3deb9-159">発行して、ポリシーをデプロイするには</span><span class="sxs-lookup"><span data-stu-id="3deb9-159">To publish and deploy the policy</span></span>  
  
1.  <span data-ttu-id="3deb9-160">ポリシー エクスプ ローラーで [、 **ResolveItineraryBasedOnCustomer**ポリシーを右クリック**バージョン 1.0 (未保存)**、] をクリックし、**発行**します。</span><span class="sxs-lookup"><span data-stu-id="3deb9-160">In Policy Explorer, under the **ResolveItineraryBasedOnCustomer** policy, right click **Version 1.0 (not saved)**, and then click **Publish**.</span></span>  
  
2.  <span data-ttu-id="3deb9-161">ポリシー エクスプ ローラーで [、 **ResolveItineraryBasedOnCustomer**ポリシーを右クリック**バージョン 1.0 - 公開済み**、] をクリックし、**デプロイ**。</span><span class="sxs-lookup"><span data-stu-id="3deb9-161">In Policy Explorer, under the **ResolveItineraryBasedOnCustomer** policy, right click **Version 1.0 - Published**, and then click **Deploy**.</span></span>  
  
#### <a name="to-create-an-esb-itinerary-domain-specific-language-dsl-model-for-globalbank-west-messages"></a><span data-ttu-id="3deb9-162">GlobalBank 西部メッセージの ESB 行程ドメイン固有言語 (DSL) モデルを作成するには</span><span class="sxs-lookup"><span data-stu-id="3deb9-162">To create an ESB itinerary domain-specific language (DSL) model for GlobalBank West messages</span></span>  
  
1.  <span data-ttu-id="3deb9-163">Visual Studio で、C:\HowTos\Patterns\Patterns.sln を開きます。</span><span class="sxs-lookup"><span data-stu-id="3deb9-163">In Visual Studio, open C:\HowTos\Patterns\Patterns.sln.</span></span>  
  
2.  <span data-ttu-id="3deb9-164">ソリューション エクスプ ローラーで右クリックし、 **ItineraryLibrary**プロジェクトをポイントして、**追加**、順にクリックします**新しい行程**します。</span><span class="sxs-lookup"><span data-stu-id="3deb9-164">In Solution Explorer, right-click the **ItineraryLibrary** project, point to **Add**, and then click **New Itinerary**.</span></span>  
  
3.  <span data-ttu-id="3deb9-165">**新しい項目の追加**ダイアログ ボックスの [テンプレート] ペインで、クリックして**ItineraryDsl**します。</span><span class="sxs-lookup"><span data-stu-id="3deb9-165">In the **Add New Item** dialog box, in the Templates pane, click **ItineraryDsl**.</span></span>  
  
4.  <span data-ttu-id="3deb9-166">**名前**ボックスに「 **GlobalBankWestItinerary**、 をクリックし、**追加**します。</span><span class="sxs-lookup"><span data-stu-id="3deb9-166">In the **Name** box, type **GlobalBankWestItinerary**, and then click **Add**.</span></span>  
  
#### <a name="to-configure-the-properties-of-the-globalbank-west-itinerary"></a><span data-ttu-id="3deb9-167">GlobalBank 西部スケジュールのプロパティを構成するには</span><span class="sxs-lookup"><span data-stu-id="3deb9-167">To configure the properties of the GlobalBank West itinerary</span></span>  
  
1.  <span data-ttu-id="3deb9-168">Visual Studio でのデザイン画面をクリックします。 **GlobalBankWestItinerary.itinerary**します。</span><span class="sxs-lookup"><span data-stu-id="3deb9-168">In Visual Studio, click the design surface of **GlobalBankWestItinerary.itinerary**.</span></span> <span data-ttu-id="3deb9-169">**GlobalBankWestItinerary**プロパティ ウィンドウで、次のプロパティを構成します。</span><span class="sxs-lookup"><span data-stu-id="3deb9-169">In the **GlobalBankWestItinerary** Properties window, configure the following properties:</span></span>  
  
    1.  <span data-ttu-id="3deb9-170">**モデル エクスポーター**ドロップダウン リストでは、をクリックして**データベース行程エクスポーター**します。</span><span class="sxs-lookup"><span data-stu-id="3deb9-170">In the **Model Exporter** drop-down list, click **Database Itinerary Exporter**.</span></span>  
  
    2.  <span data-ttu-id="3deb9-171">横にある省略記号ボタン (…) をクリックして、**行程データベース**プロパティ。</span><span class="sxs-lookup"><span data-stu-id="3deb9-171">Click the ellipsis button (...) next to the **Itinerary Database** property.</span></span>  
  
    3.  <span data-ttu-id="3deb9-172">**接続プロパティ**ダイアログ ボックスは itinerary リポジトリ データベースをホストする SQL Server を選択し、データベースの名前を指定し (既定の名前は**EsbItineraryDb**)。</span><span class="sxs-lookup"><span data-stu-id="3deb9-172">In the **Connection Properties** dialog box, choose the SQL Server that hosts the itinerary repository database, and then specify the name of the database (the default name is **EsbItineraryDb**).</span></span>  
  
2.  <span data-ttu-id="3deb9-173">**行程状態**ドロップダウン リストでは、をクリックして**配置済み**します。</span><span class="sxs-lookup"><span data-stu-id="3deb9-173">In the **Itinerary Status** drop-down list, click **Deployed**.</span></span>  
  
    > [!NOTE]
    >  <span data-ttu-id="3deb9-174">この手順では、旅行プランを中央のリポジトリにエクスポートできます。スケジュールを選択し、メッセージの受信時にこのリポジトリからアタッチされました。</span><span class="sxs-lookup"><span data-stu-id="3deb9-174">This step enables you to export the itinerary to a central repository; itineraries can be selected and attached from this repository upon message reception.</span></span> <span data-ttu-id="3deb9-175">後で、ビジネス ルール エンジンは、(BRI) 競合回避モジュールを使用して、受信メッセージを評価し、このリポジトリから適切な旅行プランを選択するスケジュール セレクターのパイプライン コンポーネントを構成します。</span><span class="sxs-lookup"><span data-stu-id="3deb9-175">You will later configure the Itinerary Selector pipeline component to use the Business Rules Engine resolver (BRI) to evaluate inbound messages and select the appropriate itinerary from this repository.</span></span>  
  
#### <a name="to-define-the-structure-of-the-itinerary"></a><span data-ttu-id="3deb9-176">旅行プランの構造を定義するには</span><span class="sxs-lookup"><span data-stu-id="3deb9-176">To define the structure of the itinerary</span></span>  
  
1.  <span data-ttu-id="3deb9-177">ツールボックスからドラッグ、**入口**デザイン サーフェイスにモデル要素。</span><span class="sxs-lookup"><span data-stu-id="3deb9-177">From the Toolbox, drag an **On-Ramp** model element to the design surface.</span></span> <span data-ttu-id="3deb9-178">**OnRamp1**プロパティ ウィンドウで、次のプロパティを構成します。</span><span class="sxs-lookup"><span data-stu-id="3deb9-178">In the **OnRamp1** Properties window, configure the following properties:</span></span>  
  
    1.  <span data-ttu-id="3deb9-179">をクリックして、**名前**プロパティ、および入力**ReceiveNAOrder**します。</span><span class="sxs-lookup"><span data-stu-id="3deb9-179">Click the **Name** property, and then type **ReceiveNAOrder**.</span></span>  
  
    2.  <span data-ttu-id="3deb9-180">**エクステンダー**ドロップダウン リストでは、をクリックして**ESB サービス拡張機能の導入**します。</span><span class="sxs-lookup"><span data-stu-id="3deb9-180">In the **Extender** drop-down list, click **On-Ramp ESB Service Extension**.</span></span>  
  
    3.  <span data-ttu-id="3deb9-181">**BizTalk アプリケーション**ドロップダウン リストでは、をクリックして**Microsoft.Practices.ESB**します。</span><span class="sxs-lookup"><span data-stu-id="3deb9-181">In the **BizTalk Application** drop-down list, click **Microsoft.Practices.ESB**.</span></span>  
  
    4.  <span data-ttu-id="3deb9-182">**受信ポート**ドロップダウン リストでは、をクリックして**OnRamp.Itinerary**します。</span><span class="sxs-lookup"><span data-stu-id="3deb9-182">In the **Receive Port** drop-down list, click **OnRamp.Itinerary**.</span></span>  
  
2.  <span data-ttu-id="3deb9-183">ツールボックスからドラッグして、**傾斜オフ**の右側に配置し、デザイン画面に要素をモデル化し、 **ReceiveNAOrder**モデル要素。</span><span class="sxs-lookup"><span data-stu-id="3deb9-183">From the Toolbox, drag an **Off-Ramp** model element to the design surface, and then place it to the right of the **ReceiveNAOrder** model element.</span></span> <span data-ttu-id="3deb9-184">**OffRamp1**プロパティ ウィンドウで、次のプロパティを構成します。</span><span class="sxs-lookup"><span data-stu-id="3deb9-184">In the **OffRamp1** Properties window, configure the following properties:</span></span>  
  
    1.  <span data-ttu-id="3deb9-185">をクリックして、**名前**プロパティ、および入力**SendNAOrder**します。</span><span class="sxs-lookup"><span data-stu-id="3deb9-185">Click the **Name** property, and then type **SendNAOrder**.</span></span>  
  
    2.  <span data-ttu-id="3deb9-186">**エクステンダー**ドロップダウン リストでは、をクリックして**傾斜オフ ESB サービス拡張**します。</span><span class="sxs-lookup"><span data-stu-id="3deb9-186">In the **Extender** drop-down list, click **Off-Ramp ESB Service Extension**.</span></span>  
  
    3.  <span data-ttu-id="3deb9-187">**BizTalk アプリケーション**ドロップダウン リストでは、をクリックして**GlobalBank.ESB**します。</span><span class="sxs-lookup"><span data-stu-id="3deb9-187">In the **BizTalk Application** drop-down list, click **GlobalBank.ESB**.</span></span>  
  
    4.  <span data-ttu-id="3deb9-188">**送信ポート**ドロップダウン リストでは、をクリックして**DynamicResolutionOneWay**します。</span><span class="sxs-lookup"><span data-stu-id="3deb9-188">In the **Send Port** drop-down list, click **DynamicResolutionOneWay**.</span></span>  
  
3.  <span data-ttu-id="3deb9-189">ツールボックスからドラッグ、**スケジュール サービス**モデルのデザイン画面に要素との間に配置し、 **ReceiveNAOrder**モデル要素と**SendNAOrder**モデル要素。</span><span class="sxs-lookup"><span data-stu-id="3deb9-189">From the Toolbox, drag an **Itinerary Service** model element to the design surface, and then place it between the **ReceiveNAOrder** model element and the **SendNAOrder** model element.</span></span> <span data-ttu-id="3deb9-190">**ItineraryService1**プロパティ ウィンドウで、次のプロパティを構成します。</span><span class="sxs-lookup"><span data-stu-id="3deb9-190">In the **ItineraryService1** Properties window, configure the following properties:</span></span>  
  
    1.  <span data-ttu-id="3deb9-191">をクリックして、**名前**プロパティ、および入力**RouteMessage**します。</span><span class="sxs-lookup"><span data-stu-id="3deb9-191">Click the **Name** property, and then type **RouteMessage**.</span></span>  
  
    2.  <span data-ttu-id="3deb9-192">**旅行プラン サービスのエクステンダー**ドロップダウン リストでは、をクリックして**傾斜オフ旅行プラン サービスの拡張機能**します。</span><span class="sxs-lookup"><span data-stu-id="3deb9-192">In the **Itinerary Service Extender** drop-down list, click **Off-Ramp Itinerary Service Extension**.</span></span>  
  
    3.  <span data-ttu-id="3deb9-193">**傾斜オフ**ドロップダウン リストで、展開**SendNAOrder**、順にクリックします**送信ハンドラー**します。</span><span class="sxs-lookup"><span data-stu-id="3deb9-193">In the **Off-Ramp** drop-down list, expand **SendNAOrder**, and then click **Send Handlers**.</span></span>  
  
4.  <span data-ttu-id="3deb9-194">右クリックし、**リゾルバー**のコレクション、 **RouteMessage**モデル要素をクリックして**新しいリゾルバーを追加**します。</span><span class="sxs-lookup"><span data-stu-id="3deb9-194">Right-click the **Resolver** collection of the **RouteMessage** model element, and then click **Add new Resolver**.</span></span> <span data-ttu-id="3deb9-195">**Resolver1**プロパティ ウィンドウで、次のプロパティを構成します。</span><span class="sxs-lookup"><span data-stu-id="3deb9-195">In the **Resolver1** Properties window, configure the following properties:</span></span>  
  
    1.  <span data-ttu-id="3deb9-196">をクリックして、**名前**プロパティ、および入力**StaticResolver**します。</span><span class="sxs-lookup"><span data-stu-id="3deb9-196">Click the **Name** property, and then type **StaticResolver**.</span></span>  
  
    2.  <span data-ttu-id="3deb9-197">**リゾルバーの実装**ドロップダウン リストでは、をクリックして**静的な競合回避モジュール拡張**します。</span><span class="sxs-lookup"><span data-stu-id="3deb9-197">In the **Resolver Implementation** drop-down list, click **Static Resolver Extension**.</span></span>  
  
    3.  <span data-ttu-id="3deb9-198">**トランスポート名**ドロップダウン リストでは、をクリックして**ファイル**します。</span><span class="sxs-lookup"><span data-stu-id="3deb9-198">In the **Transport Name** drop-down list, click **FILE**.</span></span>  
  
    4.  <span data-ttu-id="3deb9-199">をクリックして、**トランスポート場所**プロパティ、および入力**C:\HowTos\Out\West%MessageID%.xml**します。</span><span class="sxs-lookup"><span data-stu-id="3deb9-199">Click the **Transport Location** property, and then type **C:\HowTos\Out\West%MessageID%.xml**.</span></span>  
  
5.  <span data-ttu-id="3deb9-200">ツールボックス、**コネクタ**します。</span><span class="sxs-lookup"><span data-stu-id="3deb9-200">In the Toolbox, click **Connector**.</span></span> <span data-ttu-id="3deb9-201">接続をドラッグして、 **ReceiveNAOrder**モデル要素に、 **RouteMessage**モデル要素。</span><span class="sxs-lookup"><span data-stu-id="3deb9-201">Drag a connection from the **ReceiveNAOrder** model element to the **RouteMessage** model element.</span></span>  
  
6.  <span data-ttu-id="3deb9-202">ツールボックス、**コネクタ**します。</span><span class="sxs-lookup"><span data-stu-id="3deb9-202">In the Toolbox, click **Connector**.</span></span> <span data-ttu-id="3deb9-203">接続をドラッグして、 **RouteMessage**モデル要素に、 **SendNAOrder**モデル要素。</span><span class="sxs-lookup"><span data-stu-id="3deb9-203">Drag a connection from the **RouteMessage** model element to the **SendNAOrder** model element.</span></span>  
  
#### <a name="to-export-the-model-to-the-itinerary-database"></a><span data-ttu-id="3deb9-204">行程データベースにモデルをエクスポートするには</span><span class="sxs-lookup"><span data-stu-id="3deb9-204">To export the model to the itinerary database</span></span>  
  
1.  <span data-ttu-id="3deb9-205">Visual Studio でのデザイン画面を右クリックし、 **GlobalBankWestItinerary**旅行プランをクリックして**モデルのエクスポート**します。</span><span class="sxs-lookup"><span data-stu-id="3deb9-205">In Visual Studio, right-click the design surface of the **GlobalBankWestItinerary** itinerary, and then click **Export Model**.</span></span>  
  
    > [!NOTE]
    >  <span data-ttu-id="3deb9-206">旅行プランは、行程データベースをエクスポートされ、スケジュール セレクター コンポーネントで使用できるようになりました。</span><span class="sxs-lookup"><span data-stu-id="3deb9-206">The itinerary has been exported to the itinerary database and can now be used by the Itinerary Selector component.</span></span>  
  
2.  <span data-ttu-id="3deb9-207">すべてのプロジェクト成果物を保存します。</span><span class="sxs-lookup"><span data-stu-id="3deb9-207">Save all project artifacts.</span></span>  
  
#### <a name="to-create-an-esb-itinerary-dsl-model-for-globalbank-east-message"></a><span data-ttu-id="3deb9-208">GlobalBank 東部メッセージの ESB 行程 DSL モデルを作成するには</span><span class="sxs-lookup"><span data-stu-id="3deb9-208">To create an ESB itinerary DSL model for GlobalBank East message</span></span>  
  
1.  <span data-ttu-id="3deb9-209">Visual Studio で、C:\HowTos\Patterns.sln を開きます。</span><span class="sxs-lookup"><span data-stu-id="3deb9-209">In Visual Studio, open C:\HowTos\Patterns.sln.</span></span>  
  
2.  <span data-ttu-id="3deb9-210">ソリューション エクスプ ローラーで右クリックし、 **ItineraryLibrary**プロジェクトをポイントして、**追加**、順にクリックします**新しい行程**します。</span><span class="sxs-lookup"><span data-stu-id="3deb9-210">In Solution Explorer, right-click the **ItineraryLibrary** project, point to **Add**, and then click **New Itinerary**.</span></span>  
  
3.  <span data-ttu-id="3deb9-211">**新しい項目の追加**ダイアログ ボックスの [テンプレート] ペインで、クリックして**ItineraryDsl**します。</span><span class="sxs-lookup"><span data-stu-id="3deb9-211">In the **Add New Item** dialog box, in the Templates pane, click **ItineraryDsl**.</span></span>  
  
4.  <span data-ttu-id="3deb9-212">**名前**ボックスに「 **GlobalBankEastItinerary**、 をクリックし、**追加**します。</span><span class="sxs-lookup"><span data-stu-id="3deb9-212">In the **Name** box, type **GlobalBankEastItinerary**, and then click **Add**.</span></span>  
  
#### <a name="to-configure-the-properties-of-the-globalbank-east-itinerary"></a><span data-ttu-id="3deb9-213">GlobalBank 東部スケジュールのプロパティを構成するには</span><span class="sxs-lookup"><span data-stu-id="3deb9-213">To configure the properties of the GlobalBank East itinerary</span></span>  
  
1.  <span data-ttu-id="3deb9-214">Visual Studio でのデザイン画面をクリックします。 **GlobalBankEastItinerary.itinerary**します。</span><span class="sxs-lookup"><span data-stu-id="3deb9-214">In Visual Studio, click the design surface of **GlobalBankEastItinerary.itinerary**.</span></span> <span data-ttu-id="3deb9-215">**GlobalBankEastItinerary**プロパティ ウィンドウで、次のプロパティを構成します。</span><span class="sxs-lookup"><span data-stu-id="3deb9-215">In the **GlobalBankEastItinerary** Properties window, configure the following properties:</span></span>  
  
    1.  <span data-ttu-id="3deb9-216">**モデル エクスポーター**ドロップダウン リストでは、をクリックして**データベース行程エクスポーター**します。</span><span class="sxs-lookup"><span data-stu-id="3deb9-216">In the **Model Exporter** drop-down list, click **Database Itinerary Exporter**.</span></span>  
  
    2.  <span data-ttu-id="3deb9-217">横にある省略記号ボタン (…) をクリックして、**行程データベース**プロパティ。</span><span class="sxs-lookup"><span data-stu-id="3deb9-217">Click the ellipsis button (...) next to the **Itinerary Database** property.</span></span>  
  
    3.  <span data-ttu-id="3deb9-218">**接続プロパティ**ダイアログ ボックスは itinerary リポジトリ データベースをホストする SQL Server を選択し、データベースの名前を指定し (既定の名前は**EsbItineraryDb**)。</span><span class="sxs-lookup"><span data-stu-id="3deb9-218">In the **Connection Properties** dialog box, choose the SQL Server that hosts the itinerary repository database, and then specify the name of the database (the default name is **EsbItineraryDb**).</span></span>  
  
2.  <span data-ttu-id="3deb9-219">**行程状態**ドロップダウン リストでは、をクリックして**配置済み**します。</span><span class="sxs-lookup"><span data-stu-id="3deb9-219">In the **Itinerary Status** drop-down list, click **Deployed**.</span></span>  
  
    > [!NOTE]
    >  <span data-ttu-id="3deb9-220">この手順では、旅行プランを中央のリポジトリにエクスポートできます。スケジュールを選択し、メッセージが受信したときに、このリポジトリからアタッチします。</span><span class="sxs-lookup"><span data-stu-id="3deb9-220">This step enables you to export the itinerary to a central repository; itineraries can be selected and attached from this repository when messages are received.</span></span> <span data-ttu-id="3deb9-221">後で BRI 競合回避モジュールを使用して、受信メッセージを評価し、このリポジトリから適切な旅行プランを選択するスケジュール セレクターのパイプライン コンポーネントを構成します。</span><span class="sxs-lookup"><span data-stu-id="3deb9-221">You will later configure the Itinerary Selector pipeline component to use the BRI resolver to evaluate inbound messages and select the appropriate itinerary from this repository.</span></span>  
  
#### <a name="to-define-the-structure-of-the-itinerary"></a><span data-ttu-id="3deb9-222">旅行プランの構造を定義するには</span><span class="sxs-lookup"><span data-stu-id="3deb9-222">To define the structure of the itinerary</span></span>  
  
1.  <span data-ttu-id="3deb9-223">ツールボックスからドラッグ、**入口**デザイン サーフェイスにモデル要素。</span><span class="sxs-lookup"><span data-stu-id="3deb9-223">From the Toolbox, drag an **On-Ramp** model element to the design surface.</span></span> <span data-ttu-id="3deb9-224">**OnRamp1**プロパティ ウィンドウで、次のプロパティを構成します。</span><span class="sxs-lookup"><span data-stu-id="3deb9-224">In the **OnRamp1** Properties window, configure the following properties:</span></span>  
  
    1.  <span data-ttu-id="3deb9-225">をクリックして、**名前**プロパティ、および入力**ReceiveNAOrder**します。</span><span class="sxs-lookup"><span data-stu-id="3deb9-225">Click the **Name** property, and then type **ReceiveNAOrder**.</span></span>  
  
    2.  <span data-ttu-id="3deb9-226">**エクステンダー**ドロップダウン リストでは、をクリックして**ESB サービス拡張機能の導入**します。</span><span class="sxs-lookup"><span data-stu-id="3deb9-226">In the **Extender** drop-down list, click **On-Ramp ESB Service Extension**.</span></span>  
  
    3.  <span data-ttu-id="3deb9-227">**BizTalk アプリケーション**ドロップダウン リストでは、をクリックして**Microsoft.Practices.ESB**します。</span><span class="sxs-lookup"><span data-stu-id="3deb9-227">In the **BizTalk Application** drop-down list, click **Microsoft.Practices.ESB**.</span></span>  
  
    4.  <span data-ttu-id="3deb9-228">**受信ポート**ドロップダウン リストでは、をクリックして**OnRamp.Itinerary**します。</span><span class="sxs-lookup"><span data-stu-id="3deb9-228">In the **Receive Port** drop-down list, click **OnRamp.Itinerary**.</span></span>  
  
2.  <span data-ttu-id="3deb9-229">ツールボックスからドラッグして、**傾斜オフ**の右側に配置し、デザイン画面に要素をモデル化し、 **ReceiveNAOrder**モデル要素。</span><span class="sxs-lookup"><span data-stu-id="3deb9-229">From the Toolbox, drag an **Off-Ramp** model element to the design surface, and then place it to the right of the **ReceiveNAOrder** model element.</span></span> <span data-ttu-id="3deb9-230">**OffRamp1**プロパティ ウィンドウで、次のプロパティを構成します。</span><span class="sxs-lookup"><span data-stu-id="3deb9-230">In the **OffRamp1** Properties window, configure the following properties:</span></span>  
  
    1.  <span data-ttu-id="3deb9-231">をクリックして、**名前**プロパティ、および入力**SendNAOrder**します。</span><span class="sxs-lookup"><span data-stu-id="3deb9-231">Click the **Name** property, and then type **SendNAOrder**.</span></span>  
  
    2.  <span data-ttu-id="3deb9-232">**エクステンダー**ドロップダウン リストでは、をクリックして**傾斜オフ ESB サービス拡張**します。</span><span class="sxs-lookup"><span data-stu-id="3deb9-232">In the **Extender** drop-down list, click **Off-Ramp ESB Service Extension**.</span></span>  
  
    3.  <span data-ttu-id="3deb9-233">**BizTalk アプリケーション**ドロップダウン リストでは、をクリックして**GlobalBank.ESB**します。</span><span class="sxs-lookup"><span data-stu-id="3deb9-233">In the **BizTalk Application** drop-down list, click **GlobalBank.ESB**.</span></span>  
  
    4.  <span data-ttu-id="3deb9-234">**送信ポート**ドロップダウン リストでは、をクリックして**DynamicResolutionOneWay**します。</span><span class="sxs-lookup"><span data-stu-id="3deb9-234">In the **Send Port** drop-down list, click **DynamicResolutionOneWay**.</span></span>  
  
3.  <span data-ttu-id="3deb9-235">ツールボックスからドラッグ、**スケジュール サービス**モデルのデザイン画面に要素との間に配置し、 **ReceiveNAOrder**モデル要素と**SendNAOrder**モデル要素。</span><span class="sxs-lookup"><span data-stu-id="3deb9-235">From the Toolbox, drag an **Itinerary Service** model element to the design surface, and then place it between the **ReceiveNAOrder** model element and the **SendNAOrder** model element.</span></span> <span data-ttu-id="3deb9-236">**ItineraryService1**プロパティ ウィンドウで、次のプロパティを構成します。</span><span class="sxs-lookup"><span data-stu-id="3deb9-236">In the **ItineraryService1** Properties window, configure the following properties:</span></span>  
  
    1.  <span data-ttu-id="3deb9-237">をクリックして、**名前**プロパティ、および入力**RouteMessage**します。</span><span class="sxs-lookup"><span data-stu-id="3deb9-237">Click the **Name** property, and then type **RouteMessage**.</span></span>  
  
    2.  <span data-ttu-id="3deb9-238">**旅行プラン サービスのエクステンダー**ドロップダウン リストでは、をクリックして**傾斜オフ旅行プラン サービスの拡張機能**します。</span><span class="sxs-lookup"><span data-stu-id="3deb9-238">In the **Itinerary Service Extender** drop-down list, click **Off-Ramp Itinerary Service Extension**.</span></span>  
  
    3.  <span data-ttu-id="3deb9-239">**傾斜オフ**ドロップダウン リストで、展開**SendNAOrder**、順にクリックします**送信ハンドラー**します。</span><span class="sxs-lookup"><span data-stu-id="3deb9-239">In the **Off-Ramp** drop-down list, expand **SendNAOrder**, and then click **Send Handlers**.</span></span>  
  
4.  <span data-ttu-id="3deb9-240">右クリックし、**リゾルバー**のコレクション、 **RouteMessage**モデル要素をクリックして**新しいリゾルバーを追加**します。</span><span class="sxs-lookup"><span data-stu-id="3deb9-240">Right-click the **Resolver** collection of the **RouteMessage** model element, and then click **Add new Resolver**.</span></span> <span data-ttu-id="3deb9-241">**Resolver1**プロパティ ウィンドウで、次のプロパティを構成します。</span><span class="sxs-lookup"><span data-stu-id="3deb9-241">In the **Resolver1** Properties window, configure the following properties:</span></span>  
  
    1.  <span data-ttu-id="3deb9-242">をクリックして、**名前**プロパティ、および入力**StaticResolver**します。</span><span class="sxs-lookup"><span data-stu-id="3deb9-242">Click the **Name** property, and then type **StaticResolver**.</span></span>  
  
    2.  <span data-ttu-id="3deb9-243">**リゾルバーの実装**ドロップダウン リストでは、をクリックして**静的な競合回避モジュール拡張**します。</span><span class="sxs-lookup"><span data-stu-id="3deb9-243">In the **Resolver Implementation** drop-down list, click **Static Resolver Extension**.</span></span>  
  
    3.  <span data-ttu-id="3deb9-244">**トランスポート名**ドロップダウン リストでは、をクリックして**ファイル**します。</span><span class="sxs-lookup"><span data-stu-id="3deb9-244">In the **Transport Name** drop-down list, click **FILE**.</span></span>  
  
    4.  <span data-ttu-id="3deb9-245">をクリックして、**トランスポート場所**プロパティ、および入力**C:\HowTos\Out\East%MessageID%.xml**します。</span><span class="sxs-lookup"><span data-stu-id="3deb9-245">Click the **Transport Location** property, and then type **C:\HowTos\Out\East%MessageID%.xml**.</span></span>  
  
5.  <span data-ttu-id="3deb9-246">ツールボックス、**コネクタ**します。</span><span class="sxs-lookup"><span data-stu-id="3deb9-246">In the Toolbox, click **Connector**.</span></span> <span data-ttu-id="3deb9-247">接続をドラッグして、 **ReceiveNAOrder**モデル要素に、 **RouteMessage**モデル要素。</span><span class="sxs-lookup"><span data-stu-id="3deb9-247">Drag a connection from the **ReceiveNAOrder** model element to the **RouteMessage** model element.</span></span>  
  
6.  <span data-ttu-id="3deb9-248">ツールボックス、**コネクタ**します。</span><span class="sxs-lookup"><span data-stu-id="3deb9-248">In the Toolbox, click **Connector**.</span></span> <span data-ttu-id="3deb9-249">接続をドラッグして、 **RouteMessage**モデル要素に、 **SendNAOrder**モデル要素。</span><span class="sxs-lookup"><span data-stu-id="3deb9-249">Drag a connection from the **RouteMessage** model element to the **SendNAOrder** model element.</span></span>  
  
#### <a name="to-export-the-model-to-the-itinerary-database"></a><span data-ttu-id="3deb9-250">行程データベースにモデルをエクスポートするには</span><span class="sxs-lookup"><span data-stu-id="3deb9-250">To export the model to the itinerary database</span></span>  
  
1.  <span data-ttu-id="3deb9-251">Visual Studio でのデザイン画面を右クリックし、 **GlobalBankEastItinerary**旅行プランをクリックして**モデルのエクスポート**します。</span><span class="sxs-lookup"><span data-stu-id="3deb9-251">In Visual Studio, right-click the design surface of the **GlobalBankEastItinerary** itinerary, and then click **Export Model**.</span></span>  
  
    > [!NOTE]
    >  <span data-ttu-id="3deb9-252">旅行プランは、行程データベースをエクスポートされ、スケジュール セレクター コンポーネントで使用できるようになりました。</span><span class="sxs-lookup"><span data-stu-id="3deb9-252">The itinerary has been exported to the itinerary database and can now be used by the Itinerary Selector component.</span></span>  
  
2.  <span data-ttu-id="3deb9-253">すべてのプロジェクト成果物を保存します。</span><span class="sxs-lookup"><span data-stu-id="3deb9-253">Save all project artifacts.</span></span>  
  
#### <a name="to-create-and-configure-an-esb-on-ramp"></a><span data-ttu-id="3deb9-254">作成および ESB 入り口を構成するには</span><span class="sxs-lookup"><span data-stu-id="3deb9-254">To create and configure an ESB on-ramp</span></span>  
  
1.  <span data-ttu-id="3deb9-255">クリックして**開始**タスク バーで、をポイント**すべてのプログラム**、 をポイント**BizTalk Server**、順にクリックします**BizTalk Server 管理**します。</span><span class="sxs-lookup"><span data-stu-id="3deb9-255">Click **Start** on the taskbar, point to **All Programs**, point to **BizTalk Server**, and then click **BizTalk Server Administration**.</span></span>  
  
2.  <span data-ttu-id="3deb9-256">BizTalk Server 管理コンソールで  **BizTalk グループ**、展開**アプリケーション**、順に展開**Microsoft.Practices.ESB**します。</span><span class="sxs-lookup"><span data-stu-id="3deb9-256">In the BizTalk Server Administration Console, expand **BizTalk Group**, expand **Applications**, and then expand **Microsoft.Practices.ESB**.</span></span>  
  
3.  <span data-ttu-id="3deb9-257">右クリック**受信場所**、 をポイント**新規**、 をクリックし、**一方向の受信場所**します。</span><span class="sxs-lookup"><span data-stu-id="3deb9-257">Right-click **Receive Locations**, point to **New**, and then click **One-way Receive Location**.</span></span>  
  
4.  <span data-ttu-id="3deb9-258">**受信ポートの選択**ダイアログ ボックスで、をクリックして**OnRamp.Itinerary**、順にクリックします**OK**。</span><span class="sxs-lookup"><span data-stu-id="3deb9-258">In the **Select a Receive Port** dialog box, click **OnRamp.Itinerary**, and then click **OK**.</span></span>  
  
5.  <span data-ttu-id="3deb9-259">**受信場所のプロパティ** ダイアログ ボックスで、**名前**ボックスに「 **OnRamp.Itinerary.HowTo**します。</span><span class="sxs-lookup"><span data-stu-id="3deb9-259">In the **Receive Location Properties** dialog box, in the **Name** box, type **OnRamp.Itinerary.HowTo**.</span></span>  
  
6.  <span data-ttu-id="3deb9-260">**型**ドロップダウン リストでは、をクリックして**ファイル**、順にクリックします**構成**します。</span><span class="sxs-lookup"><span data-stu-id="3deb9-260">In the **Type** drop-down list, click **FILE**, and then click **Configure**.</span></span>  
  
7.  <span data-ttu-id="3deb9-261">**FILE トランスポートのプロパティ** ダイアログ ボックスで、**受信フォルダー**ボックスに「 **C:\HowTos\DropFolder**、順にクリックします**OK**します。</span><span class="sxs-lookup"><span data-stu-id="3deb9-261">In the **FILE Transport Properties** dialog box, in the **Receive folder** box, type **C:\HowTos\DropFolder**, and then click **OK**.</span></span>  
  
#### <a name="to-configure-the-itinerary-selector-pipeline-component"></a><span data-ttu-id="3deb9-262">旅行プラン セレクターのパイプライン コンポーネントを構成するには</span><span class="sxs-lookup"><span data-stu-id="3deb9-262">To configure the Itinerary Selector pipeline component</span></span>  
  
1.  <span data-ttu-id="3deb9-263">**受信場所のプロパティ** ダイアログ ボックスで、**受信パイプライン**ドロップダウン リストでは、をクリックして**ItinerarySelectReceiveXml**、省略記号ボタン (... を順にクリックします).</span><span class="sxs-lookup"><span data-stu-id="3deb9-263">In the **Receive Location Properties** dialog box, in the **Receive pipeline** drop-down list, click **ItinerarySelectReceiveXml**, and then click the ellipsis button (...).</span></span>  
  
2.  <span data-ttu-id="3deb9-264">使用して、**パイプラインの構成**、以下の構成 ダイアログ ボックス**スケジュール セレクター**コンポーネントのプロパティ。</span><span class="sxs-lookup"><span data-stu-id="3deb9-264">Use the **Configure Pipeline** dialog box to configure the following **Itinerary Selector** component properties:</span></span>  
  
    1.  <span data-ttu-id="3deb9-265">をクリックして、 **ItineraryFactKey**プロパティ、および入力**Resolver.Itinerary**します。</span><span class="sxs-lookup"><span data-stu-id="3deb9-265">Click the **ItineraryFactKey** property, and then type **Resolver.Itinerary**.</span></span>  
  
    2.  <span data-ttu-id="3deb9-266">をクリックして、 **ResolverConnectionString**プロパティ、および入力**BRI:\\\policy=ResolveItineraryBasedOnCustomer;useMsg=true;recognizeMessageFormat=true;**</span><span class="sxs-lookup"><span data-stu-id="3deb9-266">Click the **ResolverConnectionString** property, and then type **BRI:\\\policy=ResolveItineraryBasedOnCustomer;useMsg=true;recognizeMessageFormat=true;**</span></span>  
  
    3.  <span data-ttu-id="3deb9-267">クリックして**OK**を閉じる、**パイプラインの構成** ダイアログ ボックス。</span><span class="sxs-lookup"><span data-stu-id="3deb9-267">Click **OK** to close the **Configure Pipeline** dialog box.</span></span>  
  
3.  <span data-ttu-id="3deb9-268">クリックして**OK**を閉じる、**受信場所のプロパティ** ダイアログ ボックス。</span><span class="sxs-lookup"><span data-stu-id="3deb9-268">Click **OK** to close the **Receive Location Properties** dialog box.</span></span>  
  
4.  <span data-ttu-id="3deb9-269">右クリックし、BizTalk Server 管理コンソールで、 **OnRamp.Itinerary.HowTo**受信場所をクリックして**を有効にする**します。</span><span class="sxs-lookup"><span data-stu-id="3deb9-269">In the BizTalk Server Administration Console, right-click the **OnRamp.Itinerary.HowTo** receive location, and then click **Enable**.</span></span>  
  
#### <a name="to-test-the-itinerary-selector-and-business-rules"></a><span data-ttu-id="3deb9-270">スケジュール セレクターとビジネス ルールをテストするには</span><span class="sxs-lookup"><span data-stu-id="3deb9-270">To test the itinerary selector and business rules</span></span>  
  
1.  <span data-ttu-id="3deb9-271">Windows エクスプ ローラーでは、C:\HowTos を参照します。</span><span class="sxs-lookup"><span data-stu-id="3deb9-271">In Windows Explorer, browse to C:\HowTos.</span></span>  
  
2.  <span data-ttu-id="3deb9-272">コピー (移動しないでください) ファイル East.xml と West.xml DropFolder フォルダーにします。</span><span class="sxs-lookup"><span data-stu-id="3deb9-272">Copy (do not move) the files East.xml and West.xml to the DropFolder folder.</span></span>  
  
3.  <span data-ttu-id="3deb9-273">C:\HowTos\Out に移動します。East%MessageID%.xml と West%MessageID%.xml メッセージが、ディレクトリに書き込まれたことを確認します。</span><span class="sxs-lookup"><span data-stu-id="3deb9-273">Browse to C:\HowTos\Out. Verify that the East%MessageID%.xml and West%MessageID%.xml messages have been written to the directory.</span></span>  
  
    > [!NOTE]
    >  <span data-ttu-id="3deb9-274">Customer 要素の値を除いて同一です、ただしスケジュール セレクターのパイプライン コンポーネントの解像度に基づく別のスケジュールを使用して、メッセージが処理されました。</span><span class="sxs-lookup"><span data-stu-id="3deb9-274">Though identical except for the value of the customer element, the messages were processed using different itineraries, based on the resolution of the Itinerary Selector pipeline component.</span></span>  
  
4.  <span data-ttu-id="3deb9-275">右クリックし、BizTalk Server 管理コンソールで、 **OnRamp.Itinerary.HowTo**受信場所をクリックして**を無効にする**します。</span><span class="sxs-lookup"><span data-stu-id="3deb9-275">In the BizTalk Server Administration Console, right-click the **OnRamp.Itinerary.HowTo** receive location, and then click **Disable**.</span></span>  
  
5.  <span data-ttu-id="3deb9-276">後に、 **OnRamp.Itinerary.HowTo**受信場所が無効になっている、右クリックし、 をクリックし、**削除**します。</span><span class="sxs-lookup"><span data-stu-id="3deb9-276">After the **OnRamp.Itinerary.HowTo** receive location is disabled, right-click it, and then click **Delete**.</span></span> <span data-ttu-id="3deb9-277">**削除の確認の受信場所**ダイアログ ボックスで、をクリックして**はい**します。</span><span class="sxs-lookup"><span data-stu-id="3deb9-277">In the **Confirm delete receive location** dialog box, click **Yes**.</span></span>  
  
## <a name="additional-resources"></a><span data-ttu-id="3deb9-278">その他のリソース</span><span class="sxs-lookup"><span data-stu-id="3deb9-278">Additional Resources</span></span>  
 <span data-ttu-id="3deb9-279">詳細については、次の関連項目を参照してください。</span><span class="sxs-lookup"><span data-stu-id="3deb9-279">For more information, see the following related topics:</span></span>  
  
-   [<span data-ttu-id="3deb9-280">方法: 別個のスケジュールを利用し、インターチェンジを分割して結果的に生成されたメッセージを複数のファイルの場所に送る</span><span class="sxs-lookup"><span data-stu-id="3deb9-280">How to: Split an Interchange and Route the Resulting Messages to Multiple File Locations Using Distinct Itineraries</span></span>](../esb-toolkit/split-an-interchange-and-route-messages-to-multiple-locations-using-itineraries.md)  
  
-   [<span data-ttu-id="3deb9-281">開発アクティビティ</span><span class="sxs-lookup"><span data-stu-id="3deb9-281">Development Activities</span></span>](../esb-toolkit/development-activities.md)  
  
-   [<span data-ttu-id="3deb9-282">動的解決サンプルをインストールし、実行する</span><span class="sxs-lookup"><span data-stu-id="3deb9-282">Installing and Running the Dynamic Resolution Sample</span></span>](../esb-toolkit/installing-and-running-the-dynamic-resolution-sample.md)  
  
-   [<span data-ttu-id="3deb9-283">動的な解決とルーティングを利用する</span><span class="sxs-lookup"><span data-stu-id="3deb9-283">Using Dynamic Resolution and Routing</span></span>](../esb-toolkit/using-dynamic-resolution-and-routing.md)  
  
-   [<span data-ttu-id="3deb9-284">メッセージ ルーティング パターン</span><span class="sxs-lookup"><span data-stu-id="3deb9-284">Message Routing Patterns</span></span>](../esb-toolkit/message-routing-patterns.md)