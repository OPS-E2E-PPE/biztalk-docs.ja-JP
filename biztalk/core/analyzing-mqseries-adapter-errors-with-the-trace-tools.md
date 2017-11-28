---
title: "トレース ツールを使用して MQSeries アダプターのエラーの分析 |Microsoft ドキュメント"
ms.custom: 
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: 
ms.suite: 
ms.tgt_pltfrm: 
ms.topic: article
helpviewer_keywords:
- Adapter Trace Utility, about Adapter Trace Utility
- Adapter Trace Utility, installing
- installing, Adapter Trace Utility
- Adapter Trace Utility, enabling
- errors, MQSeries adapters
- MQSeries adapters, Adapter Trace Utility
- Adapter Trace Utility, running
- MQSeries adapters, errors
- Adapter Trace Utility
ms.assetid: fdc73d99-3b73-491d-9b2f-7064364fefa7
caps.latest.revision: "12"
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: f8880197e58f6a499cc63e8b6ec89f67af9f0086
ms.sourcegitcommit: cb908c540d8f1a692d01dc8f313e16cb4b4e696d
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 09/20/2017
---
# <a name="analyzing-mqseries-adapter-errors-with-the-trace-tools"></a><span data-ttu-id="22a80-102">トレース ツールを使用して MQSeries アダプターのエラーの分析</span><span class="sxs-lookup"><span data-stu-id="22a80-102">Analyzing MQSeries Adapter Errors with the Trace Tools</span></span>
<span data-ttu-id="22a80-103">アプリケーションの実行時に、トレース ツールを使用して、メッセージングのエラーを分析します。</span><span class="sxs-lookup"><span data-stu-id="22a80-103">You use the trace tools to analyze messaging failures when you run your application.</span></span> <span data-ttu-id="22a80-104">MQSeries アダプタでは、アダプタと BizTalk アプリケーション (trace.cmd) 用と、MQSAgent (MQSTrace.cmd) 用の 2 つのツールを使用する必要があります。</span><span class="sxs-lookup"><span data-stu-id="22a80-104">With the MQSeries adapter you must use two tools, one for the adapter and your BizTalk application (trace.cmd), and the other for the MQSAgent (MQSTrace.cmd).</span></span> <span data-ttu-id="22a80-105">どちらのツールでも、tracelog.exe が使用されます。</span><span class="sxs-lookup"><span data-stu-id="22a80-105">Both tools use tracelog.exe.</span></span> <span data-ttu-id="22a80-106">まだインストールしていない場合は、インストールしてください。</span><span class="sxs-lookup"><span data-stu-id="22a80-106">You have to install tracelog.exe if you do not already have it.</span></span>  
  
 <span data-ttu-id="22a80-107">Trace.cmd と MQSTrace.cmd の両方では、オプションを設定する必要がある (**-ツール**) これらのツールが tracelog.exe ファイルを検索できるようにします。</span><span class="sxs-lookup"><span data-stu-id="22a80-107">With both trace.cmd and MQSTrace.cmd you have to set an option (**-tools**) so that these tools can find the tracelog.exe file.</span></span>  
  
## <a name="install-the-trace-utility"></a><span data-ttu-id="22a80-108">Trace Utility をインストールするには</span><span class="sxs-lookup"><span data-stu-id="22a80-108">Install the Trace Utility</span></span>  
 <span data-ttu-id="22a80-109">BizTalk Adapter Trace Utility をインストールするには、次の手順を実行します。</span><span class="sxs-lookup"><span data-stu-id="22a80-109">To install the BizTalk Adapter Trace Utility, follow these steps:</span></span>  
  
1.  <span data-ttu-id="22a80-110">Tracelog.exe ファイルをダウンロードするには、Microsoft Platform SDK ダウンロード Web サイトを参照してください。 [http://go.microsoft.com/fwlink/?LinkId=21975](http://go.microsoft.com/fwlink/?LinkId=21975)です。</span><span class="sxs-lookup"><span data-stu-id="22a80-110">To download the Tracelog.exe file, visit the Microsoft Platform SDK download Web site at [http://go.microsoft.com/fwlink/?LinkId=21975](http://go.microsoft.com/fwlink/?LinkId=21975).</span></span>  
  
2.  <span data-ttu-id="22a80-111">リンクをクリックして、プラットフォーム SDK Web インストール プログラムを開始、 **x86.exe** Web ページの下部にあるファイルです。</span><span class="sxs-lookup"><span data-stu-id="22a80-111">Start the Platform SDK Web installation program by clicking the link for the **PSDK-x86.exe** file at the bottom of the Web page.</span></span>  
  
3.  <span data-ttu-id="22a80-112">インストールの種類を選択するダイアログ ボックスが表示されたら、カスタム インストール用のオプションを選択します。</span><span class="sxs-lookup"><span data-stu-id="22a80-112">When you are prompted, choose the option for a custom installation.</span></span>  
  
4.  <span data-ttu-id="22a80-113">**[Custom Installation]** ダイアログ ボックスで、利用可能な機能をすべてオフにします。</span><span class="sxs-lookup"><span data-stu-id="22a80-113">In the **Custom Installation** dialog box, click to clear all the available features.</span></span>  
  
5.  <span data-ttu-id="22a80-114">**[Microsoft Windows Core SDK]** 機能を展開し、 **[Tools]** 機能を展開します。</span><span class="sxs-lookup"><span data-stu-id="22a80-114">Expand the **Microsoft Windows Core SDK** feature, and then expand the **Tools** feature.</span></span>  
  
6.  <span data-ttu-id="22a80-115">**[Tools (Intel 64-bit)]** 機能を選択し、 **[Will be installed on local hard drive]**をクリックします。</span><span class="sxs-lookup"><span data-stu-id="22a80-115">Choose the **Tools (Intel 64-bit)** feature, and then click **Will be installed on local hard drive**.</span></span>  
  
7.  <span data-ttu-id="22a80-116">**[Next]**を 2 回クリックし、インストールを開始します。 ****</span><span class="sxs-lookup"><span data-stu-id="22a80-116">Click **Next**, and then click **Next** again to start the installation.</span></span>  
  
8.  <span data-ttu-id="22a80-117">検索、*ドライブ*:\\*MicrosoftPlatformSDKInstallationFolder\bin*フォルダーをクリックし、Microsoft BizTalk Server のインストール フォルダーに Tracelog.exe ファイルをコピーします。</span><span class="sxs-lookup"><span data-stu-id="22a80-117">Locate the *drive*:\\*MicrosoftPlatformSDKInstallationFolder\bin* folder, and then copy the Tracelog.exe file to the Microsoft BizTalk Server installation folder.</span></span> <span data-ttu-id="22a80-118">BizTalk Server のインストール フォルダには、Trace.cmd ファイルも含まれています。</span><span class="sxs-lookup"><span data-stu-id="22a80-118">The BizTalk Server installation folder also contains the Trace.cmd file.</span></span>  
  
## <a name="enable-the-trace-utility"></a><span data-ttu-id="22a80-119">Trace Utility を有効にするには</span><span class="sxs-lookup"><span data-stu-id="22a80-119">Enable the Trace Utility</span></span>  
 <span data-ttu-id="22a80-120">BizTalk Server で BizTalk Adapter Trace Utility を有効にするには、次の手順を実行します。</span><span class="sxs-lookup"><span data-stu-id="22a80-120">To enable the BizTalk Adapter Trace Utility in BizTalk Server, follow these steps:</span></span>  
  
1.  <span data-ttu-id="22a80-121">trace.cmd があるディレクトリに移動します。</span><span class="sxs-lookup"><span data-stu-id="22a80-121">Move to the directory that contains trace.cmd.</span></span> <span data-ttu-id="22a80-122">既定の場所は [!INCLUDE[btsBizTalkServer2006r3](../includes/btsbiztalkserver2006r3-md.md)] ディレクトリです。</span><span class="sxs-lookup"><span data-stu-id="22a80-122">The default location is the Microsoft [!INCLUDE[btsBizTalkServer2006r3](../includes/btsbiztalkserver2006r3-md.md)] directory.</span></span>  
  
2.  <span data-ttu-id="22a80-123">次のコマンドを入力します。入力時に二重引用符で囲まれたディレクトリを、使用しているコンピュータの tracelog.exe ファイルがあるディレクトリに置き換えてください。入力後、Enter キーを押します。</span><span class="sxs-lookup"><span data-stu-id="22a80-123">Type the following command, substituting the directory that contains the tracelog.exe file on your computer for the directory in quotes, and then press ENTER:</span></span>  
  
     <span data-ttu-id="22a80-124">**トレース - ツール"c:\Program files \microsoft sdk \bin"**</span><span class="sxs-lookup"><span data-stu-id="22a80-124">**trace -tools "c:\Program Files\Microsoft SDK\Bin"**</span></span>  
  
3.  <span data-ttu-id="22a80-125">MQSTrace.cmd があるディレクトリに移動します。</span><span class="sxs-lookup"><span data-stu-id="22a80-125">Move to the directory that contains MQSTrace.cmd.</span></span>  
  
4.  <span data-ttu-id="22a80-126">次のコマンドを入力します。入力時に二重引用符で囲まれたディレクトリを、使用しているコンピュータの tracelog.exe ファイルがあるディレクトリに置き換えてください。入力後、Enter キーを押します。</span><span class="sxs-lookup"><span data-stu-id="22a80-126">Type the following command, substituting the directory that contains the tracelog.exe file on your computer for the directory in quotes, and then press ENTER:</span></span>  
  
     <span data-ttu-id="22a80-127">**MQSTrace-ツールの"c:\Program files \microsoft sdk \bin"**</span><span class="sxs-lookup"><span data-stu-id="22a80-127">**MQSTrace -tools "c:\Program Files\Microsoft SDK\Bin"**</span></span>  
  
## <a name="run-the-trace-utility"></a><span data-ttu-id="22a80-128">Trace Utility を実行するには</span><span class="sxs-lookup"><span data-stu-id="22a80-128">Run the Trace Utility</span></span>  
 <span data-ttu-id="22a80-129">BizTalk Adapter Trace Utility を実行するには、次の手順を実行します。</span><span class="sxs-lookup"><span data-stu-id="22a80-129">To run the BizTalk Adapter Trace Utility, follow these steps:</span></span>  
  
1.  <span data-ttu-id="22a80-130">コマンド プロンプトで次のように入力します。 **trace.cmd--start-high**、ENTER キーを押します。</span><span class="sxs-lookup"><span data-stu-id="22a80-130">At the command prompt, type **trace.cmd -start -high**, and then press ENTER.</span></span>  
  
2.  <span data-ttu-id="22a80-131">エラーが発生するシナリオを実行します。</span><span class="sxs-lookup"><span data-stu-id="22a80-131">Run your failure scenario.</span></span>  
  
3.  <span data-ttu-id="22a80-132">コマンド プロンプトで次のように入力します。 **trace.cmd-停止**、ENTER キーを押します。</span><span class="sxs-lookup"><span data-stu-id="22a80-132">At the command prompt, type **trace.cmd -stop**, and then press ENTER.</span></span>  
  
4.  <span data-ttu-id="22a80-133">bts2006.bin ファイルには、トレース ツールの出力が含まれます。</span><span class="sxs-lookup"><span data-stu-id="22a80-133">The bts2006.bin file contains the output of the trace tool.</span></span> <span data-ttu-id="22a80-134">分析のため、マイクロソフト製品サポート サービスに連絡してください。</span><span class="sxs-lookup"><span data-stu-id="22a80-134">Contact Microsoft Product Support Services for analysis.</span></span> <span data-ttu-id="22a80-135">詳細については、次を参照してください。 [http://go.microsoft.com/fwlink/?LinkId=41645](http://go.microsoft.com/fwlink/?LinkId=41645)です。</span><span class="sxs-lookup"><span data-stu-id="22a80-135">For more information, see [http://go.microsoft.com/fwlink/?LinkId=41645](http://go.microsoft.com/fwlink/?LinkId=41645).</span></span>  
  
 <span data-ttu-id="22a80-136">MQSAgent Trace Utility を実行するには、次の手順を実行します。</span><span class="sxs-lookup"><span data-stu-id="22a80-136">To run the MQSAgent Trace Utility, follow these steps:</span></span>  
  
1.  <span data-ttu-id="22a80-137">コマンド プロンプトで次のように入力します。 **MQSTrace.cmd--start-high**、ENTER キーを押します。</span><span class="sxs-lookup"><span data-stu-id="22a80-137">At the command prompt, type **MQSTrace.cmd -start -high**, and then press ENTER.</span></span>  
  
2.  <span data-ttu-id="22a80-138">エラーが発生するシナリオを実行します。</span><span class="sxs-lookup"><span data-stu-id="22a80-138">Run your failure scenario.</span></span>  
  
3.  <span data-ttu-id="22a80-139">コマンド プロンプトで次のように入力します。 **MQSTrace.cmd-停止**です。</span><span class="sxs-lookup"><span data-stu-id="22a80-139">At the command prompt, type **MQSTrace.cmd -stop**.</span></span>  
  
4.  <span data-ttu-id="22a80-140">MQSAdapterTrace.bin ファイルには、トレース ツールの出力が含まれます。</span><span class="sxs-lookup"><span data-stu-id="22a80-140">The MQSAdapterTrace.bin file contains the output of the trace tool.</span></span> <span data-ttu-id="22a80-141">分析のため、マイクロソフト製品サポート サービスに連絡してください。</span><span class="sxs-lookup"><span data-stu-id="22a80-141">Contact Microsoft Product Support Services for analysis.</span></span> <span data-ttu-id="22a80-142">詳細については、次を参照してください。 [http://go.microsoft.com/fwlink/?LinkId=41645](http://go.microsoft.com/fwlink/?LinkId=41645)です。</span><span class="sxs-lookup"><span data-stu-id="22a80-142">For more information see [http://go.microsoft.com/fwlink/?LinkId=41645](http://go.microsoft.com/fwlink/?LinkId=41645).</span></span>