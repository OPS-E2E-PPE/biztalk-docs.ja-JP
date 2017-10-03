---
title: "インストール スクリプトを使用して、JMS MQRFH2 サンプルのインストール |Microsoft ドキュメント"
ms.custom: 
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: 
ms.suite: 
ms.tgt_pltfrm: 
ms.topic: article
ms.assetid: 785f3e32-83b4-406a-af1b-9499115fbb8f
caps.latest.revision: "2"
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: 27b3606d53f692ff52779eeac3505fd8062bed28
ms.sourcegitcommit: cb908c540d8f1a692d01dc8f313e16cb4b4e696d
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 09/20/2017
---
# <a name="install-the-jms-mqrfh2-sample-using-the-install-scripts"></a><span data-ttu-id="6473d-102">インストール スクリプトを使用して、JMS MQRFH2 サンプルをインストールします。</span><span class="sxs-lookup"><span data-stu-id="6473d-102">Install the JMS MQRFH2 Sample Using the Install Scripts</span></span>
<span data-ttu-id="6473d-103">このセクションでは、JMS MQRFH2 で提供するインストール スクリプトを使用してサンプルをインストールする方法について説明します、[!INCLUDE[esbToolkit](../includes/esbtoolkit-md.md)]です。</span><span class="sxs-lookup"><span data-stu-id="6473d-103">This section describes how you can install the JMS MQRFH2 sample using the install scripts provided with the [!INCLUDE[esbToolkit](../includes/esbtoolkit-md.md)].</span></span>  
  
 <span data-ttu-id="6473d-104">**インストール スクリプトから JMS MQRFH2 サンプルをインストールするには**</span><span class="sxs-lookup"><span data-stu-id="6473d-104">**To install the JMS MQRFH2 samples from the install scripts**</span></span>  
  
1.  <span data-ttu-id="6473d-105">名前のキュー マネージャーを作成する WebSphere エクスプ ローラーを使用して**ESB です。JMS です。Sample.QueueManager**です。</span><span class="sxs-lookup"><span data-stu-id="6473d-105">Using WebSphere Explorer, create a Queue Manager with the name **ESB.JMS.Sample.QueueManager**.</span></span>  
  
2.  <span data-ttu-id="6473d-106">次の 4 つのキュー内で WebSphere エクスプ ローラーを使用して作成**ESB です。JMS です。Sample.QueueManager:**</span><span class="sxs-lookup"><span data-stu-id="6473d-106">Using WebSphere Explorer, create the following four queues within **ESB.JMS.Sample.QueueManager:**</span></span>  
  
    -   <span data-ttu-id="6473d-107">ESB です。JMS です。サンプルです。DYNAMICQ1</span><span class="sxs-lookup"><span data-stu-id="6473d-107">ESB.JMS.SAMPLE.DYNAMICQ1</span></span>  
  
    -   <span data-ttu-id="6473d-108">ESB です。JMS です。サンプルです。DYNAMICQ2</span><span class="sxs-lookup"><span data-stu-id="6473d-108">ESB.JMS.SAMPLE.DYNAMICQ2</span></span>  
  
    -   <span data-ttu-id="6473d-109">ESB です。JMS です。サンプルです。応答</span><span class="sxs-lookup"><span data-stu-id="6473d-109">ESB.JMS.SAMPLE.REPLY</span></span>  
  
    -   <span data-ttu-id="6473d-110">ESB です。JMS です。サンプルです。SENDTOBIZTALK</span><span class="sxs-lookup"><span data-stu-id="6473d-110">ESB.JMS.SAMPLE.SENDTOBIZTALK</span></span>  
  
3.  <span data-ttu-id="6473d-111">**[スタート]** メニューの **[ファイル名を指定して実行]**をクリックします。</span><span class="sxs-lookup"><span data-stu-id="6473d-111">On the **Start** menu, click **Run**.</span></span>  
  
4.  <span data-ttu-id="6473d-112">**実行** ダイアログ ボックスで、「 **cmd**、ENTER キーを押します。</span><span class="sxs-lookup"><span data-stu-id="6473d-112">In the **Run** dialog box, type **cmd**, and then press ENTER.</span></span>  
  
5.  <span data-ttu-id="6473d-113">次のコマンド実行交換、 *\<パス >*をインストールする .cmd ファイルへの完全パスを持つパラメーター (このリリースでは既定のパスは \Source\Samples\JMS\Install\Scripts\\)。</span><span class="sxs-lookup"><span data-stu-id="6473d-113">Run the following command, replacing the *\<path>* parameter with the full path to the .cmd file you want to install (the default path in this release is \Source\Samples\JMS\Install\Scripts\\):</span></span>  
  
    ```  
    <path>\Setup_bin.cmd  
    ```