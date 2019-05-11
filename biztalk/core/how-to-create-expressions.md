---
title: 式を作成する方法 |Microsoft Docs
ms.custom: ''
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: ''
ms.suite: ''
ms.tgt_pltfrm: ''
ms.topic: article
helpviewer_keywords:
- creating, expressions [Expression Editor]
- opening, Expression Editor [Orchestration Designer]
- Expression Editor, opening
- editing, expressions [Expression Editor]
- Expression Editor, editing expressions
- Expression Editor, creating expressions
ms.assetid: 48f8b00f-6ef1-4145-ad17-15c95518fc8a
caps.latest.revision: 8
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: 8c96769a50de1626550409ef7e86ce0460fc3dd4
ms.sourcegitcommit: 381e83d43796a345488d54b3f7413e11d56ad7be
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 05/07/2019
ms.locfileid: "65385484"
---
# <a name="how-to-create-expressions"></a><span data-ttu-id="5e7da-102">式を作成する方法</span><span class="sxs-lookup"><span data-stu-id="5e7da-102">How to Create Expressions</span></span>
<span data-ttu-id="5e7da-103">BizTalk 式エディタでは、さまざまなオーケストレーション デザイナーの図形の機能を拡張する xlang/s 式を作成することができます。</span><span class="sxs-lookup"><span data-stu-id="5e7da-103">BizTalk Expression Editor enables you to create XLANG/s expressions to expand the capabilities of various Orchestration Designer shapes.</span></span> <span data-ttu-id="5e7da-104">意思決定、遅延の設定、.NET を呼び出して、while ループ条件をテストする xlang/s 式を作成することができます。</span><span class="sxs-lookup"><span data-stu-id="5e7da-104">You can create XLANG/s expressions to make decisions, set delays, make .NET calls, and test while loop conditions.</span></span>  
  
 <span data-ttu-id="5e7da-105">メッセージまたはメッセージの割り当て図形のメッセージ部分に値を割り当てる、.NET 呼び出しを行い、内の変数の値を操作することができます、**式**図形。</span><span class="sxs-lookup"><span data-stu-id="5e7da-105">It enables you to assign values to messages or message parts in the Message Assignment shape, and to make .NET calls and manipulate the values of variables in the **Expression** shape.</span></span> <span data-ttu-id="5e7da-106">複雑なブール式の構築に使用することもできます、**ループ**と**判断**図形で遅延を設定して、**遅延**図形。</span><span class="sxs-lookup"><span data-stu-id="5e7da-106">You can also use it to construct complex Boolean expressions in the **Loop** and **Decide** shapes, and to set a delay in the **Delay** shape.</span></span>  
  
### <a name="to-open-biztalk-expression-editor"></a><span data-ttu-id="5e7da-107">BizTalk 式エディターを開く</span><span class="sxs-lookup"><span data-stu-id="5e7da-107">To open BizTalk Expression Editor</span></span>  
  
1.  <span data-ttu-id="5e7da-108">右クリックし、**式**図形、**ループ**図形、**メッセージの割り当て**、図形、**遅延**図形、または、の分岐**判断**図形。</span><span class="sxs-lookup"><span data-stu-id="5e7da-108">Right-click an **Expression** shape, a **Loop** shape, a **Message Assignment** shape, a **Delay** shape, or a branch of a **Decide** shape.</span></span>  
  
2.  <span data-ttu-id="5e7da-109">クリックして**式の編集**します。</span><span class="sxs-lookup"><span data-stu-id="5e7da-109">Click **Edit Expression**.</span></span>  
  
3.  <span data-ttu-id="5e7da-110">BizTalk 式エディターが表示されます。</span><span class="sxs-lookup"><span data-stu-id="5e7da-110">BizTalk Expression Editor appears.</span></span>  
  
### <a name="to-create-or-edit-an-expression"></a><span data-ttu-id="5e7da-111">作成または式を編集するには</span><span class="sxs-lookup"><span data-stu-id="5e7da-111">To create or edit an expression</span></span>  
  
1.  <span data-ttu-id="5e7da-112">入力するか、BizTalk 式エディターのテキスト フィールドの式を編集します。</span><span class="sxs-lookup"><span data-stu-id="5e7da-112">Type or edit the expression in the text field of BizTalk Expression Editor.</span></span>  
  
2.  <span data-ttu-id="5e7da-113">[OK] をクリックします。</span><span class="sxs-lookup"><span data-stu-id="5e7da-113">Click OK.</span></span> <span data-ttu-id="5e7da-114">これにより、式が保存され、選択した図形に適用されます。</span><span class="sxs-lookup"><span data-stu-id="5e7da-114">This saves the expression and applies it to the selected shape.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="5e7da-115">参照</span><span class="sxs-lookup"><span data-stu-id="5e7da-115">See Also</span></span>  
 [<span data-ttu-id="5e7da-116">XLANG-s 言語</span><span class="sxs-lookup"><span data-stu-id="5e7da-116">XLANG-s Language</span></span>](../core/xlang-s-language.md)