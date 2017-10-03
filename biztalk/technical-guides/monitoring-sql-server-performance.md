---
title: "SQL Server のパフォーマンスの監視 |Microsoft ドキュメント"
ms.custom: 
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: 
ms.suite: 
ms.tgt_pltfrm: 
ms.topic: article
ms.assetid: 020fa764-968e-467c-b146-d069f5606a0f
caps.latest.revision: "7"
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: 9a5abdc3054576e03f28967017767112cea652f3
ms.sourcegitcommit: cb908c540d8f1a692d01dc8f313e16cb4b4e696d
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 09/20/2017
---
# <a name="monitoring-sql-server-performance"></a>SQL Server のパフォーマンスの監視
[!INCLUDE[btsSQLServerNoVersion](../includes/btssqlservernoversion-md.md)]内のイベントを監視するためのいくつかのツールを提供[!INCLUDE[btsSQLServerNoVersion](../includes/btssqlservernoversion-md.md)]物理データベース デザインをチューニングします。 これらのツールは、トピックで説明されて[のパフォーマンスの監視およびチューニング ツール](http://go.microsoft.com/fwlink/?LinkId=146357)(http://go.microsoft.com/fwlink/?LinkId=146357) で、[!INCLUDE[btsSQLServerNoVersion](../includes/btssqlservernoversion-md.md)]オンライン ブックの「します。 特定のツールの使用に関する情報[!INCLUDE[btsSQLServerNoVersion](../includes/btssqlservernoversion-md.md)]パフォーマンスの監視とチューニング以下に示します。  
  
## <a name="sql-server-performance-monitoring-tools"></a>SQL Server パフォーマンス監視ツール  
 [!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)]は、このようなデータベースで大量に消費するプロセスでは、何が起こって SQL Server のトラブルシューティングを行うときに時間をかけてにも役に立ちます[!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)]パフォーマンスの問題です。 このトピックの残りの部分がパフォーマンスの監視にリアルタイム データとアーカイブ済みデータを調査するために使用できるツールについて説明します[!INCLUDE[btsSQLServer2008R2](../includes/btssqlserver2008r2-md.md)]と[!INCLUDE[btsSQLServer2008](../includes/btssqlserver2008-md.md)]です。  
  
### <a name="sql-server-2008-r2-activity-monitor"></a>SQL Server 2008 R2 の利用状況モニター  
 [!INCLUDE[btsSQLServer2008R2](../includes/btssqlserver2008r2-md.md)]利用状況モニターに関する情報を提供する[!INCLUDE[btsSQLServerNoVersion](../includes/btssqlservernoversion-md.md)]プロセスおよびこれらのプロセスの現在のインスタンスに与える影響[!INCLUDE[btsSQLServerNoVersion](../includes/btssqlservernoversion-md.md)]です。 詳細については[!INCLUDE[btsSQLServer2008R2](../includes/btssqlserver2008r2-md.md)]の利用状況モニターを参照してください[利用状況モニター](http://go.microsoft.com/fwlink/?LinkId=146355) (http://go.microsoft.com/fwlink/?LinkId=146355) で、[!INCLUDE[btsSQLServerNoVersion](../includes/btssqlservernoversion-md.md)]オンライン ブックの「します。 利用状況モニターを開く方法について[!INCLUDE[btsSQLServerNoVersion](../includes/btssqlservernoversion-md.md)]Management Studio を参照してください[する方法: 利用状況モニターを開く (SQL Server Management Studio](http://go.microsoft.com/fwlink/?LinkId=135094) (http://go.microsoft.com/fwlink/?LinkId=135094) で、[!INCLUDE[btsSQLServerNoVersion](../includes/btssqlservernoversion-md.md)]オンライン ブックの「します。  
  
### <a name="sql-server-2008-r2-data-collection"></a>SQL Server 2008 R2 のデータの収集  
 [!INCLUDE[btsSQLServer2008R2](../includes/btssqlserver2008r2-md.md)] には、複数のソースから集めたデータを取得して保存するために使用できるデータ コレクターがあります。 データ コレクターでは、データ コレクション コンテナーを使用して、[!INCLUDE[btsSQLServer2008R2](../includes/btssqlserver2008r2-md.md)] を実行しているコンピューターでのデータ コレクションの範囲と頻度を決定できます。 実装の詳細については[!INCLUDE[btsSQLServer2008R2](../includes/btssqlserver2008r2-md.md)]データ コレクションを参照してください[データ コレクション](http://go.microsoft.com/fwlink/?LinkId=146356)(http://go.microsoft.com/fwlink/?LinkId=146356) で、[!INCLUDE[btsSQLServerNoVersion](../includes/btssqlservernoversion-md.md)]オンライン ブックの「します。  
  
## <a name="see-also"></a>参照  
 [データベースのパフォーマンスを最適化します。](../technical-guides/optimizing-database-performance.md)