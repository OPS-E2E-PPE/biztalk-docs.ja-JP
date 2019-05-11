---
title: BizTalk Server の AS2 機能 |Microsoft Docs
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
ms.openlocfilehash: 0511c6f134588097078d99f86261f283880f3fe0
ms.sourcegitcommit: d27732e569b0897361dfaebca8352aa97bb7efe1
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 05/10/2019
ms.locfileid: "65530417"
---
# <a name="biztalk-server-as2-functionality"></a><span data-ttu-id="35dd0-102">BizTalk Server の AS2 機能</span><span class="sxs-lookup"><span data-stu-id="35dd0-102">BizTalk Server AS2 Functionality</span></span>
[!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)] <span data-ttu-id="35dd0-103">BizTalk Server の機能と AS2 固有の BizTalk Server 機能のコアの組み合わせを使用して AS2 メッセージを処理します。</span><span class="sxs-lookup"><span data-stu-id="35dd0-103">processes AS2 messages using a combination of core BizTalk Server features and AS2-specific BizTalk Server features.</span></span> <span data-ttu-id="35dd0-104">これにより、BizTalk Server では、コア メッセージング機能を活用しながら、AS2 メッセージングに固有の処理を実行できます。</span><span class="sxs-lookup"><span data-stu-id="35dd0-104">This enables BizTalk Server to perform the processing that is unique to AS2 messaging, while leveraging its core messaging functionality.</span></span> <span data-ttu-id="35dd0-105">EDI ドキュメントは EDI 固有の機能の一部には、AS2 経由で転送される場合[!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)]も使用されます。</span><span class="sxs-lookup"><span data-stu-id="35dd0-105">If EDI documents are transported over AS2, some of the EDI-specific functionality in [!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)] will also be used.</span></span>  
  
 <span data-ttu-id="35dd0-106">このセクションでは、基本的な AS2 メッセージングについて説明しますとどのように[!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)]がこれを実装します。</span><span class="sxs-lookup"><span data-stu-id="35dd0-106">This section describes basic AS2 messaging and how [!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)] implements it.</span></span> <span data-ttu-id="35dd0-107">また、パートナーの取引先アグリーメント定義を利用して、AS2 処理、受信側 AS2 処理、および送信側 AS2 処理の方法も説明します。</span><span class="sxs-lookup"><span data-stu-id="35dd0-107">It also describes how a trading partner agreement definition can be leveraged for AS2 processing, receive-side AS2 processing, and send-side AS2 processing.</span></span>  
  
## <a name="in-this-section"></a><span data-ttu-id="35dd0-108">このセクションの内容</span><span class="sxs-lookup"><span data-stu-id="35dd0-108">In This Section</span></span>  
  
-   [<span data-ttu-id="35dd0-109">BizTalk Server における AS2 のサポート</span><span class="sxs-lookup"><span data-stu-id="35dd0-109">AS2 Support in BizTalk Server</span></span>](../core/as2-support-in-biztalk-server.md)  
  
-   [<span data-ttu-id="35dd0-110">BizTalk Server での AS2 処理</span><span class="sxs-lookup"><span data-stu-id="35dd0-110">AS2 Processing in BizTalk Server</span></span>](../core/as2-processing-in-biztalk-server.md)  
  
## <a name="see-also"></a><span data-ttu-id="35dd0-111">参照</span><span class="sxs-lookup"><span data-stu-id="35dd0-111">See Also</span></span>  
 <span data-ttu-id="35dd0-112">[BizTalk Server の EDI 機能](../core/biztalk-server-edi-functionality.md) </span><span class="sxs-lookup"><span data-stu-id="35dd0-112">[BizTalk Server EDI Functionality](../core/biztalk-server-edi-functionality.md) </span></span>  
 [<span data-ttu-id="35dd0-113">AS2 ソリューション アーキテクチャ</span><span class="sxs-lookup"><span data-stu-id="35dd0-113">AS2 Solution Architecture</span></span>](../core/as2-solution-architecture.md)