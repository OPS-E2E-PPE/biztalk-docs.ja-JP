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
# <a name="deleteparty-biztalk-server-sample"></a>DeleteParty (BizTalk Server サンプル)
DeleteParty サンプルは、指定したパーティを削除する方法を示します。  
  
> [!WARNING]
>  展開スクリプトは、展開後に不要になった場合は、削除する必要があります。 保持する必要のある管理スクリプトおよび他のスクリプトは、ACL によってセキュリティで保護し、厳重に監視する必要があります。  
  
> [!NOTE]
>  パーティを削除する前に、パーティを作成する必要があります。 実行するがこれを行う方法の 1 つ、 [PartyResolution (BizTalk Server サンプル)](../core/partyresolution-biztalk-server-sample.md)サンプル。  
  
## <a name="prerequisites"></a>前提条件  
  
- このサンプルの管理オブジェクトを使用するには、[!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)] 管理者特権が必要です。  
  
- Windows PowerShell スクリプトを実行するには、Windows PowerShell 実行ポリシーが必要です。 詳細については、次を参照してください。:[実行ポリシーの確認](http://go.microsoft.com/fwlink/?LinkId=128930)します。  
  
## <a name="what-this-sample-does"></a>このサンプルの処理  
 このサンプルは、BizTalk エクスプローラー オブジェクト モデル (ExplorerOM) のオブジェクトを使用して Microsoft Visual C# で記述されており、以下の操作を実行します。  
  
-   指定したパーティをクエリします。  
  
-   そのパーティを削除します。  
  
-   意味のある情報がユーザーに返されるようにエラーを処理します。  
  
## <a name="where-to-find-this-sample"></a>このサンプルの場所  
 このサンプルは、次の SDK の場所にあります。  
  
 \<*パスのサンプル*\>\Admin\ExplorerOM\DeleteParty\  
  
 次の表は、このサンプルのファイルとその目的を示しています。  
  
|ファイル|説明|  
|---------------|-----------------|  
|App.ico、AssemblyInfo.cs、DeleteParty.csproj、DeleteParty.sln、DeleteParty.cs|指定したパーティを削除する Visual C# コマンド ライン アプリケーションを構築するためのプロジェクト、ソリューション、およびソース ファイル。|  
  
### <a name="to-build-and-initialize-this-sample"></a>このサンプルを作成および初期化するには  
  
1. [!INCLUDE[btsVStudioNoVersion](../includes/btsvstudionoversion-md.md)] で、ソリューション ファイル DeleteParty.sln を開きます。  
  
2. **[ビルド]** メニューの **[ソリューションのビルド]** をクリックします。  
  
### <a name="to-run-this-sample"></a>このサンプルを実行するには  
  
1. コマンド ウィンドウで、次のフォルダーに移動します。  
  
    \<*パスのサンプル*\>\Admin\ExplorerOM\DeleteParty\bin\Debug\  
  
2. ファイル DeleteParty.exe を実行し、次の 2 つのコマンド ライン引数の 1 つを渡します。  
  
   - **\<** ***PartyName* \>します。** 削除するパーティの名前。 パーティ名に空白が含まれている場合は、名前を引用符で囲みます。  
  
   - **/?.** ヘルプを表示します。  
  
     以下に例を示します。  
  
   ```  
   DeleteParty "My Party #3"  
   ```  
  
    -または-  
  
   ```  
   DeleteParty /?  
   ```  
  
## <a name="windows-powershell-script-example"></a>Windows Powershell スクリプトの例  
 同じ機能を次の Windows PowerShell スクリプト フラグメントを使用することができます、 **ExplorerOM**クラス。  
  
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
  
 スクリプト例では、コマンド ライン引数として単一のパーティ名が渡されることを想定しています。  そのパーティを名前で検索し、削除を試みます。  コマンド ライン引数が渡されない場合、ローカルの Biztalk Server にあるすべてのパーティの一覧が表示されます。 次に、スクリプトからの出力例を示します。  
  
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
  
## <a name="see-also"></a>参照  
 [Admin-ExplorerOM (BizTalk Server Samples フォルダー)](../core/admin-explorerom-biztalk-server-samples-folder.md)