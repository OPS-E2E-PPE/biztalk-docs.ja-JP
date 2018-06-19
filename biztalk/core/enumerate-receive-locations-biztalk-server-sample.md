---
title: 列挙の受信場所 (BizTalk Server サンプル) |Microsoft ドキュメント
ms.custom: ''
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: ''
ms.suite: ''
ms.tgt_pltfrm: ''
ms.topic: article
helpviewer_keywords:
- receive locations, examples
- receive locations, enumerating
- examples, receive locations
ms.assetid: 27ff8ac6-7e8e-4dde-84d1-d21bf417ddd7
caps.latest.revision: 11
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: 82fcdc400395d7bbfd6de8f9bc0fca85114a25dc
ms.sourcegitcommit: 5abd0ed3f9e4858ffaaec5481bfa8878595e95f7
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 11/28/2017
ms.locfileid: "25969080"
---
# <a name="enumerate-receive-locations-biztalk-server-sample"></a><span data-ttu-id="9e446-102">列挙の受信場所 (BizTalk Server サンプル)</span><span class="sxs-lookup"><span data-stu-id="9e446-102">Enumerate Receive Locations (BizTalk Server Sample)</span></span>
<span data-ttu-id="9e446-103">受信場所の列挙サンプルでは、1 つ以上の受信場所に関する詳細情報を取得する方法を説明します。</span><span class="sxs-lookup"><span data-stu-id="9e446-103">The Enumerate Receive Locations sample demonstrates how to retrieve details about one or more receive locations.</span></span>  
  
> [!WARNING]
>  <span data-ttu-id="9e446-104">展開スクリプトは、展開後に不要になった場合は、削除する必要があります。</span><span class="sxs-lookup"><span data-stu-id="9e446-104">Deployment scripts should be removed after deployment if not needed.</span></span> <span data-ttu-id="9e446-105">保持する必要のある管理スクリプトおよび他のスクリプトは、ACL によってセキュリティで保護し、厳重に監視する必要があります。</span><span class="sxs-lookup"><span data-stu-id="9e446-105">Administration scripts and other scripts that must remain should be secured by ACL’s and closely monitored.</span></span>  
  
## <a name="what-this-sample-does"></a><span data-ttu-id="9e446-106">このサンプルの処理</span><span class="sxs-lookup"><span data-stu-id="9e446-106">What This Sample Does</span></span>  
 <span data-ttu-id="9e446-107">このサンプルには、Windows WMI オブジェクト モデルにアクセスする Visual Basic Scripting Edition (VBScript) バージョンとにアクセスする Visual c# バージョンが含まれています、 **System.Management** .NET Framework によって提供されるオブジェクト。</span><span class="sxs-lookup"><span data-stu-id="9e446-107">This sample includes a Visual Basic Scripting Edition (VBScript) version that accesses the Windows WMI object model, and a Visual C# version that accesses the **System.Management** objects provided by the .NET Framework.</span></span> <span data-ttu-id="9e446-108">いずれのバージョンも、最終的に BizTalk Server WMI プロバイダにアクセスして次の操作を実行します。</span><span class="sxs-lookup"><span data-stu-id="9e446-108">Both of these versions ultimately access the BizTalk Server WMI provider to perform the following operations:</span></span>  
  
-   <span data-ttu-id="9e446-109">名前を指定して、構成済みの受信場所のセット、または特定の受信場所をクエリします。</span><span class="sxs-lookup"><span data-stu-id="9e446-109">Query for the set of configured receive locations or for a specific receive location, given its name.</span></span>  
  
-   <span data-ttu-id="9e446-110">対象の各受信場所に関する詳細情報を取得および表示します。</span><span class="sxs-lookup"><span data-stu-id="9e446-110">Retrieve and display details about each receive location of interest.</span></span>  
  
-   <span data-ttu-id="9e446-111">意味のある情報がユーザーに返されるようにエラーを処理します。</span><span class="sxs-lookup"><span data-stu-id="9e446-111">Handle any errors such that meaningful information is returned to the user.</span></span>  
  
## <a name="where-to-find-this-sample"></a><span data-ttu-id="9e446-112">このサンプルの場所</span><span class="sxs-lookup"><span data-stu-id="9e446-112">Where to Find This Sample</span></span>  
 <span data-ttu-id="9e446-113">このサンプルは、次の SDK の場所にあります。</span><span class="sxs-lookup"><span data-stu-id="9e446-113">The samples are located in the following SDK locations:</span></span>  
  
-   <span data-ttu-id="9e446-114">VBScript バージョン: \<*サンプル パス*\>\Admin\WMI\Enumerate Receive Locations\VBScript\\</span><span class="sxs-lookup"><span data-stu-id="9e446-114">VBScript version: \<*Samples Path*\>\Admin\WMI\Enumerate Receive Locations\VBScript\\</span></span>  
  
-   <span data-ttu-id="9e446-115">Visual c# バージョン: \<*サンプル パス*\>\Admin\WMI\Enumerate Receive Locations\CSharp\\</span><span class="sxs-lookup"><span data-stu-id="9e446-115">Visual C# version: \<*Samples Path*\>\Admin\WMI\Enumerate Receive Locations\CSharp\\</span></span>  
  
 <span data-ttu-id="9e446-116">次の表は、このサンプルのファイルとその目的を示しています。</span><span class="sxs-lookup"><span data-stu-id="9e446-116">The following table shows the files in this sample and describes their purpose.</span></span>  
  
|<span data-ttu-id="9e446-117">ファイル</span><span class="sxs-lookup"><span data-stu-id="9e446-117">File(s)</span></span>|<span data-ttu-id="9e446-118">Description</span><span class="sxs-lookup"><span data-stu-id="9e446-118">Description</span></span>|  
|---------------|-----------------|  
|<span data-ttu-id="9e446-119">\VBScript フォルダー内のファイル : </span><span class="sxs-lookup"><span data-stu-id="9e446-119">In the \VBScript folder:</span></span><br /><br /> <span data-ttu-id="9e446-120">EnumRecLocs.vbs</span><span class="sxs-lookup"><span data-stu-id="9e446-120">EnumRecLocs.vbs</span></span>|<span data-ttu-id="9e446-121">構成済みのすべての受信場所についての詳細情報を取得する VBScript ファイル</span><span class="sxs-lookup"><span data-stu-id="9e446-121">VBScript file that retrieves details about all configured receive locations.</span></span>|  
|<span data-ttu-id="9e446-122">\CSharp フォルダー内のファイル : </span><span class="sxs-lookup"><span data-stu-id="9e446-122">In the \CSharp folder:</span></span><br /><br /> <span data-ttu-id="9e446-123">App.ico、AssemblyInfo.cs、BTSampleEnumerateRLs.csproj、BTSampleEnumerateRLs.sln、および EnumRLs.cs</span><span class="sxs-lookup"><span data-stu-id="9e446-123">App.ico, AssemblyInfo.cs, BTSampleEnumerateRLs.csproj, BTSampleEnumerateRLs.sln, EnumRLs.cs</span></span>|<span data-ttu-id="9e446-124">構成済みのすべての受信場所または特定の受信場所についての詳細情報を取得する Visual C# コマンド ライン アプリケーションを構築するためのプロジェクト、ソリューション、およびソース ファイル</span><span class="sxs-lookup"><span data-stu-id="9e446-124">Project, solution, and source files for building a Visual C# command-line application that retrieves details about all configured receive locations, or about a specific receive location.</span></span>|  
  
## <a name="building-and-initializing-this-sample"></a><span data-ttu-id="9e446-125">このサンプルのビルドと初期化</span><span class="sxs-lookup"><span data-stu-id="9e446-125">Building and Initializing This Sample</span></span>  
 <span data-ttu-id="9e446-126">受信場所の列挙サンプルの VBScript バージョンは、構築または初期化が不要な 1 つの Visual Basic スクリプト ファイルで構成されます。</span><span class="sxs-lookup"><span data-stu-id="9e446-126">The VBScript version of the Enumerate Receive Locations sample consists of a single Visual Basic script file that you do not need to build or initialize.</span></span>  
  
#### <a name="to-build-the-visual-c-version-of-the-enumerate-receive-locations-sample"></a><span data-ttu-id="9e446-127">受信場所の列挙サンプルの Visual C# バージョンを構築するには</span><span class="sxs-lookup"><span data-stu-id="9e446-127">To build the Visual C# version of the Enumerate Receive Locations sample</span></span>  
  
1.  <span data-ttu-id="9e446-128">[!INCLUDE[btsVStudioNoVersion](../includes/btsvstudionoversion-md.md)] で、ソリューション ファイル BTSampleEnumerateRLs.sln を開きます。</span><span class="sxs-lookup"><span data-stu-id="9e446-128">In [!INCLUDE[btsVStudioNoVersion](../includes/btsvstudionoversion-md.md)], open the solution file BTSampleEnumerateRLs.sln.</span></span>  
  
2.  <span data-ttu-id="9e446-129">**ビルド** メニューのをクリックして**ソリューションのビルド**です。</span><span class="sxs-lookup"><span data-stu-id="9e446-129">In the **Build** menu, click **Build Solution**.</span></span>  
  
## <a name="running-this-sample"></a><span data-ttu-id="9e446-130">このサンプルの実行</span><span class="sxs-lookup"><span data-stu-id="9e446-130">Running This Sample</span></span>  
  
#### <a name="to-run-the-enumerate-receive-locations-sample"></a><span data-ttu-id="9e446-131">受信場所の列挙サンプルを実行するには</span><span class="sxs-lookup"><span data-stu-id="9e446-131">To run the Enumerate Receive Locations sample</span></span>  
  
1.  <span data-ttu-id="9e446-132">コマンド ウィンドウで、このサンプルの VBScript バージョンと Visual C# バージョンのどちらを実行するかに応じて、次のフォルダのどちらかに移動します。</span><span class="sxs-lookup"><span data-stu-id="9e446-132">In a command window, navigate to one of the following folders, depending on whether you are going to run the VBScript version or the Visual C# version of this sample, respectively:</span></span>  
  
     <span data-ttu-id="9e446-133">\<*パスのサンプル*\>\Admin\WMI\Enumerate 受信 Locations\VBScript\\</span><span class="sxs-lookup"><span data-stu-id="9e446-133">\<*Samples Path*\>\Admin\WMI\Enumerate Receive Locations\VBScript\\</span></span>  
  
     <span data-ttu-id="9e446-134">\<*パスのサンプル*\>\Admin\WMI\Enumerate 受信 Locations\CSharp\bin\Debug\\</span><span class="sxs-lookup"><span data-stu-id="9e446-134">\<*Samples Path*\>\Admin\WMI\Enumerate Receive Locations\CSharp\bin\Debug\\</span></span>  
  
2.  <span data-ttu-id="9e446-135">このサンプルの VBScript バージョンと Visual C# バージョンのどちらを実行するかに応じて、EnumRecLocs.vbs (cscript プログラムを使用) または EnumRl.exe を実行します。</span><span class="sxs-lookup"><span data-stu-id="9e446-135">Either run the file EnumRecLocs.vbs using the cscript program, or run the file EnumRl.exe, depending on whether you are going to run the VBScript version or the Visual C# version of this sample, respectively.</span></span> <span data-ttu-id="9e446-136">Visual C# バージョンの場合は、次の 2 つのコマンド ライン引数の 1 つを渡します。</span><span class="sxs-lookup"><span data-stu-id="9e446-136">For the Visual C# version, pass one of the following two command-line arguments:</span></span>  
  
    -   <span data-ttu-id="9e446-137">**\<ReceiveLocationName\>です。**</span><span class="sxs-lookup"><span data-stu-id="9e446-137">**\<ReceiveLocationName\>.**</span></span> <span data-ttu-id="9e446-138">詳細情報を表示する受信場所の名前です。</span><span class="sxs-lookup"><span data-stu-id="9e446-138">The name of the receive location for which details will be displayed.</span></span> <span data-ttu-id="9e446-139">受信場所名に空白が含まれている場合は、名前を引用符で囲みます。</span><span class="sxs-lookup"><span data-stu-id="9e446-139">If the receive location name contains spaces, enclose the name in quotes.</span></span>  
  
    -   <span data-ttu-id="9e446-140">**/?.**</span><span class="sxs-lookup"><span data-stu-id="9e446-140">**/?.**</span></span> <span data-ttu-id="9e446-141">ヘルプを表示します。</span><span class="sxs-lookup"><span data-stu-id="9e446-141">Displays help.</span></span>  
  
         <span data-ttu-id="9e446-142">例 (VBScript):</span><span class="sxs-lookup"><span data-stu-id="9e446-142">For example (VBScript):</span></span>  
  
        ```  
        cscript EnumRecLocs.vbs  
        ```  
  
         <span data-ttu-id="9e446-143">または (Visual C#):</span><span class="sxs-lookup"><span data-stu-id="9e446-143">-OR- (Visual C#):</span></span>  
  
        ```  
        EnumRl "My Receive Location #3"  
        ```  
  
         <span data-ttu-id="9e446-144">または (Visual C#):</span><span class="sxs-lookup"><span data-stu-id="9e446-144">-OR- (Visual C#):</span></span>  
  
        ```  
        EnumRl /?  
        ```  
  
    > [!NOTE]
    >  <span data-ttu-id="9e446-145">このサンプルの VBScript バージョンでは、コマンド ライン パラメータを使用できないため、構成済みのすべての受信場所についての詳細情報を取得および表示することしかできません。</span><span class="sxs-lookup"><span data-stu-id="9e446-145">The VBScript version of this sample does not accept any command-line parameters, and therefore is only capable of retrieving and displaying details about all configured receive locations.</span></span>  
  
## <a name="comments"></a><span data-ttu-id="9e446-146">コメント</span><span class="sxs-lookup"><span data-stu-id="9e446-146">Comments</span></span>  
 <span data-ttu-id="9e446-147">実行できるすべてのタスク、 [!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)] # を使用して Visual C にアクセスして、Windows WMI オブジェクト モデルにアクセスするスクリプトを使用して、管理コンソールを実行することも、 **System.Management**提供されるオブジェクト.NET framework。</span><span class="sxs-lookup"><span data-stu-id="9e446-147">All tasks that you can perform in the [!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)] Administration console can also be performed by using script that accesses the Windows WMI object model and by using Visual C# that accesses the **System.Management** objects provided by the .NET Framework.</span></span>  
  
 <span data-ttu-id="9e446-148">スクリプト ファイル EnumRecLocs.vbs および Visual C# ソース ファイル EnumRLs.cs には、実行する操作について説明する詳細なコメントが含まれています。</span><span class="sxs-lookup"><span data-stu-id="9e446-148">The script file EnumRecLocs.vbs and the Visual C# source file EnumRLs.cs contain detailed comments with further explanation about the operations that they perform.</span></span> <span data-ttu-id="9e446-149">詳細については、Windows Management Instrumentation」を参照してください。 [http://go.microsoft.com/fwlink/?LinkId=21102](http://go.microsoft.com/fwlink/?LinkId=21102)です。</span><span class="sxs-lookup"><span data-stu-id="9e446-149">For more information, see Windows Management Instrumentation at [http://go.microsoft.com/fwlink/?LinkId=21102](http://go.microsoft.com/fwlink/?LinkId=21102).</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="9e446-150">参照</span><span class="sxs-lookup"><span data-stu-id="9e446-150">See Also</span></span>  
 [<span data-ttu-id="9e446-151">Admin-WMI (BizTalk Server Samples フォルダー)</span><span class="sxs-lookup"><span data-stu-id="9e446-151">Admin-WMI (BizTalk Server Samples Folder)</span></span>](../core/admin-wmi-biztalk-server-samples-folder.md)