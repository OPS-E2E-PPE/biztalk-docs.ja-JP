---
title: マップにレコード カウント Functoid を追加する方法 |Microsoft Docs
ms.custom: ''
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: ''
ms.suite: ''
ms.tgt_pltfrm: ''
ms.topic: article
ms.assetid: 3fbfd2a0-fac5-49f1-bcbb-873c287cd278
caps.latest.revision: 7
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: 0d5fda3565d2b7c3302b5ae3cb596bfed6781609
ms.sourcegitcommit: 266308ec5c6a9d8d80ff298ee6051b4843c5d626
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 06/27/2018
ms.locfileid: "36980331"
---
# <a name="how-to-add-record-count-functoids-to-a-map"></a>マップにレコード カウント Functoid を追加する方法
**レコード カウント**functoid では、インスタンス メッセージ内のレコードの出現回数の合計数を生成することができます。  
  
 概念情報については、**レコード カウント**functoid を参照してください[レコード カウント Functoid](../core/record-count-functoid.md)します。  
  
### <a name="to-add-the-record-count-functoid-to-a-map-and-configure-it"></a>マップにレコード カウント Functoid を追加して構成するには  
  
1. [!INCLUDE[btsVStudioNoVersion](../includes/btsvstudionoversion-md.md)]ツールボックス active をクリックして、**高度な Functoid** functoid のカテゴリを選択するタブ。  
  
    選択したカテゴリに含まれる高度な Functoid の一覧が表示されます。  
  
2. ドラッグ、**レコード カウント**functoid (![](../core/media/bts-tls-recordcount.gif "bts_tls_recordcount")) ツールボックスからグリッド ページの適切な場所にします。  
  
   > [!NOTE]
   >  Functoid は表示されているグリッド ページに配置されます。 別のグリッド ページに Functoid を配置する場合は、先にそのグリッド ページを表示する必要があります。  
  
   > [!NOTE]
   >  複数の Functoid を同時に使用するマップを構築する場合は、相対的な位置 (左右) に注意する必要があります。 Functoids は左から順に実行されます。 1 つの Functoid からの出力は、これよりも右にある Functoid にのみ入力することができます。  
  
3. 入力パラメーターを設定する、**レコード カウント**functoid、送信元スキーマからループ レコードをドラッグして、入力リンクを作成、**レコード カウント**functoid をドラッグするか、 **レコード カウント**functoid、送信元スキーマのループ レコードを送信します。  
  
4. 出力パラメーターを使用する、**レコード カウント**functoid をドラッグして、出力リンクを作成、**レコード カウント**またはコピー先にフィールドをドラッグして、送信先スキーマのフィールドを functoidスキーマを**レコード カウント**functoid。  
  
   > [!NOTE]
   >  他の functoid の出力と同様、**レコード カウント**functoid を別の functoid への入力として使用できます。  
  
## <a name="see-also"></a>参照  
 [マップへの高度な Functoid の追加](../core/adding-advanced-functoids-to-a-map.md)