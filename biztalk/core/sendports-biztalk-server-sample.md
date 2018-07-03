---
title: SendPorts (BizTalk Server サンプル) |Microsoft Docs
ms.custom: ''
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: ''
ms.suite: ''
ms.tgt_pltfrm: ''
ms.topic: article
ms.assetid: b84f96a2-b749-4fe0-be15-e4dd13eff66f
caps.latest.revision: 13
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: ac6ef809104e1ce11385cb88d94547d0de496af1
ms.sourcegitcommit: 266308ec5c6a9d8d80ff298ee6051b4843c5d626
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 06/27/2018
ms.locfileid: "37009907"
---
# <a name="sendports-biztalk-server-sample"></a><span data-ttu-id="3ac4a-102">SendPorts (BizTalk Server サンプル)</span><span class="sxs-lookup"><span data-stu-id="3ac4a-102">SendPorts (BizTalk Server Sample)</span></span>
<span data-ttu-id="3ac4a-103">SendPorts サンプルは、列挙およびを使用して送信ポートを管理する方法を示します、 **Microsoft.BizTalk.ExplorerOM**管理クラス。</span><span class="sxs-lookup"><span data-stu-id="3ac4a-103">The SendPorts sample demonstrates how to enumerate and manage send ports by using the **Microsoft.BizTalk.ExplorerOM** administration classes.</span></span>  

## <a name="prerequisites"></a><span data-ttu-id="3ac4a-104">前提条件</span><span class="sxs-lookup"><span data-stu-id="3ac4a-104">Prerequisites</span></span>  

- <span data-ttu-id="3ac4a-105">このサンプルの管理オブジェクトを使用するには、[!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)] 管理者特権が必要です。</span><span class="sxs-lookup"><span data-stu-id="3ac4a-105">You must have [!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)] administrative privileges to use the administrative objects in this sample.</span></span>  

- <span data-ttu-id="3ac4a-106">Windows PowerShell スクリプトを実行するには、Windows PowerShell 実行ポリシーが必要です。</span><span class="sxs-lookup"><span data-stu-id="3ac4a-106">The Windows PowerShell script requires the Windows PowerShell execution policy to allow script execution.</span></span> <span data-ttu-id="3ac4a-107">詳細については、次を参照してください。:[実行ポリシーの確認](http://go.microsoft.com/fwlink/?LinkId=128930)します。</span><span class="sxs-lookup"><span data-stu-id="3ac4a-107">For more information see: [Examining the Execution Policy](http://go.microsoft.com/fwlink/?LinkId=128930).</span></span>  

## <a name="what-this-sample-does"></a><span data-ttu-id="3ac4a-108">このサンプルの処理</span><span class="sxs-lookup"><span data-stu-id="3ac4a-108">What This Sample Does</span></span>  
 <span data-ttu-id="3ac4a-109">このサンプルを使用して、 **BtsCatalogExplorer**と**SendPort**クラスを**Microsoft.BizTalk.ExplorerOM** での送信ポートの名前空間を管理するには[!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)]環境。</span><span class="sxs-lookup"><span data-stu-id="3ac4a-109">This sample demonstrates using the **BtsCatalogExplorer** and **SendPort** classes from the **Microsoft.BizTalk.ExplorerOM** namespace to manage send ports in a [!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)] environment.</span></span> <span data-ttu-id="3ac4a-110">サンプルは Microsoft [!INCLUDE[btsVCSharp](../includes/btsvcsharp-md.md)] で作成されています。</span><span class="sxs-lookup"><span data-stu-id="3ac4a-110">The sample is written in Microsoft [!INCLUDE[btsVCSharp](../includes/btsvcsharp-md.md)].</span></span> <span data-ttu-id="3ac4a-111">このトピックには、Windows PowerShell のスクリプト例も含まれています。</span><span class="sxs-lookup"><span data-stu-id="3ac4a-111">A Windows PowerShell example script is also included in this topic.</span></span> <span data-ttu-id="3ac4a-112">このサンプルは次の操作を示します。</span><span class="sxs-lookup"><span data-stu-id="3ac4a-112">The sample demonstrates the following operations:</span></span>  

1. <span data-ttu-id="3ac4a-113">使用して、BizTalk 管理データベースに接続する、 **BtsCatalogExplorer**クラス。</span><span class="sxs-lookup"><span data-stu-id="3ac4a-113">Connecting to the BizTalk Management database by using the **BtsCatalogExplorer** class.</span></span>  

2. <span data-ttu-id="3ac4a-114">2 つの新しい送信ポートの作成は、myStaticOnewaySendPort1 および myDynamicTwowaySendPort1 という名前です。</span><span class="sxs-lookup"><span data-stu-id="3ac4a-114">Creating two new send ports named myStaticOnewaySendPort1 and myDynamicTwowaySendPort1.</span></span> <span data-ttu-id="3ac4a-115">myStaticOnewaySendPort1、その名前が示すように、静的な一方向送信ポートです。</span><span class="sxs-lookup"><span data-stu-id="3ac4a-115">myStaticOnewaySendPort1, as its name implies, is a static one-way send port.</span></span>  <span data-ttu-id="3ac4a-116">送信先 URL の例で、HTTP トランスポートを使用する作成http://sample1です。</span><span class="sxs-lookup"><span data-stu-id="3ac4a-116">It is created to use the HTTP transport with an example destination URL http://sample1.</span></span> <span data-ttu-id="3ac4a-117">myDynamicTwowaySendPort1 は、動的な双方向の送信ポートとして作成されます。</span><span class="sxs-lookup"><span data-stu-id="3ac4a-117">myDynamicTwowaySendPort1 is created as a dynamic two-way send port.</span></span>  

3. <span data-ttu-id="3ac4a-118">[!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)] 環境の送信ポートを列挙する。</span><span class="sxs-lookup"><span data-stu-id="3ac4a-118">Enumerating send ports in a [!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)] environment.</span></span> <span data-ttu-id="3ac4a-119">この列挙には、2 つの新しい送信ポートが含まれます。</span><span class="sxs-lookup"><span data-stu-id="3ac4a-119">This example enumeration should include the two new send ports.</span></span>  

4. <span data-ttu-id="3ac4a-120">2 つの新しい送信ポートを削除する。</span><span class="sxs-lookup"><span data-stu-id="3ac4a-120">Deleting the two new send ports.</span></span>  

5. <span data-ttu-id="3ac4a-121">新しい送信ポートを構成する。</span><span class="sxs-lookup"><span data-stu-id="3ac4a-121">Configuring the new send ports.</span></span> <span data-ttu-id="3ac4a-122">サンプルで示す構成は、サンプル送信ポート myStaticOnewaySendPort1 に適用されます。</span><span class="sxs-lookup"><span data-stu-id="3ac4a-122">The configurations demonstrated by the sample are applied to the example send port named myStaticOnewaySendPort1.</span></span> <span data-ttu-id="3ac4a-123">サンプルで適用される構成内容は次のとおりです。</span><span class="sxs-lookup"><span data-stu-id="3ac4a-123">The configurations applied by the sample include the following:</span></span>  

   -   <span data-ttu-id="3ac4a-124">有効にすると、**ポート処理前に、の要求メッセージ**メッセージ本文を追跡するためのオプション。</span><span class="sxs-lookup"><span data-stu-id="3ac4a-124">Enabling the **Request message before port processing** option for tracking message bodies.</span></span>  

   -   <span data-ttu-id="3ac4a-125">有効にすると、**ポート処理後の要求メッセージ**メッセージ本文を追跡するためのオプション。</span><span class="sxs-lookup"><span data-stu-id="3ac4a-125">Enabling the **Request message after port processing** option for tracking message bodies.</span></span>  

   -   <span data-ttu-id="3ac4a-126">送信メッセージで使用する送信ポートの暗号化証明書を指定する。</span><span class="sxs-lookup"><span data-stu-id="3ac4a-126">Specifying an encryption certificate for the send port to use on outgoing messages.</span></span>  

   -   <span data-ttu-id="3ac4a-127">メッセージのセットに対する参加のフィルターを指定する。</span><span class="sxs-lookup"><span data-stu-id="3ac4a-127">Specifying a filter for enlistment against a set of messages.</span></span>  

   -   <span data-ttu-id="3ac4a-128">メッセージを変換するためのマップを追加する。</span><span class="sxs-lookup"><span data-stu-id="3ac4a-128">Adding a map to transform the messages.</span></span>  

6. <span data-ttu-id="3ac4a-129">2 つの新しい送信ポートの状態を変更する。</span><span class="sxs-lookup"><span data-stu-id="3ac4a-129">Changing send port status on the two new send ports.</span></span>  <span data-ttu-id="3ac4a-130">サンプルを実行すると、myStaticOnewaySendPort1 の次の状態が変更されます。</span><span class="sxs-lookup"><span data-stu-id="3ac4a-130">The execution of the sample will make the following status changes on the myStaticOnewaySendPort1:</span></span>  

   -   <span data-ttu-id="3ac4a-131">状態が "開始" に変更される。</span><span class="sxs-lookup"><span data-stu-id="3ac4a-131">Change the status to started.</span></span>  

   -   <span data-ttu-id="3ac4a-132">状態が "停止" に変更される。</span><span class="sxs-lookup"><span data-stu-id="3ac4a-132">Change the status to stopped.</span></span>  

   -   <span data-ttu-id="3ac4a-133">状態が "バインド済み" に変更される。</span><span class="sxs-lookup"><span data-stu-id="3ac4a-133">Change the status to bound.</span></span> <span data-ttu-id="3ac4a-134">"バインド済み" は、参加解除と同じです。</span><span class="sxs-lookup"><span data-stu-id="3ac4a-134">The bound status is the same as unenlisted.</span></span>  

## <a name="where-to-find-this-sample"></a><span data-ttu-id="3ac4a-135">このサンプルの場所</span><span class="sxs-lookup"><span data-stu-id="3ac4a-135">Where To Find This Sample</span></span>  
 <span data-ttu-id="3ac4a-136">このサンプルは、SDK がある次の場所にあります。</span><span class="sxs-lookup"><span data-stu-id="3ac4a-136">The sample is located in the following SDK location:</span></span>  

 <span data-ttu-id="3ac4a-137">\<*パスのサンプル*\>\Admin\ExplorerOM\SendPorts</span><span class="sxs-lookup"><span data-stu-id="3ac4a-137">\<*Samples Path*\>\Admin\ExplorerOM\SendPorts</span></span>  

 <span data-ttu-id="3ac4a-138">次の表は、このサンプルのファイルとその目的を示しています。</span><span class="sxs-lookup"><span data-stu-id="3ac4a-138">The following table shows the files in this sample and describes their purpose.</span></span>  


|                    <span data-ttu-id="3ac4a-139">ファイル</span><span class="sxs-lookup"><span data-stu-id="3ac4a-139">File(s)</span></span>                     |                                                 <span data-ttu-id="3ac4a-140">説明</span><span class="sxs-lookup"><span data-stu-id="3ac4a-140">Description</span></span>                                                  |
|------------------------------------------------|--------------------------------------------------------------------------------------------------------------|
|                  <span data-ttu-id="3ac4a-141">SendPorts.cs</span><span class="sxs-lookup"><span data-stu-id="3ac4a-141">SendPorts.cs</span></span>                  | <span data-ttu-id="3ac4a-142">このサンプルに示されている操作の [!INCLUDE[btsVCSharp](../includes/btsvcsharp-md.md)] ソース ファイル。</span><span class="sxs-lookup"><span data-stu-id="3ac4a-142">[!INCLUDE[btsVCSharp](../includes/btsvcsharp-md.md)] source file for operations demonstrated in this sample.</span></span> |
| <span data-ttu-id="3ac4a-143">SendPorts.sln、SendPorts.csproj、SendPorts.suo</span><span class="sxs-lookup"><span data-stu-id="3ac4a-143">SendPorts.sln, SendPorts.csproj, SendPorts.suo</span></span> |                                  <span data-ttu-id="3ac4a-144">このサンプルのソリューション ファイルとプロジェクト ファイル。</span><span class="sxs-lookup"><span data-stu-id="3ac4a-144">Solution and project files for the sample.</span></span>                                  |

## <a name="building-and-running-this-sample"></a><span data-ttu-id="3ac4a-145">このサンプルのビルドおよび実行</span><span class="sxs-lookup"><span data-stu-id="3ac4a-145">Building and Running This Sample</span></span>  

#### <a name="to-build-this-sample"></a><span data-ttu-id="3ac4a-146">このサンプルをビルドするには</span><span class="sxs-lookup"><span data-stu-id="3ac4a-146">To build this sample</span></span>  

1. <span data-ttu-id="3ac4a-147">[!INCLUDE[btsVStudioNoVersion](../includes/btsvstudionoversion-md.md)] で、ソリューション ファイル SendPorts.sln を開きます。</span><span class="sxs-lookup"><span data-stu-id="3ac4a-147">In [!INCLUDE[btsVStudioNoVersion](../includes/btsvstudionoversion-md.md)], open the solution file SendPorts.sln.</span></span>  

2. <span data-ttu-id="3ac4a-148">メイン メニューで、次のようにクリックします。**ビルド**、 をクリックし、**ソリューションのビルド**します。</span><span class="sxs-lookup"><span data-stu-id="3ac4a-148">On the main menu, click **Build**, and then click **Build Solution**.</span></span>  

#### <a name="to-run-this-sample"></a><span data-ttu-id="3ac4a-149">このサンプルを実行するには</span><span class="sxs-lookup"><span data-stu-id="3ac4a-149">To run this sample</span></span>  

1.  <span data-ttu-id="3ac4a-150">コマンド ウィンドウを開き、次のフォルダーに移動します。</span><span class="sxs-lookup"><span data-stu-id="3ac4a-150">Open a command window and navigate to the following folder:</span></span>  

     <span data-ttu-id="3ac4a-151">\<*パスのサンプル*\>\Admin\ExplorerOM\SendPorts\bin\Debug</span><span class="sxs-lookup"><span data-stu-id="3ac4a-151">\<*Samples Path*\>\Admin\ExplorerOM\SendPorts\bin\Debug</span></span>  

2.  <span data-ttu-id="3ac4a-152">SendPorts.exe ファイルを実行します。</span><span class="sxs-lookup"><span data-stu-id="3ac4a-152">Run the file SendPorts.exe.</span></span>  

## <a name="windows-powershell-script-example"></a><span data-ttu-id="3ac4a-153">Windows PowerShell スクリプトの例</span><span class="sxs-lookup"><span data-stu-id="3ac4a-153">Windows PowerShell Script Example</span></span>  
 <span data-ttu-id="3ac4a-154">同じ機能を次の Windows PowerShell スクリプト フラグメントを使用することができます、 **ExplorerOM**クラス。</span><span class="sxs-lookup"><span data-stu-id="3ac4a-154">The following Windows PowerShell script fragment can be used to demonstrate the same features of the **ExplorerOM** classes:</span></span>  

```  
Function CreateSendPorts($Catalog)  
{  
    #=== Register a trap handler to discard changes on exceptions ===#  

    $ErrorActionPreference="silentlycontinue"  
    trap { "Exception encountered:`r`n"; $_; "`r`nDiscarding Changes.`r`n";$Catalog.DiscardChanges();exit; }  

    #=== create a new static one-way send port using HTTP transport ===#  

    $myStaticOnewaySendPort = $Catalog.AddNewSendPort($false,$false)  
    $myStaticOnewaySendPort.Name = "myStaticOnewaySendPort1"  
    $myStaticOnewaySendPort.PrimaryTransport.TransportType = $catalog.ProtocolTypes["HTTP"]  
    $myStaticOnewaySendPort.PrimaryTransport.Address = "http://sample1"  
    $myStaticOnewaySendPort.SendPipeline = $Catalog.Pipelines["Microsoft.BizTalk.DefaultPipelines.XMLTransmit"]  

    #=== create a new dynamic two-way send port ===#  

    $myDynamicTwowaySendPort = $catalog.AddNewSendPort($true,$true)  
    $myDynamicTwowaySendPort.Name = "myDynamicTwowaySendPort1";  
    $myDynamicTwowaySendPort.SendPipeline = $Catalog.Pipelines["Microsoft.BizTalk.DefaultPipelines.XMLTransmit"];  
    $myDynamicTwowaySendPort.ReceivePipeline = $Catalog.Pipelines["Microsoft.BizTalk.DefaultPipelines.XMLReceive"];  

    #=== Persist new ports to BizTalk configuration database ===#  

    Write-Host Adding $myStaticOnewaySendPort.Name...  
    Write-Host Adding $myDynamicTwowaySendPort.Name...  
    $catalog.SaveChanges();  
    Write-Host "`r`nCreateSendPorts() completed."  
}  

Function DeleteSendPorts($Catalog)  
{  
    #=== Register a trap handler to discard changes on exceptions ===#  

    $ErrorActionPreference="silentlycontinue"  
    trap { "Exception encountered:`r`n"; $_; "`r`nDiscarding Changes.`r`n";$Catalog.DiscardChanges();exit; }  

    #=== Delete this sample's new send ports by name ===#  

    $Catalog.RemoveSendPort($Catalog.SendPorts["myStaticOnewaySendPort1"])  
    $Catalog.RemoveSendPort($Catalog.SendPorts["myDynamicTwowaySendPort1"])  

    #=== Persist changes to BizTalk configuration database ===#  

    $catalog.SaveChanges();  
    Write-Host "DeleteSendPorts() completed."  
}  

Function EnumerateSendPorts($Catalog)  
{  
    #=== Display all send ports and their status info ===#  

    $catalog.SendPorts | format-table -Property Name, Status -autosize  

    Write-Host "EnumerateSendPorts`(`) completed."  
}  

Function ConfigureSendPort($Catalog)  
{  
    #=== Register a trap handler to discard changes on exceptions ===#  

    $ErrorActionPreference="silentlycontinue"  
    trap { "Exception encountered:`r`n"; $_; "`r`nDiscarding Changes.`r`n";$Catalog.DiscardChanges();exit; }  

    $sendport = $catalog.SendPorts["myStaticOnewaySendPort1"];  

    #=== specify tracking settings for tracking ===#  

    Write-Host $sendport.Name: Enabling BeforeSendPipeline and AfterSendPipeline message body tracking.  
    $sendport.Tracking = ([Microsoft.BizTalk.ExplorerOM.TrackingTypes] "BeforeSendPipeline" -bor   
                         [Microsoft.BizTalk.ExplorerOM.TrackingTypes] "AfterSendPipeline")  

    #=== specify an encryption certificate for outgoing messages ===#  

    Write-Host $sendport.Name: Adding a encryption certificate  
    foreach ($certificate in $catalog.Certificates)  
    {  
        if ($certificate.UsageType -eq [Microsoft.BizTalk.ExplorerOM.CertUsageType] "Encryption")  
        {  
            $sendport.EncryptionCert = $certificate  
        }  
    }  

    #=== specify filters for content-based routing ===#  
    Write-Host $sendport.Name: Adding a filter  
    $sendport.Filter = "<Filter><Group>" +  
                       "<Statement Property='SMTP.Subject' Operator='0' Value='Purchase Order'/>" +  
                       "<Statement Property='SMTP.From' Operator='0' Value='Customer'/>" +  
                       "</Group></Filter>"  

    #=== specify transform maps for document normalization ===#  

    foreach ($transform in $catalog.Transforms)  
    {  
        if (($transform.SourceSchema.FullName -ieq "myPO") -and (transform.TargetSchema.FullName -ieq "partnerPO"))  
        {  
            Write-Host $sendport.Name: Adding a transform  
            $sendport.OutboundTransforms.Add($transform)  
        }  
    }  

    #=== Persist all changes to BizTalk configuration database ===#  

    Write-Host $sendport.Name: Saving changes  
    $catalog.SaveChanges();  
    Write-Host "`r`nConfigureSendPort() completed."  
}  

Function ChangeSendPortStatus($Catalog)  
{  
    #=== Register a trap handler to discard changes on exceptions ===#  

    $ErrorActionPreference="silentlycontinue"  
    trap { "Exception encountered:`r`n"; $_; "`r`nDiscarding Changes.`r`n";$Catalog.DiscardChanges();exit; }  

    $sendport = $catalog.SendPorts["myStaticOnewaySendPort1"];  

    #=== start the send port to begin processing messages ===#  

    $sendport.Status = [Microsoft.BizTalk.ExplorerOM.PortStatus] "Started"  
    Write-Host Changing ($sendport.Name) status to ($sendport.Status)...  
    $catalog.SaveChanges();  
    Write-Host Complete.  

    #=== stop the send port to stop processing and suspend messages ===#  

    $sendport.Status = [Microsoft.BizTalk.ExplorerOM.PortStatus] "Stopped"  
    Write-Host Changing ($sendport.Name) status to ($sendport.Status)...  
    $catalog.SaveChanges();  
    Write-Host Complete.  

    #=== unenlist the send port to stop processing and discard messages ===#  

    $sendport.Status = [Microsoft.BizTalk.ExplorerOM.PortStatus] "Bound"  
    Write-Host Changing ($sendport.Name) status to ($sendport.Status)`(Unenlisted`)...  
    $catalog.SaveChanges();  
    Write-Host Complete.  
}  

#=== Main Script Body ===#  

#=== Make sure the ExplorerOM assembly is loaded ===#  

[void] [System.reflection.Assembly]::LoadWithPartialName("Microsoft.BizTalk.ExplorerOM")  

#=== Connect to the BizTalk Management database ===#  

$Catalog = New-Object Microsoft.BizTalk.ExplorerOM.BtsCatalogExplorer  
$Catalog.ConnectionString = "SERVER=.;DATABASE=BizTalkMgmtDb;Integrated Security=SSPI"  

#=== Exercise the CreateSendPorts function to create the two new ports ===#  

Write-Host "`r`n========================="  
Write-Host "=== CreateSendPorts`(`) ==="  
Write-Host "=========================`r`n"  
CreateSendPorts $Catalog  

#=== Enumerate all send ports to view the two new ports ===#  

Write-Host "`r`n============================"  
Write-Host "=== EnumerateSendPorts`(`) ==="  
Write-Host "============================`r`n"  
EnumerateSendPorts $Catalog  

#=== Add some configuration to the static send port ===#  

Write-Host "`r`n==========================="  
Write-Host "=== ConfigureSendPort`(`) ==="  
Write-Host "===========================`r`n"  
ConfigureSendPort $Catalog  

#=== Cycle through some status changes on the static send port ===#  

Write-Host "`r`n=============================="  
Write-Host "=== ChangeSendPortStatus`(`) ==="  
Write-Host "==============================`r`n"  
ChangeSendPortStatus $Catalog  

#=== Delete the two new ports ===#  

Write-Host "`r`n========================="  
Write-Host "=== DeleteSendPorts`(`) ==="  
Write-Host "=========================`r`n"  
DeleteSendPorts $Catalog  

Write-Host  
```  

 <span data-ttu-id="3ac4a-155">次に、Windows PowerShell スクリプト サンプルの実行により想定される出力例を示します。</span><span class="sxs-lookup"><span data-stu-id="3ac4a-155">Here is example expected output from running the Windows PowerShell script sample.</span></span>  

```  
PS C:\> & 'C:\SendPorts.ps1'  

=========================  
=== CreateSendPorts() ===  
=========================  

Adding myStaticOnewaySendPort1 ...  
Adding myDynamicTwowaySendPort1 ...  

CreateSendPorts() completed.  

============================  
=== EnumerateSendPorts() ===  
============================  

Name                      Status  
----                      ------  
ResendPort               Started  
HelloWorldSendPort       Started  
ToCustomerSendPort       Started  
CBRUSSendPort            Started  
CBRCANSendPort           Started  
SendportCANOrders          Bound  
myStaticOnewaySendPort1    Bound  
myDynamicTwowaySendPort1   Bound  

EnumerateSendPorts() completed.  

===========================  
=== ConfigureSendPort() ===  
===========================  

myStaticOnewaySendPort1 : Enabling BeforeSendPipeline and AfterSendPipeline message body tracking.  
myStaticOnewaySendPort1 : Adding a encryption certificate  
myStaticOnewaySendPort1 : Adding a filter  
myStaticOnewaySendPort1 : Saving changes  

ConfigureSendPort() completed.  

==============================  
=== ChangeSendPortStatus() ===  
==============================  

Changing myStaticOnewaySendPort1 status to Started ...  
Complete.  
Changing myStaticOnewaySendPort1 status to Stopped ...  
Complete.  
Changing myStaticOnewaySendPort1 status to Bound (Unenlisted)...  
Complete.  

=========================  
=== DeleteSendPorts() ===  
=========================  

DeleteSendPorts() completed.  
```  

## <a name="see-also"></a><span data-ttu-id="3ac4a-156">参照</span><span class="sxs-lookup"><span data-stu-id="3ac4a-156">See Also</span></span>  
 [<span data-ttu-id="3ac4a-157">Admin-ExplorerOM (BizTalk Server Samples フォルダー)</span><span class="sxs-lookup"><span data-stu-id="3ac4a-157">Admin-ExplorerOM (BizTalk Server Samples Folder)</span></span>](../core/admin-explorerom-biztalk-server-samples-folder.md)