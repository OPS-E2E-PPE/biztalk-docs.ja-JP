---
title: 標準のセキュリティとプライバシー |Microsoft Docs
ms.custom: ''
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: ''
ms.suite: ''
ms.tgt_pltfrm: ''
ms.topic: article
helpviewer_keywords:
- security, privacy standards
- privacy standards
- security
- security, about security
- BizTalk Accelerator for SWIFT, security
- security, BizTalk Accelerator for SWIFT
ms.assetid: 5794b25f-8a73-4f5b-97ef-1b0f61775c4b
caps.latest.revision: 7
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: 61daf6e28b03174af2b32a61c758a39b4cd16ff9
ms.sourcegitcommit: 266308ec5c6a9d8d80ff298ee6051b4843c5d626
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 06/27/2018
ms.locfileid: "36980603"
---
# <a name="security-and-privacy-standards"></a><span data-ttu-id="49cea-102">セキュリティおよびプライバシーに関する基準</span><span class="sxs-lookup"><span data-stu-id="49cea-102">Security and privacy standards</span></span>
<span data-ttu-id="49cea-103">金融サービス アプリケーションとの統合ソリューションは、Microsoft を使用して開発された[!INCLUDE[A4SWIFT_CurrentVersion_FirstRef](../../includes/a4swift-currentversion-firstref-md.md)]ネイティブによって一般にセキュリティ保護された[!INCLUDE[btsBizTalkServerNoVersion](../../includes/btsbiztalkservernoversion-md.md)]セキュリティ機能。</span><span class="sxs-lookup"><span data-stu-id="49cea-103">Financial Services applications and integration solutions developed using Microsoft [!INCLUDE[A4SWIFT_CurrentVersion_FirstRef](../../includes/a4swift-currentversion-firstref-md.md)] are generally secured by native [!INCLUDE[btsBizTalkServerNoVersion](../../includes/btsbiztalkservernoversion-md.md)] security features.</span></span> [!INCLUDE[btsBizTalkServerNoVersion](../../includes/btsbiztalkservernoversion-md.md)]<span data-ttu-id="49cea-104"> など、事実上インターネット暗号化メッセージ規格とトランスポート プロトコル、署名証明書、アグレッシブなセキュリティ メカニズムを使用して[!INCLUDE[btsWinNoVersion](../../includes/btswinnoversion-md.md)]認証、およびエンタープライズ シングル サインオンを保護する[!INCLUDE[btsBizTalkServerNoVersion](../../includes/btsbiztalkservernoversion-md.md)]アプリケーション、データ、およびランタイム。</span><span class="sxs-lookup"><span data-stu-id="49cea-104"> uses aggressive security mechanisms such as de facto Internet encrypted messaging standards and transport protocols, signing certificates, [!INCLUDE[btsWinNoVersion](../../includes/btswinnoversion-md.md)] Authentication, and Enterprise Single Sign-On to secure [!INCLUDE[btsBizTalkServerNoVersion](../../includes/btsbiztalkservernoversion-md.md)] applications, data, and runtime.</span></span>  

 <span data-ttu-id="49cea-105">Microsoft で構築されたソリューション[!INCLUDE[btsWinNoVersion](../../includes/btswinnoversion-md.md)]2000、 [!INCLUDE[btsBizTalkServerNoVersion](../../includes/btsbiztalkservernoversion-md.md)]A4SWIFT、社会の金融取引の世界銀行間金融電気通信 (SWIFT) のセキュリティとプライバシー ガイドラインに対応することが役立ちます。</span><span class="sxs-lookup"><span data-stu-id="49cea-105">Solutions built with Microsoft [!INCLUDE[btsWinNoVersion](../../includes/btswinnoversion-md.md)] 2000, [!INCLUDE[btsBizTalkServerNoVersion](../../includes/btsbiztalkservernoversion-md.md)], and A4SWIFT can help you to meet the security and privacy guidelines for Society for Worldwide Interbank Financial Telecommunication (SWIFT) financial transactions.</span></span>  

 <span data-ttu-id="49cea-106">ネイティブに加えて[!INCLUDE[btsBizTalkServerNoVersion](../../includes/btsbiztalkservernoversion-md.md)]セキュリティ機能、A4SWIFT エンドユーザー メッセージ エントリ、修復、承認、および SWIFT メッセージの送信のセキュリティ保護に固有のユーザー レベルのセキュリティを提供します。</span><span class="sxs-lookup"><span data-stu-id="49cea-106">In addition to native [!INCLUDE[btsBizTalkServerNoVersion](../../includes/btsbiztalkservernoversion-md.md)] security features, A4SWIFT provides user-level security specific to securing end-user message entry, repair, approval, and submission of SWIFT messages.</span></span> <span data-ttu-id="49cea-107">このセキュリティを使用して実現[!INCLUDE[btsInpathNoVersion](../../includes/btsinpathnoversion-md.md)]デジタル署名技術、A4SWIFT ランタイム サービスを使用して、証明書とデータの整合性を検証します。</span><span class="sxs-lookup"><span data-stu-id="49cea-107">This security is achieved by using [!INCLUDE[btsInpathNoVersion](../../includes/btsinpathnoversion-md.md)] digital signing technologies and by using A4SWIFT runtime services to verify certificate and data integrity.</span></span>  

 <span data-ttu-id="49cea-108">SWIFT メッセージとは、入力または編集中に、中に、エンドユーザーが含まれている情報を保護するための対策を検討することが重要[!INCLUDE[btsBizTalkServerNoVersion](../../includes/btsbiztalkservernoversion-md.md)]を処理し、それらを格納します。</span><span class="sxs-lookup"><span data-stu-id="49cea-108">It is important to consider measures for securing your SWIFT messages and the information they contain when they are entered or edited by end-users, in transit, and while [!INCLUDE[btsBizTalkServerNoVersion](../../includes/btsbiztalkservernoversion-md.md)] processes and stores them.</span></span>  

 <span data-ttu-id="49cea-109">同時に、BizTalk Server と A4SWIFT は、プラットフォーム、インフラストラクチャ、および設計、開発、およびセキュリティで保護された SWIFT のメッセージングとワークフロー オートメーション システムを実行するためのツールを提供します。</span><span class="sxs-lookup"><span data-stu-id="49cea-109">Together, BizTalk Server and A4SWIFT provide the platform, infrastructure, and tools for designing, developing, and executing secure SWIFT messaging and workflow automation systems.</span></span>  

 <span data-ttu-id="49cea-110">セキュリティを実装する場合は、設計および多くの領域を開発する必要があります。</span><span class="sxs-lookup"><span data-stu-id="49cea-110">When implementing security, you must design and develop many areas.</span></span> <span data-ttu-id="49cea-111">次に、これらの領域の概要を示します。</span><span class="sxs-lookup"><span data-stu-id="49cea-111">The following list is a high-level view of these areas:</span></span>  

- <span data-ttu-id="49cea-112">IT セキュリティ ポリシーを作成します。</span><span class="sxs-lookup"><span data-stu-id="49cea-112">Develop an IT security policy</span></span>  

- <span data-ttu-id="49cea-113">設計および多層防御戦略の実装</span><span class="sxs-lookup"><span data-stu-id="49cea-113">Design and implement a defense strategy</span></span>  

- <span data-ttu-id="49cea-114">設計およびサーバーのロックダウン ストラテジの実装</span><span class="sxs-lookup"><span data-stu-id="49cea-114">Design and implement a server lockdown strategy</span></span>  

- <span data-ttu-id="49cea-115">設計およびウイルス対策の戦略の実装</span><span class="sxs-lookup"><span data-stu-id="49cea-115">Design and implement an antivirus strategy</span></span>  

- <span data-ttu-id="49cea-116">設計し実装のバックアップと復元の方法</span><span class="sxs-lookup"><span data-stu-id="49cea-116">Design and implement a backup and restore strategy</span></span>  

- <span data-ttu-id="49cea-117">設計および更新プログラムの管理戦略の実装</span><span class="sxs-lookup"><span data-stu-id="49cea-117">Design and implement an update management strategy</span></span>  

- <span data-ttu-id="49cea-118">設計および監査および侵入の検出戦略の実装</span><span class="sxs-lookup"><span data-stu-id="49cea-118">Design and implement an auditing and intrusion detection strategy</span></span>  

- <span data-ttu-id="49cea-119">インシデント対応計画を設計します。</span><span class="sxs-lookup"><span data-stu-id="49cea-119">Design an incident response plan</span></span>  

  <span data-ttu-id="49cea-120">このトピックで提供される情報は、上記のすべての情報または、金融サービス準拠のソリューションを提供はできません。</span><span class="sxs-lookup"><span data-stu-id="49cea-120">The information provided in this topic does not cover all the information in the preceding list or deliver a financial services-compliant solution.</span></span> <span data-ttu-id="49cea-121">このトピックの目的には、適切な開始点を提供しに役立つセキュリティへの包括的な構造化アプローチの重要度をアンダー スコアです。</span><span class="sxs-lookup"><span data-stu-id="49cea-121">The purpose of this topic is to provide a good starting point and to help underscore the importance of a structured and comprehensive approach to security.</span></span>  

  <span data-ttu-id="49cea-122">このセクションには、次のトピックが含まれています。</span><span class="sxs-lookup"><span data-stu-id="49cea-122">This section contains:</span></span>  

- [<span data-ttu-id="49cea-123">BizTalk Server のセキュリティ機能</span><span class="sxs-lookup"><span data-stu-id="49cea-123">BizTalk Server Security Features</span></span>](../../adapters-and-accelerators/accelerator-swift/biztalk-server-security-features.md)  

- [<span data-ttu-id="49cea-124">Message Repair and New Submission の A4SWIFT セキュリティ機能</span><span class="sxs-lookup"><span data-stu-id="49cea-124">A4SWIFT Security Features for Message Repair and New Submission</span></span>](../../adapters-and-accelerators/accelerator-swift/a4swift-security-features-for-message-repair-and-new-submission.md)  

- [<span data-ttu-id="49cea-125">InfoPath のセキュリティ</span><span class="sxs-lookup"><span data-stu-id="49cea-125">InfoPath Security</span></span>](../../adapters-and-accelerators/accelerator-swift/infopath-security.md)  

- [<span data-ttu-id="49cea-126">Server ランタイムのセキュリティ</span><span class="sxs-lookup"><span data-stu-id="49cea-126">Server Runtime Security</span></span>](../../adapters-and-accelerators/accelerator-swift/server-runtime-security.md)  

- [<span data-ttu-id="49cea-127">Windows SharePoint Services のセキュリティ</span><span class="sxs-lookup"><span data-stu-id="49cea-127">Windows SharePoint Services Security</span></span>](../../adapters-and-accelerators/accelerator-swift/windows-sharepoint-services-security.md)  

- [<span data-ttu-id="49cea-128">A4SWIFT Web サービスのセキュリティ</span><span class="sxs-lookup"><span data-stu-id="49cea-128">A4SWIFT Web Service Security</span></span>](../../adapters-and-accelerators/accelerator-swift/a4swift-web-service-security.md)  

- [<span data-ttu-id="49cea-129">セキュリティの概要</span><span class="sxs-lookup"><span data-stu-id="49cea-129">Security Summary</span></span>](../../adapters-and-accelerators/accelerator-swift/security-summary.md)
