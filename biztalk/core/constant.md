---
title: "定数 |Microsoft ドキュメント"
ms.custom: 
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: 
ms.suite: 
ms.tgt_pltfrm: 
ms.topic: article
ms.assetid: 0af49bf5-e7de-41da-ac27-70301b8ee4d4
caps.latest.revision: "7"
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: 674307acea439bc260399cc01da4165eedaa2da5
ms.sourcegitcommit: cb908c540d8f1a692d01dc8f313e16cb4b4e696d
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 09/20/2017
---
# <a name="constant"></a><span data-ttu-id="33d13-102">定数</span><span class="sxs-lookup"><span data-stu-id="33d13-102">Constant</span></span>
<span data-ttu-id="33d13-103">1 つの定数値をスタックにプッシュします。</span><span class="sxs-lookup"><span data-stu-id="33d13-103">Pushes a single constant value onto the stack.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="33d13-104">構文</span><span class="sxs-lookup"><span data-stu-id="33d13-104">Syntax</span></span>  
  
```  
  
<ic:Operation Name="Constant">  
  <ic:Argument>val</ic:Argument>  
</ic:Operation>  
```  
  
#### <a name="parameters"></a><span data-ttu-id="33d13-105">パラメーター</span><span class="sxs-lookup"><span data-stu-id="33d13-105">Parameters</span></span>  
 <span data-ttu-id="33d13-106">定数値。</span><span class="sxs-lookup"><span data-stu-id="33d13-106">Constant value.</span></span>  
  
## <a name="pushed-value"></a><span data-ttu-id="33d13-107">プッシュされた値</span><span class="sxs-lookup"><span data-stu-id="33d13-107">Pushed Value</span></span>  
 <span data-ttu-id="33d13-108">定数値が含まれた文字列。</span><span class="sxs-lookup"><span data-stu-id="33d13-108">String containing the constant value.</span></span>  
  
## <a name="remarks"></a><span data-ttu-id="33d13-109">解説</span><span class="sxs-lookup"><span data-stu-id="33d13-109">Remarks</span></span>  
  
## <a name="example"></a><span data-ttu-id="33d13-110">例</span><span class="sxs-lookup"><span data-stu-id="33d13-110">Example</span></span>  
 <span data-ttu-id="33d13-111">次のサンプル フィルター式を使用して、**定数**で使用される、値をプッシュする操作、 **Equals**操作が現在のアクティビティ名が"FoodAndDrinksPolicy"であることを確認します。</span><span class="sxs-lookup"><span data-stu-id="33d13-111">The following sample filter expression uses the **Constant** operation to push a value that will then be used in an **Equals** operation to ensure that the current activity name is "FoodAndDrinksPolicy".</span></span>  
  
```  
<ic:Filter>  
  <ic:Expression>  
    <wf:Operation Name="GetActivityName"/>  
    <ic:Operation Name="Constant">  
      <ic:Argument>FoodAndDrinksPolicy</ic:Argument>  
    </ic:Operation>  
    <ic:Operation Name="Equals"/>  
  </ic:Expression>  
</ic:Filter>  
```  
  
 <span data-ttu-id="33d13-112">これは、一般的な使用パターン、**定数**操作します。</span><span class="sxs-lookup"><span data-stu-id="33d13-112">This is a common usage pattern for the **Constant** operation.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="33d13-113">参照</span><span class="sxs-lookup"><span data-stu-id="33d13-113">See Also</span></span>  
 [<span data-ttu-id="33d13-114">インターセプタの操作</span><span class="sxs-lookup"><span data-stu-id="33d13-114">Interceptor Operations</span></span>](../core/interceptor-operations.md)