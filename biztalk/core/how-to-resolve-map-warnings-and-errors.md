---
title: マップの警告とエラーを解決する方法 |Microsoft Docs
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
ms.openlocfilehash: 68ec8b45d3e336c12d6a72f8827c536605ad7ccb
ms.sourcegitcommit: 381e83d43796a345488d54b3f7413e11d56ad7be
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 05/07/2019
ms.locfileid: "65384136"
---
# <a name="how-to-resolve-map-warnings-and-errors"></a>マップの警告とエラーを解決する方法
マップをコンパイルするときに警告やエラーが、コンパイル処理があります。  
  
## <a name="resolve-warnings-and-errors-when-building-a-map"></a>マップを構築するときに、警告およびエラーを解決します。  
  
1.  リンクおよび functoid エラーの場合で、**エラー一覧**ウィンドウで、任意の説明をダブルクリックします。  
  
     リンク、functoid、またはエラーに関連付けられているスキーマのノードが強調表示されます。 問題を解決します。  
  
2.  レビュー、**説明**領域で、**エラー一覧**ウィンドウをその他のエラーを確認します。  
  
3.  をクリックして、**出力**警告およびエラー メッセージの追加情報を表示するのには、[ウィンドウ] タブ。  
  
4.  ソリューション エクスプ ローラーでマップ ファイル名を右クリックし をクリックし、すべての問題を解決したら**マップのテスト**または**ソリューションのビルド**にします。  
  
    > [!NOTE]
    >  警告が表示されたらの場合は、問題がいくつかのグリッド ページにわたって存在可能性があります。 たとえば、グリッド ページ 1 のレコードを含むがある (という名前**項目**)、送信元スキーマ ツリーでは、レコードにリンク (という名前**数**) 送信先スキーマ ツリーで。 レコードが存在するグリッド ページ 2 (という名前の**製品**)、送信元スキーマ ツリーでは、同じリンク**数**送信先スキーマ ツリー内のレコード。 このシナリオで、同じレコードを複数の入力があることを示す警告メッセージが生成されます。 ただし 1 のグリッド ページを表示する場合への入力を 1 つだけを表示、**数**レコード。 
  
## <a name="see-also"></a>参照  
 [コンパイルして、マップのテスト](../core/compiling-and-testing-maps.md)   
 [BizTalk マッパー エラー](../core/biztalk-mapper-errors.md)   
 [マップのトラブルシューティング](../core/troubleshooting-maps.md)