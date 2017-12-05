---
title: "Business Rules こんにちは World1 (BizTalk Server サンプル) |Microsoft ドキュメント"
ms.custom: 
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: 
ms.suite: 
ms.tgt_pltfrm: 
ms.topic: article
helpviewer_keywords:
- examples, business rules
- business rules, examples
ms.assetid: 0623ad20-96cc-430e-bb36-35431a5d17ee
caps.latest.revision: "16"
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: ebe9f04fc8dac06676d7f29bf5dd2ecd01e7a06c
ms.sourcegitcommit: 5abd0ed3f9e4858ffaaec5481bfa8878595e95f7
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 11/28/2017
---
# <a name="business-rules-hello-world1-biztalk-server-sample"></a><span data-ttu-id="1b4f2-102">Business Rules こんにちは World1 (BizTalk Server サンプル)</span><span class="sxs-lookup"><span data-stu-id="1b4f2-102">Business Rules Hello World1 (BizTalk Server Sample)</span></span>
<span data-ttu-id="1b4f2-103">Business Rules Hello World1 サンプルでは、BizTalk ルール セットを作成して、そのルール セットをファイル (SampleRuleSet.xml) に保存し、読み込んでから、サンプルのファクト セットに基づいて実行する方法を示します。</span><span class="sxs-lookup"><span data-stu-id="1b4f2-103">The Business Rules Hello World1 sample demonstrates how to create a BizTalk rule set, save it to a file (SampleRuleSet.xml), load it, and run it based on a sample set of facts.</span></span> <span data-ttu-id="1b4f2-104">サンプルのルール セットには、ルール定義の条件として XML 要素を含む単一のルール、および .NET ベースのオブジェクト (プロパティとメンバ) が含まれます。</span><span class="sxs-lookup"><span data-stu-id="1b4f2-104">The sample rule set contains a simple rule that involves an XML element, and .NET-based objects (properties and members) as terms in rule definition.</span></span>  
  
## <a name="what-this-sample-does"></a><span data-ttu-id="1b4f2-105">このサンプルの処理</span><span class="sxs-lookup"><span data-stu-id="1b4f2-105">What This Sample Does</span></span>  
 <span data-ttu-id="1b4f2-106">このサンプルでは、次の一連の手順を実行する実行可能ファイルを作成します。</span><span class="sxs-lookup"><span data-stu-id="1b4f2-106">This sample creates an executable that performs the following sequence of steps:</span></span>  
  
1.  <span data-ttu-id="1b4f2-107">メソッドを呼び出して**CreateRuleset**ルール「解説」セクションで説明されているセットを作成します。</span><span class="sxs-lookup"><span data-stu-id="1b4f2-107">Calls the method **CreateRuleset** to build the rule set described in the Remarks section.</span></span>  
  
2.  <span data-ttu-id="1b4f2-108">メソッドを呼び出して**SaveToFile**ファイルへのルール セットの保存を示すためにします。</span><span class="sxs-lookup"><span data-stu-id="1b4f2-108">Calls the method **SaveToFile** to demonstrate saving a rule set to a file.</span></span>  
  
3.  <span data-ttu-id="1b4f2-109">メソッドを呼び出して**LoadFromFile**ファイルからルール セットの読み込みを示すためにします。</span><span class="sxs-lookup"><span data-stu-id="1b4f2-109">Calls the method **LoadFromFile** to demonstrate loading a rule set from a file.</span></span>  
  
4.  <span data-ttu-id="1b4f2-110">ルール セットの実行対象のサンプル ファクトを作成します。</span><span class="sxs-lookup"><span data-stu-id="1b4f2-110">Constructs sample facts against which to run the rule set.</span></span>  
  
5.  <span data-ttu-id="1b4f2-111">サンプル ファクトに対してルール セットを実行し、画面出力を作成します。</span><span class="sxs-lookup"><span data-stu-id="1b4f2-111">Runs the rule set against the sample facts, producing screen output.</span></span>  
  
6.  <span data-ttu-id="1b4f2-112">一時停止し、ルール セット ファイル SampleRuleStore.xml を確認できるようにします。</span><span class="sxs-lookup"><span data-stu-id="1b4f2-112">Pauses, enabling you to examine the rule set file SampleRuleStore.xml.</span></span>  
  
7.  <span data-ttu-id="1b4f2-113">後でこのサンプルを実行するための準備として、ルール セット ファイルを削除して、クリーンアップします。</span><span class="sxs-lookup"><span data-stu-id="1b4f2-113">Cleans up by deleting the rule set file in preparation for subsequent runs of the sample.</span></span>  
  
## <a name="where-to-find-this-sample"></a><span data-ttu-id="1b4f2-114">このサンプルの場所</span><span class="sxs-lookup"><span data-stu-id="1b4f2-114">Where to Find This Sample</span></span>  
 <span data-ttu-id="1b4f2-115">\<*パスのサンプル*\>\Business Rules\Business こんにちは World1\ のルール</span><span class="sxs-lookup"><span data-stu-id="1b4f2-115">\<*Samples Path*\>\Business Rules\Business Rules Hello World1\\</span></span>  
  
 <span data-ttu-id="1b4f2-116">次の表は、このサンプルのファイルとその目的を示しています。</span><span class="sxs-lookup"><span data-stu-id="1b4f2-116">The following table shows the files in this sample and describes their purpose.</span></span>  
  
|<span data-ttu-id="1b4f2-117">ファイル</span><span class="sxs-lookup"><span data-stu-id="1b4f2-117">File(s)</span></span>|<span data-ttu-id="1b4f2-118">Description</span><span class="sxs-lookup"><span data-stu-id="1b4f2-118">Description</span></span>|  
|---------------|-----------------|  
|<span data-ttu-id="1b4f2-119">App.ico、AssemblyInfo.cs、BusinessRulesHelloWorld1.csproj、および BusinessRulesHelloWorld1.sln</span><span class="sxs-lookup"><span data-stu-id="1b4f2-119">App.ico, AssemblyInfo.cs, BusinessRulesHelloWorld1.csproj, BusinessRulesHelloWorld1.sln</span></span>|<span data-ttu-id="1b4f2-120">このサンプルで、ルール セットの作成、保存、読み込み、実行を行う部分で使用するプロジェクト ファイル、ソリューション ファイル、その他の関連ファイルです。</span><span class="sxs-lookup"><span data-stu-id="1b4f2-120">Project, solution, and related files for the portion of this sample that creates, saves, loads, and runs a rule set.</span></span>|  
|<span data-ttu-id="1b4f2-121">HelloWorld1.cs</span><span class="sxs-lookup"><span data-stu-id="1b4f2-121">HelloWorld1.cs</span></span>|<span data-ttu-id="1b4f2-122">ルール セットの作成、ファイルへのルール セットの保存、およびファイルからルール セットを読み込む方法を示すメソッドを含む Visual C# ファイルです。</span><span class="sxs-lookup"><span data-stu-id="1b4f2-122">Visual C# file that contains methods to demonstrate creating a rule set, saving a rule set to a file, and loading a rule set from a file.</span></span> <span data-ttu-id="1b4f2-123">これらのメソッドを呼び出し、作成したルール セットを実行する、前後のコードも含まれます。</span><span class="sxs-lookup"><span data-stu-id="1b4f2-123">Also contains surrounding code that calls these methods and then runs the created rule set.</span></span>|  
|<span data-ttu-id="1b4f2-124">Cleanup.bat</span><span class="sxs-lookup"><span data-stu-id="1b4f2-124">Cleanup.bat</span></span>|<span data-ttu-id="1b4f2-125">アセンブリを展開解除し、グローバル アセンブリ キャッシュ (GAC) から削除するために使用されます。</span><span class="sxs-lookup"><span data-stu-id="1b4f2-125">Used to undeploy assemblies and remove them from the global assembly cache (GAC).</span></span> <span data-ttu-id="1b4f2-126">送信ポートと受信ポートが削除されます。</span><span class="sxs-lookup"><span data-stu-id="1b4f2-126">Removes send and receive ports.</span></span> <span data-ttu-id="1b4f2-127">必要に応じて、Microsoft インターネット インフォメーション サービス (IIS) の仮想ディレクトリが削除されます。</span><span class="sxs-lookup"><span data-stu-id="1b4f2-127">Removes Microsoft Internet Information Services (IIS) virtual directories as needed.</span></span>|  
|<span data-ttu-id="1b4f2-128">SampleDocumentInstance.xml</span><span class="sxs-lookup"><span data-stu-id="1b4f2-128">SampleDocumentInstance.xml</span></span>|<span data-ttu-id="1b4f2-129">ファイル SampleSchema.xsd で定義されているスキーマに準拠したサンプル入力ファイルです。</span><span class="sxs-lookup"><span data-stu-id="1b4f2-129">Sample input file that conforms to the schema defined in the file SampleSchema.xsd.</span></span>|  
|<span data-ttu-id="1b4f2-130">SampleSchema.xsd</span><span class="sxs-lookup"><span data-stu-id="1b4f2-130">SampleSchema.xsd</span></span>|<span data-ttu-id="1b4f2-131">簡潔なスキーマを定義したスキーマ ファイルで、Visual C# ファイル HelloWorld1.cs で作成されたルール セットから参照される要素が含まれます。</span><span class="sxs-lookup"><span data-stu-id="1b4f2-131">Schema file that defines a simple schema with an element referenced by the rule set created in the Visual C# file HelloWorld1.cs.</span></span>|  
|<span data-ttu-id="1b4f2-132">Setup.bat</span><span class="sxs-lookup"><span data-stu-id="1b4f2-132">Setup.bat</span></span>|<span data-ttu-id="1b4f2-133">このサンプルをビルドおよび初期化するために使用されます。</span><span class="sxs-lookup"><span data-stu-id="1b4f2-133">Used to build and initialize this sample.</span></span>|  
|<span data-ttu-id="1b4f2-134">\MySampleLibrary フォルダーに含まれるファイル: </span><span class="sxs-lookup"><span data-stu-id="1b4f2-134">In the \MySampleLibrary folder:</span></span><br /><br /> <span data-ttu-id="1b4f2-135">AssemblyInfo.cs、MySampleLibrary.csproj、および MySampleLibrary.sln</span><span class="sxs-lookup"><span data-stu-id="1b4f2-135">AssemblyInfo.cs, MySampleLibrary.csproj, MySampleLibrary.sln</span></span>|<span data-ttu-id="1b4f2-136">このサンプルで、作成したルール セットから参照されるオブジェクトを定義するクラスを提供する部分で使用するプロジェクト ファイル、ソリューション ファイル、その他の関連ファイルです。</span><span class="sxs-lookup"><span data-stu-id="1b4f2-136">Project, solution, and related files for the portion of this sample that provides the class that defines the objects referenced by the created rule set.</span></span>|  
|<span data-ttu-id="1b4f2-137">\MySampleLibrary フォルダーに含まれるファイル: </span><span class="sxs-lookup"><span data-stu-id="1b4f2-137">In the \MySampleLibrary folder:</span></span><br /><br /> <span data-ttu-id="1b4f2-138">MySampleLibraryClass.cs</span><span class="sxs-lookup"><span data-stu-id="1b4f2-138">MySampleLibraryClass.cs</span></span>|<span data-ttu-id="1b4f2-139">参照されているプロパティを含む visual c# ファイル、 **IF** 、作成した規則で呼び出されるメソッドの部分、**し**作成したルールの一部です。</span><span class="sxs-lookup"><span data-stu-id="1b4f2-139">Visual C# file that contains the property referenced in the **IF** portion of the created rule, and the method that may be called in the **THEN** portion of the created rule.</span></span>|  
  
## <a name="building-and-initializing-this-sample"></a><span data-ttu-id="1b4f2-140">このサンプルのビルドと初期化</span><span class="sxs-lookup"><span data-stu-id="1b4f2-140">Building and Initializing This Sample</span></span>  
 <span data-ttu-id="1b4f2-141">次の手順を使用して、Business Rules Hello World1 サンプルの作成および初期化を行います。</span><span class="sxs-lookup"><span data-stu-id="1b4f2-141">Use the following procedure to build and initialize the Business Rules Hello World1 sample.</span></span>  
  
#### <a name="to-build-and-initialize-this-sample"></a><span data-ttu-id="1b4f2-142">このサンプルを作成および初期化するには</span><span class="sxs-lookup"><span data-stu-id="1b4f2-142">To build and initialize this sample</span></span>  
  
1.  <span data-ttu-id="1b4f2-143">コマンド ウィンドウで、次のフォルダーに移動します。</span><span class="sxs-lookup"><span data-stu-id="1b4f2-143">In a command window, navigate to the following folder:</span></span>  
  
     <span data-ttu-id="1b4f2-144">\<*パスのサンプル*\>\Business Rules\Business こんにちは World1\ のルール</span><span class="sxs-lookup"><span data-stu-id="1b4f2-144">\<*Samples Path*\>\Business Rules\Business Rules Hello World1\\</span></span>  
  
2.  <span data-ttu-id="1b4f2-145">次の操作を実行する Setup.bat ファイルを実行します。</span><span class="sxs-lookup"><span data-stu-id="1b4f2-145">Run the file Setup.bat, which performs the following actions:</span></span>  
  
    -   <span data-ttu-id="1b4f2-146">コンパイルし、展開、Microsoft[!INCLUDE[btsVStudioNoVersion](../includes/btsvstudionoversion-md.md)]このサンプルのプロジェクトです。</span><span class="sxs-lookup"><span data-stu-id="1b4f2-146">Compiles and deploys the Microsoft [!INCLUDE[btsVStudioNoVersion](../includes/btsvstudionoversion-md.md)] projects for this sample.</span></span>  
  
    > [!NOTE]
    >  <span data-ttu-id="1b4f2-147">このサンプルを実行する前に、ビルドと初期化のプロセス中に [!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)] でエラーが報告されていないことを確認する必要があります。</span><span class="sxs-lookup"><span data-stu-id="1b4f2-147">You should confirm that [!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)] did not report any errors during the build and initialization process before attempting to run this sample.</span></span>  
  
    > [!NOTE]
    >  <span data-ttu-id="1b4f2-148">開き、Setup.bat ファイルを実行せずにこのサンプルのプロジェクトをビルドする場合は、まず、.NET Framework の厳密名ユーティリティ (sn.exe) を使用して、厳密な名前のキー ペアを作成する必要があります。</span><span class="sxs-lookup"><span data-stu-id="1b4f2-148">If you choose to open and build the projects in this sample without running the file Setup.bat, you must first create a strong name key pair using the .NET Framework Strong Name utility (sn.exe).</span></span> <span data-ttu-id="1b4f2-149">このキー ペアは、生成されたアセンブリの署名に使用します。</span><span class="sxs-lookup"><span data-stu-id="1b4f2-149">Use this key pair to sign the resulting assemblies.</span></span>  
  
    > [!NOTE]
    >  <span data-ttu-id="1b4f2-150">Setup.bat によって行われた変更を元に戻すには、Cleanup.bat を実行します。</span><span class="sxs-lookup"><span data-stu-id="1b4f2-150">To undo changes made by Setup.bat, run Cleanup.bat.</span></span> <span data-ttu-id="1b4f2-151">Setup.bat を 2 回目に実行する場合は、その前に Cleanup.bat を実行してください。</span><span class="sxs-lookup"><span data-stu-id="1b4f2-151">You must run Cleanup.bat before running Setup.bat a second time.</span></span>  
  
## <a name="running-this-sample"></a><span data-ttu-id="1b4f2-152">このサンプルの実行</span><span class="sxs-lookup"><span data-stu-id="1b4f2-152">Running This Sample</span></span>  
 <span data-ttu-id="1b4f2-153">次の手順を使用して、Business Rules Hello World1 サンプルを実行します。</span><span class="sxs-lookup"><span data-stu-id="1b4f2-153">Use the following procedure to run the Business Rules Hello World1 sample.</span></span>  
  
#### <a name="to-run-this-sample"></a><span data-ttu-id="1b4f2-154">このサンプルを実行するには</span><span class="sxs-lookup"><span data-stu-id="1b4f2-154">To run this sample</span></span>  
  
1.  <span data-ttu-id="1b4f2-155">コマンド ウィンドウで、次のフォルダーに移動します。</span><span class="sxs-lookup"><span data-stu-id="1b4f2-155">In a command window, navigate to the following folder:</span></span>  
  
     <span data-ttu-id="1b4f2-156">\<*パスのサンプル*\>\Business Rules\Business こんにちは World1\bin\Debug\ のルール</span><span class="sxs-lookup"><span data-stu-id="1b4f2-156">\<*Samples Path*\>\Business Rules\Business Rules Hello World1\bin\Debug\\</span></span>  
  
2.  <span data-ttu-id="1b4f2-157">コマンド ウィンドウで、このサンプルの実行可能ファイル名 (BusinessRulesHelloWorld1.exe) を入力して、<localizedText>Enter</localizedText> キーを押します。</span><span class="sxs-lookup"><span data-stu-id="1b4f2-157">In the command window, type the name of the executable file for this sample (BusinessRulesHelloWorld1.exe), and then press ENTER.</span></span>  
  
    > [!NOTE]
    >  <span data-ttu-id="1b4f2-158">実行中に、この サンプルが生成されますが、ルール セット ファイル SampleRuleStore.xml で、 **bin \debug**フォルダーです。</span><span class="sxs-lookup"><span data-stu-id="1b4f2-158">While running, this sample produces the rule set file SampleRuleStore.xml in the **bin\Debug** folder.</span></span> <span data-ttu-id="1b4f2-159">実行可能ファイルを一時停止すると、<localizedText>Enter</localizedText> キーを押すまで終了が待機されるので、このファイルの内容を確認できます。</span><span class="sxs-lookup"><span data-stu-id="1b4f2-159">When the executable pauses, waiting for you to press ENTER to finish, you can examine the contents of this file.</span></span> <span data-ttu-id="1b4f2-160">このファイルは、任意のキーを押して終了する前に閉じてください。</span><span class="sxs-lookup"><span data-stu-id="1b4f2-160">Remember to close it before pressing any key to finish.</span></span> <span data-ttu-id="1b4f2-161">これを行わないと、後でこのサンプルを実行するための準備として、実行可能ファイルからこのファイルを削除できません。</span><span class="sxs-lookup"><span data-stu-id="1b4f2-161">Otherwise, the executable may not be able to delete it in preparation for subsequent runs of the sample.</span></span>  
  
 <span data-ttu-id="1b4f2-162">提供されているサンプル入力ファイル SampleDocumentInstance.xml に対して定義されている (1) 1 つの値を持つと共に、このサンプルを実行する場合は、作成したルール セットの特性に基づいてその**ID**要素を次の出力が表示されます。</span><span class="sxs-lookup"><span data-stu-id="1b4f2-162">Based on the nature of the created rule set, if you run this sample with the provided sample input file SampleDocumentInstance.xml, which has a value of one (1) defined for its **ID** element, you will see the following output:</span></span>  
  
```  
Creating a new ruleset ...  
Saving ruleset to SampleRuleStore.xml ...  
Loading ruleset ...  
Asserting objects ...  
Executing ...  
MySampleBusinessObject Class -- MySampleMethod executed for object 2 with parameter 5  
MySampleBusinessObject Class -- MySampleMethod executed for object 3 with parameter 5  
Press any key to finish ...  
```  
  
> [!NOTE]
>  <span data-ttu-id="1b4f2-163">太字、上記のコードでは両方と、次のコードでは、出力によって生成されるファイルに定義されているサンプル ビジネス オブジェクトに示す出力、 **MySampleLibrary**規則セットで参照されているフォルダーです。</span><span class="sxs-lookup"><span data-stu-id="1b4f2-163">The output shown in bold, both in the preceding code and in the code that follows, is the output produced by the sample business object, defined by the files in the **MySampleLibrary** folder, which is referenced by the rule set.</span></span>  
  
 <span data-ttu-id="1b4f2-164">関連付けられている値を変更する場合、 **ID**サンプル入力ファイル内の要素**SampleDocumentInstance.xml**から 1 つ (1 2 (2) に、出力はように変更します。</span><span class="sxs-lookup"><span data-stu-id="1b4f2-164">If you change the value associated with the **ID** element in the sample input file **SampleDocumentInstance.xml** from one (1) to two (2), the output would change as follows:</span></span>  
  
```  
Creating a new ruleset ...  
Saving ruleset to SampleRuleStore.xml ...  
Loading ruleset ...  
Asserting objects ...  
Executing ...  
MySampleBusinessObject Class -- MySampleMethod executed for object 1 with parameter 5  
MySampleBusinessObject Class -- MySampleMethod executed for object 3 with parameter 5  
Press any key to finish ...  
```  
  
 <span data-ttu-id="1b4f2-165">オブジェクトの場合、出力行は取得されません、 **MySampleBusinessObject**を持つクラス、 **MyValue**プロパティ、に関連付けられている値と一致する値(構築時)に設定します。**ID**サンプル入力ファイル SampleDocumentInstance.xml 内の要素。</span><span class="sxs-lookup"><span data-stu-id="1b4f2-165">You will not get an output line for any objects of the **MySampleBusinessObject** class that have their **MyValue** property set to a value (during construction) that matches the value associated with the **ID** element in the sample input file SampleDocumentInstance.xml.</span></span>  
  
## <a name="comments"></a><span data-ttu-id="1b4f2-166">コメント</span><span class="sxs-lookup"><span data-stu-id="1b4f2-166">Comments</span></span>  
 <span data-ttu-id="1b4f2-167">内にプログラムで作成したルール、 **CreateRuleset()**メソッドに示します。</span><span class="sxs-lookup"><span data-stu-id="1b4f2-167">The rule created programmatically within the **CreateRuleset()** method shows:</span></span>  
  
 <span data-ttu-id="1b4f2-168">**もし**</span><span class="sxs-lookup"><span data-stu-id="1b4f2-168">**IF**</span></span>  
  
 <span data-ttu-id="1b4f2-169">**MySampleBusinessObject.MyValue**がの値と等しくない、 **ID** XML ドキュメント内の要素。</span><span class="sxs-lookup"><span data-stu-id="1b4f2-169">**MySampleBusinessObject.MyValue** is not equal to the value of the **ID** element in the XML document.</span></span>  
  
 <span data-ttu-id="1b4f2-170">**そうしたら**</span><span class="sxs-lookup"><span data-stu-id="1b4f2-170">**THEN**</span></span>  
  
 <span data-ttu-id="1b4f2-171">**MySampleBusinessObject.MySampleMethod(int)**整数のパラメータをハードここでは、定数 5 (5) するようにコーディングします。</span><span class="sxs-lookup"><span data-stu-id="1b4f2-171">**MySampleBusinessObject.MySampleMethod(int)** with an integer parameter, hard coded to the constant five (5) in this case.</span></span> <span data-ttu-id="1b4f2-172">このメソッドが始まる出力行を生成する**MySampleBusinessObject Class –-**です。</span><span class="sxs-lookup"><span data-stu-id="1b4f2-172">This method produces the output lines that begin **MySampleBusinessObject Class –-**.</span></span>  
  
 <span data-ttu-id="1b4f2-173">このルールは、次の要因に依存します。</span><span class="sxs-lookup"><span data-stu-id="1b4f2-173">This rule depends on the following:</span></span>  
  
-   <span data-ttu-id="1b4f2-174">A **MySampleBusinessObject**というパブリック プロパティを持つクラス**MyValue**され、パブリック メソッドが呼び出されます**MySampleMethod** (整数のパラメータを所要時間)。</span><span class="sxs-lookup"><span data-stu-id="1b4f2-174">A **MySampleBusinessObject** class with a public property called **MyValue** and a public method called **MySampleMethod** (that takes in an integer parameter).</span></span>  
  
-   <span data-ttu-id="1b4f2-175">含む XML ドキュメントを定義する XML スキーマ定義言語 (XSD) スキーマ、 **ID**要素。</span><span class="sxs-lookup"><span data-stu-id="1b4f2-175">An XML schema definition language (XSD) schema that defines an XML document that contains an **ID** element.</span></span>  
  
 <span data-ttu-id="1b4f2-176">ルールは、クラスやスキーマとして定義しますが、実行中の場合は、関連するクラスのオブジェクト インスタンスおよび関連するスキーマのドキュメント インスタンスが必要です。</span><span class="sxs-lookup"><span data-stu-id="1b4f2-176">You define rules in terms of classes and schemas, but during execution, object instances of the relevant classes and document instances of the relevant schemas are required.</span></span> <span data-ttu-id="1b4f2-177">このような実行時のインスタンス (ファクト) に対してルールを評価します。</span><span class="sxs-lookup"><span data-stu-id="1b4f2-177">You evaluate the rules against these run-time instances (known as facts).</span></span> <span data-ttu-id="1b4f2-178">このサンプルでは、ファクトはの複数のインスタンス、 **MySampleBusinessObject**の値が異なる構築されたオブジェクト、 **MyValue**プロパティ、および定義済みのスキーマの単一の XML インスタンス値を格納している、 **ID**要素。</span><span class="sxs-lookup"><span data-stu-id="1b4f2-178">In this sample, the facts are multiple instances of the **MySampleBusinessObject** object, constructed with different values for their **MyValue** property, and a single XML instance of the defined schema that contains a value for the **ID** element.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="1b4f2-179">参照</span><span class="sxs-lookup"><span data-stu-id="1b4f2-179">See Also</span></span>  
 [<span data-ttu-id="1b4f2-180">ビジネス ルール (BizTalk Server サンプル フォルダー)</span><span class="sxs-lookup"><span data-stu-id="1b4f2-180">Business Rules (BizTalk Server Samples Folder)</span></span>](../core/business-rules-biztalk-server-samples-folder.md)