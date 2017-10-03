---
title: "繰り返し Functoid をマップに追加する方法 |Microsoft ドキュメント"
ms.custom: 
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: 
ms.suite: 
ms.tgt_pltfrm: 
ms.topic: article
ms.assetid: 1eaea929-e352-447d-b119-bd69b6b24e6c
caps.latest.revision: "7"
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: c2df7cda082a9a85e54e1dce427d73ea15d8f920
ms.sourcegitcommit: cb908c540d8f1a692d01dc8f313e16cb4b4e696d
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 09/20/2017
---
# <a name="how-to-add-iteration-functoids-to-a-map"></a>マップに繰り返し Functoid を追加する方法
**イテレーション**ループの現在のレコードのインデックス構造体の最初のレコードでは、2 番目のレコードでは、2 の場合は 1 から開始され、functoid の出力。  
  
 概要については、**イテレーション**functoid を参照してください[繰り返し Functoid](../core/iteration-functoid.md)です。  
  
### <a name="to-add-the-index-functoid-to-a-map-and-configure-it"></a>マップにインデックス Functoid を追加して構成するには  
  
1.  [!INCLUDE[btsVStudioNoVersion](../includes/btsvstudionoversion-md.md)]ツールボックス active をクリックして、**高度な Functoid** functoid のカテゴリを選択するタブです。  
  
     選択したカテゴリに含まれる高度な Functoid の一覧が表示されます。  
  
2.  ドラッグ、**インデックス**functoid (![](../core/media/bts-tls-iteration.gif "bts_tls_iteration")) をグリッド ページの適切な場所にツールボックスからです。  
  
    > [!NOTE]
    >  Functoid は表示されているグリッド ページに配置されます。 別のグリッド ページに functoid を配置する場合は、その他のグリッド ページを最初に表示する必要があります。  
  
    > [!NOTE]
    >  複数の Functoid を同時に使用するマップを構築する場合は、相対的な位置 (左右) に注意する必要があります。 Functoids は左から順に実行されます。 1 つの Functoid からの出力は、これよりも右にある Functoid にのみ入力することができます。  
  
3.  ループ レコード入力パラメーターを確立するために、**イテレーション**functoid、送信元スキーマからループ レコードをドラッグして、入力リンクを作成、**イテレーション**functoid、をドラッグするか**イテレーション**functoid、送信元スキーマのループ レコードを送信します。  
  
4.  出力パラメーターを使用する、**イテレーション**functoid をドラッグして、出力リンクを作成、**イテレーション**functoid を送信先スキーマ内のフィールドをドラッグするか、送信先スキーマのフィールドを**イテレーション**functoid です。  
  
    > [!NOTE]
    >  送信先スキーマの該当フィールドのデータ型は、その出力のデータ型に一致する数値または数値に変換する必要があります、**イテレーション**functoid です。  
  
## <a name="see-also"></a>参照  
 [マップへの高度な Functoid の追加](../core/adding-advanced-functoids-to-a-map.md)