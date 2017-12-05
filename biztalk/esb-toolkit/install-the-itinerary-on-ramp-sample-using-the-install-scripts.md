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
ms.openlocfilehash: 28bd132591730c63af219e3b8acfbcf52c882c87
ms.sourcegitcommit: 5abd0ed3f9e4858ffaaec5481bfa8878595e95f7
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 11/28/2017
---
# <a name="install-the-itinerary-on-ramp-sample-using-the-install-scripts"></a>インストール スクリプトを使用して、Itinerary ランプでサンプルをインストールします。
このセクションで提供するインストール スクリプトから行程入り口サンプルをインストールする方法について説明します、[!INCLUDE[esbToolkit](../includes/esbtoolkit-md.md)]です。  
  
### <a name="to-install-the-itinerary-on-ramp-sample-from-the-install-scripts"></a>インストール スクリプトから行程入り口サンプルをインストールするには  
  
1.  **[スタート]** メニューの **[ファイル名を指定して実行]**をクリックします。  
  
2.  **実行** ダイアログ ボックスで、「 **cmd**、し、enter キーを押してコマンド プロンプトを開きます。  
  
3.  次のコマンド実行交換、\<パス\>をインストールする .cmd ファイルへの完全パスを持つパラメーター (このリリースでは既定のパスは \Source\Samples\Itinerary\Install\Scripts\\)。  
  
    ```  
    <path>\Setup_bin.cmd  
    ```