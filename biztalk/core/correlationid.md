---
title: "CorrelationID |Microsoft ドキュメント"
ms.custom: 
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: 
ms.suite: 
ms.tgt_pltfrm: 
ms.topic: article
ms.assetid: b4faf210-7e7f-450d-8bb1-84d3d31c3022
caps.latest.revision: "7"
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: 1192de4a49c300220ce0b297bbc1ee02ce64c6dc
ms.sourcegitcommit: cb908c540d8f1a692d01dc8f313e16cb4b4e696d
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 09/20/2017
---
# <a name="correlationid"></a><span data-ttu-id="626ec-102">CorrelationID</span><span class="sxs-lookup"><span data-stu-id="626ec-102">CorrelationID</span></span>
<span data-ttu-id="626ec-103">`CorrelationID` 要素は、メッセージの関連付け ID を指定するために使用します。</span><span class="sxs-lookup"><span data-stu-id="626ec-103">The `CorrelationID` element is used to specify a correlation ID for a message.</span></span>  
  
## <a name="format"></a><span data-ttu-id="626ec-104">Format</span><span class="sxs-lookup"><span data-stu-id="626ec-104">Format</span></span>  
 <span data-ttu-id="626ec-105">`CorrelationID` 要素は、関連付け ID として使用する文字列を指定するために 1 つまたは複数の `Expression` 要素を使用する `Operation` 要素で構成されています。</span><span class="sxs-lookup"><span data-stu-id="626ec-105">The `CorrelationID` element consists of an `Expression` element that uses one or more `Operation` elements to specify the string to use as the correlation ID.</span></span>  
  
```  
<ic:CorrelationID>  
  <ic:Expression>  
    <!-- Operations -->  
  </ic:Expression>  
</ic:CorrelationID>  
```  
  
## <a name="remarks"></a><span data-ttu-id="626ec-106">解説</span><span class="sxs-lookup"><span data-stu-id="626ec-106">Remarks</span></span>  
 <span data-ttu-id="626ec-107">次の一般的な演算は、関連付け ID 式では許可されていません。</span><span class="sxs-lookup"><span data-stu-id="626ec-107">The following common operations are not allowed in correlation ID expressions:</span></span>  
  
-   <span data-ttu-id="626ec-108">And</span><span class="sxs-lookup"><span data-stu-id="626ec-108">And</span></span>  
  
-   <span data-ttu-id="626ec-109">[等しい]</span><span class="sxs-lookup"><span data-stu-id="626ec-109">Equals</span></span>  
  
## <a name="example"></a><span data-ttu-id="626ec-110">例</span><span class="sxs-lookup"><span data-stu-id="626ec-110">Example</span></span>  
 <span data-ttu-id="626ec-111">次の Workflow Foundation (WF) インターセプタ サンプルの構成ブロックは、"OrderNum" を使用して関連付け ID を確立しています。</span><span class="sxs-lookup"><span data-stu-id="626ec-111">The following Workflow Foundation (WF) interceptor sample configuration block uses "OrderNum" to establish a correlation ID.</span></span> <span data-ttu-id="626ec-112">WF と一般的な演算により、高度な式を構築してワークフローに適した関連付け ID を作成できます。</span><span class="sxs-lookup"><span data-stu-id="626ec-112">Using the WF and common operations, you can build sophisticated expressions to construct an appropriate correlation ID for your workflow.</span></span>  
  
```  
<ic:CorrelationID>  
  <ic:Expression>  
    <wf:Operation Name="GetWorkflowProperty">  
      <wf:Argument>OrderNum</wf:Argument>  
    </wf:Operation>  
  </ic:Expression>  
</ic:CorrelationID>  
```  
  
 <span data-ttu-id="626ec-113">Windows Communication Foundation (WCF) アプリケーションについては、WCF 固有の演算と一般的な演算を使用して、関連付け ID を作成できます。</span><span class="sxs-lookup"><span data-stu-id="626ec-113">For Windows Communication Foundation (WCF) applications, you can use WCF-specific and common operations to construct a correlation ID.</span></span> <span data-ttu-id="626ec-114">次のサンプルは、 **XPath**操作と XPath 相関 ID として使用するためのメッセージからクレジット_カード番号を取得します。</span><span class="sxs-lookup"><span data-stu-id="626ec-114">The following sample uses the **XPath** operation and XPath to retrieve a credit card number from a message for use as a correlation ID:</span></span>  
  
```  
<ic:CorrelationID>  
  <ic:Expression>  
    <wcf:Operation Name ="XPath">  
      <wcf:Argument>//s:Body/creditCard:CreditCardNumber</wcf:Argument>  
    </wcf:Operation>  
  </ic:Expression>  
</ic:CorrelationID>  
```  
  
## <a name="see-also"></a><span data-ttu-id="626ec-115">参照</span><span class="sxs-lookup"><span data-stu-id="626ec-115">See Also</span></span>  
 [<span data-ttu-id="626ec-116">インターセプタ OnEvent 要素</span><span class="sxs-lookup"><span data-stu-id="626ec-116">Interceptor OnEvent Element</span></span>](../core/interceptor-onevent-element.md)