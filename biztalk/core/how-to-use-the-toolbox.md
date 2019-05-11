---
title: ツールボックスを使用する方法 |Microsoft Docs
ms.custom: ''
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: ''
ms.suite: ''
ms.tgt_pltfrm: ''
ms.topic: article
helpviewer_keywords:
- creating, pipelines
- pipeline components, deleting from toolbox
- pipeline components, Pipeline Designer
- pipeline components, adding to toolbox
- Pipeline Designer, toolbox
- pipelines, creating
ms.assetid: 7a60c590-1a38-46fe-addf-0aa2c8b63cf9
caps.latest.revision: 9
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: 2990cdf576f1678078da564932542081512d09dd
ms.sourcegitcommit: 381e83d43796a345488d54b3f7413e11d56ad7be
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 05/07/2019
ms.locfileid: "65383177"
---
# <a name="how-to-use-the-toolbox"></a>ツールボックスの使用方法
パイプラインを作成するには、コンポーネント (図形) をツールボックスからデザイン画面にドラッグします。 パイプライン デザイナーを使用して、作成プロセスを特定の制限を配置することで有効なパイプラインをアセンブルできます。 作成するパイプラインの種類に適用できるツールボックス コンポーネントのみ選択できます。 たとえば、受信パイプラインは表示デコーダー、逆アセンブラー、および検証コントロール ツールボックス コンポーネントの有効なものとして、エンコードとアセンブラーが無効にするときに (淡色表示になります)。  
  
 さらに、ステージでは、有効なコンポーネントのみを受け入れることができます。 たとえば、アセンブル ステージにエンコーダー コンポーネントをドラッグすることはできません。 有効なドロップ位置の近くのコンポーネントをドラッグするときに、コンポーネントを挿入できるポイントを示す矢印が表示されます。  
  
 折りたたまれたステージに有効なコンポーネントをドラッグした場合は、数秒を展開して、ステージにコンポーネントをドロップ ステージ上でマウス ポインターを置きます。  
  
 カスタム コンポーネントをパイプライン デザイナーのツールボックスに追加するには、標準の Microsoft と似ています[!INCLUDE[btsVStudioNoVersion](../includes/btsvstudionoversion-md.md)]プロシージャ。  
  
 **開始および終了の図形**  
  
 **開始**と**エンド**図形のすべてのパイプラインの行頭文字として表示されます。 デザイン サーフェイスで視覚的に整理だけに提供されます。 それぞれ、1 つだけを使用する必要があると、それらはする追加も削除します。 **開始**と**エンド**図形がツールボックスに表示されません。  
  
### <a name="to-add-a-pipeline-component-to-the-toolbox"></a>パイプライン コンポーネントをツールボックスに追加するには  
  
1.  **[ツール]** メニューで **[ツールボックス アイテムの選択]** をクリックします。  
  
     - または -  
  
     ツールボックスを右クリックし、をクリックし、**アイテムの選択**します。  
  
2.  **ツールボックスのカスタマイズ**ダイアログ ボックスで、をクリックして、 **BizTalk パイプライン コンポーネント**タブ。  
  
     ダイアログ ボックスには、互換性のあるパイプライン コンポーネントが表示されます。 ダイアログ ボックスの上部にあるタブをクリックして、カテゴリを移動できます。  
  
3.  ツールボックスに追加するコンポーネントを選択します。  
  
4.  **[OK]** をクリックします。 コンポーネントが表示されます、 **BizTalk パイプライン コンポーネント**ツールボックス タブをクリックします。  
  
### <a name="to-remove-a-pipeline-component-from-the-toolbox"></a>ツールボックスからパイプライン コンポーネントを削除するには  
  
-   開く、**ツールボックスのカスタマイズ**(上記の手順のようにダイアログ ボックスおよび削除するコンポーネントをクリアします。  
  
     ツールボックスから削除された後でも、コンポーネントは登録済みのままになります。  
  
## <a name="see-also"></a>参照  
 [新しいパイプラインを作成する方法](../core/how-to-create-a-new-pipeline.md)   
 [パイプラインを開く方法](../core/how-to-open-a-pipeline.md)   
 [キーボードで移動する方法](../core/how-to-navigate-with-the-keyboard.md)   
 [パイプライン デザイナーでのパイプラインの作成](../core/creating-pipelines-with-pipeline-designer.md)