---
title: SOAP ヘッダーで Web サービスの使用 |Microsoft ドキュメント
ms.custom: ''
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: ''
ms.suite: ''
ms.tgt_pltfrm: ''
ms.topic: article
helpviewer_keywords:
- SOAP headers, consuming
- Web services, consuming
- Web services, SOAP headers
- SOAP headers, Web services
ms.assetid: c2dfe7d8-e2f0-4bc6-b79c-354d06a7ffd6
caps.latest.revision: 8
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: 45a3efa628e435092505fdc3884704baa15be34c
ms.sourcegitcommit: cb908c540d8f1a692d01dc8f313e16cb4b4e696d
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 09/20/2017
ms.locfileid: "22237810"
---
# <a name="consuming-web-services-with-soap-headers"></a><span data-ttu-id="e38a8-102">SOAP ヘッダーで Web サービスの使用</span><span class="sxs-lookup"><span data-stu-id="e38a8-102">Consuming Web Services with SOAP Headers</span></span>
<span data-ttu-id="e38a8-103">定義済み SOAP ヘッダーで Web サービスを使用した後、これらのヘッダーは、コンテキスト プロパティとしてオーケストレーションおよびパイプライン コンポーネントで使用できるようになります。</span><span class="sxs-lookup"><span data-stu-id="e38a8-103">After you consume a Web service with defined SOAP headers, these headers become available to your orchestrations and pipeline components as context properties.</span></span> <span data-ttu-id="e38a8-104">これらのコンテキスト プロパティには、SOAP ヘッダーの文字列表現が含まれています。</span><span class="sxs-lookup"><span data-stu-id="e38a8-104">These context properties contain string representations of the SOAP headers.</span></span> <span data-ttu-id="e38a8-105">Web サービスの定義済み SOAP ヘッダーごとに、SOAP ヘッダーのルート要素に対応する名前を使用してコンテキスト プロパティを作成できます。</span><span class="sxs-lookup"><span data-stu-id="e38a8-105">For each defined SOAP header in the Web service, you can create a context property by using the name that corresponds to the root element of the SOAP header.</span></span> <span data-ttu-id="e38a8-106">定義済みのすべての SOAP ヘッダー コンテキスト プロパティが、 **http://schemas.microsoft.com/BizTalk/2003/SOAPHeader**名前空間。</span><span class="sxs-lookup"><span data-stu-id="e38a8-106">All defined SOAP header context properties are in the **http://schemas.microsoft.com/BizTalk/2003/SOAPHeader** namespace.</span></span>  
  
 <span data-ttu-id="e38a8-107">次の例は、SOAP ヘッダー コンテキスト プロパティを作成する方法を示しています**OrigDest**例を使用して、SOAP ヘッダーで[消費される Web サービスでの SOAP ヘッダー](../core/soap-headers-with-consumed-web-services.md):。</span><span class="sxs-lookup"><span data-stu-id="e38a8-107">The following example shows how to create a SOAP header context property **OrigDest** using the SOAP header example in [SOAP Headers with Consumed Web Services](../core/soap-headers-with-consumed-web-services.md):</span></span>  
  
```  
<?xml version="1.0" encoding="utf-16"?>  
<OrigDest xmlns:xsd="http://www.w3.org/2001/XMLSchema" xmlns:xsi="http://www.w3.org/2001/XMLSchema-instance" xmlns=" http://SOAPHeaderWS.ItemAvailability">  
   <Origination xmlns="">Home</Origination>  
      <Destination xmlns="">Work</Destination>  
</OrigDest>  
```  
  
 <span data-ttu-id="e38a8-108">応答 SOAP ヘッダーにも定義済み SOAP ヘッダーの文字列表現が含まれます。</span><span class="sxs-lookup"><span data-stu-id="e38a8-108">Response SOAP headers also contain string representations of the defined SOAP header.</span></span> <span data-ttu-id="e38a8-109">その値は、要求 SOAP ヘッダーを作成するときの値と似ています。</span><span class="sxs-lookup"><span data-stu-id="e38a8-109">The values are similar to creating a request SOAP header.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="e38a8-110">参照</span><span class="sxs-lookup"><span data-stu-id="e38a8-110">See Also</span></span>  
 [<span data-ttu-id="e38a8-111">使用する Web サービスでの SOAP ヘッダー</span><span class="sxs-lookup"><span data-stu-id="e38a8-111">SOAP Headers with Consumed Web Services</span></span>](../core/soap-headers-with-consumed-web-services.md)