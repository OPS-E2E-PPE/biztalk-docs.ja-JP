---
title: "BizTalk Server の EDI 機能 |Microsoft ドキュメント"
ms.custom: 
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: 
ms.suite: 
ms.tgt_pltfrm: 
ms.topic: article
ms.assetid: 9fd91569-f246-40dc-acb1-4f9296479296
caps.latest.revision: "18"
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: c259b3f46105afc0cf164ec0781c2c0d8f1f226b
ms.sourcegitcommit: cb908c540d8f1a692d01dc8f313e16cb4b4e696d
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 09/20/2017
---
# <a name="biztalk-server-edi-functionality"></a><span data-ttu-id="d6ffe-102">BizTalk Server の EDI 機能</span><span class="sxs-lookup"><span data-stu-id="d6ffe-102">BizTalk Server EDI Functionality</span></span>
[!INCLUDE[prague](../includes/prague-md.md)]<span data-ttu-id="d6ffe-103"> では、[!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)] のコア機能と EDI 固有の [!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)] 機能を組み合わせて、EDI メッセージを処理します。</span><span class="sxs-lookup"><span data-stu-id="d6ffe-103"> processes EDI messages using a combination of core [!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)] features and EDI-specific [!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)] features.</span></span> <span data-ttu-id="d6ffe-104">その結果、[!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)] では、コア メッセージング機能を活用する一方で、EDI メッセージングに固有の処理を実行することができます。</span><span class="sxs-lookup"><span data-stu-id="d6ffe-104">This enables [!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)] to perform the processing that is unique to EDI messaging, while leveraging its core messaging functionality.</span></span>  
  
 <span data-ttu-id="d6ffe-105">このセクションでは、基本的な EDI メッセージングのしくみ、およびそのしくみが [!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)] の EDI でどのように実装されているかについて説明します。</span><span class="sxs-lookup"><span data-stu-id="d6ffe-105">This section describes how basic EDI messaging works and how [!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)] implements it.</span></span> <span data-ttu-id="d6ffe-106">また、[!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)] における取引先アグリーメント定義が EDI メッセージング、受信側の EDI 処理、および送信側の EDI 処理でどのように利用されるかについても説明します。</span><span class="sxs-lookup"><span data-stu-id="d6ffe-106">It also describes how a trading partner agreement definition in [!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)] can be leveraged for EDI messaging, receive-side EDI processing, and send-side EDI processing.</span></span>  
  
 <span data-ttu-id="d6ffe-107">EDI 処理をサポートする方法の詳細については[!INCLUDE[prague](../includes/prague-md.md)]と他のバージョンの[!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)]、および EDI 標準のサポートと EDI ドキュメント スキーマのサポートについては、次を参照してください。 [EDI サポート問題](../core/edi-support-issues.md)です。</span><span class="sxs-lookup"><span data-stu-id="d6ffe-107">For a description of how EDI processing is supported in [!INCLUDE[prague](../includes/prague-md.md)] and other versions of [!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)], and for a description of EDI standards support and EDI document schema support, see [EDI Support Issues](../core/edi-support-issues.md).</span></span>  
  
## <a name="in-this-section"></a><span data-ttu-id="d6ffe-108">このセクションの内容</span><span class="sxs-lookup"><span data-stu-id="d6ffe-108">In This Section</span></span>  
  
-   [<span data-ttu-id="d6ffe-109">BizTalk Server における EDI のサポート</span><span class="sxs-lookup"><span data-stu-id="d6ffe-109">EDI Support in BizTalk Server</span></span>](../core/edi-support-in-biztalk-server1.md)  
  
-   [<span data-ttu-id="d6ffe-110">BizTalk Server での HIPAA サポート</span><span class="sxs-lookup"><span data-stu-id="d6ffe-110">HIPAA Support in BizTalk Server</span></span>](../core/hipaa-support-in-biztalk-server.md)  
  
-   [<span data-ttu-id="d6ffe-111">BizTalk Server での EDI 処理</span><span class="sxs-lookup"><span data-stu-id="d6ffe-111">EDI Processing in BizTalk Server</span></span>](../core/edi-processing-in-biztalk-server.md)  
  
-   [<span data-ttu-id="d6ffe-112">EDI のサポートに関する問題</span><span class="sxs-lookup"><span data-stu-id="d6ffe-112">EDI Support Issues</span></span>](../core/edi-support-issues.md)  
  
## <a name="see-also"></a><span data-ttu-id="d6ffe-113">参照</span><span class="sxs-lookup"><span data-stu-id="d6ffe-113">See Also</span></span>  
 <span data-ttu-id="d6ffe-114">[BizTalk Server の AS2 機能](../core/biztalk-server-as2-functionality.md) </span><span class="sxs-lookup"><span data-stu-id="d6ffe-114">[BizTalk Server AS2 Functionality](../core/biztalk-server-as2-functionality.md) </span></span>  
 <span data-ttu-id="d6ffe-115">[EDI ソリューションのアーキテクチャ](../core/edi-solution-architecture.md) </span><span class="sxs-lookup"><span data-stu-id="d6ffe-115">[EDI Solution Architecture](../core/edi-solution-architecture.md) </span></span>  
 [<span data-ttu-id="d6ffe-116">開発および BizTalk Server EDI ソリューションを構成します。</span><span class="sxs-lookup"><span data-stu-id="d6ffe-116">Developing and Configuring BizTalk Server EDI Solutions</span></span>](../core/developing-and-configuring-biztalk-server-edi-solutions.md)