---
title: インストール スクリプトを使用して動的解決サンプルのインストール |Microsoft Docs
ms.custom: ''
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: ''
ms.suite: ''
ms.tgt_pltfrm: ''
ms.topic: article
ms.assetid: 644b6403-9883-4256-80d5-37881a87ed0e
caps.latest.revision: 2
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: 7a2ecbfcf38046a9ad9f4ca2fa7c360f2f5b50a1
ms.sourcegitcommit: 381e83d43796a345488d54b3f7413e11d56ad7be
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 05/07/2019
ms.locfileid: "65400321"
---
# <a name="install-the-dynamic-resolution-sample-using-the-install-scripts"></a>インストール スクリプトを使用して動的解決サンプルをインストールします。
このセクションで提供するインストール スクリプトから動的解決サンプルをインストールする方法について説明します、[!INCLUDE[esbToolkit](../includes/esbtoolkit-md.md)]します。  
  
 **インストール スクリプトから動的解決サンプルをインストールするには**  
  
1.  FTP を使用する一方向のメッセージングの例を実行する場合は、次の FTP サイトを作成します。  
  
    -   FTP 仮想ディレクトリ名:アウト  
  
    -   Location: \Source\Samples\DynamicResolution\Test\FTP\Out  
  
    -   権限:読み取りと書き込み  
  
    -   BizTalk Application Users グループがこの場所の完全なアクセス許可を確認します。  
  
2.  MQSeries を使用する双方向のメッセージングの例を実行する場合は、WebSphere エクスプ ローラーを使用して、以下を作成します。  
  
    -   ESB という名前のキュー マネージャー。DEP.Sample.QueueManager  
  
    -   テストをという名前のキュー。ESB 内でチェック アウトします。DEP.Sample.QueueManager  
  
3.  **[スタート]** メニューの **[ファイル名を指定して実行]** をクリックします。  
  
4.  **実行**ダイアログ ボックスに「 **cmd**、し、enter キーを押してコマンド プロンプトを開きます。  
  
5.  次のコマンドを実行して交換、\<パス\>をインストールする .cmd ファイルへの完全パスを持つパラメーター (このリリースでは既定のパスは \Source\Samples\DynamicResolution\Install\Scripts\\)。  
  
    ```  
    <path>\Setup_bin.cmd  
    ```