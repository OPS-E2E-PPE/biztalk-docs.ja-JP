---
title: "並列アクション図形を構成する方法 |Microsoft ドキュメント"
ms.custom: 
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: 
ms.suite: 
ms.tgt_pltfrm: 
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
caps.latest.revision: "5"
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: 125d479a09eefb6771a884d2cddbfa98f34aeb36
ms.sourcegitcommit: cb908c540d8f1a692d01dc8f313e16cb4b4e696d
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 09/20/2017
---
# <a name="how-to-configure-the-parallel-actions-shape"></a><span data-ttu-id="110e3-102">並列アクション図形を構成する方法</span><span class="sxs-lookup"><span data-stu-id="110e3-102">How to Configure the Parallel Actions Shape</span></span>
![](../core/media/ebiz-orch-paralactions.gif "ebiz_orch_paralactions")  
<span data-ttu-id="110e3-103">並列アクション図形</span><span class="sxs-lookup"><span data-stu-id="110e3-103">Parallel Actions shape</span></span>  
  
> [!CAUTION]
>  <span data-ttu-id="110e3-104">配置した場合、 **Terminate**図形内、**並列アクション**図形とで、分岐、 **Terminate**では、実行、インスタンスが、すぐに完了に関係なくかどうか、他の分岐の実行が完了します。</span><span class="sxs-lookup"><span data-stu-id="110e3-104">If you place a **Terminate** shape inside a **Parallel Actions** shape, and the branch with the **Terminate** on it is run, the instance completes immediately, regardless of whether other branches have finished running.</span></span> <span data-ttu-id="110e3-105">デザイン方法によっては、この場合の結果が予測できないものになる可能性があります。</span><span class="sxs-lookup"><span data-stu-id="110e3-105">Depending on your design, results might be unpredictable in this case.</span></span>  
  
## <a name="synchronization-of-data-access"></a><span data-ttu-id="110e3-106">データ アクセスの同期</span><span class="sxs-lookup"><span data-stu-id="110e3-106">Synchronization of data access</span></span>  
 <span data-ttu-id="110e3-107">可能であればその複数の 1 つの分岐、**並列アクション**図形は、同じデータにアクセスしようとしています。</span><span class="sxs-lookup"><span data-stu-id="110e3-107">It is possible that more than one branch of a **Parallel Actions** shape will attempt to access the same data.</span></span> <span data-ttu-id="110e3-108">エラーを回避するため、データにアクセスする図形を同期スコープ内に配置します。</span><span class="sxs-lookup"><span data-stu-id="110e3-108">To avoid errors, place any shapes that access the data inside synchronized scopes.</span></span> <span data-ttu-id="110e3-109">プロパティで指定できます、**スコープ**図形ことが同期されているまたは同期されていません。</span><span class="sxs-lookup"><span data-stu-id="110e3-109">You can specify in the properties of a **Scope** shape that it is synchronized or not synchronized.</span></span> <span data-ttu-id="110e3-110">詳細については、次を参照してください。[スコープ](../core/scopes.md)です。</span><span class="sxs-lookup"><span data-stu-id="110e3-110">For more information, see [Scopes](../core/scopes.md).</span></span>  
  
#### <a name="to-add-a-branch-to-a-parallel-actions-shape"></a><span data-ttu-id="110e3-111">並列アクション図形に分岐を追加するには</span><span class="sxs-lookup"><span data-stu-id="110e3-111">To add a branch to a Parallel Actions shape</span></span>  
  
1.  <span data-ttu-id="110e3-112">右クリックし、**並列アクション**図形をクリックして**新しい並列分岐**です。</span><span class="sxs-lookup"><span data-stu-id="110e3-112">Right-click the **Parallel Actions** shape, and then click **New Parallel Branch**.</span></span>  
  
     <span data-ttu-id="110e3-113">- または -</span><span class="sxs-lookup"><span data-stu-id="110e3-113">—Or—</span></span>  
  
2.  <span data-ttu-id="110e3-114">新しい図形を既存の 2 つの分岐の間にドラッグします。</span><span class="sxs-lookup"><span data-stu-id="110e3-114">Drag a new shape between two existing branches.</span></span>  
  
> [!NOTE]
>  <span data-ttu-id="110e3-115">分岐を削除する、**並列アクション**図形をクリックして、削除する分岐を右クリックして**削除**です。</span><span class="sxs-lookup"><span data-stu-id="110e3-115">To remove a branch from a **Parallel Actions** shape, right-click the branch you want to remove, and then click **Delete**.</span></span>