---
title: インフラストラクチャ管理コマンド |Microsoft ドキュメント
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
ms.openlocfilehash: c82dc5cb65156af86e66abfeffef206f18add5cb
ms.sourcegitcommit: 5abd0ed3f9e4858ffaaec5481bfa8878595e95f7
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 11/28/2017
ms.locfileid: "25973360"
---
# <a name="infrastructure-management-commands"></a><span data-ttu-id="fe2a1-102">インフラストラクチャ管理コマンド</span><span class="sxs-lookup"><span data-stu-id="fe2a1-102">Infrastructure Management Commands</span></span>
<span data-ttu-id="fe2a1-103">BAM 管理 (BM) ユーティリティ構成コマンドを使用すると、BAM の構成を取得および更新できます。</span><span class="sxs-lookup"><span data-stu-id="fe2a1-103">The BAM Management (BM) utility configuration commands allow you get and update the BAM configuration.</span></span>  
  
-   <span data-ttu-id="fe2a1-104">get-config: BAM 構成ファイルを取得します。</span><span class="sxs-lookup"><span data-stu-id="fe2a1-104">get-config: Gets the BAM configuration file.</span></span>  
  
-   <span data-ttu-id="fe2a1-105">更新設定: BAM 構成を更新します。</span><span class="sxs-lookup"><span data-stu-id="fe2a1-105">update-config: Updates the BAM configuration.</span></span>  
  
-   <span data-ttu-id="fe2a1-106">get 変更: BAM インフラストラクチャに変更を一覧表示します。</span><span class="sxs-lookup"><span data-stu-id="fe2a1-106">get-changes: Lists changes to the BAM infrastructure.</span></span>  
  
-   <span data-ttu-id="fe2a1-107">get defxml: BAM プライマリ インポート データベース内のすべての成果物を含むファイルを取得します。</span><span class="sxs-lookup"><span data-stu-id="fe2a1-107">get-defxml: Gets a file containing all the artifacts in the BAM Primary Import database.</span></span>  
  
> [!NOTE]
>  <span data-ttu-id="fe2a1-108">含めることで任意の BM ユーティリティ コマンドのトレースを有効にすることができます、 **-トレース: で &#124;オフ**パラメーター スイッチ。</span><span class="sxs-lookup"><span data-stu-id="fe2a1-108">You can enable tracing on any BM utility command by including the **-Trace:on&#124;off** parameter switch.</span></span> <span data-ttu-id="fe2a1-109">Trace スイッチを使用すると、構成ファイルのトレース設定が上書きされます。</span><span class="sxs-lookup"><span data-stu-id="fe2a1-109">Using the Trace switch overrides the tracing settings in the configuration file.</span></span> <span data-ttu-id="fe2a1-110">このスイッチは、通常の BM コマンドと組み合わせて使用できます。</span><span class="sxs-lookup"><span data-stu-id="fe2a1-110">The switch can be used in conjunction with any normal BM command.</span></span>  
  
> [!NOTE]
>  <span data-ttu-id="fe2a1-111">ユーザー アカウント制御 (UAC) をサポートするシステムでは、管理者特権を使用してこのツールを実行することが必要な場合があります。</span><span class="sxs-lookup"><span data-stu-id="fe2a1-111">On a system that supports User Account Control (UAC), you may need to run the tool with Administrative privileges.</span></span>  
  
## <a name="get-config-command"></a><span data-ttu-id="fe2a1-112">get-config コマンド</span><span class="sxs-lookup"><span data-stu-id="fe2a1-112">get-config Command</span></span>  
 <span data-ttu-id="fe2a1-113">**使用方法**</span><span class="sxs-lookup"><span data-stu-id="fe2a1-113">**Usage**</span></span>  
  
 <span data-ttu-id="fe2a1-114">**bm.exe get config ファイル名:\<出力ファイル\>[-サーバー:\<サーバー\> ] [-データベース:\<データベース\>]**</span><span class="sxs-lookup"><span data-stu-id="fe2a1-114">**bm.exe get-config -FileName:\<output file\> [ -Server:\<server\> ][ -Database:\<database\> ]**</span></span>  
  
 <span data-ttu-id="fe2a1-115">**パラメーター**</span><span class="sxs-lookup"><span data-stu-id="fe2a1-115">**Parameters**</span></span>  
  
|<span data-ttu-id="fe2a1-116">パラメーター</span><span class="sxs-lookup"><span data-stu-id="fe2a1-116">Parameter</span></span>|<span data-ttu-id="fe2a1-117">Description</span><span class="sxs-lookup"><span data-stu-id="fe2a1-117">Description</span></span>|  
|---------------|-----------------|  
|<span data-ttu-id="fe2a1-118">ファイル名:\<出力ファイル\></span><span class="sxs-lookup"><span data-stu-id="fe2a1-118">FileName:\<output file\></span></span>|<span data-ttu-id="fe2a1-119">構成ファイルの保存場所のパスおよび名前です。</span><span class="sxs-lookup"><span data-stu-id="fe2a1-119">The path and name to which to save the configuration file.</span></span>|  
|<span data-ttu-id="fe2a1-120">サーバー:\<サーバー\></span><span class="sxs-lookup"><span data-stu-id="fe2a1-120">Server:\<server\></span></span>|<span data-ttu-id="fe2a1-121">省略可能: 構成の取得元のサーバーの名前。</span><span class="sxs-lookup"><span data-stu-id="fe2a1-121">Optional: The name of the server from which to get the configuration.</span></span> <span data-ttu-id="fe2a1-122">このサーバーは、bm.exe を実行するコンピューターと同じドメインに存在している必要があります。</span><span class="sxs-lookup"><span data-stu-id="fe2a1-122">The server must be in the same domain as the computer from which you are running bm.exe.</span></span> <span data-ttu-id="fe2a1-123">サーバー名を指定しなかった場合、既定の名前 (localhost) が使用されます。</span><span class="sxs-lookup"><span data-stu-id="fe2a1-123">If the server name is not specified, bm.exe uses the default name of localhost.</span></span>|  
|<span data-ttu-id="fe2a1-124">データベース:\<データベース\></span><span class="sxs-lookup"><span data-stu-id="fe2a1-124">Database:\<database\></span></span>|<span data-ttu-id="fe2a1-125">省略可能: 構成の取得元のデータベースの名前。</span><span class="sxs-lookup"><span data-stu-id="fe2a1-125">Optional: The name of the database from which to get the configuration.</span></span> <span data-ttu-id="fe2a1-126">指定しなかった場合、既定の名前 (BamPrimaryImport) が使用されます。</span><span class="sxs-lookup"><span data-stu-id="fe2a1-126">If the name is not specified, bm.exe uses the default name BamPrimaryImport.</span></span>|  
  
 <span data-ttu-id="fe2a1-127">BAM 構成 XML を取得し、それを指定されたファイルに保存します。</span><span class="sxs-lookup"><span data-stu-id="fe2a1-127">Retrieves the BAM configuration XML and saves it in the specified file.</span></span> <span data-ttu-id="fe2a1-128">**Get-config**コマンドでは、既存のファイルは上書きされません。</span><span class="sxs-lookup"><span data-stu-id="fe2a1-128">The **get-config** command will not overwrite the existing file.</span></span>  
  
 <span data-ttu-id="fe2a1-129">**使用例**</span><span class="sxs-lookup"><span data-stu-id="fe2a1-129">**Examples**</span></span>  
  
```  
bm.exe get-config -FileName:MyConfig.xml  
bm.exe get-config -FileName:BAMConfiguration.xml -Server:OrdersServer  
```  
  
## <a name="update-config-command"></a><span data-ttu-id="fe2a1-130">update-config コマンド</span><span class="sxs-lookup"><span data-stu-id="fe2a1-130">update-config Command</span></span>  
 <span data-ttu-id="fe2a1-131">**使用方法**</span><span class="sxs-lookup"><span data-stu-id="fe2a1-131">**Usage**</span></span>  
  
 <span data-ttu-id="fe2a1-132">**bm.exe 更新 config ファイル名:\<構成ファイル\>**</span><span class="sxs-lookup"><span data-stu-id="fe2a1-132">**bm.exe update-config -FileName:\<config file\>**</span></span>  
  
 <span data-ttu-id="fe2a1-133">**パラメーター**</span><span class="sxs-lookup"><span data-stu-id="fe2a1-133">**Parameters**</span></span>  
  
|<span data-ttu-id="fe2a1-134">パラメーター</span><span class="sxs-lookup"><span data-stu-id="fe2a1-134">Parameter</span></span>|<span data-ttu-id="fe2a1-135">Description</span><span class="sxs-lookup"><span data-stu-id="fe2a1-135">Description</span></span>|  
|---------------|-----------------|  
|<span data-ttu-id="fe2a1-136">ファイル名:\<構成ファイル\></span><span class="sxs-lookup"><span data-stu-id="fe2a1-136">FileName:\<config file\></span></span>|<span data-ttu-id="fe2a1-137">BAM インフラストラクチャの更新に使用する構成ファイルのパスおよび名前です。</span><span class="sxs-lookup"><span data-stu-id="fe2a1-137">The path and name of the configuration file from which to update the BAM infrastructure.</span></span>|  
  
 <span data-ttu-id="fe2a1-138">BAM 構成 XML ファイルに格納された情報で、ローカル コンピューターの構成を更新します。</span><span class="sxs-lookup"><span data-stu-id="fe2a1-138">Updates the configuration on the local computer from a file containing BAM configuration XML.</span></span> <span data-ttu-id="fe2a1-139">追加できるのは、現在の構成にまだ存在しないサーバーおよびデータベースの名前だけです。</span><span class="sxs-lookup"><span data-stu-id="fe2a1-139">You can add server and database names that do not already exist in the current configuration.</span></span> <span data-ttu-id="fe2a1-140">動的インフラストラクチャが既に展開されているサーバーまたはデータベースの名前を変更した場合、bm.exe からエラーが報告されます。</span><span class="sxs-lookup"><span data-stu-id="fe2a1-140">Changing server or database names that already have dynamic infrastructure deployed in will fail and bm.exe will report an error.</span></span>  
  
 <span data-ttu-id="fe2a1-141">ファイルで配信された警告のファイルの格納場所を変更した場合、</span><span class="sxs-lookup"><span data-stu-id="fe2a1-141">If you modify the file drop location for alerts delivered by file.</span></span> <span data-ttu-id="fe2a1-142">SQL Notifications Services を再起動する必要があります。</span><span class="sxs-lookup"><span data-stu-id="fe2a1-142">You must restart the SQL Notifications Services.</span></span> <span data-ttu-id="fe2a1-143">NS サービスを再起動しなかった場合、警告は元のファイルの格納場所に配信され続けます。</span><span class="sxs-lookup"><span data-stu-id="fe2a1-143">If the NS service is not restarted, alerts will continue being delivered to the original file drop location.</span></span>  
  
 <span data-ttu-id="fe2a1-144">ファイルの格納場所は、BAM 構成ファイルの次の行に修正を加えることによって変更します。</span><span class="sxs-lookup"><span data-stu-id="fe2a1-144">The file drop location is changed by modifying the following line of the BAM configuration file.</span></span>  
  
 <span data-ttu-id="fe2a1-145">\<プロパティ名 ="FileDropUNC"\>\\\\< コンピューター名\>\alerts\</Property\></span><span class="sxs-lookup"><span data-stu-id="fe2a1-145">\<Property Name="FileDropUNC"\>\\\\<computer name\>\alerts\</Property\></span></span>  
  
 <span data-ttu-id="fe2a1-146">参照を更新する適切な手順については、次を参照してください。[をバックアップおよび復元する BizTalk Server](../core/backing-up-and-restoring-biztalk-server.md)です。</span><span class="sxs-lookup"><span data-stu-id="fe2a1-146">For appropriate steps to update the references, see [Backing Up and Restoring BizTalk Server](../core/backing-up-and-restoring-biztalk-server.md).</span></span>  
  
> [!IMPORTANT]
>  <span data-ttu-id="fe2a1-147">既に BAM 警告が構成されているとき、警告セクションを含まない BAM 構成ファイルを使って update-database コマンドを実行すると、今後、警告が生成されないよう、bm.exe により構成が上書きされます。</span><span class="sxs-lookup"><span data-stu-id="fe2a1-147">If you execute an update-database command, using a BAM configuration file that does not contain an alerts section, and you have already configured BAM Alerts, bm.exe will overwrite the configuration such that alerts will no longer function.</span></span>  
  
 <span data-ttu-id="fe2a1-148">**使用例**</span><span class="sxs-lookup"><span data-stu-id="fe2a1-148">**Examples**</span></span>  
  
```  
bm.exe update-config -FileName:MyConfig.xml  
```  
  
## <a name="get-changes-command"></a><span data-ttu-id="fe2a1-149">get-changes コマンド</span><span class="sxs-lookup"><span data-stu-id="fe2a1-149">get-changes Command</span></span>  
 <span data-ttu-id="fe2a1-150">**使用方法**</span><span class="sxs-lookup"><span data-stu-id="fe2a1-150">**Usage**</span></span>  
  
 <span data-ttu-id="fe2a1-151">**bm.exe get 変更 [-サーバー:\<サーバー\> ] [-データベース:\<データベース\>]**</span><span class="sxs-lookup"><span data-stu-id="fe2a1-151">**bm.exe get-changes [ -Server:\<server\> ][ -Database:\<database\> ]**</span></span>  
  
 <span data-ttu-id="fe2a1-152">**パラメーター**</span><span class="sxs-lookup"><span data-stu-id="fe2a1-152">**Parameters**</span></span>  
  
|<span data-ttu-id="fe2a1-153">パラメーター</span><span class="sxs-lookup"><span data-stu-id="fe2a1-153">Parameter</span></span>|<span data-ttu-id="fe2a1-154">Description</span><span class="sxs-lookup"><span data-stu-id="fe2a1-154">Description</span></span>|  
|---------------|-----------------|  
|<span data-ttu-id="fe2a1-155">サーバー:\<サーバー\></span><span class="sxs-lookup"><span data-stu-id="fe2a1-155">Server:\<server\></span></span>|<span data-ttu-id="fe2a1-156">省略可能: BAM プライマリ インポート データベースが存在するサーバーの名前です。</span><span class="sxs-lookup"><span data-stu-id="fe2a1-156">Optional: The name of the server on which the BAM Primary Import database resides.</span></span> <span data-ttu-id="fe2a1-157">このサーバーは、bm.exe を実行するコンピューターと同じドメインに存在している必要があります。</span><span class="sxs-lookup"><span data-stu-id="fe2a1-157">The server must be in the same domain as the computer from which you are running bm.exe.</span></span> <span data-ttu-id="fe2a1-158">サーバー名を指定しなかった場合、既定の名前 (localhost) が使用されます。</span><span class="sxs-lookup"><span data-stu-id="fe2a1-158">If the server name is not specified, bm.exe uses the default name of localhost.</span></span>|  
|<span data-ttu-id="fe2a1-159">データベース:\<データベース\></span><span class="sxs-lookup"><span data-stu-id="fe2a1-159">Database:\<database\></span></span>|<span data-ttu-id="fe2a1-160">省略可能: 名前が指定されていない場合、bm.exe は BamPrimaryImport の既定の名前を使用します。</span><span class="sxs-lookup"><span data-stu-id="fe2a1-160">Optional: If the name is not specified, bm.exe uses the default name BamPrimaryImport.</span></span>|  
  
 <span data-ttu-id="fe2a1-161">BAM プライマリ インポート データベースに対して適用された変更一覧を取得します。</span><span class="sxs-lookup"><span data-stu-id="fe2a1-161">Gets a list of changes applied to the BAM Primary Import database.</span></span> <span data-ttu-id="fe2a1-162">このコマンドを使用して、BAM インフラストラクチャに対する変更を監査できます。</span><span class="sxs-lookup"><span data-stu-id="fe2a1-162">You can use this command to audit changes to the BAM Infrastructure.</span></span> <span data-ttu-id="fe2a1-163">このコマンドで返される情報は次のとおりです。</span><span class="sxs-lookup"><span data-stu-id="fe2a1-163">The command returns the following information:</span></span>  
  
 <span data-ttu-id="fe2a1-164">変更に使用されたコマンドの種類と、変更に使用されたファイル</span><span class="sxs-lookup"><span data-stu-id="fe2a1-164">The command type of the change and the file from which the change was applied.</span></span>  
  
 <span data-ttu-id="fe2a1-165">変更を適用したユーザー</span><span class="sxs-lookup"><span data-stu-id="fe2a1-165">Who applied the change.</span></span>  
  
 <span data-ttu-id="fe2a1-166">変更されたアクティビティ</span><span class="sxs-lookup"><span data-stu-id="fe2a1-166">Which activities were changed.</span></span>  
  
 <span data-ttu-id="fe2a1-167">変更されたビュー</span><span class="sxs-lookup"><span data-stu-id="fe2a1-167">Which views were changed.</span></span>  
  
 <span data-ttu-id="fe2a1-168">**使用例**</span><span class="sxs-lookup"><span data-stu-id="fe2a1-168">**Examples**</span></span>  
  
```  
bm.exe get-changes  
```  
  
 <span data-ttu-id="fe2a1-169">コマンドの出力</span><span class="sxs-lookup"><span data-stu-id="fe2a1-169">Output of command</span></span>  
  
 <span data-ttu-id="fe2a1-170">\#1: c:\bam\ordermanagement.xml の展開</span><span class="sxs-lookup"><span data-stu-id="fe2a1-170">\#1: Deploy c:\bam\ordermanagement.xml</span></span>  
  
 <span data-ttu-id="fe2a1-171">By domain\user at 12/30/2005 8:17:08 PM (v3.5.1536.0).</span><span class="sxs-lookup"><span data-stu-id="fe2a1-171">By domain\user at 12/30/2005 8:17:08 PM (v3.5.1536.0).</span></span>  
  
 <span data-ttu-id="fe2a1-172">アクティビティ: [ordermgmt]</span><span class="sxs-lookup"><span data-stu-id="fe2a1-172">Activities: OrderMgmt</span></span>  
  
 <span data-ttu-id="fe2a1-173">ビュー: SalesManager</span><span class="sxs-lookup"><span data-stu-id="fe2a1-173">Views: SalesManager</span></span>  
  
## <a name="get-defxml-command"></a><span data-ttu-id="fe2a1-174">get-defxml コマンド</span><span class="sxs-lookup"><span data-stu-id="fe2a1-174">get-defxml Command</span></span>  
 <span data-ttu-id="fe2a1-175">**使用方法**</span><span class="sxs-lookup"><span data-stu-id="fe2a1-175">**Usage**</span></span>  
  
 <span data-ttu-id="fe2a1-176">**bm.exe get defxml-filename:\<出力ファイル\>[-サーバー:\<サーバー\> ] [-データベース:\<データベース\>]**</span><span class="sxs-lookup"><span data-stu-id="fe2a1-176">**bm.exe get-defxml -FileName:\<output file\>[ -Server:\<server\> ][ -Database:\<database\> ]**</span></span>  
  
 <span data-ttu-id="fe2a1-177">**パラメーター**</span><span class="sxs-lookup"><span data-stu-id="fe2a1-177">**Parameters**</span></span>  
  
|<span data-ttu-id="fe2a1-178">パラメーター</span><span class="sxs-lookup"><span data-stu-id="fe2a1-178">Parameter</span></span>|<span data-ttu-id="fe2a1-179">Description</span><span class="sxs-lookup"><span data-stu-id="fe2a1-179">Description</span></span>|  
|---------------|-----------------|  
|<span data-ttu-id="fe2a1-180">ファイル名:\<出力ファイル\></span><span class="sxs-lookup"><span data-stu-id="fe2a1-180">FileName:\<output file\></span></span>|<span data-ttu-id="fe2a1-181">定義の保存先ファイルのパスおよび名前です。</span><span class="sxs-lookup"><span data-stu-id="fe2a1-181">The path and name of the file to which to save the definitions.</span></span>|  
|<span data-ttu-id="fe2a1-182">サーバー:\<サーバー\></span><span class="sxs-lookup"><span data-stu-id="fe2a1-182">Server:\<server\></span></span>|<span data-ttu-id="fe2a1-183">省略可能: 定義の取得元のサーバーの名前。</span><span class="sxs-lookup"><span data-stu-id="fe2a1-183">Optional: The name of the server from which to get the definitions.</span></span> <span data-ttu-id="fe2a1-184">このサーバーは、bm.exe を実行するコンピューターと同じドメインに存在している必要があります。</span><span class="sxs-lookup"><span data-stu-id="fe2a1-184">The server must be in the same domain as the computer from which you are running bm.exe.</span></span> <span data-ttu-id="fe2a1-185">サーバー名を指定しなかった場合、既定の名前 (localhost) が使用されます。</span><span class="sxs-lookup"><span data-stu-id="fe2a1-185">If the server name is not specified, bm.exe uses the default name of localhost.</span></span>|  
|<span data-ttu-id="fe2a1-186">データベース:\<データベース\></span><span class="sxs-lookup"><span data-stu-id="fe2a1-186">Database:\<database\></span></span>|<span data-ttu-id="fe2a1-187">省略可能: 定義の取得元のデータベースの名前。</span><span class="sxs-lookup"><span data-stu-id="fe2a1-187">Optional: The name of the database from which to get the definitions.</span></span> <span data-ttu-id="fe2a1-188">指定しなかった場合、既定の名前 (BamPrimaryImport) が使用されます。</span><span class="sxs-lookup"><span data-stu-id="fe2a1-188">If the name is not specified, bm.exe uses the default name BamPrimaryImport.</span></span>|  
  
 <span data-ttu-id="fe2a1-189">BAM プライマリ インポート データベースからすべてのアイテムを取得し、それらを XML ファイルとして保存します。</span><span class="sxs-lookup"><span data-stu-id="fe2a1-189">Retrieves all artifacts on from the BAM Primary Import database and saves them in a file as XML.</span></span> <span data-ttu-id="fe2a1-190">既存のファイルは上書きされません。</span><span class="sxs-lookup"><span data-stu-id="fe2a1-190">The command will not overwrite existing files.</span></span>  
  
 <span data-ttu-id="fe2a1-191">**使用例**</span><span class="sxs-lookup"><span data-stu-id="fe2a1-191">**Examples**</span></span>  
  
```  
bm.exe get-defxml -FileName:BAMDefinition.xml  
bm.exe get-defxml -FileName:MyDef.xml -Server:MyServer -Database:MyPI  
```  
  
## <a name="see-also"></a><span data-ttu-id="fe2a1-192">参照</span><span class="sxs-lookup"><span data-stu-id="fe2a1-192">See Also</span></span>  
 [<span data-ttu-id="fe2a1-193">BAM 管理ユーティリティ</span><span class="sxs-lookup"><span data-stu-id="fe2a1-193">BAM Management Utility</span></span>](../core/bam-management-utility.md)