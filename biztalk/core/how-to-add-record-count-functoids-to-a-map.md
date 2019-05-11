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
ms.openlocfilehash: 5f2c63d0278d4962141791a7c7a98d689e84c268
ms.sourcegitcommit: 381e83d43796a345488d54b3f7413e11d56ad7be
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 05/07/2019
ms.locfileid: "65343203"
---
# <a name="how-to-add-record-count-functoids-to-a-map"></a>マップにレコード カウント Functoid を追加する方法
**レコード カウント**functoid では、インスタンス メッセージ内のレコードの出現回数の合計数を生成することができます。  
  
 概念情報については、**レコード カウント**functoid を参照してください[レコード カウント Functoid](../core/record-count-functoid.md)します。  
  
### <a name="to-add-the-record-count-functoid-to-a-map-and-configure-it"></a>マップにレコード カウント functoid を追加し、構成するには  
  
1. [!INCLUDE[btsVStudioNoVersion](../includes/btsvstudionoversion-md.md)]ツールボックス active をクリックして、**高度な Functoid** functoid のカテゴリを選択するタブ。  
  
    選択したカテゴリでの高度な functoid の一覧が表示されます。  
  
2. ドラッグ、**レコード カウント**functoid (![](../core/media/bts-tls-recordcount.gif "bts_tls_recordcount")) ツールボックスからグリッド ページの適切な場所にします。  
  
   > [!NOTE]
   >  Functoid は表示されているグリッド ページに配置されます。 別のグリッド ページに functoid を配置する場合は、最初に、その他のグリッド ページを表示する必要があります。  
  
   > [!NOTE]
   >  複数の Functoid を同時に使用するマップを構築する場合は、相対的な位置 (左右) に注意する必要があります。 Functoids は左から順に実行されます。 1 つの Functoid からの出力は、これよりも右にある Functoid にのみ入力することができます。  
  
3. 入力パラメーターを設定する、**レコード カウント**functoid、送信元スキーマからループ レコードをドラッグして、入力リンクを作成、**レコード カウント**functoid をドラッグするか、 **レコード カウント**functoid、送信元スキーマのループ レコードを送信します。  
  
4. 出力パラメーターを使用する、**レコード カウント**functoid をドラッグして、出力リンクを作成、**レコード カウント**またはコピー先にフィールドをドラッグして、送信先スキーマのフィールドを functoidスキーマを**レコード カウント**functoid。  
  
   > [!NOTE]
   >  他の functoid の出力と同様、**レコード カウント**functoid を別の functoid への入力として使用できます。  
  
## <a name="see-also"></a>参照  
 [マップへの高度な Functoid の追加](../core/adding-advanced-functoids-to-a-map.md)