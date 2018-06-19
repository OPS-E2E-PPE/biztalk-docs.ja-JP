---
title: 受信元インターフェイス |Microsoft ドキュメント
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
ms.openlocfilehash: 77b42530d721a6dcee52e082fe46deae9ae06405
ms.sourcegitcommit: cb908c540d8f1a692d01dc8f313e16cb4b4e696d
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 09/20/2017
ms.locfileid: "22268330"
---
# <a name="receiver-interfaces"></a><span data-ttu-id="ac5c8-102">受信元インターフェイス</span><span class="sxs-lookup"><span data-stu-id="ac5c8-102">Receiver Interfaces</span></span>
<span data-ttu-id="ac5c8-103">実装するアダプターの必要性が表示される、標準的なアダプター インターフェイスに加えて、 **IBTTransportConfig**です。</span><span class="sxs-lookup"><span data-stu-id="ac5c8-103">In addition to the standard adapter interfaces, receive adapters need to implement **IBTTransportConfig**.</span></span> <span data-ttu-id="ac5c8-104">これは、BizTalk Server メッセージング エンジンが、受信場所の構成をアダプターに送信するインターフェイスです。</span><span class="sxs-lookup"><span data-stu-id="ac5c8-104">This is the interface on which the BizTalk Messaging Engine delivers receive location configuration to the adapter.</span></span>  
  
## <a name="request-response-adapters"></a><span data-ttu-id="ac5c8-105">要求-応答アダプター</span><span class="sxs-lookup"><span data-stu-id="ac5c8-105">Request-Response Adapters</span></span>  
 <span data-ttu-id="ac5c8-106">受信アダプターでは、送信メッセージの処理が必要となる場合もあります。</span><span class="sxs-lookup"><span data-stu-id="ac5c8-106">Receive adapters may also need to handle send messages in some cases.</span></span> <span data-ttu-id="ac5c8-107">一般に、これを実行するアダプターは、双方向アダプター、つまり要求 - 応答アダプターと呼ばれます。</span><span class="sxs-lookup"><span data-stu-id="ac5c8-107">Adapters that do this are usually referred to as two-way, or Request-Response adapters.</span></span> <span data-ttu-id="ac5c8-108">メッセージを送信できるようにするには、受信アダプターを実装する必要がある**IBTTransmitter**です。</span><span class="sxs-lookup"><span data-stu-id="ac5c8-108">To be able to send messages, a receive adapter needs to implement **IBTTransmitter**.</span></span>  
  
 <span data-ttu-id="ac5c8-109">次の図は、受信アダプターによって実装されるインターフェイスを示します。</span><span class="sxs-lookup"><span data-stu-id="ac5c8-109">The following figure shows the interfaces implemented by receive adapters.</span></span>  
  
> [!NOTE]
>  <span data-ttu-id="ac5c8-110">**IBTBatchTransmitter**要求-応答アダプターのインターフェイスがサポートされていません。</span><span class="sxs-lookup"><span data-stu-id="ac5c8-110">The **IBTBatchTransmitter** interface is not supported for Request-Response adapters.</span></span>  
  
 ![](../core/media/requestresponseadapters.gif "RequestResponseAdapters")