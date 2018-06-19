---
title: AS2 ソリューションのアーキテクチャ |Microsoft ドキュメント
ms.custom: ''
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: ''
ms.suite: ''
ms.tgt_pltfrm: ''
ms.topic: article
ms.assetid: 41e493ba-919b-4520-9c12-92d6757984ef
caps.latest.revision: 11
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: c22557059bd13dd99e0b24a2291b7f121d561bbc
ms.sourcegitcommit: cb908c540d8f1a692d01dc8f313e16cb4b4e696d
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 09/20/2017
ms.locfileid: "22230050"
---
# <a name="as2-solution-architecture"></a><span data-ttu-id="21068-102">AS2 ソリューション アーキテクチャ</span><span class="sxs-lookup"><span data-stu-id="21068-102">AS2 Solution Architecture</span></span>
<span data-ttu-id="21068-103">AS2 処理は EDI 処理とは別個に実行されます。</span><span class="sxs-lookup"><span data-stu-id="21068-103">AS2 processing is performed separately from EDI processing.</span></span> <span data-ttu-id="21068-104">AS2 メッセージの受信、処理、受信確認の送信は EDI ペイロードの処理とは別個に行われます。</span><span class="sxs-lookup"><span data-stu-id="21068-104">AS2 messages are received, processed, and an acknowledgment sent apart from the processing of the EDI payload.</span></span> <span data-ttu-id="21068-105">したがって、AS2 処理は EDI 処理とは別個に設計され、構成されています。</span><span class="sxs-lookup"><span data-stu-id="21068-105">As a result, AS2 processing is designed and configured apart from EDI processing.</span></span> <span data-ttu-id="21068-106">また、AS2 を使用して、EDI メッセージまたは非 EDI メッセージのどちらかを転送することができます。</span><span class="sxs-lookup"><span data-stu-id="21068-106">In addition, you can use AS2 to transport either EDI messages or non-EDI messages.</span></span>  
  
 <span data-ttu-id="21068-107">このセクションでは、[!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)] のエンド ツー エンド、受信側、および送信側の処理を含む AS2 ソリューションのアーキテクチャについて説明します。</span><span class="sxs-lookup"><span data-stu-id="21068-107">This section describes the architecture of AS2 solutions on [!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)], including end-to-end, receive-side, and send-side processing.</span></span>  
  
## <a name="in-this-section"></a><span data-ttu-id="21068-108">このセクションの内容</span><span class="sxs-lookup"><span data-stu-id="21068-108">In This Section</span></span>  
  
-   [<span data-ttu-id="21068-109">AS2 メッセージング</span><span class="sxs-lookup"><span data-stu-id="21068-109">AS2 Messaging</span></span>](../core/as2-messaging.md)  
  
-   [<span data-ttu-id="21068-110">AS2 処理におけるアグリーメントのロール</span><span class="sxs-lookup"><span data-stu-id="21068-110">The Role of Agreements in AS2 Processing</span></span>](../core/the-role-of-agreements-in-as2-processing.md)  
  
-   [<span data-ttu-id="21068-111">BizTalk Server が AS2 メッセージを受信する方法</span><span class="sxs-lookup"><span data-stu-id="21068-111">How BizTalk Server Receives AS2 Messages</span></span>](../core/how-biztalk-server-receives-as2-messages.md)  
  
-   [<span data-ttu-id="21068-112">BizTalk Server が AS2 メッセージを送信する方法</span><span class="sxs-lookup"><span data-stu-id="21068-112">How BizTalk Server Sends AS2 Messages</span></span>](../core/how-biztalk-server-sends-as2-messages.md)