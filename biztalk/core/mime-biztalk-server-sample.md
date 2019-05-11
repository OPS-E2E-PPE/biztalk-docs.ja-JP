---
title: MIME (BizTalk Server サンプル) |Microsoft Docs
ms.custom: ''
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: ''
ms.suite: ''
ms.tgt_pltfrm: ''
ms.topic: article
helpviewer_keywords:
- send pipelines, MIME/SMIME Encoder [pipeline component]
- examples, send pipelines
- MIME/SMIME Encoder [pipeline component], send pipelines
- MIME/SMIME Encoder [pipeline component], examples
- examples, MIME/SMIME Encoder [pipeline component]
ms.assetid: f76c720d-3798-4f15-a5f9-885ddf421d57
caps.latest.revision: 13
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: b4ea6cfa8f2d6b4c94f1e48531167688901132cb
ms.sourcegitcommit: d27732e569b0897361dfaebca8352aa97bb7efe1
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 05/10/2019
ms.locfileid: "65527568"
---
# <a name="mime-biztalk-server-sample"></a><span data-ttu-id="728ef-102">MIME (BizTalk Server サンプル)</span><span class="sxs-lookup"><span data-stu-id="728ef-102">MIME (BizTalk Server Sample)</span></span>
<span data-ttu-id="728ef-103">MIME サンプルは、MIME エンコードの送信パイプライン内でを実行する方法を示します。</span><span class="sxs-lookup"><span data-stu-id="728ef-103">The MIME sample demonstrates how to perform MIME encoding within a send pipeline.</span></span>  

## <a name="what-this-sample-does"></a><span data-ttu-id="728ef-104">このサンプルの処理</span><span class="sxs-lookup"><span data-stu-id="728ef-104">What This Sample Does</span></span>  
 <span data-ttu-id="728ef-105">このサンプルでは、受信場所として、MIMEIn フォルダを構成します。</span><span class="sxs-lookup"><span data-stu-id="728ef-105">This sample configures the folder MIMEIn as a receive location.</span></span> <span data-ttu-id="728ef-106">サンプル ファイル ImageInput.gif、このフォルダーにファイルを配置すると、[!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)]次の手順を使用してこのファイルにメッセージを処理します。</span><span class="sxs-lookup"><span data-stu-id="728ef-106">When you place a file, such as the sample file ImageInput.gif, in this folder, [!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)] processes the message in this file using the following steps:</span></span>  

1.  <span data-ttu-id="728ef-107">受信場所フォルダ MIMEIn からメッセージ ファイルを取得します。</span><span class="sxs-lookup"><span data-stu-id="728ef-107">Retrieve the message file from the receive location folder MIMEIn.</span></span>  

2.  <span data-ttu-id="728ef-108">受信パイプラインでメッセージをそのまま渡します。</span><span class="sxs-lookup"><span data-stu-id="728ef-108">In the receive pipeline, pass the message through unchanged.</span></span>  

3.  <span data-ttu-id="728ef-109">メッセージ ボックス データベースには、送信パイプラインにメッセージをルーティングします。</span><span class="sxs-lookup"><span data-stu-id="728ef-109">In the MessageBox database, route the message to the send pipeline.</span></span>  

4.  <span data-ttu-id="728ef-110">送信パイプラインで MIME エンコードの実行し、送信アダプタ フォルダ MIMEOut にファイルを配置します。</span><span class="sxs-lookup"><span data-stu-id="728ef-110">In the send pipeline, perform MIME encoding and place the file into the send adapter folder MIMEOut.</span></span>  

## <a name="where-to-find-this-sample"></a><span data-ttu-id="728ef-111">このサンプルの場所</span><span class="sxs-lookup"><span data-stu-id="728ef-111">Where to Find This Sample</span></span>  
 <span data-ttu-id="728ef-112">\<*パスのサンプル*\>\Pipelines\MIME\\</span><span class="sxs-lookup"><span data-stu-id="728ef-112">\<*Samples Path*\>\Pipelines\MIME\\</span></span>  

 <span data-ttu-id="728ef-113">次の表は、このサンプルのファイルとその目的を示しています。</span><span class="sxs-lookup"><span data-stu-id="728ef-113">The following table shows the files in this sample and describes their purpose.</span></span>  


|                           <span data-ttu-id="728ef-114">ファイル</span><span class="sxs-lookup"><span data-stu-id="728ef-114">File(s)</span></span>                            |                                                                                              <span data-ttu-id="728ef-115">説明</span><span class="sxs-lookup"><span data-stu-id="728ef-115">Description</span></span>                                                                                               |
|--------------------------------------------------------------|--------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------|
|                         <span data-ttu-id="728ef-116">Cleanup.bat</span><span class="sxs-lookup"><span data-stu-id="728ef-116">Cleanup.bat</span></span>                          | <span data-ttu-id="728ef-117">アセンブリを展開解除し、グローバル アセンブリ キャッシュ (GAC) から削除するために使用されます。</span><span class="sxs-lookup"><span data-stu-id="728ef-117">Used to undeploy assemblies and remove them from the global assembly cache (GAC).</span></span> <span data-ttu-id="728ef-118">送信ポートと受信ポートが削除されます。</span><span class="sxs-lookup"><span data-stu-id="728ef-118">Removes send and receive ports.</span></span> <span data-ttu-id="728ef-119">必要に応じて、Microsoft インターネット インフォメーション サービス (IIS) の仮想ディレクトリが削除されます。</span><span class="sxs-lookup"><span data-stu-id="728ef-119">Removes Microsoft Internet Information Services (IIS) virtual directories as needed.</span></span> |
|                        <span data-ttu-id="728ef-120">ImageInput.GIF</span><span class="sxs-lookup"><span data-stu-id="728ef-120">ImageInput.GIF</span></span>                        |                                                                                           <span data-ttu-id="728ef-121">サンプル入力ファイルです。</span><span class="sxs-lookup"><span data-stu-id="728ef-121">Sample input file.</span></span>                                                                                           |
| <span data-ttu-id="728ef-122">SampleMimeEncoding.btproj</span><span class="sxs-lookup"><span data-stu-id="728ef-122">SampleMimeEncoding.btproj</span></span><br /><br /> <span data-ttu-id="728ef-123">SampleMimeEncoding.sln</span><span class="sxs-lookup"><span data-stu-id="728ef-123">SampleMimeEncoding.sln</span></span> |                                                                              <span data-ttu-id="728ef-124">このサンプルのプロジェクト ファイルとソリューション ファイルです。</span><span class="sxs-lookup"><span data-stu-id="728ef-124">Project and solution files for this sample.</span></span>                                                                               |
|                <span data-ttu-id="728ef-125">SampleMimeEncodingBinding.xml</span><span class="sxs-lookup"><span data-stu-id="728ef-125">SampleMimeEncodingBinding.xml</span></span>                 |                                                                             <span data-ttu-id="728ef-126">ポートのバインドなど、自動化されたセットアップに使用されます。</span><span class="sxs-lookup"><span data-stu-id="728ef-126">Used for automated setup such as port binding.</span></span>                                                                             |
|                     <span data-ttu-id="728ef-127">SendMimePipeline.btp</span><span class="sxs-lookup"><span data-stu-id="728ef-127">SendMimePipeline.btp</span></span>                     |                                 [!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)] <span data-ttu-id="728ef-128">MIME エンコーダー コンポーネントとパイプライン ファイルを送信します。</span><span class="sxs-lookup"><span data-stu-id="728ef-128">send pipeline file with the MIME Encoder component.</span></span>                                 |
|                          <span data-ttu-id="728ef-129">Setup.bat</span><span class="sxs-lookup"><span data-stu-id="728ef-129">Setup.bat</span></span>                           |                                                                               <span data-ttu-id="728ef-130">このサンプルをビルドおよび初期化するために使用されます。</span><span class="sxs-lookup"><span data-stu-id="728ef-130">Used to build and initialize this sample.</span></span>                                                                                |

## <a name="building-and-initializing-this-sample"></a><span data-ttu-id="728ef-131">このサンプルのビルドと初期化</span><span class="sxs-lookup"><span data-stu-id="728ef-131">Building and Initializing This Sample</span></span>  
 <span data-ttu-id="728ef-132">次の手順を使用して、ビルドして、MIME サンプルを初期化します。</span><span class="sxs-lookup"><span data-stu-id="728ef-132">Use the following procedure to build and initialize the MIME sample.</span></span>  

#### <a name="to-build-and-initialize-this-sample"></a><span data-ttu-id="728ef-133">このサンプルを作成および初期化するには</span><span class="sxs-lookup"><span data-stu-id="728ef-133">To build and initialize this sample</span></span>  

1. <span data-ttu-id="728ef-134">コマンド ウィンドウで、次のフォルダーに移動します。</span><span class="sxs-lookup"><span data-stu-id="728ef-134">In a command window, navigate to the following folder:</span></span>  

    <span data-ttu-id="728ef-135">\<*パスのサンプル*\>\Pipelines\MIME</span><span class="sxs-lookup"><span data-stu-id="728ef-135">\<*Samples Path*\>\Pipelines\MIME</span></span>  

2. <span data-ttu-id="728ef-136">ファイルは、次の操作を実行します。 Setup.bat を実行します。</span><span class="sxs-lookup"><span data-stu-id="728ef-136">Run the file Setup.bat, which performs the following actions:</span></span>  

   - <span data-ttu-id="728ef-137">フォルダーには、入力 (mimein フォルダ) とこのサンプルの出力 (MIMEOut) フォルダを作成します。</span><span class="sxs-lookup"><span data-stu-id="728ef-137">Creates the input (MIMEIn) and output (MIMEOut) folders for this sample in the folder:</span></span>  

      <span data-ttu-id="728ef-138">\<*パスのサンプル*\>\Pipelines\MIME</span><span class="sxs-lookup"><span data-stu-id="728ef-138">\<*Samples Path*\>\Pipelines\MIME</span></span>  

   - <span data-ttu-id="728ef-139">コンパイル、[!INCLUDE[btsVStudioNoVersion](../includes/btsvstudionoversion-md.md)]このサンプルのプロジェクト。</span><span class="sxs-lookup"><span data-stu-id="728ef-139">Compiles the [!INCLUDE[btsVStudioNoVersion](../includes/btsvstudionoversion-md.md)] project for this sample.</span></span>  

   - <span data-ttu-id="728ef-140">[!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)] の受信場所、送信ポート、および受信ポートを作成しバインドします。</span><span class="sxs-lookup"><span data-stu-id="728ef-140">Creates and binds the [!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)] receive location, and the send and receive ports.</span></span>  

     > [!NOTE]
     >  <span data-ttu-id="728ef-141">このサンプルでは、作成してポートをバインドするときに、次の警告が表示されます。</span><span class="sxs-lookup"><span data-stu-id="728ef-141">This sample displays the following warning when creating and binding the ports:</span></span>  

     > [!NOTE]
     >  `Warning: Receive handler not specified for receive location "MIMEReceiveLocation"; updating with first receive handler with matching transport type.`  

     > [!NOTE]
     >  <span data-ttu-id="728ef-142">これらの警告は、無視してもかまいません </span><span class="sxs-lookup"><span data-stu-id="728ef-142">You can safely ignore these warnings.</span></span> <span data-ttu-id="728ef-143">(インストールでの名前付け方法はユーザーによって異なる可能性があるため、ホスト名と受信ハンドラーはバインド ファイルから除外されています。)</span><span class="sxs-lookup"><span data-stu-id="728ef-143">(To accommodate for possible naming differences in user installations, the host name and receive handler have been omitted from the binding file.)</span></span>  

   - <span data-ttu-id="728ef-144">受信場所を有効にし、送信ポートを開始します。</span><span class="sxs-lookup"><span data-stu-id="728ef-144">Enables the receive location, and starts the send port.</span></span>  

> [!NOTE]
>  <span data-ttu-id="728ef-145">参照を追加する必要があります最初がインストールされている別の場所からこのサンプルを実行する場合、 **Microsoft.BizTalk.Pipeline.Components**アセンブリ。</span><span class="sxs-lookup"><span data-stu-id="728ef-145">If you run this sample from a location other than where it is installed, you must first add a reference to the **Microsoft.BizTalk.Pipeline.Components** assembly.</span></span>  
> 
> [!NOTE]
>  <span data-ttu-id="728ef-146">このサンプルを実行する前に、ビルドと初期化のプロセス中に [!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)] でエラーが報告されていないことを確認する必要があります。</span><span class="sxs-lookup"><span data-stu-id="728ef-146">You should confirm that [!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)] did not report any errors during the build and initialization process before attempting to run this sample.</span></span>  
> 
> [!NOTE]
>  <span data-ttu-id="728ef-147">開き、Setup.bat ファイルを実行することがなくこのサンプルでは、プロジェクトをビルドする場合は、まず、.NET Framework の厳密名ユーティリティ (sn.exe) を使用して厳密な名前キーのペアを作成する必要があります。</span><span class="sxs-lookup"><span data-stu-id="728ef-147">If you choose to open and build the project in this sample without running the file Setup.bat, you must first create a strong name key pair using the .NET Framework Strong Name utility (sn.exe).</span></span> <span data-ttu-id="728ef-148">結果として得られるアセンブリに署名するのにには、このキー ペアを使用します。</span><span class="sxs-lookup"><span data-stu-id="728ef-148">Use this key pair to sign the resulting assembly.</span></span> <span data-ttu-id="728ef-149">Setup.bat によって行われた変更を元に戻すには、Cleanup.bat を実行します。</span><span class="sxs-lookup"><span data-stu-id="728ef-149">To undo changes made by Setup.bat, run Cleanup.bat.</span></span> <span data-ttu-id="728ef-150">Setup.bat を 2 回目に実行する場合は、その前に Cleanup.bat を実行してください。</span><span class="sxs-lookup"><span data-stu-id="728ef-150">You must run Cleanup.bat before running Setup.bat a second time.</span></span>  

## <a name="running-this-sample"></a><span data-ttu-id="728ef-151">このサンプルの実行</span><span class="sxs-lookup"><span data-stu-id="728ef-151">Running This Sample</span></span>  
 <span data-ttu-id="728ef-152">MIME サンプルを実行するのにには、次の手順を使用します。</span><span class="sxs-lookup"><span data-stu-id="728ef-152">Use the following procedure to run the MIME sample.</span></span>  

#### <a name="to-run-this-sample"></a><span data-ttu-id="728ef-153">このサンプルを実行するには</span><span class="sxs-lookup"><span data-stu-id="728ef-153">To run this sample</span></span>  

1.  <span data-ttu-id="728ef-154">ファイル ImageInput.gif のコピーを MIMEIn フォルダに配置します。</span><span class="sxs-lookup"><span data-stu-id="728ef-154">Put a copy of the file ImageInput.gif into the folder MIMEIn.</span></span>  

2.  <span data-ttu-id="728ef-155">テキスト ファイルが MIMEOut フォルダに作成を確認します。</span><span class="sxs-lookup"><span data-stu-id="728ef-155">Observe the text file created in the folder MIMEOut.</span></span> <span data-ttu-id="728ef-156">このテキスト ファイルの名前は、メッセージ ID の GUID に基づきます。</span><span class="sxs-lookup"><span data-stu-id="728ef-156">The name of this text file is based on the message ID GUID.</span></span> <span data-ttu-id="728ef-157">このファイルには、入力ファイル ImageInput.gif の MIME でエンコードされたコンテンツが含まれています。</span><span class="sxs-lookup"><span data-stu-id="728ef-157">This file contains MIME-encoded content of the input file ImageInput.gif.</span></span>  

## <a name="see-also"></a><span data-ttu-id="728ef-158">参照</span><span class="sxs-lookup"><span data-stu-id="728ef-158">See Also</span></span>  
 [<span data-ttu-id="728ef-159">パイプライン (BizTalk Server Samples フォルダー)</span><span class="sxs-lookup"><span data-stu-id="728ef-159">Pipelines (BizTalk Server Samples Folder)</span></span>](../core/pipelines-biztalk-server-samples-folder.md)