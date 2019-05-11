---
title: SOAP 受信アダプター |Microsoft Docs
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
ms.openlocfilehash: 908554ad129fed6c99f4b8bb7e1b197cb4bc0ca6
ms.sourcegitcommit: 381e83d43796a345488d54b3f7413e11d56ad7be
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 05/07/2019
ms.locfileid: "65244438"
---
# <a name="soap-receive-adapter"></a><span data-ttu-id="bc79b-102">SOAP 受信アダプター</span><span class="sxs-lookup"><span data-stu-id="bc79b-102">SOAP Receive Adapter</span></span>
<span data-ttu-id="bc79b-103">SOAP を使用する受信アダプタ Web サービス要求を受信します。</span><span class="sxs-lookup"><span data-stu-id="bc79b-103">You use the SOAP receive adapter to receive Web service requests.</span></span> <span data-ttu-id="bc79b-104">SOAP 受信アダプターは、BizTalk メッセージ オブジェクトを作成し、メッセージ コンテキストに関連付けられているプロパティを昇格させます。</span><span class="sxs-lookup"><span data-stu-id="bc79b-104">The SOAP receive adapter creates a BizTalk Message object, and promotes the associated properties to the message context.</span></span>  
  
 <span data-ttu-id="bc79b-105">SOAP 受信アダプター URI は、1 つまたは複数の BizTalk オーケストレーションに関連付ける必要がありますまたはスキーマを持つ web サービスとして公開されている、 **BizTalk Web サービス公開ウィザード**します。</span><span class="sxs-lookup"><span data-stu-id="bc79b-105">A SOAP receive adapter URI must correlate to one or more BizTalk orchestrations or schemas that have been published as a web service with the **BizTalk Web Services Publishing Wizard**.</span></span> <span data-ttu-id="bc79b-106">公開済み web サービスは、BizTalk Server オーケストレーションまたはスキーマを BizTalk アセンブリ内の 1 つまたは複数と関連付けられている 1 つまたは複数の web メソッドを公開します。</span><span class="sxs-lookup"><span data-stu-id="bc79b-106">The published web service exposes one or more web methods which correlate to one or more BizTalk Server orchestrations or schemas in a BizTalk assembly.</span></span> <span data-ttu-id="bc79b-107">実際には、公開された web サービスは、BizTalk オーケストレーションまたはスキーマと転送の要求と、クライアントと、BizTalk オーケストレーションまたはスキーマの間の応答、サーバーのプロキシとして機能します。</span><span class="sxs-lookup"><span data-stu-id="bc79b-107">In effect, the published web service acts as a server proxy for the BizTalk orchestration(s) or schema(s) and forwards requests and responses between the client and the BizTalk orchestration(s) or schema(s).</span></span> <span data-ttu-id="bc79b-108">BizTalk オーケストレーションまたはスキーマを web サービスとしての発行の詳細については、次を参照してください。 [Web サービスの公開](../core/publishing-web-services.md)します。</span><span class="sxs-lookup"><span data-stu-id="bc79b-108">For more information about publishing BizTalk orchestrations or schemas as web services see [Publishing Web Services](../core/publishing-web-services.md).</span></span>  
  
 <span data-ttu-id="bc79b-109">SOAP アダプタを使用する受信場所は、一方向として構成するか、要求-応答 (双方向)。</span><span class="sxs-lookup"><span data-stu-id="bc79b-109">A receive location that uses the SOAP adapter can be configured as one-way or request response (two way).</span></span> <span data-ttu-id="bc79b-110">一方向の受信場所を構成するには、SOAP アダプターを使用すると関連付けられている web サービス、受信ポートにバインドされた BizTalk アセンブリを呼び出すクライアントに要求の状態を返します。</span><span class="sxs-lookup"><span data-stu-id="bc79b-110">When a one-way receive location is configured to use the SOAP adapter, the associated web service invokes the BizTalk assembly bound to the receive port, and returns the status of the request to the client.</span></span> <span data-ttu-id="bc79b-111">要求応答 (双方向) の受信場所を構成するには、SOAP アダプターを使用すると関連付けられている web サービス、受信ポートにバインドされた BizTalk アセンブリを呼び出すクライアントに応答ドキュメントを返します。</span><span class="sxs-lookup"><span data-stu-id="bc79b-111">When a request response (two way) receive location is configured to use the SOAP Adapter, the associated web service invokes the BizTalk assembly bound to the receive port, and returns a response document to the client.</span></span> <span data-ttu-id="bc79b-112">要求-応答メッセージングの詳細については、次を参照してください。[要求-応答メッセージング](../core/request-response-messaging.md)します。</span><span class="sxs-lookup"><span data-stu-id="bc79b-112">For more information about request response messaging see [Request-Response Messaging](../core/request-response-messaging.md).</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="bc79b-113">参照</span><span class="sxs-lookup"><span data-stu-id="bc79b-113">See Also</span></span>  
 <span data-ttu-id="bc79b-114">[SOAP アダプターとは何ですか。](../core/what-is-the-soap-adapter.md) </span><span class="sxs-lookup"><span data-stu-id="bc79b-114">[What Is the SOAP Adapter?](../core/what-is-the-soap-adapter.md) </span></span>  
 [<span data-ttu-id="bc79b-115">SOAP アダプターのセキュリティに関する推奨事項</span><span class="sxs-lookup"><span data-stu-id="bc79b-115">SOAP Adapter Security Recommendations</span></span>](../core/soap-adapter-security-recommendations.md)