---
title: BizTalk アダプターのトレースを使用して |Microsoft Docs
ms.custom: ''
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: ''
ms.suite: ''
ms.tgt_pltfrm: ''
ms.topic: article
helpviewer_keywords:
- Adapter Trace Utility, installing
- installing, Adapter Trace Utility
- Adapter Trace Utility, enabling
- Adapter Trace Utility, running
- enabling, Adapter Trace Utility
ms.assetid: ddc6b2c7-9dee-43c1-950b-8fd580bfcb26
caps.latest.revision: 19
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: 8b381e869597c11281f715ba0d05d504671cd062
ms.sourcegitcommit: 381e83d43796a345488d54b3f7413e11d56ad7be
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 05/07/2019
ms.locfileid: "65401702"
---
# <a name="using-biztalk-adapter-tracing"></a><span data-ttu-id="97de7-102">BizTalk アダプターのトレースの使用</span><span class="sxs-lookup"><span data-stu-id="97de7-102">Using BizTalk Adapter Tracing</span></span>
<span data-ttu-id="97de7-103">ここでは、Trace Log tool (トレース ログ ツール) をインストールする方法、および BizTalk アダプターのトレースを可能にする方法について説明します。</span><span class="sxs-lookup"><span data-stu-id="97de7-103">This topic describes how to install the Trace Log tool and how to enable BizTalk adapter tracing.</span></span>  
  
## <a name="install-the-trace-log-tool"></a><span data-ttu-id="97de7-104">トレース ログ ツールのインストール</span><span class="sxs-lookup"><span data-stu-id="97de7-104">Install the Trace Log Tool</span></span>  
  
#### <a name="to-install-the-trace-log-tool-tracelogexe"></a><span data-ttu-id="97de7-105">トレース ログ ツール (tracelog.exe) をインストールするには</span><span class="sxs-lookup"><span data-stu-id="97de7-105">To install the Trace Log tool (tracelog.exe)</span></span>  
  
1. <span data-ttu-id="97de7-106">トレース ログ ツールを [Microsoft® Windows® Software Development Kit Update for Windows Vista](http://go.microsoft.com/fwlink/?LinkId=128279) Web サイトからダウンロードします。</span><span class="sxs-lookup"><span data-stu-id="97de7-106">Download the Trace Log tool from the [Microsoft® Windows® Software Development Kit Update for Windows Vista](http://go.microsoft.com/fwlink/?LinkId=128279) Web site.</span></span>  
  
   > [!NOTE]
   >  <span data-ttu-id="97de7-107">[!INCLUDE[btsWinSvr2k8](../includes/btswinsvr2k8-md.md)]を実行している場合でも、このバージョン (6.0) の SDK をインストールしてください。</span><span class="sxs-lookup"><span data-stu-id="97de7-107">Install this version (6.0) of the SDK even if you are running [!INCLUDE[btsWinSvr2k8](../includes/btswinsvr2k8-md.md)].</span></span> <span data-ttu-id="97de7-108">インストールする場合、 **Windows SDK for Windows Server 2008 および .NET Framework 3.5**バージョン (v します。</span><span class="sxs-lookup"><span data-stu-id="97de7-108">If you install the **Windows SDK for Windows Server 2008 and .NET Framework 3.5** version (v.</span></span> <span data-ttu-id="97de7-109">6.1)、トレース ログ ツールはインストールされません。</span><span class="sxs-lookup"><span data-stu-id="97de7-109">6.1), it will not install the Trace Log tool.</span></span>  
  
2. <span data-ttu-id="97de7-110">Web ページ下部にある **PSDK-x86.exe** ファイルのリンクをクリックして、 **Microsoft® Windows® Software Development Kit Update for Windows Vista** Web インストール プログラムを起動します。</span><span class="sxs-lookup"><span data-stu-id="97de7-110">Start the **Microsoft® Windows® Software Development Kit Update for Windows Vista** Web installation program by clicking the link for the **PSDK-x86.exe** file at the bottom of the Web page.</span></span>  
  
   > [!NOTE]
   >  <span data-ttu-id="97de7-111">64 ビット版の Windows を使用している場合は、お使いのシステム用の正しいファイルを選択してダウンロードしてください。</span><span class="sxs-lookup"><span data-stu-id="97de7-111">If you are using a 64-bit version of Windows choose the correct files to download for your system.</span></span>  
  
3. <span data-ttu-id="97de7-112">**[Select an Installation Type]** ダイアログ ボックスで、 **[Custom]** インストールを選択し、 **[Next]** をクリックします。</span><span class="sxs-lookup"><span data-stu-id="97de7-112">In the **Select an Installation Type** dialog box, choose the option for a **Custom** installation, and then click **Next**.</span></span>  
  
4. <span data-ttu-id="97de7-113">既定のインストール先をそのまま使用し、 **[Next]** をクリックします。</span><span class="sxs-lookup"><span data-stu-id="97de7-113">Accept the default installation location and then click **Next**.</span></span>  
  
5. <span data-ttu-id="97de7-114">**[Custom Installation]** ダイアログ ボックスで、利用可能な機能をすべてオフにします。</span><span class="sxs-lookup"><span data-stu-id="97de7-114">In the **Custom Installation** dialog box, click to clear all the available features.</span></span>  
  
6. <span data-ttu-id="97de7-115">**[Microsoft Windows Core SDK]** 機能を展開し、 **[Tools]** 機能を展開します。</span><span class="sxs-lookup"><span data-stu-id="97de7-115">Expand the **Microsoft Windows Core SDK** feature, and then expand the **Tools** feature.</span></span>  
  
7. <span data-ttu-id="97de7-116">**[Tools (Intel 64-bit)]** 機能を選択し、 **[Will be installed on local hard drive]** をクリックします。</span><span class="sxs-lookup"><span data-stu-id="97de7-116">Choose the **Tools (Intel 64-bit)** feature, and then click **Will be installed on local hard drive**.</span></span>  
  
8. <span data-ttu-id="97de7-117">**次へ**をクリックし、**次へ**をクリックしてインストールを開始します。</span><span class="sxs-lookup"><span data-stu-id="97de7-117">Click **Next**, and then click **Next** again to start the installation.</span></span>  
  
   > [!NOTE]
   >  <span data-ttu-id="97de7-118">**Microsoft® Windows® Software Development Kit Update for Windows Vista** のインストール後、トレース ログ ツールと同時にインストールするよう選択した機能によっては、再起動を求められることがあります。</span><span class="sxs-lookup"><span data-stu-id="97de7-118">After installing the **Microsoft® Windows® Software Development Kit Update for Windows Vista** you may be prompted to reboot depending upon what other features you chose to install along with the Trace Log tool.</span></span> <span data-ttu-id="97de7-119">これは、 **Microsoft® Windows® Software Development Kit Update for Windows Vista** の特定のコンポーネントが、再起動するまで正常に機能しないためです。</span><span class="sxs-lookup"><span data-stu-id="97de7-119">This is because certain components of the **Microsoft® Windows® Software Development Kit Update for Windows Vista** will not function correctly until the reboot has been completed.</span></span> <span data-ttu-id="97de7-120">トレース ログ ツールを使用するために再起動する必要はありません。</span><span class="sxs-lookup"><span data-stu-id="97de7-120">You do not need to reboot to use the Trace Log tool.</span></span>  
  
## <a name="enable-biztalk-adapter-tracing-with-tracecmd"></a><span data-ttu-id="97de7-121">trace.cmd を使用した BizTalk アダプターのトレースの有効化</span><span class="sxs-lookup"><span data-stu-id="97de7-121">Enable BizTalk Adapter Tracing with trace.cmd</span></span>  
  
#### <a name="to-enable-biztalk-adapter-tracing"></a><span data-ttu-id="97de7-122">BizTalk アダプターのトレースを有効化するには</span><span class="sxs-lookup"><span data-stu-id="97de7-122">To enable BizTalk adapter tracing</span></span>  
  
1. <span data-ttu-id="97de7-123">コマンド プロンプトには、BizTalk Server がインストールされているディレクトリに現在のディレクトリを変更します。</span><span class="sxs-lookup"><span data-stu-id="97de7-123">At a command prompt, change the current directory to the directory where BizTalk Server is installed.</span></span> <span data-ttu-id="97de7-124">既定では、BizTalk Server がインストールされている、[!INCLUDE[btsBiztalkServerPath](../includes/btsbiztalkserverpath-md.md)]ディレクトリ。</span><span class="sxs-lookup"><span data-stu-id="97de7-124">By default, BizTalk Server is installed in the [!INCLUDE[btsBiztalkServerPath](../includes/btsbiztalkserverpath-md.md)] directory.</span></span>  <span data-ttu-id="97de7-125">インストール パスは、Windows と BizTalk Server の 64 ビット バージョンを使用して場合[!INCLUDE[btsBizTalkServerPathx64](../includes/btsbiztalkserverpathx64-md.md)]します。</span><span class="sxs-lookup"><span data-stu-id="97de7-125">If using a 64-bit version of Windows and BizTalk Server, the installation path is [!INCLUDE[btsBizTalkServerPathx64](../includes/btsbiztalkserverpathx64-md.md)].</span></span>  
  
2. <span data-ttu-id="97de7-126">次のコマンドを入力し、Enter キーを押します。</span><span class="sxs-lookup"><span data-stu-id="97de7-126">Type the following command, and then press ENTER:</span></span>  
  
    <span data-ttu-id="97de7-127">**トレース - ツール「トレース ログ ツールのパス」**</span><span class="sxs-lookup"><span data-stu-id="97de7-127">**trace -tools "Path of the Trace Log tool"**</span></span>  
  
    <span data-ttu-id="97de7-128">既定では、トレース ログ ツール (tracelog.exe) は **C:\Program Files\Microsoft SDKs\Windows\v6.0\Bin** ディレクトリにあります。</span><span class="sxs-lookup"><span data-stu-id="97de7-128">By default, the Trace Log tool (tracelog.exe) is located in the **C:\Program Files\Microsoft SDKs\Windows\v6.0\Bin** directory.</span></span> <span data-ttu-id="97de7-129">64 ビット版の Windows を使用している場合、トレース ログ ツールは **C:\Program Files (x86)\Microsoft SDKs\Windows\v6.0\Bin**.にあります。</span><span class="sxs-lookup"><span data-stu-id="97de7-129">If using a 64-bit version of Windows the Trace Log tool is located at **C:\Program Files (x86)\Microsoft SDKs\Windows\v6.0\Bin**.</span></span>  <span data-ttu-id="97de7-130">トレース ログ ツールのパスは二重引用符で囲む必要があります。</span><span class="sxs-lookup"><span data-stu-id="97de7-130">You must enclose the path of the Trace Log tool in quotation marks.</span></span>  
  
    <span data-ttu-id="97de7-131">たとえば、次のコマンドを入力し、ENTER キーを押します。</span><span class="sxs-lookup"><span data-stu-id="97de7-131">For example, type the following command, and then press ENTER:</span></span>  
  
    <span data-ttu-id="97de7-132">**trace -tools "C:\Program Files\Microsoft SDKs\Windows\v6.0\Bin"**</span><span class="sxs-lookup"><span data-stu-id="97de7-132">**trace -tools "C:\Program Files\Microsoft SDKs\Windows\v6.0\Bin"**</span></span>  
  
   > [!NOTE]
   >  <span data-ttu-id="97de7-133">**-tools** スイッチは、Trace.cmd ファイルに Tracelog.exe ファイルの場所を示します。</span><span class="sxs-lookup"><span data-stu-id="97de7-133">The **-tools** switch indicates to the Trace.cmd file the location of the Tracelog.exe file.</span></span>  
   >   
   >  <span data-ttu-id="97de7-134">コマンドが正常に実行された場合は、次のように出力されます。</span><span class="sxs-lookup"><span data-stu-id="97de7-134">If the command successfully runs, the output will be like below:</span></span>  
   >   
   >  <span data-ttu-id="97de7-135">**2.0 - 管理 BizTalk 2006 リリース ビット トレースをトレースします。**</span><span class="sxs-lookup"><span data-stu-id="97de7-135">**trace 2.0 - Manage BizTalk 2006 Release Bits Tracing.**</span></span>  
   >   
   >  <span data-ttu-id="97de7-136">**Setting TRACE_TOOL_SEARCH_PATH to "C:\Program Files\Microsoft SDKs\Windows\v6.0\Bin "**</span><span class="sxs-lookup"><span data-stu-id="97de7-136">**Setting TRACE_TOOL_SEARCH_PATH to "C:\Program Files\Microsoft SDKs\Windows\v6.0\Bin "**</span></span>  
  
## <a name="capture-trace-output-with-tracecmd"></a><span data-ttu-id="97de7-137">trace.cmd を使用したトレース出力の取得</span><span class="sxs-lookup"><span data-stu-id="97de7-137">Capture Trace output with trace.cmd</span></span>  
  
#### <a name="to-capture-trace-output"></a><span data-ttu-id="97de7-138">トレース出力を取得するには</span><span class="sxs-lookup"><span data-stu-id="97de7-138">To capture trace output</span></span>  
  
1. <span data-ttu-id="97de7-139">コマンド プロンプトには、BizTalk Server がインストールされているディレクトリに現在のディレクトリを変更します。</span><span class="sxs-lookup"><span data-stu-id="97de7-139">At a command prompt, change the current directory to the directory where BizTalk Server is installed.</span></span>  
  
2. <span data-ttu-id="97de7-140">コマンド プロンプトで次のコマンドを入力し、Enter キーを押します。</span><span class="sxs-lookup"><span data-stu-id="97de7-140">At a command prompt, type the following command, and then press ENTER:</span></span>  
  
    <span data-ttu-id="97de7-141">**トレースの開始**</span><span class="sxs-lookup"><span data-stu-id="97de7-141">**trace -start**</span></span>  
  
3. <span data-ttu-id="97de7-142">トレース出力を取得するシナリオを再現します。</span><span class="sxs-lookup"><span data-stu-id="97de7-142">Reproduce the scenario for which you want to capture trace output.</span></span>  
  
4. <span data-ttu-id="97de7-143">コマンド プロンプトで次のコマンドを入力し、Enter キーを押します。</span><span class="sxs-lookup"><span data-stu-id="97de7-143">At a command prompt, type the following command, and then press ENTER:</span></span>  
  
    <span data-ttu-id="97de7-144">**trace -stop**</span><span class="sxs-lookup"><span data-stu-id="97de7-144">**trace -stop**</span></span>  
  
5. <span data-ttu-id="97de7-145">トレースを停止した後、 **Btstrace.bin** という名前のバイナリ ファイルが、 [!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)] がインストールされているフォルダーに生成されます。</span><span class="sxs-lookup"><span data-stu-id="97de7-145">After you stop the trace, a binary file that is named **Btstrace.bin** is generated in the folder where [!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)] is installed.</span></span>  
  
6. <span data-ttu-id="97de7-146">分析のためにマイクロソフト製品サポート サービスに **Btstrace.bin** ファイルを送信します。</span><span class="sxs-lookup"><span data-stu-id="97de7-146">Send the **Btstrace.bin** file to Microsoft Product Support Services for analysis.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="97de7-147">参照</span><span class="sxs-lookup"><span data-stu-id="97de7-147">See Also</span></span>  
 <span data-ttu-id="97de7-148">[アダプターを使用します。](../core/using-adapters.md) </span><span class="sxs-lookup"><span data-stu-id="97de7-148">[Using Adapters](../core/using-adapters.md) </span></span>  
 [<span data-ttu-id="97de7-149">Windows SharePoint Services アダプターのトラブルシューティング</span><span class="sxs-lookup"><span data-stu-id="97de7-149">Troubleshooting the Windows SharePoint Services Adapter</span></span>](../core/troubleshooting-the-windows-sharepoint-services-adapter.md)