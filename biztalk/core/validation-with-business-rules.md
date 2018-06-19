---
title: ビジネス ルールによる検証 |Microsoft ドキュメント
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
ms.openlocfilehash: 8926cf8bd95c2b90c7d16151b47f8893120b812e
ms.sourcegitcommit: cb908c540d8f1a692d01dc8f313e16cb4b4e696d
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 09/20/2017
ms.locfileid: "22287778"
---
# <a name="validation-with-business-rules"></a><span data-ttu-id="5db29-102">ビジネス ルールによる検証</span><span class="sxs-lookup"><span data-stu-id="5db29-102">Validation with Business Rules</span></span>
<span data-ttu-id="5db29-103">通常、検証を行うには、ビジネス ルール フレームワークを使用してビジネス ルールのセットを作成し、</span><span class="sxs-lookup"><span data-stu-id="5db29-103">A common way to do validation is to construct a set of business rules using the Business Rules Framework.</span></span> <span data-ttu-id="5db29-104">検証を行うオーケストレーションでルールの呼び出し図形を使用します。</span><span class="sxs-lookup"><span data-stu-id="5db29-104">Then you use the Call Rules shape in the orchestration where you want to perform validation.</span></span>  
  
 <span data-ttu-id="5db29-105">ビジネス プロセス管理アプリケーションで、**検証**オーケストレーションでは、ビジネス ルールを使用して、注文の有効性をテストします。</span><span class="sxs-lookup"><span data-stu-id="5db29-105">In the business process management application, the **Validation** orchestration uses business rules to test the validity of the order.</span></span>  
  
 <span data-ttu-id="5db29-106">再コンパイルと再展開せずに、ルールを変更することができます、ビジネス ルール フレームワークを使用して、**検証**オーケストレーションです。</span><span class="sxs-lookup"><span data-stu-id="5db29-106">Using the Business Rules Framework enables you to change the rules without recompiling and redeploying the **Validation** orchestration.</span></span> <span data-ttu-id="5db29-107">ただし、単純なルール セットの場合は、オーケストレーションでロジックのコードを記述することにより、処理時間を短縮できる可能性があります。</span><span class="sxs-lookup"><span data-stu-id="5db29-107">The trade-off is that for simple sets of rules, you may be able to save processing time by coding the logic in the orchestration.</span></span>  
  
 <span data-ttu-id="5db29-108">詳細については、ビジネス ルール フレームワークを使用して、次を参照してください。[を使用してビジネス ルールの作成と](../core/creating-and-using-business-rules.md)です。</span><span class="sxs-lookup"><span data-stu-id="5db29-108">For more information about using the Business Rules Framework, see [Creating and Using Business Rules](../core/creating-and-using-business-rules.md).</span></span> <span data-ttu-id="5db29-109">ルールの呼び出し図形の詳細については、次を参照してください。[ルールの呼び出し図形を使用する方法](../core/how-to-use-the-call-rules-shape.md)です。</span><span class="sxs-lookup"><span data-stu-id="5db29-109">For more information about the Call Rules shape, see [How to Use the Call Rules Shape](../core/how-to-use-the-call-rules-shape.md).</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="5db29-110">参照</span><span class="sxs-lookup"><span data-stu-id="5db29-110">See Also</span></span>  
 <span data-ttu-id="5db29-111">[ビジネス プロセス管理ソリューションの実装の要点](../core/implementation-highlights-of-the-business-process-management-solution.md) </span><span class="sxs-lookup"><span data-stu-id="5db29-111">[Implementation Highlights of the Business Process Management Solution](../core/implementation-highlights-of-the-business-process-management-solution.md) </span></span>  
 [<span data-ttu-id="5db29-112">プロセス マネージャのロジック</span><span class="sxs-lookup"><span data-stu-id="5db29-112">Process Manager Logic</span></span>](../core/process-manager-logic.md)