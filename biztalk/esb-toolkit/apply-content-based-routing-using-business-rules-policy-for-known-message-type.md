---
title: 操作方法:既知のメッセージの種類のルール ポリシーの実装のビジネスを使用してコンテンツ ベース ルーティング |Microsoft Docs
ms.custom: ''
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: ''
ms.suite: ''
ms.tgt_pltfrm: ''
ms.topic: article
ms.assetid: 44451c85-929a-4d13-b0dd-53ea600d0859
caps.latest.revision: 4
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: f687ae84782866809ef882a5389e35da8f7ce5a9
ms.sourcegitcommit: 381e83d43796a345488d54b3f7413e11d56ad7be
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 05/07/2019
ms.locfileid: "65392313"
---
# <a name="how-to-implement-content-based-routing-using-a-business-rules-policy-for-a-known-message-type"></a><span data-ttu-id="a58cf-102">操作方法:コンテンツ ベース ルーティング ポリシーを使用してビジネス ルールの既知のメッセージの種類の実装します。</span><span class="sxs-lookup"><span data-stu-id="a58cf-102">How to: Implement Content-Based Routing Using a Business Rules Policy for a Known Message Type</span></span>
## <a name="goal"></a><span data-ttu-id="a58cf-103">[目標]</span><span class="sxs-lookup"><span data-stu-id="a58cf-103">Goal</span></span>  
 <span data-ttu-id="a58cf-104">このセクションでは動的に基づくメッセージをルーティングするスケジュールを作成する方法を示します (Microsoft BizTalk Server 構成データベースに展開されたスキーマ) の既知のメッセージ型のコンテンツに対して、ビジネス規則を使用してポリシー。</span><span class="sxs-lookup"><span data-stu-id="a58cf-104">This section demonstrates how to create an itinerary that dynamically routes a message, based on the content of a known message type (schema deployed to the Microsoft BizTalk Server Configuration database), using a business rules policy.</span></span>  
  
 <span data-ttu-id="a58cf-105">このトピックでは、次の手順を行います。</span><span class="sxs-lookup"><span data-stu-id="a58cf-105">In this How-to topic, you will complete the following steps:</span></span>  
  
-   <span data-ttu-id="a58cf-106">コンテンツに基づいてメッセージのルーティングに使用されるビジネス ルール ポリシーを作成します。</span><span class="sxs-lookup"><span data-stu-id="a58cf-106">Create a business rules policy that will be used to route a message based on content.</span></span>  
  
-   <span data-ttu-id="a58cf-107">BRE 競合回避モジュールにメッセージを動的にルーティングすると、スケジュール ルーティング スリップを作成します。</span><span class="sxs-lookup"><span data-stu-id="a58cf-107">Create an itinerary routing slip with a BRE resolver to dynamically route a message.</span></span>  
  
-   <span data-ttu-id="a58cf-108">旅行プランのテスト用クライアントのサンプル アプリケーションを使用して、旅行プランをテストします。</span><span class="sxs-lookup"><span data-stu-id="a58cf-108">Test the itinerary using the Itinerary Test Client sample application.</span></span>  
  
## <a name="prerequisites"></a><span data-ttu-id="a58cf-109">前提条件</span><span class="sxs-lookup"><span data-stu-id="a58cf-109">Prerequisites</span></span>  
 <span data-ttu-id="a58cf-110">この操作方法に関するトピックの手順の完了が必要、[開発活動の前提条件](../esb-toolkit/prerequisites-for-the-development-activities.md)します。</span><span class="sxs-lookup"><span data-stu-id="a58cf-110">The procedures in this How-to topic require the completion of the [Prerequisites for the Development Activities](../esb-toolkit/prerequisites-for-the-development-activities.md).</span></span>  
  
## <a name="before-you-begin"></a><span data-ttu-id="a58cf-111">はじめに</span><span class="sxs-lookup"><span data-stu-id="a58cf-111">Before You Begin</span></span>  
 <span data-ttu-id="a58cf-112">この操作方法に関するトピックの後半の手順を実行する前に、次のタスクを実行します。</span><span class="sxs-lookup"><span data-stu-id="a58cf-112">Complete the following tasks before you perform the steps later in this How-to topic:</span></span>  
  
- <span data-ttu-id="a58cf-113">GlobalBank 西部テスト メッセージを作成します。</span><span class="sxs-lookup"><span data-stu-id="a58cf-113">Create the GlobalBank West test message.</span></span>  
  
- <span data-ttu-id="a58cf-114">GlobalBank 東部のテスト メッセージを作成します。</span><span class="sxs-lookup"><span data-stu-id="a58cf-114">Create the GlobalBank East test message.</span></span>  
  
  <span data-ttu-id="a58cf-115">次の手順では、これらの各方法について説明します。</span><span class="sxs-lookup"><span data-stu-id="a58cf-115">The following procedures describe how to do each of these.</span></span>  
  
#### <a name="to-create-the-globalbank-west-test-message"></a><span data-ttu-id="a58cf-116">GlobalBank 西部テスト メッセージを作成するには</span><span class="sxs-lookup"><span data-stu-id="a58cf-116">To create the GlobalBank West test message</span></span>  
  
1.  <span data-ttu-id="a58cf-117">Windows エクスプ ローラーでは、C:\HowTos を参照します。</span><span class="sxs-lookup"><span data-stu-id="a58cf-117">In Windows Explorer, browse to C:\HowTos.</span></span>  
  
2.  <span data-ttu-id="a58cf-118">NAOrderDoc.xml のコピーを作成し、コピー West.xml、名前を付けます。</span><span class="sxs-lookup"><span data-stu-id="a58cf-118">Create a copy of NAOrderDoc.xml, and then name the copy West.xml.</span></span>  
  
3.  <span data-ttu-id="a58cf-119">メモ帳で、West.xml を開きの値を変更、 **customerName**要素**GlobalBankWest**します。</span><span class="sxs-lookup"><span data-stu-id="a58cf-119">In Notepad, open West.xml, and then change the value of the **customerName** element to **GlobalBankWest**.</span></span>  
  
4.  <span data-ttu-id="a58cf-120">West.xml を utf-8 として保存し、メモ帳を終了します。</span><span class="sxs-lookup"><span data-stu-id="a58cf-120">Save West.xml as UTF-8, and then close Notepad.</span></span>  
  
#### <a name="to-create-the-globalbank-east-test-message"></a><span data-ttu-id="a58cf-121">GlobalBank 東部テスト メッセージを作成するには</span><span class="sxs-lookup"><span data-stu-id="a58cf-121">To create the GlobalBank East test message</span></span>  
  
1.  <span data-ttu-id="a58cf-122">Windows エクスプ ローラーでは、C:\HowTos を参照します。</span><span class="sxs-lookup"><span data-stu-id="a58cf-122">In Windows Explorer, browse to C:\HowTos.</span></span>  
  
2.  <span data-ttu-id="a58cf-123">NAOrderDoc.xml のコピーを作成し、コピー East.xml、名前を付けます。</span><span class="sxs-lookup"><span data-stu-id="a58cf-123">Create a copy of NAOrderDoc.xml, and then name the copy East.xml.</span></span>  
  
3.  <span data-ttu-id="a58cf-124">メモ帳で、East.xml を開きの値を変更、 **customerName**要素**GlobalBankEast**します。</span><span class="sxs-lookup"><span data-stu-id="a58cf-124">In Notepad, open East.xml, and then change the value of the **customerName** element to **GlobalBankEast**.</span></span>  
  
4.  <span data-ttu-id="a58cf-125">East.xml を utf-8 として保存し、メモ帳を終了します。</span><span class="sxs-lookup"><span data-stu-id="a58cf-125">Save East.xml as UTF-8, and then close Notepad.</span></span>  
  
## <a name="steps"></a><span data-ttu-id="a58cf-126">手順</span><span class="sxs-lookup"><span data-stu-id="a58cf-126">Steps</span></span>  
  
#### <a name="to-create-a-bre-policy-to-route-using-custom-message-properties"></a><span data-ttu-id="a58cf-127">カスタム メッセージ プロパティを使用してルーティングに BRE ポリシーを作成するには</span><span class="sxs-lookup"><span data-stu-id="a58cf-127">To create a BRE policy to route using custom message properties</span></span>  
 <span data-ttu-id="a58cf-128">このルールでは、顧客の名前を使用して、メッセージをルーティングするために使用するエンドポイントを動的に設定。</span><span class="sxs-lookup"><span data-stu-id="a58cf-128">This rule will use the customer's name to dynamically set the endpoint used to route the message.</span></span>  
  
1.  <span data-ttu-id="a58cf-129">クリックして**開始**タスク バーで、をポイント**すべてのプログラム**、 をポイント**BizTalk Server**、順にクリックします**ビジネス ルール作成ツール**します。</span><span class="sxs-lookup"><span data-stu-id="a58cf-129">Click **Start** on the taskbar, point to **All Programs**, point to **BizTalk Server**, and then click **Business Rule Composer**.</span></span>  
  
2.  <span data-ttu-id="a58cf-130">ポリシー エクスプ ローラーで右クリック**ポリシー**、 をクリックし、**新しいポリシーの追加**します。</span><span class="sxs-lookup"><span data-stu-id="a58cf-130">In Policy Explorer, right-click **Policies**, and then click **Add New Policy**.</span></span> <span data-ttu-id="a58cf-131">ポリシーの名前**RouteBasedOnCustomerKnownType**します。</span><span class="sxs-lookup"><span data-stu-id="a58cf-131">Name the policy **RouteBasedOnCustomerKnownType**.</span></span>  
  
#### <a name="to-add-a-routing-rule-for-customer-globalbank-west"></a><span data-ttu-id="a58cf-132">GlobalBank 西部の顧客のルーティング規則を追加するには</span><span class="sxs-lookup"><span data-stu-id="a58cf-132">To add a routing rule for customer GlobalBank West</span></span>  
  
1. <span data-ttu-id="a58cf-133">**RouteBasedOnCustomerKnownType**ポリシーを右クリックして**バージョン 1.0 (未保存)**、順にクリックします**新しいルールの追加**します。</span><span class="sxs-lookup"><span data-stu-id="a58cf-133">In the **RouteBasedOnCustomerKnownType** policy, right-click **Version 1.0 (not saved)**, and then click **Add New Rule**.</span></span> <span data-ttu-id="a58cf-134">ルールの名前として**SetWestEndpoint**します。</span><span class="sxs-lookup"><span data-stu-id="a58cf-134">Name the rule **SetWestEndpoint**.</span></span>  
  
2. <span data-ttu-id="a58cf-135">ファクト エクスプ ローラーでクリックして、 **XML スキーマ** タブを右クリックして**スキーマ**、順にクリックします**参照**します。</span><span class="sxs-lookup"><span data-stu-id="a58cf-135">In Facts Explorer, click the **XML Schemas** tab, right-click **Schemas**, and then click **Browse**.</span></span>  
  
3. <span data-ttu-id="a58cf-136">**スキーマ ファイル** ダイアログ ボックスで、C:\Projects\Microsoft.Practices.ESB\Source\Samples\DynamicResolution\Source\ESB を参照します。DynamicResolution.Schemas で、 **NAOrderDoc.xsd**、 をクリックし、**オープン**します。</span><span class="sxs-lookup"><span data-stu-id="a58cf-136">In the **Schema Files** dialog box, browse to C:\Projects\Microsoft.Practices.ESB\Source\Samples\DynamicResolution\Source\ESB.DynamicResolution.Schemas, select **NAOrderDoc.xsd**, and then click **Open**.</span></span>  
  
   > [!NOTE]
   >  <span data-ttu-id="a58cf-137">テストに使用する西部と東部のメッセージを作成するために使用された NAOrderDoc.xml メッセージを定義するスキーマです。</span><span class="sxs-lookup"><span data-stu-id="a58cf-137">This is the schema that defines the NAOrderDoc.xml message, which was used to create the West and East messages you will use for testing.</span></span>  
  
4. <span data-ttu-id="a58cf-138">ファクト エクスプ ローラーでクリックして**NAOrderDoc.xsd**、プロパティ ペインをクリックし、**ドキュメントの種類**プロパティ、および入力**GlobalBank.ESB.DynamicResolution.Schemas.NAOrderDoc**.</span><span class="sxs-lookup"><span data-stu-id="a58cf-138">In Facts Explorer, click **NAOrderDoc.xsd**, and then in the Properties pane, click the **Document Type** property, and then type **GlobalBank.ESB.DynamicResolution.Schemas.NAOrderDoc**.</span></span>  
  
   > [!NOTE]
   >  <span data-ttu-id="a58cf-139">これは、スキーマの完全修飾名です。</span><span class="sxs-lookup"><span data-stu-id="a58cf-139">This is the fully qualified name of the schema.</span></span>  
  
5. <span data-ttu-id="a58cf-140">ファクト エクスプ ローラーで、 **NAOrderDoc.xsd**、順に展開**OrderDoc**します。</span><span class="sxs-lookup"><span data-stu-id="a58cf-140">In Facts Explorer, expand **NAOrderDoc.xsd**, and then expand **OrderDoc**.</span></span>  
  
6. <span data-ttu-id="a58cf-141">ルール ウィンドウで、右クリック**条件**、 をポイント**述語**、 をクリックし、**等しい**。</span><span class="sxs-lookup"><span data-stu-id="a58cf-141">In the Rule window, right-click **Conditions**, point to **Predicates**, and then click **Equal**.</span></span>  
  
7. <span data-ttu-id="a58cf-142">ファクト エクスプ ローラーからドラッグして、 **customerName**要素を **[引数 1]** ノードの下**条件**します。</span><span class="sxs-lookup"><span data-stu-id="a58cf-142">From Facts Explorer, drag the **customerName** element to the **argument1** node under **Conditions**.</span></span>  
  
8. <span data-ttu-id="a58cf-143">をクリックして、 **[引数 2]** ノード、および入力**GlobalBankWest**します。</span><span class="sxs-lookup"><span data-stu-id="a58cf-143">Click the **argument2** node, and then type **GlobalBankWest**.</span></span>  
  
9. <span data-ttu-id="a58cf-144">ファクト エクスプ ローラーでクリックして、**ボキャブラリ** タブで、展開**ESB します。EndPointInfo**、順に展開**バージョン 1.0**します。</span><span class="sxs-lookup"><span data-stu-id="a58cf-144">In Facts Explorer, click the **Vocabularies** tab, expand **ESB.EndPointInfo**, and then expand **Version 1.0**.</span></span>  
  
   > [!NOTE]
   >  <span data-ttu-id="a58cf-145">[!INCLUDE[esbToolkit](../includes/esbtoolkit-md.md)] ESB で使用するための規則を作成するために使用できるいくつかのボキャブラリが含まれています。</span><span class="sxs-lookup"><span data-stu-id="a58cf-145">The [!INCLUDE[esbToolkit](../includes/esbtoolkit-md.md)] includes several vocabularies that can be used for creating rules for use in the ESB.</span></span> <span data-ttu-id="a58cf-146">これらのいくつかは、置き換えをまたは独自のボキャブラリで補強します。</span><span class="sxs-lookup"><span data-stu-id="a58cf-146">Some of these should be replaced or augmented with your own vocabularies.</span></span> <span data-ttu-id="a58cf-147">たとえば、 **DynamicRunTimeMaptypes**で用意されているマップの定義が含まれて、 **GlobalBank**サンプル。</span><span class="sxs-lookup"><span data-stu-id="a58cf-147">For example, the **DynamicRunTimeMaptypes** has definitions for the maps provided in the **GlobalBank** samples.</span></span>  
  
10. <span data-ttu-id="a58cf-148">ファクト エクスプ ローラーからドラッグして、**終点の送信トランスポート場所の設定**の定義を**アクション**します。</span><span class="sxs-lookup"><span data-stu-id="a58cf-148">From Facts Explorer, drag the **Set End Point Outbound Transport Location** definition to **Actions**.</span></span>  
  
11. <span data-ttu-id="a58cf-149">クリックして**\<空の文字列\>** し入力**C:\HowTos\Out\West%MessageID%.xml**します。</span><span class="sxs-lookup"><span data-stu-id="a58cf-149">Click **\<empty string\>** and then type **C:\HowTos\Out\West%MessageID%.xml**.</span></span>  
  
12. <span data-ttu-id="a58cf-150">ファクト エクスプ ローラーからドラッグして、**設定の終了点送信トランスポートの種類**の定義を**アクション**します。</span><span class="sxs-lookup"><span data-stu-id="a58cf-150">From Facts Explorer, drag the **Set End Point Outbound Transport Type** definition to **Actions**.</span></span>  
  
13. <span data-ttu-id="a58cf-151">ファクト エクスプ ローラーで、 **ESB します。TransportTypes**、展開**バージョン 1.0**、し、ドラッグ、**アダプター プロバイダー**の定義を**\<空の文字列\>**.</span><span class="sxs-lookup"><span data-stu-id="a58cf-151">In Facts Explorer, expand **ESB.TransportTypes**, expand **Version 1.0**, and then drag the **Adaptor Providers** definition to **\<empty string\>**.</span></span>  
  
14. <span data-ttu-id="a58cf-152">**アクション**ウィンドウで、展開、**アダプター プロバイダー**ドロップダウン リスト、およびクリック**ファイル**します。</span><span class="sxs-lookup"><span data-stu-id="a58cf-152">In the **Actions** pane, expand the **Adaptor Providers** drop-down list, and then click **FILE**.</span></span>  
  
#### <a name="to-add-a-routing-rule-for-customer-globalbank-east"></a><span data-ttu-id="a58cf-153">GlobalBank 東部の顧客のルーティング規則を追加するには</span><span class="sxs-lookup"><span data-stu-id="a58cf-153">To add a routing rule for customer GlobalBank East</span></span>  
  
1.  <span data-ttu-id="a58cf-154">ポリシー エクスプ ローラーで右クリックし、 **SetWestEndpoint**ルールは、クリックして**コピー**します。</span><span class="sxs-lookup"><span data-stu-id="a58cf-154">In Policy Explorer, right-click the **SetWestEndpoint** rule, and then click **Copy**.</span></span>  
  
2.  <span data-ttu-id="a58cf-155">右クリック**バージョン 1.0 (未保存)**、 をクリックし、**貼り付け**します。</span><span class="sxs-lookup"><span data-stu-id="a58cf-155">Right-click **Version 1.0 (not saved)**, and then click **Paste**.</span></span>  
  
3.  <span data-ttu-id="a58cf-156">**新しいルール名**ダイアログ ボックスに「 **SetEastEndpoint**、順にクリックします**OK**します。</span><span class="sxs-lookup"><span data-stu-id="a58cf-156">In the **New Rule Name** dialog box, type **SetEastEndpoint**, and then click **OK**.</span></span>  
  
4.  <span data-ttu-id="a58cf-157">ポリシー エクスプ ローラーでクリックして、 **SetEastEndpoint**ルール。</span><span class="sxs-lookup"><span data-stu-id="a58cf-157">In Policy Explorer, click the **SetEastEndpoint** rule.</span></span>  
  
5.  <span data-ttu-id="a58cf-158">**条件**セクションを右クリックして**GlobalBankWest**、 をクリックし、**引数の再設定**します。</span><span class="sxs-lookup"><span data-stu-id="a58cf-158">In the **Conditions** section, right-click **GlobalBankWest**, and then click **Reset argument**.</span></span>  
  
6.  <span data-ttu-id="a58cf-159">クリックして **[引数 2]**、し、入力**GlobalBankEast**します。</span><span class="sxs-lookup"><span data-stu-id="a58cf-159">Click **argument2**, and then type **GlobalBankEast**.</span></span>  
  
7.  <span data-ttu-id="a58cf-160">**アクション**セクションで、右クリック**C:\HowTos\Out\West%MessageID%.xml**、 をクリックし、**引数の再設定**します。</span><span class="sxs-lookup"><span data-stu-id="a58cf-160">In the **Actions** section, right-click **C:\HowTos\Out\West%MessageID%.xml**, and then click **Reset argument**.</span></span>  
  
8.  <span data-ttu-id="a58cf-161">クリックして**\<空の文字列\>**、し、入力**C:\HowTos\Out\East%MessageID%.xml**します。</span><span class="sxs-lookup"><span data-stu-id="a58cf-161">Click **\<empty string\>**, and then type **C:\HowTos\Out\East%MessageID%.xml**.</span></span>  
  
#### <a name="to-add-a-routing-rule-for-unknown-customers"></a><span data-ttu-id="a58cf-162">不明な顧客のルーティング規則を追加するには</span><span class="sxs-lookup"><span data-stu-id="a58cf-162">To add a routing rule for unknown customers</span></span>  
  
1.  <span data-ttu-id="a58cf-163">RouteBasedOnCustomerKnownType ポリシーでは、バージョン 1.0 (未保存) を右クリックし、新しいルールの追加を順にクリックします。</span><span class="sxs-lookup"><span data-stu-id="a58cf-163">In the RouteBasedOnCustomerKnownType policy, right-click Version 1.0 (not saved), and then click Add New Rule.</span></span> <span data-ttu-id="a58cf-164">SetUnknownCustomerEndpoint 規則の名前を付けます。</span><span class="sxs-lookup"><span data-stu-id="a58cf-164">Name the rule SetUnknownCustomerEndpoint.</span></span>  
  
2.  <span data-ttu-id="a58cf-165">ルール ウィンドウで、条件を右クリックし、追加論理 and。</span><span class="sxs-lookup"><span data-stu-id="a58cf-165">In the Rule window, right-click Conditions, and then click Add logical AND.</span></span>  
  
3.  <span data-ttu-id="a58cf-166">ルール] ウィンドウを右クリックし、[述語をポイントし、NotEqual 順にクリックします。</span><span class="sxs-lookup"><span data-stu-id="a58cf-166">In the Rule window, right-click AND, point to Predicates, and then click NotEqual.</span></span>  
  
4.  <span data-ttu-id="a58cf-167">ファクト エクスプ ローラーでは、XML スキーマ タブをクリックして、NAOrderDoc.xsd を展開し、OrderDoc を展開します。</span><span class="sxs-lookup"><span data-stu-id="a58cf-167">In Facts Explorer, click the XML Schemas tab, expand NAOrderDoc.xsd, and then expand OrderDoc.</span></span>  
  
5.  <span data-ttu-id="a58cf-168">ファクト エクスプ ローラーからの条件下で [引数 1] ノードに customerName 要素をドラッグします。</span><span class="sxs-lookup"><span data-stu-id="a58cf-168">From Facts Explorer, drag the customerName element to the argument1 node under Conditions.</span></span>  
  
6.  <span data-ttu-id="a58cf-169">[引数 2] のノードをクリックして、GlobalBankWest を入力します。</span><span class="sxs-lookup"><span data-stu-id="a58cf-169">Click the argument2 node, and then type GlobalBankWest.</span></span>  
  
7.  <span data-ttu-id="a58cf-170">ルール] ウィンドウを右クリックし、[述語をポイントし、NotEqual 順にクリックします。</span><span class="sxs-lookup"><span data-stu-id="a58cf-170">In the Rule window, right-click AND, point to Predicates, and then click NotEqual.</span></span>  
  
8.  <span data-ttu-id="a58cf-171">ファクト エクスプ ローラーからの条件下で [引数 1] ノードに customerName 要素をドラッグします。</span><span class="sxs-lookup"><span data-stu-id="a58cf-171">From Facts Explorer, drag the customerName element to the argument1 node under Conditions.</span></span>  
  
9. <span data-ttu-id="a58cf-172">[引数 2] のノードをクリックして、GlobalBankEast を入力します。</span><span class="sxs-lookup"><span data-stu-id="a58cf-172">Click the argument2 node, and then type GlobalBankEast.</span></span>  
  
10. <span data-ttu-id="a58cf-173">ファクト エクスプ ローラーで、[ボキャブラリ] タブをクリックして、ESB を展開します。EndPointInfo、バージョン 1.0 を順に展開します。</span><span class="sxs-lookup"><span data-stu-id="a58cf-173">In Facts Explorer, click the Vocabularies tab, expand ESB.EndPointInfo, and then expand Version 1.0.</span></span>  
  
11. <span data-ttu-id="a58cf-174">ファクト エクスプ ローラーからは、アクションに終点の送信トランスポート場所の設定の定義をドラッグします。</span><span class="sxs-lookup"><span data-stu-id="a58cf-174">From Facts Explorer, drag the Set End Point Outbound Transport Location definition to Actions.</span></span>  
  
12. <span data-ttu-id="a58cf-175">クリックして\<空の文字列\>、し C:\HowTos\Out\CustomerUnknown%MessageID%.xml を入力します。</span><span class="sxs-lookup"><span data-stu-id="a58cf-175">Click \<empty string\>, and then type C:\HowTos\Out\CustomerUnknown%MessageID%.xml.</span></span>  
  
13. <span data-ttu-id="a58cf-176">ファクト エクスプ ローラーからは、アクションに、設定の終了点送信トランスポートの種類の定義をドラッグします。</span><span class="sxs-lookup"><span data-stu-id="a58cf-176">From Facts Explorer, drag the Set End Point Outbound Transport Type definition to Actions.</span></span>  
  
14. <span data-ttu-id="a58cf-177">ファクト エクスプ ローラーでは、ESB を展開します。TransportTypes がバージョン 1.0 を展開し、アダプターのプロバイダー定義をドラッグ\<空の文字列\>します。</span><span class="sxs-lookup"><span data-stu-id="a58cf-177">In Facts Explorer, expand ESB.TransportTypes, expand Version 1.0, and then drag the Adaptor Providers definition to \<empty string\>.</span></span>  
  
15. <span data-ttu-id="a58cf-178">[操作] ウィンドウで、アダプター プロバイダーのボックスの一覧を展開し、ファイルをクリックします。</span><span class="sxs-lookup"><span data-stu-id="a58cf-178">In the Actions pane, expand the Adaptor Providers drop-down list, and then click FILE.</span></span>  
  
#### <a name="to-publish-and-deploy-the-policy"></a><span data-ttu-id="a58cf-179">発行して、ポリシーをデプロイするには</span><span class="sxs-lookup"><span data-stu-id="a58cf-179">To publish and deploy the policy</span></span>  
  
1.  <span data-ttu-id="a58cf-180">ポリシー エクスプ ローラーで [、 **RouteBasedOnCustomerKnownType**ポリシーを右クリック**バージョン 1.0 (未保存)**、] をクリックし、**発行**します。</span><span class="sxs-lookup"><span data-stu-id="a58cf-180">In Policy Explorer, under the **RouteBasedOnCustomerKnownType** policy, right click **Version 1.0 (not saved)**, and then click **Publish**.</span></span>  
  
2.  <span data-ttu-id="a58cf-181">ポリシー エクスプ ローラーで [、 **RouteBasedOnCustomerKnownType**ポリシーを右クリック**バージョン 1.0 - 公開済み**、] をクリックし、**デプロイ**。</span><span class="sxs-lookup"><span data-stu-id="a58cf-181">In Policy Explorer, under the **RouteBasedOnCustomerKnownType** policy, right click **Version 1.0 - Published**, and then click **Deploy**.</span></span>  
  
#### <a name="to-create-an-esb-itinerary-dsl-model"></a><span data-ttu-id="a58cf-182">ESB スケジュール オンランプ DSL モデルを作成するには</span><span class="sxs-lookup"><span data-stu-id="a58cf-182">To create an ESB itinerary DSL model</span></span>  
  
1.  <span data-ttu-id="a58cf-183">Visual Studio で、C:\HowTos\Patterns\Patterns.sln を開きます。</span><span class="sxs-lookup"><span data-stu-id="a58cf-183">In Visual Studio, open C:\HowTos\Patterns\Patterns.sln.</span></span>  
  
2.  <span data-ttu-id="a58cf-184">ソリューション エクスプ ローラーで右クリックし、 **ItineraryLibrary**プロジェクトをポイントして、**追加**、順にクリックします**新しい行程**します。</span><span class="sxs-lookup"><span data-stu-id="a58cf-184">In Solution Explorer, right-click the **ItineraryLibrary** project, point to **Add**, and then click **New Itinerary**.</span></span>  
  
3.  <span data-ttu-id="a58cf-185">**新しい項目の追加** ダイアログ ボックスで、**名前**ボックスに「 **CbrKnownType**、 をクリックし、**追加**。</span><span class="sxs-lookup"><span data-stu-id="a58cf-185">In the **Add New Item** dialog box, in the **Name** box, type **CbrKnownType**, and then click **Add**.</span></span>  
  
#### <a name="to-configure-the-properties-of-the-itinerary"></a><span data-ttu-id="a58cf-186">旅行プランのプロパティを構成するには</span><span class="sxs-lookup"><span data-stu-id="a58cf-186">To configure the properties of the itinerary</span></span>  
  
1.  <span data-ttu-id="a58cf-187">Visual Studio でのデザイン画面をクリックします。 **CbrKnownType.itinerary**します。</span><span class="sxs-lookup"><span data-stu-id="a58cf-187">In Visual Studio, click the design surface of **CbrKnownType.itinerary**.</span></span> <span data-ttu-id="a58cf-188">**CbrKnownType**プロパティ ウィンドウで、次のプロパティを構成します。</span><span class="sxs-lookup"><span data-stu-id="a58cf-188">In the **CbrKnownType** Properties window, configure the following properties:</span></span>  
  
    1.  <span data-ttu-id="a58cf-189">**モデル エクスポーター**ドロップダウン リストでは、をクリックして**XML 行程エクスポーター**します。</span><span class="sxs-lookup"><span data-stu-id="a58cf-189">In the **Model Exporter** drop-down list, click **XML Itinerary Exporter**.</span></span>  
  
    2.  <span data-ttu-id="a58cf-190">**エクステンダー設定**セクションで、次に、**旅行プラン XML ファイル**プロパティ、省略記号ボタン (…) をクリックします。</span><span class="sxs-lookup"><span data-stu-id="a58cf-190">In the **Extender Settings** section, next to the **Itinerary XML file** property, click the ellipsis button (...).</span></span>  
  
    3.  <span data-ttu-id="a58cf-191">**XML ファイルの**ダイアログ ボックスに「 **C:\HowTos\Itineraries\CbrKnownType**で、**ファイル名**ボックスをクリック**保存**します。</span><span class="sxs-lookup"><span data-stu-id="a58cf-191">In the **Select XML File** dialog box, type **C:\HowTos\Itineraries\CbrKnownType** in the **File name** box, and then click **Save**.</span></span>  
  
        > [!NOTE]
        >  <span data-ttu-id="a58cf-192">この手順では、旅行プランを XML としてローカル ファイルの場所にエクスポートすることができます。</span><span class="sxs-lookup"><span data-stu-id="a58cf-192">This step enables you to export the itinerary as XML to a local file location.</span></span> <span data-ttu-id="a58cf-193">行程データベースの代わりにスケジュールをローカル ファイルの場所にエクスポートして、ESB のテスト用クライアント アプリケーションを使用してスケジュールのテストが可能です。</span><span class="sxs-lookup"><span data-stu-id="a58cf-193">By exporting an itinerary to a local file location, instead of to the itinerary database, enables testing of the itinerary using the ESB Test Client application.</span></span> <span data-ttu-id="a58cf-194">この操作方法に関するトピックの後半には、このプロセスを完了します。</span><span class="sxs-lookup"><span data-stu-id="a58cf-194">You will complete this process later in this How-to topic.</span></span>  
  
#### <a name="to-define-the-structure-of-the-itinerary"></a><span data-ttu-id="a58cf-195">旅行プランの構造を定義するには</span><span class="sxs-lookup"><span data-stu-id="a58cf-195">To define the structure of the itinerary</span></span>  
  
1.  <span data-ttu-id="a58cf-196">ツールボックスからドラッグ、**入口**デザイン サーフェイスにモデル要素。</span><span class="sxs-lookup"><span data-stu-id="a58cf-196">From the Toolbox, drag an **On-Ramp** model element to the design surface.</span></span> <span data-ttu-id="a58cf-197">**OnRamp1**プロパティ ウィンドウで、次のプロパティを構成します。</span><span class="sxs-lookup"><span data-stu-id="a58cf-197">In the **OnRamp1** Properties window, configure the following properties:</span></span>  
  
    1.  <span data-ttu-id="a58cf-198">をクリックして、**名前**プロパティ、および入力**ReceiveNAOrder**します。</span><span class="sxs-lookup"><span data-stu-id="a58cf-198">Click the **Name** property, and then type **ReceiveNAOrder**.</span></span>  
  
    2.  <span data-ttu-id="a58cf-199">**エクステンダー**ドロップダウン リストでは、をクリックして**入口 ESB エクステンダー**します。</span><span class="sxs-lookup"><span data-stu-id="a58cf-199">In the **Extender** drop-down list, click **On-Ramp ESB Extender**.</span></span>  
  
    3.  <span data-ttu-id="a58cf-200">**BizTalk アプリケーション**ドロップダウン リストでは、をクリックして**Microsoft.Practices.ESB**します。</span><span class="sxs-lookup"><span data-stu-id="a58cf-200">In the **BizTalk Application** drop-down list, click **Microsoft.Practices.ESB**.</span></span>  
  
    4.  <span data-ttu-id="a58cf-201">**受信ポート**ドロップダウン リストでは、をクリックして**OnRamp.Itinerary**します。</span><span class="sxs-lookup"><span data-stu-id="a58cf-201">In the **Receive Port** drop-down list, click **OnRamp.Itinerary**.</span></span>  
  
2.  <span data-ttu-id="a58cf-202">ツールボックスからドラッグして、**傾斜オフ**の右側に配置し、デザイン画面に要素をモデル化し、 **ReceiveNAOrder**モデル要素。</span><span class="sxs-lookup"><span data-stu-id="a58cf-202">From the Toolbox, drag an **Off-Ramp** model element to the design surface, and then place it to the right of the **ReceiveNAOrder** model element.</span></span> <span data-ttu-id="a58cf-203">**OffRamp1**プロパティ ウィンドウで、次のプロパティを構成します。</span><span class="sxs-lookup"><span data-stu-id="a58cf-203">In the **OffRamp1** Properties window, configure the following properties:</span></span>  
  
    1.  <span data-ttu-id="a58cf-204">をクリックして、**名前**プロパティ、および入力**SendRegionalOrders**します。</span><span class="sxs-lookup"><span data-stu-id="a58cf-204">Click the **Name** property, and then type **SendRegionalOrders**.</span></span>  
  
    2.  <span data-ttu-id="a58cf-205">**エクステンダー**ドロップダウン リストでは、をクリックして**傾斜オフ ESB エクステンダー**します。</span><span class="sxs-lookup"><span data-stu-id="a58cf-205">In the **Extender** drop-down list, click **Off-Ramp ESB Extender**.</span></span>  
  
    3.  <span data-ttu-id="a58cf-206">**BizTalk アプリケーション**ドロップダウン リストでは、をクリックして**GlobalBank.ESB**します。</span><span class="sxs-lookup"><span data-stu-id="a58cf-206">In the **BizTalk Application** drop-down list, click **GlobalBank.ESB**.</span></span>  
  
    4.  <span data-ttu-id="a58cf-207">**送信ポート**ドロップダウン リストでは、をクリックして**DynamicResolutionOneWay**します。</span><span class="sxs-lookup"><span data-stu-id="a58cf-207">In the **Send Port** drop-down list, click **DynamicResolutionOneWay**.</span></span>  
  
3.  <span data-ttu-id="a58cf-208">ツールボックスからドラッグ、**スケジュール サービス**モデルのデザイン画面に要素との間に配置し、 **ReceiveNAOrder**モデル要素と**SendRegionalOrders**モデル要素。</span><span class="sxs-lookup"><span data-stu-id="a58cf-208">From the Toolbox, drag an **Itinerary Service** model element to the design surface, and then place it between the **ReceiveNAOrder** model element and the **SendRegionalOrders** model element.</span></span> <span data-ttu-id="a58cf-209">**ItineraryService1**プロパティ ウィンドウで、次のプロパティを構成します。</span><span class="sxs-lookup"><span data-stu-id="a58cf-209">In the **ItineraryService1** Properties window, configure the following properties:</span></span>  
  
    1.  <span data-ttu-id="a58cf-210">をクリックして、**名前**プロパティ、および入力**SendPortFilter**します。</span><span class="sxs-lookup"><span data-stu-id="a58cf-210">Click the **Name** property, and then type **SendPortFilter**.</span></span>  
  
    2.  <span data-ttu-id="a58cf-211">**行程サービス エクステンダー**ドロップダウン リストでは、をクリックして**傾斜オフ エクステンダー**。</span><span class="sxs-lookup"><span data-stu-id="a58cf-211">In the **Itinerary Service Extender** drop-down list, click **Off-Ramp Extender**.</span></span>  
  
    3.  <span data-ttu-id="a58cf-212">**傾斜オフ**ドロップダウン リストで、展開**SendRegionalOrders**、順にクリックします**送信ハンドラー**します。</span><span class="sxs-lookup"><span data-stu-id="a58cf-212">In the **Off-Ramp** drop-down list, expand **SendRegionalOrders**, and then click **Send Handlers**.</span></span>  
  
4.  <span data-ttu-id="a58cf-213">右クリックし、**リゾルバー**のコレクション、 **SendPortFilter**モデル要素をクリックして**新しいリゾルバーを追加**します。</span><span class="sxs-lookup"><span data-stu-id="a58cf-213">Right-click the **Resolver** collection of the **SendPortFilter** model element, and then click **Add new Resolver**.</span></span> <span data-ttu-id="a58cf-214">**Resolver1**プロパティ ウィンドウで、次のプロパティを構成します。</span><span class="sxs-lookup"><span data-stu-id="a58cf-214">In the **Resolver1** Properties window, configure the following properties:</span></span>  
  
    1.  <span data-ttu-id="a58cf-215">をクリックして、**名前**プロパティ、および入力**RouteRegionalOrders**します。</span><span class="sxs-lookup"><span data-stu-id="a58cf-215">Click the **Name** property, and then type **RouteRegionalOrders**.</span></span>  
  
    2.  <span data-ttu-id="a58cf-216">**トランスポート名**ドロップダウン リストでは、をクリックして**BRE**します。</span><span class="sxs-lookup"><span data-stu-id="a58cf-216">In the **Transport Name** drop-down list, click **BRE**.</span></span>  
  
    3.  <span data-ttu-id="a58cf-217">**リゾルバーの実装**ドロップダウン リストでは、をクリックして**Bre 競合回避モジュールの拡張機能**します。</span><span class="sxs-lookup"><span data-stu-id="a58cf-217">In the **Resolver Implementation** drop-down list, click **Bre Resolver Extension**.</span></span>  
  
    4.  <span data-ttu-id="a58cf-218">**ポリシー**ドロップダウン リストでは、をクリックして**RouteBasedOnCustomerKnownType**します。</span><span class="sxs-lookup"><span data-stu-id="a58cf-218">In the **Policy** drop-down list, click **RouteBasedOnCustomerKnownType**.</span></span>  
  
    5.  <span data-ttu-id="a58cf-219">**メッセージ形式を認識**ドロップダウン リストをクリックして**True**します。</span><span class="sxs-lookup"><span data-stu-id="a58cf-219">In the **Recognize Message Format** drop-down list click **True**.</span></span>  
  
    6.  <span data-ttu-id="a58cf-220">**UseMsg**ドロップダウン リストでは、をクリックして**True**します。</span><span class="sxs-lookup"><span data-stu-id="a58cf-220">In the **UseMsg** drop-down list, click **True**.</span></span>  
  
        > [!NOTE]
        >  <span data-ttu-id="a58cf-221">オーケストレーションから BRE 競合回避モジュールの拡張機能を使用する場合、 **recognizeMessageFormat**にプロパティを設定する必要があります**False**します。</span><span class="sxs-lookup"><span data-stu-id="a58cf-221">If you use the BRE Resolver Extension from orchestration, the **recognizeMessageFormat** property must be set to **False**.</span></span>  
  
5.  <span data-ttu-id="a58cf-222">ツールボックス、**コネクタ**します。</span><span class="sxs-lookup"><span data-stu-id="a58cf-222">In the Toolbox, click **Connector**.</span></span> <span data-ttu-id="a58cf-223">接続をドラッグして、 **ReceiveNAOrder**モデル要素に、 **SendPortFilter**モデル要素。</span><span class="sxs-lookup"><span data-stu-id="a58cf-223">Drag a connection from the **ReceiveNAOrder** model element to the **SendPortFilter** model element.</span></span>  
  
6.  <span data-ttu-id="a58cf-224">ツールボックス、**コネクタ**します。</span><span class="sxs-lookup"><span data-stu-id="a58cf-224">In the Toolbox, click **Connector**.</span></span> <span data-ttu-id="a58cf-225">接続をドラッグして、 **SendPortFilter**モデル要素に、 **SendRegionalOrders**モデル要素。</span><span class="sxs-lookup"><span data-stu-id="a58cf-225">Drag a connection from the **SendPortFilter** model element to the **SendRegionalOrders** model element.</span></span>  
  
#### <a name="to-export-the-model-for-use-with-the-itinerary-test-client"></a><span data-ttu-id="a58cf-226">旅行プランのテスト クライアントで使用するモデルをエクスポートするには</span><span class="sxs-lookup"><span data-stu-id="a58cf-226">To export the model for use with the Itinerary Test Client</span></span>  
  
1.  <span data-ttu-id="a58cf-227">Visual Studio でのデザイン画面を右クリックし、 **CbrKnownType**旅行プランをクリックして**モデルのエクスポート**します。</span><span class="sxs-lookup"><span data-stu-id="a58cf-227">In Visual Studio, right-click the design surface of the **CbrKnownType** itinerary, and then click **Export Model**.</span></span>  
  
    > [!NOTE]
    >  <span data-ttu-id="a58cf-228">旅行プランの XML バージョンは、Visual Studio で開きます。</span><span class="sxs-lookup"><span data-stu-id="a58cf-228">The XML version of the itinerary opens in Visual Studio.</span></span>  
  
2.  <span data-ttu-id="a58cf-229">すべてのプロジェクト成果物を保存します。</span><span class="sxs-lookup"><span data-stu-id="a58cf-229">Save all project artifacts.</span></span>  
  
3.  <span data-ttu-id="a58cf-230">Windows エクスプ ローラーでは、C:\HowTos\Itineraries を参照し、旅行プラン XML (CbrKnownType.xml) の作成に注意してください。</span><span class="sxs-lookup"><span data-stu-id="a58cf-230">In Windows Explorer, browse to C:\HowTos\Itineraries and notice the creation of your itinerary XML (CbrKnownType.xml).</span></span>  
  
#### <a name="to-test-the-itinerary-and-business-rules"></a><span data-ttu-id="a58cf-231">スケジュール オンランプとビジネス ルールをテストするには</span><span class="sxs-lookup"><span data-stu-id="a58cf-231">To test the itinerary and business rules</span></span>  
  
1.  <span data-ttu-id="a58cf-232">中に作成されたショートカットを使用してスケジュールのテスト用クライアントのサンプル アプリケーションを開く、[開発活動の前提条件](../esb-toolkit/prerequisites-for-the-development-activities.md)(C:\HowTos\ESB します。Itinerary.Test.exe - ショートカット)。</span><span class="sxs-lookup"><span data-stu-id="a58cf-232">Open the Itinerary Test Client sample application using the shortcut created during the [Prerequisites for the Development Activities](../esb-toolkit/prerequisites-for-the-development-activities.md) (C:\HowTos\ESB.Itinerary.Test.exe - Shortcut).</span></span>  
  
2.  <span data-ttu-id="a58cf-233">行程テスト クライアントでオフ、 **WCF サービスを使用して**チェック ボックスをオンにし**ロード行程**。</span><span class="sxs-lookup"><span data-stu-id="a58cf-233">In the Itinerary Test Client, clear the **Use WCF Service** check box, and then click **Load Itinerary**.</span></span>  
  
3.  <span data-ttu-id="a58cf-234">**行程ファイルを開く** ダイアログ ボックスで、C:\HowTos\Itineraries を参照します。</span><span class="sxs-lookup"><span data-stu-id="a58cf-234">In the **Open Itinerary File** dialog box, browse to C:\HowTos\Itineraries.</span></span> <span data-ttu-id="a58cf-235">選択**CbrKnownType.xml**、順にクリックします**オープン**旅行プランを読み込めません。</span><span class="sxs-lookup"><span data-stu-id="a58cf-235">Select **CbrKnownType.xml**, and then click **Open** to load the itinerary.</span></span>  
  
4.  <span data-ttu-id="a58cf-236">をクリックして**OK**をオフに、**旅行プランは正常に読み込まれる**メッセージ。</span><span class="sxs-lookup"><span data-stu-id="a58cf-236">Click **OK** to clear the **Itinerary Loaded Successfully** message.</span></span>  
  
5.  <span data-ttu-id="a58cf-237">旅行プランのテスト クライアントで、横にある省略記号ボタン (…) をクリックします。、**ロード メッセージ**ボックス。</span><span class="sxs-lookup"><span data-stu-id="a58cf-237">In the Itinerary Test Client, click the ellipsis button (...) next to the **Load Message** box.</span></span>  
  
6.  <span data-ttu-id="a58cf-238">**を読み込む XML ドキュメントの選択** ダイアログ ボックスで、C:\HowTos を参照します。</span><span class="sxs-lookup"><span data-stu-id="a58cf-238">In the **Select XML Document to load** dialog box, browse to C:\HowTos.</span></span> <span data-ttu-id="a58cf-239">選択**West.xml**、順にクリックします**オープン**テスト メッセージを読み込めません。</span><span class="sxs-lookup"><span data-stu-id="a58cf-239">Select **West.xml**, and then click **Open** to load the test message.</span></span>  
  
7.  <span data-ttu-id="a58cf-240">をクリックして、**要求を提出**ボタンをクリックします。</span><span class="sxs-lookup"><span data-stu-id="a58cf-240">Click the **Submit Request** button.</span></span> <span data-ttu-id="a58cf-241">テストが完了したら、クリックして**OK**表示される確認メッセージを無視します。</span><span class="sxs-lookup"><span data-stu-id="a58cf-241">When the test completes, click **OK** to dismiss the confirmation that appears.</span></span>  
  
8.  <span data-ttu-id="a58cf-242">Windows エクスプ ローラーでは、C:\HowTos\Out を参照します。West%MessageID%.xml メッセージがディレクトリに書き込まれたことを確認します。</span><span class="sxs-lookup"><span data-stu-id="a58cf-242">In Windows Explorer, browse to C:\HowTos\Out. Verify that the West%MessageID%.xml message has been written to the directory.</span></span>  
  
9. <span data-ttu-id="a58cf-243">East.xml メッセージを使用して、テスト プロセスを繰り返します。</span><span class="sxs-lookup"><span data-stu-id="a58cf-243">Repeat the test process using the East.xml message.</span></span>  
  
10. <span data-ttu-id="a58cf-244">Windows エクスプ ローラーでは、C:\HowTos\Out を参照します。East%MessageID%.xml メッセージがディレクトリに書き込まれたことを確認します。</span><span class="sxs-lookup"><span data-stu-id="a58cf-244">In Windows Explorer, browse to C:\HowTos\Out. Verify that the East%MessageID%.xml message has been written to the directory.</span></span>  
  
11. <span data-ttu-id="a58cf-245">NAOrderDoc.xml メッセージを使用して、テスト プロセスを繰り返します。</span><span class="sxs-lookup"><span data-stu-id="a58cf-245">Repeat the test process using the NAOrderDoc.xml message.</span></span>  
  
12. <span data-ttu-id="a58cf-246">Windows エクスプ ローラーでは、C:\HowTos\Out を参照します。CustomerUnknown%MessageID%.xml メッセージがディレクトリに書き込まれたことを確認します。</span><span class="sxs-lookup"><span data-stu-id="a58cf-246">In Windows Explorer, browse to C:\HowTos\Out. Verify that the CustomerUnknown%MessageID%.xml message has been written to the directory.</span></span>  
  
## <a name="additional-resources"></a><span data-ttu-id="a58cf-247">その他のリソース</span><span class="sxs-lookup"><span data-stu-id="a58cf-247">Additional Resources</span></span>  
 <span data-ttu-id="a58cf-248">詳細については、次の関連項目を参照してください。</span><span class="sxs-lookup"><span data-stu-id="a58cf-248">For more information, see the following related topics:</span></span>  
  
-   [<span data-ttu-id="a58cf-249">方法: ビジネス ルール ポリシーを使用するスケジュールを選択します。</span><span class="sxs-lookup"><span data-stu-id="a58cf-249">How to: Select an Itinerary Using a Business Rules Policy</span></span>](../esb-toolkit/how-to-select-an-itinerary-using-a-business-rules-policy.md)  
  
-   [<span data-ttu-id="a58cf-250">方法: ビジネス ルール ポリシーを使用してメッセージのコンテキストに基づいてメッセージを動的にルーティングします。</span><span class="sxs-lookup"><span data-stu-id="a58cf-250">How to: Dynamically Route a Message Based on Message Context Using a Business Rules Policy</span></span>](../esb-toolkit/dynamically-route-messages-based-on-message-context-using-business-rules-policy.md)  
  
-   [<span data-ttu-id="a58cf-251">開発アクティビティ</span><span class="sxs-lookup"><span data-stu-id="a58cf-251">Development Activities</span></span>](../esb-toolkit/development-activities.md)  
  
-   [<span data-ttu-id="a58cf-252">メッセージ ルーティング パターン</span><span class="sxs-lookup"><span data-stu-id="a58cf-252">Message Routing Patterns</span></span>](../esb-toolkit/message-routing-patterns.md)