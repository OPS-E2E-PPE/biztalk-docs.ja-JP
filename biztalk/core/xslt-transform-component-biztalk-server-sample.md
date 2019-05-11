---
title: XSLT 変換コンポーネント (BizTalk Server サンプル) |Microsoft Docs
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
ms.openlocfilehash: 7695bfd51eced669ab4bc71cd2823ec694d4284d
ms.sourcegitcommit: 381e83d43796a345488d54b3f7413e11d56ad7be
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 05/07/2019
ms.locfileid: "65279108"
---
# <a name="xslt-transform-component-biztalk-server-sample"></a><span data-ttu-id="f241b-102">XSLT 変換コンポーネント (BizTalk Server サンプル)</span><span class="sxs-lookup"><span data-stu-id="f241b-102">XSLT Transform Component (BizTalk Server Sample)</span></span>
<span data-ttu-id="f241b-103">XSLT 変換コンポーネント サンプルでは、XSLT を使用して XML メッセージを変換するカスタム パイプライン コンポーネントを記述する方法を示します。</span><span class="sxs-lookup"><span data-stu-id="f241b-103">The XSLT Transform Component sample demonstrates how to write a custom pipeline component to transform an XML message using XSLT.</span></span>  
  
## <a name="what-this-sample-does"></a><span data-ttu-id="f241b-104">このサンプルの処理</span><span class="sxs-lookup"><span data-stu-id="f241b-104">What This Sample Does</span></span>  
 <span data-ttu-id="f241b-105">サンプルでは、次の手順で変換を実現します。</span><span class="sxs-lookup"><span data-stu-id="f241b-105">The sample accomplishes the transformation with the following steps:</span></span>  
  
1.  <span data-ttu-id="f241b-106">XML ドキュメントは、フォルダーから取得されます。</span><span class="sxs-lookup"><span data-stu-id="f241b-106">An XML document is retrieved from a folder.</span></span>  
  
2.  <span data-ttu-id="f241b-107">パイプラインは Transform.xsl を使用して電子メール メッセージの HTML 本文に XML ドキュメントを変換します。</span><span class="sxs-lookup"><span data-stu-id="f241b-107">The pipeline transforms the XML document into the HTML body of an e-mail message using Transform.xsl.</span></span>  
  
## <a name="where-to-find-this-sample"></a><span data-ttu-id="f241b-108">このサンプルの場所</span><span class="sxs-lookup"><span data-stu-id="f241b-108">Where to Find This Sample</span></span>  
 <span data-ttu-id="f241b-109">*\<Samples Path\>* \Pipelines\XslTransformComponent\\</span><span class="sxs-lookup"><span data-stu-id="f241b-109">*\<Samples Path\>* \Pipelines\XslTransformComponent\\</span></span>  
  
 <span data-ttu-id="f241b-110">次の表は、このサンプルのファイルとその目的を示しています。</span><span class="sxs-lookup"><span data-stu-id="f241b-110">The following table shows the files in this sample and describes their purpose.</span></span>  
  
|<span data-ttu-id="f241b-111">ファイル</span><span class="sxs-lookup"><span data-stu-id="f241b-111">File(s)</span></span>|<span data-ttu-id="f241b-112">説明</span><span class="sxs-lookup"><span data-stu-id="f241b-112">Description</span></span>|  
|---------------|-----------------|  
|<span data-ttu-id="f241b-113">AssemblyInfo.cs</span><span class="sxs-lookup"><span data-stu-id="f241b-113">AssemblyInfo.cs</span></span>|<span data-ttu-id="f241b-114">C#アセンブリ ファイルです。</span><span class="sxs-lookup"><span data-stu-id="f241b-114">C# assembly file.</span></span>|  
|<span data-ttu-id="f241b-115">Cleanup.bat</span><span class="sxs-lookup"><span data-stu-id="f241b-115">Cleanup.bat</span></span>|<span data-ttu-id="f241b-116">サンプルのクリーンアップ ファイル。</span><span class="sxs-lookup"><span data-stu-id="f241b-116">Sample cleanup file.</span></span>|  
|<span data-ttu-id="f241b-117">Confirmation.xsd</span><span class="sxs-lookup"><span data-stu-id="f241b-117">Confirmation.xsd</span></span>|<span data-ttu-id="f241b-118">サンプル スキーマ ファイルです。</span><span class="sxs-lookup"><span data-stu-id="f241b-118">Sample schema file.</span></span>|  
|<span data-ttu-id="f241b-119">DocInstance.xml</span><span class="sxs-lookup"><span data-stu-id="f241b-119">DocInstance.xml</span></span>|<span data-ttu-id="f241b-120">サンプルの .xml ファイルを変換します。</span><span class="sxs-lookup"><span data-stu-id="f241b-120">Sample .xml file to transform.</span></span>|  
|<span data-ttu-id="f241b-121">SendHtmlMessage.btproj</span><span class="sxs-lookup"><span data-stu-id="f241b-121">SendHtmlMessage.btproj</span></span>|<span data-ttu-id="f241b-122">BizTalk プロジェクトです。</span><span class="sxs-lookup"><span data-stu-id="f241b-122">BizTalk project.</span></span>|  
|<span data-ttu-id="f241b-123">Setup.bat</span><span class="sxs-lookup"><span data-stu-id="f241b-123">Setup.bat</span></span>|<span data-ttu-id="f241b-124">構成バッチ ファイルです。</span><span class="sxs-lookup"><span data-stu-id="f241b-124">Configuration batch file.</span></span>|  
|<span data-ttu-id="f241b-125">Xml2HtmlSendPipeline.btp</span><span class="sxs-lookup"><span data-stu-id="f241b-125">Xml2HtmlSendPipeline.btp</span></span>|<span data-ttu-id="f241b-126">BizTalk Server パイプライン ファイルです。</span><span class="sxs-lookup"><span data-stu-id="f241b-126">BizTalk Server pipeline file.</span></span>|  
|<span data-ttu-id="f241b-127">XslTransform.csproj</span><span class="sxs-lookup"><span data-stu-id="f241b-127">XslTransform.csproj</span></span>|<span data-ttu-id="f241b-128">C#プロジェクトです。</span><span class="sxs-lookup"><span data-stu-id="f241b-128">C# project.</span></span>|  
|<span data-ttu-id="f241b-129">XslTransformComponent.sln</span><span class="sxs-lookup"><span data-stu-id="f241b-129">XslTransformComponent.sln</span></span>|<span data-ttu-id="f241b-130">サンプル ソリューション ファイルです。</span><span class="sxs-lookup"><span data-stu-id="f241b-130">Sample solution file.</span></span>|  
|<span data-ttu-id="f241b-131">XslTransformComponentBinding.XML</span><span class="sxs-lookup"><span data-stu-id="f241b-131">XslTransformComponentBinding.XML</span></span>|<span data-ttu-id="f241b-132">XML バインド ファイルです。</span><span class="sxs-lookup"><span data-stu-id="f241b-132">XML binding file.</span></span>|  
|<span data-ttu-id="f241b-133">XslTransformer.cs</span><span class="sxs-lookup"><span data-stu-id="f241b-133">XslTransformer.cs</span></span>|<span data-ttu-id="f241b-134">C#ソース コードです。</span><span class="sxs-lookup"><span data-stu-id="f241b-134">C# source code.</span></span>|  
|<span data-ttu-id="f241b-135">Transform.xsl</span><span class="sxs-lookup"><span data-stu-id="f241b-135">Transform.xsl</span></span>|<span data-ttu-id="f241b-136">DocInstance.xml の変換に使用される XSLT ファイル。</span><span class="sxs-lookup"><span data-stu-id="f241b-136">XSLT file used to transform DocInstance.xml.</span></span>|  
  
## <a name="building-and-initializing-this-sample"></a><span data-ttu-id="f241b-137">このサンプルのビルドと初期化</span><span class="sxs-lookup"><span data-stu-id="f241b-137">Building and Initializing This Sample</span></span>  
 <span data-ttu-id="f241b-138">次の手順を使用して、ビルドして、XSLT 変換コンポーネント サンプルを初期化します。</span><span class="sxs-lookup"><span data-stu-id="f241b-138">Use the following procedure to build and initialize the XSLT Transform Component sample.</span></span>  
  
#### <a name="to-build-and-initialize-this-sample"></a><span data-ttu-id="f241b-139">このサンプルを作成および初期化するには</span><span class="sxs-lookup"><span data-stu-id="f241b-139">To build and initialize this sample</span></span>  
  
1.  <span data-ttu-id="f241b-140">コマンド ウィンドウでディレクトリ変更 (**cd)** 次のフォルダーに。</span><span class="sxs-lookup"><span data-stu-id="f241b-140">In a command window, change directory (**cd)** to the following folder:</span></span>  
  
     <span data-ttu-id="f241b-141">*\<Samples Path\>* \Pipelines\XslTransformComponent</span><span class="sxs-lookup"><span data-stu-id="f241b-141">*\<Samples Path\>* \Pipelines\XslTransformComponent</span></span>  
  
2.  <span data-ttu-id="f241b-142">ファイルは、次の操作を実行します。 Setup.bat を実行します。</span><span class="sxs-lookup"><span data-stu-id="f241b-142">Run the file Setup.bat, which performs the following actions:</span></span>  
  
    -   <span data-ttu-id="f241b-143">入力 (\In) と、サンプルで使用される出力 (\Out) フォルダーを作成します。</span><span class="sxs-lookup"><span data-stu-id="f241b-143">Creates the input (\In) and output (\Out) folders used in the sample.</span></span>  
  
    -   <span data-ttu-id="f241b-144">新しいキー ファイルを生成します。</span><span class="sxs-lookup"><span data-stu-id="f241b-144">Generates a new key file.</span></span>  
  
    -   <span data-ttu-id="f241b-145">ビルドし、XSLT 変換コンポーネント パイプラインをデプロイします。</span><span class="sxs-lookup"><span data-stu-id="f241b-145">Builds and deploys the XSLT Transform Component pipeline.</span></span>  
  
    -   <span data-ttu-id="f241b-146">ビルドしたパイプライン コンポーネントのコピー、\<インストール パス\>\Pipeline Components フォルダー。</span><span class="sxs-lookup"><span data-stu-id="f241b-146">Copies the built pipeline component to the \<Installation Path\>\Pipeline Components folder.</span></span>  
  
    -   <span data-ttu-id="f241b-147">ポートと受信ポート、送信を作成します。</span><span class="sxs-lookup"><span data-stu-id="f241b-147">Creates the send and receive ports.</span></span>  
  
    > [!NOTE]
    >  <span data-ttu-id="f241b-148">エラーが報告されていないこと、ビルドおよび初期化プロセス中にこのサンプルを実行する前に確認してください。</span><span class="sxs-lookup"><span data-stu-id="f241b-148">You should confirm that no errors were reported during the build and initialization process before attempting to run this sample.</span></span>  
  
    > [!NOTE]
    >  <span data-ttu-id="f241b-149">Setup.bat による変更を元に戻したりするにはまず停止し、BizTalk Server 管理 MMC コンソールから、ホスト インスタンスを再起動します。</span><span class="sxs-lookup"><span data-stu-id="f241b-149">To undo changes made by Setup.bat, you must first stop and restart the host instance from the BizTalk Server Administration MMC console.</span></span> <span data-ttu-id="f241b-150">次に、Cleanup.bat を実行します。</span><span class="sxs-lookup"><span data-stu-id="f241b-150">Next, run Cleanup.bat.</span></span> <span data-ttu-id="f241b-151">Setup.bat を 2 回目に実行する場合は、その前に Cleanup.bat を実行してください。</span><span class="sxs-lookup"><span data-stu-id="f241b-151">You must run Cleanup.bat before running Setup.bat a second time.</span></span>  
  
## <a name="running-this-sample"></a><span data-ttu-id="f241b-152">このサンプルの実行</span><span class="sxs-lookup"><span data-stu-id="f241b-152">Running This Sample</span></span>  
 <span data-ttu-id="f241b-153">XSLT 変換コンポーネント サンプルを実行するのにには、次の手順を使用します。</span><span class="sxs-lookup"><span data-stu-id="f241b-153">Use the following procedure to run the XSLT Transform Component sample.</span></span>  
  
#### <a name="to-run-this-sample"></a><span data-ttu-id="f241b-154">このサンプルを実行するには</span><span class="sxs-lookup"><span data-stu-id="f241b-154">To run this sample</span></span>  
  
1.  <span data-ttu-id="f241b-155">DocInstance.xml を \In フォルダにコピーします。</span><span class="sxs-lookup"><span data-stu-id="f241b-155">Copy DocInstance.xml to the \In folder.</span></span>  
  
2.  <span data-ttu-id="f241b-156">(出力ファイル名は guid.htm) \Out フォルダで結果を確認します。</span><span class="sxs-lookup"><span data-stu-id="f241b-156">Examine the results in the \Out folder (the output filename is guid.htm).</span></span>  
  
## <a name="configuring-this-sample-using-smtp"></a><span data-ttu-id="f241b-157">SMTP を使用してこのサンプルの構成</span><span class="sxs-lookup"><span data-stu-id="f241b-157">Configuring This Sample Using SMTP</span></span>  
 <span data-ttu-id="f241b-158">SMTP サーバーを使用するのに XSLT 変換コンポーネント サンプルを構成するのにには、次の手順を使用します。</span><span class="sxs-lookup"><span data-stu-id="f241b-158">Use the following procedure to configure the XSLT Transform Component sample to work with an SMTP server.</span></span>  
  
#### <a name="to-configure-this-sample-using-smtp"></a><span data-ttu-id="f241b-159">SMTP を使用してこのサンプルを構成するには</span><span class="sxs-lookup"><span data-stu-id="f241b-159">To configure this sample using SMTP</span></span>  
  
1.  <span data-ttu-id="f241b-160">SMTP トランスポートの種類を使用する XSLT 変換コンポーネントの送信ポートを再構成します。</span><span class="sxs-lookup"><span data-stu-id="f241b-160">Reconfigure the XSLT Transform Component send port to use an SMTP transport type.</span></span>  
  
2.  <span data-ttu-id="f241b-161">SMTP 構成に合わせてアドレス (URI) パラメーターを変更することで、SMTP 設定を構成します。</span><span class="sxs-lookup"><span data-stu-id="f241b-161">Configure the SMTP setting by changing the address (URI) parameters to match your SMTP configuration.</span></span>  
  
## <a name="running-this-sample-with-output-to-an-smtp-port"></a><span data-ttu-id="f241b-162">SMTP ポートに出力をこのサンプルを実行しています。</span><span class="sxs-lookup"><span data-stu-id="f241b-162">Running This Sample with Output to an SMTP Port</span></span>  
 <span data-ttu-id="f241b-163">SMTP ポートに出力を XSLT 変換コンポーネント サンプルを実行するのにには、次の手順を使用します。</span><span class="sxs-lookup"><span data-stu-id="f241b-163">Use the following procedure to run the XSLT Transform Component sample with output to an SMTP port.</span></span>  
  
#### <a name="to-run-this-sample-with-output-to-an-smtp-port"></a><span data-ttu-id="f241b-164">SMTP ポートに出力をこのサンプルを実行するには</span><span class="sxs-lookup"><span data-stu-id="f241b-164">To run this sample with output to an SMTP port</span></span>  
  
1.  <span data-ttu-id="f241b-165">DocInstance.xml を \In フォルダにコピーします。</span><span class="sxs-lookup"><span data-stu-id="f241b-165">Copy DocInstance.xml to the \In folder.</span></span>  
  
2.  <span data-ttu-id="f241b-166">SMTP に構成されている受信者の電子メール クライアントで結果を確認を送信します。</span><span class="sxs-lookup"><span data-stu-id="f241b-166">Examine the results in the mail client for the recipient that SMTP is configured to send to.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="f241b-167">参照</span><span class="sxs-lookup"><span data-stu-id="f241b-167">See Also</span></span>  
 [<span data-ttu-id="f241b-168">パイプライン (BizTalk Server Samples フォルダー)</span><span class="sxs-lookup"><span data-stu-id="f241b-168">Pipelines (BizTalk Server Samples Folder)</span></span>](../core/pipelines-biztalk-server-samples-folder.md)