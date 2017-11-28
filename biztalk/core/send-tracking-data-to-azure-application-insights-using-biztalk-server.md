---
title: "BizTalk Server を使用して Azure Application Insights に追跡データを送信 |Microsoft ドキュメント"
ms.custom: 
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: 
ms.suite: 
ms.tgt_pltfrm: 
ms.topic: article
ms.assetid: b3ff6cb9-44d0-46cd-9b4f-a346365afb7b
caps.latest.revision: "10"
author: tordgladnordahl
ms.author: tonordah
manager: anneta
ms.openlocfilehash: f587c3049e191505c87ba456b5ddfd41011862c2
ms.sourcegitcommit: cb908c540d8f1a692d01dc8f313e16cb4b4e696d
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 09/20/2017
---
# <a name="send-tracking-data-to-azure-application-insights-using-biztalk-server"></a><span data-ttu-id="159da-102">BizTalk Server を使用して Azure Application Insights に追跡データを送信します。</span><span class="sxs-lookup"><span data-stu-id="159da-102">Send tracking data to Azure Application Insights using BizTalk Server</span></span>
<span data-ttu-id="159da-103">送信[!INCLUDE[btsBizTalkServerNoVersion_md](../includes/btsbiztalkservernoversion-md.md)]Azure アプリケーション Inisights にデータを追跡します。</span><span class="sxs-lookup"><span data-stu-id="159da-103">Send [!INCLUDE[btsBizTalkServerNoVersion_md](../includes/btsbiztalkservernoversion-md.md)] tracking data to Azure Application Inisights.</span></span> 

<span data-ttu-id="159da-104">**以降で[!INCLUDE[bts2016_md](../includes/bts2016-md.md)] [!INCLUDE[featurepack1](../includes/featurepack1.md)]**を処理し、追跡データを Azure Application Insights に送信することができます。</span><span class="sxs-lookup"><span data-stu-id="159da-104">**Starting with [!INCLUDE[bts2016_md](../includes/bts2016-md.md)] [!INCLUDE[featurepack1](../includes/featurepack1.md)]**, you can process and send your tracking data to Azure Application Insights.</span></span> <span data-ttu-id="159da-105">Application Insights の機能を使用すると、受信ポート、送信ポート、およびオーケストレーションからのインスタンスを追跡できます。</span><span class="sxs-lookup"><span data-stu-id="159da-105">Use the Application Insights features to track your instances from receive ports, send ports, and orchestrations.</span></span>

## <a name="prerequisites"></a><span data-ttu-id="159da-106">前提条件</span><span class="sxs-lookup"><span data-stu-id="159da-106">Prerequisites</span></span>
* <span data-ttu-id="159da-107">新しいインスタンスを作成する[Application Insights](https://docs.microsoft.com/en-us/azure/application-insights/app-insights-create-new-resource)</span><span class="sxs-lookup"><span data-stu-id="159da-107">Create a new instance of [Application Insights](https://docs.microsoft.com/en-us/azure/application-insights/app-insights-create-new-resource)</span></span>
* <span data-ttu-id="159da-108">インストール[機能パック 1](https://www.microsoft.com/download/details.aspx?id=55100)で、[!INCLUDE[btsBizTalkServerNoVersion_md](../includes/btsbiztalkservernoversion-md.md)]</span><span class="sxs-lookup"><span data-stu-id="159da-108">Install [Feature Pack 1](https://www.microsoft.com/download/details.aspx?id=55100) on your [!INCLUDE[btsBizTalkServerNoVersion_md](../includes/btsbiztalkservernoversion-md.md)]</span></span>

## <a name="enable-analytics-for-your-environment"></a><span data-ttu-id="159da-109">環境の分析を有効にします。</span><span class="sxs-lookup"><span data-stu-id="159da-109">Enable analytics for your environment</span></span>

1. <span data-ttu-id="159da-110">開く、 **BizTalk Server 管理コンソール**コンソールで、 **BizTalk 管理コンソール**を右クリックし、 **BizTalk グループ**を選択して**の設定**.</span><span class="sxs-lookup"><span data-stu-id="159da-110">Open the **BizTalk Server Administration** console, expand **BizTalk Administration**, right-click the **BizTalk Group**, and select **Settings**.</span></span> 
2. <span data-ttu-id="159da-111">確認**グループ レベルの分析を有効にする**です。</span><span class="sxs-lookup"><span data-stu-id="159da-111">Check **Enable group-level analytics**.</span></span>
3. <span data-ttu-id="159da-112">**ターゲット型** **Application Insight**一覧からです。</span><span class="sxs-lookup"><span data-stu-id="159da-112">For the **Target type**, select **Application Insight** from the list.</span></span>
4. <span data-ttu-id="159da-113">**接続パラメーター**、入力、Application Insights **[インストルメンテーション キー](https://docs.microsoft.com/en-us/azure/application-insights/app-insights-create-new-resource)**  (Azure ポータルで使用可能)。</span><span class="sxs-lookup"><span data-stu-id="159da-113">For the **Connection parameters**, enter your Application Insights **[instrumentation key](https://docs.microsoft.com/en-us/azure/application-insights/app-insights-create-new-resource)** (available in the Azure portal).</span></span>

    <span data-ttu-id="159da-114">グループの設定は、次のようになります。</span><span class="sxs-lookup"><span data-stu-id="159da-114">Your Group settings look similar to the following:</span></span> 

    ![環境の分析を有効にします。](../core/media/environmentsettingapplicationinishgt.PNG)

5. <span data-ttu-id="159da-116">**[OK]** を選択して変更を保存します。</span><span class="sxs-lookup"><span data-stu-id="159da-116">Select **OK** to save your changes.</span></span> 

<span data-ttu-id="159da-117">有効にすると、 [!INCLUDE[btsBizTalkServerNoVersion_md](../includes/btsbiztalkservernoversion-md.md)] Application Insights にデータを送信する準備ができました。</span><span class="sxs-lookup"><span data-stu-id="159da-117">Once enabled, [!INCLUDE[btsBizTalkServerNoVersion_md](../includes/btsbiztalkservernoversion-md.md)] is ready to transmit data to Application Insights.</span></span> <span data-ttu-id="159da-118">次に、ポートやオーケストレーションに対する分析を有効にします。</span><span class="sxs-lookup"><span data-stu-id="159da-118">Next, enable analytics on your ports and orchestrations.</span></span> 

## <a name="enable-analytics-on-your-artifacts"></a><span data-ttu-id="159da-119">アイテムに対する分析を有効にします。</span><span class="sxs-lookup"><span data-stu-id="159da-119">Enable analytics on your artifacts</span></span>

1. <span data-ttu-id="159da-120">BizTalk Server 管理 を右クリックし、**受信ポート**、**送信ポート**または**オーケストレーション**を選択して**追跡**です。</span><span class="sxs-lookup"><span data-stu-id="159da-120">In BizTalk Server Administration, right-click a **receive port**, **send port** or **orchestration**, and select **Tracking**.</span></span>
2. <span data-ttu-id="159da-121">**Analytics**、確認**Analytics を有効にする**です。</span><span class="sxs-lookup"><span data-stu-id="159da-121">Under **Analytics**, check **Enable Analytics**.</span></span> <span data-ttu-id="159da-122">この設定は、追跡と Application Insights に成果物からのデータの送信を開始します。</span><span class="sxs-lookup"><span data-stu-id="159da-122">This setting starts tracking and transmitting data from the artifact to Application Insights.</span></span>

    <span data-ttu-id="159da-123">成果物の設定は、次のようになります。</span><span class="sxs-lookup"><span data-stu-id="159da-123">Your artifact settings look similar to the following:</span></span> 
    
    ![オーケストレーションの追跡データ](../core/media/orchestrationsettingsapplicationinsight.PNG)

3. <span data-ttu-id="159da-125">**[OK]** を選択して変更を保存します。</span><span class="sxs-lookup"><span data-stu-id="159da-125">Select **OK** to save your changes.</span></span>

<span data-ttu-id="159da-126">次に、データを見るための Application Insights 内のクエリを実行します。</span><span class="sxs-lookup"><span data-stu-id="159da-126">Next, run queries within Application Insights to see your data.</span></span>  

> [!TIP]
> <span data-ttu-id="159da-127">組織のデータをさらに多くの把握するためには、他のシステムと、BizTalk Server の分析結果を接続します。</span><span class="sxs-lookup"><span data-stu-id="159da-127">Connect your BizTalk Server Analytics with other systems to gain even more insight into your organizations data.</span></span>

## <a name="run-queries-on-your-data"></a><span data-ttu-id="159da-128">データに対するクエリを実行します。</span><span class="sxs-lookup"><span data-stu-id="159da-128">Run queries on your data</span></span>
<span data-ttu-id="159da-129">Application Insights にデータが送信されると、Azure 内で分析ツールを使用して、高度なクエリを作成し、データを分析できます。</span><span class="sxs-lookup"><span data-stu-id="159da-129">Once the data is sent to Application Insights, you can use the analytics tools within Azure to create advanced queries, and analyze your data.</span></span>

1. <span data-ttu-id="159da-130">サインイン、 [Azure ポータル](https://portal.azure.com)です。</span><span class="sxs-lookup"><span data-stu-id="159da-130">Sign in to the [Azure Portal](https://portal.azure.com).</span></span>
2. <span data-ttu-id="159da-131">Application Insights のリソースを開き、選択**Analytics**です。</span><span class="sxs-lookup"><span data-stu-id="159da-131">Open your Application Insights resource, and select **Analytics**.</span></span>
3. <span data-ttu-id="159da-132">選択**使用状況**、および指定したクエリを実行します。</span><span class="sxs-lookup"><span data-stu-id="159da-132">Select **usage**, and run the query provided.</span></span>

    > [!TIP]
    > <span data-ttu-id="159da-133">Application Insights でクエリを記述する方法の詳細について[Application Insights で分析](https://docs.microsoft.com/azure/application-insights/app-insights-analytics)です。</span><span class="sxs-lookup"><span data-stu-id="159da-133">Learn more about how to write queries in Application Insights at [Analytics in Application Insights](https://docs.microsoft.com/azure/application-insights/app-insights-analytics).</span></span>
    
## <a name="see-also"></a><span data-ttu-id="159da-134">参照</span><span class="sxs-lookup"><span data-stu-id="159da-134">See also</span></span>
 [<span data-ttu-id="159da-135">この機能パックを構成します。</span><span class="sxs-lookup"><span data-stu-id="159da-135">Configure the Feature Pack</span></span>](../core/configure-the-feature-pack.md)