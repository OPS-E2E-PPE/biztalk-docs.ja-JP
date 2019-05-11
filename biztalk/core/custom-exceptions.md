---
title: カスタムの例外 |Microsoft Docs
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
ms.openlocfilehash: 5118de4dc75d65f328838d9e7cecf4d51875db1b
ms.sourcegitcommit: 381e83d43796a345488d54b3f7413e11d56ad7be
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 05/07/2019
ms.locfileid: "65353396"
---
# <a name="custom-exceptions"></a><span data-ttu-id="3a02d-102">カスタム例外</span><span class="sxs-lookup"><span data-stu-id="3a02d-102">Custom Exceptions</span></span>
<span data-ttu-id="3a02d-103">場合、ビジネス プロセス管理ソリューションが例外ハンドラとカスタム例外の組み合わせを使用して回復不能なエラーがあります。</span><span class="sxs-lookup"><span data-stu-id="3a02d-103">For situations where there is an unrecoverable error, the Business Process Management solution uses a combination of exception handlers and custom exceptions.</span></span>  
  
## <a name="handling-exceptions"></a><span data-ttu-id="3a02d-104">例外の処理</span><span class="sxs-lookup"><span data-stu-id="3a02d-104">Handling Exceptions</span></span>  
 <span data-ttu-id="3a02d-105">使用してではなく**Terminate**呼び出されたオーケストレーションに図形をルート オーケストレーションで処理される例外をスローする方式を使用できます。</span><span class="sxs-lookup"><span data-stu-id="3a02d-105">Rather than using **Terminate** shapes in called orchestrations you can use the pattern of throwing exceptions that are handled by the root orchestration.</span></span> <span data-ttu-id="3a02d-106">これにより、例外の処理に関する決定を行うコンテキストの最も幅の広い知識を持つオーケストレーションです。</span><span class="sxs-lookup"><span data-stu-id="3a02d-106">This allows the orchestration with the widest knowledge of context to make the decision about handling the exception.</span></span> <span data-ttu-id="3a02d-107">カスタム例外をスローする下位のオーケストレーションには、ルート オーケストレーションにより具体的な情報を通信することができます。</span><span class="sxs-lookup"><span data-stu-id="3a02d-107">Having the subordinate orchestrations throw custom exceptions enables you to communicate more specific information to the root orchestration.</span></span>  
  
 <span data-ttu-id="3a02d-108">ビジネス プロセス管理ソリューションでは、このパターンに従います。</span><span class="sxs-lookup"><span data-stu-id="3a02d-108">The business process management solution follows this pattern.</span></span> <span data-ttu-id="3a02d-109">次の 4 つのルートがあるソリューションのオーケストレーションが呼び出されていない、または。**OrderBroker**、 **OrderManager**、 **CableOrder1**、および**CableOrder2**します。</span><span class="sxs-lookup"><span data-stu-id="3a02d-109">There are four root, or uncalled, orchestrations in the solution: **OrderBroker**, **OrderManager**, **CableOrder1**, and **CableOrder2**.</span></span> <span data-ttu-id="3a02d-110">3 つのルート オーケストレーションが表示され、カスタム例外を処理します。**OrderManager**、 **CableOrder1**、および**CableOrder2**します。</span><span class="sxs-lookup"><span data-stu-id="3a02d-110">Three of the root orchestrations receive and handle custom exceptions: **OrderManager**, **CableOrder1**, and **CableOrder2**.</span></span>  
  
 <span data-ttu-id="3a02d-111">ルート オーケストレーションの一部を使用ことに注意してください、 **Terminate**図形と、 **Terminate**図形がオーケストレーションの通常の終了ポイントの直前に表示されます。</span><span class="sxs-lookup"><span data-stu-id="3a02d-111">Note that some of the root orchestrations use the **Terminate** shape and that the **Terminate** shape appears just before the normal end point of the orchestration.</span></span> <span data-ttu-id="3a02d-112">オーケストレーションはまだ使用して、 **Terminate**図形のエラーが発生した場合、終了すると、オーケストレーションを記録するではなく完了したが、エラー メッセージ。</span><span class="sxs-lookup"><span data-stu-id="3a02d-112">The orchestration still uses the **Terminate** shape in case of an error so that the orchestration is recorded as terminated, rather than as completed but with an error message.</span></span> <span data-ttu-id="3a02d-113">これにより、エラーを記録するだけでなく簡単に失敗したインスタンスを追跡するソリューションです。</span><span class="sxs-lookup"><span data-stu-id="3a02d-113">This allows the solution to track failed instances easily in addition to recording the error.</span></span>  
  
 <span data-ttu-id="3a02d-114">詳細については、 **Terminate**図形は、「[終了図形を構成する方法](../core/how-to-configure-the-terminate-shape.md)します。</span><span class="sxs-lookup"><span data-stu-id="3a02d-114">For more information about the **Terminate** shape, see [How to Configure the Terminate Shape](../core/how-to-configure-the-terminate-shape.md).</span></span> <span data-ttu-id="3a02d-115">詳細については、 **ThrowException**図形は、「[例外のスロー図形を構成する方法](../core/how-to-configure-the-throw-exception-shape.md)します。</span><span class="sxs-lookup"><span data-stu-id="3a02d-115">For more information about the **ThrowException** shape, see [How to Configure the Throw Exception Shape](../core/how-to-configure-the-throw-exception-shape.md).</span></span>  
  
## <a name="the-custom-exceptions"></a><span data-ttu-id="3a02d-116">カスタム例外</span><span class="sxs-lookup"><span data-stu-id="3a02d-116">The Custom Exceptions</span></span>  
 <span data-ttu-id="3a02d-117">次の 3 つのカスタム例外の同じパターンに従います。</span><span class="sxs-lookup"><span data-stu-id="3a02d-117">Each of the following three custom exceptions follows the same pattern.</span></span> <span data-ttu-id="3a02d-118">さまざまな例外を区別するためにコードを個別の型を持つできます。</span><span class="sxs-lookup"><span data-stu-id="3a02d-118">Having distinct types allows the code to distinguish different exceptions.</span></span>  
  
|<span data-ttu-id="3a02d-119">例外</span><span class="sxs-lookup"><span data-stu-id="3a02d-119">Exception</span></span>|<span data-ttu-id="3a02d-120">スローされる (オーケストレーション)</span><span class="sxs-lookup"><span data-stu-id="3a02d-120">Thrown By (Orchestration)</span></span>|  
|---------------|---------------------------------|  
|<span data-ttu-id="3a02d-121">**ActivateException**</span><span class="sxs-lookup"><span data-stu-id="3a02d-121">**ActivateException**</span></span>|<span data-ttu-id="3a02d-122">**変更**</span><span class="sxs-lookup"><span data-stu-id="3a02d-122">**Change**</span></span>|  
|<span data-ttu-id="3a02d-123">**CableOrderException**</span><span class="sxs-lookup"><span data-stu-id="3a02d-123">**CableOrderException**</span></span>|<span data-ttu-id="3a02d-124">**アクティブ化**、 **CableOrder1**</span><span class="sxs-lookup"><span data-stu-id="3a02d-124">**Activate**, **CableOrder1**</span></span>|  
|<span data-ttu-id="3a02d-125">**InterruptException**</span><span class="sxs-lookup"><span data-stu-id="3a02d-125">**InterruptException**</span></span>|<span data-ttu-id="3a02d-126">**CableOrder1**、 **CheckInterrupt**、 **ErrorHandlerOrch**</span><span class="sxs-lookup"><span data-stu-id="3a02d-126">**CableOrder1**, **CheckInterrupt**, **ErrorHandlerOrch**</span></span>|  
  
 <span data-ttu-id="3a02d-127">定義されているすべてのカスタム例外は、**ユーティリティ**アセンブリ。</span><span class="sxs-lookup"><span data-stu-id="3a02d-127">All of the custom exceptions are defined in the **Utilities** assembly.</span></span> <span data-ttu-id="3a02d-128">カスタム例外は、すべての .NET クラスです。</span><span class="sxs-lookup"><span data-stu-id="3a02d-128">The custom exceptions are all .NET classes.</span></span> <span data-ttu-id="3a02d-129">.NET からのすべてのカスタム例外クラスを継承**ApplicationException**から継承するクラス、 **System.Exception**クラス。</span><span class="sxs-lookup"><span data-stu-id="3a02d-129">All of the custom exception classes inherit from the .NET **ApplicationException** class which in turn inherits from the **System.Exception** class.</span></span> <span data-ttu-id="3a02d-130">例外が退避される可能性の可能性があるため、(シリアル化され、データベースに格納されている)、例外する必要があります逆シリアル化コンス トラクターを実装します。</span><span class="sxs-lookup"><span data-stu-id="3a02d-130">Because there is a possibility that the exception may be dehydrated (serialized and stored in the database), the exceptions must implement a deserialization constructor.</span></span> <span data-ttu-id="3a02d-131">逆シリアル化コンス トラクターは 2 つの引数を受け取るコンス トラクター: SerializationInfo オブジェクトと StreamingContext オブジェクト。</span><span class="sxs-lookup"><span data-stu-id="3a02d-131">A deserialization constructor is a constructor that takes two arguments: a SerializationInfo object, and a StreamingContext object.</span></span> <span data-ttu-id="3a02d-132">逆シリアル化コンス トラクターは、例外のリハイド レート中に使用されます。</span><span class="sxs-lookup"><span data-stu-id="3a02d-132">The deserialization constructor will be used during rehydration of the exception.</span></span> <span data-ttu-id="3a02d-133">**ApplicationException**クラスは、シリアル化解除コンストラクタを既に実装して、カスタムの例外のコンス トラクターは、ベース (ApplicationException) の逆シリアル化コンス トラクターを呼び出すだけです。</span><span class="sxs-lookup"><span data-stu-id="3a02d-133">Because the **ApplicationException** class already implements a deserialization constructor, the constructor for the custom exception simply invokes the base (ApplicationException) deserialization constructor.</span></span> <span data-ttu-id="3a02d-134">たとえば、 **InterruptException**次のコンス トラクターが含まれています。</span><span class="sxs-lookup"><span data-stu-id="3a02d-134">For example, the **InterruptException** includes the following constructor:</span></span>  
  
```  
// "info" is the object holding the serialized object data.  
// "context" is the contextual information about the source  
// or destination.  
public InterruptException(SerializationInfo info,  
                  StreamingContext context) : base(info, context) { }  
```  
  
 <span data-ttu-id="3a02d-135">詳細については、カスタムのシリアル化でカスタムのシリアル化を参照してください、[!INCLUDE[btsDotNetFramework](../includes/btsdotnetframework-md.md)]開発者ガイド。</span><span class="sxs-lookup"><span data-stu-id="3a02d-135">For more detailed information about custom serialization, see Custom Serialization in the [!INCLUDE[btsDotNetFramework](../includes/btsdotnetframework-md.md)] Developer's Guide.</span></span>  
  
## <a name="nested-exception-handlers-and-compensation-blocks"></a><span data-ttu-id="3a02d-136">入れ子になった例外ハンドラーや補正ブロック</span><span class="sxs-lookup"><span data-stu-id="3a02d-136">Nested Exception Handlers and Compensation Blocks</span></span>  
 <span data-ttu-id="3a02d-137">特殊な例外としての機能、に加えてさまざまな場所でのカスタム例外はソート フラグとしても機能します。</span><span class="sxs-lookup"><span data-stu-id="3a02d-137">In addition to serving as specialized exceptions, the custom exceptions in several places also serve as a sort flag.</span></span> <span data-ttu-id="3a02d-138">**変更**オーケストレーションは 2 つの場所で取り消し操作をロールバックする必要があります。</span><span class="sxs-lookup"><span data-stu-id="3a02d-138">In the **Change** orchestration, there are two places that the Cancel operation must be rolled back.</span></span>  
  
> [!NOTE]
>  <span data-ttu-id="3a02d-139">このセクションを参照することも、**変更**オーケストレーションは、Visual Studio で開きます。</span><span class="sxs-lookup"><span data-stu-id="3a02d-139">You may want to read this section with the **Change** orchestration open in Visual Studio.</span></span>  
  
 <span data-ttu-id="3a02d-140">オーケストレーションの上部にある場合への呼び出し、**キャンセル**オーケストレーションが失敗した、 **CancelCompensation**ブロックが実行して、ロールバック、**キャンセル**トランザクション。</span><span class="sxs-lookup"><span data-stu-id="3a02d-140">At the top of the orchestration, if the call to the **Cancel** orchestration fails, the **CancelCompensation** block executes and rolls back the **Cancel** transaction.</span></span> <span data-ttu-id="3a02d-141">オーケストレーションを呼び出す場合、すべてうまくいけば、 **Activate**オーケストレーションします。</span><span class="sxs-lookup"><span data-stu-id="3a02d-141">If all goes well, the orchestration then calls the **Activate** orchestration.</span></span>  
  
 <span data-ttu-id="3a02d-142">場合、 **Activate**操作が失敗、**キャンセル**トランザクションは、戻るもロールバックする必要があります。</span><span class="sxs-lookup"><span data-stu-id="3a02d-142">If the **Activate** operation fails, the **Cancel** transaction must also be rolled back.</span></span> <span data-ttu-id="3a02d-143">ただし、例外ハンドラーへの呼び出しを**Activate**認識していません、**キャンセル**トランザクション。</span><span class="sxs-lookup"><span data-stu-id="3a02d-143">However, the exception handler for the call to **Activate** knows nothing about the **Cancel** transaction.</span></span> <span data-ttu-id="3a02d-144">これを処理するには、オーケストレーション全体の例外ハンドラーです。</span><span class="sxs-lookup"><span data-stu-id="3a02d-144">To handle this, there is an exception handler for the entire orchestration.</span></span> <span data-ttu-id="3a02d-145">このハンドラーが含まれています、**キャンセル**スコープを認識、**キャンセル**トランザクション。</span><span class="sxs-lookup"><span data-stu-id="3a02d-145">This handler, because it contains the **Cancel** scope, knows about the **Cancel** transaction.</span></span> <span data-ttu-id="3a02d-146">ハンドラーからスローされた例外のキャッチ、 **Activate**スコープ (、 **ActivateException**)、ロールバック、**キャンセル**トランザクション、例外を再度スローしますオーケストレーションが呼び出されるように、**変更**オーケストレーションは、追加の処理を実行できます。</span><span class="sxs-lookup"><span data-stu-id="3a02d-146">The handler catches the exception thrown from the **Activate** scope (the **ActivateException**), rolls back the **Cancel** transaction, and then throws the exception again so that the orchestration that called the **Change** orchestration can perform any additional processing.</span></span>  
  
 <span data-ttu-id="3a02d-147">この設計を補正のみに注意してください、**キャンセル**場合、 **Activate**が失敗します。</span><span class="sxs-lookup"><span data-stu-id="3a02d-147">Notice that this design only compensates the **Cancel** if the **Activate** fails.</span></span> <span data-ttu-id="3a02d-148">場合、**キャンセル**が失敗し、例外がスロー、**キャンセル**ことはありませんが行われ、補正しない必要があります。</span><span class="sxs-lookup"><span data-stu-id="3a02d-148">If the **Cancel** fails and throws an exception, the **Cancel** never took place and should not be compensated.</span></span>  
  
 <span data-ttu-id="3a02d-149">補正ブロックの詳細については、**補正**図形は、「[補正図形を構成する方法](../core/how-to-configure-the-compensate-shape.md)します。</span><span class="sxs-lookup"><span data-stu-id="3a02d-149">For more information about compensation blocks and the **Compensate** shape, see [How to Configure the Compensate Shape](../core/how-to-configure-the-compensate-shape.md).</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="3a02d-150">参照</span><span class="sxs-lookup"><span data-stu-id="3a02d-150">See Also</span></span>  
 <span data-ttu-id="3a02d-151">[ビジネス プロセス管理ソリューションでの例外処理](../core/exception-handling-in-the-business-process-management-solution.md) </span><span class="sxs-lookup"><span data-stu-id="3a02d-151">[Exception Handling in the Business Process Management Solution](../core/exception-handling-in-the-business-process-management-solution.md) </span></span>  
 [<span data-ttu-id="3a02d-152">ExceptionHandler オーケストレーション</span><span class="sxs-lookup"><span data-stu-id="3a02d-152">The ExceptionHandler Orchestration</span></span>](../core/the-exceptionhandler-orchestration.md)