---
title: 大きなスキーマの操作 |Microsoft ドキュメント
ms.custom: ''
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: ''
ms.suite: ''
ms.tgt_pltfrm: ''
ms.topic: article
ms.assetid: 8348036d-6edb-46a3-badd-0223cfe0a92f
caps.latest.revision: 6
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: e5c5ef679070009b5dfb5fdd403d238cfe243cb2
ms.sourcegitcommit: cb908c540d8f1a692d01dc8f313e16cb4b4e696d
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 09/20/2017
ms.locfileid: "22289714"
---
# <a name="working-with-large-schemas"></a>大きなスキーマの操作
スキーマが非常に大きくなると、XSD ビューの更新に時間がかかり、ユーザー インターフェイスの応答にも影響することがあります。 この問題を解決するには自動更新機能をオフにして、代わりに、手動**更新**を定期的に更新する XSD ビューと XSD ビューにリンクします。 手順については有効にするため、自動更新機能をオフを参照してくださいで XSD ビューの自動更新のオンとオフ"するには」の手順で[XSD ビューの管理](../core/how-to-manage-the-xsd-view.md)です。  
  
 パフォーマンスが低下することもサイズの大きいスキーマでにアタッチされている複数のルートを持つ、**スキーマ**ノード。 設定、**ルート参照**プロパティは、ユーザー インターフェイスのパフォーマンスを向上させることがあります。 設定**ルート参照**コンパイラがすべてのルート スキーマに対して、c# のクラスを作成するためのパフォーマンスが向上します。 単一のルートは、少数のクラスの作成を意味します。  
  
 **インスタンスの検証**が表示されるインスタンスを検証する前に、スキーマで検証が常に行われるため、ユーザー インターフェイスの速度の遅い。 スキーマの検証は、ユーザー インターフェイスでのみ行われます。 設定、**ルート参照**プロパティ ユーザー インターフェイスのパフォーマンスも向上ここでします。  
  
## <a name="see-also"></a>参照  
 [BizTalk エディターの使用](../core/using-biztalk-editor.md)