---
title: インストール スクリプトを使用して変換サービス サンプルのインストール |Microsoft Docs
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
ms.openlocfilehash: 4f82de09ec7d6236df66662c913c14111a90867d
ms.sourcegitcommit: 381e83d43796a345488d54b3f7413e11d56ad7be
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 05/07/2019
ms.locfileid: "65399881"
---
# <a name="install-the-transformation-service-sample-using-the-install-scripts"></a><span data-ttu-id="c5669-102">インストール スクリプトを使用して変換サービス サンプルをインストールします。</span><span class="sxs-lookup"><span data-stu-id="c5669-102">Install the Transformation Service Sample Using the Install Scripts</span></span>
<span data-ttu-id="c5669-103">このセクションで提供するインストール スクリプトから変換サービス サンプルをインストールする方法について説明します、[!INCLUDE[esbToolkit](../includes/esbtoolkit-md.md)]します。</span><span class="sxs-lookup"><span data-stu-id="c5669-103">This section describes how you can install the Transformation Service sample from the install scripts provided with the [!INCLUDE[esbToolkit](../includes/esbtoolkit-md.md)].</span></span>  
  
 <span data-ttu-id="c5669-104">**インストール スクリプトからの変換サービス サンプルをインストールするには**</span><span class="sxs-lookup"><span data-stu-id="c5669-104">**To install the Transformation Service sample from the install scripts**</span></span>  
  
1.  <span data-ttu-id="c5669-105">**[スタート]** メニューの **[ファイル名を指定して実行]** をクリックします。</span><span class="sxs-lookup"><span data-stu-id="c5669-105">On the **Start** menu, click **Run**.</span></span>  
  
2.  <span data-ttu-id="c5669-106">**実行**ダイアログ ボックスに「 **cmd**、し、enter キーを押してコマンド プロンプトを開きます。</span><span class="sxs-lookup"><span data-stu-id="c5669-106">In the **Run** dialog box, type **cmd**, and then press ENTER to open a command prompt.</span></span>  
  
3.  <span data-ttu-id="c5669-107">次の実行コマンドを置き換える、 *\<パス\>* をインストールする .cmd ファイルへの完全パスを持つパラメーター (このリリースでは既定のパスは \Source\Samples\TransformServices\Install\スクリプト\\)。</span><span class="sxs-lookup"><span data-stu-id="c5669-107">Execute the following command, replacing the *\<path\>* parameter with the full path to the .cmd file you want to install (the default path in this release is \Source\Samples\TransformServices\Install\Scripts\\):</span></span>  
  
    ```  
    <path>\TransformServices_Install.cmd  
    ```