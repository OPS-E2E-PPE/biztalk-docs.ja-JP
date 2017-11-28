---
title: "オペレーション データを BizTalk Server で Power BI にフィードの構成 |Microsoft ドキュメント"
ms.custom: 
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: 
ms.suite: 
ms.tgt_pltfrm: 
ms.topic: article
ms.assetid: fe6d3a97-c7c0-4147-baa9-ee12f93248eb
caps.latest.revision: "11"
author: tordgladnordahl
ms.author: tonordah
manager: anneta
ms.openlocfilehash: 09b1b1fd7f350e168b2bb13d6bee2e45c12d49cc
ms.sourcegitcommit: cb908c540d8f1a692d01dc8f313e16cb4b4e696d
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 09/20/2017
---
# <a name="configure-the-operational-data-feed-for-power-bi-with-biztalk-server"></a><span data-ttu-id="edc51-102">BizTalk Server で Power BI にフィード オペレーション データを構成します。</span><span class="sxs-lookup"><span data-stu-id="edc51-102">Configure the operational data feed for Power BI with BizTalk Server</span></span>
<span data-ttu-id="edc51-103">OData フィードによって提供されるオペレーション データを読み取る[!INCLUDE[btsBizTalkServerNoVersion_md](../includes/btsbiztalkservernoversion-md.md)]です。</span><span class="sxs-lookup"><span data-stu-id="edc51-103">Read operational data provided through an oData feed in [!INCLUDE[btsBizTalkServerNoVersion_md](../includes/btsbiztalkservernoversion-md.md)].</span></span> 

<span data-ttu-id="edc51-104">**以降で[!INCLUDE[bts2016_md](../includes/bts2016-md.md)] [!INCLUDE[featurepack1](../includes/featurepack1.md)]**追跡を指定すると、Power BI テンプレートを使用して Power BI に送信します。 または、独自に作成します。</span><span class="sxs-lookup"><span data-stu-id="edc51-104">**Starting with [!INCLUDE[bts2016_md](../includes/bts2016-md.md)] [!INCLUDE[featurepack1](../includes/featurepack1.md)]**, send tracking to Power BI using the Power BI template provided, or create your own.</span></span> 

## <a name="what-is-operational-data"></a><span data-ttu-id="edc51-105">オペレーション データとは</span><span class="sxs-lookup"><span data-stu-id="edc51-105">What is operational data</span></span>
<span data-ttu-id="edc51-106">オペレーション データは、インスタンスおよび経由でやり取りされるメッセージに関する情報、[!INCLUDE[btsBizTalkServerNoVersion_md](../includes/btsbiztalkservernoversion-md.md)]環境。</span><span class="sxs-lookup"><span data-stu-id="edc51-106">Operational data is information on the instances and messages flowing through your [!INCLUDE[btsBizTalkServerNoVersion_md](../includes/btsbiztalkservernoversion-md.md)] environment.</span></span> <span data-ttu-id="edc51-107">オペレーション データ フィードは、同じデータのグループ ハブを見ることの取得、[!INCLUDE[btsBizTalkServerAdminConsoleui_md](../includes/btsbiztalkserveradminconsoleui-md.md)]コンソールです。</span><span class="sxs-lookup"><span data-stu-id="edc51-107">The operational data feed is the same data you get looking at Group Hub in the [!INCLUDE[btsBizTalkServerAdminConsoleui_md](../includes/btsbiztalkserveradminconsoleui-md.md)] console.</span></span> <span data-ttu-id="edc51-108">データにアクセスできるし、Power BI を含む視覚化ツールを使用してクエリを実行します。</span><span class="sxs-lookup"><span data-stu-id="edc51-108">The data can be accessed and queried using visualization tools, including Power BI.</span></span> 

<span data-ttu-id="edc51-109">フィードには、次のデータ テーブルが含まれています。</span><span class="sxs-lookup"><span data-stu-id="edc51-109">The feed includes the following data tables:</span></span>
* <span data-ttu-id="edc51-110">アプリケーション データ</span><span class="sxs-lookup"><span data-stu-id="edc51-110">Application data</span></span>
* <span data-ttu-id="edc51-111">AS2 状態レコード</span><span class="sxs-lookup"><span data-stu-id="edc51-111">AS2 Status Records</span></span>
* <span data-ttu-id="edc51-112">バッチ処理の情報</span><span class="sxs-lookup"><span data-stu-id="edc51-112">Batching information</span></span>
* <span data-ttu-id="edc51-113">インスタンス情報</span><span class="sxs-lookup"><span data-stu-id="edc51-113">Instance information</span></span>
* <span data-ttu-id="edc51-114">インターチェンジの集計レコード</span><span class="sxs-lookup"><span data-stu-id="edc51-114">Interchange Aggregations Records</span></span>
* <span data-ttu-id="edc51-115">インターチェンジの状態レコード</span><span class="sxs-lookup"><span data-stu-id="edc51-115">Interchange Status Records</span></span>
* <span data-ttu-id="edc51-116">メッセージ</span><span class="sxs-lookup"><span data-stu-id="edc51-116">Messages</span></span>
* <span data-ttu-id="edc51-117">サブスクリプション</span><span class="sxs-lookup"><span data-stu-id="edc51-117">Subscriptions</span></span>
* <span data-ttu-id="edc51-118">追跡イベント</span><span class="sxs-lookup"><span data-stu-id="edc51-118">Tracked Events</span></span>
* <span data-ttu-id="edc51-119">トランザクションのレポート</span><span class="sxs-lookup"><span data-stu-id="edc51-119">Transaction reports</span></span>
* <span data-ttu-id="edc51-120">トランザクション セット</span><span class="sxs-lookup"><span data-stu-id="edc51-120">Transaction sets</span></span>

> [!TIP]
> <span data-ttu-id="edc51-121">[PowerBI.com](http://powerbi.microsoft.com)を理解し、Power BI の詳細です。</span><span class="sxs-lookup"><span data-stu-id="edc51-121">[PowerBI.com](http://powerbi.microsoft.com) is a great resource to understand and learn more about Power BI.</span></span>

## <a name="prerequisites"></a><span data-ttu-id="edc51-122">前提条件</span><span class="sxs-lookup"><span data-stu-id="edc51-122">Prerequisites</span></span>
* <span data-ttu-id="edc51-123">ダウンロードしてインストール[Power BI Desktop](https://powerbi.microsoft.com/desktop/)ネットワーク アクセス権を持つ任意のコンピューターで、[!INCLUDE[btsBizTalkServerNoVersion_md](../includes/btsbiztalkservernoversion-md.md)]</span><span class="sxs-lookup"><span data-stu-id="edc51-123">Download and install [Power BI Desktop](https://powerbi.microsoft.com/desktop/) on any computer that has network access to your [!INCLUDE[btsBizTalkServerNoVersion_md](../includes/btsbiztalkservernoversion-md.md)]</span></span>
* <span data-ttu-id="edc51-124">インストール[機能パック 1](https://www.microsoft.com/download/details.aspx?id=55100)で、[!INCLUDE[btsBizTalkServerNoVersion_md](../includes/btsbiztalkservernoversion-md.md)]</span><span class="sxs-lookup"><span data-stu-id="edc51-124">Install [Feature Pack 1](https://www.microsoft.com/download/details.aspx?id=55100) on your [!INCLUDE[btsBizTalkServerNoVersion_md](../includes/btsbiztalkservernoversion-md.md)]</span></span>
* <span data-ttu-id="edc51-125">IIS をインストール、[!INCLUDE[btsBizTalkServerNoVersion_md](../includes/btsbiztalkservernoversion-md.md)]です。</span><span class="sxs-lookup"><span data-stu-id="edc51-125">Install IIS on the [!INCLUDE[btsBizTalkServerNoVersion_md](../includes/btsbiztalkservernoversion-md.md)].</span></span> <span data-ttu-id="edc51-126">ほとんどの[!INCLUDE[btsBizTalkServerNoVersion_md](../includes/btsbiztalkservernoversion-md.md)]環境では、IIS が既にインストールされています。</span><span class="sxs-lookup"><span data-stu-id="edc51-126">In most [!INCLUDE[btsBizTalkServerNoVersion_md](../includes/btsbiztalkservernoversion-md.md)] environments, IIS is already installed.</span></span> <span data-ttu-id="edc51-127">参照してください[Hardware and Software Requirements for BizTalk Server 2016](../install-and-config-guides/hardware-and-software-requirements-for-biztalk-server-2016.md)です。</span><span class="sxs-lookup"><span data-stu-id="edc51-127">See [Hardware and Software Requirements for BizTalk Server 2016](../install-and-config-guides/hardware-and-software-requirements-for-biztalk-server-2016.md).</span></span> 

## <a name="enable-operational-data-feed"></a><span data-ttu-id="edc51-128">運用上のデータ フィードを有効にします。</span><span class="sxs-lookup"><span data-stu-id="edc51-128">Enable operational data feed</span></span>

1. <span data-ttu-id="edc51-129">Windows PowerShell を管理者として実行 (**開始**メニューで、「 **PowerShell**、右クリックし、、選択**管理者として実行**)。</span><span class="sxs-lookup"><span data-stu-id="edc51-129">Run Windows PowerShell as Administrator (**Start** menu, type **PowerShell**, right click, and select **Run as administrator**).</span></span> 
2. <span data-ttu-id="edc51-130">フォルダーを参照場所[!INCLUDE[bts2016_md](../includes/bts2016-md.md)]がインストールされている**Program Files (x86)/microsoft BizTalk Server 2016**</span><span class="sxs-lookup"><span data-stu-id="edc51-130">Browse to the folder where [!INCLUDE[bts2016_md](../includes/bts2016-md.md)] is installed **Program Files (x86)/Microsoft BizTalk Server 2016**</span></span>
3. <span data-ttu-id="edc51-131">次のコマンドを実行します。</span><span class="sxs-lookup"><span data-stu-id="edc51-131">Run the following command.</span></span> <span data-ttu-id="edc51-132">更新してください、 `website`、 `domain\user`、 `password`、および`domain\group`実際の値にします。</span><span class="sxs-lookup"><span data-stu-id="edc51-132">Be sure to update your `website`, `domain\user`, `password`, and `domain\group` with your values:</span></span> 

    ```Powershell
    FeaturePack.ConfigureServices.ps1 -Service operationaldata -WebSiteName '<Default Web Site>' -ApplicationPool <operationalDataServiceAppPool> -ApplicationPoolUser <domain>\<user> -ApplicationPoolUserPassword <password> -AuthorizationRoles '<domain>\<group1>, <domain>\<group2>'
    ```
4. <span data-ttu-id="edc51-133">スクリプトを実行した後は、新しい IIS アプリケーションを参照してください。</span><span class="sxs-lookup"><span data-stu-id="edc51-133">After you run the script, browse the new IIS Application:</span></span>  
    1. <span data-ttu-id="edc51-134">Web ブラウザーを開きます</span><span class="sxs-lookup"><span data-stu-id="edc51-134">Open your web browser</span></span>
    2. <span data-ttu-id="edc51-135">移動して**http://localhost/BizTalkOperationalDataService**</span><span class="sxs-lookup"><span data-stu-id="edc51-135">Go to **http://localhost/BizTalkOperationalDataService**</span></span>

## <a name="use-the-power-bi-template"></a><span data-ttu-id="edc51-136">Power BI テンプレートを使用します。</span><span class="sxs-lookup"><span data-stu-id="edc51-136">Use the Power BI template</span></span>
<span data-ttu-id="edc51-137">Power BI テンプレート ファイルにアクセスし、Microsoft から提供されている視覚エフェクトを使用するには、次の手順を使用します。</span><span class="sxs-lookup"><span data-stu-id="edc51-137">To access the Power BI Template file, and use the provided visualization from Microsoft, use the following steps:</span></span>

1. <span data-ttu-id="edc51-138">ダウンロードしてインストール、 [Power BI Desktop](https://powerbi.microsoft.com/desktop/)です。</span><span class="sxs-lookup"><span data-stu-id="edc51-138">Download and install the [Power BI Desktop](https://powerbi.microsoft.com/desktop/).</span></span>
2. <span data-ttu-id="edc51-139">BizTalk Server フォルダーの下を参照**%program Files (x86) \Microsoft BizTalk Server 2016\OperationalDataService**です。</span><span class="sxs-lookup"><span data-stu-id="edc51-139">Browse to your BizTalk Server folder under **Program Files (x86)\Microsoft BizTalk Server 2016\OperationalDataService**.</span></span>
3. <span data-ttu-id="edc51-140">開く、 **BizTalkOperationalData.pbit**ファイル。</span><span class="sxs-lookup"><span data-stu-id="edc51-140">Open the **BizTalkOperationalData.pbit** file.</span></span>
4. <span data-ttu-id="edc51-141">Power BI からメッセージが表示されたら、貼り付け、 **http://localhost/\<yourWebSite\>**  OData フィード用に作成した URL です。</span><span class="sxs-lookup"><span data-stu-id="edc51-141">When prompted from Power BI, paste the **http://localhost/\<yourWebSite\>** URL that you created for your OData feed.</span></span> <span data-ttu-id="edc51-142">たとえば、入力**http://localhost/OperationalDataService**です。</span><span class="sxs-lookup"><span data-stu-id="edc51-142">For example, enter **http://localhost/OperationalDataService**.</span></span> 

    <span data-ttu-id="edc51-143">URL は、次のようにはなります。</span><span class="sxs-lookup"><span data-stu-id="edc51-143">Your URL looks similar to the following:</span></span> 
    
    ![Power BI テンプレート ファイルへの OData URL を貼り付けます](../core/media/pasteurltopowerbitempaltefile.PNG)

5. <span data-ttu-id="edc51-145">選択**ロード**Power BI レポート内のフィールドに入力します。</span><span class="sxs-lookup"><span data-stu-id="edc51-145">Select **Load** to populate the fields in your Power BI report.</span></span> 
6. <span data-ttu-id="edc51-146">テンプレート ファイルでは、OData フィードから、情報と使用可能なテーブルが自動的に生成されます。</span><span class="sxs-lookup"><span data-stu-id="edc51-146">The Template file automatically generates the information and tables available from the OData feed.</span></span>

<span data-ttu-id="edc51-147">オペレーション データ、コンピューターによって公開されることができますアクセスおよび権限に基づいて他のアプリケーションによって実行されます。</span><span class="sxs-lookup"><span data-stu-id="edc51-147">The operational data is exposed through the computer, and can be accessed and executed by other applications based on permissions.</span></span> 

<span data-ttu-id="edc51-148">Power BI、およびレポート オンライン ジャンプを公開する方法の詳細について[PowerBI.com](http://powerbi.microsoft.com)</span><span class="sxs-lookup"><span data-stu-id="edc51-148">To learn more about Power BI, and how to publish the report online go to [PowerBI.com](http://powerbi.microsoft.com)</span></span>

## <a name="see-also"></a><span data-ttu-id="edc51-149">参照</span><span class="sxs-lookup"><span data-stu-id="edc51-149">See also</span></span>

[<span data-ttu-id="edc51-150">Power BI を詳細します。</span><span class="sxs-lookup"><span data-stu-id="edc51-150">Learn more about Power BI</span></span>](https://www.powerbi.com)  
[<span data-ttu-id="edc51-151">この機能パックを構成します。</span><span class="sxs-lookup"><span data-stu-id="edc51-151">Configure the Feature Pack</span></span>](../core/configure-the-feature-pack.md)