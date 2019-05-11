---
title: 等しい |Microsoft Docs
ms.custom: ''
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: ''
ms.suite: ''
ms.tgt_pltfrm: ''
ms.topic: article
ms.assetid: ac93031a-9d18-443d-9e38-71ef9edd5a30
caps.latest.revision: 7
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: e376445e8349663ab6196e99f9f31df8e5c1e139
ms.sourcegitcommit: d27732e569b0897361dfaebca8352aa97bb7efe1
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 05/10/2019
ms.locfileid: "65530732"
---
# <a name="equals"></a><span data-ttu-id="fe3f2-102">[等しい]</span><span class="sxs-lookup"><span data-stu-id="fe3f2-102">Equals</span></span>
<span data-ttu-id="fe3f2-103">スタックから上位 2 項目を削除、2 つの項目を比較し、その結果をスタックにプッシュします。</span><span class="sxs-lookup"><span data-stu-id="fe3f2-103">Removes the top two items from the stack, compares the two items, and then pushes the result onto the stack.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="fe3f2-104">構文</span><span class="sxs-lookup"><span data-stu-id="fe3f2-104">Syntax</span></span>  
  
```  
  
<ic:Operation Name="Equals" />  
```  
  
#### <a name="parameters"></a><span data-ttu-id="fe3f2-105">パラメーター</span><span class="sxs-lookup"><span data-stu-id="fe3f2-105">Parameters</span></span>  
 <span data-ttu-id="fe3f2-106">スタックの上位 2 項目。</span><span class="sxs-lookup"><span data-stu-id="fe3f2-106">Top two items on the stack.</span></span>  
  
## <a name="pushed-value"></a><span data-ttu-id="fe3f2-107">プッシュされた値</span><span class="sxs-lookup"><span data-stu-id="fe3f2-107">Pushed Value</span></span>  
 <span data-ttu-id="fe3f2-108">比較演算の結果を文字列します。</span><span class="sxs-lookup"><span data-stu-id="fe3f2-108">String result of the comparison operation.</span></span>  
  
## <a name="remarks"></a><span data-ttu-id="fe3f2-109">コメント</span><span class="sxs-lookup"><span data-stu-id="fe3f2-109">Remarks</span></span>  
  
## <a name="example"></a><span data-ttu-id="fe3f2-110">例</span><span class="sxs-lookup"><span data-stu-id="fe3f2-110">Example</span></span>  
 <span data-ttu-id="fe3f2-111">次の例のフィルタ式を使用して、 **Equals**定数"CheckPO"には、現在のアクティビティ名を比較する操作。</span><span class="sxs-lookup"><span data-stu-id="fe3f2-111">The following example filter expression uses the **Equals** operation to compare the current activity name to the constant "CheckPO".</span></span> <span data-ttu-id="fe3f2-112">2 つが等しい場合は、式の評価が`true`します。</span><span class="sxs-lookup"><span data-stu-id="fe3f2-112">If the two are equal, the expression evaluates to `true`.</span></span>  
  
```  
<ic:Filter>  
  <ic:Expression>  
    <wf:Operation Name="GetActivityName"/>  
    <ic:Operation Name="Constant">  
      <ic:Argument>CheckPO</ic:Argument>  
    </ic:Operation>  
    <ic:Operation Name="Equals"/>  
  </ic:Expression>  
</ic:Filter>  
```  
  
 <span data-ttu-id="fe3f2-113">まったく同じで、ステートメントを記述すると、式の作成をしたくなる場合がありますC#比較を実行するときにします。</span><span class="sxs-lookup"><span data-stu-id="fe3f2-113">You may be tempted to build your expression exactly as you would write a statement in C# when performing comparisons.</span></span> <span data-ttu-id="fe3f2-114">3 つの値を比較する例。C#ように記述します。</span><span class="sxs-lookup"><span data-stu-id="fe3f2-114">For example, you might want to compare three values; in C# you would write something like:</span></span>  
  
```  
bool res = a == b == c;  
```  
  
 <span data-ttu-id="fe3f2-115">ただし、フィルタ式のモデルとして少し短くなります。</span><span class="sxs-lookup"><span data-stu-id="fe3f2-115">However, as a model for your expression filter this falls a little short.</span></span> <span data-ttu-id="fe3f2-116">代わりに、変更された (ただし、同等) のステートメントを検討してください。</span><span class="sxs-lookup"><span data-stu-id="fe3f2-116">Instead, consider the modified (but equivalent) statement:</span></span>  
  
```  
Bool res = (a == b) && (a == c);  
```  
  
 <span data-ttu-id="fe3f2-117">これには、フィルター式、比較を実行に使用するものより密接と一致します。</span><span class="sxs-lookup"><span data-stu-id="fe3f2-117">This more closely matches the filter expression you would use to perform the comparison.</span></span> <span data-ttu-id="fe3f2-118">詳細と例では、次を参照してください。[と](../core/and.md)します。</span><span class="sxs-lookup"><span data-stu-id="fe3f2-118">For more details and an example, see [And](../core/and.md).</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="fe3f2-119">参照</span><span class="sxs-lookup"><span data-stu-id="fe3f2-119">See Also</span></span>  
 [<span data-ttu-id="fe3f2-120">インターセプターの操作</span><span class="sxs-lookup"><span data-stu-id="fe3f2-120">Interceptor Operations</span></span>](../core/interceptor-operations.md)