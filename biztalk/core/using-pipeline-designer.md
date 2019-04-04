---
title: パイプライン デザイナーの使用 |Microsoft Docs
ms.custom: ''
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: ''
ms.suite: ''
ms.tgt_pltfrm: ''
ms.topic: article
helpviewer_keywords:
- Pipeline Designer, how to
- pipelines, Pipeline Designer
ms.assetid: bdb2f5c7-f8a2-4bd6-a8d8-8b7a64f97bd0
caps.latest.revision: 8
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: 0f5a3e2d9d3dad37372fc01f6446f0c06272589a
ms.sourcegitcommit: 266308ec5c6a9d8d80ff298ee6051b4843c5d626
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 06/27/2018
ms.locfileid: "37019024"
---
# <a name="using-pipeline-designer"></a>パイプライン デザイナーの使用
パイプライン デザイナーとは、Microsoft [!INCLUDE[btsVStudioNoVersion](../includes/btsvstudionoversion-md.md)] でホストされるグラフィカル エディターのことで、パイプラインの新規作成、Microsoft [!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)] に付属するパイプライン テンプレートの表示、パイプライン内でのパイプライン コンポーネントの移動のほか、パイプライン、ステージ、パイプライン コンポーネントの構成などを実行できます。  
  
 パイプライン デザイナーは、[!INCLUDE[btsVStudioNoVersion](../includes/btsvstudionoversion-md.md)] シェルが備える 3 つのツールを使ってデザイン作業をサポートします。  
  
- プロパティ ウィンドウ。パイプライン オブジェクトの特性の多くは、このウィンドウで表示したり変更したりできます。  
  
- ツールボックス。デザイン画面のソースとして使用されます。  
  
- デザイン画面。ツールボックスのコンポーネントはデザイン画面にドラッグ アンド ドロップされます。  
  
  次の図は、パイプライン デザイナーの環境を示しています。  
  
  ![パイプライン デザイナー編集環境](../core/media/ebiz-prog-usepipe.gif "ebiz_prog_usepipe")  
  パイプライン デザイナーの環境  
  
  開発作業をより効率化するため、パイプライン デザイナーは、BizTalk プロジェクト テンプレートと統合されます。 新しい BizTalk プロジェクトを作成するプロジェクト システムを使用して後で使用できます、**新しい項目の追加**コマンドを**ファイル**パイプラインをソリューションに追加するメニュー。 BizTalk プロジェクト テンプレートの詳細については、[BizTalk プロジェクト システムを使用して](../core/using-the-biztalk-project-system.md)を参照してください。  
  
> [!NOTE]
>  以前のバージョンの [!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)] では、パイプラインの概念が、メッセージ チャネルおよびポートとしてカプセル化され、ドキュメントに適用される特定のコンポーネントの順序も、このメッセージ チャネルとポートによって定義されていました。 新しいバージョンでは、パイプラインによって柔軟性が向上しています。パイプラインの各ステージに含まれるコンポーネントの順序を自由に変更できるほか、パイプラインのいたるところにカスタム コンポーネントを容易に挿入できます。  
  
 パイプライン デザイナーのデザイン画面では、パイプラインをグラフィカルに表現できます。 デザイン画面は、[!INCLUDE[btsVStudioNoVersion](../includes/btsvstudionoversion-md.md)] ウィンドウのメイン セクションに表示され、この画面を使って、BizTalk プロジェクトに含まれるパイプラインを編集できます。 またデザイン画面のタブをクリックすることにより、複数のパイプラインを切り替えて表示できます。  
  
 各パイプラインはステージで構成され、各ステージには、少なくとも 1 つのコンポーネントが含まれます。 ステージにコンポーネントが存在しない場合は、ツールボックスから図形を挿入するよう促す警告が表示されます。 この警告は、1 つ目の図形をステージに挿入した時点で消えます。 デザイン画面には、パイプラインが上 (始点) から下 (終点) へと縦方向に表示されます。  
  
 他の一般的な Microsoft Windows プログラムとを実行すると、いくつかのタスクなど**オープン**と**保存**から、**ファイル**メニュー。  
  
## <a name="see-also"></a>参照  
 [パイプライン デザイナーでパイプラインを作成します。](../core/creating-pipelines-with-pipeline-designer.md)   
 [パイプライン デザイナーを使用したパイプラインの作成](../core/creating-pipelines-using-pipeline-designer.md)