---
title: 補正ブロックを追加する方法 |Microsoft Docs
ms.custom: ''
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: ''
ms.suite: ''
ms.tgt_pltfrm: ''
ms.topic: article
helpviewer_keywords:
- compensations, compensation blocks
- compensation blocks, adding
ms.assetid: 1bdeed92-3144-44ef-ad0d-1c6976f46a36
caps.latest.revision: 3
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: 1ef3cce71a85b41ccfc4291f82c5736d77f15162
ms.sourcegitcommit: 381e83d43796a345488d54b3f7413e11d56ad7be
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 05/07/2019
ms.locfileid: "65343866"
---
# <a name="how-to-add-a-compensation-block"></a><span data-ttu-id="ca8c0-102">補正ブロックを追加する方法</span><span class="sxs-lookup"><span data-stu-id="ca8c0-102">How to Add a Compensation Block</span></span>
<span data-ttu-id="ca8c0-103">独自の補正を追加しない場合、ランタイム エンジンは、現在のトランザクション内で入れ子になったトランザクションの補正を呼び出す既定の補正を実行します。</span><span class="sxs-lookup"><span data-stu-id="ca8c0-103">If you do not add your own compensation, the runtime engine performs a default compensation that invokes the compensations of any nested transactions within the current transaction.</span></span> <span data-ttu-id="ca8c0-104">まず、最近完了したトランザクションの補正が呼び出さし、すべての入れ子になったトランザクションが補正されてまで順番します。</span><span class="sxs-lookup"><span data-stu-id="ca8c0-104">It first invokes the compensation of the most recently completed transaction, and works backward until all nested transactions have been compensated.</span></span>  
  
 <span data-ttu-id="ca8c0-105">これは true を保持すると、補正が行われるループ図形内部の: 補正を逆の順序で実行されます。</span><span class="sxs-lookup"><span data-stu-id="ca8c0-105">This holds true even when your compensation takes place inside a Loop shape: the compensations will be run in reverse order.</span></span> <span data-ttu-id="ca8c0-106">最初に、ループの最後の反復の補正が呼び出される、し、前のイテレーションの補正します。</span><span class="sxs-lookup"><span data-stu-id="ca8c0-106">First, the compensation for the last iteration of the loop will be invoked, then the compensation for the previous iteration, and so on.</span></span>  
  
> [!CAUTION]
>  <span data-ttu-id="ca8c0-107">作業を補正の物理メモリにデータが永続化するためには、大きな反復数を指定します。 問題がありますパフォーマンスに影響ループ内で補正を使用して可能性があります。</span><span class="sxs-lookup"><span data-stu-id="ca8c0-107">Because data is persisted to physical memory for compensation to work, using compensations inside a loop might affect performance, which might be an issue given a large number of iterations.</span></span>  
  
 <span data-ttu-id="ca8c0-108">既定の順序が、要件が収まらない場合を明示的に指定した順序で入れ子になったスコープの補正ハンドラーを呼び出す独自の補正ハンドラーを記述できます。</span><span class="sxs-lookup"><span data-stu-id="ca8c0-108">If the default ordering does not fit your requirements, you can write your own compensation handler to explicitly call the compensation handlers of the nested scopes in the order you specify.</span></span>  
  
### <a name="to-add-a-compensation-block"></a><span data-ttu-id="ca8c0-109">補正ブロックを追加するには</span><span class="sxs-lookup"><span data-stu-id="ca8c0-109">To add a Compensation Block</span></span>  
  
1.  <span data-ttu-id="ca8c0-110">右クリックし、**スコープ**図形を追加するトランザクションを**補正ブロック**、 をクリックし、**新しい補正ブロック**します。</span><span class="sxs-lookup"><span data-stu-id="ca8c0-110">Right-click the **Scope** shape for the transaction to which you want to add a **Compensation Block**, and then click **New Compensation Block**.</span></span>  
  
    > [!NOTE]
    >  <span data-ttu-id="ca8c0-111">追加する、**補正ブロック**を**スコープ**図形、**トランザクションの種類**のプロパティ、**スコープ**に図形を設定する必要があります**アトミック**または**実行時間が長い**します。</span><span class="sxs-lookup"><span data-stu-id="ca8c0-111">To add a **Compensation Block** to a **Scope** shape, the **Transaction Type** property of the **Scope** shape must be set to **Atomic** or **Long Running**.</span></span>  
  
     <span data-ttu-id="ca8c0-112">A**補正ブロック**が関連付けられている直後のオーケストレーションに追加**スコープ**図形。</span><span class="sxs-lookup"><span data-stu-id="ca8c0-112">A **Compensation Block** is added to the orchestration immediately following the associated **Scope** shape.</span></span>  
  
2.  <span data-ttu-id="ca8c0-113">内で、**補正ブロック**図形をトランザクションのコミットを元に戻すためのプロセスを作成する図形を追加します。</span><span class="sxs-lookup"><span data-stu-id="ca8c0-113">Inside the **Compensation Block** shape, add shapes to create the process for undoing a committed transaction.</span></span>