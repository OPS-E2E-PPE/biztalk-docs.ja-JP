---
title: リレーションシップ ノード |Microsoft Docs
ms.custom: ''
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: ''
ms.suite: ''
ms.tgt_pltfrm: ''
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
caps.latest.revision: 5
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: 866a2e1367279c6a53eeb738f4800a647a0cd468
ms.sourcegitcommit: 266308ec5c6a9d8d80ff298ee6051b4843c5d626
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 06/27/2018
ms.locfileid: "37001755"
---
# <a name="relationship-nodes"></a>リレーションシップ ノード
アクティビティ定義ファイルに複数のアクティビティが含まれている場合は常に、リレーションシップ フォルダーが使用されます。 フォルダー名は、関連するアクティビティと同じ名前になります。 リレーションシップ フォルダーの名前と関連するアクティビティのアクティビティ ID を照合し、データ項目の値を照合して、リンクを形成します。 リレーションシップは、それぞれ個別のノードを使用して定義します。  
  
## <a name="working-with-relationship-nodes"></a>リレーションシップ ノードの操作  
 アクティビティ間のデータ項目をリンクする一意のインスタンス識別子を指定するには、次の操作を行います。  
  
- データ項目をメインのオーケストレーションの ActivityId ノードにマップします。  
  
- 上記手順と同じ名前のデータ項目を、関連するアクティビティのリレーションシップ ノードにドラッグ アンド ドロップします。 リレーションシップ ノードの名前は、メイン アクティビティのアクティビティ ノードと同じです。  
  
  たとえば、サンプル シナリオに、RefinanceOrchestration というオーケストレーションで表現される、関連はあるが独立したビジネス プロセスが存在するとします。 このオーケストレーションには、LoanRefinance アクティビティ ノード、Refinance ActivityID のほか、評価要求受信などのオーケストレーション図形が含まれています。 ただし、リレーションシップ ノードとリレーションシップ ID は、元の LoanProcess アクティビティへのリンクを示す LoanID になります。  
  
## <a name="see-also"></a>参照  
 [TPE アクティビティ ビューのノード](../core/tpe-activity-view-nodes.md)