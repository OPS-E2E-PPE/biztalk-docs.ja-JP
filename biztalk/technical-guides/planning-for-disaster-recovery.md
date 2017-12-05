---
title: "障害回復の計画 |Microsoft ドキュメント"
ms.custom: 
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: 
ms.suite: 
ms.tgt_pltfrm: 
ms.topic: article
ms.assetid: a33e8875-cfde-4a60-9dab-fc6bb3ac4f1c
caps.latest.revision: "2"
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: 3619a34c843665750abd4f5d852b0f1af5210e1c
ms.sourcegitcommit: 3fc338e52d5dbca2c3ea1685a2faafc7582fe23a
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 12/01/2017
---
# <a name="planning-for-disaster-recovery"></a><span data-ttu-id="6e69f-102">災害時の復旧計画</span><span class="sxs-lookup"><span data-stu-id="6e69f-102">Planning for Disaster Recovery</span></span>
<span data-ttu-id="6e69f-103">このトピックでは、災害復旧の要件をアプリケーション チームと BizTalk Server 用の手順のガイダンスを提供します。</span><span class="sxs-lookup"><span data-stu-id="6e69f-103">This topic provides guidance to application teams for disaster recovery requirements and procedures for BizTalk Server.</span></span> <span data-ttu-id="6e69f-104">Microsoft BizTalk Server の構成と処理の情報を格納する[!INCLUDE[btsSQLServerNoVersion](../includes/btssqlservernoversion-md.md)]です。</span><span class="sxs-lookup"><span data-stu-id="6e69f-104">Microsoft BizTalk Server stores configuration and processing information in [!INCLUDE[btsSQLServerNoVersion](../includes/btssqlservernoversion-md.md)].</span></span> <span data-ttu-id="6e69f-105">BizTalk Server の高可用性と災害復旧処理は、高可用性と災害復旧の機能によって達成[!INCLUDE[btsSQLServerNoVersion](../includes/btssqlservernoversion-md.md)]です。</span><span class="sxs-lookup"><span data-stu-id="6e69f-105">BizTalk Server high availability and disaster recovery is achieved through the high availability and disaster recovery capabilities of [!INCLUDE[btsSQLServerNoVersion](../includes/btssqlservernoversion-md.md)].</span></span>  
  
 <span data-ttu-id="6e69f-106">BizTalk グループでホストされているデータベースのセットで定義[!INCLUDE[btsSQLServerNoVersion](../includes/btssqlservernoversion-md.md)]です。</span><span class="sxs-lookup"><span data-stu-id="6e69f-106">A BizTalk group is defined by a set of databases hosted in [!INCLUDE[btsSQLServerNoVersion](../includes/btssqlservernoversion-md.md)].</span></span> <span data-ttu-id="6e69f-107">ホストされているデータベースのセット[!INCLUDE[btsSQLServerNoVersion](../includes/btssqlservernoversion-md.md)]Windows Server クラスターを使用して高可用性を実現することができます。</span><span class="sxs-lookup"><span data-stu-id="6e69f-107">The set of databases hosted in [!INCLUDE[btsSQLServerNoVersion](../includes/btssqlservernoversion-md.md)] can be made highly available through the use of a Windows Server cluster.</span></span> <span data-ttu-id="6e69f-108">BizTalk 環境を実行しているコンピューターで[!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)]を実行しているコンピューターで、「実行時環境」と、データベースを提供[!INCLUDE[btsSQLServerNoVersion](../includes/btssqlservernoversion-md.md)]環境の永続的ストアを提供します。</span><span class="sxs-lookup"><span data-stu-id="6e69f-108">In a BizTalk environment, the computers running [!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)] provide the “run-time environment” and the databases on the computers running [!INCLUDE[btsSQLServerNoVersion](../includes/btssqlservernoversion-md.md)] provide the persistent store for the environment.</span></span> <span data-ttu-id="6e69f-109">したがって、BizTalk Server のバックアップ、復元、および災害復旧の手順は、頻繁に重点を置きます[!INCLUDE[btsSQLServerNoVersion](../includes/btssqlservernoversion-md.md)]です。</span><span class="sxs-lookup"><span data-stu-id="6e69f-109">Therefore, BizTalk Server backup, restore, and disaster recovery procedures are heavily focused on [!INCLUDE[btsSQLServerNoVersion](../includes/btssqlservernoversion-md.md)].</span></span>  
  
## <a name="purpose"></a><span data-ttu-id="6e69f-110">用途</span><span class="sxs-lookup"><span data-stu-id="6e69f-110">Purpose</span></span>  
 <span data-ttu-id="6e69f-111">このトピックでは統合されて[!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)]主要なドキュメントや、各種の Microsoft Web サイトからの情報の障害復旧情報、[!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)]製品チームの障害復旧手順を定義する[!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)]環境。</span><span class="sxs-lookup"><span data-stu-id="6e69f-111">This topic consolidates [!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)] disaster recovery information from the core documentation, various Microsoft Web sites, and information from the [!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)] product team to define disaster recovery procedures for [!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)] environments.</span></span>  
  
 <span data-ttu-id="6e69f-112">アプリケーション チームは、バックアップ、復元、および災害復旧の手順を徹底的にテストする必要があります。</span><span class="sxs-lookup"><span data-stu-id="6e69f-112">Application teams should thoroughly test backup, restore, and disaster recovery procedures.</span></span> <span data-ttu-id="6e69f-113">手順は、実稼働環境に入る前にアプリケーションの要件を満たすに合わせてカスタマイズも確認する必要があります。</span><span class="sxs-lookup"><span data-stu-id="6e69f-113">You should also ensure the procedures are tailored to meet application requirements before entering production.</span></span>  
  
## <a name="scope"></a><span data-ttu-id="6e69f-114">スコープ</span><span class="sxs-lookup"><span data-stu-id="6e69f-114">Scope</span></span>  
 <span data-ttu-id="6e69f-115">このセクションでは、BizTalk Server との関連する手順の災害復旧の手順で焦点を当てています[!INCLUDE[btsSQLServerNoVersion](../includes/btssqlservernoversion-md.md)]です。</span><span class="sxs-lookup"><span data-stu-id="6e69f-115">This section focuses on disaster recovery procedures for BizTalk Server and related procedures for [!INCLUDE[btsSQLServerNoVersion](../includes/btssqlservernoversion-md.md)].</span></span> <span data-ttu-id="6e69f-116">このガイドは、バックアップし、BizTalk Server を復元する方法についての関連するドキュメントに基づいています。</span><span class="sxs-lookup"><span data-stu-id="6e69f-116">This guide builds on related documentation about how to back up and restore BizTalk Server.</span></span>  
  
 <span data-ttu-id="6e69f-117">バックアップと復元の詳細については、このドキュメントを参照して、参照してください[をバックアップおよび復元する BizTalk Server](http://go.microsoft.com/fwlink/?LinkID=154071) (http://go.microsoft.com/fwlink/?LinkID=154071)、BizTalk Server のヘルプします。</span><span class="sxs-lookup"><span data-stu-id="6e69f-117">For more information about backup and restore, see this documentation and see [Backing Up and Restoring BizTalk Server](http://go.microsoft.com/fwlink/?LinkID=154071) (http://go.microsoft.com/fwlink/?LinkID=154071) in BizTalk Server Help.</span></span> <span data-ttu-id="6e69f-118">各アプリケーション チームは、ドキュメントのコンピューター名、ドライブ文字など、環境固有の追加の手順では、このトピックの情報を拡張する必要があり、関連するクラスターの構成と同様の障害復旧手順ソリューションの一部である非 BizTalk アプリケーション。</span><span class="sxs-lookup"><span data-stu-id="6e69f-118">Each application team must augment the information in this topic with additional procedures specific to their environment, such as document computer names, drive letters, and cluster configuration, as well as disaster recovery procedures for related non-BizTalk applications that are part of the solution.</span></span>  
  
 <span data-ttu-id="6e69f-119">このトピックでは、詳細な障害復旧手順は次の領域。</span><span class="sxs-lookup"><span data-stu-id="6e69f-119">This topic does not provide detailed disaster recovery procedures for the following areas:</span></span>  
  
-   <span data-ttu-id="6e69f-120">非 BizTalk アプリケーション</span><span class="sxs-lookup"><span data-stu-id="6e69f-120">Non-BizTalk applications</span></span>  
  
-   <span data-ttu-id="6e69f-121">アプリケーションのソース コード</span><span class="sxs-lookup"><span data-stu-id="6e69f-121">Application source code</span></span>  
  
-   <span data-ttu-id="6e69f-122">証明書</span><span class="sxs-lookup"><span data-stu-id="6e69f-122">Certificates</span></span>  
  
-   <span data-ttu-id="6e69f-123">アプリケーションの操作</span><span class="sxs-lookup"><span data-stu-id="6e69f-123">Application operations</span></span>  
  
 <span data-ttu-id="6e69f-124">上記以外をアプリケーションの災害復旧計画でのドキュメントは、各アプリケーション チームによってアドレス指定する必要がありますを必要とするその他の領域がある可能性があります。</span><span class="sxs-lookup"><span data-stu-id="6e69f-124">There may be additional areas that require documentation in an application’s disaster recovery plan not listed above that must be addressed by each application team.</span></span>  
  
## <a name="in-this-section"></a><span data-ttu-id="6e69f-125">このセクションの内容</span><span class="sxs-lookup"><span data-stu-id="6e69f-125">In This Section</span></span>  
  
-   [<span data-ttu-id="6e69f-126">ディザスター リカバリーのベスト プラクティス</span><span class="sxs-lookup"><span data-stu-id="6e69f-126">Best Practices for Disaster Recovery</span></span>](../technical-guides/best-practices-for-disaster-recovery.md)  
  
-   [<span data-ttu-id="6e69f-127">BizTalk Server のログ配布の概要</span><span class="sxs-lookup"><span data-stu-id="6e69f-127">What Is BizTalk Server Log Shipping?</span></span>](../technical-guides/what-is-biztalk-server-log-shipping.md)