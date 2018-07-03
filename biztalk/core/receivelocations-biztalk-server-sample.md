---
title: ReceiveLocations (BizTalk Server サンプル) |Microsoft Docs
ms.custom: ''
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: ''
ms.suite: ''
ms.tgt_pltfrm: ''
ms.topic: article
ms.assetid: 87d75941-3973-4166-91b0-f1192b25a804
caps.latest.revision: 9
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: df19296fcf6c93d582034464402597248335e826
ms.sourcegitcommit: 266308ec5c6a9d8d80ff298ee6051b4843c5d626
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 06/27/2018
ms.locfileid: "37019170"
---
# <a name="receivelocations-biztalk-server-sample"></a>ReceiveLocations (BizTalk Server サンプル)
ReceiveLocations サンプルを作成する方法を示しますの受信場所で、[!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)]環境を使用して、 **ExplorerOM**管理オブジェクト。 詳細については、通常の受信場所を参照してください[受信場所](../core/receive-locations.md)します。  

## <a name="prerequisites"></a>前提条件  

- このサンプルの管理オブジェクトを使用するには、[!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)] 管理者特権が必要です。  

- Windows PowerShell スクリプトを実行するには、Windows PowerShell 実行ポリシーが必要です。 詳細については、「 [実行ポリシーの確認](http://go.microsoft.com/fwlink/?LinkId=128930)」を参照してください。  

## <a name="what-this-sample-does"></a>このサンプルの処理  
 このサンプルを使用して、 **ExplorerOM**管理クラスを作成および構成の受信ポートと受信場所。 このトピックには、Windows PowerShell のスクリプト例も含まれています。 このサンプルは、次の操作を実行します。  

-   "My Receive Port" という名前の新しい受信ポートを作成します。  

-   新しいポートに関連付けられ、HTTP トランスポート プロトコルを使用するよう構成された新しい受信場所を作成します。  

-   このサンプルには、受信ポートと受信場所の削除と列挙を行う手順の例も含まれています。  

## <a name="where-to-find-this-sample"></a>このサンプルの場所  
 このサンプルは、次の SDK の場所にあります。  

 \<*パスのサンプル*\> \Admin\ExplorerOM\ReceiveLocations  

 次の表は、このサンプルのファイルとその目的を示しています。  


|                     ファイル                      |                                                   説明                                                    |
|--------------------------------------------------|------------------------------------------------------------------------------------------------------------------|
|               ReceiveLocations.cs                | [!INCLUDE[btsVCSharp](../includes/btsvcsharp-md.md)] このサンプルで示す操作のソース ファイルです。 |
| ReceiveLocations.sln と ReceiveLocations.csproj |                                   このサンプルのソリューション ファイルとプロジェクト ファイルです。                                    |

## <a name="building-and-running-this-sample"></a>このサンプルのビルドおよび実行  

#### <a name="to-build-this-sample"></a>このサンプルをビルドするには  

1. [!INCLUDE[btsVStudioNoVersion](../includes/btsvstudionoversion-md.md)] で、ソリューション ファイル ReceiveLocations.sln を開きます。  

2. **[ビルド]** メニューの **[ソリューションのビルド]** をクリックします。  

#### <a name="to-run-this-sample"></a>このサンプルを実行するには  

1. [!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)] 管理者特権のあるコマンド プロンプトを開きます。  

2. 変更、 \<*サンプル*\>\Admin\ExplorerOM\ReceiveLocations\bin\debug ディレクトリ。  

3. ReceiveLocations.exe を実行します。  

4. [!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)] 管理コンソールで新しい受信ポートと受信場所を表示します。  

## <a name="windows-powershell-script-example"></a>Windows PowerShell スクリプトの例  
 次の PowerShell スクリプト例は、[!INCLUDE[btsVCSharp](../includes/btsvcsharp-md.md)] バージョンと同じ操作を実行します。 このトピックの要件セクションで示したように、スクリプト実行ポリシーが正しく構成されていることを確認します。  

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

 次に、作成され削除される受信ポートと受信場所を示す PowerShell スクリプト実行からの出力例を示します。  

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

## <a name="see-also"></a>参照  
 [受信場所](../core/receive-locations.md)   
 [Admin-ExplorerOM (BizTalk Server Samples フォルダー)](../core/admin-explorerom-biztalk-server-samples-folder.md)