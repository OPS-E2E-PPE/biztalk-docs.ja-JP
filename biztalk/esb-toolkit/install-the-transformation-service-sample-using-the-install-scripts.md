---
title: インストール スクリプトを使用して変換サービスのサンプルのインストール |Microsoft ドキュメント
ms.custom: ''
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: ''
ms.suite: ''
ms.tgt_pltfrm: ''
ms.topic: article
ms.assetid: e5993103-0bcf-46ff-9178-05e2924da7b7
caps.latest.revision: 2
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: 8c7d567744857d5df5e9a65b01baa46da897260d
ms.sourcegitcommit: 5abd0ed3f9e4858ffaaec5481bfa8878595e95f7
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 11/28/2017
ms.locfileid: "25974336"
---
# <a name="install-the-transformation-service-sample-using-the-install-scripts"></a>インストール スクリプトを使用して変換サービスのサンプルをインストールします。
このセクションで提供するインストール スクリプトから変換サービスのサンプルをインストールする方法について説明します、[!INCLUDE[esbToolkit](../includes/esbtoolkit-md.md)]です。  
  
 **インストール スクリプトからの変換サービスのサンプルをインストールするには**  
  
1.  **[スタート]** メニューの **[ファイル名を指定して実行]** をクリックします。  
  
2.  **実行** ダイアログ ボックスで、「 **cmd**、し、enter キーを押してコマンド プロンプトを開きます。  
  
3.  次のコード実行コマンドを置き換えて、 *\<パス\>* をインストールする .cmd ファイルへの完全パスを持つパラメーター (このリリースでは既定のパスは \Source\Samples\TransformServices\Install\スクリプト\\)。  
  
    ```  
    <path>\TransformServices_Install.cmd  
    ```