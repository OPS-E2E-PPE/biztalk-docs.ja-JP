---
title: "方法: 既知のメッセージの種類のポリシーをルール実装のビジネスを使用してコンテンツ ベース ルーティング |Microsoft ドキュメント"
ms.custom: 
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: 
ms.suite: 
ms.tgt_pltfrm: 
ms.topic: article
ms.assetid: 44451c85-929a-4d13-b0dd-53ea600d0859
caps.latest.revision: "4"
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: 878a6e180aaf7e5f37c5cf98ca0a67790917859a
ms.sourcegitcommit: 3fc338e52d5dbca2c3ea1685a2faafc7582fe23a
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 12/01/2017
---
# <a name="how-to-implement-content-based-routing-using-a-business-rules-policy-for-a-known-message-type"></a><span data-ttu-id="bc424-102">方法: 既知のメッセージの種類のポリシーをルール実装のビジネスを使用してコンテンツ ベース ルーティング</span><span class="sxs-lookup"><span data-stu-id="bc424-102">How to: Implement Content-Based Routing Using a Business Rules Policy for a Known Message Type</span></span>
## <a name="goal"></a><span data-ttu-id="bc424-103">[目標]</span><span class="sxs-lookup"><span data-stu-id="bc424-103">Goal</span></span>  
 <span data-ttu-id="bc424-104">このセクションでは、動的に基づいたメッセージをルーティングする旅程を作成する方法を示します (Microsoft BizTalk Server 構成データベースに展開されたスキーマ) の既知のメッセージ型のコンテンツに対するビジネス規則を使用してポリシー。</span><span class="sxs-lookup"><span data-stu-id="bc424-104">This section demonstrates how to create an itinerary that dynamically routes a message, based on the content of a known message type (schema deployed to the Microsoft BizTalk Server Configuration database), using a business rules policy.</span></span>  
  
 <span data-ttu-id="bc424-105">このトピックでは、次の手順を行います。</span><span class="sxs-lookup"><span data-stu-id="bc424-105">In this How-to topic, you will complete the following steps:</span></span>  
  
-   <span data-ttu-id="bc424-106">コンテンツに基づいてメッセージのルーティングに使用されるビジネス ルール ポリシーを作成します。</span><span class="sxs-lookup"><span data-stu-id="bc424-106">Create a business rules policy that will be used to route a message based on content.</span></span>  
  
-   <span data-ttu-id="bc424-107">動的にメッセージをルーティングする BRE リゾルバーを itinerary 回覧を作成します。</span><span class="sxs-lookup"><span data-stu-id="bc424-107">Create an itinerary routing slip with a BRE resolver to dynamically route a message.</span></span>  
  
-   <span data-ttu-id="bc424-108">行程テスト用クライアントのサンプル アプリケーションを使用して旅程をテストします。</span><span class="sxs-lookup"><span data-stu-id="bc424-108">Test the itinerary using the Itinerary Test Client sample application.</span></span>  
  
## <a name="prerequisites"></a><span data-ttu-id="bc424-109">前提条件</span><span class="sxs-lookup"><span data-stu-id="bc424-109">Prerequisites</span></span>  
 <span data-ttu-id="bc424-110">この操作方法に関するトピックの手順の完了が必要、[開発活動の前提条件](../esb-toolkit/prerequisites-for-the-development-activities.md)です。</span><span class="sxs-lookup"><span data-stu-id="bc424-110">The procedures in this How-to topic require the completion of the [Prerequisites for the Development Activities](../esb-toolkit/prerequisites-for-the-development-activities.md).</span></span>  
  
## <a name="before-you-begin"></a><span data-ttu-id="bc424-111">はじめに</span><span class="sxs-lookup"><span data-stu-id="bc424-111">Before You Begin</span></span>  
 <span data-ttu-id="bc424-112">このトピックの「操作方法に関する手順を実行する前に、次のタスクを実行します。</span><span class="sxs-lookup"><span data-stu-id="bc424-112">Complete the following tasks before you perform the steps later in this How-to topic:</span></span>  
  
-   <span data-ttu-id="bc424-113">GlobalBank 西部テスト メッセージを作成します。</span><span class="sxs-lookup"><span data-stu-id="bc424-113">Create the GlobalBank West test message.</span></span>  
  
-   <span data-ttu-id="bc424-114">GlobalBank 東部テスト メッセージを作成します。</span><span class="sxs-lookup"><span data-stu-id="bc424-114">Create the GlobalBank East test message.</span></span>  
  
 <span data-ttu-id="bc424-115">次の手順では、これらの各を行う方法について説明します。</span><span class="sxs-lookup"><span data-stu-id="bc424-115">The following procedures describe how to do each of these.</span></span>  
  
#### <a name="to-create-the-globalbank-west-test-message"></a><span data-ttu-id="bc424-116">GlobalBank 西部テスト メッセージを作成するには</span><span class="sxs-lookup"><span data-stu-id="bc424-116">To create the GlobalBank West test message</span></span>  
  
1.  <span data-ttu-id="bc424-117">Windows エクスプローラで、C:\HowTos を参照します。</span><span class="sxs-lookup"><span data-stu-id="bc424-117">In Windows Explorer, browse to C:\HowTos.</span></span>  
  
2.  <span data-ttu-id="bc424-118">NAOrderDoc.xml のコピーを作成し、コピー West.xml を名前します。</span><span class="sxs-lookup"><span data-stu-id="bc424-118">Create a copy of NAOrderDoc.xml, and then name the copy West.xml.</span></span>  
  
3.  <span data-ttu-id="bc424-119">メモ帳で、West.xml を開きの値を変更、 **customerName**要素**GlobalBankWest**です。</span><span class="sxs-lookup"><span data-stu-id="bc424-119">In Notepad, open West.xml, and then change the value of the **customerName** element to **GlobalBankWest**.</span></span>  
  
4.  <span data-ttu-id="bc424-120">Utf-8 として West.xml を保存し、メモ帳を閉じます。</span><span class="sxs-lookup"><span data-stu-id="bc424-120">Save West.xml as UTF-8, and then close Notepad.</span></span>  
  
#### <a name="to-create-the-globalbank-east-test-message"></a><span data-ttu-id="bc424-121">GlobalBank 東部テスト メッセージを作成するには</span><span class="sxs-lookup"><span data-stu-id="bc424-121">To create the GlobalBank East test message</span></span>  
  
1.  <span data-ttu-id="bc424-122">Windows エクスプローラで、C:\HowTos を参照します。</span><span class="sxs-lookup"><span data-stu-id="bc424-122">In Windows Explorer, browse to C:\HowTos.</span></span>  
  
2.  <span data-ttu-id="bc424-123">NAOrderDoc.xml のコピーを作成し、コピー East.xml を名前します。</span><span class="sxs-lookup"><span data-stu-id="bc424-123">Create a copy of NAOrderDoc.xml, and then name the copy East.xml.</span></span>  
  
3.  <span data-ttu-id="bc424-124">メモ帳で、East.xml を開きの値を変更、 **customerName**要素**GlobalBankEast**です。</span><span class="sxs-lookup"><span data-stu-id="bc424-124">In Notepad, open East.xml, and then change the value of the **customerName** element to **GlobalBankEast**.</span></span>  
  
4.  <span data-ttu-id="bc424-125">Utf-8 として East.xml を保存し、メモ帳を閉じます。</span><span class="sxs-lookup"><span data-stu-id="bc424-125">Save East.xml as UTF-8, and then close Notepad.</span></span>  
  
## <a name="steps"></a><span data-ttu-id="bc424-126">手順</span><span class="sxs-lookup"><span data-stu-id="bc424-126">Steps</span></span>  
  
#### <a name="to-create-a-bre-policy-to-route-using-custom-message-properties"></a><span data-ttu-id="bc424-127">カスタム メッセージ プロパティを使用してルーティングする BRE ポリシーを作成するには</span><span class="sxs-lookup"><span data-stu-id="bc424-127">To create a BRE policy to route using custom message properties</span></span>  
 <span data-ttu-id="bc424-128">このルールは動的にメッセージをルーティングするのにために使用するエンドポイントを設定するのに顧客の名前を使用します。</span><span class="sxs-lookup"><span data-stu-id="bc424-128">This rule will use the customer's name to dynamically set the endpoint used to route the message.</span></span>  
  
1.  <span data-ttu-id="bc424-129">をクリックして**開始**タスク バーで、をポイント**すべてのプログラム**、 をポイント**BizTalk Server**、順にクリック**ビジネス ルール作成ツール**です。</span><span class="sxs-lookup"><span data-stu-id="bc424-129">Click **Start** on the taskbar, point to **All Programs**, point to **BizTalk Server**, and then click **Business Rule Composer**.</span></span>  
  
2.  <span data-ttu-id="bc424-130">ポリシー エクスプ ローラーで右クリック**ポリシー**、クリックして**新しいポリシーの追加**です。</span><span class="sxs-lookup"><span data-stu-id="bc424-130">In Policy Explorer, right-click **Policies**, and then click **Add New Policy**.</span></span> <span data-ttu-id="bc424-131">ポリシーに名前**RouteBasedOnCustomerKnownType**です。</span><span class="sxs-lookup"><span data-stu-id="bc424-131">Name the policy **RouteBasedOnCustomerKnownType**.</span></span>  
  
#### <a name="to-add-a-routing-rule-for-customer-globalbank-west"></a><span data-ttu-id="bc424-132">顧客 GlobalBank 西部のルーティング規則を追加するには</span><span class="sxs-lookup"><span data-stu-id="bc424-132">To add a routing rule for customer GlobalBank West</span></span>  
  
1.  <span data-ttu-id="bc424-133">**RouteBasedOnCustomerKnownType**ポリシーを右クリックして**バージョン 1.0 (未保存)**、順にクリック**新しいルールの追加**です。</span><span class="sxs-lookup"><span data-stu-id="bc424-133">In the **RouteBasedOnCustomerKnownType** policy, right-click **Version 1.0 (not saved)**, and then click **Add New Rule**.</span></span> <span data-ttu-id="bc424-134">ルールの名前として**SetWestEndpoint**です。</span><span class="sxs-lookup"><span data-stu-id="bc424-134">Name the rule **SetWestEndpoint**.</span></span>  
  
2.  <span data-ttu-id="bc424-135">ファクト エクスプ ローラーで、をクリックして、 **XML スキーマ** タブを右クリックして**スキーマ**、クリックして**参照**です。</span><span class="sxs-lookup"><span data-stu-id="bc424-135">In Facts Explorer, click the **XML Schemas** tab, right-click **Schemas**, and then click **Browse**.</span></span>  
  
3.  <span data-ttu-id="bc424-136">**スキーマ ファイル** ダイアログ ボックスで、C:\Projects\Microsoft.Practices.ESB\Source\Samples\DynamicResolution\Source\ESB を参照します。DynamicResolution.Schemas、select **NAOrderDoc.xsd**、クリックして**開く**です。</span><span class="sxs-lookup"><span data-stu-id="bc424-136">In the **Schema Files** dialog box, browse to C:\Projects\Microsoft.Practices.ESB\Source\Samples\DynamicResolution\Source\ESB.DynamicResolution.Schemas, select **NAOrderDoc.xsd**, and then click **Open**.</span></span>  
  
    > [!NOTE]
    >  <span data-ttu-id="bc424-137">これは、テストに使用する左右のメッセージを作成するために使用された NAOrderDoc.xml メッセージを定義するスキーマです。</span><span class="sxs-lookup"><span data-stu-id="bc424-137">This is the schema that defines the NAOrderDoc.xml message, which was used to create the West and East messages you will use for testing.</span></span>  
  
4.  <span data-ttu-id="bc424-138">ファクト エクスプ ローラーでクリックして**NAOrderDoc.xsd**、プロパティ ペインをクリックし、**ドキュメントの種類**プロパティ、および入力**GlobalBank.ESB.DynamicResolution.Schemas.NAOrderDoc**.</span><span class="sxs-lookup"><span data-stu-id="bc424-138">In Facts Explorer, click **NAOrderDoc.xsd**, and then in the Properties pane, click the **Document Type** property, and then type **GlobalBank.ESB.DynamicResolution.Schemas.NAOrderDoc**.</span></span>  
  
    > [!NOTE]
    >  <span data-ttu-id="bc424-139">これは、スキーマの完全修飾名です。</span><span class="sxs-lookup"><span data-stu-id="bc424-139">This is the fully qualified name of the schema.</span></span>  
  
5.  <span data-ttu-id="bc424-140">ファクト エクスプ ローラーで、 **NAOrderDoc.xsd**の順に展開および**OrderDoc**です。</span><span class="sxs-lookup"><span data-stu-id="bc424-140">In Facts Explorer, expand **NAOrderDoc.xsd**, and then expand **OrderDoc**.</span></span>  
  
6.  <span data-ttu-id="bc424-141">ルール ウィンドウで、右クリック**条件**、 をポイント**述語**、順にクリック**等しい**です。</span><span class="sxs-lookup"><span data-stu-id="bc424-141">In the Rule window, right-click **Conditions**, point to **Predicates**, and then click **Equal**.</span></span>  
  
7.  <span data-ttu-id="bc424-142">ファクト エクスプ ローラーからドラッグして、 **customerName**要素を**argument1**ノードの下**条件**です。</span><span class="sxs-lookup"><span data-stu-id="bc424-142">From Facts Explorer, drag the **customerName** element to the **argument1** node under **Conditions**.</span></span>  
  
8.  <span data-ttu-id="bc424-143">をクリックして、 **argument2**ノード、および入力**GlobalBankWest**です。</span><span class="sxs-lookup"><span data-stu-id="bc424-143">Click the **argument2** node, and then type **GlobalBankWest**.</span></span>  
  
9. <span data-ttu-id="bc424-144">ファクト エクスプ ローラーで、をクリックして、**ボキャブラリ** タブで、展開**ESB です。EndPointInfo**の順に展開および**バージョン 1.0**です。</span><span class="sxs-lookup"><span data-stu-id="bc424-144">In Facts Explorer, click the **Vocabularies** tab, expand **ESB.EndPointInfo**, and then expand **Version 1.0**.</span></span>  
  
    > [!NOTE]
    >  <span data-ttu-id="bc424-145">[!INCLUDE[esbToolkit](../includes/esbtoolkit-md.md)] ESB の使用規則を作成するために使用できるいくつかのボキャブラリが含まれています。</span><span class="sxs-lookup"><span data-stu-id="bc424-145">The [!INCLUDE[esbToolkit](../includes/esbtoolkit-md.md)] includes several vocabularies that can be used for creating rules for use in the ESB.</span></span> <span data-ttu-id="bc424-146">これらのいくつかは、交換する必要があります。 または独自のボキャブラリで補完されました。</span><span class="sxs-lookup"><span data-stu-id="bc424-146">Some of these should be replaced or augmented with your own vocabularies.</span></span> <span data-ttu-id="bc424-147">たとえば、 **DynamicRunTimeMaptypes**で用意されているマップの定義を持つ、 **GlobalBank**サンプルです。</span><span class="sxs-lookup"><span data-stu-id="bc424-147">For example, the **DynamicRunTimeMaptypes** has definitions for the maps provided in the **GlobalBank** samples.</span></span>  
  
10. <span data-ttu-id="bc424-148">ファクト エクスプ ローラーからドラッグして、**終点送信トランスポート場所の設定**の定義を**アクション**です。</span><span class="sxs-lookup"><span data-stu-id="bc424-148">From Facts Explorer, drag the **Set End Point Outbound Transport Location** definition to **Actions**.</span></span>  
  
11. <span data-ttu-id="bc424-149">をクリックして**\<空の文字列\>**し入力**C:\HowTos\Out\West%MessageID%.xml**です。</span><span class="sxs-lookup"><span data-stu-id="bc424-149">Click **\<empty string\>** and then type **C:\HowTos\Out\West%MessageID%.xml**.</span></span>  
  
12. <span data-ttu-id="bc424-150">ファクト エクスプ ローラーからドラッグして、**設定の終了点送信トランスポートの種類**定義**アクション**です。</span><span class="sxs-lookup"><span data-stu-id="bc424-150">From Facts Explorer, drag the **Set End Point Outbound Transport Type** definition to **Actions**.</span></span>  
  
13. <span data-ttu-id="bc424-151">ファクト エクスプ ローラーで、 **ESB です。TransportTypes**、展開**バージョン 1.0**、し、ドラッグ、**アダプター プロバイダー**定義**\<空の文字列\>**.</span><span class="sxs-lookup"><span data-stu-id="bc424-151">In Facts Explorer, expand **ESB.TransportTypes**, expand **Version 1.0**, and then drag the **Adaptor Providers** definition to **\<empty string\>**.</span></span>  
  
14. <span data-ttu-id="bc424-152">**アクション** ウィンドウで、展開、**アダプター プロバイダー**クリックしてドロップダウン リスト、**ファイル**です。</span><span class="sxs-lookup"><span data-stu-id="bc424-152">In the **Actions** pane, expand the **Adaptor Providers** drop-down list, and then click **FILE**.</span></span>  
  
#### <a name="to-add-a-routing-rule-for-customer-globalbank-east"></a><span data-ttu-id="bc424-153">GlobalBank 東部の顧客のルーティング規則を追加するには</span><span class="sxs-lookup"><span data-stu-id="bc424-153">To add a routing rule for customer GlobalBank East</span></span>  
  
1.  <span data-ttu-id="bc424-154">ポリシー エクスプ ローラーで右クリックし、 **SetWestEndpoint**ルールは、クリックして**コピー**です。</span><span class="sxs-lookup"><span data-stu-id="bc424-154">In Policy Explorer, right-click the **SetWestEndpoint** rule, and then click **Copy**.</span></span>  
  
2.  <span data-ttu-id="bc424-155">右クリック**バージョン 1.0 (未保存)**、クリックして**貼り付け**です。</span><span class="sxs-lookup"><span data-stu-id="bc424-155">Right-click **Version 1.0 (not saved)**, and then click **Paste**.</span></span>  
  
3.  <span data-ttu-id="bc424-156">**新しいルールの名前** ダイアログ ボックスで、「 **SetEastEndpoint**、順にクリック**OK**です。</span><span class="sxs-lookup"><span data-stu-id="bc424-156">In the **New Rule Name** dialog box, type **SetEastEndpoint**, and then click **OK**.</span></span>  
  
4.  <span data-ttu-id="bc424-157">ポリシー エクスプ ローラーで、をクリックして、 **SetEastEndpoint**ルール。</span><span class="sxs-lookup"><span data-stu-id="bc424-157">In Policy Explorer, click the **SetEastEndpoint** rule.</span></span>  
  
5.  <span data-ttu-id="bc424-158">**条件**セクションを右クリックして**GlobalBankWest**、クリックして**引数の再設定**です。</span><span class="sxs-lookup"><span data-stu-id="bc424-158">In the **Conditions** section, right-click **GlobalBankWest**, and then click **Reset argument**.</span></span>  
  
6.  <span data-ttu-id="bc424-159">をクリックして**argument2**、し、入力**GlobalBankEast**です。</span><span class="sxs-lookup"><span data-stu-id="bc424-159">Click **argument2**, and then type **GlobalBankEast**.</span></span>  
  
7.  <span data-ttu-id="bc424-160">**アクション**セクションを右クリックして**C:\HowTos\Out\West%MessageID%.xml**、クリックして**引数の再設定**です。</span><span class="sxs-lookup"><span data-stu-id="bc424-160">In the **Actions** section, right-click **C:\HowTos\Out\West%MessageID%.xml**, and then click **Reset argument**.</span></span>  
  
8.  <span data-ttu-id="bc424-161">をクリックして**\<空の文字列\>**、し、入力**C:\HowTos\Out\East%MessageID%.xml**です。</span><span class="sxs-lookup"><span data-stu-id="bc424-161">Click **\<empty string\>**, and then type **C:\HowTos\Out\East%MessageID%.xml**.</span></span>  
  
#### <a name="to-add-a-routing-rule-for-unknown-customers"></a><span data-ttu-id="bc424-162">不明な顧客のルーティング規則を追加するには</span><span class="sxs-lookup"><span data-stu-id="bc424-162">To add a routing rule for unknown customers</span></span>  
  
1.  <span data-ttu-id="bc424-163">RouteBasedOnCustomerKnownType ポリシーでは、バージョン 1.0 (未保存) を右クリックし、[新しい規則の追加] をクリックします。</span><span class="sxs-lookup"><span data-stu-id="bc424-163">In the RouteBasedOnCustomerKnownType policy, right-click Version 1.0 (not saved), and then click Add New Rule.</span></span> <span data-ttu-id="bc424-164">SetUnknownCustomerEndpoint ルールの名前を付けます。</span><span class="sxs-lookup"><span data-stu-id="bc424-164">Name the rule SetUnknownCustomerEndpoint.</span></span>  
  
2.  <span data-ttu-id="bc424-165">ルール ウィンドウで、条件を右クリックし、追加 をクリックして論理 and。</span><span class="sxs-lookup"><span data-stu-id="bc424-165">In the Rule window, right-click Conditions, and then click Add logical AND.</span></span>  
  
3.  <span data-ttu-id="bc424-166">ルール ウィンドウを右クリックし、述語をポイントし、NotEqual をクリックします。</span><span class="sxs-lookup"><span data-stu-id="bc424-166">In the Rule window, right-click AND, point to Predicates, and then click NotEqual.</span></span>  
  
4.  <span data-ttu-id="bc424-167">ファクト エクスプ ローラーで、XML スキーマ] タブをクリックして、[NAOrderDoc.xsd を展開し、OrderDoc を展開します。</span><span class="sxs-lookup"><span data-stu-id="bc424-167">In Facts Explorer, click the XML Schemas tab, expand NAOrderDoc.xsd, and then expand OrderDoc.</span></span>  
  
5.  <span data-ttu-id="bc424-168">ファクト エクスプ ローラーからの条件下で [引数 1] ノードに customerName 要素をドラッグします。</span><span class="sxs-lookup"><span data-stu-id="bc424-168">From Facts Explorer, drag the customerName element to the argument1 node under Conditions.</span></span>  
  
6.  <span data-ttu-id="bc424-169">[引数 2] ノードをクリックし、GlobalBankWest を入力します。</span><span class="sxs-lookup"><span data-stu-id="bc424-169">Click the argument2 node, and then type GlobalBankWest.</span></span>  
  
7.  <span data-ttu-id="bc424-170">ルール ウィンドウを右クリックし、述語をポイントし、NotEqual をクリックします。</span><span class="sxs-lookup"><span data-stu-id="bc424-170">In the Rule window, right-click AND, point to Predicates, and then click NotEqual.</span></span>  
  
8.  <span data-ttu-id="bc424-171">ファクト エクスプ ローラーからの条件下で [引数 1] ノードに customerName 要素をドラッグします。</span><span class="sxs-lookup"><span data-stu-id="bc424-171">From Facts Explorer, drag the customerName element to the argument1 node under Conditions.</span></span>  
  
9. <span data-ttu-id="bc424-172">[引数 2] ノードをクリックし、GlobalBankEast を入力します。</span><span class="sxs-lookup"><span data-stu-id="bc424-172">Click the argument2 node, and then type GlobalBankEast.</span></span>  
  
10. <span data-ttu-id="bc424-173">ファクト エクスプ ローラーで、[ボキャブラリ] タブをクリックして、ESB を展開します。EndPointInfo、バージョン 1.0 を順に展開します。</span><span class="sxs-lookup"><span data-stu-id="bc424-173">In Facts Explorer, click the Vocabularies tab, expand ESB.EndPointInfo, and then expand Version 1.0.</span></span>  
  
11. <span data-ttu-id="bc424-174">ファクト エクスプ ローラーからアクションを終点送信トランスポート場所の設定の定義をドラッグします。</span><span class="sxs-lookup"><span data-stu-id="bc424-174">From Facts Explorer, drag the Set End Point Outbound Transport Location definition to Actions.</span></span>  
  
12. <span data-ttu-id="bc424-175">をクリックして\<空の文字列\>C:\HowTos\Out\CustomerUnknown%MessageID%.xml を入力します。</span><span class="sxs-lookup"><span data-stu-id="bc424-175">Click \<empty string\>, and then type C:\HowTos\Out\CustomerUnknown%MessageID%.xml.</span></span>  
  
13. <span data-ttu-id="bc424-176">ファクト エクスプ ローラーからアクションを設定の終了点送信トランスポートの種類の定義をドラッグします。</span><span class="sxs-lookup"><span data-stu-id="bc424-176">From Facts Explorer, drag the Set End Point Outbound Transport Type definition to Actions.</span></span>  
  
14. <span data-ttu-id="bc424-177">ファクト エクスプ ローラーで、ESB を展開します。TransportTypes、バージョン 1.0 を展開し、アダプターのプロバイダー定義をドラッグ\<空の文字列\>です。</span><span class="sxs-lookup"><span data-stu-id="bc424-177">In Facts Explorer, expand ESB.TransportTypes, expand Version 1.0, and then drag the Adaptor Providers definition to \<empty string\>.</span></span>  
  
15. <span data-ttu-id="bc424-178">[操作] ウィンドウで、アダプター プロバイダーのボックスの一覧を展開し、[ファイル] をクリックします。</span><span class="sxs-lookup"><span data-stu-id="bc424-178">In the Actions pane, expand the Adaptor Providers drop-down list, and then click FILE.</span></span>  
  
#### <a name="to-publish-and-deploy-the-policy"></a><span data-ttu-id="bc424-179">発行して、ポリシーを展開するには</span><span class="sxs-lookup"><span data-stu-id="bc424-179">To publish and deploy the policy</span></span>  
  
1.  <span data-ttu-id="bc424-180">ポリシー エクスプ ローラーで、、 **RouteBasedOnCustomerKnownType**ポリシーを右クリック**バージョン 1.0 (未保存)**、クリックして**発行**です。</span><span class="sxs-lookup"><span data-stu-id="bc424-180">In Policy Explorer, under the **RouteBasedOnCustomerKnownType** policy, right click **Version 1.0 (not saved)**, and then click **Publish**.</span></span>  
  
2.  <span data-ttu-id="bc424-181">ポリシー エクスプ ローラーで、、 **RouteBasedOnCustomerKnownType**ポリシーを右クリック**バージョン 1.0 - 公開済み**、クリックして**展開**です。</span><span class="sxs-lookup"><span data-stu-id="bc424-181">In Policy Explorer, under the **RouteBasedOnCustomerKnownType** policy, right click **Version 1.0 - Published**, and then click **Deploy**.</span></span>  
  
#### <a name="to-create-an-esb-itinerary-dsl-model"></a><span data-ttu-id="bc424-182">ESB itinerary DSL モデルを作成するには</span><span class="sxs-lookup"><span data-stu-id="bc424-182">To create an ESB itinerary DSL model</span></span>  
  
1.  <span data-ttu-id="bc424-183">Visual Studio で、C:\HowTos\Patterns\Patterns.sln を開きます。</span><span class="sxs-lookup"><span data-stu-id="bc424-183">In Visual Studio, open C:\HowTos\Patterns\Patterns.sln.</span></span>  
  
2.  <span data-ttu-id="bc424-184">ソリューション エクスプ ローラーで右クリックし、 **ItineraryLibrary**プロジェクトをポイントし、**追加**、クリックして**新しい行程**です。</span><span class="sxs-lookup"><span data-stu-id="bc424-184">In Solution Explorer, right-click the **ItineraryLibrary** project, point to **Add**, and then click **New Itinerary**.</span></span>  
  
3.  <span data-ttu-id="bc424-185">**新しい項目の追加** ダイアログ ボックスで、**名前**ボックスに、入力**CbrKnownType**、クリックして**追加**です。</span><span class="sxs-lookup"><span data-stu-id="bc424-185">In the **Add New Item** dialog box, in the **Name** box, type **CbrKnownType**, and then click **Add**.</span></span>  
  
#### <a name="to-configure-the-properties-of-the-itinerary"></a><span data-ttu-id="bc424-186">旅行計画のプロパティを構成するには</span><span class="sxs-lookup"><span data-stu-id="bc424-186">To configure the properties of the itinerary</span></span>  
  
1.  <span data-ttu-id="bc424-187">Visual Studio でのデザイン画面をクリックして**CbrKnownType.itinerary**です。</span><span class="sxs-lookup"><span data-stu-id="bc424-187">In Visual Studio, click the design surface of **CbrKnownType.itinerary**.</span></span> <span data-ttu-id="bc424-188">**CbrKnownType**プロパティ ウィンドウで、次のプロパティを構成します。</span><span class="sxs-lookup"><span data-stu-id="bc424-188">In the **CbrKnownType** Properties window, configure the following properties:</span></span>  
  
    1.  <span data-ttu-id="bc424-189">**モデル エクスポーター**ドロップダウン リストをクリックして**XML 行程エクスポーター**です。</span><span class="sxs-lookup"><span data-stu-id="bc424-189">In the **Model Exporter** drop-down list, click **XML Itinerary Exporter**.</span></span>  
  
    2.  <span data-ttu-id="bc424-190">**Extender 設定**セクションで、横に、**行程 XML ファイル**プロパティ、省略記号ボタン (...) をクリックします。</span><span class="sxs-lookup"><span data-stu-id="bc424-190">In the **Extender Settings** section, next to the **Itinerary XML file** property, click the ellipsis button (...).</span></span>  
  
    3.  <span data-ttu-id="bc424-191">**[XML ファイルの**] ダイアログ ボックスで、「 **C:\HowTos\Itineraries\CbrKnownType**で、**ファイル名**ボックスをクリックして**保存**です。</span><span class="sxs-lookup"><span data-stu-id="bc424-191">In the **Select XML File** dialog box, type **C:\HowTos\Itineraries\CbrKnownType** in the **File name** box, and then click **Save**.</span></span>  
  
        > [!NOTE]
        >  <span data-ttu-id="bc424-192">この手順では、旅行計画をローカル ファイルの場所に XML としてエクスポートすることができます。</span><span class="sxs-lookup"><span data-stu-id="bc424-192">This step enables you to export the itinerary as XML to a local file location.</span></span> <span data-ttu-id="bc424-193">代わりに、ローカル ファイルの場所に日程を itinerary のデータベースにエクスポートして ESB のテスト用クライアント アプリケーションを使用して旅行計画のテストを有効にします。</span><span class="sxs-lookup"><span data-stu-id="bc424-193">By exporting an itinerary to a local file location, instead of to the itinerary database, enables testing of the itinerary using the ESB Test Client application.</span></span> <span data-ttu-id="bc424-194">このトピックの後半には、このプロセスを完了します。</span><span class="sxs-lookup"><span data-stu-id="bc424-194">You will complete this process later in this How-to topic.</span></span>  
  
#### <a name="to-define-the-structure-of-the-itinerary"></a><span data-ttu-id="bc424-195">旅行計画の構造を定義するには</span><span class="sxs-lookup"><span data-stu-id="bc424-195">To define the structure of the itinerary</span></span>  
  
1.  <span data-ttu-id="bc424-196">ツールボックスからドラッグして、**入り口**デザイン画面にモデル要素。</span><span class="sxs-lookup"><span data-stu-id="bc424-196">From the Toolbox, drag an **On-Ramp** model element to the design surface.</span></span> <span data-ttu-id="bc424-197">**OnRamp1**プロパティ ウィンドウで、次のプロパティを構成します。</span><span class="sxs-lookup"><span data-stu-id="bc424-197">In the **OnRamp1** Properties window, configure the following properties:</span></span>  
  
    1.  <span data-ttu-id="bc424-198">クリックして、**名前**プロパティ、および入力**ReceiveNAOrder**です。</span><span class="sxs-lookup"><span data-stu-id="bc424-198">Click the **Name** property, and then type **ReceiveNAOrder**.</span></span>  
  
    2.  <span data-ttu-id="bc424-199">**Extender**ドロップダウン リストをクリックして**入り口 ESB Extender**です。</span><span class="sxs-lookup"><span data-stu-id="bc424-199">In the **Extender** drop-down list, click **On-Ramp ESB Extender**.</span></span>  
  
    3.  <span data-ttu-id="bc424-200">**BizTalk アプリケーション**ドロップダウン リストをクリックして**Microsoft.Practices.ESB**です。</span><span class="sxs-lookup"><span data-stu-id="bc424-200">In the **BizTalk Application** drop-down list, click **Microsoft.Practices.ESB**.</span></span>  
  
    4.  <span data-ttu-id="bc424-201">**受信ポート**ドロップダウン リストをクリックして**OnRamp.Itinerary**です。</span><span class="sxs-lookup"><span data-stu-id="bc424-201">In the **Receive Port** drop-down list, click **OnRamp.Itinerary**.</span></span>  
  
2.  <span data-ttu-id="bc424-202">ツールボックスからドラッグして、**出口**デザイン画面に要素をモデル化の右側に配置し、 **ReceiveNAOrder**モデル要素。</span><span class="sxs-lookup"><span data-stu-id="bc424-202">From the Toolbox, drag an **Off-Ramp** model element to the design surface, and then place it to the right of the **ReceiveNAOrder** model element.</span></span> <span data-ttu-id="bc424-203">**OffRamp1**プロパティ ウィンドウで、次のプロパティを構成します。</span><span class="sxs-lookup"><span data-stu-id="bc424-203">In the **OffRamp1** Properties window, configure the following properties:</span></span>  
  
    1.  <span data-ttu-id="bc424-204">クリックして、**名前**プロパティ、および入力**SendRegionalOrders**です。</span><span class="sxs-lookup"><span data-stu-id="bc424-204">Click the **Name** property, and then type **SendRegionalOrders**.</span></span>  
  
    2.  <span data-ttu-id="bc424-205">**Extender**ドロップダウン リストをクリックして**出口 ESB Extender**です。</span><span class="sxs-lookup"><span data-stu-id="bc424-205">In the **Extender** drop-down list, click **Off-Ramp ESB Extender**.</span></span>  
  
    3.  <span data-ttu-id="bc424-206">**BizTalk アプリケーション**ドロップダウン リストをクリックして**GlobalBank.ESB**です。</span><span class="sxs-lookup"><span data-stu-id="bc424-206">In the **BizTalk Application** drop-down list, click **GlobalBank.ESB**.</span></span>  
  
    4.  <span data-ttu-id="bc424-207">**送信ポート**ドロップダウン リストをクリックして**DynamicResolutionOneWay**です。</span><span class="sxs-lookup"><span data-stu-id="bc424-207">In the **Send Port** drop-down list, click **DynamicResolutionOneWay**.</span></span>  
  
3.  <span data-ttu-id="bc424-208">ツールボックスからドラッグ、**行程サービス**モデルをデザイン画面に要素との間に配置し、 **ReceiveNAOrder**モデル要素と**SendRegionalOrders**モデル要素。</span><span class="sxs-lookup"><span data-stu-id="bc424-208">From the Toolbox, drag an **Itinerary Service** model element to the design surface, and then place it between the **ReceiveNAOrder** model element and the **SendRegionalOrders** model element.</span></span> <span data-ttu-id="bc424-209">**ItineraryService1**プロパティ ウィンドウで、次のプロパティを構成します。</span><span class="sxs-lookup"><span data-stu-id="bc424-209">In the **ItineraryService1** Properties window, configure the following properties:</span></span>  
  
    1.  <span data-ttu-id="bc424-210">クリックして、**名前**プロパティ、および入力**SendPortFilter**です。</span><span class="sxs-lookup"><span data-stu-id="bc424-210">Click the **Name** property, and then type **SendPortFilter**.</span></span>  
  
    2.  <span data-ttu-id="bc424-211">**行程サービス エクステンダー**ドロップダウン リストをクリックして**出口 Extender**です。</span><span class="sxs-lookup"><span data-stu-id="bc424-211">In the **Itinerary Service Extender** drop-down list, click **Off-Ramp Extender**.</span></span>  
  
    3.  <span data-ttu-id="bc424-212">**出口**ドロップダウン リストで、展開**SendRegionalOrders**、クリックして**送信ハンドラー**です。</span><span class="sxs-lookup"><span data-stu-id="bc424-212">In the **Off-Ramp** drop-down list, expand **SendRegionalOrders**, and then click **Send Handlers**.</span></span>  
  
4.  <span data-ttu-id="bc424-213">右クリックし、**リゾルバー**のコレクション、 **SendPortFilter**モデル要素をクリックして**新しいリゾルバーを追加**です。</span><span class="sxs-lookup"><span data-stu-id="bc424-213">Right-click the **Resolver** collection of the **SendPortFilter** model element, and then click **Add new Resolver**.</span></span> <span data-ttu-id="bc424-214">**Resolver1**プロパティ ウィンドウで、次のプロパティを構成します。</span><span class="sxs-lookup"><span data-stu-id="bc424-214">In the **Resolver1** Properties window, configure the following properties:</span></span>  
  
    1.  <span data-ttu-id="bc424-215">クリックして、**名前**プロパティ、および入力**RouteRegionalOrders**です。</span><span class="sxs-lookup"><span data-stu-id="bc424-215">Click the **Name** property, and then type **RouteRegionalOrders**.</span></span>  
  
    2.  <span data-ttu-id="bc424-216">**トランスポート名**ドロップダウン リストをクリックして**BRE**です。</span><span class="sxs-lookup"><span data-stu-id="bc424-216">In the **Transport Name** drop-down list, click **BRE**.</span></span>  
  
    3.  <span data-ttu-id="bc424-217">**リゾルバーの実装**ドロップダウン リストをクリックして**Bre 競合回避モジュールの拡張機能**します。</span><span class="sxs-lookup"><span data-stu-id="bc424-217">In the **Resolver Implementation** drop-down list, click **Bre Resolver Extension**.</span></span>  
  
    4.  <span data-ttu-id="bc424-218">**ポリシー**ドロップダウン リストをクリックして**RouteBasedOnCustomerKnownType**です。</span><span class="sxs-lookup"><span data-stu-id="bc424-218">In the **Policy** drop-down list, click **RouteBasedOnCustomerKnownType**.</span></span>  
  
    5.  <span data-ttu-id="bc424-219">**メッセージ形式を認識**ドロップダウン リストをクリックして**True**です。</span><span class="sxs-lookup"><span data-stu-id="bc424-219">In the **Recognize Message Format** drop-down list click **True**.</span></span>  
  
    6.  <span data-ttu-id="bc424-220">**UseMsg**ドロップダウン リストをクリックして**True**です。</span><span class="sxs-lookup"><span data-stu-id="bc424-220">In the **UseMsg** drop-down list, click **True**.</span></span>  
  
        > [!NOTE]
        >  <span data-ttu-id="bc424-221">オーケストレーションへの BRE リゾルバー拡張機能を使用する場合、 **recognizeMessageFormat**プロパティに設定する必要があります**False**です。</span><span class="sxs-lookup"><span data-stu-id="bc424-221">If you use the BRE Resolver Extension from orchestration, the **recognizeMessageFormat** property must be set to **False**.</span></span>  
  
5.  <span data-ttu-id="bc424-222">ツールボックスで、をクリックして**コネクタ**です。</span><span class="sxs-lookup"><span data-stu-id="bc424-222">In the Toolbox, click **Connector**.</span></span> <span data-ttu-id="bc424-223">接続をドラッグして、 **ReceiveNAOrder**モデル要素を**SendPortFilter**モデル要素。</span><span class="sxs-lookup"><span data-stu-id="bc424-223">Drag a connection from the **ReceiveNAOrder** model element to the **SendPortFilter** model element.</span></span>  
  
6.  <span data-ttu-id="bc424-224">ツールボックスで、をクリックして**コネクタ**です。</span><span class="sxs-lookup"><span data-stu-id="bc424-224">In the Toolbox, click **Connector**.</span></span> <span data-ttu-id="bc424-225">接続をドラッグして、 **SendPortFilter**モデル要素を**SendRegionalOrders**モデル要素。</span><span class="sxs-lookup"><span data-stu-id="bc424-225">Drag a connection from the **SendPortFilter** model element to the **SendRegionalOrders** model element.</span></span>  
  
#### <a name="to-export-the-model-for-use-with-the-itinerary-test-client"></a><span data-ttu-id="bc424-226">行程テスト クライアントで使用するモデルをエクスポートするには</span><span class="sxs-lookup"><span data-stu-id="bc424-226">To export the model for use with the Itinerary Test Client</span></span>  
  
1.  <span data-ttu-id="bc424-227">Visual Studio でのデザイン画面を右クリックし、 **CbrKnownType**行程をクリックして**モデルのエクスポート**です。</span><span class="sxs-lookup"><span data-stu-id="bc424-227">In Visual Studio, right-click the design surface of the **CbrKnownType** itinerary, and then click **Export Model**.</span></span>  
  
    > [!NOTE]
    >  <span data-ttu-id="bc424-228">旅行計画の XML バージョンは、Visual Studio で開きます。</span><span class="sxs-lookup"><span data-stu-id="bc424-228">The XML version of the itinerary opens in Visual Studio.</span></span>  
  
2.  <span data-ttu-id="bc424-229">すべてのプロジェクトの成果物を保存します。</span><span class="sxs-lookup"><span data-stu-id="bc424-229">Save all project artifacts.</span></span>  
  
3.  <span data-ttu-id="bc424-230">Windows エクスプローラで、C:\HowTos\Itineraries を参照し、行程 XML (CbrKnownType.xml) の作成に注意してください。</span><span class="sxs-lookup"><span data-stu-id="bc424-230">In Windows Explorer, browse to C:\HowTos\Itineraries and notice the creation of your itinerary XML (CbrKnownType.xml).</span></span>  
  
#### <a name="to-test-the-itinerary-and-business-rules"></a><span data-ttu-id="bc424-231">Itinerary とビジネス ルールをテストするには</span><span class="sxs-lookup"><span data-stu-id="bc424-231">To test the itinerary and business rules</span></span>  
  
1.  <span data-ttu-id="bc424-232">中に作成されたショートカットを使用して行程テスト用クライアントのサンプル アプリケーションを開く、[開発活動の前提条件](../esb-toolkit/prerequisites-for-the-development-activities.md)(C:\HowTos\ESB です。Itinerary.Test.exe - ショートカット)。</span><span class="sxs-lookup"><span data-stu-id="bc424-232">Open the Itinerary Test Client sample application using the shortcut created during the [Prerequisites for the Development Activities](../esb-toolkit/prerequisites-for-the-development-activities.md) (C:\HowTos\ESB.Itinerary.Test.exe - Shortcut).</span></span>  
  
2.  <span data-ttu-id="bc424-233">行程テスト クライアントで、クリア、**を使用して WCF サービス**チェック ボックスをクリックして**ロード行程**です。</span><span class="sxs-lookup"><span data-stu-id="bc424-233">In the Itinerary Test Client, clear the **Use WCF Service** check box, and then click **Load Itinerary**.</span></span>  
  
3.  <span data-ttu-id="bc424-234">**行程ファイルを開く** ダイアログ ボックスで、C:\HowTos\Itineraries を参照します。</span><span class="sxs-lookup"><span data-stu-id="bc424-234">In the **Open Itinerary File** dialog box, browse to C:\HowTos\Itineraries.</span></span> <span data-ttu-id="bc424-235">選択**CbrKnownType.xml**、順にクリック**開く**日程を読み込めません。</span><span class="sxs-lookup"><span data-stu-id="bc424-235">Select **CbrKnownType.xml**, and then click **Open** to load the itinerary.</span></span>  
  
4.  <span data-ttu-id="bc424-236">をクリックして**OK**をクリアする、**行程が正常に読み込まれる**メッセージ。</span><span class="sxs-lookup"><span data-stu-id="bc424-236">Click **OK** to clear the **Itinerary Loaded Successfully** message.</span></span>  
  
5.  <span data-ttu-id="bc424-237">行程テスト クライアントで、横にある省略記号ボタン (...) をクリックして、**メッセージの読み込み**ボックス。</span><span class="sxs-lookup"><span data-stu-id="bc424-237">In the Itinerary Test Client, click the ellipsis button (...) next to the **Load Message** box.</span></span>  
  
6.  <span data-ttu-id="bc424-238">**選択読み込む XML ドキュメントを** ダイアログ ボックスで、C:\HowTos を参照します。</span><span class="sxs-lookup"><span data-stu-id="bc424-238">In the **Select XML Document to load** dialog box, browse to C:\HowTos.</span></span> <span data-ttu-id="bc424-239">選択**West.xml**、順にクリック**開く**テスト メッセージを読み込めません。</span><span class="sxs-lookup"><span data-stu-id="bc424-239">Select **West.xml**, and then click **Open** to load the test message.</span></span>  
  
7.  <span data-ttu-id="bc424-240">クリックして、**要求を提出**ボタンをクリックします。</span><span class="sxs-lookup"><span data-stu-id="bc424-240">Click the **Submit Request** button.</span></span> <span data-ttu-id="bc424-241">テストが完了したらをクリックして**OK**表示される確認メッセージを破棄します。</span><span class="sxs-lookup"><span data-stu-id="bc424-241">When the test completes, click **OK** to dismiss the confirmation that appears.</span></span>  
  
8.  <span data-ttu-id="bc424-242">Windows エクスプローラで、C:\HowTos\Out を参照します。West%MessageID%.xml メッセージがディレクトリに書き込まれたことを確認します。</span><span class="sxs-lookup"><span data-stu-id="bc424-242">In Windows Explorer, browse to C:\HowTos\Out. Verify that the West%MessageID%.xml message has been written to the directory.</span></span>  
  
9. <span data-ttu-id="bc424-243">East.xml メッセージを使用して、テスト プロセスを繰り返します。</span><span class="sxs-lookup"><span data-stu-id="bc424-243">Repeat the test process using the East.xml message.</span></span>  
  
10. <span data-ttu-id="bc424-244">Windows エクスプローラで、C:\HowTos\Out を参照します。East%MessageID%.xml メッセージがディレクトリに書き込まれたことを確認します。</span><span class="sxs-lookup"><span data-stu-id="bc424-244">In Windows Explorer, browse to C:\HowTos\Out. Verify that the East%MessageID%.xml message has been written to the directory.</span></span>  
  
11. <span data-ttu-id="bc424-245">NAOrderDoc.xml メッセージを使用して、テスト プロセスを繰り返します。</span><span class="sxs-lookup"><span data-stu-id="bc424-245">Repeat the test process using the NAOrderDoc.xml message.</span></span>  
  
12. <span data-ttu-id="bc424-246">Windows エクスプローラで、C:\HowTos\Out を参照します。CustomerUnknown%MessageID%.xml メッセージがディレクトリに書き込まれたことを確認します。</span><span class="sxs-lookup"><span data-stu-id="bc424-246">In Windows Explorer, browse to C:\HowTos\Out. Verify that the CustomerUnknown%MessageID%.xml message has been written to the directory.</span></span>  
  
## <a name="additional-resources"></a><span data-ttu-id="bc424-247">その他のリソース</span><span class="sxs-lookup"><span data-stu-id="bc424-247">Additional Resources</span></span>  
 <span data-ttu-id="bc424-248">詳細については、次の関連項目を参照してください。</span><span class="sxs-lookup"><span data-stu-id="bc424-248">For more information, see the following related topics:</span></span>  
  
-   [<span data-ttu-id="bc424-249">方法: ビジネス ルール ポリシーを使用して、日程を選択</span><span class="sxs-lookup"><span data-stu-id="bc424-249">How to: Select an Itinerary Using a Business Rules Policy</span></span>](../esb-toolkit/how-to-select-an-itinerary-using-a-business-rules-policy.md)  
  
-   [<span data-ttu-id="bc424-250">方法: ビジネス ルール ポリシーを利用し、メッセージ コンテキストに基づき、メッセージの経路を動的に決定する</span><span class="sxs-lookup"><span data-stu-id="bc424-250">How to: Dynamically Route a Message Based on Message Context Using a Business Rules Policy</span></span>](../esb-toolkit/dynamically-route-messages-based-on-message-context-using-business-rules-policy.md)  
  
-   [<span data-ttu-id="bc424-251">開発アクティビティ</span><span class="sxs-lookup"><span data-stu-id="bc424-251">Development Activities</span></span>](../esb-toolkit/development-activities.md)  
  
-   [<span data-ttu-id="bc424-252">メッセージ ルーティング パターン</span><span class="sxs-lookup"><span data-stu-id="bc424-252">Message Routing Patterns</span></span>](../esb-toolkit/message-routing-patterns.md)