---
title: Feature pack の構成 |Microsoft Docs
description: インストールし、機能パック 1 を構成し、機能パック 2 します。 API Management、team services のデプロイ、Azure の新しいアダプター、バックアップ、および BizTalk Server 2016 では、複数を含む新しい機能の一覧を参照してください。
ms.custom: ''
ms.date: 06/26/2018
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
ms.openlocfilehash: 210089dc225d85271a8c8fdc426d2ca68bf353e1
ms.sourcegitcommit: 080224caa88f9935b5b13fa035d372f8964d2e52
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 06/26/2018
ms.locfileid: "36957870"
---
# <a name="configure-the-feature-pack"></a><span data-ttu-id="324bb-104">Feature pack を構成します。</span><span class="sxs-lookup"><span data-stu-id="324bb-104">Configure the feature pack</span></span>

## <a name="overview"></a><span data-ttu-id="324bb-105">概要</span><span class="sxs-lookup"><span data-stu-id="324bb-105">Overview</span></span>

[!INCLUDE[btsBizTalkServerNoVersion_md](../includes/btsbiztalkservernoversion-md.md)]<span data-ttu-id="324bb-106"> feature pack を使用して、機能強化、機能、および Azure との統合を提供します。</span><span class="sxs-lookup"><span data-stu-id="324bb-106"> uses feature packs to provide improvements, features, and closer integration with Azure.</span></span> <span data-ttu-id="324bb-107">これらの feature pack は、展開、セキュリティ、分析、ランタイム、保守、標準的なコンプライアンス、およびハイブリッド統合などの主要分野における機能を拡張します。</span><span class="sxs-lookup"><span data-stu-id="324bb-107">These feature packs extend functionality in key areas, such as deployment, security, analytics, runtime, maintainance, standard compliance, and hybrid integration.</span></span> 

> [!NOTE]
> <span data-ttu-id="324bb-108">Feature pack の Enterprise および Developer エディションで使用可能な[!INCLUDE[bts2016_md](../includes/bts2016-md.md)]とき。</span><span class="sxs-lookup"><span data-stu-id="324bb-108">The feature packs are available with the Enterprise and Developer editions of [!INCLUDE[bts2016_md](../includes/bts2016-md.md)] when:</span></span> 
> 
> - <span data-ttu-id="324bb-109">ソフトウェア アシュアランス (SA) で使用または</span><span class="sxs-lookup"><span data-stu-id="324bb-109">Used with Software Assurance (SA), OR</span></span>
> - <span data-ttu-id="324bb-110">実行している[!INCLUDE[btsBizTalkServerNoVersion_md](../includes/btsbiztalkservernoversion-md.md)]エンタープライズ契約を使用して Azure に</span><span class="sxs-lookup"><span data-stu-id="324bb-110">Running [!INCLUDE[btsBizTalkServerNoVersion_md](../includes/btsbiztalkservernoversion-md.md)] in Azure using an Enterprise Agreement</span></span>
> 
> <span data-ttu-id="324bb-111">Feature pack がその他のご利用いただけません[!INCLUDE[btsBizTalkServerNoVersion_md](../includes/btsbiztalkservernoversion-md.md)]エディション (Standard edition および Branch edition)、またはその他の[!INCLUDE[btsBizTalkServerNoVersion_md](../includes/btsbiztalkservernoversion-md.md)]バージョン (2013 R2、2013、2010 など)。</span><span class="sxs-lookup"><span data-stu-id="324bb-111">The feature packs are not available for any other [!INCLUDE[btsBizTalkServerNoVersion_md](../includes/btsbiztalkservernoversion-md.md)] edition (Standard and Branch editions), or any other [!INCLUDE[btsBizTalkServerNoVersion_md](../includes/btsbiztalkservernoversion-md.md)] version (2013 R2, 2013, 2010, and so on).</span></span> 

## <a name="download-and-install"></a><span data-ttu-id="324bb-112">ダウンロードしてインストールする</span><span class="sxs-lookup"><span data-stu-id="324bb-112">Download and install</span></span>

<span data-ttu-id="324bb-113">Feature pack は累積されます。</span><span class="sxs-lookup"><span data-stu-id="324bb-113">The feature packs are cumulative.</span></span> <span data-ttu-id="324bb-114">したがって 3 用 feature pack をインストールするときに取得することも、機能および更新 feature pack 2 および 1。</span><span class="sxs-lookup"><span data-stu-id="324bb-114">So when you install feature pack 3, you also get the features and updates in feature packs 2 and 1.</span></span> <span data-ttu-id="324bb-115">最新の累積的更新プログラムを表示します。</span><span class="sxs-lookup"><span data-stu-id="324bb-115">You also get the latest cumulative updates.</span></span>

* <span data-ttu-id="324bb-116">ダウンロード、 [!INCLUDE[bts2016_md](../includes/bts2016-md.md)] [Feature Pack 3](https://aka.ms/bts2016fp3)します。</span><span class="sxs-lookup"><span data-stu-id="324bb-116">Download the [!INCLUDE[bts2016_md](../includes/bts2016-md.md)] [Feature Pack 3](https://aka.ms/bts2016fp3).</span></span>

* <span data-ttu-id="324bb-117">ダウンロード、 [!INCLUDE[bts2016_md](../includes/bts2016-md.md)] [Feature Pack 2](https://aka.ms/bts2016fp2)します。</span><span class="sxs-lookup"><span data-stu-id="324bb-117">Download the [!INCLUDE[bts2016_md](../includes/bts2016-md.md)] [Feature Pack 2](https://aka.ms/bts2016fp2).</span></span>

* <span data-ttu-id="324bb-118">ダウンロード、 [!INCLUDE[bts2016_md](../includes/bts2016-md.md)] [Feature Pack 1](https://www.microsoft.com/download/details.aspx?id=55100)します。</span><span class="sxs-lookup"><span data-stu-id="324bb-118">Download the [!INCLUDE[bts2016_md](../includes/bts2016-md.md)] [Feature Pack 1](https://www.microsoft.com/download/details.aspx?id=55100).</span></span>

#### <a name="install"></a><span data-ttu-id="324bb-119">インストール</span><span class="sxs-lookup"><span data-stu-id="324bb-119">Install</span></span>

1. <span data-ttu-id="324bb-120">セットアップを管理者として実行します。</span><span class="sxs-lookup"><span data-stu-id="324bb-120">Run setup as administrator.</span></span>
2. <span data-ttu-id="324bb-121">**ようこそ**を選択します**次**します。</span><span class="sxs-lookup"><span data-stu-id="324bb-121">In **Welcome**, select **Next**.</span></span> 
3. <span data-ttu-id="324bb-122">ライセンス契約に同意して、**[次へ]** を選択します。</span><span class="sxs-lookup"><span data-stu-id="324bb-122">Accept the license agreement, and select **Next**.</span></span> 
4. <span data-ttu-id="324bb-123">インストールを続行します。</span><span class="sxs-lookup"><span data-stu-id="324bb-123">Continue with the installation.</span></span> <span data-ttu-id="324bb-124">インストール中にはいくつかのコマンド ウィンドウが開き、閉じます。</span><span class="sxs-lookup"><span data-stu-id="324bb-124">During the install, several command windows may open and close.</span></span> <span data-ttu-id="324bb-125">完了すると、求められる**完了**します。</span><span class="sxs-lookup"><span data-stu-id="324bb-125">When complete, you are prompted to **Finish**.</span></span>

<span data-ttu-id="324bb-126">セットアップ ログが作成`C:\ProgramData\Microsoft\E-Business Servers Updates\Updates\Uninstall4014788-FP2\setup.log`です。</span><span class="sxs-lookup"><span data-stu-id="324bb-126">A setup log is created in `C:\ProgramData\Microsoft\E-Business Servers Updates\Updates\Uninstall4014788-FP2\setup.log`.</span></span>

>[!TIP]
> <span data-ttu-id="324bb-127">インストールの包括的なガイダンスについては、次を参照してください。、 [BizTalk Server 2016 機能パック 3: ステップ バイ ステップ インストール](https://blog.sandro-pereira.com/2018/06/26/biztalk-server-2016-feature-pack-3/)ブログの投稿。</span><span class="sxs-lookup"><span data-stu-id="324bb-127">For comprehensive guidance on the installation, see the [BizTalk Server 2016 Feature Pack 3: step-by-step installation](https://blog.sandro-pereira.com/2018/06/26/biztalk-server-2016-feature-pack-3/) blog post.</span></span>

## <a name="feature-pack-3-updates"></a><span data-ttu-id="324bb-128">機能パック 3 更新プログラム</span><span class="sxs-lookup"><span data-stu-id="324bb-128">Feature Pack 3 updates</span></span>

<span data-ttu-id="324bb-129">**Office 365 アダプター**</span><span class="sxs-lookup"><span data-stu-id="324bb-129">**Office 365 Adapters**</span></span>


<span data-ttu-id="324bb-130">Microsoft Office 365 統合した、最適なクラウド ベースのサブスクリプション サービスは、人々 のツールが現在動作します。</span><span class="sxs-lookup"><span data-stu-id="324bb-130">Microsoft Office 365 is a cloud-based subscription service that brings together the best tools for the way people work today.</span></span> <span data-ttu-id="324bb-131">Excel や Outlook などのクラス最高のアプリを OneDrive や Microsoft Teams などの強力なクラウド サービスを組み合わせることにより、Office 365 はすべてのユーザーを作成し、任意のデバイスで任意の場所を共有できます。</span><span class="sxs-lookup"><span data-stu-id="324bb-131">By combining best-in-class apps like Excel and Outlook with powerful cloud services like OneDrive and Microsoft Teams, Office 365 lets anyone create and share anywhere on any device.</span></span>

<span data-ttu-id="324bb-132">Office 365 の Microsoft BizTalk Server アダプターには、Outlook のメール、連絡先、およびスケジュールを BizTalk Server 2016 に基づく新しいソリューションと統合するには、IT プロフェッショナルおよび企業の開発者が有効にします。</span><span class="sxs-lookup"><span data-stu-id="324bb-132">Microsoft BizTalk Server adapters for Office 365 enable IT professionals and enterprise developers to integrate Outlook mail, contacts, and schedules with new solutions based on BizTalk Server 2016.</span></span>

#### <a name="office-365-mail-adapteroffice365-mail-adaptermd"></a>[<span data-ttu-id="324bb-133">Office 365 メール アダプター</span><span class="sxs-lookup"><span data-stu-id="324bb-133">Office 365 Mail adapter</span></span>](office365-mail-adapter.md)
<span data-ttu-id="324bb-134">BizTalk Adapter for Office 365 のメールを使用して読み取ることができます、既読としてマーク Outlook の一方向の BizTalk Server 経由で電子メール メッセージの受信場所を削除または。</span><span class="sxs-lookup"><span data-stu-id="324bb-134">Using the BizTalk Adapter for Office 365 Mail, you can read, mark as read or delete Outlook e-mail messages through one-way BizTalk Server receive locations.</span></span> <span data-ttu-id="324bb-135">このアダプターを使用して、一方向の静的で、メッセージの優先度の設定を含む電子メール メッセージを記述することができますか、動的な BizTalk Server 送信ポート。</span><span class="sxs-lookup"><span data-stu-id="324bb-135">Using this adapter, you can write e-mail message, including setting message priority, through one-way static or dynamic BizTalk Server send ports.</span></span>

#### <a name="office-365-calendar-adapteroffice365-calendar-adaptermd"></a>[<span data-ttu-id="324bb-136">Office 365 カレンダーのアダプター</span><span class="sxs-lookup"><span data-stu-id="324bb-136">Office 365 Calendar adapter</span></span>](office365-calendar-adapter.md)
<span data-ttu-id="324bb-137">BizTalk Adapter for Office 365 カレンダーを使用して取得できます今後の予定表が一方向の BizTalk Server を介してイベントを受信場所。</span><span class="sxs-lookup"><span data-stu-id="324bb-137">Using the BizTalk Adapter for Office 365 Calendar, you can get future calendar events through one-way BizTalk Server receive locations.</span></span> <span data-ttu-id="324bb-138">このアダプターを使用して、カレンダーのイベントを作成することができますと必須およびオプションの出席者の入力一方向の静的または動的な BizTalk Server から送信ポート。</span><span class="sxs-lookup"><span data-stu-id="324bb-138">Using this adapter, you can create calendar events, and enter required and optional attendees, through one-way static or dynamic BizTalk Server send ports.</span></span>

#### <a name="office-365-contact-adapteroffice365-contact-adaptermd"></a>[<span data-ttu-id="324bb-139">Office 365 連絡先アダプター</span><span class="sxs-lookup"><span data-stu-id="324bb-139">Office 365 Contact adapter</span></span>](office365-contact-adapter.md)
<span data-ttu-id="324bb-140">BizTalk アダプターを使用して、Office 365 の連絡先に、連絡先を作成できますとすべての設定を入力します。 一方向の静的または動的な BizTalk Server から送信ポート。</span><span class="sxs-lookup"><span data-stu-id="324bb-140">Using the BizTalk Adapter for Office 365 Contact, you can create contacts, and enter all settings, through one-way static or dynamic BizTalk Server send ports.</span></span>

## <a name="feature-pack-2-updates"></a><span data-ttu-id="324bb-141">機能パック 2 更新プログラム</span><span class="sxs-lookup"><span data-stu-id="324bb-141">Feature Pack 2 updates</span></span>

#### <a name="expose-soap-endpoints-with-api-managementcoreconnect-to-azure-api-managementmd"></a>[<span data-ttu-id="324bb-142">API Management で SOAP エンドポイントを公開します。</span><span class="sxs-lookup"><span data-stu-id="324bb-142">Expose SOAP endpoints with API Management</span></span>](../core/connect-to-azure-api-management.md)

<span data-ttu-id="324bb-143">Feature Pack 1 を使用した API management の統合で拡張すると、できるようになりました公開、Wcf-basichttp 受信場所として BizTalk Server 管理コンソールを使用して、SOAP エンドポイント。</span><span class="sxs-lookup"><span data-stu-id="324bb-143">Expanding on the API management integration made with Feature Pack 1, you can now expose a WCF-BasicHTTP receive location as a SOAP endpoint using the BizTalk Server Administration console.</span></span> 

#### <a name="use-the-event-hub-adapterevent-hubs-adaptermd"></a>[<span data-ttu-id="324bb-144">イベント ハブのアダプターを使用します。</span><span class="sxs-lookup"><span data-stu-id="324bb-144">Use the Event Hub adapter</span></span>](event-hubs-adapter.md)

<span data-ttu-id="324bb-145">Azure Event hubs では、BizTalk からのメッセージを送信して、BizTalk Server を Azure Event Hubs からメッセージを受信します。</span><span class="sxs-lookup"><span data-stu-id="324bb-145">Send messages from BizTalk to Azure Event Hubs, and receive messages from Azure Event Hubs to BizTalk Server.</span></span> <span data-ttu-id="324bb-146">トランスポートのプロパティを構成するときに、簡単に、Azure アカウントにサインインし、Azure Event Hubs 名前空間とイベント ハブを自動的に選択できます。</span><span class="sxs-lookup"><span data-stu-id="324bb-146">When you configure the transport properties, you can easily sign in to your Azure account, and automatically select your Azure Event Hubs namespace, and Event Hub.</span></span>

#### <a name="backup-to-azure-blob-accountcorehow-to-configure-the-backup-biztalk-server-jobmd"></a>[<span data-ttu-id="324bb-147">Azure blob アカウントへのバックアップ</span><span class="sxs-lookup"><span data-stu-id="324bb-147">Backup to Azure blob account</span></span>](../core/how-to-configure-the-backup-biztalk-server-job.md)
<span data-ttu-id="324bb-148">BizTalk Server のバックアップ ジョブは、BizTalk データベースとログ ファイルをバックアップします。</span><span class="sxs-lookup"><span data-stu-id="324bb-148">The Backup BizTalk Server job backs up the BizTalk databases and log files.</span></span> <span data-ttu-id="324bb-149">この SQL エージェント ジョブを構成するときに、ジョブのプロパティ内での Azure blob ストレージ アカウントを入力できます。</span><span class="sxs-lookup"><span data-stu-id="324bb-149">When you configure this SQL Agent job, you can enter an Azure blob storage account within the job properties.</span></span> <span data-ttu-id="324bb-150">これにより、ローカルの物理ディスクを使用する代わりに、データをバックアップする別のオプション。</span><span class="sxs-lookup"><span data-stu-id="324bb-150">This gives you another option to backup your data, instead of using a local physical disk.</span></span> 

#### <a name="multi-machine-deployment-using-vstscoreconfigure-automatic-deployment-with-visual-studio-team-services-in-biztalkmd"></a>[<span data-ttu-id="324bb-151">VSTS を使用して複数のコンピューターの展開</span><span class="sxs-lookup"><span data-stu-id="324bb-151">Multi-machine deployment using VSTS</span></span>](../core/configure-automatic-deployment-with-visual-studio-team-services-in-biztalk.md)
<span data-ttu-id="324bb-152">配置グループを使用して、複数の BizTalk Server アプリケーションをデプロイできます。</span><span class="sxs-lookup"><span data-stu-id="324bb-152">Using deployment groups, you can deploy your applications to multiple BizTalk Servers.</span></span> <span data-ttu-id="324bb-153">アプリケーション プロジェクト内でアプリケーション名を設定でき、管理サーバーを入力して、アプリケーションをインストールできます。</span><span class="sxs-lookup"><span data-stu-id="324bb-153">You can also set the application name within the application project, and install your application by entering your management server.</span></span>

<span data-ttu-id="324bb-154">[配置グループ](https://docs.microsoft.com/vsts/build-release/concepts/definitions/release/deployment-groups/index)VSTS でこれを行う方法の詳細を提供します。</span><span class="sxs-lookup"><span data-stu-id="324bb-154">[Deployment groups](https://docs.microsoft.com/vsts/build-release/concepts/definitions/release/deployment-groups/index) provides more details on how this is done in VSTS.</span></span>  

#### <a name="use-service-bus-premiumcoresb-messaging-adaptermd"></a>[<span data-ttu-id="324bb-155">Service Bus Premium を使用します。</span><span class="sxs-lookup"><span data-stu-id="324bb-155">Use Service Bus Premium</span></span>](../core/sb-messaging-adapter.md)

<span data-ttu-id="324bb-156">Service Bus アダプターには、パーティション分割されたキューおよびトピックにメッセージの送信など、Service Bus Premium がサポートしています。</span><span class="sxs-lookup"><span data-stu-id="324bb-156">The Service Bus adapter supports Service Bus Premium, including sending messages to partitioned queues and topics.</span></span> <span data-ttu-id="324bb-157">[Service Bus の Premium および Standard メッセージング レベル](https://docs.microsoft.com/azure/service-bus-messaging/service-bus-premium-messaging)Service Bus Premium の詳細について詳しく説明します。</span><span class="sxs-lookup"><span data-stu-id="324bb-157">[Service Bus Premium and Standard messaging tiers](https://docs.microsoft.com/azure/service-bus-messaging/service-bus-premium-messaging) details more about Service Bus Premium.</span></span> 

#### <a name="use-named-instances-with-application-insightscoresend-tracking-data-to-azure-application-insights-using-biztalk-servermd"></a>[<span data-ttu-id="324bb-158">Application Insights で名前付きインスタンスを使用します。</span><span class="sxs-lookup"><span data-stu-id="324bb-158">Use named instances with Application Insights</span></span>](../core/send-tracking-data-to-azure-application-insights-using-biztalk-server.md)
<span data-ttu-id="324bb-159">Analytics を有効にする Application Insights キーを入力すると、エラーが発生する可能性があります。</span><span class="sxs-lookup"><span data-stu-id="324bb-159">When you enable Analytics, and enter the Application Insights key, you may get error:</span></span> 

```
Group settings were not applied. (A database failure occurred due to database connectivity problems.)
```

<span data-ttu-id="324bb-160">これは、名前付きインスタンスの SQL を使用する場合に発生します。</span><span class="sxs-lookup"><span data-stu-id="324bb-160">This happens when you use SQL named instances.</span></span> <span data-ttu-id="324bb-161">これは、この feature pack; に修正します。名前付きインスタンスの SQL および SQL の既定のインスタンスを使用できます。</span><span class="sxs-lookup"><span data-stu-id="324bb-161">This is fixed in this feature pack; you can use SQL default instances, and SQL named instances.</span></span> 

#### <a name="tls-12-support"></a><span data-ttu-id="324bb-162">TLS 1.2 のサポート</span><span class="sxs-lookup"><span data-stu-id="324bb-162">TLS 1.2 support</span></span>

<span data-ttu-id="324bb-163">TLS 1.2 は、BizTalk server のすべてのアダプターなど、すべてのアクセラレータがサポートされます。</span><span class="sxs-lookup"><span data-stu-id="324bb-163">TLS 1.2 is fully supported in BizTalk Server, including all the adapters and all the accelerators.</span></span> <span data-ttu-id="324bb-164">SSL、TLS 1.0、および BizTalk Server の TLS 1.1 を無効にすることができます。</span><span class="sxs-lookup"><span data-stu-id="324bb-164">You can disable SSL, TLS 1.0, and TLS 1.1 on the BizTalk Server.</span></span> 

<span data-ttu-id="324bb-165">重要な情報:</span><span class="sxs-lookup"><span data-stu-id="324bb-165">Key information:</span></span> 

* <span data-ttu-id="324bb-166">また、BizTalk と通信するすべての外部システムが TLS 1.2 をサポートする必要があります。</span><span class="sxs-lookup"><span data-stu-id="324bb-166">Any external systems communicating with BizTalk also need to support TLS 1.2</span></span>
* <span data-ttu-id="324bb-167">Functoid などの任意のカスタム コードは、TLS 1.2 をサポートするように更新する必要があります。</span><span class="sxs-lookup"><span data-stu-id="324bb-167">Any custom code, such as functoids, may need to be updated to support TLS 1.2</span></span>

<span data-ttu-id="324bb-168">[TLS と SSL プロトコルの説明](https://support.microsoft.com/kb/3155464)TLS 1.2 の環境をセットアップする方法について説明します。</span><span class="sxs-lookup"><span data-stu-id="324bb-168">[Description of the TLS/SSL protocol](https://support.microsoft.com/kb/3155464) describes how to setup a TLS 1.2 environment.</span></span> 

#### <a name="use-latest-newtonsoft-json"></a><span data-ttu-id="324bb-169">最新 Newtonsoft の JSON を使用します。</span><span class="sxs-lookup"><span data-stu-id="324bb-169">Use latest Newtonsoft JSON</span></span> 
<span data-ttu-id="324bb-170">Newtonsoft は、.NET 用の JSON フレームワークです。</span><span class="sxs-lookup"><span data-stu-id="324bb-170">Newtonsoft is a JSON framework for .NET.</span></span> <span data-ttu-id="324bb-171">この機能パックのバージョン 10.0.3 のサポートが含まれます。</span><span class="sxs-lookup"><span data-stu-id="324bb-171">In this feature pack, support for version 10.0.3 is included.</span></span> <span data-ttu-id="324bb-172">[V をダウンロードします。10.0.3](https://www.nuget.org/packages/Newtonsoft.Json/10.0.3) NuGet から直接します。</span><span class="sxs-lookup"><span data-stu-id="324bb-172">[Download v. 10.0.3](https://www.nuget.org/packages/Newtonsoft.Json/10.0.3) directly from NuGet.</span></span> 


## <a name="feature-pack-1-updates"></a><span data-ttu-id="324bb-173">機能パック 1 更新プログラム</span><span class="sxs-lookup"><span data-stu-id="324bb-173">Feature Pack 1 updates</span></span>

#### <a name="send-tracking-data-to-application-insightscoresend-tracking-data-to-azure-application-insights-using-biztalk-servermd"></a>[<span data-ttu-id="324bb-174">追跡データを Application Insights に送信する</span><span class="sxs-lookup"><span data-stu-id="324bb-174">Send tracking data to Application Insights</span></span>](../core/send-tracking-data-to-azure-application-insights-using-biztalk-server.md)

<span data-ttu-id="324bb-175">追跡データを分析、機械学習、診断などの機能を使用する Azure Application Insights に送信します。</span><span class="sxs-lookup"><span data-stu-id="324bb-175">Send tracking data to Azure Application Insights to use its features, such as analytics, machine learning, diagnostics, and more.</span></span> 

#### <a name="configure-the-operational-data-feed-using-power-bicoreconfigure-the-operational-data-feed-for-power-bi-with-biztalk-servermd"></a>[<span data-ttu-id="324bb-176">Power BI を使用してフィード オペレーション データを構成します。</span><span class="sxs-lookup"><span data-stu-id="324bb-176">Configure the operational data feed using Power BI</span></span>](../core/configure-the-operational-data-feed-for-power-bi-with-biztalk-server.md)

<span data-ttu-id="324bb-177">OData を使用して Power BI には、追跡データを送信します。</span><span class="sxs-lookup"><span data-stu-id="324bb-177">Send tracking data to Power BI using oData.</span></span> <span data-ttu-id="324bb-178">など、ポート、およびオーケストレーションから追跡データのビジュアル表現を取得します。</span><span class="sxs-lookup"><span data-stu-id="324bb-178">For example, get a visual representation of your tracking data from your ports and orchestrations.</span></span> 

#### <a name="connect-to-the-management-rest-apis-in-biztalkcoreinstall-and-configure-the-management-rest-apis-in-biztalk-servermd"></a>[<span data-ttu-id="324bb-179">管理 REST Api では、BizTalk への接続します。</span><span class="sxs-lookup"><span data-stu-id="324bb-179">Connect to the management REST APIs in BizTalk</span></span>](../core/install-and-configure-the-management-rest-apis-in-biztalk-server.md)

<span data-ttu-id="324bb-180">REST Api を使用して、契約、中断されたインスタンス、オーケストレーションの参加解除など、BizTalk アイテムをリモートで管理します。</span><span class="sxs-lookup"><span data-stu-id="324bb-180">Use REST APIs to remotely manage your BizTalk artifacts, including agreements, suspended instances, unenlisted orchestrations, and more.</span></span>

#### <a name="configure-advanced-schedulingcoreconfigure-the-time-zone-and-recurrence-scheduling-in-biztalk-servermd"></a>[<span data-ttu-id="324bb-181">高度なスケジュール設定を構成します。</span><span class="sxs-lookup"><span data-stu-id="324bb-181">Configure advanced scheduling</span></span>](../core/configure-the-time-zone-and-recurrence-scheduling-in-biztalk-server.md)

<span data-ttu-id="324bb-182">有効にする詳細なでスケジュールの受信場所。</span><span class="sxs-lookup"><span data-stu-id="324bb-182">Enable advanced scheduling in your receive locations.</span></span> <span data-ttu-id="324bb-183">など、タイム ゾーンを設定または特定の日の特定の月に繰り返しサービス時間帯を設定します。</span><span class="sxs-lookup"><span data-stu-id="324bb-183">For example, set the timezone, or set a recurrence service window for a specific day on a specific month.</span></span>

#### <a name="configure-automatic-deployments-with-vstscoreconfigure-automatic-deployment-with-visual-studio-team-services-in-biztalkmd"></a>[<span data-ttu-id="324bb-184">VSTS を使用した自動展開を構成します。</span><span class="sxs-lookup"><span data-stu-id="324bb-184">Configure automatic deployments with VSTS</span></span>](../core/configure-automatic-deployment-with-visual-studio-team-services-in-biztalk.md)  

<span data-ttu-id="324bb-185">Visual Studio Team Services (VSTS) を使用して、ソリューションを自動的に展開するか、既存のアプリケーションを更新します。</span><span class="sxs-lookup"><span data-stu-id="324bb-185">Use Visual Studio Team Services (VSTS) to automatically deploy your solutions, or update existing applications.</span></span> <span data-ttu-id="324bb-186">VSTS と通信するエージェントがインストールされて、[!INCLUDE[btsBizTalkServerNoVersion_md](../includes/btsbiztalkservernoversion-md.md)]します。</span><span class="sxs-lookup"><span data-stu-id="324bb-186">VSTS communicates with an agent installed on the [!INCLUDE[btsBizTalkServerNoVersion_md](../includes/btsbiztalkservernoversion-md.md)].</span></span>

#### <a name="connect-to-sql-server-always-encrypted-columns-with-biztalk-servercoreconnect-to-sql-server-always-encrypted-columns-with-biztalk-servermd"></a>[<span data-ttu-id="324bb-187">BizTalk Server と SQL Server の Always Encrypted の列への接続します。</span><span class="sxs-lookup"><span data-stu-id="324bb-187">Connect to SQL Server Always Encrypted columns with BizTalk Server</span></span>](../core/connect-to-sql-server-always-encrypted-columns-with-biztalk-server.md)  

<span data-ttu-id="324bb-188">WCF-SQL アダプターを使用して、SQL Server で Always Encrypted データベースから暗号化された列をクエリします。</span><span class="sxs-lookup"><span data-stu-id="324bb-188">Use the WCF-SQL adapter to query encrypted columns from an Always Encrypted database in SQL Server.</span></span>

#### <a name="integrate-with-api-managementcoreconnect-to-azure-api-managementmd"></a>[<span data-ttu-id="324bb-189">API Management との統合します。</span><span class="sxs-lookup"><span data-stu-id="324bb-189">Integrate with API Management</span></span>](../core/connect-to-azure-api-management.md)

<span data-ttu-id="324bb-190">Azure API management サービス内で作成しとして WSDL では、API を公開し、BizTalk SOAP エンドポイントに URI を使用することができます。</span><span class="sxs-lookup"><span data-stu-id="324bb-190">Within your Azure API management service, you can create and expose an API as WSDL, and use the URI to a BizTalk SOAP endpoint.</span></span>  
