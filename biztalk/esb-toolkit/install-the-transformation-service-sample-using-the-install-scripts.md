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
# <a name="install-the-transformation-service-sample-using-the-install-scripts"></a><span data-ttu-id="d72d3-102">インストール スクリプトを使用して変換サービスのサンプルをインストールします。</span><span class="sxs-lookup"><span data-stu-id="d72d3-102">Install the Transformation Service Sample Using the Install Scripts</span></span>
<span data-ttu-id="d72d3-103">このセクションで提供するインストール スクリプトから変換サービスのサンプルをインストールする方法について説明します、[!INCLUDE[esbToolkit](../includes/esbtoolkit-md.md)]です。</span><span class="sxs-lookup"><span data-stu-id="d72d3-103">This section describes how you can install the Transformation Service sample from the install scripts provided with the [!INCLUDE[esbToolkit](../includes/esbtoolkit-md.md)].</span></span>  
  
 <span data-ttu-id="d72d3-104">**インストール スクリプトからの変換サービスのサンプルをインストールするには**</span><span class="sxs-lookup"><span data-stu-id="d72d3-104">**To install the Transformation Service sample from the install scripts**</span></span>  
  
1.  <span data-ttu-id="d72d3-105">**[スタート]** メニューの **[ファイル名を指定して実行]**をクリックします。</span><span class="sxs-lookup"><span data-stu-id="d72d3-105">On the **Start** menu, click **Run**.</span></span>  
  
2.  <span data-ttu-id="d72d3-106">**実行** ダイアログ ボックスで、「 **cmd**、し、enter キーを押してコマンド プロンプトを開きます。</span><span class="sxs-lookup"><span data-stu-id="d72d3-106">In the **Run** dialog box, type **cmd**, and then press ENTER to open a command prompt.</span></span>  
  
3.  <span data-ttu-id="d72d3-107">次のコード実行コマンドを置き換えて、 *\<パス >*をインストールする .cmd ファイルへの完全パスを持つパラメーター (このリリースでは既定のパスは \Source\Samples\TransformServices\Install\Scripts\\):</span><span class="sxs-lookup"><span data-stu-id="d72d3-107">Execute the following command, replacing the *\<path>* parameter with the full path to the .cmd file you want to install (the default path in this release is \Source\Samples\TransformServices\Install\Scripts\\):</span></span>  
  
    ```  
    <path>\TransformServices_Install.cmd  
    ```