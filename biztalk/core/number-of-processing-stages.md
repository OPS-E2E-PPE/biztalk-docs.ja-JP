---
title: 処理ステージの数 |Microsoft Docs
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
ms.openlocfilehash: 3db73745d137486011c2b56031f64b41f59f8639
ms.sourcegitcommit: 381e83d43796a345488d54b3f7413e11d56ad7be
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 05/07/2019
ms.locfileid: "65323528"
---
# <a name="number-of-processing-stages"></a>処理ステージの数
ソリューションは、(ステージを入れ替えてプロセスの実行時間の長い注文を中断することがなく変更を行うことができるようにに、注文プロセスをステージに分割します。 プロセスをステージに分割する方法の詳細についてを参照してください「ビジネス プロセスの分割」 [、ビジネス プロセス管理ソリューションの一部の設計原則](../core/some-design-principles-in-the-business-process-management-solution.md)します。  
  
 現在のバージョン ソリューションにはには、2 つだけの処理ステージが含まれています。 ただし、さらに多くを含めることができます。 ステージでは、プロセスをバージョンより多くのポイントを提供し、処理ステージの最新バージョンの操作を続行します。 ただし、各ステージには、処理時間が増加メッセージ ボックス データベースを通過する調整メッセージのオーバーヘッドが導入されています。 複数のステージの数が過剰なかどうかを判断するソリューションのパフォーマンスを監視する必要があります。  
  
## <a name="see-also"></a>参照  
 [ビジネス プロセス管理ソリューションの実装の要点](../core/implementation-highlights-of-the-business-process-management-solution.md)   
 [プロセス マネージャーのロジック](../core/process-manager-logic.md)