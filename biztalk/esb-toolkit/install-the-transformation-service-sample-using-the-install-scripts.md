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
# <a name="install-the-transformation-service-sample-using-the-install-scripts"></a><span data-ttu-id="4c18c-102">インストール スクリプトを使用して変換サービスのサンプルをインストールします。</span><span class="sxs-lookup"><span data-stu-id="4c18c-102">Install the Transformation Service Sample Using the Install Scripts</span></span>
<span data-ttu-id="4c18c-103">このセクションで提供するインストール スクリプトから変換サービスのサンプルをインストールする方法について説明します、[!INCLUDE[esbToolkit](../includes/esbtoolkit-md.md)]です。</span><span class="sxs-lookup"><span data-stu-id="4c18c-103">This section describes how you can install the Transformation Service sample from the install scripts provided with the [!INCLUDE[esbToolkit](../includes/esbtoolkit-md.md)].</span></span>  
  
 <span data-ttu-id="4c18c-104">**インストール スクリプトからの変換サービスのサンプルをインストールするには**</span><span class="sxs-lookup"><span data-stu-id="4c18c-104">**To install the Transformation Service sample from the install scripts**</span></span>  
  
1.  <span data-ttu-id="4c18c-105">**[スタート]** メニューの **[ファイル名を指定して実行]** をクリックします。</span><span class="sxs-lookup"><span data-stu-id="4c18c-105">On the **Start** menu, click **Run**.</span></span>  
  
2.  <span data-ttu-id="4c18c-106">**実行** ダイアログ ボックスで、「 **cmd**、し、enter キーを押してコマンド プロンプトを開きます。</span><span class="sxs-lookup"><span data-stu-id="4c18c-106">In the **Run** dialog box, type **cmd**, and then press ENTER to open a command prompt.</span></span>  
  
3.  <span data-ttu-id="4c18c-107">次のコード実行コマンドを置き換えて、 *\<パス\>* をインストールする .cmd ファイルへの完全パスを持つパラメーター (このリリースでは既定のパスは \Source\Samples\TransformServices\Install\スクリプト\\)。</span><span class="sxs-lookup"><span data-stu-id="4c18c-107">Execute the following command, replacing the *\<path\>* parameter with the full path to the .cmd file you want to install (the default path in this release is \Source\Samples\TransformServices\Install\Scripts\\):</span></span>  
  
    ```  
    <path>\TransformServices_Install.cmd  
    ```