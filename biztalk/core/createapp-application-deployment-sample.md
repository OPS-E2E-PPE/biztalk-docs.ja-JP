---
title: "CreateApp (アプリケーションの展開サンプル) |Microsoft ドキュメント"
ms.custom: 
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: 
ms.suite: 
ms.tgt_pltfrm: 
ms.topic: article
helpviewer_keywords:
- deploying, examples
- deploying, .msi file
- deploying, exporting
- .msi files, deploying
- examples, deploying
ms.assetid: 825627ee-21d0-4505-9df4-1dadc51335b6
caps.latest.revision: "14"
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: 842683d2eec04d77bad2b7726af0d687fae12884
ms.sourcegitcommit: 5abd0ed3f9e4858ffaaec5481bfa8878595e95f7
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 11/28/2017
---
# <a name="createapp-application-deployment-sample"></a><span data-ttu-id="2ea96-102">CreateApp (アプリケーションの展開サンプル)</span><span class="sxs-lookup"><span data-stu-id="2ea96-102">CreateApp (Application Deployment Sample)</span></span>
<span data-ttu-id="2ea96-103">このトピックでは、CreateApp サンプルの使用方法について説明し、BTSTask コマンド ライン ツールを使用して BizTalk アプリケーションを展開および展開解除する方法を示します。</span><span class="sxs-lookup"><span data-stu-id="2ea96-103">This topic explains how to use the CreateApp sample, which demonstrates using the BTSTask command-line tool to deploy and undeploy a BizTalk application.</span></span> <span data-ttu-id="2ea96-104">このサンプルに含まれるスクリプトを使用して夜間のビルド プロセスを自動化し、BizTalk アプリケーションを展開および展開解除できます。</span><span class="sxs-lookup"><span data-stu-id="2ea96-104">You could use scripts such as those included in this sample to automate your nightly build process to deploy and undeploy BizTalk applications.</span></span>  
  
> [!IMPORTANT]
>  <span data-ttu-id="2ea96-105">サイレント モードで実行する展開スクリプトを必ず記述します。</span><span class="sxs-lookup"><span data-stu-id="2ea96-105">You should always write your deployment scripts to run in silent mode.</span></span> <span data-ttu-id="2ea96-106">記述しないと、ユーザー入力を必要とするダイアログ ボックスが表示されます。</span><span class="sxs-lookup"><span data-stu-id="2ea96-106">If you do not, dialog boxes will display that require user input.</span></span> <span data-ttu-id="2ea96-107">ダイアログ ボックスが手動で閉じられるまで展開プロセスが停止され、インポート プロセスが中断されます。</span><span class="sxs-lookup"><span data-stu-id="2ea96-107">This will stop the deployment process until the dialog box is manually dismissed, which can cause the import process to hang.</span></span>  
  
## <a name="what-this-sample-does"></a><span data-ttu-id="2ea96-108">このサンプルの処理</span><span class="sxs-lookup"><span data-stu-id="2ea96-108">What This Sample Does</span></span>  
 <span data-ttu-id="2ea96-109">このサンプルには、アプリケーション展開タスクを自動化するスクリプトが含まれています。</span><span class="sxs-lookup"><span data-stu-id="2ea96-109">The sample includes scripts that automate application deployment tasks.</span></span> <span data-ttu-id="2ea96-110">これらのタスクを実行するには、BizTalk プロジェクトおよびファイルを生成するスクリプトを実行します。</span><span class="sxs-lookup"><span data-stu-id="2ea96-110">To perform these tasks, you run a script that generates the BizTalk project and files.</span></span> <span data-ttu-id="2ea96-111">次に、2 つの BizTalk アプリケーションの .msi ファイルを生成するスクリプトを実行します。これらのファイルは、アプリケーションのすべてのアイテムを含んでいるファイルと、アプリケーションの 1 つのアセンブリのみを含んでいるファイルです。</span><span class="sxs-lookup"><span data-stu-id="2ea96-111">Then you run a script that generates two BizTalk application .msi files – an .msi file that contains all of the artifacts in an application, and another that contains only one assembly in the application.</span></span> <span data-ttu-id="2ea96-112">その後、.msi ファイルを使用してアプリケーションを BizTalk グループにインポートするスクリプトを実行し、アプリケーションをローカル コンピュータにインストールします。</span><span class="sxs-lookup"><span data-stu-id="2ea96-112">Next you run a script that uses an .msi file to import an application into a BizTalk group and install the application onto the local computer.</span></span> <span data-ttu-id="2ea96-113">インストール中には、処理前のスクリプトをアプリケーションに含まれてはアプリケーションによって使用されるフォルダーを作成し、ファイルにその操作を記録します。</span><span class="sxs-lookup"><span data-stu-id="2ea96-113">During installation, a pre-processing script included in the application creates folders used by the application and logs its actions to a file.</span></span> <span data-ttu-id="2ea96-114">最後に、アプリケーションを削除およびアンインストールするスクリプトを実行します。</span><span class="sxs-lookup"><span data-stu-id="2ea96-114">Finally, you run a script that deletes and uninstalls the application.</span></span> <span data-ttu-id="2ea96-115">アンインストール中は、アプリケーションに含まれている処理前のスクリプトは、ファイルとフォルダーのインストール時に作成されたを削除し、ファイルにその操作を記録します。</span><span class="sxs-lookup"><span data-stu-id="2ea96-115">During uninstallation, a pre-processing script included in the application removes the files and folders that were created during installation and logs its actions to a file.</span></span>  
  
 <span data-ttu-id="2ea96-116">このサンプルに含まれるスクリプトは次のとおりです。</span><span class="sxs-lookup"><span data-stu-id="2ea96-116">The following are the scripts included with this sample:</span></span>  
  
-   <span data-ttu-id="2ea96-117">**Build.bat です。**</span><span class="sxs-lookup"><span data-stu-id="2ea96-117">**Build.bat.**</span></span> <span data-ttu-id="2ea96-118">キー ファイルを生成し、Visual Studio 内にプロジェクトをビルドし、.dll ファイルに署名します。</span><span class="sxs-lookup"><span data-stu-id="2ea96-118">Generates a key file, builds the project in Visual Studio, and signs the .dll files.</span></span>  
  
-   <span data-ttu-id="2ea96-119">**CreateFullAndPartialMSI.bat です。**</span><span class="sxs-lookup"><span data-stu-id="2ea96-119">**CreateFullAndPartialMSI.bat.**</span></span> <span data-ttu-id="2ea96-120">以下の処理を順番に実行します。</span><span class="sxs-lookup"><span data-stu-id="2ea96-120">Takes the following actions, in order:</span></span>  
  
    1.  <span data-ttu-id="2ea96-121">BTSTask を使用して[AddApp コマンド](../core/addapp-command.md)アプリケーションを作成します。</span><span class="sxs-lookup"><span data-stu-id="2ea96-121">Uses the BTSTask [AddApp command](../core/addapp-command.md) to create an application.</span></span>  
  
    2.  <span data-ttu-id="2ea96-122">BTSTask を使用して[AddResource コマンド](../core/addresource-command.md)Build.bat によって生成されたも他のリソースをアプリケーション 3 つの BizTalk アセンブリを追加します。</span><span class="sxs-lookup"><span data-stu-id="2ea96-122">Uses the BTSTask [AddResource command](../core/addresource-command.md) to add to the application three BizTalk assemblies as well as other resources that were generated by Build.bat.</span></span>  
  
    3.  <span data-ttu-id="2ea96-123">BTSTask を使用して[ExportApp コマンド](../core/exportapp-command.md)アプリケーションのアイテムを .msi ファイルにエクスポートする CreateApplicationSample.msi という名前です。</span><span class="sxs-lookup"><span data-stu-id="2ea96-123">Uses the BTSTask [ExportApp command](../core/exportapp-command.md) to export the application's artifacts into an .msi file named CreateApplicationSample.msi.</span></span>  
  
    4.  <span data-ttu-id="2ea96-124">BTSTask を使用して[ListApp コマンド](../core/listapp-command.md)をすべてのアプリケーションに含まれているアイテムの一覧を表示する、AppManifest.xml という名前のアプリケーション マニフェストを生成します。</span><span class="sxs-lookup"><span data-stu-id="2ea96-124">Uses the BTSTask [ListApp Command](../core/listapp-command.md) to generate an application manifest named AppManifest.xml, which lists all of the artifacts contained in the application.</span></span>  
  
    5.  <span data-ttu-id="2ea96-125">BTSTask を使用して[ExportApp コマンド](../core/exportapp-command.md)CreateApplicationSamplePartial.msi という名前の .msi ファイルに、オーケストレーション アセンブリのみをエクスポートします。</span><span class="sxs-lookup"><span data-stu-id="2ea96-125">Uses the BTSTask [ExportApp command](../core/exportapp-command.md) to export only the orchestrations assembly into an .msi file named CreateApplicationSamplePartial.msi.</span></span> <span data-ttu-id="2ea96-126">これは、ResourceSpec パラメーターに ResourceSpecPartial.xml を指定することによって行われます。</span><span class="sxs-lookup"><span data-stu-id="2ea96-126">It does this by providing ResourceSpecPartial.xml for the ResourceSpec parameter.</span></span> <span data-ttu-id="2ea96-127">ResouceSpecPartial.xml は、このサンプルに含まれている ResourceSpecComplete.xml の編集されたバージョンです。</span><span class="sxs-lookup"><span data-stu-id="2ea96-127">ResouceSpecPartial.xml is an edited version of ResourceSpecComplete.xml that has been provided with this sample.</span></span> <span data-ttu-id="2ea96-128">このファイルは、オーケストレーション アセンブリのみの参照が含まれるように編集されています。</span><span class="sxs-lookup"><span data-stu-id="2ea96-128">This file has been edited so that it contains a reference to the orchestrations assembly only.</span></span> <span data-ttu-id="2ea96-129">このパラメーターがある場合、BTSTask は ResourceSpecPartial.xml ファイル (この場合はオーケストレーション アセンブリ) にリストされているアイテムのみをエクスポートします。</span><span class="sxs-lookup"><span data-stu-id="2ea96-129">When provided with this parameter, BTSTask exports only the artifacts listed in the ResourceSpecPartial.xml file – in this case, the orchestrations assembly.</span></span>  
  
    6.  <span data-ttu-id="2ea96-130">グループの BizTalk 管理データベースからアプリケーションを削除します。</span><span class="sxs-lookup"><span data-stu-id="2ea96-130">Deletes the application from the BizTalk Management database for the group.</span></span>  
  
-   <span data-ttu-id="2ea96-131">**CreateNewAppFromMSI.bat です。**</span><span class="sxs-lookup"><span data-stu-id="2ea96-131">**CreateNewAppFromMSI.bat.**</span></span> <span data-ttu-id="2ea96-132">CreateFullAndPartialMSI.bat によって生成された CreateApplicationSample.msi を使用して、ローカル コンピュータに CreateApplicationSample という名前のアプリケーションをインストールすると共に、BizTalk グループにアプリケーションをインポートします。</span><span class="sxs-lookup"><span data-stu-id="2ea96-132">Uses CreateApplicationSample.msi generated by CreateFullAndPartialMSI.bat to install an application named CreateApplicationSample on the local computer as well as import the application into the BizTalk group.</span></span> <span data-ttu-id="2ea96-133">インストール中に、PreProcScript.bat は後の説明に従って、自動的に実行されます。</span><span class="sxs-lookup"><span data-stu-id="2ea96-133">During installation, PreProcScript.bat runs automatically, as described later.</span></span>  
  
-   <span data-ttu-id="2ea96-134">**RemoveApp.bat です。**</span><span class="sxs-lookup"><span data-stu-id="2ea96-134">**RemoveApp.bat.**</span></span> <span data-ttu-id="2ea96-135">以下の処理を順番に実行します。</span><span class="sxs-lookup"><span data-stu-id="2ea96-135">Takes the following actions, in order:</span></span>  
  
    1.  <span data-ttu-id="2ea96-136">BTSTask を使用して[RemoveApp コマンド](../core/removeapp-command.md)グループの BizTalk 管理データベースから CreateApplicationSample アプリケーションを削除します。</span><span class="sxs-lookup"><span data-stu-id="2ea96-136">Uses the BTSTask [RemoveApp Command](../core/removeapp-command.md) to delete the CreateApplicationSample application from the BizTalk Management database for the group.</span></span>  
  
    2.  <span data-ttu-id="2ea96-137">BTSTask を使用して[UninstallApp コマンド](../core/uninstallapp-command.md)をローカル コンピューターから、CreateApplicationSample アプリケーションをアンインストールします。</span><span class="sxs-lookup"><span data-stu-id="2ea96-137">Uses the BTSTask [UninstallApp Command](../core/uninstallapp-command.md) to uninstall the CreateApplicationSample application from the local computer.</span></span> <span data-ttu-id="2ea96-138">インストール中は、後で説明するように PreProcScript.bat が自動的に実行されます。</span><span class="sxs-lookup"><span data-stu-id="2ea96-138">During installation, PreProcScript.bat runs automatically, as described next.</span></span>  
  
-   <span data-ttu-id="2ea96-139">**PreProcScript.bat です。**</span><span class="sxs-lookup"><span data-stu-id="2ea96-139">**PreProcScript.bat.**</span></span> <span data-ttu-id="2ea96-140">次の処理を実行します。</span><span class="sxs-lookup"><span data-stu-id="2ea96-140">Takes the following actions:</span></span>  
  
    -   <span data-ttu-id="2ea96-141">実行のたびに、ユーザーに提供されたアセンブリの公開キー トークンを設定します。</span><span class="sxs-lookup"><span data-stu-id="2ea96-141">Each time it runs, sets the public key token for the assembly that has been provided by the user.</span></span>  
  
    -   <span data-ttu-id="2ea96-142">アプリケーションのインストール中、CreateApplicationSample アプリケーションがメッセージを格納するために使用する次のフォルダを作成します。</span><span class="sxs-lookup"><span data-stu-id="2ea96-142">During application installation, creates the following folders that will be used by the CreateApplicationSample application to contain messages:</span></span>  
  
         <span data-ttu-id="2ea96-143">C:\CreateApplicationSample\Out</span><span class="sxs-lookup"><span data-stu-id="2ea96-143">C:\CreateApplicationSample\Out</span></span>  
  
         <span data-ttu-id="2ea96-144">C:\CreateApplicationSample\In</span><span class="sxs-lookup"><span data-stu-id="2ea96-144">C:\CreateApplicationSample\In</span></span>  
  
    -   <span data-ttu-id="2ea96-145">アプリケーションのアンインストール中、インストール中に作成されたファイルおよびフォルダを削除します。</span><span class="sxs-lookup"><span data-stu-id="2ea96-145">During application uninstallation, deletes the files and folders that were created during installation.</span></span> <span data-ttu-id="2ea96-146">インストール中にグローバル アセンブリ キャッシュ (GAC) にインストールされたアセンブリをアンインストールし、ファイルにアクションのログを記録します。</span><span class="sxs-lookup"><span data-stu-id="2ea96-146">Also uninstalls from the global assembly cache (GAC) any assemblies that were installed in the GAC during installation and logs its actions to a file.</span></span> <span data-ttu-id="2ea96-147">GAC からアセンブリをアンインストールするために、ユーザーが提供した公開キー トークンを参照します。</span><span class="sxs-lookup"><span data-stu-id="2ea96-147">To uninstall the assemblies from the GAC, it refers to the public key token provided by the user.</span></span>  
  
    -   <span data-ttu-id="2ea96-148">インストールおよびアンインストール中、次の場所にログ ファイルを作成します。</span><span class="sxs-lookup"><span data-stu-id="2ea96-148">During both installation and uninstallation, creates a log file in the following location:</span></span>  
  
         <span data-ttu-id="2ea96-149">C:\ScriptLog.txt</span><span class="sxs-lookup"><span data-stu-id="2ea96-149">C:\ScriptLog.txt</span></span>  
  
## <a name="where-to-find-this-sample"></a><span data-ttu-id="2ea96-150">このサンプルの場所</span><span class="sxs-lookup"><span data-stu-id="2ea96-150">Where to Find This Sample</span></span>  
 <span data-ttu-id="2ea96-151">次のフォルダーにサンプル ファイルを検索できる*\<サンプル パス\>*\Application 展開\\:</span><span class="sxs-lookup"><span data-stu-id="2ea96-151">You can find the sample files in the following folders under *\<Samples Path\>*\Application Deployment\\:</span></span>  
  
-   <span data-ttu-id="2ea96-152">CreateApp (フォルダ)</span><span class="sxs-lookup"><span data-stu-id="2ea96-152">CreateApp (Folder)</span></span>  
  
    -   <span data-ttu-id="2ea96-153">Build.bat</span><span class="sxs-lookup"><span data-stu-id="2ea96-153">Build.bat</span></span>  
  
    -   <span data-ttu-id="2ea96-154">CreateFullAndPartialMSI.bat</span><span class="sxs-lookup"><span data-stu-id="2ea96-154">CreateFullAndPartialMSI.bat</span></span>  
  
    -   <span data-ttu-id="2ea96-155">CreateNewAppFromMSI.bat</span><span class="sxs-lookup"><span data-stu-id="2ea96-155">CreateNewAppFromMSI.bat</span></span>  
  
    -   <span data-ttu-id="2ea96-156">RemoveApp.bat</span><span class="sxs-lookup"><span data-stu-id="2ea96-156">RemoveApp.bat</span></span>  
  
-   <span data-ttu-id="2ea96-157">CreateApp\Bindings (フォルダ)</span><span class="sxs-lookup"><span data-stu-id="2ea96-157">CreateApp\Bindings (Folder)</span></span>  
  
    -   <span data-ttu-id="2ea96-158">CreateApplicationSampleBindings.xml</span><span class="sxs-lookup"><span data-stu-id="2ea96-158">CreateApplicationSampleBindings.xml</span></span>  
  
-   <span data-ttu-id="2ea96-159">CreateApp\Dlls (フォルダ)</span><span class="sxs-lookup"><span data-stu-id="2ea96-159">CreateApp\Dlls (Folder)</span></span>  
  
    -   <span data-ttu-id="2ea96-160">空</span><span class="sxs-lookup"><span data-stu-id="2ea96-160">Empty</span></span>  
  
-   <span data-ttu-id="2ea96-161">CreateApp\ResourceSpecs (フォルダ)</span><span class="sxs-lookup"><span data-stu-id="2ea96-161">CreateApp\ResourceSpecs (Folder)</span></span>  
  
    -   <span data-ttu-id="2ea96-162">ResourceSpecPartial.xml</span><span class="sxs-lookup"><span data-stu-id="2ea96-162">ResourceSpecPartial.xml</span></span>  
  
    -   <span data-ttu-id="2ea96-163">ResourceSpecComplete.xml</span><span class="sxs-lookup"><span data-stu-id="2ea96-163">ResourceSpecComplete.xml</span></span>  
  
-   <span data-ttu-id="2ea96-164">CreateApp\Scripts (フォルダ)</span><span class="sxs-lookup"><span data-stu-id="2ea96-164">CreateApp\Scripts (Folder)</span></span>  
  
    -   <span data-ttu-id="2ea96-165">PreProcScript.bat</span><span class="sxs-lookup"><span data-stu-id="2ea96-165">PreProcScript.bat</span></span>  
  
-   <span data-ttu-id="2ea96-166">CreateApp\HelloApplicationDeployment (フォルダ)</span><span class="sxs-lookup"><span data-stu-id="2ea96-166">CreateApp\HelloApplicationDeployment (Folder)</span></span>  
  
    -   <span data-ttu-id="2ea96-167">HelloApplicationDeployment.suo</span><span class="sxs-lookup"><span data-stu-id="2ea96-167">HelloApplicationDeployment.suo</span></span>  
  
    -   <span data-ttu-id="2ea96-168">HelloApplicationDeployment.sln</span><span class="sxs-lookup"><span data-stu-id="2ea96-168">HelloApplicationDeployment.sln</span></span>  
  
-   <span data-ttu-id="2ea96-169">CreateApp\HelloApplicationDeployment\Maps (フォルダ)</span><span class="sxs-lookup"><span data-stu-id="2ea96-169">CreateApp\HelloApplicationDeployment\Maps (Folder)</span></span>  
  
    -   <span data-ttu-id="2ea96-170">POToInvoice.btm</span><span class="sxs-lookup"><span data-stu-id="2ea96-170">POToInvoice.btm</span></span>  
  
    -   <span data-ttu-id="2ea96-171">Maps.btproj</span><span class="sxs-lookup"><span data-stu-id="2ea96-171">Maps.btproj</span></span>  
  
-   <span data-ttu-id="2ea96-172">CreateApp\HelloApplicationDeployment\Orchestrations (フォルダ)</span><span class="sxs-lookup"><span data-stu-id="2ea96-172">CreateApp\HelloApplicationDeployment\Orchestrations (Folder)</span></span>  
  
    -   <span data-ttu-id="2ea96-173">Orchestrations.btproj</span><span class="sxs-lookup"><span data-stu-id="2ea96-173">Orchestrations.btproj</span></span>  
  
    -   <span data-ttu-id="2ea96-174">HelloOrchestration.odx</span><span class="sxs-lookup"><span data-stu-id="2ea96-174">HelloOrchestration.odx</span></span>  
  
-   <span data-ttu-id="2ea96-175">CreateApp\HelloApplicationDeployment\Schemas (フォルダ)</span><span class="sxs-lookup"><span data-stu-id="2ea96-175">CreateApp\HelloApplicationDeployment\Schemas (Folder)</span></span>  
  
    -   <span data-ttu-id="2ea96-176">Schemas.btproj</span><span class="sxs-lookup"><span data-stu-id="2ea96-176">Schemas.btproj</span></span>  
  
    -   <span data-ttu-id="2ea96-177">POSchema.xsd</span><span class="sxs-lookup"><span data-stu-id="2ea96-177">POSchema.xsd</span></span>  
  
    -   <span data-ttu-id="2ea96-178">InvoiceSchema.xsd</span><span class="sxs-lookup"><span data-stu-id="2ea96-178">InvoiceSchema.xsd</span></span>  
  
## <a name="how-to-use-this-sample"></a><span data-ttu-id="2ea96-179">このサンプルの使用方法</span><span class="sxs-lookup"><span data-stu-id="2ea96-179">How to Use This Sample</span></span>  
 <span data-ttu-id="2ea96-180">次の手順に従って、このサンプルを使用します。</span><span class="sxs-lookup"><span data-stu-id="2ea96-180">Use the following procedure to use this sample.</span></span>  
  
### <a name="to-use-the-sample"></a><span data-ttu-id="2ea96-181">サンプルを使用するには</span><span class="sxs-lookup"><span data-stu-id="2ea96-181">To use the sample</span></span>  
  
1.  <span data-ttu-id="2ea96-182">Build.bat を実行します。</span><span class="sxs-lookup"><span data-stu-id="2ea96-182">Run Build.bat.</span></span> <span data-ttu-id="2ea96-183">これにより、キー ファイルの生成、HelloApplicationDeployment フォルダでのプロジェクトのビルド、結果の .dll ファイルの署名、Dlls フォルダへの .dll ファイルの配置が行われます。</span><span class="sxs-lookup"><span data-stu-id="2ea96-183">This generates a key file, builds the projects under the folder HelloApplicationDeployment, signs the resulting .dll files, and places the.dll files in the Dlls folder.</span></span>  
  
2.  <span data-ttu-id="2ea96-184">CreateApp\Scripts フォルダにある PreProcScript.bat ファイルを開きます。</span><span class="sxs-lookup"><span data-stu-id="2ea96-184">Open the PreProcScript.bat file, which is located in the CreateApp\Scripts folder.</span></span> <span data-ttu-id="2ea96-185">次のコードで、REM を削除し、アセンブリの公開キー トークンを入力します。</span><span class="sxs-lookup"><span data-stu-id="2ea96-185">In the following line of code, remove REM and provide the public key token for the assembly:</span></span>  
  
     <span data-ttu-id="2ea96-186">**REM 設定 PublicKeyToken =**</span><span class="sxs-lookup"><span data-stu-id="2ea96-186">**REM set PublicKeyToken=**</span></span>  
  
     <span data-ttu-id="2ea96-187">例:</span><span class="sxs-lookup"><span data-stu-id="2ea96-187">Example:</span></span>  
  
     <span data-ttu-id="2ea96-188">**設定 PublicKeyToken 1234a5b6c1234567 を =**</span><span class="sxs-lookup"><span data-stu-id="2ea96-188">**set PublicKeyToken=1234a5b6c1234567**</span></span>  
  
3.  <span data-ttu-id="2ea96-189">CreateFullAndPartialMSI.bat を実行します。</span><span class="sxs-lookup"><span data-stu-id="2ea96-189">Run CreateFullAndPartialMSI.bat.</span></span> <span data-ttu-id="2ea96-190">これにより、CreateApplicationSample.msi と CreateApplicationSamplePartial.msi の 2 つのアプリケーション .msi ファイルが作成されます。</span><span class="sxs-lookup"><span data-stu-id="2ea96-190">This creates two application .msi files, CreateApplicationSample.msi and CreateApplicationSamplePartial.msi.</span></span>  
  
4.  <span data-ttu-id="2ea96-191">CreateNewAppFromMSI.bat を実行します。</span><span class="sxs-lookup"><span data-stu-id="2ea96-191">Run CreateNewAppFromMSI.bat.</span></span> <span data-ttu-id="2ea96-192">これにより、CreateApplicationSample アプリケーションが BizTalk グループにインポートされ、ローカル コンピュータにインストールされます。</span><span class="sxs-lookup"><span data-stu-id="2ea96-192">This imports the CreateApplicationSample application into the BizTalk group and installs it on the local computer.</span></span>  
  
5.  <span data-ttu-id="2ea96-193">C:\ScriptLog.txt にあるスクリプト ログ ファイルをチェックし、スクリプトによってインストール アクションのログが記録されたかどうかを確認します。</span><span class="sxs-lookup"><span data-stu-id="2ea96-193">Check the script log file, located at C:\ScriptLog.txt to verify that the script logged its installation actions.</span></span>  
  
6.  <span data-ttu-id="2ea96-194">CreateApplicationSample アプリケーションが BizTalk Server 管理コンソールおよび [アプリケーションの追加と削除] に表示されているかどうかを確認します。</span><span class="sxs-lookup"><span data-stu-id="2ea96-194">Verify that the CreateApplicationSample application appears both in the BizTalk Server Administration console and Add or Remove Programs.</span></span>  
  
7.  <span data-ttu-id="2ea96-195">RemoveApp.bat を実行します。</span><span class="sxs-lookup"><span data-stu-id="2ea96-195">Run RemoveApp.bat.</span></span> <span data-ttu-id="2ea96-196">これにより、CreateApplicationSample が BizTalk 管理データベースから削除され、ローカル コンピュータからアンインストールされます。</span><span class="sxs-lookup"><span data-stu-id="2ea96-196">This deletes the CreateApplicationSample from the BizTalk Management database and uninstalls it from the local computer.</span></span>  
  
8.  <span data-ttu-id="2ea96-197">C:\ScriptLog.txt にあるスクリプト ログ ファイルをチェックし、スクリプトによってアンインストール アクションのログが記録されたかどうかを確認します。</span><span class="sxs-lookup"><span data-stu-id="2ea96-197">Check the script log file, located at C:\ScriptLog.txt to verify that the script logged its uninstallation actions.</span></span> <span data-ttu-id="2ea96-198">このログは、インストール中に記録されたインストール アクションの後に表示されます。</span><span class="sxs-lookup"><span data-stu-id="2ea96-198">They should appear after the installation actions logged earlier, during installation.</span></span>  
  
9. <span data-ttu-id="2ea96-199">CreateApplicationSample アプリケーションが BizTalk Server 管理コンソールおよび [アプリケーションの追加と削除] に表示されていないことを確認します。</span><span class="sxs-lookup"><span data-stu-id="2ea96-199">Verify that the CreateApplicationSample application no longer appears in either the BizTalk Server Administration console or Add or Remove Programs.</span></span>  
  
10. <span data-ttu-id="2ea96-200">インストール中に作成されたフォルダが削除されているかどうかを確認します。</span><span class="sxs-lookup"><span data-stu-id="2ea96-200">Verify that the folders that were created during installation have been deleted.</span></span>  
  
11. <span data-ttu-id="2ea96-201">アセンブリが GAC からアンインストールされているかどうかを確認します。</span><span class="sxs-lookup"><span data-stu-id="2ea96-201">Verify that the assemblies have been uninstalled from the GAC.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="2ea96-202">参照</span><span class="sxs-lookup"><span data-stu-id="2ea96-202">See Also</span></span>  
 <span data-ttu-id="2ea96-203">[アプリケーションの展開 (BizTalk Server Samples フォルダ)](../core/application-deployment-biztalk-server-samples-folder.md) </span><span class="sxs-lookup"><span data-stu-id="2ea96-203">[Application Deployment (BizTalk Server Samples Folder)](../core/application-deployment-biztalk-server-samples-folder.md) </span></span>  
 [<span data-ttu-id="2ea96-204">BizTalk アプリケーションの展開</span><span class="sxs-lookup"><span data-stu-id="2ea96-204">Deploying BizTalk Applications</span></span>](../core/deploying-biztalk-applications.md)