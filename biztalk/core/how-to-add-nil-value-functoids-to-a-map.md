---
title: マップに Nil 値 Functoid を追加する方法 |Microsoft Docs
ms.custom: ''
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: ''
ms.suite: ''
ms.tgt_pltfrm: ''
ms.topic: article
ms.assetid: b2e193ed-fe5c-4b12-aab8-ff2d81fd45e1
caps.latest.revision: 7
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: 8488ea03fb40e1616b98e3ac8a1fc68b18e70e9b
ms.sourcegitcommit: 266308ec5c6a9d8d80ff298ee6051b4843c5d626
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 06/27/2018
ms.locfileid: "37011867"
---
# <a name="how-to-add-nil-value-functoids-to-a-map"></a>マップに Nil 値 Functoid を追加する方法
**Nil 値**functoid を送信先ノードの値を設定する**Nil**します。  

 概念情報については、 **Nil 値**functoid を参照してください[Nil 値 Functoid](../core/nil-value-functoid.md)します。  

## <a name="add-the-nil-value-functoid-to-a-map-and-configure-it"></a>マップに Nil 値 functoid を追加し、構成  

1. [!INCLUDE[btsVStudioNoVersion](../includes/btsvstudionoversion-md.md)]ツールボックス active をクリックして、**高度な Functoid** functoid のカテゴリを選択するタブ。 選択したカテゴリに含まれる高度な Functoid の一覧が表示されます。  

2. ドラッグ、 **Nil 値**functoid (![Nil 値 functoid](../core/media/advanced-nil-value-functoid.gif "advanced_nil_value_functoid")) ツールボックスからグリッド ページの適切な場所にします。  

   > [!NOTE]
   >  Functoid は表示されているグリッド ページに配置されます。 別のグリッド ページに functoid を配置する場合は、最初にその他のグリッド ページを表示する必要があります。  
   >
   >  複数の Functoid を使用するマップを構築する場合は、相対的な位置 (左右) に注意する必要があります。 Functoids は左から順に実行されます。 1 つの Functoid からの出力は、これよりも右にある Functoid にのみ入力することができます。  

3. **Nil 値**functoid は 1 つの入力パラメーターに 0 であることができます。 この functoid の入力パラメーターがない場合は、ターゲット ノードに設定されている**Nil**します。 入力パラメーターを設定する、 **Nil 値**functoid からその他の出力をドラッグして、入力リンクを作成**論理**functoid または入力インスタンス メッセージ内の変数ブール値フィールドから。  

4. 出力パラメーターを使用する、 **Nil 値**functoid をドラッグして、出力リンクを作成、 **Nil 値**functoid、レコードまたは送信先スキーマ内のフィールドをします。  

   > [!NOTE]
   >  他の functoid の出力と同様、 **Nil 値**functoid を別の functoid への入力として使用できます。  

## <a name="see-also"></a>参照  
- **Nil 値 Functoid のリファレンス** [!INCLUDE[ui-guidance-developers-reference](../includes/ui-guidance-developers-reference.md)]   
- [マップへの高度な Functoid の追加](../core/adding-advanced-functoids-to-a-map.md)
