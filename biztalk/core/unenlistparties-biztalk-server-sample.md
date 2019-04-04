---
title: UnenlistParties (BizTalk Server サンプル) |Microsoft Docs
ms.custom: ''
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: ''
ms.suite: ''
ms.tgt_pltfrm: ''
ms.topic: article
helpviewer_keywords:
- examples, parties
- parties, examples
- parties, unenlisting
- examples, administering
- administering, examples
ms.assetid: a751a0fc-ca94-4610-a8aa-db3a24159334
caps.latest.revision: 17
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: c7525e97ba93ebd35d2439044b8c1be55a70be3d
ms.sourcegitcommit: 266308ec5c6a9d8d80ff298ee6051b4843c5d626
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 06/27/2018
ms.locfileid: "36973027"
---
# <a name="unenlistparties-biztalk-server-sample"></a><span data-ttu-id="4d1f3-102">UnenlistParties (BizTalk Server サンプル)</span><span class="sxs-lookup"><span data-stu-id="4d1f3-102">UnenlistParties (BizTalk Server Sample)</span></span>
<span data-ttu-id="4d1f3-103">UnenlistParties サンプルは、展開された BizTalk Server アセンブリに関連付けられているすべてのパーティの参加を解除する方法を示しています。</span><span class="sxs-lookup"><span data-stu-id="4d1f3-103">The UnenlistParties sample demonstrates how to unenlist all of the parties associated with a deployed BizTalk Server assembly.</span></span>  
  
> [!WARNING]
>  <span data-ttu-id="4d1f3-104">展開スクリプトは、展開後に不要になった場合は、削除する必要があります。</span><span class="sxs-lookup"><span data-stu-id="4d1f3-104">Deployment scripts should be removed after deployment if not needed.</span></span> <span data-ttu-id="4d1f3-105">保持する必要のある管理スクリプトおよび他のスクリプトは、ACL によってセキュリティで保護し、厳重に監視する必要があります。</span><span class="sxs-lookup"><span data-stu-id="4d1f3-105">Administration scripts and other scripts that must remain should be secured by ACL’s and closely monitored.</span></span>  
  
## <a name="prerequisites"></a><span data-ttu-id="4d1f3-106">前提条件</span><span class="sxs-lookup"><span data-stu-id="4d1f3-106">Prerequisites</span></span>  
  
- <span data-ttu-id="4d1f3-107">このサンプルの管理オブジェクトを使用するには、[!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)] 管理者特権が必要です。</span><span class="sxs-lookup"><span data-stu-id="4d1f3-107">You must have [!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)] administrative privileges to use the administrative objects in this sample.</span></span>  
  
- <span data-ttu-id="4d1f3-108">Windows PowerShell スクリプトを実行するには、Windows PowerShell 実行ポリシーが必要です。</span><span class="sxs-lookup"><span data-stu-id="4d1f3-108">The Windows PowerShell script requires the Windows PowerShell execution policy to allow script execution.</span></span> <span data-ttu-id="4d1f3-109">詳細については、:[実行ポリシーの確認](http://go.microsoft.com/fwlink/?LinkId=128930)を参照してください。</span><span class="sxs-lookup"><span data-stu-id="4d1f3-109">For more information see: [Examining the Execution Policy](http://go.microsoft.com/fwlink/?LinkId=128930).</span></span>  
  
## <a name="how-this-sample-is-designed-and-why"></a><span data-ttu-id="4d1f3-110">このサンプルのデザイン方法とその理由</span><span class="sxs-lookup"><span data-stu-id="4d1f3-110">How This Sample is Designed and Why</span></span>  
 <span data-ttu-id="4d1f3-111">このサンプルは、BizTalk エクスプローラー オブジェクト モデルのオブジェクトを使用して Visual C# で記述されています。このサンプルは、以下の操作を実行します。</span><span class="sxs-lookup"><span data-stu-id="4d1f3-111">This sample, written in Visual C# using objects from the BizTalk Explorer object model, performs the following operations:</span></span>  
  
-   <span data-ttu-id="4d1f3-112">特定のアセンブリに対するクエリを実行します。</span><span class="sxs-lookup"><span data-stu-id="4d1f3-112">Query for a particular assembly.</span></span>  
  
-   <span data-ttu-id="4d1f3-113">アセンブリに関連付けられているすべてのロールを取得します。</span><span class="sxs-lookup"><span data-stu-id="4d1f3-113">Retrieve all of the roles associated with that assembly.</span></span>  
  
-   <span data-ttu-id="4d1f3-114">各ロールに関連付けられているすべてのパーティの参加を解除します。</span><span class="sxs-lookup"><span data-stu-id="4d1f3-114">Unenlist all of the parties associated with each such role.</span></span>  
  
-   <span data-ttu-id="4d1f3-115">意味のある情報がユーザーに返されるようにエラーを処理します。</span><span class="sxs-lookup"><span data-stu-id="4d1f3-115">Handle any errors such that meaningful information is returned to the user.</span></span>  
  
## <a name="where-to-find-this-sample"></a><span data-ttu-id="4d1f3-116">このサンプルの場所</span><span class="sxs-lookup"><span data-stu-id="4d1f3-116">Where to Find This Sample</span></span>  
 <span data-ttu-id="4d1f3-117">このサンプルは、SDK がある次の場所にあります。</span><span class="sxs-lookup"><span data-stu-id="4d1f3-117">The sample is located in the following SDK location:</span></span>  
  
 <span data-ttu-id="4d1f3-118">\<*パスのサンプル*\>\Admin\ExplorerOM\UnenlistParties\\</span><span class="sxs-lookup"><span data-stu-id="4d1f3-118">\<*Samples Path*\>\Admin\ExplorerOM\UnenlistParties\\</span></span>  
  
 <span data-ttu-id="4d1f3-119">次の表は、このサンプルのファイルとその目的を示しています。</span><span class="sxs-lookup"><span data-stu-id="4d1f3-119">The following table shows the files in this sample and describes their purpose.</span></span>  
  
|<span data-ttu-id="4d1f3-120">ファイル</span><span class="sxs-lookup"><span data-stu-id="4d1f3-120">File(s)</span></span>|<span data-ttu-id="4d1f3-121">説明</span><span class="sxs-lookup"><span data-stu-id="4d1f3-121">Description</span></span>|  
|---------------|-----------------|  
|<span data-ttu-id="4d1f3-122">App.ico、AssemblyInfo.cs、UnenlistParties.csproj、UnenlistParties.sln、UnenlistParties.cs</span><span class="sxs-lookup"><span data-stu-id="4d1f3-122">App.ico, AssemblyInfo.cs, UnenlistParties.csproj, UnenlistParties.sln, UnenlistParties.cs</span></span>|<span data-ttu-id="4d1f3-123">特定のアセンブリに対してすべてのパーティの参加を解除する Visual C# コマンド ライン アプリケーションを構築するためのプロジェクト、ソリューション、およびソース ファイル。</span><span class="sxs-lookup"><span data-stu-id="4d1f3-123">Project, solution, and source files for building a Visual C# command-line application that unenlists all of the parties for a particular assembly.</span></span>|  
  
### <a name="to-build-and-initialize-this-sample"></a><span data-ttu-id="4d1f3-124">このサンプルを作成および初期化するには</span><span class="sxs-lookup"><span data-stu-id="4d1f3-124">To build and initialize this sample</span></span>  
  
1. <span data-ttu-id="4d1f3-125">[!INCLUDE[btsVStudioNoVersion](../includes/btsvstudionoversion-md.md)] で、ソリューション ファイル UnenlistParties.sln を開きます。</span><span class="sxs-lookup"><span data-stu-id="4d1f3-125">In [!INCLUDE[btsVStudioNoVersion](../includes/btsvstudionoversion-md.md)], open the solution file UnenlistParties.sln.</span></span>  
  
2. <span data-ttu-id="4d1f3-126">**ビルド**メニューの **ソリューションのビルド**します。</span><span class="sxs-lookup"><span data-stu-id="4d1f3-126">In the **Build** menu, select **Build Solution**.</span></span>  
  
### <a name="to-run-this-sample"></a><span data-ttu-id="4d1f3-127">このサンプルを実行するには</span><span class="sxs-lookup"><span data-stu-id="4d1f3-127">To run this sample</span></span>  
  
1. <span data-ttu-id="4d1f3-128">コマンド ウィンドウで、次のフォルダーに移動します。</span><span class="sxs-lookup"><span data-stu-id="4d1f3-128">In a command window, navigate to the following folder:</span></span>  
  
    <span data-ttu-id="4d1f3-129">\<*パスのサンプル*\>\Admin\ExplorerOM\UnenlistParties\bin\Debug\\</span><span class="sxs-lookup"><span data-stu-id="4d1f3-129">\<*Samples Path*\>\Admin\ExplorerOM\UnenlistParties\bin\Debug\\</span></span>  
  
2. <span data-ttu-id="4d1f3-130">ファイル UnenlistParties.exe を実行し、次の 2 つのコマンド ライン引数のいずれかを渡します。</span><span class="sxs-lookup"><span data-stu-id="4d1f3-130">Run the file UnenlistParties.exe, passing one of the two following command-line arguments:</span></span>  
  
   - <span data-ttu-id="4d1f3-131">**\<** ***AssemblyName* \>** します。</span><span class="sxs-lookup"><span data-stu-id="4d1f3-131">**\<** ***AssemblyName* \>**.</span></span> <span data-ttu-id="4d1f3-132">すべての関連パーティの参加を解除するアセンブリの名前。</span><span class="sxs-lookup"><span data-stu-id="4d1f3-132">The name of an assembly from which all associated parties are to be unenlisted.</span></span> <span data-ttu-id="4d1f3-133">アセンブリ名に空白が含まれている場合は、名前を引用符で囲みます。</span><span class="sxs-lookup"><span data-stu-id="4d1f3-133">If the assembly name contains spaces, enclose the name in quotes.</span></span>  
  
   - <span data-ttu-id="4d1f3-134">**/?.**</span><span class="sxs-lookup"><span data-stu-id="4d1f3-134">**/?.**</span></span> <span data-ttu-id="4d1f3-135">ヘルプを表示します。</span><span class="sxs-lookup"><span data-stu-id="4d1f3-135">Displays help.</span></span>  
  
     <span data-ttu-id="4d1f3-136">以下に例を示します。</span><span class="sxs-lookup"><span data-stu-id="4d1f3-136">For example:</span></span>  
  
   ```  
   UnenlistParties "My BizTalk Assembly.dll"  
   ```  
  
    <span data-ttu-id="4d1f3-137">-または-</span><span class="sxs-lookup"><span data-stu-id="4d1f3-137">-OR-</span></span>  
  
   ```  
   UnenlistParties /?  
   ```  
  
## <a name="windows-powershell-script-example"></a><span data-ttu-id="4d1f3-138">Windows PowerShell スクリプトの例</span><span class="sxs-lookup"><span data-stu-id="4d1f3-138">Windows Powershell Script Example</span></span>  
 <span data-ttu-id="4d1f3-139">同じ機能を次の Windows Powershell スクリプト フラグメントを使用することができます、 **ExplorerOM**クラス。</span><span class="sxs-lookup"><span data-stu-id="4d1f3-139">The following Windows Powershell script fragment can be used to demonstrate the same features of the **ExplorerOM** classes:</span></span>  
  
```  
#===================#  
#=== Main Script ===#  
#===================#  
  
#=== Make sure the ExplorerOM assembly is loaded ===#  
  
[void] [System.reflection.Assembly]::LoadWithPartialName("Microsoft.BizTalk.ExplorerOM")  
  
#=== Connect to the BizTalk Management database ===#  
  
$Catalog = New-Object Microsoft.BizTalk.ExplorerOM.BtsCatalogExplorer  
$Catalog.ConnectionString = "SERVER=.;DATABASE=BizTalkMgmtDb;Integrated Security=SSPI"  
  
#=====================================================#  
#=== If no assembly name is specified, just list   ===#  
#=== the assemblies, roles and partyies enlisted.  ===#  
#=====================================================#  
  
if ($args[0] -eq $null)  
{  
  Write-Host `r`n===========================================================  
  Write-Host No assembly name provided for party unenlist operation.  
  Write-Host Listing Parties for each assembly on local BizTalk Server:  
  Write-Host ===========================================================`r`n  
  
  foreach ($assembly in $Catalog.Assemblies)  
  {  
    write-host $Assembly.Name`r`n  
  
    foreach ($role in $Assembly.Roles)  
    {  
      write-host `t($role.name)  
  
      foreach($party in $role.EnlistedParties)  
      {  
        Write-Host `t`t($party.Party.Name)  
      }  
      write-host  
    }  
  }  
  
  write-host  
}  
  
#=====================================================#  
#=== If assembly name is specified, remove parties ===#  
#=== enlisted in all roles for the assembly.       ===#  
#=====================================================#  
  
else  
{  
  $Assembly = $Catalog.Assemblies[$args[0]]  
  
  if ($assembly -eq $null)  
  {  
    write-host Assembly named $args[0] not found.`r`n  
  }   
  
  else  
  {  
    write-host `r`nUnenlisting parties from all roles in ($Assembly.Name)`r`n  
  
    foreach ($role in $Assembly.Roles)  
    {  
  
      $count = $role.EnlistedParties.count  
  
      for($c=0; $c -lt $count; $c++)  
      {  
        #==========================================================#  
        #=== Array index stays at zero because the collection   ===#  
        #=== changes after each item is removed.                ===#  
        #==========================================================#  
  
        $party = $role.EnlistedParties[0]  
  
        Write-Host Unenlisting ($party.Party.Name) from ($role.Name)...  
        $role.RemoveEnlistedParty($party)  
        Write-Host done.`r`n  
      }  
    }  
  
    write-Host Comitting changes...  
    $catalog.SaveChanges()  
    Write-Host done.`r`n  
  }  
}  
  
```  
  
 <span data-ttu-id="4d1f3-140">次のスクリプト出力は、PartyResolution サンプルの一部である Supplier アセンブリからパーティを参加解除したときに生成されました。</span><span class="sxs-lookup"><span data-stu-id="4d1f3-140">The following script output was generated from unenlisting parties from the Supplier assembly which is part of the PartyResolution sample.</span></span> <span data-ttu-id="4d1f3-141">PartyResolution サンプルが記載されています、 \<*サンプル パス*\>\Admin\Orchestrations\PartyResolution ディレクトリ。</span><span class="sxs-lookup"><span data-stu-id="4d1f3-141">The PartyResolution sample is located in the \<*Samples Path*\>\Admin\Orchestrations\PartyResolution directory.</span></span>  
  
```  
PS C:\> .\UnenlistParties.ps1 Supplier  
  
Unenlisting parties from all roles in Supplier  
  
Unenlisting ShipmentAgency1 from ShipmentRole ...  
done.  
  
Unenlisting ShipmentAgency2 from ShipmentRole ...  
done.  
  
Unenlisting BuyerAgency from Buyer ...  
done.  
  
Comitting changes...  
done.  
```  
  
## <a name="see-also"></a><span data-ttu-id="4d1f3-142">参照</span><span class="sxs-lookup"><span data-stu-id="4d1f3-142">See Also</span></span>  
 [<span data-ttu-id="4d1f3-143">Admin-ExplorerOM (BizTalk Server Samples フォルダー)</span><span class="sxs-lookup"><span data-stu-id="4d1f3-143">Admin-ExplorerOM (BizTalk Server Samples Folder)</span></span>](../core/admin-explorerom-biztalk-server-samples-folder.md)