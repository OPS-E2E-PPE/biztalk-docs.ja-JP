---
title: 受信メッセージ図形にフィルターを使用して |Microsoft ドキュメント
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
caps.latest.revision: ''
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: 1434e9704e073cfef1503ef550409e6d6414bb7c
ms.sourcegitcommit: 8418b1a8f38b7f56979cd6e203f0b591e2f40fe1
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 03/23/2018
---
# <a name="using-filters-with-the-receive-message-shape"></a><span data-ttu-id="92854-102">受信メッセージ図形にフィルターを使用します。</span><span class="sxs-lookup"><span data-stu-id="92854-102">Using Filters With the Receive Message Shape</span></span>
<span data-ttu-id="92854-103">フィルター式は、"アクティブ化" プロパティに対して値 True を指定するオーケストレーションの受信図形に適用できる、オプションのパラメーターです。</span><span class="sxs-lookup"><span data-stu-id="92854-103">A filter expression is an optional parameter that can be applied to an orchestration receive shape that specifies a value of True for the Activate property.</span></span> <span data-ttu-id="92854-104">フィルター式が指定された場合、受信メッセージがフィルター式で指定された条件に一致する場合にのみ、オーケストレーションがアクティブ化されます。</span><span class="sxs-lookup"><span data-stu-id="92854-104">If a filter expression is specified then the orchestration will only be activated if an incoming message matches the condition(s) specified in the filter expression.</span></span> <span data-ttu-id="92854-105">フィルター式が指定されていない場合は、オーケストレーションがサブスクライブする受信メッセージによって、オーケストレーションがアクティブ化されます。</span><span class="sxs-lookup"><span data-stu-id="92854-105">If no filter expression is specified then any incoming message that the orchestration subscribes to will activate the orchestration.</span></span>  
  
 <span data-ttu-id="92854-106">フィルター式を作成するには、式の左側にある受信メッセージのプロパティを式の右側にある定数と比較します。</span><span class="sxs-lookup"><span data-stu-id="92854-106">To create a filter expression, you compare a property of an incoming message on the left side of the expression with a constant on the right side of the expression.</span></span> <span data-ttu-id="92854-107">複数の式に AND および OR 演算子を適用することによって、複合式を作成することもできます。</span><span class="sxs-lookup"><span data-stu-id="92854-107">You can also create compound expressions by applying the AND and OR operators to two or more expressions.</span></span> <span data-ttu-id="92854-108">フィルター式を空のままにすることもできます。この場合、すべてのメッセージが受け入れられます。</span><span class="sxs-lookup"><span data-stu-id="92854-108">You can also leave blank the filter expression, in which case all messages will be accepted.</span></span>  
  
 <span data-ttu-id="92854-109">フィルター式は以下のようになります。</span><span class="sxs-lookup"><span data-stu-id="92854-109">A filter expression might look like the following:</span></span>  
  
```  
InvoiceSchema.Quantity >= 1000  
```  
  
 <span data-ttu-id="92854-110">この例では、受信メッセージはオーケストレーションに提示されます。</span><span class="sxs-lookup"><span data-stu-id="92854-110">In this example, an incoming message is presented to the orchestration.</span></span> <span data-ttu-id="92854-111">オーケストレーションがアクティブ化 **受信** 図形 (、 **アクティブ化** にプロパティが設定されている **True** 、オーケストレーションを実行すると、特定のメッセージを受信できるように) に適用される前のフィルター式を使用します。</span><span class="sxs-lookup"><span data-stu-id="92854-111">The orchestration has an activation **Receive** shape (the **Activation** property is set to **True** so that receipt of a certain message will cause the orchestration to be run) with the preceding filter expression applied to it.</span></span> <span data-ttu-id="92854-112">名前空間に Quantity という名前のプロパティを持つ受信メッセージが期待どおり **InvoiceSchema**します。</span><span class="sxs-lookup"><span data-stu-id="92854-112">The incoming message is expected to have property called Quantity in the namespace **InvoiceSchema**.</span></span> <span data-ttu-id="92854-113">このオーケストレーションは、1000 以上のアイテムに対する請求書のみ受け付けるため、ランタイム エンジンは実行する前に受信メッセージを確認します。</span><span class="sxs-lookup"><span data-stu-id="92854-113">The orchestration accepts only invoices for 1000 or more items, so the runtime engine checks the incoming message before it runs.</span></span>  
  
 <span data-ttu-id="92854-114">次の表に、フィルター式で使用可能な演算子を示します。</span><span class="sxs-lookup"><span data-stu-id="92854-114">The following table shows operators that you can use in filter expressions.</span></span>  
  
|<span data-ttu-id="92854-115">演算子</span><span class="sxs-lookup"><span data-stu-id="92854-115">Operator</span></span>|<span data-ttu-id="92854-116">Description</span><span class="sxs-lookup"><span data-stu-id="92854-116">Description</span></span>|<span data-ttu-id="92854-117">例</span><span class="sxs-lookup"><span data-stu-id="92854-117">Example</span></span>|  
|--------------|-----------------|-------------|  
|==|<span data-ttu-id="92854-118">等しい</span><span class="sxs-lookup"><span data-stu-id="92854-118">equal to</span></span>|<span data-ttu-id="92854-119">ReqMsg(Total) == 100</span><span class="sxs-lookup"><span data-stu-id="92854-119">ReqMsg(Total) == 100</span></span>|  
|<span data-ttu-id="92854-120">!=</span><span class="sxs-lookup"><span data-stu-id="92854-120">!=</span></span>|<span data-ttu-id="92854-121">等しくないです。</span><span class="sxs-lookup"><span data-stu-id="92854-121">not equal to</span></span>|<span data-ttu-id="92854-122">ReqMsg(Total) != 100</span><span class="sxs-lookup"><span data-stu-id="92854-122">ReqMsg(Total) != 100</span></span>|  
|<|<span data-ttu-id="92854-123">小さい</span><span class="sxs-lookup"><span data-stu-id="92854-123">less than</span></span>|<span data-ttu-id="92854-124">ReqMsg(Total) \< 100</span><span class="sxs-lookup"><span data-stu-id="92854-124">ReqMsg(Total) \< 100</span></span>|  
|>|<span data-ttu-id="92854-125">大きい</span><span class="sxs-lookup"><span data-stu-id="92854-125">greater than</span></span>|<span data-ttu-id="92854-126">ReqMsg(Total) > 100</span><span class="sxs-lookup"><span data-stu-id="92854-126">ReqMsg(Total) > 100</span></span>|  
|<=|<span data-ttu-id="92854-127">以下に</span><span class="sxs-lookup"><span data-stu-id="92854-127">less than or equal to</span></span>|<span data-ttu-id="92854-128">ReqMsg(Total) \<100 を =</span><span class="sxs-lookup"><span data-stu-id="92854-128">ReqMsg(Total) \<= 100</span></span>|  
|>=|<span data-ttu-id="92854-129">大きいまたは等しい</span><span class="sxs-lookup"><span data-stu-id="92854-129">greater than or equal to</span></span>|<span data-ttu-id="92854-130">ReqMsg(Total) > = 100</span><span class="sxs-lookup"><span data-stu-id="92854-130">ReqMsg(Total) >= 100</span></span>|  
|<span data-ttu-id="92854-131">存在する</span><span class="sxs-lookup"><span data-stu-id="92854-131">exists</span></span>|<span data-ttu-id="92854-132">存在する</span><span class="sxs-lookup"><span data-stu-id="92854-132">exists</span></span>|<span data-ttu-id="92854-133">ReqMsg(Description) exists</span><span class="sxs-lookup"><span data-stu-id="92854-133">ReqMsg(Description) exists</span></span>|  
  
> [!NOTE]
>  <span data-ttu-id="92854-134">フィルター式の文字列値が次に例を引用符で囲まれた: reqmsg (description) =「注文書の状態」です。</span><span class="sxs-lookup"><span data-stu-id="92854-134">String values in filter expressions are enclosed in quotation marks, for example: ReqMsg(Description) = "Purchase Order Status".</span></span> <span data-ttu-id="92854-135">フィルター式では文字値を使用できません。</span><span class="sxs-lookup"><span data-stu-id="92854-135">You cannot use a character value in a filter expression.</span></span>  
  
> [!NOTE]
>  <span data-ttu-id="92854-136">アクティブ化受信が直接バインド ポートに関連付けられており、その後、フィルターでテストされたプロパティに対する同じ値を持つ同じ種類のメッセージを送信する場合、無限ループが作成されます。</span><span class="sxs-lookup"><span data-stu-id="92854-136">If your activate receive is associated with a direct-bound port, and you subsequently send a message of the same type with the same value for the property tested in your filter, you will create an infinite loop.</span></span> <span data-ttu-id="92854-137">メッセージはメッセージ ボックスに送られますが、フィルター条件に一致するため、そこで再度取得されます。</span><span class="sxs-lookup"><span data-stu-id="92854-137">The message will go to the MessageBox, where it will be picked up again because it matches the filter criteria.</span></span> <span data-ttu-id="92854-138">これを避けるには、別のプロパティに対してフィルター処理を行い、別の種類のメッセージを送信するか、同じ種類のメッセージを送信する前にプロパティの値を変更する必要があります。</span><span class="sxs-lookup"><span data-stu-id="92854-138">To avoid this, you should either filter on a different property, send a message of a different type, or be sure to change the value of the property before sending out a message of the same type.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="92854-139">参照</span><span class="sxs-lookup"><span data-stu-id="92854-139">See Also</span></span>  
 <span data-ttu-id="92854-140">[受信図形を構成する方法](../core/how-to-configure-the-receive-shape.md) </span><span class="sxs-lookup"><span data-stu-id="92854-140">[How to Configure the Receive Shape](../core/how-to-configure-the-receive-shape.md) </span></span>  
 <span data-ttu-id="92854-141">[オーケストレーションでの相関関係の使用](../core/using-correlations-in-orchestrations.md) </span><span class="sxs-lookup"><span data-stu-id="92854-141">[Using Correlations in Orchestrations](../core/using-correlations-in-orchestrations.md) </span></span>  
 <span data-ttu-id="92854-142">[識別フィールドおよびプロパティ フィールドの使用](../core/using-distinguished-fields-and-property-fields.md) </span><span class="sxs-lookup"><span data-stu-id="92854-142">[Using Distinguished Fields and Property Fields](../core/using-distinguished-fields-and-property-fields.md) </span></span>  
 [<span data-ttu-id="92854-143">オーケストレーションでメッセージの使用</span><span class="sxs-lookup"><span data-stu-id="92854-143">Using Messages in Orchestrations</span></span>](../core/using-messages-in-orchestrations.md)