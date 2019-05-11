---
title: 追跡対象のデータの理解 |Microsoft Docs
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
ms.openlocfilehash: 3f8119c78bdab44279feebef3a4460303b3ae78c
ms.sourcegitcommit: 381e83d43796a345488d54b3f7413e11d56ad7be
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 05/07/2019
ms.locfileid: "65292775"
---
# <a name="understanding-tracked-data"></a><span data-ttu-id="7c122-102">追跡データについて</span><span class="sxs-lookup"><span data-stu-id="7c122-102">Understanding Tracked Data</span></span>
<span data-ttu-id="7c122-103">追跡クエリを実行すると、クエリ結果 ウィンドウの下部に結果の一覧で追跡される情報が表示されます。</span><span class="sxs-lookup"><span data-stu-id="7c122-103">When you run a tracking query, the tracked information appears in the results list at the bottom of the Query Results window.</span></span>  
  
## <a name="viewing-message-details"></a><span data-ttu-id="7c122-104">メッセージの詳細を表示します。</span><span class="sxs-lookup"><span data-stu-id="7c122-104">Viewing message details</span></span>  
 <span data-ttu-id="7c122-105">メッセージのプロパティを追跡できます。</span><span class="sxs-lookup"><span data-stu-id="7c122-105">You can track message properties.</span></span> <span data-ttu-id="7c122-106">追跡されたメッセージ本文をファイルに保存し、それらを表示できるサードパーティ製のツールを使用します。</span><span class="sxs-lookup"><span data-stu-id="7c122-106">You can also save tracked message bodies to a file and view them using non-Microsoft tools.</span></span>  
  
-   <span data-ttu-id="7c122-107">サービス インスタンスによって参照されるすべてのメッセージを右クリックし、メッセージの詳細を選択できます。</span><span class="sxs-lookup"><span data-stu-id="7c122-107">You can right-click any message referenced by a service instance and select Message details.</span></span>  
  
-   <span data-ttu-id="7c122-108">メッセージの処理が既にが追跡されている場合: 追跡を有効にする必要があるので、-、ハード_ディスクに保存して調査できます。</span><span class="sxs-lookup"><span data-stu-id="7c122-108">If the message is already processed but it was tracked—because you had tracking turned on—you can save it to your hard disk and examine it.</span></span>  
  
-   <span data-ttu-id="7c122-109">オーケストレーション インスタンスに接続し、オーケストレーション デバッガーを使用できます。</span><span class="sxs-lookup"><span data-stu-id="7c122-109">You can attach to the orchestration instance and use the Orchestration Debugger.</span></span>  
  
## <a name="viewing-service-events"></a><span data-ttu-id="7c122-110">サービスのイベントを表示します。</span><span class="sxs-lookup"><span data-stu-id="7c122-110">Viewing service events</span></span>  
 <span data-ttu-id="7c122-111">使用してサービスを調査するには、イベント ログに中断されたサービスが表示されたら、**メッセージ フロー**、**オーケストレーション デバッガー**、**追跡メッセージ イベントの表示**、**Live サービス インスタンスの表示**、オプションを**コンテキスト**メニュー。</span><span class="sxs-lookup"><span data-stu-id="7c122-111">When a suspended service appears in the event log, you can investigate a service by using the **Message Flow**, **Orchestration Debugger**, **Show Tracked Message Events**, **Show Live Service Instances**, options from the **Context** menu.</span></span>  
  
## <a name="viewing-orchestration-events"></a><span data-ttu-id="7c122-112">オーケストレーションのイベントを表示します。</span><span class="sxs-lookup"><span data-stu-id="7c122-112">Viewing orchestration events</span></span>  
 <span data-ttu-id="7c122-113">オーケストレーションで使用してメッセージ インスタンス パスを表示するオーケストレーション デバッガーがかかりました。</span><span class="sxs-lookup"><span data-stu-id="7c122-113">Use the Orchestration Debugger to view the path a message instance has taken through an orchestration.</span></span> <span data-ttu-id="7c122-114">をステップ実行して、オーケストレーションの表示の画像、メッセージの進行状況を示しています。 デバッグのためのオーケストレーションにブレークポイントを配置することができます。</span><span class="sxs-lookup"><span data-stu-id="7c122-114">As you step through, a rendered image of the orchestration shows the progress of the message, and allows you to place breakpoints in the orchestration for debugging purposes.</span></span>  
  
## <a name="in-this-section"></a><span data-ttu-id="7c122-115">このセクションの内容</span><span class="sxs-lookup"><span data-stu-id="7c122-115">In This Section</span></span>  
  
-   [<span data-ttu-id="7c122-116">メッセージ追跡について</span><span class="sxs-lookup"><span data-stu-id="7c122-116">What is Message Tracking?</span></span>](../core/what-is-message-tracking.md)  
  
-   [<span data-ttu-id="7c122-117">イベント追跡について</span><span class="sxs-lookup"><span data-stu-id="7c122-117">What is Event Tracking?</span></span>](../core/what-is-event-tracking.md)