---
title: SQL Server のパフォーマンスの監視 |Microsoft Docs
description: パフォーマンス ツール、アクティビティの監視、およびデータの収集を使用して BizTalk Server データベースを監視します。
ms.custom: ''
ms.date: 11/29/2017
ms.prod: biztalk-server
ms.reviewer: ''
ms.suite: ''
ms.tgt_pltfrm: ''
ms.topic: article
ms.assetid: 020fa764-968e-467c-b146-d069f5606a0f
caps.latest.revision: 7
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: 917471344859cb7fca6a04df2236221fe780b3a8
ms.sourcegitcommit: 381e83d43796a345488d54b3f7413e11d56ad7be
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 05/07/2019
ms.locfileid: "65395311"
---
# <a name="monitor-sql-server-performance"></a><span data-ttu-id="cf07a-103">SQL Server のパフォーマンスの監視</span><span class="sxs-lookup"><span data-stu-id="cf07a-103">Monitor SQL Server Performance</span></span>
<span data-ttu-id="cf07a-104">SQL Server は、SQL Server のイベントの監視と物理データベース デザインをチューニングするためのいくつかのツールを提供します。</span><span class="sxs-lookup"><span data-stu-id="cf07a-104">SQL Server provides several tools for monitoring events in SQL Server and for tuning the physical database design.</span></span> <span data-ttu-id="cf07a-105">[パフォーマンスの監視およびチューニング ツール](https://docs.microsoft.com/sql/relational-databases/performance/performance-monitoring-and-tuning-tools)これらのツールについて説明します。</span><span class="sxs-lookup"><span data-stu-id="cf07a-105">[Tools for Performance Monitoring and Tuning](https://docs.microsoft.com/sql/relational-databases/performance/performance-monitoring-and-tuning-tools) describes these tools.</span></span> 
  
<span data-ttu-id="cf07a-106">BizTalk Server は、データベース処理を要するプロセスです。</span><span class="sxs-lookup"><span data-stu-id="cf07a-106">BizTalk Server is a database-intensive process.</span></span> <span data-ttu-id="cf07a-107">BizTalk Server パフォーマンスの問題をトラブルシューティングするときも、SQL Server のパフォーマンスを確認すると解消できます。</span><span class="sxs-lookup"><span data-stu-id="cf07a-107">when troubleshooting BizTalk Server performance issues, it can be beneficial to also check the SQL Server performance.</span></span> <span data-ttu-id="cf07a-108">次のツールが役立ちます。</span><span class="sxs-lookup"><span data-stu-id="cf07a-108">The following tools can help.</span></span>  
  
## <a name="sql-server-activity-monitor"></a><span data-ttu-id="cf07a-109">SQL Server の利用状況モニター</span><span class="sxs-lookup"><span data-stu-id="cf07a-109">SQL Server Activity Monitor</span></span>  
<span data-ttu-id="cf07a-110">SQL Server の利用状況モニターは、SQL Server のプロセスおよびこれらのプロセスが現在の SQL Server インスタンスに与える影響についての情報を提供します。</span><span class="sxs-lookup"><span data-stu-id="cf07a-110">SQL Server Activity Monitor provides information about SQL Server processes and how these processes affect the current instance of SQL Server.</span></span> <span data-ttu-id="cf07a-111">詳細については、次を参照してください。[の利用状況モニター](https://docs.microsoft.com/sql/relational-databases/performance-monitor/activity-monitor)、および[方法。利用状況モニターを開く (SQL Server Management Studio](https://docs.microsoft.com/sql/relational-databases/performance-monitor/open-activity-monitor-sql-server-management-studio)します。</span><span class="sxs-lookup"><span data-stu-id="cf07a-111">For more information, see [Activity Monitor](https://docs.microsoft.com/sql/relational-databases/performance-monitor/activity-monitor), and [How to: Open Activity Monitor (SQL Server Management Studio](https://docs.microsoft.com/sql/relational-databases/performance-monitor/open-activity-monitor-sql-server-management-studio).</span></span> 
  
## <a name="sql-serverdata-collection"></a><span data-ttu-id="cf07a-112">SQL ServerData コレクション</span><span class="sxs-lookup"><span data-stu-id="cf07a-112">SQL ServerData Collection</span></span>  
<span data-ttu-id="cf07a-113">SQL Server を取得し、複数のソースから収集されるデータの保存に使用できるデータ コレクターを提供します。</span><span class="sxs-lookup"><span data-stu-id="cf07a-113">SQL Server provides a data collector that you can use to obtain and save data that is gathered from several sources.</span></span> <span data-ttu-id="cf07a-114">データ コレクターでは、範囲と SQL Server を実行しているコンピューター上のデータ収集の頻度を決定するためのデータのコレクション コンテナーを使用することができます。</span><span class="sxs-lookup"><span data-stu-id="cf07a-114">The data collector enables you to use data collection containers, which enable you to determine the scope and frequency of data collection on a computer that is running SQL Server.</span></span> <span data-ttu-id="cf07a-115">参照してください[データ コレクション](https://docs.microsoft.com/sql/relational-databases/data-collection/data-collection)します。</span><span class="sxs-lookup"><span data-stu-id="cf07a-115">See [Data Collection](https://docs.microsoft.com/sql/relational-databases/data-collection/data-collection).</span></span>
  
## <a name="see-also"></a><span data-ttu-id="cf07a-116">参照</span><span class="sxs-lookup"><span data-stu-id="cf07a-116">See Also</span></span>  
 [<span data-ttu-id="cf07a-117">データベース パフォーマンスの最適化</span><span class="sxs-lookup"><span data-stu-id="cf07a-117">Optimizing Database Performance</span></span>](../technical-guides/optimizing-database-performance.md)
