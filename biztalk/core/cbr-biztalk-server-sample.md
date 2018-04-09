---
title: CBR (BizTalk Server サンプル) |Microsoft ドキュメント
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
ms.openlocfilehash: 30811b4f0dba463d518bdd9cd8f6d227e0e79aac
ms.sourcegitcommit: 5abd0ed3f9e4858ffaaec5481bfa8878595e95f7
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 11/28/2017
---
# <a name="cbr-biztalk-server-sample"></a>CBR (BizTalk Server サンプル)
CBR サンプルの使用例、 **ExplorerOM**管理オブジェクトを追加して新しい構成が BizTalk メッセージのコンテンツ ベース ルーティング用のポートを送信します。  
  
## <a name="prerequisites"></a>前提条件  
  
-   このサンプルにある setup.bat を実行して CBRSample を配置することが必要です、 \<*サンプル パス*\>\Messaging\CBRSample ディレクトリ。  
  
-   このサンプルの管理オブジェクトを使用するには、[!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)] 管理者特権が必要です。  
  
-   Windows PowerShell スクリプトの例を実行するには、Windows PowerShell 実行ポリシーが必要です。 詳細については、次を参照してください。:[実行ポリシーの確認](http://go.microsoft.com/fwlink/?LinkId=128930)です。  
  
## <a name="what-this-sample-does"></a>このサンプルの処理  
 このサンプルでは、管理オブジェクトを使用して、 **Microsoft.BizTalk.ExplorerOM** CBRApplication サンプルに 2 つの新しいポートを追加する名前空間。 これらの新しいポートは、CBRApplication のサンプル ポートです。 これらのポートは、HTTP アダプターを使用してメッセージを仮の HTTP Web サービス アドレスにルーティングするように構成されます。 このサンプルでは、 **ExplorerOM** オブジェクトを使用して次の操作を実行する方法を示します。  
  
-   使用して、 **AddNewSendPort**のメソッド、**アプリケーション**sendportusorders を CBRApplication に新しい送信ポートを追加するクラス。 このポートは、仮の Web アドレスによるトランスポートで HTTP アダプターを使用するように構成されます。  
  
-   アメリカ合衆国の CBRApplication のメッセージをサブスクライブする SendportUSOrders にフィルターを追加します。100 の国コード値。  
  
-   米国ベースのメッセージを変換するための CBRApplication マップを SendportUSOrders の送信マップに追加します。  
  
-   新しい送信ポート SendportCANOrders を CBRApplication に追加し、仮の Web アドレスによるトランスポートで HTTP アダプターを使用するようにこのポートを構成します。  
  
-   カナダの国コードの値 200 を持つ CBRApplication のメッセージをサブスクライブするフィルターを SendportCANOrders に追加します。  
  
-   カナダ ベースのメッセージを変換するための CBRApplication マップを SendportCANOrders の送信マップに追加します。  
  
## <a name="where-to-find-this-sample"></a>このサンプルの場所  
 このサンプルは、SDK がある次の場所にあります。  
  
 \<*パスのサンプル*\>\Admin\ExplorerOM\CBR  
  
 次の表は、このサンプルのファイルとその目的を示しています。  
  
|ファイル|Description|  
|---------------|-----------------|  
|ContentBasedRouting.cs|このサンプルに示されている操作の [!INCLUDE[btsVCSharp](../includes/btsvcsharp-md.md)] ソース ファイル。|  
|CBR.sln,CBR.csproj,CBR.suo|このサンプルのソリューション ファイルとプロジェクト ファイル。|  
  
## <a name="building-and-running-this-sample"></a>このサンプルのビルドおよび実行  
  
#### <a name="to-build-this-sample"></a>このサンプルをビルドするには  
  
1.  CBRSample をビルド、展開、および構成する手順が完了していることを確認します。 これらの手順で提供される[CBRSample (BizTalk Server サンプル)](../core/cbrsample-biztalk-server-sample.md)です。  
  
2.  [!INCLUDE[btsVStudioNoVersion](../includes/btsvstudionoversion-md.md)] で、ソリューション ファイル CBR.sln を開きます。  
  
3.  **[ビルド]** メニューの **[ソリューションのビルド]**をクリックします。  
  
#### <a name="to-run-this-sample"></a>このサンプルを実行するには  
  
1.  開く、[!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)]管理コンソールに移動して、 **CBRApplication**ノード。  
  
2.  展開して、 **CBRApplication**ことを確認するノード、**送信ポート**ノードが現在 CBRUSSendPort と CBRCANSendPort として記載されている 2 つのポートがします。  
  
3.  コマンド ウィンドウを開き、次のフォルダーに移動します。  
  
     \<*パスのサンプル*\>\Admin\ExplorerOM\CBR\bin\Debug  
  
4.  CBR.exe ファイルを実行します。  
  
5.  F5 キーを押して、[!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)]管理コンソールで表示するのには、**送信ポート**ノード。 このサンプルによって、2 つの新しいポートが CBRApplication に追加されています。 これらのポートは SendportUSOrders および SendportCANOrders です。  
  
## <a name="windows-powershell-script-example"></a>Windows PowerShell スクリプトの例  
 次の Windows PowerShell スクリプトを使用すると、 **ExplorerOM** クラスの同じ機能を実行できます。 ただし、ため、**追加**のメソッド、 **SendPort.OutboundTranforms**コレクションは内部でマークされている、 **ExplorerOM**アセンブリから直接呼び出すことができませんWindows PowerShell。 この Windows PowerShell スクリプトでは、Windows PowerShell から BizTalk WMI プロバイダーを使用して、送信変換マップを新しいポートに追加する方法を示します。  
  
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
  
 次に、Windows PowerShell スクリプトを実行して 2 つの新しいポートを作成した場合の出力例を示します。 新しいポートは、既に説明したとおり、[!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)] 管理コンソールでも確認できます。  
  
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
  
## <a name="see-also"></a>参照  
 [Admin ExplorerOM (BizTalk Server Samples フォルダ)](../core/admin-explorerom-biztalk-server-samples-folder.md)   
 [CBRSample (BizTalk Server サンプル)](../core/cbrsample-biztalk-server-sample.md)