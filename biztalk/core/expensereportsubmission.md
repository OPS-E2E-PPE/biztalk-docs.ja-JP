---
title: "ExpenseReportSubmission |Microsoft ドキュメント"
ms.custom: 
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: 
ms.suite: 
ms.tgt_pltfrm: 
ms.topic: article
helpviewer_keywords:
- orchestrations, examples
- examples, orchestrations
ms.assetid: d0bacab3-7092-44b8-a1c6-6f574a2db8bd
caps.latest.revision: "29"
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: 993d1874a95da2501636f941f1436fec894e87f6
ms.sourcegitcommit: cb908c540d8f1a692d01dc8f313e16cb4b4e696d
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 09/20/2017
---
# <a name="expensereportsubmission"></a><span data-ttu-id="62a45-102">ExpenseReportSubmission</span><span class="sxs-lookup"><span data-stu-id="62a45-102">ExpenseReportSubmission</span></span>
<span data-ttu-id="62a45-103">ExpenseReportSubmission サンプルは、Microsoft Excel などのリッチ クライアントのドキュメントを [!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)] オーケストレーションに送信する方法を示すものです。</span><span class="sxs-lookup"><span data-stu-id="62a45-103">The ExpenseReportSubmission sample demonstrates how to submit a document to a [!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)] orchestration from a rich client such as Microsoft Excel.</span></span>  
  
 <span data-ttu-id="62a45-104">リッチ クライアントを使用すると、データ検証、準備計算など多くのアクションをクライアント上で実行できます。</span><span class="sxs-lookup"><span data-stu-id="62a45-104">Rich clients enable you to perform a number of actions, such as data validation and preliminary calculations, on the client.</span></span> <span data-ttu-id="62a45-105">これによりバックエンド サーバーとの対話処理を最小限に抑えることができるので、低帯域幅接続しか使用できない場合に便利です。</span><span class="sxs-lookup"><span data-stu-id="62a45-105">This helps to minimize interactions with the back-end server, which can be useful when only low bandwidth connections are available.</span></span>  
  
## <a name="prerequisites"></a><span data-ttu-id="62a45-106">前提条件</span><span class="sxs-lookup"><span data-stu-id="62a45-106">Prerequisites</span></span>  
 <span data-ttu-id="62a45-107">開発環境が構成済みで、[!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)] Web サービスが利用可能になっていることを確認する必要があります。</span><span class="sxs-lookup"><span data-stu-id="62a45-107">You must ensure that your development environment is configured and enabled to work with [!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)] Web services.</span></span> <span data-ttu-id="62a45-108">詳細については、次を参照してください。 [Web サービスを有効にすると](../core/enabling-web-services.md)です。</span><span class="sxs-lookup"><span data-stu-id="62a45-108">For more information, see [Enabling Web Services](../core/enabling-web-services.md).</span></span>  
  
## <a name="what-this-sample-does"></a><span data-ttu-id="62a45-109">このサンプルの処理</span><span class="sxs-lookup"><span data-stu-id="62a45-109">What This Sample Does</span></span>  
 <span data-ttu-id="62a45-110">このサンプルでは、次の一連の手順で、経費報告書を Excel から [!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)] に直接送信します。</span><span class="sxs-lookup"><span data-stu-id="62a45-110">This sample shows how you can submit an expense report to [!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)] directly from Excel, using the following sequence of steps:</span></span>  
  
1.  <span data-ttu-id="62a45-111">ユーザーが、Excel ワークシートで指定のサンプル手順を手動で実行します。</span><span class="sxs-lookup"><span data-stu-id="62a45-111">The user performs the manual sample steps provided in the Excel spreadsheet.</span></span>  
  
2.  <span data-ttu-id="62a45-112">ワークシートのマクロ コードにより、ワークシートのデータが XML (Extensible Markup Language) 形式に変換され、XML メッセージが HTTP 接続経由で [!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)] に送信されます。</span><span class="sxs-lookup"><span data-stu-id="62a45-112">Macro code in the spreadsheet converts the spreadsheet data to Extensible Markup Language (XML) format, and submits the XML message to [!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)] using an HTTP connection.</span></span>  
  
3.  <span data-ttu-id="62a45-113">[!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)] を実行しているコンピューターが、XML 形式の経費報告書のメッセージを取得し、指定のスキーマを使用してメッセージの形式を検証した後、メッセージを別のフォルダーに格納します。</span><span class="sxs-lookup"><span data-stu-id="62a45-113">The computer running [!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)] retrieves the XML expense report message, validates its format using the provided schema, and then drops it into a different folder.</span></span>  
  
4.  <span data-ttu-id="62a45-114">このサンプルでは示していませんが、実際はエンタープライズ リソース プランニング (ERP) システムなどの他のアプリケーションがこのワークシート ファイルを取得し、さらに処理を行います。</span><span class="sxs-lookup"><span data-stu-id="62a45-114">In practice, beyond the scope of this sample, another application such as an Enterprise Resource Planning (ERP) system would then retrieve the spreadsheet file for further processing.</span></span>  
  
## <a name="where-to-find-this-sample"></a><span data-ttu-id="62a45-115">このサンプルの場所</span><span class="sxs-lookup"><span data-stu-id="62a45-115">Where to Find This Sample</span></span>  
 <span data-ttu-id="62a45-116">\<*パスのサンプル*> \AdaptersUsage\ExpenseReportSubmission\\</span><span class="sxs-lookup"><span data-stu-id="62a45-116">\<*Samples Path*>\AdaptersUsage\ExpenseReportSubmission\\</span></span>  
  
 <span data-ttu-id="62a45-117">次の表は、このサンプルのファイルとその目的を示しています。</span><span class="sxs-lookup"><span data-stu-id="62a45-117">The following table shows the files in this sample and describes their purpose.</span></span>  
  
|<span data-ttu-id="62a45-118">ファイル</span><span class="sxs-lookup"><span data-stu-id="62a45-118">File(s)</span></span>|<span data-ttu-id="62a45-119">Description</span><span class="sxs-lookup"><span data-stu-id="62a45-119">Description</span></span>|  
|---------------|-----------------|  
|<span data-ttu-id="62a45-120">Cleanup.bat</span><span class="sxs-lookup"><span data-stu-id="62a45-120">Cleanup.bat</span></span>|<span data-ttu-id="62a45-121">必要に応じて、アセンブリの展開の解除とグローバル アセンブリ キャッシュ (GAC) からのアセンブリの削除、送信および受信ポートの削除、Microsoft インターネット インフォメーション サービス (IIS) の仮想ディレクトリの削除などを行います。</span><span class="sxs-lookup"><span data-stu-id="62a45-121">Undeploys assemblies and removes them from the global assembly cache (GAC); removes send and receive ports; removes Microsoft Internet Information Services (IIS) virtual directories as needed.</span></span>|  
|<span data-ttu-id="62a45-122">ExpenseReport.15.3.xls</span><span class="sxs-lookup"><span data-stu-id="62a45-122">ExpenseReport.15.3.xls</span></span>|<span data-ttu-id="62a45-123">経費報告書のレイアウトの Excel ワークシートです。マクロとその呼び出し用ボタンが用意されています。</span><span class="sxs-lookup"><span data-stu-id="62a45-123">Excel spreadsheet with the expense report layout, associated macros, and buttons to invoke the macros.</span></span>|  
|<span data-ttu-id="62a45-124">MessageExample.xml</span><span class="sxs-lookup"><span data-stu-id="62a45-124">MessageExample.xml</span></span>|<span data-ttu-id="62a45-125">XML 形式の経費報告書のサンプルです。</span><span class="sxs-lookup"><span data-stu-id="62a45-125">Example of the XML expense report format.</span></span>|  
|<span data-ttu-id="62a45-126">Setup.bat</span><span class="sxs-lookup"><span data-stu-id="62a45-126">Setup.bat</span></span>|<span data-ttu-id="62a45-127">このサンプルを作成および初期化します。</span><span class="sxs-lookup"><span data-stu-id="62a45-127">Builds and initializes this sample.</span></span>|  
|<span data-ttu-id="62a45-128">\BTSExpenseDemo フォルダーには、次のファイルが含まれています。</span><span class="sxs-lookup"><span data-stu-id="62a45-128">In the \BTSExpenseDemo folder:</span></span><br /><br /> <span data-ttu-id="62a45-129">AssemblyInfo.cs、</span><span class="sxs-lookup"><span data-stu-id="62a45-129">AssemblyInfo.cs,</span></span><br /><br /> <span data-ttu-id="62a45-130">BTSExpenseDemo.btproj、</span><span class="sxs-lookup"><span data-stu-id="62a45-130">BTSExpenseDemo.btproj,</span></span><br /><br /> <span data-ttu-id="62a45-131">BTSExpenseDemo.sln</span><span class="sxs-lookup"><span data-stu-id="62a45-131">BTSExpenseDemo.sln</span></span>|<span data-ttu-id="62a45-132">このサンプルのプロジェクト ファイル、ソリューション ファイル、その他の関連ファイルを提供します。</span><span class="sxs-lookup"><span data-stu-id="62a45-132">Provides project, solution, and related files for this sample.</span></span>|  
|<span data-ttu-id="62a45-133">\BTSExpenseDemo フォルダーには、次のファイルが含まれています。</span><span class="sxs-lookup"><span data-stu-id="62a45-133">In the \BTSExpenseDemo folder:</span></span><br /><br /> <span data-ttu-id="62a45-134">BTSExpenseDemoBinding.xml</span><span class="sxs-lookup"><span data-stu-id="62a45-134">BTSExpenseDemoBinding.xml</span></span>|<span data-ttu-id="62a45-135">ポートのバインドなどの自動化されたセットアップに使用されます。</span><span class="sxs-lookup"><span data-stu-id="62a45-135">Used for automated setup, such as port binding.</span></span>|  
|<span data-ttu-id="62a45-136">\BTSExpenseDemo フォルダーには、次のファイルが含まれています。</span><span class="sxs-lookup"><span data-stu-id="62a45-136">In the \BTSExpenseDemo folder:</span></span><br /><br /> <span data-ttu-id="62a45-137">BTSExpenseOrchestration.odx</span><span class="sxs-lookup"><span data-stu-id="62a45-137">BTSExpenseOrchestration.odx</span></span>|<span data-ttu-id="62a45-138">このサンプルの [!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)] オーケストレーションを提供します。</span><span class="sxs-lookup"><span data-stu-id="62a45-138">Provides a [!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)] orchestration for this sample.</span></span>|  
|<span data-ttu-id="62a45-139">\BTSExpenseDemo フォルダーには、次のファイルが含まれています。</span><span class="sxs-lookup"><span data-stu-id="62a45-139">In the \BTSExpenseDemo folder:</span></span><br /><br /> <span data-ttu-id="62a45-140">SchemaExpenseReport.xsd</span><span class="sxs-lookup"><span data-stu-id="62a45-140">SchemaExpenseReport.xsd</span></span>|<span data-ttu-id="62a45-141">XML 形式の経費報告書のスキーマを提供します。</span><span class="sxs-lookup"><span data-stu-id="62a45-141">Provides a schema for the XML expense report format.</span></span>|  
  
### <a name="to-build-and-initialize-this-sample"></a><span data-ttu-id="62a45-142">このサンプルを作成および初期化するには</span><span class="sxs-lookup"><span data-stu-id="62a45-142">To build and initialize this sample</span></span>  
  
1.  <span data-ttu-id="62a45-143">コマンド ウィンドウで、次のフォルダーに移動します。</span><span class="sxs-lookup"><span data-stu-id="62a45-143">In a command window, navigate to the following folder:</span></span>  
  
     <span data-ttu-id="62a45-144">\<*パスのサンプル*> \AdaptersUsage\ExpenseReportSubmission</span><span class="sxs-lookup"><span data-stu-id="62a45-144">\<*Samples Path*>\AdaptersUsage\ExpenseReportSubmission</span></span>  
  
2.  <span data-ttu-id="62a45-145">次の操作を実行する Setup.bat ファイルを実行します。</span><span class="sxs-lookup"><span data-stu-id="62a45-145">Run the file Setup.bat, which performs the following actions:</span></span>  
  
    -   <span data-ttu-id="62a45-146">このサンプル用に Microsoft [!INCLUDE[btsVStudioNoVersion](../includes/btsvstudionoversion-md.md)] プロジェクトをコンパイルし、生成されたアセンブリを展開します。</span><span class="sxs-lookup"><span data-stu-id="62a45-146">Compiles the Microsoft [!INCLUDE[btsVStudioNoVersion](../includes/btsvstudionoversion-md.md)] project for this sample, and deploys the resulting assembly.</span></span>  
  
    -   <span data-ttu-id="62a45-147">[!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)] の送信ポートおよび受信ポートを作成し、バインドします。</span><span class="sxs-lookup"><span data-stu-id="62a45-147">Creates and binds the [!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)] send and receive ports.</span></span>  
  
        > [!NOTE]
        >  <span data-ttu-id="62a45-148">このサンプルは、ポートを作成してバインドする際に、以下の警告を表示します。</span><span class="sxs-lookup"><span data-stu-id="62a45-148">This sample displays the following warnings when creating and binding the ports:</span></span>  
        >   
        >  `Warning: Receive handler not specified for receive location "BTSExpenseReceiveLocation"; updating with first receive handler with matching transport type.`  
        >   
        >  <span data-ttu-id="62a45-149">`Warning: Host not specified for orchestration "Microsoft.Samples.BizTalk.BTSExpenseDemo.BTSOrchestration"; updating with first available host`」をご覧ください。</span><span class="sxs-lookup"><span data-stu-id="62a45-149">`Warning: Host not specified for orchestration "Microsoft.Samples.BizTalk.BTSExpenseDemo.BTSOrchestration"; updating with first available host`.</span></span>  
        >   
        >  <span data-ttu-id="62a45-150">これらの警告は、無視してもかまいません </span><span class="sxs-lookup"><span data-stu-id="62a45-150">You can safely ignore these warnings.</span></span> <span data-ttu-id="62a45-151">(インストールでの名前付け方法はユーザーによって異なる可能性があるため、ホスト名と受信ハンドラーはバインド ファイルから除外されています。)</span><span class="sxs-lookup"><span data-stu-id="62a45-151">(To accommodate for possible naming differences in user installations, the host name and receive handler have been omitted from the binding file.)</span></span>  
  
    -   <span data-ttu-id="62a45-152">受信場所を有効にし、送信ポートを開始します。</span><span class="sxs-lookup"><span data-stu-id="62a45-152">Enables the receive location, and starts the send port.</span></span>  
  
    -   <span data-ttu-id="62a45-153">IIS を構成します。</span><span class="sxs-lookup"><span data-stu-id="62a45-153">Configures IIS.</span></span>  
  
    -   <span data-ttu-id="62a45-154">[!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)] オーケストレーションをバインドして、開始します。</span><span class="sxs-lookup"><span data-stu-id="62a45-154">Binds and starts the [!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)] orchestration.</span></span>  
  
    -   <span data-ttu-id="62a45-155">HTTP アドレスを、Excel ワークシートで想定されている場所に設定します。</span><span class="sxs-lookup"><span data-stu-id="62a45-155">Sets the HTTP address to the location expected by the Excel spreadsheet.</span></span>  
  
    > [!NOTE]
    >  <span data-ttu-id="62a45-156">BizTalk ISAPI フィルターの詳細については、次を参照してください。 [HTTP の受信場所の IIS を構成する方法](../core/how-to-configure-iis-for-an-http-receive-location.md)です。</span><span class="sxs-lookup"><span data-stu-id="62a45-156">For more information about the BizTalk ISAPI filter, see [How to Configure IIS for an HTTP Receive Location](../core/how-to-configure-iis-for-an-http-receive-location.md).</span></span>  
  
    > [!NOTE]
    >  <span data-ttu-id="62a45-157">このサンプルを実行する前に、ビルドと初期化のプロセス中に [!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)] でエラーが報告されていないことを確認する必要があります。</span><span class="sxs-lookup"><span data-stu-id="62a45-157">You should confirm that [!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)] did not report any errors during the build and initialization process before attempting to run this sample.</span></span>  
  
    > [!NOTE]
    >  <span data-ttu-id="62a45-158">Setup.bat ファイルを実行せずに、このサンプルのプロジェクトを開いてビルドする場合は、最初に .NET Framework の厳密名ユーティリティ (sn.exe) を使用して、厳密な名前のキー ペアを作成する必要があります。</span><span class="sxs-lookup"><span data-stu-id="62a45-158">If you choose to open and build the project in this sample without running the file Setup.bat, you must first create a strong name key pair using the .NET Framework Strong Name Utility (sn.exe).</span></span> <span data-ttu-id="62a45-159">結果として得られるアセンブリに署名するのにには、このキー ペアを使用します。</span><span class="sxs-lookup"><span data-stu-id="62a45-159">Use this key pair to sign the resulting assembly.</span></span>  
  
    > [!NOTE]
    >  <span data-ttu-id="62a45-160">Setup.bat によって行われた変更を元に戻すには、Cleanup.bat を実行します。</span><span class="sxs-lookup"><span data-stu-id="62a45-160">To undo changes made by Setup.bat, run Cleanup.bat.</span></span> <span data-ttu-id="62a45-161">Setup.bat を 2 回目に実行する場合は、その前に Cleanup.bat を実行してください。</span><span class="sxs-lookup"><span data-stu-id="62a45-161">You must run Cleanup.bat before running Setup.bat a second time.</span></span>  
  
3.  <span data-ttu-id="62a45-162">Setup.bat ファイルを実行すると、このサンプルの仮想ディレクトリが構成され、既定の Web サイトに関連付けられた IIS アプリケーション プールで実行されるよう設定されます。</span><span class="sxs-lookup"><span data-stu-id="62a45-162">The setup.bat file configures the virtual directory for this sample to run in the IIS application pool associated with the default web site.</span></span>  <span data-ttu-id="62a45-163">このサンプルでのユーザーのコンテキストで実行する仮想ディレクトリを構成する、 **BizTalk Isolated Host Users**と**IIS_WPG**ユーザー グループを新しいを実行する仮想ディレクトリを構成する必要がありますIIS アプリケーション プール。</span><span class="sxs-lookup"><span data-stu-id="62a45-163">To configure the virtual directory for this sample to run under the context of a user in the **BizTalk Isolated Host Users** and **IIS_WPG** user groups, you should configure the virtual directory to run in a new IIS application pool.</span></span>  <span data-ttu-id="62a45-164">仮想ディレクトリを新しい IIS アプリケーション プールで実行するよう構成するには、次の手順を実行します。</span><span class="sxs-lookup"><span data-stu-id="62a45-164">Configure the virtual directory to run in a new IIS application pool by completing the following steps:</span></span>  
  
    > [!NOTE]
    >  <span data-ttu-id="62a45-165">別の SDK サンプル用に新しいアプリケーション プールを作成済みの場合は、次の箇条書きの最後の項目に進むことができます。</span><span class="sxs-lookup"><span data-stu-id="62a45-165">If you have already created a new application pool for another SDK sample then you can proceed to the last bullet item below.</span></span>  
  
    1.  <span data-ttu-id="62a45-166">をクリックして**開始**、 をポイント**プログラム**、 をポイント**管理ツール**、クリックして**インターネット インフォメーション サービス (IIS) マネージャー**.</span><span class="sxs-lookup"><span data-stu-id="62a45-166">Click **Start**, point to **Programs**, point to **Administrative Tools**, and then click **Internet Information Services (IIS) Manager**.</span></span>  
  
    2.  <span data-ttu-id="62a45-167">**インターネット インフォメーション サービス (IIS) マネージャー**に移動し、**アプリケーション プール**フォルダーです。</span><span class="sxs-lookup"><span data-stu-id="62a45-167">In the **Internet Information Services (IIS) Manager**, navigate to the **Application Pools** folder.</span></span>  
  
    3.  <span data-ttu-id="62a45-168">右クリックし、**アプリケーション プール**フォルダーとクリック**新規**、**アプリケーション プールしています.**</span><span class="sxs-lookup"><span data-stu-id="62a45-168">Right-click the **Application Pools** folder and click **New**, **Application Pool...**</span></span>  
  
    4.  <span data-ttu-id="62a45-169">名前を入力、**アプリケーション プール ID:** BizTalkSDKSamples などのことを確認、**新しいアプリケーション プールに既定の設定を使用して**オプションが選択されているし、をクリックして**OK**に新しいアプリケーション プールを作成します。</span><span class="sxs-lookup"><span data-stu-id="62a45-169">Enter a name for the **Application Pool ID:** such as BizTalkSDKSamples, verify that the **Use default settings for new application pool** option is selected and click **OK** to create the new application pool.</span></span>  
  
    5.  <span data-ttu-id="62a45-170">新しいアプリケーション プールを右クリックし、をクリックして**プロパティ**です。</span><span class="sxs-lookup"><span data-stu-id="62a45-170">Right-click the new application pool and then click **Properties**.</span></span>  
  
    6.  <span data-ttu-id="62a45-171">をクリックして、 **Identity**プロパティ ダイアログ ボックスのタブ ボックスし、このアプリケーション プールのメンバーであるユーザーを実行する id を変更する、 **BizTalk Isolated Host Users**ユーザー グループ。</span><span class="sxs-lookup"><span data-stu-id="62a45-171">Click the **Identity** tab of the properties dialog box and change the identity under which this application pool runs to a user that is a member of the **BizTalk Isolated Host Users** user group.</span></span>  <span data-ttu-id="62a45-172">このユーザーは、ローカルのメンバーでもある必要があります**IIS_WPG**ユーザー グループ。</span><span class="sxs-lookup"><span data-stu-id="62a45-172">This user should also be a member of the local **IIS_WPG** user group.</span></span>  
  
    7.  <span data-ttu-id="62a45-173">この SDK サンプルの仮想ディレクトリを、新しいアプリケーション プールで実行するよう構成します。</span><span class="sxs-lookup"><span data-stu-id="62a45-173">Configure the virtual directory for this SDK sample to run under the new application pool.</span></span> <span data-ttu-id="62a45-174">**アプリケーション プール:**設定は、**仮想ディレクトリ**仮想ディレクトリのプロパティ ダイアログ ボックスのタブです。</span><span class="sxs-lookup"><span data-stu-id="62a45-174">The **Application pool:** setting is available on the **Virtual Directory** tab of the Virtual Directory properties dialog box.</span></span> <span data-ttu-id="62a45-175">このサンプルは、用に作成された仮想ディレクトリ**ExpenseReportSubmission**です。</span><span class="sxs-lookup"><span data-stu-id="62a45-175">The virtual directory created for this sample is **ExpenseReportSubmission**.</span></span>  
  
4.  <span data-ttu-id="62a45-176">IIS の Web サービス拡張を HTTPReceive.dll 用に追加します。</span><span class="sxs-lookup"><span data-stu-id="62a45-176">Add a web service extension to IIS for HTTPReceive.dll</span></span>  
  
    1.  <span data-ttu-id="62a45-177">**インターネット インフォメーション サービス (IIS) マネージャー**に移動し、 **Web サービス拡張**フォルダーです。</span><span class="sxs-lookup"><span data-stu-id="62a45-177">In the **Internet Information Services (IIS) Manager**, navigate to the **Web Service Extensions** folder.</span></span>  
  
    2.  <span data-ttu-id="62a45-178">右クリックし、 **Web サービス拡張**フォルダーと選択**新しい Web サービス拡張を追加**を表示する、**新しい Web サービス拡張** ダイアログ ボックス。</span><span class="sxs-lookup"><span data-stu-id="62a45-178">Right-click the **Web Service Extensions** folder and select **Add a new Web service extension** to display the **New Web Service Extension** dialog box.</span></span>  
  
    3.  <span data-ttu-id="62a45-179">入力**ExpenseReportSubmission**の**拡張機能の名前。**</span><span class="sxs-lookup"><span data-stu-id="62a45-179">Enter **ExpenseReportSubmission** for **Extension name:**</span></span>  
  
    4.  <span data-ttu-id="62a45-180">をクリックして**追加**を表示する、 **Add file**  ダイアログ ボックス。</span><span class="sxs-lookup"><span data-stu-id="62a45-180">Click **Add** to display the **Add file** dialog box.</span></span>  
  
    5.  <span data-ttu-id="62a45-181">をクリックして**参照**を表示する、**開く** ダイアログ ボックスに移動して *\<BizTalk Server のインストール フォルダー >*\HttpReceive\BTSHTTPReceive.dll とをクリックして**開く**をクリックし、 **ok**です。</span><span class="sxs-lookup"><span data-stu-id="62a45-181">Click **Browse** to display the **Open** dialog box and navigate to *\<BizTalk Server Installation folder>*\HttpReceive\BTSHTTPReceive.dll and click **Open**, then click **OK**.</span></span>  
  
    6.  <span data-ttu-id="62a45-182">ためのオプションを有効にする**拡張機能の状態を許可 に設定** をクリック**OK**です。</span><span class="sxs-lookup"><span data-stu-id="62a45-182">Enable the option to **Set extension status to Allowed** and click **OK**.</span></span>  
  
## <a name="running-this-sample"></a><span data-ttu-id="62a45-183">このサンプルの実行</span><span class="sxs-lookup"><span data-stu-id="62a45-183">Running This Sample</span></span>  
 <span data-ttu-id="62a45-184">次の手順を使用して、ExpenseReportSubmission サンプルを実行します。</span><span class="sxs-lookup"><span data-stu-id="62a45-184">Use the following procedure to run the ExpenseReportSubmission sample.</span></span>  
  
> [!NOTE]
>  <span data-ttu-id="62a45-185">Microsoft Excel の強化されたセキュリティ機能を使用している場合、ワークシート内のマクロが無効になることがあります。</span><span class="sxs-lookup"><span data-stu-id="62a45-185">If you are using the enhanced security features of Microsoft Excel, the macros in the spreadsheet may be disabled.</span></span> <span data-ttu-id="62a45-186">信頼できるソースからの未署名のマクロを実行する方法については、Excel で提供されている指示に従ってください。</span><span class="sxs-lookup"><span data-stu-id="62a45-186">Follow the instructions provided by Excel about how to run unsigned macros from a trusted source.</span></span>  
  
#### <a name="to-run-this-sample"></a><span data-ttu-id="62a45-187">このサンプルを実行するには</span><span class="sxs-lookup"><span data-stu-id="62a45-187">To run this sample</span></span>  
  
1.  <span data-ttu-id="62a45-188">このサンプルに含まれている Excel ファイルの ExpenseReport.15.3.xls を開きます。</span><span class="sxs-lookup"><span data-stu-id="62a45-188">Open the Excel file ExpenseReport.15.3.xls included with this sample.</span></span>  
  
2.  <span data-ttu-id="62a45-189">必要に応じて、ワークシート内のサンプル データを変更します。ただし、書式は変更しないでください。</span><span class="sxs-lookup"><span data-stu-id="62a45-189">Optionally, change the sample data in the spreadsheet without changing its format.</span></span>  
  
3.  <span data-ttu-id="62a45-190">クリックして、スプレッドシートで**開始**ローカル計算を実行します。</span><span class="sxs-lookup"><span data-stu-id="62a45-190">In the spreadsheet, click **Start** to perform local calculations.</span></span>  
  
     <span data-ttu-id="62a45-191">ボタンのテキストがから変更**開始**に**送信**です。</span><span class="sxs-lookup"><span data-stu-id="62a45-191">The text of the button changes from **Start** to **Submit**.</span></span>  
  
4.  <span data-ttu-id="62a45-192">クリックして、スプレッドシートで**送信**です。</span><span class="sxs-lookup"><span data-stu-id="62a45-192">In the spreadsheet, click **Submit**.</span></span>  
  
5.  <span data-ttu-id="62a45-193">送信されたメッセージのテキストと、表の上部に黄色の背景で表示される結果 (セル C7)、および表の下方右側に表示される実際のリターン コードと説明テキスト (セル G23) を確認します。</span><span class="sxs-lookup"><span data-stu-id="62a45-193">Observe the text of the submitted message, the result above the table with yellow background (cell C7), and the actual return code and text description below and to the right (cell G23).</span></span>  
  
     <span data-ttu-id="62a45-194">送信に失敗した場合は、もう 1 度実行してください。</span><span class="sxs-lookup"><span data-stu-id="62a45-194">If submission fails, try again.</span></span> <span data-ttu-id="62a45-195">「コメント」セクションのトラブルシューティングの表も参照してください。</span><span class="sxs-lookup"><span data-stu-id="62a45-195">Also, refer to the troubleshooting table in the Comments section.</span></span>  
  
## <a name="comments"></a><span data-ttu-id="62a45-196">コメント</span><span class="sxs-lookup"><span data-stu-id="62a45-196">Comments</span></span>  
 <span data-ttu-id="62a45-197">このサンプルのシナリオが発生するのは、たとえば、フィールド営業員が使用するコンピューターに古いバージョンの Microsoft Windows が搭載されており、そのバージョンでは .NET Framework がサポートされておらず、より新しいバージョンの Windows にアップグレードすることも考えられていないといったケースです。</span><span class="sxs-lookup"><span data-stu-id="62a45-197">Scenarios such as this can occur when, for example, a field sales force is equipped with older versions of Microsoft Windows that do not support the .NET Framework, and for which the requirement to upgrade to a more current version of Windows is not a viable option.</span></span>  
  
 <span data-ttu-id="62a45-198">このサンプルでは、次のような基本機能を実行します。</span><span class="sxs-lookup"><span data-stu-id="62a45-198">Essential features demonstrated in this sample are:</span></span>  
  
-   <span data-ttu-id="62a45-199">リッチ クライアント (.NET ベース以外) からの送信</span><span class="sxs-lookup"><span data-stu-id="62a45-199">Submission from a rich client (not .NET-based)</span></span>  
  
-   <span data-ttu-id="62a45-200">Microsoft Office 統合</span><span class="sxs-lookup"><span data-stu-id="62a45-200">Microsoft Office integration</span></span>  
  
-   <span data-ttu-id="62a45-201">HTTP 受信接続</span><span class="sxs-lookup"><span data-stu-id="62a45-201">HTTP receive connections</span></span>  
  
-   <span data-ttu-id="62a45-202">簡単なオーケストレーション</span><span class="sxs-lookup"><span data-stu-id="62a45-202">Simple orchestration</span></span>  
  
-   <span data-ttu-id="62a45-203">ファイル アダプター</span><span class="sxs-lookup"><span data-stu-id="62a45-203">File adapter</span></span>  
  
 <span data-ttu-id="62a45-204">考えられる送信エラーとその解決方法を次の表に示します。</span><span class="sxs-lookup"><span data-stu-id="62a45-204">The following table shows some possible submission errors and their solutions.</span></span>  
  
|<span data-ttu-id="62a45-205">HTTP エラー コード</span><span class="sxs-lookup"><span data-stu-id="62a45-205">HTTP error code</span></span>|<span data-ttu-id="62a45-206">対処方法</span><span class="sxs-lookup"><span data-stu-id="62a45-206">Possible action</span></span>|  
|---------------------|---------------------|  
|<span data-ttu-id="62a45-207">401 権限がありません</span><span class="sxs-lookup"><span data-stu-id="62a45-207">401 Unauthorized</span></span>|<span data-ttu-id="62a45-208">仮想ディレクトリでの匿名アクセスを有効にします。</span><span class="sxs-lookup"><span data-stu-id="62a45-208">Enable anonymous access on the virtual directory.</span></span>|  
|<span data-ttu-id="62a45-209">503 サービス利用不可、その他 400 ～ 500 番台の大半の HTTP コード</span><span class="sxs-lookup"><span data-stu-id="62a45-209">503 Service Unavailable, and most other HTTP codes in the 400 and 500 ranges</span></span>|<span data-ttu-id="62a45-210">ホストが実行されていることと、サービスが展開され、正しいポートにバインドされて開始されていることを確認します。</span><span class="sxs-lookup"><span data-stu-id="62a45-210">Ensure that the host runs and that the service is deployed, bound to the correct port, and started.</span></span>|  
  
## <a name="see-also"></a><span data-ttu-id="62a45-211">参照</span><span class="sxs-lookup"><span data-stu-id="62a45-211">See Also</span></span>  
 [<span data-ttu-id="62a45-212">アダプタ サンプル – 使用状況</span><span class="sxs-lookup"><span data-stu-id="62a45-212">Adapter Samples - Usage</span></span>](../core/adapter-samples-usage.md)