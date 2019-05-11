---
title: カスタム補正をオーケストレーションに追加する方法 |Microsoft Docs
ms.custom: ''
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: ''
ms.suite: ''
ms.tgt_pltfrm: ''
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
caps.latest.revision: 7
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: 09c8d6bfa6f935c6d34de093fc066eee420705b7
ms.sourcegitcommit: 381e83d43796a345488d54b3f7413e11d56ad7be
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 05/07/2019
ms.locfileid: "65343301"
---
# <a name="how-to-add-custom-compensation-to-an-orchestration"></a><span data-ttu-id="0e673-102">カスタム補正をオーケストレーションに追加する方法</span><span class="sxs-lookup"><span data-stu-id="0e673-102">How to Add Custom Compensation to an Orchestration</span></span>
<span data-ttu-id="0e673-103">実行時間の長いとして構成されているオーケストレーション トランザクションには、カスタム補正コードを逆に、トランザクションの効果を元に戻すことができます。</span><span class="sxs-lookup"><span data-stu-id="0e673-103">An orchestration transaction that is configured as long running can have custom compensation code to reverse or undo the effects of the transaction.</span></span> <span data-ttu-id="0e673-104">補正ブロックを使用して呼び出し元のオーケストレーションを呼び出すことができます、オーケストレーションが正常に完了しましたが別のオーケストレーションによって呼び出された場合、**補正**図形。</span><span class="sxs-lookup"><span data-stu-id="0e673-104">If the orchestration has completed successfully and has been called by another orchestration, the calling orchestration can invoke its compensation block using a **Compensate** shape.</span></span>  
  
### <a name="to-specify-that-an-orchestration-will-use-custom-compensation"></a><span data-ttu-id="0e673-105">オーケストレーションがカスタム補正を使用するように指定するには</span><span class="sxs-lookup"><span data-stu-id="0e673-105">To specify that an orchestration will use custom compensation</span></span>  
  
1.  <span data-ttu-id="0e673-106">オーケストレーションの種類 ウィンドウで次のように選択します。**オーケストレーションのプロパティ**します。</span><span class="sxs-lookup"><span data-stu-id="0e673-106">In the Orchestration View window, select **Orchestration Properties**.</span></span>  
  
2.  <span data-ttu-id="0e673-107">[プロパティ] ウィンドウで次のように選択します。**カスタム**のドロップダウン リストで、**補正**プロパティ。</span><span class="sxs-lookup"><span data-stu-id="0e673-107">In the Properties window, select **Custom** in the drop-down for the **Compensation** property.</span></span>  
  
     <span data-ttu-id="0e673-108">**補正**タブが横に表示されます、**オーケストレーション**デザイン画面の下部にあるタブ。</span><span class="sxs-lookup"><span data-stu-id="0e673-108">The **Compensation** tab appears next to the **Orchestration** tab at the bottom of the Design Surface.</span></span>  
  
### <a name="to-design-custom-compensation-for-an-orchestration"></a><span data-ttu-id="0e673-109">オーケストレーションのカスタム補正をデザインするには</span><span class="sxs-lookup"><span data-stu-id="0e673-109">To design custom compensation for an orchestration</span></span>  
  
1.  <span data-ttu-id="0e673-110">をクリックして、**補正**デザイン画面の下部にあるタブ。</span><span class="sxs-lookup"><span data-stu-id="0e673-110">Click the **Compensation** tab at the bottom of the Design Surface.</span></span>  
  
     <span data-ttu-id="0e673-111">**補正デザイン サーフェイス**が表示されます。</span><span class="sxs-lookup"><span data-stu-id="0e673-111">The **Compensation Design Surface** appears.</span></span>  
  
2.  <span data-ttu-id="0e673-112">図形を追加、**補正デザイン サーフェイス**の場合と同様、**オーケストレーション デザイン画面**します。</span><span class="sxs-lookup"><span data-stu-id="0e673-112">Add shapes to the **Compensation Design Surface** just as you would in the **Orchestration Design Surface**.</span></span>  
  
     <span data-ttu-id="0e673-113">詳細については、次を参照してください。[オーケストレーションに図形を追加する](../core/how-to-add-shapes-to-orchestrations.md)します。</span><span class="sxs-lookup"><span data-stu-id="0e673-113">For more information, see [Adding Shapes to Orchestrations](../core/how-to-add-shapes-to-orchestrations.md).</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="0e673-114">参照</span><span class="sxs-lookup"><span data-stu-id="0e673-114">See Also</span></span>  
 [<span data-ttu-id="0e673-115">オーケストレーションのトランザクション化</span><span class="sxs-lookup"><span data-stu-id="0e673-115">Making Orchestrations Transactional</span></span>](../core/making-orchestrations-transactional.md)