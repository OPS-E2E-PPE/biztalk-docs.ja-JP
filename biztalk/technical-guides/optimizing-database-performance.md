---
title: データベース パフォーマンスの最適化 |Microsoft Docs
ms.custom: ''
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: ''
ms.suite: ''
ms.tgt_pltfrm: ''
ms.topic: article
ms.assetid: a95caf60-f1f5-458f-8a81-0aead88f07be
caps.latest.revision: 9
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: 2d8dda22976bfd6770fd09b5b98d02f630f7cb28
ms.sourcegitcommit: 381e83d43796a345488d54b3f7413e11d56ad7be
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 05/07/2019
ms.locfileid: "65291432"
---
# <a name="optimizing-database-performance"></a>データベースのパフォーマンスを最適化します。
BizTalk Server は、SQL Server で最大 13 個のデータベースの作成を必要とするデータベースを非常に大量に消費するアプリケーションです。 メッセージが失われたしないことを確認します。 BizTalk Server の主な設計目標の 1 つは、BizTalk Server は優れた頻度でデータをディスクが引き続き発生して、さらに、MSDTC トランザクションのコンテキスト内では。 したがって、データベースのパフォーマンスは、BizTalk Server ソリューションの全体的なパフォーマンスが非常に重要です。  
  
 このセクションでは、BizTalk Server 環境に固有のデータベースのパフォーマンスを最大化するためのメソッドと同様に SQL Server のパフォーマンスを最大化するための一般的な方法について説明します。 BizTalk データベースのパフォーマンスの最適化に関する詳細については、次を参照してください。、 [BizTalk データベースの最適化に関するホワイト ペーパー](http://go.microsoft.com/fwlink/?LinkId=101578) (http://go.microsoft.com/fwlink/?LinkId=101578)します。  
  
## <a name="in-this-section"></a>このセクションの内容  
  
-   [データベースの事前構成 Optimizations2](../technical-guides/pre-configuration-database-optimizations2.md)  
  
-   [構成後のデータベース Optimizations2](../technical-guides/post-configuration-database-optimizations2.md)  
  
-   [Databases2 のファイルグループの最適化](../technical-guides/optimizing-filegroups-for-the-databases2.md)  
  
-   [BizTalk Server メッセージボックス データベース ファイルグループの SQL スクリプト](../technical-guides/biztalk-server-messagebox-database-filegroups-sql-script.md)  
  
-   [SQL Server パフォーマンスの監視](../technical-guides/monitoring-sql-server-performance.md)