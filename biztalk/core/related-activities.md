---
title: 関連するアクティビティ |Microsoft Docs
ms.custom: ''
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: ''
ms.suite: ''
ms.tgt_pltfrm: ''
ms.topic: article
helpviewer_keywords:
- activities [BAM], related activities
- Query Builder [BAM portal], related activities
- queries [BAM], related activities
- Query Builder [BAM portal], viewing details
- queries [BAM], viewing details
ms.assetid: 141b7943-d244-4810-aa88-12aa4a2b7658
caps.latest.revision: 7
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: 547a8f80dbb84e12a89c96a5b85ec6a5cc6421ec
ms.sourcegitcommit: 266308ec5c6a9d8d80ff298ee6051b4843c5d626
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 06/27/2018
ms.locfileid: "37013867"
---
# <a name="related-activities"></a>関連アクティビティ
[関連アクティビティ] 領域には、クエリの基礎となるアクティビティに関連するアクティビティが一覧表示されます。 たとえば、1 回の発注で指示された品物を複数回に分けて出荷することが可能である場合、単一の発注アクティビティに対する関連アクティビティは、複数の出荷アクティビティになります。  
  
## <a name="creating-related-activities"></a>関連アクティビティの作成  
 2 つの方法のいずれかでは、関連アクティビティの一覧が生成されます。  
  
- 2 つのアクティビティを定義し、その両方を含んだ単一のビューを作成します。 開発者が 2 つのアクティビティの間にキー、フィールド、および値のリレーションシップを実装することで、この 2 つを結ぶ関連付けの接続を作成します。  
  
- 2 つのアクティビティを定義します。 開発者が AddRelationship() を呼び出し、2 つのアクティビティの間にキー、フィールド、および値のリレーションシップを定義することで、カスタム アプリケーションに関連付けの接続を作成します。  
  
  内の行を追加で次の方法のいずれかのアクティビティのリレーションシップを定義する、 \<activityname\>_Relationships テーブル。  
  
> [!NOTE]
>  リレーションを定義する最初の方法のみ、関連アクティビティの相互にライブ リンクが設定されます。 2 番目の方法では、2 つのアクティビティにわたるビューが定義されないので、ポータルでは両者のリレーションシップについて認識できません。  
  
## <a name="see-also"></a>参照  
 [アクティビティの検索の結果を表示する方法](../core/how-to-view-the-results-of-an-activity-search.md)