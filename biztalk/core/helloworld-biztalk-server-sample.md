---
title: "HelloWorld (BizTalk Server サンプル) |Microsoft ドキュメント"
ms.custom: 
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: 
ms.suite: 
ms.tgt_pltfrm: 
ms.topic: article
helpviewer_keywords:
- orchestrations, examples
- examples, orchestrations
- orchestrations, messages
ms.assetid: 4416029a-ca76-45a4-b66c-b44cb71ded58
caps.latest.revision: "19"
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: 5a5e8057837012d27a877117a169c2cd04fa3d8d
ms.sourcegitcommit: cb908c540d8f1a692d01dc8f313e16cb4b4e696d
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 09/20/2017
---
# <a name="helloworld-biztalk-server-sample"></a><span data-ttu-id="51ae4-102">HelloWorld (BizTalk Server サンプル)</span><span class="sxs-lookup"><span data-stu-id="51ae4-102">HelloWorld (BizTalk Server Sample)</span></span>
<span data-ttu-id="51ae4-103">HelloWorld サンプルは、BizTalk オーケストレーションを使用して、XML メッセージ (注文書) を関連する別の種類のメッセージ (請求書) に変換する方法を示すものです。</span><span class="sxs-lookup"><span data-stu-id="51ae4-103">The HelloWorld sample demonstrates how to use BizTalk orchestrations to convert an XML message (a purchase order) into a related, but distinct, type of message (an invoice).</span></span>  
  
## <a name="what-this-sample-does"></a><span data-ttu-id="51ae4-104">このサンプルの処理</span><span class="sxs-lookup"><span data-stu-id="51ae4-104">What This Sample Does</span></span>  
 <span data-ttu-id="51ae4-105">このサンプルでは構成、**で**受信場所としてフォルダーです。</span><span class="sxs-lookup"><span data-stu-id="51ae4-105">This sample configures the **In** folder as a receive location.</span></span> <span data-ttu-id="51ae4-106">サンプル ファイルなど、ファイルを配置するときに**SamplePOInput.xml**をこのフォルダーに[!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)]を次の手順を使用してメッセージを処理します。</span><span class="sxs-lookup"><span data-stu-id="51ae4-106">When you place a file, such as the sample file **SamplePOInput.xml**, into this folder, [!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)] processes the message using the following steps:</span></span>  
  
1.  [!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)]<span data-ttu-id="51ae4-107"> は受信場所フォルダーから XML 注文書メッセージを取得します。</span><span class="sxs-lookup"><span data-stu-id="51ae4-107"> retrieves the XML purchase order message from the receive location folder.</span></span>  
  
2.  <span data-ttu-id="51ae4-108">オーケストレーションで、マップ ファイルを使用して XML 注文書から XML 請求書を作成します。</span><span class="sxs-lookup"><span data-stu-id="51ae4-108">The orchestration uses the map file to create an XML invoice from the XML purchase order.</span></span>  
  
3.  [!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)]<span data-ttu-id="51ae4-109">送信アダプターに、結果の XML 請求書メッセージを配置**アウト**フォルダーです。</span><span class="sxs-lookup"><span data-stu-id="51ae4-109"> places the resulting XML invoice message into the send adapter **Out** folder.</span></span>  
  
## <a name="how-this-sample-is-designed-and-why"></a><span data-ttu-id="51ae4-110">このサンプルのデザイン方法とその理由</span><span class="sxs-lookup"><span data-stu-id="51ae4-110">How This Sample is Designed and Why</span></span>  
 <span data-ttu-id="51ae4-111">企業間のメッセージ交換シナリオでは、取引先から受信した受信メッセージを内部アプリケーションが認識できる形式に変換する作業が必要になる場合があります。</span><span class="sxs-lookup"><span data-stu-id="51ae4-111">In an intercompany message-exchange scenario, it is often necessary to convert inbound messages received from trading partners into a format that internal applications can recognize.</span></span> <span data-ttu-id="51ae4-112">このサンプルでは、**受信**図形、**変換**図形、および**送信**この結果を実現するために図形。</span><span class="sxs-lookup"><span data-stu-id="51ae4-112">This sample uses a **Receive** shape, a **Transform** shape, and a **Send** shape to achieve this result.</span></span> <span data-ttu-id="51ae4-113">**変換**図形がメッセージ形式の変換が発生したために、このサンプルで重要な役割を果たします。</span><span class="sxs-lookup"><span data-stu-id="51ae4-113">The **Transform** shape plays the important role in this sample because it is where the message format conversion occurs.</span></span> <span data-ttu-id="51ae4-114">ドラッグする、**変換**をオーケストレーションに図形し、の送信元メッセージ、マップ名、および送信先メッセージを構成します。</span><span class="sxs-lookup"><span data-stu-id="51ae4-114">You drag a **Transform** shape into your orchestration and configure the source message, map name, and destination message for it.</span></span> <span data-ttu-id="51ae4-115">実行中、指定したマップによって送信元メッセージが送信先メッセージにマップされます。</span><span class="sxs-lookup"><span data-stu-id="51ae4-115">During run time, the source message is mapped to the destination message by using the map you designated.</span></span>  
  
 <span data-ttu-id="51ae4-116">詳細については、**変換**図形は、「[変換図形を構成する方法](../core/how-to-configure-the-transform-shape.md)です。</span><span class="sxs-lookup"><span data-stu-id="51ae4-116">For more information about the **Transform** shape, see [How to Configure the Transform Shape](../core/how-to-configure-the-transform-shape.md).</span></span> <span data-ttu-id="51ae4-117">マップのビルドの詳細については、次を参照してください。 [BizTalk マッパーを使用してマップを作成する](../core/creating-maps-using-biztalk-mapper.md)です。</span><span class="sxs-lookup"><span data-stu-id="51ae4-117">For more information about building a map, see [Creating Maps Using BizTalk Mapper](../core/creating-maps-using-biztalk-mapper.md).</span></span>  
  
## <a name="where-to-find-this-sample"></a><span data-ttu-id="51ae4-118">このサンプルの場所</span><span class="sxs-lookup"><span data-stu-id="51ae4-118">Where to Find This Sample</span></span>  
 <span data-ttu-id="51ae4-119">\<*パスのサンプル*> \Orchestrations\HelloWorld\\</span><span class="sxs-lookup"><span data-stu-id="51ae4-119">\<*Samples Path*>\Orchestrations\HelloWorld\\</span></span>  
  
 <span data-ttu-id="51ae4-120">次の表は、このサンプルのファイルとその目的を示しています。</span><span class="sxs-lookup"><span data-stu-id="51ae4-120">The following table shows the files in this sample and describes their purpose.</span></span>  
  
|<span data-ttu-id="51ae4-121">ファイル</span><span class="sxs-lookup"><span data-stu-id="51ae4-121">File(s)</span></span>|<span data-ttu-id="51ae4-122">Description</span><span class="sxs-lookup"><span data-stu-id="51ae4-122">Description</span></span>|  
|---------------|-----------------|  
|<span data-ttu-id="51ae4-123">Cleanup.bat</span><span class="sxs-lookup"><span data-stu-id="51ae4-123">Cleanup.bat</span></span>|<span data-ttu-id="51ae4-124">アセンブリの展開を解除し、グローバル アセンブリ キャッシュからアセンブリを削除するために使用されます。</span><span class="sxs-lookup"><span data-stu-id="51ae4-124">Used to undeploy assemblies and remove them from the global assembly cache.</span></span> <span data-ttu-id="51ae4-125">送信ポートと受信ポートが削除されます。</span><span class="sxs-lookup"><span data-stu-id="51ae4-125">Removes send and receive ports.</span></span> <span data-ttu-id="51ae4-126">必要に応じて、Microsoft インターネット インフォメーション サービス (IIS) の仮想ディレクトリが削除されます。</span><span class="sxs-lookup"><span data-stu-id="51ae4-126">Removes Microsoft Internet Information Services (IIS) virtual directories as needed.</span></span>|  
|<span data-ttu-id="51ae4-127">HelloOrchestration.odx</span><span class="sxs-lookup"><span data-stu-id="51ae4-127">HelloOrchestration.odx</span></span>|<span data-ttu-id="51ae4-128">注文書から請求書への変換を行うオーケストレーションです。</span><span class="sxs-lookup"><span data-stu-id="51ae4-128">Orchestration that coordinates the conversion of the purchase order into an invoice.</span></span>|  
|<span data-ttu-id="51ae4-129">HelloWorld.btproj、HelloWorld.sln</span><span class="sxs-lookup"><span data-stu-id="51ae4-129">HelloWorld.btproj, HelloWorld.sln</span></span>|<span data-ttu-id="51ae4-130">このサンプルのプロジェクト ファイルとソリューション ファイルです。</span><span class="sxs-lookup"><span data-stu-id="51ae4-130">Project and solution files for this sample.</span></span>|  
|<span data-ttu-id="51ae4-131">HelloWorldBinding.xml</span><span class="sxs-lookup"><span data-stu-id="51ae4-131">HelloWorldBinding.xml</span></span>|<span data-ttu-id="51ae4-132">ポートのバインドなど、自動化されたセットアップに使用されます。</span><span class="sxs-lookup"><span data-stu-id="51ae4-132">Used for automated setup such as port binding.</span></span>|  
|<span data-ttu-id="51ae4-133">InvoiceSchema.xsd、POSchema.xsd</span><span class="sxs-lookup"><span data-stu-id="51ae4-133">InvoiceSchema.xsd, POSchema.xsd</span></span>|<span data-ttu-id="51ae4-134">それぞれ、請求書メッセージと注文書メッセージのスキーマです。</span><span class="sxs-lookup"><span data-stu-id="51ae4-134">Schemas for the invoice and purchase order messages, respectively.</span></span>|  
|<span data-ttu-id="51ae4-135">POToInvoice.btm</span><span class="sxs-lookup"><span data-stu-id="51ae4-135">POToInvoice.btm</span></span>|<span data-ttu-id="51ae4-136">注文書を請求書に変換するためのマップです。</span><span class="sxs-lookup"><span data-stu-id="51ae4-136">Map for converting the purchase order to an invoice.</span></span>|  
|<span data-ttu-id="51ae4-137">SamplePOInput.xml</span><span class="sxs-lookup"><span data-stu-id="51ae4-137">SamplePOInput.xml</span></span>|<span data-ttu-id="51ae4-138">サンプル入力ファイルです。</span><span class="sxs-lookup"><span data-stu-id="51ae4-138">Sample input file.</span></span>|  
|<span data-ttu-id="51ae4-139">Setup.bat</span><span class="sxs-lookup"><span data-stu-id="51ae4-139">Setup.bat</span></span>|<span data-ttu-id="51ae4-140">このサンプルをビルドおよび初期化するために使用されます。</span><span class="sxs-lookup"><span data-stu-id="51ae4-140">Used to build and initialize this sample.</span></span>|  
  
## <a name="building-and-initializing-this-sample"></a><span data-ttu-id="51ae4-141">このサンプルのビルドと初期化</span><span class="sxs-lookup"><span data-stu-id="51ae4-141">Building and Initializing This Sample</span></span>  
  
#### <a name="to-build-and-initialize-the-helloworld-sample"></a><span data-ttu-id="51ae4-142">HelloWorld サンプルをビルドおよび初期化するには</span><span class="sxs-lookup"><span data-stu-id="51ae4-142">To build and initialize the HelloWorld sample</span></span>  
  
1.  <span data-ttu-id="51ae4-143">コマンド ウィンドウで、次のフォルダーに移動します。</span><span class="sxs-lookup"><span data-stu-id="51ae4-143">In a command window, navigate to the following folder:</span></span>  
  
     <span data-ttu-id="51ae4-144">\<*パスのサンプル*> \Orchestrations\HelloWorld</span><span class="sxs-lookup"><span data-stu-id="51ae4-144">\<*Samples Path*>\Orchestrations\HelloWorld</span></span>  
  
2.  <span data-ttu-id="51ae4-145">次の操作を実行する Setup.bat ファイルを実行します。</span><span class="sxs-lookup"><span data-stu-id="51ae4-145">Run the file Setup.bat, which performs the following actions:</span></span>  
  
    -   <span data-ttu-id="51ae4-146">次のフォルダに、このサンプルの入力 (In) フォルダと出力 (Out) フォルダを作成します。</span><span class="sxs-lookup"><span data-stu-id="51ae4-146">Creates the input (In) and output (Out) folders for this sample in the following folder:</span></span>  
  
         <span data-ttu-id="51ae4-147">\<*パスのサンプル*> \Orchestrations\HelloWorld</span><span class="sxs-lookup"><span data-stu-id="51ae4-147">\<*Samples Path*>\Orchestrations\HelloWorld</span></span>  
  
    -   <span data-ttu-id="51ae4-148">コンパイル、[!INCLUDE[btsVStudioNoVersion](../includes/btsvstudionoversion-md.md)]このサンプルのプロジェクトです。</span><span class="sxs-lookup"><span data-stu-id="51ae4-148">Compiles the [!INCLUDE[btsVStudioNoVersion](../includes/btsvstudionoversion-md.md)] project for this sample.</span></span>  
  
    -   <span data-ttu-id="51ae4-149">[!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)] 受信場所と、オーケストレーションの送信ポートおよび受信ポートを作成しバインドします。</span><span class="sxs-lookup"><span data-stu-id="51ae4-149">Creates and binds the [!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)] receive location, and the send and receive ports to the orchestration.</span></span>  
  
    -   <span data-ttu-id="51ae4-150">受信場所を有効にし、送信ポートを開始します。</span><span class="sxs-lookup"><span data-stu-id="51ae4-150">Enables the receive location, and starts the send port.</span></span> <span data-ttu-id="51ae4-151">オーケストレーションを参加させ、開始します。</span><span class="sxs-lookup"><span data-stu-id="51ae4-151">Enlists and starts orchestration.</span></span>  
  
> [!NOTE]
>  <span data-ttu-id="51ae4-152">このサンプルを実行する前に、ビルドと初期化のプロセス中に [!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)] でエラーが報告されていないことを確認する必要があります。</span><span class="sxs-lookup"><span data-stu-id="51ae4-152">You should confirm that [!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)] did not report any errors during the build and initialization process before attempting to run this sample.</span></span> <span data-ttu-id="51ae4-153">これはイベント ログで確認できます。</span><span class="sxs-lookup"><span data-stu-id="51ae4-153">You can confirm this by viewing your event logs.</span></span>  
  
## <a name="running-this-sample"></a><span data-ttu-id="51ae4-154">このサンプルの実行</span><span class="sxs-lookup"><span data-stu-id="51ae4-154">Running This Sample</span></span>  
  
#### <a name="to-run-the-helloworld-sample"></a><span data-ttu-id="51ae4-155">HelloWorld サンプルを実行するには</span><span class="sxs-lookup"><span data-stu-id="51ae4-155">To run the HelloWorld sample</span></span>  
  
1.  <span data-ttu-id="51ae4-156">ファイル SamplePOInput.xml のコピーに、**で**フォルダーです。</span><span class="sxs-lookup"><span data-stu-id="51ae4-156">Paste a copy of the file SamplePOInput.xml into the **In** folder.</span></span>  
  
2.  <span data-ttu-id="51ae4-157">作成した .xml ファイルを確認、**アウト**フォルダーです。</span><span class="sxs-lookup"><span data-stu-id="51ae4-157">Observe the .xml file created in the **Out** folder.</span></span> <span data-ttu-id="51ae4-158">このファイルには、入力ファイル SamplePOInput.xml から作成された XML 請求書が格納されます。</span><span class="sxs-lookup"><span data-stu-id="51ae4-158">This file contains the XML invoice constructed from the input file SamplePOInput.xml.</span></span> <span data-ttu-id="51ae4-159">このファイルの名前の形式が\< *MessageID*> .xml、場所 *\<MessageID >*メッセージを一意に識別する GUID が生成されます。</span><span class="sxs-lookup"><span data-stu-id="51ae4-159">The format of the name of this file is \<*MessageID*>.xml, where *\<MessageID>* is the GUID generated to uniquely identify the message.</span></span>  
  
## <a name="uninstalling-this-sample"></a><span data-ttu-id="51ae4-160">このサンプルのアンインストール</span><span class="sxs-lookup"><span data-stu-id="51ae4-160">Uninstalling This Sample</span></span>  
  
#### <a name="to-uninstall-the-helloworld-sample"></a><span data-ttu-id="51ae4-161">HelloWorld サンプルをアンインストールするには</span><span class="sxs-lookup"><span data-stu-id="51ae4-161">To uninstall the HelloWorld sample</span></span>  
  
1.  <span data-ttu-id="51ae4-162">コマンド ウィンドウで、次のフォルダーに移動します。</span><span class="sxs-lookup"><span data-stu-id="51ae4-162">In a command window, navigate to the following folder:</span></span>  
  
     <span data-ttu-id="51ae4-163">\<*パスのサンプル*> \Orchestrations\HelloWorld\\</span><span class="sxs-lookup"><span data-stu-id="51ae4-163">\<*Samples Path*>\Orchestrations\HelloWorld\\</span></span>  
  
2.  <span data-ttu-id="51ae4-164">Cleanup.bat を実行します。</span><span class="sxs-lookup"><span data-stu-id="51ae4-164">Run Cleanup.bat.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="51ae4-165">参照</span><span class="sxs-lookup"><span data-stu-id="51ae4-165">See Also</span></span>  
 [<span data-ttu-id="51ae4-166">オーケストレーション (BizTalk Server Samples フォルダ)</span><span class="sxs-lookup"><span data-stu-id="51ae4-166">Orchestrations (BizTalk Server Samples Folder)</span></span>](../core/orchestrations-biztalk-server-samples-folder.md)