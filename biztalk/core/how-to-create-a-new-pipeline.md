---
title: 新しいパイプラインを作成する方法 |Microsoft Docs
ms.custom: ''
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: ''
ms.suite: ''
ms.tgt_pltfrm: ''
ms.topic: article
helpviewer_keywords:
- creating, pipelines
- pipelines, warnings
- Pipeline Designer, warnings
- pipelines, creating
ms.assetid: bd95325e-1a72-4705-80f6-37ac092d11a3
caps.latest.revision: 8
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: 00f19818dd5df6cafaf51298a0463ea745736ab5
ms.sourcegitcommit: c3070a7a3f332857357f056dc632829b43869c17
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 11/14/2018
ms.locfileid: "51630391"
---
# <a name="how-to-create-a-new-pipeline"></a>新しいパイプラインを作成する方法
プロジェクトにパイプライン テンプレートを追加して、新しいパイプラインを作成できます。  
  
> [!WARNING]
>  また、そのパイプライン コンポーネントを使用してプロジェクトを含むソリューションにカスタム パイプライン コンポーネントの実装を含むプロジェクトを追加する必要がありますできません。 このような状況でプロジェクトを追加すると、次回のソリューションの再ビルド時に、出力 dll が他のプロセスにより使用されていることを示すエラーが発生します。  
  
### <a name="to-create-a-new-pipeline"></a>新しいパイプラインを作成するには  
  
1. ソリューション エクスプローラーで、パイプラインを作成するプロジェクトを選択します。  
  
2. **[プロジェクト]** メニューの **[新しい項目の追加]** をクリックします。  
  
3. **新しい項目の追加**ダイアログ ボックスで、**受信パイプライン**または**送信パイプライン**テンプレートで 1 回クリックします。  
  
   > [!NOTE]
   >  パイプラインに表示される既定の名前を自動的に作成されます、テンプレートをダブルクリックした場合、**名前**フィールド。  
  
4. **名前**フィールドに、パイプラインの名前を入力します。  
  
5. **[開く]** をクリックします。  
  
    新しいパイプラインがソリューション エクスプローラーに表示されます。 デザイン画面に、パイプラインのステージおよび既定のコンポーネントが表示されます。  
  
   パイプライン コンポーネントをパイプラインに追加する方法の詳細については、次を参照してください。[パイプラインにコンポーネントを追加する方法](../core/how-to-add-a-component-to-a-pipeline.md)します。  
  
## <a name="see-also"></a>参照  
 [パイプラインを開く方法](../core/how-to-open-a-pipeline.md)   
 [パイプラインを保存する方法](../core/how-to-save-a-pipeline.md)   
 [ツールボックスの使用方法](../core/how-to-use-the-toolbox.md)   
 [キーボードで移動する方法](../core/how-to-navigate-with-the-keyboard.md)   
 [パイプライン デザイナーでのパイプラインの作成](../core/creating-pipelines-with-pipeline-designer.md)