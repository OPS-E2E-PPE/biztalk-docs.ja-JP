---
title: Business Rules こんにちは World2 (BizTalk Server サンプル) |Microsoft Docs
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
ms.assetid: 2a88a2a0-8cb6-4373-8441-0ab04345a477
caps.latest.revision: 21
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: 6ccc78579c9febfa93b489d72c40ccb603bed92a
ms.sourcegitcommit: 266308ec5c6a9d8d80ff298ee6051b4843c5d626
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 06/27/2018
ms.locfileid: "36972811"
---
# <a name="business-rules-hello-world2-biztalk-server-sample"></a><span data-ttu-id="d86a6-102">Business Rules こんにちは World2 (BizTalk Server サンプル)</span><span class="sxs-lookup"><span data-stu-id="d86a6-102">Business Rules Hello World2 (BizTalk Server Sample)</span></span>
<span data-ttu-id="d86a6-103">Business Rules こんにちは World2 サンプルを説明 Business Rules こんにちは World1 サンプルを拡張する方法のバージョンに次のように公開、および共有 SQL ルール ストア、およびポリシーを使用して、実行する方法に設定 XML 規則を展開、**ポリシー**オブジェクトビジネス ルール フレームワークによって提供されます。</span><span class="sxs-lookup"><span data-stu-id="d86a6-103">The Business Rules Hello World2 sample extends the Business Rules Hello World1 sample by demonstrating how to version, publish, and deploy the XML rule set to the shared SQL rule store, and how to run the policy using the **Policy** object provided by the Business Rules Framework.</span></span> <span data-ttu-id="d86a6-104">また、実行中のポリシーを動的に更新する方法についても示します。</span><span class="sxs-lookup"><span data-stu-id="d86a6-104">The sample also demonstrates dynamic policy updates in action.</span></span>  
  
> [!NOTE]
>  <span data-ttu-id="d86a6-105">このサンプルでは、製品のインストール時に、ルール エンジン更新サービスおよびビジネス ルール コンポーネントがインストールされている ([追加ソフトウェア] ノードの下) ことを前提としています。</span><span class="sxs-lookup"><span data-stu-id="d86a6-105">This sample assumes that the user has installed the Rule Engine Update Service and Business Rules Components (located under the "Additional Software" node) during installation of the product.</span></span>  
  
> [!NOTE]
>  <span data-ttu-id="d86a6-106">使用する**ポリシー**をスタンドアロン アプリケーションにルール エンジンを統合するオブジェクト。</span><span class="sxs-lookup"><span data-stu-id="d86a6-106">You use **Policy** objects to integrate the rule engine into any stand-alone application.</span></span> <span data-ttu-id="d86a6-107">**ポリシー**オブジェクトの抽象化を通じて複数のルール エンジン インスタンスの管理には、規則セットの取得し、共有 SQL ストアからインスタンス化し、ポリシーの更新が取得され、ホストに発行アプリケーション。</span><span class="sxs-lookup"><span data-stu-id="d86a6-107">The **Policy** object is the abstraction through which multiple rule engine instances are managed, rule sets are retrieved and instantiated from the shared SQL store, and updates to the policies are retrieved and published to the hosting application.</span></span>  
  
 <span data-ttu-id="d86a6-108">このサンプルでは、によって構築されたファクトを参照してください、ルール セットの定義、およびサンプルについての基本的な[Business Rules こんにちは World1](../core/business-rules-hello-world1-biztalk-server-sample.md)します。</span><span class="sxs-lookup"><span data-stu-id="d86a6-108">For basic information about the rule set defined, and sample facts constructed by this sample, see [Business Rules Hello World1](../core/business-rules-hello-world1-biztalk-server-sample.md).</span></span>  
  
## <a name="what-this-sample-does"></a><span data-ttu-id="d86a6-109">このサンプルの処理</span><span class="sxs-lookup"><span data-stu-id="d86a6-109">What This Sample Does</span></span>  
 <span data-ttu-id="d86a6-110">このサンプルでは、次の一連の手順を実行する実行可能ファイルを作成します。</span><span class="sxs-lookup"><span data-stu-id="d86a6-110">This sample creates an executable that performs the following sequence of steps:</span></span>  
  
1.  <span data-ttu-id="d86a6-111">メソッドを呼び出して**CreateRuleset** 「解説」セクションで説明されている設定ルールを作成しますします。</span><span class="sxs-lookup"><span data-stu-id="d86a6-111">Calls the method **CreateRuleset** to build the rule set described in the Remarks section.</span></span>  
  
2.  <span data-ttu-id="d86a6-112">メソッドを呼び出して**SaveToFile**を示すファイルへのルール セットを保存します。</span><span class="sxs-lookup"><span data-stu-id="d86a6-112">Calls the method **SaveToFile** to demonstrate saving a rule set to a file.</span></span>  
  
3.  <span data-ttu-id="d86a6-113">メソッドを呼び出して**LoadFromFile**を読み込み、ファイルからルール セットを示すためにします。</span><span class="sxs-lookup"><span data-stu-id="d86a6-113">Calls the method **LoadFromFile** to demonstrate loading a rule set from a file.</span></span>  
  
4.  <span data-ttu-id="d86a6-114">ルール セットを共有 SQL ルール ストアに展開します。</span><span class="sxs-lookup"><span data-stu-id="d86a6-114">Deploys the rule set to a shared SQL rule store.</span></span>  
  
5.  <span data-ttu-id="d86a6-115">ルールを使用してセットの実行、**ポリシー**オブジェクト、および Business Rules こんにちは World1 で使用されるサンプル ファクトの同じセットを使用してサンプルします。</span><span class="sxs-lookup"><span data-stu-id="d86a6-115">Runs the rule set by using a **Policy** object, and by using the same set of sample facts used in the Business Rules Hello World1 sample.</span></span>  
  
6.  <span data-ttu-id="d86a6-116">一時停止し、ファイルの設定、ルールを変更することを有効にする**SampleRuleStore.xml**特定の方法でします。</span><span class="sxs-lookup"><span data-stu-id="d86a6-116">Pauses, enabling you to modify the rule set file **SampleRuleStore.xml** in a specific way.</span></span>  
  
7.  <span data-ttu-id="d86a6-117">ルール セットを使用して再度の実行、**ポリシー**オブジェクト、変ルールは、設定し、もう一度、Business Rules こんにちは World1 で使用されるサンプル ファクトの同じセットのサンプルです。</span><span class="sxs-lookup"><span data-stu-id="d86a6-117">Runs the rule set again using a **Policy** object, the now modified rule set, and again with the same set of sample facts used in the Business Rules Hello World1 sample.</span></span>  
  
8.  <span data-ttu-id="d86a6-118">後でこのサンプルを実行するための準備として、ルール セット ファイルおよび展開されたルール セット レコードを削除して、クリーンアップします。</span><span class="sxs-lookup"><span data-stu-id="d86a6-118">Cleans up by deleting the rule set file and the deployed rule set records in preparation for subsequent running of the sample.</span></span>  
  
> [!NOTE]
>  <span data-ttu-id="d86a6-119">この SDK のすべてのサンプルに関する重要な情報は、次を参照してください。[サンプル](../core/samples-in-the-sdk.md)します。</span><span class="sxs-lookup"><span data-stu-id="d86a6-119">For important information about all samples in this SDK, see [Samples](../core/samples-in-the-sdk.md).</span></span>  
  
## <a name="where-to-find-this-sample"></a><span data-ttu-id="d86a6-120">このサンプルの場所</span><span class="sxs-lookup"><span data-stu-id="d86a6-120">Where to Find This Sample</span></span>  
 <span data-ttu-id="d86a6-121">*\<パスのサンプル\>* \Business Rules\Business こんにちは World2\ のルール</span><span class="sxs-lookup"><span data-stu-id="d86a6-121">*\<Samples Path\>* \Business Rules\Business Rules Hello World2\\</span></span>  
  
 <span data-ttu-id="d86a6-122">次の表は、このサンプルのファイルとその目的を示しています。</span><span class="sxs-lookup"><span data-stu-id="d86a6-122">The following table shows the files in this sample and describes their purpose.</span></span>  
  
|<span data-ttu-id="d86a6-123">ファイル</span><span class="sxs-lookup"><span data-stu-id="d86a6-123">File(s)</span></span>|<span data-ttu-id="d86a6-124">説明</span><span class="sxs-lookup"><span data-stu-id="d86a6-124">Description</span></span>|  
|---------------|-----------------|  
|<span data-ttu-id="d86a6-125">App.ico、AssemblyInfo.cs、BusinessRulesHelloWorld2.csproj、および BusinessRulesHelloWorld2.sln</span><span class="sxs-lookup"><span data-stu-id="d86a6-125">App.ico, AssemblyInfo.cs, BusinessRulesHelloWorld2.csproj, BusinessRulesHelloWorld2.sln</span></span>|<span data-ttu-id="d86a6-126">このサンプルで、ルール セットの作成、保存、ロード、展開、実行を行う部分で使用するプロジェクト ファイル、ソリューション ファイル、その他の関連ファイルです。</span><span class="sxs-lookup"><span data-stu-id="d86a6-126">Project, solution, and related files for the portion of this sample that creates, saves, loads, deploys, and executes a rule set.</span></span>|  
|<span data-ttu-id="d86a6-127">HelloWorld2.cs</span><span class="sxs-lookup"><span data-stu-id="d86a6-127">HelloWorld2.cs</span></span>|<span data-ttu-id="d86a6-128">方法を示すルールを作成するメソッドを含む visual c# ファイルの設定、ルール セット ファイルからのルール セットを読み込み、ファイルの保存ルール セットの展開共有の Microsoft SQL Server ルール ストアにおよびによるセットのルールを実行し、**ポリシー**オブジェクト。</span><span class="sxs-lookup"><span data-stu-id="d86a6-128">Visual C# file that contains methods to demonstrate creating a rule set, saving a rule set to a file, loading a rule set from a file, deploying the rule set to a shared Microsoft SQL Server rule store, and then running the rule set by using a **Policy** object.</span></span>|  
|<span data-ttu-id="d86a6-129">Cleanup.bat</span><span class="sxs-lookup"><span data-stu-id="d86a6-129">Cleanup.bat</span></span>|<span data-ttu-id="d86a6-130">アセンブリを展開解除し、グローバル アセンブリ キャッシュ (GAC) から削除するために使用されます。</span><span class="sxs-lookup"><span data-stu-id="d86a6-130">Used to undeploy assemblies and remove them from the global assembly cache (GAC).</span></span> <span data-ttu-id="d86a6-131">送信ポートと受信ポートが削除されます。</span><span class="sxs-lookup"><span data-stu-id="d86a6-131">Removes send and receive ports.</span></span> <span data-ttu-id="d86a6-132">必要に応じて、Microsoft インターネット インフォメーション サービス (IIS) の仮想ディレクトリが削除されます。</span><span class="sxs-lookup"><span data-stu-id="d86a6-132">Removes Microsoft Internet Information Services (IIS) virtual directories as needed.</span></span>|  
|<span data-ttu-id="d86a6-133">SampleDocumentInstance.xml</span><span class="sxs-lookup"><span data-stu-id="d86a6-133">SampleDocumentInstance.xml</span></span>|<span data-ttu-id="d86a6-134">ファイル SampleSchema.xsd で定義されているスキーマに準拠したサンプル入力ファイルです。</span><span class="sxs-lookup"><span data-stu-id="d86a6-134">Sample input file that conforms to the schema defined in the file SampleSchema.xsd.</span></span>|  
|<span data-ttu-id="d86a6-135">SampleSchema.xsd</span><span class="sxs-lookup"><span data-stu-id="d86a6-135">SampleSchema.xsd</span></span>|<span data-ttu-id="d86a6-136">簡潔なスキーマを定義したスキーマ ファイルで、Visual C# ファイル Class1.cs で作成されたルール セットから参照される要素が含まれます。</span><span class="sxs-lookup"><span data-stu-id="d86a6-136">Schema file that defines a simple schema with an element referenced by the rule set created in the Visual C# file Class1.cs.</span></span>|  
|<span data-ttu-id="d86a6-137">Setup.bat</span><span class="sxs-lookup"><span data-stu-id="d86a6-137">Setup.bat</span></span>|<span data-ttu-id="d86a6-138">このサンプルをビルドおよび初期化するために使用されます。</span><span class="sxs-lookup"><span data-stu-id="d86a6-138">Used to build and initialize this sample.</span></span>|  
|<span data-ttu-id="d86a6-139">\HelloWorld2Library フォルダーに含まれるファイル: </span><span class="sxs-lookup"><span data-stu-id="d86a6-139">In the \HelloWorld2Library folder:</span></span><br /><br /> <span data-ttu-id="d86a6-140">AssemblyInfo.cs、HelloWorld2Library.csproj、HelloWorld2Library.sln</span><span class="sxs-lookup"><span data-stu-id="d86a6-140">AssemblyInfo.cs, HelloWorld2Library.csproj, HelloWorld2Library.sln</span></span>|<span data-ttu-id="d86a6-141">このサンプルで、作成したルール セットから参照されるオブジェクトを定義するクラスを提供する部分で使用するプロジェクト ファイル、ソリューション ファイル、その他の関連ファイルです。</span><span class="sxs-lookup"><span data-stu-id="d86a6-141">Project, solution, and related files for the portion of this sample that provides the class that defines the objects referenced by the created rule set.</span></span>|  
|<span data-ttu-id="d86a6-142">\HelloWorld2Library フォルダーに含まれるファイル: </span><span class="sxs-lookup"><span data-stu-id="d86a6-142">In the \HelloWorld2Library folder:</span></span><br /><br /> <span data-ttu-id="d86a6-143">HelloWorld2LibraryClass.cs</span><span class="sxs-lookup"><span data-stu-id="d86a6-143">HelloWorld2LibraryClass.cs</span></span>|<span data-ttu-id="d86a6-144">参照されているプロパティを含む visual c# ファイル、**場合**、作成した規則で呼び出されるメソッドの部分、**し**作成した規則の一部です。</span><span class="sxs-lookup"><span data-stu-id="d86a6-144">Visual C# file that contains the property referenced in the **IF** portion of the created rule, and the method that may be called in the **THEN** portion of the created rule.</span></span>|  
  
### <a name="to-build-and-initialize-the-business-rules-hello-world2-sample"></a><span data-ttu-id="d86a6-145">Business Rules Hello World2 サンプルをビルドして初期化するには</span><span class="sxs-lookup"><span data-stu-id="d86a6-145">To build and initialize the Business Rules Hello World2 sample</span></span>  
  
1. <span data-ttu-id="d86a6-146">コマンド ウィンドウで、次のフォルダーに移動します。</span><span class="sxs-lookup"><span data-stu-id="d86a6-146">In a command window, navigate to the following folder:</span></span>  
  
    <span data-ttu-id="d86a6-147">*\<パスのサンプル\>* \Business Rules\Business こんにちは World2\ のルール</span><span class="sxs-lookup"><span data-stu-id="d86a6-147">*\<Samples Path\>* \Business Rules\Business Rules Hello World2\\</span></span>  
  
2. <span data-ttu-id="d86a6-148">ファイルは、次の操作を実行します。 Setup.bat を実行します。</span><span class="sxs-lookup"><span data-stu-id="d86a6-148">Run the file Setup.bat, which performs the following actions:</span></span>  
  
   - <span data-ttu-id="d86a6-149">このサンプル用に [!INCLUDE[btsVStudioNoVersion](../includes/btsvstudionoversion-md.md)] プロジェクトをコンパイルし、展開します。</span><span class="sxs-lookup"><span data-stu-id="d86a6-149">Compiles and deploys the [!INCLUDE[btsVStudioNoVersion](../includes/btsvstudionoversion-md.md)] projects for this sample.</span></span>  
  
   > [!NOTE]
   >  <span data-ttu-id="d86a6-150">このサンプルを実行する前に、ビルドと初期化のプロセス中に [!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)] でエラーが報告されていないことを確認する必要があります。</span><span class="sxs-lookup"><span data-stu-id="d86a6-150">You should confirm that [!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)] did not report any errors during the build and initialization process before attempting to run this sample.</span></span>  
   > 
   > [!NOTE]
   >  <span data-ttu-id="d86a6-151">開き、Setup.bat ファイルを実行することがなくこのサンプルでは、プロジェクトをビルドする場合は、まず、.NET Framework の厳密名ユーティリティ (sn.exe) を使用して厳密な名前キーのペアを作成する必要があります。</span><span class="sxs-lookup"><span data-stu-id="d86a6-151">If you choose to open and build the projects in this sample without running the file Setup.bat, you must first create a strong name key pair using the .NET Framework Strong Name utility (sn.exe).</span></span> <span data-ttu-id="d86a6-152">このキー ペアは、生成されたアセンブリの署名に使用します。</span><span class="sxs-lookup"><span data-stu-id="d86a6-152">Use this key pair to sign the resulting assemblies.</span></span>  
   > 
   > [!NOTE]
   >  <span data-ttu-id="d86a6-153">Setup.bat によって行われた変更を元に戻すには、Cleanup.bat を実行します。</span><span class="sxs-lookup"><span data-stu-id="d86a6-153">To undo changes made by Setup.bat, run Cleanup.bat.</span></span> <span data-ttu-id="d86a6-154">Setup.bat を 2 回目に実行する場合は、その前に Cleanup.bat を実行してください。</span><span class="sxs-lookup"><span data-stu-id="d86a6-154">You must run Cleanup.bat before running Setup.bat a second time.</span></span>  
  
### <a name="to-run-the-business-rules-hello-world2-sample"></a><span data-ttu-id="d86a6-155">Business Rules Hello World2 サンプルを実行するには</span><span class="sxs-lookup"><span data-stu-id="d86a6-155">To run the Business Rules Hello World2 sample</span></span>  
  
1.  <span data-ttu-id="d86a6-156">コマンド ウィンドウで、次のフォルダーに移動します。</span><span class="sxs-lookup"><span data-stu-id="d86a6-156">In a command window, navigate to the following folder:</span></span>  
  
     <span data-ttu-id="d86a6-157">*\<パスのサンプル\>* \Business Rules\Business こんにちは World2\bin\Debug\ のルール</span><span class="sxs-lookup"><span data-stu-id="d86a6-157">*\<Samples Path\>* \Business Rules\Business Rules Hello World2\bin\Debug\\</span></span>  
  
2.  <span data-ttu-id="d86a6-158">コマンド ウィンドウで、このサンプルのファイルの名前を入力します (**BusinessRulesHelloWorld2.exe**)、し、ENTER キーを押します。</span><span class="sxs-lookup"><span data-stu-id="d86a6-158">In the command window, type the name of the file for this sample (**BusinessRulesHelloWorld2.exe**), and then press ENTER.</span></span>  
  
## <a name="hello-world2-output"></a><span data-ttu-id="d86a6-159">Hello World2 の出力</span><span class="sxs-lookup"><span data-stu-id="d86a6-159">Hello World2 Output</span></span>  
 <span data-ttu-id="d86a6-160">[コメント] セクションで説明されている、作成したルール セットの特性に基づいて[Business Rules こんにちは World1](../core/business-rules-hello-world1-biztalk-server-sample.md)で提供されているサンプル入力ファイル SampleDocumentInstance.xml 定義 (1) 1 つの値を持つこのサンプルを実行する場合は、その**ID**要素では、次の出力が表示されます。</span><span class="sxs-lookup"><span data-stu-id="d86a6-160">Based on the nature of the created rule set, described in the Comments section of [Business Rules Hello World1](../core/business-rules-hello-world1-biztalk-server-sample.md), if you run this sample with the provided sample input file SampleDocumentInstance.xml, which has a value of one (1) defined for its **ID** element, you will see the following output:</span></span>  
  
```  
Creating a new ruleset ...  
Saving ruleset to SampleRuleStore.xml ...  
Loading ruleset ...  
Deploying the ruleset ...  
Sleeping for 60 seconds (so that the deployed ruleset becomes effective) ...  
Grabbing the policy ...  
Executing the policy...  
MySampleBusinessObject Class -- MySampleMethod executed for object 2 with parameter 5  
MySampleBusinessObject Class -- MySampleMethod executed for object 3 with parameter 5  
The major version of the policy was: 1  
The minor version of the policy was: 0  
Press the ENTER to continue after updating the policy...  
```  
  
> [!NOTE]
>  <span data-ttu-id="d86a6-161">太字で表示される出力がファイルに定義されているサンプル ビジネス オブジェクトによって生成される出力、 **HelloWorld2Library**ルール セットから参照するフォルダー。</span><span class="sxs-lookup"><span data-stu-id="d86a6-161">The output shown in bold is the output produced by the sample business object, defined by the files in the **HelloWorld2Library** folder that the rule set references.</span></span> <span data-ttu-id="d86a6-162">この時点で、アプリケーションはこの状態で待機します。</span><span class="sxs-lookup"><span data-stu-id="d86a6-162">At this point, the application is left waiting in this state.</span></span>  
  
 <span data-ttu-id="d86a6-163">次のサンプルの実行部分では、ビジネス ルール作成ツールを使用してビジネス ルールを変更します。</span><span class="sxs-lookup"><span data-stu-id="d86a6-163">The next part of running the sample involves using the Business Rules Composer to change the business rules.</span></span>  
  
#### <a name="to-use-the-business-rules-composer-to-change-the-business-rules"></a><span data-ttu-id="d86a6-164">ビジネス ルール作成ツールを使用してビジネス ルールを変更するには</span><span class="sxs-lookup"><span data-stu-id="d86a6-164">To use the Business Rules Composer to change the business rules</span></span>  
  
1. <span data-ttu-id="d86a6-165">ビジネス ルール作成ツールを開くには、次のようにクリックします。**開始**、 をクリック**すべてのプログラム**、 をクリック[!INCLUDE[btsBizTalkServerStartMenuItemui](../includes/btsbiztalkserverstartmenuitemui-md.md)]、 をクリックし、**ビジネス ルール作成ツール**。</span><span class="sxs-lookup"><span data-stu-id="d86a6-165">To open the Business Rules Composer, click **Start**, click **All Programs**, click [!INCLUDE[btsBizTalkServerStartMenuItemui](../includes/btsbiztalkserverstartmenuitemui-md.md)], and then click **Business Rules Composer**.</span></span>  
  
   > [!NOTE]
   >  <span data-ttu-id="d86a6-166">ユーザー アカウント制御 (UAC) をサポートするシステムでは、管理者特権を使用してこのツールを実行することが必要な場合があります。</span><span class="sxs-lookup"><span data-stu-id="d86a6-166">On a system that supports User Account Control (UAC), you may need to run the tool with Administrative privileges.</span></span> <span data-ttu-id="d86a6-167">これを行うには、アプリケーションを右クリックし、**管理者として実行**します。</span><span class="sxs-lookup"><span data-stu-id="d86a6-167">To do this, right-click the application, and then select **Run as administrator**.</span></span>  
  
2. <span data-ttu-id="d86a6-168">SQL Server を実行するコンピューターで、SQL Server ダイアログ ボックスが表示されたら、クリックして**OK**ルール ストアに接続します。</span><span class="sxs-lookup"><span data-stu-id="d86a6-168">If a SQL Server dialog box appears on the computer running SQL Server, click **OK** to connect to the rule store.</span></span>  
  
3. <span data-ttu-id="d86a6-169">**ポリシー エクスプ ローラー**下の**SampleRuleSet**ノード、ノードを右クリックして**バージョン 1.0-展開済み**、 をクリックし、**コピー**します。</span><span class="sxs-lookup"><span data-stu-id="d86a6-169">In **Policy Explorer**, below the **SampleRuleSet** node, right-click the node **Version 1.0 – Deployed**, and then click **Copy**.</span></span>  
  
4. <span data-ttu-id="d86a6-170">右クリックして**SampleRuleSet**、 をクリックし、**貼り付け (ポリシーのバージョン)** します。</span><span class="sxs-lookup"><span data-stu-id="d86a6-170">Right-click **SampleRuleSet**, and then click **Paste (Policy Version)**.</span></span>  
  
5. <span data-ttu-id="d86a6-171">ルール条件とアクションは、必要に応じて変更できます。</span><span class="sxs-lookup"><span data-stu-id="d86a6-171">You can change the rule condition and action to meet your needs.</span></span> <span data-ttu-id="d86a6-172">この手順では、次のようにクリックします。 **rule1**で**バージョン 1.1 (未保存)** します。</span><span class="sxs-lookup"><span data-stu-id="d86a6-172">For this procedure, click **rule1** in **Version 1.1 (not saved)**.</span></span> <span data-ttu-id="d86a6-173">右側のウィンドウで右クリック**条件**、 をクリックし、**論理否定の追加**します。</span><span class="sxs-lookup"><span data-stu-id="d86a6-173">In the right pane, right-click **Conditions**, and then click **Add Logical NOT**.</span></span> <span data-ttu-id="d86a6-174">追加、**論理否定**操作を**等しく**述語を使用することは、**と等しい**述語。</span><span class="sxs-lookup"><span data-stu-id="d86a6-174">Adding a **Logical NOT** operation to **Not Equal** to predicate is equivalent to using an **Equal** predicate.</span></span>  
  
6. <span data-ttu-id="d86a6-175">ノードを右クリックして**バージョン 1.1 (未保存)**、 をクリックし、**保存**します。</span><span class="sxs-lookup"><span data-stu-id="d86a6-175">Right-click the node **Version 1.1(not saved)**, and then click **Save**.</span></span> <span data-ttu-id="d86a6-176">ここでもを右クリックし、をクリックし、**発行**します。</span><span class="sxs-lookup"><span data-stu-id="d86a6-176">Right-click again, and then click **Publish**.</span></span> <span data-ttu-id="d86a6-177">3 番目の時間を右クリックし、をクリックして**デプロイ**します。</span><span class="sxs-lookup"><span data-stu-id="d86a6-177">Right-click a third time and click **Deploy**.</span></span>  
  
7. <span data-ttu-id="d86a6-178">一時停止しているコマンド ウィンドウ (ポリシーの更新後に任意のキーを押して続行するよう要求)、任意のキーを押します。</span><span class="sxs-lookup"><span data-stu-id="d86a6-178">In the paused command window asking you to press any key to continue after updating the policy, press any key.</span></span>  
  
   <span data-ttu-id="d86a6-179">論理否定を追加してルールを変更したとすると、実行可能ファイル BusinessRulesHelloWorld2.exe からの出力は、次のように継続されます。</span><span class="sxs-lookup"><span data-stu-id="d86a6-179">Output (assuming you changed the rule by adding a logical Not) from the executable file BusinessRulesHelloWorld2.exe continues as follows:</span></span>  
  
```  
Sleeping for 60 seconds (so that the deployed ruleset becomes effective) ...         
Grabbing the policy ...         
Executing the policy...         
MySampleBusinessObject Class -- MySampleMethod executed for object 1 with parameter 5         
The major version of the policy was: 1         
The minor version of the policy was: 1         
Press ENTER to continue after updating the policy...         
```  
  
 <span data-ttu-id="d86a6-180">出力の変更内容を確認します。</span><span class="sxs-lookup"><span data-stu-id="d86a6-180">Notice how the output has changed:</span></span>  
  
-   <span data-ttu-id="d86a6-181">メソッド内の出力行**MySampleMethod**しかここで 1 回は、インスタンスの出力、 **MySampleBusinessObject**クラスを**MyValue**プロパティが 1 に等しい、以前のルールのではなく、 **MyValue**プロパティが 1 と等しくありません。</span><span class="sxs-lookup"><span data-stu-id="d86a6-181">The output line in the method **MySampleMethod** only prints once now, for the instance of the **MySampleBusinessObject** class for which the **MyValue** property is equal to 1, rather than the previous rule of printing when the **MyValue** property is not equal to 1.</span></span>  
  
-   <span data-ttu-id="d86a6-182">ポリシーのマイナー バージョン番号は、1 になりました。</span><span class="sxs-lookup"><span data-stu-id="d86a6-182">The minor version number of the policy is now 1.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="d86a6-183">参照</span><span class="sxs-lookup"><span data-stu-id="d86a6-183">See Also</span></span>  
 [<span data-ttu-id="d86a6-184">ビジネス ルール (BizTalk Server サンプル フォルダー)</span><span class="sxs-lookup"><span data-stu-id="d86a6-184">Business Rules (BizTalk Server Samples Folder)</span></span>](../core/business-rules-biztalk-server-samples-folder.md)