---
title: "カスタム補正をオーケストレーションに追加する方法 |Microsoft ドキュメント"
ms.custom: 
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: 
ms.suite: 
ms.tgt_pltfrm: 
ms.topic: article
helpviewer_keywords:
- orchestrations, compensations
- Compensate shape [Orchestration Designer]
- Compensate shape [Orchestration Designer], orchestrations
- Compensation property
- orchestrations, transactional
- orchestrations, customizing
- customizing, orchestrations
- Compensate shape [Orchestration Designer], custom compensation
ms.assetid: d153498d-8f98-42ae-90b9-e3083d669aef
caps.latest.revision: "7"
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: 3eadb9cba6e5a49be516a8095b01f93ca7a490f7
ms.sourcegitcommit: cb908c540d8f1a692d01dc8f313e16cb4b4e696d
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 09/20/2017
---
# <a name="how-to-add-custom-compensation-to-an-orchestration"></a><span data-ttu-id="ac996-102">カスタム補正をオーケストレーションに追加する方法</span><span class="sxs-lookup"><span data-stu-id="ac996-102">How to Add Custom Compensation to an Orchestration</span></span>
<span data-ttu-id="ac996-103">長時間トランザクションとして構成されたオーケストレーションのトランザクションにはカスタム補正コードを記述し、トランザクションの効果を取り消したり、元に戻したりできます。</span><span class="sxs-lookup"><span data-stu-id="ac996-103">An orchestration transaction that is configured as long running can have custom compensation code to reverse or undo the effects of the transaction.</span></span> <span data-ttu-id="ac996-104">呼び出し元のオーケストレーションの補正ブロックを使用して呼び出すことができます、オーケストレーションが正常に完了したが、別のオーケストレーションによって呼び出された場合は、**補正**図形です。</span><span class="sxs-lookup"><span data-stu-id="ac996-104">If the orchestration has completed successfully and has been called by another orchestration, the calling orchestration can invoke its compensation block using a **Compensate** shape.</span></span>  
  
### <a name="to-specify-that-an-orchestration-will-use-custom-compensation"></a><span data-ttu-id="ac996-105">オーケストレーションがカスタム補正を使用するように指定するには</span><span class="sxs-lookup"><span data-stu-id="ac996-105">To specify that an orchestration will use custom compensation</span></span>  
  
1.  <span data-ttu-id="ac996-106">オーケストレーションの種類 ウィンドウで、選択**オーケストレーションのプロパティ**です。</span><span class="sxs-lookup"><span data-stu-id="ac996-106">In the Orchestration View window, select **Orchestration Properties**.</span></span>  
  
2.  <span data-ttu-id="ac996-107">[プロパティ] ウィンドウで選択**カスタム**のドロップダウン リストで、**補正**プロパティです。</span><span class="sxs-lookup"><span data-stu-id="ac996-107">In the Properties window, select **Custom** in the drop-down for the **Compensation** property.</span></span>  
  
     <span data-ttu-id="ac996-108">**補正** タブが横に表示、**オーケストレーション**デザイン画面の下部にあるタブ。</span><span class="sxs-lookup"><span data-stu-id="ac996-108">The **Compensation** tab appears next to the **Orchestration** tab at the bottom of the Design Surface.</span></span>  
  
### <a name="to-design-custom-compensation-for-an-orchestration"></a><span data-ttu-id="ac996-109">オーケストレーションのカスタム補正をデザインするには</span><span class="sxs-lookup"><span data-stu-id="ac996-109">To design custom compensation for an orchestration</span></span>  
  
1.  <span data-ttu-id="ac996-110">クリックして、**補正**デザイン画面の下部にあるタブ。</span><span class="sxs-lookup"><span data-stu-id="ac996-110">Click the **Compensation** tab at the bottom of the Design Surface.</span></span>  
  
     <span data-ttu-id="ac996-111">**補正デザイン サーフェイス**が表示されます。</span><span class="sxs-lookup"><span data-stu-id="ac996-111">The **Compensation Design Surface** appears.</span></span>  
  
2.  <span data-ttu-id="ac996-112">図形を追加、**補正デザイン サーフェイス**の場合と同様、**オーケストレーション デザイン画面**です。</span><span class="sxs-lookup"><span data-stu-id="ac996-112">Add shapes to the **Compensation Design Surface** just as you would in the **Orchestration Design Surface**.</span></span>  
  
     <span data-ttu-id="ac996-113">詳細については、次を参照してください。[オーケストレーションに図形を追加する](../core/how-to-add-shapes-to-orchestrations.md)です。</span><span class="sxs-lookup"><span data-stu-id="ac996-113">For more information, see [Adding Shapes to Orchestrations](../core/how-to-add-shapes-to-orchestrations.md).</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="ac996-114">参照</span><span class="sxs-lookup"><span data-stu-id="ac996-114">See Also</span></span>  
 [<span data-ttu-id="ac996-115">トランザクション オーケストレーションを行う</span><span class="sxs-lookup"><span data-stu-id="ac996-115">Making Orchestrations Transactional</span></span>](../core/making-orchestrations-transactional.md)