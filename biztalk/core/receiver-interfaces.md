---
title: 受信元インターフェイス |Microsoft Docs
ms.custom: ''
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: ''
ms.suite: ''
ms.tgt_pltfrm: ''
ms.topic: article
ms.assetid: c7ab77d4-705a-4b39-8c33-a7532ae6484c
caps.latest.revision: 11
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: 540da1fac24c69bd352a5fd0db9f2831f62f920f
ms.sourcegitcommit: 381e83d43796a345488d54b3f7413e11d56ad7be
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 05/07/2019
ms.locfileid: "65398078"
---
# <a name="receiver-interfaces"></a><span data-ttu-id="b8829-102">受信元インターフェイス</span><span class="sxs-lookup"><span data-stu-id="b8829-102">Receiver Interfaces</span></span>
<span data-ttu-id="b8829-103">標準的なアダプター インターフェイスに加えて受信アダプターが実装しなければ**IBTTransportConfig**します。</span><span class="sxs-lookup"><span data-stu-id="b8829-103">In addition to the standard adapter interfaces, receive adapters need to implement **IBTTransportConfig**.</span></span> <span data-ttu-id="b8829-104">これは、BizTalk メッセージング エンジンは受信場所の構成をアダプターにするインターフェイスです。</span><span class="sxs-lookup"><span data-stu-id="b8829-104">This is the interface on which the BizTalk Messaging Engine delivers receive location configuration to the adapter.</span></span>  
  
## <a name="request-response-adapters"></a><span data-ttu-id="b8829-105">要求-応答アダプター</span><span class="sxs-lookup"><span data-stu-id="b8829-105">Request-Response Adapters</span></span>  
 <span data-ttu-id="b8829-106">受信アダプターは、場合によっては、送信メッセージを処理する必要もあります。</span><span class="sxs-lookup"><span data-stu-id="b8829-106">Receive adapters may also need to handle send messages in some cases.</span></span> <span data-ttu-id="b8829-107">このアダプターは通常、双方向に呼ばれますまたは要求-応答アダプター。</span><span class="sxs-lookup"><span data-stu-id="b8829-107">Adapters that do this are usually referred to as two-way, or Request-Response adapters.</span></span> <span data-ttu-id="b8829-108">受信アダプターはメッセージを送信できるようにするには、実装する必要がある**IBTTransmitter**します。</span><span class="sxs-lookup"><span data-stu-id="b8829-108">To be able to send messages, a receive adapter needs to implement **IBTTransmitter**.</span></span>  
  
 <span data-ttu-id="b8829-109">次の図は、受信アダプターによって実装されるインターフェイスを示します。</span><span class="sxs-lookup"><span data-stu-id="b8829-109">The following figure shows the interfaces implemented by receive adapters.</span></span>  
  
> [!NOTE]
>  <span data-ttu-id="b8829-110">**IBTBatchTransmitter**要求-応答アダプターのインターフェイスがサポートされていません。</span><span class="sxs-lookup"><span data-stu-id="b8829-110">The **IBTBatchTransmitter** interface is not supported for Request-Response adapters.</span></span>  
  
 <span data-ttu-id="b8829-111">![](../core/media/requestresponseadapters.gif "RequestResponseAdapters")</span><span class="sxs-lookup"><span data-stu-id="b8829-111">![](../core/media/requestresponseadapters.gif "RequestResponseAdapters")</span></span>