---
title: 列挙の受信場所 (BizTalk Server サンプル) |Microsoft Docs
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
ms.openlocfilehash: 7941cffb7e796c02b84c2dbd686fa20edbe9c8df
ms.sourcegitcommit: d27732e569b0897361dfaebca8352aa97bb7efe1
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 05/10/2019
ms.locfileid: "65530764"
---
# <a name="enumerate-receive-locations-biztalk-server-sample"></a><span data-ttu-id="6d56a-102">列挙の受信場所 (BizTalk Server サンプル)</span><span class="sxs-lookup"><span data-stu-id="6d56a-102">Enumerate Receive Locations (BizTalk Server Sample)</span></span>
<span data-ttu-id="6d56a-103">受信場所の列挙サンプルでは、いずれかに関する詳細を取得または以上の受信場所。</span><span class="sxs-lookup"><span data-stu-id="6d56a-103">The Enumerate Receive Locations sample demonstrates how to retrieve details about one or more receive locations.</span></span>  
  
> [!WARNING]
>  <span data-ttu-id="6d56a-104">展開スクリプトは、展開後に不要になった場合は、削除する必要があります。</span><span class="sxs-lookup"><span data-stu-id="6d56a-104">Deployment scripts should be removed after deployment if not needed.</span></span> <span data-ttu-id="6d56a-105">保持する必要のある管理スクリプトおよび他のスクリプトは、ACL によってセキュリティで保護し、厳重に監視する必要があります。</span><span class="sxs-lookup"><span data-stu-id="6d56a-105">Administration scripts and other scripts that must remain should be secured by ACL’s and closely monitored.</span></span>  
  
## <a name="what-this-sample-does"></a><span data-ttu-id="6d56a-106">このサンプルの処理</span><span class="sxs-lookup"><span data-stu-id="6d56a-106">What This Sample Does</span></span>  
 <span data-ttu-id="6d56a-107">このサンプルは、Windows WMI オブジェクト モデルにアクセスする Visual Basic Scripting Edition (VBScript) バージョンと Visual c# バージョンにアクセスする、 **System.Management** .NET Framework で提供されているオブジェクト。</span><span class="sxs-lookup"><span data-stu-id="6d56a-107">This sample includes a Visual Basic Scripting Edition (VBScript) version that accesses the Windows WMI object model, and a Visual C# version that accesses the **System.Management** objects provided by the .NET Framework.</span></span> <span data-ttu-id="6d56a-108">これらのバージョンのどちらも最終的には、次の操作を実行する BizTalk Server WMI プロバイダーにアクセスします。</span><span class="sxs-lookup"><span data-stu-id="6d56a-108">Both of these versions ultimately access the BizTalk Server WMI provider to perform the following operations:</span></span>  
  
-   <span data-ttu-id="6d56a-109">一連のクエリが構成されている受信場所または特定の受信場所、名前を指定します。</span><span class="sxs-lookup"><span data-stu-id="6d56a-109">Query for the set of configured receive locations or for a specific receive location, given its name.</span></span>  
  
-   <span data-ttu-id="6d56a-110">取得し、それぞれの詳細を表示の目的の場所を受信します。</span><span class="sxs-lookup"><span data-stu-id="6d56a-110">Retrieve and display details about each receive location of interest.</span></span>  
  
-   <span data-ttu-id="6d56a-111">意味のある情報がユーザーに返されるようにエラーを処理します。</span><span class="sxs-lookup"><span data-stu-id="6d56a-111">Handle any errors such that meaningful information is returned to the user.</span></span>  
  
## <a name="where-to-find-this-sample"></a><span data-ttu-id="6d56a-112">このサンプルの場所</span><span class="sxs-lookup"><span data-stu-id="6d56a-112">Where to Find This Sample</span></span>  
 <span data-ttu-id="6d56a-113">サンプルは、次の SDK の場所に配置されます。</span><span class="sxs-lookup"><span data-stu-id="6d56a-113">The samples are located in the following SDK locations:</span></span>  
  
- <span data-ttu-id="6d56a-114">VBScript バージョン:\<*パスのサンプル*\>\Admin\WMI\Enumerate Locations\VBScript\ の受信</span><span class="sxs-lookup"><span data-stu-id="6d56a-114">VBScript version: \<*Samples Path*\>\Admin\WMI\Enumerate Receive Locations\VBScript\\</span></span>  
  
- <span data-ttu-id="6d56a-115">VisualC#バージョン。\<*パスのサンプル*\>\Admin\WMI\Enumerate Locations\CSharp\ の受信</span><span class="sxs-lookup"><span data-stu-id="6d56a-115">Visual C# version: \<*Samples Path*\>\Admin\WMI\Enumerate Receive Locations\CSharp\\</span></span>  
  
  <span data-ttu-id="6d56a-116">次の表は、このサンプルのファイルとその目的を示しています。</span><span class="sxs-lookup"><span data-stu-id="6d56a-116">The following table shows the files in this sample and describes their purpose.</span></span>  
  
|<span data-ttu-id="6d56a-117">ファイル</span><span class="sxs-lookup"><span data-stu-id="6d56a-117">File(s)</span></span>|<span data-ttu-id="6d56a-118">説明</span><span class="sxs-lookup"><span data-stu-id="6d56a-118">Description</span></span>|  
|---------------|-----------------|  
|<span data-ttu-id="6d56a-119">\VBScript フォルダー。</span><span class="sxs-lookup"><span data-stu-id="6d56a-119">In the \VBScript folder:</span></span><br /><br /> <span data-ttu-id="6d56a-120">EnumRecLocs.vbs</span><span class="sxs-lookup"><span data-stu-id="6d56a-120">EnumRecLocs.vbs</span></span>|<span data-ttu-id="6d56a-121">受信場所を構成済みのすべての詳細を取得する VBScript ファイル。</span><span class="sxs-lookup"><span data-stu-id="6d56a-121">VBScript file that retrieves details about all configured receive locations.</span></span>|  
|<span data-ttu-id="6d56a-122">\CSharp フォルダー。</span><span class="sxs-lookup"><span data-stu-id="6d56a-122">In the \CSharp folder:</span></span><br /><br /> <span data-ttu-id="6d56a-123">App.ico, AssemblyInfo.cs, BTSampleEnumerateRLs.csproj, BTSampleEnumerateRLs.sln, EnumRLs.cs</span><span class="sxs-lookup"><span data-stu-id="6d56a-123">App.ico, AssemblyInfo.cs, BTSampleEnumerateRLs.csproj, BTSampleEnumerateRLs.sln, EnumRLs.cs</span></span>|<span data-ttu-id="6d56a-124">プロジェクト、ソリューション、および Visual c# コマンド ラインを取得するアプリケーションの詳細については、構成済みのすべてを構築するためのソース ファイルは、受信場所、または特定の受信場所。</span><span class="sxs-lookup"><span data-stu-id="6d56a-124">Project, solution, and source files for building a Visual C# command-line application that retrieves details about all configured receive locations, or about a specific receive location.</span></span>|  
  
## <a name="building-and-initializing-this-sample"></a><span data-ttu-id="6d56a-125">このサンプルのビルドと初期化</span><span class="sxs-lookup"><span data-stu-id="6d56a-125">Building and Initializing This Sample</span></span>  
 <span data-ttu-id="6d56a-126">受信場所の列挙サンプルの VBScript バージョンは、ビルドまたは初期化する必要はありませんは、1 つ Visual Basic スクリプト ファイルで構成されます。</span><span class="sxs-lookup"><span data-stu-id="6d56a-126">The VBScript version of the Enumerate Receive Locations sample consists of a single Visual Basic script file that you do not need to build or initialize.</span></span>  
  
#### <a name="to-build-the-visual-c-version-of-the-enumerate-receive-locations-sample"></a><span data-ttu-id="6d56a-127">受信場所の列挙サンプルの Visual c# バージョンをビルドするには</span><span class="sxs-lookup"><span data-stu-id="6d56a-127">To build the Visual C# version of the Enumerate Receive Locations sample</span></span>  
  
1. <span data-ttu-id="6d56a-128">[!INCLUDE[btsVStudioNoVersion](../includes/btsvstudionoversion-md.md)]、ソリューション ファイル BTSampleEnumerateRLs.sln を開きます。</span><span class="sxs-lookup"><span data-stu-id="6d56a-128">In [!INCLUDE[btsVStudioNoVersion](../includes/btsvstudionoversion-md.md)], open the solution file BTSampleEnumerateRLs.sln.</span></span>  
  
2. <span data-ttu-id="6d56a-129">**ビルド** メニューのをクリックして**ソリューションのビルド**します。</span><span class="sxs-lookup"><span data-stu-id="6d56a-129">In the **Build** menu, click **Build Solution**.</span></span>  
  
## <a name="running-this-sample"></a><span data-ttu-id="6d56a-130">このサンプルの実行</span><span class="sxs-lookup"><span data-stu-id="6d56a-130">Running This Sample</span></span>  
  
#### <a name="to-run-the-enumerate-receive-locations-sample"></a><span data-ttu-id="6d56a-131">受信場所の列挙サンプルを実行するには</span><span class="sxs-lookup"><span data-stu-id="6d56a-131">To run the Enumerate Receive Locations sample</span></span>  
  
1.  <span data-ttu-id="6d56a-132">コマンド ウィンドウでは、それぞれの VBScript バージョンと、このサンプルの Visual c# バージョンを実行することかどうかに応じて、次のフォルダーのいずれかに移動します。</span><span class="sxs-lookup"><span data-stu-id="6d56a-132">In a command window, navigate to one of the following folders, depending on whether you are going to run the VBScript version or the Visual C# version of this sample, respectively:</span></span>  
  
     <span data-ttu-id="6d56a-133">\<*パスのサンプル*\>\Admin\WMI\Enumerate Locations\VBScript\ の受信</span><span class="sxs-lookup"><span data-stu-id="6d56a-133">\<*Samples Path*\>\Admin\WMI\Enumerate Receive Locations\VBScript\\</span></span>  
  
     <span data-ttu-id="6d56a-134">\<*パスのサンプル*\>\Admin\WMI\Enumerate Locations\CSharp\bin\Debug\ の受信</span><span class="sxs-lookup"><span data-stu-id="6d56a-134">\<*Samples Path*\>\Admin\WMI\Enumerate Receive Locations\CSharp\bin\Debug\\</span></span>  
  
2.  <span data-ttu-id="6d56a-135">EnumRecLocs.vbs cscript プログラムを使用してファイルを実行するか、それぞれの VBScript バージョンと、このサンプルの Visual c# バージョンを実行することかどうかに応じて EnumRl.exe、ファイルを実行します。</span><span class="sxs-lookup"><span data-stu-id="6d56a-135">Either run the file EnumRecLocs.vbs using the cscript program, or run the file EnumRl.exe, depending on whether you are going to run the VBScript version or the Visual C# version of this sample, respectively.</span></span> <span data-ttu-id="6d56a-136">Visual c# のバージョンには、次の 2 つのコマンドライン引数のいずれかを渡します。</span><span class="sxs-lookup"><span data-stu-id="6d56a-136">For the Visual C# version, pass one of the following two command-line arguments:</span></span>  
  
    -   <span data-ttu-id="6d56a-137">**\<ReceiveLocationName\>.**</span><span class="sxs-lookup"><span data-stu-id="6d56a-137">**\<ReceiveLocationName\>.**</span></span> <span data-ttu-id="6d56a-138">詳細が表示されます、受信場所の名前。</span><span class="sxs-lookup"><span data-stu-id="6d56a-138">The name of the receive location for which details will be displayed.</span></span> <span data-ttu-id="6d56a-139">受信場所の名前にスペースが含まれている場合は、名前を引用符で囲みます。</span><span class="sxs-lookup"><span data-stu-id="6d56a-139">If the receive location name contains spaces, enclose the name in quotes.</span></span>  
  
    -   <span data-ttu-id="6d56a-140">**/?.**</span><span class="sxs-lookup"><span data-stu-id="6d56a-140">**/?.**</span></span> <span data-ttu-id="6d56a-141">ヘルプを表示します。</span><span class="sxs-lookup"><span data-stu-id="6d56a-141">Displays help.</span></span>  
  
         <span data-ttu-id="6d56a-142">例 (VBScript)。</span><span class="sxs-lookup"><span data-stu-id="6d56a-142">For example (VBScript):</span></span>  
  
        ```  
        cscript EnumRecLocs.vbs  
        ```  
  
         <span data-ttu-id="6d56a-143">-または-(Visual c#)。</span><span class="sxs-lookup"><span data-stu-id="6d56a-143">-OR- (Visual C#):</span></span>  
  
        ```  
        EnumRl "My Receive Location #3"  
        ```  
  
         <span data-ttu-id="6d56a-144">-または-(Visual c#)。</span><span class="sxs-lookup"><span data-stu-id="6d56a-144">-OR- (Visual C#):</span></span>  
  
        ```  
        EnumRl /?  
        ```  
  
    > [!NOTE]
    >  <span data-ttu-id="6d56a-145">このサンプルの VBScript バージョンは、任意のコマンド ライン パラメーターを受け入れませんあり、したがってのみを取得できると、表示の詳細については、構成済みのすべての受信場所。</span><span class="sxs-lookup"><span data-stu-id="6d56a-145">The VBScript version of this sample does not accept any command-line parameters, and therefore is only capable of retrieving and displaying details about all configured receive locations.</span></span>  
  
## <a name="comments"></a><span data-ttu-id="6d56a-146">コメント</span><span class="sxs-lookup"><span data-stu-id="6d56a-146">Comments</span></span>  
 <span data-ttu-id="6d56a-147">すべてのタスクで実行できる、[!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)]ビジュアルを使用して、Windows WMI オブジェクト モデルにアクセスするスクリプトを使用して、管理コンソールを実行することもC#にアクセスする、 **System.Management**オブジェクト.NET Framework によって提供されます。</span><span class="sxs-lookup"><span data-stu-id="6d56a-147">All tasks that you can perform in the [!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)] Administration console can also be performed by using script that accesses the Windows WMI object model and by using Visual C# that accesses the **System.Management** objects provided by the .NET Framework.</span></span>  
  
 <span data-ttu-id="6d56a-148">スクリプト ファイル EnumRecLocs.vbs および Visual c# ソース ファイル EnumRLs.cs 詳細なコメントが実行する操作についての説明が含まれます。</span><span class="sxs-lookup"><span data-stu-id="6d56a-148">The script file EnumRecLocs.vbs and the Visual C# source file EnumRLs.cs contain detailed comments with further explanation about the operations that they perform.</span></span> <span data-ttu-id="6d56a-149">詳細については、Windows Management Instrumentation を参照してください。 [ http://go.microsoft.com/fwlink/?LinkId=21102](http://go.microsoft.com/fwlink/?LinkId=21102)します。</span><span class="sxs-lookup"><span data-stu-id="6d56a-149">For more information, see Windows Management Instrumentation at [http://go.microsoft.com/fwlink/?LinkId=21102](http://go.microsoft.com/fwlink/?LinkId=21102).</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="6d56a-150">参照</span><span class="sxs-lookup"><span data-stu-id="6d56a-150">See Also</span></span>  
 [<span data-ttu-id="6d56a-151">Admin-WMI (BizTalk Server Samples フォルダー)</span><span class="sxs-lookup"><span data-stu-id="6d56a-151">Admin-WMI (BizTalk Server Samples Folder)</span></span>](../core/admin-wmi-biztalk-server-samples-folder.md)