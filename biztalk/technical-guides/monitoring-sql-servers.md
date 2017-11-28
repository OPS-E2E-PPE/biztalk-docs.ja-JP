---
title: "SQL サーバーの監視 |Microsoft ドキュメント"
ms.custom: 
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: 
ms.suite: 
ms.tgt_pltfrm: 
ms.topic: article
ms.assetid: 31871432-e13d-4ef3-b886-16c833371f6d
caps.latest.revision: "3"
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: 6ac37905574090fb346aeee198ea8e92a0f436f1
ms.sourcegitcommit: cb908c540d8f1a692d01dc8f313e16cb4b4e696d
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 09/20/2017
---
# <a name="monitoring-sql-servers"></a><span data-ttu-id="0ab48-102">SQL サーバーの監視</span><span class="sxs-lookup"><span data-stu-id="0ab48-102">Monitoring SQL Servers</span></span>
<span data-ttu-id="0ab48-103">Microsoft[!INCLUDE[btsSQLServerNoVersion](../includes/btssqlservernoversion-md.md)]を主体的および対応の監視管理パックの提供[!INCLUDE[btsSQLServer2008R2](../includes/btssqlserver2008r2-md.md)]と[!INCLUDE[btsSQLServer2008](../includes/btssqlserver2008-md.md)]エンタープライズ環境でします。</span><span class="sxs-lookup"><span data-stu-id="0ab48-103">The Microsoft [!INCLUDE[btsSQLServerNoVersion](../includes/btssqlservernoversion-md.md)] management pack provides both proactive and reactive monitoring of [!INCLUDE[btsSQLServer2008R2](../includes/btssqlserver2008r2-md.md)] and [!INCLUDE[btsSQLServer2008](../includes/btssqlserver2008-md.md)] in an enterprise environment.</span></span> <span data-ttu-id="0ab48-104">可用性と構成の監視、パフォーマンス データの収集、および既定のしきい値は、エンタープライズ レベルの監視に構築されます。</span><span class="sxs-lookup"><span data-stu-id="0ab48-104">Availability and configuration monitoring, performance data collection, and default thresholds are built for enterprise-level monitoring.</span></span> <span data-ttu-id="0ab48-105">ローカルおよびリモートの両方の接続性チェックにより、データベースの可用性を確認してください。</span><span class="sxs-lookup"><span data-stu-id="0ab48-105">Both local and remote connectivity checks help ensure database availability.</span></span>  
  
 <span data-ttu-id="0ab48-106">組み込まれた専門知識と、[!INCLUDE[btsSQLServerNoVersion](../includes/btssqlservernoversion-md.md)]管理パックは、積極的に管理できる[!INCLUDE[btsSQLServerNoVersion](../includes/btssqlservernoversion-md.md)]、し、重大になる前に、問題を識別します。</span><span class="sxs-lookup"><span data-stu-id="0ab48-106">With the embedded expertise in the [!INCLUDE[btsSQLServerNoVersion](../includes/btssqlservernoversion-md.md)] management pack, you can proactively manage [!INCLUDE[btsSQLServerNoVersion](../includes/btssqlservernoversion-md.md)], and identify issues before they become critical.</span></span> <span data-ttu-id="0ab48-107">この管理パックは、セキュリティ、可用性、およびのパフォーマンスが向上して[!INCLUDE[btsSQLServerNoVersion](../includes/btssqlservernoversion-md.md)]インフラストラクチャです。</span><span class="sxs-lookup"><span data-stu-id="0ab48-107">This management pack increases the security, availability, and performance of your [!INCLUDE[btsSQLServerNoVersion](../includes/btssqlservernoversion-md.md)] infrastructure.</span></span>  
  
 <span data-ttu-id="0ab48-108">Microsoft[!INCLUDE[btsSQLServerNoVersion](../includes/btssqlservernoversion-md.md)]パックに付属している管理パック ガイド、管理パックの内容と展開方法について説明します。</span><span class="sxs-lookup"><span data-stu-id="0ab48-108">The Microsoft [!INCLUDE[btsSQLServerNoVersion](../includes/btssqlservernoversion-md.md)] management pack guide that comes with the pack describes the content of the management pack, and describes how to deploy it.</span></span> <span data-ttu-id="0ab48-109">管理パックの機能は次のとおりです。</span><span class="sxs-lookup"><span data-stu-id="0ab48-109">Features of the management pack include:</span></span>  
  
-   <span data-ttu-id="0ab48-110">などの含まれるサービスの状態を監視[!INCLUDE[btsSQLServerNoVersion](../includes/btssqlservernoversion-md.md)]、Notification Services のレポート サーバー、SQL エージェント</span><span class="sxs-lookup"><span data-stu-id="0ab48-110">Monitoring the state of the included services such as [!INCLUDE[btsSQLServerNoVersion](../includes/btssqlservernoversion-md.md)], SQL Agent, Report Server, Notification Services</span></span>  
  
-   <span data-ttu-id="0ab48-111">データベースの状態の監視</span><span class="sxs-lookup"><span data-stu-id="0ab48-111">Monitoring the state of databases</span></span>  
  
-   <span data-ttu-id="0ab48-112">データベースでは、% または MB で設定可能な空き領域の監視</span><span class="sxs-lookup"><span data-stu-id="0ab48-112">Monitoring the available space in databases, configurable by % or MB</span></span>  
  
-   <span data-ttu-id="0ab48-113">確保データベースが正しく構成されています。</span><span class="sxs-lookup"><span data-stu-id="0ab48-113">Ensuring databases are configured correctly</span></span>  
  
-   <span data-ttu-id="0ab48-114">クライアントに接続できることを確認します[!INCLUDE[btsSQLServerNoVersion](../includes/btssqlservernoversion-md.md)]</span><span class="sxs-lookup"><span data-stu-id="0ab48-114">Ensure clients can connect to the [!INCLUDE[btsSQLServerNoVersion](../includes/btssqlservernoversion-md.md)]</span></span>  
  
-   <span data-ttu-id="0ab48-115">ブロックされたプロセスを監視します。</span><span class="sxs-lookup"><span data-stu-id="0ab48-115">Monitor blocked processes</span></span>  
  
-   <span data-ttu-id="0ab48-116">失敗したエージェントの監視ジョブ、および、過剰にかかる時間実行ジョブ</span><span class="sxs-lookup"><span data-stu-id="0ab48-116">Watch for failed agent jobs, and jobs taking an excessive time to execute</span></span>  
  
-   <span data-ttu-id="0ab48-117">レプリケーションとアラートのエラー発生時の正常性を監視します。</span><span class="sxs-lookup"><span data-stu-id="0ab48-117">Monitor the health of replication and alert on failures</span></span>  
  
-   <span data-ttu-id="0ab48-118">データベース ミラーリングの状態を監視します。</span><span class="sxs-lookup"><span data-stu-id="0ab48-118">Monitor the state of Database Mirroring</span></span>  
  
## <a name="in-this-section"></a><span data-ttu-id="0ab48-119">このセクションの内容</span><span class="sxs-lookup"><span data-stu-id="0ab48-119">In This Section</span></span>  
  
-   [<span data-ttu-id="0ab48-120">SQL Server エージェント ジョブおよびデータベースの監視</span><span class="sxs-lookup"><span data-stu-id="0ab48-120">Monitoring SQL Server Agent Jobs and Databases</span></span>](../technical-guides/monitoring-sql-server-agent-jobs-and-databases.md)  
  
-   [<span data-ttu-id="0ab48-121">カスタマイズした監視の BizTalk Server データベースをマークする方法</span><span class="sxs-lookup"><span data-stu-id="0ab48-121">How to Mark BizTalk Server Databases for Customized Monitoring</span></span>](../technical-guides/how-to-mark-biztalk-server-databases-for-customized-monitoring.md)  
  
-   [<span data-ttu-id="0ab48-122">BizTalk Server データベースを監視します。</span><span class="sxs-lookup"><span data-stu-id="0ab48-122">Monitor the BizTalk Server Databases</span></span>](../technical-guides/monitor-the-biztalk-server-databases.md)