---
title: マップにインデックス Functoid を追加する方法 |Microsoft Docs
ms.custom: ''
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: ''
ms.suite: ''
ms.tgt_pltfrm: ''
ms.topic: article
ms.assetid: bbfccfcc-c333-422f-b40b-13ca4152e588
caps.latest.revision: 10
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: 68b560b1565638c7d82d6f497319387fc5f58755
ms.sourcegitcommit: 266308ec5c6a9d8d80ff298ee6051b4843c5d626
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 06/27/2018
ms.locfileid: "36976187"
---
# <a name="how-to-add-index-functoids-to-a-map"></a>マップにインデックス Functoid を追加する方法
**インデックス**functoid では、一連のループ レコードの特定のレコードから情報を選択することができます。 各**インデックス**functoid は、1 つのフィールドから情報を選択します。  
  
 概念情報については、**インデックス**functoid を参照してください[インデックス Functoid](../core/index-functoid.md)します。  
  
### <a name="to-add-the-index-functoid-to-a-map-and-configure-it"></a>マップにインデックス Functoid を追加して構成するには  
  
1. [!INCLUDE[btsVStudioNoVersion](../includes/btsvstudionoversion-md.md)]ツールボックス active をクリックして、**高度な Functoid** functoid のカテゴリを選択するタブ。  
  
    選択したカテゴリに含まれる高度な Functoid の一覧が表示されます。  
  
2. ドラッグ、**インデックス**functoid (![](../core/media/bts-tls-index.gif "bts_tls_index")) ツールボックスからグリッド ページの適切な場所にします。  
  
   > [!NOTE]
   >  Functoid は表示されているグリッド ページに配置されます。 別のグリッド ページに Functoid を配置する場合は、先にそのグリッド ページを表示する必要があります。  
  
   > [!NOTE]
   >  まとめて 1 つ以上の functoid を使用してマップを構築する場合は、左から右の相対的な配置を考慮する必要があります。 Functoids は左から順に実行されます。 1 つの Functoid からの出力は、これよりも右にある Functoid にのみ入力することができます。  
  
3. フィールドの入力パラメーターを設定する、**インデックス**functoid、送信元スキーマからループ レコード内のフィールドをドラッグして、入力リンクを作成、**インデックス**functoid、をドラッグするか**インデックス**functoid を送信元スキーマのループ レコード内のフィールド。  
  
4. 少なくとも 1 つのインデックス入力パラメーターを設定する、**インデックス**functoid は、次の手順に従います。  
  
   1.  **インデックス**functoid を選択すると、省略記号をクリックします (**.**) ボタンに関連付けられている、**入力パラメーター**プロパティ、**プロパティ**ウィンドウ。  
  
   2.  **インデックス Functoid の構成**ダイアログ ボックスで、をクリックして、 ![functoid への定数入力パラメーターの追加](../core/media/add-input-parameters.gif "Add_input_parameters")ボタンをクリックします。  
  
   3.  編集ボックスに、インデックス入力パラメーターを数値で入力します。 追加のインデックス値が必要ですが、クリックすると、必要に応じて繰り返します**OK**します。  
  
5. 出力パラメーターを使用する、**インデックス**functoid をドラッグして、出力リンクを作成、**インデックス**または、を送信先スキーマのフィールドをドラッグして、送信先スキーマのフィールドをfunctoid**インデックス**functoid。  
  
   > [!NOTE]
   >  他の functoid の出力と同様、**インデックス**functoid を別の functoid への入力として使用できます。  
  
## <a name="see-also"></a>参照  
 [マップへの高度な Functoid の追加](../core/adding-advanced-functoids-to-a-map.md)