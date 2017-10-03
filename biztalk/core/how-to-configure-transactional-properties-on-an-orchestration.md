---
title: "オーケストレーションでのトランザクションのプロパティを構成する方法 |Microsoft ドキュメント"
ms.custom: 
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: 
ms.suite: 
ms.tgt_pltfrm: 
ms.topic: article
helpviewer_keywords:
- atomic transactions
- orchestrations, transactions
- transactions, long-running
- orchestrations, configuring
- transactions, atomic
ms.assetid: 8eec6019-4d96-4ed6-8a90-9403738d8af4
caps.latest.revision: "6"
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: 9164a9f5670a996a62450a19d802c97b89d8e242
ms.sourcegitcommit: cb908c540d8f1a692d01dc8f313e16cb4b4e696d
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 09/20/2017
---
# <a name="how-to-configure-transactional-properties-on-an-orchestration"></a><span data-ttu-id="bed46-102">オーケストレーションでのトランザクションのプロパティを構成する方法</span><span class="sxs-lookup"><span data-stu-id="bed46-102">How to Configure Transactional Properties on an Orchestration</span></span>
<span data-ttu-id="bed46-103">オーケストレーションは、アトミック トランザクション、長時間トランザクション、またはそのどちらでもないものとして扱うことができます。</span><span class="sxs-lookup"><span data-stu-id="bed46-103">An orchestration can be treated as an atomic transaction, a long-running transaction, or neither.</span></span>  
  
### <a name="to-make-your-orchestration-an-atomic-transaction"></a><span data-ttu-id="bed46-104">オーケストレーションをアトミック トランザクションにするには</span><span class="sxs-lookup"><span data-stu-id="bed46-104">To make your orchestration an atomic transaction</span></span>  
  
1.  <span data-ttu-id="bed46-105">オーケストレーションの種類 ウィンドウで、選択**オーケストレーションのプロパティ**です。</span><span class="sxs-lookup"><span data-stu-id="bed46-105">In the Orchestration View window, select **Orchestration Properties**.</span></span>  
  
2.  <span data-ttu-id="bed46-106">[プロパティ] ウィンドウで選択**Atomic**のドロップダウン リストで、**トランザクション タイプ**プロパティです。</span><span class="sxs-lookup"><span data-stu-id="bed46-106">In the Properties window, select **Atomic** in the drop-down for the **Transaction Type** property.</span></span>  
  
     <span data-ttu-id="bed46-107">**バッチ**、**補正**、**分離レベル**、**再試行**、**タイムアウト**、および**トランザクション識別子**任意のスコープの場合と同様に、[プロパティ] ウィンドウでプロパティとして表示されます。</span><span class="sxs-lookup"><span data-stu-id="bed46-107">**Batch**, **Compensation**, **Isolation Level**, **Retry**, **Timeout**, and **Transaction Identifier** appear as properties in the Properties window, just as they do for any scope.</span></span> <span data-ttu-id="bed46-108">これらのプロパティの詳細については、次を参照してください。[スコープ図形を構成する方法](../core/how-to-configure-the-scope-shape.md)です。</span><span class="sxs-lookup"><span data-stu-id="bed46-108">For more information on these properties, see [How to Configure the Scope Shape](../core/how-to-configure-the-scope-shape.md).</span></span>  
  
### <a name="to-make-your-orchestration-a-long-running-transaction"></a><span data-ttu-id="bed46-109">オーケストレーションを長時間トランザクションにするには</span><span class="sxs-lookup"><span data-stu-id="bed46-109">To make your orchestration a long-running transaction</span></span>  
  
1.  <span data-ttu-id="bed46-110">オーケストレーションの種類 ウィンドウで、選択**オーケストレーションのプロパティ**です。</span><span class="sxs-lookup"><span data-stu-id="bed46-110">In the Orchestration View window, select **Orchestration Properties**.</span></span>  
  
2.  <span data-ttu-id="bed46-111">[プロパティ] ウィンドウで選択**長時間**のドロップダウン リストで、**トランザクション タイプ**プロパティです。</span><span class="sxs-lookup"><span data-stu-id="bed46-111">In the Properties window, select **Long Running** in the drop-down for the **Transaction Type** property.</span></span>  
  
     <span data-ttu-id="bed46-112">**補正**、**タイムアウト**、および**トランザクション識別子**プロパティ ウィンドウでプロパティとして表示されます。</span><span class="sxs-lookup"><span data-stu-id="bed46-112">**Compensation**, **Timeout**, and **Transaction Identifier** appear as properties in the Properties window.</span></span> <span data-ttu-id="bed46-113">これらのプロパティは、スコープと同様です。</span><span class="sxs-lookup"><span data-stu-id="bed46-113">For more information on these properties, just as they do for any scope.</span></span> <span data-ttu-id="bed46-114">これらのプロパティの詳細については、次を参照してください。[スコープ図形を構成する方法](../core/how-to-configure-the-scope-shape.md)です。</span><span class="sxs-lookup"><span data-stu-id="bed46-114">For more information on these properties, see [How to Configure the Scope Shape](../core/how-to-configure-the-scope-shape.md).</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="bed46-115">参照</span><span class="sxs-lookup"><span data-stu-id="bed46-115">See Also</span></span>  
 [<span data-ttu-id="bed46-116">トランザクション オーケストレーションを行う</span><span class="sxs-lookup"><span data-stu-id="bed46-116">Making Orchestrations Transactional</span></span>](../core/making-orchestrations-transactional.md)