---
title: 送信パイプラインの作成、FRR |Microsoft ドキュメント
ms.custom: ''
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: ''
ms.suite: ''
ms.tgt_pltfrm: ''
ms.topic: article
helpviewer_keywords:
- FRR, creating send pipelines
- creating, send pipelines
- send pipelines, creating
ms.assetid: c6cd2047-ea53-425f-80cc-b02a1deb5292
caps.latest.revision: 6
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: 87733b6b3a93d2543d26cd6d11b366b84218d207
ms.sourcegitcommit: cb908c540d8f1a692d01dc8f313e16cb4b4e696d
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 09/20/2017
ms.locfileid: "22209458"
---
# <a name="creating-the-frr-send-pipeline"></a>FRR 送信パイプラインを作成します。
FIN 対応調整を実行するには、SWIFT アセンブラーだけでなく、SWIFTAsmFrrMQSeriesHelper パイプライン コンポーネントを含む送信パイプラインを作成する必要があります。  
  
 **概要**  
  
 次の段階で、送信パイプラインを作成します。  
  
|段階|コンポーネント|  
|-----------|---------------|  
|アセンブル ステージ|SWIFT アセンブラー|  
|エンコード ステージ|SWIFT Frr MQSeries の送信コンポーネント|  
  
### <a name="to-create-a-custom-send-pipeline-for-frr"></a>FRR のカスタムの送信パイプラインを作成するには  
  
1.  ソリューション エクスプ ローラーの Visual Studio で、パイプライン プロジェクトを右クリックし、**追加**、クリックして**新しい項目の**します。  
  
2.  [新しい項目の追加] ダイアログ ボックスで選択**送信パイプライン**[テンプレート] ペインからです。  
  
3.  **名前**ボックスで、受信パイプラインの名前を入力します。 **FRRSendPipeline.btp**です。 **[追加]** をクリックします。  
  
4.  [!INCLUDE[btsVStudioNoVersion](../../includes/btsvstudionoversion-md.md)]をクリックして**ビュー**し**ツールボックス**です。  
  
5.  BizTalk パイプライン コンポーネント [ツールボックス] からドラッグ**SWIFT アセンブラー**を**ここにドロップ**下のボックス、**アセンブル**で図形をステージ**BizTalk パイプラインデザイナー**です。  
  
6.  BizTalk パイプライン コンポーネント [ツールボックス] からドラッグ**SWIFT Frr MQSeries の送信コンポーネント**を**ここにドロップ**下のボックス、**エンコード**で図形をステージ**BizTalk パイプライン デザイナ**です。  
  
7.  BizTalk エクスプ ローラーで、パイプライン プロジェクトを右クリックし、をクリックして**Undeploy**、順にクリック**はい**です。  
  
    > [!NOTE]
    >  展開解除と、パイプライン プロジェクトを再、後に、送信ポートをリセットするか、以前に配置されたプロジェクトでパイプラインを使用する受信場所できます。  
  
8.  ソリューション エクスプ ローラーで、パイプライン プロジェクトを右クリックし、をクリックして**ビルド**です。  
  
9. ビルドが成功した後、パイプライン プロジェクトを右クリックし、をクリックして**展開**です。