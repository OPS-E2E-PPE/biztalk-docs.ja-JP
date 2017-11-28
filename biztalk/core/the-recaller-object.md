---
title: "Recaller オブジェクト |Microsoft ドキュメント"
ms.custom: 
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: 
ms.suite: 
ms.tgt_pltfrm: 
ms.topic: article
helpviewer_keywords:
- Recaller object
- Invoke method
- process management solution tutorial, Recaller object
- process management solution tutorial, errors
ms.assetid: b30ad1ae-475f-4913-b402-4d3263fcf072
caps.latest.revision: "10"
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: 731f7703eb9145b1249872902d0b867fe22622ec
ms.sourcegitcommit: cb908c540d8f1a692d01dc8f313e16cb4b4e696d
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 09/20/2017
---
# <a name="the-recaller-object"></a><span data-ttu-id="7681c-102">Recaller オブジェクト</span><span class="sxs-lookup"><span data-stu-id="7681c-102">The Recaller Object</span></span>
<span data-ttu-id="7681c-103">ビジネス プロセス管理ソリューションでは、失敗したオブジェクト メソッドの呼び出しが、汎用的な方法で再試行できます。</span><span class="sxs-lookup"><span data-stu-id="7681c-103">The business process management solution provides for retrying, in a generic way, some failed object method calls.</span></span> <span data-ttu-id="7681c-104">このソリューションは、 **Recaller**内のオブジェクト、 **ExceptionHandler**オーケストレーションです。</span><span class="sxs-lookup"><span data-stu-id="7681c-104">The solution does this through the **Recaller** object in the **ExceptionHandler** orchestration.</span></span> <span data-ttu-id="7681c-105">**ExceptionHandler**オーケストレーションでは、オブジェクトを使用して、オブジェクト メソッドの呼び出しを再試行してください。</span><span class="sxs-lookup"><span data-stu-id="7681c-105">The **ExceptionHandler** orchestration uses the object to retry object method calls.</span></span> <span data-ttu-id="7681c-106">詳細については、次を参照してください。 [ExceptionHandler Orchestration](../core/the-exceptionhandler-orchestration.md)です。</span><span class="sxs-lookup"><span data-stu-id="7681c-106">For more information, see [The ExceptionHandler Orchestration](../core/the-exceptionhandler-orchestration.md).</span></span>  
  
## <a name="the-invoke-method"></a><span data-ttu-id="7681c-107">Invoke メソッド</span><span class="sxs-lookup"><span data-stu-id="7681c-107">The Invoke Method</span></span>  
 <span data-ttu-id="7681c-108">**Recaller**オブジェクトが 1 つの静的メソッド**Invoke**です。</span><span class="sxs-lookup"><span data-stu-id="7681c-108">The **Recaller** object has a single, static method, **Invoke**.</span></span> <span data-ttu-id="7681c-109">インスタンスを作成する必要が静的であるためありません、 **Recaller**オブジェクト。</span><span class="sxs-lookup"><span data-stu-id="7681c-109">Because it is static, you never need to create an instance of the **Recaller** object.</span></span> <span data-ttu-id="7681c-110">使用することができます、 **Invoke**メソッドを次の 3 つの方法で: メソッドを呼び出す、静的オブジェクト、またはオブジェクトの非静的メソッドを呼び出す、オブジェクトを構築します。</span><span class="sxs-lookup"><span data-stu-id="7681c-110">You can use the **Invoke** method in three ways: to construct an object, to call a static method for an object, or to call a non-static method for an object.</span></span>  
  
> [!NOTE]
>  <span data-ttu-id="7681c-111">**Invoke**メソッドのラッパーとして機能、 **Type.InvokeMember**メソッドで、[!INCLUDE[btsDotNetFramework](../includes/btsdotnetframework-md.md)]クラス ライブラリです。</span><span class="sxs-lookup"><span data-stu-id="7681c-111">The **Invoke** method serves as a wrapper for the **Type.InvokeMember** method in the [!INCLUDE[btsDotNetFramework](../includes/btsdotnetframework-md.md)] Class Library.</span></span>  
  
### <a name="arguments-for-the-invoke-method"></a><span data-ttu-id="7681c-112">Invoke メソッドの引数</span><span class="sxs-lookup"><span data-stu-id="7681c-112">Arguments for the Invoke Method</span></span>  
 <span data-ttu-id="7681c-113">次の表の引数、 **Invoke**メソッド。</span><span class="sxs-lookup"><span data-stu-id="7681c-113">The following table describes arguments for the **Invoke** method:</span></span>  
  
|<span data-ttu-id="7681c-114">パラメーター</span><span class="sxs-lookup"><span data-stu-id="7681c-114">Parameter</span></span>|<span data-ttu-id="7681c-115">型</span><span class="sxs-lookup"><span data-stu-id="7681c-115">Type</span></span>|<span data-ttu-id="7681c-116">Description</span><span class="sxs-lookup"><span data-stu-id="7681c-116">Description</span></span>|  
|---------------|----------|-----------------|  
|<span data-ttu-id="7681c-117">*t*</span><span class="sxs-lookup"><span data-stu-id="7681c-117">*t*</span></span>|<span data-ttu-id="7681c-118">**型**</span><span class="sxs-lookup"><span data-stu-id="7681c-118">**Type**</span></span>|<span data-ttu-id="7681c-119">呼び出されるメソッドがあるオブジェクトのデータ型</span><span class="sxs-lookup"><span data-stu-id="7681c-119">The type of the object on which to call the method.</span></span>|  
|<span data-ttu-id="7681c-120">*obj*</span><span class="sxs-lookup"><span data-stu-id="7681c-120">*obj*</span></span>|<span data-ttu-id="7681c-121">**オブジェクト**</span><span class="sxs-lookup"><span data-stu-id="7681c-121">**Object**</span></span>|<span data-ttu-id="7681c-122">使用するオブジェクトのインスタンス</span><span class="sxs-lookup"><span data-stu-id="7681c-122">The instance of the object to use.</span></span>|  
|<span data-ttu-id="7681c-123">*methodName*</span><span class="sxs-lookup"><span data-stu-id="7681c-123">*methodName*</span></span>|<span data-ttu-id="7681c-124">**string**</span><span class="sxs-lookup"><span data-stu-id="7681c-124">**string**</span></span>|<span data-ttu-id="7681c-125">呼び出すメソッドの名前です。</span><span class="sxs-lookup"><span data-stu-id="7681c-125">The name of the method to invoke.</span></span>|  
|<span data-ttu-id="7681c-126">*args*</span><span class="sxs-lookup"><span data-stu-id="7681c-126">*args*</span></span>|<span data-ttu-id="7681c-127">**配列**</span><span class="sxs-lookup"><span data-stu-id="7681c-127">**Array**</span></span>|<span data-ttu-id="7681c-128">型の配列**オブジェクト**メソッドの引数を格納します。</span><span class="sxs-lookup"><span data-stu-id="7681c-128">An array of type **Object** containing the method's arguments.</span></span>|  
  
 <span data-ttu-id="7681c-129">オブジェクトのコンス トラクターを呼び出しするには、空の文字列 ("") または**null**の*methodName*です。</span><span class="sxs-lookup"><span data-stu-id="7681c-129">To call the constructor for an object, use an empty string ("") or **null** for *methodName*.</span></span>  
  
 <span data-ttu-id="7681c-130">静的メソッドを呼び出すには、次のように使用します。 **null**の*obj*です。</span><span class="sxs-lookup"><span data-stu-id="7681c-130">To call a static method, use **null** for *obj*.</span></span>  
  
 <span data-ttu-id="7681c-131">非静的メソッドを呼び出すには、すべての引数に値を指定します。</span><span class="sxs-lookup"><span data-stu-id="7681c-131">To call a non-static method, supply all of the arguments.</span></span>  
  
> [!NOTE]
>  <span data-ttu-id="7681c-132">使用して**null**型引数の値として*t*、により**Invoke**をスローする、 **ArgumentNullException**例外。</span><span class="sxs-lookup"><span data-stu-id="7681c-132">Using **null** as the value of the Type argument, *t*, causes **Invoke** to throw an **ArgumentNullException** exception.</span></span> <span data-ttu-id="7681c-133">引数*t* null は使用できませんので、 **Invoke**メソッドを使用、 **Type.InvokeMember** [!INCLUDE[btsDotNetFramework](../includes/btsdotnetframework-md.md)]メソッドです。</span><span class="sxs-lookup"><span data-stu-id="7681c-133">The argument *t* should not be null because the **Invoke** method uses the **Type.InvokeMember** [!INCLUDE[btsDotNetFramework](../includes/btsdotnetframework-md.md)] method.</span></span>  
  
## <a name="calling-invoke"></a><span data-ttu-id="7681c-134">Invoke の呼び出し</span><span class="sxs-lookup"><span data-stu-id="7681c-134">Calling Invoke</span></span>  
 <span data-ttu-id="7681c-135">ソリューションでは、のみ、 **ExceptionHandler**オーケストレーションは、 **Recaller**オブジェクト。</span><span class="sxs-lookup"><span data-stu-id="7681c-135">In the solution, only the **ExceptionHandler** orchestration uses the **Recaller** object.</span></span> <span data-ttu-id="7681c-136">**ExceptionHandler** 、さらに、他のオーケストレーションで使用します。</span><span class="sxs-lookup"><span data-stu-id="7681c-136">The **ExceptionHandler** is, in turn, used by other orchestrations.</span></span> <span data-ttu-id="7681c-137">渡される値、 **Invoke**メソッドでは、他のオーケストレーションをこれらからに取得します。</span><span class="sxs-lookup"><span data-stu-id="7681c-137">The values passed to the **Invoke** method come from these other orchestrations.</span></span> <span data-ttu-id="7681c-138">たとえば、次のコードが、 **Activate**でオーケストレーション、 **InitialException**式図形。</span><span class="sxs-lookup"><span data-stu-id="7681c-138">For example, the following code appears in the **Activate** orchestration in the **InitialException** Expression shape:</span></span>  
  
```  
Ex = CodeEx;  
ObjectType = orderHandler.GetType();  
CalledObject = orderHandler;  
Reason = "Standard Activate Failed";  
MethodName = "Activate";  
ParameterArray = System.Array.CreateInstance(typeof(System.Object),  
                                              3 );  
ParameterArray.SetValue(ServiceType, 0);  
ParameterArray.SetValue(OrderMsg.CustNum, 1);  
ParameterArray.SetValue(OrderMsg.OrderNum, 2);  
ReturnValue = null; // no return value expected  
  
```  
  
 <span data-ttu-id="7681c-139">コードが使用して、配列を作成する方法に注意してください。 **System.Array.CreateInstance**を使用して、 **SetValue**メソッド内で使用される値を格納します。</span><span class="sxs-lookup"><span data-stu-id="7681c-139">Notice how the code creates an array using **System.Array.CreateInstance** and uses the **SetValue** method to store the values used in it.</span></span>  
  
 <span data-ttu-id="7681c-140">式図形後、Activate オーケストレーションを呼び出して、 **ExceptionHandler**オーケストレーションです。</span><span class="sxs-lookup"><span data-stu-id="7681c-140">After the Expression shape, the Activate orchestration calls the **ExceptionHandler** orchestration.</span></span> <span data-ttu-id="7681c-141">次のコードはオーケストレーション デザイナが呼び出し図形をどのように変換するかを示します。</span><span class="sxs-lookup"><span data-stu-id="7681c-141">The following code shows how the orchestration designer translates the Call shape:</span></span>  
  
```  
call Microsoft.Samples.  
    BizTalk.SouthridgeVideo.  
        OrderManager.ExceptionHandlerOrch  
            (  
                Reason,  
                Ex,  
                CalledObject,  
                MethodName,   
                ParameterArray,   
                OrderCorrelation,   
                OrderMsg,   
                out ReturnValue,   
                ObjectType  
            );  
  
```  
  
 <span data-ttu-id="7681c-142">**ExceptionHandler**オーケストレーションでは、次のコードが、 **Call Original Code**式図形。</span><span class="sxs-lookup"><span data-stu-id="7681c-142">In the **ExceptionHandler** orchestration, the following code appears in the **Call Original Code** Expression shape:</span></span>  
  
```  
ReturnValue =   
    Microsoft.Samples.  
        BizTalk.SouthridgeVideo.  
            Utilities.Recaller.  
                Invoke(  
                    ObjectType,  
                    CalledObject,  
                    MethodName,  
                    ParameterArray  
                );  
```  
  
 <span data-ttu-id="7681c-143">引数名は Activate オーケストレーションからの呼び出しで使用されているものに一致しますが、オーケストレーションを呼び出すとき、引数の照合は名前ではなく順序によって行われることに注意してください。</span><span class="sxs-lookup"><span data-stu-id="7681c-143">Notice that, although the argument names match those in the Activate orchestration's call, arguments are matched by order and not by name when calling orchestrations.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="7681c-144">参照</span><span class="sxs-lookup"><span data-stu-id="7681c-144">See Also</span></span>  
 <span data-ttu-id="7681c-145">[ビジネス プロセス管理ソリューションの実装の要点](../core/implementation-highlights-of-the-business-process-management-solution.md) </span><span class="sxs-lookup"><span data-stu-id="7681c-145">[Implementation Highlights of the Business Process Management Solution](../core/implementation-highlights-of-the-business-process-management-solution.md) </span></span>  
 [<span data-ttu-id="7681c-146">ExceptionHandler オーケストレーション</span><span class="sxs-lookup"><span data-stu-id="7681c-146">The ExceptionHandler Orchestration</span></span>](../core/the-exceptionhandler-orchestration.md)