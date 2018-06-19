---
title: SOAP 受信アダプター |Microsoft ドキュメント
ms.custom: ''
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: ''
ms.suite: ''
ms.tgt_pltfrm: ''
ms.topic: article
helpviewer_keywords:
- SOAP adapters, receive adapters
- receive adapters, SOAP adapters
ms.assetid: bb968fa8-0515-4f3a-bb39-9effb83e960c
caps.latest.revision: 8
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: 06fac19580d6083ed1b0d4be315d3285acf14fcc
ms.sourcegitcommit: cb908c540d8f1a692d01dc8f313e16cb4b4e696d
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 09/20/2017
ms.locfileid: "22278394"
---
# <a name="soap-receive-adapter"></a><span data-ttu-id="0d5f4-102">SOAP 受信アダプター</span><span class="sxs-lookup"><span data-stu-id="0d5f4-102">SOAP Receive Adapter</span></span>
<span data-ttu-id="0d5f4-103">SOAP 受信アダプターは、Web サービス要求を受信するために使用します。</span><span class="sxs-lookup"><span data-stu-id="0d5f4-103">You use the SOAP receive adapter to receive Web service requests.</span></span> <span data-ttu-id="0d5f4-104">BizTalk メッセージ オブジェクトの作成、および関連するプロパティのメッセージ コンテキストへの昇格を行います。</span><span class="sxs-lookup"><span data-stu-id="0d5f4-104">The SOAP receive adapter creates a BizTalk Message object, and promotes the associated properties to the message context.</span></span>  
  
 <span data-ttu-id="0d5f4-105">SOAP 受信アダプター URI は、1 つまたは複数の BizTalk オーケストレーションに関連付ける必要がありますまたはスキーマを持つ web サービスとして公開されている、 **BizTalk Web サービス公開ウィザード**です。</span><span class="sxs-lookup"><span data-stu-id="0d5f4-105">A SOAP receive adapter URI must correlate to one or more BizTalk orchestrations or schemas that have been published as a web service with the **BizTalk Web Services Publishing Wizard**.</span></span> <span data-ttu-id="0d5f4-106">公開された Web サービスは、BizTalk アセンブリ内の 1 つ以上の BizTalk Server オーケストレーションまたはスキーマと関連付けられている 1 つ以上の Web メソッドを公開します。</span><span class="sxs-lookup"><span data-stu-id="0d5f4-106">The published web service exposes one or more web methods which correlate to one or more BizTalk Server orchestrations or schemas in a BizTalk assembly.</span></span> <span data-ttu-id="0d5f4-107">事実上、公開された Web サービスは、BizTalk オーケストレーションまたはスキーマのサーバー プロキシとして機能し、クライアントと BizTalk オーケストレーションまたはスキーマの間で要求と応答を転送します。</span><span class="sxs-lookup"><span data-stu-id="0d5f4-107">In effect, the published web service acts as a server proxy for the BizTalk orchestration(s) or schema(s) and forwards requests and responses between the client and the BizTalk orchestration(s) or schema(s).</span></span> <span data-ttu-id="0d5f4-108">BizTalk オーケストレーションまたはスキーマを web サービスとして公開の詳細については、次を参照してください。 [Web サービスの公開](../core/publishing-web-services.md)です。</span><span class="sxs-lookup"><span data-stu-id="0d5f4-108">For more information about publishing BizTalk orchestrations or schemas as web services see [Publishing Web Services](../core/publishing-web-services.md).</span></span>  
  
 <span data-ttu-id="0d5f4-109">SOAP アダプターを使用する受信場所は、一方向または要求 - 応答 (双方向) として構成できます。</span><span class="sxs-lookup"><span data-stu-id="0d5f4-109">A receive location that uses the SOAP adapter can be configured as one-way or request response (two way).</span></span> <span data-ttu-id="0d5f4-110">SOAP アダプターを使用するように一方向の受信場所を構成した場合、関連する Web サービスによって受信ポートにバインドされた BizTalk アセンブリが呼び出され、クライアントに要求の状態が返されます。</span><span class="sxs-lookup"><span data-stu-id="0d5f4-110">When a one-way receive location is configured to use the SOAP adapter, the associated web service invokes the BizTalk assembly bound to the receive port, and returns the status of the request to the client.</span></span> <span data-ttu-id="0d5f4-111">SOAP アダプターを使用するように要求 - 応答 (双方向) の受信場所を構成した場合、関連する Web サービスによって受信ポートにバインドされた BizTalk アセンブリが呼び出され、クライアントに応答ドキュメントが返されます。</span><span class="sxs-lookup"><span data-stu-id="0d5f4-111">When a request response (two way) receive location is configured to use the SOAP Adapter, the associated web service invokes the BizTalk assembly bound to the receive port, and returns a response document to the client.</span></span> <span data-ttu-id="0d5f4-112">要求-応答メッセージングの詳細については、次を参照してください。[要求-応答のメッセージング](../core/request-response-messaging.md)です。</span><span class="sxs-lookup"><span data-stu-id="0d5f4-112">For more information about request response messaging see [Request-Response Messaging](../core/request-response-messaging.md).</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="0d5f4-113">参照</span><span class="sxs-lookup"><span data-stu-id="0d5f4-113">See Also</span></span>  
 <span data-ttu-id="0d5f4-114">[SOAP アダプターとは何ですか。](../core/what-is-the-soap-adapter.md) </span><span class="sxs-lookup"><span data-stu-id="0d5f4-114">[What Is the SOAP Adapter?](../core/what-is-the-soap-adapter.md) </span></span>  
 [<span data-ttu-id="0d5f4-115">SOAP アダプタのセキュリティに関する推奨事項</span><span class="sxs-lookup"><span data-stu-id="0d5f4-115">SOAP Adapter Security Recommendations</span></span>](../core/soap-adapter-security-recommendations.md)