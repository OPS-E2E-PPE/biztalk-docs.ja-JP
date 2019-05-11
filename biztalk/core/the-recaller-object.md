---
title: Recaller オブジェクト |Microsoft Docs
ms.custom: ''
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: ''
ms.suite: ''
ms.tgt_pltfrm: ''
ms.topic: article
helpviewer_keywords:
- Recaller object
- Invoke method
- process management solution tutorial, Recaller object
- process management solution tutorial, errors
ms.assetid: b30ad1ae-475f-4913-b402-4d3263fcf072
caps.latest.revision: 10
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: 15ad2868892f0190cb9ebf8c63dfd6e3df200505
ms.sourcegitcommit: 381e83d43796a345488d54b3f7413e11d56ad7be
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 05/07/2019
ms.locfileid: "65394062"
---
# <a name="the-recaller-object"></a><span data-ttu-id="6fd2c-102">Recaller オブジェクト</span><span class="sxs-lookup"><span data-stu-id="6fd2c-102">The Recaller Object</span></span>
<span data-ttu-id="6fd2c-103">再試行するには、ビジネス プロセス管理ソリューションを提供します、一般的ないくつかが失敗オブジェクト メソッドの呼び出し。</span><span class="sxs-lookup"><span data-stu-id="6fd2c-103">The business process management solution provides for retrying, in a generic way, some failed object method calls.</span></span> <span data-ttu-id="6fd2c-104">ソリューションはこれを**Recaller**オブジェクト、 **ExceptionHandler**オーケストレーションします。</span><span class="sxs-lookup"><span data-stu-id="6fd2c-104">The solution does this through the **Recaller** object in the **ExceptionHandler** orchestration.</span></span> <span data-ttu-id="6fd2c-105">**ExceptionHandler**オーケストレーションでは、オブジェクトを使用して、オブジェクト メソッドの呼び出しを再試行してください。</span><span class="sxs-lookup"><span data-stu-id="6fd2c-105">The **ExceptionHandler** orchestration uses the object to retry object method calls.</span></span> <span data-ttu-id="6fd2c-106">詳細については、次を参照してください。 [、ExceptionHandler オーケストレーション](../core/the-exceptionhandler-orchestration.md)します。</span><span class="sxs-lookup"><span data-stu-id="6fd2c-106">For more information, see [The ExceptionHandler Orchestration](../core/the-exceptionhandler-orchestration.md).</span></span>  
  
## <a name="the-invoke-method"></a><span data-ttu-id="6fd2c-107">メソッドを呼び出す</span><span class="sxs-lookup"><span data-stu-id="6fd2c-107">The Invoke Method</span></span>  
 <span data-ttu-id="6fd2c-108">**Recaller**オブジェクトが 1 つの静的メソッドでは、 **Invoke**します。</span><span class="sxs-lookup"><span data-stu-id="6fd2c-108">The **Recaller** object has a single, static method, **Invoke**.</span></span> <span data-ttu-id="6fd2c-109">決してのインスタンスを作成する必要がありますには、静的であるため、 **Recaller**オブジェクト。</span><span class="sxs-lookup"><span data-stu-id="6fd2c-109">Because it is static, you never need to create an instance of the **Recaller** object.</span></span> <span data-ttu-id="6fd2c-110">使用することができます、 **Invoke**メソッドで 3 つの方法: オブジェクトは、静的メソッドを呼び出す、またはオブジェクトの非静的メソッドを呼び出す、オブジェクトを構築します。</span><span class="sxs-lookup"><span data-stu-id="6fd2c-110">You can use the **Invoke** method in three ways: to construct an object, to call a static method for an object, or to call a non-static method for an object.</span></span>  
  
> [!NOTE]
>  <span data-ttu-id="6fd2c-111">**Invoke**メソッドのラッパーとして機能、 **Type.InvokeMember**メソッドで、[!INCLUDE[btsDotNetFramework](../includes/btsdotnetframework-md.md)]クラス ライブラリ。</span><span class="sxs-lookup"><span data-stu-id="6fd2c-111">The **Invoke** method serves as a wrapper for the **Type.InvokeMember** method in the [!INCLUDE[btsDotNetFramework](../includes/btsdotnetframework-md.md)] Class Library.</span></span>  
  
### <a name="arguments-for-the-invoke-method"></a><span data-ttu-id="6fd2c-112">引数、メソッドを呼び出す</span><span class="sxs-lookup"><span data-stu-id="6fd2c-112">Arguments for the Invoke Method</span></span>  
 <span data-ttu-id="6fd2c-113">次の表に、引数、 **Invoke**メソッド。</span><span class="sxs-lookup"><span data-stu-id="6fd2c-113">The following table describes arguments for the **Invoke** method:</span></span>  
  
|<span data-ttu-id="6fd2c-114">パラメーター</span><span class="sxs-lookup"><span data-stu-id="6fd2c-114">Parameter</span></span>|<span data-ttu-id="6fd2c-115">型</span><span class="sxs-lookup"><span data-stu-id="6fd2c-115">Type</span></span>|<span data-ttu-id="6fd2c-116">説明</span><span class="sxs-lookup"><span data-stu-id="6fd2c-116">Description</span></span>|  
|---------------|----------|-----------------|  
|<span data-ttu-id="6fd2c-117">*t*</span><span class="sxs-lookup"><span data-stu-id="6fd2c-117">*t*</span></span>|<span data-ttu-id="6fd2c-118">**型**</span><span class="sxs-lookup"><span data-stu-id="6fd2c-118">**Type**</span></span>|<span data-ttu-id="6fd2c-119">メソッドを呼び出す対象となるオブジェクトの型。</span><span class="sxs-lookup"><span data-stu-id="6fd2c-119">The type of the object on which to call the method.</span></span>|  
|<span data-ttu-id="6fd2c-120">*obj*</span><span class="sxs-lookup"><span data-stu-id="6fd2c-120">*obj*</span></span>|<span data-ttu-id="6fd2c-121">**Object**</span><span class="sxs-lookup"><span data-stu-id="6fd2c-121">**Object**</span></span>|<span data-ttu-id="6fd2c-122">使用するオブジェクトのインスタンス。</span><span class="sxs-lookup"><span data-stu-id="6fd2c-122">The instance of the object to use.</span></span>|  
|<span data-ttu-id="6fd2c-123">*methodName*</span><span class="sxs-lookup"><span data-stu-id="6fd2c-123">*methodName*</span></span>|<span data-ttu-id="6fd2c-124">**string**</span><span class="sxs-lookup"><span data-stu-id="6fd2c-124">**string**</span></span>|<span data-ttu-id="6fd2c-125">呼び出すメソッドの名前。</span><span class="sxs-lookup"><span data-stu-id="6fd2c-125">The name of the method to invoke.</span></span>|  
|<span data-ttu-id="6fd2c-126">*引数*</span><span class="sxs-lookup"><span data-stu-id="6fd2c-126">*args*</span></span>|<span data-ttu-id="6fd2c-127">**配列**</span><span class="sxs-lookup"><span data-stu-id="6fd2c-127">**Array**</span></span>|<span data-ttu-id="6fd2c-128">型の配列**オブジェクト**メソッドの引数を格納しています。</span><span class="sxs-lookup"><span data-stu-id="6fd2c-128">An array of type **Object** containing the method's arguments.</span></span>|  
  
 <span data-ttu-id="6fd2c-129">オブジェクトのコンス トラクターを呼び出す、空の文字列を使用して、("") または**null**の*methodName*します。</span><span class="sxs-lookup"><span data-stu-id="6fd2c-129">To call the constructor for an object, use an empty string ("") or **null** for *methodName*.</span></span>  
  
 <span data-ttu-id="6fd2c-130">静的メソッドを呼び出すには、次のように使用します。 **null**の*obj*します。</span><span class="sxs-lookup"><span data-stu-id="6fd2c-130">To call a static method, use **null** for *obj*.</span></span>  
  
 <span data-ttu-id="6fd2c-131">非静的メソッドを呼び出すには、すべての引数を指定します。</span><span class="sxs-lookup"><span data-stu-id="6fd2c-131">To call a non-static method, supply all of the arguments.</span></span>  
  
> [!NOTE]
>  <span data-ttu-id="6fd2c-132">使用して**null**型引数の値として*t*、により**Invoke**をスローする、 **ArgumentNullException**例外。</span><span class="sxs-lookup"><span data-stu-id="6fd2c-132">Using **null** as the value of the Type argument, *t*, causes **Invoke** to throw an **ArgumentNullException** exception.</span></span> <span data-ttu-id="6fd2c-133">引数*t*は null にできませんので、 **Invoke**メソッドは、 **Type.InvokeMember** [!INCLUDE[btsDotNetFramework](../includes/btsdotnetframework-md.md)]メソッド。</span><span class="sxs-lookup"><span data-stu-id="6fd2c-133">The argument *t* should not be null because the **Invoke** method uses the **Type.InvokeMember** [!INCLUDE[btsDotNetFramework](../includes/btsdotnetframework-md.md)] method.</span></span>  
  
## <a name="calling-invoke"></a><span data-ttu-id="6fd2c-134">Invoke の呼び出し</span><span class="sxs-lookup"><span data-stu-id="6fd2c-134">Calling Invoke</span></span>  
 <span data-ttu-id="6fd2c-135">のみのソリューションで、 **ExceptionHandler**オーケストレーションは、 **Recaller**オブジェクト。</span><span class="sxs-lookup"><span data-stu-id="6fd2c-135">In the solution, only the **ExceptionHandler** orchestration uses the **Recaller** object.</span></span> <span data-ttu-id="6fd2c-136">**ExceptionHandler** 、さらに、他のオーケストレーションで使用します。</span><span class="sxs-lookup"><span data-stu-id="6fd2c-136">The **ExceptionHandler** is, in turn, used by other orchestrations.</span></span> <span data-ttu-id="6fd2c-137">渡される値、 **Invoke**メソッドでは、他のオーケストレーションをこれらからに取得します。</span><span class="sxs-lookup"><span data-stu-id="6fd2c-137">The values passed to the **Invoke** method come from these other orchestrations.</span></span> <span data-ttu-id="6fd2c-138">たとえば、次のコードが、 **Activate**でオーケストレーション、 **InitialException**式図形。</span><span class="sxs-lookup"><span data-stu-id="6fd2c-138">For example, the following code appears in the **Activate** orchestration in the **InitialException** Expression shape:</span></span>  
  
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
  
 <span data-ttu-id="6fd2c-139">コードを使用して、配列を作成する方法に注意してください。 **System.Array.CreateInstance**を使用して、 **SetValue** 、で使用する値を格納する方法。</span><span class="sxs-lookup"><span data-stu-id="6fd2c-139">Notice how the code creates an array using **System.Array.CreateInstance** and uses the **SetValue** method to store the values used in it.</span></span>  
  
 <span data-ttu-id="6fd2c-140">式図形の後、Activate オーケストレーションを呼び出して、 **ExceptionHandler**オーケストレーションします。</span><span class="sxs-lookup"><span data-stu-id="6fd2c-140">After the Expression shape, the Activate orchestration calls the **ExceptionHandler** orchestration.</span></span> <span data-ttu-id="6fd2c-141">次のコードは、オーケストレーション デザイナーでの呼び出し図形を変換する方法を示しています。</span><span class="sxs-lookup"><span data-stu-id="6fd2c-141">The following code shows how the orchestration designer translates the Call shape:</span></span>  
  
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
  
 <span data-ttu-id="6fd2c-142">**ExceptionHandler**オーケストレーションでは、次のコードが、 **Call Original Code**式図形。</span><span class="sxs-lookup"><span data-stu-id="6fd2c-142">In the **ExceptionHandler** orchestration, the following code appears in the **Call Original Code** Expression shape:</span></span>  
  
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
  
 <span data-ttu-id="6fd2c-143">、Activate オーケストレーションからの呼び出しで引数名に合わせて、は引数が一致することによって順序と名前ではなくオーケストレーションを呼び出すときに注意してください。</span><span class="sxs-lookup"><span data-stu-id="6fd2c-143">Notice that, although the argument names match those in the Activate orchestration's call, arguments are matched by order and not by name when calling orchestrations.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="6fd2c-144">参照</span><span class="sxs-lookup"><span data-stu-id="6fd2c-144">See Also</span></span>  
 <span data-ttu-id="6fd2c-145">[ビジネス プロセス管理ソリューションの実装の要点](../core/implementation-highlights-of-the-business-process-management-solution.md) </span><span class="sxs-lookup"><span data-stu-id="6fd2c-145">[Implementation Highlights of the Business Process Management Solution](../core/implementation-highlights-of-the-business-process-management-solution.md) </span></span>  
 [<span data-ttu-id="6fd2c-146">ExceptionHandler オーケストレーション</span><span class="sxs-lookup"><span data-stu-id="6fd2c-146">The ExceptionHandler Orchestration</span></span>](../core/the-exceptionhandler-orchestration.md)