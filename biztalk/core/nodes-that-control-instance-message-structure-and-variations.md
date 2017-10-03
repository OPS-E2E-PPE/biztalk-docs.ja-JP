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
ms.openlocfilehash: 0733be2e3331e02bff38a7b93d31b8cafd5ec582
ms.sourcegitcommit: cb908c540d8f1a692d01dc8f313e16cb4b4e696d
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 09/20/2017
---
# <a name="nodes-that-control-instance-message-structure-and-variations"></a>インスタンス メッセージの構造とバリエーションを制御するノード
BizTalk エディターでスキーマの作成に使用されるノードのいくつかは、インスタンス メッセージの構造やバリエーションを制御します。 使用する**シーケンス グループ**ノード要素のシーケンスが必要があります、インスタンス メッセージ内の対応する位置の特定の順序で発生するように指定します。 使用する**選択肢グループ**要素のコレクションから 1 つの要素を指定するノードがインスタンス メッセージ内の対応する位置で発生することができます。 使用する**すべてのグループ**ことのすべての指定した要素で同時実行できるは 1 回のみ以外のすべての順序、インスタンス メッセージ内の対応する位置を指定するノードです。 **\<等価 >**ノードとその子ノードがインスタンス メッセージの派生に基づく多態性が場所実際、多くの関連する複雑なデータのいずれかの許可に対応する発生する種類を示すために、スキーマ ツリーに表示されますインスタンス メッセージ内の位置。  
  
 このセクションの残りの部分では、このクラスのノードに関する追加情報を提供します。  
  
## <a name="in-this-section"></a>このセクションの内容  
  
-   [シーケンス グループ ノード](../core/sequence-group-nodes.md)  
  
-   [選択肢グループ ノード](../core/choice-group-nodes.md)  
  
-   [グループのすべてのノード](../core/all-group-nodes.md)  
  
-   [\<等価 > ノードとその子ノード](../core/equivalent-nodes-and-their-child-nodes.md)