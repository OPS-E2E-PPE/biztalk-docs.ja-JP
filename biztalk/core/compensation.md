---
title: 補正 |Microsoft Docs
ms.custom: ''
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: ''
ms.suite: ''
ms.tgt_pltfrm: ''
ms.topic: article
helpviewer_keywords:
- compensations, errors
- compensations
- errors, compensations
- compensations, about compensations
- compensations, atomic transactions
- atomic transactions, compensations
- transactions, compensations
ms.assetid: 0a80dd16-fd35-4f45-95b7-52bb9df80cbb
caps.latest.revision: 5
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: eba08eecad12c08a3bebd6f4704d7df82b74d279
ms.sourcegitcommit: 381e83d43796a345488d54b3f7413e11d56ad7be
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 05/07/2019
ms.locfileid: "65357887"
---
# <a name="compensation"></a><span data-ttu-id="f213a-102">補正</span><span class="sxs-lookup"><span data-stu-id="f213a-102">Compensation</span></span>
<span data-ttu-id="f213a-103">エラーが発生した、元に戻すか、正常にコミットされたトランザクションの効果を反転する必要がある場合は、オーケストレーションに補正コードを追加することでこれを実行できます。</span><span class="sxs-lookup"><span data-stu-id="f213a-103">If an error occurs and you need to undo or reverse the effects of a successfully committed transaction, you can do so by adding compensation code to your orchestration.</span></span>  
  
 <span data-ttu-id="f213a-104">トランザクションがそのアクションを正常に完了した後は、補正を呼び出すことができます。</span><span class="sxs-lookup"><span data-stu-id="f213a-104">The compensation can be invoked after the transaction has completed its actions successfully.</span></span> <span data-ttu-id="f213a-105">その時点では、オーケストレーションの状態がわかっている場合と、状態情報は、補正は、トランザクションのコミット時に、オーケストレーションの状態に応じて適切に動作するコードを記述することを意味のコードに提供します。</span><span class="sxs-lookup"><span data-stu-id="f213a-105">At that point, the state of the orchestration is known, and state information is available to the code in the compensation, which means that you can write code to act appropriately depending on the state of the orchestration when the transaction commits.</span></span>  
  
 <span data-ttu-id="f213a-106">補正は、アトミックのトランザクションも指定できます。</span><span class="sxs-lookup"><span data-stu-id="f213a-106">Compensations can also be provided on atomic transactions.</span></span> <span data-ttu-id="f213a-107">これらの補正は、アトミックのトランザクションがコミットされた後にのみ呼び出すことができます。</span><span class="sxs-lookup"><span data-stu-id="f213a-107">These compensations can only be called after the atomic transaction commits.</span></span> <span data-ttu-id="f213a-108">元に戻す補正では、通常の実行のパスに戻したりするコードを記述する必要があります。</span><span class="sxs-lookup"><span data-stu-id="f213a-108">You need to write code to undo or reverse the path of the normal execution in the compensation.</span></span>  
  
 <span data-ttu-id="f213a-109">補正ブロックでは柔軟性があります。別のトランザクション スコープを含むその他の図形を含めることができます。</span><span class="sxs-lookup"><span data-stu-id="f213a-109">The compensation block is flexible; it can contain any other shape, including another transaction scope.</span></span>  
  
> [!NOTE]
>  <span data-ttu-id="f213a-110">指定されたスコープの補正を 1 回だけ行うことができます。</span><span class="sxs-lookup"><span data-stu-id="f213a-110">You can do a compensation only once on a given scope.</span></span>  
  
## <a name="in-this-section"></a><span data-ttu-id="f213a-111">このセクションの内容</span><span class="sxs-lookup"><span data-stu-id="f213a-111">In This Section</span></span>  
  
-   [<span data-ttu-id="f213a-112">補正図形を構成する方法</span><span class="sxs-lookup"><span data-stu-id="f213a-112">How to Configure the Compensate Shape</span></span>](../core/how-to-configure-the-compensate-shape.md)  
  
-   [<span data-ttu-id="f213a-113">カスタム補正をオーケストレーションに追加する方法</span><span class="sxs-lookup"><span data-stu-id="f213a-113">How to Add Custom Compensation to an Orchestration</span></span>](../core/how-to-add-custom-compensation-to-an-orchestration.md)  
  
-   [<span data-ttu-id="f213a-114">補正ブロックを追加する方法</span><span class="sxs-lookup"><span data-stu-id="f213a-114">How to Add a Compensation Block</span></span>](../core/how-to-add-a-compensation-block.md)