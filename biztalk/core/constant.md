---
title: 定数 |Microsoft Docs
ms.custom: ''
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: ''
ms.suite: ''
ms.tgt_pltfrm: ''
ms.topic: article
ms.assetid: 0af49bf5-e7de-41da-ac27-70301b8ee4d4
caps.latest.revision: 7
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: ba1da4a690ca37a5012f5abb2e31f1229cb1b4bb
ms.sourcegitcommit: 381e83d43796a345488d54b3f7413e11d56ad7be
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 05/07/2019
ms.locfileid: "65354649"
---
# <a name="constant"></a><span data-ttu-id="49c32-102">定数</span><span class="sxs-lookup"><span data-stu-id="49c32-102">Constant</span></span>
<span data-ttu-id="49c32-103">1 つの定数値をスタックにプッシュします。</span><span class="sxs-lookup"><span data-stu-id="49c32-103">Pushes a single constant value onto the stack.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="49c32-104">構文</span><span class="sxs-lookup"><span data-stu-id="49c32-104">Syntax</span></span>  
  
```  
  
<ic:Operation Name="Constant">  
  <ic:Argument>val</ic:Argument>  
</ic:Operation>  
```  
  
#### <a name="parameters"></a><span data-ttu-id="49c32-105">パラメーター</span><span class="sxs-lookup"><span data-stu-id="49c32-105">Parameters</span></span>  
 <span data-ttu-id="49c32-106">定数値。</span><span class="sxs-lookup"><span data-stu-id="49c32-106">Constant value.</span></span>  
  
## <a name="pushed-value"></a><span data-ttu-id="49c32-107">プッシュされた値</span><span class="sxs-lookup"><span data-stu-id="49c32-107">Pushed Value</span></span>  
 <span data-ttu-id="49c32-108">定数の値を表す文字列です。</span><span class="sxs-lookup"><span data-stu-id="49c32-108">String containing the constant value.</span></span>  
  
## <a name="remarks"></a><span data-ttu-id="49c32-109">コメント</span><span class="sxs-lookup"><span data-stu-id="49c32-109">Remarks</span></span>  
  
## <a name="example"></a><span data-ttu-id="49c32-110">例</span><span class="sxs-lookup"><span data-stu-id="49c32-110">Example</span></span>  
 <span data-ttu-id="49c32-111">次のサンプルのフィルター式を使用して、**定数**でを使用して値をプッシュする操作、 **Equals**操作が現在のアクティビティ名が"FoodAndDrinksPolicy"であることを確認します。</span><span class="sxs-lookup"><span data-stu-id="49c32-111">The following sample filter expression uses the **Constant** operation to push a value that will then be used in an **Equals** operation to ensure that the current activity name is "FoodAndDrinksPolicy".</span></span>  
  
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
  
 <span data-ttu-id="49c32-112">これは、一般的な使用パターン、**定数**操作。</span><span class="sxs-lookup"><span data-stu-id="49c32-112">This is a common usage pattern for the **Constant** operation.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="49c32-113">参照</span><span class="sxs-lookup"><span data-stu-id="49c32-113">See Also</span></span>  
 [<span data-ttu-id="49c32-114">インターセプターの操作</span><span class="sxs-lookup"><span data-stu-id="49c32-114">Interceptor Operations</span></span>](../core/interceptor-operations.md)