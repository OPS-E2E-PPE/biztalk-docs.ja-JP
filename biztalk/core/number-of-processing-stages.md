---
title: 処理ステージの数 |Microsoft ドキュメント
ms.custom: ''
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: ''
ms.suite: ''
ms.tgt_pltfrm: ''
ms.topic: article
helpviewer_keywords:
- processing, stages
- process management solution tutorial, processing stages
ms.assetid: 74bd9f8c-99b4-4931-a096-6c54221ab2e5
caps.latest.revision: 9
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: 1f61c5c348e54ea096c921cb6fc63f0db339dbf4
ms.sourcegitcommit: cb908c540d8f1a692d01dc8f313e16cb4b4e696d
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 09/20/2017
ms.locfileid: "22263114"
---
# <a name="number-of-processing-stages"></a>処理ステージの数
このソリューションでは、発注プロセスを複数のステージに分割します。これにより、長時間にわたる注文の処理を中断することなく、ステージを入れ替えてプロセスの変更を行えるようになります。 プロセスをステージに分割する方法の詳細についてを参照してください「ビジネス プロセスの分割」[ビジネス プロセス管理ソリューションで一部の設計原則](../core/some-design-principles-in-the-business-process-management-solution.md)です。  
  
 現バージョンのソリューションには 2 つの処理ステージしか含まれていませんが、 さらに多くのステージを含めることもできます。 ステージを増やすと、プロセスの変更バージョンを作成して処理ステージの最新バージョンで作業を継続していくことのできるポイントが増えます。 ただし、ステージが増えるごとにメッセージ ボックス データベースを通過する調整メッセージ分のオーバーヘッドが追加され、処理時間が増加します。 ソリューションのパフォーマンスを監視して、ステージ数が多すぎないかどうかを判断する必要があります。  
  
## <a name="see-also"></a>参照  
 [ビジネス プロセス管理ソリューションの実装の要点](../core/implementation-highlights-of-the-business-process-management-solution.md)   
 [プロセス マネージャのロジック](../core/process-manager-logic.md)