---
title: "バインドをバインド ファイルにエクスポートする方法 |Microsoft ドキュメント"
ms.custom: 
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: 
ms.suite: 
ms.tgt_pltfrm: 
ms.topic: article
ms.assetid: 3734ae6d-b790-40f2-8403-d7c7fdbe381b
caps.latest.revision: "2"
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: 052f30e7e1fa2461d1332702dbd61b6aa76451b9
ms.sourcegitcommit: cb908c540d8f1a692d01dc8f313e16cb4b4e696d
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 09/20/2017
---
# <a name="how-to-export-bindings-to-a-binding-file"></a><span data-ttu-id="e4ce6-102">バインドをバインド ファイルにエクスポートする方法</span><span class="sxs-lookup"><span data-stu-id="e4ce6-102">How to Export Bindings to a Binding File</span></span>
<span data-ttu-id="e4ce6-103">バインド ファイルを使用して既存の別の BizTalk アプリケーションに BizTalk アプリケーションのバインドをエクスポートすることができます。</span><span class="sxs-lookup"><span data-stu-id="e4ce6-103">You can export the bindings of a BizTalk application into another existing BizTalk application using a binding file.</span></span> <span data-ttu-id="e4ce6-104">グループ内のすべてのバインディングまたはアセンブリのバインドをエクスポートすることもできます。</span><span class="sxs-lookup"><span data-stu-id="e4ce6-104">You can also export all the bindings in a group or the binding for an assembly.</span></span> <span data-ttu-id="e4ce6-105">その後、アプリケーションまたはグループのいずれかに、これらのバインドをインポートできます。</span><span class="sxs-lookup"><span data-stu-id="e4ce6-105">Subsequently, you can import those bindings into either an application or group.</span></span>  
  
 <span data-ttu-id="e4ce6-106">バインド ファイルは、BizTalk 管理データベースとそのリレーションシップ内の成果物を記述する XML ファイルです。</span><span class="sxs-lookup"><span data-stu-id="e4ce6-106">A binding file is an XML file that describes the artifacts in the BizTalk Management database and their relationships.</span></span> <span data-ttu-id="e4ce6-107">各 BizTalk Server オーケストレーション、パイプライン、マップ、または BizTalk アセンブリ、アプリケーション、またはグループのスコープ内のスキーマのバインド情報が含まれています。</span><span class="sxs-lookup"><span data-stu-id="e4ce6-107">It contains binding information for each BizTalk Server orchestration, pipeline, map, or schema in the scope of a BizTalk assembly, application, or group.</span></span> <span data-ttu-id="e4ce6-108">各送信ポートの構成設定が含まれている、送信ポート グループ、受信ポート、受信場所、およびパーティです。</span><span class="sxs-lookup"><span data-stu-id="e4ce6-108">It contains the configuration settings for each send port, send port group, receive port, receive location, and party.</span></span> <span data-ttu-id="e4ce6-109">各オーケストレーションがバインドされているホストとその信頼レベルについても説明します。</span><span class="sxs-lookup"><span data-stu-id="e4ce6-109">It also describes which host each orchestration is bound to and its trust level.</span></span>  
  
## <a name="why-to-export-to-a-binding-file"></a><span data-ttu-id="e4ce6-110">バインド ファイルにエクスポートする理由</span><span class="sxs-lookup"><span data-stu-id="e4ce6-110">Why to Export to a Binding File</span></span>  
 <span data-ttu-id="e4ce6-111">バインド ファイルを迅速に展開次のシナリオでバインドを手動で構成する必要があります。</span><span class="sxs-lookup"><span data-stu-id="e4ce6-111">Binding files can speed deployment in the following scenarios by avoiding the need to manually configure bindings:</span></span>  
  
-   <span data-ttu-id="e4ce6-112">**アプリケーションを 1 つの展開環境間で移動するには**</span><span class="sxs-lookup"><span data-stu-id="e4ce6-112">**Moving an application from one deployment environment to another**</span></span>  
  
     <span data-ttu-id="e4ce6-113">バインド ファイルを使用すると、手動で構成するさまざまな展開環境のバインドなど、開発環境からテスト環境を回避する展開の速度が向上できます。</span><span class="sxs-lookup"><span data-stu-id="e4ce6-113">Using a binding file can speed deployment by avoiding the need to manually configure bindings for different deployment environments, such as from a development environment to a test environment.</span></span>  
  
-   <span data-ttu-id="e4ce6-114">**アセンブリの更新**</span><span class="sxs-lookup"><span data-stu-id="e4ce6-114">**Updating an assembly**</span></span>  
  
     <span data-ttu-id="e4ce6-115">バインド ファイルを使用して、自動的に適用またはアセンブリの更新後にアセンブリへのバインドを再適用することができます。</span><span class="sxs-lookup"><span data-stu-id="e4ce6-115">You can use a binding file to automatically apply or reapply the bindings to an assembly after an update of the assembly.</span></span>  
  
-   <span data-ttu-id="e4ce6-116">**複数の BizTalk グループにアセンブリを展開します。**</span><span class="sxs-lookup"><span data-stu-id="e4ce6-116">**Deploying an assembly to multiple BizTalk groups**</span></span>  
  
     <span data-ttu-id="e4ce6-117">バインド ファイルを使用して複数の BizTalk グループに展開されているアセンブリのバインドを個別に構成する必要性を回避できます。</span><span class="sxs-lookup"><span data-stu-id="e4ce6-117">You can avoid the need to separately configure the bindings for an assembly deployed into multiple BizTalk groups by using a binding file.</span></span>  
  
 <span data-ttu-id="e4ce6-118">バインド ファイルを使用する柔軟性をアプリケーションにバインドを適用します。</span><span class="sxs-lookup"><span data-stu-id="e4ce6-118">Using a binding file gives you flexibility in applying bindings to an application.</span></span> <span data-ttu-id="e4ce6-119">アプリケーションを .msi ファイルをエクスポートするときにのみのすべてのアプリケーションのバインドは、.msi ファイルにエクスポートされるようにするを指定することができます。</span><span class="sxs-lookup"><span data-stu-id="e4ce6-119">When you export an application to an .msi file, you can only specify that all of the bindings for the application will be exported to the .msi file.</span></span> <span data-ttu-id="e4ce6-120">バインド ファイルでは、次の操作を行うことができます。</span><span class="sxs-lookup"><span data-stu-id="e4ce6-120">With binding files you can do the following:</span></span>  
  
-   <span data-ttu-id="e4ce6-121">現在のアプリケーションからすべてのバインド、現在のグループからすべてのバインドまたは 1 つのアセンブリのバインドだけバインド ファイルにエクスポートします。</span><span class="sxs-lookup"><span data-stu-id="e4ce6-121">Export to a binding file all bindings from the current application, all bindings from the current group, or only the bindings for a single assembly.</span></span> <span data-ttu-id="e4ce6-122">(これを行う管理コンソールでアプリケーションのバインドのエクスポート コマンドを使用しています。)</span><span class="sxs-lookup"><span data-stu-id="e4ce6-122">(You do so by using the Export Bindings command for an application in the Administration console.)</span></span>  
  
-   <span data-ttu-id="e4ce6-123">そのバインドはすぐに適用できるように、またはアプリケーションが別のグループにインポートされるとき、バインドが適用されるように、(リソースの追加のコマンドを使用する) アプリケーションにバインド ファイルを追加できます。</span><span class="sxs-lookup"><span data-stu-id="e4ce6-123">You can add a binding file to an application (using the Add Resources command) so that its bindings are applied immediately or so the bindings are applied when the application is imported into another group.</span></span>  
  
-   <span data-ttu-id="e4ce6-124">(リソースの追加のコマンドを使用して) アプリケーションに複数のバインド ファイルを追加し、それぞれのターゲット展開環境を指定できます。</span><span class="sxs-lookup"><span data-stu-id="e4ce6-124">You can add multiple binding files to an application (using the Add Resources command) and specify a target deployment environment for each one.</span></span> <span data-ttu-id="e4ce6-125">これにより、複数のデプロイ環境で単一の展開パッケージを使用できます。</span><span class="sxs-lookup"><span data-stu-id="e4ce6-125">This enables you to use a single deployment package for multiple deployment environments.</span></span> <span data-ttu-id="e4ce6-126">アプリケーションをインポートするときに適用するバインドを選択できます。</span><span class="sxs-lookup"><span data-stu-id="e4ce6-126">When you import the application, you can select which bindings to apply.</span></span>  
  
-   <span data-ttu-id="e4ce6-127">複数のアセンブリ、アプリケーション内の個別のバインド ファイルをエクスポートできます。</span><span class="sxs-lookup"><span data-stu-id="e4ce6-127">You can export separate binding files for multiple assemblies in an application.</span></span>  
  
-   <span data-ttu-id="e4ce6-128">バインド ファイルを生成した後に編集して、そのバインド情報を変更できます。</span><span class="sxs-lookup"><span data-stu-id="e4ce6-128">You can edit binding files after you generate them to change their binding information.</span></span>  
  
## <a name="how-to-export-to-a-binding-file"></a><span data-ttu-id="e4ce6-129">バインド ファイルにエクスポートする方法</span><span class="sxs-lookup"><span data-stu-id="e4ce6-129">How to Export to a Binding File</span></span>  
 <span data-ttu-id="e4ce6-130">アプリケーションのバインドのエクスポート コマンドを実行して、バインド ファイルにアプリケーションのバインドをエクスポートする、[!INCLUDE[btsBizTalkServer2006r3](../includes/btsbiztalkserver2006r3-md.md)]管理コンソールまたは BTSTask ExportBindings コマンドを使用するコマンドラインです。</span><span class="sxs-lookup"><span data-stu-id="e4ce6-130">You export the bindings of an application to a binding file by executing the Export Bindings command for the application in the [!INCLUDE[btsBizTalkServer2006r3](../includes/btsbiztalkserver2006r3-md.md)] Administration console, or by using the BTSTask ExportBindings command on the command line.</span></span>  
  
 <span data-ttu-id="e4ce6-131">セキュリティ上の理由により、BizTalk Server では、バインド ファイルのエクスポート時にバインドのパスワードがファイルから削除されます。</span><span class="sxs-lookup"><span data-stu-id="e4ce6-131">For security reasons, when you export a binding file, BizTalk Server removes the passwords for the bindings from the file.</span></span> <span data-ttu-id="e4ce6-132">バインドをインポートした後で、送信ポートと受信場所のパスワードを再構成する必要があります。</span><span class="sxs-lookup"><span data-stu-id="e4ce6-132">After importing the bindings, you must reconfigure passwords for send ports and receive locations before they will function.</span></span> <span data-ttu-id="e4ce6-133">BizTalk Server 管理コンソールの [トランスポートのプロパティ] ダイアログ ボックスで、送信ポートと受信場所のパスワードをそれぞれ構成します。</span><span class="sxs-lookup"><span data-stu-id="e4ce6-133">You configure passwords in the Transport Properties dialog box of the BizTalk Server Administration console for the send port or receive location.</span></span>  
  
 <span data-ttu-id="e4ce6-134">バインド ファイルの情報により既存の構成情報が置き換えられます。</span><span class="sxs-lookup"><span data-stu-id="e4ce6-134">Information in a binding file supersedes existing configuration information.</span></span> <span data-ttu-id="e4ce6-135">バインド ファイルのアイテムの名前が既存の構成のアイテムの名前と一致する場合は、バインド ファイルをインポートすると、バインド ファイルのアイテムで既存の構成のアイテムが更新されます。</span><span class="sxs-lookup"><span data-stu-id="e4ce6-135">If the name of an artifact in a binding file matches the name of an artifact in your existing configuration, the artifact in the binding file will update the artifact in your existing configuration when you import the binding file.</span></span>  
  
 <span data-ttu-id="e4ce6-136">バインド ファイル内のホストと信頼レベルを格納する方法については、アプリケーション、およびバインドが適用される順序でレベル ホストおよび信頼へのバインド ファイル内のホストおよび信頼レベルの照合方法は、「[バインド ファイルとアプリケーションの配置](http://go.microsoft.com/fwlink/?LinkID=154726)(http://go.microsoft.com/fwlink/?LinkID=154726)。</span><span class="sxs-lookup"><span data-stu-id="e4ce6-136">For information about how hosts and trust levels are stored in binding files, how host and trust levels in a binding file are matched to hosts and trust levels in the application, and the order in which bindings are applied, see [Binding Files and Application Deployment](http://go.microsoft.com/fwlink/?LinkID=154726) (http://go.microsoft.com/fwlink/?LinkID=154726).</span></span> <span data-ttu-id="e4ce6-137">BizTalk アプリケーションのバインドをエクスポートする方法については、次を参照してください。 [BizTalk アプリケーションのバインドのエクスポート方法](http://go.microsoft.com/fwlink/?LinkId=155009)(http://go.microsoft.com/fwlink/?LinkId=155009)。</span><span class="sxs-lookup"><span data-stu-id="e4ce6-137">For instructions on how to export bindings for a BizTalk application, see [How to Export Bindings for a BizTalk Application](http://go.microsoft.com/fwlink/?LinkId=155009) (http://go.microsoft.com/fwlink/?LinkId=155009).</span></span>