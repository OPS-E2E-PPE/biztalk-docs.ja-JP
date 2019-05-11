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
ms.openlocfilehash: ef8cf9e4b73b4d2eda00c022270ba4cb2db8cf6a
ms.sourcegitcommit: 381e83d43796a345488d54b3f7413e11d56ad7be
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 05/07/2019
ms.locfileid: "65397993"
---
# <a name="related-activities"></a>関連アクティビティ
関連アクティビティ 領域には、クエリの基になるアクティビティに関連するアクティビティの一覧が含まれています。 発注アクティビティに関連するアクティビティの例には、1 つの購買発注品目を複数の出荷配信できるため、複数の出荷アクティビティになります。  
  
## <a name="creating-related-activities"></a>関連アクティビティの作成  
 2 つの方法のいずれかでは、関連アクティビティの一覧が生成されます。  
  
- 2 つのアクティビティを定義し、それらの両方が含まれる 1 つのビューを作成します。 開発者は、キー、フィールド、および、アクティビティ間の値の関係を実装することで 2 つの間の関連付けの接続が作成されます。  
  
- 2 つのアクティビティを定義します。 開発者は、AddRelationship() を呼び出し、キー、フィールド、およびアクティビティの間の値のリレーションシップを定義すると、カスタム アプリケーションに関連付けの接続が作成します。  
  
  内の行を追加で次の方法のいずれかのアクティビティのリレーションシップを定義する、 \<activityname\>_Relationships テーブル。  
  
> [!NOTE]
>  リレーションシップの定義の最初のメソッドのみ相互にライブ リンクが設定関連のアクティビティになります。 2 番目のメソッドにわたるビューを定義していないと、そのため、ポータルが 2 つのアクティビティ間の関係について知ることはできません。  
  
## <a name="see-also"></a>参照  
 [アクティビティの検索の結果を表示する方法](../core/how-to-view-the-results-of-an-activity-search.md)