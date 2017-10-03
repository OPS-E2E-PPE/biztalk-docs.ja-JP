---
title: "インストール スクリプトを使用して変換サービスのサンプルのインストール |Microsoft ドキュメント"
ms.custom: 
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: 
ms.suite: 
ms.tgt_pltfrm: 
ms.topic: article
ms.assetid: e5993103-0bcf-46ff-9178-05e2924da7b7
caps.latest.revision: "2"
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: 56a22ccaffd48be138a08e975864e5ec702cd18a
ms.sourcegitcommit: cb908c540d8f1a692d01dc8f313e16cb4b4e696d
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 09/20/2017
---
# <a name="install-the-transformation-service-sample-using-the-install-scripts"></a>インストール スクリプトを使用して変換サービスのサンプルをインストールします。
このセクションで提供するインストール スクリプトから変換サービスのサンプルをインストールする方法について説明します、[!INCLUDE[esbToolkit](../includes/esbtoolkit-md.md)]です。  
  
 **インストール スクリプトからの変換サービスのサンプルをインストールするには**  
  
1.  **[スタート]** メニューの **[ファイル名を指定して実行]**をクリックします。  
  
2.  **実行** ダイアログ ボックスで、「 **cmd**、し、enter キーを押してコマンド プロンプトを開きます。  
  
3.  次のコード実行コマンドを置き換えて、 *\<パス >*をインストールする .cmd ファイルへの完全パスを持つパラメーター (このリリースでは既定のパスは \Source\Samples\TransformServices\Install\Scripts\\):  
  
    ```  
    <path>\TransformServices_Install.cmd  
    ```