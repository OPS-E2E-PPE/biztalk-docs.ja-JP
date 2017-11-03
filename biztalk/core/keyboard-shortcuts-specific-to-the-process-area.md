---
title: "処理領域に固有のショートカットをキーボード |Microsoft ドキュメント"
ms.custom: 
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: 
ms.suite: 
ms.tgt_pltfrm: 
ms.topic: article
helpviewer_keywords:
- keyboard shortcuts, Orchestration Designer
- Orchestration Designer, keyboard shortcuts
ms.assetid: d993d341-99f2-4788-b1f3-6a8b911e5278
caps.latest.revision: "8"
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: ba60b23c6c8719789e8de6903dbb538fa5088b08
ms.sourcegitcommit: cb908c540d8f1a692d01dc8f313e16cb4b4e696d
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 09/20/2017
---
# <a name="keyboard-shortcuts-specific-to-the-process-area"></a>処理領域に固有のキーボード ショートカット
処理領域で使用できるキーボード操作を次の表に示します。処理領域はデザイン画面の中央の領域で、オーケストレーションのプロセス フローの定義に使用します。  
  
|[キー]|結果|  
|---------|------------|  
|下方向キー|下方向にある次の区分線または図形に選択対象を移動します。 判断図形のように、図形の下に複数の分岐が接続されている場合、選択対象は最も左の分岐の最初の図形に移動します。<br /><br /> 選択対象がオーケストレーションの終了図形である場合は、終了図形より下には図形が存在しないため、このキーを押しても何も起こりません。|  
|上矢印|上方向にある次の区分線または図形に選択対象を移動します。 図形の上に複数の分岐が接続されている場合、選択対象は最も左の分岐の最後の図形に移動します。<br /><br /> このキーを押すと持たないされるときに有効、**開始**図形が選択されています。|  
|左方向キー|選択対象が送信図形または受信図形であり、その図形がポートに接続されている場合は、次のようになります。<br /><br /> -図形にポート左ポート画面に向かうポート コネクタがある場合、図形のポート コネクタにフォーカスと選択をシフトします。<br />-図形にポート右ポート画面に向かうポート コネクタがある場合、このキーを押しても何も起こりません。<br />-図形にポート コネクタがあるない場合、ナビゲーション、その他の図形として同じです。<br /><br /> その他の図形 (ポートに接続されていない送信図形および受信図形) の場合は、次のようになります。<br /><br /> -場合、分岐が、選択されているため、現在のブランチの左側に図形を含む分岐が存在する、選択範囲は、左側の分岐で最も近い図形に移動します。<br />-キーには、他の場所、オーケストレーションでの効果はありません。|  
|右矢印|← キーと同じですが、方向が逆です。|  
|Home|選択対象をオーケストレーションの開始図形から出ているコネクタに変更します。|  
|END|選択対象をオーケストレーションの終了図形に入るコネクタに変更します。|  
|NumLock+マイナス記号 (-)|選択した複雑な図形を折りたたみます。|  
|NumLock+プラス記号 (+)|選択した複雑な図形を展開します。|  
|NumLock+*|選択した複雑な図形を展開します。その図形に複雑な子の図形がある場合は、その子の図形も展開します。|  
  
## <a name="see-also"></a>参照  
 [オーケストレーション デザイナーのキーボード ショートカット](../core/orchestration-designer-keyboard-shortcuts.md)