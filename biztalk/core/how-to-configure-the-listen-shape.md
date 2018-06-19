---
title: 待ち受け図形を構成する方法 |Microsoft ドキュメント
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
ms.openlocfilehash: 5bd8f8bbcc08d41430b95a9d177aeb06a5288be4
ms.sourcegitcommit: cb908c540d8f1a692d01dc8f313e16cb4b4e696d
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 09/20/2017
ms.locfileid: "22247898"
---
# <a name="how-to-configure-the-listen-shape"></a><span data-ttu-id="59377-102">待ち受け図形を構成する方法</span><span class="sxs-lookup"><span data-stu-id="59377-102">How to Configure the Listen Shape</span></span>
<span data-ttu-id="59377-103">アプリケーションは、待ち受けアクションを実行して、1 つ以上のポートで複数のメッセージの 1 つを待機するか、指定されたタイムアウト間隔後に待機を停止して、結果に基づいて分岐することができます。</span><span class="sxs-lookup"><span data-stu-id="59377-103">Listen actions enable applications to wait for one of several messages on one or more ports, or to stop waiting after a specified time-out interval, and branch based upon the results.</span></span>  
  
 ![](../core/media/ebiz-orch-listen.gif "ebiz_orch_listen")  
<span data-ttu-id="59377-104">待ち受け図形</span><span class="sxs-lookup"><span data-stu-id="59377-104">Listen shape</span></span>  
  
 <span data-ttu-id="59377-105">好きなように、多数の分岐を追加することができます。</span><span class="sxs-lookup"><span data-stu-id="59377-105">You can add as many branches as you like.</span></span> <span data-ttu-id="59377-106">初期の下の他の任意の図形を配置する**受信**または**遅延**図形です。</span><span class="sxs-lookup"><span data-stu-id="59377-106">You can place any other shape below the initial **Receive** or **Delay** shape.</span></span>  
  
 <span data-ttu-id="59377-107">アクティブ化を使用して行うことがで受信、**リッスン**図形です。</span><span class="sxs-lookup"><span data-stu-id="59377-107">It is possible to use an activation receive in a **Listen** shape.</span></span> <span data-ttu-id="59377-108">場合 1 つの分岐、**リッスン**図形にはアクティブ化が含まれていますが、すべての分岐を含める必要がありますのアクティブ化は、次の受信、およびタイムアウトは使用できません。</span><span class="sxs-lookup"><span data-stu-id="59377-108">If one branch of the **Listen** shape contains an activation receive, then all branches must contain activation receives, and no timeout can be used.</span></span> <span data-ttu-id="59377-109">アクティベーション受信は、各分岐の最初のアクションである必要があります。</span><span class="sxs-lookup"><span data-stu-id="59377-109">The activation receive must be the first action in each branch.</span></span>  
  
 <span data-ttu-id="59377-110">使用することができます、**リッスン**1 つまたは複数のイベントの発生に基づいてオーケストレーション フローの分岐に図形です。</span><span class="sxs-lookup"><span data-stu-id="59377-110">You can use the **Listen** shape to branch orchestration flow based on the occurrence of one or more events.</span></span> <span data-ttu-id="59377-111">各分岐の最初の図形はいずれかである必要があります、**遅延**または**受信**図形です。</span><span class="sxs-lookup"><span data-stu-id="59377-111">The first shape in each branch must be either a **Delay** or a **Receive** shape.</span></span> <span data-ttu-id="59377-112">その条件を満たす最初の分岐 — のタイムアウトの発生、**遅延**または図形のメッセージの受信、**受信**図形 — が実行されます。</span><span class="sxs-lookup"><span data-stu-id="59377-112">The first branch that meets its condition—the occurrence of a time-out for a **Delay** shape or the receipt of a message for a **Receive** shape—will execute.</span></span> <span data-ttu-id="59377-113">必要に応じて分岐を追加できます。</span><span class="sxs-lookup"><span data-stu-id="59377-113">You can add additional branches if needed.</span></span>  
  
### <a name="to-configure-a-listen-shape"></a><span data-ttu-id="59377-114">待ち受け図形を構成するには</span><span class="sxs-lookup"><span data-stu-id="59377-114">To configure a Listen shape</span></span>  
  
1.  <span data-ttu-id="59377-115">分岐を選択します。</span><span class="sxs-lookup"><span data-stu-id="59377-115">Select a branch.</span></span>  
  
2.  <span data-ttu-id="59377-116">[プロパティ] ウィンドウで指定、**分岐の種類**プロパティです。</span><span class="sxs-lookup"><span data-stu-id="59377-116">In the Properties window, specify the **Branch Type** property.</span></span>  
  
     <span data-ttu-id="59377-117">- または -</span><span class="sxs-lookup"><span data-stu-id="59377-117">—Or—</span></span>  
  
     <span data-ttu-id="59377-118">ドラッグ、**遅延**または**受信**図形に分岐します。</span><span class="sxs-lookup"><span data-stu-id="59377-118">Drag a **Delay** or **Receive** shape onto the branch.</span></span>  
  
### <a name="to-add-a-branch-to-a-listen-shape"></a><span data-ttu-id="59377-119">待ち受け図形に分岐を追加するには</span><span class="sxs-lookup"><span data-stu-id="59377-119">To add a branch to a Listen shape</span></span>  
  
-   <span data-ttu-id="59377-120">右クリックし、**リッスン**図形をクリックして**新しい待ち受け分岐**です。</span><span class="sxs-lookup"><span data-stu-id="59377-120">Right-click the **Listen** shape and then click **New Listen Branch**.</span></span>  
  
    > [!NOTE]
    >  <span data-ttu-id="59377-121">分岐を削除する、**リッスン**図形をクリックして、削除する分岐を右クリックして**削除**です。</span><span class="sxs-lookup"><span data-stu-id="59377-121">To remove a branch from a **Listen** shape, right-click the branch you want to remove, and then click **Delete**.</span></span>