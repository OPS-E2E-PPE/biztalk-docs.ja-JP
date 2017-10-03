---
title: "アクティビティ管理コマンド |Microsoft ドキュメント"
ms.custom: 
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: 
ms.suite: 
ms.tgt_pltfrm: 
ms.topic: article
ms.assetid: 34db54f3-4116-49de-880b-c9891a38d2e7
caps.latest.revision: "11"
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: d90c5f394ed32b68f4f9b747c580fac02e22a8ed
ms.sourcegitcommit: cb908c540d8f1a692d01dc8f313e16cb4b4e696d
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 09/20/2017
---
# <a name="activity-management-commands"></a><span data-ttu-id="e960a-102">アクティビティ管理コマンド</span><span class="sxs-lookup"><span data-stu-id="e960a-102">Activity Management Commands</span></span>
<span data-ttu-id="e960a-103">BAM 管理ユーティリティのアクティビティ管理コマンドを使用すると、展開済みアクティビティを操作できます。</span><span class="sxs-lookup"><span data-stu-id="e960a-103">The BAM Management utility activity management commands allow you to work with deployed activities.</span></span>  
  
-   <span data-ttu-id="e960a-104">get アクティビティ: 展開済みアクティビティの一覧を取得します。</span><span class="sxs-lookup"><span data-stu-id="e960a-104">get-activities: Gets a list of deployed activities.</span></span>  
  
-   <span data-ttu-id="e960a-105">削除アクティビティ: アクティビティを削除します。</span><span class="sxs-lookup"><span data-stu-id="e960a-105">remove-activity: Removes an activity.</span></span>  
  
-   <span data-ttu-id="e960a-106">get activitywindow: アクティビティの期間を取得します。</span><span class="sxs-lookup"><span data-stu-id="e960a-106">get-activitywindow: Gets the duration for an activity.</span></span>  
  
-   <span data-ttu-id="e960a-107">セット activitywindow: アクティビティのアクティビティの期間を設定します。</span><span class="sxs-lookup"><span data-stu-id="e960a-107">set-activitywindow: Sets the activity duration for an activity.</span></span>  
  
-   <span data-ttu-id="e960a-108">get index: インデックスの一覧を取得します。</span><span class="sxs-lookup"><span data-stu-id="e960a-108">get-index: Gets the list of indexes.</span></span>  
  
-   <span data-ttu-id="e960a-109">インデックスの作成: 新しいインデックスを作成します。</span><span class="sxs-lookup"><span data-stu-id="e960a-109">create-index: Creates a new index.</span></span>  
  
-   <span data-ttu-id="e960a-110">delete インデックス: インデックスを削除します。</span><span class="sxs-lookup"><span data-stu-id="e960a-110">delete-index: Deletes an index.</span></span>  
  
-   <span data-ttu-id="e960a-111">get アーカイブ: アーカイブ済みアクティビティの動作を取得します。</span><span class="sxs-lookup"><span data-stu-id="e960a-111">get-archive: Gets the behavior of archived activity.</span></span>  
  
-   <span data-ttu-id="e960a-112">セット アーカイブ: アーカイブ済みアクティビティの動作を設定します。</span><span class="sxs-lookup"><span data-stu-id="e960a-112">set-archive: Sets the behavior of archived activity.</span></span>  
  
> [!NOTE]
>  <span data-ttu-id="e960a-113">含めることで任意の BAM ユーティリティ コマンドのトレースを有効にすることができます、 **-トレース: で & #124 オフ**パラメーター スイッチ。</span><span class="sxs-lookup"><span data-stu-id="e960a-113">You can enable tracing on any BAM utility command by including the **-Trace:on&#124;off** parameter switch.</span></span> <span data-ttu-id="e960a-114">Trace スイッチを使用すると、構成ファイルのトレース設定が上書きされます。</span><span class="sxs-lookup"><span data-stu-id="e960a-114">Using the Trace switch overrides the tracing settings in the configuration file.</span></span> <span data-ttu-id="e960a-115">このスイッチは、通常の BAM コマンドと組み合わせて使用できます。</span><span class="sxs-lookup"><span data-stu-id="e960a-115">The switch can be used in conjunction with any normal BAM command.</span></span>  
  
> [!NOTE]
>  <span data-ttu-id="e960a-116">ユーザー アカウント制御 (UAC) をサポートするシステムでは、管理者特権を使用してこのツールを実行することが必要な場合があります。</span><span class="sxs-lookup"><span data-stu-id="e960a-116">On a system that supports User Account Control (UAC), you may need to run the tool with Administrative privileges.</span></span>  
  
## <a name="get-activities-command"></a><span data-ttu-id="e960a-117">get-activities コマンド</span><span class="sxs-lookup"><span data-stu-id="e960a-117">get-activities Command</span></span>  
 <span data-ttu-id="e960a-118">**使用方法**</span><span class="sxs-lookup"><span data-stu-id="e960a-118">**Usage**</span></span>  
  
 <span data-ttu-id="e960a-119">**bm.exe の取得活動 [-ビュー:\<ビュー名 >] [-サーバー:\<サーバー >] [-データベース:\<データベース >]**</span><span class="sxs-lookup"><span data-stu-id="e960a-119">**bm.exe get-activities [ -View:\<view name> ][ -Server:\<server> ][ -Database:\<database> ]**</span></span>  
  
 <span data-ttu-id="e960a-120">**パラメーター**</span><span class="sxs-lookup"><span data-stu-id="e960a-120">**Parameters**</span></span>  
  
|<span data-ttu-id="e960a-121">パラメーター</span><span class="sxs-lookup"><span data-stu-id="e960a-121">Parameter</span></span>|<span data-ttu-id="e960a-122">Description</span><span class="sxs-lookup"><span data-stu-id="e960a-122">Description</span></span>|  
|---------------|-----------------|  
|<span data-ttu-id="e960a-123">[名前]:\<アクティビティ名 ></span><span class="sxs-lookup"><span data-stu-id="e960a-123">Name:\<activity name></span></span>|<span data-ttu-id="e960a-124">削除するアクティビティの名前です。</span><span class="sxs-lookup"><span data-stu-id="e960a-124">The name of the activity to remove.</span></span>|  
|<span data-ttu-id="e960a-125">サーバー:\<サーバー ></span><span class="sxs-lookup"><span data-stu-id="e960a-125">Server:\<server></span></span>|<span data-ttu-id="e960a-126">省略可能: アクティビティの一覧を取得するサーバーの名前。</span><span class="sxs-lookup"><span data-stu-id="e960a-126">Optional: The name of the server from which to get the list of activities.</span></span> <span data-ttu-id="e960a-127">このサーバーは、bm.exe を実行するコンピューターと同じドメインに存在している必要があります。</span><span class="sxs-lookup"><span data-stu-id="e960a-127">The server must be in the same domain as the computer from which you are running bm.exe.</span></span> <span data-ttu-id="e960a-128">サーバー名を指定しなかった場合、既定の名前 (localhost) が使用されます。</span><span class="sxs-lookup"><span data-stu-id="e960a-128">If the server name is not specified, bm.exe uses the default name of localhost.</span></span>|  
|<span data-ttu-id="e960a-129">データベース:\<データベース ></span><span class="sxs-lookup"><span data-stu-id="e960a-129">Database:\<database></span></span>|<span data-ttu-id="e960a-130">省略可能: アクティビティの一覧の取得元のデータベースの名前。</span><span class="sxs-lookup"><span data-stu-id="e960a-130">Optional: The name of the database from which to get the list of activities.</span></span> <span data-ttu-id="e960a-131">指定しなかった場合、既定の名前 (BamPrimaryImport) が使用されます。</span><span class="sxs-lookup"><span data-stu-id="e960a-131">If the name is not specified, bm.exe uses the default name BamPrimaryImport.</span></span>|  
  
 <span data-ttu-id="e960a-132">このコマンドを実行したコンピューターに展開されているアクティビティが一覧表示されます。</span><span class="sxs-lookup"><span data-stu-id="e960a-132">Lists the activities deployed on the computer on which the command is executed.</span></span>  
  
 <span data-ttu-id="e960a-133">**使用例**</span><span class="sxs-lookup"><span data-stu-id="e960a-133">**Examples**</span></span>  
  
```  
bm.exe get-activities -View:SalesManagerView  
bm.exe get-activities -Server:MyServer -Database:MyPrimaryImport  
```  
  
## <a name="remove-activity-command"></a><span data-ttu-id="e960a-134">remove-activity コマンド</span><span class="sxs-lookup"><span data-stu-id="e960a-134">remove-activity Command</span></span>  
 <span data-ttu-id="e960a-135">**使用方法**</span><span class="sxs-lookup"><span data-stu-id="e960a-135">**Usage**</span></span>  
  
 <span data-ttu-id="e960a-136">**bm.exe 削除アクティビティの名前:\<アクティビティ名 > [-サーバー:\<サーバー >] [-データベース:\<データベース >]**</span><span class="sxs-lookup"><span data-stu-id="e960a-136">**bm.exe remove-activity -Name:\<activity name>[ -Server:\<server> ][ -Database:\<database> ]**</span></span>  
  
 <span data-ttu-id="e960a-137">**パラメーター**</span><span class="sxs-lookup"><span data-stu-id="e960a-137">**Parameters**</span></span>  
  
|<span data-ttu-id="e960a-138">パラメーター</span><span class="sxs-lookup"><span data-stu-id="e960a-138">Parameter</span></span>|<span data-ttu-id="e960a-139">Description</span><span class="sxs-lookup"><span data-stu-id="e960a-139">Description</span></span>|  
|---------------|-----------------|  
|<span data-ttu-id="e960a-140">[名前]:\<アクティビティ名 ></span><span class="sxs-lookup"><span data-stu-id="e960a-140">Name:\<activity name></span></span>|<span data-ttu-id="e960a-141">削除するアクティビティの名前です。</span><span class="sxs-lookup"><span data-stu-id="e960a-141">The name of the activity to remove.</span></span>|  
|<span data-ttu-id="e960a-142">サーバー:\<サーバー ></span><span class="sxs-lookup"><span data-stu-id="e960a-142">Server:\<server></span></span>|<span data-ttu-id="e960a-143">省略可能: アクティビティを削除するサーバーの名前。</span><span class="sxs-lookup"><span data-stu-id="e960a-143">Optional: The name of the server from which to remove the activity.</span></span> <span data-ttu-id="e960a-144">このサーバーは、bm.exe を実行するコンピューターと同じドメインに存在している必要があります。</span><span class="sxs-lookup"><span data-stu-id="e960a-144">The server must be in the same domain as the computer from which you are running bm.exe.</span></span> <span data-ttu-id="e960a-145">サーバー名を指定しなかった場合、既定の名前 (localhost) が使用されます。</span><span class="sxs-lookup"><span data-stu-id="e960a-145">If the server name is not specified, bm.exe uses the default name of localhost.</span></span>|  
|<span data-ttu-id="e960a-146">データベース:\<データベース ></span><span class="sxs-lookup"><span data-stu-id="e960a-146">Database:\<database></span></span>|<span data-ttu-id="e960a-147">省略可能: アクティビティを削除するデータベースの名前。</span><span class="sxs-lookup"><span data-stu-id="e960a-147">Optional: The name of the database from which to remove the activity.</span></span> <span data-ttu-id="e960a-148">指定しなかった場合、既定の名前 (BamPrimaryImport) が使用されます。</span><span class="sxs-lookup"><span data-stu-id="e960a-148">If the name is not specified, bm.exe uses the default name BamPrimaryImport.</span></span>|  
  
 <span data-ttu-id="e960a-149">指定されたアクティビティを BAM プライマリ インポート データベースから削除します。</span><span class="sxs-lookup"><span data-stu-id="e960a-149">Removes the specified activity from the BAM Primary Import database.</span></span> <span data-ttu-id="e960a-150">そのアクティビティに依存するビューが存在する場合、コマンドの実行は失敗し、エラーが報告されます。</span><span class="sxs-lookup"><span data-stu-id="e960a-150">If the activity has dependent views, the command will fail and report an error.</span></span> <span data-ttu-id="e960a-151">remove-view コマンドを使用して、アクティビティに依存するすべてのビューを削除してから、remove-activity コマンドを再度実行してください。</span><span class="sxs-lookup"><span data-stu-id="e960a-151">Use the remove-view command to remove all the dependent views and execute the remove-activity command again.</span></span>  
  
 <span data-ttu-id="e960a-152">**使用例**</span><span class="sxs-lookup"><span data-stu-id="e960a-152">**Examples**</span></span>  
  
```  
bm.exe remove-activity -Name:PurchaseOrder  
bm.exe remove-activity -Name:PO -Server:MyServer -Database:MyPrimaryImport  
```  
  
## <a name="get-activitywindow-command"></a><span data-ttu-id="e960a-153">get-activitywindow コマンド</span><span class="sxs-lookup"><span data-stu-id="e960a-153">get-activitywindow Command</span></span>  
 <span data-ttu-id="e960a-154">**使用方法**</span><span class="sxs-lookup"><span data-stu-id="e960a-154">**Usage**</span></span>  
  
 <span data-ttu-id="e960a-155">**bm.exe get activitywindow-アクティビティ:\<アクティビティ名 > [-サーバー:\<サーバー >] [-データベース:\<データベース >]**</span><span class="sxs-lookup"><span data-stu-id="e960a-155">**bm.exe get-activitywindow -Activity:\<activity name>[ -Server:\<server> ][ -Database:\<database> ]**</span></span>  
  
 <span data-ttu-id="e960a-156">**パラメーター**</span><span class="sxs-lookup"><span data-stu-id="e960a-156">**Parameters**</span></span>  
  
|<span data-ttu-id="e960a-157">パラメーター</span><span class="sxs-lookup"><span data-stu-id="e960a-157">Parameter</span></span>|<span data-ttu-id="e960a-158">Description</span><span class="sxs-lookup"><span data-stu-id="e960a-158">Description</span></span>|  
|---------------|-----------------|  
|<span data-ttu-id="e960a-159">アクティビティ:\<アクティビティ名 ></span><span class="sxs-lookup"><span data-stu-id="e960a-159">Activity:\<activity name></span></span>|<span data-ttu-id="e960a-160">.Activity の名前。</span><span class="sxs-lookup"><span data-stu-id="e960a-160">The name of the .activity.</span></span>|  
|<span data-ttu-id="e960a-161">サーバー:\<サーバー ></span><span class="sxs-lookup"><span data-stu-id="e960a-161">Server:\<server></span></span>|<span data-ttu-id="e960a-162">省略可能: アクティビティが存在するサーバーの名前。</span><span class="sxs-lookup"><span data-stu-id="e960a-162">Optional: The name of the server on which the activity resides.</span></span> <span data-ttu-id="e960a-163">このサーバーは、bm.exe を実行するコンピューターと同じドメインに存在している必要があります。</span><span class="sxs-lookup"><span data-stu-id="e960a-163">The server must be in the same domain as the computer from which you are running bm.exe.</span></span> <span data-ttu-id="e960a-164">サーバー名を指定しなかった場合、既定の名前 (localhost) が使用されます。</span><span class="sxs-lookup"><span data-stu-id="e960a-164">If the server name is not specified, bm.exe uses the default name of localhost.</span></span>|  
|<span data-ttu-id="e960a-165">データベース:\<データベース ></span><span class="sxs-lookup"><span data-stu-id="e960a-165">Database:\<database></span></span>|<span data-ttu-id="e960a-166">省略可能: アクティビティが存在するデータベースの名前。</span><span class="sxs-lookup"><span data-stu-id="e960a-166">Optional: The name of the database on which the activity resides.</span></span> <span data-ttu-id="e960a-167">指定しなかった場合、既定の名前 (BamPrimaryImport) が使用されます。</span><span class="sxs-lookup"><span data-stu-id="e960a-167">If the name is not specified, bm.exe uses the default name BamPrimaryImport.</span></span>|  
  
 <span data-ttu-id="e960a-168">指定されたアクティビティの期間を表示します。</span><span class="sxs-lookup"><span data-stu-id="e960a-168">Displays the duration for the specified activity.</span></span> <span data-ttu-id="e960a-169">このコマンドにより、期間の長さと、その期間の基準となる単位が返されます。</span><span class="sxs-lookup"><span data-stu-id="e960a-169">The command returns the length of the duration and the units by which the duration is measured.</span></span>  
  
 <span data-ttu-id="e960a-170">**使用例**</span><span class="sxs-lookup"><span data-stu-id="e960a-170">**Examples**</span></span>  
  
```  
bm.exe get-activitywindow -Activity:PurchaseOrder  
bm.exe get-activitywindow -Activity:PO -Server:Ship -Database:ShipDatabase  
```  
  
## <a name="set-activitywindow-command"></a><span data-ttu-id="e960a-171">set-activitywindow コマンド</span><span class="sxs-lookup"><span data-stu-id="e960a-171">set-activitywindow Command</span></span>  
 <span data-ttu-id="e960a-172">**使用方法**</span><span class="sxs-lookup"><span data-stu-id="e960a-172">**Usage**</span></span>  
  
 <span data-ttu-id="e960a-173">**bm.exe セット activitywindow-アクティビティ:\<アクティビティ名 > - TimeLength:\<整数の番号 > - TimeUnit: 月 &#124; 日付 & #124 です。1 時間 & #124 です。分 [-サーバー:\<サーバー >] [-データベース:\<データベース >]**</span><span class="sxs-lookup"><span data-stu-id="e960a-173">**bm.exe set-activitywindow -Activity:\<activity name> -TimeLength:\<integer number> -TimeUnit:Month&#124;Day&#124;Hour&#124;Minute[ -Server:\<server> ][ -Database:\<database> ]**</span></span>  
  
 <span data-ttu-id="e960a-174">**パラメーター**</span><span class="sxs-lookup"><span data-stu-id="e960a-174">**Parameters**</span></span>  
  
|<span data-ttu-id="e960a-175">パラメーター</span><span class="sxs-lookup"><span data-stu-id="e960a-175">Parameter</span></span>|<span data-ttu-id="e960a-176">Description</span><span class="sxs-lookup"><span data-stu-id="e960a-176">Description</span></span>|  
|---------------|-----------------|  
|<span data-ttu-id="e960a-177">アクティビティ:\<アクティビティ名 ></span><span class="sxs-lookup"><span data-stu-id="e960a-177">Activity:\<activity name></span></span>|<span data-ttu-id="e960a-178">アクティビティの名前です。</span><span class="sxs-lookup"><span data-stu-id="e960a-178">The name of the activity.</span></span>|  
|<span data-ttu-id="e960a-179">TimeLength:\<整数 ></span><span class="sxs-lookup"><span data-stu-id="e960a-179">TimeLength:\<integer number></span></span>|<span data-ttu-id="e960a-180">アクティビティの期間です。</span><span class="sxs-lookup"><span data-stu-id="e960a-180">The duration for the activity.</span></span>|  
|<span data-ttu-id="e960a-181">TimeUnit:Month &#124; 日付 & #124 です。1 時間 & #124 です。1 分</span><span class="sxs-lookup"><span data-stu-id="e960a-181">TimeUnit:Month&#124;Day&#124;Hour&#124;Minute</span></span>|<span data-ttu-id="e960a-182">期間の測定単位。</span><span class="sxs-lookup"><span data-stu-id="e960a-182">The unit measure for the duration.</span></span>|  
|<span data-ttu-id="e960a-183">サーバー:\<サーバー ></span><span class="sxs-lookup"><span data-stu-id="e960a-183">Server:\<server></span></span>|<span data-ttu-id="e960a-184">省略可能: アクティビティが存在するサーバーの名前。</span><span class="sxs-lookup"><span data-stu-id="e960a-184">Optional: The name of the server on which the activity resides.</span></span> <span data-ttu-id="e960a-185">このサーバーは、bm.exe を実行するコンピューターと同じドメインに存在している必要があります。</span><span class="sxs-lookup"><span data-stu-id="e960a-185">The server must be in the same domain as the computer from which you are running bm.exe.</span></span> <span data-ttu-id="e960a-186">サーバー名を指定しなかった場合、既定の名前 (localhost) が使用されます。</span><span class="sxs-lookup"><span data-stu-id="e960a-186">If the server name is not specified, bm.exe uses the default name of localhost.</span></span>|  
|<span data-ttu-id="e960a-187">データベース:\<データベース ></span><span class="sxs-lookup"><span data-stu-id="e960a-187">Database:\<database></span></span>|<span data-ttu-id="e960a-188">省略可能: アクティビティが存在するデータベースの名前。</span><span class="sxs-lookup"><span data-stu-id="e960a-188">Optional: The name of the database on which the activity resides.</span></span> <span data-ttu-id="e960a-189">指定しなかった場合、既定の名前 (BamPrimaryImport) が使用されます。</span><span class="sxs-lookup"><span data-stu-id="e960a-189">If the name is not specified, bm.exe uses the default name BamPrimaryImport.</span></span>|  
  
 <span data-ttu-id="e960a-190">指定されたアクティビティの期間を設定します。</span><span class="sxs-lookup"><span data-stu-id="e960a-190">Sets the duration for the specified activity.</span></span>  
  
 <span data-ttu-id="e960a-191">**使用例**</span><span class="sxs-lookup"><span data-stu-id="e960a-191">**Examples**</span></span>  
  
```  
bm.exe set-activitywindow -Activity:PurchaseOrder -TimeLength:6 -TimeUnit:Day  
bm.exe set-activitywindow -Activity:PurchaseOrder -TimeLength:1 -TimeUnit:Month  
```  
  
## <a name="get-index-command"></a><span data-ttu-id="e960a-192">get-index コマンド</span><span class="sxs-lookup"><span data-stu-id="e960a-192">get-index Command</span></span>  
 <span data-ttu-id="e960a-193">**使用方法**</span><span class="sxs-lookup"><span data-stu-id="e960a-193">**Usage**</span></span>  
  
 <span data-ttu-id="e960a-194">**bm.exe get インデックス-アクティビティ:\<アクティビティ名 > [-サーバー:\<サーバー >] [-データベース:\<データベース >]**</span><span class="sxs-lookup"><span data-stu-id="e960a-194">**bm.exe get-index -Activity:\<activity name>[ -Server:\<server> ][ -Database:\<database> ]**</span></span>  
  
 <span data-ttu-id="e960a-195">**パラメーター**</span><span class="sxs-lookup"><span data-stu-id="e960a-195">**Parameters**</span></span>  
  
|<span data-ttu-id="e960a-196">パラメーター</span><span class="sxs-lookup"><span data-stu-id="e960a-196">Parameter</span></span>|<span data-ttu-id="e960a-197">Description</span><span class="sxs-lookup"><span data-stu-id="e960a-197">Description</span></span>|  
|---------------|-----------------|  
|<span data-ttu-id="e960a-198">アクティビティ:\<アクティビティ名 ></span><span class="sxs-lookup"><span data-stu-id="e960a-198">Activity:\<activity name></span></span>|<span data-ttu-id="e960a-199">アクティビティの名前です。</span><span class="sxs-lookup"><span data-stu-id="e960a-199">The name of the activity.</span></span>|  
|<span data-ttu-id="e960a-200">サーバー:\<サーバー ></span><span class="sxs-lookup"><span data-stu-id="e960a-200">Server:\<server></span></span>|<span data-ttu-id="e960a-201">省略可能: アクティビティが存在するサーバーの名前。</span><span class="sxs-lookup"><span data-stu-id="e960a-201">Optional: The name of the server on which the activity resides.</span></span> <span data-ttu-id="e960a-202">このサーバーは、bm.exe を実行するコンピューターと同じドメインに存在している必要があります。</span><span class="sxs-lookup"><span data-stu-id="e960a-202">The server must be in the same domain as the computer from which you are running bm.exe.</span></span> <span data-ttu-id="e960a-203">サーバー名を指定しなかった場合、既定の名前 (localhost) が使用されます。</span><span class="sxs-lookup"><span data-stu-id="e960a-203">If the server name is not specified, bm.exe uses the default name of localhost.</span></span>|  
|<span data-ttu-id="e960a-204">データベース:\<データベース ></span><span class="sxs-lookup"><span data-stu-id="e960a-204">Database:\<database></span></span>|<span data-ttu-id="e960a-205">省略可能: アクティビティが存在するデータベースの名前。</span><span class="sxs-lookup"><span data-stu-id="e960a-205">Optional: The name of the database on which the activity resides.</span></span> <span data-ttu-id="e960a-206">指定しなかった場合、既定の名前 (BamPrimaryImport) が使用されます。</span><span class="sxs-lookup"><span data-stu-id="e960a-206">If the name is not specified, bm.exe uses the default name BamPrimaryImport.</span></span>|  
  
 <span data-ttu-id="e960a-207">指定のアクティビティについて作成されたすべてのインデックスを一覧表示します。</span><span class="sxs-lookup"><span data-stu-id="e960a-207">Lists all the indexes that have been created for the specified activity.</span></span>  
  
 <span data-ttu-id="e960a-208">**使用例**</span><span class="sxs-lookup"><span data-stu-id="e960a-208">**Examples**</span></span>  
  
```  
bm.exe get-index -Activity:PurchaseOrder  
bm.exe get-index -Activity:PurchaseOrder -Server:Ship -Database:ShipDatabase  
```  
  
## <a name="create-index-command"></a><span data-ttu-id="e960a-209">create-index コマンド</span><span class="sxs-lookup"><span data-stu-id="e960a-209">create-index Command</span></span>  
 <span data-ttu-id="e960a-210">**使用方法**</span><span class="sxs-lookup"><span data-stu-id="e960a-210">**Usage**</span></span>  
  
 <span data-ttu-id="e960a-211">**bm.exe インデックスの作成-indexname:\<インデックス名 >-アクティビティ:\<アクティビティ名 >-チェックポイント:\<checkpoint1 > [、\<チェックポイント 2 >...][-サーバー:\<サーバー >] [-データベース:\<データベース >]**</span><span class="sxs-lookup"><span data-stu-id="e960a-211">**bm.exe create-index -IndexName:\<index name> -Activity:\<activity name> -Checkpoint:\<checkpoint1>[,\<checkpoint2>...][ -Server:\<server> ][ -Database:\<database> ]**</span></span>  
  
 <span data-ttu-id="e960a-212">**パラメーター**</span><span class="sxs-lookup"><span data-stu-id="e960a-212">**Parameters**</span></span>  
  
|<span data-ttu-id="e960a-213">パラメーター</span><span class="sxs-lookup"><span data-stu-id="e960a-213">Parameter</span></span>|<span data-ttu-id="e960a-214">Description</span><span class="sxs-lookup"><span data-stu-id="e960a-214">Description</span></span>|  
|---------------|-----------------|  
|<span data-ttu-id="e960a-215">IndexName:\<インデックス名 ></span><span class="sxs-lookup"><span data-stu-id="e960a-215">IndexName:\<index name></span></span>|<span data-ttu-id="e960a-216">新しいインデックスの名前です。</span><span class="sxs-lookup"><span data-stu-id="e960a-216">The name of the new index.</span></span>|  
|<span data-ttu-id="e960a-217">アクティビティ:\<アクティビティ名 ></span><span class="sxs-lookup"><span data-stu-id="e960a-217">Activity:\<activity name></span></span>|<span data-ttu-id="e960a-218">インデックスが作成されるアクティビティの名前。</span><span class="sxs-lookup"><span data-stu-id="e960a-218">The name of the activity for which the index is created.</span></span>|  
|<span data-ttu-id="e960a-219">チェックポイント:\<checkpoint1 > [、\<チェックポイント 2 >...]</span><span class="sxs-lookup"><span data-stu-id="e960a-219">Checkpoint:\<checkpoint1>[,\<checkpoint2>...]</span></span>|<span data-ttu-id="e960a-220">インデックスの一連のチェックポイントをコンマ区切りで指定します。</span><span class="sxs-lookup"><span data-stu-id="e960a-220">A comma-delimited list of checkpoints for the index.</span></span>|  
|<span data-ttu-id="e960a-221">サーバー:\<サーバー ></span><span class="sxs-lookup"><span data-stu-id="e960a-221">Server:\<server></span></span>|<span data-ttu-id="e960a-222">省略可能: アクティビティが存在するサーバーの名前。</span><span class="sxs-lookup"><span data-stu-id="e960a-222">Optional: The name of the server on which the activity resides.</span></span> <span data-ttu-id="e960a-223">このサーバーは、bm.exe を実行するコンピューターと同じドメインに存在している必要があります。</span><span class="sxs-lookup"><span data-stu-id="e960a-223">The server must be in the same domain as the computer from which you are running bm.exe.</span></span> <span data-ttu-id="e960a-224">サーバー名を指定しなかった場合、既定の名前 (localhost) が使用されます。</span><span class="sxs-lookup"><span data-stu-id="e960a-224">If the server name is not specified, bm.exe uses the default name of localhost.</span></span>|  
|<span data-ttu-id="e960a-225">データベース:\<データベース ></span><span class="sxs-lookup"><span data-stu-id="e960a-225">Database:\<database></span></span>|<span data-ttu-id="e960a-226">省略可能: アクティビティが存在するデータベースの名前。</span><span class="sxs-lookup"><span data-stu-id="e960a-226">Optional: The name of the database on which the activity resides.</span></span> <span data-ttu-id="e960a-227">指定しなかった場合、既定の名前 (BamPrimaryImport) が使用されます。</span><span class="sxs-lookup"><span data-stu-id="e960a-227">If the name is not specified, bm.exe uses the default name BamPrimaryImport.</span></span>|  
  
 <span data-ttu-id="e960a-228">指定されたチェックポイントを使用して、指定されたアクティビティのインデックスを作成します。</span><span class="sxs-lookup"><span data-stu-id="e960a-228">Creates an index for the specified activity using the specified checkpoints.</span></span>  
  
 <span data-ttu-id="e960a-229">**使用例**</span><span class="sxs-lookup"><span data-stu-id="e960a-229">**Examples**</span></span>  
  
```  
bm.exe create-index -IndexName:Idx1 -Activity:PO -Checkpoint:State,City  
bm.exe create-index -IndexName:Idx2 -Activity:PO -Checkpoint:Amount -Server:S1  
```  
  
## <a name="delete-index-command"></a><span data-ttu-id="e960a-230">delete-index コマンド</span><span class="sxs-lookup"><span data-stu-id="e960a-230">delete-index Command</span></span>  
 <span data-ttu-id="e960a-231">**使用方法**</span><span class="sxs-lookup"><span data-stu-id="e960a-231">**Usage**</span></span>  
  
 <span data-ttu-id="e960a-232">**bm.exe delete インデックス-indexname:\<インデックス名 >-アクティビティ:\<アクティビティ名 > [-サーバー:\<サーバー >] [-データベース:\<データベース >]**</span><span class="sxs-lookup"><span data-stu-id="e960a-232">**bm.exe delete-index -IndexName:\<index name> -Activity:\<activity name>[ -Server:\<server> ][ -Database:\<database> ]**</span></span>  
  
 <span data-ttu-id="e960a-233">**パラメーター**</span><span class="sxs-lookup"><span data-stu-id="e960a-233">**Parameters**</span></span>  
  
|<span data-ttu-id="e960a-234">パラメーター</span><span class="sxs-lookup"><span data-stu-id="e960a-234">Parameter</span></span>|<span data-ttu-id="e960a-235">Description</span><span class="sxs-lookup"><span data-stu-id="e960a-235">Description</span></span>|  
|---------------|-----------------|  
|<span data-ttu-id="e960a-236">IndexName:\<インデックス名 ></span><span class="sxs-lookup"><span data-stu-id="e960a-236">IndexName:\<index name></span></span>|<span data-ttu-id="e960a-237">削除するインデックスの名前。</span><span class="sxs-lookup"><span data-stu-id="e960a-237">The name of the index to delete.</span></span>|  
|<span data-ttu-id="e960a-238">アクティビティ:\<アクティビティ名 ></span><span class="sxs-lookup"><span data-stu-id="e960a-238">Activity:\<activity name></span></span>|<span data-ttu-id="e960a-239">インデックスの削除対象アクティビティの名前です。</span><span class="sxs-lookup"><span data-stu-id="e960a-239">The name of the activity for which the index is deleted.</span></span>|  
|<span data-ttu-id="e960a-240">サーバー:\<サーバー ></span><span class="sxs-lookup"><span data-stu-id="e960a-240">Server:\<server></span></span>|<span data-ttu-id="e960a-241">省略可能: アクティビティが存在するサーバーの名前。</span><span class="sxs-lookup"><span data-stu-id="e960a-241">Optional: The name of the server on which the activity resides.</span></span> <span data-ttu-id="e960a-242">このサーバーは、bm.exe を実行するコンピューターと同じドメインに存在している必要があります。</span><span class="sxs-lookup"><span data-stu-id="e960a-242">The server must be in the same domain as the computer from which you are running bm.exe.</span></span> <span data-ttu-id="e960a-243">サーバー名を指定しなかった場合、既定の名前 (localhost) が使用されます。</span><span class="sxs-lookup"><span data-stu-id="e960a-243">If the server name is not specified, bm.exe uses the default name of localhost.</span></span>|  
|<span data-ttu-id="e960a-244">データベース:\<データベース ></span><span class="sxs-lookup"><span data-stu-id="e960a-244">Database:\<database></span></span>|<span data-ttu-id="e960a-245">省略可能: アクティビティが存在するデータベースの名前。</span><span class="sxs-lookup"><span data-stu-id="e960a-245">Optional: The name of the database on which the activity resides.</span></span> <span data-ttu-id="e960a-246">指定しなかった場合、既定の名前 (BamPrimaryImport) が使用されます。</span><span class="sxs-lookup"><span data-stu-id="e960a-246">If the name is not specified, bm.exe uses the default name BamPrimaryImport.</span></span>|  
  
 <span data-ttu-id="e960a-247">指定されたアクティビティから、特定の名前を指定してインデックスを削除します。</span><span class="sxs-lookup"><span data-stu-id="e960a-247">Deletes the specified index with the given name from the specified activity.</span></span>  
  
 <span data-ttu-id="e960a-248">**使用例**</span><span class="sxs-lookup"><span data-stu-id="e960a-248">**Examples**</span></span>  
  
```  
bm.exe delete-index -IndexName:Idx1 -Activity:PO  
bm.exe delete-index -IndexName:Idx2 -Activity:PO -Server:S1 -Database:BamPI1  
```  
  
## <a name="set-archive-command"></a><span data-ttu-id="e960a-249">set-archive コマンド</span><span class="sxs-lookup"><span data-stu-id="e960a-249">set-archive Command</span></span>  
 <span data-ttu-id="e960a-250">**使用方法**</span><span class="sxs-lookup"><span data-stu-id="e960a-250">**Usage**</span></span>  
  
 <span data-ttu-id="e960a-251">**bm.exe get アーカイブ-アクティビティ:\<アクティビティ > [-サーバー:\<サーバー >] [-データベース:\<データベース >]**</span><span class="sxs-lookup"><span data-stu-id="e960a-251">**bm.exe get-archive -Activity:\<activity> [-Server:\<server>] [-Database:\<database>]**</span></span>  
  
 <span data-ttu-id="e960a-252">**パラメーター**</span><span class="sxs-lookup"><span data-stu-id="e960a-252">**Parameters**</span></span>  
  
|<span data-ttu-id="e960a-253">パラメーター</span><span class="sxs-lookup"><span data-stu-id="e960a-253">Parameter</span></span>|<span data-ttu-id="e960a-254">Description</span><span class="sxs-lookup"><span data-stu-id="e960a-254">Description</span></span>|  
|---------------|-----------------|  
|<span data-ttu-id="e960a-255">アクティビティ:\<アクティビティ名 ></span><span class="sxs-lookup"><span data-stu-id="e960a-255">Activity:\<activity name></span></span>|<span data-ttu-id="e960a-256">動作の表示対象アクティビティの名前です。</span><span class="sxs-lookup"><span data-stu-id="e960a-256">The name of the activity for which the behavior is to be displayed.</span></span>|  
|<span data-ttu-id="e960a-257">サーバー:\<サーバー ></span><span class="sxs-lookup"><span data-stu-id="e960a-257">Server:\<server></span></span>|<span data-ttu-id="e960a-258">省略可能: アクティビティが存在するサーバーの名前。</span><span class="sxs-lookup"><span data-stu-id="e960a-258">Optional: The name of the server on which the activity resides.</span></span> <span data-ttu-id="e960a-259">このサーバーは、bm.exe を実行するコンピューターと同じドメインに存在している必要があります。</span><span class="sxs-lookup"><span data-stu-id="e960a-259">The server must be in the same domain as the computer from which you are running bm.exe.</span></span> <span data-ttu-id="e960a-260">サーバー名を指定しなかった場合、既定の名前 (localhost) が使用されます。</span><span class="sxs-lookup"><span data-stu-id="e960a-260">If the server name is not specified, bm.exe uses the default name of localhost.</span></span>|  
|<span data-ttu-id="e960a-261">データベース:\<データベース ></span><span class="sxs-lookup"><span data-stu-id="e960a-261">Database:\<database></span></span>|<span data-ttu-id="e960a-262">省略可能: アクティビティが存在するデータベースの名前。</span><span class="sxs-lookup"><span data-stu-id="e960a-262">Optional: The name of the database on which the activity resides.</span></span> <span data-ttu-id="e960a-263">指定しなかった場合、既定の名前 (BamPrimaryImport) が使用されます。</span><span class="sxs-lookup"><span data-stu-id="e960a-263">If the name is not specified, bm.exe uses the default name BamPrimaryImport.</span></span>|  
  
 <span data-ttu-id="e960a-264">指定したアクティビティのアーカイブ パッケージの動作 (アクティビティ データのアーカイブまたは削除) を取得します。</span><span class="sxs-lookup"><span data-stu-id="e960a-264">Gets the behavior of the archiving package for the specified activity, whether the archiving package will archive orpurge activity data.</span></span>  
  
 <span data-ttu-id="e960a-265">**使用例**</span><span class="sxs-lookup"><span data-stu-id="e960a-265">**Examples**</span></span>  
  
```  
bm.exe get-archive -Activity:PurchaseOrder  
```  
  
## <a name="set-archive-command"></a><span data-ttu-id="e960a-266">set-archive コマンド</span><span class="sxs-lookup"><span data-stu-id="e960a-266">set-archive Command</span></span>  
 <span data-ttu-id="e960a-267">**使用方法**</span><span class="sxs-lookup"><span data-stu-id="e960a-267">**Usage**</span></span>  
  
 <span data-ttu-id="e960a-268">**bm.exe セット アーカイブ - アクティビティ:\<アクティビティ > - ShouldArchive: True [-サーバー:\<サーバー >] [-データベース:\<データベース >]**</span><span class="sxs-lookup"><span data-stu-id="e960a-268">**bm.exe set-archive -Activity:\<activity> -ShouldArchive:True [-Server:\<server>] [-Database:\<database>]**</span></span>  
  
 <span data-ttu-id="e960a-269">**パラメーター**</span><span class="sxs-lookup"><span data-stu-id="e960a-269">**Parameters**</span></span>  
  
|<span data-ttu-id="e960a-270">パラメーター</span><span class="sxs-lookup"><span data-stu-id="e960a-270">Parameter</span></span>|<span data-ttu-id="e960a-271">Description</span><span class="sxs-lookup"><span data-stu-id="e960a-271">Description</span></span>|  
|---------------|-----------------|  
|<span data-ttu-id="e960a-272">アクティビティ:\<アクティビティ名 ></span><span class="sxs-lookup"><span data-stu-id="e960a-272">Activity:\<activity name></span></span>|<span data-ttu-id="e960a-273">動作の表示対象アクティビティの名前です。</span><span class="sxs-lookup"><span data-stu-id="e960a-273">The name of the activity for which the behavior is to be displayed.</span></span>|  
|<span data-ttu-id="e960a-274">ShouldArchive: True</span><span class="sxs-lookup"><span data-stu-id="e960a-274">ShouldArchive: True</span></span>|<span data-ttu-id="e960a-275">True に設定すると、アクティビティはアーカイブ済みデータベースに移動されます。</span><span class="sxs-lookup"><span data-stu-id="e960a-275">If set to True, the activity is moved to Archive DB.</span></span> <span data-ttu-id="e960a-276">False に設定すると、アーカイブが削除されます。</span><span class="sxs-lookup"><span data-stu-id="e960a-276">If set to False, the activity is purged.</span></span>|  
|<span data-ttu-id="e960a-277">サーバー:\<サーバー ></span><span class="sxs-lookup"><span data-stu-id="e960a-277">Server:\<server></span></span>|<span data-ttu-id="e960a-278">省略可能: アクティビティが存在するサーバーの名前。</span><span class="sxs-lookup"><span data-stu-id="e960a-278">Optional: The name of the server on which the activity resides.</span></span> <span data-ttu-id="e960a-279">このサーバーは、bm.exe を実行するコンピューターと同じドメインに存在している必要があります。</span><span class="sxs-lookup"><span data-stu-id="e960a-279">The server must be in the same domain as the computer from which you are running bm.exe.</span></span> <span data-ttu-id="e960a-280">サーバー名を指定しなかった場合、既定の名前 (localhost) が使用されます。</span><span class="sxs-lookup"><span data-stu-id="e960a-280">If the server name is not specified, bm.exe uses the default name of localhost.</span></span>|  
|<span data-ttu-id="e960a-281">データベース:\<データベース ></span><span class="sxs-lookup"><span data-stu-id="e960a-281">Database:\<database></span></span>|<span data-ttu-id="e960a-282">省略可能: アクティビティが存在するデータベースの名前。</span><span class="sxs-lookup"><span data-stu-id="e960a-282">Optional: The name of the database on which the activity resides.</span></span> <span data-ttu-id="e960a-283">指定しなかった場合、既定の名前 (BamPrimaryImport) が使用されます。</span><span class="sxs-lookup"><span data-stu-id="e960a-283">If the name is not specified, bm.exe uses the default name BamPrimaryImport.</span></span>|  
  
 <span data-ttu-id="e960a-284">指定したアクティビティのデータがアーカイブ済みデータベースに移動されるよう、アーカイブ パッケージの動作を設定します。</span><span class="sxs-lookup"><span data-stu-id="e960a-284">Sets the behavior of the archiving package for the activity specified so that activity data is moved into the Archive DB.</span></span> <span data-ttu-id="e960a-285">既定では、展開済みの新しいアクティビティに対してこの動作が設定されます。</span><span class="sxs-lookup"><span data-stu-id="e960a-285">By default, this behavior is set for new activities that are deployed.</span></span>  
  
 <span data-ttu-id="e960a-286">**使用例**</span><span class="sxs-lookup"><span data-stu-id="e960a-286">**Examples**</span></span>  
  
 <span data-ttu-id="e960a-287">BAM アクティビティ データを削除するには、次のコマンドを実行します。</span><span class="sxs-lookup"><span data-stu-id="e960a-287">To purge the BAM activity data, execute the following:</span></span>  
  
```  
bm.exe set-archive -Activity:PurchaseOrder -ShouldArchive:False  
```  
  
 <span data-ttu-id="e960a-288">BAM アクティビティ データを BAMArchive データベースに移動するには、次のコマンドを実行します。</span><span class="sxs-lookup"><span data-stu-id="e960a-288">To move the BAM activity data to the BAMArchive database, execute the following:</span></span>  
  
```  
bm.exe set-archive -Activity:PurchaseOrder -ShouldArchive:True  
```  
  
## <a name="see-also"></a><span data-ttu-id="e960a-289">参照</span><span class="sxs-lookup"><span data-stu-id="e960a-289">See Also</span></span>  
 [<span data-ttu-id="e960a-290">BAM 管理ユーティリティ</span><span class="sxs-lookup"><span data-stu-id="e960a-290">BAM Management Utility</span></span>](../core/bam-management-utility.md)