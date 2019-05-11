---
title: マップに一括コピー Functoid を追加する方法 |Microsoft Docs
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
ms.openlocfilehash: 9949e849dae69873ff3f71ad2813b7d26058e124
ms.sourcegitcommit: 381e83d43796a345488d54b3f7413e11d56ad7be
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 05/07/2019
ms.locfileid: "65343262"
---
# <a name="how-to-add-mass-copy-functoids-to-a-map"></a>マップに一括コピー Functoid を追加する方法
**一括コピー**により、マップが含まれるスキーマを使用して、functoid**任意**と**anyAttribute**要素。 これらの要素は基本的に、不明な構造や属性のセットを一致するように、XML スキーマ定義言語で提供されているワイルドカードです。  
  
 概念情報については、**一括コピー** functoid を参照してください[一括コピー Functoid](../core/mass-copy-functoid.md)します。  
  
### <a name="to-add-the-mass-copy-functoid-to-a-map-and-configure-it"></a>マップに一括コピー functoid を追加し、構成するには  
  
1. [!INCLUDE[btsVStudioNoVersion](../includes/btsvstudionoversion-md.md)]ツールボックス active をクリックして、**高度な Functoid** functoid のカテゴリを選択するタブ。  
  
    選択したカテゴリでの高度な functoid の一覧が表示されます。  
  
2. ドラッグ、**一括コピー** functoid (![](../core/media/advmasscopy.gif "advmasscopy")) ツールボックスからグリッド ページの適切な場所にします。  
  
   > [!NOTE]
   >  Functoid は表示されているグリッド ページに配置されます。 別のグリッド ページに functoid を配置する場合は、最初にその他のグリッド ページを表示する必要があります。  
  
   > [!NOTE]
   >  複数の Functoid を同時に使用するマップを構築する場合は、相対的な位置 (左右) に注意する必要があります。 Functoids は左から順に実行されます。 1 つの Functoid からの出力は、これよりも右にある Functoid にのみ入力することができます。  
  
3. 入力パラメーターを設定する、**一括コピー** functoid、送信元スキーマからレコードをドラッグして、入力リンクを作成、**一括コピー** functoid をドラッグするか、**一括コピー** functoid、送信元スキーマ内のレコードを送信します。  
  
4. 出力パラメーターを使用する、**一括コピー** functoid をドラッグして、出力リンクを作成、**一括コピー**または変換先スキーマのレコードをドラッグして、送信先スキーマのレコードを functoid**一括コピー** functoid。  
  
   > [!NOTE]
   >  他の functoid とは異なりの出力を使用することはできません、**一括コピー** functoid を別の functoid への入力として。  
  
> [!NOTE]
>  挿入して構成することができます、**一括コピー**直接リンクする 2 つの functoid を記録します。 詳細については、一括コピー functoid を使用してリンク"するには」セクションを参照してください[レコードを自動的にリンクする方法](../core/how-to-link-records-automatically.md)します。  
  
## <a name="see-also"></a>参照  
 [マップへの高度な Functoid の追加](../core/adding-advanced-functoids-to-a-map.md)