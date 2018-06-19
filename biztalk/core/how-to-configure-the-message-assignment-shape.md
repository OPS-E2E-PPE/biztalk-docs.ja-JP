---
title: メッセージの割り当て図形を構成する方法 |Microsoft ドキュメント
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
ms.openlocfilehash: c6be49a61e79ed4f5e03cfca854d4b5b4b57270e
ms.sourcegitcommit: cb908c540d8f1a692d01dc8f313e16cb4b4e696d
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 09/20/2017
ms.locfileid: "22248642"
---
# <a name="how-to-configure-the-message-assignment-shape"></a><span data-ttu-id="25a0f-102">メッセージの割り当て図形を構成する方法</span><span class="sxs-lookup"><span data-stu-id="25a0f-102">How to Configure the Message Assignment Shape</span></span>
![](../core/media/ebiz-orch-assign.gif "ebiz_orch_assign")  
<span data-ttu-id="25a0f-103">メッセージの割り当て図形</span><span class="sxs-lookup"><span data-stu-id="25a0f-103">Message Assignment shape</span></span>  
  
> [!NOTE]
>  <span data-ttu-id="25a0f-104">A**メッセージの割り当て**図形を配置できる内でのみ、**メッセージの構築**図形です。</span><span class="sxs-lookup"><span data-stu-id="25a0f-104">A **Message Assignment** shape can exist only within a **Construct Message** shape.</span></span> <span data-ttu-id="25a0f-105">デザイン サーフェイスでは、メッセージの割り当てをその他の場所にドラッグした場合、新しい**メッセージの構築**図形が作成されます。</span><span class="sxs-lookup"><span data-stu-id="25a0f-105">If you drag a Message Assignment anywhere else on the design surface, a new **Construct Message** shape will be created.</span></span>  
  
### <a name="to-configure-a-message-assignment-shape"></a><span data-ttu-id="25a0f-106">メッセージの割り当て図形を構成するには</span><span class="sxs-lookup"><span data-stu-id="25a0f-106">To configure a Message Assignment shape</span></span>  
  
1.  <span data-ttu-id="25a0f-107">BizTalk 式エディターが表示されていない場合を右クリックし、**メッセージの割り当て**図形をクリックして**式の編集**か、[プロパティ] ウィンドウをクリックして、**省略記号**(**...**) ボタンをクリックして、**式**プロパティです。</span><span class="sxs-lookup"><span data-stu-id="25a0f-107">If BizTalk Expression Editor is not visible, right-click the **Message Assignment** shape and click **Edit Expression** or, in the Properties window, click the **Ellipsis** (**...**) button for the **Expression** property.</span></span>  
  
2.  <span data-ttu-id="25a0f-108">BizTalk 式エディターで、値を割り当てる式を作成します。</span><span class="sxs-lookup"><span data-stu-id="25a0f-108">In BizTalk Expression Editor, create an expression to assign values.</span></span> <span data-ttu-id="25a0f-109">詳細については、次を参照してください。[式の要件と制限](../core/requirements-and-limitations-for-expressions.md)です。</span><span class="sxs-lookup"><span data-stu-id="25a0f-109">For more information, see [Requirements and Limitations for Expressions](../core/requirements-and-limitations-for-expressions.md).</span></span>