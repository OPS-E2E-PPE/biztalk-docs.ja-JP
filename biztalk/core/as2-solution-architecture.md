---
title: AS2 ソリューションのアーキテクチャ |Microsoft Docs
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
ms.openlocfilehash: 60f25fb229a37896846f81e37c3cc71e8419d854
ms.sourcegitcommit: d27732e569b0897361dfaebca8352aa97bb7efe1
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 05/10/2019
ms.locfileid: "65528854"
---
# <a name="as2-solution-architecture"></a><span data-ttu-id="0bf0f-102">AS2 ソリューション アーキテクチャ</span><span class="sxs-lookup"><span data-stu-id="0bf0f-102">AS2 Solution Architecture</span></span>
<span data-ttu-id="0bf0f-103">AS2 処理は EDI から個別に実行を処理します。</span><span class="sxs-lookup"><span data-stu-id="0bf0f-103">AS2 processing is performed separately from EDI processing.</span></span> <span data-ttu-id="0bf0f-104">AS2 メッセージを受信、処理、および EDI ペイロードの処理とは別に受信確認の送信。</span><span class="sxs-lookup"><span data-stu-id="0bf0f-104">AS2 messages are received, processed, and an acknowledgment sent apart from the processing of the EDI payload.</span></span> <span data-ttu-id="0bf0f-105">結果として、AS2 処理が設計し、EDI 処理とは別に構成されています。</span><span class="sxs-lookup"><span data-stu-id="0bf0f-105">As a result, AS2 processing is designed and configured apart from EDI processing.</span></span> <span data-ttu-id="0bf0f-106">さらに、AS2 を使用して EDI メッセージまたは非 EDI メッセージを転送することができます。</span><span class="sxs-lookup"><span data-stu-id="0bf0f-106">In addition, you can use AS2 to transport either EDI messages or non-EDI messages.</span></span>  
  
 <span data-ttu-id="0bf0f-107">このセクションで AS2 ソリューションのアーキテクチャを説明します[!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)]エンド ツー エンド、受信側、送信側など、処理します。</span><span class="sxs-lookup"><span data-stu-id="0bf0f-107">This section describes the architecture of AS2 solutions on [!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)], including end-to-end, receive-side, and send-side processing.</span></span>  
  
## <a name="in-this-section"></a><span data-ttu-id="0bf0f-108">このセクションの内容</span><span class="sxs-lookup"><span data-stu-id="0bf0f-108">In This Section</span></span>  
  
-   [<span data-ttu-id="0bf0f-109">AS2 メッセージング</span><span class="sxs-lookup"><span data-stu-id="0bf0f-109">AS2 Messaging</span></span>](../core/as2-messaging.md)  
  
-   [<span data-ttu-id="0bf0f-110">AS2 処理におけるアグリーメントのロール</span><span class="sxs-lookup"><span data-stu-id="0bf0f-110">The Role of Agreements in AS2 Processing</span></span>](../core/the-role-of-agreements-in-as2-processing.md)  
  
-   [<span data-ttu-id="0bf0f-111">BizTalk Server が AS2 メッセージを受信する方法</span><span class="sxs-lookup"><span data-stu-id="0bf0f-111">How BizTalk Server Receives AS2 Messages</span></span>](../core/how-biztalk-server-receives-as2-messages.md)  
  
-   [<span data-ttu-id="0bf0f-112">BizTalk Server が AS2 メッセージを送信する方法</span><span class="sxs-lookup"><span data-stu-id="0bf0f-112">How BizTalk Server Sends AS2 Messages</span></span>](../core/how-biztalk-server-sends-as2-messages.md)