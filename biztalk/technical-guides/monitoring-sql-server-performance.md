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
# <a name="monitor-sql-server-performance"></a>SQL Server のパフォーマンスの監視
SQL Server は、SQL Server のイベントの監視と物理データベース デザインをチューニングするためのいくつかのツールを提供します。 [パフォーマンスの監視およびチューニング ツール](https://docs.microsoft.com/sql/relational-databases/performance/performance-monitoring-and-tuning-tools)これらのツールについて説明します。 
  
BizTalk Server は、データベース処理を要するプロセスです。 BizTalk Server パフォーマンスの問題をトラブルシューティングするときも、SQL Server のパフォーマンスを確認すると解消できます。 次のツールが役立ちます。  
  
## <a name="sql-server-activity-monitor"></a>SQL Server の利用状況モニター  
SQL Server の利用状況モニターは、SQL Server のプロセスおよびこれらのプロセスが現在の SQL Server インスタンスに与える影響についての情報を提供します。 詳細については、次を参照してください。[の利用状況モニター](https://docs.microsoft.com/sql/relational-databases/performance-monitor/activity-monitor)、および[方法。利用状況モニターを開く (SQL Server Management Studio](https://docs.microsoft.com/sql/relational-databases/performance-monitor/open-activity-monitor-sql-server-management-studio)します。 
  
## <a name="sql-serverdata-collection"></a>SQL ServerData コレクション  
SQL Server を取得し、複数のソースから収集されるデータの保存に使用できるデータ コレクターを提供します。 データ コレクターでは、範囲と SQL Server を実行しているコンピューター上のデータ収集の頻度を決定するためのデータのコレクション コンテナーを使用することができます。 参照してください[データ コレクション](https://docs.microsoft.com/sql/relational-databases/data-collection/data-collection)します。
  
## <a name="see-also"></a>参照  
 [データベース パフォーマンスの最適化](../technical-guides/optimizing-database-performance.md)
