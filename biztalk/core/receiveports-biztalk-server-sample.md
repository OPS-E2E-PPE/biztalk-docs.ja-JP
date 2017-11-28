---
title: "ReceivePorts (BizTalk Server サンプル) |Microsoft ドキュメント"
ms.custom: 
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: 
ms.suite: 
ms.tgt_pltfrm: 
ms.topic: article
ms.assetid: c403005d-5e0e-4015-b138-6318e03192af
caps.latest.revision: "9"
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: cb14221ba11fe514ab076dd6bad8cc0aeb5b929e
ms.sourcegitcommit: cb908c540d8f1a692d01dc8f313e16cb4b4e696d
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 09/20/2017
---
# <a name="receiveports-biztalk-server-sample"></a><span data-ttu-id="8b82c-102">ReceivePorts (BizTalk Server サンプル)</span><span class="sxs-lookup"><span data-stu-id="8b82c-102">ReceivePorts (BizTalk Server Sample)</span></span>
<span data-ttu-id="8b82c-103">ReceivePorts サンプルを新規作成する方法を使用して受信ポート、 **ExplorerOM**管理クラスです。</span><span class="sxs-lookup"><span data-stu-id="8b82c-103">The ReceivePorts sample demonstrates how to create a new receive port by using the **ExplorerOM** administrative classes.</span></span>  
  
## <a name="prerequisites"></a><span data-ttu-id="8b82c-104">前提条件</span><span class="sxs-lookup"><span data-stu-id="8b82c-104">Prerequisites</span></span>  
  
-   <span data-ttu-id="8b82c-105">このサンプルの管理オブジェクトを使用するには、[!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)] 管理者特権が必要です。</span><span class="sxs-lookup"><span data-stu-id="8b82c-105">You must have [!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)] administrative privileges to use the administrative objects in this sample.</span></span>  
  
-   <span data-ttu-id="8b82c-106">Windows PowerShell スクリプトを実行するには、Windows PowerShell 実行ポリシーが必要です。</span><span class="sxs-lookup"><span data-stu-id="8b82c-106">The Windows PowerShell script requires the Windows PowerShell execution policy to allow script execution.</span></span> <span data-ttu-id="8b82c-107">詳細については、「 [実行ポリシーの確認](http://go.microsoft.com/fwlink/?LinkId=128930)」を参照してください。</span><span class="sxs-lookup"><span data-stu-id="8b82c-107">For more information see [Examining the Execution Policy](http://go.microsoft.com/fwlink/?LinkId=128930).</span></span>  
  
## <a name="what-this-sample-does"></a><span data-ttu-id="8b82c-108">このサンプルの処理</span><span class="sxs-lookup"><span data-stu-id="8b82c-108">What This Sample Does</span></span>  
 <span data-ttu-id="8b82c-109">このサンプルを使用して、 **BtsCatalogExplorer**と**ReceivePort**クラス、 **Microsoft.BizTalk.ExplorerOM**名前空間を追加、新しい受信ポートを[!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)].</span><span class="sxs-lookup"><span data-stu-id="8b82c-109">This sample demonstrates using the **BtsCatalogExplorer** and **ReceivePort** classes from the **Microsoft.BizTalk.ExplorerOM** namespace to add a new receive port to [!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)].</span></span> <span data-ttu-id="8b82c-110">サンプルは Microsoft [!INCLUDE[btsVCSharp](../includes/btsvcsharp-md.md)] で作成されています。</span><span class="sxs-lookup"><span data-stu-id="8b82c-110">The sample is written in Microsoft [!INCLUDE[btsVCSharp](../includes/btsvcsharp-md.md)].</span></span> <span data-ttu-id="8b82c-111">このトピックには、Windows PowerShell のスクリプト例も含まれています。</span><span class="sxs-lookup"><span data-stu-id="8b82c-111">A Windows PowerShell example script is also included in this topic.</span></span> <span data-ttu-id="8b82c-112">このサンプルは次の操作を示します。</span><span class="sxs-lookup"><span data-stu-id="8b82c-112">The sample demonstrates the following operations:</span></span>  
  
-   <span data-ttu-id="8b82c-113">使用して、BizTalk 管理データベースに接続する、 **BtsCatalogExplorer**クラスです。</span><span class="sxs-lookup"><span data-stu-id="8b82c-113">Connecting to the BizTalk Management database by using the **BtsCatalogExplorer** class.</span></span>  
  
-   <span data-ttu-id="8b82c-114">使用して受信ポートを追加、 **AddNewReceivePort**メソッドです。</span><span class="sxs-lookup"><span data-stu-id="8b82c-114">Adding a new receive port by using the **AddNewReceivePort** method.</span></span>  
  
-   <span data-ttu-id="8b82c-115">受信ポートを列挙する。</span><span class="sxs-lookup"><span data-stu-id="8b82c-115">Enumerating receive ports.</span></span>  
  
-   <span data-ttu-id="8b82c-116">受信ポートを削除する。</span><span class="sxs-lookup"><span data-stu-id="8b82c-116">Deleting receive ports.</span></span>  
  
## <a name="where-to-find-this-sample"></a><span data-ttu-id="8b82c-117">このサンプルの場所</span><span class="sxs-lookup"><span data-stu-id="8b82c-117">Where To Find This Sample</span></span>  
 <span data-ttu-id="8b82c-118">このサンプルは、SDK がある次の場所にあります。</span><span class="sxs-lookup"><span data-stu-id="8b82c-118">The sample is located in the following SDK location:</span></span>  
  
 <span data-ttu-id="8b82c-119">\<*パスのサンプル*> \Admin\ExplorerOM\ReceivePorts</span><span class="sxs-lookup"><span data-stu-id="8b82c-119">\<*Samples Path*>\Admin\ExplorerOM\ReceivePorts</span></span>  
  
 <span data-ttu-id="8b82c-120">次の表は、このサンプルのファイルとその目的を示しています。</span><span class="sxs-lookup"><span data-stu-id="8b82c-120">The following table shows the files in this sample and describes their purpose.</span></span>  
  
|<span data-ttu-id="8b82c-121">ファイル</span><span class="sxs-lookup"><span data-stu-id="8b82c-121">File(s)</span></span>|<span data-ttu-id="8b82c-122">Description</span><span class="sxs-lookup"><span data-stu-id="8b82c-122">Description</span></span>|  
|---------------|-----------------|  
|<span data-ttu-id="8b82c-123">ReceivePorts.cs</span><span class="sxs-lookup"><span data-stu-id="8b82c-123">ReceivePorts.cs</span></span>|<span data-ttu-id="8b82c-124">このサンプルに示されている操作の [!INCLUDE[btsVCSharp](../includes/btsvcsharp-md.md)] ソース ファイル。</span><span class="sxs-lookup"><span data-stu-id="8b82c-124">[!INCLUDE[btsVCSharp](../includes/btsvcsharp-md.md)] source file for operations demonstrated in this sample.</span></span>|  
|<span data-ttu-id="8b82c-125">ReceivePorts.sln と ReceivePorts.csproj</span><span class="sxs-lookup"><span data-stu-id="8b82c-125">ReceivePorts.sln and ReceivePorts.csproj</span></span>|<span data-ttu-id="8b82c-126">このサンプルのソリューションとプロジェクト ファイルです。</span><span class="sxs-lookup"><span data-stu-id="8b82c-126">Solution and project file for the sample.</span></span>|  
  
## <a name="building-and-running-this-sample"></a><span data-ttu-id="8b82c-127">このサンプルのビルドおよび実行</span><span class="sxs-lookup"><span data-stu-id="8b82c-127">Building and Running This Sample</span></span>  
  
#### <a name="to-build-this-sample"></a><span data-ttu-id="8b82c-128">このサンプルをビルドするには</span><span class="sxs-lookup"><span data-stu-id="8b82c-128">To build this sample</span></span>  
  
1.  <span data-ttu-id="8b82c-129">[!INCLUDE[btsVStudioNoVersion](../includes/btsvstudionoversion-md.md)] で、ソリューション ファイル ReceivePorts.sln を開きます。</span><span class="sxs-lookup"><span data-stu-id="8b82c-129">In [!INCLUDE[btsVStudioNoVersion](../includes/btsvstudionoversion-md.md)], open the solution file ReceivePorts.sln.</span></span>  
  
2.  <span data-ttu-id="8b82c-130">**[ビルド]** メニューの **[ソリューションのビルド]**をクリックします。</span><span class="sxs-lookup"><span data-stu-id="8b82c-130">On the **Build** menu, click **Build Solution**.</span></span>  
  
#### <a name="to-run-this-sample"></a><span data-ttu-id="8b82c-131">このサンプルを実行するには</span><span class="sxs-lookup"><span data-stu-id="8b82c-131">To run this sample</span></span>  
  
1.  <span data-ttu-id="8b82c-132">コマンド ウィンドウを開き、次のフォルダーに移動します。</span><span class="sxs-lookup"><span data-stu-id="8b82c-132">Open a command window and navigate to the following folder:</span></span>  
  
     <span data-ttu-id="8b82c-133">\<*パスのサンプル*> \Admin\ExplorerOM\ReceivePorts\bin\Debug</span><span class="sxs-lookup"><span data-stu-id="8b82c-133">\<*Samples Path*>\Admin\ExplorerOM\ReceivePorts\bin\Debug</span></span>  
  
2.  <span data-ttu-id="8b82c-134">ReceivePorts.exe ファイルを実行します。</span><span class="sxs-lookup"><span data-stu-id="8b82c-134">Run the file ReceivePorts.exe.</span></span> <span data-ttu-id="8b82c-135">新しい受信ポートが作成され、ポートの列挙に表示されます。</span><span class="sxs-lookup"><span data-stu-id="8b82c-135">The new receive port should be created and shown in the port enumeration.</span></span> <span data-ttu-id="8b82c-136">列挙直後に受信ポートが削除されます。</span><span class="sxs-lookup"><span data-stu-id="8b82c-136">After the enumeration the receive port is immediately removed.</span></span>  
  
## <a name="windows-powershell-script-example"></a><span data-ttu-id="8b82c-137">Windows PowerShell スクリプトの例</span><span class="sxs-lookup"><span data-stu-id="8b82c-137">Windows PowerShell Script Example</span></span>  
 <span data-ttu-id="8b82c-138">次の Windows PowerShell サンプル スクリプトは、の同じ機能を示すために使用できます、 **ExplorerOM**クラス。</span><span class="sxs-lookup"><span data-stu-id="8b82c-138">The following Windows PowerShell example script can be used to demonstrate the same features of the **ExplorerOM** classes:</span></span>  
  
```  
#==================================================================#  
#===                                                            ===#  
#=== Create a new receive port named "My Receive Port".         ===#  
#===                                                            ===#  
#==================================================================#  
Function CreateReceivePort()  
{   
  #=== Passing false here creates a one-way receive port opposed to a two-way ===#  
  $myreceivePort = $catalog.AddNewReceivePort($false)  
  
  $myreceivePort.Name = "My Receive Port"  
  $myreceivePort.Tracking = [Microsoft.BizTalk.ExplorerOM.TrackingTypes] "AfterReceivePipeline"  
  
  #=== Try to commit the changes made so far. If the commit fails, ===#  
  #=== roll back all changes.                                      ===#  
  $catalog.SaveChanges()  
}  
  
#===============================================================#  
#===                                                         ===#  
#=== Delete the receive port named "My Receive Port"         ===#  
#===                                                         ===#  
#===============================================================#  
Function DeleteReceivePort  
{  
  $receivePort = $catalog.ReceivePorts["My Receive Port"]  
  
  if ($receivePort -ne $null)  
  {  
    $catalog.RemoveReceivePort($receivePort)    
  
    #=== Try to commit the changes made so far. If the commit fails, ===#  
    #=== roll back all changes in the trap handler.                  ===#  
    $catalog.SaveChanges()  
  }  
}  
  
#================================================================#  
#===                                                          ===#  
#=== Enumerate the receive ports.                             ===#  
#===                                                          ===#  
#================================================================#  
Function EnumerateReceivePorts  
{  
   #=== Enumerate the receive ports. ===#  
   foreach ($receivePort in $catalog.ReceivePorts)  
   {  
      Write-host "`r`n$($receivePort.Name)"  
   }  
  
   Write-host ""  
}  
  
#===================#  
#=== Main Script ===#  
#===================#  
  
#=== Make sure the ExplorerOM assembly is loaded ===#  
  
[void] [System.reflection.Assembly]::LoadWithPartialName("Microsoft.BizTalk.ExplorerOM")  
  
#=== Connect to the BizTalk Management database ===#  
  
$Catalog = New-Object Microsoft.BizTalk.ExplorerOM.BtsCatalogExplorer  
$Catalog.ConnectionString = "SERVER=.;DATABASE=BizTalkMgmtDb;Integrated Security=SSPI"  
  
#==================================================================#  
#=== Register a trap handler to discard changes on exceptions   ===#  
#=== Execution will continue in the event we want to delete the ===#  
#=== receive port.                                              ===#  
#==================================================================#  
  
$Script:NoExceptionOccurred = $true  
$ErrorActionPreference="silentlycontinue"  
trap   
{   
  $Script:NoExceptionOccurred = $false  
  "Exception encountered:`r`n"; $_; "`r`nDiscarding changes and continuing execution so we can attempt to clean up the receive port...`r`n"  
  $Catalog.DiscardChanges()  
}  
  
#=== Create the new receive port ===#  
Write-Host "`r`nAttempting to create `"My Receive Port`"..."  
CreateReceivePort  
  
#=== Enumerate each receive port ===#  
Write-Host "`r`nEnumerating all receive ports...`r`n"  
EnumerateReceivePorts  
  
#=== Prompt before removing the new example receive port ===#  
Write-Host "`r`nPress <ENTER> to delete `"My Receive Port`"..."  
Read-Host  
DeleteReceivePort  
  
#=== Enumerate again to show the receive port was removed ===#  
Write-Host "`r`nEnumerating all receive ports to show `"My Receive Port`" was removed...`r`n"  
EnumerateReceivePorts  
  
```  
  
 <span data-ttu-id="8b82c-139">次に、Windows PowerShell スクリプトを実行して新しい受信ポートを作成した場合の例を示します。</span><span class="sxs-lookup"><span data-stu-id="8b82c-139">Here is an example of running the Windows PowerShell script to create the new receive port:</span></span>  
  
```  
PS C:\> .\receiveports.ps1  
  
Attempting to create "My Receive Port"...  
  
Enumerating all receive ports...  
  
BatchControlMessageRecvPort  
  
ResendReceivePort  
  
HelloWorldReceivePort  
  
CBRReceivePort  
  
RP_ReceivePOFromInternal  
  
RP_ShipmentAgency1_OrderFiles  
  
RP_ShipmentAgency2_OrderFiles  
  
RP_ReceivePOFromBuyer  
  
RP_Receive_ShipmentAgency_Ack  
  
My Receive Port  
  
Press <ENTER> to delete "My Receive Port"...  
  
Enumerating all receive ports to show "My Receive Port" was removed...  
  
BatchControlMessageRecvPort  
  
ResendReceivePort  
  
HelloWorldReceivePort  
  
CBRReceivePort  
  
RP_ReceivePOFromInternal  
  
RP_ShipmentAgency1_OrderFiles  
  
RP_ShipmentAgency2_OrderFiles  
  
RP_ReceivePOFromBuyer  
  
RP_Receive_ShipmentAgency_Ack  
```  
  
## <a name="see-also"></a><span data-ttu-id="8b82c-140">参照</span><span class="sxs-lookup"><span data-stu-id="8b82c-140">See Also</span></span>  
 [<span data-ttu-id="8b82c-141">Admin ExplorerOM (BizTalk Server Samples フォルダ)</span><span class="sxs-lookup"><span data-stu-id="8b82c-141">Admin-ExplorerOM (BizTalk Server Samples Folder)</span></span>](../core/admin-explorerom-biztalk-server-samples-folder.md)