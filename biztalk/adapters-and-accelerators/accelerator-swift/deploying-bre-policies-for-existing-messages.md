---
title: 既存のメッセージの BRE ポリシーの展開 |Microsoft Docs
ms.custom: ''
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: ''
ms.suite: ''
ms.tgt_pltfrm: ''
ms.topic: article
ms.assetid: 585c903d-ee44-4e92-8798-febb176367e3
caps.latest.revision: 2
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: bbe4f95526883f0bc8e79ff0b0c0241aa198747f
ms.sourcegitcommit: 381e83d43796a345488d54b3f7413e11d56ad7be
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 05/07/2019
ms.locfileid: "65377964"
---
# <a name="deploying-bre-policies-for-existing-messages"></a>既存のメッセージの BRE ポリシーの展開
**関連するビジネス ルールを展開するには。**  
  
1.  クリックして**開始**、 をクリックして**プログラム**、 をクリックして**Microsoft BizTalk Accelerator for SWIFT**、順にクリックします**BRE 配置ユーティリティ**します。  
  
2.  BRE 配置ユーティリティでクリックして**参照**します。  
  
3.  .NET グローバル アセンブリ キャッシュ] ダイアログ ボックスで、[ **SWIFT MX スキーマ**、順にクリックします**OK**します。  
  
4.  クリックして**デプロイ**します。  
  
     そのアセンブリに展開されているスキーマに基づき、配置ユーティリティは、関連するルールを識別し、BRE を使用して発行します。 完了したら、BRE 配置ユーティリティが表示されます、次のメッセージ。"デプロイが完了しました。 ログ ファイルまたはビジネス ルール作成ツールの表示の詳細。"  
  
5.  SWIFT BRE 配置ユーティリティ ダイアログ ボックスを閉じます。  
  
6.  Windows エクスプ ローラーを参照 *\<ドライブ\>* : \Documents and 別のバックアップ データをフォルダーに表示される BREDeploymentLog.txt をログ ファイルことを確認します。  
  
7.  をクリックして**開始**、 をクリックして**実行**、型**services.msc**、順にクリックします**OK**。 サービス (ローカル) ウィンドウで、右クリックして**ルール エンジン更新サービス**、 をクリックし、**再起動**します。