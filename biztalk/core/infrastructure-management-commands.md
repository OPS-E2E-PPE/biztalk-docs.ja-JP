---
title: インフラストラクチャ管理コマンド |Microsoft Docs
ms.custom: ''
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: ''
ms.suite: ''
ms.tgt_pltfrm: ''
ms.topic: article
ms.assetid: a2f1a88c-19fc-4384-b6bb-f95962a32921
caps.latest.revision: 8
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: 3a75743ae6f6b65bcab0afa42dd5536e8bfbf1c2
ms.sourcegitcommit: 381e83d43796a345488d54b3f7413e11d56ad7be
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 05/07/2019
ms.locfileid: "65382192"
---
# <a name="infrastructure-management-commands"></a><span data-ttu-id="dc505-102">インフラストラクチャ管理コマンド</span><span class="sxs-lookup"><span data-stu-id="dc505-102">Infrastructure Management Commands</span></span>
<span data-ttu-id="dc505-103">BAM 管理 (BM) ユーティリティ構成コマンドを許可すると、取得、および BAM 構成を更新します。</span><span class="sxs-lookup"><span data-stu-id="dc505-103">The BAM Management (BM) utility configuration commands allow you get and update the BAM configuration.</span></span>  
  
-   <span data-ttu-id="dc505-104">get-config:BAM 構成ファイルを取得します。</span><span class="sxs-lookup"><span data-stu-id="dc505-104">get-config: Gets the BAM configuration file.</span></span>  
  
-   <span data-ttu-id="dc505-105">update-config:BAM 構成を更新します。</span><span class="sxs-lookup"><span data-stu-id="dc505-105">update-config: Updates the BAM configuration.</span></span>  
  
-   <span data-ttu-id="dc505-106">get 変更:BAM インフラストラクチャの変更を一覧表示します。</span><span class="sxs-lookup"><span data-stu-id="dc505-106">get-changes: Lists changes to the BAM infrastructure.</span></span>  
  
-   <span data-ttu-id="dc505-107">get defxml:BAM プライマリ インポート データベース内のすべての成果物を含むファイルを取得します。</span><span class="sxs-lookup"><span data-stu-id="dc505-107">get-defxml: Gets a file containing all the artifacts in the BAM Primary Import database.</span></span>  
  
> [!NOTE]
>  <span data-ttu-id="dc505-108">含めることによって任意の BM ユーティリティ コマンドのトレースを有効にすることができます、 **-トレース: &#124;オフ**パラメーター スイッチ。</span><span class="sxs-lookup"><span data-stu-id="dc505-108">You can enable tracing on any BM utility command by including the **-Trace:on&#124;off** parameter switch.</span></span> <span data-ttu-id="dc505-109">トレース スイッチを使用するには、構成ファイルのトレース設定が上書きされます。</span><span class="sxs-lookup"><span data-stu-id="dc505-109">Using the Trace switch overrides the tracing settings in the configuration file.</span></span> <span data-ttu-id="dc505-110">スイッチは、通常の BM コマンドと組み合わせて使用できます。</span><span class="sxs-lookup"><span data-stu-id="dc505-110">The switch can be used in conjunction with any normal BM command.</span></span>  
  
> [!NOTE]
>  <span data-ttu-id="dc505-111">ユーザー アカウント制御 (UAC) をサポートするシステムでは、管理者特権を使用してこのツールを実行することが必要な場合があります。</span><span class="sxs-lookup"><span data-stu-id="dc505-111">On a system that supports User Account Control (UAC), you may need to run the tool with Administrative privileges.</span></span>  
  
## <a name="get-config-command"></a><span data-ttu-id="dc505-112">get-config コマンド</span><span class="sxs-lookup"><span data-stu-id="dc505-112">get-config Command</span></span>  
 <span data-ttu-id="dc505-113">**使用方法**</span><span class="sxs-lookup"><span data-stu-id="dc505-113">**Usage**</span></span>  
  
 <span data-ttu-id="dc505-114">**bm.exe get-config -FileName:\<output file\> [ -Server:\<server\> ][ -Database:\<database\> ]**</span><span class="sxs-lookup"><span data-stu-id="dc505-114">**bm.exe get-config -FileName:\<output file\> [ -Server:\<server\> ][ -Database:\<database\> ]**</span></span>  
  
 <span data-ttu-id="dc505-115">**パラメーター**</span><span class="sxs-lookup"><span data-stu-id="dc505-115">**Parameters**</span></span>  
  
|<span data-ttu-id="dc505-116">パラメーター</span><span class="sxs-lookup"><span data-stu-id="dc505-116">Parameter</span></span>|<span data-ttu-id="dc505-117">説明</span><span class="sxs-lookup"><span data-stu-id="dc505-117">Description</span></span>|  
|---------------|-----------------|  
|<span data-ttu-id="dc505-118">ファイル名:\<出力ファイル\></span><span class="sxs-lookup"><span data-stu-id="dc505-118">FileName:\<output file\></span></span>|<span data-ttu-id="dc505-119">パスと、構成ファイルの保存先となる名前。</span><span class="sxs-lookup"><span data-stu-id="dc505-119">The path and name to which to save the configuration file.</span></span>|  
|<span data-ttu-id="dc505-120">サーバー:\<サーバー\></span><span class="sxs-lookup"><span data-stu-id="dc505-120">Server:\<server\></span></span>|<span data-ttu-id="dc505-121">省略可能:構成の取得元のサーバーの名前。</span><span class="sxs-lookup"><span data-stu-id="dc505-121">Optional: The name of the server from which to get the configuration.</span></span> <span data-ttu-id="dc505-122">サーバーは、bm.exe を実行するコンピューターと同じドメインにある必要があります。</span><span class="sxs-lookup"><span data-stu-id="dc505-122">The server must be in the same domain as the computer from which you are running bm.exe.</span></span> <span data-ttu-id="dc505-123">サーバー名が指定されていない場合、bm.exe には、localhost の既定の名前が使用されます。</span><span class="sxs-lookup"><span data-stu-id="dc505-123">If the server name is not specified, bm.exe uses the default name of localhost.</span></span>|  
|<span data-ttu-id="dc505-124">データベース:\<データベース\></span><span class="sxs-lookup"><span data-stu-id="dc505-124">Database:\<database\></span></span>|<span data-ttu-id="dc505-125">省略可能:構成の取得元のデータベースの名前。</span><span class="sxs-lookup"><span data-stu-id="dc505-125">Optional: The name of the database from which to get the configuration.</span></span> <span data-ttu-id="dc505-126">名前が指定されていない場合、bm.exe には、BamPrimaryImport の既定の名前が使用されます。</span><span class="sxs-lookup"><span data-stu-id="dc505-126">If the name is not specified, bm.exe uses the default name BamPrimaryImport.</span></span>|  
  
 <span data-ttu-id="dc505-127">BAM 構成 XML を取得し、指定したファイルに保存します。</span><span class="sxs-lookup"><span data-stu-id="dc505-127">Retrieves the BAM configuration XML and saves it in the specified file.</span></span> <span data-ttu-id="dc505-128">**Config の取得**コマンドでは、既存のファイルは上書きされません。</span><span class="sxs-lookup"><span data-stu-id="dc505-128">The **get-config** command will not overwrite the existing file.</span></span>  
  
 <span data-ttu-id="dc505-129">**使用例**</span><span class="sxs-lookup"><span data-stu-id="dc505-129">**Examples**</span></span>  
  
```  
bm.exe get-config -FileName:MyConfig.xml  
bm.exe get-config -FileName:BAMConfiguration.xml -Server:OrdersServer  
```  
  
## <a name="update-config-command"></a><span data-ttu-id="dc505-130">update-config コマンド</span><span class="sxs-lookup"><span data-stu-id="dc505-130">update-config Command</span></span>  
 <span data-ttu-id="dc505-131">**使用方法**</span><span class="sxs-lookup"><span data-stu-id="dc505-131">**Usage**</span></span>  
  
 <span data-ttu-id="dc505-132">**bm.exe update-config -FileName:\<config file\>**</span><span class="sxs-lookup"><span data-stu-id="dc505-132">**bm.exe update-config -FileName:\<config file\>**</span></span>  
  
 <span data-ttu-id="dc505-133">**パラメーター**</span><span class="sxs-lookup"><span data-stu-id="dc505-133">**Parameters**</span></span>  
  
|<span data-ttu-id="dc505-134">パラメーター</span><span class="sxs-lookup"><span data-stu-id="dc505-134">Parameter</span></span>|<span data-ttu-id="dc505-135">説明</span><span class="sxs-lookup"><span data-stu-id="dc505-135">Description</span></span>|  
|---------------|-----------------|  
|<span data-ttu-id="dc505-136">ファイル名:\<構成ファイル\></span><span class="sxs-lookup"><span data-stu-id="dc505-136">FileName:\<config file\></span></span>|<span data-ttu-id="dc505-137">パスと、BAM インフラストラクチャを更新する構成ファイルの名前。</span><span class="sxs-lookup"><span data-stu-id="dc505-137">The path and name of the configuration file from which to update the BAM infrastructure.</span></span>|  
  
 <span data-ttu-id="dc505-138">BAM 構成 XML を含むファイルからローカル コンピューター上の構成を更新します。</span><span class="sxs-lookup"><span data-stu-id="dc505-138">Updates the configuration on the local computer from a file containing BAM configuration XML.</span></span> <span data-ttu-id="dc505-139">現在の構成では、サーバーおよび存在しないデータベース名を追加できます。</span><span class="sxs-lookup"><span data-stu-id="dc505-139">You can add server and database names that do not already exist in the current configuration.</span></span> <span data-ttu-id="dc505-140">サーバーまたはデータベース名にデプロイされている動的インフラストラクチャが既に存在する変更は失敗し、bm.exe エラーが報告されます。</span><span class="sxs-lookup"><span data-stu-id="dc505-140">Changing server or database names that already have dynamic infrastructure deployed in will fail and bm.exe will report an error.</span></span>  
  
 <span data-ttu-id="dc505-141">ファイルで配信された警告のファイルの格納場所を変更した場合、</span><span class="sxs-lookup"><span data-stu-id="dc505-141">If you modify the file drop location for alerts delivered by file.</span></span> <span data-ttu-id="dc505-142">SQL Notifications Services を再起動する必要があります。</span><span class="sxs-lookup"><span data-stu-id="dc505-142">You must restart the SQL Notifications Services.</span></span> <span data-ttu-id="dc505-143">NS サービスを再起動しなかった場合、警告は元のファイルの格納場所に配信され続けます。</span><span class="sxs-lookup"><span data-stu-id="dc505-143">If the NS service is not restarted, alerts will continue being delivered to the original file drop location.</span></span>  
  
 <span data-ttu-id="dc505-144">BAM 構成ファイルの次の行を変更することで、ファイルの格納場所が変更されます。</span><span class="sxs-lookup"><span data-stu-id="dc505-144">The file drop location is changed by modifying the following line of the BAM configuration file.</span></span>  
  
 <span data-ttu-id="dc505-145">\<プロパティ名 ="FileDropUNC"\>\\\\< コンピューター名\>\alerts\</Property\></span><span class="sxs-lookup"><span data-stu-id="dc505-145">\<Property Name="FileDropUNC"\>\\\\<computer name\>\alerts\</Property\></span></span>  
  
 <span data-ttu-id="dc505-146">参照を更新する適切な手順については、次を参照してください。[をバックアップおよび復元する BizTalk Server](../core/backing-up-and-restoring-biztalk-server.md)します。</span><span class="sxs-lookup"><span data-stu-id="dc505-146">For appropriate steps to update the references, see [Backing Up and Restoring BizTalk Server](../core/backing-up-and-restoring-biztalk-server.md).</span></span>  
  
> [!IMPORTANT]
>  <span data-ttu-id="dc505-147">Update-database コマンドを実行すると、[アラート] セクションを含まない BAM 構成ファイルを使用して、BAM 警告を構成済みである場合は、アラートが機能しなくなりますように bm.exe は構成を上書きします。</span><span class="sxs-lookup"><span data-stu-id="dc505-147">If you execute an update-database command, using a BAM configuration file that does not contain an alerts section, and you have already configured BAM Alerts, bm.exe will overwrite the configuration such that alerts will no longer function.</span></span>  
  
 <span data-ttu-id="dc505-148">**使用例**</span><span class="sxs-lookup"><span data-stu-id="dc505-148">**Examples**</span></span>  
  
```  
bm.exe update-config -FileName:MyConfig.xml  
```  
  
## <a name="get-changes-command"></a><span data-ttu-id="dc505-149">get-changes コマンド</span><span class="sxs-lookup"><span data-stu-id="dc505-149">get-changes Command</span></span>  
 <span data-ttu-id="dc505-150">**使用方法**</span><span class="sxs-lookup"><span data-stu-id="dc505-150">**Usage**</span></span>  
  
 <span data-ttu-id="dc505-151">**bm.exe の get 変更 [-サーバー:\<server\> ] [-データベース:\<データベース\>]**</span><span class="sxs-lookup"><span data-stu-id="dc505-151">**bm.exe get-changes [ -Server:\<server\> ][ -Database:\<database\> ]**</span></span>  
  
 <span data-ttu-id="dc505-152">**パラメーター**</span><span class="sxs-lookup"><span data-stu-id="dc505-152">**Parameters**</span></span>  
  
|<span data-ttu-id="dc505-153">パラメーター</span><span class="sxs-lookup"><span data-stu-id="dc505-153">Parameter</span></span>|<span data-ttu-id="dc505-154">説明</span><span class="sxs-lookup"><span data-stu-id="dc505-154">Description</span></span>|  
|---------------|-----------------|  
|<span data-ttu-id="dc505-155">サーバー:\<サーバー\></span><span class="sxs-lookup"><span data-stu-id="dc505-155">Server:\<server\></span></span>|<span data-ttu-id="dc505-156">省略可能:BAM プライマリ インポート データベースが存在するサーバーの名前。</span><span class="sxs-lookup"><span data-stu-id="dc505-156">Optional: The name of the server on which the BAM Primary Import database resides.</span></span> <span data-ttu-id="dc505-157">サーバーは、bm.exe を実行するコンピューターと同じドメインにある必要があります。</span><span class="sxs-lookup"><span data-stu-id="dc505-157">The server must be in the same domain as the computer from which you are running bm.exe.</span></span> <span data-ttu-id="dc505-158">サーバー名が指定されていない場合、bm.exe には、localhost の既定の名前が使用されます。</span><span class="sxs-lookup"><span data-stu-id="dc505-158">If the server name is not specified, bm.exe uses the default name of localhost.</span></span>|  
|<span data-ttu-id="dc505-159">データベース:\<データベース\></span><span class="sxs-lookup"><span data-stu-id="dc505-159">Database:\<database\></span></span>|<span data-ttu-id="dc505-160">省略可能:名前が指定されていない場合、bm.exe には、BamPrimaryImport の既定の名前が使用されます。</span><span class="sxs-lookup"><span data-stu-id="dc505-160">Optional: If the name is not specified, bm.exe uses the default name BamPrimaryImport.</span></span>|  
  
 <span data-ttu-id="dc505-161">BAM プライマリ インポート データベースに適用された変更の一覧を取得します。</span><span class="sxs-lookup"><span data-stu-id="dc505-161">Gets a list of changes applied to the BAM Primary Import database.</span></span> <span data-ttu-id="dc505-162">このコマンドを使用して、BAM インフラストラクチャの変更を監査することができます。</span><span class="sxs-lookup"><span data-stu-id="dc505-162">You can use this command to audit changes to the BAM Infrastructure.</span></span> <span data-ttu-id="dc505-163">次の情報が返されます。</span><span class="sxs-lookup"><span data-stu-id="dc505-163">The command returns the following information:</span></span>  
  
 <span data-ttu-id="dc505-164">変更と変更が適用された元のファイルのコマンドの種類。</span><span class="sxs-lookup"><span data-stu-id="dc505-164">The command type of the change and the file from which the change was applied.</span></span>  
  
 <span data-ttu-id="dc505-165">変更を適用したユーザー。</span><span class="sxs-lookup"><span data-stu-id="dc505-165">Who applied the change.</span></span>  
  
 <span data-ttu-id="dc505-166">変更されたアクティビティ。</span><span class="sxs-lookup"><span data-stu-id="dc505-166">Which activities were changed.</span></span>  
  
 <span data-ttu-id="dc505-167">ビューが変更されました。</span><span class="sxs-lookup"><span data-stu-id="dc505-167">Which views were changed.</span></span>  
  
 <span data-ttu-id="dc505-168">**使用例**</span><span class="sxs-lookup"><span data-stu-id="dc505-168">**Examples**</span></span>  
  
```  
bm.exe get-changes  
```  
  
 <span data-ttu-id="dc505-169">コマンドの出力</span><span class="sxs-lookup"><span data-stu-id="dc505-169">Output of command</span></span>  
  
 <span data-ttu-id="dc505-170">\#1:Deploy c:\bam\ordermanagement.xml</span><span class="sxs-lookup"><span data-stu-id="dc505-170">\#1: Deploy c:\bam\ordermanagement.xml</span></span>  
  
 <span data-ttu-id="dc505-171">12/30/2005 には、ドメイン \ ユーザーによって 8時 17分: 08 PM (v3.5.1536.0)。</span><span class="sxs-lookup"><span data-stu-id="dc505-171">By domain\user at 12/30/2005 8:17:08 PM (v3.5.1536.0).</span></span>  
  
 <span data-ttu-id="dc505-172">アクティビティ:[Ordermgmt]</span><span class="sxs-lookup"><span data-stu-id="dc505-172">Activities: OrderMgmt</span></span>  
  
 <span data-ttu-id="dc505-173">Views:SalesManager</span><span class="sxs-lookup"><span data-stu-id="dc505-173">Views: SalesManager</span></span>  
  
## <a name="get-defxml-command"></a><span data-ttu-id="dc505-174">get-defxml コマンド</span><span class="sxs-lookup"><span data-stu-id="dc505-174">get-defxml Command</span></span>  
 <span data-ttu-id="dc505-175">**使用方法**</span><span class="sxs-lookup"><span data-stu-id="dc505-175">**Usage**</span></span>  
  
 <span data-ttu-id="dc505-176">**bm.exe get-defxml -FileName:\<output file\>[ -Server:\<server\> ][ -Database:\<database\> ]**</span><span class="sxs-lookup"><span data-stu-id="dc505-176">**bm.exe get-defxml -FileName:\<output file\>[ -Server:\<server\> ][ -Database:\<database\> ]**</span></span>  
  
 <span data-ttu-id="dc505-177">**パラメーター**</span><span class="sxs-lookup"><span data-stu-id="dc505-177">**Parameters**</span></span>  
  
|<span data-ttu-id="dc505-178">パラメーター</span><span class="sxs-lookup"><span data-stu-id="dc505-178">Parameter</span></span>|<span data-ttu-id="dc505-179">説明</span><span class="sxs-lookup"><span data-stu-id="dc505-179">Description</span></span>|  
|---------------|-----------------|  
|<span data-ttu-id="dc505-180">ファイル名:\<出力ファイル\></span><span class="sxs-lookup"><span data-stu-id="dc505-180">FileName:\<output file\></span></span>|<span data-ttu-id="dc505-181">パスと、定義の保存先となるファイルの名前。</span><span class="sxs-lookup"><span data-stu-id="dc505-181">The path and name of the file to which to save the definitions.</span></span>|  
|<span data-ttu-id="dc505-182">サーバー:\<サーバー\></span><span class="sxs-lookup"><span data-stu-id="dc505-182">Server:\<server\></span></span>|<span data-ttu-id="dc505-183">省略可能:定義の取得元のサーバーの名前。</span><span class="sxs-lookup"><span data-stu-id="dc505-183">Optional: The name of the server from which to get the definitions.</span></span> <span data-ttu-id="dc505-184">サーバーは、bm.exe を実行するコンピューターと同じドメインにある必要があります。</span><span class="sxs-lookup"><span data-stu-id="dc505-184">The server must be in the same domain as the computer from which you are running bm.exe.</span></span> <span data-ttu-id="dc505-185">サーバー名が指定されていない場合、bm.exe には、localhost の既定の名前が使用されます。</span><span class="sxs-lookup"><span data-stu-id="dc505-185">If the server name is not specified, bm.exe uses the default name of localhost.</span></span>|  
|<span data-ttu-id="dc505-186">データベース:\<データベース\></span><span class="sxs-lookup"><span data-stu-id="dc505-186">Database:\<database\></span></span>|<span data-ttu-id="dc505-187">省略可能:定義の取得元のデータベースの名前。</span><span class="sxs-lookup"><span data-stu-id="dc505-187">Optional: The name of the database from which to get the definitions.</span></span> <span data-ttu-id="dc505-188">名前が指定されていない場合、bm.exe には、BamPrimaryImport の既定の名前が使用されます。</span><span class="sxs-lookup"><span data-stu-id="dc505-188">If the name is not specified, bm.exe uses the default name BamPrimaryImport.</span></span>|  
  
 <span data-ttu-id="dc505-189">BAM プライマリ インポート データベースからのすべての成果物を取得しに XML ファイルとして保存します。</span><span class="sxs-lookup"><span data-stu-id="dc505-189">Retrieves all artifacts on from the BAM Primary Import database and saves them in a file as XML.</span></span> <span data-ttu-id="dc505-190">コマンドでは、既存のファイルは上書きされません。</span><span class="sxs-lookup"><span data-stu-id="dc505-190">The command will not overwrite existing files.</span></span>  
  
 <span data-ttu-id="dc505-191">**使用例**</span><span class="sxs-lookup"><span data-stu-id="dc505-191">**Examples**</span></span>  
  
```  
bm.exe get-defxml -FileName:BAMDefinition.xml  
bm.exe get-defxml -FileName:MyDef.xml -Server:MyServer -Database:MyPI  
```  
  
## <a name="see-also"></a><span data-ttu-id="dc505-192">参照</span><span class="sxs-lookup"><span data-stu-id="dc505-192">See Also</span></span>  
 [<span data-ttu-id="dc505-193">BAM 管理ユーティリティ</span><span class="sxs-lookup"><span data-stu-id="dc505-193">BAM Management Utility</span></span>](../core/bam-management-utility.md)