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
ms.openlocfilehash: 372c3b7e7ce839729af416385b1404c09a7ca5dd
ms.sourcegitcommit: 381e83d43796a345488d54b3f7413e11d56ad7be
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 05/07/2019
ms.locfileid: "65322362"
---
# <a name="orchestrationbinding-biztalk-server-sample"></a>OrchestrationBinding (BizTalk Server サンプル)
オーケストレーションのバインドのサンプルでは、 [Microsoft.BizTalk.ExplorerOM](http://msdn.microsoft.com/library/microsoft.biztalk.explorerom.aspx) 管理オブジェクトを使用してオーケストレーションを構成および管理します。  

## <a name="prerequisites"></a>前提条件  

- このサンプルにある setup.bat を実行して HelloWorld サンプルを配置することが必要です、 \<*サンプル パス*\>\Orchestrations\HelloWorld ディレクトリ。  

- このサンプルの管理オブジェクトを使用するには、[!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)] 管理者特権が必要です。  

- Windows PowerShell スクリプトの例を実行するには、Windows PowerShell 実行ポリシーが必要です。 詳細については、「 [実行ポリシーの確認](http://go.microsoft.com/fwlink/?LinkId=128930)」を参照してください。  

## <a name="what-this-sample-does"></a>このサンプルの処理  
 このサンプルでは、 **Microsoft.BizTalk.ExplorerOM** 名前空間の管理オブジェクトを使用してオーケストレーションを管理する方法を示します。 このサンプルでは、 **ExplorerOM** オブジェクトを使用して次の操作を実行する方法を示します。  

-   [Microsoft.BizTalk.ExplorerOM.BtsCatalogExplorer](http://msdn.microsoft.com/library/microsoft.biztalk.explorerom.btscatalogexplorer.aspx) クラスを使用して BizTalk 管理データベースに接続する。  

-   **Microsoft.BizTalk.ExplorerOM.BtsOrchestration** クラスの [Status](http://msdn.microsoft.com/library/Microsoft.BizTalk.ExplorerOM.BtsOrchestration.aspx) プロパティを変更してオーケストレーションを停止および開始する。  

-   **Microsoft.BizTalk.ExplorerOM.BtsOrchestration** クラスの [Status](http://msdn.microsoft.com/library/Microsoft.BizTalk.ExplorerOM.BtsOrchestration.aspx) プロパティを変更してオーケストレーションを参加および参加解除する。  

-   **Microsoft.BizTalk.ExplorerOM.BtsOrchestration** クラスの [Status](http://msdn.microsoft.com/library/Microsoft.BizTalk.ExplorerOM.BtsOrchestration.aspx) プロパティを変更してオーケストレーションをバインドおよびバインド解除する。  

## <a name="where-to-find-this-sample"></a>このサンプルの場所  
 このサンプルは、SDK がある次の場所にあります。  

 \<*Samples Path*\>\Admin\ExplorerOM\OrchestrationBinding  

 次の表は、このサンプルのファイルとその目的を示しています。  


|                                     ファイル                                     |                                                 説明                                                  |
|---------------------------------------------------------------------------------|--------------------------------------------------------------------------------------------------------------|
|                             OrchestrationBinding.cs                             | このサンプルに示されている操作の [!INCLUDE[btsVCSharp](../includes/btsvcsharp-md.md)] ソース ファイル。 |
| OrchestrationBinding.sln、OrchestrationBinding.csproj、OrchestrationBinding.suo |                                  このサンプルのソリューション ファイルとプロジェクト ファイル。                                  |

## <a name="building-and-running-this-sample"></a>このサンプルのビルドおよび実行  

#### <a name="to-build-this-sample"></a>このサンプルをビルドするには  

1. HelloWorld サンプルのビルドおよび初期化の手順が完了していることを確認します。 これらの手順が記載[HelloWorld (BizTalk Server サンプル)](../core/helloworld-biztalk-server-sample.md)します。  

2. [!INCLUDE[btsVStudioNoVersion](../includes/btsvstudionoversion-md.md)]で、ソリューション ファイル OrchestrationBinding.sln を開きます。  

3. **[ビルド]** メニューの **[ソリューションのビルド]** をクリックします。  

#### <a name="to-run-this-sample"></a>このサンプルを実行するには  

1.  コマンド ウィンドウを開き、次のフォルダーに移動します。  

     \<*Samples Path*\>\Admin\ExplorerOM\OrchestrationBinding\bin\Debug  

2.  OrchestrationBinding.exe を実行して、サンプルの指示に従います。  

## <a name="windows-powershell-script-example"></a>Windows PowerShell スクリプトの例  
 次の Windows PowerShell スクリプトを使用すると、 **ExplorerOM** クラスの同じ機能を実行できます。  

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

 次に、Windows PowerShell スクリプトの実行による出力例を示します。  

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

## <a name="see-also"></a>参照  
 [Admin-explorerom (BizTalk Server Samples フォルダー)](../core/admin-explorerom-biztalk-server-samples-folder.md)   
 [HelloWorld (BizTalk Server サンプル)](../core/helloworld-biztalk-server-sample.md)