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
ms.openlocfilehash: ea7fb4a2f877baf70c0684c57b83e5f32edaa4d6
ms.sourcegitcommit: 266308ec5c6a9d8d80ff298ee6051b4843c5d626
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 06/27/2018
ms.locfileid: "36971779"
---
# <a name="dynamic-send-port-handler-is-configurable"></a><span data-ttu-id="1ddfc-102">動的送信ポート ハンドラーは構成可能</span><span class="sxs-lookup"><span data-stu-id="1ddfc-102">Dynamic Send Port Handler is Configurable</span></span>
<span data-ttu-id="1ddfc-103">動的送信ポートを作成するときに、インストールされている*すべて*のアダプターについて、アダプターの送信ハンドラーを構成できます。</span><span class="sxs-lookup"><span data-stu-id="1ddfc-103">When creating a Dynamic Send Port, an adapter Send Handler is configurable for *every* installed adapter.</span></span> <span data-ttu-id="1ddfc-104">以下のシナリオについて考えてみます。</span><span class="sxs-lookup"><span data-stu-id="1ddfc-104">Consider the following scenario:</span></span>  
  
 <span data-ttu-id="1ddfc-105">**Scenario**</span><span class="sxs-lookup"><span data-stu-id="1ddfc-105">**Scenario**</span></span>  
  
 <span data-ttu-id="1ddfc-106">アプリケーションには 2 つの ESB 行程があります。</span><span class="sxs-lookup"><span data-stu-id="1ddfc-106">There are two ESB itineraries in an application.</span></span> <span data-ttu-id="1ddfc-107">行程 1 では、動的送信ポートを使用してデータをファイル共有に送信します。</span><span class="sxs-lookup"><span data-stu-id="1ddfc-107">Itinerary1 uses a Dynamic Send Port to send data to a File share.</span></span> <span data-ttu-id="1ddfc-108">行程 2 では、動的送信ポートを使用して電子メールを送信します。</span><span class="sxs-lookup"><span data-stu-id="1ddfc-108">Itinerary2 uses a Dynamic Send Port to send e-mail.</span></span> <span data-ttu-id="1ddfc-109">これまで、動的送信ポートはアダプターの既定のホストで実行されていました。</span><span class="sxs-lookup"><span data-stu-id="1ddfc-109">In the past, Dynamic send ports execute in the adapter's default host.</span></span> <span data-ttu-id="1ddfc-110">行程 1 は、分量が少なくてメッセージ サイズが大きいシナリオ向けに設計されています。</span><span class="sxs-lookup"><span data-stu-id="1ddfc-110">Itinerary1 is designed to target a low volume - big message size scenario.</span></span> <span data-ttu-id="1ddfc-111">行程 2 は、分量が多くてメッセージ サイズが小さいシナリオを対象としています。</span><span class="sxs-lookup"><span data-stu-id="1ddfc-111">Itinerary2 targets a high volume - small message size scenario.</span></span> <span data-ttu-id="1ddfc-112">1 つのアダプターの既定のホストは 1 つだけなので、すべてのメッセージが同じホストを使用してルーティングされ、パフォーマンスを低下させています。</span><span class="sxs-lookup"><span data-stu-id="1ddfc-112">Since there is only one default host for an adapter, all messages are routed using the same host, decreasing the performance.</span></span>  
  
 <span data-ttu-id="1ddfc-113">**変更**</span><span class="sxs-lookup"><span data-stu-id="1ddfc-113">**The Change**</span></span>  
  
 <span data-ttu-id="1ddfc-114">動的送信ポートのパフォーマンスを向上させるために、任意のホストを使用するようにアダプターの送信ハンドラーを構成できます。</span><span class="sxs-lookup"><span data-stu-id="1ddfc-114">To improve the performance of Dynamic Send Ports, an adapter Send Handler is configurable to use any host.</span></span> <span data-ttu-id="1ddfc-115">ESB シナリオでは、行程 1 で HostA を使用してデータをファイル共有に送信します。</span><span class="sxs-lookup"><span data-stu-id="1ddfc-115">In the ESB scenario, Itinerary1 uses HostA to send data to a File share.</span></span> <span data-ttu-id="1ddfc-116">行程 2 では、HostB ポートを使用して電子メールを送信します。</span><span class="sxs-lookup"><span data-stu-id="1ddfc-116">Itinerary2 uses HostB Port to send e-mail.</span></span>  
  
## <a name="select-a-send-handler"></a><span data-ttu-id="1ddfc-117">送信ハンドラーの選択</span><span class="sxs-lookup"><span data-stu-id="1ddfc-117">Select a Send Handler</span></span>  
 <span data-ttu-id="1ddfc-118">動的な一方向の送信ポートまたは動的な送信請求 - 応答の送信ポートを作成するとき、インストールされたすべてのアダプターについて送信ハンドラーを構成できます。</span><span class="sxs-lookup"><span data-stu-id="1ddfc-118">When creating a Dynamic One-Way Send Port or Dynamic Solicit-Response Send Port, the Send Handler is configurable for every installed adapter.</span></span> <span data-ttu-id="1ddfc-119">手順:</span><span class="sxs-lookup"><span data-stu-id="1ddfc-119">Steps:</span></span>  
  
1. <span data-ttu-id="1ddfc-120">**BizTalk Server 管理**コンソールで、 **BizTalk グループ [*GroupName*]**、展開**アプリケーション**、順に展開送信ポートを格納するアプリケーションです。</span><span class="sxs-lookup"><span data-stu-id="1ddfc-120">In the **BizTalk Server Administration** console, expand **BizTalk Group [*GroupName*]**, expand **Applications**, and then expand the application to contain the send port.</span></span>  
  
2. <span data-ttu-id="1ddfc-121">右クリック**送信ポート**、 をクリックして**新規**、 をクリックし、**動的な一方向送信ポート**または**動的な送信請求-応答送信ポート**します。</span><span class="sxs-lookup"><span data-stu-id="1ddfc-121">Right-click **Send Ports**, click **New**, and then click **Dynamic One-way Send Port** or **Dynamic Solicit-Response Send Port**.</span></span>  
  
3. <span data-ttu-id="1ddfc-122">**プロパティ**、 をクリックして**構成**します。</span><span class="sxs-lookup"><span data-stu-id="1ddfc-122">In  **Properties**, click **Configure**.</span></span>  
  
    <span data-ttu-id="1ddfc-123">アダプターが既定の送信ハンドラーと共に一覧表示されます。</span><span class="sxs-lookup"><span data-stu-id="1ddfc-123">The adapters are listed with the default Send Handler.</span></span> <span data-ttu-id="1ddfc-124">下矢印をクリックして別のホストを選択します。</span><span class="sxs-lookup"><span data-stu-id="1ddfc-124">Click the down arrow to select a different host.</span></span>  
  
4. <span data-ttu-id="1ddfc-125">クリックして**OK**設定を保存します。</span><span class="sxs-lookup"><span data-stu-id="1ddfc-125">Click **OK** save the settings.</span></span>  
  
5. <span data-ttu-id="1ddfc-126">新しい動的送信ポートの参加を解除してから、もう一度参加させます。</span><span class="sxs-lookup"><span data-stu-id="1ddfc-126">Unenlist and reenlist the new dynamic send port.</span></span>  
  
6. <span data-ttu-id="1ddfc-127">元のホスト インスタンスを再起動します。</span><span class="sxs-lookup"><span data-stu-id="1ddfc-127">Restart the original host instance.</span></span>  
  
7. <span data-ttu-id="1ddfc-128">新しいホスト インスタンスを再起動します。</span><span class="sxs-lookup"><span data-stu-id="1ddfc-128">Restart the new host instance.</span></span>  
  
   <span data-ttu-id="1ddfc-129">送信ポートのその他の構成オプションは次のとおりです。</span><span class="sxs-lookup"><span data-stu-id="1ddfc-129">Additional Send Port configuration options include:</span></span>  
  
- [<span data-ttu-id="1ddfc-130">送信ポートに対してトランスポートの詳細オプションを構成する方法</span><span class="sxs-lookup"><span data-stu-id="1ddfc-130">How to Configure Transport Advanced Options for a Send Port</span></span>](http://go.microsoft.com/fwlink/p/?LinkId=267697)  
  
- [<span data-ttu-id="1ddfc-131">送信ポートに対してバックアップ トランスポートのオプションを構成する方法</span><span class="sxs-lookup"><span data-stu-id="1ddfc-131">How to Configure Backup Transport Options for a Send Port</span></span>](http://go.microsoft.com/fwlink/p/?LinkId=267698)  
  
- [<span data-ttu-id="1ddfc-132">送信ポートの送信マップを構成する方法</span><span class="sxs-lookup"><span data-stu-id="1ddfc-132">How to Configure Outbound Maps for a Send Port</span></span>](http://go.microsoft.com/fwlink/p/?LinkId=267699)  
  
- [<span data-ttu-id="1ddfc-133">送信ポートのフィルターを構成する方法</span><span class="sxs-lookup"><span data-stu-id="1ddfc-133">How to Configure Filters for a Send Port</span></span>](http://go.microsoft.com/fwlink/p/?LinkId=267700)  
  
- [<span data-ttu-id="1ddfc-134">送信ポートに証明書を割り当てる方法</span><span class="sxs-lookup"><span data-stu-id="1ddfc-134">How to Assign a Certificate to a Send Port</span></span>](http://go.microsoft.com/fwlink/p/?LinkId=267701)  
  
- [<span data-ttu-id="1ddfc-135">送信ポートの追跡を構成する方法</span><span class="sxs-lookup"><span data-stu-id="1ddfc-135">How to Configure Tracking for a Send Port</span></span>](http://go.microsoft.com/fwlink/p/?LinkId=267702)  
  
  <span data-ttu-id="1ddfc-136">さまざまなホストを微調整することができます。</span><span class="sxs-lookup"><span data-stu-id="1ddfc-136">The different hosts can be fine-tuned.</span></span> <span data-ttu-id="1ddfc-137">次のリンクでは、パフォーマンスの最適化について説明しています。</span><span class="sxs-lookup"><span data-stu-id="1ddfc-137">The following links discuss performance optimization:</span></span>  
  
  [<span data-ttu-id="1ddfc-138">BizTalk Server の一般的な最適化</span><span class="sxs-lookup"><span data-stu-id="1ddfc-138">General BizTalk Server Optimizations</span></span>](http://go.microsoft.com/fwlink/p/?LinkId=267703)  
  
  [<span data-ttu-id="1ddfc-139">BizTalk Server パフォーマンス設定の管理</span><span class="sxs-lookup"><span data-stu-id="1ddfc-139">Managing BizTalk Server Performance Settings</span></span>](http://go.microsoft.com/fwlink/p/?LinkId=267704)