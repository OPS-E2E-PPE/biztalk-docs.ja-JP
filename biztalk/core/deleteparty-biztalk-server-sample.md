---
title: DeleteParty (BizTalk Server サンプル) |Microsoft Docs
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
- deleting, parties
- examples, administering
- parties, deleting
- administering, examples
ms.assetid: 8161af7d-76ef-4df5-81c8-f0f5c81df9a8
caps.latest.revision: 16
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: a6d6d488bf7431f805e8719e10fe17cef7d13fa4
ms.sourcegitcommit: 266308ec5c6a9d8d80ff298ee6051b4843c5d626
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 06/27/2018
ms.locfileid: "36982963"
---
# <a name="deleteparty-biztalk-server-sample"></a><span data-ttu-id="597b9-102">DeleteParty (BizTalk Server サンプル)</span><span class="sxs-lookup"><span data-stu-id="597b9-102">DeleteParty (BizTalk Server Sample)</span></span>
<span data-ttu-id="597b9-103">DeleteParty サンプルは、指定したパーティを削除する方法を示します。</span><span class="sxs-lookup"><span data-stu-id="597b9-103">The DeleteParty sample demonstrates how to delete a specified party.</span></span>  
  
> [!WARNING]
>  <span data-ttu-id="597b9-104">展開スクリプトは、展開後に不要になった場合は、削除する必要があります。</span><span class="sxs-lookup"><span data-stu-id="597b9-104">Deployment scripts should be removed after deployment if not needed.</span></span> <span data-ttu-id="597b9-105">保持する必要のある管理スクリプトおよび他のスクリプトは、ACL によってセキュリティで保護し、厳重に監視する必要があります。</span><span class="sxs-lookup"><span data-stu-id="597b9-105">Administration scripts and other scripts that must remain should be secured by ACL’s and closely monitored.</span></span>  
  
> [!NOTE]
>  <span data-ttu-id="597b9-106">パーティを削除する前に、パーティを作成する必要があります。</span><span class="sxs-lookup"><span data-stu-id="597b9-106">Before you can delete a party, you must first create one.</span></span> <span data-ttu-id="597b9-107">実行するがこれを行う方法の 1 つ、 [PartyResolution (BizTalk Server サンプル)](../core/partyresolution-biztalk-server-sample.md)サンプル。</span><span class="sxs-lookup"><span data-stu-id="597b9-107">One way to do this is to run the [PartyResolution (BizTalk Server Sample)](../core/partyresolution-biztalk-server-sample.md) sample.</span></span>  
  
## <a name="prerequisites"></a><span data-ttu-id="597b9-108">前提条件</span><span class="sxs-lookup"><span data-stu-id="597b9-108">Prerequisites</span></span>  
  
- <span data-ttu-id="597b9-109">このサンプルの管理オブジェクトを使用するには、[!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)] 管理者特権が必要です。</span><span class="sxs-lookup"><span data-stu-id="597b9-109">You must have [!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)] administrative privileges to use the administrative objects in this sample.</span></span>  
  
- <span data-ttu-id="597b9-110">Windows PowerShell スクリプトを実行するには、Windows PowerShell 実行ポリシーが必要です。</span><span class="sxs-lookup"><span data-stu-id="597b9-110">The Windows PowerShell script requires the Windows PowerShell execution policy to allow script execution.</span></span> <span data-ttu-id="597b9-111">詳細については、:[実行ポリシーの確認](http://go.microsoft.com/fwlink/?LinkId=128930)を参照してください。</span><span class="sxs-lookup"><span data-stu-id="597b9-111">For more information see: [Examining the Execution Policy](http://go.microsoft.com/fwlink/?LinkId=128930).</span></span>  
  
## <a name="what-this-sample-does"></a><span data-ttu-id="597b9-112">このサンプルの処理</span><span class="sxs-lookup"><span data-stu-id="597b9-112">What This Sample Does</span></span>  
 <span data-ttu-id="597b9-113">このサンプルは、BizTalk エクスプローラー オブジェクト モデル (ExplorerOM) のオブジェクトを使用して Microsoft Visual C# で記述されており、以下の操作を実行します。</span><span class="sxs-lookup"><span data-stu-id="597b9-113">This sample, written in Microsoft Visual C#, using objects from the BizTalk Explorer object model (ExplorerOM), performs the following operations:</span></span>  
  
-   <span data-ttu-id="597b9-114">指定したパーティをクエリします。</span><span class="sxs-lookup"><span data-stu-id="597b9-114">Query for a specified party.</span></span>  
  
-   <span data-ttu-id="597b9-115">そのパーティを削除します。</span><span class="sxs-lookup"><span data-stu-id="597b9-115">Delete that party.</span></span>  
  
-   <span data-ttu-id="597b9-116">意味のある情報がユーザーに返されるようにエラーを処理します。</span><span class="sxs-lookup"><span data-stu-id="597b9-116">Handle any errors such that meaningful information is returned to the user.</span></span>  
  
## <a name="where-to-find-this-sample"></a><span data-ttu-id="597b9-117">このサンプルの場所</span><span class="sxs-lookup"><span data-stu-id="597b9-117">Where to Find This Sample</span></span>  
 <span data-ttu-id="597b9-118">このサンプルは、次の SDK の場所にあります。</span><span class="sxs-lookup"><span data-stu-id="597b9-118">This sample is located in the following SDK location:</span></span>  
  
 <span data-ttu-id="597b9-119">\<*パスのサンプル*\>\Admin\ExplorerOM\DeleteParty\\</span><span class="sxs-lookup"><span data-stu-id="597b9-119">\<*Samples Path*\>\Admin\ExplorerOM\DeleteParty\\</span></span>  
  
 <span data-ttu-id="597b9-120">次の表は、このサンプルのファイルとその目的を示しています。</span><span class="sxs-lookup"><span data-stu-id="597b9-120">The following table shows the files in this sample and describes their purpose.</span></span>  
  
|<span data-ttu-id="597b9-121">ファイル</span><span class="sxs-lookup"><span data-stu-id="597b9-121">File(s)</span></span>|<span data-ttu-id="597b9-122">説明</span><span class="sxs-lookup"><span data-stu-id="597b9-122">Description</span></span>|  
|---------------|-----------------|  
|<span data-ttu-id="597b9-123">App.ico、AssemblyInfo.cs、DeleteParty.csproj、DeleteParty.sln、DeleteParty.cs</span><span class="sxs-lookup"><span data-stu-id="597b9-123">App.ico, AssemblyInfo.cs, DeleteParty.csproj, DeleteParty.sln, DeleteParty.cs</span></span>|<span data-ttu-id="597b9-124">指定したパーティを削除する Visual C# コマンド ライン アプリケーションを構築するためのプロジェクト、ソリューション、およびソース ファイル。</span><span class="sxs-lookup"><span data-stu-id="597b9-124">Project, solution, and source files for building a Visual C# command-line application that removes a specified party.</span></span>|  
  
### <a name="to-build-and-initialize-this-sample"></a><span data-ttu-id="597b9-125">このサンプルを作成および初期化するには</span><span class="sxs-lookup"><span data-stu-id="597b9-125">To build and initialize this sample</span></span>  
  
1. <span data-ttu-id="597b9-126">[!INCLUDE[btsVStudioNoVersion](../includes/btsvstudionoversion-md.md)] で、ソリューション ファイル DeleteParty.sln を開きます。</span><span class="sxs-lookup"><span data-stu-id="597b9-126">In [!INCLUDE[btsVStudioNoVersion](../includes/btsvstudionoversion-md.md)], open the solution file DeleteParty.sln.</span></span>  
  
2. <span data-ttu-id="597b9-127">**[ビルド]** メニューの **[ソリューションのビルド]** をクリックします。</span><span class="sxs-lookup"><span data-stu-id="597b9-127">On the **Build** menu, click **Build Solution**.</span></span>  
  
### <a name="to-run-this-sample"></a><span data-ttu-id="597b9-128">このサンプルを実行するには</span><span class="sxs-lookup"><span data-stu-id="597b9-128">To run this sample</span></span>  
  
1. <span data-ttu-id="597b9-129">コマンド ウィンドウで、次のフォルダーに移動します。</span><span class="sxs-lookup"><span data-stu-id="597b9-129">In a command window, navigate to the following folder:</span></span>  
  
    <span data-ttu-id="597b9-130">\<*パスのサンプル*\>\Admin\ExplorerOM\DeleteParty\bin\Debug\\</span><span class="sxs-lookup"><span data-stu-id="597b9-130">\<*Samples Path*\>\Admin\ExplorerOM\DeleteParty\bin\Debug\\</span></span>  
  
2. <span data-ttu-id="597b9-131">ファイル DeleteParty.exe を実行し、次の 2 つのコマンド ライン引数の 1 つを渡します。</span><span class="sxs-lookup"><span data-stu-id="597b9-131">Run the file DeleteParty.exe, passing one of the two following command-line arguments:</span></span>  
  
   - <span data-ttu-id="597b9-132">**\<** ***PartyName* \>します。**</span><span class="sxs-lookup"><span data-stu-id="597b9-132">**\<** ***PartyName* \>.**</span></span> <span data-ttu-id="597b9-133">削除するパーティの名前。</span><span class="sxs-lookup"><span data-stu-id="597b9-133">The name of a party to be deleted.</span></span> <span data-ttu-id="597b9-134">パーティ名に空白が含まれている場合は、名前を引用符で囲みます。</span><span class="sxs-lookup"><span data-stu-id="597b9-134">If the party name contains spaces, enclose the name in quotes.</span></span>  
  
   - <span data-ttu-id="597b9-135">**/?.**</span><span class="sxs-lookup"><span data-stu-id="597b9-135">**/?.**</span></span> <span data-ttu-id="597b9-136">ヘルプを表示します。</span><span class="sxs-lookup"><span data-stu-id="597b9-136">Displays help.</span></span>  
  
     <span data-ttu-id="597b9-137">以下に例を示します。</span><span class="sxs-lookup"><span data-stu-id="597b9-137">For example:</span></span>  
  
   ```  
   DeleteParty "My Party #3"  
   ```  
  
    <span data-ttu-id="597b9-138">-または-</span><span class="sxs-lookup"><span data-stu-id="597b9-138">-OR-</span></span>  
  
   ```  
   DeleteParty /?  
   ```  
  
## <a name="windows-powershell-script-example"></a><span data-ttu-id="597b9-139">Windows Powershell スクリプトの例</span><span class="sxs-lookup"><span data-stu-id="597b9-139">Windows Powershell Script example</span></span>  
 <span data-ttu-id="597b9-140">同じ機能を次の Windows PowerShell スクリプト フラグメントを使用することができます、 **ExplorerOM**クラス。</span><span class="sxs-lookup"><span data-stu-id="597b9-140">The following Windows PowerShell script fragment can be used to demonstrate the same features of the **ExplorerOM** classes:</span></span>  
  
```  
  
#===================#  
#=== Main Script ===#  
#===================#  
  
#=== Make sure the ExplorerOM assembly is loaded ===#  
  
[void] [System.reflection.Assembly]::LoadWithPartialName("Microsoft.BizTalk.ExplorerOM")  
  
#=== Connect to the BizTalk Management database ===#  
  
$Catalog = New-Object Microsoft.BizTalk.ExplorerOM.BtsCatalogExplorer  
$Catalog.ConnectionString = "SERVER=.;DATABASE=BizTalkMgmtDb;Integrated Security=SSPI"  
  
#=======================================#  
#=== If no party name is specified   ===#  
#=== just list the parties.          ===#  
#=======================================#  
  
if ($args[0] -eq $null)  
{  
  Write-Host `r`nNo party name provided for delete operation.`r`n`r`nListing Parties on local Biztalk Server:  
  
  $Catalog.Parties | Format-List Name  
}  
  
#==========================================#  
#=== Delete the specified party by name ===#  
#==========================================#  
  
else  
{  
  $party = $Catalog.Parties[$args[0]]  
  Write-Host `r`nRemoving Party named `"($args[0])`"`r`n  
  $catalog.RemoveParty($party)  
  $catalog.SaveChanges()  
}  
```  
  
 <span data-ttu-id="597b9-141">スクリプト例では、コマンド ライン引数として単一のパーティ名が渡されることを想定しています。</span><span class="sxs-lookup"><span data-stu-id="597b9-141">The script example expects a single party name to be passed as a command line argument.</span></span>  <span data-ttu-id="597b9-142">そのパーティを名前で検索し、削除を試みます。</span><span class="sxs-lookup"><span data-stu-id="597b9-142">It looks for that party by name and attempts to delete it.</span></span>  <span data-ttu-id="597b9-143">コマンド ライン引数が渡されない場合、ローカルの Biztalk Server にあるすべてのパーティの一覧が表示されます。</span><span class="sxs-lookup"><span data-stu-id="597b9-143">The script will list all parties on the local Biztalk server if no commandline argument is passed to it.</span></span> <span data-ttu-id="597b9-144">次に、スクリプトからの出力例を示します。</span><span class="sxs-lookup"><span data-stu-id="597b9-144">Here is example output from the script:</span></span>  
  
```  
PS C:\> .\DeletePart.ps1  
  
No party name provided for delete operation.  
  
Listing Parties on local Biztalk Server:  
  
Name : Party1  
  
Name : Party3  
  
Name : Party2  
  
PS C:\> .\DeletePart.ps1 Party3  
  
Removing Party named " Party3 "  
  
PS C:\> .\DeletePart.ps1  
  
No party name provided for delete operation.  
  
Listing Parties on local Biztalk Server:  
  
Name : Party1  
  
Name : Party2  
  
```  
  
## <a name="see-also"></a><span data-ttu-id="597b9-145">参照</span><span class="sxs-lookup"><span data-stu-id="597b9-145">See Also</span></span>  
 [<span data-ttu-id="597b9-146">Admin-ExplorerOM (BizTalk Server Samples フォルダー)</span><span class="sxs-lookup"><span data-stu-id="597b9-146">Admin-ExplorerOM (BizTalk Server Samples Folder)</span></span>](../core/admin-explorerom-biztalk-server-samples-folder.md)