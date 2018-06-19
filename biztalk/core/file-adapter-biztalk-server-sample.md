---
title: ファイル アダプター (BizTalk Server サンプル) |Microsoft ドキュメント
ms.custom: ''
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: ''
ms.suite: ''
ms.tgt_pltfrm: ''
ms.topic: article
helpviewer_keywords:
- examples, File adapters
- File adapters, examples
ms.assetid: d59cecb4-6353-44d5-b8d6-316446758536
caps.latest.revision: 46
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: de68c57c6b435f85edf630a7b224c5d58ffd0cd6
ms.sourcegitcommit: 8418b1a8f38b7f56979cd6e203f0b591e2f40fe1
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 03/28/2018
ms.locfileid: "26010339"
---
# <a name="file-adapter-biztalk-server-sample"></a><span data-ttu-id="4f98c-102">ファイル アダプター (BizTalk Server サンプル)</span><span class="sxs-lookup"><span data-stu-id="4f98c-102">File Adapter (BizTalk Server Sample)</span></span>
<span data-ttu-id="4f98c-103">ファイル アダプター サンプルは、Microsoft Visual c# .NET で Microsoft BizTalk Server を使用する書き込まれます。</span><span class="sxs-lookup"><span data-stu-id="4f98c-103">The File Adapter sample is written in Microsoft Visual C# .NET to work with Microsoft BizTalk Server.</span></span> <span data-ttu-id="4f98c-104">このサンプルでは動的アダプターまたは静的アダプターのいずれかをビルドするコードが提供されますが、</span><span class="sxs-lookup"><span data-stu-id="4f98c-104">It provides code to build either a dynamic or a static adapter.</span></span>  <span data-ttu-id="4f98c-105">以下では静的アダプターの概要手順のみを説明します。</span><span class="sxs-lookup"><span data-stu-id="4f98c-105">However, the following procedure only outlines the static adapter.</span></span> <span data-ttu-id="4f98c-106">静的アダプターとは、静的な一連のスキーマが付属した、カスタム ユーザー インターフェイスのないアダプターのことです。</span><span class="sxs-lookup"><span data-stu-id="4f98c-106">A static adapter is an adapter with a static set of schemas and no custom user interface.</span></span> <span data-ttu-id="4f98c-107">動的アダプターにはカスタム ユーザー インターフェイスが備わっており、動的な一連のスキーマが付属していることもあります。</span><span class="sxs-lookup"><span data-stu-id="4f98c-107">A dynamic adapter has a custom user interface and potentially a dynamic set of schemas.</span></span> <span data-ttu-id="4f98c-108">静的アダプターと動的アダプターでは両方とも、アダプターの追加ウィザードを使用してスキーマを BizTalk プロジェクトに追加できます。</span><span class="sxs-lookup"><span data-stu-id="4f98c-108">Both static and dynamic adapters use the Add Adapter Wizard to add their schemas to a BizTalk project.</span></span>  
  
> [!NOTE]
>  <span data-ttu-id="4f98c-109">ファイル アダプター サンプルは、BizTalk Server に付属しているネイティブ ファイル アダプターと同じではありません。</span><span class="sxs-lookup"><span data-stu-id="4f98c-109">The File adapter sample is not the same as the native FILE adapter that ships with BizTalk Server.</span></span> <span data-ttu-id="4f98c-110">したがって、このサンプルで使用するトランスポートの種類を選択する際は、[FILE] ではなく [静的] を選択してください。</span><span class="sxs-lookup"><span data-stu-id="4f98c-110">Thus when selecting the transport type in using this sample select "static" instead of FILE.</span></span>  
  
 <span data-ttu-id="4f98c-111">カスタム ユーザー インターフェイスと動的な一連のスキーマを備えた動的アダプターを使用する場合、アダプター管理側ではコードを追加する必要があります。</span><span class="sxs-lookup"><span data-stu-id="4f98c-111">The dynamic adapter with a custom user interface and potentially dynamic set of schemas will require additional code in the adapter management side.</span></span> <span data-ttu-id="4f98c-112">動的な一連のスキーマの使用をより深く理解するを参照してください[動的デザイン時アダプター構成](../core/dynamic-design-time-adapter-configuration.md)です。</span><span class="sxs-lookup"><span data-stu-id="4f98c-112">To better understand use of the dynamic set of schemas, see [Dynamic Design-Time Adapter Configuration](../core/dynamic-design-time-adapter-configuration.md).</span></span>  
  
## <a name="what-this-sample-does"></a><span data-ttu-id="4f98c-113">このサンプルの処理</span><span class="sxs-lookup"><span data-stu-id="4f98c-113">What This Sample Does</span></span>  
 <span data-ttu-id="4f98c-114">サンプル アダプターがファイル フォルダーからファイルをコピー、メッセージとして BizTalk に送信またはからのメッセージを受け取る[!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)]ファイル フォルダーにドロップするとします。</span><span class="sxs-lookup"><span data-stu-id="4f98c-114">The sample adapter copies files from a file folder, submits to BizTalk as messages, or takes messages from [!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)] and drops to a file folder.</span></span> <span data-ttu-id="4f98c-115">このサンプルでは動的アダプターまたは静的アダプターのいずれかをビルドするコードが提供されますが、以下では静的アダプターの概要手順のみを説明します。</span><span class="sxs-lookup"><span data-stu-id="4f98c-115">It provides code to build either a dynamic or a static adapter; however, the following procedure only outlines the static adapter.</span></span> <span data-ttu-id="4f98c-116">静的アダプターとは、静的な一連のスキーマが付属した、カスタム ユーザー インターフェイスのないアダプターのことです。</span><span class="sxs-lookup"><span data-stu-id="4f98c-116">A static adapter is an adapter with a static set of schemas and no custom user interface.</span></span> <span data-ttu-id="4f98c-117">動的アダプターにはカスタム ユーザー インターフェイスが備わっており、動的な一連のスキーマが付属していることもあります。</span><span class="sxs-lookup"><span data-stu-id="4f98c-117">A dynamic adapter has a custom user interface and potentially a dynamic set of schemas.</span></span> <span data-ttu-id="4f98c-118">静的アダプターと動的アダプターでは両方とも、アダプターの追加ウィザードを使用してスキーマを BizTalk プロジェクトに追加できます。</span><span class="sxs-lookup"><span data-stu-id="4f98c-118">Both static and dynamic adapters use the Add Adapter Wizard to add their schemas to a BizTalk project.</span></span>  
  
 <span data-ttu-id="4f98c-119">このサンプル ファイル アダプターは、他のカスタム アダプターを作成する際にテンプレートとして使用できます。</span><span class="sxs-lookup"><span data-stu-id="4f98c-119">You can use the sample file adapter as a template on which to create other custom adapters.</span></span>  
  
## <a name="where-to-find-this-sample"></a><span data-ttu-id="4f98c-120">このサンプルの場所</span><span class="sxs-lookup"><span data-stu-id="4f98c-120">Where to Find This Sample</span></span>  
 <span data-ttu-id="4f98c-121">\<*パスのサンプル*\>**\AdaptersDevelopment\File アダプター**</span><span class="sxs-lookup"><span data-stu-id="4f98c-121">\<*Samples Path*\>**\AdaptersDevelopment\File Adapter**</span></span>  
  
> [!NOTE]
>  <span data-ttu-id="4f98c-122">既定の場所\<*サンプル パス*\>は *%programfiles%* \Microsoft BizTalk Server\SDK\Samples 32 ビットを実行するコンピューターに BizTalk Server がインストールされている場合Windows のバージョンです。</span><span class="sxs-lookup"><span data-stu-id="4f98c-122">The default location for \<*Samples Path*\> is *%ProgramFiles%* \Microsoft BizTalk Server\SDK\Samples when BizTalk Server is installed on a computer running a 32-bit version of Windows.</span></span> <span data-ttu-id="4f98c-123">既定の場所\<*サンプル パス*\>は *%programfiles (x86) %* \Microsoft BizTalk Server\SDK\Samples 64 を実行するコンピューターに BizTalk Server がインストールされている場合ビット版 Windows です。</span><span class="sxs-lookup"><span data-stu-id="4f98c-123">The default location for \<*Samples Path*\> is *%ProgramFiles(x86)%* \Microsoft BizTalk Server\SDK\Samples when BizTalk Server is installed on a computer running a 64-bit version of Windows.</span></span> <span data-ttu-id="4f98c-124">関連付けられている値を決定する、 *%programfiles%* または *%programfiles (x86) %* 環境変数の型 **echo %programfiles%** または **echo %programfiles (x86) %** コマンド プロンプトと ENTER キーを押します。</span><span class="sxs-lookup"><span data-stu-id="4f98c-124">To determine the values associated with the *%ProgramFiles%* or *%ProgramFiles(x86)%* environment variables type **echo %ProgramFiles%** or **echo %ProgramFiles(x86)%** at a command prompt and press ENTER.</span></span> <span data-ttu-id="4f98c-125">64 ビット オペレーティング システムでこのサンプルを実行している場合から .reg ファイルのいずれかのすべての参照を変更する必要があります。 **%programfiles%** に **%programfiles (x86) %** .reg ファイルを実行する前にします。</span><span class="sxs-lookup"><span data-stu-id="4f98c-125">If running this sample on a 64-bit operating system, you will need to change all references in any of the .reg files from **%ProgramFiles%** to **%ProgramFiles(x86)%** before running the .reg files.</span></span>  
  
 <span data-ttu-id="4f98c-126">このサンプルに含まれるファイルとその目的を次の表に示します。</span><span class="sxs-lookup"><span data-stu-id="4f98c-126">The following tables show the files in this sample and describe their purpose.</span></span>  
  
|<span data-ttu-id="4f98c-127">\File Adapter のファイル</span><span class="sxs-lookup"><span data-stu-id="4f98c-127">\File Adapter files</span></span>|<span data-ttu-id="4f98c-128">Description</span><span class="sxs-lookup"><span data-stu-id="4f98c-128">Description</span></span>|  
|--------------------------|-----------------|  
|<span data-ttu-id="4f98c-129">\BizTalk Project のファイル</span><span class="sxs-lookup"><span data-stu-id="4f98c-129">\BizTalk Project files</span></span>|<span data-ttu-id="4f98c-130">サンプル アダプターのテストに使用するアダプター ハーネス プロジェクトが含まれています。</span><span class="sxs-lookup"><span data-stu-id="4f98c-130">Contains the adapter harness project, used to test the sample adapter.</span></span>|  
|<span data-ttu-id="4f98c-131">\Design Time のファイル</span><span class="sxs-lookup"><span data-stu-id="4f98c-131">\Design Time files</span></span>|<span data-ttu-id="4f98c-132">デザイン時および管理のプロジェクト (AdapterManagement.csproj) が含まれています。</span><span class="sxs-lookup"><span data-stu-id="4f98c-132">Contains the design time and management project (AdapterManagement.csproj).</span></span>|  
|<span data-ttu-id="4f98c-133">\Runtime のファイル</span><span class="sxs-lookup"><span data-stu-id="4f98c-133">\Runtime files</span></span>|<span data-ttu-id="4f98c-134">ランタイム ファイル コピーの受信および送信プロジェクト (DotNetFile.csproj) が含まれています。</span><span class="sxs-lookup"><span data-stu-id="4f98c-134">Contains the run-time file-copy receive and transmit projects (DotNetFile.csproj).</span></span>|  
|<span data-ttu-id="4f98c-135">DynamicAdapterManagement.reg</span><span class="sxs-lookup"><span data-stu-id="4f98c-135">DynamicAdapterManagement.reg</span></span>|<span data-ttu-id="4f98c-136">サンプルの動的アダプターを登録します。</span><span class="sxs-lookup"><span data-stu-id="4f98c-136">Registers the sample dynamic adapter.</span></span>|  
|<span data-ttu-id="4f98c-137">Instance.xml</span><span class="sxs-lookup"><span data-stu-id="4f98c-137">Instance.xml</span></span>|<span data-ttu-id="4f98c-138">ファイル アダプターを通過するサンプル ファイルです。</span><span class="sxs-lookup"><span data-stu-id="4f98c-138">Sample file to pass through the file adapter.</span></span>|  
|<span data-ttu-id="4f98c-139">StaticAdapterManagement.reg</span><span class="sxs-lookup"><span data-stu-id="4f98c-139">StaticAdapterManagement.reg</span></span>|<span data-ttu-id="4f98c-140">サンプルの静的アダプターを登録します。</span><span class="sxs-lookup"><span data-stu-id="4f98c-140">Registers the sample static adapter.</span></span>|  
  
|<span data-ttu-id="4f98c-141">\BizTalk Project\Adapter Harness のファイル</span><span class="sxs-lookup"><span data-stu-id="4f98c-141">\BizTalk Project\Adapter Harness files</span></span>|<span data-ttu-id="4f98c-142">Description</span><span class="sxs-lookup"><span data-stu-id="4f98c-142">Description</span></span>|  
|----------------------------------------------|-----------------|  
|<span data-ttu-id="4f98c-143">AdapterHarness.odx、AdapterHarness.sln、AdapterHarnessProject.btproj</span><span class="sxs-lookup"><span data-stu-id="4f98c-143">AdapterHarness.odx, AdapterHarness.sln, AdapterHarnessProject.btproj</span></span>|<span data-ttu-id="4f98c-144">BizTalk プロジェクトのプロジェクト ファイル、ソリューション ファイル、その他の関連ファイルを提供します。</span><span class="sxs-lookup"><span data-stu-id="4f98c-144">Provides project, solution, and related files for the BizTalk project.</span></span>|  
|<span data-ttu-id="4f98c-145">mySchema.xsd</span><span class="sxs-lookup"><span data-stu-id="4f98c-145">mySchema.xsd</span></span>|<span data-ttu-id="4f98c-146">アダプターの受信部分からのハーネス オーケストレーションに必要とされる Instance.xml スキーマのほか、オーケストレーションによりアダプターの送信部分に渡される Instance.xml のスキーマを提供します。</span><span class="sxs-lookup"><span data-stu-id="4f98c-146">Provides the Instance.xml schema expected by the harness orchestration from the receive part of the adapter, as well as the schema of the Instance.xml handed to the send part of the adapter by the orchestration.</span></span>|  
  
|<span data-ttu-id="4f98c-147">\Design Time\Adapter Management のファイル</span><span class="sxs-lookup"><span data-stu-id="4f98c-147">\Design Time\Adapter Management files</span></span>|<span data-ttu-id="4f98c-148">Description</span><span class="sxs-lookup"><span data-stu-id="4f98c-148">Description</span></span>|  
|---------------------------------------------|-----------------|  
|<span data-ttu-id="4f98c-149">AdapterManagement.cs、AdapterManagement.csproj、AdapterManagement.sln</span><span class="sxs-lookup"><span data-stu-id="4f98c-149">AdapterManagement.cs, AdapterManagement.csproj, AdapterManagement.sln</span></span>|<span data-ttu-id="4f98c-150">アダプター デザイン時用のプロジェクト ファイル、ソリューション ファイル、その他の関連ファイルです。</span><span class="sxs-lookup"><span data-stu-id="4f98c-150">Project, solution, and related files for the adapter design-time.</span></span>|  
|<span data-ttu-id="4f98c-151">AssemblyInfo.cs</span><span class="sxs-lookup"><span data-stu-id="4f98c-151">AssemblyInfo.cs</span></span>|<span data-ttu-id="4f98c-152">このサンプルのアセンブリ情報が含まれています。</span><span class="sxs-lookup"><span data-stu-id="4f98c-152">Contains assembly information for this sample.</span></span>|  
|<span data-ttu-id="4f98c-153">CategorySchema2.xml</span><span class="sxs-lookup"><span data-stu-id="4f98c-153">CategorySchema2.xml</span></span>|<span data-ttu-id="4f98c-154">サンプル アダプターでは使用されません。</span><span class="sxs-lookup"><span data-stu-id="4f98c-154">Not used by the sample adapter.</span></span>|  
|<span data-ttu-id="4f98c-155">CategorySchema.xml</span><span class="sxs-lookup"><span data-stu-id="4f98c-155">CategorySchema.xml</span></span>|<span data-ttu-id="4f98c-156">静的アダプターのサービス構成ツリーが含まれています。</span><span class="sxs-lookup"><span data-stu-id="4f98c-156">Contains the service organization tree for the static adapter.</span></span>|  
|<span data-ttu-id="4f98c-157">DotNetFileResource.resx</span><span class="sxs-lookup"><span data-stu-id="4f98c-157">DotNetFileResource.resx</span></span>|<span data-ttu-id="4f98c-158">リソースが含まれています。</span><span class="sxs-lookup"><span data-stu-id="4f98c-158">Contains resources.</span></span>|  
|<span data-ttu-id="4f98c-159">ReceiveHandler.xsd、ReceiveLocation.xsd</span><span class="sxs-lookup"><span data-stu-id="4f98c-159">ReceiveHandler.xsd, ReceiveLocation.xsd</span></span>|<span data-ttu-id="4f98c-160">受信側のハンドラーおよびエンドポイントのカスタム プロパティ スキーマが含まれています。</span><span class="sxs-lookup"><span data-stu-id="4f98c-160">Contains receive side handler and endpoint custom property schemas</span></span>|  
|<span data-ttu-id="4f98c-161">service1.wsdl</span><span class="sxs-lookup"><span data-stu-id="4f98c-161">service1.wsdl</span></span>|<span data-ttu-id="4f98c-162">アダプターの操作定義が含まれています。</span><span class="sxs-lookup"><span data-stu-id="4f98c-162">Contains operation definitions for the adapter.</span></span>|  
|<span data-ttu-id="4f98c-163">TransmitHandler.xsd、TransmitLocation.xsd</span><span class="sxs-lookup"><span data-stu-id="4f98c-163">TransmitHandler.xsd, TransmitLocation.xsd</span></span>|<span data-ttu-id="4f98c-164">送信側のハンドラーおよびエンドポイントのカスタム プロパティ スキーマが含まれています。</span><span class="sxs-lookup"><span data-stu-id="4f98c-164">Contains transmit side handler and endpoint custom property schemas</span></span>|  
  
|<span data-ttu-id="4f98c-165">\Runtime のファイル</span><span class="sxs-lookup"><span data-stu-id="4f98c-165">\Runtime files</span></span>|<span data-ttu-id="4f98c-166">Description</span><span class="sxs-lookup"><span data-stu-id="4f98c-166">Description</span></span>|  
|---------------------|-----------------|  
|<span data-ttu-id="4f98c-167">DotNetFile.csproj、DotNetFile.sln、</span><span class="sxs-lookup"><span data-stu-id="4f98c-167">DotNetFile.csproj, DotNetFile.sln,</span></span><br /><br /> <span data-ttu-id="4f98c-168">AssemblyInfo.cs、</span><span class="sxs-lookup"><span data-stu-id="4f98c-168">AssemblyInfo.cs,</span></span><br /><br /> <span data-ttu-id="4f98c-169">DotNetFileExceptions.cs、DotNetFileProperties.cs、DotNetFileReceiver.cs、DotNetFileReceiverEndPoint.cs、DotNetFileTransmitter.cs、</span><span class="sxs-lookup"><span data-stu-id="4f98c-169">DotNetFileExceptions.cs, DotNetFileProperties.cs, DotNetFileReceiver.cs, DotNetFileReceiverEndPoint.cs, DotNetFileTransmitter.cs,</span></span><br /><br /> <span data-ttu-id="4f98c-170">DotNetFileTransmitterEndpoint.cs、</span><span class="sxs-lookup"><span data-stu-id="4f98c-170">DotNetFileTransmitterEndpoint.cs,</span></span><br /><br /> <span data-ttu-id="4f98c-171">DotNetFileAsyncTransmitterBatch.cs、</span><span class="sxs-lookup"><span data-stu-id="4f98c-171">DotNetFileAsyncTransmitterBatch.cs,</span></span><br /><br /> <span data-ttu-id="4f98c-172">BatchMessage.cs</span><span class="sxs-lookup"><span data-stu-id="4f98c-172">BatchMessage.cs</span></span>|<span data-ttu-id="4f98c-173">ランタイム ファイル コピーの送信および受信アダプター用のファイルです。</span><span class="sxs-lookup"><span data-stu-id="4f98c-173">Files for the run-time file-copy send and receive adapters.</span></span> <span data-ttu-id="4f98c-174">これらのファイルをカスタム コンポーネント用に修正し、新しい名前で保存できます。</span><span class="sxs-lookup"><span data-stu-id="4f98c-174">You can modify and save these files under a new name for custom components.</span></span><br /><br /> <span data-ttu-id="4f98c-175">DotNetFile.csproj と DotNetFile.sln はプロジェクト ファイルとソリューション ファイルです。</span><span class="sxs-lookup"><span data-stu-id="4f98c-175">DotNetFile.csproj and DotNetFile.sln are the project and solution files.</span></span><br /><br /> <span data-ttu-id="4f98c-176">AssemblyInfo.cs には、このサンプルのアセンブリ情報が含まれています。</span><span class="sxs-lookup"><span data-stu-id="4f98c-176">AssemblyInfo.cs contains assembly information for this sample.</span></span><br /><br /> <span data-ttu-id="4f98c-177">DotNetFileReceiver.cs は受信場所からファイルを読み取り、[!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)] に送信します。</span><span class="sxs-lookup"><span data-stu-id="4f98c-177">DotNetFileReceiver.cs reads the files from the receive locations and submits them to [!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)].</span></span><br /><br /> <span data-ttu-id="4f98c-178">DotNetFileExceptions.cs はメッセージ処理で発生する例外を処理するコードを実装します。</span><span class="sxs-lookup"><span data-stu-id="4f98c-178">DotNetFileExceptions.cs,implements code to handle exceptions during message processing</span></span><br /><br /> <span data-ttu-id="4f98c-179">DotNetFileProperties.cs には、送信操作と受信操作の両方に必要な共通プロパティが含まれています。</span><span class="sxs-lookup"><span data-stu-id="4f98c-179">DotNetFileProperties.cs, contains common properties for both Receive and Send operations</span></span><br /><br /> <span data-ttu-id="4f98c-180">BatchMessage.cs は、バッチによるメッセージ処理を実装します。</span><span class="sxs-lookup"><span data-stu-id="4f98c-180">BatchMessage.cs, implements batch messaging.</span></span><br /><br /> <span data-ttu-id="4f98c-181">DotNetFileReceiverEndPoint.cs は、受信場所/URI に対応するクラスで、</span><span class="sxs-lookup"><span data-stu-id="4f98c-181">DotNetFileReceiverEndPoint.cs, is a class corresponding to a Receive Location/URI.</span></span>  <span data-ttu-id="4f98c-182">新しいメッセージ用の特定のフォルダーのポーリングを処理します。</span><span class="sxs-lookup"><span data-stu-id="4f98c-182">It handles polling the given folder for new messages</span></span><br /><br /> <span data-ttu-id="4f98c-183">DotNetFileTransmitter.cs は、DotNetFile 送信アダプターの単一クラスです。</span><span class="sxs-lookup"><span data-stu-id="4f98c-183">DotNetFileTransmitter.cs is a singleton class for DotNetFile send adapter.</span></span> <span data-ttu-id="4f98c-184">この種類のアダプターの送信ポートに送られるすべてのメッセージは、このクラスで処理されます。</span><span class="sxs-lookup"><span data-stu-id="4f98c-184">All the messages, going to various send ports of this adapter type go through this class</span></span><br /><br /> <span data-ttu-id="4f98c-185">DotNetFileTransmitterEndpoint.cs はメッセージの送信を処理します。</span><span class="sxs-lookup"><span data-stu-id="4f98c-185">DotNetFileTransmitterEndpoint.cs,handles transmitting messages.</span></span>|  
  
|<span data-ttu-id="4f98c-186">\SDK\Samples\AdaptersDevelopment\BaseAdapter\v1.0.2 のファイル</span><span class="sxs-lookup"><span data-stu-id="4f98c-186">\SDK\Samples\AdaptersDevelopment\BaseAdapter\v1.0.2 files</span></span>|<span data-ttu-id="4f98c-187">Description</span><span class="sxs-lookup"><span data-stu-id="4f98c-187">Description</span></span>|  
|--------------------------------------------------------------------|-----------------|  
|<span data-ttu-id="4f98c-188">Adapter.cs、AdapterException.cs、AsyncTransmitter.cs、batch.cs、ConfigProperties.cs、ControlledTermination.cs、IManageEndpoints.cs、Receiver.cs、ReceiverEndpoint.cs</span><span class="sxs-lookup"><span data-stu-id="4f98c-188">Adapter.cs, AdapterException.cs, AsyncTransmitter.cs, batch.cs, ConfigProperties.cs, ControlledTermination.cs, IManageEndpoints.cs, Receiver.cs, ReceiverEndpoint.cs</span></span>|<span data-ttu-id="4f98c-189">ベース アダプターを構成するクラスを提供します。</span><span class="sxs-lookup"><span data-stu-id="4f98c-189">Provides classes that constitute the Base Adapter.</span></span> <span data-ttu-id="4f98c-190">これらのクラスを使用して、独自のアダプターを作成できます。</span><span class="sxs-lookup"><span data-stu-id="4f98c-190">You can use these to create your own adapters.</span></span>|  
  
## <a name="how-to-use-this-sample"></a><span data-ttu-id="4f98c-191">このサンプルの使用方法</span><span class="sxs-lookup"><span data-stu-id="4f98c-191">How to Use This Sample</span></span>  
 <span data-ttu-id="4f98c-192">サンプル ファイル アダプターは、他のカスタム アダプターを作成する際にテンプレートとして使用します。</span><span class="sxs-lookup"><span data-stu-id="4f98c-192">Use the sample file adapter as a template on which to create other custom adapters.</span></span>  
  
## <a name="building-this-sample"></a><span data-ttu-id="4f98c-193">このサンプルのビルド</span><span class="sxs-lookup"><span data-stu-id="4f98c-193">Building This Sample</span></span>  
  
> [!IMPORTANT]
>  <span data-ttu-id="4f98c-194">BizTalk 環境が 64 ビットである、またはインストール場所が変更されている場合は、それに合わせて OutboundAssemblyPath、InboundAssemblyPath、および AdapterMgmtAssemblyPath を変更する必要があります。</span><span class="sxs-lookup"><span data-stu-id="4f98c-194">If the BizTalk installation is 64-bit or the location of installation is modified, OutboundAssemblyPath, InboundAssemblyPath, AdapterMgmtAssemblyPath would need to be changed accordingly.</span></span>  
  
 <span data-ttu-id="4f98c-195">次の手順を使用して、ファイル アダプターのサンプルをビルドおよび初期化します。</span><span class="sxs-lookup"><span data-stu-id="4f98c-195">Use the following procedures to build and initialize the File Adapter sample.</span></span>  
  
#### <a name="to-create-a-strong-name-key-for-the-dotnetfileadapter-projects-and-the-base-adapter-project"></a><span data-ttu-id="4f98c-196">DotNetFileAdapter プロジェクトおよびベース アダプター プロジェクト用の厳密な名前のキーを作成するには</span><span class="sxs-lookup"><span data-stu-id="4f98c-196">To create a strong name key for the DotNetFileAdapter projects and the Base Adapter project</span></span>  
  
1.  <span data-ttu-id="4f98c-197">開始 **Visual Studio コマンド プロンプト**します。</span><span class="sxs-lookup"><span data-stu-id="4f98c-197">Start **Visual Studio Command Prompt**.</span></span>  
  
    > [!NOTE]
    >  <span data-ttu-id="4f98c-198">管理者としてコマンド プロンプトを実行します。</span><span class="sxs-lookup"><span data-stu-id="4f98c-198">Run the command prompt as an Administrator.</span></span>  
  
2.  <span data-ttu-id="4f98c-199">現在のディレクトリを変更、 \<*サンプル パス*\>**\AdaptersDevelopment\BaseAdapter\v1.0.2**ディレクトリ。</span><span class="sxs-lookup"><span data-stu-id="4f98c-199">Change the current directory to the \<*Samples Path*\>**\AdaptersDevelopment\BaseAdapter\v1.0.2** directory.</span></span>  
  
3.  <span data-ttu-id="4f98c-200">コマンド プロンプトで「 **sn – k BaseAdapter.snk** ENTER キーを押します。</span><span class="sxs-lookup"><span data-stu-id="4f98c-200">At the command prompt, type **sn –k BaseAdapter.snk** and then press ENTER.</span></span> <span data-ttu-id="4f98c-201">以前に実行されているその他のサンプルの結果としてこの .snk ファイルが既にあります。</span><span class="sxs-lookup"><span data-stu-id="4f98c-201">This .snk file may already exist as a result of other samples being run previously.</span></span> <span data-ttu-id="4f98c-202">この場合は、手順 4. に進んでください。</span><span class="sxs-lookup"><span data-stu-id="4f98c-202">If so, you can go right to step 4 and skip this step.</span></span>  
  
4.  <span data-ttu-id="4f98c-203">現在のディレクトリを変更、 \<*サンプル パス*\>\\**AdaptersDevelopment\File Adapter\Runtime**ディレクトリ。</span><span class="sxs-lookup"><span data-stu-id="4f98c-203">Change the current directory to the \<*Samples Path*\>\\**AdaptersDevelopment\File Adapter\Runtime** directory.</span></span>  
  
5.  <span data-ttu-id="4f98c-204">コマンド プロンプトで「 **sn – k DotNetFileAdapter.snk** ENTER キーを押します。</span><span class="sxs-lookup"><span data-stu-id="4f98c-204">At the command prompt, type **sn –k DotNetFileAdapter.snk** and then press ENTER.</span></span>  
  
6.  <span data-ttu-id="4f98c-205">コマンド プロンプトで「 **終了** し、enter キーを押してコマンド プロンプト ウィンドウを閉じます。</span><span class="sxs-lookup"><span data-stu-id="4f98c-205">At the command prompt, type **exit** and then press ENTER to close the command prompt window.</span></span>  
  
#### <a name="to-build-the-receiver-run-time-project"></a><span data-ttu-id="4f98c-206">レシーバー ランタイム プロジェクトをビルドするには</span><span class="sxs-lookup"><span data-stu-id="4f98c-206">To build the receiver run-time project</span></span>  
  
1.  <span data-ttu-id="4f98c-207">をクリックして **開始**, 、 をポイント **すべてのプログラム**, 、 をポイント **アクセサリ**, 、 をクリックし、 **Windows エクスプ ローラー**します。</span><span class="sxs-lookup"><span data-stu-id="4f98c-207">Click **Start**, point to **All Programs**, point to **Accessories**, and then click **Windows Explorer**.</span></span>  
  
2.  <span data-ttu-id="4f98c-208">移動し、 \<*サンプル パス*\>**"\AdaptersDevelopment\File Adapter\Runtime"** ディレクトリ、およびダブルクリック**DotNetFile.sln**.</span><span class="sxs-lookup"><span data-stu-id="4f98c-208">Navigate to the \<*Samples Path*\>**”\AdaptersDevelopment\File Adapter\Runtime”** directory, and then double-click **DotNetFile.sln**.</span></span>  
  
3.  <span data-ttu-id="4f98c-209">アダプタのレシーバ ランタイム プロジェクトのソリューション エクスプ ローラーでを再構築を右クリックし **DotNetFile**, 、クリックして **を再構築**します。</span><span class="sxs-lookup"><span data-stu-id="4f98c-209">To rebuild the Adapter Receiver run-time project, in Solution Explorer, right-click **DotNetFile**, and then click **Rebuild**.</span></span>  
  
4.  <span data-ttu-id="4f98c-210">**ファイル**  メニューのをクリックして **終了** Visual Studio を終了します。</span><span class="sxs-lookup"><span data-stu-id="4f98c-210">From the **File** menu, click **Exit** to close Visual Studio.</span></span>  
  
#### <a name="to-build-the-adapter-design-time-project"></a><span data-ttu-id="4f98c-211">アダプター デザイン時のプロジェクトをビルドするには</span><span class="sxs-lookup"><span data-stu-id="4f98c-211">To build the adapter design-time project</span></span>  
  
1.  <span data-ttu-id="4f98c-212">Windows エクスプ ローラーに移動、 \<*サンプル パス*\>**"\AdaptersDevelopment\File Adapter\Design time \adapter Management"** ディレクトリ、およびをダブルクリック**AdapterManagement.sln**です。</span><span class="sxs-lookup"><span data-stu-id="4f98c-212">In Windows Explorer, navigate to the \<*Samples Path*\>**”\AdaptersDevelopment\File Adapter\Design Time\Adapter Management”** directory, and then double-click **AdapterManagement.sln**.</span></span>  
  
2.  <span data-ttu-id="4f98c-213">ソリューション エクスプ ローラーで右クリック **AdapterManagement**, 、クリックして **を再構築**します。</span><span class="sxs-lookup"><span data-stu-id="4f98c-213">In Solution Explorer, right-click **AdapterManagement**, and then click **Rebuild**.</span></span>  
  
3.  <span data-ttu-id="4f98c-214">**ファイル**  メニューのをクリックして **終了** Visual Studio を終了します。</span><span class="sxs-lookup"><span data-stu-id="4f98c-214">From the **File** menu, click **Exit** to close Visual Studio.</span></span>  
  
#### <a name="to-register-the-sample-static-adapter"></a><span data-ttu-id="4f98c-215">サンプルの静的アダプターを登録するには</span><span class="sxs-lookup"><span data-stu-id="4f98c-215">To register the sample static adapter</span></span>  
  
1.  <span data-ttu-id="4f98c-216">Windows エクスプ ローラーに移動、 \<*サンプル パス*\>**"\AdaptersDevelopment\File アダプター"** ディレクトリ。</span><span class="sxs-lookup"><span data-stu-id="4f98c-216">In Windows Explorer, navigate to the \<*Samples Path*\>**”\AdaptersDevelopment\File Adapter”** directory.</span></span>  
  
2.  <span data-ttu-id="4f98c-217">サンプル アダプターをレジストリに追加するにはダブルクリック **StaticAdapterManagement.reg**します。</span><span class="sxs-lookup"><span data-stu-id="4f98c-217">To add the sample adapter to the registry, double-click **StaticAdapterManagement.reg**.</span></span>  
  
    > [!NOTE]
    >  <span data-ttu-id="4f98c-218">StaticAdapterManagement.reg には、C:\Program files \microsoft BizTalk Server へのハードコードされたパスが含まれています。\\です。</span><span class="sxs-lookup"><span data-stu-id="4f98c-218">StaticAdapterManagement.reg includes hard-coded paths to C:\Program Files\Microsoft BizTalk Server\\.</span></span> <span data-ttu-id="4f98c-219">インストールしていない場合[!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)]%ProgramFiles%\Microsoft BizTalk server で BizTalk Server 2009 または BizTalk Server 2006 R2 から BizTalk Server のインストールをアップグレードする場合、または BizTalk Server を実行しているコンピューターにインストールした場合は、ディレクトリ、64 ビット バージョンの Windows で、ファイル StaticAdapterManagement.reg のパスを適切に変更する必要があります。</span><span class="sxs-lookup"><span data-stu-id="4f98c-219">If you did not install [!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)] in the %ProgramFiles%\Microsoft BizTalk Server\ directory, if you upgraded your BizTalk Server installation from BizTalk Server 2009 or BizTalk Server 2006 R2, or if you installed BizTalk Server on a computer that is running a 64-bit version of Windows, you must modify the file StaticAdapterManagement.reg with the appropriate paths.</span></span> <span data-ttu-id="4f98c-220">既定では、BizTalk Server は、%programfiles(x86) %\Microsoft 64 ビット バージョンの Windows を実行しているコンピューター上の BizTalk server \ ディレクトリにインストールされます。</span><span class="sxs-lookup"><span data-stu-id="4f98c-220">By default, BizTalk Server is installed into the %ProgramFiles(x86)%\Microsoft BizTalk Server\ directory on computers that are running a 64-bit version of Windows.</span></span> <span data-ttu-id="4f98c-221">"InboundAssemblyPath"、"OutboundAssemblyPath"、および "AdapterMgmtAssemblyPath" の値に関連付けられたパスを更新し、指定されたファイルの正しい場所を指すようにします。</span><span class="sxs-lookup"><span data-stu-id="4f98c-221">Update the paths associated with the "InboundAssemblyPath", "OutboundAssemblyPath" and "AdapterMgmtAssemblyPath" values to point to the correct location of the specified files.</span></span>  
  
    > [!IMPORTANT]
    >  <span data-ttu-id="4f98c-222">BizTalk を 64 ビット コンピューターにインストールすると、hkey_classes_root \clsid\ レジストリ エントリのすべてのインスタンスを hkey_classes_root \wow6432node\clsid\ に変更、 **StaticAdapterManagement.reg** レジストリ ファイルです。</span><span class="sxs-lookup"><span data-stu-id="4f98c-222">If you install BizTalk on a 64 bit machine, change all instances of the HKEY_CLASSES_ROOT\CLSID\ registry entry to HKEY_CLASSES_ROOT\Wow6432Node\CLSID\ in the **StaticAdapterManagement.reg** registry file.</span></span>  
  
3.  <span data-ttu-id="4f98c-223">**レジストリ エディター** ダイアログ ボックスで、をクリックして **[はい]** サンプル アダプターをレジストリに追加する **[ok]** します。</span><span class="sxs-lookup"><span data-stu-id="4f98c-223">In the **Registry Editor** dialog box, click **Yes** to add the sample adapter to the registry, and then click **OK**.</span></span>  
  
4.  <span data-ttu-id="4f98c-224">Windows エクスプ ローラーを閉じる、 **ファイル**  メニューのをクリックして **閉じる**します。</span><span class="sxs-lookup"><span data-stu-id="4f98c-224">To close Windows Explorer, on the **File** menu, click **Close**.</span></span>  
  
#### <a name="to-install-the-sample-static-adapter"></a><span data-ttu-id="4f98c-225">サンプルの静的アダプターをインストールするには</span><span class="sxs-lookup"><span data-stu-id="4f98c-225">To install the sample static adapter</span></span>  
  
1.  <span data-ttu-id="4f98c-226">をクリックして**開始****すべてのプログラム**を選択[!INCLUDE[btsBizTalkServerStartMenuItemui](../includes/btsbiztalkserverstartmenuitemui-md.md)]、し、 **BizTalk Server 管理コンソール**です。</span><span class="sxs-lookup"><span data-stu-id="4f98c-226">Click **Start**, select **All Programs**, select [!INCLUDE[btsBizTalkServerStartMenuItemui](../includes/btsbiztalkserverstartmenuitemui-md.md)], and then select **BizTalk Server Administration**.</span></span>  
  
2.  <span data-ttu-id="4f98c-227">BizTalk Server 管理コンソール内をクリックして展開 **BizTalk Server 管理コンソール**, をクリックして展開 **BizTalk グループ**, をクリックして展開 **プラットフォームの設定**します。</span><span class="sxs-lookup"><span data-stu-id="4f98c-227">In the BizTalk Server Administration console, click to expand **BizTalk Server Administration**, click to expand **BizTalk Group**, and click to expand **Platform Settings**.</span></span>  
  
3.  <span data-ttu-id="4f98c-228">右クリックして **アダプター**, をクリックして **新規**, 、順にクリック **アダプター**します。</span><span class="sxs-lookup"><span data-stu-id="4f98c-228">Right click **Adapters**, click **New**, and then click **Adapter**.</span></span>  
  
4.  <span data-ttu-id="4f98c-229">**アダプターの追加**  ダイアログ ボックスで、次の操作です。</span><span class="sxs-lookup"><span data-stu-id="4f98c-229">In the **Add Adapter** dialog box, do the following.</span></span>  
  
    |<span data-ttu-id="4f98c-230">プロパティ</span><span class="sxs-lookup"><span data-stu-id="4f98c-230">Use this</span></span>|<span data-ttu-id="4f98c-231">目的</span><span class="sxs-lookup"><span data-stu-id="4f98c-231">To do this</span></span>|  
    |--------------|----------------|  
    |<span data-ttu-id="4f98c-232">**名**</span><span class="sxs-lookup"><span data-stu-id="4f98c-232">**Name**</span></span>|<span data-ttu-id="4f98c-233">型 **静的**します。</span><span class="sxs-lookup"><span data-stu-id="4f98c-233">Type **Static**.</span></span>|  
    |<span data-ttu-id="4f98c-234">**アダプター**</span><span class="sxs-lookup"><span data-stu-id="4f98c-234">**Adapter**</span></span>|<span data-ttu-id="4f98c-235">選択 **Static DotNetFile** ドロップ ダウン リストからです。</span><span class="sxs-lookup"><span data-stu-id="4f98c-235">Select **Static DotNetFile** from the drop-down list.</span></span>|  
    |<span data-ttu-id="4f98c-236">**コメント**</span><span class="sxs-lookup"><span data-stu-id="4f98c-236">**Comment**</span></span>|<span data-ttu-id="4f98c-237">型 **アダプターのサンプル**します。</span><span class="sxs-lookup"><span data-stu-id="4f98c-237">Type **Sample Adapter**.</span></span>|  
  
5.  <span data-ttu-id="4f98c-238">**[OK]** をクリックします。</span><span class="sxs-lookup"><span data-stu-id="4f98c-238">Click **OK**.</span></span>  
  
     <span data-ttu-id="4f98c-239">これで、BizTalk 管理コンソールの右ウィンドウにあるアダプターの一覧に静的アダプターが表示されます。</span><span class="sxs-lookup"><span data-stu-id="4f98c-239">The static adapter now appears in the list of adapters in the right window of the BizTalk Administration console.</span></span>  
  
#### <a name="to-stop-and-restart-the-host-instance"></a><span data-ttu-id="4f98c-240">停止して、ホスト インスタンスを再起動するには</span><span class="sxs-lookup"><span data-stu-id="4f98c-240">To stop and restart the host instance</span></span>  
  
1.  <span data-ttu-id="4f98c-241">をクリックして**開始****すべてのプログラム**を選択[!INCLUDE[btsBizTalkServerStartMenuItemui](../includes/btsbiztalkserverstartmenuitemui-md.md)]を選択し、 **BizTalk Server 管理コンソール**です。</span><span class="sxs-lookup"><span data-stu-id="4f98c-241">Click **Start**, select **All Programs**, select [!INCLUDE[btsBizTalkServerStartMenuItemui](../includes/btsbiztalkserverstartmenuitemui-md.md)], and select **BizTalk Server Administration**.</span></span>  
  
2.  <span data-ttu-id="4f98c-242">BizTalk Server 管理コンソール内をクリックして展開 **BizTalk Server 管理コンソール**, をクリックして展開 **BizTalk グループ**, をクリックして展開 **プラットフォームの設定**  をクリック **ホスト インスタンス**します。</span><span class="sxs-lookup"><span data-stu-id="4f98c-242">In the BizTalk Server Administration console, click to expand **BizTalk Server Administration**, click to expand **BizTalk Group**, click to expand **Platform Settings** and click **Host Instances**.</span></span> <span data-ttu-id="4f98c-243">右ペインで、[BizTalkServerApplication] を選択します。</span><span class="sxs-lookup"><span data-stu-id="4f98c-243">Select the BizTalkServerApplication in the right pane.</span></span>  
  
3.  <span data-ttu-id="4f98c-244">結果ウィンドウで、ホスト インスタンス (通常は、コンピューター名) を右クリックし、クリックして **再起動**します。</span><span class="sxs-lookup"><span data-stu-id="4f98c-244">In the results pane, right-click the host instance (typically, the computer name), and then click **Restart**.</span></span>  
  
### <a name="running-this-sample"></a><span data-ttu-id="4f98c-245">このサンプルの実行</span><span class="sxs-lookup"><span data-stu-id="4f98c-245">Running This Sample</span></span>  
  
##### <a name="to-run-the-file-adapter-sample"></a><span data-ttu-id="4f98c-246">ファイル アダプターのサンプルを実行するには</span><span class="sxs-lookup"><span data-stu-id="4f98c-246">To run the File Adapter sample</span></span>  
  
1.  <span data-ttu-id="4f98c-247">をクリックして **開始**, 、 をポイント **すべてのプログラム**, 、 をポイント **アクセサリ**, 、 をクリックし、 **Windows エクスプ ローラー**します。</span><span class="sxs-lookup"><span data-stu-id="4f98c-247">Click **Start**, point to **All Programs**, point to **Accessories**, and then click **Windows Explorer**.</span></span>  
  
2.  <span data-ttu-id="4f98c-248">BizTalk Server のインストール ドライブに、次のフォルダーを作成します。</span><span class="sxs-lookup"><span data-stu-id="4f98c-248">Create the following folders on the BizTalk Server installation drive:</span></span>  
  
    -   <span data-ttu-id="4f98c-249">*\<drive\>*:**\Temp**</span><span class="sxs-lookup"><span data-stu-id="4f98c-249">*\<drive\>*:**\Temp**</span></span>  
  
    -   <span data-ttu-id="4f98c-250">*\<drive\>*:**\Temp\Send**</span><span class="sxs-lookup"><span data-stu-id="4f98c-250">*\<drive\>*:**\Temp\Send**</span></span>  
  
    -   <span data-ttu-id="4f98c-251">*\<drive\>*:**\Temp\Receive**</span><span class="sxs-lookup"><span data-stu-id="4f98c-251">*\<drive\>*:**\Temp\Receive**</span></span>  
  
3.  <span data-ttu-id="4f98c-252">Windows エクスプ ローラーを閉じる、 **ファイル**  メニューのをクリックして **閉じる**します。</span><span class="sxs-lookup"><span data-stu-id="4f98c-252">To close Windows Explorer, on the **File** menu, click **Close**.</span></span>  
  
4.  <span data-ttu-id="4f98c-253">をクリックして**開始**、 をポイント**すべてのプログラム**、 をポイント[!INCLUDE[btsBizTalkServerStartMenuItemui](../includes/btsbiztalkserverstartmenuitemui-md.md)]、順にクリック**BizTalk Server 管理コンソール**です。</span><span class="sxs-lookup"><span data-stu-id="4f98c-253">Click **Start**, point to **All Programs**, point to [!INCLUDE[btsBizTalkServerStartMenuItemui](../includes/btsbiztalkserverstartmenuitemui-md.md)], and then click **BizTalk Server Administration**.</span></span>  
  
5.  <span data-ttu-id="4f98c-254">右クリックし、 **BizTalk Server 管理コンソール**  ノード **既存のグループへの接続**します。</span><span class="sxs-lookup"><span data-stu-id="4f98c-254">Right-click the **BizTalk Server Administration**  node and select **Connect to Existing Group**.</span></span>  
  
6.  <span data-ttu-id="4f98c-255">**既存の BizTalk Server 構成データベースへの接続**  ダイアログ ボックスで、次の操作です。</span><span class="sxs-lookup"><span data-stu-id="4f98c-255">In the **Connect to Existing BizTalk Server Configuration Database** dialog box, do the following.</span></span>  
  
    > [!NOTE]
    >  <span data-ttu-id="4f98c-256">BizTalk 管理データベースは、BizTalk 構成データベースとも呼ばれます。</span><span class="sxs-lookup"><span data-stu-id="4f98c-256">The BizTalk Management database is also referred to as the BizTalk Configuration database.</span></span>  
  
    |<span data-ttu-id="4f98c-257">プロパティ</span><span class="sxs-lookup"><span data-stu-id="4f98c-257">Use this</span></span>|<span data-ttu-id="4f98c-258">目的</span><span class="sxs-lookup"><span data-stu-id="4f98c-258">To do this</span></span>|  
    |--------------|----------------|  
    |<span data-ttu-id="4f98c-259">**SQL Server**</span><span class="sxs-lookup"><span data-stu-id="4f98c-259">**SQL Server**</span></span>|<span data-ttu-id="4f98c-260">型 **します。**</span><span class="sxs-lookup"><span data-stu-id="4f98c-260">Type **.**</span></span> <span data-ttu-id="4f98c-261">」 (ピリオド) を入力します。</span><span class="sxs-lookup"><span data-stu-id="4f98c-261">(a period).</span></span>|  
    |<span data-ttu-id="4f98c-262">**データベース**</span><span class="sxs-lookup"><span data-stu-id="4f98c-262">**Database**</span></span>|<span data-ttu-id="4f98c-263">構成ウィザードで作成された BizTalk 管理データベースの名前を選択します。</span><span class="sxs-lookup"><span data-stu-id="4f98c-263">Select the name of the BizTalk Management database that was created by the Configuration Wizard.</span></span> <span data-ttu-id="4f98c-264">構成ウィザードで使用される既定のデータベース名は **BizTalkMgmtDb**します。</span><span class="sxs-lookup"><span data-stu-id="4f98c-264">The default database name used by the Configuration Wizard is **BizTalkMgmtDb**.</span></span>|  
  
7.  <span data-ttu-id="4f98c-265">**[OK]** をクリックします。</span><span class="sxs-lookup"><span data-stu-id="4f98c-265">Click **OK**.</span></span>  
  
8.  <span data-ttu-id="4f98c-266">展開、 **BizTalk グループ [*サーバー名*]** 内のノード、[!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)]管理コンソールで、展開、**アプリケーション** ノードを展開、 **BizTalk アプリケーション 1**ノード。</span><span class="sxs-lookup"><span data-stu-id="4f98c-266">Expand the **BizTalk Group[*server name*]** node in the [!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)] Administration console, expand the **Applications** node, expand the  **BizTalk Application 1** node.</span></span>  
  
9. <span data-ttu-id="4f98c-267">右クリックし、 **送信ポート**  ノードをクリック **新規**,  **静的な一方向送信ポート**, 、 をクリックし、 **ok**します。</span><span class="sxs-lookup"><span data-stu-id="4f98c-267">Right-click the **Send Ports** node, and then click **New**, select **Static One-Way Send Port**, and then click **OK**.</span></span>  
  
10. <span data-ttu-id="4f98c-268">**送信ポートのプロパティ** ダイアログ ボックスで、 **全般**, 、し、次の操作を行います。</span><span class="sxs-lookup"><span data-stu-id="4f98c-268">In the **Send Port Properties** dialog box, select **General**, and do the following.</span></span>  
  
    |<span data-ttu-id="4f98c-269">プロパティ</span><span class="sxs-lookup"><span data-stu-id="4f98c-269">Use this</span></span>|<span data-ttu-id="4f98c-270">目的</span><span class="sxs-lookup"><span data-stu-id="4f98c-270">To do this</span></span>|  
    |--------------|----------------|  
    |<span data-ttu-id="4f98c-271">**名**</span><span class="sxs-lookup"><span data-stu-id="4f98c-271">**Name**</span></span>|<span data-ttu-id="4f98c-272">型 **AdapterSend**します。</span><span class="sxs-lookup"><span data-stu-id="4f98c-272">Type **AdapterSend**.</span></span>|  
    |<span data-ttu-id="4f98c-273">**トランスポートの種類**</span><span class="sxs-lookup"><span data-stu-id="4f98c-273">**Transport Type**</span></span>|<span data-ttu-id="4f98c-274">選択 **静的**  をクリック、ドロップ ダウン リストから **構成**します。</span><span class="sxs-lookup"><span data-stu-id="4f98c-274">Select **Static** from the drop-down list and click **Configure**.</span></span><br /><br /> <span data-ttu-id="4f98c-275">-、**ディレクトリ**ボックスに、入力 ***\<ドライブ\>*:\Temp\Send**です。</span><span class="sxs-lookup"><span data-stu-id="4f98c-275">-   In the **Directory** box, type ***\<drive\>*:\Temp\Send**.</span></span><br /><span data-ttu-id="4f98c-276">-、 **ファイル モード** ボックスで、 **CreateNew**します。</span><span class="sxs-lookup"><span data-stu-id="4f98c-276">-   In the **File Mode** box, select **CreateNew**.</span></span><br /><span data-ttu-id="4f98c-277">-、 **ファイル名** ボックスに、入力 **%MessageID%.xml**します。</span><span class="sxs-lookup"><span data-stu-id="4f98c-277">-   In the **File Name** box, type **%MessageID%.xml**.</span></span><br /><span data-ttu-id="4f98c-278">- **OK**します。</span><span class="sxs-lookup"><span data-stu-id="4f98c-278">-   Click **OK**.</span></span><br /><span data-ttu-id="4f98c-279">- **URI**フィールドを表示する必要があります ***\<ドライブ\>*:\Temp\Send\\%MessageID%.xml**です。</span><span class="sxs-lookup"><span data-stu-id="4f98c-279">-   The **URI** field should show ***\<drive\>*:\Temp\Send\\%MessageID%.xml**.</span></span>|  
    |<span data-ttu-id="4f98c-280">**送信パイプライン**</span><span class="sxs-lookup"><span data-stu-id="4f98c-280">**Send pipeline**</span></span>|<span data-ttu-id="4f98c-281">選択 **PassThruTransmit (Microsoft.BizTalk.DefaultPipelines.PassThruTransmit)**, 、 をクリックし、 **OK**します。</span><span class="sxs-lookup"><span data-stu-id="4f98c-281">Select **PassThruTransmit (Microsoft.BizTalk.DefaultPipelines.PassThruTransmit)**, and then click **OK**.</span></span>|  
  
11. <span data-ttu-id="4f98c-282">下にある、 **BizTalk アプリケーション 1**  ノードをクリック **受信ポート**, を選択して **新規/一方向の受信ポート**します。</span><span class="sxs-lookup"><span data-stu-id="4f98c-282">Under the **BizTalk Application 1** node click **Receive Ports**, and select **New / One-Way Receive Port**.</span></span>  
  
12. <span data-ttu-id="4f98c-283">**新しい受信ポートを作成する** ダイアログ ボックスで、 **受信ポートの種類を指定** ボックスで、 **一方向の受信ポート** クリックしてドロップダウン リストから **[ok]** します。</span><span class="sxs-lookup"><span data-stu-id="4f98c-283">In the **Create New Receive Port** dialog box, in the **Specify the type of Receive Port** box, select **One-way Receive Port** from the drop-down list, and then click **OK**.</span></span>  
  
13. <span data-ttu-id="4f98c-284">**受信ポートのプロパティ** ダイアログ ボックスで、 **名前** ボックスに、入力 **AdapterReceive**, 、 をクリックし、 **ok**します。</span><span class="sxs-lookup"><span data-stu-id="4f98c-284">In the **Receive Port Properties** dialog box, in the **Name** box, type **AdapterReceive**, and then click **OK**.</span></span>  
  
14. <span data-ttu-id="4f98c-285">下にある、 **BizTalk アプリケーション 1** ノードを右クリックして **受信場所**, を選択して **新規/一方向の受信場所**します。</span><span class="sxs-lookup"><span data-stu-id="4f98c-285">Under the **BizTalk Application 1** node right click **Receive Locations**, and select **New / One-way Receive Location**.</span></span>  
  
15. <span data-ttu-id="4f98c-286">**受信ポートの選択**  ダイアログ ボックスで選択 **AdapterReceive**  をクリックし、 **OK**します。</span><span class="sxs-lookup"><span data-stu-id="4f98c-286">In the **Select a Receive Port** dialog, select **AdapterReceive** then click **OK**.</span></span>  
  
16. <span data-ttu-id="4f98c-287">**受信場所のプロパティ**  ダイアログ ボックスで、次の操作です。</span><span class="sxs-lookup"><span data-stu-id="4f98c-287">In the **Receive Location Properties** dialog box, do the following.</span></span>  
  
    |<span data-ttu-id="4f98c-288">プロパティ</span><span class="sxs-lookup"><span data-stu-id="4f98c-288">Use this</span></span>|<span data-ttu-id="4f98c-289">目的</span><span class="sxs-lookup"><span data-stu-id="4f98c-289">To do this</span></span>|  
    |--------------|----------------|  
    |<span data-ttu-id="4f98c-290">**名**</span><span class="sxs-lookup"><span data-stu-id="4f98c-290">**Name**</span></span>|<span data-ttu-id="4f98c-291">型 **AdapterReceiveLocation**</span><span class="sxs-lookup"><span data-stu-id="4f98c-291">Type **AdapterReceiveLocation**</span></span>|  
    |<span data-ttu-id="4f98c-292">**トランスポートの種類**</span><span class="sxs-lookup"><span data-stu-id="4f98c-292">**Transport Type**</span></span>|<span data-ttu-id="4f98c-293">選択 **静的** ヒット、ドロップ ダウン リストから **構成** にこれらの残りのプロパティにアクセスします。</span><span class="sxs-lookup"><span data-stu-id="4f98c-293">Select **Static** from the drop-down list and hit **Configure** to access these remaining properties.</span></span>|  
    |<span data-ttu-id="4f98c-294">**URI**</span><span class="sxs-lookup"><span data-stu-id="4f98c-294">**URI**</span></span>|<span data-ttu-id="4f98c-295">省略記号ボタンをクリックする (**...**)。</span><span class="sxs-lookup"><span data-stu-id="4f98c-295">-   Click the ellipsis button (**…**).</span></span><br /><span data-ttu-id="4f98c-296">-、 **数 Of Files In Batch** ボックスに、入力 **20**します。</span><span class="sxs-lookup"><span data-stu-id="4f98c-296">-   In the **Number Of Files In Batch** box, type **20**.</span></span><br /><span data-ttu-id="4f98c-297">-、**ディレクトリ**ボックスに、入力 ***\<ドライブ\>*:\Temp\Receive**です。</span><span class="sxs-lookup"><span data-stu-id="4f98c-297">-   In the **Directory** box, type ***\<drive\>*:\Temp\Receive**.</span></span><br /><span data-ttu-id="4f98c-298">-、 **ファイル マスク** にプロパティが設定されている **\*.xml**します。</span><span class="sxs-lookup"><span data-stu-id="4f98c-298">-   Ensure the **File Mask** property is set to **\*.xml**.</span></span><br /><span data-ttu-id="4f98c-299">-、 **のポーリング間隔** ボックスに、入力 **5**, 、 をクリック **OK**します。</span><span class="sxs-lookup"><span data-stu-id="4f98c-299">-   In the **Polling Interval** box, type **5**, and click **OK**.</span></span><br /><span data-ttu-id="4f98c-300">-、 **URI**ラベルが含まれています \***\<ドライブ\>\*:\Temp\Receive\\\*.xml**です。</span><span class="sxs-lookup"><span data-stu-id="4f98c-300">-   Ensure the **URI** label contains \***\<drive\>\*:\Temp\Receive\\\*.xml**.</span></span>|  
    |<span data-ttu-id="4f98c-301">**受信ハンドラー**</span><span class="sxs-lookup"><span data-stu-id="4f98c-301">**Receive Handler**</span></span>|<span data-ttu-id="4f98c-302">選択 **BizTalkServerApplication** ドロップ ダウン リストからです。</span><span class="sxs-lookup"><span data-stu-id="4f98c-302">Select **BizTalkServerApplication** from the drop-down list.</span></span>|  
    |<span data-ttu-id="4f98c-303">**受信パイプライン**</span><span class="sxs-lookup"><span data-stu-id="4f98c-303">**Receive Pipeline**</span></span>|<span data-ttu-id="4f98c-304">選択 **XMLReceive** ドロップ ダウン リストからです。</span><span class="sxs-lookup"><span data-stu-id="4f98c-304">Select **XMLReceive** from the drop-down list.</span></span>|  
  
17. <span data-ttu-id="4f98c-305">**[OK]** をクリックします。</span><span class="sxs-lookup"><span data-stu-id="4f98c-305">Click **OK**.</span></span>  
  
     <span data-ttu-id="4f98c-306">」に進みます *ビルド、配置、およびサンプル アダプター バインド*します。</span><span class="sxs-lookup"><span data-stu-id="4f98c-306">Proceed to *Building, Deploying, and Binding the Sample Adapter*.</span></span>  
  
### <a name="building-deploying-and-binding-the-sample-adapter"></a><span data-ttu-id="4f98c-307">サンプル アダプターのビルド、展開、およびバインド</span><span class="sxs-lookup"><span data-stu-id="4f98c-307">Building, Deploying, and Binding the Sample Adapter</span></span>  
 <span data-ttu-id="4f98c-308">アダプターを実際に使用するには、その前にプロジェクトをビルドし、オーケストレーションにポートをバインドして、アダプターを参加させる必要があります。</span><span class="sxs-lookup"><span data-stu-id="4f98c-308">Before the adapter goes live, you must build the project, bind the orchestration with the ports, and enlist the adapter.</span></span>  
  
##### <a name="to-create-a-strong-name-key-for-the-static-adapter"></a><span data-ttu-id="4f98c-309">静的アダプター用の厳密な名前のキーを作成するには</span><span class="sxs-lookup"><span data-stu-id="4f98c-309">To create a strong name key for the static adapter</span></span>  
  
1.  <span data-ttu-id="4f98c-310">開始 **Visual Studio コマンド プロンプト**します。</span><span class="sxs-lookup"><span data-stu-id="4f98c-310">Start **Visual Studio Command Prompt**.</span></span>  
  
2.  <span data-ttu-id="4f98c-311">コマンド プロンプトでは、現在のディレクトリを変更する、 \<*サンプル パス*\>**\AdaptersDevelopment\File Adapter\BizTalk Project\Adapter ハーネス**ディレクトリ。</span><span class="sxs-lookup"><span data-stu-id="4f98c-311">At the command prompt, change the current directory to the \<*Samples Path*\>**\AdaptersDevelopment\File Adapter\BizTalk Project\Adapter Harness** directory.</span></span>  
  
3.  <span data-ttu-id="4f98c-312">コマンド プロンプトで「 **sn – k AdapterHarness.snk**, 、とし、enter キーを押します。</span><span class="sxs-lookup"><span data-stu-id="4f98c-312">At the command prompt, type **sn –k AdapterHarness.snk**, and then pressENTER.</span></span>  
  
4.  <span data-ttu-id="4f98c-313">**[OK]** をクリックします。</span><span class="sxs-lookup"><span data-stu-id="4f98c-313">Click **OK**.</span></span>  
  
##### <a name="to-build-the-adapter-harness-project"></a><span data-ttu-id="4f98c-314">アダプター ハーネス プロジェクトをビルドするには</span><span class="sxs-lookup"><span data-stu-id="4f98c-314">To build the Adapter Harness project</span></span>  
  
-   <span data-ttu-id="4f98c-315">ソリューション エクスプ ローラーで右クリック **[adapterharnessproject]**, 、クリックして **を再構築**します。</span><span class="sxs-lookup"><span data-stu-id="4f98c-315">In Solution Explorer, right-click **AdapterHarnessProject**, and then click **Rebuild**.</span></span>  
  
##### <a name="to-deploy-the-adapter-harness-project"></a><span data-ttu-id="4f98c-316">アダプター ハーネス プロジェクトを展開するには</span><span class="sxs-lookup"><span data-stu-id="4f98c-316">To deploy the Adapter Harness project</span></span>  
  
1.  <span data-ttu-id="4f98c-317">ソリューション エクスプ ローラーでプロジェクトがリビルドされるときに、右クリック **[adapterharnessproject]**, 、クリックして **展開**します。</span><span class="sxs-lookup"><span data-stu-id="4f98c-317">In Solution Explorer, when the project has rebuilt, right-click **AdapterHarnessProject**, and then click **Deploy**.</span></span>  
  
2.  <span data-ttu-id="4f98c-318">BizTalk Server 管理コンソールで、プロジェクトを選択および展開しました をクリックし、 **更新**します。</span><span class="sxs-lookup"><span data-stu-id="4f98c-318">In BizTalk Server Administration console, select the project you have deployed, and then click **Refresh**.</span></span>  
  
##### <a name="to-bind-the-orchestration-with-the-ports"></a><span data-ttu-id="4f98c-319">オーケストレーションにポートをバインドするには</span><span class="sxs-lookup"><span data-stu-id="4f98c-319">To bind the orchestration with the ports</span></span>  
  
1.  <span data-ttu-id="4f98c-320">[!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)]管理コンソールで、適切な [!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)]アプリケーション、展開、**オーケストレーション**ノード。</span><span class="sxs-lookup"><span data-stu-id="4f98c-320">In [!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)] Administration console, under the appropriate [!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)] application, expand the **Orchestrations** node.</span></span>  
  
2.  <span data-ttu-id="4f98c-321">右クリック **AdapterHarness.AdapterHarnessType**, 、クリックして **バインド**します。</span><span class="sxs-lookup"><span data-stu-id="4f98c-321">Right-click **AdapterHarness.AdapterHarnessType**, and then click **Bind**.</span></span>  
  
3.  <span data-ttu-id="4f98c-322">**ポート バインドのプロパティ - adapterharness.adapterharnesstype-Binding Configurations**  ダイアログ ボックスで、次の操作です。</span><span class="sxs-lookup"><span data-stu-id="4f98c-322">In the **Port Binding Properties - AdapterHarness.AdapterHarnessType- Binding Configurations** dialog box, do the following.</span></span>  
  
    |<span data-ttu-id="4f98c-323">プロパティ</span><span class="sxs-lookup"><span data-stu-id="4f98c-323">Use this</span></span>|<span data-ttu-id="4f98c-324">目的</span><span class="sxs-lookup"><span data-stu-id="4f98c-324">To do this</span></span>|  
    |--------------|----------------|  
    |<span data-ttu-id="4f98c-325">**AdapterFileReceivePort**</span><span class="sxs-lookup"><span data-stu-id="4f98c-325">**AdapterFileReceivePort**</span></span>|<span data-ttu-id="4f98c-326">選択 **AdapterReceive** ドロップ ダウン リストからです。</span><span class="sxs-lookup"><span data-stu-id="4f98c-326">Select **AdapterReceive** from the drop-down list.</span></span>|  
    |<span data-ttu-id="4f98c-327">**AdapterFileSendPort**</span><span class="sxs-lookup"><span data-stu-id="4f98c-327">**AdapterFileSendPort**</span></span>|<span data-ttu-id="4f98c-328">選択 **AdapterSend** ドロップ ダウン リストからです。</span><span class="sxs-lookup"><span data-stu-id="4f98c-328">Select **AdapterSend** from the drop-down list.</span></span>|  
  
4.  <span data-ttu-id="4f98c-329">左のウィンドウで **ホスト**します。</span><span class="sxs-lookup"><span data-stu-id="4f98c-329">In the left pane, click **Host**.</span></span>  
  
5.  <span data-ttu-id="4f98c-330">**ホスト** ボックスで、 **BizTalkServerApplication** クリックしてドロップダウン リストから **OK**します。</span><span class="sxs-lookup"><span data-stu-id="4f98c-330">In the **Host** box, select **BizTalkServerApplication** from the drop-down list, and then click **OK**.</span></span>  
  
 <span data-ttu-id="4f98c-331">」に進みます *サンプル アダプターを管理する*です。</span><span class="sxs-lookup"><span data-stu-id="4f98c-331">Proceed to *Administering the Sample Adapter*.</span></span>  
  
### <a name="administering-the-sample-adapter"></a><span data-ttu-id="4f98c-332">サンプル アダプターの管理</span><span class="sxs-lookup"><span data-stu-id="4f98c-332">Administering the Sample Adapter</span></span>  
 <span data-ttu-id="4f98c-333">BizTalk 管理コンソールで、サンプル アダプターに対する管理タスクを実行します。</span><span class="sxs-lookup"><span data-stu-id="4f98c-333">You complete administration tasks for the sample adapter in the BizTalk Administration console.</span></span>  
  
##### <a name="to-administer-the-file-adapter-sample"></a><span data-ttu-id="4f98c-334">ファイル アダプターのサンプルを管理するには</span><span class="sxs-lookup"><span data-stu-id="4f98c-334">To administer the File Adapter sample</span></span>  
  
1.  <span data-ttu-id="4f98c-335">をクリックして**開始**、 をポイント**すべてのプログラム**、 をポイント[!INCLUDE[btsBizTalkServerStartMenuItemui](../includes/btsbiztalkserverstartmenuitemui-md.md)]、順にクリック**BizTalk Server 管理コンソール**です。</span><span class="sxs-lookup"><span data-stu-id="4f98c-335">Click **Start**, point to **All Programs**, point to [!INCLUDE[btsBizTalkServerStartMenuItemui](../includes/btsbiztalkserverstartmenuitemui-md.md)], and then click **BizTalk Server Administration**.</span></span>  
  
2.  <span data-ttu-id="4f98c-336">左側のウィンドウで、クリックして展開 **アプリケーション**, をクリックして展開 **BizTalk アプリケーション 1**, 、 をクリック **受信場所**します。</span><span class="sxs-lookup"><span data-stu-id="4f98c-336">In the left pane, click to expand **Applications**, click to expand **BizTalk Application 1**, and click **Receive Locations**.</span></span>  
  
3.  <span data-ttu-id="4f98c-337">確認、 **AdapterReceive** 状態が  **Enabled**します。</span><span class="sxs-lookup"><span data-stu-id="4f98c-337">Ensure the **AdapterReceive** status is **Enabled**.</span></span>  
  
     <span data-ttu-id="4f98c-338">状態がない場合 **有効**, を右クリックして **AdapterReceive** をクリックして右側のペイン **を有効にする**です。</span><span class="sxs-lookup"><span data-stu-id="4f98c-338">If the status is not **Enabled**, right-click **AdapterReceive** in the right pane, and then click **Enable**.</span></span>  
  
4.  <span data-ttu-id="4f98c-339">左のウィンドウで **オーケストレーション** いることを確認および **AdapterHarness.AdapterHarnessType** は **参加している**します。</span><span class="sxs-lookup"><span data-stu-id="4f98c-339">In the left pane, click **Orchestrations** and ensure that **AdapterHarness.AdapterHarnessType** is **Enlisted**.</span></span> <span data-ttu-id="4f98c-340">右クリックして **AdapterHarness.AdapterHarnessType**, 、 をクリックし、 **Enlist** (AdapterHarness.AdapterHarnessType が既に参加している場合、 **Enlist** メニュー オプションは使用できません)。</span><span class="sxs-lookup"><span data-stu-id="4f98c-340">Right click **AdapterHarness.AdapterHarnessType**, and then click **Enlist** (if AdapterHarness.AdapterHarnessType is already enlisted, the **Enlist** menu option is unavailable).</span></span>  
  
5.  <span data-ttu-id="4f98c-341">右クリック **AdapterHarness.AdapterHarnessType** 選択 **開始**します。</span><span class="sxs-lookup"><span data-stu-id="4f98c-341">Right-click **AdapterHarness.AdapterHarnessType** and select **Start**.</span></span> <span data-ttu-id="4f98c-342">このオーケストレーションの状態に変わります **を実行している**します。</span><span class="sxs-lookup"><span data-stu-id="4f98c-342">The status of this orchestration should change to **Running**.</span></span>  
  
 <span data-ttu-id="4f98c-343">」に進みます *サンプル アダプターのテスト*します。</span><span class="sxs-lookup"><span data-stu-id="4f98c-343">Proceed to *Testing the Sample Adapter*.</span></span>  
  
### <a name="testing-the-sample-adapter"></a><span data-ttu-id="4f98c-344">サンプル アダプターのテスト</span><span class="sxs-lookup"><span data-stu-id="4f98c-344">Testing the Sample Adapter</span></span>  
 <span data-ttu-id="4f98c-345">サンプル アダプターを展開したら、ホスト インスタンスを停止して再起動する必要があります。</span><span class="sxs-lookup"><span data-stu-id="4f98c-345">After you deploy the sample adapter, you must stop and restart the host instance.</span></span> <span data-ttu-id="4f98c-346">サンプル アダプターを運用する前には必ずテストしてください。</span><span class="sxs-lookup"><span data-stu-id="4f98c-346">It is critical that you test the sample adapter before you place it into production.</span></span>  
  
##### <a name="to-stop-and-restart-the-host-instance"></a><span data-ttu-id="4f98c-347">停止して、ホスト インスタンスを再起動するには</span><span class="sxs-lookup"><span data-stu-id="4f98c-347">To stop and restart the host instance</span></span>  
  
1.  <span data-ttu-id="4f98c-348">**BizTalk Server 管理コンソール** コンソールをクリックして展開 **BizTalk Server 管理コンソール**, をクリックして展開 **BizTalk グループ**, をクリックして展開 **プラットフォームの設定**  をクリック **ホスト インスタンス**します。</span><span class="sxs-lookup"><span data-stu-id="4f98c-348">In the **BizTalk Server Administration** console, click to expand **BizTalk Server Administration**, click to expand **BizTalk Group**, click to expand **Platform Settings** and click **Host Instances**.</span></span> <span data-ttu-id="4f98c-349">右ペインで、[BizTalkServerApplication] を選択します。</span><span class="sxs-lookup"><span data-stu-id="4f98c-349">Select the BizTalkServerApplication in the right pane.</span></span>  
  
2.  <span data-ttu-id="4f98c-350">ホスト インスタンス (通常は、コンピューター名) を右クリックし、 **停止**します。</span><span class="sxs-lookup"><span data-stu-id="4f98c-350">Right-click the host instance (typically, the computer name), and then click **Stop**.</span></span>  
  
     <span data-ttu-id="4f98c-351">ホスト インスタンスの状態に変わる **Stopped**します。</span><span class="sxs-lookup"><span data-stu-id="4f98c-351">The status of the host instance changes to **Stopped**.</span></span>  
  
3.  <span data-ttu-id="4f98c-352">ホスト インスタンスを右クリックし、 **開始**します。</span><span class="sxs-lookup"><span data-stu-id="4f98c-352">Right-click the host instance, and then click **Start**.</span></span>  
  
     <span data-ttu-id="4f98c-353">ホスト インスタンスの状態に変わる **を実行している**します。</span><span class="sxs-lookup"><span data-stu-id="4f98c-353">The status of the host instance changes to **Running**.</span></span>  
  
##### <a name="to-test-the-sample-static-adapter-runtime"></a><span data-ttu-id="4f98c-354">サンプルの静的アダプターをランタイムでテストするには</span><span class="sxs-lookup"><span data-stu-id="4f98c-354">To test the sample static adapter runtime</span></span>  
  
1.  <span data-ttu-id="4f98c-355">Windows エクスプ ローラーに移動、 \<*サンプル パス*\>**\AdaptersDevelopment\File アダプター**ディレクトリ、および InstanceXML.xml ファイルをクリップボードにコピーします。</span><span class="sxs-lookup"><span data-stu-id="4f98c-355">In Windows Explorer, navigate to the \<*Samples Path*\>**\AdaptersDevelopment\File Adapter** directory, and copy the InstanceXML.xml file to your clipboard.</span></span>  
  
2.  <span data-ttu-id="4f98c-356">移動*\<ドライブ\>*:**\Temp\Receive**し、Instance.xml ファイルをフォルダーに貼り付けます。</span><span class="sxs-lookup"><span data-stu-id="4f98c-356">Navigate to *\<drive\>*:**\Temp\Receive** and paste the Instance.xml file into the folder.</span></span>  
  
     <span data-ttu-id="4f98c-357">場合、送信と受信を使用しているアダプターからファイルを移動する必要があります、 *\<ドライブ\>*:**\Temp\Receive**フォルダーを*\<ドライブ\>* :**\Temp\Send**フォルダーです。</span><span class="sxs-lookup"><span data-stu-id="4f98c-357">If the transmit and receive adapters are working, the file should move from the *\<drive\>*:**\Temp\Receive** folder to the *\<drive\>*:**\Temp\Send** folder.</span></span>  
  
##### <a name="to-test-the-sample-add-adapter-wizard-functionality-for-the-sample-static-adapter"></a><span data-ttu-id="4f98c-358">サンプルの静的アダプターで、サンプルのアダプターの追加ウィザード機能をテストするには</span><span class="sxs-lookup"><span data-stu-id="4f98c-358">To test the sample Add Adapter Wizard functionality for the sample static adapter</span></span>  
  
1.  <span data-ttu-id="4f98c-359">[!INCLUDE[btsVStudioNoVersion](../includes/btsvstudionoversion-md.md)]、ソリューション エクスプ ローラーで右クリック **[adapterharnessproject]**、をポイント**追加**、クリックして**生成した項目の追加**です。</span><span class="sxs-lookup"><span data-stu-id="4f98c-359">In [!INCLUDE[btsVStudioNoVersion](../includes/btsvstudionoversion-md.md)], in Solution Explorer, right-click **AdapterHarnessProject**, point to **Add**, and then click **Add Generated Items**.</span></span>  
  
2.  <span data-ttu-id="4f98c-360">**生成項目の追加 - [adapterharnessproject]** ダイアログ ボックスで、をクリックして **アダプター メタデータの追加**, 、順にクリック **開く**します。</span><span class="sxs-lookup"><span data-stu-id="4f98c-360">In the **Add Generated Items - AdapterHarnessProject** dialog box, click **Add Adapter Metadata**, and then click **Open**.</span></span>  
  
     <span data-ttu-id="4f98c-361">登録されたアダプターの一覧が表示されます。</span><span class="sxs-lookup"><span data-stu-id="4f98c-361">The list of registered adapters appears.</span></span>  
  
3.  <span data-ttu-id="4f98c-362">選択 **Static DotNetFile**, 、 をクリックし、 **次**します。</span><span class="sxs-lookup"><span data-stu-id="4f98c-362">Select **Static DotNetFile**, and then click **Next**.</span></span>  
  
     <span data-ttu-id="4f98c-363">アダプターで公開されるサービス構成が表示されます。</span><span class="sxs-lookup"><span data-stu-id="4f98c-363">The service organization exposed by the adapter appears.</span></span>  
  
4.  <span data-ttu-id="4f98c-364">展開 **サービスに関する組織**, 、**医療**, 、クリックして **管理**します。</span><span class="sxs-lookup"><span data-stu-id="4f98c-364">Expand **Service Organization**, **Health Care**, and then click **Administrative**.</span></span>  
  
     <span data-ttu-id="4f98c-365">注意して **適格性** は他のノードが異なる方法で表示されます。</span><span class="sxs-lookup"><span data-stu-id="4f98c-365">Notice that **Eligibility** displays differently from the other nodes.</span></span> <span data-ttu-id="4f98c-366">**対象となる** サービス ノードを選択できます。</span><span class="sxs-lookup"><span data-stu-id="4f98c-366">**Eligibility** is a service node that you can select.</span></span> <span data-ttu-id="4f98c-367">他のノードは構成ノードで、特定のサービスを表すものではありません。</span><span class="sxs-lookup"><span data-stu-id="4f98c-367">The other nodes are organization nodes that do not describe any specific service.</span></span>  
  
5.  <span data-ttu-id="4f98c-368">選択、 **適格性** ノードをクリックして **完了**します。</span><span class="sxs-lookup"><span data-stu-id="4f98c-368">Select the **Eligibility** node, and then click **Finish**.</span></span>  
  
     <span data-ttu-id="4f98c-369">BizTalk では .odx ファイルと .xsd ファイルがプロジェクトにインポートされます。</span><span class="sxs-lookup"><span data-stu-id="4f98c-369">BizTalk imports an .odx file and an .xsd file into the project.</span></span>  
  
     <span data-ttu-id="4f98c-370">これで、アダプターからインポートしたスキーマ、ポートの種類、操作、およびメッセージの種類を BizTalk プロジェクトのスケジュールで使用できます。</span><span class="sxs-lookup"><span data-stu-id="4f98c-370">You can now use the schemas, PortTypes, Operations, and MessageTypes imported from the adapter in the schedule for the BizTalk project.</span></span>  
  
## <a name="classes-or-methods-used-in-this-sample"></a><span data-ttu-id="4f98c-371">クラスまたはメソッドのこのサンプルで使用します。</span><span class="sxs-lookup"><span data-stu-id="4f98c-371">Classes or Methods used in this Sample</span></span>  
 <span data-ttu-id="4f98c-372">インターフェイス: IBaseMessage、IPropertyBag、IBTTransportProxy</span><span class="sxs-lookup"><span data-stu-id="4f98c-372">Interfaces: IBaseMessage, IPropertyBag, IBTTransportProxy</span></span>  
  
 <span data-ttu-id="4f98c-373">クラス (ベース アダプターから): AsyncTransmitterEndpoint、AsyncTransmitter、BatchMessage、ControlledTermination、ReceiverEndpoint、DotNetFileCommonProperties、BatchOperationType</span><span class="sxs-lookup"><span data-stu-id="4f98c-373">Classes (from Base Adapter): AsyncTransmitterEndpoint, AsyncTransmitter, BatchMessage, ControlledTermination, ReceiverEndpoint, DotNetFileCommonProperties, BatchOperationType</span></span>  
  
### <a name="comments"></a><span data-ttu-id="4f98c-374">コメント</span><span class="sxs-lookup"><span data-stu-id="4f98c-374">Comments</span></span>  
 <span data-ttu-id="4f98c-375">サンプル アダプターを完了すると、詳細については、カスタムの静的または動的アダプターを作成するを参照してくださいサンプル アダプターを変更できます[アダプター デザイン時構成](../core/adapter-design-time-configuration.md)です。</span><span class="sxs-lookup"><span data-stu-id="4f98c-375">After completing the sample adapter, you can modify the sample adapter to create a custom static or dynamic adapter For more information, see [Adapter Design-Time Configuration](../core/adapter-design-time-configuration.md).</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="4f98c-376">参照</span><span class="sxs-lookup"><span data-stu-id="4f98c-376">See Also</span></span>  
 <span data-ttu-id="4f98c-377">[アダプタ サンプル – 使用状況](../core/adapter-samples-usage.md) </span><span class="sxs-lookup"><span data-stu-id="4f98c-377">[Adapter Samples - Usage](../core/adapter-samples-usage.md) </span></span>  
 [<span data-ttu-id="4f98c-378">アダプターの登録</span><span class="sxs-lookup"><span data-stu-id="4f98c-378">Registering an Adapter</span></span>](../core/registering-an-adapter.md)