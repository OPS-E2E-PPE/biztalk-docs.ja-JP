---
title: オーケストレーションのトランザクション |Microsoft Docs
ms.custom: ''
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: ''
ms.suite: ''
ms.tgt_pltfrm: ''
ms.topic: article
helpviewer_keywords:
- orchestrations, compensations
- orchestrations, transactional
- Transaction Type property
ms.assetid: c4f0b6ca-d939-4d3a-b7ef-53c6aafdea9c
caps.latest.revision: 5
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: 2607c6619391481870baa19b5cda07d7419f9dca
ms.sourcegitcommit: 381e83d43796a345488d54b3f7413e11d56ad7be
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 05/07/2019
ms.locfileid: "65313292"
---
# <a name="transacted-orchestrations"></a><span data-ttu-id="8079c-102">トランザクション オーケストレーション</span><span class="sxs-lookup"><span data-stu-id="8079c-102">Transacted Orchestrations</span></span>
<span data-ttu-id="8079c-103">オーケストレーションがトランザクション スコープと同じようにできます。</span><span class="sxs-lookup"><span data-stu-id="8079c-103">Orchestrations can be transactional, just like scopes.</span></span> <span data-ttu-id="8079c-104">実際には、オーケストレーション自体と見なすスコープ。</span><span class="sxs-lookup"><span data-stu-id="8079c-104">In fact, an orchestration can itself be considered a scope.</span></span> <span data-ttu-id="8079c-105">一般に、トランザクションのスコープとオーケストレーションがトランザクションの場合と同じ規則が適用されます。</span><span class="sxs-lookup"><span data-stu-id="8079c-105">In general, the same rules apply for transacted orchestrations as for transacted scopes.</span></span>  
  
> [!NOTE]
>  <span data-ttu-id="8079c-106">オーケストレーションとその他のスコープには 1 つの違いは、オーケストレーションに例外ハンドラーがないことです。</span><span class="sxs-lookup"><span data-stu-id="8079c-106">One difference between orchestrations and other scopes is that orchestrations do not have exception handlers.</span></span>  
  
## <a name="orchestration-compensation"></a><span data-ttu-id="8079c-107">オーケストレーションの補正</span><span class="sxs-lookup"><span data-stu-id="8079c-107">Orchestration compensation</span></span>  
 <span data-ttu-id="8079c-108">場合、**トランザクション タイプ**プロパティ、オーケストレーションの実行時間の長いに設定されてまたはアトミックで選択することも、値、**補正**プロパティで、既定またはカスタムを指定できます。</span><span class="sxs-lookup"><span data-stu-id="8079c-108">If the **Transaction Type** property for your orchestration is set to long-running or atomic, you can also select a value for the **Compensation** property, which can be Default or Custom.</span></span>  
  
 <span data-ttu-id="8079c-109">選択した場合**カスタム**、補正、**補正** タブは、オーケストレーション デザイン画面と並んで表示されます。</span><span class="sxs-lookup"><span data-stu-id="8079c-109">If you select **Custom** for the compensation, a **Compensation** tab will appear alongside the Orchestration Design Surface.</span></span> <span data-ttu-id="8079c-110">クラスでは、オーケストレーション デザイン画面としての同じを参照し、追加できます図形とポートを同じ方法でします。</span><span class="sxs-lookup"><span data-stu-id="8079c-110">It will look the same as the Orchestration Design Surface, and you can add shapes and ports to it in the same way.</span></span>  
  
 <span data-ttu-id="8079c-111">補正では、他のオーケストレーションによって呼び出されるオーケストレーションにのみ実行します。</span><span class="sxs-lookup"><span data-stu-id="8079c-111">Compensations only take place on orchestrations that are called by other orchestrations.</span></span> <span data-ttu-id="8079c-112">使用して特定のオーケストレーション インスタンスを補うことができます、**識別子**プロパティを**オーケストレーションの呼び出し**図形。</span><span class="sxs-lookup"><span data-stu-id="8079c-112">You can compensate a specific orchestration instance by using the **Identifier** property on the **Call Orchestration** shape.</span></span>  
  
> [!IMPORTANT]
>  <span data-ttu-id="8079c-113">最上位のオーケストレーションの補正が存在する場合は、ランタイム エンジンによって無視されます。</span><span class="sxs-lookup"><span data-stu-id="8079c-113">If a compensation exists on a top-level orchestration, it will be ignored by the runtime engine.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="8079c-114">参照</span><span class="sxs-lookup"><span data-stu-id="8079c-114">See Also</span></span>  
 <span data-ttu-id="8079c-115">[オーケストレーションのトランザクション化](../core/making-orchestrations-transactional.md) </span><span class="sxs-lookup"><span data-stu-id="8079c-115">[Making Orchestrations Transactional](../core/making-orchestrations-transactional.md) </span></span>  
 [<span data-ttu-id="8079c-116">トランザクションの使用と例外の処理</span><span class="sxs-lookup"><span data-stu-id="8079c-116">Using Transactions and Handling Exceptions</span></span>](../core/using-transactions-and-handling-exceptions.md)