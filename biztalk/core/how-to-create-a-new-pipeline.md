---
title: 新しいパイプラインを作成する方法 |Microsoft ドキュメント
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
ms.openlocfilehash: 83c1df14c0015ac26b99ad8f0760fe18438e8024
ms.sourcegitcommit: cb908c540d8f1a692d01dc8f313e16cb4b4e696d
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 09/20/2017
ms.locfileid: "22248762"
---
# <a name="how-to-create-a-new-pipeline"></a>新しいパイプラインを作成する方法
プロジェクトにパイプライン テンプレートを追加して、新しいパイプラインを作成できます。  
  
> [!WARNING]
>  カスタム パイプライン コンポーネントの実装を含むプロジェクトを、そのパイプライン コンポーネントを使用しているプロジェクトを含むソリューションには追加しないでください。 このような状況でプロジェクトを追加すると、次回のソリューションの再ビルド時に、出力 dll が他のプロセスにより使用されていることを示すエラーが発生します。  
  
### <a name="to-create-a-new-pipeline"></a>新しいパイプラインを作成するには  
  
1.  ソリューション エクスプローラーで、パイプラインを作成するプロジェクトを選択します。  
  
2.  **[プロジェクト]** メニューの **[新しい項目の追加]** をクリックします。  
  
3.  **新しい項目の追加**ダイアログ ボックスで、**受信パイプライン**または**送信パイプライン**テンプレートを 1 回クリックするとします。  
  
    > [!NOTE]
    >  パイプラインに表示される既定の名前で自動的に作成する場合は、テンプレートをダブルクリックすると、**名前**フィールドです。  
  
4.  **名前**フィールドに、パイプラインの名前を入力します。  
  
5.  **[開く]** をクリックします。  
  
     新しいパイプラインがソリューション エクスプローラーに表示されます。 デザイン画面に、パイプラインのステージおよび既定のコンポーネントが表示されます。  
  
 パイプライン コンポーネントをパイプラインに追加する方法の詳細については、次を参照してください。[パイプラインにコンポーネントを追加する方法](../core/how-to-add-a-component-to-a-pipeline.md)です。  
  
## <a name="see-also"></a>参照  
 [パイプラインを開く方法](../core/how-to-open-a-pipeline.md)   
 [パイプラインを保存する方法](../core/how-to-save-a-pipeline.md)   
 [ツールボックスの使用方法](../core/how-to-use-the-toolbox.md)   
 [キーボードで移動する方法](../core/how-to-navigate-with-the-keyboard.md)   
 [パイプライン デザイナーでパイプラインの作成](../core/creating-pipelines-with-pipeline-designer.md)