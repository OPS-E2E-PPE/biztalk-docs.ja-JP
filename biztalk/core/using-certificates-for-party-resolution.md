---
title: 証明書を使用して、パーティの解決の |Microsoft Docs
ms.custom: ''
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: ''
ms.suite: ''
ms.tgt_pltfrm: ''
ms.topic: article
ms.assetid: 4eb9b616-be1c-4b68-b3de-8721a344a423
caps.latest.revision: 9
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: 5b8ebd7023b687cd66ab0de082079330b20c2ac8
ms.sourcegitcommit: 381e83d43796a345488d54b3f7413e11d56ad7be
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 05/07/2019
ms.locfileid: "65401640"
---
# <a name="using-certificates-for-party-resolution"></a><span data-ttu-id="ace1e-102">パーティの解決の証明書の使用</span><span class="sxs-lookup"><span data-stu-id="ace1e-102">Using Certificates for Party Resolution</span></span>
<span data-ttu-id="ace1e-103">A*パーティ*はオーケストレーションと連携する BizTalk Server 外部のエンティティです。</span><span class="sxs-lookup"><span data-stu-id="ace1e-103">A *party* is an entity outside BizTalk Server that interacts with an orchestration.</span></span> <span data-ttu-id="ace1e-104">BizTalk Server では、メッセージを受信したときに、メッセージの送信者を確認して、送信者を BizTalk Server 環境での既知のパーティに解決するのには、公開キー証明書を使用します。</span><span class="sxs-lookup"><span data-stu-id="ace1e-104">When BizTalk Server receives a message, it uses the public key certificate to determine who sent the message, and to resolve the sender to a known party in the BizTalk Server environment.</span></span>  
  
 <span data-ttu-id="ace1e-105">このセクションでは、構成する方法についての情報を提供します。[!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)]パイプライン、受信場所、ポート、およびパーティの解決用の BizTalk Server 環境。</span><span class="sxs-lookup"><span data-stu-id="ace1e-105">This section provides information about how to configure [!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)] pipelines, receive locations, ports, and the BizTalk Server environment for party resolution.</span></span>  
  
 <span data-ttu-id="ace1e-106">メッセージの認証の詳細については、次を参照してください。[メッセージの送信者の認証](../core/authenticating-the-sender-of-a-message.md)します。</span><span class="sxs-lookup"><span data-stu-id="ace1e-106">For more information about authentication of a message, see [Authenticating the Sender of a Message](../core/authenticating-the-sender-of-a-message.md).</span></span>  
  
## <a name="in-this-section"></a><span data-ttu-id="ace1e-107">このセクションの内容</span><span class="sxs-lookup"><span data-stu-id="ace1e-107">In This Section</span></span>  
 [<span data-ttu-id="ace1e-108">BizTalk Server パーティの解決を構成する方法</span><span class="sxs-lookup"><span data-stu-id="ace1e-108">How to Configure BizTalk Server for Party Resolution</span></span>](../core/how-to-configure-biztalk-server-for-party-resolution.md)