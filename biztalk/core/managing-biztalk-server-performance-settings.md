---
title: BizTalk Server パフォーマンス設定を管理する |Microsoft ドキュメント
description: 設定ダッシュ ボードを使用して BizTalk グループ、ホスト、およびホスト インスタンスが BizTalk Server での設定を更新
ms.custom: ''
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: ''
ms.suite: ''
ms.tgt_pltfrm: ''
ms.topic: article
ms.assetid: ca56a981-a255-4c4d-82f8-a57d390e425e
caps.latest.revision: 10
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: 0660fd4aa130049d80de4a0c2ee239ef5cae0068
ms.sourcegitcommit: 36350889f318e1f7e0ac9506dc8df794d475bda6
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 04/20/2018
---
# <a name="manage-biztalk-server-performance-settings"></a><span data-ttu-id="4d48c-103">BizTalk Server パフォーマンス設定を管理します。</span><span class="sxs-lookup"><span data-stu-id="4d48c-103">Manage BizTalk Server Performance Settings</span></span>
  
 <span data-ttu-id="4d48c-104">[!INCLUDE[btsSettingsDashboard](../includes/btssettingsdashboard-md.md)]を BizTalk Server のパフォーマンス設定を収集し、これらの設定を管理する中央コンソールを提供します。</span><span class="sxs-lookup"><span data-stu-id="4d48c-104">The [!INCLUDE[btsSettingsDashboard](../includes/btssettingsdashboard-md.md)] in BizTalk Server collates the performance settings, and provides a central console to manage these settings.</span></span> <span data-ttu-id="4d48c-105">これに役立ちます。</span><span class="sxs-lookup"><span data-stu-id="4d48c-105">This helps to:</span></span>  
  
-   <span data-ttu-id="4d48c-106">設定できるプロパティの探索可能性を向上させる</span><span class="sxs-lookup"><span data-stu-id="4d48c-106">Improve the discoverability of the properties that can be set</span></span>
  
-   <span data-ttu-id="4d48c-107">すべての設定を 1 か所でがアクセスできるよう、エクスポート/インポートできる簡単にするために、解決に時間を削減します。</span><span class="sxs-lookup"><span data-stu-id="4d48c-107">Reduce the time-to-solution because all settings are now accessible in a single place and can be exported/imported easily</span></span>
  
-   <span data-ttu-id="4d48c-108">特定の BizTalk 展開の実行のパフォーマンス チューニング レベルの全体像を提供しています</span><span class="sxs-lookup"><span data-stu-id="4d48c-108">Offers a holistic view of level of performance tuning done on a given BizTalk deployment</span></span>
  
## <a name="why-use-it"></a><span data-ttu-id="4d48c-109">使用する理由にしますか。</span><span class="sxs-lookup"><span data-stu-id="4d48c-109">Why use it?</span></span>  
 <span data-ttu-id="4d48c-110">[!INCLUDE[btsSettingsDashboard](../includes/btssettingsdashboard-md.md)]は、パフォーマンス最適化のために [!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)] の設定を幅広く調整する必要のある IT 管理者向けのものです。</span><span class="sxs-lookup"><span data-stu-id="4d48c-110">The [!INCLUDE[btsSettingsDashboard](../includes/btssettingsdashboard-md.md)] is targeted towards IT administrators who need to extensively tweak [!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)] settings for performance optimization.</span></span>  
  
 <span data-ttu-id="4d48c-111">[!INCLUDE[btsSettingsDashboard](../includes/btssettingsdashboard-md.md)]を使用すると、BizTalk グループと、そのグループに含まれるすべての BizTalk ホストおよび BizTalk ホスト インスタンスの設定を変更できます。</span><span class="sxs-lookup"><span data-stu-id="4d48c-111">You can use the [!INCLUDE[btsSettingsDashboard](../includes/btssettingsdashboard-md.md)] to modify settings for the BizTalk Group, and all the BizTalk Hosts and BizTalk Host Instances in that Group.</span></span>  
  
 <span data-ttu-id="4d48c-112">グループ、ホスト、およびホスト インスタンスの設定については、次を参照してください。 [グループ設定を変更する方法](../core/how-to-modify-group-settings.md), 、[ホスト設定を変更する方法](../core/how-to-modify-host-settings.md), 、および [ホスト インスタンス設定を変更する方法](../core/how-to-modify-host-instance-settings.md)します。</span><span class="sxs-lookup"><span data-stu-id="4d48c-112">To know more about the group, host, and host instance settings, see [How to Modify Group Settings](../core/how-to-modify-group-settings.md), [How to Modify Host Settings](../core/how-to-modify-host-settings.md), and [How to Modify Host Instance Settings](../core/how-to-modify-host-instance-settings.md).</span></span>  
  
## <a name="prerequisites"></a><span data-ttu-id="4d48c-113">前提条件</span><span class="sxs-lookup"><span data-stu-id="4d48c-113">Prerequisites</span></span> 
 <span data-ttu-id="4d48c-114">[!INCLUDE[btsSettingsDashboard](../includes/btssettingsdashboard-md.md)]は [!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)] 管理コンソールから起動できます。</span><span class="sxs-lookup"><span data-stu-id="4d48c-114">You can launch the [!INCLUDE[btsSettingsDashboard](../includes/btssettingsdashboard-md.md)] from the [!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)] Administration console.</span></span> <span data-ttu-id="4d48c-115">管理する方法の詳細について [!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)] パフォーマンス設定を使用して、 [!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)] 管理コンソールを参照してください [、BizTalk Server 管理コンソールを使用して](../core/using-the-biztalk-server-administration-console.md)します。</span><span class="sxs-lookup"><span data-stu-id="4d48c-115">For information on how to manage [!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)] performance settings using the [!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)] Administration console, see [Using the BizTalk Server Administration Console](../core/using-the-biztalk-server-administration-console.md).</span></span>  
  
## <a name="where-do-i-start"></a><span data-ttu-id="4d48c-116">どのように開始しますか。</span><span class="sxs-lookup"><span data-stu-id="4d48c-116">Where Do I Start?</span></span>  
 <span data-ttu-id="4d48c-117">[!INCLUDE[btsSettingsDashboard](../includes/btssettingsdashboard-md.md)]には、次のいずれかの方法でアクセスすることができます。</span><span class="sxs-lookup"><span data-stu-id="4d48c-117">You can access the [!INCLUDE[btsSettingsDashboard](../includes/btssettingsdashboard-md.md)] in any of the following ways:</span></span>  
  
-   <span data-ttu-id="4d48c-118">開始、 [!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)] 管理コンソールで、右クリックし **BizTalk グループ** クリックしてコンソール ツリーで **設定**します。</span><span class="sxs-lookup"><span data-stu-id="4d48c-118">Start the [!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)] Administration console, right-click **BizTalk Group** in the console tree, and then select **Settings**.</span></span>  
  
-   <span data-ttu-id="4d48c-119">下にあるすべてのホストを右クリックして、 **プラットフォームの設定** MMC とのクリックのノードの **設定**します。</span><span class="sxs-lookup"><span data-stu-id="4d48c-119">Right click any host under the **Platform Settings** node in MMC and click on **Settings**.</span></span> <span data-ttu-id="4d48c-120">これによって [!INCLUDE[btsSettingsDashboard](../includes/btssettingsdashboard-md.md)]が起動し、ホストに関連する設定を変更できます。</span><span class="sxs-lookup"><span data-stu-id="4d48c-120">This launches [!INCLUDE[btsSettingsDashboard](../includes/btssettingsdashboard-md.md)] and you can modify the settings related to that host.</span></span>  
  
-   <span data-ttu-id="4d48c-121">任意のホスト インスタンスを右クリックして、 **プラットフォームの設定** MMC とのクリックのノードの **設定**します。</span><span class="sxs-lookup"><span data-stu-id="4d48c-121">Right click any host instance under the **Platform Settings** node in MMC and click on **Settings**.</span></span> <span data-ttu-id="4d48c-122">これによって [!INCLUDE[btsSettingsDashboard](../includes/btssettingsdashboard-md.md)]が起動し、ホスト インスタンスに関連する設定を変更できます。</span><span class="sxs-lookup"><span data-stu-id="4d48c-122">This launches [!INCLUDE[btsSettingsDashboard](../includes/btssettingsdashboard-md.md)] and you can modify the settings related to that host instance.</span></span>  
  
## <a name="export-and-import-settings"></a><span data-ttu-id="4d48c-123">エクスポートし、インポートの設定</span><span class="sxs-lookup"><span data-stu-id="4d48c-123">Export and import settings</span></span>  
 <span data-ttu-id="4d48c-124">[!INCLUDE[btsSettingsDashboard](../includes/btssettingsdashboard-md.md)]では、ある [!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)] 環境から設定をエクスポートして別の [!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)] 環境にインポートすることで、問題解決までの全体的な時間を短縮できます。</span><span class="sxs-lookup"><span data-stu-id="4d48c-124">The [!INCLUDE[btsSettingsDashboard](../includes/btssettingsdashboard-md.md)] can be used to export settings from a [!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)] environment and import it into another [!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)] environment, thereby reducing the overall time-to-solution.</span></span> <span data-ttu-id="4d48c-125">この機能は、管理者がテスト環境で [!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)] のパフォーマンスを調整するシナリオで特に役立ちます。管理者は、希望の結果を達成すると同時に、その設定を運用環境にインポートできます。</span><span class="sxs-lookup"><span data-stu-id="4d48c-125">This is especially useful in scenarios where the administrators try to tune [!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)] performance in a test environment, and upon achieving the desired results, they can import the settings into a production environment.</span></span>  
  
 <span data-ttu-id="4d48c-126">インポート/エクスポートを使用する方法については、[!INCLUDE[btsSettingsDashboard](../includes/btssettingsdashboard-md.md)]ユーザー インターフェイスを参照してください[インポートまたはエクスポート BizTalk の設定を使用して設定のダッシュ ボード](how-to-import-biztalk-settings-using-settings-dashboard.md)です。</span><span class="sxs-lookup"><span data-stu-id="4d48c-126">For information about how to import/export using the [!INCLUDE[btsSettingsDashboard](../includes/btssettingsdashboard-md.md)] user interface, see [Import or export BizTalk Settings Using Settings Dashboard](how-to-import-biztalk-settings-using-settings-dashboard.md).</span></span>
  
## <a name="scripting-support"></a><span data-ttu-id="4d48c-127">スクリプトのサポート</span><span class="sxs-lookup"><span data-stu-id="4d48c-127">Scripting support</span></span>
 <span data-ttu-id="4d48c-128">[!INCLUDE[btsSettingsDashboard](../includes/btssettingsdashboard-md.md)]では、BizTalk の設定を管理するための集中型のユーザー インターフェイスを利用できるだけでなく、すべての設定およびインポート/エクスポートのタスクに API とコマンドライン オプションをとおしてアクセスすることもできます。</span><span class="sxs-lookup"><span data-stu-id="4d48c-128">The [!INCLUDE[btsSettingsDashboard](../includes/btssettingsdashboard-md.md)] not only provides a central user interface to manage BizTalk settings but also ensures that all settings and the import/export tasks are accessible via APIs and command-line options.</span></span> <span data-ttu-id="4d48c-129">これによって BizTalk Server 管理者は、BizTalk Server の設定に関連したタスクを自動化できます。</span><span class="sxs-lookup"><span data-stu-id="4d48c-129">This enables BizTalk Server administrators to automate tasks related to BizTalk Server settings.</span></span> <span data-ttu-id="4d48c-130">スクリプトのサポートによって、次のことも可能になります。</span><span class="sxs-lookup"><span data-stu-id="4d48c-130">As part of the scripting support:</span></span>  
  
-   <span data-ttu-id="4d48c-131">すべてのグループ設定は、WMI クラス `MSBTS_GroupSetting` をとおしてアクセスおよび変更できます。</span><span class="sxs-lookup"><span data-stu-id="4d48c-131">All group settings can be accessed and modified via the WMI Class: `MSBTS_GroupSetting`</span></span>  
  
-   <span data-ttu-id="4d48c-132">すべてのホスト設定は、WMI クラス `MSBTS_HostSetting` をとおしてアクセスおよび変更できます。</span><span class="sxs-lookup"><span data-stu-id="4d48c-132">All host settings can be accessed and modified via the WMI Class: `MSBTS_HostSetting`</span></span>  
  
-   <span data-ttu-id="4d48c-133">すべてのホスト インスタンス設定は、WMI クラス `MSBTS_HostInstanceSetting` をとおしてアクセスおよび変更できます。</span><span class="sxs-lookup"><span data-stu-id="4d48c-133">All host instance settings can be accessed and modified via the WMI Class: `MSBTS_HostInstanceSetting`</span></span>  
  
-   <span data-ttu-id="4d48c-134">インポートとエクスポート操作経由でアクセスできる **BTSTask.exe** コマンド: `ExportSettings` と `ImportSettings`</span><span class="sxs-lookup"><span data-stu-id="4d48c-134">Import and export operations can be accessed through **BTSTask.exe** commands: `ExportSettings` and `ImportSettings`</span></span>  
  
 <span data-ttu-id="4d48c-135">BTSTask.exe コマンドライン ユーティリティを使用してインポート/エクスポートする方法の詳細については、「[インポートまたはエクスポート BizTalk の設定を使用して BTSTask](how-to-import-biztalk-settings-using-btstask.md)です。</span><span class="sxs-lookup"><span data-stu-id="4d48c-135">For details about how to import/export using the BTSTask.exe command-line utility, see [Import or export BizTalk Settings Using BTSTask](how-to-import-biztalk-settings-using-btstask.md).</span></span>  
  
## <a name="next"></a><span data-ttu-id="4d48c-136">Next</span><span class="sxs-lookup"><span data-stu-id="4d48c-136">Next</span></span>  
  
-   [<span data-ttu-id="4d48c-137">BizTalk Server パフォーマンス チューニングのための設定ダッシュボードの使用</span><span class="sxs-lookup"><span data-stu-id="4d48c-137">Use Settings Dashboard for BizTalk Server Performance Tuning</span></span>](../core/using-settings-dashboard-for-biztalk-server-performance-tuning.md)  
  
-   [<span data-ttu-id="4d48c-138">BizTalk Server パフォーマンス チューニングの自動化</span><span class="sxs-lookup"><span data-stu-id="4d48c-138">Automate BizTalk Server Performance Tuning</span></span>](../core/automating-biztalk-server-performance-tuning.md)  
  
## <a name="see-also"></a><span data-ttu-id="4d48c-139">参照</span><span class="sxs-lookup"><span data-stu-id="4d48c-139">See Also</span></span>  
 [<span data-ttu-id="4d48c-140">BizTalk Server の管理</span><span class="sxs-lookup"><span data-stu-id="4d48c-140">Manage BizTalk Server</span></span>](../core/use-groups-create-artifacts-optimize-performance-and-more-in-biztalk-server.md)