---
title: 動的送信ポート ハンドラーは構成可能 |Microsoft Docs
ms.custom: ''
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: ''
ms.suite: ''
ms.tgt_pltfrm: ''
ms.topic: article
ms.assetid: 5eb8f5ef-af95-4b2e-9a43-6f1240b25855
caps.latest.revision: 6
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: 21f4985b3e22bd2095e66c240d6c614e1a88c45c
ms.sourcegitcommit: 381e83d43796a345488d54b3f7413e11d56ad7be
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 05/07/2019
ms.locfileid: "65389268"
---
# <a name="dynamic-send-port-handler-is-configurable"></a><span data-ttu-id="824a5-102">動的送信ポート ハンドラーは構成可能です。</span><span class="sxs-lookup"><span data-stu-id="824a5-102">Dynamic Send Port Handler is Configurable</span></span>
<span data-ttu-id="824a5-103">動的送信ポートを作成するときに、インストールされている*すべて*のアダプターについて、アダプターの送信ハンドラーを構成できます。</span><span class="sxs-lookup"><span data-stu-id="824a5-103">When creating a Dynamic Send Port, an adapter Send Handler is configurable for *every* installed adapter.</span></span> <span data-ttu-id="824a5-104">次のシナリオを考えてみましょう。</span><span class="sxs-lookup"><span data-stu-id="824a5-104">Consider the following scenario:</span></span>  
  
 <span data-ttu-id="824a5-105">**Scenario**</span><span class="sxs-lookup"><span data-stu-id="824a5-105">**Scenario**</span></span>  
  
 <span data-ttu-id="824a5-106">アプリケーションには、2 つの ESB 行程があります。</span><span class="sxs-lookup"><span data-stu-id="824a5-106">There are two ESB itineraries in an application.</span></span> <span data-ttu-id="824a5-107">行程 1 では、動的送信ポートを使用して、ファイル共有にデータを送信します。</span><span class="sxs-lookup"><span data-stu-id="824a5-107">Itinerary1 uses a Dynamic Send Port to send data to a File share.</span></span> <span data-ttu-id="824a5-108">行程 2 では、動的送信ポートを使用して、電子メールを送信します。</span><span class="sxs-lookup"><span data-stu-id="824a5-108">Itinerary2 uses a Dynamic Send Port to send e-mail.</span></span> <span data-ttu-id="824a5-109">以前は、動的送信ポートは、アダプターの既定のホストで実行します。</span><span class="sxs-lookup"><span data-stu-id="824a5-109">In the past, Dynamic send ports execute in the adapter's default host.</span></span> <span data-ttu-id="824a5-110">行程 1 は、少量の大きなメッセージ サイズのシナリオを対象に設計されています。</span><span class="sxs-lookup"><span data-stu-id="824a5-110">Itinerary1 is designed to target a low volume - big message size scenario.</span></span> <span data-ttu-id="824a5-111">行程 2 は、大量の小さなメッセージ サイズのシナリオを対象とします。</span><span class="sxs-lookup"><span data-stu-id="824a5-111">Itinerary2 targets a high volume - small message size scenario.</span></span> <span data-ttu-id="824a5-112">アダプターの既定のホストを 1 つだけなので、パフォーマンスが低下、同じホストを使用してすべてのメッセージがルーティングされます。</span><span class="sxs-lookup"><span data-stu-id="824a5-112">Since there is only one default host for an adapter, all messages are routed using the same host, decreasing the performance.</span></span>  
  
 <span data-ttu-id="824a5-113">**変更**</span><span class="sxs-lookup"><span data-stu-id="824a5-113">**The Change**</span></span>  
  
 <span data-ttu-id="824a5-114">動的送信ポートのパフォーマンスを向上させるのには、アダプターの送信ハンドラーは任意のホストを使用する構成できます。</span><span class="sxs-lookup"><span data-stu-id="824a5-114">To improve the performance of Dynamic Send Ports, an adapter Send Handler is configurable to use any host.</span></span> <span data-ttu-id="824a5-115">ESB シナリオでは、行程 1 は、ファイル共有にデータを送信するのに HostA を使用します。</span><span class="sxs-lookup"><span data-stu-id="824a5-115">In the ESB scenario, Itinerary1 uses HostA to send data to a File share.</span></span> <span data-ttu-id="824a5-116">行程 2 では、HostB ポートを使用して、電子メールを送信します。</span><span class="sxs-lookup"><span data-stu-id="824a5-116">Itinerary2 uses HostB Port to send e-mail.</span></span>  
  
## <a name="select-a-send-handler"></a><span data-ttu-id="824a5-117">送信ハンドラーを選択します。</span><span class="sxs-lookup"><span data-stu-id="824a5-117">Select a Send Handler</span></span>  
 <span data-ttu-id="824a5-118">動的な一方向送信ポートまたは動的な送信請求-応答送信ポートを作成する場合、送信ハンドラーがすべてインストールされているアダプターの構成可能です。</span><span class="sxs-lookup"><span data-stu-id="824a5-118">When creating a Dynamic One-Way Send Port or Dynamic Solicit-Response Send Port, the Send Handler is configurable for every installed adapter.</span></span> <span data-ttu-id="824a5-119">手順:</span><span class="sxs-lookup"><span data-stu-id="824a5-119">Steps:</span></span>  
  
1. <span data-ttu-id="824a5-120">**BizTalk Server 管理**コンソールで、 **BizTalk グループ [*GroupName*]**、展開**アプリケーション**、順に展開送信ポートを格納するアプリケーションです。</span><span class="sxs-lookup"><span data-stu-id="824a5-120">In the **BizTalk Server Administration** console, expand **BizTalk Group [*GroupName*]**, expand **Applications**, and then expand the application to contain the send port.</span></span>  
  
2. <span data-ttu-id="824a5-121">右クリック**送信ポート**、 をクリックして**新規**、 をクリックし、**動的な一方向送信ポート**または**動的な送信請求-応答送信ポート**します。</span><span class="sxs-lookup"><span data-stu-id="824a5-121">Right-click **Send Ports**, click **New**, and then click **Dynamic One-way Send Port** or **Dynamic Solicit-Response Send Port**.</span></span>  
  
3. <span data-ttu-id="824a5-122">**プロパティ**、 をクリックして**構成**します。</span><span class="sxs-lookup"><span data-stu-id="824a5-122">In  **Properties**, click **Configure**.</span></span>  
  
    <span data-ttu-id="824a5-123">アダプターは、既定の送信ハンドラーと共に一覧表示されます。</span><span class="sxs-lookup"><span data-stu-id="824a5-123">The adapters are listed with the default Send Handler.</span></span> <span data-ttu-id="824a5-124">別のホストを選択して下矢印をクリックします。</span><span class="sxs-lookup"><span data-stu-id="824a5-124">Click the down arrow to select a different host.</span></span>  
  
4. <span data-ttu-id="824a5-125">クリックして**OK**設定を保存します。</span><span class="sxs-lookup"><span data-stu-id="824a5-125">Click **OK** save the settings.</span></span>  
  
5. <span data-ttu-id="824a5-126">参加を解除し、新しい動的送信ポートを登録します。</span><span class="sxs-lookup"><span data-stu-id="824a5-126">Unenlist and reenlist the new dynamic send port.</span></span>  
  
6. <span data-ttu-id="824a5-127">元のホスト インスタンスを再起動します。</span><span class="sxs-lookup"><span data-stu-id="824a5-127">Restart the original host instance.</span></span>  
  
7. <span data-ttu-id="824a5-128">新しいホスト インスタンスを再起動します。</span><span class="sxs-lookup"><span data-stu-id="824a5-128">Restart the new host instance.</span></span>  
  
   <span data-ttu-id="824a5-129">送信ポートのその他の構成オプションは次のとおりです。</span><span class="sxs-lookup"><span data-stu-id="824a5-129">Additional Send Port configuration options include:</span></span>  
  
- [<span data-ttu-id="824a5-130">送信ポートに対してトランスポートの詳細オプションを構成する方法</span><span class="sxs-lookup"><span data-stu-id="824a5-130">How to Configure Transport Advanced Options for a Send Port</span></span>](http://go.microsoft.com/fwlink/p/?LinkId=267697)  
  
- [<span data-ttu-id="824a5-131">送信ポートに対してバックアップ トランスポートのオプションを構成する方法</span><span class="sxs-lookup"><span data-stu-id="824a5-131">How to Configure Backup Transport Options for a Send Port</span></span>](http://go.microsoft.com/fwlink/p/?LinkId=267698)  
  
- [<span data-ttu-id="824a5-132">送信ポートの送信マップを構成する方法</span><span class="sxs-lookup"><span data-stu-id="824a5-132">How to Configure Outbound Maps for a Send Port</span></span>](http://go.microsoft.com/fwlink/p/?LinkId=267699)  
  
- [<span data-ttu-id="824a5-133">送信ポートのフィルターを構成する方法</span><span class="sxs-lookup"><span data-stu-id="824a5-133">How to Configure Filters for a Send Port</span></span>](http://go.microsoft.com/fwlink/p/?LinkId=267700)  
  
- [<span data-ttu-id="824a5-134">送信ポートに証明書を割り当てる方法</span><span class="sxs-lookup"><span data-stu-id="824a5-134">How to Assign a Certificate to a Send Port</span></span>](http://go.microsoft.com/fwlink/p/?LinkId=267701)  
  
- [<span data-ttu-id="824a5-135">送信ポートの追跡を構成する方法</span><span class="sxs-lookup"><span data-stu-id="824a5-135">How to Configure Tracking for a Send Port</span></span>](http://go.microsoft.com/fwlink/p/?LinkId=267702)  
  
  <span data-ttu-id="824a5-136">さまざまなホストを微調整できます。</span><span class="sxs-lookup"><span data-stu-id="824a5-136">The different hosts can be fine-tuned.</span></span> <span data-ttu-id="824a5-137">次のリンクでは、パフォーマンスの最適化について説明します。</span><span class="sxs-lookup"><span data-stu-id="824a5-137">The following links discuss performance optimization:</span></span>  
  
  [<span data-ttu-id="824a5-138">BizTalk Server の一般的な最適化</span><span class="sxs-lookup"><span data-stu-id="824a5-138">General BizTalk Server Optimizations</span></span>](http://go.microsoft.com/fwlink/p/?LinkId=267703)  
  
  [<span data-ttu-id="824a5-139">BizTalk Server パフォーマンス設定の管理</span><span class="sxs-lookup"><span data-stu-id="824a5-139">Managing BizTalk Server Performance Settings</span></span>](http://go.microsoft.com/fwlink/p/?LinkId=267704)