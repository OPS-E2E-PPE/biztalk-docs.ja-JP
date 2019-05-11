---
title: 例外管理をインストールするサンプルのインストール スクリプトの使用 |Microsoft Docs
ms.custom: ''
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: ''
ms.suite: ''
ms.tgt_pltfrm: ''
ms.topic: article
ms.assetid: 8ba65a4b-5fe1-4e17-b979-c3d380b526d6
caps.latest.revision: 3
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: 0ba9086e1a354a6ffc547076cd61e206182fc388
ms.sourcegitcommit: 381e83d43796a345488d54b3f7413e11d56ad7be
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 05/07/2019
ms.locfileid: "65279051"
---
# <a name="installing-the-exception-management-samples-using-install-scripts"></a><span data-ttu-id="8b7be-102">インストール スクリプトを使用して、例外管理サンプルをインストールします。</span><span class="sxs-lookup"><span data-stu-id="8b7be-102">Installing the Exception Management Samples Using Install Scripts</span></span>
<span data-ttu-id="8b7be-103">このセクションで提供するインストール スクリプトから、例外管理サンプルをインストールする方法について説明します、[!INCLUDE[esbToolkit](../includes/esbtoolkit-md.md)]します。</span><span class="sxs-lookup"><span data-stu-id="8b7be-103">This section describes how you can install the Exception Management samples from the install scripts provided with the [!INCLUDE[esbToolkit](../includes/esbtoolkit-md.md)].</span></span>  
  
 <span data-ttu-id="8b7be-104">**インストール スクリプトから ESB 例外管理サンプルをインストールするには**</span><span class="sxs-lookup"><span data-stu-id="8b7be-104">**To install the ESB Exception Management samples from the install scripts**</span></span>  
  
1.  <span data-ttu-id="8b7be-105">**[スタート]** メニューの **[ファイル名を指定して実行]** をクリックします。</span><span class="sxs-lookup"><span data-stu-id="8b7be-105">On the **Start** menu, click **Run**.</span></span>  
  
2.  <span data-ttu-id="8b7be-106">**実行**ダイアログ ボックスに「 **cmd**、し、enter キーを押してコマンド プロンプトを開きます。</span><span class="sxs-lookup"><span data-stu-id="8b7be-106">In the **Run** dialog box, type **cmd**, and then press ENTER to open a command prompt.</span></span>  
  
3.  <span data-ttu-id="8b7be-107">次のコマンドを実行して交換、 *\<パス\>* をインストールする .cmd ファイルへの完全パスを持つパラメーター (このリリースでの名前と既定のパスは \Source\Samples\Exception Handling\Install\Scripts\\)。</span><span class="sxs-lookup"><span data-stu-id="8b7be-107">Run the following command, replacing the *\<path\>* parameter with the full path to the .cmd file you want to install (the default path and name in this release is \Source\Samples\Exception Handling\Install\Scripts\\):</span></span>  
  
    ```  
    <path>\Setup_bin.cmd  
    ```