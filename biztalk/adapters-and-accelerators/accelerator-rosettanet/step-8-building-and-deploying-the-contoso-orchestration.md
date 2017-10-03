---
title: "手順 8: ビルドと Contoso オーケストレーションの展開 |Microsoft ドキュメント"
ms.custom: 
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: 
ms.suite: 
ms.tgt_pltfrm: 
ms.topic: article
helpviewer_keywords:
- private process tutorial, building solutions
- private process tutorial, deploying solutions
ms.assetid: d350b87a-0e4e-4837-ad39-fb5b1fdc1532
caps.latest.revision: "3"
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: 706c5ab2b52d30aeedfba7b3e002dc637fcece93
ms.sourcegitcommit: cb908c540d8f1a692d01dc8f313e16cb4b4e696d
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 09/20/2017
---
# <a name="step-8-building-and-deploying-the-contoso-orchestration"></a>手順 8: ビルドと Contoso オーケストレーションの展開
ここでは、オーケストレーション プロジェクトをビルドし、BizTalk 展開ウィザードを使用して展開します。 これにより、アセンブリが構成データベースに追加され、グローバル アセンブリ キャッシュ (GAC) にインストールされます。  
  
### <a name="to-assign-a-strong-name-to-your-assembly"></a>アセンブリに厳密な名前を割り当てるには  
  
1.  ソリューション エクスプ ローラーで右クリックし、 **PrivateResponder**プロジェクトをクリックして**プロパティ**です。  
  
2.  PrivateResponder プロパティ ページ] ダイアログ ボックスで、[**アセンブリ**左側のペインからです。  
  
3.  右側のペインでスクロールして、**厳密な名前**セクションで、フィールドの右側をクリックして、**アセンブリ キー ファイル**、省略記号ボタンをクリックして (**.**).  
  
4.  プロジェクト フォルダで、選択、 **FabConPriceAvail.snk**ファイルを開き、をクリックして**開く**です。  
  
5.  右側のペインで選択**False**から、**アセンブリの遅延署名**ドロップ ダウン リスト。  
  
6.  をクリックして**OK**変更を保存します。  
  
### <a name="to-build-and-deploy-the-orchestration-project"></a>オーケストレーション プロジェクトを構築および展開するには  
  
1.  ソリューション エクスプ ローラーで右クリックし、 **PrivateResponder**プロジェクトをクリックして**ビルド**です。  
  
    > [!NOTE]
    >  ビルド プロセス中に発生した警告は、すべて無視しても問題ありません。  
  
2.  ビルドが完了すると、もう一度、プロジェクトを右クリックし、クリックして**展開**です。  
  
## <a name="see-also"></a>参照  
 [手順 9: Contoso オーケストレーションの開始](../../adapters-and-accelerators/accelerator-rosettanet/step-9-starting-the-contoso-orchestration.md)