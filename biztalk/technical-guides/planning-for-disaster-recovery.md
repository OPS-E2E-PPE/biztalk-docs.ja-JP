---
title: ディザスター リカバリーの計画 |Microsoft Docs
ms.custom: ''
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: ''
ms.suite: ''
ms.tgt_pltfrm: ''
ms.topic: article
ms.assetid: a33e8875-cfde-4a60-9dab-fc6bb3ac4f1c
caps.latest.revision: 2
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: 415064960644356db37530b87ce0f591d5a23bb9
ms.sourcegitcommit: 381e83d43796a345488d54b3f7413e11d56ad7be
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 05/07/2019
ms.locfileid: "65400707"
---
# <a name="planning-for-disaster-recovery"></a><span data-ttu-id="65334-102">ディザスター リカバリーの計画</span><span class="sxs-lookup"><span data-stu-id="65334-102">Planning for Disaster Recovery</span></span>
<span data-ttu-id="65334-103">このトピックでは、ディザスター リカバリーの要件のアプリケーション チームと BizTalk Server 用の手順のガイダンスを提供します。</span><span class="sxs-lookup"><span data-stu-id="65334-103">This topic provides guidance to application teams for disaster recovery requirements and procedures for BizTalk Server.</span></span> <span data-ttu-id="65334-104">Microsoft BizTalk Server の構成と処理の情報を格納する[!INCLUDE[btsSQLServerNoVersion](../includes/btssqlservernoversion-md.md)]します。</span><span class="sxs-lookup"><span data-stu-id="65334-104">Microsoft BizTalk Server stores configuration and processing information in [!INCLUDE[btsSQLServerNoVersion](../includes/btssqlservernoversion-md.md)].</span></span> <span data-ttu-id="65334-105">BizTalk Server の高可用性とディザスター リカバリーは、の高可用性とディザスター リカバリー機能によって実現[!INCLUDE[btsSQLServerNoVersion](../includes/btssqlservernoversion-md.md)]します。</span><span class="sxs-lookup"><span data-stu-id="65334-105">BizTalk Server high availability and disaster recovery is achieved through the high availability and disaster recovery capabilities of [!INCLUDE[btsSQLServerNoVersion](../includes/btssqlservernoversion-md.md)].</span></span>  
  
 <span data-ttu-id="65334-106">ホストされているデータベースのセットを BizTalk グループが定義されている[!INCLUDE[btsSQLServerNoVersion](../includes/btssqlservernoversion-md.md)]します。</span><span class="sxs-lookup"><span data-stu-id="65334-106">A BizTalk group is defined by a set of databases hosted in [!INCLUDE[btsSQLServerNoVersion](../includes/btssqlservernoversion-md.md)].</span></span> <span data-ttu-id="65334-107">ホストされているデータベースのセット[!INCLUDE[btsSQLServerNoVersion](../includes/btssqlservernoversion-md.md)]Windows Server クラスターを使用して高可用性を実現することができます。</span><span class="sxs-lookup"><span data-stu-id="65334-107">The set of databases hosted in [!INCLUDE[btsSQLServerNoVersion](../includes/btssqlservernoversion-md.md)] can be made highly available through the use of a Windows Server cluster.</span></span> <span data-ttu-id="65334-108">BizTalk 環境を実行しているコンピューターで[!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)]「実行時環境」と、データベースを実行するコンピューターで提供[!INCLUDE[btsSQLServerNoVersion](../includes/btssqlservernoversion-md.md)]環境の永続的なストアを提供します。</span><span class="sxs-lookup"><span data-stu-id="65334-108">In a BizTalk environment, the computers running [!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)] provide the “run-time environment” and the databases on the computers running [!INCLUDE[btsSQLServerNoVersion](../includes/btssqlservernoversion-md.md)] provide the persistent store for the environment.</span></span> <span data-ttu-id="65334-109">そのため、BizTalk Server のバックアップ、復元、およびディザスター リカバリーに重点を置いて、頻度の高い[!INCLUDE[btsSQLServerNoVersion](../includes/btssqlservernoversion-md.md)]します。</span><span class="sxs-lookup"><span data-stu-id="65334-109">Therefore, BizTalk Server backup, restore, and disaster recovery procedures are heavily focused on [!INCLUDE[btsSQLServerNoVersion](../includes/btssqlservernoversion-md.md)].</span></span>  
  
## <a name="purpose"></a><span data-ttu-id="65334-110">目的</span><span class="sxs-lookup"><span data-stu-id="65334-110">Purpose</span></span>  
 <span data-ttu-id="65334-111">このトピックでは統合[!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)]ディザスター リカバリーについては、主要なドキュメント、さまざまな Microsoft Web サイト、および情報から、[!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)]製品チームのディザスター リカバリー手順を定義する[!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)]環境。</span><span class="sxs-lookup"><span data-stu-id="65334-111">This topic consolidates [!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)] disaster recovery information from the core documentation, various Microsoft Web sites, and information from the [!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)] product team to define disaster recovery procedures for [!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)] environments.</span></span>  
  
 <span data-ttu-id="65334-112">アプリケーション チームは、バックアップ、復元、および障害回復の手順を徹底的にテストする必要があります。</span><span class="sxs-lookup"><span data-stu-id="65334-112">Application teams should thoroughly test backup, restore, and disaster recovery procedures.</span></span> <span data-ttu-id="65334-113">また、手順、運用環境に入る前にアプリケーションの要件を満たすに合わせてカスタマイズを確認する必要があります。</span><span class="sxs-lookup"><span data-stu-id="65334-113">You should also ensure the procedures are tailored to meet application requirements before entering production.</span></span>  
  
## <a name="scope"></a><span data-ttu-id="65334-114">スコープ</span><span class="sxs-lookup"><span data-stu-id="65334-114">Scope</span></span>  
 <span data-ttu-id="65334-115">BizTalk Server との関連する手順のディザスター リカバリー手順に関して、このセクションに焦点を当てます[!INCLUDE[btsSQLServerNoVersion](../includes/btssqlservernoversion-md.md)]します。</span><span class="sxs-lookup"><span data-stu-id="65334-115">This section focuses on disaster recovery procedures for BizTalk Server and related procedures for [!INCLUDE[btsSQLServerNoVersion](../includes/btssqlservernoversion-md.md)].</span></span> <span data-ttu-id="65334-116">このガイドは、バックアップし、BizTalk Server を復元する方法についての関連ドキュメントに基づいています。</span><span class="sxs-lookup"><span data-stu-id="65334-116">This guide builds on related documentation about how to back up and restore BizTalk Server.</span></span>  
  
 <span data-ttu-id="65334-117">バックアップと復元に関する詳細については、このドキュメントを参照して、参照してください[をバックアップおよび復元する BizTalk Server](http://go.microsoft.com/fwlink/?LinkID=154071) (http://go.microsoft.com/fwlink/?LinkID=154071) BizTalk Server のヘルプ。</span><span class="sxs-lookup"><span data-stu-id="65334-117">For more information about backup and restore, see this documentation and see [Backing Up and Restoring BizTalk Server](http://go.microsoft.com/fwlink/?LinkID=154071) (http://go.microsoft.com/fwlink/?LinkID=154071) in BizTalk Server Help.</span></span> <span data-ttu-id="65334-118">各アプリケーション チームがドキュメントのコンピューター名、ドライブ文字など、環境固有の追加の手順では、このトピックの情報を強化する必要がありますおよび関連するクラスターの構成と同様のディザスター リカバリー手順ソリューションの一部である BizTalk 以外のアプリケーション。</span><span class="sxs-lookup"><span data-stu-id="65334-118">Each application team must augment the information in this topic with additional procedures specific to their environment, such as document computer names, drive letters, and cluster configuration, as well as disaster recovery procedures for related non-BizTalk applications that are part of the solution.</span></span>  
  
 <span data-ttu-id="65334-119">このトピックでは、詳細な障害復旧手順、次の領域。</span><span class="sxs-lookup"><span data-stu-id="65334-119">This topic does not provide detailed disaster recovery procedures for the following areas:</span></span>  
  
- <span data-ttu-id="65334-120">非 BizTalk アプリケーション</span><span class="sxs-lookup"><span data-stu-id="65334-120">Non-BizTalk applications</span></span>  
  
- <span data-ttu-id="65334-121">アプリケーションのソース コード</span><span class="sxs-lookup"><span data-stu-id="65334-121">Application source code</span></span>  
  
- <span data-ttu-id="65334-122">証明書</span><span class="sxs-lookup"><span data-stu-id="65334-122">Certificates</span></span>  
  
- <span data-ttu-id="65334-123">アプリケーションの操作</span><span class="sxs-lookup"><span data-stu-id="65334-123">Application operations</span></span>  
  
  <span data-ttu-id="65334-124">ドキュメントを上に挙げた以外、アプリケーションのディザスター リカバリー計画では、各アプリケーション チームでアドレス指定する必要がありますを必要とするその他の領域である可能性があります。</span><span class="sxs-lookup"><span data-stu-id="65334-124">There may be additional areas that require documentation in an application’s disaster recovery plan not listed above that must be addressed by each application team.</span></span>  
  
## <a name="in-this-section"></a><span data-ttu-id="65334-125">このセクションの内容</span><span class="sxs-lookup"><span data-stu-id="65334-125">In This Section</span></span>  
  
-   [<span data-ttu-id="65334-126">ディザスター リカバリーのベスト プラクティス</span><span class="sxs-lookup"><span data-stu-id="65334-126">Best Practices for Disaster Recovery</span></span>](../technical-guides/best-practices-for-disaster-recovery.md)  
  
-   [<span data-ttu-id="65334-127">BizTalk Server のログ配布の概要</span><span class="sxs-lookup"><span data-stu-id="65334-127">What Is BizTalk Server Log Shipping?</span></span>](../technical-guides/what-is-biztalk-server-log-shipping.md)