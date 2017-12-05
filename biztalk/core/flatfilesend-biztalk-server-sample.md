---
title: "FlatFileSend (BizTalk Server サンプル) |Microsoft ドキュメント"
ms.custom: 
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: 
ms.suite: 
ms.tgt_pltfrm: 
ms.topic: article
ms.assetid: 52dd0018-e272-40db-a26a-509d444d7106
caps.latest.revision: "18"
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: 5a9e967a8127a07b561e950b084bf799b0e2a4ee
ms.sourcegitcommit: 5abd0ed3f9e4858ffaaec5481bfa8878595e95f7
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 11/28/2017
---
# <a name="flatfilesend-biztalk-server-sample"></a><span data-ttu-id="65598-102">FlatFileSend (BizTalk Server サンプル)</span><span class="sxs-lookup"><span data-stu-id="65598-102">FlatFileSend (BizTalk Server Sample)</span></span>
<span data-ttu-id="65598-103">FlatFileSend サンプルは、[!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)] を使用して、XML ファイルを同等のフラット ファイルに変換する方法を示します。</span><span class="sxs-lookup"><span data-stu-id="65598-103">The FlatFileSend sample demonstrates how you can use [!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)] to process an XML file into the equivalent flat file.</span></span>  
  
## <a name="what-this-sample-does"></a><span data-ttu-id="65598-104">このサンプルの処理</span><span class="sxs-lookup"><span data-stu-id="65598-104">What This Sample Does</span></span>  
 <span data-ttu-id="65598-105">このサンプルでは、FFInput フォルダを受信場所として構成します。</span><span class="sxs-lookup"><span data-stu-id="65598-105">This sample configures the folder FFInput as a receive location.</span></span> <span data-ttu-id="65598-106">このフォルダーにサンプル ファイル FlatFileSend_in.xml のようなファイルを置くと、このファイル内のメッセージが [!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)] によって、次の手順で処理されます。</span><span class="sxs-lookup"><span data-stu-id="65598-106">When you place a file, such as the sample file FlatFileSend_in.xml, into this folder, [!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)] processes the message in this file using the following steps:</span></span>  
  
1.  [!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)]<span data-ttu-id="65598-107"> は、受信場所フォルダー FFInput の入力ファイルからメッセージを読み取ります。</span><span class="sxs-lookup"><span data-stu-id="65598-107"> reads the message from the input file in the receive location folder FFInput.</span></span>  
  
2.  <span data-ttu-id="65598-108">メッセージが XML 受信パイプライン経由で受け渡されます。</span><span class="sxs-lookup"><span data-stu-id="65598-108">The message is passed through an XML receive pipeline.</span></span>  
  
3.  <span data-ttu-id="65598-109">MessageBox データベースで、メッセージが FILE 送信ポートにルーティングされます。このポートには、フラット ファイル アセンブラ コンポーネントを使用するよう構成された送信パイプラインがあります。</span><span class="sxs-lookup"><span data-stu-id="65598-109">In the MessageBox database, the message is routed to a FILE send port that has a send pipeline configured with a Flat File Assembler component.</span></span> <span data-ttu-id="65598-110">フラット ファイル アセンブラ コンポーネントは、フラット ファイル スキーマを使用して、XML メッセージを同等のフラット ファイル表現に変換します。</span><span class="sxs-lookup"><span data-stu-id="65598-110">The Flat File Assembler component converts the XML message to an equivalent flat file representation using a flat file schema.</span></span>  
  
4.  [!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)]<span data-ttu-id="65598-111"> が、変換されたメッセージを送信アダプター フォルダー FFOutput のテキスト ファイルに書き込みます。</span><span class="sxs-lookup"><span data-stu-id="65598-111"> writes the converted message to a text file in the send adapter folder FFOutput.</span></span>  
  
## <a name="how-this-sample-is-designed-and-why"></a><span data-ttu-id="65598-112">このサンプルのデザイン方法とその理由</span><span class="sxs-lookup"><span data-stu-id="65598-112">How This Sample is Designed and Why</span></span>  
 <span data-ttu-id="65598-113">サンプル メッセージはこのサンプル内の基本デザインの多くを示しています。</span><span class="sxs-lookup"><span data-stu-id="65598-113">The sample message dictates much of the basic design in this sample.</span></span> <span data-ttu-id="65598-114">フラット ファイル メッセージは、カスタム送信パイプライン内のフラット ファイル アセンブラとフラット ファイル スキーマを使用してアセンブルする必要があります。</span><span class="sxs-lookup"><span data-stu-id="65598-114">Flat file messages must be assembled using the Flat File Assembler and a flat file schema within a custom send pipeline.</span></span> <span data-ttu-id="65598-115">これらのデザイン要素と他のデザイン要素を次の表にまとめます。</span><span class="sxs-lookup"><span data-stu-id="65598-115">These and other design elements are summarized in the following table.</span></span>  
  
|<span data-ttu-id="65598-116">デザイン要素</span><span class="sxs-lookup"><span data-stu-id="65598-116">Design element</span></span>|<span data-ttu-id="65598-117">選択理由</span><span class="sxs-lookup"><span data-stu-id="65598-117">Reason(s) selected</span></span>|  
|--------------------|--------------------------|  
|<span data-ttu-id="65598-118">カスタム送信パイプライン</span><span class="sxs-lookup"><span data-stu-id="65598-118">Custom send pipeline</span></span>|<span data-ttu-id="65598-119">-カスタム パイプラインはフラット ファイル アセンブラとフラット ファイル スキーマを使用して、インスタンス メッセージをフラット ファイル形式に変換するにはフラット ファイル アセンブラー自体はパイプラインで送信パイプラインを構成するときに使用することはできません、[!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)]管理コンソールです。</span><span class="sxs-lookup"><span data-stu-id="65598-119">-   The custom pipeline uses the Flat File Assembler and a flat file schema to translate the instance messages into flat file format; the Flat File Assembler is not itself a pipeline and cannot be used when configuring a send pipeline in the [!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)] Management console.</span></span>|  
|<span data-ttu-id="65598-120">フラット ファイル スキーマ</span><span class="sxs-lookup"><span data-stu-id="65598-120">Flat file schema</span></span>|<span data-ttu-id="65598-121">-すべて、同じレコードおよびフィールドの特性 (構造を含む) として定義 XML スキーマとすべての XML インスタンス メッセージをフラット ファイル メッセージに (またはその逆) に変換するために必要なフラット ファイルの特性を定義するためのメカニズムを提供します。</span><span class="sxs-lookup"><span data-stu-id="65598-121">-   Define all of the same record and field characteristics (including structure) as an XML schema and provides a mechanism for defining all of the flat file characteristics that are required to translate an XML instance message into a flat file message (or vice versa).</span></span>|  
|<span data-ttu-id="65598-122">サブスクリプション フィルター</span><span class="sxs-lookup"><span data-stu-id="65598-122">Subscription filter</span></span>|<span data-ttu-id="65598-123">-サブスクリプション フィルターは、プロパティ フィールドに基づいて 1 つまたは複数の条件を満たすメッセージをキャプチャして実際のルーティングを実行します。</span><span class="sxs-lookup"><span data-stu-id="65598-123">-   The subscription filter performs the actual routing by capturing messages that meet one or more criteria based on property fields.</span></span>|  
|<span data-ttu-id="65598-124">XMLReceive</span><span class="sxs-lookup"><span data-stu-id="65598-124">XMLReceive</span></span>|<span data-ttu-id="65598-125">-受信 XML メッセージの処理を実行します。</span><span class="sxs-lookup"><span data-stu-id="65598-125">-   Performs processing of inbound XML messages.</span></span> <span data-ttu-id="65598-126">この例では、注文書の XML 表現が変換対象のメッセージとして使用されます。</span><span class="sxs-lookup"><span data-stu-id="65598-126">For this example an XML representation of a purchase order is used as the source message.</span></span>|  
  
 <span data-ttu-id="65598-127">これらの要素が組み合わされて、XML 形式の注文書メッセージを受信場所から受け入れ、フラット ファイル形式の注文書を送信場所に書き込むソリューションが作成されます。</span><span class="sxs-lookup"><span data-stu-id="65598-127">These elements are combined to produce a solution that accepts purchase order messages in XML format from the receive location and writes out a flat file purchase order to the send location.</span></span>  
  
## <a name="where-to-find-this-sample"></a><span data-ttu-id="65598-128">このサンプルの場所</span><span class="sxs-lookup"><span data-stu-id="65598-128">Where to Find This Sample</span></span>  
 <span data-ttu-id="65598-129">*\<パスのサンプル\>*\Pipelines\AssemblerDisassembler\FlatFileSend</span><span class="sxs-lookup"><span data-stu-id="65598-129">*\<Samples Path\>*\Pipelines\AssemblerDisassembler\FlatFileSend</span></span>  
  
 <span data-ttu-id="65598-130">次の表は、このサンプルのファイルとその目的を示しています。</span><span class="sxs-lookup"><span data-stu-id="65598-130">The following table shows the files in this sample and describes their purpose.</span></span>  
  
|<span data-ttu-id="65598-131">ファイル</span><span class="sxs-lookup"><span data-stu-id="65598-131">File(s)</span></span>|<span data-ttu-id="65598-132">Description</span><span class="sxs-lookup"><span data-stu-id="65598-132">Description</span></span>|  
|---------------|-----------------|  
|<span data-ttu-id="65598-133">Cleanup.bat</span><span class="sxs-lookup"><span data-stu-id="65598-133">Cleanup.bat</span></span>|<span data-ttu-id="65598-134">アセンブリの展開を解除し、グローバル アセンブリ キャッシュからアセンブリを削除するために使用されます。</span><span class="sxs-lookup"><span data-stu-id="65598-134">Used to undeploy assemblies and remove them from the global assembly cache.</span></span> <span data-ttu-id="65598-135">送信ポートと受信ポートが削除されます。</span><span class="sxs-lookup"><span data-stu-id="65598-135">Removes send and receive ports.</span></span> <span data-ttu-id="65598-136">必要に応じて、Microsoft インターネット インフォメーション サービス (IIS) の仮想ディレクトリが削除されます。</span><span class="sxs-lookup"><span data-stu-id="65598-136">Removes Microsoft Internet Information Services (IIS) virtual directories as needed.</span></span>|  
|<span data-ttu-id="65598-137">FlatFileSend.btproj、FlatFileSend.sln</span><span class="sxs-lookup"><span data-stu-id="65598-137">FlatFileSend.btproj, FlatFileSend.sln</span></span>|<span data-ttu-id="65598-138">このサンプルのプロジェクト ファイルとソリューション ファイルです。</span><span class="sxs-lookup"><span data-stu-id="65598-138">Project and solution files for this sample.</span></span>|  
|<span data-ttu-id="65598-139">FlatFileSendBinding.xml</span><span class="sxs-lookup"><span data-stu-id="65598-139">FlatFileSendBinding.xml</span></span>|<span data-ttu-id="65598-140">ポートのバインドなど、自動化されたセットアップに使用されます。</span><span class="sxs-lookup"><span data-stu-id="65598-140">Used for automated setup such as port binding.</span></span>|  
|<span data-ttu-id="65598-141">FlatFileSend_in.xml</span><span class="sxs-lookup"><span data-stu-id="65598-141">FlatFileSend_in.xml</span></span>|<span data-ttu-id="65598-142">サンプル入力ファイルです。</span><span class="sxs-lookup"><span data-stu-id="65598-142">Sample input file.</span></span>|  
|<span data-ttu-id="65598-143">PO.xsd</span><span class="sxs-lookup"><span data-stu-id="65598-143">PO.xsd</span></span>|<span data-ttu-id="65598-144">送信フラット ファイルのスキーマです。</span><span class="sxs-lookup"><span data-stu-id="65598-144">Schema for outbound flat file.</span></span>|  
|<span data-ttu-id="65598-145">SendPipeline.btp</span><span class="sxs-lookup"><span data-stu-id="65598-145">SendPipeline.btp</span></span>|<span data-ttu-id="65598-146">フラット ファイル アセンブラー コンポーネントを含む [!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)] 送信パイプライン ファイルです。</span><span class="sxs-lookup"><span data-stu-id="65598-146">[!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)] send pipeline file with the Flat File Assembler component.</span></span>|  
|<span data-ttu-id="65598-147">Setup.bat</span><span class="sxs-lookup"><span data-stu-id="65598-147">Setup.bat</span></span>|<span data-ttu-id="65598-148">このサンプルをビルドおよび初期化するために使用されます。</span><span class="sxs-lookup"><span data-stu-id="65598-148">Used to build and initialize this sample.</span></span>|  
  
## <a name="how-to-use-this-sample"></a><span data-ttu-id="65598-149">このサンプルの使用方法</span><span class="sxs-lookup"><span data-stu-id="65598-149">How to Use This Sample</span></span>  
 <span data-ttu-id="65598-150">このサンプルは、独自のフラット ファイル処理ソリューションの基礎として使用してください。</span><span class="sxs-lookup"><span data-stu-id="65598-150">Use this sample as the basis for your own flat file processing solution.</span></span> <span data-ttu-id="65598-151">このサンプルで使用されているデザイン要素の多くは、独自の要件に合うように拡張できます。</span><span class="sxs-lookup"><span data-stu-id="65598-151">You can extend many of the design elements used in this sample to fit your own requirements.</span></span>  
  
## <a name="building-and-initializing-this-sample"></a><span data-ttu-id="65598-152">このサンプルのビルドと初期化</span><span class="sxs-lookup"><span data-stu-id="65598-152">Building and Initializing This Sample</span></span>  
  
1.  <span data-ttu-id="65598-153">コマンド ウィンドウで、次のフォルダーに移動します。</span><span class="sxs-lookup"><span data-stu-id="65598-153">In a command window, navigate to the following folder:</span></span>  
  
     <span data-ttu-id="65598-154">*\<パスのサンプル\>*\Pipelines\AssemblerDisassembler\FlatFileSend</span><span class="sxs-lookup"><span data-stu-id="65598-154">*\<Samples Path\>*\Pipelines\AssemblerDisassembler\FlatFileSend</span></span>  
  
2.  <span data-ttu-id="65598-155">次の操作を実行する Setup.bat ファイルを実行します。</span><span class="sxs-lookup"><span data-stu-id="65598-155">Run the file Setup.bat, which performs the following actions:</span></span>  
  
    -   <span data-ttu-id="65598-156">次のフォルダに、このサンプルの入力 (FFInput) フォルダと出力 (FFOutput) フォルダを作成します。</span><span class="sxs-lookup"><span data-stu-id="65598-156">Creates the input (FFInput) and output (FFOutput) folders for this sample in the folder:</span></span>  
  
         <span data-ttu-id="65598-157">*\<パスのサンプル\>*\Pipelines\AssemblerDisassembler\FlatFileSend</span><span class="sxs-lookup"><span data-stu-id="65598-157">*\<Samples Path\>*\Pipelines\AssemblerDisassembler\FlatFileSend</span></span>  
  
    -   <span data-ttu-id="65598-158">コンパイル、[!INCLUDE[btsVStudioNoVersion](../includes/btsvstudionoversion-md.md)]このサンプルのプロジェクトです。</span><span class="sxs-lookup"><span data-stu-id="65598-158">Compiles the [!INCLUDE[btsVStudioNoVersion](../includes/btsvstudionoversion-md.md)] project for this sample.</span></span>  
  
    -   <span data-ttu-id="65598-159">[!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)] の受信場所、送信ポート、および受信ポートを作成しバインドします。</span><span class="sxs-lookup"><span data-stu-id="65598-159">Creates and binds the [!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)] receive location, and the send and receive ports.</span></span>  
  
        > [!NOTE]
        >  <span data-ttu-id="65598-160">このサンプルを作成して、ポートのバインド時に、次の警告が表示されます:`Warning: Receive handler not specified for receive location "FlatFileSend_RL"; updating with first receive handler with matching transport type. Warning: Host not specified for orchestration "FlatFileSend"; updating with first available host.`これらの警告を無視してかまいません。</span><span class="sxs-lookup"><span data-stu-id="65598-160">This sample displays the following warnings when creating and binding the ports: `Warning: Receive handler not specified for receive location "FlatFileSend_RL"; updating with first receive handler with matching transport type. Warning: Host not specified for orchestration "FlatFileSend"; updating with first available host.` You can safely ignore these warnings.</span></span> <span data-ttu-id="65598-161">(インストールでの名前付け方法はユーザーによって異なる可能性があるため、ホスト名と受信ハンドラーはバインド ファイルから除外されています。)</span><span class="sxs-lookup"><span data-stu-id="65598-161">(To accommodate for possible naming differences in user installations, the host name and receive handler have been omitted from the binding file.)</span></span>  
  
    -   <span data-ttu-id="65598-162">受信場所を有効にし、送信ポートを開始します。</span><span class="sxs-lookup"><span data-stu-id="65598-162">Enables the receive location, and starts the send port.</span></span>  
  
> [!NOTE]
>  <span data-ttu-id="65598-163">このサンプルを実行する前に、ビルドと初期化のプロセス中に [!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)] でエラーが報告されていないことを確認する必要があります。</span><span class="sxs-lookup"><span data-stu-id="65598-163">You should confirm that [!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)] did not report any errors during the build and initialization process before attempting to run this sample.</span></span>  
  
> [!NOTE]
>  <span data-ttu-id="65598-164">開き、Setup.bat を実行しなくてもこのサンプルでは、プロジェクトをビルドする場合は、まず、.NET Framework の厳密名ユーティリティ (sn.exe) を使用して、厳密な名前のキー ペアを作成する必要があります。</span><span class="sxs-lookup"><span data-stu-id="65598-164">If you choose to open and build the project in this sample without running Setup.bat, you must first create a strong name key pair using the .NET Framework Strong Name utility (sn.exe).</span></span> <span data-ttu-id="65598-165">結果として得られるアセンブリに署名するのにには、このキー ペアを使用します。</span><span class="sxs-lookup"><span data-stu-id="65598-165">Use this key pair to sign the resulting assembly.</span></span>  
  
> [!NOTE]
>  <span data-ttu-id="65598-166">Setup.bat によって行われた変更を元に戻すには、Cleanup.bat を実行します。</span><span class="sxs-lookup"><span data-stu-id="65598-166">To undo changes made by Setup.bat, run Cleanup.bat.</span></span> <span data-ttu-id="65598-167">Setup.bat を 2 回目に実行する場合は、その前に Cleanup.bat を実行してください。</span><span class="sxs-lookup"><span data-stu-id="65598-167">You must run Cleanup.bat before running Setup.bat a second time.</span></span>  
  
## <a name="running-this-sample"></a><span data-ttu-id="65598-168">このサンプルの実行</span><span class="sxs-lookup"><span data-stu-id="65598-168">Running This Sample</span></span>  
  
1.  <span data-ttu-id="65598-169">ファイル FlatFileSend_in.xml を FFInput フォルダにコピーします。</span><span class="sxs-lookup"><span data-stu-id="65598-169">Put a copy of the file FlatFileSend_in.xml into the folder FFInput.</span></span>  
  
2.  <span data-ttu-id="65598-170">テキスト ファイルが FFOutput フォルダに作成されることを確認します。</span><span class="sxs-lookup"><span data-stu-id="65598-170">Observe the text file created in the folder FFOutput.</span></span> <span data-ttu-id="65598-171">テキスト ファイルの名前は、メッセージ ID の GUID に基づきます。</span><span class="sxs-lookup"><span data-stu-id="65598-171">The name of the text file is based on the message ID GUID.</span></span> <span data-ttu-id="65598-172">このファイルには、XML 入力ファイル FlatFileSend_in.xml と同等のフラット ファイルが含まれています。</span><span class="sxs-lookup"><span data-stu-id="65598-172">This file contains the flat file equivalent of the XML input file FlatFileSend_in.xml.</span></span>  
  
## <a name="classes-or-methods-used-in-this-sample"></a><span data-ttu-id="65598-173">このサンプルで使用されるクラスまたはメソッド</span><span class="sxs-lookup"><span data-stu-id="65598-173">Classes or Methods Used in This Sample</span></span>  
 <span data-ttu-id="65598-174">Setup.bat および Cleanup.bat の 2 つの構成スクリプトは、次の管理用 Windows Management Instrumentation (WMI) スクリプトに依存しています。</span><span class="sxs-lookup"><span data-stu-id="65598-174">The configuration scripts Setup.bat and Cleanup.bat rely on the following administrative Windows Management Instrumentation (WMI) scripts:</span></span>  
  
-   <span data-ttu-id="65598-175">Start Send Port\StartSendPort.vbs</span><span class="sxs-lookup"><span data-stu-id="65598-175">Start Send Port\StartSendPort.vbs</span></span>  
  
-   <span data-ttu-id="65598-176">Enable Receive Location\EnableRecLoc</span><span class="sxs-lookup"><span data-stu-id="65598-176">Enable Receive Location\EnableRecLoc</span></span>  
  
-   <span data-ttu-id="65598-177">Remove Send Port\RemoveSendPort</span><span class="sxs-lookup"><span data-stu-id="65598-177">Remove Send Port\RemoveSendPort</span></span>  
  
 <span data-ttu-id="65598-178">セットアップおよびクリーンアップのバッチ ファイルでは、次のように BTSTask を使用します。</span><span class="sxs-lookup"><span data-stu-id="65598-178">The setup and cleanup batch files use BTSTask as follows:</span></span>  
  
-   <span data-ttu-id="65598-179">**BTSTask ImportBindings**バインド ファイルを適用し、アプリケーション、ポート、およびバインドを作成するには</span><span class="sxs-lookup"><span data-stu-id="65598-179">**BTSTask ImportBindings** to apply the binding file and create the application, ports, and bindings</span></span>  
  
-   <span data-ttu-id="65598-180">**BTSTask RemoveApp** FlatFileSendApplication を削除するには</span><span class="sxs-lookup"><span data-stu-id="65598-180">**BTSTask RemoveApp** to remove the FlatFileSendApplication</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="65598-181">参照</span><span class="sxs-lookup"><span data-stu-id="65598-181">See Also</span></span>  
-  [<span data-ttu-id="65598-182">フラット ファイル スキーマ</span><span class="sxs-lookup"><span data-stu-id="65598-182">Flat File Schemas</span></span>](../core/flat-file-schemas.md)   
-  [<span data-ttu-id="65598-183">既定のパイプライン</span><span class="sxs-lookup"><span data-stu-id="65598-183">Default Pipelines</span></span>](../core/default-pipelines.md)   
-  [<span data-ttu-id="65598-184">Pipelines-AssemblerDisassembler (BizTalk Server サンプル フォルダー)</span><span class="sxs-lookup"><span data-stu-id="65598-184">Pipelines-AssemblerDisassembler (BizTalk Server Samples Folder)</span></span>](../core/pipelines-assemblerdisassembler-biztalk-server-samples-folder.md)   
-  <span data-ttu-id="65598-185">**WMI スクリプト サンプル**[!INCLUDE[ui-guidance-developers-reference](../includes/ui-guidance-developers-reference.md)]</span><span class="sxs-lookup"><span data-stu-id="65598-185">**WMI Script Samples** [!INCLUDE[ui-guidance-developers-reference](../includes/ui-guidance-developers-reference.md)]</span></span>
-  [<span data-ttu-id="65598-186">BTSTask コマンド ライン リファレンス</span><span class="sxs-lookup"><span data-stu-id="65598-186">BTSTask Command-Line Reference</span></span>](../core/btstask-command-line-reference.md)   
-  [<span data-ttu-id="65598-187">FlatFileReceive (BizTalk Server サンプル)</span><span class="sxs-lookup"><span data-stu-id="65598-187">FlatFileReceive (BizTalk Server Sample)</span></span>](../core/flatfilereceive-biztalk-server-sample.md)