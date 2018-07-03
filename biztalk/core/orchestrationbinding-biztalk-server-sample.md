---
title: OrchestrationBinding (BizTalk Server サンプル) |Microsoft Docs
ms.custom: ''
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: ''
ms.suite: ''
ms.tgt_pltfrm: ''
ms.topic: article
ms.assetid: ea14c0db-ea83-4bf9-b417-f877b3cb1bf9
caps.latest.revision: 10
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: 4eaa3d227a2f02990befeafbd9ead5313fed3c7f
ms.sourcegitcommit: 266308ec5c6a9d8d80ff298ee6051b4843c5d626
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 06/27/2018
ms.locfileid: "37009835"
---
# <a name="orchestrationbinding-biztalk-server-sample"></a><span data-ttu-id="3e663-102">OrchestrationBinding (BizTalk Server サンプル)</span><span class="sxs-lookup"><span data-stu-id="3e663-102">OrchestrationBinding (BizTalk Server Sample)</span></span>
<span data-ttu-id="3e663-103">オーケストレーションのバインドのサンプルでは、 [Microsoft.BizTalk.ExplorerOM](http://msdn.microsoft.com/library/microsoft.biztalk.explorerom.aspx) 管理オブジェクトを使用してオーケストレーションを構成および管理します。</span><span class="sxs-lookup"><span data-stu-id="3e663-103">The Orchestration Binding sample demonstrates using the [Microsoft.BizTalk.ExplorerOM](http://msdn.microsoft.com/library/microsoft.biztalk.explorerom.aspx) administrative objects to configure and manage orchestrations.</span></span>  

## <a name="prerequisites"></a><span data-ttu-id="3e663-104">前提条件</span><span class="sxs-lookup"><span data-stu-id="3e663-104">Prerequisites</span></span>  

- <span data-ttu-id="3e663-105">このサンプルにある setup.bat を実行して HelloWorld サンプルを配置することが必要です、 \<*サンプル パス*\>\Orchestrations\HelloWorld ディレクトリ。</span><span class="sxs-lookup"><span data-stu-id="3e663-105">This sample requires that the HelloWorld sample be deployed by running setup.bat located in the \<*Samples Path*\>\Orchestrations\HelloWorld directory.</span></span>  

- <span data-ttu-id="3e663-106">このサンプルの管理オブジェクトを使用するには、[!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)] 管理者特権が必要です。</span><span class="sxs-lookup"><span data-stu-id="3e663-106">You must have [!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)] administrative privileges to use the administrative objects in this sample.</span></span>  

- <span data-ttu-id="3e663-107">Windows PowerShell スクリプトの例を実行するには、Windows PowerShell 実行ポリシーが必要です。</span><span class="sxs-lookup"><span data-stu-id="3e663-107">The Windows PowerShell script example requires the Windows PowerShell execution policy to allow script execution.</span></span> <span data-ttu-id="3e663-108">詳細については、「 [実行ポリシーの確認](http://go.microsoft.com/fwlink/?LinkId=128930)」を参照してください。</span><span class="sxs-lookup"><span data-stu-id="3e663-108">For more information see [Examining the Execution Policy](http://go.microsoft.com/fwlink/?LinkId=128930).</span></span>  

## <a name="what-this-sample-does"></a><span data-ttu-id="3e663-109">このサンプルの処理</span><span class="sxs-lookup"><span data-stu-id="3e663-109">What This Sample Does</span></span>  
 <span data-ttu-id="3e663-110">このサンプルでは、 **Microsoft.BizTalk.ExplorerOM** 名前空間の管理オブジェクトを使用してオーケストレーションを管理する方法を示します。</span><span class="sxs-lookup"><span data-stu-id="3e663-110">This sample demonstrates using the administrative objects in the **Microsoft.BizTalk.ExplorerOM** namespace to manage orchestrations.</span></span> <span data-ttu-id="3e663-111">このサンプルでは、 **ExplorerOM** オブジェクトを使用して次の操作を実行する方法を示します。</span><span class="sxs-lookup"><span data-stu-id="3e663-111">The sample demonstrates the following operations using the **ExplorerOM** objects:</span></span>  

-   <span data-ttu-id="3e663-112">[Microsoft.BizTalk.ExplorerOM.BtsCatalogExplorer](http://msdn.microsoft.com/library/microsoft.biztalk.explorerom.btscatalogexplorer.aspx) クラスを使用して BizTalk 管理データベースに接続する。</span><span class="sxs-lookup"><span data-stu-id="3e663-112">Connecting to the BizTalk Management database by using the[Microsoft.BizTalk.ExplorerOM.BtsCatalogExplorer](http://msdn.microsoft.com/library/microsoft.biztalk.explorerom.btscatalogexplorer.aspx) class.</span></span>  

-   <span data-ttu-id="3e663-113">**Microsoft.BizTalk.ExplorerOM.BtsOrchestration** クラスの [Status](http://msdn.microsoft.com/library/Microsoft.BizTalk.ExplorerOM.BtsOrchestration.aspx) プロパティを変更してオーケストレーションを停止および開始する。</span><span class="sxs-lookup"><span data-stu-id="3e663-113">Stopping and starting orchestrations by changing the **Status** property of the [Microsoft.BizTalk.ExplorerOM.BtsOrchestration](http://msdn.microsoft.com/library/Microsoft.BizTalk.ExplorerOM.BtsOrchestration.aspx) class.</span></span>  

-   <span data-ttu-id="3e663-114">**Microsoft.BizTalk.ExplorerOM.BtsOrchestration** クラスの [Status](http://msdn.microsoft.com/library/Microsoft.BizTalk.ExplorerOM.BtsOrchestration.aspx) プロパティを変更してオーケストレーションを参加および参加解除する。</span><span class="sxs-lookup"><span data-stu-id="3e663-114">Enlisting and unenlisting orchestrations by changing the **Status** property of the [Microsoft.BizTalk.ExplorerOM.BtsOrchestration](http://msdn.microsoft.com/library/Microsoft.BizTalk.ExplorerOM.BtsOrchestration.aspx) class.</span></span>  

-   <span data-ttu-id="3e663-115">**Microsoft.BizTalk.ExplorerOM.BtsOrchestration** クラスの [Status](http://msdn.microsoft.com/library/Microsoft.BizTalk.ExplorerOM.BtsOrchestration.aspx) プロパティを変更してオーケストレーションをバインドおよびバインド解除する。</span><span class="sxs-lookup"><span data-stu-id="3e663-115">Binding and unbinding orchestrations by using the **Ports** collection on the [Microsoft.BizTalk.ExplorerOM.BtsOrchestration](http://msdn.microsoft.com/library/Microsoft.BizTalk.ExplorerOM.BtsOrchestration.aspx) class.</span></span>  

## <a name="where-to-find-this-sample"></a><span data-ttu-id="3e663-116">このサンプルの場所</span><span class="sxs-lookup"><span data-stu-id="3e663-116">Where To Find This Sample</span></span>  
 <span data-ttu-id="3e663-117">このサンプルは、SDK がある次の場所にあります。</span><span class="sxs-lookup"><span data-stu-id="3e663-117">The sample is located in the following SDK location:</span></span>  

 <span data-ttu-id="3e663-118">\<*パスのサンプル*\>\Admin\ExplorerOM\OrchestrationBinding</span><span class="sxs-lookup"><span data-stu-id="3e663-118">\<*Samples Path*\>\Admin\ExplorerOM\OrchestrationBinding</span></span>  

 <span data-ttu-id="3e663-119">次の表は、このサンプルのファイルとその目的を示しています。</span><span class="sxs-lookup"><span data-stu-id="3e663-119">The following table shows the files in this sample and describes their purpose.</span></span>  


|                                     <span data-ttu-id="3e663-120">ファイル</span><span class="sxs-lookup"><span data-stu-id="3e663-120">File(s)</span></span>                                     |                                                 <span data-ttu-id="3e663-121">説明</span><span class="sxs-lookup"><span data-stu-id="3e663-121">Description</span></span>                                                  |
|---------------------------------------------------------------------------------|--------------------------------------------------------------------------------------------------------------|
|                             <span data-ttu-id="3e663-122">OrchestrationBinding.cs</span><span class="sxs-lookup"><span data-stu-id="3e663-122">OrchestrationBinding.cs</span></span>                             | <span data-ttu-id="3e663-123">このサンプルに示されている操作の [!INCLUDE[btsVCSharp](../includes/btsvcsharp-md.md)] ソース ファイル。</span><span class="sxs-lookup"><span data-stu-id="3e663-123">[!INCLUDE[btsVCSharp](../includes/btsvcsharp-md.md)] source file for operations demonstrated in this sample.</span></span> |
| <span data-ttu-id="3e663-124">OrchestrationBinding.sln、OrchestrationBinding.csproj、OrchestrationBinding.suo</span><span class="sxs-lookup"><span data-stu-id="3e663-124">OrchestrationBinding.sln, OrchestrationBinding.csproj, OrchestrationBinding.suo</span></span> |                                  <span data-ttu-id="3e663-125">このサンプルのソリューション ファイルとプロジェクト ファイル。</span><span class="sxs-lookup"><span data-stu-id="3e663-125">Solution and project files for the sample.</span></span>                                  |

## <a name="building-and-running-this-sample"></a><span data-ttu-id="3e663-126">このサンプルのビルドおよび実行</span><span class="sxs-lookup"><span data-stu-id="3e663-126">Building and Running This Sample</span></span>  

#### <a name="to-build-this-sample"></a><span data-ttu-id="3e663-127">このサンプルをビルドするには</span><span class="sxs-lookup"><span data-stu-id="3e663-127">To build this sample</span></span>  

1. <span data-ttu-id="3e663-128">HelloWorld サンプルのビルドおよび初期化の手順が完了していることを確認します。</span><span class="sxs-lookup"><span data-stu-id="3e663-128">Make sure you have completed the steps for building and initializing the HelloWorld sample.</span></span> <span data-ttu-id="3e663-129">これらの手順が記載[HelloWorld (BizTalk Server サンプル)](../core/helloworld-biztalk-server-sample.md)します。</span><span class="sxs-lookup"><span data-stu-id="3e663-129">Those steps are provided in [HelloWorld (BizTalk Server Sample)](../core/helloworld-biztalk-server-sample.md).</span></span>  

2. <span data-ttu-id="3e663-130">[!INCLUDE[btsVStudioNoVersion](../includes/btsvstudionoversion-md.md)] で、ソリューション ファイル OrchestrationBinding.sln を開きます。</span><span class="sxs-lookup"><span data-stu-id="3e663-130">In [!INCLUDE[btsVStudioNoVersion](../includes/btsvstudionoversion-md.md)], open the solution file OrchestrationBinding.sln.</span></span>  

3. <span data-ttu-id="3e663-131">**[ビルド]** メニューの **[ソリューションのビルド]** をクリックします。</span><span class="sxs-lookup"><span data-stu-id="3e663-131">On the **Build** menu, click **Build Solution**.</span></span>  

#### <a name="to-run-this-sample"></a><span data-ttu-id="3e663-132">このサンプルを実行するには</span><span class="sxs-lookup"><span data-stu-id="3e663-132">To run this sample</span></span>  

1.  <span data-ttu-id="3e663-133">コマンド ウィンドウを開き、次のフォルダーに移動します。</span><span class="sxs-lookup"><span data-stu-id="3e663-133">Open a command window and navigate to the following folder:</span></span>  

     <span data-ttu-id="3e663-134">\<*パスのサンプル*\>\Admin\ExplorerOM\OrchestrationBinding\bin\Debug</span><span class="sxs-lookup"><span data-stu-id="3e663-134">\<*Samples Path*\>\Admin\ExplorerOM\OrchestrationBinding\bin\Debug</span></span>  

2.  <span data-ttu-id="3e663-135">OrchestrationBinding.exe を実行して、サンプルの指示に従います。</span><span class="sxs-lookup"><span data-stu-id="3e663-135">Run the file OrchestrationBinding.exe and follow the directions provided by the sample.</span></span>  

## <a name="windows-powershell-script-example"></a><span data-ttu-id="3e663-136">Windows PowerShell スクリプトの例</span><span class="sxs-lookup"><span data-stu-id="3e663-136">Windows PowerShell Script Example</span></span>  
 <span data-ttu-id="3e663-137">次の Windows PowerShell スクリプトを使用すると、 **ExplorerOM** クラスの同じ機能を実行できます。</span><span class="sxs-lookup"><span data-stu-id="3e663-137">The following Windows PowerShell script can be used to demonstrate the same features of the **ExplorerOM** classes.</span></span>  

```  

Function RefreshPrompt($oldstatus,$newstatus)  
{  
  Write-Host Orchestration Status should now be `"$oldstatus`"  
  Write-Host Press F5 in the Orchestrations view of BizTalk Server Administration Console to refresh and verify   

  if ($newstatus)  
  {  
    Write-Host Pressing `<Enter`> now will $newstatus the orchestration using ExplorerOM`.`.`.  
    Read-Host  
    Write-Host "=== Please wait, attempting to $newstatus the orchestration... ===`r`n"  
  }  
  else  
  {  
    write-host `r`n  
  }  
}  

#===================#  
#=== Main Script ===#  
#===================#  

#=== Make sure the ExplorerOM assembly is loaded ===#  

[void] [System.reflection.Assembly]::LoadWithPartialName("Microsoft.BizTalk.ExplorerOM")  

#=== Connect to the BizTalk Management database ===#  

$Catalog = New-Object Microsoft.BizTalk.ExplorerOM.BtsCatalogExplorer  
$Catalog.ConnectionString = "SERVER=.;DATABASE=BizTalkMgmtDb;Integrated Security=SSPI"  

#=== This sample expects the HelloWorld sample orchestration to be using the ===#  
#=== default name "Biztalk Application 1"                                    ===#  

$HelloWorldApp = $Catalog.Applications["Biztalk Application 1"]  
$orch = $HelloWorldApp.orchestrations["Microsoft.Samples.BizTalk.HelloWorld.HelloSchedule"]  

#==================================================================#  
#=== Register a trap handler to discard changes on exceptions   ===#  
#=== Execution will continue in the event we need to re-enlist, ===#  
#=== re-bind, or restart the orchestration.                     ===#  
#==================================================================#  

$ErrorActionPreference="silentlycontinue"  
trap { "Exception encountered:`r`n"; $_; "`r`nDiscarding Changes and continuing execution...`r`n";$Catalog.DiscardChanges();}  

write-host `r`nMake sure the "HelloWorld" sample application is deployed and running.  
write-host By default it will be listed in the BizTalk Server Administration Console  
write-host with the application name: `"BizTalk.Application.1`"`r`n  

#==========================================================#  
#=== Change orchestration state from Started to stopped ===#  
#==========================================================#  

RefreshPrompt Started stop  
$orch.Status = [Microsoft.BizTalk.ExplorerOM.OrchestrationStatus] "Enlisted"  
$Catalog.SaveChanges()  

#=============================================================#  
#=== Change orchestration state from stopped to unenlisted ===#  
#=============================================================#  

RefreshPrompt Stopped unenlist  
$orch.Status = [Microsoft.BizTalk.ExplorerOM.OrchestrationStatus] "Unenlisted"  
$Catalog.SaveChanges()  

#=============================================================#  
#=== Change orchestration state from unenlisted to unbound ===#  
#=============================================================#  

RefreshPrompt Unenlisted unbind  
$orch.Ports["SendInvoicePort"].SendPort = $null  
$orch.Ports["ReceivePOPort"].ReceivePort = $null;  
$orch.Host = $null  
$Catalog.SaveChanges()  

#==================================================================#  
#=== Change orchestration state from unbound back to unenlisted ===#  
#==================================================================#  

RefreshPrompt Unenlisted`(Unbound`) re-bind  
$orch.Ports["SendInvoicePort"].SendPort = $Catalog.SendPorts["HelloWorldSendPort"]  
$orch.Ports["ReceivePOPort"].ReceivePort = $Catalog.ReceivePorts["HelloWorldReceivePort"]  
$orch.Host = $Catalog.Hosts["BizTalkServerApplication"]  
$Catalog.SaveChanges()  

#==================================================================#  
#=== Change orchestration state from unenlisted back to stopped ===#  
#==================================================================#  

RefreshPrompt Unenlisted enlist  
$orch.Status = [Microsoft.BizTalk.ExplorerOM.OrchestrationStatus] "Enlisted"  
$Catalog.SaveChanges()  

#===============================================================#  
#=== Change orchestration state from stopped back to started ===#  
#===============================================================#  

RefreshPrompt Stopped restart  
$orch.Status = [Microsoft.BizTalk.ExplorerOM.OrchestrationStatus] "Started"  
$Catalog.SaveChanges()  

RefreshPrompt Started  

```  

 <span data-ttu-id="3e663-138">次に、Windows PowerShell スクリプトの実行による出力例を示します。</span><span class="sxs-lookup"><span data-stu-id="3e663-138">Here is an example output from running the Windows PowerShell script.</span></span>  

```  
PS C:\> .\OrchestrationBind.ps1  

Make sure the HelloWorld sample application is deployed and running.  
By default it will be listed in the BizTalk Server Administration Console  
with the application name: "BizTalk.Application.1"  

Orchestration Status should now be "Started"  
Press F5 in the Orchestrations view of BizTalk Server Administration Console to refresh and verify  
Pressing <Enter> now will stop the orchestration using ExplorerOM...  

=== Please wait, attempting to stop the orchestration... ===  

Orchestration Status should now be "Stopped"  
Press F5 in the Orchestrations view of BizTalk Server Administration Console to refresh and verify  
Pressing <Enter> now will unenlist the orchestration using ExplorerOM...  

=== Please wait, attempting to unenlist the orchestration... ===  

Orchestration Status should now be "Unenlisted"  
Press F5 in the Orchestrations view of BizTalk Server Administration Console to refresh and verify  
Pressing <Enter> now will unbind the orchestration using ExplorerOM...  

=== Please wait, attempting to unbind the orchestration... ===  

Orchestration Status should now be "Unenlisted(Unbound)"  
Press F5 in the Orchestrations view of BizTalk Server Administration Console to refresh and verify  
Pressing <Enter> now will re-bind the orchestration using ExplorerOM...  

=== Please wait, attempting to re-bind the orchestration... ===  

Orchestration Status should now be "Unenlisted"  
Press F5 in the Orchestrations view of BizTalk Server Administration Console to refresh and verify  
Pressing <Enter> now will enlist the orchestration using ExplorerOM...  

=== Please wait, attempting to enlist the orchestration... ===  

Orchestration Status should now be "Stopped"  
Press F5 in the Orchestrations view of BizTalk Server Administration Console to refresh and verify  
Pressing <Enter> now will restart the orchestration using ExplorerOM...  

=== Please wait, attempting to restart the orchestration... ===  

Orchestration Status should now be "Started"  
Press F5 in the Orchestrations view of BizTalk Server Administration Console to refresh and verify  

```  

## <a name="see-also"></a><span data-ttu-id="3e663-139">参照</span><span class="sxs-lookup"><span data-stu-id="3e663-139">See Also</span></span>  
 <span data-ttu-id="3e663-140">[Admin-explorerom (BizTalk Server Samples フォルダー)](../core/admin-explorerom-biztalk-server-samples-folder.md) </span><span class="sxs-lookup"><span data-stu-id="3e663-140">[Admin-ExplorerOM (BizTalk Server Samples Folder)](../core/admin-explorerom-biztalk-server-samples-folder.md) </span></span>  
 [<span data-ttu-id="3e663-141">HelloWorld (BizTalk Server サンプル)</span><span class="sxs-lookup"><span data-stu-id="3e663-141">HelloWorld (BizTalk Server Sample)</span></span>](../core/helloworld-biztalk-server-sample.md)