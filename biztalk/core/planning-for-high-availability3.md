---
title: 高 Availability3 の計画 |Microsoft Docs
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
ms.openlocfilehash: 79b4993522725d1a42fd8777fbfd21f91edc0940
ms.sourcegitcommit: 381e83d43796a345488d54b3f7413e11d56ad7be
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 05/07/2019
ms.locfileid: "65395701"
---
# <a name="planning-for-high-availability"></a><span data-ttu-id="ce28e-102">高可用性の計画</span><span class="sxs-lookup"><span data-stu-id="ce28e-102">Planning for High Availability</span></span>
<span data-ttu-id="ce28e-103">多くの企業を使用して、[!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)]ビジネスが依存しているデータを処理します。</span><span class="sxs-lookup"><span data-stu-id="ce28e-103">Many companies use [!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)] to process data that their business depends on.</span></span> <span data-ttu-id="ce28e-104">これらの企業の生産性の低下や収益性、ハードウェア障害が原因の長期にわたるダウンタイムの影響を意味します。</span><span class="sxs-lookup"><span data-stu-id="ce28e-104">For these companies, the consequences of a prolonged downtime because of a hardware outage can mean diminished productivity and profitability.</span></span> <span data-ttu-id="ce28e-105">このセクションでは可用性を高めるため、[!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)]のアップタイムを最大化するための環境、[!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)]ソリューション。</span><span class="sxs-lookup"><span data-stu-id="ce28e-105">This section provides guidance for increasing availability of your [!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)] environment in order to maximize uptime of the [!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)] solution.</span></span>  
  
## <a name="in-this-section"></a><span data-ttu-id="ce28e-106">このセクションの内容</span><span class="sxs-lookup"><span data-stu-id="ce28e-106">In This Section</span></span>  
-   [<span data-ttu-id="ce28e-107">SQL Server Always On 可用性グループを使用した高可用性</span><span class="sxs-lookup"><span data-stu-id="ce28e-107">High Availability using SQL Server Always On Availability Groups</span></span>](../core/high-availability-using-sql-server-always-on-availability-groups.md)
  
-   [<span data-ttu-id="ce28e-108">プラットフォームのフォールト トレランスの計画</span><span class="sxs-lookup"><span data-stu-id="ce28e-108">Planning Your Platform for Fault Tolerance</span></span>](../core/planning-your-platform-for-fault-tolerance.md)  
  
-   [<span data-ttu-id="ce28e-109">高可用性 BizTalk Server 環境を作成します。</span><span class="sxs-lookup"><span data-stu-id="ce28e-109">Creating a Highly Available BizTalk Server Environment</span></span>](../core/creating-a-highly-available-biztalk-server-environment.md)  
  
-   [<span data-ttu-id="ce28e-110">BizTalk Server の高可用性を実現するサンプル シナリオ</span><span class="sxs-lookup"><span data-stu-id="ce28e-110">Sample BizTalk Server High Availability Scenarios</span></span>](../core/sample-biztalk-server-high-availability-scenarios.md)  
  
-   [<span data-ttu-id="ce28e-111">Enterprise Single Sign-On の高可用性</span><span class="sxs-lookup"><span data-stu-id="ce28e-111">High Availability for Enterprise Single Sign-On</span></span>](../core/high-availability-for-enterprise-single-sign-on.md)  
  
-   [<span data-ttu-id="ce28e-112">高可用性と MOF</span><span class="sxs-lookup"><span data-stu-id="ce28e-112">High Availability and the Microsoft Operations Framework</span></span>](../core/high-availability-and-the-microsoft-operations-framework.md)  
  
## <a name="reference"></a><span data-ttu-id="ce28e-113">リファレンス</span><span class="sxs-lookup"><span data-stu-id="ce28e-113">Reference</span></span>  
  
-   <span data-ttu-id="ce28e-114">[SQL Server 2008 フェールオーバー クラスタ リングの概要](http://go.microsoft.com/fwlink/?LinkId=130375)(http://go.microsoft.com/fwlink/?LinkId=130375)</span><span class="sxs-lookup"><span data-stu-id="ce28e-114">[Getting Started with SQL Server 2008 Failover Clustering](http://go.microsoft.com/fwlink/?LinkId=130375) (http://go.microsoft.com/fwlink/?LinkId=130375)</span></span>  
  
-   <span data-ttu-id="ce28e-115">[ホワイト ペーパー:SQL Server 2008 フェールオーバー クラスタ リング](http://go.microsoft.com/fwlink/?LinkId=189522)(http://go.microsoft.com/fwlink/?LinkId=189522)</span><span class="sxs-lookup"><span data-stu-id="ce28e-115">[White Paper: SQL Server 2008 Failover Clustering](http://go.microsoft.com/fwlink/?LinkId=189522) (http://go.microsoft.com/fwlink/?LinkId=189522)</span></span>  
  
-   <span data-ttu-id="ce28e-116">[Windows Server 2008 ステップ バイ ステップ ガイド](http://go.microsoft.com/fwlink/?LinkId=189545)(http://go.microsoft.com/fwlink/?LinkId=189545)</span><span class="sxs-lookup"><span data-stu-id="ce28e-116">[Windows Server 2008 Step-by-Step Guides](http://go.microsoft.com/fwlink/?LinkId=189545) (http://go.microsoft.com/fwlink/?LinkId=189545)</span></span>