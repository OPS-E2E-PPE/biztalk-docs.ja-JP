---
title: フィルターと受信メッセージ図形の使用 |Microsoft Docs
ms.custom: ''
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: ''
ms.suite: ''
ms.tgt_pltfrm: ''
ms.topic: article
helpviewer_keywords:
- filters, receive messages
- messages, filters
ms.assetid: 5310039b-6719-4971-933a-2da0573fb5e7
caps.latest.revision: 9
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: 58c0ed34645fc7b576a76092c676d4eb4c390020
ms.sourcegitcommit: 381e83d43796a345488d54b3f7413e11d56ad7be
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 05/07/2019
ms.locfileid: "65246420"
---
# <a name="using-filters-with-the-receive-message-shape"></a><span data-ttu-id="3a17e-102">受信メッセージ図形にフィルターを使用します。</span><span class="sxs-lookup"><span data-stu-id="3a17e-102">Using Filters With the Receive Message Shape</span></span>
<span data-ttu-id="3a17e-103">フィルター式は、受信のアクティブ化プロパティの値を指定する図形をオーケストレーションに適用できるオプションのパラメーターです。</span><span class="sxs-lookup"><span data-stu-id="3a17e-103">A filter expression is an optional parameter that can be applied to an orchestration receive shape that specifies a value of True for the Activate property.</span></span> <span data-ttu-id="3a17e-104">フィルター式が指定されている場合、受信メッセージがフィルター式で指定された条件と一致する場合とし、オーケストレーションはアクティブのみです。</span><span class="sxs-lookup"><span data-stu-id="3a17e-104">If a filter expression is specified then the orchestration will only be activated if an incoming message matches the condition(s) specified in the filter expression.</span></span> <span data-ttu-id="3a17e-105">フィルター式が指定されていない場合、オーケストレーションがサブスクライブしているすべての受信メッセージはオーケストレーション アクティブ化されます。</span><span class="sxs-lookup"><span data-stu-id="3a17e-105">If no filter expression is specified then any incoming message that the orchestration subscribes to will activate the orchestration.</span></span>  
  
 <span data-ttu-id="3a17e-106">フィルター式を作成するには、式の右側にある定数式の左側にある着信メッセージのプロパティを比較します。</span><span class="sxs-lookup"><span data-stu-id="3a17e-106">To create a filter expression, you compare a property of an incoming message on the left side of the expression with a constant on the right side of the expression.</span></span> <span data-ttu-id="3a17e-107">AND を適用することで、複合式を作成することもできます。 および OR 演算子を 2 つまたは複数の式。</span><span class="sxs-lookup"><span data-stu-id="3a17e-107">You can also create compound expressions by applying the AND and OR operators to two or more expressions.</span></span> <span data-ttu-id="3a17e-108">できますも空白のままに、フィルター式では、すべてのメッセージを受け入れられる場合。</span><span class="sxs-lookup"><span data-stu-id="3a17e-108">You can also leave blank the filter expression, in which case all messages will be accepted.</span></span>  
  
 <span data-ttu-id="3a17e-109">フィルター式は、次のようになります。</span><span class="sxs-lookup"><span data-stu-id="3a17e-109">A filter expression might look like the following:</span></span>  
  
```  
InvoiceSchema.Quantity >= 1000  
```  
  
 <span data-ttu-id="3a17e-110">この例では、オーケストレーションに受信メッセージが表示されます。</span><span class="sxs-lookup"><span data-stu-id="3a17e-110">In this example, an incoming message is presented to the orchestration.</span></span> <span data-ttu-id="3a17e-111">オーケストレーションがアクティブ化**受信**図形 (、**アクティベーション**プロパティに設定されて**True**できるように、特定のメッセージの受信、オーケストレーションを実行すると、) を適用前のフィルター式で。</span><span class="sxs-lookup"><span data-stu-id="3a17e-111">The orchestration has an activation **Receive** shape (the **Activation** property is set to **True** so that receipt of a certain message will cause the orchestration to be run) with the preceding filter expression applied to it.</span></span> <span data-ttu-id="3a17e-112">名前空間に Quantity という名前のプロパティを持つ受信メッセージが期待どおり**InvoiceSchema**します。</span><span class="sxs-lookup"><span data-stu-id="3a17e-112">The incoming message is expected to have property called Quantity in the namespace **InvoiceSchema**.</span></span> <span data-ttu-id="3a17e-113">オーケストレーションは、実行前に、ランタイム エンジンが受信メッセージをチェックしますので 1000 以上の項目に対する請求書のみを受け入れます。</span><span class="sxs-lookup"><span data-stu-id="3a17e-113">The orchestration accepts only invoices for 1000 or more items, so the runtime engine checks the incoming message before it runs.</span></span>  
  
 <span data-ttu-id="3a17e-114">次の表では、フィルター式で使用できる演算子を示します。</span><span class="sxs-lookup"><span data-stu-id="3a17e-114">The following table shows operators that you can use in filter expressions.</span></span>  
  
|<span data-ttu-id="3a17e-115">演算子</span><span class="sxs-lookup"><span data-stu-id="3a17e-115">Operator</span></span>|<span data-ttu-id="3a17e-116">説明</span><span class="sxs-lookup"><span data-stu-id="3a17e-116">Description</span></span>|<span data-ttu-id="3a17e-117">例</span><span class="sxs-lookup"><span data-stu-id="3a17e-117">Example</span></span>|  
|--------------|-----------------|-------------|  
|==|<span data-ttu-id="3a17e-118">等しい</span><span class="sxs-lookup"><span data-stu-id="3a17e-118">equal to</span></span>|<span data-ttu-id="3a17e-119">ReqMsg(Total) == 100</span><span class="sxs-lookup"><span data-stu-id="3a17e-119">ReqMsg(Total) == 100</span></span>|  
|<span data-ttu-id="3a17e-120">!=</span><span class="sxs-lookup"><span data-stu-id="3a17e-120">!=</span></span>|<span data-ttu-id="3a17e-121">等しくないです。</span><span class="sxs-lookup"><span data-stu-id="3a17e-121">not equal to</span></span>|<span data-ttu-id="3a17e-122">ReqMsg(Total) != 100</span><span class="sxs-lookup"><span data-stu-id="3a17e-122">ReqMsg(Total) != 100</span></span>|  
|<|<span data-ttu-id="3a17e-123">小さい</span><span class="sxs-lookup"><span data-stu-id="3a17e-123">less than</span></span>|<span data-ttu-id="3a17e-124">ReqMsg(Total) \< 100</span><span class="sxs-lookup"><span data-stu-id="3a17e-124">ReqMsg(Total) \< 100</span></span>|  
|>|<span data-ttu-id="3a17e-125">大きい</span><span class="sxs-lookup"><span data-stu-id="3a17e-125">greater than</span></span>|<span data-ttu-id="3a17e-126">ReqMsg(Total) > 100</span><span class="sxs-lookup"><span data-stu-id="3a17e-126">ReqMsg(Total) > 100</span></span>|  
|<=|<span data-ttu-id="3a17e-127">等しいまたはそれよりも小さい</span><span class="sxs-lookup"><span data-stu-id="3a17e-127">less than or equal to</span></span>|<span data-ttu-id="3a17e-128">ReqMsg(Total) \<= 100</span><span class="sxs-lookup"><span data-stu-id="3a17e-128">ReqMsg(Total) \<= 100</span></span>|  
|>=|<span data-ttu-id="3a17e-129">大きいまたは等しい</span><span class="sxs-lookup"><span data-stu-id="3a17e-129">greater than or equal to</span></span>|<span data-ttu-id="3a17e-130">ReqMsg(Total) >= 100</span><span class="sxs-lookup"><span data-stu-id="3a17e-130">ReqMsg(Total) >= 100</span></span>|  
|<span data-ttu-id="3a17e-131">存在します。</span><span class="sxs-lookup"><span data-stu-id="3a17e-131">exists</span></span>|<span data-ttu-id="3a17e-132">存在します。</span><span class="sxs-lookup"><span data-stu-id="3a17e-132">exists</span></span>|<span data-ttu-id="3a17e-133">ReqMsg(Description) exists</span><span class="sxs-lookup"><span data-stu-id="3a17e-133">ReqMsg(Description) exists</span></span>|  
  
> [!NOTE]
>  <span data-ttu-id="3a17e-134">フィルター式の文字列値は、たとえば、引用符で囲まれました。Reqmsg (description) =「発注書のステータス」。</span><span class="sxs-lookup"><span data-stu-id="3a17e-134">String values in filter expressions are enclosed in quotation marks, for example: ReqMsg(Description) = "Purchase Order Status".</span></span> <span data-ttu-id="3a17e-135">フィルター式の文字の値を使用することはできません。</span><span class="sxs-lookup"><span data-stu-id="3a17e-135">You cannot use a character value in a filter expression.</span></span>  
  
> [!NOTE]
>  <span data-ttu-id="3a17e-136">アクティブ化受信である場合は、直接バインド ポートに関連付けられて、その後、フィルターでテストされたプロパティの値が同じで、同じ型のメッセージを送信しては、無限ループを作成します。</span><span class="sxs-lookup"><span data-stu-id="3a17e-136">If your activate receive is associated with a direct-bound port, and you subsequently send a message of the same type with the same value for the property tested in your filter, you will create an infinite loop.</span></span> <span data-ttu-id="3a17e-137">メッセージは、場所は再度選択、フィルター条件に一致するため、メッセージ ボックスに移動します。</span><span class="sxs-lookup"><span data-stu-id="3a17e-137">The message will go to the MessageBox, where it will be picked up again because it matches the filter criteria.</span></span> <span data-ttu-id="3a17e-138">これを回避するには、する必要があります別のプロパティでフィルター処理、別の種類のメッセージを送信するか、同じ種類のメッセージを送信する前に、プロパティの値を変更してください。</span><span class="sxs-lookup"><span data-stu-id="3a17e-138">To avoid this, you should either filter on a different property, send a message of a different type, or be sure to change the value of the property before sending out a message of the same type.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="3a17e-139">参照</span><span class="sxs-lookup"><span data-stu-id="3a17e-139">See Also</span></span>  
 <span data-ttu-id="3a17e-140">[受信図形を構成する方法](../core/how-to-configure-the-receive-shape.md) </span><span class="sxs-lookup"><span data-stu-id="3a17e-140">[How to Configure the Receive Shape](../core/how-to-configure-the-receive-shape.md) </span></span>  
 <span data-ttu-id="3a17e-141">[オーケストレーションでの相関関係の使用](../core/using-correlations-in-orchestrations.md) </span><span class="sxs-lookup"><span data-stu-id="3a17e-141">[Using Correlations in Orchestrations](../core/using-correlations-in-orchestrations.md) </span></span>  
 <span data-ttu-id="3a17e-142">[識別フィールドとプロパティ フィールドの使用](../core/using-distinguished-fields-and-property-fields.md) </span><span class="sxs-lookup"><span data-stu-id="3a17e-142">[Using Distinguished Fields and Property Fields](../core/using-distinguished-fields-and-property-fields.md) </span></span>  
 [<span data-ttu-id="3a17e-143">オーケストレーションでのメッセージの使用</span><span class="sxs-lookup"><span data-stu-id="3a17e-143">Using Messages in Orchestrations</span></span>](../core/using-messages-in-orchestrations.md)