---
title: "ノード インスタンスを制御するメッセージの構造とバリエーション |Microsoft ドキュメント"
ms.custom: 
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: 
ms.suite: 
ms.tgt_pltfrm: 
ms.topic: article
ms.assetid: 3af8e6ce-282d-4318-a538-046b423ef033
caps.latest.revision: "5"
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: baa82def3f62c6a603ef67e098e53b48a49013a3
ms.sourcegitcommit: 5abd0ed3f9e4858ffaaec5481bfa8878595e95f7
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 11/28/2017
---
# <a name="nodes-that-control-instance-message-structure-and-variations"></a>インスタンス メッセージの構造とバリエーションを制御するノード
BizTalk エディターでスキーマの作成に使用されるノードのいくつかは、インスタンス メッセージの構造やバリエーションを制御します。 使用する**シーケンス グループ**ノード要素のシーケンスが必要があります、インスタンス メッセージ内の対応する位置の特定の順序で発生するように指定します。 使用する**選択肢グループ**要素のコレクションから 1 つの要素を指定するノードがインスタンス メッセージ内の対応する位置で発生することができます。 使用する**すべてのグループ**ことのすべての指定した要素で同時実行できるは 1 回のみ以外のすべての順序、インスタンス メッセージ内の対応する位置を指定するノードです。 **\<等価\>**ノードとその子ノードがインスタンス メッセージの派生に基づく多態性が場所実際、多くの関連する複雑なデータの許可のいずれかで発生する種類を示すために、スキーマ ツリーに表示されますが、インスタンス メッセージに対応する場所です。  
  
 このセクションの残りの部分では、このクラスのノードに関する追加情報を提供します。  
  
## <a name="in-this-section"></a>このセクションの内容  
  
-   [[シーケンス グループ] ノード](../core/sequence-group-nodes.md)  
  
-   [[グループの選択] ノード](../core/choice-group-nodes.md)  
  
-   [[すべてのグループ] ノード](../core/all-group-nodes.md)  
  
-   [\<等価\>ノードとその子ノード](../core/equivalent-nodes-and-their-child-nodes.md)