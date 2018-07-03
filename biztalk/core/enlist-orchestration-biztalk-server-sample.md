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
ms.openlocfilehash: eac588d853a485f12c173cfd9d939369515a57fe
ms.sourcegitcommit: 266308ec5c6a9d8d80ff298ee6051b4843c5d626
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 06/27/2018
ms.locfileid: "37022240"
---
# <a name="enlist-orchestration-biztalk-server-sample"></a><span data-ttu-id="5b8de-102">オーケストレーション (BizTalk Server サンプル) を参加させる</span><span class="sxs-lookup"><span data-stu-id="5b8de-102">Enlist Orchestration (BizTalk Server Sample)</span></span>
<span data-ttu-id="5b8de-103">オーケストレーションの参加のサンプルは、BizTalk Server オーケストレーションをホストに参加させる方法を示します。</span><span class="sxs-lookup"><span data-stu-id="5b8de-103">The Enlist Orchestration sample demonstrates how to enlist a BizTalk Server orchestration to a host.</span></span>  
  
> [!WARNING]
>  <span data-ttu-id="5b8de-104">展開スクリプトは、展開後に不要になった場合は、削除する必要があります。</span><span class="sxs-lookup"><span data-stu-id="5b8de-104">Deployment scripts should be removed after deployment if not needed.</span></span> <span data-ttu-id="5b8de-105">保持する必要のある管理スクリプトおよび他のスクリプトは、ACL によってセキュリティで保護し、厳重に監視する必要があります。</span><span class="sxs-lookup"><span data-stu-id="5b8de-105">Administration scripts and other scripts that must remain should be secured by ACL’s and closely monitored.</span></span>  
  
## <a name="what-this-sample-does"></a><span data-ttu-id="5b8de-106">このサンプルの処理</span><span class="sxs-lookup"><span data-stu-id="5b8de-106">What This Sample Does</span></span>  
 <span data-ttu-id="5b8de-107">このサンプルは、Windows Management Instrumentation (WMI) オブジェクト モデルにアクセスする Visual Basic Scripting Edition (VBScript) バージョンと Visual c# バージョンにアクセスする、 **System.Management**によって提供されるオブジェクト.NET Framework です。</span><span class="sxs-lookup"><span data-stu-id="5b8de-107">This sample includes a Visual Basic Scripting Edition (VBScript) version that accesses the Windows Management Instrumentation (WMI) object model, and a Visual C# version that accesses the **System.Management** objects provided by the .NET Framework.</span></span> <span data-ttu-id="5b8de-108">いずれのバージョンも、最終的に BizTalk Server WMI プロバイダにアクセスして次の操作を実行します。</span><span class="sxs-lookup"><span data-stu-id="5b8de-108">Both of these versions ultimately access the BizTalk Server WMI provider to perform the following operations:</span></span>  
  
-   <span data-ttu-id="5b8de-109">オーケストレーション名とアセンブリ名を受け取ると、展開された特定の BizTalk Server オーケストレーションに対するクエリを実行します。</span><span class="sxs-lookup"><span data-stu-id="5b8de-109">Given an orchestration name and an assembly name, query for a specific deployed BizTalk Server orchestration.</span></span>  
  
-   <span data-ttu-id="5b8de-110">そのオーケストレーションを既定のホストに参加させます。</span><span class="sxs-lookup"><span data-stu-id="5b8de-110">Enlist that orchestration to the default host.</span></span>  
  
-   <span data-ttu-id="5b8de-111">意味のある情報がユーザーに返されるようにエラーを処理します。</span><span class="sxs-lookup"><span data-stu-id="5b8de-111">Handle any errors such that meaningful information is returned to the user.</span></span>  
  
## <a name="where-to-find-this-sample"></a><span data-ttu-id="5b8de-112">このサンプルの場所</span><span class="sxs-lookup"><span data-stu-id="5b8de-112">Where to Find This Sample</span></span>  
 <span data-ttu-id="5b8de-113">このサンプルは、次の SDK の場所にあります。</span><span class="sxs-lookup"><span data-stu-id="5b8de-113">The samples are located in the following SDK locations:</span></span>  
  
- <span data-ttu-id="5b8de-114">VBScript バージョン: \<*サンプル パス*\>\Admin\WMI\Enlist Orchestration\VBScript\\</span><span class="sxs-lookup"><span data-stu-id="5b8de-114">VBScript version: \<*Samples Path*\>\Admin\WMI\Enlist Orchestration\VBScript\\</span></span>  
  
- <span data-ttu-id="5b8de-115">Visusal c# バージョン: \<*サンプル パス*\>\Admin\WMI\Enlist Orchestration\CSharp\\</span><span class="sxs-lookup"><span data-stu-id="5b8de-115">Visusal C# version: \<*Samples Path*\>\Admin\WMI\Enlist Orchestration\CSharp\\</span></span>  
  
  <span data-ttu-id="5b8de-116">次の表は、このサンプルのファイルとその目的を示しています。</span><span class="sxs-lookup"><span data-stu-id="5b8de-116">The following table shows the files in this sample and describes their purpose.</span></span>  
  
|<span data-ttu-id="5b8de-117">ファイル</span><span class="sxs-lookup"><span data-stu-id="5b8de-117">File(s)</span></span>|<span data-ttu-id="5b8de-118">説明</span><span class="sxs-lookup"><span data-stu-id="5b8de-118">Description</span></span>|  
|---------------|-----------------|  
|<span data-ttu-id="5b8de-119">\VBScript フォルダー内のファイル : </span><span class="sxs-lookup"><span data-stu-id="5b8de-119">In the \VBScript folder:</span></span><br /><br /> <span data-ttu-id="5b8de-120">EnlistOrch.vbs</span><span class="sxs-lookup"><span data-stu-id="5b8de-120">EnlistOrch.vbs</span></span>|<span data-ttu-id="5b8de-121">ホストに参加させるオーケストレーションを指定するパラメータを受け取る VBScript ファイルです。</span><span class="sxs-lookup"><span data-stu-id="5b8de-121">VBScript file that takes parameters to specify an orchestration to be enlisted to a host.</span></span>|  
|<span data-ttu-id="5b8de-122">\CSharp フォルダー内のファイル : </span><span class="sxs-lookup"><span data-stu-id="5b8de-122">In the \CSharp folder:</span></span><br /><br /> <span data-ttu-id="5b8de-123">App.ico、AssemblyInfo.cs、BTSampleEnlistOrc.csproj、BTSampleEnlistOrc.sln、EnlistOrc.cs</span><span class="sxs-lookup"><span data-stu-id="5b8de-123">App.ico, AssemblyInfo.cs, BTSampleEnlistOrc.csproj, BTSampleEnlistOrc.sln, EnlistOrc.cs</span></span>|<span data-ttu-id="5b8de-124">ホストに参加させるオーケストレーションを指定するパラメータを受け取る Visual C# コマンド ライン アプリケーションを構築するための、プロジェクト、ソリューション、ソース ファイルです。</span><span class="sxs-lookup"><span data-stu-id="5b8de-124">Project, solution, and source files for building a Visual C# command-line application that takes parameters to specify an orchestration to be enlisted to a host.</span></span>|  
  
## <a name="building-and-initializing-this-sample"></a><span data-ttu-id="5b8de-125">このサンプルのビルドと初期化</span><span class="sxs-lookup"><span data-stu-id="5b8de-125">Building and Initializing This Sample</span></span>  
 <span data-ttu-id="5b8de-126">オーケストレーションの参加サンプルの VBScript バージョンは、構築または初期化が不要な 1 つの Visual Basic スクリプト ファイルで構成されます。</span><span class="sxs-lookup"><span data-stu-id="5b8de-126">The VBScript version of the Enlist Orchestration sample consists of a single Visual Basic script file that you do not need to build or initialize.</span></span>  
  
#### <a name="to-build-the-visual-c-version-of-the-enlist-orchestration-sample"></a><span data-ttu-id="5b8de-127">オーケストレーションの参加サンプルの Visual C# バージョンを構築するには</span><span class="sxs-lookup"><span data-stu-id="5b8de-127">To build the Visual C# version of the Enlist Orchestration sample</span></span>  
  
1. <span data-ttu-id="5b8de-128">[!INCLUDE[btsVStudioNoVersion](../includes/btsvstudionoversion-md.md)] で、ソリューション ファイル BTSampleEnlistOrc.sln を開きます。</span><span class="sxs-lookup"><span data-stu-id="5b8de-128">In [!INCLUDE[btsVStudioNoVersion](../includes/btsvstudionoversion-md.md)], open the solution file BTSampleEnlistOrc.sln.</span></span>  
  
2. <span data-ttu-id="5b8de-129">**ビルド** メニューのをクリックして**ソリューションのビルド**します。</span><span class="sxs-lookup"><span data-stu-id="5b8de-129">In the **Build** menu, click **Build Solution**.</span></span>  
  
#### <a name="to-run-the-enlist-orchestration-sample"></a><span data-ttu-id="5b8de-130">オーケストレーションの参加のサンプルを実行するには</span><span class="sxs-lookup"><span data-stu-id="5b8de-130">To run the Enlist Orchestration sample.</span></span>  
  
1.  <span data-ttu-id="5b8de-131">コマンド ウィンドウで、このサンプルの VBScript バージョンと Visual C# バージョンのどちらを実行するかに応じて、それぞれ以下のいずれかのフォルダに移動します。</span><span class="sxs-lookup"><span data-stu-id="5b8de-131">In a command window, navigate to one of the following folders, depending on whether you are planning to run the VBScript version or the Visual C# version of this sample, respectively:</span></span>  
  
     <span data-ttu-id="5b8de-132">\<*パスのサンプル*\>\Admin\WMI\Enlist Orchestration\VBScript\\</span><span class="sxs-lookup"><span data-stu-id="5b8de-132">\<*Samples Path*\>\Admin\WMI\Enlist Orchestration\VBScript\\</span></span>  
  
     <span data-ttu-id="5b8de-133">\<*パスのサンプル*\>AdminWMIEnlist OrchestrationCSharpbinDebug</span><span class="sxs-lookup"><span data-stu-id="5b8de-133">\<*Samples Path*\>AdminWMIEnlist OrchestrationCSharpbinDebug</span></span>  
  
2.  <span data-ttu-id="5b8de-134">このサンプルの VBScript バージョンと Visual C# バージョンのどちらを実行するかに応じて、cscript プログラムを使用して EnlistOrch.vbs を実行するか、ファイル EnlistOrc.exe を実行します。</span><span class="sxs-lookup"><span data-stu-id="5b8de-134">Either run the file EnlistOrch.vbs using the cscript program, or run the file EnlistOrc.exe, depending on whether you are planning to run the VBScript version or the Visual C# version of this sample, respectively.</span></span> <span data-ttu-id="5b8de-135">どちらの場合にも、以下のコマンド ライン引数を渡します。</span><span class="sxs-lookup"><span data-stu-id="5b8de-135">In any event, pass the following command-line arguments:</span></span>  
  
    -   <span data-ttu-id="5b8de-136">**\<** ***OrchestrationName* \>します。**</span><span class="sxs-lookup"><span data-stu-id="5b8de-136">**\<** ***OrchestrationName* \>.**</span></span> <span data-ttu-id="5b8de-137">参加させるオーケストレーションの名前。</span><span class="sxs-lookup"><span data-stu-id="5b8de-137">The name of the orchestration to be enlisted.</span></span>  
  
    -   <span data-ttu-id="5b8de-138">**\<** ***AssemblyName* \>します。**</span><span class="sxs-lookup"><span data-stu-id="5b8de-138">**\<** ***AssemblyName* \>.**</span></span> <span data-ttu-id="5b8de-139">オーケストレーションが展開されているアセンブリの名前。</span><span class="sxs-lookup"><span data-stu-id="5b8de-139">The name of the assembly in which the orchestration was deployed.</span></span> <span data-ttu-id="5b8de-140">アセンブリ名に空白が含まれている場合は、名前を引用符で囲みます。</span><span class="sxs-lookup"><span data-stu-id="5b8de-140">If the assembly name contains spaces, enclose the name in quotes.</span></span>  
  
         <span data-ttu-id="5b8de-141">例: (VBScript)。</span><span class="sxs-lookup"><span data-stu-id="5b8de-141">For example: (VBScript):</span></span>  
  
        ```  
        cscript EnlistOrch.vbs MyBusinessOrchestration "My Business Assembly"  
        ```  
  
         <span data-ttu-id="5b8de-142">または (Visual C#):</span><span class="sxs-lookup"><span data-stu-id="5b8de-142">-OR- (Visual C#):</span></span>  
  
        ```  
        EnlistOrc MyBusinessOrchestration "My Business Assembly"  
        ```  
  
## <a name="comments"></a><span data-ttu-id="5b8de-143">コメント</span><span class="sxs-lookup"><span data-stu-id="5b8de-143">Comments</span></span>  
 <span data-ttu-id="5b8de-144">すべてのタスクで実行できる、 [!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)] # を使用して Visual C にアクセスして、Windows WMI オブジェクト モデルにアクセスするスクリプトを使用して、管理コンソールを実行することも、 **System.Management**提供されているオブジェクト.NET framework です。</span><span class="sxs-lookup"><span data-stu-id="5b8de-144">All tasks that you can perform in the [!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)] Administration console can also be performed by using script that accesses the Windows WMI object model and by using Visual C# that accesses the **System.Management** objects provided by the .NET Framework.</span></span>  
  
 <span data-ttu-id="5b8de-145">スクリプト ファイル EnlistOrch.vbs および Visual C# ソース ファイル EnlistOrc.cs には、実行する操作について説明する詳細なコメントが含まれています。</span><span class="sxs-lookup"><span data-stu-id="5b8de-145">The script file EnlistOrch.vbs and the Visual C# source file EnlistOrc.cs contain detailed comments with further explanation about the operations that they perform.</span></span> <span data-ttu-id="5b8de-146">詳細については、Windows Management Instrumentation を参照してください。 [ http://go.microsoft.com/fwlink/?LinkId=21102](http://go.microsoft.com/fwlink/?LinkId=21102)します。</span><span class="sxs-lookup"><span data-stu-id="5b8de-146">For more information, see Windows Management Instrumentation at [http://go.microsoft.com/fwlink/?LinkId=21102](http://go.microsoft.com/fwlink/?LinkId=21102).</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="5b8de-147">参照</span><span class="sxs-lookup"><span data-stu-id="5b8de-147">See Also</span></span>  
 [<span data-ttu-id="5b8de-148">Admin-WMI (BizTalk Server Samples フォルダー)</span><span class="sxs-lookup"><span data-stu-id="5b8de-148">Admin-WMI (BizTalk Server Samples Folder)</span></span>](../core/admin-wmi-biztalk-server-samples-folder.md)