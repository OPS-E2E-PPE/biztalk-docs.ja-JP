---
title: "ツールボックスを使用する方法 |Microsoft ドキュメント"
ms.custom: 
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: 
ms.suite: 
ms.tgt_pltfrm: 
ms.topic: article
helpviewer_keywords:
- creating, pipelines
- pipeline components, deleting from toolbox
- pipeline components, Pipeline Designer
- pipeline components, adding to toolbox
- Pipeline Designer, toolbox
- pipelines, creating
ms.assetid: 7a60c590-1a38-46fe-addf-0aa2c8b63cf9
caps.latest.revision: "9"
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: 3965a063aebcc932f07937fd19c3998412591ea1
ms.sourcegitcommit: cb908c540d8f1a692d01dc8f313e16cb4b4e696d
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 09/20/2017
---
# <a name="how-to-use-the-toolbox"></a>ツールボックスの使用方法
パイプラインを作成する場合は、コンポーネント (図形) をツールボックスからデザイン画面にドラッグします。 パイプライン デザイナーでは、作成プロセスに特定の制限を設けることによって、有効なパイプラインをアセンブルできます。 作成しているパイプラインの種類に適用できるツールボックス コンポーネントのみ選択できます。 たとえば、受信パイプラインの場合は有効なツールボックス コンポーネントとしてデコーダー、逆アセンブラー、および検証が示されますが、エンコードとアセンブラーは無効 (淡色表示) になります。  
  
 さらに、ステージは有効なコンポーネントのみを受け取ります。 たとえば、エンコーダー コンポーネントをアセンブル ステータスにドラッグすることはできません。 ドロップ先として有効な場所の付近までコンポーネントをドラッグすると、矢印が表示され、コンポーネントを挿入できるポイントが示されます。  
  
 折りたたまれたステージの場合は、有効なコンポーネントをドラッグし、マウスをステージ上で静止させると、数秒後にステージが展開され、コンポーネントをドロップできます。  
  
 パイプライン デザイナーのツールボックスにカスタム コンポーネントを追加する手順は、Microsoft [!INCLUDE[btsVStudioNoVersion](../includes/btsvstudionoversion-md.md)] の標準的な手順と同様です。  
  
 **開始および終了の図形**  
  
 **開始**と**終了**図形のすべてのパイプラインに行頭文字として表示されます。 これらは、構成を視覚的にわかりやすくするために、デザイン画面上に表示されます。 開始および終了図形はそれぞれ 1 つのみが表示され、追加や削除はできません。 **開始**と**終了**図形がツールボックスに表示されません。  
  
### <a name="to-add-a-pipeline-component-to-the-toolbox"></a>パイプライン コンポーネントをツールボックスに追加するには  
  
1.  **[ツール]** メニューで **[ツールボックス アイテムの選択]**をクリックします。  
  
     - または -  
  
     ツールボックスを右クリックし、をクリックして**アイテムの選択**です。  
  
2.  **ツールボックスのカスタマイズ**ダイアログ ボックスで、をクリックして、 **BizTalk パイプライン コンポーネント**タブです。  
  
     ダイアログ ボックスには、互換性のあるパイプライン コンポーネントが表示されます。 ダイアログ ボックスの上部にあるタブをクリックすると、カテゴリ間を移動できます。  
  
3.  ツールボックスに追加するコンポーネントを選択します。  
  
4.  **[OK]**をクリックします。 コンポーネントが表示されます、 **BizTalk パイプライン コンポーネント**ツールボックス タブをクリックします。  
  
### <a name="to-remove-a-pipeline-component-from-the-toolbox"></a>パイプライン コンポーネントをツールボックスから削除するには  
  
-   開く、**ツールボックスのカスタマイズ** ダイアログ ボックス (上記の手順と、削除するコンポーネントをクリアします。  
  
     ツールボックスから削除した後も、コンポーネントは登録されたままの状態です。  
  
## <a name="see-also"></a>参照  
 [新しいパイプラインを作成する方法](../core/how-to-create-a-new-pipeline.md)   
 [パイプラインを開く方法](../core/how-to-open-a-pipeline.md)   
 [キーボードで移動する方法](../core/how-to-navigate-with-the-keyboard.md)   
 [パイプライン デザイナーでパイプラインの作成](../core/creating-pipelines-with-pipeline-designer.md)