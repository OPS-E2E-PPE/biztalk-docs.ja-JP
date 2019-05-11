---
title: メッセージの割り当て図形を構成する方法 |Microsoft Docs
ms.custom: ''
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: ''
ms.suite: ''
ms.tgt_pltfrm: ''
ms.topic: article
helpviewer_keywords:
- Message Assignment shape [Orchestration Designer], configuring
- Message Assignment shape [Orchestration Designer], about Message Assignment shape
- configuring [Orchestration Designer], Message Assignment shape
- Message Assignment shape [Orchestration Designer]
ms.assetid: 46920b49-5955-4e15-9a7c-2652e02ba1bf
caps.latest.revision: 5
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: 4ef13227071bcb483f541afeaf8465cb83ae9b21
ms.sourcegitcommit: 381e83d43796a345488d54b3f7413e11d56ad7be
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 05/07/2019
ms.locfileid: "65386042"
---
# <a name="how-to-configure-the-message-assignment-shape"></a><span data-ttu-id="70144-102">メッセージの割り当て図形を構成する方法</span><span class="sxs-lookup"><span data-stu-id="70144-102">How to Configure the Message Assignment Shape</span></span>
<span data-ttu-id="70144-103">![](../core/media/ebiz-orch-assign.gif "ebiz_orch_assign")</span><span class="sxs-lookup"><span data-stu-id="70144-103">![](../core/media/ebiz-orch-assign.gif "ebiz_orch_assign")</span></span>  
<span data-ttu-id="70144-104">メッセージの割り当て図形</span><span class="sxs-lookup"><span data-stu-id="70144-104">Message Assignment shape</span></span>  
  
> [!NOTE]
>  <span data-ttu-id="70144-105">A**メッセージの割り当て**図形を配置できる内でのみ、**メッセージの構築**図形。</span><span class="sxs-lookup"><span data-stu-id="70144-105">A **Message Assignment** shape can exist only within a **Construct Message** shape.</span></span> <span data-ttu-id="70144-106">デザイン サーフェイスでは、メッセージの割り当てをその他の場所にドラッグした場合、新しい**メッセージの構築**図形が作成されます。</span><span class="sxs-lookup"><span data-stu-id="70144-106">If you drag a Message Assignment anywhere else on the design surface, a new **Construct Message** shape will be created.</span></span>  
  
### <a name="to-configure-a-message-assignment-shape"></a><span data-ttu-id="70144-107">メッセージの割り当て図形を構成するには</span><span class="sxs-lookup"><span data-stu-id="70144-107">To configure a Message Assignment shape</span></span>  
  
1.  <span data-ttu-id="70144-108">BizTalk 式エディターが表示されていない場合を右クリックし、**メッセージの割り当て**図形し、クリックして**式の編集**または、[プロパティ] ウィンドウで、**省略記号**(**...**) ボタンを**式**プロパティ。</span><span class="sxs-lookup"><span data-stu-id="70144-108">If BizTalk Expression Editor is not visible, right-click the **Message Assignment** shape and click **Edit Expression** or, in the Properties window, click the **Ellipsis** (**...**) button for the **Expression** property.</span></span>  
  
2.  <span data-ttu-id="70144-109">BizTalk 式エディターでは、値を代入する式を作成します。</span><span class="sxs-lookup"><span data-stu-id="70144-109">In BizTalk Expression Editor, create an expression to assign values.</span></span> <span data-ttu-id="70144-110">詳細については、次を参照してください。[式の要件と制限](../core/requirements-and-limitations-for-expressions.md)します。</span><span class="sxs-lookup"><span data-stu-id="70144-110">For more information, see [Requirements and Limitations for Expressions](../core/requirements-and-limitations-for-expressions.md).</span></span>