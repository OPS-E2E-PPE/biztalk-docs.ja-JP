---
title: "リレーションシップ ノード |Microsoft ドキュメント"
ms.custom: 
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: 
ms.suite: 
ms.tgt_pltfrm: 
ms.topic: article
helpviewer_keywords:
- definition files [BAM], relationships
- definition files [BAM], Tracking Profile Editor
- Relationship nodes [Tracking Profile Editor]
- activities [BAM], relationships
- activities [BAM], Tracking Profile Editor
- Tracking Profile Editor, node descriptions
- Tracking Profile Editor, definition files [BAM]
ms.assetid: 74090133-24d1-4aba-a4fc-f12d19c881fb
caps.latest.revision: "5"
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: f670c62b4e883b124d849ab61396f6f5216e7182
ms.sourcegitcommit: cb908c540d8f1a692d01dc8f313e16cb4b4e696d
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 09/20/2017
---
# <a name="relationship-nodes"></a>リレーションシップ ノード
アクティビティ定義ファイルに複数のアクティビティが含まれている場合は常に、リレーションシップ フォルダーが使用されます。 フォルダー名は、関連するアクティビティと同じ名前になります。 リレーションシップ フォルダーの名前と関連するアクティビティのアクティビティ ID を照合し、データ項目の値を照合して、リンクを形成します。 リレーションシップは、それぞれ個別のノードを使用して定義します。  
  
## <a name="working-with-relationship-nodes"></a>リレーションシップ ノードの操作  
 アクティビティ間のデータ項目をリンクする一意のインスタンス識別子を指定するには、次の操作を行います。  
  
-   メインのオーケストレーションの ActivityId ノードには、データ項目をマップします。  
  
-   上記手順と同じ名前のデータ項目を、関連するアクティビティのリレーションシップ ノードにドラッグ アンド ドロップします。 リレーションシップ ノードの名前は、メイン アクティビティのアクティビティ ノードと同じです。  
  
 たとえば、サンプル シナリオに、RefinanceOrchestration というオーケストレーションで表現される、関連はあるが独立したビジネス プロセスが存在するとします。 このオーケストレーションには、LoanRefinance アクティビティ ノード、Refinance ActivityID のほか、評価要求受信などのオーケストレーション図形が含まれています。 ただし、リレーションシップ ノードとリレーションシップ ID は、元の LoanProcess アクティビティへのリンクを示す LoanID になります。  
  
## <a name="see-also"></a>参照  
 [TPE アクティビティ ビューのノード](../core/tpe-activity-view-nodes.md)