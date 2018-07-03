---
title: ホスト インスタンスの監視 |Microsoft Docs
ms.custom: ''
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: ''
ms.suite: ''
ms.tgt_pltfrm: ''
ms.topic: article
ms.assetid: 4e7c6b80-7371-46ea-bf9c-82acb22012a3
caps.latest.revision: 2
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: 91ad5ec158466db6716b515fe3d34ae76c4cde0f
ms.sourcegitcommit: 266308ec5c6a9d8d80ff298ee6051b4843c5d626
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 06/27/2018
ms.locfileid: "37003339"
---
# <a name="monitoring-host-instances"></a><span data-ttu-id="10e4c-102">ホスト インスタンスの監視</span><span class="sxs-lookup"><span data-stu-id="10e4c-102">Monitoring Host Instances</span></span>
<span data-ttu-id="10e4c-103">このトピックでは、Microsoft System Center Operations Manager を使用して BizTalk ホスト インスタンスの監視について説明します。</span><span class="sxs-lookup"><span data-stu-id="10e4c-103">This topic describes monitoring BizTalk host instances using Microsoft System Center Operations Manager.</span></span>  
  
## <a name="using-threshold-rules-to-monitor-health"></a><span data-ttu-id="10e4c-104">しきい値規則を使用して、正常性を監視するには</span><span class="sxs-lookup"><span data-stu-id="10e4c-104">Using Threshold Rules to Monitor Health</span></span>  
 <span data-ttu-id="10e4c-105">BizTalk Server 管理パックには、BizTalk ホストの正常性の包括的なビューを提供するパフォーマンスしきい値ルールが組み込まれています。</span><span class="sxs-lookup"><span data-stu-id="10e4c-105">The BizTalk Server Management Pack incorporates performance threshold rules that provide a comprehensive view of the health of the BizTalk hosts.</span></span> <span data-ttu-id="10e4c-106">次の 2 種類のしきい値ルールがあります。</span><span class="sxs-lookup"><span data-stu-id="10e4c-106">Two different types of threshold rules are provided:</span></span>  
  
- <span data-ttu-id="10e4c-107">一般的に (たとえば、すべての BizTalk ホストに、すべてのメッセージ ボックス データベースに) 適用される規則です。</span><span class="sxs-lookup"><span data-stu-id="10e4c-107">Rules that apply generically (for example, to all BizTalk hosts and to all MessageBox databases).</span></span>  
  
- <span data-ttu-id="10e4c-108">特定の BizTalk ホストに固有の規則。</span><span class="sxs-lookup"><span data-stu-id="10e4c-108">Rules that are specific to a particular BizTalk host.</span></span>  
  
  <span data-ttu-id="10e4c-109">汎用的なルールは、共通のしきい値に基づくすべての BizTalk ホストを監視します。</span><span class="sxs-lookup"><span data-stu-id="10e4c-109">Generic rules monitor all the BizTalk hosts based on a common threshold.</span></span> <span data-ttu-id="10e4c-110">たとえば、Monitor HostQ サイズ ルールは、共通のしきい値に基づくすべての BizTalk ホストの作業キューを監視します。</span><span class="sxs-lookup"><span data-stu-id="10e4c-110">For example, the rule Monitor HostQ Size monitors the work queues of all BizTalk hosts based on a common threshold.</span></span> <span data-ttu-id="10e4c-111">3 つの異なるホストがある場合は、そのすべての作業キューが、同じルールで監視し、アラートは、共通のしきい値を越えるホストの作業キューのいずれかが発生しました。</span><span class="sxs-lookup"><span data-stu-id="10e4c-111">If there are three different hosts, all their work queues are monitored by the same rule, and alerts occur when any of the host work queues cross the common threshold.</span></span>  
  
  <span data-ttu-id="10e4c-112">BizTalk ホストに固有のルールでは、さまざまなホストの別のしきい値を構成できます。</span><span class="sxs-lookup"><span data-stu-id="10e4c-112">BizTalk host-specific rules enable you to configure different thresholds for different hosts.</span></span> <span data-ttu-id="10e4c-113">[Biztalkserverapplication] – モニターの HostQ サイズのルールがあるなど、BizTalkServerApplication ホストの作業キューを監視するホスト固有の規則。</span><span class="sxs-lookup"><span data-stu-id="10e4c-113">For example, the rule Monitor HostQ Size – BizTalkServerApplication is a host-specific rule that monitors the work queue of the BizTalkServerApplication host.</span></span> <span data-ttu-id="10e4c-114">この例では、特定のパフォーマンス カウンター インスタンスの特定の Operations Manager プロバイダーを定義し、しきい値規則でそのプロバイダーを使用することができます。</span><span class="sxs-lookup"><span data-stu-id="10e4c-114">In this example you can define a specific Operations Manager provider for the particular performance counter instance and use that provider in the threshold rule.</span></span> <span data-ttu-id="10e4c-115">これらの規則は、ホスト固有であるために、新しく作成された各ホストに固有のルールを定義する必要があります。</span><span class="sxs-lookup"><span data-stu-id="10e4c-115">Because these rules are host-specific, you must define rules specific to each newly created host.</span></span>  
  
  <span data-ttu-id="10e4c-116">BizTalk ホストに固有のルールは、環境内で適用可能なルールを作成するためのテンプレート規則に提供されます。</span><span class="sxs-lookup"><span data-stu-id="10e4c-116">BizTalk host-specific rules are provided as template rules for creating rules that are applicable in your environment.</span></span> <span data-ttu-id="10e4c-117">既定では、すべてのしきい値監視ルールが無効に設定されています。</span><span class="sxs-lookup"><span data-stu-id="10e4c-117">All threshold monitoring rules are disabled by default:</span></span>  
  
- <span data-ttu-id="10e4c-118">環境内に特定のしきい値の値を汎用的なルールを構成する必要があります。</span><span class="sxs-lookup"><span data-stu-id="10e4c-118">You should configure generic rules with threshold values specific to your environment.</span></span>  
  
- <span data-ttu-id="10e4c-119">テンプレート ルールと適切なしきい値に基づく BizTalk ホストに固有のルールを作成する必要があります。</span><span class="sxs-lookup"><span data-stu-id="10e4c-119">You should create BizTalk host-specific rules based on the template rules and appropriate thresholds.</span></span>  
  
## <a name="monitoring-biztalk-host-instances"></a><span data-ttu-id="10e4c-120">BizTalk ホスト インスタンスの監視</span><span class="sxs-lookup"><span data-stu-id="10e4c-120">Monitoring BizTalk Host Instances</span></span>  
 <span data-ttu-id="10e4c-121">特定の BizTalk ホストを対象とするルールは、監視の観点からはより柔軟です。</span><span class="sxs-lookup"><span data-stu-id="10e4c-121">Rules that target specific BizTalk hosts are more flexible from a monitoring perspective.</span></span> <span data-ttu-id="10e4c-122">BizTalk Server 管理パックに用意されている BizTalkServerApplication ホストのすべてのしきい値監視ルールは、テンプレート規則です。</span><span class="sxs-lookup"><span data-stu-id="10e4c-122">All threshold monitoring rules for the BizTalkServerApplication host provided in the BizTalk Server Management pack are template rules.</span></span> <span data-ttu-id="10e4c-123">これらの規則を使用するに Operations Manager 管理者コンソールを使用する必要があります。</span><span class="sxs-lookup"><span data-stu-id="10e4c-123">In order to use these rules, you should use the Operations Manager Administrator console to:</span></span>  
  
- <span data-ttu-id="10e4c-124">[!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)] ルール グループのテンプレート ルールのコピーを作成して、その名前を変更します。</span><span class="sxs-lookup"><span data-stu-id="10e4c-124">Create a copy of the template rule in the [!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)] rule group and rename it.</span></span>  
  
- <span data-ttu-id="10e4c-125">BizTalk ホスト固有のパフォーマンス カウンターのインスタンス用の新しい Operations Manager プロバイダーを作成します。</span><span class="sxs-lookup"><span data-stu-id="10e4c-125">Create a new Operations Manager provider for the BizTalk host-specific performance counter instance.</span></span>  
  
- <span data-ttu-id="10e4c-126">ルールで使用される Operations Manager のプロバイダーを変更し、新しい 1 つをポイントします。</span><span class="sxs-lookup"><span data-stu-id="10e4c-126">Modify the Operations Manager provider used by the rule and point it to the new one.</span></span>  
  
  <span data-ttu-id="10e4c-127">たとえば、[!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)]インストール BizTalk ホストの ReceiveHost があり、このホストのホスト キューのサイズを監視します。</span><span class="sxs-lookup"><span data-stu-id="10e4c-127">Suppose your [!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)] installation has a BizTalk host ReceiveHost and you want to monitor the Host Queue size for this host.</span></span> <span data-ttu-id="10e4c-128">この場合、BizTalk ホスト キュー サイズのパフォーマンス カウンターの ReceiveHost インスタンスに基づいて Operations Manager プロバイダーを作成する必要があります。</span><span class="sxs-lookup"><span data-stu-id="10e4c-128">In this case, you should create a Operations Manager provider based on the ReceiveHost instance of the performance counter for the queue size for the BizTalk host.</span></span> <span data-ttu-id="10e4c-129">また、ルールのしきい値を、使用する環境に応じて設定する必要があります。</span><span class="sxs-lookup"><span data-stu-id="10e4c-129">You should also set the threshold value in the rule appropriately for your environment.</span></span>  
  
  <span data-ttu-id="10e4c-130">ホスト固有のしきい値監視ルールを使用している場合は、汎用的な監視ルールを無効にする必要があります。</span><span class="sxs-lookup"><span data-stu-id="10e4c-130">If you are using host-specific threshold monitoring rules, you should disable generic monitoring rules.</span></span> <span data-ttu-id="10e4c-131">これにより、冗長な警告が防止されます。</span><span class="sxs-lookup"><span data-stu-id="10e4c-131">This prevents redundant alerts.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="10e4c-132">参照</span><span class="sxs-lookup"><span data-stu-id="10e4c-132">See Also</span></span>  
 [<span data-ttu-id="10e4c-133">System Center Operations Manager 2007 による BizTalk Server の監視</span><span class="sxs-lookup"><span data-stu-id="10e4c-133">Monitoring BizTalk Server with System Center Operations Manager 2007</span></span>](../technical-guides/monitoring-biztalk-server-with-system-center-operations-manager-2007.md)