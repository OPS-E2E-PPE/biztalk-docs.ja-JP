---
title: BizTalk Server が EDI メッセージを受信する方法 |Microsoft Docs
ms.custom: ''
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: ''
ms.suite: ''
ms.tgt_pltfrm: ''
ms.topic: article
ms.assetid: 6f3bb88c-9226-4791-b100-ba68dea45278
caps.latest.revision: 18
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: d9365904b90e3e21f9903be684b33327a3fd037d
ms.sourcegitcommit: 381e83d43796a345488d54b3f7413e11d56ad7be
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 05/07/2019
ms.locfileid: "65387478"
---
# <a name="how-biztalk-server-receives-edi-messages"></a><span data-ttu-id="31ddd-102">BizTalk Server が EDI メッセージを受信する方法</span><span class="sxs-lookup"><span data-stu-id="31ddd-102">How BizTalk Server Receives EDI Messages</span></span>
<span data-ttu-id="31ddd-103">ときに[!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)]EDI メッセージを受信、受信確認 (該当する) 場合は、送信、メッセージの検証、および、EDI バッチの解析、取引先パートナー アグリーメント参照とスキーマ探索を実行します。</span><span class="sxs-lookup"><span data-stu-id="31ddd-103">When [!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)] receives an EDI message, it performs trading partner agreement lookup and schema discovery, validates the message, sends an acknowledgment (if appropriate), and parses the EDI batch.</span></span> <span data-ttu-id="31ddd-104">この処理は、EDI 受信パイプラインで EDI 逆アセンブラーが実行されます。</span><span class="sxs-lookup"><span data-stu-id="31ddd-104">This processing is performed by the EDI disassembler in the EDI Receive Pipeline.</span></span>  
  
## <a name="in-this-section"></a><span data-ttu-id="31ddd-105">このセクションの内容</span><span class="sxs-lookup"><span data-stu-id="31ddd-105">In This Section</span></span>  
  
-   [<span data-ttu-id="31ddd-106">EDI の受信コンポーネント</span><span class="sxs-lookup"><span data-stu-id="31ddd-106">EDI Receive Components</span></span>](../core/edi-receive-components.md)  
  
-   [<span data-ttu-id="31ddd-107">受信した EDI メッセージのアグリーメントの解決、スキーマ探索、および認証</span><span class="sxs-lookup"><span data-stu-id="31ddd-107">Agreement Resolution, Schema Discovery, and Authorization for Received EDI Messages</span></span>](../core/agreement-resolution-schema-discovery-and-authorization-for-received-edi.md)  
  
-   [<span data-ttu-id="31ddd-108">EDI 逆アセンブラーの動作</span><span class="sxs-lookup"><span data-stu-id="31ddd-108">How the EDI Disassembler Works</span></span>](../core/how-the-edi-disassembler-works.md)  
  
-   [<span data-ttu-id="31ddd-109">受信した EDI メッセージの検証</span><span class="sxs-lookup"><span data-stu-id="31ddd-109">Validation of Received EDI Messages</span></span>](../core/validation-of-received-edi-messages.md)  
  
-   [<span data-ttu-id="31ddd-110">EDI 受信確認の送信</span><span class="sxs-lookup"><span data-stu-id="31ddd-110">Sending an EDI Acknowledgment</span></span>](../core/sending-an-edi-acknowledgment.md)  
  
-   [<span data-ttu-id="31ddd-111">受信バッチの処理</span><span class="sxs-lookup"><span data-stu-id="31ddd-111">Processing Incoming Batches</span></span>](../core/processing-incoming-batches.md)