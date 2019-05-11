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
ms.openlocfilehash: 9da52cf639cac369198e6fadc9c79dc7e2290a31
ms.sourcegitcommit: 381e83d43796a345488d54b3f7413e11d56ad7be
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 05/07/2019
ms.locfileid: "65305549"
---
# <a name="monitoring-host-instances"></a><span data-ttu-id="472e0-102">ホスト インスタンスの監視</span><span class="sxs-lookup"><span data-stu-id="472e0-102">Monitoring Host Instances</span></span>
<span data-ttu-id="472e0-103">このトピックでは、Microsoft System Center Operations Manager を使用して BizTalk ホスト インスタンスの監視について説明します。</span><span class="sxs-lookup"><span data-stu-id="472e0-103">This topic describes monitoring BizTalk host instances using Microsoft System Center Operations Manager.</span></span>  
  
## <a name="using-threshold-rules-to-monitor-health"></a><span data-ttu-id="472e0-104">しきい値規則を使用して、正常性を監視するには</span><span class="sxs-lookup"><span data-stu-id="472e0-104">Using Threshold Rules to Monitor Health</span></span>  
 <span data-ttu-id="472e0-105">BizTalk Server 管理パックには、BizTalk ホストの正常性の包括的なビューを提供するパフォーマンスしきい値ルールが組み込まれています。</span><span class="sxs-lookup"><span data-stu-id="472e0-105">The BizTalk Server Management Pack incorporates performance threshold rules that provide a comprehensive view of the health of the BizTalk hosts.</span></span> <span data-ttu-id="472e0-106">しきい値規則の 2 つのさまざまな種類が用意されています。</span><span class="sxs-lookup"><span data-stu-id="472e0-106">Two different types of threshold rules are provided:</span></span>  
  
- <span data-ttu-id="472e0-107">一般的に (たとえば、すべての BizTalk ホストに、すべてのメッセージ ボックス データベースに) 適用される規則です。</span><span class="sxs-lookup"><span data-stu-id="472e0-107">Rules that apply generically (for example, to all BizTalk hosts and to all MessageBox databases).</span></span>  
  
- <span data-ttu-id="472e0-108">特定の BizTalk ホストに固有の規則。</span><span class="sxs-lookup"><span data-stu-id="472e0-108">Rules that are specific to a particular BizTalk host.</span></span>  
  
  <span data-ttu-id="472e0-109">汎用的なルールは、共通のしきい値に基づくすべての BizTalk ホストを監視します。</span><span class="sxs-lookup"><span data-stu-id="472e0-109">Generic rules monitor all the BizTalk hosts based on a common threshold.</span></span> <span data-ttu-id="472e0-110">たとえば、Monitor HostQ サイズ ルールは、共通のしきい値に基づくすべての BizTalk ホストの作業キューを監視します。</span><span class="sxs-lookup"><span data-stu-id="472e0-110">For example, the rule Monitor HostQ Size monitors the work queues of all BizTalk hosts based on a common threshold.</span></span> <span data-ttu-id="472e0-111">3 つの異なるホストがある場合は、そのすべての作業キューが、同じルールで監視し、アラートは、共通のしきい値を越えるホストの作業キューのいずれかが発生しました。</span><span class="sxs-lookup"><span data-stu-id="472e0-111">If there are three different hosts, all their work queues are monitored by the same rule, and alerts occur when any of the host work queues cross the common threshold.</span></span>  
  
  <span data-ttu-id="472e0-112">BizTalk ホストに固有のルールでは、さまざまなホストの別のしきい値を構成できます。</span><span class="sxs-lookup"><span data-stu-id="472e0-112">BizTalk host-specific rules enable you to configure different thresholds for different hosts.</span></span> <span data-ttu-id="472e0-113">[Biztalkserverapplication] – モニターの HostQ サイズのルールがあるなど、BizTalkServerApplication ホストの作業キューを監視するホスト固有の規則。</span><span class="sxs-lookup"><span data-stu-id="472e0-113">For example, the rule Monitor HostQ Size – BizTalkServerApplication is a host-specific rule that monitors the work queue of the BizTalkServerApplication host.</span></span> <span data-ttu-id="472e0-114">この例では、特定のパフォーマンス カウンター インスタンスの特定の Operations Manager プロバイダーを定義し、しきい値規則でそのプロバイダーを使用することができます。</span><span class="sxs-lookup"><span data-stu-id="472e0-114">In this example you can define a specific Operations Manager provider for the particular performance counter instance and use that provider in the threshold rule.</span></span> <span data-ttu-id="472e0-115">これらの規則は、ホスト固有であるために、新しく作成された各ホストに固有のルールを定義する必要があります。</span><span class="sxs-lookup"><span data-stu-id="472e0-115">Because these rules are host-specific, you must define rules specific to each newly created host.</span></span>  
  
  <span data-ttu-id="472e0-116">BizTalk ホストに固有のルールは、環境内で適用可能なルールを作成するためのテンプレート規則に提供されます。</span><span class="sxs-lookup"><span data-stu-id="472e0-116">BizTalk host-specific rules are provided as template rules for creating rules that are applicable in your environment.</span></span> <span data-ttu-id="472e0-117">既定では、すべてのしきい値監視ルールが無効にします。</span><span class="sxs-lookup"><span data-stu-id="472e0-117">All threshold monitoring rules are disabled by default:</span></span>  
  
- <span data-ttu-id="472e0-118">環境内に特定のしきい値の値を汎用的なルールを構成する必要があります。</span><span class="sxs-lookup"><span data-stu-id="472e0-118">You should configure generic rules with threshold values specific to your environment.</span></span>  
  
- <span data-ttu-id="472e0-119">テンプレート ルールと適切なしきい値に基づく BizTalk ホストに固有のルールを作成する必要があります。</span><span class="sxs-lookup"><span data-stu-id="472e0-119">You should create BizTalk host-specific rules based on the template rules and appropriate thresholds.</span></span>  
  
## <a name="monitoring-biztalk-host-instances"></a><span data-ttu-id="472e0-120">BizTalk ホスト インスタンスの監視</span><span class="sxs-lookup"><span data-stu-id="472e0-120">Monitoring BizTalk Host Instances</span></span>  
 <span data-ttu-id="472e0-121">特定の BizTalk ホストを対象とするルールは、監視の観点からはより柔軟です。</span><span class="sxs-lookup"><span data-stu-id="472e0-121">Rules that target specific BizTalk hosts are more flexible from a monitoring perspective.</span></span> <span data-ttu-id="472e0-122">BizTalk Server 管理パックに用意されている BizTalkServerApplication ホストのすべてのしきい値監視ルールは、テンプレート規則です。</span><span class="sxs-lookup"><span data-stu-id="472e0-122">All threshold monitoring rules for the BizTalkServerApplication host provided in the BizTalk Server Management pack are template rules.</span></span> <span data-ttu-id="472e0-123">これらの規則を使用するに Operations Manager 管理者コンソールを使用する必要があります。</span><span class="sxs-lookup"><span data-stu-id="472e0-123">In order to use these rules, you should use the Operations Manager Administrator console to:</span></span>  
  
- <span data-ttu-id="472e0-124">内のテンプレート規則のコピーを作成、[!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)]ルール グループとその名前を変更します。</span><span class="sxs-lookup"><span data-stu-id="472e0-124">Create a copy of the template rule in the [!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)] rule group and rename it.</span></span>  
  
- <span data-ttu-id="472e0-125">BizTalk ホスト固有のパフォーマンス カウンターのインスタンス用の新しい Operations Manager プロバイダーを作成します。</span><span class="sxs-lookup"><span data-stu-id="472e0-125">Create a new Operations Manager provider for the BizTalk host-specific performance counter instance.</span></span>  
  
- <span data-ttu-id="472e0-126">ルールで使用される Operations Manager のプロバイダーを変更し、新しい 1 つをポイントします。</span><span class="sxs-lookup"><span data-stu-id="472e0-126">Modify the Operations Manager provider used by the rule and point it to the new one.</span></span>  
  
  <span data-ttu-id="472e0-127">たとえば、[!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)]インストール BizTalk ホストの ReceiveHost があり、このホストのホスト キューのサイズを監視します。</span><span class="sxs-lookup"><span data-stu-id="472e0-127">Suppose your [!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)] installation has a BizTalk host ReceiveHost and you want to monitor the Host Queue size for this host.</span></span> <span data-ttu-id="472e0-128">この場合、BizTalk ホスト キュー サイズのパフォーマンス カウンターの ReceiveHost インスタンスに基づいて Operations Manager プロバイダーを作成する必要があります。</span><span class="sxs-lookup"><span data-stu-id="472e0-128">In this case, you should create a Operations Manager provider based on the ReceiveHost instance of the performance counter for the queue size for the BizTalk host.</span></span> <span data-ttu-id="472e0-129">必要があります設定しても、しきい値の値、ルールで適切に環境内の。</span><span class="sxs-lookup"><span data-stu-id="472e0-129">You should also set the threshold value in the rule appropriately for your environment.</span></span>  
  
  <span data-ttu-id="472e0-130">ホスト固有のしきい値監視ルールを使用している場合は、汎用的な監視ルールを無効にする必要があります。</span><span class="sxs-lookup"><span data-stu-id="472e0-130">If you are using host-specific threshold monitoring rules, you should disable generic monitoring rules.</span></span> <span data-ttu-id="472e0-131">これには、冗長な警告ができないようにします。</span><span class="sxs-lookup"><span data-stu-id="472e0-131">This prevents redundant alerts.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="472e0-132">参照</span><span class="sxs-lookup"><span data-stu-id="472e0-132">See Also</span></span>  
 [<span data-ttu-id="472e0-133">System Center Operations Manager 2007 による BizTalk Server の監視</span><span class="sxs-lookup"><span data-stu-id="472e0-133">Monitoring BizTalk Server with System Center Operations Manager 2007</span></span>](../technical-guides/monitoring-biztalk-server-with-system-center-operations-manager-2007.md)