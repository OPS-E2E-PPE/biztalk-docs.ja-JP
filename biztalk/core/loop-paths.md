---
title: ループ パスが |Microsoft ドキュメント
ms.custom: ''
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: ''
ms.suite: ''
ms.tgt_pltfrm: ''
ms.topic: article
helpviewer_keywords:
- Looping functoids, paths
- maps, conditional looping
ms.assetid: 4612dc2d-2c39-427d-88ac-65f9e85873c7
caps.latest.revision: 7
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: e69e7d1c092ee5ca34b8c2ef3f309eff6c44b271
ms.sourcegitcommit: cb908c540d8f1a692d01dc8f313e16cb4b4e696d
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 09/20/2017
ms.locfileid: "22262154"
---
# <a name="loop-paths"></a>ループ パス
その Max Occurs プロパティが 1 より大きい場合は、スキーマ内の要素がループです。 ループ パスは、送信元スキーマのループ要素と送信先スキーマのループ要素間のリンクを描画するときに発生します。  
  
## <a name="configuring-a-loop-path"></a>ループ パスの構成  
 ループ パスを作成するときに、BizTalk マッパーは、ループ レコードを自動的に処理します。  
  
 ループ パスは、送信元スキーマのループ レコードのフィールドを、送信先スキーマのループ レコードのフィールドにリンクさせることによって構成できます。 次の図に、食品調査レコードのみをマスター住所リストにコピーするマップを示します。  
  
 ![ループ パスの使用方法を示すマップです。] (../core/media/correct-loop-path-map.gif "correct_loop_path_map")  
ループ パス マップ  
  
## <a name="multiple-loop-paths"></a>ループ パスが複数あります  
 複数のループ レコードに含まれるフィールドと、単一のループ レコードに含まれるフィールドとをリンクさせた場合、マップ内に複数のループ パスが形成されます。 次の図は、単一のマスター住所リストに 2 つの異なるアンケートから収集されたアドレスを組み合わせようとしたを示します。  
  
 ![複数のループ パスを使用したマップ](../core/media/multiple-loop-path-map.gif "multiple_loop_path_map")  
複数のループ パスが含まれたマップ (正しくない)  
  
 このマップでは、予想どおりの結果にはなりません。 コンパイル時にマッパーにより複数のループ パスが検出されると、警告が生成され、既定では最初のループ パスが選択されます。 単一のマスター住所リストに 2 つの異なるアドレスを結合するために使用して、**ループ**functoid マップの下に示すようにします。  
  
 ![ループ functoid の使用方法を示すマップです。] (../core/media/loopingfunctoid.gif "loopingfunctoid")  
ループ Functoid マップ (正しい)  
  
 **ループ**functoid は、次のシナリオで複数のループ パスの代わりに使用する必要があります。  
  
1.  複数のループ パス シナリオで、マッパーによって必要な出力が生成されない場合。  
  
2.  入力インスタンス メッセージ内の複数の繰り返し構造を、出力インスタンス メッセージ内の単一の繰り返し構造に結合する場合。  
  
3.  単一のレコードを複数のレコードにマッピングすることにより、フラット スキーマを階層構造のスキーマに変換する場合。 これは、フラット スキーマを Microsoft Commerce Server カタログに変換する場合の一般的な操作です。  
  
## <a name="see-also"></a>参照  
 [マップにループ Functoid を追加する方法](../core/how-to-add-looping-functoids-to-a-map.md)   
 [ループ Functoid](../core/looping-functoid.md)