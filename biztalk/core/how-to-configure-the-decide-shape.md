---
title: 判断図形を構成する方法 |Microsoft Docs
ms.custom: ''
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: ''
ms.suite: ''
ms.tgt_pltfrm: ''
ms.topic: article
helpviewer_keywords:
- Decide shape [Orchestration Designer]
- Decide shape [Orchestration Designer], configuring
- Decide shape [Orchestration Designer], branching
- configuring [Orchestration Designer], Decide shapes
ms.assetid: 70910861-3834-49e7-ab1e-d62730ea2a95
caps.latest.revision: 6
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: cadca52dade623190b347c0daa3cbd5581c58b2b
ms.sourcegitcommit: 381e83d43796a345488d54b3f7413e11d56ad7be
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 05/07/2019
ms.locfileid: "65341027"
---
# <a name="how-to-configure-the-decide-shape"></a><span data-ttu-id="85948-102">判断図形を構成する方法</span><span class="sxs-lookup"><span data-stu-id="85948-102">How to Configure the Decide Shape</span></span>
<span data-ttu-id="85948-103">![](../core/media/ebiz-orch-decide.gif "ebiz_orch_decide")</span><span class="sxs-lookup"><span data-stu-id="85948-103">![](../core/media/ebiz-orch-decide.gif "ebiz_orch_decide")</span></span>  
<span data-ttu-id="85948-104">判断図形</span><span class="sxs-lookup"><span data-stu-id="85948-104">Decide shape</span></span>  
  
 <span data-ttu-id="85948-105">各分岐を**判断**図形、以外、**他**分岐で、ルールと、対応します。</span><span class="sxs-lookup"><span data-stu-id="85948-105">Each branch of a **Decide** shape, except the **else** branch, has a rule associated with it.</span></span> <span data-ttu-id="85948-106">BizTalk 式エディターを使用して、その分岐を実行するために評価されるルールのブール式を作成することができます。</span><span class="sxs-lookup"><span data-stu-id="85948-106">You can use BizTalk Expression Editor to create a Boolean expression in the rule that is evaluated for the execution of that branch.</span></span> <span data-ttu-id="85948-107">**他**ブランチ直前の分岐のブール式の否定を意味する、関連付けられている式がありません。</span><span class="sxs-lookup"><span data-stu-id="85948-107">Because the **else** branch implies the negation of the Boolean expression in the previous branch, it does not have an expression associated with it.</span></span>  
  
 <span data-ttu-id="85948-108">ルールの下または**他**句では、分岐を**判断**図形がオーケストレーションの他の部分と同様、追加の図形を含めることができます。</span><span class="sxs-lookup"><span data-stu-id="85948-108">Below the rule or **else** clause, a branch of a **Decide** shape can contain additional shapes, just like any other part of the orchestration.</span></span>  
  
### <a name="to-configure-a-decide-shape"></a><span data-ttu-id="85948-109">判断図形を構成するには</span><span class="sxs-lookup"><span data-stu-id="85948-109">To configure a Decide shape</span></span>  
  
1.  <span data-ttu-id="85948-110">BizTalk 式エディターが表示されない場合、ルールを右クリックし、クリックして**ブール式の編集**、プロパティ ウィンドウで次のようにクリックしますまたは、**省略記号**(**...。**) ボタンを**式**プロパティ。</span><span class="sxs-lookup"><span data-stu-id="85948-110">If BizTalk Expression Editor is not visible, right-click the rule and click **Edit Boolean Expression**, or in the Properties window, click the **Ellipsis** (**...**) button for the **Expression** property.</span></span>  
  
2.  <span data-ttu-id="85948-111">BizTalk 式エディターでは、以外の各分岐のブール式を作成、 **Else**分岐します。</span><span class="sxs-lookup"><span data-stu-id="85948-111">In BizTalk Expression Editor, create a Boolean expression for each branch except the **Else** branch.</span></span> <span data-ttu-id="85948-112">例を次に示します。</span><span class="sxs-lookup"><span data-stu-id="85948-112">For example,</span></span>  
  
    ```  
    myMessage.Total > 1000  
    myObject.IsValid()  
    myMessage.VIP == true  
    ```  
  
### <a name="to-add-a-branch-to-a-decide-shape"></a><span data-ttu-id="85948-113">判断図形に分岐を追加するには</span><span class="sxs-lookup"><span data-stu-id="85948-113">To add a branch to a Decide shape</span></span>  
  
1.  <span data-ttu-id="85948-114">右クリックし、**判断**図形をクリックして**新しいルール分岐**します。</span><span class="sxs-lookup"><span data-stu-id="85948-114">Right-click the **Decide** shape, and then click **New Rule Branch**.</span></span>  
  
     <span data-ttu-id="85948-115">- または -</span><span class="sxs-lookup"><span data-stu-id="85948-115">—Or—</span></span>  
  
2.  <span data-ttu-id="85948-116">既存の 2 つの分岐の間には、新しい図形をドラッグします。</span><span class="sxs-lookup"><span data-stu-id="85948-116">Drag a new shape between two existing branches.</span></span>  
  
    > [!NOTE]
    >  <span data-ttu-id="85948-117">分岐を削除する、**判断**図形を削除するをクリックする分岐を右クリックして**削除**、またはキーを押してルール分岐を選択、**削除**キー。</span><span class="sxs-lookup"><span data-stu-id="85948-117">To remove a branch from a **Decide** shape, right-click the branch you want to remove, and then click **Delete**, or select the rule branch and press the **DELETE** key.</span></span>