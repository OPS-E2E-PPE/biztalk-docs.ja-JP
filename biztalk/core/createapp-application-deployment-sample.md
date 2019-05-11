---
title: CreateApp (アプリケーションの展開サンプル) |Microsoft Docs
ms.custom: ''
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: ''
ms.suite: ''
ms.tgt_pltfrm: ''
ms.topic: article
helpviewer_keywords:
- deploying, examples
- deploying, .msi file
- deploying, exporting
- .msi files, deploying
- examples, deploying
ms.assetid: 825627ee-21d0-4505-9df4-1dadc51335b6
caps.latest.revision: 14
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: ce2b895b11a8a2ad0fc6b863d3cd67a20c5c1007
ms.sourcegitcommit: 381e83d43796a345488d54b3f7413e11d56ad7be
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 05/07/2019
ms.locfileid: "65354178"
---
# <a name="createapp-application-deployment-sample"></a><span data-ttu-id="1e716-102">CreateApp (アプリケーションの展開サンプル)</span><span class="sxs-lookup"><span data-stu-id="1e716-102">CreateApp (Application Deployment Sample)</span></span>
<span data-ttu-id="1e716-103">このトピックでは、CreateApp サンプルは、BTSTask コマンド ライン ツールを使用して、展開および BizTalk アプリケーションを展開解除する方法を使用する方法について説明します。</span><span class="sxs-lookup"><span data-stu-id="1e716-103">This topic explains how to use the CreateApp sample, which demonstrates using the BTSTask command-line tool to deploy and undeploy a BizTalk application.</span></span> <span data-ttu-id="1e716-104">このサンプルに含まれるものなどのスクリプトを使用して、デプロイし、BizTalk アプリケーションの展開を解除し、夜間ビルド プロセスを自動化する可能性があります。</span><span class="sxs-lookup"><span data-stu-id="1e716-104">You could use scripts such as those included in this sample to automate your nightly build process to deploy and undeploy BizTalk applications.</span></span>  
  
> [!IMPORTANT]
>  <span data-ttu-id="1e716-105">いつでも、サイレント モードで実行する配置スクリプトを記述する必要があります。</span><span class="sxs-lookup"><span data-stu-id="1e716-105">You should always write your deployment scripts to run in silent mode.</span></span> <span data-ttu-id="1e716-106">そうでない場合は、ユーザー入力を必要とするダイアログ ボックスが表示されます。</span><span class="sxs-lookup"><span data-stu-id="1e716-106">If you do not, dialog boxes will display that require user input.</span></span> <span data-ttu-id="1e716-107">ダイアログ ボックスを手動で閉じると、インポート プロセスがハングアップする可能性があるまで、展開プロセスを停止します。</span><span class="sxs-lookup"><span data-stu-id="1e716-107">This will stop the deployment process until the dialog box is manually dismissed, which can cause the import process to hang.</span></span>  
  
## <a name="what-this-sample-does"></a><span data-ttu-id="1e716-108">このサンプルの処理</span><span class="sxs-lookup"><span data-stu-id="1e716-108">What This Sample Does</span></span>  
 <span data-ttu-id="1e716-109">このサンプルには、アプリケーション展開タスクを自動化するスクリプトが含まれます。</span><span class="sxs-lookup"><span data-stu-id="1e716-109">The sample includes scripts that automate application deployment tasks.</span></span> <span data-ttu-id="1e716-110">これらのタスクを実行するには、BizTalk プロジェクトとファイルを生成するスクリプトを実行します。</span><span class="sxs-lookup"><span data-stu-id="1e716-110">To perform these tasks, you run a script that generates the BizTalk project and files.</span></span> <span data-ttu-id="1e716-111">2 つの BizTalk アプリケーションの .msi ファイル – すべてのアプリケーションで 1 つだけのアセンブリを含む、アプリケーションと別のアイテムを含む .msi ファイルを生成するスクリプトを実行します。</span><span class="sxs-lookup"><span data-stu-id="1e716-111">Then you run a script that generates two BizTalk application .msi files – an .msi file that contains all of the artifacts in an application, and another that contains only one assembly in the application.</span></span> <span data-ttu-id="1e716-112">次に、BizTalk グループにアプリケーションをインポートして、ローカル コンピューター上にアプリケーションをインストールする .msi ファイルを使用するスクリプトを実行します。</span><span class="sxs-lookup"><span data-stu-id="1e716-112">Next you run a script that uses an .msi file to import an application into a BizTalk group and install the application onto the local computer.</span></span> <span data-ttu-id="1e716-113">インストール中には、処理前のスクリプトをアプリケーションに含まれるはアプリケーションによって使用されるフォルダーを作成し、ファイルにその操作を記録します。</span><span class="sxs-lookup"><span data-stu-id="1e716-113">During installation, a pre-processing script included in the application creates folders used by the application and logs its actions to a file.</span></span> <span data-ttu-id="1e716-114">最後に、削除し、アプリケーションをアンインストールするスクリプトを実行します。</span><span class="sxs-lookup"><span data-stu-id="1e716-114">Finally, you run a script that deletes and uninstalls the application.</span></span> <span data-ttu-id="1e716-115">アンインストール中は、アプリケーションに含まれる処理前のスクリプトは、ファイルとフォルダーのインストール時に作成されたを削除し、ファイルにその操作を記録します。</span><span class="sxs-lookup"><span data-stu-id="1e716-115">During uninstallation, a pre-processing script included in the application removes the files and folders that were created during installation and logs its actions to a file.</span></span>  
  
 <span data-ttu-id="1e716-116">次に、このサンプルに含まれているスクリプトを示します。</span><span class="sxs-lookup"><span data-stu-id="1e716-116">The following are the scripts included with this sample:</span></span>  
  
-   <span data-ttu-id="1e716-117">**Build.bat します。**</span><span class="sxs-lookup"><span data-stu-id="1e716-117">**Build.bat.**</span></span> <span data-ttu-id="1e716-118">キー ファイルが生成され、Visual Studio でプロジェクトをビルド、.dll ファイルに署名します。</span><span class="sxs-lookup"><span data-stu-id="1e716-118">Generates a key file, builds the project in Visual Studio, and signs the .dll files.</span></span>  
  
-   <span data-ttu-id="1e716-119">**CreateFullAndPartialMSI.bat.**</span><span class="sxs-lookup"><span data-stu-id="1e716-119">**CreateFullAndPartialMSI.bat.**</span></span> <span data-ttu-id="1e716-120">順序で、次の操作を受け取ります。</span><span class="sxs-lookup"><span data-stu-id="1e716-120">Takes the following actions, in order:</span></span>  
  
    1.  <span data-ttu-id="1e716-121">BTSTask を使用して[AddApp コマンド](../core/addapp-command.md)アプリケーションを作成します。</span><span class="sxs-lookup"><span data-stu-id="1e716-121">Uses the BTSTask [AddApp command](../core/addapp-command.md) to create an application.</span></span>  
  
    2.  <span data-ttu-id="1e716-122">BTSTask を使用して[AddResource コマンド](../core/addresource-command.md)Build.bat によって生成されたや他のリソースをアプリケーション 3 つの BizTalk アセンブリに追加します。</span><span class="sxs-lookup"><span data-stu-id="1e716-122">Uses the BTSTask [AddResource command](../core/addresource-command.md) to add to the application three BizTalk assemblies as well as other resources that were generated by Build.bat.</span></span>  
  
    3.  <span data-ttu-id="1e716-123">BTSTask を使用して[ExportApp コマンド](../core/exportapp-command.md)CreateApplicationSample.msi という名前のアプリケーションのアイテムを .msi ファイルにエクスポートします。</span><span class="sxs-lookup"><span data-stu-id="1e716-123">Uses the BTSTask [ExportApp command](../core/exportapp-command.md) to export the application's artifacts into an .msi file named CreateApplicationSample.msi.</span></span>  
  
    4.  <span data-ttu-id="1e716-124">BTSTask を使用して[ListApp コマンド](../core/listapp-command.md)をアプリケーションに含まれるアイテムの一覧が表示、AppManifest.xml という名前のアプリケーション マニフェストを生成します。</span><span class="sxs-lookup"><span data-stu-id="1e716-124">Uses the BTSTask [ListApp Command](../core/listapp-command.md) to generate an application manifest named AppManifest.xml, which lists all of the artifacts contained in the application.</span></span>  
  
    5.  <span data-ttu-id="1e716-125">BTSTask を使用して[ExportApp コマンド](../core/exportapp-command.md)CreateApplicationSamplePartial.msi という名前の .msi ファイルに、オーケストレーション アセンブリのみをエクスポートします。</span><span class="sxs-lookup"><span data-stu-id="1e716-125">Uses the BTSTask [ExportApp command](../core/exportapp-command.md) to export only the orchestrations assembly into an .msi file named CreateApplicationSamplePartial.msi.</span></span> <span data-ttu-id="1e716-126">この機能を使用するには、ResourceSpec パラメーターに ResourceSpecPartial.xml を提供します。</span><span class="sxs-lookup"><span data-stu-id="1e716-126">It does this by providing ResourceSpecPartial.xml for the ResourceSpec parameter.</span></span> <span data-ttu-id="1e716-127">ResouceSpecPartial.xml が含まれているが、このサンプルで指定されている ResourceSpecComplete.xml の編集済みバージョンです。</span><span class="sxs-lookup"><span data-stu-id="1e716-127">ResouceSpecPartial.xml is an edited version of ResourceSpecComplete.xml that has been provided with this sample.</span></span> <span data-ttu-id="1e716-128">このファイルは、オーケストレーション アセンブリのみへの参照を含むように編集されました。</span><span class="sxs-lookup"><span data-stu-id="1e716-128">This file has been edited so that it contains a reference to the orchestrations assembly only.</span></span> <span data-ttu-id="1e716-129">このパラメーターで指定した場合、BTSTask は ResourceSpecPartial.xml ファイル – ここでは、オーケストレーション アセンブリで表示されているアイテムのみをエクスポートします。</span><span class="sxs-lookup"><span data-stu-id="1e716-129">When provided with this parameter, BTSTask exports only the artifacts listed in the ResourceSpecPartial.xml file – in this case, the orchestrations assembly.</span></span>  
  
    6.  <span data-ttu-id="1e716-130">グループの BizTalk 管理データベースからアプリケーションを削除します。</span><span class="sxs-lookup"><span data-stu-id="1e716-130">Deletes the application from the BizTalk Management database for the group.</span></span>  
  
-   <span data-ttu-id="1e716-131">**CreateNewAppFromMSI.bat します。**</span><span class="sxs-lookup"><span data-stu-id="1e716-131">**CreateNewAppFromMSI.bat.**</span></span> <span data-ttu-id="1e716-132">CreateFullAndPartialMSI.bat によって生成された CreateApplicationSample.msi を使用して、BizTalk グループにアプリケーションをインポートするほか、ローカル コンピューターに CreateApplicationSample という名前のアプリケーションをインストールします。</span><span class="sxs-lookup"><span data-stu-id="1e716-132">Uses CreateApplicationSample.msi generated by CreateFullAndPartialMSI.bat to install an application named CreateApplicationSample on the local computer as well as import the application into the BizTalk group.</span></span> <span data-ttu-id="1e716-133">インストール中に PreProcScript.bat が後の説明に従って、自動的に実行されます。</span><span class="sxs-lookup"><span data-stu-id="1e716-133">During installation, PreProcScript.bat runs automatically, as described later.</span></span>  
  
-   <span data-ttu-id="1e716-134">**RemoveApp.bat.**</span><span class="sxs-lookup"><span data-stu-id="1e716-134">**RemoveApp.bat.**</span></span> <span data-ttu-id="1e716-135">順序で、次の操作を受け取ります。</span><span class="sxs-lookup"><span data-stu-id="1e716-135">Takes the following actions, in order:</span></span>  
  
    1.  <span data-ttu-id="1e716-136">BTSTask を使用して[RemoveApp コマンド](../core/removeapp-command.md)グループの BizTalk 管理データベースから CreateApplicationSample アプリケーションを削除します。</span><span class="sxs-lookup"><span data-stu-id="1e716-136">Uses the BTSTask [RemoveApp Command](../core/removeapp-command.md) to delete the CreateApplicationSample application from the BizTalk Management database for the group.</span></span>  
  
    2.  <span data-ttu-id="1e716-137">BTSTask を使用して[UninstallApp コマンド](../core/uninstallapp-command.md)CreateApplicationSample アプリケーションをローカル コンピューターからアンインストールします。</span><span class="sxs-lookup"><span data-stu-id="1e716-137">Uses the BTSTask [UninstallApp Command](../core/uninstallapp-command.md) to uninstall the CreateApplicationSample application from the local computer.</span></span> <span data-ttu-id="1e716-138">インストール中に PreProcScript.bat はよう自動的に実行されます。</span><span class="sxs-lookup"><span data-stu-id="1e716-138">During installation, PreProcScript.bat runs automatically, as described next.</span></span>  
  
-   <span data-ttu-id="1e716-139">**PreProcScript.bat します。**</span><span class="sxs-lookup"><span data-stu-id="1e716-139">**PreProcScript.bat.**</span></span> <span data-ttu-id="1e716-140">次の操作を実行します。</span><span class="sxs-lookup"><span data-stu-id="1e716-140">Takes the following actions:</span></span>  
  
    -   <span data-ttu-id="1e716-141">たびに、実行、ユーザーが提供されているアセンブリの公開キー トークンを設定します。</span><span class="sxs-lookup"><span data-stu-id="1e716-141">Each time it runs, sets the public key token for the assembly that has been provided by the user.</span></span>  
  
    -   <span data-ttu-id="1e716-142">アプリケーションのインストール中は、メッセージを格納する、CreateApplicationSample アプリケーションによって使用される次のフォルダーを作成します。</span><span class="sxs-lookup"><span data-stu-id="1e716-142">During application installation, creates the following folders that will be used by the CreateApplicationSample application to contain messages:</span></span>  
  
         <span data-ttu-id="1e716-143">C:\CreateApplicationSample\Out</span><span class="sxs-lookup"><span data-stu-id="1e716-143">C:\CreateApplicationSample\Out</span></span>  
  
         <span data-ttu-id="1e716-144">C:\CreateApplicationSample\In</span><span class="sxs-lookup"><span data-stu-id="1e716-144">C:\CreateApplicationSample\In</span></span>  
  
    -   <span data-ttu-id="1e716-145">アプリケーションのアンインストール中には、ファイルおよびインストール中に作成されたフォルダーを削除します。</span><span class="sxs-lookup"><span data-stu-id="1e716-145">During application uninstallation, deletes the files and folders that were created during installation.</span></span> <span data-ttu-id="1e716-146">インストール時に GAC にインストールされているすべてのアセンブリをグローバル アセンブリ キャッシュ (GAC) からアンインストールし、そのアクションをファイルにログインします。</span><span class="sxs-lookup"><span data-stu-id="1e716-146">Also uninstalls from the global assembly cache (GAC) any assemblies that were installed in the GAC during installation and logs its actions to a file.</span></span> <span data-ttu-id="1e716-147">GAC からアセンブリをアンインストールするにはユーザーによって提供される公開キー トークンを指します。</span><span class="sxs-lookup"><span data-stu-id="1e716-147">To uninstall the assemblies from the GAC, it refers to the public key token provided by the user.</span></span>  
  
    -   <span data-ttu-id="1e716-148">インストールおよびアンインストール中には、次の場所にログ ファイルを作成します。</span><span class="sxs-lookup"><span data-stu-id="1e716-148">During both installation and uninstallation, creates a log file in the following location:</span></span>  
  
         <span data-ttu-id="1e716-149">C:\ScriptLog.txt</span><span class="sxs-lookup"><span data-stu-id="1e716-149">C:\ScriptLog.txt</span></span>  
  
## <a name="where-to-find-this-sample"></a><span data-ttu-id="1e716-150">このサンプルの場所</span><span class="sxs-lookup"><span data-stu-id="1e716-150">Where to Find This Sample</span></span>  
 <span data-ttu-id="1e716-151">次のフォルダーにサンプル ファイルを検索できる*\<サンプル パス\>* \Application Deployment\\:</span><span class="sxs-lookup"><span data-stu-id="1e716-151">You can find the sample files in the following folders under *\<Samples Path\>* \Application Deployment\\:</span></span>  
  
-   <span data-ttu-id="1e716-152">CreateApp (フォルダ)</span><span class="sxs-lookup"><span data-stu-id="1e716-152">CreateApp (Folder)</span></span>  
  
    -   <span data-ttu-id="1e716-153">Build.bat</span><span class="sxs-lookup"><span data-stu-id="1e716-153">Build.bat</span></span>  
  
    -   <span data-ttu-id="1e716-154">CreateFullAndPartialMSI.bat</span><span class="sxs-lookup"><span data-stu-id="1e716-154">CreateFullAndPartialMSI.bat</span></span>  
  
    -   <span data-ttu-id="1e716-155">CreateNewAppFromMSI.bat</span><span class="sxs-lookup"><span data-stu-id="1e716-155">CreateNewAppFromMSI.bat</span></span>  
  
    -   <span data-ttu-id="1e716-156">RemoveApp.bat</span><span class="sxs-lookup"><span data-stu-id="1e716-156">RemoveApp.bat</span></span>  
  
-   <span data-ttu-id="1e716-157">CreateApp\Bindings (Folder)</span><span class="sxs-lookup"><span data-stu-id="1e716-157">CreateApp\Bindings (Folder)</span></span>  
  
    -   <span data-ttu-id="1e716-158">CreateApplicationSampleBindings.xml</span><span class="sxs-lookup"><span data-stu-id="1e716-158">CreateApplicationSampleBindings.xml</span></span>  
  
-   <span data-ttu-id="1e716-159">Createapp \dlls (フォルダ)</span><span class="sxs-lookup"><span data-stu-id="1e716-159">CreateApp\Dlls (Folder)</span></span>  
  
    -   <span data-ttu-id="1e716-160">空</span><span class="sxs-lookup"><span data-stu-id="1e716-160">Empty</span></span>  
  
-   <span data-ttu-id="1e716-161">Createapp \resourcespecs (フォルダ)</span><span class="sxs-lookup"><span data-stu-id="1e716-161">CreateApp\ResourceSpecs (Folder)</span></span>  
  
    -   <span data-ttu-id="1e716-162">ResourceSpecPartial.xml</span><span class="sxs-lookup"><span data-stu-id="1e716-162">ResourceSpecPartial.xml</span></span>  
  
    -   <span data-ttu-id="1e716-163">ResourceSpecComplete.xml</span><span class="sxs-lookup"><span data-stu-id="1e716-163">ResourceSpecComplete.xml</span></span>  
  
-   <span data-ttu-id="1e716-164">CreateApp\Scripts (Folder)</span><span class="sxs-lookup"><span data-stu-id="1e716-164">CreateApp\Scripts (Folder)</span></span>  
  
    -   <span data-ttu-id="1e716-165">PreProcScript.bat</span><span class="sxs-lookup"><span data-stu-id="1e716-165">PreProcScript.bat</span></span>  
  
-   <span data-ttu-id="1e716-166">Createapp \helloapplicationdeployment (フォルダ)</span><span class="sxs-lookup"><span data-stu-id="1e716-166">CreateApp\HelloApplicationDeployment (Folder)</span></span>  
  
    -   <span data-ttu-id="1e716-167">HelloApplicationDeployment.suo</span><span class="sxs-lookup"><span data-stu-id="1e716-167">HelloApplicationDeployment.suo</span></span>  
  
    -   <span data-ttu-id="1e716-168">HelloApplicationDeployment.sln</span><span class="sxs-lookup"><span data-stu-id="1e716-168">HelloApplicationDeployment.sln</span></span>  
  
-   <span data-ttu-id="1e716-169">CreateApp\HelloApplicationDeployment\Maps (Folder)</span><span class="sxs-lookup"><span data-stu-id="1e716-169">CreateApp\HelloApplicationDeployment\Maps (Folder)</span></span>  
  
    -   <span data-ttu-id="1e716-170">POToInvoice.btm</span><span class="sxs-lookup"><span data-stu-id="1e716-170">POToInvoice.btm</span></span>  
  
    -   <span data-ttu-id="1e716-171">Maps.btproj</span><span class="sxs-lookup"><span data-stu-id="1e716-171">Maps.btproj</span></span>  
  
-   <span data-ttu-id="1e716-172">CreateApp\HelloApplicationDeployment\Orchestrations (Folder)</span><span class="sxs-lookup"><span data-stu-id="1e716-172">CreateApp\HelloApplicationDeployment\Orchestrations (Folder)</span></span>  
  
    -   <span data-ttu-id="1e716-173">Orchestrations.btproj</span><span class="sxs-lookup"><span data-stu-id="1e716-173">Orchestrations.btproj</span></span>  
  
    -   <span data-ttu-id="1e716-174">HelloOrchestration.odx</span><span class="sxs-lookup"><span data-stu-id="1e716-174">HelloOrchestration.odx</span></span>  
  
-   <span data-ttu-id="1e716-175">Createapp \helloapplicationdeployment\schemas (フォルダ)</span><span class="sxs-lookup"><span data-stu-id="1e716-175">CreateApp\HelloApplicationDeployment\Schemas (Folder)</span></span>  
  
    -   <span data-ttu-id="1e716-176">Schemas.btproj</span><span class="sxs-lookup"><span data-stu-id="1e716-176">Schemas.btproj</span></span>  
  
    -   <span data-ttu-id="1e716-177">POSchema.xsd</span><span class="sxs-lookup"><span data-stu-id="1e716-177">POSchema.xsd</span></span>  
  
    -   <span data-ttu-id="1e716-178">InvoiceSchema.xsd</span><span class="sxs-lookup"><span data-stu-id="1e716-178">InvoiceSchema.xsd</span></span>  
  
## <a name="how-to-use-this-sample"></a><span data-ttu-id="1e716-179">このサンプルの使用方法</span><span class="sxs-lookup"><span data-stu-id="1e716-179">How to Use This Sample</span></span>  
 <span data-ttu-id="1e716-180">このサンプルを使用するのにには、次の手順を使用します。</span><span class="sxs-lookup"><span data-stu-id="1e716-180">Use the following procedure to use this sample.</span></span>  
  
### <a name="to-use-the-sample"></a><span data-ttu-id="1e716-181">サンプルを使用するには</span><span class="sxs-lookup"><span data-stu-id="1e716-181">To use the sample</span></span>  
  
1.  <span data-ttu-id="1e716-182">Build.bat を実行します。</span><span class="sxs-lookup"><span data-stu-id="1e716-182">Run Build.bat.</span></span> <span data-ttu-id="1e716-183">これは、コマンドで、キー ファイルを生成、HelloApplicationDeployment フォルダーの下のプロジェクトのビルド、結果の .dll ファイルに署名、および、Dlls フォルダに行われますファイルを配置します。</span><span class="sxs-lookup"><span data-stu-id="1e716-183">This generates a key file, builds the projects under the folder HelloApplicationDeployment, signs the resulting .dll files, and places the.dll files in the Dlls folder.</span></span>  
  
2.  <span data-ttu-id="1e716-184">Createapp \scripts フォルダにある PreProcScript.bat ファイルを開きます。</span><span class="sxs-lookup"><span data-stu-id="1e716-184">Open the PreProcScript.bat file, which is located in the CreateApp\Scripts folder.</span></span> <span data-ttu-id="1e716-185">次のコード行で REM を削除し、アセンブリの公開キー トークンを提供します。</span><span class="sxs-lookup"><span data-stu-id="1e716-185">In the following line of code, remove REM and provide the public key token for the assembly:</span></span>  
  
     <span data-ttu-id="1e716-186">**REM 設定 PublicKeyToken =**</span><span class="sxs-lookup"><span data-stu-id="1e716-186">**REM set PublicKeyToken=**</span></span>  
  
     <span data-ttu-id="1e716-187">例:</span><span class="sxs-lookup"><span data-stu-id="1e716-187">Example:</span></span>  
  
     <span data-ttu-id="1e716-188">**set PublicKeyToken=1234a5b6c1234567**</span><span class="sxs-lookup"><span data-stu-id="1e716-188">**set PublicKeyToken=1234a5b6c1234567**</span></span>  
  
3.  <span data-ttu-id="1e716-189">CreateFullAndPartialMSI.bat を実行します。</span><span class="sxs-lookup"><span data-stu-id="1e716-189">Run CreateFullAndPartialMSI.bat.</span></span> <span data-ttu-id="1e716-190">これにより、CreateApplicationSample.msi と CreateApplicationSamplePartial.msi 2 つのアプリケーション .msi ファイルが作成されます。</span><span class="sxs-lookup"><span data-stu-id="1e716-190">This creates two application .msi files, CreateApplicationSample.msi and CreateApplicationSamplePartial.msi.</span></span>  
  
4.  <span data-ttu-id="1e716-191">CreateNewAppFromMSI.bat を実行します。</span><span class="sxs-lookup"><span data-stu-id="1e716-191">Run CreateNewAppFromMSI.bat.</span></span> <span data-ttu-id="1e716-192">これにより、CreateApplicationSample アプリケーションを BizTalk グループにインポートし、ローカル コンピューターにインストールします。</span><span class="sxs-lookup"><span data-stu-id="1e716-192">This imports the CreateApplicationSample application into the BizTalk group and installs it on the local computer.</span></span>  
  
5.  <span data-ttu-id="1e716-193">スクリプトがインストール アクションを記録することを確認する c:\scriptlog.txt にある、スクリプト ログ ファイルを確認します。</span><span class="sxs-lookup"><span data-stu-id="1e716-193">Check the script log file, located at C:\ScriptLog.txt to verify that the script logged its installation actions.</span></span>  
  
6.  <span data-ttu-id="1e716-194">BizTalk Server 管理コンソールと追加と削除 の両方に、CreateApplicationSample アプリケーションが表示されることを確認します。</span><span class="sxs-lookup"><span data-stu-id="1e716-194">Verify that the CreateApplicationSample application appears both in the BizTalk Server Administration console and Add or Remove Programs.</span></span>  
  
7.  <span data-ttu-id="1e716-195">RemoveApp.bat を実行します。</span><span class="sxs-lookup"><span data-stu-id="1e716-195">Run RemoveApp.bat.</span></span> <span data-ttu-id="1e716-196">これは、CreateApplicationSample が BizTalk 管理データベースから削除し、ローカル コンピューターからアンインストールされます。</span><span class="sxs-lookup"><span data-stu-id="1e716-196">This deletes the CreateApplicationSample from the BizTalk Management database and uninstalls it from the local computer.</span></span>  
  
8.  <span data-ttu-id="1e716-197">スクリプトがアンインストール アクションを記録することを確認する c:\scriptlog.txt にある、スクリプト ログ ファイルを確認します。</span><span class="sxs-lookup"><span data-stu-id="1e716-197">Check the script log file, located at C:\ScriptLog.txt to verify that the script logged its uninstallation actions.</span></span> <span data-ttu-id="1e716-198">インストール時に以前では、ログに記録するインストール アクションの後に出現する必要があります。</span><span class="sxs-lookup"><span data-stu-id="1e716-198">They should appear after the installation actions logged earlier, during installation.</span></span>  
  
9. <span data-ttu-id="1e716-199">BizTalk Server 管理コンソールまたは追加と削除 で、CreateApplicationSample アプリケーションが表示されないことを確認します。</span><span class="sxs-lookup"><span data-stu-id="1e716-199">Verify that the CreateApplicationSample application no longer appears in either the BizTalk Server Administration console or Add or Remove Programs.</span></span>  
  
10. <span data-ttu-id="1e716-200">インストール中に作成されたフォルダーが削除されたことを確認します。</span><span class="sxs-lookup"><span data-stu-id="1e716-200">Verify that the folders that were created during installation have been deleted.</span></span>  
  
11. <span data-ttu-id="1e716-201">アセンブリが GAC からアンインストールされていることを確認します。</span><span class="sxs-lookup"><span data-stu-id="1e716-201">Verify that the assemblies have been uninstalled from the GAC.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="1e716-202">参照</span><span class="sxs-lookup"><span data-stu-id="1e716-202">See Also</span></span>  
 <span data-ttu-id="1e716-203">[アプリケーションの展開 (BizTalk Server Samples フォルダー)](../core/application-deployment-biztalk-server-samples-folder.md) </span><span class="sxs-lookup"><span data-stu-id="1e716-203">[Application Deployment (BizTalk Server Samples Folder)](../core/application-deployment-biztalk-server-samples-folder.md) </span></span>  
 [<span data-ttu-id="1e716-204">BizTalk アプリケーションの展開</span><span class="sxs-lookup"><span data-stu-id="1e716-204">Deploying BizTalk Applications</span></span>](../core/deploying-biztalk-applications.md)