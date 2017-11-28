---
title: "XPath |Microsoft ドキュメント"
ms.custom: 
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: 
ms.suite: 
ms.tgt_pltfrm: 
ms.topic: article
ms.assetid: 444b5eb9-0c00-4225-918e-b973532c67d0
caps.latest.revision: "8"
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: 2ee46838596a55512df5d1476f2c3ba34b1f5cb9
ms.sourcegitcommit: cb908c540d8f1a692d01dc8f313e16cb4b4e696d
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 09/20/2017
---
# <a name="xpath"></a><span data-ttu-id="ea03f-102">XPath</span><span class="sxs-lookup"><span data-stu-id="ea03f-102">XPath</span></span>
<span data-ttu-id="ea03f-103">XPath ステートメントで指定された値をプッシュします。</span><span class="sxs-lookup"><span data-stu-id="ea03f-103">Pushes the value indicated by an XPath statement.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="ea03f-104">構文</span><span class="sxs-lookup"><span data-stu-id="ea03f-104">Syntax</span></span>  
  
```  
  
<wcf:Operation Name="XPath">  
  <wcf:Argument>//po:POID</wcf:Argument>  
</wcf:Operation>  
```  
  
#### <a name="parameters"></a><span data-ttu-id="ea03f-105">パラメーター</span><span class="sxs-lookup"><span data-stu-id="ea03f-105">Parameters</span></span>  
 <span data-ttu-id="ea03f-106">有効な XPath ステートメント。</span><span class="sxs-lookup"><span data-stu-id="ea03f-106">Valid XPath statement.</span></span>  
  
## <a name="pushed-value"></a><span data-ttu-id="ea03f-107">プッシュされた値</span><span class="sxs-lookup"><span data-stu-id="ea03f-107">Pushed Value</span></span>  
 <span data-ttu-id="ea03f-108">XPath ステートメントの実行によって見つかった文字列値。</span><span class="sxs-lookup"><span data-stu-id="ea03f-108">String value of the result found by executing the XPath statement.</span></span>  
  
## <a name="remarks"></a><span data-ttu-id="ea03f-109">解説</span><span class="sxs-lookup"><span data-stu-id="ea03f-109">Remarks</span></span>  
 <span data-ttu-id="ea03f-110">有効な XPath ステートメントを使用する必要があります。</span><span class="sxs-lookup"><span data-stu-id="ea03f-110">You must use a valid XPath statement.</span></span>  
  
 <span data-ttu-id="ea03f-111">一致する値が複数見つかった場合は、最初に見つかった値だけが使用されます。</span><span class="sxs-lookup"><span data-stu-id="ea03f-111">In the case of multiple matches, only the first match is used.</span></span>  
  
## <a name="example"></a><span data-ttu-id="ea03f-112">例</span><span class="sxs-lookup"><span data-stu-id="ea03f-112">Example</span></span>  
 <span data-ttu-id="ea03f-113">次に示す式の例では、現在のメッセージに含まれる注文書 ID に定数 "C_" を連結することにより、関連付けの値を生成します。</span><span class="sxs-lookup"><span data-stu-id="ea03f-113">The following example expression constructs a correlation value by concatenating a constant "C_" with the purchase order ID from the current message.</span></span> <span data-ttu-id="ea03f-114">注文書 ID は、XPath 操作を使用して取得されます。</span><span class="sxs-lookup"><span data-stu-id="ea03f-114">The purchase order ID is retrieved by using the XPath operation.</span></span>  
  
```  
<ic:CorrelationID>  
  <ic:Expression>  
    <ic:Operation Name="Constant">  
      <ic:Argument>C_</ic:Argument>  
    </ic:Operation>  
    <wcf:Operation Name="XPath">  
      <wcf:Argument>//po:POID</wcf:Argument>  
    </wcf:Operation>  
    <ic:Operation Name="Concatenate" />  
  </ic:Expression>  
</ic:CorrelationID>  
```  
  
## <a name="see-also"></a><span data-ttu-id="ea03f-115">参照</span><span class="sxs-lookup"><span data-stu-id="ea03f-115">See Also</span></span>  
 [<span data-ttu-id="ea03f-116">Windows Communication Foundation での操作</span><span class="sxs-lookup"><span data-stu-id="ea03f-116">Operations in Windows Communication Foundation</span></span>](../core/operations-in-windows-communication-foundation.md)