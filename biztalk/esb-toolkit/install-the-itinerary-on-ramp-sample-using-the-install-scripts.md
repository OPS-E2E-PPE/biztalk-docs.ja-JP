---
title: インストール スクリプトを使用して、Itinerary ランプのサンプルがインストール |Microsoft Docs
ms.custom: ''
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: ''
ms.suite: ''
ms.tgt_pltfrm: ''
ms.topic: article
ms.assetid: 5f493148-5600-42db-981d-38b93a9b25e1
caps.latest.revision: 2
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: 57043fd3212c0f4f023f8b7936d2a010838cac5f
ms.sourcegitcommit: 381e83d43796a345488d54b3f7413e11d56ad7be
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 05/07/2019
ms.locfileid: "65399910"
---
# <a name="install-the-itinerary-on-ramp-sample-using-the-install-scripts"></a>インストール スクリプトを使用して、Itinerary ランプでサンプルをインストールします。
このセクションで提供するインストール スクリプトから、旅行プラン サンプルをインストールする方法について説明します、[!INCLUDE[esbToolkit](../includes/esbtoolkit-md.md)]します。  
  
### <a name="to-install-the-itinerary-on-ramp-sample-from-the-install-scripts"></a>インストール スクリプトから、旅行プラン サンプルをインストールするには  
  
1.  **[スタート]** メニューの **[ファイル名を指定して実行]** をクリックします。  
  
2.  **実行**ダイアログ ボックスに「 **cmd**、し、enter キーを押してコマンド プロンプトを開きます。  
  
3.  次のコマンドを実行して交換、\<パス\>をインストールする .cmd ファイルへの完全パスを持つパラメーター (このリリースでは既定のパスは \Source\Samples\Itinerary\Install\Scripts\\)。  
  
    ```  
    <path>\Setup_bin.cmd  
    ```