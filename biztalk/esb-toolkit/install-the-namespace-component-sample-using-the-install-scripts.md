---
title: "インストール スクリプトを使用して、Namespace コンポーネント サンプルのインストール |Microsoft ドキュメント"
ms.custom: 
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: 
ms.suite: 
ms.tgt_pltfrm: 
ms.topic: article
ms.assetid: 66046ef4-91a2-4fe7-93ad-3b8137294411
caps.latest.revision: "2"
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: d3e3fc23d938fb9fc209124f7c9beff001d66771
ms.sourcegitcommit: 5abd0ed3f9e4858ffaaec5481bfa8878595e95f7
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 11/28/2017
---
# <a name="install-the-namespace-component-sample-using-the-install-scripts"></a>インストール スクリプトを使用して、Namespace コンポーネント サンプルをインストールします。
このセクションで提供される Windows インストーラー ファイルから、Namespace コンポーネント サンプルをインストールする方法について説明します、[!INCLUDE[esbToolkit](../includes/esbtoolkit-md.md)]です。  
  
 **インストール スクリプトから、Namespace コンポーネント サンプルをインストールするには**  
  
1.  **[スタート]** メニューの **[ファイル名を指定して実行]**をクリックします。  
  
2.  **実行** ダイアログ ボックスで、「 **cmd**、し、enter キーを押してコマンド プロンプトを開きます。  
  
3.  次のコマンド実行置き換えて、 *\<パス\>*をインストールする .cmd ファイルへの完全パスを持つパラメーター (このリリースでは既定のパスは \Source\Samples\Namepace\Install\Scripts\\):  
  
    ```  
    <path>\Setup_bin.cmd  
    ```