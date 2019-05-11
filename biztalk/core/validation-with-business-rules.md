---
title: ビジネス ルールによる検証 |Microsoft Docs
ms.custom: ''
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: ''
ms.suite: ''
ms.tgt_pltfrm: ''
ms.topic: article
helpviewer_keywords:
- validating, process management solutions
- process management solution tutorial, validating
- business rules, validating
- process management solution tutorial, business rules
ms.assetid: a67f3781-629a-4157-9a27-3b73d7a5a3a8
caps.latest.revision: 10
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: 2383f8cabf2e27aa62b7bdcfd6ac56ec30acc018
ms.sourcegitcommit: 381e83d43796a345488d54b3f7413e11d56ad7be
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 05/07/2019
ms.locfileid: "65292620"
---
# <a name="validation-with-business-rules"></a><span data-ttu-id="458e1-102">ビジネス ルールによる検証</span><span class="sxs-lookup"><span data-stu-id="458e1-102">Validation with Business Rules</span></span>
<span data-ttu-id="458e1-103">検証を実行する一般的な方法では、ビジネス ルール フレームワークを使用してビジネス ルールのセットを作成します。</span><span class="sxs-lookup"><span data-stu-id="458e1-103">A common way to do validation is to construct a set of business rules using the Business Rules Framework.</span></span> <span data-ttu-id="458e1-104">使用するルールの呼び出し図形のオーケストレーションで検証を実行します。</span><span class="sxs-lookup"><span data-stu-id="458e1-104">Then you use the Call Rules shape in the orchestration where you want to perform validation.</span></span>  
  
 <span data-ttu-id="458e1-105">ビジネス プロセス管理アプリケーションで、**検証**オーケストレーションはビジネス ルールを使用して、注文の有効性をテストします。</span><span class="sxs-lookup"><span data-stu-id="458e1-105">In the business process management application, the **Validation** orchestration uses business rules to test the validity of the order.</span></span>  
  
 <span data-ttu-id="458e1-106">再コンパイルして再展開することがなく、ルールを変更することができます、ビジネス ルール フレームワークを使用して、**検証**オーケストレーションします。</span><span class="sxs-lookup"><span data-stu-id="458e1-106">Using the Business Rules Framework enables you to change the rules without recompiling and redeploying the **Validation** orchestration.</span></span> <span data-ttu-id="458e1-107">トレードオフである必要がルールの単純なセットの場合があります、オーケストレーションのロジックをコーディングして処理時間を保存することです。</span><span class="sxs-lookup"><span data-stu-id="458e1-107">The trade-off is that for simple sets of rules, you may be able to save processing time by coding the logic in the orchestration.</span></span>  
  
 <span data-ttu-id="458e1-108">ビジネス ルール フレームワークの使用に関する詳細については、次を参照してください。[を使用してビジネス ルールの作成と](../core/creating-and-using-business-rules.md)します。</span><span class="sxs-lookup"><span data-stu-id="458e1-108">For more information about using the Business Rules Framework, see [Creating and Using Business Rules](../core/creating-and-using-business-rules.md).</span></span> <span data-ttu-id="458e1-109">ルールの呼び出し図形の詳細については、次を参照してください。[ルールの呼び出し図形の使用方法](../core/how-to-use-the-call-rules-shape.md)します。</span><span class="sxs-lookup"><span data-stu-id="458e1-109">For more information about the Call Rules shape, see [How to Use the Call Rules Shape](../core/how-to-use-the-call-rules-shape.md).</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="458e1-110">参照</span><span class="sxs-lookup"><span data-stu-id="458e1-110">See Also</span></span>  
 <span data-ttu-id="458e1-111">[ビジネス プロセス管理ソリューションの実装の要点](../core/implementation-highlights-of-the-business-process-management-solution.md) </span><span class="sxs-lookup"><span data-stu-id="458e1-111">[Implementation Highlights of the Business Process Management Solution](../core/implementation-highlights-of-the-business-process-management-solution.md) </span></span>  
 [<span data-ttu-id="458e1-112">プロセス マネージャーのロジック</span><span class="sxs-lookup"><span data-stu-id="458e1-112">Process Manager Logic</span></span>](../core/process-manager-logic.md)