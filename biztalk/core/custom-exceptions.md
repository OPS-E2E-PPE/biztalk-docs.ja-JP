---
title: カスタム例外 |Microsoft ドキュメント
ms.custom: ''
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: ''
ms.suite: ''
ms.tgt_pltfrm: ''
ms.topic: article
helpviewer_keywords:
- process management solution tutorial, compensation blocks
- compensation blocks, process management solutions
- process management solution tutorial, custom exceptions
- Terminate shape [Orchestration Designer], called orchestrations
- process management solution tutorial, errors
ms.assetid: 0c923303-82ad-4a20-9c7c-5e38c477993a
caps.latest.revision: 14
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: bfead2aadc237d27e0fb8ed28a776dd1e4f5c6f6
ms.sourcegitcommit: cb908c540d8f1a692d01dc8f313e16cb4b4e696d
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 09/20/2017
ms.locfileid: "22240138"
---
# <a name="custom-exceptions"></a><span data-ttu-id="851a2-102">カスタム例外</span><span class="sxs-lookup"><span data-stu-id="851a2-102">Custom Exceptions</span></span>
<span data-ttu-id="851a2-103">回復できないエラーが発生すると、ビジネス プロセス管理ソリューションは、例外ハンドラとカスタム例外を組み合わせて使用します。</span><span class="sxs-lookup"><span data-stu-id="851a2-103">For situations where there is an unrecoverable error, the Business Process Management solution uses a combination of exception handlers and custom exceptions.</span></span>  
  
## <a name="handling-exceptions"></a><span data-ttu-id="851a2-104">例外の処理</span><span class="sxs-lookup"><span data-stu-id="851a2-104">Handling Exceptions</span></span>  
 <span data-ttu-id="851a2-105">使用するのではなく**Terminate**呼び出されたオーケストレーションに図形をルート オーケストレーションで処理される例外をスローする方式を使用することができます。</span><span class="sxs-lookup"><span data-stu-id="851a2-105">Rather than using **Terminate** shapes in called orchestrations you can use the pattern of throwing exceptions that are handled by the root orchestration.</span></span> <span data-ttu-id="851a2-106">これにより、最も強力なコンテキストのオーケストレーションで例外処理を判断できます。</span><span class="sxs-lookup"><span data-stu-id="851a2-106">This allows the orchestration with the widest knowledge of context to make the decision about handling the exception.</span></span> <span data-ttu-id="851a2-107">下位のオーケストレーションがカスタム例外をスローすると、ルート オーケストレーションの詳細な情報と通信できます。</span><span class="sxs-lookup"><span data-stu-id="851a2-107">Having the subordinate orchestrations throw custom exceptions enables you to communicate more specific information to the root orchestration.</span></span>  
  
 <span data-ttu-id="851a2-108">ビジネス プロセス管理ソリューションは、この方式に従います。</span><span class="sxs-lookup"><span data-stu-id="851a2-108">The business process management solution follows this pattern.</span></span> <span data-ttu-id="851a2-109">次の 4 つのルートがあるか、ソリューションのオーケストレーションが、呼び出さ: **OrderBroker**、 **OrderManager**、 **CableOrder1**、および**CableOrder2**.</span><span class="sxs-lookup"><span data-stu-id="851a2-109">There are four root, or uncalled, orchestrations in the solution: **OrderBroker**, **OrderManager**, **CableOrder1**, and **CableOrder2**.</span></span> <span data-ttu-id="851a2-110">3 つのルート オーケストレーションを受け取り、カスタム例外を処理します。 **OrderManager**、 **CableOrder1**、および**CableOrder2**です。</span><span class="sxs-lookup"><span data-stu-id="851a2-110">Three of the root orchestrations receive and handle custom exceptions: **OrderManager**, **CableOrder1**, and **CableOrder2**.</span></span>  
  
 <span data-ttu-id="851a2-111">ルート オーケストレーションの一部を使用、 **Terminate**図形と、 **Terminate**図形がオーケストレーションの通常の終了ポイントの直前に表示されます。</span><span class="sxs-lookup"><span data-stu-id="851a2-111">Note that some of the root orchestrations use the **Terminate** shape and that the **Terminate** shape appears just before the normal end point of the orchestration.</span></span> <span data-ttu-id="851a2-112">オーケストレーションが現在も使用して、 **Terminate**終了すると、オーケストレーションが記録するようではなく完了したが、エラー メッセージ、エラーが発生した場合の図形です。</span><span class="sxs-lookup"><span data-stu-id="851a2-112">The orchestration still uses the **Terminate** shape in case of an error so that the orchestration is recorded as terminated, rather than as completed but with an error message.</span></span> <span data-ttu-id="851a2-113">これにより、このソリューションは、エラーの記録に加えて、失敗したインスタンスを簡単に追跡できます。</span><span class="sxs-lookup"><span data-stu-id="851a2-113">This allows the solution to track failed instances easily in addition to recording the error.</span></span>  
  
 <span data-ttu-id="851a2-114">詳細については、 **Terminate**図形は、「[終了図形を構成する方法](../core/how-to-configure-the-terminate-shape.md)です。</span><span class="sxs-lookup"><span data-stu-id="851a2-114">For more information about the **Terminate** shape, see [How to Configure the Terminate Shape](../core/how-to-configure-the-terminate-shape.md).</span></span> <span data-ttu-id="851a2-115">詳細については、 **ThrowException**図形は、「[例外のスロー図形を構成する方法](../core/how-to-configure-the-throw-exception-shape.md)です。</span><span class="sxs-lookup"><span data-stu-id="851a2-115">For more information about the **ThrowException** shape, see [How to Configure the Throw Exception Shape](../core/how-to-configure-the-throw-exception-shape.md).</span></span>  
  
## <a name="the-custom-exceptions"></a><span data-ttu-id="851a2-116">カスタム例外</span><span class="sxs-lookup"><span data-stu-id="851a2-116">The Custom Exceptions</span></span>  
 <span data-ttu-id="851a2-117">次の 3 つのカスタム例外は、同じ方式に従います。</span><span class="sxs-lookup"><span data-stu-id="851a2-117">Each of the following three custom exceptions follows the same pattern.</span></span> <span data-ttu-id="851a2-118">異なる種類を使用すると、コードは、各種の例外を区別できます。</span><span class="sxs-lookup"><span data-stu-id="851a2-118">Having distinct types allows the code to distinguish different exceptions.</span></span>  
  
|<span data-ttu-id="851a2-119">例外</span><span class="sxs-lookup"><span data-stu-id="851a2-119">Exception</span></span>|<span data-ttu-id="851a2-120">スローされる (オーケストレーション)</span><span class="sxs-lookup"><span data-stu-id="851a2-120">Thrown By (Orchestration)</span></span>|  
|---------------|---------------------------------|  
|<span data-ttu-id="851a2-121">**ActivateException**</span><span class="sxs-lookup"><span data-stu-id="851a2-121">**ActivateException**</span></span>|<span data-ttu-id="851a2-122">**変更**</span><span class="sxs-lookup"><span data-stu-id="851a2-122">**Change**</span></span>|  
|<span data-ttu-id="851a2-123">**CableOrderException**</span><span class="sxs-lookup"><span data-stu-id="851a2-123">**CableOrderException**</span></span>|<span data-ttu-id="851a2-124">**アクティブ化**、 **CableOrder1**</span><span class="sxs-lookup"><span data-stu-id="851a2-124">**Activate**, **CableOrder1**</span></span>|  
|<span data-ttu-id="851a2-125">**InterruptException**</span><span class="sxs-lookup"><span data-stu-id="851a2-125">**InterruptException**</span></span>|<span data-ttu-id="851a2-126">**CableOrder1**、 **CheckInterrupt**、 **ErrorHandlerOrch**</span><span class="sxs-lookup"><span data-stu-id="851a2-126">**CableOrder1**, **CheckInterrupt**, **ErrorHandlerOrch**</span></span>|  
  
 <span data-ttu-id="851a2-127">定義されているすべてのカスタム例外は、**ユーティリティ**アセンブリ。</span><span class="sxs-lookup"><span data-stu-id="851a2-127">All of the custom exceptions are defined in the **Utilities** assembly.</span></span> <span data-ttu-id="851a2-128">カスタム例外は、すべて .NET クラスです。</span><span class="sxs-lookup"><span data-stu-id="851a2-128">The custom exceptions are all .NET classes.</span></span> <span data-ttu-id="851a2-129">すべてのカスタム例外クラス継承した .NET **ApplicationException**から継承するクラス、 **System.Exception**クラスです。</span><span class="sxs-lookup"><span data-stu-id="851a2-129">All of the custom exception classes inherit from the .NET **ApplicationException** class which in turn inherits from the **System.Exception** class.</span></span> <span data-ttu-id="851a2-130">例外が退避されている (シリアル化されてデータベースに格納されている) 可能性があるので、シリアル化解除コンストラクタが例外に実装されている必要があります。</span><span class="sxs-lookup"><span data-stu-id="851a2-130">Because there is a possibility that the exception may be dehydrated (serialized and stored in the database), the exceptions must implement a deserialization constructor.</span></span> <span data-ttu-id="851a2-131">シリアル化解除コンストラクタは、2 つの引数 (SerializationInfo オブジェクトと StreamingContext オブジェクト) を使用するコンストラクタです。</span><span class="sxs-lookup"><span data-stu-id="851a2-131">A deserialization constructor is a constructor that takes two arguments: a SerializationInfo object, and a StreamingContext object.</span></span> <span data-ttu-id="851a2-132">例外の退避中に、シリアル化解除コンストラクタが使用されます。</span><span class="sxs-lookup"><span data-stu-id="851a2-132">The deserialization constructor will be used during rehydration of the exception.</span></span> <span data-ttu-id="851a2-133">**ApplicationException**クラスは、シリアル化解除コンストラクタを既に実装して、カスタムの例外のコンス トラクターは、ベース (ApplicationException) の逆シリアル化コンス トラクターを呼び出すだけです。</span><span class="sxs-lookup"><span data-stu-id="851a2-133">Because the **ApplicationException** class already implements a deserialization constructor, the constructor for the custom exception simply invokes the base (ApplicationException) deserialization constructor.</span></span> <span data-ttu-id="851a2-134">たとえば、 **InterruptException**次のコンス トラクターが含まれています。</span><span class="sxs-lookup"><span data-stu-id="851a2-134">For example, the **InterruptException** includes the following constructor:</span></span>  
  
```  
// "info" is the object holding the serialized object data.  
// "context" is the contextual information about the source  
// or destination.  
public InterruptException(SerializationInfo info,  
                  StreamingContext context) : base(info, context) { }  
```  
  
 <span data-ttu-id="851a2-135">カスタムのシリアル化の詳細については、『[!INCLUDE[btsDotNetFramework](../includes/btsdotnetframework-md.md)] 開発者ガイド』の「シリアル化のカスタマイズ」を参照してください。</span><span class="sxs-lookup"><span data-stu-id="851a2-135">For more detailed information about custom serialization, see Custom Serialization in the [!INCLUDE[btsDotNetFramework](../includes/btsdotnetframework-md.md)] Developer's Guide.</span></span>  
  
## <a name="nested-exception-handlers-and-compensation-blocks"></a><span data-ttu-id="851a2-136">入れ子になっている例外ハンドラと補正ブロック</span><span class="sxs-lookup"><span data-stu-id="851a2-136">Nested Exception Handlers and Compensation Blocks</span></span>  
 <span data-ttu-id="851a2-137">特殊な例外としての機能に加えて、一部の場所のカスタム例外は、ソート フラグとしての役割も果たします。</span><span class="sxs-lookup"><span data-stu-id="851a2-137">In addition to serving as specialized exceptions, the custom exceptions in several places also serve as a sort flag.</span></span> <span data-ttu-id="851a2-138">**変更**オーケストレーション、取り消し操作をロールバックする必要が 2 つの場所があります。</span><span class="sxs-lookup"><span data-stu-id="851a2-138">In the **Change** orchestration, there are two places that the Cancel operation must be rolled back.</span></span>  
  
> [!NOTE]
>  <span data-ttu-id="851a2-139">このセクションを参照することも、**変更**Visual Studio でオーケストレーションを開きます。</span><span class="sxs-lookup"><span data-stu-id="851a2-139">You may want to read this section with the **Change** orchestration open in Visual Studio.</span></span>  
  
 <span data-ttu-id="851a2-140">オーケストレーションの上部にある場合はへの呼び出し、**キャンセル**オーケストレーションが失敗した、 **CancelCompensation**ブロックが実行され、ロールバック、**キャンセル**トランザクションです。</span><span class="sxs-lookup"><span data-stu-id="851a2-140">At the top of the orchestration, if the call to the **Cancel** orchestration fails, the **CancelCompensation** block executes and rolls back the **Cancel** transaction.</span></span> <span data-ttu-id="851a2-141">オーケストレーションを呼び出す場合はすべてうまく行けば、 **Activate**オーケストレーションです。</span><span class="sxs-lookup"><span data-stu-id="851a2-141">If all goes well, the orchestration then calls the **Activate** orchestration.</span></span>  
  
 <span data-ttu-id="851a2-142">場合、 **Activate**操作が失敗、**キャンセル**トランザクションもロールバックする必要があります。</span><span class="sxs-lookup"><span data-stu-id="851a2-142">If the **Activate** operation fails, the **Cancel** transaction must also be rolled back.</span></span> <span data-ttu-id="851a2-143">ただし、例外ハンドラーへの呼び出しの**Activate**について何ら、**キャンセル**トランザクションです。</span><span class="sxs-lookup"><span data-stu-id="851a2-143">However, the exception handler for the call to **Activate** knows nothing about the **Cancel** transaction.</span></span> <span data-ttu-id="851a2-144">これに対処するには、オーケストレーション全体の例外ハンドラを使用します。</span><span class="sxs-lookup"><span data-stu-id="851a2-144">To handle this, there is an exception handler for the entire orchestration.</span></span> <span data-ttu-id="851a2-145">このハンドラーが含まれているため、**キャンセル**スコープを認識、**キャンセル**トランザクションです。</span><span class="sxs-lookup"><span data-stu-id="851a2-145">This handler, because it contains the **Cancel** scope, knows about the **Cancel** transaction.</span></span> <span data-ttu-id="851a2-146">スローされた例外をキャッチするハンドラー、 **Activate**スコープ (、 **ActivateException**)、ロールバック、**キャンセル**トランザクション、し、再度、例外をスローオーケストレーションが呼び出されるように、**変更**オーケストレーションは、追加の処理を実行できます。</span><span class="sxs-lookup"><span data-stu-id="851a2-146">The handler catches the exception thrown from the **Activate** scope (the **ActivateException**), rolls back the **Cancel** transaction, and then throws the exception again so that the orchestration that called the **Change** orchestration can perform any additional processing.</span></span>  
  
 <span data-ttu-id="851a2-147">補正するだけこの設計に注意してください、**キャンセル**場合、 **Activate**は失敗します。</span><span class="sxs-lookup"><span data-stu-id="851a2-147">Notice that this design only compensates the **Cancel** if the **Activate** fails.</span></span> <span data-ttu-id="851a2-148">場合、**キャンセル**は失敗し、例外がスロー、**キャンセル**ことはありませんが行われ、補正いない必要があります。</span><span class="sxs-lookup"><span data-stu-id="851a2-148">If the **Cancel** fails and throws an exception, the **Cancel** never took place and should not be compensated.</span></span>  
  
 <span data-ttu-id="851a2-149">補正ブロックの詳細については、**補正**図形は、「[補正図形を構成する方法](../core/how-to-configure-the-compensate-shape.md)です。</span><span class="sxs-lookup"><span data-stu-id="851a2-149">For more information about compensation blocks and the **Compensate** shape, see [How to Configure the Compensate Shape](../core/how-to-configure-the-compensate-shape.md).</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="851a2-150">参照</span><span class="sxs-lookup"><span data-stu-id="851a2-150">See Also</span></span>  
 <span data-ttu-id="851a2-151">[ビジネス プロセス管理ソリューションでの例外処理](../core/exception-handling-in-the-business-process-management-solution.md) </span><span class="sxs-lookup"><span data-stu-id="851a2-151">[Exception Handling in the Business Process Management Solution](../core/exception-handling-in-the-business-process-management-solution.md) </span></span>  
 [<span data-ttu-id="851a2-152">ExceptionHandler オーケストレーション</span><span class="sxs-lookup"><span data-stu-id="851a2-152">The ExceptionHandler Orchestration</span></span>](../core/the-exceptionhandler-orchestration.md)