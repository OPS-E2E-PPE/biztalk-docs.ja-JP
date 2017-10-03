---
title: "インストール スクリプトを使用して、Itinerary ランプでサンプルをインストール |Microsoft ドキュメント"
ms.custom: 
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: 
ms.suite: 
ms.tgt_pltfrm: 
ms.topic: article
ms.assetid: 5f493148-5600-42db-981d-38b93a9b25e1
caps.latest.revision: "2"
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: b1912bd6c9ec0b32c8b6b230d15299777ff42735
ms.sourcegitcommit: cb908c540d8f1a692d01dc8f313e16cb4b4e696d
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 09/20/2017
---
# <a name="install-the-itinerary-on-ramp-sample-using-the-install-scripts"></a>インストール スクリプトを使用して、Itinerary ランプでサンプルをインストールします。
このセクションで提供するインストール スクリプトから行程入り口サンプルをインストールする方法について説明します、[!INCLUDE[esbToolkit](../includes/esbtoolkit-md.md)]です。  
  
### <a name="to-install-the-itinerary-on-ramp-sample-from-the-install-scripts"></a>インストール スクリプトから行程入り口サンプルをインストールするには  
  
1.  **[スタート]** メニューの **[ファイル名を指定して実行]**をクリックします。  
  
2.  **実行** ダイアログ ボックスで、「 **cmd**、し、enter キーを押してコマンド プロンプトを開きます。  
  
3.  次のコマンド実行交換、\<パス > をインストールする .cmd ファイルへの完全パスを持つパラメーター (このリリースでは既定のパスは \Source\Samples\Itinerary\Install\Scripts\\)。  
  
    ```  
    <path>\Setup_bin.cmd  
    ```