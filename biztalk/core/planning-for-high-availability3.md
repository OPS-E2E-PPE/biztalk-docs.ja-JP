---
title: 高 Availability3 の計画 |Microsoft ドキュメント
ms.custom: ''
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: ''
ms.suite: ''
ms.tgt_pltfrm: ''
ms.topic: article
helpviewer_keywords:
- architecture, high availability
- high availability
- planning, high availability
- high availability, architecture
ms.assetid: 16feada0-b0b1-4e58-9477-fbd1aae2f51e
caps.latest.revision: 30
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: 3a6a8a69af5fd1ff59a4e69e02a52124d89db1ab
ms.sourcegitcommit: cb908c540d8f1a692d01dc8f313e16cb4b4e696d
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 09/20/2017
ms.locfileid: "22264346"
---
# <a name="planning-for-high-availability"></a><span data-ttu-id="56119-102">高可用性の計画</span><span class="sxs-lookup"><span data-stu-id="56119-102">Planning for High Availability</span></span>
<span data-ttu-id="56119-103">[!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)] は、重要なビジネス データを処理する目的で多くの企業によって使用されています。</span><span class="sxs-lookup"><span data-stu-id="56119-103">Many companies use [!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)] to process data that their business depends on.</span></span> <span data-ttu-id="56119-104">こうした企業にとって、ハードウェア障害に起因する長時間にわたる中断は、生産性や収益性の低下を意味します。</span><span class="sxs-lookup"><span data-stu-id="56119-104">For these companies, the consequences of a prolonged downtime because of a hardware outage can mean diminished productivity and profitability.</span></span> <span data-ttu-id="56119-105">ここでは、[!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)] ソリューションの稼働時間を最大化するための [!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)] 環境の可用性向上に関するガイダンスを提供します。</span><span class="sxs-lookup"><span data-stu-id="56119-105">This section provides guidance for increasing availability of your [!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)] environment in order to maximize uptime of the [!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)] solution.</span></span>  
  
## <a name="in-this-section"></a><span data-ttu-id="56119-106">このセクションの内容</span><span class="sxs-lookup"><span data-stu-id="56119-106">In This Section</span></span>  
-   [<span data-ttu-id="56119-107">SQL Server Always On 可用性グループを使用して高可用性</span><span class="sxs-lookup"><span data-stu-id="56119-107">High Availability using SQL Server Always On Availability Groups</span></span>](../core/high-availability-using-sql-server-always-on-availability-groups.md)
  
-   [<span data-ttu-id="56119-108">フォールト トレランスのためには、プラットフォームの計画</span><span class="sxs-lookup"><span data-stu-id="56119-108">Planning Your Platform for Fault Tolerance</span></span>](../core/planning-your-platform-for-fault-tolerance.md)  
  
-   [<span data-ttu-id="56119-109">高可用性の BizTalk Server 環境を作成します。</span><span class="sxs-lookup"><span data-stu-id="56119-109">Creating a Highly Available BizTalk Server Environment</span></span>](../core/creating-a-highly-available-biztalk-server-environment.md)  
  
-   [<span data-ttu-id="56119-110">サンプル BizTalk Server の高可用性のシナリオ</span><span class="sxs-lookup"><span data-stu-id="56119-110">Sample BizTalk Server High Availability Scenarios</span></span>](../core/sample-biztalk-server-high-availability-scenarios.md)  
  
-   [<span data-ttu-id="56119-111">エンタープライズ シングル サインオンの高可用性</span><span class="sxs-lookup"><span data-stu-id="56119-111">High Availability for Enterprise Single Sign-On</span></span>](../core/high-availability-for-enterprise-single-sign-on.md)  
  
-   [<span data-ttu-id="56119-112">高可用性と、Microsoft Operations Framework</span><span class="sxs-lookup"><span data-stu-id="56119-112">High Availability and the Microsoft Operations Framework</span></span>](../core/high-availability-and-the-microsoft-operations-framework.md)  
  
## <a name="reference"></a><span data-ttu-id="56119-113">リファレンス</span><span class="sxs-lookup"><span data-stu-id="56119-113">Reference</span></span>  
  
-   <span data-ttu-id="56119-114">[SQL Server 2008 フェールオーバー クラスタ リングの概要](http://go.microsoft.com/fwlink/?LinkId=130375)(http://go.microsoft.com/fwlink/?LinkId=130375)</span><span class="sxs-lookup"><span data-stu-id="56119-114">[Getting Started with SQL Server 2008 Failover Clustering](http://go.microsoft.com/fwlink/?LinkId=130375) (http://go.microsoft.com/fwlink/?LinkId=130375)</span></span>  
  
-   <span data-ttu-id="56119-115">[ホワイト ペーパー: SQL Server 2008 フェールオーバー クラスタ リング](http://go.microsoft.com/fwlink/?LinkId=189522)(http://go.microsoft.com/fwlink/?LinkId=189522)</span><span class="sxs-lookup"><span data-stu-id="56119-115">[White Paper: SQL Server 2008 Failover Clustering](http://go.microsoft.com/fwlink/?LinkId=189522) (http://go.microsoft.com/fwlink/?LinkId=189522)</span></span>  
  
-   <span data-ttu-id="56119-116">[Windows Server 2008 ステップ バイ ステップ ガイド](http://go.microsoft.com/fwlink/?LinkId=189545)(http://go.microsoft.com/fwlink/?LinkId=189545)</span><span class="sxs-lookup"><span data-stu-id="56119-116">[Windows Server 2008 Step-by-Step Guides](http://go.microsoft.com/fwlink/?LinkId=189545) (http://go.microsoft.com/fwlink/?LinkId=189545)</span></span>