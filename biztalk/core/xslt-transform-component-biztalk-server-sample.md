---
title: XSLT 変換コンポーネント (BizTalk Server サンプル) |Microsoft ドキュメント
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
- XSLT, examples
- examples, XSLT
ms.assetid: 9152e897-4db9-4924-b37e-fd9e908dbef1
caps.latest.revision: 10
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: 1879cb4d748e974454f929bde2018c24b5d276f2
ms.sourcegitcommit: 5abd0ed3f9e4858ffaaec5481bfa8878595e95f7
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 11/28/2017
ms.locfileid: "25974928"
---
# <a name="xslt-transform-component-biztalk-server-sample"></a><span data-ttu-id="ac69f-102">XSLT 変換コンポーネント (BizTalk Server サンプル)</span><span class="sxs-lookup"><span data-stu-id="ac69f-102">XSLT Transform Component (BizTalk Server Sample)</span></span>
<span data-ttu-id="ac69f-103">XSLT 変換コンポーネント サンプルは、カスタム パイプライン コンポーネントを作成し、XSLT を使用して XML メッセージを変換する方法を示します。</span><span class="sxs-lookup"><span data-stu-id="ac69f-103">The XSLT Transform Component sample demonstrates how to write a custom pipeline component to transform an XML message using XSLT.</span></span>  
  
## <a name="what-this-sample-does"></a><span data-ttu-id="ac69f-104">このサンプルの処理</span><span class="sxs-lookup"><span data-stu-id="ac69f-104">What This Sample Does</span></span>  
 <span data-ttu-id="ac69f-105">このサンプルでは、次の手順で変換を行います。</span><span class="sxs-lookup"><span data-stu-id="ac69f-105">The sample accomplishes the transformation with the following steps:</span></span>  
  
1.  <span data-ttu-id="ac69f-106">XML ドキュメントがフォルダから取得されます。</span><span class="sxs-lookup"><span data-stu-id="ac69f-106">An XML document is retrieved from a folder.</span></span>  
  
2.  <span data-ttu-id="ac69f-107">パイプラインは Transform.xsl を使用して、XML ドキュメントを電子メール メッセージの HTML 本文に変換します。</span><span class="sxs-lookup"><span data-stu-id="ac69f-107">The pipeline transforms the XML document into the HTML body of an e-mail message using Transform.xsl.</span></span>  
  
## <a name="where-to-find-this-sample"></a><span data-ttu-id="ac69f-108">このサンプルの場所</span><span class="sxs-lookup"><span data-stu-id="ac69f-108">Where to Find This Sample</span></span>  
 <span data-ttu-id="ac69f-109">*\<パスのサンプル\>* \Pipelines\XslTransformComponent\\</span><span class="sxs-lookup"><span data-stu-id="ac69f-109">*\<Samples Path\>* \Pipelines\XslTransformComponent\\</span></span>  
  
 <span data-ttu-id="ac69f-110">次の表は、このサンプルのファイルとその目的を示しています。</span><span class="sxs-lookup"><span data-stu-id="ac69f-110">The following table shows the files in this sample and describes their purpose.</span></span>  
  
|<span data-ttu-id="ac69f-111">ファイル</span><span class="sxs-lookup"><span data-stu-id="ac69f-111">File(s)</span></span>|<span data-ttu-id="ac69f-112">Description</span><span class="sxs-lookup"><span data-stu-id="ac69f-112">Description</span></span>|  
|---------------|-----------------|  
|<span data-ttu-id="ac69f-113">AssemblyInfo.cs</span><span class="sxs-lookup"><span data-stu-id="ac69f-113">AssemblyInfo.cs</span></span>|<span data-ttu-id="ac69f-114">C# アセンブリ ファイル。</span><span class="sxs-lookup"><span data-stu-id="ac69f-114">C# assembly file.</span></span>|  
|<span data-ttu-id="ac69f-115">Cleanup.bat</span><span class="sxs-lookup"><span data-stu-id="ac69f-115">Cleanup.bat</span></span>|<span data-ttu-id="ac69f-116">サンプルのクリーンアップ ファイル。</span><span class="sxs-lookup"><span data-stu-id="ac69f-116">Sample cleanup file.</span></span>|  
|<span data-ttu-id="ac69f-117">Confirmation.xsd</span><span class="sxs-lookup"><span data-stu-id="ac69f-117">Confirmation.xsd</span></span>|<span data-ttu-id="ac69f-118">サンプルのスキーマ ファイル。</span><span class="sxs-lookup"><span data-stu-id="ac69f-118">Sample schema file.</span></span>|  
|<span data-ttu-id="ac69f-119">DocInstance.xml</span><span class="sxs-lookup"><span data-stu-id="ac69f-119">DocInstance.xml</span></span>|<span data-ttu-id="ac69f-120">変換するサンプルの .xml ファイル。</span><span class="sxs-lookup"><span data-stu-id="ac69f-120">Sample .xml file to transform.</span></span>|  
|<span data-ttu-id="ac69f-121">SendHtmlMessage.btproj</span><span class="sxs-lookup"><span data-stu-id="ac69f-121">SendHtmlMessage.btproj</span></span>|<span data-ttu-id="ac69f-122">BizTalk プロジェクト。</span><span class="sxs-lookup"><span data-stu-id="ac69f-122">BizTalk project.</span></span>|  
|<span data-ttu-id="ac69f-123">Setup.bat</span><span class="sxs-lookup"><span data-stu-id="ac69f-123">Setup.bat</span></span>|<span data-ttu-id="ac69f-124">構成バッチ ファイル。</span><span class="sxs-lookup"><span data-stu-id="ac69f-124">Configuration batch file.</span></span>|  
|<span data-ttu-id="ac69f-125">Xml2HtmlSendPipeline.btp</span><span class="sxs-lookup"><span data-stu-id="ac69f-125">Xml2HtmlSendPipeline.btp</span></span>|<span data-ttu-id="ac69f-126">BizTalk Server パイプライン ファイル。</span><span class="sxs-lookup"><span data-stu-id="ac69f-126">BizTalk Server pipeline file.</span></span>|  
|<span data-ttu-id="ac69f-127">XslTransform.csproj</span><span class="sxs-lookup"><span data-stu-id="ac69f-127">XslTransform.csproj</span></span>|<span data-ttu-id="ac69f-128">C# プロジェクト。</span><span class="sxs-lookup"><span data-stu-id="ac69f-128">C# project.</span></span>|  
|<span data-ttu-id="ac69f-129">XslTransformComponent.sln</span><span class="sxs-lookup"><span data-stu-id="ac69f-129">XslTransformComponent.sln</span></span>|<span data-ttu-id="ac69f-130">サンプルのソリューション ファイル。</span><span class="sxs-lookup"><span data-stu-id="ac69f-130">Sample solution file.</span></span>|  
|<span data-ttu-id="ac69f-131">XslTransformComponentBinding.XML</span><span class="sxs-lookup"><span data-stu-id="ac69f-131">XslTransformComponentBinding.XML</span></span>|<span data-ttu-id="ac69f-132">XML バインド ファイル。</span><span class="sxs-lookup"><span data-stu-id="ac69f-132">XML binding file.</span></span>|  
|<span data-ttu-id="ac69f-133">XslTransformer.cs</span><span class="sxs-lookup"><span data-stu-id="ac69f-133">XslTransformer.cs</span></span>|<span data-ttu-id="ac69f-134">C# ソース コード。</span><span class="sxs-lookup"><span data-stu-id="ac69f-134">C# source code.</span></span>|  
|<span data-ttu-id="ac69f-135">Transform.xsl</span><span class="sxs-lookup"><span data-stu-id="ac69f-135">Transform.xsl</span></span>|<span data-ttu-id="ac69f-136">DocInstance.xml の変換に使用する XSLT ファイル。</span><span class="sxs-lookup"><span data-stu-id="ac69f-136">XSLT file used to transform DocInstance.xml.</span></span>|  
  
## <a name="building-and-initializing-this-sample"></a><span data-ttu-id="ac69f-137">このサンプルのビルドと初期化</span><span class="sxs-lookup"><span data-stu-id="ac69f-137">Building and Initializing This Sample</span></span>  
 <span data-ttu-id="ac69f-138">次の手順を使用して、XSLT 変換コンポーネント サンプルをビルドおよび初期化します。</span><span class="sxs-lookup"><span data-stu-id="ac69f-138">Use the following procedure to build and initialize the XSLT Transform Component sample.</span></span>  
  
#### <a name="to-build-and-initialize-this-sample"></a><span data-ttu-id="ac69f-139">このサンプルを作成および初期化するには</span><span class="sxs-lookup"><span data-stu-id="ac69f-139">To build and initialize this sample</span></span>  
  
1.  <span data-ttu-id="ac69f-140">コマンド ウィンドウでディレクトリ変更 (**cd)** 次のフォルダーに。</span><span class="sxs-lookup"><span data-stu-id="ac69f-140">In a command window, change directory (**cd)** to the following folder:</span></span>  
  
     <span data-ttu-id="ac69f-141">*\<パスのサンプル\>* \Pipelines\XslTransformComponent</span><span class="sxs-lookup"><span data-stu-id="ac69f-141">*\<Samples Path\>* \Pipelines\XslTransformComponent</span></span>  
  
2.  <span data-ttu-id="ac69f-142">次の操作を実行する Setup.bat ファイルを実行します。</span><span class="sxs-lookup"><span data-stu-id="ac69f-142">Run the file Setup.bat, which performs the following actions:</span></span>  
  
    -   <span data-ttu-id="ac69f-143">サンプルで使用される入力 (\In) フォルダと出力 (\Out) フォルダを作成します。</span><span class="sxs-lookup"><span data-stu-id="ac69f-143">Creates the input (\In) and output (\Out) folders used in the sample.</span></span>  
  
    -   <span data-ttu-id="ac69f-144">新しいキー ファイルを生成します。</span><span class="sxs-lookup"><span data-stu-id="ac69f-144">Generates a new key file.</span></span>  
  
    -   <span data-ttu-id="ac69f-145">XSLT 変換コンポーネント パイプラインをビルドおよび展開します。</span><span class="sxs-lookup"><span data-stu-id="ac69f-145">Builds and deploys the XSLT Transform Component pipeline.</span></span>  
  
    -   <span data-ttu-id="ac69f-146">ビルドしたパイプライン コンポーネントへのコピー、\<インストール パス\>\Pipeline Components フォルダーです。</span><span class="sxs-lookup"><span data-stu-id="ac69f-146">Copies the built pipeline component to the \<Installation Path\>\Pipeline Components folder.</span></span>  
  
    -   <span data-ttu-id="ac69f-147">送信ポートおよび受信ポートを作成します。</span><span class="sxs-lookup"><span data-stu-id="ac69f-147">Creates the send and receive ports.</span></span>  
  
    > [!NOTE]
    >  <span data-ttu-id="ac69f-148">このサンプルを実行する前に、ビルド処理および初期化処理でエラーが報告されていないことを確認してください。</span><span class="sxs-lookup"><span data-stu-id="ac69f-148">You should confirm that no errors were reported during the build and initialization process before attempting to run this sample.</span></span>  
  
    > [!NOTE]
    >  <span data-ttu-id="ac69f-149">Setup.bat が行った変更を元に戻すには、BizTalk Server 管理 MMC コンソールでホスト インスタンスをまず停止し、再起動する必要があります。</span><span class="sxs-lookup"><span data-stu-id="ac69f-149">To undo changes made by Setup.bat, you must first stop and restart the host instance from the BizTalk Server Administration MMC console.</span></span> <span data-ttu-id="ac69f-150">次に、Cleanup.bat を実行します。</span><span class="sxs-lookup"><span data-stu-id="ac69f-150">Next, run Cleanup.bat.</span></span> <span data-ttu-id="ac69f-151">Setup.bat を 2 回目に実行する場合は、その前に Cleanup.bat を実行してください。</span><span class="sxs-lookup"><span data-stu-id="ac69f-151">You must run Cleanup.bat before running Setup.bat a second time.</span></span>  
  
## <a name="running-this-sample"></a><span data-ttu-id="ac69f-152">このサンプルの実行</span><span class="sxs-lookup"><span data-stu-id="ac69f-152">Running This Sample</span></span>  
 <span data-ttu-id="ac69f-153">次の手順を使用して、XSLT 変換コンポーネント サンプルを実行します。</span><span class="sxs-lookup"><span data-stu-id="ac69f-153">Use the following procedure to run the XSLT Transform Component sample.</span></span>  
  
#### <a name="to-run-this-sample"></a><span data-ttu-id="ac69f-154">このサンプルを実行するには</span><span class="sxs-lookup"><span data-stu-id="ac69f-154">To run this sample</span></span>  
  
1.  <span data-ttu-id="ac69f-155">DocInstance.xml を \In フォルダにコピーします。</span><span class="sxs-lookup"><span data-stu-id="ac69f-155">Copy DocInstance.xml to the \In folder.</span></span>  
  
2.  <span data-ttu-id="ac69f-156">\Out フォルダ内の結果を確認します (出力ファイル名は guid.htm)。</span><span class="sxs-lookup"><span data-stu-id="ac69f-156">Examine the results in the \Out folder (the output filename is guid.htm).</span></span>  
  
## <a name="configuring-this-sample-using-smtp"></a><span data-ttu-id="ac69f-157">SMTP を使用したこのサンプルの構成</span><span class="sxs-lookup"><span data-stu-id="ac69f-157">Configuring This Sample Using SMTP</span></span>  
 <span data-ttu-id="ac69f-158">次の手順を使用して、SMTP サーバーで使用する XSLT 変換コンポーネント サンプルを構成します。</span><span class="sxs-lookup"><span data-stu-id="ac69f-158">Use the following procedure to configure the XSLT Transform Component sample to work with an SMTP server.</span></span>  
  
#### <a name="to-configure-this-sample-using-smtp"></a><span data-ttu-id="ac69f-159">SMTP を使用してこのサンプルを構成するには</span><span class="sxs-lookup"><span data-stu-id="ac69f-159">To configure this sample using SMTP</span></span>  
  
1.  <span data-ttu-id="ac69f-160">SMTP のトランスポートの種類を使用するように XSLT 変換コンポーネントの送信ポートを再構成します。</span><span class="sxs-lookup"><span data-stu-id="ac69f-160">Reconfigure the XSLT Transform Component send port to use an SMTP transport type.</span></span>  
  
2.  <span data-ttu-id="ac69f-161">SMTP 構成に合わせてアドレス (URI) パラメータを変更し、SMTP 設定を構成します。</span><span class="sxs-lookup"><span data-stu-id="ac69f-161">Configure the SMTP setting by changing the address (URI) parameters to match your SMTP configuration.</span></span>  
  
## <a name="running-this-sample-with-output-to-an-smtp-port"></a><span data-ttu-id="ac69f-162">SMTP ポートに出力するためのこのサンプルの実行</span><span class="sxs-lookup"><span data-stu-id="ac69f-162">Running This Sample with Output to an SMTP Port</span></span>  
 <span data-ttu-id="ac69f-163">次の手順を使用して、XSLT 変換コンポーネント サンプルを実行し、SMTP ポートに出力します。</span><span class="sxs-lookup"><span data-stu-id="ac69f-163">Use the following procedure to run the XSLT Transform Component sample with output to an SMTP port.</span></span>  
  
#### <a name="to-run-this-sample-with-output-to-an-smtp-port"></a><span data-ttu-id="ac69f-164">SMTP ポートに出力するためのこのサンプルを実行するには</span><span class="sxs-lookup"><span data-stu-id="ac69f-164">To run this sample with output to an SMTP port</span></span>  
  
1.  <span data-ttu-id="ac69f-165">DocInstance.xml を \In フォルダにコピーします。</span><span class="sxs-lookup"><span data-stu-id="ac69f-165">Copy DocInstance.xml to the \In folder.</span></span>  
  
2.  <span data-ttu-id="ac69f-166">SMTP に構成されている送信先受信者のメール クライアントの結果を確認します。</span><span class="sxs-lookup"><span data-stu-id="ac69f-166">Examine the results in the mail client for the recipient that SMTP is configured to send to.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="ac69f-167">参照</span><span class="sxs-lookup"><span data-stu-id="ac69f-167">See Also</span></span>  
 [<span data-ttu-id="ac69f-168">パイプライン (BizTalk Server Samples フォルダー)</span><span class="sxs-lookup"><span data-stu-id="ac69f-168">Pipelines (BizTalk Server Samples Folder)</span></span>](../core/pipelines-biztalk-server-samples-folder.md)