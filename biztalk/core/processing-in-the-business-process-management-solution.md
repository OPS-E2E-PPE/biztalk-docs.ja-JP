---
title: "ビジネス プロセス管理ソリューションでの処理 |Microsoft ドキュメント"
ms.custom: 
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: 
ms.suite: 
ms.tgt_pltfrm: 
ms.topic: article
helpviewer_keywords:
- process management solution tutorial, processing
- processing, process management solutions
ms.assetid: 0b26447e-d8f1-4084-aa34-6e7f8ffccea5
caps.latest.revision: "12"
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: 145dd8e616048f1caaa1a59ec41d099e93e47880
ms.sourcegitcommit: cb908c540d8f1a692d01dc8f313e16cb4b4e696d
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 09/20/2017
---
# <a name="processing-in-the-business-process-management-solution"></a><span data-ttu-id="81e5a-102">ビジネス プロセス管理ソリューションでの処理</span><span class="sxs-lookup"><span data-stu-id="81e5a-102">Processing in the Business Process Management Solution</span></span>
<span data-ttu-id="81e5a-103">このセクションでは、ビジネス プロセス管理ソリューションのしくみについて説明します。、注文の処理方法、割り込みとため例外を処理する方法を使用するその操作方法により再試行できます。</span><span class="sxs-lookup"><span data-stu-id="81e5a-103">This section describes how the Business Process Management Solution works: how it processes orders, how it makes use of interrupts, and how it handles exceptions so that actions can be retried.</span></span>  
  
 <span data-ttu-id="81e5a-104">注文処理は、2 つの主なオーケストレーションに依存しています**OrderBroker**と**OrderManager**です。</span><span class="sxs-lookup"><span data-stu-id="81e5a-104">Order processing relies on two main orchestrations, **OrderBroker** and **OrderManager**.</span></span> <span data-ttu-id="81e5a-105">**OrderBroker**複数の ordermanager オーケストレーション、注文の種類ごとに 1 つができるように、オーケストレーションが書き込まれます。</span><span class="sxs-lookup"><span data-stu-id="81e5a-105">The **OrderBroker** orchestration is written so that there can be multiple order manager orchestrations, one for each kind of order.</span></span> <span data-ttu-id="81e5a-106">ソリューション内に 1 つだけ**OrderManager**です。</span><span class="sxs-lookup"><span data-stu-id="81e5a-106">The solution includes only one **OrderManager**.</span></span> <span data-ttu-id="81e5a-107">他の種類の注文に適応させる方法としても比較的一般的です。</span><span class="sxs-lookup"><span data-stu-id="81e5a-107">It, too, is relatively generic so that it can be adapted to other types of orders.</span></span>  
  
## <a name="in-this-section"></a><span data-ttu-id="81e5a-108">このセクションの内容</span><span class="sxs-lookup"><span data-stu-id="81e5a-108">In This Section</span></span>  
  
-   [<span data-ttu-id="81e5a-109">OrderBroker オーケストレーションでの処理</span><span class="sxs-lookup"><span data-stu-id="81e5a-109">Processing in the OrderBroker Orchestration</span></span>](../core/processing-in-the-orderbroker-orchestration.md)  
  
-   [<span data-ttu-id="81e5a-110">プロセス マネージャのロジック</span><span class="sxs-lookup"><span data-stu-id="81e5a-110">Process Manager Logic</span></span>](../core/process-manager-logic.md)  
  
-   [<span data-ttu-id="81e5a-111">注文処理ステージでの処理</span><span class="sxs-lookup"><span data-stu-id="81e5a-111">Processing in the Order Processing Stages</span></span>](../core/processing-in-the-order-processing-stages.md)  
  
-   [<span data-ttu-id="81e5a-112">ビジネス プロセス管理ソリューションでの処理を中断します。</span><span class="sxs-lookup"><span data-stu-id="81e5a-112">Interrupt Handling in the Business Process Management Solution</span></span>](../core/interrupt-handling-in-the-business-process-management-solution.md)  
  
-   [<span data-ttu-id="81e5a-113">ビジネス プロセス管理ソリューションでの例外処理</span><span class="sxs-lookup"><span data-stu-id="81e5a-113">Exception Handling in the Business Process Management Solution</span></span>](../core/exception-handling-in-the-business-process-management-solution.md)