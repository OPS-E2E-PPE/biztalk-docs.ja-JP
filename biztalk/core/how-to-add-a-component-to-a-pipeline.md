---
title: パイプラインにコンポーネントを追加する方法 |Microsoft Docs
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
ms.openlocfilehash: 7b1d37c6fafcec158f63c3728c773c19089658b2
ms.sourcegitcommit: 266308ec5c6a9d8d80ff298ee6051b4843c5d626
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 06/27/2018
ms.locfileid: "36991331"
---
# <a name="how-to-add-a-component-to-a-pipeline"></a>パイプラインにコンポーネントを追加する方法
コンポーネントをパイプラインに追加する場合は、ツールボックスからデザイン画面にパイプラインをドラッグします。  
  
### <a name="to-add-a-component-to-a-pipeline"></a>コンポーネントをパイプラインに追加するには  
  
- ツールボックスで、パイプライン コンポーネントをドラッグして、**ここにドロップします。** ボックスにドラッグします。  
  
  次の図は、パイプラインのデザイン画面がパイプラインに示しています。 このパイプラインには、アセンブル ステージとエンコード ステージという 2 つのステージがあります。 XML アセンブラー パイプライン コンポーネントがアセンブル ステージに追加されましたが、表示されたままにするため、エンコード ステージが空のまま、**ここにドロップします。** これは、ステージが空であること、つまりパイプライン コンポーネントを追加できることを示しています。  
  
  ![BizTalk パイプラインのステージおよびコンポーネント](../core/media/ebiz-pipe-stages02.gif "ebiz_pipe_stages02")  
  BizTalk パイプラインのステージおよびコンポーネントを示します。  
  
> [!NOTE]
>  パイプライン コンポーネントは、デザイン画面の特定の位置にのみドロップできます。 パイプライン コンポーネントをドロップできるのは、コンポーネントがステージ関係を持つステージ内のみです。 パイプライン コンポーネントをドロップできないポインターの隣には、中に 1 本の線が描かれた円が表示されます。 矢印が表示され、デザイン画面内でパイプライン コンポーネントを配置できる部分が強調表示されます。  
  
## <a name="see-also"></a>参照  
 [新しいパイプラインを作成する方法](../core/how-to-create-a-new-pipeline.md)   
 [パイプラインを開く方法](../core/how-to-open-a-pipeline.md)   
 [ツールボックスの使用方法](../core/how-to-use-the-toolbox.md)   
 [キーボードで移動する方法](../core/how-to-navigate-with-the-keyboard.md)   
 [パイプライン デザイナーでのパイプラインの作成](../core/creating-pipelines-with-pipeline-designer.md)