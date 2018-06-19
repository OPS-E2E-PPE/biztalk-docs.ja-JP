---
title: 補正図形を構成する方法 |Microsoft ドキュメント
ms.custom: ''
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: ''
ms.suite: ''
ms.tgt_pltfrm: ''
ms.topic: article
helpviewer_keywords:
- Compensate shape [Orchestration Designer], about Compensate shape
- Compensate shape [Orchestration Designer]
- compensations, Compensate shape [Orchestration Designer]
- configuring [Orchestration Designer], Compensate shape
- Compensate shape [Orchestration Designer], configuring
ms.assetid: 9f06289e-4d11-4864-9851-c210276865a7
caps.latest.revision: 4
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: 059ac58d95d33234737033c00c4a6a2a36e256f6
ms.sourcegitcommit: cb908c540d8f1a692d01dc8f313e16cb4b4e696d
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 09/20/2017
ms.locfileid: "22248282"
---
# <a name="how-to-configure-the-compensate-shape"></a><span data-ttu-id="039e7-102">補正図形を構成する方法</span><span class="sxs-lookup"><span data-stu-id="039e7-102">How to Configure the Compensate Shape</span></span>
<span data-ttu-id="039e7-103">追加できるかどうか、オーケストレーションで入れ子になったトランザクションを使っている場合、**補正**補正ブロックまたはトランザクション スコープの例外ブロックに図形です。</span><span class="sxs-lookup"><span data-stu-id="039e7-103">If you are using nested transactions in your orchestration, you can add a **Compensate** shape in the compensation block or an exception block of a transaction scope.</span></span> <span data-ttu-id="039e7-104">これにより、入れ子にされたトランザクションに対して、オーケストレーション内で明示的に補正を実行することができます。</span><span class="sxs-lookup"><span data-stu-id="039e7-104">This enables your orchestration to explicitly perform compensation on a nested transaction.</span></span> <span data-ttu-id="039e7-105">補正するトランザクションを指定する、**補正**形状、および入れ子になったトランザクション内のすべての補正コードが実行される正常にコミットされたトランザクションを提供します。</span><span class="sxs-lookup"><span data-stu-id="039e7-105">You specify which transaction you would like to be compensated in the **Compensate** shape, and any compensation code in the nested transaction will be run, provided the transaction committed successfully.</span></span>  
  
> [!NOTE]
>  <span data-ttu-id="039e7-106">**補正**プロパティは、トランザクション スコープの一意の識別子を参照; はスコープの名前を参照していません。</span><span class="sxs-lookup"><span data-stu-id="039e7-106">The **Compensation** property refers to the unique identifier of the transaction scope; it does not refer to the name of the scope.</span></span>  
  
 <span data-ttu-id="039e7-107">1 つ以上の入れ子になったトランザクションを補正する場合は、追加する**補正**トランザクションごとの図形です。</span><span class="sxs-lookup"><span data-stu-id="039e7-107">If you want to compensate more than one nested transaction, you add an additional **Compensate** shape for each transaction.</span></span>  
  
 <span data-ttu-id="039e7-108">いいえ**補正**図形は外側のトランザクションに他の補正コードがない場合に必要です。 入れ子になったトランザクションの補正コードを自動的に実行されます。</span><span class="sxs-lookup"><span data-stu-id="039e7-108">No **Compensate** shape is necessary if there is no other compensation code in an outer transaction; the compensation code of any nested transactions will be run automatically.</span></span> <span data-ttu-id="039e7-109">**補正**図形を使用すると入れ子になったトランザクションを補正するかどうかを決定することにより、プロセスを制御します。</span><span class="sxs-lookup"><span data-stu-id="039e7-109">The **Compensate** shape gives you control over the process by allowing you to decide whether or not you want a nested transaction to be compensated.</span></span>  
  
### <a name="to-configure-a-compensate-shape"></a><span data-ttu-id="039e7-110">補正図形を構成するには</span><span class="sxs-lookup"><span data-stu-id="039e7-110">To configure a Compensate shape</span></span>  
  
-   <span data-ttu-id="039e7-111">[プロパティ] ウィンドウでからを呼び出す補正ブロックを選択、**補正**ドロップダウン リスト。</span><span class="sxs-lookup"><span data-stu-id="039e7-111">In the Properties window, select the compensation block to call from the **Compensation** drop-down list.</span></span>  
  
     <span data-ttu-id="039e7-112">ドロップダウン リストには、補正可能なすべてのトランザクションが表示されます。これには、現在のトランザクションと、現在のトランザクション直下の子トランザクションも含まれます。</span><span class="sxs-lookup"><span data-stu-id="039e7-112">The drop-down list will display all of the transactions which can be compensated, which includes the current transaction and any immediate child transactions of the current transaction.</span></span> <span data-ttu-id="039e7-113">目的のトランザクションが表示されない場合は、トランザクションの関係が原因である可能性があります。</span><span class="sxs-lookup"><span data-stu-id="039e7-113">If you cannot see a transaction that you expect, it might be due to the relationship of the transactions.</span></span>  
  
    > [!NOTE]
    >  <span data-ttu-id="039e7-114">現在のトランザクションの本体の中からトランザクションを補正することはできません。</span><span class="sxs-lookup"><span data-stu-id="039e7-114">You cannot compensate the current transaction from within the body of the transaction.</span></span>  <span data-ttu-id="039e7-115">補正は、トランザクションの補正ブロックまたは例外ブロックから行います。</span><span class="sxs-lookup"><span data-stu-id="039e7-115">You can compensate it from the compensation block or an exception block of the transaction.</span></span>  
  
     <span data-ttu-id="039e7-116">現在のトランザクションの補正を選択した場合は、明示的な補正ブロックではなく (存在する場合)、既定のハンドラーが呼び出されます。</span><span class="sxs-lookup"><span data-stu-id="039e7-116">If you choose to compensate the current transaction, that means that the default handler will be invoked, and not an explicit compensation block (if there is one).</span></span> <span data-ttu-id="039e7-117">これは、直接入れ子にされている、正常に完了したトランザクションを、自動的に補正するためのメカニズムです。</span><span class="sxs-lookup"><span data-stu-id="039e7-117">This is a mechanism for automatically compensating directly nested transactions that have completed successfully.</span></span>