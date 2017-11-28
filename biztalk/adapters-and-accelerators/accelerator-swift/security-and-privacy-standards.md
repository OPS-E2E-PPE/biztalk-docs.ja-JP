---
title: "セキュリティおよびプライバシーに関する標準 |Microsoft ドキュメント"
ms.custom: 
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: 
ms.suite: 
ms.tgt_pltfrm: 
ms.topic: article
helpviewer_keywords:
- security, privacy standards
- privacy standards
- security
- security, about security
- BizTalk Accelerator for SWIFT, security
- security, BizTalk Accelerator for SWIFT
ms.assetid: 5794b25f-8a73-4f5b-97ef-1b0f61775c4b
caps.latest.revision: "7"
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: e652ff10c4ebfaf00069f3a7197dfd739eb680e1
ms.sourcegitcommit: cb908c540d8f1a692d01dc8f313e16cb4b4e696d
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 09/20/2017
---
# <a name="security-and-privacy-standards"></a><span data-ttu-id="4cfad-102">標準のセキュリティとプライバシー</span><span class="sxs-lookup"><span data-stu-id="4cfad-102">Security and privacy standards</span></span>
<span data-ttu-id="4cfad-103">財務アプリケーションはサービスとの統合ソリューションを使用して開発[!INCLUDE[btsCoName](../../includes/btsconame-md.md)][!INCLUDE[A4SWIFT_CurrentVersion_FirstRef](../../includes/a4swift-currentversion-firstref-md.md)]ネイティブによって一般的に保護された[!INCLUDE[btsBizTalkServerNoVersion](../../includes/btsbiztalkservernoversion-md.md)]セキュリティ機能です。</span><span class="sxs-lookup"><span data-stu-id="4cfad-103">Financial Services applications and integration solutions developed using [!INCLUDE[btsCoName](../../includes/btsconame-md.md)][!INCLUDE[A4SWIFT_CurrentVersion_FirstRef](../../includes/a4swift-currentversion-firstref-md.md)] are generally secured by native [!INCLUDE[btsBizTalkServerNoVersion](../../includes/btsbiztalkservernoversion-md.md)] security features.</span></span> [!INCLUDE[btsBizTalkServerNoVersion](../../includes/btsbiztalkservernoversion-md.md)]<span data-ttu-id="4cfad-104">など、事実上インターネット暗号化メッセージングの標準とトランスポート プロトコル、署名証明書、積極的なセキュリティ メカニズムを使用して[!INCLUDE[btsWinNoVersion](../../includes/btswinnoversion-md.md)]認証、およびエンタープライズ シングル サインオンをセキュリティで保護[!INCLUDE[btsBizTalkServerNoVersion](../../includes/btsbiztalkservernoversion-md.md)]アプリケーション、データ、およびランタイム。</span><span class="sxs-lookup"><span data-stu-id="4cfad-104"> uses aggressive security mechanisms such as de facto Internet encrypted messaging standards and transport protocols, signing certificates, [!INCLUDE[btsWinNoVersion](../../includes/btswinnoversion-md.md)] Authentication, and Enterprise Single Sign-On to secure [!INCLUDE[btsBizTalkServerNoVersion](../../includes/btsbiztalkservernoversion-md.md)] applications, data, and runtime.</span></span>  
  
 <span data-ttu-id="4cfad-105">ソリューションでビルドされた[!INCLUDE[btsCoName](../../includes/btsconame-md.md)] [!INCLUDE[btsWinNoVersion](../../includes/btswinnoversion-md.md)] 2000 [!INCLUDE[btsBizTalkServerNoVersion](../../includes/btsbiztalkservernoversion-md.md)]A4SWIFT に役立つことが世界銀行間財務通信 (SWIFT) の財務トランザクションの Society のセキュリティとプライバシーのガイドラインを満たしているとします。</span><span class="sxs-lookup"><span data-stu-id="4cfad-105">Solutions built with [!INCLUDE[btsCoName](../../includes/btsconame-md.md)][!INCLUDE[btsWinNoVersion](../../includes/btswinnoversion-md.md)] 2000, [!INCLUDE[btsBizTalkServerNoVersion](../../includes/btsbiztalkservernoversion-md.md)], and A4SWIFT can help you to meet the security and privacy guidelines for Society for Worldwide Interbank Financial Telecommunication (SWIFT) financial transactions.</span></span>  
  
 <span data-ttu-id="4cfad-106">ネイティブに加えて[!INCLUDE[btsBizTalkServerNoVersion](../../includes/btsbiztalkservernoversion-md.md)]セキュリティ機能、A4SWIFT がエンドユーザー メッセージ エントリ、修復、承認、および SWIFT メッセージの送信のセキュリティ保護に固有のユーザー レベルのセキュリティを提供します。</span><span class="sxs-lookup"><span data-stu-id="4cfad-106">In addition to native [!INCLUDE[btsBizTalkServerNoVersion](../../includes/btsbiztalkservernoversion-md.md)] security features, A4SWIFT provides user-level security specific to securing end-user message entry, repair, approval, and submission of SWIFT messages.</span></span> <span data-ttu-id="4cfad-107">このセキュリティを使用して達成される[!INCLUDE[btsInpathNoVersion](../../includes/btsinpathnoversion-md.md)]のデジタル署名のテクノロジ、A4SWIFT ランタイム サービスを使用して証明書とデータの整合性を確認します。</span><span class="sxs-lookup"><span data-stu-id="4cfad-107">This security is achieved by using [!INCLUDE[btsInpathNoVersion](../../includes/btsinpathnoversion-md.md)] digital signing technologies and by using A4SWIFT runtime services to verify certificate and data integrity.</span></span>  
  
 <span data-ttu-id="4cfad-108">SWIFT メッセージとは、入力またはエンドユーザー、および接続中に、移動中の編集が含まれている情報を保護するための対策を検討することが重要[!INCLUDE[btsBizTalkServerNoVersion](../../includes/btsbiztalkservernoversion-md.md)]を処理し、それらを格納します。</span><span class="sxs-lookup"><span data-stu-id="4cfad-108">It is important to consider measures for securing your SWIFT messages and the information they contain when they are entered or edited by end-users, in transit, and while [!INCLUDE[btsBizTalkServerNoVersion](../../includes/btsbiztalkservernoversion-md.md)] processes and stores them.</span></span>  
  
 <span data-ttu-id="4cfad-109">同時に、[!INCLUDE[btsBizTalkServer2006r3](../../includes/btsbiztalkserver2006r3-md.md)]し、設計、開発、および実行するシステムのセキュリティ保護 SWIFT メッセージングとワークフローの自動化のプラットフォーム、インフラストラクチャ、およびツールを A4SWIFT が提供されます。</span><span class="sxs-lookup"><span data-stu-id="4cfad-109">Together, [!INCLUDE[btsBizTalkServer2006r3](../../includes/btsbiztalkserver2006r3-md.md)] and A4SWIFT provide the platform, infrastructure, and tools for designing, developing, and executing secure SWIFT messaging and workflow automation systems.</span></span>  
  
 <span data-ttu-id="4cfad-110">セキュリティを実装する場合は、設計および多くの領域を開発する必要があります。</span><span class="sxs-lookup"><span data-stu-id="4cfad-110">When implementing security, you must design and develop many areas.</span></span> <span data-ttu-id="4cfad-111">次に、これらの領域の概要を示します。</span><span class="sxs-lookup"><span data-stu-id="4cfad-111">The following list is a high-level view of these areas:</span></span>  
  
-   <span data-ttu-id="4cfad-112">IT セキュリティ ポリシーを作成します。</span><span class="sxs-lookup"><span data-stu-id="4cfad-112">Develop an IT security policy</span></span>  
  
-   <span data-ttu-id="4cfad-113">設計および実装防御戦略</span><span class="sxs-lookup"><span data-stu-id="4cfad-113">Design and implement a defense strategy</span></span>  
  
-   <span data-ttu-id="4cfad-114">設計およびサーバーのロックダウン ストラテジの実装</span><span class="sxs-lookup"><span data-stu-id="4cfad-114">Design and implement a server lockdown strategy</span></span>  
  
-   <span data-ttu-id="4cfad-115">設計およびウイルス対策戦略を実装</span><span class="sxs-lookup"><span data-stu-id="4cfad-115">Design and implement an antivirus strategy</span></span>  
  
-   <span data-ttu-id="4cfad-116">デザインし実装バックアップと復元のストラテジ</span><span class="sxs-lookup"><span data-stu-id="4cfad-116">Design and implement a backup and restore strategy</span></span>  
  
-   <span data-ttu-id="4cfad-117">設計および実装の更新の管理方法</span><span class="sxs-lookup"><span data-stu-id="4cfad-117">Design and implement an update management strategy</span></span>  
  
-   <span data-ttu-id="4cfad-118">設計および監査および侵入の検出戦略を実装</span><span class="sxs-lookup"><span data-stu-id="4cfad-118">Design and implement an auditing and intrusion detection strategy</span></span>  
  
-   <span data-ttu-id="4cfad-119">インシデント レスポンス計画を設計します。</span><span class="sxs-lookup"><span data-stu-id="4cfad-119">Design an incident response plan</span></span>  
  
 <span data-ttu-id="4cfad-120">このトピックで提供される情報、上記の一覧内のすべての情報をカバーまたはしません金融サービスに準拠したソリューションを提供します。</span><span class="sxs-lookup"><span data-stu-id="4cfad-120">The information provided in this topic does not cover all the information in the preceding list or deliver a financial services-compliant solution.</span></span> <span data-ttu-id="4cfad-121">このトピックの目的は、適切な開始点を提供し、セキュリティを構造化し、包括的なアプローチの重要度をアンダー スコアを支援します。</span><span class="sxs-lookup"><span data-stu-id="4cfad-121">The purpose of this topic is to provide a good starting point and to help underscore the importance of a structured and comprehensive approach to security.</span></span>  
  
 <span data-ttu-id="4cfad-122">このセクションには、次のトピックが含まれています。</span><span class="sxs-lookup"><span data-stu-id="4cfad-122">This section contains:</span></span>  
  
-   [<span data-ttu-id="4cfad-123">BizTalk Server のセキュリティ機能</span><span class="sxs-lookup"><span data-stu-id="4cfad-123">BizTalk Server Security Features</span></span>](../../adapters-and-accelerators/accelerator-swift/biztalk-server-security-features.md)  
  
-   [<span data-ttu-id="4cfad-124">Message Repair and New Submission の A4SWIFT セキュリティ機能</span><span class="sxs-lookup"><span data-stu-id="4cfad-124">A4SWIFT Security Features for Message Repair and New Submission</span></span>](../../adapters-and-accelerators/accelerator-swift/a4swift-security-features-for-message-repair-and-new-submission.md)  
  
-   [<span data-ttu-id="4cfad-125">InfoPath のセキュリティ</span><span class="sxs-lookup"><span data-stu-id="4cfad-125">InfoPath Security</span></span>](../../adapters-and-accelerators/accelerator-swift/infopath-security.md)  
  
-   [<span data-ttu-id="4cfad-126">Server ランタイムのセキュリティ</span><span class="sxs-lookup"><span data-stu-id="4cfad-126">Server Runtime Security</span></span>](../../adapters-and-accelerators/accelerator-swift/server-runtime-security.md)  
  
-   [<span data-ttu-id="4cfad-127">Windows SharePoint Services のセキュリティ</span><span class="sxs-lookup"><span data-stu-id="4cfad-127">Windows SharePoint Services Security</span></span>](../../adapters-and-accelerators/accelerator-swift/windows-sharepoint-services-security.md)  
  
-   [<span data-ttu-id="4cfad-128">A4SWIFT Web サービスのセキュリティ</span><span class="sxs-lookup"><span data-stu-id="4cfad-128">A4SWIFT Web Service Security</span></span>](../../adapters-and-accelerators/accelerator-swift/a4swift-web-service-security.md)  
  
-   [<span data-ttu-id="4cfad-129">セキュリティの概要</span><span class="sxs-lookup"><span data-stu-id="4cfad-129">Security Summary</span></span>](../../adapters-and-accelerators/accelerator-swift/security-summary.md)