---
title: 追跡データベースのサイズを記録 |Microsoft Docs
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
ms.openlocfilehash: b1e19e5861a061294806c428d300d475ac2e21c4
ms.sourcegitcommit: 381e83d43796a345488d54b3f7413e11d56ad7be
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 05/07/2019
ms.locfileid: "65398046"
---
# <a name="record-size-in-tracking-databases"></a><span data-ttu-id="bd212-102">追跡データベースのレコード サイズ</span><span class="sxs-lookup"><span data-stu-id="bd212-102">Record Size in Tracking Databases</span></span>
<span data-ttu-id="bd212-103">次の表は、追跡データベースのさまざまなイベント レコードに予期されるレコード サイズを示しています。この表は、BizTalk のハードウェア要件を計画する際に役立ちます。</span><span class="sxs-lookup"><span data-stu-id="bd212-103">To help you plan your hardware requirements for BizTalk, the following table shows the expected record size for various event records in the Tracking database.</span></span>  
  
|<span data-ttu-id="bd212-104">アクションの種類</span><span class="sxs-lookup"><span data-stu-id="bd212-104">Action Type</span></span>|<span data-ttu-id="bd212-105">サイズ</span><span class="sxs-lookup"><span data-stu-id="bd212-105">Size</span></span>|<span data-ttu-id="bd212-106">メモ</span><span class="sxs-lookup"><span data-stu-id="bd212-106">Notes</span></span>|  
|-----------------|----------|-----------|  
|<span data-ttu-id="bd212-107">サービスの展開</span><span class="sxs-lookup"><span data-stu-id="bd212-107">Deploying a Service</span></span>|<span data-ttu-id="bd212-108">1864 + シンボル情報のサイズ。</span><span class="sxs-lookup"><span data-stu-id="bd212-108">1864 + Symbolic Information Size</span></span>|<span data-ttu-id="bd212-109">シンボル情報は、オーケストレーションのサイズによって異なります。</span><span class="sxs-lookup"><span data-stu-id="bd212-109">Symbolic Information depends on the size of the orchestration.</span></span> <span data-ttu-id="bd212-110">たとえば、1 つのメッセージを受信し、1 つのメッセージを送信し、2 つの図形を含むオーケストレーションのサイズは約 4000 バイトです。</span><span class="sxs-lookup"><span data-stu-id="bd212-110">For example, an orchestration that receives one message and sends one message out with 2 shapes in it takes approximately 4000 bytes.</span></span>|  
|<span data-ttu-id="bd212-111">開始して正常に完了したサービスのインスタンス</span><span class="sxs-lookup"><span data-stu-id="bd212-111">Started and Successfully Completed Service Instance</span></span>|<span data-ttu-id="bd212-112">通常は 252 バイト。</span><span class="sxs-lookup"><span data-stu-id="bd212-112">Normally 252 bytes.</span></span><br /><br /> <span data-ttu-id="bd212-113">特殊な場合には 735 バイトまで増大します。</span><span class="sxs-lookup"><span data-stu-id="bd212-113">Extreme cases, can reach 735 bytes.</span></span>||  
|<span data-ttu-id="bd212-114">開始後、失敗したか、例外が発生したサービスのインスタンス</span><span class="sxs-lookup"><span data-stu-id="bd212-114">Started and Failed/Exception Met Service Instance</span></span>|<span data-ttu-id="bd212-115">通常は 252 バイト + エラー情報。</span><span class="sxs-lookup"><span data-stu-id="bd212-115">Normally 252 bytes + error information.</span></span><br /><br /> <span data-ttu-id="bd212-116">特殊な場合には 735 バイト + エラー情報まで増大します。</span><span class="sxs-lookup"><span data-stu-id="bd212-116">Extreme cases can reach 735 bytes + error information.</span></span>|<span data-ttu-id="bd212-117">エラー情報は、BizTalk またはユーザー コンポーネントによって返されるテキスト データです。</span><span class="sxs-lookup"><span data-stu-id="bd212-117">Error information is the text data returned by a BizTalk or user component.</span></span> <span data-ttu-id="bd212-118">このサイズの範囲は 100 バイト ～ 2 KB です。</span><span class="sxs-lookup"><span data-stu-id="bd212-118">Ranges from 100 bytes to 2 KB.</span></span>|  
|<span data-ttu-id="bd212-119">オーケストレーションの開始/終了図形</span><span class="sxs-lookup"><span data-stu-id="bd212-119">Start/End of a Shape In an Orchestration</span></span>|<span data-ttu-id="bd212-120">各 120 バイト。</span><span class="sxs-lookup"><span data-stu-id="bd212-120">120 bytes each.</span></span>||  
|<span data-ttu-id="bd212-121">メッセージ送受信イベント</span><span class="sxs-lookup"><span data-stu-id="bd212-121">Message In/Out Events</span></span>|<span data-ttu-id="bd212-122">最小 162 バイト。</span><span class="sxs-lookup"><span data-stu-id="bd212-122">Minimum 162 bytes.</span></span><br /><br /> <span data-ttu-id="bd212-123">最初に表示されるメッセージのサイズは 202 バイト + メッセージ プロパティ (追跡している場合) になります。</span><span class="sxs-lookup"><span data-stu-id="bd212-123">First time message is seen it is 202 bytes + Message Property (if tracked)</span></span><br /><br /> <span data-ttu-id="bd212-124">2930 バイトにまで到達する極端なケースもあります。</span><span class="sxs-lookup"><span data-stu-id="bd212-124">Extreme cases can reach 2930 bytes.</span></span>|<span data-ttu-id="bd212-125">メッセージ プロパティを追跡していない場合、平均的なサイズは 182 バイトと見なすことができます。</span><span class="sxs-lookup"><span data-stu-id="bd212-125">You can safely assume that the average is 182 bytes if there is no message property tracking.</span></span>|  
|<span data-ttu-id="bd212-126">メッセージ プロパティのサイズ</span><span class="sxs-lookup"><span data-stu-id="bd212-126">Message Property Size</span></span>|<span data-ttu-id="bd212-127">この追跡プロパティが DTA によって認識される場合は 40 ～ 288 バイト。</span><span class="sxs-lookup"><span data-stu-id="bd212-127">40 to 288 bytes if DTA recognizes this tracking property.</span></span><br /><br /> <span data-ttu-id="bd212-128">最初にプロパティを追跡する場合は、最大で 268 バイトを追加します。</span><span class="sxs-lookup"><span data-stu-id="bd212-128">Add up to 268 bytes for tracking the property the first time.</span></span>||  
  
## <a name="see-also"></a><span data-ttu-id="bd212-129">参照</span><span class="sxs-lookup"><span data-stu-id="bd212-129">See Also</span></span>  
 <span data-ttu-id="bd212-130">[メッセージの追跡とは](../core/what-is-message-tracking.md) </span><span class="sxs-lookup"><span data-stu-id="bd212-130">[What is Message Tracking?](../core/what-is-message-tracking.md) </span></span>  
 [<span data-ttu-id="bd212-131">アーキテクチャの管理および追跡</span><span class="sxs-lookup"><span data-stu-id="bd212-131">Management and Tracking Architecture</span></span>](../core/management-and-tracking-architecture.md)