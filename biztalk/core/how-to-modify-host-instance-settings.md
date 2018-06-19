---
title: ホスト インスタンスの設定の更新 |Microsoft ドキュメント
description: ホスト インスタンスの設定では、BizTalk Server 管理者の変更します。
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
ms.openlocfilehash: d85635f7f7a3b2cfe05abaf041cac07913b36f96
ms.sourcegitcommit: cb908c540d8f1a692d01dc8f313e16cb4b4e696d
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 09/20/2017
ms.locfileid: "22254378"
---
# <a name="update-biztalk-host-instance-settings"></a><span data-ttu-id="eb3b4-103">BizTalk ホスト インスタンス設定を更新します。</span><span class="sxs-lookup"><span data-stu-id="eb3b4-103">Update BizTalk host instance settings</span></span>

## <a name="overview"></a><span data-ttu-id="eb3b4-104">概要</span><span class="sxs-lookup"><span data-stu-id="eb3b4-104">Overview</span></span>
<span data-ttu-id="eb3b4-105">[!INCLUDE[btsSettingsDashboard](../includes/btssettingsdashboard-md.md)] を使用すると、BizTalk グループ全体にわたって、特定のホスト インスタンスの構成情報を変更することができます。</span><span class="sxs-lookup"><span data-stu-id="eb3b4-105">Using the [!INCLUDE[btsSettingsDashboard](../includes/btssettingsdashboard-md.md)], you can modify the configuration information of a given host instance, across a BizTalk group.</span></span> <span data-ttu-id="eb3b4-106">このトピックでは、[!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)] でホスト インスタンス レベルのパフォーマンスを変更するための手順を説明します。</span><span class="sxs-lookup"><span data-stu-id="eb3b4-106">This topic provides the step-by-step procedure to modify the host instance level performance settings in [!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)].</span></span>  
  
 <span data-ttu-id="eb3b4-107">多くの場合、送信元の環境の BizTalk 設定は XML ファイルとして保存されています。</span><span class="sxs-lookup"><span data-stu-id="eb3b4-107">Often you have the BizTalk settings (from a source environment) saved as an XML file.</span></span> <span data-ttu-id="eb3b4-108">この XML ファイルには、設定を送信先コンピューターにレプリケートできるようにする情報が含まれています。</span><span class="sxs-lookup"><span data-stu-id="eb3b4-108">The XML file contains information that allows you to replicate the settings on the target machine.</span></span> <span data-ttu-id="eb3b4-109">新しい値を設定する代わりに、これらの設定を設定ダッシュボードにインポートできます。</span><span class="sxs-lookup"><span data-stu-id="eb3b4-109">You can import those settings to Settings Dashboard, instead of setting up new values.</span></span> <span data-ttu-id="eb3b4-110">一方、[!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)] 用の新しい値を設定した後に、その値を XML ファイルにエクスポートし、別のコンピューターで使用することができます。</span><span class="sxs-lookup"><span data-stu-id="eb3b4-110">On the other hand, after setting up new values for [!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)], you can export them to an XML file to be used in another machine.</span></span>  
  
 <span data-ttu-id="eb3b4-111">インポートする方法について、[!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)]設定を参照してください[インポートまたはエクスポート BizTalk の設定を使用して設定のダッシュ ボード](how-to-import-biztalk-settings-using-settings-dashboard.md)と[インポートまたはエクスポート BizTalk の設定を使用して BTSTask](how-to-import-biztalk-settings-using-btstask.md)です。</span><span class="sxs-lookup"><span data-stu-id="eb3b4-111">For information on importing the [!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)] settings, see [Import or export BizTalk Settings Using Settings Dashboard](how-to-import-biztalk-settings-using-settings-dashboard.md) and [Import or export BizTalk Settings Using BTSTask](how-to-import-biztalk-settings-using-btstask.md).</span></span> 
  
## <a name="prerequisites"></a><span data-ttu-id="eb3b4-112">前提条件</span><span class="sxs-lookup"><span data-stu-id="eb3b4-112">Prerequisites</span></span>  
 <span data-ttu-id="eb3b4-113">この操作を実行するには、BizTalk Server 管理者グループのメンバーとしてサインインする必要があります。</span><span class="sxs-lookup"><span data-stu-id="eb3b4-113">To perform this operation, you must be signed in as a member of the BizTalk Server Administrators group.</span></span>  
  
## <a name="update-the-host-instance-level-settings"></a><span data-ttu-id="eb3b4-114">ホスト インスタンス レベルの設定を更新します。</span><span class="sxs-lookup"><span data-stu-id="eb3b4-114">Update the host instance level settings</span></span>  
  
1.  <span data-ttu-id="eb3b4-115">**BizTalk Server 管理コンソール**、展開[!INCLUDE[btsBizTalkServerAdminConsoleui](../includes/btsbiztalkserveradminconsoleui-md.md)]を右クリックして**BizTalk グループ**、クリックして**設定**です。</span><span class="sxs-lookup"><span data-stu-id="eb3b4-115">In the **BizTalk Server Administration Console**, expand [!INCLUDE[btsBizTalkServerAdminConsoleui](../includes/btsbiztalkserveradminconsoleui-md.md)], right-click **BizTalk Group**, and then click **Settings**.</span></span>  
  
2.  <span data-ttu-id="eb3b4-116">**BizTalk 設定ダッシュ ボード** ダイアログ ボックスで、**ホスト インスタンス** タブで、次のいずれかの操作します。</span><span class="sxs-lookup"><span data-stu-id="eb3b4-116">In the **BizTalk Settings Dashboard** dialog box, on the **Host Instances** tab, do any of the following:</span></span>  
  
    -   <span data-ttu-id="eb3b4-117">ホスト インスタンスの .NET CLR 設定を変更する。</span><span class="sxs-lookup"><span data-stu-id="eb3b4-117">Modify the .NET CLR settings for a host instance.</span></span> <span data-ttu-id="eb3b4-118">参照してください[.NET CLR 設定を変更する](../core/how-to-modify-net-clr-settings.md)です。</span><span class="sxs-lookup"><span data-stu-id="eb3b4-118">See [Change the .NET CLR Settings](../core/how-to-modify-net-clr-settings.md).</span></span>  
  
    -   <span data-ttu-id="eb3b4-119">オーケストレーション メモリ制限の設定を変更する。</span><span class="sxs-lookup"><span data-stu-id="eb3b4-119">Modify the orchestration memory throttling settings.</span></span> <span data-ttu-id="eb3b4-120">参照してください[オーケストレーション メモリ制限の設定を変更する](../core/how-to-modify-orchestration-memory-throttling-settings.md)です。</span><span class="sxs-lookup"><span data-stu-id="eb3b4-120">See [Change the Orchestration Memory Throttling Settings](../core/how-to-modify-orchestration-memory-throttling-settings.md).</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="eb3b4-121">参照</span><span class="sxs-lookup"><span data-stu-id="eb3b4-121">See Also</span></span>  
 [<span data-ttu-id="eb3b4-122">BizTalk server 設定ダッシュ ボードを使用してパフォーマンス チューニング</span><span class="sxs-lookup"><span data-stu-id="eb3b4-122">Use Settings Dashboard for BizTalk Server Performance Tuning</span></span>](../core/using-settings-dashboard-for-biztalk-server-performance-tuning.md)