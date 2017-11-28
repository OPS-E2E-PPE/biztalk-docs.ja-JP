---
title: "展開して、アプリケーションのエクスポート |Microsoft ドキュメント"
ms.custom: 
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: 
ms.suite: 
ms.tgt_pltfrm: 
ms.topic: article
ms.assetid: 4106a0a7-878d-4052-8eca-02d546233048
caps.latest.revision: "2"
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: b33762f50f32dda58f1453fde7be37bc959af6aa
ms.sourcegitcommit: cb908c540d8f1a692d01dc8f313e16cb4b4e696d
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 09/20/2017
---
# <a name="deploying-and-exporting-an-application"></a><span data-ttu-id="7215a-102">展開して、アプリケーションをエクスポートします。</span><span class="sxs-lookup"><span data-stu-id="7215a-102">Deploying and Exporting an Application</span></span>
<span data-ttu-id="7215a-103">このセクションには、BizTalk アプリケーションの展開に必要な手順を実行する方法に関する詳細情報が含まれています。</span><span class="sxs-lookup"><span data-stu-id="7215a-103">This section contains detailed information about how to perform the steps involved in deploying a BizTalk application.</span></span> <span data-ttu-id="7215a-104">このセクションのトピックでは、次のチェックリストをサポートします。</span><span class="sxs-lookup"><span data-stu-id="7215a-104">The topics in this section support the following checklists:</span></span>  
  
-   <span data-ttu-id="7215a-105">[チェックリスト: アプリケーションを展開する](../technical-guides/checklist-deploying-an-application.md)、開発環境でアプリケーションを展開、.msi ファイルにエクスポートし、.msi ファイルから実稼働環境にインポートする方法が示されます。</span><span class="sxs-lookup"><span data-stu-id="7215a-105">[Checklist: Deploying an Application](../technical-guides/checklist-deploying-an-application.md), which shows how to deploy an application in a development environment, export it into an .msi file, and then import it into a production environment from the .msi file.</span></span>  
  
-   <span data-ttu-id="7215a-106">[チェックリスト: から別のアプリケーションへのバインドのエクスポート](../technical-guides/checklist-exporting-bindings-from-one-application-to-another.md)、いずれかで他のアプリケーションにアプリケーションからバインドをエクスポートする方法、開発環境または運用環境が示されます。</span><span class="sxs-lookup"><span data-stu-id="7215a-106">[Checklist: Exporting Bindings from One Application to Another](../technical-guides/checklist-exporting-bindings-from-one-application-to-another.md), which shows how to export bindings from an application into another application in either a development or production environment.</span></span>  
  
 <span data-ttu-id="7215a-107">次のツールを使用して、展開および BizTalk アプリケーションを管理することができます。</span><span class="sxs-lookup"><span data-stu-id="7215a-107">You can use the following tools to deploy and manage a BizTalk application:</span></span>  
  
|<span data-ttu-id="7215a-108">ツール</span><span class="sxs-lookup"><span data-stu-id="7215a-108">Tool</span></span>|<span data-ttu-id="7215a-109">新しく使用する機能</span><span class="sxs-lookup"><span data-stu-id="7215a-109">Use</span></span>|  
|----------|---------|  
|<span data-ttu-id="7215a-110">BizTalk Server 管理コンソール</span><span class="sxs-lookup"><span data-stu-id="7215a-110">BizTalk Server Administration console</span></span>|<span data-ttu-id="7215a-111">このグラフィカル ユーザー インターフェイスからすべての BizTalk アプリケーションの場合、次の展開と管理の操作を行うことができます。</span><span class="sxs-lookup"><span data-stu-id="7215a-111">From this graphical user interface, you can perform all of the deployment and management operations for a BizTalk application, including the following:</span></span><br /><br /> <span data-ttu-id="7215a-112">-インポート、インストール、およびエクスポート ウィザードを開始します。</span><span class="sxs-lookup"><span data-stu-id="7215a-112">-   Starting the Import, Installation, and Export Wizards</span></span><br /><span data-ttu-id="7215a-113">-追加、アプリケーションのアイテムを削除して、アプリケーションにその他の変更を加える</span><span class="sxs-lookup"><span data-stu-id="7215a-113">-   Adding and removing an application's artifacts, and making other modifications to the application</span></span><br /><span data-ttu-id="7215a-114">生成する BizTalk アプリケーションの .msi ファイルを BizTalk Server</span><span class="sxs-lookup"><span data-stu-id="7215a-114">-   Generating BizTalk Server .msi files for a BizTalk application</span></span><br /><span data-ttu-id="7215a-115">.Msi ファイルからコンピューターにアプリケーションのインストールや、アプリケーションを .msi ファイルから別の BizTalk グループにインポートします。</span><span class="sxs-lookup"><span data-stu-id="7215a-115">-   Installing the application onto a computer from the .msi file or importing the application from the .msi file into another BizTalk group</span></span><br /><span data-ttu-id="7215a-116">-バインド ファイルからアプリケーションのバインドをインポートします。</span><span class="sxs-lookup"><span data-stu-id="7215a-116">-   Importing the bindings for an application from a binding file</span></span><br /><br /> <span data-ttu-id="7215a-117">管理コンソールの詳細については、次を参照してください。 [、BizTalk Server 管理コンソールを使用して](http://go.microsoft.com/fwlink/?LinkID=154689)(http://go.microsoft.com/fwlink/?LinkID=154689)。</span><span class="sxs-lookup"><span data-stu-id="7215a-117">For more information about the administration console, see [Using the BizTalk Server Administration Console](http://go.microsoft.com/fwlink/?LinkID=154689) (http://go.microsoft.com/fwlink/?LinkID=154689).</span></span>|  
|<span data-ttu-id="7215a-118">BTSTask コマンド ライン ツール</span><span class="sxs-lookup"><span data-stu-id="7215a-118">BTSTask command-line tool</span></span>|<span data-ttu-id="7215a-119">コマンドラインから多くのアプリケーション管理タスクを実行することができます。</span><span class="sxs-lookup"><span data-stu-id="7215a-119">You can perform many application management tasks from the command line.</span></span> <span data-ttu-id="7215a-120">コマンド ライン ツールの詳細については、次を参照してください。 [BTSTask コマンド ライン リファレンス](http://go.microsoft.com/fwlink/?LinkId=155003)(http://go.microsoft.com/fwlink/?LinkId=155003)。</span><span class="sxs-lookup"><span data-stu-id="7215a-120">For more information about the command-line tool, see [BTSTask Command Line Reference](http://go.microsoft.com/fwlink/?LinkId=155003) (http://go.microsoft.com/fwlink/?LinkId=155003).</span></span>|  
|<span data-ttu-id="7215a-121">スクリプト API とプログラミング API</span><span class="sxs-lookup"><span data-stu-id="7215a-121">Scripting and programmability APIs</span></span>|<span data-ttu-id="7215a-122">Microsoft Windows Management Instrumentation (WMI) や BizTalk エクスプローラー オブジェクト モデルを使用して、多くのアプリケーション管理タスクを自動化するスクリプトを作成および実行することができます。</span><span class="sxs-lookup"><span data-stu-id="7215a-122">You can use Microsoft Windows Management Instrumentation (WMI) or the BizTalk Explorer Object Model to create and run scripts that automate many application management tasks.</span></span> <span data-ttu-id="7215a-123">スクリプト作成の詳細については、次を参照してください。 [WMI クラス参照](http://go.microsoft.com/fwlink/?LinkId=155004)(http://go.microsoft.com/fwlink/?LinkId=155004)。</span><span class="sxs-lookup"><span data-stu-id="7215a-123">For more information about scripting, see [WMI Class Reference](http://go.microsoft.com/fwlink/?LinkId=155004) (http://go.microsoft.com/fwlink/?LinkId=155004).</span></span>|  
|[!INCLUDE[btsVStudio2008](../includes/btsvstudio2008-md.md)]|<span data-ttu-id="7215a-124">Visual Studio で BizTalk アセンブリを作成、BizTalk アプリケーションに自動的に展開する展開コマンドを使用して、および BizTalk エクスプ ローラーを使用して、Visual Studio 内からアプリケーションのアイテムを構成することができます。</span><span class="sxs-lookup"><span data-stu-id="7215a-124">You can create BizTalk assemblies in Visual Studio, use the Deploy command to automatically deploy them into a BizTalk application, and use BizTalk Explorer to configure application artifacts from within Visual Studio.</span></span> <span data-ttu-id="7215a-125">Visual Studio 内での作業の詳細については、次を参照してください。 [BizTalk アプリケーションに Visual Studio から BizTalk アセンブリを展開する](http://go.microsoft.com/fwlink/?LinkID=154719)(http://go.microsoft.com/fwlink/?LinkID=154719)。</span><span class="sxs-lookup"><span data-stu-id="7215a-125">For more information about working within Visual Studio, see [Deploying BizTalk Assemblies from Visual Studio into a BizTalk Application](http://go.microsoft.com/fwlink/?LinkID=154719) (http://go.microsoft.com/fwlink/?LinkID=154719).</span></span>|  
  
## <a name="in-this-section"></a><span data-ttu-id="7215a-126">このセクションの内容</span><span class="sxs-lookup"><span data-stu-id="7215a-126">In This Section</span></span>  
  
-   [<span data-ttu-id="7215a-127">アプリケーションを作成します。</span><span class="sxs-lookup"><span data-stu-id="7215a-127">Creating an Application</span></span>](../technical-guides/creating-an-application.md)  
  
-   [<span data-ttu-id="7215a-128">アセンブリを展開します。</span><span class="sxs-lookup"><span data-stu-id="7215a-128">Deploying an Assembly</span></span>](../technical-guides/deploying-an-assembly.md)  
  
-   [<span data-ttu-id="7215a-129">成果物をアプリケーションに追加します。</span><span class="sxs-lookup"><span data-stu-id="7215a-129">Adding Artifacts to an Application</span></span>](../technical-guides/adding-artifacts-to-an-application.md)  
  
-   [<span data-ttu-id="7215a-130">アプリケーションを .msi ファイルにエクスポートする方法</span><span class="sxs-lookup"><span data-stu-id="7215a-130">How to Export an Application to an .msi File</span></span>](../technical-guides/how-to-export-an-application-to-an-msi-file.md)  
  
-   [<span data-ttu-id="7215a-131">バインドをバインド ファイルにエクスポートする方法</span><span class="sxs-lookup"><span data-stu-id="7215a-131">How to Export Bindings to a Binding File</span></span>](../technical-guides/how-to-export-bindings-to-a-binding-file.md)  
  
-   [<span data-ttu-id="7215a-132">バインド ファイルをアプリケーション 1 に追加する方法</span><span class="sxs-lookup"><span data-stu-id="7215a-132">How to Add a Binding File to an Application1</span></span>](../technical-guides/how-to-add-a-binding-file-to-an-application1.md)  
  
-   [<span data-ttu-id="7215a-133">アプリケーションを .msi ファイルからインポートする方法</span><span class="sxs-lookup"><span data-stu-id="7215a-133">How to Import an Application from an .msi File</span></span>](../technical-guides/how-to-import-an-application-from-an-msi-file.md)  
  
-   [<span data-ttu-id="7215a-134">アプリケーションをインストールする方法</span><span class="sxs-lookup"><span data-stu-id="7215a-134">How to Install an Application</span></span>](../technical-guides/how-to-install-an-application.md)  
  
-   [<span data-ttu-id="7215a-135">バインド ファイルからバインドをインポートする方法</span><span class="sxs-lookup"><span data-stu-id="7215a-135">How to Import Bindings from a Binding File</span></span>](../technical-guides/how-to-import-bindings-from-a-binding-file.md)  
  
-   [<span data-ttu-id="7215a-136">アプリケーションのテスト</span><span class="sxs-lookup"><span data-stu-id="7215a-136">Testing an Application</span></span>](../technical-guides/testing-an-application.md)  
  
-   [<span data-ttu-id="7215a-137">アプリケーションへの参照を追加する方法</span><span class="sxs-lookup"><span data-stu-id="7215a-137">How to Add a Reference to an Application</span></span>](../technical-guides/how-to-add-a-reference-to-an-application.md)