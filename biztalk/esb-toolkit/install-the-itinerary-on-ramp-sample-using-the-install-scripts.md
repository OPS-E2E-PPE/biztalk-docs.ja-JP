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
# <a name="install-the-itinerary-on-ramp-sample-using-the-install-scripts"></a><span data-ttu-id="d5453-102">インストール スクリプトを使用して、Itinerary ランプでサンプルをインストールします。</span><span class="sxs-lookup"><span data-stu-id="d5453-102">Install the Itinerary On-Ramp Sample Using the Install Scripts</span></span>
<span data-ttu-id="d5453-103">このセクションで提供するインストール スクリプトから、旅行プラン サンプルをインストールする方法について説明します、[!INCLUDE[esbToolkit](../includes/esbtoolkit-md.md)]します。</span><span class="sxs-lookup"><span data-stu-id="d5453-103">This section describes how you can install the Itinerary On-Ramp sample from the install scripts provided with the [!INCLUDE[esbToolkit](../includes/esbtoolkit-md.md)].</span></span>  
  
### <a name="to-install-the-itinerary-on-ramp-sample-from-the-install-scripts"></a><span data-ttu-id="d5453-104">インストール スクリプトから、旅行プラン サンプルをインストールするには</span><span class="sxs-lookup"><span data-stu-id="d5453-104">To install the Itinerary On-Ramp sample from the install scripts</span></span>  
  
1.  <span data-ttu-id="d5453-105">**[スタート]** メニューの **[ファイル名を指定して実行]** をクリックします。</span><span class="sxs-lookup"><span data-stu-id="d5453-105">On the **Start** menu, click **Run**.</span></span>  
  
2.  <span data-ttu-id="d5453-106">**実行**ダイアログ ボックスに「 **cmd**、し、enter キーを押してコマンド プロンプトを開きます。</span><span class="sxs-lookup"><span data-stu-id="d5453-106">In the **Run** dialog box, type **cmd**, and then press ENTER to open a command prompt.</span></span>  
  
3.  <span data-ttu-id="d5453-107">次のコマンドを実行して交換、\<パス\>をインストールする .cmd ファイルへの完全パスを持つパラメーター (このリリースでは既定のパスは \Source\Samples\Itinerary\Install\Scripts\\)。</span><span class="sxs-lookup"><span data-stu-id="d5453-107">Run the following command, replacing the \<path\> parameter with the full path to the .cmd file you want to install (the default path in this release is \Source\Samples\Itinerary\Install\Scripts\\):</span></span>  
  
    ```  
    <path>\Setup_bin.cmd  
    ```