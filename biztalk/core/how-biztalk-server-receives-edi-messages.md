---
title: "BizTalk Server が EDI メッセージを受信する方法 |Microsoft ドキュメント"
ms.custom: 
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: 
ms.suite: 
ms.tgt_pltfrm: 
ms.topic: article
ms.assetid: 6f3bb88c-9226-4791-b100-ba68dea45278
caps.latest.revision: "18"
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: eb7cdda6a54db06c0388d8c72dcb65a2c8f21f02
ms.sourcegitcommit: cb908c540d8f1a692d01dc8f313e16cb4b4e696d
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 09/20/2017
---
# <a name="how-biztalk-server-receives-edi-messages"></a><span data-ttu-id="4b474-102">BizTalk Server が EDI メッセージを受信する方法</span><span class="sxs-lookup"><span data-stu-id="4b474-102">How BizTalk Server Receives EDI Messages</span></span>
<span data-ttu-id="4b474-103">[!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)] が EDI メッセージを受信すると、取引先アグリーメント参照とスキーマ探索の実行、メッセージの検証、受信確認の送信 (該当する場合)、および EDI バッチの解析が行われます。</span><span class="sxs-lookup"><span data-stu-id="4b474-103">When [!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)] receives an EDI message, it performs trading partner agreement lookup and schema discovery, validates the message, sends an acknowledgment (if appropriate), and parses the EDI batch.</span></span> <span data-ttu-id="4b474-104">この処理は、EDI 受信パイプラインの EDI 逆アセンブラーによって行われます。</span><span class="sxs-lookup"><span data-stu-id="4b474-104">This processing is performed by the EDI disassembler in the EDI Receive Pipeline.</span></span>  
  
## <a name="in-this-section"></a><span data-ttu-id="4b474-105">このセクションの内容</span><span class="sxs-lookup"><span data-stu-id="4b474-105">In This Section</span></span>  
  
-   [<span data-ttu-id="4b474-106">EDI の受信コンポーネント</span><span class="sxs-lookup"><span data-stu-id="4b474-106">EDI Receive Components</span></span>](../core/edi-receive-components.md)  
  
-   [<span data-ttu-id="4b474-107">アグリーメントの解決、スキーマ探索、および受信した EDI メッセージの承認</span><span class="sxs-lookup"><span data-stu-id="4b474-107">Agreement Resolution, Schema Discovery, and Authorization for Received EDI Messages</span></span>](../core/agreement-resolution-schema-discovery-and-authorization-for-received-edi.md)  
  
-   [<span data-ttu-id="4b474-108">EDI 逆アセンブラーの動作方法</span><span class="sxs-lookup"><span data-stu-id="4b474-108">How the EDI Disassembler Works</span></span>](../core/how-the-edi-disassembler-works.md)  
  
-   [<span data-ttu-id="4b474-109">受信した EDI メッセージの検証</span><span class="sxs-lookup"><span data-stu-id="4b474-109">Validation of Received EDI Messages</span></span>](../core/validation-of-received-edi-messages.md)  
  
-   [<span data-ttu-id="4b474-110">EDI 受信確認を送信します。</span><span class="sxs-lookup"><span data-stu-id="4b474-110">Sending an EDI Acknowledgment</span></span>](../core/sending-an-edi-acknowledgment.md)  
  
-   [<span data-ttu-id="4b474-111">受信バッチの処理</span><span class="sxs-lookup"><span data-stu-id="4b474-111">Processing Incoming Batches</span></span>](../core/processing-incoming-batches.md)