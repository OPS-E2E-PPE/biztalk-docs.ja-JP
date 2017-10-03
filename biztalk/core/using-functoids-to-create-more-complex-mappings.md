---
title: "Functoid を使用して、複雑なマッピングを作成する |Microsoft ドキュメント"
ms.custom: 
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: 
ms.suite: 
ms.tgt_pltfrm: 
ms.topic: article
ms.assetid: 7d53e3a3-5ccd-4733-8c2f-3101e41fca61
caps.latest.revision: "10"
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: 736b6fa99844182c59db582182056faea1d3f322
ms.sourcegitcommit: cb908c540d8f1a692d01dc8f313e16cb4b4e696d
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 09/20/2017
---
# <a name="using-functoids-to-create-more-complex-mappings"></a>Functoid を使用した複雑なマッピングの作成

## <a name="overview"></a>概要
Functoid は、マッピング シナリオの多くで重要な役割を果たします。 Functoid を使用しなくても要素と属性データをコピーできますが、値自体を操作することはできません。 Functoid を使用すると、ほとんどすべての変換が可能です。 たとえば、Functoid を使用して、異なる場所から 2 つの値を取得し、これらの値を加算して、合計を送信先スキーマに配置できます。  
  
 BizTalk マップを編集するとき、Functoid は [!INCLUDE[btsVStudioNoVersion](../includes/btsvstudionoversion-md.md)] ツールボックスに表示されます。カテゴリごとにツールボックス タブが 1 つ表示されます。 ツールボックスを開き、対応するタブをクリックして Functoid のカテゴリを選択してから、Functoid をグリッド ページにドラッグします。 次に、Functoid とスキーマ ノード間、または Functoid と別の Functoid 間に入力リンクや出力リンクを作成します。 入力リンクは入力パラメーターに対応し、Functoid の左側から入ります。出力リンクは出力パラメーターに対応し、Functoid の右側に出て行きます。  
  
 他のマップ要素と同じように、Functoid にはプロパティがあります。 Functoid の最も重要なプロパティの 1 つは、入力パラメーターのセットです。 詳細については、次を参照してください。[マップに基本 Functoid を追加する方法](../core/how-to-add-basic-functoids-to-a-map.md)です。  
  
 このセクションでは、BizTalk マップでの Functoid の操作手順について説明します。 Functoid のリファレンスについては、次を参照してください。、 **Functoid リファレンス**[!INCLUDE[ui-guidance-developers-reference](../includes/ui-guidance-developers-reference.md)]です。
  
## <a name="next-steps"></a>次の手順 
  
-   [Functoid のツールボックスを開く方法](../core/how-to-open-the-functoid-toolbox.md)  
  
-   [マップに基本 Functoid を追加する方法](../core/how-to-add-basic-functoids-to-a-map.md)  
  
-   [マップへの高度な Functoid の追加](../core/adding-advanced-functoids-to-a-map.md)  
  
-   [Functoid のプロパティおよび入力パラメーターの編集](../core/editing-functoid-properties-and-input-parameters.md)  
  
-   [複数の Functoid を選択する方法](../core/how-to-select-multiple-functoids.md)  
  
-   [Functoid を削除する方法](../core/how-to-delete-functoids.md)  
  
-   [コピー、切り取り、および Functoid を貼り付けする方法](../core/how-to-copy-cut-and-paste-a-functoid.md)