---
title: HTTPSolicitResponse |Microsoft ドキュメント
ms.custom: ''
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: ''
ms.suite: ''
ms.tgt_pltfrm: ''
ms.topic: article
helpviewer_keywords:
- HTTP adapters, examples
- examples, HTTP adapters
ms.assetid: b149544e-3279-4ac9-b31f-fff3e41ec8e7
caps.latest.revision: 27
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: 500ec05df9a3a365a350571e8b3e66f5d584f92d
ms.sourcegitcommit: 5abd0ed3f9e4858ffaaec5481bfa8878595e95f7
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 11/28/2017
ms.locfileid: "25973128"
---
# <a name="httpsolicitresponse"></a><span data-ttu-id="3ed3d-102">HTTPSolicitResponse</span><span class="sxs-lookup"><span data-stu-id="3ed3d-102">HTTPSolicitResponse</span></span>
<span data-ttu-id="3ed3d-103">HTTPSolicitResponse サンプルは、オーケストレーション データの処理に ASP.NET アプリケーションを利用する Microsoft [!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)] オーケストレーションを作成する方法を示します。</span><span class="sxs-lookup"><span data-stu-id="3ed3d-103">The HTTPSolicitResponse sample demonstrates how to create a Microsoft [!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)] orchestration that leverages an ASP.NET application to help process orchestration data.</span></span> <span data-ttu-id="3ed3d-104">このサンプルでは、オーケストレーションは要求 - 応答のポートを利用して、ASP.NET アプリケーションにメッセージを送信し、応答を受信します。</span><span class="sxs-lookup"><span data-stu-id="3ed3d-104">In this sample, the orchestration makes use of a request/response port to send a message to the ASP.NET application and to retrieve the response.</span></span> <span data-ttu-id="3ed3d-105">HTTP アダプターを使用することにより、BizTalk Server オーケストレーションと ASP.NET アプリケーションを統合できます。</span><span class="sxs-lookup"><span data-stu-id="3ed3d-105">You achieve the integration between the BizTalk Server orchestration and the ASP.NET application by using the HTTP adapter.</span></span> <span data-ttu-id="3ed3d-106">詳細については、次を参照してください。 [HTTP アダプター](../core/http-adapter.md)です。</span><span class="sxs-lookup"><span data-stu-id="3ed3d-106">For more information, see [HTTP Adapter](../core/http-adapter.md).</span></span>  
  
## <a name="what-this-sample-does"></a><span data-ttu-id="3ed3d-107">このサンプルの処理</span><span class="sxs-lookup"><span data-stu-id="3ed3d-107">What This Sample Does</span></span>  
 <span data-ttu-id="3ed3d-108">このサンプルは、以下の手順で、乗算する 2 つの数値を含んでいる要求を受信し、その要求に応答する BizTalk Server オーケストレーションを提供します。</span><span class="sxs-lookup"><span data-stu-id="3ed3d-108">This sample consists of a BizTalk Server orchestration that receives a request containing two numbers to be multiplied, and satisfies that request using the following sequence of steps:</span></span>  
  
1.  <span data-ttu-id="3ed3d-109">BizTalk Server オーケストレーションが、特定のフォルダーから .xml 入力ファイルを取得します。</span><span class="sxs-lookup"><span data-stu-id="3ed3d-109">The BizTalk Server orchestration retrieves an .xml input file from a specific folder.</span></span>  
  
2.  <span data-ttu-id="3ed3d-110">次に、BizTalk Server オーケストレーションは、HTTP 要求を使用して、.xml 入力ファイルからマルチプライア ASP.NET アプリケーションに XML を転送します。</span><span class="sxs-lookup"><span data-stu-id="3ed3d-110">The orchestration uses an HTTP request to forward the XML from the file to a multiplier ASP.NET application.</span></span>  
  
3.  <span data-ttu-id="3ed3d-111">マルチプライア ASP.NET アプリケーションが、乗算を実行し、HTTP 応答で結果を XML として返すことにより、HTTP 要求に応答します。</span><span class="sxs-lookup"><span data-stu-id="3ed3d-111">The multiplier ASP.NET application responds to the HTTP request by performing the multiplication and returning the result as XML in the HTTP response.</span></span>  
  
4.  <span data-ttu-id="3ed3d-112">BizTalk Server オーケストレーションが、HTTP 応答で結果を XML として受信し、特定のフォルダーの .xml ファイルに結果を書き込みます。</span><span class="sxs-lookup"><span data-stu-id="3ed3d-112">The orchestration receives the result as XML in an HTTP response, and writes that result to an .xml file in a specific folder.</span></span>  
  
## <a name="where-to-find-this-sample"></a><span data-ttu-id="3ed3d-113">このサンプルの場所</span><span class="sxs-lookup"><span data-stu-id="3ed3d-113">Where to Find This Sample</span></span>  
 <span data-ttu-id="3ed3d-114">\<*パスのサンプル*\>\AdaptersUsage\HTTPSolicitResponse</span><span class="sxs-lookup"><span data-stu-id="3ed3d-114">\<*Samples Path*\>\AdaptersUsage\HTTPSolicitResponse</span></span>  
  
 <span data-ttu-id="3ed3d-115">次の表は、このサンプルのファイルとその目的を示しています。</span><span class="sxs-lookup"><span data-stu-id="3ed3d-115">The following table shows the files in this sample and describes their purpose.</span></span>  
  
|<span data-ttu-id="3ed3d-116">ファイル</span><span class="sxs-lookup"><span data-stu-id="3ed3d-116">File(s)</span></span>|<span data-ttu-id="3ed3d-117">Description</span><span class="sxs-lookup"><span data-stu-id="3ed3d-117">Description</span></span>|  
|---------------|-----------------|  
|<span data-ttu-id="3ed3d-118">Cleanup.bat</span><span class="sxs-lookup"><span data-stu-id="3ed3d-118">Cleanup.bat</span></span>|<span data-ttu-id="3ed3d-119">必要に応じて、アセンブリの展開の解除とグローバル アセンブリ キャッシュ (GAC) からのアセンブリの削除、送信および受信ポートの削除、Microsoft インターネット インフォメーション サービス (IIS) の仮想ディレクトリの削除などを行います。</span><span class="sxs-lookup"><span data-stu-id="3ed3d-119">Undeploys assemblies and removes them from the global assembly cache (GAC); removes send and receive ports; removes Microsoft Internet Information Services (IIS) virtual directories as needed.</span></span>|  
|<span data-ttu-id="3ed3d-120">HttpSolicitResponse.btproj、HttpSolicitResponse.sln</span><span class="sxs-lookup"><span data-stu-id="3ed3d-120">HttpSolicitResponse.btproj, HttpSolicitResponse.sln</span></span>|<span data-ttu-id="3ed3d-121">マルチプライア ASP.NET アプリケーションや関連スキーマなどを使用するオーケストレーションを含む BizTalk プロジェクトのプロジェクト ファイルとソース ファイルを提供します。</span><span class="sxs-lookup"><span data-stu-id="3ed3d-121">Provides project and source files for the BizTalk project that contains the orchestration that uses the multiplier ASP.NET application, the associated schemas, and so on.</span></span>|  
|<span data-ttu-id="3ed3d-122">HttpSolicitResponseBinding.xml</span><span class="sxs-lookup"><span data-stu-id="3ed3d-122">HttpSolicitResponseBinding.xml</span></span>|<span data-ttu-id="3ed3d-123">ポートのバインドなどの自動化されたセットアップを可能にします。</span><span class="sxs-lookup"><span data-stu-id="3ed3d-123">Provides for automated setup such as port binding.</span></span>|  
|<span data-ttu-id="3ed3d-124">MultiplyRequest.xsd、MultiplyResponse.xsd</span><span class="sxs-lookup"><span data-stu-id="3ed3d-124">MultiplyRequest.xsd, MultiplyResponse.xsd</span></span>|<span data-ttu-id="3ed3d-125">MultiplyRequest.xsd は乗算要求、MultiplyResponse.xsd は乗算応答の XML メッセージのスキーマを提供します。</span><span class="sxs-lookup"><span data-stu-id="3ed3d-125">Provides schemas for the multiplication request and response XML messages, respectively.</span></span>|  
|<span data-ttu-id="3ed3d-126">MultiplyTwoIntegers.odx</span><span class="sxs-lookup"><span data-stu-id="3ed3d-126">MultiplyTwoIntegers.odx</span></span>|<span data-ttu-id="3ed3d-127">乗算演算を要求する .xml ファイルを受信し、その要求をマルチプライア ASP.NET アプリケーションに転送してから、その応答を .xml ファイルに書き込む BizTalk Server オーケストレーションを提供します。</span><span class="sxs-lookup"><span data-stu-id="3ed3d-127">Provides a BizTalk Server orchestration that receives an .xml file requesting a multiplication operation, forwards the request to the multiplier ASP.NET application, and writes its response to a file.</span></span>|  
|<span data-ttu-id="3ed3d-128">request_in.xml</span><span class="sxs-lookup"><span data-stu-id="3ed3d-128">request_in.xml</span></span>|<span data-ttu-id="3ed3d-129">サンプル入力ファイルです。</span><span class="sxs-lookup"><span data-stu-id="3ed3d-129">Sample input file.</span></span>|  
|<span data-ttu-id="3ed3d-130">Setup.bat</span><span class="sxs-lookup"><span data-stu-id="3ed3d-130">Setup.bat</span></span>|<span data-ttu-id="3ed3d-131">このサンプルを作成および初期化します。</span><span class="sxs-lookup"><span data-stu-id="3ed3d-131">Builds and initializes this sample.</span></span>|  
|<span data-ttu-id="3ed3d-132">\Multiplier フォルダー内のファイル: </span><span class="sxs-lookup"><span data-stu-id="3ed3d-132">In the \Multiplier folder:</span></span><br /><br /> <span data-ttu-id="3ed3d-133">Multiplier.aspx, Multiplier.aspx.cs, Multiplier.sln</span><span class="sxs-lookup"><span data-stu-id="3ed3d-133">Multiplier.aspx, Multiplier.aspx.cs, Multiplier.sln</span></span>|<span data-ttu-id="3ed3d-134">マルチプライア サービスを実装する ASP.NET アプリケーションを構成するファイル (プロジェクト ファイルとソリューション ファイル、ASPX ファイル、Microsoft Visual C# .NET ソース ファイルなど) を含みます。</span><span class="sxs-lookup"><span data-stu-id="3ed3d-134">Contains files that constitute the ASP.NET application that implements the multiplier service, including project and solution files, ASPX files, Microsoft Visual C# .NET source files, and so on.</span></span>|  
  
## <a name="building-and-initializing-the-sample"></a><span data-ttu-id="3ed3d-135">サンプルのビルドおよび初期化</span><span class="sxs-lookup"><span data-stu-id="3ed3d-135">Building and Initializing the Sample</span></span>  
 <span data-ttu-id="3ed3d-136">次の手順に従って、HTTPSolicitResponse サンプルをビルドおよび初期化します。</span><span class="sxs-lookup"><span data-stu-id="3ed3d-136">Use the following procedure to build and initialize the HTTPSolicitResponse sample.</span></span>  
  
> [!NOTE]
>  <span data-ttu-id="3ed3d-137">受信場所の名前に大文字が含まれている場合、このサンプルは機能しません。</span><span class="sxs-lookup"><span data-stu-id="3ed3d-137">This sample doesn't work if the name of the receive location contains any uppercase characters.</span></span>  
  
#### <a name="to-build-and-initialize-the-sample"></a><span data-ttu-id="3ed3d-138">このサンプルをビルドおよび初期化するには</span><span class="sxs-lookup"><span data-stu-id="3ed3d-138">To build and initialize the sample</span></span>  
  
1.  <span data-ttu-id="3ed3d-139">コマンド ウィンドウで、次のフォルダーに移動します。</span><span class="sxs-lookup"><span data-stu-id="3ed3d-139">In a command window, navigate to the following folder:</span></span>  
  
     <span data-ttu-id="3ed3d-140">\<*パスのサンプル*\>\AdaptersUsage\HTTPSolicitResponse</span><span class="sxs-lookup"><span data-stu-id="3ed3d-140">\<*Samples Path*\>\AdaptersUsage\HTTPSolicitResponse</span></span>  
  
2.  <span data-ttu-id="3ed3d-141">次の操作を実行する Setup.bat ファイルを実行します。</span><span class="sxs-lookup"><span data-stu-id="3ed3d-141">Run the file Setup.bat, which performs the following actions:</span></span>  
  
    -   <span data-ttu-id="3ed3d-142">このサンプルで使用する入力フォルダーと出力フォルダーを作成します。</span><span class="sxs-lookup"><span data-stu-id="3ed3d-142">Creates the input and output folders for this sample:</span></span>  
  
         <span data-ttu-id="3ed3d-143">\<*パスのサンプル*\>\AdaptersUsage\HttpSolicitResponse\HttpSolicitResponseInput</span><span class="sxs-lookup"><span data-stu-id="3ed3d-143">\<*Samples Path*\>\AdaptersUsage\HttpSolicitResponse\HttpSolicitResponseInput</span></span>  
  
         <span data-ttu-id="3ed3d-144">\<*パスのサンプル*\>\AdaptersUsage\HttpSolicitResponse\HttpSolicitResponseOutput</span><span class="sxs-lookup"><span data-stu-id="3ed3d-144">\<*Samples Path*\>\AdaptersUsage\HttpSolicitResponse\HttpSolicitResponseOutput</span></span>  
  
    -   <span data-ttu-id="3ed3d-145">このサンプルで使用するマルチプライア ASP.NET アプリケーションをコンパイルして構成します。</span><span class="sxs-lookup"><span data-stu-id="3ed3d-145">Compiles and configures the multiplier ASP.NET application used by this sample.</span></span>  
  
        > [!NOTE]
        >  <span data-ttu-id="3ed3d-146">IIS マネージャーでアプリケーション プールを作成中に次のように設定します。、 **DefaultAppPool** .NET Framework バージョンを **.Net Framework v4.0**です。</span><span class="sxs-lookup"><span data-stu-id="3ed3d-146">While creating application pool in IIS Manager, set the **DefaultAppPool** .NET Framework version to **.Net Framework v4.0**.</span></span>  
  
    -   <span data-ttu-id="3ed3d-147">このサンプルで使用する [!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)] オーケストレーションをコンパイルし、展開します。</span><span class="sxs-lookup"><span data-stu-id="3ed3d-147">Compiles and deploys the [!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)] orchestration used in this sample.</span></span>  
  
    -   <span data-ttu-id="3ed3d-148">必要な [!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)] 受信場所およびポートを作成してバインドします。</span><span class="sxs-lookup"><span data-stu-id="3ed3d-148">Creates and binds the necessary [!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)] receive location and ports.</span></span>  
  
        > [!NOTE]
        >  <span data-ttu-id="3ed3d-149">このサンプルは、ポートを作成してバインドする際に、以下の警告を表示します。</span><span class="sxs-lookup"><span data-stu-id="3ed3d-149">This sample displays the following warnings when creating and binding the ports:</span></span>  
  
        > [!NOTE]
        >  `Warning: Receive handler not specified for receive location "HttpSolicitResponseReceiveLocation"; updating with first receive handler with matching transport type.`  
  
        > [!NOTE]
        >  `Warning: Host not specified for orchestration "Microsoft.Samples.BizTalk.HttpSolicitResponse.MultiplyTwoIntegers"; updating with first available host.`  
  
    -   <span data-ttu-id="3ed3d-150">受信場所を有効にし、送信ポートを開始します。</span><span class="sxs-lookup"><span data-stu-id="3ed3d-150">Enables the receive location, and starts the send port.</span></span>  
  
        > [!NOTE]
        >  <span data-ttu-id="3ed3d-151">このサンプルのオーケストレーションは、ASP.NET アプリケーションとの HTTP 通信に双方向ポートを使用します。</span><span class="sxs-lookup"><span data-stu-id="3ed3d-151">The orchestration in this sample uses a two-way port for the HTTP interaction with the ASP.NET application.</span></span>  
  
        > [!NOTE]
        >  <span data-ttu-id="3ed3d-152">このサンプルを実行する前に、BizTalk がビルド プロセス中および初期化プロセス中にエラーを報告していないことを確認してください。</span><span class="sxs-lookup"><span data-stu-id="3ed3d-152">You should confirm that BizTalk did not report any errors during the build and initialization process before attempting to run this sample.</span></span>  
  
        > [!NOTE]
        >  <span data-ttu-id="3ed3d-153">開き、Setup.bat ファイルを実行せずにこのサンプルのプロジェクトをビルドする場合は、まず、.NET Framework の厳密名ユーティリティ (sn.exe) を使用して厳密な名前キーのペアを作成する必要があります。</span><span class="sxs-lookup"><span data-stu-id="3ed3d-153">If you choose to open and build the projects in this sample without running the file Setup.bat, you must first create a strong name key pair using the .NET Framework Strong Name Utility (sn.exe).</span></span> <span data-ttu-id="3ed3d-154">このキー ペアは、生成されたアセンブリの署名に使用します。</span><span class="sxs-lookup"><span data-stu-id="3ed3d-154">Use this key pair to sign the resulting assemblies.</span></span>  
  
        > [!NOTE]
        >  <span data-ttu-id="3ed3d-155">Setup.bat によって行われた変更を元に戻すには、Cleanup.bat を実行します。</span><span class="sxs-lookup"><span data-stu-id="3ed3d-155">To undo changes made by Setup.bat, run Cleanup.bat.</span></span> <span data-ttu-id="3ed3d-156">Setup.bat を 2 回目に実行する場合は、その前に Cleanup.bat を実行してください。</span><span class="sxs-lookup"><span data-stu-id="3ed3d-156">You must run Cleanup.bat before running Setup.bat a second time.</span></span>  
  
## <a name="running-the-sample"></a><span data-ttu-id="3ed3d-157">サンプルを実行します。</span><span class="sxs-lookup"><span data-stu-id="3ed3d-157">Running the Sample</span></span>  
 <span data-ttu-id="3ed3d-158">次の手順に従って、HTTPSolicitResponse サンプルを実行します。</span><span class="sxs-lookup"><span data-stu-id="3ed3d-158">Use the following procedure to run the HTTPSolicitResponse sample.</span></span>  
  
#### <a name="to-run-the-sample"></a><span data-ttu-id="3ed3d-159">サンプルを実行するには</span><span class="sxs-lookup"><span data-stu-id="3ed3d-159">To run the sample</span></span>  
  
1.  <span data-ttu-id="3ed3d-160">request_in.xml ファイルのコピーを HttpSolicitResponseInput フォルダーに貼り付けます。</span><span class="sxs-lookup"><span data-stu-id="3ed3d-160">Paste a copy of the file request_in.xml into the folder HttpSolicitResponseInput.</span></span>  
  
2.  <span data-ttu-id="3ed3d-161">.xml ファイルが HttpSolicitResponseOutput フォルダーに作成されたことを確認します。</span><span class="sxs-lookup"><span data-stu-id="3ed3d-161">Observe the .xml file created in the folder HttpSolicitResponseOutput.</span></span> <span data-ttu-id="3ed3d-162">この .xml ファイルの名前はメッセージ ID GUID に基づいて付けられます。</span><span class="sxs-lookup"><span data-stu-id="3ed3d-162">The name of this .xml file is based on the message ID GUID.</span></span> <span data-ttu-id="3ed3d-163">このファイルには、乗算演算の XML 形式の結果が含まれています。</span><span class="sxs-lookup"><span data-stu-id="3ed3d-163">This file contains the XML-formatted result of the multiplication operation.</span></span>  
  
    > [!NOTE]
    >  <span data-ttu-id="3ed3d-164">入力ファイルのオペランド値を変更すると、異なる乗算演算を実行できます。</span><span class="sxs-lookup"><span data-stu-id="3ed3d-164">You can change the operand values in the input file to perform a different multiplication operation.</span></span>  
  
## <a name="comments"></a><span data-ttu-id="3ed3d-165">コメント</span><span class="sxs-lookup"><span data-stu-id="3ed3d-165">Comments</span></span>  
 <span data-ttu-id="3ed3d-166">このサンプルは、HTTP インターフェイスを公開する異なる外部システムと通信するようにカスタマイズできます。</span><span class="sxs-lookup"><span data-stu-id="3ed3d-166">You can adapt this sample to communicate with a different external system that exposes an HTTP interface.</span></span>  
  
 <span data-ttu-id="3ed3d-167">MultiplyRequest.xsd ファイルと MultiplyResponse.xsd ファイルは、それぞれ、マルチプライア ASP.NET アプリケーションの入力データおよび出力データの形式を定義する XML スキーマです。</span><span class="sxs-lookup"><span data-stu-id="3ed3d-167">The files MultiplyRequest.xsd and MultiplyResponse.xsd are the XML schemas that define the format of the input and output data for the multiplier ASP.NET application.</span></span> <span data-ttu-id="3ed3d-168">オーケストレーションは、これらのファイルを使用して要求メッセージと応答メッセージの種類を定義します。</span><span class="sxs-lookup"><span data-stu-id="3ed3d-168">The orchestration uses these files to define the request and response message types.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="3ed3d-169">参照</span><span class="sxs-lookup"><span data-stu-id="3ed3d-169">See Also</span></span>  
 [<span data-ttu-id="3ed3d-170">HTTP アダプター サンプル</span><span class="sxs-lookup"><span data-stu-id="3ed3d-170">HTTP Adapter Samples</span></span>](../core/http-adapter-samples.md)