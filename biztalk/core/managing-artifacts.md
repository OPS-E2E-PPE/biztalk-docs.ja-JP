---
title: "成果物の管理 |Microsoft ドキュメント"
ms.custom: 
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: 
ms.suite: 
ms.tgt_pltfrm: 
ms.topic: article
helpviewer_keywords:
- managing [applications], artifacts
- managing [artifacts]
- artifacts, managing
- managing [artifacts], about managing artificats
ms.assetid: aa7c5e60-7c16-4bcf-b913-b1bdfc5c7543
caps.latest.revision: "13"
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: 0ccca48682f009a24f538015b055c45dd79a9587
ms.sourcegitcommit: cb908c540d8f1a692d01dc8f313e16cb4b4e696d
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 09/20/2017
---
# <a name="managing-artifacts"></a><span data-ttu-id="dc9e0-102">アイテムの管理</span><span class="sxs-lookup"><span data-stu-id="dc9e0-102">Managing Artifacts</span></span>
<span data-ttu-id="dc9e0-103">このセクションでは、アイテムの管理方法について説明します。BizTalk アプリケーションにアイテムを追加したり、BizTalk アプリケーションからアイテムを削除したりする方法のほか、アイテムのプロパティを構成する方法などを紹介します。</span><span class="sxs-lookup"><span data-stu-id="dc9e0-103">This section describes how to manage artifacts, including how to add and remove them from a BizTalk application and how to configure their properties.</span></span>  
  
 <span data-ttu-id="dc9e0-104">BizTalk アプリケーションには、その実行に必要なアイテムが含まれています。</span><span class="sxs-lookup"><span data-stu-id="dc9e0-104">Artifacts are the items contained in a BizTalk application that are required for it to run.</span></span> <span data-ttu-id="dc9e0-105">BizTalk アプリケーション内の成果物の使用方法に関する背景情報については、次を参照してください。 [BizTalk アプリケーションは何ですか。](../core/what-is-a-biztalk-application.md)</span><span class="sxs-lookup"><span data-stu-id="dc9e0-105">For background information about how artifacts are used in a BizTalk application, see [What Is a BizTalk Application?](../core/what-is-a-biztalk-application.md)</span></span> <span data-ttu-id="dc9e0-106">バック グラウンド成果物については、次を参照してください。[ランタイム アーキテクチャ](../core/runtime-architecture.md)です。</span><span class="sxs-lookup"><span data-stu-id="dc9e0-106">For background information about artifacts, see [Runtime Architecture](../core/runtime-architecture.md).</span></span> <span data-ttu-id="dc9e0-107">作成および BizTalk アプリケーションを変更するときにアイテムを操作する方法については、次を参照してください。[を変更する BizTalk アプリケーションの作成と](../core/creating-and-modifying-biztalk-applications.md)です。</span><span class="sxs-lookup"><span data-stu-id="dc9e0-107">For information about how you manipulate artifacts when you create and modify a BizTalk application, see [Creating and Modifying BizTalk Applications](../core/creating-and-modifying-biztalk-applications.md).</span></span>  

## <a name="tracking-artifacts"></a><span data-ttu-id="dc9e0-108">成果物を追跡</span><span class="sxs-lookup"><span data-stu-id="dc9e0-108">Tracking artifacts</span></span>
<span data-ttu-id="dc9e0-109">大きな部分を作成するアイテムを管理するを追跡します。</span><span class="sxs-lookup"><span data-stu-id="dc9e0-109">A big part of managing the artifacts you create is tracking.</span></span> <span data-ttu-id="dc9e0-110">BizTalk Server 管理コンソールを使用して、オーケストレーション、送信ポート、受信ポート、およびパイプラインの実行時にさまざまな追跡オプションを構成できます。</span><span class="sxs-lookup"><span data-stu-id="dc9e0-110">You can configure various tracking options during run time for orchestrations, send ports, receive ports, and pipelines using the BizTalk Server Administration console.</span></span> <span data-ttu-id="dc9e0-111">項目の追跡オプションは、ビジネス プロセスを中断することなく、いつでも変更できます。</span><span class="sxs-lookup"><span data-stu-id="dc9e0-111">You can change the tracking options for an item at any time, without interrupting the business process.</span></span>

<span data-ttu-id="dc9e0-112">追跡の構成設定では、次の種類のデータを追跡することができます。</span><span class="sxs-lookup"><span data-stu-id="dc9e0-112">The tracking configuration settings allow you to track the following types of data:</span></span>

- <span data-ttu-id="dc9e0-113">受信または送信イベント データ。</span><span class="sxs-lookup"><span data-stu-id="dc9e0-113">Inbound and/or outbound event data.</span></span> <span data-ttu-id="dc9e0-114">たとえば、メッセージ ID、アイテムの開始時刻および停止時刻です。</span><span class="sxs-lookup"><span data-stu-id="dc9e0-114">For example, message ID, start and stop times for the artifact.</span></span>

- <span data-ttu-id="dc9e0-115">受信または送信メッセージ プロパティ。</span><span class="sxs-lookup"><span data-stu-id="dc9e0-115">Inbound and/or outbound message properties.</span></span> <span data-ttu-id="dc9e0-116">たとえば、アイテムが処理する各メッセージの全般プロパティや昇格させたプロパティです。</span><span class="sxs-lookup"><span data-stu-id="dc9e0-116">For example, general and promoted properties for each message that the artifact processes.</span></span>

- <span data-ttu-id="dc9e0-117">受信または送信メッセージの本文および部分。</span><span class="sxs-lookup"><span data-stu-id="dc9e0-117">Inbound and/or outbound message bodies and parts.</span></span> <span data-ttu-id="dc9e0-118">たとえば、アイテムが処理する各メッセージの本文やその他の部分です。</span><span class="sxs-lookup"><span data-stu-id="dc9e0-118">For example, body and parts for each message that the artifact processes.</span></span>

- <span data-ttu-id="dc9e0-119">オーケストレーションです。</span><span class="sxs-lookup"><span data-stu-id="dc9e0-119">Orchestrations.</span></span> <span data-ttu-id="dc9e0-120">オーケストレーション図形の実行データ。</span><span class="sxs-lookup"><span data-stu-id="dc9e0-120">Execution data for orchestration shapes.</span></span>

<span data-ttu-id="dc9e0-121">[追跡メッセージおよびインスタンス データを表示する](../core/viewing-tracked-message-and-instance-data.md)よい情報を提供します。</span><span class="sxs-lookup"><span data-stu-id="dc9e0-121">[Viewing Tracked Message and Instance Data](../core/viewing-tracked-message-and-instance-data.md) provides some good info.</span></span> 


> [!TIP]
> <span data-ttu-id="dc9e0-122">パイプラインに追跡オプションを設定した場合、追跡オプションはに対してグローバルに設定、パイプラインを使用するすべてのポートです。</span><span class="sxs-lookup"><span data-stu-id="dc9e0-122">If you set tracking options on a pipeline, then the tracking options are set globally for every port that uses the pipeline.</span></span> <span data-ttu-id="dc9e0-123">これは、結果より多くのデータの追跡を超える場合があり、システムのパフォーマンスに影響を与える可能性があります。</span><span class="sxs-lookup"><span data-stu-id="dc9e0-123">This results in far more data being tracked than you may intend, and may impact system performance.</span></span> <span data-ttu-id="dc9e0-124">開発中は、通常この可能性があります。</span><span class="sxs-lookup"><span data-stu-id="dc9e0-124">During development, this may be normal.</span></span> <span data-ttu-id="dc9e0-125">実稼働のシナリオで、送信ポートの追跡オプションを有効にして、受信パイプラインではなく、ポートお勧めします。</span><span class="sxs-lookup"><span data-stu-id="dc9e0-125">In production scenarios, we recommend you enable any tracking options on the send ports and receive ports, instead of the pipelines.</span></span>
  
## <a name="in-this-section"></a><span data-ttu-id="dc9e0-126">このセクションの内容</span><span class="sxs-lookup"><span data-stu-id="dc9e0-126">In this section</span></span>  
  
-   [<span data-ttu-id="dc9e0-127">オーケストレーションの管理</span><span class="sxs-lookup"><span data-stu-id="dc9e0-127">Managing Orchestrations</span></span>](../core/managing-orchestrations.md)  
  
-   [<span data-ttu-id="dc9e0-128">ロール リンクの管理</span><span class="sxs-lookup"><span data-stu-id="dc9e0-128">Managing Role Links</span></span>](../core/managing-role-links.md)  
  
-   [<span data-ttu-id="dc9e0-129">送信ポートと送信ポート グループの管理</span><span class="sxs-lookup"><span data-stu-id="dc9e0-129">Managing Send Ports and Send Port Groups</span></span>](../core/managing-send-ports-and-send-port-groups.md)  
  
-   [<span data-ttu-id="dc9e0-130">受信ポートの管理</span><span class="sxs-lookup"><span data-stu-id="dc9e0-130">Managing Receive Ports</span></span>](../core/managing-receive-ports.md)  
  
-   [<span data-ttu-id="dc9e0-131">受信場所の管理</span><span class="sxs-lookup"><span data-stu-id="dc9e0-131">Managing Receive Locations</span></span>](../core/managing-receive-locations.md)  
  
-   [<span data-ttu-id="dc9e0-132">ポリシーの管理</span><span class="sxs-lookup"><span data-stu-id="dc9e0-132">Managing Policies</span></span>](../core/managing-policies.md)  
  
-   [<span data-ttu-id="dc9e0-133">スキーマの管理</span><span class="sxs-lookup"><span data-stu-id="dc9e0-133">Managing Schemas</span></span>](../core/managing-schemas.md)  
  
-   [<span data-ttu-id="dc9e0-134">マップを管理します。</span><span class="sxs-lookup"><span data-stu-id="dc9e0-134">Managing Maps</span></span>](../core/managing-maps.md)  
  
-   [<span data-ttu-id="dc9e0-135">パイプラインの管理</span><span class="sxs-lookup"><span data-stu-id="dc9e0-135">Managing Pipelines</span></span>](../core/managing-pipelines.md)  
  
-   [<span data-ttu-id="dc9e0-136">リソースの管理</span><span class="sxs-lookup"><span data-stu-id="dc9e0-136">Managing Resources</span></span>](../core/managing-resources.md)