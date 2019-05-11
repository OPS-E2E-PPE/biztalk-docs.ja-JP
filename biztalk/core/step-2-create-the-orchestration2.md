---
title: 手順 2:作成、Orchestration2 |Microsoft Docs
ms.custom: ''
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: ''
ms.suite: ''
ms.tgt_pltfrm: ''
ms.topic: article
ms.assetid: 08d65525-77a9-4be2-a509-40ea60fa7401
caps.latest.revision: 6
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: 2510505e52b336a41578834bbd71d69ede6621c9
ms.sourcegitcommit: 381e83d43796a345488d54b3f7413e11d56ad7be
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 05/07/2019
ms.locfileid: "65392736"
---
# <a name="step-2-create-the-orchestration"></a><span data-ttu-id="c16dd-102">手順 2:オーケストレーションを作成します。</span><span class="sxs-lookup"><span data-stu-id="c16dd-102">Step 2: Create the Orchestration</span></span>
<span data-ttu-id="c16dd-103">オーケストレーションのセットアップは、BeginDocTest というプロジェクトを使用して次のようには。</span><span class="sxs-lookup"><span data-stu-id="c16dd-103">The orchestration setup is as follows using a project called BeginDocTest:</span></span>  
  
 <span data-ttu-id="c16dd-104">• ポート</span><span class="sxs-lookup"><span data-stu-id="c16dd-104">• Ports</span></span>  
  
 <span data-ttu-id="c16dd-105">• メッセージ</span><span class="sxs-lookup"><span data-stu-id="c16dd-105">• Messages</span></span>  
  
 <span data-ttu-id="c16dd-106">• 送受信</span><span class="sxs-lookup"><span data-stu-id="c16dd-106">• Send and Receive</span></span>  
  
 <span data-ttu-id="c16dd-107">• メッセージの構築</span><span class="sxs-lookup"><span data-stu-id="c16dd-107">• Construct Message</span></span>  
  
 <span data-ttu-id="c16dd-108">• 変換</span><span class="sxs-lookup"><span data-stu-id="c16dd-108">• Transforms</span></span>  
  
 <span data-ttu-id="c16dd-109">オーケストレーションは、例外処理を行いません。</span><span class="sxs-lookup"><span data-stu-id="c16dd-109">The orchestration does not do any exception handling.</span></span> <span data-ttu-id="c16dd-110">J. D.</span><span class="sxs-lookup"><span data-stu-id="c16dd-110">J.D.</span></span> <span data-ttu-id="c16dd-111">Edwards EnterpriseOne では、BeginDoc およびロールバックは、接続がタイムアウトした場合、暗黙のトランザクション内の後続の操作を実行します。BizTalk オーケストレーションが j. d. の変更をロールバックすることが何もする必要はありませんので</span><span class="sxs-lookup"><span data-stu-id="c16dd-111">Edwards EnterpriseOne performs the BeginDoc and subsequent operations within an implicit transaction that it will rollback if the connection times out. The BizTalk orchestration thus does not need to do anything to rollback changes J.D.</span></span> <span data-ttu-id="c16dd-112">Edwards EnterpriseOne は、します。</span><span class="sxs-lookup"><span data-stu-id="c16dd-112">Edwards EnterpriseOne makes.</span></span> <span data-ttu-id="c16dd-113">ただし、タイムアウトでは、BizTalk オーケストレーションで例外が発生します。</span><span class="sxs-lookup"><span data-stu-id="c16dd-113">However, a time out will cause an exception in the BizTalk orchestration.</span></span> <span data-ttu-id="c16dd-114">BizTalk は、例外をイベント ログに記録されます。</span><span class="sxs-lookup"><span data-stu-id="c16dd-114">BizTalk will record the exception in the event log.</span></span> <span data-ttu-id="c16dd-115">例外処理オーケストレーションを追加する場合は、「方法を追加、例外のキャッチ ブロック」と「方法に補正ブロックを追加」で、Microsoft BizTalk 2006 メイン ヘルプを参照してください。</span><span class="sxs-lookup"><span data-stu-id="c16dd-115">If you want to add exception handling to the orchestration, see "How to Add a Catch Exception Block" and "How to Add a Compensation Block" in the Microsoft BizTalk 2006 main help.</span></span>  
  
## <a name="in-this-section"></a><span data-ttu-id="c16dd-116">このセクションの内容</span><span class="sxs-lookup"><span data-stu-id="c16dd-116">In This Section</span></span>  
  
-   [<span data-ttu-id="c16dd-117">タスク 1:ポートを作成します。</span><span class="sxs-lookup"><span data-stu-id="c16dd-117">Task 1: Create the Ports</span></span>](../core/task-1-create-the-ports1.md)  
  
-   [<span data-ttu-id="c16dd-118">タスク 2:メッセージを作成します。</span><span class="sxs-lookup"><span data-stu-id="c16dd-118">Task 2: Create the Messages</span></span>](../core/task-2-create-the-messages2.md)  
  
-   [<span data-ttu-id="c16dd-119">タスク 3:受信図形と送信の構成</span><span class="sxs-lookup"><span data-stu-id="c16dd-119">Task 3: Configure the Send and Receive Shapes</span></span>](../core/task-3-configure-the-send-and-receive-shapes2.md)  
  
-   [<span data-ttu-id="c16dd-120">タスク 4:メッセージの構築図形を構成します。</span><span class="sxs-lookup"><span data-stu-id="c16dd-120">Task 4: Configure the Construct Message Shape</span></span>](../core/task-4-configure-the-construct-message-shape1.md)  
  
-   [<span data-ttu-id="c16dd-121">タスク 5:変換図形を構成します。</span><span class="sxs-lookup"><span data-stu-id="c16dd-121">Task 5: Configure the Transform Shape</span></span>](../core/task-5-configure-the-transform-shape2.md)