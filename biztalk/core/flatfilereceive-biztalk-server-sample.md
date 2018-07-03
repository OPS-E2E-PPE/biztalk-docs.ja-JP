---
title: FlatFileReceive (BizTalk Server サンプル) |Microsoft Docs
ms.custom: ''
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: ''
ms.suite: ''
ms.tgt_pltfrm: ''
ms.topic: article
ms.assetid: 90bd9e8d-6ed9-49c4-8437-c0c8b2a9a78d
caps.latest.revision: 20
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: ae4cdace5a38d3b6a7058f16e894ca9bdbe912c8
ms.sourcegitcommit: 266308ec5c6a9d8d80ff298ee6051b4843c5d626
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 06/27/2018
ms.locfileid: "36975539"
---
# <a name="flatfilereceive-biztalk-server-sample"></a><span data-ttu-id="9f24a-102">FlatFileReceive (BizTalk Server サンプル)</span><span class="sxs-lookup"><span data-stu-id="9f24a-102">FlatFileReceive (BizTalk Server Sample)</span></span>
<span data-ttu-id="9f24a-103">FlatFileReceive サンプルは、[!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)] を使用してフラット ファイルを同等の .xml ファイルに変換する方法を示します。</span><span class="sxs-lookup"><span data-stu-id="9f24a-103">The FlatFileReceive sample demonstrates how you can use [!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)] to process a flat file into the equivalent .xml file.</span></span>  

## <a name="what-this-sample-does"></a><span data-ttu-id="9f24a-104">このサンプルの処理</span><span class="sxs-lookup"><span data-stu-id="9f24a-104">What This Sample Does</span></span>  
 <span data-ttu-id="9f24a-105">このサンプルでは、FFInput フォルダを受信場所として構成します。</span><span class="sxs-lookup"><span data-stu-id="9f24a-105">This sample configures the folder FFInput as a receive location.</span></span> <span data-ttu-id="9f24a-106">このフォルダーにサンプル ファイル FlatFileReceive_in.txt のようなファイルを置くと、[!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)] はこのファイル内のメッセージを次の手順で処理します。</span><span class="sxs-lookup"><span data-stu-id="9f24a-106">When you place a file, such as the sample file FlatFileReceive_in.txt, into this folder, [!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)] processes the message in this file using the following sequence of steps:</span></span>  

1.  <span data-ttu-id="9f24a-107">受信場所フォルダ FFInput の入力ファイルからメッセージを読み取ります。</span><span class="sxs-lookup"><span data-stu-id="9f24a-107">Reads the message from the input file in the receive location folder FFInput.</span></span>  

2.  <span data-ttu-id="9f24a-108">受信パイプラインにおいて、フラット ファイル逆アセンブラ コンポーネントが、メッセージをフラット ファイル形式から同等の XML メッセージに変換します。</span><span class="sxs-lookup"><span data-stu-id="9f24a-108">In the receive pipeline, the Flat File Disassembler component converts the message from flat file format to the equivalent XML message.</span></span>  

3.  <span data-ttu-id="9f24a-109">MessageBox データベース内で、メッセージが FILE 送信ポートに回送されます。この送信ポートは、XML メッセージを送信アダプタ フォルダ FFOutput 内のファイルに書き込みます。</span><span class="sxs-lookup"><span data-stu-id="9f24a-109">In the MessageBox database, the message is routed to a FILE send port that writes the XML message to a file in the send adapter folder FFOutput.</span></span>  

## <a name="how-this-sample-is-designed-and-why"></a><span data-ttu-id="9f24a-110">このサンプルのデザイン方法とその理由</span><span class="sxs-lookup"><span data-stu-id="9f24a-110">How This Sample is Designed and Why</span></span>  
 <span data-ttu-id="9f24a-111">サンプル メッセージはこのサンプル内の基本デザインの多くを示しています。</span><span class="sxs-lookup"><span data-stu-id="9f24a-111">The sample message dictates much of the basic design in this sample.</span></span> <span data-ttu-id="9f24a-112">フラット ファイル メッセージは、フラット ファイル逆アセンブラおよびカスタム受信パイプライン内のフラット ファイル スキーマを使用して逆アセンブルする必要があります。</span><span class="sxs-lookup"><span data-stu-id="9f24a-112">Flat file messages must be disassembled using the Flat File Disassembler and a flat file schema within a custom receive pipeline.</span></span> <span data-ttu-id="9f24a-113">これらのデザイン要素と他のデザイン要素を次の表にまとめます。</span><span class="sxs-lookup"><span data-stu-id="9f24a-113">These and other design elements are summarized in the following table.</span></span>  


|     <span data-ttu-id="9f24a-114">デザイン要素</span><span class="sxs-lookup"><span data-stu-id="9f24a-114">Design element</span></span>      |                                                                                                                                                                  <span data-ttu-id="9f24a-115">選択理由</span><span class="sxs-lookup"><span data-stu-id="9f24a-115">Reason(s) selected</span></span>                                                                                                                                                                   |
|-------------------------|-------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------|
| <span data-ttu-id="9f24a-116">カスタム受信パイプライン</span><span class="sxs-lookup"><span data-stu-id="9f24a-116">Custom receive pipeline</span></span> | <span data-ttu-id="9f24a-117">-カスタム パイプラインはフラット ファイル逆アセンブラーを使用し、変換、受信するフラット ファイル スキーマは、注文メッセージを購入します。</span><span class="sxs-lookup"><span data-stu-id="9f24a-117">-   The custom pipeline uses the Flat File Disassembler and a flat file schema to translate inbound purchase order messages.</span></span> <span data-ttu-id="9f24a-118">フラット ファイル逆アセンブラー自体はパイプラインではなく、[!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)] 管理コンソールでの受信パイプラインの構成時に使用することはできません。</span><span class="sxs-lookup"><span data-stu-id="9f24a-118">The Flat File Disassembler is not itself a pipeline and cannot be used when configuring a receive pipeline in the [!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)] Management console.</span></span> |
|    <span data-ttu-id="9f24a-119">フラット ファイル スキーマ</span><span class="sxs-lookup"><span data-stu-id="9f24a-119">Flat file schema</span></span>     |                           <span data-ttu-id="9f24a-120">-すべての定義、同じレコードとフィールドの特性 (構造体を含む) を XML スキーマとして、すべてのフラット ファイル インスタンス メッセージを同等の XML インスタンスに変換するために必要なフラット ファイルの特性を定義するためのメカニズムを提供メッセージ (またはその逆)。</span><span class="sxs-lookup"><span data-stu-id="9f24a-120">-   Define all of the same record and field characteristics (including structure) as an XML schema and provide a mechanism for defining all of the flat file characteristics that are required to translate a flat file instance message into an equivalent XML instance message (or vice versa).</span></span>                           |
|   <span data-ttu-id="9f24a-121">サブスクリプション フィルター</span><span class="sxs-lookup"><span data-stu-id="9f24a-121">Subscription filter</span></span>   |                                                                                                        <span data-ttu-id="9f24a-122">-サブスクリプション フィルターは、プロパティ フィールドに基づいて 1 つまたは複数の条件を満たすメッセージをキャプチャすることで実際のルーティングを実行します。</span><span class="sxs-lookup"><span data-stu-id="9f24a-122">-   The subscription filter performs the actual routing by capturing messages that meet one or more criteria based on property fields.</span></span>                                                                                                         |
|       <span data-ttu-id="9f24a-123">XMLTransmit</span><span class="sxs-lookup"><span data-stu-id="9f24a-123">XMLTransmit</span></span>       |                                                                                                           <span data-ttu-id="9f24a-124">-出力方向の基本的なアセンブリを実行する XML メッセージを必要な箇所です。</span><span class="sxs-lookup"><span data-stu-id="9f24a-124">-   Performs basic assembly of outgoing XML messages where needed.</span></span> <span data-ttu-id="9f24a-125">PassThruTransmit パイプラインでは追加のサポートは行われません。</span><span class="sxs-lookup"><span data-stu-id="9f24a-125">The PassThruTransmit pipeline provides no additional support.</span></span>                                                                                                            |

 <span data-ttu-id="9f24a-126">これらの要素が組み合わされて、フラット ファイル形式の注文書メッセージを受信場所から受け入れ、変換した XML 表現を送信場所に書き込むソリューションが作成されます。</span><span class="sxs-lookup"><span data-stu-id="9f24a-126">These elements are combined to produce a solution that accepts purchase order messages in flat file format from the receive location and writes out the resulting XML representation to the send location.</span></span>  

 <span data-ttu-id="9f24a-127">このサンプルの設計には次の考慮事項が適用されます。</span><span class="sxs-lookup"><span data-stu-id="9f24a-127">The following considerations apply to the design of this sample:</span></span>  

-   <span data-ttu-id="9f24a-128">フラット ファイル スキーマ (PO.xsd) には、注文書フラット ファイルの構造を記述した拡張注釈が含まれています。</span><span class="sxs-lookup"><span data-stu-id="9f24a-128">The flat file schema (PO.xsd) contains extended annotations describing the structure of the purchase order flat file.</span></span> <span data-ttu-id="9f24a-129">これらのファイルは手動で作成できますが、その多くはフラット ファイル ウィザードを使用して生成できます。</span><span class="sxs-lookup"><span data-stu-id="9f24a-129">These files can be created by hand, but many can be generated by using the Flat File Wizard.</span></span>  

-   <span data-ttu-id="9f24a-130">フラット ファイル スキーマは Unqualified の elementFormDefault 値を使用します。</span><span class="sxs-lookup"><span data-stu-id="9f24a-130">The flat file schema uses an elementFormDefault value of Unqualified.</span></span> <span data-ttu-id="9f24a-131">これにより正しい結果がもたらされますが、結果には予期しない XML 名前空間 (xmlns) 修飾が追加されます。</span><span class="sxs-lookup"><span data-stu-id="9f24a-131">This produces correct results but with additional and unexpected XML namespace (xmlns) qualifications.</span></span> <span data-ttu-id="9f24a-132">この問題を避けるには、Qualified の elementFormDefault を使用してください。</span><span class="sxs-lookup"><span data-stu-id="9f24a-132">Use an elementFormDefault of Qualified to avoid this issue.</span></span>  

-   <span data-ttu-id="9f24a-133">XmlTransmit が送信パイプラインとして使用されます。</span><span class="sxs-lookup"><span data-stu-id="9f24a-133">XmlTransmit is used as the send pipeline.</span></span> <span data-ttu-id="9f24a-134">プロパティの降格または他のメッセージ処理が送信ポートで必要ない場合は、PassThruTransmit パイプラインを使用してください。</span><span class="sxs-lookup"><span data-stu-id="9f24a-134">Use the PassThruTransmit pipeline when property demotion or other messaging processing is not required in the send port.</span></span>  

## <a name="where-to-find-this-sample"></a><span data-ttu-id="9f24a-135">このサンプルの場所</span><span class="sxs-lookup"><span data-stu-id="9f24a-135">Where to Find This Sample</span></span>  
 <span data-ttu-id="9f24a-136">*\<パスのサンプル\>* \Pipelines\AssemblerDisassembler\FlatFileReceive\\</span><span class="sxs-lookup"><span data-stu-id="9f24a-136">*\<Samples Path\>* \Pipelines\AssemblerDisassembler\FlatFileReceive\\</span></span>  

 <span data-ttu-id="9f24a-137">次の表は、このサンプルのファイルとその目的を示しています。</span><span class="sxs-lookup"><span data-stu-id="9f24a-137">The following table shows the files in this sample and describes their purpose.</span></span>  


|                   <span data-ttu-id="9f24a-138">ファイル</span><span class="sxs-lookup"><span data-stu-id="9f24a-138">File(s)</span></span>                   |                                                                                           <span data-ttu-id="9f24a-139">説明</span><span class="sxs-lookup"><span data-stu-id="9f24a-139">Description</span></span>                                                                                            |
|---------------------------------------------|--------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------|
|                 <span data-ttu-id="9f24a-140">Cleanup.bat</span><span class="sxs-lookup"><span data-stu-id="9f24a-140">Cleanup.bat</span></span>                 | <span data-ttu-id="9f24a-141">アセンブリの展開を解除し、グローバル アセンブリ キャッシュからアセンブリを削除するために使用されます。</span><span class="sxs-lookup"><span data-stu-id="9f24a-141">Used to undeploy assemblies and remove them from the global assembly cache.</span></span> <span data-ttu-id="9f24a-142">送信ポートと受信ポートが削除されます。</span><span class="sxs-lookup"><span data-stu-id="9f24a-142">Removes send and receive ports.</span></span> <span data-ttu-id="9f24a-143">必要に応じて、Microsoft インターネット インフォメーション サービス (IIS) の仮想ディレクトリが削除されます。</span><span class="sxs-lookup"><span data-stu-id="9f24a-143">Removes Microsoft Internet Information Services (IIS) virtual directories as needed.</span></span> |
|            <span data-ttu-id="9f24a-144">FFReceivePipeline.btp</span><span class="sxs-lookup"><span data-stu-id="9f24a-144">FFReceivePipeline.btp</span></span>            |                       [!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)]<span data-ttu-id="9f24a-145"> は、フラット ファイル逆アセンブラー コンポーネントを含むパイプライン ファイルを受信します。</span><span class="sxs-lookup"><span data-stu-id="9f24a-145"> receive pipeline file with the Flat File Disassembler component.</span></span>                        |
| <span data-ttu-id="9f24a-146">FlatFileReceive.btproj, FlatFileReceive.sln</span><span class="sxs-lookup"><span data-stu-id="9f24a-146">FlatFileReceive.btproj, FlatFileReceive.sln</span></span> |                                                                           <span data-ttu-id="9f24a-147">このサンプルのプロジェクト ファイルとソリューション ファイルです。</span><span class="sxs-lookup"><span data-stu-id="9f24a-147">Project and solution files for this sample.</span></span>                                                                            |
|           <span data-ttu-id="9f24a-148">FlatFileReceive_in.txt</span><span class="sxs-lookup"><span data-stu-id="9f24a-148">FlatFileReceive_in.txt</span></span>            |                                                                                        <span data-ttu-id="9f24a-149">サンプル入力ファイルです。</span><span class="sxs-lookup"><span data-stu-id="9f24a-149">Sample input file.</span></span>                                                                                        |
|         <span data-ttu-id="9f24a-150">FlatFileReceiveBinding.xml</span><span class="sxs-lookup"><span data-stu-id="9f24a-150">FlatFileReceiveBinding.xml</span></span>          |                                                                          <span data-ttu-id="9f24a-151">ポートのバインドなど、自動化されたセットアップに使用されます。</span><span class="sxs-lookup"><span data-stu-id="9f24a-151">Used for automated setup such as port binding.</span></span>                                                                          |
|                   <span data-ttu-id="9f24a-152">PO.xsd</span><span class="sxs-lookup"><span data-stu-id="9f24a-152">PO.xsd</span></span>                    |                                                                                <span data-ttu-id="9f24a-153">受信フラット ファイルのスキーマです。</span><span class="sxs-lookup"><span data-stu-id="9f24a-153">Schema for the inbound flat file.</span></span>                                                                                 |
|                  <span data-ttu-id="9f24a-154">Setup.bat</span><span class="sxs-lookup"><span data-stu-id="9f24a-154">Setup.bat</span></span>                  |                                                                            <span data-ttu-id="9f24a-155">このサンプルをビルドおよび初期化するために使用されます。</span><span class="sxs-lookup"><span data-stu-id="9f24a-155">Used to build and initialize this sample.</span></span>                                                                             |

## <a name="how-to-use-this-sample"></a><span data-ttu-id="9f24a-156">このサンプルの使用方法</span><span class="sxs-lookup"><span data-stu-id="9f24a-156">How to Use This Sample</span></span>  
 <span data-ttu-id="9f24a-157">このサンプルは、独自のフラット ファイル処理ソリューションの基礎として使用してください。</span><span class="sxs-lookup"><span data-stu-id="9f24a-157">Use this sample as the basis for your own flat file processing solution.</span></span> <span data-ttu-id="9f24a-158">このサンプルで使用されているデザイン要素の多くは、独自の要件に合うように拡張できます。</span><span class="sxs-lookup"><span data-stu-id="9f24a-158">You can extend many of the design elements used in this sample to fit your own requirements.</span></span>  

## <a name="building-and-initializing-this-sample"></a><span data-ttu-id="9f24a-159">このサンプルのビルドと初期化</span><span class="sxs-lookup"><span data-stu-id="9f24a-159">Building and Initializing This Sample</span></span>  

1. <span data-ttu-id="9f24a-160">コマンド ウィンドウで、次のフォルダーに移動します。</span><span class="sxs-lookup"><span data-stu-id="9f24a-160">In a command window, navigate to the following folder:</span></span>  

    <span data-ttu-id="9f24a-161">*\<パスのサンプル\>* \Pipelines\AssemblerDisassembler\FlatFileReceive</span><span class="sxs-lookup"><span data-stu-id="9f24a-161">*\<Samples Path\>* \Pipelines\AssemblerDisassembler\FlatFileReceive</span></span>  

2. <span data-ttu-id="9f24a-162">ファイルは、次の操作を実行します。 Setup.bat を実行します。</span><span class="sxs-lookup"><span data-stu-id="9f24a-162">Run the file Setup.bat, which performs the following actions:</span></span>  

   - <span data-ttu-id="9f24a-163">次のフォルダに、このサンプルの入力 (FFInput) フォルダと出力 (FFOutput) フォルダを作成します。</span><span class="sxs-lookup"><span data-stu-id="9f24a-163">Creates the input (FFInput) and output (FFOutput) folders for this sample in the folder:</span></span>  

      <span data-ttu-id="9f24a-164">*\<パスのサンプル\>* \Pipelines\AssemblerDisassembler\FlatFileReceive</span><span class="sxs-lookup"><span data-stu-id="9f24a-164">*\<Samples Path\>* \Pipelines\AssemblerDisassembler\FlatFileReceive</span></span>  

   - <span data-ttu-id="9f24a-165">このサンプル用に Visual Studio プロジェクトをコンパイルおよび展開します。</span><span class="sxs-lookup"><span data-stu-id="9f24a-165">Compiles and deploys the Visual Studio project for this sample.</span></span>  

   - <span data-ttu-id="9f24a-166">[!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)] の受信場所、送信ポート、および受信ポートを作成しバインドします。</span><span class="sxs-lookup"><span data-stu-id="9f24a-166">Creates and binds the [!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)] receive location, and the send and receive ports.</span></span>  

     > [!NOTE]
     >  <span data-ttu-id="9f24a-167">このサンプルには、作成してポートをバインドする場合は、次の警告が表示されます:`Warning: Receive handler not specified for receive location "FlatFileReceive_RL"; updating with first receive handler with matching transport type.`これらの警告を無視してかまいません。</span><span class="sxs-lookup"><span data-stu-id="9f24a-167">This sample displays the following warning when creating and binding ports: `Warning: Receive handler not specified for receive location "FlatFileReceive_RL"; updating with first receive handler with matching transport type.` You can safely ignore these warnings.</span></span> <span data-ttu-id="9f24a-168">(インストールでの名前付け方法はユーザーによって異なる可能性があるため、ホスト名と受信ハンドラーはバインド ファイルから除外されています。)</span><span class="sxs-lookup"><span data-stu-id="9f24a-168">(To accommodate for possible naming differences in user installations, the host name and receive handler have been omitted from the binding file.)</span></span>  

   - <span data-ttu-id="9f24a-169">受信場所を有効にし、送信ポートを開始します。</span><span class="sxs-lookup"><span data-stu-id="9f24a-169">Enables the receive location, and starts the send port.</span></span>  

> [!NOTE]
>  <span data-ttu-id="9f24a-170">このサンプルを実行する前に、ビルドと初期化のプロセス中に [!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)] でエラーが報告されていないことを確認する必要があります。</span><span class="sxs-lookup"><span data-stu-id="9f24a-170">You should confirm that [!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)] did not report any errors during the build and initialization process before attempting to run this sample.</span></span>  
> 
> [!NOTE]
>  <span data-ttu-id="9f24a-171">開き、Setup.bat を実行することがなく、このサンプルでは、プロジェクトをビルドする場合は、まず、.NET Framework の厳密名ユーティリティ (sn.exe) を使用して厳密な名前キーのペアを作成する必要があります。</span><span class="sxs-lookup"><span data-stu-id="9f24a-171">If you choose to open and build the project in this sample without running Setup.bat, you must first create a strong name key pair using the .NET Framework Strong Name utility (sn.exe).</span></span> <span data-ttu-id="9f24a-172">結果として得られるアセンブリに署名するのにには、このキー ペアを使用します。</span><span class="sxs-lookup"><span data-stu-id="9f24a-172">Use this key pair to sign the resulting assembly.</span></span>  
> 
> [!NOTE]
>  <span data-ttu-id="9f24a-173">Setup.bat によって行われた変更を元に戻すには、Cleanup.bat を実行します。</span><span class="sxs-lookup"><span data-stu-id="9f24a-173">To undo changes made by Setup.bat, run Cleanup.bat.</span></span> <span data-ttu-id="9f24a-174">Setup.bat を 2 回目に実行する場合は、その前に Cleanup.bat を実行してください。</span><span class="sxs-lookup"><span data-stu-id="9f24a-174">You must run Cleanup.bat before running Setup.bat a second time.</span></span>  

## <a name="running-this-sample"></a><span data-ttu-id="9f24a-175">このサンプルの実行</span><span class="sxs-lookup"><span data-stu-id="9f24a-175">Running This Sample</span></span>  

1.  <span data-ttu-id="9f24a-176">ファイル FlatFileReceive_in.txt を FFInput フォルダにコピーします。</span><span class="sxs-lookup"><span data-stu-id="9f24a-176">Put a copy of the file FlatFileReceive_in.txt into the folder FFInput.</span></span>  

2.  <span data-ttu-id="9f24a-177">.xml ファイルが FFOutput フォルダに作成されることを確認します。</span><span class="sxs-lookup"><span data-stu-id="9f24a-177">Observe the .xml file created in the folder FFOutput.</span></span> <span data-ttu-id="9f24a-178">出力ファイルの名前はメッセージ ID GUID に基づきます。</span><span class="sxs-lookup"><span data-stu-id="9f24a-178">The name of the output file is based on the message ID GUID.</span></span> <span data-ttu-id="9f24a-179">このファイルには、受信フォルダに配置されたフラット ファイルに相当する XML が含まれています。</span><span class="sxs-lookup"><span data-stu-id="9f24a-179">This file contains XML equivalent of the flat file placed in the receive folder.</span></span>  

## <a name="classes-or-methods-used-in-this-sample"></a><span data-ttu-id="9f24a-180">このサンプルで使用されるクラスまたはメソッド</span><span class="sxs-lookup"><span data-stu-id="9f24a-180">Classes or Methods Used in This Sample</span></span>  
 <span data-ttu-id="9f24a-181">Setup.bat および Cleanup.bat の 2 つの構成スクリプトは、次の管理用 Windows Management Instrumentation (WMI) スクリプトに依存しています。</span><span class="sxs-lookup"><span data-stu-id="9f24a-181">The configuration scripts Setup.bat and Cleanup.bat rely on the following administrative Windows Management Instrumentation (WMI) scripts:</span></span>  

- <span data-ttu-id="9f24a-182">Start Send Port\StartSendPort.vbs</span><span class="sxs-lookup"><span data-stu-id="9f24a-182">Start Send Port\StartSendPort.vbs</span></span>  

- <span data-ttu-id="9f24a-183">Enable Receive Location\EnableRecLoc</span><span class="sxs-lookup"><span data-stu-id="9f24a-183">Enable Receive Location\EnableRecLoc</span></span>  

- <span data-ttu-id="9f24a-184">Remove Send Port\RemoveSendPort</span><span class="sxs-lookup"><span data-stu-id="9f24a-184">Remove Send Port\RemoveSendPort</span></span>  

  <span data-ttu-id="9f24a-185">セットアップおよびクリーンアップのバッチ ファイルでは、次のように BTSTask を使用します。</span><span class="sxs-lookup"><span data-stu-id="9f24a-185">The setup and cleanup batch files use BTSTask as follows:</span></span>  

- <span data-ttu-id="9f24a-186">**BTSTask ImportBindings**バインド ファイルを適用し、アプリケーション、ポート、およびバインドを作成するには</span><span class="sxs-lookup"><span data-stu-id="9f24a-186">**BTSTask ImportBindings** to apply the binding file and create the application, ports, and bindings</span></span>  

- <span data-ttu-id="9f24a-187">**BTSTask RemoveApp** FlatFileReceiveApplication を削除するには</span><span class="sxs-lookup"><span data-stu-id="9f24a-187">**BTSTask RemoveApp** to remove the FlatFileReceiveApplication</span></span>  

## <a name="see-also"></a><span data-ttu-id="9f24a-188">参照</span><span class="sxs-lookup"><span data-stu-id="9f24a-188">See Also</span></span>  
- [<span data-ttu-id="9f24a-189">Pipelines-AssemblerDisassembler (BizTalk Server サンプル フォルダー)</span><span class="sxs-lookup"><span data-stu-id="9f24a-189">Pipelines-AssemblerDisassembler (BizTalk Server Samples Folder)</span></span>](../core/pipelines-assemblerdisassembler-biztalk-server-samples-folder.md)   
- [<span data-ttu-id="9f24a-190">フラット ファイル逆アセンブラー パイプライン コンポーネント</span><span class="sxs-lookup"><span data-stu-id="9f24a-190">Flat File Disassembler Pipeline Component</span></span>](../core/flat-file-disassembler-pipeline-component.md)   
- [<span data-ttu-id="9f24a-191">フラット ファイル スキーマ</span><span class="sxs-lookup"><span data-stu-id="9f24a-191">Flat File Schemas</span></span>](../core/flat-file-schemas.md)   
- [<span data-ttu-id="9f24a-192">既定のパイプライン</span><span class="sxs-lookup"><span data-stu-id="9f24a-192">Default Pipelines</span></span>](../core/default-pipelines.md)   
- <span data-ttu-id="9f24a-193">**WMI スクリプトのサンプル** [!INCLUDE[ui-guidance-developers-reference](../includes/ui-guidance-developers-reference.md)]</span><span class="sxs-lookup"><span data-stu-id="9f24a-193">**WMI Script Samples** [!INCLUDE[ui-guidance-developers-reference](../includes/ui-guidance-developers-reference.md)]</span></span>   
- [<span data-ttu-id="9f24a-194">BTSTask コマンド ライン リファレンス</span><span class="sxs-lookup"><span data-stu-id="9f24a-194">BTSTask Command-Line Reference</span></span>](../core/btstask-command-line-reference.md)   
- [<span data-ttu-id="9f24a-195">FlatFileSend (BizTalk Server サンプル)</span><span class="sxs-lookup"><span data-stu-id="9f24a-195">FlatFileSend (BizTalk Server Sample)</span></span>](../core/flatfilesend-biztalk-server-sample.md)
