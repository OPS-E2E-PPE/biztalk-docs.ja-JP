---
title: "インストール スクリプトを使用して動的解決のサンプルをインストール |Microsoft ドキュメント"
ms.custom: 
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: 
ms.suite: 
ms.tgt_pltfrm: 
ms.topic: article
ms.assetid: 644b6403-9883-4256-80d5-37881a87ed0e
caps.latest.revision: "2"
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: 872bb73b9060e25986876c1c2da71afae84b5c52
ms.sourcegitcommit: 5abd0ed3f9e4858ffaaec5481bfa8878595e95f7
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 11/28/2017
---
# <a name="install-the-dynamic-resolution-sample-using-the-install-scripts"></a>インストール スクリプトを使用して動的解決のサンプルをインストールします。
このセクションで提供するインストール スクリプトから動的解決のサンプルをインストールする方法について説明します、[!INCLUDE[esbToolkit](../includes/esbtoolkit-md.md)]です。  
  
 **インストール スクリプトから動的解決サンプルをインストールするには**  
  
1.  FTP を使用する一方向のメッセージングの例を実行する場合は、次の FTP サイトを作成します。  
  
    -   FTP 仮想ディレクトリ名: アウト  
  
    -   場所: \Source\Samples\DynamicResolution\Test\FTP\Out  
  
    -   アクセス許可: 読み取りし、書き込み  
  
    -   BizTalk Application Users グループがこの場所に対するフル アクセスのアクセス許可を確認してください。  
  
2.  MQSeries を使用する双方向のメッセージングの例を実行する場合は、WebSphere エクスプ ローラーを使用して、以下を作成します。  
  
    -   ESB 名前のキュー マネージャー。 DEPSample.QueueManager  
  
    -   テストをという名前のキューです。ESB 内で出力します。 DEPSample.QueueManager  
  
3.  **[スタート]** メニューの **[ファイル名を指定して実行]**をクリックします。  
  
4.  **実行** ダイアログ ボックスで、「 **cmd**、し、enter キーを押してコマンド プロンプトを開きます。  
  
5.  次のコマンド実行交換、\<パス\>をインストールする .cmd ファイルへの完全パスを持つパラメーター (このリリースでは既定のパスは \Source\Samples\DynamicResolution\Install\Scripts\\)。  
  
    ```  
    <path>\Setup_bin.cmd  
    ```