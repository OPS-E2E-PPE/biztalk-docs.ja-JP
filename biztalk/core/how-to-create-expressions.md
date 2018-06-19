---
title: 式を作成する方法 |Microsoft ドキュメント
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
ms.openlocfilehash: 9d4dbb6e5494856abea00a999a455542c5f4996e
ms.sourcegitcommit: cb908c540d8f1a692d01dc8f313e16cb4b4e696d
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 09/20/2017
ms.locfileid: "22248866"
---
# <a name="how-to-create-expressions"></a><span data-ttu-id="ae841-102">式を作成する方法</span><span class="sxs-lookup"><span data-stu-id="ae841-102">How to Create Expressions</span></span>
<span data-ttu-id="ae841-103">BizTalk 式エディターを使用すると、さまざまなオーケストレーション デザイナーの図形の機能を拡張する XLANG/s 式を作成できます。</span><span class="sxs-lookup"><span data-stu-id="ae841-103">BizTalk Expression Editor enables you to create XLANG/s expressions to expand the capabilities of various Orchestration Designer shapes.</span></span> <span data-ttu-id="ae841-104">XLANG/s 式を作成すると、判断、遅延の設定、.NET の呼び出し、while ループ条件のテストなどを行うことができます。</span><span class="sxs-lookup"><span data-stu-id="ae841-104">You can create XLANG/s expressions to make decisions, set delays, make .NET calls, and test while loop conditions.</span></span>  
  
 <span data-ttu-id="ae841-105">メッセージまたはメッセージの割り当て図形でメッセージ部分に値を割り当てるおよび .NET の呼び出しを行い、内の変数の値を操作することができます、**式**図形です。</span><span class="sxs-lookup"><span data-stu-id="ae841-105">It enables you to assign values to messages or message parts in the Message Assignment shape, and to make .NET calls and manipulate the values of variables in the **Expression** shape.</span></span> <span data-ttu-id="ae841-106">複雑なブール式を構築するために使用することもできます、**ループ**と**判断**図形遅延時間を設定して、**遅延**図形です。</span><span class="sxs-lookup"><span data-stu-id="ae841-106">You can also use it to construct complex Boolean expressions in the **Loop** and **Decide** shapes, and to set a delay in the **Delay** shape.</span></span>  
  
### <a name="to-open-biztalk-expression-editor"></a><span data-ttu-id="ae841-107">BizTalk 式エディターを開くには</span><span class="sxs-lookup"><span data-stu-id="ae841-107">To open BizTalk Expression Editor</span></span>  
  
1.  <span data-ttu-id="ae841-108">右クリックし、**式**図形、**ループ**図形、**メッセージの割り当て**図形、**遅延**図形、または、の分岐**判断**図形です。</span><span class="sxs-lookup"><span data-stu-id="ae841-108">Right-click an **Expression** shape, a **Loop** shape, a **Message Assignment** shape, a **Delay** shape, or a branch of a **Decide** shape.</span></span>  
  
2.  <span data-ttu-id="ae841-109">をクリックして**式を編集**です。</span><span class="sxs-lookup"><span data-stu-id="ae841-109">Click **Edit Expression**.</span></span>  
  
3.  <span data-ttu-id="ae841-110">BizTalk 式エディターが表示されます。</span><span class="sxs-lookup"><span data-stu-id="ae841-110">BizTalk Expression Editor appears.</span></span>  
  
### <a name="to-create-or-edit-an-expression"></a><span data-ttu-id="ae841-111">式を作成または編集するには</span><span class="sxs-lookup"><span data-stu-id="ae841-111">To create or edit an expression</span></span>  
  
1.  <span data-ttu-id="ae841-112">BizTalk 式エディターのテキスト フィールドで、式を入力または編集します。</span><span class="sxs-lookup"><span data-stu-id="ae841-112">Type or edit the expression in the text field of BizTalk Expression Editor.</span></span>  
  
2.  <span data-ttu-id="ae841-113">[OK] をクリックします。</span><span class="sxs-lookup"><span data-stu-id="ae841-113">Click OK.</span></span> <span data-ttu-id="ae841-114">式が保存され、選択した図形に適用されます。</span><span class="sxs-lookup"><span data-stu-id="ae841-114">This saves the expression and applies it to the selected shape.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="ae841-115">参照</span><span class="sxs-lookup"><span data-stu-id="ae841-115">See Also</span></span>  
 [<span data-ttu-id="ae841-116">XLANG の言語</span><span class="sxs-lookup"><span data-stu-id="ae841-116">XLANG-s Language</span></span>](../core/xlang-s-language.md)