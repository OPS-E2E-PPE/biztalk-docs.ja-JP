---
title: グリッド ページの順序を変更する方法 |Microsoft Docs
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
ms.openlocfilehash: 6a8ea3a0f5eb08544862081d1495ce5413aaa6f0
ms.sourcegitcommit: 381e83d43796a345488d54b3f7413e11d56ad7be
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 05/07/2019
ms.locfileid: "65384276"
---
# <a name="how-to-reorder-grid-pages"></a>グリッド ページの順序を変更する方法
マップが複雑な場合は、複数のグリッド ページが含まれますと名前を変更しして順序を変更します。 このトピックでには、これらの操作を実行する手順が含まれています。  
  
 マップの表示を簡略化し、整理したり読みして、グリッド ページの 1 つまたは複数を含めることができます。 たとえば、すべてのリンクと 1 ページにヘッダー情報に関連する functoid を配置し、し、すべてのリンクと別のページにはマップの本体に関連する functoid を配置できます。 名前を変更し、作成したグリッド ページを並べ替えることができます。  
  
## <a name="prerequisites"></a>前提条件  
 これらの手順では、BizTalk マッパーが実行されている必要があります。  
  
### <a name="to-add-and-rename-a-grid-page"></a>追加して、グリッド ページの名前を変更するには  
  
1.  ページ タブのパネルを右クリックし、をクリックし、**ページの追加**します。 マップには、挿入された新しいページが表示されます。  
  
     ![追加して、グリッド ページの名前を変更する](../core/media/adding-and-renaming-grid-page.gif "Adding_and_renaming_grid_page")  
  
2.  ページ タブのパネルを右クリックし、をクリックし、**ページ名の変更**します。  
  
    > [!TIP]
    >  または、既存のページ タブをダブルクリックしますか、または、キーボードの F2 キーを押してできます。  
  
3.  グリッド ページの新しい名前を入力し、ENTER キーを押します。  
  
### <a name="to-reorder-grid-pages-using-reorder-map-pages-dialog-box"></a>並べ替えマップ ページ ダイアログ ボックスを使用してグリッド ページの順序を変更するには  
  
1.  ページ タブのパネルを右クリックし、をクリックし、**ページの並べ替え**します。  
  
2.  **マップ ページの並べ替え** ダイアログ ボックスでは、移動するページのタブを選択し、上矢印または下矢印をクリックして、グリッド ページの相対位置を変更 をクリックして**OK**します。  
  
     ![グリッド ページの上下移動](../core/media/reorder-map-pages.gif "Reorder_map_pages")  
  
### <a name="to-reorder-grid-pages-using-the-page-tabs-panel"></a>ページ タブのパネルを使用してグリッド ページの順序を変更するには  
  
1.  移動/並べ替えするページのタブを選択します。  
  
2.  マウス キーを押したままページ タブのパネルに沿って動かします。  
  
3.  ページ タブのパネルで目的の場所にページのタブを連続したときに、マウスを放します。  
  
    > [!TIP]
    >  ページは移動/並べ替えマウス カーソルが 2 つのページ タブ間で縦線に変更したときのみです。 垂直線では、順序が変更されるページの位置を示します。  
  
### <a name="to-delete-a-grid-page"></a>グリッド ページを削除するには  
  
1.  削除するページのタブを選択します。  
  
2.  ページのタブを右クリックし、をクリックし、**ページの削除**します。 ページは自動的に削除されます。  
  
    > [!IMPORTANT]
    >  グリッド ページを削除したくない場合は、削除操作を元に戻すには、ctrl キーを押しながら Z キーを押します。 元に戻すまたはユーザーの操作を再実行する方法の詳細については、次を参照してください。[を元に戻すまたはユーザーの操作をやり直す方法](../core/how-to-undo-or-redo-user-operations.md)します。  
  
## <a name="see-also"></a>参照  
 [グリッド ページの操作](../core/working-with-grid-pages.md)