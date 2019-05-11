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
ms.openlocfilehash: 70cc813f448ad4c24a58ae6640780942911ef879
ms.sourcegitcommit: 381e83d43796a345488d54b3f7413e11d56ad7be
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 05/07/2019
ms.locfileid: "65386291"
---
# <a name="how-to-configure-correlation-sets"></a>関連付けセットを構成する方法
で関連付けセットを構成するには、既存の関連付けの種類を選択し、新しい関連付けの種類を作成または既存の関連付けの種類を変更することができます。  
  
### <a name="to-assign-a-correlation-type-to-a-correlation-set"></a>関連付けセットに関連付けの種類を割り当てる  
  
- 既存の関連付けの種類を選択します。  
  
   \- または -  
  
   新しい関連付けの種類を右クリックして**関連付けプロパティの構成**します。  
  
   \- または -  
  
   省略記号をクリックします (**.**) ボタンを**相関**プロパティで、**プロパティ**ウィンドウ。  
  
   **関連付けのプロパティ** ダイアログ ボックスが表示されます。 関連付けセットに含めるプロパティを追加します。 関連付けの種類は関連付けセットに既に割り当てられていない、新しい関連付けの種類が作成されます。  
  
  関連付けセットに対して関連付けの種類が既に存在して、追加またはプロパティを削除する場合、**関連付けのプロパティ**ダイアログ ボックスで、既存の相関関係の種類が変更されます。  
  
#### <a name="to-associate-send-and-receive-activities-with-a-correlation-set"></a>送信を関連付け、receive アクティビティで関連付けセット  
  
1.  展開、**関連付けセット**ノード。  
  
2.  送信を選択するか、ドロップダウン リストから受信するアクティビティ。  
  
     \- または -  
  
     いずれかで関連付けセットを選択して、**イニシャライズ関連付けセット**プロパティまたは**フォロー関連付けセット**プロパティ、**プロパティ**各ウィンドウ**送信**または**受信**図形を関連付けセットに関連付けます。  
  
#### <a name="to-disassociate-send-and-receive-activities-from-a-correlation-set"></a>送信の関連付けを解除し、関連付けセットからの receive アクティビティ  
  
-   **オーケストレーション**ウィンドウで、必要な場合は、関連付けセットのノードを展開し、削除、およびクリックするアクティビティを右クリックして**削除**します。  
  
     \- または -  
  
     いずれかで関連付けセットを消去、**イニシャライズ関連付けセット**プロパティまたは**フォロー関連付けセット**プロパティ、**プロパティ**各のウィンドウ**送信**または**受信**図形の関連付けセットから関連付けを解除します。  
  
## <a name="see-also"></a>参照  
 [受信メッセージ図形にフィルターを使用します。](../core/using-filters-with-the-receive-message-shape.md)   
 [オーケストレーションでの関連付けの使用](../core/using-correlations-in-orchestrations.md)