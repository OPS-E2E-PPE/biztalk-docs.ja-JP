---
title: "追跡データを Azure Application Insights に送信 |Microsoft ドキュメント"
description: "BizTalk Server で Azure Application Insights による追跡データの分析を有効にする feature pack をインストールします。"
ms.custom: fp1
ms.date: 11/06/2017
ms.prod: biztalk-server
ms.reviewer: 
ms.suite: 
ms.tgt_pltfrm: 
ms.topic: article
ms.assetid: b3ff6cb9-44d0-46cd-9b4f-a346365afb7b
caps.latest.revision: "10"
author: tordgladnordahl
ms.author: mandia
manager: anneta
ms.openlocfilehash: 4a65ffd2c5ee76d857effde6ab82dddf17b3de4b
ms.sourcegitcommit: 30189176c44873e3de42cc5f2b8951da51ffd251
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 11/07/2017
---
# <a name="send-tracking-data-to-azure-application-insights-using-biztalk-server"></a><span data-ttu-id="92186-103">BizTalk Server を使用して Azure Application Insights に追跡データを送信します。</span><span class="sxs-lookup"><span data-stu-id="92186-103">Send tracking data to Azure Application Insights using BizTalk Server</span></span>

<span data-ttu-id="92186-104">**以降で[!INCLUDE[bts2016_md](../includes/bts2016-md.md)] [!INCLUDE[featurepack1](../includes/featurepack1.md)]**を処理し、追跡データを Azure Application Insights に送信することができます。</span><span class="sxs-lookup"><span data-stu-id="92186-104">**Starting with [!INCLUDE[bts2016_md](../includes/bts2016-md.md)] [!INCLUDE[featurepack1](../includes/featurepack1.md)]**, you can process and send your tracking data to Azure Application Insights.</span></span> <span data-ttu-id="92186-105">Application Insights の機能を使用すると、受信ポート、送信ポート、およびオーケストレーションからのインスタンスを追跡できます。</span><span class="sxs-lookup"><span data-stu-id="92186-105">Use the Application Insights features to track your instances from receive ports, send ports, and orchestrations.</span></span>
          
> [!IMPORTANT]
> <span data-ttu-id="92186-106">この機能は、現在、という名前の SQL インスタンスでは使用されません。</span><span class="sxs-lookup"><span data-stu-id="92186-106">This feature currently does not work with SQL Named Instances.</span></span>

## <a name="prerequisites"></a><span data-ttu-id="92186-107">前提条件</span><span class="sxs-lookup"><span data-stu-id="92186-107">Prerequisites</span></span>
* <span data-ttu-id="92186-108">新しいインスタンスを作成する[Application Insights](https://docs.microsoft.com/azure/application-insights/app-insights-create-new-resource)です。</span><span class="sxs-lookup"><span data-stu-id="92186-108">Create a new instance of [Application Insights](https://docs.microsoft.com/azure/application-insights/app-insights-create-new-resource).</span></span> <span data-ttu-id="92186-109">そのプロパティでは、コピー、**インストルメンテーション キー**です。</span><span class="sxs-lookup"><span data-stu-id="92186-109">In its properties, copy the **Instrumentation Key**.</span></span> <span data-ttu-id="92186-110">準備する必要は、別のファイルに貼り付けます。</span><span class="sxs-lookup"><span data-stu-id="92186-110">Paste it in another file so you have it ready.</span></span> <span data-ttu-id="92186-111">BizTalk Server 内でこのキーを使用します。</span><span class="sxs-lookup"><span data-stu-id="92186-111">We use this key within BizTalk Server.</span></span> 
* <span data-ttu-id="92186-112">インストール[機能パック 1](https://www.microsoft.com/download/details.aspx?id=55100)で、[!INCLUDE[btsBizTalkServerNoVersion_md](../includes/btsbiztalkservernoversion-md.md)]</span><span class="sxs-lookup"><span data-stu-id="92186-112">Install [Feature Pack 1](https://www.microsoft.com/download/details.aspx?id=55100) on your [!INCLUDE[btsBizTalkServerNoVersion_md](../includes/btsbiztalkservernoversion-md.md)]</span></span>

## <a name="enable-analytics-for-your-environment"></a><span data-ttu-id="92186-113">環境の分析を有効にします。</span><span class="sxs-lookup"><span data-stu-id="92186-113">Enable analytics for your environment</span></span>

1. <span data-ttu-id="92186-114">開く、 **BizTalk Server 管理コンソール**コンソールで、右クリックし、 **BizTalk グループ**を選択して**設定**です。</span><span class="sxs-lookup"><span data-stu-id="92186-114">Open the **BizTalk Server Administration** console, right-click the **BizTalk Group**, and select **Settings**.</span></span> 
2. <span data-ttu-id="92186-115">確認**グループ レベルの分析を有効にする**です。</span><span class="sxs-lookup"><span data-stu-id="92186-115">Check **Enable group-level analytics**.</span></span>
3. <span data-ttu-id="92186-116">**ターゲット型** **Application Insight**一覧からです。</span><span class="sxs-lookup"><span data-stu-id="92186-116">For the **Target type**, select **Application Insight** from the list.</span></span>
4. <span data-ttu-id="92186-117">**接続パラメーター**、入力、Application Insights **[インストルメンテーション キー](https://docs.microsoft.com/en-us/azure/application-insights/app-insights-create-new-resource)**  (Azure ポータルで使用可能)。</span><span class="sxs-lookup"><span data-stu-id="92186-117">For the **Connection parameters**, enter your Application Insights **[instrumentation key](https://docs.microsoft.com/en-us/azure/application-insights/app-insights-create-new-resource)** (available in the Azure portal).</span></span> <span data-ttu-id="92186-118">グループの設定は、次のようになります。</span><span class="sxs-lookup"><span data-stu-id="92186-118">Your Group settings look similar to the following:</span></span> 

    ![環境の分析を有効にします。](../core/media/environmentsettingapplicationinishgt.PNG)

5. <span data-ttu-id="92186-120">**[OK]** を選択して変更を保存します。</span><span class="sxs-lookup"><span data-stu-id="92186-120">Select **OK** to save your changes.</span></span> 

<span data-ttu-id="92186-121">有効にすると、 [!INCLUDE[btsBizTalkServerNoVersion_md](../includes/btsbiztalkservernoversion-md.md)] Application Insights にデータを送信する準備ができました。</span><span class="sxs-lookup"><span data-stu-id="92186-121">Once enabled, [!INCLUDE[btsBizTalkServerNoVersion_md](../includes/btsbiztalkservernoversion-md.md)] is ready to transmit data to Application Insights.</span></span> <span data-ttu-id="92186-122">次に、ポートやオーケストレーションに対する分析を有効にします。</span><span class="sxs-lookup"><span data-stu-id="92186-122">Next, enable analytics on your ports and orchestrations.</span></span> 

## <a name="enable-analytics-on-your-artifacts"></a><span data-ttu-id="92186-123">アイテムに対する分析を有効にします。</span><span class="sxs-lookup"><span data-stu-id="92186-123">Enable analytics on your artifacts</span></span>

1. <span data-ttu-id="92186-124">BizTalk Server 管理 を右クリックし、**受信ポート**、**送信ポート**または**オーケストレーション**を選択して**追跡**です。</span><span class="sxs-lookup"><span data-stu-id="92186-124">In BizTalk Server Administration, right-click a **receive port**, **send port** or **orchestration**, and select **Tracking**.</span></span>
2. <span data-ttu-id="92186-125">**分析**、確認**Analytics を有効にする**次のようなです。</span><span class="sxs-lookup"><span data-stu-id="92186-125">Under **Analytics**, check **Enable Analytics**, similar to the following.</span></span> <span data-ttu-id="92186-126">この設定は、追跡と Application Insights に成果物からのデータの送信を開始します。</span><span class="sxs-lookup"><span data-stu-id="92186-126">This setting starts tracking and transmitting data from the artifact to Application Insights.</span></span>
    
    ![オーケストレーションの追跡データ](../core/media/orchestrationsettingsapplicationinsight.PNG)

3. <span data-ttu-id="92186-128">**[OK]** を選択して変更を保存します。</span><span class="sxs-lookup"><span data-stu-id="92186-128">Select **OK** to save your changes.</span></span>
4. <span data-ttu-id="92186-129">追跡ホスト インスタンスを再起動し、BizTalk アプリケーションが開始されたことを確認します。</span><span class="sxs-lookup"><span data-stu-id="92186-129">Restart the tracking host Instance, and confirm the BizTalk Application is started.</span></span>

<span data-ttu-id="92186-130">次に、データを見るための Application Insights 内のクエリを実行します。</span><span class="sxs-lookup"><span data-stu-id="92186-130">Next, run queries within Application Insights to see your data.</span></span>  

> [!TIP]
> <span data-ttu-id="92186-131">組織のデータをさらに多くの把握するためには、他のシステムと、BizTalk Server の分析結果を接続します。</span><span class="sxs-lookup"><span data-stu-id="92186-131">Connect your BizTalk Server Analytics with other systems to gain even more insight into your organizations data.</span></span>

## <a name="view-your-data"></a><span data-ttu-id="92186-132">データを表示します。</span><span class="sxs-lookup"><span data-stu-id="92186-132">View your data</span></span>
<span data-ttu-id="92186-133">Application Insights にデータが送信されると、Azure 内で分析ツールを使用して、高度なクエリを作成し、データを分析できます。</span><span class="sxs-lookup"><span data-stu-id="92186-133">Once the data is sent to Application Insights, you can use the analytics tools within Azure to create advanced queries, and analyze your data.</span></span>

1. <span data-ttu-id="92186-134">サインイン、 [Azure ポータル](https://portal.azure.com)です。</span><span class="sxs-lookup"><span data-stu-id="92186-134">Sign in to the [Azure Portal](https://portal.azure.com).</span></span>
2. <span data-ttu-id="92186-135">Application Insights のリソースを開き、選択**メトリックス エクスプ ローラー**です。</span><span class="sxs-lookup"><span data-stu-id="92186-135">Open your Application Insights resource, and select **Metrics Explorer**.</span></span>
3. <span data-ttu-id="92186-136">空のグラフが表示されます。</span><span class="sxs-lookup"><span data-stu-id="92186-136">Empty charts may display.</span></span> <span data-ttu-id="92186-137">グラフでは、次のように選択します。**編集**です。</span><span class="sxs-lookup"><span data-stu-id="92186-137">In a chart, select **Edit**.</span></span> <span data-ttu-id="92186-138">**メトリック****カスタム**使用の追跡対象のプロパティを表示します。</span><span class="sxs-lookup"><span data-stu-id="92186-138">Under **Metrics**, select **Custom** to see the available tracked properties.</span></span> <span data-ttu-id="92186-139">グラフに変更を表示するさまざまなオプションを選択します。</span><span class="sxs-lookup"><span data-stu-id="92186-139">Select some of the different options to see the changes on your chart:</span></span> 

    ![Azure の分析](../core/media/azure-stream-metrics-custom.png)

4. <span data-ttu-id="92186-141">戻り、Application Insights のリソースを選択して**Analytics**です。</span><span class="sxs-lookup"><span data-stu-id="92186-141">Go back to your Application Insights resource, and select **Analytics**.</span></span> <span data-ttu-id="92186-142">**使用状況****実行**です。</span><span class="sxs-lookup"><span data-stu-id="92186-142">In **Usage**, select **Run**.</span></span> <span data-ttu-id="92186-143">サンプル クエリが実行され、結果がグラフに表示されます。</span><span class="sxs-lookup"><span data-stu-id="92186-143">A sample query is executed, and the results are displayed in a chart.</span></span>  

> [!TIP]
> <span data-ttu-id="92186-144">Azure の Application Insights は、強力なツールです。</span><span class="sxs-lookup"><span data-stu-id="92186-144">Azure Application Insights is a powerful tool.</span></span> <span data-ttu-id="92186-145">Application Insights でのクエリを作成するのに役立つリソースがある[Application Insights で分析](https://docs.microsoft.com/azure/application-insights/app-insights-analytics)とで作業を開始する場合でも[Application Insights とは?](https://docs.microsoft.com/en-us/azure/application-insights/app-insights-overview)です。</span><span class="sxs-lookup"><span data-stu-id="92186-145">There are resources to help you write queries in Application Insights at [Analytics in Application Insights](https://docs.microsoft.com/azure/application-insights/app-insights-analytics), and even to get started at [What is Application Insights?](https://docs.microsoft.com/en-us/azure/application-insights/app-insights-overview).</span></span>

## <a name="where-the-data-is-stored"></a><span data-ttu-id="92186-146">データの格納場所</span><span class="sxs-lookup"><span data-stu-id="92186-146">Where the data is stored</span></span>

<span data-ttu-id="92186-147">Application Insights 内で、非常に早く (、数分以内)、追跡データが表示されます。</span><span class="sxs-lookup"><span data-stu-id="92186-147">Your tracking data should display fairly quickly (within a few minutes) within Application Insights.</span></span> <span data-ttu-id="92186-148">しない場合、追跡ホストの問題があります。</span><span class="sxs-lookup"><span data-stu-id="92186-148">If it doesn't, then there may be an issue with the tracking host.</span></span> <span data-ttu-id="92186-149">SQL Server で分析データは、TrackingData_2_ で、BizTalkMsgBoxDb データベースに格納*x*テーブル。</span><span class="sxs-lookup"><span data-stu-id="92186-149">In SQL Server, the Analytics data is stored in the BizTalkMsgBoxDb database, in the TrackingData_2_*x* tables.</span></span> <span data-ttu-id="92186-150">SQL Server Management Studio では、これら 4 つのテーブルで上位 1000 行を返します。</span><span class="sxs-lookup"><span data-stu-id="92186-150">In SQL Server Management Studio, return the top 1000 rows on these four tables.</span></span> <span data-ttu-id="92186-151">データが存在する場合、追跡ホストに移行しないデータ、BizTalkDTADb データベース。</span><span class="sxs-lookup"><span data-stu-id="92186-151">If the data is there, then the tracking host is not moving the data to the BizTalkDTADb database.</span></span> 

<span data-ttu-id="92186-152">いくつか考えられる解決策:</span><span class="sxs-lookup"><span data-stu-id="92186-152">Some possible resolutions:</span></span>

1. <span data-ttu-id="92186-153">追跡ホストを再起動します。</span><span class="sxs-lookup"><span data-stu-id="92186-153">Restart the tracking host.</span></span>
2. <span data-ttu-id="92186-154">専用の追跡ホストを作成します。</span><span class="sxs-lookup"><span data-stu-id="92186-154">Create a dedicated tracking host.</span></span> <span data-ttu-id="92186-155">追跡を有効にすることがあります BizTalk Server がインストールされているときに、 **BizTalk Server アプリケーション 1**ホストします。</span><span class="sxs-lookup"><span data-stu-id="92186-155">When BizTalk Server is installed, tracking may be enabled on the **BizTalk Server Application 1** host.</span></span> <span data-ttu-id="92186-156">通常、このアプリケーションは、メッセージの処理にも使用されます。</span><span class="sxs-lookup"><span data-stu-id="92186-156">Typically, this application is also used to process messages.</span></span> <span data-ttu-id="92186-157">次の手順を使用して、専用の追跡ホストを作成します。</span><span class="sxs-lookup"><span data-stu-id="92186-157">Create a dedicated tracking host using the following steps:</span></span> 

    1. <span data-ttu-id="92186-158">BizTalk Server 管理コンソールで、BizTalk Server アプリケーション 1 ホストのプロパティを開き、オフにして**ホストの追跡を許可する**です。</span><span class="sxs-lookup"><span data-stu-id="92186-158">In BizTalk Server Administration, open the properties of the BizTalk Server Application 1 host, and uncheck **Allow Host Tracking**.</span></span> <span data-ttu-id="92186-159">このホスト インスタンスを再起動します。</span><span class="sxs-lookup"><span data-stu-id="92186-159">Restart this host instance.</span></span>

    2. <span data-ttu-id="92186-160">という名前の新しいホストを作成する**追跡**、し確認**ホストの追跡を許可する**です。</span><span class="sxs-lookup"><span data-stu-id="92186-160">Create a new host named **Tracking**, and check **Allow Host Tracking**.</span></span> <span data-ttu-id="92186-161">ホスト インスタンスを作成し、それを開始します。</span><span class="sxs-lookup"><span data-stu-id="92186-161">Create a host instance, and start it.</span></span>

<span data-ttu-id="92186-162">ここで、もう一度 BizTalkMsgBoxDb TrackingData_2_x テーブルを照会します。</span><span class="sxs-lookup"><span data-stu-id="92186-162">Now, query the BizTalkMsgBoxDb TrackingData_2_x tables again.</span></span> <span data-ttu-id="92186-163">テーブルが空の場合は、データは、移動され、Application Insights での表示を開始する必要があります。</span><span class="sxs-lookup"><span data-stu-id="92186-163">If the tables are empty, then the data was moved, and should start displaying in Application Insights.</span></span>
    
## <a name="see-also"></a><span data-ttu-id="92186-164">参照</span><span class="sxs-lookup"><span data-stu-id="92186-164">See also</span></span>
 [<span data-ttu-id="92186-165">この機能パックを構成します。</span><span class="sxs-lookup"><span data-stu-id="92186-165">Configure the Feature Pack</span></span>](../core/configure-the-feature-pack.md)