---
title: SQL Server の最適化 |Microsoft ドキュメント
ms.custom: ''
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: ''
ms.suite: ''
ms.tgt_pltfrm: ''
ms.topic: article
ms.assetid: eb735b54-595e-4dd0-9e4d-9a5e7a007a78
caps.latest.revision: 4
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: 36317d99387fde1d7b5e1c56b45255129daedb25
ms.sourcegitcommit: 32f380810b90b70e5df7be72a6a14988a747868e
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 02/28/2018
ms.locfileid: "29710805"
---
# <a name="sql-server-optimizations"></a>SQL Server の最適化
BizTalk Server は非常に高くデータベース処理を要するアプリケーションの SQL Server での最大 13 個のデータベースの作成が必要な場合があります。 をメッセージが失われないことを確認するには BizTalk Server の主な設計目標の 1 つあるため、BizTalk Server は優れた頻度でデータをディスクが引き続き発生して、さらに、MSDTC トランザクションのコンテキスト内で処理が実行します。 そのため、データベースのパフォーマンスは、BizTalk Server ソリューションの全体的なパフォーマンスが非常に重要です。  
  
このセクションでは、BizTalk Server 環境に固有のデータベースのパフォーマンスを最大化するためのメソッドと同様に SQL Server のパフォーマンスを最大化するための一般的な方法について説明します。 次のリンクも優れたリソース。 

- [インストール、サイズ変更、配置、およびソリューションを維持するための BizTalk サーバー: 推奨事項](https://social.technet.microsoft.com/wiki/contents/articles/666.biztalk-server-recommendations-for-installing-sizing-deploying-and-maintaining-a-solution.aspx)

- [BizTalk Server Performance Optimization Guide](biztalk-server-2013-performance-optimization-guide.md)

  
## <a name="next-steps"></a>次の手順
  
-   [構成前のデータベースの最適化](../technical-guides/pre-configuration-database-optimizations1.md)  
  
-   [構成後のデータベースの最適化](../technical-guides/post-configuration-database-optimizations1.md)  
  
-   [データベースのファイルグループの最適化](../technical-guides/optimizing-filegroups-for-the-databases1.md)