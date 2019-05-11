---
title: 間およびグリッド ページ内で移動する方法 |Microsoft Docs
ms.custom: ''
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: ''
ms.suite: ''
ms.tgt_pltfrm: ''
ms.topic: article
f1_keywords:
- bts10.mapper.gridpreview
ms.assetid: 9553d9ad-1c57-4e73-bb77-0eaaa172090c
caps.latest.revision: 16
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: cedbf885b9e017a50d0e2dd68fc693bf5b54491a
ms.sourcegitcommit: 381e83d43796a345488d54b3f7413e11d56ad7be
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 05/07/2019
ms.locfileid: "65335919"
---
# <a name="how-to-move-between-and-within-grid-pages"></a>間およびグリッド ページ内を移動する方法
マップが複雑な場合は、すべてのリンクおよび functoid を表示することを 1 つのグリッド ページ内で同時に可能性があります。 これはグリッド ページ内をスクロールすることができる必要があることを意味します。 また、複数のグリッド ページの発行に値する、マップ、グリッド ページ間を移動できる必要があります。 このトピックでは、これらの作業の手順について説明します。  
  
## <a name="prerequisites"></a>前提条件  
 これらの手順では、BizTalk マッパーが実行されている必要があります。  
  
### <a name="to-pan-within-a-grid-page"></a>グリッド ページ内を移動するには  
  
1.  マッパー ユーティリティ リボンで、をクリックして、![このボタンを使用するマッパーのスクロール](../core/media/mapper-pan-hand.gif "Mapper_Pan_Hand")アイコン。  
  
2.  マウスの左ボタンでは、キーを押しながらマップをスクロールする方向にマウスをドラッグします。  
  
    > [!NOTE]
    >  通常モードに切り替えるには、クリックして、![このボタンを使用するマッパーのスクロール](../core/media/mapper-pan-hand.gif "Mapper_Pan_Hand")アイコン。  
  
## <a name="to-scroll-within-a-grid-page-using-keyboard"></a>キーボードを使用してグリッド ページ内をスクロールするには  
 焦点を当てるグリッド画面で任意の場所をクリックしてグリッド ページを表示します。 次に、キーボードの左、右、上、または、下矢印を使用して、したい方向にグリッド ページをスクロールします。 一度に 1 つだけのグリッド セルを移動できます。  
  
 \- または -  
  
 焦点を当てるグリッド画面で任意の場所をクリックしてグリッド ページを表示します。 ページを使用して、/、Pagedown キーをグリッド ページをスクロールするキーボード。  
  
## <a name="to-scroll-within-a-grid-page-using-mouse"></a>マウスを使用してグリッド ページ内をスクロールするには  
 グリッド ページの上にマウス ポインターを移動し、マップを上下に移動する、マウスのスクロール ホイールを回転します。  
  
> [!NOTE]
>  マップでは、マウスの右に移動するか、左を使用できません。  
  
 代わりに、エッジまたはスクロールする方向にグリッド ページの上にマウス ポインターを移動できます。 カーソルが矢印に変わります。 グリッド ページ内を移動、マウスの左ボタンを押したままにします。  
  
### <a name="to-scroll-within-a-grid-page-by-using-the-grid-preview"></a>グリッドのプレビューを使用してグリッド ページ内をスクロールするには  
  
1.  **BizTalk**  メニューのをクリックして**グリッドのプレビュー**します。  
  
    > [!NOTE]
    >  グリッド ページのバック グラウンドで右クリックしてをクリックしたことができます**グリッドのプレビュー**ショートカット メニューから。 または、CTRL + M, CTRL + G キーを押しますを押してもできます。 マッパーのキーボード ショートカットの一覧は、次を参照してください。 [BizTalk マッパーのキーボード ショートカット](../core/biztalk-mapper-keyboard-shortcuts.md)です。  
  
2.  **グリッドのプレビュー**  ダイアログ ボックスで、正方形のロケーターを新しい場所にドラッグします。 正方形のロケーターを移動すると、それに応じて、表示されているグリッド ページをスクロールします。  
  
    > [!NOTE]
    >  グリッドのプレビューは、多くの functoid およびリンクに分散された大規模な領域で、大きなグリッド ページの移動に便利です。  
  
     ![グリッドのプレビュー](../core/media/gridpreview.gif "GridPreview")  
  
## <a name="to-zoom-the-grid-page"></a>グリッド ページを拡大するには  
 縮小または拡大で作業しているグリッド ページに、ズーム スライダーをドラッグします。 十分に小さいサイズに収まるの完全なグリッド ページを参照してに縮小することができます。 逆に、グリッド ページの一部を拡大表示にズームインすることができます。  
  
 ![ドラッグすると、拡大または縮小](../core/media/zoom-gridpage.gif "Zoom_gridpage")  
  
### <a name="to-move-between-grid-pages"></a>グリッド ページ間を移動するには  
  
1.  使用して、**左端へ移動**、**左へ移動**、**右へ移動**、および**右端へ移動** タブを表示するグリッドの下部にある矢印を移動するグリッド ページの名前が表示されます。  
  
     ![マップのグリッド ページ間の移動](../core/media/move-between-grid-pages.gif "Move_between_grid_pages")  
  
2.  移動するグリッド ページのタブをクリックします。  
  
    > [!TIP]
    >  またはを右クリックして任意の場所、リージョンの場所、**左端へ移動**、**左へ移動**、**右へ移動**、および**右端へ移動**矢印が表示されます。 コンテキスト メニューに移動するページをクリックします。  
  
## <a name="see-also"></a>参照  
 [グリッド ページの操作](../core/working-with-grid-pages.md)