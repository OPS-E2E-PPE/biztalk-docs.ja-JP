---
title: オーケストレーション (BizTalk Server サンプル) を参加させる |Microsoft Docs
ms.custom: ''
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: ''
ms.suite: ''
ms.tgt_pltfrm: ''
ms.topic: article
helpviewer_keywords:
- orchestrations, examples
- orchestrations, enlisting
- examples, orchestrations
ms.assetid: d8d53e59-2313-40dd-a278-0a29d8eb4ce8
caps.latest.revision: 11
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: c70276a30004c1a21f95a3e2ff43a28209deea87
ms.sourcegitcommit: 381e83d43796a345488d54b3f7413e11d56ad7be
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 05/07/2019
ms.locfileid: "65389073"
---
# <a name="enlist-orchestration-biztalk-server-sample"></a><span data-ttu-id="ab9c9-102">オーケストレーション (BizTalk Server サンプル) を参加させる</span><span class="sxs-lookup"><span data-stu-id="ab9c9-102">Enlist Orchestration (BizTalk Server Sample)</span></span>
<span data-ttu-id="ab9c9-103">オーケストレーションの参加サンプルでは、ホストに BizTalk Server オーケストレーションを参加させる方法を示します。</span><span class="sxs-lookup"><span data-stu-id="ab9c9-103">The Enlist Orchestration sample demonstrates how to enlist a BizTalk Server orchestration to a host.</span></span>  
  
> [!WARNING]
>  <span data-ttu-id="ab9c9-104">展開スクリプトは、展開後に不要になった場合は、削除する必要があります。</span><span class="sxs-lookup"><span data-stu-id="ab9c9-104">Deployment scripts should be removed after deployment if not needed.</span></span> <span data-ttu-id="ab9c9-105">保持する必要のある管理スクリプトおよび他のスクリプトは、ACL によってセキュリティで保護し、厳重に監視する必要があります。</span><span class="sxs-lookup"><span data-stu-id="ab9c9-105">Administration scripts and other scripts that must remain should be secured by ACL’s and closely monitored.</span></span>  
  
## <a name="what-this-sample-does"></a><span data-ttu-id="ab9c9-106">このサンプルの処理</span><span class="sxs-lookup"><span data-stu-id="ab9c9-106">What This Sample Does</span></span>  
 <span data-ttu-id="ab9c9-107">このサンプルは、Windows Management Instrumentation (WMI) オブジェクト モデルにアクセスする Visual Basic Scripting Edition (VBScript) バージョンと Visual c# バージョンにアクセスする、 **System.Management**によって提供されるオブジェクト.NET Framework です。</span><span class="sxs-lookup"><span data-stu-id="ab9c9-107">This sample includes a Visual Basic Scripting Edition (VBScript) version that accesses the Windows Management Instrumentation (WMI) object model, and a Visual C# version that accesses the **System.Management** objects provided by the .NET Framework.</span></span> <span data-ttu-id="ab9c9-108">これらのバージョンのどちらも最終的には、次の操作を実行する BizTalk Server WMI プロバイダーにアクセスします。</span><span class="sxs-lookup"><span data-stu-id="ab9c9-108">Both of these versions ultimately access the BizTalk Server WMI provider to perform the following operations:</span></span>  
  
-   <span data-ttu-id="ab9c9-109">オーケストレーション名とアセンブリ名を指定するには、特定のクエリには、BizTalk Server オーケストレーションが展開されています。</span><span class="sxs-lookup"><span data-stu-id="ab9c9-109">Given an orchestration name and an assembly name, query for a specific deployed BizTalk Server orchestration.</span></span>  
  
-   <span data-ttu-id="ab9c9-110">既定のホストにオーケストレーションを参加させます。</span><span class="sxs-lookup"><span data-stu-id="ab9c9-110">Enlist that orchestration to the default host.</span></span>  
  
-   <span data-ttu-id="ab9c9-111">意味のある情報がユーザーに返されるようにエラーを処理します。</span><span class="sxs-lookup"><span data-stu-id="ab9c9-111">Handle any errors such that meaningful information is returned to the user.</span></span>  
  
## <a name="where-to-find-this-sample"></a><span data-ttu-id="ab9c9-112">このサンプルの場所</span><span class="sxs-lookup"><span data-stu-id="ab9c9-112">Where to Find This Sample</span></span>  
 <span data-ttu-id="ab9c9-113">サンプルは、次の SDK の場所に配置されます。</span><span class="sxs-lookup"><span data-stu-id="ab9c9-113">The samples are located in the following SDK locations:</span></span>  
  
- <span data-ttu-id="ab9c9-114">VBScript バージョン:\<*Samples Path*\>\Admin\WMI\Enlist Orchestration\VBScript\\</span><span class="sxs-lookup"><span data-stu-id="ab9c9-114">VBScript version: \<*Samples Path*\>\Admin\WMI\Enlist Orchestration\VBScript\\</span></span>  
  
- <span data-ttu-id="ab9c9-115">VisusalC#バージョン。\<*Samples Path*\>\Admin\WMI\Enlist Orchestration\CSharp\\</span><span class="sxs-lookup"><span data-stu-id="ab9c9-115">Visusal C# version: \<*Samples Path*\>\Admin\WMI\Enlist Orchestration\CSharp\\</span></span>  
  
  <span data-ttu-id="ab9c9-116">次の表は、このサンプルのファイルとその目的を示しています。</span><span class="sxs-lookup"><span data-stu-id="ab9c9-116">The following table shows the files in this sample and describes their purpose.</span></span>  
  
|<span data-ttu-id="ab9c9-117">ファイル</span><span class="sxs-lookup"><span data-stu-id="ab9c9-117">File(s)</span></span>|<span data-ttu-id="ab9c9-118">説明</span><span class="sxs-lookup"><span data-stu-id="ab9c9-118">Description</span></span>|  
|---------------|-----------------|  
|<span data-ttu-id="ab9c9-119">\VBScript フォルダー。</span><span class="sxs-lookup"><span data-stu-id="ab9c9-119">In the \VBScript folder:</span></span><br /><br /> <span data-ttu-id="ab9c9-120">EnlistOrch.vbs</span><span class="sxs-lookup"><span data-stu-id="ab9c9-120">EnlistOrch.vbs</span></span>|<span data-ttu-id="ab9c9-121">ホストに参加させるオーケストレーションを指定するパラメーターを取る VBScript ファイル。</span><span class="sxs-lookup"><span data-stu-id="ab9c9-121">VBScript file that takes parameters to specify an orchestration to be enlisted to a host.</span></span>|  
|<span data-ttu-id="ab9c9-122">\CSharp フォルダー。</span><span class="sxs-lookup"><span data-stu-id="ab9c9-122">In the \CSharp folder:</span></span><br /><br /> <span data-ttu-id="ab9c9-123">App.ico、AssemblyInfo.cs、BTSampleEnlistOrc.csproj、BTSampleEnlistOrc.sln、EnlistOrc.cs</span><span class="sxs-lookup"><span data-stu-id="ab9c9-123">App.ico, AssemblyInfo.cs, BTSampleEnlistOrc.csproj, BTSampleEnlistOrc.sln, EnlistOrc.cs</span></span>|<span data-ttu-id="ab9c9-124">プロジェクト、ソリューション、およびビジュアルを構築するためのソース ファイルC#ホストに参加させるオーケストレーションを指定するパラメーターを受け取るコマンド ライン アプリケーションです。</span><span class="sxs-lookup"><span data-stu-id="ab9c9-124">Project, solution, and source files for building a Visual C# command-line application that takes parameters to specify an orchestration to be enlisted to a host.</span></span>|  
  
## <a name="building-and-initializing-this-sample"></a><span data-ttu-id="ab9c9-125">このサンプルのビルドと初期化</span><span class="sxs-lookup"><span data-stu-id="ab9c9-125">Building and Initializing This Sample</span></span>  
 <span data-ttu-id="ab9c9-126">オーケストレーションの参加サンプルの VBScript バージョンは、ビルドまたは初期化する必要はありませんは、1 つ Visual Basic スクリプト ファイルで構成されます。</span><span class="sxs-lookup"><span data-stu-id="ab9c9-126">The VBScript version of the Enlist Orchestration sample consists of a single Visual Basic script file that you do not need to build or initialize.</span></span>  
  
#### <a name="to-build-the-visual-c-version-of-the-enlist-orchestration-sample"></a><span data-ttu-id="ab9c9-127">ビジュアルを構築するC#オーケストレーションの参加サンプルのバージョン</span><span class="sxs-lookup"><span data-stu-id="ab9c9-127">To build the Visual C# version of the Enlist Orchestration sample</span></span>  
  
1. <span data-ttu-id="ab9c9-128">[!INCLUDE[btsVStudioNoVersion](../includes/btsvstudionoversion-md.md)]、ソリューション ファイル BTSampleEnlistOrc.sln を開きます。</span><span class="sxs-lookup"><span data-stu-id="ab9c9-128">In [!INCLUDE[btsVStudioNoVersion](../includes/btsvstudionoversion-md.md)], open the solution file BTSampleEnlistOrc.sln.</span></span>  
  
2. <span data-ttu-id="ab9c9-129">**ビルド** メニューのをクリックして**ソリューションのビルド**します。</span><span class="sxs-lookup"><span data-stu-id="ab9c9-129">In the **Build** menu, click **Build Solution**.</span></span>  
  
#### <a name="to-run-the-enlist-orchestration-sample"></a><span data-ttu-id="ab9c9-130">オーケストレーションの参加のサンプルを実行します。</span><span class="sxs-lookup"><span data-stu-id="ab9c9-130">To run the Enlist Orchestration sample.</span></span>  
  
1.  <span data-ttu-id="ab9c9-131">コマンド ウィンドウで、ビジュアルの VBScript バージョンとの実行を計画しているかどうかに応じて、次のフォルダーのいずれかに移動します。C#のこのバージョンのサンプルをそれぞれ。</span><span class="sxs-lookup"><span data-stu-id="ab9c9-131">In a command window, navigate to one of the following folders, depending on whether you are planning to run the VBScript version or the Visual C# version of this sample, respectively:</span></span>  
  
     <span data-ttu-id="ab9c9-132">\<*Samples Path*\>\Admin\WMI\Enlist Orchestration\VBScript\\</span><span class="sxs-lookup"><span data-stu-id="ab9c9-132">\<*Samples Path*\>\Admin\WMI\Enlist Orchestration\VBScript\\</span></span>  
  
     <span data-ttu-id="ab9c9-133">\<*パスのサンプル*\>AdminWMIEnlist OrchestrationCSharpbinDebug</span><span class="sxs-lookup"><span data-stu-id="ab9c9-133">\<*Samples Path*\>AdminWMIEnlist OrchestrationCSharpbinDebug</span></span>  
  
2.  <span data-ttu-id="ab9c9-134">Cscript プログラムを使用して enlistorch.vbs を実行するか、ビジュアルの VBScript バージョンとの実行を計画しているかどうかに応じて、ファイル EnlistOrc.exe を実行C#のこのバージョンのサンプル、それぞれします。</span><span class="sxs-lookup"><span data-stu-id="ab9c9-134">Either run the file EnlistOrch.vbs using the cscript program, or run the file EnlistOrc.exe, depending on whether you are planning to run the VBScript version or the Visual C# version of this sample, respectively.</span></span> <span data-ttu-id="ab9c9-135">いずれの場合は、次のコマンドライン引数を渡します。</span><span class="sxs-lookup"><span data-stu-id="ab9c9-135">In any event, pass the following command-line arguments:</span></span>  
  
    -   <span data-ttu-id="ab9c9-136">**\<** ***OrchestrationName* \>.**</span><span class="sxs-lookup"><span data-stu-id="ab9c9-136">**\<** ***OrchestrationName* \>.**</span></span> <span data-ttu-id="ab9c9-137">参加させるオーケストレーションの名前。</span><span class="sxs-lookup"><span data-stu-id="ab9c9-137">The name of the orchestration to be enlisted.</span></span>  
  
    -   <span data-ttu-id="ab9c9-138">**\<** ***AssemblyName* \>.**</span><span class="sxs-lookup"><span data-stu-id="ab9c9-138">**\<** ***AssemblyName* \>.**</span></span> <span data-ttu-id="ab9c9-139">オーケストレーションが展開されているアセンブリの名前。</span><span class="sxs-lookup"><span data-stu-id="ab9c9-139">The name of the assembly in which the orchestration was deployed.</span></span> <span data-ttu-id="ab9c9-140">アセンブリ名に空白が含まれている場合は、名前を引用符で囲みます。</span><span class="sxs-lookup"><span data-stu-id="ab9c9-140">If the assembly name contains spaces, enclose the name in quotes.</span></span>  
  
         <span data-ttu-id="ab9c9-141">以下に例を示します。(VBScript) の場合:</span><span class="sxs-lookup"><span data-stu-id="ab9c9-141">For example: (VBScript):</span></span>  
  
        ```  
        cscript EnlistOrch.vbs MyBusinessOrchestration "My Business Assembly"  
        ```  
  
         <span data-ttu-id="ab9c9-142">-または-(Visual c#)。</span><span class="sxs-lookup"><span data-stu-id="ab9c9-142">-OR- (Visual C#):</span></span>  
  
        ```  
        EnlistOrc MyBusinessOrchestration "My Business Assembly"  
        ```  
  
## <a name="comments"></a><span data-ttu-id="ab9c9-143">コメント</span><span class="sxs-lookup"><span data-stu-id="ab9c9-143">Comments</span></span>  
 <span data-ttu-id="ab9c9-144">すべてのタスクで実行できる、[!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)]ビジュアルを使用して、Windows WMI オブジェクト モデルにアクセスするスクリプトを使用して、管理コンソールを実行することもC#にアクセスする、 **System.Management**オブジェクト.NET Framework によって提供されます。</span><span class="sxs-lookup"><span data-stu-id="ab9c9-144">All tasks that you can perform in the [!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)] Administration console can also be performed by using script that accesses the Windows WMI object model and by using Visual C# that accesses the **System.Management** objects provided by the .NET Framework.</span></span>  
  
 <span data-ttu-id="ab9c9-145">スクリプト ファイル EnlistOrch.vbs およびビジュアルC#ソース ファイル EnlistOrc.cs には、実行する操作についての説明と詳細なコメントが含まれています。</span><span class="sxs-lookup"><span data-stu-id="ab9c9-145">The script file EnlistOrch.vbs and the Visual C# source file EnlistOrc.cs contain detailed comments with further explanation about the operations that they perform.</span></span> <span data-ttu-id="ab9c9-146">詳細については、Windows Management Instrumentation を参照してください。 [ http://go.microsoft.com/fwlink/?LinkId=21102](http://go.microsoft.com/fwlink/?LinkId=21102)します。</span><span class="sxs-lookup"><span data-stu-id="ab9c9-146">For more information, see Windows Management Instrumentation at [http://go.microsoft.com/fwlink/?LinkId=21102](http://go.microsoft.com/fwlink/?LinkId=21102).</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="ab9c9-147">参照</span><span class="sxs-lookup"><span data-stu-id="ab9c9-147">See Also</span></span>  
 [<span data-ttu-id="ab9c9-148">Admin-WMI (BizTalk Server Samples フォルダー)</span><span class="sxs-lookup"><span data-stu-id="ab9c9-148">Admin-WMI (BizTalk Server Samples Folder)</span></span>](../core/admin-wmi-biztalk-server-samples-folder.md)