---
title: 追跡データを理解する |Microsoft ドキュメント
ms.custom: ''
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: ''
ms.suite: ''
ms.tgt_pltfrm: ''
ms.topic: article
helpviewer_keywords:
- instances, viewing
- service instances, viewing
- viewing, suspended instances
- messages, viewing
- viewing, service details
- viewing, orchestration details
- viewing, message details
- orchestrations, viewing
- suspended instances
- instances, suspended
ms.assetid: dcc3fbd5-cd2c-4780-a577-0ccd521cf5eb
caps.latest.revision: 16
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: ed30934ca154c8b6921682112b12d016c57f92be
ms.sourcegitcommit: cb908c540d8f1a692d01dc8f313e16cb4b4e696d
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 09/20/2017
ms.locfileid: "22286586"
---
# <a name="understanding-tracked-data"></a><span data-ttu-id="2b862-102">追跡データについて</span><span class="sxs-lookup"><span data-stu-id="2b862-102">Understanding Tracked Data</span></span>
<span data-ttu-id="2b862-103">クエリの追跡を実行すると、クエリ結果ウィンドウ下部の結果一覧に追跡情報が表示されます。</span><span class="sxs-lookup"><span data-stu-id="2b862-103">When you run a tracking query, the tracked information appears in the results list at the bottom of the Query Results window.</span></span>  
  
## <a name="viewing-message-details"></a><span data-ttu-id="2b862-104">メッセージの詳細の表示</span><span class="sxs-lookup"><span data-stu-id="2b862-104">Viewing message details</span></span>  
 <span data-ttu-id="2b862-105">メッセージのプロパティを追跡できます。</span><span class="sxs-lookup"><span data-stu-id="2b862-105">You can track message properties.</span></span> <span data-ttu-id="2b862-106">できますも追跡されたメッセージ本文をファイルに保存して表示すること、Microsoft 以外のツールを使用します。</span><span class="sxs-lookup"><span data-stu-id="2b862-106">You can also save tracked message bodies to a file and view them using non-Microsoft tools.</span></span>  
  
-   <span data-ttu-id="2b862-107">サービス インスタンスによって参照されているメッセージを右クリックし、[メッセージの詳細] をクリックします。</span><span class="sxs-lookup"><span data-stu-id="2b862-107">You can right-click any message referenced by a service instance and select Message details.</span></span>  
  
-   <span data-ttu-id="2b862-108">既に処理されたメッセージでも、追跡を有効にしていて追跡が行われていれば、ハード ディスクに保存して調査できます。</span><span class="sxs-lookup"><span data-stu-id="2b862-108">If the message is already processed but it was tracked—because you had tracking turned on—you can save it to your hard disk and examine it.</span></span>  
  
-   <span data-ttu-id="2b862-109">オーケストレーション インスタンスに接続し、オーケストレーション デバッガーを使用できます。</span><span class="sxs-lookup"><span data-stu-id="2b862-109">You can attach to the orchestration instance and use the Orchestration Debugger.</span></span>  
  
## <a name="viewing-service-events"></a><span data-ttu-id="2b862-110">サービス イベントの表示</span><span class="sxs-lookup"><span data-stu-id="2b862-110">Viewing service events</span></span>  
 <span data-ttu-id="2b862-111">使用してサービスを調査するには、イベント ログに中断されたサービスが表示されたら、**メッセージ フロー**、**オーケストレーション デバッガー**、**追跡メッセージ イベントの表示**、**Live サービス インスタンスの表示**、オプションを**コンテキスト**メニュー。</span><span class="sxs-lookup"><span data-stu-id="2b862-111">When a suspended service appears in the event log, you can investigate a service by using the **Message Flow**, **Orchestration Debugger**, **Show Tracked Message Events**, **Show Live Service Instances**, options from the **Context** menu.</span></span>  
  
## <a name="viewing-orchestration-events"></a><span data-ttu-id="2b862-112">オーケストレーション イベントの表示</span><span class="sxs-lookup"><span data-stu-id="2b862-112">Viewing orchestration events</span></span>  
 <span data-ttu-id="2b862-113">オーケストレーション デバッガーを使用して、メッセージ インスタンスがオーケストレーションを通過したときのパスを表示できます。</span><span class="sxs-lookup"><span data-stu-id="2b862-113">Use the Orchestration Debugger to view the path a message instance has taken through an orchestration.</span></span> <span data-ttu-id="2b862-114">パスをたどると、表示されたオーケストレーションの画像にメッセージ処理の進行状況が示されたり、オーケストレーション内にデバッグ用のブレークポイントを設けることができます。</span><span class="sxs-lookup"><span data-stu-id="2b862-114">As you step through, a rendered image of the orchestration shows the progress of the message, and allows you to place breakpoints in the orchestration for debugging purposes.</span></span>  
  
## <a name="in-this-section"></a><span data-ttu-id="2b862-115">このセクションの内容</span><span class="sxs-lookup"><span data-stu-id="2b862-115">In This Section</span></span>  
  
-   [<span data-ttu-id="2b862-116">メッセージの追跡とは</span><span class="sxs-lookup"><span data-stu-id="2b862-116">What is Message Tracking?</span></span>](../core/what-is-message-tracking.md)  
  
-   [<span data-ttu-id="2b862-117">イベントの追跡とは</span><span class="sxs-lookup"><span data-stu-id="2b862-117">What is Event Tracking?</span></span>](../core/what-is-event-tracking.md)