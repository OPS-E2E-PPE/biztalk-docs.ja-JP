---
title: 値のマッピング Functoid をマップに追加する方法 |Microsoft ドキュメント
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
ms.openlocfilehash: 47e463489332c3a1d2887dab5f7bd734fdd20af5
ms.sourcegitcommit: cb908c540d8f1a692d01dc8f313e16cb4b4e696d
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 09/20/2017
ms.locfileid: "22247842"
---
# <a name="how-to-add-value-mapping-functoids-to-a-map"></a>マップに値のマッピング Functoid を追加する方法
**値のマッピング**functoid は、最初のパラメーターが true の場合に、2 番目のパラメーターの値を返します。 この Functoid は、主にフィールドの属性をレコードの属性に変更する場合に使用します。  
  
 概要については、**値のマッピング**functoid を参照してください[値のマッピング Functoid](../core/value-mapping-functoid.md)です。  
  
### <a name="to-add-the-value-mapping-functoid-to-a-map-and-configure-it"></a>マップに値のマッピング Functoid を追加して構成するには  
  
1.  [!INCLUDE[btsVStudioNoVersion](../includes/btsvstudionoversion-md.md)]ツールボックス active をクリックして、**高度な Functoid** functoid のカテゴリを選択するタブです。  
  
     選択したカテゴリに含まれる高度な Functoid の一覧が表示されます。  
  
2.  ドラッグ、**値のマッピング**functoid (![](../core/media/bts-tls-valmap.gif "bts_tls_valmap")) をグリッド ページの適切な場所にツールボックスからです。  
  
    > [!NOTE]
    >  Functoid は表示されているグリッド ページに配置されます。 別のグリッド ページに functoid を配置する場合は、その他のグリッド ページを最初に表示する必要があります。  
  
    > [!NOTE]
    >  複数の Functoid を同時に使用するマップを構築する場合は、相対的な位置 (左右) に注意する必要があります。 Functoids は左から順に実行されます。 1 つの Functoid からの出力は、これよりも右にある Functoid にのみ入力することができます。  
  
3.  最初の入力パラメーターを確立するために、**値のマッピング**functoid をドラッグして、入力リンクを作成、**値のマッピング**functoid、送信元スキーマ内のレコードまたはフィールド ノードに、または別の functoid を左は、Boolean データ型を持つおよびを"true"または"false"の入力値が生成されます。  
  
    > [!NOTE]
    >  ドラッグすることも、反対方向にドラッグするブール値のソース、**値のマッピング**functoid です。  
  
4.  2 番目の入力パラメーターを設定する、**値のマッピング**functoid をドラッグして、入力リンクを作成、**値のマッピング**レコードをドラッグするか、送信元スキーマのレコードまたはフィールド ノードを functoidまたはフィールド ノードに、送信元スキーマ、**値のマッピング**functoid です。  
  
    > [!NOTE]
    >  2 番目の入力パラメーターを**値のマッピング**functoid もできる別の functoid の出力からの左側にします。 該当する Functoid を別の Functoid へドラッグして、このような入力ソースを表すリンクを作成します。  
  
5.  出力パラメーターを使用する、**値のマッピング**functoid をドラッグして、出力リンクを作成、**値のマッピング**レコードまたはフィールド レコード フィールドをドラッグするか、送信先スキーマの functoid変換先スキーマ、**値のマッピング**functoid です。  
  
    > [!NOTE]
    >  その他の functoid の出力と同様、**値のマッピング**functoid が別の functoid への入力として使用できます。  
  
## <a name="see-also"></a>参照  
 [マップへの高度な Functoid の追加](../core/adding-advanced-functoids-to-a-map.md)