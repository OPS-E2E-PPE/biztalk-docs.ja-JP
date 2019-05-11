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
ms.openlocfilehash: 48097f4803aba02c19abbd0a1a48c7f9103545c4
ms.sourcegitcommit: 381e83d43796a345488d54b3f7413e11d56ad7be
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 05/07/2019
ms.locfileid: "65357668"
---
# <a name="business-rules-hello-world1-biztalk-server-sample"></a><span data-ttu-id="54d00-102">Business Rules こんにちは World1 (BizTalk Server サンプル)</span><span class="sxs-lookup"><span data-stu-id="54d00-102">Business Rules Hello World1 (BizTalk Server Sample)</span></span>
<span data-ttu-id="54d00-103">Business Rules こんにちは World1 サンプルでは、BizTalk ルール セットを作成、ファイル (SampleRuleSet.xml) に保存、読み込み、およびサンプルのファクト セットに基づいて実行する方法を示します。</span><span class="sxs-lookup"><span data-stu-id="54d00-103">The Business Rules Hello World1 sample demonstrates how to create a BizTalk rule set, save it to a file (SampleRuleSet.xml), load it, and run it based on a sample set of facts.</span></span> <span data-ttu-id="54d00-104">サンプルのルール セットが XML 要素を含む単純なルールを含むとします。NET ベースのオブジェクト (プロパティとメンバ) ルールの定義の条件として。</span><span class="sxs-lookup"><span data-stu-id="54d00-104">The sample rule set contains a simple rule that involves an XML element, and .NET-based objects (properties and members) as terms in rule definition.</span></span>  
  
## <a name="what-this-sample-does"></a><span data-ttu-id="54d00-105">このサンプルの処理</span><span class="sxs-lookup"><span data-stu-id="54d00-105">What This Sample Does</span></span>  
 <span data-ttu-id="54d00-106">このサンプルでは、次の一連の手順を実行する実行可能ファイルを作成します。</span><span class="sxs-lookup"><span data-stu-id="54d00-106">This sample creates an executable that performs the following sequence of steps:</span></span>  
  
1.  <span data-ttu-id="54d00-107">メソッドを呼び出して**CreateRuleset** 「解説」セクションで説明されている設定ルールを作成しますします。</span><span class="sxs-lookup"><span data-stu-id="54d00-107">Calls the method **CreateRuleset** to build the rule set described in the Remarks section.</span></span>  
  
2.  <span data-ttu-id="54d00-108">メソッドを呼び出して**SaveToFile**を示すファイルへのルール セットを保存します。</span><span class="sxs-lookup"><span data-stu-id="54d00-108">Calls the method **SaveToFile** to demonstrate saving a rule set to a file.</span></span>  
  
3.  <span data-ttu-id="54d00-109">メソッドを呼び出して**LoadFromFile**を読み込み、ファイルからルール セットを示すためにします。</span><span class="sxs-lookup"><span data-stu-id="54d00-109">Calls the method **LoadFromFile** to demonstrate loading a rule set from a file.</span></span>  
  
4.  <span data-ttu-id="54d00-110">構成要素のサンプル ファクトに対してルール セットを実行します。</span><span class="sxs-lookup"><span data-stu-id="54d00-110">Constructs sample facts against which to run the rule set.</span></span>  
  
5.  <span data-ttu-id="54d00-111">画面出力を生成する、サンプル ファクトに対してルール セットを実行します。</span><span class="sxs-lookup"><span data-stu-id="54d00-111">Runs the rule set against the sample facts, producing screen output.</span></span>  
  
6.  <span data-ttu-id="54d00-112">一時停止し、ファイル SampleRuleStore.xml を設定をルールを確認します。</span><span class="sxs-lookup"><span data-stu-id="54d00-112">Pauses, enabling you to examine the rule set file SampleRuleStore.xml.</span></span>  
  
7.  <span data-ttu-id="54d00-113">サンプルの後続の実行の準備のルール セット ファイルを削除してクリーンアップします。</span><span class="sxs-lookup"><span data-stu-id="54d00-113">Cleans up by deleting the rule set file in preparation for subsequent runs of the sample.</span></span>  
  
## <a name="where-to-find-this-sample"></a><span data-ttu-id="54d00-114">このサンプルの場所</span><span class="sxs-lookup"><span data-stu-id="54d00-114">Where to Find This Sample</span></span>  
 <span data-ttu-id="54d00-115">\<*パスのサンプル*\>\Business Rules\Business こんにちは World1\ のルール</span><span class="sxs-lookup"><span data-stu-id="54d00-115">\<*Samples Path*\>\Business Rules\Business Rules Hello World1\\</span></span>  
  
 <span data-ttu-id="54d00-116">次の表は、このサンプルのファイルとその目的を示しています。</span><span class="sxs-lookup"><span data-stu-id="54d00-116">The following table shows the files in this sample and describes their purpose.</span></span>  
  
|<span data-ttu-id="54d00-117">ファイル</span><span class="sxs-lookup"><span data-stu-id="54d00-117">File(s)</span></span>|<span data-ttu-id="54d00-118">説明</span><span class="sxs-lookup"><span data-stu-id="54d00-118">Description</span></span>|  
|---------------|-----------------|  
|<span data-ttu-id="54d00-119">App.ico, AssemblyInfo.cs, BusinessRulesHelloWorld1.csproj, BusinessRulesHelloWorld1.sln</span><span class="sxs-lookup"><span data-stu-id="54d00-119">App.ico, AssemblyInfo.cs, BusinessRulesHelloWorld1.csproj, BusinessRulesHelloWorld1.sln</span></span>|<span data-ttu-id="54d00-120">プロジェクト、ソリューション、および他の関連ファイルを作成、保存、このサンプルの一部が読み込まれ、ルール セットを実行します。</span><span class="sxs-lookup"><span data-stu-id="54d00-120">Project, solution, and related files for the portion of this sample that creates, saves, loads, and runs a rule set.</span></span>|  
|<span data-ttu-id="54d00-121">HelloWorld1.cs</span><span class="sxs-lookup"><span data-stu-id="54d00-121">HelloWorld1.cs</span></span>|<span data-ttu-id="54d00-122">VisualC#ファイルからルール セットを作成する、規則セットをファイルに保存、およびルールの読み込みを示すためにメソッドを含むファイルを設定します。</span><span class="sxs-lookup"><span data-stu-id="54d00-122">Visual C# file that contains methods to demonstrate creating a rule set, saving a rule set to a file, and loading a rule set from a file.</span></span> <span data-ttu-id="54d00-123">これらのメソッドを呼び出すし、作成したルール セットを実行する前後のコードも含まれています。</span><span class="sxs-lookup"><span data-stu-id="54d00-123">Also contains surrounding code that calls these methods and then runs the created rule set.</span></span>|  
|<span data-ttu-id="54d00-124">Cleanup.bat</span><span class="sxs-lookup"><span data-stu-id="54d00-124">Cleanup.bat</span></span>|<span data-ttu-id="54d00-125">アセンブリを展開解除し、グローバル アセンブリ キャッシュ (GAC) から削除するために使用されます。</span><span class="sxs-lookup"><span data-stu-id="54d00-125">Used to undeploy assemblies and remove them from the global assembly cache (GAC).</span></span> <span data-ttu-id="54d00-126">送信ポートと受信ポートが削除されます。</span><span class="sxs-lookup"><span data-stu-id="54d00-126">Removes send and receive ports.</span></span> <span data-ttu-id="54d00-127">必要に応じて、Microsoft インターネット インフォメーション サービス (IIS) の仮想ディレクトリが削除されます。</span><span class="sxs-lookup"><span data-stu-id="54d00-127">Removes Microsoft Internet Information Services (IIS) virtual directories as needed.</span></span>|  
|<span data-ttu-id="54d00-128">SampleDocumentInstance.xml</span><span class="sxs-lookup"><span data-stu-id="54d00-128">SampleDocumentInstance.xml</span></span>|<span data-ttu-id="54d00-129">ファイル SampleSchema.xsd で定義されているスキーマに準拠したサンプル入力ファイルです。</span><span class="sxs-lookup"><span data-stu-id="54d00-129">Sample input file that conforms to the schema defined in the file SampleSchema.xsd.</span></span>|  
|<span data-ttu-id="54d00-130">SampleSchema.xsd</span><span class="sxs-lookup"><span data-stu-id="54d00-130">SampleSchema.xsd</span></span>|<span data-ttu-id="54d00-131">セットは、ビジュアルの作成ルールによって参照される要素を単純なスキーマを定義したスキーマ ファイルC#ファイル HelloWorld1.cs します。</span><span class="sxs-lookup"><span data-stu-id="54d00-131">Schema file that defines a simple schema with an element referenced by the rule set created in the Visual C# file HelloWorld1.cs.</span></span>|  
|<span data-ttu-id="54d00-132">Setup.bat</span><span class="sxs-lookup"><span data-stu-id="54d00-132">Setup.bat</span></span>|<span data-ttu-id="54d00-133">このサンプルをビルドおよび初期化するために使用されます。</span><span class="sxs-lookup"><span data-stu-id="54d00-133">Used to build and initialize this sample.</span></span>|  
|<span data-ttu-id="54d00-134">\MySampleLibrary フォルダーには。</span><span class="sxs-lookup"><span data-stu-id="54d00-134">In the \MySampleLibrary folder:</span></span><br /><br /> <span data-ttu-id="54d00-135">AssemblyInfo.cs、MySampleLibrary.csproj、および MySampleLibrary.sln</span><span class="sxs-lookup"><span data-stu-id="54d00-135">AssemblyInfo.cs, MySampleLibrary.csproj, MySampleLibrary.sln</span></span>|<span data-ttu-id="54d00-136">このサンプルで、作成したルール セットから参照されるオブジェクトを定義するクラスを提供する部分で使用するプロジェクト ファイル、ソリューション ファイル、その他の関連ファイルです。</span><span class="sxs-lookup"><span data-stu-id="54d00-136">Project, solution, and related files for the portion of this sample that provides the class that defines the objects referenced by the created rule set.</span></span>|  
|<span data-ttu-id="54d00-137">\MySampleLibrary フォルダーには。</span><span class="sxs-lookup"><span data-stu-id="54d00-137">In the \MySampleLibrary folder:</span></span><br /><br /> <span data-ttu-id="54d00-138">MySampleLibraryClass.cs</span><span class="sxs-lookup"><span data-stu-id="54d00-138">MySampleLibraryClass.cs</span></span>|<span data-ttu-id="54d00-139">参照されているプロパティを含む visual c# ファイル、**場合**、作成した規則で呼び出されるメソッドの部分、**し**作成した規則の一部です。</span><span class="sxs-lookup"><span data-stu-id="54d00-139">Visual C# file that contains the property referenced in the **IF** portion of the created rule, and the method that may be called in the **THEN** portion of the created rule.</span></span>|  
  
## <a name="building-and-initializing-this-sample"></a><span data-ttu-id="54d00-140">このサンプルのビルドと初期化</span><span class="sxs-lookup"><span data-stu-id="54d00-140">Building and Initializing This Sample</span></span>  
 <span data-ttu-id="54d00-141">ビルドおよび初期化する Business Rules こんにちは World1 サンプルを次の手順を使用します。</span><span class="sxs-lookup"><span data-stu-id="54d00-141">Use the following procedure to build and initialize the Business Rules Hello World1 sample.</span></span>  
  
#### <a name="to-build-and-initialize-this-sample"></a><span data-ttu-id="54d00-142">このサンプルを作成および初期化するには</span><span class="sxs-lookup"><span data-stu-id="54d00-142">To build and initialize this sample</span></span>  
  
1. <span data-ttu-id="54d00-143">コマンド ウィンドウで、次のフォルダーに移動します。</span><span class="sxs-lookup"><span data-stu-id="54d00-143">In a command window, navigate to the following folder:</span></span>  
  
    <span data-ttu-id="54d00-144">\<*パスのサンプル*\>\Business Rules\Business こんにちは World1\ のルール</span><span class="sxs-lookup"><span data-stu-id="54d00-144">\<*Samples Path*\>\Business Rules\Business Rules Hello World1\\</span></span>  
  
2. <span data-ttu-id="54d00-145">ファイルは、次の操作を実行します。 Setup.bat を実行します。</span><span class="sxs-lookup"><span data-stu-id="54d00-145">Run the file Setup.bat, which performs the following actions:</span></span>  
  
   - <span data-ttu-id="54d00-146">コンパイルし、Microsoft の展開[!INCLUDE[btsVStudioNoVersion](../includes/btsvstudionoversion-md.md)]このサンプルのプロジェクト。</span><span class="sxs-lookup"><span data-stu-id="54d00-146">Compiles and deploys the Microsoft [!INCLUDE[btsVStudioNoVersion](../includes/btsvstudionoversion-md.md)] projects for this sample.</span></span>  
  
   > [!NOTE]
   >  <span data-ttu-id="54d00-147">このサンプルを実行する前に、ビルドと初期化のプロセス中に [!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)] でエラーが報告されていないことを確認する必要があります。</span><span class="sxs-lookup"><span data-stu-id="54d00-147">You should confirm that [!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)] did not report any errors during the build and initialization process before attempting to run this sample.</span></span>  
   > 
   > [!NOTE]
   >  <span data-ttu-id="54d00-148">開き、Setup.bat ファイルを実行することがなくこのサンプルでは、プロジェクトをビルドする場合は、まず、.NET Framework の厳密名ユーティリティ (sn.exe) を使用して厳密な名前キーのペアを作成する必要があります。</span><span class="sxs-lookup"><span data-stu-id="54d00-148">If you choose to open and build the projects in this sample without running the file Setup.bat, you must first create a strong name key pair using the .NET Framework Strong Name utility (sn.exe).</span></span> <span data-ttu-id="54d00-149">このキー ペアは、生成されたアセンブリの署名に使用します。</span><span class="sxs-lookup"><span data-stu-id="54d00-149">Use this key pair to sign the resulting assemblies.</span></span>  
   > 
   > [!NOTE]
   >  <span data-ttu-id="54d00-150">Setup.bat によって行われた変更を元に戻すには、Cleanup.bat を実行します。</span><span class="sxs-lookup"><span data-stu-id="54d00-150">To undo changes made by Setup.bat, run Cleanup.bat.</span></span> <span data-ttu-id="54d00-151">Setup.bat を 2 回目に実行する場合は、その前に Cleanup.bat を実行してください。</span><span class="sxs-lookup"><span data-stu-id="54d00-151">You must run Cleanup.bat before running Setup.bat a second time.</span></span>  
  
## <a name="running-this-sample"></a><span data-ttu-id="54d00-152">このサンプルの実行</span><span class="sxs-lookup"><span data-stu-id="54d00-152">Running This Sample</span></span>  
 <span data-ttu-id="54d00-153">Business Rules こんにちは World1 サンプルを実行するのにには、次の手順を使用します。</span><span class="sxs-lookup"><span data-stu-id="54d00-153">Use the following procedure to run the Business Rules Hello World1 sample.</span></span>  
  
#### <a name="to-run-this-sample"></a><span data-ttu-id="54d00-154">このサンプルを実行するには</span><span class="sxs-lookup"><span data-stu-id="54d00-154">To run this sample</span></span>  
  
1. <span data-ttu-id="54d00-155">コマンド ウィンドウで、次のフォルダーに移動します。</span><span class="sxs-lookup"><span data-stu-id="54d00-155">In a command window, navigate to the following folder:</span></span>  
  
    <span data-ttu-id="54d00-156">\<*パスのサンプル*\>\Business Rules\Business こんにちは World1\bin\Debug\ のルール</span><span class="sxs-lookup"><span data-stu-id="54d00-156">\<*Samples Path*\>\Business Rules\Business Rules Hello World1\bin\Debug\\</span></span>  
  
2. <span data-ttu-id="54d00-157">コマンド ウィンドウで (BusinessRulesHelloWorld1.exe)、このサンプルの実行可能ファイルの名前を入力し、ENTER キーを押します。</span><span class="sxs-lookup"><span data-stu-id="54d00-157">In the command window, type the name of the executable file for this sample (BusinessRulesHelloWorld1.exe), and then press ENTER.</span></span>  
  
   > [!NOTE]
   >  <span data-ttu-id="54d00-158">規則セット ファイル SampleRuleStore.xml このサンプルでの実行中に、 **bin \debug**フォルダー。</span><span class="sxs-lookup"><span data-stu-id="54d00-158">While running, this sample produces the rule set file SampleRuleStore.xml in the **bin\Debug** folder.</span></span> <span data-ttu-id="54d00-159">実行可能ファイルが一時停止したときにすると、完了、ENTER キーを押すを待つことができますを確認するこのファイルの内容。</span><span class="sxs-lookup"><span data-stu-id="54d00-159">When the executable pauses, waiting for you to press ENTER to finish, you can examine the contents of this file.</span></span> <span data-ttu-id="54d00-160">終了する任意のキーを押す前に閉じることに注意してください。</span><span class="sxs-lookup"><span data-stu-id="54d00-160">Remember to close it before pressing any key to finish.</span></span> <span data-ttu-id="54d00-161">それ以外の場合、実行可能ファイルは、サンプルの後続の実行の準備では削除できません可能性があります。</span><span class="sxs-lookup"><span data-stu-id="54d00-161">Otherwise, the executable may not be able to delete it in preparation for subsequent runs of the sample.</span></span>  
  
   <span data-ttu-id="54d00-162">提供されているサンプル入力ファイル SampleDocumentInstance.xml に対して定義されている (1) 1 つの値を持つこのサンプルを実行する場合、作成したルール セットの特性に基づき、 **ID**要素、次の出力が表示されます。</span><span class="sxs-lookup"><span data-stu-id="54d00-162">Based on the nature of the created rule set, if you run this sample with the provided sample input file SampleDocumentInstance.xml, which has a value of one (1) defined for its **ID** element, you will see the following output:</span></span>  
  
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
>  <span data-ttu-id="54d00-163">太字、上記のコードでは両方と、次のコードでは、出力によって生成されたファイルに定義されているサンプル ビジネス オブジェクトに示した出力、 **MySampleLibrary**フォルダーで、ルール セットによって参照されています。</span><span class="sxs-lookup"><span data-stu-id="54d00-163">The output shown in bold, both in the preceding code and in the code that follows, is the output produced by the sample business object, defined by the files in the **MySampleLibrary** folder, which is referenced by the rule set.</span></span>  
  
 <span data-ttu-id="54d00-164">関連付けられている値を変更する場合、 **ID**サンプル入力ファイル内の要素**SampleDocumentInstance.xml**から 1 つ (1) に 2 つ (2)、出力はように変更します。</span><span class="sxs-lookup"><span data-stu-id="54d00-164">If you change the value associated with the **ID** element in the sample input file **SampleDocumentInstance.xml** from one (1) to two (2), the output would change as follows:</span></span>  
  
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
  
 <span data-ttu-id="54d00-165">オブジェクトの場合、出力行は取得されません、 **MySampleBusinessObject**を持つクラス、 **MyValue**プロパティ、に関連付けられている値と一致する値(構築時)に設定**ID**サンプル入力ファイル SampleDocumentInstance.xml 内の要素。</span><span class="sxs-lookup"><span data-stu-id="54d00-165">You will not get an output line for any objects of the **MySampleBusinessObject** class that have their **MyValue** property set to a value (during construction) that matches the value associated with the **ID** element in the sample input file SampleDocumentInstance.xml.</span></span>  
  
## <a name="comments"></a><span data-ttu-id="54d00-166">コメント</span><span class="sxs-lookup"><span data-stu-id="54d00-166">Comments</span></span>  
 <span data-ttu-id="54d00-167">内にプログラムで作成した規則、 **CreateRuleset()** メソッドに示します。</span><span class="sxs-lookup"><span data-stu-id="54d00-167">The rule created programmatically within the **CreateRuleset()** method shows:</span></span>  
  
 <span data-ttu-id="54d00-168">**IF**</span><span class="sxs-lookup"><span data-stu-id="54d00-168">**IF**</span></span>  
  
 <span data-ttu-id="54d00-169">**MySampleBusinessObject.MyValue**の値と等しく、 **ID** XML ドキュメント内の要素。</span><span class="sxs-lookup"><span data-stu-id="54d00-169">**MySampleBusinessObject.MyValue** is not equal to the value of the **ID** element in the XML document.</span></span>  
  
 <span data-ttu-id="54d00-170">**THEN**</span><span class="sxs-lookup"><span data-stu-id="54d00-170">**THEN**</span></span>  
  
 <span data-ttu-id="54d00-171">**MySampleBusinessObject.MySampleMethod(int)** パラメーターを使用して、整数、ハードここでは、定数 5 (5) にコード化されました。</span><span class="sxs-lookup"><span data-stu-id="54d00-171">**MySampleBusinessObject.MySampleMethod(int)** with an integer parameter, hard coded to the constant five (5) in this case.</span></span> <span data-ttu-id="54d00-172">このメソッドが始まる出力行を生成**MySampleBusinessObject Class –-** します。</span><span class="sxs-lookup"><span data-stu-id="54d00-172">This method produces the output lines that begin **MySampleBusinessObject Class –-**.</span></span>  
  
 <span data-ttu-id="54d00-173">このルールは、次に依存します。</span><span class="sxs-lookup"><span data-stu-id="54d00-173">This rule depends on the following:</span></span>  
  
- <span data-ttu-id="54d00-174">A **MySampleBusinessObject**というパブリック プロパティを持つクラス**MyValue**というパブリック メソッドと**MySampleMethod** (整数パラメーターで受け取る)。</span><span class="sxs-lookup"><span data-stu-id="54d00-174">A **MySampleBusinessObject** class with a public property called **MyValue** and a public method called **MySampleMethod** (that takes in an integer parameter).</span></span>  
  
- <span data-ttu-id="54d00-175">含む XML ドキュメントを定義する XML スキーマ定義言語 (XSD) スキーマ、 **ID**要素。</span><span class="sxs-lookup"><span data-stu-id="54d00-175">An XML schema definition language (XSD) schema that defines an XML document that contains an **ID** element.</span></span>  
  
  <span data-ttu-id="54d00-176">クラスと、スキーマの観点から規則を定義するが、実行中に、関連するクラスのオブジェクトのインスタンスと、適切なスキーマのドキュメント インスタンスが必要です。</span><span class="sxs-lookup"><span data-stu-id="54d00-176">You define rules in terms of classes and schemas, but during execution, object instances of the relevant classes and document instances of the relevant schemas are required.</span></span> <span data-ttu-id="54d00-177">これらの実行時インスタンス (ファクトと呼ばれます) に対してルールを評価します。</span><span class="sxs-lookup"><span data-stu-id="54d00-177">You evaluate the rules against these run-time instances (known as facts).</span></span> <span data-ttu-id="54d00-178">このサンプルでは、ファクトはの複数のインスタンス、 **MySampleBusinessObject**に別の値を使用して構築されているオブジェクト、 **MyValue**プロパティ、および定義済みのスキーマの単一の XML インスタンス値を格納している、 **ID**要素。</span><span class="sxs-lookup"><span data-stu-id="54d00-178">In this sample, the facts are multiple instances of the **MySampleBusinessObject** object, constructed with different values for their **MyValue** property, and a single XML instance of the defined schema that contains a value for the **ID** element.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="54d00-179">参照</span><span class="sxs-lookup"><span data-stu-id="54d00-179">See Also</span></span>  
 [<span data-ttu-id="54d00-180">ビジネス ルール (BizTalk Server サンプル フォルダー)</span><span class="sxs-lookup"><span data-stu-id="54d00-180">Business Rules (BizTalk Server Samples Folder)</span></span>](../core/business-rules-biztalk-server-samples-folder.md)