---
title: 値のマッピング (フラット化) Functoid をマップに追加する方法 |Microsoft ドキュメント
ms.custom: ''
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: ''
ms.suite: ''
ms.tgt_pltfrm: ''
ms.topic: article
ms.assetid: 00a447c3-58d0-42ab-a5c4-417ee7800a6b
caps.latest.revision: 7
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: 2e5fe3f7b55a5bd5ef532bf2727c60bad2a621c7
ms.sourcegitcommit: cb908c540d8f1a692d01dc8f313e16cb4b4e696d
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 09/20/2017
ms.locfileid: "22247586"
---
# <a name="how-to-add-value-mapping-flattening-functoids-to-a-map"></a>マップに値のマッピング (フラット化) Functoid を追加する方法
**値のマッピング (フラット化)** functoid では、複数のレコードを 1 つのレコードに変換することによって、入力インスタンス メッセージの一部をフラット化することができます。 これは、Microsoft Commerce Server カタログを変換する場合の一般的な操作です。  
  
 概要については、**値のマッピング (フラット化)** functoid を参照してください[値のマッピング (フラット化) Functoid](../core/value-mapping-flattening-functoid.md)です。  
  
### <a name="to-add-the-value-mapping-flattening-functoid-to-a-map-and-configure-it"></a>マップに値のマッピング (フラット化) Functoid を追加して構成するには  
  
1.  [!INCLUDE[btsVStudioNoVersion](../includes/btsvstudionoversion-md.md)]ツールボックス active をクリックして、**高度な Functoid** functoid のカテゴリを選択するタブです。  
  
     選択したカテゴリに含まれる高度な Functoid の一覧が表示されます。  
  
2.  ドラッグ、**値のマッピング (フラット化)** functoid (![](../core/media/bts-tls-valmapflat.gif "bts_tls_valmapflat")) をグリッド ページの適切な場所にツールボックスからです。  
  
    > [!NOTE]
    >  Functoid は表示されているグリッド ページに配置されます。 別のグリッド ページに functoid を配置する場合は、その他のグリッド ページを最初に表示する必要があります。  
  
    > [!NOTE]
    >  複数の Functoid を同時に使用するマップを構築する場合は、相対的な位置 (左右) に注意する必要があります。 Functoids は左から順に実行されます。 1 つの Functoid からの出力は、これよりも右にある Functoid にのみ入力することができます。  
  
3.  最初の入力パラメーターを確立するために、**値のマッピング (フラット化)** functoid をドラッグして、入力リンクを作成、**値のマッピング (フラット化)** ソースのレコードまたはフィールド ノードを functoidスキーマまたはブールのデータ型を持つ別の functoid の左側とを"true"または"false"の入力値が生成されます  
  
    > [!NOTE]
    >  ドラッグすることも、反対方向にドラッグするブール値のソース、**値のマッピング (フラット化)** functoid です。  
  
4.  2 番目の入力パラメーターを設定する、**値のマッピング (フラット化)** functoid をドラッグして、入力リンクを作成、**値のマッピング (フラット化)** ソースのレコードまたはフィールド ノードを functoidスキーマに送信元スキーマのレコードまたはフィールド ノードをドラッグするか、**値のマッピング (フラット化)** functoid、または定数を挿入します。  
  
    > [!NOTE]
    >  2 番目の入力パラメーターを**値のマッピング (フラット化)** functoid もできる別の functoid の出力からの左側にします。 リンクを作成して表す、このような入力ソースを他の関連する functoid に関連する functoid のいずれかをドラッグしています。  
  
5.  出力パラメーターを使用する、**値のマッピング (フラット化)** functoid をドラッグして、出力リンクを作成、**値のマッピング (フラット化)** レコードまたはフィールドを送信先スキーマで functoid変換先スキーマのレコード フィールドをドラッグして、**値のマッピング (フラット化)** functoid です。  
  
    > [!NOTE]
    >  その他の functoid の出力と同様、**値のマッピング (フラット化)** functoid を別の functoid への入力として使用できます。  
  
## <a name="see-also"></a>参照  
 [マップへの高度な Functoid の追加](../core/adding-advanced-functoids-to-a-map.md)