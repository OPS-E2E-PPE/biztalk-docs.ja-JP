---
title: 並列アクション図形を構成する方法 |Microsoft Docs
ms.custom: ''
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: ''
ms.suite: ''
ms.tgt_pltfrm: ''
ms.topic: article
helpviewer_keywords:
- Parallel Actions shape [Orchestration Designer], Terminate shape [Orchestration Designer]
- Parallel Actions shape [Orchestration Designer], synchronizing data access
- Parallel Actions shape [Orchestration Designer]
- configuring [Orchestration Designer], Parallel Actions shapes
- Parallel Actions shape [Orchestration Designer], branching
- Parallel Actions shape [Orchestration Designer], about Parallel Actions shape
- Terminate shape [Orchestration Designer], Parallel Actions shape [Orchestration Designer]
- Parallel Actions shape [Orchestration Designer], configuring
ms.assetid: 396d6182-f5dd-4aab-9edc-92efe236fd3e
caps.latest.revision: 5
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: f3179995031ea91243f602d554808c198863f2c9
ms.sourcegitcommit: 381e83d43796a345488d54b3f7413e11d56ad7be
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 05/07/2019
ms.locfileid: "65386018"
---
# <a name="how-to-configure-the-parallel-actions-shape"></a><span data-ttu-id="d92a1-102">並列アクション図形を構成する方法</span><span class="sxs-lookup"><span data-stu-id="d92a1-102">How to Configure the Parallel Actions Shape</span></span>
<span data-ttu-id="d92a1-103">![](../core/media/ebiz-orch-paralactions.gif "ebiz_orch_paralactions")</span><span class="sxs-lookup"><span data-stu-id="d92a1-103">![](../core/media/ebiz-orch-paralactions.gif "ebiz_orch_paralactions")</span></span>  
<span data-ttu-id="d92a1-104">並列アクション図形</span><span class="sxs-lookup"><span data-stu-id="d92a1-104">Parallel Actions shape</span></span>  
  
> [!CAUTION]
>  <span data-ttu-id="d92a1-105">配置した場合、 **Terminate**図形内、**並列アクション**形状、および分岐を**Terminate**で実行されて、インスタンスが、すぐに完了に関係なくかどうか他の分岐の実行が完了します。</span><span class="sxs-lookup"><span data-stu-id="d92a1-105">If you place a **Terminate** shape inside a **Parallel Actions** shape, and the branch with the **Terminate** on it is run, the instance completes immediately, regardless of whether other branches have finished running.</span></span> <span data-ttu-id="d92a1-106">設計によって結果予測できないここでします。</span><span class="sxs-lookup"><span data-stu-id="d92a1-106">Depending on your design, results might be unpredictable in this case.</span></span>  
  
## <a name="synchronization-of-data-access"></a><span data-ttu-id="d92a1-107">データ アクセスの同期</span><span class="sxs-lookup"><span data-stu-id="d92a1-107">Synchronization of data access</span></span>  
 <span data-ttu-id="d92a1-108">その 1 つ以上のブランチの**並列アクション**図形は、同じデータにアクセスしようとしています。</span><span class="sxs-lookup"><span data-stu-id="d92a1-108">It is possible that more than one branch of a **Parallel Actions** shape will attempt to access the same data.</span></span> <span data-ttu-id="d92a1-109">エラーを回避するには、同期スコープ内のデータにアクセスするすべての図形を配置します。</span><span class="sxs-lookup"><span data-stu-id="d92a1-109">To avoid errors, place any shapes that access the data inside synchronized scopes.</span></span> <span data-ttu-id="d92a1-110">プロパティで指定することができます、**スコープ**同期または同期されていない、という図形。</span><span class="sxs-lookup"><span data-stu-id="d92a1-110">You can specify in the properties of a **Scope** shape that it is synchronized or not synchronized.</span></span> <span data-ttu-id="d92a1-111">詳細については、次を参照してください。[スコープ](../core/scopes.md)します。</span><span class="sxs-lookup"><span data-stu-id="d92a1-111">For more information, see [Scopes](../core/scopes.md).</span></span>  
  
#### <a name="to-add-a-branch-to-a-parallel-actions-shape"></a><span data-ttu-id="d92a1-112">並列アクション図形に分岐を追加するには</span><span class="sxs-lookup"><span data-stu-id="d92a1-112">To add a branch to a Parallel Actions shape</span></span>  
  
1.  <span data-ttu-id="d92a1-113">右クリックし、**並列アクション**図形をクリックして**新しい並列分岐**します。</span><span class="sxs-lookup"><span data-stu-id="d92a1-113">Right-click the **Parallel Actions** shape, and then click **New Parallel Branch**.</span></span>  
  
     <span data-ttu-id="d92a1-114">- または -</span><span class="sxs-lookup"><span data-stu-id="d92a1-114">—Or—</span></span>  
  
2.  <span data-ttu-id="d92a1-115">既存の 2 つの分岐の間には、新しい図形をドラッグします。</span><span class="sxs-lookup"><span data-stu-id="d92a1-115">Drag a new shape between two existing branches.</span></span>  
  
> [!NOTE]
>  <span data-ttu-id="d92a1-116">分岐を削除する、**並列アクション**図形を削除するをクリックする分岐を右クリックして**削除**します。</span><span class="sxs-lookup"><span data-stu-id="d92a1-116">To remove a branch from a **Parallel Actions** shape, right-click the branch you want to remove, and then click **Delete**.</span></span>