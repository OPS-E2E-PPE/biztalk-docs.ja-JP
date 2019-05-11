---
title: アイテムの管理 |Microsoft Docs
ms.custom: ''
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: ''
ms.suite: ''
ms.tgt_pltfrm: ''
ms.topic: article
helpviewer_keywords:
- managing [applications], artifacts
- managing [artifacts]
- artifacts, managing
- managing [artifacts], about managing artificats
ms.assetid: aa7c5e60-7c16-4bcf-b913-b1bdfc5c7543
caps.latest.revision: 13
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: 2327f1093658a7d6e01472e393fea40120abd6c0
ms.sourcegitcommit: 381e83d43796a345488d54b3f7413e11d56ad7be
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 05/07/2019
ms.locfileid: "65380402"
---
# <a name="managing-artifacts"></a><span data-ttu-id="50123-102">アイテムの管理</span><span class="sxs-lookup"><span data-stu-id="50123-102">Managing Artifacts</span></span>
<span data-ttu-id="50123-103">このセクションは、アーティファクトを管理する方法を説明を追加し、BizTalk アプリケーションから削除する方法など、そのプロパティを構成する方法。</span><span class="sxs-lookup"><span data-stu-id="50123-103">This section describes how to manage artifacts, including how to add and remove them from a BizTalk application and how to configure their properties.</span></span>  
  
 <span data-ttu-id="50123-104">成果物は、その実行に必要な BizTalk アプリケーションに含まれる項目です。</span><span class="sxs-lookup"><span data-stu-id="50123-104">Artifacts are the items contained in a BizTalk application that are required for it to run.</span></span> <span data-ttu-id="50123-105">BizTalk アプリケーションでの成果物の使用方法については、次を参照してください[BizTalk アプリケーションとは何ですか?。](../core/what-is-a-biztalk-application.md)</span><span class="sxs-lookup"><span data-stu-id="50123-105">For background information about how artifacts are used in a BizTalk application, see [What Is a BizTalk Application?](../core/what-is-a-biztalk-application.md)</span></span> <span data-ttu-id="50123-106">アイテムの背景については、次を参照してください。[ランタイム アーキテクチャ](../core/runtime-architecture.md)します。</span><span class="sxs-lookup"><span data-stu-id="50123-106">For background information about artifacts, see [Runtime Architecture](../core/runtime-architecture.md).</span></span> <span data-ttu-id="50123-107">作成して BizTalk アプリケーションを変更するときにアイテムを操作する方法については、次を参照してください。[を変更する BizTalk アプリケーションの作成と](../core/creating-and-modifying-biztalk-applications.md)します。</span><span class="sxs-lookup"><span data-stu-id="50123-107">For information about how you manipulate artifacts when you create and modify a BizTalk application, see [Creating and Modifying BizTalk Applications](../core/creating-and-modifying-biztalk-applications.md).</span></span>  

## <a name="tracking-artifacts"></a><span data-ttu-id="50123-108">成果物を追跡</span><span class="sxs-lookup"><span data-stu-id="50123-108">Tracking artifacts</span></span>
<span data-ttu-id="50123-109">作成するアイテムの管理の大きな部分を追跡します。</span><span class="sxs-lookup"><span data-stu-id="50123-109">A big part of managing the artifacts you create is tracking.</span></span> <span data-ttu-id="50123-110">オーケストレーションの実行時にさまざまな追跡オプションを構成、送信ポート、受信ポート、およびパイプラインが BizTalk Server 管理コンソールを使用することができます。</span><span class="sxs-lookup"><span data-stu-id="50123-110">You can configure various tracking options during run time for orchestrations, send ports, receive ports, and pipelines using the BizTalk Server Administration console.</span></span> <span data-ttu-id="50123-111">項目の追跡オプションは、ビジネス プロセスを中断することがなく、いつでも変更できます。</span><span class="sxs-lookup"><span data-stu-id="50123-111">You can change the tracking options for an item at any time, without interrupting the business process.</span></span>

<span data-ttu-id="50123-112">追跡構成設定では、次の種類のデータを追跡することができます。</span><span class="sxs-lookup"><span data-stu-id="50123-112">The tracking configuration settings allow you to track the following types of data:</span></span>

- <span data-ttu-id="50123-113">受信または送信イベント データ。</span><span class="sxs-lookup"><span data-stu-id="50123-113">Inbound and/or outbound event data.</span></span> <span data-ttu-id="50123-114">たとえば、メッセージ ID、開始、停止、成果物の時間します。</span><span class="sxs-lookup"><span data-stu-id="50123-114">For example, message ID, start and stop times for the artifact.</span></span>

- <span data-ttu-id="50123-115">受信または送信メッセージのプロパティです。</span><span class="sxs-lookup"><span data-stu-id="50123-115">Inbound and/or outbound message properties.</span></span> <span data-ttu-id="50123-116">たとえば、アイテムが処理される各メッセージの [全般] と昇格させたプロパティです。</span><span class="sxs-lookup"><span data-stu-id="50123-116">For example, general and promoted properties for each message that the artifact processes.</span></span>

- <span data-ttu-id="50123-117">受信または送信メッセージの本文および部分。</span><span class="sxs-lookup"><span data-stu-id="50123-117">Inbound and/or outbound message bodies and parts.</span></span> <span data-ttu-id="50123-118">たとえば、本文とメッセージごとにアイテムが処理する部分。</span><span class="sxs-lookup"><span data-stu-id="50123-118">For example, body and parts for each message that the artifact processes.</span></span>

- <span data-ttu-id="50123-119">オーケストレーションします。</span><span class="sxs-lookup"><span data-stu-id="50123-119">Orchestrations.</span></span> <span data-ttu-id="50123-120">オーケストレーション図形のデータを実行します。</span><span class="sxs-lookup"><span data-stu-id="50123-120">Execution data for orchestration shapes.</span></span>

<span data-ttu-id="50123-121">[追跡メッセージおよびインスタンス データを表示する](../core/viewing-tracked-message-and-instance-data.md)なかなかよい情報を提供します。</span><span class="sxs-lookup"><span data-stu-id="50123-121">[Viewing Tracked Message and Instance Data](../core/viewing-tracked-message-and-instance-data.md) provides some good info.</span></span> 


> [!TIP]
> <span data-ttu-id="50123-122">パイプラインに追跡オプションを設定した場合、追跡オプションはグローバルに設定パイプラインを使用するすべてのポートに対して。</span><span class="sxs-lookup"><span data-stu-id="50123-122">If you set tracking options on a pipeline, then the tracking options are set globally for every port that uses the pipeline.</span></span> <span data-ttu-id="50123-123">これは、結果より多くのデータの場合があり、システムのパフォーマンスに影響を与える可能性よりも追跡されています。</span><span class="sxs-lookup"><span data-stu-id="50123-123">This results in far more data being tracked than you may intend, and may impact system performance.</span></span> <span data-ttu-id="50123-124">開発中は、通常この可能性があります。</span><span class="sxs-lookup"><span data-stu-id="50123-124">During development, this may be normal.</span></span> <span data-ttu-id="50123-125">運用環境シナリオでは、送信ポートの追跡オプションを有効にし、受信ポートのパイプラインではなく、お勧めします。</span><span class="sxs-lookup"><span data-stu-id="50123-125">In production scenarios, we recommend you enable any tracking options on the send ports and receive ports, instead of the pipelines.</span></span>
  
## <a name="in-this-section"></a><span data-ttu-id="50123-126">このセクションの内容</span><span class="sxs-lookup"><span data-stu-id="50123-126">In this section</span></span>  
  
-   [<span data-ttu-id="50123-127">オーケストレーションの管理</span><span class="sxs-lookup"><span data-stu-id="50123-127">Managing Orchestrations</span></span>](../core/managing-orchestrations.md)  
  
-   [<span data-ttu-id="50123-128">ロール リンクの管理</span><span class="sxs-lookup"><span data-stu-id="50123-128">Managing Role Links</span></span>](../core/managing-role-links.md)  
  
-   [<span data-ttu-id="50123-129">送信ポートと送信ポート グループの管理</span><span class="sxs-lookup"><span data-stu-id="50123-129">Managing Send Ports and Send Port Groups</span></span>](../core/managing-send-ports-and-send-port-groups.md)  
  
-   [<span data-ttu-id="50123-130">受信ポートの管理</span><span class="sxs-lookup"><span data-stu-id="50123-130">Managing Receive Ports</span></span>](../core/managing-receive-ports.md)  
  
-   [<span data-ttu-id="50123-131">受信場所の管理</span><span class="sxs-lookup"><span data-stu-id="50123-131">Managing Receive Locations</span></span>](../core/managing-receive-locations.md)  
  
-   [<span data-ttu-id="50123-132">ポリシーの管理</span><span class="sxs-lookup"><span data-stu-id="50123-132">Managing Policies</span></span>](../core/managing-policies.md)  
  
-   [<span data-ttu-id="50123-133">スキーマの管理</span><span class="sxs-lookup"><span data-stu-id="50123-133">Managing Schemas</span></span>](../core/managing-schemas.md)  
  
-   [<span data-ttu-id="50123-134">マップの管理</span><span class="sxs-lookup"><span data-stu-id="50123-134">Managing Maps</span></span>](../core/managing-maps.md)  
  
-   [<span data-ttu-id="50123-135">パイプラインの管理</span><span class="sxs-lookup"><span data-stu-id="50123-135">Managing Pipelines</span></span>](../core/managing-pipelines.md)  
  
-   [<span data-ttu-id="50123-136">リソースの管理</span><span class="sxs-lookup"><span data-stu-id="50123-136">Managing Resources</span></span>](../core/managing-resources.md)