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
# <a name="receiveports-biztalk-server-sample"></a>ReceivePorts (BizTalk Server サンプル)
ReceivePorts サンプルを新規作成する方法を使用して受信ポート、 **ExplorerOM**管理クラスです。  
  
## <a name="prerequisites"></a>前提条件  
  
-   このサンプルの管理オブジェクトを使用するには、[!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)] 管理者特権が必要です。  
  
-   Windows PowerShell スクリプトを実行するには、Windows PowerShell 実行ポリシーが必要です。 詳細については、「 [実行ポリシーの確認](http://go.microsoft.com/fwlink/?LinkId=128930)」を参照してください。  
  
## <a name="what-this-sample-does"></a>このサンプルの処理  
 このサンプルを使用して、 **BtsCatalogExplorer**と**ReceivePort**クラス、 **Microsoft.BizTalk.ExplorerOM**名前空間を追加、新しい受信ポートを[!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)]. サンプルは Microsoft [!INCLUDE[btsVCSharp](../includes/btsvcsharp-md.md)] で作成されています。 このトピックには、Windows PowerShell のスクリプト例も含まれています。 このサンプルは次の操作を示します。  
  
-   使用して、BizTalk 管理データベースに接続する、 **BtsCatalogExplorer**クラスです。  
  
-   使用して受信ポートを追加、 **AddNewReceivePort**メソッドです。  
  
-   受信ポートを列挙する。  
  
-   受信ポートを削除する。  
  
## <a name="where-to-find-this-sample"></a>このサンプルの場所  
 このサンプルは、SDK がある次の場所にあります。  
  
 \<*パスのサンプル*> \Admin\ExplorerOM\ReceivePorts  
  
 次の表は、このサンプルのファイルとその目的を示しています。  
  
|ファイル|Description|  
|---------------|-----------------|  
|ReceivePorts.cs|このサンプルに示されている操作の [!INCLUDE[btsVCSharp](../includes/btsvcsharp-md.md)] ソース ファイル。|  
|ReceivePorts.sln と ReceivePorts.csproj|このサンプルのソリューションとプロジェクト ファイルです。|  
  
## <a name="building-and-running-this-sample"></a>このサンプルのビルドおよび実行  
  
#### <a name="to-build-this-sample"></a>このサンプルをビルドするには  
  
1.  [!INCLUDE[btsVStudioNoVersion](../includes/btsvstudionoversion-md.md)] で、ソリューション ファイル ReceivePorts.sln を開きます。  
  
2.  **[ビルド]** メニューの **[ソリューションのビルド]**をクリックします。  
  
#### <a name="to-run-this-sample"></a>このサンプルを実行するには  
  
1.  コマンド ウィンドウを開き、次のフォルダーに移動します。  
  
     \<*パスのサンプル*> \Admin\ExplorerOM\ReceivePorts\bin\Debug  
  
2.  ReceivePorts.exe ファイルを実行します。 新しい受信ポートが作成され、ポートの列挙に表示されます。 列挙直後に受信ポートが削除されます。  
  
## <a name="windows-powershell-script-example"></a>Windows PowerShell スクリプトの例  
 次の Windows PowerShell サンプル スクリプトは、の同じ機能を示すために使用できます、 **ExplorerOM**クラス。  
  
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
  
 次に、Windows PowerShell スクリプトを実行して新しい受信ポートを作成した場合の例を示します。  
  
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
  
## <a name="see-also"></a>参照  
 [Admin ExplorerOM (BizTalk Server Samples フォルダ)](../core/admin-explorerom-biztalk-server-samples-folder.md)