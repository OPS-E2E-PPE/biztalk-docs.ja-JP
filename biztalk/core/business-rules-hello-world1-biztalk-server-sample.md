---
title: Business Rules こんにちは World1 (BizTalk Server サンプル) |Microsoft Docs
ms.custom: ''
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: ''
ms.suite: ''
ms.tgt_pltfrm: ''
ms.topic: article
helpviewer_keywords:
- examples, business rules
- business rules, examples
ms.assetid: 0623ad20-96cc-430e-bb36-35431a5d17ee
caps.latest.revision: 16
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: ebf4afafeabeae8fa9dec0683bd344c40ce23da8
ms.sourcegitcommit: 266308ec5c6a9d8d80ff298ee6051b4843c5d626
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 06/27/2018
ms.locfileid: "36990003"
---
# <a name="business-rules-hello-world1-biztalk-server-sample"></a><span data-ttu-id="d0198-102">Business Rules こんにちは World1 (BizTalk Server サンプル)</span><span class="sxs-lookup"><span data-stu-id="d0198-102">Business Rules Hello World1 (BizTalk Server Sample)</span></span>
<span data-ttu-id="d0198-103">Business Rules Hello World1 サンプルでは、BizTalk ルール セットを作成して、そのルール セットをファイル (SampleRuleSet.xml) に保存し、読み込んでから、サンプルのファクト セットに基づいて実行する方法を示します。</span><span class="sxs-lookup"><span data-stu-id="d0198-103">The Business Rules Hello World1 sample demonstrates how to create a BizTalk rule set, save it to a file (SampleRuleSet.xml), load it, and run it based on a sample set of facts.</span></span> <span data-ttu-id="d0198-104">サンプルのルール セットには、ルール定義の条件として XML 要素を含む単一のルール、および .NET ベースのオブジェクト (プロパティとメンバ) が含まれます。</span><span class="sxs-lookup"><span data-stu-id="d0198-104">The sample rule set contains a simple rule that involves an XML element, and .NET-based objects (properties and members) as terms in rule definition.</span></span>  
  
## <a name="what-this-sample-does"></a><span data-ttu-id="d0198-105">このサンプルの処理</span><span class="sxs-lookup"><span data-stu-id="d0198-105">What This Sample Does</span></span>  
 <span data-ttu-id="d0198-106">このサンプルでは、次の一連の手順を実行する実行可能ファイルを作成します。</span><span class="sxs-lookup"><span data-stu-id="d0198-106">This sample creates an executable that performs the following sequence of steps:</span></span>  
  
1.  <span data-ttu-id="d0198-107">メソッドを呼び出して**CreateRuleset** 「解説」セクションで説明されている設定ルールを作成しますします。</span><span class="sxs-lookup"><span data-stu-id="d0198-107">Calls the method **CreateRuleset** to build the rule set described in the Remarks section.</span></span>  
  
2.  <span data-ttu-id="d0198-108">メソッドを呼び出して**SaveToFile**を示すファイルへのルール セットを保存します。</span><span class="sxs-lookup"><span data-stu-id="d0198-108">Calls the method **SaveToFile** to demonstrate saving a rule set to a file.</span></span>  
  
3.  <span data-ttu-id="d0198-109">メソッドを呼び出して**LoadFromFile**を読み込み、ファイルからルール セットを示すためにします。</span><span class="sxs-lookup"><span data-stu-id="d0198-109">Calls the method **LoadFromFile** to demonstrate loading a rule set from a file.</span></span>  
  
4.  <span data-ttu-id="d0198-110">ルール セットの実行対象のサンプル ファクトを作成します。</span><span class="sxs-lookup"><span data-stu-id="d0198-110">Constructs sample facts against which to run the rule set.</span></span>  
  
5.  <span data-ttu-id="d0198-111">サンプル ファクトに対してルール セットを実行し、画面出力を作成します。</span><span class="sxs-lookup"><span data-stu-id="d0198-111">Runs the rule set against the sample facts, producing screen output.</span></span>  
  
6.  <span data-ttu-id="d0198-112">一時停止し、ルール セット ファイル SampleRuleStore.xml を確認できるようにします。</span><span class="sxs-lookup"><span data-stu-id="d0198-112">Pauses, enabling you to examine the rule set file SampleRuleStore.xml.</span></span>  
  
7.  <span data-ttu-id="d0198-113">後でこのサンプルを実行するための準備として、ルール セット ファイルを削除して、クリーンアップします。</span><span class="sxs-lookup"><span data-stu-id="d0198-113">Cleans up by deleting the rule set file in preparation for subsequent runs of the sample.</span></span>  
  
## <a name="where-to-find-this-sample"></a><span data-ttu-id="d0198-114">このサンプルの場所</span><span class="sxs-lookup"><span data-stu-id="d0198-114">Where to Find This Sample</span></span>  
 <span data-ttu-id="d0198-115">\<*パスのサンプル*\>\Business Rules\Business こんにちは World1\ のルール</span><span class="sxs-lookup"><span data-stu-id="d0198-115">\<*Samples Path*\>\Business Rules\Business Rules Hello World1\\</span></span>  
  
 <span data-ttu-id="d0198-116">次の表は、このサンプルのファイルとその目的を示しています。</span><span class="sxs-lookup"><span data-stu-id="d0198-116">The following table shows the files in this sample and describes their purpose.</span></span>  
  
|<span data-ttu-id="d0198-117">ファイル</span><span class="sxs-lookup"><span data-stu-id="d0198-117">File(s)</span></span>|<span data-ttu-id="d0198-118">説明</span><span class="sxs-lookup"><span data-stu-id="d0198-118">Description</span></span>|  
|---------------|-----------------|  
|<span data-ttu-id="d0198-119">App.ico、AssemblyInfo.cs、BusinessRulesHelloWorld1.csproj、および BusinessRulesHelloWorld1.sln</span><span class="sxs-lookup"><span data-stu-id="d0198-119">App.ico, AssemblyInfo.cs, BusinessRulesHelloWorld1.csproj, BusinessRulesHelloWorld1.sln</span></span>|<span data-ttu-id="d0198-120">このサンプルで、ルール セットの作成、保存、読み込み、実行を行う部分で使用するプロジェクト ファイル、ソリューション ファイル、その他の関連ファイルです。</span><span class="sxs-lookup"><span data-stu-id="d0198-120">Project, solution, and related files for the portion of this sample that creates, saves, loads, and runs a rule set.</span></span>|  
|<span data-ttu-id="d0198-121">HelloWorld1.cs</span><span class="sxs-lookup"><span data-stu-id="d0198-121">HelloWorld1.cs</span></span>|<span data-ttu-id="d0198-122">ルール セットの作成、ファイルへのルール セットの保存、およびファイルからルール セットを読み込む方法を示すメソッドを含む Visual C# ファイルです。</span><span class="sxs-lookup"><span data-stu-id="d0198-122">Visual C# file that contains methods to demonstrate creating a rule set, saving a rule set to a file, and loading a rule set from a file.</span></span> <span data-ttu-id="d0198-123">これらのメソッドを呼び出し、作成したルール セットを実行する、前後のコードも含まれます。</span><span class="sxs-lookup"><span data-stu-id="d0198-123">Also contains surrounding code that calls these methods and then runs the created rule set.</span></span>|  
|<span data-ttu-id="d0198-124">Cleanup.bat</span><span class="sxs-lookup"><span data-stu-id="d0198-124">Cleanup.bat</span></span>|<span data-ttu-id="d0198-125">アセンブリを展開解除し、グローバル アセンブリ キャッシュ (GAC) から削除するために使用されます。</span><span class="sxs-lookup"><span data-stu-id="d0198-125">Used to undeploy assemblies and remove them from the global assembly cache (GAC).</span></span> <span data-ttu-id="d0198-126">送信ポートと受信ポートが削除されます。</span><span class="sxs-lookup"><span data-stu-id="d0198-126">Removes send and receive ports.</span></span> <span data-ttu-id="d0198-127">必要に応じて、Microsoft インターネット インフォメーション サービス (IIS) の仮想ディレクトリが削除されます。</span><span class="sxs-lookup"><span data-stu-id="d0198-127">Removes Microsoft Internet Information Services (IIS) virtual directories as needed.</span></span>|  
|<span data-ttu-id="d0198-128">SampleDocumentInstance.xml</span><span class="sxs-lookup"><span data-stu-id="d0198-128">SampleDocumentInstance.xml</span></span>|<span data-ttu-id="d0198-129">ファイル SampleSchema.xsd で定義されているスキーマに準拠したサンプル入力ファイルです。</span><span class="sxs-lookup"><span data-stu-id="d0198-129">Sample input file that conforms to the schema defined in the file SampleSchema.xsd.</span></span>|  
|<span data-ttu-id="d0198-130">SampleSchema.xsd</span><span class="sxs-lookup"><span data-stu-id="d0198-130">SampleSchema.xsd</span></span>|<span data-ttu-id="d0198-131">簡潔なスキーマを定義したスキーマ ファイルで、Visual C# ファイル HelloWorld1.cs で作成されたルール セットから参照される要素が含まれます。</span><span class="sxs-lookup"><span data-stu-id="d0198-131">Schema file that defines a simple schema with an element referenced by the rule set created in the Visual C# file HelloWorld1.cs.</span></span>|  
|<span data-ttu-id="d0198-132">Setup.bat</span><span class="sxs-lookup"><span data-stu-id="d0198-132">Setup.bat</span></span>|<span data-ttu-id="d0198-133">このサンプルをビルドおよび初期化するために使用されます。</span><span class="sxs-lookup"><span data-stu-id="d0198-133">Used to build and initialize this sample.</span></span>|  
|<span data-ttu-id="d0198-134">\MySampleLibrary フォルダーに含まれるファイル: </span><span class="sxs-lookup"><span data-stu-id="d0198-134">In the \MySampleLibrary folder:</span></span><br /><br /> <span data-ttu-id="d0198-135">AssemblyInfo.cs、MySampleLibrary.csproj、および MySampleLibrary.sln</span><span class="sxs-lookup"><span data-stu-id="d0198-135">AssemblyInfo.cs, MySampleLibrary.csproj, MySampleLibrary.sln</span></span>|<span data-ttu-id="d0198-136">このサンプルで、作成したルール セットから参照されるオブジェクトを定義するクラスを提供する部分で使用するプロジェクト ファイル、ソリューション ファイル、その他の関連ファイルです。</span><span class="sxs-lookup"><span data-stu-id="d0198-136">Project, solution, and related files for the portion of this sample that provides the class that defines the objects referenced by the created rule set.</span></span>|  
|<span data-ttu-id="d0198-137">\MySampleLibrary フォルダーに含まれるファイル: </span><span class="sxs-lookup"><span data-stu-id="d0198-137">In the \MySampleLibrary folder:</span></span><br /><br /> <span data-ttu-id="d0198-138">MySampleLibraryClass.cs</span><span class="sxs-lookup"><span data-stu-id="d0198-138">MySampleLibraryClass.cs</span></span>|<span data-ttu-id="d0198-139">参照されているプロパティを含む visual c# ファイル、**場合**、作成した規則で呼び出されるメソッドの部分、**し**作成した規則の一部です。</span><span class="sxs-lookup"><span data-stu-id="d0198-139">Visual C# file that contains the property referenced in the **IF** portion of the created rule, and the method that may be called in the **THEN** portion of the created rule.</span></span>|  
  
## <a name="building-and-initializing-this-sample"></a><span data-ttu-id="d0198-140">このサンプルのビルドと初期化</span><span class="sxs-lookup"><span data-stu-id="d0198-140">Building and Initializing This Sample</span></span>  
 <span data-ttu-id="d0198-141">次の手順を使用して、Business Rules Hello World1 サンプルの作成および初期化を行います。</span><span class="sxs-lookup"><span data-stu-id="d0198-141">Use the following procedure to build and initialize the Business Rules Hello World1 sample.</span></span>  
  
#### <a name="to-build-and-initialize-this-sample"></a><span data-ttu-id="d0198-142">このサンプルを作成および初期化するには</span><span class="sxs-lookup"><span data-stu-id="d0198-142">To build and initialize this sample</span></span>  
  
1. <span data-ttu-id="d0198-143">コマンド ウィンドウで、次のフォルダーに移動します。</span><span class="sxs-lookup"><span data-stu-id="d0198-143">In a command window, navigate to the following folder:</span></span>  
  
    <span data-ttu-id="d0198-144">\<*パスのサンプル*\>\Business Rules\Business こんにちは World1\ のルール</span><span class="sxs-lookup"><span data-stu-id="d0198-144">\<*Samples Path*\>\Business Rules\Business Rules Hello World1\\</span></span>  
  
2. <span data-ttu-id="d0198-145">ファイルは、次の操作を実行します。 Setup.bat を実行します。</span><span class="sxs-lookup"><span data-stu-id="d0198-145">Run the file Setup.bat, which performs the following actions:</span></span>  
  
   - <span data-ttu-id="d0198-146">コンパイルし、Microsoft の展開[!INCLUDE[btsVStudioNoVersion](../includes/btsvstudionoversion-md.md)]このサンプルのプロジェクト。</span><span class="sxs-lookup"><span data-stu-id="d0198-146">Compiles and deploys the Microsoft [!INCLUDE[btsVStudioNoVersion](../includes/btsvstudionoversion-md.md)] projects for this sample.</span></span>  
  
   > [!NOTE]
   >  <span data-ttu-id="d0198-147">このサンプルを実行する前に、ビルドと初期化のプロセス中に [!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)] でエラーが報告されていないことを確認する必要があります。</span><span class="sxs-lookup"><span data-stu-id="d0198-147">You should confirm that [!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)] did not report any errors during the build and initialization process before attempting to run this sample.</span></span>  
   > 
   > [!NOTE]
   >  <span data-ttu-id="d0198-148">開き、Setup.bat ファイルを実行することがなくこのサンプルでは、プロジェクトをビルドする場合は、まず、.NET Framework の厳密名ユーティリティ (sn.exe) を使用して厳密な名前キーのペアを作成する必要があります。</span><span class="sxs-lookup"><span data-stu-id="d0198-148">If you choose to open and build the projects in this sample without running the file Setup.bat, you must first create a strong name key pair using the .NET Framework Strong Name utility (sn.exe).</span></span> <span data-ttu-id="d0198-149">このキー ペアは、生成されたアセンブリの署名に使用します。</span><span class="sxs-lookup"><span data-stu-id="d0198-149">Use this key pair to sign the resulting assemblies.</span></span>  
   > 
   > [!NOTE]
   >  <span data-ttu-id="d0198-150">Setup.bat によって行われた変更を元に戻すには、Cleanup.bat を実行します。</span><span class="sxs-lookup"><span data-stu-id="d0198-150">To undo changes made by Setup.bat, run Cleanup.bat.</span></span> <span data-ttu-id="d0198-151">Setup.bat を 2 回目に実行する場合は、その前に Cleanup.bat を実行してください。</span><span class="sxs-lookup"><span data-stu-id="d0198-151">You must run Cleanup.bat before running Setup.bat a second time.</span></span>  
  
## <a name="running-this-sample"></a><span data-ttu-id="d0198-152">このサンプルの実行</span><span class="sxs-lookup"><span data-stu-id="d0198-152">Running This Sample</span></span>  
 <span data-ttu-id="d0198-153">次の手順を使用して、Business Rules Hello World1 サンプルを実行します。</span><span class="sxs-lookup"><span data-stu-id="d0198-153">Use the following procedure to run the Business Rules Hello World1 sample.</span></span>  
  
#### <a name="to-run-this-sample"></a><span data-ttu-id="d0198-154">このサンプルを実行するには</span><span class="sxs-lookup"><span data-stu-id="d0198-154">To run this sample</span></span>  
  
1. <span data-ttu-id="d0198-155">コマンド ウィンドウで、次のフォルダーに移動します。</span><span class="sxs-lookup"><span data-stu-id="d0198-155">In a command window, navigate to the following folder:</span></span>  
  
    <span data-ttu-id="d0198-156">\<*パスのサンプル*\>\Business Rules\Business こんにちは World1\bin\Debug\ のルール</span><span class="sxs-lookup"><span data-stu-id="d0198-156">\<*Samples Path*\>\Business Rules\Business Rules Hello World1\bin\Debug\\</span></span>  
  
2. <span data-ttu-id="d0198-157">コマンド ウィンドウで、このサンプルの実行可能ファイル名 (BusinessRulesHelloWorld1.exe) を入力して、<localizedText>Enter</localizedText> キーを押します。</span><span class="sxs-lookup"><span data-stu-id="d0198-157">In the command window, type the name of the executable file for this sample (BusinessRulesHelloWorld1.exe), and then press ENTER.</span></span>  
  
   > [!NOTE]
   >  <span data-ttu-id="d0198-158">規則セット ファイル SampleRuleStore.xml このサンプルでの実行中に、 **bin \debug**フォルダー。</span><span class="sxs-lookup"><span data-stu-id="d0198-158">While running, this sample produces the rule set file SampleRuleStore.xml in the **bin\Debug** folder.</span></span> <span data-ttu-id="d0198-159">実行可能ファイルを一時停止すると、<localizedText>Enter</localizedText> キーを押すまで終了が待機されるので、このファイルの内容を確認できます。</span><span class="sxs-lookup"><span data-stu-id="d0198-159">When the executable pauses, waiting for you to press ENTER to finish, you can examine the contents of this file.</span></span> <span data-ttu-id="d0198-160">このファイルは、任意のキーを押して終了する前に閉じてください。</span><span class="sxs-lookup"><span data-stu-id="d0198-160">Remember to close it before pressing any key to finish.</span></span> <span data-ttu-id="d0198-161">これを行わないと、後でこのサンプルを実行するための準備として、実行可能ファイルからこのファイルを削除できません。</span><span class="sxs-lookup"><span data-stu-id="d0198-161">Otherwise, the executable may not be able to delete it in preparation for subsequent runs of the sample.</span></span>  
  
   <span data-ttu-id="d0198-162">提供されているサンプル入力ファイル SampleDocumentInstance.xml に対して定義されている (1) 1 つの値を持つこのサンプルを実行する場合、作成したルール セットの特性に基づき、 **ID**要素、次の出力が表示されます。</span><span class="sxs-lookup"><span data-stu-id="d0198-162">Based on the nature of the created rule set, if you run this sample with the provided sample input file SampleDocumentInstance.xml, which has a value of one (1) defined for its **ID** element, you will see the following output:</span></span>  
  
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
>  <span data-ttu-id="d0198-163">太字、上記のコードでは両方と、次のコードでは、出力によって生成されたファイルに定義されているサンプル ビジネス オブジェクトに示した出力、 **MySampleLibrary**フォルダーで、ルール セットによって参照されています。</span><span class="sxs-lookup"><span data-stu-id="d0198-163">The output shown in bold, both in the preceding code and in the code that follows, is the output produced by the sample business object, defined by the files in the **MySampleLibrary** folder, which is referenced by the rule set.</span></span>  
  
 <span data-ttu-id="d0198-164">関連付けられている値を変更する場合、 **ID**サンプル入力ファイル内の要素**SampleDocumentInstance.xml**から 1 つ (1) に 2 つ (2)、出力はように変更します。</span><span class="sxs-lookup"><span data-stu-id="d0198-164">If you change the value associated with the **ID** element in the sample input file **SampleDocumentInstance.xml** from one (1) to two (2), the output would change as follows:</span></span>  
  
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
  
 <span data-ttu-id="d0198-165">オブジェクトの場合、出力行は取得されません、 **MySampleBusinessObject**を持つクラス、 **MyValue**プロパティ、に関連付けられている値と一致する値(構築時)に設定**ID**サンプル入力ファイル SampleDocumentInstance.xml 内の要素。</span><span class="sxs-lookup"><span data-stu-id="d0198-165">You will not get an output line for any objects of the **MySampleBusinessObject** class that have their **MyValue** property set to a value (during construction) that matches the value associated with the **ID** element in the sample input file SampleDocumentInstance.xml.</span></span>  
  
## <a name="comments"></a><span data-ttu-id="d0198-166">コメント</span><span class="sxs-lookup"><span data-stu-id="d0198-166">Comments</span></span>  
 <span data-ttu-id="d0198-167">内にプログラムで作成した規則、 **CreateRuleset()** メソッドに示します。</span><span class="sxs-lookup"><span data-stu-id="d0198-167">The rule created programmatically within the **CreateRuleset()** method shows:</span></span>  
  
 <span data-ttu-id="d0198-168">**IF**</span><span class="sxs-lookup"><span data-stu-id="d0198-168">**IF**</span></span>  
  
 <span data-ttu-id="d0198-169">**MySampleBusinessObject.MyValue**の値と等しく、 **ID** XML ドキュメント内の要素。</span><span class="sxs-lookup"><span data-stu-id="d0198-169">**MySampleBusinessObject.MyValue** is not equal to the value of the **ID** element in the XML document.</span></span>  
  
 <span data-ttu-id="d0198-170">**THEN**</span><span class="sxs-lookup"><span data-stu-id="d0198-170">**THEN**</span></span>  
  
 <span data-ttu-id="d0198-171">**MySampleBusinessObject.MySampleMethod(int)** パラメーターを使用して、整数、ハードここでは、定数 5 (5) にコード化されました。</span><span class="sxs-lookup"><span data-stu-id="d0198-171">**MySampleBusinessObject.MySampleMethod(int)** with an integer parameter, hard coded to the constant five (5) in this case.</span></span> <span data-ttu-id="d0198-172">このメソッドが始まる出力行を生成**MySampleBusinessObject Class –-** します。</span><span class="sxs-lookup"><span data-stu-id="d0198-172">This method produces the output lines that begin **MySampleBusinessObject Class –-**.</span></span>  
  
 <span data-ttu-id="d0198-173">このルールは、次の要因に依存します。</span><span class="sxs-lookup"><span data-stu-id="d0198-173">This rule depends on the following:</span></span>  
  
- <span data-ttu-id="d0198-174">A **MySampleBusinessObject**というパブリック プロパティを持つクラス**MyValue**というパブリック メソッドと**MySampleMethod** (整数パラメーターで受け取る)。</span><span class="sxs-lookup"><span data-stu-id="d0198-174">A **MySampleBusinessObject** class with a public property called **MyValue** and a public method called **MySampleMethod** (that takes in an integer parameter).</span></span>  
  
- <span data-ttu-id="d0198-175">含む XML ドキュメントを定義する XML スキーマ定義言語 (XSD) スキーマ、 **ID**要素。</span><span class="sxs-lookup"><span data-stu-id="d0198-175">An XML schema definition language (XSD) schema that defines an XML document that contains an **ID** element.</span></span>  
  
  <span data-ttu-id="d0198-176">ルールは、クラスやスキーマとして定義しますが、実行中の場合は、関連するクラスのオブジェクト インスタンスおよび関連するスキーマのドキュメント インスタンスが必要です。</span><span class="sxs-lookup"><span data-stu-id="d0198-176">You define rules in terms of classes and schemas, but during execution, object instances of the relevant classes and document instances of the relevant schemas are required.</span></span> <span data-ttu-id="d0198-177">このような実行時のインスタンス (ファクト) に対してルールを評価します。</span><span class="sxs-lookup"><span data-stu-id="d0198-177">You evaluate the rules against these run-time instances (known as facts).</span></span> <span data-ttu-id="d0198-178">このサンプルでは、ファクトはの複数のインスタンス、 **MySampleBusinessObject**に別の値を使用して構築されているオブジェクト、 **MyValue**プロパティ、および定義済みのスキーマの単一の XML インスタンス値を格納している、 **ID**要素。</span><span class="sxs-lookup"><span data-stu-id="d0198-178">In this sample, the facts are multiple instances of the **MySampleBusinessObject** object, constructed with different values for their **MyValue** property, and a single XML instance of the defined schema that contains a value for the **ID** element.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="d0198-179">参照</span><span class="sxs-lookup"><span data-stu-id="d0198-179">See Also</span></span>  
 [<span data-ttu-id="d0198-180">ビジネス ルール (BizTalk Server サンプル フォルダー)</span><span class="sxs-lookup"><span data-stu-id="d0198-180">Business Rules (BizTalk Server Samples Folder)</span></span>](../core/business-rules-biztalk-server-samples-folder.md)