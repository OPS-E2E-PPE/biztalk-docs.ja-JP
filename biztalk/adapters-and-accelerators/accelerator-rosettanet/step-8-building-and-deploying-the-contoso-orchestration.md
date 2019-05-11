---
title: 手順 8:Contoso オーケストレーションのビルドと |Microsoft Docs
ms.custom: ''
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: ''
ms.suite: ''
ms.tgt_pltfrm: ''
ms.topic: article
helpviewer_keywords:
- private process tutorial, building solutions
- private process tutorial, deploying solutions
ms.assetid: d350b87a-0e4e-4837-ad39-fb5b1fdc1532
caps.latest.revision: 3
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: 68708976c91d96b3729b1a39776981d9345eb519
ms.sourcegitcommit: 381e83d43796a345488d54b3f7413e11d56ad7be
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 05/07/2019
ms.locfileid: "65280650"
---
# <a name="step-8-building-and-deploying-the-contoso-orchestration"></a>手順 8:ビルドと Contoso オーケストレーションの展開
この手順では、オーケストレーション プロジェクトをビルドし、BizTalk 展開ウィザードを使用して展開します。 これは構成データベースにアセンブリを追加し、アセンブリをグローバル アセンブリ キャッシュ (GAC) にインストールします。  
  
### <a name="to-assign-a-strong-name-to-your-assembly"></a>アセンブリに厳密な名前を割り当てる  
  
1.  ソリューション エクスプ ローラーで右クリックし、 **PrivateResponder**プロジェクトをクリックして**プロパティ**します。  
  
2.  PrivateResponder プロパティ ページ] ダイアログ ボックスで、[**アセンブリ**左側のウィンドウ。  
  
3.  右側のペインでスクロールして、**厳密な名前**セクションで、フィールドの右側をクリックして、**アセンブリ キー ファイル**、省略記号ボタンをクリックし、(**.**).  
  
4.  プロジェクト フォルダーを見つけ、選択、 **FabConPriceAvail.snk**ファイルを開き、をクリックし、**オープン**します。  
  
5.  右側のウィンドウで次のように選択します。 **False**から、**アセンブリの遅延署名**ドロップダウン リスト。  
  
6.  **[OK]** をクリックして変更を保存します。  
  
### <a name="to-build-and-deploy-the-orchestration-project"></a>構築して、オーケストレーション プロジェクトをデプロイするには  
  
1.  ソリューション エクスプ ローラーで右クリックし、 **PrivateResponder**プロジェクトをクリックして**ビルド**します。  
  
    > [!NOTE]
    >  ビルド処理中に発生した警告を無視してかまいません。  
  
2.  ビルドが完了すると、もう一度、プロジェクトを右クリックし、クリックして**デプロイ**します。  
  
## <a name="see-also"></a>参照  
 [手順 9:Contoso オーケストレーションの開始](../../adapters-and-accelerators/accelerator-rosettanet/step-9-starting-the-contoso-orchestration.md)