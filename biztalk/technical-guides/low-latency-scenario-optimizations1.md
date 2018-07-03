---
title: 低待機時間シナリオ Optimizations1 |Microsoft Docs
ms.custom: ''
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: ''
ms.suite: ''
ms.tgt_pltfrm: ''
ms.topic: article
ms.assetid: cd2a891a-ee4b-4542-b3ce-434e2a6474be
caps.latest.revision: 3
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: ed309a8ea9d6728dc4e0e653969f456e69f6eb34
ms.sourcegitcommit: 266308ec5c6a9d8d80ff298ee6051b4843c5d626
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 06/27/2018
ms.locfileid: "36986059"
---
# <a name="low-latency-scenario-optimizations"></a><span data-ttu-id="a406b-102">低待機時間シナリオの最適化</span><span class="sxs-lookup"><span data-stu-id="a406b-102">Low-Latency Scenario Optimizations</span></span>
<span data-ttu-id="a406b-103">既定では、[!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)]は低待機時間よりもスループットに最適化されています。</span><span class="sxs-lookup"><span data-stu-id="a406b-103">By default, [!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)] is optimized for throughput rather than low-latency.</span></span> <span data-ttu-id="a406b-104">次の最適化が適用された[!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)]テスト シナリオではこのガイドに使用します。</span><span class="sxs-lookup"><span data-stu-id="a406b-104">The following optimizations were applied to [!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)] for the test scenario used for this guide.</span></span>  
  
> [!NOTE]  
>  <span data-ttu-id="a406b-105">これらの最適化では、待機時間が改善されますが、全体的なスループットをいくつかのコストで行うことがあります。</span><span class="sxs-lookup"><span data-stu-id="a406b-105">These optimizations will improve latency but may do so at some cost to overall throughput.</span></span>  
  
## <a name="increase-the-biztalk-server-host-internal-message-queue-size"></a><span data-ttu-id="a406b-106">BizTalk Server ホストの内部メッセージ キューのサイズを増やす</span><span class="sxs-lookup"><span data-stu-id="a406b-106">Increase the BizTalk Server host internal message queue size</span></span>  
 <span data-ttu-id="a406b-107">各 BizTalk ホストには、内部のメモリ内キューがあります。</span><span class="sxs-lookup"><span data-stu-id="a406b-107">Each BizTalk host has its own internal in-memory queue.</span></span> <span data-ttu-id="a406b-108">低待機時間シナリオのパフォーマンスを向上させるためには、100 ~ 1000 の既定値からこのキューのサイズを大ききます。</span><span class="sxs-lookup"><span data-stu-id="a406b-108">Increase the size of this queue from the default value of 100 to 1000 to improve performance for a low-latency scenario.</span></span> <span data-ttu-id="a406b-109">内部メッセージ キューのサイズの値を変更する方法の詳細については、「方法を既定のホスト制限設定の変更」、BizTalk Server ヘルプでを参照してください。 [ http://go.microsoft.com/fwlink/?LinkID=120225](http://go.microsoft.com/fwlink/?LinkID=120225)します。</span><span class="sxs-lookup"><span data-stu-id="a406b-109">For more information about modifying the value of the internal message queue size, see “How to Modify the Default Host Throttling Settings” in the BizTalk Server help at [http://go.microsoft.com/fwlink/?LinkID=120225](http://go.microsoft.com/fwlink/?LinkID=120225).</span></span>  
  
## <a name="reduce-the-maxreceiveinterval-value-in-the-admserviceclass-table-of-the-biztalk-server-management-database"></a><span data-ttu-id="a406b-110">BizTalk Server 管理データベースの adm_ServiceClass テーブルの MaxReceiveInterval 値を減らします</span><span class="sxs-lookup"><span data-stu-id="a406b-110">Reduce the MaxReceiveInterval value in the adm_ServiceClass table of the BizTalk Server management database</span></span>  
 [!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)]<span data-ttu-id="a406b-111"> ポーリング メカニズムを使用して、メッセージ ボックスで、ホスト キューからメッセージを受信します。</span><span class="sxs-lookup"><span data-stu-id="a406b-111"> uses a polling mechanism to receive messages from its host queues in the Messagebox.</span></span> <span data-ttu-id="a406b-112">**MaxReceiveInterval** BizTalk 管理 (BizTalkMgmtDb) データベースの adm_ServiceClass テーブル内の値は、各 BizTalk ホスト インスタンスが待機するミリ秒単位で最大値まで、メッセージ ボックス データベースをポーリングします。</span><span class="sxs-lookup"><span data-stu-id="a406b-112">The **MaxReceiveInterval** value in the adm_ServiceClass table of the BizTalk Management (BizTalkMgmtDb) database is the maximum value in milliseconds that each BizTalk host instance will wait until it polls the MessageBox.</span></span> <span data-ttu-id="a406b-113">Adm_ServiceClass テーブルには、次のサービスの種類のレコードが含まれています。</span><span class="sxs-lookup"><span data-stu-id="a406b-113">The adm_ServiceClass table contains a record for the following service types:</span></span>  
  
- <span data-ttu-id="a406b-114">**XLANG/S** -オーケストレーションの BizTalk ホスト インスタンスの場合</span><span class="sxs-lookup"><span data-stu-id="a406b-114">**XLANG/S** – for BizTalk orchestration host instances</span></span>  
  
- <span data-ttu-id="a406b-115">**Messaging InProcess** – のインプロセス ホスト インスタンス</span><span class="sxs-lookup"><span data-stu-id="a406b-115">**Messaging InProcess** – for in-process host instances</span></span>  
  
- <span data-ttu-id="a406b-116">**MSMQT** -MSMQT アダプターのホスト インスタンスの場合</span><span class="sxs-lookup"><span data-stu-id="a406b-116">**MSMQT** – for MSMQT adapter host instances</span></span>  
  
- <span data-ttu-id="a406b-117">**Messaging Isolated** -HTTP の場合で使用される、プロセス ホストのインスタンスから SOAP、および特定の WCF 受信アダプターのハンドラー</span><span class="sxs-lookup"><span data-stu-id="a406b-117">**Messaging Isolated** – for out of process host instances, used by the HTTP, SOAP, and certain WCF receive adapter handlers</span></span>  
  
  <span data-ttu-id="a406b-118">既定では、低待機時間よりもスループットが最適化された 500 (ミリ秒単位) をこの値が設定されます。</span><span class="sxs-lookup"><span data-stu-id="a406b-118">By default, this value is set to 500 milliseconds, which is optimized for throughput rather than low-latency.</span></span> <span data-ttu-id="a406b-119">特定のシナリオでは、この値を減らすことで待機時間を改善できます。</span><span class="sxs-lookup"><span data-stu-id="a406b-119">In certain scenarios, latency can be improved by reducing this value.</span></span>  
  
> [!NOTE]
>  <span data-ttu-id="a406b-120">この値を変更は、関連付けられているサービスの種類のすべてのインスタンスに影響を与えるため、この値を変更する前にすべてのホスト インスタンスへの影響を評価するように注意します。</span><span class="sxs-lookup"><span data-stu-id="a406b-120">Changes to this value impact all instances of the associated service type, therefore, take care to evaluate the impact on all host instances before changing this value.</span></span>  
> 
> [!NOTE]
>  <span data-ttu-id="a406b-121">この値は、メッセージ ボックスが残っている未処理メッセージを持たない場合にのみ使用します。</span><span class="sxs-lookup"><span data-stu-id="a406b-121">This value is only used if the Messagebox has no remaining unprocessed messages.</span></span> <span data-ttu-id="a406b-122">メッセージ ボックス内の未処理のメッセージのバックログが絶えず場合、[!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)]ポーリング遅延に待機することがなく、メッセージの処理を試みます。</span><span class="sxs-lookup"><span data-stu-id="a406b-122">If there is a constant backlog of unprocessed messages in the Messagebox, [!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)] will attempt to process the messages without waiting on the polling delay.</span></span> <span data-ttu-id="a406b-123">すべてのメッセージが処理された後[!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)]MaxReceiveInterval に指定された値を使用して、ポーリングが開始されます。</span><span class="sxs-lookup"><span data-stu-id="a406b-123">After all messages are processed, [!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)] will begin polling using the value specified for MaxReceiveInterval.</span></span>  
> 
> [!NOTE]
>  <span data-ttu-id="a406b-124">[!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)]高比率 MaxReceiveInterval がメッセージ ボックス データベースのインスタンスを格納する SQL Server コンピューターで過剰な CPU 使用率を引き起こす可能性が値を減らす、メッセージ ボックス データベースのインスタンスへのホスト インスタンスの環境。</span><span class="sxs-lookup"><span data-stu-id="a406b-124">In a [!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)] environment with a high ratio of host instances to Messagebox database instances, decreasing the value for MaxReceiveInterval may cause excessive CPU utilization on the SQL Server computer that houses the Messagebox database instance.</span></span> <span data-ttu-id="a406b-125">たとえば、低い値に、MaxReceiveInterval が減少 (\< 100) で、 [!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)] 1 つのメッセージ ボックスおよび > 50 ホスト インスタンスの使用環境では、SQL Server の CPU 使用率は 50% を超える上昇する可能性があります。</span><span class="sxs-lookup"><span data-stu-id="a406b-125">For example, if the MaxReceiveInterval is decreased to a low value (\< 100) in a [!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)] environment with a single Messagebox and > 50 host instances, CPU utilization on the SQL Server may climb above 50%.</span></span> <span data-ttu-id="a406b-126">この現象は、継続的にホストのキューのポーリングに伴うオーバーヘッドは大幅な場合に発生します。</span><span class="sxs-lookup"><span data-stu-id="a406b-126">This phenomenon can occur because the overhead associated with continually polling host queues is significant.</span></span> <span data-ttu-id="a406b-127">MaxReceiveInterval を 100 未満の値を小さく場合、SQL Server コンピューターの CPU 使用率がこの影響を評価する必要もあります。</span><span class="sxs-lookup"><span data-stu-id="a406b-127">If you reduce MaxReceiveInterval to a value less than 100, you should also evaluate the impact that this has on your SQL Server computer’s CPU utilization.</span></span>