---
title: 等しい |Microsoft ドキュメント
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
ms.openlocfilehash: 2b82ac5c779dc6b4d3624b48cebe9df1bc3d1966
ms.sourcegitcommit: cb908c540d8f1a692d01dc8f313e16cb4b4e696d
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 09/20/2017
ms.locfileid: "22239818"
---
# <a name="equals"></a><span data-ttu-id="de74e-102">[等しい]</span><span class="sxs-lookup"><span data-stu-id="de74e-102">Equals</span></span>
<span data-ttu-id="de74e-103">スタックから上位 2 項目を削除し、その 2 つの項目を比較して、結果をスタックにプッシュします。</span><span class="sxs-lookup"><span data-stu-id="de74e-103">Removes the top two items from the stack, compares the two items, and then pushes the result onto the stack.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="de74e-104">構文</span><span class="sxs-lookup"><span data-stu-id="de74e-104">Syntax</span></span>  
  
```  
  
<ic:Operation Name="Equals" />  
```  
  
#### <a name="parameters"></a><span data-ttu-id="de74e-105">パラメーター</span><span class="sxs-lookup"><span data-stu-id="de74e-105">Parameters</span></span>  
 <span data-ttu-id="de74e-106">スタックの上位 2 項目。</span><span class="sxs-lookup"><span data-stu-id="de74e-106">Top two items on the stack.</span></span>  
  
## <a name="pushed-value"></a><span data-ttu-id="de74e-107">プッシュされた値</span><span class="sxs-lookup"><span data-stu-id="de74e-107">Pushed Value</span></span>  
 <span data-ttu-id="de74e-108">比較演算の結果の文字列。</span><span class="sxs-lookup"><span data-stu-id="de74e-108">String result of the comparison operation.</span></span>  
  
## <a name="remarks"></a><span data-ttu-id="de74e-109">解説</span><span class="sxs-lookup"><span data-stu-id="de74e-109">Remarks</span></span>  
  
## <a name="example"></a><span data-ttu-id="de74e-110">例</span><span class="sxs-lookup"><span data-stu-id="de74e-110">Example</span></span>  
 <span data-ttu-id="de74e-111">次の例のフィルタ式を使用して、 **Equals**定数"CheckPO"には、現在のアクティビティ名を比較する操作。</span><span class="sxs-lookup"><span data-stu-id="de74e-111">The following example filter expression uses the **Equals** operation to compare the current activity name to the constant "CheckPO".</span></span> <span data-ttu-id="de74e-112">両者が等しい場合、式は `true` に評価されます。</span><span class="sxs-lookup"><span data-stu-id="de74e-112">If the two are equal, the expression evaluates to `true`.</span></span>  
  
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
  
 <span data-ttu-id="de74e-113">比較の実行時に C# でステートメントを作成する場合と同様に、フィルタ式を作成することがあります。</span><span class="sxs-lookup"><span data-stu-id="de74e-113">You may be tempted to build your expression exactly as you would write a statement in C# when performing comparisons.</span></span> <span data-ttu-id="de74e-114">たとえば、3 つの値を比較する場合、C# では次のようなステートメントを作成します。</span><span class="sxs-lookup"><span data-stu-id="de74e-114">For example, you might want to compare three values; in C# you would write something like:</span></span>  
  
```  
bool res = a == b == c;  
```  
  
 <span data-ttu-id="de74e-115">ただし、このステートメントは、フィルタ式のモデルとしては不十分です。</span><span class="sxs-lookup"><span data-stu-id="de74e-115">However, as a model for your expression filter this falls a little short.</span></span> <span data-ttu-id="de74e-116">その代わりに、次のように修正した (同等の) ステートメントを使用します。</span><span class="sxs-lookup"><span data-stu-id="de74e-116">Instead, consider the modified (but equivalent) statement:</span></span>  
  
```  
Bool res = (a == b) && (a == c);  
```  
  
 <span data-ttu-id="de74e-117">こちらの方が、比較を実行するときに使用するフィルタ式により近くなっています。</span><span class="sxs-lookup"><span data-stu-id="de74e-117">This more closely matches the filter expression you would use to perform the comparison.</span></span> <span data-ttu-id="de74e-118">詳細および例に、次を参照してください。[と](../core/and.md)です。</span><span class="sxs-lookup"><span data-stu-id="de74e-118">For more details and an example, see [And](../core/and.md).</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="de74e-119">参照</span><span class="sxs-lookup"><span data-stu-id="de74e-119">See Also</span></span>  
 [<span data-ttu-id="de74e-120">インターセプタの操作</span><span class="sxs-lookup"><span data-stu-id="de74e-120">Interceptor Operations</span></span>](../core/interceptor-operations.md)