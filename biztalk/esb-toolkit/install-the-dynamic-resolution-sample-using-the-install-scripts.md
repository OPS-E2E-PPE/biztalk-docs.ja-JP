---
title: インストール スクリプトを使用して動的解決サンプルのインストール |Microsoft Docs
ms.custom: ''
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: ''
ms.suite: ''
ms.tgt_pltfrm: ''
ms.topic: article
ms.assetid: 644b6403-9883-4256-80d5-37881a87ed0e
caps.latest.revision: 2
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: 7a2ecbfcf38046a9ad9f4ca2fa7c360f2f5b50a1
ms.sourcegitcommit: 381e83d43796a345488d54b3f7413e11d56ad7be
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 05/07/2019
ms.locfileid: "65400321"
---
# <a name="install-the-dynamic-resolution-sample-using-the-install-scripts"></a><span data-ttu-id="800af-102">インストール スクリプトを使用して動的解決サンプルをインストールします。</span><span class="sxs-lookup"><span data-stu-id="800af-102">Install the Dynamic Resolution Sample Using the Install Scripts</span></span>
<span data-ttu-id="800af-103">このセクションで提供するインストール スクリプトから動的解決サンプルをインストールする方法について説明します、[!INCLUDE[esbToolkit](../includes/esbtoolkit-md.md)]します。</span><span class="sxs-lookup"><span data-stu-id="800af-103">This section describes how you can install the Dynamic Resolution sample from the install scripts provided with the [!INCLUDE[esbToolkit](../includes/esbtoolkit-md.md)].</span></span>  
  
 <span data-ttu-id="800af-104">**インストール スクリプトから動的解決サンプルをインストールするには**</span><span class="sxs-lookup"><span data-stu-id="800af-104">**To install the Dynamic Resolution sample from the install scripts**</span></span>  
  
1.  <span data-ttu-id="800af-105">FTP を使用する一方向のメッセージングの例を実行する場合は、次の FTP サイトを作成します。</span><span class="sxs-lookup"><span data-stu-id="800af-105">If you want to execute one-way messaging examples that use FTP, create the following FTP site:</span></span>  
  
    -   <span data-ttu-id="800af-106">FTP 仮想ディレクトリ名:アウト</span><span class="sxs-lookup"><span data-stu-id="800af-106">FTP Virtual Directory name: Out</span></span>  
  
    -   <span data-ttu-id="800af-107">Location: \Source\Samples\DynamicResolution\Test\FTP\Out</span><span class="sxs-lookup"><span data-stu-id="800af-107">Location: \Source\Samples\DynamicResolution\Test\FTP\Out</span></span>  
  
    -   <span data-ttu-id="800af-108">権限:読み取りと書き込み</span><span class="sxs-lookup"><span data-stu-id="800af-108">Permissions: Read and Write</span></span>  
  
    -   <span data-ttu-id="800af-109">BizTalk Application Users グループがこの場所の完全なアクセス許可を確認します。</span><span class="sxs-lookup"><span data-stu-id="800af-109">Ensure the BizTalk Application Users group has full access permission for this location</span></span>  
  
2.  <span data-ttu-id="800af-110">MQSeries を使用する双方向のメッセージングの例を実行する場合は、WebSphere エクスプ ローラーを使用して、以下を作成します。</span><span class="sxs-lookup"><span data-stu-id="800af-110">If you want to execute two-way messaging examples that use MQSeries, use WebSphere Explorer to create the following:</span></span>  
  
    -   <span data-ttu-id="800af-111">ESB という名前のキュー マネージャー。DEP.Sample.QueueManager</span><span class="sxs-lookup"><span data-stu-id="800af-111">A queue manager with the name ESB.DEP.Sample.QueueManager</span></span>  
  
    -   <span data-ttu-id="800af-112">テストをという名前のキュー。ESB 内でチェック アウトします。DEP.Sample.QueueManager</span><span class="sxs-lookup"><span data-stu-id="800af-112">A queue named TEST.OUT within the ESB.DEP.Sample.QueueManager</span></span>  
  
3.  <span data-ttu-id="800af-113">**[スタート]** メニューの **[ファイル名を指定して実行]** をクリックします。</span><span class="sxs-lookup"><span data-stu-id="800af-113">On the **Start** menu, click **Run**.</span></span>  
  
4.  <span data-ttu-id="800af-114">**実行**ダイアログ ボックスに「 **cmd**、し、enter キーを押してコマンド プロンプトを開きます。</span><span class="sxs-lookup"><span data-stu-id="800af-114">In the **Run** dialog box, type **cmd**, and then press ENTER to open the command prompt.</span></span>  
  
5.  <span data-ttu-id="800af-115">次のコマンドを実行して交換、\<パス\>をインストールする .cmd ファイルへの完全パスを持つパラメーター (このリリースでは既定のパスは \Source\Samples\DynamicResolution\Install\Scripts\\)。</span><span class="sxs-lookup"><span data-stu-id="800af-115">Run the following command, replacing the \<path\> parameter with the full path to the .cmd file you want to install (the default path in this release is \Source\Samples\DynamicResolution\Install\Scripts\\):</span></span>  
  
    ```  
    <path>\Setup_bin.cmd  
    ```