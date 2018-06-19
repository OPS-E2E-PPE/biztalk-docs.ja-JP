---
title: BizTalk Server の AS2 機能 |Microsoft ドキュメント
ms.custom: ''
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: ''
ms.suite: ''
ms.tgt_pltfrm: ''
ms.topic: article
ms.assetid: c16c017e-b68b-483b-a4af-e47eb229de00
caps.latest.revision: 13
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: c72e8acf77f57c18a87a44de365ea1ab611e49c1
ms.sourcegitcommit: cb908c540d8f1a692d01dc8f313e16cb4b4e696d
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 09/20/2017
ms.locfileid: "22231002"
---
# <a name="biztalk-server-as2-functionality"></a><span data-ttu-id="3d79c-102">BizTalk Server の AS2 機能</span><span class="sxs-lookup"><span data-stu-id="3d79c-102">BizTalk Server AS2 Functionality</span></span>
[!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)]<span data-ttu-id="3d79c-103"> は、BizTalk Server のコア機能と AS2 固有の BizTalk Server 機能を組み合わせて AS2 メッセージを処理します。</span><span class="sxs-lookup"><span data-stu-id="3d79c-103"> processes AS2 messages using a combination of core BizTalk Server features and AS2-specific BizTalk Server features.</span></span> <span data-ttu-id="3d79c-104">したがって、BizTalk Server は、コア メッセージング機能を活用すると同時に、AS2 メッセージングに固有の処理を実行することができます。</span><span class="sxs-lookup"><span data-stu-id="3d79c-104">This enables BizTalk Server to perform the processing that is unique to AS2 messaging, while leveraging its core messaging functionality.</span></span> <span data-ttu-id="3d79c-105">EDI ドキュメントが AS2 を介してトランスポートされるとき、[!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)] の EDI 固有の機能の一部も使用されます。</span><span class="sxs-lookup"><span data-stu-id="3d79c-105">If EDI documents are transported over AS2, some of the EDI-specific functionality in [!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)] will also be used.</span></span>  
  
 <span data-ttu-id="3d79c-106">このセクションでは、基本的な AS2 メッセージングと [!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)] における実装方法について説明します。</span><span class="sxs-lookup"><span data-stu-id="3d79c-106">This section describes basic AS2 messaging and how [!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)] implements it.</span></span> <span data-ttu-id="3d79c-107">また、AS2 処理、受信側 AS2 処理、および送信側 AS2 処理に取引先アグリーメント定義を利用する方法についても説明します。</span><span class="sxs-lookup"><span data-stu-id="3d79c-107">It also describes how a trading partner agreement definition can be leveraged for AS2 processing, receive-side AS2 processing, and send-side AS2 processing.</span></span>  
  
## <a name="in-this-section"></a><span data-ttu-id="3d79c-108">このセクションの内容</span><span class="sxs-lookup"><span data-stu-id="3d79c-108">In This Section</span></span>  
  
-   [<span data-ttu-id="3d79c-109">BizTalk Server における AS2 のサポート</span><span class="sxs-lookup"><span data-stu-id="3d79c-109">AS2 Support in BizTalk Server</span></span>](../core/as2-support-in-biztalk-server.md)  
  
-   [<span data-ttu-id="3d79c-110">BizTalk Server での AS2 処理</span><span class="sxs-lookup"><span data-stu-id="3d79c-110">AS2 Processing in BizTalk Server</span></span>](../core/as2-processing-in-biztalk-server.md)  
  
## <a name="see-also"></a><span data-ttu-id="3d79c-111">参照</span><span class="sxs-lookup"><span data-stu-id="3d79c-111">See Also</span></span>  
 <span data-ttu-id="3d79c-112">[BizTalk Server の EDI 機能](../core/biztalk-server-edi-functionality.md) </span><span class="sxs-lookup"><span data-stu-id="3d79c-112">[BizTalk Server EDI Functionality](../core/biztalk-server-edi-functionality.md) </span></span>  
 [<span data-ttu-id="3d79c-113">AS2 ソリューションのアーキテクチャ</span><span class="sxs-lookup"><span data-stu-id="3d79c-113">AS2 Solution Architecture</span></span>](../core/as2-solution-architecture.md)