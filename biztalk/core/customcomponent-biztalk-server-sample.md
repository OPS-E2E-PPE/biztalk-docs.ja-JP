---
title: CustomComponent (BizTalk Server サンプル) |Microsoft Docs
ms.custom: ''
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: ''
ms.suite: ''
ms.tgt_pltfrm: ''
ms.topic: article
helpviewer_keywords:
- pipeline components [custom], examples
- examples, pipeline components [custom]
- messages, streamed
- pipeline components [custom], configuring
ms.assetid: ed0da9f5-8cc7-4528-be8c-35b80744fd38
caps.latest.revision: 13
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: 51b5d3e6f90184143b59fe8637b88352f610981b
ms.sourcegitcommit: 381e83d43796a345488d54b3f7413e11d56ad7be
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 05/07/2019
ms.locfileid: "65353263"
---
# <a name="customcomponent-biztalk-server-sample"></a><span data-ttu-id="7438d-102">CustomComponent (BizTalk Server サンプル)</span><span class="sxs-lookup"><span data-stu-id="7438d-102">CustomComponent (BizTalk Server Sample)</span></span>
<span data-ttu-id="7438d-103">CustomComponent サンプルでは、作成してストリーミングされたメッセージを変更するカスタム パイプライン コンポーネントを使用する方法を示します。</span><span class="sxs-lookup"><span data-stu-id="7438d-103">The CustomComponent sample demonstrates how to create and use a custom pipeline component that modifies a streamed message.</span></span> <span data-ttu-id="7438d-104">このサンプルでは、パイプライン デザイナーでのカスタム パイプライン コンポーネントの構成も示します。</span><span class="sxs-lookup"><span data-stu-id="7438d-104">This sample also demonstrates the configuration of a custom pipeline component in Pipeline Designer.</span></span>  

## <a name="what-this-sample-does"></a><span data-ttu-id="7438d-105">このサンプルの処理</span><span class="sxs-lookup"><span data-stu-id="7438d-105">What This Sample Does</span></span>  
 <span data-ttu-id="7438d-106">このサンプルでは、プレフィックスまたは入力メッセージに文字列を追加できるカスタム パイプライン コンポーネントを実装します。</span><span class="sxs-lookup"><span data-stu-id="7438d-106">This sample implements a custom pipeline component that can prefix or append strings to the input message.</span></span> [!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)] <span data-ttu-id="7438d-107">ストリーミング モード、メッセージ全体がメモリに読み込まれていないことを意味のメッセージを処理します。</span><span class="sxs-lookup"><span data-stu-id="7438d-107">processes the message in streaming mode, meaning that the entire message is never loaded into memory.</span></span> <span data-ttu-id="7438d-108">カスタム パイプライン コンポーネントは、次の一連の手順を使用して示されています。</span><span class="sxs-lookup"><span data-stu-id="7438d-108">The custom pipeline component is demonstrated using the following sequence of steps:</span></span>  

1. <span data-ttu-id="7438d-109">BizTalk は、特定のフォルダー内のファイルからテキスト メッセージを取得します。</span><span class="sxs-lookup"><span data-stu-id="7438d-109">BizTalk retrieves a text message from a file in a specific folder.</span></span>  

2. <span data-ttu-id="7438d-110">テキスト メッセージは、FixMsg カスタム パイプライン コンポーネントを含む受信パイプラインを通じて送信されます。</span><span class="sxs-lookup"><span data-stu-id="7438d-110">The text message is sent through a receive pipeline containing the FixMsg custom pipeline component.</span></span> <span data-ttu-id="7438d-111">メッセージの先頭に文字列を挿入するには、このコンポーネントを構成します。</span><span class="sxs-lookup"><span data-stu-id="7438d-111">You configure this component to insert a string at the beginning of the message.</span></span>  

3. <span data-ttu-id="7438d-112">FixMsg カスタム パイプライン コンポーネントで送信パイプラインを介して結果のテキスト メッセージを送信します。</span><span class="sxs-lookup"><span data-stu-id="7438d-112">You send the resulting text message through a send pipeline with the FixMsg custom pipeline component.</span></span> <span data-ttu-id="7438d-113">メッセージの末尾に文字列を追加するコンポーネントを構成するとします。</span><span class="sxs-lookup"><span data-stu-id="7438d-113">You configure the component to append a string to the end of the message.</span></span>  

4. [!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)] <span data-ttu-id="7438d-114">特定のフォルダー内のファイルにテキスト メッセージを書き込みます。</span><span class="sxs-lookup"><span data-stu-id="7438d-114">writes the resulting text message to a file in a specific folder.</span></span>  

## <a name="where-to-find-this-sample"></a><span data-ttu-id="7438d-115">このサンプルの場所</span><span class="sxs-lookup"><span data-stu-id="7438d-115">Where to Find This Sample</span></span>  
 <span data-ttu-id="7438d-116">\<*パスのサンプル*\>\Pipelines\CustomComponent\\</span><span class="sxs-lookup"><span data-stu-id="7438d-116">\<*Samples Path*\>\Pipelines\CustomComponent\\</span></span>  

 <span data-ttu-id="7438d-117">次の表は、このサンプルのファイルとその目的を示しています。</span><span class="sxs-lookup"><span data-stu-id="7438d-117">The following table shows the files in this sample and describes their purpose.</span></span>  


|                                                     <span data-ttu-id="7438d-118">ファイル</span><span class="sxs-lookup"><span data-stu-id="7438d-118">File(s)</span></span>                                                     |                                                                                              <span data-ttu-id="7438d-119">説明</span><span class="sxs-lookup"><span data-stu-id="7438d-119">Description</span></span>                                                                                               |
|-----------------------------------------------------------------------------------------------------------------|--------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------|
|                                                   <span data-ttu-id="7438d-120">Cleanup.bat</span><span class="sxs-lookup"><span data-stu-id="7438d-120">Cleanup.bat</span></span>                                                   | <span data-ttu-id="7438d-121">アセンブリを展開解除し、グローバル アセンブリ キャッシュ (GAC) から削除するために使用されます。</span><span class="sxs-lookup"><span data-stu-id="7438d-121">Used to undeploy assemblies and remove them from the global assembly cache (GAC).</span></span> <span data-ttu-id="7438d-122">送信ポートと受信ポートが削除されます。</span><span class="sxs-lookup"><span data-stu-id="7438d-122">Removes send and receive ports.</span></span> <span data-ttu-id="7438d-123">必要に応じて、Microsoft インターネット インフォメーション サービス (IIS) の仮想ディレクトリが削除されます。</span><span class="sxs-lookup"><span data-stu-id="7438d-123">Removes Microsoft Internet Information Services (IIS) virtual directories as needed.</span></span> |
|                                                    <span data-ttu-id="7438d-124">Input.txt</span><span class="sxs-lookup"><span data-stu-id="7438d-124">Input.txt</span></span>                                                    |                                                                                           <span data-ttu-id="7438d-125">サンプル入力ファイルです。</span><span class="sxs-lookup"><span data-stu-id="7438d-125">Sample input file.</span></span>                                                                                           |
|                                                    <span data-ttu-id="7438d-126">Setup.bat</span><span class="sxs-lookup"><span data-stu-id="7438d-126">Setup.bat</span></span>                                                    |                                                                               <span data-ttu-id="7438d-127">このサンプルをビルドおよび初期化するために使用されます。</span><span class="sxs-lookup"><span data-stu-id="7438d-127">Used to build and initialize this sample.</span></span>                                                                                |
|                  <span data-ttu-id="7438d-128">\FixMsg フォルダー。</span><span class="sxs-lookup"><span data-stu-id="7438d-128">In the \FixMsg folder:</span></span><br /><br /> <span data-ttu-id="7438d-129">AssemblyInfo.cs、FixMsg.csproj、FixMsg.sln</span><span class="sxs-lookup"><span data-stu-id="7438d-129">AssemblyInfo.cs, FixMsg.csproj, FixMsg.sln</span></span>                  |                                              <span data-ttu-id="7438d-130">このサンプルのカスタム パイプライン コンポーネント部分のプロジェクト、ソリューション、およびアセンブリ情報ファイルです。</span><span class="sxs-lookup"><span data-stu-id="7438d-130">Project, solution, and assembly information files for the custom pipeline component portion of this sample.</span></span>                                               |
|                                  <span data-ttu-id="7438d-131">\FixMsg フォルダー。</span><span class="sxs-lookup"><span data-stu-id="7438d-131">In the \FixMsg folder:</span></span><br /><br /> <span data-ttu-id="7438d-132">FixMsg.cs</span><span class="sxs-lookup"><span data-stu-id="7438d-132">FixMsg.cs</span></span>                                   |                                                                             <span data-ttu-id="7438d-133">パイプライン コンポーネントのインターフェイスを実装します。</span><span class="sxs-lookup"><span data-stu-id="7438d-133">Implements the pipeline component interfaces.</span></span>                                                                              |
|                               <span data-ttu-id="7438d-134">\FixMsg フォルダー。</span><span class="sxs-lookup"><span data-stu-id="7438d-134">In the \FixMsg folder:</span></span><br /><br /> <span data-ttu-id="7438d-135">FixMsgStream.cs</span><span class="sxs-lookup"><span data-stu-id="7438d-135">FixMsgStream.cs</span></span>                                |                                                      <span data-ttu-id="7438d-136">実装のラッパー、 **System.IO.Stream**クラス、データのストリーム処理を有効にします。</span><span class="sxs-lookup"><span data-stu-id="7438d-136">Implements a wrapper for the **System.IO.Stream** class, enabling stream processing of data.</span></span>                                                      |
|                             <span data-ttu-id="7438d-137">\FixMsg フォルダー。</span><span class="sxs-lookup"><span data-stu-id="7438d-137">In the \FixMsg folder:</span></span><br /><br /> <span data-ttu-id="7438d-138">FixMsgDescription.cs</span><span class="sxs-lookup"><span data-stu-id="7438d-138">FixMsgDescription.cs</span></span>                             |                                                       <span data-ttu-id="7438d-139">アクセスおよびパイプライン デザイナーでコンポーネント UI リソースをレンダリングするためのメソッドを提供します。</span><span class="sxs-lookup"><span data-stu-id="7438d-139">Provides methods for accessing and rendering component UI resources in Pipeline Designer.</span></span>                                                        |
|                                 <span data-ttu-id="7438d-140">\FixMsg フォルダー。</span><span class="sxs-lookup"><span data-stu-id="7438d-140">In the \FixMsg folder:</span></span><br /><br /> <span data-ttu-id="7438d-141">FixMsg.resx</span><span class="sxs-lookup"><span data-stu-id="7438d-141">FixMsg.resx</span></span>                                  |                                                                      <span data-ttu-id="7438d-142">プロパティの説明、アイコン、およびエラー メッセージが含まれています。</span><span class="sxs-lookup"><span data-stu-id="7438d-142">Contains property descriptions, an icon, and error messages.</span></span>                                                                      |
| <span data-ttu-id="7438d-143">\PipelineComponentSample フォルダー。</span><span class="sxs-lookup"><span data-stu-id="7438d-143">In the \PipelineComponentSample folder:</span></span><br /><br /> <span data-ttu-id="7438d-144">PipelineComponentSample.btproj、PipelineComponentSample.sln</span><span class="sxs-lookup"><span data-stu-id="7438d-144">PipelineComponentSample.btproj, PipelineComponentSample.sln</span></span> |                                                               <span data-ttu-id="7438d-145">このサンプルの BizTalk プロジェクト部分のプロジェクトおよびソリューション ファイル。</span><span class="sxs-lookup"><span data-stu-id="7438d-145">Project and solution files for the BizTalk project portion of this sample.</span></span>                                                               |
|             <span data-ttu-id="7438d-146">\PipelineComponentSample フォルダー。</span><span class="sxs-lookup"><span data-stu-id="7438d-146">In the \PipelineComponentSample folder:</span></span><br /><br /> <span data-ttu-id="7438d-147">PipelineComponentSampleBinding.xml</span><span class="sxs-lookup"><span data-stu-id="7438d-147">PipelineComponentSampleBinding.xml</span></span>              |                                                                             <span data-ttu-id="7438d-148">ポートのバインドなど、自動化されたセットアップに使用されます。</span><span class="sxs-lookup"><span data-stu-id="7438d-148">Used for automated setup such as port binding.</span></span>                                                                             |
|      <span data-ttu-id="7438d-149">\PipelineComponentSample フォルダー。</span><span class="sxs-lookup"><span data-stu-id="7438d-149">In the \PipelineComponentSample folder:</span></span><br /><br /> <span data-ttu-id="7438d-150">FixMsgReceivePipeline.btp, FixMsgSendPipeline.btp</span><span class="sxs-lookup"><span data-stu-id="7438d-150">FixMsgReceivePipeline.btp, FixMsgSendPipeline.btp</span></span>      |  [!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)] <span data-ttu-id="7438d-151">FixMsg カスタム パイプライン コンポーネントの受信パイプラインおよび送信パイプラインに対するをそれぞれ含むパイプライン。</span><span class="sxs-lookup"><span data-stu-id="7438d-151">pipelines containing the FixMsg custom pipeline component, for the receive and the send pipelines, respectively.</span></span>   |

## <a name="building-and-initializing-this-sample"></a><span data-ttu-id="7438d-152">このサンプルのビルドと初期化</span><span class="sxs-lookup"><span data-stu-id="7438d-152">Building and Initializing This Sample</span></span>  

#### <a name="to-build-and-initialize-the-customcomponent-sample"></a><span data-ttu-id="7438d-153">ビルドして初期化 CustomComponent サンプル</span><span class="sxs-lookup"><span data-stu-id="7438d-153">To build and initialize the CustomComponent sample</span></span>  

1. <span data-ttu-id="7438d-154">コマンド ウィンドウで、次のフォルダーに移動します。</span><span class="sxs-lookup"><span data-stu-id="7438d-154">In a command window, navigate to the following folder:</span></span>  

    <span data-ttu-id="7438d-155">\<*パスのサンプル*\>\Pipelines\CustomComponent</span><span class="sxs-lookup"><span data-stu-id="7438d-155">\<*Samples Path*\>\Pipelines\CustomComponent</span></span>  

2. <span data-ttu-id="7438d-156">ファイルは、次の操作を実行します。 Setup.bat を実行します。</span><span class="sxs-lookup"><span data-stu-id="7438d-156">Run the file Setup.bat, which performs the following actions:</span></span>  

   - <span data-ttu-id="7438d-157">入力 (In) フォルダと出力 (Out) フォルダーに、このサンプル用のフォルダーを作成します。</span><span class="sxs-lookup"><span data-stu-id="7438d-157">Creates the input (In) and output (Out) folders for this sample in the folder:</span></span>  

      <span data-ttu-id="7438d-158">\<*パスのサンプル*\>\Pipelines\CustomComponent</span><span class="sxs-lookup"><span data-stu-id="7438d-158">\<*Samples Path*\>\Pipelines\CustomComponent</span></span>  

   - <span data-ttu-id="7438d-159">このサンプル用に [!INCLUDE[btsVStudioNoVersion](../includes/btsvstudionoversion-md.md)] プロジェクトをコンパイルし、展開します。</span><span class="sxs-lookup"><span data-stu-id="7438d-159">Compiles and deploys the [!INCLUDE[btsVStudioNoVersion](../includes/btsvstudionoversion-md.md)] projects for this sample.</span></span>  

   - <span data-ttu-id="7438d-160">[!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)] の受信場所、送信ポート、および受信ポートを作成しバインドします。</span><span class="sxs-lookup"><span data-stu-id="7438d-160">Creates and binds the [!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)] receive location, and the send and receive ports.</span></span>  

     > [!NOTE]
     >  <span data-ttu-id="7438d-161">このサンプルは、ポートを作成してバインドする際に、以下の警告を表示します。</span><span class="sxs-lookup"><span data-stu-id="7438d-161">This sample displays the following warnings when creating and binding the ports:</span></span>  
     >   
     >  `Warning: Receive handler not specified for receive location "PCReceiveLocation"; updating with first receive handler with matching transport type.`  
     >   
     >  `Warning: Host not specified for orchestration "CustomComponent"; updating with first available host.`  
     >   
     >  <span data-ttu-id="7438d-162">これらの警告は、無視してもかまいません </span><span class="sxs-lookup"><span data-stu-id="7438d-162">You can safely ignore these warnings.</span></span> <span data-ttu-id="7438d-163">(インストールでの名前付け方法はユーザーによって異なる可能性があるため、ホスト名と受信ハンドラーはバインド ファイルから除外されています。)</span><span class="sxs-lookup"><span data-stu-id="7438d-163">(To accommodate for possible naming differences in user installations, the host name and receive handler have been omitted from the binding file.)</span></span>  

   - <span data-ttu-id="7438d-164">受信場所を有効にし、送信ポートを開始します。</span><span class="sxs-lookup"><span data-stu-id="7438d-164">Enables the receive location, and starts the send port.</span></span>  

> [!NOTE]
>  <span data-ttu-id="7438d-165">このサンプルを実行する前に、ビルドと初期化のプロセス中に [!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)] でエラーが報告されていないことを確認する必要があります。</span><span class="sxs-lookup"><span data-stu-id="7438d-165">You should confirm that [!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)] did not report any errors during the build and initialization process before attempting to run this sample.</span></span>  
> 
> [!NOTE]
>  <span data-ttu-id="7438d-166">開き、Setup.bat ファイルを実行することがなくこのサンプルでは、プロジェクトをビルドする場合は、まず、.NET Framework の厳密名ユーティリティ (sn.exe) を使用して厳密な名前キーのペアを作成する必要があります。</span><span class="sxs-lookup"><span data-stu-id="7438d-166">If you choose to open and build the projects in this sample without running the file Setup.bat, you must first create a strong name key pair using the .NET Framework Strong Name utility (sn.exe).</span></span> <span data-ttu-id="7438d-167">このキー ペアが結果として得られるアセンブリの署名に使用されるを使用します。</span><span class="sxs-lookup"><span data-stu-id="7438d-167">Use this key pair is used to sign the resulting assemblies.</span></span>  
> 
> [!NOTE]
>  <span data-ttu-id="7438d-168">Setup.bat による変更を元に戻したりするにはまず停止してから、ホスト インスタンスを再起動、[!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)]管理 MMC コンソール。</span><span class="sxs-lookup"><span data-stu-id="7438d-168">To undo changes made by Setup.bat, you must first stop and restart the host instance from the [!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)] Administration MMC console.</span></span> <span data-ttu-id="7438d-169">次に、Cleanup.bat を実行します。</span><span class="sxs-lookup"><span data-stu-id="7438d-169">Next, run Cleanup.bat.</span></span> <span data-ttu-id="7438d-170">Setup.bat を 2 回目に実行する場合は、その前に Cleanup.bat を実行してください。</span><span class="sxs-lookup"><span data-stu-id="7438d-170">You must run Cleanup.bat before running Setup.bat a second time.</span></span>  

## <a name="running-this-sample"></a><span data-ttu-id="7438d-171">このサンプルの実行</span><span class="sxs-lookup"><span data-stu-id="7438d-171">Running This Sample</span></span>  

#### <a name="to-run-the-customcomponent-sample"></a><span data-ttu-id="7438d-172">CustomComponent サンプルを実行するには</span><span class="sxs-lookup"><span data-stu-id="7438d-172">To run the CustomComponent sample</span></span>  

1.  <span data-ttu-id="7438d-173">テキストのコピーでは、Input.txt をファイルのフォルダーに貼り付けます。</span><span class="sxs-lookup"><span data-stu-id="7438d-173">Paste a copy of the text file Input.txt into the folder In.</span></span>  

2.  <span data-ttu-id="7438d-174">テキスト ファイルが Out フォルダに作成されたことを確認します。このファイルには、(受信パイプライン) を先頭に、(送信パイプライン) によって最後に挿入される追加のテキスト ファイル Input.txt の内容が含まれています。</span><span class="sxs-lookup"><span data-stu-id="7438d-174">Observe the text file created in the folder Out. This file contains the contents of the file Input.txt with additional text inserted at the beginning (by the receive pipeline) and at the end (by the send pipeline).</span></span> <span data-ttu-id="7438d-175">このファイルの名前の形式が\< *MessageID*\>、.xml、 *\<MessageID\>* メッセージを一意に識別するために生成される GUID.</span><span class="sxs-lookup"><span data-stu-id="7438d-175">The format of the name of this file is \<*MessageID*\>.xml, where *\<MessageID\>* is the GUID generated to uniquely identify the message.</span></span>  

## <a name="comments"></a><span data-ttu-id="7438d-176">コメント</span><span class="sxs-lookup"><span data-stu-id="7438d-176">Comments</span></span>  
 <span data-ttu-id="7438d-177">次の手順に従って、パイプライン デザイナーで構成済みのパイプラインを表示できます。</span><span class="sxs-lookup"><span data-stu-id="7438d-177">You can view the preconfigured pipelines in Pipeline Designer by following these steps:</span></span>  

1.  <span data-ttu-id="7438d-178">ソリューション エクスプ ローラーで、パイプライン デザイナーで、受信パイプラインを開く ReceivePipeline.btp をダブルクリックします。</span><span class="sxs-lookup"><span data-stu-id="7438d-178">In Solution Explorer, double-click ReceivePipeline.btp to open the receive pipeline in Pipeline Designer.</span></span> <span data-ttu-id="7438d-179">FixMsg コンポーネントが内に配置されるかを確認、**検証**受信パイプラインのステージ。</span><span class="sxs-lookup"><span data-stu-id="7438d-179">Observe that the FixMsg component is placed in the **Validate** stage of the receive pipeline.</span></span>  

2.  <span data-ttu-id="7438d-180">内の FixMsg コンポーネントをクリックして、**検証**デザイン サーフェイス上のステージ。</span><span class="sxs-lookup"><span data-stu-id="7438d-180">Click the FixMsg component in the **Validate** stage on the design surface.</span></span> <span data-ttu-id="7438d-181">[プロパティ] ウィンドウで、パイプライン コンポーネントの構成プロパティを確認できます。</span><span class="sxs-lookup"><span data-stu-id="7438d-181">In the Properties window, you can see the configuration properties of the pipeline component.</span></span> <span data-ttu-id="7438d-182">観察、 **PrependData**プロパティに設定されて**受信パイプライン文字列の前に追加するデータ**します。</span><span class="sxs-lookup"><span data-stu-id="7438d-182">Observe that the **PrependData** property is set to **Data to prepend in receive pipeline string**.</span></span>  

3.  <span data-ttu-id="7438d-183">ソリューション エクスプローラで、パイプライン デザイナーで、送信パイプラインを開く SendPipeline.btp をダブルクリックします。</span><span class="sxs-lookup"><span data-stu-id="7438d-183">In Solution Explorer, double-click SendPipeline.btp to open the send pipeline in Pipeline Designer.</span></span> <span data-ttu-id="7438d-184">FixMsg コンポーネントが内に配置されるかを確認、**プリアセンブル**送信パイプラインのステージ。</span><span class="sxs-lookup"><span data-stu-id="7438d-184">Observe that the FixMsg component is placed in the **Pre-Assemble** stage of the send pipeline.</span></span>  

4.  <span data-ttu-id="7438d-185">内の FixMsg コンポーネントをクリックします。**プリアセンブル**デザイン サーフェイス上のステージ。</span><span class="sxs-lookup"><span data-stu-id="7438d-185">Click the FixMsg component in **Pre-Assemble** stage on the design surface.</span></span> <span data-ttu-id="7438d-186">なお、 **AppendData**プロパティに設定されて**送信パイプライン文字列の後に追加するデータ**します。</span><span class="sxs-lookup"><span data-stu-id="7438d-186">Note that the **AppendData** property is set to **Data to append in send pipeline string**.</span></span>  

## <a name="see-also"></a><span data-ttu-id="7438d-187">参照</span><span class="sxs-lookup"><span data-stu-id="7438d-187">See Also</span></span>  
 [<span data-ttu-id="7438d-188">パイプライン (BizTalk Server Samples フォルダー)</span><span class="sxs-lookup"><span data-stu-id="7438d-188">Pipelines (BizTalk Server Samples Folder)</span></span>](../core/pipelines-biztalk-server-samples-folder.md)