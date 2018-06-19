---
title: 式図形を使用する方法 |Microsoft ドキュメント
ms.custom: ''
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: ''
ms.suite: ''
ms.tgt_pltfrm: ''
ms.topic: article
helpviewer_keywords:
- configuring [Orchestration Designer], Expression shapes
- Expression shape [Orchestration Designer]
- Expression shape [Orchestration Designer], configuring
- Expression shape [Orchestration Designer], about Expression shape
ms.assetid: 2d702aa9-b824-4f47-a416-70707ce8ef29
caps.latest.revision: 5
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: e263454db9674d5bc86b6b7dae1649003f3d129c
ms.sourcegitcommit: cb908c540d8f1a692d01dc8f313e16cb4b4e696d
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 09/20/2017
ms.locfileid: "22256058"
---
# <a name="how-to-use-expression-shape"></a><span data-ttu-id="71806-102">式図形の使用方法</span><span class="sxs-lookup"><span data-stu-id="71806-102">How to Use Expression Shape</span></span>
<span data-ttu-id="71806-103">**式**図形では、オーケストレーションで選択した任意の xlang/s 式を入力することができます。</span><span class="sxs-lookup"><span data-stu-id="71806-103">The **Expression** shape enables you to enter any XLANG/s expression you choose in your orchestration.</span></span> <span data-ttu-id="71806-104">たとえば、外部プログラムに対して .NET 呼び出しを行ったり、オーケストレーション変数の値を操作できます。</span><span class="sxs-lookup"><span data-stu-id="71806-104">For example, you can make a .NET call to run an external program, or simply manipulate the values of your orchestration variables.</span></span>  
  
 <span data-ttu-id="71806-105">中に、**式**図形が非常に柔軟なはないを使用して、オーケストレーション図面自体に表示可能であればされますが、高度なオーケストレーション ロジックを実行することをお勧めします。</span><span class="sxs-lookup"><span data-stu-id="71806-105">While the **Expression** shape is quite flexible, it is not good practice to use it to perform high-level orchestration logic, which preferably would be visible in the orchestration drawing itself.</span></span> <span data-ttu-id="71806-106">一般に、わかりやすくなり、オーケストレーションが保持は、**式**図形には、単純なモジュール形式の式が含まれています。</span><span class="sxs-lookup"><span data-stu-id="71806-106">In general, it is easier to understand and maintain your orchestrations if your **Expression** shapes contain simple and modular expressions.</span></span>  
  
### <a name="to-configure-an-expression-shape"></a><span data-ttu-id="71806-107">式図形を構成するには</span><span class="sxs-lookup"><span data-stu-id="71806-107">To configure an Expression shape</span></span>  
  
1.  <span data-ttu-id="71806-108">BizTalk 式エディターが表示されていない場合を右クリックし、**式**図形をクリックして**式の編集**か、[プロパティ] ウィンドウをクリックして、省略記号ボタン (**.**) ボタンをクリックして、**式**プロパティです。</span><span class="sxs-lookup"><span data-stu-id="71806-108">If BizTalk Expression Editor is not visible, right-click the **Expression** shape and click **Edit Expression** or, in the Properties window, click the Ellipsis (**...**) button for the **Expression** property.</span></span>  
  
2.  <span data-ttu-id="71806-109">BizTalk 式エディターで、値を割り当てる式を作成します。</span><span class="sxs-lookup"><span data-stu-id="71806-109">In BizTalk Expression Editor, create an expression to assign values.</span></span> <span data-ttu-id="71806-110">詳細については、次を参照してください。[式の要件と制限](../core/requirements-and-limitations-for-expressions.md)です。</span><span class="sxs-lookup"><span data-stu-id="71806-110">For more information, see [Requirements and Limitations for Expressions](../core/requirements-and-limitations-for-expressions.md).</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="71806-111">参照</span><span class="sxs-lookup"><span data-stu-id="71806-111">See Also</span></span>  
 [<span data-ttu-id="71806-112">XLANG の言語</span><span class="sxs-lookup"><span data-stu-id="71806-112">XLANG-s Language</span></span>](../core/xlang-s-language.md)