---
title: BizTalk Server が EDI メッセージを送信する方法 |Microsoft Docs
ms.custom: ''
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: ''
ms.suite: ''
ms.tgt_pltfrm: ''
ms.topic: article
ms.assetid: 4eaf1085-4244-4df2-9d89-52ebdf6bcbbc
caps.latest.revision: 15
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: 24d55493c8ae467886dc8fa91404a414ac55a336
ms.sourcegitcommit: 381e83d43796a345488d54b3f7413e11d56ad7be
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 05/07/2019
ms.locfileid: "65387498"
---
# <a name="how-biztalk-server-sends-edi-messages"></a><span data-ttu-id="fceb9-102">BizTalk Server が EDI メッセージを送信する方法</span><span class="sxs-lookup"><span data-stu-id="fceb9-102">How BizTalk Server Sends EDI Messages</span></span>
<span data-ttu-id="fceb9-103">[!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)]が EDI メッセージを送信すると、アグリーメント参照とスキーマ探索の実行、メッセージの検証、受信確認の送信 (該当する場合)、および EDI バッチのシリアル化が行われます。</span><span class="sxs-lookup"><span data-stu-id="fceb9-103">When [!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)] sends an EDI message, it performs agreement lookup and schema discovery, validates the message, sends an acknowledgment (if appropriate), and serializes the EDI batch.</span></span> <span data-ttu-id="fceb9-104">この処理は、EDI 送信パイプラインの EDI アセンブラーによって行われます。</span><span class="sxs-lookup"><span data-stu-id="fceb9-104">This processing is performed by the EDI assembler in the EDI Send Pipeline.</span></span>  
  
## <a name="in-this-section"></a><span data-ttu-id="fceb9-105">このセクションの内容</span><span class="sxs-lookup"><span data-stu-id="fceb9-105">In This Section</span></span>  
  
-   [<span data-ttu-id="fceb9-106">EDI 送信コンポーネント</span><span class="sxs-lookup"><span data-stu-id="fceb9-106">EDI Send Components</span></span>](../core/edi-send-components.md)  
  
-   [<span data-ttu-id="fceb9-107">送信 EDI メッセージのアグリーメントの解決とスキーマの決定</span><span class="sxs-lookup"><span data-stu-id="fceb9-107">Agreement Resolution and Schema Determination for Outgoing EDI Messages</span></span>](../core/agreement-resolution-and-schema-determination-for-outgoing-edi-messages.md)  
  
-   [<span data-ttu-id="fceb9-108">EDI アセンブラーの動作</span><span class="sxs-lookup"><span data-stu-id="fceb9-108">How the EDI Assembler Works</span></span>](../core/how-the-edi-assembler-works.md)  
  
-   [<span data-ttu-id="fceb9-109">EDI ヘッダーのオーバーライド</span><span class="sxs-lookup"><span data-stu-id="fceb9-109">Overriding EDI Headers</span></span>](../core/overriding-edi-headers.md)  
  
-   [<span data-ttu-id="fceb9-110">送信 EDI メッセージの検証</span><span class="sxs-lookup"><span data-stu-id="fceb9-110">Validation of Outgoing EDI Messages</span></span>](../core/validation-of-outgoing-edi-messages.md)  
  
-   [<span data-ttu-id="fceb9-111">送信 EDI メッセージのバッチ処理</span><span class="sxs-lookup"><span data-stu-id="fceb9-111">Batching Outgoing EDI Messages</span></span>](../core/batching-outgoing-edi-messages.md)  
  
-   [<span data-ttu-id="fceb9-112">受信した確認の処理</span><span class="sxs-lookup"><span data-stu-id="fceb9-112">Processing a Received Acknowledgment</span></span>](../core/processing-a-received-acknowledgment.md)