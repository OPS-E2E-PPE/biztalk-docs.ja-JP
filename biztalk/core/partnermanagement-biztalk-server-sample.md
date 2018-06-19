---
title: PartnerManagement (BizTalk Server サンプル) |Microsoft ドキュメント
ms.custom: ''
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: ''
ms.suite: ''
ms.tgt_pltfrm: ''
ms.topic: article
ms.assetid: 83e2a84f-ab25-4a7c-b8d7-0ba2dfa93095
caps.latest.revision: 12
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: c2ffc9e84e8c31ed1e1feb4c768498e817ad474c
ms.sourcegitcommit: 5abd0ed3f9e4858ffaaec5481bfa8878595e95f7
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 11/28/2017
ms.locfileid: "25973656"
---
# <a name="partnermanagement-biztalk-server-sample"></a>PartnerManagement (BizTalk Server サンプル)
PartnerManagement サンプルでパーティを管理する方法を示します、[!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)]環境を使用して、 **ExplorerOM**管理オブジェクト。  
  
## <a name="prerequisites"></a>前提条件  
  
-   このサンプルの管理オブジェクトを使用するには、[!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)] 管理者特権が必要です。  
  
-   Windows PowerShell スクリプトを実行するには、Windows PowerShell 実行ポリシーが必要です。 詳細については、「 [実行ポリシーの確認](http://go.microsoft.com/fwlink/?LinkId=128930)」を参照してください。  
  
## <a name="what-this-sample-does"></a>このサンプルの処理  
 このサンプルでは、管理クラスを使用して、 **Microsoft.BizTalk.ExplorerOM**パーティを管理する名前空間。 パーティは、ビジネス プロセスで操作できる取引先またはバックエンド アプリケーションを表します。 パーティの詳細についてはドキュメントを参照して一般に、[パーティ](../core/parties.md)または[ロール リンクとサービス リンク ロール](../core/role-links-and-service-link-roles.md)です。 サンプルは Microsoft [!INCLUDE[btsVCSharp](../includes/btsvcsharp-md.md)] で作成されています。 このトピックには、Windows PowerShell のスクリプト例も含まれています。 このサンプルは次の操作を示します。  
  
-   カスタム エイリアスまたは標準エイリアスを持つ新しいパーティを作成し、既存の [!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)] 送信ポートをパーティに追加する。  
  
-   既存のロール リンクを持つ新しいパーティを BizTalk Server に参加させる。  
  
-   新しいパーティを参加解除する。  
  
-   新しいパーティを削除する。  
  
## <a name="where-to-find-this-sample"></a>このサンプルの場所  
 このサンプルは、SDK がある次の場所にあります。  
  
 \<*パスのサンプル*\>\Admin\ExplorerOM\PartnerManagement  
  
 次の表は、このサンプルのファイルとその目的を示しています。  
  
|ファイル|Description|  
|---------------|-----------------|  
|PartnerManagement.cs|このサンプルに示されている操作の [!INCLUDE[btsVCSharp](../includes/btsvcsharp-md.md)] ソース ファイル。|  
|PartnerManagement.sln と PartnerManagement.csproj|このサンプルのソリューション ファイルとプロジェクト ファイル。|  
  
## <a name="building-and-running-this-sample"></a>このサンプルのビルドおよび実行  
 サンプルをビルドする前に、コードを 4 か所で変更し、BizTalk Server のサンプルをカスタマイズする必要があります。 これは、サンプルではパーティに関連付けられた送信ポートと参加のロールに任意の名前を使用しているためです。 したがって、サンプルに有効な名前を指定する必要があります。 このサンプルを示すためには、このトピックの内容について説明します最初に、次のディレクトリから PartyResolution サンプルのビルド: \<*サンプル パス*\>\Orchestrations\PartyResolution。 この方法を使用するのは、有効なロール名と送信ポート名が BizTalk Server に存在することを確認し、サンプルの手順を示すことができるようにするためです。  
  
#### <a name="to-build-this-sample"></a>このサンプルをビルドするには  
  
1.  最初に、有効なロール名と送信ポート名をサンプルで使用できるよう、PartyResolution サンプルがビルドされ初期化されていることを確認します。 これがで「ビルドおよび初期化してこのサンプルの」というタイトルのセクションに記載されている[PartyResolution (BizTalk Server サンプル)](../core/partyresolution-biztalk-server-sample.md)です。  
  
2.  [!INCLUDE[btsVStudioNoVersion](../includes/btsvstudionoversion-md.md)] で、ソリューション ファイル PartnerManagement.sln を開きます。  
  
3.  ソリューション エクスプローラーでソース ファイル PartnerManagement.cs を開きます。  
  
4.  という名前の関数までスクロール**CreateParty**と 2 つの送信ポート名、PartyResolution からサンプルまたは、BizTalk server 環境から有効な名前を使用して挿入します。 次のコード例では、PartyResolution サンプルの送信ポートを使用する変更を示しています。  
  
    ```  
    // Replacing arbitrary send port names with PartyResolution send port names ===  
  
    //            myParty.SendPorts.Add(catalog.SendPorts["NormalDelivery"]);  
    //            myParty.SendPorts.Add(catalog.SendPorts["ExpressDelivery"]);  
                myParty.SendPorts.Add(catalog.SendPorts["SP_FilesToShipmentAgency1"]);  
                myParty.SendPorts.Add(catalog.SendPorts["SP_FilesToShipmentAgency2"]);  
  
    ```  
  
5.  という名前の関数までスクロール**EnlistParty** "shipmentrole"ロールの Supplier アセンブリを検索するように、foreach ループを変更し、参加リストで使用します。 次のコード例では、PartyResolution サンプルの ShipmentRole を使用する変更を示しています。  
  
    ```  
                // Search for the “Shipmentrole” instead of “shipperRole”  
                Role svcRole = null;  
    //===       foreach (Role role in catalog.Assemblies[0].Roles)  
                foreach (Role role in catalog.Assemblies["Supplier"].Roles)  
                {  
    //===          if (role.Name == "ShipperRole")  
                   if (role.Name == "ShipmentRole")  
                   {  
                      svcRole = role;  
                      break;  
                   }  
                }  
  
    ```  
  
6.  という名前の関数までスクロール**UnenlistParty** ShipmentRole の Supplier アセンブリを検索する foreach ループを変更します。 次のコード例に、この変更を示します。  
  
    ```  
                // Search for the “ShipmentRole” instead of “shipperRole”  
                Role svcRole = null;  
    //===       foreach (Role role in catalog.Assemblies[0].Roles)  
                foreach (Role role in catalog.Assemblies["Supplier"].Roles)  
                {  
    //===          if (role.Name == "ShipperRole")  
                   if (role.Name == "ShipmentRole")  
                   {  
                      svcRole = role;  
                      break;  
                   }  
                }  
  
    ```  
  
7.  ShipmentRole を持つ新しいパーティを作成し、参加させた後、サンプルはすぐにパーティを参加解除し削除するようデザインされています。 メイン プロシージャに次のコード変更を追加して実行を一時停止し、[!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)] 管理コンソールで新しいパーティに作成した参加を表示できるようにします。  
  
    ```  
    static void Main(string[] args)  
    {  
       CreateParty();     
       EnlistParty();     
  
       Console.WriteLine("\nNew Party created and enlisted.\n\nPress <Enter> to unenlist and delete.\n");  
       Console.ReadLine();  
  
       UnenlistParty();   
       DeleteParty();  
    }  
  
    ```  
  
8.  **[ビルド]** メニューの **[ソリューションのビルド]** をクリックします。  
  
#### <a name="to-run-this-sample"></a>このサンプルを実行するには  
  
1.  コマンド ウィンドウを開き、次のフォルダーに移動します。  
  
     \<*パスのサンプル*\>\Admin\ExplorerOM\PartnerManagement\bin\Debug  
  
2.  PartnerManagement.exe ファイルを実行します。  
  
3.  サンプルには、新しいパーティが作成され、参加しているメッセージが表示されたら、開く、[!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)]新しいパーティがという名前の管理コンソールとビュー **FedEx**下にある、**パーティ**ノード。  
  
4.  [!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)]管理コンソールで、ツリー ビューを移動、 **ShipmentRole**  **Applications\BizTalk Application 1 \role Links**です。 ダブルクリックして**ShipmentRole**と**ShipmentAgency1**にマップされている、 **SupplierAdvice**操作と**ShipmentAgency2**マップされている、 **SupplierOrder**参加で操作します。  
  
5.  コマンド ウィンドウで Enter キーを押すと、サンプルを参加解除し削除できます。  
  
6.  [!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)]管理コンソールで、パーティがからできなかったことを確認、 **ShipmentRole**から削除し、**パーティ**ノード。  
  
## <a name="windows-powershell-script-example"></a>Windows PowerShell スクリプトの例  
 次の Windows PowerShell スクリプトの例は、の同じ機能を示すために使用できます、 **ExplorerOM**クラス。  
  
```  
#===============================================================#  
#===                                                         ===#  
#=== Create a new party named "FedEx" as an example.         ===#  
#===                                                         ===#  
#=== Two Shipment agency send ports from the PartyResolution ===#  
#=== sample will be added to the party.                      ===#  
#===                                                         ===#  
#===============================================================#  
Function CreateParty  
{  
  #=== Create a party =====================#  
  $myParty = $Catalog.AddNewParty()  
  $myParty.Name = "FedEx"  
  
  #=== create a standard alias ==========================#  
  $standardAlias = $myParty.AddNewAlias()  
  $standardAlias.Name = "D-U-N-S (Dun & Bradstreet)"  
  $standardAlias.Value = "Value1"  
  
  #=== Create a custom alias ==================#  
  $customAlias = $myParty.AddNewAlias()  
  $customAlias.Name = "Telephone"  
  $customAlias.Qualifier = "100"  
  $customAlias.Value = "4255550234"  
  
  #=== Add party send ports =====================================================#  
  
  #===============================================================#  
  #=== Have to use IList directly on this sendports collection ===#  
  #=== to work around a PowerShell issue.                      ===#  
  #===============================================================#  
  $iList = [System.Collections.IList]  
  
  $sendport1 = $Catalog.SendPorts["SP_FilesToShipmentAgency1"]  
  [void] $iList.GetMethod("Add").Invoke($myParty.SendPorts,$sendport1)  
  
  $sendport2 = $Catalog.SendPorts["SP_FilesToShipmentAgency2"]  
  [void] $iList.GetMethod("Add").Invoke($myParty.SendPorts,$sendport2)  
  
  #=== Specify a signature certificate, make sure the certificate is available ===#  
  #=== in the AddressBook store of the Local Machine                           ===#  
  
  foreach ($certificate in $Catalog.Certificates)  
  {  
    if ($certificate.ShortName -eq "BR, Certisign Certificadora Digital Ltda., Certisign - Autoridade Certificadora - AC2")  
    {  
      $myParty.SignatureCert = $certificate  
    }  
  }  
  
  #=== Commit the changes ===#  
  $catalog.SaveChanges()  
}  
  
#===============================================================#  
#===                                                         ===#  
#=== Delete the party named "FedEx"                          ===#  
#===                                                         ===#  
#===============================================================#  
Function DeleteParty  
{  
  $Catalog.RemoveParty($Catalog.Parties["FedEx"])  
  
  #=== Commit the changes ===#  
  $catalog.SaveChanges()  
}  
  
#===============================================================#  
#===                                                         ===#  
#=== Enlist the "FedEx" party with the "ShipmentRole"        ===#  
#===                                                         ===#  
#===============================================================#  
Function EnlistParty  
{  
  $myParty = $Catalog.Parties["FedEx"]  
  
  #=== Get the "ShipmentRole" in the Supplier assembly.        ===#  
  $svcRole = $Catalog.Assemblies["Supplier"].Roles["ShipmentRole"]  
  
  #=== Enlist the party under the shipper role ===#  
  $enlistedParty = $svcRole.AddNewEnlistedParty($myParty)  
  
  #===============================================================#  
  #=== Have to use IList directly on this sendports collection ===#  
  #=== to work around a PowerShell issue.                      ===#  
  #===============================================================#  
  $iList = [System.Collections.IList]   
  
  #===============================================================#  
  #=== Example port to be used for the role's "SupplierAdvice" ===#  
  #=== operation.                                              ===#  
  #=== Using the first send port added to the new party which  ===#  
  #=== is "SP_FilesToShipmentAgency1" at index 0 in the        ===#  
  #=== sendports collection.                                   ===#  
  #===============================================================#  
  $enlistedParty.Mappings[0].SendPort = $iList.GetProperty("Item").GetValue($myParty.SendPorts,0)  
  
  #===============================================================#  
  #=== Example port to be used for the role's "SupplierOrder"  ===#  
  #=== operation.                                              ===#  
  #=== Using the second send port added to the new party which ===#  
  #=== is "SP_FilesToShipmentAgency2" at index 1 in the        ===#  
  #=== sendports collection.                                   ===#  
  #===============================================================#  
  $enlistedParty.Mappings[1].SendPort = $iList.GetProperty("Item").GetValue($myParty.SendPorts,1)  
  
  #=== Commit the changes ===#  
  $Catalog.SaveChanges()  
}  
  
#===============================================================#  
#===                                                         ===#  
#=== Unenlist the "FedEx" party from the ShipmentRole        ===#  
#===                                                         ===#  
#===============================================================#  
Function UnenlistParty  
{  
  #=== Get the "ShipmentRole" from the Supplier assembly. ===#  
  $svcRole = $Catalog.Assemblies["Supplier"].Roles["ShipmentRole"]  
  
  #=== Remove the "FedEx" party ===#  
  foreach ($enlistedparty in $svcRole.EnlistedParties)  
  {  
    if ($enlistedparty.Party.Name -eq "FedEx")  
    {  
      $svcRole.RemoveEnlistedParty($enlistedparty)  
      break  
    }  
  }  
  
  #=== Commit the changes ===#  
  $Catalog.SaveChanges()  
}  
  
#===================#  
#=== Main Script ===#  
#===================#  
  
#=== Make sure the ExplorerOM assembly is loaded ===#  
  
[void] [System.reflection.Assembly]::LoadWithPartialName("Microsoft.BizTalk.ExplorerOM")  
  
#=== Connect to the BizTalk Management database ===#  
  
$Catalog = New-Object Microsoft.BizTalk.ExplorerOM.BtsCatalogExplorer  
$Catalog.ConnectionString = "SERVER=.;DATABASE=BizTalkMgmtDb;Integrated Security=SSPI"  
  
#=== This sample expects the PartyResolution sample to be built and deployed  ===#  
#=== to the BizTalk Server.                                                   ===#  
  
write-host `r`nMake sure the "PartyResolution" sample application from the Orchestrations   
write-host sample directory is deployed and running.  
write-host By default it will be listed in the BizTalk Server Administration Console  
write-host with the application name: `"BizTalk.Application.1`"`r`n  
  
$SupplierAssembly = $Catalog.Assemblies["Supplier"]  
  
#==================================================================#  
#=== Register a trap handler to discard changes on exceptions   ===#  
#=== Execution will continue in the event we want to unenlist,  ===#  
#=== and delete the party.                                      ===#  
#==================================================================#  
  
$Script:NoExceptionOccurred = $true  
$ErrorActionPreference="silentlycontinue"  
trap   
{   
  $Script:NoExceptionOccurred = $false  
  "Exception encountered:`r`n"; $_; "`r`nDiscarding Changes and continuing execution so we can attempt to clean up the party...`r`n"  
  $Catalog.DiscardChanges()  
}  
  
CreateParty  
EnlistParty  
  
if ($Script:NoExceptionOccurred)  
{  
  Write-Host "`r`nExample Party `"FedEx`" should be created and enlisted with the `"ShipmentRole`".`r`n"  
  Write-Host You can view the results in the BizTalk Server Administration console.`r`n  
  Write-Host "Press <Enter> to unenlist and delete...`r`n"  
  Read-Host  
}  
  
UnenlistParty  
DeleteParty  
  
```  
  
 次に、PowerShell スクリプト例の実行による出力の例を示します。 スクリプトの実行が失敗した場合、PowerShell スクリプトがこのトピックの先頭にある要件の説明に従って有効になっていることを確認してください。  
  
```  
PS C:\> .\PartnerManagement.ps1  
  
Make sure the PartyResolution sample application from the Orchestrations  
sample directory is deployed and running.  
By default it will be listed in the BizTalk Server Administration Console  
with the application name: "BizTalk.Application.1"  
  
Example Party "FedEx" should be created and enlisted with the "ShipmentRole".  
  
You can view the results in the BizTalk Server Administration console.  
  
Press <Enter> to unenlist and delete...  
```  
  
## <a name="see-also"></a>参照  
 [パーティ](../core/parties.md)   
 [ロール リンクとサービス リンク ロール](../core/role-links-and-service-link-roles.md)   
 [Admin (BizTalk Server Samples フォルダー)](../core/admin-biztalk-server-samples-folder.md)