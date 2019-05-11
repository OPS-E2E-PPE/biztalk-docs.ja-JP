---
title: BizTalk server 設定ダッシュ ボードを使用してパフォーマンスのチューニング |Microsoft Docs
description: BizTalk Server 管理の設定ダッシュ ボードを使用して、グループ、ホスト、およびホスト インスタンスの設定を更新するには
ms.custom: ''
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: ''
ms.suite: ''
ms.tgt_pltfrm: ''
ms.topic: article
ms.assetid: 3bb1ddac-1e8f-4928-9c70-8326ae64a734
caps.latest.revision: 7
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: b906ccae0e17d79f5783a3689a517fe4cba310ba
ms.sourcegitcommit: 381e83d43796a345488d54b3f7413e11d56ad7be
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 05/07/2019
ms.locfileid: "65395392"
---
# <a name="use-settings-dashboard-for-biztalk-server-performance-tuning"></a><span data-ttu-id="b7521-103">BizTalk server 設定ダッシュ ボードを使用してパフォーマンス チューニング</span><span class="sxs-lookup"><span data-stu-id="b7521-103">Use Settings Dashboard for BizTalk Server Performance Tuning</span></span>

## <a name="overview"></a><span data-ttu-id="b7521-104">概要</span><span class="sxs-lookup"><span data-stu-id="b7521-104">Overview</span></span>
<span data-ttu-id="b7521-105">設定ダッシュボードを使用して、[!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)] のさまざまな設定を微調整してパフォーマンスを最適化することができます。</span><span class="sxs-lookup"><span data-stu-id="b7521-105">Using the Settings Dashboard, you can extensively tweak [!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)] settings for performance optimization.</span></span> <span data-ttu-id="b7521-106">BizTalk グループ、BizTalk ホスト、および BizTalk ホスト インスタンスの設定を変更することもできます。</span><span class="sxs-lookup"><span data-stu-id="b7521-106">You can also modify settings for the BizTalk Group, BizTalk Host, and BizTalk Host Instance.</span></span>  
  
- <span data-ttu-id="b7521-107">**グループ レベル設定**:グループ レベルで使用することができます、[!INCLUDE[btsSettingsDashboard](../includes/btssettingsdashboard-md.md)]などの構成の更新間隔、最大メッセージ バッチ サイズ、グループ レベルの追跡などのプロパティを設定します。これらの設定は、BizTalk グループのすべてのマシンに適用されます。</span><span class="sxs-lookup"><span data-stu-id="b7521-107">**Group-level settings**: At the group level, you can use the [!INCLUDE[btsSettingsDashboard](../includes/btssettingsdashboard-md.md)] to set properties like the configuration refresh interval, maximum message batch size, group level tracking, etc. These settings are applied to all machines in a BizTalk Group.</span></span>  
  
- <span data-ttu-id="b7521-108">**ホスト レベルの設定**:ホスト レベルでは、ホストの追跡、リソース ベースの制限、メッセージ処理の制限に関連するプロパティに関連するプロパティ、およびオーケストレーションの制限に関連するプロパティなどの設定を変更できます。</span><span class="sxs-lookup"><span data-stu-id="b7521-108">**Host-level settings**: At the host level, you can modify settings like host tracking, properties related to resource based throttling, properties related to message process throttling, and properties related to orchestrations throttling.</span></span> <span data-ttu-id="b7521-109">これらの設定は、選択したホストのすべてのインスタンスに適用されます。</span><span class="sxs-lookup"><span data-stu-id="b7521-109">These settings are applied to all instances of the selected host.</span></span>  
  
- <span data-ttu-id="b7521-110">**インスタンス レベルの設定をホスト**:ホスト インスタンス レベルでは、.NET CLR 設定やオーケストレーション メモリ制限に関連するプロパティを変更することができます。</span><span class="sxs-lookup"><span data-stu-id="b7521-110">**Host instance level settings**: At the host instance level, you can modify .NET CLR settings and properties related to orchestration memory throttling.</span></span> <span data-ttu-id="b7521-111">これらの設定は、選択したホスト インスタンスにのみ適用されます。</span><span class="sxs-lookup"><span data-stu-id="b7521-111">These settings are applied to only the selected host instance.</span></span>  
  
  <span data-ttu-id="b7521-112">BizTalk グループ、BizTalk ホスト、および BizTalk ホスト インスタンスの設定の詳細については、次を参照してください[グループ設定を変更する方法](../core/how-to-modify-group-settings.md)、[ホスト設定の変更方法](../core/how-to-modify-host-settings.md)、および[ホストを変更する方法。設定インスタンス](../core/how-to-modify-host-instance-settings.md)します。</span><span class="sxs-lookup"><span data-stu-id="b7521-112">For more information about BizTalk Group, BizTalk Host, and BizTalk Host Instance settings, see [How to Modify Group Settings](../core/how-to-modify-group-settings.md), [How to Modify Host Settings](../core/how-to-modify-host-settings.md), and [How to Modify Host Instance Settings](../core/how-to-modify-host-instance-settings.md).</span></span>  
  
  <span data-ttu-id="b7521-113">設定ダッシュボードによって、同じである必要がない複数の展開で BizTalk の設定をインポート/エクスポートすることができます。</span><span class="sxs-lookup"><span data-stu-id="b7521-113">The Settings Dashboard enables you to import/export BizTalk settings across deployments that need not be identical.</span></span> <span data-ttu-id="b7521-114">ユーザー インターフェイスを使用して、ターゲットとソースの展開の間でホストとホスト インスタンスをマップできます。</span><span class="sxs-lookup"><span data-stu-id="b7521-114">Using the user interface, you can map the hosts and host instances from destination to source deployments.</span></span> <span data-ttu-id="b7521-115">これによって、ホスト名、コンピューター名、またはそれぞれの数が異なる環境に設定を適用できます。</span><span class="sxs-lookup"><span data-stu-id="b7521-115">This helps you apply settings to an environment where host and machine names, or their respective counts, are different.</span></span> <span data-ttu-id="b7521-116">BizTalk の設定のインポート/エクスポートの詳細については、次を参照してください。[インポートまたはエクスポート BizTalk の設定を使用して設定のダッシュ ボード](how-to-import-biztalk-settings-using-settings-dashboard.md)します。</span><span class="sxs-lookup"><span data-stu-id="b7521-116">For more details about importing/exporting BizTalk settings, see [Import or export BizTalk Settings Using Settings Dashboard](how-to-import-biztalk-settings-using-settings-dashboard.md).</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="b7521-117">参照</span><span class="sxs-lookup"><span data-stu-id="b7521-117">See Also</span></span>  
 [<span data-ttu-id="b7521-118">BizTalk Server パフォーマンス設定を管理します。</span><span class="sxs-lookup"><span data-stu-id="b7521-118">Manage BizTalk Server Performance Settings</span></span>](../core/managing-biztalk-server-performance-settings.md)