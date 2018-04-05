---
title: グリッド ページの順序を変更する方法 |Microsoft ドキュメント
ms.custom: ''
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: ''
ms.suite: ''
ms.tgt_pltfrm: ''
ms.topic: article
f1_keywords:
- bts10.mapper.reorderpages
ms.assetid: bbf45501-109f-4333-8d1f-1ad47b010db0
caps.latest.revision: 13
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: 622ee8346855e41c722898a59de6dbe3da90c8a3
ms.sourcegitcommit: cb908c540d8f1a692d01dc8f313e16cb4b4e696d
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 09/20/2017
---
# <a name="how-to-reorder-grid-pages"></a>グリッド ページを並び替える方法
マップが複雑である場合は、複数のグリッド ページを設定できます。グリッド ページの名前や順序を変更することもできます。 このトピックでは、これらの操作の手順について説明します。  
  
 グリッド ページを含めることで、マップの表示を簡素化したり、マップを整理したり読みやすくすることができます。 たとえば、あるページにはヘッダー情報に関連するすべてのリンクと Functoid を配置し、別のページにはマップの本体に関連するすべてのリンクと Functoid を配置することができます。 グリッド ページを作成した後で、ページの名前や順序を変更できます。  
  
## <a name="prerequisites"></a>前提条件  
 これらの手順では、BizTalk マッパーが実行されている必要があります。  
  
### <a name="to-add-and-rename-a-grid-page"></a>グリッド ページを追加したりその名前を変更するには  
  
1.  ページ タブのパネルを右クリックし、をクリックして**Add Page**です。 マップに新しいページが挿入されます。  
  
     ![追加して、グリッド ページの名前を変更する](../core/media/adding-and-renaming-grid-page.gif "Adding_and_renaming_grid_page")  
  
2.  ページ タブのパネルを右クリックし、をクリックして**ページ名の変更**です。  
  
    > [!TIP]
    >  または、既存のページ タブをダブルクリックするか、キーボードの F2 キーを押して変更することもできます。  
  
3.  グリッド ページの新しい名前を入力し、Enter キーを押します。  
  
### <a name="to-reorder-grid-pages-using-reorder-map-pages-dialog-box"></a>[マップ ページの並べ替え] ダイアログ ボックスでグリッド ページを並べ替えるには  
  
1.  ページ タブのパネルを右クリックし、をクリックして**ページの並べ替え**です。  
  
2.  **マップ ページの並べ替え** ダイアログ ボックスは、移動するページ タブを選択し、上矢印または下矢印キー、グリッド ページの相対位置を変更し、クリックをクリックして**OK**です。  
  
     ![グリッド ページを並べ替える上下移動](../core/media/reorder-map-pages.gif "Reorder_map_pages")  
  
### <a name="to-reorder-grid-pages-using-the-page-tabs-panel"></a>ページ タブのパネルでグリッド ページを並べ替えるには  
  
1.  移動/並べ替えを行うページ タブを選択します。  
  
2.  マウスのボタンを押したまま、ページ タブのパネルに沿って動かします。  
  
3.  ページ タブのパネル上で目的の場所までページ タブを移動したら、マウス ボタンを離します。  
  
    > [!TIP]
    >  ページの移動/並べ替えが行われるのは、マウスのカーソルが 2 つのページ タブの間で縦線に変化する場合のみです。 縦線は、ページの位置が並べ替えられることを示します。  
  
### <a name="to-delete-a-grid-page"></a>グリッド ページを削除するには  
  
1.  削除するページのタブを選択します。  
  
2.  [ページ] タブを右クリックし、をクリックして**ページの削除**です。 ページを削除する際、確認メッセージは表示されません。  
  
    > [!IMPORTANT]
    >  グリッド ページを削除したくない場合は、Ctrl キーを押しながら Z キーを押して、削除操作を取り消します。 元に戻すまたはユーザーの操作を再実行する方法の詳細については、次を参照してください。[を元に戻すまたはユーザーの操作を再実行する方法](../core/how-to-undo-or-redo-user-operations.md)です。  
  
## <a name="see-also"></a>参照  
 [グリッド ページの操作](../core/working-with-grid-pages.md)