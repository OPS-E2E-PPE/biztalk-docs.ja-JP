---
title: 使用してスクリプトのサンプル例外管理をインストールする |Microsoft ドキュメント
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
ms.openlocfilehash: 03af6a8317aa9b2dd3d26bf0204553401fc8978e
ms.sourcegitcommit: 5abd0ed3f9e4858ffaaec5481bfa8878595e95f7
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 11/28/2017
ms.locfileid: "25976312"
---
# <a name="installing-the-exception-management-samples-using-install-scripts"></a><span data-ttu-id="4b404-102">インストール スクリプトを使用して例外管理のサンプルをインストールします。</span><span class="sxs-lookup"><span data-stu-id="4b404-102">Installing the Exception Management Samples Using Install Scripts</span></span>
<span data-ttu-id="4b404-103">このセクションで提供するインストール スクリプトから例外管理のサンプルをインストールする方法について説明します、[!INCLUDE[esbToolkit](../includes/esbtoolkit-md.md)]です。</span><span class="sxs-lookup"><span data-stu-id="4b404-103">This section describes how you can install the Exception Management samples from the install scripts provided with the [!INCLUDE[esbToolkit](../includes/esbtoolkit-md.md)].</span></span>  
  
 <span data-ttu-id="4b404-104">**インストール スクリプトから ESB 例外管理のサンプルをインストールするには**</span><span class="sxs-lookup"><span data-stu-id="4b404-104">**To install the ESB Exception Management samples from the install scripts**</span></span>  
  
1.  <span data-ttu-id="4b404-105">**[スタート]** メニューの **[ファイル名を指定して実行]** をクリックします。</span><span class="sxs-lookup"><span data-stu-id="4b404-105">On the **Start** menu, click **Run**.</span></span>  
  
2.  <span data-ttu-id="4b404-106">**実行** ダイアログ ボックスで、「 **cmd**、し、enter キーを押してコマンド プロンプトを開きます。</span><span class="sxs-lookup"><span data-stu-id="4b404-106">In the **Run** dialog box, type **cmd**, and then press ENTER to open a command prompt.</span></span>  
  
3.  <span data-ttu-id="4b404-107">次のコマンド実行交換、 *\<パス\>* をインストールする .cmd ファイルへの完全パスを持つパラメーター (このリリースでは名前と既定のパスは \Source\Samples\Exception Handling\Install\Scripts\\)。</span><span class="sxs-lookup"><span data-stu-id="4b404-107">Run the following command, replacing the *\<path\>* parameter with the full path to the .cmd file you want to install (the default path and name in this release is \Source\Samples\Exception Handling\Install\Scripts\\):</span></span>  
  
    ```  
    <path>\Setup_bin.cmd  
    ```