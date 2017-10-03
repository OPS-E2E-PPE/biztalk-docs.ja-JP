---
title: "データベースのパフォーマンスの最適化 |Microsoft ドキュメント"
ms.custom: 
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: 
ms.suite: 
ms.tgt_pltfrm: 
ms.topic: article
ms.assetid: a95caf60-f1f5-458f-8a81-0aead88f07be
caps.latest.revision: "9"
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: fe9148c5b14c5c915de9a8d16699856922e051a9
ms.sourcegitcommit: cb908c540d8f1a692d01dc8f313e16cb4b4e696d
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 09/20/2017
---
# <a name="optimizing-database-performance"></a>データベースのパフォーマンスを最適化します。
BizTalk Server は、SQL Server で最大 13 個のデータベースの作成を必要とするデータベースを非常に大量に消費するアプリケーションです。 をメッセージが失われないことを確認するには BizTalk Server の主な設計目標の 1 つあるため、BizTalk Server は優れた頻度でデータをディスクが引き続き発生して、さらに、MSDTC トランザクションのコンテキスト内で処理が実行します。 そのため、データベースのパフォーマンスは、BizTalk Server ソリューションの全体的なパフォーマンスが非常に重要です。  
  
 このセクションでは、BizTalk Server 環境に固有のデータベースのパフォーマンスを最大化するためのメソッドと同様に SQL Server のパフォーマンスを最大化するための一般的な方法について説明します。 BizTalk データベースのパフォーマンスの最適化に関する詳細については、次を参照してください。、 [BizTalk データベースの最適化に関するホワイト ペーパー](http://go.microsoft.com/fwlink/?LinkId=101578) (http://go.microsoft.com/fwlink/?LinkId=101578)。  
  
## <a name="in-this-section"></a>このセクションの内容  
  
-   [事前構成データベース Optimizations2](../technical-guides/pre-configuration-database-optimizations2.md)  
  
-   [インストール後の構成データベース Optimizations2](../technical-guides/post-configuration-database-optimizations2.md)  
  
-   [ファイル グループを Databases2 の最適化](../technical-guides/optimizing-filegroups-for-the-databases2.md)  
  
-   [BizTalk Server メッセージ ボックス データベースのファイル グループの SQL スクリプト](../technical-guides/biztalk-server-messagebox-database-filegroups-sql-script.md)  
  
-   [SQL Server のパフォーマンスの監視](../technical-guides/monitoring-sql-server-performance.md)