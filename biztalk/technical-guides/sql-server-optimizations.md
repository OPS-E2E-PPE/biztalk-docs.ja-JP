---
title: SQL Server の最適化 |Microsoft Docs
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
ms.openlocfilehash: a84b6ec1a2c5febb4f0aafdde3f82f8c4afe1962
ms.sourcegitcommit: 381e83d43796a345488d54b3f7413e11d56ad7be
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 05/07/2019
ms.locfileid: "65313255"
---
# <a name="sql-server-optimizations"></a>SQL Server の最適化
BizTalk Server は、非常にデータベース処理を要するアプリケーションで SQL Server の最大 13 個のデータベースを作成することがあります。 メッセージが失われたしないことを確認します。 BizTalk Server の主な設計目標の 1 つは、BizTalk Server は優れた頻度でデータをディスクが引き続き発生して、さらに、MSDTC トランザクションのコンテキスト内では。 したがって、データベースのパフォーマンスは、BizTalk Server ソリューションの全体的なパフォーマンスが非常に重要です。  
  
このセクションでは、BizTalk Server 環境に固有のデータベースのパフォーマンスを最大化するためのメソッドと同様に SQL Server のパフォーマンスを最大化するための一般的な方法について説明します。 次のリンクも優れたリソース。 

- [BizTalk Server:インストール、サイズ変更、展開、およびソリューションを維持するための推奨事項](https://social.technet.microsoft.com/wiki/contents/articles/666.biztalk-server-recommendations-for-installing-sizing-deploying-and-maintaining-a-solution.aspx)

- [BizTalk Server のパフォーマンス最適化ガイド](biztalk-server-2013-performance-optimization-guide.md)

  
## <a name="next-steps"></a>次のステップ
  
-   [構成前のデータベースの最適化](../technical-guides/pre-configuration-database-optimizations1.md)  
  
-   [構成後のデータベースの最適化](../technical-guides/post-configuration-database-optimizations1.md)  
  
-   [データベースのファイルグループの最適化](../technical-guides/optimizing-filegroups-for-the-databases1.md)