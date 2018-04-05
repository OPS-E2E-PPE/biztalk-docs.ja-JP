---
title: コンポーネントをパイプラインに追加する方法 |Microsoft ドキュメント
ms.custom: ''
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: ''
ms.suite: ''
ms.tgt_pltfrm: ''
ms.topic: article
helpviewer_keywords:
- pipelines, components
ms.assetid: 6b1dbeab-6acc-46d7-8ddd-79b79da3591c
caps.latest.revision: 7
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: 9a9f11f03e818ae1067bc22027822bfeef202260
ms.sourcegitcommit: cb908c540d8f1a692d01dc8f313e16cb4b4e696d
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 09/20/2017
---
# <a name="how-to-add-a-component-to-a-pipeline"></a>コンポーネントをパイプラインに追加する方法
コンポーネントをパイプラインに追加する場合は、ツールボックスからデザイン画面にパイプラインをドラッグします。  
  
### <a name="to-add-a-component-to-a-pipeline"></a>コンポーネントをパイプラインに追加するには  
  
-   ツールボックスで、パイプライン コンポーネントをドラッグして、**ここにドロップします。** ボックスにドラッグします。  
  
 次の図は、パイプラインがパイプラインのデザイン画面でどのように示されてを示します。 このパイプラインには、アセンブル ステージとエンコード ステージという 2 つのステージがあります。 XML アセンブラー パイプライン コンポーネントがアセンブル ステージに追加されましたが、エンコード ステージでは、空のまま表示されたままに**ここにドロップします。** これは、ステージが空であること、つまりパイプライン コンポーネントを追加できることを示しています。  
  
 ![BizTalk パイプラインのステージおよびコンポーネント](../core/media/ebiz-pipe-stages02.gif "ebiz_pipe_stages02")  
BizTalk パイプラインのステージおよびコンポーネントを示します。  
  
> [!NOTE]
>  パイプライン コンポーネントは、デザイン画面の特定の位置にのみドロップできます。 パイプライン コンポーネントをドロップできるのは、コンポーネントがステージ関係を持つステージ内のみです。 パイプライン コンポーネントをドロップできないポインターの隣には、中に 1 本の線が描かれた円が表示されます。 矢印が表示され、デザイン画面内でパイプライン コンポーネントを配置できる部分が強調表示されます。  
  
## <a name="see-also"></a>参照  
 [新しいパイプラインを作成する方法](../core/how-to-create-a-new-pipeline.md)   
 [パイプラインを開く方法](../core/how-to-open-a-pipeline.md)   
 [ツールボックスの使用方法](../core/how-to-use-the-toolbox.md)   
 [キーボードで移動する方法](../core/how-to-navigate-with-the-keyboard.md)   
 [パイプライン デザイナーでパイプラインの作成](../core/creating-pipelines-with-pipeline-designer.md)