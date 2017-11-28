---
title: "ApplicationManager (BizTalk Server サンプル) |Microsoft ドキュメント"
ms.custom: 
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: 
ms.suite: 
ms.tgt_pltfrm: 
ms.topic: article
ms.assetid: 51ebe7a8-a0ca-4d2a-bf40-ec6421ba5a95
caps.latest.revision: "13"
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: e352eb3ffb5418d7d109b5c0f574689c67f969f4
ms.sourcegitcommit: cb908c540d8f1a692d01dc8f313e16cb4b4e696d
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 09/20/2017
---
# <a name="applicationmanager-biztalk-server-sample"></a><span data-ttu-id="dd234-102">ApplicationManager (BizTalk Server サンプル)</span><span class="sxs-lookup"><span data-stu-id="dd234-102">ApplicationManager (BizTalk Server Sample)</span></span>
<span data-ttu-id="dd234-103">ApplicationManager サンプルでは、管理オブジェクトを使用して BizTalk アプリケーションを開始または停止する方法を示します。</span><span class="sxs-lookup"><span data-stu-id="dd234-103">The ApplicationManager sample demonstrates how to start or stop a  BizTalk application by using the administration objects.</span></span>  
  
## <a name="prerequisites"></a><span data-ttu-id="dd234-104">前提条件</span><span class="sxs-lookup"><span data-stu-id="dd234-104">Prerequisites</span></span>  
  
-   <span data-ttu-id="dd234-105">このサンプルの管理オブジェクトを使用するには、[!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)] 管理者特権が必要です。</span><span class="sxs-lookup"><span data-stu-id="dd234-105">You must have [!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)] administrative privileges to use the administrative objects in this sample.</span></span>  
  
-   <span data-ttu-id="dd234-106">Windows PowerShell スクリプトを実行するには、Windows PowerShell 実行ポリシーが必要です。</span><span class="sxs-lookup"><span data-stu-id="dd234-106">The Windows PowerShell script requires the Windows PowerShell execution policy to allow script execution.</span></span> <span data-ttu-id="dd234-107">詳細については、次を参照してください。:[実行ポリシーの確認](http://go.microsoft.com/fwlink/?LinkId=128930)です。</span><span class="sxs-lookup"><span data-stu-id="dd234-107">For more information see: [Examining the Execution Policy](http://go.microsoft.com/fwlink/?LinkId=128930).</span></span>  
  
## <a name="what-this-sample-does"></a><span data-ttu-id="dd234-108">このサンプルの処理</span><span class="sxs-lookup"><span data-stu-id="dd234-108">What This Sample Does</span></span>  
 <span data-ttu-id="dd234-109">このサンプルを使用して、 **BtsCatalogExplorer**と**アプリケーション**クラス、 **Microsoft.BizTalk.ExplorerOM**を開始および停止、展開済みの名前空間 BizTalk アプリケーション。</span><span class="sxs-lookup"><span data-stu-id="dd234-109">This sample demonstrates using the **BtsCatalogExplorer** and **Application** classes from the **Microsoft.BizTalk.ExplorerOM** namespace to start and stop a deployed  BizTalk application.</span></span> <span data-ttu-id="dd234-110">サンプルは Microsoft [!INCLUDE[btsVCSharp](../includes/btsvcsharp-md.md)] で作成されています。</span><span class="sxs-lookup"><span data-stu-id="dd234-110">The sample is written in Microsoft [!INCLUDE[btsVCSharp](../includes/btsvcsharp-md.md)].</span></span> <span data-ttu-id="dd234-111">このトピックには、Windows PowerShell のスクリプト例も含まれています。</span><span class="sxs-lookup"><span data-stu-id="dd234-111">A Windows PowerShell example script is also included in this topic.</span></span> <span data-ttu-id="dd234-112">このサンプルは次の操作を示します。</span><span class="sxs-lookup"><span data-stu-id="dd234-112">The sample demonstrates the following operations:</span></span>  
  
-   <span data-ttu-id="dd234-113">使用して、BizTalk 管理データベースに接続する、 **BtsCatalogExplorer**クラスです。</span><span class="sxs-lookup"><span data-stu-id="dd234-113">Connecting to the BizTalk Management database by using the **BtsCatalogExplorer** class.</span></span>  
  
-   <span data-ttu-id="dd234-114">アプリケーション インスタンスを検索する**BtsCatalogExplorer**アプリケーション名に基づいています。</span><span class="sxs-lookup"><span data-stu-id="dd234-114">Finding an application instance from  **BtsCatalogExplorer** based on application name.</span></span>  
  
-   <span data-ttu-id="dd234-115">アプリケーションの開始コマンドまたは停止コマンドを実行する。</span><span class="sxs-lookup"><span data-stu-id="dd234-115">Submitting a start or stop command for the application.</span></span>  
  
## <a name="where-to-find-this-sample"></a><span data-ttu-id="dd234-116">このサンプルの場所</span><span class="sxs-lookup"><span data-stu-id="dd234-116">Where To Find This Sample</span></span>  
 <span data-ttu-id="dd234-117">このサンプルは、SDK がある次の場所にあります。</span><span class="sxs-lookup"><span data-stu-id="dd234-117">The sample is located in the following SDK location:</span></span>  
  
 <span data-ttu-id="dd234-118">\<*パスのサンプル*> \Admin\ExplorerOM\ApplicationManager</span><span class="sxs-lookup"><span data-stu-id="dd234-118">\<*Samples Path*>\Admin\ExplorerOM\ApplicationManager</span></span>  
  
 <span data-ttu-id="dd234-119">次の表は、このサンプルのファイルとその目的を示しています。</span><span class="sxs-lookup"><span data-stu-id="dd234-119">The following table shows the files in this sample and describes their purpose.</span></span>  
  
|<span data-ttu-id="dd234-120">ファイル</span><span class="sxs-lookup"><span data-stu-id="dd234-120">File(s)</span></span>|<span data-ttu-id="dd234-121">Description</span><span class="sxs-lookup"><span data-stu-id="dd234-121">Description</span></span>|  
|---------------|-----------------|  
|<span data-ttu-id="dd234-122">Program.cs</span><span class="sxs-lookup"><span data-stu-id="dd234-122">Program.cs</span></span>|<span data-ttu-id="dd234-123">このサンプルに示されている操作の [!INCLUDE[btsVCSharp](../includes/btsvcsharp-md.md)] ソース ファイル。</span><span class="sxs-lookup"><span data-stu-id="dd234-123">[!INCLUDE[btsVCSharp](../includes/btsvcsharp-md.md)] source file for operations demonstrated in this sample.</span></span>|  
|<span data-ttu-id="dd234-124">ApplicationManager.sln、ApplicationManager.csproj、ApplicationManager.suo</span><span class="sxs-lookup"><span data-stu-id="dd234-124">ApplicationManager.sln,ApplicationManager.csproj,ApplicationManager.suo</span></span>|<span data-ttu-id="dd234-125">このサンプルのソリューション ファイルとプロジェクト ファイル。</span><span class="sxs-lookup"><span data-stu-id="dd234-125">Solution and project files for the sample.</span></span>|  
  
## <a name="building-and-running-this-sample"></a><span data-ttu-id="dd234-126">このサンプルのビルドおよび実行</span><span class="sxs-lookup"><span data-stu-id="dd234-126">Building and Running This Sample</span></span>  
  
#### <a name="to-build-this-sample"></a><span data-ttu-id="dd234-127">このサンプルをビルドするには</span><span class="sxs-lookup"><span data-stu-id="dd234-127">To build this sample</span></span>  
  
1.  <span data-ttu-id="dd234-128">[!INCLUDE[btsVStudioNoVersion](../includes/btsvstudionoversion-md.md)] で、ソリューション ファイル ApplicationManager.sln を開きます。</span><span class="sxs-lookup"><span data-stu-id="dd234-128">In [!INCLUDE[btsVStudioNoVersion](../includes/btsvstudionoversion-md.md)], open the solution file ApplicationManager.sln.</span></span>  
  
2.  <span data-ttu-id="dd234-129">**[ビルド]** メニューの **[ソリューションのビルド]**をクリックします。</span><span class="sxs-lookup"><span data-stu-id="dd234-129">On the **Build** menu, click **Build Solution**.</span></span>  
  
#### <a name="to-run-this-sample"></a><span data-ttu-id="dd234-130">このサンプルを実行するには</span><span class="sxs-lookup"><span data-stu-id="dd234-130">To run this sample</span></span>  
  
1.  <span data-ttu-id="dd234-131">コマンド ウィンドウを開き、次のフォルダーに移動します。</span><span class="sxs-lookup"><span data-stu-id="dd234-131">Open a command window and navigate to the following folder:</span></span>  
  
     <span data-ttu-id="dd234-132">\<*パスのサンプル*> \Admin\ExplorerOM\ApplicationManager\bin\Debug</span><span class="sxs-lookup"><span data-stu-id="dd234-132">\<*Samples Path*>\Admin\ExplorerOM\ApplicationManager\bin\Debug</span></span>  
  
2.  <span data-ttu-id="dd234-133">次の 2 つのコマンドライン引数を順番どおりに指定して、ApplicationManager.exe ファイルを実行します。</span><span class="sxs-lookup"><span data-stu-id="dd234-133">Run the file ApplicationManager.exe providing the following two ordered command-line arguments:</span></span>  
  
    -   <span data-ttu-id="dd234-134">**\<開始 (&) #124 です。 停止 >**最初の引数は、展開されたアプリケーションで実行する操作。</span><span class="sxs-lookup"><span data-stu-id="dd234-134">**\<start&#124;stop>** First argument is the operation to be performed on the deployed application.</span></span>  
  
    -   <span data-ttu-id="dd234-135">**\<ApplicationName >** 2 番目の引数は、展開されたアプリケーションの名前。</span><span class="sxs-lookup"><span data-stu-id="dd234-135">**\<ApplicationName>** Second argument is the name of the deployed application.</span></span>  
  
     <span data-ttu-id="dd234-136">例:</span><span class="sxs-lookup"><span data-stu-id="dd234-136">For example:</span></span>  
  
    ```  
    ApplicationManager.exe stop MyBizTalkApp  
    ```  
  
     <span data-ttu-id="dd234-137">一部のコマンドライン パラメーターのみを指定してサンプルを実行すると、使用する構文が表示されます。</span><span class="sxs-lookup"><span data-stu-id="dd234-137">Running the sample with insufficient command-line parameters displays the usage syntax.</span></span> <span data-ttu-id="dd234-138">例:</span><span class="sxs-lookup"><span data-stu-id="dd234-138">For example:</span></span>  
  
    ```  
    Usage:  
  
    ApplicationManager <start|stop> <Application Name>  
  
     Where:  
      <Application Name> = The name of the application that needs to be changed  
  
    Example: ApplicationManager start Application1  
    ```  
  
## <a name="windows-powershell-script-example"></a><span data-ttu-id="dd234-139">Windows PowerShell スクリプトの例</span><span class="sxs-lookup"><span data-stu-id="dd234-139">Windows PowerShell Script Example</span></span>  
 <span data-ttu-id="dd234-140">次の Windows PowerShell スクリプト フラグメントは、の同じ機能を示すために使用できます、 **ExplorerOM**クラス。</span><span class="sxs-lookup"><span data-stu-id="dd234-140">The following Windows PowerShell script fragment can be used to demonstrate the same features of the **ExplorerOM** classes:</span></span>  
  
```  
#=== Make sure the ExplorerOM assembly is loaded ===#  
  
[void] [System.reflection.Assembly]::LoadWithPartialName("Microsoft.BizTalk.ExplorerOM")  
  
#=== Connect the BizTalk Management database ===#  
  
$Catalog = New-Object Microsoft.BizTalk.ExplorerOM.BtsCatalogExplorer  
$Catalog.ConnectionString = "SERVER=.;DATABASE=BizTalkMgmtDb;Integrated Security=SSPI"  
  
#=== Loop through applications in the catalog trying to find a name match ===#  
  
foreach($app in $Catalog.Applications)  
{  
    if ($($app.Name) -ieq $args[1])  
    {  
  
        #=== The first command-line argument should be "start" or "stop" ===#  
  
        if ($args[0] -ieq "start")  
        {  
            Write-Host `r`nIssuing start command to $app.Name...`r`n  
            $app.Start([Microsoft.BizTalk.ExplorerOM.ApplicationStartOption] "StartAll")  
            $Catalog.SaveChanges()  
        }  
  
        if ($args[0] -ieq "stop")  
        {  
            Write-Host `r`nIssuing stop command to $app.Name...`r`n  
            $app.Stop([Microsoft.BizTalk.ExplorerOM.ApplicationStopOption] "StopAll")  
            $Catalog.SaveChanges()  
        }  
  
    }  
}  
```  
  
 <span data-ttu-id="dd234-141">このスクリプトは、[!INCLUDE[btsVCSharp](../includes/btsvcsharp-md.md)] サンプルと同じコマンドライン引数を受け取ります。</span><span class="sxs-lookup"><span data-stu-id="dd234-141">The script expects the same command-line arguments as the [!INCLUDE[btsVCSharp](../includes/btsvcsharp-md.md)] sample.</span></span> <span data-ttu-id="dd234-142">Windows PowerShell スクリプトを実行して、展開されている BizTalk アプリケーションを開始する例を次に示します。</span><span class="sxs-lookup"><span data-stu-id="dd234-142">Here is an example of running the Windows PowerShell script to start a deployed BizTalk application:</span></span>  
  
```  
PS C:\> .\ApplicationManager.ps1 start MyBizTalkApp  
  
Issuing start command to MyBizTalkApp ...  
```  
  
## <a name="see-also"></a><span data-ttu-id="dd234-143">参照</span><span class="sxs-lookup"><span data-stu-id="dd234-143">See Also</span></span>  
 [<span data-ttu-id="dd234-144">Admin ExplorerOM (BizTalk Server Samples フォルダ)</span><span class="sxs-lookup"><span data-stu-id="dd234-144">Admin-ExplorerOM (BizTalk Server Samples Folder)</span></span>](../core/admin-explorerom-biztalk-server-samples-folder.md)