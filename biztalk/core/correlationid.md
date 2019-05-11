---
title: CorrelationID | Microsoft Docs
ms.custom: ''
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: ''
ms.suite: ''
ms.tgt_pltfrm: ''
ms.topic: article
ms.assetid: b4faf210-7e7f-450d-8bb1-84d3d31c3022
caps.latest.revision: 7
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: 374ae165d48e1d91bc60d83a285df3b0f3594357
ms.sourcegitcommit: 381e83d43796a345488d54b3f7413e11d56ad7be
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 05/07/2019
ms.locfileid: "65354424"
---
# <a name="correlationid"></a><span data-ttu-id="630be-102">CorrelationID</span><span class="sxs-lookup"><span data-stu-id="630be-102">CorrelationID</span></span>
<span data-ttu-id="630be-103">`CorrelationID`要素を使用して、メッセージの相関 ID を指定します。</span><span class="sxs-lookup"><span data-stu-id="630be-103">The `CorrelationID` element is used to specify a correlation ID for a message.</span></span>  
  
## <a name="format"></a><span data-ttu-id="630be-104">形式</span><span class="sxs-lookup"><span data-stu-id="630be-104">Format</span></span>  
 <span data-ttu-id="630be-105">`CorrelationID`要素から成る、 `Expression` 1 つまたは複数を使用する要素`Operation`相関 ID として使用する文字列を指定する要素</span><span class="sxs-lookup"><span data-stu-id="630be-105">The `CorrelationID` element consists of an `Expression` element that uses one or more `Operation` elements to specify the string to use as the correlation ID.</span></span>  
  
```  
<ic:CorrelationID>  
  <ic:Expression>  
    <!-- Operations -->  
  </ic:Expression>  
</ic:CorrelationID>  
```  
  
## <a name="remarks"></a><span data-ttu-id="630be-106">コメント</span><span class="sxs-lookup"><span data-stu-id="630be-106">Remarks</span></span>  
 <span data-ttu-id="630be-107">次の一般的な操作は、関連付け ID 式では使用できません。</span><span class="sxs-lookup"><span data-stu-id="630be-107">The following common operations are not allowed in correlation ID expressions:</span></span>  
  
-   <span data-ttu-id="630be-108">And</span><span class="sxs-lookup"><span data-stu-id="630be-108">And</span></span>  
  
-   <span data-ttu-id="630be-109">[等しい]</span><span class="sxs-lookup"><span data-stu-id="630be-109">Equals</span></span>  
  
## <a name="example"></a><span data-ttu-id="630be-110">例</span><span class="sxs-lookup"><span data-stu-id="630be-110">Example</span></span>  
 <span data-ttu-id="630be-111">次の Workflow Foundation (WF) インターセプタ サンプルの構成ブロックは、相関関係を確立するには、"OrderNum"の id。</span><span class="sxs-lookup"><span data-stu-id="630be-111">The following Workflow Foundation (WF) interceptor sample configuration block uses "OrderNum" to establish a correlation ID.</span></span> <span data-ttu-id="630be-112">WF と一般的な操作を使用して、ワークフローの ID を適切な相関関係を構築する高度な式を構築できます。</span><span class="sxs-lookup"><span data-stu-id="630be-112">Using the WF and common operations, you can build sophisticated expressions to construct an appropriate correlation ID for your workflow.</span></span>  
  
```  
<ic:CorrelationID>  
  <ic:Expression>  
    <wf:Operation Name="GetWorkflowProperty">  
      <wf:Argument>OrderNum</wf:Argument>  
    </wf:Operation>  
  </ic:Expression>  
</ic:CorrelationID>  
```  
  
 <span data-ttu-id="630be-113">Windows Communication Foundation (WCF) アプリケーションの場合は、相関 ID を作成するのに WCF 固有および共通の操作を使用できます。</span><span class="sxs-lookup"><span data-stu-id="630be-113">For Windows Communication Foundation (WCF) applications, you can use WCF-specific and common operations to construct a correlation ID.</span></span> <span data-ttu-id="630be-114">次のサンプルは、 **XPath**操作と XPath を関連付け ID として使用するためのメッセージからクレジット_カード番号を取得します。</span><span class="sxs-lookup"><span data-stu-id="630be-114">The following sample uses the **XPath** operation and XPath to retrieve a credit card number from a message for use as a correlation ID:</span></span>  
  
```  
<ic:CorrelationID>  
  <ic:Expression>  
    <wcf:Operation Name ="XPath">  
      <wcf:Argument>//s:Body/creditCard:CreditCardNumber</wcf:Argument>  
    </wcf:Operation>  
  </ic:Expression>  
</ic:CorrelationID>  
```  
  
## <a name="see-also"></a><span data-ttu-id="630be-115">参照</span><span class="sxs-lookup"><span data-stu-id="630be-115">See Also</span></span>  
 [<span data-ttu-id="630be-116">インターセプター OnEvent 要素</span><span class="sxs-lookup"><span data-stu-id="630be-116">Interceptor OnEvent Element</span></span>](../core/interceptor-onevent-element.md)