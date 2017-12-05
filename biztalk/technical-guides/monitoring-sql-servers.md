---
title: "SQL サーバーの監視 |Microsoft ドキュメント"
description: "SQL Server 管理パックを使用して、パフォーマンス、使用可能な領域、データベースの構成、ブロックされるプロセス、接続、失敗した SQL エージェント ジョブ、レプリケーション、および BizTalk Server の詳細を確認するには"
ms.custom: 
ms.date: 11/29/2017
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
ms.openlocfilehash: 1d0e3ea9ecb9d9d910549790568d5891b72d06de
ms.sourcegitcommit: 3fc338e52d5dbca2c3ea1685a2faafc7582fe23a
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 12/01/2017
---
# <a name="monitoring-sql-servers"></a><span data-ttu-id="2324c-103">SQL サーバーの監視</span><span class="sxs-lookup"><span data-stu-id="2324c-103">Monitoring SQL Servers</span></span>

## <a name="use-sql-management-pack"></a><span data-ttu-id="2324c-104">SQL 管理パックを使用します。</span><span class="sxs-lookup"><span data-stu-id="2324c-104">Use SQL management pack</span></span>
<span data-ttu-id="2324c-105">Microsoft SQL Server 管理パックを主体的および対応のエンタープライズ環境での SQL Server の監視を提供します。</span><span class="sxs-lookup"><span data-stu-id="2324c-105">The Microsoft SQL Server management pack provides both proactive and reactive monitoring of SQL Server in an enterprise environment.</span></span> <span data-ttu-id="2324c-106">可用性と構成の監視、パフォーマンス データの収集、および既定のしきい値は、エンタープライズ レベルの監視に構築されます。</span><span class="sxs-lookup"><span data-stu-id="2324c-106">Availability and configuration monitoring, performance data collection, and default thresholds are built for enterprise-level monitoring.</span></span> <span data-ttu-id="2324c-107">ローカルおよびリモートの両方の接続性チェックにより、データベースの可用性を確認してください。</span><span class="sxs-lookup"><span data-stu-id="2324c-107">Both local and remote connectivity checks help ensure database availability.</span></span>  
  
 <span data-ttu-id="2324c-108">SQL Server 管理パックに組み込まれた専門知識と事前に SQL サーバーを管理し、重大になる前に、問題を特定することがことができます。</span><span class="sxs-lookup"><span data-stu-id="2324c-108">With the embedded expertise in the SQL Server management pack, you can proactively manage SQL Server, and identify issues before they become critical.</span></span> <span data-ttu-id="2324c-109">この管理パックは、セキュリティ、可用性、および SQL Server インフラストラクチャのパフォーマンスが向上します。</span><span class="sxs-lookup"><span data-stu-id="2324c-109">This management pack increases the security, availability, and performance of your SQL Server infrastructure.</span></span>  
  
 <span data-ttu-id="2324c-110">パックに付属している Microsoft SQL Server 管理パック ガイドでは、管理パックの内容、および展開方法を説明します。</span><span class="sxs-lookup"><span data-stu-id="2324c-110">The Microsoft SQL Server management pack guide that comes with the pack describes the content of the management pack, and describes how to deploy it.</span></span> <span data-ttu-id="2324c-111">管理パックの機能は次のとおりです。</span><span class="sxs-lookup"><span data-stu-id="2324c-111">Features of the management pack include:</span></span>  
  
-   <span data-ttu-id="2324c-112">SQL Server、SQL エージェント、レポート サーバー、Notification Services などの含まれるサービスの状態の監視</span><span class="sxs-lookup"><span data-stu-id="2324c-112">Monitoring the state of the included services such as SQL Server, SQL Agent, Report Server, Notification Services</span></span>  
  
-   <span data-ttu-id="2324c-113">データベースの状態の監視</span><span class="sxs-lookup"><span data-stu-id="2324c-113">Monitoring the state of databases</span></span>  
  
-   <span data-ttu-id="2324c-114">データベースでは、% または MB で設定可能な空き領域の監視</span><span class="sxs-lookup"><span data-stu-id="2324c-114">Monitoring the available space in databases, configurable by % or MB</span></span>  
  
-   <span data-ttu-id="2324c-115">確保データベースが正しく構成されています。</span><span class="sxs-lookup"><span data-stu-id="2324c-115">Ensuring databases are configured correctly</span></span>  
  
-   <span data-ttu-id="2324c-116">クライアントは、SQL Server に接続できることを確認します。</span><span class="sxs-lookup"><span data-stu-id="2324c-116">Ensure clients can connect to the SQL Server</span></span>  
  
-   <span data-ttu-id="2324c-117">ブロックされたプロセスを監視します。</span><span class="sxs-lookup"><span data-stu-id="2324c-117">Monitor blocked processes</span></span>  
  
-   <span data-ttu-id="2324c-118">失敗したエージェントの監視ジョブ、および、過剰にかかる時間実行ジョブ</span><span class="sxs-lookup"><span data-stu-id="2324c-118">Watch for failed agent jobs, and jobs taking an excessive time to execute</span></span>  
  
-   <span data-ttu-id="2324c-119">レプリケーションとアラートのエラー発生時の正常性を監視します。</span><span class="sxs-lookup"><span data-stu-id="2324c-119">Monitor the health of replication and alert on failures</span></span>  
  
-   <span data-ttu-id="2324c-120">データベース ミラーリングの状態を監視します。</span><span class="sxs-lookup"><span data-stu-id="2324c-120">Monitor the state of Database Mirroring</span></span>  
  
## <a name="next-steps"></a><span data-ttu-id="2324c-121">次の手順</span><span class="sxs-lookup"><span data-stu-id="2324c-121">Next steps</span></span>
  
-   [<span data-ttu-id="2324c-122">SQL Server エージェント ジョブとデータベースの監視</span><span class="sxs-lookup"><span data-stu-id="2324c-122">Monitoring SQL Server Agent Jobs and Databases</span></span>](../technical-guides/monitoring-sql-server-agent-jobs-and-databases.md)  
  
-   [<span data-ttu-id="2324c-123">カスタマイズした監視用に BizTalk Server データベースをマークする方法</span><span class="sxs-lookup"><span data-stu-id="2324c-123">How to Mark BizTalk Server Databases for Customized Monitoring</span></span>](../technical-guides/how-to-mark-biztalk-server-databases-for-customized-monitoring.md)  
  
-   [<span data-ttu-id="2324c-124">BizTalk Server データベースの監視</span><span class="sxs-lookup"><span data-stu-id="2324c-124">Monitor the BizTalk Server Databases</span></span>](../technical-guides/monitor-the-biztalk-server-databases.md)