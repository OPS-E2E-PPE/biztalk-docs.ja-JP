---
title: 算術演算子 |Microsoft ドキュメント
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
ms.openlocfilehash: 4b3d66a990437929176835228efa1a74a5fa8683
ms.sourcegitcommit: cb908c540d8f1a692d01dc8f313e16cb4b4e696d
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 09/20/2017
ms.locfileid: "22230522"
---
# <a name="arithmetic-operators"></a><span data-ttu-id="99584-102">算術演算子</span><span class="sxs-lookup"><span data-stu-id="99584-102">Arithmetic Operators</span></span>
<span data-ttu-id="99584-103">ビジネス ルール フレームワークでは、ビジネス ルールの作成時に、加算、減算、乗算、除算、剰余の各演算子を使用できます。</span><span class="sxs-lookup"><span data-stu-id="99584-103">The Business Rules Framework supports using the addition, subtraction, multiplication, division, and remainder (modulo) operators in creating business rules.</span></span> <span data-ttu-id="99584-104">次の表に、算術演算子を示します。</span><span class="sxs-lookup"><span data-stu-id="99584-104">The following table describes the arithmetic operators.</span></span>  
  
|<span data-ttu-id="99584-105">算術演算子</span><span class="sxs-lookup"><span data-stu-id="99584-105">Arithmetic operator</span></span>|<span data-ttu-id="99584-106">Description</span><span class="sxs-lookup"><span data-stu-id="99584-106">Description</span></span>|  
|-------------------------|-----------------|  
|<span data-ttu-id="99584-107">**[追加]**</span><span class="sxs-lookup"><span data-stu-id="99584-107">**Add**</span></span>|<span data-ttu-id="99584-108">2 つの引数間で加算を行うための演算子を表します。</span><span class="sxs-lookup"><span data-stu-id="99584-108">Represents the addition operator (arg1 added to arg2).</span></span>|  
|<span data-ttu-id="99584-109">**減算**</span><span class="sxs-lookup"><span data-stu-id="99584-109">**Subtract**</span></span>|<span data-ttu-id="99584-110">2 つの引数間で減算を行うための演算子を表します。</span><span class="sxs-lookup"><span data-stu-id="99584-110">Represents the subtraction operator (arg1 subtracted from arg2).</span></span>|  
|<span data-ttu-id="99584-111">**乗算**</span><span class="sxs-lookup"><span data-stu-id="99584-111">**Multiply**</span></span>|<span data-ttu-id="99584-112">2 つの引数間で乗算を行うための演算子を表します。</span><span class="sxs-lookup"><span data-stu-id="99584-112">Represents the multiplication operator (arg1 multiplied by arg2).</span></span>|  
|<span data-ttu-id="99584-113">**Divide**</span><span class="sxs-lookup"><span data-stu-id="99584-113">**Divide**</span></span>|<span data-ttu-id="99584-114">2 つの引数間で除算を行うための演算子を表します。</span><span class="sxs-lookup"><span data-stu-id="99584-114">Represents the division operator (arg1 divided by arg2).</span></span>|  
|<span data-ttu-id="99584-115">**残りの部分**</span><span class="sxs-lookup"><span data-stu-id="99584-115">**Remainder**</span></span>|<span data-ttu-id="99584-116">2 つの引数間での除算の剰余の演算子を表します。</span><span class="sxs-lookup"><span data-stu-id="99584-116">Represents the remainder operator (arg1 modulo arg2).</span></span>|  
  
 <span data-ttu-id="99584-117">オペランドの型が異なる場合、短い方の型の数値が長い方の型に合わせて自動的に変換されます。</span><span class="sxs-lookup"><span data-stu-id="99584-117">When operands are of different types, automatic numeric promotion occurs with the smaller operand type being converted to the larger operand type.</span></span> <span data-ttu-id="99584-118">たとえば場合、**追加**の最初のオペランドに演算子が使用される**int**型との 2 番目のオペランド**長い**に最初のオペランドの型は型が変換されます**長い**実行する前に、**追加**操作します。</span><span class="sxs-lookup"><span data-stu-id="99584-118">For example, if the **Add** operator is used with the first operand of **int** type and the second operand of **long** type, the type of the first operand is converted to **long** before performing the **Add** operation.</span></span> <span data-ttu-id="99584-119">ルール エンジンでは、両方のオペランドの型を同一のものに変換できる場合は、同時変換もサポートしています。</span><span class="sxs-lookup"><span data-stu-id="99584-119">The rule engine also supports double promotion if both the operands can be promoted to a common type.</span></span> <span data-ttu-id="99584-120">たとえば場合、**追加**の最初のオペランドに演算子が使用される**int**型との 2 番目のオペランド**uint** する型、両方のオペランドの型を変換**長い**実行する前に、**追加**操作します。</span><span class="sxs-lookup"><span data-stu-id="99584-120">For example, if the **Add** operator is used with the first operand of **int** type and the second operand of **uint** type, the types of both operands are converted to **long** before performing the **Add** operation.</span></span>  
  
## <a name="to-use-a-logical-operator-in-a-business-rule"></a><span data-ttu-id="99584-121">ビジネス ルールで論理演算子を使用するには</span><span class="sxs-lookup"><span data-stu-id="99584-121">To use a logical operator in a business rule</span></span>  
 <span data-ttu-id="99584-122">ビジネス ルールで論理演算子を使用するには、次の手順に従います。</span><span class="sxs-lookup"><span data-stu-id="99584-122">Use the following procedure to use a logical operator in a business rule.</span></span>  
  
1.  <span data-ttu-id="99584-123">[ファクト エクスプ ローラー] ウィンドウ、**ボキャブラリ**タブです。</span><span class="sxs-lookup"><span data-stu-id="99584-123">In the Facts Explorer window, click the **Vocabularies** tab.</span></span>  
  
2.  <span data-ttu-id="99584-124">展開**ボキャブラリ**、展開**関数**、展開**バージョン 1.0 - 公開済み**、し、ドラッグ、**追加/削除/乗算/除算/剰余**条件ペイン/アクション ウィンドウにします。</span><span class="sxs-lookup"><span data-stu-id="99584-124">Expand **Vocabularies**, expand **Functions**, expand **Version 1.0 - Published**, and then drag the **Add/Subtract/Multiply/Divide/Remainder** to the Conditions pane/Actions pane.</span></span>  
  
3.  <span data-ttu-id="99584-125">左側および右側の演算子の値を指定します。</span><span class="sxs-lookup"><span data-stu-id="99584-125">Specify values for left and right operators.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="99584-126">参照</span><span class="sxs-lookup"><span data-stu-id="99584-126">See Also</span></span>  
 [<span data-ttu-id="99584-127">論理演算子</span><span class="sxs-lookup"><span data-stu-id="99584-127">Logical Operators</span></span>](../core/logical-operators.md)