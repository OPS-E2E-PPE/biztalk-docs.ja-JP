---
title: SOAP ヘッダーの使用 |Microsoft Docs
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
ms.openlocfilehash: dfc28000b6a1028ad97403b9c8ae17e0a047dd98
ms.sourcegitcommit: 381e83d43796a345488d54b3f7413e11d56ad7be
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 05/07/2019
ms.locfileid: "65321690"
---
# <a name="using-soap-headers"></a><span data-ttu-id="0bdaf-102">SOAP ヘッダーの使用</span><span class="sxs-lookup"><span data-stu-id="0bdaf-102">Using SOAP Headers</span></span>
<span data-ttu-id="0bdaf-103">Microsoft BizTalk Server では、定義されていると、不明な SOAP ヘッダーのサポートを提供します。</span><span class="sxs-lookup"><span data-stu-id="0bdaf-103">Microsoft BizTalk Server provides support for defined and unknown SOAP headers.</span></span> <span data-ttu-id="0bdaf-104">定義済みの SOAP ヘッダーとは、Web サービスで明示的に指定される Web サービス記述言語 (WSDL) でのヘッダーです。</span><span class="sxs-lookup"><span data-stu-id="0bdaf-104">Defined SOAP headers are headers in the Web Service Description Language (WSDL) that are explicity stated in the Web service.</span></span> <span data-ttu-id="0bdaf-105">不明な SOAP ヘッダーは、ヘッダーを WSDL ではない Web サービスで明示的に指定します。</span><span class="sxs-lookup"><span data-stu-id="0bdaf-105">Unknown SOAP headers are headers that in the WSDL that are not explicity stated in the Web service.</span></span> <span data-ttu-id="0bdaf-106">SOAP ヘッダーの使用に関する詳細については、SOAP ヘッダーの使用"で、Microsoft .NET Framework のドキュメントでを参照してください。 [ http://go.microsoft.com/fwlink/?LinkId=25363](http://go.microsoft.com/fwlink/?LinkId=25363)します。</span><span class="sxs-lookup"><span data-stu-id="0bdaf-106">For more information about using SOAP headers, see "Using SOAP Headers" in the Microsoft .NET Framework documentation at [http://go.microsoft.com/fwlink/?LinkId=25363](http://go.microsoft.com/fwlink/?LinkId=25363).</span></span>  
  
 <span data-ttu-id="0bdaf-107">BizTalk Server では、Web サービスで定義されている各 SOAP ヘッダー コンテキスト プロパティを作成します。</span><span class="sxs-lookup"><span data-stu-id="0bdaf-107">BizTalk Server creates a context property for each defined SOAP header in the Web service.</span></span>  
  
> [!NOTE]
>  <span data-ttu-id="0bdaf-108">消費済み Web サービスのサポートは、SOAP ヘッダーを定義するだけです。Web サービスを使用するときに、不明なヘッダーを設定することはできません。</span><span class="sxs-lookup"><span data-stu-id="0bdaf-108">Consumed Web services support only defined SOAP headers.You cannot set unknown headers when consuming Web services.</span></span>  
  
## <a name="in-this-section"></a><span data-ttu-id="0bdaf-109">このセクションの内容</span><span class="sxs-lookup"><span data-stu-id="0bdaf-109">In This Section</span></span>  
  
-   [<span data-ttu-id="0bdaf-110">使用する Web サービスでの SOAP ヘッダー</span><span class="sxs-lookup"><span data-stu-id="0bdaf-110">SOAP Headers with Consumed Web Services</span></span>](../core/soap-headers-with-consumed-web-services.md)  
  
-   [<span data-ttu-id="0bdaf-111">公開済み Web サービスでの SOAP ヘッダー</span><span class="sxs-lookup"><span data-stu-id="0bdaf-111">SOAP Headers with Published Web Services</span></span>](../core/soap-headers-with-published-web-services.md)