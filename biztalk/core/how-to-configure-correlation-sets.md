---
title: "関連付けセットを構成する方法 |Microsoft ドキュメント"
ms.custom: 
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: 
ms.suite: 
ms.tgt_pltfrm: 
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
caps.latest.revision: "8"
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: 52bcb0216fc24e14107c7632df97671b64f2ac1d
ms.sourcegitcommit: cb908c540d8f1a692d01dc8f313e16cb4b4e696d
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 09/20/2017
---
# <a name="how-to-configure-correlation-sets"></a>関連付けセットを構成する方法
関連付けセットを構成するには、既存の関連付けの種類を選択し、新しい関連付けの種類を作成するか、既存の関連付けの種類を変更します。  
  
### <a name="to-assign-a-correlation-type-to-a-correlation-set"></a>関連付けの種類を関連付けセットに割り当てるには  
  
-   既存の関連付けの種類を選択します。  
  
     \-または、  
  
     新しい関連付けの種類を右クリックし **関連付けのプロパティを構成する**です。  
  
     \-または、  
  
     省略記号ボタン (**.**) ボタンを**相関**プロパティで、**プロパティ**ウィンドウです。  
  
     **関連付けのプロパティ** ダイアログ ボックスが表示されたらです。 関連付けセットに含めるプロパティを追加します。 関連付けの種類を関連付けセットにまだ割り当てていない場合、新しい関連付けの種類が作成されます。  
  
 関連付けの種類が、関連付けセットに既に存在し、追加またはプロパティを削除する場合、**関連付けのプロパティ**ダイアログ ボックスで、既存の相関関係の種類が変更されます。  
  
#### <a name="to-associate-send-and-receive-activities-with-a-correlation-set"></a>関連付けセットに送受信の動作を関連付けるには  
  
1.  展開して、**関連付けセット**ノード。  
  
2.  ドロップダウン リストから送信または受信の動作を選択します。  
  
     \-または、  
  
     相関関係のいずれかで設定を選択して、**イニシャライズ関連付けセット**プロパティまたは**フォロー関連付けセット**プロパティに、**プロパティ**ごと ウィンドウ**送信**または**受信**図形を関連付けセットに関連付けます。  
  
#### <a name="to-disassociate-send-and-receive-activities-from-a-correlation-set"></a>関連付けセットと送受信の動作との関連付けを解除するには  
  
-   **オーケストレーション**ウィンドウで、必要な場合は、関連付けセットのノードを展開し、削除、およびをクリックする活動を右クリックして**削除**です。  
  
     \-または、  
  
     相関関係のいずれかで設定をオフに、**イニシャライズ関連付けセット**プロパティまたは**フォロー関連付けセット**プロパティに、**プロパティ**各のウィンドウ**送信**または**受信**図形を関連付けセットからの関連付けを解除します。  
  
## <a name="see-also"></a>参照  
 [受信メッセージ図形にフィルターを使用します。](../core/using-filters-with-the-receive-message-shape.md)   
 [オーケストレーションでの相関関係の使用](../core/using-correlations-in-orchestrations.md)