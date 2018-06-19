---
title: マップの警告とエラーを解決する方法 |Microsoft ドキュメント
ms.custom: ''
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: ''
ms.suite: ''
ms.tgt_pltfrm: ''
ms.topic: article
ms.assetid: e8a3e7f3-c96c-4d3d-9f7c-d2bfd9ace4fd
caps.latest.revision: 11
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: 1a2983a53bb47aa66d1564772d0f8e033132e5a8
ms.sourcegitcommit: cb908c540d8f1a692d01dc8f313e16cb4b4e696d
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 09/20/2017
ms.locfileid: "22254882"
---
# <a name="how-to-resolve-map-warnings-and-errors"></a>マップ作成時の警告およびエラーの解決方法
マップをコンパイルすると、コンパイル処理で警告やエラーが表示される場合があります。  
  
## <a name="resolve-warnings-and-errors-when-building-a-map"></a>マップを構築するときに、警告およびエラーを解決します。  
  
1.  リンクおよび functoid エラーの場合に、**エラー一覧**ウィンドウで、任意の説明をダブルクリックします。  
  
     エラーに関連するリンク、Functoid、またはスキーマ ノードが強調表示されます。 問題を解決してください。  
  
2.  確認、**説明**内の領域、**エラー一覧**ウィンドウをその他のエラーを確認します。  
  
3.  クリックして、**出力**ウィンドウ タブには警告とエラー メッセージの追加情報を表示します。  
  
4.  ソリューション エクスプ ローラーで、マップ ファイル名を右クリックしをクリックし、すべての問題を解決したら**マップのテスト**または**ソリューションのビルド**、としてすることができます。  
  
    > [!NOTE]
    >  警告が表示される場合、複数のグリッド ページに問題が存在する可能性があります。 たとえば、グリッド ページ 1 で、レコードがある (という**項目**) 送信元スキーマ ツリー内のレコードにリンク (という名前**数**) 送信先スキーマ ツリーでします。 2 のグリッド ページのレコードが存在する (名前付き**製品**) 送信元スキーマ ツリーで、同じにリンクして**数**送信先スキーマ ツリーでレコード。 このシナリオでは、複数の入力が同じレコードがあることを示す警告メッセージが生成されます。 ただし 1 のグリッド ページを表示する場合に、1 つのみの入力を表示、**数**レコード。 
  
## <a name="see-also"></a>参照  
 [コンパイルして、マップのテスト](../core/compiling-and-testing-maps.md)   
 [BizTalk マッパーのエラー](../core/biztalk-mapper-errors.md)   
 [マップのトラブルシューティング](../core/troubleshooting-maps.md)