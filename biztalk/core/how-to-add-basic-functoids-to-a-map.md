---
title: マップに基本 Functoid を追加する方法 |Microsoft ドキュメント
ms.custom: ''
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: ''
ms.suite: ''
ms.tgt_pltfrm: ''
ms.topic: article
ms.assetid: 6a81fb73-cccf-4f74-af92-39e4af13e255
caps.latest.revision: 8
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: 23a6748a5ce128ef13ce012412e36570e4e01eba
ms.sourcegitcommit: cb908c540d8f1a692d01dc8f313e16cb4b4e696d
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 09/20/2017
ms.locfileid: "22248986"
---
# <a name="how-to-add-basic-functoids-to-a-map"></a>マップに基本 Functoid を追加する方法
簡単に使用できる Functoid が多数用意されています。 これらと呼ばれるここまでで functoid と区別するための基本 functoid、**詳細**カテゴリ。 基本 Functoid では、変換、データベース、日時、論理、関数、文字列などのカテゴリを対象としています。  
  
 通常、基本 Functoid の入力リンクおよび出力リンクの型は数値や文字列などの単純な型です。  
  
 基本 Functoid を使用する場合、グリッド ページへの追加、Functoid への入力リンクの作成 (左側からのリンク)、および Functoid からの出力リンクの作成 (右側へのリンク) を行います。 このトピックでは、これらの作業の手順について説明します。  
  
## <a name="add-a-basic-functoid-to-a-map"></a>マップに基本 functoid を追加します。  
  
1.  [!INCLUDE[btsVStudioNoVersion](../includes/btsvstudionoversion-md.md)] ツールボックスをアクティブにして、該当するタブをクリックし、使用する Functoid のカテゴリを選択します。  
  
     選択したカテゴリで使用可能な Functoid の一覧が表示されます。  
  
2.  ツールボックスから使用する Functoid をグリッド ページの該当する位置にドラッグします。  
  
    > [!NOTE]
    >  Functoid は表示されているグリッド ページに配置されます。 別のグリッド ページに functoid を配置する場合は、その他のグリッド ページを最初に表示する必要があります。  
  
    > [!NOTE]
    >  複数の Functoid を同時に使用するマップを構築する場合は、相対的な位置 (左右) に注意する必要があります。 Functoids は左から順に実行されます。 1 つの Functoid からの出力は、これよりも右にある Functoid にのみ入力することができます。  
  
## <a name="create-input-links-to-a-basic-functoid"></a>基本 functoid への入力リンクを作成します。  
  
1.  送信元スキーマ内のレコード ノードまたはフィールド ノードを、表示されているグリッド ページ内の基本 Functoid にドラッグします。  
  
     **- または -**  
  
     表示されているグリッド ページで、入力リンクの対象となる基本 Functoid に、この Functoid よりも左にある別の Functoid をドラッグします。  
  
     **- または -**  
  
     表示されているグリッド ページ内の基本 Functoid を、送信元スキーマ内のレコード ノードまたはフィールド ノードにドラッグします。  
  
     **- または -**  
  
     表示されているグリッド ページで、入力リンクの対象となる基本 Functoid を、この Functoid よりも左に位置している別の Functoid にドラッグします。  
  
    > [!NOTE]
    >  ドラッグ中には、リンクの固定されたエンドポイントではなく、リンクの移動のエンドポイントより正確な対象とした 2 番目のエンドポイントの使用できるように十字カーソル アイコンに変わります。 リンクの移動、エンドポイント、リンクの適切な 2 番目のエンドポイントではなくなど、発生する可能性がデータ型の不一致がある場合にオブジェクトをポイントする場合、十字カーソル アイコンは、斜めのスラッシュを含む円を示すアイコンに変わります。  
  
2.  必要に応じて手順 1. を繰り返して、基本 Functoid への入力リンクのセットを完成します (ただし、入力パラメーターのすべてのセットが完成するわけではありません)。  
  
    > [!NOTE]
    >  一部の Functoid は、入力リンクを必要としません。 たとえば、**日付**、**時間**、および**日付と時刻**functoid を**日付と時刻**functoid カテゴリは、現在の日付を指定時間、または日付と時刻、インスタンス メッセージを処理中に、それぞれします。 したがって、送信元スキーマからの入力パラメーターは必要ありません。  
  
    > [!NOTE]
    >  多くの functoid への入力パラメーターの順序は、重要では、対応する functoid のリファレンス トピックに記載されている (を参照してください**Functoid リファレンス** [!INCLUDE[ui-guidance-developers-reference](../includes/ui-guidance-developers-reference.md)])。 リンクの作成順序により、Functoid への入力パラメーターの順序が設定されます。 Functoid のプロパティおよび functoid の入力パラメーターの順序の指定の詳細については、次を参照してください。 [Functoid プロパティの編集および入力パラメーター](../core/editing-functoid-properties-and-input-parameters.md)です。 Functoid の入力パラメーターを構成する方法については、次を参照してください。 [Functoid の入力パラメーターを構成する方法](../core/how-to-configure-functoid-input-parameters.md)です。  
  
    > [!NOTE]
    >  リンクを作成する前に、リンクの対象となる Functoid や送信元スキーマ ノードが、グリッド ページまたは送信元スキーマ ウィンドウに表示されていることを確認してください。  
  
## <a name="create-the-output-link-from-a-basic-functoid"></a>基本 functoid からの出力リンクを作成します。  
  
1.  送信先スキーマ内のレコード ノードまたはフィールド ノードを、表示されているグリッド ページ内の基本 Functoid にドラッグします。  
  
     **- または -**  
  
     表示されているグリッド ページで、出力リンクの対象となる基本 Functoid に、その Functoid よりも右に位置している別の Functoid をドラッグします。  
  
     **- または -**  
  
     表示されているグリッド ページ内の基本 Functoid を、送信先スキーマ内のレコード ノードまたはフィールド ノードにドラッグします。  
  
     **- または -**  
  
2.  表示されているグリッド ページで、出力リンクの対象となる基本 Functoid を、この Functoid よりも右に位置している別の Functoid にドラッグします。  
  
    > [!NOTE]
    >  リンクを作成する前に、リンクの対象となる Functoid や送信元スキーマ ノードが、グリッド ページまたは送信元スキーマ ウィンドウにそれぞれ表示されていることを確認してください。  
  
    > [!NOTE]
    >  Functoid のリンクの作成では、送信元と送信先のデータ型が一致しない場合など不適切なリンクは必ず拒否されます。  
  
    > [!NOTE]
    >  ドラッグしているときは、リンクの移動する側のエンドポイント (固定されたエンドポイントの反対側のポイント) が十字型に変わり、移動するエンドポイントが明確になるため、リンク先へ適切に接続することができます。 リンクの移動、エンドポイント、リンクの適切な 2 番目のエンドポイントではなくなど、発生する可能性がデータ型の不一致がある場合にオブジェクトをポイントする場合、十字カーソル アイコンは、斜めのスラッシュを含む円を示すアイコンに変わります。  
  
## <a name="see-also"></a>参照  
**Functoid のリファレンス**[!INCLUDE[ui-guidance-developers-reference](../includes/ui-guidance-developers-reference.md)]