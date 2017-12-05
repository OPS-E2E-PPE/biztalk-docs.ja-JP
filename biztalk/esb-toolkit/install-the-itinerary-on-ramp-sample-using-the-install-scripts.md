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
# <a name="install-the-itinerary-on-ramp-sample-using-the-install-scripts"></a><span data-ttu-id="fcbbe-102">インストール スクリプトを使用して、Itinerary ランプでサンプルをインストールします。</span><span class="sxs-lookup"><span data-stu-id="fcbbe-102">Install the Itinerary On-Ramp Sample Using the Install Scripts</span></span>
<span data-ttu-id="fcbbe-103">このセクションで提供するインストール スクリプトから行程入り口サンプルをインストールする方法について説明します、[!INCLUDE[esbToolkit](../includes/esbtoolkit-md.md)]です。</span><span class="sxs-lookup"><span data-stu-id="fcbbe-103">This section describes how you can install the Itinerary On-Ramp sample from the install scripts provided with the [!INCLUDE[esbToolkit](../includes/esbtoolkit-md.md)].</span></span>  
  
### <a name="to-install-the-itinerary-on-ramp-sample-from-the-install-scripts"></a><span data-ttu-id="fcbbe-104">インストール スクリプトから行程入り口サンプルをインストールするには</span><span class="sxs-lookup"><span data-stu-id="fcbbe-104">To install the Itinerary On-Ramp sample from the install scripts</span></span>  
  
1.  <span data-ttu-id="fcbbe-105">**[スタート]** メニューの **[ファイル名を指定して実行]**をクリックします。</span><span class="sxs-lookup"><span data-stu-id="fcbbe-105">On the **Start** menu, click **Run**.</span></span>  
  
2.  <span data-ttu-id="fcbbe-106">**実行** ダイアログ ボックスで、「 **cmd**、し、enter キーを押してコマンド プロンプトを開きます。</span><span class="sxs-lookup"><span data-stu-id="fcbbe-106">In the **Run** dialog box, type **cmd**, and then press ENTER to open a command prompt.</span></span>  
  
3.  <span data-ttu-id="fcbbe-107">次のコマンド実行交換、\<パス\>をインストールする .cmd ファイルへの完全パスを持つパラメーター (このリリースでは既定のパスは \Source\Samples\Itinerary\Install\Scripts\\)。</span><span class="sxs-lookup"><span data-stu-id="fcbbe-107">Run the following command, replacing the \<path\> parameter with the full path to the .cmd file you want to install (the default path in this release is \Source\Samples\Itinerary\Install\Scripts\\):</span></span>  
  
    ```  
    <path>\Setup_bin.cmd  
    ```