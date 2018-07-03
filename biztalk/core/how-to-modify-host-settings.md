---
title: ホストの設定を変更する方法 |Microsoft Docs
description: パフォーマンスと調整を向上させるために BizTalk Server 管理コンソールでの BizTalk ホストの設定を変更します。
ms.custom: ''
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: ''
ms.suite: ''
ms.tgt_pltfrm: ''
ms.topic: article
ms.assetid: 0759b3a0-560e-4a11-92e6-9de0e15f463b
caps.latest.revision: 13
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: 93b2ea993e044d1cb18efcc73f631e8ba3fcb8ff
ms.sourcegitcommit: 266308ec5c6a9d8d80ff298ee6051b4843c5d626
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 06/27/2018
ms.locfileid: "36975843"
---
# <a name="update-biztalk-host-settings"></a><span data-ttu-id="e78ec-103">BizTalk ホストの設定を更新します。</span><span class="sxs-lookup"><span data-stu-id="e78ec-103">Update BizTalk host settings</span></span>

## <a name="overview"></a><span data-ttu-id="e78ec-104">概要</span><span class="sxs-lookup"><span data-stu-id="e78ec-104">Overview</span></span>
<span data-ttu-id="e78ec-105">設定ダッシュボードを使用して、1 つの BizTalk グループ全体で使用する特定のホストの構成情報を変更できます。</span><span class="sxs-lookup"><span data-stu-id="e78ec-105">Using the Settings Dashboard, you can modify the configuration information of a given host, across a BizTalk group.</span></span> <span data-ttu-id="e78ec-106">このトピックでは、[!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)] でホストレベルのパフォーマンス設定を変更する手順を説明します。</span><span class="sxs-lookup"><span data-stu-id="e78ec-106">This topic provides the step-by-step procedure to modify the host-level performance settings in [!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)].</span></span>  
  
> [!NOTE]
>  <span data-ttu-id="e78ec-107">グループとホスト インスタンスの設定を変更することもできます。</span><span class="sxs-lookup"><span data-stu-id="e78ec-107">You can also modify the group and host instance settings.</span></span> <span data-ttu-id="e78ec-108">設定を変更する方法については、次を参照してください。[設定ダッシュ ボードの BizTalk Server のパフォーマンス チューニングを使用して](../core/using-settings-dashboard-for-biztalk-server-performance-tuning.md)します。</span><span class="sxs-lookup"><span data-stu-id="e78ec-108">For information about how to modify the settings, see [Using Settings Dashboard for BizTalk Server Performance Tuning](../core/using-settings-dashboard-for-biztalk-server-performance-tuning.md).</span></span>  
  
 <span data-ttu-id="e78ec-109">BizTalk Server の現在の設定は XML ファイルにエクスポートできます。</span><span class="sxs-lookup"><span data-stu-id="e78ec-109">The current BizTalk Server settings can be exported to an XML file.</span></span> <span data-ttu-id="e78ec-110">後で、新しい値を設定する代わりに、これらの設定を設定ダッシュボードにインポートできます。</span><span class="sxs-lookup"><span data-stu-id="e78ec-110">Later, you can import those settings to the Settings Dashboard instead of setting up new values.</span></span> <span data-ttu-id="e78ec-111">インポートする方法についての[!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)]設定を参照してください[インポートまたはエクスポート BizTalk の設定を使用して設定のダッシュ ボード](how-to-import-biztalk-settings-using-settings-dashboard.md)と[インポートまたはエクスポート BizTalk の設定を使用して BTSTask](how-to-import-biztalk-settings-using-btstask.md)します。</span><span class="sxs-lookup"><span data-stu-id="e78ec-111">For information on importing the [!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)] settings, see [Import or export BizTalk Settings Using Settings Dashboard](how-to-import-biztalk-settings-using-settings-dashboard.md) and [Import or export BizTalk Settings Using BTSTask](how-to-import-biztalk-settings-using-btstask.md).</span></span> 
  
## <a name="prerequisites"></a><span data-ttu-id="e78ec-112">前提条件</span><span class="sxs-lookup"><span data-stu-id="e78ec-112">Prerequisites</span></span>  
 <span data-ttu-id="e78ec-113">この操作を実行するには、BizTalk Server 管理者グループのメンバーとしてサインインする必要があります。</span><span class="sxs-lookup"><span data-stu-id="e78ec-113">To perform this operation, you must be signed in as a member of the BizTalk Server Administrators group.</span></span>  
  
## <a name="update-the-host-level-settings"></a><span data-ttu-id="e78ec-114">ホスト レベルの設定を更新します。</span><span class="sxs-lookup"><span data-stu-id="e78ec-114">Update the host-level settings</span></span>  
  
1. <span data-ttu-id="e78ec-115">**BizTalk Server 管理コンソール**、展開[!INCLUDE[btsBizTalkServerAdminConsoleui](../includes/btsbiztalkserveradminconsoleui-md.md)]を右クリックして**BizTalk グループ**、 をクリックし、**設定**します。</span><span class="sxs-lookup"><span data-stu-id="e78ec-115">In the **BizTalk Server Administration Console**, expand [!INCLUDE[btsBizTalkServerAdminConsoleui](../includes/btsbiztalkserveradminconsoleui-md.md)], right-click **BizTalk Group**, and then click **Settings**.</span></span>  
  
2. <span data-ttu-id="e78ec-116">**BizTalk 設定ダッシュ ボード** ダイアログ ボックスで、**ホスト**ページで、次の 1 つ以上の操作を行います。</span><span class="sxs-lookup"><span data-stu-id="e78ec-116">In the **BizTalk Settings Dashboard** dialog box, on the **Hosts** page, do one or more of the following.</span></span>  
  
   -   <span data-ttu-id="e78ec-117">BizTalk ホストのパフォーマンスの全般的な設定を変更します。</span><span class="sxs-lookup"><span data-stu-id="e78ec-117">Modify the general performance settings of the BizTalk host.</span></span> <span data-ttu-id="e78ec-118">参照してください[全般設定を変更する方法](../core/how-to-modify-general-settings.md)します。</span><span class="sxs-lookup"><span data-stu-id="e78ec-118">See [How to Modify General Settings](../core/how-to-modify-general-settings.md).</span></span>  
  
   -   <span data-ttu-id="e78ec-119">BizTalk ホストのリソースベースでの制限の設定を変更します。</span><span class="sxs-lookup"><span data-stu-id="e78ec-119">Modify the resource-based throttling settings of the BizTalk host.</span></span> <span data-ttu-id="e78ec-120">参照してください[ベースの制限の設定をリソースを変更する方法](../core/how-to-modify-resource-based-throttling-settings.md)します。</span><span class="sxs-lookup"><span data-stu-id="e78ec-120">See [How to Modify Resource Based Throttling Settings](../core/how-to-modify-resource-based-throttling-settings.md).</span></span>  
  
   -   <span data-ttu-id="e78ec-121">BizTalk ホストの比率ベースのスロットル設定を変更します。</span><span class="sxs-lookup"><span data-stu-id="e78ec-121">Modify the rate-based throttling settings of the BizTalk host.</span></span> <span data-ttu-id="e78ec-122">参照してください[レートを変更する方法は、制限の設定をベース](../core/how-to-modify-rate-based-throttling-settings.md)します。</span><span class="sxs-lookup"><span data-stu-id="e78ec-122">See [How to Modify Rate Based Throttling Settings](../core/how-to-modify-rate-based-throttling-settings.md).</span></span>  
  
   -   <span data-ttu-id="e78ec-123">BizTalk ホストのオーケストレーション制限の設定を変更します。</span><span class="sxs-lookup"><span data-stu-id="e78ec-123">Modify the orchestration throttling settings of the BizTalk host.</span></span> <span data-ttu-id="e78ec-124">参照してください[オーケストレーション制限の設定を変更する方法](../core/how-to-modify-orchestration-throttling-settings.md)します。</span><span class="sxs-lookup"><span data-stu-id="e78ec-124">See [How to Modify Orchestration Throttling Settings](../core/how-to-modify-orchestration-throttling-settings.md).</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="e78ec-125">参照</span><span class="sxs-lookup"><span data-stu-id="e78ec-125">See Also</span></span>  
 [<span data-ttu-id="e78ec-126">BizTalk Server パフォーマンス チューニングのための設定ダッシュボードの使用</span><span class="sxs-lookup"><span data-stu-id="e78ec-126">Use Settings Dashboard for BizTalk Server Performance Tuning</span></span>](../core/using-settings-dashboard-for-biztalk-server-performance-tuning.md)