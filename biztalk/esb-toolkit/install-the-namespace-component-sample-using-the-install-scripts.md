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
ms.openlocfilehash: 822f2b2f97374b5e5953f81025fb02027328f054
ms.sourcegitcommit: cb908c540d8f1a692d01dc8f313e16cb4b4e696d
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 09/20/2017
---
# <a name="install-the-namespace-component-sample-using-the-install-scripts"></a><span data-ttu-id="a017e-102">インストール スクリプトを使用して、Namespace コンポーネント サンプルをインストールします。</span><span class="sxs-lookup"><span data-stu-id="a017e-102">Install the Namespace Component Sample Using the Install Scripts</span></span>
<span data-ttu-id="a017e-103">このセクションで提供される Windows インストーラー ファイルから、Namespace コンポーネント サンプルをインストールする方法について説明します、[!INCLUDE[esbToolkit](../includes/esbtoolkit-md.md)]です。</span><span class="sxs-lookup"><span data-stu-id="a017e-103">This section describes how you can install the Namespace Component sample from the Windows Installer file provided with the [!INCLUDE[esbToolkit](../includes/esbtoolkit-md.md)].</span></span>  
  
 <span data-ttu-id="a017e-104">**インストール スクリプトから、Namespace コンポーネント サンプルをインストールするには**</span><span class="sxs-lookup"><span data-stu-id="a017e-104">**To install the Namespace Component sample from the install scripts**</span></span>  
  
1.  <span data-ttu-id="a017e-105">**[スタート]** メニューの **[ファイル名を指定して実行]**をクリックします。</span><span class="sxs-lookup"><span data-stu-id="a017e-105">On the **Start** menu, click **Run**.</span></span>  
  
2.  <span data-ttu-id="a017e-106">**実行** ダイアログ ボックスで、「 **cmd**、し、enter キーを押してコマンド プロンプトを開きます。</span><span class="sxs-lookup"><span data-stu-id="a017e-106">In the **Run** dialog box, type **cmd**, and then press ENTER to open a command prompt.</span></span>  
  
3.  <span data-ttu-id="a017e-107">次のコマンド実行交換、 *\<パス >*をインストールする .cmd ファイルへの完全パスを持つパラメーター (このリリースでは既定のパスは \Source\Samples\Namepace\Install\Scripts\\)。</span><span class="sxs-lookup"><span data-stu-id="a017e-107">Run the following command, replacing the *\<path>* parameter with the full path to the .cmd file you want to install (the default path in this release is \Source\Samples\Namepace\Install\Scripts\\):</span></span>  
  
    ```  
    <path>\Setup_bin.cmd  
    ```