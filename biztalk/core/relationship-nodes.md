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
ms.openlocfilehash: ce7acbed8914fa7af8c80e739c9d29279df1054d
ms.sourcegitcommit: 381e83d43796a345488d54b3f7413e11d56ad7be
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 05/07/2019
ms.locfileid: "65397983"
---
# <a name="relationship-nodes"></a>リレーションシップ ノード
アクティビティ定義ファイルには、1 つ以上のアクティビティが含まれている場合、リレーションシップ フォルダーが使用されます。 フォルダーの名前では、関連付けられているアクティビティの名前と一致します。 関連のアクティビティのアクティビティ ID、リレーションシップ フォルダーの名前を照合することによって、データ アイテムの値を照合することによって、リンクを形成します。 個別のノードを使用して、各リレーションシップを定義します。  
  
## <a name="working-with-relationship-nodes"></a>リレーションシップ ノードの操作  
 アクティビティ間のデータ項目をリンクする一意のインスタンス識別子を指定します。  
  
- データ項目をメインのオーケストレーションの ActivityId ノードにマップします。  
  
- ドラッグし、関連するアクティビティのと同じ名前の上にリレーションシップ ノードでのデータ項目を削除します。 リレーションシップ ノードには、メイン アクティビティのアクティビティ ノードと同じ名前があります。  
  
  たとえば、サンプル シナリオで、関連が存在する可能性がありますが RefinanceOrchestration というオーケストレーションで独立したビジネス プロセスが表されます。 そのオーケストレーションには、LoanRefinance アクティビティ ノード、Refinance ActivityID の場合、および評価要求受信などのオーケストレーション図形が含まれます。 リレーションシップ ノードとリレーションシップの ID は、元の LoanProcess アクティビティへのリンクを示す LoanID がただし、可能性があります。  
  
## <a name="see-also"></a>参照  
 [TPE アクティビティ ビューのノード](../core/tpe-activity-view-nodes.md)