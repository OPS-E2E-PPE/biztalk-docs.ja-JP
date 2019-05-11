---
title: インストール スクリプトを使用して、Namespace コンポーネント サンプルのインストール |Microsoft Docs
ms.custom: ''
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: ''
ms.suite: ''
ms.tgt_pltfrm: ''
ms.topic: article
ms.assetid: 66046ef4-91a2-4fe7-93ad-3b8137294411
caps.latest.revision: 2
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: 37e8a802a9c811695bdaee66fbd623ef4b11ba41
ms.sourcegitcommit: 381e83d43796a345488d54b3f7413e11d56ad7be
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 05/07/2019
ms.locfileid: "65399895"
---
# <a name="install-the-namespace-component-sample-using-the-install-scripts"></a>インストール スクリプトを使用して、Namespace コンポーネント サンプルをインストールします。
このセクションで提供される Windows インストーラー ファイルから、Namespace コンポーネント サンプルをインストールする方法について説明します、[!INCLUDE[esbToolkit](../includes/esbtoolkit-md.md)]します。  
  
 **インストール スクリプトから、Namespace コンポーネント サンプルをインストールするには**  
  
1.  **[スタート]** メニューの **[ファイル名を指定して実行]** をクリックします。  
  
2.  **実行**ダイアログ ボックスに「 **cmd**、し、enter キーを押してコマンド プロンプトを開きます。  
  
3.  次のコマンドを実行して交換、 *\<パス\>* をインストールする .cmd ファイルへの完全パスを持つパラメーター (このリリースでは既定のパスは \Source\Samples\Namepace\Install\Scripts\\):  
  
    ```  
    <path>\Setup_bin.cmd  
    ```