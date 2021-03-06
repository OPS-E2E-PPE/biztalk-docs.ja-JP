---
title: SendPortGroups (BizTalk Server サンプル) |Microsoft Docs
ms.custom: ''
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: ''
ms.suite: ''
ms.tgt_pltfrm: ''
ms.topic: article
ms.assetid: 4510aa31-16c3-475a-98aa-b590e13ae189
caps.latest.revision: 9
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: ca073cdbe6bc7a32ce0168db227d2121980c92ef
ms.sourcegitcommit: 381e83d43796a345488d54b3f7413e11d56ad7be
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 05/07/2019
ms.locfileid: "65254430"
---
# <a name="sendportgroups-biztalk-server-sample"></a>SendPortGroups (BizTalk Server サンプル)
SendPortGroups サンプルは、列挙およびを使用して送信ポート グループを管理する方法を示します、 **Microsoft.BizTalk.ExplorerOM**管理クラス。  

## <a name="prerequisites"></a>前提条件  

- このサンプルの管理オブジェクトを使用するには、[!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)] 管理者特権が必要です。  

- Windows PowerShell スクリプトを実行するには、Windows PowerShell 実行ポリシーが必要です。 詳細については、「 [実行ポリシーの確認](http://go.microsoft.com/fwlink/?LinkId=128930)」を参照してください。  

## <a name="what-this-sample-does"></a>このサンプルの処理  
 このサンプルを使用して、 **BtsCatalogExplorer**と**SendPortGroup**クラスを**Microsoft.BizTalk.ExplorerOM**送信ポート グループの名前空間を管理するには[!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)]環境。 サンプルは Microsoft [!INCLUDE[btsVCSharp](../includes/btsvcsharp-md.md)] で作成されています。 このトピックには、Windows PowerShell のスクリプト例も含まれています。 このサンプルは次の操作を示します。  

- 使用して、BizTalk 管理データベースに接続する、 **BtsCatalogExplorer**クラス。  

- "My Send Port Group"という名前の新しい送信ポート グループを作成します。  

- 列挙の送信ポート グループを新しく作成された表示は送信ポート グループです。  

- 新しい送信ポート グループを削除しています。  

  追加の関数は、サンプルに存在するでは実行されません、[!INCLUDE[btsVCSharp](../includes/btsvcsharp-md.md)]バージョン。  いくつかの追加の関数は、PowerShell スクリプト例で説明します。 追加の関数は、次の機能を示しています。  

- (PowerShell の例で説明)、新しく作成した送信ポート グループへの送信ポートを追加します。  

- (PowerShell の例で説明) 送信ポート グループから送信ポートを削除しています。  

- 送信ポート グループを開始しています。  

- 送信ポート グループを停止しています。  

## <a name="where-to-find-this-sample"></a>このサンプルの場所  
 このサンプルは、SDK がある次の場所にあります。  

 \<*パスのサンプル*\>\Admin\ExplorerOM\SendPortGroups  

 次の表は、このサンプルのファイルとその目的を示しています。  


|                            ファイル                            |                                                 説明                                                  |
|---------------------------------------------------------------|--------------------------------------------------------------------------------------------------------------|
|                       SendPortGroups.cs                       | このサンプルに示されている操作の [!INCLUDE[btsVCSharp](../includes/btsvcsharp-md.md)] ソース ファイル。 |
| SendPortGroups.sln, SendPortGroups.csproj, SendPortGroups.suo |                                  このサンプルのソリューション ファイルとプロジェクト ファイル。                                  |

## <a name="building-and-running-this-sample"></a>このサンプルのビルドおよび実行  

#### <a name="to-build-this-sample"></a>このサンプルをビルドするには  

1. [!INCLUDE[btsVStudioNoVersion](../includes/btsvstudionoversion-md.md)]、SendPortGroups.sln ソリューション ファイルを開きます。  

2. ソリューション エクスプ ローラーでダブルクリック**SendPortGroups.cs**サンプル コードを開きます。  

3. 検索、`root.ConnectionString`で、`CreateSendPortGroup`関数。  BizTalk 管理データベースをホストする SQL server を正しく指すサーバーの仕様を変更する必要があります。  ローカルの SQL server への接続にピリオド (.) を使用することもできます。  例 :  

   ```  
   root.ConnectionString = "Integrated Security=SSPI;database=BizTalkMgmtDb;server=.";  
   ```  

4. 次の関数について、手順 3。  

   -   **EnumerateSendPortGroups**  

   -   **DeleteSendPortGroup**  

5. 保存**SendPortGroups.cs**します。  

6. メイン メニューで、次のようにクリックします。**ビルド**、 をクリックし、**ソリューションのビルド**します。  

#### <a name="to-run-this-sample"></a>このサンプルを実行するには  

1.  コマンド ウィンドウを開き、次のフォルダーに移動します。  

     \<*Samples Path*\>\Admin\ExplorerOM\SendPortGroups\bin\Debug  

2.  SendPortGroups.exe ファイルを実行します。  

## <a name="windows-powershell-script-example"></a>Windows PowerShell スクリプトの例  
 同じ機能を次の Windows PowerShell スクリプト フラグメントを使用することができます、 **ExplorerOM**クラス。  

```  
Function CreateSendPortGroup($Catalog, $strName)  
{  
   #=== Register a trap handler to discard changes on exceptions ===#  

   $ErrorActionPreference="silentlycontinue"  
   trap { "Exception encountered:`r`n"; $_; "`r`nDiscarding Changes.`r`n";$Catalog.DiscardChanges();exit; }  

   #=== Create a new send port group and set its name ===#  

   $NewSendPortGroup = $Catalog.AddNewSendPortGroup()  
   $NewSendPortGroup.Name = $strName  

   #=== Persist new ports to the BizTalk Management database ===#  

   Write-Host Adding "`"$($NewSendPortGroup.Name)`"..."  
   $catalog.SaveChanges();  
   Write-Host "`r`nCreateSendPortGroup() completed."  
}  

Function DeleteSendPortGroup($Catalog,$strName)  
{  
   #=== Register a trap handler to discard changes on exceptions ===#  

   $ErrorActionPreference="silentlycontinue"  
   trap { "Exception encountered DeleteSendPortGroup:`r`n"; $_; "`r`nDiscarding Changes.`r`n";$Catalog.DiscardChanges();}  

   #=== Delete this sample's new send ports by name ===#  

   $NewSendPortGroup = $Catalog.SendPortGroups[$strName]  
   $Catalog.RemoveSendPortGroup($NewSendPortGroup)  

   #=== Persist changes to the BizTalk Management database ===#  

   Write-Host "Deleting `"$strName`"..."  
   $catalog.SaveChanges();  
   Write-Host "DeleteSendPortGroup() completed."  
}  

Function EnumerateSendPortGroups($Catalog)  
{  
   #=== Register a trap handler to discard changes on exceptions ===#  

   $ErrorActionPreference="silentlycontinue"  
   trap { "Exception encountered During Enumeration:`r`n"; $_; "`r`n"}  

   #=== Display all send port groups by name ===#  

   $count = 1  
   foreach ($group in $catalog.SendPortGroups)  
   {  
     Write-Host "$count. $($group.Name)"  
     $count++  
   }  

   Write-Host "`r`nEnumerateSendPortGroups() completed."  
}  

Function PromptForSendPort($Catalog)  
{  
   #=== Provide a list of the send ports for the user to make a selection ===#  

   Write-Host "Here is a list of send ports:`r`n"  
   $count = 1  
   foreach($sendport in $Catalog.SendPorts)  
   {  
      Write-Host ($Count). ($Sendport.Name)  
      $count++  
   }     

   Write-Host "`r`nChoose a port to add to the group by ordinal (ex. 1,2, etc): " -nonewline  
   $selection = read-host  
   $selection = $Catalog.SendPorts[([int]$selection)-1]  
   Write-Host $Selection.Name selected.  

   return $Selection.Name     
}  

Function AddSendPortToSendPortGroup($Catalog,$strPortName,$strGroupName)  
{  

   #=== Add the user's selected send port to the group ===#  

   #========================================================#  
   #=== Presently, we have to use WMI from PowerShell    ===#  
   #=== This is because the methods on the collections   ===#  
   #=== are marked internal. So unfortunately the        ===#  
   #=== following very straightforward code won't work.  ===#  
   #========================================================#  

   # $sendportgroup = $Catalog.SendPortGroups[$strName]  
   # $sendportgroup.SendPorts.Add($Catalog.SendPorts[$strPortName])  
   # $catalog.SaveChanges();  

   #============================================================================#  
   #=== Get the WMI send port group representation to look up DB and server. ===#     
   #=== Expecting only one to match the query in this example.               ===#  
   #============================================================================#  

   $WQL = "select * from MSBTS_SendPortGroup where Name='" + $strGroupName + "'"  
   $groupset = gwmi -query ($WQL) -namespace "root\MicrosoftBizTalkServer"  

   #=== Create a new MSBTS_SendPortGroup2SendPort instance to map the port to the group ===#     

   $group2port = [WMICLASS]"root\MicrosoftBizTalkServer:MSBTS_SendPortGroup2SendPort"  
   $newPortEntry = [WMI] $group2port.psbase.CreateInstance()  
   $newPortEntry.MgmtDbServerOverride = $groupset.MgmtDbServerOverride   
   $newPortEntry.MgmtDbNameOverride = $groupset.MgmtDbNameOverride  
   $newPortEntry.SendPortGroupName = $groupset.Name  
   $newPortEntry.SendPortName = $strPortName  
   Write-Host "Adding $strPortName to $($groupset.Name)"  

   #=== Persist changes to the BizTalk Management database ===#  

   #=== POWERSHELL V1 BUG WORKAROUND =============================#  
   #=== First method call on a non-cimv2 WMI object can fail.  ===#  
   #=== The workaround in PowerShell V1 is to call GetType()   ===#  
   #=== as the first method.                                   ===#   
   $ErrorActionPreference="silentlycontinue"                     
   trap {}  
   $newPortEntry.GetType()  
   #=== POWERSHELL V1 BUG WORKAROUND =============================#  

   $ErrorActionPreference="continue"                     
   [void] $newPortEntry.Put()  

   #=== Since we used WMI to update the BizTalk Management database, ===#  
   #=== refresh our BtsExplorerCatalog to have an updated DB view.   ===#  

   $Catalog.Refresh()  
   Write-Host "AddSendPortToSendPortGroup() completed."  
}  

Function DeleteSendPortFromSendPortGroup($Catalog, $strPortName, $strGroupName)  
{  
   #========================================================#  
   #=== Presently, we have to use WMI from PowerShell    ===#  
   #=== This is because the methods on the collections   ===#  
   #=== are marked internal. So unfortunately the        ===#  
   #=== following very straightforward code won't work.  ===#  
   #========================================================#  

   # $sendportgroup = $Catalog.SendPortGroups[$strGroupName]  
   # $sendportgroup.SendPorts.Remove($Catalog.SendPorts[$strPortName])  
   # $catalog.SaveChanges();  

   #============================================================================#  
   #=== Get the WMI send port to group instance and delete it.               ===#     
   #=== Expecting only one to match the query in this example.               ===#  
   #============================================================================#  

   $WQL = "select * from MSBTS_SendPortGroup2SendPort where " +   
          "SendPortName='" + $strPortName + "' and " +   
          "SendPortGroupName='" + $strGroupName + "'"  

   $groupset = gwmi -query ($WQL) -namespace "root\MicrosoftBizTalkServer"  

   write-host "Removing $strPortName from $strGroupName..."  
   $groupset.Delete();  

   #=== Since we used WMI to update the BizTalk Management database, ===#  
   #=== refresh our BtsExplorerCatalog to have an updated DB view.   ===#  

   $Catalog.Refresh()  
   Write-Host "DeleteSendPortFromSendPortGroup() completed."  
}  

#========================#  
#=== Main Script Body ===#  
#========================#  

#=== Make sure the ExplorerOM assembly is loaded ===#  

[void] [System.reflection.Assembly]::LoadWithPartialName("Microsoft.BizTalk.ExplorerOM")  

#=== Connect to the BizTalk Management database ===#  

$Catalog = New-Object Microsoft.BizTalk.ExplorerOM.BtsCatalogExplorer  
$Catalog.ConnectionString = "DATABASE=BizTalkMgmtDb;Integrated Security=SSPI;SERVER=."  

#=== Exercise the CreateSendPortGroup function to create a new send port group ===#  

$SendPortGroupName = "PowerShell Sample Send Port Group"  

Write-Host "`r`n============================="  
Write-Host "=== CreateSendPortGroup() ==="  
Write-Host "=============================`r`n"  
CreateSendPortGroup $Catalog $SendPortGroupName  

#=== Enumerate all send port groups to view the new one ===#  

Write-Host "`r`n================================="  
Write-Host "=== EnumerateSendPortGroups() ==="  
Write-Host "=================================`r`n"  
EnumerateSendPortGroups $Catalog  

#=== Add a send port to the group ===#  

Write-Host "`r`n===================================="  
Write-Host "=== AddSendPortToSendPortGroup() ==="  
Write-Host "====================================`r`n"  
$SendPortName = PromptForSendPort($Catalog)  
AddSendPortToSendPortGroup $Catalog $SendPortName $SendPortGroupName  

#=== Remove the send port from the group ===#  

Write-Host "`r`n========================================="  
Write-Host "=== DeleteSendPortFromSendPortGroup() ==="  
Write-Host "=========================================`r`n"  
DeleteSendPortFromSendPortGroup $Catalog $SendPortName $SendPortGroupName  

#=== Delete the group ===#  

Write-Host "`r`n============================="  
Write-Host "=== DeleteSendPortGroup() ==="  
Write-Host "=============================`r`n"  
DeleteSendPortGroup $Catalog $SendPortGroupName  

Write-Host  
```  

 次に、Windows PowerShell スクリプト サンプルの実行により想定される出力例を示します。  

```  
PS C:\> .\sendportgroups.ps1  

=============================  
=== CreateSendPortGroup() ===  
=============================  

Adding "PowerShell Sample Send Port Group"...  

CreateSendPortGroup() completed.  

=================================  
=== EnumerateSendPortGroups() ===  
=================================  

1. PowerShell Sample Send Port Group  

EnumerateSendPortGroups() completed.  

====================================  
=== AddSendPortToSendPortGroup() ===  
====================================  

Here is a list of send ports:  

1 . ResendPort  
2 . HelloWorldSendPort  
3 . ToCustomerSendPort  
4 . CBRUSSendPort  
5 . CBRCANSendPort  
6 . SendportCANOrders  

Choose a port to add to the group by ordinal (ex. 1,2, etc): 2  
HelloWorldSendPort selected.  
Adding HelloWorldSendPort to PowerShell Sample Send Port Group  
AddSendPortToSendPortGroup() completed.  

=========================================  
=== DeleteSendPortFromSendPortGroup() ===  
=========================================  

Removing HelloWorldSendPort from PowerShell Sample Send Port Group...  
DeleteSendPortFromSendPortGroup() completed.  

=============================  
=== DeleteSendPortGroup() ===  
=============================  

Deleting "PowerShell Sample Send Port Group"...  
DeleteSendPortGroup() completed.  
```  

## <a name="see-also"></a>参照  
 [Admin-ExplorerOM (BizTalk Server Samples フォルダー)](../core/admin-explorerom-biztalk-server-samples-folder.md)