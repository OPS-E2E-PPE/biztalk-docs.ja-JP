---
title: 追加する方法にアサート Functoid をマップ |Microsoft Docs
ms.custom: ''
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: ''
ms.suite: ''
ms.tgt_pltfrm: ''
ms.topic: article
ms.assetid: ccdd79a2-b70f-489b-8711-e00a50d8e2d8
caps.latest.revision: 7
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: e4cfeabbbeac860e927854fb79c90d2b1608b9c3
ms.sourcegitcommit: 266308ec5c6a9d8d80ff298ee6051b4843c5d626
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 06/27/2018
ms.locfileid: "37015275"
---
# <a name="how-to-add-assert-functoids-to-a-map"></a>マップにアサート Functoid を追加する方法
**Assert** functoid では、マップには、条件に関する仮定をテストすることができます。 たとえば、製品の購入で追加の割引を決定する計算を実行する場合がありますをアサートする追加の割引になる論理 functoid を使用して 100 ドルを超える (**より大きい**または**Less Than**)。  

> [!NOTE]
>  **Assert** functoid は、開発途中のビルドにのみ実行されますか、**デバッグ情報の生成**プロジェクトのビルド設定のプロパティに設定されて**True**します。 展開用に、BizTalk アプリケーションをコンパイルするときに、**デバッグ情報の生成**プロパティに設定されて**False** (既定)、アサートは無視されます。  

 概念情報については、 **Assert** functoid を参照してください[アサート Functoid](../core/assert-functoid.md)します。  

## <a name="add-the-assert-functoid-to-a-map-and-configure-it"></a>マップにアサート functoid を追加し、構成  

1. [!INCLUDE[btsVStudioNoVersion](../includes/btsvstudionoversion-md.md)]ツールボックス active をクリックして、**高度な Functoid** functoid のカテゴリを選択するタブ。 選択したカテゴリに含まれる高度な Functoid の一覧が表示されます。  

2. ドラッグ、 **Assert** functoid (![アサート functoid](../core/media/advanced-assert-functoid.gif "advanced_assert_functoid")) ツールボックスからグリッド ページの適切な場所にします。  

   > [!NOTE]
   >  Functoid は表示されているグリッド ページに配置されます。 別のグリッド ページに functoid を配置する場合は、最初にその他のグリッド ページを表示する必要があります。 
   >    
   >  複数の Functoid を使用するマップを構築する場合は、相対的な位置 (左右) に注意する必要があります。 Functoids は左から順に実行されます。 1 つの Functoid からの出力は、これよりも右にある Functoid にのみ入力することができます。  

3. Functoid には 3 つの入力パラメーターが必要で、それによって 1 つの出力パラメーターが生成されます。 最初のパラメーターを確立するために、 **Assert** functoid からその他の出力をドラッグして、入力リンクを作成**論理**functoid または入力インスタンス メッセージ内の変数ブール値フィールドから。  

4. 2 番目の入力パラメーターを設定する、 **Assert** functoid は、フィールド ノードに送信元スキーマによって、入力リンクを作成、 **Assert** functoid、または定数を挿入します。  

5. 3 番目の入力パラメーターを設定する、 **Assert** functoid、送信元スキーマ内のフィールド ノードで、入力リンクを作成、 **Assert** functoid、定数を挿入または。  

6. 出力パラメーターを使用する、 **Assert** functoid をドラッグして、出力リンクを作成、 **Assert** functoid を送信先スキーマ内のフィールド。  

   > [!NOTE]
   >  他の functoid の出力と同様、 **Assert** functoid を別の functoid への入力として使用できます。  

## <a name="see-also"></a>参照  
- **アサート Functoid リファレンス** [!INCLUDE[ui-guidance-developers-reference](../includes/ui-guidance-developers-reference.md)]   
- [マップへの高度な Functoid の追加](../core/adding-advanced-functoids-to-a-map.md)
