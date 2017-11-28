---
title: "インデックス Functoid をマップに追加する方法 |Microsoft ドキュメント"
ms.custom: 
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: 
ms.suite: 
ms.tgt_pltfrm: 
ms.topic: article
ms.assetid: bbfccfcc-c333-422f-b40b-13ca4152e588
caps.latest.revision: "10"
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: 6695f7830dcc35fbb0100c012cff10fa207f1ae2
ms.sourcegitcommit: cb908c540d8f1a692d01dc8f313e16cb4b4e696d
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 09/20/2017
---
# <a name="how-to-add-index-functoids-to-a-map"></a>マップにインデックス Functoid を追加する方法
**インデックス**functoid では、一連のループ レコードの特定のレコードから情報を選択することができます。 各**インデックス**functoid が 1 つのフィールドから情報を選択します。  
  
 概要については、**インデックス**functoid を参照してください[インデックス Functoid](../core/index-functoid.md)です。  
  
### <a name="to-add-the-index-functoid-to-a-map-and-configure-it"></a>マップにインデックス Functoid を追加して構成するには  
  
1.  [!INCLUDE[btsVStudioNoVersion](../includes/btsvstudionoversion-md.md)]ツールボックス active をクリックして、**高度な Functoid** functoid のカテゴリを選択するタブです。  
  
     選択したカテゴリに含まれる高度な Functoid の一覧が表示されます。  
  
2.  ドラッグ、**インデックス**functoid (![](../core/media/bts-tls-index.gif "bts_tls_index")) をグリッド ページの適切な場所にツールボックスからです。  
  
    > [!NOTE]
    >  Functoid は表示されているグリッド ページに配置されます。 別のグリッド ページに Functoid を配置する場合は、先にそのグリッド ページを表示する必要があります。  
  
    > [!NOTE]
    >  一緒に複数の functoid を使用してマップを構築する場合は、相対左から右への配置を検討する必要があります。 Functoids は左から順に実行されます。 1 つの Functoid からの出力は、これよりも右にある Functoid にのみ入力することができます。  
  
3.  フィールドの入力パラメーターを設定する、**インデックス**functoid、送信元スキーマからループ レコード内のフィールドをドラッグして、入力リンクを作成、**インデックス**functoid、をドラッグするか**インデックス**functoid、送信元スキーマのループ レコード内のフィールドを送信します。  
  
4.  少なくとも 1 つのインデックス入力パラメーターを設定する、**インデックス**functoid は、次の手順を実行します。  
  
    1.  **インデックス**functoid を選択すると、省略記号ボタンをクリックして (**.**) に関連付けられたボタン、**入力パラメーター**プロパティに、**プロパティ**ウィンドウです。  
  
    2.  **インデックス Functoid の構成**ダイアログ ボックスで、をクリックして、 ![functoid への定数入力パラメーターの追加](../core/media/add-input-parameters.gif "Add_input_parameters")ボタンをクリックします。  
  
    3.  編集ボックスに、インデックス入力パラメーターを数値で入力します。 追加のインデックス値が必要であり、をクリックした場合に、必要に応じて繰り返します**OK**です。  
  
5.  出力パラメーターを使用する、**インデックス**functoid をドラッグして、出力リンクを作成、**インデックス**を送信先スキーマのフィールドをドラッグするか、送信先スキーマのフィールドをfunctoid**インデックス**functoid です。  
  
    > [!NOTE]
    >  その他の functoid の出力と同様、**インデックス**functoid を別の functoid への入力として使用できます。  
  
## <a name="see-also"></a>参照  
 [マップへの高度な Functoid の追加](../core/adding-advanced-functoids-to-a-map.md)