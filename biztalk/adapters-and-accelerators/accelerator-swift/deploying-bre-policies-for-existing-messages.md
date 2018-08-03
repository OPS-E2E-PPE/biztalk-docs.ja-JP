---
title: 既存のメッセージの BRE ポリシーを展開する |Microsoft ドキュメント
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
ms.openlocfilehash: 4cd094feabe1ba23a6a73c89aae3a1042b8f7fc9
ms.sourcegitcommit: 5abd0ed3f9e4858ffaaec5481bfa8878595e95f7
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 11/28/2017
ms.locfileid: "25965008"
---
# <a name="deploying-bre-policies-for-existing-messages"></a>既存のメッセージの BRE ポリシーを展開します。
**関連するビジネス ルールを展開するには。**  
  
1.  をクリックして**開始**、 をクリックして**プログラム**、 をクリックして**Microsoft BizTalk Accelerator 用 SWIFT**、順にクリック**BRE 配置ユーティリティ**です。  
  
2.  BRE 配置ユーティリティでクリックして**参照**です。  
  
3.  .NET グローバル アセンブリ キャッシュ] ダイアログ ボックスで、[ **SWIFT MX スキーマ**、順にクリック**OK**です。  
  
4.  をクリックして**展開**です。  
  
     そのアセンブリに展開されているスキーマに基づくと、配置ユーティリティ関連するルールを識別それらを発行して、BRE を使用します。 完了したら、BRE 配置ユーティリティが表示されます、次のメッセージ:"配置が完了しました。 ログ ファイルまたはビジネス ルール作成ツールの表示の詳細。"  
  
5.  SWIFT BRE 配置ユーティリティ ダイアログ ボックスを閉じます。  
  
6.  Windows エクスプ ローラーで参照*\<ドライブ\>*: \Documents and settings \all \all データをログ ファイル BREDeploymentLog.txt に表示されるフォルダーを確認します。  
  
7.  をクリックして**開始**、 をクリックして**実行**、型**services.msc**、順にクリック**ok**です。 サービス (ローカル) ウィンドウで右クリック**ルール エンジン更新サービス**、クリックして**再起動**です。