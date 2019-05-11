---
title: Web サービスの使用 |Microsoft Docs
ms.custom: ''
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: ''
ms.suite: ''
ms.tgt_pltfrm: ''
ms.topic: article
helpviewer_keywords:
- SOAP adapters, Web services
- orchestrations, Web services
- Web services, consuming
- Web services, orchestrations
ms.assetid: 803ba623-86e7-479a-a4b6-5b576fee8825
caps.latest.revision: 9
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: 1239f54d3bd0ce71db1c77875e5b1bc852ec8bc1
ms.sourcegitcommit: 381e83d43796a345488d54b3f7413e11d56ad7be
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 05/07/2019
ms.locfileid: "65354554"
---
# <a name="consuming-web-services"></a><span data-ttu-id="6ba5e-102">Web サービスの使用</span><span class="sxs-lookup"><span data-stu-id="6ba5e-102">Consuming Web Services</span></span>
<span data-ttu-id="6ba5e-103">Web サービスの使用には、既存の Web サービス、ビジネス プロセスを追加することができます。</span><span class="sxs-lookup"><span data-stu-id="6ba5e-103">Consuming Web services enables you to add existing Web services to your business process.</span></span> <span data-ttu-id="6ba5e-104">複数の Web サービスは、1 つのオーケストレーションに集計できます。</span><span class="sxs-lookup"><span data-stu-id="6ba5e-104">You can aggregate several Web services into a single orchestration.</span></span>  
  
 <span data-ttu-id="6ba5e-105">Web ポートを使用して、オーケストレーションから (呼び出し)、Web サービスを利用できます。</span><span class="sxs-lookup"><span data-stu-id="6ba5e-105">You can consume (call) a Web service from your orchestration by using Web ports.</span></span> <span data-ttu-id="6ba5e-106">オーケストレーションから Web サービスを使用するにはするには、は、Web ポートを作成し、Web メッセージを構築します。</span><span class="sxs-lookup"><span data-stu-id="6ba5e-106">To consume a Web service from an orchestration, you create a Web port and construct Web messages.</span></span>  
  
 <span data-ttu-id="6ba5e-107">使用する Web サービスで SOAP ヘッダーを使用して、使用する Web サービスの URI を変更し、使用する Web サービスの URI を動的に設定できます。</span><span class="sxs-lookup"><span data-stu-id="6ba5e-107">You can use SOAP headers with the consumed Web service, change the URI of a consumed Web service, and dynamically set the URI for a consumed Web service.</span></span>  
  
 <span data-ttu-id="6ba5e-108">SOAP を構成する方法については、受信ハンドラーを参照してください[SOAP 受信ハンドラを構成する方法](../core/how-to-configure-a-soap-receive-handler.md)します。</span><span class="sxs-lookup"><span data-stu-id="6ba5e-108">For information about configuring a SOAP receive handler, see [How to Configure a SOAP Receive Handler](../core/how-to-configure-a-soap-receive-handler.md).</span></span> <span data-ttu-id="6ba5e-109">SOAP を構成する方法については、受信場所を参照してください[SOAP 受信場所を構成する方法](../core/how-to-configure-a-soap-receive-location.md)します。</span><span class="sxs-lookup"><span data-stu-id="6ba5e-109">For information about configuring a SOAP receive location, see [How to Configure a SOAP Receive Location](../core/how-to-configure-a-soap-receive-location.md).</span></span>  
  
## <a name="in-this-section"></a><span data-ttu-id="6ba5e-110">このセクションの内容</span><span class="sxs-lookup"><span data-stu-id="6ba5e-110">In This Section</span></span>  
  
-   [<span data-ttu-id="6ba5e-111">Web 参照の追加</span><span class="sxs-lookup"><span data-stu-id="6ba5e-111">Adding Web References</span></span>](../core/adding-web-references.md)  
  
-   [<span data-ttu-id="6ba5e-112">Web メッセージの構築</span><span class="sxs-lookup"><span data-stu-id="6ba5e-112">Constructing Web Messages</span></span>](../core/constructing-web-messages.md)  
  
-   [<span data-ttu-id="6ba5e-113">Web ポートの作成</span><span class="sxs-lookup"><span data-stu-id="6ba5e-113">Creating Web Ports</span></span>](../core/creating-web-ports.md)  
  
-   [<span data-ttu-id="6ba5e-114">Web サービスを使用する際の考慮事項</span><span class="sxs-lookup"><span data-stu-id="6ba5e-114">Considerations When Consuming Web Services</span></span>](../core/considerations-when-consuming-web-services.md)