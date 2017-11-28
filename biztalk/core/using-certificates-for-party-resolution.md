---
title: "証明書を使用して、パーティの解決の |Microsoft ドキュメント"
ms.custom: 
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: 
ms.suite: 
ms.tgt_pltfrm: 
ms.topic: article
ms.assetid: 4eb9b616-be1c-4b68-b3de-8721a344a423
caps.latest.revision: "9"
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: b157191e4004671a8b276f47d15a8589974dfbac
ms.sourcegitcommit: cb908c540d8f1a692d01dc8f313e16cb4b4e696d
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 09/20/2017
---
# <a name="using-certificates-for-party-resolution"></a><span data-ttu-id="4f862-102">パーティの解決での証明書の使用</span><span class="sxs-lookup"><span data-stu-id="4f862-102">Using Certificates for Party Resolution</span></span>
<span data-ttu-id="4f862-103">A*パーティ*オーケストレーションと連携する BizTalk Server 外部のエンティティがします。</span><span class="sxs-lookup"><span data-stu-id="4f862-103">A *party* is an entity outside BizTalk Server that interacts with an orchestration.</span></span> <span data-ttu-id="4f862-104">BizTalk Server は、メッセージを受信すると、公開キー証明書を使用してメッセージの送信者を特定し、その送信者を BizTalk Server 環境の既知のパーティに解決します。</span><span class="sxs-lookup"><span data-stu-id="4f862-104">When BizTalk Server receives a message, it uses the public key certificate to determine who sent the message, and to resolve the sender to a known party in the BizTalk Server environment.</span></span>  
  
 <span data-ttu-id="4f862-105">ここでは、パーティの解決に使用する [!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)] パイプライン、受信場所、ポート、および BizTalk Server 環境を構成する方法について説明します。</span><span class="sxs-lookup"><span data-stu-id="4f862-105">This section provides information about how to configure [!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)] pipelines, receive locations, ports, and the BizTalk Server environment for party resolution.</span></span>  
  
 <span data-ttu-id="4f862-106">メッセージの認証の詳細については、次を参照してください。[メッセージの送信者の認証](../core/authenticating-the-sender-of-a-message.md)です。</span><span class="sxs-lookup"><span data-stu-id="4f862-106">For more information about authentication of a message, see [Authenticating the Sender of a Message](../core/authenticating-the-sender-of-a-message.md).</span></span>  
  
## <a name="in-this-section"></a><span data-ttu-id="4f862-107">このセクションの内容</span><span class="sxs-lookup"><span data-stu-id="4f862-107">In This Section</span></span>  
 [<span data-ttu-id="4f862-108">BizTalk Server パーティの解決を構成する方法</span><span class="sxs-lookup"><span data-stu-id="4f862-108">How to Configure BizTalk Server for Party Resolution</span></span>](../core/how-to-configure-biztalk-server-for-party-resolution.md)