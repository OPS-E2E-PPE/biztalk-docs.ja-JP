---
title: ユーザー管理コマンド |Microsoft Docs
ms.custom: ''
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: ''
ms.suite: ''
ms.tgt_pltfrm: ''
ms.topic: article
ms.assetid: feb12226-a4da-4fc5-93a1-aced239f60a9
caps.latest.revision: 9
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: b79ff5a6bc94faab130de5d7d793612f2130d732
ms.sourcegitcommit: 381e83d43796a345488d54b3f7413e11d56ad7be
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 05/07/2019
ms.locfileid: "65399960"
---
# <a name="user-management-commands"></a><span data-ttu-id="c39db-102">ユーザー管理コマンド</span><span class="sxs-lookup"><span data-stu-id="c39db-102">User Management Commands</span></span>
<span data-ttu-id="c39db-103">BAM 管理ユーティリティの警告のユーザー管理コマンドを使用すると、取得、追加、およびユーザーを削除できます。</span><span class="sxs-lookup"><span data-stu-id="c39db-103">The BAM Management utility alert user management commands allow you to get, add, and remove users.</span></span>  
  
-   <span data-ttu-id="c39db-104">get アカウント:すべてのユーザーと指定されたビューにアクセスできるグループの一覧を取得します。</span><span class="sxs-lookup"><span data-stu-id="c39db-104">get-accounts: Gets a list of all users and groups that can access a specified view.</span></span>  
  
-   <span data-ttu-id="c39db-105">追加のアカウント:指定されたビューを指定したユーザーまたはグループの権限のアクセス権を付与します。</span><span class="sxs-lookup"><span data-stu-id="c39db-105">add-account: Grants access rights for the specified user or group to the specified view.</span></span>  
  
-   <span data-ttu-id="c39db-106">削除-アカウント:指定されたビューからユーザーまたはグループの権限にアクセスして削除します。</span><span class="sxs-lookup"><span data-stu-id="c39db-106">remove-account: Removes access rights for a user or group from a specified view.</span></span>  
  
> [!NOTE]
>  <span data-ttu-id="c39db-107">含めることによって任意の BM ユーティリティ コマンドのトレースを有効にすることができます、 **-トレース: &#124;オフ**パラメーター スイッチ。</span><span class="sxs-lookup"><span data-stu-id="c39db-107">You can enable tracing on any BM utility command by including the **-Trace:on&#124;off** parameter switch.</span></span> <span data-ttu-id="c39db-108">トレース スイッチを使用するには、構成ファイルのトレース設定が上書きされます。</span><span class="sxs-lookup"><span data-stu-id="c39db-108">Using the Trace switch overrides the tracing settings in the configuration file.</span></span> <span data-ttu-id="c39db-109">スイッチは、通常の BM コマンドと組み合わせて使用できます。</span><span class="sxs-lookup"><span data-stu-id="c39db-109">The switch can be used in conjunction with any normal BM command.</span></span>  
  
> [!NOTE]
>  <span data-ttu-id="c39db-110">ユーザー アカウント制御 (UAC) をサポートするシステムでは、管理者特権を使用してこのツールを実行することが必要な場合があります。</span><span class="sxs-lookup"><span data-stu-id="c39db-110">On a system that supports User Account Control (UAC), you may need to run the tool with Administrative privileges.</span></span>  
  
## <a name="get-accounts-command"></a><span data-ttu-id="c39db-111">get-accounts コマンド</span><span class="sxs-lookup"><span data-stu-id="c39db-111">get-accounts Command</span></span>  
 <span data-ttu-id="c39db-112">**使用方法**</span><span class="sxs-lookup"><span data-stu-id="c39db-112">**Usage**</span></span>  
  
 <span data-ttu-id="c39db-113">**bm.exe get-accounts -View:\<view name\>[ -Server:\<server\> ][ -Database:\<database\> ]**</span><span class="sxs-lookup"><span data-stu-id="c39db-113">**bm.exe get-accounts -View:\<view name\>[ -Server:\<server\> ][ -Database:\<database\> ]**</span></span>  
  
 <span data-ttu-id="c39db-114">**パラメーター**</span><span class="sxs-lookup"><span data-stu-id="c39db-114">**Parameters**</span></span>  
  
|<span data-ttu-id="c39db-115">パラメーター</span><span class="sxs-lookup"><span data-stu-id="c39db-115">Parameter</span></span>|<span data-ttu-id="c39db-116">説明</span><span class="sxs-lookup"><span data-stu-id="c39db-116">Description</span></span>|  
|---------------|-----------------|  
|<span data-ttu-id="c39db-117">ビュー:\<ビュー名\></span><span class="sxs-lookup"><span data-stu-id="c39db-117">View:\<view name\></span></span>|<span data-ttu-id="c39db-118">アカウントを一覧表示する対象のビューの名前。</span><span class="sxs-lookup"><span data-stu-id="c39db-118">The name of the view for which to list accounts.</span></span>|  
|<span data-ttu-id="c39db-119">サーバー:\<サーバー\></span><span class="sxs-lookup"><span data-stu-id="c39db-119">Server:\<server\></span></span>|<span data-ttu-id="c39db-120">省略可能:アカウントの取得元となるサーバーの名前。</span><span class="sxs-lookup"><span data-stu-id="c39db-120">Optional: The name of the server from which to retrieve the accounts.</span></span> <span data-ttu-id="c39db-121">サーバーは、bm.exe を実行するコンピューターと同じドメインにある必要があります。</span><span class="sxs-lookup"><span data-stu-id="c39db-121">The server must be in the same domain as the computer from which you are running bm.exe.</span></span> <span data-ttu-id="c39db-122">サーバー名が指定されていない場合、bm.exe には、localhost の既定の名前が使用されます。</span><span class="sxs-lookup"><span data-stu-id="c39db-122">If the server name is not specified, bm.exe uses the default name of localhost.</span></span>|  
|<span data-ttu-id="c39db-123">データベース:\<データベース\></span><span class="sxs-lookup"><span data-stu-id="c39db-123">Database:\<database\></span></span>|<span data-ttu-id="c39db-124">省略可能:アカウントの取得元となるデータベースの名前。</span><span class="sxs-lookup"><span data-stu-id="c39db-124">Optional: The name of the database from which to retrieve the accounts.</span></span> <span data-ttu-id="c39db-125">名前が指定されていない場合、bm.exe には、BamPrimaryImport の既定の名前が使用されます。</span><span class="sxs-lookup"><span data-stu-id="c39db-125">If the name is not specified, bm.exe uses the default name BamPrimaryImport.</span></span>|  
  
 <span data-ttu-id="c39db-126">すべてのユーザーと、指定されたビューにアクセスできるグループを一覧表示します。</span><span class="sxs-lookup"><span data-stu-id="c39db-126">Lists all users and groups that can access the specified view.</span></span>  
  
 <span data-ttu-id="c39db-127">**使用例**</span><span class="sxs-lookup"><span data-stu-id="c39db-127">**Examples**</span></span>  
  
 `bm.exe get-accounts -View:PurchaseOrder`  
  
 `bm.exe get-accounts -View:ShipmentOrder -Server:Ship -Database:ShipDatabase`  
  
## <a name="add-account-command"></a><span data-ttu-id="c39db-128">add-account コマンド</span><span class="sxs-lookup"><span data-stu-id="c39db-128">add-account Command</span></span>  
 <span data-ttu-id="c39db-129">**使用方法**</span><span class="sxs-lookup"><span data-stu-id="c39db-129">**Usage**</span></span>  
  
 <span data-ttu-id="c39db-130">**bm.exe add-account -AccountName:\<account name\> -View:\<view name\>[ -Server:\<server\> ][ -Database:\<database\> ]**</span><span class="sxs-lookup"><span data-stu-id="c39db-130">**bm.exe add-account -AccountName:\<account name\> -View:\<view name\>[ -Server:\<server\> ][ -Database:\<database\> ]**</span></span>  
  
 <span data-ttu-id="c39db-131">**パラメーター**</span><span class="sxs-lookup"><span data-stu-id="c39db-131">**Parameters**</span></span>  
  
|<span data-ttu-id="c39db-132">パラメーター</span><span class="sxs-lookup"><span data-stu-id="c39db-132">Parameter</span></span>|<span data-ttu-id="c39db-133">説明</span><span class="sxs-lookup"><span data-stu-id="c39db-133">Description</span></span>|  
|---------------|-----------------|  
|<span data-ttu-id="c39db-134">AccountName: < アカウント名</span><span class="sxs-lookup"><span data-stu-id="c39db-134">AccountName:<account name</span></span>|<span data-ttu-id="c39db-135">権限を付与するアカウントの名前。</span><span class="sxs-lookup"><span data-stu-id="c39db-135">The name of the account to which rights are granted.</span></span>|  
|<span data-ttu-id="c39db-136">ビュー:\<ビュー名\></span><span class="sxs-lookup"><span data-stu-id="c39db-136">View:\<view name\></span></span>|<span data-ttu-id="c39db-137">権限を付与するビューの名前。</span><span class="sxs-lookup"><span data-stu-id="c39db-137">The name of the view to which rights are granted.</span></span>|  
|<span data-ttu-id="c39db-138">サーバー:\<サーバー\></span><span class="sxs-lookup"><span data-stu-id="c39db-138">Server:\<server\></span></span>|<span data-ttu-id="c39db-139">省略可能:ビューが存在するサーバーの名前。</span><span class="sxs-lookup"><span data-stu-id="c39db-139">Optional: The name of the server on which the view resides.</span></span> <span data-ttu-id="c39db-140">サーバーは、bm.exe を実行するコンピューターと同じドメインにある必要があります。</span><span class="sxs-lookup"><span data-stu-id="c39db-140">The server must be in the same domain as the computer from which you are running bm.exe.</span></span> <span data-ttu-id="c39db-141">サーバー名が指定されていない場合、bm.exe には、localhost の既定の名前が使用されます。</span><span class="sxs-lookup"><span data-stu-id="c39db-141">If the server name is not specified, bm.exe uses the default name of localhost.</span></span>|  
|<span data-ttu-id="c39db-142">データベース:\<データベース\></span><span class="sxs-lookup"><span data-stu-id="c39db-142">Database:\<database\></span></span>|<span data-ttu-id="c39db-143">省略可能:ビューが存在するデータベースの名前。</span><span class="sxs-lookup"><span data-stu-id="c39db-143">Optional: The name of the database on which the view resides.</span></span> <span data-ttu-id="c39db-144">名前が指定されていない場合、bm.exe には、BamPrimaryImport の既定の名前が使用されます。</span><span class="sxs-lookup"><span data-stu-id="c39db-144">If the name is not specified, bm.exe uses the default name BamPrimaryImport.</span></span>|  
  
 <span data-ttu-id="c39db-145">指定したユーザーまたはグループを指定されたビューのアクセス権を付与します。</span><span class="sxs-lookup"><span data-stu-id="c39db-145">Grants the specified user or group access rights to the specified view.</span></span>  
  
> [!IMPORTANT]
>  <span data-ttu-id="c39db-146">リアルタイム集計 (Rta) を使用している場合で追加されたユーザー**アカウントの追加**コマンドでは SQL Server へのログオン権限が自動的に付与されません。</span><span class="sxs-lookup"><span data-stu-id="c39db-146">If you are using Real Time Aggregations (RTAs), users added with **add-account** command are not automatically granted logon rights to SQL Server.</span></span> <span data-ttu-id="c39db-147">RTA を使用している場合は、RTA のビューを表示しなければならないすべてのユーザーを含む、Windows ユーザー グループの作成を検討してください。</span><span class="sxs-lookup"><span data-stu-id="c39db-147">If you are using RTAs, consider establishing a Windows user group that contains all of the users that need to see views of the RTAs.</span></span> <span data-ttu-id="c39db-148">そのグループ BAM プライマリ インポート データベースをホストする SQL server で SQL Server ログオン権限を明示的に許可します。</span><span class="sxs-lookup"><span data-stu-id="c39db-148">Grant that group explicit SQL Server logon rights on the SQL server hosting the BAM Primary Import databases.</span></span>  
  
 <span data-ttu-id="c39db-149">**使用例**</span><span class="sxs-lookup"><span data-stu-id="c39db-149">**Examples**</span></span>  
  
```  
bm.exe add-account -AccountName:john -View:PurchaseOrder  
bm.exe add-account -AccountName:Agents -View:PO -Server:Srv1 -Database:Db2  
```  
  
## <a name="remove-account-command"></a><span data-ttu-id="c39db-150">remove-account コマンド</span><span class="sxs-lookup"><span data-stu-id="c39db-150">remove-account Command</span></span>  
 <span data-ttu-id="c39db-151">**使用方法**</span><span class="sxs-lookup"><span data-stu-id="c39db-151">**Usage**</span></span>  
  
 <span data-ttu-id="c39db-152">**bm.exe remove-account -AccountName:\<account name\> -View:\<view name\>[ -Server:\<server\> ][ -Database:\<database\> ]**</span><span class="sxs-lookup"><span data-stu-id="c39db-152">**bm.exe remove-account -AccountName:\<account name\> -View:\<view name\>[ -Server:\<server\> ][ -Database:\<database\> ]**</span></span>  
  
 <span data-ttu-id="c39db-153">**パラメーター**</span><span class="sxs-lookup"><span data-stu-id="c39db-153">**Parameters**</span></span>  
  
|<span data-ttu-id="c39db-154">パラメーター</span><span class="sxs-lookup"><span data-stu-id="c39db-154">Parameter</span></span>|<span data-ttu-id="c39db-155">説明</span><span class="sxs-lookup"><span data-stu-id="c39db-155">Description</span></span>|  
|---------------|-----------------|  
|<span data-ttu-id="c39db-156">AccountName:\<アカウント名\></span><span class="sxs-lookup"><span data-stu-id="c39db-156">AccountName:\<account name\></span></span>|<span data-ttu-id="c39db-157">ビューに対する権限を削除するアカウントの名前。</span><span class="sxs-lookup"><span data-stu-id="c39db-157">The name of the account from which to remove rights to the view.</span></span>|  
|<span data-ttu-id="c39db-158">ビュー:\<ビュー名\></span><span class="sxs-lookup"><span data-stu-id="c39db-158">View:\<view name\></span></span>|<span data-ttu-id="c39db-159">権限を削除するビューの名前。</span><span class="sxs-lookup"><span data-stu-id="c39db-159">The name of the view to which rights are removed.</span></span>|  
|<span data-ttu-id="c39db-160">サーバー:\<サーバー\></span><span class="sxs-lookup"><span data-stu-id="c39db-160">Server:\<server\></span></span>|<span data-ttu-id="c39db-161">省略可能:ビューが存在するサーバーの名前。</span><span class="sxs-lookup"><span data-stu-id="c39db-161">Optional: The name of the server on which the view resides.</span></span> <span data-ttu-id="c39db-162">サーバーは、bm.exe を実行するコンピューターと同じドメインにある必要があります。</span><span class="sxs-lookup"><span data-stu-id="c39db-162">The server must be in the same domain as the computer from which you are running bm.exe.</span></span> <span data-ttu-id="c39db-163">サーバー名が指定されていない場合、bm.exe には、localhost の既定の名前が使用されます。</span><span class="sxs-lookup"><span data-stu-id="c39db-163">If the server name is not specified, bm.exe uses the default name of localhost.</span></span>|  
|<span data-ttu-id="c39db-164">データベース:\<データベース\></span><span class="sxs-lookup"><span data-stu-id="c39db-164">Database:\<database\></span></span>|<span data-ttu-id="c39db-165">省略可能:ビューが存在するデータベースの名前。</span><span class="sxs-lookup"><span data-stu-id="c39db-165">Optional: The name of the database on which the view resides.</span></span> <span data-ttu-id="c39db-166">名前が指定されていない場合、bm.exe には、BamPrimaryImport の既定の名前が使用されます。</span><span class="sxs-lookup"><span data-stu-id="c39db-166">If the name is not specified, bm.exe uses the default name BamPrimaryImport.</span></span>|  
  
 <span data-ttu-id="c39db-167">指定されたビューからユーザーまたはグループの権限にアクセスして削除します。</span><span class="sxs-lookup"><span data-stu-id="c39db-167">Removes access rights for a user or group from a specified view.</span></span> <span data-ttu-id="c39db-168">ビューからアカウントを削除する、指定されたビューに定義された警告からそのアカウントとそのすべてのメンバーを削除します。</span><span class="sxs-lookup"><span data-stu-id="c39db-168">Removing an account from a view removes that account and all of its members from alerts defined for the specified view.</span></span> <span data-ttu-id="c39db-169">そのアカウントが、警告の唯一の所有者である場合は、現在のユーザー (管理者) は、アラートの新しい所有者になります。</span><span class="sxs-lookup"><span data-stu-id="c39db-169">If that account is the sole owner of an alert, the current user (admin) becomes the new owner of the alert.</span></span>  
  
 <span data-ttu-id="c39db-170">**使用例**</span><span class="sxs-lookup"><span data-stu-id="c39db-170">**Examples**</span></span>  
  
```  
bm.exe remove-account -AccountName:john -View:PurchaseOrder  
bm.exe remove-account -AccountName:Agents -View:PO -Server:Srv1 -Database:Db2  
```  
  
## <a name="see-also"></a><span data-ttu-id="c39db-171">参照</span><span class="sxs-lookup"><span data-stu-id="c39db-171">See Also</span></span>  
 [<span data-ttu-id="c39db-172">BAM 管理ユーティリティ</span><span class="sxs-lookup"><span data-stu-id="c39db-172">BAM Management Utility</span></span>](../core/bam-management-utility.md)