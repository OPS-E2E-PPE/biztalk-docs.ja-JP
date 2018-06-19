---
title: SQL Server のパフォーマンスの監視 |Microsoft ドキュメント
description: パフォーマンス ツール、アクティビティの監視、およびデータ コレクションを使用して BizTalk Server データベースを監視します。
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
ms.openlocfilehash: 1e4f9db738298ec2a242350faae3ba5bc9da1c92
ms.sourcegitcommit: 3fc338e52d5dbca2c3ea1685a2faafc7582fe23a
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 12/01/2017
ms.locfileid: "26007899"
---
# <a name="monitor-sql-server-performance"></a>SQL Server のパフォーマンスの監視
SQL Server は、SQL Server のイベントを監視するためと、物理データベース デザインをチューニングするために、いくつかのツールを提供します。 [パフォーマンスの監視およびチューニング ツール](https://docs.microsoft.com/en-us/sql/relational-databases/performance/performance-monitoring-and-tuning-tools)これらのツールについて説明します。 
  
BizTalk Server は、データベースで大量に消費するプロセスです。 BizTalk Server のパフォーマンスの問題をトラブルシューティングするときも、SQL Server のパフォーマンスを確認すると役に立つがあります。 次のツールが役立ちます。  
  
## <a name="sql-server-activity-monitor"></a>SQL Server の利用状況モニター  
SQL Server の利用状況モニターは、SQL Server プロセスおよびこれらのプロセスが現在の SQL Server インスタンスに与える影響に関する情報を提供します。 詳細については、次を参照してください。[利用状況モニター](https://docs.microsoft.com/sql/relational-databases/performance-monitor/activity-monitor)、および[する方法: 利用状況モニターを開く (SQL Server Management Studio](https://docs.microsoft.com/sql/relational-databases/performance-monitor/open-activity-monitor-sql-server-management-studio)です。 
  
## <a name="sql-serverdata-collection"></a>SQL ServerData コレクション  
SQL Server では、取得して、複数のソースから収集されるデータの保存に使用できるデータ コレクターを提供します。 データ コレクターでは、データ コレクション コンテナーは、スコープと SQL Server を実行しているコンピューター上のデータ収集の頻度を決定するために使用することができます。 参照してください[データ コレクション](https://docs.microsoft.com/sql/relational-databases/data-collection/data-collection)です。
  
## <a name="see-also"></a>参照  
 [データベース パフォーマンスの最適化](../technical-guides/optimizing-database-performance.md)