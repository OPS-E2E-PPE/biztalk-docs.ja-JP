---
title: 値のマッピングをマップに Functoid を追加する方法 |Microsoft Docs
ms.custom: ''
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: ''
ms.suite: ''
ms.tgt_pltfrm: ''
ms.topic: article
ms.assetid: cc70067a-67a1-4a0e-95e5-b0cb327d2cee
caps.latest.revision: 7
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: 3e4ba1b22b7db156717c2f40e91117562e879caa
ms.sourcegitcommit: 266308ec5c6a9d8d80ff298ee6051b4843c5d626
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 06/27/2018
ms.locfileid: "36996259"
---
# <a name="how-to-add-value-mapping-functoids-to-a-map"></a>マップに値のマッピング Functoid を追加する方法
**値のマッピング**functoid は、最初のパラメーターが true の場合に 2 番目のパラメーターの値を返します。 この Functoid は、主にフィールドの属性をレコードの属性に変更する場合に使用します。  
  
 概念情報については、**値のマッピング**functoid を参照してください[値のマッピング Functoid](../core/value-mapping-functoid.md)します。  
  
### <a name="to-add-the-value-mapping-functoid-to-a-map-and-configure-it"></a>マップに値のマッピング Functoid を追加して構成するには  
  
1. [!INCLUDE[btsVStudioNoVersion](../includes/btsvstudionoversion-md.md)]ツールボックス active をクリックして、**高度な Functoid** functoid のカテゴリを選択するタブ。  
  
    選択したカテゴリに含まれる高度な Functoid の一覧が表示されます。  
  
2. ドラッグ、**値のマッピング**functoid (![](../core/media/bts-tls-valmap.gif "bts_tls_valmap")) ツールボックスからグリッド ページの適切な場所にします。  
  
   > [!NOTE]
   >  Functoid は表示されているグリッド ページに配置されます。 別のグリッド ページに functoid を配置する場合は、最初にその他のグリッド ページを表示する必要があります。  
  
   > [!NOTE]
   >  複数の Functoid を同時に使用するマップを構築する場合は、相対的な位置 (左右) に注意する必要があります。 Functoids は左から順に実行されます。 1 つの Functoid からの出力は、これよりも右にある Functoid にのみ入力することができます。  
  
3. 最初の入力パラメーターを設定する、**値のマッピング**functoid をドラッグして、入力リンクを作成、**値のマッピング**functoid、送信元スキーマのレコードまたはフィールド ノードまたは別の functoid左は、Boolean データ型を持つし、"true"または"false"の入力値が生成されます。  
  
   > [!NOTE]
   >  ドラッグすることも、方向が逆にするブール値のソースをドラッグ、**値のマッピング**functoid。  
  
4. 2 番目の入力パラメーターを設定する、**値のマッピング**functoid をドラッグして、入力リンクを作成、**値のマッピング**レコードまたはフィールド ノードは、送信元スキーマ、またはレコードをドラッグして functoidまたはフィールド ノードに送信元スキーマ、**値のマッピング**functoid。  
  
   > [!NOTE]
   >  2 番目の入力パラメーターを**値のマッピング**の左側に、functoid は別の functoid の出力から指定もできます。 該当する Functoid を別の Functoid へドラッグして、このような入力ソースを表すリンクを作成します。  
  
5. 出力パラメーターを使用する、**値のマッピング**functoid をドラッグして、出力リンクを作成、**値のマッピング**functoid、レコードまたはフィールドに、送信先スキーマ レコード フィールドをドラッグするかを変換先スキーマ、**値のマッピング**functoid。  
  
   > [!NOTE]
   >  他の functoid の出力と同様、**値のマッピング**functoid が別の functoid への入力として使用できます。  
  
## <a name="see-also"></a>参照  
 [マップへの高度な Functoid の追加](../core/adding-advanced-functoids-to-a-map.md)