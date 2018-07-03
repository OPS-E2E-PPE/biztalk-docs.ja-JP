---
title: '手順 2: 作成、Orchestration1 |Microsoft Docs'
ms.custom: ''
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: ''
ms.suite: ''
ms.tgt_pltfrm: ''
ms.topic: article
ms.assetid: a88cafbb-3b6f-4d27-8516-79a2391b4e31
caps.latest.revision: 7
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: 9802b7c75b704ec34c399df8ecc432ed22d342e9
ms.sourcegitcommit: 266308ec5c6a9d8d80ff298ee6051b4843c5d626
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 06/27/2018
ms.locfileid: "36982211"
---
# <a name="step-2-create-the-orchestration"></a><span data-ttu-id="90dd4-102">手順 2: オーケストレーションを作成します。</span><span class="sxs-lookup"><span data-stu-id="90dd4-102">Step 2: Create the Orchestration</span></span>
<span data-ttu-id="90dd4-103">次に示すオーケストレーションのセットアップには、BeginDocTest という名前のプロジェクトを使用します。</span><span class="sxs-lookup"><span data-stu-id="90dd4-103">The orchestration setup is as follows using a project called BeginDocTest:</span></span>  
  
- <span data-ttu-id="90dd4-104">[ポート]</span><span class="sxs-lookup"><span data-stu-id="90dd4-104">Ports</span></span>  
  
- <span data-ttu-id="90dd4-105">メッセージ</span><span class="sxs-lookup"><span data-stu-id="90dd4-105">Messages</span></span>  
  
- <span data-ttu-id="90dd4-106">送受信</span><span class="sxs-lookup"><span data-stu-id="90dd4-106">Send and Receive</span></span>  
  
- <span data-ttu-id="90dd4-107">メッセージの構築</span><span class="sxs-lookup"><span data-stu-id="90dd4-107">Construct Message</span></span>  
  
- <span data-ttu-id="90dd4-108">変換</span><span class="sxs-lookup"><span data-stu-id="90dd4-108">Transforms</span></span>  
  
  <span data-ttu-id="90dd4-109">オーケストレーションは、例外処理を行いません。</span><span class="sxs-lookup"><span data-stu-id="90dd4-109">The orchestration does not do any exception handling.</span></span> <span data-ttu-id="90dd4-110">J. D.</span><span class="sxs-lookup"><span data-stu-id="90dd4-110">J.D.</span></span> <span data-ttu-id="90dd4-111">Edwards OneWorld では、BeginDoc およびロールバックは、接続がタイムアウトした場合、暗黙のトランザクション内の後続の操作を実行します。BizTalk オーケストレーションが j. d. の変更をロールバックすることが何もする必要はありませんので</span><span class="sxs-lookup"><span data-stu-id="90dd4-111">Edwards OneWorld performs the BeginDoc and subsequent operations within an implicit transaction that it will rollback if the connection times out. The BizTalk orchestration thus does not need to do anything to rollback changes J.D.</span></span> <span data-ttu-id="90dd4-112">Edwards OneWorld は、します。</span><span class="sxs-lookup"><span data-stu-id="90dd4-112">Edwards OneWorld makes.</span></span> <span data-ttu-id="90dd4-113">ただし、タイムアウトになった場合、BizTalk オーケストレーションで例外が発生します。</span><span class="sxs-lookup"><span data-stu-id="90dd4-113">However, a time out will cause an exception in the BizTalk orchestration.</span></span> <span data-ttu-id="90dd4-114">例外は、BizTalk によってイベント ログに記録されます。</span><span class="sxs-lookup"><span data-stu-id="90dd4-114">BizTalk will record the exception in the event log.</span></span> <span data-ttu-id="90dd4-115">オーケストレーションに例外処理を追加する場合、Microsoft BizTalk Server ヘルプの「例外のキャッチ ブロックを追加する方法」および「補正ブロックを追加する方法」を参照してください。</span><span class="sxs-lookup"><span data-stu-id="90dd4-115">If you want to add exception handling to the orchestration, see "How to Add a Catch Exception Block" and "How to Add a Compensation Block" in the Microsoft BizTalk Server Help.</span></span>  
  
## <a name="in-this-section"></a><span data-ttu-id="90dd4-116">このセクションの内容</span><span class="sxs-lookup"><span data-stu-id="90dd4-116">In This Section</span></span>  
  
-   [<span data-ttu-id="90dd4-117">タスク 1: ポートの作成</span><span class="sxs-lookup"><span data-stu-id="90dd4-117">Task 1: Create the Ports</span></span>](../core/task-1-create-the-ports2.md)  
  
-   [<span data-ttu-id="90dd4-118">タスク 2: メッセージの作成</span><span class="sxs-lookup"><span data-stu-id="90dd4-118">Task 2: Create the Messages</span></span>](../core/task-2-create-the-messages1.md)  
  
-   [<span data-ttu-id="90dd4-119">タスク 3: 受信図形と送信図形の構成</span><span class="sxs-lookup"><span data-stu-id="90dd4-119">Task 3: Configure the Send and Receive Shapes</span></span>](../core/task-3-configure-the-send-and-receive-shapes1.md)  
  
-   [<span data-ttu-id="90dd4-120">タスク 4: メッセージの構築図形の構成</span><span class="sxs-lookup"><span data-stu-id="90dd4-120">Task 4: Configure the Construct Message Shape</span></span>](../core/task-4-configure-the-construct-message-shape2.md)  
  
-   [<span data-ttu-id="90dd4-121">タスク 5: 変換図形の構成</span><span class="sxs-lookup"><span data-stu-id="90dd4-121">Task 5: Configure the Transform Shape</span></span>](../core/task-5-configure-the-transform-shape1.md)