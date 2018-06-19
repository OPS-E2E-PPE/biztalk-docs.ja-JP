---
title: 'レッスン 2: 表示され、通知をフィルター処理 |Microsoft ドキュメント'
ms.custom: ''
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: ''
ms.suite: ''
ms.tgt_pltfrm: ''
ms.topic: article
ms.assetid: b5ec679c-1c67-4bf4-aa88-0787373343f5
caps.latest.revision: 3
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: 0f28d0479510078b3717d68f99976808ee19aa7c
ms.sourcegitcommit: cb908c540d8f1a692d01dc8f313e16cb4b4e696d
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 09/20/2017
ms.locfileid: "22222554"
---
# <a name="lesson-2-receive-and-filter-notifications"></a><span data-ttu-id="ceeee-102">レッスン 2: 表示され、通知をフィルター処理</span><span class="sxs-lookup"><span data-stu-id="ceeee-102">Lesson 2: Receive and Filter Notifications</span></span>
<span data-ttu-id="ceeee-103">このレッスンで開始するへの変更の通知を受信するオーケストレーションを作成、**従業員**テーブル。</span><span class="sxs-lookup"><span data-stu-id="ceeee-103">In this lesson, you start creating an orchestration that receives notifications for changes to the **Employee** table.</span></span> <span data-ttu-id="ceeee-104">通知とかどうか、通知の種類の挿入操作の種類を抽出し、オーケストレーションは、通知を受信した後、**従業員**テーブル、"if"条件を使用して後続のタスクを実行します。</span><span class="sxs-lookup"><span data-stu-id="ceeee-104">After the orchestration receives the notification, it extracts the type of notification and if the notification type is for an Insert operation on the **Employee** table, an “if” condition is used to perform subsequent tasks.</span></span> <span data-ttu-id="ceeee-105">このレッスンでは、次のタスクを行います。</span><span class="sxs-lookup"><span data-stu-id="ceeee-105">In this lesson, you will perform the following tasks:</span></span>  
  
1.  <span data-ttu-id="ceeee-106">追加、一方向受信ポートと**受信**通知メッセージを受信するオーケストレーションに図形です。</span><span class="sxs-lookup"><span data-stu-id="ceeee-106">Add a one-way receive port and a **Receive** shape to the orchestration to receive the notification message.</span></span>  
  
2.  <span data-ttu-id="ceeee-107">追加、**式**通知の種類を抽出する xpath クエリを含む図形です。</span><span class="sxs-lookup"><span data-stu-id="ceeee-107">Add an **Expression** shape that contains an xpath query to extract the type of notification.</span></span>  
  
3.  <span data-ttu-id="ceeee-108">通知の種類がわかっている後にフィルターを追加、オーケストレーションを含めることによって、**判断**図形です。</span><span class="sxs-lookup"><span data-stu-id="ceeee-108">After the notification type is known, add a filter to the orchestration by including a **Decide** shape.</span></span> <span data-ttu-id="ceeee-109">この図形は、通知が挿入の通知し、後続の操作を実行するかどうかを決定します。</span><span class="sxs-lookup"><span data-stu-id="ceeee-109">This shape decides whether the notification is for an Insert notification and then performs subsequent operations.</span></span> <span data-ttu-id="ceeee-110">挿入操作の通知がない場合は、オーケストレーションは何も実行されません。</span><span class="sxs-lookup"><span data-stu-id="ceeee-110">If the notification is not for an Insert operation, the orchestration does not do anything.</span></span>  
  
## <a name="in-this-section"></a><span data-ttu-id="ceeee-111">このセクションの内容</span><span class="sxs-lookup"><span data-stu-id="ceeee-111">In This Section</span></span>  
  
-   [<span data-ttu-id="ceeee-112">手順 1: 通知を受信するオーケストレーション図形を追加します。</span><span class="sxs-lookup"><span data-stu-id="ceeee-112">Step 1: Add Orchestration Shapes to Receive Notification</span></span>](../../adapters-and-accelerators/adapter-sql/step-1-add-orchestration-shapes-to-receive-notification.md)  
  
-   [<span data-ttu-id="ceeee-113">手順 2: 通知メッセージからの通知の種類を抽出します。</span><span class="sxs-lookup"><span data-stu-id="ceeee-113">Step 2: Extract Notification Type from Notification Message</span></span>](../../adapters-and-accelerators/adapter-sql/step-2-extract-notification-type-from-notification-message.md)  
  
-   [<span data-ttu-id="ceeee-114">手順 3: 挿入の通知にフィルターを追加します。</span><span class="sxs-lookup"><span data-stu-id="ceeee-114">Step 3: Add a Filter for Insert Notifications</span></span>](../../adapters-and-accelerators/adapter-sql/step-3-add-a-filter-for-insert-notifications.md)