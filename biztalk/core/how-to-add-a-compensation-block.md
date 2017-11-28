---
title: "補正ブロックを追加する方法 |Microsoft ドキュメント"
ms.custom: 
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: 
ms.suite: 
ms.tgt_pltfrm: 
ms.topic: article
helpviewer_keywords:
- compensations, compensation blocks
- compensation blocks, adding
ms.assetid: 1bdeed92-3144-44ef-ad0d-1c6976f46a36
caps.latest.revision: "3"
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: a2dec4f4dd01c2bbf522dfff44ec8aaf0c2f5e89
ms.sourcegitcommit: cb908c540d8f1a692d01dc8f313e16cb4b4e696d
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 09/20/2017
---
# <a name="how-to-add-a-compensation-block"></a><span data-ttu-id="f6f2a-102">補正ブロックを追加する方法</span><span class="sxs-lookup"><span data-stu-id="f6f2a-102">How to Add a Compensation Block</span></span>
<span data-ttu-id="f6f2a-103">独自の補正コードを追加しなければ、ランタイム エンジンにより、現在のトランザクション内に入れ子にされたトランザクションの補正を呼び出す既定の補正が実行されます。</span><span class="sxs-lookup"><span data-stu-id="f6f2a-103">If you do not add your own compensation, the runtime engine performs a default compensation that invokes the compensations of any nested transactions within the current transaction.</span></span> <span data-ttu-id="f6f2a-104">最初に最近完了したトランザクションの補正が呼び出され、すべての入れ子になったトランザクションが完了するまで、古いものへ順番に処理されます。</span><span class="sxs-lookup"><span data-stu-id="f6f2a-104">It first invokes the compensation of the most recently completed transaction, and works backward until all nested transactions have been compensated.</span></span>  
  
 <span data-ttu-id="f6f2a-105">これは true を保持すると、補正が行われるループ図形内部の: 補正は逆の順序で実行されます。</span><span class="sxs-lookup"><span data-stu-id="f6f2a-105">This holds true even when your compensation takes place inside a Loop shape: the compensations will be run in reverse order.</span></span> <span data-ttu-id="f6f2a-106">最初にループの最後の繰り返し処理の補正が呼び出され、その次にその前の繰り返し処理の補正が呼び出され、その後も同様に続きます。</span><span class="sxs-lookup"><span data-stu-id="f6f2a-106">First, the compensation for the last iteration of the loop will be invoked, then the compensation for the previous iteration, and so on.</span></span>  
  
> [!CAUTION]
>  <span data-ttu-id="f6f2a-107">データが処理のために補正の物理メモリに維持されるため、ループの内側で補正を使用すると、パフォーマンスに影響を与える可能性があり、繰り返し処理が大量に存在する場合は問題になる可能性があります。</span><span class="sxs-lookup"><span data-stu-id="f6f2a-107">Because data is persisted to physical memory for compensation to work, using compensations inside a loop might affect performance, which might be an issue given a large number of iterations.</span></span>  
  
 <span data-ttu-id="f6f2a-108">既定の順序が要件に適合しない場合は、指定した順序で入れ子になったスコープの補正ハンドラーを明示的に呼び出す独自の補正ハンドラーを記述できます。</span><span class="sxs-lookup"><span data-stu-id="f6f2a-108">If the default ordering does not fit your requirements, you can write your own compensation handler to explicitly call the compensation handlers of the nested scopes in the order you specify.</span></span>  
  
### <a name="to-add-a-compensation-block"></a><span data-ttu-id="f6f2a-109">補正ブロックを追加するには</span><span class="sxs-lookup"><span data-stu-id="f6f2a-109">To add a Compensation Block</span></span>  
  
1.  <span data-ttu-id="f6f2a-110">右クリックし、**スコープ**図形を追加するトランザクションを**補正ブロック**、クリックして**新しい補正ブロック**です。</span><span class="sxs-lookup"><span data-stu-id="f6f2a-110">Right-click the **Scope** shape for the transaction to which you want to add a **Compensation Block**, and then click **New Compensation Block**.</span></span>  
  
    > [!NOTE]
    >  <span data-ttu-id="f6f2a-111">追加する、**補正ブロック**を**スコープ**図形、**トランザクション タイプ**のプロパティ、**スコープ**に図形を設定する必要があります**アトミック**または**実行時間が長い**です。</span><span class="sxs-lookup"><span data-stu-id="f6f2a-111">To add a **Compensation Block** to a **Scope** shape, the **Transaction Type** property of the **Scope** shape must be set to **Atomic** or **Long Running**.</span></span>  
  
     <span data-ttu-id="f6f2a-112">A**補正ブロック**が関連付けられている直後のオーケストレーションに追加**スコープ**図形です。</span><span class="sxs-lookup"><span data-stu-id="f6f2a-112">A **Compensation Block** is added to the orchestration immediately following the associated **Scope** shape.</span></span>  
  
2.  <span data-ttu-id="f6f2a-113">内部、**補正ブロック**図形の図形を追加して、コミットしたトランザクションを元に戻すためのプロセスを作成します。</span><span class="sxs-lookup"><span data-stu-id="f6f2a-113">Inside the **Compensation Block** shape, add shapes to create the process for undoing a committed transaction.</span></span>