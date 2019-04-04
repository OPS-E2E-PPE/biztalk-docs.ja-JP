---
title: バインド ファイルにバインドをエクスポートする方法 |Microsoft Docs
ms.custom: ''
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: ''
ms.suite: ''
ms.tgt_pltfrm: ''
ms.topic: article
ms.assetid: 3734ae6d-b790-40f2-8403-d7c7fdbe381b
caps.latest.revision: 2
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: 8ab9dd60b37c16169f76e052706adb43c4606fcf
ms.sourcegitcommit: 266308ec5c6a9d8d80ff298ee6051b4843c5d626
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 06/27/2018
ms.locfileid: "36982219"
---
# <a name="how-to-export-bindings-to-a-binding-file"></a><span data-ttu-id="d6271-102">バインド ファイルにバインドをエクスポートする方法</span><span class="sxs-lookup"><span data-stu-id="d6271-102">How to Export Bindings to a Binding File</span></span>
<span data-ttu-id="d6271-103">バインド ファイルを使用して既存の別の BizTalk アプリケーションに BizTalk アプリケーションのバインドをエクスポートすることができます。</span><span class="sxs-lookup"><span data-stu-id="d6271-103">You can export the bindings of a BizTalk application into another existing BizTalk application using a binding file.</span></span> <span data-ttu-id="d6271-104">グループ内のすべてのバインドまたはアセンブリのバインドをエクスポートすることもできます。</span><span class="sxs-lookup"><span data-stu-id="d6271-104">You can also export all the bindings in a group or the binding for an assembly.</span></span> <span data-ttu-id="d6271-105">その後、アプリケーションまたはグループにこれらのバインドをインポートできます。</span><span class="sxs-lookup"><span data-stu-id="d6271-105">Subsequently, you can import those bindings into either an application or group.</span></span>  
  
 <span data-ttu-id="d6271-106">バインド ファイルは、BizTalk 管理データベースとそのリレーションシップの成果物を表す XML ファイルです。</span><span class="sxs-lookup"><span data-stu-id="d6271-106">A binding file is an XML file that describes the artifacts in the BizTalk Management database and their relationships.</span></span> <span data-ttu-id="d6271-107">各 BizTalk Server オーケストレーション、パイプライン、マップ、またはスキーマを BizTalk アセンブリ、アプリケーション、またはグループのスコープ内のバインド情報が含まれています。</span><span class="sxs-lookup"><span data-stu-id="d6271-107">It contains binding information for each BizTalk Server orchestration, pipeline, map, or schema in the scope of a BizTalk assembly, application, or group.</span></span> <span data-ttu-id="d6271-108">各送信ポートの構成設定が含まれていますが、送信ポート グループ、受信ポート、受信場所、およびパーティです。</span><span class="sxs-lookup"><span data-stu-id="d6271-108">It contains the configuration settings for each send port, send port group, receive port, receive location, and party.</span></span> <span data-ttu-id="d6271-109">各オーケストレーションにバインドするホストとその信頼レベルについても説明します。</span><span class="sxs-lookup"><span data-stu-id="d6271-109">It also describes which host each orchestration is bound to and its trust level.</span></span>  
  
## <a name="why-to-export-to-a-binding-file"></a><span data-ttu-id="d6271-110">バインド ファイルにエクスポートする理由</span><span class="sxs-lookup"><span data-stu-id="d6271-110">Why to Export to a Binding File</span></span>  
 <span data-ttu-id="d6271-111">バインド ファイル、次のシナリオでバインドを手動で構成する必要がないので展開できる速度します。</span><span class="sxs-lookup"><span data-stu-id="d6271-111">Binding files can speed deployment in the following scenarios by avoiding the need to manually configure bindings:</span></span>  
  
- <span data-ttu-id="d6271-112">**1 つの展開環境から別のアプリケーションを移行**</span><span class="sxs-lookup"><span data-stu-id="d6271-112">**Moving an application from one deployment environment to another**</span></span>  
  
   <span data-ttu-id="d6271-113">バインド ファイルを使用すると、手動で構成するさまざまな環境のバインドなど、開発環境からテスト環境に依存せずに展開の時間が短縮できます。</span><span class="sxs-lookup"><span data-stu-id="d6271-113">Using a binding file can speed deployment by avoiding the need to manually configure bindings for different deployment environments, such as from a development environment to a test environment.</span></span>  
  
- <span data-ttu-id="d6271-114">**アセンブリの更新**</span><span class="sxs-lookup"><span data-stu-id="d6271-114">**Updating an assembly**</span></span>  
  
   <span data-ttu-id="d6271-115">バインド ファイルを使用して、自動的に適用またはアセンブリの更新後にアセンブリへのバインドを再適用することができます。</span><span class="sxs-lookup"><span data-stu-id="d6271-115">You can use a binding file to automatically apply or reapply the bindings to an assembly after an update of the assembly.</span></span>  
  
- <span data-ttu-id="d6271-116">**複数の BizTalk グループにアセンブリを展開します。**</span><span class="sxs-lookup"><span data-stu-id="d6271-116">**Deploying an assembly to multiple BizTalk groups**</span></span>  
  
   <span data-ttu-id="d6271-117">バインド ファイルを使用して複数の BizTalk グループに展開されているアセンブリのバインドを個別に構成する必要を回避できます。</span><span class="sxs-lookup"><span data-stu-id="d6271-117">You can avoid the need to separately configure the bindings for an assembly deployed into multiple BizTalk groups by using a binding file.</span></span>  
  
  <span data-ttu-id="d6271-118">バインド ファイルを使用して、アプリケーションへのバインドを適用する柔軟が。</span><span class="sxs-lookup"><span data-stu-id="d6271-118">Using a binding file gives you flexibility in applying bindings to an application.</span></span> <span data-ttu-id="d6271-119">アプリケーションを .msi ファイルをエクスポートするときに、すべてのアプリケーションのバインドは、.msi ファイルにエクスポートすることのみ指定できます。</span><span class="sxs-lookup"><span data-stu-id="d6271-119">When you export an application to an .msi file, you can only specify that all of the bindings for the application will be exported to the .msi file.</span></span> <span data-ttu-id="d6271-120">バインド ファイルでは、次の操作を行うことができます。</span><span class="sxs-lookup"><span data-stu-id="d6271-120">With binding files you can do the following:</span></span>  
  
- <span data-ttu-id="d6271-121">現在のアプリケーションからすべてのバインド、現在のグループからすべてのバインドまたは 1 つのアセンブリのバインドだけは、バインド ファイルにエクスポートします。</span><span class="sxs-lookup"><span data-stu-id="d6271-121">Export to a binding file all bindings from the current application, all bindings from the current group, or only the bindings for a single assembly.</span></span> <span data-ttu-id="d6271-122">(これを行う管理コンソールでアプリケーションのバインドのエクスポート コマンドを使用しています。)</span><span class="sxs-lookup"><span data-stu-id="d6271-122">(You do so by using the Export Bindings command for an application in the Administration console.)</span></span>  
  
- <span data-ttu-id="d6271-123">そのバインドがすぐに適用されるよう、またはアプリケーションが別のグループにインポートされるとき、バインドが適用されるように、(リソースの追加のコマンドを使用して) アプリケーションにバインド ファイルを追加できます。</span><span class="sxs-lookup"><span data-stu-id="d6271-123">You can add a binding file to an application (using the Add Resources command) so that its bindings are applied immediately or so the bindings are applied when the application is imported into another group.</span></span>  
  
- <span data-ttu-id="d6271-124">(リソースの追加のコマンドを使用して) アプリケーションに複数のバインド ファイルを追加し、それぞれに対してターゲット展開環境を指定できます。</span><span class="sxs-lookup"><span data-stu-id="d6271-124">You can add multiple binding files to an application (using the Add Resources command) and specify a target deployment environment for each one.</span></span> <span data-ttu-id="d6271-125">これにより、複数のデプロイ環境を単一の展開パッケージを使用することができます。</span><span class="sxs-lookup"><span data-stu-id="d6271-125">This enables you to use a single deployment package for multiple deployment environments.</span></span> <span data-ttu-id="d6271-126">アプリケーションをインポートするときに適用するバインドを選択できます。</span><span class="sxs-lookup"><span data-stu-id="d6271-126">When you import the application, you can select which bindings to apply.</span></span>  
  
- <span data-ttu-id="d6271-127">アプリケーションの複数のアセンブリには、個別のバインド ファイルをエクスポートできます。</span><span class="sxs-lookup"><span data-stu-id="d6271-127">You can export separate binding files for multiple assemblies in an application.</span></span>  
  
- <span data-ttu-id="d6271-128">バインド ファイルを生成した後に編集して、そのバインド情報を変更できます。</span><span class="sxs-lookup"><span data-stu-id="d6271-128">You can edit binding files after you generate them to change their binding information.</span></span>  
  
## <a name="how-to-export-to-a-binding-file"></a><span data-ttu-id="d6271-129">バインド ファイルにエクスポートする方法</span><span class="sxs-lookup"><span data-stu-id="d6271-129">How to Export to a Binding File</span></span>  
 <span data-ttu-id="d6271-130">BizTalk Server 管理コンソールで、アプリケーションのバインドのエクスポート コマンドを実行することによって、またはコマンドラインで BTSTask ExportBindings コマンドを使用して、バインド ファイルにアプリケーションのバインドをエクスポートします。</span><span class="sxs-lookup"><span data-stu-id="d6271-130">You export the bindings of an application to a binding file by executing the Export Bindings command for the application in the BizTalk Server Administration console, or by using the BTSTask ExportBindings command on the command line.</span></span>  
  
 <span data-ttu-id="d6271-131">セキュリティ上の理由により、BizTalk Server では、バインド ファイルのエクスポート時にバインドのパスワードがファイルから削除されます。</span><span class="sxs-lookup"><span data-stu-id="d6271-131">For security reasons, when you export a binding file, BizTalk Server removes the passwords for the bindings from the file.</span></span> <span data-ttu-id="d6271-132">バインドをインポートした後で、送信ポートと受信場所のパスワードを再構成する必要があります。</span><span class="sxs-lookup"><span data-stu-id="d6271-132">After importing the bindings, you must reconfigure passwords for send ports and receive locations before they will function.</span></span> <span data-ttu-id="d6271-133">BizTalk Server 管理コンソールの [トランスポートのプロパティ] ダイアログ ボックスで、送信ポートと受信場所のパスワードをそれぞれ構成します。</span><span class="sxs-lookup"><span data-stu-id="d6271-133">You configure passwords in the Transport Properties dialog box of the BizTalk Server Administration console for the send port or receive location.</span></span>  
  
 <span data-ttu-id="d6271-134">バインド ファイルの情報により既存の構成情報が置き換えられます。</span><span class="sxs-lookup"><span data-stu-id="d6271-134">Information in a binding file supersedes existing configuration information.</span></span> <span data-ttu-id="d6271-135">バインド ファイルのアイテムの名前が既存の構成のアイテムの名前と一致する場合は、バインド ファイルをインポートすると、バインド ファイルのアイテムで既存の構成のアイテムが更新されます。</span><span class="sxs-lookup"><span data-stu-id="d6271-135">If the name of an artifact in a binding file matches the name of an artifact in your existing configuration, the artifact in the binding file will update the artifact in your existing configuration when you import the binding file.</span></span>  
  
 <span data-ttu-id="d6271-136">バインド ファイル内のホストと信頼レベルを格納する方法については、アプリケーション、およびバインドが適用される順序でレベル ホストと信頼レベルをバインド ファイルを照合してホストと信頼する方法は、「[バインド ファイルとアプリケーションの展開](http://go.microsoft.com/fwlink/?LinkID=154726)(http://go.microsoft.com/fwlink/?LinkID=154726)します。</span><span class="sxs-lookup"><span data-stu-id="d6271-136">For information about how hosts and trust levels are stored in binding files, how host and trust levels in a binding file are matched to hosts and trust levels in the application, and the order in which bindings are applied, see [Binding Files and Application Deployment](http://go.microsoft.com/fwlink/?LinkID=154726) (http://go.microsoft.com/fwlink/?LinkID=154726).</span></span> <span data-ttu-id="d6271-137">BizTalk アプリケーションのバインドをエクスポートする方法の詳細については、[BizTalk アプリケーションのバインドのエクスポート方法](http://go.microsoft.com/fwlink/?LinkId=155009)(http://go.microsoft.com/fwlink/?LinkId=155009)を参照してください。</span><span class="sxs-lookup"><span data-stu-id="d6271-137">For instructions on how to export bindings for a BizTalk application, see [How to Export Bindings for a BizTalk Application](http://go.microsoft.com/fwlink/?LinkId=155009) (http://go.microsoft.com/fwlink/?LinkId=155009).</span></span>