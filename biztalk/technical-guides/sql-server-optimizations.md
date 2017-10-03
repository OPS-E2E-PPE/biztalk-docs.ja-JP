---
title: "SQL Server の最適化 |Microsoft ドキュメント"
ms.custom: 
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: 
ms.suite: 
ms.tgt_pltfrm: 
ms.topic: article
ms.assetid: eb735b54-595e-4dd0-9e4d-9a5e7a007a78
caps.latest.revision: "4"
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: 3783c09b1155202ac8fe5a964d16c24d33082c26
ms.sourcegitcommit: cb908c540d8f1a692d01dc8f313e16cb4b4e696d
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 09/20/2017
---
# <a name="sql-server-optimizations"></a>SQL Server の最適化
BizTalk Server は非常に高くデータベース処理を要するアプリケーションの SQL Server での最大 13 個のデータベースの作成が必要な場合があります。 をメッセージが失われないことを確認するには BizTalk Server の主な設計目標の 1 つあるため、BizTalk Server は優れた頻度でデータをディスクが引き続き発生して、さらに、MSDTC トランザクションのコンテキスト内で処理が実行します。 そのため、データベースのパフォーマンスは、BizTalk Server ソリューションの全体的なパフォーマンスが非常に重要です。  
  
 このセクションでは、BizTalk Server 環境に固有のデータベースのパフォーマンスを最大化するためのメソッドと同様に SQL Server のパフォーマンスを最大化するための一般的な方法について説明します。 データベースのパフォーマンスを最適化する BizTalk の詳細については、BizTalk データベースの最適化の TechNet の記事を参照してください[http://go.microsoft.com/fwlink/?LinkId=118001](http://go.microsoft.com/fwlink/?LinkId=118001)です。  
  
## <a name="in-this-section"></a>このセクションの内容  
  
-   [事前構成データベース Optimizations1](../technical-guides/pre-configuration-database-optimizations1.md)  
  
-   [インストール後の構成データベース Optimizations1](../technical-guides/post-configuration-database-optimizations1.md)  
  
-   [ファイル グループを Databases1 の最適化](../technical-guides/optimizing-filegroups-for-the-databases1.md)