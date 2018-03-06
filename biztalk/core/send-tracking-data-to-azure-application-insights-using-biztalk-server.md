---
title: "Application Insights または Event Hubs へのデータの追跡 |Microsoft ドキュメント"
description: "Azure の Application Insights または BizTalk Server で Azure Event Hubs での追跡データの分析を有効にする feature pack をインストールします。"
ms.custom: fp1, fp2
ms.date: 11/16/2017
ms.prod: biztalk-server
ms.reviewer: 
ms.suite: 
ms.tgt_pltfrm: 
ms.topic: article
ms.assetid: b3ff6cb9-44d0-46cd-9b4f-a346365afb7b
caps.latest.revision: 
author: tordgladnordahl
ms.author: mandia
manager: anneta
ms.openlocfilehash: f5ddd60f72955c7196edfc8bf2310b73226d2abe
ms.sourcegitcommit: 32f380810b90b70e5df7be72a6a14988a747868e
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 02/28/2018
---
# <a name="send-biztalk-tracking-data-to-azure-application-insights-or-event-hubs"></a><span data-ttu-id="3f2cd-103">BizTalk 追跡データを Azure の Application Insights または Event Hubs の送信します。</span><span class="sxs-lookup"><span data-stu-id="3f2cd-103">Send BizTalk tracking data to Azure Application Insights or Event Hubs</span></span>

<span data-ttu-id="3f2cd-104">**以降で[!INCLUDE[bts2016_md](../includes/bts2016-md.md)] [!INCLUDE[featurepack1](../includes/featurepack1.md)]**を処理し、追跡データを Azure Application Insights に送信することができます。</span><span class="sxs-lookup"><span data-stu-id="3f2cd-104">**Starting with [!INCLUDE[bts2016_md](../includes/bts2016-md.md)] [!INCLUDE[featurepack1](../includes/featurepack1.md)]**, you can process and send your tracking data to Azure Application Insights.</span></span> 
          
<span data-ttu-id="3f2cd-105">**以降で[!INCLUDE[bts2016_md](../includes/bts2016-md.md)]Feature Pack 2**:</span><span class="sxs-lookup"><span data-stu-id="3f2cd-105">**Starting with [!INCLUDE[bts2016_md](../includes/bts2016-md.md)] Feature Pack 2**:</span></span>

* <span data-ttu-id="3f2cd-106">Application Insights は、既定の SQL インスタンスと名前付きインスタンスの SQL サポートしています。</span><span class="sxs-lookup"><span data-stu-id="3f2cd-106">Application Insights supports SQL default instances, and SQL named instances</span></span>
* <span data-ttu-id="3f2cd-107">プロセスおよび追跡データを Azure Event Hubs に送信できます。</span><span class="sxs-lookup"><span data-stu-id="3f2cd-107">You can process and send tracking data to Azure Event Hubs</span></span>

<span data-ttu-id="3f2cd-108">受信ポート、送信ポート、およびオーケストレーションからのインスタンスを追跡するには、これらの Azure サービスを使用します。</span><span class="sxs-lookup"><span data-stu-id="3f2cd-108">Use these Azure services to track your instances from receive ports, send ports, and orchestrations.</span></span>

## <a name="prerequisites"></a><span data-ttu-id="3f2cd-109">前提条件</span><span class="sxs-lookup"><span data-stu-id="3f2cd-109">Prerequisites</span></span>
* <span data-ttu-id="3f2cd-110">新しいインスタンスを作成する[Application Insights](https://docs.microsoft.com/azure/application-insights/app-insights-create-new-resource)です。</span><span class="sxs-lookup"><span data-stu-id="3f2cd-110">Create a new instance of [Application Insights](https://docs.microsoft.com/azure/application-insights/app-insights-create-new-resource).</span></span> <span data-ttu-id="3f2cd-111">BizTalk Server を使用して、**インストルメンテーション キー**を認証します。</span><span class="sxs-lookup"><span data-stu-id="3f2cd-111">BizTalk Server uses the **Instrumentation Key** to authenticate.</span></span>
* <span data-ttu-id="3f2cd-112">作成、 [Azure Event Hubs の名前空間とイベント ハブ](https://docs.microsoft.com/azure/event-hubs/event-hubs-create)です。</span><span class="sxs-lookup"><span data-stu-id="3f2cd-112">Create an [Azure Event Hubs namespace and event hub](https://docs.microsoft.com/azure/event-hubs/event-hubs-create).</span></span> <span data-ttu-id="3f2cd-113">BizTalk Server では、SAS (名前空間レベル) またはイベント ハブ レベルのポリシーを使用して、認証します。</span><span class="sxs-lookup"><span data-stu-id="3f2cd-113">BizTalk Server uses the SAS (namespace-level) or event hub-level policy to authenticate.</span></span>
* <span data-ttu-id="3f2cd-114">インストール[Feature Pack 2](https://aka.ms/bts2016fp2)で、</span><span class="sxs-lookup"><span data-stu-id="3f2cd-114">Install [Feature Pack 2](https://aka.ms/bts2016fp2) on your</span></span> [!INCLUDE[btsBizTalkServerNoVersion_md](../includes/btsbiztalkservernoversion-md.md)]

## <a name="enable-analytics-for-your-environment"></a><span data-ttu-id="3f2cd-115">環境の分析を有効にします。</span><span class="sxs-lookup"><span data-stu-id="3f2cd-115">Enable analytics for your environment</span></span>

1. <span data-ttu-id="3f2cd-116">開く、 **BizTalk Server 管理コンソール**コンソールで、右クリックし、 **BizTalk グループ**を選択して**設定**です。</span><span class="sxs-lookup"><span data-stu-id="3f2cd-116">Open the **BizTalk Server Administration** console, right-click the **BizTalk Group**, and select **Settings**.</span></span> 
2. <span data-ttu-id="3f2cd-117">確認**グループ レベルの分析を有効にする**です。</span><span class="sxs-lookup"><span data-stu-id="3f2cd-117">Check **Enable group-level analytics**.</span></span>
3. <span data-ttu-id="3f2cd-118">**ターゲット型** **Application Insight**または**Event Hub**一覧からです。</span><span class="sxs-lookup"><span data-stu-id="3f2cd-118">For the **Target type**, select **Application Insight** or **Event Hub** from the list.</span></span>
    <span data-ttu-id="3f2cd-119">![環境の分析を有効にします。](../core/media/environmentsettingapplicationinishgt.PNG)</span><span class="sxs-lookup"><span data-stu-id="3f2cd-119">![Enable analytics for your environment](../core/media/environmentsettingapplicationinishgt.PNG)</span></span>

4. <span data-ttu-id="3f2cd-120">**接続パラメーター**、select、**しています.**ボタン、および**サインイン**Azure アカウントにします。</span><span class="sxs-lookup"><span data-stu-id="3f2cd-120">For the **Connection parameters**, select the **...** button, and **Sign-in** to your Azure account.</span></span>  

    <span data-ttu-id="3f2cd-121">**Application Insights 用**</span><span class="sxs-lookup"><span data-stu-id="3f2cd-121">**For Application Insights**</span></span>  
    <span data-ttu-id="3f2cd-122">選択、**サブスクリプション**、**リソース グループ**と、Application Insights インスタンス。</span><span class="sxs-lookup"><span data-stu-id="3f2cd-122">Select your **Subscription**, **Resource Group**, and your Application Insights instance.</span></span>

    ![環境の分析を有効にします。](../core/media/analytics-group-application-insights.png)

    <span data-ttu-id="3f2cd-124">**イベント ハブの**</span><span class="sxs-lookup"><span data-stu-id="3f2cd-124">**For Event Hub**</span></span>  
    <span data-ttu-id="3f2cd-125">選択、**サブスクリプション**、**リソース グループ**、Event Hub の名前空間、およびイベント ハブ。</span><span class="sxs-lookup"><span data-stu-id="3f2cd-125">Select your **Subscription**, **Resource Group**, Event Hub namespace, and event hub.</span></span> <span data-ttu-id="3f2cd-126">認証の場合は、名前空間レベル、またはイベント ハブ レベルでもエンティティの署名でアクセス署名 (SAS) を使用できます。</span><span class="sxs-lookup"><span data-stu-id="3f2cd-126">For authentication, you can use an access signature (SAS) at the namespace-level, or entity signature at the event hub-level.</span></span> <span data-ttu-id="3f2cd-127">使用可能なキーに問題が自動的に入力されます内で構成した値[Azure](https://portal.azure.com)です。</span><span class="sxs-lookup"><span data-stu-id="3f2cd-127">Your available keys are auto-populated with the values previously configured within [Azure](https://portal.azure.com).</span></span>

    ![環境の分析を有効にします。](../core/media/send-tracking-data-to-azure.png)

5. <span data-ttu-id="3f2cd-129">選択 **OK** して変更を保存します。</span><span class="sxs-lookup"><span data-stu-id="3f2cd-129">Select **OK** to save your changes.</span></span> 

<span data-ttu-id="3f2cd-130">有効にすると、 [!INCLUDE[btsBizTalkServerNoVersion_md](../includes/btsbiztalkservernoversion-md.md)] Azure リソースへのデータを送信する準備ができました。</span><span class="sxs-lookup"><span data-stu-id="3f2cd-130">Once enabled, [!INCLUDE[btsBizTalkServerNoVersion_md](../includes/btsbiztalkservernoversion-md.md)] is ready to transmit data to your Azure resource.</span></span> <span data-ttu-id="3f2cd-131">次に、ポートやオーケストレーションに対する分析を有効にします。</span><span class="sxs-lookup"><span data-stu-id="3f2cd-131">Next, enable analytics on your ports and orchestrations.</span></span> 

## <a name="enable-analytics-on-your-artifacts"></a><span data-ttu-id="3f2cd-132">アイテムに対する分析を有効にします。</span><span class="sxs-lookup"><span data-stu-id="3f2cd-132">Enable analytics on your artifacts</span></span>

1. <span data-ttu-id="3f2cd-133">BizTalk Server 管理 を右クリックし、**受信ポート**、**送信ポート**または**オーケストレーション**を選択して**追跡**です。</span><span class="sxs-lookup"><span data-stu-id="3f2cd-133">In BizTalk Server Administration, right-click a **receive port**, **send port** or **orchestration**, and select **Tracking**.</span></span>
2. <span data-ttu-id="3f2cd-134">**分析**、確認**Analytics を有効にする**次のようなです。</span><span class="sxs-lookup"><span data-stu-id="3f2cd-134">Under **Analytics**, check **Enable Analytics**, similar to the following.</span></span> <span data-ttu-id="3f2cd-135">この設定は、追跡、および成果物から Azure リソースへのデータの送信を開始します。</span><span class="sxs-lookup"><span data-stu-id="3f2cd-135">This setting starts tracking and transmitting data from the artifact to your Azure resource.</span></span>
    
    ![オーケストレーションの追跡データ](../core/media/orchestrationsettingsapplicationinsight.PNG)

3. <span data-ttu-id="3f2cd-137">選択 **OK** して変更を保存します。</span><span class="sxs-lookup"><span data-stu-id="3f2cd-137">Select **OK** to save your changes.</span></span>
4. <span data-ttu-id="3f2cd-138">追跡ホスト インスタンスを再起動し、BizTalk アプリケーションが開始されたことを確認します。</span><span class="sxs-lookup"><span data-stu-id="3f2cd-138">Restart the tracking host Instance, and confirm the BizTalk Application is started.</span></span>

> [!TIP]
> <span data-ttu-id="3f2cd-139">組織のデータをさらに多くの把握するためには、他のシステムと、BizTalk Server の分析結果を接続します。</span><span class="sxs-lookup"><span data-stu-id="3f2cd-139">Connect your BizTalk Server Analytics with other systems to gain even more insight into your organizations data.</span></span>

## <a name="view-your-data"></a><span data-ttu-id="3f2cd-140">データを表示します。</span><span class="sxs-lookup"><span data-stu-id="3f2cd-140">View your data</span></span>

#### <a name="use-application-insights"></a><span data-ttu-id="3f2cd-141">Application Insights を使用します。</span><span class="sxs-lookup"><span data-stu-id="3f2cd-141">Use Application Insights</span></span>
<span data-ttu-id="3f2cd-142">Application Insights にデータが送信されると、Azure 内で分析ツールを使用して、高度なクエリを作成し、データを分析できます。</span><span class="sxs-lookup"><span data-stu-id="3f2cd-142">Once the data is sent to Application Insights, you can use the analytics tools within Azure to create advanced queries, and analyze your data.</span></span>

1. <span data-ttu-id="3f2cd-143">サインイン、 [Azure ポータル](https://portal.azure.com)です。</span><span class="sxs-lookup"><span data-stu-id="3f2cd-143">Sign in to the [Azure Portal](https://portal.azure.com).</span></span>
2. <span data-ttu-id="3f2cd-144">Application Insights のリソースを開き、選択**メトリックス エクスプ ローラー**です。</span><span class="sxs-lookup"><span data-stu-id="3f2cd-144">Open your Application Insights resource, and select **Metrics Explorer**.</span></span>
3. <span data-ttu-id="3f2cd-145">空のグラフが表示されます。</span><span class="sxs-lookup"><span data-stu-id="3f2cd-145">Empty charts may display.</span></span> <span data-ttu-id="3f2cd-146">グラフでは、次のように選択します。**編集**です。</span><span class="sxs-lookup"><span data-stu-id="3f2cd-146">In a chart, select **Edit**.</span></span> <span data-ttu-id="3f2cd-147">**メトリック****カスタム**使用の追跡対象のプロパティを表示します。</span><span class="sxs-lookup"><span data-stu-id="3f2cd-147">Under **Metrics**, select **Custom** to see the available tracked properties.</span></span> <span data-ttu-id="3f2cd-148">グラフに変更を表示するさまざまなオプションを選択します。</span><span class="sxs-lookup"><span data-stu-id="3f2cd-148">Select some of the different options to see the changes on your chart:</span></span> 

    ![Azure Analytics](../core/media/azure-stream-metrics-custom.png)

4. <span data-ttu-id="3f2cd-150">戻り、Application Insights のリソースを選択して**Analytics**です。</span><span class="sxs-lookup"><span data-stu-id="3f2cd-150">Go back to your Application Insights resource, and select **Analytics**.</span></span> <span data-ttu-id="3f2cd-151">**使用状況****実行**です。</span><span class="sxs-lookup"><span data-stu-id="3f2cd-151">In **Usage**, select **Run**.</span></span> <span data-ttu-id="3f2cd-152">サンプル クエリが実行され、結果がグラフに表示されます。</span><span class="sxs-lookup"><span data-stu-id="3f2cd-152">A sample query is executed, and the results are displayed in a chart.</span></span>  

> [!TIP]
> <span data-ttu-id="3f2cd-153">Azure の Application Insights は、強力なツールです。</span><span class="sxs-lookup"><span data-stu-id="3f2cd-153">Azure Application Insights is a powerful tool.</span></span> <span data-ttu-id="3f2cd-154">Application Insights でのクエリを作成するのに役立つリソースがある[Application Insights で分析](https://docs.microsoft.com/azure/application-insights/app-insights-analytics)とで作業を開始する場合でも[Application Insights とは?](https://docs.microsoft.com/azure/application-insights/app-insights-overview)です。</span><span class="sxs-lookup"><span data-stu-id="3f2cd-154">There are resources to help you write queries in Application Insights at [Analytics in Application Insights](https://docs.microsoft.com/azure/application-insights/app-insights-analytics), and even to get started at [What is Application Insights?](https://docs.microsoft.com/azure/application-insights/app-insights-overview).</span></span>

#### <a name="use-event-hubs"></a><span data-ttu-id="3f2cd-155">Event Hubs を使用します。</span><span class="sxs-lookup"><span data-stu-id="3f2cd-155">Use Event Hubs</span></span>
<span data-ttu-id="3f2cd-156">Event Hubs にデータが送信されると、複数のデータを表示する方法があります。</span><span class="sxs-lookup"><span data-stu-id="3f2cd-156">Once the data is sent to Event Hubs, there are a couple of ways to see the data.</span></span> <span data-ttu-id="3f2cd-157">Event Hubs の多くのユーザーを使用しているイベント ハブをキャプチャしてストリーミング データを Azure に読み込みます。</span><span class="sxs-lookup"><span data-stu-id="3f2cd-157">Many Event Hubs users are using Event Hubs Capture to load streaming data into Azure.</span></span> <span data-ttu-id="3f2cd-158">目的は、フォーカス データ キャプチャではなく、データ処理をするのです。</span><span class="sxs-lookup"><span data-stu-id="3f2cd-158">The intent is for you to focus on data processing, rather than on data capture.</span></span> <span data-ttu-id="3f2cd-159">[イベント ハブのキャプチャ](https://docs.microsoft.com/azure/event-hubs/event-hubs-capture-overview)しくみ、およびを設定する方法について説明します。</span><span class="sxs-lookup"><span data-stu-id="3f2cd-159">[Event Hubs Capture](https://docs.microsoft.com/azure/event-hubs/event-hubs-capture-overview) explains how it works, and how to set it up.</span></span>

<span data-ttu-id="3f2cd-160">別のオプションでは、受信ポートと、イベント ハブのアダプターを使用して受信場所を作成します。</span><span class="sxs-lookup"><span data-stu-id="3f2cd-160">Another option is to create a receive port and receive location using the Event Hub Adapter.</span></span> <span data-ttu-id="3f2cd-161">次に、フォルダーにデータを出力することができます。</span><span class="sxs-lookup"><span data-stu-id="3f2cd-161">Then, you can output the data to a folder.</span></span> <span data-ttu-id="3f2cd-162">この概念は、シナリオをテストする場合に最適な可能性があります。</span><span class="sxs-lookup"><span data-stu-id="3f2cd-162">This idea may be best if you want to test the scenario.</span></span> <span data-ttu-id="3f2cd-163">[イベント ハブのアダプター](event-hubs-adapter.md) Event Hubs から BizTalk Server にメッセージを受信する手順について説明します。</span><span class="sxs-lookup"><span data-stu-id="3f2cd-163">[Event Hubs adapter](event-hubs-adapter.md) lists the steps to receive messages into BizTalk Server from Event Hubs.</span></span>

## <a name="where-the-data-is-stored"></a><span data-ttu-id="3f2cd-164">データの格納場所</span><span class="sxs-lookup"><span data-stu-id="3f2cd-164">Where the data is stored</span></span>

<span data-ttu-id="3f2cd-165">Azure リソース内で、非常に早く (、数分以内)、追跡データが表示されます。</span><span class="sxs-lookup"><span data-stu-id="3f2cd-165">Your tracking data should display fairly quickly (within a few minutes) within your Azure resources.</span></span> <span data-ttu-id="3f2cd-166">しない場合、追跡ホストの問題があります。</span><span class="sxs-lookup"><span data-stu-id="3f2cd-166">If it doesn't, then there may be an issue with the tracking host.</span></span> <span data-ttu-id="3f2cd-167">SQL Server で分析データは、TrackingData_2_ で、BizTalkMsgBoxDb データベースに格納*x*テーブル。</span><span class="sxs-lookup"><span data-stu-id="3f2cd-167">In SQL Server, the Analytics data is stored in the BizTalkMsgBoxDb database, in the TrackingData_2_*x* tables.</span></span> <span data-ttu-id="3f2cd-168">SQL Server Management Studio では、これら 4 つのテーブルで上位 1000 行を返します。</span><span class="sxs-lookup"><span data-stu-id="3f2cd-168">In SQL Server Management Studio, return the top 1000 rows on these four tables.</span></span> <span data-ttu-id="3f2cd-169">データが存在する場合、追跡ホストに移行しないデータ、BizTalkDTADb データベース。</span><span class="sxs-lookup"><span data-stu-id="3f2cd-169">If the data is there, then the tracking host is not moving the data to the BizTalkDTADb database.</span></span> 

<span data-ttu-id="3f2cd-170">いくつか考えられる解決策:</span><span class="sxs-lookup"><span data-stu-id="3f2cd-170">Some possible resolutions:</span></span>

1. <span data-ttu-id="3f2cd-171">追跡ホストを再起動します。</span><span class="sxs-lookup"><span data-stu-id="3f2cd-171">Restart the tracking host.</span></span>
2. <span data-ttu-id="3f2cd-172">専用の追跡ホストを作成します。</span><span class="sxs-lookup"><span data-stu-id="3f2cd-172">Create a dedicated tracking host.</span></span> <span data-ttu-id="3f2cd-173">追跡を有効にすることがあります BizTalk Server がインストールされているときに、 **BizTalk Server アプリケーション 1**ホストします。</span><span class="sxs-lookup"><span data-stu-id="3f2cd-173">When BizTalk Server is installed, tracking may be enabled on the **BizTalk Server Application 1** host.</span></span> <span data-ttu-id="3f2cd-174">通常、このアプリケーションは、メッセージの処理にも使用されます。</span><span class="sxs-lookup"><span data-stu-id="3f2cd-174">Typically, this application is also used to process messages.</span></span> <span data-ttu-id="3f2cd-175">次の手順を使用して、専用の追跡ホストを作成します。</span><span class="sxs-lookup"><span data-stu-id="3f2cd-175">Create a dedicated tracking host using the following steps:</span></span> 

    1. <span data-ttu-id="3f2cd-176">BizTalk Server 管理コンソールで、BizTalk Server アプリケーション 1 ホストのプロパティを開き、オフにして**ホストの追跡を許可する**です。</span><span class="sxs-lookup"><span data-stu-id="3f2cd-176">In BizTalk Server Administration, open the properties of the BizTalk Server Application 1 host, and uncheck **Allow Host Tracking**.</span></span> <span data-ttu-id="3f2cd-177">このホスト インスタンスを再起動します。</span><span class="sxs-lookup"><span data-stu-id="3f2cd-177">Restart this host instance.</span></span>

    2. <span data-ttu-id="3f2cd-178">という名前の新しいホストを作成する**追跡**、し確認**ホストの追跡を許可する**です。</span><span class="sxs-lookup"><span data-stu-id="3f2cd-178">Create a new host named **Tracking**, and check **Allow Host Tracking**.</span></span> <span data-ttu-id="3f2cd-179">ホスト インスタンスを作成し、それを開始します。</span><span class="sxs-lookup"><span data-stu-id="3f2cd-179">Create a host instance, and start it.</span></span>

<span data-ttu-id="3f2cd-180">ここで、もう一度 BizTalkMsgBoxDb TrackingData_2_x テーブルを照会します。</span><span class="sxs-lookup"><span data-stu-id="3f2cd-180">Now, query the BizTalkMsgBoxDb TrackingData_2_x tables again.</span></span> <span data-ttu-id="3f2cd-181">テーブルが空の場合は、データは、移動され、Application Insights での表示を開始する必要があります。</span><span class="sxs-lookup"><span data-stu-id="3f2cd-181">If the tables are empty, then the data was moved, and should start displaying in Application Insights.</span></span>
    
## <a name="see-also"></a><span data-ttu-id="3f2cd-182">参照</span><span class="sxs-lookup"><span data-stu-id="3f2cd-182">See also</span></span>
 [<span data-ttu-id="3f2cd-183">インストールして、機能パックを構成する.</span><span class="sxs-lookup"><span data-stu-id="3f2cd-183">Install & configure the Feature Pack</span></span>](../core/configure-the-feature-pack.md)