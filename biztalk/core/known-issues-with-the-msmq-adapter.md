---
title: "MSMQ アダプターに関する既知の問題 |Microsoft ドキュメント"
ms.custom: 
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: 
ms.suite: 
ms.tgt_pltfrm: 
ms.topic: article
ms.assetid: ce77cdac-79c1-4529-8f09-0fb1f87ca037
caps.latest.revision: "11"
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: 67f210d0e480a311aed0bed5d50f6a827bd6ea4e
ms.sourcegitcommit: cb908c540d8f1a692d01dc8f313e16cb4b4e696d
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 09/20/2017
---
# <a name="known-issues-with-the-msmq-adapter"></a><span data-ttu-id="cd51b-102">MSMQ アダプターに関する既知の問題</span><span class="sxs-lookup"><span data-stu-id="cd51b-102">Known Issues with the MSMQ Adapter</span></span>
<span data-ttu-id="cd51b-103">ここでは、エラー回避に役立つ情報を記載します。</span><span class="sxs-lookup"><span data-stu-id="cd51b-103">This section contains information that may help you avoid errors.</span></span>  
  
## <a name="known-issues"></a><span data-ttu-id="cd51b-104">既知の問題</span><span class="sxs-lookup"><span data-stu-id="cd51b-104">Known Issues</span></span>  
  
#### <a name="msmq-adapter-receive-locations-do-not-process-documents"></a><span data-ttu-id="cd51b-105">MSMQ アダプターの受信場所でドキュメントが処理されない</span><span class="sxs-lookup"><span data-stu-id="cd51b-105">MSMQ Adapter receive locations do not process documents</span></span>  
  
##### <a name="problem"></a><span data-ttu-id="cd51b-106">問題</span><span class="sxs-lookup"><span data-stu-id="cd51b-106">Problem</span></span>  
 <span data-ttu-id="cd51b-107">MSMQ アダプターの受信場所でドキュメントが処理されません。</span><span class="sxs-lookup"><span data-stu-id="cd51b-107">MSMQ Adapter receive locations will not process documents.</span></span>  
  
##### <a name="cause"></a><span data-ttu-id="cd51b-108">原因</span><span class="sxs-lookup"><span data-stu-id="cd51b-108">Cause</span></span>  
 <span data-ttu-id="cd51b-109">MSMQ アダプターの受信ハンドラーが実行されている BizTalk ホスト インスタンスに関連付けられた .NET スレッド プールで、使用できるスレッド数が不足している場合、MSMQ アダプターの受信場所ではドキュメントを処理できません。</span><span class="sxs-lookup"><span data-stu-id="cd51b-109">If there are insufficient threads available in the .NET thread pool associated with the BizTalk host instance that the MSMQ adapter receive handler is running in then MSMQ Adapter receive locations are unable to process documents due to thread starvation.</span></span>  
  
##### <a name="resolution"></a><span data-ttu-id="cd51b-110">解決策</span><span class="sxs-lookup"><span data-stu-id="cd51b-110">Resolution</span></span>  
 <span data-ttu-id="cd51b-111">ホスト インスタンスの .NET スレッド プールで使用可能なスレッドの数を増やすには、手順で、**ホスト用 CLR Hosting スレッド値**」の「[に影響するアダプターの構成パラメーターパフォーマンス](../core/configuration-parameters-that-affect-adapter-performance.md)です。</span><span class="sxs-lookup"><span data-stu-id="cd51b-111">To increase the number of available threads in the .NET thread pool for the host instance, follow the steps in the **CLR Hosting thread values for the host** section of the topic [Configuration Parameters that Affect Adapter Performance](../core/configuration-parameters-that-affect-adapter-performance.md).</span></span>  
  
 <span data-ttu-id="cd51b-112">各 MSMQ 受信場所、MSMQ にバインドされているために、受信ハンドラーには、.NET スレッド プールのスレッドが必要があります、設定**MinIOThreads**と**MinWorkerThreads**に値がより大きいか等しいMSMQ 受信場所の数は、受信ハンドラーにバインドされます。</span><span class="sxs-lookup"><span data-stu-id="cd51b-112">Because each MSMQ receive location that is bound to an MSMQ receive handler requires a thread from the .NET thread pool, set **MinIOThreads** and **MinWorkerThreads** to a value that is greater than or equal to the number of MSMQ receive locations bound to the receive handler.</span></span> <span data-ttu-id="cd51b-113">同様の値を設定します。 **MaxIOThreads**と**MaxWorkerThreads** MSMQ の数に相当する値を受信場所の受信ハンドラーにバインドされている * 2 ヘッドルームを許可します。</span><span class="sxs-lookup"><span data-stu-id="cd51b-113">Accordingly, set the value for **MaxIOThreads** and **MaxWorkerThreads** to a value equal to the number of MSMQ receive locations bound to the receive handler * 2 to allow for headroom:</span></span>  
  
|<span data-ttu-id="cd51b-114">DWORD エントリ</span><span class="sxs-lookup"><span data-stu-id="cd51b-114">DWORD Entry</span></span>|<span data-ttu-id="cd51b-115">推奨値</span><span class="sxs-lookup"><span data-stu-id="cd51b-115">Recommended value</span></span>|  
|-----------------|-----------------------|  
|<span data-ttu-id="cd51b-116">MaxIOThreads</span><span class="sxs-lookup"><span data-stu-id="cd51b-116">MaxIOThreads</span></span>|<span data-ttu-id="cd51b-117">MSMQ アダプターの受信ハンドラーにバインドされている MSMQ 受信場所の数 * 2。</span><span class="sxs-lookup"><span data-stu-id="cd51b-117">Number of MSMQ receive locations bound to the MSMQ adapter receive handler * 2.</span></span>|  
|<span data-ttu-id="cd51b-118">MaxWorkerThreads</span><span class="sxs-lookup"><span data-stu-id="cd51b-118">MaxWorkerThreads</span></span>|<span data-ttu-id="cd51b-119">MSMQ アダプターの受信ハンドラーにバインドされている MSMQ 受信場所の数 * 2。</span><span class="sxs-lookup"><span data-stu-id="cd51b-119">Number of MSMQ receive locations bound to the MSMQ adapter receive handler * 2.</span></span>|  
|<span data-ttu-id="cd51b-120">MinIOThreads</span><span class="sxs-lookup"><span data-stu-id="cd51b-120">MinIOThreads</span></span>|<span data-ttu-id="cd51b-121">MSMQ アダプターの受信ハンドラーにバインドされている MSMQ 受信場所の数</span><span class="sxs-lookup"><span data-stu-id="cd51b-121">Number of MSMQ receive locations bound to the MSMQ adapter receive handler.</span></span>|  
|<span data-ttu-id="cd51b-122">MinWorkerThreads</span><span class="sxs-lookup"><span data-stu-id="cd51b-122">MinWorkerThreads</span></span>|<span data-ttu-id="cd51b-123">MSMQ アダプターの受信ハンドラーにバインドされている MSMQ 受信場所の数</span><span class="sxs-lookup"><span data-stu-id="cd51b-123">Number of MSMQ receive locations bound to the MSMQ adapter receive handler.</span></span>|  
  
 <span data-ttu-id="cd51b-124">これらの推奨値には、ホスト インスタンス内で実行されている他のアダプター ハンドラーやオーケストレーションによって使用されるスレッドは考慮されていません。したがって、これらのスレッドを考慮して値を増やす必要があります。</span><span class="sxs-lookup"><span data-stu-id="cd51b-124">These recommended values do not factor in the threads used by other adapter handlers or orchestrations running in the host instance so the values should be increased accordingly.</span></span>  
  
#### <a name="msmq-adapter-receive-locations-shut-down-shortly-after-they-are-enabled"></a><span data-ttu-id="cd51b-125">有効にした MSMQ アダプターの受信場所がすぐにシャットダウンする</span><span class="sxs-lookup"><span data-stu-id="cd51b-125">MSMQ Adapter receive locations shut down shortly after they are enabled</span></span>  
  
##### <a name="problem"></a><span data-ttu-id="cd51b-126">問題</span><span class="sxs-lookup"><span data-stu-id="cd51b-126">Problem</span></span>  
 <span data-ttu-id="cd51b-127">有効にした MSMQ 受信場所がすぐにシャットダウンします。</span><span class="sxs-lookup"><span data-stu-id="cd51b-127">MSMQ receive locations shut down shortly after they are enabled.</span></span>  
  
##### <a name="cause"></a><span data-ttu-id="cd51b-128">原因</span><span class="sxs-lookup"><span data-stu-id="cd51b-128">Cause</span></span>  
 <span data-ttu-id="cd51b-129">メッセージ キュー サービスのクラスター化されていないローカル インスタンスが、MSMQ 受信ハンドラーのホスト インスタンスと同じコンピューター上で実行されていない場合に、この問題が発生することがあります。</span><span class="sxs-lookup"><span data-stu-id="cd51b-129">This problem can occur if a local non-clustered instance of the Message Queuing service is not running on the same computer that the host instance for the MSMQ receive handler is running on.</span></span>  
  
##### <a name="resolution"></a><span data-ttu-id="cd51b-130">解決策</span><span class="sxs-lookup"><span data-stu-id="cd51b-130">Resolution</span></span>  
 <span data-ttu-id="cd51b-131">MSMQ 受信ハンドラーのホスト インスタンスを実行中のコンピューターで、メッセージ キュー サービスを開始します</span><span class="sxs-lookup"><span data-stu-id="cd51b-131">Start the Message Queuing service on the computer that the host instance for the MSMQ receive handler is running on.</span></span> <span data-ttu-id="cd51b-132">メッセージ キュー サービスのクラスター化されたインスタンスが、MSMQ アダプターの受信ハンドラーと同じコンピューター上で実行されている場合でも、メッセージ キュー サービスのローカル インスタンスが実行されている必要があります。</span><span class="sxs-lookup"><span data-stu-id="cd51b-132">The MSMQ adapter receive handler requires that a local instance of the Message Queuing service is running even if a clustered instance of the Message Queuing service is running on the same computer.</span></span>  
  
#### <a name="sc-tool-causes-error-when-attempting-to-stop-service-for-host-instance"></a><span data-ttu-id="cd51b-133">SC ツールでホスト インスタンスのサービスを停止しようとしたときにエラーが発生する</span><span class="sxs-lookup"><span data-stu-id="cd51b-133">SC tool causes error when attempting to stop service for host instance</span></span>  
  
##### <a name="problem"></a><span data-ttu-id="cd51b-134">問題</span><span class="sxs-lookup"><span data-stu-id="cd51b-134">Problem</span></span>  
 <span data-ttu-id="cd51b-135">SC ツール (Sc.exe) を使用して BizTalk ホスト インスタンスのサービスをシャットダウンしようとすると、次のようなエラー メッセージが表示される場合があります。</span><span class="sxs-lookup"><span data-stu-id="cd51b-135">When you try to use the SC tool (Sc.exe) to shut down the service for the BizTalk host instance, you may receive an error message that resembles the following:</span></span>  
  
 <span data-ttu-id="cd51b-136">**ControlService 1053 が失敗しました。**</span><span class="sxs-lookup"><span data-stu-id="cd51b-136">**ControlService FAILED 1053:**</span></span>  
  
 <span data-ttu-id="cd51b-137">**サービスは、適切なタイミングで開始または制御要求に応答しませんでした。**</span><span class="sxs-lookup"><span data-stu-id="cd51b-137">**The service did not respond to the start or control request in a timely fashion.**</span></span>  
  
 <span data-ttu-id="cd51b-138">このエラー メッセージが表示された後、BizTalk ホスト インスタンスのサービスが停止します。</span><span class="sxs-lookup"><span data-stu-id="cd51b-138">After you receive this error message, the service for the BizTalk host instance is stopped.</span></span> <span data-ttu-id="cd51b-139">しかし、SC ツールによってサービスがシャットダウンされるまで、2 分以上かかる場合があります。</span><span class="sxs-lookup"><span data-stu-id="cd51b-139">However, the SC tool may need two minutes or more to shut down the service.</span></span>  
  
 <span data-ttu-id="cd51b-140">Microsoft メッセージ キューの受信場所を [!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)] で有効にしたときに、この問題が発生します。</span><span class="sxs-lookup"><span data-stu-id="cd51b-140">This problem occurs when a Microsoft Message Queuing receive location is enabled in [!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)].</span></span>  
  
 <span data-ttu-id="cd51b-141">また、次のようなエラー メッセージがシステム ログに記録されることもあります。</span><span class="sxs-lookup"><span data-stu-id="cd51b-141">Additionally, an error message that resembles the following may be logged in the System log:</span></span>  
  
 <span data-ttu-id="cd51b-142">**イベントの種類: エラー**</span><span class="sxs-lookup"><span data-stu-id="cd51b-142">**Event Type: Error**</span></span>  
  
 <span data-ttu-id="cd51b-143">**イベント ソース: サービス コントロール マネージャー**</span><span class="sxs-lookup"><span data-stu-id="cd51b-143">**Event Source: Service Control Manager**</span></span>  
  
 <span data-ttu-id="cd51b-144">**イベント カテゴリ: なし**</span><span class="sxs-lookup"><span data-stu-id="cd51b-144">**Event Category: None**</span></span>  
  
 <span data-ttu-id="cd51b-145">**イベント ID: 7011**</span><span class="sxs-lookup"><span data-stu-id="cd51b-145">**Event ID: 7011**</span></span>  
  
 <span data-ttu-id="cd51b-146">**説明:**</span><span class="sxs-lookup"><span data-stu-id="cd51b-146">**Description:**</span></span>  
  
 <span data-ttu-id="cd51b-147">**タイムアウト (30000 ミリ秒) BTSSvc$ BizTalkServerApplication サービスからトランザクションの応答を待機しています。**</span><span class="sxs-lookup"><span data-stu-id="cd51b-147">**Timeout (30000 milliseconds) waiting for a transaction response from the BTSSvc$BizTalkServerApplication service.**</span></span>  
  
##### <a name="resolution"></a><span data-ttu-id="cd51b-148">解決策</span><span class="sxs-lookup"><span data-stu-id="cd51b-148">Resolution</span></span>  
 <span data-ttu-id="cd51b-149">サポートされている修正プログラムを Microsoft から入手できます。</span><span class="sxs-lookup"><span data-stu-id="cd51b-149">A supported hotfix is now available from Microsoft.</span></span> <span data-ttu-id="cd51b-150">ただし、この修正プログラムは、この資料で説明した問題のみの修正を目的としています。</span><span class="sxs-lookup"><span data-stu-id="cd51b-150">However, this hotfix is intended to correct only the problem that is described in this article.</span></span> <span data-ttu-id="cd51b-151">この特定の問題が発生しているシステム以外には適用しないでください。</span><span class="sxs-lookup"><span data-stu-id="cd51b-151">Apply this hotfix only to systems that are experiencing this specific problem.</span></span> <span data-ttu-id="cd51b-152">この修正プログラムは、さらにテストされる可能性があります。</span><span class="sxs-lookup"><span data-stu-id="cd51b-152">This hotfix might receive additional testing.</span></span> <span data-ttu-id="cd51b-153">したがって、この問題による影響が非常に深刻でない限り、この修正プログラムを含む次のサービス パックが提供されるまで待つことをお勧めします。</span><span class="sxs-lookup"><span data-stu-id="cd51b-153">Therefore, if you are not severely affected by this problem, we recommend that you wait for the next service pack that contains this hotfix.</span></span>  
  
 <span data-ttu-id="cd51b-154">この問題を解決するには、マイクロソフト オンライン カスタマー サービスに要求を送信して、修正プログラムを入手してください。</span><span class="sxs-lookup"><span data-stu-id="cd51b-154">To resolve this problem, submit a request to Microsoft Online Customer Services to obtain the hotfix.</span></span>  
  
> [!NOTE]
>  <span data-ttu-id="cd51b-155">さらに問題が発生した場合やトラブルシューティングが必要な場合、別のサービス要求の作成が必要になる場合があります。</span><span class="sxs-lookup"><span data-stu-id="cd51b-155">If additional issues occur or any troubleshooting is required, you might have to create a separate service request.</span></span> <span data-ttu-id="cd51b-156">この修正プログラムの対象とならない追加のサポートおよび問題には、通常のサポート費用が適用されます。</span><span class="sxs-lookup"><span data-stu-id="cd51b-156">The usual support costs will apply to additional support questions and issues that do not qualify for this specific hotfix.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="cd51b-157">参照</span><span class="sxs-lookup"><span data-stu-id="cd51b-157">See Also</span></span>  
 [<span data-ttu-id="cd51b-158">MSMQ アダプターのトラブルシューティング</span><span class="sxs-lookup"><span data-stu-id="cd51b-158">Troubleshooting the MSMQ Adapter</span></span>](../core/troubleshooting-the-msmq-adapter.md)