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
# <a name="partnermanagement-biztalk-server-sample"></a><span data-ttu-id="48d63-102">PartnerManagement (BizTalk Server サンプル)</span><span class="sxs-lookup"><span data-stu-id="48d63-102">PartnerManagement (BizTalk Server Sample)</span></span>
<span data-ttu-id="48d63-103">PartnerManagement サンプルでパーティを管理する方法を示します、[!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)]環境を使用して、 **ExplorerOM**管理オブジェクト。</span><span class="sxs-lookup"><span data-stu-id="48d63-103">The PartnerManagement sample demonstrates how to manage parties in the [!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)] environment by using the **ExplorerOM** administration objects.</span></span>  
  
## <a name="prerequisites"></a><span data-ttu-id="48d63-104">前提条件</span><span class="sxs-lookup"><span data-stu-id="48d63-104">Prerequisites</span></span>  
  
-   <span data-ttu-id="48d63-105">このサンプルの管理オブジェクトを使用するには、[!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)] 管理者特権が必要です。</span><span class="sxs-lookup"><span data-stu-id="48d63-105">You must have [!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)] administrative privileges to use the administrative objects in this sample.</span></span>  
  
-   <span data-ttu-id="48d63-106">Windows PowerShell スクリプトを実行するには、Windows PowerShell 実行ポリシーが必要です。</span><span class="sxs-lookup"><span data-stu-id="48d63-106">The Windows PowerShell script requires the Windows PowerShell execution policy to allow script execution.</span></span> <span data-ttu-id="48d63-107">詳細については、「 [実行ポリシーの確認](http://go.microsoft.com/fwlink/?LinkId=128930)」を参照してください。</span><span class="sxs-lookup"><span data-stu-id="48d63-107">For more information see [Examining the Execution Policy](http://go.microsoft.com/fwlink/?LinkId=128930).</span></span>  
  
## <a name="what-this-sample-does"></a><span data-ttu-id="48d63-108">このサンプルの処理</span><span class="sxs-lookup"><span data-stu-id="48d63-108">What This Sample Does</span></span>  
 <span data-ttu-id="48d63-109">このサンプルでは、管理クラスを使用して、 **Microsoft.BizTalk.ExplorerOM**パーティを管理する名前空間。</span><span class="sxs-lookup"><span data-stu-id="48d63-109">This sample demonstrates using the administrative classes from the **Microsoft.BizTalk.ExplorerOM** namespace to manage parties.</span></span> <span data-ttu-id="48d63-110">パーティは、ビジネス プロセスで操作できる取引先またはバックエンド アプリケーションを表します。</span><span class="sxs-lookup"><span data-stu-id="48d63-110">Parties represent trading partners or back-end applications with which a business process can interact.</span></span> <span data-ttu-id="48d63-111">パーティの詳細についてはドキュメントを参照して一般に、[パーティ](../core/parties.md)または[ロール リンクとサービス リンク ロール](../core/role-links-and-service-link-roles.md)です。</span><span class="sxs-lookup"><span data-stu-id="48d63-111">For more information about parties in general, see the documentation for [Parties](../core/parties.md) or [Role Links and Service Link Roles](../core/role-links-and-service-link-roles.md).</span></span> <span data-ttu-id="48d63-112">サンプルは Microsoft [!INCLUDE[btsVCSharp](../includes/btsvcsharp-md.md)] で作成されています。</span><span class="sxs-lookup"><span data-stu-id="48d63-112">The sample is written in Microsoft [!INCLUDE[btsVCSharp](../includes/btsvcsharp-md.md)].</span></span> <span data-ttu-id="48d63-113">このトピックには、Windows PowerShell のスクリプト例も含まれています。</span><span class="sxs-lookup"><span data-stu-id="48d63-113">A Windows PowerShell example script is also included in this topic.</span></span> <span data-ttu-id="48d63-114">このサンプルは次の操作を示します。</span><span class="sxs-lookup"><span data-stu-id="48d63-114">The sample demonstrates the following operations:</span></span>  
  
-   <span data-ttu-id="48d63-115">カスタム エイリアスまたは標準エイリアスを持つ新しいパーティを作成し、既存の [!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)] 送信ポートをパーティに追加する。</span><span class="sxs-lookup"><span data-stu-id="48d63-115">Creating a new party with a custom or standard alias and adding existing [!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)] send ports to the party.</span></span>  
  
-   <span data-ttu-id="48d63-116">既存のロール リンクを持つ新しいパーティを BizTalk Server に参加させる。</span><span class="sxs-lookup"><span data-stu-id="48d63-116">Enlisting the new party with an existing role link on the BizTalk server.</span></span>  
  
-   <span data-ttu-id="48d63-117">新しいパーティを参加解除する。</span><span class="sxs-lookup"><span data-stu-id="48d63-117">Un-enlisting the new party.</span></span>  
  
-   <span data-ttu-id="48d63-118">新しいパーティを削除する。</span><span class="sxs-lookup"><span data-stu-id="48d63-118">Deleting the new party.</span></span>  
  
## <a name="where-to-find-this-sample"></a><span data-ttu-id="48d63-119">このサンプルの場所</span><span class="sxs-lookup"><span data-stu-id="48d63-119">Where To Find This Sample</span></span>  
 <span data-ttu-id="48d63-120">このサンプルは、SDK がある次の場所にあります。</span><span class="sxs-lookup"><span data-stu-id="48d63-120">The sample is located in the following SDK location:</span></span>  
  
 <span data-ttu-id="48d63-121">\<*パスのサンプル*\>\Admin\ExplorerOM\PartnerManagement</span><span class="sxs-lookup"><span data-stu-id="48d63-121">\<*Samples Path*\>\Admin\ExplorerOM\PartnerManagement</span></span>  
  
 <span data-ttu-id="48d63-122">次の表は、このサンプルのファイルとその目的を示しています。</span><span class="sxs-lookup"><span data-stu-id="48d63-122">The following table shows the files in this sample and describes their purpose.</span></span>  
  
|<span data-ttu-id="48d63-123">ファイル</span><span class="sxs-lookup"><span data-stu-id="48d63-123">File(s)</span></span>|<span data-ttu-id="48d63-124">Description</span><span class="sxs-lookup"><span data-stu-id="48d63-124">Description</span></span>|  
|---------------|-----------------|  
|<span data-ttu-id="48d63-125">PartnerManagement.cs</span><span class="sxs-lookup"><span data-stu-id="48d63-125">PartnerManagement.cs</span></span>|<span data-ttu-id="48d63-126">このサンプルに示されている操作の [!INCLUDE[btsVCSharp](../includes/btsvcsharp-md.md)] ソース ファイル。</span><span class="sxs-lookup"><span data-stu-id="48d63-126">[!INCLUDE[btsVCSharp](../includes/btsvcsharp-md.md)] source file for operations demonstrated in this sample.</span></span>|  
|<span data-ttu-id="48d63-127">PartnerManagement.sln と PartnerManagement.csproj</span><span class="sxs-lookup"><span data-stu-id="48d63-127">PartnerManagement.sln and PartnerManagement.csproj</span></span>|<span data-ttu-id="48d63-128">このサンプルのソリューション ファイルとプロジェクト ファイル。</span><span class="sxs-lookup"><span data-stu-id="48d63-128">Solution and project files for the sample.</span></span>|  
  
## <a name="building-and-running-this-sample"></a><span data-ttu-id="48d63-129">このサンプルのビルドおよび実行</span><span class="sxs-lookup"><span data-stu-id="48d63-129">Building and Running This Sample</span></span>  
 <span data-ttu-id="48d63-130">サンプルをビルドする前に、コードを 4 か所で変更し、BizTalk Server のサンプルをカスタマイズする必要があります。</span><span class="sxs-lookup"><span data-stu-id="48d63-130">Before you build the sample, you need to make four code modifications to customize the sample for the BizTalk server.</span></span> <span data-ttu-id="48d63-131">これは、サンプルではパーティに関連付けられた送信ポートと参加のロールに任意の名前を使用しているためです。</span><span class="sxs-lookup"><span data-stu-id="48d63-131">This is necessary because the sample uses arbitrary names for send ports associated with the party and an arbitrary role name for the enlistment.</span></span> <span data-ttu-id="48d63-132">したがって、サンプルに有効な名前を指定する必要があります。</span><span class="sxs-lookup"><span data-stu-id="48d63-132">Therefore you need to provide valid names to the sample.</span></span> <span data-ttu-id="48d63-133">このサンプルを示すためには、このトピックの内容について説明します最初に、次のディレクトリから PartyResolution サンプルのビルド: \<*サンプル パス*\>\Orchestrations\PartyResolution。</span><span class="sxs-lookup"><span data-stu-id="48d63-133">To demonstrate this sample, this topic describes first building the PartyResolution sample from the following directory: \<*Samples Path*\>\Orchestrations\PartyResolution.</span></span> <span data-ttu-id="48d63-134">この方法を使用するのは、有効なロール名と送信ポート名が BizTalk Server に存在することを確認し、サンプルの手順を示すことができるようにするためです。</span><span class="sxs-lookup"><span data-stu-id="48d63-134">This approach is used to make sure a valid role name and send port names are present on the BizTalk server to demonstrate the sample procedures.</span></span>  
  
#### <a name="to-build-this-sample"></a><span data-ttu-id="48d63-135">このサンプルをビルドするには</span><span class="sxs-lookup"><span data-stu-id="48d63-135">To build this sample</span></span>  
  
1.  <span data-ttu-id="48d63-136">最初に、有効なロール名と送信ポート名をサンプルで使用できるよう、PartyResolution サンプルがビルドされ初期化されていることを確認します。</span><span class="sxs-lookup"><span data-stu-id="48d63-136">First make sure the PartyResolution sample has been built and initialized so that a valid role name and send port names can be used by the sample.</span></span> <span data-ttu-id="48d63-137">これがで「ビルドおよび初期化してこのサンプルの」というタイトルのセクションに記載されている[PartyResolution (BizTalk Server サンプル)](../core/partyresolution-biztalk-server-sample.md)です。</span><span class="sxs-lookup"><span data-stu-id="48d63-137">This is documented in the section entitled “Building and Initializing This Sample” in  [PartyResolution (BizTalk Server Sample)](../core/partyresolution-biztalk-server-sample.md).</span></span>  
  
2.  <span data-ttu-id="48d63-138">[!INCLUDE[btsVStudioNoVersion](../includes/btsvstudionoversion-md.md)] で、ソリューション ファイル PartnerManagement.sln を開きます。</span><span class="sxs-lookup"><span data-stu-id="48d63-138">In [!INCLUDE[btsVStudioNoVersion](../includes/btsvstudionoversion-md.md)], open the solution file PartnerManagement.sln.</span></span>  
  
3.  <span data-ttu-id="48d63-139">ソリューション エクスプローラーでソース ファイル PartnerManagement.cs を開きます。</span><span class="sxs-lookup"><span data-stu-id="48d63-139">In Solution Explorer, open the source file PartnerManagement.cs.</span></span>  
  
4.  <span data-ttu-id="48d63-140">という名前の関数までスクロール**CreateParty**と 2 つの送信ポート名、PartyResolution からサンプルまたは、BizTalk server 環境から有効な名前を使用して挿入します。</span><span class="sxs-lookup"><span data-stu-id="48d63-140">Scroll down into the function named **CreateParty** and insert the two send port names from the PartyResolution sample or use valid names from the BizTalk server environment.</span></span> <span data-ttu-id="48d63-141">次のコード例では、PartyResolution サンプルの送信ポートを使用する変更を示しています。</span><span class="sxs-lookup"><span data-stu-id="48d63-141">The following code example demonstrates the change using the send ports from the PartyResolution sample.</span></span>  
  
    ```  
    // Replacing arbitrary send port names with PartyResolution send port names ===  
  
    //            myParty.SendPorts.Add(catalog.SendPorts["NormalDelivery"]);  
    //            myParty.SendPorts.Add(catalog.SendPorts["ExpressDelivery"]);  
                myParty.SendPorts.Add(catalog.SendPorts["SP_FilesToShipmentAgency1"]);  
                myParty.SendPorts.Add(catalog.SendPorts["SP_FilesToShipmentAgency2"]);  
  
    ```  
  
5.  <span data-ttu-id="48d63-142">という名前の関数までスクロール**EnlistParty** "shipmentrole"ロールの Supplier アセンブリを検索するように、foreach ループを変更し、参加リストで使用します。</span><span class="sxs-lookup"><span data-stu-id="48d63-142">Scroll down into the function named **EnlistParty** and change the foreach loop so that it searches the Supplier assembly for a role named “ShipmentRole” to use with the enlistment.</span></span> <span data-ttu-id="48d63-143">次のコード例では、PartyResolution サンプルの ShipmentRole を使用する変更を示しています。</span><span class="sxs-lookup"><span data-stu-id="48d63-143">The following code example demonstrates the change to use the ShipmentRole from the PartyResolution sample.</span></span>  
  
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
  
6.  <span data-ttu-id="48d63-144">という名前の関数までスクロール**UnenlistParty** ShipmentRole の Supplier アセンブリを検索する foreach ループを変更します。</span><span class="sxs-lookup"><span data-stu-id="48d63-144">Scroll down into the function named **UnenlistParty** and change the foreach loop to search the Supplier assembly for the ShipmentRole.</span></span> <span data-ttu-id="48d63-145">次のコード例に、この変更を示します。</span><span class="sxs-lookup"><span data-stu-id="48d63-145">The following code example demonstrates this change.</span></span>  
  
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
  
7.  <span data-ttu-id="48d63-146">ShipmentRole を持つ新しいパーティを作成し、参加させた後、サンプルはすぐにパーティを参加解除し削除するようデザインされています。</span><span class="sxs-lookup"><span data-stu-id="48d63-146">After creating and enlisting the new party with the ShipmentRole, the sample is designed to immediately un-enlist the party and delete it.</span></span> <span data-ttu-id="48d63-147">メイン プロシージャに次のコード変更を追加して実行を一時停止し、[!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)] 管理コンソールで新しいパーティに作成した参加を表示できるようにします。</span><span class="sxs-lookup"><span data-stu-id="48d63-147">Add the following code change to the main procedure to pause execution and allow you to view the created enlistment for the new party in the [!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)] Administration console.</span></span>  
  
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
  
8.  <span data-ttu-id="48d63-148">**[ビルド]** メニューの **[ソリューションのビルド]** をクリックします。</span><span class="sxs-lookup"><span data-stu-id="48d63-148">On the **Build** menu, click **Build Solution**.</span></span>  
  
#### <a name="to-run-this-sample"></a><span data-ttu-id="48d63-149">このサンプルを実行するには</span><span class="sxs-lookup"><span data-stu-id="48d63-149">To run this sample</span></span>  
  
1.  <span data-ttu-id="48d63-150">コマンド ウィンドウを開き、次のフォルダーに移動します。</span><span class="sxs-lookup"><span data-stu-id="48d63-150">Open a command window and navigate to the following folder:</span></span>  
  
     <span data-ttu-id="48d63-151">\<*パスのサンプル*\>\Admin\ExplorerOM\PartnerManagement\bin\Debug</span><span class="sxs-lookup"><span data-stu-id="48d63-151">\<*Samples Path*\>\Admin\ExplorerOM\PartnerManagement\bin\Debug</span></span>  
  
2.  <span data-ttu-id="48d63-152">PartnerManagement.exe ファイルを実行します。</span><span class="sxs-lookup"><span data-stu-id="48d63-152">Run the file PartnerManagement.exe.</span></span>  
  
3.  <span data-ttu-id="48d63-153">サンプルには、新しいパーティが作成され、参加しているメッセージが表示されたら、開く、[!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)]新しいパーティがという名前の管理コンソールとビュー **FedEx**下にある、**パーティ**ノード。</span><span class="sxs-lookup"><span data-stu-id="48d63-153">When the sample displays the message that the new party is created and enlisted, open the [!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)] Administration console and view the new party named **FedEx** under the **Parties** node.</span></span>  
  
4.  <span data-ttu-id="48d63-154">[!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)]管理コンソールで、ツリー ビューを移動、 **ShipmentRole**  **Applications\BizTalk Application 1 \role Links**です。</span><span class="sxs-lookup"><span data-stu-id="48d63-154">In the [!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)] Administration console, navigate the tree view to the **ShipmentRole** under **Applications\BizTalk Application 1\Role Links**.</span></span> <span data-ttu-id="48d63-155">ダブルクリックして**ShipmentRole**と**ShipmentAgency1**にマップされている、 **SupplierAdvice**操作と**ShipmentAgency2**マップされている、 **SupplierOrder**参加で操作します。</span><span class="sxs-lookup"><span data-stu-id="48d63-155">Double-click **ShipmentRole** and notice **ShipmentAgency1** mapped to the **SupplierAdvice** operation and **ShipmentAgency2** mapped to the **SupplierOrder** operation in the enlistment.</span></span>  
  
5.  <span data-ttu-id="48d63-156">コマンド ウィンドウで Enter キーを押すと、サンプルを参加解除し削除できます。</span><span class="sxs-lookup"><span data-stu-id="48d63-156">In the command window, press ENTER to allow the sample to un-enlist and delete the new party.</span></span>  
  
6.  <span data-ttu-id="48d63-157">[!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)]管理コンソールで、パーティがからできなかったことを確認、 **ShipmentRole**から削除し、**パーティ**ノード。</span><span class="sxs-lookup"><span data-stu-id="48d63-157">In the [!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)] Administration console, verify the party was un-enlisted from the **ShipmentRole** and deleted from the **Parties** node.</span></span>  
  
## <a name="windows-powershell-script-example"></a><span data-ttu-id="48d63-158">Windows PowerShell スクリプトの例</span><span class="sxs-lookup"><span data-stu-id="48d63-158">Windows PowerShell Script Example</span></span>  
 <span data-ttu-id="48d63-159">次の Windows PowerShell スクリプトの例は、の同じ機能を示すために使用できます、 **ExplorerOM**クラス。</span><span class="sxs-lookup"><span data-stu-id="48d63-159">The following Windows PowerShell script example can be used to demonstrate the same features of the **ExplorerOM** classes:</span></span>  
  
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
  
 <span data-ttu-id="48d63-160">次に、PowerShell スクリプト例の実行による出力の例を示します。</span><span class="sxs-lookup"><span data-stu-id="48d63-160">Here is example output from running the PowerShell example script.</span></span> <span data-ttu-id="48d63-161">スクリプトの実行が失敗した場合、PowerShell スクリプトがこのトピックの先頭にある要件の説明に従って有効になっていることを確認してください。</span><span class="sxs-lookup"><span data-stu-id="48d63-161">If the script fails to run, make sure PowerShell scripting is enabled according to the requirements note at the top of this topic.</span></span>  
  
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
  
## <a name="see-also"></a><span data-ttu-id="48d63-162">参照</span><span class="sxs-lookup"><span data-stu-id="48d63-162">See Also</span></span>  
 <span data-ttu-id="48d63-163">[パーティ](../core/parties.md) </span><span class="sxs-lookup"><span data-stu-id="48d63-163">[Parties](../core/parties.md) </span></span>  
 <span data-ttu-id="48d63-164">[ロール リンクとサービス リンク ロール](../core/role-links-and-service-link-roles.md) </span><span class="sxs-lookup"><span data-stu-id="48d63-164">[Role Links and Service Link Roles](../core/role-links-and-service-link-roles.md) </span></span>  
 [<span data-ttu-id="48d63-165">Admin (BizTalk Server Samples フォルダー)</span><span class="sxs-lookup"><span data-stu-id="48d63-165">Admin (BizTalk Server Samples Folder)</span></span>](../core/admin-biztalk-server-samples-folder.md)