---
title: 関連付けセットを構成する方法 |Microsoft Docs
ms.custom: ''
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: ''
ms.suite: ''
ms.tgt_pltfrm: ''
ms.topic: article
helpviewer_keywords:
- correlation sets, send activities
- correlation sets, assigning correlation types
- correlation types, correlation sets
- correlation sets, receive activities
- configuring, correlation sets
- correlation sets, configuring
- correlation types, assigning
ms.assetid: 060bf2ba-c173-4dca-a8c4-4c5341e5ceaa
caps.latest.revision: 8
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: 51c56d7f319023bb0379050452253c65634929c0
ms.sourcegitcommit: 266308ec5c6a9d8d80ff298ee6051b4843c5d626
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 06/27/2018
ms.locfileid: "36968859"
---
# <a name="how-to-configure-correlation-sets"></a>関連付けセットを構成する方法
関連付けセットを構成するには、既存の関連付けの種類を選択し、新しい関連付けの種類を作成するか、既存の関連付けの種類を変更します。  
  
### <a name="to-assign-a-correlation-type-to-a-correlation-set"></a>関連付けの種類を関連付けセットに割り当てるには  
  
- 既存の関連付けの種類を選択します。  
  
   \- または -  
  
   新しい関連付けの種類を右クリックして**関連付けプロパティの構成**します。  
  
   \- または -  
  
   省略記号をクリックします (**.**) ボタンを**相関**プロパティで、**プロパティ**ウィンドウ。  
  
   **関連付けのプロパティ** ダイアログ ボックスが表示されます。 関連付けセットに含めるプロパティを追加します。 関連付けの種類を関連付けセットにまだ割り当てていない場合、新しい関連付けの種類が作成されます。  
  
  関連付けセットに対して関連付けの種類が既に存在して、追加またはプロパティを削除する場合、**関連付けのプロパティ**ダイアログ ボックスで、既存の相関関係の種類が変更されます。  
  
#### <a name="to-associate-send-and-receive-activities-with-a-correlation-set"></a>関連付けセットに送受信の動作を関連付けるには  
  
1.  展開、**関連付けセット**ノード。  
  
2.  ドロップダウン リストから送信または受信の動作を選択します。  
  
     \- または -  
  
     いずれかで関連付けセットを選択して、**イニシャライズ関連付けセット**プロパティまたは**フォロー関連付けセット**プロパティ、**プロパティ**各ウィンドウ**送信**または**受信**図形を関連付けセットに関連付けます。  
  
#### <a name="to-disassociate-send-and-receive-activities-from-a-correlation-set"></a>関連付けセットと送受信の動作との関連付けを解除するには  
  
-   **オーケストレーション**ウィンドウで、必要な場合は、関連付けセットのノードを展開し、削除、およびクリックするアクティビティを右クリックして**削除**します。  
  
     \- または -  
  
     いずれかで関連付けセットを消去、**イニシャライズ関連付けセット**プロパティまたは**フォロー関連付けセット**プロパティ、**プロパティ**各のウィンドウ**送信**または**受信**図形の関連付けセットから関連付けを解除します。  
  
## <a name="see-also"></a>参照  
 [受信メッセージ図形にフィルターを使用します。](../core/using-filters-with-the-receive-message-shape.md)   
 [オーケストレーションでの関連付けの使用](../core/using-correlations-in-orchestrations.md)