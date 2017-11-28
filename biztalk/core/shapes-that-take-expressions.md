---
title: "式を使用する図形 |Microsoft ドキュメント"
ms.custom: 
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: 
ms.suite: 
ms.tgt_pltfrm: 
ms.topic: article
helpviewer_keywords:
- Expression Editor, shapes
- Decide shape [Orchestration Designer], expressions
- Message Assignment shape [Orchestration Designer], expressions
- Filter Expression property
- Listen shape [Orchestration Designer], expressions
- Delay shape [Orchestration Designer], expressions
- shapes, expressions
- Receive shape [Orchestration Designer], expressions
- Loop shape [Orchestration Designer], expressions
- Rule shape [Orchestration Designer]
ms.assetid: 0d27f711-ff7c-422b-b231-aa3c9a42ed0c
caps.latest.revision: "9"
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: 3e78ada2c69205a0201c4bae9f3c7fa5b0656fa7
ms.sourcegitcommit: cb908c540d8f1a692d01dc8f313e16cb4b4e696d
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 09/20/2017
---
# <a name="shapes-that-take-expressions"></a><span data-ttu-id="0be28-102">式を使用する図形</span><span class="sxs-lookup"><span data-stu-id="0be28-102">Shapes that Take Expressions</span></span>
<span data-ttu-id="0be28-103">オーケストレーション デザイナーで、複数の図形を含む**判断**と**ループ**、分岐を制御するルールを作成、ブール式を使用します。</span><span class="sxs-lookup"><span data-stu-id="0be28-103">Several shapes in Orchestration Designer, including **Decide** and **Loop**, use Boolean expressions to form rules that control branching.</span></span> <span data-ttu-id="0be28-104">他の図形は、それぞれ他の目的で式を使用します。</span><span class="sxs-lookup"><span data-stu-id="0be28-104">Other shapes use expressions for other purposes.</span></span> <span data-ttu-id="0be28-105">BizTalk 式エディターを使用して、これらの図形の式を作成または編集できます。</span><span class="sxs-lookup"><span data-stu-id="0be28-105">You can create or edit an expression for these shapes by using BizTalk Expression Editor.</span></span>  
  
 <span data-ttu-id="0be28-106">次の表は、オーケストレーション デザイナーで式を使用する図形とそれらの式に対して有効なデータ型を示しています。</span><span class="sxs-lookup"><span data-stu-id="0be28-106">The following table summarizes the shapes that use expressions in Orchestration Designer and lists the data types that are valid for those expressions.</span></span>  
  
|<span data-ttu-id="0be28-107">図形</span><span class="sxs-lookup"><span data-stu-id="0be28-107">Shape</span></span>|<span data-ttu-id="0be28-108">式の使用方法の説明</span><span class="sxs-lookup"><span data-stu-id="0be28-108">Description of expression use</span></span>|<span data-ttu-id="0be28-109">有効な式のデータ型</span><span class="sxs-lookup"><span data-stu-id="0be28-109">Valid expression data types</span></span>|  
|-----------|-----------------------------------|---------------------------------|  
|<span data-ttu-id="0be28-110">**決定**</span><span class="sxs-lookup"><span data-stu-id="0be28-110">**Decide**</span></span>|<span data-ttu-id="0be28-111">**決定**図形を含める**ルール**図形で、ブール式を使用します。</span><span class="sxs-lookup"><span data-stu-id="0be28-111">**Decide** shapes contain **Rule** shapes, which use Boolean expressions.</span></span>|<span data-ttu-id="0be28-112">ブール値</span><span class="sxs-lookup"><span data-stu-id="0be28-112">Boolean</span></span>|  
|<span data-ttu-id="0be28-113">**受信**</span><span class="sxs-lookup"><span data-stu-id="0be28-113">**Receive**</span></span>|<span data-ttu-id="0be28-114">**受信**、"アクティブ化"プロパティが設定された場合は True。 使用する図形、**フィルター式**受信メッセージをフィルター選択するプロパティです。</span><span class="sxs-lookup"><span data-stu-id="0be28-114">**Receive** shapes that have the Activate property set to True use the **Filter Expression** property to filter incoming messages.</span></span> <span data-ttu-id="0be28-115">このプロパティの式は、ブール値として評価される必要があります。この値は、受信メッセージを受け付けるかどうかを決定します。</span><span class="sxs-lookup"><span data-stu-id="0be28-115">The expression in this property must evaluate to a Boolean, whose value determines whether or not to accept an incoming message.</span></span><br /><br /> <span data-ttu-id="0be28-116">**フィルター式** ダイアログ ボックスを使用してフィルター式を作成します。</span><span class="sxs-lookup"><span data-stu-id="0be28-116">The **Filter Expression** dialog box is used to create filter expressions.</span></span>|<span data-ttu-id="0be28-117">ブール値</span><span class="sxs-lookup"><span data-stu-id="0be28-117">Boolean</span></span>|  
|<span data-ttu-id="0be28-118">**ループ**</span><span class="sxs-lookup"><span data-stu-id="0be28-118">**Loop**</span></span>|<span data-ttu-id="0be28-119">A**ループ**図形が必要です、**ルール**図形で、さらに、ブール式を含める必要があります。</span><span class="sxs-lookup"><span data-stu-id="0be28-119">A **Loop** shape requires a **Rule** shape, which in turn must contain a Boolean expression.</span></span>|<span data-ttu-id="0be28-120">ブール値</span><span class="sxs-lookup"><span data-stu-id="0be28-120">Boolean</span></span>|  
|<span data-ttu-id="0be28-121">**Rule**</span><span class="sxs-lookup"><span data-stu-id="0be28-121">**Rule**</span></span>|<span data-ttu-id="0be28-122">**ルール**(「分岐」図形として処理領域に表示されます) 図形は、ブール式が含まれており、その他の (複雑な) 図形内で分岐を制御するために使用する単純な図形です。</span><span class="sxs-lookup"><span data-stu-id="0be28-122">**Rule** shapes (displayed on the Process Area as "branch" shapes) are simple shapes that contain Boolean expressions and are used within other (complex) shapes to govern branching.</span></span>|<span data-ttu-id="0be28-123">ブール値</span><span class="sxs-lookup"><span data-stu-id="0be28-123">Boolean</span></span>|  
|<span data-ttu-id="0be28-124">**リッスン**</span><span class="sxs-lookup"><span data-stu-id="0be28-124">**Listen**</span></span>|<span data-ttu-id="0be28-125">各分岐は**リッスン**図形が含まれているには、少なくともいずれか、**受信**のみのフィルター式はブール式を使用する図形 (のエントリを参照してください**受信**)、、または**遅延**図形を使用して、 **System.DateTime**オブジェクトまたは**System.TimeSpan**オブジェクト。</span><span class="sxs-lookup"><span data-stu-id="0be28-125">Each branch of a **Listen** shape contains, at a minimum, either a **Receive** shape, which uses a Boolean expression only for filter expressions (see the entry for **Receive**), or a **Delay** shape, which uses a **System.DateTime** object or **System.TimeSpan** object.</span></span>|<span data-ttu-id="0be28-126">ブール値、System.DateTime、System.TimeSpan</span><span class="sxs-lookup"><span data-stu-id="0be28-126">Boolean, System.DateTime, System.TimeSpan</span></span>|  
|<span data-ttu-id="0be28-127">**遅延**</span><span class="sxs-lookup"><span data-stu-id="0be28-127">**Delay**</span></span>|<span data-ttu-id="0be28-128">使用される式、**遅延**に図形を評価する必要があります、 **System.DateTime** 、期限のオブジェクトまたは**System.TimeSpan**期間を表すためのオブジェクト。</span><span class="sxs-lookup"><span data-stu-id="0be28-128">The expression used in a **Delay** shape must evaluate to a **System.DateTime** object, to express a deadline, or a **System.TimeSpan** object, to express duration.</span></span>|<span data-ttu-id="0be28-129">System.DateTime、System.TimeSpan</span><span class="sxs-lookup"><span data-stu-id="0be28-129">System.DateTime, System.TimeSpan</span></span>|  
|<span data-ttu-id="0be28-130">**メッセージの割り当て**</span><span class="sxs-lookup"><span data-stu-id="0be28-130">**Message Assignment**</span></span>|<span data-ttu-id="0be28-131">内の式、**メッセージの割り当て**図形がメッセージに値を割り当てます。</span><span class="sxs-lookup"><span data-stu-id="0be28-131">The expression in a **Message Assignment** shape assigns a value to a message.</span></span> <span data-ttu-id="0be28-132">割り当てられる値は、通常はメッセージですが、任意のデータ型も使用できます。</span><span class="sxs-lookup"><span data-stu-id="0be28-132">The value assigned can be of any type, though typically a message is assigned.</span></span>|<span data-ttu-id="0be28-133">Any</span><span class="sxs-lookup"><span data-stu-id="0be28-133">Any</span></span>|  
|<span data-ttu-id="0be28-134">**[式]**</span><span class="sxs-lookup"><span data-stu-id="0be28-134">**Expression**</span></span>|<span data-ttu-id="0be28-135">**式**図形では、オーケストレーションに任意の式を入力することができます。</span><span class="sxs-lookup"><span data-stu-id="0be28-135">The **Expression** shape enables you to enter any expression you choose in your orchestration.</span></span> <span data-ttu-id="0be28-136">たとえば、外部プログラムに対して .NET 呼び出しを行ったり、オーケストレーション変数の値を操作できます。</span><span class="sxs-lookup"><span data-stu-id="0be28-136">For example, you can make a .NET call to run an external program, or simply manipulate the values of your orchestration variables.</span></span>|<span data-ttu-id="0be28-137">Any</span><span class="sxs-lookup"><span data-stu-id="0be28-137">Any</span></span>|  
  
## <a name="in-this-section"></a><span data-ttu-id="0be28-138">このセクションの内容</span><span class="sxs-lookup"><span data-stu-id="0be28-138">In This Section</span></span>  
 [<span data-ttu-id="0be28-139">式図形を使用する方法</span><span class="sxs-lookup"><span data-stu-id="0be28-139">How to Use Expression Shape</span></span>](../core/how-to-use-expression-shape.md)  
  
## <a name="see-also"></a><span data-ttu-id="0be28-140">参照</span><span class="sxs-lookup"><span data-stu-id="0be28-140">See Also</span></span>  
 <span data-ttu-id="0be28-141">[式の要件と制限](../core/requirements-and-limitations-for-expressions.md) </span><span class="sxs-lookup"><span data-stu-id="0be28-141">[Requirements and Limitations for Expressions](../core/requirements-and-limitations-for-expressions.md) </span></span>  
 <span data-ttu-id="0be28-142">[メッセージの構築](../core/constructing-messages.md) </span><span class="sxs-lookup"><span data-stu-id="0be28-142">[Constructing Messages](../core/constructing-messages.md) </span></span>  
 [<span data-ttu-id="0be28-143">フロー制御図形を構成します。</span><span class="sxs-lookup"><span data-stu-id="0be28-143">Configuring Flow Control Shapes</span></span>](../core/configuring-flow-control-shapes.md)