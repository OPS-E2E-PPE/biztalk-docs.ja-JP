---
title: "低待機時間シナリオ Optimizations1 |Microsoft ドキュメント"
ms.custom: 
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: 
ms.suite: 
ms.tgt_pltfrm: 
ms.topic: article
ms.assetid: cd2a891a-ee4b-4542-b3ce-434e2a6474be
caps.latest.revision: "3"
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: 12f16f67f1c161f74e6a9179db8c85f48b5b3e14
ms.sourcegitcommit: 3fc338e52d5dbca2c3ea1685a2faafc7582fe23a
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 12/01/2017
---
# <a name="low-latency-scenario-optimizations"></a><span data-ttu-id="9b310-102">低待機時間シナリオの最適化</span><span class="sxs-lookup"><span data-stu-id="9b310-102">Low-Latency Scenario Optimizations</span></span>
<span data-ttu-id="9b310-103">既定では、[!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)]低待機時間ではなく、スループットを最適化します。</span><span class="sxs-lookup"><span data-stu-id="9b310-103">By default, [!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)] is optimized for throughput rather than low-latency.</span></span> <span data-ttu-id="9b310-104">次の最適化が適用された[!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)]テスト シナリオではこのガイドに使用します。</span><span class="sxs-lookup"><span data-stu-id="9b310-104">The following optimizations were applied to [!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)] for the test scenario used for this guide.</span></span>  
  
> [!NOTE]  
>  <span data-ttu-id="9b310-105">これらの最適化では、待機時間が改善されますが、全体的なスループットにいくつかのコストで行うことがあります。</span><span class="sxs-lookup"><span data-stu-id="9b310-105">These optimizations will improve latency but may do so at some cost to overall throughput.</span></span>  
  
## <a name="increase-the-biztalk-server-host-internal-message-queue-size"></a><span data-ttu-id="9b310-106">BizTalk Server ホストの内部メッセージ キューのサイズを増やす</span><span class="sxs-lookup"><span data-stu-id="9b310-106">Increase the BizTalk Server host internal message queue size</span></span>  
 <span data-ttu-id="9b310-107">各 BizTalk ホストでは、内部のメモリ内キューがあります。</span><span class="sxs-lookup"><span data-stu-id="9b310-107">Each BizTalk host has its own internal in-memory queue.</span></span> <span data-ttu-id="9b310-108">低待機時間シナリオでパフォーマンスを向上させるためには、100 ~ 1000 の既定値からこのキューのサイズが増加します。</span><span class="sxs-lookup"><span data-stu-id="9b310-108">Increase the size of this queue from the default value of 100 to 1000 to improve performance for a low-latency scenario.</span></span> <span data-ttu-id="9b310-109">内部メッセージ キュー サイズの値を変更する方法の詳細については、「方法に、既定のホスト制限設定の変更」、BizTalk Server ヘルプでを参照してください。 [http://go.microsoft.com/fwlink/?LinkID=120225](http://go.microsoft.com/fwlink/?LinkID=120225)です。</span><span class="sxs-lookup"><span data-stu-id="9b310-109">For more information about modifying the value of the internal message queue size, see “How to Modify the Default Host Throttling Settings” in the BizTalk Server help at [http://go.microsoft.com/fwlink/?LinkID=120225](http://go.microsoft.com/fwlink/?LinkID=120225).</span></span>  
  
## <a name="reduce-the-maxreceiveinterval-value-in-the-admserviceclass-table-of-the-biztalk-server-management-database"></a><span data-ttu-id="9b310-110">BizTalk Server 管理データベースの adm_ServiceClass テーブルの MaxReceiveInterval 値を減らします</span><span class="sxs-lookup"><span data-stu-id="9b310-110">Reduce the MaxReceiveInterval value in the adm_ServiceClass table of the BizTalk Server management database</span></span>  
 [!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)]<span data-ttu-id="9b310-111">ポーリング機構を使用して、メッセージ ボックス内のホスト キューからメッセージを受信します。</span><span class="sxs-lookup"><span data-stu-id="9b310-111"> uses a polling mechanism to receive messages from its host queues in the Messagebox.</span></span> <span data-ttu-id="9b310-112">**MaxReceiveInterval** BizTalk 管理 (BizTalkMgmtDb) データベースの adm_ServiceClass テーブルに値は、各 BizTalk ホスト インスタンスが待機するミリ秒単位で最大値まで、メッセージ ボックス データベースをポーリングします。</span><span class="sxs-lookup"><span data-stu-id="9b310-112">The **MaxReceiveInterval** value in the adm_ServiceClass table of the BizTalk Management (BizTalkMgmtDb) database is the maximum value in milliseconds that each BizTalk host instance will wait until it polls the MessageBox.</span></span> <span data-ttu-id="9b310-113">Adm_ServiceClass テーブルには、次のサービスの種類のレコードが含まれます。</span><span class="sxs-lookup"><span data-stu-id="9b310-113">The adm_ServiceClass table contains a record for the following service types:</span></span>  
  
-   <span data-ttu-id="9b310-114">**XLANG/S** -オーケストレーションの BizTalk ホスト インスタンスの場合</span><span class="sxs-lookup"><span data-stu-id="9b310-114">**XLANG/S** – for BizTalk orchestration host instances</span></span>  
  
-   <span data-ttu-id="9b310-115">**Messaging InProcess** – インプロセス ホスト インスタンスの詳細</span><span class="sxs-lookup"><span data-stu-id="9b310-115">**Messaging InProcess** – for in-process host instances</span></span>  
  
-   <span data-ttu-id="9b310-116">**MSMQT** – MSMQT アダプターのホスト インスタンスの詳細</span><span class="sxs-lookup"><span data-stu-id="9b310-116">**MSMQT** – for MSMQT adapter host instances</span></span>  
  
-   <span data-ttu-id="9b310-117">**Messaging Isolated**の HTTP の場合で使用される、処理ホストのインスタンスから SOAP、および特定の WCF 受信アダプターのハンドラー。</span><span class="sxs-lookup"><span data-stu-id="9b310-117">**Messaging Isolated** – for out of process host instances, used by the HTTP, SOAP, and certain WCF receive adapter handlers</span></span>  
  
 <span data-ttu-id="9b310-118">既定では、これは、低待機時間ではなく、スループットについて最適化されて 500 (ミリ秒単位) にこの値が設定されます。</span><span class="sxs-lookup"><span data-stu-id="9b310-118">By default, this value is set to 500 milliseconds, which is optimized for throughput rather than low-latency.</span></span> <span data-ttu-id="9b310-119">特定のシナリオでは、この値を減らすことによって待機時間を向上できます。</span><span class="sxs-lookup"><span data-stu-id="9b310-119">In certain scenarios, latency can be improved by reducing this value.</span></span>  
  
> [!NOTE]  
>  <span data-ttu-id="9b310-120">この値を変更は関連付けられているサービスの種類のすべてのインスタンスに影響を与えるため、この値を変更する前にすべてのホスト インスタンスへの影響を評価するように注意します。</span><span class="sxs-lookup"><span data-stu-id="9b310-120">Changes to this value impact all instances of the associated service type, therefore, take care to evaluate the impact on all host instances before changing this value.</span></span>  
  
> [!NOTE]  
>  <span data-ttu-id="9b310-121">この値は、メッセージ ボックス データベースに残りのメッセージが未処理があるない場合にのみ使用します。</span><span class="sxs-lookup"><span data-stu-id="9b310-121">This value is only used if the Messagebox has no remaining unprocessed messages.</span></span> <span data-ttu-id="9b310-122">定数、メッセージ ボックス内の未処理のメッセージのバックログがない場合[!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)]ポーリング遅延に待機することがなく、メッセージの処理を試みます。</span><span class="sxs-lookup"><span data-stu-id="9b310-122">If there is a constant backlog of unprocessed messages in the Messagebox, [!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)] will attempt to process the messages without waiting on the polling delay.</span></span> <span data-ttu-id="9b310-123">すべてのメッセージを処理した後[!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)]MaxReceiveInterval に指定された値を使用して、ポーリングが開始されます。</span><span class="sxs-lookup"><span data-stu-id="9b310-123">After all messages are processed, [!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)] will begin polling using the value specified for MaxReceiveInterval.</span></span>  
  
> [!NOTE]  
>  <span data-ttu-id="9b310-124">[!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)] MaxReceiveInterval がメッセージ ボックス データベース インスタンスを格納する SQL Server コンピューターで過剰な CPU 使用率を引き起こす可能性が値を小さく、メッセージ ボックス データベースのインスタンスにホスト インスタンスの比率が高い環境。</span><span class="sxs-lookup"><span data-stu-id="9b310-124">In a [!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)] environment with a high ratio of host instances to Messagebox database instances, decreasing the value for MaxReceiveInterval may cause excessive CPU utilization on the SQL Server computer that houses the Messagebox database instance.</span></span> <span data-ttu-id="9b310-125">たとえば、MaxReceiveInterval が低い値に減らさ (\< 100) で、[!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)]環境の 1 つのメッセージ ボックスおよび > 50 ホスト インスタンスでは、SQL Server の CPU 使用率は 50% を超える上昇する可能性があります。</span><span class="sxs-lookup"><span data-stu-id="9b310-125">For example, if the MaxReceiveInterval is decreased to a low value (\< 100) in a [!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)] environment with a single Messagebox and > 50 host instances, CPU utilization on the SQL Server may climb above 50%.</span></span> <span data-ttu-id="9b310-126">この現象は、継続的にホスト キューのポーリングに関連するオーバーヘッドが大幅なために発生することができます。</span><span class="sxs-lookup"><span data-stu-id="9b310-126">This phenomenon can occur because the overhead associated with continually polling host queues is significant.</span></span> <span data-ttu-id="9b310-127">MaxReceiveInterval を 100 未満の値を小さく場合もの SQL Server コンピューターの CPU 使用率がこの影響を評価する必要があります。</span><span class="sxs-lookup"><span data-stu-id="9b310-127">If you reduce MaxReceiveInterval to a value less than 100, you should also evaluate the impact that this has on your SQL Server computer’s CPU utilization.</span></span>