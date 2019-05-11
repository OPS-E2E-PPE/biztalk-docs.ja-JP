---
title: 任意の XPath プロパティ ハンドラ (BizTalk Server サンプル) |Microsoft Docs
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
ms.assetid: 4eb26c38-5ece-42b0-a28e-73214df1dc41
caps.latest.revision: 14
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: 41b66ae9dd0149e8172726ff882de11dcf35ba25
ms.sourcegitcommit: d27732e569b0897361dfaebca8352aa97bb7efe1
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 05/10/2019
ms.locfileid: "65528587"
---
# <a name="arbitrary-xpath-property-handler-biztalk-server-sample"></a><span data-ttu-id="568ab-102">任意の XPath プロパティ ハンドラ (BizTalk Server サンプル)</span><span class="sxs-lookup"><span data-stu-id="568ab-102">Arbitrary XPath Property Handler (BizTalk Server Sample)</span></span>
<span data-ttu-id="568ab-103">任意の XPath プロパティ ハンドラ ([!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)]サンプル) に送信される XML ドキュメントの特定のプロパティを昇格させるためのカスタム パイプライン コンポーネントを記述する方法を示します[!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)]します。</span><span class="sxs-lookup"><span data-stu-id="568ab-103">The Arbitrary XPath Property Handler ([!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)] Sample) demonstrates how to write a custom pipeline component to promote specific properties on an XML document that is submitted to [!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)].</span></span> <span data-ttu-id="568ab-104">サンプルに含まれる機能を使用して、XPath 式を評価するカスタムの正規表現、アセンブラー、および逆アセンブラー コンポーネントを作成することができます。</span><span class="sxs-lookup"><span data-stu-id="568ab-104">You can use functionality contained in the sample to create custom regular, assembler, and disassembler components to evaluate XPath expressions.</span></span>  
  
## <a name="what-this-sample-does"></a><span data-ttu-id="568ab-105">このサンプルの処理</span><span class="sxs-lookup"><span data-stu-id="568ab-105">What This Sample Does</span></span>  
 <span data-ttu-id="568ab-106">サンプルには、プロセス、DocInstance.xml を発注書 (PO) XML ドキュメントが含まれています。</span><span class="sxs-lookup"><span data-stu-id="568ab-106">The sample includes a purchase order (PO) XML document to process, DocInstance.xml.</span></span> <span data-ttu-id="568ab-107">サンプルでは、DocInstance.xml を処理する次の手順を使用します。</span><span class="sxs-lookup"><span data-stu-id="568ab-107">The sample uses the following steps to process DocInstance.xml:</span></span>  
  
1. <span data-ttu-id="568ab-108">DocInstance.xml はによって取得、[!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)]受信ポートと、任意の XPath プロパティ ハンドラというカスタム パイプライン コンポーネントによって処理されます。</span><span class="sxs-lookup"><span data-stu-id="568ab-108">DocInstance.xml is retrieved by a [!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)] receive port and processed by a custom pipeline component called Arbitrary XPath Property Handler.</span></span>  
  
2. <span data-ttu-id="568ab-109">任意の XPath プロパティ ハンドラ コンポーネントはすべてを昇格\<価格\>と\<数量\>として任意の XPath 式を持つ要素は、PO スキーマで定義されています。</span><span class="sxs-lookup"><span data-stu-id="568ab-109">The arbitrary XPath property handler component promotes all \<Price\> and \<Quantity\> elements with an arbitrary XPath expression as defined in the PO schema.</span></span> <span data-ttu-id="568ab-110">XPath 式には、PO ドキュメントのルート要素のあいまいな子要素で使用される位置コンストラクタも含まれています。</span><span class="sxs-lookup"><span data-stu-id="568ab-110">The XPath expression also contains the position construct for use with ambiguous child elements of the PO document root element.</span></span>  
  
3. <span data-ttu-id="568ab-111">任意の XPath プロパティ ハンドラ コンポーネントは、メッセージの種類を決定し、メッセージ コンテキストに昇格させます。</span><span class="sxs-lookup"><span data-stu-id="568ab-111">The arbitrary XPath property handler component determines the message type and promotes it into the message context.</span></span>  
  
4. <span data-ttu-id="568ab-112">次に、コンポーネントは、オーケストレーションをさらに処理するために、昇格する要素を持つ XML ドキュメントを送信します。</span><span class="sxs-lookup"><span data-stu-id="568ab-112">The component then sends the XML document with the promoted elements to an orchestration for further processing.</span></span>  
  
5. <span data-ttu-id="568ab-113">オーケストレーションは、PO ドキュメントで昇格させた要素にアクセスし、PO 内の項目の合計数を計算します。</span><span class="sxs-lookup"><span data-stu-id="568ab-113">The orchestration accesses the promoted elements in the PO document and calculates the total number of items in the PO.</span></span>  
  
6. <span data-ttu-id="568ab-114">オーケストレーションは、元の PO と更新された合計から情報を含む新しい PO ドキュメントを作成します。</span><span class="sxs-lookup"><span data-stu-id="568ab-114">The orchestration creates a new PO document that contains the information from the original PO as well as the updated total.</span></span>  
  
7. <span data-ttu-id="568ab-115">新しい PO ドキュメントは、\Output ディレクトリのファイルに書き込まれます。</span><span class="sxs-lookup"><span data-stu-id="568ab-115">The new PO document is written to a file in the \Output directory.</span></span>  
  
## <a name="where-to-find-this-sample"></a><span data-ttu-id="568ab-116">このサンプルの場所</span><span class="sxs-lookup"><span data-stu-id="568ab-116">Where to Find This Sample</span></span>  
 <span data-ttu-id="568ab-117">*\<パスのサンプル\>* \Pipelines\ArbitraryXPathPropertyHandler</span><span class="sxs-lookup"><span data-stu-id="568ab-117">*\<Samples Path\>* \Pipelines\ArbitraryXPathPropertyHandler</span></span>  
  
 <span data-ttu-id="568ab-118">次の表は、このサンプルのファイルとその目的を示しています。</span><span class="sxs-lookup"><span data-stu-id="568ab-118">The following table shows the files in this sample and describes their purpose.</span></span>  
  
|<span data-ttu-id="568ab-119">ファイル</span><span class="sxs-lookup"><span data-stu-id="568ab-119">File(s)</span></span>|<span data-ttu-id="568ab-120">説明</span><span class="sxs-lookup"><span data-stu-id="568ab-120">Description</span></span>|  
|---------------|-----------------|  
|<span data-ttu-id="568ab-121">ArbitraryXPathPropertyHandler.sln</span><span class="sxs-lookup"><span data-stu-id="568ab-121">ArbitraryXPathPropertyHandler.sln</span></span>|<span data-ttu-id="568ab-122">カスタム パイプライン コンポーネント ソリューション ファイルです。</span><span class="sxs-lookup"><span data-stu-id="568ab-122">Custom pipeline component solution file.</span></span>|  
|<span data-ttu-id="568ab-123">ArbitraryXPathPropertyHandler.resX</span><span class="sxs-lookup"><span data-stu-id="568ab-123">ArbitraryXPathPropertyHandler.resX</span></span>|<span data-ttu-id="568ab-124">リソース ファイル。</span><span class="sxs-lookup"><span data-stu-id="568ab-124">Resource file.</span></span>|  
|<span data-ttu-id="568ab-125">ArbitraryXPathPropertyHandlerComp.cs</span><span class="sxs-lookup"><span data-stu-id="568ab-125">ArbitraryXPathPropertyHandlerComp.cs</span></span>|<span data-ttu-id="568ab-126">主要なコンポーネントの実装。</span><span class="sxs-lookup"><span data-stu-id="568ab-126">Main component implementation.</span></span>|  
|<span data-ttu-id="568ab-127">AssemblyInfo.cs</span><span class="sxs-lookup"><span data-stu-id="568ab-127">AssemblyInfo.cs</span></span>|<span data-ttu-id="568ab-128">アセンブリ情報です。</span><span class="sxs-lookup"><span data-stu-id="568ab-128">Assembly information.</span></span>|  
|<span data-ttu-id="568ab-129">Cleanup.bat</span><span class="sxs-lookup"><span data-stu-id="568ab-129">Cleanup.bat</span></span>|<span data-ttu-id="568ab-130">サンプルのクリーンアップ ファイル。</span><span class="sxs-lookup"><span data-stu-id="568ab-130">Sample cleanup file.</span></span>|  
|<span data-ttu-id="568ab-131">PromotingMap.cs</span><span class="sxs-lookup"><span data-stu-id="568ab-131">PromotingMap.cs</span></span>|<span data-ttu-id="568ab-132">ネイティブの CLR 型としてプロパティの昇格では、実装をマップします。</span><span class="sxs-lookup"><span data-stu-id="568ab-132">Property promotion as native CLR types map implementation.</span></span>|  
|<span data-ttu-id="568ab-133">PropertyAttributes.cs</span><span class="sxs-lookup"><span data-stu-id="568ab-133">PropertyAttributes.cs</span></span>|<span data-ttu-id="568ab-134">カスタム属性、プロパティ記述子、および ICustomTypePropertyDescriptor 実装です。</span><span class="sxs-lookup"><span data-stu-id="568ab-134">Custom attributes, property descriptor, and ICustomTypePropertyDescriptor implementation.</span></span>|  
|<span data-ttu-id="568ab-135">SchemaMap.cs</span><span class="sxs-lookup"><span data-stu-id="568ab-135">SchemaMap.cs</span></span>|<span data-ttu-id="568ab-136">スキーマのマッピングは、メッセージの種類から IDocumentSpec スキーマのあいまいさを解決します。</span><span class="sxs-lookup"><span data-stu-id="568ab-136">Schema mapping from message type to IDocumentSpec to resolve schema ambiguity.</span></span>|  
|<span data-ttu-id="568ab-137">Setup.bat</span><span class="sxs-lookup"><span data-stu-id="568ab-137">Setup.bat</span></span>|<span data-ttu-id="568ab-138">ビルドおよび設定のサンプル パイプライン コンポーネント。</span><span class="sxs-lookup"><span data-stu-id="568ab-138">Build and setup sample pipeline component.</span></span>|  
|<span data-ttu-id="568ab-139">VirtualStream.cs</span><span class="sxs-lookup"><span data-stu-id="568ab-139">VirtualStream.cs</span></span>|<span data-ttu-id="568ab-140">仮想ストリームの実装。</span><span class="sxs-lookup"><span data-stu-id="568ab-140">Virtual stream implementation.</span></span>|  
|<span data-ttu-id="568ab-141">SeekableReadOnlyStream.cs</span><span class="sxs-lookup"><span data-stu-id="568ab-141">SeekableReadOnlyStream.cs</span></span>|<span data-ttu-id="568ab-142">シーク可能な読み取り専用ストリームの実装。</span><span class="sxs-lookup"><span data-stu-id="568ab-142">Seekable read-only stream implementation.</span></span>|  
|<span data-ttu-id="568ab-143">ArbitraryXPathSample.sln</span><span class="sxs-lookup"><span data-stu-id="568ab-143">ArbitraryXPathSample.sln</span></span>|<span data-ttu-id="568ab-144">サンプル オーケストレーション ソリューション ファイルです。</span><span class="sxs-lookup"><span data-stu-id="568ab-144">Sample orchestration solution file.</span></span>|  
|<span data-ttu-id="568ab-145">CalculateTotalAmount.odx</span><span class="sxs-lookup"><span data-stu-id="568ab-145">CalculateTotalAmount.odx</span></span>|<span data-ttu-id="568ab-146">サンプル オーケストレーションです。</span><span class="sxs-lookup"><span data-stu-id="568ab-146">Sample orchestration.</span></span>|  
|<span data-ttu-id="568ab-147">PODocument.xsd</span><span class="sxs-lookup"><span data-stu-id="568ab-147">PODocument.xsd</span></span>|<span data-ttu-id="568ab-148">注文書スキーマ。</span><span class="sxs-lookup"><span data-stu-id="568ab-148">Purchase order schema.</span></span>|  
|<span data-ttu-id="568ab-149">DocInstance.xml</span><span class="sxs-lookup"><span data-stu-id="568ab-149">DocInstance.xml</span></span>|<span data-ttu-id="568ab-150">サンプルの注文書インスタンス。</span><span class="sxs-lookup"><span data-stu-id="568ab-150">Sample purchase order instance.</span></span>|  
  
## <a name="building-and-initializing-this-sample"></a><span data-ttu-id="568ab-151">このサンプルのビルドと初期化</span><span class="sxs-lookup"><span data-stu-id="568ab-151">Building and Initializing This Sample</span></span>  
 <span data-ttu-id="568ab-152">このサンプルがで実行するように設計、[!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)]環境[!INCLUDE[btsSQLServerNoVersion](../includes/btssqlservernoversion-md.md)]同じマシンで実行されています。</span><span class="sxs-lookup"><span data-stu-id="568ab-152">This sample is designed to run in a [!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)] environment with [!INCLUDE[btsSQLServerNoVersion](../includes/btssqlservernoversion-md.md)] running on the same machine.</span></span> <span data-ttu-id="568ab-153">環境内でこの構成が一致しない場合は、任意の XPath プロパティ ハンドラーを変更する必要があります ([!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)]サンプル) を適切な SQL Server コンピューター をポイントします。</span><span class="sxs-lookup"><span data-stu-id="568ab-153">If your environment does not match this configuration, you must modify the Arbitrary XPath Property Handler ([!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)] Sample) to point to the correct SQL Server computer.</span></span>  
  
> [!IMPORTANT]
>  <span data-ttu-id="568ab-154">Setup.bat では、Microsoft Windows のインストール ディレクトリが C:\Windows 前提としています。</span><span class="sxs-lookup"><span data-stu-id="568ab-154">Setup.bat assumes your Microsoft Windows installation directory is C:\Windows.</span></span> <span data-ttu-id="568ab-155">Windows のインストールが別のディレクトリにある場合は、グローバル アセンブリ キャッシュの Microsoft.BizTalk.Component.Utilities アセンブリの場所を反映するように、ArbitraryXPathPropertyHandler.csproj ファイルを変更する必要があります。</span><span class="sxs-lookup"><span data-stu-id="568ab-155">If your Windows installation is in another directory, you must modify the ArbitraryXPathPropertyHandler.csproj file to reflect the location of the Microsoft.BizTalk.Component.Utilities assembly in the global assembly cache.</span></span> <span data-ttu-id="568ab-156">参照要素では、次のように変更します。 \<SYSTEMROOT\> Windows がインストールされている場所に (たとえば、C:\WINNT\\)。</span><span class="sxs-lookup"><span data-stu-id="568ab-156">In the Reference element, change \<SYSTEMROOT\> to the location where Windows is installed (for example, C:\WINNT\\).</span></span>  
  
```  
<Reference  
  Name = "Microsoft.BizTalk.Component.Utilities"  
  AssemblyName = "Microsoft.BizTalk.Component.Utilities"  
  HintPath = "<SYSTEMROOT>\assembly\GAC\Microsoft.BizTalk.Component.Utilities\3.0.1.0__31bf3856ad364e35\Microsoft.BizTalk.Component.Utilities.dll"  
/>  
```  
  
 <span data-ttu-id="568ab-157">次の手順を使用してビルドして、任意の XPath プロパティ ハンドラーを初期化 ([!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)]サンプル)。</span><span class="sxs-lookup"><span data-stu-id="568ab-157">Use the following procedure to build and initialize the Arbitrary XPath Property Handler ([!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)] Sample).</span></span>  
  
#### <a name="to-build-and-initialize-this-sample"></a><span data-ttu-id="568ab-158">このサンプルを作成および初期化するには</span><span class="sxs-lookup"><span data-stu-id="568ab-158">To build and initialize this sample</span></span>  
  
1. <span data-ttu-id="568ab-159">コマンド ウィンドウでディレクトリ変更 (**cd**) 次のフォルダーに。</span><span class="sxs-lookup"><span data-stu-id="568ab-159">In a command window, change directories (**cd**) to the following folder:</span></span>  
  
    <span data-ttu-id="568ab-160">*\<パスのサンプル\>* \Pipelines\ArbitraryXPathPropertyHandler</span><span class="sxs-lookup"><span data-stu-id="568ab-160">*\<Samples Path\>* \Pipelines\ArbitraryXPathPropertyHandler</span></span>  
  
2. <span data-ttu-id="568ab-161">ファイルは、次の操作を実行します。 Setup.bat を実行します。</span><span class="sxs-lookup"><span data-stu-id="568ab-161">Run the file Setup.bat, which performs the following actions:</span></span>  
  
   - <span data-ttu-id="568ab-162">任意の XPath プロパティ ハンドラ パイプライン コンポーネントをビルドします。</span><span class="sxs-lookup"><span data-stu-id="568ab-162">Builds the Arbitrary XPath Property Handler pipeline component.</span></span>  
  
   - <span data-ttu-id="568ab-163">構築されたコピーのパイプライン コンポーネントを*\<インストール パス\>* \Pipeline Components ディレクトリ。</span><span class="sxs-lookup"><span data-stu-id="568ab-163">Copies built pipeline component to the *\<Installation Path\>* \Pipeline Components directory.</span></span>  
  
   - <span data-ttu-id="568ab-164">ポートと受信ポート、送信を作成します。</span><span class="sxs-lookup"><span data-stu-id="568ab-164">Creates the send and receive ports.</span></span>  
  
   - <span data-ttu-id="568ab-165">このサンプルで使用される入力と出力ディレクトリを作成します。</span><span class="sxs-lookup"><span data-stu-id="568ab-165">Creates the input and output directories used in the sample.</span></span>  
  
   - <span data-ttu-id="568ab-166">サンプル[!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)]オーケストレーション arbitraryxpathsample をインストールします。</span><span class="sxs-lookup"><span data-stu-id="568ab-166">Installs the sample [!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)] orchestration ArbitraryXPathSample.</span></span>  
  
   - <span data-ttu-id="568ab-167">サンプル オーケストレーションにポートをバインドします。</span><span class="sxs-lookup"><span data-stu-id="568ab-167">Binds the ports to the sample orchestration.</span></span>  
  
   - <span data-ttu-id="568ab-168">オーケストレーションを開始します。</span><span class="sxs-lookup"><span data-stu-id="568ab-168">Starts the orchestration.</span></span>  
  
   > [!NOTE]
   >  <span data-ttu-id="568ab-169">ビルドおよび初期化中にエラーを報告しない必要があります。</span><span class="sxs-lookup"><span data-stu-id="568ab-169">No errors should be reported during the build and initialization.</span></span> <span data-ttu-id="568ab-170">エラーが発生した場合は、インストールされているすべての必要なソフトウェアがあることと、Microsoft ビルド ツールは、パスで使用できることを確認します。</span><span class="sxs-lookup"><span data-stu-id="568ab-170">If any errors occur, make sure that you have all necessary software installed and that Microsoft build tools are available on the path.</span></span>  
   > 
   > [!NOTE]
   >  <span data-ttu-id="568ab-171">Setup.bat による変更を元に戻したりするにはまず停止してから、ホスト インスタンスを再起動、[!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)]管理コンソール。</span><span class="sxs-lookup"><span data-stu-id="568ab-171">To undo changes made by Setup.bat, you must first stop and restart the host instance from the [!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)] Administration console.</span></span> <span data-ttu-id="568ab-172">次に、Cleanup.bat を実行します。</span><span class="sxs-lookup"><span data-stu-id="568ab-172">Next, run Cleanup.bat.</span></span> <span data-ttu-id="568ab-173">Setup.bat を 2 回目に実行する場合は、その前に Cleanup.bat を実行してください。</span><span class="sxs-lookup"><span data-stu-id="568ab-173">You must run Cleanup.bat before running Setup.bat a second time.</span></span>  
  
## <a name="running-this-sample"></a><span data-ttu-id="568ab-174">このサンプルの実行</span><span class="sxs-lookup"><span data-stu-id="568ab-174">Running This Sample</span></span>  
 <span data-ttu-id="568ab-175">次の手順を使用して、任意の XPath プロパティ ハンドラを実行する ([!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)]サンプル)。</span><span class="sxs-lookup"><span data-stu-id="568ab-175">Use the following procedure to run the Arbitrary XPath Property Handler ([!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)] Sample).</span></span>  
  
#### <a name="to-run-this-sample"></a><span data-ttu-id="568ab-176">このサンプルを実行するには</span><span class="sxs-lookup"><span data-stu-id="568ab-176">To run this sample</span></span>  
  
1.  <span data-ttu-id="568ab-177">注文書 (po) ファイル DocInstance.xml を \Input ディレクトリにコピーします。</span><span class="sxs-lookup"><span data-stu-id="568ab-177">Copy the purchase order (PO) file DocInstance.xml to the \Input directory.</span></span> <span data-ttu-id="568ab-178">PO ファイルは、任意の XPath プロパティ ハンドラ パイプライン コンポーネントに XML データを送信する受信ポートによって取得されます。</span><span class="sxs-lookup"><span data-stu-id="568ab-178">The PO file is picked up by a receive port, which sends the XML data to the Arbitrary XPath Property Handler pipeline component.</span></span>  
  
2.  <span data-ttu-id="568ab-179">\Output ディレクトリの内容を表示します。</span><span class="sxs-lookup"><span data-stu-id="568ab-179">View the contents in the \Output directory.</span></span> <span data-ttu-id="568ab-180">新しいファイルが作成 \Input ディレクトリにコピーした DocInstance.xml ファイルからのすべての情報を格納することに注意してください。</span><span class="sxs-lookup"><span data-stu-id="568ab-180">Notice that a new file is created that contains all the information from the DocInstance.xml file that you copied to the \Input directory.</span></span> <span data-ttu-id="568ab-181">ファイルの違いは今すぐ、 \<TotalAmount\>要素に PO の合計量に設定されています。</span><span class="sxs-lookup"><span data-stu-id="568ab-181">The difference in the file is that now the \<TotalAmount\> element has been populated with the total amount for the PO.</span></span>  
  
## <a name="comments"></a><span data-ttu-id="568ab-182">コメント</span><span class="sxs-lookup"><span data-stu-id="568ab-182">Comments</span></span>  
 <span data-ttu-id="568ab-183">正規 XPath 式の単純な式として"/\* [ローカル名 () =' 要素名 ' と namespaceURI() ='http://MyUri.org']/\*[ローカル名 () =' 要素名 ']/@\*[ローカル名 =' 属性名 ']"。</span><span class="sxs-lookup"><span data-stu-id="568ab-183">Canonical XPath expressions are simple expressions such as "/\*[local-name()='element-name' and namespaceURI()='http://MyUri.org']/\*[local-name()='element-name']/@\*[local-name='attribute-name']".</span></span>  
  
 <span data-ttu-id="568ab-184">任意の XPath 式はくらい複雑であることができます"//element-name//\* [ローカル名 () 'の要素名' と位置 () = = 2]"。</span><span class="sxs-lookup"><span data-stu-id="568ab-184">An arbitrary XPath expression can be as complex as "//element-name//\*[local-name()='element-name' and position()=2]".</span></span> <span data-ttu-id="568ab-185">実際、受け取りますで非正規 XPath 式がサポートされていないことを示す実行時エラー [!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)] XPath ボディまたは XPath プロパティで使用される非正規 XPath がスキーマにある場合。</span><span class="sxs-lookup"><span data-stu-id="568ab-185">If fact, you will receive a run-time error stating that non-canonical XPath expressions are not supported by [!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)] if your schema has a non-canonical XPath used in the XPath body or an XPath property.</span></span> <span data-ttu-id="568ab-186">任意の XPath 式をサポートするために、ソリューションでは、任意の XPath ボディと任意の XPath プロパティ式をサポートするカスタム逆アセンブラーおよびアセンブラー コンポーネントを作成します。</span><span class="sxs-lookup"><span data-stu-id="568ab-186">A solution to support arbitrary XPath expressions is to create custom disassembler and assembler components that support an arbitrary XPath body as well as arbitrary XPath property expressions.</span></span>  
  
 <span data-ttu-id="568ab-187">このサンプルは、カスタム パイプライン コンポーネントで、次の一連の手順を使用してとき**IComponent.Execute**実装されます。</span><span class="sxs-lookup"><span data-stu-id="568ab-187">This sample uses the following sequence of steps in the custom pipeline component when **IComponent.Execute** is implemented:</span></span>  
  
1.  <span data-ttu-id="568ab-188">入力メッセージのボディ パーツ ストリームに対して仮想のシーク可能ストリームを作成します。</span><span class="sxs-lookup"><span data-stu-id="568ab-188">Creates a virtual seekable stream over the input message body part stream.</span></span> <span data-ttu-id="568ab-189">(入力メッセージが大きくなることができます、ストリームをシーク可能ではないことができるためにする必要があります最小メモリ フット プリントがあるおよびストリームの位置を変更できる。)</span><span class="sxs-lookup"><span data-stu-id="568ab-189">(Because the input message can be large and the stream can be non-seekable, it should have a small memory footprint and be able to change stream positions.)</span></span>  
  
2.  <span data-ttu-id="568ab-190">そのため、新しい送信メッセージと新しいボディ部を作成、仮想ストリームを新しいボディ部に割り当てます、ボディ部のプロパティのクローンを作成およびメッセージ コンテキストのクローンを作成します。</span><span class="sxs-lookup"><span data-stu-id="568ab-190">Creates a new outgoing message and a new body part for it, assigns a virtual stream to the new body part, clones body part properties, and clones message context.</span></span>  
  
3.  <span data-ttu-id="568ab-191">デザイン時に指定されたスキーマに基づいて、入力メッセージのスキーマを取得します。</span><span class="sxs-lookup"><span data-stu-id="568ab-191">Gets a schema for the input message or based on schemas specified during design time.</span></span>  
  
4.  <span data-ttu-id="568ab-192">インスタンスに、ストリームを読み込みます**System.Xml.XmlDocument**します。</span><span class="sxs-lookup"><span data-stu-id="568ab-192">Loads the stream into an instance of **System.Xml.XmlDocument**.</span></span>  
  
5.  <span data-ttu-id="568ab-193">昇格させたプロパティと識別フィールドについて説明しますと昇格または送信メッセージのメッセージ コンテキストに書き込みます。</span><span class="sxs-lookup"><span data-stu-id="568ab-193">Walks through promoted properties and distinguished fields and promotes or writes them to the message context of the outgoing message.</span></span>  
  
6.  <span data-ttu-id="568ab-194">送信メッセージを返します。</span><span class="sxs-lookup"><span data-stu-id="568ab-194">Returns the outgoing message.</span></span>  
  
7.  <span data-ttu-id="568ab-195">送信メッセージをファイルに書き込みます。</span><span class="sxs-lookup"><span data-stu-id="568ab-195">Writes the outgoing message to a file.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="568ab-196">参照</span><span class="sxs-lookup"><span data-stu-id="568ab-196">See Also</span></span>  
 [<span data-ttu-id="568ab-197">パイプライン (BizTalk Server Samples フォルダー)</span><span class="sxs-lookup"><span data-stu-id="568ab-197">Pipelines (BizTalk Server Samples Folder)</span></span>](../core/pipelines-biztalk-server-samples-folder.md)