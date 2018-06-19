---
title: OperationsSamples (BizTalk Server サンプル) |Microsoft ドキュメント
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
ms.openlocfilehash: 2e42b17f19791eef9bd3f1b5d7d4554f61f08356
ms.sourcegitcommit: 3fc338e52d5dbca2c3ea1685a2faafc7582fe23a
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 12/01/2017
ms.locfileid: "26010251"
---
# <a name="operationssamples-biztalk-server-sample"></a><span data-ttu-id="14e3f-102">OperationsSamples (BizTalk Server サンプル)</span><span class="sxs-lookup"><span data-stu-id="14e3f-102">OperationsSamples (BizTalk Server Sample)</span></span>
<span data-ttu-id="14e3f-103">OperationsSamples サンプルは、Operations オブジェクト モデルを使用して、さまざまな操作を実行する方法を具体的に示します。</span><span class="sxs-lookup"><span data-stu-id="14e3f-103">The OperationsSamples sample demonstrates how to perform operational activities using the Operations object model.</span></span>  
  
## <a name="what-this-sample-does"></a><span data-ttu-id="14e3f-104">このサンプルの処理</span><span class="sxs-lookup"><span data-stu-id="14e3f-104">What This Sample Does</span></span>  
 <span data-ttu-id="14e3f-105">このサンプルは、次の操作方法を示します。</span><span class="sxs-lookup"><span data-stu-id="14e3f-105">This sample demonstrates the following:</span></span>  
  
-   <span data-ttu-id="14e3f-106">追跡プロファイルを使用して、オーケストレーションにアクティビティのコメントを付ける。</span><span class="sxs-lookup"><span data-stu-id="14e3f-106">How to use a tracking profile to comment an orchestration with activities.</span></span>  
  
-   <span data-ttu-id="14e3f-107">BAM 追跡データベースを使用して、アクティビティ ID を検索し、ID を使用して、関連するオーケストレーション インスタンスを検索する方法です。</span><span class="sxs-lookup"><span data-stu-id="14e3f-107">How to use the BAM tracking database to find an activity ID and then use the ID to find a related orchestration instance.</span></span>  
  
-   <span data-ttu-id="14e3f-108">検索およびメッセージ フローを使用して操作する方法、 **MessageFlow**クラスとその他の Operations オブジェクト モデル クラスおよび Api です。</span><span class="sxs-lookup"><span data-stu-id="14e3f-108">How to find and work with message flows by using the **MessageFlow** class and other Operations object model classes and APIs.</span></span>  
  
-   <span data-ttu-id="14e3f-109">ポートへのアクセス方法、メッセージ、およびから派生したクラスを使用して他のインスタンス、**インスタンス**クラスです。</span><span class="sxs-lookup"><span data-stu-id="14e3f-109">How to access ports, messages, and other instances by using classes derived from the **Instance** class.</span></span>  
  
 <span data-ttu-id="14e3f-110">サンプルには、上の操作をサポートする多くの有益なヘルパー クラスとメソッドが含まれています。</span><span class="sxs-lookup"><span data-stu-id="14e3f-110">The sample contains many useful helper classes and methods to support the operations above.</span></span> <span data-ttu-id="14e3f-111">これらと他のコードの特長については、次のセクションで説明します。</span><span class="sxs-lookup"><span data-stu-id="14e3f-111">These and other code highlights are discussed in the next section.</span></span>  
  
## <a name="how-this-sample-is-designed-and-why"></a><span data-ttu-id="14e3f-112">このサンプルの目的とその理由</span><span class="sxs-lookup"><span data-stu-id="14e3f-112">How This Sample Is Designed and Why</span></span>  
 <span data-ttu-id="14e3f-113">このサンプルは、Operations オブジェクト モデルの主要クラスおよびメソッドの機能を紹介し、ユーザーに公開されている BAM 追跡データベースでクエリを実行する方法を示すことを目的としています。</span><span class="sxs-lookup"><span data-stu-id="14e3f-113">This sample is designed to demonstrate several of the key classes and methods in the Operations object model and to show how to query the publicly available BAM tracking database.</span></span>  
  
 <span data-ttu-id="14e3f-114">Operations オブジェクト モデルには、BizTalk Server 内でメッセージや他のインスタンスを操作できるクラスが含まれています。</span><span class="sxs-lookup"><span data-stu-id="14e3f-114">The Operations object model contains classes that provide the ability to manipulate messages and other instances within BizTalk Server.</span></span>  
  
### <a name="using-a-bam-activity-id"></a><span data-ttu-id="14e3f-115">BAM アクティビティ ID の使用</span><span class="sxs-lookup"><span data-stu-id="14e3f-115">Using a BAM Activity ID</span></span>  
 <span data-ttu-id="14e3f-116">このサンプルでは、BAM との対話方法と、ユーザーに公開されている追跡データベースのビューを使用して、ビジネス データを使ってメッセージ ボックスのライブ メッセージを見つける方法を示します。</span><span class="sxs-lookup"><span data-stu-id="14e3f-116">This sample shows how to interact with BAM and how to use the publicly available views in the tracking database to locate a live message in the message box by using business data.</span></span> <span data-ttu-id="14e3f-117">サンプルでは、注文書番号に対応するオーケストレーション ID を取得して、この作業を行います。</span><span class="sxs-lookup"><span data-stu-id="14e3f-117">The sample does this by retrieving an orchestration ID corresponding to a purchase order number.</span></span> <span data-ttu-id="14e3f-118">このタスクを成功させるには、次のことを行う必要があります。</span><span class="sxs-lookup"><span data-stu-id="14e3f-118">For this task to succeed, it must do the following:</span></span>  
  
1.  <span data-ttu-id="14e3f-119">ビジネス データ (注文書番号) を使用して、アクティビティ ID を検索します。</span><span class="sxs-lookup"><span data-stu-id="14e3f-119">Use business data (a purchase order number) to find an activity ID.</span></span> <span data-ttu-id="14e3f-120">この手順では、ビジネス データを内部 ID にマップして、追加情報の検索に使用できるようにします。</span><span class="sxs-lookup"><span data-stu-id="14e3f-120">This step maps business data to an internal ID that can be used to find additional information.</span></span>  
  
2.  <span data-ttu-id="14e3f-121">アクティビティ ID に関連する BAM 参照を取得します。</span><span class="sxs-lookup"><span data-stu-id="14e3f-121">Retrieve the BAM references related to the activity ID.</span></span>  
  
3.  <span data-ttu-id="14e3f-122">種類が "BizTalkService" の参照を検索し、オーケストレーションを参照します。</span><span class="sxs-lookup"><span data-stu-id="14e3f-122">Find a reference that has a type of "BizTalkService" and refers to an orchestration.</span></span> <span data-ttu-id="14e3f-123">見つかったら、そのインスタンス ID を返します。</span><span class="sxs-lookup"><span data-stu-id="14e3f-123">If one is found, return its instance ID.</span></span>  
  
 <span data-ttu-id="14e3f-124">この機能は、 **BAMWebService.GetOrchestrationID**静的メソッドと、BamManagementService.cs ソース ファイルのクラスとメソッドを含む関連ヘルパー メソッドです。</span><span class="sxs-lookup"><span data-stu-id="14e3f-124">This functionality is provided by the **BAMWebService.GetOrchestrationID** static method and associated helper methods including classes and methods in the BamManagementService.cs source file.</span></span>  
  
### <a name="suspending-terminating-and-resuming-an-instance"></a><span data-ttu-id="14e3f-125">インスタンスの中断、終了、および再開</span><span class="sxs-lookup"><span data-stu-id="14e3f-125">Suspending, Terminating, and Resuming an Instance</span></span>  
 <span data-ttu-id="14e3f-126">サンプル プログラムが含まれています、 **Samples.OperateOnInstance**メソッドを操作し、インスタンス ID をインスタンスに対して指定された操作を実行します。</span><span class="sxs-lookup"><span data-stu-id="14e3f-126">The sample program includes a **Samples.OperateOnInstance** method that takes an operation and instance ID and performs the specified operation on the instance.</span></span> <span data-ttu-id="14e3f-127">有効な操作がによって定義されている、 **InstanceOperation**列挙しており、Suspend、Terminate、Resume です。</span><span class="sxs-lookup"><span data-stu-id="14e3f-127">Valid operations are defined by the **InstanceOperation** enumeration and include Suspend, Terminate, and Resume.</span></span> <span data-ttu-id="14e3f-128">これらの操作は、biztalkoperations のメソッドに直接マップ —**SuspendInstance**、 **TerminateInstance**、および**ResumeInstance**です。</span><span class="sxs-lookup"><span data-stu-id="14e3f-128">These operations map directly to methods of the BizTalkOperations class—**SuspendInstance**, **TerminateInstance**, and **ResumeInstance**.</span></span>  
  
 <span data-ttu-id="14e3f-129">メソッドは ArgumentException と SqlException の両方の例外を処理します。</span><span class="sxs-lookup"><span data-stu-id="14e3f-129">Notice that the method handles both ArgumentException and SqlException exceptions.</span></span> <span data-ttu-id="14e3f-130">Operations オブジェクト モデルのクラスおよびメソッドの操作時に、SqlException を含む例外が発生する可能性があるので注意してください。</span><span class="sxs-lookup"><span data-stu-id="14e3f-130">You must be careful to anticipate exceptions—including SqlException—when working with the classes and methods in the Operations object model.</span></span>  
  
> [!NOTE]
>  <span data-ttu-id="14e3f-131">Operations メソッドの多くは、データベースにアクセスする必要があります。</span><span class="sxs-lookup"><span data-stu-id="14e3f-131">Many of the Operations methods require access to the database.</span></span> <span data-ttu-id="14e3f-132">これらのメソッドによって例外がスローされる可能性があることを予測し、適切に処理する必要があります。</span><span class="sxs-lookup"><span data-stu-id="14e3f-132">You should anticipate the exceptions thrown by these methods and handle them appropriately.</span></span>  
  
### <a name="retrieving-all-live-messages"></a><span data-ttu-id="14e3f-133">すべてのライブ メッセージの取得</span><span class="sxs-lookup"><span data-stu-id="14e3f-133">Retrieving All Live Messages</span></span>  
 <span data-ttu-id="14e3f-134">次のコードに示すように、Operations オブジェクト モデルでは、取得可能なすべてのライブ メッセージを簡単に繰り返すことができます。</span><span class="sxs-lookup"><span data-stu-id="14e3f-134">The Operations object model makes it straightforward to iterate over all of the available live messages, as shown in the following code fragment:</span></span>  
  
```  
BizTalkOperations _operations = new BizTalkOperations()  
IEnumerable messages = _operations.GetMessages();  
foreach (BizTalkMessage msg in messages)  
…  
```  
  
 <span data-ttu-id="14e3f-135">OperationsSamples プログラムは、この手順をさらに一歩進め、メッセージ部分の数や種類と共に、メッセージ ID とメッセージの種類を含む、各メッセージに関する情報にアクセスする方法を示します。</span><span class="sxs-lookup"><span data-stu-id="14e3f-135">The OperationsSamples program takes this a step further by demonstrating how to access information about each message, including message ID and message type along with the number and types of message parts.</span></span> <span data-ttu-id="14e3f-136">このコードを変更して、BizTalk Server で、取得可能なライブ メッセージの多くまたはすべてで繰り返す必要があるシナリオに使用できます。</span><span class="sxs-lookup"><span data-stu-id="14e3f-136">You can modify this code and use it in scenarios where you have to iterate through many or all of the available live messages in BizTalk Server.</span></span>  
  
> [!NOTE]
>  <span data-ttu-id="14e3f-137">数百または数千のメッセージが存在する場合があります。</span><span class="sxs-lookup"><span data-stu-id="14e3f-137">There may be hundreds or thousands of messages available.</span></span> <span data-ttu-id="14e3f-138">リスト全体をスキャンすると、パフォーマンスが低下することがあります。</span><span class="sxs-lookup"><span data-stu-id="14e3f-138">Scanning the entire list may adversely affect performance.</span></span>  
  
## <a name="where-to-find-this-sample"></a><span data-ttu-id="14e3f-139">このサンプルの場所</span><span class="sxs-lookup"><span data-stu-id="14e3f-139">Where to Find This Sample</span></span>  
 <span data-ttu-id="14e3f-140">このサンプルは、SDK がある次の場所にあります。</span><span class="sxs-lookup"><span data-stu-id="14e3f-140">The sample is located in the following SDK location:</span></span>  
  
 <span data-ttu-id="14e3f-141">\<*パスのサンプル*\>\Admin\OperationsOM\OperationsSamples\\</span><span class="sxs-lookup"><span data-stu-id="14e3f-141">\<*Samples Path*\>\Admin\OperationsOM\OperationsSamples\\</span></span>  
  
 <span data-ttu-id="14e3f-142">次の表は、このサンプルのファイルとその目的を示しています。</span><span class="sxs-lookup"><span data-stu-id="14e3f-142">The following table shows the files in this sample and describes their purpose.</span></span>  
  
|<span data-ttu-id="14e3f-143">ファイル</span><span class="sxs-lookup"><span data-stu-id="14e3f-143">File(s)</span></span>|<span data-ttu-id="14e3f-144">Description</span><span class="sxs-lookup"><span data-stu-id="14e3f-144">Description</span></span>|  
|---------------|-----------------|  
|<span data-ttu-id="14e3f-145">BamManagementService.cs</span><span class="sxs-lookup"><span data-stu-id="14e3f-145">BamManagementService.cs</span></span>|<span data-ttu-id="14e3f-146">BAM Web サービスの Web プロキシ クラスです。</span><span class="sxs-lookup"><span data-stu-id="14e3f-146">Web proxy class for the BAM Web service.</span></span>|  
|<span data-ttu-id="14e3f-147">Cleanup.bat</span><span class="sxs-lookup"><span data-stu-id="14e3f-147">Cleanup.bat</span></span>|<span data-ttu-id="14e3f-148">サンプル オーケストレーションを削除し、HelloWorld サンプルを元の状態に戻します。</span><span class="sxs-lookup"><span data-stu-id="14e3f-148">Removes the sample orchestration and restores the HelloWorld sample to its original state.</span></span>|  
|<span data-ttu-id="14e3f-149">HelloOrchestration.btt</span><span class="sxs-lookup"><span data-stu-id="14e3f-149">HelloOrchestration.btt</span></span>|<span data-ttu-id="14e3f-150">BizTalk イベント ソースを BAM ターゲット アクティビティにマップするときに使用する追跡プロファイルです。</span><span class="sxs-lookup"><span data-stu-id="14e3f-150">Tracking profile used to map BizTalk event sources to BAM target activities.</span></span>|  
|<span data-ttu-id="14e3f-151">HelloOrchestration.xls</span><span class="sxs-lookup"><span data-stu-id="14e3f-151">HelloOrchestration.xls</span></span>|<span data-ttu-id="14e3f-152">BAM 定義スタイルシート。</span><span class="sxs-lookup"><span data-stu-id="14e3f-152">BAM definition style sheet.</span></span>|  
|<span data-ttu-id="14e3f-153">OperationsSamples.cs</span><span class="sxs-lookup"><span data-stu-id="14e3f-153">OperationsSamples.cs</span></span>|<span data-ttu-id="14e3f-154">Operations オブジェクト モデルのさまざまな側面を示すコードを含む C# ソース ファイルです。</span><span class="sxs-lookup"><span data-stu-id="14e3f-154">C# source file containing code that demonstrates various aspects of the Operations object model.</span></span>|  
|<span data-ttu-id="14e3f-155">OperationsSamples.csproj、OperationsSamples.sln、AssemblyInfo.cs</span><span class="sxs-lookup"><span data-stu-id="14e3f-155">OperationsSamples.csproj, OperationsSamples.sln, AssemblyInfo.cs</span></span>|<span data-ttu-id="14e3f-156">このサンプルのプロジェクト、ソリューション、およびアセンブリ情報です。</span><span class="sxs-lookup"><span data-stu-id="14e3f-156">Project, solution, and assembly information files for this sample.</span></span>|  
|<span data-ttu-id="14e3f-157">Setup.bat</span><span class="sxs-lookup"><span data-stu-id="14e3f-157">Setup.bat</span></span>|<span data-ttu-id="14e3f-158">HelloWorld オーケストレーション サンプルを変更して、このサンプルをビルドおよび初期化するのに使用します。</span><span class="sxs-lookup"><span data-stu-id="14e3f-158">Used to build and initialize this sample by modifying the HelloWorld orchestration sample.</span></span> <span data-ttu-id="14e3f-159">サンプル オーケストレーションのインストール、BAM アクティビティ定義および追跡プロファイル エディター ファイルの展開、ポートの構成、受信場所へのサンプル ファイルのドロップを実行します。</span><span class="sxs-lookup"><span data-stu-id="14e3f-159">It installs a sample orchestration, deploys a BAM Activity Definition and a Tracking Profile Editor file, configures ports, and drops a sample file into the receive location.</span></span>|  
  
## <a name="how-to-use-this-sample"></a><span data-ttu-id="14e3f-160">このサンプルの使用方法</span><span class="sxs-lookup"><span data-stu-id="14e3f-160">How to Use This Sample</span></span>  
 <span data-ttu-id="14e3f-161">このサンプルを使用して、Operations オブジェクト モデルで使用できる機能を試してください。</span><span class="sxs-lookup"><span data-stu-id="14e3f-161">Use this sample to explore the functionality available in the Operations object model.</span></span> <span data-ttu-id="14e3f-162">既存のルーチンを変更して、メッセージを異なる方法で検索および操作したり、BizTalk Server 管理コンソールのグループ ハブの一部を複製する新しいコードを追加します。</span><span class="sxs-lookup"><span data-stu-id="14e3f-162">Modify existing routines to find and work with messages differently or add new code that replicates portions of the Group Hub in the BizTalk Server Management console.</span></span>  
  
 <span data-ttu-id="14e3f-163">次のタスクを行うこともできます。</span><span class="sxs-lookup"><span data-stu-id="14e3f-163">You may also consider some of the following tasks:</span></span>  
  
-   <span data-ttu-id="14e3f-164">カスタム アプリケーションにグループのハブのよく使われるサブセットをレプリケートするアプリケーションを作成します。</span><span class="sxs-lookup"><span data-stu-id="14e3f-164">Write an application that replicates the most-used subset of the Group Hub into a custom application.</span></span>  
  
-   <span data-ttu-id="14e3f-165">ポートを作成し、新しい取引先にテスト メッセージを送信するカスタム プロビジョニング アプリケーションを作成する。</span><span class="sxs-lookup"><span data-stu-id="14e3f-165">Write a custom provisioning application that creates ports and sends a test message through for new trading partners.</span></span>  
  
-   <span data-ttu-id="14e3f-166">サンプル プログラムを、1 件の注文書または一連の注文書に関する情報を画面、XML ファイル、またはテキスト レポートに出力するコマンド ライン ユーティリティに変更する。</span><span class="sxs-lookup"><span data-stu-id="14e3f-166">Modify the sample program into a command-line utility that provides information about a single purchase order or a range of purchase orders to the screen, an XML file, or a text report.</span></span>  
  
## <a name="installing-sample-support-files"></a><span data-ttu-id="14e3f-167">サンプル サポート ファイルのインストール</span><span class="sxs-lookup"><span data-stu-id="14e3f-167">Installing Sample Support Files</span></span>  
 <span data-ttu-id="14e3f-168">このセクションでは、サンプルをインストールして実行するために必要な手順を説明します。</span><span class="sxs-lookup"><span data-stu-id="14e3f-168">This section walks through the procedures required to install and run the sample.</span></span>  
  
> [!NOTE]
>  <span data-ttu-id="14e3f-169">このサンプルをインストールして実行する前に、BAM がインストールされ、機能していることを確認してください。</span><span class="sxs-lookup"><span data-stu-id="14e3f-169">Before installing and running this sample, you must verify that BAM has been installed and is functioning.</span></span> <span data-ttu-id="14e3f-170">BAM がインストールされていないと、このサンプルは動作しません。</span><span class="sxs-lookup"><span data-stu-id="14e3f-170">If BAM has not been installed, this sample will not work.</span></span>  
  
#### <a name="to-compile-and-install-the-support-files-for-this-sample"></a><span data-ttu-id="14e3f-171">このサンプルのサポート ファイルをコンパイルおよびインストールするには</span><span class="sxs-lookup"><span data-stu-id="14e3f-171">To compile and install the support files for this sample</span></span>  
  
1.  <span data-ttu-id="14e3f-172">コマンド ウィンドウで、次のフォルダーに移動します。</span><span class="sxs-lookup"><span data-stu-id="14e3f-172">In a command window, navigate to the following folder:</span></span>  
  
     `<Samples Path>\Admin\OperationsOM\OperationSamples`  
  
2.  <span data-ttu-id="14e3f-173">Setup.bat を実行します。処理内容は次のとおりです。</span><span class="sxs-lookup"><span data-stu-id="14e3f-173">Run Setup.bat, which performs the following actions:</span></span>  
  
    -   <span data-ttu-id="14e3f-174">送信および受信ディレクトリの作成</span><span class="sxs-lookup"><span data-stu-id="14e3f-174">Creates send and receive directories</span></span>  
  
    -   <span data-ttu-id="14e3f-175">送信および受信ポートの作成と起動</span><span class="sxs-lookup"><span data-stu-id="14e3f-175">Creates and starts send and receive ports</span></span>  
  
    -   <span data-ttu-id="14e3f-176">`<Samples Path>`\Orchestrations\HelloWorld フォルダーの HelloWorld オーケストレーションのコンパイルと展開</span><span class="sxs-lookup"><span data-stu-id="14e3f-176">Compiles and deploys the HelloWorld orchestration in the `<Samples Path>`\Orchestrations\HelloWorld folder.</span></span>  
  
    -   <span data-ttu-id="14e3f-177">HelloWorld オーケストレーション用に公開キー トークンを変更</span><span class="sxs-lookup"><span data-stu-id="14e3f-177">Modifies the public key token for the HelloWorld orchestration</span></span>  
  
    -   <span data-ttu-id="14e3f-178">BAM アクティビティ定義および追跡プロファイル エディター ファイルの展開</span><span class="sxs-lookup"><span data-stu-id="14e3f-178">Deploys the BAM Activity Definition and Tracking Profile Editor file</span></span>  
  
    -   <span data-ttu-id="14e3f-179">出力ディレクトリの名前の変更</span><span class="sxs-lookup"><span data-stu-id="14e3f-179">Renames the out directory</span></span>  
  
    > [!NOTE]
    >  <span data-ttu-id="14e3f-180">インストールを中止するには、最初の "press any key to continue" プロンプトで Ctrl キーを押しながら C キーを押します。</span><span class="sxs-lookup"><span data-stu-id="14e3f-180">To abort the installation, press CTRL+C at the first "press any key to continue" prompt.</span></span> <span data-ttu-id="14e3f-181">スクリプトが停止し、HelloWorld サンプルは元の状態のままです。</span><span class="sxs-lookup"><span data-stu-id="14e3f-181">This stops the script and leaves the HelloWorld sample in its original state.</span></span> <span data-ttu-id="14e3f-182">2 番目および最後のプロンプトで Ctrl キーを押しながら C キーを押しても、インストールは終了しません。</span><span class="sxs-lookup"><span data-stu-id="14e3f-182">Pressing CTRL+C on the second and final prompt does not stop the installation.</span></span> <span data-ttu-id="14e3f-183">この場合は、Cleanup.bat を実行して、OperationsOM サンプルをアンインストールし、HelloWorld サンプルを復元してください。</span><span class="sxs-lookup"><span data-stu-id="14e3f-183">In this case, run Cleanup.bat to uninstall the OperationsOM sample and restore the HelloWorld sample.</span></span>  
  
## <a name="running-this-sample"></a><span data-ttu-id="14e3f-184">このサンプルの実行</span><span class="sxs-lookup"><span data-stu-id="14e3f-184">Running This Sample</span></span>  
 <span data-ttu-id="14e3f-185">次の手順で、OperationsOM サンプルを実行します。</span><span class="sxs-lookup"><span data-stu-id="14e3f-185">Use the following procedure to run the OperationsOM sample.</span></span>  
  
#### <a name="to-compile-and-run-the-sample"></a><span data-ttu-id="14e3f-186">サンプルをコンパイルおよび実行するには</span><span class="sxs-lookup"><span data-stu-id="14e3f-186">To compile and run the sample</span></span>  
  
1.  <span data-ttu-id="14e3f-187">をクリックして**開始****すべてのプログラム**を選択**Microsoft BizTalk Server**、し、 **BizTalk Server 管理コンソール**です。</span><span class="sxs-lookup"><span data-stu-id="14e3f-187">Click **Start**, select **All Programs**, select **Microsoft BizTalk Server**, and then select **BizTalk Server Administration**.</span></span>  
  
2.  <span data-ttu-id="14e3f-188">BizTalk Server 管理コンソールで、展開**BizTalk Server 管理コンソール**、展開**BizTalk グループ**、展開**プラットフォームの設定**を順に展開**ホスト インスタンスの**します。</span><span class="sxs-lookup"><span data-stu-id="14e3f-188">In the BizTalk Server Administration console, expand **BizTalk Server Administration**, expand **BizTalk Group**, expand **Platform Settings**, and then expand **Host Instances**.</span></span>  
  
3.  <span data-ttu-id="14e3f-189">右クリック**BizTalkServerApplication**、クリックして**再起動**です。</span><span class="sxs-lookup"><span data-stu-id="14e3f-189">Right-click **BizTalkServerApplication**, and then click **Restart**.</span></span>  
  
    > [!NOTE]
    >  <span data-ttu-id="14e3f-190">製品を構成してからホスト インスタンスを再起動していない場合は、BAM に正しい作業データベースを設定するために、BizTalkServerApplication ホスト インスタンスの再起動が必要です。</span><span class="sxs-lookup"><span data-stu-id="14e3f-190">Restarting the BizTalkServerApplication host instance may be necessary to set the correct working database for BAM if you have not restarted the host instance since configuring the product.</span></span>  
  
4.  <span data-ttu-id="14e3f-191">Windows エクスプローラーから、次のフォルダーに移動します。</span><span class="sxs-lookup"><span data-stu-id="14e3f-191">From Windows Explorer, navigate to the following folder:</span></span>  
  
     `<Samples Path>\Admin\OperationsOM\OperationSamples`  
  
5.  <span data-ttu-id="14e3f-192">ダブルクリックして、 **OperationsOM.sln** Visual Studio に読み込むプロジェクト ファイルです。</span><span class="sxs-lookup"><span data-stu-id="14e3f-192">Double-click the **OperationsOM.sln** project file to load it into Visual Studio.</span></span>  
  
6.  <span data-ttu-id="14e3f-193">F5 キーを押して、サンプルを実行します。</span><span class="sxs-lookup"><span data-stu-id="14e3f-193">Press F5 to run the sample.</span></span>  
  
     <span data-ttu-id="14e3f-194">-または--</span><span class="sxs-lookup"><span data-stu-id="14e3f-194">-- OR --</span></span>  
  
     <span data-ttu-id="14e3f-195">**ビルド** メニューのをクリックして**ソリューションのリビルド**です。</span><span class="sxs-lookup"><span data-stu-id="14e3f-195">On the **Build** menu, click **Rebuild Solution**.</span></span> <span data-ttu-id="14e3f-196">ビルドが完了したら、エクスプ ローラーを使用して、移動する`<Samples Path>\Admin\OperationsOM\OperationSamples\bin\Debug,`順にダブルクリック**OperationsSamples.exe**です。</span><span class="sxs-lookup"><span data-stu-id="14e3f-196">When the build is complete, use Windows Explorer to navigate to `<Samples Path>\Admin\OperationsOM\OperationSamples\bin\Debug,` and then double-click **OperationsSamples.exe**.</span></span>  
  
## <a name="classes-or-methods-used-in-this-sample"></a><span data-ttu-id="14e3f-197">このサンプルで使用されるクラスまたはメソッド</span><span class="sxs-lookup"><span data-stu-id="14e3f-197">Classes or Methods Used in This Sample</span></span>  
 <span data-ttu-id="14e3f-198">[Microsoft.BizTalk.Operations.BizTalkOperations](http://msdn.microsoft.com/library/microsoft.biztalk.operations.biztalkoperations.aspx)&#124;です。[Microsoft.BizTalk.Operations.MessageFlow](http://msdn.microsoft.com/library/microsoft.biztalk.operations.messageflow.aspx)&#124;です。[Microsoft.BizTalk.Operations.SendPortInstance](http://msdn.microsoft.com/library/microsoft.biztalk.operations.sendportinstance.aspx)&#124;です。[Microsoft.BizTalk.Operations.RoutingFailureInstance](http://msdn.microsoft.com/library/microsoft.biztalk.operations.routingfailureinstance.aspx)&#124;です。[Microsoft.BizTalk.Operations.OrchestrationInstance](http://msdn.microsoft.com/library/microsoft.biztalk.operations.orchestrationinstance.aspx)&#124;です。[Microsoft.BizTalk.Operations.MSMQtInstance](http://msdn.microsoft.com/library/microsoft.biztalk.operations.msmqtinstance.aspx)&#124;です。[Microsoft.BizTalk.Operations.TrackedServiceInstance](http://msdn.microsoft.com/library/Microsoft.BizTalk.Operations.TrackedServiceInstance.aspx)</span><span class="sxs-lookup"><span data-stu-id="14e3f-198">[Microsoft.BizTalk.Operations.BizTalkOperations](http://msdn.microsoft.com/library/microsoft.biztalk.operations.biztalkoperations.aspx)&#124; [Microsoft.BizTalk.Operations.MessageFlow](http://msdn.microsoft.com/library/microsoft.biztalk.operations.messageflow.aspx)&#124; [Microsoft.BizTalk.Operations.SendPortInstance](http://msdn.microsoft.com/library/microsoft.biztalk.operations.sendportinstance.aspx)&#124; [Microsoft.BizTalk.Operations.RoutingFailureInstance](http://msdn.microsoft.com/library/microsoft.biztalk.operations.routingfailureinstance.aspx)&#124; [Microsoft.BizTalk.Operations.OrchestrationInstance](http://msdn.microsoft.com/library/microsoft.biztalk.operations.orchestrationinstance.aspx)&#124; [Microsoft.BizTalk.Operations.MSMQtInstance](http://msdn.microsoft.com/library/microsoft.biztalk.operations.msmqtinstance.aspx)&#124; [Microsoft.BizTalk.Operations.TrackedServiceInstance](http://msdn.microsoft.com/library/Microsoft.BizTalk.Operations.TrackedServiceInstance.aspx)</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="14e3f-199">参照</span><span class="sxs-lookup"><span data-stu-id="14e3f-199">See Also</span></span>  
 [<span data-ttu-id="14e3f-200">Admin-OperationsOM (BizTalk Server Samples フォルダー)</span><span class="sxs-lookup"><span data-stu-id="14e3f-200">Admin-OperationsOM (BizTalk Server Samples Folder)</span></span>](../core/admin-operationsom-biztalk-server-samples-folder.md)