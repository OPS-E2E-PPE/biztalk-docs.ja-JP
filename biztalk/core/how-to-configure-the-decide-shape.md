---
title: "判断図形を構成する方法 |Microsoft ドキュメント"
ms.custom: 
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: 
ms.suite: 
ms.tgt_pltfrm: 
ms.topic: article
helpviewer_keywords:
- Decide shape [Orchestration Designer]
- Decide shape [Orchestration Designer], configuring
- Decide shape [Orchestration Designer], branching
- configuring [Orchestration Designer], Decide shapes
ms.assetid: 70910861-3834-49e7-ab1e-d62730ea2a95
caps.latest.revision: "6"
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: a22368134e2c1a0d8deb277e186792158a7c2dd0
ms.sourcegitcommit: cb908c540d8f1a692d01dc8f313e16cb4b4e696d
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 09/20/2017
---
# <a name="how-to-configure-the-decide-shape"></a><span data-ttu-id="0c26e-102">判断図形を構成する方法</span><span class="sxs-lookup"><span data-stu-id="0c26e-102">How to Configure the Decide Shape</span></span>
![](../core/media/ebiz-orch-decide.gif "ebiz_orch_decide")  
<span data-ttu-id="0c26e-103">判断図形</span><span class="sxs-lookup"><span data-stu-id="0c26e-103">Decide shape</span></span>  
  
 <span data-ttu-id="0c26e-104">各分岐、**判断**図形を除く、 **else**分岐、ルールに関連付けられていること。</span><span class="sxs-lookup"><span data-stu-id="0c26e-104">Each branch of a **Decide** shape, except the **else** branch, has a rule associated with it.</span></span> <span data-ttu-id="0c26e-105">個々の分岐の実行のために評価されるルール内のブール式は、BizTalk 式エディターを使用して作成できます。</span><span class="sxs-lookup"><span data-stu-id="0c26e-105">You can use BizTalk Expression Editor to create a Boolean expression in the rule that is evaluated for the execution of that branch.</span></span> <span data-ttu-id="0c26e-106">**Else**ブランチ直前の分岐にブール式の否定を意味する、関連付けられている式がないです。</span><span class="sxs-lookup"><span data-stu-id="0c26e-106">Because the **else** branch implies the negation of the Boolean expression in the previous branch, it does not have an expression associated with it.</span></span>  
  
 <span data-ttu-id="0c26e-107">規則の下または**else**句、支店、**判断**図形がオーケストレーションの他の部分と同じように、追加の図形を含めることができます。</span><span class="sxs-lookup"><span data-stu-id="0c26e-107">Below the rule or **else** clause, a branch of a **Decide** shape can contain additional shapes, just like any other part of the orchestration.</span></span>  
  
### <a name="to-configure-a-decide-shape"></a><span data-ttu-id="0c26e-108">判断図形を構成するには</span><span class="sxs-lookup"><span data-stu-id="0c26e-108">To configure a Decide shape</span></span>  
  
1.  <span data-ttu-id="0c26e-109">BizTalk 式エディターが表示されていない場合は、ルールを右クリックし、をクリックして**ブール式の編集**は、[プロパティ] ウィンドウで、**省略記号**(**.**) ボタンをクリックして、**式**プロパティです。</span><span class="sxs-lookup"><span data-stu-id="0c26e-109">If BizTalk Expression Editor is not visible, right-click the rule and click **Edit Boolean Expression**, or in the Properties window, click the **Ellipsis** (**...**) button for the **Expression** property.</span></span>  
  
2.  <span data-ttu-id="0c26e-110">BizTalk 式エディターでは、以外の各分岐のブール式を作成、 **Else**分岐します。</span><span class="sxs-lookup"><span data-stu-id="0c26e-110">In BizTalk Expression Editor, create a Boolean expression for each branch except the **Else** branch.</span></span> <span data-ttu-id="0c26e-111">例を次に示します。</span><span class="sxs-lookup"><span data-stu-id="0c26e-111">For example,</span></span>  
  
    ```  
    myMessage.Total > 1000  
    myObject.IsValid()  
    myMessage.VIP == true  
    ```  
  
### <a name="to-add-a-branch-to-a-decide-shape"></a><span data-ttu-id="0c26e-112">判断図形に分岐を追加するには</span><span class="sxs-lookup"><span data-stu-id="0c26e-112">To add a branch to a Decide shape</span></span>  
  
1.  <span data-ttu-id="0c26e-113">右クリックし、**判断**図形をクリックして**新しいルール分岐**です。</span><span class="sxs-lookup"><span data-stu-id="0c26e-113">Right-click the **Decide** shape, and then click **New Rule Branch**.</span></span>  
  
     <span data-ttu-id="0c26e-114">- または -</span><span class="sxs-lookup"><span data-stu-id="0c26e-114">—Or—</span></span>  
  
2.  <span data-ttu-id="0c26e-115">新しい図形を既存の 2 つの分岐の間にドラッグします。</span><span class="sxs-lookup"><span data-stu-id="0c26e-115">Drag a new shape between two existing branches.</span></span>  
  
    > [!NOTE]
    >  <span data-ttu-id="0c26e-116">分岐を削除する、**判断**図形をクリックして、削除する分岐を右クリックして**削除**、ルール分岐とキーを押すか、選択、**削除**キー。</span><span class="sxs-lookup"><span data-stu-id="0c26e-116">To remove a branch from a **Decide** shape, right-click the branch you want to remove, and then click **Delete**, or select the rule branch and press the **DELETE** key.</span></span>