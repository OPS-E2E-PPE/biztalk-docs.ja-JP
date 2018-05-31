---
title: インストール スクリプトを使用して動的解決のサンプルをインストール |Microsoft ドキュメント
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
ms.openlocfilehash: 872bb73b9060e25986876c1c2da71afae84b5c52
ms.sourcegitcommit: 5abd0ed3f9e4858ffaaec5481bfa8878595e95f7
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 11/28/2017
ms.locfileid: "25973144"
---
# <a name="install-the-dynamic-resolution-sample-using-the-install-scripts"></a><span data-ttu-id="37e4e-102">インストール スクリプトを使用して動的解決のサンプルをインストールします。</span><span class="sxs-lookup"><span data-stu-id="37e4e-102">Install the Dynamic Resolution Sample Using the Install Scripts</span></span>
<span data-ttu-id="37e4e-103">このセクションで提供するインストール スクリプトから動的解決のサンプルをインストールする方法について説明します、[!INCLUDE[esbToolkit](../includes/esbtoolkit-md.md)]です。</span><span class="sxs-lookup"><span data-stu-id="37e4e-103">This section describes how you can install the Dynamic Resolution sample from the install scripts provided with the [!INCLUDE[esbToolkit](../includes/esbtoolkit-md.md)].</span></span>  
  
 <span data-ttu-id="37e4e-104">**インストール スクリプトから動的解決サンプルをインストールするには**</span><span class="sxs-lookup"><span data-stu-id="37e4e-104">**To install the Dynamic Resolution sample from the install scripts**</span></span>  
  
1.  <span data-ttu-id="37e4e-105">FTP を使用する一方向のメッセージングの例を実行する場合は、次の FTP サイトを作成します。</span><span class="sxs-lookup"><span data-stu-id="37e4e-105">If you want to execute one-way messaging examples that use FTP, create the following FTP site:</span></span>  
  
    -   <span data-ttu-id="37e4e-106">FTP 仮想ディレクトリ名: アウト</span><span class="sxs-lookup"><span data-stu-id="37e4e-106">FTP Virtual Directory name: Out</span></span>  
  
    -   <span data-ttu-id="37e4e-107">場所: \Source\Samples\DynamicResolution\Test\FTP\Out</span><span class="sxs-lookup"><span data-stu-id="37e4e-107">Location: \Source\Samples\DynamicResolution\Test\FTP\Out</span></span>  
  
    -   <span data-ttu-id="37e4e-108">アクセス許可: 読み取りし、書き込み</span><span class="sxs-lookup"><span data-stu-id="37e4e-108">Permissions: Read and Write</span></span>  
  
    -   <span data-ttu-id="37e4e-109">BizTalk Application Users グループがこの場所に対するフル アクセスのアクセス許可を確認してください。</span><span class="sxs-lookup"><span data-stu-id="37e4e-109">Ensure the BizTalk Application Users group has full access permission for this location</span></span>  
  
2.  <span data-ttu-id="37e4e-110">MQSeries を使用する双方向のメッセージングの例を実行する場合は、WebSphere エクスプ ローラーを使用して、以下を作成します。</span><span class="sxs-lookup"><span data-stu-id="37e4e-110">If you want to execute two-way messaging examples that use MQSeries, use WebSphere Explorer to create the following:</span></span>  
  
    -   <span data-ttu-id="37e4e-111">ESB 名前のキュー マネージャー。 DEPSample.QueueManager</span><span class="sxs-lookup"><span data-stu-id="37e4e-111">A queue manager with the name ESB.DEP.Sample.QueueManager</span></span>  
  
    -   <span data-ttu-id="37e4e-112">テストをという名前のキューです。ESB 内で出力します。 DEPSample.QueueManager</span><span class="sxs-lookup"><span data-stu-id="37e4e-112">A queue named TEST.OUT within the ESB.DEP.Sample.QueueManager</span></span>  
  
3.  <span data-ttu-id="37e4e-113">**[スタート]** メニューの **[ファイル名を指定して実行]** をクリックします。</span><span class="sxs-lookup"><span data-stu-id="37e4e-113">On the **Start** menu, click **Run**.</span></span>  
  
4.  <span data-ttu-id="37e4e-114">**実行** ダイアログ ボックスで、「 **cmd**、し、enter キーを押してコマンド プロンプトを開きます。</span><span class="sxs-lookup"><span data-stu-id="37e4e-114">In the **Run** dialog box, type **cmd**, and then press ENTER to open the command prompt.</span></span>  
  
5.  <span data-ttu-id="37e4e-115">次のコマンド実行交換、\<パス\>をインストールする .cmd ファイルへの完全パスを持つパラメーター (このリリースでは既定のパスは \Source\Samples\DynamicResolution\Install\Scripts\\)。</span><span class="sxs-lookup"><span data-stu-id="37e4e-115">Run the following command, replacing the \<path\> parameter with the full path to the .cmd file you want to install (the default path in this release is \Source\Samples\DynamicResolution\Install\Scripts\\):</span></span>  
  
    ```  
    <path>\Setup_bin.cmd  
    ```