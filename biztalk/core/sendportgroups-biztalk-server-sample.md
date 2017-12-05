---
title: "SendPortGroups (BizTalk Server サンプル) |Microsoft ドキュメント"
ms.custom: 
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: 
ms.suite: 
ms.tgt_pltfrm: 
ms.topic: article
ms.assetid: 4510aa31-16c3-475a-98aa-b590e13ae189
caps.latest.revision: "9"
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: c9bb4a3453539a4c1329e9b0a2de6b46785b53fd
ms.sourcegitcommit: 5abd0ed3f9e4858ffaaec5481bfa8878595e95f7
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 11/28/2017
---
# <a name="sendportgroups-biztalk-server-sample"></a><span data-ttu-id="2413c-102">SendPortGroups (BizTalk Server サンプル)</span><span class="sxs-lookup"><span data-stu-id="2413c-102">SendPortGroups (BizTalk Server Sample)</span></span>
<span data-ttu-id="2413c-103">SendPortGroups サンプルを列挙しを使用して送信ポート グループを管理する方法を示します、 **Microsoft.BizTalk.ExplorerOM**管理クラスです。</span><span class="sxs-lookup"><span data-stu-id="2413c-103">The SendPortGroups sample demonstrates how to enumerate and manage send port groups by using the **Microsoft.BizTalk.ExplorerOM** administration classes.</span></span>  
  
## <a name="prerequisites"></a><span data-ttu-id="2413c-104">前提条件</span><span class="sxs-lookup"><span data-stu-id="2413c-104">Prerequisites</span></span>  
  
-   <span data-ttu-id="2413c-105">このサンプルの管理オブジェクトを使用するには、[!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)] 管理者特権が必要です。</span><span class="sxs-lookup"><span data-stu-id="2413c-105">You must have [!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)] administrative privileges to use the administrative objects in this sample.</span></span>  
  
-   <span data-ttu-id="2413c-106">Windows PowerShell スクリプトを実行するには、Windows PowerShell 実行ポリシーが必要です。</span><span class="sxs-lookup"><span data-stu-id="2413c-106">The Windows PowerShell script requires the Windows PowerShell execution policy to allow script execution.</span></span> <span data-ttu-id="2413c-107">詳細については、「 [実行ポリシーの確認](http://go.microsoft.com/fwlink/?LinkId=128930)」を参照してください。</span><span class="sxs-lookup"><span data-stu-id="2413c-107">For more information see [Examining the Execution Policy](http://go.microsoft.com/fwlink/?LinkId=128930).</span></span>  
  
## <a name="what-this-sample-does"></a><span data-ttu-id="2413c-108">このサンプルの処理</span><span class="sxs-lookup"><span data-stu-id="2413c-108">What This Sample Does</span></span>  
 <span data-ttu-id="2413c-109">このサンプルを使用して、 **BtsCatalogExplorer**と**SendPortGroup**クラス、 **Microsoft.BizTalk.ExplorerOM**送信ポート グループの名前空間を管理するには[!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)]環境。</span><span class="sxs-lookup"><span data-stu-id="2413c-109">This sample demonstrates using the **BtsCatalogExplorer** and **SendPortGroup** classes from the **Microsoft.BizTalk.ExplorerOM** namespace to manage send port groups in a [!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)] environment.</span></span> <span data-ttu-id="2413c-110">サンプルは Microsoft [!INCLUDE[btsVCSharp](../includes/btsvcsharp-md.md)] で作成されています。</span><span class="sxs-lookup"><span data-stu-id="2413c-110">The sample is written in Microsoft [!INCLUDE[btsVCSharp](../includes/btsvcsharp-md.md)].</span></span> <span data-ttu-id="2413c-111">このトピックには、Windows PowerShell のスクリプト例も含まれています。</span><span class="sxs-lookup"><span data-stu-id="2413c-111">A Windows PowerShell example script is also included in this topic.</span></span> <span data-ttu-id="2413c-112">このサンプルは次の操作を示します。</span><span class="sxs-lookup"><span data-stu-id="2413c-112">The sample demonstrates the following operations:</span></span>  
  
-   <span data-ttu-id="2413c-113">使用して、BizTalk 管理データベースに接続する、 **BtsCatalogExplorer**クラスです。</span><span class="sxs-lookup"><span data-stu-id="2413c-113">Connecting to the BizTalk Management database by using the **BtsCatalogExplorer** class.</span></span>  
  
-   <span data-ttu-id="2413c-114">"My Send Port Group" という名前の新しい送信ポート グループを作成する。</span><span class="sxs-lookup"><span data-stu-id="2413c-114">Creating a new send port group named “My Send Port Group”.</span></span>  
  
-   <span data-ttu-id="2413c-115">送信ポート グループを列挙して新たに作成した送信ポート グループを表示する。</span><span class="sxs-lookup"><span data-stu-id="2413c-115">Enumerating send port groups to display the newly created send port group.</span></span>  
  
-   <span data-ttu-id="2413c-116">新しい送信ポート グループを削除する。</span><span class="sxs-lookup"><span data-stu-id="2413c-116">Deleting the new send port group.</span></span>  
  
 <span data-ttu-id="2413c-117">サンプルにはこれ以外の機能もありますが、[!INCLUDE[btsVCSharp](../includes/btsvcsharp-md.md)] バージョンでは実行されません。</span><span class="sxs-lookup"><span data-stu-id="2413c-117">Additional functions are present in the sample but are not executed in the [!INCLUDE[btsVCSharp](../includes/btsvcsharp-md.md)] version.</span></span>  <span data-ttu-id="2413c-118">これらの機能の一部は、PowerShell サンプル スクリプトで示します。</span><span class="sxs-lookup"><span data-stu-id="2413c-118">Some of the additional functions are demonstrated in the PowerShell example script.</span></span> <span data-ttu-id="2413c-119">これらの機能の内容は、次のとおりです。</span><span class="sxs-lookup"><span data-stu-id="2413c-119">The additional functions demonstrate the following functionality:</span></span>  
  
-   <span data-ttu-id="2413c-120">新たに作成した送信ポート グループに送信ポートを追加する (PowerShell サンプルに収録)。</span><span class="sxs-lookup"><span data-stu-id="2413c-120">Adding a send port to the newly created send port group (covered in the PowerShell example).</span></span>  
  
-   <span data-ttu-id="2413c-121">送信ポート グループから送信ポートを削除する (PowerShell サンプルに収録)。</span><span class="sxs-lookup"><span data-stu-id="2413c-121">Deleting a send port from the send port group (covered in the PowerShell example).</span></span>  
  
-   <span data-ttu-id="2413c-122">送信ポート グループを開始する。</span><span class="sxs-lookup"><span data-stu-id="2413c-122">Starting the send port group.</span></span>  
  
-   <span data-ttu-id="2413c-123">送信ポート グループを停止する。</span><span class="sxs-lookup"><span data-stu-id="2413c-123">Stopping the send port group.</span></span>  
  
## <a name="where-to-find-this-sample"></a><span data-ttu-id="2413c-124">このサンプルの場所</span><span class="sxs-lookup"><span data-stu-id="2413c-124">Where To Find This Sample</span></span>  
 <span data-ttu-id="2413c-125">このサンプルは、SDK がある次の場所にあります。</span><span class="sxs-lookup"><span data-stu-id="2413c-125">The sample is located in the following SDK location:</span></span>  
  
 <span data-ttu-id="2413c-126">\<*パスのサンプル*\>\Admin\ExplorerOM\SendPortGroups</span><span class="sxs-lookup"><span data-stu-id="2413c-126">\<*Samples Path*\>\Admin\ExplorerOM\SendPortGroups</span></span>  
  
 <span data-ttu-id="2413c-127">次の表は、このサンプルのファイルとその目的を示しています。</span><span class="sxs-lookup"><span data-stu-id="2413c-127">The following table shows the files in this sample and describes their purpose.</span></span>  
  
|<span data-ttu-id="2413c-128">ファイル</span><span class="sxs-lookup"><span data-stu-id="2413c-128">File(s)</span></span>|<span data-ttu-id="2413c-129">Description</span><span class="sxs-lookup"><span data-stu-id="2413c-129">Description</span></span>|  
|---------------|-----------------|  
|<span data-ttu-id="2413c-130">SendPortGroups.cs</span><span class="sxs-lookup"><span data-stu-id="2413c-130">SendPortGroups.cs</span></span>|<span data-ttu-id="2413c-131">このサンプルに示されている操作の [!INCLUDE[btsVCSharp](../includes/btsvcsharp-md.md)] ソース ファイル。</span><span class="sxs-lookup"><span data-stu-id="2413c-131">[!INCLUDE[btsVCSharp](../includes/btsvcsharp-md.md)] source file for operations demonstrated in this sample.</span></span>|  
|<span data-ttu-id="2413c-132">SendPortGroups.sln、SendPortGroups.csproj、SendPortGroups.suo</span><span class="sxs-lookup"><span data-stu-id="2413c-132">SendPortGroups.sln, SendPortGroups.csproj, SendPortGroups.suo</span></span>|<span data-ttu-id="2413c-133">このサンプルのソリューション ファイルとプロジェクト ファイル。</span><span class="sxs-lookup"><span data-stu-id="2413c-133">Solution and project files for the sample.</span></span>|  
  
## <a name="building-and-running-this-sample"></a><span data-ttu-id="2413c-134">このサンプルのビルドおよび実行</span><span class="sxs-lookup"><span data-stu-id="2413c-134">Building and Running This Sample</span></span>  
  
#### <a name="to-build-this-sample"></a><span data-ttu-id="2413c-135">このサンプルをビルドするには</span><span class="sxs-lookup"><span data-stu-id="2413c-135">To build this sample</span></span>  
  
1.  <span data-ttu-id="2413c-136">[!INCLUDE[btsVStudioNoVersion](../includes/btsvstudionoversion-md.md)] で、SendPortGroups.sln ソリューション ファイルを開きます。</span><span class="sxs-lookup"><span data-stu-id="2413c-136">In [!INCLUDE[btsVStudioNoVersion](../includes/btsvstudionoversion-md.md)], open the solution file SendPortGroups.sln.</span></span>  
  
2.  <span data-ttu-id="2413c-137">ソリューション エクスプ ローラーで、ダブルクリックして**SendPortGroups.cs**サンプル コードを開きます。</span><span class="sxs-lookup"><span data-stu-id="2413c-137">In Solution Explorer, double click **SendPortGroups.cs** to open the sample code.</span></span>  
  
3.  <span data-ttu-id="2413c-138">`root.ConnectionString` 関数内で `CreateSendPortGroup` を見つけます。</span><span class="sxs-lookup"><span data-stu-id="2413c-138">Find the `root.ConnectionString` in the `CreateSendPortGroup` function.</span></span>  <span data-ttu-id="2413c-139">BizTalk 管理データベースをホストする SQL Server を正しく参照するようにサーバー指定を変更する必要があります。</span><span class="sxs-lookup"><span data-stu-id="2413c-139">You must change the server specification to correctly point to the SQL server hosting your BizTalk Management database.</span></span>  <span data-ttu-id="2413c-140">ピリオド (.) を使用してローカル SQL サーバーに接続することもできます。</span><span class="sxs-lookup"><span data-stu-id="2413c-140">You can also use a period (.) to connect to the local SQL server.</span></span>  <span data-ttu-id="2413c-141">例:</span><span class="sxs-lookup"><span data-stu-id="2413c-141">For example:</span></span>  
  
    ```  
    root.ConnectionString = "Integrated Security=SSPI;database=BizTalkMgmtDb;server=.";  
    ```  
  
4.  <span data-ttu-id="2413c-142">次の関数について、手順 3. を繰り返します。</span><span class="sxs-lookup"><span data-stu-id="2413c-142">Repeat step 3 for the following functions:</span></span>  
  
    -   <span data-ttu-id="2413c-143">**EnumerateSendPortGroups**</span><span class="sxs-lookup"><span data-stu-id="2413c-143">**EnumerateSendPortGroups**</span></span>  
  
    -   <span data-ttu-id="2413c-144">**DeleteSendPortGroup**</span><span class="sxs-lookup"><span data-stu-id="2413c-144">**DeleteSendPortGroup**</span></span>  
  
5.  <span data-ttu-id="2413c-145">保存**SendPortGroups.cs**です。</span><span class="sxs-lookup"><span data-stu-id="2413c-145">Save **SendPortGroups.cs**.</span></span>  
  
6.  <span data-ttu-id="2413c-146">メイン メニューで、をクリックして**ビルド**、クリックして**ソリューションのビルド**です。</span><span class="sxs-lookup"><span data-stu-id="2413c-146">On the main menu, click **Build**, and then click **Build Solution**.</span></span>  
  
#### <a name="to-run-this-sample"></a><span data-ttu-id="2413c-147">このサンプルを実行するには</span><span class="sxs-lookup"><span data-stu-id="2413c-147">To run this sample</span></span>  
  
1.  <span data-ttu-id="2413c-148">コマンド ウィンドウを開き、次のフォルダーに移動します。</span><span class="sxs-lookup"><span data-stu-id="2413c-148">Open a command window and navigate to the following folder:</span></span>  
  
     <span data-ttu-id="2413c-149">\<*パスのサンプル*\>\Admin\ExplorerOM\SendPortGroups\bin\Debug</span><span class="sxs-lookup"><span data-stu-id="2413c-149">\<*Samples Path*\>\Admin\ExplorerOM\SendPortGroups\bin\Debug</span></span>  
  
2.  <span data-ttu-id="2413c-150">SendPortGroups.exe ファイルを実行します。</span><span class="sxs-lookup"><span data-stu-id="2413c-150">Run the file SendPortGroups.exe.</span></span>  
  
## <a name="windows-powershell-script-example"></a><span data-ttu-id="2413c-151">Windows PowerShell スクリプトの例</span><span class="sxs-lookup"><span data-stu-id="2413c-151">Windows PowerShell Script Example</span></span>  
 <span data-ttu-id="2413c-152">次の Windows PowerShell スクリプト フラグメントは、の同じ機能を示すために使用できます、 **ExplorerOM**クラス。</span><span class="sxs-lookup"><span data-stu-id="2413c-152">The following Windows PowerShell script fragment can be used to demonstrate the same features of the **ExplorerOM** classes:</span></span>  
  
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
  
 <span data-ttu-id="2413c-153">次に、Windows PowerShell スクリプト サンプルの実行により想定される出力例を示します。</span><span class="sxs-lookup"><span data-stu-id="2413c-153">Here is example expected output from running the Windows PowerShell script sample.</span></span>  
  
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
  
## <a name="see-also"></a><span data-ttu-id="2413c-154">参照</span><span class="sxs-lookup"><span data-stu-id="2413c-154">See Also</span></span>  
 [<span data-ttu-id="2413c-155">Admin-ExplorerOM (BizTalk Server Samples フォルダー)</span><span class="sxs-lookup"><span data-stu-id="2413c-155">Admin-ExplorerOM (BizTalk Server Samples Folder)</span></span>](../core/admin-explorerom-biztalk-server-samples-folder.md)