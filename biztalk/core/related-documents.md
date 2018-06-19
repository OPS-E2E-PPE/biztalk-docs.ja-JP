---
title: 関連するドキュメント |Microsoft ドキュメント
ms.custom: ''
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: ''
ms.suite: ''
ms.tgt_pltfrm: ''
ms.topic: article
helpviewer_keywords:
- queries [BAM], document references
- definition files [BAM], related documents
- Query Builder [BAM portal], viewing details
- document references [BAM]
- Query Builder [BAM portal], document references
- queries [BAM], viewing details
ms.assetid: 9c5f2175-fe7c-40ec-910d-1ac5c8142045
caps.latest.revision: 10
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: 5b87f0d31010a8bf80e09c59f05f2f9302a510e2
ms.sourcegitcommit: 5abd0ed3f9e4858ffaaec5481bfa8878595e95f7
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 11/28/2017
ms.locfileid: "25970072"
---
# <a name="related-documents"></a>関連ドキュメント
クエリ結果の詳細に表示される [関連ドキュメント] 領域には、アクティビティに関連する参考用ドキュメントが一覧表示されます。 表示されるドキュメントの種類は、CAD 画像、.WAV ファイル、注文書などさまざまです。 たとえば、発注アクティビティでは、通常、基本のドキュメントの種類として注文書が使用されます。 表示される一覧には、注文書へのリンクが含まれます。  
  
## <a name="adding-document-references"></a>ドキュメント参照の追加  
 関連ドキュメントの一覧は、次のいずれかの方法で生成します。  
  
-   追跡プロファイルの作成時にアクティビティ ツリーの Document Reference URL ノードを含め、物理的なドキュメントへの参照ポインターを含んだソースからその Document Reference URL ノードを割り当てます。  
  
-   統合アプリケーション開発者が、カスタム アプリケーションを呼び出すことにより、プログラムを使用してこの一覧を作成します。  
  
 内の行を追加するいずれかの方法を使用してドキュメント参照を定義する、 \<activityname\>_References がドキュメントの場所を持つテーブルです。  
  
 これらのタスクのどちらが実行された場合、**関連ドキュメント**領域は空白です。  
  
## <a name="see-also"></a>参照  
 [追跡プロファイル エディター](../core/tracking-profile-editor.md)