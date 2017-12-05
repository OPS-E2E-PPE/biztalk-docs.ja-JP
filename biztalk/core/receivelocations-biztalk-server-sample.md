---
title: "ReceiveLocations (BizTalk Server サンプル) |Microsoft ドキュメント"
ms.custom: 
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: 
ms.suite: 
ms.tgt_pltfrm: 
ms.topic: article
ms.assetid: 87d75941-3973-4166-91b0-f1192b25a804
caps.latest.revision: "9"
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: b5b1a6d6b651ea07430f67667a17029dfe162d4d
ms.sourcegitcommit: 5abd0ed3f9e4858ffaaec5481bfa8878595e95f7
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 11/28/2017
---
# <a name="receivelocations-biztalk-server-sample"></a><span data-ttu-id="b1d66-102">ReceiveLocations (BizTalk Server サンプル)</span><span class="sxs-lookup"><span data-stu-id="b1d66-102">ReceiveLocations (BizTalk Server Sample)</span></span>
<span data-ttu-id="b1d66-103">サンプルを作成する方法を示します ReceiveLocations に受信場所、[!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)]環境を使用して、 **ExplorerOM**管理オブジェクト。</span><span class="sxs-lookup"><span data-stu-id="b1d66-103">The ReceiveLocations sample demonstrates how to create receive locations in the [!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)] environment by using the **ExplorerOM** administration objects.</span></span> <span data-ttu-id="b1d66-104">詳細については、受信場所全般を参照してください[受信場所](../core/receive-locations.md)です。</span><span class="sxs-lookup"><span data-stu-id="b1d66-104">For more information about receive locations in general, see [Receive Locations](../core/receive-locations.md).</span></span>  
  
## <a name="prerequisites"></a><span data-ttu-id="b1d66-105">前提条件</span><span class="sxs-lookup"><span data-stu-id="b1d66-105">Prerequisites</span></span>  
  
-   <span data-ttu-id="b1d66-106">このサンプルの管理オブジェクトを使用するには、[!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)] 管理者特権が必要です。</span><span class="sxs-lookup"><span data-stu-id="b1d66-106">You must have [!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)] administrative privileges to use the administrative objects in this sample.</span></span>  
  
-   <span data-ttu-id="b1d66-107">Windows PowerShell スクリプトを実行するには、Windows PowerShell 実行ポリシーが必要です。</span><span class="sxs-lookup"><span data-stu-id="b1d66-107">The Windows PowerShell script requires the Windows PowerShell execution policy to allow script execution.</span></span> <span data-ttu-id="b1d66-108">詳細については、「 [実行ポリシーの確認](http://go.microsoft.com/fwlink/?LinkId=128930)」を参照してください。</span><span class="sxs-lookup"><span data-stu-id="b1d66-108">For more information see [Examining the Execution Policy](http://go.microsoft.com/fwlink/?LinkId=128930).</span></span>  
  
## <a name="what-this-sample-does"></a><span data-ttu-id="b1d66-109">このサンプルの処理</span><span class="sxs-lookup"><span data-stu-id="b1d66-109">What This Sample Does</span></span>  
 <span data-ttu-id="b1d66-110">このサンプルを使用して、 **ExplorerOM**受信ポートおよび受信場所の管理クラスを作成および構成します。</span><span class="sxs-lookup"><span data-stu-id="b1d66-110">This sample demonstrates using the **ExplorerOM** administrative classes to create and configure receive ports and receive locations.</span></span> <span data-ttu-id="b1d66-111">このトピックには、Windows PowerShell のスクリプト例も含まれています。</span><span class="sxs-lookup"><span data-stu-id="b1d66-111">A Windows PowerShell example script is also included in this topic.</span></span> <span data-ttu-id="b1d66-112">このサンプルは、次の操作を実行します。</span><span class="sxs-lookup"><span data-stu-id="b1d66-112">The sample performs the following operations:</span></span>  
  
-   <span data-ttu-id="b1d66-113">"My Receive Port" という名前の新しい受信ポートを作成します。</span><span class="sxs-lookup"><span data-stu-id="b1d66-113">Create a new receive port named “My Receive Port”.</span></span>  
  
-   <span data-ttu-id="b1d66-114">新しいポートに関連付けられ、HTTP トランスポート プロトコルを使用するよう構成された新しい受信場所を作成します。</span><span class="sxs-lookup"><span data-stu-id="b1d66-114">Create a new receive location associated with the new port and configured to use the HTTP transport protocol.</span></span>  
  
-   <span data-ttu-id="b1d66-115">このサンプルには、受信ポートと受信場所の削除と列挙を行う手順の例も含まれています。</span><span class="sxs-lookup"><span data-stu-id="b1d66-115">This sample also contains example procedures to delete and enumerate receive ports and locations.</span></span>  
  
## <a name="where-to-find-this-sample"></a><span data-ttu-id="b1d66-116">このサンプルの場所</span><span class="sxs-lookup"><span data-stu-id="b1d66-116">Where To Find This Sample</span></span>  
 <span data-ttu-id="b1d66-117">このサンプルは、次の SDK の場所にあります。</span><span class="sxs-lookup"><span data-stu-id="b1d66-117">This sample is located in the following SDK location:</span></span>  
  
 <span data-ttu-id="b1d66-118">\<*パスのサンプル*\> \Admin\ExplorerOM\ReceiveLocations</span><span class="sxs-lookup"><span data-stu-id="b1d66-118">\<*Samples Path*\> \Admin\ExplorerOM\ReceiveLocations</span></span>  
  
 <span data-ttu-id="b1d66-119">次の表は、このサンプルのファイルとその目的を示しています。</span><span class="sxs-lookup"><span data-stu-id="b1d66-119">The following table shows the files in this sample and describes their purpose.</span></span>  
  
|<span data-ttu-id="b1d66-120">ファイル</span><span class="sxs-lookup"><span data-stu-id="b1d66-120">File(s)</span></span>|<span data-ttu-id="b1d66-121">Description</span><span class="sxs-lookup"><span data-stu-id="b1d66-121">Description</span></span>|  
|---------------|-----------------|  
|<span data-ttu-id="b1d66-122">ReceiveLocations.cs</span><span class="sxs-lookup"><span data-stu-id="b1d66-122">ReceiveLocations.cs</span></span>|[!INCLUDE[btsVCSharp](../includes/btsvcsharp-md.md)]<span data-ttu-id="b1d66-123">このサンプルで示す操作のソース ファイルです。</span><span class="sxs-lookup"><span data-stu-id="b1d66-123"> source file for the operations demonstrated in this sample.</span></span>|  
|<span data-ttu-id="b1d66-124">ReceiveLocations.sln と ReceiveLocations.csproj</span><span class="sxs-lookup"><span data-stu-id="b1d66-124">ReceiveLocations.sln and ReceiveLocations.csproj</span></span>|<span data-ttu-id="b1d66-125">このサンプルのソリューション ファイルとプロジェクト ファイルです。</span><span class="sxs-lookup"><span data-stu-id="b1d66-125">Solution and project files for this sample.</span></span>|  
  
## <a name="building-and-running-this-sample"></a><span data-ttu-id="b1d66-126">このサンプルのビルドおよび実行</span><span class="sxs-lookup"><span data-stu-id="b1d66-126">Building and Running This Sample</span></span>  
  
#### <a name="to-build-this-sample"></a><span data-ttu-id="b1d66-127">このサンプルをビルドするには</span><span class="sxs-lookup"><span data-stu-id="b1d66-127">To build this sample</span></span>  
  
1.  <span data-ttu-id="b1d66-128">[!INCLUDE[btsVStudioNoVersion](../includes/btsvstudionoversion-md.md)] で、ソリューション ファイル ReceiveLocations.sln を開きます。</span><span class="sxs-lookup"><span data-stu-id="b1d66-128">In [!INCLUDE[btsVStudioNoVersion](../includes/btsvstudionoversion-md.md)], open the solution file ReceiveLocations.sln.</span></span>  
  
2.  <span data-ttu-id="b1d66-129">**[ビルド]** メニューの **[ソリューションのビルド]**をクリックします。</span><span class="sxs-lookup"><span data-stu-id="b1d66-129">On the **Build** menu, click **Build Solution**.</span></span>  
  
#### <a name="to-run-this-sample"></a><span data-ttu-id="b1d66-130">このサンプルを実行するには</span><span class="sxs-lookup"><span data-stu-id="b1d66-130">To run this sample</span></span>  
  
1.  <span data-ttu-id="b1d66-131">[!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)] 管理者特権のあるコマンド プロンプトを開きます。</span><span class="sxs-lookup"><span data-stu-id="b1d66-131">Open a command prompt with [!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)] administrative privileges.</span></span>  
  
2.  <span data-ttu-id="b1d66-132">変更、 \<*サンプル*\>\Admin\ExplorerOM\ReceiveLocations\bin\debug ディレクトリ。</span><span class="sxs-lookup"><span data-stu-id="b1d66-132">Change to the \<*Samples*\>\Admin\ExplorerOM\ReceiveLocations\bin\debug directory.</span></span>  
  
3.  <span data-ttu-id="b1d66-133">ReceiveLocations.exe を実行します。</span><span class="sxs-lookup"><span data-stu-id="b1d66-133">Run ReceiveLocations.exe.</span></span>  
  
4.  <span data-ttu-id="b1d66-134">[!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)] 管理コンソールで新しい受信ポートと受信場所を表示します。</span><span class="sxs-lookup"><span data-stu-id="b1d66-134">View the new receive port and receive location with the [!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)] Administration console.</span></span>  
  
## <a name="windows-powershell-script-example"></a><span data-ttu-id="b1d66-135">Windows PowerShell スクリプトの例</span><span class="sxs-lookup"><span data-stu-id="b1d66-135">Windows PowerShell Script Example</span></span>  
 <span data-ttu-id="b1d66-136">次の PowerShell スクリプト例は、[!INCLUDE[btsVCSharp](../includes/btsvcsharp-md.md)] バージョンと同じ操作を実行します。</span><span class="sxs-lookup"><span data-stu-id="b1d66-136">The following PowerShell example script demonstrates the same operations as the [!INCLUDE[btsVCSharp](../includes/btsvcsharp-md.md)] version.</span></span> <span data-ttu-id="b1d66-137">このトピックの要件セクションで示したように、スクリプト実行ポリシーが正しく構成されていることを確認します。</span><span class="sxs-lookup"><span data-stu-id="b1d66-137">Make sure the script execution policy has been properly configured as mentioned in the requirements section of this topic.</span></span>  
  
```  
#==================================================================#  
#===                                                            ===#  
#=== Create a new receive port named "My Receive Port" as an    ===#  
#=== example.                                                   ===#  
#===                                                            ===#  
#=== A new receive location will also be created and associated ===#  
#=== with the receive port.                                     ===#  
#===                                                            ===#  
#==================================================================#  
Function CreateAndConfigureReceiveLocation()  
{  
   $myreceivePort = $catalog.AddNewReceivePort($false)  
  
   #=== Note that if you don’t set the name property for the receieve port, ===#  
   #=== it will create a new receive location and add it to the receive     ===#     
   #=== port.                                                               ===#  
  
   $myreceivePort.Name = "My Receive Port"  
  
   #=== Create a new receive location and add it to the receive port ===#  
   $myreceiveLocation = $myreceivePort.AddNewReceiveLocation()  
  
   foreach ($handler in $catalog.ReceiveHandlers)  
   {  
      if ($handler.TransportType.Name -eq "HTTP")  
      {  
         $myreceiveLocation.ReceiveHandler = $handler  
         break  
      }  
   }  
  
   #=== Associate a transport protocol and URI with the receive location. ===#   
   $myreceiveLocation.TransportType = $catalog.ProtocolTypes["HTTP"]  
   $myreceiveLocation.Address = "/home"  
  
   #=== Assign the first receive pipeline found to process the message. ===#  
   foreach ($pipeline in $catalog.Pipelines)  
   {  
      if ($pipeline.Type -eq [Microsoft.Biztalk.ExplorerOM.PipelineType] "Receive")  
      {  
         $myreceiveLocation.ReceivePipeline = $pipeline  
         break  
      }  
  
      #=== Enable the receive location. ===#  
      $myreceiveLocation.Enable = $true  
  
      #=== Optional Properties ===#  
      $myreceiveLocation.FragmentMessages = [Microsoft.BizTalk.ExplorerOM.Fragmentation] "Yes"  
      $myreceiveLocation.ServiceWindowEnabled = $false    
   }  
  
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
  
    #=== Enumerate the receive locations. ===#  
    foreach ($location in $receivePort.ReceiveLocations)  
    {  
        if (($location.Name -eq "Receive Location1") -and ($location.IsPrimary -eq $false))  
        {  
          $receivePort.RemoveReceiveLocation($location)  
        }  
    }  
  
    $catalog.RemoveReceivePort($receivePort)    
  
    #=== Try to commit the changes made so far. If the commit fails, ===#  
    #=== roll back all changes in the trap handler.                  ===#  
    $catalog.SaveChanges()  
  }  
}  
  
#================================================================#  
#===                                                          ===#  
#=== Enumerate the receive ports and their receive locations. ===#  
#===                                                          ===#  
#================================================================#  
Function EnumerateReceiveLocations  
{  
   #=== Enumerate the receive locations in each of the receive ports. ===#  
   foreach ($receivePort in $catalog.ReceivePorts)  
   {  
      Write-host "`r`n$($receivePort.Name)"  
  
      #=== Enumerate the receive locations. ===#  
      foreach ($location in $receivePort.ReceiveLocations)  
      {  
         Write-Host "`t$($location.Name)"  
      }  
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
  "Exception encountered:`r`n"; $_; "`r`nDiscarding Changes and continuing execution so we can attempt to clean up the receive port...`r`n"  
  $Catalog.DiscardChanges()  
}  
  
#=== Create the new receive port with its new receive location ===#  
CreateAndConfigureReceiveLocation  
Write-Host "`r`n`"My Receive Port`" created."  
  
#=== Enumerate each receive port along with its receive locations ===#  
Write-Host "`r`nEnumerating all receive ports...`r`n"  
EnumerateReceiveLocations  
  
#=== Prompt before removing the new example receive port and location ===#  
Write-Host "`r`nPress <ENTER> to delete `"My Receive Port`"..."  
Read-Host  
DeleteReceivePort  
  
#=== Enumerate again to show the receive port and location was removed ===#  
Write-Host "`r`nEnumerating all receive ports to show `"My Receive Port`" was removed...`r`n"  
EnumerateReceiveLocations  
  
```  
  
 <span data-ttu-id="b1d66-138">次に、作成され削除される受信ポートと受信場所を示す PowerShell スクリプト実行からの出力例を示します。</span><span class="sxs-lookup"><span data-stu-id="b1d66-138">Here is example output from the PowerShell script execution showing the receive port and location being created and deleted:</span></span>  
  
```  
PS C:\> .\ReceiveLocations.ps1  
  
"My Receive Port" created.  
  
Enumerating all receive ports...  
  
BatchControlMessageRecvPort  
        BatchControlMessageRecvLoc  
  
ResendReceivePort  
        ResendReceiveLocation  
  
HelloWorldReceivePort  
        HelloWorldReceiveLocation  
  
CBRReceivePort  
        CBRReceiveLocation  
  
RP_ReceivePOFromInternal  
        RL_ReceivePOFromInternal  
  
RP_ShipmentAgency1_OrderFiles  
        RL_ShipmentAgency1_OrderFiles  
  
RP_ShipmentAgency2_OrderFiles  
        RL_ShipmentAgency2_OrderFiles  
  
RP_ReceivePOFromBuyer  
        RL_ReceivePOFromBuyer  
  
RP_Receive_ShipmentAgency_Ack  
        RL_Receive_ShipmentAgency_Ack  
  
My Receive Port  
        Receive Location1  
  
Press <ENTER> to delete "My Receive Port"...  
  
Enumerating all receive ports to show "My Receive Port" was removed...  
  
BatchControlMessageRecvPort  
        BatchControlMessageRecvLoc  
  
ResendReceivePort  
        ResendReceiveLocation  
  
HelloWorldReceivePort  
        HelloWorldReceiveLocation  
  
CBRReceivePort  
        CBRReceiveLocation  
  
RP_ReceivePOFromInternal  
        RL_ReceivePOFromInternal  
  
RP_ShipmentAgency1_OrderFiles  
        RL_ShipmentAgency1_OrderFiles  
  
RP_ShipmentAgency2_OrderFiles  
        RL_ShipmentAgency2_OrderFiles  
  
RP_ReceivePOFromBuyer  
        RL_ReceivePOFromBuyer  
  
RP_Receive_ShipmentAgency_Ack  
        RL_Receive_ShipmentAgency_Ack  
  
```  
  
## <a name="see-also"></a><span data-ttu-id="b1d66-139">参照</span><span class="sxs-lookup"><span data-stu-id="b1d66-139">See Also</span></span>  
 <span data-ttu-id="b1d66-140">[受信場所](../core/receive-locations.md) </span><span class="sxs-lookup"><span data-stu-id="b1d66-140">[Receive Locations](../core/receive-locations.md) </span></span>  
 [<span data-ttu-id="b1d66-141">Admin-ExplorerOM (BizTalk Server Samples フォルダー)</span><span class="sxs-lookup"><span data-stu-id="b1d66-141">Admin-ExplorerOM (BizTalk Server Samples Folder)</span></span>](../core/admin-explorerom-biztalk-server-samples-folder.md)