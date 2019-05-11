---
title: ビジネス プロセス管理ソリューションでの処理 |Microsoft Docs
ms.custom: ''
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: ''
ms.suite: ''
ms.tgt_pltfrm: ''
ms.topic: article
helpviewer_keywords:
- process management solution tutorial, processing
- processing, process management solutions
ms.assetid: 0b26447e-d8f1-4084-aa34-6e7f8ffccea5
caps.latest.revision: 12
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: bf08892ff975348624eec4548d0895ef5f3221b0
ms.sourcegitcommit: 381e83d43796a345488d54b3f7413e11d56ad7be
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 05/07/2019
ms.locfileid: "65299828"
---
# <a name="processing-in-the-business-process-management-solution"></a><span data-ttu-id="5b20a-102">ビジネス プロセス管理ソリューションでの処理</span><span class="sxs-lookup"><span data-stu-id="5b20a-102">Processing in the Business Process Management Solution</span></span>
<span data-ttu-id="5b20a-103">このセクションでは、ビジネス プロセス管理ソリューションのしくみについて説明します。 注文の処理、割り込みとため例外を処理する方法を使用して、そのアクションは、その方法を再試行できます。</span><span class="sxs-lookup"><span data-stu-id="5b20a-103">This section describes how the Business Process Management Solution works: how it processes orders, how it makes use of interrupts, and how it handles exceptions so that actions can be retried.</span></span>  
  
 <span data-ttu-id="5b20a-104">注文処理の 2 つの主なオーケストレーションが依存**OrderBroker**と**OrderManager**します。</span><span class="sxs-lookup"><span data-stu-id="5b20a-104">Order processing relies on two main orchestrations, **OrderBroker** and **OrderManager**.</span></span> <span data-ttu-id="5b20a-105">**OrderBroker**注文の種類ごとに 1 つずつ、複数の注文マネージャー オーケストレーションができるようにするため、オーケストレーションが書き込まれます。</span><span class="sxs-lookup"><span data-stu-id="5b20a-105">The **OrderBroker** orchestration is written so that there can be multiple order manager orchestrations, one for each kind of order.</span></span> <span data-ttu-id="5b20a-106">ソリューションは、1 つだけ**OrderManager**します。</span><span class="sxs-lookup"><span data-stu-id="5b20a-106">The solution includes only one **OrderManager**.</span></span> <span data-ttu-id="5b20a-107">、、が比較的一般的な注文の他の種類に対応できるようにします。</span><span class="sxs-lookup"><span data-stu-id="5b20a-107">It, too, is relatively generic so that it can be adapted to other types of orders.</span></span>  
  
## <a name="in-this-section"></a><span data-ttu-id="5b20a-108">このセクションの内容</span><span class="sxs-lookup"><span data-stu-id="5b20a-108">In This Section</span></span>  
  
-   [<span data-ttu-id="5b20a-109">OrderBroker オーケストレーションの処理</span><span class="sxs-lookup"><span data-stu-id="5b20a-109">Processing in the OrderBroker Orchestration</span></span>](../core/processing-in-the-orderbroker-orchestration.md)  
  
-   [<span data-ttu-id="5b20a-110">プロセス マネージャーのロジック</span><span class="sxs-lookup"><span data-stu-id="5b20a-110">Process Manager Logic</span></span>](../core/process-manager-logic.md)  
  
-   [<span data-ttu-id="5b20a-111">注文処理ステージでの処理</span><span class="sxs-lookup"><span data-stu-id="5b20a-111">Processing in the Order Processing Stages</span></span>](../core/processing-in-the-order-processing-stages.md)  
  
-   [<span data-ttu-id="5b20a-112">ビジネス プロセス管理ソリューションの割り込み処理</span><span class="sxs-lookup"><span data-stu-id="5b20a-112">Interrupt Handling in the Business Process Management Solution</span></span>](../core/interrupt-handling-in-the-business-process-management-solution.md)  
  
-   [<span data-ttu-id="5b20a-113">ビジネス プロセス管理ソリューションでの例外処理</span><span class="sxs-lookup"><span data-stu-id="5b20a-113">Exception Handling in the Business Process Management Solution</span></span>](../core/exception-handling-in-the-business-process-management-solution.md)