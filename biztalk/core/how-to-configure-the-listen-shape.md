---
title: 待ち受け図形を構成する方法 |Microsoft Docs
ms.custom: ''
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: ''
ms.suite: ''
ms.tgt_pltfrm: ''
ms.topic: article
helpviewer_keywords:
- Listen shape [Orchestration Designer], about Listen shape
- Listen shape [Orchestration Designer], configuring
- Listen shape [Orchestration Designer]
- Listen shape [Orchestration Designer], branching
- configuring [Orchestration Designer], Listen shapes
ms.assetid: 4765dc0a-a30e-4515-83bc-72b4f37268cf
caps.latest.revision: 6
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: 55a717c45e5c40b4022c38d2b668cae4c615f248
ms.sourcegitcommit: 381e83d43796a345488d54b3f7413e11d56ad7be
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 05/07/2019
ms.locfileid: "65386051"
---
# <a name="how-to-configure-the-listen-shape"></a><span data-ttu-id="72649-102">待ち受け図形を構成する方法</span><span class="sxs-lookup"><span data-stu-id="72649-102">How to Configure the Listen Shape</span></span>
<span data-ttu-id="72649-103">待ち受けアクションを使用するアプリケーションのいずれか 1 つまたは複数のポートでのいくつかのメッセージを待機する、または指定されたタイムアウト間隔、および結果に基づいて分岐の後に待機を停止します。</span><span class="sxs-lookup"><span data-stu-id="72649-103">Listen actions enable applications to wait for one of several messages on one or more ports, or to stop waiting after a specified time-out interval, and branch based upon the results.</span></span>  
  
 <span data-ttu-id="72649-104">![](../core/media/ebiz-orch-listen.gif "ebiz_orch_listen")</span><span class="sxs-lookup"><span data-stu-id="72649-104">![](../core/media/ebiz-orch-listen.gif "ebiz_orch_listen")</span></span>  
<span data-ttu-id="72649-105">待ち受け図形</span><span class="sxs-lookup"><span data-stu-id="72649-105">Listen shape</span></span>  
  
 <span data-ttu-id="72649-106">好きなように、多数の分岐を追加することができます。</span><span class="sxs-lookup"><span data-stu-id="72649-106">You can add as many branches as you like.</span></span> <span data-ttu-id="72649-107">初期の下の他の任意の図形を配置する**受信**または**遅延**図形。</span><span class="sxs-lookup"><span data-stu-id="72649-107">You can place any other shape below the initial **Receive** or **Delay** shape.</span></span>  
  
 <span data-ttu-id="72649-108">ライセンス認証を使用することがで受信を**リッスン**図形。</span><span class="sxs-lookup"><span data-stu-id="72649-108">It is possible to use an activation receive in a **Listen** shape.</span></span> <span data-ttu-id="72649-109">場合の 1 つの分岐、**リッスン**図形には、アクティブ化が含まれているすべての分岐を含める必要がありますが、表示されるライセンス認証を受信して、タイムアウトは使用できません。</span><span class="sxs-lookup"><span data-stu-id="72649-109">If one branch of the **Listen** shape contains an activation receive, then all branches must contain activation receives, and no timeout can be used.</span></span> <span data-ttu-id="72649-110">アクティブ化する必要がありますが表示される各分岐の最初のアクションがあります。</span><span class="sxs-lookup"><span data-stu-id="72649-110">The activation receive must be the first action in each branch.</span></span>  
  
 <span data-ttu-id="72649-111">使用することができます、**リッスン**の 1 つまたは複数のイベントの発生に基づいてオーケストレーション フローを分岐図形。</span><span class="sxs-lookup"><span data-stu-id="72649-111">You can use the **Listen** shape to branch orchestration flow based on the occurrence of one or more events.</span></span> <span data-ttu-id="72649-112">各分岐の最初の図形はいずれかである必要があります、**遅延**または**受信**図形。</span><span class="sxs-lookup"><span data-stu-id="72649-112">The first shape in each branch must be either a **Delay** or a **Receive** shape.</span></span> <span data-ttu-id="72649-113">その条件を満たす最初の分岐 — のタイムアウトの発生を**遅延**図形または受信確認のメッセージの**受信**図形 — が実行されます。</span><span class="sxs-lookup"><span data-stu-id="72649-113">The first branch that meets its condition—the occurrence of a time-out for a **Delay** shape or the receipt of a message for a **Receive** shape—will execute.</span></span> <span data-ttu-id="72649-114">必要な場合は、分岐を追加できます。</span><span class="sxs-lookup"><span data-stu-id="72649-114">You can add additional branches if needed.</span></span>  
  
### <a name="to-configure-a-listen-shape"></a><span data-ttu-id="72649-115">待ち受け図形を構成するには</span><span class="sxs-lookup"><span data-stu-id="72649-115">To configure a Listen shape</span></span>  
  
1.  <span data-ttu-id="72649-116">ブランチを選択します。</span><span class="sxs-lookup"><span data-stu-id="72649-116">Select a branch.</span></span>  
  
2.  <span data-ttu-id="72649-117">プロパティ ウィンドウで、指定、**分岐の種類**プロパティ。</span><span class="sxs-lookup"><span data-stu-id="72649-117">In the Properties window, specify the **Branch Type** property.</span></span>  
  
     <span data-ttu-id="72649-118">- または -</span><span class="sxs-lookup"><span data-stu-id="72649-118">—Or—</span></span>  
  
     <span data-ttu-id="72649-119">ドラッグ、**遅延**または**受信**図形を分岐にします。</span><span class="sxs-lookup"><span data-stu-id="72649-119">Drag a **Delay** or **Receive** shape onto the branch.</span></span>  
  
### <a name="to-add-a-branch-to-a-listen-shape"></a><span data-ttu-id="72649-120">待ち受け図形に分岐を追加するには</span><span class="sxs-lookup"><span data-stu-id="72649-120">To add a branch to a Listen shape</span></span>  
  
-   <span data-ttu-id="72649-121">右クリックし、**リッスン**図形をクリックして**新しい待ち受け分岐**します。</span><span class="sxs-lookup"><span data-stu-id="72649-121">Right-click the **Listen** shape and then click **New Listen Branch**.</span></span>  
  
    > [!NOTE]
    >  <span data-ttu-id="72649-122">分岐を削除する、**リッスン**図形を削除するをクリックする分岐を右クリックして**削除**します。</span><span class="sxs-lookup"><span data-stu-id="72649-122">To remove a branch from a **Listen** shape, right-click the branch you want to remove, and then click **Delete**.</span></span>