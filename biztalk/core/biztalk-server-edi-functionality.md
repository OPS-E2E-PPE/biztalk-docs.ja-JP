---
title: BizTalk Server の EDI 機能 |Microsoft Docs
ms.custom: ''
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: ''
ms.suite: ''
ms.tgt_pltfrm: ''
ms.topic: article
ms.assetid: 9fd91569-f246-40dc-acb1-4f9296479296
caps.latest.revision: 18
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: 282fcc0c2845245035e9d850c2e6fbf315e90301
ms.sourcegitcommit: d27732e569b0897361dfaebca8352aa97bb7efe1
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 05/10/2019
ms.locfileid: "65530437"
---
# <a name="biztalk-server-edi-functionality"></a><span data-ttu-id="18ae0-102">BizTalk Server の EDI 機能</span><span class="sxs-lookup"><span data-stu-id="18ae0-102">BizTalk Server EDI Functionality</span></span>
<span data-ttu-id="18ae0-103">BizTalk Server core の組み合わせを使用して EDI メッセージを処理する[!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)]機能と EDI 固有[!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)]機能します。</span><span class="sxs-lookup"><span data-stu-id="18ae0-103">BizTalk Server processes EDI messages using a combination of core [!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)] features and EDI-specific [!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)] features.</span></span> <span data-ttu-id="18ae0-104">これにより、[!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)]コア メッセージング機能を活用しながら、EDI メッセージングに固有である処理を実行します。</span><span class="sxs-lookup"><span data-stu-id="18ae0-104">This enables [!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)] to perform the processing that is unique to EDI messaging, while leveraging its core messaging functionality.</span></span>  
  
 <span data-ttu-id="18ae0-105">このセクションでは、基本的な EDI メッセージングのしくみ、および方法について説明します。[!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)]がこれを実装します。</span><span class="sxs-lookup"><span data-stu-id="18ae0-105">This section describes how basic EDI messaging works and how [!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)] implements it.</span></span> <span data-ttu-id="18ae0-106">取引先パートナー契約の定義方法も説明[!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)]EDI メッセージング、受信側の EDI 処理、および送信側の EDI 処理に利用できます。</span><span class="sxs-lookup"><span data-stu-id="18ae0-106">It also describes how a trading partner agreement definition in [!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)] can be leveraged for EDI messaging, receive-side EDI processing, and send-side EDI processing.</span></span>  
  
 <span data-ttu-id="18ae0-107">BizTalk Server との他のバージョンでの EDI 処理のサポートについての説明については[!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)]、および EDI 標準のサポートと EDI ドキュメント スキーマのサポートについては、次を参照してください。 [EDI のサポートに関する問題点](../core/edi-support-issues.md)します。</span><span class="sxs-lookup"><span data-stu-id="18ae0-107">For a description of how EDI processing is supported in BizTalk Server and other versions of [!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)], and for a description of EDI standards support and EDI document schema support, see [EDI Support Issues](../core/edi-support-issues.md).</span></span>  
  
## <a name="in-this-section"></a><span data-ttu-id="18ae0-108">このセクションの内容</span><span class="sxs-lookup"><span data-stu-id="18ae0-108">In This Section</span></span>  
  
-   [<span data-ttu-id="18ae0-109">BizTalk Server における EDI のサポート</span><span class="sxs-lookup"><span data-stu-id="18ae0-109">EDI Support in BizTalk Server</span></span>](../core/edi-support-in-biztalk-server1.md)  
  
-   [<span data-ttu-id="18ae0-110">BizTalk Server における HIPAA のサポート</span><span class="sxs-lookup"><span data-stu-id="18ae0-110">HIPAA Support in BizTalk Server</span></span>](../core/hipaa-support-in-biztalk-server.md)  
  
-   [<span data-ttu-id="18ae0-111">BizTalk Server での EDI の処理</span><span class="sxs-lookup"><span data-stu-id="18ae0-111">EDI Processing in BizTalk Server</span></span>](../core/edi-processing-in-biztalk-server.md)  
  
-   [<span data-ttu-id="18ae0-112">EDI のサポートに関する問題点</span><span class="sxs-lookup"><span data-stu-id="18ae0-112">EDI Support Issues</span></span>](../core/edi-support-issues.md)  
  
## <a name="see-also"></a><span data-ttu-id="18ae0-113">参照</span><span class="sxs-lookup"><span data-stu-id="18ae0-113">See Also</span></span>  
 <span data-ttu-id="18ae0-114">[BizTalk Server の AS2 機能](../core/biztalk-server-as2-functionality.md) </span><span class="sxs-lookup"><span data-stu-id="18ae0-114">[BizTalk Server AS2 Functionality](../core/biztalk-server-as2-functionality.md) </span></span>  
 <span data-ttu-id="18ae0-115">[EDI ソリューションのアーキテクチャ](../core/edi-solution-architecture.md) </span><span class="sxs-lookup"><span data-stu-id="18ae0-115">[EDI Solution Architecture](../core/edi-solution-architecture.md) </span></span>  
 [<span data-ttu-id="18ae0-116">BizTalk Server EDI ソリューションの開発と構成</span><span class="sxs-lookup"><span data-stu-id="18ae0-116">Developing and Configuring BizTalk Server EDI Solutions</span></span>](../core/developing-and-configuring-biztalk-server-edi-solutions.md)