---
title: "補正 |Microsoft ドキュメント"
ms.custom: 
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: 
ms.suite: 
ms.tgt_pltfrm: 
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
caps.latest.revision: "5"
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: 0c572638ea6212c3fb79e6b239aa8ffbe713c3c8
ms.sourcegitcommit: cb908c540d8f1a692d01dc8f313e16cb4b4e696d
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 09/20/2017
---
# <a name="compensation"></a><span data-ttu-id="7f2d5-102">[補正]</span><span class="sxs-lookup"><span data-stu-id="7f2d5-102">Compensation</span></span>
<span data-ttu-id="7f2d5-103">エラーが発生し、正常にコミットされたトランザクションの効果を元に戻したり、取り消したりする必要がある場合は、オーケストレーションに補正コードを追加します。</span><span class="sxs-lookup"><span data-stu-id="7f2d5-103">If an error occurs and you need to undo or reverse the effects of a successfully committed transaction, you can do so by adding compensation code to your orchestration.</span></span>  
  
 <span data-ttu-id="7f2d5-104">補正は、トランザクションがアクションを正常に完了した後に呼び出すことができます。</span><span class="sxs-lookup"><span data-stu-id="7f2d5-104">The compensation can be invoked after the transaction has completed its actions successfully.</span></span> <span data-ttu-id="7f2d5-105">この時点で、オーケストレーションの状態は認識されており、状態情報を補正のコードに使用できます。これは、トランザクションがコミットされたときのオーケストレーションの状態に応じて、適切に動作するコードを記述できることを意味します。</span><span class="sxs-lookup"><span data-stu-id="7f2d5-105">At that point, the state of the orchestration is known, and state information is available to the code in the compensation, which means that you can write code to act appropriately depending on the state of the orchestration when the transaction commits.</span></span>  
  
 <span data-ttu-id="7f2d5-106">補正は、アトミックのトランザクションでも使用できます。</span><span class="sxs-lookup"><span data-stu-id="7f2d5-106">Compensations can also be provided on atomic transactions.</span></span> <span data-ttu-id="7f2d5-107">これらの補正は、アトミックのトランザクションがコミットした後にのみ呼び出すことができます。</span><span class="sxs-lookup"><span data-stu-id="7f2d5-107">These compensations can only be called after the atomic transaction commits.</span></span> <span data-ttu-id="7f2d5-108">補正での通常の実行のパスを元に戻したり、取り消したりするコードを記述する必要があります。</span><span class="sxs-lookup"><span data-stu-id="7f2d5-108">You need to write code to undo or reverse the path of the normal execution in the compensation.</span></span>  
  
 <span data-ttu-id="7f2d5-109">補正ブロックは柔軟です。別のトランザクション スコープなど、任意の他の図形を格納できます。</span><span class="sxs-lookup"><span data-stu-id="7f2d5-109">The compensation block is flexible; it can contain any other shape, including another transaction scope.</span></span>  
  
> [!NOTE]
>  <span data-ttu-id="7f2d5-110">補正は、指定したスコープで一度だけ実行できます。</span><span class="sxs-lookup"><span data-stu-id="7f2d5-110">You can do a compensation only once on a given scope.</span></span>  
  
## <a name="in-this-section"></a><span data-ttu-id="7f2d5-111">このセクションの内容</span><span class="sxs-lookup"><span data-stu-id="7f2d5-111">In This Section</span></span>  
  
-   [<span data-ttu-id="7f2d5-112">補正図形を構成する方法</span><span class="sxs-lookup"><span data-stu-id="7f2d5-112">How to Configure the Compensate Shape</span></span>](../core/how-to-configure-the-compensate-shape.md)  
  
-   [<span data-ttu-id="7f2d5-113">カスタム補正をオーケストレーションに追加する方法</span><span class="sxs-lookup"><span data-stu-id="7f2d5-113">How to Add Custom Compensation to an Orchestration</span></span>](../core/how-to-add-custom-compensation-to-an-orchestration.md)  
  
-   [<span data-ttu-id="7f2d5-114">補正ブロックを追加する方法</span><span class="sxs-lookup"><span data-stu-id="7f2d5-114">How to Add a Compensation Block</span></span>](../core/how-to-add-a-compensation-block.md)