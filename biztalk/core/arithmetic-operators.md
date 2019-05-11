---
title: 算術演算子 |Microsoft Docs
ms.custom: ''
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: ''
ms.suite: ''
ms.tgt_pltfrm: ''
ms.topic: article
ms.assetid: d73e153c-aac1-4cea-92d8-af4a1bea6e6a
caps.latest.revision: 10
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: d9e56d48f6c49107923541d5095fe0b1019f6afa
ms.sourcegitcommit: d27732e569b0897361dfaebca8352aa97bb7efe1
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 05/10/2019
ms.locfileid: "65528822"
---
# <a name="arithmetic-operators"></a><span data-ttu-id="394a9-102">算術演算子</span><span class="sxs-lookup"><span data-stu-id="394a9-102">Arithmetic Operators</span></span>
<span data-ttu-id="394a9-103">ビジネス ルール フレームワークでは、加算、減算、乗算、除算、および残りの部分 (剰余) 演算子でビジネス ルールの作成に使用がサポートしています。</span><span class="sxs-lookup"><span data-stu-id="394a9-103">The Business Rules Framework supports using the addition, subtraction, multiplication, division, and remainder (modulo) operators in creating business rules.</span></span> <span data-ttu-id="394a9-104">次の表では、算術演算子について説明します。</span><span class="sxs-lookup"><span data-stu-id="394a9-104">The following table describes the arithmetic operators.</span></span>  
  
|<span data-ttu-id="394a9-105">算術演算子</span><span class="sxs-lookup"><span data-stu-id="394a9-105">Arithmetic operator</span></span>|<span data-ttu-id="394a9-106">説明</span><span class="sxs-lookup"><span data-stu-id="394a9-106">Description</span></span>|  
|-------------------------|-----------------|  
|<span data-ttu-id="394a9-107">**[追加]**</span><span class="sxs-lookup"><span data-stu-id="394a9-107">**Add**</span></span>|<span data-ttu-id="394a9-108">加算演算子 (arg1 arg2 に追加) を表します。</span><span class="sxs-lookup"><span data-stu-id="394a9-108">Represents the addition operator (arg1 added to arg2).</span></span>|  
|<span data-ttu-id="394a9-109">**減算**</span><span class="sxs-lookup"><span data-stu-id="394a9-109">**Subtract**</span></span>|<span data-ttu-id="394a9-110">減算演算子 (arg1 arg2 減算) を表します。</span><span class="sxs-lookup"><span data-stu-id="394a9-110">Represents the subtraction operator (arg1 subtracted from arg2).</span></span>|  
|<span data-ttu-id="394a9-111">**乗算**</span><span class="sxs-lookup"><span data-stu-id="394a9-111">**Multiply**</span></span>|<span data-ttu-id="394a9-112">乗算演算子 (arg1 arg2 を掛けた値) を表します。</span><span class="sxs-lookup"><span data-stu-id="394a9-112">Represents the multiplication operator (arg1 multiplied by arg2).</span></span>|  
|<span data-ttu-id="394a9-113">**Divide**</span><span class="sxs-lookup"><span data-stu-id="394a9-113">**Divide**</span></span>|<span data-ttu-id="394a9-114">除算演算子 (arg1 arg2 で除算) を表します。</span><span class="sxs-lookup"><span data-stu-id="394a9-114">Represents the division operator (arg1 divided by arg2).</span></span>|  
|<span data-ttu-id="394a9-115">**残りの部分**</span><span class="sxs-lookup"><span data-stu-id="394a9-115">**Remainder**</span></span>|<span data-ttu-id="394a9-116">剰余演算子を表します (arg1 arg2 剰余)。</span><span class="sxs-lookup"><span data-stu-id="394a9-116">Represents the remainder operator (arg1 modulo arg2).</span></span>|  
  
 <span data-ttu-id="394a9-117">オペランドがさまざまな種類で、長い方の型に変換する、小さい方のオペランド型の数値の自動昇格が発生します。</span><span class="sxs-lookup"><span data-stu-id="394a9-117">When operands are of different types, automatic numeric promotion occurs with the smaller operand type being converted to the larger operand type.</span></span> <span data-ttu-id="394a9-118">たとえば場合、**追加**の最初のオペランドと演算子を使用**int**型と 2 番目のオペランドの**長い**型では、最初のオペランドの型に変換されます**長い**実行する前に、**追加**操作。</span><span class="sxs-lookup"><span data-stu-id="394a9-118">For example, if the **Add** operator is used with the first operand of **int** type and the second operand of **long** type, the type of the first operand is converted to **long** before performing the **Add** operation.</span></span> <span data-ttu-id="394a9-119">ルール エンジンは、両方のオペランドを共通の型に昇格できる場合にも二重の昇格をサポートします。</span><span class="sxs-lookup"><span data-stu-id="394a9-119">The rule engine also supports double promotion if both the operands can be promoted to a common type.</span></span> <span data-ttu-id="394a9-120">たとえば場合、**追加**の最初のオペランドと演算子が使用される**int**型と 2 番目のオペランドの**uint** に両方のオペランドの型の型が変換されます**長い**実行する前に、**追加**操作。</span><span class="sxs-lookup"><span data-stu-id="394a9-120">For example, if the **Add** operator is used with the first operand of **int** type and the second operand of **uint** type, the types of both operands are converted to **long** before performing the **Add** operation.</span></span>  
  
## <a name="to-use-a-logical-operator-in-a-business-rule"></a><span data-ttu-id="394a9-121">ビジネス ルールで論理演算子を使用するには</span><span class="sxs-lookup"><span data-stu-id="394a9-121">To use a logical operator in a business rule</span></span>  
 <span data-ttu-id="394a9-122">ビジネス ルールで論理演算子を使用するのにには、次の手順を使用します。</span><span class="sxs-lookup"><span data-stu-id="394a9-122">Use the following procedure to use a logical operator in a business rule.</span></span>  
  
1.  <span data-ttu-id="394a9-123">[ファクト エクスプ ローラー] ウィンドウ、**ボキャブラリ**タブ。</span><span class="sxs-lookup"><span data-stu-id="394a9-123">In the Facts Explorer window, click the **Vocabularies** tab.</span></span>  
  
2.  <span data-ttu-id="394a9-124">展開**ボキャブラリ**、展開**関数**、展開**バージョン 1.0 - 公開済み**、し、ドラッグ、**追加/削除/乗算/分割/残りの部分**条件ペイン/アクション ウィンドウにします。</span><span class="sxs-lookup"><span data-stu-id="394a9-124">Expand **Vocabularies**, expand **Functions**, expand **Version 1.0 - Published**, and then drag the **Add/Subtract/Multiply/Divide/Remainder** to the Conditions pane/Actions pane.</span></span>  
  
3.  <span data-ttu-id="394a9-125">演算子の左辺と右辺の値を指定します。</span><span class="sxs-lookup"><span data-stu-id="394a9-125">Specify values for left and right operators.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="394a9-126">参照</span><span class="sxs-lookup"><span data-stu-id="394a9-126">See Also</span></span>  
 [<span data-ttu-id="394a9-127">論理演算子</span><span class="sxs-lookup"><span data-stu-id="394a9-127">Logical Operators</span></span>](../core/logical-operators.md)