---
title: ホスト インスタンスの設定の更新 |Microsoft Docs
description: ホスト インスタンス設定では、BizTalk Server 管理者を変更します。
ms.custom: ''
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: ''
ms.suite: ''
ms.tgt_pltfrm: ''
ms.topic: article
ms.assetid: 2338255b-cc13-4f6a-86c3-9ecc666c43e5
caps.latest.revision: 8
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: 6102e4cce6a850c7e2ed5656a8fd5aacfd5d5a09
ms.sourcegitcommit: 266308ec5c6a9d8d80ff298ee6051b4843c5d626
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 06/27/2018
ms.locfileid: "37011715"
---
# <a name="update-biztalk-host-instance-settings"></a><span data-ttu-id="f11a0-103">BizTalk ホスト インスタンス設定を更新します。</span><span class="sxs-lookup"><span data-stu-id="f11a0-103">Update BizTalk host instance settings</span></span>

## <a name="overview"></a><span data-ttu-id="f11a0-104">概要</span><span class="sxs-lookup"><span data-stu-id="f11a0-104">Overview</span></span>
<span data-ttu-id="f11a0-105">[!INCLUDE[btsSettingsDashboard](../includes/btssettingsdashboard-md.md)] を使用すると、BizTalk グループ全体にわたって、特定のホスト インスタンスの構成情報を変更することができます。</span><span class="sxs-lookup"><span data-stu-id="f11a0-105">Using the [!INCLUDE[btsSettingsDashboard](../includes/btssettingsdashboard-md.md)], you can modify the configuration information of a given host instance, across a BizTalk group.</span></span> <span data-ttu-id="f11a0-106">このトピックでは、[!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)] でホスト インスタンス レベルのパフォーマンスを変更するための手順を説明します。</span><span class="sxs-lookup"><span data-stu-id="f11a0-106">This topic provides the step-by-step procedure to modify the host instance level performance settings in [!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)].</span></span>  
  
 <span data-ttu-id="f11a0-107">多くの場合、送信元の環境の BizTalk 設定は XML ファイルとして保存されています。</span><span class="sxs-lookup"><span data-stu-id="f11a0-107">Often you have the BizTalk settings (from a source environment) saved as an XML file.</span></span> <span data-ttu-id="f11a0-108">この XML ファイルには、設定を送信先コンピューターにレプリケートできるようにする情報が含まれています。</span><span class="sxs-lookup"><span data-stu-id="f11a0-108">The XML file contains information that allows you to replicate the settings on the target machine.</span></span> <span data-ttu-id="f11a0-109">新しい値を設定する代わりに、これらの設定を設定ダッシュボードにインポートできます。</span><span class="sxs-lookup"><span data-stu-id="f11a0-109">You can import those settings to Settings Dashboard, instead of setting up new values.</span></span> <span data-ttu-id="f11a0-110">一方、[!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)] 用の新しい値を設定した後に、その値を XML ファイルにエクスポートし、別のコンピューターで使用することができます。</span><span class="sxs-lookup"><span data-stu-id="f11a0-110">On the other hand, after setting up new values for [!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)], you can export them to an XML file to be used in another machine.</span></span>  
  
 <span data-ttu-id="f11a0-111">インポートする方法についての[!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)]設定を参照してください[インポートまたはエクスポート BizTalk の設定を使用して設定のダッシュ ボード](how-to-import-biztalk-settings-using-settings-dashboard.md)と[インポートまたはエクスポート BizTalk の設定を使用して BTSTask](how-to-import-biztalk-settings-using-btstask.md)します。</span><span class="sxs-lookup"><span data-stu-id="f11a0-111">For information on importing the [!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)] settings, see [Import or export BizTalk Settings Using Settings Dashboard](how-to-import-biztalk-settings-using-settings-dashboard.md) and [Import or export BizTalk Settings Using BTSTask](how-to-import-biztalk-settings-using-btstask.md).</span></span> 
  
## <a name="prerequisites"></a><span data-ttu-id="f11a0-112">前提条件</span><span class="sxs-lookup"><span data-stu-id="f11a0-112">Prerequisites</span></span>  
 <span data-ttu-id="f11a0-113">この操作を実行するには、BizTalk Server 管理者グループのメンバーとしてサインインする必要があります。</span><span class="sxs-lookup"><span data-stu-id="f11a0-113">To perform this operation, you must be signed in as a member of the BizTalk Server Administrators group.</span></span>  
  
## <a name="update-the-host-instance-level-settings"></a><span data-ttu-id="f11a0-114">ホスト インスタンス レベルの設定を更新します。</span><span class="sxs-lookup"><span data-stu-id="f11a0-114">Update the host instance level settings</span></span>  
  
1. <span data-ttu-id="f11a0-115">**BizTalk Server 管理コンソール**、展開[!INCLUDE[btsBizTalkServerAdminConsoleui](../includes/btsbiztalkserveradminconsoleui-md.md)]を右クリックして**BizTalk グループ**、 をクリックし、**設定**します。</span><span class="sxs-lookup"><span data-stu-id="f11a0-115">In the **BizTalk Server Administration Console**, expand [!INCLUDE[btsBizTalkServerAdminConsoleui](../includes/btsbiztalkserveradminconsoleui-md.md)], right-click **BizTalk Group**, and then click **Settings**.</span></span>  
  
2. <span data-ttu-id="f11a0-116">**BizTalk 設定ダッシュ ボード** ダイアログ ボックスの 、**ホスト インスタンス** タブで、次のいずれかの操作を行います。</span><span class="sxs-lookup"><span data-stu-id="f11a0-116">In the **BizTalk Settings Dashboard** dialog box, on the **Host Instances** tab, do any of the following:</span></span>  
  
   -   <span data-ttu-id="f11a0-117">ホスト インスタンスの .NET CLR 設定を変更する。</span><span class="sxs-lookup"><span data-stu-id="f11a0-117">Modify the .NET CLR settings for a host instance.</span></span> <span data-ttu-id="f11a0-118">参照してください[.NET CLR 設定を変更する](../core/how-to-modify-net-clr-settings.md)します。</span><span class="sxs-lookup"><span data-stu-id="f11a0-118">See [Change the .NET CLR Settings](../core/how-to-modify-net-clr-settings.md).</span></span>  
  
   -   <span data-ttu-id="f11a0-119">オーケストレーション メモリ制限の設定を変更する。</span><span class="sxs-lookup"><span data-stu-id="f11a0-119">Modify the orchestration memory throttling settings.</span></span> <span data-ttu-id="f11a0-120">参照してください[オーケストレーション メモリ制限の設定を変更する](../core/how-to-modify-orchestration-memory-throttling-settings.md)します。</span><span class="sxs-lookup"><span data-stu-id="f11a0-120">See [Change the Orchestration Memory Throttling Settings](../core/how-to-modify-orchestration-memory-throttling-settings.md).</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="f11a0-121">参照</span><span class="sxs-lookup"><span data-stu-id="f11a0-121">See Also</span></span>  
 [<span data-ttu-id="f11a0-122">BizTalk Server パフォーマンス チューニングのための設定ダッシュボードの使用</span><span class="sxs-lookup"><span data-stu-id="f11a0-122">Use Settings Dashboard for BizTalk Server Performance Tuning</span></span>](../core/using-settings-dashboard-for-biztalk-server-performance-tuning.md)