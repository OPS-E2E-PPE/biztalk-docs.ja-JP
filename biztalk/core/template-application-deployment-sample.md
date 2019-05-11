---
title: テンプレート (アプリケーションの展開サンプル) |Microsoft Docs
ms.custom: ''
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: ''
ms.suite: ''
ms.tgt_pltfrm: ''
ms.topic: article
helpviewer_keywords:
- deploying, examples
- scripts, deploying
- deploying, scripts
- examples, deploying
ms.assetid: 7e77ff8e-b2bc-4d38-b5fd-329d6d54221f
caps.latest.revision: 20
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: 11933fe580b52ce63589c0906f0f9c17694b5c1f
ms.sourcegitcommit: 381e83d43796a345488d54b3f7413e11d56ad7be
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 05/07/2019
ms.locfileid: "65299475"
---
# <a name="template-application-deployment-sample"></a><span data-ttu-id="8835d-102">Template (アプリケーションの展開サンプル)</span><span class="sxs-lookup"><span data-stu-id="8835d-102">Template (Application Deployment Sample)</span></span>
<span data-ttu-id="8835d-103">このトピックでは、Template サンプルを使用してアプリケーションを展開する方法について説明します。</span><span class="sxs-lookup"><span data-stu-id="8835d-103">This topic describes how to use the Template sample for application deployment.</span></span>  
  
 <span data-ttu-id="8835d-104">2 種類の展開スクリプト (処理前のスクリプトと処理後のスクリプト) を作成して使用し、BizTalk アプリケーションの展開をカスタマイズできます。</span><span class="sxs-lookup"><span data-stu-id="8835d-104">You can create and use two types of deployment scripts to customize BizTalk application deployment: pre-processing scripts and post-processing scripts.</span></span> <span data-ttu-id="8835d-105">処理前のスクリプトは、アプリケーションのインストールおよびインポートの開始前およびアンインストールの完了後に呼び出されます。</span><span class="sxs-lookup"><span data-stu-id="8835d-105">Pre-processing scripts are invoked before application installation and import begins and after uninstallation completes.</span></span> <span data-ttu-id="8835d-106">処理後のスクリプトは、アプリケーションのインストールおよびインポートの完了後およびアンインストールの開始前に呼び出されます。</span><span class="sxs-lookup"><span data-stu-id="8835d-106">Post-processing scripts are invoked after application installation and import completes and before uninstallation begins.</span></span>  
  
 <span data-ttu-id="8835d-107">処理前と処理後のスクリプトは、これらの個々の操作で呼び出されるように記述できます。</span><span class="sxs-lookup"><span data-stu-id="8835d-107">You can write pre- and post- processing scripts so that they are invoked for each of these operations.</span></span> <span data-ttu-id="8835d-108">別の方法として、いずれかの操作の後にだけ実行するようスクリプトを構成することもできます。</span><span class="sxs-lookup"><span data-stu-id="8835d-108">Alternatively, you can configure scripts to execute after only one of them.</span></span> <span data-ttu-id="8835d-109">スクリプトの作成の詳細については、次を参照してください。[アプリケーション展開のカスタマイズを前処理および後処理のスクリプトを使用して](../core/using-pre-and-post-processing-scripts-to-customize-application-deployment.md)します。</span><span class="sxs-lookup"><span data-stu-id="8835d-109">For more information about writing scripts, see [Using Pre- and Post-processing Scripts to Customize Application Deployment](../core/using-pre-and-post-processing-scripts-to-customize-application-deployment.md).</span></span>  
  
 <span data-ttu-id="8835d-110">このトピックでは、1 つの操作の前または後にのみ呼び出されるようスクリプトを記述して展開する方法について説明します。</span><span class="sxs-lookup"><span data-stu-id="8835d-110">This topic demonstrates how to write and deploy a script so that it is invoked before or after only one operation.</span></span> <span data-ttu-id="8835d-111">3 つの環境変数の値をチェックして、自身が呼び出されるコンテキストの操作を判断するスクリプトを記述します。</span><span class="sxs-lookup"><span data-stu-id="8835d-111">You do this by writing a script that checks the values of three environment variables to determine the operation in the context of which it is being called.</span></span> <span data-ttu-id="8835d-112">そのコンテキストに基づいて、スクリプトは実行を継続または停止します。</span><span class="sxs-lookup"><span data-stu-id="8835d-112">Based on this context, the script either continues or discontinues execution.</span></span>  
  
 <span data-ttu-id="8835d-113">このトピックでは、以下の手順を実行する方法について説明します。</span><span class="sxs-lookup"><span data-stu-id="8835d-113">This topic describes how to take the following steps:</span></span>  
  
1.  <span data-ttu-id="8835d-114">スクリプト操作のログ ファイルを生成できるようログ ファイルの場所を設定します。</span><span class="sxs-lookup"><span data-stu-id="8835d-114">Set the log file location, so that you can generate a log file of the script operations.</span></span>  
  
    > [!NOTE]
    >  <span data-ttu-id="8835d-115">ベスト プラクティスとして、スクリプトの操作の検証および問題のトラブルシューティングを行うことができるようにログ ファイルを常に生成することをお勧めします。</span><span class="sxs-lookup"><span data-stu-id="8835d-115">As a best practice, you should always generate a log file so that you can verify script operations and troubleshoot any problems.</span></span>  
  
2.  <span data-ttu-id="8835d-116">新しい BizTalk アプリケーションを作成し、サンプル スクリプトを追加します。</span><span class="sxs-lookup"><span data-stu-id="8835d-116">Create a new BizTalk application and add the sample scripts to it.</span></span>  
  
3.  <span data-ttu-id="8835d-117">アプリケーションのアイテムを含む .msi ファイルをエクスポートします。</span><span class="sxs-lookup"><span data-stu-id="8835d-117">Export an .msi file containing the application artifacts.</span></span>  
  
4.  <span data-ttu-id="8835d-118">.msi ファイルを同じグループにインポートして .msi ファイルからアプリケーションをインストールできるように、BizTalk グループからアプリケーションを削除します。</span><span class="sxs-lookup"><span data-stu-id="8835d-118">Delete the application from the BizTalk group, so that you can import the .msi file back into the same group as well as install it from the .msi file.</span></span>  
  
5.  <span data-ttu-id="8835d-119">アプリケーションをインポートし、ログ ファイルをチェックしてインポート操作が記録されていることを確認します。</span><span class="sxs-lookup"><span data-stu-id="8835d-119">Import the application, and check the log file to see that the import operation was logged.</span></span>  
  
6.  <span data-ttu-id="8835d-120">アプリケーションをインストールし、ログ ファイルをチェックしてインストール ログがログ ファイルに追加されていることを確認します。</span><span class="sxs-lookup"><span data-stu-id="8835d-120">Install the application, and check the log file to see that the installation log was appended to the log file.</span></span>  
  
7.  <span data-ttu-id="8835d-121">ログ ファイルを表示して、スクリプトによって実行された操作および操作がいつ実行されたかを確認します。</span><span class="sxs-lookup"><span data-stu-id="8835d-121">View the log files and note what operations the scripts performed and when they were performed.</span></span>  
  
## <a name="what-this-sample-does"></a><span data-ttu-id="8835d-122">このサンプルの処理</span><span class="sxs-lookup"><span data-stu-id="8835d-122">What This Sample Does</span></span>  
 <span data-ttu-id="8835d-123">このサンプルには、インポート、インストール、およびアンインストールの環境変数の値を含む 2 つの .bat ファイルが付属しています。</span><span class="sxs-lookup"><span data-stu-id="8835d-123">Two .bat files provided for this sample contain the values of the environment variables for import, installation, and uninstallation.</span></span> <span data-ttu-id="8835d-124">SamplePreProcessing.bat には、処理前のスクリプトの変数が含まれています。</span><span class="sxs-lookup"><span data-stu-id="8835d-124">SamplePreProcessing.bat contains variables for a pre-processing script.</span></span> <span data-ttu-id="8835d-125">SamplePostProcessing.bat には、処理後のスクリプトの変数が含まれています。</span><span class="sxs-lookup"><span data-stu-id="8835d-125">SamplePostProcessing.bat contains variables for a post-processing script.</span></span> <span data-ttu-id="8835d-126">これらのファイルは、スクリプトからのメッセージをログ記録する方法も示します。</span><span class="sxs-lookup"><span data-stu-id="8835d-126">The files also demonstrate how to log messages from scripts.</span></span> <span data-ttu-id="8835d-127">これらのファイル内の関連するセクションをスクリプトにコピーできます。</span><span class="sxs-lookup"><span data-stu-id="8835d-127">You can copy the relevant sections of these files into your scripts.</span></span>  
  
> [!IMPORTANT]
>  <span data-ttu-id="8835d-128">スクリプト ファイル内のコメントには間違っているものがあります。次に例を示します。</span><span class="sxs-lookup"><span data-stu-id="8835d-128">Some of the comments within the script files are incorrect, as follows:</span></span>  
>   
>  <span data-ttu-id="8835d-129">SamplePreProcessing.bat の "既存のアプリケーションのアンインストール前に呼び出されるスクリプトの部分 (Pre uninstall part of the script called for an existing application)" というコメントは、"既存のアプリケーションのアンインストール後に呼び出されるスクリプトの部分 (Post uninstall part of the script called for an existing application)" の誤りです。</span><span class="sxs-lookup"><span data-stu-id="8835d-129">In SamplePreProcessing.bat, the script comment, “Pre uninstall part of the script called for an existing application” should read "Post uninstall part of the script called for an existing application."</span></span>  
>   
>  <span data-ttu-id="8835d-130">SamplePostProcessing.bat の "既存のアプリケーションのアンインストール後に呼び出されるスクリプトの部分 (Post uninstall part of the script called for an existing application)" というコメントは、"既存のアプリケーションのアンインストール前に呼び出されるスクリプトの部分 (Pre uninstall part of the script called for an existing application)" の誤りです。</span><span class="sxs-lookup"><span data-stu-id="8835d-130">In SamplePostProcessing.bat, the script comment, “Post uninstall part of the script called for an existing application” should read "Pre uninstall part of the script called for an existing application."</span></span>  
  
## <a name="where-to-find-this-sample"></a><span data-ttu-id="8835d-131">このサンプルの場所</span><span class="sxs-lookup"><span data-stu-id="8835d-131">Where to Find This Sample</span></span>  
 <span data-ttu-id="8835d-132">このサンプルは、[!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)] インストール フォルダーに格納されています</span><span class="sxs-lookup"><span data-stu-id="8835d-132">The sample is located in the [!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)] installation folder, as follows:</span></span>  
  
 <span data-ttu-id="8835d-133">*\<パスのサンプル\>* \Application Deployment\Template</span><span class="sxs-lookup"><span data-stu-id="8835d-133">*\<Samples Path\>* \Application Deployment\Template</span></span>  
  
 <span data-ttu-id="8835d-134">前に説明したように、サンプルには以下の 2 つのファイルが含まれています。</span><span class="sxs-lookup"><span data-stu-id="8835d-134">As previously mentioned, the sample includes the following two files:</span></span>  
  
-   <span data-ttu-id="8835d-135">SamplePreProcessing.bat</span><span class="sxs-lookup"><span data-stu-id="8835d-135">SamplePreProcessing.bat</span></span>  
  
-   <span data-ttu-id="8835d-136">SamplePostProcessing.bat</span><span class="sxs-lookup"><span data-stu-id="8835d-136">SamplePostProcessing.bat</span></span>  
  
## <a name="how-to-use-this-sample"></a><span data-ttu-id="8835d-137">このサンプルの使用方法</span><span class="sxs-lookup"><span data-stu-id="8835d-137">How to Use This Sample</span></span>  
 <span data-ttu-id="8835d-138">このサンプルを実行するには、次の手順を実行します。</span><span class="sxs-lookup"><span data-stu-id="8835d-138">To run the sample, take the following steps.</span></span>  
  
### <a name="to-set-the-logging-location"></a><span data-ttu-id="8835d-139">ログ ファイルの場所を設定するには</span><span class="sxs-lookup"><span data-stu-id="8835d-139">To set the logging location</span></span>  
  
-   <span data-ttu-id="8835d-140">両方のスクリプト サンプルを開き、LogFile 変数を変更して、ログ ファイルを書き込む場所を指定します。</span><span class="sxs-lookup"><span data-stu-id="8835d-140">Open both the script samples and change the LogFile variable to point to the location where the log files are to be written.</span></span> <span data-ttu-id="8835d-141">ファイル名を含む完全なパスを指定する必要があります。</span><span class="sxs-lookup"><span data-stu-id="8835d-141">You must provide the full path including the file name.</span></span> <span data-ttu-id="8835d-142">スペースが含まれている場合、パスを二重引用符 (") で囲む必要があります。</span><span class="sxs-lookup"><span data-stu-id="8835d-142">If it includes spaces, you must enclose the path in double quotation marks (").</span></span>  
  
     <span data-ttu-id="8835d-143">例:</span><span class="sxs-lookup"><span data-stu-id="8835d-143">Example:</span></span>  
  
     <span data-ttu-id="8835d-144">set LogFile="*\<Samples Path\>* \ApplicationDeployment\Templates\SampleLogOut.txt"</span><span class="sxs-lookup"><span data-stu-id="8835d-144">set LogFile="*\<Samples Path\>* \ApplicationDeployment\Templates\SampleLogOut.txt"</span></span>  
  
### <a name="to-create-a-new-application"></a><span data-ttu-id="8835d-145">新しいアプリケーションの作成</span><span class="sxs-lookup"><span data-stu-id="8835d-145">To create a new application</span></span>  
  
1. <span data-ttu-id="8835d-146">クリックして**開始**、 をクリックして**すべてのプログラム**、 をクリックして[!INCLUDE[btsBizTalkServerStartMenuItemui](../includes/btsbiztalkserverstartmenuitemui-md.md)]、順にクリックします**BizTalk Server 管理**します。</span><span class="sxs-lookup"><span data-stu-id="8835d-146">Click **Start**, click **All Programs**, click [!INCLUDE[btsBizTalkServerStartMenuItemui](../includes/btsbiztalkserverstartmenuitemui-md.md)], and then click **BizTalk Server Administration**.</span></span>  
  
2. <span data-ttu-id="8835d-147">コンソール ツリーで、[[!INCLUDE[btsBizTalkServerAdminConsoleui](../includes/btsbiztalkserveradminconsoleui-md.md)]]、[BizTalk グループ] の順に展開します。</span><span class="sxs-lookup"><span data-stu-id="8835d-147">In the console tree, expand [!INCLUDE[btsBizTalkServerAdminConsoleui](../includes/btsbiztalkserveradminconsoleui-md.md)] and expand the BizTalk group.</span></span>  
  
3. <span data-ttu-id="8835d-148">右クリックして**アプリケーション** をクリックし、**新規**します。</span><span class="sxs-lookup"><span data-stu-id="8835d-148">Right-click **Applications** and then click **New**.</span></span>  
  
4. <span data-ttu-id="8835d-149">**アプリケーション名**、型`SamplesTemplate`、 をクリックし、 **OK**。</span><span class="sxs-lookup"><span data-stu-id="8835d-149">In **Application name**, type `SamplesTemplate`, and then click **OK**.</span></span>  
  
### <a name="to-add-the-scripts-to-the-application"></a><span data-ttu-id="8835d-150">アプリケーションへのスクリプトの追加</span><span class="sxs-lookup"><span data-stu-id="8835d-150">To add the scripts to the application</span></span>  
  
1.  <span data-ttu-id="8835d-151">先ほど作成した SamplesTemplate アプリケーションのフォルダーを展開し、右クリックして**リソース**左側のウィンドウでします。</span><span class="sxs-lookup"><span data-stu-id="8835d-151">Expand the folder of the SamplesTemplate application that you just created and right-click **Resources** in the left pane.</span></span>  
  
2.  <span data-ttu-id="8835d-152">をポイント**追加**クリック**処理前のスクリプト**します。</span><span class="sxs-lookup"><span data-stu-id="8835d-152">Point to **Add** and click **Pre-processing Scripts**.</span></span>  
  
3.  <span data-ttu-id="8835d-153">クリックして**追加**SamplePreProcessing.bat を参照します。</span><span class="sxs-lookup"><span data-stu-id="8835d-153">Click **Add** and browse to SamplePreProcessing.bat.</span></span>  
  
4.  <span data-ttu-id="8835d-154">ファイルを選択し、をクリックして**オープン**します。</span><span class="sxs-lookup"><span data-stu-id="8835d-154">Select the file and click **Open**.</span></span>  
  
5.  <span data-ttu-id="8835d-155">**ファイルの種類**、 をクリックして**System.BizTalk:PreprocessingScript**、 をクリックし、 **OK**。</span><span class="sxs-lookup"><span data-stu-id="8835d-155">In **File type**, click **System.BizTalk:PreprocessingScript**, and then click **OK**.</span></span>  
  
     <span data-ttu-id="8835d-156">SamplePreProcessing.bat が追加されて、アプリケーションのリソース フォルダーに表示されます。</span><span class="sxs-lookup"><span data-stu-id="8835d-156">SamplePreProcessing.bat is added to the application and is displayed in the Resources folder of the application.</span></span>  
  
6.  <span data-ttu-id="8835d-157">リソースをもう一度右クリックし、[**追加**、] をクリックし、**処理後のスクリプト**します。</span><span class="sxs-lookup"><span data-stu-id="8835d-157">Right-click Resources again, point to **Add**, and then click **Post-processing Scripts**.</span></span>  
  
7.  <span data-ttu-id="8835d-158">クリックして**追加**SamplePostProcessing.bat を参照します。</span><span class="sxs-lookup"><span data-stu-id="8835d-158">Click **Add** and browse to SamplePostProcessing.bat.</span></span>  
  
8.  <span data-ttu-id="8835d-159">ファイルを選択し、をクリックして**オープン**します。</span><span class="sxs-lookup"><span data-stu-id="8835d-159">Select the file and click **Open**.</span></span>  
  
9. <span data-ttu-id="8835d-160">**ファイルの種類**、 をクリックして**System.BizTalk:PostprocessingScript**、 をクリックし、 **OK**。</span><span class="sxs-lookup"><span data-stu-id="8835d-160">In **File type**, click **System.BizTalk:PostprocessingScript**, and then click **OK**.</span></span>  
  
     <span data-ttu-id="8835d-161">SamplePostProcessing.bat が追加されて、アプリケーションのリソース フォルダーに表示されます。</span><span class="sxs-lookup"><span data-stu-id="8835d-161">SamplePostProcessing.bat is added to the application and is displayed in the Resources folder of the application.</span></span>  
  
### <a name="to-export-an-msi-file"></a><span data-ttu-id="8835d-162">.msi ファイルのエクスポート</span><span class="sxs-lookup"><span data-stu-id="8835d-162">To export an .msi file</span></span>  
  
1.  <span data-ttu-id="8835d-163">BizTalk Server 管理コンソールで、SamplesTemplate アプリケーションを右クリックして**エクスポート**、 をクリックし、 **MSI ファイル**します。</span><span class="sxs-lookup"><span data-stu-id="8835d-163">In the BizTalk Server Administration console, right-click the SamplesTemplate application, point to **Export**, and then click **MSI file**.</span></span>  
  
2.  <span data-ttu-id="8835d-164">エクスポート ウィザードのページへようこそ、をクリックして**次**します。</span><span class="sxs-lookup"><span data-stu-id="8835d-164">On the Welcome to the Export Wizard page, click **Next**.</span></span>  
  
3.  <span data-ttu-id="8835d-165">リソースの選択 ページで、次のようにクリックします。**次**します。</span><span class="sxs-lookup"><span data-stu-id="8835d-165">On the Select Resources page, click **Next**.</span></span>  
  
4.  <span data-ttu-id="8835d-166">IIS ホストの指定 ページで、次のようにクリックします。**次**します。</span><span class="sxs-lookup"><span data-stu-id="8835d-166">On the Specify IIS Hosts page, click **Next**.</span></span>  
  
5.  <span data-ttu-id="8835d-167">依存関係 ページで、次のようにクリックします。**次**します。</span><span class="sxs-lookup"><span data-stu-id="8835d-167">On the Dependencies page, click **Next**.</span></span>  
  
6.  <span data-ttu-id="8835d-168">変換先 ページで**送信先アプリケーション名**アプリケーション名を入力します。</span><span class="sxs-lookup"><span data-stu-id="8835d-168">On the Destination page, in **Destination application name**, type the application name.</span></span>  
  
7.  <span data-ttu-id="8835d-169">**を生成する MSI ファイル**、MSI ファイルの完全なパスを入力し、クリックして**エクスポート**します。</span><span class="sxs-lookup"><span data-stu-id="8835d-169">In **MSI file to generate**, type the full path for the MSI file, and then click **Export**.</span></span> <span data-ttu-id="8835d-170">例:C:\MSI\SamplesTemplate.msi</span><span class="sxs-lookup"><span data-stu-id="8835d-170">Example: C:\MSI\SamplesTemplate.msi</span></span>  
  
8.  <span data-ttu-id="8835d-171">[概要] ページで、次のようにクリックします。**完了**します。</span><span class="sxs-lookup"><span data-stu-id="8835d-171">On the Summary page, click **Finish**.</span></span>  
  
### <a name="delete-the-application"></a><span data-ttu-id="8835d-172">アプリケーションの削除</span><span class="sxs-lookup"><span data-stu-id="8835d-172">Delete the application</span></span>  
  
-   <span data-ttu-id="8835d-173">BizTalk Server 管理コンソールで、SamplesTemplate アプリケーションを右クリックし、**削除**します。</span><span class="sxs-lookup"><span data-stu-id="8835d-173">In the BizTalk Server Administration console, right-click the SamplesTemplate application, and then click **Delete**.</span></span>  
  
### <a name="to-import-the-msi-file"></a><span data-ttu-id="8835d-174">.msi ファイルのインポート</span><span class="sxs-lookup"><span data-stu-id="8835d-174">To import the .msi file</span></span>  
  
1.  <span data-ttu-id="8835d-175">右クリックし、BizTalk Server 管理コンソールで**アプリケーション**、 をポイント**インポート**、 をクリックし、 **MSI ファイル**。</span><span class="sxs-lookup"><span data-stu-id="8835d-175">In the BizTalk Server Administration console, right-click **Applications**, point to **Import**, and then click **MSI file**.</span></span>  
  
2.  <span data-ttu-id="8835d-176">インポート ウィザードのページへようこそ で**インポートする MSI ファイル**、以前エクスポートされたをクリックした .msi ファイルのパスを入力**次**します。</span><span class="sxs-lookup"><span data-stu-id="8835d-176">On the Welcome to the Import Wizard page, in **MSI file to import**, type the path of the .msi file that you previously exported, and then click **Next**.</span></span> <span data-ttu-id="8835d-177">かどうか必要に応じてを参照できます、MSI ファイルをクリックして、 **(...)** ボタンをクリックします。</span><span class="sxs-lookup"><span data-stu-id="8835d-177">If necessary, you can browse for the MSI file by clicking the **(….)** button.</span></span>  
  
3.  <span data-ttu-id="8835d-178">アプリケーションの設定 ページで、**アプリケーション名**ドロップダウン リストで、アプリケーション名を選択します。</span><span class="sxs-lookup"><span data-stu-id="8835d-178">On the Application Settings page, in the **Application name** drop-down list, select the application name.</span></span>  
  
4.  <span data-ttu-id="8835d-179">**への参照を追加できるアプリケーション**存在する場合、参照を追加するアプリケーションを選択し、クリックして**次**します。</span><span class="sxs-lookup"><span data-stu-id="8835d-179">In **Available applications to add references to**, select the applications to which to add references, if any, and then click **Next**.</span></span>  
  
5.  <span data-ttu-id="8835d-180">アプリケーションのターゲット環境の設定 ページで、次のようにクリックします。**次**します。</span><span class="sxs-lookup"><span data-stu-id="8835d-180">On the Application Target Environment Settings page, click **Next**.</span></span>  
  
    > [!NOTE]
    >  <span data-ttu-id="8835d-181">このサンプルではターゲット環境を指定する必要はありません。</span><span class="sxs-lookup"><span data-stu-id="8835d-181">You do not need to specify a target environment for the purposes of this sample.</span></span> <span data-ttu-id="8835d-182">この機能の背景については、次を参照してください。[バインド ファイルとアプリケーションの展開](../core/binding-files-and-application-deployment.md)します。</span><span class="sxs-lookup"><span data-stu-id="8835d-182">For background information on this feature, see [Binding Files and Application Deployment](../core/binding-files-and-application-deployment.md).</span></span> <span data-ttu-id="8835d-183">バインド ファイルを追加する手順については、次を参照してください。[アプリケーションにバインド ファイルを追加する方法](../core/how-to-add-a-binding-file-to-an-application2.md)します。</span><span class="sxs-lookup"><span data-stu-id="8835d-183">For instructions on adding binding files, see [How to Add a Binding File to an Application](../core/how-to-add-a-binding-file-to-an-application2.md).</span></span>  
  
6.  <span data-ttu-id="8835d-184">インポートの概要 ページで、概要情報が正しいことを確認し、**インポート**します。</span><span class="sxs-lookup"><span data-stu-id="8835d-184">On the Import Summary page, confirm that the summary information is correct, and then click **Import**.</span></span>  
  
7.  <span data-ttu-id="8835d-185">[結果] ページで、次のようにクリックします。**完了**します。</span><span class="sxs-lookup"><span data-stu-id="8835d-185">On the Results page, click **Finish**.</span></span>  
  
8.  <span data-ttu-id="8835d-186">スクリプトの実行時に作成されたログ ファイルを開き、インポート操作が記録されていることを確認します。</span><span class="sxs-lookup"><span data-stu-id="8835d-186">Open the log file that was created when the scripts executed, and verify that import operation was logged.</span></span>  
  
### <a name="to-install-the-application"></a><span data-ttu-id="8835d-187">アプリケーションをインストールするには</span><span class="sxs-lookup"><span data-stu-id="8835d-187">To install the application</span></span>  
  
1.  <span data-ttu-id="8835d-188">.msi ファイルをダブルクリックし、インストール ウィザードを実行します。</span><span class="sxs-lookup"><span data-stu-id="8835d-188">Double-click the .msi file and run the Installation Wizard.</span></span>  
  
2.  <span data-ttu-id="8835d-189">ログ ファイルを開き、ログ情報にインストール操作が追加されていることを確認します。</span><span class="sxs-lookup"><span data-stu-id="8835d-189">Open the log file and verify that installation operation was added to the logging information.</span></span>  
  
### <a name="to-verify-that-the-scripts-functioned-correctly"></a><span data-ttu-id="8835d-190">スクリプトが正常に機能したことの確認</span><span class="sxs-lookup"><span data-stu-id="8835d-190">To verify that the scripts functioned correctly</span></span>  
  
-   <span data-ttu-id="8835d-191">ログ ファイルを開き、指定した操作でスクリプトが実行されたことを確認します。</span><span class="sxs-lookup"><span data-stu-id="8835d-191">Open the log files and verify that they executed during the specified operations.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="8835d-192">参照</span><span class="sxs-lookup"><span data-stu-id="8835d-192">See Also</span></span>  
 <span data-ttu-id="8835d-193">[アプリケーションの展開 (BizTalk Server Samples フォルダー)](../core/application-deployment-biztalk-server-samples-folder.md) </span><span class="sxs-lookup"><span data-stu-id="8835d-193">[Application Deployment (BizTalk Server Samples Folder)](../core/application-deployment-biztalk-server-samples-folder.md) </span></span>  
 [<span data-ttu-id="8835d-194">BizTalk アプリケーションの展開</span><span class="sxs-lookup"><span data-stu-id="8835d-194">Deploying BizTalk Applications</span></span>](../core/deploying-biztalk-applications.md)