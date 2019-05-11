---
title: レッスン 2:受信して通知をフィルター処理 |Microsoft Docs
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
ms.openlocfilehash: 1d2814065e188f72d42b444e04ad11ace0194d6a
ms.sourcegitcommit: 381e83d43796a345488d54b3f7413e11d56ad7be
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 05/07/2019
ms.locfileid: "65368877"
---
# <a name="lesson-2-receive-and-filter-notifications"></a><span data-ttu-id="1a871-102">レッスン 2:受信して通知をフィルター処理</span><span class="sxs-lookup"><span data-stu-id="1a871-102">Lesson 2: Receive and Filter Notifications</span></span>
<span data-ttu-id="1a871-103">変更の通知を受信するオーケストレーションの作成を開始するこのレッスンで、**従業員**テーブル。</span><span class="sxs-lookup"><span data-stu-id="1a871-103">In this lesson, you start creating an orchestration that receives notifications for changes to the **Employee** table.</span></span> <span data-ttu-id="1a871-104">通知で通知の種類は、挿入操作のかどうかの型を抽出し、オーケストレーションは、通知を受信後、**従業員**テーブル、"if"条件を使用して後続のタスクを実行します。</span><span class="sxs-lookup"><span data-stu-id="1a871-104">After the orchestration receives the notification, it extracts the type of notification and if the notification type is for an Insert operation on the **Employee** table, an “if” condition is used to perform subsequent tasks.</span></span> <span data-ttu-id="1a871-105">このレッスンでは、次のタスクを行います。</span><span class="sxs-lookup"><span data-stu-id="1a871-105">In this lesson, you will perform the following tasks:</span></span>  
  
1.  <span data-ttu-id="1a871-106">追加、一方向受信ポートと**受信**通知メッセージを受信するオーケストレーションに図形。</span><span class="sxs-lookup"><span data-stu-id="1a871-106">Add a one-way receive port and a **Receive** shape to the orchestration to receive the notification message.</span></span>  
  
2.  <span data-ttu-id="1a871-107">追加、**式**通知の種類を抽出する xpath クエリを格納している図形。</span><span class="sxs-lookup"><span data-stu-id="1a871-107">Add an **Expression** shape that contains an xpath query to extract the type of notification.</span></span>  
  
3.  <span data-ttu-id="1a871-108">通知の種類がわかったら、フィルターを追加、オーケストレーションを含めることによって、**判断**図形。</span><span class="sxs-lookup"><span data-stu-id="1a871-108">After the notification type is known, add a filter to the orchestration by including a **Decide** shape.</span></span> <span data-ttu-id="1a871-109">この図形は、通知が挿入通知し、後続の操作を実行するかどうかを決定します。</span><span class="sxs-lookup"><span data-stu-id="1a871-109">This shape decides whether the notification is for an Insert notification and then performs subsequent operations.</span></span> <span data-ttu-id="1a871-110">挿入操作では、通知がない場合、オーケストレーションは何も行いません。</span><span class="sxs-lookup"><span data-stu-id="1a871-110">If the notification is not for an Insert operation, the orchestration does not do anything.</span></span>  
  
## <a name="in-this-section"></a><span data-ttu-id="1a871-111">このセクションの内容</span><span class="sxs-lookup"><span data-stu-id="1a871-111">In This Section</span></span>  
  
-   [<span data-ttu-id="1a871-112">ステップ 1: 通知を受信するためのオーケストレーション図形を追加する</span><span class="sxs-lookup"><span data-stu-id="1a871-112">Step 1: Add Orchestration Shapes to Receive Notification</span></span>](../../adapters-and-accelerators/adapter-sql/step-1-add-orchestration-shapes-to-receive-notification.md)  
  
-   [<span data-ttu-id="1a871-113">手順 2:通知メッセージから通知の種類を抽出する</span><span class="sxs-lookup"><span data-stu-id="1a871-113">Step 2: Extract Notification Type from Notification Message</span></span>](../../adapters-and-accelerators/adapter-sql/step-2-extract-notification-type-from-notification-message.md)  
  
-   [<span data-ttu-id="1a871-114">ステップ 3:挿入通知のフィルターを追加する</span><span class="sxs-lookup"><span data-stu-id="1a871-114">Step 3: Add a Filter for Insert Notifications</span></span>](../../adapters-and-accelerators/adapter-sql/step-3-add-a-filter-for-insert-notifications.md)