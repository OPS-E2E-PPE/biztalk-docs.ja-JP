---
title: "間およびグリッド ページ内で移動する方法 |Microsoft ドキュメント"
ms.custom: 
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: 
ms.suite: 
ms.tgt_pltfrm: 
ms.topic: article
f1_keywords: bts10.mapper.gridpreview
ms.assetid: 9553d9ad-1c57-4e73-bb77-0eaaa172090c
caps.latest.revision: "16"
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: 928e9540c91e33b8e5027bd33757beeff62b145b
ms.sourcegitcommit: cb908c540d8f1a692d01dc8f313e16cb4b4e696d
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 09/20/2017
---
# <a name="how-to-move-between-and-within-grid-pages"></a>グリッド ページ間およびグリッド ページ内で移動する方法
マップが複雑である場合、通常は単一のグリッド ページ内にすべてのリンクと Functoid を同時に表示できません。 このような場合は、グリッド ページをスクロールする必要があります。 複数のグリッド ページに対応するマップを使用する場合は、グリッド ページ間の移動を可能にする必要があります。 このトピックでは、これらの作業の手順について説明します。  
  
## <a name="prerequisites"></a>前提条件  
 これらの手順では、BizTalk マッパーが実行されている必要があります。  
  
### <a name="to-pan-within-a-grid-page"></a>グリッド ページ内を移動するには  
  
1.  マッパー ユーティリティ リボンで、をクリックして、![このボタンを使用するマッパーのスクロール](../core/media/mapper-pan-hand.gif "Mapper_Pan_Hand")アイコン。  
  
2.  左マウス ボタンを押したまま、マップのスクロール方向にマウスをドラッグします。  
  
    > [!NOTE]
    >  標準モードに切り替えるをクリックして、![このボタンを使用するマッパーのスクロール](../core/media/mapper-pan-hand.gif "Mapper_Pan_Hand")アイコン。  
  
## <a name="to-scroll-within-a-grid-page-using-keyboard"></a>キーボードを使用してグリッド ページ内をスクロールするには  
 グリッド画面の任意の場所をクリックしてグリッド ページにフォーカスを移します。 次に、キーボードの上下左右方向の矢印キーを使用して、希望する方向にグリッド ページをスクロールします。 一度に移動できるグリッド セルは 1 つだけです。  
  
 \-または、  
  
 グリッド画面の任意の場所をクリックしてグリッド ページにフォーカスを移します。 次に、キーボードの PageUp キーと PageDown キーを使用して、グリッド ページをスクロールします。  
  
## <a name="to-scroll-within-a-grid-page-using-mouse"></a>マウスを使用してグリッド ページ内をスクロールするには  
 マウス ポインターをグリッド ページ上に移動し、マウス ホイールを回転させてマップを上下に移動します。  
  
> [!NOTE]
>  マウスを使用してマップを左右の方向に移動することはできません。  
  
 または、グリッド ページ内のスクロールする方向の端または隅にマウス ポインターを移動します。 カーソルが矢印の形に変化します。 マウスの左ボタンをクリックして押したまま、グリッド ページ内を移動します。  
  
### <a name="to-scroll-within-a-grid-page-by-using-the-grid-preview"></a>グリッドのプレビューでグリッド ページ内をスクロールするには  
  
1.  **BizTalk**  メニューのをクリックして**グリッドのプレビュー**です。  
  
    > [!NOTE]
    >  グリッド ページの背景を右クリックし、をクリックすることができます**グリッドのプレビュー**ショートカット メニューからです。 または、キーボードで Ctrl キーを押しながら M キーを押し、Ctrl キーを押しながら G キーを押します。 マッパーのキーボード ショートカットの一覧は、次を参照してください。 [BizTalk マッパーのキーボード ショートカット](../core/biztalk-mapper-keyboard-shortcuts.md)です。  
  
2.  **グリッドのプレビュー**  ダイアログ ボックスで、正方形のロケーターを新しい場所にドラッグします。 正方形のロケーターの移動に合わせて、表示されているグリッド ページがスクロールします。  
  
    > [!NOTE]
    >  広い領域に多くの Functoid およびリンクが配置されている、大きなグリッド ページを操作する場合は、グリッドのプレビューが便利です。  
  
     ![グリッドのプレビュー](../core/media/gridpreview.gif "GridPreview")  
  
## <a name="to-zoom-the-grid-page"></a>グリッド ページを拡大/縮小するには  
 使用しているグリッド ページを縮小または拡大するには、ズーム スライダーを使用します。 完全なグリッド ページ内のサイズに収まるようを参照してくださいに縮小することができます。 逆に、グリッド ページの一部を拡大表示するレベルにズームできます。  
  
 ![ドラッグすると、拡大または縮小](../core/media/zoom-gridpage.gif "Zoom_gridpage")  
  
### <a name="to-move-between-grid-pages"></a>グリッド ページ間を移動するには  
  
1.  使用して、**左端へ移動**、**左へ移動**、**右へ移動**、および**右端へ移動** タブを表示するグリッドの下部にある矢印を移動するグリッド ページの名前を示します。  
  
     ![マップのグリッド ページ間を移動](../core/media/move-between-grid-pages.gif "Move_between_grid_pages")  
  
2.  移動するグリッド ページのタブをクリックします。  
  
    > [!TIP]
    >  またはを右クリックして任意の場所、領域の場所、**左端へ移動**、**左へ移動**、**右へ移動**、および**右端へ移動**矢印が表示されます。 ショートカット メニューから、移動先のページをクリックすることもできます。  
  
## <a name="see-also"></a>参照  
 [グリッド ページの操作](../core/working-with-grid-pages.md)