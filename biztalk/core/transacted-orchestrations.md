---
title: "オーケストレーションをトランザクション |Microsoft ドキュメント"
ms.custom: 
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: 
ms.suite: 
ms.tgt_pltfrm: 
ms.topic: article
helpviewer_keywords:
- orchestrations, compensations
- orchestrations, transactional
- Transaction Type property
ms.assetid: c4f0b6ca-d939-4d3a-b7ef-53c6aafdea9c
caps.latest.revision: "5"
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: f8c6fb466e0c3cc5cae4a076237d1dbc970b5794
ms.sourcegitcommit: cb908c540d8f1a692d01dc8f313e16cb4b4e696d
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 09/20/2017
---
# <a name="transacted-orchestrations"></a><span data-ttu-id="97bdc-102">トランザクション オーケストレーション</span><span class="sxs-lookup"><span data-stu-id="97bdc-102">Transacted Orchestrations</span></span>
<span data-ttu-id="97bdc-103">オーケストレーションは、スコープと同様にトランザクションになることができます。</span><span class="sxs-lookup"><span data-stu-id="97bdc-103">Orchestrations can be transactional, just like scopes.</span></span> <span data-ttu-id="97bdc-104">実際、オーケストレーションそのものをスコープと見なすことができます。</span><span class="sxs-lookup"><span data-stu-id="97bdc-104">In fact, an orchestration can itself be considered a scope.</span></span> <span data-ttu-id="97bdc-105">一般的に、トランザクションの対象であるオーケストレーションには、トランザクションの対象であるスコープと同じルールが適用されます。</span><span class="sxs-lookup"><span data-stu-id="97bdc-105">In general, the same rules apply for transacted orchestrations as for transacted scopes.</span></span>  
  
> [!NOTE]
>  <span data-ttu-id="97bdc-106">オーケストレーションとその他のスコープの違いとして、オーケストレーションには例外ハンドラーがないという点があります。</span><span class="sxs-lookup"><span data-stu-id="97bdc-106">One difference between orchestrations and other scopes is that orchestrations do not have exception handlers.</span></span>  
  
## <a name="orchestration-compensation"></a><span data-ttu-id="97bdc-107">オーケストレーションの補正</span><span class="sxs-lookup"><span data-stu-id="97bdc-107">Orchestration compensation</span></span>  
 <span data-ttu-id="97bdc-108">場合、**トランザクション タイプ**、オーケストレーションのプロパティが長時間またはアトミック、選択することも、値を**補正**プロパティで、既定またはカスタム指定できます。</span><span class="sxs-lookup"><span data-stu-id="97bdc-108">If the **Transaction Type** property for your orchestration is set to long-running or atomic, you can also select a value for the **Compensation** property, which can be Default or Custom.</span></span>  
  
 <span data-ttu-id="97bdc-109">選択した場合**カスタム**、補正、**補正**と共に、オーケストレーション デザイン画面にタブが表示されます。</span><span class="sxs-lookup"><span data-stu-id="97bdc-109">If you select **Custom** for the compensation, a **Compensation** tab will appear alongside the Orchestration Design Surface.</span></span> <span data-ttu-id="97bdc-110">このタブの表示はオーケストレーション デザイン画面と同じで、図形やポートも同じように追加できます。</span><span class="sxs-lookup"><span data-stu-id="97bdc-110">It will look the same as the Orchestration Design Surface, and you can add shapes and ports to it in the same way.</span></span>  
  
 <span data-ttu-id="97bdc-111">補正は、他のオーケストレーションから呼び出された場合にのみオーケストレーションで実行されます。</span><span class="sxs-lookup"><span data-stu-id="97bdc-111">Compensations only take place on orchestrations that are called by other orchestrations.</span></span> <span data-ttu-id="97bdc-112">使用して特定のオーケストレーション インスタンスを補うことができます、**識別子**プロパティを**オーケストレーションの呼び出し**図形です。</span><span class="sxs-lookup"><span data-stu-id="97bdc-112">You can compensate a specific orchestration instance by using the **Identifier** property on the **Call Orchestration** shape.</span></span>  
  
> [!IMPORTANT]
>  <span data-ttu-id="97bdc-113">最上位のオーケストレーションに存在する補正は、ランタイム エンジンにより無視されます。</span><span class="sxs-lookup"><span data-stu-id="97bdc-113">If a compensation exists on a top-level orchestration, it will be ignored by the runtime engine.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="97bdc-114">参照</span><span class="sxs-lookup"><span data-stu-id="97bdc-114">See Also</span></span>  
 <span data-ttu-id="97bdc-115">[トランザクション オーケストレーションを行う](../core/making-orchestrations-transactional.md) </span><span class="sxs-lookup"><span data-stu-id="97bdc-115">[Making Orchestrations Transactional](../core/making-orchestrations-transactional.md) </span></span>  
 [<span data-ttu-id="97bdc-116">トランザクションを使用して、例外の処理</span><span class="sxs-lookup"><span data-stu-id="97bdc-116">Using Transactions and Handling Exceptions</span></span>](../core/using-transactions-and-handling-exceptions.md)