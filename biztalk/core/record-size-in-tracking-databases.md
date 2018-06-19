---
title: 追跡データベースのレコード サイズ |Microsoft ドキュメント
ms.custom: ''
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: ''
ms.suite: ''
ms.tgt_pltfrm: ''
ms.topic: article
helpviewer_keywords:
- Tracking database, database size
ms.assetid: be7a891b-2674-49a3-a8e0-6aa11a918bf2
caps.latest.revision: 10
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: d1f4d09d1af92ce4777f5036885d81ea7bf3e648
ms.sourcegitcommit: cb908c540d8f1a692d01dc8f313e16cb4b4e696d
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 09/20/2017
ms.locfileid: "22268314"
---
# <a name="record-size-in-tracking-databases"></a><span data-ttu-id="6ba41-102">追跡データベースのレコード サイズ</span><span class="sxs-lookup"><span data-stu-id="6ba41-102">Record Size in Tracking Databases</span></span>
<span data-ttu-id="6ba41-103">次の表は、追跡データベースのさまざまなイベント レコードに予期されるレコード サイズを示しています。この表は、BizTalk のハードウェア要件を計画する際に役立ちます。</span><span class="sxs-lookup"><span data-stu-id="6ba41-103">To help you plan your hardware requirements for BizTalk, the following table shows the expected record size for various event records in the Tracking database.</span></span>  
  
|<span data-ttu-id="6ba41-104">アクションの種類</span><span class="sxs-lookup"><span data-stu-id="6ba41-104">Action Type</span></span>|<span data-ttu-id="6ba41-105">サイズ</span><span class="sxs-lookup"><span data-stu-id="6ba41-105">Size</span></span>|<span data-ttu-id="6ba41-106">注</span><span class="sxs-lookup"><span data-stu-id="6ba41-106">Notes</span></span>|  
|-----------------|----------|-----------|  
|<span data-ttu-id="6ba41-107">サービスの展開</span><span class="sxs-lookup"><span data-stu-id="6ba41-107">Deploying a Service</span></span>|<span data-ttu-id="6ba41-108">1864 + シンボル情報のサイズ。</span><span class="sxs-lookup"><span data-stu-id="6ba41-108">1864 + Symbolic Information Size</span></span>|<span data-ttu-id="6ba41-109">シンボル情報は、オーケストレーションのサイズによって異なります。</span><span class="sxs-lookup"><span data-stu-id="6ba41-109">Symbolic Information depends on the size of the orchestration.</span></span> <span data-ttu-id="6ba41-110">たとえば、1 つのメッセージを受信し、1 つのメッセージを送信し、2 つの図形を含むオーケストレーションのサイズは約 4000 バイトです。</span><span class="sxs-lookup"><span data-stu-id="6ba41-110">For example, an orchestration that receives one message and sends one message out with 2 shapes in it takes approximately 4000 bytes.</span></span>|  
|<span data-ttu-id="6ba41-111">開始して正常に完了したサービスのインスタンス</span><span class="sxs-lookup"><span data-stu-id="6ba41-111">Started and Successfully Completed Service Instance</span></span>|<span data-ttu-id="6ba41-112">通常は 252 バイト。</span><span class="sxs-lookup"><span data-stu-id="6ba41-112">Normally 252 bytes.</span></span><br /><br /> <span data-ttu-id="6ba41-113">特殊な場合には 735 バイトまで増大します。</span><span class="sxs-lookup"><span data-stu-id="6ba41-113">Extreme cases, can reach 735 bytes.</span></span>||  
|<span data-ttu-id="6ba41-114">開始後、失敗したか、例外が発生したサービスのインスタンス</span><span class="sxs-lookup"><span data-stu-id="6ba41-114">Started and Failed/Exception Met Service Instance</span></span>|<span data-ttu-id="6ba41-115">通常は 252 バイト + エラー情報。</span><span class="sxs-lookup"><span data-stu-id="6ba41-115">Normally 252 bytes + error information.</span></span><br /><br /> <span data-ttu-id="6ba41-116">特殊な場合には 735 バイト + エラー情報まで増大します。</span><span class="sxs-lookup"><span data-stu-id="6ba41-116">Extreme cases can reach 735 bytes + error information.</span></span>|<span data-ttu-id="6ba41-117">エラー情報は、BizTalk またはユーザー コンポーネントによって返されるテキスト データです。</span><span class="sxs-lookup"><span data-stu-id="6ba41-117">Error information is the text data returned by a BizTalk or user component.</span></span> <span data-ttu-id="6ba41-118">このサイズの範囲は 100 バイト ～ 2 KB です。</span><span class="sxs-lookup"><span data-stu-id="6ba41-118">Ranges from 100 bytes to 2 KB.</span></span>|  
|<span data-ttu-id="6ba41-119">オーケストレーションの開始/終了図形</span><span class="sxs-lookup"><span data-stu-id="6ba41-119">Start/End of a Shape In an Orchestration</span></span>|<span data-ttu-id="6ba41-120">各 120 バイト。</span><span class="sxs-lookup"><span data-stu-id="6ba41-120">120 bytes each.</span></span>||  
|<span data-ttu-id="6ba41-121">メッセージ送受信イベント</span><span class="sxs-lookup"><span data-stu-id="6ba41-121">Message In/Out Events</span></span>|<span data-ttu-id="6ba41-122">最小 162 バイト。</span><span class="sxs-lookup"><span data-stu-id="6ba41-122">Minimum 162 bytes.</span></span><br /><br /> <span data-ttu-id="6ba41-123">最初に表示されるメッセージのサイズは 202 バイト + メッセージ プロパティ (追跡している場合) になります。</span><span class="sxs-lookup"><span data-stu-id="6ba41-123">First time message is seen it is 202 bytes + Message Property (if tracked)</span></span><br /><br /> <span data-ttu-id="6ba41-124">2930 バイトにまで到達する極端なケースもあります。</span><span class="sxs-lookup"><span data-stu-id="6ba41-124">Extreme cases can reach 2930 bytes.</span></span>|<span data-ttu-id="6ba41-125">メッセージ プロパティを追跡していない場合、平均的なサイズは 182 バイトと見なすことができます。</span><span class="sxs-lookup"><span data-stu-id="6ba41-125">You can safely assume that the average is 182 bytes if there is no message property tracking.</span></span>|  
|<span data-ttu-id="6ba41-126">メッセージ プロパティのサイズ</span><span class="sxs-lookup"><span data-stu-id="6ba41-126">Message Property Size</span></span>|<span data-ttu-id="6ba41-127">この追跡プロパティが DTA によって認識される場合は 40 ～ 288 バイト。</span><span class="sxs-lookup"><span data-stu-id="6ba41-127">40 to 288 bytes if DTA recognizes this tracking property.</span></span><br /><br /> <span data-ttu-id="6ba41-128">最初にプロパティを追跡する場合は、最大で 268 バイトを追加します。</span><span class="sxs-lookup"><span data-stu-id="6ba41-128">Add up to 268 bytes for tracking the property the first time.</span></span>||  
  
## <a name="see-also"></a><span data-ttu-id="6ba41-129">参照</span><span class="sxs-lookup"><span data-stu-id="6ba41-129">See Also</span></span>  
 <span data-ttu-id="6ba41-130">[メッセージの追跡とは](../core/what-is-message-tracking.md) </span><span class="sxs-lookup"><span data-stu-id="6ba41-130">[What is Message Tracking?](../core/what-is-message-tracking.md) </span></span>  
 [<span data-ttu-id="6ba41-131">管理と追跡アーキテクチャ</span><span class="sxs-lookup"><span data-stu-id="6ba41-131">Management and Tracking Architecture</span></span>](../core/management-and-tracking-architecture.md)