---
title: 例外管理をインストールするサンプルのインストール スクリプトの使用 |Microsoft Docs
ms.custom: ''
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: ''
ms.suite: ''
ms.tgt_pltfrm: ''
ms.topic: article
ms.assetid: 8ba65a4b-5fe1-4e17-b979-c3d380b526d6
caps.latest.revision: 3
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: 0ba9086e1a354a6ffc547076cd61e206182fc388
ms.sourcegitcommit: 381e83d43796a345488d54b3f7413e11d56ad7be
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 05/07/2019
ms.locfileid: "65279051"
---
# <a name="installing-the-exception-management-samples-using-install-scripts"></a>インストール スクリプトを使用して、例外管理サンプルをインストールします。
このセクションで提供するインストール スクリプトから、例外管理サンプルをインストールする方法について説明します、[!INCLUDE[esbToolkit](../includes/esbtoolkit-md.md)]します。  
  
 **インストール スクリプトから ESB 例外管理サンプルをインストールするには**  
  
1.  **[スタート]** メニューの **[ファイル名を指定して実行]** をクリックします。  
  
2.  **実行**ダイアログ ボックスに「 **cmd**、し、enter キーを押してコマンド プロンプトを開きます。  
  
3.  次のコマンドを実行して交換、 *\<パス\>* をインストールする .cmd ファイルへの完全パスを持つパラメーター (このリリースでの名前と既定のパスは \Source\Samples\Exception Handling\Install\Scripts\\)。  
  
    ```  
    <path>\Setup_bin.cmd  
    ```