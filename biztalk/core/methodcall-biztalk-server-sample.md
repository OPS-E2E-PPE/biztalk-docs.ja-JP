---
title: MethodCall (BizTalk Server サンプル) |Microsoft Docs
ms.custom: ''
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: ''
ms.suite: ''
ms.tgt_pltfrm: ''
ms.topic: article
helpviewer_keywords:
- orchestrations, calling
- examples, orchestrations
- orchestrations, methods
ms.assetid: 6bdc72da-9478-403a-b706-3089b7374ac7
caps.latest.revision: 20
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: 0ef3869161c699c48648bc0c22f1d9f40c9bde73
ms.sourcegitcommit: 266308ec5c6a9d8d80ff298ee6051b4843c5d626
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 06/27/2018
ms.locfileid: "36986875"
---
# <a name="methodcall-biztalk-server-sample"></a><span data-ttu-id="cfa67-102">MethodCall (BizTalk Server サンプル)</span><span class="sxs-lookup"><span data-stu-id="cfa67-102">MethodCall (BizTalk Server Sample)</span></span>
<span data-ttu-id="cfa67-103">MethodCall サンプルは、BizTalk Server オーケストレーションから .NET ベースのメソッドを呼び出す方法を示すものです。</span><span class="sxs-lookup"><span data-stu-id="cfa67-103">The MethodCall sample demonstrates how to call a .NET-based method from a BizTalk Server orchestration.</span></span>  

## <a name="what-this-sample-does"></a><span data-ttu-id="cfa67-104">このサンプルの処理</span><span class="sxs-lookup"><span data-stu-id="cfa67-104">What This Sample Does</span></span>  
 <span data-ttu-id="cfa67-105">このサンプルでは、次の一連の手順を実行して .NET ベースのメソッドと連携します。</span><span class="sxs-lookup"><span data-stu-id="cfa67-105">This sample interacts with a .NET-based method using the following sequence of steps:</span></span>  

1. <span data-ttu-id="cfa67-106">[!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)] オーケストレーションで、In フォルダーから XML 入力ファイルを取得します。</span><span class="sxs-lookup"><span data-stu-id="cfa67-106">The [!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)] orchestration retrieves an XML input file from the In folder.</span></span> <span data-ttu-id="cfa67-107">このファイルには、数値演算ライブラリで実行する加算または減算に関する情報が含まれています。</span><span class="sxs-lookup"><span data-stu-id="cfa67-107">This file contains information about an addition or subtraction you want the math library to perform.</span></span>  

2. <span data-ttu-id="cfa67-108">オーケストレーションで、インクルードされた数値演算ライブラリを呼び出し、XML 入力ファイルに指定されている加算または減算を実行します。</span><span class="sxs-lookup"><span data-stu-id="cfa67-108">The orchestration calls the included math library to perform the addition or subtraction specified in the XML input file.</span></span>  

3. <span data-ttu-id="cfa67-109">数値演算ライブラリのメソッドを適切な**追加**または**減算**要求された計算を行い、結果を XML ドキュメントとしてパッケージ化します。</span><span class="sxs-lookup"><span data-stu-id="cfa67-109">The appropriate math library method, either **Add** or **Subtract**, performs the requested calculation and packages the result as an XML document.</span></span>  

4. <span data-ttu-id="cfa67-110">オーケストレーションで、生成された .xml ファイルを Out フォルダに格納します。</span><span class="sxs-lookup"><span data-stu-id="cfa67-110">The orchestration places the resulting .xml file in the Out folder.</span></span>  

## <a name="how-this-sample-is-designed-and-why"></a><span data-ttu-id="cfa67-111">このサンプルのデザイン方法とその理由</span><span class="sxs-lookup"><span data-stu-id="cfa67-111">How This Sample is Designed and Why</span></span>  
 <span data-ttu-id="cfa67-112">このサンプルは、次の機能を実行します。</span><span class="sxs-lookup"><span data-stu-id="cfa67-112">This sample demonstrates the following functionalities:</span></span>  

-   <span data-ttu-id="cfa67-113">昇格させたプロパティをオーケストレーション内で使用します。</span><span class="sxs-lookup"><span data-stu-id="cfa67-113">Leveraging the promoted properties in an orchestration.</span></span> <span data-ttu-id="cfa67-114">InputSchema.xsd の 3 つの要素は、識別フィールドとして昇格されています。</span><span class="sxs-lookup"><span data-stu-id="cfa67-114">The three elements in InputSchema.xsd are promoted as distinguished fields.</span></span> <span data-ttu-id="cfa67-115">オーケストレーションでは、入力メッセージの受信時にこれら 3 つのフィールドの値を取得し、オーケストレーション内で対応する宣言済みの変数に割り当てます。</span><span class="sxs-lookup"><span data-stu-id="cfa67-115">When the orchestration receives the input message, it gets the values of these three fields and assigns them to the corresponding variables declared in the orchestration.</span></span>  

-   <span data-ttu-id="cfa67-116">使用して、**判断**図形をオーケストレーションに"if then else"ロジックを表現します。</span><span class="sxs-lookup"><span data-stu-id="cfa67-116">Using the **Decide** shape to express "if-then-else" logic in an orchestration.</span></span> <span data-ttu-id="cfa67-117">入力した後、オーケストレーションは、識別フィールドの値を内部変数に割り当てる、**判断**図形を加算または減算を実行するかどうかを確認します。</span><span class="sxs-lookup"><span data-stu-id="cfa67-117">After the orchestration assigns the values of distinguished fields to internal variables, it enters the **Decide** shape to check whether an addition or subtraction should be performed.</span></span> <span data-ttu-id="cfa67-118">演算を実行する必要がない場合、オーケストレーションは終了します。</span><span class="sxs-lookup"><span data-stu-id="cfa67-118">If no operation needs to be performed, the orchestration terminates.</span></span>  

-   <span data-ttu-id="cfa67-119">オーケストレーションから外部アセンブリを呼び出します。</span><span class="sxs-lookup"><span data-stu-id="cfa67-119">Calling an external assembly from an orchestration.</span></span> <span data-ttu-id="cfa67-120">加算を実行する場合、オーケストレーションでは外部 C# アセンブリを呼び出し、2 つのパラメータを渡して加算を実行します。</span><span class="sxs-lookup"><span data-stu-id="cfa67-120">If an addition is to be performed, the orchestration calls an external C# assembly and passes in two parameters to perform the addition.</span></span> <span data-ttu-id="cfa67-121">減算も同様の手順です。</span><span class="sxs-lookup"><span data-stu-id="cfa67-121">The same procedures apply to a subtraction.</span></span>  

    > [!NOTE]
    >  <span data-ttu-id="cfa67-122">アセンブリをオーケストレーションから呼び出すには、アセンブリをグローバル アセンブリ キャッシュにインストールしておく必要があります。グローバル アセンブリ キャッシュにアセンブリがない場合、実行時に XLANG エラーが返されます。</span><span class="sxs-lookup"><span data-stu-id="cfa67-122">You need to install the assembly to the global assembly cache before you can call it from the orchestration; otherwise you will receive an XLANG error during run time.</span></span>  

-   <span data-ttu-id="cfa67-123">使用して、**メッセージの割り当て**図形を出力メッセージを構築します。</span><span class="sxs-lookup"><span data-stu-id="cfa67-123">Using the **Message Assignment** shape to construct the output message.</span></span>  

-   <span data-ttu-id="cfa67-124">次のコードを式図形に配置することにより、オーケストレーションをデバッグします。</span><span class="sxs-lookup"><span data-stu-id="cfa67-124">Debugging the orchestration by putting the following code in the Expression shape:</span></span>  

    ```  
    System.Diagnostics.Debug.WriteLine(iResult);  
    ```  

     <span data-ttu-id="cfa67-125">次のコードを使用して、結果をイベント ログに書き込むこともできます。</span><span class="sxs-lookup"><span data-stu-id="cfa67-125">You can also write the result to the event log by using:</span></span>  

    ```  
    System.Diagnostics.EventLog.WriteEntry("MethodCall SDK Sample Debug", System.String.Format("Result = {0}", iResult);  
    ```  

## <a name="where-to-find-this-sample"></a><span data-ttu-id="cfa67-126">このサンプルの場所</span><span class="sxs-lookup"><span data-stu-id="cfa67-126">Where to Find This Sample</span></span>  
 <span data-ttu-id="cfa67-127">\<*パスのサンプル*\>\Orchestrations\MethodCall\\</span><span class="sxs-lookup"><span data-stu-id="cfa67-127">\<*Samples Path*\>\Orchestrations\MethodCall\\</span></span>  

 <span data-ttu-id="cfa67-128">次の表は、このサンプルのファイルとその目的を示しています。</span><span class="sxs-lookup"><span data-stu-id="cfa67-128">The following table shows the files in this sample and describes their purpose.</span></span>  


|                                          <span data-ttu-id="cfa67-129">ファイル</span><span class="sxs-lookup"><span data-stu-id="cfa67-129">File(s)</span></span>                                           |                                                                                           <span data-ttu-id="cfa67-130">説明</span><span class="sxs-lookup"><span data-stu-id="cfa67-130">Description</span></span>                                                                                            |
|--------------------------------------------------------------------------------------------|--------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------|
|                                        <span data-ttu-id="cfa67-131">Cleanup.bat</span><span class="sxs-lookup"><span data-stu-id="cfa67-131">Cleanup.bat</span></span>                                         | <span data-ttu-id="cfa67-132">アセンブリの展開を解除し、グローバル アセンブリ キャッシュからアセンブリを削除するために使用されます。</span><span class="sxs-lookup"><span data-stu-id="cfa67-132">Used to undeploy assemblies and remove them from the global assembly cache.</span></span> <span data-ttu-id="cfa67-133">送信ポートと受信ポートが削除されます。</span><span class="sxs-lookup"><span data-stu-id="cfa67-133">Removes send and receive ports.</span></span> <span data-ttu-id="cfa67-134">必要に応じて、Microsoft インターネット インフォメーション サービス (IIS) の仮想ディレクトリが削除されます。</span><span class="sxs-lookup"><span data-stu-id="cfa67-134">Removes Microsoft Internet Information Services (IIS) virtual directories as needed.</span></span> |
|                                         <span data-ttu-id="cfa67-135">Input.xml</span><span class="sxs-lookup"><span data-stu-id="cfa67-135">Input.xml</span></span>                                          |                                                                                        <span data-ttu-id="cfa67-136">サンプル入力ファイルです。</span><span class="sxs-lookup"><span data-stu-id="cfa67-136">Sample input file.</span></span>                                                                                        |
|                                         <span data-ttu-id="cfa67-137">Setup.bat</span><span class="sxs-lookup"><span data-stu-id="cfa67-137">Setup.bat</span></span>                                          |                                                                            <span data-ttu-id="cfa67-138">このサンプルをビルドおよび初期化するために使用されます。</span><span class="sxs-lookup"><span data-stu-id="cfa67-138">Used to build and initialize this sample.</span></span>                                                                             |
| <span data-ttu-id="cfa67-139">\MathLibrary フォルダには、次のファイルが含まれます。</span><span class="sxs-lookup"><span data-stu-id="cfa67-139">In the \MathLibrary folder:</span></span><br /><br /> <span data-ttu-id="cfa67-140">AssemblyInfo.cs、MathHelper.cs、MathLibrary.csproj</span><span class="sxs-lookup"><span data-stu-id="cfa67-140">AssemblyInfo.cs, MathHelper.cs, MathLibrary.csproj</span></span> |                                                                <span data-ttu-id="cfa67-141">このサンプルで使用する数値演算ライブラリのプロジェクト ファイルとソース ファイルです。</span><span class="sxs-lookup"><span data-stu-id="cfa67-141">Project and source files for the math library used by this sample.</span></span>                                                                |
|       <span data-ttu-id="cfa67-142">\MethodCallSample フォルダには、次のファイルが含まれます。</span><span class="sxs-lookup"><span data-stu-id="cfa67-142">In the \MethodCallSample folder:</span></span><br /><br /> <span data-ttu-id="cfa67-143">InputSchema.xsd、OutputSchema.xsd</span><span class="sxs-lookup"><span data-stu-id="cfa67-143">InputSchema.xsd, OutputSchema.xsd</span></span>       |                                                                    <span data-ttu-id="cfa67-144">それぞれ、入力 .xml ファイルと出力 .xml ファイルのスキーマです。</span><span class="sxs-lookup"><span data-stu-id="cfa67-144">Schemas for the input and output .xml files, respectively.</span></span>                                                                    |
| <span data-ttu-id="cfa67-145">\MethodCallSample フォルダには、次のファイルが含まれます。</span><span class="sxs-lookup"><span data-stu-id="cfa67-145">In the \MethodCallSample folder:</span></span><br /><br /> <span data-ttu-id="cfa67-146">MethodCallSample.btproj、MethodCallSample.sln</span><span class="sxs-lookup"><span data-stu-id="cfa67-146">MethodCallSample.btproj, MethodCallSample.sln</span></span> |                                                                           <span data-ttu-id="cfa67-147">このサンプルのプロジェクト ファイルとソリューション ファイルです。</span><span class="sxs-lookup"><span data-stu-id="cfa67-147">Project and solution files for this sample.</span></span>                                                                            |
|          <span data-ttu-id="cfa67-148">\MethodCallSample フォルダには、次のファイルが含まれます。</span><span class="sxs-lookup"><span data-stu-id="cfa67-148">In the \MethodCallSample folder:</span></span><br /><br /> <span data-ttu-id="cfa67-149">MethodCallSampleBinding.xml</span><span class="sxs-lookup"><span data-stu-id="cfa67-149">MethodCallSampleBinding.xml</span></span>          |                                                                          <span data-ttu-id="cfa67-150">ポートのバインドなど、自動化されたセットアップに使用されます。</span><span class="sxs-lookup"><span data-stu-id="cfa67-150">Used for automated setup such as port binding.</span></span>                                                                          |
|             <span data-ttu-id="cfa67-151">\MethodCallSample フォルダには、次のファイルが含まれます。</span><span class="sxs-lookup"><span data-stu-id="cfa67-151">In the \MethodCallSample folder:</span></span><br /><br /> <span data-ttu-id="cfa67-152">MethodCallService.odx</span><span class="sxs-lookup"><span data-stu-id="cfa67-152">MethodCallService.odx</span></span>             |                <span data-ttu-id="cfa67-153">数値演算ライブラリを呼び出し、要求された計算を実行する [!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)] オーケストレーションです。</span><span class="sxs-lookup"><span data-stu-id="cfa67-153">[!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)] orchestration that calls the math library to perform the requested calculation.</span></span>                |

## <a name="building-and-initializing-this-sample"></a><span data-ttu-id="cfa67-154">このサンプルのビルドと初期化</span><span class="sxs-lookup"><span data-stu-id="cfa67-154">Building and Initializing This Sample</span></span>  

#### <a name="to-build-and-initialize-the-methodcall-sample"></a><span data-ttu-id="cfa67-155">MethodCall サンプルをビルドおよび初期化するには</span><span class="sxs-lookup"><span data-stu-id="cfa67-155">To build and initialize the MethodCall sample</span></span>  

1. <span data-ttu-id="cfa67-156">コマンド ウィンドウで、次のフォルダーに移動します。</span><span class="sxs-lookup"><span data-stu-id="cfa67-156">In a command window, navigate to the following folder:</span></span>  

    <span data-ttu-id="cfa67-157">\<*パスのサンプル*\>\Orchestrations\MethodCall</span><span class="sxs-lookup"><span data-stu-id="cfa67-157">\<*Samples Path*\>\Orchestrations\MethodCall</span></span>  

2. <span data-ttu-id="cfa67-158">ファイルは、次の操作を実行します。 Setup.bat を実行します。</span><span class="sxs-lookup"><span data-stu-id="cfa67-158">Run the file Setup.bat, which performs the following actions:</span></span>  

   - <span data-ttu-id="cfa67-159">MethodCall フォルダに、このサンプルの入力 (In) フォルダと出力 (Out) フォルダを作成します。</span><span class="sxs-lookup"><span data-stu-id="cfa67-159">Creates the input (In) and output (Out) folders for this sample in the MethodCall folder.</span></span>  

   - <span data-ttu-id="cfa67-160">このサンプル用に [!INCLUDE[btsVStudioNoVersion](../includes/btsvstudionoversion-md.md)] プロジェクトをコンパイルし、生成されたアセンブリを展開します。</span><span class="sxs-lookup"><span data-stu-id="cfa67-160">Compiles the [!INCLUDE[btsVStudioNoVersion](../includes/btsvstudionoversion-md.md)] projects for this sample, and deploys the resulting assemblies.</span></span>  

   - <span data-ttu-id="cfa67-161">[!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)] 受信場所と、オーケストレーションの送信ポートおよび受信ポートを作成しバインドします。</span><span class="sxs-lookup"><span data-stu-id="cfa67-161">Creates and binds the [!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)] receive location, and the send and receive ports to the orchestration.</span></span>  

   - <span data-ttu-id="cfa67-162">受信場所を有効にし、送信ポートを開始します。</span><span class="sxs-lookup"><span data-stu-id="cfa67-162">Enables the receive location, and starts the send port.</span></span> <span data-ttu-id="cfa67-163">オーケストレーションを参加させ、開始します。</span><span class="sxs-lookup"><span data-stu-id="cfa67-163">Enlists and starts orchestration.</span></span>  

> [!NOTE]
>  <span data-ttu-id="cfa67-164">このサンプルを実行する前に、ビルドと初期化のプロセス中に [!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)] でエラーが報告されていないことを確認する必要があります。</span><span class="sxs-lookup"><span data-stu-id="cfa67-164">You should confirm that [!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)] did not report any errors during the build and initialization process before attempting to run this sample.</span></span>  

## <a name="running-this-sample"></a><span data-ttu-id="cfa67-165">このサンプルの実行</span><span class="sxs-lookup"><span data-stu-id="cfa67-165">Running This Sample</span></span>  

#### <a name="to-run-the-methodcall-sample"></a><span data-ttu-id="cfa67-166">MethodCall サンプルを実行するには</span><span class="sxs-lookup"><span data-stu-id="cfa67-166">To run the MethodCall sample</span></span>  

1.  <span data-ttu-id="cfa67-167">ファイル Input.xml を In フォルダにコピーします。</span><span class="sxs-lookup"><span data-stu-id="cfa67-167">Paste a copy of the file Input.xml into the In folder.</span></span>  

2.  <span data-ttu-id="cfa67-168">.xml ファイルが Out フォルダに作成されることを確認します。</span><span class="sxs-lookup"><span data-stu-id="cfa67-168">Observe the .xml file created in the Out folder.</span></span> <span data-ttu-id="cfa67-169">このファイルには、要求された加算または減算の計算結果が含まれています。</span><span class="sxs-lookup"><span data-stu-id="cfa67-169">This file contains the result of the requested addition or subtraction calculation.</span></span> <span data-ttu-id="cfa67-170">このファイルの名前の形式が\< *MessageID*\>、.xml、 *\<MessageID\>* メッセージを一意に識別するために生成される GUID.</span><span class="sxs-lookup"><span data-stu-id="cfa67-170">The format of the name of this file is \<*MessageID*\>.xml, where *\<MessageID\>* is the GUID generated to uniquely identify the message.</span></span>  

3.  <span data-ttu-id="cfa67-171">入力ファイルを変更し、別の加算または減算を要求することもできます。</span><span class="sxs-lookup"><span data-stu-id="cfa67-171">You can modify the input file to request different addition or subtraction calculations.</span></span>  

## <a name="uninstalling-this-sample"></a><span data-ttu-id="cfa67-172">このサンプルのアンインストール</span><span class="sxs-lookup"><span data-stu-id="cfa67-172">Uninstalling This Sample</span></span>  

#### <a name="to-uninstall-the-methodcall-sample"></a><span data-ttu-id="cfa67-173">MethodCall サンプルをアンインストールするには</span><span class="sxs-lookup"><span data-stu-id="cfa67-173">To uninstall the MethodCall sample</span></span>  

1. <span data-ttu-id="cfa67-174">[!INCLUDE[btsVStudioNoVersion](../includes/btsvstudionoversion-md.md)]コマンド プロンプトでディレクトリ変更コマンド (**cd**) に\<*サンプル パス*\>\Orchestrations\MethodCall\\します。</span><span class="sxs-lookup"><span data-stu-id="cfa67-174">At a [!INCLUDE[btsVStudioNoVersion](../includes/btsvstudionoversion-md.md)] command prompt, change directory (**cd**) to \<*Samples Path*\>\Orchestrations\MethodCall\\.</span></span>  

2. <span data-ttu-id="cfa67-175">Cleanup.bat を実行します。</span><span class="sxs-lookup"><span data-stu-id="cfa67-175">Run Cleanup.bat.</span></span>  

## <a name="see-also"></a><span data-ttu-id="cfa67-176">参照</span><span class="sxs-lookup"><span data-stu-id="cfa67-176">See Also</span></span>  
 [<span data-ttu-id="cfa67-177">オーケストレーション (BizTalk Server サンプル フォルダー)</span><span class="sxs-lookup"><span data-stu-id="cfa67-177">Orchestrations (BizTalk Server Samples Folder)</span></span>](../core/orchestrations-biztalk-server-samples-folder.md)