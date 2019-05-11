---
title: インストール スクリプトを使用して、JMS MQRFH2 サンプルのインストール |Microsoft Docs
ms.custom: ''
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: ''
ms.suite: ''
ms.tgt_pltfrm: ''
ms.topic: article
ms.assetid: 785f3e32-83b4-406a-af1b-9499115fbb8f
caps.latest.revision: 2
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: 8dfde04d2f4b9faebabbac102f938839596540af
ms.sourcegitcommit: 381e83d43796a345488d54b3f7413e11d56ad7be
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 05/07/2019
ms.locfileid: "65399884"
---
# <a name="install-the-jms-mqrfh2-sample-using-the-install-scripts"></a><span data-ttu-id="f6453-102">インストール スクリプトを使用して、JMS MQRFH2 サンプルをインストールします。</span><span class="sxs-lookup"><span data-stu-id="f6453-102">Install the JMS MQRFH2 Sample Using the Install Scripts</span></span>
<span data-ttu-id="f6453-103">このセクションでは、付属のインストール スクリプトを使用して、JMS MQRFH2 サンプルをインストールする方法について説明します、[!INCLUDE[esbToolkit](../includes/esbtoolkit-md.md)]します。</span><span class="sxs-lookup"><span data-stu-id="f6453-103">This section describes how you can install the JMS MQRFH2 sample using the install scripts provided with the [!INCLUDE[esbToolkit](../includes/esbtoolkit-md.md)].</span></span>  
  
 <span data-ttu-id="f6453-104">**インストール スクリプトから JMS MQRFH2 サンプルをインストールするには**</span><span class="sxs-lookup"><span data-stu-id="f6453-104">**To install the JMS MQRFH2 samples from the install scripts**</span></span>  
  
1.  <span data-ttu-id="f6453-105">名前のキュー マネージャーを作成する WebSphere エクスプ ローラーを使用して**ESB します。JMS します。Sample.QueueManager**します。</span><span class="sxs-lookup"><span data-stu-id="f6453-105">Using WebSphere Explorer, create a Queue Manager with the name **ESB.JMS.Sample.QueueManager**.</span></span>  
  
2.  <span data-ttu-id="f6453-106">内で次の 4 つのキューを作成して WebSphere エクスプ ローラーを使用して**ESB します。JMS します。Sample.QueueManager:**</span><span class="sxs-lookup"><span data-stu-id="f6453-106">Using WebSphere Explorer, create the following four queues within **ESB.JMS.Sample.QueueManager:**</span></span>  
  
    -   <span data-ttu-id="f6453-107">ESB します。JMS します。サンプルです。DYNAMICQ1</span><span class="sxs-lookup"><span data-stu-id="f6453-107">ESB.JMS.SAMPLE.DYNAMICQ1</span></span>  
  
    -   <span data-ttu-id="f6453-108">ESB します。JMS します。サンプルです。DYNAMICQ2</span><span class="sxs-lookup"><span data-stu-id="f6453-108">ESB.JMS.SAMPLE.DYNAMICQ2</span></span>  
  
    -   <span data-ttu-id="f6453-109">ESB します。JMS します。サンプルです。応答</span><span class="sxs-lookup"><span data-stu-id="f6453-109">ESB.JMS.SAMPLE.REPLY</span></span>  
  
    -   <span data-ttu-id="f6453-110">ESB します。JMS します。サンプルです。SENDTOBIZTALK</span><span class="sxs-lookup"><span data-stu-id="f6453-110">ESB.JMS.SAMPLE.SENDTOBIZTALK</span></span>  
  
3.  <span data-ttu-id="f6453-111">**[スタート]** メニューの **[ファイル名を指定して実行]** をクリックします。</span><span class="sxs-lookup"><span data-stu-id="f6453-111">On the **Start** menu, click **Run**.</span></span>  
  
4.  <span data-ttu-id="f6453-112">**実行**ダイアログ ボックスに「 **cmd**、し、ENTER キーを押します。</span><span class="sxs-lookup"><span data-stu-id="f6453-112">In the **Run** dialog box, type **cmd**, and then press ENTER.</span></span>  
  
5.  <span data-ttu-id="f6453-113">次のコマンドを実行して交換、 *\<パス\>* をインストールする .cmd ファイルへの完全パスを持つパラメーター (このリリースでは既定のパスは \Source\Samples\JMS\Install\Scripts\\):</span><span class="sxs-lookup"><span data-stu-id="f6453-113">Run the following command, replacing the *\<path\>* parameter with the full path to the .cmd file you want to install (the default path in this release is \Source\Samples\JMS\Install\Scripts\\):</span></span>  
  
    ```  
    <path>\Setup_bin.cmd  
    ```