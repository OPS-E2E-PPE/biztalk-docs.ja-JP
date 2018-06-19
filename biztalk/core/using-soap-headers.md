---
title: SOAP ヘッダーの使用 |Microsoft ドキュメント
ms.custom: ''
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: ''
ms.suite: ''
ms.tgt_pltfrm: ''
ms.topic: article
helpviewer_keywords:
- SOAP headers
- SOAP headers, about SOAP headers
- Web services, SOAP headers
ms.assetid: 816618ff-ecd8-4f12-b9a9-dbe4203411d8
caps.latest.revision: 8
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: 0671dabe7547d3f55b937a1de58241a35cb70b39
ms.sourcegitcommit: cb908c540d8f1a692d01dc8f313e16cb4b4e696d
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 09/20/2017
ms.locfileid: "22287122"
---
# <a name="using-soap-headers"></a><span data-ttu-id="55491-102">SOAP ヘッダーの使用</span><span class="sxs-lookup"><span data-stu-id="55491-102">Using SOAP Headers</span></span>
<span data-ttu-id="55491-103">Microsoft BizTalk Server は、定義されている SOAP ヘッダーと不明な SOAP ヘッダーのサポートを提供します。</span><span class="sxs-lookup"><span data-stu-id="55491-103">Microsoft BizTalk Server provides support for defined and unknown SOAP headers.</span></span> <span data-ttu-id="55491-104">定義されている SOAP ヘッダーは、Web サービスで明示的に指定されている Web サービス記述言語 (WSDL) のヘッダーです。</span><span class="sxs-lookup"><span data-stu-id="55491-104">Defined SOAP headers are headers in the Web Service Description Language (WSDL) that are explicity stated in the Web service.</span></span> <span data-ttu-id="55491-105">不明な SOAP ヘッダーは、Web サービスで明示的に指定されていない Web サービス記述言語 (WSDL) のヘッダーです。</span><span class="sxs-lookup"><span data-stu-id="55491-105">Unknown SOAP headers are headers that in the WSDL that are not explicity stated in the Web service.</span></span> <span data-ttu-id="55491-106">SOAP ヘッダーの使用の詳細については、SOAP ヘッダーの使用"Microsoft .NET Framework のドキュメントでを参照してください。 [http://go.microsoft.com/fwlink/?LinkId=25363](http://go.microsoft.com/fwlink/?LinkId=25363)です。</span><span class="sxs-lookup"><span data-stu-id="55491-106">For more information about using SOAP headers, see "Using SOAP Headers" in the Microsoft .NET Framework documentation at [http://go.microsoft.com/fwlink/?LinkId=25363](http://go.microsoft.com/fwlink/?LinkId=25363).</span></span>  
  
 <span data-ttu-id="55491-107">定義済みの各 SOAP ヘッダーのコンテキスト プロパティが BizTalk Server によって Web サービス内に作成されます。</span><span class="sxs-lookup"><span data-stu-id="55491-107">BizTalk Server creates a context property for each defined SOAP header in the Web service.</span></span>  
  
> [!NOTE]
>  <span data-ttu-id="55491-108">Web サービスは、定義されている SOAP ヘッダーのみをサポートします。Web サービスを利用するとき、不明なヘッダーを設定することはできません。</span><span class="sxs-lookup"><span data-stu-id="55491-108">Consumed Web services support only defined SOAP headers.You cannot set unknown headers when consuming Web services.</span></span>  
  
## <a name="in-this-section"></a><span data-ttu-id="55491-109">このセクションの内容</span><span class="sxs-lookup"><span data-stu-id="55491-109">In This Section</span></span>  
  
-   [<span data-ttu-id="55491-110">使用する Web サービスでの SOAP ヘッダー</span><span class="sxs-lookup"><span data-stu-id="55491-110">SOAP Headers with Consumed Web Services</span></span>](../core/soap-headers-with-consumed-web-services.md)  
  
-   [<span data-ttu-id="55491-111">公開済み Web サービスでの SOAP ヘッダー</span><span class="sxs-lookup"><span data-stu-id="55491-111">SOAP Headers with Published Web Services</span></span>](../core/soap-headers-with-published-web-services.md)