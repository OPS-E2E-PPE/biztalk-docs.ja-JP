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
# <a name="sendportgroups-biztalk-server-sample"></a><span data-ttu-id="c86d1-102">SendPortGroups (BizTalk Server サンプル)</span><span class="sxs-lookup"><span data-stu-id="c86d1-102">SendPortGroups (BizTalk Server Sample)</span></span>
<span data-ttu-id="c86d1-103">SendPortGroups サンプルは、列挙およびを使用して送信ポート グループを管理する方法を示します、 **Microsoft.BizTalk.ExplorerOM**管理クラス。</span><span class="sxs-lookup"><span data-stu-id="c86d1-103">The SendPortGroups sample demonstrates how to enumerate and manage send port groups by using the **Microsoft.BizTalk.ExplorerOM** administration classes.</span></span>  

## <a name="prerequisites"></a><span data-ttu-id="c86d1-104">前提条件</span><span class="sxs-lookup"><span data-stu-id="c86d1-104">Prerequisites</span></span>  

- <span data-ttu-id="c86d1-105">このサンプルの管理オブジェクトを使用するには、[!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)] 管理者特権が必要です。</span><span class="sxs-lookup"><span data-stu-id="c86d1-105">You must have [!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)] administrative privileges to use the administrative objects in this sample.</span></span>  

- <span data-ttu-id="c86d1-106">Windows PowerShell スクリプトを実行するには、Windows PowerShell 実行ポリシーが必要です。</span><span class="sxs-lookup"><span data-stu-id="c86d1-106">The Windows PowerShell script requires the Windows PowerShell execution policy to allow script execution.</span></span> <span data-ttu-id="c86d1-107">詳細については、「 [実行ポリシーの確認](http://go.microsoft.com/fwlink/?LinkId=128930)」を参照してください。</span><span class="sxs-lookup"><span data-stu-id="c86d1-107">For more information see [Examining the Execution Policy](http://go.microsoft.com/fwlink/?LinkId=128930).</span></span>  

## <a name="what-this-sample-does"></a><span data-ttu-id="c86d1-108">このサンプルの処理</span><span class="sxs-lookup"><span data-stu-id="c86d1-108">What This Sample Does</span></span>  
 <span data-ttu-id="c86d1-109">このサンプルを使用して、 **BtsCatalogExplorer**と**SendPortGroup**クラスを**Microsoft.BizTalk.ExplorerOM**送信ポート グループの名前空間を管理するには[!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)]環境。</span><span class="sxs-lookup"><span data-stu-id="c86d1-109">This sample demonstrates using the **BtsCatalogExplorer** and **SendPortGroup** classes from the **Microsoft.BizTalk.ExplorerOM** namespace to manage send port groups in a [!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)] environment.</span></span> <span data-ttu-id="c86d1-110">サンプルは Microsoft [!INCLUDE[btsVCSharp](../includes/btsvcsharp-md.md)] で作成されています。</span><span class="sxs-lookup"><span data-stu-id="c86d1-110">The sample is written in Microsoft [!INCLUDE[btsVCSharp](../includes/btsvcsharp-md.md)].</span></span> <span data-ttu-id="c86d1-111">このトピックには、Windows PowerShell のスクリプト例も含まれています。</span><span class="sxs-lookup"><span data-stu-id="c86d1-111">A Windows PowerShell example script is also included in this topic.</span></span> <span data-ttu-id="c86d1-112">このサンプルは次の操作を示します。</span><span class="sxs-lookup"><span data-stu-id="c86d1-112">The sample demonstrates the following operations:</span></span>  

- <span data-ttu-id="c86d1-113">使用して、BizTalk 管理データベースに接続する、 **BtsCatalogExplorer**クラス。</span><span class="sxs-lookup"><span data-stu-id="c86d1-113">Connecting to the BizTalk Management database by using the **BtsCatalogExplorer** class.</span></span>  

- <span data-ttu-id="c86d1-114">"My Send Port Group"という名前の新しい送信ポート グループを作成します。</span><span class="sxs-lookup"><span data-stu-id="c86d1-114">Creating a new send port group named “My Send Port Group”.</span></span>  

- <span data-ttu-id="c86d1-115">列挙の送信ポート グループを新しく作成された表示は送信ポート グループです。</span><span class="sxs-lookup"><span data-stu-id="c86d1-115">Enumerating send port groups to display the newly created send port group.</span></span>  

- <span data-ttu-id="c86d1-116">新しい送信ポート グループを削除しています。</span><span class="sxs-lookup"><span data-stu-id="c86d1-116">Deleting the new send port group.</span></span>  

  <span data-ttu-id="c86d1-117">追加の関数は、サンプルに存在するでは実行されません、[!INCLUDE[btsVCSharp](../includes/btsvcsharp-md.md)]バージョン。</span><span class="sxs-lookup"><span data-stu-id="c86d1-117">Additional functions are present in the sample but are not executed in the [!INCLUDE[btsVCSharp](../includes/btsvcsharp-md.md)] version.</span></span>  <span data-ttu-id="c86d1-118">いくつかの追加の関数は、PowerShell スクリプト例で説明します。</span><span class="sxs-lookup"><span data-stu-id="c86d1-118">Some of the additional functions are demonstrated in the PowerShell example script.</span></span> <span data-ttu-id="c86d1-119">追加の関数は、次の機能を示しています。</span><span class="sxs-lookup"><span data-stu-id="c86d1-119">The additional functions demonstrate the following functionality:</span></span>  

- <span data-ttu-id="c86d1-120">(PowerShell の例で説明)、新しく作成した送信ポート グループへの送信ポートを追加します。</span><span class="sxs-lookup"><span data-stu-id="c86d1-120">Adding a send port to the newly created send port group (covered in the PowerShell example).</span></span>  

- <span data-ttu-id="c86d1-121">(PowerShell の例で説明) 送信ポート グループから送信ポートを削除しています。</span><span class="sxs-lookup"><span data-stu-id="c86d1-121">Deleting a send port from the send port group (covered in the PowerShell example).</span></span>  

- <span data-ttu-id="c86d1-122">送信ポート グループを開始しています。</span><span class="sxs-lookup"><span data-stu-id="c86d1-122">Starting the send port group.</span></span>  

- <span data-ttu-id="c86d1-123">送信ポート グループを停止しています。</span><span class="sxs-lookup"><span data-stu-id="c86d1-123">Stopping the send port group.</span></span>  

## <a name="where-to-find-this-sample"></a><span data-ttu-id="c86d1-124">このサンプルの場所</span><span class="sxs-lookup"><span data-stu-id="c86d1-124">Where To Find This Sample</span></span>  
 <span data-ttu-id="c86d1-125">このサンプルは、SDK がある次の場所にあります。</span><span class="sxs-lookup"><span data-stu-id="c86d1-125">The sample is located in the following SDK location:</span></span>  

 <span data-ttu-id="c86d1-126">\<*パスのサンプル*\>\Admin\ExplorerOM\SendPortGroups</span><span class="sxs-lookup"><span data-stu-id="c86d1-126">\<*Samples Path*\>\Admin\ExplorerOM\SendPortGroups</span></span>  

 <span data-ttu-id="c86d1-127">次の表は、このサンプルのファイルとその目的を示しています。</span><span class="sxs-lookup"><span data-stu-id="c86d1-127">The following table shows the files in this sample and describes their purpose.</span></span>  


|                            <span data-ttu-id="c86d1-128">ファイル</span><span class="sxs-lookup"><span data-stu-id="c86d1-128">File(s)</span></span>                            |                                                 <span data-ttu-id="c86d1-129">説明</span><span class="sxs-lookup"><span data-stu-id="c86d1-129">Description</span></span>                                                  |
|---------------------------------------------------------------|--------------------------------------------------------------------------------------------------------------|
|                       <span data-ttu-id="c86d1-130">SendPortGroups.cs</span><span class="sxs-lookup"><span data-stu-id="c86d1-130">SendPortGroups.cs</span></span>                       | <span data-ttu-id="c86d1-131">このサンプルに示されている操作の [!INCLUDE[btsVCSharp](../includes/btsvcsharp-md.md)] ソース ファイル。</span><span class="sxs-lookup"><span data-stu-id="c86d1-131">[!INCLUDE[btsVCSharp](../includes/btsvcsharp-md.md)] source file for operations demonstrated in this sample.</span></span> |
| <span data-ttu-id="c86d1-132">SendPortGroups.sln, SendPortGroups.csproj, SendPortGroups.suo</span><span class="sxs-lookup"><span data-stu-id="c86d1-132">SendPortGroups.sln, SendPortGroups.csproj, SendPortGroups.suo</span></span> |                                  <span data-ttu-id="c86d1-133">このサンプルのソリューション ファイルとプロジェクト ファイル。</span><span class="sxs-lookup"><span data-stu-id="c86d1-133">Solution and project files for the sample.</span></span>                                  |

## <a name="building-and-running-this-sample"></a><span data-ttu-id="c86d1-134">このサンプルのビルドおよび実行</span><span class="sxs-lookup"><span data-stu-id="c86d1-134">Building and Running This Sample</span></span>  

#### <a name="to-build-this-sample"></a><span data-ttu-id="c86d1-135">このサンプルをビルドするには</span><span class="sxs-lookup"><span data-stu-id="c86d1-135">To build this sample</span></span>  

1. <span data-ttu-id="c86d1-136">[!INCLUDE[btsVStudioNoVersion](../includes/btsvstudionoversion-md.md)]、SendPortGroups.sln ソリューション ファイルを開きます。</span><span class="sxs-lookup"><span data-stu-id="c86d1-136">In [!INCLUDE[btsVStudioNoVersion](../includes/btsvstudionoversion-md.md)], open the solution file SendPortGroups.sln.</span></span>  

2. <span data-ttu-id="c86d1-137">ソリューション エクスプ ローラーでダブルクリック**SendPortGroups.cs**サンプル コードを開きます。</span><span class="sxs-lookup"><span data-stu-id="c86d1-137">In Solution Explorer, double click **SendPortGroups.cs** to open the sample code.</span></span>  

3. <span data-ttu-id="c86d1-138">検索、`root.ConnectionString`で、`CreateSendPortGroup`関数。</span><span class="sxs-lookup"><span data-stu-id="c86d1-138">Find the `root.ConnectionString` in the `CreateSendPortGroup` function.</span></span>  <span data-ttu-id="c86d1-139">BizTalk 管理データベースをホストする SQL server を正しく指すサーバーの仕様を変更する必要があります。</span><span class="sxs-lookup"><span data-stu-id="c86d1-139">You must change the server specification to correctly point to the SQL server hosting your BizTalk Management database.</span></span>  <span data-ttu-id="c86d1-140">ローカルの SQL server への接続にピリオド (.) を使用することもできます。</span><span class="sxs-lookup"><span data-stu-id="c86d1-140">You can also use a period (.) to connect to the local SQL server.</span></span>  <span data-ttu-id="c86d1-141">例 :</span><span class="sxs-lookup"><span data-stu-id="c86d1-141">For example:</span></span>  

   ```  
   root.ConnectionString = "Integrated Security=SSPI;database=BizTalkMgmtDb;server=.";  
   ```  

4. <span data-ttu-id="c86d1-142">次の関数について、手順 3。</span><span class="sxs-lookup"><span data-stu-id="c86d1-142">Repeat step 3 for the following functions:</span></span>  

   -   <span data-ttu-id="c86d1-143">**EnumerateSendPortGroups**</span><span class="sxs-lookup"><span data-stu-id="c86d1-143">**EnumerateSendPortGroups**</span></span>  

   -   <span data-ttu-id="c86d1-144">**DeleteSendPortGroup**</span><span class="sxs-lookup"><span data-stu-id="c86d1-144">**DeleteSendPortGroup**</span></span>  

5. <span data-ttu-id="c86d1-145">保存**SendPortGroups.cs**します。</span><span class="sxs-lookup"><span data-stu-id="c86d1-145">Save **SendPortGroups.cs**.</span></span>  

6. <span data-ttu-id="c86d1-146">メイン メニューで、次のようにクリックします。**ビルド**、 をクリックし、**ソリューションのビルド**します。</span><span class="sxs-lookup"><span data-stu-id="c86d1-146">On the main menu, click **Build**, and then click **Build Solution**.</span></span>  

#### <a name="to-run-this-sample"></a><span data-ttu-id="c86d1-147">このサンプルを実行するには</span><span class="sxs-lookup"><span data-stu-id="c86d1-147">To run this sample</span></span>  

1.  <span data-ttu-id="c86d1-148">コマンド ウィンドウを開き、次のフォルダーに移動します。</span><span class="sxs-lookup"><span data-stu-id="c86d1-148">Open a command window and navigate to the following folder:</span></span>  

     <span data-ttu-id="c86d1-149">\<*Samples Path*\>\Admin\ExplorerOM\SendPortGroups\bin\Debug</span><span class="sxs-lookup"><span data-stu-id="c86d1-149">\<*Samples Path*\>\Admin\ExplorerOM\SendPortGroups\bin\Debug</span></span>  

2.  <span data-ttu-id="c86d1-150">SendPortGroups.exe ファイルを実行します。</span><span class="sxs-lookup"><span data-stu-id="c86d1-150">Run the file SendPortGroups.exe.</span></span>  

## <a name="windows-powershell-script-example"></a><span data-ttu-id="c86d1-151">Windows PowerShell スクリプトの例</span><span class="sxs-lookup"><span data-stu-id="c86d1-151">Windows PowerShell Script Example</span></span>  
 <span data-ttu-id="c86d1-152">同じ機能を次の Windows PowerShell スクリプト フラグメントを使用することができます、 **ExplorerOM**クラス。</span><span class="sxs-lookup"><span data-stu-id="c86d1-152">The following Windows PowerShell script fragment can be used to demonstrate the same features of the **ExplorerOM** classes:</span></span>  

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

 <span data-ttu-id="c86d1-153">次に、Windows PowerShell スクリプト サンプルの実行により想定される出力例を示します。</span><span class="sxs-lookup"><span data-stu-id="c86d1-153">Here is example expected output from running the Windows PowerShell script sample.</span></span>  

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

## <a name="see-also"></a><span data-ttu-id="c86d1-154">参照</span><span class="sxs-lookup"><span data-stu-id="c86d1-154">See Also</span></span>  
 [<span data-ttu-id="c86d1-155">Admin-ExplorerOM (BizTalk Server Samples フォルダー)</span><span class="sxs-lookup"><span data-stu-id="c86d1-155">Admin-ExplorerOM (BizTalk Server Samples Folder)</span></span>](../core/admin-explorerom-biztalk-server-samples-folder.md)