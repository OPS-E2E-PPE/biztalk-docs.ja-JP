---
title: セキュリティで保護し、BizTalk メッセージを保護する |Microsoft ドキュメント
ms.custom: ''
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: ''
ms.suite: ''
ms.tgt_pltfrm: ''
ms.topic: article
helpviewer_keywords:
- security
ms.assetid: f2419d2a-57cf-435e-b0d0-0b0e1433d585
caps.latest.revision: 12
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: 7e73c635ce423ad77c2986bb12ebda9bfa285e68
ms.sourcegitcommit: cb908c540d8f1a692d01dc8f313e16cb4b4e696d
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 09/20/2017
---
# <a name="secure-and-protect-your-biztalk-messages"></a><span data-ttu-id="c63d9-102">セキュリティで保護し、BizTalk メッセージを保護します。</span><span class="sxs-lookup"><span data-stu-id="c63d9-102">Secure and protect your BizTalk messages</span></span>
<span data-ttu-id="c63d9-103">Microsoft® BizTalk® Server には、イントラネット内およびインターネット経由の両方で、ドキュメントを送受信するための標準のゲートウェイが用意されています。</span><span class="sxs-lookup"><span data-stu-id="c63d9-103">Microsoft® BizTalk® Server provides a standard gateway for sending and receiving documents both within an intranet and through the Internet.</span></span> <span data-ttu-id="c63d9-104">可能な基幹業務の特性により、BizTalk Server との間に送信されたメッセージがこれらのメッセージおよび送信中に、BizTalk Server プロセスとストアの中にはその両方を含まれる情報を保護するための対策を検討してください。します。</span><span class="sxs-lookup"><span data-stu-id="c63d9-104">Due to the possible business-critical nature of the messages sent to and from BizTalk Server, it is important to consider measures for securing these messages and the information they contain both as they are in transit and while BizTalk Server processes and stores them.</span></span> <span data-ttu-id="c63d9-105">ここでは、BizTalk Server のセキュリティ機能と、これらの機能を使用してデータと環境をセキュリティで保護する方法について説明します。</span><span class="sxs-lookup"><span data-stu-id="c63d9-105">This section provides information about the BizTalk Server security features, and how you can use them to secure your data and environment.</span></span>  
  
 <span data-ttu-id="c63d9-106">BizTalk Server の展開のセキュリティ保護に関する詳細については、次を参照してください。 [BizTalk Server のシステム アーキテクチャの設計](../core/designing-the-system-architectures-for-biztalk-server.md)です。</span><span class="sxs-lookup"><span data-stu-id="c63d9-106">For more information about securing a BizTalk Server deployment, see [Designing the System Architectures for BizTalk Server](../core/designing-the-system-architectures-for-biztalk-server.md).</span></span>  
  
## <a name="in-this-section"></a><span data-ttu-id="c63d9-107">このセクションの内容</span><span class="sxs-lookup"><span data-stu-id="c63d9-107">In This Section</span></span>  
  
-   [<span data-ttu-id="c63d9-108">BizTalk Server のセキュリティ機能</span><span class="sxs-lookup"><span data-stu-id="c63d9-108">Security Features in BizTalk Server</span></span>](../core/security-features-in-biztalk-server.md)  
  
-   [<span data-ttu-id="c63d9-109">メッセージ セキュリティの計画</span><span class="sxs-lookup"><span data-stu-id="c63d9-109">Planning Message Security</span></span>](../core/planning-message-security.md)  
  
-   [<span data-ttu-id="c63d9-110">アクセス制御とデータのセキュリティ</span><span class="sxs-lookup"><span data-stu-id="c63d9-110">Access Control and Data Security</span></span>](../core/access-control-and-data-security.md)