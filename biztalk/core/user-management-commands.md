---
title: "ユーザー管理コマンド |Microsoft ドキュメント"
ms.custom: 
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: 
ms.suite: 
ms.tgt_pltfrm: 
ms.topic: article
ms.assetid: feb12226-a4da-4fc5-93a1-aced239f60a9
caps.latest.revision: "9"
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: 16527acda7432b2eea35f0c87bb9d89fff632430
ms.sourcegitcommit: 5abd0ed3f9e4858ffaaec5481bfa8878595e95f7
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 11/28/2017
---
# <a name="user-management-commands"></a><span data-ttu-id="52f76-102">ユーザー管理コマンド</span><span class="sxs-lookup"><span data-stu-id="52f76-102">User Management Commands</span></span>
<span data-ttu-id="52f76-103">BAM 管理ユーティリティの警告ユーザー管理コマンドを使用すると、ユーザーの取得、追加、および削除を行うことができます。</span><span class="sxs-lookup"><span data-stu-id="52f76-103">The BAM Management utility alert user management commands allow you to get, add, and remove users.</span></span>  
  
-   <span data-ttu-id="52f76-104">get アカウント: すべてのユーザーと指定されたビューにアクセスできるグループの一覧を取得します。</span><span class="sxs-lookup"><span data-stu-id="52f76-104">get-accounts: Gets a list of all users and groups that can access a specified view.</span></span>  
  
-   <span data-ttu-id="52f76-105">アカウントの追加: アクセス権を指定したユーザーまたはグループの指定されたビューを与えます。</span><span class="sxs-lookup"><span data-stu-id="52f76-105">add-account: Grants access rights for the specified user or group to the specified view.</span></span>  
  
-   <span data-ttu-id="52f76-106">アカウントの削除: 指定されたビューからのアクセス権をユーザーまたはグループを削除します。</span><span class="sxs-lookup"><span data-stu-id="52f76-106">remove-account: Removes access rights for a user or group from a specified view.</span></span>  
  
> [!NOTE]
>  <span data-ttu-id="52f76-107">含めることで任意の BM ユーティリティ コマンドのトレースを有効にすることができます、 **-トレース: で &#124;オフ**パラメーター スイッチ。</span><span class="sxs-lookup"><span data-stu-id="52f76-107">You can enable tracing on any BM utility command by including the **-Trace:on&#124;off** parameter switch.</span></span> <span data-ttu-id="52f76-108">Trace スイッチを使用すると、構成ファイルのトレース設定が上書きされます。</span><span class="sxs-lookup"><span data-stu-id="52f76-108">Using the Trace switch overrides the tracing settings in the configuration file.</span></span> <span data-ttu-id="52f76-109">このスイッチは、通常の BM コマンドと組み合わせて使用できます。</span><span class="sxs-lookup"><span data-stu-id="52f76-109">The switch can be used in conjunction with any normal BM command.</span></span>  
  
> [!NOTE]
>  <span data-ttu-id="52f76-110">ユーザー アカウント制御 (UAC) をサポートするシステムでは、管理者特権を使用してこのツールを実行することが必要な場合があります。</span><span class="sxs-lookup"><span data-stu-id="52f76-110">On a system that supports User Account Control (UAC), you may need to run the tool with Administrative privileges.</span></span>  
  
## <a name="get-accounts-command"></a><span data-ttu-id="52f76-111">get-accounts コマンド</span><span class="sxs-lookup"><span data-stu-id="52f76-111">get-accounts Command</span></span>  
 <span data-ttu-id="52f76-112">**使用方法**</span><span class="sxs-lookup"><span data-stu-id="52f76-112">**Usage**</span></span>  
  
 <span data-ttu-id="52f76-113">**bm.exe get-アカウントの表示:\<ビュー名\>[-サーバー:\<サーバー\> ] [-データベース:\<データベース\>]**</span><span class="sxs-lookup"><span data-stu-id="52f76-113">**bm.exe get-accounts -View:\<view name\>[ -Server:\<server\> ][ -Database:\<database\> ]**</span></span>  
  
 <span data-ttu-id="52f76-114">**パラメーター**</span><span class="sxs-lookup"><span data-stu-id="52f76-114">**Parameters**</span></span>  
  
|<span data-ttu-id="52f76-115">パラメーター</span><span class="sxs-lookup"><span data-stu-id="52f76-115">Parameter</span></span>|<span data-ttu-id="52f76-116">Description</span><span class="sxs-lookup"><span data-stu-id="52f76-116">Description</span></span>|  
|---------------|-----------------|  
|<span data-ttu-id="52f76-117">ビュー:\<ビュー名\></span><span class="sxs-lookup"><span data-stu-id="52f76-117">View:\<view name\></span></span>|<span data-ttu-id="52f76-118">アカウントを一覧表示するビューの名前です。</span><span class="sxs-lookup"><span data-stu-id="52f76-118">The name of the view for which to list accounts.</span></span>|  
|<span data-ttu-id="52f76-119">サーバー:\<サーバー\></span><span class="sxs-lookup"><span data-stu-id="52f76-119">Server:\<server\></span></span>|<span data-ttu-id="52f76-120">省略可能: アカウントを取得する対象のサーバーの名前。</span><span class="sxs-lookup"><span data-stu-id="52f76-120">Optional: The name of the server from which to retrieve the accounts.</span></span> <span data-ttu-id="52f76-121">このサーバーは、bm.exe を実行するコンピューターと同じドメインに存在している必要があります。</span><span class="sxs-lookup"><span data-stu-id="52f76-121">The server must be in the same domain as the computer from which you are running bm.exe.</span></span> <span data-ttu-id="52f76-122">サーバー名を指定しなかった場合、既定の名前 (localhost) が使用されます。</span><span class="sxs-lookup"><span data-stu-id="52f76-122">If the server name is not specified, bm.exe uses the default name of localhost.</span></span>|  
|<span data-ttu-id="52f76-123">データベース:\<データベース\></span><span class="sxs-lookup"><span data-stu-id="52f76-123">Database:\<database\></span></span>|<span data-ttu-id="52f76-124">省略可能: アカウントを取得する対象のデータベースの名前。</span><span class="sxs-lookup"><span data-stu-id="52f76-124">Optional: The name of the database from which to retrieve the accounts.</span></span> <span data-ttu-id="52f76-125">指定しなかった場合、既定の名前 (BamPrimaryImport) が使用されます。</span><span class="sxs-lookup"><span data-stu-id="52f76-125">If the name is not specified, bm.exe uses the default name BamPrimaryImport.</span></span>|  
  
 <span data-ttu-id="52f76-126">指定されたビューにアクセスすることのできるすべてのユーザーおよびグループを一覧表示します。</span><span class="sxs-lookup"><span data-stu-id="52f76-126">Lists all users and groups that can access the specified view.</span></span>  
  
 <span data-ttu-id="52f76-127">**使用例**</span><span class="sxs-lookup"><span data-stu-id="52f76-127">**Examples**</span></span>  
  
 `bm.exe get-accounts -View:PurchaseOrder`  
  
 `bm.exe get-accounts -View:ShipmentOrder -Server:Ship -Database:ShipDatabase`  
  
## <a name="add-account-command"></a><span data-ttu-id="52f76-128">add-account コマンド</span><span class="sxs-lookup"><span data-stu-id="52f76-128">add-account Command</span></span>  
 <span data-ttu-id="52f76-129">**使用方法**</span><span class="sxs-lookup"><span data-stu-id="52f76-129">**Usage**</span></span>  
  
 <span data-ttu-id="52f76-130">**bm.exe アカウントの追加-accountname:\<アカウント名\>-ビュー:\<ビュー名\>[-サーバー:\<サーバー\> ] [-データベース:\<データベース\>]**</span><span class="sxs-lookup"><span data-stu-id="52f76-130">**bm.exe add-account -AccountName:\<account name\> -View:\<view name\>[ -Server:\<server\> ][ -Database:\<database\> ]**</span></span>  
  
 <span data-ttu-id="52f76-131">**パラメーター**</span><span class="sxs-lookup"><span data-stu-id="52f76-131">**Parameters**</span></span>  
  
|<span data-ttu-id="52f76-132">パラメーター</span><span class="sxs-lookup"><span data-stu-id="52f76-132">Parameter</span></span>|<span data-ttu-id="52f76-133">Description</span><span class="sxs-lookup"><span data-stu-id="52f76-133">Description</span></span>|  
|---------------|-----------------|  
|<span data-ttu-id="52f76-134">AccountName:<アカウント名</span><span class="sxs-lookup"><span data-stu-id="52f76-134">AccountName:<account name</span></span>|<span data-ttu-id="52f76-135">権限を付与するアカウントの名前です。</span><span class="sxs-lookup"><span data-stu-id="52f76-135">The name of the account to which rights are granted.</span></span>|  
|<span data-ttu-id="52f76-136">ビュー:\<ビュー名\></span><span class="sxs-lookup"><span data-stu-id="52f76-136">View:\<view name\></span></span>|<span data-ttu-id="52f76-137">権限を付与するビューの名前です。</span><span class="sxs-lookup"><span data-stu-id="52f76-137">The name of the view to which rights are granted.</span></span>|  
|<span data-ttu-id="52f76-138">サーバー:\<サーバー\></span><span class="sxs-lookup"><span data-stu-id="52f76-138">Server:\<server\></span></span>|<span data-ttu-id="52f76-139">省略可能: ビューが存在するサーバーの名前です。</span><span class="sxs-lookup"><span data-stu-id="52f76-139">Optional: The name of the server on which the view resides.</span></span> <span data-ttu-id="52f76-140">このサーバーは、bm.exe を実行するコンピューターと同じドメインに存在している必要があります。</span><span class="sxs-lookup"><span data-stu-id="52f76-140">The server must be in the same domain as the computer from which you are running bm.exe.</span></span> <span data-ttu-id="52f76-141">サーバー名を指定しなかった場合、既定の名前 (localhost) が使用されます。</span><span class="sxs-lookup"><span data-stu-id="52f76-141">If the server name is not specified, bm.exe uses the default name of localhost.</span></span>|  
|<span data-ttu-id="52f76-142">データベース:\<データベース\></span><span class="sxs-lookup"><span data-stu-id="52f76-142">Database:\<database\></span></span>|<span data-ttu-id="52f76-143">省略可能: ビューが存在するデータベースの名前。</span><span class="sxs-lookup"><span data-stu-id="52f76-143">Optional: The name of the database on which the view resides.</span></span> <span data-ttu-id="52f76-144">指定しなかった場合、既定の名前 (BamPrimaryImport) が使用されます。</span><span class="sxs-lookup"><span data-stu-id="52f76-144">If the name is not specified, bm.exe uses the default name BamPrimaryImport.</span></span>|  
  
 <span data-ttu-id="52f76-145">指定されたユーザーまたはグループに対し、特定のビューに対するアクセス権を付与します。</span><span class="sxs-lookup"><span data-stu-id="52f76-145">Grants the specified user or group access rights to the specified view.</span></span>  
  
> [!IMPORTANT]
>  <span data-ttu-id="52f76-146">リアルタイム集計 (Rta) を使用している場合で追加されたユーザー**アカウントの追加**コマンドでは、SQL Server へのログオン権限が自動的に付与されません。</span><span class="sxs-lookup"><span data-stu-id="52f76-146">If you are using Real Time Aggregations (RTAs), users added with **add-account** command are not automatically granted logon rights to SQL Server.</span></span> <span data-ttu-id="52f76-147">RTA を使用している場合は、RTA のビューを表示しなければならないすべてのユーザーを含む、Windows ユーザー グループの作成を検討してください。</span><span class="sxs-lookup"><span data-stu-id="52f76-147">If you are using RTAs, consider establishing a Windows user group that contains all of the users that need to see views of the RTAs.</span></span> <span data-ttu-id="52f76-148">BAM プライマリ インポート データベースをホストする SQL Server の明示的な SQL Server ログオン権限をそのグループに許可します。</span><span class="sxs-lookup"><span data-stu-id="52f76-148">Grant that group explicit SQL Server logon rights on the SQL server hosting the BAM Primary Import databases.</span></span>  
  
 <span data-ttu-id="52f76-149">**使用例**</span><span class="sxs-lookup"><span data-stu-id="52f76-149">**Examples**</span></span>  
  
```  
bm.exe add-account -AccountName:john -View:PurchaseOrder  
bm.exe add-account -AccountName:Agents -View:PO -Server:Srv1 -Database:Db2  
```  
  
## <a name="remove-account-command"></a><span data-ttu-id="52f76-150">remove-account コマンド</span><span class="sxs-lookup"><span data-stu-id="52f76-150">remove-account Command</span></span>  
 <span data-ttu-id="52f76-151">**使用方法**</span><span class="sxs-lookup"><span data-stu-id="52f76-151">**Usage**</span></span>  
  
 <span data-ttu-id="52f76-152">**bm.exe 削除アカウント-accountname:\<アカウント名\>-ビュー:\<ビュー名\>[-サーバー:\<サーバー\> ] [-データベース:\<データベース\>]**</span><span class="sxs-lookup"><span data-stu-id="52f76-152">**bm.exe remove-account -AccountName:\<account name\> -View:\<view name\>[ -Server:\<server\> ][ -Database:\<database\> ]**</span></span>  
  
 <span data-ttu-id="52f76-153">**パラメーター**</span><span class="sxs-lookup"><span data-stu-id="52f76-153">**Parameters**</span></span>  
  
|<span data-ttu-id="52f76-154">パラメーター</span><span class="sxs-lookup"><span data-stu-id="52f76-154">Parameter</span></span>|<span data-ttu-id="52f76-155">Description</span><span class="sxs-lookup"><span data-stu-id="52f76-155">Description</span></span>|  
|---------------|-----------------|  
|<span data-ttu-id="52f76-156">AccountName:\<アカウント名\></span><span class="sxs-lookup"><span data-stu-id="52f76-156">AccountName:\<account name\></span></span>|<span data-ttu-id="52f76-157">ビューに対するアクセス権を削除するアカウントの名前です。</span><span class="sxs-lookup"><span data-stu-id="52f76-157">The name of the account from which to remove rights to the view.</span></span>|  
|<span data-ttu-id="52f76-158">ビュー:\<ビュー名\></span><span class="sxs-lookup"><span data-stu-id="52f76-158">View:\<view name\></span></span>|<span data-ttu-id="52f76-159">権限を削除するビューの名前です。</span><span class="sxs-lookup"><span data-stu-id="52f76-159">The name of the view to which rights are removed.</span></span>|  
|<span data-ttu-id="52f76-160">サーバー:\<サーバー\></span><span class="sxs-lookup"><span data-stu-id="52f76-160">Server:\<server\></span></span>|<span data-ttu-id="52f76-161">省略可能: ビューが存在するサーバーの名前です。</span><span class="sxs-lookup"><span data-stu-id="52f76-161">Optional: The name of the server on which the view resides.</span></span> <span data-ttu-id="52f76-162">このサーバーは、bm.exe を実行するコンピューターと同じドメインに存在している必要があります。</span><span class="sxs-lookup"><span data-stu-id="52f76-162">The server must be in the same domain as the computer from which you are running bm.exe.</span></span> <span data-ttu-id="52f76-163">サーバー名を指定しなかった場合、既定の名前 (localhost) が使用されます。</span><span class="sxs-lookup"><span data-stu-id="52f76-163">If the server name is not specified, bm.exe uses the default name of localhost.</span></span>|  
|<span data-ttu-id="52f76-164">データベース:\<データベース\></span><span class="sxs-lookup"><span data-stu-id="52f76-164">Database:\<database\></span></span>|<span data-ttu-id="52f76-165">省略可能: ビューが存在するデータベースの名前。</span><span class="sxs-lookup"><span data-stu-id="52f76-165">Optional: The name of the database on which the view resides.</span></span> <span data-ttu-id="52f76-166">指定しなかった場合、既定の名前 (BamPrimaryImport) が使用されます。</span><span class="sxs-lookup"><span data-stu-id="52f76-166">If the name is not specified, bm.exe uses the default name BamPrimaryImport.</span></span>|  
  
 <span data-ttu-id="52f76-167">指定されたビューからユーザーまたはグループのアクセス権を削除します。</span><span class="sxs-lookup"><span data-stu-id="52f76-167">Removes access rights for a user or group from a specified view.</span></span> <span data-ttu-id="52f76-168">ビューからアカウントを削除すると、指定されたビューに対して定義されている警告から、対応するアカウントとそのすべてのメンバーが削除されます。</span><span class="sxs-lookup"><span data-stu-id="52f76-168">Removing an account from a view removes that account and all of its members from alerts defined for the specified view.</span></span> <span data-ttu-id="52f76-169">そのアカウントが、警告の唯一の所有者であった場合は、現在のユーザー (admin) が、その警告の新しい所有者になります。</span><span class="sxs-lookup"><span data-stu-id="52f76-169">If that account is the sole owner of an alert, the current user (admin) becomes the new owner of the alert.</span></span>  
  
 <span data-ttu-id="52f76-170">**使用例**</span><span class="sxs-lookup"><span data-stu-id="52f76-170">**Examples**</span></span>  
  
```  
bm.exe remove-account -AccountName:john -View:PurchaseOrder  
bm.exe remove-account -AccountName:Agents -View:PO -Server:Srv1 -Database:Db2  
```  
  
## <a name="see-also"></a><span data-ttu-id="52f76-171">参照</span><span class="sxs-lookup"><span data-stu-id="52f76-171">See Also</span></span>  
 [<span data-ttu-id="52f76-172">BAM 管理ユーティリティ</span><span class="sxs-lookup"><span data-stu-id="52f76-172">BAM Management Utility</span></span>](../core/bam-management-utility.md)