---
title: オーケストレーションでのトランザクションのプロパティを構成する方法 |Microsoft Docs
ms.custom: ''
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: ''
ms.suite: ''
ms.tgt_pltfrm: ''
ms.topic: article
helpviewer_keywords:
- atomic transactions
- orchestrations, transactions
- transactions, long-running
- orchestrations, configuring
- transactions, atomic
ms.assetid: 8eec6019-4d96-4ed6-8a90-9403738d8af4
caps.latest.revision: 6
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: c999ca7c487cdcf59fd29e76b3d466194aa8ee21
ms.sourcegitcommit: 381e83d43796a345488d54b3f7413e11d56ad7be
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 05/07/2019
ms.locfileid: "65385782"
---
# <a name="how-to-configure-transactional-properties-on-an-orchestration"></a><span data-ttu-id="038db-102">オーケストレーションでのトランザクションのプロパティを構成する方法</span><span class="sxs-lookup"><span data-stu-id="038db-102">How to Configure Transactional Properties on an Orchestration</span></span>
<span data-ttu-id="038db-103">オーケストレーションは、アトミック トランザクション、実行時間の長いトランザクションの場合、またはそのどちらもとして扱うことができます。</span><span class="sxs-lookup"><span data-stu-id="038db-103">An orchestration can be treated as an atomic transaction, a long-running transaction, or neither.</span></span>  
  
### <a name="to-make-your-orchestration-an-atomic-transaction"></a><span data-ttu-id="038db-104">オーケストレーションのアトミックのトランザクションを作成するには</span><span class="sxs-lookup"><span data-stu-id="038db-104">To make your orchestration an atomic transaction</span></span>  
  
1.  <span data-ttu-id="038db-105">オーケストレーションの種類 ウィンドウで次のように選択します。**オーケストレーションのプロパティ**します。</span><span class="sxs-lookup"><span data-stu-id="038db-105">In the Orchestration View window, select **Orchestration Properties**.</span></span>  
  
2.  <span data-ttu-id="038db-106">[プロパティ] ウィンドウで次のように選択します。**アトミック**のドロップダウン リストで、**トランザクション タイプ**プロパティ。</span><span class="sxs-lookup"><span data-stu-id="038db-106">In the Properties window, select **Atomic** in the drop-down for the **Transaction Type** property.</span></span>  
  
     <span data-ttu-id="038db-107">**バッチ**、**補正**、**分離レベル**、**再試行**、**タイムアウト**、および**トランザクション識別子**の任意のスコープと同じように、[プロパティ] ウィンドウでプロパティとして表示されます。</span><span class="sxs-lookup"><span data-stu-id="038db-107">**Batch**, **Compensation**, **Isolation Level**, **Retry**, **Timeout**, and **Transaction Identifier** appear as properties in the Properties window, just as they do for any scope.</span></span> <span data-ttu-id="038db-108">これらのプロパティの詳細については、次を参照してください。[スコープ図形を構成する方法](../core/how-to-configure-the-scope-shape.md)します。</span><span class="sxs-lookup"><span data-stu-id="038db-108">For more information on these properties, see [How to Configure the Scope Shape](../core/how-to-configure-the-scope-shape.md).</span></span>  
  
### <a name="to-make-your-orchestration-a-long-running-transaction"></a><span data-ttu-id="038db-109">オーケストレーションの実行時間の長いトランザクションを作成するには</span><span class="sxs-lookup"><span data-stu-id="038db-109">To make your orchestration a long-running transaction</span></span>  
  
1.  <span data-ttu-id="038db-110">オーケストレーションの種類 ウィンドウで次のように選択します。**オーケストレーションのプロパティ**します。</span><span class="sxs-lookup"><span data-stu-id="038db-110">In the Orchestration View window, select **Orchestration Properties**.</span></span>  
  
2.  <span data-ttu-id="038db-111">[プロパティ] ウィンドウで次のように選択します。**長時間**のドロップダウン リストで、**トランザクション タイプ**プロパティ。</span><span class="sxs-lookup"><span data-stu-id="038db-111">In the Properties window, select **Long Running** in the drop-down for the **Transaction Type** property.</span></span>  
  
     <span data-ttu-id="038db-112">**補正**、**タイムアウト**、および**トランザクション識別子**プロパティ ウィンドウでプロパティとして表示されます。</span><span class="sxs-lookup"><span data-stu-id="038db-112">**Compensation**, **Timeout**, and **Transaction Identifier** appear as properties in the Properties window.</span></span> <span data-ttu-id="038db-113">詳細について、これらのプロパティの任意のスコープと同様です。</span><span class="sxs-lookup"><span data-stu-id="038db-113">For more information on these properties, just as they do for any scope.</span></span> <span data-ttu-id="038db-114">これらのプロパティの詳細については、次を参照してください。[スコープ図形を構成する方法](../core/how-to-configure-the-scope-shape.md)します。</span><span class="sxs-lookup"><span data-stu-id="038db-114">For more information on these properties, see [How to Configure the Scope Shape](../core/how-to-configure-the-scope-shape.md).</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="038db-115">参照</span><span class="sxs-lookup"><span data-stu-id="038db-115">See Also</span></span>  
 [<span data-ttu-id="038db-116">オーケストレーションのトランザクション化</span><span class="sxs-lookup"><span data-stu-id="038db-116">Making Orchestrations Transactional</span></span>](../core/making-orchestrations-transactional.md)