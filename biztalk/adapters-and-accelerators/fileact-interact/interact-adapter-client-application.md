---
title: InterAct アダプターのクライアント アプリケーション |Microsoft Docs
ms.custom: ''
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: ''
ms.suite: ''
ms.tgt_pltfrm: ''
ms.topic: article
ms.assetid: cdab4624-0fc2-42a3-9867-8f77e144b40c
caps.latest.revision: 5
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: 935e7fd0672db3445e850ec470ed90e86ed8bfeb
ms.sourcegitcommit: 381e83d43796a345488d54b3f7413e11d56ad7be
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 05/07/2019
ms.locfileid: "65366939"
---
# <a name="interact-adapter-client-application"></a><span data-ttu-id="48b75-102">InterAct アダプターのクライアント アプリケーション</span><span class="sxs-lookup"><span data-stu-id="48b75-102">InterAct Adapter Client Application</span></span>
<span data-ttu-id="48b75-103">アダプター クライアントのアプリケーション要求メッセージは、クライアント側 SWIFTNet リンク (SNL) をクライアント アプリケーションから渡された XML ドキュメントを操作します。</span><span class="sxs-lookup"><span data-stu-id="48b75-103">InterAct adapter client application request messages are XML documents passed from the client application to the client-side SWIFTNet Link (SNL).</span></span> <span data-ttu-id="48b75-104">この種類のメッセージは、クライアント側で実行される要求/応答の SWIFTNet プリミティブの最初の部分として発生します。</span><span class="sxs-lookup"><span data-stu-id="48b75-104">Messages of this type occur as the first part of the SWIFTNet Request/Response primitives exercised on the client side.</span></span>  
  
 <span data-ttu-id="48b75-105">このトピックでは、SwInt:ExchangeRequest メッセージについて説明します。</span><span class="sxs-lookup"><span data-stu-id="48b75-105">This topic describes the SwInt:ExchangeRequest message.</span></span> <span data-ttu-id="48b75-106">SWIFTNet を「同期」のクライアント側の呼び出しに使用されます。</span><span class="sxs-lookup"><span data-stu-id="48b75-106">It is used for “synchronous” client-side calls to SWIFTNet.</span></span> <span data-ttu-id="48b75-107">このコンテキストでは、「同期」は意味関数呼び出しが強制的に、サーバー側のアプリケーションからの応答を受信するまで待ってから、クライアント アプリケーションをブロックします。</span><span class="sxs-lookup"><span data-stu-id="48b75-107">In this context, “synchronous” means that the function call blocks the client application, forcing it to wait until the Response is received from the server-side application.</span></span> <span data-ttu-id="48b75-108">(または、代わりに、エラーが発生し、このエラーは、クライアントに報告します。)</span><span class="sxs-lookup"><span data-stu-id="48b75-108">(Or, alternatively, an error condition occurs and that error is reported back to the client.)</span></span>  
  
 <span data-ttu-id="48b75-109">暗号のブロック (SwSec:Crypto) 存在する場合のメッセージの署名または検証処理結果を含めることができます。</span><span class="sxs-lookup"><span data-stu-id="48b75-109">The cryptographic blocks (SwSec:Crypto), if they exist, contain the results of message signing and/or verification processing.</span></span> <span data-ttu-id="48b75-110">また、特定の処理段階で、SNL によって実行される暗号化の処理を指示する命令を含めることができます、します。</span><span class="sxs-lookup"><span data-stu-id="48b75-110">Also, at certain processing stages, they may contain instructions that direct cryptographic processing that is to be performed by the SNL.</span></span>  
  
## <a name="interact-adapter-payload-format"></a><span data-ttu-id="48b75-111">アダプターのペイロード形式を対話します。</span><span class="sxs-lookup"><span data-stu-id="48b75-111">InterAct Adapter Payload Format</span></span>  
 <span data-ttu-id="48b75-112">要求ペイロードには、ビジネス メッセージの内容が含まれています。</span><span class="sxs-lookup"><span data-stu-id="48b75-112">The Request Payload contains the substance of the business message.</span></span> <span data-ttu-id="48b75-113">ペイロードの構造は、整形式 XML (つまり、ペイロードは、XML の解析を中断しませんが、そのためがない、XML ドキュメント構造を使用する) の要件に従う必要があります。</span><span class="sxs-lookup"><span data-stu-id="48b75-113">The structure of the payload must conform to the requirements of well-formed XML (this simply means that the payload does not break the XML parsing, but as such, it does not have to use the XML document structure).</span></span> <span data-ttu-id="48b75-114">SWIFTNet メッセージの検証が適用されている場合は、ペイロードが準拠するその他の構造の要件です。</span><span class="sxs-lookup"><span data-stu-id="48b75-114">If SWIFTNet Message Validation is applied, then there are other structural requirements to which the payload must conform.</span></span> <span data-ttu-id="48b75-115">別に、ペイロードの構造と内容は、業務アプリケーションによって決まります。</span><span class="sxs-lookup"><span data-stu-id="48b75-115">Aside from that, the payload structure and contents are determined by the business application.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="48b75-116">参照</span><span class="sxs-lookup"><span data-stu-id="48b75-116">See Also</span></span>  
 <span data-ttu-id="48b75-117">[InterAct アダプターのアーキテクチャ](../../adapters-and-accelerators/fileact-interact/interact-adapter-architecture.md) </span><span class="sxs-lookup"><span data-stu-id="48b75-117">[InterAct Adapter Architecture](../../adapters-and-accelerators/fileact-interact/interact-adapter-architecture.md) </span></span>  
 <span data-ttu-id="48b75-118">[InterAct アダプターのコンポーネント](../../adapters-and-accelerators/fileact-interact/interact-adapter-components.md) </span><span class="sxs-lookup"><span data-stu-id="48b75-118">[InterAct Adapter Components](../../adapters-and-accelerators/fileact-interact/interact-adapter-components.md) </span></span>  
 <span data-ttu-id="48b75-119">[業務用 Exchange 用の interAct アダプターのメッセージ](../../adapters-and-accelerators/fileact-interact/interact-adapter-messages-for-business-exchange.md) </span><span class="sxs-lookup"><span data-stu-id="48b75-119">[InterAct Adapter Messages for Business Exchange](../../adapters-and-accelerators/fileact-interact/interact-adapter-messages-for-business-exchange.md) </span></span>  
 <span data-ttu-id="48b75-120">[InterAct アダプタ サーバー アプリケーション](../../adapters-and-accelerators/fileact-interact/interact-adapter-server-application.md) </span><span class="sxs-lookup"><span data-stu-id="48b75-120">[InterAct Adapter Server Application](../../adapters-and-accelerators/fileact-interact/interact-adapter-server-application.md) </span></span>  
 <span data-ttu-id="48b75-121">[InterAct アダプター ストア アンド フォワード](../../adapters-and-accelerators/fileact-interact/interact-adapter-store-and-forward.md) </span><span class="sxs-lookup"><span data-stu-id="48b75-121">[InterAct Adapter Store and Forward](../../adapters-and-accelerators/fileact-interact/interact-adapter-store-and-forward.md) </span></span>  
 <span data-ttu-id="48b75-122">[InterAct アダプターのセキュリティ アーキテクチャ](../../adapters-and-accelerators/fileact-interact/interact-adapter-security-architecture.md) </span><span class="sxs-lookup"><span data-stu-id="48b75-122">[InterAct Adapter Security Architecture](../../adapters-and-accelerators/fileact-interact/interact-adapter-security-architecture.md) </span></span>  
 <span data-ttu-id="48b75-123">[アダプターのエンド ツー エンドの信頼性の高い配信を操作します。](../../adapters-and-accelerators/fileact-interact/interact-adapter-end-to-end-reliable-delivery.md) </span><span class="sxs-lookup"><span data-stu-id="48b75-123">[InterAct Adapter End-to-End Reliable Delivery](../../adapters-and-accelerators/fileact-interact/interact-adapter-end-to-end-reliable-delivery.md) </span></span>  
 <span data-ttu-id="48b75-124">[InterAct アダプターの状態の監視](../../adapters-and-accelerators/fileact-interact/interact-adapter-status-monitoring.md) </span><span class="sxs-lookup"><span data-stu-id="48b75-124">[InterAct Adapter Status Monitoring](../../adapters-and-accelerators/fileact-interact/interact-adapter-status-monitoring.md) </span></span>  
 [<span data-ttu-id="48b75-125">InterAct アダプターの否認不可</span><span class="sxs-lookup"><span data-stu-id="48b75-125">InterAct Adapter Non-Repudiation</span></span>](../../adapters-and-accelerators/fileact-interact/interact-adapter-non-repudiation.md)