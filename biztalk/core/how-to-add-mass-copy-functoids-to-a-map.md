---
title: マップに一括コピー Functoid を追加する方法 |Microsoft ドキュメント
ms.custom: ''
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: ''
ms.suite: ''
ms.tgt_pltfrm: ''
ms.topic: article
ms.assetid: 1cff63fc-8f34-4bd0-8501-a8401bde6349
caps.latest.revision: 8
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: 4cee6f2c53bbd3b3dbabe55f0160309532d0ebf3
ms.sourcegitcommit: cb908c540d8f1a692d01dc8f313e16cb4b4e696d
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 09/20/2017
ms.locfileid: "22247570"
---
# <a name="how-to-add-mass-copy-functoids-to-a-map"></a>マップに一括コピー Functoid を追加する方法
**一括コピー** functoid を含むスキーマを使用して、マップを有効に**任意**と**anyAttribute**要素。 これらの要素は基本的に、XML スキーマ定義言語で提供されているワイルドカードであり、不明な構造や属性のセットに一致します。  
  
 概要については、**一括コピー** functoid を参照してください[一括コピー Functoid](../core/mass-copy-functoid.md)です。  
  
### <a name="to-add-the-mass-copy-functoid-to-a-map-and-configure-it"></a>マップに一括コピー Functoid を追加して構成するには  
  
1.  [!INCLUDE[btsVStudioNoVersion](../includes/btsvstudionoversion-md.md)]ツールボックス active をクリックして、**高度な Functoid** functoid のカテゴリを選択するタブです。  
  
     選択したカテゴリに含まれる高度な Functoid の一覧が表示されます。  
  
2.  ドラッグ、**一括コピー** functoid (![](../core/media/advmasscopy.gif "advmasscopy")) をグリッド ページの適切な場所にツールボックスからです。  
  
    > [!NOTE]
    >  Functoid は表示されているグリッド ページに配置されます。 別のグリッド ページに functoid を配置する場合は、その他のグリッド ページを最初に表示する必要があります。  
  
    > [!NOTE]
    >  複数の Functoid を同時に使用するマップを構築する場合は、相対的な位置 (左右) に注意する必要があります。 Functoids は左から順に実行されます。 1 つの Functoid からの出力は、これよりも右にある Functoid にのみ入力することができます。  
  
3.  入力パラメーターを設定する、**一括コピー** functoid、送信元スキーマからレコードをドラッグして、入力リンクを作成、**一括コピー** functoid をドラッグするか、**一括コピー** functoid、送信元スキーマ内のレコードを送信します。  
  
4.  出力パラメーターを使用する、**一括コピー** functoid をドラッグして、出力リンクを作成、**一括コピー** functoid を送信先スキーマのレコードをドラッグするか、送信先スキーマのレコードを**一括コピー** functoid です。  
  
    > [!NOTE]
    >  他の functoid とは異なりの出力を使用することはできません、**一括コピー** functoid を別の functoid の入力として。  
  
> [!NOTE]
>  挿入して構成することができます、**一括コピー**直接リンクすると 2 つの functoid を記録します。 詳細については、リンクするには、一括コピー functoid を使用する」セクションを参照してください[レコードを自動的にリンクする方法](../core/how-to-link-records-automatically.md)です。  
  
## <a name="see-also"></a>参照  
 [マップへの高度な Functoid の追加](../core/adding-advanced-functoids-to-a-map.md)