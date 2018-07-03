---
title: パイプライン ツール |Microsoft Docs
ms.custom: ''
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: ''
ms.suite: ''
ms.tgt_pltfrm: ''
ms.topic: article
helpviewer_keywords:
- pipeline tools, XMLAsm.exe
- pipeline tools, FFDasm.exe
- Pipeline.exe
- FFDasm.exe
- pipeline tools, XMLDasm.exe
- pipeline tools
- XMLAsm.exe
- pipeline tools, DSDump.exe
- FFAsm.exe
- pipeline tools, FFAsm.exe
- pipeline tools, how to
- pipeline tools, about pipeline tools
- pipeline tools, Pipeline.exe
- utilities, pipeline tools
- XMLDasm.exe
ms.assetid: ca4d053a-1473-4d40-8cd0-1ed3a3af988a
caps.latest.revision: 8
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: 9c53791906e64930b39b15a89ca20bc269dc8cd9
ms.sourcegitcommit: 266308ec5c6a9d8d80ff298ee6051b4843c5d626
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 06/27/2018
ms.locfileid: "37017047"
---
# <a name="pipeline-tools"></a><span data-ttu-id="8e6f8-102">パイプライン ツール</span><span class="sxs-lookup"><span data-stu-id="8e6f8-102">Pipeline Tools</span></span>
<span data-ttu-id="8e6f8-103">Microsoft [!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)] ソフトウェア開発キット (SDK) 付属のパイプライン ツールを使用すると、送信ポートや受信ポートなどの BizTalk Server 環境を構成することなく、パイプラインが正しく機能するかどうかを確認できます。</span><span class="sxs-lookup"><span data-stu-id="8e6f8-103">The pipeline tools supplied with the Microsoft [!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)] Software Development Kit (SDK) enable you to verify that a pipeline is functioning correctly without having to configure the BizTalk Server environment, such as send/receive ports.</span></span> <span data-ttu-id="8e6f8-104">パイプライン ツールは次の用途にも使用できます。</span><span class="sxs-lookup"><span data-stu-id="8e6f8-104">You can also use the pipeline tools to:</span></span>  

-   <span data-ttu-id="8e6f8-105">サード パーティのパイプライン コンポーネントを、サーバー環境外でデバッグします。</span><span class="sxs-lookup"><span data-stu-id="8e6f8-105">Debug third-party pipeline components outside of the server environment.</span></span>  

-   <span data-ttu-id="8e6f8-106">解析エンジンのエラー メッセージを診断します。</span><span class="sxs-lookup"><span data-stu-id="8e6f8-106">Diagnose parsing engine error messages.</span></span>  

-   <span data-ttu-id="8e6f8-107">コンパイル、展開、展開解除、および再コンパイルを行うことなく、さまざまなスキーマをテストします。</span><span class="sxs-lookup"><span data-stu-id="8e6f8-107">Experiment with different schemas without the burden of compiling, deploying, undeploying, and recompiling.</span></span>  

-   <span data-ttu-id="8e6f8-108">フラット ファイルおよび XML のアセンブラー/逆アセンブラーの動作を検討します。</span><span class="sxs-lookup"><span data-stu-id="8e6f8-108">Explore flat file and XML assembler/disassembler behavior.</span></span>  

-   <span data-ttu-id="8e6f8-109">逆アセンブラーの出力を表示し、昇格したメッセージ コンテキスト プロパティとその値を確認します。</span><span class="sxs-lookup"><span data-stu-id="8e6f8-109">View disassembler output and discover which message context properties are promoted and their values.</span></span>  

-   <span data-ttu-id="8e6f8-110">逆アセンブラー コンポーネントやアセンブラー コンポーネントが含まれない送受信パイプラインを実行します (たとえば、S/MIME デコーダーの出力を表示できます)。</span><span class="sxs-lookup"><span data-stu-id="8e6f8-110">Run send/receive pipelines without disassembler and assembler components (for example, you can view the output of the S/MIME decoder).</span></span>  

-   <span data-ttu-id="8e6f8-111">メッセージング サブシステム全体ではなく、パイプラインのみに対し、詳細なパフォーマンス測定を行います。</span><span class="sxs-lookup"><span data-stu-id="8e6f8-111">Make fine-grained performance measurements of the pipeline alone (rather than the entire messaging subsystem).</span></span>  

## <a name="location-in-sdk"></a><span data-ttu-id="8e6f8-112">SDK でのパス</span><span class="sxs-lookup"><span data-stu-id="8e6f8-112">Location in SDK</span></span>  
 <span data-ttu-id="8e6f8-113">\<*インストール パス*\>\SDK\Utilities\PipelineTools</span><span class="sxs-lookup"><span data-stu-id="8e6f8-113">\<*Installation Path*\>\SDK\Utilities\PipelineTools</span></span>  

 <span data-ttu-id="8e6f8-114">パイプライン ツールは、パイプラインとパイプライン コンポーネント (フラット ファイルおよび XML のアセンブラー/逆アセンブラー コンポーネント) の実行、デバッグ、およびプロファイルに使用します。</span><span class="sxs-lookup"><span data-stu-id="8e6f8-114">You use pipeline tools for executing, debugging, and profiling pipelines, and pipeline components (that is, flat file and XML assembler/disassembler components).</span></span>  

## <a name="file-inventory"></a><span data-ttu-id="8e6f8-115">ファイルのインベントリ</span><span class="sxs-lookup"><span data-stu-id="8e6f8-115">File Inventory</span></span>  
 <span data-ttu-id="8e6f8-116">次の表は、パイプライン ツールのファイルとその目的を示しています。</span><span class="sxs-lookup"><span data-stu-id="8e6f8-116">The following table lists the pipeline tools files and describes their purpose.</span></span>  


|   <span data-ttu-id="8e6f8-117">ファイル</span><span class="sxs-lookup"><span data-stu-id="8e6f8-117">File(s)</span></span>    |                                                                                                                                                                                                                                <span data-ttu-id="8e6f8-118">説明</span><span class="sxs-lookup"><span data-stu-id="8e6f8-118">Description</span></span>                                                                                                                                                                                                                                 |
|--------------|----------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------|
|  <span data-ttu-id="8e6f8-119">DSDump.exe</span><span class="sxs-lookup"><span data-stu-id="8e6f8-119">DSDump.exe</span></span>  |                                                <span data-ttu-id="8e6f8-120">ドキュメント スキーマ構造をダンプするために使用します。この構造は、1 つ以上の XSD スキーマのメモリ内簡易表現で、フラット ファイルの注釈を含む場合と含まない場合があります。</span><span class="sxs-lookup"><span data-stu-id="8e6f8-120">Enables you to dump the document schema structure, which is an in-memory lightweight representation of the one or more XSD schemas, with or without flat file annotations.</span></span> <span data-ttu-id="8e6f8-121">$Root$0$3$2 などの解析エンジン エラーが発生し、デコードする必要がある場合に、このツールが役立ちます。</span><span class="sxs-lookup"><span data-stu-id="8e6f8-121">This tool can be helpful when you get parsing engine errors such as $Root$0$3$2 and you need to decode them.</span></span> <span data-ttu-id="8e6f8-122">$ 後の数値は、ドキュメント スキーマに表示される、0 から始まるインデックスまたはレコードを意味します。</span><span class="sxs-lookup"><span data-stu-id="8e6f8-122">Numbers after $ mean 0-based index or records as they appear in the document schema.</span></span>                                                |
|  <span data-ttu-id="8e6f8-123">FFAsm.exe</span><span class="sxs-lookup"><span data-stu-id="8e6f8-123">FFAsm.exe</span></span>   |                                                                                                                                     <span data-ttu-id="8e6f8-124">送信パイプラインをエミュレートすることにより、フラット ファイル アセンブラー コンポーネントを直接呼び出して実行し、ユーザーの XML ドキュメント (複数可) をフラット ファイル ドキュメントにシリアル化またはアセンブルするようすを表示します。</span><span class="sxs-lookup"><span data-stu-id="8e6f8-124">Runs the flat file assembler component, directly invoking it by emulating a send pipeline to enable you to see how it serializes or assembles a user's XML document(s) into a flat file document.</span></span>                                                                                                                                      |
|  <span data-ttu-id="8e6f8-125">FFDasm.exe</span><span class="sxs-lookup"><span data-stu-id="8e6f8-125">FFDasm.exe</span></span>  |                                                                                                                               <span data-ttu-id="8e6f8-126">受信パイプラインをエミュレートすることにより、フラット ファイル逆アセンブラー コンポーネントを直接呼び出して実行し、ユーザーのフラット ファイル ドキュメントを 1 つ以上の XML ドキュメントに解析または逆アセンブルするようすを表示します。</span><span class="sxs-lookup"><span data-stu-id="8e6f8-126">Runs the flat file disassembler component, directly invoking it by emulating a receive pipeline to enable you to see how it parses or disassembles a user's flat file document into one or more XML documents.</span></span>                                                                                                                               |
| <span data-ttu-id="8e6f8-127">Pipeline.exe</span><span class="sxs-lookup"><span data-stu-id="8e6f8-127">Pipeline.exe</span></span> | <span data-ttu-id="8e6f8-128">送信パイプラインまたは受信パイプラインを実行し、1 つ以上の入力ドキュメントとその部分、XSD スキーマ、および関連情報を受け取り、パイプラインの実行後に出力ドキュメントを生成します。</span><span class="sxs-lookup"><span data-stu-id="8e6f8-128">Runs a send or receive pipeline; accepts one or more input documents and their parts, XSD schemas and related information; and produces an output document after the pipeline runs.</span></span> <span data-ttu-id="8e6f8-129">Pipeline.exe は BizTalk Server データベースにアクセスしないので、実行時に [!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)] データベースにアクセスする BizTalk Framework アセンブラー コンポーネントや逆アセンブラー コンポーネントが含まれるパイプラインは、サポートされません。</span><span class="sxs-lookup"><span data-stu-id="8e6f8-129">Pipeline.exe does not access BizTalk Server databases, so pipelines containing BizTalk Framework assembler and disassembler components that access [!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)] databases during execution may not be supported.</span></span> |
|  <span data-ttu-id="8e6f8-130">XMLAsm.exe</span><span class="sxs-lookup"><span data-stu-id="8e6f8-130">XMLAsm.exe</span></span>  |                                                                                                                                 <span data-ttu-id="8e6f8-131">送信パイプラインをエミュレートすることにより、XML アセンブラー コンポーネントを直接呼び出して実行し、ユーザーの XML ドキュメント (複数可) を 1 つの出力 XML ドキュメントにシリアル化、アセンブル、またはエンベロープするようすを表示します。</span><span class="sxs-lookup"><span data-stu-id="8e6f8-131">Runs the XML assembler component, directly invoking it by emulating a send pipeline to enable you to see how it serializes, assembles, or envelopes a user's XML document(s) into an output XML document.</span></span>                                                                                                                                  |
| <span data-ttu-id="8e6f8-132">XMLDasm.exe</span><span class="sxs-lookup"><span data-stu-id="8e6f8-132">XMLDasm.exe</span></span>  |                                                                                                                             <span data-ttu-id="8e6f8-133">受信パイプラインをエミュレートすることにより、XML 逆アセンブラー コンポーネントを直接呼び出して実行し、ユーザーの XML ドキュメントを 1 つ以上の XML ドキュメントに解析、逆アセンブル、またはエンベロープ解除するようすを表示します。</span><span class="sxs-lookup"><span data-stu-id="8e6f8-133">Runs the XML disassembler component, directly invoking it by emulating a receive pipeline to enable you to see how it parses, disassembles, or un-envelopes a user's XML document into one or more XML documents.</span></span>                                                                                                                              |

## <a name="usage"></a><span data-ttu-id="8e6f8-134">使用方法</span><span class="sxs-lookup"><span data-stu-id="8e6f8-134">Usage</span></span>  
 <span data-ttu-id="8e6f8-135">以下のセクションで、各ファイルについてさらに詳しく説明します。</span><span class="sxs-lookup"><span data-stu-id="8e6f8-135">A more detailed description of each file is provided in the sections that follow.</span></span>  

### <a name="dsdumpexe"></a><span data-ttu-id="8e6f8-136">DSDump.exe</span><span class="sxs-lookup"><span data-stu-id="8e6f8-136">DSDump.exe</span></span>  
 <span data-ttu-id="8e6f8-137">DSDump.exe を使用すると、ドキュメント スキーマ構造をダンプできます。この構造は、1 つ以上の XSD スキーマのメモリ内簡易表現で、フラット ファイルの注釈を含む場合と含まない場合があります。</span><span class="sxs-lookup"><span data-stu-id="8e6f8-137">DSDump.exe enables you to dump the document schema structure, which is an in-memory lightweight representation of one or more XSD schemas, with or without flat file annotations.</span></span>  

 <span data-ttu-id="8e6f8-138">DSDump.exe (ドキュメント スキーマ ダンプ ツール) は、次のコマンド ライン パラメーターをサポートしています。</span><span class="sxs-lookup"><span data-stu-id="8e6f8-138">DSDump.exe (document schema dump tool) supports the following command-line parameter:</span></span>  

```  
DSDump.exe schemaFileName  
```  

 <span data-ttu-id="8e6f8-139">DSDump が成功すると、コンソールにドキュメント スキーマが出力されます。</span><span class="sxs-lookup"><span data-stu-id="8e6f8-139">In case of success, DSDump prints the document schema to the console.</span></span>  

### <a name="ffasmexe"></a><span data-ttu-id="8e6f8-140">FFAsm.exe</span><span class="sxs-lookup"><span data-stu-id="8e6f8-140">FFAsm.exe</span></span>  
 <span data-ttu-id="8e6f8-141">FFAsm.exe (フラット ファイル アセンブラー) は、次のコマンド ライン パラメーターをサポートしています。</span><span class="sxs-lookup"><span data-stu-id="8e6f8-141">FFAsm.exe (flat file assembler) supports the following command-line parameters:</span></span>  

```  
usage: ffasm document... [-dm documentMask...]-bs bodySchema [ -hs headerSchema ] [ -ts trailerSchema ] [ -c ] [ -d ] [ -sb ] [ -m filenamemask ] [ -en encoding ] [ -v ]  

where:  
  document           XML document(s)  
  documentMask       XML document(s) file mask, e.g., c:\\documents\\*.xml  
  bodySchema         Flat File body schema  
  headerSchema       Flat File header schema  
  trailerSchema      Flat File trailer schema  
  -c                 Display assembled FF message on the console  
  -d                 Demote properties  
  -sb                Set body schema(s) as design-time property  
  -m                 Output file name mask (default is %MessageID%)  
  encoding           Output message encoding name (e.g. windows-1252) or   
                         code page (e.g. 936)  
  -v                 Verbose mode  

file name macros:  
  %MessageID%        FF message identifier (Guid)  
  %MessagePartID%    FF message part identifier (Guid)  

```  

 <span data-ttu-id="8e6f8-142">たとえば、3 つの入力 XML ドキュメントを、ヘッダーを持つ 1 つのフラット ファイル ドキュメントにアセンブルし、プロパティを降格するには、次のコマンドを使用します。</span><span class="sxs-lookup"><span data-stu-id="8e6f8-142">For example, if you want to assemble three input XML documents into a single flat file document with a header and property demotion, use the following command:</span></span>  

```  
FFAsm.exe file_in1.xml file_in2.xml file_in3.xml –hs myHeaderSchema.xsd –bs myBodySchema.xsd -d  
```  

### <a name="ffdasmexe"></a><span data-ttu-id="8e6f8-143">FFDasm.exe</span><span class="sxs-lookup"><span data-stu-id="8e6f8-143">FFDasm.exe</span></span>  
 <span data-ttu-id="8e6f8-144">FFDasm.exe (フラット ファイル 逆アセンブラー) は、次のコマンド ライン パラメーターをサポートしています。</span><span class="sxs-lookup"><span data-stu-id="8e6f8-144">FFDasm.exe (flat file disassembler) supports the following command-line parameters:</span></span>  

```  
usage: ffdasm document -bs bodySchema [ -hs headerSchema ] [ -ts trailerSchema ] [ -s ] [ -c ] [ -p ] [ -m filenamemask ] [ -en encoding ] [ -v ]  

where:  
  document           Flat File document  
  bodySchema         Flat File body schema  
  headerSchema       Flat File header schema  
  trailerSchema      Flat File trailer schema  
  -s                 Validate document structure  
  -c                 Display disassembled XML message on the console  
  -p                 Display promoted properties on the console  
  encoding           Input message body part encoding name (e.g. windows-1252) or code page (e.g., 396)  
  -m                 Output file name mask (default is %MessageID%)  
  -v                 Verbous mode  

file name macros:  
  %MessageID%        XML message identifier (Guid)  
  %MessagePartID%    XML message part identifier (Guid)  

```  

 <span data-ttu-id="8e6f8-145">たとえば、ヘッダー、ボディ、およびトレーラーを持つフラット ファイル ドキュメントを逆アセンブルし、結果をコンソールに表示するには、次のコマンドを使用します。</span><span class="sxs-lookup"><span data-stu-id="8e6f8-145">For example, if you want to disassemble a flat file document that has a header, body, and trailer, and display the results to the console, use the following command:</span></span>  

```  
FFDasm.exe file_in.txt –hs myHeaderSchema.xsd –bs myBodySchema.xsd –ts myTrailerSchema.xsd –c  
```  

### <a name="pipelineexe"></a><span data-ttu-id="8e6f8-146">Pipeline.exe</span><span class="sxs-lookup"><span data-stu-id="8e6f8-146">Pipeline.exe</span></span>  
 <span data-ttu-id="8e6f8-147">Pipeline.exe (パイプライン ツール) は、次のコマンド ライン パラメーターをサポートしています。</span><span class="sxs-lookup"><span data-stu-id="8e6f8-147">Pipeline.exe (the Pipeline tool) supports the following command-line parameters:</span></span>  

```  
usage: pipeline ( pipeline[.btp] | -pt pipelineTypeName [ -an assemblyName ] ) -d document... [ -part part... ] [ -s schema[.xsd][:namespace.type]... ] [ -proj project[.btproj] ] [ -p ] [ -c ] [ -t ] [ -m filenamemask ] [ -pm partfilenamemask ] [ -en encoding ] [ -v ]  

where:  
  pipeline                Pipeline file name  
  pipelineTypeName     Compiled pipeline assembly qualified type name (e.g.   
"MyPipelines.ReceivePipeline, MyPipelines,   
Version=1.0.0.0, Culture=neutral,   
PublicKeyToken=e03965cb5971ad66" or full name (e.g.   
"MyPipelines.ReceivePipeline") if assembly name is   
specified  
  assemblyName         Compiled pipeline assembly file name (e.g.   
MyPipelines.dll) or name (e.g. "MyPipelines,   
Version=1.0.0.0, Culture=neutral,   
PublicKeyToken=e03965cb5971ad66")  
  document             Input document(s)  
  part                 Input document's part  
  schema               Schema file name  
  namespace            Schema namespace (as in BizTalk project system)  
  type                 Schema type (as in BizTalk project system)  
  project              BizTalk project file  
  -p                   Display promoted context properties for receive and   
send pipelines, and promote context properties for   
send pipelines  
  -c                      Display output document on the console  
  -t                      Display elapsed time of components execution  
  filenamemask         Output message file name mask (default is   
Message_%MessageID%.out)  
  partfilenamemask     Output part file name mask (default is   
Part_%MessagePartID%.out)  
  encoding             Output message encoding name (e.g. windows-1252)   
or code page (e.g. 936)  
  -v                   Verbous mode  

note:  
You can specify namespace and type for schemas either using namespace.type notation in schema file reference or by using BizTalk project file.  

file name macros:  
  %MessageID%           Message identifier (Guid)  
  %MessagePartID%       Message part identifier (Guid)  
  %MessageNumber%       Message number  

```  

 <span data-ttu-id="8e6f8-148">たとえば、ファイル ReceivePipeline.btp (XML 逆アセンブラー コンポーネントと XML 検証コンポーネントが含まれる) から mySchema.xsd を使用して受信パイプラインを実行し、結果をコンソールに表示するには、次のコマンドを使用します。</span><span class="sxs-lookup"><span data-stu-id="8e6f8-148">For example, if you want to run a receive pipeline from the file ReceivePipeline.btp (which has XML disassembler and XML validator components) using mySchema.xsd and display the results to the console, use the following command:</span></span>  

```  
Pipeline.exe ReceivePipeline.btp –d file_in.xml –s MySchema.xsd:MyProject.MySchema -c  

```  

 <span data-ttu-id="8e6f8-149">\- または -</span><span class="sxs-lookup"><span data-stu-id="8e6f8-149">\- Or -</span></span>  

```  
Pipeline.exe ReceivePipeline.btp –d file_in.xml –s MySchema.xsd –proj MyProject.btproj -c  

```  

 <span data-ttu-id="8e6f8-150">最初の例では、修飾型名 (**MyProject.MySchema**)、スキーマは、コマンドラインの引数として含まれています。</span><span class="sxs-lookup"><span data-stu-id="8e6f8-150">In the first example, a qualified type name (**MyProject.MySchema**) for the schema is included as a command-line argument.</span></span> <span data-ttu-id="8e6f8-151">2 番目の例では、指定した BizTalk プロジェクト ファイルからスキーマが取得されます。</span><span class="sxs-lookup"><span data-stu-id="8e6f8-151">In the second example, the schema is obtained from the specified BizTalk project file.</span></span>  

 <span data-ttu-id="8e6f8-152">コンパイルされた [!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)] プロジェクト ファイルからパイプラインを実行することもできます。次に例を示します (パイプラインはアセンブリ修飾型名によって参照されています)。</span><span class="sxs-lookup"><span data-stu-id="8e6f8-152">You can also run pipelines from the compiled [!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)] project files, as in the following example (the pipeline is referenced by its assembly-qualified type name):</span></span>  

```  
Pipeline.exe -pt "TestBtsProject.ReceivePipeline, TestBtsProject, Version=1.0.0.0, Culture=neutral, PublicKeyToken=e03965cb5971ad66" -d in.xml -s PO.xsd -proj TestBtsProject.btproj –c  
```  

 <span data-ttu-id="8e6f8-153">次の例では、型名とアセンブリ ファイル名でそれぞれ個別にパイプラインが参照されています。</span><span class="sxs-lookup"><span data-stu-id="8e6f8-153">In the following example, a pipeline is referenced by its type name and assembly file name separately:</span></span>  

```  
Pipeline.exe -pt TestBtsProject.ReceivePipeline –an TestBtsProject.dll -d in.xml -s PO.xsd -proj TestBtsProject.btproj –c   
```  

 <span data-ttu-id="8e6f8-154">次の例では、アセンブリ名によってパイプラインが参照されています。</span><span class="sxs-lookup"><span data-stu-id="8e6f8-154">The following example shows a pipeline referenced by its assembly name:</span></span>  

```  
Pipeline.exe -pt TestBtsProject.ReceivePipeline –an "TestBtsProject, Version=1.0.0.0, Culture=neutral, PublicKeyToken=e03965cb5971ad66" -d in.xml -s PO.xsd -proj TestBtsProject.btproj –c  
```  

 <span data-ttu-id="8e6f8-155">Pipeline.exe は、起動時に使用した資格情報で実行されます。</span><span class="sxs-lookup"><span data-stu-id="8e6f8-155">Pipeline.exe runs with whatever credentials you have used to launch it.</span></span> <span data-ttu-id="8e6f8-156">通常の [!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)] ホスト インスタンスを実行するアカウントは使用されません。このため、データベース アクセスを必要とするコンポーネントが含まれているパイプラインは、実行できないことがあります。</span><span class="sxs-lookup"><span data-stu-id="8e6f8-156">It does not use the account that normal [!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)] host instances run under, so you may not be able to run pipelines that contain components that require database access.</span></span> <span data-ttu-id="8e6f8-157">Pipeline.exe を実行するアカウントに、必要な特権がすべて含まれていることを確認してください。</span><span class="sxs-lookup"><span data-stu-id="8e6f8-157">Make sure you run Pipeline.exe under an account that has all the required privileges.</span></span>  

 <span data-ttu-id="8e6f8-158">Pipeline.exe は、サード パーティのカスタム コンポーネントが含まれないカスタム パイプラインを確認するためにのみ使用してください。</span><span class="sxs-lookup"><span data-stu-id="8e6f8-158">You should only use Pipeline.exe to verify custom pipelines without third-party custom components.</span></span> <span data-ttu-id="8e6f8-159">サード パーティのカスタム コンポーネントが含まれたカスタム パイプラインを確認するために Pipeline.exe を使用しても、必要な出力は生成されます。</span><span class="sxs-lookup"><span data-stu-id="8e6f8-159">If you use pipeline.exe to verify a custom pipeline with third-party custom components, Pipeline.exe will produce the desired output.</span></span> <span data-ttu-id="8e6f8-160">しかし、サード パーティのカスタム コンポーネントが含まれたカスタム パイプラインを展開した場合、受信ポートまたは送信ポートでこのパイプラインを使用し、その後 Pipeline.exe を使用してパイプラインにメッセージを送信すると、パイプラインは失敗し、BizTalk Server からエラーが返されます。</span><span class="sxs-lookup"><span data-stu-id="8e6f8-160">However, if you deploy the same custom pipeline with third-party custom components, use the pipeline in a receive or send port, and then use Pipeline.exe to submit a message to the pipeline, the pipeline will fail and BizTalk Server will return an error.</span></span>  

### <a name="xmlasmexe"></a><span data-ttu-id="8e6f8-161">XMLAsm.exe</span><span class="sxs-lookup"><span data-stu-id="8e6f8-161">XMLAsm.exe</span></span>  
 <span data-ttu-id="8e6f8-162">XMLAsm.exe (XML アセンブラー ツール) は、次のコマンド ライン パラメーターをサポートしています。</span><span class="sxs-lookup"><span data-stu-id="8e6f8-162">XMLAsm.exe  (XML Assembler tool) supports the following command-line parameters:</span></span>  

```  
usage: xmlasm document...[-dm documentmask...] -ds documentSchema... [ -es envelopeSchema... ] [ -c ] [ -d ] [ -sd ] [ -m filenamemask ] [ -v ]  

where:  
  document           XML document(s)  
  documentMask       XML document(s) file mask, e.g., c:\\documents\\*.xml  
  documentSchema     XML document schema(s)  
  envelopeSchema     XML envelope schema(s)  
  -c                 Display assembled XML message on the console  
  -d                 Demote properties  
  -sd                Set document schema(s) as design-time property  
  -d                 Demote properties  
  -m                 Output file name mask (default is %MessageID%)  
  -v                 Verbous mode  

file name macros:  
  %MessageID%        XML message identifier (Guid)  
  %MessagePartID%    XML message part identifier (Guid)  

```  

 <span data-ttu-id="8e6f8-163">たとえば、2 つの入力 XML ドキュメントを、エンベロープを持つ 1 つの XML ドキュメントにアセンブルし、結果をコンソールに表示するには、次のコマンドを使用します。</span><span class="sxs-lookup"><span data-stu-id="8e6f8-163">For example, if you want to assemble two input XML documents into a single XML document with an envelope and display the results to the console, use the following command:</span></span>  

```  
FFAsm.exe file_in1.xml file_in2.xml–es myEnvelopeSchema.xsd –ds myBodySchema.xsd –c  
```  

### <a name="xmldasmexe"></a><span data-ttu-id="8e6f8-164">XMLDasm.exe</span><span class="sxs-lookup"><span data-stu-id="8e6f8-164">XMLDasm.exe</span></span>  
 <span data-ttu-id="8e6f8-165">XMLDasm.exe は、次のコマンド ライン パラメーターをサポートしています。</span><span class="sxs-lookup"><span data-stu-id="8e6f8-165">XMLDasm.exe supports the following command-line parameters:</span></span>  

```  
usage: xmldasm document -ds documentSchema... [ -es envelopeSchema... ] [ -s ] [ -c ] [ -p ] [ -sd ] [ -se ] [ -m filenamemask ] [ -en encoding ] [ -v ]  

where:  
  document           XML document  
  documentSchema     XML document schema(s)  
  envelopeSchema     XML envelope schema(s)  
  -s                 Validate document structure  
  -c                 Display disassembled XML message on the console  
  -p                 Display promoted properties on the console  
  -sd                Set document schema(s) as design-time property  
  -se                Set envelope schema(s) as design-time property  
  -m                 Output file name mask (default is %MessageID%)  
  encoding           Input message body part encoding name (e.g., windows-1252) or code page (e.g., 936)  
  -v                 Verbous mode  

file name macros:  
  %MessageID%        XML message identifier (Guid)  
  %MessagePartID%    XML message part identifier (Guid)  
  %MessageNumber%    XML message number  

```  

 <span data-ttu-id="8e6f8-166">たとえば、2 つのネストされたエンベロープを持つ XML ドキュメントを逆アセンブルし、結果をコンソールに表示するには、次のコマンドを使用します。</span><span class="sxs-lookup"><span data-stu-id="8e6f8-166">For example, if you want to disassemble an XML document with two nested envelopes and display the results to the console, use the following command:</span></span>  

```  
XmlDasm.exe file_in.txt –ds myDocumentSchema.xsd –es myEnvelopeSchema1.xsd –es myEnvelopeSchema2.xsd –c  
```  

## <a name="see-also"></a><span data-ttu-id="8e6f8-167">参照</span><span class="sxs-lookup"><span data-stu-id="8e6f8-167">See Also</span></span>  
 [<span data-ttu-id="8e6f8-168">SDK のユーティリティ</span><span class="sxs-lookup"><span data-stu-id="8e6f8-168">Utilities in the SDK</span></span>](../core/utilities-in-the-sdk.md)