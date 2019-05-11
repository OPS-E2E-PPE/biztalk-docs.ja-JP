---
title: OperationsSamples (BizTalk Server サンプル) |Microsoft Docs
ms.custom: ''
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: ''
ms.suite: ''
ms.tgt_pltfrm: ''
ms.topic: article
ms.assetid: 3c9e3f3e-a570-4edd-aa2e-3f8e2e37c8a0
caps.latest.revision: 6
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: 5101e047c41e12f322639986179b4b87504da75f
ms.sourcegitcommit: 381e83d43796a345488d54b3f7413e11d56ad7be
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 05/07/2019
ms.locfileid: "65262932"
---
# <a name="operationssamples-biztalk-server-sample"></a><span data-ttu-id="0c7b9-102">OperationsSamples (BizTalk Server サンプル)</span><span class="sxs-lookup"><span data-stu-id="0c7b9-102">OperationsSamples (BizTalk Server Sample)</span></span>
<span data-ttu-id="0c7b9-103">OperationsSamples サンプルは、Operations オブジェクト モデルを使用して運用上のアクティビティを実行する方法を示します。</span><span class="sxs-lookup"><span data-stu-id="0c7b9-103">The OperationsSamples sample demonstrates how to perform operational activities using the Operations object model.</span></span>  
  
## <a name="what-this-sample-does"></a><span data-ttu-id="0c7b9-104">このサンプルの処理</span><span class="sxs-lookup"><span data-stu-id="0c7b9-104">What This Sample Does</span></span>  
 <span data-ttu-id="0c7b9-105">このサンプルでは、次の項目を示しています。</span><span class="sxs-lookup"><span data-stu-id="0c7b9-105">This sample demonstrates the following:</span></span>  
  
- <span data-ttu-id="0c7b9-106">追跡プロファイルを使用してアクティビティを使用したオーケストレーションにコメントをする方法。</span><span class="sxs-lookup"><span data-stu-id="0c7b9-106">How to use a tracking profile to comment an orchestration with activities.</span></span>  
  
- <span data-ttu-id="0c7b9-107">BAM 追跡データベースを使用して、アクティビティ ID を検索し、関連するオーケストレーション インスタンスを検索する ID を使用する方法。</span><span class="sxs-lookup"><span data-stu-id="0c7b9-107">How to use the BAM tracking database to find an activity ID and then use the ID to find a related orchestration instance.</span></span>  
  
- <span data-ttu-id="0c7b9-108">検索して、メッセージ フローを使用して操作する方法、 **MessageFlow**クラスおよびその他の Operations オブジェクト モデル クラスと Api。</span><span class="sxs-lookup"><span data-stu-id="0c7b9-108">How to find and work with message flows by using the **MessageFlow** class and other Operations object model classes and APIs.</span></span>  
  
- <span data-ttu-id="0c7b9-109">ポートにアクセスする方法、メッセージ、およびから派生したクラスを使用して他のインスタンス、**インスタンス**クラス。</span><span class="sxs-lookup"><span data-stu-id="0c7b9-109">How to access ports, messages, and other instances by using classes derived from the **Instance** class.</span></span>  
  
  <span data-ttu-id="0c7b9-110">このサンプルには、多くの有益なヘルパー クラスと上記の操作をサポートするメソッドが含まれています。</span><span class="sxs-lookup"><span data-stu-id="0c7b9-110">The sample contains many useful helper classes and methods to support the operations above.</span></span> <span data-ttu-id="0c7b9-111">これらおよびその他のコードの特長については、次のセクションで説明します。</span><span class="sxs-lookup"><span data-stu-id="0c7b9-111">These and other code highlights are discussed in the next section.</span></span>  
  
## <a name="how-this-sample-is-designed-and-why"></a><span data-ttu-id="0c7b9-112">このサンプルのデザイン方法とその理由</span><span class="sxs-lookup"><span data-stu-id="0c7b9-112">How This Sample Is Designed and Why</span></span>  
 <span data-ttu-id="0c7b9-113">このサンプルと公開されている BAM 追跡データベースを照会する方法について説明をいくつかの主要なクラスと、Operations オブジェクト モデル内のメソッドを示すために設計されています。</span><span class="sxs-lookup"><span data-stu-id="0c7b9-113">This sample is designed to demonstrate several of the key classes and methods in the Operations object model and to show how to query the publicly available BAM tracking database.</span></span>  
  
 <span data-ttu-id="0c7b9-114">Operations オブジェクト モデルには、メッセージと BizTalk Server 内では、他のインスタンスを操作する機能を提供するクラスが含まれています。</span><span class="sxs-lookup"><span data-stu-id="0c7b9-114">The Operations object model contains classes that provide the ability to manipulate messages and other instances within BizTalk Server.</span></span>  
  
### <a name="using-a-bam-activity-id"></a><span data-ttu-id="0c7b9-115">BAM アクティビティ ID を使用します。</span><span class="sxs-lookup"><span data-stu-id="0c7b9-115">Using a BAM Activity ID</span></span>  
 <span data-ttu-id="0c7b9-116">このサンプルでは、BAM と対話する方法と追跡データベースに公開されているビューを使用して、ビジネス データを使用して、メッセージ ボックスのライブ メッセージを検索する方法を示します。</span><span class="sxs-lookup"><span data-stu-id="0c7b9-116">This sample shows how to interact with BAM and how to use the publicly available views in the tracking database to locate a live message in the message box by using business data.</span></span> <span data-ttu-id="0c7b9-117">このサンプルではこの注文書番号に対応するオーケストレーション ID を取得することによって。</span><span class="sxs-lookup"><span data-stu-id="0c7b9-117">The sample does this by retrieving an orchestration ID corresponding to a purchase order number.</span></span> <span data-ttu-id="0c7b9-118">このタスクを成功させるには、次に行う必要があります。</span><span class="sxs-lookup"><span data-stu-id="0c7b9-118">For this task to succeed, it must do the following:</span></span>  
  
1. <span data-ttu-id="0c7b9-119">ビジネス データ (注文書番号) を使用して、アクティビティ ID を検索するには</span><span class="sxs-lookup"><span data-stu-id="0c7b9-119">Use business data (a purchase order number) to find an activity ID.</span></span> <span data-ttu-id="0c7b9-120">この手順では、ビジネス データを追加情報を見つけるために使用する内部の ID にマップします。</span><span class="sxs-lookup"><span data-stu-id="0c7b9-120">This step maps business data to an internal ID that can be used to find additional information.</span></span>  
  
2. <span data-ttu-id="0c7b9-121">アクティビティ ID に関連する BAM 参照を取得します。</span><span class="sxs-lookup"><span data-stu-id="0c7b9-121">Retrieve the BAM references related to the activity ID.</span></span>  
  
3. <span data-ttu-id="0c7b9-122">"BizTalkService"の型であり、オーケストレーションを参照する参照を検索します。</span><span class="sxs-lookup"><span data-stu-id="0c7b9-122">Find a reference that has a type of "BizTalkService" and refers to an orchestration.</span></span> <span data-ttu-id="0c7b9-123">見つかった場合は、そのインスタンス ID を返します</span><span class="sxs-lookup"><span data-stu-id="0c7b9-123">If one is found, return its instance ID.</span></span>  
  
   <span data-ttu-id="0c7b9-124">この機能は、 **BAMWebService.GetOrchestrationID**静的メソッドと、BamManagementService.cs ソース ファイルでクラスとメソッドを含む関連ヘルパー メソッド。</span><span class="sxs-lookup"><span data-stu-id="0c7b9-124">This functionality is provided by the **BAMWebService.GetOrchestrationID** static method and associated helper methods including classes and methods in the BamManagementService.cs source file.</span></span>  
  
### <a name="suspending-terminating-and-resuming-an-instance"></a><span data-ttu-id="0c7b9-125">中断、終了、およびインスタンスの再開</span><span class="sxs-lookup"><span data-stu-id="0c7b9-125">Suspending, Terminating, and Resuming an Instance</span></span>  
 <span data-ttu-id="0c7b9-126">サンプル プログラムが含まれています、 **Samples.OperateOnInstance**メソッドを操作とインスタンス ID を受け取り、インスタンスで指定された操作を実行します。</span><span class="sxs-lookup"><span data-stu-id="0c7b9-126">The sample program includes a **Samples.OperateOnInstance** method that takes an operation and instance ID and performs the specified operation on the instance.</span></span> <span data-ttu-id="0c7b9-127">有効な操作がによって定義されている、 **InstanceOperation**列挙しており、Suspend、Terminate、再開します。</span><span class="sxs-lookup"><span data-stu-id="0c7b9-127">Valid operations are defined by the **InstanceOperation** enumeration and include Suspend, Terminate, and Resume.</span></span> <span data-ttu-id="0c7b9-128">これらの操作は、biztalkoperations のメソッドに直接マップ-**SuspendInstance**、 **TerminateInstance**、および**ResumeInstance**します。</span><span class="sxs-lookup"><span data-stu-id="0c7b9-128">These operations map directly to methods of the BizTalkOperations class—**SuspendInstance**, **TerminateInstance**, and **ResumeInstance**.</span></span>  
  
 <span data-ttu-id="0c7b9-129">メソッドは ArgumentException と SqlException の両方の例外を処理することを確認します。</span><span class="sxs-lookup"><span data-stu-id="0c7b9-129">Notice that the method handles both ArgumentException and SqlException exceptions.</span></span> <span data-ttu-id="0c7b9-130">例外が発生するように注意する必要があります: SqlException を含む、クラスと、Operations オブジェクト モデル内のメソッドを使用する場合。</span><span class="sxs-lookup"><span data-stu-id="0c7b9-130">You must be careful to anticipate exceptions—including SqlException—when working with the classes and methods in the Operations object model.</span></span>  
  
> [!NOTE]
>  <span data-ttu-id="0c7b9-131">多くの操作メソッドには、データベースへのアクセスが必要です。</span><span class="sxs-lookup"><span data-stu-id="0c7b9-131">Many of the Operations methods require access to the database.</span></span> <span data-ttu-id="0c7b9-132">これらのメソッドによってスローされた例外を予測し、適切に処理する必要があります。</span><span class="sxs-lookup"><span data-stu-id="0c7b9-132">You should anticipate the exceptions thrown by these methods and handle them appropriately.</span></span>  
  
### <a name="retrieving-all-live-messages"></a><span data-ttu-id="0c7b9-133">すべてのライブ メッセージを取得します。</span><span class="sxs-lookup"><span data-stu-id="0c7b9-133">Retrieving All Live Messages</span></span>  
 <span data-ttu-id="0c7b9-134">Operations オブジェクト モデルでは、次のコード フラグメントで示すように、簡単に使用可能なライブ メッセージをすべて繰り返します。</span><span class="sxs-lookup"><span data-stu-id="0c7b9-134">The Operations object model makes it straightforward to iterate over all of the available live messages, as shown in the following code fragment:</span></span>  
  
```  
BizTalkOperations _operations = new BizTalkOperations()  
IEnumerable messages = _operations.GetMessages();  
foreach (BizTalkMessage msg in messages)  
…  
```  
  
 <span data-ttu-id="0c7b9-135">OperationsSamples プログラムは、このさらにメッセージ ID とメッセージ部分の数と共にメッセージ型と型を含む、各メッセージに関する情報にアクセスする方法について説明します。</span><span class="sxs-lookup"><span data-stu-id="0c7b9-135">The OperationsSamples program takes this a step further by demonstrating how to access information about each message, including message ID and message type along with the number and types of message parts.</span></span> <span data-ttu-id="0c7b9-136">このコードを変更し、BizTalk Server で使用可能なライブ メッセージの一部またはすべてを反復処理するには、あるシナリオで使用できます。</span><span class="sxs-lookup"><span data-stu-id="0c7b9-136">You can modify this code and use it in scenarios where you have to iterate through many or all of the available live messages in BizTalk Server.</span></span>  
  
> [!NOTE]
>  <span data-ttu-id="0c7b9-137">ある数百または何千ものメッセージの使用可能です。</span><span class="sxs-lookup"><span data-stu-id="0c7b9-137">There may be hundreds or thousands of messages available.</span></span> <span data-ttu-id="0c7b9-138">リスト全体をスキャンすると、パフォーマンスが低下する可能性があります。</span><span class="sxs-lookup"><span data-stu-id="0c7b9-138">Scanning the entire list may adversely affect performance.</span></span>  
  
## <a name="where-to-find-this-sample"></a><span data-ttu-id="0c7b9-139">このサンプルの場所</span><span class="sxs-lookup"><span data-stu-id="0c7b9-139">Where to Find This Sample</span></span>  
 <span data-ttu-id="0c7b9-140">このサンプルは、SDK がある次の場所にあります。</span><span class="sxs-lookup"><span data-stu-id="0c7b9-140">The sample is located in the following SDK location:</span></span>  
  
 <span data-ttu-id="0c7b9-141">\<*Samples Path*\>\Admin\OperationsOM\OperationsSamples\\</span><span class="sxs-lookup"><span data-stu-id="0c7b9-141">\<*Samples Path*\>\Admin\OperationsOM\OperationsSamples\\</span></span>  
  
 <span data-ttu-id="0c7b9-142">次の表は、このサンプルのファイルとその目的を示しています。</span><span class="sxs-lookup"><span data-stu-id="0c7b9-142">The following table shows the files in this sample and describes their purpose.</span></span>  
  
|<span data-ttu-id="0c7b9-143">ファイル</span><span class="sxs-lookup"><span data-stu-id="0c7b9-143">File(s)</span></span>|<span data-ttu-id="0c7b9-144">説明</span><span class="sxs-lookup"><span data-stu-id="0c7b9-144">Description</span></span>|  
|---------------|-----------------|  
|<span data-ttu-id="0c7b9-145">BamManagementService.cs</span><span class="sxs-lookup"><span data-stu-id="0c7b9-145">BamManagementService.cs</span></span>|<span data-ttu-id="0c7b9-146">BAM Web サービスの web プロキシ クラスです。</span><span class="sxs-lookup"><span data-stu-id="0c7b9-146">Web proxy class for the BAM Web service.</span></span>|  
|<span data-ttu-id="0c7b9-147">Cleanup.bat</span><span class="sxs-lookup"><span data-stu-id="0c7b9-147">Cleanup.bat</span></span>|<span data-ttu-id="0c7b9-148">サンプル オーケストレーションを削除し、HelloWorld サンプルを元の状態に戻します。</span><span class="sxs-lookup"><span data-stu-id="0c7b9-148">Removes the sample orchestration and restores the HelloWorld sample to its original state.</span></span>|  
|<span data-ttu-id="0c7b9-149">HelloOrchestration.btt</span><span class="sxs-lookup"><span data-stu-id="0c7b9-149">HelloOrchestration.btt</span></span>|<span data-ttu-id="0c7b9-150">追跡プロファイルが BizTalk イベント ソースを BAM ターゲット アクティビティにマップするために使用します。</span><span class="sxs-lookup"><span data-stu-id="0c7b9-150">Tracking profile used to map BizTalk event sources to BAM target activities.</span></span>|  
|<span data-ttu-id="0c7b9-151">HelloOrchestration.xls</span><span class="sxs-lookup"><span data-stu-id="0c7b9-151">HelloOrchestration.xls</span></span>|<span data-ttu-id="0c7b9-152">BAM 定義スタイル シートです。</span><span class="sxs-lookup"><span data-stu-id="0c7b9-152">BAM definition style sheet.</span></span>|  
|<span data-ttu-id="0c7b9-153">OperationsSamples.cs</span><span class="sxs-lookup"><span data-stu-id="0c7b9-153">OperationsSamples.cs</span></span>|<span data-ttu-id="0c7b9-154">C# ソース ファイルは、Operations オブジェクト モデルのさまざまな側面を説明するコードを格納しています。</span><span class="sxs-lookup"><span data-stu-id="0c7b9-154">C# source file containing code that demonstrates various aspects of the Operations object model.</span></span>|  
|<span data-ttu-id="0c7b9-155">OperationsSamples.csproj、OperationsSamples.sln、AssemblyInfo.cs</span><span class="sxs-lookup"><span data-stu-id="0c7b9-155">OperationsSamples.csproj, OperationsSamples.sln, AssemblyInfo.cs</span></span>|<span data-ttu-id="0c7b9-156">このサンプルのプロジェクト、ソリューション、およびアセンブリ情報ファイルです。</span><span class="sxs-lookup"><span data-stu-id="0c7b9-156">Project, solution, and assembly information files for this sample.</span></span>|  
|<span data-ttu-id="0c7b9-157">Setup.bat</span><span class="sxs-lookup"><span data-stu-id="0c7b9-157">Setup.bat</span></span>|<span data-ttu-id="0c7b9-158">ビルドして HelloWorld オーケストレーション サンプルを変更することでこのサンプルを初期化するために使用します。</span><span class="sxs-lookup"><span data-stu-id="0c7b9-158">Used to build and initialize this sample by modifying the HelloWorld orchestration sample.</span></span> <span data-ttu-id="0c7b9-159">これは、コマンドで、サンプル オーケストレーションのインストール、BAM アクティビティ定義と、追跡プロファイル エディター ファイルが展開、ポートの構成、および受信場所にサンプル ファイルをドロップします。</span><span class="sxs-lookup"><span data-stu-id="0c7b9-159">It installs a sample orchestration, deploys a BAM Activity Definition and a Tracking Profile Editor file, configures ports, and drops a sample file into the receive location.</span></span>|  
  
## <a name="how-to-use-this-sample"></a><span data-ttu-id="0c7b9-160">このサンプルの使用方法</span><span class="sxs-lookup"><span data-stu-id="0c7b9-160">How to Use This Sample</span></span>  
 <span data-ttu-id="0c7b9-161">このサンプルを使用して、Operations オブジェクト モデルで使用可能な機能を試してください。</span><span class="sxs-lookup"><span data-stu-id="0c7b9-161">Use this sample to explore the functionality available in the Operations object model.</span></span> <span data-ttu-id="0c7b9-162">メッセージを異なる方法で操作を検索して既存のルーチンの変更または BizTalk Server 管理コンソールの グループ ハブの一部を複製する新しいコードを追加します。</span><span class="sxs-lookup"><span data-stu-id="0c7b9-162">Modify existing routines to find and work with messages differently or add new code that replicates portions of the Group Hub in the BizTalk Server Management console.</span></span>  
  
 <span data-ttu-id="0c7b9-163">次のタスクのいくつかを検討できます。</span><span class="sxs-lookup"><span data-stu-id="0c7b9-163">You may also consider some of the following tasks:</span></span>  
  
-   <span data-ttu-id="0c7b9-164">カスタム アプリケーションに、グループのハブの最も使用頻度のサブセットをレプリケートするアプリケーションを作成します。</span><span class="sxs-lookup"><span data-stu-id="0c7b9-164">Write an application that replicates the most-used subset of the Group Hub into a custom application.</span></span>  
  
-   <span data-ttu-id="0c7b9-165">ポートを作成し、新しい取引を使ってのテスト メッセージを送信するカスタム プロビジョニング アプリケーションを作成します。</span><span class="sxs-lookup"><span data-stu-id="0c7b9-165">Write a custom provisioning application that creates ports and sends a test message through for new trading partners.</span></span>  
  
-   <span data-ttu-id="0c7b9-166">1 つの発注や、画面、XML ファイル、またはテキスト レポートへの注文書の範囲に関する情報を提供するコマンド ライン ユーティリティには、サンプル プログラムを変更します。</span><span class="sxs-lookup"><span data-stu-id="0c7b9-166">Modify the sample program into a command-line utility that provides information about a single purchase order or a range of purchase orders to the screen, an XML file, or a text report.</span></span>  
  
## <a name="installing-sample-support-files"></a><span data-ttu-id="0c7b9-167">サンプル サポート ファイルをインストールします。</span><span class="sxs-lookup"><span data-stu-id="0c7b9-167">Installing Sample Support Files</span></span>  
 <span data-ttu-id="0c7b9-168">このセクションでは、インストールして、サンプルの実行に必要な手順について説明します。</span><span class="sxs-lookup"><span data-stu-id="0c7b9-168">This section walks through the procedures required to install and run the sample.</span></span>  
  
> [!NOTE]
>  <span data-ttu-id="0c7b9-169">インストールして、このサンプルを実行する前に、BAM がインストールされており、機能していることを確認する必要があります。</span><span class="sxs-lookup"><span data-stu-id="0c7b9-169">Before installing and running this sample, you must verify that BAM has been installed and is functioning.</span></span> <span data-ttu-id="0c7b9-170">BAM がインストールされていない場合、このサンプルは機能しません。</span><span class="sxs-lookup"><span data-stu-id="0c7b9-170">If BAM has not been installed, this sample will not work.</span></span>  
  
#### <a name="to-compile-and-install-the-support-files-for-this-sample"></a><span data-ttu-id="0c7b9-171">コンパイルして、このサンプルのサポート ファイルをインストールするには</span><span class="sxs-lookup"><span data-stu-id="0c7b9-171">To compile and install the support files for this sample</span></span>  
  
1.  <span data-ttu-id="0c7b9-172">コマンド ウィンドウで、次のフォルダーに移動します。</span><span class="sxs-lookup"><span data-stu-id="0c7b9-172">In a command window, navigate to the following folder:</span></span>  
  
     `<Samples Path>\Admin\OperationsOM\OperationSamples`  
  
2.  <span data-ttu-id="0c7b9-173">次の操作を実行します。 Setup.bat を実行します。</span><span class="sxs-lookup"><span data-stu-id="0c7b9-173">Run Setup.bat, which performs the following actions:</span></span>  
  
    -   <span data-ttu-id="0c7b9-174">送信を作成し、ディレクトリを受信</span><span class="sxs-lookup"><span data-stu-id="0c7b9-174">Creates send and receive directories</span></span>  
  
    -   <span data-ttu-id="0c7b9-175">作成および送信が開始され、受信ポート</span><span class="sxs-lookup"><span data-stu-id="0c7b9-175">Creates and starts send and receive ports</span></span>  
  
    -   <span data-ttu-id="0c7b9-176">コンパイルし、HelloWorld オーケストレーションの展開、 `<Samples Path>`\Orchestrations\HelloWorld フォルダー。</span><span class="sxs-lookup"><span data-stu-id="0c7b9-176">Compiles and deploys the HelloWorld orchestration in the `<Samples Path>`\Orchestrations\HelloWorld folder.</span></span>  
  
    -   <span data-ttu-id="0c7b9-177">HelloWorld オーケストレーションの公開キー トークンを変更します。</span><span class="sxs-lookup"><span data-stu-id="0c7b9-177">Modifies the public key token for the HelloWorld orchestration</span></span>  
  
    -   <span data-ttu-id="0c7b9-178">BAM アクティビティ定義および追跡プロファイル エディター ファイルをデプロイします。</span><span class="sxs-lookup"><span data-stu-id="0c7b9-178">Deploys the BAM Activity Definition and Tracking Profile Editor file</span></span>  
  
    -   <span data-ttu-id="0c7b9-179">出力ディレクトリの名前を変更します</span><span class="sxs-lookup"><span data-stu-id="0c7b9-179">Renames the out directory</span></span>  
  
    > [!NOTE]
    >  <span data-ttu-id="0c7b9-180">インストールを中止するには、最初の"press any key to continue"プロンプトで ctrl キーを押しながら C キーを押します。</span><span class="sxs-lookup"><span data-stu-id="0c7b9-180">To abort the installation, press CTRL+C at the first "press any key to continue" prompt.</span></span> <span data-ttu-id="0c7b9-181">これにより、スクリプトを停止し、HelloWorld サンプルの元の状態のままにします。</span><span class="sxs-lookup"><span data-stu-id="0c7b9-181">This stops the script and leaves the HelloWorld sample in its original state.</span></span> <span data-ttu-id="0c7b9-182">2 番目と最後のプロンプトで ctrl キーを押しながら C キーを押しても、インストールは停止しません。</span><span class="sxs-lookup"><span data-stu-id="0c7b9-182">Pressing CTRL+C on the second and final prompt does not stop the installation.</span></span> <span data-ttu-id="0c7b9-183">この場合、OperationsOM サンプルをアンインストールし、HelloWorld サンプルを復元する Cleanup.bat を実行します。</span><span class="sxs-lookup"><span data-stu-id="0c7b9-183">In this case, run Cleanup.bat to uninstall the OperationsOM sample and restore the HelloWorld sample.</span></span>  
  
## <a name="running-this-sample"></a><span data-ttu-id="0c7b9-184">このサンプルの実行</span><span class="sxs-lookup"><span data-stu-id="0c7b9-184">Running This Sample</span></span>  
 <span data-ttu-id="0c7b9-185">次の手順を使用して、OperationsOM サンプルを実行します。</span><span class="sxs-lookup"><span data-stu-id="0c7b9-185">Use the following procedure to run the OperationsOM sample.</span></span>  
  
#### <a name="to-compile-and-run-the-sample"></a><span data-ttu-id="0c7b9-186">コンパイルして、サンプルを実行するには</span><span class="sxs-lookup"><span data-stu-id="0c7b9-186">To compile and run the sample</span></span>  
  
1.  <span data-ttu-id="0c7b9-187">をクリックして**開始**を選択します**すべてのプログラム**を選択します**Microsoft BizTalk Server**、し、 **BizTalk Server 管理**します。</span><span class="sxs-lookup"><span data-stu-id="0c7b9-187">Click **Start**, select **All Programs**, select **Microsoft BizTalk Server**, and then select **BizTalk Server Administration**.</span></span>  
  
2.  <span data-ttu-id="0c7b9-188">BizTalk Server 管理コンソールで  **BizTalk Server 管理**、展開**BizTalk グループ**、展開**プラットフォームの設定**順に展開**ホスト インスタンスの**します。</span><span class="sxs-lookup"><span data-stu-id="0c7b9-188">In the BizTalk Server Administration console, expand **BizTalk Server Administration**, expand **BizTalk Group**, expand **Platform Settings**, and then expand **Host Instances**.</span></span>  
  
3.  <span data-ttu-id="0c7b9-189">右クリック**BizTalkServerApplication**、 をクリックし、**再起動**します。</span><span class="sxs-lookup"><span data-stu-id="0c7b9-189">Right-click **BizTalkServerApplication**, and then click **Restart**.</span></span>  
  
    > [!NOTE]
    >  <span data-ttu-id="0c7b9-190">BizTalkServerApplication ホスト インスタンスを再起動すると、製品を構成してから、ホスト インスタンスを再起動していない場合は、BAM の正しい作業データベースを設定するために必要なことがあります。</span><span class="sxs-lookup"><span data-stu-id="0c7b9-190">Restarting the BizTalkServerApplication host instance may be necessary to set the correct working database for BAM if you have not restarted the host instance since configuring the product.</span></span>  
  
4.  <span data-ttu-id="0c7b9-191">Windows エクスプ ローラーで、次のフォルダーに移動します。</span><span class="sxs-lookup"><span data-stu-id="0c7b9-191">From Windows Explorer, navigate to the following folder:</span></span>  
  
     `<Samples Path>\Admin\OperationsOM\OperationSamples`  
  
5.  <span data-ttu-id="0c7b9-192">ダブルクリックして、 **OperationsOM.sln**プロジェクト ファイルを Visual Studio に読み込みます。</span><span class="sxs-lookup"><span data-stu-id="0c7b9-192">Double-click the **OperationsOM.sln** project file to load it into Visual Studio.</span></span>  
  
6.  <span data-ttu-id="0c7b9-193">F5 キーを押して、サンプルを実行します。</span><span class="sxs-lookup"><span data-stu-id="0c7b9-193">Press F5 to run the sample.</span></span>  
  
     <span data-ttu-id="0c7b9-194">--または--</span><span class="sxs-lookup"><span data-stu-id="0c7b9-194">-- OR --</span></span>  
  
     <span data-ttu-id="0c7b9-195">**ビルド** メニューのをクリックして**ソリューションのリビルド**します。</span><span class="sxs-lookup"><span data-stu-id="0c7b9-195">On the **Build** menu, click **Rebuild Solution**.</span></span> <span data-ttu-id="0c7b9-196">ビルドが完了したらは、Windows エクスプ ローラーを使用して、移動する`<Samples Path>\Admin\OperationsOM\OperationSamples\bin\Debug,`し、ダブルクリック**OperationsSamples.exe**します。</span><span class="sxs-lookup"><span data-stu-id="0c7b9-196">When the build is complete, use Windows Explorer to navigate to `<Samples Path>\Admin\OperationsOM\OperationSamples\bin\Debug,` and then double-click **OperationsSamples.exe**.</span></span>  
  
## <a name="classes-or-methods-used-in-this-sample"></a><span data-ttu-id="0c7b9-197">クラスまたはメソッドのこのサンプルで使用</span><span class="sxs-lookup"><span data-stu-id="0c7b9-197">Classes or Methods Used in This Sample</span></span>  
 <span data-ttu-id="0c7b9-198">[Microsoft.BizTalk.Operations.BizTalkOperations](http://msdn.microsoft.com/library/microsoft.biztalk.operations.biztalkoperations.aspx) &#124; [Microsoft.BizTalk.Operations.MessageFlow](http://msdn.microsoft.com/library/microsoft.biztalk.operations.messageflow.aspx) &#124; [Microsoft.BizTalk.Operations.SendPortInstance](http://msdn.microsoft.com/library/microsoft.biztalk.operations.sendportinstance.aspx)&#124; [Microsoft.BizTalk.Operations.RoutingFailureInstance](http://msdn.microsoft.com/library/microsoft.biztalk.operations.routingfailureinstance.aspx) &#124; [Microsoft.BizTalk.Operations.OrchestrationInstance](http://msdn.microsoft.com/library/microsoft.biztalk.operations.orchestrationinstance.aspx) &#124; [Microsoft.BizTalk.Operations.MSMQtInstance](http://msdn.microsoft.com/library/microsoft.biztalk.operations.msmqtinstance.aspx) &#124; [Microsoft.BizTalk.Operations.TrackedServiceInstance](http://msdn.microsoft.com/library/Microsoft.BizTalk.Operations.TrackedServiceInstance.aspx)</span><span class="sxs-lookup"><span data-stu-id="0c7b9-198">[Microsoft.BizTalk.Operations.BizTalkOperations](http://msdn.microsoft.com/library/microsoft.biztalk.operations.biztalkoperations.aspx)&#124; [Microsoft.BizTalk.Operations.MessageFlow](http://msdn.microsoft.com/library/microsoft.biztalk.operations.messageflow.aspx)&#124; [Microsoft.BizTalk.Operations.SendPortInstance](http://msdn.microsoft.com/library/microsoft.biztalk.operations.sendportinstance.aspx)&#124; [Microsoft.BizTalk.Operations.RoutingFailureInstance](http://msdn.microsoft.com/library/microsoft.biztalk.operations.routingfailureinstance.aspx)&#124; [Microsoft.BizTalk.Operations.OrchestrationInstance](http://msdn.microsoft.com/library/microsoft.biztalk.operations.orchestrationinstance.aspx)&#124; [Microsoft.BizTalk.Operations.MSMQtInstance](http://msdn.microsoft.com/library/microsoft.biztalk.operations.msmqtinstance.aspx)&#124; [Microsoft.BizTalk.Operations.TrackedServiceInstance](http://msdn.microsoft.com/library/Microsoft.BizTalk.Operations.TrackedServiceInstance.aspx)</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="0c7b9-199">参照</span><span class="sxs-lookup"><span data-stu-id="0c7b9-199">See Also</span></span>  
 [<span data-ttu-id="0c7b9-200">Admin-OperationsOM (BizTalk Server Samples フォルダー)</span><span class="sxs-lookup"><span data-stu-id="0c7b9-200">Admin-OperationsOM (BizTalk Server Samples Folder)</span></span>](../core/admin-operationsom-biztalk-server-samples-folder.md)