---
title: 関連ドキュメント |Microsoft Docs
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
ms.openlocfilehash: 3cb8259a6c8975673308a0aebb5e9c0336920715
ms.sourcegitcommit: 381e83d43796a345488d54b3f7413e11d56ad7be
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 05/07/2019
ms.locfileid: "65397974"
---
# <a name="related-documents"></a>関連ドキュメント
クエリ結果の詳細の関連するドキュメント領域には、ドキュメントに、アクティビティに関連する参考用ドキュメントの一覧が表示されます。 表示される、CAD 画像を含む、あらゆる種類のドキュメントをします。WAV ファイル、または注文書。 たとえば、発注アクティビティでは、ベースのドキュメントの種類として注文書が必要が通常あります。 注文書へのリンクの一覧が表示されます。  
  
## <a name="adding-document-references"></a>ドキュメント参照の追加  
 2 つの方法のいずれかでは、関連ドキュメントの一覧が生成されます。  
  
- 追跡プロファイルを開発する際に、ドキュメント参照 URL ノードをアクティビティ ツリーに追加し、物理的なドキュメントへの参照ポインターを格納しているソースからマップします。  
  
- 統合開発者プログラムでは、カスタム アプリケーションを呼び出すことによってリストを設定します。  
  
  これらのメソッドのいずれかを使用してドキュメント参照の定義内の行を追加します、 \<activityname\>_References テーブルにドキュメントの場所。  
  
  これらのタスクのどちらが実行された場合、**関連ドキュメント**領域は空白です。  
  
## <a name="see-also"></a>参照  
 [追跡プロファイル エディター](../core/tracking-profile-editor.md)