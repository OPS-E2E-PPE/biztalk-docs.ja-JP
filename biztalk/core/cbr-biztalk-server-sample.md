---
title: CBR (BizTalk Server サンプル) |Microsoft Docs
ms.custom: ''
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: ''
ms.suite: ''
ms.tgt_pltfrm: ''
ms.topic: article
ms.assetid: add16683-4090-4854-8d6e-923b58937e9d
caps.latest.revision: 11
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: 9b93831275f2ae12bdef54f9116a2242d9cc52d5
ms.sourcegitcommit: 381e83d43796a345488d54b3f7413e11d56ad7be
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 05/07/2019
ms.locfileid: "65357834"
---
# <a name="cbr-biztalk-server-sample"></a><span data-ttu-id="d1240-102">CBR (BizTalk Server サンプル)</span><span class="sxs-lookup"><span data-stu-id="d1240-102">CBR (BizTalk Server Sample)</span></span>
<span data-ttu-id="d1240-103">CBR サンプルの使用例、 **ExplorerOM**管理オブジェクトを追加して新しい構成が BizTalk メッセージのコンテンツ ベース ルーティング用のポートを送信します。</span><span class="sxs-lookup"><span data-stu-id="d1240-103">The CBR sample demonstrates using the **ExplorerOM** administrative objects to add and configure new send ports for content-based routing of BizTalk messages.</span></span>  

## <a name="prerequisites"></a><span data-ttu-id="d1240-104">前提条件</span><span class="sxs-lookup"><span data-stu-id="d1240-104">Prerequisites</span></span>  

- <span data-ttu-id="d1240-105">このサンプルにある setup.bat を実行して CBRSample を展開することが必要です、 \<*サンプル パス*\>\Messaging\CBRSample ディレクトリ。</span><span class="sxs-lookup"><span data-stu-id="d1240-105">This sample requires that the CBRSample be deployed by running setup.bat located in the \<*Samples Path*\>\Messaging\CBRSample directory.</span></span>  

- <span data-ttu-id="d1240-106">このサンプルの管理オブジェクトを使用するには、[!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)] 管理者特権が必要です。</span><span class="sxs-lookup"><span data-stu-id="d1240-106">You must have [!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)] administrative privileges to use the administrative objects in this sample.</span></span>  

- <span data-ttu-id="d1240-107">Windows PowerShell スクリプトの例を実行するには、Windows PowerShell 実行ポリシーが必要です。</span><span class="sxs-lookup"><span data-stu-id="d1240-107">The Windows PowerShell script example requires the Windows PowerShell execution policy to allow script execution.</span></span> <span data-ttu-id="d1240-108">詳しくは、次のトピックをご覧ください。[実行ポリシーの確認](http://go.microsoft.com/fwlink/?LinkId=128930)します。</span><span class="sxs-lookup"><span data-stu-id="d1240-108">For more information see: [Examining the Execution Policy](http://go.microsoft.com/fwlink/?LinkId=128930).</span></span>  

## <a name="what-this-sample-does"></a><span data-ttu-id="d1240-109">このサンプルの処理</span><span class="sxs-lookup"><span data-stu-id="d1240-109">What This Sample Does</span></span>  
 <span data-ttu-id="d1240-110">このサンプルで管理オブジェクトを使用して、 **Microsoft.BizTalk.ExplorerOM** CBRApplication サンプルに 2 つの新しいポートを追加する名前空間。</span><span class="sxs-lookup"><span data-stu-id="d1240-110">This sample demonstrates using the administrative objects in the **Microsoft.BizTalk.ExplorerOM** namespace to add two new ports to the CBRApplication sample.</span></span> <span data-ttu-id="d1240-111">これらの新しいポートは、CBRApplication のサンプル ポートです。</span><span class="sxs-lookup"><span data-stu-id="d1240-111">These new ports are example ports for CBRApplication.</span></span> <span data-ttu-id="d1240-112">これらのポートは、HTTP アダプターを使用してメッセージを仮の HTTP Web サービス アドレスにルーティングするように構成されます。</span><span class="sxs-lookup"><span data-stu-id="d1240-112">The ports are configured to route messages to a hypothetical HTTP Web service address by using the HTTP adapter.</span></span> <span data-ttu-id="d1240-113">このサンプルでは、 **ExplorerOM** オブジェクトを使用して次の操作を実行する方法を示します。</span><span class="sxs-lookup"><span data-stu-id="d1240-113">The sample demonstrates the following operations using the **ExplorerOM** objects:</span></span>  

-   <span data-ttu-id="d1240-114">使用して、 **AddNewSendPort**のメソッド、**アプリケーション**新しい送信ポート sendportusorders を CBRApplication に追加するクラス。</span><span class="sxs-lookup"><span data-stu-id="d1240-114">Using the **AddNewSendPort** method of the **Application** class to add a new send port called SendportUSOrders to CBRApplication.</span></span> <span data-ttu-id="d1240-115">このポートは、仮の Web アドレスによるトランスポートで HTTP アダプターを使用するように構成されます。</span><span class="sxs-lookup"><span data-stu-id="d1240-115">The port is configured to use the HTTP adapter for transport with a hypothetical Web address.</span></span>  

-   <span data-ttu-id="d1240-116">アメリカ合衆国の CBRApplication のメッセージをサブスクライブする SendportUSOrders にフィルターを追加します。100 の国コード値。</span><span class="sxs-lookup"><span data-stu-id="d1240-116">Adding a filter to SendportUSOrders that subscribes to messages in CBRApplication with the U.S. Country Code value of 100.</span></span>  

-   <span data-ttu-id="d1240-117">米国ベースのメッセージを変換するための CBRApplication マップを SendportUSOrders の送信マップに追加します。</span><span class="sxs-lookup"><span data-stu-id="d1240-117">Adding the CBRApplication map for transforming U.S.-based messages to the outbound maps for SendportUSOrders.</span></span>  

-   <span data-ttu-id="d1240-118">新しい送信ポート SendportCANOrders を CBRApplication に追加し、仮の Web アドレスによるトランスポートで HTTP アダプターを使用するようにこのポートを構成します。</span><span class="sxs-lookup"><span data-stu-id="d1240-118">Adding a new send port called SendportCANOrders to CBRApplication and configuring it to use the HTTP adapter for transport with a hypothetical Web address.</span></span>  

-   <span data-ttu-id="d1240-119">カナダの国コードの値 200 を持つ CBRApplication のメッセージをサブスクライブするフィルターを SendportCANOrders に追加します。</span><span class="sxs-lookup"><span data-stu-id="d1240-119">Adding a filter to SendportCANOrders that subscribes to messages in CBRApplication with the Canada Country Code value of 200.</span></span>  

-   <span data-ttu-id="d1240-120">カナダ ベースのメッセージを変換するための CBRApplication マップを SendportCANOrders の送信マップに追加します。</span><span class="sxs-lookup"><span data-stu-id="d1240-120">Adding the CBRApplication map for transforming Canadian-based messages to the outbound maps for SendportCANOrders.</span></span>  

## <a name="where-to-find-this-sample"></a><span data-ttu-id="d1240-121">このサンプルの場所</span><span class="sxs-lookup"><span data-stu-id="d1240-121">Where To Find This Sample</span></span>  
 <span data-ttu-id="d1240-122">このサンプルは、SDK がある次の場所にあります。</span><span class="sxs-lookup"><span data-stu-id="d1240-122">The sample is located in the following SDK location:</span></span>  

 <span data-ttu-id="d1240-123">\<*Samples Path*\>\Admin\ExplorerOM\CBR</span><span class="sxs-lookup"><span data-stu-id="d1240-123">\<*Samples Path*\>\Admin\ExplorerOM\CBR</span></span>  

 <span data-ttu-id="d1240-124">次の表は、このサンプルのファイルとその目的を示しています。</span><span class="sxs-lookup"><span data-stu-id="d1240-124">The following table shows the files in this sample and describes their purpose.</span></span>  


|           <span data-ttu-id="d1240-125">ファイル</span><span class="sxs-lookup"><span data-stu-id="d1240-125">File(s)</span></span>            |                                                 <span data-ttu-id="d1240-126">説明</span><span class="sxs-lookup"><span data-stu-id="d1240-126">Description</span></span>                                                  |
|------------------------------|--------------------------------------------------------------------------------------------------------------|
|    <span data-ttu-id="d1240-127">ContentBasedRouting.cs</span><span class="sxs-lookup"><span data-stu-id="d1240-127">ContentBasedRouting.cs</span></span>    | <span data-ttu-id="d1240-128">このサンプルに示されている操作の [!INCLUDE[btsVCSharp](../includes/btsvcsharp-md.md)] ソース ファイル。</span><span class="sxs-lookup"><span data-stu-id="d1240-128">[!INCLUDE[btsVCSharp](../includes/btsvcsharp-md.md)] source file for operations demonstrated in this sample.</span></span> |
| <span data-ttu-id="d1240-129">CBR.sln,CBR.csproj,CBR.suo</span><span class="sxs-lookup"><span data-stu-id="d1240-129">CBR.sln, CBR.csproj, CBR.suo</span></span> |                                  <span data-ttu-id="d1240-130">このサンプルのソリューション ファイルとプロジェクト ファイル。</span><span class="sxs-lookup"><span data-stu-id="d1240-130">Solution and project files for the sample.</span></span>                                  |

## <a name="building-and-running-this-sample"></a><span data-ttu-id="d1240-131">このサンプルのビルドおよび実行</span><span class="sxs-lookup"><span data-stu-id="d1240-131">Building and Running This Sample</span></span>  

#### <a name="to-build-this-sample"></a><span data-ttu-id="d1240-132">このサンプルをビルドするには</span><span class="sxs-lookup"><span data-stu-id="d1240-132">To build this sample</span></span>  

1. <span data-ttu-id="d1240-133">CBRSample をビルド、展開、および構成する手順が完了していることを確認します。</span><span class="sxs-lookup"><span data-stu-id="d1240-133">Make sure you have completed the steps for building, deploying, and configuring the CBRSample.</span></span> <span data-ttu-id="d1240-134">これらの手順が記載[CBRSample (BizTalk Server サンプル)](../core/cbrsample-biztalk-server-sample.md)します。</span><span class="sxs-lookup"><span data-stu-id="d1240-134">Those steps are provided in [CBRSample (BizTalk Server Sample)](../core/cbrsample-biztalk-server-sample.md).</span></span>  

2. <span data-ttu-id="d1240-135">[!INCLUDE[btsVStudioNoVersion](../includes/btsvstudionoversion-md.md)] で、ソリューション ファイル CBR.sln を開きます。</span><span class="sxs-lookup"><span data-stu-id="d1240-135">In [!INCLUDE[btsVStudioNoVersion](../includes/btsvstudionoversion-md.md)], open the solution file CBR.sln.</span></span>  

3. <span data-ttu-id="d1240-136">**[ビルド]** メニューの **[ソリューションのビルド]** をクリックします。</span><span class="sxs-lookup"><span data-stu-id="d1240-136">On the **Build** menu, click **Build Solution**.</span></span>  

#### <a name="to-run-this-sample"></a><span data-ttu-id="d1240-137">このサンプルを実行するには</span><span class="sxs-lookup"><span data-stu-id="d1240-137">To run this sample</span></span>  

1. <span data-ttu-id="d1240-138">開く、[!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)]管理コンソールに移動して、 **CBRApplication**ノード。</span><span class="sxs-lookup"><span data-stu-id="d1240-138">Open the [!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)] Administration console and navigate to the **CBRApplication** node.</span></span>  

2. <span data-ttu-id="d1240-139">展開、 **CBRApplication**ことを確認するノード、**送信ポート**ノードが現在 CBRUSSendPort と CBRCANSendPort として記載されている 2 つのポートが。</span><span class="sxs-lookup"><span data-stu-id="d1240-139">Expand the **CBRApplication** node to verify that the **Send Ports** node currently has only two ports listed as CBRUSSendPort and CBRCANSendPort.</span></span>  

3. <span data-ttu-id="d1240-140">コマンド ウィンドウを開き、次のフォルダーに移動します。</span><span class="sxs-lookup"><span data-stu-id="d1240-140">Open a command window and navigate to the following folder:</span></span>  

    <span data-ttu-id="d1240-141">\<*Samples Path*\>\Admin\ExplorerOM\CBR\bin\Debug</span><span class="sxs-lookup"><span data-stu-id="d1240-141">\<*Samples Path*\>\Admin\ExplorerOM\CBR\bin\Debug</span></span>  

4. <span data-ttu-id="d1240-142">CBR.exe ファイルを実行します。</span><span class="sxs-lookup"><span data-stu-id="d1240-142">Run the file CBR.exe.</span></span>  

5. <span data-ttu-id="d1240-143">F5 キーを押して、[!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)]管理コンソールで表示するのには、**送信ポート**ノード。</span><span class="sxs-lookup"><span data-stu-id="d1240-143">Press F5 in the [!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)] Administration console to refresh the view under the **Send Ports** node.</span></span> <span data-ttu-id="d1240-144">このサンプルによって、2 つの新しいポートが CBRApplication に追加されています。</span><span class="sxs-lookup"><span data-stu-id="d1240-144">You should now see the two new ports added to CBRApplication by this sample.</span></span> <span data-ttu-id="d1240-145">これらのポートは SendportUSOrders および SendportCANOrders です。</span><span class="sxs-lookup"><span data-stu-id="d1240-145">They are called SendportUSOrders and SendportCANOrders.</span></span>  

## <a name="windows-powershell-script-example"></a><span data-ttu-id="d1240-146">Windows PowerShell スクリプトの例</span><span class="sxs-lookup"><span data-stu-id="d1240-146">Windows PowerShell Script Example</span></span>  
 <span data-ttu-id="d1240-147">次の Windows PowerShell スクリプトを使用すると、 **ExplorerOM** クラスの同じ機能を実行できます。</span><span class="sxs-lookup"><span data-stu-id="d1240-147">The following Windows PowerShell script can be used to demonstrate the same features of the **ExplorerOM** classes.</span></span> <span data-ttu-id="d1240-148">ただし、ため、**追加**のメソッド、 **SendPort.OutboundTranforms**コレクションは内部でマークされている、 **ExplorerOM**アセンブリから直接呼び出せることはできませんWindows PowerShell。</span><span class="sxs-lookup"><span data-stu-id="d1240-148">However, because the **Add** method for the **SendPort.OutboundTranforms** collection is marked Internal in the **ExplorerOM** assembly it cannot be called directly from Windows PowerShell.</span></span> <span data-ttu-id="d1240-149">この Windows PowerShell スクリプトでは、Windows PowerShell から BizTalk WMI プロバイダーを使用して、送信変換マップを新しいポートに追加する方法を示します。</span><span class="sxs-lookup"><span data-stu-id="d1240-149">This Windows PowerShell script demonstrates using the BizTalk WMI Provider from Windows PowerShell to add the outbound transform map to the new port.</span></span>  

```  
Function WMI_AddOutboundTransformToPort($transform,$strPortName)  
{  
    Write-Host "WMI Processing Transform...`r`nPortName `:"$strPortName  
    Write-Host "Transform `:"$transform.AssemblyQualifiedName  

    $WMIsendport = get-wmiobject MSBTS_SendPort -filter "Name=`"$strPortName`"" -namespace root\microsoftbiztalkserver  
    $WMIsendport.OutboundTransforms = $transform.AssemblyQualifiedName  
    [Void] $WMIsendport.Put()  
    [Void] $WMIsendport.Start()  
}  

#===================#  
#=== Main Script ===#  
#===================#  

#=== Make sure the ExplorerOM assembly is loaded ===#  

[void] [System.reflection.Assembly]::LoadWithPartialName("Microsoft.BizTalk.ExplorerOM")  

#=== Connect to the BizTalk Management database ===#  

$Catalog = New-Object Microsoft.BizTalk.ExplorerOM.BtsCatalogExplorer  
$Catalog.ConnectionString = "SERVER=.;DATABASE=BizTalkMgmtDb;Integrated Security=SSPI"  

$CBRApp = $Catalog.Applications["CBRApplication"]  

if ($CBRApp -eq $null)  
{  
    Write-Host "`r`nFailed to find `"CBRApplication`" deployed on this BizTalk server."  
    Write-Host "You must deploy the SDK\Samples\Messaging\CBRSample in order to test this script.`r`n"  
}  
else  
{  
    #=== Register a trap handler for any exceptions ===#  
    $ErrorActionPreference="silentlycontinue"  
    trap { "Exception encountered:`r`n"; $_; "`r`nDiscarding Changes.`r`n";$Catalog.DiscardChanges();exit; }  

    #===================================#  
    #=== Create the U.S. Orders Port ===#  
    #===================================#  

    $USPort = $CBRApp.AddNewSendPort($false,$false)  
    $USPort.Name = "SendportUSOrders"  
    $USPort.PrimaryTransport.TransportType = $Catalog.ProtocolTypes["HTTP"]  
    $USPort.PrimaryTransport.Address = "http://process_orders_US.asp"  
    $USPort.SendPipeline = $Catalog.Pipelines["Microsoft.BizTalk.DefaultPipelines.XMLTransmit"]  

    #=== add the filter to subscribe to messages with U.S country code 100 ===#  

    $USPort.Filter = "<Filter><Group>" +  
                     "<Statement Property='BTS.ReceivePortName' Operator='0' Value='ReceivePortPO'/>" +   
                     "<Statement Property='CBRSample.CountryCode' Operator='0' Value='100'/>" +  
                     "</Group></Filter>"  

    Write-Host("`r`nAdding " + $UsPort.Name + " to catalog ...")  
    $Catalog.SaveChanges()  

    #=========================================================================================#  
    #=== SendPortTranformCollection::Add is marked internal in ExplorerOM for some reason. ===#  
    #=== Use WMI to set this as a workaround through PowerShell.                           ===#  
    #=========================================================================================#  

    WMI_AddOutboundTransformToPort $Catalog.Transforms["CBRSample.CBRInput2USMap"] $USport.Name  

    #=====================================#  
    #=== Create the Canada Orders Port ===#  
    #=====================================#  

    $CanadaPort = $CBRApp.AddNewSendPort($false,$false)  
    $CanadaPort.Name = "SendportCANOrders"  
    $CanadaPort.PrimaryTransport.TransportType = $Catalog.ProtocolTypes["HTTP"]  
    $CanadaPort.PrimaryTransport.Address = "http://process_orders_CAN.asp"  
    $CanadaPort.SendPipeline = $Catalog.Pipelines["Microsoft.BizTalk.DefaultPipelines.XMLTransmit"]  

    #=== add the filter to subscribe to messages with U.S country code 100 ===#  

    $CanadaPort.Filter = "<Filter><Group>" +  
                     "<Statement Property='BTS.ReceivePortName' Operator='0' Value='ReceivePortPO'/>" +   
                     "<Statement Property='CBRSample.CountryCode' Operator='0' Value='200'/>" +  
                     "</Group></Filter>"  

    Write-Host("`r`nAdding " + $UsPort.Name + " to catalog ...")  
    $Catalog.SaveChanges()  

    #=========================================================================================#  
    #=== SendPortTranformCollection::Add is marked internal in ExplorerOM for some reason. ===#  
    #=== Use WMI to set this as a workaround through PowerShell.                           ===#  
    #=========================================================================================#  

    WMI_AddOutboundTransformToPort $Catalog.Transforms["CBRSample.CBRInput2CANMap"] $CanadaPort.Name  

    Write-Host  
}  
```  

 <span data-ttu-id="d1240-150">次に、Windows PowerShell スクリプトを実行して 2 つの新しいポートを作成した場合の出力例を示します。</span><span class="sxs-lookup"><span data-stu-id="d1240-150">Here is an example output from running the Windows PowerShell script to create the two new ports.</span></span> <span data-ttu-id="d1240-151">新しいポートは、既に説明したとおり、[!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)] 管理コンソールでも確認できます。</span><span class="sxs-lookup"><span data-stu-id="d1240-151">The new ports can also be verified in the [!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)] Administration console as mentioned above.</span></span>  

```  
PS C:\> .\CBR.ps1  

Adding SendportUSOrders to catalog ...  
WMI Processing Transform...  
PortName : SendportUSOrders  
Transform : CBRSample.CBRInput2USMap,CBRSample, Version=1.0.0.0, Culture=neutral, PublicKeyToken=ba2e1651515c6db7  

Adding SendportUSOrders to catalog ...  
WMI Processing Transform...  
PortName : SendportCANOrders  
Transform : CBRSample.CBRInput2CANMap,CBRSample, Version=1.0.0.0, Culture=neutral, PublicKeyToken=ba2e1651515c6db7  

```  

## <a name="see-also"></a><span data-ttu-id="d1240-152">参照</span><span class="sxs-lookup"><span data-stu-id="d1240-152">See Also</span></span>  
 <span data-ttu-id="d1240-153">[Admin-explorerom (BizTalk Server Samples フォルダー)](../core/admin-explorerom-biztalk-server-samples-folder.md) </span><span class="sxs-lookup"><span data-stu-id="d1240-153">[Admin-ExplorerOM (BizTalk Server Samples Folder)](../core/admin-explorerom-biztalk-server-samples-folder.md) </span></span>  
 [<span data-ttu-id="d1240-154">CBRSample (BizTalk Server サンプル)</span><span class="sxs-lookup"><span data-stu-id="d1240-154">CBRSample (BizTalk Server Sample)</span></span>](../core/cbrsample-biztalk-server-sample.md)