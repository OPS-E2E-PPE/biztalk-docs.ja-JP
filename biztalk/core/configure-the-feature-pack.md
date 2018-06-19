---
title: Feature pack の構成 |Microsoft ドキュメント
description: インストールし 1, 用 feature pack を構成および機能パック 2 です。 新しい機能の一覧から、API Management、team services デプロイメント、Azure に新しいアダプター、バックアップなど、BizTalk Server 2016 での詳細を参照してください。
ms.custom: ''
ms.date: 11/22/2017
ms.prod: biztalk-server
ms.reviewer: ''
ms.suite: ''
ms.tgt_pltfrm: ''
ms.topic: article
ms.assetid: 1027bfa6-49b9-4f58-a2e2-3e0ae2fc3bf3
caps.latest.revision: 15
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: e5b4164cf1f1355ab9a0d2f350aa5b3b5ce411e0
ms.sourcegitcommit: f4c0d7bc4b617688c643101a34062db90014851a
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 11/23/2017
ms.locfileid: "25550761"
---
# <a name="configure-the-feature-pack"></a><span data-ttu-id="77688-104">この機能パックを構成します。</span><span class="sxs-lookup"><span data-stu-id="77688-104">Configure the feature pack</span></span>

## <a name="overview"></a><span data-ttu-id="77688-105">概要</span><span class="sxs-lookup"><span data-stu-id="77688-105">Overview</span></span>

[!INCLUDE[btsBizTalkServerNoVersion_md](../includes/btsbiztalkservernoversion-md.md)]<span data-ttu-id="77688-106">feature pack を使用して、機能強化、機能、および Azure でよくの統合を提供します。</span><span class="sxs-lookup"><span data-stu-id="77688-106"> uses feature packs to provide improvements, features, and closer integration with Azure.</span></span> <span data-ttu-id="77688-107">これらの機能パックは、展開、セキュリティ、分析、ランタイム、およびバックアップなど、重要な分野の機能を拡張します。</span><span class="sxs-lookup"><span data-stu-id="77688-107">These feature packs extend functionality in key areas, such as deployment, security, analytics, runtime, and backup.</span></span> 

> [!NOTE]
> <span data-ttu-id="77688-108">Feature pack の Enterprise および Developer エディションで使用可能な[!INCLUDE[bts2016_md](../includes/bts2016-md.md)]とき。</span><span class="sxs-lookup"><span data-stu-id="77688-108">The feature packs are available with the Enterprise and Developer editions of [!INCLUDE[bts2016_md](../includes/bts2016-md.md)] when:</span></span> 
> 
> - <span data-ttu-id="77688-109">Software Assurance (SA) で使用または</span><span class="sxs-lookup"><span data-stu-id="77688-109">Used with Software Assurance (SA), OR</span></span>
> - <span data-ttu-id="77688-110">実行している[!INCLUDE[btsBizTalkServerNoVersion_md](../includes/btsbiztalkservernoversion-md.md)]Enterprise Agreement を使用して azure</span><span class="sxs-lookup"><span data-stu-id="77688-110">Running [!INCLUDE[btsBizTalkServerNoVersion_md](../includes/btsbiztalkservernoversion-md.md)] in Azure using an Enterprise Agreement</span></span>
> 
> <span data-ttu-id="77688-111">Feature pack がそれ以外のご利用いただけません[!INCLUDE[btsBizTalkServerNoVersion_md](../includes/btsbiztalkservernoversion-md.md)]edition、またはその他の[!INCLUDE[btsBizTalkServerNoVersion_md](../includes/btsbiztalkservernoversion-md.md)]バージョン。</span><span class="sxs-lookup"><span data-stu-id="77688-111">The feature packs are not available for any other [!INCLUDE[btsBizTalkServerNoVersion_md](../includes/btsbiztalkservernoversion-md.md)] edition, or any other [!INCLUDE[btsBizTalkServerNoVersion_md](../includes/btsbiztalkservernoversion-md.md)] version.</span></span> 

## <a name="download-and-install"></a><span data-ttu-id="77688-112">ダウンロードしてインストールする</span><span class="sxs-lookup"><span data-stu-id="77688-112">Download and install</span></span>

<span data-ttu-id="77688-113">Feature pack は累積されます。</span><span class="sxs-lookup"><span data-stu-id="77688-113">The feature packs are cumulative.</span></span> <span data-ttu-id="77688-114">ように feature pack 2 をインストールするときに取得することも、機能と更新プログラム機能パック 1 でします。</span><span class="sxs-lookup"><span data-stu-id="77688-114">So when you install feature pack 2, you also get the features and updates in feature pack 1.</span></span>

* <span data-ttu-id="77688-115">ダウンロード、 [!INCLUDE[bts2016_md](../includes/bts2016-md.md)] [Feature Pack 2](https://aka.ms/bts2016fp2)です。</span><span class="sxs-lookup"><span data-stu-id="77688-115">Download the [!INCLUDE[bts2016_md](../includes/bts2016-md.md)] [Feature Pack 2](https://aka.ms/bts2016fp2).</span></span>

* <span data-ttu-id="77688-116">ダウンロード、 [!INCLUDE[bts2016_md](../includes/bts2016-md.md)] [機能パック 1](https://www.microsoft.com/download/details.aspx?id=55100)です。</span><span class="sxs-lookup"><span data-stu-id="77688-116">Download the [!INCLUDE[bts2016_md](../includes/bts2016-md.md)] [Feature Pack 1](https://www.microsoft.com/download/details.aspx?id=55100).</span></span>

#### <a name="install"></a><span data-ttu-id="77688-117">Install</span><span class="sxs-lookup"><span data-stu-id="77688-117">Install</span></span>

1. <span data-ttu-id="77688-118">セットアップを管理者として実行します。</span><span class="sxs-lookup"><span data-stu-id="77688-118">Run setup as administrator.</span></span>
2. <span data-ttu-id="77688-119">**へようこそ]**[**次**です。</span><span class="sxs-lookup"><span data-stu-id="77688-119">In **Welcome**, select **Next**.</span></span> 
3. <span data-ttu-id="77688-120">ライセンス契約に同意して、**[次へ]** を選択します。</span><span class="sxs-lookup"><span data-stu-id="77688-120">Accept the license agreement, and select **Next**.</span></span> 
4. <span data-ttu-id="77688-121">インストールを続行します。</span><span class="sxs-lookup"><span data-stu-id="77688-121">Continue with the installation.</span></span> <span data-ttu-id="77688-122">インストール中にいくつかのコマンド ウィンドウ可能性があります開いたり閉じたりします。</span><span class="sxs-lookup"><span data-stu-id="77688-122">During the install, several command windows may open and close.</span></span> <span data-ttu-id="77688-123">完了したら、されたら**完了**です。</span><span class="sxs-lookup"><span data-stu-id="77688-123">When complete, you are prompted to **Finish**.</span></span>

<span data-ttu-id="77688-124">セットアップ ログに作成されて`C:\ProgramData\Microsoft\E-Business Servers Updates\Updates\Uninstall4014788-FP2\setup.log`です。</span><span class="sxs-lookup"><span data-stu-id="77688-124">A setup log is created in `C:\ProgramData\Microsoft\E-Business Servers Updates\Updates\Uninstall4014788-FP2\setup.log`.</span></span>

>[!TIP]
> <span data-ttu-id="77688-125">インストールの包括的なガイダンスについては、次を参照してください。、 [Feature Pack のインストールに関する手順](https://blog.sandro-pereira.com/2017/04/27/microsoft-biztalk-server-2016-feature-pack-1-step-by-step-installation/)ブログの投稿。</span><span class="sxs-lookup"><span data-stu-id="77688-125">For comprehensive guidance on the installation, see the [Feature Pack step-by-step installation](https://blog.sandro-pereira.com/2017/04/27/microsoft-biztalk-server-2016-feature-pack-1-step-by-step-installation/) blog post.</span></span>

## <a name="feature-pack-2-updates"></a><span data-ttu-id="77688-126">機能パック 2 の更新</span><span class="sxs-lookup"><span data-stu-id="77688-126">Feature Pack 2 updates</span></span>

#### <a name="expose-soap-endpoints-with-api-managementcoreconnect-to-azure-api-managementmd"></a>[<span data-ttu-id="77688-127">API Management の SOAP エンドポイントを公開します</span><span class="sxs-lookup"><span data-stu-id="77688-127">Expose SOAP endpoints with API Management</span></span>](../core/connect-to-azure-api-management.md)

<span data-ttu-id="77688-128">機能パック 1 で行われた API 管理の統合に展開すると、できるようになりましたを公開して、Wcf-basichttp 受信、BizTalk Server 管理コンソールを使用して SOAP エンドポイントの場所。</span><span class="sxs-lookup"><span data-stu-id="77688-128">Expanding on the API management integration made with Feature Pack 1, you can now expose a WCF-BasicHTTP receive location as a SOAP endpoint using the BizTalk Server Administration console.</span></span> 

#### <a name="use-the-event-hub-adapterevent-hubs-adaptermd"></a>[<span data-ttu-id="77688-129">Event Hub のアダプターを使用します。</span><span class="sxs-lookup"><span data-stu-id="77688-129">Use the Event Hub adapter</span></span>](event-hubs-adapter.md)

<span data-ttu-id="77688-130">BizTalk からのメッセージを Azure Event Hubs に送信し、Azure Event Hubs から BizTalk Server にメッセージを受信します。</span><span class="sxs-lookup"><span data-stu-id="77688-130">Send messages from BizTalk to Azure Event Hubs, and receive messages from Azure Event Hubs to BizTalk Server.</span></span> <span data-ttu-id="77688-131">トランスポートのプロパティを構成するときに、簡単に、Azure アカウントにサインインし、Azure Event Hubs の名前空間、および Event Hub を自動的に選択できます。</span><span class="sxs-lookup"><span data-stu-id="77688-131">When you configure the transport properties, you can easily sign in to your Azure account, and automatically select your Azure Event Hubs namespace, and Event Hub.</span></span>

#### <a name="backup-to-azure-blob-accountcorehow-to-configure-the-backup-biztalk-server-jobmd"></a>[<span data-ttu-id="77688-132">Azure blob アカウントへのバックアップ</span><span class="sxs-lookup"><span data-stu-id="77688-132">Backup to Azure blob account</span></span>](../core/how-to-configure-the-backup-biztalk-server-job.md)
<span data-ttu-id="77688-133">BizTalk Server のバックアップ ジョブは、BizTalk データベースとログ ファイルをバックアップします。</span><span class="sxs-lookup"><span data-stu-id="77688-133">The Backup BizTalk Server job backs up the BizTalk databases and log files.</span></span> <span data-ttu-id="77688-134">この SQL エージェント ジョブを構成するときに、ジョブのプロパティ内での Azure blob ストレージ アカウントを入力できます。</span><span class="sxs-lookup"><span data-stu-id="77688-134">When you configure this SQL Agent job, you can enter an Azure blob storage account within the job properties.</span></span> <span data-ttu-id="77688-135">これにより、ローカルの物理ディスクを使用する代わりに、データをバックアップする別のオプションです。</span><span class="sxs-lookup"><span data-stu-id="77688-135">This gives you another option to backup your data, instead of using a local physical disk.</span></span> 

#### <a name="multi-machine-deployment-using-vstscoreconfigure-automatic-deployment-with-visual-studio-team-services-in-biztalkmd"></a>[<span data-ttu-id="77688-136">VSTS を使用して複数のコンピューターの展開</span><span class="sxs-lookup"><span data-stu-id="77688-136">Multi-machine deployment using VSTS</span></span>](../core/configure-automatic-deployment-with-visual-studio-team-services-in-biztalk.md)
<span data-ttu-id="77688-137">展開グループを使用して、複数の BizTalk Server にアプリケーションを展開できます。</span><span class="sxs-lookup"><span data-stu-id="77688-137">Using deployment groups, you can deploy your applications to multiple BizTalk Servers.</span></span> <span data-ttu-id="77688-138">また、アプリケーション プロジェクト内でアプリケーション名を設定でき、管理サーバーを入力して、アプリケーションをインストールできます。</span><span class="sxs-lookup"><span data-stu-id="77688-138">You can also set the application name within the application project, and install your application by entering your management server.</span></span>

<span data-ttu-id="77688-139">[展開グループ](https://docs.microsoft.com/vsts/build-release/concepts/definitions/release/deployment-groups/index)VSTS でこれを行う方法の詳細を提供します。</span><span class="sxs-lookup"><span data-stu-id="77688-139">[Deployment groups](https://docs.microsoft.com/vsts/build-release/concepts/definitions/release/deployment-groups/index) provides more details on how this is done in VSTS.</span></span>  

#### <a name="use-service-bus-premiumcoresb-messaging-adaptermd"></a>[<span data-ttu-id="77688-140">サービス バス Premium を使用します。</span><span class="sxs-lookup"><span data-stu-id="77688-140">Use Service Bus Premium</span></span>](../core/sb-messaging-adapter.md)

<span data-ttu-id="77688-141">Service Bus アダプターには、パーティション分割されたキューおよびトピックにメッセージを送信するなど、サービス バス Premium がサポートしています。</span><span class="sxs-lookup"><span data-stu-id="77688-141">The Service Bus adapter supports Service Bus Premium, including sending messages to partitioned queues and topics.</span></span> <span data-ttu-id="77688-142">[サービス バス プレミアムおよび標準的なメッセージング層](https://docs.microsoft.com/azure/service-bus-messaging/service-bus-premium-messaging)サービス バス Premium の詳細について詳しく説明します。</span><span class="sxs-lookup"><span data-stu-id="77688-142">[Service Bus Premium and Standard messaging tiers](https://docs.microsoft.com/azure/service-bus-messaging/service-bus-premium-messaging) details more about Service Bus Premium.</span></span> 

#### <a name="use-named-instances-with-application-insightscoresend-tracking-data-to-azure-application-insights-using-biztalk-servermd"></a>[<span data-ttu-id="77688-143">Application Insights による名前付きインスタンスを使用します。</span><span class="sxs-lookup"><span data-stu-id="77688-143">Use named instances with Application Insights</span></span>](../core/send-tracking-data-to-azure-application-insights-using-biztalk-server.md)
<span data-ttu-id="77688-144">分析を可能になり、Application Insights キーを入力すると、エラーが発生する可能性があります。</span><span class="sxs-lookup"><span data-stu-id="77688-144">When you enable Analytics, and enter the Application Insights key, you may get error:</span></span> 

```
Group settings were not applied. (A database failure occurred due to database connectivity problems.)
```

<span data-ttu-id="77688-145">これは、名前付きインスタンスの SQL を使用する場合に発生します。</span><span class="sxs-lookup"><span data-stu-id="77688-145">This happens when you use SQL named instances.</span></span> <span data-ttu-id="77688-146">これは、です。 この feature pack で修正します。名前付きインスタンスの SQL および SQL の既定のインスタンスを使用できます。</span><span class="sxs-lookup"><span data-stu-id="77688-146">This is fixed in this feature pack; you can use SQL default instances, and SQL named instances.</span></span> 

#### <a name="tls-12-support"></a><span data-ttu-id="77688-147">TLS 1.2 サポート</span><span class="sxs-lookup"><span data-stu-id="77688-147">TLS 1.2 support</span></span>

<span data-ttu-id="77688-148">TLS 1.2 は、BizTalk Server で、すべてのアダプターなど、すべてのアクセラレータがサポートされます。</span><span class="sxs-lookup"><span data-stu-id="77688-148">TLS 1.2 is fully supported in BizTalk Server, including all the adapters and all the accelerators.</span></span> <span data-ttu-id="77688-149">SSL、TLS 1.0、および BizTalk サーバーで TLS 1.1 を無効にすることができます。</span><span class="sxs-lookup"><span data-stu-id="77688-149">You can disable SSL, TLS 1.0, and TLS 1.1 on the BizTalk Server.</span></span> 

<span data-ttu-id="77688-150">重要な情報:</span><span class="sxs-lookup"><span data-stu-id="77688-150">Key information:</span></span> 

* <span data-ttu-id="77688-151">BizTalk とも通信するすべての外部システムは、TLS 1.2 をサポートする必要があります。</span><span class="sxs-lookup"><span data-stu-id="77688-151">Any external systems communicating with BizTalk also need to support TLS 1.2</span></span>
* <span data-ttu-id="77688-152">Functoid などの任意のカスタム コードは、サポート TLS 1.2 に更新する必要があります。</span><span class="sxs-lookup"><span data-stu-id="77688-152">Any custom code, such as functoids, may need to be updated to support TLS 1.2</span></span>

<span data-ttu-id="77688-153">[TLS と SSL プロトコルの説明](https://support.microsoft.com/kb/3155464)TLS 1.2 環境をセットアップする方法について説明します。</span><span class="sxs-lookup"><span data-stu-id="77688-153">[Description of the TLS/SSL protocol](https://support.microsoft.com/kb/3155464) describes how to setup a TLS 1.2 environment.</span></span> 

#### <a name="use-latest-newtonsoft-json"></a><span data-ttu-id="77688-154">最新の Newtonsoft の JSON を使用します。</span><span class="sxs-lookup"><span data-stu-id="77688-154">Use latest Newtonsoft JSON</span></span> 
<span data-ttu-id="77688-155">Newtonsoft は、.NET 用 JSON フレームワークです。</span><span class="sxs-lookup"><span data-stu-id="77688-155">Newtonsoft is a JSON framework for .NET.</span></span> <span data-ttu-id="77688-156">この機能パックには、バージョン 10.0.3 のサポートが含まれます。</span><span class="sxs-lookup"><span data-stu-id="77688-156">In this feature pack, support for version 10.0.3 is included.</span></span> <span data-ttu-id="77688-157">[V をダウンロードします。10.0.3](https://www.nuget.org/packages/Newtonsoft.Json/10.0.3) NuGet から直接です。</span><span class="sxs-lookup"><span data-stu-id="77688-157">[Download v. 10.0.3](https://www.nuget.org/packages/Newtonsoft.Json/10.0.3) directly from NuGet.</span></span> 


## <a name="feature-pack-1-updates"></a><span data-ttu-id="77688-158">機能パック 1 の更新</span><span class="sxs-lookup"><span data-stu-id="77688-158">Feature Pack 1 updates</span></span>

#### <a name="send-tracking-data-to-application-insightscoresend-tracking-data-to-azure-application-insights-using-biztalk-servermd"></a>[<span data-ttu-id="77688-159">追跡データを Application Insights に送信する</span><span class="sxs-lookup"><span data-stu-id="77688-159">Send tracking data to Application Insights</span></span>](../core/send-tracking-data-to-azure-application-insights-using-biztalk-server.md)

<span data-ttu-id="77688-160">追跡データを分析、機械学習、診断などの機能を使用する Azure Application Insights に送信します。</span><span class="sxs-lookup"><span data-stu-id="77688-160">Send tracking data to Azure Application Insights to use its features, such as analytics, machine learning, diagnostics, and more.</span></span> 

#### <a name="configure-the-operational-data-feed-using-power-bicoreconfigure-the-operational-data-feed-for-power-bi-with-biztalk-servermd"></a>[<span data-ttu-id="77688-161">フィードの Power BI を使用して運用データを構成します。</span><span class="sxs-lookup"><span data-stu-id="77688-161">Configure the operational data feed using Power BI</span></span>](../core/configure-the-operational-data-feed-for-power-bi-with-biztalk-server.md)

<span data-ttu-id="77688-162">OData を使用して Power BI に追跡データを送信します。</span><span class="sxs-lookup"><span data-stu-id="77688-162">Send tracking data to Power BI using oData.</span></span> <span data-ttu-id="77688-163">たとえば、ポートやオーケストレーションから追跡データのビジュアル表現を取得します。</span><span class="sxs-lookup"><span data-stu-id="77688-163">For example, get a visual representation of your tracking data from your ports and orchestrations.</span></span> 

#### <a name="connect-to-the-management-rest-apis-in-biztalkcoreinstall-and-configure-the-management-rest-apis-in-biztalk-servermd"></a>[<span data-ttu-id="77688-164">管理の BizTalk で REST Api への接続します。</span><span class="sxs-lookup"><span data-stu-id="77688-164">Connect to the management REST APIs in BizTalk</span></span>](../core/install-and-configure-the-management-rest-apis-in-biztalk-server.md)

<span data-ttu-id="77688-165">REST Api を使用すると、契約、中断されたインスタンス、参加解除のオーケストレーションなど、BizTalk アイテムをリモートで管理します。</span><span class="sxs-lookup"><span data-stu-id="77688-165">Use REST APIs to remotely manage your BizTalk artifacts, including agreements, suspended instances, unenlisted orchestrations, and more.</span></span>

#### <a name="configure-advanced-schedulingcoreconfigure-the-time-zone-and-recurrence-scheduling-in-biztalk-servermd"></a>[<span data-ttu-id="77688-166">高度なスケジュール設定を構成します。</span><span class="sxs-lookup"><span data-stu-id="77688-166">Configure advanced scheduling</span></span>](../core/configure-the-time-zone-and-recurrence-scheduling-in-biztalk-server.md)

<span data-ttu-id="77688-167">有効にする詳細なでスケジュールの受信場所。</span><span class="sxs-lookup"><span data-stu-id="77688-167">Enable advanced scheduling in your receive locations.</span></span> <span data-ttu-id="77688-168">たとえば、タイム ゾーンを設定または特定の月に特定の日の定期的なサービス時間帯を設定します。</span><span class="sxs-lookup"><span data-stu-id="77688-168">For example, set the timezone, or set a recurrence service window for a specific day on a specific month.</span></span>

#### <a name="configure-automatic-deployments-with-vstscoreconfigure-automatic-deployment-with-visual-studio-team-services-in-biztalkmd"></a>[<span data-ttu-id="77688-169">VSTS と自動展開を構成します。</span><span class="sxs-lookup"><span data-stu-id="77688-169">Configure automatic deployments with VSTS</span></span>](../core/configure-automatic-deployment-with-visual-studio-team-services-in-biztalk.md)  

<span data-ttu-id="77688-170">Visual Studio Team Services (VSTS) を使用して、ソリューションを自動的に展開するか、既存のアプリケーションを更新します。</span><span class="sxs-lookup"><span data-stu-id="77688-170">Use Visual Studio Team Services (VSTS) to automatically deploy your solutions, or update existing applications.</span></span> <span data-ttu-id="77688-171">インストールされたエージェントと通信する VSTS、[!INCLUDE[btsBizTalkServerNoVersion_md](../includes/btsbiztalkservernoversion-md.md)]です。</span><span class="sxs-lookup"><span data-stu-id="77688-171">VSTS communicates with an agent installed on the [!INCLUDE[btsBizTalkServerNoVersion_md](../includes/btsbiztalkservernoversion-md.md)].</span></span>

#### <a name="connect-to-sql-server-always-encrypted-columns-with-biztalk-servercoreconnect-to-sql-server-always-encrypted-columns-with-biztalk-servermd"></a>[<span data-ttu-id="77688-172">BizTalk Server と SQL Server の Always Encrypted の列への接続します。</span><span class="sxs-lookup"><span data-stu-id="77688-172">Connect to SQL Server Always Encrypted columns with BizTalk Server</span></span>](../core/connect-to-sql-server-always-encrypted-columns-with-biztalk-server.md)  

<span data-ttu-id="77688-173">WCF-SQL アダプターを使用して、SQL Server で Always Encrypted データベースから暗号化された列をクエリします。</span><span class="sxs-lookup"><span data-stu-id="77688-173">Use the WCF-SQL adapter to query encrypted columns from an Always Encrypted database in SQL Server.</span></span>

#### <a name="integrate-with-api-managementcoreconnect-to-azure-api-managementmd"></a>[<span data-ttu-id="77688-174">API Management を統合します。</span><span class="sxs-lookup"><span data-stu-id="77688-174">Integrate with API Management</span></span>](../core/connect-to-azure-api-management.md)

<span data-ttu-id="77688-175">Azure API management サービス内で作成および WSDL、として API を公開したり BizTalk SOAP エンドポイントに URI を使用します。</span><span class="sxs-lookup"><span data-stu-id="77688-175">Within your Azure API management service, you can create and expose an API as WSDL, and use the URI to a BizTalk SOAP endpoint.</span></span>  